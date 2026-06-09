# winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(void)

- ea: `0x180024180`
- end: `0x1800241b4`
- name: `?GetRuntimeClassName@?$implements@U?$vector_impl@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@5673@U?$IIterable@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@5673@@winrt@@EEBA?AUhstring@2@XZ`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800114ec`

## string_xrefs

- `0x180024192`: `Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdate>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::impl::vector_impl<winrt::Windows::Management::Update::WindowsSoftwareUpdate,std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdate>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Management::Update::WindowsSoftwareUpdate>>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 89;
  v4[0] = L"Windows.Foundation.Collections.IVector`1<Windows.Management.Update.WindowsSoftwareUpdate>";
  winrt::hstring::hstring(a2, (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180024180  push    rbx
0x180024182  sub     rsp, 40h
0x180024186  mov     rbx, rdx
0x180024189  mov     [rsp+48h+var_18], 59h ; 'Y'
0x180024192  lea     rax, ??$name_v@U?$IVector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0FK@@std@@B; "Windows.Foundation.Collections.IVector`"...
0x180024199  mov     rcx, rbx
0x18002419c  lea     rdx, [rsp+48h+var_20]
0x1800241a1  mov     [rsp+48h+var_20], rax
0x1800241a6  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x1800241ab  mov     rax, rbx
0x1800241ae  add     rsp, 40h
0x1800241b2  pop     rbx
0x1800241b3  retn
```
