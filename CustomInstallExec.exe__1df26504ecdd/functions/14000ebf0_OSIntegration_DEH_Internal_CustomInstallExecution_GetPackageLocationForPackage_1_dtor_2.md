# _OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor$2

- ea: `0x14000ebf0`
- end: `0x14000ebfc`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 32);
}

```

## disassembly

```asm
0x14000ebf0  lea     rcx, [rdx+20h]
0x14000ebf7  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
