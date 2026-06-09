# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::GetRuntimeClassName(void)

- ea: `0x1800091a0`
- end: `0x1800091d4`
- name: `?GetRuntimeClassName@?$ModelCacheManager_base@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@$$V@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@UEBA?AUhstring@7@XZ`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012f10`

## string_xrefs

- `0x1800091b2`: `Microsoft.Windows.Private.CacheManagement.ModelCacheManager`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager_base<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,>::GetRuntimeClassName(
        __int64 a1,
        __int64 a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 59;
  v4[0] = L"Microsoft.Windows.Private.CacheManagement.ModelCacheManager";
  winrt::hstring::hstring(a2, v4);
  return a2;
}

```

## disassembly

```asm
0x1800091a0  push    rbx
0x1800091a2  sub     rsp, 40h
0x1800091a6  mov     rbx, rdx
0x1800091a9  mov     [rsp+48h+var_18], 3Bh ; ';'
0x1800091b2  lea     rax, aMicrosoftWindo_0; "Microsoft.Windows.Private.CacheManageme"...
0x1800091b9  mov     rcx, rbx
0x1800091bc  lea     rdx, [rsp+48h+var_20]
0x1800091c1  mov     [rsp+48h+var_20], rax
0x1800091c6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x1800091cb  mov     rax, rbx
0x1800091ce  add     rsp, 40h
0x1800091d2  pop     rbx
0x1800091d3  retn
```
