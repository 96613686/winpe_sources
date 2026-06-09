# CIconOverlayHandler::UpdateRegistry(int)

- ea: `0x1800091c0`
- end: `0x1800091cd`
- name: `?UpdateRegistry@CIconOverlayHandler@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800091d4`

## pseudocode

```c
__int64 __fastcall CIconOverlayHandler::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x67u, (int)a1, a4);
}

```

## disassembly

```asm
0x1800091c0  mov     r8d, ecx; int
0x1800091c3  mov     edx, 67h ; 'g'; unsigned int
0x1800091c8  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
