# ModelPackageManager::IsDefaultImageTextQueryGeneratorAvailable(void)

- ea: `0x1800758e4`
- end: `0x180075a77`
- name: `?IsDefaultImageTextQueryGeneratorAvailable@ModelPackageManager@@CA_NXZ`
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
- `0x1800758e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075921`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800759e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075921`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800759e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075a3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075a3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char ModelPackageManager::IsDefaultImageTextQueryGeneratorAvailable(void)
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
  LODWORD(v0[6].SpinCount) = 35;
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
      v1 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)(const struct winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> + 120LL))(
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
      v14 = _lambda_57c6d09c08da4f0ae3b7878ea67db15c_::_lambda_invoker_cdecl_;
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
      (void *)0x1C6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800758e4  mov     [rsp+arg_10], rbx
0x1800758e9  mov     [rsp+arg_18], rsi
0x1800758ee  push    rdi
0x1800758ef  sub     rsp, 80h
0x1800758f6  lea     rcx, [rsp+88h+var_48]
0x1800758fb  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180075900  nop
0x180075901  mov     rbx, [rsp+88h+pv]
0x180075906  mov     [rsp+88h+arg_0], rbx
0x18007590e  test    rbx, rbx
0x180075911  jz      short loc_18007591A
0x180075913  lock inc dword ptr [rbx+120h]
0x18007591a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180075921  call    cs:__imp_EnterCriticalSection
0x180075927  inc     dword ptr [rbx+0F0h]
0x18007592d  mov     dword ptr [rbx+110h], 23h ; '#'
0x180075937  lea     rcx, [rsp+88h+arg_0]
0x18007593f  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180075944  lea     rax, qword_1800AF658
0x18007594b  mov     [rsp+88h+arg_8], rax
0x180075953  lock inc cs:qword_1800AF658
0x18007595b  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x180075962  test    rcx, rcx
0x180075965  jz      short loc_1800759AE
0x180075967  mov     byte ptr [rsp+88h+arg_0], 0
0x18007596f  mov     [rsp+88h+var_68], 0
0x180075977  xorps   xmm0, xmm0
0x18007597a  movdqu  [rsp+88h+var_60], xmm0
0x180075980  mov     rax, [rcx]
0x180075983  lea     rdx, [rsp+88h+arg_0]
0x18007598b  mov     rax, [rax+78h]
0x18007598f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075994  test    eax, eax
0x180075996  js      loc_180075A69
0x18007599c  mov     sil, byte ptr [rsp+88h+arg_0]
0x1800759a4  lock dec cs:qword_1800AF658
0x1800759ac  jmp     short loc_1800759D5
0x1800759ae  lock dec cs:qword_1800AF658
0x1800759b6  lea     rax, ?_lambda_invoker_cdecl_@_lambda_57c6d09c08da4f0ae3b7878ea67db15c_@@CA@AEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z; _lambda_57c6d09c08da4f0ae3b7878ea67db15c_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)
0x1800759bd  mov     [rsp+88h+arg_0], rax
0x1800759c5  lea     rdx, [rsp+88h+arg_0]
0x1800759cd  call    ??$call@P6A_NAEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@2@@Z@Z
0x1800759d2  mov     sil, al
0x1800759d5  mov     rbx, [rsp+88h+pv]
0x1800759da  lea     rdi, [rbx+0C8h]
0x1800759e1  mov     rcx, rdi; lpCriticalSection
0x1800759e4  call    cs:__imp_EnterCriticalSection
0x1800759ea  or      dword ptr [rbx+48h], 300h
0x1800759f1  cmp     qword ptr [rbx+0F8h], 0
0x1800759f9  jz      short loc_180075A09
0x1800759fb  mov     edx, 2
0x180075a00  lea     rcx, [rbx+8]
0x180075a04  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180075a09  test    rdi, rdi
0x180075a0c  jz      short loc_180075A18
0x180075a0e  mov     rcx, rdi; lpCriticalSection
0x180075a11  call    cs:__imp_LeaveCriticalSection
0x180075a17  nop
0x180075a18  mov     rbx, [rsp+88h+pv]
0x180075a1d  test    rbx, rbx
0x180075a20  jz      short loc_180075A43
0x180075a22  or      edx, 0FFFFFFFFh
0x180075a25  lock xadd [rbx+120h], edx
0x180075a2d  cmp     edx, 1
0x180075a30  jnz     short loc_180075A43
0x180075a32  mov     rcx, rbx
0x180075a35  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180075a3a  mov     rcx, rbx; pv
0x180075a3d  call    cs:__imp_CoTaskMemFree
0x180075a43  lea     rcx, [rsp+88h+var_40]; this
0x180075a48  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180075a4d  mov     al, sil
0x180075a50  jmp     short loc_180075A54
0x180075a52  xor     al, al
0x180075a54  lea     r11, [rsp+88h+var_8]
0x180075a5c  mov     rbx, [r11+20h]
0x180075a60  mov     rsi, [r11+28h]
0x180075a64  mov     rsp, r11
0x180075a67  pop     rdi
0x180075a68  retn
0x180075a69  lea     rdx, [rsp+88h+var_68]
0x180075a6e  mov     ecx, eax
0x180075a70  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
