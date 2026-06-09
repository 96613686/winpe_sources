# winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptionsT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions,>::GetRuntimeClassName(void)

- ea: `0x180014e10`
- end: `0x180014e38`
- name: `?GetRuntimeClassName@?$WindowsUpdateManagerScanOptionsT@UWindowsUpdateManagerScanOptions@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014e22`: `Windows.Management.Update.WindowsUpdateManagerScanOptions`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptionsT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,winrt::Windows::Management::Update::implementation::WindowsUpdateManagerScanOptions,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsUpdateManagerScanOptions", 0x39u);
  return a2;
}

```

## disassembly

```asm
0x180014e10  push    rbx
0x180014e12  sub     rsp, 30h
0x180014e16  mov     rbx, rdx
0x180014e19  mov     r8d, 39h ; '9'; unsigned int
0x180014e1f  mov     rcx, rbx; this
0x180014e22  lea     rdx, aWindowsManagem_14; "Windows.Management.Update.WindowsUpdate"...
0x180014e29  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014e2e  mov     rax, rbx
0x180014e31  add     rsp, 30h
0x180014e35  pop     rbx
0x180014e36  retn
```
