# CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceRemoved(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x18000fa80`
- end: `0x18000faad`
- name: `?OnDeviceRemoved@CMidi2UmpProtocolDownscalerMidiTransform@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fa80`
- `0x180011e0c`

## pseudocode

```c
__int64 __fastcall CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceRemoved(__int64 a1, __int64 *a2, __int64 *a3)
{
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return 0;
}

```

## disassembly

```asm
0x18000fa80  push    rbx
0x18000fa82  sub     rsp, 20h
0x18000fa86  cmp     qword ptr [rdx], 0
0x18000fa8a  mov     rbx, r8
0x18000fa8d  jz      short loc_18000FA97
0x18000fa8f  mov     rcx, rdx
0x18000fa92  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fa97  cmp     qword ptr [rbx], 0
0x18000fa9b  jz      short loc_18000FAA5
0x18000fa9d  mov     rcx, rbx
0x18000faa0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000faa5  xor     eax, eax
0x18000faa7  add     rsp, 20h
0x18000faab  pop     rbx
0x18000faac  retn
```
