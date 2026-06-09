# _OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$6

- ea: `0x14000ed6a`
- end: `0x14000ed76`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x140008600`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository_::_1_::dtor_6(
        __int64 a1,
        __int64 a2)
{
  return wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(a2 + 80);
}

```

## disassembly

```asm
0x14000ed6a  lea     rcx, [rdx+50h]
0x14000ed71  jmp     ??1vector_iterator@?$vector_range@U?$IVectorView@PEAVCustomInstallWork@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)
```
