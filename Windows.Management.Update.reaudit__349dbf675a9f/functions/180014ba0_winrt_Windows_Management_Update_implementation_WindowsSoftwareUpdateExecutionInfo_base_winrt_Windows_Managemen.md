# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,>::GetRuntimeClassName(void)

- ea: `0x180014ba0`
- end: `0x180014bc8`
- name: `?GetRuntimeClassName@?$WindowsSoftwareUpdateExecutionInfo_base@UWindowsSoftwareUpdateExecutionInfo@implementation@Update@Management@Windows@winrt@@$$V@implementation@Update@Management@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180014bb2`: `Windows.Management.Update.WindowsSoftwareUpdateExecutionInfo`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo_base<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateExecutionInfo,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Management.Update.WindowsSoftwareUpdateExecutionInfo", 0x3Cu);
  return a2;
}

```

## disassembly

```asm
0x180014ba0  push    rbx
0x180014ba2  sub     rsp, 30h
0x180014ba6  mov     rbx, rdx
0x180014ba9  mov     r8d, 3Ch ; '<'; unsigned int
0x180014baf  mov     rcx, rbx; this
0x180014bb2  lea     rdx, aWindowsManagem_4; "Windows.Management.Update.WindowsSoftwa"...
0x180014bb9  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x180014bbe  mov     rax, rbx
0x180014bc1  add     rsp, 30h
0x180014bc5  pop     rbx
0x180014bc6  retn
```
