# FSMonitorService::InternalShutdown(void)

- ea: `0x18000950c`
- end: `0x180009854`
- name: `?InternalShutdown@FSMonitorService@@IEAAJXZ`
- size: `840`
- prototype: `__int64 __fastcall(FSMonitorService *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c100`
- `0x18000cad0`

## callees

- `0x180003194`
- `0x180003294`
- `0x1800032d0`
- `0x1800060e8`
- `0x180006a68`
- `0x180006a98`
- `0x180006b84`
- `0x180007068`
- `0x1800071ac`
- `0x1800071e4`
- `0x18000950c`
- `0x18000af58`
- `0x18000d294`
- `0x18000d2f0`
- `0x18000d4f8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000957b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000957b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000958a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000958a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009677`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009725`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009749`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000968a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000968a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009693`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009693`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009635`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009635`
- `RPCRT4!RpcEpUnregister` at `0x1800096ac`
- `RPCRT4!RpcEpUnregister` at `0x1800096ac`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800096bf`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x1800096bf`
- `MFPlat!MFCancelWorkItem` at `0x180009656`
- `MFPlat!MFCancelWorkItem` at `0x180009656`
- `MFPlat!MFUnregisterPlatformFromMMCSS` at `0x1800097b0`
- `MFPlat!MFUnregisterPlatformFromMMCSS` at `0x1800097b0`
- `MFPlat!MFShutdown` at `0x1800097c4`
- `MFPlat!MFShutdown` at `0x1800097c4`
- `MFPlat!MFGetTimerPeriodicity` at `0x1800097ce`
- `MFPlat!MFGetTimerPeriodicity` at `0x1800097ce`

## pseudocode

```c
__int64 __fastcall FSMonitorService::InternalShutdown(FSMonitorService *this)
{
  struct _TP_TIMER *v2; // r14
  __int64 v3; // r12
  __int64 v4; // r15
  __int64 v5; // rax
  void *v6; // rdx
  struct _TP_TIMER *v7; // rcx
  MFWORKITEM_KEY v8; // rcx
  char v9; // r15
  char v10; // r12
  __int64 i; // rbx
  __int64 v12; // rcx
  int j; // ebx
  HANDLE *v14; // rdi
  DWORD v15; // eax
  int v16; // ecx
  signed int LastError; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  _QWORD v21[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details *Periodicity; // [rsp+80h] [rbp+30h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+88h] [rbp+38h] BYREF

  `vector constructor iterator'(v21, 0x10u, 2u, (void *(*)(void *))FSMWatcherEntry::FSMWatcherEntry);
  BindingVector = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 146, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 23) == 3 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  }
  else
  {
    v2 = 0;
    *((_DWORD *)this + 23) = 3;
    v3 = 0;
    v4 = 0;
    do
    {
      v5 = *(_QWORD *)((char *)this + v4 * 8 + 168);
      *(_QWORD *)((char *)this + v4 * 8 + 168) = v21[v4];
      v21[v4] = v5;
      Periodicity = (wil::details *)v21[v4 + 1];
      v21[v4 + 1] = 0;
      __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
        &v21[v4 + 1],
        (char *)this + v4 * 8 + 176);
      __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
        (char *)this + v4 * 8 + 176,
        &Periodicity);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &Periodicity,
        v6);
      ++v3;
      v4 += 2;
    }
    while ( v3 != 2 );
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>::swap(
      &BindingVector,
      (char *)this + 96);
    CTUnkArray<IFSMemory>::RemoveAll((char *)this + 144);
    v7 = (struct _TP_TIMER *)*((_QWORD *)this + 17);
    if ( v7 )
    {
      SetThreadpoolTimer(v7, 0, 0, 0);
      v2 = (struct _TP_TIMER *)*((_QWORD *)this + 17);
      *((_QWORD *)this + 17) = 0;
    }
    v8 = *((_QWORD *)this + 14);
    if ( v8 )
    {
      MFCancelWorkItem(v8);
      *((_QWORD *)this + 14) = 0;
    }
    v9 = *((_BYTE *)this + 89);
    v10 = *((_BYTE *)this + 88);
    *((_BYTE *)this + 89) = 0;
    *((_BYTE *)this + 88) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( v2 )
    {
      WaitForThreadpoolTimerCallbacks(v2, 1);
      CloseThreadpoolTimer(v2);
    }
    if ( BindingVector )
    {
      RpcEpUnregister(qword_1800500A0, BindingVector, 0);
      RpcServerUnregisterIfEx(qword_1800500A0, 0, 1);
      wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(
        &BindingVector,
        0);
    }
    for ( i = 0; i != 2; ++i )
    {
      v12 = v21[2 * i];
      if ( v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v21[2 * i]);
      }
    }
    for ( j = 0; j < 2; ++j )
    {
      v14 = (HANDLE *)&v21[2 * (unsigned int)j + 1];
      if ( *v14 )
      {
        v15 = WaitForSingleObject(*v14, 0x1388u);
        if ( v15 && v15 != 128 && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        {
          if ( v16 == 258 )
          {
            WPP_SF_qDD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              147,
              &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
              this,
              -2147024638,
              j);
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            WPP_SF_qDD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              148,
              &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
              this,
              LastError,
              j);
          }
        }
        __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___T_Z(v14);
      }
    }
    if ( v9 )
      MFUnregisterPlatformFromMMCSS();
    if ( v10 )
    {
      v18 = 0;
      do
      {
        LODWORD(Periodicity) = 0;
        MFShutdown();
        if ( MFGetTimerPeriodicity((DWORD *)&Periodicity) == -1072873851 )
          break;
        v19 = v18++;
      }
      while ( v19 < 0x64 );
    }
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 149, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, 0);
  wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(&BindingVector);
  `vector destructor iterator'(v21, 0x10u, 2u, (void (*)(void *))FSMWatcherEntry::~FSMWatcherEntry);
  return 0;
}

```

## disassembly

```asm
0x18000950c  mov     [rsp-28h+arg_10], rbx
0x180009511  mov     [rsp-28h+arg_18], rsi
0x180009516  push    rbp
0x180009517  push    rdi
0x180009518  push    r12
0x18000951a  push    r14
0x18000951c  push    r15
0x18000951e  mov     rbp, rsp
0x180009521  sub     rsp, 50h
0x180009525  mov     edx, 10h; unsigned __int64
0x18000952a  lea     r9, ??0FSMWatcherEntry@@QEAA@XZ; void *(*)(void *)
0x180009531  mov     rsi, rcx
0x180009534  lea     rcx, [rbp+var_20]; void *
0x180009538  lea     r8d, [rdx-0Eh]; unsigned __int64
0x18000953c  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180009541  mov     [rbp+BindingVector], 0
0x180009549  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000954e  cmp     al, 8
0x180009550  jb      short loc_180009574
0x180009552  mov     rcx, cs:WPP_GLOBAL_Control
0x180009559  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180009560  mov     edx, 92h
0x180009565  mov     r9, rsi
0x180009568  mov     rcx, [rcx+0D8h]
0x18000956f  call    WPP_SF_q
0x180009574  lea     rbx, [rsi+30h]
0x180009578  mov     rcx, rbx; lpCriticalSection
0x18000957b  call    cs:__imp_EnterCriticalSection
0x180009581  cmp     dword ptr [rsi+5Ch], 3
0x180009585  jnz     short loc_180009595
0x180009587  mov     rcx, rbx; lpCriticalSection
0x18000958a  call    cs:__imp_LeaveCriticalSection
0x180009590  jmp     loc_1800097E4
0x180009595  xor     r14d, r14d
0x180009598  mov     dword ptr [rsi+5Ch], 3
0x18000959f  xor     r12d, r12d
0x1800095a2  xor     r15d, r15d
0x1800095a5  mov     rcx, [rbp+r15+var_20]
0x1800095aa  lea     rdi, [r15+rsi]
0x1800095ae  mov     rax, [rsi+r15+0A8h]
0x1800095b6  lea     rdx, [rdi+0B0h]
0x1800095bd  mov     [rsi+r15+0A8h], rcx
0x1800095c5  lea     rcx, [rbp+var_18]
0x1800095c9  mov     [rbp+r15+var_20], rax
0x1800095ce  add     rcx, r15
0x1800095d1  mov     rax, [rcx]
0x1800095d4  mov     [rbp+Periodicity], rax
0x1800095d8  mov     [rbp+r15+var_18], r14
0x1800095dd  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800095e2  lea     rdx, [rbp+Periodicity]
0x1800095e6  lea     rcx, [rdi+0B0h]
0x1800095ed  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800095f2  lea     rcx, [rbp+Periodicity]
0x1800095f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800095fb  inc     r12
0x1800095fe  add     r15, 10h
0x180009602  cmp     r12, 2
0x180009606  jnz     short loc_1800095A5
0x180009608  lea     rdx, [rsi+60h]
0x18000960c  lea     rcx, [rbp+BindingVector]
0x180009610  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>> &)
0x180009615  lea     rcx, [rsi+90h]
0x18000961c  call    ?RemoveAll@?$CTUnkArray@UIFSMemory@@@@QEAAXXZ; CTUnkArray<IFSMemory>::RemoveAll(void)
0x180009621  mov     rcx, [rsi+88h]; pti
0x180009628  test    rcx, rcx
0x18000962b  jz      short loc_18000964D
0x18000962d  xor     r9d, r9d; msWindowLength
0x180009630  xor     r8d, r8d; msPeriod
0x180009633  xor     edx, edx; pftDueTime
0x180009635  call    cs:__imp_SetThreadpoolTimer
0x18000963b  mov     r14, [rsi+88h]
0x180009642  mov     qword ptr [rsi+88h], 0
0x18000964d  mov     rcx, [rsi+70h]; Key
0x180009651  test    rcx, rcx
0x180009654  jz      short loc_180009664
0x180009656  call    cs:__imp_MFCancelWorkItem
0x18000965c  mov     qword ptr [rsi+70h], 0
0x180009664  mov     r15b, [rsi+59h]
0x180009668  mov     rcx, rbx; lpCriticalSection
0x18000966b  mov     r12b, [rsi+58h]
0x18000966f  mov     byte ptr [rsi+59h], 0
0x180009673  mov     byte ptr [rsi+58h], 0
0x180009677  call    cs:__imp_LeaveCriticalSection
0x18000967d  test    r14, r14
0x180009680  jz      short loc_180009699
0x180009682  mov     edx, 1; fCancelPendingCallbacks
0x180009687  mov     rcx, r14; pti
0x18000968a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009690  mov     rcx, r14; pti
0x180009693  call    cs:__imp_CloseThreadpoolTimer
0x180009699  mov     rdx, [rbp+BindingVector]; BindingVector
0x18000969d  test    rdx, rdx
0x1800096a0  jz      short loc_1800096D0
0x1800096a2  xor     r8d, r8d; UuidVector
0x1800096a5  lea     rcx, qword_1800500A0; IfSpec
0x1800096ac  call    cs:__imp_RpcEpUnregister
0x1800096b2  xor     edx, edx; MgrTypeUuid
0x1800096b4  lea     rcx, qword_1800500A0; IfSpec
0x1800096bb  lea     r8d, [rdx+1]; RundownContextHandles
0x1800096bf  call    cs:__imp_RpcServerUnregisterIfEx
0x1800096c5  xor     edx, edx
0x1800096c7  lea     rcx, [rbp+BindingVector]
0x1800096cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RPC_BINDING_VECTOR@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::reset(_RPC_BINDING_VECTOR *)
0x1800096d0  xor     ebx, ebx
0x1800096d2  mov     rax, rbx
0x1800096d5  lea     rdi, [rbp+var_20]
0x1800096d9  shl     rax, 4
0x1800096dd  add     rdi, rax
0x1800096e0  mov     rcx, [rdi]
0x1800096e3  test    rcx, rcx
0x1800096e6  jz      short loc_1800096FC
0x1800096e8  mov     rax, [rcx]
0x1800096eb  mov     rax, [rax+30h]
0x1800096ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096f4  mov     rcx, rdi
0x1800096f7  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x1800096fc  inc     rbx
0x1800096ff  cmp     rbx, 2
0x180009703  jnz     short loc_1800096D2
0x180009705  xor     ebx, ebx
0x180009707  mov     eax, ebx
0x180009709  lea     rdi, [rbp+var_18]
0x18000970d  shl     rax, 4
0x180009711  add     rdi, rax
0x180009714  mov     rcx, [rdi]; hHandle
0x180009717  test    rcx, rcx
0x18000971a  jz      loc_1800097A0
0x180009720  mov     edx, 1388h; dwMilliseconds
0x180009725  call    cs:__imp_WaitForSingleObject
0x18000972b  mov     ecx, eax
0x18000972d  test    eax, eax
0x18000972f  jz      short loc_180009798
0x180009731  cmp     eax, 80h
0x180009736  jz      short loc_180009798
0x180009738  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000973d  cmp     al, 1
0x18000973f  jb      short loc_180009798
0x180009741  cmp     ecx, 102h
0x180009747  jz      short loc_18000976A
0x180009749  call    cs:__imp_GetLastError
0x18000974f  test    eax, eax
0x180009751  jle     short loc_18000975B
0x180009753  movzx   eax, ax
0x180009756  or      eax, 80070000h
0x18000975b  mov     [rsp+50h+var_28], ebx
0x18000975f  mov     edx, 94h
0x180009764  mov     [rsp+50h+var_30], eax
0x180009768  jmp     short loc_18000977B
0x18000976a  mov     [rsp+50h+var_28], ebx
0x18000976e  mov     edx, 93h
0x180009773  mov     [rsp+50h+var_30], 80070102h
0x18000977b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009782  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180009789  mov     r9, rsi
0x18000978c  mov     rcx, [rcx+0D8h]
0x180009793  call    WPP_SF_qDD
0x180009798  mov     rcx, rdi
0x18000979b  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$T@Z
0x1800097a0  inc     ebx
0x1800097a2  cmp     ebx, 2
0x1800097a5  jl      loc_180009707
0x1800097ab  test    r15b, r15b
0x1800097ae  jz      short loc_1800097B6
0x1800097b0  call    cs:__imp_MFUnregisterPlatformFromMMCSS
0x1800097b6  test    r12b, r12b
0x1800097b9  jz      short loc_1800097E4
0x1800097bb  xor     ebx, ebx
0x1800097bd  mov     dword ptr [rbp+Periodicity], 0
0x1800097c4  call    cs:__imp_MFShutdown
0x1800097ca  lea     rcx, [rbp+Periodicity]; Periodicity
0x1800097ce  call    cs:__imp_MFGetTimerPeriodicity
0x1800097d4  cmp     eax, 0C00D3E85h
0x1800097d9  jz      short loc_1800097E4
0x1800097db  mov     eax, ebx
0x1800097dd  inc     ebx
0x1800097df  cmp     eax, 64h ; 'd'
0x1800097e2  jb      short loc_1800097BD
0x1800097e4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800097e9  cmp     al, 8
0x1800097eb  jb      short loc_180009817
0x1800097ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097f4  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800097fb  mov     edx, 95h
0x180009800  mov     [rsp+50h+var_30], 0
0x180009808  mov     r9, rsi
0x18000980b  mov     rcx, [rcx+0D8h]
0x180009812  call    WPP_SF_qD
0x180009817  lea     rcx, [rbp+BindingVector]
0x18000981b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(void)
0x180009820  mov     edx, 10h; unsigned __int64
0x180009825  lea     r9, ??1FSMWatcherEntry@@QEAA@XZ; void (*)(void *)
0x18000982c  lea     rcx, [rbp+var_20]; void *
0x180009830  lea     r8d, [rdx-0Eh]; unsigned __int64
0x180009834  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180009839  lea     r11, [rsp+50h+var_s0]
0x18000983e  xor     eax, eax
0x180009840  mov     rbx, [r11+40h]
0x180009844  mov     rsi, [r11+48h]
0x180009848  mov     rsp, r11
0x18000984b  pop     r15
0x18000984d  pop     r14
0x18000984f  pop     r12
0x180009851  pop     rdi
0x180009852  pop     rbp
0x180009853  retn
```
