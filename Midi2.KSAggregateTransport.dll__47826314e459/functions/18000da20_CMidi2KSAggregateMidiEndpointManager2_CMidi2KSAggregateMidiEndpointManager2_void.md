# CMidi2KSAggregateMidiEndpointManager2::~CMidi2KSAggregateMidiEndpointManager2(void)

- ea: `0x18000da20`
- end: `0x18000dbba`
- name: `??1CMidi2KSAggregateMidiEndpointManager2@@UEAA@XZ`
- size: `410`
- prototype: `void __fastcall(CMidi2KSAggregateMidiEndpointManager2 *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e000`

## callees

- `0x180005044`
- `0x18000c684`
- `0x18000cfc8`
- `0x18000d4dc`
- `0x18000d54c`
- `0x18000d5bc`
- `0x18000d62c`
- `0x18000d69c`
- `0x18000d7d8`
- `0x18000da20`
- `0x18000de1c`
- `0x180010b94`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000daeb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000db1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000db31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000daeb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000db1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000db31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dad1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMidi2KSAggregateMidiEndpointManager2::~CMidi2KSAggregateMidiEndpointManager2(
        CMidi2KSAggregateMidiEndpointManager2 *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  void *v5; // rcx
  unsigned int v6; // r8d
  const char *v7; // r9
  void *v8; // rcx
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ((char *)this + 344);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ((char *)this + 328);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ((char *)this + 312);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ((char *)this + 296);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ((char *)this + 280);
  if ( *((_QWORD *)this + 34) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref();
  std::jthread::~jthread((CMidi2KSAggregateMidiEndpointManager2 *)((char *)this + 248));
  v2 = (void *)*((_QWORD *)this + 30);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  v5 = (void *)*((_QWORD *)this + 29);
  if ( v5 && !CloseHandle(v5) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
  v8 = (void *)*((_QWORD *)this + 28);
  if ( v8 && !CloseHandle(v8) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *>>>(
    (char *)this + 168,
    (char *)this + 168,
    *(_QWORD *)(*((_QWORD *)this + 21) + 8LL));
  operator delete(*((void **)this + 21));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::~vector<std::shared_ptr<KsAggregateEndpointDefinition2>>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *>>>(
    (char *)this + 48,
    (char *)this + 48,
    *(_QWORD *)(*((_QWORD *)this + 6) + 8LL));
  operator delete(*((void **)this + 6));
  v11 = *((_QWORD *)this + 5);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = *((_QWORD *)this + 4);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000da20  mov     [rsp+arg_0], rbx
0x18000da25  push    rdi
0x18000da26  sub     rsp, 20h
0x18000da2a  mov     rdi, rcx
0x18000da2d  add     rcx, 158h
0x18000da34  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BGI@AA@impl@winrt@@QEAA@XZ
0x18000da39  lea     rcx, [rdi+148h]
0x18000da40  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BHI@AA@impl@winrt@@QEAA@XZ
0x18000da45  lea     rcx, [rdi+138h]
0x18000da4c  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BEI@AA@impl@winrt@@QEAA@XZ
0x18000da51  lea     rcx, [rdi+128h]
0x18000da58  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BFI@AA@impl@winrt@@QEAA@XZ
0x18000da5d  lea     rcx, [rdi+118h]
0x18000da64  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ
0x18000da69  lea     rcx, [rdi+110h]
0x18000da70  cmp     qword ptr [rcx], 0
0x18000da74  jz      short loc_18000DA7B
0x18000da76  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000da7b  lea     rcx, [rdi+0F8h]; this
0x18000da82  call    ??1jthread@std@@QEAA@XZ; std::jthread::~jthread(void)
0x18000da87  mov     rcx, [rdi+0F0h]; hObject
0x18000da8e  test    rcx, rcx
0x18000da91  jz      short loc_18000DAA6
0x18000da93  call    cs:__imp_CloseHandle
0x18000da99  mov     rcx, [rsp+28h]; this
0x18000da9e  test    eax, eax
0x18000daa0  jz      loc_18000DBA4
0x18000daa6  mov     rcx, [rdi+0E8h]; hObject
0x18000daad  test    rcx, rcx
0x18000dab0  jz      short loc_18000DAC5
0x18000dab2  call    cs:__imp_CloseHandle
0x18000dab8  mov     rcx, [rsp+28h]; this
0x18000dabd  test    eax, eax
0x18000dabf  jz      loc_18000DBAF
0x18000dac5  mov     rcx, [rdi+0E0h]; hObject
0x18000dacc  test    rcx, rcx
0x18000dacf  jz      short loc_18000DAE4
0x18000dad1  call    cs:__imp_CloseHandle
0x18000dad7  mov     rcx, [rsp+28h]; this
0x18000dadc  test    eax, eax
0x18000dade  jz      loc_18000DB99
0x18000dae4  lea     rcx, [rdi+0B8h]; lpCriticalSection
0x18000daeb  call    cs:__imp_DeleteCriticalSection
0x18000daf1  lea     rbx, [rdi+0A8h]
0x18000daf8  mov     r8, [rbx]
0x18000dafb  mov     r8, [r8+8]
0x18000daff  mov     rdx, rbx
0x18000db02  mov     rcx, rbx
0x18000db05  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *> *)
0x18000db0a  mov     edx, 50h ; 'P'
0x18000db0f  mov     rcx, [rbx]; Block
0x18000db12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000db17  lea     rcx, [rdi+80h]; lpCriticalSection
0x18000db1e  call    cs:__imp_DeleteCriticalSection
0x18000db24  lea     rcx, [rdi+68h]
0x18000db28  call    ??1?$vector@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@V?$allocator@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::~vector<std::shared_ptr<KsAggregateEndpointDefinition2>>(void)
0x18000db2d  lea     rcx, [rdi+40h]; lpCriticalSection
0x18000db31  call    cs:__imp_DeleteCriticalSection
0x18000db37  lea     rbx, [rdi+30h]
0x18000db3b  mov     r8, [rbx]
0x18000db3e  mov     r8, [r8+8]
0x18000db42  mov     rdx, rbx
0x18000db45  mov     rcx, rbx
0x18000db48  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UKsAggregateEndpointDefinition2@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<KsAggregateEndpointDefinition2>>,void *> *)
0x18000db4d  mov     edx, 50h ; 'P'
0x18000db52  mov     rcx, [rbx]; Block
0x18000db55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000db5a  nop
0x18000db5b  mov     rcx, [rdi+28h]
0x18000db5f  test    rcx, rcx
0x18000db62  jz      short loc_18000DB71
0x18000db64  mov     rax, [rcx]
0x18000db67  mov     rax, [rax+10h]
0x18000db6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db70  nop
0x18000db71  mov     rcx, [rdi+20h]
0x18000db75  test    rcx, rcx
0x18000db78  jz      short loc_18000DB87
0x18000db7a  mov     rax, [rcx]
0x18000db7d  mov     rax, [rax+10h]
0x18000db81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db86  nop
0x18000db87  mov     dword ptr [rdi+0Ch], 0C0000001h
0x18000db8e  mov     rbx, [rsp+28h+arg_0]
0x18000db93  add     rsp, 20h
0x18000db97  pop     rdi
0x18000db98  retn
0x18000db99  mov     edx, 0A0Bh; void *
0x18000db9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dba4  mov     edx, 0A0Bh; void *
0x18000dba9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dbaf  mov     edx, 0A0Bh; void *
0x18000dbb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
