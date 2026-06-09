# _ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$0

- ea: `0x18000e874`
- end: `0x18000e880`
- name: `_ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000352c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)(a2 + 48));
}

```

## disassembly

```asm
0x18000e874  lea     rcx, [rdx+30h]; this
0x18000e87b  jmp     ??1CRegObject@ATL@@UEAA@XZ
```
