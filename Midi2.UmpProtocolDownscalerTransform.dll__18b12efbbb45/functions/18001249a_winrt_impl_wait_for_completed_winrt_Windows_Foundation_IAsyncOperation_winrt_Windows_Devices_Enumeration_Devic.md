# _winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_1_::dtor$1

- ea: `0x18001249a`
- end: `0x1800124a6`
- name: `_winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d4a8`

## pseudocode

```c
BOOL __fastcall winrt::impl::wait_for_completed_winrt::Windows::Foundation::IAsyncOperation_winrt::Windows::Devices::Enumeration::DeviceInformation____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return `winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>>'::`2'::shared_type::~shared_type((void **)(a2 + 32));
}

```

## disassembly

```asm
0x18001249a  lea     rcx, [rdx+20h]
0x1800124a1  jmp     ??1shared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@2@I@Z@QEAA@XZ
```
