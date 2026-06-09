# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x180006350`
- end: `0x180006366`
- name: `?QueryInterface@?$produce_base@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@X@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64, const void *, __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800068f0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::QueryInterface(
        __int64 a1,
        const void *a2,
        __int64 *a3)
{
  volatile signed __int64 *v3; // rax

  v3 = (volatile signed __int64 *)(a1 - 16);
  if ( !a1 )
    v3 = 0;
  return winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::QueryInterface(
           v3,
           a2,
           a3);
}

```

## disassembly

```asm
0x180006350  xor     r9d, r9d
0x180006353  lea     rax, [rcx-10h]
0x180006357  test    rcx, rcx
0x18000635a  cmovz   rax, r9
0x18000635e  mov     rcx, rax
0x180006361  jmp     ?QueryInterface@?$implements@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@UIImageBufferResourceFactory@3456@@winrt@@QEAAJAEBU_GUID@@PEAPEAX@Z; winrt::implements<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,winrt::Microsoft::Windows::PrivateCommon::IImageBufferResourceFactory>::QueryInterface(_GUID const &,void * *)
```
