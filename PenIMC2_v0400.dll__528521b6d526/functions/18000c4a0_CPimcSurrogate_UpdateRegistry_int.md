# CPimcSurrogate::UpdateRegistry(int)

- ea: `0x18000c4a0`
- end: `0x18000c4af`
- name: `?UpdateRegistry@CPimcSurrogate@@SAJH@Z`
- size: `15`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800057c0`

## pseudocode

```c
__int64 __fastcall CPimcSurrogate::UpdateRegistry(ATL::CAtlModule *a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResource(a1, 0x69u, (int)a1, 0);
}

```

## disassembly

```asm
0x18000c4a0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x18000c4a3  mov     r8d, ecx; int
0x18000c4a6  lea     edx, [r9+69h]; unsigned int
0x18000c4aa  jmp     ?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
