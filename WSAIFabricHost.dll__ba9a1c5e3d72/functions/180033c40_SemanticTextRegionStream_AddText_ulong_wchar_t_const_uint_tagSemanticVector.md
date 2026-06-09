# SemanticTextRegionStream::AddText(ulong,wchar_t const *,uint *,tagSemanticVector * *)

- ea: `0x180033c40`
- end: `0x18003407e`
- name: `?AddText@SemanticTextRegionStream@@UEAAJKPEB_WPEAIPEAPEAUtagSemanticVector@@@Z`
- size: `1086`
- prototype: `int(SemanticTextRegionStream *__hidden this, unsigned int, const wchar_t *, unsigned int *, struct tagSemanticVector **)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x180007fae`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x1800187b0`
- `0x180019c3c`
- `0x180022760`
- `0x180028c20`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180033c40`
- `0x180036954`
- `0x180036d18`
- `0x1800373cc`
- `0x180049a80`
- `0x18004cb7c`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033edb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033edb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033eb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033eb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033cb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033db5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033cb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033db5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034026`

## string_xrefs

- `0x180033c77`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180033f8f`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180033e03`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003406b`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SemanticTextRegionStream::AddText(
        SemanticTextRegionStream *this,
        unsigned int a2,
        const wchar_t *a3,
        unsigned int *a4,
        struct tagSemanticVector **a5)
{
  __int64 v7; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  unsigned int v10; // edx
  volatile signed __int32 *v11; // rdi
  __int64 v12; // rcx
  int v13; // eax
  void *v14; // rbx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  int matched; // edi
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  int v19; // edi
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  const char *v21; // r9
  __int64 result; // rax
  _DWORD *v23; // rdi
  struct _RTL_CRITICAL_SECTION *v24; // rsi
  __int64 v25; // rsi
  struct tagSemanticVector *v26; // rax
  const char *v27; // r9
  struct tagSemanticVector **v28; // r12
  __int64 i; // rdi
  __int128 *v30; // rax
  __int128 v31; // xmm1
  __int128 v32; // xmm2
  __int64 v33; // r15
  struct tagSemanticVector *v34; // rax
  char *v35; // rdi
  char *v36; // rsi
  struct _RTL_CRITICAL_SECTION *v37; // rbx
  const char *v38; // [rsp+28h] [rbp-B0h]
  void *v39; // [rsp+30h] [rbp-A8h] BYREF
  LPVOID v40; // [rsp+38h] [rbp-A0h] BYREF
  wchar_t *v41; // [rsp+40h] [rbp-98h]
  LPVOID v42; // [rsp+48h] [rbp-90h] BYREF
  int v43; // [rsp+50h] [rbp-88h] BYREF
  LPVOID v44[2]; // [rsp+58h] [rbp-80h]
  LPVOID v45; // [rsp+68h] [rbp-70h]
  char v46[8]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v47[48]; // [rsp+78h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  LPVOID v50; // [rsp+E0h] [rbp+8h] BYREF
  int v51; // [rsp+E8h] [rbp+10h] BYREF

  v7 = a2;
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0xBF4,
    (unsigned int)L"AddText : inputLength: %lu",
    (const wchar_t *)a2);
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v46);
  v9 = (struct _RTL_CRITICAL_SECTION *)pv;
  v50 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v9 + 5);
  ++LODWORD(v9[6].DebugInfo);
  LODWORD(v9[6].SpinCount) = 6;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v50);
  try
  {
    if ( (_DWORD)v7 )
    {
      v11 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v7, v10);
      memcpy_s((void *const)(v11 + 7), 2 * v7, a3, 2 * v7);
    }
    else
    {
      v11 = 0;
    }
    v50 = (LPVOID)v11;
    v39 = 0;
    v12 = *((_QWORD *)this + 3);
    v43 = 0;
    *(_OWORD *)v44 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, void **))(*(_QWORD *)v12 + 72LL))(
            v12,
            v11,
            &v39);
    if ( v13 < 0 )
      winrt::throw_hresult((unsigned int)v13, &v43);
    v14 = v39;
    v50 = v39;
    if ( v11 )
    {
      v15 = _InterlockedDecrement(v11 + 6);
      if ( v15 )
      {
        if ( v15 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v11);
      }
    }
    if ( (unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(&v50) )
    {
      winrt::impl::consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult<winrt::Microsoft::Windows::SemanticSearch::IMultipleEmbeddingsResult>::Embeddings(
        &v50,
        &v40);
      v23 = pv;
      v24 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      v23[18] |= 0x300u;
      if ( *((_QWORD *)v23 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v23 + 2, 2);
      if ( v24 )
        LeaveCriticalSection(v24);
      v25 = (unsigned int)v41;
      if ( (_DWORD)v41 )
      {
        *a4 = (unsigned int)v41;
        v26 = (struct tagSemanticVector *)CoTaskMemAlloc(32 * v25);
        if ( !v26 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xC06,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            v27);
        v28 = a5;
        *a5 = v26;
        for ( i = 0; (unsigned int)i < (unsigned int)v25; i = (unsigned int)(i + 1) )
        {
          v30 = (__int128 *)anonymous_namespace_::EmbeddingToSemanticVector(
                              &v43,
                              *((_QWORD *)this + 4),
                              (char *)v40 + 8 * i);
          v31 = *v30;
          v32 = v30[1];
          *v30 = 0;
          v30[1] = 0;
          v33 = 32LL * (unsigned int)i;
          v34 = *v28;
          *(_OWORD *)((char *)v34 + v33) = v31;
          *(_OWORD *)((char *)v34 + v33 + 16) = v32;
          if ( v44[0] )
          {
            CoTaskMemFree(v44[0]);
            v44[0] = 0;
          }
          if ( v45 )
            CoTaskMemFree(v45);
          SearchIndexerTrace::Verbose(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            (const wchar_t *)0xC0A,
            (unsigned int)L"AddText : Successfully generated vector using AIFabric. EmbeddingCount: %u",
            (const wchar_t *)(unsigned int)v25);
        }
        LODWORD(v25) = (_DWORD)v41;
      }
      else
      {
        *a4 = 0;
        *a5 = 0;
      }
      v35 = (char *)v40;
      if ( v40 )
      {
        v36 = (char *)v40 + 8 * (unsigned int)v25;
        if ( v40 != v36 )
        {
          do
          {
            if ( *(_QWORD *)v35 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v35);
            v35 += 8;
          }
          while ( v35 != v36 );
          v35 = (char *)v40;
        }
        CoTaskMemFree_0(v35);
        v40 = 0;
        LODWORD(v41) = 0;
      }
      if ( v14 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v50);
      v37 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v37);
        CoTaskMemFree(v37);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v47);
      result = 0;
    }
    else
    {
      matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v50);
      v18 = (struct _RTL_CRITICAL_SECTION *)pv;
      v42 = pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v18 + 5);
      ++LODWORD(v18[6].DebugInfo);
      LODWORD(v18[7].DebugInfo) = matched;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v42);
      v19 = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
                         &v50,
                         &v51);
      if ( v19 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xBFC,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const char *)(unsigned int)v19,
          (int)"Failed to AppendText to TextRegionStream",
          v38);
      if ( v39 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v50);
      v20 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v20);
        CoTaskMemFree(v20);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v47);
      result = (unsigned int)v19;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC15,
                           (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x180033c40  mov     [rsp+arg_10], rbx
0x180033c45  mov     [rsp+arg_18], rsi
0x180033c4a  push    rdi
0x180033c4b  push    r12
0x180033c4d  push    r13
0x180033c4f  push    r14
0x180033c51  push    r15
0x180033c53  sub     rsp, 0B0h
0x180033c5a  mov     r15, r9
0x180033c5d  mov     r14, r8
0x180033c60  mov     esi, edx
0x180033c62  mov     r13, rcx
0x180033c65  xor     r12d, r12d
0x180033c68  mov     r9d, esi; wchar_t *
0x180033c6b  lea     r8, aAddtextInputle; "AddText : inputLength: %lu"
0x180033c72  mov     edx, 0BF4h; wchar_t *
0x180033c77  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180033c7e  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180033c83  lea     rcx, [rsp+0D8h+var_68]
0x180033c88  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180033c8d  nop
0x180033c8e  mov     rbx, [rsp+0D8h+pv]
0x180033c96  mov     [rsp+0D8h+arg_0], rbx
0x180033c9e  test    rbx, rbx
0x180033ca1  jz      short loc_180033CAA
0x180033ca3  lock inc dword ptr [rbx+120h]
0x180033caa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180033cb1  call    cs:__imp_EnterCriticalSection
0x180033cb7  inc     dword ptr [rbx+0F0h]
0x180033cbd  mov     dword ptr [rbx+110h], 6
0x180033cc7  lea     rcx, [rsp+0D8h+arg_0]
0x180033ccf  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180033cd4  test    esi, esi
0x180033cd6  jnz     short loc_180033CDD
0x180033cd8  mov     rdi, r12
0x180033cdb  jmp     short loc_180033CFC
0x180033cdd  mov     ecx, esi; this
0x180033cdf  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180033ce4  mov     rdi, rax
0x180033ce7  mov     rdx, rsi
0x180033cea  add     rdx, rdx; DestinationSize
0x180033ced  lea     rcx, [rax+1Ch]; Destination
0x180033cf1  mov     r9, rdx; SourceSize
0x180033cf4  mov     r8, r14; Source
0x180033cf7  call    memcpy_s
0x180033cfc  mov     [rsp+0D8h+arg_0], rdi
0x180033d04  mov     [rsp+0D8h+var_A8], r12
0x180033d09  mov     rcx, [r13+18h]
0x180033d0d  mov     [rsp+0D8h+var_88], r12d
0x180033d12  xorps   xmm0, xmm0
0x180033d15  movdqu  xmmword ptr [rsp+0D8h+var_80], xmm0
0x180033d1b  mov     rax, [rcx]
0x180033d1e  lea     r8, [rsp+0D8h+var_A8]
0x180033d23  mov     rdx, rdi
0x180033d26  mov     rax, [rax+48h]
0x180033d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d2f  test    eax, eax
0x180033d31  js      loc_18003405E
0x180033d37  mov     rbx, [rsp+0D8h+var_A8]
0x180033d3c  mov     [rsp+0D8h+arg_0], rbx
0x180033d44  or      r14d, 0FFFFFFFFh
0x180033d48  test    rdi, rdi
0x180033d4b  jz      short loc_180033D71
0x180033d4d  mov     eax, r14d
0x180033d50  lock xadd [rdi+18h], eax
0x180033d55  sub     eax, 1
0x180033d58  jnz     loc_180033ED3
0x180033d5e  nop
0x180033d5f  call    WINRT_IMPL_GetProcessHeap
0x180033d64  mov     rcx, rax; hHeap
0x180033d67  mov     r8, rdi; lpMem
0x180033d6a  xor     edx, edx; dwFlags
0x180033d6c  call    WINRT_IMPL_HeapFree
0x180033d71  lea     rcx, [rsp+0D8h+arg_0]
0x180033d79  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x180033d7e  lea     rcx, [rsp+0D8h+arg_0]
0x180033d86  test    al, al
0x180033d88  jnz     loc_180033E69
0x180033d8e  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x180033d93  mov     edi, eax
0x180033d95  mov     rbx, [rsp+0D8h+pv]
0x180033d9d  mov     [rsp+0D8h+var_90], rbx
0x180033da2  test    rbx, rbx
0x180033da5  jz      short loc_180033DAE
0x180033da7  lock inc dword ptr [rbx+120h]
0x180033dae  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180033db5  call    cs:__imp_EnterCriticalSection
0x180033dbb  inc     dword ptr [rbx+0F0h]
0x180033dc1  mov     [rbx+118h], edi
0x180033dc7  lea     rcx, [rsp+0D8h+var_90]
0x180033dcc  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180033dd1  lea     rdx, [rsp+0D8h+arg_8]
0x180033dd9  lea     rcx, [rsp+0D8h+arg_0]
0x180033de1  call    ?ExtendedError@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(void)
0x180033de6  mov     edi, [rax]
0x180033de8  test    edi, edi
0x180033dea  jns     short loc_180033E15
0x180033dec  mov     rcx, [rsp+0D8h]; this
0x180033df4  lea     rax, aFailedToAppend; "Failed to AppendText to TextRegionStrea"...
0x180033dfb  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x180033e00  mov     r9d, edi; char *
0x180033e03  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180033e0a  mov     edx, 0BFCh; void *
0x180033e0f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033e14  nop
0x180033e15  cmp     [rsp+0D8h+var_A8], r12
0x180033e1a  jz      short loc_180033E2A
0x180033e1c  lea     rcx, [rsp+0D8h+arg_0]
0x180033e24  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180033e29  nop
0x180033e2a  mov     rbx, [rsp+0D8h+pv]
0x180033e32  test    rbx, rbx
0x180033e35  jz      short loc_180033E58
0x180033e37  mov     edx, r14d
0x180033e3a  lock xadd [rbx+120h], edx
0x180033e42  add     edx, r14d
0x180033e45  jnz     short loc_180033E58
0x180033e47  mov     rcx, rbx
0x180033e4a  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180033e4f  mov     rcx, rbx; pv
0x180033e52  call    cs:__imp_CoTaskMemFree
0x180033e58  lea     rcx, [rsp+0D8h+var_60]; this
0x180033e5d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180033e62  mov     eax, edi
0x180033e64  jmp     loc_180034041
0x180033e69  lea     rdx, [rsp+0D8h+var_A0]
0x180033e6e  call    ?Embeddings@?$consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult@UIMultipleEmbeddingsResult@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult<winrt::Microsoft::Windows::SemanticSearch::IMultipleEmbeddingsResult>::Embeddings(void)
0x180033e73  nop
0x180033e74  mov     rdi, [rsp+0D8h+pv]
0x180033e7c  lea     rsi, [rdi+0C8h]
0x180033e83  mov     rcx, rsi; lpCriticalSection
0x180033e86  call    cs:__imp_EnterCriticalSection
0x180033e8c  or      dword ptr [rdi+48h], 300h
0x180033e93  cmp     [rdi+0F8h], r12
0x180033e9a  jz      short loc_180033EAA
0x180033e9c  mov     edx, 2
0x180033ea1  lea     rcx, [rdi+8]
0x180033ea5  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180033eaa  test    rsi, rsi
0x180033ead  jz      short loc_180033EB8
0x180033eaf  mov     rcx, rsi; lpCriticalSection
0x180033eb2  call    cs:__imp_LeaveCriticalSection
0x180033eb8  mov     esi, dword ptr [rsp+0D8h+var_98]
0x180033ebc  test    esi, esi
0x180033ebe  jnz     short loc_180033EE2
0x180033ec0  mov     [r15], r12d
0x180033ec3  mov     rax, [rsp+0D8h+arg_20]
0x180033ecb  mov     [rax], r12
0x180033ece  jmp     loc_180033FA9
0x180033ed3  test    eax, eax
0x180033ed5  jns     loc_180033D71
0x180033edb  call    cs:__imp_abort
0x180033ee2  mov     [r15], esi
0x180033ee5  mov     rcx, rsi
0x180033ee8  shl     rcx, 5; cb
0x180033eec  call    cs:__imp_CoTaskMemAlloc
0x180033ef2  mov     rcx, [rsp+0D8h]; this
0x180033efa  test    rax, rax
0x180033efd  jz      loc_18003406B
0x180033f03  mov     r12, [rsp+0D8h+arg_20]
0x180033f0b  mov     [r12], rax
0x180033f0f  xor     edi, edi
0x180033f11  cmp     edi, esi
0x180033f13  jnb     loc_180033FA2
0x180033f19  mov     r15d, edi
0x180033f1c  mov     rax, [rsp+0D8h+var_A0]
0x180033f21  lea     r8, [rax+rdi*8]
0x180033f25  mov     rdx, [r13+20h]
0x180033f29  lea     rcx, [rsp+0D8h+var_88]
0x180033f2e  call    _anonymous_namespace___EmbeddingToSemanticVector
0x180033f33  movups  xmm1, xmmword ptr [rax]
0x180033f36  movups  xmm2, xmmword ptr [rax+10h]
0x180033f3a  xorps   xmm0, xmm0
0x180033f3d  movups  xmmword ptr [rax], xmm0
0x180033f40  movups  xmmword ptr [rax+10h], xmm0
0x180033f44  shl     r15, 5
0x180033f48  mov     rax, [r12]
0x180033f4c  movups  xmmword ptr [r15+rax], xmm1
0x180033f51  movups  xmmword ptr [r15+rax+10h], xmm2
0x180033f57  mov     rcx, [rsp+0D8h+var_80]; pv
0x180033f5c  test    rcx, rcx
0x180033f5f  jz      short loc_180033F70
0x180033f61  call    cs:__imp_CoTaskMemFree
0x180033f67  mov     [rsp+0D8h+var_80], 0
0x180033f70  mov     rcx, [rsp+0D8h+var_70]; pv
0x180033f75  test    rcx, rcx
0x180033f78  jz      short loc_180033F80
0x180033f7a  call    cs:__imp_CoTaskMemFree
0x180033f80  mov     r9d, esi; wchar_t *
0x180033f83  lea     r8, aAddtextSuccess; "AddText : Successfully generated vector"...
0x180033f8a  mov     edx, 0C0Ah; wchar_t *
0x180033f8f  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180033f96  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180033f9b  inc     edi
0x180033f9d  jmp     loc_180033F11
0x180033fa2  mov     esi, dword ptr [rsp+0D8h+var_98]
0x180033fa6  xor     r12d, r12d
0x180033fa9  mov     rdi, [rsp+0D8h+var_A0]
0x180033fae  test    rdi, rdi
0x180033fb1  jz      short loc_180033FEB
0x180033fb3  mov     eax, esi
0x180033fb5  lea     rsi, [rdi+rax*8]
0x180033fb9  cmp     rdi, rsi
0x180033fbc  jz      short loc_180033FD9
0x180033fbe  cmp     [rdi], r12
0x180033fc1  jz      short loc_180033FCB
0x180033fc3  mov     rcx, rdi
0x180033fc6  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180033fcb  add     rdi, 8
0x180033fcf  cmp     rdi, rsi
0x180033fd2  jnz     short loc_180033FBE
0x180033fd4  mov     rdi, [rsp+0D8h+var_A0]
0x180033fd9  mov     rcx, rdi; pv
0x180033fdc  call    CoTaskMemFree_0
0x180033fe1  mov     [rsp+0D8h+var_A0], r12
0x180033fe6  mov     dword ptr [rsp+0D8h+var_98], r12d
0x180033feb  test    rbx, rbx
0x180033fee  jz      short loc_180033FFE
0x180033ff0  lea     rcx, [rsp+0D8h+arg_0]
0x180033ff8  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180033ffd  nop
0x180033ffe  mov     rbx, [rsp+0D8h+pv]
0x180034006  test    rbx, rbx
0x180034009  jz      short loc_18003402C
0x18003400b  mov     eax, r14d
0x18003400e  lock xadd [rbx+120h], eax
0x180034016  add     eax, r14d
0x180034019  jnz     short loc_18003402C
0x18003401b  mov     rcx, rbx
0x18003401e  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180034023  mov     rcx, rbx; pv
0x180034026  call    cs:__imp_CoTaskMemFree
0x18003402c  lea     rcx, [rsp+0D8h+var_60]; this
0x180034031  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180034036  xor     eax, eax
0x180034038  jmp     short loc_180034041
0x18003403a  mov     eax, [rsp+0D8h+arg_8]
0x180034041  lea     r11, [rsp+0D8h+var_28]
0x180034049  mov     rbx, [r11+40h]
0x18003404d  mov     rsi, [r11+48h]
0x180034051  mov     rsp, r11
0x180034054  pop     r15
0x180034056  pop     r14
0x180034058  pop     r13
0x18003405a  pop     r12
0x18003405c  pop     rdi
0x18003405d  retn
0x18003405e  lea     rdx, [rsp+0D8h+var_88]
0x180034063  mov     ecx, eax
0x180034065  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003406b  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180034072  mov     edx, 0C06h; void *
0x180034077  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
