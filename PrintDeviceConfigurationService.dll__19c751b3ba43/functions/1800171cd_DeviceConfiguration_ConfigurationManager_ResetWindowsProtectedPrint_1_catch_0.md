# _DeviceConfiguration::ConfigurationManager::_ResetWindowsProtectedPrint_::_1_::catch$0

- ea: `0x1800171cd`
- end: `0x180017203`
- name: `_DeviceConfiguration::ConfigurationManager::_ResetWindowsProtectedPrint_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x1800171de`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_ResetWindowsProtectedPrint_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x187,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800171cd  mov     [rsp+arg_8], rdx
0x1800171d2  push    rbp
0x1800171d3  sub     rsp, 30h
0x1800171d7  mov     rbp, rdx
0x1800171da  mov     rcx, [rbp+38h]; this
0x1800171de  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800171e5  mov     edx, 187h; void *
0x1800171ea  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800171ef  mov     [rbp+40h], eax
0x1800171f2  mov     rax, 0
0x1800171fc  add     rsp, 30h
0x180017200  pop     rbp
0x180017201  retn
```
