# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(winrt::Microsoft::Windows::Imaging::ImageBuffer const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x18000a710`
- end: `0x18000aab6`
- name: `?CreateVectorForImageInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUImageBuffer@Imaging@456@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `934`
- prototype: ``
- caller_count: `4`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a0d0`
- `0x18000a5b0`
- `0x180051d80`
- `0x180052120`

## callees

- `0x1800018b0`
- `0x180001f40`
- `0x180002bb0`
- `0x180008840`
- `0x180009580`
- `0x18000a710`
- `0x18000b6b0`
- `0x18000ed90`
- `0x18000f160`
- `0x18000fba0`
- `0x18000fc60`
- `0x180010050`
- `0x180010590`
- `0x180010910`
- `0x180011960`
- `0x180015450`
- `0x180015a70`
- `0x1800161b0`
- `0x18004c070`
- `0x18004c8cc`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a9d9`
- `KERNEL32!LeaveCriticalSection` at `0x18000a9d9`
- `KERNEL32!EnterCriticalSection` at `0x18000a9ac`
- `KERNEL32!EnterCriticalSection` at `0x18000a9ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a7b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a7b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  const struct _tlgProvider_t *v6; // rax
  char v7; // bl
  struct _RTL_CRITICAL_SECTION *v8; // rax
  wil::details::in1diag3 *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  int v11; // r9d
  __int64 v12; // rdi
  size_t v13; // rdi
  size_t v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  __int128 *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rax
  const struct _tlgProvider_t *v21; // rax
  winrt::hresult *v23; // rax
  winrt::hresult *v24; // rax
  _QWORD v25[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h]
  _QWORD v28[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+60h] [rbp-A0h] BYREF
  const char *v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[24]; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int128 v34; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v35[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v36; // [rsp+F0h] [rbp-10h] BYREF
  size_t v37; // [rsp+100h] [rbp+0h]

  v28[0] = a4;
  v26 = a3;
  v25[0] = a2;
  v6 = TraceLogger::Provider();
  if ( *(_DWORD *)v6 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v6,
      (unsigned __int8 *)qword_1800793C0);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_IMGEMB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_IMGEMB>::GetImpl'::`2'::impl) )
  {
    LODWORD(v29) = 85;
    v30 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\ImageSearch\\ImageSearchEmbeddingsCreator.cpp";
    v23 = winrt::hresult::hresult((winrt::hresult *)v25, -2147467259);
    winrt::throw_hresult(*(unsigned int *)v23, &v29);
  }
  v25[0] = 0;
  v7 = winrt::Windows::Foundation::operator==(a1 + 48, v25);
  if ( v25[0] )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v25);
  if ( v7 )
  {
    LODWORD(v29) = 90;
    v30 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\ImageSearch\\ImageSearchEmbeddingsCreator.cpp";
    v24 = winrt::hresult::hresult((winrt::hresult *)v25, -2147483629);
    winrt::throw_hresult(*(unsigned int *)v24, &v29);
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)CoTaskMemAlloc(0x110u);
  v10 = v8;
  if ( !v8 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v9);
  v8->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::test_data_interface::`vftable';
  *(_QWORD *)&v31 = 0xC10002A85422LL;
  *((_QWORD *)&v31 + 1) = "ImageEmbeddingsTest";
  *(_WORD *)v32 = 1;
  *(_OWORD *)&v32[8] = 0;
  v33 = 0;
  v35[0] = v31;
  v35[1] = *(_OWORD *)v32;
  v35[2] = 0u;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(&v8->LockCount, v8, v35);
  v10->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable';
  LODWORD(v10[6].LockSemaphore) = 1;
  v10[6].OwningThread = &v10->OwningThread;
  v29 = v10;
  tip2::details::shared_data<0,0,0>::start((__int64)&v10->LockCount, &v34);
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
  *(_QWORD *)&v31 = v26;
  DWORD2(v31) = *(_DWORD *)v28[0];
  *(_QWORD *)v32 = a1;
  v28[0] = a1 + 48;
  v26 = a1;
  v27 = a1 + 48;
  RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal_::_2_::_lambda_1___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchImageEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal_::_2_::_lambda_1____::_2_::_lambda_1___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchImageEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal_::_2_::_lambda_1____::_2_::_lambda_2___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchImageEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal_::_2_::_lambda_1____::_2_::_lambda_3___(
    (unsigned int)v25,
    (unsigned int)&v31,
    (unsigned int)&v26,
    v11,
    (__int64)v28);
  v15 = (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 2;
  LODWORD(v28[0]) = 159;
  v28[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
           "Microsoft.Windows.SemanticSearch.h";
  v16 = 4;
  if ( (_DWORD)v15 )
    v16 = v36;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)v25[0] + 48LL))(v25[0], v15, v16);
  if ( v17 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v17, v28);
  }
  v18 = (__int128 *)winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::VectorSpaceId(
                      a1,
                      &v31);
  v28[0] = operator new(0x40u);
  v26 = v36;
  LODWORD(v27) = (__int64)(*((_QWORD *)&v36 + 1) - v36) >> 2;
  v34 = *v18;
  v19 = winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(
          v28[0],
          &v26,
          &v34);
  v20 = v19 + 16;
  if ( !v19 )
    v20 = 0;
  *a2 = v20;
  EnterCriticalSection(v10 + 5);
  LODWORD(v10[1].SpinCount) |= 0x300u;
  if ( v10[6].DebugInfo )
    tip2::details::shared_data<0,0,0>::complete_helper((__int64)&v10->LockCount, 2u);
  if ( v10 != (struct _RTL_CRITICAL_SECTION *)-200LL )
    LeaveCriticalSection(v10 + 5);
  v21 = TraceLogger::Provider();
  if ( *(_DWORD *)v21 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v21,
      (unsigned __int8 *)byte_1800793A1);
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v25);
  std::vector<float>::_Tidy(&v36);
  tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(v10);
  return a2;
}

```

## disassembly

```asm
0x18000a710  mov     [rsp-8+arg_10], rbx
0x18000a715  push    rbp
0x18000a716  push    rsi
0x18000a717  push    rdi
0x18000a718  push    r12
0x18000a71a  push    r13
0x18000a71c  push    r14
0x18000a71e  push    r15
0x18000a720  lea     rbp, [rsp-10h]
0x18000a725  sub     rsp, 110h
0x18000a72c  mov     rax, cs:__security_cookie
0x18000a733  xor     rax, rsp
0x18000a736  mov     [rbp+40h+var_38], rax
0x18000a73a  mov     [rsp+140h+var_F0], r9
0x18000a73f  mov     qword ptr [rsp+140h+var_100], r8
0x18000a744  mov     r14, rdx
0x18000a747  mov     r13, rcx
0x18000a74a  mov     [rsp+140h+var_110], rdx
0x18000a74f  xor     edi, edi
0x18000a751  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18000a756  cmp     dword ptr [rax], 5
0x18000a759  jbe     short loc_18000A76A
0x18000a75b  lea     rdx, qword_1800793C0
0x18000a762  mov     rcx, rax
0x18000a765  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000a76a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_IMGEMB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_IMGEMB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_IMGEMB> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_IMGEMB>::GetImpl(void)'::`2'::impl
0x18000a771  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_IMGEMB@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_IMGEMB>::__private_IsEnabled(void)
0x18000a776  test    al, al
0x18000a778  jz      loc_18000AA50
0x18000a77e  mov     [rsp+140h+var_110], rdi
0x18000a783  lea     r12, [r13+30h]
0x18000a787  lea     rdx, [rsp+140h+var_110]
0x18000a78c  mov     rcx, r12
0x18000a78f  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000a794  movzx   ebx, al
0x18000a797  cmp     [rsp+140h+var_110], rdi
0x18000a79c  jz      short loc_18000A7A8
0x18000a79e  lea     rcx, [rsp+140h+var_110]
0x18000a7a3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18000a7a8  test    bl, bl
0x18000a7aa  jnz     loc_18000AA80
0x18000a7b0  mov     ecx, 110h; cb
0x18000a7b5  call    cs:__imp_CoTaskMemAlloc
0x18000a7bb  mov     rsi, rax
0x18000a7be  test    rax, rax
0x18000a7c1  jz      loc_18000AAB0
0x18000a7c7  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000a7ce  mov     [rsi], rax
0x18000a7d1  mov     dword ptr [rsp+140h+var_D0], 2A85422h
0x18000a7d9  mov     dword ptr [rsp+140h+var_D0+4], 0C100h
0x18000a7e1  lea     rax, aImageembedding; "ImageEmbeddingsTest"
0x18000a7e8  mov     qword ptr [rsp+140h+var_D0+8], rax
0x18000a7ed  mov     word ptr [rbp+40h+var_C0], 1
0x18000a7f3  xorps   xmm0, xmm0
0x18000a7f6  movdqu  xmmword ptr [rbp+40h+var_C0+8], xmm0
0x18000a7fb  mov     [rbp+40h+var_A8], rdi
0x18000a7ff  movups  xmm0, [rsp+140h+var_D0]
0x18000a804  movups  [rbp+40h+var_80], xmm0
0x18000a808  movups  xmm1, xmmword ptr [rbp+40h+var_C0]
0x18000a80c  movups  [rbp+40h+var_70], xmm1
0x18000a810  movups  xmm0, xmmword ptr [rbp-70h]
0x18000a814  movups  [rbp+40h+var_60], xmm0
0x18000a818  lea     r8, [rbp+40h+var_80]
0x18000a81c  mov     rdx, rsi
0x18000a81f  lea     rcx, [rsi+8]
0x18000a823  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18000a828  lea     rax, ??_7?$merged_data@U_tip_ImageEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable'
0x18000a82f  mov     [rsi], rax
0x18000a832  mov     dword ptr [rsi+108h], 1
0x18000a83c  lea     rax, [rsi+10h]
0x18000a840  mov     [rsi+100h], rax
0x18000a847  mov     [rsp+140h+var_E0], rsi
0x18000a84c  lea     rdx, [rbp+40h+var_90]
0x18000a850  lea     rcx, [rsi+8]
0x18000a854  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000a859  nop
0x18000a85a  xorps   xmm0, xmm0
0x18000a85d  xor     eax, eax
0x18000a85f  mov     edi, [r13+40h]
0x18000a863  movdqu  [rbp+40h+var_50], xmm0
0x18000a868  mov     [rbp+40h+var_40], rax
0x18000a86c  test    rdi, rdi
0x18000a86f  jz      short loc_18000A8A1
0x18000a871  lfence
0x18000a874  lea     rdi, ds:0[rdi*4]
0x18000a87c  mov     rcx, rdi
0x18000a87f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a884  mov     qword ptr [rbp+40h+var_50], rax
0x18000a888  lea     rbx, [rdi+rax]
0x18000a88c  mov     [rbp+40h+var_40], rbx
0x18000a890  mov     r8, rdi; Size
0x18000a893  xor     edx, edx; Val
0x18000a895  mov     rcx, rax; void *
0x18000a898  call    memset
0x18000a89d  mov     qword ptr [rbp+40h+var_50+8], rbx
0x18000a8a1  mov     rax, qword ptr [rsp+140h+var_100]
0x18000a8a6  mov     qword ptr [rsp+140h+var_D0], rax
0x18000a8ab  mov     rax, [rsp+140h+var_F0]
0x18000a8b0  mov     eax, [rax]
0x18000a8b2  mov     dword ptr [rsp+140h+var_D0+8], eax
0x18000a8b6  mov     qword ptr [rbp+40h+var_C0], r13
0x18000a8ba  mov     [rsp+140h+var_F0], r12
0x18000a8bf  mov     qword ptr [rsp+140h+var_100], r13
0x18000a8c4  mov     qword ptr [rsp+140h+var_100+8], r12
0x18000a8c9  lea     rax, [rsp+140h+var_F0]
0x18000a8ce  mov     [rsp+140h+var_120], rax
0x18000a8d3  lea     r8, [rsp+140h+var_100]
0x18000a8d8  lea     rdx, [rsp+140h+var_D0]
0x18000a8dd  lea     rcx, [rsp+140h+var_110]
0x18000a8e2  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForImageInternal____2____lambda_1___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchImageEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForImageInternal____2____lambda_1_______2____lambda_1___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchImageEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForImageInternal____2____lambda_1_______2____lambda_2___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchImageEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorForImageInternal____2____lambda_1_______2____lambda_3___
0x18000a8e7  nop
0x18000a8e8  mov     rdx, qword ptr [rbp+40h+var_50+8]
0x18000a8ec  sub     rdx, qword ptr [rbp+40h+var_50]
0x18000a8f0  sar     rdx, 2
0x18000a8f4  mov     dword ptr [rsp+140h+var_F0], 9Fh
0x18000a8fc  lea     rax, aCW1SProductApi_25; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000a903  mov     [rsp+140h+var_E8], rax
0x18000a908  mov     rcx, [rsp+140h+var_110]
0x18000a90d  mov     rax, [rcx]
0x18000a910  mov     r8d, 4
0x18000a916  test    edx, edx
0x18000a918  cmovnz  r8, qword ptr [rbp+40h+var_50]
0x18000a91d  mov     rax, [rax+30h]
0x18000a921  call    cs:__guard_dispatch_icall_fptr
0x18000a927  test    eax, eax
0x18000a929  js      loc_18000AA40
0x18000a92f  lea     rdx, [rsp+140h+var_D0]
0x18000a934  mov     rcx, r13
0x18000a937  call    ?VectorSpaceId@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUguid@6@XZ; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::VectorSpaceId(void)
0x18000a93c  mov     rbx, rax
0x18000a93f  mov     ecx, 40h ; '@'; Size
0x18000a944  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a949  mov     r9, rax
0x18000a94c  mov     [rsp+140h+var_F0], rax
0x18000a951  mov     rax, qword ptr [rbp+40h+var_50]
0x18000a955  mov     qword ptr [rsp+140h+var_100], rax
0x18000a95a  mov     rcx, qword ptr [rbp+40h+var_50+8]
0x18000a95e  sub     rcx, rax
0x18000a961  sar     rcx, 2
0x18000a965  mov     dword ptr [rsp+140h+var_100+8], ecx
0x18000a969  movups  xmm0, xmmword ptr [rbx]
0x18000a96c  movaps  [rbp+40h+var_90], xmm0
0x18000a970  movaps  xmm1, [rsp+140h+var_100]
0x18000a975  movdqa  [rsp+140h+var_100], xmm1
0x18000a97b  lea     r8, [rbp+40h+var_90]
0x18000a97f  lea     rdx, [rsp+140h+var_100]
0x18000a984  mov     rcx, r9
0x18000a987  call    ??0?$heap_implements@UEmbeddingVector@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEAA@U?$array_view@$$CBM@2@Uguid@2@@Z; winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(winrt::array_view<float const>,winrt::guid)
0x18000a98c  mov     rdx, rax
0x18000a98f  add     rax, 10h
0x18000a993  test    rdx, rdx
0x18000a996  mov     ecx, 0
0x18000a99b  cmovz   rax, rcx
0x18000a99f  mov     [r14], rax
0x18000a9a2  lea     rbx, [rsi+0C8h]
0x18000a9a9  mov     rcx, rbx; lpCriticalSection
0x18000a9ac  call    cs:__imp_EnterCriticalSection
0x18000a9b2  or      dword ptr [rsi+48h], 300h
0x18000a9b9  cmp     qword ptr [rsi+0F0h], 0
0x18000a9c1  jz      short loc_18000A9D1
0x18000a9c3  mov     edx, 2
0x18000a9c8  lea     rcx, [rsi+8]
0x18000a9cc  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000a9d1  test    rbx, rbx
0x18000a9d4  jz      short loc_18000A9DF
0x18000a9d6  mov     rcx, rbx; lpCriticalSection
0x18000a9d9  call    cs:__imp_LeaveCriticalSection
0x18000a9df  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18000a9e4  cmp     dword ptr [rax], 5
0x18000a9e7  jbe     short loc_18000A9F9
0x18000a9e9  lea     rdx, byte_1800793A1
0x18000a9f0  mov     rcx, rax
0x18000a9f3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000a9f8  nop
0x18000a9f9  lea     rcx, [rsp+140h+var_110]
0x18000a9fe  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18000aa03  nop
0x18000aa04  lea     rcx, [rbp+40h+var_50]
0x18000aa08  call    ?_Tidy@?$vector@MV?$allocator@M@std@@@std@@AEAAXXZ; std::vector<float>::_Tidy(void)
0x18000aa0d  nop
0x18000aa0e  mov     rcx, rsi; pv
0x18000aa11  call    ?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)
0x18000aa16  mov     rax, r14
0x18000aa19  mov     rcx, [rbp+40h+var_38]
0x18000aa1d  xor     rcx, rsp; StackCookie
0x18000aa20  call    __security_check_cookie
0x18000aa25  mov     rbx, [rsp+140h+arg_10]
0x18000aa2d  add     rsp, 110h
0x18000aa34  pop     r15
0x18000aa36  pop     r14
0x18000aa38  pop     r13
0x18000aa3a  pop     r12
0x18000aa3c  pop     rdi
0x18000aa3d  pop     rsi
0x18000aa3e  pop     rbp
0x18000aa3f  retn
0x18000aa40  lfence
0x18000aa43  lea     rdx, [rsp+140h+var_F0]
0x18000aa48  mov     ecx, eax
0x18000aa4a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000aa50  mov     dword ptr [rsp+140h+var_E0], 55h ; 'U'
0x18000aa58  lea     rax, aCW1SProductApi_8; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000aa5f  mov     [rsp+140h+var_D8], rax
0x18000aa64  mov     edx, 80004005h; int
0x18000aa69  lea     rcx, [rsp+140h+var_110]; this
0x18000aa6e  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000aa73  lea     rdx, [rsp+140h+var_E0]
0x18000aa78  mov     ecx, [rax]
0x18000aa7a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000aa80  mov     dword ptr [rsp+140h+var_E0], 5Ah ; 'Z'
0x18000aa88  lea     rax, aCW1SProductApi_8; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000aa8f  mov     [rsp+140h+var_D8], rax
0x18000aa94  mov     edx, 80000013h; int
0x18000aa99  lea     rcx, [rsp+140h+var_110]; this
0x18000aa9e  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000aaa3  lea     rdx, [rsp+140h+var_E0]
0x18000aaa8  mov     ecx, [rax]
0x18000aaaa  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000aab0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
