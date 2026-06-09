# _DeviceConfiguration::PrintDeviceConfigurationService::s_StopCallback_::_1_::catch$0

- ea: `0x180016a29`
- end: `0x180016a5d`
- name: `_DeviceConfiguration::PrintDeviceConfigurationService::s_StopCallback_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016a3a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::PrintDeviceConfigurationService::s_StopCallback_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0xB5,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016a29  mov     [rsp+arg_8], rdx
0x180016a2e  push    rbp
0x180016a2f  sub     rsp, 20h
0x180016a33  mov     rbp, rdx
0x180016a36  mov     rcx, [rbp+28h]; this
0x180016a3a  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x180016a41  mov     edx, 0B5h; void *
0x180016a46  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016a4b  nop
0x180016a4c  mov     rax, 0
0x180016a56  add     rsp, 20h
0x180016a5a  pop     rbp
0x180016a5b  retn
```
