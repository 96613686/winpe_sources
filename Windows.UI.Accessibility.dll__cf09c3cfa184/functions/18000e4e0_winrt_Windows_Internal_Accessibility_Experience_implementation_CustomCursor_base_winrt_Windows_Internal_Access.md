# winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor_base<winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor,>::GetRuntimeClassName(void)

- ea: `0x18000e4e0`
- end: `0x18000e501`
- name: `?GetRuntimeClassName@?$CustomCursor_base@UCustomCursor@implementation@Experience@Accessibility@Internal@Windows@winrt@@$$V@implementation@Experience@Accessibility@Internal@Windows@winrt@@UEBA?AUhstring@7@XZ`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000def4`

## string_xrefs

- `0x18000e4e9`: `Windows.Internal.Accessibility.Experience.CustomCursor`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor_base<winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursor,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Internal.Accessibility.Experience.CustomCursor");
  return a2;
}

```

## disassembly

```asm
0x18000e4e0  push    rbx
0x18000e4e2  sub     rsp, 30h
0x18000e4e6  mov     rbx, rdx
0x18000e4e9  lea     rdx, aWindowsInterna_0; "Windows.Internal.Accessibility.Experien"...
0x18000e4f0  mov     rcx, rbx; this
0x18000e4f3  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18000e4f8  mov     rax, rbx
0x18000e4fb  add     rsp, 30h
0x18000e4ff  pop     rbx
0x18000e500  retn
```
