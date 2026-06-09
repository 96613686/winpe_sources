# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateAsync$_ResumeCoro$1

- ea: `0x180051770`
- end: `0x180051d60`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateAsync$_ResumeCoro$1`
- size: `1520`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c000`
- `0x180051760`

## callees

- `0x180001f40`
- `0x180002bb0`
- `0x180008520`
- `0x180008600`
- `0x180009580`
- `0x180009ac0`
- `0x180009bb0`
- `0x180009fa0`
- `0x18000c160`
- `0x18000d050`
- `0x180010230`
- `0x1800103e0`
- `0x180014100`
- `0x180014540`
- `0x180014840`
- `0x180015090`
- `0x1800151a0`
- `0x180015bd0`
- `0x1800161b0`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18004ecf0`
- `0x180051770`
- `0x18005e260`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800519b6`
- `KERNEL32!CloseHandle` at `0x180051b01`
- `KERNEL32!CloseHandle` at `0x180051b1f`
- `KERNEL32!CloseHandle` at `0x180051cb7`
- `KERNEL32!CloseHandle` at `0x1800519b6`
- `KERNEL32!CloseHandle` at `0x180051b01`
- `KERNEL32!CloseHandle` at `0x180051b1f`
- `KERNEL32!CloseHandle` at `0x180051cb7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180051ae9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180051ae9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180051ab5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180051ab5`

## string_xrefs

- `0x180051891`: `CreateAsync`
- `0x180051909`: `CreateAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateAsync__ResumeCoro_1(
        char *a1)
{
  _WORD *v2; // r12
  const wchar_t *v3; // r14
  _DWORD *v4; // rcx
  TelemetryLogger *v5; // rax
  char *v6; // rcx
  const wchar_t *v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx
  winrt::hresult *v10; // rax
  __int64 *v11; // r13
  __int64 *v12; // r14
  void *v13; // rsi
  HANDLE *v14; // rsi
  void *v15; // r14
  unsigned int v16; // r8d
  const char *v17; // r9
  wil::details::in1diag3 *v18; // rcx
  _QWORD *v19; // r15
  __int64 *v20; // rsi
  __int64 v21; // rcx
  void (*v22)(void); // rax
  __int64 *v23; // r14
  __int64 v24; // rax
  void (*v25)(void); // rax
  __int64 v26; // rax
  __int64 v27; // rax
  _QWORD *v28; // r14
  _QWORD *v29; // rsi
  HANDLE hToken; // [rsp+20h] [rbp-118h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-D0h]
  __int64 v33; // [rsp+70h] [rbp-C8h]
  HANDLE v34; // [rsp+78h] [rbp-C0h]
  __int128 v35; // [rsp+80h] [rbp-B8h]
  unsigned __int64 v36; // [rsp+98h] [rbp-A0h]
  HANDLE v37; // [rsp+A0h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v2 = a1 + 152;
  switch ( *((_WORD *)a1 + 76) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_61;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&dword_180086670) != 1 )
          goto LABEL_14;
        *((_OWORD *)a1 + 10) = 0;
        *((_QWORD *)a1 + 22) = 0;
        *((_QWORD *)a1 + 23) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)a1 + 20,
          L"Microsoft.Windows.SemanticSearch.ImageSearchEmbeddingsCreator",
          0x3Du);
        v3 = (const wchar_t *)(a1 + 160);
        v36 = *((_QWORD *)a1 + 23);
        if ( v36 > 7 )
        {
          v3 = (const wchar_t *)*((_QWORD *)a1 + 20);
          *(_QWORD *)&v35 = v3;
        }
        v4 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
        if ( v4 && *v4 )
        {
          v5 = TelemetryLogger::Instance();
          TelemetryLogger::InitApiData_(v5, v3, L"CreateAsync", &dword_180086670);
        }
        v6 = a1 + 160;
      }
      else
      {
        *((_OWORD *)a1 + 20) = 0;
        *((_QWORD *)a1 + 42) = 0;
        *((_QWORD *)a1 + 43) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)a1 + 40,
          L"Microsoft.Windows.SemanticSearch.ImageSearchEmbeddingsCreator",
          0x3Du);
        v7 = (const wchar_t *)(a1 + 320);
        v36 = *((_QWORD *)a1 + 43);
        if ( v36 > 7 )
        {
          v7 = (const wchar_t *)*((_QWORD *)a1 + 40);
          *(_QWORD *)&v35 = v7;
        }
        TelemetryLogger::LogWclApiUsage(v7, L"CreateAsync");
        v6 = a1 + 320;
      }
      std::wstring::_Tidy_deallocate((__int64)v6);
LABEL_14:
      *((_WORD *)a1 + 96) = 257;
      *((_QWORD *)a1 + 25) = 0;
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 200);
      a1[208] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 88) = 3980;
        *((_QWORD *)a1 + 45) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 352));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v8, a1);
      return;
    case 4:
      if ( (*((_DWORD *)a1 + 33) & 3) == 0 )
      {
        *((_DWORD *)a1 + 54) = 281;
        *((_QWORD *)a1 + 28) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\ImageSearch\\Imag"
                               "eSearchEmbeddingsCreator.cpp";
        v10 = winrt::hresult::hresult((winrt::hresult *)(a1 + 232), -2147024809);
        winrt::throw_hresult(*(unsigned int *)v10, a1 + 216);
      }
      v11 = (__int64 *)(a1 + 240);
      *((_QWORD *)a1 + 30) = 0;
      v12 = (__int64 *)(a1 + 248);
      *((_QWORD *)a1 + 31) = 0;
      *((_QWORD *)a1 + 32) = a1 + 132;
      *((_QWORD *)a1 + 33) = a1 + 192;
      *((_QWORD *)a1 + 34) = a1 + 136;
      *((_QWORD *)a1 + 35) = a1 + 240;
      *((_QWORD *)a1 + 36) = a1 + 193;
      *((_QWORD *)a1 + 37) = a1 + 248;
      v13 = (void *)*((_QWORD *)a1 + 25);
      hToken = v13;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::GetImpl'::`2'::impl)
        && v13 )
      {
        v14 = (HANDLE *)(a1 + 368);
        *((_QWORD *)a1 + 46) = 0;
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 368);
        v15 = (void *)*((_QWORD *)a1 + 46);
        *((_QWORD *)a1 + 46) = 0;
        *((_QWORD *)a1 + 47) = v15;
        if ( !ImpersonateLoggedOnUser(hToken) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x23, v16, v17);
        winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateAsync_::_2_::_lambda_1_::operator()(a1 + 256);
        if ( v15 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v15) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
          if ( v15 )
            CloseHandle(v15);
        }
        if ( *v14 && *v14 != (HANDLE)-1LL )
        {
          v37 = *v14;
          CloseHandle(v37);
        }
        v12 = (__int64 *)(a1 + 248);
      }
      else
      {
        winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateAsync_::_2_::_lambda_1_::operator()(a1 + 256);
      }
      v19 = operator new(0x60u);
      *((_QWORD *)a1 + 48) = v19;
      v35 = *(_OWORD *)(a1 + 136);
      v20 = (__int64 *)(a1 + 392);
      v21 = *v12;
      *((_QWORD *)a1 + 49) = *v12;
      if ( v21 )
      {
        v32 = v21;
        v22 = *(void (**)(void))(*(_QWORD *)v21 + 8LL);
        v32 = *v12;
        v22();
      }
      *((_QWORD *)a1 + 52) = v20;
      v23 = (__int64 *)(a1 + 400);
      v24 = *v11;
      *((_QWORD *)a1 + 50) = *v11;
      if ( v24 )
      {
        v33 = v24;
        v25 = *(void (**)(void))(*(_QWORD *)v24 + 8LL);
        v33 = *v11;
        v25();
      }
      *((_QWORD *)a1 + 53) = v23;
      v26 = *v20;
      *v20 = 0;
      *((_QWORD *)a1 + 51) = v26;
      v27 = *v23;
      *v23 = 0;
      *((_QWORD *)a1 + 54) = v27;
      *((_OWORD *)a1 + 28) = v35;
      winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::ImageSearchEmbeddingsCreator(v19);
      *v19 = &winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::`vftable';
      if ( *v23 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 400);
      if ( *v20 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 392);
      v28 = v19 + 2;
      if ( !v19 )
        v28 = 0;
      *((_QWORD *)a1 + 38) = v28;
      v29 = a1 + 120;
      if ( a1 + 120 == a1 + 304 )
      {
        if ( v28 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 304);
      }
      else
      {
        if ( *v29 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        *v29 = v28;
      }
      v32 = *((_QWORD *)a1 + 31);
      if ( v32 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 248);
      v33 = *v11;
      if ( v33 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 240);
      if ( *((_QWORD *)a1 + 25) && *((_QWORD *)a1 + 25) != -1 )
      {
        v34 = (HANDLE)*((_QWORD *)a1 + 25);
        CloseHandle(v34);
      }
      *((_QWORD *)a1 + 39) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 39) )
        goto LABEL_61;
      return;
    case 5:
      if ( *((_QWORD *)a1 + 25) && *((_QWORD *)a1 + 25) != -1 )
      {
        v9 = (void *)*((_QWORD *)a1 + 25);
        v34 = (HANDLE)*((_QWORD *)a1 + 25);
        CloseHandle(v9);
      }
LABEL_61:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_WORD *)a1 + 77) )
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
0x180051770  mov     r11, rsp
0x180051773  mov     [r11+10h], rbx
0x180051777  mov     [r11+18h], rsi
0x18005177b  mov     [r11+8], rcx
0x18005177f  push    rdi
0x180051780  push    r12
0x180051782  push    r13
0x180051784  push    r14
0x180051786  push    r15
0x180051788  sub     rsp, 110h
0x18005178f  mov     rax, cs:__security_cookie
0x180051796  xor     rax, rsp
0x180051799  mov     [rsp+138h+var_38], rax
0x1800517a1  mov     rbx, rcx
0x1800517a4  mov     [rsp+138h+var_108], rcx
0x1800517a9  lea     r12, [rbx+98h]
0x1800517b0  mov     [rsp+138h+var_100], r12
0x1800517b5  movzx   eax, word ptr [r12]
0x1800517ba  mov     [rsp+138h+var_110], ax
0x1800517bf  inc     ax; switch 7 cases
0x1800517c2  cmp     ax, 6
0x1800517c6  ja      def_1800517E1; jumptable 00000001800517E1 default case, case 0
0x1800517cc  movsx   rax, ax
0x1800517d0  lea     rdx, cs:180000000h
0x1800517d7  mov     ecx, ds:(jpt_1800517E1 - 180000000h)[rdx+rax*4]
0x1800517de  add     rcx, rdx
0x1800517e1  jmp     rcx; switch jump
0x1800517e3  jmp     loc_180051CF0; jumptable 00000001800517E1 case 3
0x1800517e8  xor     edi, edi; jumptable 00000001800517E1 case 2
0x1800517ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x1800517f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x1800517f6  test    al, al
0x1800517f8  jz      loc_1800518AD
0x1800517fe  mov     eax, 1
0x180051803  lock xadd cs:dword_180086670, eax
0x18005180b  inc     eax
0x18005180d  cmp     eax, 1
0x180051810  jnz     loc_180051921
0x180051816  xorps   xmm0, xmm0
0x180051819  movups  xmmword ptr [rbx+0A0h], xmm0
0x180051820  mov     [rbx+0B0h], rdi
0x180051827  mov     [rbx+0B8h], rdi
0x18005182e  mov     r8d, 3Dh ; '='
0x180051834  lea     rdx, aMicrosoftWindo_31; "Microsoft.Windows.SemanticSearch.ImageS"...
0x18005183b  lea     rcx, [rbx+0A0h]
0x180051842  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180051847  lea     r14, [rbx+0A0h]
0x18005184e  mov     rax, [rbx+0B8h]
0x180051855  mov     [rsp+138h+var_A0], rax
0x18005185d  cmp     rax, 7
0x180051861  jbe     short loc_180051872
0x180051863  mov     r14, [rbx+0A0h]
0x18005186a  mov     qword ptr [rsp+138h+var_B8], r14
0x180051872  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180051877  mov     rcx, [rax+8]
0x18005187b  test    rcx, rcx
0x18005187e  jz      short loc_1800518A4
0x180051880  cmp     dword ptr [rcx], 0
0x180051883  jbe     short loc_1800518A4
0x180051885  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18005188a  lea     r9, dword_180086670; volatile int *
0x180051891  lea     r8, aCreateasync; "CreateAsync"
0x180051898  mov     rdx, r14; wchar_t *
0x18005189b  mov     rcx, rax; this
0x18005189e  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x1800518a3  nop
0x1800518a4  lea     rcx, [rbx+0A0h]
0x1800518ab  jmp     short loc_18005191C
0x1800518ad  xorps   xmm0, xmm0
0x1800518b0  movups  xmmword ptr [rbx+140h], xmm0
0x1800518b7  mov     [rbx+150h], rdi
0x1800518be  mov     [rbx+158h], rdi
0x1800518c5  mov     r8d, 3Dh ; '='
0x1800518cb  lea     rdx, aMicrosoftWindo_31; "Microsoft.Windows.SemanticSearch.ImageS"...
0x1800518d2  lea     rcx, [rbx+140h]
0x1800518d9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800518de  lea     rcx, [rbx+140h]
0x1800518e5  mov     rax, [rbx+158h]
0x1800518ec  mov     [rsp+138h+var_A0], rax
0x1800518f4  cmp     rax, 7
0x1800518f8  jbe     short loc_180051909
0x1800518fa  mov     rcx, [rbx+140h]; wchar_t *
0x180051901  mov     qword ptr [rsp+138h+var_B8], rcx
0x180051909  lea     rdx, aCreateasync; "CreateAsync"
0x180051910  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180051915  lea     rcx, [rbx+140h]
0x18005191c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051921  mov     word ptr [rbx+0C0h], 101h
0x18005192a  lea     rcx, [rbx+0C8h]
0x180051931  mov     [rcx], rdi
0x180051934  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180051939  nop
0x18005193a  mov     byte ptr [rbx+0D0h], 0
0x180051941  mov     eax, [rbx+70h]
0x180051944  cmp     eax, 2
0x180051947  jnz     short loc_18005197F
0x180051949  lea     rdx, [rbx+160h]; struct winrt::impl::slim_source_location *
0x180051950  mov     dword ptr [rdx], 0F8Ch
0x180051956  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005195d  mov     [rbx+168h], rax
0x180051964  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180051969  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005196e  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180051975  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18005197a  call    _CxxThrowException
0x18005197f  mov     eax, 4
0x180051984  mov     [r12], ax
0x180051989  mov     rdx, rbx
0x18005198c  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180051991  jmp     loc_180051D13
0x180051996  cmp     qword ptr [rbx+0C8h], 0; jumptable 00000001800517E1 case 5
0x18005199e  jz      short loc_1800519BD
0x1800519a0  cmp     qword ptr [rbx+0C8h], 0FFFFFFFFFFFFFFFFh
0x1800519a8  jz      short loc_1800519BD
0x1800519aa  mov     rcx, [rbx+0C8h]; hObject
0x1800519b1  mov     [rsp+138h+var_C0], rcx
0x1800519b6  call    cs:__imp_CloseHandle
0x1800519bc  nop
0x1800519bd  jmp     loc_180051CF0; jumptable 00000001800517E1 cases -1,1
0x1800519c2  lea     rax, [rbx+84h]; jumptable 00000001800517E1 case 4
0x1800519c9  test    dword ptr [rax], 3
0x1800519cf  jnz     short loc_180051A08
0x1800519d1  mov     dword ptr [rbx+0D8h], 119h
0x1800519db  lea     rax, aCW1SProductApi_8; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800519e2  mov     [rbx+0E0h], rax
0x1800519e9  lea     rcx, [rbx+0E8h]; this
0x1800519f0  mov     edx, 80070057h; int
0x1800519f5  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800519fa  lea     rdx, [rbx+0D8h]
0x180051a01  mov     ecx, [rax]
0x180051a03  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180051a08  lea     r13, [rbx+0F0h]
0x180051a0f  xor     edi, edi
0x180051a11  mov     [r13+0], rdi
0x180051a15  lea     r14, [rbx+0F8h]
0x180051a1c  mov     [r14], rdi
0x180051a1f  mov     [rbx+100h], rax
0x180051a26  lea     rax, [rbx+0C0h]
0x180051a2d  mov     [rbx+108h], rax
0x180051a34  lea     rax, [rbx+88h]
0x180051a3b  mov     [rbx+110h], rax
0x180051a42  mov     [rbx+118h], r13
0x180051a49  lea     rax, [rbx+0C1h]
0x180051a50  mov     [rbx+120h], rax
0x180051a57  mov     [rbx+128h], r14
0x180051a5e  mov     rsi, [rbx+0C8h]
0x180051a65  mov     [rsp+138h+hToken], rsi
0x180051a6a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_LocalService_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_LocalService_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::GetImpl(void)'::`2'::impl
0x180051a71  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_LocalService_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::__private_IsEnabled(void)
0x180051a76  test    al, al
0x180051a78  jz      short loc_180051A7F
0x180051a7a  test    rsi, rsi
0x180051a7d  jnz     short loc_180051A90
0x180051a7f  lea     rcx, [rbx+100h]
0x180051a86  call    _winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateAsync____2____lambda_1___operator__
0x180051a8b  jmp     loc_180051B2C
0x180051a90  lea     rsi, [rbx+170h]
0x180051a97  mov     [rsi], rdi
0x180051a9a  mov     rcx, rsi
0x180051a9d  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180051aa2  nop
0x180051aa3  mov     r14, [rsi]
0x180051aa6  mov     [rsi], rdi
0x180051aa9  mov     [rbx+178h], r14
0x180051ab0  mov     rcx, [rsp+138h+hToken]; hToken
0x180051ab5  call    cs:__imp_ImpersonateLoggedOnUser
0x180051abb  mov     rcx, [rsp+138h]; this
0x180051ac3  test    eax, eax
0x180051ac5  jnz     short loc_180051AD1
0x180051ac7  mov     edx, 23h ; '#'; void *
0x180051acc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180051ad1  lea     rcx, [rbx+100h]
0x180051ad8  call    _winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateAsync____2____lambda_1___operator__
0x180051add  nop
0x180051ade  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180051ae2  jz      short loc_180051B08
0x180051ae4  mov     rdx, r14; Token
0x180051ae7  xor     ecx, ecx; Thread
0x180051ae9  call    cs:__imp_SetThreadToken
0x180051aef  test    eax, eax
0x180051af1  jnz     short loc_180051AF9
0x180051af3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180051af9  test    r14, r14
0x180051afc  jz      short loc_180051B08
0x180051afe  mov     rcx, r14; hObject
0x180051b01  call    cs:__imp_CloseHandle
0x180051b07  nop
0x180051b08  cmp     qword ptr [rsi], 0
0x180051b0c  jz      short loc_180051B25
0x180051b0e  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180051b12  jz      short loc_180051B25
0x180051b14  mov     rcx, [rsi]; hObject
0x180051b17  mov     [rsp+138h+var_98], rcx
0x180051b1f  call    cs:__imp_CloseHandle
0x180051b25  lea     r14, [rbx+0F8h]
0x180051b2c  mov     ecx, 60h ; '`'; Size
0x180051b31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051b36  mov     r15, rax
0x180051b39  mov     [rbx+180h], rax
0x180051b40  movups  xmm0, xmmword ptr [rbx+88h]
0x180051b47  movups  [rsp+138h+var_B8], xmm0
0x180051b4f  lea     rsi, [rbx+188h]
0x180051b56  mov     rcx, [r14]
0x180051b59  mov     [rsi], rcx
0x180051b5c  cmp     rcx, 0
0x180051b60  jz      short loc_180051B7C
0x180051b62  mov     [rsp+138h+var_D0], rcx
0x180051b67  mov     rcx, [rcx]
0x180051b6a  mov     rax, [rcx+8]
0x180051b6e  mov     rcx, [r14]
0x180051b71  mov     [rsp+138h+var_D0], rcx
0x180051b76  call    cs:__guard_dispatch_icall_fptr
0x180051b7c  mov     [rbx+1A0h], rsi
0x180051b83  lea     r14, [rbx+190h]
0x180051b8a  mov     rax, [r13+0]
0x180051b8e  mov     [r14], rax
0x180051b91  cmp     rax, 0
0x180051b95  jz      short loc_180051BB2
0x180051b97  mov     [rsp+138h+var_C8], rax
0x180051b9c  mov     rcx, [rax]
0x180051b9f  mov     rax, [rcx+8]
0x180051ba3  mov     rcx, [r13+0]
0x180051ba7  mov     [rsp+138h+var_C8], rcx
0x180051bac  call    cs:__guard_dispatch_icall_fptr
0x180051bb2  mov     [rbx+1A8h], r14
0x180051bb9  lea     r8, [rbx+198h]
0x180051bc0  mov     rax, [rsi]
0x180051bc3  mov     [rsi], rdi
0x180051bc6  mov     [r8], rax
0x180051bc9  lea     rdx, [rbx+1B0h]
0x180051bd0  mov     rax, [r14]
0x180051bd3  mov     [r14], rdi
0x180051bd6  mov     [rdx], rax
0x180051bd9  lea     r9, [rbx+1C0h]
0x180051be0  movups  xmm0, [rsp+138h+var_B8]
0x180051be8  movaps  xmmword ptr [r9], xmm0
0x180051bec  mov     rcx, r15
0x180051bef  call    ??0ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA@UIImageSearchImageEmbeddingsSession4@SemanticSearchInternal@345@UIImageSearchTextEmbeddingsSession4@7345@Uguid@5@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::ImageSearchEmbeddingsCreator(winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchImageEmbeddingsSession4,winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchTextEmbeddingsSession4,winrt::guid)
0x180051bf4  lea     rax, ??_7ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::`vftable'
0x180051bfb  mov     [r15], rax
0x180051bfe  mov     rax, [r14]
0x180051c01  mov     [rsp+138h+var_F8], rax
0x180051c06  test    rax, rax
0x180051c09  jz      short loc_180051C14
0x180051c0b  mov     rcx, r14
0x180051c0e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180051c13  nop
0x180051c14  mov     rax, [rsi]
0x180051c17  mov     [rsp+138h+var_F0], rax
0x180051c1c  test    rax, rax
0x180051c1f  jz      short loc_180051C2A
0x180051c21  mov     rcx, rsi
0x180051c24  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180051c29  nop
0x180051c2a  lea     r14, [r15+10h]
0x180051c2e  test    r15, r15
0x180051c31  cmovz   r14, rdi
0x180051c35  lea     rcx, [rbx+130h]
0x180051c3c  mov     [rcx], r14
0x180051c3f  lea     rsi, [rbx+78h]
0x180051c43  cmp     rsi, rcx
0x180051c46  jz      short loc_180051C5B
0x180051c48  cmp     qword ptr [rsi], 0
0x180051c4c  jz      short loc_180051C56
0x180051c4e  mov     rcx, rsi
0x180051c51  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180051c56  mov     [rsi], r14
0x180051c59  jmp     short loc_180051C66
0x180051c5b  test    r14, r14
0x180051c5e  jz      short loc_180051C66
0x180051c60  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180051c65  nop
0x180051c66  lea     rcx, [rbx+0F8h]
0x180051c6d  mov     rax, [rcx]
0x180051c70  mov     [rsp+138h+var_D0], rax
0x180051c75  test    rax, rax
0x180051c78  jz      short loc_180051C80
0x180051c7a  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180051c7f  nop
0x180051c80  mov     rax, [r13+0]
0x180051c84  mov     [rsp+138h+var_C8], rax
0x180051c89  test    rax, rax
0x180051c8c  jz      short loc_180051C97
0x180051c8e  mov     rcx, r13
0x180051c91  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180051c96  nop
0x180051c97  cmp     qword ptr [rbx+0C8h], 0
0x180051c9f  jz      short loc_180051CBE
0x180051ca1  cmp     qword ptr [rbx+0C8h], 0FFFFFFFFFFFFFFFFh
0x180051ca9  jz      short loc_180051CBE
0x180051cab  mov     rcx, [rbx+0C8h]; hObject
0x180051cb2  mov     [rsp+138h+var_C0], rcx
0x180051cb7  call    cs:__imp_CloseHandle
0x180051cbd  nop
0x180051cbe  jmp     short loc_180051CCC
0x180051cc0  xor     edi, edi
0x180051cc2  mov     r12, [rsp+138h+var_100]
0x180051cc7  mov     rbx, [rsp+138h+var_108]
0x180051ccc  lea     rax, [rbx+10h]
0x180051cd0  lea     rcx, [rbx+138h]
  ... truncated ...
```
