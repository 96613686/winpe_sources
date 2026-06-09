# CMidi2KSAggregateMidiEndpointManager::~CMidi2KSAggregateMidiEndpointManager(void)

- ea: `0x18000dbc0`
- end: `0x18000dc85`
- name: `??1CMidi2KSAggregateMidiEndpointManager@@UEAA@XZ`
- size: `197`
- prototype: `void __fastcall(CMidi2KSAggregateMidiEndpointManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000e040`

## callees

- `0x18000c684`
- `0x18000d3c0`
- `0x18000d4dc`
- `0x18000d54c`
- `0x18000d5bc`
- `0x18000d62c`
- `0x18000d69c`
- `0x18000dbc0`
- `0x180010b94`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dc3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dc3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMidi2KSAggregateMidiEndpointManager::~CMidi2KSAggregateMidiEndpointManager(
        CMidi2KSAggregateMidiEndpointManager *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 22);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ((char *)this + 160);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ((char *)this + 144);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ((char *)this + 128);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ((char *)this + 112);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ((char *)this + 96);
  if ( *((_QWORD *)this + 11) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 88);
  std::_Tree<std::_Tmap_traits<std::wstring,KsAggregateEndpointDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KsAggregateEndpointDefinition>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,KsAggregateEndpointDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KsAggregateEndpointDefinition>>,0>>((char *)this + 72);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000dbc0  push    rbx
0x18000dbc2  sub     rsp, 20h
0x18000dbc6  mov     rbx, rcx
0x18000dbc9  mov     rcx, [rcx+0B0h]; hObject
0x18000dbd0  test    rcx, rcx
0x18000dbd3  jz      short loc_18000DBE8
0x18000dbd5  call    cs:__imp_CloseHandle
0x18000dbdb  mov     rcx, [rsp+28h]; this
0x18000dbe0  test    eax, eax
0x18000dbe2  jz      loc_18000DC7A
0x18000dbe8  lea     rcx, [rbx+0A0h]
0x18000dbef  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BGI@AA@impl@winrt@@QEAA@XZ
0x18000dbf4  lea     rcx, [rbx+90h]
0x18000dbfb  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BHI@AA@impl@winrt@@QEAA@XZ
0x18000dc00  lea     rcx, [rbx+80h]
0x18000dc07  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BEI@AA@impl@winrt@@QEAA@XZ
0x18000dc0c  lea     rcx, [rbx+70h]
0x18000dc10  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BFI@AA@impl@winrt@@QEAA@XZ
0x18000dc15  lea     rcx, [rbx+60h]
0x18000dc19  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ
0x18000dc1e  lea     rcx, [rbx+58h]
0x18000dc22  cmp     qword ptr [rcx], 0
0x18000dc26  jz      short loc_18000DC2D
0x18000dc28  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000dc2d  lea     rcx, [rbx+48h]
0x18000dc31  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKsAggregateEndpointDefinition@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKsAggregateEndpointDefinition@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,KsAggregateEndpointDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KsAggregateEndpointDefinition>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,KsAggregateEndpointDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,KsAggregateEndpointDefinition>>,0>>(void)
0x18000dc36  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000dc3a  call    cs:__imp_DeleteCriticalSection
0x18000dc40  nop
0x18000dc41  mov     rcx, [rbx+18h]
0x18000dc45  test    rcx, rcx
0x18000dc48  jz      short loc_18000DC57
0x18000dc4a  mov     rax, [rcx]
0x18000dc4d  mov     rax, [rax+10h]
0x18000dc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc56  nop
0x18000dc57  mov     rcx, [rbx+10h]
0x18000dc5b  test    rcx, rcx
0x18000dc5e  jz      short loc_18000DC6D
0x18000dc60  mov     rax, [rcx]
0x18000dc63  mov     rax, [rax+10h]
0x18000dc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc6c  nop
0x18000dc6d  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000dc74  add     rsp, 20h
0x18000dc78  pop     rbx
0x18000dc79  retn
0x18000dc7a  mov     edx, 0A0Bh; void *
0x18000dc7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
