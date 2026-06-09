# _OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated_::_1_::dtor$1

- ea: `0x14000edc4`
- end: `0x14000edd0`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 120);
}

```

## disassembly

```asm
0x14000edc4  lea     rcx, [rdx+78h]
0x14000edcb  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
