# _OSIntegration::DEH::Internal::CustomInstallExecution::ClearPackageStatus_::_1_::dtor$2

- ea: `0x14000ec02`
- end: `0x14000ec0e`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::ClearPackageStatus_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000858c`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::ClearPackageStatus_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 40));
}

```

## disassembly

```asm
0x14000ec02  lea     rcx, [rdx+28h]; this
0x14000ec09  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
