# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::get_ErrorCode(winrt::hresult *)

- ea: `0x1800089b0`
- end: `0x1800089df`
- name: `?get_ErrorCode@?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@UEAAHPEAUhresult@3@@Z`
- size: `47`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009c20`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::get_ErrorCode(
        __int64 a1,
        _DWORD *a2)
{
  __int64 v3; // rax
  int v4; // ecx
  __int64 result; // rax
  int v6; // [rsp+30h] [rbp+8h] BYREF

  v3 = a1 - 24;
  if ( !a1 )
    v3 = 0;
  v4 = *winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::ErrorCode(
          v3,
          &v6);
  result = 0;
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x1800089b0  push    rbx
0x1800089b2  sub     rsp, 20h
0x1800089b6  mov     rbx, rdx
0x1800089b9  lea     rax, [rcx-18h]
0x1800089bd  xor     edx, edx
0x1800089bf  test    rcx, rcx
0x1800089c2  cmovz   rax, rdx
0x1800089c6  lea     rdx, [rsp+28h+arg_0]
0x1800089cb  mov     rcx, rax
0x1800089ce  call    ?ErrorCode@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAA?AUhresult@3@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::ErrorCode(void)
0x1800089d3  mov     ecx, [rax]
0x1800089d5  xor     eax, eax
0x1800089d7  mov     [rbx], ecx
0x1800089d9  add     rsp, 20h
0x1800089dd  pop     rbx
0x1800089de  retn
```
