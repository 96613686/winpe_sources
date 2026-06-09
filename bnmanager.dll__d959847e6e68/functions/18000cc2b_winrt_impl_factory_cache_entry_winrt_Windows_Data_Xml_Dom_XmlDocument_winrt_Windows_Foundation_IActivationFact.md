# _winrt::impl::factory_cache_entry_winrt::Windows::Data::Xml::Dom::XmlDocument_winrt::Windows::Foundation::IActivationFactory_::call_winrt::Windows::Data::Xml::Dom::XmlDocument_(__cdecl_)(winrt::Windows::Foundation::IActivationFactory_const_&)__::_1_::dtor$0

- ea: `0x18000cc2b`
- end: `0x18000cc37`
- name: `_winrt::impl::factory_cache_entry_winrt::Windows::Data::Xml::Dom::XmlDocument_winrt::Windows::Foundation::IActivationFactory_::call_winrt::Windows::Data::Xml::Dom::XmlDocument_(__cdecl_)(winrt::Windows::Foundation::IActivationFactory_const_&)__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180005540`

## pseudocode

```c
void __fastcall winrt::impl::factory_cache_entry_winrt::Windows::Data::Xml::Dom::XmlDocument_winrt::Windows::Foundation::IActivationFactory_::call_winrt::Windows::Data::Xml::Dom::XmlDocument____cdecl___winrt::Windows::Foundation::IActivationFactory_const_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement((winrt::Windows::Data::Xml::Dom::XmlElement *)(a2 + 168));
}

```

## disassembly

```asm
0x18000cc2b  lea     rcx, [rdx+0A8h]; this
0x18000cc32  jmp     ??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)
```
