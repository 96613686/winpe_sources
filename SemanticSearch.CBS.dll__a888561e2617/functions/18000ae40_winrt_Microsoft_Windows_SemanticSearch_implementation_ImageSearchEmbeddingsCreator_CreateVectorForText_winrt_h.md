# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForText(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x18000ae40`
- end: `0x18000af9e`
- name: `?CreateVectorForText@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e480`

## callees

- `0x18000ae40`
- `0x18000afa0`
- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000af32`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000af97`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000af32`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000af97`

## string_xrefs

- `0x18000aed1`: `CreateVectorForText`
- `0x18000af63`: `CreateVectorForText`

## pseudocode

```c
void *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForText(
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
    if ( _InterlockedIncrement(&dword_180086684) == 1 )
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
        TelemetryLogger::InitApiData_(v9, v7, L"CreateVectorForText", &dword_180086684);
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
    TelemetryLogger::LogWclApiUsage(v15, L"CreateVectorForText");
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
  winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(
    a1,
    a2,
    a3);
  return a2;
}

```

## disassembly

```asm
0x18000ae40  push    rbx
0x18000ae42  push    rbp
0x18000ae43  push    rsi
0x18000ae44  push    rdi
0x18000ae45  push    r14
0x18000ae47  sub     rsp, 30h
0x18000ae4b  mov     r14, r9
0x18000ae4e  mov     rbp, r8
0x18000ae51  mov     rsi, rdx
0x18000ae54  mov     rdi, rcx
0x18000ae57  mov     [rsp+58h+lpMem], rdx
0x18000ae5c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18000ae63  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x18000ae68  test    al, al
0x18000ae6a  jz      loc_18000AF39
0x18000ae70  mov     eax, 1
0x18000ae75  lock xadd cs:dword_180086684, eax
0x18000ae7d  inc     eax
0x18000ae7f  cmp     eax, 1
0x18000ae82  jnz     loc_18000AF0F
0x18000ae88  mov     rax, [rdi]
0x18000ae8b  lea     rdx, [rsp+58h+lpMem]
0x18000ae90  mov     rcx, rdi
0x18000ae93  mov     rax, [rax+28h]
0x18000ae97  call    cs:__guard_dispatch_icall_fptr
0x18000ae9d  mov     rbx, [rax]
0x18000aea0  test    rbx, rbx
0x18000aea3  jz      short loc_18000AEAB
0x18000aea5  mov     rbx, [rbx+10h]
0x18000aea9  jmp     short loc_18000AEB2
0x18000aeab  lea     rbx, qword_18006D0D8
0x18000aeb2  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000aeb7  mov     rcx, [rax+8]
0x18000aebb  test    rcx, rcx
0x18000aebe  jz      short loc_18000AEE4
0x18000aec0  cmp     dword ptr [rcx], 0
0x18000aec3  jbe     short loc_18000AEE4
0x18000aec5  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000aeca  lea     r9, dword_180086684; volatile int *
0x18000aed1  lea     r8, aCreatevectorfo_0; "CreateVectorForText"
0x18000aed8  mov     rdx, rbx; wchar_t *
0x18000aedb  mov     rcx, rax; this
0x18000aede  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18000aee3  nop
0x18000aee4  mov     rbx, [rsp+58h+lpMem]
0x18000aee9  test    rbx, rbx
0x18000aeec  jz      short loc_18000AF0F
0x18000aeee  mov     eax, 0FFFFFFFFh
0x18000aef3  lock xadd [rbx+18h], eax
0x18000aef8  sub     eax, 1
0x18000aefb  jnz     short loc_18000AF2E
0x18000aefd  call    WINRT_IMPL_GetProcessHeap
0x18000af02  mov     rcx, rax; hHeap
0x18000af05  mov     r8, rbx; lpMem
0x18000af08  xor     edx, edx; dwFlags
0x18000af0a  call    WINRT_IMPL_HeapFree
0x18000af0f  mov     r9, r14
0x18000af12  mov     r8, rbp
0x18000af15  mov     rdx, rsi
0x18000af18  mov     rcx, rdi
0x18000af1b  call    ?CreateVectorForTextInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x18000af20  mov     rax, rsi
0x18000af23  add     rsp, 30h
0x18000af27  pop     r14
0x18000af29  pop     rdi
0x18000af2a  pop     rsi
0x18000af2b  pop     rbp
0x18000af2c  pop     rbx
0x18000af2d  retn
0x18000af2e  test    eax, eax
0x18000af30  jns     short loc_18000AF0F
0x18000af32  call    cs:__imp_abort
0x18000af39  mov     rax, [rdi]
0x18000af3c  lea     rdx, [rsp+58h+lpMem]
0x18000af41  mov     rcx, rdi
0x18000af44  mov     rax, [rax+28h]
0x18000af48  call    cs:__guard_dispatch_icall_fptr
0x18000af4e  mov     rbx, [rax]
0x18000af51  test    rbx, rbx
0x18000af54  jz      short loc_18000AF5C
0x18000af56  mov     rbx, [rbx+10h]
0x18000af5a  jmp     short loc_18000AF63
0x18000af5c  lea     rbx, qword_18006D0D8
0x18000af63  lea     rdx, aCreatevectorfo_0; "CreateVectorForText"
0x18000af6a  mov     rcx, rbx; wchar_t *
0x18000af6d  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18000af72  mov     rbx, [rsp+58h+lpMem]
0x18000af77  test    rbx, rbx
0x18000af7a  jz      short loc_18000AF0F
0x18000af7c  mov     eax, 0FFFFFFFFh
0x18000af81  lock xadd [rbx+18h], eax
0x18000af86  sub     eax, 1
0x18000af89  jz      loc_18000AEFD
0x18000af8f  test    eax, eax
0x18000af91  jns     loc_18000AF0F
0x18000af97  call    cs:__imp_abort
```
