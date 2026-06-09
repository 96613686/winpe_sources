# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,>::GetRuntimeClassName(void)

- ea: `0x180014b40`
- end: `0x180014b68`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateAppPackageInfoT@UWindowsSoftwareUpdateAppPackageInfo@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014b52`: `Windows.Management.Update.WindowsSoftwareUpdateAppPackageInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateAppPackageInfo", 0x3Du);
  return a2;
}

```

## disassembly

```asm
0x180014b40  push    rbx
0x180014b42  sub     rsp, 30h
0x180014b46  mov     rbx, rdx
0x180014b49  mov     r8d, 3Dh ; '='; unsigned int
0x180014b4f  mov     rcx, rbx; this
0x180014b52  lea     rdx, aWindowsManagem_3; "Windows.Management.Update.WindowsSoftwa"...
0x180014b59  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014b5e  mov     rax, rbx
0x180014b61  add     rsp, 30h
0x180014b65  pop     rbx
0x180014b66  retn
```
