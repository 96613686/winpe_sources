# _OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated_::_1_::dtor$0

- ea: `0x14000ecfe`
- end: `0x14000ed0a`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 48);
}

```

## disassembly

```asm
0x14000ecfe  lea     rcx, [rdx+30h]
0x14000ed05  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
