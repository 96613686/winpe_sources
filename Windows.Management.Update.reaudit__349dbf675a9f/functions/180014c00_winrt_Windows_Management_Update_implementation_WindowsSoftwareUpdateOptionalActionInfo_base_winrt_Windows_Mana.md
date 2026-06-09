# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo,>::GetRuntimeClassName(void)

- ea: `0x180014c00`
- end: `0x180014c28`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateOptionalActionInfo_base@UWindowsSoftwareUpdateOptionalActionInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014c12`: `Windows.Management.Update.WindowsSoftwareUpdateOptionalActionInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateOptionalActionInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateOptionalActionInfo", 0x41u);
  return a2;
}

```

## disassembly

```asm
0x180014c00  push    rbx
0x180014c02  sub     rsp, 30h
0x180014c06  mov     rbx, rdx
0x180014c09  mov     r8d, 41h ; 'A'; unsigned int
0x180014c0f  mov     rcx, rbx; this
0x180014c12  lea     rdx, aWindowsManagem_10; "Windows.Management.Update.WindowsSoftwa"...
0x180014c19  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014c1e  mov     rax, rbx
0x180014c21  add     rsp, 30h
0x180014c25  pop     rbx
0x180014c26  retn
```
