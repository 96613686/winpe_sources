# _PrintCore::UserImpersonationHelpers::TryGetUserSidFromSessionId_::_1_::catch$6

- ea: `0x180046515`
- end: `0x180046550`
- name: `_PrintCore::UserImpersonationHelpers::TryGetUserSidFromSessionId_::_1_::catch$6`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180029ff8`

## string_xrefs

- `0x18004652d`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x180046526`: `GetUserSidFromSessionId failed`

## pseudocode

```c
__int64 __fastcall PrintCore::UserImpersonationHelpers::TryGetUserSidFromSessionId_::_1_::catch_6(
        __int64 a1,
        __int64 a2)
{
  const char *v3; // [rsp+20h] [rbp-8h]

  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 104),
    (void *)0xF5,
    (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
    "GetUserSidFromSessionId failed",
    v3);
  return 0;
}

```

## disassembly

```asm
0x180046515  mov     [rsp+arg_8], rdx
0x18004651a  push    rbp; char *
0x18004651b  sub     rsp, 20h
0x18004651f  mov     rbp, rdx
0x180046522  mov     rcx, [rbp+68h]; this
0x180046526  lea     r9, aGetusersidfrom; "GetUserSidFromSessionId failed"
0x18004652d  lea     r8, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x180046534  mov     edx, 0F5h; void *
0x180046539  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18004653e  nop
0x18004653f  mov     rax, 0
0x180046549  add     rsp, 20h
0x18004654d  pop     rbp
0x18004654e  retn
```
