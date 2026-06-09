# ATL::CComModule::UpdateRegistryFromResourceS(char const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180007010`
- end: `0x180007015`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@UEAAJPEBDHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `5`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, const char *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006b14`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const char *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(this, a2, a3, a4);
}

```

## disassembly

```asm
0x180007010  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBDHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(char const *,int,ATL::_ATL_REGMAP_ENTRY *)
```
