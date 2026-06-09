# _DeviceConfiguration::Device::RetrievePsaInfo_::_1_::catch$7

- ea: `0x1800173a2`
- end: `0x1800173d8`
- name: `_DeviceConfiguration::Device::RetrievePsaInfo_::_1_::catch$7`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x1800173b3`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::RetrievePsaInfo_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x115,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800173a2  mov     [rsp+arg_8], rdx
0x1800173a7  push    rbp
0x1800173a8  sub     rsp, 20h
0x1800173ac  mov     rbp, rdx
0x1800173af  mov     rcx, [rbp+58h]; this
0x1800173b3  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x1800173ba  mov     edx, 115h; void *
0x1800173bf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800173c4  mov     [rbp+20h], eax
0x1800173c7  mov     rax, 0
0x1800173d1  add     rsp, 20h
0x1800173d5  pop     rbp
0x1800173d6  retn
```
