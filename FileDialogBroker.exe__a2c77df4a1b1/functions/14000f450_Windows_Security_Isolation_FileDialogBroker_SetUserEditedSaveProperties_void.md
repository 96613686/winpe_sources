# Windows::Security::Isolation::FileDialogBroker::SetUserEditedSaveProperties(void)

- ea: `0x14000f450`
- end: `0x14000f4a4`
- name: `?SetUserEditedSaveProperties@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `84`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000f450`
- `0x140014010`

## string_xrefs

- `0x14000f485`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetUserEditedSaveProperties(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  char *v1; // rcx
  __int64 v2; // rax
  int v3; // eax
  const char *v4; // r9
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (char *)this - 24;
  try
  {
    v2 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v1 + 72LL))(v1);
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 168LL))(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x521,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v3,
        v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x524,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000f450  sub     rsp, 28h
0x14000f454  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000f458  mov     rax, [rcx]
0x14000f45b  mov     rax, [rax+48h]
0x14000f45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f464  mov     rdx, rax
0x14000f467  mov     rcx, [rax]
0x14000f46a  mov     rax, [rcx+0A8h]
0x14000f471  mov     rcx, rdx
0x14000f474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f479  mov     rcx, [rsp+28h]; this
0x14000f47e  test    eax, eax
0x14000f480  jns     short loc_14000F496
0x14000f482  mov     r9d, eax; char *
0x14000f485  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f48c  mov     edx, 521h; void *
0x14000f491  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f496  xor     eax, eax
0x14000f498  jmp     short loc_14000F49E
0x14000f49a  mov     eax, [rsp+28h+arg_0]
0x14000f49e  add     rsp, 28h
0x14000f4a2  retn
```
