# CContextMenuHandler::UpdateRegistry(int)

- ea: `0x180009180`
- end: `0x18000918d`
- name: `?UpdateRegistry@CContextMenuHandler@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800091d4`

## pseudocode

```c
__int64 __fastcall CContextMenuHandler::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x66u, (int)a1, a4);
}

```

## disassembly

```asm
0x180009180  mov     r8d, ecx; int
0x180009183  mov     edx, 66h ; 'f'; unsigned int
0x180009188  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
