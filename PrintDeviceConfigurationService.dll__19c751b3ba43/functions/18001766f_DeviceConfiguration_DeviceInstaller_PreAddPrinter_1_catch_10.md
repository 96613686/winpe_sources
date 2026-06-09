# _DeviceConfiguration::DeviceInstaller::_PreAddPrinter_::_1_::catch$10

- ea: `0x18001766f`
- end: `0x1800176a5`
- name: `_DeviceConfiguration::DeviceInstaller::_PreAddPrinter_::_1_::catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017680`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_PreAddPrinter_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 52) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x6B,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001766f  mov     [rsp+arg_8], rdx
0x180017674  push    rbp
0x180017675  sub     rsp, 30h
0x180017679  mov     rbp, rdx
0x18001767c  mov     rcx, [rbp+78h]; this
0x180017680  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180017687  mov     edx, 6Bh ; 'k'; void *
0x18001768c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017691  mov     [rbp+34h], eax
0x180017694  mov     rax, 0
0x18001769e  add     rsp, 30h
0x1800176a2  pop     rbp
0x1800176a3  retn
```
