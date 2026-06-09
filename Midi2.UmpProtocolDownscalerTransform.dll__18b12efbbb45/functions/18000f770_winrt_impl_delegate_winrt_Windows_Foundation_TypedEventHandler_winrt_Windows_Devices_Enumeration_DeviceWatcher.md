# winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::DeviceWatcher(CMidi2UmpProtocolDownscalerMidiTransform *,long (CMidi2UmpProtocolDownscalerMidiTransform::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))'::`1'::_lambda_17__>::Invoke(void *,void *)

- ea: `0x18000f770`
- end: `0x18000f7ee`
- name: `?Invoke@?$delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@V_lambda_17__@?0???$?0VCMidi2UmpProtocolDownscalerMidiTransform@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@1234@QEAA@PEAVCMidi2UmpProtocolDownscalerMidiTransform@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformationUpdate@8934@@Z@Z@@impl@winrt@@UEAAHPEAX0@Z`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f770`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall _Invoke___delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Foundation_Windows_winrt__V_lambda_17____0_____0VCMidi2UmpProtocolDownscalerMidiTransform__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformationUpdate_2345__Z_1234_QEAA_PEAVCMidi2UmpProtocolDownscalerMidiTransform__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformationUpdate_8934__Z_Z__impl_winrt__UEAAHPEAX0_Z(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  void (*v4)(void); // rsi
  __int64 result; // rax
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h]

  v4 = *(void (**)(void))(a1 + 24);
  v6 = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  v7 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  try
  {
    v4();
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000f770  mov     [rsp+arg_10], rbx
0x18000f775  mov     [rsp+arg_18], rsi
0x18000f77a  push    rdi
0x18000f77b  sub     rsp, 20h
0x18000f77f  mov     rbx, rdx
0x18000f782  movsxd  rdi, dword ptr [rcx+20h]
0x18000f786  add     rdi, [rcx+10h]
0x18000f78a  mov     rsi, [rcx+18h]
0x18000f78e  mov     [rsp+28h+arg_0], r8
0x18000f793  test    r8, r8
0x18000f796  jz      short loc_18000F7A7
0x18000f798  mov     rax, [r8]
0x18000f79b  mov     rcx, r8
0x18000f79e  mov     rax, [rax+8]
0x18000f7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7a7  mov     [rsp+28h+arg_8], rbx
0x18000f7ac  test    rbx, rbx
0x18000f7af  jz      short loc_18000F7C0
0x18000f7b1  mov     rdx, [rbx]
0x18000f7b4  mov     rcx, rbx
0x18000f7b7  mov     rax, [rdx+8]
0x18000f7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7c0  lea     r8, [rsp+28h+arg_0]
0x18000f7c5  lea     rdx, [rsp+28h+arg_8]
0x18000f7ca  mov     rcx, rdi
0x18000f7cd  mov     rax, rsi
0x18000f7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7d5  xor     eax, eax
0x18000f7d7  jmp     short loc_18000F7DD
0x18000f7d9  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000f7dd  mov     rbx, [rsp+28h+arg_10]
0x18000f7e2  mov     rsi, [rsp+28h+arg_18]
0x18000f7e7  add     rsp, 20h
0x18000f7eb  pop     rdi
0x18000f7ec  retn
```
