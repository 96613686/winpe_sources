# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,>::GetRuntimeClassName(void)

- ea: `0x180014d50`
- end: `0x180014d78`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdate_base@UWindowsSoftwareUpdate@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014d62`: `Windows.Management.Update.WindowsSoftwareUpdate`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdate,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdate", 0x2Fu);
  return a2;
}

```

## disassembly

```asm
0x180014d50  push    rbx
0x180014d52  sub     rsp, 30h
0x180014d56  mov     rbx, rdx
0x180014d59  mov     r8d, 2Fh ; '/'; unsigned int
0x180014d5f  mov     rcx, rbx; this
0x180014d62  lea     rdx, aWindowsManagem_15; "Windows.Management.Update.WindowsSoftwa"...
0x180014d69  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014d6e  mov     rax, rbx
0x180014d71  add     rsp, 30h
0x180014d75  pop     rbx
0x180014d76  retn
```
