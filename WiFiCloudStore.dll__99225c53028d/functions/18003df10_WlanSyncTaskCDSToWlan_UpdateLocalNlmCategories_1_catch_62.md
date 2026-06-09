# _WlanSyncTaskCDSToWlan::UpdateLocalNlmCategories_::_1_::catch$62

- ea: `0x18003df10`
- end: `0x18003df47`
- name: `_WlanSyncTaskCDSToWlan::UpdateLocalNlmCategories_::_1_::catch$62`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18003df24`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskCDSToWlan::UpdateLocalNlmCategories_::_1_::catch_62(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 584),
    (void *)0x383,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003df10  mov     [rsp+arg_8], rdx
0x18003df15  push    rbp
0x18003df16  sub     rsp, 40h
0x18003df1a  mov     rbp, rdx
0x18003df1d  mov     rcx, [rbp+248h]; this
0x18003df24  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003df2b  mov     edx, 383h; void *
0x18003df30  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003df35  nop
0x18003df36  mov     rax, 0
0x18003df40  add     rsp, 40h
0x18003df44  pop     rbp
0x18003df45  retn
```
