# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$21

- ea: `0x1400115e4`
- end: `0x1400115f0`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$21`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a4f0`

## pseudocode

```c
__int64 __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor_21(
        __int64 a1,
        __int64 a2)
{
  return wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(a2 + 96);
}

```

## disassembly

```asm
0x1400115e4  lea     rcx, [rdx+60h]
0x1400115eb  jmp     ??1vector_iterator@?$vector_range@U?$IVectorView@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)
```
