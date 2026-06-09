# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorAsync$_ResumeCoro$1

- ea: `0x180058d60`
- end: `0x18005912c`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorAsync$_ResumeCoro$1`
- size: `972`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800337e0`
- `0x180058d40`

## callees

- `0x180002bb0`
- `0x180009fa0`
- `0x18000d050`
- `0x180010000`
- `0x180010230`
- `0x180014100`
- `0x180014540`
- `0x180014840`
- `0x180015090`
- `0x1800151a0`
- `0x180033f70`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x180051379`
- `0x18005137f`
- `0x180058d60`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180058e98`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180058f03`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800590bf`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180058e98`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180058f03`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800590bf`

## string_xrefs

- `0x180058e48`: `CreateVectorAsync`
- `0x180058ecf`: `CreateVectorAsync`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorAsync__ResumeCoro_1(
        char *a1)
{
  _WORD *v2; // r15
  unsigned __int64 v3; // rcx
  __int64 v4; // rax
  const wchar_t *v5; // rdi
  TelemetryLogger *v6; // rax
  volatile signed __int32 *v7; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v9; // rax
  const wchar_t *v10; // rdi
  __int64 v11; // rdx
  signed __int64 v12; // rax
  signed __int64 v13; // rtt
  char *VectorInternal; // rsi
  _QWORD *v15; // rdi
  __int64 v16; // rax
  volatile signed __int32 *v17; // rdi
  int v18; // ecx
  HANDLE v19; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v21; // [rsp+58h] [rbp-30h]

  v2 = a1 + 152;
  switch ( *((_WORD *)a1 + 76) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_42;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&dword_180086A2C) == 1 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(
                 *((_QWORD *)a1 + 17),
                 a1 + 160);
          if ( *(_QWORD *)v4 )
            v5 = *(const wchar_t **)(*(_QWORD *)v4 + 16LL);
          else
            v5 = (const wchar_t *)&qword_18006D0D8;
          v3 = *((_QWORD *)TelemetryLogger::Instance() + 1);
          if ( v3 && *(_DWORD *)v3 )
          {
            v6 = TelemetryLogger::Instance();
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorAsync", &dword_180086A2C);
          }
          v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 20);
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
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(*((_QWORD *)a1 + 17), a1 + 168);
        if ( *(_QWORD *)v9 )
          v10 = *(const wchar_t **)(*(_QWORD *)v9 + 16LL);
        else
          v10 = (const wchar_t *)&qword_18006D0D8;
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorAsync");
        v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 21);
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
      *((_QWORD *)a1 + 28) = v11;
      *((_QWORD *)a1 + 22) = 0;
      if ( v11 )
      {
        *((_QWORD *)a1 + 22) = v11;
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
      a1[184] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 52) = 3980;
        *((_QWORD *)a1 + 27) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 208));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      *((_DWORD *)a1 + 47) = 0;
      VectorInternal = (char *)winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(
                                 *((_QWORD *)a1 + 28),
                                 a1 + 192,
                                 a1 + 144);
      v15 = a1 + 120;
      if ( a1 + 120 != VectorInternal )
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v16 = *(_QWORD *)VectorInternal;
        *(_QWORD *)VectorInternal = 0;
        *v15 = v16;
      }
      if ( *((_QWORD *)a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 192);
      v21 = *((_QWORD *)a1 + 22);
      if ( v21 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 25) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 25) )
        goto LABEL_42;
      return;
    case 5:
      v21 = *((_QWORD *)a1 + 22);
      if ( v21 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
LABEL_42:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      v17 = (volatile signed __int32 *)*((_QWORD *)a1 + 18);
      if ( v17 )
      {
        v18 = _InterlockedDecrement(v17 + 6);
        if ( v18 )
        {
          if ( v18 < 0 )
            abort();
        }
        else
        {
          v19 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
        }
        *((_QWORD *)a1 + 18) = 0;
      }
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
0x180058d60  mov     r11, rsp
0x180058d63  mov     [r11+10h], rbx
0x180058d67  mov     [r11+18h], rsi
0x180058d6b  mov     [r11+8], rcx
0x180058d6f  push    rdi
0x180058d70  push    r14
0x180058d72  push    r15
0x180058d74  sub     rsp, 70h
0x180058d78  mov     rax, cs:__security_cookie
0x180058d7f  xor     rax, rsp
0x180058d82  mov     [rsp+88h+var_20], rax
0x180058d87  mov     rbx, rcx
0x180058d8a  mov     [rsp+88h+var_60], rcx
0x180058d8f  lea     r15, [rbx+98h]
0x180058d96  mov     [rsp+88h+var_50], r15
0x180058d9b  movzx   eax, word ptr [r15]
0x180058d9f  mov     [rsp+88h+var_68], ax
0x180058da4  inc     ax; switch 7 cases
0x180058da7  cmp     ax, 6
0x180058dab  ja      def_180058DC6; jumptable 0000000180058DC6 default case, case 0
0x180058db1  movsx   rax, ax
0x180058db5  lea     rdx, cs:180000000h
0x180058dbc  mov     ecx, ds:(jpt_180058DC6 - 180000000h)[rdx+rax*4]
0x180058dc3  add     rcx, rdx
0x180058dc6  jmp     rcx; switch jump
0x180058dc8  jmp     loc_180059083; jumptable 0000000180058DC6 case 3
0x180058dcd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 0000000180058DC6 case 2
0x180058dd4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180058dd9  test    al, al
0x180058ddb  jz      loc_180058E9F
0x180058de1  mov     eax, 1
0x180058de6  lock xadd cs:dword_180086A2C, eax
0x180058dee  inc     eax
0x180058df0  cmp     eax, 1
0x180058df3  jnz     loc_180058F0A
0x180058df9  mov     rcx, [rbx+88h]
0x180058e00  mov     rax, [rcx]
0x180058e03  lea     rdx, [rbx+0A0h]
0x180058e0a  mov     rax, [rax+28h]
0x180058e0e  call    cs:__guard_dispatch_icall_fptr
0x180058e14  mov     rdi, [rax]
0x180058e17  test    rdi, rdi
0x180058e1a  jz      short loc_180058E22
0x180058e1c  mov     rdi, [rdi+10h]
0x180058e20  jmp     short loc_180058E29
0x180058e22  lea     rdi, qword_18006D0D8
0x180058e29  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180058e2e  mov     rcx, [rax+8]
0x180058e32  test    rcx, rcx
0x180058e35  jz      short loc_180058E5B
0x180058e37  cmp     dword ptr [rcx], 0
0x180058e3a  jbe     short loc_180058E5B
0x180058e3c  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180058e41  lea     r9, dword_180086A2C; volatile int *
0x180058e48  lea     r8, aCreatevectoras; "CreateVectorAsync"
0x180058e4f  mov     rdx, rdi; wchar_t *
0x180058e52  mov     rcx, rax; this
0x180058e55  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180058e5a  nop
0x180058e5b  mov     rdi, [rbx+0A0h]
0x180058e62  cmp     rdi, 0
0x180058e66  jz      loc_180058F0A
0x180058e6c  mov     [rsp+88h+var_58], rdi
0x180058e71  mov     ecx, 0FFFFFFFFh
0x180058e76  lock xadd [rdi+18h], ecx
0x180058e7b  sub     ecx, 1
0x180058e7e  jnz     short loc_180058E94
0x180058e80  call    WINRT_IMPL_GetProcessHeap
0x180058e85  mov     rcx, rax; hHeap
0x180058e88  mov     r8, rdi; lpMem
0x180058e8b  xor     edx, edx; dwFlags
0x180058e8d  call    WINRT_IMPL_HeapFree
0x180058e92  jmp     short loc_180058F0A
0x180058e94  test    ecx, ecx
0x180058e96  jns     short loc_180058F0A
0x180058e98  call    cs:__imp_abort
0x180058e9f  mov     rcx, [rbx+88h]
0x180058ea6  mov     rax, [rcx]
0x180058ea9  lea     rdx, [rbx+0A8h]
0x180058eb0  mov     rax, [rax+28h]
0x180058eb4  call    cs:__guard_dispatch_icall_fptr
0x180058eba  mov     rdi, [rax]
0x180058ebd  test    rdi, rdi
0x180058ec0  jz      short loc_180058EC8
0x180058ec2  mov     rdi, [rdi+10h]
0x180058ec6  jmp     short loc_180058ECF
0x180058ec8  lea     rdi, qword_18006D0D8
0x180058ecf  lea     rdx, aCreatevectoras; "CreateVectorAsync"
0x180058ed6  mov     rcx, rdi; wchar_t *
0x180058ed9  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180058ede  mov     rdi, [rbx+0A8h]
0x180058ee5  cmp     rdi, 0
0x180058ee9  jz      short loc_180058F0A
0x180058eeb  mov     [rsp+88h+var_58], rdi
0x180058ef0  mov     ecx, 0FFFFFFFFh
0x180058ef5  lock xadd [rdi+18h], ecx
0x180058efa  sub     ecx, 1
0x180058efd  jz      short loc_180058E80
0x180058eff  test    ecx, ecx
0x180058f01  jns     short loc_180058F0A
0x180058f03  call    cs:__imp_abort
0x180058f0a  mov     rdx, [rbx+88h]
0x180058f11  mov     [rbx+0E0h], rdx
0x180058f18  mov     qword ptr [rbx+0B0h], 0
0x180058f23  test    rdx, rdx
0x180058f26  jz      short loc_180058F56
0x180058f28  mov     [rbx+0B0h], rdx
0x180058f2f  mov     rax, [rdx+8]
0x180058f33  test    rax, rax
0x180058f36  js      short loc_180058F51
0x180058f38  nop     dword ptr [rax+rax+00000000h]
0x180058f40  lea     rcx, [rax+1]
0x180058f44  lock cmpxchg [rdx+8], rcx
0x180058f4a  jz      short loc_180058F56
0x180058f4c  test    rax, rax
0x180058f4f  jns     short loc_180058F40
0x180058f51  lock inc dword ptr [rax+rax+18h]
0x180058f56  mov     byte ptr [rbx+0B8h], 0
0x180058f5d  mov     eax, [rbx+70h]
0x180058f60  cmp     eax, 2
0x180058f63  jnz     short loc_180058F9B
0x180058f65  lea     rdx, [rbx+0D0h]; struct winrt::impl::slim_source_location *
0x180058f6c  mov     dword ptr [rdx], 0F8Ch
0x180058f72  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180058f79  mov     [rbx+0D8h], rax
0x180058f80  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180058f85  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180058f8a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180058f91  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180058f96  call    _CxxThrowException
0x180058f9b  mov     eax, 4
0x180058fa0  mov     [r15], ax
0x180058fa4  mov     rdx, rbx
0x180058fa7  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180058fac  jmp     loc_1800590EB
0x180058fb1  lea     rcx, [rbx+0B0h]; jumptable 0000000180058DC6 case 5
0x180058fb8  mov     rax, [rcx]
0x180058fbb  mov     [rsp+88h+var_30], rax
0x180058fc0  test    rax, rax
0x180058fc3  jz      short loc_180058FCB
0x180058fc5  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180058fca  nop
0x180058fcb  jmp     loc_180059083; jumptable 0000000180058DC6 cases -1,1
0x180058fd0  lea     r9, [rbx+0BCh]; jumptable 0000000180058DC6 case 4
0x180058fd7  mov     dword ptr [r9], 0
0x180058fde  lea     r8, [rbx+90h]
0x180058fe5  lea     rdx, [rbx+0C0h]
0x180058fec  mov     rcx, [rbx+0E0h]
0x180058ff3  call    ?CreateVectorInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180058ff8  mov     rsi, rax
0x180058ffb  lea     rdi, [rbx+78h]
0x180058fff  cmp     rdi, rax
0x180059002  jz      short loc_18005901F
0x180059004  cmp     qword ptr [rdi], 0
0x180059008  jz      short loc_180059012
0x18005900a  mov     rcx, rdi
0x18005900d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180059012  mov     rax, [rsi]
0x180059015  mov     qword ptr [rsi], 0
0x18005901c  mov     [rdi], rax
0x18005901f  mov     rax, [rbx+0C0h]
0x180059026  mov     [rsp+88h+var_58], rax
0x18005902b  test    rax, rax
0x18005902e  jz      short loc_18005903D
0x180059030  lea     rcx, [rbx+0C0h]
0x180059037  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005903c  nop
0x18005903d  lea     rcx, [rbx+0B0h]
0x180059044  mov     rax, [rcx]
0x180059047  mov     [rsp+88h+var_30], rax
0x18005904c  test    rax, rax
0x18005904f  jz      short loc_180059057
0x180059051  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180059056  nop
0x180059057  jmp     short loc_180059063
0x180059059  mov     r15, [rsp+88h+var_50]
0x18005905e  mov     rbx, [rsp+88h+var_60]
0x180059063  lea     rax, [rbx+10h]
0x180059067  lea     rcx, [rbx+0C8h]
0x18005906e  mov     [rcx], rax
0x180059071  xor     eax, eax
0x180059073  mov     [r15], ax
0x180059077  mov     [rbx], rax
0x18005907a  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18005907f  test    al, al
0x180059081  jnz     short loc_1800590EB
0x180059083  lea     rcx, [rbx+10h]; jumptable 0000000180058DC6 cases -1,1
0x180059087  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x18005908c  mov     rdi, [rbx+90h]
0x180059093  test    rdi, rdi
0x180059096  jz      short loc_1800590D1
0x180059098  mov     ecx, 0FFFFFFFFh
0x18005909d  lock xadd [rdi+18h], ecx
0x1800590a2  sub     ecx, 1
0x1800590a5  jnz     short loc_1800590BB
0x1800590a7  call    WINRT_IMPL_GetProcessHeap
0x1800590ac  mov     rcx, rax; hHeap
0x1800590af  mov     r8, rdi; lpMem
0x1800590b2  xor     edx, edx; dwFlags
0x1800590b4  call    WINRT_IMPL_HeapFree
0x1800590b9  jmp     short loc_1800590C6
0x1800590bb  test    ecx, ecx
0x1800590bd  jns     short loc_1800590C6
0x1800590bf  call    cs:__imp_abort
0x1800590c6  mov     qword ptr [rbx+90h], 0
0x1800590d1  cmp     word ptr [rbx+9Ah], 0
0x1800590d9  jz      short loc_1800590EB
0x1800590db  mov     edx, 0F0h; unsigned __int64
0x1800590e0  mov     rcx, rbx; void *
0x1800590e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800590e8  jmp     short loc_1800590EB
0x1800590ea  int     3; Trap to Debugger
0x1800590eb  mov     rcx, [rsp+88h+var_20]
0x1800590f0  xor     rcx, rsp; StackCookie
0x1800590f3  call    __security_check_cookie
0x1800590f8  lea     r11, [rsp+88h+var_18]
0x1800590fd  mov     rbx, [r11+28h]
0x180059101  mov     rsi, [r11+30h]
0x180059105  mov     rsp, r11
0x180059108  pop     r15
0x18005910a  pop     r14
0x18005910c  pop     rdi
0x18005910d  retn
```
