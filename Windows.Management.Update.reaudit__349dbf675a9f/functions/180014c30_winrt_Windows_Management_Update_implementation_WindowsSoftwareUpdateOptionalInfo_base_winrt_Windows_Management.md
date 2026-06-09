# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,>::GetRuntimeClassName(void)

- ea: `0x180014c30`
- end: `0x180014c58`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateOptionalInfo_base@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014c42`: `Windows.Management.Update.WindowsSoftwareUpdateOptionalInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateOptionalInfo", 0x3Bu);
  return a2;
}

```

## disassembly

```asm
0x180014c30  push    rbx
0x180014c32  sub     rsp, 30h
0x180014c36  mov     rbx, rdx
0x180014c39  mov     r8d, 3Bh ; ';'; unsigned int
0x180014c3f  mov     rcx, rbx; this
0x180014c42  lea     rdx, aWindowsManagem_8; "Windows.Management.Update.WindowsSoftwa"...
0x180014c49  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014c4e  mov     rax, rbx
0x180014c51  add     rsp, 30h
0x180014c55  pop     rbx
0x180014c56  retn
```
