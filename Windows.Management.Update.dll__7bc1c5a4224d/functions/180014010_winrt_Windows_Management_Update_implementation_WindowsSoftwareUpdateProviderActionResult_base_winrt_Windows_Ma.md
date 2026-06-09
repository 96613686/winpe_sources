# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,>::GetRuntimeClassName(void)

- ea: `0x180014010`
- end: `0x180014044`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateProviderActionResult_base@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180014022`: `Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 67;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014010  push    rbx
0x180014012  sub     rsp, 40h
0x180014016  mov     rbx, rdx
0x180014019  mov     [rsp+48h+var_18], 43h ; 'C'
0x180014022  lea     rax, aWindowsManagem_6; "Windows.Management.Update.WindowsSoftwa"...
0x180014029  mov     rcx, rbx
0x18001402c  lea     rdx, [rsp+48h+var_20]
0x180014031  mov     [rsp+48h+var_20], rax
0x180014036  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001403b  mov     rax, rbx
0x18001403e  add     rsp, 40h
0x180014042  pop     rbx
0x180014043  retn
```
