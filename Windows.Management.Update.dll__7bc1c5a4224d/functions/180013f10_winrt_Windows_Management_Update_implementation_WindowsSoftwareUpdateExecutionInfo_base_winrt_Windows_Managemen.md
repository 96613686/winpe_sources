# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,>::GetRuntimeClassName(void)

- ea: `0x180013f10`
- end: `0x180013f44`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateExecutionInfo_base@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180013f22`: `Windows.Management.Update.WindowsSoftwareUpdateExecutionInfo`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 60;
  v4[0] = L"Windows.Management.Update.WindowsSoftwareUpdateExecutionInfo";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180013f10  push    rbx
0x180013f12  sub     rsp, 40h
0x180013f16  mov     rbx, rdx
0x180013f19  mov     [rsp+48h+var_18], 3Ch ; '<'
0x180013f22  lea     rax, aWindowsManagem_4; "Windows.Management.Update.WindowsSoftwa"...
0x180013f29  mov     rcx, rbx
0x180013f2c  lea     rdx, [rsp+48h+var_20]
0x180013f31  mov     [rsp+48h+var_20], rax
0x180013f36  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x180013f3b  mov     rax, rbx
0x180013f3e  add     rsp, 40h
0x180013f42  pop     rbx
0x180013f43  retn
```
