# _DeviceConfiguration::DeviceInstaller::_TrySetPsaInformation_::_1_::catch$1

- ea: `0x1800176bd`
- end: `0x1800176f3`
- name: `_DeviceConfiguration::DeviceInstaller::_TrySetPsaInformation_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x1800176ce`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_TrySetPsaInformation_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x177,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800176bd  mov     [rsp+arg_8], rdx
0x1800176c2  push    rbp
0x1800176c3  sub     rsp, 30h
0x1800176c7  mov     rbp, rdx
0x1800176ca  mov     rcx, [rbp+38h]; this
0x1800176ce  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800176d5  mov     edx, 177h; void *
0x1800176da  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800176df  mov     [rbp+40h], eax
0x1800176e2  mov     rax, 0
0x1800176ec  add     rsp, 30h
0x1800176f0  pop     rbp
0x1800176f1  retn
```
