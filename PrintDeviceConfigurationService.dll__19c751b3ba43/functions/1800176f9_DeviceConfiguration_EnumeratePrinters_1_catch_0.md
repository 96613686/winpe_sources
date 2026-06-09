# _DeviceConfiguration::EnumeratePrinters_::_1_::catch$0

- ea: `0x1800176f9`
- end: `0x18001772f`
- name: `_DeviceConfiguration::EnumeratePrinters_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x18001770a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\util.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::EnumeratePrinters_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 104) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 88),
                            (void *)0x21,
                            (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\util.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x1800176f9  mov     [rsp+arg_8], rdx
0x1800176fe  push    rbp
0x1800176ff  sub     rsp, 40h
0x180017703  mov     rbp, rdx
0x180017706  mov     rcx, [rbp+58h]; this
0x18001770a  lea     r8, aPrintscanPrint_4; "printscan\\print\\spooler\\configuratio"...
0x180017711  mov     edx, 21h ; '!'; void *
0x180017716  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001771b  mov     [rbp+68h], eax
0x18001771e  mov     rax, 0
0x180017728  add     rsp, 40h
0x18001772c  pop     rbp
0x18001772d  retn
```
