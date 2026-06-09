# _DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint_::_1_::catch$7

- ea: `0x1800170b7`
- end: `0x1800170ed`
- name: `_DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint_::_1_::catch$7`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x1800170c8`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x160,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800170b7  mov     [rsp+arg_8], rdx
0x1800170bc  push    rbp
0x1800170bd  sub     rsp, 40h
0x1800170c1  mov     rbp, rdx
0x1800170c4  mov     rcx, [rbp+58h]; this
0x1800170c8  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800170cf  mov     edx, 160h; void *
0x1800170d4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800170d9  mov     [rbp+60h], eax
0x1800170dc  mov     rax, 0
0x1800170e6  add     rsp, 40h
0x1800170ea  pop     rbp
0x1800170eb  retn
```
