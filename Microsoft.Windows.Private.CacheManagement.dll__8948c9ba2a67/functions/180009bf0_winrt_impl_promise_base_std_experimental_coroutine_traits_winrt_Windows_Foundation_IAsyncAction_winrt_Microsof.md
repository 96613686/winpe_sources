# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::rethrow_if_failed(winrt::Windows::Foundation::AsyncStatus)

- ea: `0x180009bf0`
- end: `0x180009c18`
- name: `?rethrow_if_failed@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@IEBAXW4AsyncStatus@Foundation@Windows@3@@Z`
- size: `40`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008b70`

## callees

- `0x180009bf0`
- `0x180012ae0`
- `0x180012b00`

## pseudocode

```c
__int64 __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::rethrow_if_failed(
        __int64 a1,
        int a2)
{
  __int64 result; // rax
  __int64 v3; // rax
  _BYTE v4[24]; // [rsp+20h] [rbp-18h] BYREF

  result = (unsigned int)(a2 - 2);
  if ( (unsigned int)result <= 1 )
  {
    v3 = std::exception_ptr::exception_ptr((std::exception_ptr *)v4, (const struct std::exception_ptr *)(a1 + 56));
    std::rethrow_exception(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180009bf0  sub     rsp, 38h
0x180009bf4  lea     eax, [rdx-2]
0x180009bf7  cmp     eax, 1
0x180009bfa  jbe     short loc_180009C01
0x180009bfc  add     rsp, 38h
0x180009c00  retn
0x180009c01  lea     rdx, [rcx+38h]; struct std::exception_ptr *
0x180009c05  lea     rcx, [rsp+38h+var_18]; this
0x180009c0a  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180009c0f  mov     rcx, rax
0x180009c12  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
```
