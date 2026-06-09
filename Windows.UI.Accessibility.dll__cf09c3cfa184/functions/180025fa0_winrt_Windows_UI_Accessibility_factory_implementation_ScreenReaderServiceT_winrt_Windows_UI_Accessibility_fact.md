# winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderServiceT<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,>::GetRuntimeClassName(void)

- ea: `0x180025fa0`
- end: `0x180025fc1`
- name: `?GetRuntimeClassName@?$ScreenReaderServiceT@UScreenReaderService@factory_implementation@Accessibility@UI@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Accessibility@UI@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000def4`

## string_xrefs

- `0x180025fa9`: `Windows.UI.Accessibility.ScreenReaderService`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderServiceT<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.UI.Accessibility.ScreenReaderService");
  return a2;
}

```

## disassembly

```asm
0x180025fa0  push    rbx
0x180025fa2  sub     rsp, 30h
0x180025fa6  mov     rbx, rdx
0x180025fa9  lea     rdx, aWindowsUiAcces_0; "Windows.UI.Accessibility.ScreenReaderSe"...
0x180025fb0  mov     rcx, rbx; this
0x180025fb3  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180025fb8  mov     rax, rbx
0x180025fbb  add     rsp, 30h
0x180025fbf  pop     rbx
0x180025fc0  retn
```
