# CAutoplayHandler::UpdateRegistry(int)

- ea: `0x180009160`
- end: `0x18000916d`
- name: `?UpdateRegistry@CAutoplayHandler@@SAJH@Z`
- size: `13`
- prototype: `__int64 __fastcall(ATL::CAtlModule *, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800091d4`

## pseudocode

```c
__int64 __fastcall CAutoplayHandler::UpdateRegistry(
        ATL::CAtlModule *a1,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x68u, (int)a1, a4);
}

```

## disassembly

```asm
0x180009160  mov     r8d, ecx; int
0x180009163  mov     edx, 68h ; 'h'; unsigned int
0x180009168  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
