# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider,>::GetRuntimeClassName(void)

- ea: `0x180014090`
- end: `0x1800140c4`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateProvider_base@UWindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x1800140a2`: `Windows.Management.Update.WindowsSoftwareUpdateProvider`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 55;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateProvider";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180014090  push    rbx
0x180014092  sub     rsp, 40h
0x180014096  mov     rbx, rdx
0x180014099  mov     [rsp+48h+var_18], 37h ; '7'
0x1800140a2  lea     rax, aWindowsManagem_13; "Windows.Management.Update.WindowsSoftwa"...
0x1800140a9  mov     rcx, rbx
0x1800140ac  lea     rdx, [rsp+48h+var_20]
0x1800140b1  mov     [rsp+48h+var_20], rax
0x1800140b6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800140bb  mov     rax, rbx
0x1800140be  add     rsp, 40h
0x1800140c2  pop     rbx
0x1800140c3  retn
```
