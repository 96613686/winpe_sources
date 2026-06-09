# wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)

- ea: `0x140008600`
- end: `0x140008609`
- name: `??1vector_iterator@?$vector_range@U?$IVectorView@PEAVCustomInstallWork@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ed58`
- `0x14000ed6a`

## callees

- `0x1400098dc`

## pseudocode

```c
__int64 __fastcall wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(a1 + 16);
}

```

## disassembly

```asm
0x140008600  add     rcx, 10h
0x140008604  jmp     ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
```
