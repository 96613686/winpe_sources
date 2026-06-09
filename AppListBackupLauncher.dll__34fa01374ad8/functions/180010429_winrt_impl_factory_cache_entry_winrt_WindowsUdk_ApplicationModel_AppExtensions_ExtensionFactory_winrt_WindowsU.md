# _winrt::impl::factory_cache_entry_winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory_winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics_::call__lambda_7b7c9298bfeaa6f21443744179c3c395__&__::_1_::dtor$3

- ea: `0x180010429`
- end: `0x180010435`
- name: `_winrt::impl::factory_cache_entry_winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory_winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics_::call__lambda_7b7c9298bfeaa6f21443744179c3c395__&__::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006568`

## pseudocode

```c
void __fastcall winrt::impl::factory_cache_entry_winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory_winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics_::call__lambda_7b7c9298bfeaa6f21443744179c3c395_____::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((winrt::impl::factory_count_guard *)(a2 + 56));
}

```

## disassembly

```asm
0x180010429  lea     rcx, [rdx+38h]; this
0x180010430  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
