# _winrt::impl::factory_cache_entry_winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory_winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics_::call__lambda_7b7c9298bfeaa6f21443744179c3c395__&__::_1_::dtor$0

- ea: `0x180010417`
- end: `0x180010423`
- name: `_winrt::impl::factory_cache_entry_winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory_winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics_::call__lambda_7b7c9298bfeaa6f21443744179c3c395__&__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005b54`

## pseudocode

```c
void __fastcall winrt::impl::factory_cache_entry_winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory_winrt::WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics_::call__lambda_7b7c9298bfeaa6f21443744179c3c395_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)(a2 + 160));
}

```

## disassembly

```asm
0x180010417  lea     rcx, [rdx+0A0h]; this
0x18001041e  jmp     ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
```
