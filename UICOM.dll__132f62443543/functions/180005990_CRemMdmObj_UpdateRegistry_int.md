# CRemMdmObj::UpdateRegistry(int)

- ea: `0x180005990`
- end: `0x18000599f`
- name: `?UpdateRegistry@CRemMdmObj@@SAJH@Z`
- size: `15`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180004bac`

## pseudocode

```c
__int64 __fastcall CRemMdmObj::UpdateRegistry(ATL::CAtlModule *a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x67u, (int)a1, 0);
}

```

## disassembly

```asm
0x180005990  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180005993  mov     r8d, ecx; int
0x180005996  lea     edx, [r9+67h]; unsigned int
0x18000599a  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
