# _DeviceConfiguration::WNFListener::_IsWPPConfigurationNeededAfterUpgrade_::_1_::catch$0

- ea: `0x180016b8d`
- end: `0x180016bc1`
- name: `_DeviceConfiguration::WNFListener::_IsWPPConfigurationNeededAfterUpgrade_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016b9e`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::_IsWPPConfigurationNeededAfterUpgrade_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0xC1,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016b8d  mov     [rsp+arg_8], rdx
0x180016b92  push    rbp
0x180016b93  sub     rsp, 20h
0x180016b97  mov     rbp, rdx
0x180016b9a  mov     rcx, [rbp+28h]; this
0x180016b9e  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x180016ba5  mov     edx, 0C1h; void *
0x180016baa  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016baf  nop
0x180016bb0  mov     rax, 0
0x180016bba  add     rsp, 20h
0x180016bbe  pop     rbp
0x180016bbf  retn
```
