# CServiceProvider::UpdateRegistry(int)

- ea: `0x1800088d0`
- end: `0x1800088e6`
- name: `?UpdateRegistry@CServiceProvider@@SAJH@Z`
- size: `22`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800088fc`

## pseudocode

```c
__int64 __fastcall CServiceProvider::UpdateRegistry(int a1)
{
  return ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x65u, a1, 0);
}

```

## disassembly

```asm
0x1800088d0  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x1800088d3  mov     r8d, ecx; int
0x1800088d6  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x1800088dd  lea     edx, [r9+65h]; unsigned int
0x1800088e1  jmp     ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
```
