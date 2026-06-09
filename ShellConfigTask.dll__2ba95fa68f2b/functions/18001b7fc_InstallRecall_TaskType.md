# InstallRecall(TaskType)

- ea: `0x18001b7fc`
- end: `0x18001bda1`
- name: `?InstallRecall@@YAJW4TaskType@@@Z`
- size: `1445`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001dac8`
- `0x18001fd50`
- `0x18002d050`

## callees

- `0x180002590`
- `0x18000d7a4`
- `0x18000d870`
- `0x18000f29c`
- `0x180012efc`
- `0x180013890`
- `0x180013ae0`
- `0x180013d08`
- `0x18001448c`
- `0x180014dc4`
- `0x180014e60`
- `0x180018648`
- `0x180018758`
- `0x18001a038`
- `0x18001b7fc`
- `0x18001c784`
- `0x18001d188`
- `0x18001e2dc`
- `0x18002062c`
- `0x18002073c`
- `0x180020e9c`
- `0x18002189c`
- `0x180022198`
- `0x1800248a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b98b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bae8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bce5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b98b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bae8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bce5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bb3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bd7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bb3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bd7d`
- `DismApi!DismInitialize` at `0x18001b84f`
- `DismApi!DismInitialize` at `0x18001b84f`
- `DismApi!DismEnableFeature` at `0x18001bb81`
- `DismApi!DismEnableFeature` at `0x18001bca2`
- `DismApi!DismEnableFeature` at `0x18001bb81`
- `DismApi!DismEnableFeature` at `0x18001bca2`
- `DismApi!DismOpenSession` at `0x18001b95c`
- `DismApi!DismOpenSession` at `0x18001b95c`
- `DismApi!DismGetFeatureInfo` at `0x18001b9f3`
- `DismApi!DismGetFeatureInfo` at `0x18001b9f3`

## string_xrefs

- `0x18001ba06`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`
- `0x18001bb9e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InstallRecall(int a1)
{
  _QWORD *v1; // rax
  __int64 v2; // rcx
  int v3; // esi
  __int64 v4; // rdi
  char *v5; // rbx
  __int64 v7; // rdi
  int FeatureInfo; // eax
  __int64 v9; // rdi
  __int64 v10; // r14
  char v11; // di
  unsigned __int8 v12; // si
  __int64 v13; // rdi
  void *v14; // rdi
  int v15; // edi
  __int64 v16; // rdx
  AIXPolicyHelper *v17; // rcx
  unsigned int CurrentBuildRevision; // ecx
  int v19; // eax
  int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // rsi
  __int64 v25; // rdi
  void *v26; // rbx
  LPVOID pv; // [rsp+60h] [rbp-69h] BYREF
  char v28[8]; // [rsp+68h] [rbp-61h] BYREF
  unsigned __int8 v29[8]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v30; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v31; // [rsp+80h] [rbp-49h] BYREF
  __int64 v32; // [rsp+88h] [rbp-41h] BYREF
  int v33[2]; // [rsp+90h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+98h] [rbp-31h] BYREF
  int v35; // [rsp+9Ch] [rbp-2Dh]
  int v36; // [rsp+A0h] [rbp-29h]
  _QWORD v37[3]; // [rsp+A8h] [rbp-21h] BYREF
  char v38; // [rsp+C0h] [rbp-9h]
  _OWORD v39[2]; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  int v41; // [rsp+130h] [rbp+67h] BYREF

  v41 = a1;
  pv = 0;
  v1 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v1 + 8LL, &v34);
  v3 = DismInitialize(2, 0, 0);
  if ( v3 < 0 )
  {
    v4 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
    *(_QWORD *)v33 = v4;
    if ( v4 )
      _InterlockedAdd((volatile signed __int32 *)(v4 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 200));
    ++*(_DWORD *)(v4 + 240);
    *(_DWORD *)(v4 + 272) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(v33);
    v5 = (char *)pv;
    if ( pv )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      *((_DWORD *)v5 + 18) |= 0x300u;
      if ( *((_QWORD *)v5 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v5 + 8, 2);
      if ( v5 != (char *)-200LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)v5 + 5);
      v5 = (char *)pv;
    }
    goto LABEL_10;
  }
  if ( !v41 )
  {
    LODWORD(v30) = 1;
    wil::wnf_publish_nothrow<int>(v2, &v30);
  }
  v31 = 0;
  v37[0] = &v31;
  v37[1] = &v41;
  v37[2] = &pv;
  v38 = 1;
  v3 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v31);
  if ( v3 < 0 )
  {
    v7 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
    *(_QWORD *)v33 = v7;
    if ( v7 )
      _InterlockedAdd((volatile signed __int32 *)(v7 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
    ++*(_DWORD *)(v7 + 240);
    *(_DWORD *)(v7 + 272) = 3;
    tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(v33);
    v38 = 0;
    _lambda_f52b1b46d4377ba4206e193596a6de21_::operator()(v37);
LABEL_20:
    v5 = (char *)pv;
LABEL_10:
    if ( v5 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(v5);
        CoTaskMemFree(v5);
      }
    }
    return (unsigned int)v3;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)v33 = 0;
    FeatureInfo = DismGetFeatureInfo(v31, L"Recall", 0, 0);
    v3 = FeatureInfo;
    if ( FeatureInfo < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
        (const char *)(unsigned int)FeatureInfo,
        (int)v33);
      v9 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
      v30 = v9;
      if ( v9 )
        _InterlockedAdd((volatile signed __int32 *)(v9 + 280), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
      ++*(_DWORD *)(v9 + 240);
      *(_DWORD *)(v9 + 272) = 9;
      tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(&v30);
      v38 = 0;
      _lambda_f52b1b46d4377ba4206e193596a6de21_::operator()(v37);
      goto LABEL_20;
    }
    v10 = *(_QWORD *)v33;
    IsUpdateManaged();
    v11 = 1;
    if ( IsCTAMachine() )
    {
      v12 = 1;
      if ( v10 && (!*(_DWORD *)(v10 + 8) || *(_DWORD *)(v10 + 8) == 3) )
        v11 = 0;
    }
    else
    {
      v12 = 0;
    }
    v28[0] = v11;
    v29[0] = v12;
    LOBYTE(v30) = v12;
    BYTE1(v30) = v11;
    AIXTelemetry::DismEnablementAndAccessStatus<bool &,bool &>(v29, v28);
    if ( !v11 )
    {
      v13 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
      v30 = v13;
      if ( v13 )
        _InterlockedAdd((volatile signed __int32 *)(v13 + 280), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 200));
      ++*(_DWORD *)(v13 + 240);
      *(_DWORD *)(v13 + 272) = 8;
      tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(&v30);
      AIXTelemetry::DismEnableFeatureSkipped();
      v38 = 0;
      _lambda_f52b1b46d4377ba4206e193596a6de21_::operator()(v37);
      v14 = pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(v14);
        CoTaskMemFree(v14);
      }
      return 1;
    }
    v15 = DismEnableFeature(v31, L"Recall", 0, 0, v12, 0, 0, 1, 0, 0, 0);
    memset(v39, 0, sizeof(v39));
    std::wstring::_Construct<1,unsigned short const *>(
      v39,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
      69);
    AIXPolicyHelper::InstallAttempts::GetCurrentInstallAttempts(&v34, v16, v39);
    CurrentBuildRevision = AIXPolicyHelper::GetCurrentBuildRevision(v17);
    if ( CurrentBuildRevision == v34 )
      v19 = v35 + 1;
    else
      v19 = 1;
    v34 = CurrentBuildRevision;
    v35 = v19;
    v20 = 5;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl'::`2'::impl) == 1 )
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::GetCachedVariantState(v22, &v32);
      v20 = HIDWORD(v32);
    }
    v36 = v20;
    AIXPolicyHelper::InstallAttempts::SaveAttemptsToRegistry(&v34, v21, v39);
    std::wstring::~wstring(v39);
    if ( (int)(v15 + 0x80000000) >= 0 && v15 != -2147021886 )
    {
      AIXTelemetry::DismEnableFeatureFailed();
LABEL_55:
      v24 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
      v32 = v24;
      if ( v24 )
        _InterlockedAdd((volatile signed __int32 *)(v24 + 280), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 200));
      ++*(_DWORD *)(v24 + 240);
      *(_DWORD *)(v24 + 272) = 5;
      tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(&v32);
      goto LABEL_61;
    }
    AIXTelemetry::DismEnableFeatureSucceeded<bool const &>(&v30);
    if ( v15 >= 0 )
    {
      v23 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
      v32 = v23;
      if ( v23 )
        _InterlockedAdd((volatile signed __int32 *)(v23 + 280), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v23 + 200));
      ++*(_DWORD *)(v23 + 240);
      *(_DWORD *)(v23 + 272) = 10;
      tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(&v32);
      goto LABEL_53;
    }
  }
  else
  {
    v15 = DismEnableFeature(v31, L"Recall", 0, 0, 1, 0, 0, 1, 0, 0, 0);
  }
  if ( v15 == -2147021886 )
  {
LABEL_58:
    v25 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(&pv);
    v32 = v25;
    if ( v25 )
      _InterlockedAdd((volatile signed __int32 *)(v25 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v25 + 200));
    ++*(_DWORD *)(v25 + 240);
    *(_DWORD *)(v25 + 272) = 7;
    tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(&v32);
    v15 = 0;
    goto LABEL_61;
  }
LABEL_53:
  if ( v15 == 3010 )
    goto LABEL_58;
  if ( v15 < 0 )
    goto LABEL_55;
LABEL_61:
  v38 = 0;
  _lambda_f52b1b46d4377ba4206e193596a6de21_::operator()(v37);
  v26 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(v26);
    CoTaskMemFree(v26);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001b7fc  mov     [rsp-8+arg_0], ecx
0x18001b800  push    rbp
0x18001b801  push    rbx
0x18001b802  push    rsi
0x18001b803  push    rdi
0x18001b804  push    r14
0x18001b806  push    r15
0x18001b808  lea     rbp, [rsp-2Fh]
0x18001b80d  sub     rsp, 0F8h
0x18001b814  mov     rax, cs:__security_cookie
0x18001b81b  xor     rax, rsp
0x18001b81e  mov     [rbp+57h+var_38], rax
0x18001b822  xor     r15d, r15d
0x18001b825  mov     [rbp+57h+pv], r15
0x18001b829  lea     rcx, [rbp+57h+pv]
0x18001b82d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(void)
0x18001b832  mov     rcx, [rax]
0x18001b835  add     rcx, 8
0x18001b839  lea     rdx, [rbp+57h+var_88]
0x18001b83d  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001b842  nop
0x18001b843  xor     r8d, r8d
0x18001b846  xor     edx, edx
0x18001b848  lea     r14d, [r15+2]
0x18001b84c  mov     ecx, r14d
0x18001b84f  call    cs:__imp_DismInitialize
0x18001b855  mov     esi, eax
0x18001b857  test    eax, eax
0x18001b859  jns     loc_18001B916
0x18001b85f  lea     rcx, [rbp+57h+pv]
0x18001b863  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(void)
0x18001b868  mov     rdi, [rax]
0x18001b86b  mov     qword ptr [rbp+57h+var_90], rdi
0x18001b86f  lea     ebx, [r15+1]
0x18001b873  test    rdi, rdi
0x18001b876  jz      short loc_18001B87F
0x18001b878  lock add [rdi+118h], ebx
0x18001b87f  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18001b886  call    cs:__imp_EnterCriticalSection
0x18001b88c  add     [rdi+0F0h], ebx
0x18001b892  mov     [rdi+110h], r14d
0x18001b899  lea     rcx, [rbp+57h+var_90]
0x18001b89d  call    ??1?$test_data_control@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(void)
0x18001b8a2  mov     rbx, [rbp+57h+pv]
0x18001b8a6  test    rbx, rbx
0x18001b8a9  jz      short loc_18001B8E9
0x18001b8ab  lea     rdi, [rbx+0C8h]
0x18001b8b2  mov     rcx, rdi; lpCriticalSection
0x18001b8b5  call    cs:__imp_EnterCriticalSection
0x18001b8bb  or      dword ptr [rbx+48h], 300h
0x18001b8c2  cmp     [rbx+0F8h], r15
0x18001b8c9  jz      short loc_18001B8D7
0x18001b8cb  mov     edx, r14d
0x18001b8ce  lea     rcx, [rbx+8]
0x18001b8d2  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001b8d7  test    rdi, rdi
0x18001b8da  jz      short loc_18001B8E5
0x18001b8dc  mov     rcx, rdi; lpCriticalSection
0x18001b8df  call    cs:__imp_LeaveCriticalSection
0x18001b8e5  mov     rbx, [rbp+57h+pv]
0x18001b8e9  test    rbx, rbx
0x18001b8ec  jz      short loc_18001B90F
0x18001b8ee  or      eax, 0FFFFFFFFh
0x18001b8f1  lock xadd [rbx+118h], eax
0x18001b8f9  cmp     eax, 1
0x18001b8fc  jnz     short loc_18001B90F
0x18001b8fe  mov     rcx, rbx
0x18001b901  call    ??1?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(void)
0x18001b906  mov     rcx, rbx; pv
0x18001b909  call    cs:__imp_CoTaskMemFree
0x18001b90f  mov     eax, esi
0x18001b911  jmp     loc_18001BD85
0x18001b916  mov     ebx, 1
0x18001b91b  cmp     [rbp+57h+arg_0], r15d
0x18001b91f  jnz     short loc_18001B92D
0x18001b921  mov     dword ptr [rbp+57h+var_A8], ebx
0x18001b924  lea     rdx, [rbp+57h+var_A8]
0x18001b928  call    ??$wnf_publish_nothrow@H@wil@@YAJAEBU_WNF_STATE_NAME@@AEBH@Z; wil::wnf_publish_nothrow<int>(_WNF_STATE_NAME const &,int const &)
0x18001b92d  mov     [rbp+57h+var_A0], r15d
0x18001b931  lea     rax, [rbp+57h+var_A0]
0x18001b935  mov     [rbp+57h+var_78], rax
0x18001b939  lea     rax, [rbp+57h+arg_0]
0x18001b93d  mov     [rbp+57h+var_70], rax
0x18001b941  lea     rax, [rbp+57h+pv]
0x18001b945  mov     [rbp+57h+var_68], rax
0x18001b949  mov     [rbp+57h+var_60], bl
0x18001b94c  lea     r9, [rbp+57h+var_A0]
0x18001b950  xor     r8d, r8d
0x18001b953  xor     edx, edx
0x18001b955  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x18001b95c  call    cs:__imp_DismOpenSession
0x18001b962  mov     esi, eax
0x18001b964  test    eax, eax
0x18001b966  jns     short loc_18001B9C2
0x18001b968  lea     rcx, [rbp+57h+pv]
0x18001b96c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(void)
0x18001b971  mov     rdi, [rax]
0x18001b974  mov     qword ptr [rbp+57h+var_90], rdi
0x18001b978  test    rdi, rdi
0x18001b97b  jz      short loc_18001B984
0x18001b97d  lock add [rdi+118h], ebx
0x18001b984  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18001b98b  call    cs:__imp_EnterCriticalSection
0x18001b991  add     [rdi+0F0h], ebx
0x18001b997  mov     dword ptr [rdi+110h], 3
0x18001b9a1  lea     rcx, [rbp+57h+var_90]
0x18001b9a5  call    ??1?$test_data_control@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(void)
0x18001b9aa  nop
0x18001b9ab  mov     [rbp+57h+var_60], r15b
0x18001b9af  lea     rcx, [rbp+57h+var_78]
0x18001b9b3  call    ??R_lambda_f52b1b46d4377ba4206e193596a6de21_@@QEBA@XZ; _lambda_f52b1b46d4377ba4206e193596a6de21_::operator()(void)
0x18001b9b8  nop
0x18001b9b9  mov     rbx, [rbp+57h+pv]
0x18001b9bd  jmp     loc_18001B8E9
0x18001b9c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769107@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107> `wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl(void)'::`2'::impl
0x18001b9c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_IsEnabled(void)
0x18001b9ce  xor     r9d, r9d
0x18001b9d1  xor     r8d, r8d
0x18001b9d4  lea     rdx, aRecall; "Recall"
0x18001b9db  mov     ecx, [rbp+57h+var_A0]
0x18001b9de  test    al, al
0x18001b9e0  jz      loc_18001BC81
0x18001b9e6  mov     qword ptr [rbp+57h+var_90], r15
0x18001b9ea  lea     rax, [rbp+57h+var_90]
0x18001b9ee  mov     qword ptr [rsp+120h+var_100], rax; int
0x18001b9f3  call    cs:__imp_DismGetFeatureInfo
0x18001b9f9  mov     esi, eax
0x18001b9fb  mov     rcx, [rbp+5Fh]; this
0x18001b9ff  test    eax, eax
0x18001ba01  jns     short loc_18001BA6D
0x18001ba03  mov     r9d, eax; char *
0x18001ba06  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18001ba0d  mov     edx, 11Bh; void *
0x18001ba12  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ba17  lea     rcx, [rbp+57h+pv]
0x18001ba1b  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(void)
0x18001ba20  mov     rdi, [rax]
0x18001ba23  mov     [rbp+57h+var_A8], rdi
0x18001ba27  test    rdi, rdi
0x18001ba2a  jz      short loc_18001BA33
0x18001ba2c  lock add [rdi+118h], ebx
0x18001ba33  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18001ba3a  call    cs:__imp_EnterCriticalSection
0x18001ba40  add     [rdi+0F0h], ebx
0x18001ba46  mov     dword ptr [rdi+110h], 9
0x18001ba50  lea     rcx, [rbp+57h+var_A8]
0x18001ba54  call    ??1?$test_data_control@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(void)
0x18001ba59  nop
0x18001ba5a  mov     [rbp+57h+var_60], r15b
0x18001ba5e  lea     rcx, [rbp+57h+var_78]
0x18001ba62  call    ??R_lambda_f52b1b46d4377ba4206e193596a6de21_@@QEBA@XZ; _lambda_f52b1b46d4377ba4206e193596a6de21_::operator()(void)
0x18001ba67  nop
0x18001ba68  jmp     loc_18001B9B9
0x18001ba6d  mov     r14, qword ptr [rbp+57h+var_90]
0x18001ba71  call    ?IsUpdateManaged@@YA_NXZ; IsUpdateManaged(void)
0x18001ba76  call    ?IsCTAMachine@@YA_NXZ; IsCTAMachine(void)
0x18001ba7b  mov     dil, bl
0x18001ba7e  test    al, al
0x18001ba80  jz      short loc_18001BA9C
0x18001ba82  mov     sil, bl
0x18001ba85  test    r14, r14
0x18001ba88  jz      short loc_18001BA9F
0x18001ba8a  cmp     [r14+8], r15d
0x18001ba8e  jz      short loc_18001BA97
0x18001ba90  cmp     dword ptr [r14+8], 3
0x18001ba95  jnz     short loc_18001BA9F
0x18001ba97  mov     dil, r15b
0x18001ba9a  jmp     short loc_18001BA9F
0x18001ba9c  mov     sil, r15b
0x18001ba9f  mov     [rbp+57h+var_B8], dil
0x18001baa3  mov     [rbp+57h+var_B0], sil
0x18001baa7  mov     byte ptr [rbp+57h+var_A8], sil
0x18001baab  mov     byte ptr [rbp+57h+var_A8+1], dil
0x18001baaf  lea     rdx, [rbp+57h+var_B8]
0x18001bab3  lea     rcx, [rbp+57h+var_B0]
0x18001bab7  call    ??$DismEnablementAndAccessStatus@AEA_NAEA_N@AIXTelemetry@@SAXAEA_N0@Z; AIXTelemetry::DismEnablementAndAccessStatus<bool &,bool &>(bool &,bool &)
0x18001babc  test    dil, dil
0x18001babf  jnz     loc_18001BB4C
0x18001bac5  lea     rcx, [rbp+57h+pv]
0x18001bac9  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(void)
0x18001bace  mov     rdi, [rax]
0x18001bad1  mov     [rbp+57h+var_A8], rdi
0x18001bad5  test    rdi, rdi
0x18001bad8  jz      short loc_18001BAE1
0x18001bada  lock add [rdi+118h], ebx
0x18001bae1  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18001bae8  call    cs:__imp_EnterCriticalSection
0x18001baee  add     [rdi+0F0h], ebx
0x18001baf4  mov     dword ptr [rdi+110h], 8
0x18001bafe  lea     rcx, [rbp+57h+var_A8]
0x18001bb02  call    ??1?$test_data_control@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(void)
0x18001bb07  call    ?DismEnableFeatureSkipped@AIXTelemetry@@SAXXZ; AIXTelemetry::DismEnableFeatureSkipped(void)
0x18001bb0c  nop
0x18001bb0d  mov     [rbp+57h+var_60], r15b
0x18001bb11  lea     rcx, [rbp+57h+var_78]
0x18001bb15  call    ??R_lambda_f52b1b46d4377ba4206e193596a6de21_@@QEBA@XZ; _lambda_f52b1b46d4377ba4206e193596a6de21_::operator()(void)
0x18001bb1a  nop
0x18001bb1b  mov     rdi, [rbp+57h+pv]
0x18001bb1f  test    rdi, rdi
0x18001bb22  jz      short loc_18001BB45
0x18001bb24  or      edx, 0FFFFFFFFh
0x18001bb27  lock xadd [rdi+118h], edx
0x18001bb2f  cmp     edx, 1
0x18001bb32  jnz     short loc_18001BB45
0x18001bb34  mov     rcx, rdi
0x18001bb37  call    ??1?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>::~merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>(void)
0x18001bb3c  mov     rcx, rdi; pv
0x18001bb3f  call    cs:__imp_CoTaskMemFree
0x18001bb45  mov     eax, ebx
0x18001bb47  jmp     loc_18001BD85
0x18001bb4c  movzx   eax, sil
0x18001bb50  mov     [rsp+120h+var_D0], r15
0x18001bb55  mov     [rsp+120h+var_D8], r15
0x18001bb5a  mov     [rsp+120h+var_E0], r15
0x18001bb5f  mov     [rsp+120h+var_E8], ebx
0x18001bb63  mov     [rsp+120h+var_F0], r15d
0x18001bb68  mov     [rsp+120h+var_F8], r15
0x18001bb6d  mov     [rsp+120h+var_100], eax
0x18001bb71  xor     r9d, r9d
0x18001bb74  xor     r8d, r8d
0x18001bb77  lea     rdx, aRecall; "Recall"
0x18001bb7e  mov     ecx, [rbp+57h+var_A0]
0x18001bb81  call    cs:__imp_DismEnableFeature
0x18001bb87  mov     edi, eax
0x18001bb89  xorps   xmm0, xmm0
0x18001bb8c  movups  [rbp+57h+var_58], xmm0
0x18001bb90  xorps   xmm1, xmm1
0x18001bb93  movdqu  [rbp+57h+var_48], xmm1
0x18001bb98  mov     r8d, 45h ; 'E'
0x18001bb9e  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001bba5  lea     rcx, [rbp+57h+var_58]
0x18001bba9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bbae  nop
0x18001bbaf  lea     r8, [rbp+57h+var_58]
0x18001bbb3  lea     rcx, [rbp+57h+var_88]
0x18001bbb7  call    ?GetCurrentInstallAttempts@InstallAttempts@AIXPolicyHelper@@SA?AU12@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AIXPolicyHelper::InstallAttempts::GetCurrentInstallAttempts(HKEY__ *,std::wstring const &)
0x18001bbbc  call    ?GetCurrentBuildRevision@AIXPolicyHelper@@YAKXZ; AIXPolicyHelper::GetCurrentBuildRevision(void)
0x18001bbc1  mov     ecx, eax
0x18001bbc3  cmp     eax, [rbp+57h+var_88]
0x18001bbc6  jz      short loc_18001BBCC
0x18001bbc8  mov     eax, ebx
0x18001bbca  jmp     short loc_18001BBD1
0x18001bbcc  mov     eax, [rbp+57h+var_84]
0x18001bbcf  inc     eax
0x18001bbd1  mov     [rbp+57h+var_88], ecx
0x18001bbd4  mov     [rbp+57h+var_84], eax
0x18001bbd7  mov     esi, 5
0x18001bbdc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769107@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107> `wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl(void)'::`2'::impl
0x18001bbe3  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@wil@@QEAA?AW4Variant_56769107@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18001bbe8  cmp     al, bl
0x18001bbea  jnz     short loc_18001BBF8
0x18001bbec  lea     rdx, [rbp+57h+var_98]
0x18001bbf0  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::GetCachedVariantState(void)
0x18001bbf5  mov     esi, dword ptr [rbp+57h+var_98+4]
0x18001bbf8  mov     [rbp+57h+var_80], esi
0x18001bbfb  lea     r8, [rbp+57h+var_58]
0x18001bbff  lea     rcx, [rbp+57h+var_88]
0x18001bc03  call    ?SaveAttemptsToRegistry@InstallAttempts@AIXPolicyHelper@@SAXAEBU12@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AIXPolicyHelper::InstallAttempts::SaveAttemptsToRegistry(AIXPolicyHelper::InstallAttempts const &,HKEY__ *,std::wstring const &)
0x18001bc08  nop
0x18001bc09  lea     rcx, [rbp+57h+var_58]
0x18001bc0d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bc12  mov     ecx, 80000000h
0x18001bc17  lea     eax, [rdi+rcx]
0x18001bc1a  test    ecx, eax
0x18001bc1c  jnz     short loc_18001BC30
0x18001bc1e  cmp     edi, 80070BC2h
0x18001bc24  jz      short loc_18001BC30
0x18001bc26  call    ?DismEnableFeatureFailed@AIXTelemetry@@SAXXZ; AIXTelemetry::DismEnableFeatureFailed(void)
0x18001bc2b  jmp     loc_18001BCC2
0x18001bc30  lea     rcx, [rbp+57h+var_A8]
0x18001bc34  call    ??$DismEnableFeatureSucceeded@AEB_N@AIXTelemetry@@SAXAEB_N@Z; AIXTelemetry::DismEnableFeatureSucceeded<bool const &>(bool const &)
0x18001bc39  test    edi, edi
0x18001bc3b  js      short loc_18001BCAA
0x18001bc3d  lea     rcx, [rbp+57h+pv]
0x18001bc41  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::ensure_data(void)
0x18001bc46  mov     rsi, [rax]
0x18001bc49  mov     [rbp+57h+var_98], rsi
0x18001bc4d  test    rsi, rsi
0x18001bc50  jz      short loc_18001BC59
0x18001bc52  lock add [rsi+118h], ebx
0x18001bc59  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x18001bc60  call    cs:__imp_EnterCriticalSection
0x18001bc66  add     [rsi+0F0h], ebx
0x18001bc6c  mov     dword ptr [rsi+110h], 0Ah
0x18001bc76  lea     rcx, [rbp+57h+var_98]
0x18001bc7a  call    ??1?$test_data_control@V?$merged_data@U_tip_DismEnableTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DismEnableTipTest,_tip_DismEnableTipTest>>(void)
0x18001bc7f  jmp     short loc_18001BCB2
0x18001bc81  mov     [rsp+120h+var_D0], r15
0x18001bc86  mov     [rsp+120h+var_D8], r15
0x18001bc8b  mov     [rsp+120h+var_E0], r15
0x18001bc90  mov     [rsp+120h+var_E8], ebx
0x18001bc94  mov     [rsp+120h+var_F0], r15d
0x18001bc99  mov     [rsp+120h+var_F8], r15
0x18001bc9e  mov     [rsp+120h+var_100], ebx
0x18001bca2  call    cs:__imp_DismEnableFeature
0x18001bca8  mov     edi, eax
0x18001bcaa  cmp     edi, 80070BC2h
0x18001bcb0  jz      short loc_18001BD06
0x18001bcb2  cmp     edi, 0BC2h
0x18001bcb8  jz      short loc_18001BD06
  ... truncated ...
```
