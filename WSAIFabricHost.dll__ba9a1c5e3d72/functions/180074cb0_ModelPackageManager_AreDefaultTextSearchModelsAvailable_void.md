# ModelPackageManager::AreDefaultTextSearchModelsAvailable(void)

- ea: `0x180074cb0`
- end: `0x180074e43`
- name: `?AreDefaultTextSearchModelsAvailable@ModelPackageManager@@SA_NXZ`
- size: `403`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001abd0`
- `0x18001bde0`
- `0x1800765d0`

## callees

- `0x180019c3c`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18004dea8`
- `0x180074684`
- `0x180074cb0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ddd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074ced`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074db0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074ced`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074db0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074e09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074e09`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char ModelPackageManager::AreDefaultTextSearchModelsAvailable(void)
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
  LODWORD(v0[6].SpinCount) = 36;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)&v14);
  try
  {
    v15 = &qword_1800AF6D8;
    _InterlockedIncrement64(&qword_1800AF6D8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> )
    {
      LOBYTE(v14) = 0;
      v8 = 0;
      v9 = 0;
      v1 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)(const struct winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> + 72LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>,
             &v14);
      if ( v1 < 0 )
        winrt::throw_hresult((unsigned int)v1, &v8);
      v2 = (char)v14;
      _InterlockedDecrement64(&qword_1800AF6D8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF6D8);
      v14 = _lambda_c383ee11250bbd797773811d520c56c5_::_lambda_invoker_cdecl_;
      v2 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::call<bool (*)(winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics const &)>(
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
      (void *)0x178,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180074cb0  mov     [rsp+arg_10], rbx
0x180074cb5  mov     [rsp+arg_18], rsi
0x180074cba  push    rdi
0x180074cbb  sub     rsp, 80h
0x180074cc2  lea     rcx, [rsp+88h+var_48]
0x180074cc7  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180074ccc  nop
0x180074ccd  mov     rbx, [rsp+88h+pv]
0x180074cd2  mov     [rsp+88h+arg_0], rbx
0x180074cda  test    rbx, rbx
0x180074cdd  jz      short loc_180074CE6
0x180074cdf  lock inc dword ptr [rbx+120h]
0x180074ce6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180074ced  call    cs:__imp_EnterCriticalSection
0x180074cf3  inc     dword ptr [rbx+0F0h]
0x180074cf9  mov     dword ptr [rbx+110h], 24h ; '$'
0x180074d03  lea     rcx, [rsp+88h+arg_0]
0x180074d0b  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180074d10  lea     rax, qword_1800AF6D8
0x180074d17  mov     [rsp+88h+arg_8], rax
0x180074d1f  lock inc cs:qword_1800AF6D8
0x180074d27  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
0x180074d2e  test    rcx, rcx
0x180074d31  jz      short loc_180074D7A
0x180074d33  mov     byte ptr [rsp+88h+arg_0], 0
0x180074d3b  mov     [rsp+88h+var_68], 0
0x180074d43  xorps   xmm0, xmm0
0x180074d46  movdqu  [rsp+88h+var_60], xmm0
0x180074d4c  mov     rax, [rcx]
0x180074d4f  lea     rdx, [rsp+88h+arg_0]
0x180074d57  mov     rax, [rax+48h]
0x180074d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074d60  test    eax, eax
0x180074d62  js      loc_180074E35
0x180074d68  mov     sil, byte ptr [rsp+88h+arg_0]
0x180074d70  lock dec cs:qword_1800AF6D8
0x180074d78  jmp     short loc_180074DA1
0x180074d7a  lock dec cs:qword_1800AF6D8
0x180074d82  lea     rax, ?_lambda_invoker_cdecl_@_lambda_c383ee11250bbd797773811d520c56c5_@@CA@AEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z; _lambda_c383ee11250bbd797773811d520c56c5_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)
0x180074d89  mov     [rsp+88h+arg_0], rax
0x180074d91  lea     rdx, [rsp+88h+arg_0]
0x180074d99  call    ??$call@P6A_NAEBUISemanticTextIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUISemanticTextIndexStoreStatics@SemanticSearch@Windows@Microsoft@2@@Z@Z
0x180074d9e  mov     sil, al
0x180074da1  mov     rbx, [rsp+88h+pv]
0x180074da6  lea     rdi, [rbx+0C8h]
0x180074dad  mov     rcx, rdi; lpCriticalSection
0x180074db0  call    cs:__imp_EnterCriticalSection
0x180074db6  or      dword ptr [rbx+48h], 300h
0x180074dbd  cmp     qword ptr [rbx+0F8h], 0
0x180074dc5  jz      short loc_180074DD5
0x180074dc7  mov     edx, 2
0x180074dcc  lea     rcx, [rbx+8]
0x180074dd0  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180074dd5  test    rdi, rdi
0x180074dd8  jz      short loc_180074DE4
0x180074dda  mov     rcx, rdi; lpCriticalSection
0x180074ddd  call    cs:__imp_LeaveCriticalSection
0x180074de3  nop
0x180074de4  mov     rbx, [rsp+88h+pv]
0x180074de9  test    rbx, rbx
0x180074dec  jz      short loc_180074E0F
0x180074dee  or      edx, 0FFFFFFFFh
0x180074df1  lock xadd [rbx+120h], edx
0x180074df9  cmp     edx, 1
0x180074dfc  jnz     short loc_180074E0F
0x180074dfe  mov     rcx, rbx
0x180074e01  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180074e06  mov     rcx, rbx; pv
0x180074e09  call    cs:__imp_CoTaskMemFree
0x180074e0f  lea     rcx, [rsp+88h+var_40]; this
0x180074e14  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180074e19  mov     al, sil
0x180074e1c  jmp     short loc_180074E20
0x180074e1e  xor     al, al
0x180074e20  lea     r11, [rsp+88h+var_8]
0x180074e28  mov     rbx, [r11+20h]
0x180074e2c  mov     rsi, [r11+28h]
0x180074e30  mov     rsp, r11
0x180074e33  pop     rdi
0x180074e34  retn
0x180074e35  lea     rdx, [rsp+88h+var_68]
0x180074e3a  mov     ecx, eax
0x180074e3c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
