# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$22

- ea: `0x1400115f6`
- end: `0x140011602`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$22`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a4f0`

## pseudocode

```c
__int64 __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor_22(
        __int64 a1,
        __int64 a2)
{
  return wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(a2 + 200);
}

```

## disassembly

```asm
0x1400115f6  lea     rcx, [rdx+0C8h]
0x1400115fd  jmp     ??1vector_iterator@?$vector_range@U?$IVectorView@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)
```
