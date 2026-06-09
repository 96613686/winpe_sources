# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatusT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,>::GetRuntimeClassName(void)

- ea: `0x180014050`
- end: `0x180014084`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateProviderStatusT@UWindowsSoftwareUpdateProviderStatus@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180014062`: `Windows.Management.Update.WindowsSoftwareUpdateProviderStatus`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatusT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 61;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateProviderStatus";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014050  push    rbx
0x180014052  sub     rsp, 40h
0x180014056  mov     rbx, rdx
0x180014059  mov     [rsp+48h+var_18], 3Dh ; '='
0x180014062  lea     rax, aWindowsManagem_7; "Windows.Management.Update.WindowsSoftwa"...
0x180014069  mov     rcx, rbx
0x18001406c  lea     rdx, [rsp+48h+var_20]
0x180014071  mov     [rsp+48h+var_20], rax
0x180014076  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001407b  mov     rax, rbx
0x18001407e  add     rsp, 40h
0x180014082  pop     rbx
0x180014083  retn
```
