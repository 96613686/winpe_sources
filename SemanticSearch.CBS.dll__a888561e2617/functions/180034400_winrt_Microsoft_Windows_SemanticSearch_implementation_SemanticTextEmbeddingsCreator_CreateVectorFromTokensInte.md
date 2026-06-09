# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x180034400`
- end: `0x18003479d`
- name: `?CreateVectorFromTokensInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `925`
- prototype: ``
- caller_count: `4`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180033af0`
- `0x180034290`
- `0x180059520`
- `0x180059980`

## callees

- `0x1800018b0`
- `0x180001f40`
- `0x180002080`
- `0x180007790`
- `0x180008840`
- `0x180009580`
- `0x18000ed90`
- `0x18000fba0`
- `0x18000fc60`
- `0x180010000`
- `0x180010910`
- `0x180014660`
- `0x180015a70`
- `0x180034400`
- `0x1800353b0`
- `0x1800363d0`
- `0x1800364f0`
- `0x180036c70`
- `0x180036e20`
- `0x18004c070`
- `0x18004c8cc`
- `0x18004ecf0`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18003460b`
- `KERNEL32!LeaveCriticalSection` at `0x18003460b`
- `KERNEL32!EnterCriticalSection` at `0x1800345de`
- `KERNEL32!EnterCriticalSection` at `0x1800345de`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(
        __int64 a1,
        __int64 *a2,
        __m128i *a3,
        __int64 a4)
{
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rbx
  signed __int64 v10; // rax
  signed __int64 v11; // rtt
  __int64 v12; // rsi
  size_t v13; // rsi
  size_t v14; // rdi
  __int64 v15; // r8
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18; // rax
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  const struct _tlgProvider_t *v20; // rax
  __m128i v22; // xmm1
  __int64 v23; // r8
  int v24; // eax
  winrt::hresult *v25; // rax
  winrt::hresult *v26; // rax
  __int64 *v27; // [rsp+40h] [rbp-89h] BYREF
  const char *v28; // [rsp+48h] [rbp-81h]
  LPVOID pv; // [rsp+50h] [rbp-79h] BYREF
  __int64 v30; // [rsp+58h] [rbp-71h] BYREF
  __int128 v31; // [rsp+60h] [rbp-69h] BYREF
  __int64 v32; // [rsp+70h] [rbp-59h] BYREF
  int v33; // [rsp+78h] [rbp-51h]
  int v34; // [rsp+7Ch] [rbp-4Dh]
  __int128 pExceptionObject; // [rsp+90h] [rbp-39h] BYREF
  __int128 *v36; // [rsp+A0h] [rbp-29h]
  __int64 v37; // [rsp+A8h] [rbp-21h]
  __int128 v38; // [rsp+B8h] [rbp-11h] BYREF
  size_t v39; // [rsp+C8h] [rbp-1h]

  v27 = a2;
  v8 = TraceLogger::Provider();
  if ( *(_DWORD *)v8 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v8,
      (unsigned __int8 *)&word_180079C0E);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::GetImpl'::`2'::impl) )
  {
    LODWORD(v27) = 142;
    v28 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\SemanticText\\SemanticTextEmbeddingsCreator.cpp";
    winrt::param::hstring::hstring((winrt::param::hstring *)&v32, L"Velocity key not enabled");
    v26 = winrt::hresult::hresult((winrt::hresult *)&pv, -2147467259);
    winrt::hresult_error::hresult_error(&pExceptionObject, *(unsigned int *)v26, &v32, &v27);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    LODWORD(v27) = 147;
    v28 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\SemanticText\\SemanticTextEmbeddingsCreator.cpp";
    v25 = winrt::hresult::hresult((winrt::hresult *)&pv, -2147483629);
    winrt::hresult_error::hresult_error(&pExceptionObject, *(unsigned int *)v25, &v27);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  v9 = 0;
  v30 = 0;
  if ( a1 )
  {
    v9 = a1;
    v30 = a1;
    v10 = *(_QWORD *)(a1 + 8);
    if ( v10 < 0 )
    {
LABEL_9:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v10 + 24));
    }
    else
    {
      while ( 1 )
      {
        v11 = v10;
        v10 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v10 + 1, v10);
        if ( v11 == v10 )
          break;
        if ( v10 < 0 )
          goto LABEL_9;
      }
    }
  }
  pv = 0;
  tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_SemTextTest,AIFabricTipTest::_tip_SemTextTest>>>(&pv);
  v12 = *(unsigned int *)(a1 + 80);
  v38 = 0;
  v39 = 0;
  if ( v12 )
  {
    _mm_lfence();
    v13 = 4 * v12;
    *(_QWORD *)&v38 = std::_Allocate<16,std::_Default_allocate_traits>(v13);
    v14 = v13 + v38;
    v39 = v13 + v38;
    memset((void *)v38, 0, v13);
    *((_QWORD *)&v38 + 1) = v14;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_7AyR4ebk>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_7AyR4ebk>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&pExceptionObject = a1;
    *((_QWORD *)&pExceptionObject + 1) = a3;
    v36 = &v38;
    v37 = a4;
    *(_QWORD *)&v31 = a1 + 40;
    v32 = a1 + 40;
    RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal_::_11_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal_::_11_::_lambda_1____::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal_::_11_::_lambda_1____::_2_::_lambda_2___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal_::_11_::_lambda_1____::_2_::_lambda_3___(
      &pExceptionObject,
      &v32,
      v15,
      &v31);
  }
  else
  {
    v22 = *a3;
    LODWORD(v27) = 218;
    v28 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Windows.SemanticSearchInternal.h";
    v23 = 8;
    if ( a3->m128i_i32[2] )
      v23 = a3->m128i_i64[0];
    v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 64) + 72LL))(
            *(_QWORD *)(a1 + 64),
            (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v22, 8)),
            v23);
    if ( v24 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v24, &v27);
    }
  }
  v27 = (__int64 *)a1;
  v32 = a1 + 40;
  *(_QWORD *)&v31 = a1 + 40;
  RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1____::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1____::_2_::_lambda_2___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1____::_2_::_lambda_3___(
    (unsigned int)&pExceptionObject,
    (unsigned int)&v27,
    (unsigned int)&v31,
    v16,
    (__int64)&v32);
  v32 = v38;
  v33 = (__int64)(*((_QWORD *)&v38 + 1) - v38) >> 2;
  v34 = HIDWORD(pExceptionObject);
  v27 = (__int64 *)operator new(0x40u);
  v31 = pExceptionObject;
  v17 = winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(
          v27,
          &v32,
          &v31);
  v18 = v17 + 16;
  if ( !v17 )
    v18 = 0;
  *a2 = v18;
  v19 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    LODWORD(v19[1].SpinCount) |= 0x300u;
    if ( v19[6].DebugInfo )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)&v19->LockCount, 2u);
    if ( v19 != (struct _RTL_CRITICAL_SECTION *)-200LL )
      LeaveCriticalSection(v19 + 5);
  }
  v20 = TraceLogger::Provider();
  if ( *(_DWORD *)v20 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v20,
      (unsigned __int8 *)qword_180079BF0);
  std::vector<float>::_Tidy(&v38);
  if ( v19 )
    tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release((volatile signed __int32 *)v19);
  if ( v9 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(&v30);
  return a2;
}

```

## disassembly

```asm
0x180034400  push    rbp
0x180034402  push    rbx
0x180034403  push    rsi
0x180034404  push    rdi
0x180034405  push    r12
0x180034407  push    r13
0x180034409  push    r14
0x18003440b  push    r15
0x18003440d  lea     rbp, [rsp-1Fh]
0x180034412  sub     rsp, 0E8h
0x180034419  mov     rax, cs:__security_cookie
0x180034420  xor     rax, rsp
0x180034423  mov     [rbp+57h+var_50], rax
0x180034427  mov     r13, r9
0x18003442a  mov     r12, r8
0x18003442d  mov     r15, rdx
0x180034430  mov     r14, rcx
0x180034433  mov     [rsp+120h+var_E0], rdx
0x180034438  xor     edi, edi
0x18003443a  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18003443f  cmp     dword ptr [rax], 5
0x180034442  jbe     short loc_180034453
0x180034444  lea     rdx, word_180079C0E
0x18003444b  mov     rcx, rax
0x18003444e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180034453  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_SEMTXT@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_SEMTXT@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_SEMTXT> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::GetImpl(void)'::`2'::impl
0x18003445a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_SEMTXT@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::__private_IsEnabled(void)
0x18003445f  test    al, al
0x180034461  jz      loc_180034746
0x180034467  movzx   eax, byte ptr [r14+48h]
0x18003446c  test    al, al
0x18003446e  jnz     loc_1800346F3
0x180034474  mov     rbx, rdi
0x180034477  mov     [rbp+57h+var_C8], rbx
0x18003447b  test    r14, r14
0x18003447e  jz      short loc_1800344A6
0x180034480  mov     rbx, r14
0x180034483  mov     [rbp+57h+var_C8], rbx
0x180034487  mov     rax, [r14+8]
0x18003448b  test    rax, rax
0x18003448e  js      short loc_1800344A1
0x180034490  lea     rcx, [rax+1]
0x180034494  lock cmpxchg [r14+8], rcx
0x18003449a  jz      short loc_1800344A6
0x18003449c  test    rax, rax
0x18003449f  jns     short loc_180034490
0x1800344a1  lock inc dword ptr [rax+rax+18h]
0x1800344a6  mov     [rbp+57h+pv], rdi
0x1800344aa  lea     rcx, [rbp+57h+pv]
0x1800344ae  call    ??$start@V?$tip_test@V?$merged_data@U_tip_SemTextTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_SemTextTest@AIFabricTipTest@@U12@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_SemTextTest,AIFabricTipTest::_tip_SemTextTest>>>(void)
0x1800344b3  nop
0x1800344b4  xorps   xmm0, xmm0
0x1800344b7  mov     esi, [r14+50h]
0x1800344bb  movdqu  [rbp+57h+var_68], xmm0
0x1800344c0  mov     [rbp+57h+var_58], rdi
0x1800344c4  test    rsi, rsi
0x1800344c7  jz      short loc_1800344F9
0x1800344c9  lfence
0x1800344cc  lea     rsi, ds:0[rsi*4]
0x1800344d4  mov     rcx, rsi
0x1800344d7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800344dc  mov     qword ptr [rbp+57h+var_68], rax
0x1800344e0  lea     rdi, [rsi+rax]
0x1800344e4  mov     [rbp+57h+var_58], rdi
0x1800344e8  mov     r8, rsi; Size
0x1800344eb  xor     edx, edx; Val
0x1800344ed  mov     rcx, rax; void *
0x1800344f0  call    memset
0x1800344f5  mov     qword ptr [rbp+57h+var_68+8], rdi
0x1800344f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_7AyR4ebk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_7AyR4ebk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_7AyR4ebk> `wil::Feature<__WilFeatureTraits_Feature_7AyR4ebk>::GetImpl(void)'::`2'::impl
0x180034500  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_7AyR4ebk@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_7AyR4ebk>::__private_IsEnabled(void)
0x180034505  test    al, al
0x180034507  jz      loc_180034674
0x18003450d  lea     rax, [r14+28h]
0x180034511  mov     qword ptr [rbp+57h+pExceptionObject], r14
0x180034515  mov     qword ptr [rbp+57h+pExceptionObject+8], r12
0x180034519  lea     rcx, [rbp+57h+var_68]
0x18003451d  mov     [rbp+57h+var_80], rcx
0x180034521  mov     [rbp+57h+var_78], r13
0x180034525  mov     qword ptr [rbp+57h+var_C0], rax
0x180034529  mov     qword ptr [rbp+57h+var_B0], rax
0x18003452d  lea     r9, [rbp+57h+var_C0]
0x180034531  lea     rdx, [rbp+57h+var_B0]
0x180034535  lea     rcx, [rbp+57h+pExceptionObject]
0x180034539  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorFromTokensInternal____11____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorFromTokensInternal____11____lambda_1_______2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorFromTokensInternal____11____lambda_1_______2____lambda_2___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorFromTokensInternal____11____lambda_1_______2____lambda_3___
0x18003453e  xor     r12d, r12d
0x180034541  lea     rax, [r14+28h]
0x180034545  mov     [rsp+120h+var_E0], r14
0x18003454a  mov     qword ptr [rbp+57h+var_B0], rax
0x18003454e  mov     qword ptr [rbp+57h+var_C0], rax
0x180034552  lea     rax, [rbp+57h+var_B0]
0x180034556  mov     [rsp+120h+var_100], rax
0x18003455b  lea     r8, [rbp+57h+var_C0]
0x18003455f  lea     rdx, [rsp+120h+var_E0]
0x180034564  lea     rcx, [rbp+57h+pExceptionObject]
0x180034568  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1_______2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1_______2____lambda_2___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1_______2____lambda_3___
0x18003456d  mov     rax, qword ptr [rbp+57h+var_68]
0x180034571  mov     qword ptr [rbp+57h+var_B0], rax
0x180034575  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x180034579  sub     rcx, rax
0x18003457c  sar     rcx, 2
0x180034580  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x180034583  mov     eax, dword ptr [rbp+57h+pExceptionObject+0Ch]
0x180034586  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x180034589  mov     ecx, 40h ; '@'; Size
0x18003458e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034593  mov     [rsp+120h+var_E0], rax
0x180034598  movaps  xmm0, [rbp+57h+pExceptionObject]
0x18003459c  movdqa  [rbp+57h+var_C0], xmm0
0x1800345a1  movaps  xmm1, [rbp+57h+var_B0]
0x1800345a5  movdqa  [rbp+57h+var_B0], xmm1
0x1800345aa  lea     r8, [rbp+57h+var_C0]
0x1800345ae  lea     rdx, [rbp+57h+var_B0]
0x1800345b2  mov     rcx, rax
0x1800345b5  call    ??0?$heap_implements@UEmbeddingVector@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEAA@U?$array_view@$$CBM@2@Uguid@2@@Z; winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(winrt::array_view<float const>,winrt::guid)
0x1800345ba  mov     rcx, rax
0x1800345bd  add     rax, 10h
0x1800345c1  test    rcx, rcx
0x1800345c4  cmovz   rax, r12
0x1800345c8  mov     [r15], rax
0x1800345cb  mov     rdi, [rbp+57h+pv]
0x1800345cf  test    rdi, rdi
0x1800345d2  jz      short loc_180034611
0x1800345d4  lea     r14, [rdi+0C8h]
0x1800345db  mov     rcx, r14; lpCriticalSection
0x1800345de  call    cs:__imp_EnterCriticalSection
0x1800345e4  or      dword ptr [rdi+48h], 300h
0x1800345eb  cmp     qword ptr [rdi+0F0h], 0
0x1800345f3  jz      short loc_180034603
0x1800345f5  mov     edx, 2
0x1800345fa  lea     rcx, [rdi+8]
0x1800345fe  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180034603  test    r14, r14
0x180034606  jz      short loc_180034611
0x180034608  mov     rcx, r14; lpCriticalSection
0x18003460b  call    cs:__imp_LeaveCriticalSection
0x180034611  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180034616  cmp     dword ptr [rax], 5
0x180034619  jbe     short loc_18003462B
0x18003461b  lea     rdx, qword_180079BF0
0x180034622  mov     rcx, rax
0x180034625  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003462a  nop
0x18003462b  lea     rcx, [rbp+57h+var_68]
0x18003462f  call    ?_Tidy@?$vector@MV?$allocator@M@std@@@std@@AEAAXXZ; std::vector<float>::_Tidy(void)
0x180034634  nop
0x180034635  test    rdi, rdi
0x180034638  jz      short loc_180034643
0x18003463a  mov     rcx, rdi; pv
0x18003463d  call    ?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)
0x180034642  nop
0x180034643  test    rbx, rbx
0x180034646  jz      short loc_180034651
0x180034648  lea     rcx, [rbp+57h+var_C8]
0x18003464c  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180034651  mov     rax, r15
0x180034654  mov     rcx, [rbp+57h+var_50]
0x180034658  xor     rcx, rsp; StackCookie
0x18003465b  call    __security_check_cookie
0x180034660  add     rsp, 0E8h
0x180034667  pop     r15
0x180034669  pop     r14
0x18003466b  pop     r13
0x18003466d  pop     r12
0x18003466f  pop     rdi
0x180034670  pop     rsi
0x180034671  pop     rbx
0x180034672  pop     rbp
0x180034673  retn
0x180034674  mov     esi, [r13+0]
0x180034678  mov     r9, qword ptr [rbp+57h+var_68+8]
0x18003467c  sub     r9, qword ptr [rbp+57h+var_68]
0x180034680  sar     r9, 2
0x180034684  movups  xmm1, xmmword ptr [r12]
0x180034689  mov     dword ptr [rsp+120h+var_E0], 0DAh
0x180034691  lea     rax, aCW1SProductApi_7; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180034698  mov     [rsp+120h+var_D8], rax
0x18003469d  mov     rdi, [r14+40h]
0x1800346a1  mov     rax, [rdi]
0x1800346a4  mov     r10d, 4
0x1800346aa  test    r9d, r9d
0x1800346ad  cmovnz  r10, qword ptr [rbp+57h+var_68]
0x1800346b2  mov     r8d, 8
0x1800346b8  cmp     dword ptr [r12+8], 0
0x1800346be  cmovnz  r8, [r12]
0x1800346c3  xor     r12d, r12d
0x1800346c6  mov     [rsp+120h+var_F0], r12d
0x1800346cb  mov     [rsp+120h+var_F8], esi
0x1800346cf  mov     [rsp+120h+var_100], r10
0x1800346d4  psrldq  xmm1, 8
0x1800346d9  movd    edx, xmm1
0x1800346dd  mov     rcx, rdi
0x1800346e0  mov     rax, [rax+48h]
0x1800346e4  call    cs:__guard_dispatch_icall_fptr
0x1800346ea  test    eax, eax
0x1800346ec  js      short loc_180034736
0x1800346ee  jmp     loc_180034541
0x1800346f3  mov     dword ptr [rsp+120h+var_E0], 93h
0x1800346fb  lea     rax, aCW1SProductApi_10; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180034702  mov     [rsp+120h+var_D8], rax
0x180034707  mov     edx, 80000013h; int
0x18003470c  lea     rcx, [rbp+57h+pv]; this
0x180034710  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180034715  lea     r8, [rsp+120h+var_E0]
0x18003471a  mov     edx, [rax]
0x18003471c  lea     rcx, [rbp+57h+pExceptionObject]
0x180034720  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x180034725  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003472c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180034730  call    _CxxThrowException
0x180034736  lfence
0x180034739  lea     rdx, [rsp+120h+var_E0]
0x18003473e  mov     ecx, eax
0x180034740  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180034746  mov     dword ptr [rsp+120h+var_E0], 8Eh
0x18003474e  lea     rax, aCW1SProductApi_10; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180034755  mov     [rsp+120h+var_D8], rax
0x18003475a  lea     rdx, aVelocityKeyNot; "Velocity key not enabled"
0x180034761  lea     rcx, [rbp+57h+var_B0]; this
0x180034765  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003476a  mov     edx, 80004005h; int
0x18003476f  lea     rcx, [rbp+57h+pv]; this
0x180034773  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180034778  lea     r9, [rsp+120h+var_E0]
0x18003477d  lea     r8, [rbp+57h+var_B0]
0x180034781  mov     edx, [rax]
0x180034783  lea     rcx, [rbp+57h+pExceptionObject]
0x180034787  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18003478c  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180034793  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180034797  call    _CxxThrowException
```
