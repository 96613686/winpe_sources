# winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetTrustLevel(winrt::Windows::Foundation::TrustLevel *)

- ea: `0x18000ab10`
- end: `0x18000ab37`
- name: `?NonDelegatingGetTrustLevel@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@IEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008690`
- `0x180008a10`

## callees

- `0x18000ab10`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetTrustLevel(
        __int64 a1,
        _DWORD *a2)
{
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000ab10  push    rbx
0x18000ab12  sub     rsp, 20h
0x18000ab16  mov     rbx, rdx
0x18000ab19  mov     rax, [rcx]
0x18000ab1c  mov     rax, [rax+10h]
0x18000ab20  call    cs:__guard_dispatch_icall_fptr
0x18000ab26  mov     [rbx], eax
0x18000ab28  xor     eax, eax
0x18000ab2a  jmp     short loc_18000AB30
0x18000ab2c  mov     eax, [rsp+28h+arg_0]
0x18000ab30  add     rsp, 20h
0x18000ab34  pop     rbx
0x18000ab35  retn
```
