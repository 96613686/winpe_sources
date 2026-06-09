# _GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$4

- ea: `0x140011993`
- end: `0x14001199f`
- name: `_GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a4f0`

## pseudocode

```c
__int64 __fastcall GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(a2 + 120);
}

```

## disassembly

```asm
0x140011993  lea     rcx, [rdx+78h]
0x14001199a  jmp     ??1vector_iterator@?$vector_range@U?$IVectorView@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)
```
