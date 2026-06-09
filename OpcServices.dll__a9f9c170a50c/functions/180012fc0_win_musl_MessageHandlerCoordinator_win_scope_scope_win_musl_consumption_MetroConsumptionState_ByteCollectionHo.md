# win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::DoDerecurse(void)

- ea: `0x180012fc0`
- end: `0x18001337e`
- name: `?DoDerecurse@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@AEAAXXZ`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013d3c`

## callees

- `0x1800016b0`
- `0x180001abc`
- `0x180011438`
- `0x180012d18`
- `0x180012fa0`
- `0x180012fc0`
- `0x180014da8`
- `0x180015114`
- `0x1800303b0`
- `0x180031260`
- `0x180031d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013125`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013125`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013110`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013110`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::DoDerecurse(
        __int64 a1)
{
  __int64 v2; // r13
  __int64 v3; // rsi
  __int64 v4; // r15
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  __int64 *v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // r12
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  _QWORD *v14; // rdi
  bool v15; // dl
  win_dox *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  char v19; // di
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 result; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int128 v28; // [rsp+28h] [rbp-58h] BYREF
  __int128 v29; // [rsp+38h] [rbp-48h] BYREF
  __int128 v30; // [rsp+48h] [rbp-38h] BYREF
  char v31[16]; // [rsp+58h] [rbp-28h] BYREF
  char v32[8]; // [rsp+68h] [rbp-18h] BYREF
  win_scope::counted_strong_weak_base *v33[2]; // [rsp+70h] [rbp-10h] BYREF

  v2 = a1 + 8;
  v3 = a1 + 8;
  do
  {
    while ( 1 )
    {
      if ( *(_QWORD *)(a1 + 392) )
      {
        v4 = v2;
        v5 = *(_QWORD *)(a1 + 384);
        v6 = *(_QWORD *)(a1 + 376);
        v29 = 0;
        v7 = v5 - v6;
        if ( v6 > v5 )
          v7 = v5;
        v8 = *(__int64 **)(*(_QWORD *)(a1 + 368) + 8 * v7);
        v9 = *v8;
        if ( *v8 )
        {
          v10 = v8[1];
          if ( _InterlockedIncrement((volatile signed __int32 *)(v9 + 8)) == 1 )
            _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
          *(_QWORD *)&v29 = v9;
          *((_QWORD *)&v29 + 1) = v10;
        }
        else
        {
          v10 = *((_QWORD *)&v29 + 1);
          v9 = v29;
        }
        v11 = *(_QWORD *)(a1 + 392);
        if ( v11 )
        {
          v12 = *(_QWORD *)(a1 + 384);
          v13 = *(_QWORD *)(a1 + 368);
          v14 = *(_QWORD **)(v13 + 8 * v12);
          if ( *v14 && v14[1] )
          {
            win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(*(_QWORD *)(v13 + 8 * v12));
            *v14 = 0;
            v14[1] = 0;
            v11 = *(_QWORD *)(a1 + 392);
          }
          if ( *(_QWORD *)(a1 + 376) <= ++*(_QWORD *)(a1 + 384) )
            *(_QWORD *)(a1 + 384) = 0;
          *(_QWORD *)(a1 + 392) = v11 - 1;
          if ( v11 == 1 )
            *(_QWORD *)(a1 + 384) = 0;
        }
        v28 = 0;
        if ( v9 )
        {
          if ( _InterlockedIncrement((volatile signed __int32 *)(v9 + 8)) == 1 )
            _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
          *(_QWORD *)&v28 = v9;
          *((_QWORD *)&v28 + 1) = v10;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 296));
        v16 = (win_dox *)*(unsigned int *)(v2 + 340);
        *(_DWORD *)(v2 + 340) = (_DWORD)v16 + 1;
        if ( !(_DWORD)v16 )
          *(_DWORD *)(v2 + 336) = GetCurrentThreadId();
        LOBYTE(v16) = *(_BYTE *)(v2 + 288);
        win_dox::ThrowIfFailed(v16, v15);
        v30 = 0;
        v17 = v28;
        if ( (_QWORD)v28 )
        {
          v18 = *((_QWORD *)&v28 + 1);
          if ( _InterlockedIncrement((volatile signed __int32 *)(v28 + 8)) == 1 )
            _InterlockedIncrement((volatile signed __int32 *)(v17 + 12));
          *(_QWORD *)&v30 = v17;
          *((_QWORD *)&v30 + 1) = v18;
        }
        v19 = win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>::ProcessMessage(
                v2,
                &v30);
        if ( !v19 )
        {
          if ( v2 )
            v20 = v2 + 56;
          else
            v20 = 0;
          v30 = 0;
          v21 = v28;
          if ( (_QWORD)v28 )
          {
            v22 = *((_QWORD *)&v28 + 1);
            if ( _InterlockedIncrement((volatile signed __int32 *)(v28 + 8)) == 1 )
              _InterlockedIncrement((volatile signed __int32 *)(v21 + 12));
            *(_QWORD *)&v30 = v21;
            *((_QWORD *)&v30 + 1) = v22;
          }
          v19 = win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::ProcessMessage(
                  v20,
                  &v30);
        }
        if ( (*(_DWORD *)(v2 + 340))-- == 1 )
          *(_DWORD *)(v2 + 336) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 296));
        if ( *((_QWORD *)&v28 + 1) && (_QWORD)v28 )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v28);
          v28 = 0;
        }
        if ( v19 )
        {
          v27 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                  v31,
                  &v29);
          _RemoveMessage___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAAXV__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope___Z(
            v2,
            v27);
        }
        if ( v9 && v10 )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v29);
          v29 = 0;
        }
      }
      else
      {
        v4 = v3;
        v19 = 0;
      }
      if ( !v19 )
      {
        _ProcessAnEventHandler___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAA_AU__pair__NV__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope___std__XZ(
          v4,
          (__int64)v32);
        v19 = v32[0];
        if ( v32[0] )
        {
          v30 = 0;
          if ( v33[0] )
          {
            win_scope::counted_strong_weak_base::AddRef(v33[0]);
            *(_QWORD *)&v30 = v25;
            *((_QWORD *)&v30 + 1) = v26;
          }
          _RemoveMessage___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAAXV__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope___Z(
            v4,
            &v30);
        }
        if ( v33[1] && v33[0] )
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v33);
      }
      if ( *(_BYTE *)(a1 + 4)
        && !v19
        && (unsigned __int8)_EventQueueEmpty___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAA_NXZ(v4) )
      {
        break;
      }
      v3 = v4;
      if ( !v19 )
        goto LABEL_52;
    }
    if ( !*(_QWORD *)(a1 + 392) )
      _PurgeHandlers___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAAXXZ(v4);
LABEL_52:
    v3 = v4;
    result = _EventQueueEmpty___MessageHandlers_V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib_____MessageHandlerCoordinator_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__type_list_V__KeyedMessageHandler_V__basic_string__WU__char_traits__W_std__V__allocator__W_2_V_STL70___std__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VUriHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVUriHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl__UUriExtractor_MetroConsumptionState_consumption_6__win_musl__V__type_list_V__BroadcastMessageHandler_V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__EventHandler_VBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__V__scope_PEAVByteCollectionHolder_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___win_scope__V__scope_PEAVBroadcastHandlerBase_MetroConsumptionState_consumption_win_musl__U__const_policies_Ushared_policies_win_scope___win_scope___6__win_musl___win_musl__Vnull_type_win_mp_lib___win_mp_lib___win_mp_lib___win_musl__QEAA_NXZ(v4);
  }
  while ( !(_BYTE)result || *(_QWORD *)(a1 + 392) );
  return result;
}

```

## disassembly

```asm
0x180012fc0  mov     rax, rsp
0x180012fc3  push    rbp
0x180012fc4  push    rsi
0x180012fc5  push    rdi
0x180012fc6  push    r12
0x180012fc8  push    r13
0x180012fca  push    r14
0x180012fcc  push    r15
0x180012fce  mov     rbp, rsp
0x180012fd1  sub     rsp, 80h
0x180012fd8  mov     [rbp+var_60], 0FFFFFFFFFFFFFFFEh
0x180012fe0  mov     [rax+20h], rbx
0x180012fe4  mov     rbx, rcx
0x180012fe7  lea     r13, [rcx+8]
0x180012feb  mov     rsi, r13
0x180012fee  xor     r14d, r14d
0x180012ff1  cmp     [rbx+188h], r14
0x180012ff8  jz      loc_1800132D2
0x180012ffe  mov     r15, r13
0x180013001  mov     rdx, [rbx+180h]
0x180013008  mov     rax, [rbx+178h]
0x18001300f  xorps   xmm0, xmm0
0x180013012  movdqu  [rbp+var_48], xmm0
0x180013017  mov     rcx, rdx
0x18001301a  sub     rcx, rax
0x18001301d  cmp     rax, rdx
0x180013020  cmova   rcx, rdx
0x180013024  mov     rax, [rbx+170h]
0x18001302b  mov     rdx, [rax+rcx*8]
0x18001302f  mov     rsi, [rdx]
0x180013032  test    rsi, rsi
0x180013035  jz      loc_180013353
0x18001303b  mov     r12, [rdx+8]
0x18001303f  mov     eax, 1
0x180013044  lock xadd [rsi+8], eax
0x180013049  inc     eax
0x18001304b  cmp     eax, 1
0x18001304e  jz      loc_1800132B7
0x180013054  mov     qword ptr [rbp+var_48], rsi
0x180013058  mov     qword ptr [rbp+var_48+8], r12
0x18001305c  mov     rdx, [rbx+188h]
0x180013063  test    rdx, rdx
0x180013066  jz      short loc_1800130D0
0x180013068  mov     rcx, [rbx+180h]
0x18001306f  mov     rax, [rbx+170h]
0x180013076  mov     rdi, [rax+rcx*8]
0x18001307a  cmp     [rdi], r14
0x18001307d  jz      short loc_18001309B
0x18001307f  cmp     [rdi+8], r14
0x180013083  jz      short loc_18001309B
0x180013085  mov     rcx, rdi
0x180013088  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18001308d  mov     [rdi], r14
0x180013090  mov     [rdi+8], r14
0x180013094  mov     rdx, [rbx+188h]
0x18001309b  inc     qword ptr [rbx+180h]
0x1800130a2  mov     rax, [rbx+180h]
0x1800130a9  cmp     [rbx+178h], rax
0x1800130b0  ja      short loc_1800130B9
0x1800130b2  mov     [rbx+180h], r14
0x1800130b9  lea     rax, [rdx-1]
0x1800130bd  mov     [rbx+188h], rax
0x1800130c4  test    rax, rax
0x1800130c7  jnz     short loc_1800130D0
0x1800130c9  mov     [rbx+180h], r14
0x1800130d0  xorps   xmm0, xmm0
0x1800130d3  movdqu  [rbp+var_58], xmm0
0x1800130d8  test    rsi, rsi
0x1800130db  jz      short loc_1800130FA
0x1800130dd  mov     eax, 1
0x1800130e2  lock xadd [rsi+8], eax
0x1800130e7  inc     eax
0x1800130e9  cmp     eax, 1
0x1800130ec  jz      loc_1800132C0
0x1800130f2  mov     qword ptr [rbp+var_58], rsi
0x1800130f6  mov     qword ptr [rbp+var_58+8], r12
0x1800130fa  lea     rax, [rbp+var_58]
0x1800130fe  mov     [rbp+arg_0], rax
0x180013102  lea     r14, [r13+128h]
0x180013109  mov     [rbp+arg_8], r14
0x18001310d  mov     rcx, r14; lpCriticalSection
0x180013110  call    cs:__imp_EnterCriticalSection
0x180013116  mov     ecx, [r14+2Ch]
0x18001311a  lea     eax, [rcx+1]
0x18001311d  mov     [r14+2Ch], eax
0x180013121  test    ecx, ecx
0x180013123  jnz     short loc_18001312F
0x180013125  call    cs:__imp_GetCurrentThreadId
0x18001312b  mov     [r14+28h], eax
0x18001312f  mov     cl, [r13+120h]; this
0x180013136  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x18001313b  xorps   xmm0, xmm0
0x18001313e  movdqu  [rbp+var_38], xmm0
0x180013143  mov     rcx, qword ptr [rbp+var_58]
0x180013147  test    rcx, rcx
0x18001314a  jz      short loc_18001316D
0x18001314c  mov     rdx, qword ptr [rbp+var_58+8]
0x180013150  mov     eax, 1
0x180013155  lock xadd [rcx+8], eax
0x18001315a  inc     eax
0x18001315c  cmp     eax, 1
0x18001315f  jz      loc_1800132C9
0x180013165  mov     qword ptr [rbp+var_38], rcx
0x180013169  mov     qword ptr [rbp+var_38+8], rdx
0x18001316d  lea     rdx, [rbp+var_38]
0x180013171  mov     rcx, r13
0x180013174  call    ?ProcessMessage@?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@QEAA_NV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>::ProcessMessage(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>)
0x180013179  mov     dil, al
0x18001317c  test    al, al
0x18001317e  jnz     short loc_1800131CB
0x180013180  test    r13, r13
0x180013183  jz      loc_1800132DD
0x180013189  lea     rcx, [r13+38h]
0x18001318d  xorps   xmm0, xmm0
0x180013190  movdqu  [rbp+var_38], xmm0
0x180013195  mov     rdx, qword ptr [rbp+var_58]
0x180013199  test    rdx, rdx
0x18001319c  jz      short loc_1800131BF
0x18001319e  mov     r8, qword ptr [rbp+var_58+8]
0x1800131a2  mov     eax, 1
0x1800131a7  lock xadd [rdx+8], eax
0x1800131ac  inc     eax
0x1800131ae  cmp     eax, 1
0x1800131b1  jz      loc_1800132E4
0x1800131b7  mov     qword ptr [rbp+var_38], rdx
0x1800131bb  mov     qword ptr [rbp+var_38+8], r8
0x1800131bf  lea     rdx, [rbp+var_38]
0x1800131c3  call    ?ProcessMessage@?$MessageHandlers@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::ProcessMessage(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800131c8  mov     dil, al
0x1800131cb  add     dword ptr [r14+2Ch], 0FFFFFFFFh
0x1800131d0  jnz     short loc_1800131DA
0x1800131d2  mov     dword ptr [r14+28h], 0
0x1800131da  mov     rcx, r14; lpCriticalSection
0x1800131dd  call    cs:__imp_LeaveCriticalSection
0x1800131e3  nop
0x1800131e4  xor     r14d, r14d
0x1800131e7  cmp     qword ptr [rbp+var_58+8], r14
0x1800131eb  jz      short loc_180013204
0x1800131ed  cmp     qword ptr [rbp+var_58], r14
0x1800131f1  jz      short loc_180013204
0x1800131f3  lea     rcx, [rbp+var_58]
0x1800131f7  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800131fc  xorps   xmm0, xmm0
0x1800131ff  movdqu  [rbp+var_58], xmm0
0x180013204  test    dil, dil
0x180013207  jnz     loc_180013360
0x18001320d  test    rsi, rsi
0x180013210  jz      short loc_18001321B
0x180013212  test    r12, r12
0x180013215  jnz     loc_1800132A1
0x18001321b  test    dil, dil
0x18001321e  jnz     short loc_180013250
0x180013220  lea     rdx, [rbp+var_18]
0x180013224  mov     rcx, r15
0x180013227  call    ?ProcessAnEventHandler@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA?AU?$pair@_NV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@XZ
0x18001322c  nop
0x18001322d  mov     dil, [rbp+var_18]
0x180013231  test    dil, dil
0x180013234  jnz     loc_1800132ED
0x18001323a  cmp     [rbp+var_8], r14
0x18001323e  jz      short loc_180013250
0x180013240  cmp     [rbp+var_10], r14
0x180013244  jz      short loc_180013250
0x180013246  lea     rcx, [rbp+var_10]
0x18001324a  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18001324f  nop
0x180013250  cmp     [rbx+4], r14b
0x180013254  jnz     loc_180013320
0x18001325a  mov     rsi, r15
0x18001325d  test    dil, dil
0x180013260  jnz     loc_180012FF1
0x180013266  mov     rsi, r15
0x180013269  mov     rcx, r15
0x18001326c  call    ?EventQueueEmpty@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NXZ
0x180013271  test    al, al
0x180013273  jz      loc_180012FF1
0x180013279  cmp     [rbx+188h], r14
0x180013280  jnz     loc_180012FF1
0x180013286  mov     rbx, [rsp+80h+arg_18]
0x18001328e  add     rsp, 80h
0x180013295  pop     r15
0x180013297  pop     r14
0x180013299  pop     r13
0x18001329b  pop     r12
0x18001329d  pop     rdi
0x18001329e  pop     rsi
0x18001329f  pop     rbp
0x1800132a0  retn
0x1800132a1  lea     rcx, [rbp+var_48]
0x1800132a5  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800132aa  xorps   xmm0, xmm0
0x1800132ad  movdqu  [rbp+var_48], xmm0
0x1800132b2  jmp     loc_18001321B
0x1800132b7  lock inc dword ptr [rsi+0Ch]
0x1800132bb  jmp     loc_180013054
0x1800132c0  lock inc dword ptr [rsi+0Ch]
0x1800132c4  jmp     loc_1800130F2
0x1800132c9  lock inc dword ptr [rcx+0Ch]
0x1800132cd  jmp     loc_180013165
0x1800132d2  mov     r15, rsi
0x1800132d5  mov     dil, r14b
0x1800132d8  jmp     loc_18001321B
0x1800132dd  xor     ecx, ecx
0x1800132df  jmp     loc_18001318D
0x1800132e4  lock inc dword ptr [rdx+0Ch]
0x1800132e8  jmp     loc_1800131B7
0x1800132ed  xorps   xmm0, xmm0
0x1800132f0  movdqu  [rbp+var_38], xmm0
0x1800132f5  mov     rcx, [rbp+var_10]; this
0x1800132f9  test    rcx, rcx
0x1800132fc  jz      short loc_18001330F
0x1800132fe  mov     rdx, [rbp+var_8]
0x180013302  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x180013307  mov     qword ptr [rbp+var_38], rcx
0x18001330b  mov     qword ptr [rbp+var_38+8], rdx
0x18001330f  lea     rdx, [rbp+var_38]
0x180013313  mov     rcx, r15
0x180013316  call    ?RemoveMessage@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAAXV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z
0x18001331b  jmp     loc_18001323A
0x180013320  test    dil, dil
0x180013323  jnz     loc_18001325A
0x180013329  mov     rcx, r15
0x18001332c  call    ?EventQueueEmpty@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NXZ
0x180013331  test    al, al
0x180013333  jz      loc_18001325A
0x180013339  cmp     [rbx+188h], r14
0x180013340  jnz     loc_180013266
0x180013346  mov     rcx, r15
0x180013349  call    ?PurgeHandlers@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAAXXZ
0x18001334e  jmp     loc_180013266
0x180013353  mov     r12, qword ptr [rbp+var_48+8]
0x180013357  mov     rsi, qword ptr [rbp+var_48]
0x18001335b  jmp     loc_18001305C
0x180013360  lea     rdx, [rbp+var_48]
0x180013364  lea     rcx, [rbp+var_28]
0x180013368  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18001336d  mov     rdx, rax
0x180013370  mov     rcx, r13
0x180013373  call    ?RemoveMessage@?$MessageHandlers@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAAXV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z
0x180013378  jmp     loc_18001320D
```
