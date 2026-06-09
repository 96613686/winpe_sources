# winrt::Microsoft::Windows::Workloads::Internal::factory_implementation::CacheManagerInternalT<winrt::Microsoft::Windows::Workloads::Internal::factory_implementation::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal,>::GetRuntimeClassName(void)

- ea: `0x18002c950`
- end: `0x18002c984`
- name: `?GetRuntimeClassName@?$CacheManagerInternalT@UCacheManagerInternal@factory_implementation@Internal@Workloads@Windows@Microsoft@winrt@@U1implementation@34567@$$V@factory_implementation@Internal@Workloads@Windows@Microsoft@winrt@@UEBA?AUhstring@7@XZ`
- size: `52`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(__int64, struct winrt::impl::shared_hstring_header **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800139b0`

## string_xrefs

- `0x18002c962`: `Microsoft.Windows.Workloads.Internal.CacheManagerInternal`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Microsoft::Windows::Workloads::Internal::factory_implementation::CacheManagerInternalT<winrt::Microsoft::Windows::Workloads::Internal::factory_implementation::CacheManagerInternal,winrt::Microsoft::Windows::Workloads::Internal::implementation::CacheManagerInternal,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 57;
  v4[0] = L"Microsoft.Windows.Workloads.Internal.CacheManagerInternal";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x18002c950  push    rbx
0x18002c952  sub     rsp, 40h
0x18002c956  mov     rbx, rdx
0x18002c959  mov     [rsp+48h+var_18], 39h ; '9'
0x18002c962  lea     rax, aMicrosoftWindo_1; "Microsoft.Windows.Workloads.Internal.Ca"...
0x18002c969  mov     rcx, rbx
0x18002c96c  lea     rdx, [rsp+48h+var_20]
0x18002c971  mov     [rsp+48h+var_20], rax
0x18002c976  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18002c97b  mov     rax, rbx
0x18002c97e  add     rsp, 40h
0x18002c982  pop     rbx
0x18002c983  retn
```
