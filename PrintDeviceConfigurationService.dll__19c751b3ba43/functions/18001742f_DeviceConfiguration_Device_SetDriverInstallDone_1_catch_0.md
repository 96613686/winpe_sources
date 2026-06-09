# _DeviceConfiguration::Device::SetDriverInstallDone_::_1_::catch$0

- ea: `0x18001742f`
- end: `0x180017465`
- name: `_DeviceConfiguration::Device::SetDriverInstallDone_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017440`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::SetDriverInstallDone_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0xA4,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001742f  mov     [rsp+arg_8], rdx
0x180017434  push    rbp
0x180017435  sub     rsp, 30h
0x180017439  mov     rbp, rdx
0x18001743c  mov     rcx, [rbp+78h]; this
0x180017440  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x180017447  mov     edx, 0A4h; void *
0x18001744c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017451  mov     [rbp+30h], eax
0x180017454  mov     rax, 0
0x18001745e  add     rsp, 30h
0x180017462  pop     rbp
0x180017463  retn
```
