# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,>::GetRuntimeClassName(void)

- ea: `0x180013f50`
- end: `0x180013f84`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateLocalizationInfo_base@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180013f62`: `Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 63;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180013f50  push    rbx
0x180013f52  sub     rsp, 40h
0x180013f56  mov     rbx, rdx
0x180013f59  mov     [rsp+48h+var_18], 3Fh ; '?'
0x180013f62  lea     rax, aWindowsManagem_5; "Windows.Management.Update.WindowsSoftwa"...
0x180013f69  mov     rcx, rbx
0x180013f6c  lea     rdx, [rsp+48h+var_20]
0x180013f71  mov     [rsp+48h+var_20], rax
0x180013f76  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013f7b  mov     rax, rbx
0x180013f7e  add     rsp, 40h
0x180013f82  pop     rbx
0x180013f83  retn
```
