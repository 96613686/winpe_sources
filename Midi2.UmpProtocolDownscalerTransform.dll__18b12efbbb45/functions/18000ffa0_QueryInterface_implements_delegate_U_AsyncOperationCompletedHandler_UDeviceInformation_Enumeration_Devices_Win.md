# ?QueryInterface@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z

- ea: `0x18000ffa0`
- end: `0x18000ffc1`
- name: `?QueryInterface@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001176c`

## pseudocode

```c
__int64 __fastcall _QueryInterface___implements_delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__UEAAHAEBUguid_3_PEAPEAX_Z(
        int a1,
        int a2,
        int a3)
{
  return winrt::impl::implements_delegate_base::query_interface(
           a1 + 8,
           a2,
           a3,
           a1,
           (__int64)winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Devices::Enumeration::DeviceInformation>>);
}

```

## disassembly

```asm
0x18000ffa0  sub     rsp, 38h
0x18000ffa4  mov     r9, rcx
0x18000ffa7  lea     rax, ??$guid_v@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Devices::Enumeration::DeviceInformation>>
0x18000ffae  add     rcx, 8
0x18000ffb2  mov     [rsp+38h+var_18], rax
0x18000ffb7  call    ?query_interface@implements_delegate_base@impl@winrt@@QEAAIAEBUguid@3@PEAPEAXPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@0@Z; winrt::impl::implements_delegate_base::query_interface(winrt::guid const &,void * *,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,winrt::guid const &)
0x18000ffbc  add     rsp, 38h
0x18000ffc0  retn
```
