# _WlanSyncTaskCommon::Start_::_1_::catch$16

- ea: `0x18003ec8c`
- end: `0x18003ecc5`
- name: `_WlanSyncTaskCommon::Start_::_1_::catch$16`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002e55c`

## string_xrefs

- `0x18003eca0`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskCommon::Start_::_1_::catch_16(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 424),
                           (void *)0x16F,
                           (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003ec8c  mov     [rsp+arg_8], rdx
0x18003ec91  push    rbp
0x18003ec92  sub     rsp, 20h
0x18003ec96  mov     rbp, rdx
0x18003ec99  mov     rcx, [rbp+1A8h]; this
0x18003eca0  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003eca7  mov     edx, 16Fh; void *
0x18003ecac  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003ecb1  mov     [rbp+20h], eax
0x18003ecb4  mov     rax, 0
0x18003ecbe  add     rsp, 20h
0x18003ecc2  pop     rbp
0x18003ecc3  retn
```
