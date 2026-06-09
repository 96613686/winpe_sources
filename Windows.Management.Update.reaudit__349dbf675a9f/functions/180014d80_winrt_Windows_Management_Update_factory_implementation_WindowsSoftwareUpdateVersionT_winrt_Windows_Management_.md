# winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersionT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>::GetRuntimeClassName(void)

- ea: `0x180014d80`
- end: `0x180014da8`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateVersionT@UWindowsSoftwareUpdateVersion@factory_implementation@Update@Management@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014d92`: `Windows.Management.Update.WindowsSoftwareUpdateVersion`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersionT<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateVersion", 0x36u);
  return a2;
}

```

## disassembly

```asm
0x180014d80  push    rbx
0x180014d82  sub     rsp, 30h
0x180014d86  mov     rbx, rdx
0x180014d89  mov     r8d, 36h ; '6'; unsigned int
0x180014d8f  mov     rcx, rbx; this
0x180014d92  lea     rdx, aWindowsManagem_19; "Windows.Management.Update.WindowsSoftwa"...
0x180014d99  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014d9e  mov     rax, rbx
0x180014da1  add     rsp, 30h
0x180014da5  pop     rbx
0x180014da6  retn
```
