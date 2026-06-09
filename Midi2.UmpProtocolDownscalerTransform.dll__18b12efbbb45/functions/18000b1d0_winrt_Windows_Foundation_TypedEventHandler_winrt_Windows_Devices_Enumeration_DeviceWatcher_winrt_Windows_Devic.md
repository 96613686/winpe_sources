# winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(CMidi2UmpProtocolDownscalerMidiTransform *,long (CMidi2UmpProtocolDownscalerMidiTransform::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))

- ea: `0x18000b1d0`
- end: `0x18000b22f`
- name: `??$?0VCMidi2UmpProtocolDownscalerMidiTransform@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2UmpProtocolDownscalerMidiTransform@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UDeviceInformationUpdate@6723@@Z@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e950`

## callees

- `0x180002ec0`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
        _QWORD *a1,
        __int64 a2,
        __int128 *a3)
{
  __int128 v4; // xmm6
  char *v7; // [rsp+40h] [rbp+8h]

  v4 = *a3;
  v7 = (char *)operator new(0x28u);
  *((_DWORD *)v7 + 2) = 1;
  *((_QWORD *)v7 + 2) = a2;
  *(_OWORD *)(v7 + 24) = v4;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v7 = ___7__delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Foundation_Windows_winrt__V_lambda_17____0_____0VCMidi2UmpProtocolDownscalerMidiTransform__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Z_1234_QEAA_PEAVCMidi2UmpProtocolDownscalerMidiTransform__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformationUpdate_8934__Z_Z__impl_winrt__6B_;
  *a1 = v7;
  return a1;
}

```

## disassembly

```asm
0x18000b1d0  mov     [rsp+arg_8], rbx
0x18000b1d5  push    rdi
0x18000b1d6  sub     rsp, 30h
0x18000b1da  mov     rdi, rcx
0x18000b1dd  movaps  [rsp+38h+var_18], xmm6
0x18000b1e2  movups  xmm6, xmmword ptr [r8]
0x18000b1e6  mov     ecx, 28h ; '('; Size
0x18000b1eb  mov     rbx, rdx
0x18000b1ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b1f3  mov     [rsp+38h+arg_0], rax
0x18000b1f8  mov     dword ptr [rax+8], 1
0x18000b1ff  mov     [rax+10h], rbx
0x18000b203  movdqu  xmmword ptr [rax+18h], xmm6
0x18000b208  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000b20f  mov     rbx, [rsp+38h+arg_8]
0x18000b214  lea     rcx, ??_7?$delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@V_lambda_17__@?0???$?0VCMidi2UmpProtocolDownscalerMidiTransform@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@1234@QEAA@PEAVCMidi2UmpProtocolDownscalerMidiTransform@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformationUpdate@8934@@Z@Z@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::DeviceWatcher(CMidi2UmpProtocolDownscalerMidiTransform *,long (CMidi2UmpProtocolDownscalerMidiTransform::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))'::`1'::_lambda_17__>::`vftable'
0x18000b21b  movaps  xmm6, [rsp+38h+var_18]
0x18000b220  mov     [rax], rcx
0x18000b223  mov     [rdi], rax
0x18000b226  mov     rax, rdi
0x18000b229  add     rsp, 30h
0x18000b22d  pop     rdi
0x18000b22e  retn
```
