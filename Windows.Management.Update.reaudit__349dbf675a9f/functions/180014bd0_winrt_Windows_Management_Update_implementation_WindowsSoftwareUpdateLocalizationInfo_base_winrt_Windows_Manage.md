# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,>::GetRuntimeClassName(void)

- ea: `0x180014bd0`
- end: `0x180014bf8`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateLocalizationInfo_base@UWindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014be2`: `Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo", 0x3Fu);
  return a2;
}

```

## disassembly

```asm
0x180014bd0  push    rbx
0x180014bd2  sub     rsp, 30h
0x180014bd6  mov     rbx, rdx
0x180014bd9  mov     r8d, 3Fh ; '?'; unsigned int
0x180014bdf  mov     rcx, rbx; this
0x180014be2  lea     rdx, aWindowsManagem_5; "Windows.Management.Update.WindowsSoftwa"...
0x180014be9  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014bee  mov     rax, rbx
0x180014bf1  add     rsp, 30h
0x180014bf5  pop     rbx
0x180014bf6  retn
```
