# CLocationAcquireEmulatedTrackingCpe::Initialize(void)

- ea: `0x1800891e0`
- end: `0x1800894c6`
- name: `?Initialize@CLocationAcquireEmulatedTrackingCpe@@EEAAJXZ`
- size: `742`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c974`
- `0x180012398`
- `0x18001be08`
- `0x180021450`
- `0x1800229bc`
- `0x1800234ec`
- `0x18002435c`
- `0x180024440`
- `0x180027594`
- `0x1800277ec`
- `0x180028434`
- `0x18003b92c`
- `0x180048a04`
- `0x180067a60`
- `0x180087f08`
- `0x1800891e0`
- `0x1800894cc`
- `0x1800a98c0`
- `0x18010dc94`
- `0x18010df10`
- `0x18010e004`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089294`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800892f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089294`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800892f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800892ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800892ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089307`

## string_xrefs

- `0x180089410`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationacquireemulatedtrackingcpe.cpp`
- `0x1800893fd`: `LocationSignalManagerHelper::CreateCoalescedFunction(realFn, 1000, m_coalescedSignalFnCookie, registerFn)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
signed int __fastcall CLocationAcquireEmulatedTrackingCpe::Initialize(_DWORD *pv)
{
  __int64 v2; // rcx
  int Location; // esi
  HANDLE EventW; // rax
  __int64 v5; // rcx
  signed int LastError; // eax
  HANDLE v7; // rax
  signed int result; // eax
  std::_Ref_count_base *v9; // rbx
  __int64 v10; // rax
  int CoalescedFunction; // eax
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  char *v15; // [rsp+28h] [rbp-D8h]
  int v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[64]; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v20[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v21[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v22; // [rsp+B0h] [rbp-50h]
  int v23; // [rsp+B4h] [rbp-4Ch]
  _DWORD *v24; // [rsp+B8h] [rbp-48h]
  _QWORD *v25; // [rsp+D8h] [rbp-28h]
  _BYTE v26[56]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v27; // [rsp+118h] [rbp+18h]
  wil::details::in1diag5 *retaddr; // [rsp+148h] [rbp+48h]

  pv[78] = CLocationAcquireEmulatedTrackingCpe::Initialize_::_3_::_lambda_1_::operator()();
  *(_QWORD *)v16 = 0;
  if ( (int)CLocationComponentHelper::AutoCreateLocationComponentImpl<ILocationPalMisc>(v2, v16) >= 0 )
  {
    v19 = 256;
    if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)v16 + 64LL))(*(_QWORD *)v16, &v19) >= 0
      && ((v19 - 2) & 0xFFFFFFFD) == 0 )
    {
      pv[78] = CLocationAcquireEmulatedTrackingCpe::Initialize_::_9_::_lambda_2_::operator()();
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
  Location = CLocationAcquireBase::Initialize(pv);
  if ( Location < 0 )
    return Location;
  EventW = CreateEventW(0, 0, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    pv + 82,
    EventW);
  if ( !*((_QWORD *)pv + 41) )
  {
    LastError = GetLastError();
    Location = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return Location;
  }
  Location = LocationHelper::CreateLocationComponent<ILocationMovementDetector>(v5, pv + 80);
  if ( Location < 0 )
    return Location;
  v7 = CreateEventW(0, 0, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    pv + 92,
    v7);
  if ( *((_QWORD *)pv + 46) )
  {
    *(_OWORD *)v17 = 0;
    *(_QWORD *)v16 = 0;
    wil::EnterCriticalSection(v16, &stru_1801E4420);
    if ( !dword_1801E4448 )
      CLocationObjectManager::Start();
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v16);
    CLocationObjectManager::GetSignalMan(&CLocationObjectManager::s_instance, v17);
    *(_OWORD *)v20 = 0;
    std::weak_ptr<ILocationUIHandler>::lock(v17, v20);
    v9 = v20[0];
    if ( v20[0] )
    {
      v21[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CLocationAcquireEmulatedTrackingCpe::*)(void),CLocationAcquireEmulatedTrackingCpe *>,void,>::`vftable';
      v21[1] = CLocationAcquireEmulatedTrackingCpe::OnInterestingSignals;
      v22 = 0;
      v23 = HIDWORD(v17[1]);
      v24 = pv;
      v25 = v21;
      v27 = 0;
      v10 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
              v18,
              v21);
      CoalescedFunction = LocationSignalManagerHelper::CreateCoalescedFunction(v10, 1000, pv + 84, v26);
      if ( CoalescedFunction >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v9 + 144LL))(v9);
        v13 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v9 + 104LL))(v9);
        v14 = std::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>::function<void (_BROKERED_EVENT *,_GUID const *,unsigned long,unsigned char *)>(
                v18,
                v26);
        LocationSignalManagerHelper::RegisterForMultipleSignals<SignalValue<bool>,SignalValue<bool>>(
          v14,
          pv + 88,
          v13,
          v12);
      }
      else
      {
        LODWORD(v15) = CoalescedFunction;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x150,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationacquireemulatedtrackingcpe.cpp",
          "CLocationAcquireEmulatedTrackingCpe::Initialize",
          "LocationSignalManagerHelper::CreateCoalescedFunction(realFn, 1000, m_coalescedSignalFnCookie, registerFn)",
          v15,
          v16[0]);
      }
      std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v26);
      std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v21);
    }
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
    if ( v17[1] )
      std::_Ref_count_base::_Decwref(v17[1]);
    return Location;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800891e0  mov     [rsp-8+arg_8], rbx
0x1800891e5  mov     [rsp-8+arg_10], rsi
0x1800891ea  push    rbp
0x1800891eb  push    rdi
0x1800891ec  push    r14
0x1800891ee  lea     rbp, [rsp-30h]
0x1800891f3  sub     rsp, 130h
0x1800891fa  mov     rax, cs:__security_cookie
0x180089201  xor     rax, rsp
0x180089204  mov     [rbp+40h+var_20], rax
0x180089208  mov     r14, rcx
0x18008920b  call    _CLocationAcquireEmulatedTrackingCpe__Initialize____3____lambda_1___operator__
0x180089210  mov     [r14+138h], eax
0x180089217  mov     qword ptr [rsp+140h+var_110], 0
0x180089220  lea     rdx, [rsp+140h+var_110]
0x180089225  call    ??$AutoCreateLocationComponentImpl@UILocationPalMisc@@@CLocationComponentHelper@@CAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAPEAUILocationPalMisc@@@Z; CLocationComponentHelper::AutoCreateLocationComponentImpl<ILocationPalMisc>(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ILocationPalMisc * *)
0x18008922a  test    eax, eax
0x18008922c  js      short loc_180089267
0x18008922e  mov     [rbp+40h+var_B8], 100h
0x180089235  mov     rcx, qword ptr [rsp+140h+var_110]
0x18008923a  mov     rax, [rcx]
0x18008923d  lea     rdx, [rbp+40h+var_B8]
0x180089241  mov     rax, [rax+40h]
0x180089245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008924a  test    eax, eax
0x18008924c  js      short loc_180089267
0x18008924e  mov     eax, [rbp+40h+var_B8]
0x180089251  add     eax, 0FFFFFFFEh
0x180089254  test    eax, 0FFFFFFFDh
0x180089259  jnz     short loc_180089267
0x18008925b  call    _CLocationAcquireEmulatedTrackingCpe__Initialize____9____lambda_2___operator__
0x180089260  mov     [r14+138h], eax
0x180089267  lea     rcx, [rsp+140h+var_110]
0x18008926c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180089271  mov     rcx, r14; pv
0x180089274  call    ?Initialize@CLocationAcquireBase@@UEAAJXZ; CLocationAcquireBase::Initialize(void)
0x180089279  mov     esi, eax
0x18008927b  test    eax, eax
0x18008927d  js      loc_1800894A0
0x180089283  lea     rbx, [r14+148h]
0x18008928a  xor     r9d, r9d; lpName
0x18008928d  xor     r8d, r8d; bInitialState
0x180089290  xor     edx, edx; bManualReset
0x180089292  xor     ecx, ecx; lpEventAttributes
0x180089294  call    cs:__imp_CreateEventW
0x18008929a  mov     rdx, rax
0x18008929d  mov     rcx, rbx
0x1800892a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800892a5  cmp     qword ptr [rbx], 0
0x1800892a9  jnz     short loc_1800892C9
0x1800892ab  call    cs:__imp_GetLastError
0x1800892b1  mov     esi, eax
0x1800892b3  test    eax, eax
0x1800892b5  jle     loc_1800894A0
0x1800892bb  movzx   esi, ax
0x1800892be  or      esi, 80070000h
0x1800892c4  jmp     loc_1800894A0
0x1800892c9  lea     rdx, [r14+140h]
0x1800892d0  call    ??$CreateLocationComponent@UILocationMovementDetector@@@LocationHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAPEAUILocationMovementDetector@@@Z; LocationHelper::CreateLocationComponent<ILocationMovementDetector>(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ILocationMovementDetector * *)
0x1800892d5  mov     esi, eax
0x1800892d7  test    eax, eax
0x1800892d9  js      loc_1800894A0
0x1800892df  lea     rbx, [r14+170h]
0x1800892e6  xor     r9d, r9d; lpName
0x1800892e9  xor     r8d, r8d; bInitialState
0x1800892ec  xor     edx, edx; bManualReset
0x1800892ee  xor     ecx, ecx; lpEventAttributes
0x1800892f0  call    cs:__imp_CreateEventW
0x1800892f6  mov     rdx, rax
0x1800892f9  mov     rcx, rbx
0x1800892fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180089301  cmp     qword ptr [rbx], 0
0x180089305  jnz     short loc_180089322
0x180089307  call    cs:__imp_GetLastError
0x18008930d  test    eax, eax
0x18008930f  jle     loc_1800894A2
0x180089315  movzx   eax, ax
0x180089318  or      eax, 80070000h
0x18008931d  jmp     loc_1800894A2
0x180089322  xorps   xmm0, xmm0
0x180089325  movups  xmmword ptr [rsp+140h+var_108], xmm0
0x18008932a  mov     qword ptr [rsp+140h+var_110], 0; int
0x180089333  lea     rdx, stru_1801E4420
0x18008933a  lea     rcx, [rsp+140h+var_110]
0x18008933f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180089344  nop
0x180089345  cmp     cs:dword_1801E4448, 0
0x18008934c  jnz     short loc_180089354
0x18008934e  call    ?Start@CLocationObjectManager@@KAJXZ; CLocationObjectManager::Start(void)
0x180089353  nop
0x180089354  lea     rcx, [rsp+140h+var_110]
0x180089359  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18008935e  lea     rdx, [rsp+140h+var_108]
0x180089363  lea     rcx, ?s_instance@CLocationObjectManager@@1V1@A; CLocationObjectManager CLocationObjectManager::s_instance
0x18008936a  call    ?GetSignalMan@CLocationObjectManager@@QEBA?AV?$weak_ptr@VILocationSignalManager@@@std@@XZ; CLocationObjectManager::GetSignalMan(void)
0x18008936f  nop
0x180089370  xorps   xmm0, xmm0
0x180089373  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x180089377  lea     rdx, [rbp+40h+var_B0]
0x18008937b  lea     rcx, [rsp+140h+var_108]
0x180089380  call    ?lock@?$weak_ptr@VILocationUIHandler@@@std@@QEBA?AV?$shared_ptr@VILocationUIHandler@@@2@XZ; std::weak_ptr<ILocationUIHandler>::lock(void)
0x180089385  nop
0x180089386  mov     rbx, [rbp+40h+var_B0]
0x18008938a  test    rbx, rbx
0x18008938d  jz      loc_180089482
0x180089393  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8CLocationAcquireEmulatedTrackingCpe@@EAAXXZPEAV3@@std@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CLocationAcquireEmulatedTrackingCpe::*)(void),CLocationAcquireEmulatedTrackingCpe *>,void,>::`vftable'
0x18008939a  mov     [rbp+40h+var_A0], rax
0x18008939e  lea     rax, ?OnInterestingSignals@CLocationAcquireEmulatedTrackingCpe@@AEAAXXZ; CLocationAcquireEmulatedTrackingCpe::OnInterestingSignals(void)
0x1800893a5  mov     [rbp+40h+var_98], rax
0x1800893a9  mov     [rbp+40h+var_90], 0
0x1800893b0  mov     eax, dword ptr [rsp+140h+var_108+0Ch]
0x1800893b4  mov     [rbp+40h+var_8C], eax
0x1800893b7  mov     [rbp+40h+var_88], r14
0x1800893bb  lea     rax, [rbp+40h+var_A0]
0x1800893bf  mov     [rbp+40h+var_68], rax
0x1800893c3  mov     [rbp+40h+var_28], 0
0x1800893cb  lea     rdx, [rbp+40h+var_A0]
0x1800893cf  lea     rcx, [rsp+140h+var_F8]
0x1800893d4  call    ??0?$function@$$A6AXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z@std@@QEAA@AEBV01@@Z; std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>(std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)> const &)
0x1800893d9  lea     r8, [r14+150h]
0x1800893e0  lea     r9, [rbp+40h+var_60]
0x1800893e4  mov     edx, 3E8h
0x1800893e9  mov     rcx, rax
0x1800893ec  call    ?CreateCoalescedFunction@LocationSignalManagerHelper@@SAJV?$function@$$A6AXXZ@std@@_KAEAV?$shared_ptr@VLocationCallOnExit@@@3@AEAV23@@Z; LocationSignalManagerHelper::CreateCoalescedFunction(std::function<void (void)>,unsigned __int64,std::shared_ptr<LocationCallOnExit> &,std::function<void (void)> &)
0x1800893f1  mov     rcx, [rbp+48h]; this
0x1800893f5  test    eax, eax
0x1800893f7  jns     short loc_180089423
0x1800893f9  mov     dword ptr [rsp+140h+var_118], eax; char *
0x1800893fd  lea     rax, aLocationsignal; "LocationSignalManagerHelper::CreateCoal"...
0x180089404  mov     [rsp+140h+var_120], rax; char *
0x180089409  lea     r9, aClocationacqui_8; "CLocationAcquireEmulatedTrackingCpe::In"...
0x180089410  lea     r8, aOnecoreuapDriv_73; "onecoreuap\\drivers\\mobilepc\\location"...
0x180089417  mov     edx, 150h; void *
0x18008941c  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180089421  jmp     short loc_18008946E
0x180089423  mov     rax, [rbx]
0x180089426  mov     rcx, rbx
0x180089429  mov     rax, [rax+90h]
0x180089430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089435  mov     rdi, rax
0x180089438  mov     rdx, [rbx]
0x18008943b  mov     rcx, rbx
0x18008943e  mov     rax, [rdx+68h]
0x180089442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089447  mov     rbx, rax
0x18008944a  lea     rdx, [rbp+40h+var_60]
0x18008944e  lea     rcx, [rsp+140h+var_F8]
0x180089453  call    ??0?$function@$$A6AXPEAU_BROKERED_EVENT@@PEBU_GUID@@KPEAE@Z@std@@QEAA@AEBV01@@Z; std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)>(std::function<void (_BROKERED_EVENT *,_GUID const *,ulong,uchar *)> const &)
0x180089458  lea     rdx, [r14+160h]
0x18008945f  mov     r9, rdi
0x180089462  mov     r8, rbx
0x180089465  mov     rcx, rax
0x180089468  call    ??$RegisterForMultipleSignals@V?$SignalValue@_N@@V1@@LocationSignalManagerHelper@@SAXV?$function@$$A6AXXZ@std@@AEAV?$list@V?$shared_ptr@VLocationCallOnExit@@@std@@V?$allocator@V?$shared_ptr@VLocationCallOnExit@@@std@@@2@@2@AEAV?$SignalValue@_N@@2@Z; LocationSignalManagerHelper::RegisterForMultipleSignals<SignalValue<bool>,SignalValue<bool>>(std::function<void (void)>,std::list<std::shared_ptr<LocationCallOnExit>> &,SignalValue<bool> &,SignalValue<bool> &)
0x18008946d  nop
0x18008946e  lea     rcx, [rbp+40h+var_60]
0x180089472  call    ?_Tidy@?$_Func_class@XW4ActivityType@CLocationActivityDetector@@_N@std@@IEAAXXZ; std::_Func_class<void,CLocationActivityDetector::ActivityType,bool>::_Tidy(void)
0x180089477  nop
0x180089478  lea     rcx, [rbp+40h+var_A0]
0x18008947c  call    ?_Tidy@?$_Func_class@XW4ActivityType@CLocationActivityDetector@@_N@std@@IEAAXXZ; std::_Func_class<void,CLocationActivityDetector::ActivityType,bool>::_Tidy(void)
0x180089481  nop
0x180089482  mov     rcx, [rbp+40h+var_B0+8]; this
0x180089486  test    rcx, rcx
0x180089489  jz      short loc_180089491
0x18008948b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180089490  nop
0x180089491  mov     rcx, [rsp+140h+var_108+8]; this
0x180089496  test    rcx, rcx
0x180089499  jz      short loc_1800894A0
0x18008949b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800894a0  mov     eax, esi
0x1800894a2  mov     rcx, [rbp+40h+var_20]
0x1800894a6  xor     rcx, rsp; StackCookie
0x1800894a9  call    __security_check_cookie
0x1800894ae  lea     r11, [rsp+140h+var_10]
0x1800894b6  mov     rbx, [r11+28h]
0x1800894ba  mov     rsi, [r11+30h]
0x1800894be  mov     rsp, r11
0x1800894c1  pop     r14
0x1800894c3  pop     rdi
0x1800894c4  pop     rbp
0x1800894c5  retn
```
