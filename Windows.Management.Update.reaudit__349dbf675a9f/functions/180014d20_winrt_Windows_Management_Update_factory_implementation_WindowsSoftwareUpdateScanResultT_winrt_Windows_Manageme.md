# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResultT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,>::GetRuntimeClassName(void)

- ea: `0x180014d20`
- end: `0x180014d48`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateScanResultT@UWindowsSoftwareUpdateScanResult@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014d32`: `Windows.Management.Update.WindowsSoftwareUpdateScanResult`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResultT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateScanResult", 0x39u);
  return a2;
}

```

## disassembly

```asm
0x180014d20  push    rbx
0x180014d22  sub     rsp, 30h
0x180014d26  mov     rbx, rdx
0x180014d29  mov     r8d, 39h ; '9'; unsigned int
0x180014d2f  mov     rcx, rbx; this
0x180014d32  lea     rdx, aWindowsManagem_11; "Windows.Management.Update.WindowsSoftwa"...
0x180014d39  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014d3e  mov     rax, rbx
0x180014d41  add     rsp, 30h
0x180014d45  pop     rbx
0x180014d46  retn
```
