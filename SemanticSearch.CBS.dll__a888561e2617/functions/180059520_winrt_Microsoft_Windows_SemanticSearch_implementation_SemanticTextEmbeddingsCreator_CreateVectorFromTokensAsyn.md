# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensAsync$_ResumeCoro$1

- ea: `0x180059520`
- end: `0x180059980`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensAsync$_ResumeCoro$1`
- size: `1120`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180035d10`
- `0x180059500`

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
- `0x180059520`
- `0x18005e260`
- `0x18005e770`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059662`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800596cd`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059662`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800596cd`

## string_xrefs

- `0x180059612`: `CreateVectorFromTokensAsync`
- `0x180059699`: `CreateVectorFromTokensAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensAsync__ResumeCoro_1(
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

  v2 = a1 + 160;
  switch ( *((_WORD *)a1 + 80) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_44;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&dword_180086A24) == 1 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(
                 *((_QWORD *)a1 + 17),
                 a1 + 168);
          if ( *(_QWORD *)v4 )
            v5 = *(const wchar_t **)(*(_QWORD *)v4 + 16LL);
          else
            v5 = (const wchar_t *)&qword_18006D0D8;
          v3 = *((_QWORD *)TelemetryLogger::Instance() + 1);
          if ( v3 && *(_DWORD *)v3 )
          {
            v6 = TelemetryLogger::Instance();
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorFromTokensAsync", &dword_180086A24);
          }
          v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 21);
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
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(*((_QWORD *)a1 + 17), a1 + 176);
        if ( *(_QWORD *)v9 )
          v10 = *(const wchar_t **)(*(_QWORD *)v9 + 16LL);
        else
          v10 = (const wchar_t *)&qword_18006D0D8;
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorFromTokensAsync");
        v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 22);
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
      *((_QWORD *)a1 + 36) = v11;
      *((_QWORD *)a1 + 23) = 0;
      if ( v11 )
      {
        *((_QWORD *)a1 + 23) = v11;
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
      *((_QWORD *)a1 + 25) = 0;
      *((_QWORD *)a1 + 26) = 0;
      v14 = (const void *)*((_QWORD *)a1 + 18);
      v15 = *((unsigned int *)a1 + 38);
      v16 = v15;
      *((_QWORD *)a1 + 24) = 0;
      *((_QWORD *)a1 + 25) = 0;
      *((_QWORD *)a1 + 26) = 0;
      if ( v15 )
      {
        v17 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v15);
        *((_QWORD *)a1 + 24) = v17;
        *((_QWORD *)a1 + 25) = v17;
        v18 = &v17[v16];
        *((_QWORD *)a1 + 26) = &v17[v16];
        memmove(v17, v14, v16 * 8);
        *((_QWORD *)a1 + 25) = v18;
      }
      a1[216] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 68) = 3980;
        *((_QWORD *)a1 + 35) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 272));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      *((_DWORD *)a1 + 55) = 0;
      *((_QWORD *)a1 + 28) = *((_QWORD *)a1 + 24);
      v26 = *((_QWORD *)a1 + 25);
      v25 = *((_QWORD *)a1 + 24);
      *((_DWORD *)a1 + 58) = (v26 - v25) >> 3;
      v23 = *((_OWORD *)a1 + 14);
      *((_OWORD *)a1 + 16) = v23;
      VectorFromTokensInternal = (char *)winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(
                                           *((_QWORD *)a1 + 36),
                                           a1 + 240);
      v20 = a1 + 120;
      if ( a1 + 120 != VectorFromTokensInternal )
      {
        if ( *v20 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v21 = *(_QWORD *)VectorFromTokensInternal;
        *(_QWORD *)VectorFromTokensInternal = 0;
        *v20 = v21;
      }
      if ( *((_QWORD *)a1 + 30) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 240);
      std::vector<__int64>::_Tidy(a1 + 192);
      v24 = *((_QWORD *)a1 + 23);
      if ( v24 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 31) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 31) )
        goto LABEL_44;
      return;
    case 5:
      std::vector<__int64>::_Tidy(a1 + 192);
      v24 = *((_QWORD *)a1 + 23);
      if ( v24 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
LABEL_44:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_WORD *)a1 + 81) )
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
0x180059520  mov     r11, rsp
0x180059523  mov     [r11+10h], rbx
0x180059527  mov     [r11+18h], rsi
0x18005952b  mov     [r11+8], rcx
0x18005952f  push    rdi
0x180059530  push    r12
0x180059532  push    r13
0x180059534  push    r14
0x180059536  push    r15
0x180059538  sub     rsp, 0A0h
0x18005953f  mov     rax, cs:__security_cookie
0x180059546  xor     rax, rsp
0x180059549  mov     [rsp+0C8h+var_30], rax
0x180059551  mov     rdi, rcx
0x180059554  mov     [rsp+0C8h+var_A0], rcx
0x180059559  lea     r14, [rdi+0A0h]
0x180059560  mov     [rsp+0C8h+var_90], r14
0x180059565  movzx   eax, word ptr [r14]
0x180059569  mov     [rsp+0C8h+var_A8], ax
0x18005956e  inc     ax; switch 7 cases
0x180059571  cmp     ax, 6
0x180059575  ja      def_180059590; jumptable 0000000180059590 default case, case 0
0x18005957b  movsx   rax, ax
0x18005957f  lea     rdx, cs:180000000h
0x180059586  mov     ecx, ds:(jpt_180059590 - 180000000h)[rdx+rax*4]
0x18005958d  add     rcx, rdx
0x180059590  jmp     rcx; switch jump
0x180059592  jmp     loc_180059910; jumptable 0000000180059590 case 3
0x180059597  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 0000000180059590 case 2
0x18005959e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x1800595a3  test    al, al
0x1800595a5  jz      loc_180059669
0x1800595ab  mov     eax, 1
0x1800595b0  lock xadd cs:dword_180086A24, eax
0x1800595b8  inc     eax
0x1800595ba  cmp     eax, 1
0x1800595bd  jnz     loc_1800596D4
0x1800595c3  mov     rcx, [rdi+88h]
0x1800595ca  mov     rax, [rcx]
0x1800595cd  lea     rdx, [rdi+0A8h]
0x1800595d4  mov     rax, [rax+28h]
0x1800595d8  call    cs:__guard_dispatch_icall_fptr
0x1800595de  mov     rbx, [rax]
0x1800595e1  test    rbx, rbx
0x1800595e4  jz      short loc_1800595EC
0x1800595e6  mov     rbx, [rbx+10h]
0x1800595ea  jmp     short loc_1800595F3
0x1800595ec  lea     rbx, qword_18006D0D8
0x1800595f3  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800595f8  mov     rcx, [rax+8]
0x1800595fc  test    rcx, rcx
0x1800595ff  jz      short loc_180059625
0x180059601  cmp     dword ptr [rcx], 0
0x180059604  jbe     short loc_180059625
0x180059606  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18005960b  lea     r9, dword_180086A24; volatile int *
0x180059612  lea     r8, aCreatevectorfr; "CreateVectorFromTokensAsync"
0x180059619  mov     rdx, rbx; wchar_t *
0x18005961c  mov     rcx, rax; this
0x18005961f  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180059624  nop
0x180059625  mov     rbx, [rdi+0A8h]
0x18005962c  cmp     rbx, 0
0x180059630  jz      loc_1800596D4
0x180059636  mov     [rsp+0C8h+var_98], rbx
0x18005963b  mov     ecx, 0FFFFFFFFh
0x180059640  lock xadd [rbx+18h], ecx
0x180059645  sub     ecx, 1
0x180059648  jnz     short loc_18005965E
0x18005964a  call    WINRT_IMPL_GetProcessHeap
0x18005964f  mov     rcx, rax; hHeap
0x180059652  mov     r8, rbx; lpMem
0x180059655  xor     edx, edx; dwFlags
0x180059657  call    WINRT_IMPL_HeapFree
0x18005965c  jmp     short loc_1800596D4
0x18005965e  test    ecx, ecx
0x180059660  jns     short loc_1800596D4
0x180059662  call    cs:__imp_abort
0x180059669  mov     rcx, [rdi+88h]
0x180059670  mov     rax, [rcx]
0x180059673  lea     rdx, [rdi+0B0h]
0x18005967a  mov     rax, [rax+28h]
0x18005967e  call    cs:__guard_dispatch_icall_fptr
0x180059684  mov     rbx, [rax]
0x180059687  test    rbx, rbx
0x18005968a  jz      short loc_180059692
0x18005968c  mov     rbx, [rbx+10h]
0x180059690  jmp     short loc_180059699
0x180059692  lea     rbx, qword_18006D0D8
0x180059699  lea     rdx, aCreatevectorfr; "CreateVectorFromTokensAsync"
0x1800596a0  mov     rcx, rbx; wchar_t *
0x1800596a3  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x1800596a8  mov     rbx, [rdi+0B0h]
0x1800596af  cmp     rbx, 0
0x1800596b3  jz      short loc_1800596D4
0x1800596b5  mov     [rsp+0C8h+var_98], rbx
0x1800596ba  mov     ecx, 0FFFFFFFFh
0x1800596bf  lock xadd [rbx+18h], ecx
0x1800596c4  sub     ecx, 1
0x1800596c7  jz      short loc_18005964A
0x1800596c9  test    ecx, ecx
0x1800596cb  jns     short loc_1800596D4
0x1800596cd  call    cs:__imp_abort
0x1800596d4  mov     rdx, [rdi+88h]
0x1800596db  mov     [rdi+120h], rdx
0x1800596e2  xor     ebx, ebx
0x1800596e4  mov     [rdi+0B8h], rbx
0x1800596eb  test    rdx, rdx
0x1800596ee  jz      short loc_180059716
0x1800596f0  mov     [rdi+0B8h], rdx
0x1800596f7  mov     rax, [rdx+8]
0x1800596fb  test    rax, rax
0x1800596fe  js      short loc_180059711
0x180059700  lea     rcx, [rax+1]
0x180059704  lock cmpxchg [rdx+8], rcx
0x18005970a  jz      short loc_180059716
0x18005970c  test    rax, rax
0x18005970f  jns     short loc_180059700
0x180059711  lock inc dword ptr [rax+rax+18h]
0x180059716  mov     [rdi+0C8h], rbx
0x18005971d  mov     [rdi+0D0h], rbx
0x180059724  mov     r15, [rdi+90h]
0x18005972b  mov     eax, [rdi+98h]
0x180059731  lea     rsi, ds:0[rax*8]
0x180059739  mov     [rdi+0C0h], rbx
0x180059740  mov     [rdi+0C8h], rbx
0x180059747  mov     [rdi+0D0h], rbx
0x18005974e  test    rax, rax
0x180059751  jz      short loc_180059789
0x180059753  mov     rcx, rsi
0x180059756  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005975b  mov     [rdi+0C0h], rax
0x180059762  mov     [rdi+0C8h], rax
0x180059769  lea     rbx, [rsi+rax]
0x18005976d  mov     [rdi+0D0h], rbx
0x180059774  mov     r8, rsi; Size
0x180059777  mov     rdx, r15; Src
0x18005977a  mov     rcx, rax; void *
0x18005977d  call    memmove
0x180059782  mov     [rdi+0C8h], rbx
0x180059789  mov     byte ptr [rdi+0D8h], 0
0x180059790  mov     eax, [rdi+70h]
0x180059793  cmp     eax, 2
0x180059796  jnz     short loc_1800597CE
0x180059798  lea     rdx, [rdi+110h]; struct winrt::impl::slim_source_location *
0x18005979f  mov     dword ptr [rdx], 0F8Ch
0x1800597a5  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800597ac  mov     [rdi+118h], rax
0x1800597b3  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x1800597b8  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1800597bd  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1800597c4  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800597c9  call    _CxxThrowException
0x1800597ce  mov     eax, 4
0x1800597d3  mov     [r14], ax
0x1800597d7  mov     rdx, rdi
0x1800597da  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x1800597df  jmp     loc_180059933
0x1800597e4  lea     rcx, [rdi+0C0h]; jumptable 0000000180059590 case 5
0x1800597eb  call    ?_Tidy@?$vector@_JV?$allocator@_J@std@@@std@@AEAAXXZ; std::vector<__int64>::_Tidy(void)
0x1800597f0  nop
0x1800597f1  lea     rcx, [rdi+0B8h]
0x1800597f8  mov     rax, [rcx]
0x1800597fb  mov     [rsp+0C8h+var_60], rax
0x180059800  test    rax, rax
0x180059803  jz      short loc_18005980B
0x180059805  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x18005980a  nop
0x18005980b  jmp     loc_180059910; jumptable 0000000180059590 cases -1,1
0x180059810  lea     r9, [rdi+0DCh]; jumptable 0000000180059590 case 4
0x180059817  xor     ebx, ebx
0x180059819  mov     [r9], ebx
0x18005981c  mov     rax, [rdi+0C0h]
0x180059823  mov     [rdi+0E0h], rax
0x18005982a  mov     rcx, [rdi+0C8h]
0x180059831  mov     [rsp+0C8h+var_50], rcx
0x180059836  mov     rax, [rdi+0C0h]
0x18005983d  mov     [rsp+0C8h+var_58], rax
0x180059842  sub     rcx, rax
0x180059845  sar     rcx, 3
0x180059849  mov     [rdi+0E8h], ecx
0x18005984f  lea     r8, [rdi+100h]
0x180059856  movups  xmm0, xmmword ptr [rdi+0E0h]
0x18005985d  movups  [rsp+0C8h+var_70], xmm0
0x180059862  movaps  xmmword ptr [r8], xmm0
0x180059866  lea     rdx, [rdi+0F0h]
0x18005986d  mov     rcx, [rdi+120h]
0x180059874  call    ?CreateVectorFromTokensInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180059879  mov     r15, rax
0x18005987c  lea     rsi, [rdi+78h]
0x180059880  cmp     rsi, rax
0x180059883  jz      short loc_18005989B
0x180059885  cmp     [rsi], rbx
0x180059888  jz      short loc_180059892
0x18005988a  mov     rcx, rsi
0x18005988d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180059892  mov     rax, [r15]
0x180059895  mov     [r15], rbx
0x180059898  mov     [rsi], rax
0x18005989b  mov     rax, [rdi+0F0h]
0x1800598a2  mov     [rsp+0C8h+var_98], rax
0x1800598a7  test    rax, rax
0x1800598aa  jz      short loc_1800598B9
0x1800598ac  lea     rcx, [rdi+0F0h]
0x1800598b3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800598b8  nop
0x1800598b9  lea     rcx, [rdi+0C0h]
0x1800598c0  call    ?_Tidy@?$vector@_JV?$allocator@_J@std@@@std@@AEAAXXZ; std::vector<__int64>::_Tidy(void)
0x1800598c5  nop
0x1800598c6  lea     rcx, [rdi+0B8h]
0x1800598cd  mov     rax, [rcx]
0x1800598d0  mov     [rsp+0C8h+var_60], rax
0x1800598d5  test    rax, rax
0x1800598d8  jz      short loc_1800598E0
0x1800598da  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x1800598df  nop
0x1800598e0  jmp     short loc_1800598EE
0x1800598e2  xor     ebx, ebx
0x1800598e4  mov     r14, [rsp+0C8h+var_90]
0x1800598e9  mov     rdi, [rsp+0C8h+var_A0]
0x1800598ee  lea     rax, [rdi+10h]
0x1800598f2  lea     rcx, [rdi+0F8h]
0x1800598f9  mov     [rcx], rax
0x1800598fc  xor     eax, eax
0x1800598fe  mov     [r14], ax
0x180059902  mov     [rdi], rbx
0x180059905  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18005990a  test    al, al
0x18005990c  jnz     short loc_180059933
0x18005990e  xchg    ax, ax
0x180059910  lea     rcx, [rdi+10h]; jumptable 0000000180059590 cases -1,1
0x180059914  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x180059919  cmp     word ptr [rdi+0A2h], 0
0x180059921  jz      short loc_180059933
0x180059923  mov     edx, 130h; unsigned __int64
0x180059928  mov     rcx, rdi; void *
0x18005992b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180059930  jmp     short loc_180059933
0x180059932  int     3; Trap to Debugger
0x180059933  mov     rcx, [rsp+0C8h+var_30]
0x18005993b  xor     rcx, rsp; StackCookie
0x18005993e  call    __security_check_cookie
0x180059943  lea     r11, [rsp+0C8h+var_28]
0x18005994b  mov     rbx, [r11+38h]
0x18005994f  mov     rsi, [r11+40h]
0x180059953  mov     rsp, r11
0x180059956  pop     r15
0x180059958  pop     r14
0x18005995a  pop     r13
0x18005995c  pop     r12
0x18005995e  pop     rdi
0x18005995f  retn
```
