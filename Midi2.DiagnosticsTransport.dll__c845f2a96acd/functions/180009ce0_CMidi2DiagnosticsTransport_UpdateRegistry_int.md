# CMidi2DiagnosticsTransport::UpdateRegistry(int)

- ea: `0x180009ce0`
- end: `0x180009ceb`
- name: `?UpdateRegistry@CMidi2DiagnosticsTransport@@SAJH@Z`
- size: `11`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180009cf4`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsTransport::UpdateRegistry(ATL::CAtlModule *a1, __int64 a2)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, a2, (int)a1, 0);
}

```

## disassembly

```asm
0x180009ce0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180009ce3  mov     r8d, ecx; int
0x180009ce6  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
