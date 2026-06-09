# winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)

- ea: `0x1800106e0`
- end: `0x18001074f`
- name: `??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ`
- size: `111`
- prototype: `winrt::Windows::Data::Xml::Dom::XmlDocument *__fastcall(winrt::Windows::Data::Xml::Dom::XmlDocument *this)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011e50`
- `0x1800120b8`
- `0x180016a30`
- `0x180016b6c`
- `0x18001874c`

## callees

- `0x18000eef0`
- `0x18000fb20`
- `0x1800106e0`

## pseudocode

```c
winrt::Windows::Data::Xml::Dom::XmlDocument *__fastcall winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(
        winrt::Windows::Data::Xml::Dom::XmlDocument *this)
{
  void (__fastcall *v3)(__int64, __int64 *); // [rsp+30h] [rbp+8h] BYREF

  v3 = (void (__fastcall *)(__int64, __int64 *))&qword_180027A58;
  _InterlockedIncrement64(&qword_180027A58);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> )
  {
    winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>,
      this);
    _InterlockedDecrement64(&qword_180027A58);
  }
  else
  {
    _InterlockedDecrement64(&qword_180027A58);
    v3 = (void (__fastcall *)(__int64, __int64 *))_lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Xml::Dom::XmlDocument (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      (__int64 *)this,
      (__int64)this,
      &v3);
  }
  return this;
}

```

## disassembly

```asm
0x1800106e0  mov     [rsp+arg_0], rcx
0x1800106e5  push    rbx
0x1800106e6  sub     rsp, 20h
0x1800106ea  mov     rbx, rcx
0x1800106ed  lea     rax, qword_180027A58
0x1800106f4  mov     [rsp+28h+arg_0], rax
0x1800106f9  lock inc cs:qword_180027A58
0x180010701  cmp     cs:??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, 0; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x180010709  jz      short loc_180010725
0x18001070b  mov     rdx, rcx
0x18001070e  lea     rcx, ??$factory_cache_entry_v@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Xml::Dom::XmlDocument,winrt::Windows::Foundation::IActivationFactory>
0x180010715  call    ??$ActivateInstance@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUXmlDocument@Dom@Xml@Data@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Data::Xml::Dom::XmlDocument>(void)
0x18001071a  nop
0x18001071b  lock dec cs:qword_180027A58
0x180010723  jmp     short loc_180010746
0x180010725  lock dec cs:qword_180027A58
0x18001072d  lea     rax, ?_lambda_invoker_cdecl_@_lambda_e39067982572d3667926157dc9eb0f0a_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_e39067982572d3667926157dc9eb0f0a_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180010734  mov     [rsp+28h+arg_0], rax
0x180010739  lea     r8, [rsp+28h+arg_0]
0x18001073e  mov     rdx, rbx
0x180010741  call    ??$call@P6A?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UXmlDocument@Dom@Xml@Data@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUXmlDocument@Dom@Xml@Data@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z
0x180010746  mov     rax, rbx
0x180010749  add     rsp, 20h
0x18001074d  pop     rbx
0x18001074e  retn
```
