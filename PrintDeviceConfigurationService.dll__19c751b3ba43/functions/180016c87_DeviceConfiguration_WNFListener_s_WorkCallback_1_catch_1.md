# _DeviceConfiguration::WNFListener::s_WorkCallback_::_1_::catch$1

- ea: `0x180016c87`
- end: `0x180016cbb`
- name: `_DeviceConfiguration::WNFListener::s_WorkCallback_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000bfb4`

## string_xrefs

- `0x180016c98`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::WNFListener::s_WorkCallback_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0xEF,
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180016c87  mov     [rsp+arg_8], rdx
0x180016c8c  push    rbp
0x180016c8d  sub     rsp, 30h
0x180016c91  mov     rbp, rdx
0x180016c94  mov     rcx, [rbp+38h]; this
0x180016c98  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x180016c9f  mov     edx, 0EFh; void *
0x180016ca4  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180016ca9  nop
0x180016caa  mov     rax, 0
0x180016cb4  add     rsp, 30h
0x180016cb8  pop     rbp
0x180016cb9  retn
```
