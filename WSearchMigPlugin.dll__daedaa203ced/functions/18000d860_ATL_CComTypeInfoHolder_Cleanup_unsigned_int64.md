# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x18000d860`
- end: `0x18000d8e0`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `128`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002714`
- `0x180002720`
- `0x18000d860`
- `0x180018010`

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
0x18000d860  test    rcx, rcx
0x18000d863  jz      short locret_18000D8DF
0x18000d865  push    rdi
0x18000d866  sub     rsp, 30h
0x18000d86a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000d873  mov     [rsp+38h+arg_0], rbx
0x18000d878  mov     rdi, rcx
0x18000d87b  mov     rcx, [rcx+18h]
0x18000d87f  test    rcx, rcx
0x18000d882  jz      short loc_18000D890
0x18000d884  mov     rax, [rcx]
0x18000d887  mov     rax, [rax+10h]
0x18000d88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d890  mov     qword ptr [rdi+18h], 0
0x18000d898  mov     rcx, [rdi+28h]; void *
0x18000d89c  test    rcx, rcx
0x18000d89f  jz      short loc_18000D8CD
0x18000d8a1  lea     rbx, [rcx-8]
0x18000d8a5  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18000d8ac  mov     r8, [rbx]; unsigned __int64
0x18000d8af  mov     edx, 10h; unsigned __int64
0x18000d8b4  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000d8b9  mov     rdx, [rbx]
0x18000d8bc  shl     rdx, 4
0x18000d8c0  add     rdx, 8; unsigned __int64
0x18000d8c4  mov     rcx, rbx; void *
0x18000d8c7  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18000d8cc  nop
0x18000d8cd  mov     qword ptr [rdi+28h], 0
0x18000d8d5  mov     rbx, [rsp+38h+arg_0]
0x18000d8da  add     rsp, 30h
0x18000d8de  pop     rdi
0x18000d8df  retn
```
