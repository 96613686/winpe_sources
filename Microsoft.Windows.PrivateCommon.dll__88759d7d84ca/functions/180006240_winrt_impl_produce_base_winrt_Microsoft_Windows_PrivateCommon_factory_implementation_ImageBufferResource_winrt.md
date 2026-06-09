# winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::GetTrustLevel(winrt::Windows::Foundation::TrustLevel *)

- ea: `0x180006240`
- end: `0x180006256`
- name: `?GetTrustLevel@?$produce_base@UImageBufferResource@factory_implementation@PrivateCommon@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@X@impl@winrt@@UEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006ab0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::Microsoft::Windows::PrivateCommon::factory_implementation::ImageBufferResource,winrt::Windows::Foundation::IActivationFactory,void>::GetTrustLevel(
        __int64 a1)
{
  __int64 v1; // rax

  v1 = a1 - 16;
  if ( !a1 )
    v1 = 0;
  return winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetTrustLevel(v1);
}

```

## disassembly

```asm
0x180006240  xor     r8d, r8d
0x180006243  lea     rax, [rcx-10h]
0x180006247  test    rcx, rcx
0x18000624a  cmovz   rax, r8
0x18000624e  mov     rcx, rax
0x180006251  jmp     ?NonDelegatingGetTrustLevel@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z; winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetTrustLevel(winrt::Windows::Foundation::TrustLevel *)
```
