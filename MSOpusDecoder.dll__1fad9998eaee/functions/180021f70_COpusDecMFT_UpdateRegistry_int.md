# COpusDecMFT::UpdateRegistry(int)

- ea: `0x180021f70`
- end: `0x180021f86`
- name: `?UpdateRegistry@COpusDecMFT@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180021f9c`

## pseudocode

```c
__int64 __fastcall COpusDecMFT::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(ATL::_pAtlModule, 0x69u, a1, 0);
}

```

## disassembly

```asm
0x180021f70  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180021f73  mov     r8d, ecx; int
0x180021f76  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; this
0x180021f7d  lea     edx, [r9+69h]; unsigned int
0x180021f81  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
