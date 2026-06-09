# _DeviceConfiguration::DeviceInstaller::_AddPrinter_::_1_::catch$15

- ea: `0x180017501`
- end: `0x18001753a`
- name: `_DeviceConfiguration::DeviceInstaller::_AddPrinter_::_1_::catch$15`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017515`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_AddPrinter_::_1_::catch_15(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 1944),
                           (void *)0xA3,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017501  mov     [rsp+arg_8], rdx
0x180017506  push    rbp
0x180017507  sub     rsp, 30h
0x18001750b  mov     rbp, rdx
0x18001750e  mov     rcx, [rbp+798h]; this
0x180017515  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x18001751c  mov     edx, 0A3h; void *
0x180017521  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017526  mov     [rbp+30h], eax
0x180017529  mov     rax, 0
0x180017533  add     rsp, 30h
0x180017537  pop     rbp
0x180017538  retn
```
