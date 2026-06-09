# DeferralRankingHelper::GetDishonoredDeferrals(Update const &,Action const &)

- ea: `0x140121524`
- end: `0x14012235c`
- name: `?GetDishonoredDeferrals@DeferralRankingHelper@@QEAA?AV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBVUpdate@@AEBVAction@@@Z`
- size: `3640`
- prototype: `__int64 __fastcall(DeferralRankingHelper *this)`
- caller_count: `1`
- callee_count: `35`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14008424c`

## callees

- `0x140029f9c`
- `0x140040184`
- `0x140042d04`
- `0x140043284`
- `0x140043504`
- `0x14004519c`
- `0x140045404`
- `0x1400454a0`
- `0x1400574cc`
- `0x140057a20`
- `0x140075a18`
- `0x1400aa8ac`
- `0x1400ad7e4`
- `0x1400d0f68`
- `0x1400d11ac`
- `0x1400d24bc`
- `0x1400d25f8`
- `0x1400d277c`
- `0x1400d8130`
- `0x1400fe9c0`
- `0x1400fea2c`
- `0x140104900`
- `0x140120ec4`
- `0x140121258`
- `0x140121524`
- `0x140122364`
- `0x1401225ac`
- `0x1401227b0`
- `0x140122a84`
- `0x14012d7d8`
- `0x140378e7c`
- `0x140378f6c`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140121964`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140121999`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401219e4`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140121a48`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140121964`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140121999`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401219e4`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140121a48`

## string_xrefs

- `0x1401222ff`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140122318`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140122331`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14012234a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140121d67`: `C:\__w\1\s\src\orchestrator\mostack\updatemanager\Threads.hpp`
- `0x14012208e`: `FeatureUpdate`
- `0x140122085`: `QualityUpdate`
- `0x1401216a1`: `C:\__w\1\s\src\orchestrator\mostack\updatemanager\Callback.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 *__fastcall DeferralRankingHelper::GetDishonoredDeferrals(
        DeferralRankingHelper *this,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rax
  const wchar_t *v10; // rax
  __int64 v11; // rcx
  __int64 System; // rax
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, const wchar_t **, _QWORD *); // rbx
  const char *traits_2_unsigned_short; // rax
  const char *v16; // r9
  __int64 v17; // r11
  __int64 v18; // rax
  int v19; // r12d
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  __int64 v22; // rbx
  __int128 *p_pExceptionObject; // rdx
  __int64 v24; // r9
  unsigned __int64 i; // rcx
  int v26; // ebx
  __int64 v27; // r15
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 PredictedActionDeferredDuration; // rax
  int v31; // eax
  double v32; // xmm10_8
  double v33; // xmm8_8
  double v34; // xmm6_8
  __int16 *v35; // rax
  const char *v36; // r9
  __int64 v37; // r11
  __int64 v38; // rax
  signed __int64 v39; // r15
  signed __int64 v40; // rdx
  __int128 v41; // rax
  _QWORD *v42; // rbx
  _QWORD *DiscoveryTime; // rbx
  double v44; // xmm9_8
  DeferralRankingHelper *v45; // rcx
  double DeferralEligibilityRatio; // xmm7_8
  __int64 v47; // rcx
  double v48; // xmm0_8
  __int64 v49; // rax
  __int64 v50; // rax
  char v51; // bl
  int v52; // r15d
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 (__fastcall *v55)(__int64, const wchar_t **, _QWORD *); // rbx
  __int16 *v56; // rax
  const char *v57; // r9
  __int64 v58; // r11
  __int64 v59; // rax
  int v60; // r12d
  volatile signed __int32 *v61; // rbx
  volatile signed __int32 *v62; // rbx
  __int64 v63; // rax
  const char *v64; // r9
  __int64 v65; // r11
  __int64 v66; // rax
  __int64 v67; // rbx
  __int64 v68; // rax
  __int64 **v69; // r12
  __int64 *v70; // rbx
  __int64 *v71; // r15
  char v72; // al
  __int64 *v73; // rcx
  __int64 v74; // rax
  const wchar_t *v75; // rdx
  size_t v76; // r8
  const wchar_t *v77; // rdx
  const wchar_t *v78; // rcx
  _QWORD *v79; // rax
  double v80; // xmm7_8
  wchar_t **v81; // rax
  _QWORD *v82; // r12
  int v83; // eax
  int v84; // eax
  int v85; // eax
  const wchar_t *v86; // rbx
  __int64 v87; // r15
  wchar_t **v88; // rax
  size_t v89; // rdx
  volatile signed __int32 *v90; // rbx
  volatile signed __int32 *v91; // rbx
  wchar_t **v92; // rax
  void *v93; // rax
  __int64 v94; // rax
  __int64 v95; // rcx
  _QWORD v96[2]; // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *v97; // [rsp+78h] [rbp-90h] BYREF
  __int64 v98; // [rsp+80h] [rbp-88h]
  __int128 pExceptionObject; // [rsp+88h] [rbp-80h] BYREF
  __int128 v100; // [rsp+98h] [rbp-70h]
  wchar_t **v101; // [rsp+A8h] [rbp-60h] BYREF
  size_t v102; // [rsp+B0h] [rbp-58h]
  __int128 v103; // [rsp+B8h] [rbp-50h] BYREF
  signed __int64 v104; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v105; // [rsp+D0h] [rbp-38h]
  __int128 v106; // [rsp+E8h] [rbp-20h] BYREF
  char v107[8]; // [rsp+F8h] [rbp-10h] BYREF
  volatile signed __int32 *v108; // [rsp+100h] [rbp-8h]
  _BYTE v109[32]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v110[32]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v111[32]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v112[32]; // [rsp+178h] [rbp+70h] BYREF
  __int128 v113; // [rsp+198h] [rbp+90h] BYREF
  wchar_t *S2[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  size_t N; // [rsp+1B8h] [rbp+B0h]
  unsigned __int64 v116; // [rsp+1C0h] [rbp+B8h]
  __int128 v117; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v118; // [rsp+1D8h] [rbp+D0h]
  wchar_t S1[8]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int128 v120; // [rsp+1F8h] [rbp+F0h]
  __int128 v121; // [rsp+208h] [rbp+100h] BYREF
  __int128 v122; // [rsp+218h] [rbp+110h]
  wchar_t *v123; // [rsp+228h] [rbp+120h] BYREF
  char v124[8]; // [rsp+230h] [rbp+128h] BYREF
  __int64 v125; // [rsp+238h] [rbp+130h]
  unsigned __int64 v126; // [rsp+240h] [rbp+138h] BYREF
  char v127; // [rsp+248h] [rbp+140h]
  wil::details::in1diag3 *retaddr; // [rsp+310h] [rbp+208h]

  v97 = (const wchar_t *)a2;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a4 + 176LL))(a4) )
  {
    v117 = 0;
    v118 = 0;
    v10 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a4 + 8LL))(a4, v107);
    v11 = *((_QWORD *)v10 + 2);
    if ( *((_QWORD *)v10 + 3) > 7u )
      v10 = *(const wchar_t **)v10;
    v97 = v10;
    v98 = v11;
    DeferralRankingHelper::GetActionDeferralRanking(this);
    std::wstring::~wstring(v107);
    System = SystemInterface::Providers::GetSystem(&v103);
    v13 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    v14 = *(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, wchar_t ***))(*(_QWORD *)v13 + 40LL))(
                                                                                         v13,
                                                                                         &v101)
                                                                        + 56LL);
    LODWORD(v96[0]) = 33;
    traits_2_unsigned_short = (const char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                              L"TLD-DownloadTimeThresholdPercentage",
                                              "C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\Callback.cpp",
                                              0);
    if ( traits_2_unsigned_short == "C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\Callback.cpp"
      || (v18 = (traits_2_unsigned_short - (const char *)L"TLD-DownloadTimeThresholdPercentage") >> 1, v18 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v16);
    }
    v97 = L"TLD-DownloadTimeThresholdPercentage";
    v98 = v18;
    v19 = v14(v17, &v97, v96);
    v20 = (volatile signed __int32 *)v102;
    if ( v102 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v102 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v21 = (volatile signed __int32 *)*((_QWORD *)&v103 + 1);
    if ( *((_QWORD *)&v103 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v103 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    v22 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)a3 + 648LL))(a3, &v123);
    pExceptionObject = 0;
    v100 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&pExceptionObject, L"Opportunistic", 13);
    p_pExceptionObject = &pExceptionObject;
    if ( *((_QWORD *)&v100 + 1) > 7u )
      p_pExceptionObject = (__int128 *)pExceptionObject;
    v24 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * (__int64)v100; ++i )
      v24 = 0x100000001B3LL * (*((unsigned __int8 *)p_pExceptionObject + i) ^ (unsigned __int64)v24);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
      v22,
      &v101,
      &pExceptionObject,
      v24);
    if ( !v102 )
      std::_Xout_of_range("invalid unordered_map<K, T> key");
    v26 = *(_DWORD *)(v102 + 48);
    std::wstring::~wstring(&pExceptionObject);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(&v126);
    std::list<std::pair<std::wstring const,std::chrono::duration<int,std::ratio<60,1>>>>::~list<std::pair<std::wstring const,std::chrono::duration<int,std::ratio<60,1>>>>(v124);
    v27 = *(_QWORD *)this;
    v28 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a4 + 8LL))(a4, &pExceptionObject);
    v29 = v28[2];
    if ( v28[3] > 7u )
      v28 = (_QWORD *)*v28;
    v104 = (signed __int64)v28;
    v105 = v29;
    PredictedActionDeferredDuration = UpdateDatabase::GetPredictedActionDeferredDuration(v27, &v97, &v104);
    if ( *(_BYTE *)(PredictedActionDeferredDuration + 4) )
      v31 = *(_DWORD *)PredictedActionDeferredDuration;
    else
      v31 = 200;
    v32 = (double)v31;
    std::wstring::~wstring(&pExceptionObject);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a4 + 16LL))(a4) == 1
      || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a4 + 16LL))(a4) == 7 )
    {
      v33 = DOUBLE_100_0;
      v34 = (double)(v19 * v26) / 100.0;
      DiscoveryTime = (_QWORD *)UpdateDatabase::GetDiscoveryTime(*(_QWORD *)this, &v97, a3);
      v96[0] = 0;
      GetSystemTimePreciseAsFileTime(v96);
      v41 = (__int64)(((unsigned __int64)HIDWORD(v96[0]) << 32) - *DiscoveryTime - 116444736000000000LL + LODWORD(v96[0]))
          * (__int128)0x1CA213D840BAF7D5LL;
    }
    else
    {
      v33 = DOUBLE_100_0;
      v34 = (double)v26 - (double)(v19 * v26) / 100.0;
      v35 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Download",
                         word_1403FDDF2,
                         0);
      if ( v35 == word_1403FDDF2 || (v38 = ((char *)v35 - (char *)L"Download") >> 1, v38 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v36);
      v97 = L"Download";
      v98 = v38;
      UpdateDatabase::GetActionCompleteTimeByActionName(v37, &v104, a3, &v97);
      if ( (_BYTE)v105
        && (v96[0] = 0,
            GetSystemTimePreciseAsFileTime(v96),
            v39 = v104,
            v104 < (__int64)(LODWORD(v96[0]) + ((unsigned __int64)HIDWORD(v96[0]) << 32) - 116444736000000000LL)) )
      {
        v96[0] = 0;
        GetSystemTimePreciseAsFileTime(v96);
        v40 = LODWORD(v96[0]) + ((unsigned __int64)HIDWORD(v96[0]) << 32) - v39 - 116444736000000000LL;
      }
      else
      {
        v42 = (_QWORD *)UpdateDatabase::GetDiscoveryTime(*(_QWORD *)this, &v97, a3);
        v96[0] = 0;
        GetSystemTimePreciseAsFileTime(v96);
        v40 = LODWORD(v96[0]) + ((unsigned __int64)HIDWORD(v96[0]) << 32) - *v42 - 116444736000000000LL;
      }
      v41 = v40 * (__int128)0x1CA213D840BAF7D5LL;
    }
    v44 = (double)(int)((*((_QWORD *)&v41 + 1) >> 63) + (*((__int64 *)&v41 + 1) >> 26));
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 640LL))(a3) )
      DeferralEligibilityRatio = DOUBLE_1_0;
    else
      DeferralEligibilityRatio = DeferralRankingHelper::GetDeferralEligibilityRatio(v45, v34, v32, v44);
    v47 = (__int64)(*((_QWORD *)&v117 + 1) - v117) >> 5;
    if ( v47 < 0 )
    {
      v49 = ((__int64)(*((_QWORD *)&v117 + 1) - v117) >> 5) & 1 | ((unsigned __int64)v47 >> 1);
      v48 = (double)(int)v49 + (double)(int)v49;
    }
    else
    {
      v48 = (double)(int)v47;
    }
    floor(v48 * DeferralEligibilityRatio);
    v113 = 0;
    v50 = std::_Allocate<16,std::_Default_allocate_traits>(64);
    *(_QWORD *)v50 = v50;
    *(_QWORD *)(v50 + 8) = v50;
    *(_QWORD *)(v50 + 16) = v50;
    *(_WORD *)(v50 + 24) = 257;
    *(_QWORD *)&v113 = v50;
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_range_unchecked<std::wstring const *,std::wstring const *>(&v113);
    pExceptionObject = 0;
    v100 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&pExceptionObject, L"DelayDueToUserLogon", 19);
    v51 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::contains(
            &v113,
            &pExceptionObject);
    std::wstring::~wstring(&pExceptionObject);
    if ( v51 )
    {
      UpdateDatabase::GetUpdateActionDelayDetails(*(_QWORD *)this, &pExceptionObject, a3);
      if ( (_BYTE)v100 )
      {
        v52 = pExceptionObject;
        if ( (int)pExceptionObject < 0 )
        {
          pExceptionObject = 0;
          *(_QWORD *)&v100 = 0;
          Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&pExceptionObject);
          throw (gsl::narrowing_error *)&pExceptionObject;
        }
      }
      else
      {
        v52 = 0;
      }
      v53 = SystemInterface::Providers::GetSystem(&v103);
      v54 = *(_QWORD *)v53 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v53 + 8LL) + 4LL);
      v55 = *(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, wchar_t ***))(*(_QWORD *)v54 + 40LL))(
                                                                                           v54,
                                                                                           &v101)
                                                                          + 56LL);
      LODWORD(v96[0]) = 3;
      v56 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"TLD-LogonDeferralDishonorThreshold",
                         &word_140414D56,
                         0);
      if ( v56 == &word_140414D56
        || (v59 = ((char *)v56 - (char *)L"TLD-LogonDeferralDishonorThreshold") >> 1, v59 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v57);
      }
      v97 = L"TLD-LogonDeferralDishonorThreshold";
      v98 = v59;
      v60 = v55(v58, &v97, v96);
      v61 = (volatile signed __int32 *)v102;
      if ( v102 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v102 + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
          if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
        }
      }
      v62 = (volatile signed __int32 *)*((_QWORD *)&v103 + 1);
      if ( *((_QWORD *)&v103 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v103 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
          if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
        }
      }
      if ( v52 < v60 )
      {
        pExceptionObject = 0;
        v100 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&pExceptionObject, L"DelayDueToUserLogon", 19);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
          &v113,
          &pExceptionObject);
        std::wstring::~wstring(&pExceptionObject);
      }
    }
    v63 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L",",
            "C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\Threads.hpp",
            0);
    if ( v63 == v65 || (v66 = (v63 - (__int64)L",") >> 1, v66 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v64);
    v97 = L",";
    v98 = v66;
    Strings::join<std::set<std::wstring>>(S2, &v113, &v97);
    v67 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a4 + 8LL))(a4, v110);
    v68 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a3 + 24LL))(a3, v109);
    *(_OWORD *)S1 = 0;
    v120 = 0;
    *(_OWORD *)S1 = *(_OWORD *)v67;
    v120 = *(_OWORD *)(v67 + 16);
    *(_QWORD *)(v67 + 24) = 7;
    *(_WORD *)v67 = 0;
    *(_QWORD *)(v67 + 16) = 0;
    v121 = 0;
    v122 = 0;
    v121 = *(_OWORD *)v68;
    v122 = *(_OWORD *)(v68 + 16);
    *(_WORD *)v68 = 0;
    *(_QWORD *)(v68 + 16) = 0;
    *(_QWORD *)(v68 + 24) = 7;
    std::wstring::~wstring(v109);
    std::wstring::~wstring(v110);
    v69 = (__int64 **)((char *)this + 152);
    v70 = (__int64 *)*((_QWORD *)this + 19);
    v71 = (__int64 *)v70[1];
    HIDWORD(pExceptionObject) = 0;
    if ( !*((_BYTE *)v71 + 25) )
    {
      do
      {
        v72 = *(_BYTE *)std::tuple<std::wstring,std::wstring>::_Three_way_compare<std::wstring,std::wstring>((wchar_t *)v71 + 16);
        if ( v72 >= 0 )
          v70 = v71;
        v73 = v71 + 2;
        if ( v72 >= 0 )
          v73 = v71;
        v71 = (__int64 *)*v73;
      }
      while ( !*(_BYTE *)(*v73 + 25) );
      v69 = (__int64 **)((char *)this + 152);
    }
    if ( *((_BYTE *)v70 + 25)
      || *(char *)std::tuple<std::wstring,std::wstring>::_Three_way_compare<std::wstring,std::wstring>(S1) < 0
      || v70 == *v69 )
    {
      goto LABEL_78;
    }
    v74 = std::map<std::tuple<std::wstring,std::wstring>,std::wstring>::operator[](v69, S1);
    v75 = (const wchar_t *)S2;
    if ( v116 > 7 )
      v75 = S2[0];
    v76 = *(_QWORD *)(v74 + 16);
    if ( *(_QWORD *)(v74 + 24) > 7u )
      v74 = *(_QWORD *)v74;
    if ( v76 != N || v76 && wmemcmp((const wchar_t *)v74, v75, v76) )
    {
LABEL_78:
      UpdateDatabase::GetUpdateActionDishonoredDeferrals(*(_QWORD *)this, &v123, a3, a4);
      if ( !v127 )
        goto LABEL_86;
      v77 = (const wchar_t *)&v123;
      if ( v126 > 7 )
        v77 = v123;
      v78 = (const wchar_t *)S2;
      if ( v116 > 7 )
        v78 = S2[0];
      if ( N != v125 || N && wmemcmp(v78, v77, N) )
      {
LABEL_86:
        v79 = (_QWORD *)SystemInterface::Providers::GetSystem(&pExceptionObject);
        v104 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v79 + 40LL))(*v79, v107);
        v97 = *(const wchar_t **)(*(_QWORD *)v104 + 256LL);
        v80 = round(DeferralEligibilityRatio * v33) / v33;
        v81 = S2;
        if ( v116 > 7 )
          v81 = (wchar_t **)S2[0];
        *(_QWORD *)&v103 = v81;
        *((_QWORD *)&v103 + 1) = N;
        v82 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a4 + 8LL))(a4, v112);
        v96[0] = v82[2];
        if ( v82[3] > 7u )
          v82 = (_QWORD *)*v82;
        v83 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 40LL))(a3);
        if ( v83 )
        {
          v84 = v83 - 1;
          if ( v84 )
          {
            v85 = v84 - 1;
            if ( v85 )
            {
              if ( v85 == 1 )
                v86 = L"MinorImpact";
              else
                v86 = L"Other";
            }
            else
            {
              v86 = L"Driver";
            }
          }
          else
          {
            v86 = L"QualityUpdate";
          }
        }
        else
        {
          v86 = L"FeatureUpdate";
        }
        v87 = -1;
        do
          ++v87;
        while ( v86[v87] );
        v88 = (wchar_t **)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a3 + 24LL))(a3, v111);
        v89 = (size_t)v88[2];
        if ( (unsigned __int64)v88[3] > 7 )
          v88 = (wchar_t **)*v88;
        v106 = v103;
        *(_QWORD *)&v103 = v82;
        *((_QWORD *)&v103 + 1) = v96[0];
        v96[0] = v86;
        v96[1] = v87;
        v101 = v88;
        v102 = v89;
        ((void (__fastcall *)(signed __int64, wchar_t ***, _QWORD *, __int128 *, __int128 *, _QWORD, _QWORD, _QWORD, _QWORD))v97)(
          v104,
          &v101,
          v96,
          &v103,
          &v106,
          *(_QWORD *)&v34,
          *(_QWORD *)&v44,
          *(_QWORD *)&v32,
          *(_QWORD *)&v80);
        std::wstring::~wstring(v111);
        std::wstring::~wstring(v112);
        v90 = v108;
        if ( v108 )
        {
          if ( _InterlockedExchangeAdd(v108 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
            if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
          }
        }
        v91 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject + 1);
        if ( *((_QWORD *)&pExceptionObject + 1) )
        {
          if ( _InterlockedExchangeAdd(
                 (volatile signed __int32 *)(*((_QWORD *)&pExceptionObject + 1) + 8LL),
                 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v91)(v91);
            if ( _InterlockedExchangeAdd(v91 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v91 + 8LL))(v91);
          }
        }
        v92 = S2;
        if ( v116 > 7 )
          v92 = (wchar_t **)S2[0];
        v101 = v92;
        v102 = N;
        UpdateDatabase::SetUpdateActionDishonoredDeferrals(*(_QWORD *)this, a3, a4, &v101);
        v93 = (void *)std::map<std::tuple<std::wstring,std::wstring>,std::wstring>::operator[]((char *)this + 152, S1);
        std::wstring::operator=(v93);
      }
      if ( v127 )
        std::wstring::~wstring(&v123);
    }
    *a2 = 0;
    a2[1] = 0;
    v94 = std::_Allocate<16,std::_Default_allocate_traits>(64);
    *(_QWORD *)v94 = v94;
    *(_QWORD *)(v94 + 8) = v94;
    *(_QWORD *)(v94 + 16) = v94;
    *(_WORD *)(v94 + 24) = 257;
    *a2 = v113;
    *(_QWORD *)&v113 = v94;
    v95 = a2[1];
    a2[1] = *((_QWORD *)&v113 + 1);
    *((_QWORD *)&v113 + 1) = v95;
    std::wstring::~wstring(&v121);
    std::wstring::~wstring(S1);
    std::wstring::~wstring(S2);
    std::_Tree<std::_Tset_traits<std::wstring,case_insensitive_less,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,case_insensitive_less,std::allocator<std::wstring>,0>>(&v113);
    std::vector<std::filesystem::path>::_Tidy(&v117);
  }
  else
  {
    *a2 = 0;
    a2[1] = 0;
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(64);
    *(_QWORD *)v8 = v8;
    *(_QWORD *)(v8 + 8) = v8;
    *(_QWORD *)(v8 + 16) = v8;
    *(_WORD *)(v8 + 24) = 257;
    *a2 = v8;
  }
  return a2;
}

```

## disassembly

```asm
0x140121524  mov     rax, rsp
0x140121527  mov     [rax+10h], rdx
0x14012152b  push    rbp
0x14012152c  push    rbx
0x14012152d  push    rsi
0x14012152e  push    rdi
0x14012152f  push    r12
0x140121531  push    r13
0x140121533  push    r14
0x140121535  push    r15
0x140121537  lea     rbp, [rax-208h]
0x14012153e  sub     rsp, 2C8h
0x140121545  movaps  xmmword ptr [rax-58h], xmm6
0x140121549  movaps  xmmword ptr [rax-68h], xmm7
0x14012154d  movaps  xmmword ptr [rax-78h], xmm8
0x140121552  movaps  xmmword ptr [rax-88h], xmm9
0x14012155a  movaps  xmmword ptr [rax-98h], xmm10
0x140121562  mov     rax, cs:__security_cookie
0x140121569  xor     rax, rsp
0x14012156c  mov     [rbp+200h+var_A0], rax
0x140121573  mov     rsi, r9
0x140121576  mov     r14, r8
0x140121579  mov     rdi, rdx
0x14012157c  mov     r13, rcx
0x14012157f  mov     [rsp+300h+var_290], rdx
0x140121584  xor     ebx, ebx
0x140121586  mov     rax, [r9]
0x140121589  mov     rcx, r9
0x14012158c  mov     rax, [rax+0B0h]
0x140121593  call    _guard_dispatch_icall
0x140121598  test    al, al
0x14012159a  jnz     short loc_140121602
0x14012159c  mov     [rdi], rbx
0x14012159f  mov     [rdi+8], rbx
0x1401215a3  lea     ecx, [rbx+40h]
0x1401215a6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1401215ab  mov     [rax], rax
0x1401215ae  mov     [rax+8], rax
0x1401215b2  mov     [rax+10h], rax
0x1401215b6  mov     word ptr [rax+18h], 101h
0x1401215bc  mov     [rdi], rax
0x1401215bf  mov     rax, rdi
0x1401215c2  mov     rcx, [rbp+200h+var_A0]
0x1401215c9  xor     rcx, rsp; StackCookie
0x1401215cc  call    __security_check_cookie
0x1401215d1  lea     r11, [rsp+300h+var_38]
0x1401215d9  movaps  xmm6, xmmword ptr [r11-18h]
0x1401215de  movaps  xmm7, xmmword ptr [r11-28h]
0x1401215e3  movaps  xmm8, xmmword ptr [r11-38h]
0x1401215e8  movaps  xmm9, xmmword ptr [r11-48h]
0x1401215ed  movaps  xmm10, xmmword ptr [r11-58h]
0x1401215f2  mov     rsp, r11
0x1401215f5  pop     r15
0x1401215f7  pop     r14
0x1401215f9  pop     r13
0x1401215fb  pop     r12
0x1401215fd  pop     rdi
0x1401215fe  pop     rsi
0x1401215ff  pop     rbx
0x140121600  pop     rbp
0x140121601  retn
0x140121602  xorps   xmm0, xmm0
0x140121605  xor     eax, eax
0x140121607  movups  [rbp+200h+var_140], xmm0
0x14012160e  mov     [rbp+200h+var_130], rax
0x140121615  mov     rax, [rsi]
0x140121618  lea     rdx, [rbp+200h+var_210]
0x14012161c  mov     rcx, rsi
0x14012161f  mov     rax, [rax+8]
0x140121623  call    _guard_dispatch_icall
0x140121628  nop
0x140121629  mov     rcx, [rax+10h]
0x14012162d  cmp     qword ptr [rax+18h], 7
0x140121632  jbe     short loc_140121637
0x140121634  mov     rax, [rax]
0x140121637  mov     [rsp+300h+var_290], rax
0x14012163c  mov     [rsp+300h+var_288], rcx
0x140121641  lea     r8, [rsp+300h+var_290]
0x140121646  lea     rdx, [rbp+200h+var_140]
0x14012164d  mov     rcx, r13; this
0x140121650  call    ?GetActionDeferralRanking@DeferralRankingHelper@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$basic_zstring_view@_W@wil@@@Z; DeferralRankingHelper::GetActionDeferralRanking(wil::basic_zstring_view<wchar_t>)
0x140121655  nop
0x140121656  lea     rcx, [rbp+200h+var_210]
0x14012165a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14012165f  lea     rcx, [rbp+200h+var_250]
0x140121663  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140121668  nop
0x140121669  mov     rdx, [rax]
0x14012166c  mov     rax, [rdx+8]
0x140121670  movsxd  rcx, dword ptr [rax+4]
0x140121674  add     rdx, 8
0x140121678  add     rcx, rdx
0x14012167b  mov     rax, [rcx]
0x14012167e  lea     rdx, [rbp+200h+var_260]
0x140121682  mov     rax, [rax+28h]
0x140121686  call    _guard_dispatch_icall
0x14012168b  nop
0x14012168c  mov     r11, [rax]
0x14012168f  mov     rax, [r11]
0x140121692  mov     rbx, [rax+38h]
0x140121696  mov     dword ptr [rsp+300h+var_2A0], 21h ; '!'
0x14012169e  xor     r8d, r8d
0x1401216a1  lea     r15, aCW1SSrcOrchest_6; "C:\\__w\\1\\s\\src\\orchestrator\\mosta"...
0x1401216a8  mov     rdx, r15
0x1401216ab  lea     r12, aTldDownloadtim; "TLD-DownloadTimeThresholdPercentage"
0x1401216b2  mov     rcx, r12
0x1401216b5  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1401216ba  cmp     rax, r15
0x1401216bd  jz      loc_1401222F8
0x1401216c3  sub     rax, r12
0x1401216c6  sar     rax, 1
0x1401216c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401216cd  jz      loc_1401222F8
0x1401216d3  mov     [rsp+300h+var_290], r12
0x1401216d8  mov     [rsp+300h+var_288], rax
0x1401216dd  lea     r8, [rsp+300h+var_2A0]
0x1401216e2  lea     rdx, [rsp+300h+var_290]
0x1401216e7  mov     rcx, r11
0x1401216ea  mov     rax, rbx
0x1401216ed  call    _guard_dispatch_icall
0x1401216f2  mov     r12d, eax
0x1401216f5  mov     rbx, [rbp+200h+var_258]
0x1401216f9  xor     r15d, r15d
0x1401216fc  test    rbx, rbx
0x1401216ff  jz      short loc_140121739
0x140121701  or      ecx, 0FFFFFFFFh
0x140121704  lock xadd [rbx+8], ecx
0x140121709  cmp     ecx, 1
0x14012170c  jnz     short loc_140121739
0x14012170e  mov     rdx, [rbx]
0x140121711  mov     rcx, rbx
0x140121714  mov     rax, [rdx]
0x140121717  call    _guard_dispatch_icall
0x14012171c  or      eax, 0FFFFFFFFh
0x14012171f  lock xadd [rbx+0Ch], eax
0x140121724  cmp     eax, 1
0x140121727  jnz     short loc_140121739
0x140121729  mov     rax, [rbx]
0x14012172c  mov     rcx, rbx
0x14012172f  mov     rax, [rax+8]
0x140121733  call    _guard_dispatch_icall
0x140121738  nop
0x140121739  mov     rbx, qword ptr [rbp+200h+var_250+8]
0x14012173d  test    rbx, rbx
0x140121740  jz      short loc_140121779
0x140121742  or      eax, 0FFFFFFFFh
0x140121745  lock xadd [rbx+8], eax
0x14012174a  cmp     eax, 1
0x14012174d  jnz     short loc_140121779
0x14012174f  mov     rax, [rbx]
0x140121752  mov     rcx, rbx
0x140121755  mov     rax, [rax]
0x140121758  call    _guard_dispatch_icall
0x14012175d  or      eax, 0FFFFFFFFh
0x140121760  lock xadd [rbx+0Ch], eax
0x140121765  cmp     eax, 1
0x140121768  jnz     short loc_140121779
0x14012176a  mov     rax, [rbx]
0x14012176d  mov     rcx, rbx
0x140121770  mov     rax, [rax+8]
0x140121774  call    _guard_dispatch_icall
0x140121779  mov     rax, [r14]
0x14012177c  lea     rdx, [rbp+200h+var_E0]
0x140121783  mov     rcx, r14
0x140121786  mov     rax, [rax+288h]
0x14012178d  call    _guard_dispatch_icall
0x140121792  mov     rbx, rax
0x140121795  xorps   xmm0, xmm0
0x140121798  movups  [rbp+200h+pExceptionObject], xmm0
0x14012179c  xorps   xmm1, xmm1
0x14012179f  movdqu  [rbp+200h+var_270], xmm1
0x1401217a4  mov     r8d, 0Dh
0x1401217aa  lea     rdx, aOpportunistic; "Opportunistic"
0x1401217b1  lea     rcx, [rbp+200h+pExceptionObject]
0x1401217b5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1401217ba  nop
0x1401217bb  lea     rdx, [rbp+200h+pExceptionObject]
0x1401217bf  cmp     qword ptr [rbp+200h+var_270+8], 7
0x1401217c4  cmova   rdx, qword ptr [rbp+200h+pExceptionObject]
0x1401217c9  mov     r9, 0CBF29CE484222325h
0x1401217d3  mov     rax, qword ptr [rbp+200h+var_270]
0x1401217d7  lea     r8, [rax+rax]
0x1401217db  mov     rcx, r15
0x1401217de  test    r8, r8
0x1401217e1  jz      short loc_140121800
0x1401217e3  movzx   eax, byte ptr [rcx+rdx]
0x1401217e7  xor     r9, rax
0x1401217ea  mov     r10, 100000001B3h
0x1401217f4  imul    r9, r10
0x1401217f8  inc     rcx
0x1401217fb  cmp     rcx, r8
0x1401217fe  jb      short loc_1401217E3
0x140121800  lea     r8, [rbp+200h+pExceptionObject]
0x140121804  lea     rdx, [rbp+200h+var_260]
0x140121808  mov     rcx, rbx
0x14012180b  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x140121810  mov     rbx, [rbp+200h+var_258]
0x140121814  test    rbx, rbx
0x140121817  jz      loc_1401222C4
0x14012181d  mov     ebx, [rbx+30h]
0x140121820  lea     rcx, [rbp+200h+pExceptionObject]
0x140121824  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140121829  nop
0x14012182a  lea     rcx, [rbp+200h+var_C8]
0x140121831  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@Vpath@filesystem@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::filesystem::path>>,std::_Iterator_base0>>>(void)
0x140121836  lea     rcx, [rbp+200h+var_D8]
0x14012183d  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@2@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::wstring const,std::chrono::duration<int,std::ratio<60,1>>>>::~list<std::pair<std::wstring const,std::chrono::duration<int,std::ratio<60,1>>>>(void)
0x140121842  mov     r15, [r13+0]
0x140121846  mov     rax, [rsi]
0x140121849  lea     rdx, [rbp+200h+pExceptionObject]
0x14012184d  mov     rcx, rsi
0x140121850  mov     rax, [rax+8]
0x140121854  call    _guard_dispatch_icall
0x140121859  nop
0x14012185a  mov     rcx, [rax+10h]
0x14012185e  cmp     qword ptr [rax+18h], 7
0x140121863  jbe     short loc_140121868
0x140121865  mov     rax, [rax]
0x140121868  mov     [rbp+200h+var_240], rax
0x14012186c  mov     [rbp+200h+var_238], rcx
0x140121870  lea     r8, [rbp+200h+var_240]
0x140121874  lea     rdx, [rsp+300h+var_290]
0x140121879  mov     rcx, r15
0x14012187c  call    ?GetPredictedActionDeferredDuration@UpdateDatabase@@QEBA?AV?$optional@I@std@@V?$basic_zstring_view@_W@wil@@@Z; UpdateDatabase::GetPredictedActionDeferredDuration(wil::basic_zstring_view<wchar_t>)
0x140121881  cmp     byte ptr [rax+4], 0
0x140121885  jz      short loc_14012188B
0x140121887  mov     eax, [rax]
0x140121889  jmp     short loc_140121890
0x14012188b  mov     eax, 0C8h
0x140121890  xorps   xmm10, xmm10
0x140121894  cvtsi2sd xmm10, rax
0x140121899  lea     rcx, [rbp+200h+pExceptionObject]
0x14012189d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1401218a2  mov     rax, [rsi]
0x1401218a5  mov     rcx, rsi
0x1401218a8  mov     rax, [rax+10h]
0x1401218ac  call    _guard_dispatch_icall
0x1401218b1  cmp     eax, 1
0x1401218b4  jz      loc_140121A0B
0x1401218ba  mov     rax, [rsi]
0x1401218bd  mov     rcx, rsi
0x1401218c0  mov     rax, [rax+10h]
0x1401218c4  call    _guard_dispatch_icall
0x1401218c9  cmp     eax, 7
0x1401218cc  jz      loc_140121A0B
0x1401218d2  movd    xmm6, ebx
0x1401218d6  cvtdq2pd xmm6, xmm6
0x1401218da  imul    ebx, r12d
0x1401218de  mov     eax, ebx
0x1401218e0  xorps   xmm0, xmm0
0x1401218e3  cvtsi2sd xmm0, rax
0x1401218e8  movsd   xmm8, cs:__real@4059000000000000
0x1401218f1  divsd   xmm0, xmm8
0x1401218f6  subsd   xmm6, xmm0
0x1401218fa  mov     r11, [r13+0]
0x1401218fe  xor     r8d, r8d
0x140121901  lea     rbx, word_1403FDDF2
0x140121908  mov     rdx, rbx
0x14012190b  lea     r15, aDownload_1; "Download"
0x140121912  mov     rcx, r15
0x140121915  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14012191a  cmp     rax, rbx
0x14012191d  jz      loc_140122311
0x140121923  sub     rax, r15
0x140121926  sar     rax, 1
0x140121929  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14012192d  jz      loc_140122311
0x140121933  mov     [rsp+300h+var_290], r15
0x140121938  mov     [rsp+300h+var_288], rax
0x14012193d  lea     r9, [rsp+300h+var_290]
0x140121942  mov     r8, r14
0x140121945  lea     rdx, [rbp+200h+var_240]
0x140121949  mov     rcx, r11
0x14012194c  call    ?GetActionCompleteTimeByActionName@UpdateDatabase@@QEBA?AV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@AEBVUpdate@@V?$basic_zstring_view@_W@wil@@@Z; UpdateDatabase::GetActionCompleteTimeByActionName(Update const &,wil::basic_zstring_view<wchar_t>)
0x140121951  xor     r12d, r12d
0x140121954  cmp     byte ptr [rbp+200h+var_238], r12b
0x140121958  jz      short loc_1401219C6
0x14012195a  mov     [rsp+300h+var_2A0], r12
0x14012195f  lea     rcx, [rsp+300h+var_2A0]
0x140121964  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x14012196a  mov     edx, dword ptr [rsp+300h+var_2A0+4]
0x14012196e  shl     rdx, 20h
0x140121972  mov     ecx, dword ptr [rsp+300h+var_2A0]
0x140121976  mov     rbx, 0FE624E212AC18000h
0x140121980  add     rdx, rbx
0x140121983  add     rdx, rcx
0x140121986  mov     r15, [rbp+200h+var_240]
0x14012198a  cmp     r15, rdx
0x14012198d  jge     short loc_1401219C6
0x14012198f  mov     [rsp+300h+var_2A0], r12
0x140121994  lea     rcx, [rsp+300h+var_2A0]
0x140121999  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x14012199f  mov     edx, dword ptr [rsp+300h+var_2A0+4]
0x1401219a3  shl     rdx, 20h
0x1401219a7  sub     rdx, r15
0x1401219aa  mov     ecx, dword ptr [rsp+300h+var_2A0]
0x1401219ae  add     rdx, rbx
0x1401219b1  add     rdx, rcx
0x1401219b4  mov     rax, 1CA213D840BAF7D5h
0x1401219be  imul    rdx
  ... truncated ...
```
