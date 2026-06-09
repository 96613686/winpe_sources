# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,>::GetRuntimeClassName(void)

- ea: `0x180013e90`
- end: `0x180013ec4`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateAppPackageInfoT@UWindowsSoftwareUpdateAppPackageInfo@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180013ea2`: `Windows.Management.Update.WindowsSoftwareUpdateAppPackageInfo`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 61;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateAppPackageInfo";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180013e90  push    rbx
0x180013e92  sub     rsp, 40h
0x180013e96  mov     rbx, rdx
0x180013e99  mov     [rsp+48h+var_18], 3Dh ; '='
0x180013ea2  lea     rax, aWindowsManagem_3; "Windows.Management.Update.WindowsSoftwa"...
0x180013ea9  mov     rcx, rbx
0x180013eac  lea     rdx, [rsp+48h+var_20]
0x180013eb1  mov     [rsp+48h+var_20], rax
0x180013eb6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013ebb  mov     rax, rbx
0x180013ebe  add     rsp, 40h
0x180013ec2  pop     rbx
0x180013ec3  retn
```
