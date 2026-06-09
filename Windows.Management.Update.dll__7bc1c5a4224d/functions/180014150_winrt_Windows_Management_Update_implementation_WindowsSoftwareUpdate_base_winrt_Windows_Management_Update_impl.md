# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,>::GetRuntimeClassName(void)

- ea: `0x180014150`
- end: `0x180014184`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdate_base@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180014162`: `Windows.Management.Update.WindowsSoftwareUpdate`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 47;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdate";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014150  push    rbx
0x180014152  sub     rsp, 40h
0x180014156  mov     rbx, rdx
0x180014159  mov     [rsp+48h+var_18], 2Fh ; '/'
0x180014162  lea     rax, aWindowsManagem_15; "Windows.Management.Update.WindowsSoftwa"...
0x180014169  mov     rcx, rbx
0x18001416c  lea     rdx, [rsp+48h+var_20]
0x180014171  mov     [rsp+48h+var_20], rax
0x180014176  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001417b  mov     rax, rbx
0x18001417e  add     rsp, 40h
0x180014182  pop     rbx
0x180014183  retn
```
