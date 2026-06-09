# CRemoveDeviceElevatedHandler::UpdateRegistry(int)

- ea: `0x18000b2a0`
- end: `0x18000b2a8`
- name: `?UpdateRegistry@CRemoveDeviceElevatedHandler@@SAJH@Z`
- size: `8`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000b2b0`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceElevatedHandler::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, a2, (unsigned int)a1, a4);
}

```

## disassembly

```asm
0x18000b2a0  mov     r8d, ecx; int
0x18000b2a3  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
