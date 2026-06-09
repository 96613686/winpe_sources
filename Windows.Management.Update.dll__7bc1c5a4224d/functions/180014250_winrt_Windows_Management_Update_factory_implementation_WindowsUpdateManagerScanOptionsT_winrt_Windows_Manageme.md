# winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptionsT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions,>::GetRuntimeClassName(void)

- ea: `0x180014250`
- end: `0x180014284`
- name: `?GetRuntimeClassName@?$WindowsUpdateManagerScanOptionsT@UWindowsUpdateManagerScanOptions@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180014262`: `Windows.Management.Update.WindowsUpdateManagerScanOptions`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptionsT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 57;
  v4[0] = L"Windows.Management.Update.WindowsUpdateManagerScanOptions";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014250  push    rbx
0x180014252  sub     rsp, 40h
0x180014256  mov     rbx, rdx
0x180014259  mov     [rsp+48h+var_18], 39h ; '9'
0x180014262  lea     rax, aWindowsManagem_14; "Windows.Management.Update.WindowsUpdate"...
0x180014269  mov     rcx, rbx
0x18001426c  lea     rdx, [rsp+48h+var_20]
0x180014271  mov     [rsp+48h+var_20], rax
0x180014276  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001427b  mov     rax, rbx
0x18001427e  add     rsp, 40h
0x180014282  pop     rbx
0x180014283  retn
```
