# IndexerSemanticStore::ClearStorage(void)

- ea: `0x180034730`
- end: `0x18003489d`
- name: `?ClearStorage@IndexerSemanticStore@@UEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(IndexerSemanticStore *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180019c3c`
- `0x180021290`
- `0x18002abe0`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180034730`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034788`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800347e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034788`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800347e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003485f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003485f`

## string_xrefs

- `0x180034751`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IndexerSemanticStore::ClearStorage(
        IndexerSemanticStore *this,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  _DWORD *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  wchar_t **v10; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  const char *v13; // r9
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-68h] BYREF
  __int128 v16; // [rsp+28h] [rbp-60h]
  _BYTE v17[8]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v18[48]; // [rsp+48h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+90h] [rbp+8h] BYREF

  SearchIndexerTrace::Information(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0xA83,
    (unsigned int)L"IndexerSemanticStore ClearStorage invoked",
    a4);
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v17);
  v5 = (struct _RTL_CRITICAL_SECTION *)pv;
  v21 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v5 + 5);
  ++LODWORD(v5[6].DebugInfo);
  LODWORD(v5[6].SpinCount) = 3;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v21);
  v6 = *((_QWORD *)this + 4);
  v15 = 0;
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 88LL))(v6);
  if ( v7 < 0 )
  {
    try
    {
      winrt::throw_hresult((unsigned int)v7, &v15);
    }
    catch ( ... )
    {
      *(_DWORD *)(v14 + 144) = wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0xA96,
                                 (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sema"
                                               "nticsupportimpl.cpp",
                                 v13);
      return (unsigned int)v21;
    }
  }
  v8 = pv;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  v8[18] |= 0x300u;
  if ( *((_QWORD *)v8 + 31) )
    tip2::details::shared_data<0,0,0>::complete_helper((__int64)(v8 + 2), 2);
  if ( v9 )
    LeaveCriticalSection(v9);
  if ( *((_QWORD *)this + 5) )
  {
    v10 = off_18008BE80;
LABEL_12:
    SemanticSearchTelemetry::SemanticIndexStoreCleared<wchar_t * const &>(v10);
    goto LABEL_13;
  }
  if ( *((_QWORD *)this + 6) )
  {
    v10 = off_18008BE88;
    goto LABEL_12;
  }
LABEL_13:
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v11);
    CoTaskMemFree(v11);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v18);
  return 0;
}

```

## disassembly

```asm
0x180034730  mov     [rsp+arg_8], rbx
0x180034735  mov     [rsp+arg_10], rsi
0x18003473a  push    rdi
0x18003473b  sub     rsp, 80h
0x180034742  mov     rsi, rcx
0x180034745  lea     r8, aIndexersemanti; "IndexerSemanticStore ClearStorage invok"...
0x18003474c  mov     edx, 0A83h; wchar_t *
0x180034751  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180034758  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18003475d  lea     rcx, [rsp+88h+var_48]
0x180034762  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180034767  nop
0x180034768  mov     rbx, [rsp+88h+pv]
0x18003476d  mov     [rsp+88h+arg_0], rbx
0x180034775  test    rbx, rbx
0x180034778  jz      short loc_180034781
0x18003477a  lock inc dword ptr [rbx+120h]
0x180034781  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180034788  call    cs:__imp_EnterCriticalSection
0x18003478e  inc     dword ptr [rbx+0F0h]
0x180034794  mov     dword ptr [rbx+110h], 3
0x18003479e  lea     rcx, [rsp+88h+arg_0]
0x1800347a6  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x1800347ab  mov     rcx, [rsi+20h]
0x1800347af  mov     [rsp+88h+var_68], 0
0x1800347b7  xorps   xmm0, xmm0
0x1800347ba  movdqu  [rsp+88h+var_60], xmm0
0x1800347c0  mov     rax, [rcx]
0x1800347c3  mov     rax, [rax+58h]
0x1800347c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800347cc  test    eax, eax
0x1800347ce  js      loc_18003488F
0x1800347d4  mov     rbx, [rsp+88h+pv]
0x1800347d9  lea     rdi, [rbx+0C8h]
0x1800347e0  mov     rcx, rdi; lpCriticalSection
0x1800347e3  call    cs:__imp_EnterCriticalSection
0x1800347e9  or      dword ptr [rbx+48h], 300h
0x1800347f0  cmp     qword ptr [rbx+0F8h], 0
0x1800347f8  jz      short loc_180034808
0x1800347fa  mov     edx, 2
0x1800347ff  lea     rcx, [rbx+8]
0x180034803  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180034808  test    rdi, rdi
0x18003480b  jz      short loc_180034816
0x18003480d  mov     rcx, rdi; lpCriticalSection
0x180034810  call    cs:__imp_LeaveCriticalSection
0x180034816  cmp     qword ptr [rsi+28h], 0
0x18003481b  jz      short loc_180034826
0x18003481d  lea     rcx, off_18008BE80; "SemanticTextStore"
0x180034824  jmp     short loc_180034834
0x180034826  cmp     qword ptr [rsi+30h], 0
0x18003482b  jz      short loc_18003483A
0x18003482d  lea     rcx, off_18008BE88; "SemanticImageStore"
0x180034834  call    ??$SemanticIndexStoreCleared@AEBQEA_W@SemanticSearchTelemetry@@SAXAEBQEA_W@Z; SemanticSearchTelemetry::SemanticIndexStoreCleared<wchar_t * const &>(wchar_t * const &)
0x180034839  nop
0x18003483a  mov     rbx, [rsp+88h+pv]
0x18003483f  test    rbx, rbx
0x180034842  jz      short loc_180034865
0x180034844  or      eax, 0FFFFFFFFh
0x180034847  lock xadd [rbx+120h], eax
0x18003484f  cmp     eax, 1
0x180034852  jnz     short loc_180034865
0x180034854  mov     rcx, rbx
0x180034857  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18003485c  mov     rcx, rbx; pv
0x18003485f  call    cs:__imp_CoTaskMemFree
0x180034865  lea     rcx, [rsp+88h+var_40]; this
0x18003486a  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003486f  xor     eax, eax
0x180034871  jmp     short loc_18003487A
0x180034873  mov     eax, dword ptr [rsp+88h+arg_0]
0x18003487a  lea     r11, [rsp+88h+var_8]
0x180034882  mov     rbx, [r11+18h]
0x180034886  mov     rsi, [r11+20h]
0x18003488a  mov     rsp, r11
0x18003488d  pop     rdi
0x18003488e  retn
0x18003488f  lea     rdx, [rsp+88h+var_68]
0x180034894  mov     ecx, eax
0x180034896  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
