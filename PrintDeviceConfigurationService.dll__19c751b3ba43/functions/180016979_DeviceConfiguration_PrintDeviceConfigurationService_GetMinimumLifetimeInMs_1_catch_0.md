# _DeviceConfiguration::PrintDeviceConfigurationService::_GetMinimumLifetimeInMs_::_1_::catch$0

- ea: `0x180016979`
- end: `0x1800169ad`
- name: `_DeviceConfiguration::PrintDeviceConfigurationService::_GetMinimumLifetimeInMs_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x18001698a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::PrintDeviceConfigurationService::_GetMinimumLifetimeInMs_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0xF0,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016979  mov     [rsp+arg_8], rdx
0x18001697e  push    rbp
0x18001697f  sub     rsp, 20h
0x180016983  mov     rbp, rdx
0x180016986  mov     rcx, [rbp+28h]; this
0x18001698a  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x180016991  mov     edx, 0F0h; void *
0x180016996  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18001699b  nop
0x18001699c  mov     rax, 0
0x1800169a6  add     rsp, 20h
0x1800169aa  pop     rbp
0x1800169ab  retn
```
