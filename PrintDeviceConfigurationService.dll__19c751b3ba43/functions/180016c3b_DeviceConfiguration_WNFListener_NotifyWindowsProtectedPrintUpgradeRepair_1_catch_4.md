# _DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair_::_1_::catch$4

- ea: `0x180016c3b`
- end: `0x180016c6f`
- name: `_DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair_::_1_::catch$4`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016c4c`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintUpgradeRepair_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0xAE,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016c3b  mov     [rsp+arg_8], rdx
0x180016c40  push    rbp
0x180016c41  sub     rsp, 20h
0x180016c45  mov     rbp, rdx
0x180016c48  mov     rcx, [rbp+28h]; this
0x180016c4c  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x180016c53  mov     edx, 0AEh; void *
0x180016c58  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016c5d  nop
0x180016c5e  mov     rax, 0
0x180016c68  add     rsp, 20h
0x180016c6c  pop     rbp
0x180016c6d  retn
```
