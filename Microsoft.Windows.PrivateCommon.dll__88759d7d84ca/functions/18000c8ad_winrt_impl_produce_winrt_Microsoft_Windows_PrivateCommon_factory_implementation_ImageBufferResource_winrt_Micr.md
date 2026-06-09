# _winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::dtor$6

- ea: `0x18000c8ad`
- end: `0x18000c8b9`
- name: `_winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::dtor$6`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005d60`

## pseudocode

```c
__int64 winrt::impl::produce_winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource_winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory_::CreateInstance_::_1_::dtor_6()
{
  return winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>::~ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>();
}

```

## disassembly

```asm
0x18000c8ad  mov     rcx, [rdx+20h]
0x18000c8b4  jmp     ??1?$ImageBufferResource_base@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@$$V@implementation@PrivateCommon@Windows@Microsoft@winrt@@UEAA@XZ; winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>::~ImageBufferResource_base<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,>(void)
```
