# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x18000afa0`
- end: `0x18000b292`
- name: `?CreateVectorForTextInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `754`
- prototype: `struct winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector __high(const struct winrt::hstring *, const enum winrt::Microsoft::Windows::Workloads::WorkloadPriority *)`
- caller_count: `4`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x18000a440`
- `0x18000ae40`
- `0x1800524e0`
- `0x1800528b0`

## callees

- `0x1800018b0`
- `0x180001f40`
- `0x180002bb0`
- `0x180008840`
- `0x180009580`
- `0x18000afa0`
- `0x18000b6b0`
- `0x18000cf50`
- `0x18000ed90`
- `0x18000f4f0`
- `0x18000fba0`
- `0x18000fc60`
- `0x180010740`
- `0x180010910`
- `0x1800146c0`
- `0x180015390`
- `0x180015450`
- `0x180015a70`
- `0x18004c070`
- `0x18004c8cc`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000b173`
- `KERNEL32!LeaveCriticalSection` at `0x18000b173`
- `KERNEL32!EnterCriticalSection` at `0x18000b146`
- `KERNEL32!EnterCriticalSection` at `0x18000b146`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(
        __int64 a1,
        __int64 *a2,
        const struct winrt::hstring *a3,
        int *a4)
{
  char v8; // bl
  winrt::hstring *v9; // rax
  const struct _tlgProvider_t *v10; // rax
  int v11; // r9d
  __int64 v12; // rdi
  size_t v13; // rdi
  size_t v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  const struct _tlgProvider_t *v18; // rax
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  __int128 *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rcx
  winrt::hresult *v24; // rax
  winrt::hresult *v25; // rax
  LPVOID pv; // [rsp+30h] [rbp-69h] BYREF
  __int64 *v27; // [rsp+38h] [rbp-61h] BYREF
  const char *v28; // [rsp+40h] [rbp-59h]
  __int64 v29; // [rsp+50h] [rbp-49h] BYREF
  const char *v30; // [rsp+58h] [rbp-41h]
  _QWORD v31[2]; // [rsp+60h] [rbp-39h] BYREF
  const struct winrt::hstring *v32; // [rsp+70h] [rbp-29h] BYREF
  int v33; // [rsp+78h] [rbp-21h]
  __int64 v34; // [rsp+80h] [rbp-19h]
  __int128 v35; // [rsp+90h] [rbp-9h] BYREF
  __int128 v36; // [rsp+A0h] [rbp+7h] BYREF
  size_t v37; // [rsp+B0h] [rbp+17h]

  v27 = a2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::GetImpl'::`2'::impl) )
  {
    LODWORD(v27) = 140;
    v28 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\ImageSearch\\ImageSearchEmbeddingsCreator.cpp";
    v24 = winrt::hresult::hresult((winrt::hresult *)&pv, -2147467259);
    winrt::throw_hresult(*(unsigned int *)v24, &v27);
  }
  pv = 0;
  v8 = winrt::Windows::Foundation::operator==(a1 + 56, &pv);
  if ( pv )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&pv);
  if ( v8 )
  {
    LODWORD(v27) = 145;
    v28 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\ImageSearch\\ImageSearchEmbeddingsCreator.cpp";
    v25 = winrt::hresult::hresult((winrt::hresult *)&pv, -2147483629);
    winrt::throw_hresult(*(unsigned int *)v25, &v27);
  }
  v9 = winrt::hstring::hstring((winrt::hstring *)v31, a3);
  CheckContainsNullChar(v9);
  pv = 0;
  tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>>>(&pv);
  v10 = TraceLogger::Provider();
  if ( *(_DWORD *)v10 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v10,
      (unsigned __int8 *)byte_180079381);
  v12 = *(unsigned int *)(a1 + 64);
  v36 = 0;
  v37 = 0;
  if ( v12 )
  {
    _mm_lfence();
    v13 = 4 * v12;
    *(_QWORD *)&v36 = std::_Allocate<16,std::_Default_allocate_traits>(v13);
    v14 = v13 + v36;
    v37 = v13 + v36;
    memset((void *)v36, 0, v13);
    *((_QWORD *)&v36 + 1) = v14;
  }
  v32 = a3;
  v33 = *a4;
  v34 = a1;
  v27 = (__int64 *)(a1 + 56);
  v29 = a1;
  v30 = (const char *)(a1 + 56);
  RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal_::_2_::_lambda_1___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchTextEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal_::_2_::_lambda_1____::_2_::_lambda_1___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchTextEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal_::_2_::_lambda_1____::_2_::_lambda_2___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchTextEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal_::_2_::_lambda_1____::_2_::_lambda_3___(
    (unsigned int)v31,
    (unsigned int)&v32,
    (unsigned int)&v29,
    v11,
    (__int64)&v27);
  v15 = (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 2;
  LODWORD(v29) = 159;
  v30 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Windows.SemanticSearch.h";
  v16 = 4;
  if ( (_DWORD)v15 )
    v16 = v36;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)v31[0] + 48LL))(v31[0], v15, v16);
  if ( v17 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v17, &v29);
  }
  v18 = TraceLogger::Provider();
  if ( *(_DWORD *)v18 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v18,
      (unsigned __int8 *)word_180079362);
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
  v20 = (__int128 *)winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::VectorSpaceId(
                      a1,
                      &v32);
  v27 = (__int64 *)operator new(0x40u);
  v29 = v36;
  LODWORD(v30) = (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 2;
  v35 = *v20;
  v21 = winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(
          v27,
          &v29,
          &v35);
  v22 = v21 + 16;
  if ( !v21 )
    v22 = 0;
  *a2 = v22;
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v31);
  std::vector<float>::_Tidy(&v36);
  if ( v19 )
    tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release((volatile signed __int32 *)v19);
  return a2;
}

```

## disassembly

```asm
0x18000afa0  mov     [rsp-8+arg_18], rbx
0x18000afa5  push    rbp
0x18000afa6  push    rsi
0x18000afa7  push    rdi
0x18000afa8  push    r12
0x18000afaa  push    r13
0x18000afac  push    r14
0x18000afae  push    r15
0x18000afb0  lea     rbp, [rsp-27h]
0x18000afb5  sub     rsp, 0C0h
0x18000afbc  mov     rax, cs:__security_cookie
0x18000afc3  xor     rax, rsp
0x18000afc6  mov     [rbp+57h+var_38], rax
0x18000afca  mov     r13, r9
0x18000afcd  mov     r12, r8
0x18000afd0  mov     r14, rdx
0x18000afd3  mov     r15, rcx
0x18000afd6  mov     [rbp+57h+var_B8], rdx
0x18000afda  xor     edi, edi
0x18000afdc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_TXTEMB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_TXTEMB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_TXTEMB> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::GetImpl(void)'::`2'::impl
0x18000afe3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_TXTEMB@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::__private_IsEnabled(void)
0x18000afe8  test    al, al
0x18000afea  jz      loc_18000B23A
0x18000aff0  mov     [rbp+57h+pv], rdi
0x18000aff4  lea     rsi, [r15+38h]
0x18000aff8  lea     rdx, [rbp+57h+pv]
0x18000affc  mov     rcx, rsi
0x18000afff  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000b004  movzx   ebx, al
0x18000b007  cmp     [rbp+57h+pv], rdi
0x18000b00b  jz      short loc_18000B016
0x18000b00d  lea     rcx, [rbp+57h+pv]
0x18000b011  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18000b016  test    bl, bl
0x18000b018  jnz     loc_18000B266
0x18000b01e  mov     rdx, r12; struct winrt::hstring *
0x18000b021  lea     rcx, [rbp+57h+var_90]; this
0x18000b025  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18000b02a  mov     rcx, rax
0x18000b02d  call    ?CheckContainsNullChar@@YAXUhstring@winrt@@@Z; CheckContainsNullChar(winrt::hstring)
0x18000b032  mov     [rbp+57h+pv], rdi
0x18000b036  lea     rcx, [rbp+57h+pv]
0x18000b03a  call    ??$start@V?$tip_test@V?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>>>(void)
0x18000b03f  nop
0x18000b040  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18000b045  cmp     dword ptr [rax], 5
0x18000b048  jbe     short loc_18000B059
0x18000b04a  lea     rdx, byte_180079381
0x18000b051  mov     rcx, rax
0x18000b054  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000b059  xorps   xmm0, xmm0
0x18000b05c  xor     eax, eax
0x18000b05e  mov     edi, [r15+40h]
0x18000b062  movdqu  [rbp+57h+var_50], xmm0
0x18000b067  mov     [rbp+57h+var_40], rax
0x18000b06b  test    rdi, rdi
0x18000b06e  jz      short loc_18000B0A0
0x18000b070  lfence
0x18000b073  lea     rdi, ds:0[rdi*4]
0x18000b07b  mov     rcx, rdi
0x18000b07e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000b083  mov     qword ptr [rbp+57h+var_50], rax
0x18000b087  lea     rbx, [rdi+rax]
0x18000b08b  mov     [rbp+57h+var_40], rbx
0x18000b08f  mov     r8, rdi; Size
0x18000b092  xor     edx, edx; Val
0x18000b094  mov     rcx, rax; void *
0x18000b097  call    memset
0x18000b09c  mov     qword ptr [rbp+57h+var_50+8], rbx
0x18000b0a0  mov     [rbp+57h+var_80], r12
0x18000b0a4  mov     eax, [r13+0]
0x18000b0a8  mov     [rbp+57h+var_78], eax
0x18000b0ab  mov     [rbp+57h+var_70], r15
0x18000b0af  mov     [rbp+57h+var_B8], rsi
0x18000b0b3  mov     qword ptr [rbp+57h+var_A0], r15
0x18000b0b7  mov     qword ptr [rbp+57h+var_A0+8], rsi
0x18000b0bb  lea     rax, [rbp+57h+var_B8]
0x18000b0bf  mov     [rsp+0F0h+var_D0], rax
0x18000b0c4  lea     r8, [rbp+57h+var_A0]
0x18000b0c8  lea     rdx, [rbp+57h+var_80]
0x18000b0cc  lea     rcx, [rbp+57h+var_90]
0x18000b0d0  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForTextInternal____2____lambda_1___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchTextEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForTextInternal____2____lambda_1_______2____lambda_1___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchTextEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForTextInternal____2____lambda_1_______2____lambda_2___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchTextEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForTextInternal____2____lambda_1_______2____lambda_3___
0x18000b0d5  nop
0x18000b0d6  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18000b0da  sub     rdx, qword ptr [rbp+57h+var_50]
0x18000b0de  sar     rdx, 2
0x18000b0e2  mov     dword ptr [rbp+57h+var_A0], 9Fh
0x18000b0e9  lea     rax, aCW1SProductApi_25; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000b0f0  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18000b0f4  mov     rcx, [rbp+57h+var_90]
0x18000b0f8  mov     rax, [rcx]
0x18000b0fb  mov     r8d, 4
0x18000b101  test    edx, edx
0x18000b103  cmovnz  r8, qword ptr [rbp+57h+var_50]
0x18000b108  mov     rax, [rax+30h]
0x18000b10c  call    cs:__guard_dispatch_icall_fptr
0x18000b112  test    eax, eax
0x18000b114  js      loc_18000B22B
0x18000b11a  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18000b11f  cmp     dword ptr [rax], 5
0x18000b122  jbe     short loc_18000B133
0x18000b124  lea     rdx, word_180079362
0x18000b12b  mov     rcx, rax
0x18000b12e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000b133  mov     rbx, [rbp+57h+pv]
0x18000b137  test    rbx, rbx
0x18000b13a  jz      short loc_18000B179
0x18000b13c  lea     rsi, [rbx+0C8h]
0x18000b143  mov     rcx, rsi; lpCriticalSection
0x18000b146  call    cs:__imp_EnterCriticalSection
0x18000b14c  or      dword ptr [rbx+48h], 300h
0x18000b153  cmp     qword ptr [rbx+0F0h], 0
0x18000b15b  jz      short loc_18000B16B
0x18000b15d  mov     edx, 2
0x18000b162  lea     rcx, [rbx+8]
0x18000b166  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000b16b  test    rsi, rsi
0x18000b16e  jz      short loc_18000B179
0x18000b170  mov     rcx, rsi; lpCriticalSection
0x18000b173  call    cs:__imp_LeaveCriticalSection
0x18000b179  lea     rdx, [rbp+57h+var_80]
0x18000b17d  mov     rcx, r15
0x18000b180  call    ?VectorSpaceId@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUguid@6@XZ; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::VectorSpaceId(void)
0x18000b185  mov     rdi, rax
0x18000b188  mov     ecx, 40h ; '@'; Size
0x18000b18d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b192  mov     [rbp+57h+var_B8], rax
0x18000b196  mov     rcx, qword ptr [rbp+57h+var_50]
0x18000b19a  mov     qword ptr [rbp+57h+var_A0], rcx
0x18000b19e  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18000b1a2  sub     rdx, rcx
0x18000b1a5  sar     rdx, 2
0x18000b1a9  mov     dword ptr [rbp+57h+var_A0+8], edx
0x18000b1ac  movups  xmm0, xmmword ptr [rdi]
0x18000b1af  movaps  [rbp+57h+var_60], xmm0
0x18000b1b3  movaps  xmm1, [rbp+57h+var_A0]
0x18000b1b7  movdqa  [rbp+57h+var_A0], xmm1
0x18000b1bc  lea     r8, [rbp+57h+var_60]
0x18000b1c0  lea     rdx, [rbp+57h+var_A0]
0x18000b1c4  mov     rcx, rax
0x18000b1c7  call    ??0?$heap_implements@UEmbeddingVector@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEAA@U?$array_view@$$CBM@2@Uguid@2@@Z; winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(winrt::array_view<float const>,winrt::guid)
0x18000b1cc  nop
0x18000b1cd  lea     rcx, [rax+10h]
0x18000b1d1  test    rax, rax
0x18000b1d4  mov     eax, 0
0x18000b1d9  cmovz   rcx, rax
0x18000b1dd  mov     [r14], rcx
0x18000b1e0  lea     rcx, [rbp+57h+var_90]
0x18000b1e4  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18000b1e9  nop
0x18000b1ea  lea     rcx, [rbp+57h+var_50]
0x18000b1ee  call    ?_Tidy@?$vector@MV?$allocator@M@std@@@std@@AEAAXXZ; std::vector<float>::_Tidy(void)
0x18000b1f3  nop
0x18000b1f4  test    rbx, rbx
0x18000b1f7  jz      short loc_18000B201
0x18000b1f9  mov     rcx, rbx; pv
0x18000b1fc  call    ?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)
0x18000b201  mov     rax, r14
0x18000b204  mov     rcx, [rbp+57h+var_38]
0x18000b208  xor     rcx, rsp; StackCookie
0x18000b20b  call    __security_check_cookie
0x18000b210  mov     rbx, [rsp+0F0h+arg_18]
0x18000b218  add     rsp, 0C0h
0x18000b21f  pop     r15
0x18000b221  pop     r14
0x18000b223  pop     r13
0x18000b225  pop     r12
0x18000b227  pop     rdi
0x18000b228  pop     rsi
0x18000b229  pop     rbp
0x18000b22a  retn
0x18000b22b  lfence
0x18000b22e  lea     rdx, [rbp+57h+var_A0]
0x18000b232  mov     ecx, eax
0x18000b234  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000b23a  mov     dword ptr [rbp+57h+var_B8], 8Ch
0x18000b241  lea     rax, aCW1SProductApi_8; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000b248  mov     [rbp+57h+var_B0], rax
0x18000b24c  mov     edx, 80004005h; int
0x18000b251  lea     rcx, [rbp+57h+pv]; this
0x18000b255  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000b25a  lea     rdx, [rbp+57h+var_B8]
0x18000b25e  mov     ecx, [rax]
0x18000b260  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000b266  mov     dword ptr [rbp+57h+var_B8], 91h
0x18000b26d  lea     rax, aCW1SProductApi_8; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000b274  mov     [rbp+57h+var_B0], rax
0x18000b278  mov     edx, 80000013h; int
0x18000b27d  lea     rcx, [rbp+57h+pv]; this
0x18000b281  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000b286  lea     rdx, [rbp+57h+var_B8]
0x18000b28a  mov     ecx, [rax]
0x18000b28c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
