# winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(void)

- ea: `0x1800241c0`
- end: `0x1800241f4`
- name: `?GetRuntimeClassName@?$implements@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@winrt@@EEBA?AUhstring@2@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x1800241d2`: `Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdate>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 91;
  v4[0] = L"Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdate>";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x1800241c0  push    rbx
0x1800241c2  sub     rsp, 40h
0x1800241c6  mov     rbx, rdx
0x1800241c9  mov     [rsp+48h+var_18], 5Bh ; '['
0x1800241d2  lea     rax, ??$name_v@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0FM@@std@@B; "Windows.Foundation.Collections.IIterato"...
0x1800241d9  mov     rcx, rbx
0x1800241dc  lea     rdx, [rsp+48h+var_20]
0x1800241e1  mov     [rsp+48h+var_20], rax
0x1800241e6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800241eb  mov     rax, rbx
0x1800241ee  add     rsp, 40h
0x1800241f2  pop     rbx
0x1800241f3  retn
```
