# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,>::GetRuntimeClassName(void)

- ea: `0x180013fd0`
- end: `0x180014004`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateOptionalInfo_base@UWindowsSoftwareUpdateOptionalInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180013fe2`: `Windows.Management.Update.WindowsSoftwareUpdateOptionalInfo`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalInfo,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 59;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateOptionalInfo";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180013fd0  push    rbx
0x180013fd2  sub     rsp, 40h
0x180013fd6  mov     rbx, rdx
0x180013fd9  mov     [rsp+48h+var_18], 3Bh ; ';'
0x180013fe2  lea     rax, aWindowsManagem_8; "Windows.Management.Update.WindowsSoftwa"...
0x180013fe9  mov     rcx, rbx
0x180013fec  lea     rdx, [rsp+48h+var_20]
0x180013ff1  mov     [rsp+48h+var_20], rax
0x180013ff6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013ffb  mov     rax, rbx
0x180013ffe  add     rsp, 40h
0x180014002  pop     rbx
0x180014003  retn
```
