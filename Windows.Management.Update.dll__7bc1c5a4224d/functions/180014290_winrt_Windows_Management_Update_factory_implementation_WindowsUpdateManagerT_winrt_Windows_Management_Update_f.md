# winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,winrt::Windows::Management::Update::implementation::WindowsUpdateManager,>::GetRuntimeClassName(void)

- ea: `0x180014290`
- end: `0x1800142c4`
- name: `?GetRuntimeClassName@?$WindowsUpdateManagerT@UWindowsUpdateManager@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x1800142a2`: `Windows.Management.Update.WindowsUpdateManager`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,winrt::Windows::Management::Update::implementation::WindowsUpdateManager,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 46;
  v4[0] = L"Windows.Management.Update.WindowsUpdateManager";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014290  push    rbx
0x180014292  sub     rsp, 40h
0x180014296  mov     rbx, rdx
0x180014299  mov     [rsp+48h+var_18], 2Eh ; '.'
0x1800142a2  lea     rax, aWindowsManagem_2; "Windows.Management.Update.WindowsUpdate"...
0x1800142a9  mov     rcx, rbx
0x1800142ac  lea     rdx, [rsp+48h+var_20]
0x1800142b1  mov     [rsp+48h+var_20], rax
0x1800142b6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800142bb  mov     rax, rbx
0x1800142be  add     rsp, 40h
0x1800142c2  pop     rbx
0x1800142c3  retn
```
