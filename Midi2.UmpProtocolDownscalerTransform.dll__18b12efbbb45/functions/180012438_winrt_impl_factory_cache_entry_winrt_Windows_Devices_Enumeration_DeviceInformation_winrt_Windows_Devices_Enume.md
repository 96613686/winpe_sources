# _winrt::impl::factory_cache_entry_winrt::Windows::Devices::Enumeration::DeviceInformation_winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2_::call__winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher_::_2_::_lambda_1__&__::_1_::dtor$3

- ea: `0x180012438`
- end: `0x180012444`
- name: `_winrt::impl::factory_cache_entry_winrt::Windows::Devices::Enumeration::DeviceInformation_winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2_::call__winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher_::_2_::_lambda_1__&__::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d408`

## pseudocode

```c
void __fastcall winrt::impl::factory_cache_entry_winrt::Windows::Devices::Enumeration::DeviceInformation_winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2_::call__winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher_::_2_::_lambda_1_____::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((winrt::impl::factory_count_guard *)(a2 + 152));
}

```

## disassembly

```asm
0x180012438  lea     rcx, [rdx+98h]; this
0x18001243f  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
