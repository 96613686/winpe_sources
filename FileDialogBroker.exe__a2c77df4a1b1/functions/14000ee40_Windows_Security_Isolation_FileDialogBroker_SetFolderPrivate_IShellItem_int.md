# Windows::Security::Isolation::FileDialogBroker::SetFolderPrivate(IShellItem *,int)

- ea: `0x14000ee40`
- end: `0x14000eeac`
- name: `?SetFolderPrivate@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItem@@H@Z`
- size: `108`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000ee40`
- `0x140014010`

## string_xrefs

- `0x14000ee87`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetFolderPrivate(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem *a2,
        unsigned int a3)
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
    v7 = (*(__int64 (__fastcall **)(__int64, struct IShellItem *, _QWORD))(*(_QWORD *)v6 + 136LL))(v6, a2, a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x501,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x504,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000ee40  mov     [rsp+arg_8], rbx
0x14000ee45  push    rdi; int
0x14000ee46  sub     rsp, 20h
0x14000ee4a  mov     ebx, r8d
0x14000ee4d  mov     rdi, rdx
0x14000ee50  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000ee54  mov     rax, [rcx]
0x14000ee57  mov     rax, [rax+48h]
0x14000ee5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee60  mov     r9, rax
0x14000ee63  mov     rcx, [rax]
0x14000ee66  mov     rax, [rcx+88h]
0x14000ee6d  mov     r8d, ebx
0x14000ee70  mov     rdx, rdi
0x14000ee73  mov     rcx, r9
0x14000ee76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee7b  mov     rcx, [rsp+28h]; this
0x14000ee80  test    eax, eax
0x14000ee82  jns     short loc_14000EE98
0x14000ee84  mov     r9d, eax; char *
0x14000ee87  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000ee8e  mov     edx, 501h; void *
0x14000ee93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000ee98  xor     eax, eax
0x14000ee9a  jmp     short loc_14000EEA0
0x14000ee9c  mov     eax, [rsp+28h+arg_0]
0x14000eea0  mov     rbx, [rsp+28h+arg_8]
0x14000eea5  add     rsp, 20h
0x14000eea9  pop     rdi
0x14000eeaa  retn
```
