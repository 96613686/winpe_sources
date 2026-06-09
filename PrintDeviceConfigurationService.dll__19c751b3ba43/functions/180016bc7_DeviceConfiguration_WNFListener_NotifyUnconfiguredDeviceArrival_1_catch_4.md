# _DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival_::_1_::catch$4

- ea: `0x180016bc7`
- end: `0x180016bfb`
- name: `_DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival_::_1_::catch$4`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016bd8`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::_NotifyUnconfiguredDeviceArrival_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x7E,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016bc7  mov     [rsp+arg_8], rdx
0x180016bcc  push    rbp
0x180016bcd  sub     rsp, 20h
0x180016bd1  mov     rbp, rdx
0x180016bd4  mov     rcx, [rbp+28h]; this
0x180016bd8  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x180016bdf  mov     edx, 7Eh ; '~'; void *
0x180016be4  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016be9  nop
0x180016bea  mov     rax, 0
0x180016bf4  add     rsp, 20h
0x180016bf8  pop     rbp
0x180016bf9  retn
```
