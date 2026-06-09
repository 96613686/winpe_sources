# winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(void)

- ea: `0x180020230`
- end: `0x180020258`
- name: `?GetRuntimeClassName@?$implements@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@5673@U?$IIterable@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@5673@@winrt@@EEBA?AUhstring@2@XZ`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180012078`

## string_xrefs

- `0x180020242`: `Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>`

## pseudocode

```c
winrt::hstring *__fastcall winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(
    a2,
    L"Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>",
    0x69u);
  return a2;
}

```

## disassembly

```asm
0x180020230  push    rbx
0x180020232  sub     rsp, 30h
0x180020236  mov     rbx, rdx
0x180020239  mov     r8d, 69h ; 'i'; unsigned int
0x18002023f  mov     rcx, rbx; this
0x180020242  lea     rdx, ??$name_v@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0GK@@std@@B; "Windows.Foundation.Collections.IVector`"...
0x180020249  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18002024e  mov     rax, rbx
0x180020251  add     rsp, 30h
0x180020255  pop     rbx
0x180020256  retn
```
