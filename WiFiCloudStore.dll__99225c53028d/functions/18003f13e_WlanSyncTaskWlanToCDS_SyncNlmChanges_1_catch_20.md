# _WlanSyncTaskWlanToCDS::SyncNlmChanges_::_1_::catch$20

- ea: `0x18003f13e`
- end: `0x18003f175`
- name: `_WlanSyncTaskWlanToCDS::SyncNlmChanges_::_1_::catch$20`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18003f152`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::SyncNlmChanges_::_1_::catch_20(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 600),
    (void *)0x16E,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003f13e  mov     [rsp+arg_8], rdx
0x18003f143  push    rbp
0x18003f144  sub     rsp, 40h
0x18003f148  mov     rbp, rdx
0x18003f14b  mov     rcx, [rbp+258h]; this
0x18003f152  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003f159  mov     edx, 16Eh; void *
0x18003f15e  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003f163  nop
0x18003f164  mov     rax, 0
0x18003f16e  add     rsp, 40h
0x18003f172  pop     rbp
0x18003f173  retn
```
