# _DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback_::_1_::catch$6

- ea: `0x180016a87`
- end: `0x180016abe`
- name: `_DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback_::_1_::catch$6`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016a9b`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 152),
    (void *)0xE1,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016a87  mov     [rsp+arg_8], rdx
0x180016a8c  push    rbp
0x180016a8d  sub     rsp, 30h
0x180016a91  mov     rbp, rdx
0x180016a94  mov     rcx, [rbp+98h]; this
0x180016a9b  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x180016aa2  mov     edx, 0E1h; void *
0x180016aa7  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016aac  nop
0x180016aad  mov     rax, 0
0x180016ab7  add     rsp, 30h
0x180016abb  pop     rbp
0x180016abc  retn
```
