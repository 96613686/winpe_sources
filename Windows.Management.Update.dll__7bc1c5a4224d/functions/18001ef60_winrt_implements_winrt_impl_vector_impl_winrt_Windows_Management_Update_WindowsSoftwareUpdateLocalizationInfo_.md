# winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(void)

- ea: `0x18001ef60`
- end: `0x18001ef94`
- name: `?GetRuntimeClassName@?$implements@U?$vector_impl@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@5673@U?$IIterable@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@5673@@winrt@@EEBA?AUhstring@2@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x18001ef72`: `Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 105;
  v4[0] = L"Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdateLocalizationInfo>";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x18001ef60  push    rbx
0x18001ef62  sub     rsp, 40h
0x18001ef66  mov     rbx, rdx
0x18001ef69  mov     [rsp+48h+var_18], 69h ; 'i'
0x18001ef72  lea     rax, ??$name_v@U?$IVector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0GK@@std@@B; "Windows.Foundation.Collections.IVector`"...
0x18001ef79  mov     rcx, rbx
0x18001ef7c  lea     rdx, [rsp+48h+var_20]
0x18001ef81  mov     [rsp+48h+var_20], rax
0x18001ef86  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001ef8b  mov     rax, rbx
0x18001ef8e  add     rsp, 40h
0x18001ef92  pop     rbx
0x18001ef93  retn
```
