# winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(void)

- ea: `0x18001efa0`
- end: `0x18001efd4`
- name: `?GetRuntimeClassName@?$implements@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@winrt@@EEBA?AUhstring@2@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x18001efb2`: `Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 107;
  v4[0] = L"Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x18001efa0  push    rbx
0x18001efa2  sub     rsp, 40h
0x18001efa6  mov     rbx, rdx
0x18001efa9  mov     [rsp+48h+var_18], 6Bh ; 'k'
0x18001efb2  lea     rax, ??$name_v@U?$IIterator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0GM@@std@@B; "Windows.Foundation.Collections.IIterato"...
0x18001efb9  mov     rcx, rbx
0x18001efbc  lea     rdx, [rsp+48h+var_20]
0x18001efc1  mov     [rsp+48h+var_20], rax
0x18001efc6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001efcb  mov     rax, rbx
0x18001efce  add     rsp, 40h
0x18001efd2  pop     rbx
0x18001efd3  retn
```
