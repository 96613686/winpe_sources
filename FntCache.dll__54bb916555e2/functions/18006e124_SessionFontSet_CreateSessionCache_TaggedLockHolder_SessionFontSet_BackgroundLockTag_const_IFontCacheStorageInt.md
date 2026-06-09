# SessionFontSet::CreateSessionCache(TaggedLockHolder<SessionFontSet::BackgroundLockTag> const &,IFontCacheStorageInternal *,IFontCacheStorageInternal *)

- ea: `0x18006e124`
- end: `0x18006ecbd`
- name: `?CreateSessionCache@SessionFontSet@@AEAA?AV?$ComPtr@UIFontCacheStorageInternal@@@@AEBV?$TaggedLockHolder@W4BackgroundLockTag@SessionFontSet@@@@PEAUIFontCacheStorageInternal@@1@Z`
- size: `2969`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011a60`

## callees

- `0x180004810`
- `0x180007668`
- `0x180010338`
- `0x180010ca0`
- `0x180010cc4`
- `0x1800113a4`
- `0x180011a2c`
- `0x180011f00`
- `0x180012478`
- `0x1800124b8`
- `0x1800124f4`
- `0x180013e1c`
- `0x180028c50`
- `0x18002bc8c`
- `0x180041d18`
- `0x18004dc5c`
- `0x18004fecc`
- `0x18004ff2c`
- `0x18004ff84`
- `0x18006bc24`
- `0x18006bf70`
- `0x18006c27c`
- `0x18006d874`
- `0x18006e124`
- `0x18006ecc4`
- `0x18006ee2c`
- `0x18006ef50`
- `0x18006f778`
- `0x18006f82c`
- `0x1800729f0`
- `0x18009372c`
- `0x1800993e0`
- `0x18009acf4`
- `0x18009d96c`
- `0x18009e3b8`
- `0x18009f4ac`
- `0x18009fe58`
- `0x1800a2230`
- `0x1800a47d4`
- `0x1800aa674`
- `0x1800aaa58`
- `0x1800b2908`
- `0x1800b61b4`
- `0x1800b70ec`
- `0x1800b821c`
- `0x1800e6010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18006e1cf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18006e1cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eaf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eaf8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006eac2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006eac2`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
FontCacheStorage **__fastcall SessionFontSet::CreateSessionCache(
        __int64 a1,
        FontCacheStorage **a2,
        struct DWrite::RefString::Data *a3,
        FontCacheStorage *a4,
        __int64 a5)
{
  FontCacheStorage **v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  struct DWrite::RefString::Data **v11; // rdi
  FontCollection *v12; // r12
  FontCollection *v13; // r13
  struct DWrite::RefString::Data **v14; // rbx
  struct DWrite::RefString::Data *v15; // rsi
  FontCollectionBuilder *v17; // rdi
  __int64 v18; // r14
  struct DWrite::RefString::Data *v19; // rax
  __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rbx
  __int64 *v24; // r14
  __int64 *v25; // r12
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rax
  int v32; // r9d
  __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rax
  int v36; // ecx
  unsigned int v37; // edi
  FontCacheStorage *v38; // rax
  FontCacheStorage *v39; // rax
  struct FontCacheStorage *v40; // rbx
  _QWORD *v41; // rax
  unsigned __int64 v42; // rcx
  __int64 v43; // rbx
  char v44; // al
  int v45; // r9d
  char v46; // cl
  __int64 v47; // r9
  unsigned int v48; // edx
  int v49; // r8d
  unsigned int v50; // eax
  _QWORD *SessionFontNames; // rdi
  _QWORD *v52; // rsi
  _QWORD *v53; // rdi
  _QWORD *v54; // rsi
  EventTag *v55; // rax
  __int64 v56; // r10
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  __int64 v59; // rdx
  __int64 v60; // rax
  unsigned int v61; // edx
  unsigned int v62; // [rsp+50h] [rbp-1C8h]
  __int128 v63; // [rsp+58h] [rbp-1C0h] BYREF
  __int64 v64; // [rsp+68h] [rbp-1B0h]
  int v65; // [rsp+70h] [rbp-1A8h]
  unsigned int MissingRequiredFonts; // [rsp+74h] [rbp-1A4h]
  FontCollection *v67; // [rsp+78h] [rbp-1A0h] BYREF
  FontCollection *v68; // [rsp+80h] [rbp-198h] BYREF
  int v69; // [rsp+88h] [rbp-190h]
  unsigned int v70; // [rsp+8Ch] [rbp-18Ch]
  DWriteTraceLogging *v71; // [rsp+90h] [rbp-188h]
  unsigned int v72[2]; // [rsp+98h] [rbp-180h]
  unsigned int v73; // [rsp+A0h] [rbp-178h]
  unsigned int v74[2]; // [rsp+A8h] [rbp-170h]
  FontCacheStorage *v75; // [rsp+B0h] [rbp-168h] BYREF
  __int128 v76; // [rsp+C0h] [rbp-158h] BYREF
  unsigned int v77[2]; // [rsp+D0h] [rbp-148h]
  FontCollectionBuilder *v78; // [rsp+D8h] [rbp-140h]
  __int64 v79[6]; // [rsp+E0h] [rbp-138h] BYREF
  unsigned int v80[6]; // [rsp+110h] [rbp-108h] BYREF
  FontCollectionBuilder *v81; // [rsp+128h] [rbp-F0h]
  _QWORD v82[3]; // [rsp+130h] [rbp-E8h] BYREF
  __int64 v83; // [rsp+148h] [rbp-D0h]
  unsigned int v84; // [rsp+150h] [rbp-C8h]
  char v85[8]; // [rsp+158h] [rbp-C0h] BYREF
  char v86[8]; // [rsp+160h] [rbp-B8h] BYREF
  char v87[8]; // [rsp+168h] [rbp-B0h] BYREF
  _QWORD v88[4]; // [rsp+170h] [rbp-A8h] BYREF
  _BYTE v89[16]; // [rsp+190h] [rbp-88h] BYREF
  char v90[24]; // [rsp+1A0h] [rbp-78h] BYREF
  char v91[96]; // [rsp+1B8h] [rbp-60h] BYREF
  struct DWrite::RefString::Data *v94; // [rsp+230h] [rbp+18h] BYREF

  v94 = a3;
  v6 = a2;
  v7 = a1;
  TryGetFontCollection(&v67, a4);
  TryGetFontCollection(&v68, a5);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v63);
  v8 = *(_QWORD *)(v7 + 288);
  v9 = *(_QWORD *)(v7 + 296);
  if ( v8 == v9 )
  {
    v12 = v67;
    v13 = v68;
  }
  else
  {
    v10 = (v9 - v8) >> 3;
    v94 = (struct DWrite::RefString::Data *)v10;
    if ( v10 > (v64 - (__int64)v63) >> 3 )
    {
      if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      std::vector<IDWriteFontFileStreamInternal *>::_Reallocate<0>(&v63, &v94);
    }
    v11 = *(struct DWrite::RefString::Data ***)(v7 + 288);
    v12 = v67;
    v13 = v68;
    if ( v11 != *(struct DWrite::RefString::Data ***)(v7 + 296) )
    {
      v14 = *(struct DWrite::RefString::Data ***)(v7 + 296);
      do
      {
        v15 = *v11;
        v94 = v15;
        (*(void (__fastcall **)(struct DWrite::RefString::Data *, __int64 *))(*(_QWORD *)v15 + 72LL))(v15, v79);
        if ( !CollectionHasFile(v12, (const struct FontFileReference *)v79)
          && !CollectionHasFile(v13, (const struct FontFileReference *)v79) )
        {
          if ( *((_QWORD *)&v63 + 1) == v64 )
          {
            std::vector<void *>::_Emplace_reallocate<void * const &>(&v63, *((_QWORD *)&v63 + 1), &v94);
          }
          else
          {
            **((_QWORD **)&v63 + 1) = v15;
            *((_QWORD *)&v63 + 1) += 8LL;
          }
        }
        FontFileReference::~FontFileReference((FontFileReference *)v79);
        ++v11;
      }
      while ( v11 != v14 );
      v7 = a1;
    }
    v6 = a2;
  }
  if ( a4 && (_QWORD)v63 == *((_QWORD *)&v63 + 1) && !v13 )
  {
    EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag>(
      v7,
      0x437365536B6DLL,
      0x6D6574737973LL);
    *v6 = a4;
    ComPtr<FileCleanup>::AddRef(v6);
    if ( (_QWORD)v63 )
    {
      std::_Deallocate<16>((void *)v63, (v64 - v63) & 0xFFFFFFFFFFFFFFF8uLL);
      v63 = 0;
      v64 = 0;
    }
    ScopedPtr<FontCollection>::~ScopedPtr<FontCollection>(&v68);
    ScopedPtr<FontCollection>::~ScopedPtr<FontCollection>(&v67);
    return v6;
  }
  v94 = (struct DWrite::RefString::Data *)operator new(0x70u);
  v17 = FontCollectionBuilder::FontCollectionBuilder(v94, 0, &dword_1800EC744, 0);
  v78 = v17;
  v81 = v17;
  v18 = *((_QWORD *)v17 + 4);
  v19 = (struct DWrite::RefString::Data *)*((_QWORD *)v17 + 3);
  v94 = v19;
  if ( v12 )
  {
    v20 = *((_QWORD *)v12 + 3);
    v21 = *(unsigned int *)(*(_QWORD *)v12 + 12LL);
    v22 = *((unsigned int *)v12 + 8);
    if ( v21 > v22 || v22 - v21 < 4 || (((_BYTE)v21 + (_BYTE)v20) & 3) != 0 )
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*((_QWORD *)v12 + 3));
    LODWORD(v71) = *(_DWORD *)(v21 + v20);
    *(_QWORD *)v74 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)v12 + 9) - *((_QWORD *)v12 + 8)) >> 2);
    MissingRequiredFonts = (unsigned __int8)FontSetCache::GetMissingRequiredFonts(v12);
    FontSetBuilder::AddFontSet(v17, v12);
    v19 = v94;
  }
  else
  {
    LODWORD(v71) = 0;
    MissingRequiredFonts = 7;
    v74[0] = 0;
  }
  v23 = 0x8F5C28F5C28F5C29uLL * ((__int64)(*((_QWORD *)v17 + 4) - *((_QWORD *)v17 + 3)) >> 3);
  v69 = -1030792151 * ((__int64)(*((_QWORD *)v17 + 4) - *((_QWORD *)v17 + 3)) >> 3)
      - -1030792151 * ((v18 - (__int64)v19) >> 3);
  if ( v13 )
  {
    *(_OWORD *)v79 = *(_OWORD *)((char *)v13 + 24);
    v70 = *(_DWORD *)CheckedPtr<unsigned char const,FailAsExceptionPolicy<InvalidCacheDataException>,unsigned int>::ReadAt<unsigned int const>(
                       (__int64)v79,
                       *(unsigned int *)(*(_QWORD *)v13 + 12LL));
    *(_QWORD *)v72 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)v13 + 9) - *((_QWORD *)v13 + 8)) >> 2);
    FontSetBuilder::AddFontSet(v17, v13);
  }
  else
  {
    v70 = 0;
    *(_QWORD *)v72 = 0;
  }
  *(_QWORD *)&v76 = 0x8F5C28F5C28F5C29uLL * ((__int64)(*((_QWORD *)v17 + 4) - *((_QWORD *)v17 + 3)) >> 3);
  v65 = v76 - v23;
  v24 = (__int64 *)v63;
  if ( (_QWORD)v63 != *((_QWORD *)&v63 + 1) )
  {
    v25 = (__int64 *)*((_QWORD *)&v63 + 1);
    do
    {
      v26 = *v24;
      v94 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
      v27 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 32LL);
      v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 72LL))(v26, v79);
      FontSetBuilder::AddFontFile(v17, v28, v27, 0, &v94);
      FontFileReference::~FontFileReference((FontFileReference *)v79);
      DWrite::RefString::DecrementRef(v94);
      ++v24;
    }
    while ( v24 != v25 );
    v12 = v67;
    v13 = v68;
  }
  *(_QWORD *)v80 = 0x8F5C28F5C28F5C29uLL * ((__int64)(*((_QWORD *)v17 + 4) - *((_QWORD *)v17 + 3)) >> 3);
  EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag,EventTag,unsigned int,EventTag,unsigned int,EventTag,unsigned int>(
    a1,
    1699965805,
    1718449518,
    7567731,
    v69,
    7500661,
    v65,
    7562611,
    v80[0] - v76);
  if ( v12 )
  {
    v29 = *((_QWORD *)v12 + 3);
    v30 = *(unsigned int *)(*(_QWORD *)v12 + 12LL);
    v31 = *((unsigned int *)v12 + 8);
    if ( v30 > v31 || v31 - v30 < 4 || (((_BYTE)v30 + (_BYTE)v29) & 3) != 0 )
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*((_QWORD *)v12 + 3));
    v32 = *(_DWORD *)(v30 + v29);
  }
  else
  {
    v32 = 0;
  }
  if ( v13 )
  {
    v33 = *((_QWORD *)v13 + 3);
    v34 = *(unsigned int *)(*(_QWORD *)v13 + 12LL);
    v35 = *((unsigned int *)v13 + 8);
    if ( v34 > v35 || v35 - v34 < 4 || (((_BYTE)v34 + (_BYTE)v33) & 3) != 0 )
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(*((_QWORD *)v13 + 3));
    v36 = *(_DWORD *)(v34 + v33);
  }
  else
  {
    v36 = 0;
  }
  EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag,EventTag,unsigned int,EventTag,unsigned int,EventTag,unsigned int>(
    a1,
    1699965805,
    1718449518,
    7500661,
    v36,
    7567731,
    v32,
    7562611,
    (__int64)(*((_QWORD *)&v63 + 1) - v63) >> 3);
  v37 = 0x80000000;
  if ( *(_DWORD *)(a1 + 172) != -1 )
    v37 = *(_DWORD *)(a1 + 172) + 1;
  EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag>(
    a1,
    g_makeTag,
    0x656761726F7453LL);
  v38 = (FontCacheStorage *)operator new(0x70u);
  v39 = FontCacheStorage::FontCacheStorage(v38, &pszSrc);
  v40 = v39;
  v75 = v39;
  if ( v39 )
    (*(void (__fastcall **)(FontCacheStorage *))(*(_QWORD *)v39 + 8LL))(v39);
  v94 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
  FontSetCache::CreateFontSetCacheInstance(v40, (const struct DWrite::RefString *)&v94, &pszSrc, 0, v37, v78);
  DWrite::RefString::DecrementRef(v94);
  v41 = (_QWORD *)(*(__int64 (__fastcall **)(struct FontCacheStorage *, struct DWrite::RefString::Data **))(*(_QWORD *)v40 + 72LL))(
                    v40,
                    &v94);
  try
  {
    FontSetCache::GetFontCollectionFromCacheWriter(v82, *v41);
    ReleaseReference<CacheWriter>((volatile signed __int32 *)v94);
    v42 = *(unsigned int *)(v82[0] + 12LL);
    if ( v42 > v84 || v84 - v42 < 4 || (((_BYTE)v42 + (_BYTE)v83) & 3) != 0 )
      FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(v83);
    v79[0] = *((_QWORD *)&v63 + 1) - v63;
    v73 = *(_DWORD *)(v42 + v83);
    v43 = v88[1] - v88[0];
    v44 = FontSetCache::GetMissingRequiredFonts(v82);
    LOBYTE(v62) = v44;
    if ( MissingRequiredFonts || (v46 = 0, v44) )
      v46 = 1;
    LOBYTE(v94) = v46;
    *(_QWORD *)v77 = 0xAAAAAAAAAAAAAAABuLL * (v43 >> 2);
    if ( v74[0] != v69 )
    {
      EventLogger::LogEvent<long,EventTag,unsigned int,EventTag,unsigned int,unsigned int>(
        a1 + 16,
        1936942419,
        1869771365,
        v45,
        0x437365536B6DLL,
        835,
        0x7379536D754ELL,
        v74[0],
        v69);
      v46 = 1;
      LOBYTE(v94) = 1;
    }
    v47 = a1 + 16;
    v48 = v72[0];
    v49 = v65;
    if ( v72[0] != v65 )
    {
      EventLogger::LogEvent<long,EventTag,unsigned int,EventTag,unsigned int,unsigned int>(
        a1 + 16,
        1936942419,
        1869771365,
        v47,
        0x437365536B6DLL,
        840,
        0x7273556D754ELL,
        v72[0],
        v65);
      v46 = 1;
      LOBYTE(v94) = 1;
      v48 = v72[0];
      v49 = v65;
    }
    v50 = v77[0];
    if ( v77[0] == v80[0] )
    {
      if ( !v46 )
      {
LABEL_70:
        SessionFontNames = (_QWORD *)SessionFontSet::GetSessionFontNames(v79, (unsigned int)v76, v82, v47);
        v52 = (_QWORD *)(a1 + 320);
        *(_QWORD *)&v76 = a1 + 328;
        if ( (_QWORD *)(a1 + 320) == SessionFontNames )
        {
          *(_QWORD *)&v76 = a1 + 328;
        }
        else
        {
          std::vector<DWrite::RefString>::_Tidy(a1 + 320);
          *v52 = *SessionFontNames;
          *(_QWORD *)(a1 + 328) = SessionFontNames[1];
          *(_QWORD *)(a1 + 336) = SessionFontNames[2];
          *SessionFontNames = 0;
          SessionFontNames[1] = 0;
          SessionFontNames[2] = 0;
        }
        std::vector<DWrite::RefString>::_Tidy(v79);
        v53 = (_QWORD *)*v52;
        if ( *v52 != *(_QWORD *)v76 )
        {
          v54 = *(_QWORD **)v76;
          do
          {
            v55 = EventTag::EventTag((EventTag *)v79, (const char (*)[9])"sessFont");
            EventLogger::LogEvent<wchar_t const *>(v56, 0x6E6F6973736553LL, *(_QWORD *)v55, *v53++ + 8LL);
          }
          while ( v53 != v54 );
        }
        v79[0] = a1 + 112;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
        if ( !*(_QWORD *)(a1 + 312) )
          ThreadpoolTimer::Initialize(
            (ThreadpoolTimer *)(a1 + 312),
            (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *))SessionFontSet::TimerCallback,
            (void *)a1);
        ThreadpoolTimer::SetOnce((struct _TP_TIMER **)(a1 + 312), 0x7D0u);
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
        if ( (_BYTE)v94 && v12 && v13 )
        {
          v57 = *(_OWORD *)((char *)v13 + 24);
          v58 = *(_OWORD *)((char *)v12 + 24);
          v59 = *((_QWORD *)v75 + 12);
          v79[0] = v59;
          if ( v59 )
            _InterlockedIncrement((volatile signed __int32 *)(v59 + 8));
          v76 = v57;
          *(_OWORD *)v80 = v58;
          v60 = CreateCombinedSessionCache(&v94, v59, v80, &v76);
          ComPtr<FontCacheStorage>::operator=(&v75, v60);
          ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&v94);
          IntrusivePtr<CacheWriter>::~IntrusivePtr<CacheWriter>(v79);
        }
        std::vector<GlyphDependencyRegion::GlyphToListMapping>::_Tidy(v91);
        std::vector<unsigned __int64>::~vector<unsigned __int64>(v90);
        std::_Tree_val<std::_Tree_simple_types<std::pair<StringCheckedPtr const,unsigned int>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<StringCheckedPtr const,unsigned int>,void *>>>(
          v89,
          v89);
        std::vector<FontFeatureCoverageRegionBuilder::Feature>::_Tidy(v88);
        RefCountedArray<unsigned char>::~RefCountedArray<unsigned char>(v87);
        IntrusivePtr<ICacheReference>::~IntrusivePtr<ICacheReference>(v86);
        RefCountedArray<unsigned char>::~RefCountedArray<unsigned char>(v85);
        goto LABEL_98;
      }
    }
    else
    {
      EventLogger::LogEvent<long,EventTag,unsigned int,EventTag,unsigned int,unsigned int>(
        a1 + 16,
        1936942419,
        1869771365,
        v47,
        0x437365536B6DLL,
        847,
        0x6C6C416D754ELL,
        v48,
        v49);
      LOBYTE(v94) = 1;
      v50 = v77[0];
    }
    DWriteTraceLogging::LogSessionCacheUpdateResult(
      (DWriteTraceLogging *)(unsigned int)v71,
      v70,
      v79[0] >> 3,
      v73,
      v74[0],
      v72[0],
      v80[0],
      v50,
      MissingRequiredFonts,
      (unsigned __int8)v62,
      v62);
    goto LABEL_70;
  }
  catch ( ... )
  {
    EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogCurrentException<>((struct IExceptionHandler *)a1);
  }
LABEL_98:
  *a2 = v75;
  if ( v78 )
    FontCollectionBuilder::`scalar deleting destructor'(v78, v61);
  if ( (_QWORD)v63 )
  {
    std::_Deallocate<16>((void *)v63, (v64 - v63) & 0xFFFFFFFFFFFFFFF8uLL);
    v63 = 0;
    v64 = 0;
  }
  if ( v13 )
  {
    FontCollection::~FontCollection(v13);
    operator delete(v13, 0xA8u);
  }
  if ( v12 )
  {
    FontCollection::~FontCollection(v12);
    operator delete(v12, 0xA8u);
  }
  return a2;
}

```

## disassembly

```asm
0x18006e124  mov     [rsp+arg_10], r8
0x18006e129  mov     [rsp+arg_8], rdx
0x18006e12e  mov     [rsp+arg_0], rcx
0x18006e133  push    rbx
0x18006e134  push    rsi
0x18006e135  push    rdi
0x18006e136  push    r12
0x18006e138  push    r13
0x18006e13a  push    r14
0x18006e13c  push    r15
0x18006e13e  sub     rsp, 1E0h
0x18006e145  mov     r14, r9
0x18006e148  mov     rdi, rdx
0x18006e14b  mov     rbx, rcx
0x18006e14e  xor     r15d, r15d
0x18006e151  mov     rdx, r9
0x18006e154  lea     rcx, [rsp+218h+var_1A0]
0x18006e159  call    ?TryGetFontCollection@@YA?AV?$ScopedPtr@VFontCollection@@@@PEAUIFontCacheStorageInternal@@@Z; TryGetFontCollection(IFontCacheStorageInternal *)
0x18006e15e  nop
0x18006e15f  mov     rdx, [rsp+218h+arg_20]
0x18006e167  lea     rcx, [rsp+218h+var_198]
0x18006e16f  call    ?TryGetFontCollection@@YA?AV?$ScopedPtr@VFontCollection@@@@PEAUIFontCacheStorageInternal@@@Z; TryGetFontCollection(IFontCacheStorageInternal *)
0x18006e174  nop
0x18006e175  lea     rcx, [rsp+218h+var_1C0]; void *
0x18006e17a  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18006e17f  nop
0x18006e180  mov     rax, [rbx+120h]
0x18006e187  mov     rcx, [rbx+128h]
0x18006e18e  cmp     rax, rcx
0x18006e191  jz      loc_18006E2B0
0x18006e197  sub     rcx, rax
0x18006e19a  sar     rcx, 3
0x18006e19e  mov     [rsp+218h+arg_10], rcx
0x18006e1a6  mov     rax, [rsp+218h+var_1B0]
0x18006e1ab  sub     rax, qword ptr [rsp+218h+var_1C0]
0x18006e1b0  sar     rax, 3
0x18006e1b4  cmp     rcx, rax
0x18006e1b7  jbe     short loc_18006E1E8
0x18006e1b9  mov     rax, 1FFFFFFFFFFFFFFFh
0x18006e1c3  cmp     rcx, rax
0x18006e1c6  jbe     short loc_18006E1D6
0x18006e1c8  lea     rcx, aVectorTooLong; "vector too long"
0x18006e1cf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18006e1d6  lea     rdx, [rsp+218h+arg_10]
0x18006e1de  lea     rcx, [rsp+218h+var_1C0]
0x18006e1e3  call    ??$_Reallocate@$0A@@?$vector@PEAUIDWriteFontFileStreamInternal@@V?$allocator@PEAUIDWriteFontFileStreamInternal@@@std@@@std@@AEAAXAEA_K@Z; std::vector<IDWriteFontFileStreamInternal *>::_Reallocate<0>(unsigned __int64 &)
0x18006e1e8  mov     rdi, [rbx+120h]
0x18006e1ef  mov     rax, [rbx+128h]
0x18006e1f6  mov     r12, [rsp+218h+var_1A0]
0x18006e1fb  mov     r13, [rsp+218h+var_198]
0x18006e203  cmp     rdi, rax
0x18006e206  jz      loc_18006E2A6
0x18006e20c  mov     rbx, rax
0x18006e20f  mov     rsi, [rdi]
0x18006e212  mov     [rsp+218h+arg_10], rsi
0x18006e21a  mov     rax, [rsi]
0x18006e21d  lea     rdx, [rsp+218h+var_138]
0x18006e225  mov     rcx, rsi
0x18006e228  mov     rax, [rax+48h]
0x18006e22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e231  nop
0x18006e232  lea     rdx, [rsp+218h+var_138]; struct FontFileReference *
0x18006e23a  mov     rcx, r12; struct FontCollection *
0x18006e23d  call    ?CollectionHasFile@@YA_NPEAVFontCollection@@AEBVFontFileReference@@@Z; CollectionHasFile(FontCollection *,FontFileReference const &)
0x18006e242  test    al, al
0x18006e244  jnz     short loc_18006E284
0x18006e246  lea     rdx, [rsp+218h+var_138]; struct FontFileReference *
0x18006e24e  mov     rcx, r13; struct FontCollection *
0x18006e251  call    ?CollectionHasFile@@YA_NPEAVFontCollection@@AEBVFontFileReference@@@Z; CollectionHasFile(FontCollection *,FontFileReference const &)
0x18006e256  test    al, al
0x18006e258  jnz     short loc_18006E284
0x18006e25a  mov     rdx, qword ptr [rsp+218h+var_1C0+8]
0x18006e25f  cmp     rdx, [rsp+218h+var_1B0]
0x18006e264  jz      short loc_18006E271
0x18006e266  mov     [rdx], rsi
0x18006e269  add     qword ptr [rsp+218h+var_1C0+8], 8
0x18006e26f  jmp     short loc_18006E284
0x18006e271  lea     r8, [rsp+218h+arg_10]
0x18006e279  lea     rcx, [rsp+218h+var_1C0]
0x18006e27e  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x18006e283  nop
0x18006e284  lea     rcx, [rsp+218h+var_138]; this
0x18006e28c  call    ??1FontFileReference@@QEAA@XZ; FontFileReference::~FontFileReference(void)
0x18006e291  add     rdi, 8
0x18006e295  cmp     rdi, rbx
0x18006e298  jnz     loc_18006E20F
0x18006e29e  mov     rbx, [rsp+218h+arg_0]
0x18006e2a6  mov     rdi, [rsp+218h+arg_8]
0x18006e2ae  jmp     short loc_18006E2BD
0x18006e2b0  mov     r12, [rsp+218h+var_1A0]
0x18006e2b5  mov     r13, [rsp+218h+var_198]
0x18006e2bd  mov     rsi, 437365536B6Dh
0x18006e2c7  test    r14, r14
0x18006e2ca  jz      short loc_18006E347
0x18006e2cc  mov     rax, qword ptr [rsp+218h+var_1C0+8]
0x18006e2d1  cmp     qword ptr [rsp+218h+var_1C0], rax
0x18006e2d6  jnz     short loc_18006E347
0x18006e2d8  test    r13, r13
0x18006e2db  jnz     short loc_18006E347
0x18006e2dd  mov     r8, 6D6574737973h
0x18006e2e7  mov     rdx, rsi
0x18006e2ea  mov     rcx, rbx
0x18006e2ed  call    ??$LogEvent@VEventTag@@@?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@QEBAXVEventTag@@0@Z; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag>(EventTag,EventTag)
0x18006e2f2  mov     [rdi], r14
0x18006e2f5  mov     rcx, rdi
0x18006e2f8  call    ?AddRef@?$ComPtr@VFileCleanup@@@@AEBAXXZ; ComPtr<FileCleanup>::AddRef(void)
0x18006e2fd  nop
0x18006e2fe  mov     rcx, qword ptr [rsp+218h+var_1C0]
0x18006e303  test    rcx, rcx
0x18006e306  jz      short loc_18006E327
0x18006e308  mov     rdx, [rsp+218h+var_1B0]
0x18006e30d  sub     rdx, rcx
0x18006e310  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18006e314  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006e319  xorps   xmm0, xmm0
0x18006e31c  movdqu  [rsp+218h+var_1C0], xmm0
0x18006e322  mov     [rsp+218h+var_1B0], r15
0x18006e327  lea     rcx, [rsp+218h+var_198]
0x18006e32f  call    ??1?$ScopedPtr@VFontCollection@@@@QEAA@XZ; ScopedPtr<FontCollection>::~ScopedPtr<FontCollection>(void)
0x18006e334  nop
0x18006e335  lea     rcx, [rsp+218h+var_1A0]
0x18006e33a  call    ??1?$ScopedPtr@VFontCollection@@@@QEAA@XZ; ScopedPtr<FontCollection>::~ScopedPtr<FontCollection>(void)
0x18006e33f  mov     rax, rdi
0x18006e342  jmp     loc_18006ECAA
0x18006e347  mov     ecx, 70h ; 'p'; Size
0x18006e34c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e351  mov     [rsp+218h+arg_10], rax
0x18006e359  xor     r9d, r9d; unsigned int
0x18006e35c  lea     r8, dword_1800EC744; void *
0x18006e363  xor     edx, edx; unsigned __int64
0x18006e365  mov     rcx, rax; this
0x18006e368  call    ??0FontCollectionBuilder@@QEAA@_KPEBXI@Z; FontCollectionBuilder::FontCollectionBuilder(unsigned __int64,void const *,uint)
0x18006e36d  mov     rdi, rax
0x18006e370  mov     [rsp+218h+var_140], rax
0x18006e378  mov     [rsp+218h+var_F0], rax
0x18006e380  mov     r14, [rax+20h]
0x18006e384  mov     rax, [rax+18h]
0x18006e388  mov     [rsp+218h+arg_10], rax
0x18006e390  test    r12, r12
0x18006e393  jz      loc_18006E41A
0x18006e399  mov     rdx, [r12+18h]
0x18006e39e  mov     rax, [r12]
0x18006e3a2  mov     ecx, [rax+0Ch]
0x18006e3a5  mov     eax, [r12+20h]
0x18006e3aa  cmp     rcx, rax
0x18006e3ad  ja      short loc_18006E411
0x18006e3af  sub     rax, rcx
0x18006e3b2  cmp     rax, 4
0x18006e3b6  jb      short loc_18006E411
0x18006e3b8  lea     rax, [rcx+rdx]
0x18006e3bc  test    al, 3
0x18006e3be  jnz     short loc_18006E411
0x18006e3c0  mov     eax, [rax]
0x18006e3c2  mov     dword ptr [rsp+218h+var_188], eax
0x18006e3c9  mov     rax, [r12+48h]
0x18006e3ce  sub     rax, [r12+40h]
0x18006e3d3  sar     rax, 2
0x18006e3d7  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18006e3e1  imul    rax, rcx
0x18006e3e5  mov     qword ptr [rsp+218h+var_170], rax
0x18006e3ed  mov     rcx, r12
0x18006e3f0  call    ?GetMissingRequiredFonts@FontSetCache@@SA?AW4RequiredFonts@1@AEBVFontSet@@@Z; FontSetCache::GetMissingRequiredFonts(FontSet const &)
0x18006e3f5  movzx   eax, al
0x18006e3f8  mov     [rsp+218h+var_1A4], eax
0x18006e3fc  mov     rdx, r12; struct FontSet *
0x18006e3ff  mov     rcx, rdi; this
0x18006e402  call    ?AddFontSet@FontSetBuilder@@QEAAXAEBVFontSet@@@Z; FontSetBuilder::AddFontSet(FontSet const &)
0x18006e407  mov     rax, [rsp+218h+arg_10]
0x18006e40f  jmp     short loc_18006E432
0x18006e411  mov     rcx, rdx
0x18006e414  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x18006e41a  mov     dword ptr [rsp+218h+var_188], r15d
0x18006e422  mov     [rsp+218h+var_1A4], 7
0x18006e42a  mov     [rsp+218h+var_170], r15d
0x18006e432  mov     rbx, [rdi+20h]
0x18006e436  sub     rbx, [rdi+18h]
0x18006e43a  sar     rbx, 3
0x18006e43e  mov     rcx, 8F5C28F5C28F5C29h
0x18006e448  imul    rbx, rcx
0x18006e44c  sub     r14, rax
0x18006e44f  sar     r14, 3
0x18006e453  imul    r14, rcx
0x18006e457  mov     eax, ebx
0x18006e459  sub     eax, r14d
0x18006e45c  mov     [rsp+218h+var_190], eax
0x18006e463  test    r13, r13
0x18006e466  jz      short loc_18006E4CC
0x18006e468  movups  xmm0, xmmword ptr [r13+18h]
0x18006e46d  movdqu  xmmword ptr [rsp+218h+var_138], xmm0
0x18006e476  mov     rax, [r13+0]
0x18006e47a  mov     edx, [rax+0Ch]
0x18006e47d  lea     rcx, [rsp+218h+var_138]
0x18006e485  call    ??$ReadAt@$$CBI@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@QEBAAEBI_K0@Z; CheckedPtr<uchar const,FailAsExceptionPolicy<InvalidCacheDataException>,uint>::ReadAt<uint const>(unsigned __int64,unsigned __int64)
0x18006e48a  mov     eax, [rax]
0x18006e48c  mov     [rsp+218h+var_18C], eax
0x18006e493  mov     r14, [r13+48h]
0x18006e497  sub     r14, [r13+40h]
0x18006e49b  sar     r14, 2
0x18006e49f  mov     rax, 0AAAAAAAAAAAAAAABh
0x18006e4a9  imul    r14, rax
0x18006e4ad  mov     qword ptr [rsp+218h+var_180], r14
0x18006e4b5  mov     rdx, r13; struct FontSet *
0x18006e4b8  mov     rcx, rdi; this
0x18006e4bb  call    ?AddFontSet@FontSetBuilder@@QEAAXAEBVFontSet@@@Z; FontSetBuilder::AddFontSet(FontSet const &)
0x18006e4c0  mov     rcx, 8F5C28F5C28F5C29h
0x18006e4ca  jmp     short loc_18006E4DF
0x18006e4cc  mov     [rsp+218h+var_18C], r15d
0x18006e4d4  mov     eax, r15d
0x18006e4d7  mov     qword ptr [rsp+218h+var_180], rax
0x18006e4df  mov     rax, [rdi+20h]
0x18006e4e3  sub     rax, [rdi+18h]
0x18006e4e7  sar     rax, 3
0x18006e4eb  imul    rax, rcx
0x18006e4ef  mov     qword ptr [rsp+218h+var_158], rax
0x18006e4f7  sub     eax, ebx
0x18006e4f9  mov     [rsp+218h+var_1A8], eax
0x18006e4fd  mov     r14, qword ptr [rsp+218h+var_1C0]
0x18006e502  mov     rax, qword ptr [rsp+218h+var_1C0+8]
0x18006e507  cmp     r14, rax
0x18006e50a  jz      loc_18006E5AE
0x18006e510  lea     r13, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18006e517  mov     rsi, [rsp+218h+arg_0]
0x18006e51f  mov     r12, rax
0x18006e522  mov     rcx, [r14]
0x18006e525  mov     [rsp+218h+arg_10], r13
0x18006e52d  mov     rax, [rsi+38h]
0x18006e531  mov     rbx, [rax+20h]
0x18006e535  mov     rax, [rcx]
0x18006e538  lea     rdx, [rsp+218h+var_138]
0x18006e540  mov     rax, [rax+48h]
0x18006e544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e549  nop
0x18006e54a  lea     rcx, [rsp+218h+arg_10]
0x18006e552  mov     qword ptr [rsp+218h+var_1F8], rcx
0x18006e557  xor     r9d, r9d
0x18006e55a  mov     r8, rbx
0x18006e55d  mov     rdx, rax
0x18006e560  mov     rcx, rdi
0x18006e563  call    ?AddFontFile@FontSetBuilder@@QEAAJAEBVFontFileReference@@PEAUIBaseCacheContext@@W4DWRITE_FONT_SOURCE_TYPE@@AEBVRefString@DWrite@@@Z; FontSetBuilder::AddFontFile(FontFileReference const &,IBaseCacheContext *,DWRITE_FONT_SOURCE_TYPE,DWrite::RefString const &)
0x18006e568  nop
0x18006e569  lea     rcx, [rsp+218h+var_138]; this
0x18006e571  call    ??1FontFileReference@@QEAA@XZ; FontFileReference::~FontFileReference(void)
0x18006e576  nop
0x18006e577  mov     rcx, [rsp+218h+arg_10]; struct DWrite::RefString::Data *
0x18006e57f  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006e584  add     r14, 8
0x18006e588  cmp     r14, r12
0x18006e58b  jnz     short loc_18006E522
0x18006e58d  mov     rsi, 437365536B6Dh
0x18006e597  mov     r12, [rsp+218h+var_1A0]
0x18006e59c  mov     r13, [rsp+218h+var_198]
0x18006e5a4  mov     rcx, 8F5C28F5C28F5C29h
0x18006e5ae  mov     rax, [rdi+20h]
0x18006e5b2  sub     rax, [rdi+18h]
0x18006e5b6  sar     rax, 3
0x18006e5ba  imul    rax, rcx
0x18006e5be  mov     qword ptr [rsp+218h+var_108], rax
0x18006e5c6  mov     ebx, 736573h
0x18006e5cb  mov     edi, 737973h
0x18006e5d0  mov     r14d, 727375h
0x18006e5d6  mov     r8, 73746E6F666D756Eh
0x18006e5e0  sub     eax, dword ptr [rsp+218h+var_158]
0x18006e5e7  mov     [rsp+218h+var_1D8], eax
0x18006e5eb  mov     qword ptr [rsp+218h+var_1E0], rbx
0x18006e5f0  mov     eax, [rsp+218h+var_1A8]
0x18006e5f4  mov     [rsp+218h+var_1E8], eax
0x18006e5f8  mov     [rsp+218h+var_1F0], r14
0x18006e5fd  mov     eax, [rsp+218h+var_190]
0x18006e604  mov     [rsp+218h+var_1F8], eax
0x18006e608  mov     r9d, edi
0x18006e60b  mov     rdx, rsi
0x18006e60e  mov     rcx, [rsp+218h+arg_0]
0x18006e616  call    ??$LogEvent@VEventTag@@V1@IV1@IV1@I@?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@QEBAXVEventTag@@00I0I0I@Z; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<EventTag,EventTag,uint,EventTag,uint,EventTag,uint>(EventTag,EventTag,EventTag,uint,EventTag,uint,EventTag,uint)
0x18006e61b  test    r12, r12
0x18006e61e  jz      short loc_18006E655
0x18006e620  mov     rdx, [r12+18h]
0x18006e625  mov     rax, [r12]
0x18006e629  mov     ecx, [rax+0Ch]
0x18006e62c  mov     eax, [r12+20h]
0x18006e631  cmp     rcx, rax
0x18006e634  ja      short loc_18006E64C
0x18006e636  sub     rax, rcx
0x18006e639  cmp     rax, 4
0x18006e63d  jb      short loc_18006E64C
0x18006e63f  lea     rax, [rcx+rdx]
0x18006e643  test    al, 3
0x18006e645  jnz     short loc_18006E64C
0x18006e647  mov     r9d, [rax]
0x18006e64a  jmp     short loc_18006E658
0x18006e64c  mov     rcx, rdx
0x18006e64f  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@SAXPEBX@Z; FailAsExceptionPolicy<InvalidCacheDataException>::OnOutOfRange(void const *)
0x18006e655  mov     r9d, r15d
0x18006e658  test    r13, r13
0x18006e65b  jz      short loc_18006E68F
0x18006e65d  mov     rdx, [r13+18h]
0x18006e661  mov     rax, [r13+0]
0x18006e665  mov     ecx, [rax+0Ch]
0x18006e668  mov     eax, [r13+20h]
0x18006e66c  cmp     rcx, rax
0x18006e66f  ja      short loc_18006E686
  ... truncated ...
```
