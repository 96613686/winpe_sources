# winrt::impl::implements_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::DeviceWatcher(CMidi2UmpProtocolDownscalerMidiTransform *,long (CMidi2UmpProtocolDownscalerMidiTransform::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))'::`1'::_lambda_17__>::AddRef(void)

- ea: `0x18000dbd0`
- end: `0x18000dbd9`
- name: `?AddRef@?$implements_delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@V_lambda_17__@?0???$?0VCMidi2UmpProtocolDownscalerMidiTransform@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@1234@QEAA@PEAVCMidi2UmpProtocolDownscalerMidiTransform@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformationUpdate@8934@@Z@Z@@impl@winrt@@UEAAIXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800114dc`

## pseudocode

```c
unsigned int __fastcall _AddRef___implements_delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Foundation_Windows_winrt__V_lambda_17____0_____0VCMidi2UmpProtocolDownscalerMidiTransform__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Z_1234_QEAA_PEAVCMidi2UmpProtocolDownscalerMidiTransform__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformationUpdate_8934__Z_Z__impl_winrt__UEAAIXZ(
        __int64 a1)
{
  return winrt::impl::implements_delegate_base::increment_reference((winrt::impl::implements_delegate_base *)(a1 + 8));
}

```

## disassembly

```asm
0x18000dbd0  add     rcx, 8; this
0x18000dbd4  jmp     ?increment_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::increment_reference(void)
```
