# WindowsInternal::Shell::UnifiedTile::AllTilesCollection::RuntimeClassInitialize(DataStoreCache::IDataManager *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *,WindowsInternal::Shell::UnifiedTile::AllTilesCollection::FilterKind)

- ea: `0x180045838`
- end: `0x180046760`
- name: `?RuntimeClassInitialize@AllTilesCollection@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUIDataManager@DataStoreCache@@PEAUIUnifiedTileManager@234@W4FilterKind@1234@@Z`
- size: `3880`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009902c`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18001f0a0`
- `0x180020474`
- `0x180021b78`
- `0x180030e28`
- `0x180037d34`
- `0x180037f6c`
- `0x18003ab30`
- `0x1800433a4`
- `0x180043530`
- `0x1800435b0`
- `0x180045678`
- `0x180045838`
- `0x180046874`
- `0x180046d90`
- `0x180046eb0`
- `0x180046f34`
- `0x1800474d8`
- `0x18004766c`
- `0x180075c30`
- `0x18007a720`
- `0x1800a4db8`
- `0x180161204`
- `0x18020be0c`
- `0x1802eb3dc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004598c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004598c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800464e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800464e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045f17`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045f17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045ec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045eed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045ec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045eed`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800458ba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180045ada`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800458ba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180045ada`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800464f7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800464f7`

## string_xrefs

- `0x180046195`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilehelpers.cpp`
- `0x180046339`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilehelpers.cpp`
- `0x180046375`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilehelpers.cpp`
- `0x1800466e4`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilehelpers.cpp`
- `0x180046164`: `shellcommon\shell\tiles\unifiedtilemodel\lib\collectiontile.cpp`
- `0x1800463e3`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x180046406`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x180046445`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18004648f`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18004664f`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18004666d`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x180046686`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`
- `0x18004673b`: `shellcommon\shell\tiles\unifiedtilemodel\lib\alltilescollection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::AllTilesCollection::RuntimeClassInitialize(
        HSTRING a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        int a4)
{
  __int64 (__fastcall ***v5)(_QWORD, GUID *, _QWORD *); // r15
  HSTRING v7; // r12
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  HRESULT Guid; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // rcx
  int v15; // eax
  unsigned int v16; // ebx
  RTL_SRWLOCK *v17; // rsi
  _QWORD *v18; // r14
  _QWORD *v19; // rdi
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // r13
  __int64 v21; // rcx
  WindowsInternal::Shell::UnifiedTile **v22; // rax
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **v23; // r8
  int Instance; // ebx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // r12
  WindowsInternal::Shell::UnifiedTile::CollectionTile *v28; // rax
  __int64 v29; // r15
  HRESULT v30; // ebx
  __int64 v31; // rcx
  __int64 v32; // rcx
  volatile int *v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  signed __int64 v41; // rax
  signed __int64 v42; // rtt
  __int64 v43; // rcx
  int v44; // eax
  __int64 (__fastcall ***v45)(_QWORD, GUID *, _QWORD *); // r15
  int v46; // eax
  wil::details::in1diag3 *v47; // rcx
  __int64 v48; // rcx
  char v49; // bl
  __int64 (__fastcall ***v50)(_QWORD, GUID *, _QWORD *); // rcx
  DataStoreCache::DataItemIdentifier *v51; // r15
  __int64 v52; // rdx
  __int64 v53; // rbx
  HSTRING v54; // rax
  _QWORD *v55; // r13
  __int64 v56; // r13
  const WCHAR *StringRawBuffer; // r15
  const WCHAR *v58; // rax
  volatile signed __int64 *v59; // rax
  __int64 v60; // rcx
  volatile signed __int64 *v61; // r10
  signed __int64 v62; // rax
  unsigned int v63; // ecx
  signed __int64 v64; // rtt
  __int64 v65; // rdx
  float v66; // xmm0_4
  __int64 v67; // rcx
  float v68; // xmm1_4
  __int64 *v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rcx
  _QWORD *v72; // r8
  __int64 v73; // rbx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // rcx
  _QWORD *v80; // r15
  _QWORD *v81; // r13
  __int64 (__fastcall *v82)(_QWORD, _QWORD); // rbx
  int v83; // eax
  wil::details::in1diag3 *v84; // rcx
  __int64 (__fastcall ***v85)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rdx
  const char *v89; // r9
  __int64 result; // rax
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 (__fastcall ***v93)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v94)(_QWORD, GUID *, __int64 *); // r15
  int v95; // eax
  wil::details::in1diag3 *v96; // rcx
  __int64 v97; // rcx
  __int64 (__fastcall *v98)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64 *); // rbx
  int v99; // eax
  wil::details::in1diag3 *v100; // rcx
  __int64 v101; // rdx
  __int64 v102; // rdx
  __int64 v103; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-198h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-198h]
  volatile signed __int64 *v106; // [rsp+30h] [rbp-188h] BYREF
  __int64 v107; // [rsp+38h] [rbp-180h] BYREF
  int v108; // [rsp+40h] [rbp-178h] BYREF
  __int64 v109; // [rsp+48h] [rbp-170h] BYREF
  HSTRING__ v110[2]; // [rsp+50h] [rbp-168h] BYREF
  __int64 (__fastcall ***v111)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-160h] BYREF
  UINT32 length[2]; // [rsp+60h] [rbp-158h] BYREF
  __int64 v113; // [rsp+68h] [rbp-150h] BYREF
  __int64 v114; // [rsp+70h] [rbp-148h] BYREF
  __int64 v115; // [rsp+78h] [rbp-140h] BYREF
  __int64 (__fastcall ***v116)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-138h] BYREF
  HSTRING *v117; // [rsp+88h] [rbp-130h] BYREF
  HSTRING v118; // [rsp+90h] [rbp-128h] BYREF
  UINT32 v119; // [rsp+98h] [rbp-120h] BYREF
  __int64 v120; // [rsp+A0h] [rbp-118h] BYREF
  __int64 v121; // [rsp+A8h] [rbp-110h] BYREF
  __int64 v122; // [rsp+B0h] [rbp-108h] BYREF
  __int64 v123; // [rsp+B8h] [rbp-100h] BYREF
  unsigned __int64 v124; // [rsp+C0h] [rbp-F8h] BYREF
  HSTRING string[2]; // [rsp+C8h] [rbp-F0h] BYREF
  __int64 v126; // [rsp+D8h] [rbp-E0h]
  HSTRING v127; // [rsp+E0h] [rbp-D8h]
  _BYTE v128[80]; // [rsp+F0h] [rbp-C8h] BYREF
  char v129[8]; // [rsp+140h] [rbp-78h] BYREF
  _QWORD *v130; // [rsp+148h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]
  int v134; // [rsp+1D8h] [rbp+20h] BYREF

  v5 = a3;
  v7 = a1;
  UnifiedTileTelemetry::WatchCurrentThread(v128, "AllTilesCollection_RuntimeClassInitialize");
  *((_DWORD *)v7 + 42) = a4;
  v118 = v7 + 36;
  v8 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v118);
  v9 = Microsoft::WRL::AsWeak<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager>(v5, v8);
  try
  {
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v128);
      return v10;
    }
    Guid = CoCreateGuid((GUID *)(v7 + 46));
    v12 = Guid;
    if ( Guid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
        (const char *)(unsigned int)Guid,
        bIgnoreCase);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v128);
      return v12;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)a2 + 24LL))(a2, &v111, &TileData);
    Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>::operator=(v7 + 38, v13);
    v14 = v111;
    if ( v111 )
    {
      v111 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v14)[2])(v14);
    }
    Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=(v7 + 40, a2);
    v109 = 0;
    v118 = v7;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
    v15 = Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::DataItemEventHandlerWrapper,IDataItemEventHandler,WindowsInternal::Shell::UnifiedTile::AllTilesCollection *>(
            &v109,
            &v118);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCase);
      v91 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      }
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v128);
      result = v16;
    }
    else
    {
      *(_DWORD *)(v7 + 50) = *(_DWORD *)(HSTRING)(*(__int64 (__fastcall **)(_QWORD, int *, __int64))(**((_QWORD **)v7 + 20) + 40LL))(
                                                   *((_QWORD *)v7 + 20),
                                                   &v134,
                                                   v109);
      v17 = (RTL_SRWLOCK *)(v7 + 44);
      AcquireSRWLockExclusive((PSRWLOCK)v7 + 22);
      v127 = v7 + 44;
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v7 + 19) + 32LL))(*((_QWORD *)v7 + 19), v129);
      v18 = v130;
      v19 = (_QWORD *)*v130;
      while ( v19 != v18 )
      {
        v106 = 0;
        Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v106);
        v20 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))((unsigned __int64)(v7 + 4) & -(__int64)(v7 != 0));
        v117 = (HSTRING *)(v19 + 3);
        v21 = v19[3];
        v106 = 0;
        v115 = 0;
        *(_QWORD *)&v110[0].unused = 0;
        v22 = (WindowsInternal::Shell::UnifiedTile **)(*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 32LL))(
                                                        v21,
                                                        string);
        Instance = WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifier_CreateInstance(*v22, v110, v23);
        WindowsDeleteString(string[0]);
        string[0] = 0;
        if ( Instance < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x92,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilehelpers.cpp",
            (const char *)(unsigned int)Instance,
            bIgnoreCase);
          v86 = *(_QWORD *)&v110[0].unused;
          if ( *(_QWORD *)&v110[0].unused )
          {
            *(_QWORD *)&v110[0].unused = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
          }
        }
        else
        {
          v25 = (*v5)[9](v5, *(GUID **)&v110[0].unused, &v115);
          Instance = v25;
          if ( v25 >= 0 )
          {
            v26 = *(_QWORD *)&v110[0].unused;
            if ( *(_QWORD *)&v110[0].unused )
            {
              *(_QWORD *)&v110[0].unused = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            }
            v27 = v115;
            if ( !v115 )
              goto LABEL_53;
            v106 = 0;
            v28 = (WindowsInternal::Shell::UnifiedTile::CollectionTile *)operator new(
                                                                           0xA8u,
                                                                           (const struct std::nothrow_t *)std::nothrow);
            *(_QWORD *)length = v28;
            if ( v28 )
            {
              v29 = WindowsInternal::Shell::UnifiedTile::CollectionTile::CollectionTile(v28);
              v124 = v29;
              *(_QWORD *)length = 0;
              v30 = CoCreateGuid((GUID *)(v29 + 80));
              if ( v30 < 0 )
              {
                v77 = 23;
                goto LABEL_107;
              }
              if ( *(_QWORD *)(v29 + 96) != v27 )
              {
                if ( v27 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
                v31 = *(_QWORD *)(v29 + 96);
                *(_QWORD *)(v29 + 96) = v27;
                if ( v31 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              }
              v32 = *(_QWORD *)(v29 + 104);
              *(_QWORD *)(v29 + 104) = 0;
              if ( v32 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
              v107 = 0;
              v30 = (**v20)(v20, &GUID_00000038_0000_0000_c000_000000000046, &v107);
              if ( v30 < 0 )
              {
                v35 = v107;
                if ( v107 )
                  goto LABEL_28;
              }
              else
              {
                v113 = 0;
                v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v107 + 24LL))(v107, &v113);
                if ( v30 >= 0 )
                {
                  v73 = v113;
                  if ( v113 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 8LL))(v113);
                  v74 = *(_QWORD *)(v29 + 104);
                  *(_QWORD *)(v29 + 104) = v73;
                  if ( v74 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
                  v75 = v113;
                  if ( v113 )
                  {
                    v113 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
                  }
                  v76 = v107;
                  if ( v107 )
                  {
                    v107 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
                  }
                  v30 = 0;
                }
                else
                {
                  v34 = v113;
                  if ( v113 )
                  {
                    v113 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                  }
                  v35 = v107;
                  if ( v107 )
                  {
LABEL_28:
                    v107 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                  }
                }
              }
              if ( v30 < 0 )
              {
                v77 = 25;
                goto LABEL_107;
              }
              if ( !a3 )
                goto LABEL_45;
              v36 = *(_QWORD *)(v29 + 128);
              *(_QWORD *)(v29 + 128) = 0;
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              v114 = 0;
              v30 = (**a3)(a3, &GUID_00000038_0000_0000_c000_000000000046, &v114);
              if ( v30 >= 0 )
              {
                v120 = 0;
                v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v114 + 24LL))(v114, &v120);
                if ( v30 >= 0 )
                {
                  v37 = v120;
                  if ( v120 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 8LL))(v120);
                  v38 = *(_QWORD *)(v29 + 128);
                  *(_QWORD *)(v29 + 128) = v37;
                  if ( v38 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                  v39 = v120;
                  if ( v120 )
                  {
                    v120 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                  }
                  v40 = v114;
                  if ( v114 )
                  {
                    v114 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                  }
                  v30 = 0;
LABEL_44:
                  if ( v30 >= 0 )
                  {
LABEL_45:
                    if ( v29 )
                    {
                      v41 = *(_QWORD *)(v29 + 56);
                      while ( v41 >= 0 )
                      {
                        if ( (_DWORD)v41 != 0x7FFFFFFF )
                        {
                          v42 = v41;
                          v41 = _InterlockedCompareExchange64((volatile signed __int64 *)(v29 + 56), v41 + 1, v41);
                          if ( v42 != v41 )
                            continue;
                        }
                        goto LABEL_50;
                      }
                      Microsoft::WRL::Details::SafeUnknownIncrementReference(
                        (Microsoft::WRL::Details *)(2 * v41 + 16),
                        v33);
LABEL_50:
                      v106 = (volatile signed __int64 *)v29;
                      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ICollectionTile,Microsoft::WRL::FtmBase>::Release(v29);
                    }
                    else
                    {
                      v106 = 0;
                    }
LABEL_51:
                    v43 = v115;
                    if ( v115 )
                    {
                      v115 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                    }
LABEL_53:
                    v7 = a1;
                    goto LABEL_54;
                  }
                  v77 = 29;
LABEL_107:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v77,
                    (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\collectiontile.cpp",
                    (const char *)(unsigned int)v30,
                    bIgnoreCase);
                  Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v124);
LABEL_108:
                  Microsoft::WRL::Details::MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>::~MakeAllocator<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileGroup>(length);
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xA3,
                    (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilehelpers.cpp",
                    (const char *)(unsigned int)v30,
                    bIgnoreCase);
                  goto LABEL_51;
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v120);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v114);
              goto LABEL_44;
            }
            v30 = -2147024882;
            goto LABEL_108;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x93,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilehelpers.cpp",
            (const char *)(unsigned int)v25,
            bIgnoreCase);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v110);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA1,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilehelpers.cpp",
          (const char *)(unsigned int)Instance,
          bIgnoreCasea);
        v87 = v115;
        if ( v115 )
        {
          v115 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
        }
LABEL_54:
        if ( !v106 )
          goto LABEL_78;
        v111 = 0;
        v44 = (*(__int64 (__fastcall **)(volatile signed __int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*v106 + 64))(
                v106,
                &v111);
        if ( v44 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
            (const char *)(unsigned int)v44,
            bIgnoreCase);
          goto LABEL_176;
        }
        if ( !*((_DWORD *)v7 + 42) )
        {
          LOBYTE(v134) = 1;
LABEL_63:
          v49 = 1;
          goto LABEL_64;
        }
        v45 = v111;
        LOBYTE(v134) = 0;
        v123 = 0;
        v46 = (**v111)(v111, &GUID_de10b7d8_bebd_4599_925d_759462d1c1b1, &v123);
        v47 = retaddr;
        if ( v46 < 0 )
        {
          v88 = 96;
LABEL_136:
          wil::details::in1diag3::_Log_Hr(
            v47,
            (void *)v88,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
            (const char *)(unsigned int)v46,
            bIgnoreCase);
          goto LABEL_59;
        }
        v46 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v123 + 48LL))(v123, &v134);
        v47 = retaddr;
        if ( v46 < 0 )
        {
          v88 = 98;
          goto LABEL_136;
        }
LABEL_59:
        if ( (_BYTE)v134 || *((_DWORD *)v7 + 42) != 2 )
          goto LABEL_60;
        v116 = 0;
        v108 = 0;
        v82 = (__int64 (__fastcall *)(_QWORD, _QWORD))(*v45)[6];
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v116);
        v83 = v82(v45, &v116);
        v84 = retaddr;
        if ( v83 < 0
          || (v83 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), int *))(*v116)[6])(
                      v116,
                      &v108),
              v84 = retaddr,
              v83 < 0) )
        {
          wil::details::in1diag3::_Log_Hr(
            v84,
            (void *)0x69,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
            (const char *)(unsigned int)v83,
            bIgnoreCase);
          goto LABEL_126;
        }
        if ( v108 == 1 )
        {
          v121 = 0;
          v93 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v116;
          v94 = **v116;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v121);
          v95 = v94(v93, &GUID_a7668288_cc23_4b67_be8b_6c10455986b8, &v121);
          v96 = retaddr;
          if ( v95 < 0 )
          {
            v101 = 110;
          }
          else
          {
            v95 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v121 + 64LL))(v121, &v134);
            v96 = retaddr;
            if ( v95 >= 0 )
            {
LABEL_153:
              v97 = v121;
              if ( !v121 )
                goto LABEL_126;
              v121 = 0;
              goto LABEL_155;
            }
            v101 = 112;
          }
          wil::details::in1diag3::_Log_Hr(
            v96,
            (void *)v101,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
            (const char *)(unsigned int)v95,
            bIgnoreCase);
          goto LABEL_153;
        }
        if ( v108 != 2 )
          goto LABEL_126;
        v122 = 0;
        v98 = (__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64 *))(*v45)[12];
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v122);
        v99 = v98(v45, &v122);
        v100 = retaddr;
        if ( v99 < 0 )
        {
          v102 = 118;
LABEL_165:
          wil::details::in1diag3::_Log_Hr(
            v100,
            (void *)v102,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
            (const char *)(unsigned int)v99,
            bIgnoreCase);
          goto LABEL_159;
        }
        if ( v122 )
        {
          v99 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v122 + 72LL))(v122, &v134);
          v100 = retaddr;
          if ( v99 < 0 )
          {
            v102 = 120;
            goto LABEL_165;
          }
        }
LABEL_159:
        v97 = v122;
        if ( v122 )
        {
          v122 = 0;
LABEL_155:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        }
LABEL_126:
        v85 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v116;
        if ( v116 )
        {
          v116 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v85)[2])(v85);
        }
LABEL_60:
        v48 = v123;
        if ( v123 )
        {
          v123 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        }
        if ( (_BYTE)v134 )
          goto LABEL_63;
LABEL_176:
        v49 = 0;
LABEL_64:
        v50 = v111;
        if ( v111 )
        {
          v111 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v50)[2])(v50);
        }
        if ( v49 )
        {
          v51 = (DataStoreCache::DataItemIdentifier *)(*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*v117 + 32LL))(
                                                        *v117,
                                                        &v118);
          v117 = (HSTRING *)v51;
          v124 = DataStoreCache::DataItemIdentifier::Hash(v51);
          v52 = *((_QWORD *)v7 + 13);
          v53 = *(_QWORD *)(v52 + 16 * (v124 & *((_QWORD *)v7 + 16)) + 8);
          v54 = v7 + 22;
          v55 = (_QWORD *)*((_QWORD *)v7 + 11);
          if ( (_QWORD *)v53 != v55 )
          {
            v56 = *(_QWORD *)(v52 + 16 * (v124 & *((_QWORD *)v7 + 16)));
            while ( 1 )
            {
              length[0] = 0;
              StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v53 + 16), length);
              v119 = 0;
              v58 = WindowsGetStringRawBuffer(*v117, &v119);
              if ( v119 == length[0]
                && (v58 == StringRawBuffer || CompareStringOrdinal(v58, v119, StringRawBuffer, length[0], 1) == 2) )
              {
                goto LABEL_75;
              }
              if ( v53 == v56 )
              {
                v55 = (_QWORD *)v53;
                v51 = (DataStoreCache::DataItemIdentifier *)v117;
                v54 = v7 + 22;
                break;
              }
              v53 = *(_QWORD *)(v53 + 8);
            }
          }
          if ( *((_QWORD *)v7 + 12) == 0x7FFFFFFFFFFFFFFLL )
            std::_Xlength_error("unordered_map/set too long");
          string[1] = v54;
          v126 = 0;
          v53 = std::allocator<std::_List_node<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>,void *>>::allocate();
          v126 = v53;
          v117 = (HSTRING *)v51;
          ____0V__tuple___QEAVDataItemIdentifier_DataStoreCache___std__V__tuple___V_1__0A___Z_S___pair___CBVDataItemIdentifier_DataStoreCache__V__ComPtr_UICDSLocalVolatileTilePropertiesPriv_CDSProperties_Shell_WindowsInternal___WRL_Microsoft___std__AEAA_AEAV__tuple___QEAVDataItemIdentifier_DataStoreCache___1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
            v53 + 16,
            &v117);
          v65 = *((_QWORD *)v7 + 12) + 1LL;
          if ( v65 < 0 )
            v66 = (float)(v65 & 1 | (unsigned int)((unsigned __int64)v65 >> 1))
                + (float)(v65 & 1 | (unsigned int)((unsigned __int64)v65 >> 1));
          else
            v66 = (float)(int)v65;
          v67 = *((_QWORD *)v7 + 17);
          if ( v67 < 0 )
          {
            v103 = *((_QWORD *)v7 + 17) & 1LL | ((unsigned __int64)v67 >> 1);
            v68 = (float)(int)v103 + (float)(int)v103;
          }
          else
          {
            v68 = (float)(int)v67;
          }
          if ( (float)(v66 / v68) > *((float *)v7 + 20) )
          {
            v78 = std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::_Desired_grow_bucket_count(v7 + 20);
            std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ICollectionTile>>>,0>>::_Forced_rehash(
              v7 + 20,
              v78);
            v79 = *((_QWORD *)v7 + 13);
            v80 = *(_QWORD **)(v79 + 16 * (v124 & *((_QWORD *)v7 + 16)) + 8);
            v55 = (_QWORD *)*((_QWORD *)v7 + 11);
            if ( v80 != v55 )
            {
              v81 = *(_QWORD **)(v79 + 16 * (v124 & *((_QWORD *)v7 + 16)));
              while ( (unsigned __int8)std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>::operator()<DataStoreCache::DataItemIdentifier,DataStoreCache::DataItemIdentifier>(
                                         v79,
                                         v53 + 16,
                                         v80 + 2) )
              {
                if ( v80 == v81 )
                {
                  v55 = v80;
                  goto LABEL_92;
                }
                v80 = (_QWORD *)v80[1];
              }
              v55 = (_QWORD *)*v80;
            }
          }
LABEL_92:
          v126 = 0;
          v69 = (__int64 *)v55[1];
          ++*((_QWORD *)v7 + 12);
          *(_QWORD *)v53 = v55;
          *(_QWORD *)(v53 + 8) = v69;
          *v69 = v53;
          v55[1] = v53;
          v70 = 2 * (v124 & *((_QWORD *)v7 + 16));
          v71 = *((_QWORD *)v7 + 13);
          v72 = *(_QWORD **)(v71 + 16 * (v124 & *((_QWORD *)v7 + 16)));
          if ( v72 == *((_QWORD **)v7 + 11) )
          {
            *(_QWORD *)(v71 + 16 * (v124 & *((_QWORD *)v7 + 16))) = v53;
          }
          else
          {
            if ( v72 == v55 )
            {
              *(_QWORD *)(v71 + 16 * (v124 & *((_QWORD *)v7 + 16))) = v53;
              goto LABEL_75;
            }
            if ( *(__int64 **)(v71 + 16 * (v124 & *((_QWORD *)v7 + 16)) + 8) != v69 )
            {
LABEL_75:
              v59 = v106;
              v106 = 0;
              v60 = *(_QWORD *)(v53 + 24);
              *(_QWORD *)(v53 + 24) = v59;
              if ( v60 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
              WindowsDeleteString(v118);
              v118 = 0;
              goto LABEL_78;
            }
          }
          *(_QWORD *)(v71 + 8 * v70 + 8) = v53;
          goto LABEL_75;
        }
LABEL_78:
        v61 = v106;
        if ( v106 )
        {
          v106 = 0;
          v62 = *((_QWORD *)v61 + 7);
          while ( v62 >= 0 )
          {
            if ( (_DWORD)v62 == 0x7FFFFFFF )
              goto LABEL_84;
            v63 = v62 - 1;
            v64 = v62;
            v62 = _InterlockedCompareExchange64(v61 + 7, v62 - 1, v62);
            if ( v64 == v62 )
              goto LABEL_83;
          }
          v63 = Microsoft::WRL::Details::StrongReference::DecrementStrongReference((Microsoft::WRL::Details::StrongReference *)(2 * v62 + 16));
LABEL_83:
          if ( !v63 )
          {
            (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*v61 + 112))(v61, 1);
            if ( Microsoft::WRL::Details::ModuleBase::module_ )
              (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                   + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
          }
        }
LABEL_84:
        v19 = (_QWORD *)*v19;
        v7 = a1;
        v5 = a3;
      }
      std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>::~_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>>>,0>>(v129);
      if ( v17 )
        ReleaseSRWLockExclusive(v17);
      v92 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      }
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v128);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4A,
                           (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\alltilescollection.cpp",
                           v89);
  }
  return result;
}

```

## disassembly

```asm
0x180045838  mov     [rsp+arg_10], r8
0x18004583d  mov     [rsp+arg_0], rcx
0x180045842  push    rbx
0x180045843  push    rsi
0x180045844  push    rdi
0x180045845  push    r12
0x180045847  push    r13
0x180045849  push    r14
0x18004584b  push    r15
0x18004584d  sub     rsp, 180h
0x180045854  mov     ebx, r9d
0x180045857  mov     r15, r8
0x18004585a  mov     rdi, rdx
0x18004585d  mov     r12, rcx
0x180045860  lea     rdx, aAlltilescollec; "AllTilesCollection_RuntimeClassInitiali"...
0x180045867  lea     rcx, [rsp+1B8h+var_C8]
0x18004586f  call    ?WatchCurrentThread@UnifiedTileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; UnifiedTileTelemetry::WatchCurrentThread(char const *)
0x180045874  nop
0x180045875  mov     [r12+0A8h], ebx
0x18004587d  lea     rax, [r12+90h]
0x180045885  mov     [rsp+1B8h+var_128], rax
0x18004588d  lea     rcx, [rsp+1B8h+var_128]
0x180045895  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18004589a  mov     rdx, rax
0x18004589d  mov     rcx, r15
0x1800458a0  call    ??$AsWeak@UIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@YAJPEAUIUnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileManager *,Microsoft::WRL::WeakRef *)
0x1800458a5  mov     ebx, eax
0x1800458a7  xor     r13d, r13d
0x1800458aa  test    eax, eax
0x1800458ac  js      loc_180046484
0x1800458b2  lea     rcx, [r12+0B8h]; pguid
0x1800458ba  call    cs:__imp_CoCreateGuid
0x1800458c0  mov     ebx, eax
0x1800458c2  test    eax, eax
0x1800458c4  js      loc_1800463FB
0x1800458ca  mov     rax, [rdi]
0x1800458cd  lea     r8, TileData
0x1800458d4  lea     rdx, [rsp+1B8h+var_160]
0x1800458d9  mov     rcx, rdi
0x1800458dc  mov     rax, [rax+18h]
0x1800458e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458e5  lea     r14, [r12+98h]
0x1800458ed  mov     rdx, rax
0x1800458f0  mov     rcx, r14
0x1800458f3  call    ??4?$ComPtr@UICDSLocalTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv>::operator=(Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalTilePropertiesPriv> &&)
0x1800458f8  nop
0x1800458f9  mov     rcx, [rsp+1B8h+var_160]
0x1800458fe  test    rcx, rcx
0x180045901  jz      short loc_180045915
0x180045903  mov     [rsp+1B8h+var_160], r13
0x180045908  mov     rax, [rcx]
0x18004590b  mov     rax, [rax+10h]
0x18004590f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045914  nop
0x180045915  lea     rsi, [r12+0A0h]
0x18004591d  mov     rdx, rdi
0x180045920  mov     rcx, rsi
0x180045923  call    ??4?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDataItem@DataStoreCache@@@Z; Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::operator=(DataStoreCache::IDataItem *)
0x180045928  mov     [rsp+1B8h+var_170], r13
0x18004592d  mov     [rsp+1B8h+var_128], r12
0x180045935  lea     rcx, [rsp+1B8h+var_170]
0x18004593a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004593f  lea     rdx, [rsp+1B8h+var_128]
0x180045947  lea     rcx, [rsp+1B8h+var_170]
0x18004594c  call    ??$MakeAndInitialize@VDataItemEventHandlerWrapper@DataStoreCache@@UIDataItemEventHandler@@PEAVAllTilesCollection@UnifiedTile@Shell@WindowsInternal@@@Details@WRL@Microsoft@@YAJPEAPEAUIDataItemEventHandler@@$$QEAPEAVAllTilesCollection@UnifiedTile@Shell@WindowsInternal@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::DataItemEventHandlerWrapper,IDataItemEventHandler,WindowsInternal::Shell::UnifiedTile::AllTilesCollection *>(IDataItemEventHandler * *,WindowsInternal::Shell::UnifiedTile::AllTilesCollection * &&)
0x180045951  mov     ebx, eax
0x180045953  test    eax, eax
0x180045955  js      loc_18004643A
0x18004595b  mov     rcx, [rsi]
0x18004595e  mov     rax, [rcx]
0x180045961  mov     r8, [rsp+1B8h+var_170]
0x180045966  lea     rdx, [rsp+1B8h+arg_18]
0x18004596e  mov     rax, [rax+28h]
0x180045972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045977  mov     eax, [rax]
0x180045979  mov     [r12+0C8h], eax
0x180045981  lea     rsi, [r12+0B0h]
0x180045989  mov     rcx, rsi; SRWLock
0x18004598c  call    cs:__imp_AcquireSRWLockExclusive
0x180045992  mov     [rsp+1B8h+var_D8], rsi
0x18004599a  mov     rcx, [r14]
0x18004599d  mov     rax, [rcx]
0x1800459a0  lea     rdx, [rsp+1B8h+var_78]
0x1800459a8  mov     rax, [rax+20h]
0x1800459ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459b1  nop
0x1800459b2  mov     r14, [rsp+1B8h+var_70]
0x1800459ba  mov     rdi, [r14]
0x1800459bd  cmp     rdi, r14
0x1800459c0  jz      loc_1800460C7
0x1800459c6  mov     [rsp+1B8h+var_188], r13
0x1800459cb  lea     rcx, [rsp+1B8h+var_188]
0x1800459d0  call    ?InternalRelease@?$ComPtr@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(void)
0x1800459d5  mov     rax, r12
0x1800459d8  lea     rcx, [r12+10h]
0x1800459dd  neg     rax
0x1800459e0  sbb     r13, r13
0x1800459e3  and     r13, rcx
0x1800459e6  lea     rax, [rdi+18h]
0x1800459ea  mov     [rsp+1B8h+var_130], rax
0x1800459f2  mov     rcx, [rax]
0x1800459f5  xor     eax, eax
0x1800459f7  mov     [rsp+1B8h+var_188], rax
0x1800459fc  mov     [rsp+1B8h+var_140], rax
0x180045a01  mov     qword ptr [rsp+1B8h+var_168.unused], rax
0x180045a06  mov     rax, [rcx]
0x180045a09  lea     rdx, [rsp+1B8h+string]
0x180045a11  mov     rax, [rax+20h]
0x180045a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a1a  lea     rdx, [rsp+1B8h+var_168]; HSTRING
0x180045a1f  mov     rcx, [rax]; this
0x180045a22  call    ?UnifiedTileIdentifier_CreateInstance@UnifiedTile@Shell@WindowsInternal@@YAJPEAUHSTRING__@@PEAPEAUIUnifiedTileIdentifier@123@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifier_CreateInstance(HSTRING__ *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *)
0x180045a27  mov     ebx, eax
0x180045a29  mov     rcx, [rsp+1B8h+string]; string
0x180045a31  call    cs:__imp_WindowsDeleteString
0x180045a37  mov     [rsp+1B8h+string], 0
0x180045a43  test    ebx, ebx
0x180045a45  js      loc_18004632E
0x180045a4b  mov     rax, [r15]
0x180045a4e  lea     r8, [rsp+1B8h+var_140]
0x180045a53  mov     rdx, qword ptr [rsp+1B8h+var_168.unused]
0x180045a58  mov     rcx, r15
0x180045a5b  mov     rax, [rax+48h]
0x180045a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a64  mov     ebx, eax
0x180045a66  test    eax, eax
0x180045a68  js      loc_1800466D9
0x180045a6e  mov     rcx, qword ptr [rsp+1B8h+var_168.unused]
0x180045a73  xor     ebx, ebx
0x180045a75  test    rcx, rcx
0x180045a78  jz      short loc_180045A8C
0x180045a7a  mov     qword ptr [rsp+1B8h+var_168.unused], rbx
0x180045a7f  mov     rax, [rcx]
0x180045a82  mov     rax, [rax+10h]
0x180045a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a8b  nop
0x180045a8c  mov     r12, [rsp+1B8h+var_140]
0x180045a91  test    r12, r12
0x180045a94  jz      loc_1800463A8
0x180045a9a  mov     [rsp+1B8h+var_188], rbx
0x180045a9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180045aa6  mov     ecx, 0A8h; unsigned __int64
0x180045aab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180045ab0  mov     qword ptr [rsp+1B8h+length], rax
0x180045ab5  test    rax, rax
0x180045ab8  jz      loc_180046708
0x180045abe  mov     rcx, rax; this
0x180045ac1  call    ??0CollectionTile@UnifiedTile@Shell@WindowsInternal@@QEAA@XZ; WindowsInternal::Shell::UnifiedTile::CollectionTile::CollectionTile(void)
0x180045ac6  mov     r15, rax
0x180045ac9  mov     [rsp+1B8h+var_F8], rax
0x180045ad1  mov     qword ptr [rsp+1B8h+length], rbx
0x180045ad6  lea     rcx, [rax+50h]; pguid
0x180045ada  call    cs:__imp_CoCreateGuid
0x180045ae0  mov     ebx, eax
0x180045ae2  test    eax, eax
0x180045ae4  js      loc_180046712
0x180045aea  cmp     [r15+60h], r12
0x180045aee  jz      short loc_180045B20
0x180045af0  test    r12, r12
0x180045af3  jz      short loc_180045B06
0x180045af5  mov     rax, [r12]
0x180045af9  mov     rcx, r12
0x180045afc  mov     rax, [rax+8]
0x180045b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b05  nop
0x180045b06  mov     rcx, [r15+60h]
0x180045b0a  mov     [r15+60h], r12
0x180045b0e  test    rcx, rcx
0x180045b11  jz      short loc_180045B20
0x180045b13  mov     rax, [rcx]
0x180045b16  mov     rax, [rax+10h]
0x180045b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b1f  nop
0x180045b20  mov     rcx, [r15+68h]
0x180045b24  mov     qword ptr [r15+68h], 0
0x180045b2c  test    rcx, rcx
0x180045b2f  jz      short loc_180045B3E
0x180045b31  mov     rax, [rcx]
0x180045b34  mov     rax, [rax+10h]
0x180045b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b3d  nop
0x180045b3e  mov     [rsp+1B8h+var_180], 0
0x180045b47  mov     rax, [r13+0]
0x180045b4b  lea     r8, [rsp+1B8h+var_180]
0x180045b50  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x180045b57  mov     rcx, r13
0x180045b5a  mov     rax, [rax]
0x180045b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b62  mov     ebx, eax
0x180045b64  xor     r13d, r13d
0x180045b67  test    eax, eax
0x180045b69  js      loc_180046508
0x180045b6f  mov     [rsp+1B8h+var_150], r13
0x180045b74  mov     rcx, [rsp+1B8h+var_180]
0x180045b79  mov     rax, [rcx]
0x180045b7c  lea     rdx, [rsp+1B8h+var_150]
0x180045b81  mov     rax, [rax+18h]
0x180045b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b8a  mov     ebx, eax
0x180045b8c  test    eax, eax
0x180045b8e  jns     loc_1800460E3
0x180045b94  mov     rcx, [rsp+1B8h+var_150]
0x180045b99  test    rcx, rcx
0x180045b9c  jz      short loc_180045BB0
0x180045b9e  mov     [rsp+1B8h+var_150], r13
0x180045ba3  mov     rax, [rcx]
0x180045ba6  mov     rax, [rax+10h]
0x180045baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045baf  nop
0x180045bb0  mov     rcx, [rsp+1B8h+var_180]
0x180045bb5  test    rcx, rcx
0x180045bb8  jz      short loc_180045BCC
0x180045bba  mov     [rsp+1B8h+var_180], r13
0x180045bbf  mov     rax, [rcx]
0x180045bc2  mov     rax, [rax+10h]
0x180045bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bcb  nop
0x180045bcc  test    ebx, ebx
0x180045bce  js      loc_1800463BD
0x180045bd4  mov     rbx, [rsp+1B8h+arg_10]
0x180045bdc  test    rbx, rbx
0x180045bdf  jz      loc_180045CDF
0x180045be5  mov     rcx, [r15+80h]
0x180045bec  mov     [r15+80h], r13
0x180045bf3  test    rcx, rcx
0x180045bf6  jz      short loc_180045C05
0x180045bf8  mov     rax, [rcx]
0x180045bfb  mov     rax, [rax+10h]
0x180045bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c04  nop
0x180045c05  mov     [rsp+1B8h+var_148], r13
0x180045c0a  mov     rax, [rbx]
0x180045c0d  lea     r8, [rsp+1B8h+var_148]
0x180045c12  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x180045c19  mov     rcx, rbx
0x180045c1c  mov     rax, [rax]
0x180045c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c24  mov     ebx, eax
0x180045c26  test    eax, eax
0x180045c28  js      loc_180046729
0x180045c2e  mov     [rsp+1B8h+var_118], r13
0x180045c36  mov     rcx, [rsp+1B8h+var_148]
0x180045c3b  mov     rax, [rcx]
0x180045c3e  lea     rdx, [rsp+1B8h+var_118]
0x180045c46  mov     rax, [rax+18h]
0x180045c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c4f  mov     ebx, eax
0x180045c51  test    eax, eax
0x180045c53  js      loc_18004671C
0x180045c59  mov     rbx, [rsp+1B8h+var_118]
0x180045c61  test    rbx, rbx
0x180045c64  jz      short loc_180045C76
0x180045c66  mov     rax, [rbx]
0x180045c69  mov     rcx, rbx
0x180045c6c  mov     rax, [rax+8]
0x180045c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c75  nop
0x180045c76  mov     rcx, [r15+80h]
0x180045c7d  mov     [r15+80h], rbx
0x180045c84  test    rcx, rcx
0x180045c87  jz      short loc_180045C96
0x180045c89  mov     rax, [rcx]
0x180045c8c  mov     rax, [rax+10h]
0x180045c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c95  nop
0x180045c96  mov     rcx, [rsp+1B8h+var_118]
0x180045c9e  test    rcx, rcx
0x180045ca1  jz      short loc_180045CB8
0x180045ca3  mov     [rsp+1B8h+var_118], r13
0x180045cab  mov     rax, [rcx]
0x180045cae  mov     rax, [rax+10h]
0x180045cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cb7  nop
0x180045cb8  mov     rcx, [rsp+1B8h+var_148]
0x180045cbd  test    rcx, rcx
0x180045cc0  jz      short loc_180045CD4
0x180045cc2  mov     [rsp+1B8h+var_148], r13
0x180045cc7  mov     rax, [rcx]
0x180045cca  mov     rax, [rax+10h]
0x180045cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cd3  nop
0x180045cd4  mov     ebx, r13d
0x180045cd7  test    ebx, ebx
0x180045cd9  js      loc_180046157
0x180045cdf  test    r15, r15
0x180045ce2  jz      loc_1800464FE
0x180045ce8  mov     rax, [r15+38h]
0x180045cec  test    rax, rax
0x180045cef  js      loc_180046263
0x180045cf5  cmp     eax, 7FFFFFFFh
0x180045cfa  jz      short loc_180045D08
0x180045cfc  lea     rcx, [rax+1]
0x180045d00  lock cmpxchg [r15+38h], rcx
0x180045d06  jnz     short loc_180045CEC
0x180045d08  mov     [rsp+1B8h+var_188], r15
0x180045d0d  mov     rcx, r15
0x180045d10  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UICollectionTile@UnifiedTile@Shell@WindowsInternal@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ICollectionTile,Microsoft::WRL::FtmBase>::Release(void)
0x180045d15  nop
0x180045d16  mov     rcx, [rsp+1B8h+var_140]
0x180045d1b  test    rcx, rcx
  ... truncated ...
```
