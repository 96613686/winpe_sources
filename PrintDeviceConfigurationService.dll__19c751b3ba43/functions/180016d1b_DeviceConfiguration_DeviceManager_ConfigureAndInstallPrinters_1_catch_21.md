# _DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters_::_1_::catch$21

- ea: `0x180016d1b`
- end: `0x180016d54`
- name: `_DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters_::_1_::catch$21`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180016d2f`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters_::_1_::catch_21(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 376),
                           (void *)0x84,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016d1b  mov     [rsp+arg_8], rdx
0x180016d20  push    rbp
0x180016d21  sub     rsp, 40h
0x180016d25  mov     rbp, rdx
0x180016d28  mov     rcx, [rbp+178h]; this
0x180016d2f  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x180016d36  mov     edx, 84h; void *
0x180016d3b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016d40  mov     [rbp+40h], eax
0x180016d43  mov     rax, 0
0x180016d4d  add     rsp, 40h
0x180016d51  pop     rbp
0x180016d52  retn
```
