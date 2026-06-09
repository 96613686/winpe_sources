# _DeviceConfiguration::ConfigurationManager::_RemoveInternetPrintComponents_::_1_::catch$0

- ea: `0x180017181`
- end: `0x1800171b5`
- name: `_DeviceConfiguration::ConfigurationManager::_RemoveInternetPrintComponents_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180017192`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_RemoveInternetPrintComponents_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x2EE,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180017181  mov     [rsp+arg_8], rdx
0x180017186  push    rbp
0x180017187  sub     rsp, 30h
0x18001718b  mov     rbp, rdx
0x18001718e  mov     rcx, [rbp+38h]; this
0x180017192  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180017199  mov     edx, 2EEh; void *
0x18001719e  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800171a3  nop
0x1800171a4  mov     rax, 0
0x1800171ae  add     rsp, 30h
0x1800171b2  pop     rbp
0x1800171b3  retn
```
