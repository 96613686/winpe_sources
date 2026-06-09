# _DeviceConfiguration::Device::Initalize_::_1_::catch$0

- ea: `0x180017303`
- end: `0x180017339`
- name: `_DeviceConfiguration::Device::Initalize_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180017314`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::Initalize_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x37,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017303  mov     [rsp+arg_8], rdx
0x180017308  push    rbp
0x180017309  sub     rsp, 20h
0x18001730d  mov     rbp, rdx
0x180017310  mov     rcx, [rbp+38h]; this
0x180017314  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x18001731b  mov     edx, 37h ; '7'; void *
0x180017320  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017325  mov     [rbp+40h], eax
0x180017328  mov     rax, 0
0x180017332  add     rsp, 20h
0x180017336  pop     rbp
0x180017337  retn
```
