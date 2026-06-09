# CPnpxPairingHandler::UpdateRegistry(int)

- ea: `0x1800088b0`
- end: `0x1800088c6`
- name: `?UpdateRegistry@CPnpxPairingHandler@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800088fc`

## pseudocode

```c
__int64 __fastcall CPnpxPairingHandler::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x66u, a1, 0);
}

```

## disassembly

```asm
0x1800088b0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800088b3  mov     r8d, ecx; int
0x1800088b6  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x1800088bd  lea     edx, [r9+66h]; unsigned int
0x1800088c1  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
