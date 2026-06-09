# _DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint_::_1_::catch$2

- ea: `0x180016fe5`
- end: `0x18001701b`
- name: `_DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint_::_1_::catch$2`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180016ff6`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::ConfigureWindowsProtectedPrint_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x97,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016fe5  mov     [rsp+arg_8], rdx
0x180016fea  push    rbp
0x180016feb  sub     rsp, 30h
0x180016fef  mov     rbp, rdx
0x180016ff2  mov     rcx, [rbp+38h]; this
0x180016ff6  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180016ffd  mov     edx, 97h; void *
0x180017002  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017007  mov     [rbp+40h], eax
0x18001700a  mov     rax, 0
0x180017014  add     rsp, 30h
0x180017018  pop     rbp
0x180017019  retn
```
