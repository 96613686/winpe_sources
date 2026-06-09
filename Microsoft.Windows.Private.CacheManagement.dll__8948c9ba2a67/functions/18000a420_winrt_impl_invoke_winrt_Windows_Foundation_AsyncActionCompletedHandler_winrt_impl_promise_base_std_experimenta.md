# winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void> const &,winrt::Windows::Foundation::AsyncStatus const &)

- ea: `0x18000a420`
- end: `0x18000a461`
- name: `??$invoke@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z`
- size: `65`
- prototype: `char __fastcall(_QWORD *, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800085a0`
- `0x180008c70`

## callees

- `0x180003ee0`
- `0x18000a420`
- `0x18001cdf0`

## pseudocode

```c
char __fastcall winrt::impl::invoke<winrt::Windows::Foundation::AsyncActionCompletedHandler,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>,enum winrt::Windows::Foundation::AsyncStatus>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3)
{
  int v3; // eax
  winrt::impl *v5; // rcx
  __int64 *v6; // rdx
  __int64 v7; // [rsp+0h] [rbp-38h] BYREF
  char v8; // [rsp+20h] [rbp-18h]
  __int64 v9; // [rsp+28h] [rbp-10h]

  v9 = a2 + 16;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*a1 + 24LL))(*a1, a2 + 16, *a3);
  if ( v3 < 0 )
  {
    _mm_lfence();
    try
    {
      winrt::throw_hresult((unsigned int)v3);
    }
    catch ( ... )
    {
      v6 = &v7;
      *((_BYTE *)v6 + 32) = winrt::impl::report_failed_invoke(v5);
      return v8;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000a420  sub     rsp, 38h
0x18000a424  add     rdx, 10h
0x18000a428  mov     [rsp+38h+var_10], rdx
0x18000a42d  mov     rcx, [rcx]
0x18000a430  mov     rax, [rcx]
0x18000a433  mov     r8d, [r8]
0x18000a436  mov     rax, [rax+18h]
0x18000a43a  call    cs:__guard_dispatch_icall_fptr
0x18000a440  test    eax, eax
0x18000a442  js      short loc_18000A455
0x18000a444  mov     al, 1
0x18000a446  add     rsp, 38h
0x18000a44a  retn
0x18000a44b  movzx   eax, [rsp+38h+var_18]
0x18000a450  add     rsp, 38h
0x18000a454  retn
0x18000a455  lfence
0x18000a458  mov     ecx, eax
0x18000a45a  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
