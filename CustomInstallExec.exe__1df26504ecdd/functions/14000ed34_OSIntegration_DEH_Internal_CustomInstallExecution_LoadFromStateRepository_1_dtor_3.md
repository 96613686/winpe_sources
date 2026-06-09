# _OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$3

- ea: `0x14000ed34`
- end: `0x14000ed40`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 160);
}

```

## disassembly

```asm
0x14000ed34  lea     rcx, [rdx+0A0h]
0x14000ed3b  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
