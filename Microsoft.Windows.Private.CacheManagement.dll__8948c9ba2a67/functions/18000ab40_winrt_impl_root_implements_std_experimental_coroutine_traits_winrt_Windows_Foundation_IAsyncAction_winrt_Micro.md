# winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x18000ab40`
- end: `0x18000ab6a`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `42`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800086b0`

## callees

- `0x180009a00`
- `0x18000ab40`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax
  _QWORD v4[3]; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncAction,void>::get(v4);
    *a2 = v4[0];
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(v4);
  }
  return result;
}

```

## disassembly

```asm
0x18000ab40  push    rbx
0x18000ab42  sub     rsp, 30h
0x18000ab46  mov     rbx, rdx
0x18000ab49  lea     rcx, [rsp+38h+var_18]
0x18000ab4e  call    ?get@?$runtime_class_name@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@SA?AUhstring@3@XZ; winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncAction,void>::get(void)
0x18000ab53  mov     rax, [rsp+38h+var_18]
0x18000ab58  mov     [rbx], rax
0x18000ab5b  xor     eax, eax
0x18000ab5d  jmp     short loc_18000AB63
0x18000ab5f  mov     eax, dword ptr [rsp+38h+var_18]
0x18000ab63  add     rsp, 30h
0x18000ab67  pop     rbx
0x18000ab68  retn
```
