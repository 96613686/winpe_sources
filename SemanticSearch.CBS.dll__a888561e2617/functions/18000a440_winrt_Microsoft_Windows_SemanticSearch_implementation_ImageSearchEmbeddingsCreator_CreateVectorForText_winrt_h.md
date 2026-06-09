# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForText(winrt::hstring const &)

- ea: `0x18000a440`
- end: `0x18000a5a8`
- name: `?CreateVectorForText@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@AEBUhstring@6@@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e830`

## callees

- `0x18000a440`
- `0x18000afa0`
- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a53c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a5a1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a53c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a5a1`

## string_xrefs

- `0x18000a4cf`: `CreateVectorForText`
- `0x18000a56d`: `CreateVectorForText`

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
  LPVOID lpMem[5]; // [rsp+20h] [rbp-28h] BYREF

  lpMem[0] = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&dword_180086694) == 1 )
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
        TelemetryLogger::InitApiData_(v9, v7, L"CreateVectorForText", &dword_180086694);
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
  LODWORD(lpMem[0]) = 0;
  winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(
    a1,
    a2,
    a3);
  return a2;
}

```

## disassembly

```asm
0x18000a440  mov     [rsp+arg_18], rbx
0x18000a445  push    rbp
0x18000a446  push    rsi
0x18000a447  push    rdi
0x18000a448  sub     rsp, 30h
0x18000a44c  mov     rbp, r8
0x18000a44f  mov     rdi, rdx
0x18000a452  mov     rsi, rcx
0x18000a455  mov     [rsp+48h+lpMem], rdx
0x18000a45a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18000a461  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x18000a466  test    al, al
0x18000a468  jz      loc_18000A543
0x18000a46e  mov     eax, 1
0x18000a473  lock xadd cs:dword_180086694, eax
0x18000a47b  inc     eax
0x18000a47d  cmp     eax, 1
0x18000a480  jnz     loc_18000A50D
0x18000a486  mov     rax, [rsi]
0x18000a489  lea     rdx, [rsp+48h+lpMem]
0x18000a48e  mov     rcx, rsi
0x18000a491  mov     rax, [rax+28h]
0x18000a495  call    cs:__guard_dispatch_icall_fptr
0x18000a49b  mov     rbx, [rax]
0x18000a49e  test    rbx, rbx
0x18000a4a1  jz      short loc_18000A4A9
0x18000a4a3  mov     rbx, [rbx+10h]
0x18000a4a7  jmp     short loc_18000A4B0
0x18000a4a9  lea     rbx, qword_18006D0D8
0x18000a4b0  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000a4b5  mov     rcx, [rax+8]
0x18000a4b9  test    rcx, rcx
0x18000a4bc  jz      short loc_18000A4E2
0x18000a4be  cmp     dword ptr [rcx], 0
0x18000a4c1  jbe     short loc_18000A4E2
0x18000a4c3  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000a4c8  lea     r9, dword_180086694; volatile int *
0x18000a4cf  lea     r8, aCreatevectorfo_0; "CreateVectorForText"
0x18000a4d6  mov     rdx, rbx; wchar_t *
0x18000a4d9  mov     rcx, rax; this
0x18000a4dc  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18000a4e1  nop
0x18000a4e2  mov     rbx, [rsp+48h+lpMem]
0x18000a4e7  test    rbx, rbx
0x18000a4ea  jz      short loc_18000A50D
0x18000a4ec  mov     eax, 0FFFFFFFFh
0x18000a4f1  lock xadd [rbx+18h], eax
0x18000a4f6  sub     eax, 1
0x18000a4f9  jnz     short loc_18000A538
0x18000a4fb  call    WINRT_IMPL_GetProcessHeap
0x18000a500  mov     rcx, rax; hHeap
0x18000a503  mov     r8, rbx; lpMem
0x18000a506  xor     edx, edx; dwFlags
0x18000a508  call    WINRT_IMPL_HeapFree
0x18000a50d  mov     dword ptr [rsp+48h+lpMem], 0
0x18000a515  lea     r9, [rsp+48h+lpMem]
0x18000a51a  mov     r8, rbp
0x18000a51d  mov     rdx, rdi
0x18000a520  mov     rcx, rsi
0x18000a523  call    ?CreateVectorForTextInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x18000a528  mov     rax, rdi
0x18000a52b  mov     rbx, [rsp+48h+arg_18]
0x18000a530  add     rsp, 30h
0x18000a534  pop     rdi
0x18000a535  pop     rsi
0x18000a536  pop     rbp
0x18000a537  retn
0x18000a538  test    eax, eax
0x18000a53a  jns     short loc_18000A50D
0x18000a53c  call    cs:__imp_abort
0x18000a543  mov     rax, [rsi]
0x18000a546  lea     rdx, [rsp+48h+lpMem]
0x18000a54b  mov     rcx, rsi
0x18000a54e  mov     rax, [rax+28h]
0x18000a552  call    cs:__guard_dispatch_icall_fptr
0x18000a558  mov     rbx, [rax]
0x18000a55b  test    rbx, rbx
0x18000a55e  jz      short loc_18000A566
0x18000a560  mov     rbx, [rbx+10h]
0x18000a564  jmp     short loc_18000A56D
0x18000a566  lea     rbx, qword_18006D0D8
0x18000a56d  lea     rdx, aCreatevectorfo_0; "CreateVectorForText"
0x18000a574  mov     rcx, rbx; wchar_t *
0x18000a577  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18000a57c  mov     rbx, [rsp+48h+lpMem]
0x18000a581  test    rbx, rbx
0x18000a584  jz      short loc_18000A50D
0x18000a586  mov     eax, 0FFFFFFFFh
0x18000a58b  lock xadd [rbx+18h], eax
0x18000a590  sub     eax, 1
0x18000a593  jz      loc_18000A4FB
0x18000a599  test    eax, eax
0x18000a59b  jns     loc_18000A50D
0x18000a5a1  call    cs:__imp_abort
```
