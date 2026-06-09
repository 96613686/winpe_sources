# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x180033f70`
- end: `0x180034286`
- name: `?CreateVectorInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `790`
- prototype: `struct winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector __high(const struct winrt::hstring *, const enum winrt::Microsoft::Windows::Workloads::WorkloadPriority *)`
- caller_count: `4`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180033980`
- `0x180033e10`
- `0x180058d60`
- `0x180059130`

## callees

- `0x1800018b0`
- `0x180001f40`
- `0x180002080`
- `0x180007790`
- `0x180008840`
- `0x18000ed90`
- `0x18000fba0`
- `0x18000fc60`
- `0x180010000`
- `0x180010910`
- `0x180014660`
- `0x1800146c0`
- `0x180015390`
- `0x180015a70`
- `0x180033f70`
- `0x1800353b0`
- `0x1800362d0`
- `0x1800364f0`
- `0x180036e20`
- `0x18004c070`
- `0x18004c8cc`
- `0x18004ecf0`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180034182`
- `KERNEL32!LeaveCriticalSection` at `0x180034182`
- `KERNEL32!EnterCriticalSection` at `0x180034155`
- `KERNEL32!EnterCriticalSection` at `0x180034155`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(
        __int64 a1,
        __int64 *a2,
        const struct winrt::hstring *a3,
        __int64 a4)
{
  const struct _tlgProvider_t *v8; // rax
  winrt::hstring *v9; // rax
  __int64 v10; // rbx
  signed __int64 v11; // rax
  signed __int64 v12; // rtt
  __int64 v13; // r8
  __int64 v14; // rsi
  size_t v15; // rsi
  size_t v16; // rdi
  int v17; // r9d
  __int64 v18; // rcx
  __int64 v19; // rax
  struct _RTL_CRITICAL_SECTION *v20; // rdi
  const struct _tlgProvider_t *v21; // rax
  winrt::hresult *v23; // rax
  winrt::hresult *v24; // rax
  __int64 *v25; // [rsp+30h] [rbp-79h] BYREF
  const char *v26; // [rsp+38h] [rbp-71h]
  LPVOID pv; // [rsp+40h] [rbp-69h] BYREF
  __int64 v28; // [rsp+48h] [rbp-61h] BYREF
  __int128 v29; // [rsp+50h] [rbp-59h] BYREF
  __int64 v30; // [rsp+60h] [rbp-49h] BYREF
  int v31; // [rsp+68h] [rbp-41h]
  int v32; // [rsp+6Ch] [rbp-3Dh]
  __int128 pExceptionObject; // [rsp+80h] [rbp-29h] BYREF
  __int128 *v34; // [rsp+90h] [rbp-19h]
  __int64 v35; // [rsp+98h] [rbp-11h]
  __int128 v36; // [rsp+A8h] [rbp-1h] BYREF
  size_t v37; // [rsp+B8h] [rbp+Fh]

  v25 = a2;
  v8 = TraceLogger::Provider();
  if ( *(_DWORD *)v8 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v8,
      (unsigned __int8 *)&word_180079C0E);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::GetImpl'::`2'::impl) )
  {
    LODWORD(v25) = 81;
    v26 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\SemanticText\\SemanticTextEmbeddingsCreator.cpp";
    winrt::param::hstring::hstring((winrt::param::hstring *)&v30, L"Velocity key not enabled");
    v24 = winrt::hresult::hresult((winrt::hresult *)&pv, -2147467259);
    winrt::hresult_error::hresult_error(&pExceptionObject, *(unsigned int *)v24, &v30, &v25);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    LODWORD(v25) = 86;
    v26 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\SemanticText\\SemanticTextEmbeddingsCreator.cpp";
    v23 = winrt::hresult::hresult((winrt::hresult *)&pv, -2147483629);
    winrt::hresult_error::hresult_error(&pExceptionObject, *(unsigned int *)v23, &v25);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  v9 = winrt::hstring::hstring((winrt::hstring *)&v28, a3);
  CheckContainsNullChar(v9);
  v10 = 0;
  v28 = 0;
  if ( a1 )
  {
    v10 = a1;
    v28 = a1;
    v11 = *(_QWORD *)(a1 + 8);
    if ( v11 < 0 )
    {
LABEL_9:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v11 + 24));
    }
    else
    {
      while ( 1 )
      {
        v12 = v11;
        v11 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v11 + 1, v11);
        if ( v12 == v11 )
          break;
        if ( v11 < 0 )
          goto LABEL_9;
      }
    }
  }
  pv = 0;
  tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_SemTextTest,AIFabricTipTest::_tip_SemTextTest>>>(&pv);
  v14 = *(unsigned int *)(a1 + 80);
  v36 = 0;
  v37 = 0;
  if ( v14 )
  {
    _mm_lfence();
    v15 = 4 * v14;
    *(_QWORD *)&v36 = std::_Allocate<16,std::_Default_allocate_traits>(v15);
    v16 = v15 + v36;
    v37 = v15 + v36;
    memset((void *)v36, 0, v15);
    *((_QWORD *)&v36 + 1) = v16;
  }
  *(_QWORD *)&pExceptionObject = a1;
  *((_QWORD *)&pExceptionObject + 1) = a3;
  v34 = &v36;
  v35 = a4;
  *(_QWORD *)&v29 = a1 + 40;
  v30 = a1 + 40;
  RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal_::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal_::_2_::_lambda_1____::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal_::_2_::_lambda_1____::_2_::_lambda_2___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal_::_2_::_lambda_1____::_2_::_lambda_3___(
    &pExceptionObject,
    &v30,
    v13,
    &v29);
  v25 = (__int64 *)a1;
  v30 = a1 + 40;
  *(_QWORD *)&v29 = a1 + 40;
  RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1____::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1____::_2_::_lambda_2___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator__winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::VectorSpaceId_::_2_::_lambda_1____::_2_::_lambda_3___(
    (unsigned int)&pExceptionObject,
    (unsigned int)&v25,
    (unsigned int)&v29,
    v17,
    (__int64)&v30);
  v30 = v36;
  v31 = (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 2;
  v32 = HIDWORD(pExceptionObject);
  v25 = (__int64 *)operator new(0x40u);
  v29 = pExceptionObject;
  v18 = winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(
          v25,
          &v30,
          &v29);
  v19 = v18 + 16;
  if ( !v18 )
    v19 = 0;
  *a2 = v19;
  v20 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    LODWORD(v20[1].SpinCount) |= 0x300u;
    if ( v20[6].DebugInfo )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)&v20->LockCount, 2u);
    if ( v20 != (struct _RTL_CRITICAL_SECTION *)-200LL )
      LeaveCriticalSection(v20 + 5);
  }
  v21 = TraceLogger::Provider();
  if ( *(_DWORD *)v21 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v21,
      (unsigned __int8 *)qword_180079BF0);
  std::vector<float>::_Tidy(&v36);
  if ( v20 )
    tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release((volatile signed __int32 *)v20);
  if ( v10 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(&v28);
  return a2;
}

```

## disassembly

```asm
0x180033f70  mov     [rsp-8+arg_18], rbx
0x180033f75  push    rbp
0x180033f76  push    rsi
0x180033f77  push    rdi
0x180033f78  push    r12
0x180033f7a  push    r13
0x180033f7c  push    r14
0x180033f7e  push    r15
0x180033f80  lea     rbp, [rsp-27h]
0x180033f85  sub     rsp, 0D0h
0x180033f8c  mov     rax, cs:__security_cookie
0x180033f93  xor     rax, rsp
0x180033f96  mov     [rbp+57h+var_40], rax
0x180033f9a  mov     r13, r9
0x180033f9d  mov     r12, r8
0x180033fa0  mov     r15, rdx
0x180033fa3  mov     r14, rcx
0x180033fa6  mov     [rbp+57h+var_D0], rdx
0x180033faa  xor     edi, edi
0x180033fac  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180033fb1  cmp     dword ptr [rax], 5
0x180033fb4  jbe     short loc_180033FC5
0x180033fb6  lea     rdx, word_180079C0E
0x180033fbd  mov     rcx, rax
0x180033fc0  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180033fc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_SEMTXT@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_SEMTXT@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_SEMTXT> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::GetImpl(void)'::`2'::impl
0x180033fcc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_SEMTXT@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_SEMTXT>::__private_IsEnabled(void)
0x180033fd1  test    al, al
0x180033fd3  jz      loc_180034232
0x180033fd9  movzx   eax, byte ptr [r14+48h]
0x180033fde  test    al, al
0x180033fe0  jnz     loc_1800341F2
0x180033fe6  mov     rdx, r12; struct winrt::hstring *
0x180033fe9  lea     rcx, [rbp+57h+var_B8]; this
0x180033fed  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180033ff2  mov     rcx, rax
0x180033ff5  call    ?CheckContainsNullChar@@YAXUhstring@winrt@@@Z; CheckContainsNullChar(winrt::hstring)
0x180033ffa  mov     rbx, rdi
0x180033ffd  mov     [rbp+57h+var_B8], rbx
0x180034001  test    r14, r14
0x180034004  jz      short loc_180034036
0x180034006  mov     rbx, r14
0x180034009  mov     [rbp+57h+var_B8], rbx
0x18003400d  mov     rax, [r14+8]
0x180034011  test    rax, rax
0x180034014  js      short loc_180034031
0x180034016  nop     word ptr [rax+rax+00000000h]
0x180034020  lea     rcx, [rax+1]
0x180034024  lock cmpxchg [r14+8], rcx
0x18003402a  jz      short loc_180034036
0x18003402c  test    rax, rax
0x18003402f  jns     short loc_180034020
0x180034031  lock inc dword ptr [rax+rax+18h]
0x180034036  mov     [rbp+57h+pv], rdi
0x18003403a  lea     rcx, [rbp+57h+pv]
0x18003403e  call    ??$start@V?$tip_test@V?$merged_data@U_tip_SemTextTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_SemTextTest@AIFabricTipTest@@U12@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_SemTextTest,AIFabricTipTest::_tip_SemTextTest>>>(void)
0x180034043  nop
0x180034044  xorps   xmm0, xmm0
0x180034047  mov     esi, [r14+50h]
0x18003404b  movdqu  [rbp+57h+var_58], xmm0
0x180034050  mov     [rbp+57h+var_48], rdi
0x180034054  test    rsi, rsi
0x180034057  jz      short loc_180034089
0x180034059  lfence
0x18003405c  lea     rsi, ds:0[rsi*4]
0x180034064  mov     rcx, rsi
0x180034067  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003406c  mov     qword ptr [rbp+57h+var_58], rax
0x180034070  lea     rdi, [rsi+rax]
0x180034074  mov     [rbp+57h+var_48], rdi
0x180034078  mov     r8, rsi; Size
0x18003407b  xor     edx, edx; Val
0x18003407d  mov     rcx, rax; void *
0x180034080  call    memset
0x180034085  mov     qword ptr [rbp+57h+var_58+8], rdi
0x180034089  lea     rdi, [r14+28h]
0x18003408d  mov     qword ptr [rbp+57h+pExceptionObject], r14
0x180034091  mov     qword ptr [rbp+57h+pExceptionObject+8], r12
0x180034095  lea     rax, [rbp+57h+var_58]
0x180034099  mov     [rbp+57h+var_70], rax
0x18003409d  mov     [rbp+57h+var_68], r13
0x1800340a1  mov     qword ptr [rbp+57h+var_B0], rdi
0x1800340a5  mov     qword ptr [rbp+57h+var_A0], rdi
0x1800340a9  lea     r9, [rbp+57h+var_B0]
0x1800340ad  lea     rdx, [rbp+57h+var_A0]
0x1800340b1  lea     rcx, [rbp+57h+pExceptionObject]
0x1800340b5  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorInternal____2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorInternal____2____lambda_1_______2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorInternal____2____lambda_1_______2____lambda_2___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__CreateVectorInternal____2____lambda_1_______2____lambda_3___
0x1800340ba  mov     [rbp+57h+var_D0], r14
0x1800340be  mov     qword ptr [rbp+57h+var_A0], rdi
0x1800340c2  mov     qword ptr [rbp+57h+var_B0], rdi
0x1800340c6  lea     rax, [rbp+57h+var_A0]
0x1800340ca  mov     [rsp+100h+var_E0], rax
0x1800340cf  lea     r8, [rbp+57h+var_B0]
0x1800340d3  lea     rdx, [rbp+57h+var_D0]
0x1800340d7  lea     rcx, [rbp+57h+pExceptionObject]
0x1800340db  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1_______2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1_______2____lambda_2___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator_winrt__Microsoft__Windows__SemanticSearchInternal__ISemanticTextSession2_2___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__SemanticTextEmbeddingsCreator__winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextEmbeddingsCreator__VectorSpaceId____2____lambda_1_______2____lambda_3___
0x1800340e0  mov     rax, qword ptr [rbp+57h+var_58]
0x1800340e4  mov     qword ptr [rbp+57h+var_A0], rax
0x1800340e8  mov     rcx, qword ptr [rbp+57h+var_58+8]
0x1800340ec  sub     rcx, rax
0x1800340ef  sar     rcx, 2
0x1800340f3  mov     dword ptr [rbp+57h+var_A0+8], ecx
0x1800340f6  mov     eax, dword ptr [rbp+57h+pExceptionObject+0Ch]
0x1800340f9  mov     dword ptr [rbp+57h+var_A0+0Ch], eax
0x1800340fc  mov     ecx, 40h ; '@'; Size
0x180034101  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034106  mov     [rbp+57h+var_D0], rax
0x18003410a  movaps  xmm0, [rbp+57h+pExceptionObject]
0x18003410e  movdqa  [rbp+57h+var_B0], xmm0
0x180034113  movaps  xmm1, [rbp+57h+var_A0]
0x180034117  movdqa  [rbp+57h+var_A0], xmm1
0x18003411c  lea     r8, [rbp+57h+var_B0]
0x180034120  lea     rdx, [rbp+57h+var_A0]
0x180034124  mov     rcx, rax
0x180034127  call    ??0?$heap_implements@UEmbeddingVector@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEAA@U?$array_view@$$CBM@2@Uguid@2@@Z; winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(winrt::array_view<float const>,winrt::guid)
0x18003412c  mov     rcx, rax
0x18003412f  add     rax, 10h
0x180034133  test    rcx, rcx
0x180034136  mov     ecx, 0
0x18003413b  cmovz   rax, rcx
0x18003413f  mov     [r15], rax
0x180034142  mov     rdi, [rbp+57h+pv]
0x180034146  test    rdi, rdi
0x180034149  jz      short loc_180034188
0x18003414b  lea     r14, [rdi+0C8h]
0x180034152  mov     rcx, r14; lpCriticalSection
0x180034155  call    cs:__imp_EnterCriticalSection
0x18003415b  or      dword ptr [rdi+48h], 300h
0x180034162  cmp     qword ptr [rdi+0F0h], 0
0x18003416a  jz      short loc_18003417A
0x18003416c  mov     edx, 2
0x180034171  lea     rcx, [rdi+8]
0x180034175  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003417a  test    r14, r14
0x18003417d  jz      short loc_180034188
0x18003417f  mov     rcx, r14; lpCriticalSection
0x180034182  call    cs:__imp_LeaveCriticalSection
0x180034188  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18003418d  cmp     dword ptr [rax], 5
0x180034190  jbe     short loc_1800341A2
0x180034192  lea     rdx, qword_180079BF0
0x180034199  mov     rcx, rax
0x18003419c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800341a1  nop
0x1800341a2  lea     rcx, [rbp+57h+var_58]
0x1800341a6  call    ?_Tidy@?$vector@MV?$allocator@M@std@@@std@@AEAAXXZ; std::vector<float>::_Tidy(void)
0x1800341ab  nop
0x1800341ac  test    rdi, rdi
0x1800341af  jz      short loc_1800341BA
0x1800341b1  mov     rcx, rdi; pv
0x1800341b4  call    ?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)
0x1800341b9  nop
0x1800341ba  test    rbx, rbx
0x1800341bd  jz      short loc_1800341C8
0x1800341bf  lea     rcx, [rbp+57h+var_B8]
0x1800341c3  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x1800341c8  mov     rax, r15
0x1800341cb  mov     rcx, [rbp+57h+var_40]
0x1800341cf  xor     rcx, rsp; StackCookie
0x1800341d2  call    __security_check_cookie
0x1800341d7  mov     rbx, [rsp+100h+arg_18]
0x1800341df  add     rsp, 0D0h
0x1800341e6  pop     r15
0x1800341e8  pop     r14
0x1800341ea  pop     r13
0x1800341ec  pop     r12
0x1800341ee  pop     rdi
0x1800341ef  pop     rsi
0x1800341f0  pop     rbp
0x1800341f1  retn
0x1800341f2  mov     dword ptr [rbp+57h+var_D0], 56h ; 'V'
0x1800341f9  lea     rax, aCW1SProductApi_10; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180034200  mov     [rbp+57h+var_C8], rax
0x180034204  mov     edx, 80000013h; int
0x180034209  lea     rcx, [rbp+57h+pv]; this
0x18003420d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180034212  lea     r8, [rbp+57h+var_D0]
0x180034216  mov     edx, [rax]
0x180034218  lea     rcx, [rbp+57h+pExceptionObject]
0x18003421c  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x180034221  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180034228  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003422c  call    _CxxThrowException
0x180034232  mov     dword ptr [rbp+57h+var_D0], 51h ; 'Q'
0x180034239  lea     rax, aCW1SProductApi_10; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180034240  mov     [rbp+57h+var_C8], rax
0x180034244  lea     rdx, aVelocityKeyNot; "Velocity key not enabled"
0x18003424b  lea     rcx, [rbp+57h+var_A0]; this
0x18003424f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180034254  mov     edx, 80004005h; int
0x180034259  lea     rcx, [rbp+57h+pv]; this
0x18003425d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180034262  lea     r9, [rbp+57h+var_D0]
0x180034266  lea     r8, [rbp+57h+var_A0]
0x18003426a  mov     edx, [rax]
0x18003426c  lea     rcx, [rbp+57h+pExceptionObject]
0x180034270  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180034275  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003427c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180034280  call    _CxxThrowException
```
