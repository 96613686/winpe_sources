# _DeviceConfiguration::Device::SetPsaInfoForPrinter_::_1_::catch$0

- ea: `0x18001746b`
- end: `0x1800174a1`
- name: `_DeviceConfiguration::Device::SetPsaInfoForPrinter_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x18001747c`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::SetPsaInfoForPrinter_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0xFF,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001746b  mov     [rsp+arg_8], rdx
0x180017470  push    rbp
0x180017471  sub     rsp, 40h
0x180017475  mov     rbp, rdx
0x180017478  mov     rcx, [rbp+48h]; this
0x18001747c  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x180017483  mov     edx, 0FFh; void *
0x180017488  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001748d  mov     [rbp+50h], eax
0x180017490  mov     rax, 0
0x18001749a  add     rsp, 40h
0x18001749e  pop     rbp
0x18001749f  retn
```
