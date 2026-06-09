# CMidi2UMP2BSTransform::UpdateRegistry(int)

- ea: `0x1800084c0`
- end: `0x1800084cb`
- name: `?UpdateRegistry@CMidi2UMP2BSTransform@@SAJH@Z`
- size: `11`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800084d4`

## pseudocode

```c
__int64 __fastcall CMidi2UMP2BSTransform::UpdateRegistry(ATL::CAtlModule *a1, __int64 a2)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, a2, (int)a1, 0);
}

```

## disassembly

```asm
0x1800084c0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800084c3  mov     r8d, ecx; int
0x1800084c6  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
