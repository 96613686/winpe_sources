# winrt::Windows::System::Update::factory_implementation::SystemUpdateManagerT<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,winrt::Windows::System::Update::implementation::SystemUpdateManager,winrt::static_lifetime>::GetRuntimeClassName(void)

- ea: `0x180006d40`
- end: `0x180006d61`
- name: `?GetRuntimeClassName@?$SystemUpdateManagerT@USystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@U1implementation@3456@Ustatic_lifetime@6@@factory_implementation@Update@System@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005954`

## string_xrefs

- `0x180006d49`: `Windows.System.Update.SystemUpdateManager`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManagerT<winrt::Windows::System::Update::factory_implementation::SystemUpdateManager,winrt::Windows::System::Update::implementation::SystemUpdateManager,winrt::static_lifetime>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.System.Update.SystemUpdateManager");
  return a2;
}

```

## disassembly

```asm
0x180006d40  push    rbx
0x180006d42  sub     rsp, 30h
0x180006d46  mov     rbx, rdx
0x180006d49  lea     rdx, aWindowsSystemU_3; "Windows.System.Update.SystemUpdateManag"...
0x180006d50  mov     rcx, rbx; this
0x180006d53  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180006d58  mov     rax, rbx
0x180006d5b  add     rsp, 30h
0x180006d5f  pop     rbx
0x180006d60  retn
```
