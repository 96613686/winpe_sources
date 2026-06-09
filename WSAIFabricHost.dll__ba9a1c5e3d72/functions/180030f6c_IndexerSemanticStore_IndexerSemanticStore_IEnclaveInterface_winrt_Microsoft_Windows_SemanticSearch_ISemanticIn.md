# IndexerSemanticStore::IndexerSemanticStore(IEnclaveInterface &,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex)

- ea: `0x180030f6c`
- end: `0x1800313f4`
- name: `??0IndexerSemanticStore@@QEAA@AEAUIEnclaveInterface@@UISemanticIndex@SemanticSearch@Windows@Microsoft@winrt@@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(__int64, void *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002e86c`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x180007ad0`
- `0x18000c018`
- `0x18000c478`
- `0x180012444`
- `0x180013930`
- `0x1800189b8`
- `0x180019c3c`
- `0x180030f6c`
- `0x180034e2c`
- `0x180049174`
- `0x18007c2e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003125a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003139c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003125a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003139c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003106f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003106f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800310fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800310fd`

## string_xrefs

- `0x1800313af`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800313c1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800313d6`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
__int64 __fastcall IndexerSemanticStore::IndexerSemanticStore(__int64 a1, void *a2, void **a3)
{
  void *v5; // rcx
  void **v6; // r15
  void **v7; // r12
  __int128 *v8; // rdi
  void **v9; // rdi
  void *v10; // rsi
  HANDLE EventW; // rbx
  BOOL v12; // eax
  const char *v13; // r9
  signed int LastError; // eax
  void (__fastcall ***v15)(_QWORD, __int64 *, void **); // rcx
  void *v16; // rbx
  const char *v17; // r9
  void *v18; // rcx
  int v19; // eax
  volatile signed __int32 *v20; // rbx
  const wchar_t *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // edi
  HANDLE ProcessHeap; // rax
  void (__fastcall ***v27)(_QWORD, __int64 *, void **); // rcx
  void *v28; // rbx
  void *v29; // rcx
  int v30; // eax
  const wchar_t *v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rcx
  int v34; // edi
  void *v35; // [rsp+28h] [rbp-59h] BYREF
  void *v36; // [rsp+30h] [rbp-51h] BYREF
  __int128 v37; // [rsp+38h] [rbp-49h] BYREF
  void *v38; // [rsp+48h] [rbp-39h]
  void *v39; // [rsp+50h] [rbp-31h]
  __int128 v40; // [rsp+58h] [rbp-29h] BYREF
  void *v41; // [rsp+68h] [rbp-19h]
  void *v42; // [rsp+70h] [rbp-11h]
  int v43; // [rsp+78h] [rbp-9h] BYREF
  __int128 v44; // [rsp+80h] [rbp-1h]
  char v45; // [rsp+90h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  void *dwErrCode; // [rsp+F0h] [rbp+6Fh] BYREF
  void **v48; // [rsp+F8h] [rbp+77h]
  __int128 *v49; // [rsp+100h] [rbp+7Fh]

  v48 = a3;
  dwErrCode = a2;
  *(_QWORD *)(a1 + 8) = &winrt::impl::produce<IndexerSemanticStore,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations>::`vftable';
  *(_QWORD *)a1 = &winrt::impl::producers_base<SessionManagerBrokerImpl,std::tuple<ISessionManagerBroker,ISessionManagerBroker2,ISessionManagerBroker3,IUpdateModelCacheOnDriverUpdate>>::`vftable'{for `winrt::impl::producer_convert<SessionManagerBrokerImpl,ISessionManagerBroker2,void>'};
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(a1 + 24);
  *(_QWORD *)(a1 + 24) = 1;
  *(_QWORD *)a1 = &IndexerSemanticStore::`vftable'{for `winrt::impl::producers_base<IndexerSemanticStore,std::tuple<IIndexerSemanticStore,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations>>'};
  *(_QWORD *)(a1 + 16) = &IndexerSemanticStore::`vftable'{for `winrt::impl::root_implements<IndexerSemanticStore,IIndexerSemanticStore,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations,winrt::non_agile>'};
  v5 = *a3;
  *(_QWORD *)(a1 + 32) = *a3;
  if ( v5 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 8LL))(v5);
  v6 = (void **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  v7 = (void **)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  v8 = (__int128 *)operator new(0x20u);
  v49 = v8;
  *v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<semantic_index::implementation::embedding_factory>::`vftable';
  v8[1] = 0;
  semantic_index::embedding_converter::embedding_converter((semantic_index::embedding_converter *)(v8 + 1));
  *(_QWORD *)(a1 + 56) = v8 + 1;
  *(_QWORD *)(a1 + 64) = v8;
  *(_QWORD *)(a1 + 72) = dwErrCode;
  v9 = (void **)(a1 + 80);
  v10 = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = -2147467259;
  EventW = CreateEventW(0, 1, 1, 0);
  if ( (char *)(a1 + 80) == &v45 )
  {
    if ( EventW && !CloseHandle(EventW) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
  }
  else
  {
    v10 = *v9;
    if ( *v9 )
    {
      LODWORD(dwErrCode) = GetLastError();
      v12 = CloseHandle(v10);
      v10 = 0;
      if ( !v12 )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v13);
      SetLastError((DWORD)dwErrCode);
    }
    *v9 = EventW;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( *v9 == v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x819,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const char *)(unsigned int)LastError,
      (int)v35);
  if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(a3) )
  {
    if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(a3) == 1 )
    {
      v27 = (void (__fastcall ***)(_QWORD, __int64 *, void **))*a3;
      if ( *a3 )
      {
        dwErrCode = v10;
        (**v27)(
          v27,
          winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStore>,
          &dwErrCode);
        v28 = dwErrCode;
        v36 = dwErrCode;
      }
      else
      {
        v36 = v10;
        v28 = v10;
      }
      if ( v7 == &v36 )
      {
        if ( v28 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v36);
      }
      else
      {
        if ( *v7 != v10 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 48);
        *v7 = v28;
      }
      if ( *v7 != v10 )
      {
        v49 = &v40;
        v40 = 0;
        v41 = v10;
        v42 = v10;
        std::wstring::_Construct<1,wchar_t const *>(&v40, L"SemanticImageStore");
        dwErrCode = v10;
        v29 = *v7;
        v43 = (int)v10;
        v44 = 0;
        v30 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)v29 + 48LL))(v29, &dwErrCode);
        if ( v30 < 0 )
          winrt::throw_hresult((unsigned int)v30, &v43);
        v20 = (volatile signed __int32 *)dwErrCode;
        v31 = dwErrCode ? (const wchar_t *)*((_QWORD *)dwErrCode + 2) : &pszText;
        v37 = 0;
        v38 = v10;
        v39 = v10;
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] != (_WORD)v10 );
        std::wstring::_Construct<1,wchar_t const *>(&v37, v31);
        IndexerSemanticStore::ReportDatabseSize(v33, &v37, &v40);
        if ( v20 )
        {
          v34 = _InterlockedDecrement(v20 + 6);
          if ( !v34 )
            goto LABEL_33;
          if ( v34 < 0 )
            abort();
        }
      }
    }
  }
  else
  {
    v15 = (void (__fastcall ***)(_QWORD, __int64 *, void **))*a3;
    if ( *a3 )
    {
      dwErrCode = v10;
      (**v15)(v15, winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStore>, &dwErrCode);
      v16 = dwErrCode;
      v35 = dwErrCode;
    }
    else
    {
      v35 = v10;
      v16 = v10;
    }
    if ( v6 == &v35 )
    {
      if ( v16 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v35);
    }
    else
    {
      if ( *v6 != v10 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 40);
      *v6 = v16;
    }
    if ( *v6 != v10 )
    {
      v49 = &v37;
      v37 = 0;
      v38 = v10;
      v39 = v10;
      std::wstring::_Construct<1,wchar_t const *>(&v37, L"SemanticTextStore");
      dwErrCode = v10;
      v18 = *v6;
      v43 = (int)v10;
      v44 = 0;
      v19 = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)v18 + 48LL))(v18, &dwErrCode);
      if ( v19 < 0 )
        winrt::throw_hresult((unsigned int)v19, &v43);
      v20 = (volatile signed __int32 *)dwErrCode;
      v21 = dwErrCode ? (const wchar_t *)*((_QWORD *)dwErrCode + 2) : &pszText;
      v40 = 0;
      v41 = v10;
      v42 = v10;
      v22 = -1;
      do
        ++v22;
      while ( v21[v22] != (_WORD)v10 );
      std::wstring::_Construct<1,wchar_t const *>(&v40, v21);
      IndexerSemanticStore::ReportDatabseSize(v23, &v40, &v37);
      if ( v20 )
      {
        v24 = _InterlockedDecrement(v20 + 6);
        if ( !v24 )
        {
LABEL_33:
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v20);
          goto LABEL_34;
        }
        if ( v24 < 0 )
          abort();
      }
    }
  }
LABEL_34:
  if ( *a3 != v10 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a3);
  return a1;
}

```

## disassembly

```asm
0x180030f6c  mov     rax, rsp
0x180030f6f  mov     [rax+18h], r8
0x180030f73  mov     [rax+10h], rdx
0x180030f77  mov     [rax+8], rcx
0x180030f7b  push    rbp
0x180030f7c  push    rbx
0x180030f7d  push    rsi
0x180030f7e  push    rdi
0x180030f7f  push    r12
0x180030f81  push    r13
0x180030f83  push    r14
0x180030f85  push    r15
0x180030f87  lea     rbp, [rax-5Fh]
0x180030f8b  sub     rsp, 98h
0x180030f92  mov     r14, r8
0x180030f95  mov     r13, rcx
0x180030f98  xor     edi, edi
0x180030f9a  lea     rax, ??_7?$produce@UIndexerSemanticStore@@UISemanticIndexOperations@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<IndexerSemanticStore,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations>::`vftable'
0x180030fa1  mov     [rcx+8], rax
0x180030fa5  lea     rax, ??_7?$producers_base@USessionManagerBrokerImpl@@V?$tuple@UISessionManagerBroker@@UISessionManagerBroker2@@UISessionManagerBroker3@@UIUpdateModelCacheOnDriverUpdate@@@std@@@impl@winrt@@6B?$producer_convert@USessionManagerBrokerImpl@@UISessionManagerBroker2@@X@12@@; const winrt::impl::producers_base<SessionManagerBrokerImpl,std::tuple<ISessionManagerBroker,ISessionManagerBroker2,ISessionManagerBroker3,IUpdateModelCacheOnDriverUpdate>>::`vftable'{for `winrt::impl::producer_convert<SessionManagerBrokerImpl,ISessionManagerBroker2,void>'}
0x180030fac  mov     [rcx], rax
0x180030faf  add     rcx, 18h
0x180030fb3  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x180030fb8  mov     qword ptr [r13+18h], 1
0x180030fc0  lea     rax, ??_7IndexerSemanticStore@@6B?$producers_base@UIndexerSemanticStore@@V?$tuple@UIIndexerSemanticStore@@UISemanticIndexOperations@SemanticSearch@Indexer@Windows@winrt@@@std@@@impl@winrt@@@; const IndexerSemanticStore::`vftable'{for `winrt::impl::producers_base<IndexerSemanticStore,std::tuple<IIndexerSemanticStore,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations>>'}
0x180030fc7  mov     [r13+0], rax
0x180030fcb  lea     rax, ??_7IndexerSemanticStore@@6B?$root_implements@UIndexerSemanticStore@@UIIndexerSemanticStore@@UISemanticIndexOperations@SemanticSearch@Indexer@Windows@winrt@@Unon_agile@7@@impl@winrt@@@; const IndexerSemanticStore::`vftable'{for `winrt::impl::root_implements<IndexerSemanticStore,IIndexerSemanticStore,winrt::Windows::Indexer::SemanticSearch::ISemanticIndexOperations,winrt::non_agile>'}
0x180030fd2  mov     [r13+10h], rax
0x180030fd6  mov     rcx, [r14]
0x180030fd9  mov     [r13+20h], rcx
0x180030fdd  test    rcx, rcx
0x180030fe0  jz      short loc_180030FEF
0x180030fe2  mov     rax, [rcx]
0x180030fe5  mov     rax, [rax+8]
0x180030fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fee  nop
0x180030fef  lea     r15, [r13+28h]
0x180030ff3  mov     [r15], rdi
0x180030ff6  lea     r12, [r13+30h]
0x180030ffa  mov     [r12], rdi
0x180030ffe  mov     ecx, 20h ; ' '; Size
0x180031003  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031008  mov     rdi, rax
0x18003100b  mov     [rbp+57h+arg_18], rax
0x18003100f  xorps   xmm0, xmm0
0x180031012  movups  xmmword ptr [rax], xmm0
0x180031015  mov     dword ptr [rax+8], 1
0x18003101c  mov     dword ptr [rax+0Ch], 1
0x180031023  lea     rax, ??_7?$_Ref_count_obj2@Uembedding_factory@implementation@semantic_index@@@std@@6B@; const std::_Ref_count_obj2<semantic_index::implementation::embedding_factory>::`vftable'
0x18003102a  mov     [rdi], rax
0x18003102d  lea     rbx, [rdi+10h]
0x180031031  movups  xmmword ptr [rbx], xmm0
0x180031034  mov     rcx, rbx; this
0x180031037  call    ??0embedding_converter@semantic_index@@QEAA@XZ; semantic_index::embedding_converter::embedding_converter(void)
0x18003103c  nop
0x18003103d  mov     [r13+38h], rbx
0x180031041  mov     [r13+40h], rdi
0x180031045  mov     rax, [rbp+57h+dwErrCode]
0x180031049  mov     [r13+48h], rax
0x18003104d  lea     rdi, [r13+50h]
0x180031051  xor     esi, esi
0x180031053  mov     [rdi], rsi
0x180031056  xor     eax, eax
0x180031058  mov     [r13+58h], rax
0x18003105c  mov     dword ptr [r13+60h], 80004005h
0x180031064  xor     r9d, r9d; lpName
0x180031067  lea     edx, [rsi+1]; bManualReset
0x18003106a  xor     ecx, ecx; lpEventAttributes
0x18003106c  mov     r8d, edx; bInitialState
0x18003106f  call    cs:__imp_CreateEventW
0x180031075  mov     rbx, rax
0x180031078  lea     rax, [rbp+57h+var_48]
0x18003107c  cmp     rdi, rax
0x18003107f  jz      short loc_1800310F5
0x180031081  mov     rsi, [rdi]
0x180031084  test    rsi, rsi
0x180031087  jz      short loc_1800310B2
0x180031089  call    cs:__imp_GetLastError
0x18003108f  mov     dword ptr [rbp+57h+dwErrCode], eax
0x180031092  mov     rcx, rsi; hObject
0x180031095  call    cs:__imp_CloseHandle
0x18003109b  mov     rcx, [rbp+5Fh]; this
0x18003109f  xor     esi, esi
0x1800310a1  test    eax, eax
0x1800310a3  jz      loc_1800313C1
0x1800310a9  mov     ecx, dword ptr [rbp+57h+dwErrCode]; dwErrCode
0x1800310ac  call    cs:__imp_SetLastError
0x1800310b2  mov     [rdi], rbx
0x1800310b5  call    cs:__imp_GetLastError
0x1800310bb  test    eax, eax
0x1800310bd  jle     short loc_1800310C7
0x1800310bf  movzx   eax, ax
0x1800310c2  or      eax, 80070000h
0x1800310c7  mov     rcx, [rbp+5Fh]; this
0x1800310cb  cmp     [rdi], rsi
0x1800310ce  jz      loc_1800313D3
0x1800310d4  mov     rcx, r14
0x1800310d7  call    ?Size@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(void)
0x1800310dc  test    eax, eax
0x1800310de  jnz     loc_180031261
0x1800310e4  mov     rcx, [r14]
0x1800310e7  test    rcx, rcx
0x1800310ea  jnz     short loc_180031111
0x1800310ec  mov     [rbp+57h+var_B0], rsi
0x1800310f0  mov     rbx, rsi
0x1800310f3  jmp     short loc_180031133
0x1800310f5  test    rbx, rbx
0x1800310f8  jz      short loc_1800310B5
0x1800310fa  mov     rcx, rbx; hObject
0x1800310fd  call    cs:__imp_CloseHandle
0x180031103  mov     rcx, [rbp+5Fh]; this
0x180031107  test    eax, eax
0x180031109  jz      loc_1800313AF
0x18003110f  jmp     short loc_1800310B5
0x180031111  mov     [rbp+57h+dwErrCode], rsi
0x180031115  mov     rax, [rcx]
0x180031118  lea     r8, [rbp+57h+dwErrCode]
0x18003111c  lea     rdx, ??$guid_v@UISemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStore>
0x180031123  mov     rax, [rax]
0x180031126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003112b  mov     rbx, [rbp+57h+dwErrCode]
0x18003112f  mov     [rbp+57h+var_B0], rbx
0x180031133  lea     rax, [rbp+57h+var_B0]
0x180031137  cmp     r15, rax
0x18003113a  jz      short loc_18003114E
0x18003113c  cmp     [r15], rsi
0x18003113f  jz      short loc_180031149
0x180031141  mov     rcx, r15
0x180031144  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180031149  mov     [r15], rbx
0x18003114c  jmp     short loc_18003115C
0x18003114e  test    rbx, rbx
0x180031151  jz      short loc_18003115C
0x180031153  lea     rcx, [rbp+57h+var_B0]
0x180031157  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003115c  cmp     [r15], rsi
0x18003115f  jz      loc_180031232
0x180031165  lea     rax, [rbp+57h+var_A0]
0x180031169  mov     [rbp+57h+arg_18], rax
0x18003116d  xorps   xmm0, xmm0
0x180031170  movups  [rbp+57h+var_A0], xmm0
0x180031174  mov     [rbp+57h+var_90], rsi
0x180031178  mov     [rbp+57h+var_88], rsi
0x18003117c  mov     r8d, 11h
0x180031182  lea     rdx, aSemantictextst; "SemanticTextStore"
0x180031189  lea     rcx, [rbp+57h+var_A0]
0x18003118d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180031192  nop
0x180031193  mov     [rbp+57h+dwErrCode], rsi
0x180031197  mov     rcx, [r15]
0x18003119a  mov     [rbp+57h+var_60], esi
0x18003119d  xorps   xmm0, xmm0
0x1800311a0  movdqu  [rbp+57h+var_58], xmm0
0x1800311a5  mov     rax, [rcx]
0x1800311a8  lea     rdx, [rbp+57h+dwErrCode]
0x1800311ac  mov     rax, [rax+30h]
0x1800311b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311b5  test    eax, eax
0x1800311b7  js      loc_1800313E8
0x1800311bd  mov     rbx, [rbp+57h+dwErrCode]
0x1800311c1  mov     [rbp+57h+dwErrCode], rbx
0x1800311c5  test    rbx, rbx
0x1800311c8  jz      short loc_1800311D0
0x1800311ca  mov     rdx, [rbx+10h]
0x1800311ce  jmp     short loc_1800311D7
0x1800311d0  lea     rdx, pszText
0x1800311d7  xorps   xmm0, xmm0
0x1800311da  movups  [rbp+57h+var_80], xmm0
0x1800311de  mov     [rbp+57h+var_70], rsi
0x1800311e2  mov     [rbp+57h+var_68], rsi
0x1800311e6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800311ea  mov     r8, rdi
0x1800311ed  inc     r8
0x1800311f0  cmp     [rdx+r8*2], si
0x1800311f5  jnz     short loc_1800311ED
0x1800311f7  lea     rcx, [rbp+57h+var_80]
0x1800311fb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180031200  nop
0x180031201  lea     r8, [rbp+57h+var_A0]
0x180031205  lea     rdx, [rbp+57h+var_80]
0x180031209  call    ?ReportDatabseSize@IndexerSemanticStore@@AEAAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; IndexerSemanticStore::ReportDatabseSize(std::wstring,std::wstring)
0x18003120e  nop
0x18003120f  test    rbx, rbx
0x180031212  jz      short loc_180031232
0x180031214  lock xadd [rbx+18h], edi
0x180031219  sub     edi, 1
0x18003121c  jnz     short loc_180031256
0x18003121e  nop
0x18003121f  call    WINRT_IMPL_GetProcessHeap
0x180031224  mov     rcx, rax; hHeap
0x180031227  mov     r8, rbx; lpMem
0x18003122a  xor     edx, edx; dwFlags
0x18003122c  call    WINRT_IMPL_HeapFree
0x180031231  nop
0x180031232  cmp     [r14], rsi
0x180031235  jz      short loc_18003123F
0x180031237  mov     rcx, r14
0x18003123a  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003123f  mov     rax, r13
0x180031242  add     rsp, 98h
0x180031249  pop     r15
0x18003124b  pop     r14
0x18003124d  pop     r13
0x18003124f  pop     r12
0x180031251  pop     rdi
0x180031252  pop     rsi
0x180031253  pop     rbx
0x180031254  pop     rbp
0x180031255  retn
0x180031256  test    edi, edi
0x180031258  jns     short loc_180031232
0x18003125a  call    cs:__imp_abort
0x180031261  mov     rcx, r14
0x180031264  call    ?Size@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(void)
0x180031269  cmp     eax, 1
0x18003126c  jnz     short loc_180031232
0x18003126e  mov     rcx, [r14]
0x180031271  test    rcx, rcx
0x180031274  jnz     short loc_18003127F
0x180031276  mov     [rbp+57h+var_A8], rsi
0x18003127a  mov     rbx, rsi
0x18003127d  jmp     short loc_1800312A1
0x18003127f  mov     [rbp+57h+dwErrCode], rsi
0x180031283  mov     rax, [rcx]
0x180031286  lea     r8, [rbp+57h+dwErrCode]
0x18003128a  lea     rdx, ??$guid_v@UISemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStore>
0x180031291  mov     rax, [rax]
0x180031294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031299  mov     rbx, [rbp+57h+dwErrCode]
0x18003129d  mov     [rbp+57h+var_A8], rbx
0x1800312a1  lea     rax, [rbp+57h+var_A8]
0x1800312a5  cmp     r12, rax
0x1800312a8  jz      short loc_1800312BE
0x1800312aa  cmp     [r12], rsi
0x1800312ae  jz      short loc_1800312B8
0x1800312b0  mov     rcx, r12
0x1800312b3  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800312b8  mov     [r12], rbx
0x1800312bc  jmp     short loc_1800312CC
0x1800312be  test    rbx, rbx
0x1800312c1  jz      short loc_1800312CC
0x1800312c3  lea     rcx, [rbp+57h+var_A8]
0x1800312c7  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800312cc  cmp     [r12], rsi
0x1800312d0  jz      loc_180031232
0x1800312d6  lea     rax, [rbp+57h+var_80]
0x1800312da  mov     [rbp+57h+arg_18], rax
0x1800312de  xorps   xmm0, xmm0
0x1800312e1  movups  [rbp+57h+var_80], xmm0
0x1800312e5  mov     [rbp+57h+var_70], rsi
0x1800312e9  mov     [rbp+57h+var_68], rsi
0x1800312ed  mov     r8d, 12h
0x1800312f3  lea     rdx, aSemanticimages; "SemanticImageStore"
0x1800312fa  lea     rcx, [rbp+57h+var_80]
0x1800312fe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180031303  nop
0x180031304  mov     [rbp+57h+dwErrCode], rsi
0x180031308  mov     rcx, [r12]
0x18003130c  mov     [rbp+57h+var_60], esi
0x18003130f  xorps   xmm0, xmm0
0x180031312  movdqu  [rbp+57h+var_58], xmm0
0x180031317  mov     rax, [rcx]
0x18003131a  lea     rdx, [rbp+57h+dwErrCode]
0x18003131e  mov     rax, [rax+30h]
0x180031322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031327  test    eax, eax
0x180031329  js      short loc_1800313A3
0x18003132b  mov     rbx, [rbp+57h+dwErrCode]
0x18003132f  mov     [rbp+57h+dwErrCode], rbx
0x180031333  test    rbx, rbx
0x180031336  jz      short loc_18003133E
0x180031338  mov     rdx, [rbx+10h]
0x18003133c  jmp     short loc_180031345
0x18003133e  lea     rdx, pszText
0x180031345  xorps   xmm0, xmm0
0x180031348  movups  [rbp+57h+var_A0], xmm0
0x18003134c  mov     [rbp+57h+var_90], rsi
0x180031350  mov     [rbp+57h+var_88], rsi
0x180031354  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031358  mov     r8, rdi
0x18003135b  inc     r8
0x18003135e  cmp     [rdx+r8*2], si
0x180031363  jnz     short loc_18003135B
0x180031365  lea     rcx, [rbp+57h+var_A0]
0x180031369  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003136e  nop
0x18003136f  lea     r8, [rbp+57h+var_80]
0x180031373  lea     rdx, [rbp+57h+var_A0]
0x180031377  call    ?ReportDatabseSize@IndexerSemanticStore@@AEAAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; IndexerSemanticStore::ReportDatabseSize(std::wstring,std::wstring)
0x18003137c  nop
0x18003137d  test    rbx, rbx
0x180031380  jz      loc_180031232
0x180031386  lock xadd [rbx+18h], edi
0x18003138b  sub     edi, 1
0x18003138e  jz      loc_18003121E
0x180031394  test    edi, edi
0x180031396  jns     loc_180031232
0x18003139c  call    cs:__imp_abort
0x1800313a3  lea     rdx, [rbp+57h+var_60]
0x1800313a7  mov     ecx, eax
  ... truncated ...
```
