# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,>::GetRuntimeClassName(void)

- ea: `0x1800140d0`
- end: `0x180014104`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateResult_base@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x1800140e2`: `Windows.Management.Update.WindowsSoftwareUpdateResult`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 53;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateResult";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x1800140d0  push    rbx
0x1800140d2  sub     rsp, 40h
0x1800140d6  mov     rbx, rdx
0x1800140d9  mov     [rsp+48h+var_18], 35h ; '5'
0x1800140e2  lea     rax, aWindowsManagem_18; "Windows.Management.Update.WindowsSoftwa"...
0x1800140e9  mov     rcx, rbx
0x1800140ec  lea     rdx, [rsp+48h+var_20]
0x1800140f1  mov     [rsp+48h+var_20], rax
0x1800140f6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800140fb  mov     rax, rbx
0x1800140fe  add     rsp, 40h
0x180014102  pop     rbx
0x180014103  retn
```
