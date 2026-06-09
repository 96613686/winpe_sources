# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x140005000`
- end: `0x14000506d`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `109`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001cdc`
- `0x140005000`
- `0x140017010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x140005053`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140005053`

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
0x140005000  test    rcx, rcx
0x140005003  jz      short locret_14000506C
0x140005005  mov     [rsp+arg_0], rbx
0x14000500a  push    rdi
0x14000500b  sub     rsp, 20h
0x14000500f  mov     rdi, rcx
0x140005012  mov     rcx, [rcx+18h]
0x140005016  test    rcx, rcx
0x140005019  jz      short loc_140005027
0x14000501b  mov     rax, [rcx]
0x14000501e  mov     rax, [rax+10h]
0x140005022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005027  mov     qword ptr [rdi+18h], 0
0x14000502f  mov     rcx, [rdi+28h]; void *
0x140005033  test    rcx, rcx
0x140005036  jz      short loc_14000505A
0x140005038  lea     rbx, [rcx-8]
0x14000503c  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x140005043  mov     r8, [rbx]; unsigned __int64
0x140005046  mov     edx, 10h; unsigned __int64
0x14000504b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140005050  mov     rcx, rbx
0x140005053  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140005059  nop
0x14000505a  mov     qword ptr [rdi+28h], 0
0x140005062  mov     rbx, [rsp+28h+arg_0]
0x140005067  add     rsp, 20h
0x14000506b  pop     rdi
0x14000506c  retn
```
