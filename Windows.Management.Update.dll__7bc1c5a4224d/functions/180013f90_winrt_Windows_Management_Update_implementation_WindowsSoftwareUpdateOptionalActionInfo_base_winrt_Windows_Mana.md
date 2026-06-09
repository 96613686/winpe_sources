# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo,>::GetRuntimeClassName(void)

- ea: `0x180013f90`
- end: `0x180013fc4`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateOptionalActionInfo_base@UWindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180013fa2`: `Windows.Management.Update.WindowsSoftwareUpdateOptionalActionInfo`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 65;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateOptionalActionInfo";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180013f90  push    rbx
0x180013f92  sub     rsp, 40h
0x180013f96  mov     rbx, rdx
0x180013f99  mov     [rsp+48h+var_18], 41h ; 'A'
0x180013fa2  lea     rax, aWindowsManagem_10; "Windows.Management.Update.WindowsSoftwa"...
0x180013fa9  mov     rcx, rbx
0x180013fac  lea     rdx, [rsp+48h+var_20]
0x180013fb1  mov     [rsp+48h+var_20], rax
0x180013fb6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013fbb  mov     rax, rbx
0x180013fbe  add     rsp, 40h
0x180013fc2  pop     rbx
0x180013fc3  retn
```
