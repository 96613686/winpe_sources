# CGatherer::DeleteUnvisitedEntriesFromMapIterator(ulong &,CCrawl *,TableIterator &,int,int,int,_FILETIME *)

- ea: `0x18002e4b8`
- end: `0x18002eb4d`
- name: `?DeleteUnvisitedEntriesFromMapIterator@CGatherer@@QEAAJAEAKPEAVCCrawl@@AEAVTableIterator@@HHHPEAU_FILETIME@@@Z`
- size: `1685`
- prototype: `__int64 __fastcall(CGatherer *this, unsigned int *, struct CCrawl *, struct TableIterator *, int, int, int)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e24c`

## callees

- `0x180009be8`
- `0x180009c7c`
- `0x18000a23c`
- `0x18000a940`
- `0x18000a970`
- `0x18000bf8c`
- `0x18000d0d0`
- `0x18000e628`
- `0x180013d40`
- `0x180014394`
- `0x180014ff0`
- `0x180015ae0`
- `0x180016c94`
- `0x1800178f0`
- `0x18001e7ac`
- `0x180022b2c`
- `0x1800296b0`
- `0x18002b620`
- `0x18002bf00`
- `0x18002e4b8`
- `0x18002eb54`
- `0x18002eb88`
- `0x18002fd30`
- `0x1800303dc`
- `0x1800454ec`
- `0x180045680`
- `0x180045cf4`
- `0x18006bdec`
- `0x18010b6e0`
- `0x1801244c0`
- `0x1801ca1f4`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eab1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eae9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eab1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eae9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e637`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e637`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e686`

## string_xrefs

- `0x18002e522`: `DeleteUnvistedEntriesFromMapIterator - Beginning for Crawl ID %d, shallow: %s`
- `0x18002eb0c`: `DeleteUnvistedEntriesFromMapIterator - Ending for Crawl ID %d`
- `0x18002e5e3`: `[SrchGatherSvc] delete unvisited crawl %d, dcnt %d, apply %d`
- `0x18002eb18`: `DeleteUnvistedEntriesFromMapIterator`
- `0x18002e582`: `DeleteUnvistedEntriesFromMapIterator - Start Address: %s`
- `0x18002e983`: `DeleteUnvistedEntriesFromMapIterator - Notification URL not found and older than crawl, deleting`
- `0x18002e9b0`: `DeleteUnvistedEntriesFromMapIterator - URL will be removed (marked for delete, fIsParentDeleted, or fIsFOlderNoIndex & FILE)`
- `0x18002e8df`: `DeleteUnvistedEntriesFromMapIterator - URL Didn't pass Exclusion Rules`
- `0x18002e968`: `DeleteUnvistedEntriesFromMapIterator - Notification URL no longer matches start addresses`
- `0x18002e91c`: `DeleteUnvistedEntriesFromMapIterator - URL will be removed (entry crawl number: %d less than crawl: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CGatherer::DeleteUnvisitedEntriesFromMapIterator(
        CGatherer *this,
        unsigned int *a2,
        struct CCrawl *a3,
        struct TableIterator *a4,
        int a5,
        int a6,
        int a7)
{
  CGatherer *v9; // rsi
  int v10; // eax
  const wchar_t *v11; // r8
  int v12; // r12d
  volatile __int32 *v13; // rcx
  CGatherer *v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // r14
  int v16; // r15d
  TableMap *v17; // rbx
  int v18; // edi
  int v19; // esi
  int v20; // eax
  __int16 v21; // bx
  unsigned int v22; // r15d
  CGatherer *v23; // rdi
  CGatherer *v24; // rcx
  int v25; // ebx
  unsigned int v26; // ebx
  volatile __int32 *v27; // rcx
  __int64 v29; // [rsp+20h] [rbp-E0h]
  unsigned int v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  CGatherer *v31; // [rsp+68h] [rbp-98h]
  unsigned int v32; // [rsp+70h] [rbp-90h]
  struct TableIterator *v33; // [rsp+78h] [rbp-88h]
  struct CStartPage *v34; // [rsp+80h] [rbp-80h] BYREF
  const int *v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+98h] [rbp-68h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h]
  char *v39; // [rsp+B0h] [rbp-50h]
  _BYTE v40[140]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v41; // [rsp+14Ch] [rbp+4Ch]
  unsigned int v42; // [rsp+150h] [rbp+50h]
  unsigned int v43; // [rsp+154h] [rbp+54h]
  unsigned int v44; // [rsp+160h] [rbp+60h]
  void **v45; // [rsp+1F0h] [rbp+F0h] BYREF
  int v46; // [rsp+1F8h] [rbp+F8h]
  void **v47; // [rsp+208h] [rbp+108h]
  wchar_t *v48; // [rsp+210h] [rbp+110h]
  __int64 v49; // [rsp+218h] [rbp+118h]
  _WORD v50[207]; // [rsp+220h] [rbp+120h] BYREF
  __int16 v51; // [rsp+3BEh] [rbp+2BEh]
  int v52; // [rsp+3C8h] [rbp+2C8h]
  void **v53; // [rsp+3D0h] [rbp+2D0h] BYREF
  wchar_t *v54; // [rsp+3D8h] [rbp+2D8h]
  __int64 v55; // [rsp+3E0h] [rbp+2E0h]
  __int16 v56; // [rsp+3E8h] [rbp+2E8h] BYREF
  _BYTE v57[480]; // [rsp+570h] [rbp+470h] BYREF
  _BYTE v58[8]; // [rsp+750h] [rbp+650h] BYREF
  int v59; // [rsp+758h] [rbp+658h]
  unsigned int v60; // [rsp+764h] [rbp+664h]
  char v61; // [rsp+76Ch] [rbp+66Ch]
  int v62; // [rsp+77Ch] [rbp+67Ch]

  v33 = a4;
  v9 = this;
  v31 = this;
  v10 = (*(__int64 (__fastcall **)(struct TableIterator *))(*(_QWORD *)a4 + 32LL))(a4);
  v11 = L"TRUE";
  if ( !v10 )
    v11 = L"FALSE";
  ETWLog::Log(
    L"DeleteUnvistedEntriesFromMapIterator - Beginning for Crawl ID %d, shallow: %s",
    *((unsigned int *)a3 + 24),
    v11);
  v34 = (struct CCrawl *)((char *)a3 + 240);
  CSyncReadWrite::GetReadAccess((struct CCrawl *)((char *)a3 + 240));
  v35 = (const int *)((char *)a3 + 40);
  v36 = 0x100000000LL;
  v37 = 0;
  v38 = 0;
  while ( (unsigned int)CTComObjHMapIter<unsigned long,CStartPage,unsigned long>::operator++(&v35) )
  {
    *(_QWORD *)v30 = 0;
    CTComObjSListIter<unsigned long,CStartPage,unsigned long>::GetCurrentValue(&v37, v30);
    ETWLog::Log(L"DeleteUnvistedEntriesFromMapIterator - Start Address: %s", *(_QWORD *)(*(_QWORD *)v30 + 336LL));
    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(v30);
  }
  CSyncReadWrite::ReleaseReadAccess((struct CCrawl *)((char *)a3 + 240));
  v12 = 0;
  v32 = *((_DWORD *)a3 + 24);
  *a2 = 0;
  v13 = (volatile __int32 *)*((_QWORD *)v9 + 567);
  if ( v13 )
    _InterlockedExchange(v13, 1);
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\gatherobj.cxx\"",
    (const wchar_t *)0x1D2C,
    (unsigned int)L"[SrchGatherSvc] delete unvisited crawl %d, dcnt %d, apply %d",
    (const wchar_t *)*((unsigned int *)a3 + 24),
    *a2,
    1);
  while ( !*((_DWORD *)v9 + 301) && v12 >= 0 )
  {
    CGatherer::SleepIfBackOff(v14);
    v15 = (struct _RTL_CRITICAL_SECTION *)((char *)v9 + 1352);
    v39 = (char *)v9 + 1352;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 1352));
    v54 = (wchar_t *)&v56;
    v55 = 193;
    v56 = 0;
    v53 = &TLMString<192,64,32767>::`vftable';
    CTransactionHashEntry::CTransactionHashEntry((CTransactionHashEntry *)v40);
    v16 = 0;
    v17 = (TableMap *)*((_QWORD *)v9 + 175);
    v35 = &TableTransactionManager::`vftable';
    v36 = (__int64)v9 + 1352;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 1352));
    v18 = 0;
    *(_QWORD *)&v37 = 0;
    v19 = 0;
    *((_QWORD *)&v37 + 1) = v17;
    if ( v17 )
    {
      v20 = TableMap::BeginTransaction(v17);
      LODWORD(v38) = v20;
      if ( !v20 )
      {
        v18 = 1;
        *(_QWORD *)&v37 = 0x100000001LL;
        v19 = 1;
      }
    }
    else
    {
      v20 = -2147418113;
    }
    if ( v20 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(struct TableIterator *))(*(_QWORD *)v33 + 8LL))(v33);
      if ( v16 )
        v16 = (*(__int64 (__fastcall **)(struct TableIterator *, void ***, _BYTE *))(*(_QWORD *)v33 + 16LL))(
                v33,
                &v53,
                v40);
    }
    v35 = &TableTransactionManager::`vftable';
    if ( v18 )
    {
      if ( v19 )
        TableMap::EndTransaction(v17);
      else
        TableMap::RollbackTransaction(v17);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v36);
    if ( !v16 )
    {
      CTransactionHashEntry::~CTransactionHashEntry((CTransactionHashEntry *)v40);
      TLMString<192,64,32767>::~TLMString<192,64,32767>(&v53);
      if ( v15 )
        LeaveCriticalSection(v15);
      v9 = v31;
      break;
    }
    v46 = 0;
    v48 = v50;
    v49 = 193;
    v50[0] = 0;
    v47 = &TLMString<192,64,32767>::`vftable';
    v45 = &CComObjectStackRefCount<CURL>::`vftable';
    v52 = 0;
    CURL::Init((CURL *)&v45, v54, 0xFFFFFFFF);
    if ( (v51 & 8) != 0 )
    {
      v51 &= ~8u;
      CURL::ParseHost((CURL *)&v45);
      v50[202] = v50[203] - v50[201];
    }
    if ( v50[204] )
    {
      CURL::ParseAccessType((CURL *)&v45);
      if ( v50[196] != 1 )
        CURL::ParseAccessType((CURL *)&v45);
    }
    v21 = v43;
    v22 = v32;
    if ( (v42 < v32 || v42 == -1 || (v43 & 0x40000) != 0 || a6 || a7 && (v43 & 1) != 0)
      && (unsigned int)CCrawl::ContainsStartPage(a3, v41) )
    {
      if ( (v43 & 0x40000) != 0 || a6 || a7 && (v43 & 1) != 0 )
      {
        ETWLog::LogItem(
          v44,
          v48,
          L"DeleteUnvistedEntriesFromMapIterator - URL will be removed (marked for delete, fIsParentDeleted, or fIsFOlderNoIndex & FILE)");
        v23 = v31;
LABEL_53:
        if ( (v43 & 8) == 0 )
        {
          SDataChange::SDataChange((SDataChange *)v57);
          v12 = CURL::Init((CURL *)v57, (const struct CURL *)&v45);
          if ( v12 >= 0 )
          {
            v26 = v43 & 0xFFEBFFFF;
            if ( !(*(unsigned int (__fastcall **)(struct TableIterator *))(*(_QWORD *)v33 + 32LL))(v33) )
              v62 |= 0x10u;
            v60 = v26;
            TComNoUnkPointer<CPlugin>::operator=(v58, a3);
            v59 = 1;
            v61 = 0;
            v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*((_QWORD *)v23 + 10) + 24LL))((__int64)v23 + 80, v57);
          }
          SDataChange::~SDataChange((SDataChange *)v57);
        }
        goto LABEL_59;
      }
      v30[0] = 0;
      v23 = v31;
      if ( (int)CGatherer::CheckExclusionRules(
                  v31,
                  (struct CURL *)&v45,
                  v43,
                  (int *)v30,
                  v41,
                  0xFFFFFFFF,
                  0xFFFFFFFF,
                  1,
                  0,
                  0,
                  0,
                  0) < 0 )
      {
        SearchIndexerTrace::Verbose(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\server\\\\gatherobj.cxx\"",
          (const wchar_t *)0x1D9B,
          (unsigned int)L"[SrchGatherPI] Notification excluded in full crawl %ls",
          v54);
        ETWLog::LogItem(v44, v48, L"DeleteUnvistedEntriesFromMapIterator - URL Didn't pass Exclusion Rules");
        _InterlockedIncrement((volatile signed __int32 *)a3 + 91);
        goto LABEL_53;
      }
      if ( v42 < v22 )
      {
        if ( (v21 & 0x200) != 0 )
          goto LABEL_59;
        LODWORD(v29) = v22;
        ETWLog::LogItem(
          v44,
          v48,
          L"DeleteUnvistedEntriesFromMapIterator - URL will be removed (entry crawl number: %d less than crawl: %d)",
          v42,
          v29);
        goto LABEL_53;
      }
      if ( v42 != -1 )
        goto LABEL_59;
      v34 = 0;
      v30[0] = -1;
      if ( CStartPageCollection::FindStartAddressByUrl(
             (CGatherer *)((char *)v23 + 2504),
             (struct CURL *)&v45,
             &v34,
             v30) )
      {
        ETWLog::LogItem(
          v44,
          v48,
          L"DeleteUnvistedEntriesFromMapIterator - Notification URL no longer matches start addresses");
        goto LABEL_49;
      }
      v25 = 0;
      if ( CGatherer::ShouldCrawlDeleteNotification(v24, (const struct CTransactionHashEntry *)v40, a3) )
      {
        ETWLog::LogItem(
          v44,
          v48,
          L"DeleteUnvistedEntriesFromMapIterator - Notification URL not found and older than crawl, deleting");
LABEL_49:
        v25 = 1;
      }
      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v34);
      if ( !v25 )
        goto LABEL_59;
      goto LABEL_53;
    }
LABEL_59:
    CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(&v45);
    CTransactionHashEntry::~CTransactionHashEntry((CTransactionHashEntry *)v40);
    TLMString<192,64,32767>::~TLMString<192,64,32767>(&v53);
    v9 = v31;
    if ( v15 )
      LeaveCriticalSection(v15);
  }
  v27 = (volatile __int32 *)*((_QWORD *)v9 + 567);
  if ( v27 )
    _InterlockedExchange(v27, 0);
  ETWLog::Log(L"DeleteUnvistedEntriesFromMapIterator - Ending for Crawl ID %d", *((unsigned int *)a3 + 24));
  ETWLog::LogIfFailed(v12, L"DeleteUnvistedEntriesFromMapIterator");
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002e4b8  push    rbp
0x18002e4ba  push    rbx
0x18002e4bb  push    rsi
0x18002e4bc  push    rdi
0x18002e4bd  push    r12
0x18002e4bf  push    r13
0x18002e4c1  push    r14
0x18002e4c3  push    r15
0x18002e4c5  lea     rbp, [rsp-6C8h]
0x18002e4cd  sub     rsp, 7C8h
0x18002e4d4  mov     rax, cs:__security_cookie
0x18002e4db  xor     rax, rsp
0x18002e4de  mov     [rbp+700h+var_50], rax
0x18002e4e5  mov     [rsp+800h+var_788], r9
0x18002e4ea  mov     r13, r8
0x18002e4ed  mov     rdi, rdx
0x18002e4f0  mov     rsi, rcx
0x18002e4f3  mov     [rsp+800h+var_798], rcx
0x18002e4f8  mov     rax, [r9]
0x18002e4fb  mov     rcx, r9
0x18002e4fe  mov     rax, [rax+20h]
0x18002e502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e507  lea     rcx, aFalse_0; "FALSE"
0x18002e50e  lea     r8, aTrue_0; "TRUE"
0x18002e515  xor     r14d, r14d
0x18002e518  test    eax, eax
0x18002e51a  cmovz   r8, rcx
0x18002e51e  mov     edx, [r13+60h]
0x18002e522  lea     rcx, aDeleteunvisted_4; "DeleteUnvistedEntriesFromMapIterator - "...
0x18002e529  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x18002e52e  lea     rbx, [r13+0F0h]
0x18002e535  mov     [rbp+700h+var_780], rbx
0x18002e539  mov     rcx, rbx; this
0x18002e53c  call    ?GetReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetReadAccess(void)
0x18002e541  nop
0x18002e542  lea     rax, [r13+28h]
0x18002e546  mov     [rbp+700h+var_778], rax
0x18002e54a  mov     dword ptr [rbp+700h+var_770], r14d
0x18002e54e  mov     dword ptr [rbp+700h+var_770+4], 1
0x18002e555  xorps   xmm0, xmm0
0x18002e558  movdqu  [rbp+700h+var_768], xmm0
0x18002e55d  mov     [rbp+700h+var_758], r14
0x18002e561  jmp     short loc_18002E599
0x18002e563  mov     qword ptr [rsp+800h+var_7A0], r14
0x18002e568  lea     rdx, [rsp+800h+var_7A0]
0x18002e56d  lea     rcx, [rbp+700h+var_768]
0x18002e571  call    ?GetCurrentValue@?$CTComObjSListIter@KVCStartPage@@K@@QEBAJPEAPEAVCStartPage@@@Z; CTComObjSListIter<ulong,CStartPage,ulong>::GetCurrentValue(CStartPage * *)
0x18002e576  mov     rdx, qword ptr [rsp+800h+var_7A0]
0x18002e57b  mov     rdx, [rdx+150h]
0x18002e582  lea     rcx, aDeleteunvisted_7; "DeleteUnvistedEntriesFromMapIterator - "...
0x18002e589  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x18002e58e  nop
0x18002e58f  lea     rcx, [rsp+800h+var_7A0]
0x18002e594  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x18002e599  lea     rcx, [rbp+700h+var_778]
0x18002e59d  call    ??E?$CTComObjHMapIter@KVCStartPage@@K@@QEAAHXZ; CTComObjHMapIter<ulong,CStartPage,ulong>::operator++(void)
0x18002e5a2  test    eax, eax
0x18002e5a4  jnz     short loc_18002E563
0x18002e5a6  mov     rcx, rbx; this
0x18002e5a9  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x18002e5ae  nop
0x18002e5af  mov     r12d, r14d
0x18002e5b2  mov     r15d, [r13+60h]
0x18002e5b6  mov     [rsp+800h+var_790], r15d
0x18002e5bb  mov     [rdi], r14d
0x18002e5be  mov     rcx, [rsi+11B8h]
0x18002e5c5  test    rcx, rcx
0x18002e5c8  jz      short loc_18002E5D1
0x18002e5ca  mov     eax, 1
0x18002e5cf  xchg    eax, [rcx]
0x18002e5d1  mov     [rsp+800h+var_7D8], 1
0x18002e5d9  mov     eax, [rdi]
0x18002e5db  mov     dword ptr [rsp+800h+var_7E0], eax
0x18002e5df  mov     r9d, [r13+60h]; wchar_t *
0x18002e5e3  lea     r8, aSrchgathersvcD; "[SrchGatherSvc] delete unvisited crawl "...
0x18002e5ea  mov     edx, 1D2Ch; wchar_t *
0x18002e5ef  lea     rcx, aOnecoreuapBase_114; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18002e5f6  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18002e5fb  lea     rbx, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18002e602  lea     rdi, ??_7TableTransactionManager@@6B@; const TableTransactionManager::`vftable'
0x18002e609  jmp     short loc_18002E60E
0x18002e60b  xor     r14d, r14d
0x18002e60e  cmp     [rsi+4B4h], r14d
0x18002e615  jnz     loc_18002EAF7
0x18002e61b  test    r12d, r12d
0x18002e61e  js      loc_18002EAF7
0x18002e624  call    ?SleepIfBackOff@CGatherer@@AEAAXXZ; CGatherer::SleepIfBackOff(void)
0x18002e629  lea     r14, [rsi+548h]
0x18002e630  mov     [rbp+700h+var_750], r14
0x18002e634  mov     rcx, r14; lpCriticalSection
0x18002e637  call    cs:__imp_EnterCriticalSection
0x18002e63d  nop
0x18002e63e  lea     rax, [rbp+700h+var_418]
0x18002e645  mov     [rbp+700h+var_428], rax
0x18002e64c  mov     [rbp+700h+var_420], 0C1h
0x18002e657  xor     eax, eax
0x18002e659  mov     [rbp+700h+var_418], ax
0x18002e660  mov     [rbp+700h+var_430], rbx
0x18002e667  lea     rcx, [rbp+700h+var_740]; this
0x18002e66b  call    ??0CTransactionHashEntry@@QEAA@XZ; CTransactionHashEntry::CTransactionHashEntry(void)
0x18002e670  nop
0x18002e671  xor     r15d, r15d
0x18002e674  mov     rbx, [rsi+578h]
0x18002e67b  mov     [rbp+700h+var_778], rdi
0x18002e67f  mov     [rbp+700h+var_770], r14
0x18002e683  mov     rcx, r14; lpCriticalSection
0x18002e686  call    cs:__imp_EnterCriticalSection
0x18002e68c  nop
0x18002e68d  xor     edi, edi
0x18002e68f  mov     qword ptr [rbp+700h+var_768], rdi
0x18002e693  xor     esi, esi
0x18002e695  mov     qword ptr [rbp+700h+var_768+8], rbx
0x18002e699  test    rbx, rbx
0x18002e69c  jnz     short loc_18002E6A5
0x18002e69e  mov     eax, 8000FFFFh
0x18002e6a3  jmp     short loc_18002E6C1
0x18002e6a5  mov     rcx, rbx; this
0x18002e6a8  call    ?BeginTransaction@TableMap@@UEAAJXZ; TableMap::BeginTransaction(void)
0x18002e6ad  mov     dword ptr [rbp+700h+var_758], eax
0x18002e6b0  test    eax, eax
0x18002e6b2  jnz     short loc_18002E6C1
0x18002e6b4  lea     ecx, [rax+1]
0x18002e6b7  mov     edi, ecx
0x18002e6b9  mov     dword ptr [rbp+700h+var_768], ecx
0x18002e6bc  mov     esi, ecx
0x18002e6be  mov     dword ptr [rbp+700h+var_768+4], ecx
0x18002e6c1  test    eax, eax
0x18002e6c3  js      short loc_18002E6FC
0x18002e6c5  mov     rcx, [rsp+800h+var_788]
0x18002e6ca  mov     rax, [rcx]
0x18002e6cd  mov     rax, [rax+8]
0x18002e6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6d6  mov     r15d, eax
0x18002e6d9  test    eax, eax
0x18002e6db  jz      short loc_18002E6FC
0x18002e6dd  mov     rcx, [rsp+800h+var_788]
0x18002e6e2  mov     rax, [rcx]
0x18002e6e5  lea     r8, [rbp+700h+var_740]
0x18002e6e9  lea     rdx, [rbp+700h+var_430]
0x18002e6f0  mov     rax, [rax+10h]
0x18002e6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6f9  mov     r15d, eax
0x18002e6fc  lea     rax, ??_7TableTransactionManager@@6B@; const TableTransactionManager::`vftable'
0x18002e703  mov     [rbp+700h+var_778], rax
0x18002e707  test    edi, edi
0x18002e709  jz      short loc_18002E71E
0x18002e70b  mov     rcx, rbx; this
0x18002e70e  test    esi, esi
0x18002e710  jz      short loc_18002E719
0x18002e712  call    ?EndTransaction@TableMap@@UEAAJXZ; TableMap::EndTransaction(void)
0x18002e717  jmp     short loc_18002E71E
0x18002e719  call    ?RollbackTransaction@TableMap@@UEAAJXZ; TableMap::RollbackTransaction(void)
0x18002e71e  lea     rcx, [rbp+700h+var_770]
0x18002e722  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18002e727  nop
0x18002e728  xor     esi, esi
0x18002e72a  test    r15d, r15d
0x18002e72d  jz      loc_18002EACA
0x18002e733  mov     [rbp+700h+var_608], esi
0x18002e739  lea     rax, [rbp+700h+var_5E0]
0x18002e740  mov     [rbp+700h+var_5F0], rax
0x18002e747  mov     [rbp+700h+var_5E8], 0C1h
0x18002e752  mov     [rbp+700h+var_5E0], si
0x18002e759  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x18002e760  mov     [rbp+700h+var_5F8], rax
0x18002e767  lea     rax, ??_7?$CComObjectStackRefCount@VCURL@@@@6B@; const CComObjectStackRefCount<CURL>::`vftable'
0x18002e76e  mov     [rbp+700h+var_610], rax
0x18002e775  mov     [rbp+700h+var_438], esi
0x18002e77b  or      r8d, 0FFFFFFFFh; unsigned int
0x18002e77f  mov     rdx, [rbp+700h+var_428]; wchar_t *
0x18002e786  lea     rcx, [rbp+700h+var_610]; this
0x18002e78d  call    ?Init@CURL@@QEAAJPEB_WK@Z; CURL::Init(wchar_t const *,ulong)
0x18002e792  test    byte ptr [rbp+700h+var_442], 8
0x18002e799  jz      short loc_18002E7C8
0x18002e79b  mov     eax, 0FFF7h
0x18002e7a0  and     [rbp+700h+var_442], ax
0x18002e7a7  lea     rcx, [rbp+700h+var_610]; this
0x18002e7ae  call    ?ParseHost@CURL@@IEAAXXZ; CURL::ParseHost(void)
0x18002e7b3  movzx   eax, [rbp+700h+var_44A]
0x18002e7ba  sub     ax, [rbp+700h+var_44E]
0x18002e7c1  mov     [rbp+700h+var_44C], ax
0x18002e7c8  cmp     [rbp+700h+var_448], si
0x18002e7cf  jz      short loc_18002E7F9
0x18002e7d1  lea     rcx, [rbp+700h+var_610]; this
0x18002e7d8  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x18002e7dd  mov     edi, 1
0x18002e7e2  cmp     [rbp+700h+var_458], di
0x18002e7e9  jz      short loc_18002E7FE
0x18002e7eb  lea     rcx, [rbp+700h+var_610]; this
0x18002e7f2  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x18002e7f7  jmp     short loc_18002E7FE
0x18002e7f9  mov     edi, 1
0x18002e7fe  mov     ebx, [rbp+700h+var_6AC]
0x18002e801  mov     r15d, [rsp+800h+var_790]
0x18002e806  cmp     [rbp+700h+var_6B0], r15d
0x18002e80a  jb      short loc_18002E835
0x18002e80c  cmp     [rbp+700h+var_6B0], 0FFFFFFFFh
0x18002e810  jz      short loc_18002E835
0x18002e812  bt      ebx, 12h
0x18002e816  jb      short loc_18002E835
0x18002e818  cmp     [rbp+700h+arg_28], esi
0x18002e81e  jnz     short loc_18002E835
0x18002e820  cmp     [rbp+700h+arg_30], esi
0x18002e826  jz      loc_18002EA6E
0x18002e82c  test    dil, bl
0x18002e82f  jz      loc_18002EA6E
0x18002e835  movzx   edx, [rbp+700h+var_6B4]; unsigned int
0x18002e839  mov     rcx, r13; this
0x18002e83c  call    ?ContainsStartPage@CCrawl@@QEAAHK@Z; CCrawl::ContainsStartPage(ulong)
0x18002e841  test    eax, eax
0x18002e843  jz      loc_18002EA6E
0x18002e849  mov     r8d, [rbp+700h+var_6AC]; unsigned int
0x18002e84d  bt      r8d, 12h
0x18002e852  jb      loc_18002E9B0
0x18002e858  cmp     [rbp+700h+arg_28], esi
0x18002e85e  jnz     loc_18002E9B0
0x18002e864  cmp     [rbp+700h+arg_30], esi
0x18002e86a  jz      short loc_18002E875
0x18002e86c  test    dil, r8b
0x18002e86f  jnz     loc_18002E9B0
0x18002e875  mov     [rsp+800h+var_7A0], esi
0x18002e879  movzx   eax, [rbp+700h+var_6B4]
0x18002e87d  mov     [rsp+800h+var_7A8], rsi; struct IGatherPropertyBag **
0x18002e882  mov     [rsp+800h+var_7B0], rsi; bool *
0x18002e887  mov     [rsp+800h+var_7B8], rsi; wchar_t *
0x18002e88c  mov     [rsp+800h+var_7C0], esi; int
0x18002e890  mov     [rsp+800h+var_7C8], edi; int
0x18002e894  or      ecx, 0FFFFFFFFh
0x18002e897  mov     [rsp+800h+var_7D0], ecx; unsigned int
0x18002e89b  mov     [rsp+800h+var_7D8], ecx; unsigned int
0x18002e89f  mov     dword ptr [rsp+800h+var_7E0], eax; unsigned int
0x18002e8a3  lea     r9, [rsp+800h+var_7A0]; int *
0x18002e8a8  lea     rdx, [rbp+700h+var_610]; struct CURL *
0x18002e8af  mov     rdi, [rsp+800h+var_798]
0x18002e8b4  mov     rcx, rdi; this
0x18002e8b7  call    ?CheckExclusionRules@CGatherer@@QEAAJAEAVCURL@@KAEAJKKKHHPEB_WPEA_NPEAPEAUIGatherPropertyBag@@@Z; CGatherer::CheckExclusionRules(CURL &,ulong,long &,ulong,ulong,ulong,int,int,wchar_t const *,bool *,IGatherPropertyBag * *)
0x18002e8bc  test    eax, eax
0x18002e8be  jns     short loc_18002E902
0x18002e8c0  mov     r9, [rbp+700h+var_428]; wchar_t *
0x18002e8c7  lea     r8, aSrchgatherpiNo; "[SrchGatherPI] Notification excluded in"...
0x18002e8ce  mov     edx, 1D9Bh; wchar_t *
0x18002e8d3  lea     rcx, aOnecoreuapBase_114; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18002e8da  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18002e8df  lea     r8, aDeleteunvisted_2; "DeleteUnvistedEntriesFromMapIterator - "...
0x18002e8e6  mov     rdx, [rbp+700h+var_5F0]; wchar_t *
0x18002e8ed  mov     ecx, [rbp+700h+var_6A0]; unsigned int
0x18002e8f0  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18002e8f5  lock inc dword ptr [r13+16Ch]
0x18002e8fd  jmp     loc_18002E9CB
0x18002e902  mov     eax, [rbp+700h+var_6B0]
0x18002e905  cmp     eax, r15d
0x18002e908  jnb     short loc_18002E937
0x18002e90a  bt      ebx, 9
0x18002e90e  jb      loc_18002EA6E
0x18002e914  mov     dword ptr [rsp+800h+var_7E0], r15d
0x18002e919  mov     r9d, eax
0x18002e91c  lea     r8, aDeleteunvisted_0; "DeleteUnvistedEntriesFromMapIterator - "...
0x18002e923  mov     rdx, [rbp+700h+var_5F0]; wchar_t *
0x18002e92a  mov     ecx, [rbp+700h+var_6A0]; unsigned int
0x18002e92d  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18002e932  jmp     loc_18002E9CB
0x18002e937  cmp     eax, 0FFFFFFFFh
0x18002e93a  jnz     loc_18002EA6E
0x18002e940  mov     [rbp+700h+var_780], rsi
0x18002e944  mov     [rsp+800h+var_7A0], eax
0x18002e948  lea     rcx, [rdi+9C8h]; this
0x18002e94f  lea     r9, [rsp+800h+var_7A0]; unsigned int *
0x18002e954  lea     r8, [rbp+700h+var_780]; struct CStartPage **
0x18002e958  lea     rdx, [rbp+700h+var_610]; struct CURL *
0x18002e95f  call    ?FindStartAddressByUrl@CStartPageCollection@@QEAAJAEAVCURL@@PEAPEAVCStartPage@@AEAK@Z; CStartPageCollection::FindStartAddressByUrl(CURL &,CStartPage * *,ulong &)
0x18002e964  test    eax, eax
0x18002e966  jz      short loc_18002E971
0x18002e968  lea     r8, aDeleteunvisted; "DeleteUnvistedEntriesFromMapIterator - "...
0x18002e96f  jmp     short loc_18002E98A
0x18002e971  mov     ebx, esi
0x18002e973  mov     r8, r13; struct CCrawl *
0x18002e976  lea     rdx, [rbp+700h+var_740]; struct CTransactionHashEntry *
0x18002e97a  call    ?ShouldCrawlDeleteNotification@CGatherer@@QEAA_NAEBVCTransactionHashEntry@@PEAVCCrawl@@@Z; CGatherer::ShouldCrawlDeleteNotification(CTransactionHashEntry const &,CCrawl *)
0x18002e97f  test    al, al
0x18002e981  jz      short loc_18002E99E
0x18002e983  lea     r8, aDeleteunvisted_5; "DeleteUnvistedEntriesFromMapIterator - "...
0x18002e98a  mov     rdx, [rbp+700h+var_5F0]; wchar_t *
0x18002e991  mov     ecx, [rbp+700h+var_6A0]; unsigned int
0x18002e994  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18002e999  mov     ebx, 1
0x18002e99e  lea     rcx, [rbp+700h+var_780]
0x18002e9a2  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x18002e9a7  test    ebx, ebx
0x18002e9a9  jnz     short loc_18002E9CB
0x18002e9ab  jmp     loc_18002EA6E
0x18002e9b0  lea     r8, aDeleteunvisted_3; "DeleteUnvistedEntriesFromMapIterator - "...
0x18002e9b7  mov     rdx, [rbp+700h+var_5F0]; wchar_t *
0x18002e9be  mov     ecx, [rbp+700h+var_6A0]; unsigned int
0x18002e9c1  call    ?LogItem@ETWLog@@SAXKPEB_W0ZZ; ETWLog::LogItem(ulong,wchar_t const *,wchar_t const *,...)
0x18002e9c6  mov     rdi, [rsp+800h+var_798]
0x18002e9cb  test    byte ptr [rbp+700h+var_6AC], 8
0x18002e9cf  jnz     loc_18002EA6E
0x18002e9d5  lea     rcx, [rbp+700h+var_290]; this
0x18002e9dc  call    ??0SDataChange@@QEAA@XZ; SDataChange::SDataChange(void)
0x18002e9e1  nop
  ... truncated ...
```
