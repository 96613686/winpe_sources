# _UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$0

- ea: `0x14001162c`
- end: `0x140011638`
- name: `_UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall UpdateRegistryForAppUriHandlerPackage_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 64);
}

```

## disassembly

```asm
0x14001162c  lea     rcx, [rdx+40h]
0x140011633  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
