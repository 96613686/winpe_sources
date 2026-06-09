# winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData_base<winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData,>::GetRuntimeClassName(void)

- ea: `0x180014de0`
- end: `0x180014e08`
- name: `?GetRuntimeClassName@?$WindowsUpdateApprovalData_base@UWindowsUpdateApprovalData@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014df2`: `Windows.Management.Update.WindowsUpdateApprovalData`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData_base<winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsUpdateApprovalData", 0x33u);
  return a2;
}

```

## disassembly

```asm
0x180014de0  push    rbx
0x180014de2  sub     rsp, 30h
0x180014de6  mov     rbx, rdx
0x180014de9  mov     r8d, 33h ; '3'; unsigned int
0x180014def  mov     rcx, rbx; this
0x180014df2  lea     rdx, aWindowsManagem_1; "Windows.Management.Update.WindowsUpdate"...
0x180014df9  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014dfe  mov     rax, rbx
0x180014e01  add     rsp, 30h
0x180014e05  pop     rbx
0x180014e06  retn
```
