# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResultT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,>::GetRuntimeClassName(void)

- ea: `0x180014110`
- end: `0x180014144`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateScanResultT@UWindowsSoftwareUpdateScanResult@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180014122`: `Windows.Management.Update.WindowsSoftwareUpdateScanResult`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResultT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 57;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateScanResult";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014110  push    rbx
0x180014112  sub     rsp, 40h
0x180014116  mov     rbx, rdx
0x180014119  mov     [rsp+48h+var_18], 39h ; '9'
0x180014122  lea     rax, aWindowsManagem_11; "Windows.Management.Update.WindowsSoftwa"...
0x180014129  mov     rcx, rbx
0x18001412c  lea     rdx, [rsp+48h+var_20]
0x180014131  mov     [rsp+48h+var_20], rax
0x180014136  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001413b  mov     rax, rbx
0x18001413e  add     rsp, 40h
0x180014142  pop     rbx
0x180014143  retn
```
