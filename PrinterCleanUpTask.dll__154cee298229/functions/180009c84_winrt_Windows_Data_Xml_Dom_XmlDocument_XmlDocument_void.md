# winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)

- ea: `0x180009c84`
- end: `0x180009cf3`
- name: `??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ`
- size: `111`
- prototype: `struct IUnknown *__fastcall(struct IUnknown *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000cc58`
- `0x180012918`
- `0x180012a58`

## callees

- `0x180007708`
- `0x180008910`
- `0x180009c84`

## pseudocode

```c
struct IUnknown *__fastcall winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(struct IUnknown *this)
{
  void (__fastcall *v3)(__int64, __int64 *); // [rsp+30h] [rbp+8h] BYREF

  v3 = (void (__fastcall *)(__int64, __int64 *))&qword_1800227D8;
  _InterlockedIncrement64(&qword_1800227D8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> )
  {
    winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>,
      this);
    _InterlockedDecrement64(&qword_1800227D8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1800227D8);
    v3 = (void (__fastcall *)(__int64, __int64 *))_lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Xml::Dom::XmlDocument (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      this,
      (__int64)this,
      &v3);
  }
  return this;
}

```

## disassembly

```asm
0x180009c84  mov     [rsp+arg_0], rcx
0x180009c89  push    rbx
0x180009c8a  sub     rsp, 20h
0x180009c8e  mov     rbx, rcx
0x180009c91  lea     rax, qword_1800227D8
0x180009c98  mov     [rsp+28h+arg_0], rax
0x180009c9d  lock inc cs:qword_1800227D8
0x180009ca5  cmp     cs:??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, 0; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x180009cad  jz      short loc_180009CC9
0x180009caf  mov     rdx, rcx
0x180009cb2  lea     rcx, ??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x180009cb9  call    ??$ActivateInstance@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUXmlDocument@Dom@Xml@Data@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(void)
0x180009cbe  nop
0x180009cbf  lock dec cs:qword_1800227D8
0x180009cc7  jmp     short loc_180009CEA
0x180009cc9  lock dec cs:qword_1800227D8
0x180009cd1  lea     rax, ?_lambda_invoker_cdecl_@_lambda_e39067982572d3667926157dc9eb0f0a_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180009cd8  mov     [rsp+28h+arg_0], rax
0x180009cdd  lea     r8, [rsp+28h+arg_0]
0x180009ce2  mov     rdx, rbx
0x180009ce5  call    ??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z
0x180009cea  mov     rax, rbx
0x180009ced  add     rsp, 20h
0x180009cf1  pop     rbx
0x180009cf2  retn
```
