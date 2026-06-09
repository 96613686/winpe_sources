# CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)

- ea: `0x180032328`
- end: `0x180032dee`
- name: `??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z`
- size: `2758`
- prototype: `CMapiStore *(CMapiStore *this, __int64, __int64, struct _SPropValue *, struct IUnknown *, unsigned int, int, ...)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003664c`

## callees

- `0x180002780`
- `0x18000ad14`
- `0x18000bf84`
- `0x18000bfb0`
- `0x18000d7c0`
- `0x18000e684`
- `0x18000e6e0`
- `0x18000f1c4`
- `0x18000fd58`
- `0x1800113ec`
- `0x180011884`
- `0x1800122d8`
- `0x18001bd9c`
- `0x180022690`
- `0x180023a30`
- `0x18002cd78`
- `0x18002d4e0`
- `0x18002e57c`
- `0x18002eb44`
- `0x18002f4b0`
- `0x1800301d8`
- `0x180030870`
- `0x180031310`
- `0x180032328`
- `0x180033154`
- `0x1800339a4`
- `0x180033a38`
- `0x180033e70`
- `0x180033f4c`
- `0x1800340c0`
- `0x180034304`
- `0x180034370`
- `0x1800343f8`
- `0x180034488`
- `0x180034b8c`
- `0x18003519c`
- `0x180035248`
- `0x180035a18`
- `0x180036df0`
- `0x180037a68`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180032b2a`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180032b2a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800326f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180032beb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800326f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180032beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032b4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032b4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180032b5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180032b5a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180032cf2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180032cf2`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180032cd5`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180032cd5`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x180032c75`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x180032c75`

## string_xrefs

- `0x1800329db`: `IsCached`
- `0x180032c18`: `Unable to create CPusherAdvise()`
- `0x180032d90`: `CMapiStore::CMapiStore(%s) Created`

## pseudocode

```c
CMapiStore *CMapiStore::CMapiStore(
        CMapiStore *this,
        __int64 a2,
        __int64 a3,
        struct _SPropValue *a4,
        struct IUnknown *a5,
        unsigned int a6,
        int a7,
        ...)
{
  _QWORD *v10; // r12
  struct IUnknown **v11; // rsi
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v18; // xmm5_4
  int v19; // r11d
  int v20; // r10d
  int v21; // r9d
  __int64 v22; // r8
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  int *v25; // r15
  __int64 v26; // rbx
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  int v30; // r15d
  struct IUnknown *v31; // rbx
  BOOL v32; // eax
  LPSPropValue v33; // rbx
  LPCWSTR v34; // rsi
  wchar_t *v35; // r9
  int InstalledOutlookVersion; // eax
  __int64 v37; // rdi
  int v38; // eax
  LPMAPIPROP *v39; // r15
  int MapiManager; // eax
  struct CMapiManager *v41; // rcx
  LPSPropValue v42; // r12
  char *v43; // rbx
  _QWORD *v44; // r13
  unsigned int v45; // ebx
  LPSPropValue v46; // rcx
  __int64 ul; // rdx
  LPSPropValue v48; // r8
  LPMAPIPROP v49; // rcx
  __int64 v50; // rbx
  unsigned int v52; // [rsp+20h] [rbp-48h]
  unsigned int v53; // [rsp+28h] [rbp-40h]
  struct _SECURITY_ATTRIBUTES *v54; // [rsp+30h] [rbp-38h]
  unsigned int *v55; // [rsp+38h] [rbp-30h]
  __int64 v56; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v57[4]; // [rsp+48h] [rbp-20h] BYREF
  LPCWSTR lpSubKey; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v59; // [rsp+C0h] [rbp+58h] BYREF
  LPSPropValue pProp; // [rsp+C8h] [rbp+60h] BYREF
  __int64 v61; // [rsp+E8h] [rbp+80h] BYREF
  va_list va; // [rsp+E8h] [rbp+80h]
  __int64 v63; // [rsp+F0h] [rbp+88h]
  va_list va1; // [rsp+F8h] [rbp+90h] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v61 = va_arg(va1, _QWORD);
  v63 = va_arg(va1, _QWORD);
  pProp = a4;
  *(_QWORD *)this = &CMapiStore::`vftable';
  CEntryId::CEntryId((CMapiStore *)((char *)this + 16), (struct CEntryId *)a3, (int *)a3);
  *((_QWORD *)this + 4) = 0;
  v10 = (_QWORD *)((char *)this + 40);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 40);
  v11 = (struct IUnknown **)((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 64);
  *((_DWORD *)this + 18) = 1;
  *((_DWORD *)this + 19) = 1;
  *((_QWORD *)this + 13) = 0;
  *(_QWORD *)((char *)this + 132) = 500;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 144);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 248,
    v12,
    v13,
    v14,
    LODWORD(FLOAT_2_25));
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(
    (_DWORD)this + 320,
    v15,
    v16,
    v17,
    v18);
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_DWORD *)this + 102) = 17;
  *((_QWORD *)this + 53) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 110) = 0;
  *((_DWORD *)this + 111) = 10;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_DWORD *)this + 103) = 1061158912;
  *((_DWORD *)this + 104) = 1048576000;
  *((_DWORD *)this + 105) = 1074790400;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds((char *)this + 392);
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_DWORD *)this + 120) = 17;
  *((_QWORD *)this + 62) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 63) = 0;
  *((_DWORD *)this + 128) = 0;
  *((_DWORD *)this + 129) = 10;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_DWORD *)this + 121) = v19;
  *((_DWORD *)this + 122) = v20;
  *((_DWORD *)this + 123) = v21;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds((char *)this + 464);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 536);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 544);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 552);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 560);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 568);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 576);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 584);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 592);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 600);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 608);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 616);
  *((_QWORD *)this + 79) = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)this + 664);
  *((_QWORD *)this + 78) = a2;
  *((_DWORD *)this + 30) = a6;
  v23 = *(_QWORD *)(a3 + 80);
  v24 = (_QWORD *)(v23 - 24);
  v25 = (int *)(*((_QWORD *)this + 5) - 24LL);
  if ( (int *)(v23 - 24) != v25 )
  {
    if ( v25[4] >= 0 && *v24 == *(_QWORD *)v25 )
    {
      v26 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v24);
      ATL::CStringData::Release((ATL::CStringData *)v25);
      *v10 = v26 + 24;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 40, v23, *(unsigned int *)(v23 - 16));
    }
  }
  LOBYTE(v22) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 248,
    257,
    v22);
  LOBYTE(v27) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 320,
    257,
    v27);
  LOBYTE(v28) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 392,
    257,
    v28);
  LOBYTE(v29) = 1;
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(
    (char *)this + 464,
    257,
    v29);
  if ( v61 )
    CMapiStore::GenerateDisplayName((char *)this + 40, v61, (char *)this + 64);
  else
    ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 64, &dword_1800444C4, 0);
  *((_DWORD *)this + 2) = 1;
  v30 = 0;
  v31 = a5;
  if ( !a5 )
    goto LABEL_17;
  v61 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a5->lpVtbl->QueryInterface)(
         a5,
         &IID_IProxyStoreObject,
         (__int64 *)va) >= 0 )
  {
    a5 = 0;
    if ( (*(int (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v61 + 32LL))(v61, &a5) < 0 )
    {
      CLogger::Error(-2147467259, L"Unable to unwrap PRXPST store");
    }
    else
    {
      if ( *v11 != a5 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 6, a5);
      v30 = 1;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)va);
  if ( !v30 )
  {
LABEL_17:
    if ( *v11 != v31 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 6, v31);
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 4);
  *((_DWORD *)this + 20) = *(_DWORD *)(a3 + 32);
  *((_DWORD *)this + 21) = *(_DWORD *)(a3 + 36);
  *((_DWORD *)this + 24) = *(_DWORD *)(a3 + 40);
  v32 = v30 || *(_DWORD *)(a3 + 44);
  *((_DWORD *)this + 23) = v32;
  *((_DWORD *)this + 22) = *(_DWORD *)(a3 + 48);
  *((_DWORD *)this + 31) = a7;
  *((_DWORD *)this + 25) = 0;
  *((_DWORD *)this + 28) = *(_DWORD *)(a3 + 52);
  *((_DWORD *)this + 29) = 0;
  *((_DWORD *)this + 32) = v63;
  if ( pProp )
  {
    if ( !*v11 )
      goto LABEL_44;
    CMapiSession::GetProfileNameDisplayName(pProp, (char *)this + 664);
  }
  if ( *v11 )
  {
    *((_DWORD *)this + 25) = CMapiStore::IsStorePusherEnabled(this);
    pProp = 0;
    if ( (int)CMapiStore::GetRootFolderorIPMSubTree(this, (struct IMAPIFolder **)&pProp, 1) < 0 )
    {
      CLogger::Error(L"CMapiStore::CMapiStore: Failed to fetch IPMSubtree");
    }
    else
    {
      *((_DWORD *)this + 27) = CMapiStore::IsDeepHierarchyNotificationSupported(this, (struct IMAPIFolder *)pProp);
      if ( !*((_DWORD *)this + 24)
        && (unsigned int)CMapiStore::IsICSSupported(this, (struct IMAPIFolder *)pProp)
        && *((_DWORD *)this + 27) )
      {
        *((_DWORD *)this + 26) = 1;
        if ( (*(int (__fastcall **)(LPSPropValue, __int64, char *))(*(_QWORD *)&pProp->ulPropTag + 120LL))(
               pProp,
               2147483649LL,
               (char *)this + 56) < 0 )
          CLogger::Error(L"CMapiStore::CMapiStore: Failed to get hierarchy table");
      }
      else
      {
        *((_DWORD *)this + 26) = 0;
      }
    }
    a6 = -1;
    if ( (int)CMapiSupport::CheckPolicy_DWORD(L"EnableThrottlingOnlineMailboxes", 0, &a6, 1, 1) >= 0 && a6 != -1 )
    {
      if ( a6 )
      {
        a6 = 0;
        if ( (int)CMapiSupport::CheckPolicy_DWORD(L"EnableThrottlingOnlineMailboxesValue", 0, &a6, 1, 1) >= 0 && a6 )
          *((_DWORD *)this + 33) = 0xEA60 / a6;
        else
          CLogger::Error(L"CMapistore::CMapiStore Failed to get Group Policy EnableThrottlingOnlineMailboxesValue");
      }
      else
      {
        *((_DWORD *)this + 33) = 0;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pProp);
  }
LABEL_44:
  if ( *((_DWORD *)this + 20) )
  {
    if ( *((_DWORD *)this + 28) )
    {
      a6 = 0;
      if ( (int)CMapiStore::GetOnlineStatus(this, (int *)&a6) >= 0 )
      {
        if ( a6 )
        {
          if ( *((_DWORD *)this + 24) )
          {
            *((_DWORD *)this + 29) = 1;
            if ( CLogger::m_fLoggingEnabled )
            {
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&pProp);
              CMapiStore::GetDisplayName(this, &pProp);
              v33 = pProp;
              CLogger::Info(L"CMapiStore::CMapiStore: Do not index offline classic OST {%s} when online", pProp);
LABEL_54:
              ATL::CStringData::Release((ATL::CStringData *)&v33[-1]);
            }
          }
        }
        else if ( !*((_DWORD *)this + 24) )
        {
          *((_DWORD *)this + 29) = 1;
          if ( CLogger::m_fLoggingEnabled )
          {
            ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&pProp);
            CMapiStore::GetDisplayName(this, &pProp);
            v33 = pProp;
            CLogger::Info(L"CMapiStore::CMapiStore: Do not index online classic OST {%s} when offline", pProp);
            goto LABEL_54;
          }
        }
      }
    }
  }
  *((_DWORD *)this + 35) = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&a5);
  CEntryId::ToByte(a3, &a5);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)va);
  CEntryId::ToByte(a3 + 16, (__int64 *)va);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&lpSubKey);
  CMapiStore::GetHashTableRegistryLocation(&lpSubKey);
  memset(v57, 0, 24);
  v34 = lpSubKey;
  if ( !(unsigned int)ATL::CRegKey::Create((ATL::CRegKey *)v57, HKEY_CURRENT_USER, lpSubKey, v35, v52, v53, v54, v55) )
  {
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      (__int64)&pProp,
      (const wchar_t *)&dword_1800444C4);
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsCached");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v57, (const wchar_t *)pProp, *((_DWORD *)this + 24));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsPublic");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v57, (const wchar_t *)pProp, *((_DWORD *)this + 21));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsExchange");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v57, (const wchar_t *)pProp, *((_DWORD *)this + 20));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(&pProp, L"%s.%s", *v10, L"IsPST");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v57, (const wchar_t *)pProp, *((_DWORD *)this + 23));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &pProp,
      L"%s.%s",
      *v10,
      L"IsDelegate");
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v57, (const wchar_t *)pProp, *((_DWORD *)this + 22));
    ATL::CStringData::Release((ATL::CStringData *)&pProp[-1]);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v57);
  CMapiStore::RecordHash((char *)this + 40, &a5, (__int64 *)va);
  if ( *((_DWORD *)this + 25) )
  {
    ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + 64, &dword_1800444C4, 0);
    CMapiStore::IsProviderExcluded(this);
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v56);
  CMapiStore::GetDisplayName(this, &v56);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v59);
  InstalledOutlookVersion = CMapiSupport::GetInstalledOutlookVersion(&v59);
  v37 = v59;
  if ( InstalledOutlookVersion < 0 )
    v38 = 0;
  else
    v38 = _o__wtol(v59);
  *((_DWORD *)this + 39) = v38;
  *((_QWORD *)this + 80) = 0;
  *((_DWORD *)this + 162) = 0;
  *((_DWORD *)this + 163) = GetCurrentProcessId();
  *((_DWORD *)this + 164) = GetTickCount();
  v39 = (LPMAPIPROP *)((char *)this + 48);
  if ( *((_QWORD *)this + 6) )
  {
    pProp = 0;
    MapiManager = CMapiManager::GetMapiManager((struct CMapiManager **)&pProp, 0);
    v42 = pProp;
    if ( MapiManager < 0 || !pProp[6].Value.cur.Hi || !*((_DWORD *)&pProp[6].Value.at + 2) )
    {
LABEL_92:
      if ( v42 )
        CMapiManager::ReleaseMapiManager(v41);
      goto LABEL_94;
    }
    if ( *((_DWORD *)this + 25) )
    {
      v43 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      pProp = (LPSPropValue)v43;
      if ( v43 )
      {
        *(_QWORD *)v43 = &CMapiStore::CPusherAdvise::`vftable';
        *((_DWORD *)v43 + 2) = 1;
        *((_QWORD *)v43 + 7) = this;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v43 + 16));
      }
      else
      {
        v43 = 0;
      }
      v44 = (_QWORD *)((char *)this + 632);
      if ( *((char **)this + 79) != v43 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 79, (struct IUnknown *)v43);
      v45 = 0;
      if ( *v44 )
      {
        if ( ((int (__fastcall *)(LPMAPIPROP, _QWORD, _QWORD, __int64, _QWORD, char *))(*v39)->lpVtbl[1].QueryInterface)(
               *v39,
               0,
               0,
               0x10000,
               *v44,
               (char *)this + 640) >= 0 )
        {
          pProp = 0;
          if ( HrGetOneProp(*v39, 0x34190003u, &pProp) )
          {
            if ( *((_DWORD *)this + 161) )
            {
LABEL_86:
              CLogger::Info(L"Store watcher added successfully to %s", *((_QWORD *)this + 8));
              goto LABEL_92;
            }
            do
            {
              if ( v45 >= 5 )
                break;
              ++v45;
              Sleep(0xC8u);
            }
            while ( !*((_DWORD *)this + 161) );
          }
          else
          {
            v46 = pProp;
            if ( pProp->ulPropTag == 874053635 )
            {
              ul = pProp->Value.ul;
              if ( (_DWORD)ul )
              {
                if ( (unsigned int)CMapiManager::AddStoreWatcher(*((_QWORD *)this + 78), ul, (char *)this + 40) )
                {
                  *((_DWORD *)this + 161) = 1;
                  v48 = pProp;
                  *((_DWORD *)this + 162) = pProp->Value.l;
                  CLogger::Info(
                    L"Store %s is waiting on process (%u) - via GetProps()",
                    *((_QWORD *)this + 8),
                    v48->Value.ul);
                }
                v46 = pProp;
              }
            }
            MAPIFreeBuffer(v46);
          }
        }
      }
      else
      {
        CLogger::Error(-2147024882, L"Unable to create CPusherAdvise()");
      }
    }
    else if ( (unsigned int)CMapiManager::AddStoreWatcher(pProp, 0, (char *)this + 40) )
    {
      *((_DWORD *)this + 161) = 1;
    }
    if ( !*((_DWORD *)this + 161) )
    {
      CMapiStore::RemoveAllSinks(this);
      CMapiStore::RemoveMapiManager(this);
      v49 = *v39;
      *v39 = 0;
      ((void (__fastcall *)(LPMAPIPROP))v49->lpVtbl->Release)(v49);
      if ( *v39 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 6, 0);
      CLogger::Warning(L"Store watcher add failed for %s", *((_QWORD *)this + 8));
      goto LABEL_92;
    }
    goto LABEL_86;
  }
LABEL_94:
  v50 = v56;
  CLogger::Info(L"CMapiStore::CMapiStore(%s) Created", v56);
  ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v34 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v61 - 24));
  ATL::CStringData::Release((ATL::CStringData *)&a5[-3]);
  return this;
}

```

## disassembly

```asm
0x180032328  mov     [rsp-40h+pProp], r9
0x18003232d  mov     [rsp-40h+arg_0], rcx
0x180032332  push    rbp
0x180032333  push    rbx
0x180032334  push    rsi
0x180032335  push    rdi
0x180032336  push    r12
0x180032338  push    r13
0x18003233a  push    r14
0x18003233c  push    r15
0x18003233e  mov     rbp, rsp
0x180032341  sub     rsp, 68h
0x180032345  mov     rdi, r8
0x180032348  mov     rbx, rdx
0x18003234b  mov     r14, rcx
0x18003234e  lea     rax, ??_7CMapiStore@@6B@; const CMapiStore::`vftable'
0x180032355  mov     [rcx], rax
0x180032358  add     rcx, 10h; this
0x18003235c  mov     rdx, r8; struct CEntryId *
0x18003235f  call    ??0CEntryId@@QEAA@AEAV0@PEAJ@Z; CEntryId::CEntryId(CEntryId &,long *)
0x180032364  nop
0x180032365  xor     r15d, r15d
0x180032368  mov     [r14+20h], r15
0x18003236c  lea     r12, [r14+28h]
0x180032370  mov     rcx, r12
0x180032373  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032378  nop
0x180032379  lea     rsi, [r14+30h]
0x18003237d  mov     [rsi], r15
0x180032380  mov     [r14+38h], r15
0x180032384  lea     rcx, [r14+40h]
0x180032388  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18003238d  nop
0x18003238e  lea     eax, [r15+1]
0x180032392  mov     [r14+48h], eax
0x180032396  mov     [r14+4Ch], eax
0x18003239a  mov     [r14+68h], r15
0x18003239e  mov     qword ptr [r14+84h], 1F4h
0x1800323a9  lea     rcx, [r14+90h]
0x1800323b0  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800323b5  nop
0x1800323b6  mov     [r14+0C8h], r15
0x1800323bd  mov     [r14+0D0h], r15
0x1800323c4  mov     [r14+0D8h], r15
0x1800323cb  mov     [r14+0E0h], r15
0x1800323d2  mov     [r14+0E8h], r15
0x1800323d9  mov     [r14+0F0h], r15
0x1800323e0  lea     rcx, [r14+0F8h]
0x1800323e7  movss   xmm5, cs:__real@40100000
0x1800323ef  movss   [rsp+68h+var_48], xmm5
0x1800323f5  movss   xmm3, cs:__real@3e800000
0x1800323fd  movss   xmm4, cs:__real@3f400000
0x180032405  movaps  xmm2, xmm4
0x180032408  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x18003240d  nop
0x18003240e  lea     rcx, [r14+140h]
0x180032415  movss   [rsp+68h+var_48], xmm5
0x18003241b  movaps  xmm2, xmm4
0x18003241e  call    ??0?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiSession@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiSession@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiSession *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiSession *>>(uint,float,float,float,uint)
0x180032423  nop
0x180032424  lea     r13, [r14+188h]
0x18003242b  mov     [r13+0], r15
0x18003242f  mov     [r13+8], r15
0x180032433  mov     dword ptr [r13+10h], 11h
0x18003243b  mov     eax, 0FFFFFFFFh
0x180032440  mov     [r13+20h], rax
0x180032444  mov     [r13+28h], r15
0x180032448  mov     [r13+30h], r15d
0x18003244c  mov     r15d, 0Ah
0x180032452  mov     [r13+34h], r15d
0x180032456  mov     qword ptr [r13+38h], 0
0x18003245e  mov     qword ptr [r13+40h], 0
0x180032466  mov     r11d, 3F400000h
0x18003246c  mov     [r13+14h], r11d
0x180032470  mov     r10d, 3E800000h
0x180032476  mov     [r13+18h], r10d
0x18003247a  mov     r9d, 40100000h
0x180032480  mov     [r13+1Ch], r9d
0x180032484  mov     rcx, r13
0x180032487  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds(void)
0x18003248c  nop
0x18003248d  lea     rax, [r14+1D0h]
0x180032494  xor     ecx, ecx
0x180032496  mov     [rax], rcx
0x180032499  mov     [rax+8], rcx
0x18003249d  mov     dword ptr [rax+10h], 11h
0x1800324a4  mov     edx, 0FFFFFFFFh
0x1800324a9  mov     [rax+20h], rdx
0x1800324ad  mov     [rax+28h], rcx
0x1800324b1  mov     [rax+30h], ecx
0x1800324b4  mov     [rax+34h], r15d
0x1800324b8  mov     [rax+38h], rcx
0x1800324bc  mov     [rax+40h], rcx
0x1800324c0  mov     [rax+14h], r11d
0x1800324c4  mov     [rax+18h], r10d
0x1800324c8  mov     [rax+1Ch], r9d
0x1800324cc  mov     rcx, rax
0x1800324cf  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::UpdateRehashThresholds(void)
0x1800324d4  nop
0x1800324d5  lea     rcx, [r14+218h]
0x1800324dc  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800324e1  nop
0x1800324e2  lea     rcx, [r14+220h]
0x1800324e9  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800324ee  nop
0x1800324ef  lea     rcx, [r14+228h]
0x1800324f6  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800324fb  nop
0x1800324fc  lea     rcx, [r14+230h]
0x180032503  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032508  nop
0x180032509  lea     rcx, [r14+238h]
0x180032510  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032515  nop
0x180032516  lea     rcx, [r14+240h]
0x18003251d  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032522  nop
0x180032523  lea     rcx, [r14+248h]
0x18003252a  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18003252f  nop
0x180032530  lea     rcx, [r14+250h]
0x180032537  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18003253c  nop
0x18003253d  lea     rcx, [r14+258h]
0x180032544  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032549  nop
0x18003254a  lea     rcx, [r14+260h]
0x180032551  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032556  nop
0x180032557  lea     rcx, [r14+268h]
0x18003255e  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180032563  nop
0x180032564  mov     qword ptr [r14+278h], 0
0x18003256f  lea     rcx, [r14+298h]
0x180032576  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18003257b  nop
0x18003257c  mov     [r14+270h], rbx
0x180032583  mov     eax, [rbp+arg_28]
0x180032586  mov     [r14+78h], eax
0x18003258a  mov     rdx, [rdi+50h]
0x18003258e  lea     rcx, [rdx-18h]
0x180032592  mov     r15, [r12]
0x180032596  add     r15, 0FFFFFFFFFFFFFFE8h
0x18003259a  cmp     rcx, r15
0x18003259d  jz      short loc_1800325D4
0x18003259f  cmp     dword ptr [r15+10h], 0
0x1800325a4  jl      short loc_1800325C8
0x1800325a6  mov     rax, [r15]
0x1800325a9  cmp     [rcx], rax
0x1800325ac  jnz     short loc_1800325C8
0x1800325ae  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x1800325b3  mov     rbx, rax
0x1800325b6  mov     rcx, r15; this
0x1800325b9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800325be  lea     rax, [rbx+18h]
0x1800325c2  mov     [r12], rax
0x1800325c6  jmp     short loc_1800325D4
0x1800325c8  mov     r8d, [rdx-10h]
0x1800325cc  mov     rcx, r12
0x1800325cf  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800325d4  mov     r8b, 1
0x1800325d7  mov     ebx, 101h
0x1800325dc  mov     edx, ebx
0x1800325de  lea     rcx, [r14+0F8h]
0x1800325e5  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x1800325ea  mov     r8b, 1
0x1800325ed  mov     edx, ebx
0x1800325ef  lea     rcx, [r14+140h]
0x1800325f6  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x1800325fb  mov     r8b, 1
0x1800325fe  mov     edx, ebx
0x180032600  mov     rcx, r13
0x180032603  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x180032608  mov     r8b, 1
0x18003260b  mov     edx, ebx
0x18003260d  lea     rcx, [r14+1D0h]
0x180032614  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::InitHashTable(uint,bool)
0x180032619  mov     rdx, [rbp+arg_38]
0x180032620  lea     r13, [r14+40h]
0x180032624  test    rdx, rdx
0x180032627  jz      short loc_180032636
0x180032629  mov     r8, r13
0x18003262c  mov     rcx, r12
0x18003262f  call    ?GenerateDisplayName@CMapiStore@@SAXAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@00@Z; CMapiStore::GenerateDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180032634  jmp     short loc_180032648
0x180032636  xor     r8d, r8d
0x180032639  lea     rdx, dword_1800444C4
0x180032640  mov     rcx, r13
0x180032643  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180032648  mov     dword ptr [r14+8], 1
0x180032650  xor     r15d, r15d
0x180032653  mov     rbx, [rbp+arg_20]
0x180032657  test    rbx, rbx
0x18003265a  jz      loc_1800326E2
0x180032660  mov     [rbp+arg_38], r15
0x180032667  mov     rax, [rbx]
0x18003266a  lea     r8, [rbp+arg_38]
0x180032671  lea     rdx, IID_IProxyStoreObject
0x180032678  mov     rcx, rbx
0x18003267b  mov     rax, [rax]
0x18003267e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032683  test    eax, eax
0x180032685  js      short loc_1800326D1
0x180032687  mov     [rbp+arg_20], r15
0x18003268b  mov     rcx, [rbp+arg_38]
0x180032692  mov     rax, [rcx]
0x180032695  lea     rdx, [rbp+arg_20]
0x180032699  mov     rax, [rax+20h]
0x18003269d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326a2  test    eax, eax
0x1800326a4  js      short loc_1800326BF
0x1800326a6  mov     rdx, [rbp+arg_20]; struct IUnknown *
0x1800326aa  cmp     [rsi], rdx
0x1800326ad  jz      short loc_1800326B7
0x1800326af  mov     rcx, rsi; struct IUnknown **
0x1800326b2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800326b7  mov     r15d, 1
0x1800326bd  jmp     short loc_1800326D1
0x1800326bf  lea     rdx, aUnableToUnwrap; "Unable to unwrap PRXPST store"
0x1800326c6  mov     ecx, 80004005h; int
0x1800326cb  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x1800326d0  nop
0x1800326d1  lea     rcx, [rbp+arg_38]
0x1800326d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800326dd  test    r15d, r15d
0x1800326e0  jnz     short loc_1800326F2
0x1800326e2  cmp     [rsi], rbx
0x1800326e5  jz      short loc_1800326F2
0x1800326e7  mov     rdx, rbx; struct IUnknown *
0x1800326ea  mov     rcx, rsi; struct IUnknown **
0x1800326ed  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800326f2  lea     rcx, [r14+0A0h]; lpCriticalSection
0x1800326f9  call    cs:__imp_InitializeCriticalSection
0x1800326ff  mov     eax, [rdi+20h]
0x180032702  mov     [r14+50h], eax
0x180032706  mov     eax, [rdi+24h]
0x180032709  mov     [r14+54h], eax
0x18003270d  mov     eax, [rdi+28h]
0x180032710  mov     [r14+60h], eax
0x180032714  xor     ebx, ebx
0x180032716  test    r15d, r15d
0x180032719  jnz     short loc_180032728
0x18003271b  cmp     [rdi+2Ch], ebx
0x18003271e  jnz     short loc_180032728
0x180032720  mov     eax, ebx
0x180032722  lea     r15d, [rbx+1]
0x180032726  jmp     short loc_180032731
0x180032728  mov     r15d, 1
0x18003272e  mov     eax, r15d
0x180032731  mov     [r14+5Ch], eax
0x180032735  mov     eax, [rdi+30h]
0x180032738  mov     [r14+58h], eax
0x18003273c  mov     eax, [rbp+arg_30]
0x18003273f  mov     [r14+7Ch], eax
0x180032743  mov     [r14+64h], ebx
0x180032747  mov     eax, [rdi+34h]
0x18003274a  mov     [r14+70h], eax
0x18003274e  mov     [r14+74h], ebx
0x180032752  mov     eax, dword ptr [rbp+arg_40]
0x180032758  mov     [r14+80h], eax
0x18003275f  mov     rax, [rbp+pProp]
0x180032763  test    rax, rax
0x180032766  jz      short loc_180032780
0x180032768  cmp     [rsi], rbx
0x18003276b  jz      loc_18003289D
0x180032771  lea     rdx, [r14+298h]
0x180032778  mov     rcx, rax
0x18003277b  call    ?GetProfileNameDisplayName@CMapiSession@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::GetProfileNameDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180032780  cmp     [rsi], rbx
0x180032783  jz      loc_18003289D
0x180032789  mov     rcx, r14; this
0x18003278c  call    ?IsStorePusherEnabled@CMapiStore@@AEAAHXZ; CMapiStore::IsStorePusherEnabled(void)
0x180032791  mov     [r14+64h], eax
0x180032795  mov     [rbp+pProp], rbx
0x180032799  mov     r8d, r15d; int
0x18003279c  lea     rdx, [rbp+pProp]; struct IMAPIFolder **
0x1800327a0  mov     rcx, r14; this
0x1800327a3  call    ?GetRootFolderorIPMSubTree@CMapiStore@@QEAAJPEAPEAUIMAPIFolder@@H@Z; CMapiStore::GetRootFolderorIPMSubTree(IMAPIFolder * *,int)
0x1800327a8  test    eax, eax
0x1800327aa  js      short loc_180032808
0x1800327ac  mov     rdx, [rbp+pProp]; struct IMAPIFolder *
0x1800327b0  mov     rcx, r14; this
0x1800327b3  call    ?IsDeepHierarchyNotificationSupported@CMapiStore@@AEAAHPEAUIMAPIFolder@@@Z; CMapiStore::IsDeepHierarchyNotificationSupported(IMAPIFolder *)
0x1800327b8  mov     [r14+6Ch], eax
0x1800327bc  cmp     [r14+60h], ebx
0x1800327c0  jnz     short loc_180032802
0x1800327c2  mov     rdx, [rbp+pProp]; struct IMAPIFolder *
0x1800327c6  mov     rcx, r14; this
0x1800327c9  call    ?IsICSSupported@CMapiStore@@AEAAHPEAUIMAPIFolder@@@Z; CMapiStore::IsICSSupported(IMAPIFolder *)
0x1800327ce  test    eax, eax
0x1800327d0  jz      short loc_180032802
0x1800327d2  cmp     [r14+6Ch], ebx
0x1800327d6  jz      short loc_180032802
0x1800327d8  mov     [r14+68h], r15d
0x1800327dc  mov     rcx, [rbp+pProp]
0x1800327e0  mov     rax, [rcx]
0x1800327e3  lea     r8, [r14+38h]
0x1800327e7  mov     edx, 80000001h
0x1800327ec  mov     rax, [rax+78h]
0x1800327f0  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
