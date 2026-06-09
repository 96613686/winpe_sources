# SemanticTextRegionStream::Complete(uint *,tagSemanticVector * *)

- ea: `0x180034a00`
- end: `0x180034dd2`
- name: `?Complete@SemanticTextRegionStream@@UEAAJPEAIPEAPEAUtagSemanticVector@@@Z`
- size: `978`
- prototype: `__int64 __fastcall(SemanticTextRegionStream *__hidden this, unsigned int *, struct tagSemanticVector **)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007fae`
- `0x18000c478`
- `0x1800187b0`
- `0x180019c3c`
- `0x180022760`
- `0x180028c20`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180034a00`
- `0x180036954`
- `0x180036d18`
- `0x1800373cc`
- `0x180049a80`
- `0x18004cb7c`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034c10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034c10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034a63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034b1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034be3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034a63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034b1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034be3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d7f`

## string_xrefs

- `0x180034a29`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180034ce3`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180034b6d`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180034dbf`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180034a1d`: `Complete : Started`
- `0x180034cd7`: `Complete : Successfully generated vector using AIFabric. EmbeddingCount: %u`
- `0x180034b5e`: `Failed to complete TextRegionStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SemanticTextRegionStream::Complete(
        SemanticTextRegionStream *this,
        unsigned int *a2,
        struct tagSemanticVector **a3,
        const wchar_t *a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  LPVOID v10; // rbx
  int matched; // esi
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  int v13; // edi
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  const char *v15; // r9
  __int64 result; // rax
  _DWORD *v17; // rdi
  struct _RTL_CRITICAL_SECTION *v18; // rsi
  __int64 v19; // rsi
  struct tagSemanticVector *v20; // rax
  const char *v21; // r9
  __int64 i; // rdi
  __int128 *v23; // rax
  __int128 v24; // xmm1
  __int128 v25; // xmm2
  __int64 v26; // r14
  __int64 v27; // rax
  char *v28; // rdi
  char *v29; // rsi
  struct _RTL_CRITICAL_SECTION *v30; // rbx
  const char *v31; // [rsp+28h] [rbp-B0h]
  LPVOID v32; // [rsp+30h] [rbp-A8h] BYREF
  wchar_t *v33; // [rsp+38h] [rbp-A0h]
  LPVOID v34; // [rsp+40h] [rbp-98h] BYREF
  int v35; // [rsp+48h] [rbp-90h] BYREF
  LPVOID v36[2]; // [rsp+50h] [rbp-88h]
  LPVOID v37; // [rsp+60h] [rbp-78h]
  _BYTE v38[8]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v39[48]; // [rsp+78h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  LPVOID v42; // [rsp+E0h] [rbp+8h] BYREF
  LPVOID v43; // [rsp+F8h] [rbp+20h] BYREF

  SearchIndexerTrace::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0xC1C,
    (unsigned int)L"Complete : Started",
    a4);
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v38);
  v7 = (struct _RTL_CRITICAL_SECTION *)pv;
  v42 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v7 + 5);
  ++LODWORD(v7[6].DebugInfo);
  LODWORD(v7[6].SpinCount) = 7;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v42);
  v42 = 0;
  v8 = *((_QWORD *)this + 3);
  v35 = 0;
  *(_OWORD *)v36 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 80LL))(v8, &v42);
  try
  {
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v35);
    v10 = v42;
    v43 = v42;
    if ( (unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(&v43) )
    {
      v17 = pv;
      v18 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      v17[18] |= 0x300u;
      if ( *((_QWORD *)v17 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v17 + 2, 2);
      if ( v18 )
        LeaveCriticalSection(v18);
      winrt::impl::consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult<winrt::Microsoft::Windows::SemanticSearch::IMultipleEmbeddingsResult>::Embeddings(
        &v43,
        &v32);
      v19 = (unsigned int)v33;
      if ( (_DWORD)v33 )
      {
        *a2 = (unsigned int)v33;
        v20 = (struct tagSemanticVector *)CoTaskMemAlloc(32 * v19);
        if ( !v20 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xC2E,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            v21);
        *a3 = v20;
        for ( i = 0; (unsigned int)i < (unsigned int)v19; i = (unsigned int)(i + 1) )
        {
          v23 = (__int128 *)anonymous_namespace_::EmbeddingToSemanticVector(
                              &v35,
                              *((_QWORD *)this + 4),
                              (char *)v32 + 8 * i);
          v24 = *v23;
          v25 = v23[1];
          *v23 = 0;
          v23[1] = 0;
          v26 = 32LL * (unsigned int)i;
          v27 = (__int64)*a3;
          *(_OWORD *)(v26 + v27) = v24;
          *(_OWORD *)(v26 + v27 + 16) = v25;
          if ( v36[0] )
          {
            CoTaskMemFree(v36[0]);
            v36[0] = 0;
          }
          if ( v37 )
            CoTaskMemFree(v37);
          SearchIndexerTrace::Verbose(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            (const wchar_t *)0xC32,
            (unsigned int)L"Complete : Successfully generated vector using AIFabric. EmbeddingCount: %u",
            (const wchar_t *)(unsigned int)v19);
        }
        LODWORD(v19) = (_DWORD)v33;
      }
      else
      {
        *a2 = (unsigned int)v33;
        *a3 = 0;
      }
      v28 = (char *)v32;
      if ( v32 )
      {
        v29 = (char *)v32 + 8 * (unsigned int)v19;
        if ( v32 != v29 )
        {
          do
          {
            if ( *(_QWORD *)v28 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v28);
            v28 += 8;
          }
          while ( v28 != v29 );
          v28 = (char *)v32;
        }
        CoTaskMemFree_0(v28);
        v32 = 0;
        LODWORD(v33) = 0;
      }
      if ( v10 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v43);
      v30 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v30);
        CoTaskMemFree(v30);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v39);
      result = 0;
    }
    else
    {
      matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v43);
      v12 = (struct _RTL_CRITICAL_SECTION *)pv;
      v34 = pv;
      if ( pv )
      {
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        v10 = v42;
      }
      EnterCriticalSection(v12 + 5);
      ++LODWORD(v12[6].DebugInfo);
      LODWORD(v12[7].DebugInfo) = matched;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v34);
      v13 = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
                         &v43,
                         &v42);
      if ( v13 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xC24,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const char *)(unsigned int)v13,
          (int)"Failed to complete TextRegionStream",
          v31);
      if ( v10 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v43);
      v14 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v14);
        CoTaskMemFree(v14);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v39);
      result = (unsigned int)v13;
    }
  }
  catch ( ... )
  {
    LODWORD(v42) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xC3D,
                     (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                     v15);
    return (unsigned int)v42;
  }
  return result;
}

```

## disassembly

```asm
0x180034a00  mov     [rsp+arg_8], rbx
0x180034a05  push    rsi
0x180034a06  push    rdi
0x180034a07  push    r13
0x180034a09  push    r14
0x180034a0b  push    r15
0x180034a0d  sub     rsp, 0B0h
0x180034a14  mov     r15, r8
0x180034a17  mov     r14, rdx
0x180034a1a  mov     r13, rcx
0x180034a1d  lea     r8, aCompleteStarte; "Complete : Started"
0x180034a24  mov     edx, 0C1Ch; wchar_t *
0x180034a29  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180034a30  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180034a35  lea     rcx, [rsp+0D8h+var_68]
0x180034a3a  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180034a3f  nop
0x180034a40  mov     rbx, [rsp+0D8h+pv]
0x180034a48  mov     [rsp+0D8h+arg_0], rbx
0x180034a50  test    rbx, rbx
0x180034a53  jz      short loc_180034A5C
0x180034a55  lock inc dword ptr [rbx+120h]
0x180034a5c  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180034a63  call    cs:__imp_EnterCriticalSection
0x180034a69  inc     dword ptr [rbx+0F0h]
0x180034a6f  mov     dword ptr [rbx+110h], 7
0x180034a79  lea     rcx, [rsp+0D8h+arg_0]
0x180034a81  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180034a86  mov     [rsp+0D8h+arg_0], 0
0x180034a92  mov     rcx, [r13+18h]
0x180034a96  mov     [rsp+0D8h+var_90], 0
0x180034a9e  xorps   xmm0, xmm0
0x180034aa1  movdqu  xmmword ptr [rsp+0D8h+var_88], xmm0
0x180034aa7  mov     rax, [rcx]
0x180034aaa  lea     rdx, [rsp+0D8h+arg_0]
0x180034ab2  mov     rax, [rax+50h]
0x180034ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034abb  test    eax, eax
0x180034abd  js      loc_180034DB2
0x180034ac3  mov     rbx, [rsp+0D8h+arg_0]
0x180034acb  mov     [rsp+0D8h+arg_18], rbx
0x180034ad3  lea     rcx, [rsp+0D8h+arg_18]
0x180034adb  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x180034ae0  test    al, al
0x180034ae2  jnz     loc_180034BD1
0x180034ae8  lea     rcx, [rsp+0D8h+arg_18]
0x180034af0  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x180034af5  mov     esi, eax
0x180034af7  mov     rdi, [rsp+0D8h+pv]
0x180034aff  mov     [rsp+0D8h+var_98], rdi
0x180034b04  test    rdi, rdi
0x180034b07  jz      short loc_180034B18
0x180034b09  lock inc dword ptr [rdi+120h]
0x180034b10  mov     rbx, [rsp+0D8h+arg_0]
0x180034b18  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180034b1f  call    cs:__imp_EnterCriticalSection
0x180034b25  inc     dword ptr [rdi+0F0h]
0x180034b2b  mov     [rdi+118h], esi
0x180034b31  lea     rcx, [rsp+0D8h+var_98]
0x180034b36  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180034b3b  lea     rdx, [rsp+0D8h+arg_0]
0x180034b43  lea     rcx, [rsp+0D8h+arg_18]
0x180034b4b  call    ?ExtendedError@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(void)
0x180034b50  mov     edi, [rax]
0x180034b52  test    edi, edi
0x180034b54  jns     short loc_180034B7F
0x180034b56  mov     rcx, [rsp+0D8h]; this
0x180034b5e  lea     rax, aFailedToComple; "Failed to complete TextRegionStream"
0x180034b65  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x180034b6a  mov     r9d, edi; char *
0x180034b6d  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180034b74  mov     edx, 0C24h; void *
0x180034b79  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034b7e  nop
0x180034b7f  test    rbx, rbx
0x180034b82  jz      short loc_180034B92
0x180034b84  lea     rcx, [rsp+0D8h+arg_18]
0x180034b8c  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180034b91  nop
0x180034b92  mov     rbx, [rsp+0D8h+pv]
0x180034b9a  test    rbx, rbx
0x180034b9d  jz      short loc_180034BC0
0x180034b9f  or      edx, 0FFFFFFFFh
0x180034ba2  lock xadd [rbx+120h], edx
0x180034baa  cmp     edx, 1
0x180034bad  jnz     short loc_180034BC0
0x180034baf  mov     rcx, rbx
0x180034bb2  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180034bb7  mov     rcx, rbx; pv
0x180034bba  call    cs:__imp_CoTaskMemFree
0x180034bc0  lea     rcx, [rsp+0D8h+var_60]; this
0x180034bc5  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180034bca  mov     eax, edi
0x180034bcc  jmp     loc_180034D9A
0x180034bd1  mov     rdi, [rsp+0D8h+pv]
0x180034bd9  lea     rsi, [rdi+0C8h]
0x180034be0  mov     rcx, rsi; lpCriticalSection
0x180034be3  call    cs:__imp_EnterCriticalSection
0x180034be9  or      dword ptr [rdi+48h], 300h
0x180034bf0  cmp     qword ptr [rdi+0F8h], 0
0x180034bf8  jz      short loc_180034C08
0x180034bfa  mov     edx, 2
0x180034bff  lea     rcx, [rdi+8]
0x180034c03  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180034c08  test    rsi, rsi
0x180034c0b  jz      short loc_180034C16
0x180034c0d  mov     rcx, rsi; lpCriticalSection
0x180034c10  call    cs:__imp_LeaveCriticalSection
0x180034c16  lea     rdx, [rsp+0D8h+var_A8]
0x180034c1b  lea     rcx, [rsp+0D8h+arg_18]
0x180034c23  call    ?Embeddings@?$consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult@UIMultipleEmbeddingsResult@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult<winrt::Microsoft::Windows::SemanticSearch::IMultipleEmbeddingsResult>::Embeddings(void)
0x180034c28  nop
0x180034c29  mov     esi, dword ptr [rsp+0D8h+var_A0]
0x180034c2d  test    esi, esi
0x180034c2f  jnz     short loc_180034C40
0x180034c31  mov     [r14], esi
0x180034c34  mov     qword ptr [r15], 0
0x180034c3b  jmp     loc_180034CFA
0x180034c40  mov     [r14], esi
0x180034c43  mov     rcx, rsi
0x180034c46  shl     rcx, 5; cb
0x180034c4a  call    cs:__imp_CoTaskMemAlloc
0x180034c50  mov     rcx, [rsp+0D8h]; this
0x180034c58  test    rax, rax
0x180034c5b  jz      loc_180034DBF
0x180034c61  mov     [r15], rax
0x180034c64  xor     edi, edi
0x180034c66  cmp     edi, esi
0x180034c68  jnb     loc_180034CF6
0x180034c6e  mov     r14d, edi
0x180034c71  mov     rax, [rsp+0D8h+var_A8]
0x180034c76  lea     r8, [rax+rdi*8]
0x180034c7a  mov     rdx, [r13+20h]
0x180034c7e  lea     rcx, [rsp+0D8h+var_90]
0x180034c83  call    _anonymous_namespace___EmbeddingToSemanticVector
0x180034c88  movups  xmm1, xmmword ptr [rax]
0x180034c8b  movups  xmm2, xmmword ptr [rax+10h]
0x180034c8f  xorps   xmm0, xmm0
0x180034c92  movups  xmmword ptr [rax], xmm0
0x180034c95  movups  xmmword ptr [rax+10h], xmm0
0x180034c99  shl     r14, 5
0x180034c9d  mov     rax, [r15]
0x180034ca0  movups  xmmword ptr [r14+rax], xmm1
0x180034ca5  movups  xmmword ptr [r14+rax+10h], xmm2
0x180034cab  mov     rcx, [rsp+0D8h+var_88]; pv
0x180034cb0  test    rcx, rcx
0x180034cb3  jz      short loc_180034CC4
0x180034cb5  call    cs:__imp_CoTaskMemFree
0x180034cbb  mov     [rsp+0D8h+var_88], 0
0x180034cc4  mov     rcx, [rsp+0D8h+var_78]; pv
0x180034cc9  test    rcx, rcx
0x180034ccc  jz      short loc_180034CD4
0x180034cce  call    cs:__imp_CoTaskMemFree
0x180034cd4  mov     r9d, esi; wchar_t *
0x180034cd7  lea     r8, aCompleteSucces; "Complete : Successfully generated vecto"...
0x180034cde  mov     edx, 0C32h; wchar_t *
0x180034ce3  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180034cea  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180034cef  inc     edi
0x180034cf1  jmp     loc_180034C66
0x180034cf6  mov     esi, dword ptr [rsp+0D8h+var_A0]
0x180034cfa  mov     rdi, [rsp+0D8h+var_A8]
0x180034cff  test    rdi, rdi
0x180034d02  jz      short loc_180034D44
0x180034d04  mov     eax, esi
0x180034d06  lea     rsi, [rdi+rax*8]
0x180034d0a  cmp     rdi, rsi
0x180034d0d  jz      short loc_180034D2B
0x180034d0f  cmp     qword ptr [rdi], 0
0x180034d13  jz      short loc_180034D1D
0x180034d15  mov     rcx, rdi
0x180034d18  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180034d1d  add     rdi, 8
0x180034d21  cmp     rdi, rsi
0x180034d24  jnz     short loc_180034D0F
0x180034d26  mov     rdi, [rsp+0D8h+var_A8]
0x180034d2b  mov     rcx, rdi; pv
0x180034d2e  call    CoTaskMemFree_0
0x180034d33  mov     [rsp+0D8h+var_A8], 0
0x180034d3c  mov     dword ptr [rsp+0D8h+var_A0], 0
0x180034d44  test    rbx, rbx
0x180034d47  jz      short loc_180034D57
0x180034d49  lea     rcx, [rsp+0D8h+arg_18]
0x180034d51  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180034d56  nop
0x180034d57  mov     rbx, [rsp+0D8h+pv]
0x180034d5f  test    rbx, rbx
0x180034d62  jz      short loc_180034D85
0x180034d64  or      eax, 0FFFFFFFFh
0x180034d67  lock xadd [rbx+120h], eax
0x180034d6f  cmp     eax, 1
0x180034d72  jnz     short loc_180034D85
0x180034d74  mov     rcx, rbx
0x180034d77  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180034d7c  mov     rcx, rbx; pv
0x180034d7f  call    cs:__imp_CoTaskMemFree
0x180034d85  lea     rcx, [rsp+0D8h+var_60]; this
0x180034d8a  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180034d8f  xor     eax, eax
0x180034d91  jmp     short loc_180034D9A
0x180034d93  mov     eax, dword ptr [rsp+0D8h+arg_0]
0x180034d9a  mov     rbx, [rsp+0D8h+arg_8]
0x180034da2  add     rsp, 0B0h
0x180034da9  pop     r15
0x180034dab  pop     r14
0x180034dad  pop     r13
0x180034daf  pop     rdi
0x180034db0  pop     rsi
0x180034db1  retn
0x180034db2  lea     rdx, [rsp+0D8h+var_90]
0x180034db7  mov     ecx, eax
0x180034db9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180034dbf  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180034dc6  mov     edx, 0C2Eh; void *
0x180034dcb  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
