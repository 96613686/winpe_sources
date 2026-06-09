# ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable(void)

- ea: `0x180075748`
- end: `0x1800758db`
- name: `?IsDefaultImageEmbeddingsGeneratorAvailable@ModelPackageManager@@CA_NXZ`
- size: `403`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ab30`
- `0x18001b430`
- `0x180075dd0`

## callees

- `0x180019c3c`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18004dea8`
- `0x180074574`
- `0x180075748`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075875`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075875`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075785`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075848`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075785`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable(void)
{
  struct _RTL_CRITICAL_SECTION *v0; // rbx
  int v1; // eax
  char v2; // si
  _DWORD *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  const char *v6; // r9
  char result; // al
  int v8; // [rsp+20h] [rbp-68h] BYREF
  __int128 v9; // [rsp+28h] [rbp-60h]
  _BYTE v10[8]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v11[48]; // [rsp+48h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 (__fastcall *v14)(const struct winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics *); // [rsp+90h] [rbp+8h] BYREF
  __int64 *v15; // [rsp+98h] [rbp+10h]

  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v10);
  v0 = (struct _RTL_CRITICAL_SECTION *)pv;
  v14 = (__int64 (__fastcall *)(const struct winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics *))pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v0 + 5);
  ++LODWORD(v0[6].DebugInfo);
  LODWORD(v0[6].SpinCount) = 16;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)&v14);
  try
  {
    v15 = &qword_1800AF658;
    _InterlockedIncrement64(&qword_1800AF658);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> )
    {
      LOBYTE(v14) = 0;
      v8 = 0;
      v9 = 0;
      v1 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)(const struct winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> + 72LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>,
             &v14);
      if ( v1 < 0 )
        winrt::throw_hresult((unsigned int)v1, &v8);
      v2 = (char)v14;
      _InterlockedDecrement64(&qword_1800AF658);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF658);
      v14 = _lambda_c383ee11250bbd797773811d520c56c5_::_lambda_invoker_cdecl_;
      v2 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::call<bool (*)(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)>(
             0,
             (__int64 (__fastcall **)(__int64 *))&v14);
    }
    v3 = pv;
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v3[18] |= 0x300u;
    if ( *((_QWORD *)v3 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)(v3 + 2), 2);
    if ( v4 )
      LeaveCriticalSection(v4);
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v5);
      CoTaskMemFree(v5);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v11);
    result = v2;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180075748  mov     [rsp+arg_10], rbx
0x18007574d  mov     [rsp+arg_18], rsi
0x180075752  push    rdi
0x180075753  sub     rsp, 80h
0x18007575a  lea     rcx, [rsp+88h+var_48]
0x18007575f  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180075764  nop
0x180075765  mov     rbx, [rsp+88h+pv]
0x18007576a  mov     [rsp+88h+arg_0], rbx
0x180075772  test    rbx, rbx
0x180075775  jz      short loc_18007577E
0x180075777  lock inc dword ptr [rbx+120h]
0x18007577e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180075785  call    cs:__imp_EnterCriticalSection
0x18007578b  inc     dword ptr [rbx+0F0h]
0x180075791  mov     dword ptr [rbx+110h], 10h
0x18007579b  lea     rcx, [rsp+88h+arg_0]
0x1800757a3  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x1800757a8  lea     rax, qword_1800AF658
0x1800757af  mov     [rsp+88h+arg_8], rax
0x1800757b7  lock inc cs:qword_1800AF658
0x1800757bf  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x1800757c6  test    rcx, rcx
0x1800757c9  jz      short loc_180075812
0x1800757cb  mov     byte ptr [rsp+88h+arg_0], 0
0x1800757d3  mov     [rsp+88h+var_68], 0
0x1800757db  xorps   xmm0, xmm0
0x1800757de  movdqu  [rsp+88h+var_60], xmm0
0x1800757e4  mov     rax, [rcx]
0x1800757e7  lea     rdx, [rsp+88h+arg_0]
0x1800757ef  mov     rax, [rax+48h]
0x1800757f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757f8  test    eax, eax
0x1800757fa  js      loc_1800758CD
0x180075800  mov     sil, byte ptr [rsp+88h+arg_0]
0x180075808  lock dec cs:qword_1800AF658
0x180075810  jmp     short loc_180075839
0x180075812  lock dec cs:qword_1800AF658
0x18007581a  lea     rax, ?_lambda_invoker_cdecl_@_lambda_c383ee11250bbd797773811d520c56c5_@@CA@AEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z; _lambda_c383ee11250bbd797773811d520c56c5_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)
0x180075821  mov     [rsp+88h+arg_0], rax
0x180075829  lea     rdx, [rsp+88h+arg_0]
0x180075831  call    ??$call@P6A_NAEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@2@@Z@Z
0x180075836  mov     sil, al
0x180075839  mov     rbx, [rsp+88h+pv]
0x18007583e  lea     rdi, [rbx+0C8h]
0x180075845  mov     rcx, rdi; lpCriticalSection
0x180075848  call    cs:__imp_EnterCriticalSection
0x18007584e  or      dword ptr [rbx+48h], 300h
0x180075855  cmp     qword ptr [rbx+0F8h], 0
0x18007585d  jz      short loc_18007586D
0x18007585f  mov     edx, 2
0x180075864  lea     rcx, [rbx+8]
0x180075868  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18007586d  test    rdi, rdi
0x180075870  jz      short loc_18007587C
0x180075872  mov     rcx, rdi; lpCriticalSection
0x180075875  call    cs:__imp_LeaveCriticalSection
0x18007587b  nop
0x18007587c  mov     rbx, [rsp+88h+pv]
0x180075881  test    rbx, rbx
0x180075884  jz      short loc_1800758A7
0x180075886  or      edx, 0FFFFFFFFh
0x180075889  lock xadd [rbx+120h], edx
0x180075891  cmp     edx, 1
0x180075894  jnz     short loc_1800758A7
0x180075896  mov     rcx, rbx
0x180075899  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18007589e  mov     rcx, rbx; pv
0x1800758a1  call    cs:__imp_CoTaskMemFree
0x1800758a7  lea     rcx, [rsp+88h+var_40]; this
0x1800758ac  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800758b1  mov     al, sil
0x1800758b4  jmp     short loc_1800758B8
0x1800758b6  xor     al, al
0x1800758b8  lea     r11, [rsp+88h+var_8]
0x1800758c0  mov     rbx, [r11+20h]
0x1800758c4  mov     rsi, [r11+28h]
0x1800758c8  mov     rsp, r11
0x1800758cb  pop     rdi
0x1800758cc  retn
0x1800758cd  lea     rdx, [rsp+88h+var_68]
0x1800758d2  mov     ecx, eax
0x1800758d4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
