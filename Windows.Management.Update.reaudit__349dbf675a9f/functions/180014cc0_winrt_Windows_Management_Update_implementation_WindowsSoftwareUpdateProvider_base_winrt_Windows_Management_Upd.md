# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider,>::GetRuntimeClassName(void)

- ea: `0x180014cc0`
- end: `0x180014ce8`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateProvider_base@UWindowsSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014cd2`: `Windows.Management.Update.WindowsSoftwareUpdateProvider`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateProvider,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateProvider", 0x37u);
  return a2;
}

```

## disassembly

```asm
0x180014cc0  push    rbx
0x180014cc2  sub     rsp, 30h
0x180014cc6  mov     rbx, rdx
0x180014cc9  mov     r8d, 37h ; '7'; unsigned int
0x180014ccf  mov     rcx, rbx; this
0x180014cd2  lea     rdx, aWindowsManagem_13; "Windows.Management.Update.WindowsSoftwa"...
0x180014cd9  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014cde  mov     rax, rbx
0x180014ce1  add     rsp, 30h
0x180014ce5  pop     rbx
0x180014ce6  retn
```
