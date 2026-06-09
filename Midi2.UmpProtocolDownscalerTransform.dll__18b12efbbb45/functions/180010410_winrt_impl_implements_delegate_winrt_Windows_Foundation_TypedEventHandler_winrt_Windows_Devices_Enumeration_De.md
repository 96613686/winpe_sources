# winrt::impl::implements_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::DeviceWatcher(CMidi2UmpProtocolDownscalerMidiTransform *,long (CMidi2UmpProtocolDownscalerMidiTransform::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))'::`1'::_lambda_17__>::Release(void)

- ea: `0x180010410`
- end: `0x180010467`
- name: `?Release@?$implements_delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@V_lambda_17__@?0???$?0VCMidi2UmpProtocolDownscalerMidiTransform@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@1234@QEAA@PEAVCMidi2UmpProtocolDownscalerMidiTransform@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformationUpdate@8934@@Z@Z@@impl@winrt@@UEAAIXZ`
- size: `87`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002e94`
- `0x180010410`
- `0x180010f80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010460`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010460`

## pseudocode

```c
__int64 __fastcall _Release___implements_delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Foundation_Windows_winrt__V_lambda_17____0_____0VCMidi2UmpProtocolDownscalerMidiTransform__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Z_1234_QEAA_PEAVCMidi2UmpProtocolDownscalerMidiTransform__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformationUpdate_8934__Z_Z__impl_winrt__UEAAIXZ(
        char *Block)
{
  unsigned int v2; // edi

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(Block + 8));
  if ( !v2 && Block )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    operator delete(Block);
  }
  return v2;
}

```

## disassembly

```asm
0x180010410  mov     [rsp+arg_0], rbx
0x180010415  push    rdi
0x180010416  sub     rsp, 20h
0x18001041a  mov     rbx, rcx
0x18001041d  add     rcx, 8; this
0x180010421  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x180010426  mov     edi, eax
0x180010428  test    eax, eax
0x18001042a  jnz     short loc_18001044F
0x18001042c  test    rbx, rbx
0x18001042f  jz      short loc_18001044F
0x180010431  or      edx, 0FFFFFFFFh
0x180010434  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001043c  sub     edx, 1
0x18001043f  jnz     short loc_18001045C
0x180010441  nop
0x180010442  mov     edx, 28h ; '('
0x180010447  mov     rcx, rbx; Block
0x18001044a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001044f  mov     rbx, [rsp+28h+arg_0]
0x180010454  mov     eax, edi
0x180010456  add     rsp, 20h
0x18001045a  pop     rdi
0x18001045b  retn
0x18001045c  test    edx, edx
0x18001045e  jns     short loc_180010442
0x180010460  call    cs:__imp_abort
```
