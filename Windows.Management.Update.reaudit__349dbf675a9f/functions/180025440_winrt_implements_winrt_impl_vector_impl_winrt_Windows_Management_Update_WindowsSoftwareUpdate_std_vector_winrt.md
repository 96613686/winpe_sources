# winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(void)

- ea: `0x180025440`
- end: `0x180025468`
- name: `?GetRuntimeClassName@?$implements@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@5673@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@5673@@winrt@@EEBA?AUhstring@2@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180025452`: `Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdate>`

## pseudocode

```c
winrt::hstring *__fastcall winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(
    a2,
    L"Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdate>",
    0x59u);
  return a2;
}

```

## disassembly

```asm
0x180025440  push    rbx
0x180025442  sub     rsp, 30h
0x180025446  mov     rbx, rdx
0x180025449  mov     r8d, 59h ; 'Y'; unsigned int
0x18002544f  mov     rcx, rbx; this
0x180025452  lea     rdx, ??$name_v@U?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0FK@@std@@B; "Windows.Foundation.Collections.IVector`"...
0x180025459  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18002545e  mov     rax, rbx
0x180025461  add     rsp, 30h
0x180025465  pop     rbx
0x180025466  retn
```
