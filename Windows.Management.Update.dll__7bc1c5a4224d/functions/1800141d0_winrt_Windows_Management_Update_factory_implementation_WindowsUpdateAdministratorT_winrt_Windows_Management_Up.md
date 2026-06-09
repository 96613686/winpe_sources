# winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministratorT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator,>::GetRuntimeClassName(void)

- ea: `0x1800141d0`
- end: `0x180014204`
- name: `?GetRuntimeClassName@?$WindowsUpdateAdministratorT@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x1800141e2`: `Windows.Management.Update.WindowsUpdateAdministrator`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministratorT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 52;
  v4[0] = L"Windows.Management.Update.WindowsUpdateAdministrator";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x1800141d0  push    rbx
0x1800141d2  sub     rsp, 40h
0x1800141d6  mov     rbx, rdx
0x1800141d9  mov     [rsp+48h+var_18], 34h ; '4'
0x1800141e2  lea     rax, aWindowsManagem_17; "Windows.Management.Update.WindowsUpdate"...
0x1800141e9  mov     rcx, rbx
0x1800141ec  lea     rdx, [rsp+48h+var_20]
0x1800141f1  mov     [rsp+48h+var_20], rax
0x1800141f6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800141fb  mov     rax, rbx
0x1800141fe  add     rsp, 40h
0x180014202  pop     rbx
0x180014203  retn
```
