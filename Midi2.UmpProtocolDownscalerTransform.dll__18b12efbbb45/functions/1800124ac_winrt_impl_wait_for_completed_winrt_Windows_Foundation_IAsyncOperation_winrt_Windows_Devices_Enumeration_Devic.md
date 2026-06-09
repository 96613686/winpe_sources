# _winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_1_::dtor$2

- ea: `0x1800124ac`
- end: `0x1800124b8`
- name: `_winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d000`

## pseudocode

```c
__int64 __fastcall winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((__int64 *)(a2 + 32));
}

```

## disassembly

```asm
0x1800124ac  lea     rcx, [rdx+20h]
0x1800124b3  jmp     ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
```
