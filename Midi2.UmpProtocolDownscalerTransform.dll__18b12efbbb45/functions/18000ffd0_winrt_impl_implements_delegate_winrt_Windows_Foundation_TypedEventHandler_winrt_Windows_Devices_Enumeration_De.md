# winrt::impl::implements_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>::DeviceWatcher(CMidi2UmpProtocolDownscalerMidiTransform *,long (CMidi2UmpProtocolDownscalerMidiTransform::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation))'::`1'::_lambda_16__>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x18000ffd0`
- end: `0x18000fff1`
- name: `?QueryInterface@?$implements_delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Foundation@Windows@winrt@@V_lambda_16__@?0???$?0VCMidi2UmpProtocolDownscalerMidiTransform@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Z@1234@QEAA@PEAVCMidi2UmpProtocolDownscalerMidiTransform@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformation@8934@@Z@Z@@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001176c`

## pseudocode

```c
__int64 __fastcall _QueryInterface___implements_delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Foundation_Windows_winrt__V_lambda_16____0_____0VCMidi2UmpProtocolDownscalerMidiTransform__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Z_1234_QEAA_PEAVCMidi2UmpProtocolDownscalerMidiTransform__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformation_8934__Z_Z__impl_winrt__UEAAHAEBUguid_3_PEAPEAX_Z(
        int a1,
        int a2,
        int a3)
{
  return winrt::impl::implements_delegate_base::query_interface(
           a1 + 8,
           a2,
           a3,
           a1,
           (__int64)winrt::impl::guid_v<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>>);
}

```

## disassembly

```asm
0x18000ffd0  sub     rsp, 38h
0x18000ffd4  mov     r9, rcx
0x18000ffd7  lea     rax, ??$guid_v@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>>
0x18000ffde  add     rcx, 8
0x18000ffe2  mov     [rsp+38h+var_18], rax
0x18000ffe7  call    ?query_interface@implements_delegate_base@impl@winrt@@QEAAIAEBUguid@3@PEAPEAXPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@0@Z; winrt::impl::implements_delegate_base::query_interface(winrt::guid const &,void * *,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,winrt::guid const &)
0x18000ffec  add     rsp, 38h
0x18000fff0  retn
```
