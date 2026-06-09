# Windows::Security::Isolation::FileDialogBroker::AdviseFirst(IFileDialogEvents *,ulong *)

- ea: `0x140009d20`
- end: `0x140009d8c`
- name: `?AdviseFirst@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIFileDialogEvents@@PEAK@Z`
- size: `108`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, struct IFileDialogEvents *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x140009d20`
- `0x140014010`

## string_xrefs

- `0x140009d67`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AdviseFirst(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IFileDialogEvents *a2,
        unsigned int *a3)
{
  char *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  const char *v8; // r9
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = (char *)this - 24;
  try
  {
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 72LL))(v5);
    v7 = (*(__int64 (__fastcall **)(__int64, struct IFileDialogEvents *, unsigned int *))(*(_QWORD *)v6 + 240LL))(
           v6,
           a2,
           a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x569,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x56C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x140009d20  mov     [rsp+arg_8], rbx
0x140009d25  push    rdi; int
0x140009d26  sub     rsp, 20h
0x140009d2a  mov     rbx, r8
0x140009d2d  mov     rdi, rdx
0x140009d30  add     rcx, 0FFFFFFFFFFFFFFE8h
0x140009d34  mov     rax, [rcx]
0x140009d37  mov     rax, [rax+48h]
0x140009d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d40  mov     r9, rax
0x140009d43  mov     rcx, [rax]
0x140009d46  mov     rax, [rcx+0F0h]
0x140009d4d  mov     r8, rbx
0x140009d50  mov     rdx, rdi
0x140009d53  mov     rcx, r9
0x140009d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d5b  mov     rcx, [rsp+28h]; this
0x140009d60  test    eax, eax
0x140009d62  jns     short loc_140009D78
0x140009d64  mov     r9d, eax; char *
0x140009d67  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140009d6e  mov     edx, 569h; void *
0x140009d73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140009d78  xor     eax, eax
0x140009d7a  jmp     short loc_140009D80
0x140009d7c  mov     eax, [rsp+28h+arg_0]
0x140009d80  mov     rbx, [rsp+28h+arg_8]
0x140009d85  add     rsp, 20h
0x140009d89  pop     rdi
0x140009d8a  retn
```
