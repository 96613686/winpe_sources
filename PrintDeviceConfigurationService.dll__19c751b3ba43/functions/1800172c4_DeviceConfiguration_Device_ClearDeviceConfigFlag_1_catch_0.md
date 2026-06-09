# _DeviceConfiguration::Device::ClearDeviceConfigFlag_::_1_::catch$0

- ea: `0x1800172c4`
- end: `0x1800172fd`
- name: `_DeviceConfiguration::Device::ClearDeviceConfigFlag_::_1_::catch$0`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x1800172d8`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::ClearDeviceConfigFlag_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0xC9,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800172c4  mov     [rsp+arg_8], rdx
0x1800172c9  push    rbp
0x1800172ca  sub     rsp, 40h
0x1800172ce  mov     rbp, rdx
0x1800172d1  mov     rcx, [rbp+98h]; this
0x1800172d8  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x1800172df  mov     edx, 0C9h; void *
0x1800172e4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800172e9  mov     [rbp+40h], eax
0x1800172ec  mov     rax, 0
0x1800172f6  add     rsp, 40h
0x1800172fa  pop     rbp
0x1800172fb  retn
```
