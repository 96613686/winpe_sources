# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextAsync$_ResumeCoro$1_0

- ea: `0x1800528b0`
- end: `0x180052c78`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextAsync$_ResumeCoro$1_0`
- size: `968`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000aca0`
- `0x1800524d0`

## callees

- `0x180002bb0`
- `0x180009fa0`
- `0x18000afa0`
- `0x18000d050`
- `0x180010000`
- `0x180010230`
- `0x180014100`
- `0x180014540`
- `0x180014840`
- `0x180015090`
- `0x1800151a0`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x180051379`
- `0x18005137f`
- `0x1800528b0`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800529e8`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052a53`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052c0c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800529e8`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052a53`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052c0c`

## string_xrefs

- `0x180052998`: `CreateVectorForTextAsync`
- `0x180052a1f`: `CreateVectorForTextAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextAsync__ResumeCoro_1_0(
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
  char *VectorForTextInternal; // rsi
  _QWORD *v15; // rdi
  __int64 v16; // rax
  volatile signed __int32 *v17; // rdi
  int v18; // ecx
  HANDLE v19; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v21; // [rsp+58h] [rbp-30h]

  v2 = a1 + 160;
  switch ( *((_WORD *)a1 + 80) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_42;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&dword_180086688) == 1 )
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
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorForTextAsync", &dword_180086688);
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
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorForTextAsync");
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
      *((_QWORD *)a1 + 30) = v11;
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
      a1[192] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 54) = 3980;
        *((_QWORD *)a1 + 28) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 216));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      VectorForTextInternal = (char *)winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(
                                        *((_QWORD *)a1 + 30),
                                        a1 + 200,
                                        a1 + 144);
      v15 = a1 + 120;
      if ( a1 + 120 != VectorForTextInternal )
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v16 = *(_QWORD *)VectorForTextInternal;
        *(_QWORD *)VectorForTextInternal = 0;
        *v15 = v16;
      }
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
      v21 = *((_QWORD *)a1 + 23);
      if ( v21 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 26) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 26) )
        goto LABEL_42;
      return;
    case 5:
      v21 = *((_QWORD *)a1 + 23);
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
0x1800528b0  mov     r11, rsp
0x1800528b3  mov     [r11+10h], rbx
0x1800528b7  mov     [r11+18h], rsi
0x1800528bb  mov     [r11+8], rcx
0x1800528bf  push    rdi
0x1800528c0  push    r14
0x1800528c2  push    r15
0x1800528c4  sub     rsp, 70h
0x1800528c8  mov     rax, cs:__security_cookie
0x1800528cf  xor     rax, rsp
0x1800528d2  mov     [rsp+88h+var_20], rax
0x1800528d7  mov     rbx, rcx
0x1800528da  mov     [rsp+88h+var_60], rcx
0x1800528df  lea     r15, [rbx+0A0h]
0x1800528e6  mov     [rsp+88h+var_50], r15
0x1800528eb  movzx   eax, word ptr [r15]
0x1800528ef  mov     [rsp+88h+var_68], ax
0x1800528f4  inc     ax; switch 7 cases
0x1800528f7  cmp     ax, 6
0x1800528fb  ja      def_180052916; jumptable 0000000180052916 default case, case 0
0x180052901  movsx   rax, ax
0x180052905  lea     rdx, cs:180000000h
0x18005290c  mov     ecx, ds:(jpt_180052916 - 180000000h)[rdx+rax*4]
0x180052913  add     rcx, rdx
0x180052916  jmp     rcx; switch jump
0x180052918  jmp     loc_180052BD0; jumptable 0000000180052916 case 3
0x18005291d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 0000000180052916 case 2
0x180052924  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180052929  test    al, al
0x18005292b  jz      loc_1800529EF
0x180052931  mov     eax, 1
0x180052936  lock xadd cs:dword_180086688, eax
0x18005293e  inc     eax
0x180052940  cmp     eax, 1
0x180052943  jnz     loc_180052A5A
0x180052949  mov     rcx, [rbx+88h]
0x180052950  mov     rax, [rcx]
0x180052953  lea     rdx, [rbx+0A8h]
0x18005295a  mov     rax, [rax+28h]
0x18005295e  call    cs:__guard_dispatch_icall_fptr
0x180052964  mov     rdi, [rax]
0x180052967  test    rdi, rdi
0x18005296a  jz      short loc_180052972
0x18005296c  mov     rdi, [rdi+10h]
0x180052970  jmp     short loc_180052979
0x180052972  lea     rdi, qword_18006D0D8
0x180052979  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18005297e  mov     rcx, [rax+8]
0x180052982  test    rcx, rcx
0x180052985  jz      short loc_1800529AB
0x180052987  cmp     dword ptr [rcx], 0
0x18005298a  jbe     short loc_1800529AB
0x18005298c  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180052991  lea     r9, dword_180086688; volatile int *
0x180052998  lea     r8, aCreatevectorfo_1; "CreateVectorForTextAsync"
0x18005299f  mov     rdx, rdi; wchar_t *
0x1800529a2  mov     rcx, rax; this
0x1800529a5  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x1800529aa  nop
0x1800529ab  mov     rdi, [rbx+0A8h]
0x1800529b2  cmp     rdi, 0
0x1800529b6  jz      loc_180052A5A
0x1800529bc  mov     [rsp+88h+var_58], rdi
0x1800529c1  mov     ecx, 0FFFFFFFFh
0x1800529c6  lock xadd [rdi+18h], ecx
0x1800529cb  sub     ecx, 1
0x1800529ce  jnz     short loc_1800529E4
0x1800529d0  call    WINRT_IMPL_GetProcessHeap
0x1800529d5  mov     rcx, rax; hHeap
0x1800529d8  mov     r8, rdi; lpMem
0x1800529db  xor     edx, edx; dwFlags
0x1800529dd  call    WINRT_IMPL_HeapFree
0x1800529e2  jmp     short loc_180052A5A
0x1800529e4  test    ecx, ecx
0x1800529e6  jns     short loc_180052A5A
0x1800529e8  call    cs:__imp_abort
0x1800529ef  mov     rcx, [rbx+88h]
0x1800529f6  mov     rax, [rcx]
0x1800529f9  lea     rdx, [rbx+0B0h]
0x180052a00  mov     rax, [rax+28h]
0x180052a04  call    cs:__guard_dispatch_icall_fptr
0x180052a0a  mov     rdi, [rax]
0x180052a0d  test    rdi, rdi
0x180052a10  jz      short loc_180052A18
0x180052a12  mov     rdi, [rdi+10h]
0x180052a16  jmp     short loc_180052A1F
0x180052a18  lea     rdi, qword_18006D0D8
0x180052a1f  lea     rdx, aCreatevectorfo_1; "CreateVectorForTextAsync"
0x180052a26  mov     rcx, rdi; wchar_t *
0x180052a29  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180052a2e  mov     rdi, [rbx+0B0h]
0x180052a35  cmp     rdi, 0
0x180052a39  jz      short loc_180052A5A
0x180052a3b  mov     [rsp+88h+var_58], rdi
0x180052a40  mov     ecx, 0FFFFFFFFh
0x180052a45  lock xadd [rdi+18h], ecx
0x180052a4a  sub     ecx, 1
0x180052a4d  jz      short loc_1800529D0
0x180052a4f  test    ecx, ecx
0x180052a51  jns     short loc_180052A5A
0x180052a53  call    cs:__imp_abort
0x180052a5a  mov     rdx, [rbx+88h]
0x180052a61  mov     [rbx+0F0h], rdx
0x180052a68  mov     qword ptr [rbx+0B8h], 0
0x180052a73  test    rdx, rdx
0x180052a76  jz      short loc_180052AA6
0x180052a78  mov     [rbx+0B8h], rdx
0x180052a7f  mov     rax, [rdx+8]
0x180052a83  test    rax, rax
0x180052a86  js      short loc_180052AA1
0x180052a88  nop     dword ptr [rax+rax+00000000h]
0x180052a90  lea     rcx, [rax+1]
0x180052a94  lock cmpxchg [rdx+8], rcx
0x180052a9a  jz      short loc_180052AA6
0x180052a9c  test    rax, rax
0x180052a9f  jns     short loc_180052A90
0x180052aa1  lock inc dword ptr [rax+rax+18h]
0x180052aa6  mov     byte ptr [rbx+0C0h], 0
0x180052aad  mov     eax, [rbx+70h]
0x180052ab0  cmp     eax, 2
0x180052ab3  jnz     short loc_180052AEB
0x180052ab5  lea     rdx, [rbx+0D8h]; struct winrt::impl::slim_source_location *
0x180052abc  mov     dword ptr [rdx], 0F8Ch
0x180052ac2  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180052ac9  mov     [rbx+0E0h], rax
0x180052ad0  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180052ad5  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180052ada  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180052ae1  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180052ae6  call    _CxxThrowException
0x180052aeb  mov     eax, 4
0x180052af0  mov     [r15], ax
0x180052af4  mov     rdx, rbx
0x180052af7  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180052afc  jmp     loc_180052C38
0x180052b01  lea     rcx, [rbx+0B8h]; jumptable 0000000180052916 case 5
0x180052b08  mov     rax, [rcx]
0x180052b0b  mov     [rsp+88h+var_30], rax
0x180052b10  test    rax, rax
0x180052b13  jz      short loc_180052B1B
0x180052b15  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180052b1a  nop
0x180052b1b  jmp     loc_180052BD0; jumptable 0000000180052916 cases -1,1
0x180052b20  lea     r9, [rbx+98h]; jumptable 0000000180052916 case 4
0x180052b27  lea     r8, [rbx+90h]
0x180052b2e  lea     rdx, [rbx+0C8h]
0x180052b35  mov     rcx, [rbx+0F0h]
0x180052b3c  call    ?CreateVectorForTextInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180052b41  mov     rsi, rax
0x180052b44  lea     rdi, [rbx+78h]
0x180052b48  cmp     rdi, rax
0x180052b4b  jz      short loc_180052B68
0x180052b4d  cmp     qword ptr [rdi], 0
0x180052b51  jz      short loc_180052B5B
0x180052b53  mov     rcx, rdi
0x180052b56  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180052b5b  mov     rax, [rsi]
0x180052b5e  mov     qword ptr [rsi], 0
0x180052b65  mov     [rdi], rax
0x180052b68  mov     rax, [rbx+0C8h]
0x180052b6f  mov     [rsp+88h+var_58], rax
0x180052b74  test    rax, rax
0x180052b77  jz      short loc_180052B86
0x180052b79  lea     rcx, [rbx+0C8h]
0x180052b80  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180052b85  nop
0x180052b86  lea     rcx, [rbx+0B8h]
0x180052b8d  mov     rax, [rcx]
0x180052b90  mov     [rsp+88h+var_30], rax
0x180052b95  test    rax, rax
0x180052b98  jz      short loc_180052BA0
0x180052b9a  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180052b9f  nop
0x180052ba0  jmp     short loc_180052BAC
0x180052ba2  mov     r15, [rsp+88h+var_50]
0x180052ba7  mov     rbx, [rsp+88h+var_60]
0x180052bac  lea     rax, [rbx+10h]
0x180052bb0  lea     rcx, [rbx+0D0h]
0x180052bb7  mov     [rcx], rax
0x180052bba  xor     eax, eax
0x180052bbc  mov     [r15], ax
0x180052bc0  mov     [rbx], rax
0x180052bc3  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180052bc8  test    al, al
0x180052bca  jnz     short loc_180052C38
0x180052bcc  nop     dword ptr [rax+00h]
0x180052bd0  lea     rcx, [rbx+10h]; jumptable 0000000180052916 cases -1,1
0x180052bd4  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x180052bd9  mov     rdi, [rbx+90h]
0x180052be0  test    rdi, rdi
0x180052be3  jz      short loc_180052C1E
0x180052be5  mov     ecx, 0FFFFFFFFh
0x180052bea  lock xadd [rdi+18h], ecx
0x180052bef  sub     ecx, 1
0x180052bf2  jnz     short loc_180052C08
0x180052bf4  call    WINRT_IMPL_GetProcessHeap
0x180052bf9  mov     rcx, rax; hHeap
0x180052bfc  mov     r8, rdi; lpMem
0x180052bff  xor     edx, edx; dwFlags
0x180052c01  call    WINRT_IMPL_HeapFree
0x180052c06  jmp     short loc_180052C13
0x180052c08  test    ecx, ecx
0x180052c0a  jns     short loc_180052C13
0x180052c0c  call    cs:__imp_abort
0x180052c13  mov     qword ptr [rbx+90h], 0
0x180052c1e  cmp     word ptr [rbx+0A2h], 0
0x180052c26  jz      short loc_180052C38
0x180052c28  mov     edx, 100h; unsigned __int64
0x180052c2d  mov     rcx, rbx; void *
0x180052c30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180052c35  jmp     short loc_180052C38
0x180052c37  int     3; Trap to Debugger
0x180052c38  mov     rcx, [rsp+88h+var_20]
0x180052c3d  xor     rcx, rsp; StackCookie
0x180052c40  call    __security_check_cookie
0x180052c45  lea     r11, [rsp+88h+var_18]
0x180052c4a  mov     rbx, [r11+28h]
0x180052c4e  mov     rsi, [r11+30h]
0x180052c52  mov     rsp, r11
0x180052c55  pop     r15
0x180052c57  pop     r14
0x180052c59  pop     rdi
0x180052c5a  retn
```
