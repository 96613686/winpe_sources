# _DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown_::_1_::catch$12

- ea: `0x1800169ef`
- end: `0x180016a23`
- name: `_DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown_::_1_::catch$12`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016a00`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::PrintDeviceConfigurationService::_ServiceShutdown_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x90,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800169ef  mov     [rsp+arg_8], rdx
0x1800169f4  push    rbp
0x1800169f5  sub     rsp, 20h
0x1800169f9  mov     rbp, rdx
0x1800169fc  mov     rcx, [rbp+48h]; this
0x180016a00  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x180016a07  mov     edx, 90h; void *
0x180016a0c  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016a11  nop
0x180016a12  mov     rax, 0
0x180016a1c  add     rsp, 20h
0x180016a20  pop     rbp
0x180016a21  retn
```
