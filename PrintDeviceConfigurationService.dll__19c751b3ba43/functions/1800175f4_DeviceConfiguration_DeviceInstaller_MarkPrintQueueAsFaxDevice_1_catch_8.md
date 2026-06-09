# _DeviceConfiguration::DeviceInstaller::_MarkPrintQueueAsFaxDevice_::_1_::catch$8

- ea: `0x1800175f4`
- end: `0x18001762d`
- name: `_DeviceConfiguration::DeviceInstaller::_MarkPrintQueueAsFaxDevice_::_1_::catch$8`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017608`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_MarkPrintQueueAsFaxDevice_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x168,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800175f4  mov     [rsp+arg_8], rdx
0x1800175f9  push    rbp
0x1800175fa  sub     rsp, 40h
0x1800175fe  mov     rbp, rdx
0x180017601  mov     rcx, [rbp+0F8h]; this
0x180017608  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x18001760f  mov     edx, 168h; void *
0x180017614  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017619  mov     [rbp+40h], eax
0x18001761c  mov     rax, 0
0x180017626  add     rsp, 40h
0x18001762a  pop     rbp
0x18001762b  retn
```
