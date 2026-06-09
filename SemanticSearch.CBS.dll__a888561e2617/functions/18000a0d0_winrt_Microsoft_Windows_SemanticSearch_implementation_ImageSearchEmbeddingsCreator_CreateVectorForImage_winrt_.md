# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImage(winrt::Microsoft::Windows::Imaging::ImageBuffer const &)

- ea: `0x18000a0d0`
- end: `0x18000a238`
- name: `?CreateVectorForImage@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@AEBUImageBuffer@Imaging@456@@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e940`

## callees

- `0x18000a0d0`
- `0x18000a710`
- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a1cc`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a231`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a1cc`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a231`

## string_xrefs

- `0x18000a15f`: `CreateVectorForImage`
- `0x18000a1fd`: `CreateVectorForImage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImage(
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
    if ( _InterlockedIncrement(&dword_18008669C) == 1 )
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
        TelemetryLogger::InitApiData_(v9, v7, L"CreateVectorForImage", &dword_18008669C);
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
    TelemetryLogger::LogWclApiUsage(v15, L"CreateVectorForImage");
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
  winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(
    a1,
    (__int64 *)a2,
    a3,
    (__int64)lpMem);
  return a2;
}

```

## disassembly

```asm
0x18000a0d0  mov     [rsp+arg_18], rbx
0x18000a0d5  push    rbp
0x18000a0d6  push    rsi
0x18000a0d7  push    rdi
0x18000a0d8  sub     rsp, 30h
0x18000a0dc  mov     rbp, r8
0x18000a0df  mov     rdi, rdx
0x18000a0e2  mov     rsi, rcx
0x18000a0e5  mov     [rsp+48h+lpMem], rdx
0x18000a0ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18000a0f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x18000a0f6  test    al, al
0x18000a0f8  jz      loc_18000A1D3
0x18000a0fe  mov     eax, 1
0x18000a103  lock xadd cs:dword_18008669C, eax
0x18000a10b  inc     eax
0x18000a10d  cmp     eax, 1
0x18000a110  jnz     loc_18000A19D
0x18000a116  mov     rax, [rsi]
0x18000a119  lea     rdx, [rsp+48h+lpMem]
0x18000a11e  mov     rcx, rsi
0x18000a121  mov     rax, [rax+28h]
0x18000a125  call    cs:__guard_dispatch_icall_fptr
0x18000a12b  mov     rbx, [rax]
0x18000a12e  test    rbx, rbx
0x18000a131  jz      short loc_18000A139
0x18000a133  mov     rbx, [rbx+10h]
0x18000a137  jmp     short loc_18000A140
0x18000a139  lea     rbx, qword_18006D0D8
0x18000a140  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000a145  mov     rcx, [rax+8]
0x18000a149  test    rcx, rcx
0x18000a14c  jz      short loc_18000A172
0x18000a14e  cmp     dword ptr [rcx], 0
0x18000a151  jbe     short loc_18000A172
0x18000a153  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000a158  lea     r9, dword_18008669C; volatile int *
0x18000a15f  lea     r8, aCreatevectorfo; "CreateVectorForImage"
0x18000a166  mov     rdx, rbx; wchar_t *
0x18000a169  mov     rcx, rax; this
0x18000a16c  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18000a171  nop
0x18000a172  mov     rbx, [rsp+48h+lpMem]
0x18000a177  test    rbx, rbx
0x18000a17a  jz      short loc_18000A19D
0x18000a17c  mov     eax, 0FFFFFFFFh
0x18000a181  lock xadd [rbx+18h], eax
0x18000a186  sub     eax, 1
0x18000a189  jnz     short loc_18000A1C8
0x18000a18b  call    WINRT_IMPL_GetProcessHeap
0x18000a190  mov     rcx, rax; hHeap
0x18000a193  mov     r8, rbx; lpMem
0x18000a196  xor     edx, edx; dwFlags
0x18000a198  call    WINRT_IMPL_HeapFree
0x18000a19d  mov     dword ptr [rsp+48h+lpMem], 0
0x18000a1a5  lea     r9, [rsp+48h+lpMem]
0x18000a1aa  mov     r8, rbp
0x18000a1ad  mov     rdx, rdi
0x18000a1b0  mov     rcx, rsi
0x18000a1b3  call    ?CreateVectorForImageInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUImageBuffer@Imaging@456@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(winrt::Microsoft::Windows::Imaging::ImageBuffer const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x18000a1b8  mov     rax, rdi
0x18000a1bb  mov     rbx, [rsp+48h+arg_18]
0x18000a1c0  add     rsp, 30h
0x18000a1c4  pop     rdi
0x18000a1c5  pop     rsi
0x18000a1c6  pop     rbp
0x18000a1c7  retn
0x18000a1c8  test    eax, eax
0x18000a1ca  jns     short loc_18000A19D
0x18000a1cc  call    cs:__imp_abort
0x18000a1d3  mov     rax, [rsi]
0x18000a1d6  lea     rdx, [rsp+48h+lpMem]
0x18000a1db  mov     rcx, rsi
0x18000a1de  mov     rax, [rax+28h]
0x18000a1e2  call    cs:__guard_dispatch_icall_fptr
0x18000a1e8  mov     rbx, [rax]
0x18000a1eb  test    rbx, rbx
0x18000a1ee  jz      short loc_18000A1F6
0x18000a1f0  mov     rbx, [rbx+10h]
0x18000a1f4  jmp     short loc_18000A1FD
0x18000a1f6  lea     rbx, qword_18006D0D8
0x18000a1fd  lea     rdx, aCreatevectorfo; "CreateVectorForImage"
0x18000a204  mov     rcx, rbx; wchar_t *
0x18000a207  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18000a20c  mov     rbx, [rsp+48h+lpMem]
0x18000a211  test    rbx, rbx
0x18000a214  jz      short loc_18000A19D
0x18000a216  mov     eax, 0FFFFFFFFh
0x18000a21b  lock xadd [rbx+18h], eax
0x18000a220  sub     eax, 1
0x18000a223  jz      loc_18000A18B
0x18000a229  test    eax, eax
0x18000a22b  jns     loc_18000A19D
0x18000a231  call    cs:__imp_abort
```
