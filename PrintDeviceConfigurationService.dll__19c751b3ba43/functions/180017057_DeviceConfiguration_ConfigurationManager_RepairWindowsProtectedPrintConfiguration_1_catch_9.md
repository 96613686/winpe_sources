# _DeviceConfiguration::ConfigurationManager::RepairWindowsProtectedPrintConfiguration_::_1_::catch$9

- ea: `0x180017057`
- end: `0x18001708d`
- name: `_DeviceConfiguration::ConfigurationManager::RepairWindowsProtectedPrintConfiguration_::_1_::catch$9`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017068`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::RepairWindowsProtectedPrintConfiguration_::_1_::catch_9(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0xC6,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017057  mov     [rsp+arg_8], rdx
0x18001705c  push    rbp
0x18001705d  sub     rsp, 40h
0x180017061  mov     rbp, rdx
0x180017064  mov     rcx, [rbp+48h]; this
0x180017068  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x18001706f  mov     edx, 0C6h; void *
0x180017074  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017079  mov     [rbp+50h], eax
0x18001707c  mov     rax, 0
0x180017086  add     rsp, 40h
0x18001708a  pop     rbp
0x18001708b  retn
```
