# _WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch$40

- ea: `0x18003f32c`
- end: `0x18003f363`
- name: `_WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch$40`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18003f340`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch_40(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 680),
    (void *)0x26D,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003f32c  mov     [rsp+arg_8], rdx
0x18003f331  push    rbp
0x18003f332  sub     rsp, 50h
0x18003f336  mov     rbp, rdx
0x18003f339  mov     rcx, [rbp+2A8h]; this
0x18003f340  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003f347  mov     edx, 26Dh; void *
0x18003f34c  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003f351  nop
0x18003f352  mov     rax, 0
0x18003f35c  add     rsp, 50h
0x18003f360  pop     rbp
0x18003f361  retn
```
