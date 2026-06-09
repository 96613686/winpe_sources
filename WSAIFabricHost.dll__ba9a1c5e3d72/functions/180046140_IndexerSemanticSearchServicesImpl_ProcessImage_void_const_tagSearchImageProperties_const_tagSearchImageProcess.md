# IndexerSemanticSearchServicesImpl::ProcessImage(void * const,tagSearchImageProperties const *,tagSearchImageProcessingType,tagSearchImageProcessingOptions const *,tagSemanticVector *,tagSAFEARRAY * *,tagSAFEARRAY * *)

- ea: `0x180046140`
- end: `0x1800473fe`
- name: `?ProcessImage@IndexerSemanticSearchServicesImpl@@UEAAJQEAXPEBUtagSearchImageProperties@@W4tagSearchImageProcessingType@@PEBUtagSearchImageProcessingOptions@@PEAUtagSemanticVector@@PEAPEAUtagSAFEARRAY@@5@Z`
- size: `4798`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64, const wchar_t *, _DWORD *, _OWORD *, SAFEARRAY **, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `44`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004ca0`
- `0x1800058cb`
- `0x18000591f`
- `0x180007f72`
- `0x180007fae`
- `0x18000b064`
- `0x18000c478`
- `0x180012444`
- `0x180013d94`
- `0x180014428`
- `0x180015f90`
- `0x1800187b0`
- `0x180018fa0`
- `0x180019c3c`
- `0x18001a464`
- `0x18001fd14`
- `0x18002be84`
- `0x18002e074`
- `0x18002f924`
- `0x180030900`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180032ac4`
- `0x180032c94`
- `0x180032ca0`
- `0x180032e80`
- `0x180034f90`
- `0x1800353b8`
- `0x180036954`
- `0x18003e364`
- `0x18003e914`
- `0x18003eb7c`
- `0x180045790`
- `0x180046140`
- `0x18004858c`
- `0x18004d1d8`
- `0x18004d4ec`
- `0x18004d708`
- `0x18004dea8`
- `0x18004ff60`
- `0x18005079c`
- `0x180051eb0`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180047178`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180047178`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046754`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046754`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004693e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004693e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800466ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800466ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046727`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046727`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ab3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ab3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800467db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004687e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046972`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800467db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004687e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046972`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046a83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046394`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800463af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800468f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800470d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004720e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046394`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800463af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800468f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800470d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004720e`
- `OLEAUT32!__imp_SysFreeString` at `0x180046d82`
- `OLEAUT32!__imp_SysFreeString` at `0x180046ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x18004703e`
- `OLEAUT32!__imp_SysFreeString` at `0x180047146`
- `OLEAUT32!__imp_SysFreeString` at `0x180046d82`
- `OLEAUT32!__imp_SysFreeString` at `0x180046ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x18004703e`
- `OLEAUT32!__imp_SysFreeString` at `0x180047146`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180046d44`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180046d44`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180047000`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180047000`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180046ea2`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180046ea2`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046ac3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180046ac3`

## string_xrefs

- `0x180046205`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004628e`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800462b0`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180046484`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180047285`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180046310`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800463d9`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180046d64`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180046ec2`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180047020`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180047379`: `TextRecognizer::CreateAsync timed out`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall IndexerSemanticSearchServicesImpl::ProcessImage(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        const wchar_t *a4,
        _DWORD *a5,
        _OWORD *a6,
        SAFEARRAY **a7,
        struct tagSAFEARRAY **a8)
{
  unsigned int v8; // esi
  __int64 v9; // r12
  const wchar_t *v10; // r15
  __int64 v11; // r13
  _OWORD *v12; // rbx
  int v13; // r14d
  unsigned __int8 v14; // cl
  __int64 result; // rax
  const wchar_t *v16; // r9
  SAFEARRAY **v17; // rcx
  const wchar_t *v18; // r9
  struct tagSAFEARRAY **v19; // rsi
  __int128 *v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm2
  int v23; // eax
  unsigned int v24; // ebx
  _OWORD *v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  SAFEARRAY *v28; // rbx
  int v29; // r14d
  int v30; // r14d
  int v31; // r14d
  int v32; // eax
  _DWORD *v33; // rsi
  int v34; // eax
  int v35; // eax
  __int64 v36; // r13
  __int64 *TextRecognizer; // rax
  SAFEARRAY *v38; // r12
  RTL_SRWLOCK *v39; // rsi
  SAFEARRAY *v40; // r12
  __int64 v41; // rcx
  RTL_SRWLOCK *v42; // rsi
  __int64 v43; // rax
  struct _RTL_CRITICAL_SECTION *v44; // rsi
  SAFEARRAY *v45; // rsi
  __int64 v46; // rax
  struct _RTL_CRITICAL_SECTION *v47; // rsi
  void *v48; // rsi
  struct _RTL_CRITICAL_SECTION *v49; // rsi
  SAFEARRAY *v50; // r12
  SAFEARRAY **v51; // rax
  int v52; // eax
  struct _RTL_CRITICAL_SECTION *v53; // rsi
  int v54; // eax
  _QWORD *v55; // rsi
  int v56; // r14d
  SAFEARRAY *p_cLocks; // rcx
  __int64 *v58; // rax
  __int64 v59; // rcx
  int v60; // eax
  volatile signed __int32 *v61; // r12
  const wchar_t *v62; // rdx
  int v63; // eax
  HANDLE ProcessHeap; // rax
  LPVOID *v65; // rdx
  _QWORD *v66; // r12
  _QWORD *j; // r14
  void *v68; // rsi
  HRESULT UBound; // eax
  unsigned int v70; // r12d
  _QWORD *v71; // r12
  _QWORD *k; // r14
  void *v73; // rsi
  HRESULT v74; // eax
  unsigned int v75; // r12d
  _QWORD *v76; // r12
  _QWORD *m; // r14
  void *v78; // rsi
  HRESULT v79; // eax
  unsigned int v80; // r12d
  _QWORD *v81; // r12
  _QWORD *n; // r14
  void *v83; // rsi
  _QWORD *v84; // r12
  _QWORD *ii; // r14
  void *v86; // rsi
  __int64 v87; // rax
  __int64 v88; // rbx
  unsigned int *v89; // rax
  int v90; // ecx
  int v91; // [rsp+20h] [rbp-268h]
  char v92; // [rsp+30h] [rbp-258h]
  LPVOID lpMem; // [rsp+38h] [rbp-250h] BYREF
  __int64 v94; // [rsp+40h] [rbp-248h] BYREF
  __int64 v95; // [rsp+48h] [rbp-240h] BYREF
  int v96; // [rsp+50h] [rbp-238h]
  __int64 v97; // [rsp+58h] [rbp-230h] BYREF
  SAFEARRAY *v98; // [rsp+60h] [rbp-228h] BYREF
  SAFEARRAY *psa; // [rsp+68h] [rbp-220h] BYREF
  __int64 v100; // [rsp+70h] [rbp-218h] BYREF
  SAFEARRAY *v101; // [rsp+78h] [rbp-210h] BYREF
  SAFEARRAY *v102; // [rsp+80h] [rbp-208h] BYREF
  SAFEARRAY *v103; // [rsp+88h] [rbp-200h] BYREF
  LONG plUbound; // [rsp+90h] [rbp-1F8h] BYREF
  int v105; // [rsp+98h] [rbp-1F0h] BYREF
  __int128 v106; // [rsp+A0h] [rbp-1E8h]
  __int64 v107; // [rsp+B0h] [rbp-1D8h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp-1D0h] BYREF
  LPVOID v109; // [rsp+C0h] [rbp-1C8h]
  int v110; // [rsp+C8h] [rbp-1C0h]
  SAFEARRAY **v111; // [rsp+D0h] [rbp-1B8h]
  __int64 *i; // [rsp+D8h] [rbp-1B0h]
  __int64 v113; // [rsp+E0h] [rbp-1A8h] BYREF
  _DWORD *v114; // [rsp+E8h] [rbp-1A0h]
  unsigned int v115; // [rsp+F0h] [rbp-198h]
  __int64 v116; // [rsp+F8h] [rbp-190h]
  LONG rgIndices; // [rsp+100h] [rbp-188h] BYREF
  __int64 v118; // [rsp+108h] [rbp-180h] BYREF
  __int64 v119; // [rsp+110h] [rbp-178h] BYREF
  __int64 v120; // [rsp+118h] [rbp-170h] BYREF
  __int64 v121; // [rsp+120h] [rbp-168h] BYREF
  SAFEARRAYBOUND psaboundNew; // [rsp+128h] [rbp-160h] BYREF
  _DWORD *v123; // [rsp+138h] [rbp-150h]
  struct tagSAFEARRAY **v124; // [rsp+140h] [rbp-148h]
  __int64 v125; // [rsp+148h] [rbp-140h]
  char v126[8]; // [rsp+150h] [rbp-138h] BYREF
  char v127[8]; // [rsp+158h] [rbp-130h] BYREF
  const wchar_t *v128; // [rsp+160h] [rbp-128h]
  __int64 v129; // [rsp+168h] [rbp-120h]
  _OWORD *v130; // [rsp+170h] [rbp-118h]
  __int64 v131; // [rsp+178h] [rbp-110h] BYREF
  char v132[8]; // [rsp+180h] [rbp-108h] BYREF
  _BYTE v133[48]; // [rsp+188h] [rbp-100h] BYREF
  LPVOID v134; // [rsp+1B8h] [rbp-D0h]
  char v135[8]; // [rsp+1D0h] [rbp-B8h] BYREF
  char v136[48]; // [rsp+1D8h] [rbp-B0h] BYREF
  LPVOID v137; // [rsp+208h] [rbp-80h]
  _BYTE pExceptionObject[24]; // [rsp+210h] [rbp-78h] BYREF
  LPVOID pv[2]; // [rsp+228h] [rbp-60h] BYREF
  __int128 v140; // [rsp+238h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v8 = (unsigned int)a4;
  v9 = a3;
  v10 = a2;
  v11 = a1;
  v123 = a5;
  v116 = a1;
  v128 = a2;
  v129 = a3;
  v115 = (unsigned int)a4;
  v114 = a5;
  v12 = a6;
  v130 = a6;
  v111 = a7;
  v124 = a8;
  v13 = 0;
  v96 = 0;
  v14 = 0;
  v92 = 0;
  result = 0;
  while ( 2 )
  {
    psa = (SAFEARRAY *)v11;
    if ( v14 >= 3u )
      return result;
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x4C9,
      (unsigned int)L"ProcessImage : Started",
      a4);
    if ( v12 )
    {
      *v12 = 0;
      v12[1] = 0;
    }
    if ( !v10 || !v9 || !v114 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0x4D2,
        (unsigned int)L"ProcessImage : Invalid arguments imageHandle: %p, imageProperties: %p, processingOptions: %p",
        v10,
        v9,
        v114);
      return 2147500035LL;
    }
    LODWORD(v97) = v8 & 1;
    if ( (v8 & 1) != 0 && !v12 )
    {
      v17 = v111;
LABEL_14:
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0x4D9,
        (unsigned int)L"ProcessImage : Invalid arguments processingType: %d, vector: %p, recognizedText: %p",
        (const wchar_t *)v8,
        v12,
        v17);
      return 2147500035LL;
    }
    LODWORD(lpMem) = v8 & 2;
    if ( (v8 & 2) != 0 )
    {
      v17 = v111;
      if ( !v111 )
        goto LABEL_14;
    }
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x4DD,
      (unsigned int)L"Process Image: Model are available",
      v16);
    try
    {
      anonymous_namespace_::CreateSoftwareBitmapFromSharedMem(&v94, v10, v9);
      if ( (_DWORD)v97 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl)
          && (v8 & 3) != 0 )
        {
          v19 = v124;
          if ( !v124 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4E8,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              (const char *)0x80004003LL,
              v91);
            if ( v94 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v94);
            return 2147500035LL;
          }
          IndexerSemanticSearchServicesImpl::ImageEmbedding(v11, &v107, &v94);
          v20 = (__int128 *)anonymous_namespace_::EmbeddingToSemanticVector(pv, *(_QWORD *)(v11 + 160), &v107);
          v21 = *v20;
          v22 = v20[1];
          *v20 = 0;
          v20[1] = 0;
          *v12 = v21;
          v12[1] = v22;
          if ( pv[1] )
          {
            CoTaskMemFree(pv[1]);
            pv[1] = 0;
          }
          if ( *((_QWORD *)&v140 + 1) )
            CoTaskMemFree(*((LPVOID *)&v140 + 1));
          v23 = IndexerSemanticSearchServicesImpl::PopulateCategoriesFromImageEmbedding(
                  (IndexerSemanticSearchServicesImpl *)v11,
                  (const struct winrt::Microsoft::Windows::SemanticSearch::Embedding *)&v107,
                  v19);
          v24 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4ED,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              (const char *)(unsigned int)v23,
              v91);
            if ( v107 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v107);
            if ( v94 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v94);
            return v24;
          }
          if ( v107 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v107);
        }
        else
        {
          v25 = (_OWORD *)IndexerSemanticSearchServicesImpl::ImageEmbeddingGenerationCommon(v11, pv, &v94);
          *v12 = *v25;
          v12[1] = v25[1];
        }
      }
      if ( (_DWORD)lpMem )
      {
        SearchIndexerTrace::Verbose(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const wchar_t *)0x504,
          (unsigned int)L"ProcessImage : RecognizeText is enabled",
          v18);
        v98 = (SAFEARRAY *)&v94;
        i = &qword_1800AF8B8;
        _InterlockedIncrement64(&qword_1800AF8B8);
        if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Imaging::ImageBuffer,winrt::Microsoft::Windows::Imaging::IImageBufferStatics> )
        {
          v101 = 0;
          v105 = 0;
          v106 = 0;
          v26 = (*(__int64 (__fastcall **)(__int64, __int64, SAFEARRAY **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Imaging::ImageBuffer,winrt::Microsoft::Windows::Imaging::IImageBufferStatics>
                                                                          + 56LL))(
                  winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Imaging::ImageBuffer,winrt::Microsoft::Windows::Imaging::IImageBufferStatics>,
                  v94,
                  &v101);
          if ( v26 < 0 )
            winrt::throw_hresult((unsigned int)v26, &v105);
          v28 = v101;
          v103 = v101;
          v29 = v13 | 0xE;
          _InterlockedAdd64(&qword_1800AF8B8, 0xFFFFFFFFFFFFFFFFuLL);
        }
        else
        {
          _InterlockedAdd64(&qword_1800AF8B8, 0xFFFFFFFFFFFFFFFFuLL);
          winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Imaging::ImageBuffer,winrt::Microsoft::Windows::Imaging::IImageBufferStatics>::call<_lambda_070952ad0fe39ba07f3112bb474bc2f7_ &>(
            0,
            &v103,
            &v98);
          v29 = v13 | 2;
          v28 = v103;
        }
        v30 = v29 | 1;
        v96 = v30;
        i = &qword_1800AF878;
        _InterlockedIncrement64(&qword_1800AF878);
        if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory> )
        {
          _lambda_0beaa2be1232e06794b986e5bb43a2ed_::operator()(
            v27,
            &v95,
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory>);
          v31 = v30 | 0x10;
          v96 = v31;
          _InterlockedAdd64(&qword_1800AF878, 0xFFFFFFFFFFFFFFFFuLL);
        }
        else
        {
          _InterlockedAdd64(&qword_1800AF878, 0xFFFFFFFFFFFFFFFFuLL);
          v98 = (SAFEARRAY *)_lambda_0beaa2be1232e06794b986e5bb43a2ed_::_lambda_invoker_cdecl_;
          winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Vision::TextRecognizerOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
            v27,
            &v95,
            &v98);
          v31 = v30 | 0x10;
          v96 = v31;
        }
        v105 = 0;
        v106 = 0;
        v32 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v95 + 56LL))(v95, 0);
        if ( v32 < 0 )
          winrt::throw_hresult((unsigned int)v32, &v105);
        LODWORD(v125) = *v123;
        v33 = v114;
        HIDWORD(v125) = v114[1];
        v105 = 0;
        v106 = 0;
        v34 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v95 + 72LL))(v95, v125);
        if ( v34 < 0 )
          winrt::throw_hresult((unsigned int)v34, &v105);
        v105 = 0;
        v106 = 0;
        v35 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v95 + 88LL))(v95, (unsigned int)v33[2]);
        if ( v35 < 0 )
          winrt::throw_hresult((unsigned int)v35, &v105);
        v36 = 0;
        v100 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56631575>::GetImpl'::`2'::impl) )
        {
          TextRecognizer = (__int64 *)IndexerSemanticSearchServicesImpl::GetTextRecognizer(psa, &v118);
          if ( &v100 != TextRecognizer )
          {
            v36 = *TextRecognizer;
            *TextRecognizer = 0;
            v100 = v36;
          }
          if ( v118 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v118);
        }
        else
        {
          LODWORD(lpMem) = 0;
          v38 = psa;
          v98 = psa + 1;
          v39 = *(RTL_SRWLOCK **)std::unordered_map<enum AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](
                                   &psa[1],
                                   &lpMem);
          AcquireSRWLockShared(v39);
          v40 = v38 + 3;
          v41 = *(_QWORD *)&v40->cDims;
          if ( *(_QWORD *)&v40->cDims && &v100 != (__int64 *)v40 )
          {
            v36 = *(_QWORD *)&v40->cDims;
            v100 = *(_QWORD *)&v40->cDims;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
          }
          if ( v39 )
            ReleaseSRWLockShared(v39);
          if ( !v36 )
          {
            LODWORD(lpMem) = 0;
            v42 = *(RTL_SRWLOCK **)std::unordered_map<enum AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](
                                     v98,
                                     &lpMem);
            v101 = (SAFEARRAY *)v42;
            AcquireSRWLockExclusive(v42);
            i = (__int64 *)v42;
            if ( !*(_QWORD *)&v40->cDims )
            {
              v43 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)psa[4].rgsabound + 32LL))(
                      *(_QWORD *)psa[4].rgsabound,
                      &v119);
              winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v43);
              if ( v119 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v119);
              tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v135);
              v44 = (struct _RTL_CRITICAL_SECTION *)v137;
              v98 = (SAFEARRAY *)v137;
              if ( v137 )
                _InterlockedIncrement((volatile signed __int32 *)v137 + 72);
              EnterCriticalSection(v44 + 5);
              ++LODWORD(v44[6].DebugInfo);
              LODWORD(v44[6].SpinCount) = 34;
              tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v98);
              winrt::Microsoft::Windows::Vision::TextRecognizer::CreateAsync();
              if ( !(unsigned int)winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Vision::TextRecognizer>>(
                                    &v113,
                                    120000) )
              {
                v87 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
                        v135,
                        v127);
                *(_BYTE *)(std::unique_ptr<wil::srwlock>::operator->(v87) + 276) = 1;
                tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(v127);
                v88 = winrt::impl::slim_source_location::current(&v105);
                winrt::param::hstring::hstring((winrt::param::hstring *)pv, L"TextRecognizer::CreateAsync timed out");
                v89 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v126, -2147023436);
                winrt::hresult_error::hresult_error(pExceptionObject, *v89, pv, v88);
                throw (winrt::hresult_error *)pExceptionObject;
              }
              v45 = (SAFEARRAY *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Vision::TextRecognizer>,winrt::Microsoft::Windows::Vision::TextRecognizer>::get(
                                   &v113,
                                   &v120);
              if ( v40 != v45 )
              {
                if ( *(_QWORD *)&v40->cDims )
                  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v40);
                v46 = *(_QWORD *)&v45->cDims;
                *(_QWORD *)&v45->cDims = 0;
                *(_QWORD *)&v40->cDims = v46;
              }
              if ( v120 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v120);
              v47 = (struct _RTL_CRITICAL_SECTION *)v137;
              EnterCriticalSection((LPCRITICAL_SECTION)v137 + 5);
              LODWORD(v47[1].SpinCount) |= 0x300u;
              if ( *(_QWORD *)&v47[6].LockCount )
                tip2::details::shared_data<0,0,0>::complete_helper(&v47->LockCount, 2);
              if ( v47 != (struct _RTL_CRITICAL_SECTION *)-200LL )
                LeaveCriticalSection(v47 + 5);
              if ( v113 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v113);
              v48 = v137;
              if ( v137 && _InterlockedExchangeAdd((volatile signed __int32 *)v137 + 72, 0xFFFFFFFF) == 1 )
              {
                tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v48);
                CoTaskMemFree(v48);
              }
              wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v136);
              v42 = (RTL_SRWLOCK *)v101;
            }
            if ( &v100 != (__int64 *)v40 )
            {
              v36 = *(_QWORD *)&v40->cDims;
              v100 = v36;
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
            }
            if ( v42 )
              ReleaseSRWLockExclusive(v42);
          }
        }
        tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v132);
        v49 = (struct _RTL_CRITICAL_SECTION *)v134;
        v98 = (SAFEARRAY *)v134;
        if ( v134 )
          _InterlockedIncrement((volatile signed __int32 *)v134 + 72);
        EnterCriticalSection(v49 + 5);
        ++LODWORD(v49[6].DebugInfo);
        LODWORD(v49[6].SpinCount) = 11;
        tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v98);
        v50 = 0;
        v101 = 0;
        v102 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55481656>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55481656>::GetImpl'::`2'::impl) )
        {
          LODWORD(lpMem) = 1;
          v51 = (SAFEARRAY **)winrt::impl::consume_Microsoft_Windows_Vision_ITextRecognizer2<winrt::Microsoft::Windows::Vision::TextRecognizer>::RecognizeTextFromImage(
                                (unsigned int)&v100,
                                (unsigned int)&v121,
                                (unsigned int)&v103,
                                (unsigned int)&v95,
                                (__int64)&lpMem);
          if ( &v102 != v51 )
          {
            v101 = *v51;
            v50 = v101;
            *v51 = 0;
            v102 = v50;
          }
          if ( v121 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v121);
        }
        else
        {
          psa = 0;
          v105 = 0;
          v106 = 0;
          v52 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *, __int64, SAFEARRAY **))(*(_QWORD *)v36 + 56LL))(
                  v36,
                  v28,
                  v95,
                  &psa);
          if ( v52 < 0 )
            winrt::throw_hresult((unsigned int)v52, &v105);
          v31 |= 0x20u;
          v96 = v31;
          v50 = psa;
          v101 = psa;
          v102 = psa;
        }
        v53 = (struct _RTL_CRITICAL_SECTION *)v134;
        EnterCriticalSection((LPCRITICAL_SECTION)v134 + 5);
        LODWORD(v53[1].SpinCount) |= 0x300u;
        if ( *(_QWORD *)&v53[6].LockCount )
          tip2::details::shared_data<0,0,0>::complete_helper(&v53->LockCount, 2);
        if ( v53 != (struct _RTL_CRITICAL_SECTION *)-200LL )
          LeaveCriticalSection(v53 + 5);
        psa = SafeArrayCreateVector(8u, 0, 0);
        LODWORD(v97) = 0;
        lpMem = 0;
        v105 = 0;
        v106 = 0;
        v54 = (*(__int64 (__fastcall **)(SAFEARRAY *, __int64 *, LPVOID *))(*(_QWORD *)&v50->cDims + 48LL))(
                v50,
                &v97,
                &lpMem);
        if ( v54 < 0 )
          winrt::throw_hresult((unsigned int)v54, &v105);
        v55 = lpMem;
        v109 = lpMem;
        v97 = (unsigned int)v97;
        v110 = v97;
        v56 = v31 | 0x40;
        v96 = v56;
        p_cLocks = (SAFEARRAY *)lpMem;
        v58 = (__int64 *)((char *)lpMem + 8 * (unsigned int)v97);
        for ( i = v58; ; v58 = i )
        {
          v98 = p_cLocks;
          if ( p_cLocks == (SAFEARRAY *)v58 )
            break;
          lpMem = 0;
          v59 = *(_QWORD *)&p_cLocks->cDims;
          v105 = 0;
          v106 = 0;
          v60 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v59 + 48LL))(v59, &lpMem);
          if ( v60 < 0 )
            winrt::throw_hresult((unsigned int)v60, &v105);
          v61 = (volatile signed __int32 *)lpMem;
          v56 |= 0x80u;
          v96 = v56;
          *(_OWORD *)pv = 0;
          v140 = 0;
          if ( lpMem )
          {
            v62 = (const wchar_t *)*((_QWORD *)lpMem + 2);
          }
          else
          {
            v62 = &pszText;
            v61 = 0;
          }
          std::wstring::_Construct<1,wchar_t const *>(pv, v62);
          if ( v61 )
          {
            v63 = _InterlockedDecrement(v61 + 6);
            if ( v63 )
            {
              if ( v63 < 0 )
                abort();
            }
            else
            {
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v61);
            }
          }
          v65 = pv;
          if ( *((_QWORD *)&v140 + 1) > 7u )
            v65 = (LPVOID *)pv[0];
          wil::make_bstr(&bstrString, v65);
          if ( !bstrString )
          {
            std::wstring::~wstring(pv);
            if ( v55 )
            {
              v66 = &v55[(unsigned int)v97];
              for ( j = v55; j != v66; ++j )
              {
                if ( *j )
                  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(j);
              }
              CoTaskMemFree_0(v55);
              v109 = 0;
              v110 = 0;
            }
            if ( v101 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v102);
            v68 = v134;
            if ( v134 && _InterlockedExchangeAdd((volatile signed __int32 *)v134 + 72, 0xFFFFFFFF) == 1 )
            {
              tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v68);
              CoTaskMemFree(v68);
            }
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v133);
            if ( v36 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v100);
            if ( v95 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v95);
            if ( v28 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v103);
            if ( v94 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v94);
            return 2147942414LL;
          }
          plUbound = 0;
          UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
          v70 = UBound;
          LODWORD(lpMem) = UBound;
          if ( UBound < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x54C,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              (const char *)(unsigned int)UBound,
              v91);
            if ( bstrString )
              SysFreeString(bstrString);
            std::wstring::~wstring(pv);
            if ( v55 )
            {
              v71 = &v55[(unsigned int)v97];
              for ( k = v55; k != v71; ++k )
              {
                if ( *k )
                  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(k);
              }
              CoTaskMemFree_0(v55);
              v109 = 0;
              v110 = 0;
              v70 = (unsigned int)lpMem;
            }
            if ( v101 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v102);
            v73 = v134;
            if ( v134 && _InterlockedExchangeAdd((volatile signed __int32 *)v134 + 72, 0xFFFFFFFF) == 1 )
            {
              tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v73);
              CoTaskMemFree(v73);
            }
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v133);
            if ( v36 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v100);
            if ( v95 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v95);
            if ( v28 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v103);
            if ( v94 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v94);
            return v70;
          }
          psaboundNew.lLbound = 0;
          psaboundNew.cElements = plUbound + 2;
          v74 = SafeArrayRedim(psa, &psaboundNew);
          v75 = v74;
          LODWORD(lpMem) = v74;
          if ( v74 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x550,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              (const char *)(unsigned int)v74,
              v91);
            if ( bstrString )
              SysFreeString(bstrString);
            std::wstring::~wstring(pv);
            if ( v55 )
            {
              v76 = &v55[(unsigned int)v97];
              for ( m = v55; m != v76; ++m )
              {
                if ( *m )
                  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(m);
              }
              CoTaskMemFree_0(v55);
              v109 = 0;
              v110 = 0;
              v75 = (unsigned int)lpMem;
            }
            if ( v101 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v102);
            v78 = v134;
            if ( v134 && _InterlockedExchangeAdd((volatile signed __int32 *)v134 + 72, 0xFFFFFFFF) == 1 )
            {
              tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v78);
              CoTaskMemFree(v78);
            }
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v133);
            if ( v36 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v100);
            if ( v95 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v95);
            if ( v28 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v103);
            if ( v94 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v94);
            return v75;
          }
          rgIndices = plUbound + 1;
          v79 = SafeArrayPutElement(psa, &rgIndices, bstrString);
          v80 = v79;
          LODWORD(lpMem) = v79;
          if ( v79 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x552,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              (const char *)(unsigned int)v79,
              v91);
            if ( bstrString )
              SysFreeString(bstrString);
            std::wstring::~wstring(pv);
            if ( v55 )
            {
              v81 = &v55[(unsigned int)v97];
              for ( n = v55; n != v81; ++n )
              {
                if ( *n )
                  winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(n);
              }
              CoTaskMemFree_0(v55);
              v109 = 0;
              v110 = 0;
              v80 = (unsigned int)lpMem;
            }
            if ( v101 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v102);
            v83 = v134;
            if ( v134 && _InterlockedExchangeAdd((volatile signed __int32 *)v134 + 72, 0xFFFFFFFF) == 1 )
            {
              tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v83);
              CoTaskMemFree(v83);
            }
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v133);
            if ( v36 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v100);
            if ( v95 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v95);
            if ( v28 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v103);
            if ( v94 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v94);
            return v80;
          }
          if ( bstrString )
            SysFreeString(bstrString);
          std::wstring::~wstring(pv);
          p_cLocks = (SAFEARRAY *)&v98->cLocks;
        }
        if ( v55 )
        {
          v84 = &v55[(unsigned int)v97];
          for ( ii = v55; ii != v84; ++ii )
          {
            if ( *ii )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(ii);
          }
          CoTaskMemFree_0(v55);
          v109 = 0;
          v110 = 0;
        }
        *v111 = psa;
        if ( v101 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v102);
        v86 = v134;
        if ( v134 && _InterlockedExchangeAdd((volatile signed __int32 *)v134 + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v86);
          CoTaskMemFree(v86);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v133);
        if ( v36 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v100);
        if ( v95 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v95);
        if ( v28 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v103);
      }
      if ( v94 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v94);
      result = 0;
    }
    catch ( ... )
    {
      v90 = *(_DWORD *)winrt::to_hresult(&v131);
      LODWORD(v97) = v90;
      if ( v90 < 0
        && ((v90 & 0x1FFF0000) == 0x10000
         || (v90 & 0x1FFF0000) == 0x70000 && (unsigned int)(unsigned __int16)v90 - 1700 <= 0x12B) )
      {
        v14 = ++v92;
        result = (unsigned int)v97;
        v13 = v96;
        v11 = v116;
        v10 = v128;
        v9 = v129;
        v8 = v115;
        v12 = v130;
        continue;
      }
      return (unsigned int)v97;
    }
    return result;
  }
}

```

## disassembly

```asm
0x180046140  push    rbx
0x180046142  push    rsi
0x180046143  push    rdi
0x180046144  push    r12
0x180046146  push    r13
0x180046148  push    r14
0x18004614a  push    r15
0x18004614c  sub     rsp, 250h
0x180046153  mov     rax, cs:__security_cookie
0x18004615a  xor     rax, rsp
0x18004615d  mov     [rsp+288h+var_40], rax
0x180046165  mov     esi, r9d
0x180046168  mov     r12, r8
0x18004616b  mov     r15, rdx
0x18004616e  mov     r13, rcx
0x180046171  mov     r8, [rsp+288h+arg_20]
0x180046179  mov     [rsp+288h+var_150], r8
0x180046181  mov     [rsp+288h+var_190], rcx
0x180046189  mov     [rsp+288h+var_128], rdx
0x180046191  mov     [rsp+288h+var_120], r12
0x180046199  mov     [rsp+288h+var_198], r9d
0x1800461a1  mov     [rsp+288h+var_1A0], r8
0x1800461a9  mov     rbx, [rsp+288h+arg_28]
0x1800461b1  mov     [rsp+288h+var_118], rbx
0x1800461b9  mov     r8, [rsp+288h+arg_30]
0x1800461c1  mov     [rsp+288h+var_1B8], r8
0x1800461c9  mov     rdx, [rsp+288h+arg_38]
0x1800461d1  mov     [rsp+288h+var_148], rdx
0x1800461d9  xor     edi, edi
0x1800461db  mov     r14d, edi
0x1800461de  mov     [rsp+288h+var_238], edi
0x1800461e2  mov     cl, dil
0x1800461e5  mov     [rsp+288h+var_258], cl
0x1800461e9  mov     eax, edi
0x1800461eb  mov     [rsp+288h+psa], r13
0x1800461f0  cmp     cl, 3
0x1800461f3  jnb     loc_1800472D7
0x1800461f9  lea     r8, aProcessimageSt; "ProcessImage : Started"
0x180046200  mov     edx, 4C9h; wchar_t *
0x180046205  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18004620c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180046211  test    rbx, rbx
0x180046214  jz      short loc_180046220
0x180046216  xorps   xmm0, xmm0
0x180046219  movups  xmmword ptr [rbx], xmm0
0x18004621c  movups  xmmword ptr [rbx+10h], xmm0
0x180046220  mov     rax, [rsp+288h+var_1A0]
0x180046228  test    r15, r15
0x18004622b  jz      loc_18004726C
0x180046231  test    r12, r12
0x180046234  jz      loc_18004726C
0x18004623a  test    rax, rax
0x18004623d  jz      loc_18004726C
0x180046243  mov     eax, esi
0x180046245  and     eax, 1
0x180046248  mov     dword ptr [rsp+288h+var_230], eax
0x18004624c  jz      short loc_180046253
0x18004624e  test    rbx, rbx
0x180046251  jz      short loc_18004626D
0x180046253  mov     eax, esi
0x180046255  and     eax, 2
0x180046258  mov     dword ptr [rsp+288h+lpMem], eax
0x18004625c  jz      short loc_1800462A4
0x18004625e  mov     rcx, [rsp+288h+var_1B8]
0x180046266  test    rcx, rcx
0x180046269  jnz     short loc_1800462A4
0x18004626b  jmp     short loc_180046275
0x18004626d  mov     rcx, [rsp+288h+var_1B8]
0x180046275  mov     [rsp+288h+var_260], rcx
0x18004627a  mov     [rsp+288h+var_268], rbx
0x18004627f  mov     r9d, esi; wchar_t *
0x180046282  lea     r8, aProcessimageIn_0; "ProcessImage : Invalid arguments proces"...
0x180046289  mov     edx, 4D9h; wchar_t *
0x18004628e  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180046295  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18004629a  mov     eax, 80004003h
0x18004629f  jmp     loc_1800472D7
0x1800462a4  lea     r8, aProcessImageMo; "Process Image: Model are available"
0x1800462ab  mov     edx, 4DDh; wchar_t *
0x1800462b0  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800462b7  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800462bc  mov     r8, r12
0x1800462bf  mov     rdx, r15
0x1800462c2  lea     rcx, [rsp+288h+var_248]
0x1800462c7  call    _anonymous_namespace___CreateSoftwareBitmapFromSharedMem
0x1800462cc  nop
0x1800462cd  cmp     dword ptr [rsp+288h+var_230], edi
0x1800462d1  jz      loc_18004646E
0x1800462d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x1800462de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x1800462e3  test    al, al
0x1800462e5  jz      loc_18004644B
0x1800462eb  test    sil, 3
0x1800462ef  jz      loc_180046434
0x1800462f5  mov     rsi, [rsp+288h+var_148]
0x1800462fd  test    rsi, rsi
0x180046300  jnz     short loc_18004633D
0x180046302  mov     rcx, [rsp+288h]; this
0x18004630a  mov     r9d, 80004003h; char *
0x180046310  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180046317  mov     edx, 4E8h; void *
0x18004631c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046321  nop
0x180046322  cmp     [rsp+288h+var_248], rdi
0x180046327  jz      short loc_180046333
0x180046329  lea     rcx, [rsp+288h+var_248]
0x18004632e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180046333  mov     eax, 80004003h
0x180046338  jmp     loc_1800472D7
0x18004633d  lea     r8, [rsp+288h+var_248]
0x180046342  lea     rdx, [rsp+288h+var_1D8]
0x18004634a  mov     rcx, r13
0x18004634d  call    ?ImageEmbedding@IndexerSemanticSearchServicesImpl@@AEAA?AUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@AEBUSoftwareBitmap@Imaging@Graphics@46@@Z; IndexerSemanticSearchServicesImpl::ImageEmbedding(winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)
0x180046352  nop
0x180046353  lea     r8, [rsp+288h+var_1D8]
0x18004635b  mov     rdx, [r13+0A0h]
0x180046362  lea     rcx, [rsp+288h+pv]
0x18004636a  call    _anonymous_namespace___EmbeddingToSemanticVector
0x18004636f  movups  xmm1, xmmword ptr [rax]
0x180046372  movups  xmm2, xmmword ptr [rax+10h]
0x180046376  xorps   xmm0, xmm0
0x180046379  movups  xmmword ptr [rax], xmm0
0x18004637c  movups  xmmword ptr [rax+10h], xmm0
0x180046380  movups  xmmword ptr [rbx], xmm1
0x180046383  movups  xmmword ptr [rbx+10h], xmm2
0x180046387  mov     rcx, [rsp+288h+pv+8]; pv
0x18004638f  test    rcx, rcx
0x180046392  jz      short loc_1800463A2
0x180046394  call    cs:__imp_CoTaskMemFree
0x18004639a  mov     [rsp+288h+pv+8], rdi
0x1800463a2  mov     rcx, [rsp+288h+var_48]; pv
0x1800463aa  test    rcx, rcx
0x1800463ad  jz      short loc_1800463B5
0x1800463af  call    cs:__imp_CoTaskMemFree
0x1800463b5  mov     r8, rsi; struct tagSAFEARRAY **
0x1800463b8  lea     rdx, [rsp+288h+var_1D8]; struct winrt::Microsoft::Windows::SemanticSearch::Embedding *
0x1800463c0  mov     rcx, r13; this
0x1800463c3  call    ?PopulateCategoriesFromImageEmbedding@IndexerSemanticSearchServicesImpl@@AEAAJAEBUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@PEAPEAUtagSAFEARRAY@@@Z; IndexerSemanticSearchServicesImpl::PopulateCategoriesFromImageEmbedding(winrt::Microsoft::Windows::SemanticSearch::Embedding const &,tagSAFEARRAY * *)
0x1800463c8  mov     ebx, eax
0x1800463ca  test    eax, eax
0x1800463cc  jns     short loc_18004641B
0x1800463ce  mov     rcx, [rsp+288h]; this
0x1800463d6  mov     r9d, eax; char *
0x1800463d9  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800463e0  mov     edx, 4EDh; void *
0x1800463e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800463ea  nop
0x1800463eb  cmp     [rsp+288h+var_1D8], rdi
0x1800463f3  jz      short loc_180046403
0x1800463f5  lea     rcx, [rsp+288h+var_1D8]
0x1800463fd  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180046402  nop
0x180046403  cmp     [rsp+288h+var_248], rdi
0x180046408  jz      short loc_180046414
0x18004640a  lea     rcx, [rsp+288h+var_248]
0x18004640f  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180046414  mov     eax, ebx
0x180046416  jmp     loc_1800472D7
0x18004641b  cmp     [rsp+288h+var_1D8], rdi
0x180046423  jz      short loc_18004646E
0x180046425  lea     rcx, [rsp+288h+var_1D8]
0x18004642d  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180046432  jmp     short loc_18004646E
0x180046434  lea     r8, [rsp+288h+var_248]
0x180046439  lea     rdx, [rsp+288h+pv]
0x180046441  mov     rcx, r13
0x180046444  call    ?ImageEmbeddingGenerationCommon@IndexerSemanticSearchServicesImpl@@AEAA?AUtagSemanticVector@@AEBUSoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Z; IndexerSemanticSearchServicesImpl::ImageEmbeddingGenerationCommon(winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)
0x180046449  jmp     short loc_180046460
0x18004644b  lea     r8, [rsp+288h+var_248]
0x180046450  lea     rdx, [rsp+288h+pv]
0x180046458  mov     rcx, r13
0x18004645b  call    ?ImageEmbeddingGenerationCommon@IndexerSemanticSearchServicesImpl@@AEAA?AUtagSemanticVector@@AEBUSoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Z; IndexerSemanticSearchServicesImpl::ImageEmbeddingGenerationCommon(winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)
0x180046460  movups  xmm0, xmmword ptr [rax]
0x180046463  movups  xmmword ptr [rbx], xmm0
0x180046466  movups  xmm1, xmmword ptr [rax+10h]
0x18004646a  movups  xmmword ptr [rbx+10h], xmm1
0x18004646e  cmp     dword ptr [rsp+288h+lpMem], edi
0x180046472  jz      loc_180047257
0x180046478  lea     r8, aProcessimageRe; "ProcessImage : RecognizeText is enabled"
0x18004647f  mov     edx, 504h; wchar_t *
0x180046484  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18004648b  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180046490  lea     rax, [rsp+288h+var_248]
0x180046495  mov     [rsp+288h+var_228], rax
0x18004649a  lea     rax, qword_1800AF8B8
0x1800464a1  mov     [rsp+288h+var_1B0], rax
0x1800464a9  lock inc cs:qword_1800AF8B8
0x1800464b1  mov     rcx, cs:??$factory_cache_entry_v@UImageBuffer@Imaging@Windows@Microsoft@winrt@@UIImageBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UImageBuffer@Imaging@Windows@Microsoft@winrt@@UIImageBufferStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Imaging::ImageBuffer,winrt::Microsoft::Windows::Imaging::IImageBufferStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Imaging::ImageBuffer,winrt::Microsoft::Windows::Imaging::IImageBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Imaging::ImageBuffer,winrt::Microsoft::Windows::Imaging::IImageBufferStatics>
0x1800464b8  test    rcx, rcx
0x1800464bb  jz      short loc_180046512
0x1800464bd  mov     [rsp+288h+var_210], rdi
0x1800464c2  mov     [rsp+288h+var_1F0], edi
0x1800464c9  xorps   xmm0, xmm0
0x1800464cc  movdqu  [rsp+288h+var_1E8], xmm0
0x1800464d5  mov     rax, [rcx]
0x1800464d8  lea     r8, [rsp+288h+var_210]
0x1800464dd  mov     rdx, [rsp+288h+var_248]
0x1800464e2  mov     rax, [rax+38h]
0x1800464e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464eb  test    eax, eax
0x1800464ed  js      loc_1800472FA
0x1800464f3  mov     rbx, [rsp+288h+var_210]
0x1800464f8  mov     [rsp+288h+var_200], rbx
0x180046500  or      r14d, 0Eh
0x180046504  or      r15, 0FFFFFFFFFFFFFFFFh
0x180046508  lock add cs:qword_1800AF8B8, r15
0x180046510  jmp     short loc_18004653C
0x180046512  or      r15, 0FFFFFFFFFFFFFFFFh
0x180046516  lock add cs:qword_1800AF8B8, r15
0x18004651e  lea     r8, [rsp+288h+var_228]
0x180046523  lea     rdx, [rsp+288h+var_200]
0x18004652b  call    ??$call@AEAV_lambda_070952ad0fe39ba07f3112bb474bc2f7_@@@?$factory_cache_entry@UImageBuffer@Imaging@Windows@Microsoft@winrt@@UIImageBufferStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_070952ad0fe39ba07f3112bb474bc2f7_@@@Z
0x180046530  or      r14d, 2
0x180046534  mov     rbx, [rsp+288h+var_200]
0x18004653c  or      r14d, 1
0x180046540  mov     [rsp+288h+var_238], r14d
0x180046545  lea     rax, qword_1800AF878
0x18004654c  mov     [rsp+288h+var_1B0], rax
0x180046554  lock inc cs:qword_1800AF878
0x18004655c  cmp     cs:??$factory_cache_entry_v@UTextRecognizerOptions@Vision@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UTextRecognizerOptions@Vision@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A, rdi; factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory>
0x180046563  jz      short loc_180046589
0x180046565  lea     r8, ??$factory_cache_entry_v@UTextRecognizerOptions@Vision@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UTextRecognizerOptions@Vision@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizerOptions,winrt::Windows::Foundation::IActivationFactory>
0x18004656c  lea     rdx, [rsp+288h+var_240]
0x180046571  call    ??R_lambda_0beaa2be1232e06794b986e5bb43a2ed_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_0beaa2be1232e06794b986e5bb43a2ed_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180046576  or      r14d, 10h
0x18004657a  mov     [rsp+288h+var_238], r14d
0x18004657f  lock add cs:qword_1800AF878, r15
0x180046587  jmp     short loc_1800465B5
0x180046589  lock add cs:qword_1800AF878, r15
0x180046591  lea     rax, ?_lambda_invoker_cdecl_@_lambda_0beaa2be1232e06794b986e5bb43a2ed_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_0beaa2be1232e06794b986e5bb43a2ed_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180046598  mov     [rsp+288h+var_228], rax
0x18004659d  lea     r8, [rsp+288h+var_228]
0x1800465a2  lea     rdx, [rsp+288h+var_240]
0x1800465a7  call    ??$call@P6A?AUTextRecognizerOptions@Vision@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@35@@Z@?$factory_cache_entry@UTextRecognizerOptions@Vision@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@QEAA?A_P$$QEAP6A?AUTextRecognizerOptions@Vision@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@52@@Z@Z
0x1800465ac  or      r14d, 10h
0x1800465b0  mov     [rsp+288h+var_238], r14d
0x1800465b5  mov     rcx, [rsp+288h+var_240]
0x1800465ba  mov     [rsp+288h+var_1F0], edi
0x1800465c1  xorps   xmm0, xmm0
0x1800465c4  movdqu  [rsp+288h+var_1E8], xmm0
0x1800465cd  mov     rax, [rcx]
0x1800465d0  xor     edx, edx
0x1800465d2  mov     rax, [rax+38h]
0x1800465d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465db  test    eax, eax
0x1800465dd  js      loc_18004730A
0x1800465e3  mov     rax, [rsp+288h+var_150]
0x1800465eb  mov     eax, [rax]
0x1800465ed  mov     dword ptr [rsp+288h+var_140], eax
0x1800465f4  mov     rsi, [rsp+288h+var_1A0]
0x1800465fc  mov     eax, [rsi+4]
0x1800465ff  mov     dword ptr [rsp+288h+var_140+4], eax
0x180046606  mov     rcx, [rsp+288h+var_240]
0x18004660b  mov     [rsp+288h+var_1F0], edi
0x180046612  xorps   xmm0, xmm0
0x180046615  movdqu  [rsp+288h+var_1E8], xmm0
0x18004661e  mov     rax, [rcx]
0x180046621  mov     rdx, [rsp+288h+var_140]
0x180046629  mov     rax, [rax+48h]
0x18004662d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046632  test    eax, eax
0x180046634  js      loc_180047319
0x18004663a  mov     rcx, [rsp+288h+var_240]
0x18004663f  mov     [rsp+288h+var_1F0], edi
0x180046646  xorps   xmm0, xmm0
0x180046649  movdqu  [rsp+288h+var_1E8], xmm0
0x180046652  mov     rax, [rcx]
0x180046655  mov     edx, [rsi+8]
0x180046658  mov     rax, [rax+58h]
0x18004665c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046661  test    eax, eax
0x180046663  js      loc_180047328
0x180046669  mov     r13, rdi
0x18004666c  mov     [rsp+288h+var_218], rdi
0x180046671  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56631575@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56631575@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575> `wil::Feature<__WilFeatureTraits_Feature_56631575>::GetImpl(void)'::`2'::impl
0x180046678  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56631575@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575>::__private_IsEnabled(void)
0x18004667d  test    al, al
0x18004667f  jz      short loc_1800466C8
0x180046681  lea     rdx, [rsp+288h+var_180]
0x180046689  mov     rcx, [rsp+288h+psa]
0x18004668e  call    ?GetTextRecognizer@IndexerSemanticSearchServicesImpl@@AEAA?AUTextRecognizer@Vision@Windows@Microsoft@winrt@@XZ; IndexerSemanticSearchServicesImpl::GetTextRecognizer(void)
0x180046693  lea     rcx, [rsp+288h+var_218]
0x180046698  cmp     rcx, rax
0x18004669b  jz      short loc_1800466A8
0x18004669d  mov     r13, [rax]
0x1800466a0  mov     [rax], rdi
0x1800466a3  mov     [rsp+288h+var_218], r13
0x1800466a8  cmp     [rsp+288h+var_180], rdi
0x1800466b0  jz      loc_180046944
0x1800466b6  lea     rcx, [rsp+288h+var_180]
0x1800466be  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800466c3  jmp     loc_180046944
0x1800466c8  mov     dword ptr [rsp+288h+lpMem], edi
0x1800466cc  mov     r12, [rsp+288h+psa]
0x1800466d1  lea     rax, [r12+20h]
0x1800466d6  mov     [rsp+288h+var_228], rax
0x1800466db  lea     rdx, [rsp+288h+lpMem]
0x1800466e0  mov     rcx, rax
0x1800466e3  call    ??A?$unordered_map@W4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@U?$hash@W4AIFabric_Component@@@3@U?$equal_to@W4AIFabric_Component@@@3@V?$allocator@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@3@@std@@QEAAAEAV?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@1@$$QEAW4AIFabric_Component@@@Z; std::unordered_map<AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](AIFabric_Component &&)
0x1800466e8  mov     rsi, [rax]
  ... truncated ...
```
