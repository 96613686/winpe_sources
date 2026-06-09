# ATL::CComModule::UpdateRegistryFromResourceD(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180021f90`
- end: `0x180021f96`
- name: `?UpdateRegistryFromResourceD@CComModule@ATL@@UEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `6`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceD(
        ATL::CComModule *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return 2147500037LL;
}

```

## disassembly

```asm
0x180021f90  mov     eax, 80004005h
0x180021f95  retn
```
