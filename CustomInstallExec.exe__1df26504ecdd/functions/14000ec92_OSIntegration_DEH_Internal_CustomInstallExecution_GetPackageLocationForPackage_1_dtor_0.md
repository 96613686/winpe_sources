# _OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor$0

- ea: `0x14000ec92`
- end: `0x14000ec9e`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 40);
}

```

## disassembly

```asm
0x14000ec92  lea     rcx, [rdx+28h]
0x14000ec99  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
