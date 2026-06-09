# FontCacheServer::~FontCacheServer(void)

- ea: `0x1800a6b7c`
- end: `0x1800a6dca`
- name: `??1FontCacheServer@@UEAA@XZ`
- size: `590`
- prototype: `void __fastcall(FontCacheServer *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b1a20`

## callees

- `0x180028c50`
- `0x18004ff84`
- `0x18006c6d8`
- `0x18006c6f8`
- `0x18006c718`
- `0x180076ca4`
- `0x18009372c`
- `0x180096954`
- `0x18009b3b0`
- `0x18009b4f8`
- `0x1800a1960`
- `0x1800a422c`
- `0x1800a4544`
- `0x1800a45fc`
- `0x1800a6b7c`
- `0x1800a6dd0`
- `0x1800b1978`
- `0x1800b1d64`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6c0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6c82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6c0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a6c82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a6d86`

## string_xrefs

- `0x1800a6cf6`: `FontCache-Obsolete-*.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FontCacheServer::~FontCacheServer(FontCacheServer *this)
{
  __int64 *v2; // r15
  __int64 *v3; // rax
  bool v4; // dl
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  const struct DWrite::RefString *CacheFolderPath; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+8h] BYREF
  char v10; // [rsp+68h] [rbp+10h] BYREF

  *(_QWORD *)this = &FontCacheServer::`vftable'{for `IFontCacheServer'};
  *((_QWORD *)this + 1) = &FontCacheServer::`vftable'{for `IFontCacheServerInternal'};
  *((_QWORD *)this + 5) = &FontCacheServer::`vftable'{for `LocalFileLoader::IDeferredCleanup'};
  *((_QWORD *)this + 6) = &FontCacheServer::`vftable'{for `IFontDownloadManagerCallbacks'};
  v2 = (__int64 *)((char *)this + 80);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 40LL))(*((_QWORD *)this + 10));
  LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (FontCacheServer *)((char *)this + 136));
  *((_BYTE *)this + 176) = 1;
  v3 = (__int64 *)EventTag::EventTag((EventTag *)&v10, (const char (*)[9])"stopping");
  EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::LogEvent<>(
    (__int64)this,
    *v3);
  LeaveCriticalSection(lpCriticalSection);
  ThreadpoolWork::WaitForCompletion((FontCacheServer *)((char *)this + 192), 1);
  ThreadpoolWork::WaitForCompletion((FontCacheServer *)((char *)this + 240), 1);
  LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (struct Lock *)&g_localFileLoaderLock);
  if ( g_cleanupHandler )
  {
    LocalFileLoader::FreeList::CleanupAll((LocalFileLoader::FreeList *)&LocalFileLoader::g_freeList);
    (*(void (__fastcall **)(struct LocalFileLoader::IDeferredCleanup *, LPCRITICAL_SECTION *))(*(_QWORD *)g_cleanupHandler
                                                                                             + 16LL))(
      g_cleanupHandler,
      &lpCriticalSection);
    g_cleanupHandler = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( *((_QWORD *)this + 23) )
    ThreadpoolTimer::WaitForCompletion((FontCacheServer *)((char *)this + 184), v4);
  v5 = *((_QWORD *)this + 50);
  *((_QWORD *)this + 50) = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *v2;
  *v2 = 0;
  ComPtr<IFontSetCache>::Deref(v6);
  v7 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  CacheFolderPath = (const struct DWrite::RefString *)FontCacheServer::GetCacheFolderPath(
                                                        (__int64)this,
                                                        (__int64)&lpCriticalSection);
  FontCache::DeleteCacheFiles(CacheFolderPath, L"FontCache-Obsolete-*.dat", 0);
  DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)lpCriticalSection);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 400);
  ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>::~ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>((char *)this + 368);
  ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>::~ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>((char *)this + 344);
  HashTableImpl::~HashTableImpl((FontCacheServer *)((char *)this + 304));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  ComPtr<FileCleanup>::Deref((char *)this + 248);
  ThreadpoolWork::~ThreadpoolWork((FontCacheServer *)((char *)this + 240));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  ThreadpoolWork::~ThreadpoolWork((FontCacheServer *)((char *)this + 192));
  ThreadpoolTimer::~ThreadpoolTimer((FontCacheServer *)((char *)this + 184));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(v2);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 72);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 64);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 56);
  EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::~EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>(this);
}

```

## disassembly

```asm
0x1800a6b7c  mov     [rsp+arg_10], rbx
0x1800a6b81  push    rbp
0x1800a6b82  push    rsi
0x1800a6b83  push    rdi
0x1800a6b84  push    r12
0x1800a6b86  push    r13
0x1800a6b88  push    r14
0x1800a6b8a  push    r15
0x1800a6b8c  sub     rsp, 20h
0x1800a6b90  mov     rbx, rcx
0x1800a6b93  lea     rax, ??_7FontCacheServer@@6BIFontCacheServer@@@; const FontCacheServer::`vftable'{for `IFontCacheServer'}
0x1800a6b9a  mov     [rcx], rax
0x1800a6b9d  lea     rax, ??_7FontCacheServer@@6BIFontCacheServerInternal@@@; const FontCacheServer::`vftable'{for `IFontCacheServerInternal'}
0x1800a6ba4  mov     [rcx+8], rax
0x1800a6ba8  lea     rax, ??_7FontCacheServer@@6BIDeferredCleanup@LocalFileLoader@@@; const FontCacheServer::`vftable'{for `LocalFileLoader::IDeferredCleanup'}
0x1800a6baf  mov     [rcx+28h], rax
0x1800a6bb3  lea     rax, ??_7FontCacheServer@@6BIFontDownloadManagerCallbacks@@@; const FontCacheServer::`vftable'{for `IFontDownloadManagerCallbacks'}
0x1800a6bba  mov     [rcx+30h], rax
0x1800a6bbe  lea     r15, [rcx+50h]
0x1800a6bc2  mov     rcx, [r15]
0x1800a6bc5  mov     rax, [rcx]
0x1800a6bc8  mov     rax, [rax+28h]
0x1800a6bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6bd1  lea     rbp, [rbx+88h]
0x1800a6bd8  mov     rdx, rbp; struct Lock *
0x1800a6bdb  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x1800a6be0  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800a6be5  mov     byte ptr [rbx+0B0h], 1
0x1800a6bec  lea     rdx, aStopping; "stopping"
0x1800a6bf3  lea     rcx, [rsp+58h+arg_8]; this
0x1800a6bf8  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x1800a6bfd  mov     rdx, [rax]
0x1800a6c00  mov     rcx, rbx
0x1800a6c03  call    ??$LogEvent@$$V@?$EventSource@V?$ComInterfaceList@VFontCacheServer@@UIFontCacheServer@@UIFontCacheServerInternal@@@@UIFontCacheServer@@UIFontCacheServerInternal@@@@QEBAXVEventTag@@@Z; EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::LogEvent<>(EventTag)
0x1800a6c08  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800a6c0d  call    cs:__imp_LeaveCriticalSection
0x1800a6c13  lea     r12, [rbx+0C0h]
0x1800a6c1a  mov     dl, 1; bool
0x1800a6c1c  mov     rcx, r12; this
0x1800a6c1f  call    ?WaitForCompletion@ThreadpoolWork@@QEAAX_N@Z; ThreadpoolWork::WaitForCompletion(bool)
0x1800a6c24  lea     r13, [rbx+0F0h]
0x1800a6c2b  mov     dl, 1; bool
0x1800a6c2d  mov     rcx, r13; this
0x1800a6c30  call    ?WaitForCompletion@ThreadpoolWork@@QEAAX_N@Z; ThreadpoolWork::WaitForCompletion(bool)
0x1800a6c35  lea     rdx, ?g_localFileLoaderLock@@3VLock@@A; struct Lock *
0x1800a6c3c  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x1800a6c41  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800a6c46  xor     r14d, r14d
0x1800a6c49  cmp     cs:?g_cleanupHandler@@3PEAVIDeferredCleanup@LocalFileLoader@@EA, r14; LocalFileLoader::IDeferredCleanup * g_cleanupHandler
0x1800a6c50  jz      short loc_1800A6C7D
0x1800a6c52  lea     rcx, ?g_freeList@LocalFileLoader@@0VFreeList@1@A; this
0x1800a6c59  call    ?CleanupAll@FreeList@LocalFileLoader@@QEAAXXZ; LocalFileLoader::FreeList::CleanupAll(void)
0x1800a6c5e  mov     rcx, cs:?g_cleanupHandler@@3PEAVIDeferredCleanup@LocalFileLoader@@EA; LocalFileLoader::IDeferredCleanup * g_cleanupHandler
0x1800a6c65  mov     rax, [rcx]
0x1800a6c68  lea     rdx, [rsp+58h+lpCriticalSection]
0x1800a6c6d  mov     rax, [rax+10h]
0x1800a6c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c76  mov     cs:?g_cleanupHandler@@3PEAVIDeferredCleanup@LocalFileLoader@@EA, r14; LocalFileLoader::IDeferredCleanup * g_cleanupHandler
0x1800a6c7d  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800a6c82  call    cs:__imp_LeaveCriticalSection
0x1800a6c88  lea     rdi, [rbx+0B8h]
0x1800a6c8f  cmp     [rdi], r14
0x1800a6c92  jz      short loc_1800A6C9C
0x1800a6c94  mov     rcx, rdi; this
0x1800a6c97  call    ?WaitForCompletion@ThreadpoolTimer@@QEAAX_N@Z; ThreadpoolTimer::WaitForCompletion(bool)
0x1800a6c9c  lea     rsi, [rbx+190h]
0x1800a6ca3  mov     rcx, [rsi]
0x1800a6ca6  mov     [rsi], r14
0x1800a6ca9  test    rcx, rcx
0x1800a6cac  jz      short loc_1800A6CBB
0x1800a6cae  mov     rax, [rcx]
0x1800a6cb1  mov     rax, [rax+10h]
0x1800a6cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6cba  nop
0x1800a6cbb  mov     rcx, [r15]
0x1800a6cbe  mov     [r15], r14
0x1800a6cc1  call    ?Deref@?$ComPtr@UIFontSetCache@@@@CAXPEAUIFontSetCache@@@Z; ComPtr<IFontSetCache>::Deref(IFontSetCache *)
0x1800a6cc6  lea     r14, [rbx+48h]
0x1800a6cca  mov     rcx, [r14]
0x1800a6ccd  mov     qword ptr [r14], 0
0x1800a6cd4  test    rcx, rcx
0x1800a6cd7  jz      short loc_1800A6CE6
0x1800a6cd9  mov     rax, [rcx]
0x1800a6cdc  mov     rax, [rax+10h]
0x1800a6ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ce5  nop
0x1800a6ce6  lea     rdx, [rsp+58h+lpCriticalSection]
0x1800a6ceb  mov     rcx, rbx
0x1800a6cee  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x1800a6cf3  xor     r8d, r8d; bool
0x1800a6cf6  lea     rdx, aFontcacheObsol_0; "FontCache-Obsolete-*.dat"
0x1800a6cfd  mov     rcx, rax; struct DWrite::RefString *
0x1800a6d00  call    ?DeleteCacheFiles@FontCache@@SAXAEBVRefString@DWrite@@PEB_W_N@Z; FontCache::DeleteCacheFiles(DWrite::RefString const &,wchar_t const *,bool)
0x1800a6d05  mov     rcx, [rsp+58h+lpCriticalSection]; struct DWrite::RefString::Data *
0x1800a6d0a  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a6d0f  mov     rcx, rsi
0x1800a6d12  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a6d17  lea     rcx, [rbx+170h]
0x1800a6d1e  call    ??1?$ListContainer@VUserCacheList@FontCacheServer@@UUserCacheReference@2@V?$UniqueOwnershipPolicy@UUserCacheReference@FontCacheServer@@@@@@QEAA@XZ; ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>::~ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>(void)
0x1800a6d23  lea     rcx, [rbx+158h]
0x1800a6d2a  call    ??1?$ListContainer@VUserCacheList@FontCacheServer@@UUserCacheReference@2@V?$UniqueOwnershipPolicy@UUserCacheReference@FontCacheServer@@@@@@QEAA@XZ; ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>::~ListContainer<FontCacheServer::UserCacheList,FontCacheServer::UserCacheReference,UniqueOwnershipPolicy<FontCacheServer::UserCacheReference>>(void)
0x1800a6d2f  lea     rcx, [rbx+130h]; this
0x1800a6d36  call    ??1HashTableImpl@@QEAA@XZ; HashTableImpl::~HashTableImpl(void)
0x1800a6d3b  lea     rcx, [rbx+108h]; lpCriticalSection
0x1800a6d42  call    cs:__imp_DeleteCriticalSection
0x1800a6d48  lea     rcx, [rbx+0F8h]
0x1800a6d4f  call    ?Deref@?$ComPtr@VFileCleanup@@@@AEAAXXZ; ComPtr<FileCleanup>::Deref(void)
0x1800a6d54  mov     rcx, r13; this
0x1800a6d57  call    ??1ThreadpoolWork@@QEAA@XZ; ThreadpoolWork::~ThreadpoolWork(void)
0x1800a6d5c  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800a6d63  call    cs:__imp_DeleteCriticalSection
0x1800a6d69  mov     rcx, r12; this
0x1800a6d6c  call    ??1ThreadpoolWork@@QEAA@XZ; ThreadpoolWork::~ThreadpoolWork(void)
0x1800a6d71  mov     rcx, rdi; this
0x1800a6d74  call    ??1ThreadpoolTimer@@QEAA@XZ; ThreadpoolTimer::~ThreadpoolTimer(void)
0x1800a6d79  mov     rcx, rbp; lpCriticalSection
0x1800a6d7c  call    cs:__imp_DeleteCriticalSection
0x1800a6d82  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800a6d86  call    cs:__imp_DeleteCriticalSection
0x1800a6d8c  mov     rcx, r15
0x1800a6d8f  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a6d94  mov     rcx, r14
0x1800a6d97  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a6d9c  lea     rcx, [rbx+40h]
0x1800a6da0  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a6da5  lea     rcx, [rbx+38h]
0x1800a6da9  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a6dae  mov     rcx, rbx
0x1800a6db1  mov     rbx, [rsp+58h+arg_10]
0x1800a6db6  add     rsp, 20h
0x1800a6dba  pop     r15
0x1800a6dbc  pop     r14
0x1800a6dbe  pop     r13
0x1800a6dc0  pop     r12
0x1800a6dc2  pop     rdi
0x1800a6dc3  pop     rsi
0x1800a6dc4  pop     rbp
0x1800a6dc5  jmp     ??1?$EventSource@V?$ComInterfaceList@VFontCacheServer@@UIFontCacheServer@@UIFontCacheServerInternal@@@@UIFontCacheServer@@UIFontCacheServerInternal@@@@UEAA@XZ; EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::~EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>(void)
```
