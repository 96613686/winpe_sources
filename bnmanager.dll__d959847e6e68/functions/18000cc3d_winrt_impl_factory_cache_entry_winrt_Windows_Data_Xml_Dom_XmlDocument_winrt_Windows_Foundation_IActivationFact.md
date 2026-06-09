# _winrt::impl::factory_cache_entry_winrt::Windows::Data::Xml::Dom::XmlDocument_winrt::Windows::Foundation::IActivationFactory_::call_winrt::Windows::Data::Xml::Dom::XmlDocument_(__cdecl_)(winrt::Windows::Foundation::IActivationFactory_const_&)__::_1_::dtor$3

- ea: `0x18000cc3d`
- end: `0x18000cc49`
- name: `_winrt::impl::factory_cache_entry_winrt::Windows::Data::Xml::Dom::XmlDocument_winrt::Windows::Foundation::IActivationFactory_::call_winrt::Windows::Data::Xml::Dom::XmlDocument_(__cdecl_)(winrt::Windows::Foundation::IActivationFactory_const_&)__::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800057b4`

## pseudocode

```c
void __fastcall winrt::impl::factory_cache_entry_winrt::Windows::Data::Xml::Dom::XmlDocument_winrt::Windows::Foundation::IActivationFactory_::call_winrt::Windows::Data::Xml::Dom::XmlDocument____cdecl___winrt::Windows::Foundation::IActivationFactory_const_____::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((volatile signed __int64 **)(a2 + 144));
}

```

## disassembly

```asm
0x18000cc3d  lea     rcx, [rdx+90h]; this
0x18000cc44  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
