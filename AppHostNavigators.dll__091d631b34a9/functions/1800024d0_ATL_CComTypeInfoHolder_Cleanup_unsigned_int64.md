# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x1800024d0`
- end: `0x18000253c`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `108`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011d4`
- `0x1800016d8`
- `0x1800024d0`
- `0x180014010`

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
      operator delete(v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x1800024d0  test    rcx, rcx
0x1800024d3  jz      short locret_18000253B
0x1800024d5  mov     [rsp+arg_0], rbx
0x1800024da  push    rdi
0x1800024db  sub     rsp, 20h
0x1800024df  mov     rdi, rcx
0x1800024e2  mov     rcx, [rcx+18h]
0x1800024e6  test    rcx, rcx
0x1800024e9  jz      short loc_1800024F7
0x1800024eb  mov     rax, [rcx]
0x1800024ee  mov     rax, [rax+10h]
0x1800024f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f7  mov     qword ptr [rdi+18h], 0
0x1800024ff  mov     rcx, [rdi+28h]; void *
0x180002503  test    rcx, rcx
0x180002506  jz      short loc_180002529
0x180002508  lea     rbx, [rcx-8]
0x18000250c  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180002513  mov     r8, [rbx]; unsigned __int64
0x180002516  mov     edx, 10h; unsigned __int64
0x18000251b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180002520  mov     rcx, rbx; Block
0x180002523  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002528  nop
0x180002529  mov     qword ptr [rdi+28h], 0
0x180002531  mov     rbx, [rsp+28h+arg_0]
0x180002536  add     rsp, 20h
0x18000253a  pop     rdi
0x18000253b  retn
```
