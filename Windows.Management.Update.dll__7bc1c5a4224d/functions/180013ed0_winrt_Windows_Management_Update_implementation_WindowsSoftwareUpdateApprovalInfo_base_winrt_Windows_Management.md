# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,>::GetRuntimeClassName(void)

- ea: `0x180013ed0`
- end: `0x180013f04`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateApprovalInfo_base@UWindowsSoftwareUpdateApprovalInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180013ee2`: `Windows.Management.Update.WindowsSoftwareUpdateApprovalInfo`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateApprovalInfo,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 59;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateApprovalInfo";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180013ed0  push    rbx
0x180013ed2  sub     rsp, 40h
0x180013ed6  mov     rbx, rdx
0x180013ed9  mov     [rsp+48h+var_18], 3Bh ; ';'
0x180013ee2  lea     rax, aWindowsManagem_16; "Windows.Management.Update.WindowsSoftwa"...
0x180013ee9  mov     rcx, rbx
0x180013eec  lea     rdx, [rsp+48h+var_20]
0x180013ef1  mov     [rsp+48h+var_20], rax
0x180013ef6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013efb  mov     rax, rbx
0x180013efe  add     rsp, 40h
0x180013f02  pop     rbx
0x180013f03  retn
```
