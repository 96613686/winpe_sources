# _WlanSyncTaskCDSToWlan::DoWork_::_1_::catch$27

- ea: `0x18003ed91`
- end: `0x18003edc8`
- name: `_WlanSyncTaskCDSToWlan::DoWork_::_1_::catch$27`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18003eda5`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskCDSToWlan::DoWork_::_1_::catch_27(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 1224),
    (void *)0x326,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003ed91  mov     [rsp+arg_8], rdx
0x18003ed96  push    rbp
0x18003ed97  sub     rsp, 50h
0x18003ed9b  mov     rbp, rdx
0x18003ed9e  mov     rcx, [rbp+4C8h]; this
0x18003eda5  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003edac  mov     edx, 326h; void *
0x18003edb1  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003edb6  nop
0x18003edb7  mov     rax, 0
0x18003edc1  add     rsp, 50h
0x18003edc5  pop     rbp
0x18003edc6  retn
```
