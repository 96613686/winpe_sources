# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,>::GetRuntimeClassName(void)

- ea: `0x180014c60`
- end: `0x180014c88`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateProviderActionResult_base@UWindowsSoftwareUpdateProviderActionResult@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014c72`: `Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProviderActionResult,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult", 0x43u);
  return a2;
}

```

## disassembly

```asm
0x180014c60  push    rbx
0x180014c62  sub     rsp, 30h
0x180014c66  mov     rbx, rdx
0x180014c69  mov     r8d, 43h ; 'C'; unsigned int
0x180014c6f  mov     rcx, rbx; this
0x180014c72  lea     rdx, aWindowsManagem_6; "Windows.Management.Update.WindowsSoftwa"...
0x180014c79  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014c7e  mov     rax, rbx
0x180014c81  add     rsp, 30h
0x180014c85  pop     rbx
0x180014c86  retn
```
