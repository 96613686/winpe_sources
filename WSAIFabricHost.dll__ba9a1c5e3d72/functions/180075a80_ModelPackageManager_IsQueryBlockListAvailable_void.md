# ModelPackageManager::IsQueryBlockListAvailable(void)

- ea: `0x180075a80`
- end: `0x180075c13`
- name: `?IsQueryBlockListAvailable@ModelPackageManager@@SA_NXZ`
- size: `403`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001aeb0`
- `0x18001d120`
- `0x180076a40`

## callees

- `0x180019c3c`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18004dea8`
- `0x180074464`
- `0x180075a80`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075bad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075bad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075abd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075b80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075abd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075bd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char ModelPackageManager::IsQueryBlockListAvailable(void)
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
  __int64 (__fastcall *v14)(__int64 *); // [rsp+90h] [rbp+8h] BYREF
  __int64 *v15; // [rsp+98h] [rbp+10h]

  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v10);
  v0 = (struct _RTL_CRITICAL_SECTION *)pv;
  v14 = (__int64 (__fastcall *)(__int64 *))pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v0 + 5);
  ++LODWORD(v0[6].DebugInfo);
  LODWORD(v0[6].SpinCount) = 23;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)&v14);
  try
  {
    v15 = &qword_1800AF638;
    _InterlockedIncrement64(&qword_1800AF638);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> )
    {
      LOBYTE(v14) = 0;
      v8 = 0;
      v9 = 0;
      v1 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)(__int64 *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>
                                                                                  + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>,
             &v14);
      if ( v1 < 0 )
        winrt::throw_hresult((unsigned int)v1, &v8);
      v2 = (char)v14;
      _InterlockedDecrement64(&qword_1800AF638);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF638);
      v14 = (__int64 (__fastcall *)(__int64 *))winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK;
      v2 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::call<bool (*)(winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics const &)>(
             0,
             &v14);
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
      (void *)0x159,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180075a80  mov     [rsp+arg_10], rbx
0x180075a85  mov     [rsp+arg_18], rsi
0x180075a8a  push    rdi
0x180075a8b  sub     rsp, 80h
0x180075a92  lea     rcx, [rsp+88h+var_48]
0x180075a97  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180075a9c  nop
0x180075a9d  mov     rbx, [rsp+88h+pv]
0x180075aa2  mov     [rsp+88h+arg_0], rbx
0x180075aaa  test    rbx, rbx
0x180075aad  jz      short loc_180075AB6
0x180075aaf  lock inc dword ptr [rbx+120h]
0x180075ab6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180075abd  call    cs:__imp_EnterCriticalSection
0x180075ac3  inc     dword ptr [rbx+0F0h]
0x180075ac9  mov     dword ptr [rbx+110h], 17h
0x180075ad3  lea     rcx, [rsp+88h+arg_0]
0x180075adb  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180075ae0  lea     rax, qword_1800AF638
0x180075ae7  mov     [rsp+88h+arg_8], rax
0x180075aef  lock inc cs:qword_1800AF638
0x180075af7  mov     rcx, cs:??$factory_cache_entry_v@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>
0x180075afe  test    rcx, rcx
0x180075b01  jz      short loc_180075B4A
0x180075b03  mov     byte ptr [rsp+88h+arg_0], 0
0x180075b0b  mov     [rsp+88h+var_68], 0
0x180075b13  xorps   xmm0, xmm0
0x180075b16  movdqu  [rsp+88h+var_60], xmm0
0x180075b1c  mov     rax, [rcx]
0x180075b1f  lea     rdx, [rsp+88h+arg_0]
0x180075b27  mov     rax, [rax+30h]
0x180075b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b30  test    eax, eax
0x180075b32  js      loc_180075C05
0x180075b38  mov     sil, byte ptr [rsp+88h+arg_0]
0x180075b40  lock dec cs:qword_1800AF638
0x180075b48  jmp     short loc_180075B71
0x180075b4a  lock dec cs:qword_1800AF638
0x180075b52  lea     rax, ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x180075b59  mov     [rsp+88h+arg_0], rax
0x180075b61  lea     rdx, [rsp+88h+arg_0]
0x180075b69  call    ??$call@P6A_NAEBUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUIQueryBlockListStatics@SemanticSearch@Windows@Microsoft@2@@Z@Z
0x180075b6e  mov     sil, al
0x180075b71  mov     rbx, [rsp+88h+pv]
0x180075b76  lea     rdi, [rbx+0C8h]
0x180075b7d  mov     rcx, rdi; lpCriticalSection
0x180075b80  call    cs:__imp_EnterCriticalSection
0x180075b86  or      dword ptr [rbx+48h], 300h
0x180075b8d  cmp     qword ptr [rbx+0F8h], 0
0x180075b95  jz      short loc_180075BA5
0x180075b97  mov     edx, 2
0x180075b9c  lea     rcx, [rbx+8]
0x180075ba0  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180075ba5  test    rdi, rdi
0x180075ba8  jz      short loc_180075BB4
0x180075baa  mov     rcx, rdi; lpCriticalSection
0x180075bad  call    cs:__imp_LeaveCriticalSection
0x180075bb3  nop
0x180075bb4  mov     rbx, [rsp+88h+pv]
0x180075bb9  test    rbx, rbx
0x180075bbc  jz      short loc_180075BDF
0x180075bbe  or      edx, 0FFFFFFFFh
0x180075bc1  lock xadd [rbx+120h], edx
0x180075bc9  cmp     edx, 1
0x180075bcc  jnz     short loc_180075BDF
0x180075bce  mov     rcx, rbx
0x180075bd1  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180075bd6  mov     rcx, rbx; pv
0x180075bd9  call    cs:__imp_CoTaskMemFree
0x180075bdf  lea     rcx, [rsp+88h+var_40]; this
0x180075be4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180075be9  mov     al, sil
0x180075bec  jmp     short loc_180075BF0
0x180075bee  xor     al, al
0x180075bf0  lea     r11, [rsp+88h+var_8]
0x180075bf8  mov     rbx, [r11+20h]
0x180075bfc  mov     rsi, [r11+28h]
0x180075c00  mov     rsp, r11
0x180075c03  pop     rdi
0x180075c04  retn
0x180075c05  lea     rdx, [rsp+88h+var_68]
0x180075c0a  mov     ecx, eax
0x180075c0c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
