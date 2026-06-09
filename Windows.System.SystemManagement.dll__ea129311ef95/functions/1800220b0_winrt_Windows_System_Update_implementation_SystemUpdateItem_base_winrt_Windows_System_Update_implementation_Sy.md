# winrt::Windows::System::Update::implementation::SystemUpdateItem_base<winrt::Windows::System::Update::implementation::SystemUpdateItem,>::GetRuntimeClassName(void)

- ea: `0x1800220b0`
- end: `0x1800220d1`
- name: `?GetRuntimeClassName@?$SystemUpdateItem_base@USystemUpdateItem@implementation@Update@System@Windows@winrt@@$$V@implementation@Update@System@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005954`

## string_xrefs

- `0x1800220b9`: `Windows.System.Update.SystemUpdateItem`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::System::Update::implementation::SystemUpdateItem_base<winrt::Windows::System::Update::implementation::SystemUpdateItem,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.System.Update.SystemUpdateItem");
  return a2;
}

```

## disassembly

```asm
0x1800220b0  push    rbx
0x1800220b2  sub     rsp, 30h
0x1800220b6  mov     rbx, rdx
0x1800220b9  lea     rdx, aWindowsSystemU_0; "Windows.System.Update.SystemUpdateItem"
0x1800220c0  mov     rcx, rbx; this
0x1800220c3  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800220c8  mov     rax, rbx
0x1800220cb  add     rsp, 30h
0x1800220cf  pop     rbx
0x1800220d0  retn
```
