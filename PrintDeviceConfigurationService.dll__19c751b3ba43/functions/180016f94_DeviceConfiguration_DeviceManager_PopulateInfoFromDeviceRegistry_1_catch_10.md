# _DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry_::_1_::catch$10

- ea: `0x180016f94`
- end: `0x180016fcd`
- name: `_DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry_::_1_::catch$10`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000c0f0`

## string_xrefs

- `0x180016fa8`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::_PopulateInfoFromDeviceRegistry_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 280),
                           (void *)0x2CC,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016f94  mov     [rsp+arg_8], rdx
0x180016f99  push    rbp
0x180016f9a  sub     rsp, 30h
0x180016f9e  mov     rbp, rdx
0x180016fa1  mov     rcx, [rbp+118h]; this
0x180016fa8  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x180016faf  mov     edx, 2CCh; void *
0x180016fb4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016fb9  mov     [rbp+38h], eax
0x180016fbc  mov     rax, 0
0x180016fc6  add     rsp, 30h
0x180016fca  pop     rbp
0x180016fcb  retn
```
