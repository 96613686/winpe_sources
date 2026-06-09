# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,>::GetRuntimeClassName(void)

- ea: `0x180014cf0`
- end: `0x180014d18`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateResult_base@UWindowsSoftwareUpdateResult@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014d02`: `Windows.Management.Update.WindowsSoftwareUpdateResult`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateResult,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateResult", 0x35u);
  return a2;
}

```

## disassembly

```asm
0x180014cf0  push    rbx
0x180014cf2  sub     rsp, 30h
0x180014cf6  mov     rbx, rdx
0x180014cf9  mov     r8d, 35h ; '5'; unsigned int
0x180014cff  mov     rcx, rbx; this
0x180014d02  lea     rdx, aWindowsManagem_18; "Windows.Management.Update.WindowsSoftwa"...
0x180014d09  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014d0e  mov     rax, rbx
0x180014d11  add     rsp, 30h
0x180014d15  pop     rbx
0x180014d16  retn
```
