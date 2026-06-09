# DeleteAndUpdateAuthorityProvider(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800bb4bc`
- end: `0x1800bba92`
- name: `?DeleteAndUpdateAuthorityProvider@@YAJPEBG00000@Z`
- size: `1494`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ae150`
- `0x1800b5370`
- `0x1800bbaa0`
- `0x1800bfff8`
- `0x1800e4848`
- `0x1800e6c94`

## callees

- `0x18000b9e0`
- `0x18000bf00`
- `0x1800117dc`
- `0x180013d4c`
- `0x18001438c`
- `0x18001440c`
- `0x180018a70`
- `0x180018ac0`
- `0x180018ba4`
- `0x180018cc4`
- `0x180019ec8`
- `0x18001c300`
- `0x18001def8`
- `0x180048fe8`
- `0x18004b7f4`
- `0x1800a01ec`
- `0x1800ae114`
- `0x1800bb4bc`
- `0x1800c0c70`
- `0x1800c4640`
- `0x1800cbb24`
- `0x1800d7b78`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x1800f9e64`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bba31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bba31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb8fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb8fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb8ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bba23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb8ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bba23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb9be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb9be`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800bb9af`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800bb9af`

## string_xrefs

- `0x1800bb563`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bb5e4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bb677`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bb7c3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bb915`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bb9e9`: `RefreshDocumentAsyncThread`
- `0x1800bb546`: `DCTrackingStore::GetInstance()->DeleteAuthority`
- `0x1800bb54d`: `DeleteAndUpdateAuthorityProvider`
- `0x1800bb63e`: `DeleteAndUpdateAuthorityProvider`
- `0x1800bb7af`: `DeleteAndUpdateAuthorityProvider`
- `0x1800bb84c`: `DeleteAndUpdateAuthorityProvider`
- `0x1800bb9f0`: `DeleteAndUpdateAuthorityProvider`
- `0x1800bb65d`: `DeleteAndUpdateAuthorityProvider GetAllAuthorities`
- `0x1800bb7a8`: `GetDriftControlStateWithPrecedenceOrderConsidered - currentAuthority`
- `0x1800bb87e`: `DeleteAndUpdateAuthorityProvider GetTheHighestIndex`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeleteAndUpdateAuthorityProvider(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const unsigned __int16 *v7; // rsi
  struct IDCTrackingStore *Instance; // rax
  int v10; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  struct IDCTrackingStore *v13; // rax
  signed int v14; // edi
  CDeclaredConfigurationLogger *v15; // rax
  int v16; // ecx
  __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // rdx
  unsigned int i; // r14d
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r9
  int DriftControlStateWithPrecedenceOrderConsidered; // eax
  _QWORD *v24; // rdx
  CDeclaredConfigurationLogger *v25; // rax
  const unsigned __int16 *v26; // r9
  __int64 v27; // rdx
  struct IDCPrecedenceManager *v28; // rax
  __int64 v29; // rsi
  CDeclaredConfigurationLogger *v30; // rcx
  __int64 v31; // rdi
  const wchar_t *v32; // rbx
  const wchar_t *v33; // r9
  int v34; // ecx
  __int64 v35; // rdi
  DCAuthorityInfo *v36; // rax
  DCAuthorityInfo *v37; // rbx
  __int64 v38; // rdx
  HANDLE ProcessHeap; // rax
  DCAuthorityInfo *v40; // rax
  const unsigned __int16 *v41; // rsi
  signed int LastError; // eax
  CDeclaredConfigurationLogger *v43; // rax
  HANDLE v44; // rax
  int dwCreationFlagsc; // [rsp+20h] [rbp-79h]
  int *dwCreationFlags; // [rsp+20h] [rbp-79h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-79h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-79h]
  char v49; // [rsp+40h] [rbp-59h] BYREF
  bool v50; // [rsp+41h] [rbp-58h] BYREF
  int v51[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v52; // [rsp+50h] [rbp-49h]
  __int64 v53; // [rsp+58h] [rbp-41h]
  _QWORD v54[4]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v55[32]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v7 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl'::`2'::impl,
    a2);
  v49 = 0;
  Instance = DCTrackingStore::GetInstance();
  v10 = (*(__int64 (__fastcall **)(struct IDCTrackingStore *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, char *))(*(_QWORD *)Instance + 24LL))(
          Instance,
          a1,
          v7,
          a3,
          a4,
          a5,
          &v49);
  if ( v10 < 0 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"DeleteAndUpdateAuthorityProvider",
      L"DCTrackingStore::GetInstance()->DeleteAuthority",
      v7,
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)(unsigned int)v10,
      dwCreationFlagsc);
    return (unsigned int)v10;
  }
  if ( !v49 )
    return 0;
  std::vector<ConfigDoc>::vector<ConfigDoc>(v51);
  v13 = DCTrackingStore::GetInstance();
  dwCreationFlags = v51;
  v10 = (*(__int64 (__fastcall **)(struct IDCTrackingStore *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v13 + 32LL))(
          v13,
          a1,
          v7,
          a3);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
  {
    if ( v10 < 0 )
    {
      v15 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v15,
        L"DeleteAndUpdateAuthorityProvider",
        L"DCTrackingStore::GetInstance()->GetAllAuthorities",
        v7,
        v10);
      if ( byte_180189FC1 < 0 )
        McTemplateU0zzd_EventWriteTransfer(
          v16,
          (unsigned int)OrchestratorGenericFailure,
          (unsigned int)L"DeleteAndUpdateAuthorityProvider GetAllAuthorities",
          (_DWORD)v7,
          v10);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
        (const char *)(unsigned int)v10,
        dwCreationFlagsa);
      if ( *(_QWORD *)v51 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(*(_QWORD *)v51, v52);
        std::_Deallocate<16>(*(void **)v51, (v53 - *(_QWORD *)v51) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      return (unsigned int)v10;
    }
    goto LABEL_18;
  }
  v14 = 0;
  if ( v10 != -2147024894 )
    v14 = v10;
  if ( v14 >= 0 )
  {
LABEL_18:
    v17 = v52;
    v18 = *(void **)v51;
    if ( v52 != *(_QWORD *)v51 )
    {
      std::vector<ConfigDoc>::vector<ConfigDoc>(v54);
      for ( i = 0; i < (unsigned __int64)((v52 - *(_QWORD *)v51) >> 4); ++i )
      {
        v50 = 1;
        LOBYTE(v19) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl>::GetImpl'::`2'::impl,
          v19);
        v21 = *(const unsigned __int16 **)(*(_QWORD *)v51 + 16LL * i);
        v22 = v21 + 16;
        if ( *((_QWORD *)v21 + 7) > 7u )
          v22 = *(const unsigned __int16 **)v22;
        if ( *((_QWORD *)v21 + 3) > 7u )
          v21 = *(const unsigned __int16 **)v21;
        DriftControlStateWithPrecedenceOrderConsidered = GetDriftControlStateWithPrecedenceOrderConsidered(
                                                           a1,
                                                           v7,
                                                           v21,
                                                           v22,
                                                           &v50);
        v14 = DriftControlStateWithPrecedenceOrderConsidered;
        v19 = 0x80000000LL;
        if ( (int)(DriftControlStateWithPrecedenceOrderConsidered + 0x80000000) >= 0
          && DriftControlStateWithPrecedenceOrderConsidered != -2147024894 )
        {
          v25 = CDeclaredConfigurationLogger::GetLogger();
          v26 = *(const unsigned __int16 **)(*(_QWORD *)v51 + 16LL * i);
          if ( *((_QWORD *)v26 + 3) > 7u )
            v26 = *(const unsigned __int16 **)v26;
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v25,
            L"DeleteAndUpdateAuthorityProvider",
            L"GetDriftControlStateWithPrecedenceOrderConsidered - currentAuthority",
            v26,
            v14);
          v27 = 675;
          goto LABEL_35;
        }
        if ( v50 )
        {
          v24 = *(_QWORD **)(*(_QWORD *)v51 + 16LL * i);
          if ( v24[3] > 7u )
            v24 = (_QWORD *)*v24;
          std::wstring::wstring((__int64)v55, (__int64)v24);
          std::vector<std::wstring>::push_back(v54, v55);
          std::wstring::_Tidy_deallocate(v55);
        }
      }
      if ( v54[1] != v54[0] )
      {
        v28 = DCPrecedenceManager::GetInstance();
        v29 = (*(int (__fastcall **)(struct IDCPrecedenceManager *, _QWORD *))(*(_QWORD *)v28 + 8LL))(v28, v54);
        v30 = CDeclaredConfigurationLogger::GetLogger();
        v31 = 32 * v29;
        v32 = L"empty";
        if ( (_DWORD)v29 == -1 )
        {
          v33 = L"empty";
        }
        else
        {
          v33 = (const wchar_t *)(v31 + v54[0]);
          if ( *(_QWORD *)(v31 + v54[0] + 24) > 7u )
            v33 = *(const wchar_t **)v33;
        }
        CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
          v30,
          L"DeleteAndUpdateAuthorityProvider",
          L"DCPrecedenceManager::GetInstance()->GetTheHighestIndex",
          v33);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          if ( (_DWORD)v29 != -1 )
          {
            v32 = (const wchar_t *)(v31 + v54[0]);
            if ( *(_QWORD *)(v31 + v54[0] + 24) > 7u )
              v32 = *(const wchar_t **)v32;
          }
          McTemplateU0zzd_EventWriteTransfer(
            v34,
            (unsigned int)OrchestratorGenericInformation,
            (unsigned int)L"DeleteAndUpdateAuthorityProvider GetTheHighestIndex",
            (_DWORD)v32,
            v29);
        }
        if ( (_DWORD)v29 != -1 )
        {
          v35 = *(_QWORD *)(*(_QWORD *)v51 + 16 * v29);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
          {
            v36 = (DCAuthorityInfo *)operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
            v54[3] = v36;
            if ( !v36 || (v37 = DCAuthorityInfo::DCAuthorityInfo(v36)) == 0 )
            {
              v38 = 709;
LABEL_53:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v38,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                (const char *)0x8007000ELL,
                (int)dwCreationFlags);
              std::vector<std::wstring>::_Tidy(v54);
              if ( *(_QWORD *)v51 )
              {
                std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(*(_QWORD *)v51, v52);
                std::_Deallocate<16>(*(void **)v51, (v53 - *(_QWORD *)v51) & 0xFFFFFFFFFFFFFFF0uLL);
              }
              return 2147942414LL;
            }
          }
          else
          {
            ProcessHeap = GetProcessHeap();
            v40 = (DCAuthorityInfo *)HeapAlloc(ProcessHeap, 8u, 0x60u);
            v37 = v40;
            if ( !v40 )
            {
              v38 = 717;
              goto LABEL_53;
            }
            DCAuthorityInfo::DCAuthorityInfo(v40);
          }
          std::wstring::operator=(v37, v35);
          v41 = (const unsigned __int16 *)(v35 + 32);
          std::wstring::operator=((char *)v37 + 32, v35 + 32);
          std::wstring::operator=((char *)v37 + 64, v35 + 64);
          if ( !CreateThread(0, 0, RefreshDocumentAsyncThread, v37, 0, 0) )
          {
            LastError = GetLastError();
            v14 = LastError;
            if ( LastError > 0 )
              v14 = (unsigned __int16)LastError | 0x80070000;
            v43 = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)v41 + 3) > 7u )
              v41 = *(const unsigned __int16 **)v41;
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v43,
              L"DeleteAndUpdateAuthorityProvider",
              L"RefreshDocumentAsyncThread",
              v41,
              v14);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
            {
              if ( v37 )
                DCAuthorityInfo::`scalar deleting destructor'(v37, 1u);
            }
            else
            {
              v44 = GetProcessHeap();
              HeapFree(v44, 0, v37);
            }
            if ( v14 < 0 )
            {
              v27 = 743;
LABEL_35:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v27,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                (const char *)(unsigned int)v14,
                dwCreationFlagsb);
              std::vector<std::wstring>::_Tidy(v54);
              goto LABEL_10;
            }
          }
        }
      }
      std::vector<std::wstring>::_Tidy(v54);
      v17 = v52;
      v18 = *(void **)v51;
    }
    if ( v18 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(v18, v17);
      std::_Deallocate<16>(*(void **)v51, (v53 - *(_QWORD *)v51) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x270,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
    (const char *)(unsigned int)v14,
    (int)v51);
LABEL_10:
  if ( *(_QWORD *)v51 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(*(_QWORD *)v51, v52);
    std::_Deallocate<16>(*(void **)v51, (v53 - *(_QWORD *)v51) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800bb4bc  push    rbp
0x1800bb4be  push    rbx
0x1800bb4bf  push    rsi
0x1800bb4c0  push    rdi
0x1800bb4c1  push    r14
0x1800bb4c3  push    r15
0x1800bb4c5  lea     rbp, [rsp-1Fh]
0x1800bb4ca  sub     rsp, 0B8h
0x1800bb4d1  mov     rax, cs:__security_cookie
0x1800bb4d8  xor     rax, rsp
0x1800bb4db  mov     [rbp+47h+var_40], rax
0x1800bb4df  mov     rdi, r9
0x1800bb4e2  mov     r14, r8
0x1800bb4e5  mov     rsi, rdx
0x1800bb4e8  mov     r15, rcx
0x1800bb4eb  mov     rbx, [rbp+47h+arg_20]
0x1800bb4ef  mov     dl, 1
0x1800bb4f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl(void)'::`2'::impl
0x1800bb4f8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bb4fd  mov     [rbp+47h+var_A0], 0
0x1800bb501  call    ?GetInstance@DCTrackingStore@@SAPEAVIDCTrackingStore@@XZ; DCTrackingStore::GetInstance(void)
0x1800bb506  mov     r10, rax
0x1800bb509  mov     rcx, [rax]
0x1800bb50c  mov     rax, [rcx+18h]
0x1800bb510  lea     rcx, [rbp+47h+var_A0]
0x1800bb514  mov     [rsp+0E0h+var_B0], rcx
0x1800bb519  mov     [rsp+0E0h+lpThreadId], rbx
0x1800bb51e  mov     qword ptr [rsp+0E0h+dwCreationFlags], rdi
0x1800bb523  mov     r9, r14
0x1800bb526  mov     r8, rsi
0x1800bb529  mov     rdx, r15
0x1800bb52c  mov     rcx, r10
0x1800bb52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb534  mov     ebx, eax
0x1800bb536  test    eax, eax
0x1800bb538  jns     short loc_1800BB57B
0x1800bb53a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bb53f  mov     [rsp+0E0h+dwCreationFlags], ebx; int
0x1800bb543  mov     r9, rsi; unsigned __int16 *
0x1800bb546  lea     r8, aDctrackingstor_0; "DCTrackingStore::GetInstance()->DeleteA"...
0x1800bb54d  lea     rdx, aDeleteandupdat; "DeleteAndUpdateAuthorityProvider"
0x1800bb554  mov     rcx, rax; this
0x1800bb557  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800bb55c  mov     rcx, [rbp+4Fh]; this
0x1800bb560  mov     r9d, ebx; char *
0x1800bb563  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bb56a  mov     edx, 25Ch; void *
0x1800bb56f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb574  mov     eax, ebx
0x1800bb576  jmp     loc_1800BBA76
0x1800bb57b  cmp     [rbp+47h+var_A0], 0
0x1800bb57f  jz      loc_1800BBA74
0x1800bb585  lea     rcx, [rbp+47h+var_98]
0x1800bb589  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x1800bb58e  nop
0x1800bb58f  call    ?GetInstance@DCTrackingStore@@SAPEAVIDCTrackingStore@@XZ; DCTrackingStore::GetInstance(void)
0x1800bb594  mov     r10, rax
0x1800bb597  mov     rcx, [rax]
0x1800bb59a  mov     rax, [rcx+20h]
0x1800bb59e  lea     rcx, [rbp+47h+var_98]
0x1800bb5a2  mov     qword ptr [rsp+0E0h+dwCreationFlags], rcx; int
0x1800bb5a7  mov     r9, r14
0x1800bb5aa  mov     r8, rsi
0x1800bb5ad  mov     rdx, r15
0x1800bb5b0  mov     rcx, r10
0x1800bb5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb5b8  mov     ebx, eax
0x1800bb5ba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl(void)'::`2'::impl
0x1800bb5c1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(void)
0x1800bb5c6  test    al, al
0x1800bb5c8  jz      short loc_1800BB623
0x1800bb5ca  xor     edi, edi
0x1800bb5cc  cmp     ebx, 80070002h
0x1800bb5d2  cmovnz  edi, ebx
0x1800bb5d5  test    edi, edi
0x1800bb5d7  jns     loc_1800BB6B8
0x1800bb5dd  mov     rcx, [rbp+4Fh]; this
0x1800bb5e1  mov     r9d, edi; char *
0x1800bb5e4  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bb5eb  mov     edx, 270h; void *
0x1800bb5f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb5f5  nop
0x1800bb5f6  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb5fa  test    rcx, rcx
0x1800bb5fd  jz      short loc_1800BB61C
0x1800bb5ff  mov     rdx, [rbp+47h+var_90]
0x1800bb603  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDCProviderOrchestration@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(std::shared_ptr<DCProviderOrchestration> *,std::shared_ptr<DCProviderOrchestration> * const,std::allocator<std::shared_ptr<DCProviderOrchestration>> &)
0x1800bb608  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb60c  mov     rdx, [rbp+47h+var_88]
0x1800bb610  sub     rdx, rcx
0x1800bb613  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800bb617  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800bb61c  mov     eax, edi
0x1800bb61e  jmp     loc_1800BBA76
0x1800bb623  test    ebx, ebx
0x1800bb625  jns     loc_1800BB6B8
0x1800bb62b  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bb630  mov     [rsp+0E0h+dwCreationFlags], ebx; int
0x1800bb634  mov     r9, rsi; unsigned __int16 *
0x1800bb637  lea     r8, aDctrackingstor_2; "DCTrackingStore::GetInstance()->GetAllA"...
0x1800bb63e  lea     rdx, aDeleteandupdat; "DeleteAndUpdateAuthorityProvider"
0x1800bb645  mov     rcx, rax; this
0x1800bb648  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800bb64d  cmp     cs:byte_180189FC1, 0
0x1800bb654  jge     short loc_1800BB670
0x1800bb656  mov     [rsp+0E0h+dwCreationFlags], ebx; int
0x1800bb65a  mov     r9, rsi
0x1800bb65d  lea     r8, aDeleteandupdat_0; "DeleteAndUpdateAuthorityProvider GetAll"...
0x1800bb664  lea     rdx, OrchestratorGenericFailure
0x1800bb66b  call    McTemplateU0zzd_EventWriteTransfer
0x1800bb670  mov     rcx, [rbp+4Fh]; this
0x1800bb674  mov     r9d, ebx; char *
0x1800bb677  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bb67e  mov     edx, 27Dh; void *
0x1800bb683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb688  nop
0x1800bb689  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb68d  test    rcx, rcx
0x1800bb690  jz      loc_1800BB574
0x1800bb696  mov     rdx, [rbp+47h+var_90]
0x1800bb69a  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDCProviderOrchestration@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(std::shared_ptr<DCProviderOrchestration> *,std::shared_ptr<DCProviderOrchestration> * const,std::allocator<std::shared_ptr<DCProviderOrchestration>> &)
0x1800bb69f  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb6a3  mov     rdx, [rbp+47h+var_88]
0x1800bb6a7  sub     rdx, rcx
0x1800bb6aa  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800bb6ae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800bb6b3  jmp     loc_1800BB574
0x1800bb6b8  mov     rdx, [rbp+47h+var_90]
0x1800bb6bc  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb6c0  cmp     rdx, rcx
0x1800bb6c3  jz      loc_1800BBA56
0x1800bb6c9  lea     rcx, [rbp+47h+var_80]
0x1800bb6cd  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x1800bb6d2  nop
0x1800bb6d3  xor     r14d, r14d
0x1800bb6d6  mov     ebx, r14d
0x1800bb6d9  mov     rax, [rbp+47h+var_90]
0x1800bb6dd  sub     rax, qword ptr [rbp+47h+var_98]
0x1800bb6e1  sar     rax, 4
0x1800bb6e5  cmp     rbx, rax
0x1800bb6e8  jnb     loc_1800BB7E5
0x1800bb6ee  mov     [rbp+47h+var_9F], 1
0x1800bb6f2  mov     dl, 1
0x1800bb6f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl>::GetImpl(void)'::`2'::impl
0x1800bb6fb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bb700  add     rbx, rbx
0x1800bb703  mov     rax, qword ptr [rbp+47h+var_98]
0x1800bb707  mov     r8, [rax+rbx*8]
0x1800bb70b  lea     r9, [r8+20h]
0x1800bb70f  cmp     qword ptr [r9+18h], 7
0x1800bb714  jbe     short loc_1800BB719
0x1800bb716  mov     r9, [r9]; unsigned __int16 *
0x1800bb719  cmp     qword ptr [r8+18h], 7
0x1800bb71e  jbe     short loc_1800BB723
0x1800bb720  mov     r8, [r8]; unsigned __int16 *
0x1800bb723  lea     rax, [rbp+47h+var_9F]
0x1800bb727  mov     qword ptr [rsp+0E0h+dwCreationFlags], rax; bool *
0x1800bb72c  mov     rdx, rsi; unsigned __int16 *
0x1800bb72f  mov     rcx, r15; unsigned __int16 *
0x1800bb732  call    ?GetDriftControlStateWithPrecedenceOrderConsidered@@YAJPEBG000PEA_N@Z; GetDriftControlStateWithPrecedenceOrderConsidered(ushort const *,ushort const *,ushort const *,ushort const *,bool *)
0x1800bb737  mov     edi, eax
0x1800bb739  mov     edx, 80000000h
0x1800bb73e  lea     ecx, [rax+rdx]
0x1800bb741  test    edx, ecx
0x1800bb743  jnz     short loc_1800BB74C
0x1800bb745  cmp     eax, 80070002h
0x1800bb74a  jnz     short loc_1800BB78D
0x1800bb74c  cmp     [rbp+47h+var_9F], 0
0x1800bb750  jz      short loc_1800BB785
0x1800bb752  mov     rax, qword ptr [rbp+47h+var_98]
0x1800bb756  mov     rdx, [rax+rbx*8]
0x1800bb75a  cmp     qword ptr [rdx+18h], 7
0x1800bb75f  jbe     short loc_1800BB764
0x1800bb761  mov     rdx, [rdx]
0x1800bb764  lea     rcx, [rbp+47h+var_60]
0x1800bb768  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800bb76d  nop
0x1800bb76e  lea     rdx, [rbp+47h+var_60]
0x1800bb772  lea     rcx, [rbp+47h+var_80]
0x1800bb776  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800bb77b  nop
0x1800bb77c  lea     rcx, [rbp+47h+var_60]
0x1800bb780  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bb785  inc     r14d
0x1800bb788  jmp     loc_1800BB6D6
0x1800bb78d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bb792  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb796  mov     r9, [rcx+rbx*8]
0x1800bb79a  cmp     qword ptr [r9+18h], 7
0x1800bb79f  jbe     short loc_1800BB7A4
0x1800bb7a1  mov     r9, [r9]; unsigned __int16 *
0x1800bb7a4  mov     [rsp+0E0h+dwCreationFlags], edi; int
0x1800bb7a8  lea     r8, aGetdriftcontro_0; "GetDriftControlStateWithPrecedenceOrder"...
0x1800bb7af  lea     rdx, aDeleteandupdat; "DeleteAndUpdateAuthorityProvider"
0x1800bb7b6  mov     rcx, rax; this
0x1800bb7b9  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800bb7be  mov     edx, 2A3h; void *
0x1800bb7c3  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bb7ca  mov     r9d, edi; char *
0x1800bb7cd  mov     rcx, [rbp+4Fh]; this
0x1800bb7d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb7d6  nop
0x1800bb7d7  lea     rcx, [rbp+47h+var_80]
0x1800bb7db  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800bb7e0  jmp     loc_1800BB5F6
0x1800bb7e5  mov     rax, [rbp+47h+var_78]
0x1800bb7e9  cmp     rax, [rbp+47h+var_80]
0x1800bb7ed  jz      loc_1800BBA45
0x1800bb7f3  call    ?GetInstance@DCPrecedenceManager@@SAPEAVIDCPrecedenceManager@@XZ; DCPrecedenceManager::GetInstance(void)
0x1800bb7f8  mov     r8, rax
0x1800bb7fb  mov     rcx, [rax]
0x1800bb7fe  mov     rax, [rcx+8]
0x1800bb802  lea     rdx, [rbp+47h+var_80]
0x1800bb806  mov     rcx, r8
0x1800bb809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb80e  movsxd  rsi, eax
0x1800bb811  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800bb816  mov     rcx, rax; this
0x1800bb819  mov     r14, rsi
0x1800bb81c  mov     rdi, rsi
0x1800bb81f  shl     rdi, 5
0x1800bb823  lea     rbx, aEmpty; "empty"
0x1800bb82a  cmp     esi, 0FFFFFFFFh
0x1800bb82d  jnz     short loc_1800BB834
0x1800bb82f  mov     r9, rbx
0x1800bb832  jmp     short loc_1800BB845
0x1800bb834  mov     r9, [rbp+47h+var_80]
0x1800bb838  add     r9, rdi
0x1800bb83b  cmp     qword ptr [r9+18h], 7
0x1800bb840  jbe     short loc_1800BB845
0x1800bb842  mov     r9, [r9]; unsigned __int16 *
0x1800bb845  lea     r8, aDcprecedencema; "DCPrecedenceManager::GetInstance()->Get"...
0x1800bb84c  lea     rdx, aDeleteandupdat; "DeleteAndUpdateAuthorityProvider"
0x1800bb853  call    ?LogOrchestratorGenericInfo@CDeclaredConfigurationLogger@@QEAAXPEBG00@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(ushort const *,ushort const *,ushort const *)
0x1800bb858  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x1800bb85f  jz      short loc_1800BB891
0x1800bb861  cmp     esi, 0FFFFFFFFh
0x1800bb864  jz      short loc_1800BB877
0x1800bb866  mov     rbx, [rbp+47h+var_80]
0x1800bb86a  add     rbx, rdi
0x1800bb86d  cmp     qword ptr [rbx+18h], 7
0x1800bb872  jbe     short loc_1800BB877
0x1800bb874  mov     rbx, [rbx]
0x1800bb877  mov     [rsp+0E0h+dwCreationFlags], esi; int
0x1800bb87b  mov     r9, rbx
0x1800bb87e  lea     r8, aDeleteandupdat_1; "DeleteAndUpdateAuthorityProvider GetThe"...
0x1800bb885  lea     rdx, OrchestratorGenericInformation
0x1800bb88c  call    McTemplateU0zzd_EventWriteTransfer
0x1800bb891  cmp     esi, 0FFFFFFFFh
0x1800bb894  jz      loc_1800BBA45
0x1800bb89a  add     r14, r14
0x1800bb89d  mov     rax, qword ptr [rbp+47h+var_98]
0x1800bb8a1  mov     rdi, [rax+r14*8]
0x1800bb8a5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x1800bb8ac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x1800bb8b1  test    al, al
0x1800bb8b3  jz      short loc_1800BB8EA
0x1800bb8b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bb8bc  mov     ecx, 60h ; '`'; unsigned __int64
0x1800bb8c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800bb8c6  mov     [rbp+47h+var_68], rax
0x1800bb8ca  test    rax, rax
0x1800bb8cd  jz      short loc_1800BB8E3
0x1800bb8cf  mov     rcx, rax; this
0x1800bb8d2  call    ??0DCAuthorityInfo@@QEAA@XZ; DCAuthorityInfo::DCAuthorityInfo(void)
0x1800bb8d7  mov     rbx, rax
0x1800bb8da  test    rax, rax
0x1800bb8dd  jnz     loc_1800BB968
0x1800bb8e3  mov     edx, 2C5h
0x1800bb8e8  jmp     short loc_1800BB90F
0x1800bb8ea  call    cs:__imp_GetProcessHeap
0x1800bb8f0  mov     rcx, rax; hHeap
0x1800bb8f3  mov     edx, 8; dwFlags
0x1800bb8f8  lea     r8d, [rdx+58h]; dwBytes
0x1800bb8fc  call    cs:__imp_HeapAlloc
0x1800bb902  mov     rbx, rax
0x1800bb905  test    rax, rax
0x1800bb908  jnz     short loc_1800BB960
0x1800bb90a  mov     edx, 2CDh; void *
0x1800bb90f  mov     r9d, 8007000Eh; char *
0x1800bb915  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800bb91c  mov     rcx, [rbp+4Fh]; this
0x1800bb920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb925  nop
0x1800bb926  lea     rcx, [rbp+47h+var_80]
0x1800bb92a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800bb92f  nop
0x1800bb930  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb934  test    rcx, rcx
0x1800bb937  jz      short loc_1800BB956
0x1800bb939  mov     rdx, [rbp+47h+var_90]
0x1800bb93d  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDCProviderOrchestration@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDCProviderOrchestration@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(std::shared_ptr<DCProviderOrchestration> *,std::shared_ptr<DCProviderOrchestration> * const,std::allocator<std::shared_ptr<DCProviderOrchestration>> &)
0x1800bb942  mov     rcx, qword ptr [rbp+47h+var_98]
0x1800bb946  mov     rdx, [rbp+47h+var_88]
0x1800bb94a  sub     rdx, rcx
0x1800bb94d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800bb951  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800bb956  mov     eax, 8007000Eh
0x1800bb95b  jmp     loc_1800BBA76
0x1800bb960  mov     rcx, rax; this
  ... truncated ...
```
