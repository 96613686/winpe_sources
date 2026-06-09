# winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,winrt::Windows::Management::Update::implementation::WindowsUpdateManager,>::GetRuntimeClassName(void)

- ea: `0x180014e40`
- end: `0x180014e68`
- name: `?GetRuntimeClassName@?$WindowsUpdateManagerT@UWindowsUpdateManager@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014e52`: `Windows.Management.Update.WindowsUpdateManager`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerT<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,winrt::Windows::Management::Update::implementation::WindowsUpdateManager,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsUpdateManager", 0x2Eu);
  return a2;
}

```

## disassembly

```asm
0x180014e40  push    rbx
0x180014e42  sub     rsp, 30h
0x180014e46  mov     rbx, rdx
0x180014e49  mov     r8d, 2Eh ; '.'; unsigned int
0x180014e4f  mov     rcx, rbx; this
0x180014e52  lea     rdx, aWindowsManagem_2; "Windows.Management.Update.WindowsUpdate"...
0x180014e59  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014e5e  mov     rax, rbx
0x180014e61  add     rsp, 30h
0x180014e65  pop     rbx
0x180014e66  retn
```
