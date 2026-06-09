# wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(void)

- ea: `0x18000e1ac`
- end: `0x18000e1b5`
- name: `??1vector_iterator@?$vector_range@U?$IVector@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020c9e`
- `0x180020cb0`
- `0x180020cd4`
- `0x180020ce6`
- `0x180020e3e`
- `0x180020e50`
- `0x180020e86`
- `0x180020e98`

## callees

- `0x180007630`

## pseudocode

```c
__int64 __fastcall wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::~vector_iterator(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 16);
}

```

## disassembly

```asm
0x18000e1ac  add     rcx, 10h
0x18000e1b0  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
