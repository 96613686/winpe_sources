# winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(void)

- ea: `0x180020260`
- end: `0x180020288`
- name: `?GetRuntimeClassName@?$implements@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@winrt@@EEBA?AUhstring@2@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180020272`: `Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>`

## pseudocode

```c
winrt::hstring *__fastcall winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(
    a2,
    L"Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>",
    0x6Bu);
  return a2;
}

```

## disassembly

```asm
0x180020260  push    rbx
0x180020262  sub     rsp, 30h
0x180020266  mov     rbx, rdx
0x180020269  mov     r8d, 6Bh ; 'k'; unsigned int
0x18002026f  mov     rcx, rbx; this
0x180020272  lea     rdx, ??$name_v@U?$IIterator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0GM@@std@@B; "Windows.Foundation.Collections.IIterato"...
0x180020279  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18002027e  mov     rax, rbx
0x180020281  add     rsp, 30h
0x180020285  pop     rbx
0x180020286  retn
```
