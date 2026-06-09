# CDfsShell::UpdateRegistry(int)

- ea: `0x180006310`
- end: `0x180006326`
- name: `?UpdateRegistry@CDfsShell@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000633c`

## pseudocode

```c
__int64 __fastcall CDfsShell::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x65u, a1, 0);
}

```

## disassembly

```asm
0x180006310  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180006313  mov     r8d, ecx; int
0x180006316  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000631d  lea     edx, [r9+65h]; unsigned int
0x180006321  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
