# _UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$3

- ea: `0x140011794`
- end: `0x1400117a0`
- name: `_UpdateRegistryForAppUriHandlerPackage_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall UpdateRegistryForAppUriHandlerPackage_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 56);
}

```

## disassembly

```asm
0x140011794  lea     rcx, [rdx+38h]
0x14001179b  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
