# _winrt::impl::factory_cache_entry_winrt::Windows::Devices::Enumeration::DeviceInformation_winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2_::call__winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher_::_2_::_lambda_1__&__::_1_::dtor$0

- ea: `0x180012426`
- end: `0x180012432`
- name: `_winrt::impl::factory_cache_entry_winrt::Windows::Devices::Enumeration::DeviceInformation_winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2_::call__winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher_::_2_::_lambda_1__&__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d000`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry_winrt::Windows::Devices::Enumeration::DeviceInformation_winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2_::call__winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher_::_2_::_lambda_1_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x180012426  lea     rcx, [rdx+80h]
0x18001242d  jmp     ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
```
