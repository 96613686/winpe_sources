# _WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch$38

- ea: `0x18003f26c`
- end: `0x18003f2a3`
- name: `_WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch$38`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18003f280`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch_38(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 680),
    (void *)0x24A,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003f26c  mov     [rsp+arg_8], rdx
0x18003f271  push    rbp
0x18003f272  sub     rsp, 50h
0x18003f276  mov     rbp, rdx
0x18003f279  mov     rcx, [rbp+2A8h]; this
0x18003f280  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003f287  mov     edx, 24Ah; void *
0x18003f28c  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003f291  nop
0x18003f292  mov     rax, 0
0x18003f29c  add     rsp, 50h
0x18003f2a0  pop     rbp
0x18003f2a1  retn
```
