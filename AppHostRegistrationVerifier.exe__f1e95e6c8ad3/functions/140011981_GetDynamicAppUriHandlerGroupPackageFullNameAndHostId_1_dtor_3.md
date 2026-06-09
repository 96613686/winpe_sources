# _GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$3

- ea: `0x140011981`
- end: `0x14001198d`
- name: `_GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a4f0`

## pseudocode

```c
__int64 __fastcall GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(a2 + 88);
}

```

## disassembly

```asm
0x140011981  lea     rcx, [rdx+58h]
0x140011988  jmp     ??1vector_iterator@?$vector_range@U?$IVectorView@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)
```
