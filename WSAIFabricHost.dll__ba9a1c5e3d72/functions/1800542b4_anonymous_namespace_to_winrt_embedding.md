# _anonymous_namespace_::to_winrt_embedding

- ea: `0x1800542b4`
- end: `0x1800548cd`
- name: `_anonymous_namespace_::to_winrt_embedding`
- size: `1561`
- prototype: `gsl::details *__fastcall(gsl::details *, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033500`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x180008f84`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x1800187b0`
- `0x180019c3c`
- `0x1800228b0`
- `0x18002fa8c`
- `0x1800319dc`
- `0x180031cbc`
- `0x1800326e8`
- `0x180048660`
- `0x18004ba10`
- `0x18004ce18`
- `0x18004d098`
- `0x18004dea8`
- `0x18004df50`
- `0x180054244`
- `0x1800542b4`
- `0x18007b784`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180054619`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180054624`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180054619`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180054624`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054475`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054401`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054449`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800543bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054401`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054449`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005431c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005466f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005431c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005466f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005432a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005432a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005467d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005467d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054656`

## string_xrefs

- `0x18005435b`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180054487`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18005481c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18005484b`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18005488c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800548bb`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18005447b`: `Completed emb decryption`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
gsl::details *__fastcall anonymous_namespace_::to_winrt_embedding(gsl::details *a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v8; // r9d
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  void *v11; // r12
  const wchar_t *v12; // r9
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  _DWORD *v16; // rsi
  struct _RTL_CRITICAL_SECTION *v17; // rbx
  const wchar_t *v18; // r9
  gsl::details *v19; // rcx
  unsigned int v20; // edx
  _WORD *v21; // r15
  __int64 v22; // rbx
  struct winrt::impl::shared_hstring_header *v23; // rdi
  volatile signed __int32 *v24; // r14
  unsigned int v25; // r15d
  const void *v26; // rbx
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  HANDLE v30; // rax
  int v31; // eax
  HANDLE v32; // rax
  void *v33; // rbx
  HANDLE v34; // rax
  struct winrt::impl::shared_hstring_header *v35; // rbx
  __int64 v36; // r15
  const wchar_t *v37; // rcx
  __int64 v38; // rsi
  LPVOID *v39; // rcx
  char v40; // bl
  LPVOID v41; // rax
  char v42; // bl
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  const char *v48; // [rsp+28h] [rbp-B1h]
  __int64 v49; // [rsp+30h] [rbp-A9h] BYREF
  unsigned __int64 v50; // [rsp+38h] [rbp-A1h]
  LPVOID v51; // [rsp+40h] [rbp-99h] BYREF
  LPVOID v52; // [rsp+48h] [rbp-91h] BYREF
  struct winrt::impl::shared_hstring_header *v53; // [rsp+50h] [rbp-89h] BYREF
  __int64 v54; // [rsp+58h] [rbp-81h]
  _QWORD v55[2]; // [rsp+60h] [rbp-79h] BYREF
  SIZE_T v56; // [rsp+70h] [rbp-69h]
  unsigned __int64 v57; // [rsp+78h] [rbp-61h]
  int v58; // [rsp+80h] [rbp-59h]
  __int64 *v59; // [rsp+88h] [rbp-51h]
  char v60[8]; // [rsp+90h] [rbp-49h] BYREF
  char v61[48]; // [rsp+98h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp-11h]
  void *v63; // [rsp+D0h] [rbp-9h]
  int v64; // [rsp+D8h] [rbp-1h] BYREF
  __int128 v65; // [rsp+E0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v58 = 0;
  v8 = *(_DWORD *)(a4 + 16);
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      v45 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const char *)v45,
        (int)"Unexpected SemanticVector type.",
        v48);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl'::`2'::impl) )
    {
      v47 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const char *)v47,
        (int)"Unexpected SemanticVector type.",
        v48);
    }
    if ( *(_DWORD *)(a4 + 32) < 0x1Cu )
    {
      v46 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const char *)v46,
        (int)"Embedding blob must be at least the size of metadata.",
        v48);
    }
    v9 = *(unsigned int *)(a4 + 32) - 28LL;
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 0, v9);
    v63 = v11;
    v55[1] = *(_QWORD *)(a4 + 40);
    v12 = (const wchar_t *)*(unsigned int *)(a4 + 32);
    v55[0] = v12;
    v56 = v9;
    v57 = (unsigned __int64)v11;
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0xBE,
      (unsigned int)L"Invoked enclave emb decryption with input size: %lu",
      v12);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>>(v60);
    v13 = (struct _RTL_CRITICAL_SECTION *)pv;
    v51 = pv;
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v13 + 5);
    ++LODWORD(v13[6].DebugInfo);
    v14 = (struct _RTL_CRITICAL_SECTION *)pv;
    v52 = pv;
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v14 + 5);
    ++LODWORD(v14[6].DebugInfo);
    LOBYTE(v14[6].SpinCount) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(&v52);
    tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(&v51);
    v15 = (struct _RTL_CRITICAL_SECTION *)pv;
    v52 = pv;
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v15 + 5);
    ++LODWORD(v15[6].DebugInfo);
    v15[7].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v55[0];
    tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(&v52);
    (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)a2 + 16LL))(a2, 2, v55);
    v16 = pv;
    v17 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v16[18] |= 0x300u;
    if ( *((_QWORD *)v16 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v16 + 2, 2);
    if ( v17 )
      LeaveCriticalSection(v17);
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0xC6,
      (unsigned int)L"Completed emb decryption",
      v18);
    if ( v56 == -1 || !v57 && v56 )
      gsl::details::terminate(v19);
    v49 = v56;
    v50 = v57;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54352721>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54352721>::GetImpl'::`2'::impl) )
    {
      anonymous_namespace_::create_from_blob((__int64)a1, (int *)&v49);
LABEL_45:
      v33 = pv;
      if ( pv && !_InterlockedDecrement((volatile signed __int32 *)pv + 72) )
      {
        tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(v33);
        CoTaskMemFree(v33);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v61);
      if ( v11 )
      {
        v34 = GetProcessHeap();
        HeapFree(v34, 0, v11);
      }
      return a1;
    }
    anonymous_namespace_::create_from_blob((__int64)&v51, (int *)&v49);
    v59 = (__int64 *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(
                       &v51,
                       &v52);
    v21 = *(_WORD **)(a4 + 8);
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    if ( (_DWORD)v22 )
    {
      v23 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v22, v20);
      memcpy_s((char *)v23 + 28, 2LL * (unsigned int)v22, v21, 2LL * (unsigned int)v22);
    }
    else
    {
      v23 = 0;
    }
    v53 = v23;
    if ( v23 )
    {
      if ( (*(_BYTE *)v23 & 1) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v23 + 6);
        v24 = (volatile signed __int32 *)v23;
        goto LABEL_30;
      }
      v25 = *((_DWORD *)v23 + 1);
      if ( v25 )
      {
        v26 = (const void *)*((_QWORD *)v23 + 2);
        v24 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v25, v20);
        memcpy_s((void *const)(v24 + 7), 2LL * v25, v26, 2LL * v25);
        goto LABEL_30;
      }
    }
    v24 = 0;
LABEL_30:
    v49 = (__int64)v24;
    v27 = *v59;
    v64 = 0;
    v65 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *))(*(_QWORD *)v27 + 64LL))(v27, v24);
    if ( v28 < 0 )
      winrt::throw_hresult((unsigned int)v28, &v64);
    if ( v24 )
    {
      v29 = _InterlockedDecrement(v24 + 6);
      if ( v29 )
      {
        if ( v29 < 0 )
          abort();
      }
      else
      {
        v30 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v30, 0, (LPVOID)v24);
      }
    }
    if ( v23 )
    {
      v31 = _InterlockedDecrement((volatile signed __int32 *)v23 + 6);
      if ( v31 )
      {
        if ( v31 < 0 )
          abort();
      }
      else
      {
        v32 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v32, 0, v23);
      }
    }
    if ( v52 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v52);
    *(_QWORD *)a1 = v51;
    goto LABEL_45;
  }
  v35 = (struct winrt::impl::shared_hstring_header *)*(unsigned int *)(a4 + 20);
  v36 = *(_QWORD *)(a4 + 24);
  if ( !v36 && *(_DWORD *)(a4 + 20) )
    gsl::details::terminate(a1);
  v37 = *(const wchar_t **)a4;
  v38 = -1;
  do
    ++v38;
  while ( v37[v38] );
  if ( v38 == 11 )
  {
    if ( !wmemcmp(v37, L"florence-d3", 0xBu) )
    {
      v53 = v35;
      v54 = v36;
      v49 = 0x4F1FABFA7C16FC1ELL;
      v50 = 0xD330987B9438799CuLL;
      anonymous_namespace_::create((unsigned int)&v52, *a3, (unsigned int)&v49, 1, (__int64)&v53);
      v39 = &v52;
      v40 = 9;
      v41 = v52;
      goto LABEL_60;
    }
LABEL_68:
    v44 = wil::verify_hresult(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const char *)v44,
      (int)"Unknown model ID.",
      v48);
  }
  if ( v38 != 8 || wmemcmp(v37, L"space-v6", 8u) )
    goto LABEL_68;
  v53 = v35;
  v54 = v36;
  v49 = 0x4C8F60E1CEE5420BLL;
  v50 = 0xD400F4D8806A53B9uLL;
  anonymous_namespace_::create((unsigned int)&v51, *a3, (unsigned int)&v49, 0, (__int64)&v53);
  v39 = &v51;
  v40 = 18;
  v41 = v51;
LABEL_60:
  *v39 = 0;
  *(_QWORD *)a1 = v41;
  v42 = v40 | 4;
  if ( (v42 & 2) != 0 )
  {
    v42 &= ~2u;
    if ( v51 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
  }
  if ( (v42 & 1) != 0 && v52 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v52);
  return a1;
}

```

## disassembly

```asm
0x1800542b4  push    rbp
0x1800542b6  push    rbx
0x1800542b7  push    rsi
0x1800542b8  push    rdi
0x1800542b9  push    r12
0x1800542bb  push    r13
0x1800542bd  push    r14
0x1800542bf  push    r15
0x1800542c1  lea     rbp, [rsp-1Fh]
0x1800542c6  sub     rsp, 0F8h
0x1800542cd  mov     rdi, r9
0x1800542d0  mov     r12, r8
0x1800542d3  mov     rsi, rdx
0x1800542d6  mov     r13, rcx
0x1800542d9  xor     r15d, r15d
0x1800542dc  mov     [rbp+57h+var_B0], r15d
0x1800542e0  mov     r9d, [r9+10h]
0x1800542e4  test    r9d, r9d
0x1800542e7  jz      loc_180054688
0x1800542ed  cmp     r9d, 1
0x1800542f1  jnz     loc_18005482E
0x1800542f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49288935@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49288935@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935> `wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl(void)'::`2'::impl
0x1800542fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49288935@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(void)
0x180054303  test    al, al
0x180054305  jz      loc_18005489E
0x18005430b  cmp     dword ptr [rdi+20h], 1Ch
0x18005430f  jb      loc_18005486F
0x180054315  mov     ebx, [rdi+20h]
0x180054318  add     rbx, 0FFFFFFFFFFFFFFE4h
0x18005431c  call    cs:__imp_GetProcessHeap
0x180054322  mov     rcx, rax; hHeap
0x180054325  mov     r8, rbx; dwBytes
0x180054328  xor     edx, edx; dwFlags
0x18005432a  call    cs:__imp_HeapAlloc
0x180054330  mov     r12, rax
0x180054333  mov     [rbp+57h+var_60], rax
0x180054337  mov     rax, [rdi+28h]
0x18005433b  mov     [rbp+57h+var_C8], rax
0x18005433f  mov     r9d, [rdi+20h]; wchar_t *
0x180054343  mov     [rbp+57h+var_D0], r9
0x180054347  mov     [rbp+57h+var_C0], rbx
0x18005434b  mov     [rbp+57h+var_B8], r12
0x18005434f  lea     r8, aInvokedEnclave; "Invoked enclave emb decryption with inp"...
0x180054356  mov     edx, 0BEh; wchar_t *
0x18005435b  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180054362  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180054367  lea     rcx, [rbp+57h+var_A0]
0x18005436b  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180054370  nop
0x180054371  mov     rbx, [rbp+57h+pv]
0x180054375  mov     [rsp+130h+var_F0], rbx
0x18005437a  lea     r14d, [r15+1]
0x18005437e  test    rbx, rbx
0x180054381  jz      short loc_18005438B
0x180054383  lock add [rbx+120h], r14d
0x18005438b  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180054392  call    cs:__imp_EnterCriticalSection
0x180054398  add     [rbx+0F0h], r14d
0x18005439f  mov     rbx, [rbp+57h+pv]
0x1800543a3  mov     [rsp+130h+var_E8], rbx
0x1800543a8  test    rbx, rbx
0x1800543ab  jz      short loc_1800543B5
0x1800543ad  lock add [rbx+120h], r14d
0x1800543b5  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800543bc  call    cs:__imp_EnterCriticalSection
0x1800543c2  add     [rbx+0F0h], r14d
0x1800543c9  mov     byte ptr [rbx+110h], 2
0x1800543d0  lea     rcx, [rsp+130h+var_E8]
0x1800543d5  call    ??1?$test_data_control@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(void)
0x1800543da  lea     rcx, [rsp+130h+var_F0]
0x1800543df  call    ??1?$test_data_control@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(void)
0x1800543e4  mov     rbx, [rbp+57h+pv]
0x1800543e8  mov     [rsp+130h+var_E8], rbx
0x1800543ed  test    rbx, rbx
0x1800543f0  jz      short loc_1800543FA
0x1800543f2  lock add [rbx+120h], r14d
0x1800543fa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180054401  call    cs:__imp_EnterCriticalSection
0x180054407  add     [rbx+0F0h], r14d
0x18005440e  mov     rax, [rbp+57h+var_D0]
0x180054412  mov     [rbx+118h], rax
0x180054419  lea     rcx, [rsp+130h+var_E8]
0x18005441e  call    ??1?$test_data_control@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(void)
0x180054423  mov     rax, [rsi]
0x180054426  lea     r8, [rbp+57h+var_D0]
0x18005442a  mov     edx, 2
0x18005442f  mov     rcx, rsi
0x180054432  mov     rax, [rax+10h]
0x180054436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005443b  mov     rsi, [rbp+57h+pv]
0x18005443f  lea     rbx, [rsi+0C8h]
0x180054446  mov     rcx, rbx; lpCriticalSection
0x180054449  call    cs:__imp_EnterCriticalSection
0x18005444f  or      dword ptr [rsi+48h], 300h
0x180054456  cmp     [rsi+0F8h], r15
0x18005445d  jz      short loc_18005446D
0x18005445f  mov     edx, 2
0x180054464  lea     rcx, [rsi+8]
0x180054468  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18005446d  test    rbx, rbx
0x180054470  jz      short loc_18005447B
0x180054472  mov     rcx, rbx; lpCriticalSection
0x180054475  call    cs:__imp_LeaveCriticalSection
0x18005447b  lea     r8, aCompletedEmbDe; "Completed emb decryption"
0x180054482  mov     edx, 0C6h; wchar_t *
0x180054487  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18005448e  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180054493  mov     rbx, [rbp+57h+var_C0]
0x180054497  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005449b  cmp     rbx, rsi
0x18005449e  jz      loc_180054869
0x1800544a4  mov     r15, [rbp+57h+var_B8]
0x1800544a8  test    r15, r15
0x1800544ab  jnz     short loc_1800544B6
0x1800544ad  test    rbx, rbx
0x1800544b0  jnz     loc_180054869
0x1800544b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54352721@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54352721@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54352721> `wil::Feature<__WilFeatureTraits_Feature_54352721>::GetImpl(void)'::`2'::impl
0x1800544bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54352721@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54352721>::__private_IsEnabled(void)
0x1800544c2  mov     [rsp+130h+var_100], rbx
0x1800544c7  mov     [rsp+130h+var_F8], r15
0x1800544cc  lea     rdx, [rsp+130h+var_100]
0x1800544d1  test    al, al
0x1800544d3  jz      loc_18005462B
0x1800544d9  lea     rcx, [rsp+130h+var_F0]
0x1800544de  call    _anonymous_namespace___create_from_blob
0x1800544e3  nop
0x1800544e4  lea     rdx, [rsp+130h+var_E8]
0x1800544e9  lea     rcx, [rsp+130h+var_F0]
0x1800544ee  call    ?PackageFamilyName@?$consume_Microsoft_Windows_Management_Deployment_IPackageSetItem@UIPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(void)
0x1800544f3  mov     [rbp+57h+var_A8], rax
0x1800544f7  mov     r15, [rdi+8]
0x1800544fb  mov     rbx, rsi
0x1800544fe  xor     eax, eax
0x180054500  inc     rbx
0x180054503  cmp     [r15+rbx*2], ax
0x180054508  jnz     short loc_180054500
0x18005450a  test    ebx, ebx
0x18005450c  jnz     short loc_180054514
0x18005450e  xor     ebx, ebx
0x180054510  mov     edi, ebx
0x180054512  jmp     short loc_180054534
0x180054514  mov     ecx, ebx; this
0x180054516  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18005451b  mov     rdi, rax
0x18005451e  mov     edx, ebx
0x180054520  add     rdx, rdx; DestinationSize
0x180054523  lea     rcx, [rax+1Ch]; Destination
0x180054527  mov     r9, rdx; SourceSize
0x18005452a  mov     r8, r15; Source
0x18005452d  call    memcpy_s
0x180054532  xor     ebx, ebx
0x180054534  mov     [rsp+130h+var_E0], rdi
0x180054539  test    rdi, rdi
0x18005453c  jnz     short loc_180054543
0x18005453e  mov     r14, rbx
0x180054541  jmp     short loc_180054580
0x180054543  test    [rdi], r14b
0x180054546  jnz     short loc_180054551
0x180054548  lock inc dword ptr [rdi+18h]
0x18005454c  mov     r14, rdi
0x18005454f  jmp     short loc_180054580
0x180054551  mov     r15d, [rdi+4]
0x180054555  test    r15d, r15d
0x180054558  jz      short loc_18005453E
0x18005455a  mov     rbx, [rdi+10h]
0x18005455e  mov     ecx, r15d; this
0x180054561  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180054566  mov     r14, rax
0x180054569  mov     edx, r15d
0x18005456c  add     rdx, rdx; DestinationSize
0x18005456f  lea     rcx, [rax+1Ch]; Destination
0x180054573  mov     r9, rdx; SourceSize
0x180054576  mov     r8, rbx; Source
0x180054579  call    memcpy_s
0x18005457e  xor     ebx, ebx
0x180054580  mov     [rsp+130h+var_100], r14
0x180054585  mov     rcx, [rbp+57h+var_A8]
0x180054589  mov     rcx, [rcx]
0x18005458c  mov     [rbp+57h+var_58], ebx
0x18005458f  xorps   xmm0, xmm0
0x180054592  movdqu  [rbp+57h+var_50], xmm0
0x180054597  mov     rax, [rcx]
0x18005459a  mov     rdx, r14
0x18005459d  mov     rax, [rax+40h]
0x1800545a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545a6  test    eax, eax
0x1800545a8  js      loc_18005485D
0x1800545ae  test    r14, r14
0x1800545b1  jz      short loc_1800545D4
0x1800545b3  mov     eax, esi
0x1800545b5  lock xadd [r14+18h], eax
0x1800545bb  sub     eax, 1
0x1800545be  jnz     short loc_180054615
0x1800545c0  nop
0x1800545c1  call    WINRT_IMPL_GetProcessHeap
0x1800545c6  mov     rcx, rax; hHeap
0x1800545c9  mov     r8, r14; lpMem
0x1800545cc  xor     edx, edx; dwFlags
0x1800545ce  call    WINRT_IMPL_HeapFree
0x1800545d3  nop
0x1800545d4  test    rdi, rdi
0x1800545d7  jz      short loc_1800545F9
0x1800545d9  mov     eax, esi
0x1800545db  lock xadd [rdi+18h], eax
0x1800545e0  sub     eax, 1
0x1800545e3  jnz     short loc_180054620
0x1800545e5  nop
0x1800545e6  call    WINRT_IMPL_GetProcessHeap
0x1800545eb  mov     rcx, rax; hHeap
0x1800545ee  mov     r8, rdi; lpMem
0x1800545f1  xor     edx, edx; dwFlags
0x1800545f3  call    WINRT_IMPL_HeapFree
0x1800545f8  nop
0x1800545f9  cmp     [rsp+130h+var_E8], rbx
0x1800545fe  jz      short loc_18005460A
0x180054600  lea     rcx, [rsp+130h+var_E8]
0x180054605  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18005460a  mov     rax, [rsp+130h+var_F0]
0x18005460f  mov     [r13+0], rax
0x180054613  jmp     short loc_180054634
0x180054615  test    eax, eax
0x180054617  jns     short loc_1800545D4
0x180054619  call    cs:__imp_abort
0x180054620  test    eax, eax
0x180054622  jns     short loc_1800545F9
0x180054624  call    cs:__imp_abort
0x18005462b  mov     rcx, r13
0x18005462e  call    _anonymous_namespace___create_from_blob
0x180054633  nop
0x180054634  mov     rbx, [rbp+57h+pv]
0x180054638  test    rbx, rbx
0x18005463b  jz      short loc_18005465C
0x18005463d  mov     eax, esi
0x18005463f  lock xadd [rbx+120h], eax
0x180054647  add     eax, esi
0x180054649  jnz     short loc_18005465C
0x18005464b  mov     rcx, rbx
0x18005464e  call    ??1?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(void)
0x180054653  mov     rcx, rbx; pv
0x180054656  call    cs:__imp_CoTaskMemFree
0x18005465c  lea     rcx, [rbp+57h+var_98]; this
0x180054660  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180054665  nop
0x180054666  test    r12, r12
0x180054669  jz      loc_1800547E2
0x18005466f  call    cs:__imp_GetProcessHeap
0x180054675  mov     rcx, rax; hHeap
0x180054678  mov     r8, r12; lpMem
0x18005467b  xor     edx, edx; dwFlags
0x18005467d  call    cs:__imp_HeapFree
0x180054683  jmp     loc_1800547E2
0x180054688  mov     ebx, [rdi+14h]
0x18005468b  mov     r15, [rdi+18h]
0x18005468f  test    r15, r15
0x180054692  jnz     short loc_18005469D
0x180054694  test    rbx, rbx
0x180054697  jnz     loc_1800547F9
0x18005469d  mov     rcx, [rdi]; S1
0x1800546a0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800546a4  xor     edi, edi
0x1800546a6  inc     rsi
0x1800546a9  cmp     [rcx+rsi*2], di
0x1800546ad  jnz     short loc_1800546A6
0x1800546af  mov     r14d, 1
0x1800546b5  lea     r8d, [r14+0Ah]; N
0x1800546b9  cmp     rsi, r8
0x1800546bc  jnz     short loc_18005472C
0x1800546be  lea     rdx, aFlorenceD3; "florence-d3"
0x1800546c5  call    wmemcmp
0x1800546ca  test    eax, eax
0x1800546cc  jnz     loc_1800547FF
0x1800546d2  mov     [rsp+130h+var_E0], rbx
0x1800546d7  mov     [rsp+130h+var_D8], r15
0x1800546dc  mov     dword ptr [rsp+130h+var_100], 7C16FC1Eh
0x1800546e4  mov     dword ptr [rsp+130h+var_100+4], 4F1FABFAh
0x1800546ec  mov     dword ptr [rsp+130h+var_F8], 9438799Ch
0x1800546f4  mov     dword ptr [rsp+130h+var_F8+4], 0D330987Bh
0x1800546fc  lea     rax, [rsp+130h+var_E0]
0x180054701  mov     qword ptr [rsp+130h+var_110], rax
0x180054706  mov     r9d, r14d
0x180054709  lea     r8, [rsp+130h+var_100]
0x18005470e  mov     rdx, [r12]
0x180054712  lea     rcx, [rsp+130h+var_E8]
0x180054717  call    _anonymous_namespace___create
0x18005471c  lea     rcx, [rsp+130h+var_E8]
0x180054721  lea     ebx, [r14+8]
0x180054725  mov     rax, [rsp+130h+var_E8]
0x18005472a  jmp     short loc_1800547A8
0x18005472c  mov     r8d, 8; N
0x180054732  cmp     rsi, r8
0x180054735  jnz     loc_1800547FF
0x18005473b  lea     rdx, aSpaceV6; "space-v6"
0x180054742  call    wmemcmp
0x180054747  test    eax, eax
0x180054749  jnz     loc_1800547FF
0x18005474f  mov     [rsp+130h+var_E0], rbx
0x180054754  mov     [rsp+130h+var_D8], r15
0x180054759  mov     dword ptr [rsp+130h+var_100], 0CEE5420Bh
0x180054761  mov     dword ptr [rsp+130h+var_100+4], 4C8F60E1h
0x180054769  mov     dword ptr [rsp+130h+var_F8], 806A53B9h
  ... truncated ...
```
