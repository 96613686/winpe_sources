# _OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$4

- ea: `0x14000ed46`
- end: `0x14000ed52`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 168);
}

```

## disassembly

```asm
0x14000ed46  lea     rcx, [rdx+0A8h]
0x14000ed4d  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
