# winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo_base<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo,>::GetRuntimeClassName(void)

- ea: `0x1800220e0`
- end: `0x180022101`
- name: `?GetRuntimeClassName@?$SystemUpdateLastErrorInfo_base@USystemUpdateLastErrorInfo@implementation@Update@System@Windows@winrt@@$$V@implementation@Update@System@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005954`

## string_xrefs

- `0x1800220e9`: `Windows.System.Update.SystemUpdateLastErrorInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo_base<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.System.Update.SystemUpdateLastErrorInfo");
  return a2;
}

```

## disassembly

```asm
0x1800220e0  push    rbx
0x1800220e2  sub     rsp, 30h
0x1800220e6  mov     rbx, rdx
0x1800220e9  lea     rdx, aWindowsSystemU_2; "Windows.System.Update.SystemUpdateLastE"...
0x1800220f0  mov     rcx, rbx; this
0x1800220f3  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800220f8  mov     rax, rbx
0x1800220fb  add     rsp, 30h
0x1800220ff  pop     rbx
0x180022100  retn
```
