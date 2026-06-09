# CCommandHandler::UpdateRegistry(int)

- ea: `0x18000b2d0`
- end: `0x18000b2dd`
- name: `?UpdateRegistry@CCommandHandler@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800091d4`

## pseudocode

```c
__int64 __fastcall CCommandHandler::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x6Au, (int)a1, a4);
}

```

## disassembly

```asm
0x18000b2d0  mov     r8d, ecx; int
0x18000b2d3  mov     edx, 6Ah ; 'j'; unsigned int
0x18000b2d8  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
