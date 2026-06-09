# _DeviceConfiguration::Device::SetDeviceInstallationState_::_1_::catch$2

- ea: `0x1800173f0`
- end: `0x180017429`
- name: `_DeviceConfiguration::Device::SetDeviceInstallationState_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017404`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::SetDeviceInstallationState_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0xE3,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800173f0  mov     [rsp+arg_8], rdx
0x1800173f5  push    rbp
0x1800173f6  sub     rsp, 30h
0x1800173fa  mov     rbp, rdx
0x1800173fd  mov     rcx, [rbp+0A8h]; this
0x180017404  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x18001740b  mov     edx, 0E3h; void *
0x180017410  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017415  mov     [rbp+30h], eax
0x180017418  mov     rax, 0
0x180017422  add     rsp, 30h
0x180017426  pop     rbp
0x180017427  retn
```
