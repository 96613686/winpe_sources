# winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData_base<winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData,>::GetRuntimeClassName(void)

- ea: `0x180014210`
- end: `0x180014244`
- name: `?GetRuntimeClassName@?$WindowsUpdateApprovalData_base@UWindowsUpdateApprovalData@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180014222`: `Windows.Management.Update.WindowsUpdateApprovalData`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData_base<winrt::Windows::Management::Update::implementation::WindowsUpdateApprovalData,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 51;
  v4[0] = L"Windows.Management.Update.WindowsUpdateApprovalData";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014210  push    rbx
0x180014212  sub     rsp, 40h
0x180014216  mov     rbx, rdx
0x180014219  mov     [rsp+48h+var_18], 33h ; '3'
0x180014222  lea     rax, aWindowsManagem_1; "Windows.Management.Update.WindowsUpdate"...
0x180014229  mov     rcx, rbx
0x18001422c  lea     rdx, [rsp+48h+var_20]
0x180014231  mov     [rsp+48h+var_20], rax
0x180014236  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001423b  mov     rax, rbx
0x18001423e  add     rsp, 40h
0x180014242  pop     rbx
0x180014243  retn
```
