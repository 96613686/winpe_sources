# CMidi2UmpProtocolDownscalerMidiTransform::~CMidi2UmpProtocolDownscalerMidiTransform(void)

- ea: `0x18000d36c`
- end: `0x18000d3e5`
- name: `??1CMidi2UmpProtocolDownscalerMidiTransform@@UEAA@XZ`
- size: `121`
- prototype: `void __fastcall(CMidi2UmpProtocolDownscalerMidiTransform *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d900`

## callees

- `0x18000d0ac`
- `0x18000d118`
- `0x18000d188`
- `0x18000d1f8`
- `0x18000d36c`
- `0x180011e0c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d3d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d3d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMidi2UmpProtocolDownscalerMidiTransform::~CMidi2UmpProtocolDownscalerMidiTransform(
        CMidi2UmpProtocolDownscalerMidiTransform *this)
{
  __int64 v2; // rcx

  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ((char *)this + 192);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ((char *)this + 176);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ((char *)this + 160);
  if ( *((_QWORD *)this + 19) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 152);
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  std::wstring::~wstring((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000d36c  push    rbx
0x18000d36e  sub     rsp, 20h
0x18000d372  mov     rbx, rcx
0x18000d375  add     rcx, 0C0h
0x18000d37c  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BEI@AA@impl@winrt@@QEAA@XZ
0x18000d381  lea     rcx, [rbx+0B0h]
0x18000d388  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BFI@AA@impl@winrt@@QEAA@XZ
0x18000d38d  lea     rcx, [rbx+0A0h]
0x18000d394  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ
0x18000d399  lea     rcx, [rbx+98h]
0x18000d3a0  cmp     qword ptr [rcx], 0
0x18000d3a4  jz      short loc_18000D3AC
0x18000d3a6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d3ab  nop
0x18000d3ac  mov     rcx, [rbx+88h]
0x18000d3b3  test    rcx, rcx
0x18000d3b6  jz      short loc_18000D3C5
0x18000d3b8  mov     rax, [rcx]
0x18000d3bb  mov     rax, [rax+10h]
0x18000d3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c4  nop
0x18000d3c5  lea     rcx, [rbx+68h]
0x18000d3c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d3ce  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000d3d2  call    cs:__imp_DeleteCriticalSection
0x18000d3d8  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000d3df  add     rsp, 20h
0x18000d3e3  pop     rbx
0x18000d3e4  retn
```
