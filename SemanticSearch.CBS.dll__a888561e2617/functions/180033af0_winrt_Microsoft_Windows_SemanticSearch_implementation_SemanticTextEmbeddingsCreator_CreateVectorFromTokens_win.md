# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokens(winrt::array_view<__int64 const>)

- ea: `0x180033af0`
- end: `0x180033c67`
- name: `?CreateVectorFromTokens@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@@Z`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180035c10`

## callees

- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180033af0`
- `0x180034400`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033bf7`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033c60`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033bf7`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033c60`

## string_xrefs

- `0x180033b7f`: `CreateVectorFromTokens`
- `0x180033c28`: `CreateVectorFromTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokens(
        __int64 a1,
        void *a2,
        __int128 *a3)
{
  __int64 v6; // rax
  const wchar_t *v7; // rbx
  _DWORD *v8; // rcx
  TelemetryLogger *v9; // rax
  void *v10; // rbx
  int v11; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  const wchar_t *v15; // rbx
  int v16; // eax
  LPVOID lpMem[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v18; // [rsp+30h] [rbp-28h]

  lpMem[0] = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&dword_180086A20) == 1 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, lpMem);
      if ( *(_QWORD *)v6 )
        v7 = *(const wchar_t **)(*(_QWORD *)v6 + 16LL);
      else
        v7 = (const wchar_t *)&qword_18006D0D8;
      v8 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
      if ( v8 && *v8 )
      {
        v9 = TelemetryLogger::Instance();
        TelemetryLogger::InitApiData_(v9, v7, L"CreateVectorFromTokens", &dword_180086A20);
      }
      v10 = lpMem[0];
      if ( lpMem[0] )
      {
        v11 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
        if ( !v11 )
        {
LABEL_11:
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v10);
          goto LABEL_12;
        }
        if ( v11 < 0 )
          abort();
      }
    }
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, lpMem);
    if ( *(_QWORD *)v14 )
      v15 = *(const wchar_t **)(*(_QWORD *)v14 + 16LL);
    else
      v15 = (const wchar_t *)&qword_18006D0D8;
    TelemetryLogger::LogWclApiUsage(v15, L"CreateVectorFromTokens");
    v10 = lpMem[0];
    if ( lpMem[0] )
    {
      v16 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( !v16 )
        goto LABEL_11;
      if ( v16 < 0 )
        abort();
    }
  }
LABEL_12:
  LODWORD(lpMem[0]) = 0;
  v18 = *a3;
  winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(
    a1,
    a2);
  return a2;
}

```

## disassembly

```asm
0x180033af0  mov     [rsp+arg_18], rbx
0x180033af5  push    rbp
0x180033af6  push    rsi
0x180033af7  push    rdi
0x180033af8  sub     rsp, 40h
0x180033afc  mov     rbp, r8
0x180033aff  mov     rsi, rdx
0x180033b02  mov     rdi, rcx
0x180033b05  mov     [rsp+58h+lpMem], rdx
0x180033b0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x180033b11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180033b16  test    al, al
0x180033b18  jz      loc_180033BFE
0x180033b1e  mov     eax, 1
0x180033b23  lock xadd cs:dword_180086A20, eax
0x180033b2b  inc     eax
0x180033b2d  cmp     eax, 1
0x180033b30  jnz     loc_180033BBD
0x180033b36  mov     rax, [rdi]
0x180033b39  lea     rdx, [rsp+58h+lpMem]
0x180033b3e  mov     rcx, rdi
0x180033b41  mov     rax, [rax+28h]
0x180033b45  call    cs:__guard_dispatch_icall_fptr
0x180033b4b  mov     rbx, [rax]
0x180033b4e  test    rbx, rbx
0x180033b51  jz      short loc_180033B59
0x180033b53  mov     rbx, [rbx+10h]
0x180033b57  jmp     short loc_180033B60
0x180033b59  lea     rbx, qword_18006D0D8
0x180033b60  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180033b65  mov     rcx, [rax+8]
0x180033b69  test    rcx, rcx
0x180033b6c  jz      short loc_180033B92
0x180033b6e  cmp     dword ptr [rcx], 0
0x180033b71  jbe     short loc_180033B92
0x180033b73  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180033b78  lea     r9, dword_180086A20; volatile int *
0x180033b7f  lea     r8, aCreatevectorfr_0; "CreateVectorFromTokens"
0x180033b86  mov     rdx, rbx; wchar_t *
0x180033b89  mov     rcx, rax; this
0x180033b8c  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180033b91  nop
0x180033b92  mov     rbx, [rsp+58h+lpMem]
0x180033b97  test    rbx, rbx
0x180033b9a  jz      short loc_180033BBD
0x180033b9c  mov     eax, 0FFFFFFFFh
0x180033ba1  lock xadd [rbx+18h], eax
0x180033ba6  sub     eax, 1
0x180033ba9  jnz     short loc_180033BF3
0x180033bab  call    WINRT_IMPL_GetProcessHeap
0x180033bb0  mov     rcx, rax; hHeap
0x180033bb3  mov     r8, rbx; lpMem
0x180033bb6  xor     edx, edx; dwFlags
0x180033bb8  call    WINRT_IMPL_HeapFree
0x180033bbd  mov     dword ptr [rsp+58h+lpMem], 0
0x180033bc5  movups  xmm0, xmmword ptr [rbp+0]
0x180033bc9  movaps  [rsp+58h+var_28], xmm0
0x180033bce  lea     r9, [rsp+58h+lpMem]
0x180033bd3  lea     r8, [rsp+58h+var_28]
0x180033bd8  mov     rdx, rsi
0x180033bdb  mov     rcx, rdi
0x180033bde  call    ?CreateVectorFromTokensInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180033be3  mov     rax, rsi
0x180033be6  mov     rbx, [rsp+58h+arg_18]
0x180033beb  add     rsp, 40h
0x180033bef  pop     rdi
0x180033bf0  pop     rsi
0x180033bf1  pop     rbp
0x180033bf2  retn
0x180033bf3  test    eax, eax
0x180033bf5  jns     short loc_180033BBD
0x180033bf7  call    cs:__imp_abort
0x180033bfe  mov     rax, [rdi]
0x180033c01  lea     rdx, [rsp+58h+lpMem]
0x180033c06  mov     rcx, rdi
0x180033c09  mov     rax, [rax+28h]
0x180033c0d  call    cs:__guard_dispatch_icall_fptr
0x180033c13  mov     rbx, [rax]
0x180033c16  test    rbx, rbx
0x180033c19  jz      short loc_180033C21
0x180033c1b  mov     rbx, [rbx+10h]
0x180033c1f  jmp     short loc_180033C28
0x180033c21  lea     rbx, qword_18006D0D8
0x180033c28  lea     rdx, aCreatevectorfr_0; "CreateVectorFromTokens"
0x180033c2f  mov     rcx, rbx; wchar_t *
0x180033c32  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180033c37  mov     rbx, [rsp+58h+lpMem]
0x180033c3c  test    rbx, rbx
0x180033c3f  jz      loc_180033BBD
0x180033c45  mov     eax, 0FFFFFFFFh
0x180033c4a  lock xadd [rbx+18h], eax
0x180033c4f  sub     eax, 1
0x180033c52  jz      loc_180033BAB
0x180033c58  test    eax, eax
0x180033c5a  jns     loc_180033BBD
0x180033c60  call    cs:__imp_abort
```
