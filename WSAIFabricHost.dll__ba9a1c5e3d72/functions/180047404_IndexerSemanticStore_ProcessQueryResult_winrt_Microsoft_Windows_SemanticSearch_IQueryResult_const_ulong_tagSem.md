# IndexerSemanticStore::ProcessQueryResult(winrt::Microsoft::Windows::SemanticSearch::IQueryResult const &,ulong *,tagSemanticMatch * *)

- ea: `0x180047404`
- end: `0x1800476cd`
- name: `?ProcessQueryResult@IndexerSemanticStore@@AEAAJAEBUIQueryResult@SemanticSearch@Windows@Microsoft@winrt@@PEAKPEAPEAUtagSemanticMatch@@@Z`
- size: `713`
- prototype: `__int64 __fastcall(IndexerSemanticStore *__hidden this, const struct winrt::Microsoft::Windows::SemanticSearch::IQueryResult *, unsigned int *, struct tagSemanticMatch **)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037488`

## callees

- `0x180004ca0`
- `0x1800058cb`
- `0x18000591f`
- `0x18000c478`
- `0x18000c634`
- `0x180019c3c`
- `0x180021290`
- `0x180028898`
- `0x18002b04c`
- `0x180032370`
- `0x180034dd8`
- `0x1800402dc`
- `0x180047404`
- `0x1800486c0`
- `0x18004cb7c`
- `0x18004e888`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180047652`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180047652`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047498`
- `OLEAUT32!__imp_SysAllocString` at `0x1800475c5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800475c5`

## string_xrefs

- `0x1800474dd`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800476ad`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall IndexerSemanticStore::ProcessQueryResult(
        IndexerSemanticStore *this,
        const struct winrt::Microsoft::Windows::SemanticSearch::IQueryResult *a2,
        unsigned int *a3,
        struct tagSemanticMatch **a4)
{
  unsigned int v6; // edi
  signed __int64 v7; // rcx
  struct tagSemanticMatch *v8; // rax
  const char *v9; // r9
  const char *v10; // r9
  __int64 result; // rax
  int v12; // edi
  int v13; // eax
  __int64 v14; // rax
  __int128 v15; // xmm6
  __int64 v16; // rax
  __int64 v17; // rax
  const OLECHAR *v18; // rcx
  void *v19; // rbx
  int v20; // eax
  HANDLE ProcessHeap; // rax
  _OWORD *v22; // rdx
  unsigned int v23; // esi
  __int64 v24; // [rsp+28h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+30h] [rbp-B8h] BYREF
  void *Source[2]; // [rsp+38h] [rbp-B0h] BYREF
  void *v27; // [rsp+48h] [rbp-A0h]
  __int64 v28; // [rsp+50h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-90h] BYREF
  __int64 v30; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-80h] BYREF
  int v32; // [rsp+70h] [rbp-78h]
  _OWORD v33[2]; // [rsp+78h] [rbp-70h] BYREF
  _BYTE v34[16]; // [rsp+98h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v6 = 0;
  *(_OWORD *)Source = 0;
  v27 = 0;
  try
  {
    winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
      a2,
      &v25);
    v23 = 0;
    winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>::end(
      &v25,
      v31);
    while ( v23 != v32 )
    {
      v24 = 0;
      v12 = v6 | 2;
      LODWORD(v33[0]) = 0;
      *(_OWORD *)((char *)v33 + 8) = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL))(v25, v23, &v24);
      if ( v13 < 0 )
        winrt::throw_hresult((unsigned int)v13, v33);
      v6 = v12 & 0xFFFFFFFC | 1;
      memset(v33, 0, sizeof(v33));
      v14 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
              &v24,
              &v28);
      v15 = *(_OWORD *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemRegion<winrt::Microsoft::Windows::SemanticSearch::IItemRegion>::ItemId(
                         v14,
                         v34);
      v33[0] = v15;
      if ( v28 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v28);
      v16 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
              &v24,
              &v30);
      v17 = *(_QWORD *)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
                         v16,
                         &lpMem);
      if ( v17 )
        v18 = *(const OLECHAR **)(v17 + 16);
      else
        v18 = &pszText;
      *(_QWORD *)&v33[1] = SysAllocString(v18);
      v19 = lpMem;
      if ( lpMem )
      {
        v20 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v20 )
        {
          if ( v20 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v19);
        }
        lpMem = 0;
      }
      if ( v30 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v30);
      DWORD2(v33[1]) = winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemQueryMatch<winrt::Microsoft::Windows::SemanticSearch::IItemQueryMatch>::ConfidenceScore(&v24);
      v22 = Source[1];
      if ( Source[1] == v27 )
      {
        std::vector<tagSemanticMatch>::_Emplace_reallocate<tagSemanticMatch const &>(Source, Source[1], v33);
      }
      else
      {
        *(_OWORD *)Source[1] = v15;
        v22[1] = v33[1];
        Source[1] = (char *)Source[1] + 32;
      }
      if ( v24 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v24);
      ++v23;
    }
    if ( v25 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v25);
    v7 = ((char *)Source[1] - (char *)Source[0]) >> 5;
    *a3 = v7;
    v8 = (struct tagSemanticMatch *)CoTaskMemAlloc(32 * v7);
    if ( !v8 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xADE,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        v9);
    *a4 = v8;
    memcpy_s(
      v8,
      ((char *)Source[1] - (char *)Source[0]) & 0xFFFFFFFFFFFFFFE0uLL,
      Source[0],
      ((char *)Source[1] - (char *)Source[0]) & 0xFFFFFFFFFFFFFFE0uLL);
    SearchIndexerTrace::Information(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0xAE5,
      (unsigned int)L"ProcessQueryResult : MatchCount: %lu",
      (const wchar_t *)*a3);
    std::vector<tagSemanticMatch>::~vector<tagSemanticMatch>(Source);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAE8,
                           (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180047404  mov     rax, rsp
0x180047407  push    rbx
0x180047408  push    rsi
0x180047409  push    rdi
0x18004740a  push    r14
0x18004740c  push    r15
0x18004740e  sub     rsp, 0C0h
0x180047415  movaps  xmmword ptr [rax-38h], xmm6
0x180047419  mov     rax, cs:__security_cookie
0x180047420  xor     rax, rsp
0x180047423  mov     [rsp+0E8h+var_40], rax
0x18004742b  mov     r15, r9
0x18004742e  mov     r14, r8
0x180047431  mov     rax, rdx
0x180047434  xor     edi, edi
0x180047436  mov     [rsp+0E8h+var_C8], edi
0x18004743a  xorps   xmm0, xmm0
0x18004743d  movdqu  xmmword ptr [rsp+0E8h+Source], xmm0
0x180047443  mov     [rsp+0E8h+var_A0], rdi
0x180047448  lea     rdx, [rsp+0E8h+var_B8]
0x18004744d  mov     rcx, rax
0x180047450  call    ?ErrorText@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(void)
0x180047455  nop
0x180047456  xor     esi, esi
0x180047458  lea     rdx, [rsp+0E8h+var_80]
0x18004745d  lea     rcx, [rsp+0E8h+var_B8]
0x180047462  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@U?$IVectorView@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@UItemQueryMatch@SemanticSearch@4Microsoft@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>::end(void)
0x180047467  cmp     esi, [rsp+0E8h+var_78]
0x18004746b  jnz     loc_1800474FB
0x180047471  cmp     [rsp+0E8h+var_B8], 0
0x180047477  jz      short loc_180047483
0x180047479  lea     rcx, [rsp+0E8h+var_B8]
0x18004747e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180047483  mov     rcx, [rsp+0E8h+Source+8]
0x180047488  sub     rcx, [rsp+0E8h+Source]
0x18004748d  sar     rcx, 5
0x180047491  mov     [r14], ecx
0x180047494  shl     rcx, 5; cb
0x180047498  call    cs:__imp_CoTaskMemAlloc
0x18004749e  mov     rcx, [rsp+0E8h]; this
0x1800474a6  test    rax, rax
0x1800474a9  jz      loc_1800476AD
0x1800474af  mov     [r15], rax
0x1800474b2  mov     rdx, [rsp+0E8h+Source+8]
0x1800474b7  mov     r8, [rsp+0E8h+Source]; Source
0x1800474bc  sub     rdx, r8
0x1800474bf  and     rdx, 0FFFFFFFFFFFFFFE0h; DestinationSize
0x1800474c3  mov     r9, rdx; SourceSize
0x1800474c6  mov     rcx, rax; Destination
0x1800474c9  call    memcpy_s
0x1800474ce  mov     r9d, [r14]; wchar_t *
0x1800474d1  lea     r8, aProcessqueryre; "ProcessQueryResult : MatchCount: %lu"
0x1800474d8  mov     edx, 0AE5h; wchar_t *
0x1800474dd  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800474e4  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1800474e9  nop
0x1800474ea  lea     rcx, [rsp+0E8h+Source]
0x1800474ef  call    ??1?$vector@UtagSemanticMatch@@V?$allocator@UtagSemanticMatch@@@std@@@std@@QEAA@XZ; std::vector<tagSemanticMatch>::~vector<tagSemanticMatch>(void)
0x1800474f4  xor     eax, eax
0x1800474f6  jmp     loc_180047686
0x1800474fb  mov     [rsp+0E8h+var_C0], 0
0x180047504  or      edi, 2
0x180047507  mov     [rsp+0E8h+var_C8], edi
0x18004750b  mov     rcx, [rsp+0E8h+var_B8]
0x180047510  mov     dword ptr [rsp+0E8h+var_70], 0
0x180047518  xorps   xmm0, xmm0
0x18004751b  movdqu  [rsp+0E8h+var_70+8], xmm0
0x180047524  mov     rax, [rcx]
0x180047527  lea     r8, [rsp+0E8h+var_C0]
0x18004752c  mov     edx, esi
0x18004752e  mov     rax, [rax+30h]
0x180047532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047537  test    eax, eax
0x180047539  js      loc_1800476BF
0x18004753f  and     edi, 0FFFFFFFDh
0x180047542  mov     [rsp+0E8h+var_C8], edi
0x180047546  or      edi, 1
0x180047549  xorps   xmm0, xmm0
0x18004754c  movups  [rsp+0E8h+var_70], xmm0
0x180047551  movups  [rsp+0E8h+var_60], xmm0
0x180047559  lea     rdx, [rsp+0E8h+var_98]
0x18004755e  lea     rcx, [rsp+0E8h+var_C0]
0x180047563  call    ?TextIndexBasePath@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(void)
0x180047568  nop
0x180047569  lea     rdx, [rsp+0E8h+var_50]
0x180047571  mov     rcx, rax
0x180047574  call    ?ItemId@?$consume_Microsoft_Windows_SemanticSearch_IItemRegion@UIItemRegion@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemRegion<winrt::Microsoft::Windows::SemanticSearch::IItemRegion>::ItemId(void)
0x180047579  movups  xmm6, xmmword ptr [rax]
0x18004757c  movups  [rsp+0E8h+var_70], xmm6
0x180047581  cmp     [rsp+0E8h+var_98], 0
0x180047587  jz      short loc_180047593
0x180047589  lea     rcx, [rsp+0E8h+var_98]
0x18004758e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180047593  lea     rdx, [rsp+0E8h+var_88]
0x180047598  lea     rcx, [rsp+0E8h+var_C0]
0x18004759d  call    ?TextIndexBasePath@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(void)
0x1800475a2  nop
0x1800475a3  lea     rdx, [rsp+0E8h+lpMem]
0x1800475a8  mov     rcx, rax
0x1800475ab  call    ?TextIndexBasePath@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(void)
0x1800475b0  mov     rax, [rax]
0x1800475b3  test    rax, rax
0x1800475b6  jz      short loc_1800475BE
0x1800475b8  mov     rcx, [rax+10h]
0x1800475bc  jmp     short loc_1800475C5
0x1800475be  lea     rcx, pszText; psz
0x1800475c5  call    cs:__imp_SysAllocString
0x1800475cb  mov     qword ptr [rsp+0E8h+var_60], rax
0x1800475d3  mov     rbx, [rsp+0E8h+lpMem]
0x1800475d8  test    rbx, rbx
0x1800475db  jz      short loc_180047606
0x1800475dd  or      eax, 0FFFFFFFFh
0x1800475e0  lock xadd [rbx+18h], eax
0x1800475e5  sub     eax, 1
0x1800475e8  jnz     short loc_18004764E
0x1800475ea  nop
0x1800475eb  call    WINRT_IMPL_GetProcessHeap
0x1800475f0  mov     rcx, rax; hHeap
0x1800475f3  mov     r8, rbx; lpMem
0x1800475f6  xor     edx, edx; dwFlags
0x1800475f8  call    WINRT_IMPL_HeapFree
0x1800475fd  mov     [rsp+0E8h+lpMem], 0
0x180047606  cmp     [rsp+0E8h+var_88], 0
0x18004760c  jz      short loc_180047618
0x18004760e  lea     rcx, [rsp+0E8h+var_88]
0x180047613  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180047618  lea     rcx, [rsp+0E8h+var_C0]
0x18004761d  call    ?ConfidenceScore@?$consume_Microsoft_Windows_SemanticSearch_IItemQueryMatch@UIItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemQueryMatch<winrt::Microsoft::Windows::SemanticSearch::IItemQueryMatch>::ConfidenceScore(void)
0x180047622  movss   dword ptr [rsp+0E8h+var_60+8], xmm0
0x18004762b  mov     rdx, [rsp+0E8h+Source+8]
0x180047630  cmp     rdx, [rsp+0E8h+var_A0]
0x180047635  jz      short loc_180047659
0x180047637  movups  xmmword ptr [rdx], xmm6
0x18004763a  movups  xmm0, [rsp+0E8h+var_60]
0x180047642  movups  xmmword ptr [rdx+10h], xmm0
0x180047646  add     [rsp+0E8h+Source+8], 20h ; ' '
0x18004764c  jmp     short loc_180047669
0x18004764e  test    eax, eax
0x180047650  jns     short loc_1800475FD
0x180047652  call    cs:__imp_abort
0x180047659  lea     r8, [rsp+0E8h+var_70]
0x18004765e  lea     rcx, [rsp+0E8h+Source]
0x180047663  call    ??$_Emplace_reallocate@AEBUtagSemanticMatch@@@?$vector@UtagSemanticMatch@@V?$allocator@UtagSemanticMatch@@@std@@@std@@AEAAPEAUtagSemanticMatch@@QEAU2@AEBU2@@Z; std::vector<tagSemanticMatch>::_Emplace_reallocate<tagSemanticMatch const &>(tagSemanticMatch * const,tagSemanticMatch const &)
0x180047668  nop
0x180047669  cmp     [rsp+0E8h+var_C0], 0
0x18004766f  jz      short loc_18004767B
0x180047671  lea     rcx, [rsp+0E8h+var_C0]
0x180047676  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18004767b  inc     esi
0x18004767d  jmp     loc_180047467
0x180047682  mov     eax, [rsp+0E8h+var_C8]
0x180047686  mov     rcx, [rsp+0E8h+var_40]
0x18004768e  xor     rcx, rsp; StackCookie
0x180047691  call    __security_check_cookie
0x180047696  movaps  xmm6, [rsp+0E8h+var_38]
0x18004769e  add     rsp, 0C0h
0x1800476a5  pop     r15
0x1800476a7  pop     r14
0x1800476a9  pop     rdi
0x1800476aa  pop     rsi
0x1800476ab  pop     rbx
0x1800476ac  retn
0x1800476ad  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800476b4  mov     edx, 0ADEh; void *
0x1800476b9  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800476bf  lea     rdx, [rsp+0E8h+var_70]
0x1800476c4  mov     ecx, eax
0x1800476c6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
