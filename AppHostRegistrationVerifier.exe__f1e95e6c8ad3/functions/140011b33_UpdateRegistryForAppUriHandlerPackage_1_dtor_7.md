# _UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$7

- ea: `0x140011b33`
- end: `0x140011b3f`
- name: `_UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a39c`

## pseudocode

```c
void __fastcall UpdateRegistryForAppUriHandlerPackage_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 112));
}

```

## disassembly

```asm
0x140011b33  lea     rcx, [rdx+70h]; this
0x140011b3a  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
