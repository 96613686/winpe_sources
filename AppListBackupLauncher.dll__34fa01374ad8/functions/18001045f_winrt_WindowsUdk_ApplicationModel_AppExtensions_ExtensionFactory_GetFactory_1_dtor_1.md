# _winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory_::_1_::dtor$1

- ea: `0x18001045f`
- end: `0x18001046b`
- name: `_winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006568`

## pseudocode

```c
void __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((winrt::impl::factory_count_guard *)(a2 + 112));
}

```

## disassembly

```asm
0x18001045f  lea     rcx, [rdx+70h]; this
0x180010466  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
