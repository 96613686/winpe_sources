# winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(void)

- ea: `0x180008d80`
- end: `0x180008d9a`
- name: `?GetRuntimeClassName@?$implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@EEBA?AUhstring@2@XZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009a00`

## pseudocode

```c
__int64 __fastcall winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncAction,void>::get(a2);
  return a2;
}

```

## disassembly

```asm
0x180008d80  push    rbx
0x180008d82  sub     rsp, 30h
0x180008d86  mov     rcx, rdx
0x180008d89  mov     rbx, rdx
0x180008d8c  call    ?get@?$runtime_class_name@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@SA?AUhstring@3@XZ; winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncAction,void>::get(void)
0x180008d91  mov     rax, rbx
0x180008d94  add     rsp, 30h
0x180008d98  pop     rbx
0x180008d99  retn
```
