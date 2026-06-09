# winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::System::Update::SystemUpdateItem,std::vector<winrt::Windows::System::Update::SystemUpdateItem,std::allocator<winrt::Windows::System::Update::SystemUpdateItem>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::System::Update::SystemUpdateItem,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::System::Update::SystemUpdateItem>>::GetRuntimeClassName(void)

- ea: `0x180022190`
- end: `0x1800221c4`
- name: `?GetRuntimeClassName@?$implements@Uiterator@?$iterable_base@U?$vector_impl@USystemUpdateItem@Update@System@Windows@winrt@@V?$vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@USystemUpdateItem@Update@System@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@USystemUpdateItem@Update@System@Windows@winrt@@@Collections@Foundation@Windows@3@@winrt@@EEBA?AUhstring@2@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005930`

## string_xrefs

- `0x1800221a2`: `Windows.Foundation.Collections.IIterator`1<Windows.System.Update.SystemUpdateItem>`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::System::Update::SystemUpdateItem,std::vector<winrt::Windows::System::Update::SystemUpdateItem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::System::Update::SystemUpdateItem,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::System::Update::SystemUpdateItem>>::GetRuntimeClassName(
        __int64 a1,
        __int64 a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 82;
  v4[0] = L"Windows.Foundation.Collections.IIterator`1<Windows.System.Update.SystemUpdateItem>";
  winrt::hstring::hstring(a2, v4);
  return a2;
}

```

## disassembly

```asm
0x180022190  push    rbx
0x180022192  sub     rsp, 40h
0x180022196  mov     rbx, rdx
0x180022199  mov     [rsp+48h+var_18], 52h ; 'R'
0x1800221a2  lea     rax, ??$name_v@U?$IIterator@USystemUpdateItem@Update@System@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0FD@@std@@B; "Windows.Foundation.Collections.IIterato"...
0x1800221a9  mov     rcx, rbx
0x1800221ac  lea     rdx, [rsp+48h+var_20]
0x1800221b1  mov     [rsp+48h+var_20], rax
0x1800221b6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800221bb  mov     rax, rbx
0x1800221be  add     rsp, 40h
0x1800221c2  pop     rbx
0x1800221c3  retn
```
