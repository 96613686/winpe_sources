# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokens(winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x180034290`
- end: `0x1800343f9`
- name: `?CreateVectorFromTokens@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180035850`

## callees

- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180034290`
- `0x180034400`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003438d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800343f2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003438d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800343f2`

## string_xrefs

- `0x180034321`: `CreateVectorFromTokens`
- `0x1800343be`: `CreateVectorFromTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokens(
        __int64 a1,
        void *a2,
        _OWORD *a3)
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
  LPVOID lpMem[9]; // [rsp+20h] [rbp-48h] BYREF

  lpMem[0] = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&dword_180086A10) == 1 )
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
        TelemetryLogger::InitApiData_(v9, v7, L"CreateVectorFromTokens", &dword_180086A10);
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
  *(_OWORD *)lpMem = *a3;
  winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(
    a1,
    a2);
  return a2;
}

```

## disassembly

```asm
0x180034290  push    rbx
0x180034292  push    rbp
0x180034293  push    rsi
0x180034294  push    rdi
0x180034295  push    r14
0x180034297  sub     rsp, 40h
0x18003429b  mov     r14, r9
0x18003429e  mov     rbp, r8
0x1800342a1  mov     rsi, rdx
0x1800342a4  mov     rdi, rcx
0x1800342a7  mov     [rsp+68h+lpMem], rdx
0x1800342ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x1800342b3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x1800342b8  test    al, al
0x1800342ba  jz      loc_180034394
0x1800342c0  mov     eax, 1
0x1800342c5  lock xadd cs:dword_180086A10, eax
0x1800342cd  inc     eax
0x1800342cf  cmp     eax, 1
0x1800342d2  jnz     loc_18003435F
0x1800342d8  mov     rax, [rdi]
0x1800342db  lea     rdx, [rsp+68h+lpMem]
0x1800342e0  mov     rcx, rdi
0x1800342e3  mov     rax, [rax+28h]
0x1800342e7  call    cs:__guard_dispatch_icall_fptr
0x1800342ed  mov     rbx, [rax]
0x1800342f0  test    rbx, rbx
0x1800342f3  jz      short loc_1800342FB
0x1800342f5  mov     rbx, [rbx+10h]
0x1800342f9  jmp     short loc_180034302
0x1800342fb  lea     rbx, qword_18006D0D8
0x180034302  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180034307  mov     rcx, [rax+8]
0x18003430b  test    rcx, rcx
0x18003430e  jz      short loc_180034334
0x180034310  cmp     dword ptr [rcx], 0
0x180034313  jbe     short loc_180034334
0x180034315  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18003431a  lea     r9, dword_180086A10; volatile int *
0x180034321  lea     r8, aCreatevectorfr_0; "CreateVectorFromTokens"
0x180034328  mov     rdx, rbx; wchar_t *
0x18003432b  mov     rcx, rax; this
0x18003432e  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180034333  nop
0x180034334  mov     rbx, [rsp+68h+lpMem]
0x180034339  test    rbx, rbx
0x18003433c  jz      short loc_18003435F
0x18003433e  mov     eax, 0FFFFFFFFh
0x180034343  lock xadd [rbx+18h], eax
0x180034348  sub     eax, 1
0x18003434b  jnz     short loc_180034389
0x18003434d  call    WINRT_IMPL_GetProcessHeap
0x180034352  mov     rcx, rax; hHeap
0x180034355  mov     r8, rbx; lpMem
0x180034358  xor     edx, edx; dwFlags
0x18003435a  call    WINRT_IMPL_HeapFree
0x18003435f  movups  xmm0, xmmword ptr [rbp+0]
0x180034363  movaps  xmmword ptr [rsp+68h+lpMem], xmm0
0x180034368  mov     r9, r14
0x18003436b  lea     r8, [rsp+68h+lpMem]
0x180034370  mov     rdx, rsi
0x180034373  mov     rcx, rdi
0x180034376  call    ?CreateVectorFromTokensInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorFromTokensInternal(winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x18003437b  mov     rax, rsi
0x18003437e  add     rsp, 40h
0x180034382  pop     r14
0x180034384  pop     rdi
0x180034385  pop     rsi
0x180034386  pop     rbp
0x180034387  pop     rbx
0x180034388  retn
0x180034389  test    eax, eax
0x18003438b  jns     short loc_18003435F
0x18003438d  call    cs:__imp_abort
0x180034394  mov     rax, [rdi]
0x180034397  lea     rdx, [rsp+68h+lpMem]
0x18003439c  mov     rcx, rdi
0x18003439f  mov     rax, [rax+28h]
0x1800343a3  call    cs:__guard_dispatch_icall_fptr
0x1800343a9  mov     rbx, [rax]
0x1800343ac  test    rbx, rbx
0x1800343af  jz      short loc_1800343B7
0x1800343b1  mov     rbx, [rbx+10h]
0x1800343b5  jmp     short loc_1800343BE
0x1800343b7  lea     rbx, qword_18006D0D8
0x1800343be  lea     rdx, aCreatevectorfr_0; "CreateVectorFromTokens"
0x1800343c5  mov     rcx, rbx; wchar_t *
0x1800343c8  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x1800343cd  mov     rbx, [rsp+68h+lpMem]
0x1800343d2  test    rbx, rbx
0x1800343d5  jz      short loc_18003435F
0x1800343d7  mov     eax, 0FFFFFFFFh
0x1800343dc  lock xadd [rbx+18h], eax
0x1800343e1  sub     eax, 1
0x1800343e4  jz      loc_18003434D
0x1800343ea  test    eax, eax
0x1800343ec  jns     loc_18003435F
0x1800343f2  call    cs:__imp_abort
```
