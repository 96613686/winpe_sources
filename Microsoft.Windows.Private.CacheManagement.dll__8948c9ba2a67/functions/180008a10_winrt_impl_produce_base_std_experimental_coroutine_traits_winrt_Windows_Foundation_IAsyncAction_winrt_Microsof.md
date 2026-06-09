# winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::GetTrustLevel(winrt::Windows::Foundation::TrustLevel *)

- ea: `0x180008a10`
- end: `0x180008a26`
- name: `?GetTrustLevel@?$produce_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@UEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z`
- size: `22`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ab10`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::GetTrustLevel(
        __int64 a1)
{
  __int64 v1; // rax

  v1 = a1 - 16;
  if ( !a1 )
    v1 = 0;
  return winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetTrustLevel(v1);
}

```

## disassembly

```asm
0x180008a10  xor     r8d, r8d
0x180008a13  lea     rax, [rcx-10h]
0x180008a17  test    rcx, rcx
0x180008a1a  cmovz   rax, r8
0x180008a1e  mov     rcx, rax
0x180008a21  jmp     ?NonDelegatingGetTrustLevel@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetTrustLevel(winrt::Windows::Foundation::TrustLevel *)
```
