# _DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange_::_1_::catch$4

- ea: `0x180016c01`
- end: `0x180016c35`
- name: `_DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange_::_1_::catch$4`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016c12`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::_NotifyWindowsProtectedPrintConfigurationChange_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x96,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016c01  mov     [rsp+arg_8], rdx
0x180016c06  push    rbp
0x180016c07  sub     rsp, 20h
0x180016c0b  mov     rbp, rdx
0x180016c0e  mov     rcx, [rbp+48h]; this
0x180016c12  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x180016c19  mov     edx, 96h; void *
0x180016c1e  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016c23  nop
0x180016c24  mov     rax, 0
0x180016c2e  add     rsp, 20h
0x180016c32  pop     rbp
0x180016c33  retn
```
