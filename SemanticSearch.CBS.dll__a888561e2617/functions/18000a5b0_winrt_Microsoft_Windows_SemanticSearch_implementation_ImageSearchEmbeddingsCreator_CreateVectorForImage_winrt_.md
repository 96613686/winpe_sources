# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImage(winrt::Microsoft::Windows::Imaging::ImageBuffer const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x18000a5b0`
- end: `0x18000a70e`
- name: `?CreateVectorForImage@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@AEBUImageBuffer@Imaging@456@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e5b0`

## callees

- `0x18000a5b0`
- `0x18000a710`
- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a6a2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a707`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a6a2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a707`

## string_xrefs

- `0x18000a641`: `CreateVectorForImage`
- `0x18000a6d3`: `CreateVectorForImage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImage(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rax
  const wchar_t *v9; // rbx
  _DWORD *v10; // rcx
  TelemetryLogger *v11; // rax
  void *v12; // rbx
  int v13; // eax
  HANDLE ProcessHeap; // rax
  __int64 v16; // rax
  const wchar_t *v17; // rbx
  int v18; // eax
  LPVOID lpMem[7]; // [rsp+20h] [rbp-38h] BYREF

  lpMem[0] = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&dword_18008668C) == 1 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, lpMem);
      if ( *(_QWORD *)v8 )
        v9 = *(const wchar_t **)(*(_QWORD *)v8 + 16LL);
      else
        v9 = (const wchar_t *)&qword_18006D0D8;
      v10 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
      if ( v10 && *v10 )
      {
        v11 = TelemetryLogger::Instance();
        TelemetryLogger::InitApiData_(v11, v9, L"CreateVectorForImage", &dword_18008668C);
      }
      v12 = lpMem[0];
      if ( lpMem[0] )
      {
        v13 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
        if ( !v13 )
        {
LABEL_11:
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v12);
          goto LABEL_12;
        }
        if ( v13 < 0 )
          abort();
      }
    }
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, lpMem);
    if ( *(_QWORD *)v16 )
      v17 = *(const wchar_t **)(*(_QWORD *)v16 + 16LL);
    else
      v17 = (const wchar_t *)&qword_18006D0D8;
    TelemetryLogger::LogWclApiUsage(v17, L"CreateVectorForImage");
    v12 = lpMem[0];
    if ( lpMem[0] )
    {
      v18 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( !v18 )
        goto LABEL_11;
      if ( v18 < 0 )
        abort();
    }
  }
LABEL_12:
  winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(
    a1,
    (__int64 *)a2,
    a3,
    a4);
  return a2;
}

```

## disassembly

```asm
0x18000a5b0  push    rbx
0x18000a5b2  push    rbp
0x18000a5b3  push    rsi
0x18000a5b4  push    rdi
0x18000a5b5  push    r14
0x18000a5b7  sub     rsp, 30h
0x18000a5bb  mov     r14, r9
0x18000a5be  mov     rbp, r8
0x18000a5c1  mov     rsi, rdx
0x18000a5c4  mov     rdi, rcx
0x18000a5c7  mov     [rsp+58h+lpMem], rdx
0x18000a5cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18000a5d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x18000a5d8  test    al, al
0x18000a5da  jz      loc_18000A6A9
0x18000a5e0  mov     eax, 1
0x18000a5e5  lock xadd cs:dword_18008668C, eax
0x18000a5ed  inc     eax
0x18000a5ef  cmp     eax, 1
0x18000a5f2  jnz     loc_18000A67F
0x18000a5f8  mov     rax, [rdi]
0x18000a5fb  lea     rdx, [rsp+58h+lpMem]
0x18000a600  mov     rcx, rdi
0x18000a603  mov     rax, [rax+28h]
0x18000a607  call    cs:__guard_dispatch_icall_fptr
0x18000a60d  mov     rbx, [rax]
0x18000a610  test    rbx, rbx
0x18000a613  jz      short loc_18000A61B
0x18000a615  mov     rbx, [rbx+10h]
0x18000a619  jmp     short loc_18000A622
0x18000a61b  lea     rbx, qword_18006D0D8
0x18000a622  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000a627  mov     rcx, [rax+8]
0x18000a62b  test    rcx, rcx
0x18000a62e  jz      short loc_18000A654
0x18000a630  cmp     dword ptr [rcx], 0
0x18000a633  jbe     short loc_18000A654
0x18000a635  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000a63a  lea     r9, dword_18008668C; volatile int *
0x18000a641  lea     r8, aCreatevectorfo; "CreateVectorForImage"
0x18000a648  mov     rdx, rbx; wchar_t *
0x18000a64b  mov     rcx, rax; this
0x18000a64e  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18000a653  nop
0x18000a654  mov     rbx, [rsp+58h+lpMem]
0x18000a659  test    rbx, rbx
0x18000a65c  jz      short loc_18000A67F
0x18000a65e  mov     eax, 0FFFFFFFFh
0x18000a663  lock xadd [rbx+18h], eax
0x18000a668  sub     eax, 1
0x18000a66b  jnz     short loc_18000A69E
0x18000a66d  call    WINRT_IMPL_GetProcessHeap
0x18000a672  mov     rcx, rax; hHeap
0x18000a675  mov     r8, rbx; lpMem
0x18000a678  xor     edx, edx; dwFlags
0x18000a67a  call    WINRT_IMPL_HeapFree
0x18000a67f  mov     r9, r14
0x18000a682  mov     r8, rbp
0x18000a685  mov     rdx, rsi
0x18000a688  mov     rcx, rdi
0x18000a68b  call    ?CreateVectorForImageInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUImageBuffer@Imaging@456@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(winrt::Microsoft::Windows::Imaging::ImageBuffer const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x18000a690  mov     rax, rsi
0x18000a693  add     rsp, 30h
0x18000a697  pop     r14
0x18000a699  pop     rdi
0x18000a69a  pop     rsi
0x18000a69b  pop     rbp
0x18000a69c  pop     rbx
0x18000a69d  retn
0x18000a69e  test    eax, eax
0x18000a6a0  jns     short loc_18000A67F
0x18000a6a2  call    cs:__imp_abort
0x18000a6a9  mov     rax, [rdi]
0x18000a6ac  lea     rdx, [rsp+58h+lpMem]
0x18000a6b1  mov     rcx, rdi
0x18000a6b4  mov     rax, [rax+28h]
0x18000a6b8  call    cs:__guard_dispatch_icall_fptr
0x18000a6be  mov     rbx, [rax]
0x18000a6c1  test    rbx, rbx
0x18000a6c4  jz      short loc_18000A6CC
0x18000a6c6  mov     rbx, [rbx+10h]
0x18000a6ca  jmp     short loc_18000A6D3
0x18000a6cc  lea     rbx, qword_18006D0D8
0x18000a6d3  lea     rdx, aCreatevectorfo; "CreateVectorForImage"
0x18000a6da  mov     rcx, rbx; wchar_t *
0x18000a6dd  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18000a6e2  mov     rbx, [rsp+58h+lpMem]
0x18000a6e7  test    rbx, rbx
0x18000a6ea  jz      short loc_18000A67F
0x18000a6ec  mov     eax, 0FFFFFFFFh
0x18000a6f1  lock xadd [rbx+18h], eax
0x18000a6f6  sub     eax, 1
0x18000a6f9  jz      loc_18000A66D
0x18000a6ff  test    eax, eax
0x18000a701  jns     loc_18000A67F
0x18000a707  call    cs:__imp_abort
```
