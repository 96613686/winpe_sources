# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,>::GetRuntimeClassName(void)

- ea: `0x180013e50`
- end: `0x180013e84`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateActionInfoT@UWindowsSoftwareUpdateActionInfo@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180013e62`: `Windows.Management.Update.WindowsSoftwareUpdateActionInfo`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 57;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateActionInfo";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180013e50  push    rbx
0x180013e52  sub     rsp, 40h
0x180013e56  mov     rbx, rdx
0x180013e59  mov     [rsp+48h+var_18], 39h ; '9'
0x180013e62  lea     rax, aWindowsManagem_12; "Windows.Management.Update.WindowsSoftwa"...
0x180013e69  mov     rcx, rbx
0x180013e6c  lea     rdx, [rsp+48h+var_20]
0x180013e71  mov     [rsp+48h+var_20], rax
0x180013e76  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013e7b  mov     rax, rbx
0x180013e7e  add     rsp, 40h
0x180013e82  pop     rbx
0x180013e83  retn
```
