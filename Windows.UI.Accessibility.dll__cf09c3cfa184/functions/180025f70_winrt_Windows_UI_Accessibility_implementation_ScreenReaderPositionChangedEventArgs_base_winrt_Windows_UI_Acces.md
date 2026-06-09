# winrt::Windows::UI::Accessibility::implementation::ScreenReaderPositionChangedEventArgs_base<winrt::Windows::UI::Accessibility::implementation::ScreenReaderPositionChangedEventArgs,>::GetRuntimeClassName(void)

- ea: `0x180025f70`
- end: `0x180025f91`
- name: `?GetRuntimeClassName@?$ScreenReaderPositionChangedEventArgs_base@UScreenReaderPositionChangedEventArgs@implementation@Accessibility@UI@Windows@winrt@@$$V@implementation@Accessibility@UI@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000def4`

## string_xrefs

- `0x180025f79`: `Windows.UI.Accessibility.ScreenReaderPositionChangedEventArgs`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::UI::Accessibility::implementation::ScreenReaderPositionChangedEventArgs_base<winrt::Windows::UI::Accessibility::implementation::ScreenReaderPositionChangedEventArgs,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.UI.Accessibility.ScreenReaderPositionChangedEventArgs");
  return a2;
}

```

## disassembly

```asm
0x180025f70  push    rbx
0x180025f72  sub     rsp, 30h
0x180025f76  mov     rbx, rdx
0x180025f79  lea     rdx, aWindowsUiAcces_1; "Windows.UI.Accessibility.ScreenReaderPo"...
0x180025f80  mov     rcx, rbx; this
0x180025f83  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180025f88  mov     rax, rbx
0x180025f8b  add     rsp, 30h
0x180025f8f  pop     rbx
0x180025f90  retn
```
