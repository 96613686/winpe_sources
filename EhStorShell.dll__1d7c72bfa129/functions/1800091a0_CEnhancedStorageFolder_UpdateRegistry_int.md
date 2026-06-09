# CEnhancedStorageFolder::UpdateRegistry(int)

- ea: `0x1800091a0`
- end: `0x1800091ad`
- name: `?UpdateRegistry@CEnhancedStorageFolder@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800091d4`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageFolder::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x69u, (int)a1, a4);
}

```

## disassembly

```asm
0x1800091a0  mov     r8d, ecx; int
0x1800091a3  mov     edx, 69h ; 'i'; unsigned int
0x1800091a8  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
