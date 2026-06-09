# WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::GetOrCreateTileWrapper(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *,bool,WindowsInternal::Shell::UnifiedTile::IUnifiedTile * *)

- ea: `0x18001e570`
- end: `0x18001f098`
- name: `?GetOrCreateTileWrapper@UnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@AEAAJPEAUIUnifiedTileIdentifier@234@_NPEAPEAUIUnifiedTile@234@@Z`
- size: `2856`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, bool, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile **)`
- caller_count: `3`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x180020530`
- `0x180078ab0`
- `0x18012ca80`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18001dac0`
- `0x18001e570`
- `0x18001f0a0`
- `0x18001f268`
- `0x18001f2d8`
- `0x180020078`
- `0x1800203d4`
- `0x180020474`
- `0x1800204d0`
- `0x180020574`
- `0x1800205c8`
- `0x1800206d0`
- `0x180020e34`
- `0x1800223a4`
- `0x1800468f8`
- `0x18007a720`
- `0x1800d0fc0`
- `0x1800d42d0`
- `0x180119d94`
- `0x180136f44`
- `0x1801593b0`
- `0x18020be0c`
- `0x1802eb8c8`
- `0x1802ebaa8`
- `0x1802f1d18`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e6c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001eb86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e6c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001eb86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e825`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ecc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ef8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e825`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ecc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ed21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ef8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e5f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e5f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e75b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f004`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e75b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f045`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f063`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f081`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f045`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f063`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f037`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f073`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f037`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e5c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ea3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eadb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ee31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e5c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ea3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eadb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ee31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e7bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ec8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e7bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ec8a`

## string_xrefs

- `0x18001e746`: `shellcommon\shell\DataStoreCache\inc\DataStoreCacheItemIdentifier.h`
- `0x18001e5a2`: `UnifiedTileManager_GetOrCreateTileWrapper`
- `0x18001e80b`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18001ea96`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18001eb71`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18001ecd8`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18001ed03`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18001ed37`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18001ef71`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`
- `0x18001efeb`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::GetOrCreateTileWrapper(
        RTL_SRWLOCK *this,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *a2,
        char a3,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile **a4)
{
  __int64 (*v8)(void); // rbx
  int v9; // eax
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v10; // rcx
  struct DataStoreCache::IDataItem **v11; // rax
  bool v12; // di
  __int64 v13; // rcx
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v14; // r10
  PVOID *v15; // rax
  char *v16; // rdi
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v17; // rcx
  int v18; // eax
  unsigned int v19; // edi
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v20; // rcx
  volatile signed __int64 *v21; // r8
  signed __int64 v22; // rcx
  signed __int32 v23; // edx
  bool v24; // zf
  signed __int64 v25; // rax
  signed __int32 j; // r9d
  const char *v27; // r9
  __int64 result; // rax
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v29; // rax
  __int64 v30; // rax
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v31; // r10
  __int64 v32; // rax
  volatile int *v33; // rdx
  __int64 v34; // r8
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v35; // r9
  signed __int64 v36; // rax
  signed __int64 v37; // rtt
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v38; // rcx
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v39; // rcx
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v40; // rcx
  int v41; // eax
  unsigned int v42; // ebx
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v43; // rcx
  char *v44; // rdx
  PVOID *v45; // rax
  int v46; // eax
  unsigned int v47; // edi
  int v48; // eax
  int v49; // eax
  _QWORD *v50; // rax
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v51; // rcx
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v52; // rcx
  volatile signed __int64 *v53; // r9
  signed __int64 v54; // rcx
  signed __int32 v55; // r8d
  signed __int64 v56; // rax
  signed __int32 i; // r8d
  __int64 v58; // rax
  int Interface; // eax
  unsigned int v60; // edi
  void *v61; // rbx
  HANDLE ProcessHeap; // rax
  void *v63; // rbx
  HANDLE v64; // rax
  void *v65; // rbx
  HANDLE v66; // rax
  WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *v67; // [rsp+20h] [rbp-A8h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v68; // [rsp+28h] [rbp-A0h] BYREF
  _QWORD v69[2]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v70[16]; // [rsp+40h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-78h]
  char v72; // [rsp+58h] [rbp-70h]
  _BYTE v73[24]; // [rsp+60h] [rbp-68h] BYREF
  int v74; // [rsp+78h] [rbp-50h]
  RTL_SRWLOCK *v75; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *StringRawBuffer; // [rsp+D8h] [rbp+10h] BYREF
  HSTRING string; // [rsp+E8h] [rbp+20h] BYREF

  StringRawBuffer = a2;
  *a4 = 0;
  UnifiedTileTelemetry::WatchCurrentThread(v70, "UnifiedTileManager_GetOrCreateTileWrapper");
  string = 0;
  v8 = *(__int64 (**)(void))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  try
  {
    v9 = v8();
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"shellcommon\\shell\\DataStoreCache\\inc\\DataStoreCacheItemIdentifier.h",
        (const char *)(unsigned int)v9,
        (int)v67);
    AcquireSRWLockShared(this + 73);
    std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(
      &this[30],
      v69,
      &string);
    if ( (PVOID)v69[0] == this[31].Ptr )
    {
      if ( a3 )
      {
        v58 = std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(
                &this[38],
                v69,
                &string);
        if ( *(PVOID *)v58 != this[39].Ptr )
        {
          Interface = WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::QueryInterface(
                        *(WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper **)(*(_QWORD *)v58 + 24LL),
                        &GUID_65b4e03e_a32e_40cf_8bab_b2d9c5287307,
                        (void **)a4);
          v60 = Interface;
          if ( Interface < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x540,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
              (const char *)(unsigned int)Interface,
              (int)v67);
            if ( this != (RTL_SRWLOCK *)-584LL )
              ReleaseSRWLockShared(this + 73);
            WindowsDeleteString(string);
            string = 0;
            wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v70);
            return v60;
          }
        }
      }
    }
    else
    {
      v10 = *(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile **)(v69[0] + 24LL);
      *a4 = v10;
      (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    if ( this != (RTL_SRWLOCK *)-584LL )
      ReleaseSRWLockShared(this + 73);
    if ( *a4 )
      goto LABEL_60;
    v67 = 0;
    v68 = 0;
    v11 = (struct DataStoreCache::IDataItem **)(*(__int64 (__fastcall **)(PVOID, _QWORD *, HSTRING))(*(_QWORD *)this[17].Ptr + 40LL))(
                                                 this[17].Ptr,
                                                 v69,
                                                 string);
    v12 = (int)WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::CreateTileFromDataItem(
                 (WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *)this,
                 *v11,
                 &v68) >= 0;
    v13 = v69[0];
    if ( v69[0] )
    {
      v69[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    if ( v12 )
    {
      AcquireSRWLockExclusive(this + 73);
      v69[0] = this + 73;
      std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(
        &this[30],
        &StringRawBuffer,
        &string);
      if ( StringRawBuffer == this[31].Ptr )
      {
        v15 = (PVOID *)std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(
                         &this[38],
                         &StringRawBuffer,
                         &string);
        v16 = (char *)*v15;
        if ( *v15 != this[39].Ptr )
        {
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::operator=(&v67, v16 + 24);
          std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>>>,0>(
            &this[38],
            &StringRawBuffer,
            v16);
          StringRawBuffer = (struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)WindowsGetStringRawBuffer(
                                                                                                    string,
                                                                                                    0);
          UnifiedTileTelemetry::UnifiedTileManager_EmptyTileReplaced<unsigned short const *>(&StringRawBuffer);
        }
        v17 = v67;
        if ( !v67 )
        {
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(&v67);
          v67 = 0;
          v29 = (WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *)operator new(
                                                                             0xE0u,
                                                                             (const struct std::nothrow_t *)std::nothrow);
          if ( !v29 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x569,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
              (const char *)0x8007000ELL,
              (int)v67);
            if ( this != (RTL_SRWLOCK *)-584LL )
              ReleaseSRWLockExclusive(this + 73);
            v52 = v68;
            if ( v68 )
            {
              v68 = 0;
              (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v52 + 16LL))(v52);
            }
            v53 = (volatile signed __int64 *)v67;
            if ( v67 )
            {
              v67 = 0;
              v54 = *((_QWORD *)v53 + 12);
              while ( v54 >= 0 )
              {
                if ( (_DWORD)v54 == 0x7FFFFFFF )
                  goto LABEL_112;
                v55 = v54 - 1;
                v56 = _InterlockedCompareExchange64(v53 + 12, v54 - 1, v54);
                v24 = v54 == v56;
                v54 = v56;
                if ( v24 )
                  goto LABEL_111;
              }
              for ( i = *(_DWORD *)(2 * v54 + 0x10); i != 0x7FFFFFFF; i = *(_DWORD *)(2 * v54 + 0x10) )
              {
                if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v54 + 16), i - 1, i) )
                  break;
              }
              v55 = i - 1;
LABEL_111:
              if ( !v55 )
              {
                (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*v53 + 176))(v53, 1);
                if ( Microsoft::WRL::Details::ModuleBase::module_ )
                  (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                       + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
              }
            }
LABEL_112:
            WindowsDeleteString(string);
            string = 0;
            if ( v74 )
              wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v73);
            if ( v72 )
            {
              v61 = lpMem;
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v61);
            }
            return 2147942414LL;
          }
          v30 = WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::UnifiedTileWrapper(v29);
          StringRawBuffer = (struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)v30;
          *(RTL_SRWLOCK *)(v30 + 120) = this[71];
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile2,WindowsInternal::Shell::UnifiedTile::IUnifiedTile3,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate,Microsoft::WRL::CloakedIid<INotificationStateChange>,Microsoft::WRL::CloakedIid<ITileNotificationCollection>,Microsoft::WRL::FtmBase>::InternalAddRef(v30);
          v67 = v31;
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(&StringRawBuffer);
          v17 = v67;
        }
        v18 = WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::SetInternalTile(v17, v68, 0);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56C,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
            (const char *)(unsigned int)v18,
            (int)v67);
          if ( this != (RTL_SRWLOCK *)-584LL )
            ReleaseSRWLockExclusive(this + 73);
          v20 = v68;
          if ( v68 )
          {
            v68 = 0;
            (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v20 + 16LL))(v20);
          }
          v21 = (volatile signed __int64 *)v67;
          if ( v67 )
          {
            v67 = 0;
            v22 = *((_QWORD *)v21 + 12);
            while ( v22 >= 0 )
            {
              if ( (_DWORD)v22 == 0x7FFFFFFF )
                goto LABEL_36;
              v23 = v22 - 1;
              v25 = _InterlockedCompareExchange64(v21 + 12, v22 - 1, v22);
              v24 = v22 == v25;
              v22 = v25;
              if ( v24 )
                goto LABEL_35;
            }
            for ( j = *(_DWORD *)(2 * v22 + 0x10); j != 0x7FFFFFFF; j = *(_DWORD *)(2 * v22 + 0x10) )
            {
              if ( j == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v22 + 16), j - 1, j) )
                break;
            }
            v23 = j - 1;
LABEL_35:
            if ( !v23 )
            {
              (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*v21 + 176))(v21, 1);
              if ( Microsoft::WRL::Details::ModuleBase::module_ )
                (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                     + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
            }
          }
LABEL_36:
          WindowsDeleteString(string);
          string = 0;
          if ( v74 )
            wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v73);
          if ( v72 )
          {
            v63 = lpMem;
            v64 = GetProcessHeap();
            HeapFree(v64, 0, v63);
          }
          return v19;
        }
        v32 = std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::_Try_emplace<DataStoreCache::DataItemIdentifier const &,>(
                &this[30],
                &v75,
                &string);
        v34 = *(_QWORD *)v32;
        v35 = v67;
        if ( *(WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper **)(*(_QWORD *)v32 + 24LL) != v67 )
        {
          if ( v67 )
          {
            v36 = *((_QWORD *)v67 + 12);
            while ( v36 >= 0 )
            {
              if ( (_DWORD)v36 != 0x7FFFFFFF )
              {
                v37 = v36;
                v36 = _InterlockedCompareExchange64((volatile signed __int64 *)v35 + 12, v36 + 1, v36);
                if ( v37 != v36 )
                  continue;
              }
              goto LABEL_49;
            }
            Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v36 + 16), v33);
          }
LABEL_49:
          v38 = *(WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper **)(v34 + 24);
          *(_QWORD *)(v34 + 24) = v35;
          if ( v38 )
            WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::Release(v38);
        }
      }
      else
      {
        v14 = (WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *)*((_QWORD *)StringRawBuffer + 3);
        if ( v67 != v14 )
        {
          if ( v14 )
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile2,WindowsInternal::Shell::UnifiedTile::IUnifiedTile3,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate,Microsoft::WRL::CloakedIid<INotificationStateChange>,Microsoft::WRL::CloakedIid<ITileNotificationCollection>,Microsoft::WRL::FtmBase>::InternalAddRef(*((_QWORD *)StringRawBuffer + 3));
          StringRawBuffer = v67;
          v67 = v14;
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(&StringRawBuffer);
        }
      }
      if ( this == (RTL_SRWLOCK *)-584LL )
        goto LABEL_54;
      goto LABEL_85;
    }
    if ( !a3 )
    {
LABEL_54:
      if ( !v67 )
      {
        if ( a3 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x592,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
            0);
        goto LABEL_56;
      }
      v41 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile2,WindowsInternal::Shell::UnifiedTile::IUnifiedTile3,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate,Microsoft::WRL::CloakedIid<INotificationStateChange>,Microsoft::WRL::CloakedIid<ITileNotificationCollection>,Microsoft::WRL::FtmBase>>(
              v67,
              &GUID_65b4e03e_a32e_40cf_8bab_b2d9c5287307,
              a4);
      v42 = v41;
      if ( v41 >= 0 )
      {
LABEL_56:
        v39 = v68;
        if ( v68 )
        {
          v68 = 0;
          (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v39 + 16LL))(v39);
        }
        v40 = v67;
        if ( v67 )
        {
          v67 = 0;
          WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::Release(v40);
        }
LABEL_60:
        WindowsDeleteString(string);
        string = 0;
        if ( v74 )
          wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v73);
        if ( v72 )
        {
          v65 = lpMem;
          v66 = GetProcessHeap();
          HeapFree(v66, 0, v65);
        }
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58D,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
        (const char *)(unsigned int)v41,
        (int)v67);
      v43 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v43 + 16LL))(v43);
      }
      Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(&v67);
      WindowsDeleteString(string);
      string = 0;
      if ( v74 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v73);
      wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)v70);
      return v42;
    }
    AcquireSRWLockExclusive(this + 73);
    v75 = this + 73;
    std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(
      &this[38],
      v69,
      &string);
    v44 = (char *)v69[0];
    if ( (PVOID)v69[0] != this[39].Ptr
      || (v45 = (PVOID *)std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(
                           &this[30],
                           v69,
                           &string),
          v44 = (char *)*v45,
          *v45 != this[31].Ptr) )
    {
      Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::operator=(&v67, v44 + 24);
LABEL_84:
      if ( this != (RTL_SRWLOCK *)-584LL )
      {
LABEL_85:
        ReleaseSRWLockExclusive(this + 73);
        goto LABEL_54;
      }
      goto LABEL_54;
    }
    v46 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper,WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper,enum WindowsInternal::Shell::UnifiedTile::TileSources &,enum WindowsInternal::Shell::UnifiedTile::TileFeatures &>(
            &v67,
            (char *)&this[71].Ptr + 4,
            &this[71]);
    v47 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x579,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
        (const char *)(unsigned int)v46,
        (int)v67);
      if ( this != (RTL_SRWLOCK *)-584LL )
        ReleaseSRWLockExclusive(this + 73);
      v51 = v68;
      if ( !v68 )
        goto LABEL_98;
    }
    else
    {
      v69[0] = this;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      v48 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::EmptyUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * &,WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *>((void **)&v68);
      v47 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57A,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
          (const char *)(unsigned int)v48,
          (int)v67);
        if ( this != (RTL_SRWLOCK *)-584LL )
          ReleaseSRWLockExclusive(this + 73);
        v51 = v68;
        if ( !v68 )
          goto LABEL_98;
      }
      else
      {
        v49 = WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::SetInternalTile(v67, v68, 0);
        v47 = v49;
        if ( v49 >= 0 )
        {
          v50 = (_QWORD *)std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::_Try_emplace<DataStoreCache::DataItemIdentifier const &,>(
                            &this[38],
                            v69,
                            &string);
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::operator=(*v50 + 24LL, &v67);
          StringRawBuffer = (struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)WindowsGetStringRawBuffer(
                                                                                                    string,
                                                                                                    0);
          UnifiedTileTelemetry::UnifiedTileManager_EmptyTileCreated<unsigned short const *>(&StringRawBuffer);
          goto LABEL_84;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57B,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
          (const char *)(unsigned int)v49,
          (int)v67);
        if ( this != (RTL_SRWLOCK *)-584LL )
          ReleaseSRWLockExclusive(this + 73);
        v51 = v68;
        if ( !v68 )
        {
LABEL_98:
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(&v67);
          WindowsDeleteString(string);
          string = 0;
          wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v70);
          return v47;
        }
      }
    }
    v68 = 0;
    (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v51 + 16LL))(v51);
    goto LABEL_98;
  }
  catch ( ... )
  {
    LODWORD(StringRawBuffer) = wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x597,
                                 (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilemanager.cpp",
                                 v27);
    return (unsigned int)StringRawBuffer;
  }
  return result;
}

```

## disassembly

```asm
0x18001e570  mov     [rsp+arg_0], rbx
0x18001e575  mov     [rsp+arg_10], rsi
0x18001e57a  mov     [rsp+arg_8], rdx
0x18001e57f  push    rdi
0x18001e580  push    r12
0x18001e582  push    r13
0x18001e584  push    r14
0x18001e586  push    r15
0x18001e588  sub     rsp, 0A0h
0x18001e58f  mov     r15, r9
0x18001e592  movzx   r12d, r8b
0x18001e596  mov     rdi, rdx
0x18001e599  mov     rsi, rcx
0x18001e59c  xor     r13d, r13d
0x18001e59f  mov     [r9], r13
0x18001e5a2  lea     rdx, aUnifiedtileman_3; "UnifiedTileManager_GetOrCreateTileWrapp"...
0x18001e5a9  lea     rcx, [rsp+0C8h+var_88]
0x18001e5ae  call    ?WatchCurrentThread@UnifiedTileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; UnifiedTileTelemetry::WatchCurrentThread(char const *)
0x18001e5b3  nop
0x18001e5b4  mov     [rsp+0C8h+string], r13
0x18001e5bc  mov     rax, [rdi]
0x18001e5bf  mov     rbx, [rax+38h]
0x18001e5c3  xor     ecx, ecx; string
0x18001e5c5  call    cs:__imp_WindowsDeleteString
0x18001e5cb  mov     [rsp+0C8h+string], r13
0x18001e5d3  lea     rdx, [rsp+0C8h+string]
0x18001e5db  mov     rcx, rdi
0x18001e5de  mov     rax, rbx
0x18001e5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5e6  test    eax, eax
0x18001e5e8  js      loc_18001E73B
0x18001e5ee  lea     rbx, [rsi+248h]
0x18001e5f5  mov     rcx, rbx; SRWLock
0x18001e5f8  call    cs:__imp_AcquireSRWLockShared
0x18001e5fe  lea     r8, [rsp+0C8h+string]
0x18001e606  lea     rdx, [rsp+0C8h+var_98]
0x18001e60b  lea     rcx, [rsi+0F0h]
0x18001e612  call    ?find@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(DataStoreCache::DataItemIdentifier const &)
0x18001e617  mov     rax, [rsp+0C8h+var_98]
0x18001e61c  cmp     rax, [rsi+0F8h]
0x18001e623  jz      short loc_18001E63B
0x18001e625  mov     rcx, [rax+18h]
0x18001e629  mov     [r15], rcx
0x18001e62c  mov     rax, [rcx]
0x18001e62f  mov     rax, [rax+8]
0x18001e633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e638  nop
0x18001e639  jmp     short loc_18001E644
0x18001e63b  test    r12b, r12b
0x18001e63e  jnz     loc_18001EF9A
0x18001e644  test    rbx, rbx
0x18001e647  jnz     loc_18001E758
0x18001e64d  cmp     qword ptr [r15], 0
0x18001e651  jnz     loc_18001EA35
0x18001e657  mov     [rsp+0C8h+var_A8], r13; int
0x18001e65c  mov     [rsp+0C8h+var_A0], r13
0x18001e661  mov     rcx, [rsi+88h]
0x18001e668  mov     rax, [rcx]
0x18001e66b  mov     r8, [rsp+0C8h+string]
0x18001e673  lea     rdx, [rsp+0C8h+var_98]
0x18001e678  mov     rax, [rax+28h]
0x18001e67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e681  nop
0x18001e682  lea     r8, [rsp+0C8h+var_A0]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile **
0x18001e687  mov     rdx, [rax]; struct DataStoreCache::IDataItem *
0x18001e68a  mov     rcx, rsi; this
0x18001e68d  call    ?CreateTileFromDataItem@UnifiedTileManager@UnifiedTile@Shell@WindowsInternal@@AEAAJPEAUIDataItem@DataStoreCache@@PEAPEAUIUnifiedTile@234@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileManager::CreateTileFromDataItem(DataStoreCache::IDataItem *,WindowsInternal::Shell::UnifiedTile::IUnifiedTile * *)
0x18001e692  mov     edi, eax
0x18001e694  shr     edi, 1Fh
0x18001e697  xor     dil, 1
0x18001e69b  mov     rcx, [rsp+0C8h+var_98]
0x18001e6a0  test    rcx, rcx
0x18001e6a3  jz      short loc_18001E6B7
0x18001e6a5  mov     [rsp+0C8h+var_98], r13
0x18001e6aa  mov     rax, [rcx]
0x18001e6ad  mov     rax, [rax+10h]
0x18001e6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6b6  nop
0x18001e6b7  test    dil, dil
0x18001e6ba  jz      loc_18001E9DD
0x18001e6c0  mov     rcx, rbx; SRWLock
0x18001e6c3  call    cs:__imp_AcquireSRWLockExclusive
0x18001e6c9  mov     [rsp+0C8h+var_98], rbx
0x18001e6ce  lea     r8, [rsp+0C8h+string]
0x18001e6d6  lea     rdx, [rsp+0C8h+arg_8]
0x18001e6de  lea     rcx, [rsi+0F0h]
0x18001e6e5  call    ?find@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(DataStoreCache::DataItemIdentifier const &)
0x18001e6ea  mov     rax, [rsp+0C8h+arg_8]
0x18001e6f2  cmp     rax, [rsi+0F8h]
0x18001e6f9  jz      short loc_18001E766
0x18001e6fb  mov     r10, [rax+18h]
0x18001e6ff  cmp     [rsp+0C8h+var_A8], r10
0x18001e704  jz      loc_18001E9D2
0x18001e70a  test    r10, r10
0x18001e70d  jz      short loc_18001E717
0x18001e70f  mov     rcx, r10
0x18001e712  call    ?InternalAddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTile2@567@UIUnifiedTile3@567@UIUnifiedTilePrivate@Private@567@U?$CloakedIid@UINotificationStateChange@@@23@U?$CloakedIid@UITileNotificationCollection@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile2,WindowsInternal::Shell::UnifiedTile::IUnifiedTile3,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate,Microsoft::WRL::CloakedIid<INotificationStateChange>,Microsoft::WRL::CloakedIid<ITileNotificationCollection>,Microsoft::WRL::FtmBase>::InternalAddRef(void)
0x18001e717  mov     rax, [rsp+0C8h+var_A8]
0x18001e71c  mov     [rsp+0C8h+arg_8], rax
0x18001e724  mov     [rsp+0C8h+var_A8], r10
0x18001e729  lea     rcx, [rsp+0C8h+arg_8]
0x18001e731  call    ?InternalRelease@?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(void)
0x18001e736  jmp     loc_18001E9D2
0x18001e73b  mov     rcx, [rsp+0C8h]; this
0x18001e743  mov     r9d, eax; char *
0x18001e746  lea     r8, aShellcommonShe_92; "shellcommon\\shell\\DataStoreCache\\inc"...
0x18001e74d  mov     edx, 80h; void *
0x18001e752  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e758  mov     rcx, rbx; SRWLock
0x18001e75b  call    cs:__imp_ReleaseSRWLockShared
0x18001e761  jmp     loc_18001E64D
0x18001e766  lea     r8, [rsp+0C8h+string]
0x18001e76e  lea     rdx, [rsp+0C8h+arg_8]
0x18001e776  lea     rcx, [rsi+130h]
0x18001e77d  call    ?find@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::find(DataStoreCache::DataItemIdentifier const &)
0x18001e782  mov     rdi, [rax]
0x18001e785  cmp     rdi, [rsi+138h]
0x18001e78c  jz      short loc_18001E7D8
0x18001e78e  lea     rdx, [rdi+18h]
0x18001e792  lea     rcx, [rsp+0C8h+var_A8]
0x18001e797  call    ??4?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::operator=(Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper> const &)
0x18001e79c  mov     r8, rdi
0x18001e79f  lea     rdx, [rsp+0C8h+arg_8]
0x18001e7a7  lea     rcx, [rsi+130h]
0x18001e7ae  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>>>)
0x18001e7b3  xor     edx, edx; length
0x18001e7b5  mov     rcx, [rsp+0C8h+string]; string
0x18001e7bd  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e7c3  mov     [rsp+0C8h+arg_8], rax
0x18001e7cb  lea     rcx, [rsp+0C8h+arg_8]
0x18001e7d3  call    ??$UnifiedTileManager_EmptyTileReplaced@PEBG@UnifiedTileTelemetry@@SAX$$QEAPEBG@Z; UnifiedTileTelemetry::UnifiedTileManager_EmptyTileReplaced<ushort const *>(ushort const * &&)
0x18001e7d8  mov     rcx, [rsp+0C8h+var_A8]; this
0x18001e7dd  test    rcx, rcx
0x18001e7e0  jz      loc_18001E8FB
0x18001e7e6  xor     r13d, r13d
0x18001e7e9  xor     r8d, r8d; struct DataStoreCache::IDataItemChangeEvent *
0x18001e7ec  mov     rdx, [rsp+0C8h+var_A0]; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *
0x18001e7f1  call    ?SetInternalTile@UnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUIUnifiedTile@234@PEAUIDataItemChangeEvent@DataStoreCache@@@Z; WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::SetInternalTile(WindowsInternal::Shell::UnifiedTile::IUnifiedTile *,DataStoreCache::IDataItemChangeEvent *)
0x18001e7f6  mov     edi, eax
0x18001e7f8  test    eax, eax
0x18001e7fa  jns     loc_18001E970
0x18001e800  mov     rcx, [rsp+0C8h]; this
0x18001e808  mov     r9d, eax; char *
0x18001e80b  lea     r8, aShellcommonShe_56; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18001e812  mov     edx, 56Ch; void *
0x18001e817  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e81c  nop
0x18001e81d  test    rbx, rbx
0x18001e820  jz      short loc_18001E82C
0x18001e822  mov     rcx, rbx; SRWLock
0x18001e825  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e82b  nop
0x18001e82c  mov     rcx, [rsp+0C8h+var_A0]
0x18001e831  test    rcx, rcx
0x18001e834  jz      short loc_18001E848
0x18001e836  mov     [rsp+0C8h+var_A0], r13
0x18001e83b  mov     rax, [rcx]
0x18001e83e  mov     rax, [rax+10h]
0x18001e842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e847  nop
0x18001e848  mov     r8, [rsp+0C8h+var_A8]
0x18001e84d  test    r8, r8
0x18001e850  jz      short loc_18001E8A9
0x18001e852  mov     [rsp+0C8h+var_A8], r13
0x18001e857  mov     rcx, [r8+60h]
0x18001e85b  test    rcx, rcx
0x18001e85e  js      short loc_18001E87C
0x18001e860  cmp     ecx, 7FFFFFFFh
0x18001e866  jz      short loc_18001E8A9
0x18001e868  lea     rdx, [rcx-1]
0x18001e86c  mov     rax, rcx
0x18001e86f  lock cmpxchg [r8+60h], rdx
0x18001e875  mov     rcx, rax
0x18001e878  jnz     short loc_18001E85B
0x18001e87a  jmp     short loc_18001E8A1
0x18001e87c  mov     r9d, [rcx+rcx+10h]
0x18001e881  cmp     r9d, 7FFFFFFFh
0x18001e888  jz      short loc_18001E89D
0x18001e88a  lea     edx, [r9-1]
0x18001e88e  mov     eax, r9d
0x18001e891  lock cmpxchg [rcx+rcx+10h], edx
0x18001e897  jnz     loc_18001EB10
0x18001e89d  lea     edx, [r9-1]
0x18001e8a1  test    edx, edx
0x18001e8a3  jz      loc_18001EB27
0x18001e8a9  mov     rcx, [rsp+0C8h+string]; string
0x18001e8b1  call    cs:__imp_WindowsDeleteString
0x18001e8b7  mov     [rsp+0C8h+string], r13
0x18001e8bf  cmp     [rsp+0C8h+var_50], 0
0x18001e8c4  jz      short loc_18001E8D1
0x18001e8c6  lea     rcx, [rsp+0C8h+var_68]; this
0x18001e8cb  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001e8d0  nop
0x18001e8d1  cmp     [rsp+0C8h+var_70], 0
0x18001e8d6  jnz     loc_18001F050
0x18001e8dc  mov     eax, edi
0x18001e8de  lea     r11, [rsp+0C8h+var_28]
0x18001e8e6  mov     rbx, [r11+30h]
0x18001e8ea  mov     rsi, [r11+40h]
0x18001e8ee  mov     rsp, r11
0x18001e8f1  pop     r15
0x18001e8f3  pop     r14
0x18001e8f5  pop     r13
0x18001e8f7  pop     r12
0x18001e8f9  pop     rdi
0x18001e8fa  retn
0x18001e8fb  lea     rcx, [rsp+0C8h+var_A8]
0x18001e900  call    ?InternalRelease@?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(void)
0x18001e905  xor     r13d, r13d
0x18001e908  mov     [rsp+0C8h+var_A8], r13; int
0x18001e90d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e914  mov     ecx, 0E0h; unsigned __int64
0x18001e919  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e91e  test    rax, rax
0x18001e921  jz      loc_18001EF63
0x18001e927  mov     rcx, rax; this
0x18001e92a  call    ??0UnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@QEAA@XZ; WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::UnifiedTileWrapper(void)
0x18001e92f  mov     r10, rax
0x18001e932  mov     [rsp+0C8h+arg_8], rax
0x18001e93a  mov     edx, [rsi+238h]
0x18001e940  mov     ecx, [rsi+23Ch]
0x18001e946  mov     [rax+7Ch], ecx
0x18001e949  mov     [rax+78h], edx
0x18001e94c  mov     rcx, rax
0x18001e94f  call    ?InternalAddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTile2@567@UIUnifiedTile3@567@UIUnifiedTilePrivate@Private@567@U?$CloakedIid@UINotificationStateChange@@@23@U?$CloakedIid@UITileNotificationCollection@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile2,WindowsInternal::Shell::UnifiedTile::IUnifiedTile3,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate,Microsoft::WRL::CloakedIid<INotificationStateChange>,Microsoft::WRL::CloakedIid<ITileNotificationCollection>,Microsoft::WRL::FtmBase>::InternalAddRef(void)
0x18001e954  mov     [rsp+0C8h+var_A8], r10
0x18001e959  lea     rcx, [rsp+0C8h+arg_8]
0x18001e961  call    ?InternalRelease@?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>::InternalRelease(void)
0x18001e966  mov     rcx, [rsp+0C8h+var_A8]
0x18001e96b  jmp     loc_18001E7E9
0x18001e970  lea     r8, [rsp+0C8h+string]
0x18001e978  lea     rdx, [rsp+0C8h+var_38]
0x18001e980  lea     rcx, [rsi+0F0h]
0x18001e987  call    ??$_Try_emplace@AEBVDataItemIdentifier@DataStoreCache@@$$V@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@VUnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper>>>,0>>::_Try_emplace<DataStoreCache::DataItemIdentifier const &,>(DataStoreCache::DataItemIdentifier const &)
0x18001e98c  mov     r8, [rax]
0x18001e98f  mov     r9, [rsp+0C8h+var_A8]
0x18001e994  cmp     [r8+18h], r9
0x18001e998  jz      short loc_18001E9D2
0x18001e99a  test    r9, r9
0x18001e99d  jz      short loc_18001E9BF
0x18001e99f  mov     rax, [r9+60h]
0x18001e9a3  test    rax, rax
0x18001e9a6  js      loc_18001EB5F
0x18001e9ac  cmp     eax, 7FFFFFFFh
0x18001e9b1  jz      short loc_18001E9BF
0x18001e9b3  lea     rcx, [rax+1]
0x18001e9b7  lock cmpxchg [r9+60h], rcx
0x18001e9bd  jnz     short loc_18001E9A3
0x18001e9bf  mov     rcx, [r8+18h]; this
0x18001e9c3  mov     [r8+18h], r9
0x18001e9c7  test    rcx, rcx
0x18001e9ca  jz      short loc_18001E9D2
0x18001e9cc  call    ?Release@UnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@UEAAKXZ; WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::Release(void)
0x18001e9d1  nop
0x18001e9d2  test    rbx, rbx
0x18001e9d5  jnz     loc_18001ECBF
0x18001e9db  jmp     short loc_18001E9E6
0x18001e9dd  test    r12b, r12b
0x18001e9e0  jnz     loc_18001EB83
0x18001e9e6  mov     r9, [rsp+0C8h+var_A8]; char *
0x18001e9eb  test    r9, r9
0x18001e9ee  jnz     short loc_18001EA6F
0x18001e9f0  mov     rcx, [rsp+0C8h]; this
0x18001e9f8  test    r12b, r12b
0x18001e9fb  jnz     loc_18001EB71
0x18001ea01  mov     rcx, [rsp+0C8h+var_A0]
0x18001ea06  xor     r13d, r13d
0x18001ea09  test    rcx, rcx
0x18001ea0c  jz      short loc_18001EA20
0x18001ea0e  mov     [rsp+0C8h+var_A0], r13
0x18001ea13  mov     rax, [rcx]
0x18001ea16  mov     rax, [rax+10h]
0x18001ea1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea1f  nop
0x18001ea20  mov     rcx, [rsp+0C8h+var_A8]; this
0x18001ea25  test    rcx, rcx
0x18001ea28  jz      short loc_18001EA35
0x18001ea2a  mov     [rsp+0C8h+var_A8], r13
0x18001ea2f  call    ?Release@UnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@UEAAKXZ; WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::Release(void)
0x18001ea34  nop
0x18001ea35  mov     rcx, [rsp+0C8h+string]; string
0x18001ea3d  call    cs:__imp_WindowsDeleteString
0x18001ea43  mov     [rsp+0C8h+string], r13
0x18001ea4b  cmp     [rsp+0C8h+var_50], 0
0x18001ea50  jz      short loc_18001EA5D
0x18001ea52  lea     rcx, [rsp+0C8h+var_68]; this
0x18001ea57  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001ea5c  nop
0x18001ea5d  cmp     [rsp+0C8h+var_70], 0
0x18001ea62  jnz     loc_18001F06E
0x18001ea68  xor     eax, eax
0x18001ea6a  jmp     loc_18001E8DE
0x18001ea6f  mov     r8, r15
0x18001ea72  lea     rdx, _GUID_65b4e03e_a32e_40cf_8bab_b2d9c5287307
0x18001ea79  mov     rcx, r9
0x18001ea7c  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTile2@567@UIUnifiedTile3@567@UIUnifiedTilePrivate@Private@567@U?$CloakedIid@UINotificationStateChange@@@23@U?$CloakedIid@UITileNotificationCollection@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTile2@567@UIUnifiedTile3@567@UIUnifiedTilePrivate@Private@567@U?$CloakedIid@UINotificationStateChange@@@23@U?$CloakedIid@UITileNotificationCollection@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile2,WindowsInternal::Shell::UnifiedTile::IUnifiedTile3,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate,Microsoft::WRL::CloakedIid<INotificationStateChange>,Microsoft::WRL::CloakedIid<ITileNotificationCollection>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::IUnifiedTile,WindowsInternal::Shell::UnifiedTile::IUnifiedTile2,WindowsInternal::Shell::UnifiedTile::IUnifiedTile3,WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate,Microsoft::WRL::CloakedIid<INotificationStateChange>,Microsoft::WRL::CloakedIid<ITileNotificationCollection>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18001ea81  mov     ebx, eax
0x18001ea83  test    eax, eax
0x18001ea85  jns     loc_18001EA01
0x18001ea8b  mov     rcx, [rsp+0C8h]; this
  ... truncated ...
```
