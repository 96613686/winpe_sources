# _DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback_::_1_::catch$0

- ea: `0x1800169b3`
- end: `0x1800169e9`
- name: `_DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x1800169c4`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::PrintDeviceConfigurationService::_ServiceControlHandlerCallback_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0xAF,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceco"
                                "nfigurationservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800169b3  mov     [rsp+arg_8], rdx
0x1800169b8  push    rbp
0x1800169b9  sub     rsp, 20h
0x1800169bd  mov     rbp, rdx
0x1800169c0  mov     rcx, [rbp+28h]; this
0x1800169c4  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x1800169cb  mov     edx, 0AFh; void *
0x1800169d0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800169d5  mov     [rbp+38h], eax
0x1800169d8  mov     rax, 0
0x1800169e2  add     rsp, 20h
0x1800169e6  pop     rbp
0x1800169e7  retn
```
