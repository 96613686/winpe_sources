# _DeviceConfiguration::DeviceInstaller::_PostAddPrinter_::_1_::catch$3

- ea: `0x180017633`
- end: `0x180017669`
- name: `_DeviceConfiguration::DeviceInstaller::_PostAddPrinter_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017644`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_PostAddPrinter_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0xB6,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017633  mov     [rsp+arg_8], rdx
0x180017638  push    rbp
0x180017639  sub     rsp, 30h
0x18001763d  mov     rbp, rdx
0x180017640  mov     rcx, [rbp+48h]; this
0x180017644  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x18001764b  mov     edx, 0B6h; void *
0x180017650  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017655  mov     [rbp+58h], eax
0x180017658  mov     rax, 0
0x180017662  add     rsp, 30h
0x180017666  pop     rbp
0x180017667  retn
```
