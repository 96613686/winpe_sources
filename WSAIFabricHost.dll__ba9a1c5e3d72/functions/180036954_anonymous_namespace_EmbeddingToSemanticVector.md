# _anonymous_namespace_::EmbeddingToSemanticVector

- ea: `0x180036954`
- end: `0x180036d12`
- name: `_anonymous_namespace_::EmbeddingToSemanticVector`
- size: `958`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033c40`
- `0x180034a00`
- `0x180035640`
- `0x18003eb7c`
- `0x180046140`

## callees

- `0x180007ad0`
- `0x180007f42`
- `0x18000c478`
- `0x1800187b0`
- `0x18002a838`
- `0x18002dbe4`
- `0x18002fa8c`
- `0x1800319dc`
- `0x180031cbc`
- `0x1800321e4`
- `0x1800323e0`
- `0x1800326e8`
- `0x180036954`
- `0x18004cb7c`
- `0x18004ce18`
- `0x18004dea8`
- `0x180053984`
- `0x18007bbb4`
- `0x18007c2e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036c66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036c66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036b88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036bb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036bf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036c38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036b88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036bb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036bf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036cb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036cb6`

## string_xrefs

- `0x180036b56`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180036c78`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180036d00`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180036c6c`: `Completed emb encryption`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall anonymous_namespace_::EmbeddingToSemanticVector(__int64 a1, __int64 a2, __int64 a3)
{
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // rcx
  _DWORD *v7; // rdi
  volatile signed __int32 *v8; // rbx
  SIZE_T v9; // rcx
  void *v10; // rax
  const char *v11; // r9
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  _DWORD *v15; // r14
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  const wchar_t *v17; // r9
  void *v18; // rbx
  __int64 *v20; // [rsp+28h] [rbp-69h] BYREF
  volatile signed __int32 *v21; // [rsp+30h] [rbp-61h]
  __int64 v22; // [rsp+38h] [rbp-59h] BYREF
  __int64 (__fastcall *v23)(const struct winrt::Windows::Foundation::IActivationFactory *); // [rsp+40h] [rbp-51h] BYREF
  void *Src; // [rsp+48h] [rbp-49h] BYREF
  __int64 v25; // [rsp+50h] [rbp-41h]
  wchar_t *v26[2]; // [rsp+60h] [rbp-31h] BYREF
  SIZE_T v27; // [rsp+70h] [rbp-21h]
  LPVOID v28; // [rsp+78h] [rbp-19h]
  _BYTE v29[8]; // [rsp+88h] [rbp-9h] BYREF
  _BYTE v30[48]; // [rsp+90h] [rbp-1h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl'::`2'::impl) )
  {
    v20 = &qword_1800AF618;
    _InterlockedAdd64(&qword_1800AF618, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory> )
    {
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer>(
        &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>,
        &v22);
      _InterlockedDecrement64(&qword_1800AF618);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF618);
      v23 = _lambda_0bef2169a06e939039e50b364aa179a0_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        v6,
        (__int64)&v22,
        (void (__fastcall **)(__int64, __int64 *))&v23);
    }
    anonymous_namespace_::serialize(&Src, &v22, a3);
    *(_DWORD *)a1 = 1;
    v28 = 0;
    v26[1] = (wchar_t *)Src;
    v26[0] = (wchar_t *)(v25 - (_QWORD)Src);
    v27 = v25 - (_QWORD)Src + 28;
    v28 = CoTaskMemAlloc(v27);
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x116,
      (unsigned int)L"Invoking enclave emb encryption with input size: %lu",
      v26[0],
      v20);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>>((__int64)v29);
    v12 = (struct _RTL_CRITICAL_SECTION *)pv;
    v20 = (__int64 *)pv;
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v12 + 5);
    ++LODWORD(v12[6].DebugInfo);
    v13 = (struct _RTL_CRITICAL_SECTION *)pv;
    v23 = (__int64 (__fastcall *)(const struct winrt::Windows::Foundation::IActivationFactory *))pv;
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v13 + 5);
    ++LODWORD(v13[6].DebugInfo);
    LOBYTE(v13[6].SpinCount) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(&v23);
    tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(&v20);
    v14 = (struct _RTL_CRITICAL_SECTION *)pv;
    v20 = (__int64 *)pv;
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v14 + 5);
    ++LODWORD(v14[6].DebugInfo);
    v14[7].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v26[0];
    tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(&v20);
    (*(void (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)a2 + 16LL))(a2, 1, v26);
    v15 = pv;
    v16 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v15[18] |= 0x300u;
    if ( *((_QWORD *)v15 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v15 + 2, 2);
    if ( v16 )
      LeaveCriticalSection(v16);
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x11E,
      (unsigned int)L"Completed emb encryption",
      v17,
      v20);
    *(_DWORD *)(a1 + 16) = v27;
    *(_QWORD *)(a1 + 24) = v28;
    v18 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(v18);
      CoTaskMemFree(v18);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v30);
    std::vector<enum gsl::byte>::~vector<enum gsl::byte>(&Src);
    if ( v22 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v22);
  }
  else
  {
    *(_DWORD *)a1 = 0;
    v7 = operator new(0x20u);
    *(_OWORD *)v7 = 0;
    v7[2] = 1;
    v7[3] = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<semantic_index::implementation::embedding_factory>::`vftable';
    *((_OWORD *)v7 + 1) = 0;
    semantic_index::embedding_converter::embedding_converter((semantic_index::embedding_converter *)(v7 + 4));
    v20 = (__int64 *)(v7 + 4);
    v21 = v7;
    semantic_index::embedding_data_accessor::get_data(&v20, &Src, a3);
    v8 = v21;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v9 = (v25 - (__int64)Src) >> 2;
    *(_DWORD *)(a1 + 4) = v9;
    v10 = CoTaskMemAlloc(v9);
    if ( !v10 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x12B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        v11);
    *(_QWORD *)(a1 + 8) = v10;
    memcpy_0(v10, Src, (v25 - (__int64)Src) >> 2);
    std::vector<float>::~vector<float>(&Src);
  }
  return a1;
}

```

## disassembly

```asm
0x180036954  mov     rax, rsp
0x180036957  mov     [rax+10h], rbx
0x18003695b  mov     [rax+18h], rsi
0x18003695f  mov     [rax+8], rcx
0x180036963  push    rbp
0x180036964  push    rdi
0x180036965  push    r12
0x180036967  push    r14
0x180036969  push    r15
0x18003696b  lea     rbp, [rax-5Fh]
0x18003696f  sub     rsp, 0C0h
0x180036976  mov     r14, r8
0x180036979  mov     r15, rdx
0x18003697c  mov     rsi, rcx
0x18003697f  mov     r12d, 1
0x180036985  mov     [rbp+57h+arg_18], r12d
0x180036989  xorps   xmm0, xmm0
0x18003698c  movups  xmmword ptr [rcx], xmm0
0x18003698f  movups  xmmword ptr [rcx+10h], xmm0
0x180036993  mov     [rbp+57h+arg_18], r12d
0x180036997  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49288935@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49288935@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935> `wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl(void)'::`2'::impl
0x18003699e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49288935@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(void)
0x1800369a3  test    al, al
0x1800369a5  jnz     loc_180036A96
0x1800369ab  mov     dword ptr [rsi], 0
0x1800369b1  lea     ecx, [r12+1Fh]; Size
0x1800369b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800369bb  mov     rdi, rax
0x1800369be  mov     [rbp+57h+var_C0], rax
0x1800369c2  xorps   xmm0, xmm0
0x1800369c5  movups  xmmword ptr [rax], xmm0
0x1800369c8  mov     [rax+8], r12d
0x1800369cc  mov     [rax+0Ch], r12d
0x1800369d0  lea     rax, ??_7?$_Ref_count_obj2@Uembedding_factory@implementation@semantic_index@@@std@@6B@; const std::_Ref_count_obj2<semantic_index::implementation::embedding_factory>::`vftable'
0x1800369d7  mov     [rdi], rax
0x1800369da  lea     rbx, [rdi+10h]
0x1800369de  movups  xmmword ptr [rbx], xmm0
0x1800369e1  mov     rcx, rbx; this
0x1800369e4  call    ??0embedding_converter@semantic_index@@QEAA@XZ; semantic_index::embedding_converter::embedding_converter(void)
0x1800369e9  nop
0x1800369ea  mov     [rbp+57h+arg_18], 9
0x1800369f1  mov     [rbp+57h+var_C0], rbx
0x1800369f5  mov     [rbp+57h+var_B8], rdi
0x1800369f9  mov     r8, r14
0x1800369fc  lea     rdx, [rbp+57h+Src]
0x180036a00  lea     rcx, [rbp+57h+var_C0]
0x180036a04  call    ?get_data@embedding_data_accessor@semantic_index@@QEBA?AV?$vector@MV?$allocator@M@std@@@std@@AEBUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@Z; semantic_index::embedding_data_accessor::get_data(winrt::Microsoft::Windows::SemanticSearch::Embedding const &)
0x180036a09  nop
0x180036a0a  mov     rbx, [rbp+57h+var_B8]
0x180036a0e  test    rbx, rbx
0x180036a11  jz      short loc_180036A4A
0x180036a13  or      eax, 0FFFFFFFFh
0x180036a16  lock xadd [rbx+8], eax
0x180036a1b  cmp     eax, r12d
0x180036a1e  jnz     short loc_180036A4A
0x180036a20  mov     rax, [rbx]
0x180036a23  mov     rcx, rbx
0x180036a26  mov     rax, [rax]
0x180036a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a2e  or      eax, 0FFFFFFFFh
0x180036a31  lock xadd [rbx+0Ch], eax
0x180036a36  cmp     eax, r12d
0x180036a39  jnz     short loc_180036A4A
0x180036a3b  mov     rax, [rbx]
0x180036a3e  mov     rcx, rbx
0x180036a41  mov     rax, [rax+8]
0x180036a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a4a  mov     rcx, [rbp+57h+var_98]
0x180036a4e  sub     rcx, [rbp+57h+Src]
0x180036a52  sar     rcx, 2; cb
0x180036a56  mov     [rsi+4], ecx
0x180036a59  call    cs:__imp_CoTaskMemAlloc
0x180036a5f  mov     rcx, [rbp+5Fh]; this
0x180036a63  test    rax, rax
0x180036a66  jz      loc_180036D00
0x180036a6c  mov     [rsi+8], rax
0x180036a70  mov     rdx, [rbp+57h+Src]; Src
0x180036a74  mov     r8, [rbp+57h+var_98]
0x180036a78  sub     r8, rdx
0x180036a7b  sar     r8, 2; Size
0x180036a7f  mov     rcx, rax; void *
0x180036a82  call    memcpy_0
0x180036a87  nop
0x180036a88  lea     rcx, [rbp+57h+Src]
0x180036a8c  call    ??1?$vector@MV?$allocator@M@std@@@std@@QEAA@XZ; std::vector<float>::~vector<float>(void)
0x180036a91  jmp     loc_180036CE1
0x180036a96  lea     rax, qword_1800AF618
0x180036a9d  mov     [rbp+57h+var_C0], rax
0x180036aa1  lock add cs:qword_1800AF618, r12
0x180036aa9  cmp     cs:??$factory_cache_entry_v@UEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A, 0; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>
0x180036ab1  jz      short loc_180036AD5
0x180036ab3  lea     rdx, [rbp+57h+var_B0]
0x180036ab7  lea     rcx, ??$factory_cache_entry_v@UEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>
0x180036abe  call    ??$ActivateInstance@UEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUEmbeddingsSerializer@SemanticSearch@2Microsoft@3@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Microsoft::Windows::SemanticSearch::EmbeddingsSerializer>(void)
0x180036ac3  mov     edi, 7
0x180036ac8  mov     [rbp+57h+arg_18], edi
0x180036acb  lock dec cs:qword_1800AF618
0x180036ad3  jmp     short loc_180036AFD
0x180036ad5  lock dec cs:qword_1800AF618
0x180036add  lea     rax, ?_lambda_invoker_cdecl_@_lambda_0bef2169a06e939039e50b364aa179a0_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_0bef2169a06e939039e50b364aa179a0_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180036ae4  mov     [rbp+57h+var_A8], rax
0x180036ae8  lea     r8, [rbp+57h+var_A8]
0x180036aec  lea     rdx, [rbp+57h+var_B0]
0x180036af0  call    ??$call@P6A?AUEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@35@@Z@?$factory_cache_entry@UEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@QEAA?A_P$$QEAP6A?AUEmbeddingsSerializer@SemanticSearch@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@52@@Z@Z
0x180036af5  mov     edi, 3
0x180036afa  mov     [rbp+57h+arg_18], edi
0x180036afd  mov     r8, r14
0x180036b00  lea     rdx, [rbp+57h+var_B0]
0x180036b04  lea     rcx, [rbp+57h+Src]
0x180036b08  call    _anonymous_namespace___serialize
0x180036b0d  nop
0x180036b0e  mov     [rsi], r12d
0x180036b11  mov     [rbp+57h+var_78], 0
0x180036b19  mov     [rbp+57h+var_70], 0
0x180036b21  mov     rax, [rbp+57h+Src]
0x180036b25  mov     [rbp+57h+var_80], rax
0x180036b29  mov     rcx, [rbp+57h+var_98]
0x180036b2d  sub     rcx, rax
0x180036b30  mov     [rbp+57h+var_88], rcx
0x180036b34  add     rcx, 1Ch; cb
0x180036b38  mov     [rbp+57h+var_78], rcx
0x180036b3c  call    cs:__imp_CoTaskMemAlloc
0x180036b42  mov     [rbp+57h+var_70], rax
0x180036b46  mov     r9, [rbp+57h+var_88]; wchar_t *
0x180036b4a  lea     r8, aInvokingEnclav; "Invoking enclave emb encryption with in"...
0x180036b51  mov     edx, 116h; wchar_t *
0x180036b56  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036b5d  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180036b62  lea     rcx, [rbp+57h+var_60]
0x180036b66  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180036b6b  nop
0x180036b6c  mov     rbx, [rbp+57h+pv]
0x180036b70  mov     [rbp+57h+var_C0], rbx
0x180036b74  test    rbx, rbx
0x180036b77  jz      short loc_180036B81
0x180036b79  lock add [rbx+120h], r12d
0x180036b81  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180036b88  call    cs:__imp_EnterCriticalSection
0x180036b8e  add     [rbx+0F0h], r12d
0x180036b95  mov     rbx, [rbp+57h+pv]
0x180036b99  mov     [rbp+57h+var_A8], rbx
0x180036b9d  test    rbx, rbx
0x180036ba0  jz      short loc_180036BAA
0x180036ba2  lock add [rbx+120h], r12d
0x180036baa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180036bb1  call    cs:__imp_EnterCriticalSection
0x180036bb7  add     [rbx+0F0h], r12d
0x180036bbe  mov     [rbx+110h], r12b
0x180036bc5  lea     rcx, [rbp+57h+var_A8]
0x180036bc9  call    ??1?$test_data_control@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(void)
0x180036bce  lea     rcx, [rbp+57h+var_C0]
0x180036bd2  call    ??1?$test_data_control@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(void)
0x180036bd7  mov     rbx, [rbp+57h+pv]
0x180036bdb  mov     [rbp+57h+var_C0], rbx
0x180036bdf  test    rbx, rbx
0x180036be2  jz      short loc_180036BEC
0x180036be4  lock add [rbx+120h], r12d
0x180036bec  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180036bf3  call    cs:__imp_EnterCriticalSection
0x180036bf9  add     [rbx+0F0h], r12d
0x180036c00  mov     rax, [rbp+57h+var_88]
0x180036c04  mov     [rbx+118h], rax
0x180036c0b  lea     rcx, [rbp+57h+var_C0]
0x180036c0f  call    ??1?$test_data_control@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(void)
0x180036c14  mov     rax, [r15]
0x180036c17  lea     r8, [rbp+57h+var_88]
0x180036c1b  mov     edx, r12d
0x180036c1e  mov     rcx, r15
0x180036c21  mov     rax, [rax+10h]
0x180036c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c2a  mov     r14, [rbp+57h+pv]
0x180036c2e  lea     rbx, [r14+0C8h]
0x180036c35  mov     rcx, rbx; lpCriticalSection
0x180036c38  call    cs:__imp_EnterCriticalSection
0x180036c3e  or      dword ptr [r14+48h], 300h
0x180036c46  cmp     qword ptr [r14+0F8h], 0
0x180036c4e  jz      short loc_180036C5E
0x180036c50  mov     edx, 2
0x180036c55  lea     rcx, [r14+8]
0x180036c59  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180036c5e  test    rbx, rbx
0x180036c61  jz      short loc_180036C6C
0x180036c63  mov     rcx, rbx; lpCriticalSection
0x180036c66  call    cs:__imp_LeaveCriticalSection
0x180036c6c  lea     r8, aCompletedEmbEn; "Completed emb encryption"
0x180036c73  mov     edx, 11Eh; wchar_t *
0x180036c78  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036c7f  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180036c84  mov     eax, dword ptr [rbp+57h+var_78]
0x180036c87  mov     [rsi+10h], eax
0x180036c8a  mov     rax, [rbp+57h+var_70]
0x180036c8e  mov     [rsi+18h], rax
0x180036c92  mov     rbx, [rbp+57h+pv]
0x180036c96  test    rbx, rbx
0x180036c99  jz      short loc_180036CBC
0x180036c9b  or      eax, 0FFFFFFFFh
0x180036c9e  lock xadd [rbx+120h], eax
0x180036ca6  cmp     eax, 1
0x180036ca9  jnz     short loc_180036CBC
0x180036cab  mov     rcx, rbx
0x180036cae  call    ??1?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(void)
0x180036cb3  mov     rcx, rbx; pv
0x180036cb6  call    cs:__imp_CoTaskMemFree
0x180036cbc  lea     rcx, [rbp+57h+var_58]; this
0x180036cc0  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180036cc5  nop
0x180036cc6  lea     rcx, [rbp+57h+Src]
0x180036cca  call    ??1?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::vector<gsl::byte>::~vector<gsl::byte>(void)
0x180036ccf  nop
0x180036cd0  cmp     [rbp+57h+var_B0], 0
0x180036cd5  jz      short loc_180036CE1
0x180036cd7  lea     rcx, [rbp+57h+var_B0]
0x180036cdb  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180036ce0  nop
0x180036ce1  mov     rax, rsi
0x180036ce4  lea     r11, [rsp+0E0h+var_20]
0x180036cec  mov     rbx, [r11+38h]
0x180036cf0  mov     rsi, [r11+40h]
0x180036cf4  mov     rsp, r11
0x180036cf7  pop     r15
0x180036cf9  pop     r14
0x180036cfb  pop     r12
0x180036cfd  pop     rdi
0x180036cfe  pop     rbp
0x180036cff  retn
0x180036d00  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036d07  mov     edx, 12Bh; void *
0x180036d0c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
