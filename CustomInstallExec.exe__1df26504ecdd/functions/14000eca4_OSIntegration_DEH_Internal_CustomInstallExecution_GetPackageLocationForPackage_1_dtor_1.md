# _OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor$1

- ea: `0x14000eca4`
- end: `0x14000ecb0`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000858c`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 56));
}

```

## disassembly

```asm
0x14000eca4  lea     rcx, [rdx+38h]; this
0x14000ecab  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
