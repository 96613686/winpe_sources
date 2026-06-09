# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatusT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,>::GetRuntimeClassName(void)

- ea: `0x180014c90`
- end: `0x180014cb8`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateProviderStatusT@UWindowsSoftwareUpdateProviderStatus@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014ca2`: `Windows.Management.Update.WindowsSoftwareUpdateProviderStatus`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatusT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatus,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderStatus,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateProviderStatus", 0x3Du);
  return a2;
}

```

## disassembly

```asm
0x180014c90  push    rbx
0x180014c92  sub     rsp, 30h
0x180014c96  mov     rbx, rdx
0x180014c99  mov     r8d, 3Dh ; '='; unsigned int
0x180014c9f  mov     rcx, rbx; this
0x180014ca2  lea     rdx, aWindowsManagem_7; "Windows.Management.Update.WindowsSoftwa"...
0x180014ca9  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014cae  mov     rax, rbx
0x180014cb1  add     rsp, 30h
0x180014cb5  pop     rbx
0x180014cb6  retn
```
