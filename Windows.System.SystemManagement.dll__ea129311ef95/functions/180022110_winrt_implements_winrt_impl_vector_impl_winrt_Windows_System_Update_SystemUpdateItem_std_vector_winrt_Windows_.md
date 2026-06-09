# winrt::implements<winrt::impl::vector_impl<winrt::Windows::System::Update::SystemUpdateItem,std::vector<winrt::Windows::System::Update::SystemUpdateItem,std::allocator<winrt::Windows::System::Update::SystemUpdateItem>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::System::Update::SystemUpdateItem>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::Update::SystemUpdateItem>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::System::Update::SystemUpdateItem>>::GetRuntimeClassName(void)

- ea: `0x180022110`
- end: `0x180022144`
- name: `?GetRuntimeClassName@?$implements@U?$vector_impl@USystemUpdateItem@Update@System@Windows@winrt@@V?$vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@USystemUpdateItem@Update@System@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@USystemUpdateItem@Update@System@Windows@winrt@@@5673@U?$IIterable@USystemUpdateItem@Update@System@Windows@winrt@@@5673@@winrt@@EEBA?AUhstring@2@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005930`

## string_xrefs

- `0x180022122`: `Windows.Foundation.Collections.IVector`1<Windows.System.Update.SystemUpdateItem>`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::impl::vector_impl<winrt::Windows::System::Update::SystemUpdateItem,std::vector<winrt::Windows::System::Update::SystemUpdateItem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::System::Update::SystemUpdateItem>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::Update::SystemUpdateItem>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::System::Update::SystemUpdateItem>>::GetRuntimeClassName(
        __int64 a1,
        __int64 a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 80;
  v4[0] = L"Windows.Foundation.Collections.IVector`1<Windows.System.Update.SystemUpdateItem>";
  winrt::hstring::hstring(a2, v4);
  return a2;
}

```

## disassembly

```asm
0x180022110  push    rbx
0x180022112  sub     rsp, 40h
0x180022116  mov     rbx, rdx
0x180022119  mov     [rsp+48h+var_18], 50h ; 'P'
0x180022122  lea     rax, ??$name_v@U?$IVector@USystemUpdateItem@Update@System@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0FB@@std@@B; "Windows.Foundation.Collections.IVector`"...
0x180022129  mov     rcx, rbx
0x18002212c  lea     rdx, [rsp+48h+var_20]
0x180022131  mov     [rsp+48h+var_20], rax
0x180022136  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18002213b  mov     rax, rbx
0x18002213e  add     rsp, 40h
0x180022142  pop     rbx
0x180022143  retn
```
