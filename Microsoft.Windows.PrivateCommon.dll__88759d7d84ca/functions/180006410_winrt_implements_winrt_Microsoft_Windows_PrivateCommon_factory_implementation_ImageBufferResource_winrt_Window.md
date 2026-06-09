# winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::get_local_iids(void)

- ea: `0x180006410`
- end: `0x180006425`
- name: `?get_local_iids@?$implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@winrt@@UEBA?AU?$pair@IPEBUguid@winrt@@@std@@XZ`
- size: `21`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::get_local_iids(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)a2 = 2;
  *(_QWORD *)(a2 + 8) = winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>>::value;
  return a2;
}

```

## disassembly

```asm
0x180006410  lea     rax, ?value@?$uncloaked_iids@U?$interface_list@UIActivationFactory@Foundation@Windows@winrt@@UIImageBufferResourceFactory@PrivateCommon@3Microsoft@4@@impl@winrt@@@impl@winrt@@2V?$array@Uguid@winrt@@$01@std@@B; std::array<winrt::guid,2> const winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>>::value
0x180006417  mov     dword ptr [rdx], 2
0x18000641d  mov     [rdx+8], rax
0x180006421  mov     rax, rdx
0x180006424  retn
```
