# TokenManager::Evaluate(void)

- ea: `0x18001716c`
- end: `0x180017962`
- name: `?Evaluate@TokenManager@@AEAAXXZ`
- size: `2038`
- prototype: `void __fastcall(TokenManager *__hidden this)`
- caller_count: `7`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800156f0`
- `0x18003db30`
- `0x18003dc78`
- `0x180069420`
- `0x18006fe60`
- `0x180070070`
- `0x1800df4e8`

## callees

- `0x180008394`
- `0x18000974c`
- `0x18000dd88`
- `0x180010080`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180015e88`
- `0x1800168a0`
- `0x180016ff8`
- `0x180017110`
- `0x18001716c`
- `0x180017968`
- `0x1800179f0`
- `0x180017ad0`
- `0x180017b04`
- `0x180017c94`
- `0x1800181fc`
- `0x1800184e8`
- `0x180018578`
- `0x1800188cc`
- `0x180019434`
- `0x18001945c`
- `0x180032d98`
- `0x180039260`
- `0x180039c48`
- `0x1800416e0`
- `0x180049cd8`
- `0x18004df8c`
- `0x1800664ec`
- `0x180084f50`
- `0x180088d44`
- `0x180088de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017533`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017626`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017533`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017626`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171cd`

## string_xrefs

- `0x1800173b0`: `TokenManager::ApplyDomainPolicyFilter: Allow auto and manual connect for non-ethernet candidate`
- `0x1800175a1`: `TokenManager::ApplyDomainPolicyFilter: No action for ethernet candidate`
- `0x1800175c9`: `TokenManager::Evaluate`
- `0x18001767d`: `TokenManager::Evaluate`
- `0x180017785`: `TokenManager::Evaluate`
- `0x1800177f2`: `TokenManager::Evaluate`
- `0x18001786f`: `TokenManager::ApplyDomainPolicyFilter: Disconnect and deny Auto and Manual Connect`
- `0x18001789f`: `TokenManager::ApplyDomainPolicyFilter: Disconnect and deny Auto Connect`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall TokenManager::Evaluate(TokenManager *this)
{
  RTL_SRWLOCK *v2; // rbx
  unsigned int v3; // esi
  void *v4; // rcx
  __m128i v5; // xmm6
  __int64 v6; // rdx
  LONG LockCount; // eax
  LONG v8; // ett
  std::_Ref_count_base *v9; // rcx
  __m128i v10; // xmm6
  __int64 v11; // rdx
  LONG v12; // eax
  LONG v13; // ett
  std::_Ref_count_base *v14; // rcx
  int v15; // r8d
  __int64 *v16; // rsi
  __int64 *v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rdx
  int DomainPolicyActionForInterface; // eax
  int v21; // eax
  int *v22; // rdx
  __int128 *v23; // rsi
  char v24; // r14
  __int64 *i; // rsi
  __int64 *v26; // r14
  __int64 v27; // rcx
  int v28; // eax
  const char *v29; // r9
  __int64 v30; // rsi
  __int64 v31; // r14
  std::_Ref_count_base *v32; // rcx
  void *v33; // rcx
  int *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r12
  __int64 v39; // r14
  const char *v40; // r9
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  const char *v44; // rcx
  struct _WCM_INTERFACE_INFO_LIST *v45[2]; // [rsp+30h] [rbp-A8h] BYREF
  char v46; // [rsp+40h] [rbp-98h]
  RTL_SRWLOCK *v47; // [rsp+48h] [rbp-90h] BYREF
  __int128 v48; // [rsp+58h] [rbp-80h] BYREF
  __int64 v49; // [rsp+68h] [rbp-70h]
  LPVOID lpMem; // [rsp+70h] [rbp-68h] BYREF
  __int128 v51; // [rsp+78h] [rbp-60h] BYREF
  const char *v52; // [rsp+88h] [rbp-50h]
  int v53; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_s(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        144,
        &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids,
        "TokenManager::Evaluate");
    }
    v2 = &SRWLock;
    AcquireSRWLockExclusive(&SRWLock);
    v47 = &SRWLock;
    if ( g_CdeContext )
    {
      lpMem = 0;
      v45[1] = 0;
      v46 = 1;
      v3 = ConnectionAggregator::EnumInterfaces(&v45[1]);
      if ( v46 )
      {
        v4 = lpMem;
        lpMem = v45[1];
        if ( v4 )
          WcmFree(v4);
      }
      if ( v3 )
      {
        v41 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 147, &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids, v3);
            v41 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v41 != &WPP_GLOBAL_Control && *(_BYTE *)(v41 + 25) >= 5u && (*(_BYTE *)(v41 + 28) & 1) != 0 )
            WPP_SF_sL(
              *(_QWORD *)(v41 + 16),
              148,
              (unsigned int)&WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids,
              (unsigned int)"TokenManager::Evaluate",
              v3);
        }
        wistd::unique_ptr<_WCM_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WcmFree(void *)>>::reset(
          &lpMem,
          0);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v47);
      }
      else
      {
        v48 = 0;
        v49 = 0;
        std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(&v48);
        _InterlockedCompareExchange(&dword_18013F8A8, 0, 0);
        v5 = 0;
        *(_OWORD *)v45 = 0;
        v6 = (__int64)*(&lpCriticalSection + 1);
        if ( *(&lpCriticalSection + 1) )
        {
          LockCount = (*(&lpCriticalSection + 1))->LockCount;
          while ( LockCount )
          {
            v8 = LockCount;
            LockCount = _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 8), LockCount + 1, LockCount);
            if ( v8 == LockCount )
            {
              v5 = *(__m128i *)&lpCriticalSection;
              v45[1] = (struct _WCM_INTERFACE_INFO_LIST *)*(&lpCriticalSection + 1);
              break;
            }
          }
        }
        if ( v5.m128i_i64[0] )
        {
          ConnectionAggregator::InternalBuildConnectionCandidates((LPCRITICAL_SECTION)v5.m128i_i64[0]);
        }
        else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
               && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 72, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids);
        }
        v9 = (std::_Ref_count_base *)_mm_srli_si128(v5, 8).m128i_u64[0];
        if ( v9 )
          std::_Ref_count_base::_Decref(v9);
        v53 = 0;
        v10 = 0;
        *(_OWORD *)v45 = 0;
        v11 = (__int64)*(&xmmword_18013FE60 + 1);
        if ( *(&xmmword_18013FE60 + 1) )
        {
          v12 = (*(&xmmword_18013FE60 + 1))->LockCount;
          while ( v12 )
          {
            v13 = v12;
            v12 = _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 8), v12 + 1, v12);
            if ( v13 == v12 )
            {
              v10 = *(__m128i *)&xmmword_18013FE60;
              v45[1] = (struct _WCM_INTERFACE_INFO_LIST *)*(&xmmword_18013FE60 + 1);
              break;
            }
          }
        }
        if ( v10.m128i_i64[0] )
          OnDemand::InternalApplyOnDemandPolicyFilter((LPCRITICAL_SECTION)v10.m128i_i64[0]);
        v14 = (std::_Ref_count_base *)_mm_srli_si128(v10, 8).m128i_u64[0];
        if ( v14 )
          std::_Ref_count_base::_Decref(v14);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 149, &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids);
        }
        LogCandidates(&v48);
        v17 = (__int64 *)*((_QWORD *)&v48 + 1);
        v16 = (__int64 *)v48;
        if ( (_QWORD)v48 != *((_QWORD *)&v48 + 1) )
        {
          v18 = WPP_GLOBAL_Control;
          while ( 1 )
          {
            v19 = *v16;
            if ( *(_DWORD *)(*v16 + 32) == 1 )
            {
              if ( (_UNKNOWN *)v18 == &WPP_GLOBAL_Control
                || *(_BYTE *)(v18 + 25) < 4u
                || (*(_BYTE *)(v18 + 28) & 1) == 0 )
              {
                goto LABEL_43;
              }
              v34 = (int *)(v19 + 52);
              if ( (*(_BYTE *)(v19 + 44) & 1) == 0 )
                v34 = &dword_180103494;
              WPP_SF_S_guid_S(
                *(_QWORD *)(v18 + 16),
                v19,
                v15,
                (unsigned int)L"TokenManager::ApplyDomainPolicyFilter: No action for ethernet candidate",
                *v16,
                (__int64)v34);
              goto LABEL_42;
            }
            DomainPolicyActionForInterface = DomainPolicyHandler::GetDomainPolicyActionForInterface((char *)this + 304);
            if ( !DomainPolicyActionForInterface )
              goto LABEL_116;
            v21 = DomainPolicyActionForInterface - 1;
            if ( !v21 )
              break;
            if ( v21 == 1 )
            {
              v18 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_43;
              }
              v22 = (int *)(*v16 + 52);
              if ( (*(_BYTE *)(*v16 + 44) & 1) == 0 )
                v22 = &dword_180103494;
              WPP_SF_S_guid_S(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                (_DWORD)v22,
                v15,
                (unsigned int)L"TokenManager::ApplyDomainPolicyFilter: Allow auto and manual connect for non-ethernet candidate",
                *v16,
                (__int64)v22);
            }
LABEL_42:
            v18 = WPP_GLOBAL_Control;
LABEL_43:
            v16 += 2;
            if ( v16 == v17 )
              goto LABEL_44;
          }
          *(_DWORD *)(*v16 + 40) &= ~4u;
          LogCandidate(L"TokenManager::ApplyDomainPolicyFilter: Disconnect and deny Auto and Manual Connect", v16);
LABEL_116:
          if ( (*(_BYTE *)(*v16 + 40) & 2) != 0 )
          {
            TrackInitialTokenRemovalReason(v16, 10);
            *(_DWORD *)(*v16 + 40) &= ~2u;
            LogCandidate(L"TokenManager::ApplyDomainPolicyFilter: Disconnect and deny Auto Connect", v16);
          }
          goto LABEL_42;
        }
LABEL_44:
        v23 = (__int128 *)((char *)this + 280);
        ApplyMinimizeDestinationsPolicyFilter((__int64)&v48, (_QWORD *)this + 35);
        ApplyStrictMinimizePolicyFilter(&v48);
        if ( !(unsigned int)IsServerSKU() )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 150, &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids);
          }
          LogCandidates(&v48);
          v24 = BuildTokens(&v48, (char *)this + 280, lpMem);
          OnDemand::UpdateDryCandidatesAfterEvaluation(&v48);
          if ( v24 )
          {
            LogCandidates(&v48);
            ApplyTokens(lpMem);
            std::vector<std::shared_ptr<WCM_CANDIDATE>>::clear((char *)this + 280);
            v51 = 0;
            v52 = 0;
            std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(&v51);
            v38 = *((_QWORD *)&v48 + 1);
            v39 = v48;
            v40 = (const char *)*((_QWORD *)&v51 + 1);
            while ( v39 != v38 )
            {
              if ( (*(_BYTE *)(*(_QWORD *)v39 + 40LL) & 2) != 0 )
              {
                if ( v40 == v52 )
                {
                  try
                  {
                    std::vector<std::shared_ptr<WCM_CONAGG_INTERFACE_INFO>>::_Emplace_reallocate<std::shared_ptr<WCM_CONAGG_INTERFACE_INFO> const &>(
                      &v51,
                      v40,
                      v39);
                    v40 = (const char *)*((_QWORD *)&v51 + 1);
                  }
                  catch ( ... )
                  {
                    wil::details::in1diag3::Log_CaughtException(
                      retaddr,
                      (void *)0xB8C,
                      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
                      v40);
                    v2 = v47;
                    goto LABEL_47;
                  }
                }
                else
                {
                  std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(v40);
                  v40 = (const char *)(*((_QWORD *)&v51 + 1) + 16LL);
                  *((_QWORD *)&v51 + 1) += 16LL;
                }
              }
              v39 += 16;
            }
            if ( v23 != &v51 )
            {
              v42 = *(_QWORD *)v23;
              *(_QWORD *)v23 = v51;
              *(_QWORD *)&v51 = v42;
              v43 = *((_QWORD *)this + 36);
              *((_QWORD *)this + 36) = v40;
              *((_QWORD *)&v51 + 1) = v43;
              v44 = (const char *)*((_QWORD *)this + 37);
              *((_QWORD *)this + 37) = v52;
              v52 = v44;
            }
            std::vector<std::shared_ptr<WCM_CANDIDATE>>::_Tidy(&v51, v36, v37, v40);
          }
LABEL_47:
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 151, &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids);
          }
          v26 = (__int64 *)*((_QWORD *)&v48 + 1);
          for ( i = (__int64 *)v48; i != v26; i += 2 )
          {
            v27 = *i;
            v28 = *(_DWORD *)(*i + 40) & 0x60;
            if ( (*(_DWORD *)(*i + 40) & 1) == 0 || v28 )
            {
              if ( *(_DWORD *)(v27 + 36) == 4 && (*(_DWORD *)(*i + 40) & 1) == 0 )
              {
                if ( v28 )
                  ConnectionAggregator::AbortSoftDisconnect((const struct _GUID *)v27);
              }
            }
            else
            {
              ConnectionAggregator::BeginSoftDisconnect((const struct _GUID *)v27);
            }
          }
        }
        CdeUpdateWnfState(&v48);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_sL(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            152,
            (unsigned int)&WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids,
            (unsigned int)"TokenManager::Evaluate",
            0);
        }
        v30 = v48;
        if ( (_QWORD)v48 )
        {
          v31 = *((_QWORD *)&v48 + 1);
          if ( (_QWORD)v48 != *((_QWORD *)&v48 + 1) )
          {
            do
            {
              v32 = *(std::_Ref_count_base **)(v30 + 8);
              if ( v32 )
                std::_Ref_count_base::_Decref(v32);
              v30 += 16;
            }
            while ( v30 != v31 );
            v30 = v48;
          }
          std::_Deallocate<16>(v30, (v49 - v30) & 0xFFFFFFFFFFFFFFF0uLL);
          v48 = 0;
          v49 = 0;
        }
        v33 = lpMem;
        lpMem = 0;
        if ( v33 )
          WcmFree(v33);
        if ( v2 )
          ReleaseSRWLockExclusive(v2);
      }
    }
    else
    {
      v35 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 145, &WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids);
          v35 = WPP_GLOBAL_Control;
        }
        if ( (_UNKNOWN *)v35 != &WPP_GLOBAL_Control && *(_BYTE *)(v35 + 25) >= 5u && (*(_BYTE *)(v35 + 28) & 1) != 0 )
          WPP_SF_sL(
            *(_QWORD *)(v35 + 16),
            146,
            (unsigned int)&WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids,
            (unsigned int)"TokenManager::Evaluate",
            21);
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xB9A,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\tokenmanager\\lib\\tokenmanager.cpp",
      v29);
  }
}

```

## disassembly

```asm
0x18001716c  mov     rax, rsp
0x18001716f  mov     [rax+10h], rbx
0x180017173  mov     [rax+18h], rsi
0x180017177  push    rdi
0x180017178  push    r12
0x18001717a  push    r13
0x18001717c  push    r14
0x18001717e  push    r15
0x180017180  sub     rsp, 0B0h
0x180017187  movaps  xmmword ptr [rax-38h], xmm6
0x18001718b  mov     rax, cs:__security_cookie
0x180017192  xor     rax, rsp
0x180017195  mov     [rsp+0D8h+var_40], rax
0x18001719d  mov     r13, rcx
0x1800171a0  lea     r15, WPP_GLOBAL_Control
0x1800171a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171ae  cmp     rcx, r15
0x1800171b1  jz      short loc_1800171C3
0x1800171b3  cmp     byte ptr [rcx+19h], 5
0x1800171b7  jb      short loc_1800171C3
0x1800171b9  test    byte ptr [rcx+1Ch], 1
0x1800171bd  jnz     loc_1800175C4
0x1800171c3  lea     rbx, SRWLock
0x1800171ca  mov     rcx, rbx; SRWLock
0x1800171cd  call    cs:__imp_AcquireSRWLockExclusive
0x1800171d3  mov     [rsp+0D8h+var_90], rbx
0x1800171d8  xor     edi, edi
0x1800171da  cmp     cs:?g_CdeContext@@3UCDE_CONTEXT@@A, edi; CDE_CONTEXT g_CdeContext
0x1800171e0  jz      loc_180017613
0x1800171e6  mov     [rsp+0D8h+lpMem], rdi
0x1800171eb  lea     rax, [rsp+0D8h+lpMem]
0x1800171f0  mov     [rsp+0D8h+var_A8], rax
0x1800171f5  mov     [rsp+0D8h+var_A8+8], rdi
0x1800171fa  mov     [rsp+0D8h+var_98], 1
0x1800171ff  lea     rcx, [rsp+0D8h+var_A8+8]; struct _WCM_INTERFACE_INFO_LIST **
0x180017204  call    ?EnumInterfaces@ConnectionAggregator@@SAKPEAPEAU_WCM_INTERFACE_INFO_LIST@@@Z; ConnectionAggregator::EnumInterfaces(_WCM_INTERFACE_INFO_LIST * *)
0x180017209  mov     esi, eax
0x18001720b  cmp     [rsp+0D8h+var_98], dil
0x180017210  jz      short loc_18001722C
0x180017212  mov     r8, [rsp+0D8h+var_A8]
0x180017217  mov     rcx, [r8]; lpMem
0x18001721a  mov     rdx, [rsp+0D8h+var_A8+8]
0x18001721f  mov     [r8], rdx
0x180017222  test    rcx, rcx
0x180017225  jz      short loc_18001722C
0x180017227  call    WcmFree
0x18001722c  test    esi, esi
0x18001722e  jnz     loc_1800177A1
0x180017234  xorps   xmm0, xmm0
0x180017237  xor     eax, eax
0x180017239  movups  [rsp+0D8h+var_80], xmm0
0x18001723e  mov     [rsp+0D8h+var_70], rax
0x180017243  lea     rcx, [rsp+0D8h+var_80]
0x180017248  call    ??0?$vector@UTrafficDescriptor@FirewallManager@@V?$allocator@UTrafficDescriptor@FirewallManager@@@std@@@std@@QEAA@XZ; std::vector<FirewallManager::TrafficDescriptor>::vector<FirewallManager::TrafficDescriptor>(void)
0x18001724d  nop
0x18001724e  xor     eax, eax
0x180017250  lock cmpxchg cs:dword_18013F8A8, edi
0x180017258  mov     r8d, edi
0x18001725b  setz    r8b
0x18001725f  xorps   xmm6, xmm6
0x180017262  movdqu  xmmword ptr [rsp+0D8h+var_A8], xmm6
0x180017268  mov     rdx, qword ptr cs:lpCriticalSection+8
0x18001726f  test    rdx, rdx
0x180017272  jz      short loc_180017292
0x180017274  mov     eax, [rdx+8]
0x180017277  test    eax, eax
0x180017279  jz      short loc_180017292
0x18001727b  lea     ecx, [rax+1]
0x18001727e  lock cmpxchg [rdx+8], ecx
0x180017283  jnz     short loc_180017277
0x180017285  movups  xmm6, cs:lpCriticalSection
0x18001728c  movdqu  xmmword ptr [rsp+0D8h+var_A8], xmm6
0x180017292  movq    rcx, xmm6; lpCriticalSection
0x180017297  test    rcx, rcx
0x18001729a  jz      loc_180017827
0x1800172a0  lea     rdx, [rsp+0D8h+var_80]
0x1800172a5  call    ?InternalBuildConnectionCandidates@ConnectionAggregator@@AEAAXAEAV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@H@Z; ConnectionAggregator::InternalBuildConnectionCandidates(std::vector<std::shared_ptr<WCM_CANDIDATE>> &,int)
0x1800172aa  nop
0x1800172ab  psrldq  xmm6, 8
0x1800172b0  movq    rcx, xmm6; this
0x1800172b5  test    rcx, rcx
0x1800172b8  jz      short loc_1800172BF
0x1800172ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800172bf  mov     [rsp+0D8h+var_48], edi
0x1800172c6  xorps   xmm6, xmm6
0x1800172c9  movdqu  xmmword ptr [rsp+0D8h+var_A8], xmm6
0x1800172cf  mov     rdx, qword ptr cs:xmmword_18013FE60+8
0x1800172d6  test    rdx, rdx
0x1800172d9  jz      short loc_1800172F9
0x1800172db  mov     eax, [rdx+8]
0x1800172de  test    eax, eax
0x1800172e0  jz      short loc_1800172F9
0x1800172e2  lea     ecx, [rax+1]
0x1800172e5  lock cmpxchg [rdx+8], ecx
0x1800172ea  jnz     short loc_1800172DE
0x1800172ec  movups  xmm6, cs:xmmword_18013FE60
0x1800172f3  movdqu  xmmword ptr [rsp+0D8h+var_A8], xmm6
0x1800172f9  movq    rcx, xmm6; lpCriticalSection
0x1800172fe  test    rcx, rcx
0x180017301  jnz     loc_1800175AD
0x180017307  psrldq  xmm6, 8
0x18001730c  movq    rcx, xmm6; this
0x180017311  test    rcx, rcx
0x180017314  jz      short loc_18001731B
0x180017316  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001731b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017322  cmp     rcx, r15
0x180017325  jnz     loc_1800175E5
0x18001732b  lea     rcx, [rsp+0D8h+var_80]
0x180017330  call    LogCandidates
0x180017335  mov     rsi, qword ptr [rsp+0D8h+var_80]
0x18001733a  mov     r14, qword ptr [rsp+0D8h+var_80+8]
0x18001733f  cmp     rsi, r14
0x180017342  jz      loc_1800173D4
0x180017348  mov     rcx, cs:WPP_GLOBAL_Control
0x18001734f  mov     rdx, [rsi]
0x180017352  cmp     dword ptr [rdx+20h], 1
0x180017356  jz      loc_18001756C
0x18001735c  lea     rcx, [r13+130h]
0x180017363  call    ?GetDomainPolicyActionForInterface@DomainPolicyHandler@@QEAA?AW4DomainPolicyAction@@AEBU_GUID@@@Z; DomainPolicyHandler::GetDomainPolicyActionForInterface(_GUID const &)
0x180017368  test    eax, eax
0x18001736a  jz      loc_18001787B
0x180017370  sub     eax, 1
0x180017373  jz      loc_180017865
0x180017379  cmp     eax, 1
0x18001737c  jnz     short loc_1800173C0
0x18001737e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017385  cmp     rcx, r15
0x180017388  jz      short loc_1800173C7
0x18001738a  cmp     byte ptr [rcx+19h], 4
0x18001738e  jb      short loc_1800173C7
0x180017390  test    [rcx+1Ch], al
0x180017393  jz      short loc_1800173C7
0x180017395  mov     rax, [rsi]
0x180017398  test    byte ptr [rax+2Ch], 1
0x18001739c  lea     rdx, [rax+34h]
0x1800173a0  jz      loc_180017699
0x1800173a6  mov     [rsp+0D8h+var_B0], rdx
0x1800173ab  mov     [rsp+0D8h+var_B8], rax
0x1800173b0  lea     r9, aTokenmanagerAp_2; "TokenManager::ApplyDomainPolicyFilter: "...
0x1800173b7  mov     rcx, [rcx+10h]
0x1800173bb  call    WPP_SF_S_guid_S
0x1800173c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173c7  add     rsi, 10h
0x1800173cb  cmp     rsi, r14
0x1800173ce  jnz     loc_18001734F
0x1800173d4  lea     rsi, [r13+118h]
0x1800173db  mov     rdx, rsi
0x1800173de  lea     rcx, [rsp+0D8h+var_80]
0x1800173e3  call    ?ApplyMinimizeDestinationsPolicyFilter@@YAXAEBV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@0@Z; ApplyMinimizeDestinationsPolicyFilter(std::vector<std::shared_ptr<WCM_CANDIDATE>> const &,std::vector<std::shared_ptr<WCM_CANDIDATE>> const &)
0x1800173e8  lea     rcx, [rsp+0D8h+var_80]
0x1800173ed  call    ?ApplyStrictMinimizePolicyFilter@@YAXAEBV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@@Z; ApplyStrictMinimizePolicyFilter(std::vector<std::shared_ptr<WCM_CANDIDATE>> const &)
0x1800173f2  call    IsServerSKU
0x1800173f7  test    eax, eax
0x1800173f9  jnz     loc_1800174AA
0x1800173ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180017406  cmp     rcx, r15
0x180017409  jnz     loc_180017632
0x18001740f  lea     rcx, [rsp+0D8h+var_80]
0x180017414  call    LogCandidates
0x180017419  mov     r8, [rsp+0D8h+lpMem]
0x18001741e  mov     rdx, rsi
0x180017421  lea     rcx, [rsp+0D8h+var_80]
0x180017426  call    ?BuildTokens@@YA_NAEBV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@0PEAU_WCM_INTERFACE_INFO_LIST@@@Z; BuildTokens(std::vector<std::shared_ptr<WCM_CANDIDATE>> const &,std::vector<std::shared_ptr<WCM_CANDIDATE>> const &,_WCM_INTERFACE_INFO_LIST *)
0x18001742b  mov     r14b, al
0x18001742e  lea     rcx, [rsp+0D8h+var_80]
0x180017433  call    ?UpdateDryCandidatesAfterEvaluation@OnDemand@@SAKAEAV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@@Z; OnDemand::UpdateDryCandidatesAfterEvaluation(std::vector<std::shared_ptr<WCM_CANDIDATE>> &)
0x180017438  test    r14b, r14b
0x18001743b  jnz     loc_1800176B1
0x180017441  mov     rcx, cs:WPP_GLOBAL_Control
0x180017448  cmp     rcx, r15
0x18001744b  jz      short loc_18001746E
0x18001744d  cmp     byte ptr [rcx+19h], 4
0x180017451  jb      short loc_18001746E
0x180017453  test    byte ptr [rcx+1Ch], 1
0x180017457  jz      short loc_18001746E
0x180017459  mov     edx, 97h
0x18001745e  lea     r8, WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids
0x180017465  mov     rcx, [rcx+10h]
0x180017469  call    WPP_SF_
0x18001746e  mov     rsi, qword ptr [rsp+0D8h+var_80]
0x180017473  mov     r14, qword ptr [rsp+0D8h+var_80+8]
0x180017478  cmp     rsi, r14
0x18001747b  jz      short loc_1800174AA
0x18001747d  mov     rcx, [rsi]; struct _GUID *
0x180017480  mov     eax, [rcx+28h]
0x180017483  mov     edx, eax
0x180017485  and     eax, 60h
0x180017488  and     edx, 1
0x18001748b  jnz     loc_18001794B
0x180017491  cmp     dword ptr [rcx+24h], 4
0x180017495  jnz     short loc_1800174A4
0x180017497  test    edx, edx
0x180017499  jnz     short loc_1800174A4
0x18001749b  test    eax, eax
0x18001749d  jz      short loc_1800174A4
0x18001749f  call    ?AbortSoftDisconnect@ConnectionAggregator@@SAXPEBU_GUID@@@Z; ConnectionAggregator::AbortSoftDisconnect(_GUID const *)
0x1800174a4  add     rsi, 10h
0x1800174a8  jmp     short loc_180017478
0x1800174aa  lea     rcx, [rsp+0D8h+var_80]
0x1800174af  call    ?CdeUpdateWnfState@@YAXAEBV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@@Z; CdeUpdateWnfState(std::vector<std::shared_ptr<WCM_CANDIDATE>> const &)
0x1800174b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174bb  cmp     rcx, r15
0x1800174be  jnz     loc_180017660
0x1800174c4  mov     rsi, qword ptr [rsp+0D8h+var_80]
0x1800174c9  test    rsi, rsi
0x1800174cc  jz      short loc_180017516
0x1800174ce  mov     r14, qword ptr [rsp+0D8h+var_80+8]
0x1800174d3  cmp     rsi, r14
0x1800174d6  jz      short loc_1800174F4
0x1800174d8  mov     rcx, [rsi+8]; this
0x1800174dc  test    rcx, rcx
0x1800174df  jz      short loc_1800174E6
0x1800174e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800174e6  add     rsi, 10h
0x1800174ea  cmp     rsi, r14
0x1800174ed  jnz     short loc_1800174D8
0x1800174ef  mov     rsi, qword ptr [rsp+0D8h+var_80]
0x1800174f4  mov     rdx, [rsp+0D8h+var_70]
0x1800174f9  sub     rdx, rsi
0x1800174fc  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180017500  mov     rcx, rsi
0x180017503  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017508  xorps   xmm0, xmm0
0x18001750b  movdqu  [rsp+0D8h+var_80], xmm0
0x180017511  mov     [rsp+0D8h+var_70], rdi
0x180017516  mov     rcx, [rsp+0D8h+lpMem]; lpMem
0x18001751b  mov     [rsp+0D8h+lpMem], rdi
0x180017520  test    rcx, rcx
0x180017523  jz      short loc_18001752B
0x180017525  call    WcmFree
0x18001752a  nop
0x18001752b  test    rbx, rbx
0x18001752e  jz      short loc_18001753A
0x180017530  mov     rcx, rbx; SRWLock
0x180017533  call    cs:__imp_ReleaseSRWLockExclusive
0x180017539  nop
0x18001753a  mov     rcx, [rsp+0D8h+var_40]
0x180017542  xor     rcx, rsp; StackCookie
0x180017545  call    __security_check_cookie
0x18001754a  lea     r11, [rsp+0D8h+var_28]
0x180017552  mov     rbx, [r11+38h]
0x180017556  mov     rsi, [r11+40h]
0x18001755a  movaps  xmm6, xmmword ptr [r11-10h]
0x18001755f  mov     rsp, r11
0x180017562  pop     r15
0x180017564  pop     r14
0x180017566  pop     r13
0x180017568  pop     r12
0x18001756a  pop     rdi
0x18001756b  retn
0x18001756c  cmp     rcx, r15
0x18001756f  jz      loc_1800173C7
0x180017575  cmp     byte ptr [rcx+19h], 4
0x180017579  jb      loc_1800173C7
0x18001757f  test    byte ptr [rcx+1Ch], 1
0x180017583  jz      loc_1800173C7
0x180017589  test    byte ptr [rdx+2Ch], 1
0x18001758d  lea     rax, [rdx+34h]
0x180017591  jz      loc_1800176A5
0x180017597  mov     [rsp+0D8h+var_B0], rax
0x18001759c  mov     [rsp+0D8h+var_B8], rdx
0x1800175a1  lea     r9, aTokenmanagerAp_1; "TokenManager::ApplyDomainPolicyFilter: "...
0x1800175a8  jmp     loc_1800173B7
0x1800175ad  lea     r8, [rsp+0D8h+var_48]
0x1800175b5  lea     rdx, [rsp+0D8h+var_80]
0x1800175ba  call    ?InternalApplyOnDemandPolicyFilter@OnDemand@@AEAAKAEAV?$vector@V?$shared_ptr@UWCM_CANDIDATE@@@std@@V?$allocator@V?$shared_ptr@UWCM_CANDIDATE@@@std@@@2@@std@@PEAH@Z; OnDemand::InternalApplyOnDemandPolicyFilter(std::vector<std::shared_ptr<WCM_CANDIDATE>> &,int *)
0x1800175bf  jmp     loc_180017307
0x1800175c4  mov     edx, 90h
0x1800175c9  lea     r9, aTokenmanagerEv; "TokenManager::Evaluate"
0x1800175d0  lea     r8, WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids
0x1800175d7  mov     rcx, [rcx+10h]
0x1800175db  call    WPP_SF_s
0x1800175e0  jmp     loc_1800171C3
0x1800175e5  cmp     byte ptr [rcx+19h], 4
0x1800175e9  jb      loc_18001732B
0x1800175ef  test    byte ptr [rcx+1Ch], 1
0x1800175f3  jz      loc_18001732B
0x1800175f9  mov     edx, 95h
0x1800175fe  lea     r8, WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids
0x180017605  mov     rcx, [rcx+10h]
0x180017609  call    WPP_SF_
0x18001760e  jmp     loc_18001732B
0x180017613  mov     rcx, cs:WPP_GLOBAL_Control
0x18001761a  cmp     rcx, r15
0x18001761d  jnz     loc_180017733
0x180017623  mov     rcx, rbx; SRWLock
0x180017626  call    cs:__imp_ReleaseSRWLockExclusive
0x18001762c  nop
0x18001762d  jmp     loc_18001753A
0x180017632  cmp     byte ptr [rcx+19h], 4
0x180017636  jb      loc_18001740F
0x18001763c  test    byte ptr [rcx+1Ch], 1
0x180017640  jz      loc_18001740F
0x180017646  mov     edx, 96h
0x18001764b  lea     r8, WPP_fa856c8c960337a50ed78c4cc7c33dd3_Traceguids
0x180017652  mov     rcx, [rcx+10h]
0x180017656  call    WPP_SF_
0x18001765b  jmp     loc_18001740F
0x180017660  cmp     byte ptr [rcx+19h], 5
  ... truncated ...
```
