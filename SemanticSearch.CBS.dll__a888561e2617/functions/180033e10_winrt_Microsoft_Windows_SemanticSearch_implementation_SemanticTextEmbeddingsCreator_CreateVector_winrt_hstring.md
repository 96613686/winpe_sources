# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVector(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x180033e10`
- end: `0x180033f6e`
- name: `?CreateVector@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800358f0`

## callees

- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180033e10`
- `0x180033f70`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033f02`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033f67`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033f02`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033f67`

## string_xrefs

- `0x180033ea1`: `CreateVector`
- `0x180033f33`: `CreateVector`

## pseudocode

```c
void *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVector(
        __int64 a1,
        void *a2,
        __int64 a3)
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
  LPVOID lpMem[7]; // [rsp+20h] [rbp-38h] BYREF

  lpMem[0] = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&dword_180086A18) == 1 )
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
        TelemetryLogger::InitApiData_(v9, v7, L"CreateVector", &dword_180086A18);
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
    TelemetryLogger::LogWclApiUsage(v15, L"CreateVector");
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
  winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(
    a1,
    a2,
    a3);
  return a2;
}

```

## disassembly

```asm
0x180033e10  push    rbx
0x180033e12  push    rbp
0x180033e13  push    rsi
0x180033e14  push    rdi
0x180033e15  push    r14
0x180033e17  sub     rsp, 30h
0x180033e1b  mov     r14, r9
0x180033e1e  mov     rbp, r8
0x180033e21  mov     rsi, rdx
0x180033e24  mov     rdi, rcx
0x180033e27  mov     [rsp+58h+lpMem], rdx
0x180033e2c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x180033e33  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180033e38  test    al, al
0x180033e3a  jz      loc_180033F09
0x180033e40  mov     eax, 1
0x180033e45  lock xadd cs:dword_180086A18, eax
0x180033e4d  inc     eax
0x180033e4f  cmp     eax, 1
0x180033e52  jnz     loc_180033EDF
0x180033e58  mov     rax, [rdi]
0x180033e5b  lea     rdx, [rsp+58h+lpMem]
0x180033e60  mov     rcx, rdi
0x180033e63  mov     rax, [rax+28h]
0x180033e67  call    cs:__guard_dispatch_icall_fptr
0x180033e6d  mov     rbx, [rax]
0x180033e70  test    rbx, rbx
0x180033e73  jz      short loc_180033E7B
0x180033e75  mov     rbx, [rbx+10h]
0x180033e79  jmp     short loc_180033E82
0x180033e7b  lea     rbx, qword_18006D0D8
0x180033e82  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180033e87  mov     rcx, [rax+8]
0x180033e8b  test    rcx, rcx
0x180033e8e  jz      short loc_180033EB4
0x180033e90  cmp     dword ptr [rcx], 0
0x180033e93  jbe     short loc_180033EB4
0x180033e95  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180033e9a  lea     r9, dword_180086A18; volatile int *
0x180033ea1  lea     r8, aCreatevector; "CreateVector"
0x180033ea8  mov     rdx, rbx; wchar_t *
0x180033eab  mov     rcx, rax; this
0x180033eae  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180033eb3  nop
0x180033eb4  mov     rbx, [rsp+58h+lpMem]
0x180033eb9  test    rbx, rbx
0x180033ebc  jz      short loc_180033EDF
0x180033ebe  mov     eax, 0FFFFFFFFh
0x180033ec3  lock xadd [rbx+18h], eax
0x180033ec8  sub     eax, 1
0x180033ecb  jnz     short loc_180033EFE
0x180033ecd  call    WINRT_IMPL_GetProcessHeap
0x180033ed2  mov     rcx, rax; hHeap
0x180033ed5  mov     r8, rbx; lpMem
0x180033ed8  xor     edx, edx; dwFlags
0x180033eda  call    WINRT_IMPL_HeapFree
0x180033edf  mov     r9, r14
0x180033ee2  mov     r8, rbp
0x180033ee5  mov     rdx, rsi
0x180033ee8  mov     rcx, rdi
0x180033eeb  call    ?CreateVectorInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180033ef0  mov     rax, rsi
0x180033ef3  add     rsp, 30h
0x180033ef7  pop     r14
0x180033ef9  pop     rdi
0x180033efa  pop     rsi
0x180033efb  pop     rbp
0x180033efc  pop     rbx
0x180033efd  retn
0x180033efe  test    eax, eax
0x180033f00  jns     short loc_180033EDF
0x180033f02  call    cs:__imp_abort
0x180033f09  mov     rax, [rdi]
0x180033f0c  lea     rdx, [rsp+58h+lpMem]
0x180033f11  mov     rcx, rdi
0x180033f14  mov     rax, [rax+28h]
0x180033f18  call    cs:__guard_dispatch_icall_fptr
0x180033f1e  mov     rbx, [rax]
0x180033f21  test    rbx, rbx
0x180033f24  jz      short loc_180033F2C
0x180033f26  mov     rbx, [rbx+10h]
0x180033f2a  jmp     short loc_180033F33
0x180033f2c  lea     rbx, qword_18006D0D8
0x180033f33  lea     rdx, aCreatevector; "CreateVector"
0x180033f3a  mov     rcx, rbx; wchar_t *
0x180033f3d  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180033f42  mov     rbx, [rsp+58h+lpMem]
0x180033f47  test    rbx, rbx
0x180033f4a  jz      short loc_180033EDF
0x180033f4c  mov     eax, 0FFFFFFFFh
0x180033f51  lock xadd [rbx+18h], eax
0x180033f56  sub     eax, 1
0x180033f59  jz      loc_180033ECD
0x180033f5f  test    eax, eax
0x180033f61  jns     loc_180033EDF
0x180033f67  call    cs:__imp_abort
```
