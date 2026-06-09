# CVsShellExtHandler::UpdateRegistry(int)

- ea: `0x180002450`
- end: `0x180002458`
- name: `?UpdateRegistry@CVsShellExtHandler@@SAJH@Z`
- size: `8`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000572c`

## pseudocode

```c
__int64 __fastcall CVsShellExtHandler::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResource(a1, a2, (unsigned int)a1, a4);
}

```

## disassembly

```asm
0x180002450  mov     r8d, ecx; int
0x180002453  jmp     ?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
