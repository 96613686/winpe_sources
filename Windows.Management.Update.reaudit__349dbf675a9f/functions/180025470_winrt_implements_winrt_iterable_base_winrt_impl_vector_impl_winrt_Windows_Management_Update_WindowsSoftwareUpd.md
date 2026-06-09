# winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(void)

- ea: `0x180025470`
- end: `0x180025498`
- name: `?GetRuntimeClassName@?$implements@Uiterator@?$iterable_base@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWindowsSoftwareUpdate@Update@Management@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@@winrt@@EEBA?AUhstring@2@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180025482`: `Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdate>`

## pseudocode

```c
winrt::hstring *__fastcall winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Management::Update::WindowsSoftwareUpdate,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(
    a2,
    L"Windows.Foundation.Collections.IIterator`1<Windows.Management.Update.WindowsSoftwareUpdate>",
    0x5Bu);
  return a2;
}

```

## disassembly

```asm
0x180025470  push    rbx
0x180025472  sub     rsp, 30h
0x180025476  mov     rbx, rdx
0x180025479  mov     r8d, 5Bh ; '['; unsigned int
0x18002547f  mov     rcx, rbx; this
0x180025482  lea     rdx, ??$name_v@U?$IIterator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0FM@@std@@B; "Windows.Foundation.Collections.IIterato"...
0x180025489  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18002548e  mov     rax, rbx
0x180025491  add     rsp, 30h
0x180025495  pop     rbx
0x180025496  retn
```
