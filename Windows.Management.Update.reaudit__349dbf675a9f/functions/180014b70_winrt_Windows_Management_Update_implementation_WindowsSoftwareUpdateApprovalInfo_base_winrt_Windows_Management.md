# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,>::GetRuntimeClassName(void)

- ea: `0x180014b70`
- end: `0x180014b98`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateApprovalInfo_base@UWindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014b82`: `Windows.Management.Update.WindowsSoftwareUpdateApprovalInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateApprovalInfo", 0x3Bu);
  return a2;
}

```

## disassembly

```asm
0x180014b70  push    rbx
0x180014b72  sub     rsp, 30h
0x180014b76  mov     rbx, rdx
0x180014b79  mov     r8d, 3Bh ; ';'; unsigned int
0x180014b7f  mov     rcx, rbx; this
0x180014b82  lea     rdx, aWindowsManagem_16; "Windows.Management.Update.WindowsSoftwa"...
0x180014b89  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014b8e  mov     rax, rbx
0x180014b91  add     rsp, 30h
0x180014b95  pop     rbx
0x180014b96  retn
```
