# CAddMdmObj::UpdateRegistry(int)

- ea: `0x180005da0`
- end: `0x180005daf`
- name: `?UpdateRegistry@CAddMdmObj@@SAJH@Z`
- size: `15`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180004bac`

## pseudocode

```c
__int64 __fastcall CAddMdmObj::UpdateRegistry(ATL::CAtlModule *a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x66u, (int)a1, 0);
}

```

## disassembly

```asm
0x180005da0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180005da3  mov     r8d, ecx; int
0x180005da6  lea     edx, [r9+66h]; unsigned int
0x180005daa  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
