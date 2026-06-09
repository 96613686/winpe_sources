# _UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$2

- ea: `0x140011c29`
- end: `0x140011c35`
- name: `_UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a1bc`

## pseudocode

```c
__int64 __fastcall UpdateRegistryForAppUriHandlerPackage_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short>::~vector<unsigned short>(a2 + 88);
}

```

## disassembly

```asm
0x140011c29  lea     rcx, [rdx+58h]
0x140011c30  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
