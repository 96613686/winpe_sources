# StateRepository::CacheManagement::_Update(StateRepository::Database &,StateRepository::CacheManagement::Options)

- ea: `0x180011280`
- end: `0x180011bb7`
- name: `?_Update@CacheManagement@StateRepository@@CAJAEAVDatabase@2@W4Options@12@@Z`
- size: `2359`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000fd00`

## callees

- `0x180007a40`
- `0x18000b3a0`
- `0x18000c93c`
- `0x18000f748`
- `0x180010d28`
- `0x180010d84`
- `0x180011168`
- `0x180011280`
- `0x18001254c`
- `0x180016030`
- `0x1800171c0`
- `0x180017a58`
- `0x180018574`
- `0x180019794`
- `0x18001a9e0`
- `0x180034b4c`
- `0x180051298`
- `0x18005142c`
- `0x180052244`
- `0x180052358`
- `0x180052384`
- `0x180052444`
- `0x180062bec`
- `0x180062cd8`
- `0x1800693a4`
- `0x180069780`
- `0x180069810`
- `0x18008d1d4`
- `0x180090700`
- `0x18018f650`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001153f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800115df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800117d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001189a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011920`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800119c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011a62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011ae5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011b72`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001153f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800115df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800117d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001189a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011920`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800119c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011a62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011ae5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180011b72`

## string_xrefs

- `0x1800113f8`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-srjournal.cpp`
- `0x18001176a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-srjournal.cpp`
- `0x1800112b5`: `Cache_Update`
- `0x1800114b3`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180011501`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1800117ff`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180011415`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x1800114d8`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x18001158e`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180011787`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x1800118ff`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180011971`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180011a11`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180011ab1`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`
- `0x180011b34`: `onecore\base\appmodel\staterepository\dataaccesslayer\cachemanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::CacheManagement::_Update(StateRepository::Database *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int v5; // eax
  StateRepository::Database *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  __int64 v10; // r8
  char v11; // si
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int updated; // eax
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  struct sqlite3_stmt *v37; // [rsp+58h] [rbp-A8h] BYREF
  StateRepository::Database *v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h] BYREF
  __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v49[3]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-38h]
  __int64 v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D8h] [rbp-28h]
  __int128 v53; // [rsp+E0h] [rbp-20h]
  __int128 v54; // [rsp+F0h] [rbp-10h]
  __int128 v55; // [rsp+100h] [rbp+0h]
  __int128 v56; // [rsp+110h] [rbp+10h]
  _OWORD v57[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v58[128]; // [rsp+140h] [rbp+40h] BYREF
  void **v59; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v60[272]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v61[8]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v62[48]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v59);
  v59 = &StateRepository::Logging::CacheManagement::Cache_Update::`vftable';
  StateRepository::Logging::CacheManagement::Cache_Update::StartActivity(
    (StateRepository::Logging::CacheManagement::Cache_Update *)&v59,
    0);
  v36 = 0;
  v2 = StateRepository::Cache::Manager_NoThrow::Open(&v36, 1);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
      (const char *)(unsigned int)v2,
      v32);
    v27 = v36;
    v36 = 0;
    if ( v27 )
      ((void (*)(void))SRCacheManager_Close)();
    goto LABEL_56;
  }
  StateRepository::Database::Database((StateRepository::Database *)v58);
  v39 = 0;
  if ( !*(_QWORD *)a1 )
  {
    v5 = StateRepository::Repository::OpenDatabaseFromCache(1, v4, v58);
    v3 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
        (const char *)(unsigned int)v5,
        v32);
      StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
      StateRepository::Database::~Database((StateRepository::Database *)v58);
      v30 = v36;
      v36 = 0;
      if ( v30 )
        ((void (*)(void))SRCacheManager_Close)();
      goto LABEL_56;
    }
    a1 = (StateRepository::Database *)v58;
    v39 = v58;
  }
  v6 = 0;
  v38 = 0;
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v32 = 0;
    v14 = StateRepository::Database::BeginTransaction(a1, 3, &unk_1802A8E68, 0);
    v3 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
        (const char *)(unsigned int)v14,
        0);
      StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
      StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
      StateRepository::Database::~Database((StateRepository::Database *)v58);
      v31 = v36;
      v36 = 0;
      if ( v31 )
        ((void (*)(void))SRCacheManager_Close)();
      goto LABEL_56;
    }
    v6 = a1;
    v38 = a1;
  }
  v37 = 0;
  v7 = StateRepository::Entity::SRJournal::FindBySRCacheable_SortedBySequenceId(
         a1,
         (struct StateRepository::Statement *)&v37);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
      (const char *)(unsigned int)v7,
      v32);
    v15 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v37);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v15,
        v34);
    StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
    StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
    StateRepository::Database::~Database((StateRepository::Database *)v58);
    v16 = v36;
    v36 = 0;
    if ( v16 )
      ((void (*)(void))SRCacheManager_Close)();
LABEL_27:
    v59 = &StateRepository::Logging::CacheManagement::Cache_Update::`vftable';
    wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v59);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v62);
    wil::details::shared_object<wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>>::reset(v61);
    wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>(v60);
    return v8;
  }
  memset(v49, 0, sizeof(v49));
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  memset(v57, 0, sizeof(v57));
  if ( !v37 )
  {
    v8 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v32);
    goto LABEL_19;
  }
  v9 = StateRepository::Statement::dal_step(v37);
  v8 = v9;
  if ( v9 == -2018574236 )
  {
    v11 = 1;
    goto LABEL_10;
  }
  v11 = 0;
  if ( v9 != -2018574235 )
  {
    if ( v9 >= 0 )
    {
      while ( 1 )
      {
LABEL_31:
        if ( !v11 )
          goto LABEL_47;
        v42 = *((_QWORD *)&v54 + 1);
        v43 = v54;
        v44 = *((_QWORD *)&v53 + 1);
        v45 = v53;
        v46 = v51;
        v40 = HIDWORD(v50);
        v41 = v50;
        v47 = *(_QWORD *)&v57[0];
        v48 = v49[0];
        StateRepository::Logging::CacheManagement::Cache_Update::Cache_Update_SRJournalEntry<__int64,__int64,int,int,__int64,__int64,__int64,__int64,__int64>(
          (unsigned int)&v59,
          (unsigned int)&v48,
          (unsigned int)&v47,
          (unsigned int)&v41,
          (__int64)&v40,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42);
        updated = StateRepository::CacheManagement::_Update_JournalEntry(
                    a1,
                    (struct StateRepository::Cache::Manager_NoThrow *)&v36,
                    (struct StateRepository::Entity::SRJournal *)v49);
        v8 = updated;
        if ( updated < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17D,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
            (const char *)(unsigned int)updated,
            v32);
          StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v57 + 8));
          StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
          StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
          StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
          StateRepository::Database::~Database((StateRepository::Database *)v58);
          v28 = v36;
          v36 = 0;
          if ( v28 )
            ((void (*)(void))SRCacheManager_Close)();
          goto LABEL_27;
        }
        if ( !v37 )
        {
          v8 = -2147019873;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)0x8007139FLL,
            v32);
LABEL_43:
          v22 = 593;
LABEL_39:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-srjournal.cpp",
            (const char *)v8,
            v32);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17E,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
            (const char *)v8,
            v35);
          StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v57 + 8));
          StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
          StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
          StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
          StateRepository::Database::~Database((StateRepository::Database *)v58);
          v23 = v36;
          v36 = 0;
          if ( v23 )
            SRCacheManager_Close(v23);
          goto LABEL_41;
        }
        v20 = StateRepository::Statement::dal_step(v37);
        v8 = v20;
        if ( v20 == -2018574236 )
        {
          v11 = 1;
        }
        else
        {
          if ( v20 != -2018574235 )
          {
            if ( v20 < 0 )
              goto LABEL_43;
            goto LABEL_37;
          }
          v11 = 0;
        }
        if ( !v11 )
          goto LABEL_47;
LABEL_37:
        v8 = StateRepository::Entity::SRJournal::RowToObject(
               (const struct StateRepository::Statement *)&v37,
               (struct StateRepository::Entity::SRJournal *)v49,
               v21);
        if ( (v8 & 0x80000000) != 0 )
        {
          v22 = 596;
          goto LABEL_39;
        }
      }
    }
LABEL_19:
    v12 = 593;
    goto LABEL_13;
  }
LABEL_10:
  if ( v11 )
  {
    v8 = StateRepository::Entity::SRJournal::RowToObject(
           (const struct StateRepository::Statement *)&v37,
           (struct StateRepository::Entity::SRJournal *)v49,
           v10);
    if ( (v8 & 0x80000000) == 0 )
      goto LABEL_31;
    v12 = 596;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-srjournal.cpp",
      (const char *)v8,
      v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
      (const char *)v8,
      v33);
    StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v57 + 8));
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
    StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
    StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
    StateRepository::Database::~Database((StateRepository::Database *)v58);
    v13 = v36;
    v36 = 0;
    if ( v13 )
      SRCacheManager_Close(v13);
LABEL_41:
    StateRepository::Logging::CacheManagement::Cache_Update::~Cache_Update((StateRepository::Logging::CacheManagement::Cache_Update *)&v59);
    return v8;
  }
LABEL_47:
  v24 = StateRepository::Entity::SRJournal::Clear(a1);
  v8 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
      (const char *)(unsigned int)v24,
      v32);
    StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v57 + 8));
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
    StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
    StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
    StateRepository::Database::~Database((StateRepository::Database *)v58);
    v17 = v36;
    v36 = 0;
    if ( v17 )
      ((void (*)(void))SRCacheManager_Close)();
    goto LABEL_27;
  }
  if ( v6 )
  {
    v25 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)&v38);
    v3 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\cachemanagement.cpp",
        (const char *)(unsigned int)v25,
        v32);
      StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v57 + 8));
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
      StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
      StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
      StateRepository::Database::~Database((StateRepository::Database *)v58);
      v29 = v36;
      v36 = 0;
      if ( v29 )
        ((void (*)(void))SRCacheManager_Close)();
LABEL_56:
      v59 = &StateRepository::Logging::CacheManagement::Cache_Update::`vftable';
      wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v59);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v62);
      wil::details::shared_object<wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>>::reset(v61);
      wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>(v60);
      return v3;
    }
  }
  StateRepository::Blob::Reset((StateRepository::Blob *)((char *)v57 + 8));
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
  StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v38);
  StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache((StateRepository::AutoAddDatabaseToCache *)&v39);
  StateRepository::Database::~Database((StateRepository::Database *)v58);
  v26 = v36;
  v36 = 0;
  if ( v26 )
    SRCacheManager_Close(v26);
  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v59);
  v59 = &StateRepository::Logging::CacheManagement::Cache_Update::`vftable';
  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v59);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v62);
  wil::details::shared_object<wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>>::reset(v61);
  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>(v60);
  return 0;
}

```

## disassembly

```asm
0x180011280  mov     [rsp-8+arg_8], rbx
0x180011285  mov     [rsp-8+arg_10], rsi
0x18001128a  push    rbp
0x18001128b  push    rdi
0x18001128c  push    r12
0x18001128e  push    r14
0x180011290  push    r15
0x180011292  lea     rbp, [rsp-220h]
0x18001129a  sub     rsp, 320h
0x1800112a1  mov     rax, cs:__security_cookie
0x1800112a8  xor     rax, rsp
0x1800112ab  mov     [rbp+240h+var_30], rax
0x1800112b2  mov     r14, rcx
0x1800112b5  lea     rdx, aCacheUpdate; "Cache_Update"
0x1800112bc  lea     rcx, [rbp+240h+var_180]; struct wil::details::IFailureCallback *
0x1800112c3  call    ??0?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800112c8  lea     r12, ??_7Cache_Update@CacheManagement@Logging@StateRepository@@6B@; const StateRepository::Logging::CacheManagement::Cache_Update::`vftable'
0x1800112cf  mov     [rbp+240h+var_180], r12
0x1800112d6  xor     edx, edx; int
0x1800112d8  lea     rcx, [rbp+240h+var_180]; this
0x1800112df  call    ?StartActivity@Cache_Update@CacheManagement@Logging@StateRepository@@QEAAXH@Z; StateRepository::Logging::CacheManagement::Cache_Update::StartActivity(int)
0x1800112e4  nop
0x1800112e5  xor     r15d, r15d
0x1800112e8  mov     [rsp+340h+var_2F0], r15
0x1800112ed  lea     edx, [r15+1]
0x1800112f1  lea     rcx, [rsp+340h+var_2F0]
0x1800112f6  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x1800112fb  mov     ebx, eax
0x1800112fd  test    eax, eax
0x1800112ff  js      loc_1800118F5
0x180011305  lea     rcx, [rbp+240h+var_200]; this
0x180011309  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18001130e  mov     [rsp+340h+var_2D8], r15
0x180011313  cmp     [r14], r15
0x180011316  jnz     short loc_18001133C
0x180011318  lea     r8, [rbp+240h+var_200]
0x18001131c  lea     ecx, [r15+1]
0x180011320  call    ?OpenDatabaseFromCache@Repository@StateRepository@@SAJW4Partition@2@W4OpenFlags@12@AEAVDatabase@2@@Z; StateRepository::Repository::OpenDatabaseFromCache(StateRepository::Partition,StateRepository::Repository::OpenFlags,StateRepository::Database &)
0x180011325  mov     ebx, eax
0x180011327  test    eax, eax
0x180011329  js      loc_180011AA7
0x18001132f  lea     r14, [rbp+240h+var_200]
0x180011333  lea     rax, [rbp+240h+var_200]
0x180011337  mov     [rsp+340h+var_2D8], rax
0x18001133c  mov     rbx, r15
0x18001133f  mov     [rsp+340h+var_2E0], rbx
0x180011344  mov     rcx, r14; this
0x180011347  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001134c  test    al, al
0x18001134e  jnz     loc_180011472
0x180011354  mov     [rsp+340h+var_2E8], r15
0x180011359  lea     rdx, [rsp+340h+var_2E8]; struct StateRepository::Statement *
0x18001135e  mov     rcx, r14; struct StateRepository::Database *
0x180011361  call    ?FindBySRCacheable_SortedBySequenceId@SRJournal@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::SRJournal::FindBySRCacheable_SortedBySequenceId(StateRepository::Database &,StateRepository::Statement &)
0x180011366  mov     edi, eax
0x180011368  test    eax, eax
0x18001136a  js      loc_1800114CE
0x180011370  mov     [rbp+240h+var_290], r15
0x180011374  mov     [rbp+240h+var_288], r15
0x180011378  mov     [rbp+240h+var_280], r15
0x18001137c  mov     [rbp+240h+var_278], r15
0x180011380  mov     [rbp+240h+var_270], r15
0x180011384  mov     [rbp+240h+var_268], r15d
0x180011388  xorps   xmm0, xmm0
0x18001138b  movdqa  [rbp+240h+var_260], xmm0
0x180011390  xorps   xmm1, xmm1
0x180011393  movdqa  [rbp+240h+var_250], xmm1
0x180011398  movdqa  [rbp+240h+var_240], xmm0
0x18001139d  movdqa  [rbp+240h+var_230], xmm1
0x1800113a2  movdqa  [rbp+240h+var_220], xmm0
0x1800113a7  movdqa  [rbp+240h+var_210], xmm1
0x1800113ac  mov     rcx, [rsp+340h+var_2E8]; struct sqlite3_stmt *
0x1800113b1  test    rcx, rcx
0x1800113b4  jz      loc_1800114A4
0x1800113ba  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x1800113bf  mov     edi, eax
0x1800113c1  cmp     eax, 87AF0064h
0x1800113c6  jnz     loc_18001164C
0x1800113cc  mov     sil, 1
0x1800113cf  test    sil, sil
0x1800113d2  jz      loc_18001182F
0x1800113d8  lea     rdx, [rbp+240h+var_290]; struct StateRepository::Entity::SRJournal *
0x1800113dc  lea     rcx, [rsp+340h+var_2E8]; this
0x1800113e1  call    ?RowToObject@SRJournal@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::SRJournal::RowToObject(StateRepository::Statement const &,StateRepository::Entity::SRJournal &,__int64)
0x1800113e6  mov     edi, eax
0x1800113e8  test    eax, eax
0x1800113ea  jns     loc_180011662
0x1800113f0  mov     edx, 254h; void *
0x1800113f5  mov     r9d, edi; char *
0x1800113f8  lea     r8, aOnecoreBaseApp_476; "onecore\\base\\appmodel\\staterepositor"...
0x1800113ff  mov     rcx, [rbp+248h]; this
0x180011406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001140b  mov     rcx, [rbp+248h]; this
0x180011412  mov     r9d, edi; char *
0x180011415  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x18001141c  mov     edx, 177h; void *
0x180011421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011426  lea     rcx, [rbp+240h+var_220+8]; this
0x18001142a  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x18001142f  lea     rcx, [rsp+340h+var_2E8]; this
0x180011434  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180011439  lea     rcx, [rsp+340h+var_2E0]; this
0x18001143e  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x180011443  lea     rcx, [rsp+340h+var_2D8]; this
0x180011448  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x18001144d  lea     rcx, [rbp+240h+var_200]; this
0x180011451  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x180011456  nop
0x180011457  mov     rcx, [rsp+340h+var_2F0]
0x18001145c  mov     [rsp+340h+var_2F0], r15
0x180011461  test    rcx, rcx
0x180011464  jz      short loc_18001146D
0x180011466  call    cs:__imp_SRCacheManager_Close
0x18001146c  nop
0x18001146d  jmp     loc_1800117DF
0x180011472  mov     qword ptr [rsp+340h+var_320], r15; int
0x180011477  xor     r9d, r9d
0x18001147a  lea     r8, unk_1802A8E68
0x180011481  lea     edx, [r9+3]
0x180011485  mov     rcx, r14
0x180011488  call    ?BeginTransaction@Database@StateRepository@@QEAAJW4BeginTransactionLock@12@AEBU_GUID@@P6AJPEAX@Z2@Z; StateRepository::Database::BeginTransaction(StateRepository::Database::BeginTransactionLock,_GUID const &,long (*)(void *),void *)
0x18001148d  mov     ebx, eax
0x18001148f  test    eax, eax
0x180011491  js      loc_180011B2A
0x180011497  mov     rbx, r14
0x18001149a  mov     [rsp+340h+var_2E0], rbx
0x18001149f  jmp     loc_180011354
0x1800114a4  mov     rcx, [rbp+248h]; this
0x1800114ab  mov     edi, 8007139Fh
0x1800114b0  mov     r9d, edi; char *
0x1800114b3  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x1800114ba  mov     edx, 3Fh ; '?'; void *
0x1800114bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114c4  mov     edx, 251h
0x1800114c9  jmp     loc_1800113F5
0x1800114ce  mov     rcx, [rbp+248h]; this
0x1800114d5  mov     r9d, edi; char *
0x1800114d8  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x1800114df  mov     edx, 174h; void *
0x1800114e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114e9  lea     rcx, [rsp+340h+var_2E8]; this
0x1800114ee  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x1800114f3  mov     rcx, [rbp+248h]; this
0x1800114fa  test    eax, eax
0x1800114fc  jns     short loc_180011512
0x1800114fe  mov     r9d, eax; char *
0x180011501  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180011508  mov     edx, 16h; void *
0x18001150d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011512  lea     rcx, [rsp+340h+var_2E0]; this
0x180011517  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x18001151c  lea     rcx, [rsp+340h+var_2D8]; this
0x180011521  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x180011526  lea     rcx, [rbp+240h+var_200]; this
0x18001152a  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18001152f  nop
0x180011530  mov     rcx, [rsp+340h+var_2F0]
0x180011535  mov     [rsp+340h+var_2F0], r15
0x18001153a  test    rcx, rcx
0x18001153d  jz      short loc_180011546
0x18001153f  call    cs:__imp_SRCacheManager_Close
0x180011545  nop
0x180011546  mov     [rbp+240h+var_180], r12
0x18001154d  lea     rcx, [rbp+240h+var_180]
0x180011554  call    ?Destroy@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011559  nop
0x18001155a  lea     rcx, [rbp+240h+var_60]; this
0x180011561  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180011566  lea     rcx, [rbp+240h+var_68]
0x18001156d  call    ?reset@?$shared_object@V?$ActivityData@VService@Tracing@StateRepository@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180011572  lea     rcx, [rbp+240h+var_178]
0x180011579  call    ??1?$ActivityData@VService@Tracing@StateRepository@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001157e  nop
0x18001157f  jmp     loc_18001161F
0x180011584  mov     rcx, [rbp+248h]; this
0x18001158b  mov     r9d, edi; char *
0x18001158e  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x180011595  mov     edx, 182h; void *
0x18001159a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001159f  lea     rcx, [rbp+240h+var_220+8]; this
0x1800115a3  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x1800115a8  lea     rcx, [rsp+340h+var_2E8]; this
0x1800115ad  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800115b2  lea     rcx, [rsp+340h+var_2E0]; this
0x1800115b7  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x1800115bc  lea     rcx, [rsp+340h+var_2D8]; this
0x1800115c1  call    ??1AutoAddDatabaseToCache@StateRepository@@QEAA@XZ; StateRepository::AutoAddDatabaseToCache::~AutoAddDatabaseToCache(void)
0x1800115c6  lea     rcx, [rbp+240h+var_200]; this
0x1800115ca  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x1800115cf  nop
0x1800115d0  mov     rcx, [rsp+340h+var_2F0]
0x1800115d5  mov     [rsp+340h+var_2F0], r15
0x1800115da  test    rcx, rcx
0x1800115dd  jz      short loc_1800115E6
0x1800115df  call    cs:__imp_SRCacheManager_Close
0x1800115e5  nop
0x1800115e6  mov     [rbp+240h+var_180], r12
0x1800115ed  lea     rcx, [rbp+240h+var_180]
0x1800115f4  call    ?Destroy@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800115f9  nop
0x1800115fa  lea     rcx, [rbp+240h+var_60]; this
0x180011601  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180011606  lea     rcx, [rbp+240h+var_68]
0x18001160d  call    ?reset@?$shared_object@V?$ActivityData@VService@Tracing@StateRepository@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180011612  lea     rcx, [rbp+240h+var_178]
0x180011619  call    ??1?$ActivityData@VService@Tracing@StateRepository@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StateRepository::Tracing::Service,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001161e  nop
0x18001161f  mov     eax, edi
0x180011621  mov     rcx, [rbp+240h+var_30]
0x180011628  xor     rcx, rsp; StackCookie
0x18001162b  call    __security_check_cookie
0x180011630  lea     r11, [rsp+340h+var_20]
0x180011638  mov     rbx, [r11+38h]
0x18001163c  mov     rsi, [r11+40h]
0x180011640  mov     rsp, r11
0x180011643  pop     r15
0x180011645  pop     r14
0x180011647  pop     r12
0x180011649  pop     rdi
0x18001164a  pop     rbp
0x18001164b  retn
0x18001164c  mov     sil, r15b
0x18001164f  cmp     eax, 87AF0065h
0x180011654  jz      loc_1800113CF
0x18001165a  test    eax, eax
0x18001165c  js      loc_1800114C4
0x180011662  test    sil, sil
0x180011665  jz      loc_18001182F
0x18001166b  mov     rax, qword ptr [rbp+240h+var_250+8]
0x18001166f  mov     [rsp+340h+var_2C8], rax
0x180011674  mov     rax, qword ptr [rbp+240h+var_250]
0x180011678  mov     [rbp+240h+var_2C0], rax
0x18001167c  mov     rax, qword ptr [rbp+240h+var_260+8]
0x180011680  mov     [rbp+240h+var_2B8], rax
0x180011684  mov     rax, qword ptr [rbp+240h+var_260]
0x180011688  mov     [rbp+240h+var_2B0], rax
0x18001168c  mov     rax, [rbp+240h+var_270]
0x180011690  mov     [rbp+240h+var_2A8], rax
0x180011694  mov     eax, dword ptr [rbp+240h+var_278+4]
0x180011697  mov     [rsp+340h+var_2D0], eax
0x18001169b  mov     eax, dword ptr [rbp+240h+var_278]
0x18001169e  mov     [rsp+340h+var_2CC], eax
0x1800116a2  mov     rax, qword ptr [rbp+240h+var_220]
0x1800116a6  mov     [rbp+240h+var_2A0], rax
0x1800116aa  mov     rax, [rbp+240h+var_290]
0x1800116ae  mov     [rbp+240h+var_298], rax
0x1800116b2  lea     rax, [rsp+340h+var_2C8]
0x1800116b7  mov     [rsp+340h+var_2F8], rax
0x1800116bc  lea     rax, [rbp+240h+var_2C0]
0x1800116c0  mov     [rsp+340h+var_300], rax
0x1800116c5  lea     rax, [rbp+240h+var_2B8]
0x1800116c9  mov     [rsp+340h+var_308], rax
0x1800116ce  lea     rax, [rbp+240h+var_2B0]
0x1800116d2  mov     [rsp+340h+var_310], rax
0x1800116d7  lea     rax, [rbp+240h+var_2A8]
0x1800116db  mov     [rsp+340h+var_318], rax
0x1800116e0  lea     rax, [rsp+340h+var_2D0]
0x1800116e5  mov     qword ptr [rsp+340h+var_320], rax; int
0x1800116ea  lea     r9, [rsp+340h+var_2CC]
0x1800116ef  lea     r8, [rbp+240h+var_2A0]
0x1800116f3  lea     rdx, [rbp+240h+var_298]
0x1800116f7  lea     rcx, [rbp+240h+var_180]
0x1800116fe  call    ??$Cache_Update_SRJournalEntry@_J_JHH_J_J_J_J_J@Cache_Update@CacheManagement@Logging@StateRepository@@QEAAX$$QEA_J0$$QEAH100000@Z; StateRepository::Logging::CacheManagement::Cache_Update::Cache_Update_SRJournalEntry<__int64,__int64,int,int,__int64,__int64,__int64,__int64,__int64>(__int64 &&,__int64 &&,int &&,int &&,__int64 &&,__int64 &&,__int64 &&,__int64 &&,__int64 &&)
0x180011703  lea     r8, [rbp+240h+var_290]; struct StateRepository::Entity::SRJournal *
0x180011707  lea     rdx, [rsp+340h+var_2F0]; struct StateRepository::Cache::Manager_NoThrow *
0x18001170c  mov     rcx, r14; struct StateRepository::Database *
0x18001170f  call    ?_Update_JournalEntry@CacheManagement@StateRepository@@CAJAEAVDatabase@2@AEAVManager_NoThrow@Cache@2@AEAVSRJournal@Entity@2@@Z; StateRepository::CacheManagement::_Update_JournalEntry(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::Entity::SRJournal &)
0x180011714  mov     edi, eax
0x180011716  test    eax, eax
0x180011718  js      loc_180011967
0x18001171e  mov     rcx, [rsp+340h+var_2E8]; struct sqlite3_stmt *
0x180011723  test    rcx, rcx
0x180011726  jz      loc_1800117F0
0x18001172c  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x180011731  mov     edi, eax
0x180011733  cmp     eax, 87AF0064h
0x180011738  jnz     loc_18001181A
0x18001173e  mov     sil, 1
0x180011741  test    sil, sil
0x180011744  jz      loc_18001182F
0x18001174a  lea     rdx, [rbp+240h+var_290]; struct StateRepository::Entity::SRJournal *
0x18001174e  lea     rcx, [rsp+340h+var_2E8]; this
0x180011753  call    ?RowToObject@SRJournal@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::SRJournal::RowToObject(StateRepository::Statement const &,StateRepository::Entity::SRJournal &,__int64)
0x180011758  mov     edi, eax
0x18001175a  test    eax, eax
0x18001175c  jns     loc_180011662
0x180011762  mov     edx, 254h; void *
0x180011767  mov     r9d, edi; char *
0x18001176a  lea     r8, aOnecoreBaseApp_476; "onecore\\base\\appmodel\\staterepositor"...
0x180011771  mov     rcx, [rbp+248h]; this
0x180011778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001177d  mov     rcx, [rbp+248h]; this
0x180011784  mov     r9d, edi; char *
0x180011787  lea     r8, aOnecoreBaseApp_221; "onecore\\base\\appmodel\\staterepositor"...
0x18001178e  mov     edx, 17Eh; void *
0x180011793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011798  lea     rcx, [rbp+240h+var_220+8]; this
0x18001179c  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x1800117a1  lea     rcx, [rsp+340h+var_2E8]; this
0x1800117a6  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
  ... truncated ...
```
