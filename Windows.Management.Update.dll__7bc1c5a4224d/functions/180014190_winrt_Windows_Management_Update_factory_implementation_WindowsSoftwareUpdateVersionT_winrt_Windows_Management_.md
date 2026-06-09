# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersionT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>::GetRuntimeClassName(void)

- ea: `0x180014190`
- end: `0x1800141c4`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateVersionT@UWindowsSoftwareUpdateVersion@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x1800141a2`: `Windows.Management.Update.WindowsSoftwareUpdateVersion`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersionT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 54;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateVersion";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014190  push    rbx
0x180014192  sub     rsp, 40h
0x180014196  mov     rbx, rdx
0x180014199  mov     [rsp+48h+var_18], 36h ; '6'
0x1800141a2  lea     rax, aWindowsManagem_19; "Windows.Management.Update.WindowsSoftwa"...
0x1800141a9  mov     rcx, rbx
0x1800141ac  lea     rdx, [rsp+48h+var_20]
0x1800141b1  mov     [rsp+48h+var_20], rax
0x1800141b6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800141bb  mov     rax, rbx
0x1800141be  add     rsp, 40h
0x1800141c2  pop     rbx
0x1800141c3  retn
```
