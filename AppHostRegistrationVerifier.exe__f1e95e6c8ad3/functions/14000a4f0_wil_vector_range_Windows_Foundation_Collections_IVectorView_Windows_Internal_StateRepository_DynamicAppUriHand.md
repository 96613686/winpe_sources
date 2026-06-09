# wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)

- ea: `0x14000a4f0`
- end: `0x14000a4f9`
- name: `??1vector_iterator@?$vector_range@U?$IVectorView@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400115e4`
- `0x1400115f6`
- `0x140011981`
- `0x140011993`

## callees

- `0x14000d49c`

## pseudocode

```c
__int64 __fastcall wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(a1 + 16);
}

```

## disassembly

```asm
0x14000a4f0  add     rcx, 10h
0x14000a4f4  jmp     ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
```
