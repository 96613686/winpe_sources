# _DeviceConfiguration::Device::RestartDevice_::_1_::catch$3

- ea: `0x180017351`
- end: `0x18001738a`
- name: `_DeviceConfiguration::Device::RestartDevice_::_1_::catch$3`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017365`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::RestartDevice_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0xF2,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017351  mov     [rsp+arg_8], rdx
0x180017356  push    rbp
0x180017357  sub     rsp, 30h
0x18001735b  mov     rbp, rdx
0x18001735e  mov     rcx, [rbp+88h]; this
0x180017365  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x18001736c  mov     edx, 0F2h; void *
0x180017371  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017376  mov     [rbp+30h], eax
0x180017379  mov     rax, 0
0x180017383  add     rsp, 30h
0x180017387  pop     rbp
0x180017388  retn
```
