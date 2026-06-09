# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,>::GetRuntimeClassName(void)

- ea: `0x180014b10`
- end: `0x180014b38`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateActionInfoT@UWindowsSoftwareUpdateActionInfo@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014b22`: `Windows.Management.Update.WindowsSoftwareUpdateActionInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfoT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateActionInfo", 0x39u);
  return a2;
}

```

## disassembly

```asm
0x180014b10  push    rbx
0x180014b12  sub     rsp, 30h
0x180014b16  mov     rbx, rdx
0x180014b19  mov     r8d, 39h ; '9'; unsigned int
0x180014b1f  mov     rcx, rbx; this
0x180014b22  lea     rdx, aWindowsManagem_12; "Windows.Management.Update.WindowsSoftwa"...
0x180014b29  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014b2e  mov     rax, rbx
0x180014b31  add     rsp, 30h
0x180014b35  pop     rbx
0x180014b36  retn
```
