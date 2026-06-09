# CBrowserCap::UpdateRegistry(int)

- ea: `0x180006700`
- end: `0x180006716`
- name: `?UpdateRegistry@CBrowserCap@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000672c`

## pseudocode

```c
__int64 __fastcall CBrowserCap::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x65u, a1, 0);
}

```

## disassembly

```asm
0x180006700  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180006703  mov     r8d, ecx; int
0x180006706  lea     rcx, ?_Module@@3VCBrwCapModule@@A; this
0x18000670d  lea     edx, [r9+65h]; unsigned int
0x180006711  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
