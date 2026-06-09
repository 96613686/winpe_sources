# _DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled_::_1_::catch$0

- ea: `0x180017147`
- end: `0x18001717b`
- name: `_DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180017158`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_IsWindowsProtectedPrintEnabled_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x237,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180017147  mov     [rsp+arg_8], rdx
0x18001714c  push    rbp
0x18001714d  sub     rsp, 20h
0x180017151  mov     rbp, rdx
0x180017154  mov     rcx, [rbp+28h]; this
0x180017158  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x18001715f  mov     edx, 237h; void *
0x180017164  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180017169  nop
0x18001716a  mov     rax, 0
0x180017174  add     rsp, 20h
0x180017178  pop     rbp
0x180017179  retn
```
