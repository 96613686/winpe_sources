# winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions_base<winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions,>::GetRuntimeClassName(void)

- ea: `0x180014e70`
- end: `0x180014e98`
- name: `?GetRuntimeClassName@?$WindowsUpdateRestartRequestOptions_base@UWindowsUpdateRestartRequestOptions@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014e82`: `Windows.Management.Update.WindowsUpdateRestartRequestOptions`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions_base<winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsUpdateRestartRequestOptions", 0x3Cu);
  return a2;
}

```

## disassembly

```asm
0x180014e70  push    rbx
0x180014e72  sub     rsp, 30h
0x180014e76  mov     rbx, rdx
0x180014e79  mov     r8d, 3Ch ; '<'; unsigned int
0x180014e7f  mov     rcx, rbx; this
0x180014e82  lea     rdx, aWindowsManagem_9; "Windows.Management.Update.WindowsUpdate"...
0x180014e89  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014e8e  mov     rax, rbx
0x180014e91  add     rsp, 30h
0x180014e95  pop     rbx
0x180014e96  retn
```
