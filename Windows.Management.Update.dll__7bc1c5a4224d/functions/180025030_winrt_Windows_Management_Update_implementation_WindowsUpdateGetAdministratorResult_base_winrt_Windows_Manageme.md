# winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult_base<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,>::GetRuntimeClassName(void)

- ea: `0x180025030`
- end: `0x180025064`
- name: `?GetRuntimeClassName@?$WindowsUpdateGetAdministratorResult_base@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180025042`: `Windows.Management.Update.WindowsUpdateGetAdministratorResult`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult_base<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 61;
  v4[0] = L"Windows.Management.Update.WindowsUpdateGetAdministratorResult";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180025030  push    rbx
0x180025032  sub     rsp, 40h
0x180025036  mov     rbx, rdx
0x180025039  mov     [rsp+48h+var_18], 3Dh ; '='
0x180025042  lea     rax, aWindowsManagem_0; "Windows.Management.Update.WindowsUpdate"...
0x180025049  mov     rcx, rbx
0x18002504c  lea     rdx, [rsp+48h+var_20]
0x180025051  mov     [rsp+48h+var_20], rax
0x180025056  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18002505b  mov     rax, rbx
0x18002505e  add     rsp, 40h
0x180025062  pop     rbx
0x180025063  retn
```
