# _OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$1

- ea: `0x14000ed10`
- end: `0x14000ed1c`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 184);
}

```

## disassembly

```asm
0x14000ed10  lea     rcx, [rdx+0B8h]
0x14000ed17  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
