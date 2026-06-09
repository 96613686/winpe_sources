# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensAsync$_ResumeCoro$1_0

- ea: `0x180059980`
- end: `0x180059de0`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensAsync$_ResumeCoro$1_0`
- size: `1120`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180035980`
- `0x180059510`

## callees

- `0x180002bb0`
- `0x180008840`
- `0x180009fa0`
- `0x18000d050`
- `0x180010000`
- `0x180010230`
- `0x180014100`
- `0x180014540`
- `0x180014840`
- `0x180015090`
- `0x1800151a0`
- `0x180034400`
- `0x1800369a0`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x180051379`
- `0x18005137f`
- `0x180059980`
- `0x18005e260`
- `0x18005e770`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059ac2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059b2d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059ac2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059b2d`

## string_xrefs

- `0x180059a72`: `CreateVectorFromTokensAsync`
- `0x180059af9`: `CreateVectorFromTokensAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensAsync__ResumeCoro_1_0(
        char *a1)
{
  _WORD *v2; // r14
  unsigned __int64 v3; // rcx
  __int64 v4; // rax
  const wchar_t *v5; // rbx
  TelemetryLogger *v6; // rax
  volatile signed __int32 *v7; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v9; // rax
  const wchar_t *v10; // rbx
  __int64 v11; // rdx
  signed __int64 v12; // rax
  signed __int64 v13; // rtt
  const void *v14; // r15
  size_t v15; // rax
  size_t v16; // rsi
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  char *VectorFromTokensInternal; // r15
  _QWORD *v20; // rsi
  __int64 v21; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-88h] BYREF
  __int128 v23; // [rsp+58h] [rbp-70h]
  __int64 v24; // [rsp+68h] [rbp-60h]
  __int64 v25; // [rsp+70h] [rbp-58h]
  __int64 v26; // [rsp+78h] [rbp-50h]

  v2 = a1 + 168;
  switch ( *((_WORD *)a1 + 84) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_44;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&dword_180086A14) == 1 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(
                 *((_QWORD *)a1 + 17),
                 a1 + 176);
          if ( *(_QWORD *)v4 )
            v5 = *(const wchar_t **)(*(_QWORD *)v4 + 16LL);
          else
            v5 = (const wchar_t *)&qword_18006D0D8;
          v3 = *((_QWORD *)TelemetryLogger::Instance() + 1);
          if ( v3 && *(_DWORD *)v3 )
          {
            v6 = TelemetryLogger::Instance();
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorFromTokensAsync", &dword_180086A14);
          }
          v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 22);
          if ( v7 )
          {
            v3 = (unsigned int)_InterlockedDecrement(v7 + 6);
            if ( !(_DWORD)v3 )
            {
LABEL_12:
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v7);
              goto LABEL_22;
            }
            if ( (v3 & 0x80000000) != 0LL )
              abort();
          }
        }
      }
      else
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(*((_QWORD *)a1 + 17), a1 + 184);
        if ( *(_QWORD *)v9 )
          v10 = *(const wchar_t **)(*(_QWORD *)v9 + 16LL);
        else
          v10 = (const wchar_t *)&qword_18006D0D8;
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorFromTokensAsync");
        v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 23);
        if ( v7 )
        {
          v3 = (unsigned int)_InterlockedDecrement(v7 + 6);
          if ( !(_DWORD)v3 )
            goto LABEL_12;
          if ( (v3 & 0x80000000) != 0LL )
            abort();
        }
      }
LABEL_22:
      v11 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 38) = v11;
      *((_QWORD *)a1 + 24) = 0;
      if ( v11 )
      {
        *((_QWORD *)a1 + 24) = v11;
        v12 = *(_QWORD *)(v11 + 8);
        if ( v12 < 0 )
        {
LABEL_26:
          _InterlockedIncrement((volatile signed __int32 *)(2 * v12 + 24));
        }
        else
        {
          while ( 1 )
          {
            v3 = v12 + 1;
            v13 = v12;
            v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(v11 + 8), v12 + 1, v12);
            if ( v13 == v12 )
              break;
            if ( v12 < 0 )
              goto LABEL_26;
          }
        }
      }
      *((_QWORD *)a1 + 26) = 0;
      *((_QWORD *)a1 + 27) = 0;
      v14 = (const void *)*((_QWORD *)a1 + 18);
      v15 = *((unsigned int *)a1 + 38);
      v16 = v15;
      *((_QWORD *)a1 + 25) = 0;
      *((_QWORD *)a1 + 26) = 0;
      *((_QWORD *)a1 + 27) = 0;
      if ( v15 )
      {
        v17 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v15);
        *((_QWORD *)a1 + 25) = v17;
        *((_QWORD *)a1 + 26) = v17;
        v18 = &v17[v16];
        *((_QWORD *)a1 + 27) = &v17[v16];
        memmove(v17, v14, v16 * 8);
        *((_QWORD *)a1 + 26) = v18;
      }
      a1[224] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 72) = 3980;
        *((_QWORD *)a1 + 37) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 288));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      *((_QWORD *)a1 + 29) = *((_QWORD *)a1 + 25);
      v26 = *((_QWORD *)a1 + 26);
      v25 = *((_QWORD *)a1 + 25);
      *((_DWORD *)a1 + 60) = (v26 - v25) >> 3;
      v23 = *(_OWORD *)(a1 + 232);
      *((_OWORD *)a1 + 17) = v23;
      VectorFromTokensInternal = (char *)winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(
                                           *((_QWORD *)a1 + 38),
                                           a1 + 248);
      v20 = a1 + 120;
      if ( a1 + 120 != VectorFromTokensInternal )
      {
        if ( *v20 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v21 = *(_QWORD *)VectorFromTokensInternal;
        *(_QWORD *)VectorFromTokensInternal = 0;
        *v20 = v21;
      }
      if ( *((_QWORD *)a1 + 31) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 248);
      std::vector<__int64>::_Tidy(a1 + 200);
      v24 = *((_QWORD *)a1 + 24);
      if ( v24 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 32) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 32) )
        goto LABEL_44;
      return;
    case 5:
      std::vector<__int64>::_Tidy(a1 + 200);
      v24 = *((_QWORD *)a1 + 24);
      if ( v24 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
LABEL_44:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_WORD *)a1 + 85) )
        operator delete(a1);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180059980  mov     r11, rsp
0x180059983  mov     [r11+10h], rbx
0x180059987  mov     [r11+18h], rsi
0x18005998b  mov     [r11+8], rcx
0x18005998f  push    rdi
0x180059990  push    r12
0x180059992  push    r13
0x180059994  push    r14
0x180059996  push    r15
0x180059998  sub     rsp, 0A0h
0x18005999f  mov     rax, cs:__security_cookie
0x1800599a6  xor     rax, rsp
0x1800599a9  mov     [rsp+0C8h+var_30], rax
0x1800599b1  mov     rdi, rcx
0x1800599b4  mov     [rsp+0C8h+var_A0], rcx
0x1800599b9  lea     r14, [rdi+0A8h]
0x1800599c0  mov     [rsp+0C8h+var_90], r14
0x1800599c5  movzx   eax, word ptr [r14]
0x1800599c9  mov     [rsp+0C8h+var_A8], ax
0x1800599ce  inc     ax; switch 7 cases
0x1800599d1  cmp     ax, 6
0x1800599d5  ja      def_1800599F0; jumptable 00000001800599F0 default case, case 0
0x1800599db  movsx   rax, ax
0x1800599df  lea     rdx, cs:180000000h
0x1800599e6  mov     ecx, ds:(jpt_1800599F0 - 180000000h)[rdx+rax*4]
0x1800599ed  add     rcx, rdx
0x1800599f0  jmp     rcx; switch jump
0x1800599f2  jmp     loc_180059D70; jumptable 00000001800599F0 case 3
0x1800599f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 00000001800599F0 case 2
0x1800599fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180059a03  test    al, al
0x180059a05  jz      loc_180059AC9
0x180059a0b  mov     eax, 1
0x180059a10  lock xadd cs:dword_180086A14, eax
0x180059a18  inc     eax
0x180059a1a  cmp     eax, 1
0x180059a1d  jnz     loc_180059B34
0x180059a23  mov     rcx, [rdi+88h]
0x180059a2a  mov     rax, [rcx]
0x180059a2d  lea     rdx, [rdi+0B0h]
0x180059a34  mov     rax, [rax+28h]
0x180059a38  call    cs:__guard_dispatch_icall_fptr
0x180059a3e  mov     rbx, [rax]
0x180059a41  test    rbx, rbx
0x180059a44  jz      short loc_180059A4C
0x180059a46  mov     rbx, [rbx+10h]
0x180059a4a  jmp     short loc_180059A53
0x180059a4c  lea     rbx, qword_18006D0D8
0x180059a53  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180059a58  mov     rcx, [rax+8]
0x180059a5c  test    rcx, rcx
0x180059a5f  jz      short loc_180059A85
0x180059a61  cmp     dword ptr [rcx], 0
0x180059a64  jbe     short loc_180059A85
0x180059a66  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180059a6b  lea     r9, dword_180086A14; volatile int *
0x180059a72  lea     r8, aCreatevectorfr; "CreateVectorFromTokensAsync"
0x180059a79  mov     rdx, rbx; wchar_t *
0x180059a7c  mov     rcx, rax; this
0x180059a7f  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180059a84  nop
0x180059a85  mov     rbx, [rdi+0B0h]
0x180059a8c  cmp     rbx, 0
0x180059a90  jz      loc_180059B34
0x180059a96  mov     [rsp+0C8h+var_98], rbx
0x180059a9b  mov     ecx, 0FFFFFFFFh
0x180059aa0  lock xadd [rbx+18h], ecx
0x180059aa5  sub     ecx, 1
0x180059aa8  jnz     short loc_180059ABE
0x180059aaa  call    WINRT_IMPL_GetProcessHeap
0x180059aaf  mov     rcx, rax; hHeap
0x180059ab2  mov     r8, rbx; lpMem
0x180059ab5  xor     edx, edx; dwFlags
0x180059ab7  call    WINRT_IMPL_HeapFree
0x180059abc  jmp     short loc_180059B34
0x180059abe  test    ecx, ecx
0x180059ac0  jns     short loc_180059B34
0x180059ac2  call    cs:__imp_abort
0x180059ac9  mov     rcx, [rdi+88h]
0x180059ad0  mov     rax, [rcx]
0x180059ad3  lea     rdx, [rdi+0B8h]
0x180059ada  mov     rax, [rax+28h]
0x180059ade  call    cs:__guard_dispatch_icall_fptr
0x180059ae4  mov     rbx, [rax]
0x180059ae7  test    rbx, rbx
0x180059aea  jz      short loc_180059AF2
0x180059aec  mov     rbx, [rbx+10h]
0x180059af0  jmp     short loc_180059AF9
0x180059af2  lea     rbx, qword_18006D0D8
0x180059af9  lea     rdx, aCreatevectorfr; "CreateVectorFromTokensAsync"
0x180059b00  mov     rcx, rbx; wchar_t *
0x180059b03  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180059b08  mov     rbx, [rdi+0B8h]
0x180059b0f  cmp     rbx, 0
0x180059b13  jz      short loc_180059B34
0x180059b15  mov     [rsp+0C8h+var_98], rbx
0x180059b1a  mov     ecx, 0FFFFFFFFh
0x180059b1f  lock xadd [rbx+18h], ecx
0x180059b24  sub     ecx, 1
0x180059b27  jz      short loc_180059AAA
0x180059b29  test    ecx, ecx
0x180059b2b  jns     short loc_180059B34
0x180059b2d  call    cs:__imp_abort
0x180059b34  mov     rdx, [rdi+88h]
0x180059b3b  mov     [rdi+130h], rdx
0x180059b42  xor     ebx, ebx
0x180059b44  mov     [rdi+0C0h], rbx
0x180059b4b  test    rdx, rdx
0x180059b4e  jz      short loc_180059B76
0x180059b50  mov     [rdi+0C0h], rdx
0x180059b57  mov     rax, [rdx+8]
0x180059b5b  test    rax, rax
0x180059b5e  js      short loc_180059B71
0x180059b60  lea     rcx, [rax+1]
0x180059b64  lock cmpxchg [rdx+8], rcx
0x180059b6a  jz      short loc_180059B76
0x180059b6c  test    rax, rax
0x180059b6f  jns     short loc_180059B60
0x180059b71  lock inc dword ptr [rax+rax+18h]
0x180059b76  mov     [rdi+0D0h], rbx
0x180059b7d  mov     [rdi+0D8h], rbx
0x180059b84  mov     r15, [rdi+90h]
0x180059b8b  mov     eax, [rdi+98h]
0x180059b91  lea     rsi, ds:0[rax*8]
0x180059b99  mov     [rdi+0C8h], rbx
0x180059ba0  mov     [rdi+0D0h], rbx
0x180059ba7  mov     [rdi+0D8h], rbx
0x180059bae  test    rax, rax
0x180059bb1  jz      short loc_180059BE9
0x180059bb3  mov     rcx, rsi
0x180059bb6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180059bbb  mov     [rdi+0C8h], rax
0x180059bc2  mov     [rdi+0D0h], rax
0x180059bc9  lea     rbx, [rsi+rax]
0x180059bcd  mov     [rdi+0D8h], rbx
0x180059bd4  mov     r8, rsi; Size
0x180059bd7  mov     rdx, r15; Src
0x180059bda  mov     rcx, rax; void *
0x180059bdd  call    memmove
0x180059be2  mov     [rdi+0D0h], rbx
0x180059be9  mov     byte ptr [rdi+0E0h], 0
0x180059bf0  mov     eax, [rdi+70h]
0x180059bf3  cmp     eax, 2
0x180059bf6  jnz     short loc_180059C2E
0x180059bf8  lea     rdx, [rdi+120h]; struct winrt::impl::slim_source_location *
0x180059bff  mov     dword ptr [rdx], 0F8Ch
0x180059c05  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180059c0c  mov     [rdi+128h], rax
0x180059c13  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x180059c18  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180059c1d  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180059c24  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180059c29  call    _CxxThrowException
0x180059c2e  mov     eax, 4
0x180059c33  mov     [r14], ax
0x180059c37  mov     rdx, rdi
0x180059c3a  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180059c3f  jmp     loc_180059D93
0x180059c44  lea     rcx, [rdi+0C8h]; jumptable 00000001800599F0 case 5
0x180059c4b  call    ?_Tidy@?$vector@_JV?$allocator@_J@std@@@std@@AEAAXXZ; std::vector<__int64>::_Tidy(void)
0x180059c50  nop
0x180059c51  lea     rcx, [rdi+0C0h]
0x180059c58  mov     rax, [rcx]
0x180059c5b  mov     [rsp+0C8h+var_60], rax
0x180059c60  test    rax, rax
0x180059c63  jz      short loc_180059C6B
0x180059c65  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180059c6a  nop
0x180059c6b  jmp     loc_180059D70; jumptable 00000001800599F0 cases -1,1
0x180059c70  mov     rax, [rdi+0C8h]; jumptable 00000001800599F0 case 4
0x180059c77  mov     [rdi+0E8h], rax
0x180059c7e  mov     rcx, [rdi+0D0h]
0x180059c85  mov     [rsp+0C8h+var_50], rcx
0x180059c8a  mov     rax, [rdi+0C8h]
0x180059c91  mov     [rsp+0C8h+var_58], rax
0x180059c96  sub     rcx, rax
0x180059c99  sar     rcx, 3
0x180059c9d  mov     [rdi+0F0h], ecx
0x180059ca3  lea     r8, [rdi+110h]
0x180059caa  movups  xmm0, xmmword ptr [rdi+0E8h]
0x180059cb1  movups  [rsp+0C8h+var_70], xmm0
0x180059cb6  movaps  xmmword ptr [r8], xmm0
0x180059cba  lea     r9, [rdi+0A0h]
0x180059cc1  lea     rdx, [rdi+0F8h]
0x180059cc8  mov     rcx, [rdi+130h]
0x180059ccf  call    ?CreateVectorFromTokensInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180059cd4  mov     r15, rax
0x180059cd7  lea     rsi, [rdi+78h]
0x180059cdb  cmp     rsi, rax
0x180059cde  jz      short loc_180059CFB
0x180059ce0  cmp     qword ptr [rsi], 0
0x180059ce4  jz      short loc_180059CEE
0x180059ce6  mov     rcx, rsi
0x180059ce9  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180059cee  mov     rax, [r15]
0x180059cf1  xor     ebx, ebx
0x180059cf3  mov     [r15], rbx
0x180059cf6  mov     [rsi], rax
0x180059cf9  jmp     short loc_180059CFD
0x180059cfb  xor     ebx, ebx
0x180059cfd  mov     rax, [rdi+0F8h]
0x180059d04  mov     [rsp+0C8h+var_98], rax
0x180059d09  test    rax, rax
0x180059d0c  jz      short loc_180059D1B
0x180059d0e  lea     rcx, [rdi+0F8h]
0x180059d15  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180059d1a  nop
0x180059d1b  lea     rcx, [rdi+0C8h]
0x180059d22  call    ?_Tidy@?$vector@_JV?$allocator@_J@std@@@std@@AEAAXXZ; std::vector<__int64>::_Tidy(void)
0x180059d27  nop
0x180059d28  lea     rcx, [rdi+0C0h]
0x180059d2f  mov     rax, [rcx]
0x180059d32  mov     [rsp+0C8h+var_60], rax
0x180059d37  test    rax, rax
0x180059d3a  jz      short loc_180059D42
0x180059d3c  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180059d41  nop
0x180059d42  jmp     short loc_180059D50
0x180059d44  xor     ebx, ebx
0x180059d46  mov     r14, [rsp+0C8h+var_90]
0x180059d4b  mov     rdi, [rsp+0C8h+var_A0]
0x180059d50  lea     rax, [rdi+10h]
0x180059d54  lea     rcx, [rdi+100h]
0x180059d5b  mov     [rcx], rax
0x180059d5e  xor     eax, eax
0x180059d60  mov     [r14], ax
0x180059d64  mov     [rdi], rbx
0x180059d67  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180059d6c  test    al, al
0x180059d6e  jnz     short loc_180059D93
0x180059d70  lea     rcx, [rdi+10h]; jumptable 00000001800599F0 cases -1,1
0x180059d74  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x180059d79  cmp     word ptr [rdi+0AAh], 0
0x180059d81  jz      short loc_180059D93
0x180059d83  mov     edx, 140h; unsigned __int64
0x180059d88  mov     rcx, rdi; void *
0x180059d8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180059d90  jmp     short loc_180059D93
0x180059d92  int     3; Trap to Debugger
0x180059d93  mov     rcx, [rsp+0C8h+var_30]
0x180059d9b  xor     rcx, rsp; StackCookie
0x180059d9e  call    __security_check_cookie
0x180059da3  lea     r11, [rsp+0C8h+var_28]
0x180059dab  mov     rbx, [r11+38h]
0x180059daf  mov     rsi, [r11+40h]
0x180059db3  mov     rsp, r11
0x180059db6  pop     r15
0x180059db8  pop     r14
0x180059dba  pop     r13
0x180059dbc  pop     r12
0x180059dbe  pop     rdi
0x180059dbf  retn
```
