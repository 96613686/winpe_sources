# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x18000a0a0`
- end: `0x18000a117`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800017e4`
- `0x1800017f0`
- `0x18000a0a0`
- `0x18000f010`

## pseudocode

```c
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
0x18000a0a0  test    rcx, rcx
0x18000a0a3  jz      short locret_18000A116
0x18000a0a5  mov     [rsp+arg_0], rbx
0x18000a0aa  push    rdi
0x18000a0ab  sub     rsp, 20h
0x18000a0af  mov     rdi, rcx
0x18000a0b2  mov     rcx, [rcx+18h]
0x18000a0b6  test    rcx, rcx
0x18000a0b9  jz      short loc_18000A0C7
0x18000a0bb  mov     rax, [rcx]
0x18000a0be  mov     rax, [rax+10h]
0x18000a0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c7  mov     qword ptr [rdi+18h], 0
0x18000a0cf  mov     rcx, [rdi+28h]; void *
0x18000a0d3  test    rcx, rcx
0x18000a0d6  jz      short loc_18000A104
0x18000a0d8  lea     rbx, [rcx-8]
0x18000a0dc  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18000a0e3  mov     r8, [rbx]; unsigned __int64
0x18000a0e6  mov     edx, 10h; unsigned __int64
0x18000a0eb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000a0f0  mov     rdx, [rbx]
0x18000a0f3  shl     rdx, 4
0x18000a0f7  add     rdx, 8; unsigned __int64
0x18000a0fb  mov     rcx, rbx; void *
0x18000a0fe  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18000a103  nop
0x18000a104  mov     qword ptr [rdi+28h], 0
0x18000a10c  mov     rbx, [rsp+28h+arg_0]
0x18000a111  add     rsp, 20h
0x18000a115  pop     rdi
0x18000a116  retn
```
