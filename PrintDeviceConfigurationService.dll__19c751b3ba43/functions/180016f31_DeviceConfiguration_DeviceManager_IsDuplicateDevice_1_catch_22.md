# _DeviceConfiguration::DeviceManager::_IsDuplicateDevice_::_1_::catch$22

- ea: `0x180016f31`
- end: `0x180016f6a`
- name: `_DeviceConfiguration::DeviceManager::_IsDuplicateDevice_::_1_::catch$22`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180016f45`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::_IsDuplicateDevice_::_1_::catch_22(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 296),
                           (void *)0x28C,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016f31  mov     [rsp+arg_8], rdx
0x180016f36  push    rbp
0x180016f37  sub     rsp, 30h
0x180016f3b  mov     rbp, rdx
0x180016f3e  mov     rcx, [rbp+128h]; this
0x180016f45  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x180016f4c  mov     edx, 28Ch; void *
0x180016f51  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016f56  mov     [rbp+38h], eax
0x180016f59  mov     rax, 0
0x180016f63  add     rsp, 30h
0x180016f67  pop     rbp
0x180016f68  retn
```
