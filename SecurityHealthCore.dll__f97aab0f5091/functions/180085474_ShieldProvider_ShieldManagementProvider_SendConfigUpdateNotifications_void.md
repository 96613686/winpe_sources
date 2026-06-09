# ShieldProvider::ShieldManagementProvider::SendConfigUpdateNotifications(void)

- ea: `0x180085474`
- end: `0x1800859f1`
- name: `?SendConfigUpdateNotifications@ShieldManagementProvider@ShieldProvider@@AEAAJXZ`
- size: `1405`
- prototype: `__int64 __fastcall(ShieldProvider::ShieldManagementProvider *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180085a00`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180016d08`
- `0x18002e680`
- `0x180046c88`
- `0x180046e44`
- `0x180053a5c`
- `0x180083edc`
- `0x1800840a4`
- `0x1800840d4`
- `0x180085474`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e17e8`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x18008552d`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180085697`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180085825`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800859bb`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18008552d`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180085697`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180085825`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800859bb`
- `ole32!CoTaskMemFree` at `0x18008566c`
- `ole32!CoTaskMemFree` at `0x1800857fa`
- `ole32!CoTaskMemFree` at `0x180085990`
- `ole32!CoTaskMemFree` at `0x18008566c`
- `ole32!CoTaskMemFree` at `0x1800857fa`
- `ole32!CoTaskMemFree` at `0x180085990`

## string_xrefs

- `0x180085875`: `ShieldProvider::ShieldManagementProvider::SendConfigUpdateNotifications`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall ShieldProvider::ShieldManagementProvider::SendConfigUpdateNotifications(
        ShieldProvider::ShieldManagementProvider *this)
{
  unsigned int v2; // r14d
  void *v3; // rbx
  char i; // al
  void *v6; // rcx
  __int64 **v7; // rdx
  __int64 *v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // r8
  bool v11; // r9
  _DWORD *v12; // rdi
  unsigned int v13; // r12d
  int v14; // eax
  __int64 v15; // r8
  __int64 *v16; // rax
  __int64 *j; // rcx
  __int64 *v18; // rdx
  __int64 v19; // rcx
  char v20; // al
  int v21; // eax
  ShieldProvider::ShieldManagementProvider *k; // rsi
  CommonUtil *v23; // rcx
  __int64 v24; // [rsp+0h] [rbp-1D8h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-1B0h] BYREF
  __int64 *v26; // [rsp+30h] [rbp-1A8h] BYREF
  __int64 v27; // [rsp+38h] [rbp-1A0h]
  __int128 v28; // [rsp+40h] [rbp-198h] BYREF
  __int64 v29; // [rsp+50h] [rbp-188h]
  void *v30; // [rsp+58h] [rbp-180h]
  ShieldProvider::ShieldManagementProvider *v31; // [rsp+60h] [rbp-178h]
  int v32; // [rsp+68h] [rbp-170h]
  __int128 v33; // [rsp+70h] [rbp-168h] BYREF
  _BYTE v34[16]; // [rsp+80h] [rbp-158h] BYREF
  char v35; // [rsp+90h] [rbp-148h]
  _BYTE v36[248]; // [rsp+A0h] [rbp-138h] BYREF
  const std::exception *v37; // [rsp+198h] [rbp-40h] BYREF

  v31 = this;
  v2 = 0;
  v3 = 0;
  v30 = 0;
  std::set<unsigned long>::set<unsigned long>(&v26);
  v33 = 0;
  std::_Tree<std::_Tmap_traits<unsigned int,enum _tagHealthAdvisorSeverity,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,enum _tagHealthAdvisorSeverity>>,0>>::_Alloc_sentinel_and_proxy(&v33);
  pv = (char *)this + 16;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    &v28,
    (char *)this + 16);
  for ( i = 1; ; i = 0 )
  {
    LOBYTE(v29) = i;
    if ( !i )
      break;
    if ( *((_BYTE *)this + 176) )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v28);
      std::_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>::~_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>(&v33);
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(&v26);
      if ( v3 )
        DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      return 0;
    }
    v6 = v3;
    v3 = (void *)*((_QWORD *)this + 21);
    v30 = v3;
    *((_QWORD *)this + 21) = *((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = v6;
    v7 = (__int64 **)((char *)this + 144);
    if ( &v26 != (__int64 **)((char *)this + 144) )
    {
      v8 = v26;
      v26 = *v7;
      *v7 = v8;
      v9 = v27;
      v27 = *((_QWORD *)this + 19);
      *((_QWORD *)this + 19) = v9;
    }
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(&v28);
  v12 = 0;
  pv = 0;
  v13 = v27;
  v32 = v27;
  if ( !(_DWORD)v27 )
    goto LABEL_62;
  LOBYTE(v10) = 1;
  v14 = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)&pv, (void **)(4LL * (unsigned int)v27), v10, v11);
  v2 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids,
        (unsigned int)v14);
    if ( pv )
      CoTaskMemFree(pv);
    std::_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>::~_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>(&v33);
    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(&v26);
    if ( v3 )
      DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    return v2;
  }
  v15 = 0;
  v16 = (__int64 *)*v26;
  v12 = pv;
  while ( v16 != v26 )
  {
    v12[v15] = *((_DWORD *)v16 + 7);
    v15 = (unsigned int)(v15 + 1);
    j = (__int64 *)v16[2];
    if ( *((_BYTE *)j + 25) )
    {
      for ( j = (__int64 *)v16[1]; !*((_BYTE *)j + 25) && v16 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v16 = j;
LABEL_27:
      v16 = j;
    }
    else
    {
      v18 = (__int64 *)*j;
      if ( *(_BYTE *)(*j + 25) )
        goto LABEL_27;
      do
      {
        v16 = v18;
        v18 = (__int64 *)*v18;
      }
      while ( !*((_BYTE *)v18 + 25) );
    }
  }
  std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(&v28);
  v19 = (__int64)(*((_QWORD *)this + 28) - *((_QWORD *)this + 27)) >> 4;
  if ( v19 && v19 != *((_DWORD *)this + 61) )
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v34,
      (char *)this + 16);
    v20 = 1;
    v35 = 1;
    while ( v20 )
    {
      v21 = ShieldProvider::HrStdCopyVector<ShieldProvider::NetworkProtectionStatusSinkRecord>(&v28, (char *)this + 216);
      v2 = v21;
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids,
            (unsigned int)v21);
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v34);
        if ( (_QWORD)v28 )
        {
          std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(
            v28,
            *((_QWORD *)&v28 + 1));
          std::_Deallocate<16>(v28, (v29 - v28) & 0xFFFFFFFFFFFFFFF0uLL);
          v28 = 0;
          v29 = 0;
        }
        if ( v12 )
          CoTaskMemFree(v12);
        std::_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>::~_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>(&v33);
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(&v26);
        if ( v3 )
          DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        return v2;
      }
      v20 = 0;
      v35 = 0;
    }
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v34);
    for ( k = (ShieldProvider::ShieldManagementProvider *)v28;
          ;
          k = (ShieldProvider::ShieldManagementProvider *)((char *)k + 16) )
    {
      v31 = k;
      if ( k == *((ShieldProvider::ShieldManagementProvider **)&v28 + 1) )
        break;
      if ( *((_QWORD *)k + 1) )
      {
        ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
          (ShieldProvider::CRPCTimeoutEx *)v36,
          0xBB8u,
          L"ShieldProvider::ShieldManagementProvider::SendConfigUpdateNotifications");
        try
        {
          (*(void (__fastcall **)(_QWORD *, _QWORD, _DWORD *))(**((_QWORD **)k + 1) + 24LL))(
            *((_QWORD **)k + 1),
            v13,
            v12);
          ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v36);
        }
        catch ( const std::exception *v37 )
        {
          CommonUtil::HrFromStdException(v23, (const struct std::exception *)&v24);
        }
        if ( (v2 & 0x80000000) != 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids, v2);
        }
      }
    }
  }
  if ( (_QWORD)v28 )
  {
    std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(v28, *((_QWORD *)&v28 + 1));
    std::_Deallocate<16>(v28, (v29 - v28) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  if ( (v2 & 0x80000000) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids, v2);
  }
LABEL_62:
  if ( v12 )
    CoTaskMemFree(v12);
  std::_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>::~_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>(&v33);
  std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(&v26);
  if ( v3 )
    DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  return v2;
}

```

## disassembly

```asm
0x180085474  mov     [rsp+arg_8], rbx
0x180085479  mov     [rsp+arg_10], rsi
0x18008547e  push    rdi
0x18008547f  push    r12
0x180085481  push    r13
0x180085483  push    r14
0x180085485  push    r15
0x180085487  sub     rsp, 1B0h
0x18008548e  mov     rax, cs:__security_cookie
0x180085495  xor     rax, rsp
0x180085498  mov     [rsp+1D8h+var_30], rax
0x1800854a0  mov     rsi, rcx
0x1800854a3  mov     [rsp+1D8h+var_178], rcx
0x1800854a8  xor     r14d, r14d
0x1800854ab  xor     ebx, ebx
0x1800854ad  mov     [rsp+1D8h+var_180], rbx
0x1800854b2  lea     rcx, [rsp+1D8h+var_1A8]
0x1800854b7  call    ??0?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@QEAA@XZ; std::set<ulong>::set<ulong>(void)
0x1800854bc  nop
0x1800854bd  xorps   xmm0, xmm0
0x1800854c0  movdqu  [rsp+1D8h+var_168], xmm0
0x1800854c6  lea     rcx, [rsp+1D8h+var_168]
0x1800854cb  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@IW4_tagHealthAdvisorSeverity@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIW4_tagHealthAdvisorSeverity@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<uint,_tagHealthAdvisorSeverity,std::less<uint>,std::allocator<std::pair<uint const,_tagHealthAdvisorSeverity>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800854d0  nop
0x1800854d1  lea     r13, [rsi+10h]
0x1800854d5  mov     [rsp+1D8h+pv], r13
0x1800854da  mov     rdx, r13
0x1800854dd  lea     rcx, [rsp+1D8h+var_198]
0x1800854e2  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800854e7  mov     al, 1
0x1800854e9  mov     byte ptr [rsp+1D8h+var_188], al
0x1800854ed  test    al, al
0x1800854ef  jz      loc_1800855F3
0x1800854f5  cmp     byte ptr [rsi+0B0h], 0
0x1800854fc  jz      short loc_18008553A
0x1800854fe  lea     rcx, [rsp+1D8h+var_198]
0x180085503  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180085508  nop
0x180085509  lea     rcx, [rsp+1D8h+var_168]
0x18008550e  call    ??1?$_Tree@V?$_Tset_traits@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@U?$less@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@@std@@V?$allocator@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>::~_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>(void)
0x180085513  nop
0x180085514  lea     rcx, [rsp+1D8h+var_1A8]
0x180085519  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x18008551e  nop
0x18008551f  test    rbx, rbx
0x180085522  jz      short loc_180085533
0x180085524  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180085528  mov     rdx, rbx; Timer
0x18008552b  xor     ecx, ecx; TimerQueue
0x18008552d  call    cs:__imp_DeleteTimerQueueTimer
0x180085533  xor     eax, eax
0x180085535  jmp     loc_1800859C4
0x18008553a  mov     rcx, rbx
0x18008553d  mov     rbx, [rsi+0A8h]
0x180085544  mov     [rsp+1D8h+var_180], rbx
0x180085549  mov     rax, [rsi+0A0h]
0x180085550  mov     [rsi+0A8h], rax
0x180085557  mov     [rsi+0A0h], rcx
0x18008555e  lea     rdx, [rsi+90h]
0x180085565  lea     rax, [rsp+1D8h+var_1A8]
0x18008556a  cmp     rax, rdx
0x18008556d  jz      short loc_180085591
0x18008556f  mov     rcx, [rsp+1D8h+var_1A8]
0x180085574  mov     rax, [rdx]
0x180085577  mov     [rsp+1D8h+var_1A8], rax
0x18008557c  mov     [rdx], rcx
0x18008557f  mov     rcx, [rsp+1D8h+var_1A0]
0x180085584  mov     rax, [rdx+8]
0x180085588  mov     [rsp+1D8h+var_1A0], rax
0x18008558d  mov     [rdx+8], rcx
0x180085591  jmp     short loc_1800855A7
0x180085593  mov     r14d, [rsp+1D8h+var_1B8]
0x180085598  mov     rbx, [rsp+1D8h+var_180]
0x18008559d  mov     rsi, [rsp+1D8h+var_178]
0x1800855a2  mov     r13, [rsp+1D8h+pv]
0x1800855a7  test    r14d, r14d
0x1800855aa  jns     short loc_1800855EC
0x1800855ac  lea     r15, WPP_GLOBAL_Control
0x1800855b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800855ba  cmp     rcx, r15
0x1800855bd  jz      short loc_1800855DD
0x1800855bf  test    byte ptr [rcx+1Ch], 1
0x1800855c3  jz      short loc_1800855DD
0x1800855c5  mov     edx, 28h ; '('
0x1800855ca  mov     r9d, r14d
0x1800855cd  lea     r8, WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids
0x1800855d4  mov     rcx, [rcx+10h]
0x1800855d8  call    WPP_SF_d
0x1800855dd  lea     rcx, [rsp+1D8h+var_198]
0x1800855e2  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800855e7  jmp     loc_180085997
0x1800855ec  xor     al, al
0x1800855ee  jmp     loc_1800854E9
0x1800855f3  lea     rcx, [rsp+1D8h+var_198]
0x1800855f8  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800855fd  xor     edi, edi
0x1800855ff  mov     [rsp+1D8h+pv], rdi
0x180085604  mov     r12d, dword ptr [rsp+1D8h+var_1A0]
0x180085609  mov     [rsp+1D8h+var_170], r12d
0x18008560e  test    r12d, r12d
0x180085611  jz      loc_180085988
0x180085617  mov     edx, r12d
0x18008561a  shl     rdx, 2; void **
0x18008561e  mov     r8b, 1; unsigned __int64
0x180085621  lea     rcx, [rsp+1D8h+pv]; this
0x180085626  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x18008562b  mov     r14d, eax
0x18008562e  test    eax, eax
0x180085630  jns     short loc_1800856A5
0x180085632  lea     r15, WPP_GLOBAL_Control
0x180085639  mov     rcx, cs:WPP_GLOBAL_Control
0x180085640  cmp     rcx, r15
0x180085643  jz      short loc_180085662
0x180085645  test    byte ptr [rcx+1Ch], 1
0x180085649  jz      short loc_180085662
0x18008564b  lea     edx, [rdi+29h]
0x18008564e  mov     r9d, eax
0x180085651  lea     r8, WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids
0x180085658  mov     rcx, [rcx+10h]
0x18008565c  call    WPP_SF_d
0x180085661  nop
0x180085662  mov     rcx, [rsp+1D8h+pv]; pv
0x180085667  test    rcx, rcx
0x18008566a  jz      short loc_180085673
0x18008566c  call    cs:__imp_CoTaskMemFree
0x180085672  nop
0x180085673  lea     rcx, [rsp+1D8h+var_168]
0x180085678  call    ??1?$_Tree@V?$_Tset_traits@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@U?$less@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@@std@@V?$allocator@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>::~_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>(void)
0x18008567d  nop
0x18008567e  lea     rcx, [rsp+1D8h+var_1A8]
0x180085683  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180085688  nop
0x180085689  test    rbx, rbx
0x18008568c  jz      short loc_18008569D
0x18008568e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180085692  mov     rdx, rbx; Timer
0x180085695  xor     ecx, ecx; TimerQueue
0x180085697  call    cs:__imp_DeleteTimerQueueTimer
0x18008569d  mov     eax, r14d
0x1800856a0  jmp     loc_1800859C4
0x1800856a5  xor     r8d, r8d
0x1800856a8  mov     rax, [rsp+1D8h+var_1A8]
0x1800856ad  mov     rax, [rax]
0x1800856b0  mov     rdi, [rsp+1D8h+pv]
0x1800856b5  cmp     rax, [rsp+1D8h+var_1A8]
0x1800856ba  jz      short loc_180085708
0x1800856bc  mov     ecx, [rax+1Ch]
0x1800856bf  mov     [rdi+r8*4], ecx
0x1800856c3  inc     r8d
0x1800856c6  mov     rcx, [rax+10h]
0x1800856ca  cmp     byte ptr [rcx+19h], 0
0x1800856ce  jz      short loc_1800856EE
0x1800856d0  mov     rcx, [rax+8]
0x1800856d4  jmp     short loc_1800856E3
0x1800856d6  cmp     rax, [rcx+10h]
0x1800856da  jnz     short loc_1800856E9
0x1800856dc  mov     rax, rcx
0x1800856df  mov     rcx, [rcx+8]
0x1800856e3  cmp     byte ptr [rcx+19h], 0
0x1800856e7  jz      short loc_1800856D6
0x1800856e9  mov     rax, rcx
0x1800856ec  jmp     short loc_1800856B5
0x1800856ee  mov     rdx, [rcx]
0x1800856f1  cmp     byte ptr [rdx+19h], 0
0x1800856f5  jnz     short loc_1800856E9
0x1800856f7  mov     rax, rdx
0x1800856fa  mov     rcx, [rdx]
0x1800856fd  mov     rdx, rcx
0x180085700  cmp     byte ptr [rcx+19h], 0
0x180085704  jz      short loc_1800856F7
0x180085706  jmp     short loc_1800856B5
0x180085708  lea     rcx, [rsp+1D8h+var_198]
0x18008570d  call    ??0?$vector@U_incompatibleDriver@@V?$allocator@U_incompatibleDriver@@@std@@@std@@QEAA@XZ; std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(void)
0x180085712  nop
0x180085713  lea     r15, [rsi+0D8h]
0x18008571a  mov     rcx, [r15+8]
0x18008571e  sub     rcx, [r15]
0x180085721  sar     rcx, 4
0x180085725  test    rcx, rcx
0x180085728  jz      loc_18008590E
0x18008572e  mov     eax, [rsi+0F4h]
0x180085734  cmp     rcx, rax
0x180085737  jz      loc_18008590E
0x18008573d  mov     rdx, r13
0x180085740  lea     rcx, [rsp+1D8h+var_158]
0x180085748  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x18008574d  mov     al, 1
0x18008574f  mov     [rsp+1D8h+var_148], al
0x180085756  test    al, al
0x180085758  jz      loc_180085841
0x18008575e  mov     rdx, r15
0x180085761  lea     rcx, [rsp+1D8h+var_198]
0x180085766  call    ??$HrStdCopyVector@UNetworkProtectionStatusSinkRecord@ShieldProvider@@@ShieldProvider@@YAJAEAV?$CStdVector@UNetworkProtectionStatusSinkRecord@ShieldProvider@@V?$allocator@UNetworkProtectionStatusSinkRecord@ShieldProvider@@@std@@@CommonUtil@@AEBV12@@Z; ShieldProvider::HrStdCopyVector<ShieldProvider::NetworkProtectionStatusSinkRecord>(CommonUtil::CStdVector<ShieldProvider::NetworkProtectionStatusSinkRecord,std::allocator<ShieldProvider::NetworkProtectionStatusSinkRecord>> &,CommonUtil::CStdVector<ShieldProvider::NetworkProtectionStatusSinkRecord,std::allocator<ShieldProvider::NetworkProtectionStatusSinkRecord>> const &)
0x18008576b  mov     r14d, eax
0x18008576e  test    eax, eax
0x180085770  jns     loc_180085833
0x180085776  lea     r15, WPP_GLOBAL_Control
0x18008577d  mov     rcx, cs:WPP_GLOBAL_Control
0x180085784  cmp     rcx, r15
0x180085787  jz      short loc_1800857A8
0x180085789  test    byte ptr [rcx+1Ch], 1
0x18008578d  jz      short loc_1800857A8
0x18008578f  mov     edx, 2Ah ; '*'
0x180085794  mov     r9d, eax
0x180085797  lea     r8, WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids
0x18008579e  mov     rcx, [rcx+10h]
0x1800857a2  call    WPP_SF_d
0x1800857a7  nop
0x1800857a8  lea     rcx, [rsp+1D8h+var_158]
0x1800857b0  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800857b5  nop
0x1800857b6  mov     rcx, qword ptr [rsp+1D8h+var_198]
0x1800857bb  test    rcx, rcx
0x1800857be  jz      short loc_1800857F2
0x1800857c0  mov     rdx, qword ptr [rsp+1D8h+var_198+8]
0x1800857c5  call    ??$_Destroy_range@V?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@std@@@std@@YAXPEAU_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@QEAU1234@AEAV?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@0@@Z; std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink *,WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink * const,std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink> &)
0x1800857ca  mov     rcx, qword ptr [rsp+1D8h+var_198]
0x1800857cf  mov     rdx, [rsp+1D8h+var_188]
0x1800857d4  sub     rdx, rcx
0x1800857d7  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800857db  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800857e0  xorps   xmm0, xmm0
0x1800857e3  movdqu  [rsp+1D8h+var_198], xmm0
0x1800857e9  mov     [rsp+1D8h+var_188], 0
0x1800857f2  test    rdi, rdi
0x1800857f5  jz      short loc_180085801
0x1800857f7  mov     rcx, rdi; pv
0x1800857fa  call    cs:__imp_CoTaskMemFree
0x180085800  nop
0x180085801  lea     rcx, [rsp+1D8h+var_168]
0x180085806  call    ??1?$_Tree@V?$_Tset_traits@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@U?$less@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@@std@@V?$allocator@V?$AutoRef@UIManagementStatusSink@@@CommonUtil@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>::~_Tree<std::_Tset_traits<CommonUtil::AutoRef<IManagementStatusSink>,std::less<CommonUtil::AutoRef<IManagementStatusSink>>,std::allocator<CommonUtil::AutoRef<IManagementStatusSink>>,0>>(void)
0x18008580b  nop
0x18008580c  lea     rcx, [rsp+1D8h+var_1A8]
0x180085811  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x180085816  nop
0x180085817  test    rbx, rbx
0x18008581a  jz      short loc_18008582B
0x18008581c  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180085820  mov     rdx, rbx; Timer
0x180085823  xor     ecx, ecx; TimerQueue
0x180085825  call    cs:__imp_DeleteTimerQueueTimer
0x18008582b  mov     eax, r14d
0x18008582e  jmp     loc_1800859C4
0x180085833  xor     al, al
0x180085835  mov     [rsp+1D8h+var_148], al
0x18008583c  jmp     loc_180085756
0x180085841  lea     rcx, [rsp+1D8h+var_158]
0x180085849  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x18008584e  mov     rsi, qword ptr [rsp+1D8h+var_198]
0x180085853  lea     r15, WPP_GLOBAL_Control
0x18008585a  mov     [rsp+1D8h+var_178], rsi
0x18008585f  cmp     rsi, qword ptr [rsp+1D8h+var_198+8]
0x180085864  jz      loc_180085915
0x18008586a  cmp     qword ptr [rsi+8], 0
0x18008586f  jz      loc_180085905
0x180085875  lea     r8, aShieldprovider_53; "ShieldProvider::ShieldManagementProvide"...
0x18008587c  mov     edx, 0BB8h; DueTime
0x180085881  lea     rcx, [rsp+1D8h+var_138]; this
0x180085889  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x18008588e  nop
0x18008588f  mov     rcx, [rsi+8]
0x180085893  mov     rax, [rcx]
0x180085896  mov     r8, rdi
0x180085899  mov     edx, r12d
0x18008589c  mov     rax, [rax+18h]
0x1800858a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858a5  nop
0x1800858a6  lea     rcx, [rsp+1D8h+var_138]; this
0x1800858ae  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800858b3  nop
0x1800858b4  jmp     short loc_1800858D6
0x1800858b6  lea     r15, WPP_GLOBAL_Control
0x1800858bd  mov     r14d, [rsp+1D8h+var_1B8]
0x1800858c2  mov     rbx, [rsp+1D8h+var_180]
0x1800858c7  mov     rdi, [rsp+1D8h+pv]
0x1800858cc  mov     r12d, [rsp+1D8h+var_170]
0x1800858d1  mov     rsi, [rsp+1D8h+var_178]
0x1800858d6  test    r14d, r14d
0x1800858d9  jns     short loc_180085905
0x1800858db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800858e2  cmp     rcx, r15
0x1800858e5  jz      short loc_180085905
0x1800858e7  test    byte ptr [rcx+1Ch], 2
0x1800858eb  jz      short loc_180085905
0x1800858ed  mov     edx, 2Bh ; '+'
0x1800858f2  mov     r9d, r14d
0x1800858f5  lea     r8, WPP_082fb507c5233e4aeca1f15f7ddff04e_Traceguids
0x1800858fc  mov     rcx, [rcx+10h]
0x180085900  call    WPP_SF_d
0x180085905  add     rsi, 10h
0x180085909  jmp     loc_18008585A
0x18008590e  lea     r15, WPP_GLOBAL_Control
0x180085915  mov     rcx, qword ptr [rsp+1D8h+var_198]
0x18008591a  test    rcx, rcx
0x18008591d  jz      short loc_180085940
0x18008591f  mov     rdx, qword ptr [rsp+1D8h+var_198+8]
0x180085924  call    ??$_Destroy_range@V?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@std@@@std@@YAXPEAU_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@QEAU1234@AEAV?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@0@@Z; std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink *,WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink * const,std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink> &)
0x180085929  mov     rcx, qword ptr [rsp+1D8h+var_198]
0x18008592e  mov     rdx, [rsp+1D8h+var_188]
0x180085933  sub     rdx, rcx
  ... truncated ...
```
