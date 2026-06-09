# winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministratorT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator,>::GetRuntimeClassName(void)

- ea: `0x180014db0`
- end: `0x180014dd8`
- name: `?GetRuntimeClassName@?$WindowsUpdateAdministratorT@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014dc2`: `Windows.Management.Update.WindowsUpdateAdministrator`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministratorT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,winrt::Windows::Management::Update::implementation::WindowsUpdateAdministrator,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsUpdateAdministrator", 0x34u);
  return a2;
}

```

## disassembly

```asm
0x180014db0  push    rbx
0x180014db2  sub     rsp, 30h
0x180014db6  mov     rbx, rdx
0x180014db9  mov     r8d, 34h ; '4'; unsigned int
0x180014dbf  mov     rcx, rbx; this
0x180014dc2  lea     rdx, aWindowsManagem_17; "Windows.Management.Update.WindowsUpdate"...
0x180014dc9  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014dce  mov     rax, rbx
0x180014dd1  add     rsp, 30h
0x180014dd5  pop     rbx
0x180014dd6  retn
```
