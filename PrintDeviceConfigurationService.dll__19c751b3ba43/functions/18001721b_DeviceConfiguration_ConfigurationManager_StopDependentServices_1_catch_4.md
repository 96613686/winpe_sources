# _DeviceConfiguration::ConfigurationManager::_StopDependentServices_::_1_::catch$4

- ea: `0x18001721b`
- end: `0x180017252`
- name: `_DeviceConfiguration::ConfigurationManager::_StopDependentServices_::_1_::catch$4`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x18001722f`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_StopDependentServices_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 168),
    (void *)0x319,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18001721b  mov     [rsp+arg_8], rdx
0x180017220  push    rbp
0x180017221  sub     rsp, 30h
0x180017225  mov     rbp, rdx
0x180017228  mov     rcx, [rbp+0A8h]; this
0x18001722f  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180017236  mov     edx, 319h; void *
0x18001723b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180017240  nop
0x180017241  mov     rax, 0
0x18001724b  add     rsp, 30h
0x18001724f  pop     rbp
0x180017250  retn
```
