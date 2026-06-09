# _DeviceConfiguration::WNFListener::SubscribeToWNFNotifications_::_1_::catch$10

- ea: `0x180016b02`
- end: `0x180016b39`
- name: `_DeviceConfiguration::WNFListener::SubscribeToWNFNotifications_::_1_::catch$10`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016b16`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::SubscribeToWNFNotifications_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 216),
    (void *)0x61,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016b02  mov     [rsp+arg_8], rdx
0x180016b07  push    rbp
0x180016b08  sub     rsp, 20h
0x180016b0c  mov     rbp, rdx
0x180016b0f  mov     rcx, [rbp+0D8h]; this
0x180016b16  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x180016b1d  mov     edx, 61h ; 'a'; void *
0x180016b22  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016b27  nop
0x180016b28  mov     rax, 0
0x180016b32  add     rsp, 20h
0x180016b36  pop     rbp
0x180016b37  retn
```
