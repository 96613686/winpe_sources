# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVector(winrt::hstring const &)

- ea: `0x180033980`
- end: `0x180033ae8`
- name: `?CreateVector@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@AEBUhstring@6@@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180035c90`

## callees

- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180033980`
- `0x180033f70`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033a7c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033ae1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033a7c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180033ae1`

## string_xrefs

- `0x180033a0f`: `CreateVector`
- `0x180033aad`: `CreateVector`

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
  LPVOID lpMem[5]; // [rsp+20h] [rbp-28h] BYREF

  lpMem[0] = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&dword_180086A28) == 1 )
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
        TelemetryLogger::InitApiData_(v9, v7, L"CreateVector", &dword_180086A28);
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
  LODWORD(lpMem[0]) = 0;
  winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(
    a1,
    a2,
    a3);
  return a2;
}

```

## disassembly

```asm
0x180033980  mov     [rsp+arg_18], rbx
0x180033985  push    rbp
0x180033986  push    rsi
0x180033987  push    rdi
0x180033988  sub     rsp, 30h
0x18003398c  mov     rbp, r8
0x18003398f  mov     rdi, rdx
0x180033992  mov     rsi, rcx
0x180033995  mov     [rsp+48h+lpMem], rdx
0x18003399a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x1800339a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x1800339a6  test    al, al
0x1800339a8  jz      loc_180033A83
0x1800339ae  mov     eax, 1
0x1800339b3  lock xadd cs:dword_180086A28, eax
0x1800339bb  inc     eax
0x1800339bd  cmp     eax, 1
0x1800339c0  jnz     loc_180033A4D
0x1800339c6  mov     rax, [rsi]
0x1800339c9  lea     rdx, [rsp+48h+lpMem]
0x1800339ce  mov     rcx, rsi
0x1800339d1  mov     rax, [rax+28h]
0x1800339d5  call    cs:__guard_dispatch_icall_fptr
0x1800339db  mov     rbx, [rax]
0x1800339de  test    rbx, rbx
0x1800339e1  jz      short loc_1800339E9
0x1800339e3  mov     rbx, [rbx+10h]
0x1800339e7  jmp     short loc_1800339F0
0x1800339e9  lea     rbx, qword_18006D0D8
0x1800339f0  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800339f5  mov     rcx, [rax+8]
0x1800339f9  test    rcx, rcx
0x1800339fc  jz      short loc_180033A22
0x1800339fe  cmp     dword ptr [rcx], 0
0x180033a01  jbe     short loc_180033A22
0x180033a03  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180033a08  lea     r9, dword_180086A28; volatile int *
0x180033a0f  lea     r8, aCreatevector; "CreateVector"
0x180033a16  mov     rdx, rbx; wchar_t *
0x180033a19  mov     rcx, rax; this
0x180033a1c  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180033a21  nop
0x180033a22  mov     rbx, [rsp+48h+lpMem]
0x180033a27  test    rbx, rbx
0x180033a2a  jz      short loc_180033A4D
0x180033a2c  mov     eax, 0FFFFFFFFh
0x180033a31  lock xadd [rbx+18h], eax
0x180033a36  sub     eax, 1
0x180033a39  jnz     short loc_180033A78
0x180033a3b  call    WINRT_IMPL_GetProcessHeap
0x180033a40  mov     rcx, rax; hHeap
0x180033a43  mov     r8, rbx; lpMem
0x180033a46  xor     edx, edx; dwFlags
0x180033a48  call    WINRT_IMPL_HeapFree
0x180033a4d  mov     dword ptr [rsp+48h+lpMem], 0
0x180033a55  lea     r9, [rsp+48h+lpMem]
0x180033a5a  mov     r8, rbp
0x180033a5d  mov     rdx, rdi
0x180033a60  mov     rcx, rsi
0x180033a63  call    ?CreateVectorInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180033a68  mov     rax, rdi
0x180033a6b  mov     rbx, [rsp+48h+arg_18]
0x180033a70  add     rsp, 30h
0x180033a74  pop     rdi
0x180033a75  pop     rsi
0x180033a76  pop     rbp
0x180033a77  retn
0x180033a78  test    eax, eax
0x180033a7a  jns     short loc_180033A4D
0x180033a7c  call    cs:__imp_abort
0x180033a83  mov     rax, [rsi]
0x180033a86  lea     rdx, [rsp+48h+lpMem]
0x180033a8b  mov     rcx, rsi
0x180033a8e  mov     rax, [rax+28h]
0x180033a92  call    cs:__guard_dispatch_icall_fptr
0x180033a98  mov     rbx, [rax]
0x180033a9b  test    rbx, rbx
0x180033a9e  jz      short loc_180033AA6
0x180033aa0  mov     rbx, [rbx+10h]
0x180033aa4  jmp     short loc_180033AAD
0x180033aa6  lea     rbx, qword_18006D0D8
0x180033aad  lea     rdx, aCreatevector; "CreateVector"
0x180033ab4  mov     rcx, rbx; wchar_t *
0x180033ab7  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180033abc  mov     rbx, [rsp+48h+lpMem]
0x180033ac1  test    rbx, rbx
0x180033ac4  jz      short loc_180033A4D
0x180033ac6  mov     eax, 0FFFFFFFFh
0x180033acb  lock xadd [rbx+18h], eax
0x180033ad0  sub     eax, 1
0x180033ad3  jz      loc_180033A3B
0x180033ad9  test    eax, eax
0x180033adb  jns     loc_180033A4D
0x180033ae1  call    cs:__imp_abort
```
