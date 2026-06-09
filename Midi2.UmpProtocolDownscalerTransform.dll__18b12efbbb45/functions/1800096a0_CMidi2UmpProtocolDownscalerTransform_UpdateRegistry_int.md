# CMidi2UmpProtocolDownscalerTransform::UpdateRegistry(int)

- ea: `0x1800096a0`
- end: `0x1800096ab`
- name: `?UpdateRegistry@CMidi2UmpProtocolDownscalerTransform@@SAJH@Z`
- size: `11`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800096b4`

## pseudocode

```c
__int64 __fastcall CMidi2UmpProtocolDownscalerTransform::UpdateRegistry(ATL::CAtlModule *a1, __int64 a2)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, a2, (int)a1, 0);
}

```

## disassembly

```asm
0x1800096a0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800096a3  mov     r8d, ecx; int
0x1800096a6  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
