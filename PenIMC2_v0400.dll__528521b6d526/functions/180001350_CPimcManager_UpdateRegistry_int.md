# CPimcManager::UpdateRegistry(int)

- ea: `0x180001350`
- end: `0x18000135f`
- name: `?UpdateRegistry@CPimcManager@@SAJH@Z`
- size: `15`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800057c0`

## pseudocode

```c
__int64 __fastcall CPimcManager::UpdateRegistry(ATL::CAtlModule *a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResource(a1, 0x66u, (int)a1, 0);
}

```

## disassembly

```asm
0x180001350  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180001353  mov     r8d, ecx; int
0x180001356  lea     edx, [r9+66h]; unsigned int
0x18000135a  jmp     ?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
