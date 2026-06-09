# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x180003300`
- end: `0x18000336d`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `109`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800019f4`
- `0x180003300`
- `0x18000a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180003353`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003353`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  char *v3; // rcx
  char *v4; // rbx

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 24) = 0;
    v3 = *(char **)(a1 + 40);
    if ( v3 )
    {
      v4 = v3 - 8;
      `eh vector destructor iterator'(v3, 0x10u, *((_QWORD *)v3 - 1), (void (*)(void *))ATL::CComBSTR::~CComBSTR);
      operator delete[](v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180003300  test    rcx, rcx
0x180003303  jz      short locret_18000336C
0x180003305  mov     [rsp+arg_0], rbx
0x18000330a  push    rdi
0x18000330b  sub     rsp, 20h
0x18000330f  mov     rdi, rcx
0x180003312  mov     rcx, [rcx+18h]
0x180003316  test    rcx, rcx
0x180003319  jz      short loc_180003327
0x18000331b  mov     rax, [rcx]
0x18000331e  mov     rax, [rax+10h]
0x180003322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003327  mov     qword ptr [rdi+18h], 0
0x18000332f  mov     rcx, [rdi+28h]; void *
0x180003333  test    rcx, rcx
0x180003336  jz      short loc_18000335A
0x180003338  lea     rbx, [rcx-8]
0x18000333c  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180003343  mov     r8, [rbx]; unsigned __int64
0x180003346  mov     edx, 10h; unsigned __int64
0x18000334b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180003350  mov     rcx, rbx
0x180003353  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003359  nop
0x18000335a  mov     qword ptr [rdi+28h], 0
0x180003362  mov     rbx, [rsp+28h+arg_0]
0x180003367  add     rsp, 20h
0x18000336b  pop     rdi
0x18000336c  retn
```
