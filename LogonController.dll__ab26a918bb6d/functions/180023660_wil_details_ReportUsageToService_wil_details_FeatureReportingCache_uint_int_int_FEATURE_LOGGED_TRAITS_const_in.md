# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180023660`
- end: `0x180023b7c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `1308`
- prototype: `void __high(struct wil_details_FeatureReportingCache *, unsigned int, int, int, const struct FEATURE_LOGGED_TRAITS *, int, enum wil_ReportingKind, unsigned __int64)`
- caller_count: `35`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024ac0`
- `0x1800250a0`
- `0x18002547c`
- `0x180061d3c`
- `0x180062aa4`
- `0x180062b30`
- `0x180063cc8`
- `0x180076ea4`
- `0x18007709c`
- `0x180078f5c`
- `0x180078fe8`
- `0x180079070`
- `0x1800790f4`
- `0x180079178`
- `0x1800791fc`
- `0x180079280`
- `0x180079304`
- `0x180079388`
- `0x180079410`
- `0x180079498`
- `0x180079520`
- `0x1800795a8`
- `0x180079630`
- `0x1800796b8`
- `0x1800859b8`
- `0x180085ae4`
- `0x180085b70`
- `0x1800875ac`
- `0x180089f14`
- `0x180089fa0`
- `0x18008a02c`
- `0x18008d9ac`
- `0x180097834`
- `0x180099290`
- `0x18009a774`

## callees

- `0x18000b290`
- `0x18000ba60`
- `0x18000bac8`
- `0x18000bd70`
- `0x180023660`
- `0x180023b84`
- `0x180043c64`
- `0x18007c7bc`
- `0x18009d010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180023806`
- `KERNEL32!CreateThreadpoolTimer` at `0x180023806`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180023843`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800238f2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180023843`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800238f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800238a6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180023acd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800238a6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180023acd`
- `KERNEL32!SetLastError` at `0x18002381d`
- `KERNEL32!SetLastError` at `0x18002381d`
- `KERNEL32!GetLastError` at `0x1800237ed`
- `KERNEL32!GetLastError` at `0x1800237ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::ReportUsageToService(
        volatile signed __int32 *i,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        unsigned __int8 a8)
{
  volatile signed __int32 *v10; // rdi
  unsigned int v11; // r9d
  unsigned int v12; // ebx
  BOOL v13; // esi
  DWORD LastError; // edi
  PTP_TIMER ThreadpoolTimer; // rax
  signed __int32 v16; // r8d
  unsigned __int32 v17; // eax
  unsigned __int32 v18; // eax
  unsigned __int32 v19; // ett
  void (__fastcall *v20)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  int v21; // ebx
  int v22; // edx
  unsigned int v23; // r8d
  wil *v24; // rcx
  unsigned int v25; // edx
  const char *v26; // [rsp+20h] [rbp-88h]
  _DWORD v27[2]; // [rsp+50h] [rbp-58h] BYREF
  volatile signed __int32 *v28; // [rsp+58h] [rbp-50h]
  unsigned int v29[4]; // [rsp+60h] [rbp-48h] BYREF
  _BOOL8 v30; // [rsp+70h] [rbp-38h]

  v10 = i;
  if ( !a7 )
    return;
  v11 = 4;
  if ( a7 == 3 )
  {
    v12 = 6;
    if ( a6 )
      v12 = 2;
  }
  else
  {
    switch ( a7 )
    {
      case 0:
        goto LABEL_45;
      case 1:
        v12 = 0;
        if ( !a6 )
          v12 = 4;
        break;
      case 2:
        v12 = 1;
        if ( !a6 )
          v12 = 5;
        break;
      case 4:
        v12 = 3;
        if ( !a6 )
          v12 = 7;
        break;
      case 5:
        v12 = 8;
        if ( !a6 )
          v12 = 10;
        break;
      case 6:
        v12 = 9;
        if ( !a6 )
          v12 = 11;
        break;
      default:
        if ( (unsigned __int8)(a7 - 100) > 0x31u )
        {
LABEL_45:
          v12 = 255;
        }
        else
        {
          v21 = 100;
          if ( !a6 )
            v21 = 150;
          v12 = (unsigned __int8)(a7 - 100) + v21;
        }
        break;
    }
  }
  a8 = *(_BYTE *)(a5 + 4);
  *(_OWORD *)v29 = 0;
  v30 = 0;
  if ( v12 == 4 )
  {
LABEL_6:
    wil_details_FeatureReporting_IncrementUsageInCache(i, v12, 2, v29);
LABEL_7:
    v13 = v30;
    goto LABEL_8;
  }
  switch ( v12 )
  {
    case 0u:
      goto LABEL_6;
    case 1u:
    case 5u:
      wil_details_FeatureReporting_IncrementOpportunityInCache(i, v12, 2, v29);
      goto LABEL_7;
    case 2u:
    case 3u:
    case 6u:
    case 7u:
      v22 = 0;
      switch ( v12 )
      {
        case 2u:
          v22 = 2;
          break;
        case 3u:
          v22 = 8;
          break;
        case 6u:
          v22 = 4;
          break;
        case 7u:
          v22 = 16;
          break;
      }
      for ( i = (volatile signed __int32 *)*(unsigned int *)i; ; i = (volatile signed __int32 *)v17 )
      {
        v13 = ((unsigned int)i | v22) == (_DWORD)i;
        v16 = (unsigned int)i | v22 | 1;
        if ( ((unsigned int)i | v22) == (_DWORD)i )
          v16 = (unsigned int)i | v22;
        v17 = _InterlockedCompareExchange(v10, v16, (signed __int32)i);
        if ( (_DWORD)i == v17 )
          break;
      }
      v29[0] = (v16 & 1) != 0 && ((unsigned __int8)i & 1) == 0;
      goto LABEL_8;
    default:
      v23 = v12 - 320;
      if ( (int)(v12 - 320) >= 64 )
      {
        v13 = v30;
LABEL_81:
        v29[2] = v12;
        v29[1] = 1;
        goto LABEL_8;
      }
      v18 = *((_DWORD *)i + 1);
      do
      {
        v13 = (v18 & 0x10) != 0 && ((v18 >> 5) & 0x3F) == v23;
        i = (volatile signed __int32 *)(v18 ^ ((unsigned __int16)v18 ^ (unsigned __int16)(32 * v23)) & 0x7E0 | 0x10);
        v19 = v18;
        v18 = _InterlockedCompareExchange(v10 + 1, (signed __int32)i, v18);
      }
      while ( v19 != v18 );
      if ( !v13 )
        goto LABEL_81;
LABEL_8:
      if ( g_wil_details_RecordSRUMFeatureUsage )
      {
        i = (volatile signed __int32 *)(v12 - 100);
        if ( (unsigned int)i <= 0x31 || !v12 )
          g_wil_details_RecordSRUMFeatureUsage(a2, v12, 1);
      }
      if ( v29[0] && wil::details::g_enabledStateManager && !wil::ProcessShutdownInProgress((wil *)i) )
      {
        AcquireSRWLockExclusive(&SRWLock);
        if ( wil::details::g_enabledStateManager )
        {
          if ( !wil::ProcessShutdownInProgress(v24) )
          {
            v27[0] = a2;
            v27[1] = 0;
            v28 = v10;
            wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800D35D8, v27, 0x10u);
            if ( !byte_1800D35D0 )
            {
              if ( !qword_1800D35C8 )
              {
                LastError = GetLastError();
                ThreadpoolTimer = CreateThreadpoolTimer(
                                    _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                    &wil::details::g_enabledStateManager,
                                    0);
                wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                  &qword_1800D35C8,
                  ThreadpoolTimer);
                SetLastError(LastError);
              }
              wil::details::EnsureCoalescedTimer_SetTimer(&qword_1800D35C8, &byte_1800D35D0, 300000);
            }
          }
        }
        ReleaseSRWLockExclusive(&SRWLock);
      }
      if ( v29[1] )
        wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v29[2], v29[1], v11, v26);
      if ( !v13 && wil::details::g_enabledStateManager )
      {
        AcquireSRWLockExclusive(&SRWLock);
        if ( !qword_1800D3620 )
        {
          qword_1800D3620 = 0;
          v20 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
          if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
            || (v20 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
          {
            v20(&qword_1800D3620, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
          }
        }
        ReleaseSRWLockExclusive(&SRWLock);
      }
      if ( a3 )
      {
        v25 = v12 | 0x80000000;
        if ( !a4 )
          v25 = v12;
        wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v25, 0, v11, v26);
      }
      if ( !v13 )
      {
        if ( g_wil_details_realtimeFeatureUsageHook )
          g_wil_details_realtimeFeatureUsageHook(a2, v12, a8);
        if ( g_wil_details_pfnFeatureLoggingHook )
          g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, 0, 1);
      }
      return;
  }
}

```

## disassembly

```asm
0x180023660  mov     rax, rsp
0x180023663  mov     [rax+8], rbx
0x180023667  mov     [rax+10h], rsi
0x18002366b  mov     [rax+20h], r9d
0x18002366f  push    rdi
0x180023670  push    r12
0x180023672  push    r13
0x180023674  push    r14
0x180023676  push    r15
0x180023678  sub     rsp, 80h
0x18002367f  mov     r14d, r8d
0x180023682  mov     r12d, edx
0x180023685  mov     rdi, rcx
0x180023688  movsxd  r10, dword ptr [rax+38h]
0x18002368c  test    r10d, r10d
0x18002368f  jz      loc_180023764
0x180023695  mov     r9d, 4
0x18002369b  mov     r8d, 2
0x1800236a1  mov     r15d, [rsp+0A8h+arg_28]
0x1800236a9  lea     rdx, __ImageBase
0x1800236b0  cmp     r10d, 3
0x1800236b4  jnz     loc_180023936
0x1800236ba  mov     ebx, 6
0x1800236bf  test    r15d, r15d
0x1800236c2  cmovnz  ebx, r8d
0x1800236c6  mov     r13, [rsp+0A8h+arg_20]
0x1800236ce  movzx   eax, byte ptr [r13+4]
0x1800236d3  mov     [rsp+0A8h+arg_38], al
0x1800236da  xorps   xmm0, xmm0
0x1800236dd  xor     eax, eax
0x1800236df  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x1800236e4  mov     [rsp+0A8h+var_38], rax
0x1800236e9  cmp     ebx, r9d
0x1800236ec  jnz     loc_1800239DA
0x1800236f2  lea     r9, [rsp+0A8h+var_48]; jumptable 00000001800239EC case 0
0x1800236f7  mov     edx, ebx
0x1800236f9  mov     rcx, rdi
0x1800236fc  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180023701  mov     esi, dword ptr [rsp+0A8h+var_38]
0x180023705  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18002370c  test    rax, rax
0x18002370f  jz      short loc_180023725
0x180023711  lea     ecx, [rbx-64h]; this
0x180023714  cmp     ecx, 31h ; '1'
0x180023717  jbe     loc_180023AA4
0x18002371d  test    ebx, ebx
0x18002371f  jz      loc_180023AA4
0x180023725  cmp     [rsp+0A8h+var_48], 0
0x18002372a  jz      short loc_18002373A
0x18002372c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180023732  test    eax, eax
0x180023734  jnz     loc_180023AB9
0x18002373a  cmp     [rsp+0A8h+var_48+4], 0
0x18002373f  ja      loc_180023AF3
0x180023745  test    esi, esi
0x180023747  jnz     short loc_180023757
0x180023749  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002374f  test    eax, eax
0x180023751  jnz     loc_18002389F
0x180023757  test    r14d, r14d
0x18002375a  jnz     loc_180023B1E
0x180023760  test    esi, esi
0x180023762  jz      short loc_180023781
0x180023764  lea     r11, [rsp+0A8h+var_28]
0x18002376c  mov     rbx, [r11+30h]
0x180023770  mov     rsi, [r11+38h]
0x180023774  mov     rsp, r11
0x180023777  pop     r15
0x180023779  pop     r14
0x18002377b  pop     r13
0x18002377d  pop     r12
0x18002377f  pop     rdi
0x180023780  retn
0x180023781  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180023788  test    rax, rax
0x18002378b  jz      short loc_1800237A0
0x18002378d  movzx   r8d, [rsp+0A8h+arg_38]
0x180023796  mov     edx, ebx
0x180023798  mov     ecx, r12d
0x18002379b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237a0  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800237a7  test    rax, rax
0x1800237aa  jz      short loc_180023764
0x1800237ac  mov     [rsp+0A8h+var_70], 1
0x1800237b5  mov     [rsp+0A8h+var_78], 0
0x1800237ba  mov     [rsp+0A8h+var_80], 0
0x1800237c3  lea     rcx, [rsp+0A8h+arg_30]
0x1800237cb  mov     [rsp+0A8h+var_88], rcx
0x1800237d0  mov     r9d, r15d
0x1800237d3  xor     r8d, r8d
0x1800237d6  mov     rdx, r13
0x1800237d9  mov     ecx, r12d
0x1800237dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237e1  jmp     short loc_180023764
0x1800237e3  cmp     cs:qword_1800D35C8, 0
0x1800237eb  jnz     short loc_180023823
0x1800237ed  call    cs:__imp_GetLastError
0x1800237f3  mov     edi, eax
0x1800237f5  xor     r8d, r8d; pcbe
0x1800237f8  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800237ff  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180023806  call    cs:__imp_CreateThreadpoolTimer
0x18002380c  mov     rdx, rax
0x18002380f  lea     rcx, qword_1800D35C8
0x180023816  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002381b  mov     ecx, edi; dwErrCode
0x18002381d  call    cs:__imp_SetLastError
0x180023823  mov     r8d, 493E0h
0x180023829  lea     rdx, byte_1800D35D0
0x180023830  lea     rcx, qword_1800D35C8
0x180023837  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002383c  lea     rcx, SRWLock; SRWLock
0x180023843  call    cs:__imp_ReleaseSRWLockExclusive
0x180023849  jmp     loc_18002373A
0x18002384e  mov     eax, edx
0x180023850  or      eax, ecx
0x180023852  xor     esi, esi
0x180023854  cmp     eax, ecx
0x180023856  setz    sil
0x18002385a  mov     r8d, eax
0x18002385d  or      r8d, 1
0x180023861  test    esi, esi
0x180023863  cmovnz  r8d, eax
0x180023867  mov     eax, ecx
0x180023869  lock cmpxchg [rdi], r8d
0x18002386e  jz      loc_180023A23
0x180023874  mov     ecx, eax
0x180023876  jmp     short loc_18002384E
0x180023878  mov     ecx, edx
0x18002387a  xor     ecx, eax
0x18002387c  and     ecx, 7E0h
0x180023882  xor     ecx, eax
0x180023884  or      ecx, 10h
0x180023887  lock cmpxchg [rdi+4], ecx
0x18002388c  jnz     loc_180023A6D
0x180023892  test    esi, esi
0x180023894  jz      loc_180023A93
0x18002389a  jmp     loc_180023705
0x18002389f  lea     rcx, SRWLock; SRWLock
0x1800238a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800238ac  cmp     cs:qword_1800D3620, 0
0x1800238b4  jnz     short loc_1800238EB
0x1800238b6  mov     cs:qword_1800D3620, 0
0x1800238c1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800238c8  test    rax, rax
0x1800238cb  jz      loc_180023B09
0x1800238d1  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800238d8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800238df  lea     rcx, qword_1800D3620
0x1800238e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238eb  lea     rcx, SRWLock; SRWLock
0x1800238f2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800238f8  jmp     loc_180023757
0x1800238fd  mov     [rsp+0A8h+var_58], r12d
0x180023902  xor     eax, eax
0x180023904  mov     [rsp+0A8h+var_54], eax
0x180023908  mov     [rsp+0A8h+var_50], rdi
0x18002390d  mov     r8d, 10h; unsigned __int64
0x180023913  lea     rdx, [rsp+0A8h+var_58]; void *
0x180023918  lea     rcx, qword_1800D35D8; this
0x18002391f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180023924  cmp     cs:byte_1800D35D0, 0
0x18002392b  jnz     loc_18002383C
0x180023931  jmp     loc_1800237E3
0x180023936  cmp     r10d, 6; switch 7 cases
0x18002393a  ja      short def_180023947; jumptable 0000000180023947 default case, case 3
0x18002393c  mov     ecx, ds:(jpt_180023947 - 180000000h)[rdx+r10*4]
0x180023944  add     rcx, rdx
0x180023947  jmp     rcx; switch jump
0x180023949  xor     ebx, ebx; jumptable 0000000180023947 case 1
0x18002394b  test    r15d, r15d
0x18002394e  cmovz   ebx, r9d
0x180023952  jmp     loc_1800236C6
0x180023957  mov     ebx, 0FFh; jumptable 0000000180023947 case 0
0x18002395c  jmp     loc_1800236C6
0x180023961  mov     ebx, 1; jumptable 0000000180023947 case 2
0x180023966  mov     eax, 5
0x18002396b  test    r15d, r15d
0x18002396e  cmovz   ebx, eax
0x180023971  jmp     loc_1800236C6
0x180023976  mov     ebx, 3; jumptable 0000000180023947 case 4
0x18002397b  mov     eax, 7
0x180023980  test    r15d, r15d
0x180023983  cmovz   ebx, eax
0x180023986  jmp     loc_1800236C6
0x18002398b  mov     ebx, 8; jumptable 0000000180023947 case 5
0x180023990  mov     eax, 0Ah
0x180023995  test    r15d, r15d
0x180023998  cmovz   ebx, eax
0x18002399b  jmp     loc_1800236C6
0x1800239a0  mov     ebx, 9; jumptable 0000000180023947 case 6
0x1800239a5  mov     eax, 0Bh
0x1800239aa  test    r15d, r15d
0x1800239ad  cmovz   ebx, eax
0x1800239b0  jmp     loc_1800236C6
0x1800239b5  sub     r10b, 64h ; 'd'; jumptable 0000000180023947 default case, case 3
0x1800239b9  cmp     r10b, 31h ; '1'
0x1800239bd  ja      short loc_180023957; jumptable 0000000180023947 case 0
0x1800239bf  mov     ebx, 64h ; 'd'
0x1800239c4  mov     eax, 96h
0x1800239c9  test    r15d, r15d
0x1800239cc  cmovz   ebx, eax
0x1800239cf  movzx   eax, r10b
0x1800239d3  add     ebx, eax
0x1800239d5  jmp     loc_1800236C6
0x1800239da  cmp     ebx, 7; switch 8 cases
0x1800239dd  ja      short def_1800239EC; jumptable 00000001800239EC default case, case 4
0x1800239df  movsxd  rax, ebx
0x1800239e2  mov     ecx, ds:(jpt_1800239EC - 180000000h)[rdx+rax*4]
0x1800239e9  add     rcx, rdx
0x1800239ec  jmp     rcx; switch jump
0x1800239ee  xor     edx, edx; jumptable 00000001800239EC cases 2,3,6,7
0x1800239f0  mov     ecx, ebx
0x1800239f2  sub     ecx, r8d
0x1800239f5  jz      short loc_180023A19
0x1800239f7  sub     ecx, 1
0x1800239fa  jz      short loc_180023A12
0x1800239fc  sub     ecx, 3
0x1800239ff  jz      short loc_180023A0D
0x180023a01  cmp     ecx, 1
0x180023a04  jnz     short loc_180023A1C
0x180023a06  mov     edx, 10h
0x180023a0b  jmp     short loc_180023A1C
0x180023a0d  mov     edx, r9d
0x180023a10  jmp     short loc_180023A1C
0x180023a12  mov     edx, 8
0x180023a17  jmp     short loc_180023A1C
0x180023a19  mov     edx, r8d
0x180023a1c  mov     ecx, [rdi]
0x180023a1e  jmp     loc_18002384E
0x180023a23  test    r8b, 1
0x180023a27  setnz   dl
0x180023a2a  test    cl, 1
0x180023a2d  setz    al
0x180023a30  test    al, dl
0x180023a32  mov     eax, 0
0x180023a37  setnz   al
0x180023a3a  mov     [rsp+0A8h+var_48], eax
0x180023a3e  jmp     loc_180023705
0x180023a43  lea     r9, [rsp+0A8h+var_48]; jumptable 00000001800239EC cases 1,5
0x180023a48  mov     edx, ebx
0x180023a4a  mov     rcx, rdi
0x180023a4d  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180023a52  jmp     loc_180023701
0x180023a57  lea     r8d, [rbx-140h]; jumptable 00000001800239EC default case, case 4
0x180023a5e  cmp     r8d, 40h ; '@'
0x180023a62  jge     short loc_180023A8F
0x180023a64  mov     eax, [rdi+4]
0x180023a67  mov     edx, r8d
0x180023a6a  shl     edx, 5
0x180023a6d  test    al, 10h
0x180023a6f  jz      short loc_180023A88
0x180023a71  mov     ecx, eax
0x180023a73  shr     ecx, 5
0x180023a76  and     ecx, 3Fh
0x180023a79  cmp     ecx, r8d
0x180023a7c  jnz     short loc_180023A88
0x180023a7e  mov     esi, 1
0x180023a83  jmp     loc_180023878
0x180023a88  xor     esi, esi
0x180023a8a  jmp     loc_180023878
0x180023a8f  mov     esi, dword ptr [rsp+0A8h+var_38]
0x180023a93  mov     [rsp+0A8h+var_48+8], ebx
0x180023a97  mov     [rsp+0A8h+var_48+4], 1
0x180023a9f  jmp     loc_180023705
0x180023aa4  mov     r8d, 1
0x180023aaa  mov     edx, ebx
0x180023aac  mov     ecx, r12d
0x180023aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ab4  jmp     loc_180023725
0x180023ab9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180023abe  test    al, al
0x180023ac0  jnz     loc_18002373A
0x180023ac6  lea     rcx, SRWLock; SRWLock
0x180023acd  call    cs:__imp_AcquireSRWLockExclusive
0x180023ad3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180023ad9  test    eax, eax
0x180023adb  jz      loc_18002383C
0x180023ae1  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180023ae6  test    al, al
0x180023ae8  jnz     loc_18002383C
0x180023aee  jmp     loc_1800238FD
0x180023af3  mov     r8d, [rsp+0A8h+var_48+4]; unsigned int
0x180023af8  mov     edx, [rsp+0A8h+var_48+8]; unsigned int
0x180023afc  mov     ecx, r12d; this
0x180023aff  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180023b04  jmp     loc_180023745
0x180023b09  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180023b10  test    rax, rax
0x180023b13  jz      loc_1800238EB
0x180023b19  jmp     loc_1800238D1
0x180023b1e  mov     edx, ebx
0x180023b20  bts     edx, 1Fh
0x180023b24  cmp     [rsp+0A8h+arg_18], 0
0x180023b2c  cmovz   edx, ebx; unsigned int
0x180023b2f  xor     r8d, r8d; unsigned int
0x180023b32  mov     ecx, r12d; this
0x180023b35  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180023b3a  jmp     loc_180023760
```
