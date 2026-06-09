# FontCacheServer::Start(void)

- ea: `0x1800a7190`
- end: `0x1800a74f8`
- name: `?Start@FontCacheServer@@UEAAJXZ`
- size: `872`
- prototype: `__int64 __fastcall(struct IFontDownloadManager **this)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180010ca0`
- `0x180028c50`
- `0x18004ff84`
- `0x180069a20`
- `0x180076ca4`
- `0x180089268`
- `0x18008bfc0`
- `0x180096954`
- `0x18009a364`
- `0x18009b3b0`
- `0x1800a1960`
- `0x1800a4ca0`
- `0x1800a7190`
- `0x1800a781c`
- `0x1800a8148`
- `0x1800aaa58`
- `0x1800b09dc`
- `0x1800b0e3c`
- `0x1800b1948`
- `0x1800b2020`
- `0x1800b24c0`
- `0x1800b58cc`
- `0x1800b8f78`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a71d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a71d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7419`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7419`

## string_xrefs

- `0x1800a7201`: `~FontCache-*.dat`
- `0x1800a74ae`: `~FontCache-*.dat`
- `0x1800a7497`: `FontCache-*.dat`
- `0x1800a72b5`: `FontFaceCacheSize`
- `0x1800a734d`: `FontCache-System.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall FontCacheServer::Start(struct IFontDownloadManager **this)
{
  FontCacheServer *v2; // rsi
  ServerSideRemoteFileLoader *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rax
  void *v5; // r15
  struct IDWriteFontFileLoader *v6; // rbx
  ServerSideFontFaceContext *v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  __int64 SystemFontFileEnumerator; // rbx
  int v10; // eax
  FontCacheServer *FontSetCache; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  struct IFontDownloadManager *v15; // rdx
  _QWORD *v16; // rax
  struct DWrite::RefString::Data *v17; // rcx
  struct IExceptionHandler *v18; // rcx
  _BYTE v20[8]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v21[8]; // [rsp+48h] [rbp-40h] BYREF
  struct DWrite::RefString::Data *v22; // [rsp+90h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+98h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp+18h] BYREF
  char v25; // [rsp+A8h] [rbp+20h] BYREF

  v2 = (FontCacheServer *)(this - 1);
  LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (struct Lock *)&g_localFileLoaderLock);
  g_cleanupHandler = (struct LocalFileLoader::IDeferredCleanup *)((unsigned __int64)(this + 4) & -(__int64)(v2 != 0));
  LeaveCriticalSection(lpCriticalSection);
  FontCacheServer::GetCacheFolderPath((__int64)v2, (__int64)&v22);
  FontCacheServer::SetStorageReserve(v2, (const struct DWrite::RefString *)&v22);
  try
  {
    FontCache::DeleteCacheFiles((const struct DWrite::RefString *)&v22, L"~FontCache-*.dat", 1);
    if ( !FontCacheServiceConfiguration::AreFontProvidersDisabled() )
      FontCacheServer::InitializeDownloadManager(v2);
    v3 = (ServerSideRemoteFileLoader *)operator new(0x20u);
    ServerSideRemoteFileLoader::ServerSideRemoteFileLoader(v3, this[49]);
    *(_QWORD *)v3 = &ComObject<ServerSideRemoteFileLoader,DeleteOnZeroReference>::`vftable'{for `IDWriteFontFileLoader'};
    *((_QWORD *)v3 + 1) = &ComObject<ServerSideRemoteFileLoader,DeleteOnZeroReference>::`vftable'{for `IDWriteFontFileLoaderInternal'};
    *((_DWORD *)v3 + 6) = 0;
    lpCriticalSection = (LPCRITICAL_SECTION)v3;
    ComPtr<FileCleanup>::AddRef(&lpCriticalSection);
    v4 = (struct _RTL_CRITICAL_SECTION *)this[7];
    this[7] = v3;
    lpCriticalSection = v4;
    ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&lpCriticalSection);
    v5 = operator new(0x228u);
    hObject = v5;
    v6 = this[7];
    lpCriticalSection = (LPCRITICAL_SECTION)(GetCacheSize(L"FontFaceCacheSize", 0x1000000u, &g_fontFaceCacheSize)
                                           | 0x55F000000000LL);
    v7 = ServerSideFontFaceContext::ServerSideFontFaceContext(
           (ServerSideFontFaceContext *)v5,
           (volatile signed __int32 **)&v22,
           (const struct CacheGrowthPolicy *)&lpCriticalSection,
           v6);
    ComPtr<ServerSideFontFaceContext>::ComPtr<ServerSideFontFaceContext>(&lpCriticalSection, v7);
    v8 = (struct _RTL_CRITICAL_SECTION *)this[8];
    this[8] = (struct IFontDownloadManager *)lpCriticalSection;
    lpCriticalSection = v8;
    ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&lpCriticalSection);
    hObject = 0;
    SystemFontFileEnumerator = CreateSystemFontFileEnumerator(v20);
    v21[0] = L"FontCache-System.dat";
    v21[1] = 20;
    DWrite::RefString::RefString(&lpCriticalSection, v21);
    v10 = (*(__int64 (__fastcall **)(struct IFontDownloadManager *))(*(_QWORD *)this[8] + 40LL))(this[8]);
    FontSetCache = (FontCacheServer *)ServerFactory::CreateFontSetCache(
                                        (unsigned int)&v25,
                                        0,
                                        (unsigned int)this[8],
                                        v10,
                                        (__int64)&v22,
                                        (__int64)&lpCriticalSection,
                                        SystemFontFileEnumerator,
                                        (__int64)&hObject);
    v12 = this + 9;
    if ( this + 9 != (struct IFontDownloadManager **)FontSetCache )
    {
      v13 = *v12;
      v14 = *(_QWORD *)FontSetCache;
      *(_QWORD *)FontSetCache = 0;
      *v12 = v14;
      ComPtr<IFontSetCache>::Deref(v13);
    }
    ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&v25);
    DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)lpCriticalSection);
    ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(v20);
    if ( hObject )
      CloseHandle(hObject);
    v15 = this[49];
    if ( v15 )
      (*(void (__fastcall **)(_QWORD, struct IFontDownloadManager *, struct IFontDownloadManager *, GUID *))(*(_QWORD *)*v12 + 24LL))(
        *v12,
        v15,
        this[7],
        &g_systemFontProviderGuid);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 32LL))(*v12);
    FontCacheServer::InitializeUserCacheReferences(v2);
    v16 = (_QWORD *)DateTime::Now(&lpCriticalSection);
    FontCacheServer::Notify(v2, 0, *v16);
    GetLegacyFontCacheDirectory(&lpCriticalSection);
    v17 = (struct DWrite::RefString::Data *)lpCriticalSection;
    if ( HIDWORD(lpCriticalSection->DebugInfo) )
    {
      FontCache::DeleteCacheFiles((const struct DWrite::RefString *)&lpCriticalSection, L"FontCache-*.dat", 0);
      FontCache::DeleteCacheFiles((const struct DWrite::RefString *)&lpCriticalSection, L"~FontCache-*.dat", 0);
      v17 = (struct DWrite::RefString::Data *)lpCriticalSection;
    }
    DWrite::RefString::DecrementRef(v17);
    DWrite::RefString::DecrementRef(v22);
  }
  catch ( ... )
  {
    MapExceptionToHresult(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a7190  mov     rax, rsp
0x1800a7193  push    rbx
0x1800a7194  push    rsi
0x1800a7195  push    rdi
0x1800a7196  push    r14
0x1800a7198  push    r15
0x1800a719a  sub     rsp, 60h
0x1800a719e  mov     rdi, rcx
0x1800a71a1  xor     r14d, r14d
0x1800a71a4  lea     rsi, [rcx-8]
0x1800a71a8  lea     rdx, ?g_localFileLoaderLock@@3VLock@@A; struct Lock *
0x1800a71af  lea     rcx, [rax+10h]; this
0x1800a71b3  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800a71b8  mov     rax, rsi
0x1800a71bb  lea     rdx, [rdi+20h]
0x1800a71bf  neg     rax
0x1800a71c2  sbb     rcx, rcx
0x1800a71c5  and     rcx, rdx
0x1800a71c8  mov     cs:?g_cleanupHandler@@3PEAVIDeferredCleanup@LocalFileLoader@@EA, rcx; LocalFileLoader::IDeferredCleanup * g_cleanupHandler
0x1800a71cf  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x1800a71d7  call    cs:__imp_LeaveCriticalSection
0x1800a71dd  lea     rdx, [rsp+88h+arg_0]
0x1800a71e5  mov     rcx, rsi
0x1800a71e8  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x1800a71ed  nop
0x1800a71ee  lea     rdx, [rsp+88h+arg_0]; struct DWrite::RefString *
0x1800a71f6  mov     rcx, rsi; this
0x1800a71f9  call    ?SetStorageReserve@FontCacheServer@@AEAAXAEBVRefString@DWrite@@@Z; FontCacheServer::SetStorageReserve(DWrite::RefString const &)
0x1800a71fe  mov     r8b, 1; bool
0x1800a7201  lea     rdx, aFontcacheDat_0; "~FontCache-*.dat"
0x1800a7208  lea     rcx, [rsp+88h+arg_0]; struct DWrite::RefString *
0x1800a7210  call    ?DeleteCacheFiles@FontCache@@SAXAEBVRefString@DWrite@@PEB_W_N@Z; FontCache::DeleteCacheFiles(DWrite::RefString const &,wchar_t const *,bool)
0x1800a7215  call    ?AreFontProvidersDisabled@FontCacheServiceConfiguration@@SA_NXZ; FontCacheServiceConfiguration::AreFontProvidersDisabled(void)
0x1800a721a  test    al, al
0x1800a721c  jnz     short loc_1800A7226
0x1800a721e  mov     rcx, rsi; this
0x1800a7221  call    ?InitializeDownloadManager@FontCacheServer@@AEAAXXZ; FontCacheServer::InitializeDownloadManager(void)
0x1800a7226  mov     ecx, 20h ; ' '; Size
0x1800a722b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a7230  mov     rbx, rax
0x1800a7233  mov     rdx, [rdi+188h]; struct IFontDownloadManager *
0x1800a723a  mov     rcx, rax; this
0x1800a723d  call    ??0ServerSideRemoteFileLoader@@QEAA@PEAUIFontDownloadManager@@@Z; ServerSideRemoteFileLoader::ServerSideRemoteFileLoader(IFontDownloadManager *)
0x1800a7242  lea     rcx, ??_7?$ComObject@VServerSideRemoteFileLoader@@UDeleteOnZeroReference@@@@6BIDWriteFontFileLoader@@@; const ComObject<ServerSideRemoteFileLoader,DeleteOnZeroReference>::`vftable'{for `IDWriteFontFileLoader'}
0x1800a7249  mov     [rbx], rcx
0x1800a724c  lea     rax, ??_7?$ComObject@VServerSideRemoteFileLoader@@UDeleteOnZeroReference@@@@6BIDWriteFontFileLoaderInternal@@@; const ComObject<ServerSideRemoteFileLoader,DeleteOnZeroReference>::`vftable'{for `IDWriteFontFileLoaderInternal'}
0x1800a7253  mov     [rbx+8], rax
0x1800a7257  mov     dword ptr [rbx+18h], 0
0x1800a725e  mov     [rsp+88h+lpCriticalSection], rbx
0x1800a7266  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a726e  call    ?AddRef@?$ComPtr@VFileCleanup@@@@AEBAXXZ; ComPtr<FileCleanup>::AddRef(void)
0x1800a7273  mov     rax, [rdi+38h]
0x1800a7277  mov     [rdi+38h], rbx
0x1800a727b  mov     [rsp+88h+lpCriticalSection], rax
0x1800a7283  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a728b  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a7290  mov     ecx, 228h; Size
0x1800a7295  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a729a  mov     r15, rax
0x1800a729d  mov     [rsp+88h+hObject], rax
0x1800a72a5  mov     rbx, [rdi+38h]
0x1800a72a9  lea     r8, ?g_fontFaceCacheSize@@3IA; unsigned int *
0x1800a72b0  mov     edx, 1000000h; unsigned int
0x1800a72b5  lea     rcx, ?FontCacheServiceFontFaceCacheSizeValue@@3QB_WB; "FontFaceCacheSize"
0x1800a72bc  call    ?GetCacheSize@@YAIPEB_WIAEAI@Z; GetCacheSize(wchar_t const *,uint,uint &)
0x1800a72c1  mov     dword ptr [rsp+88h+lpCriticalSection], eax
0x1800a72c8  mov     dword ptr [rsp+88h+lpCriticalSection+4], 55F0h
0x1800a72d3  mov     rcx, [rsp+88h+lpCriticalSection]
0x1800a72db  mov     [rsp+88h+lpCriticalSection], rcx
0x1800a72e3  mov     r9, rbx; struct IDWriteFontFileLoader *
0x1800a72e6  lea     r8, [rsp+88h+lpCriticalSection]; struct CacheGrowthPolicy *
0x1800a72ee  lea     rdx, [rsp+88h+arg_0]; struct DWrite::RefString *
0x1800a72f6  mov     rcx, r15; this
0x1800a72f9  call    ??0ServerSideFontFaceContext@@QEAA@AEBVRefString@DWrite@@AEBUCacheGrowthPolicy@@PEAUIDWriteFontFileLoader@@@Z; ServerSideFontFaceContext::ServerSideFontFaceContext(DWrite::RefString const &,CacheGrowthPolicy const &,IDWriteFontFileLoader *)
0x1800a72fe  nop
0x1800a72ff  mov     rdx, rax
0x1800a7302  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a730a  call    ??0?$ComPtr@VServerSideFontFaceContext@@@@QEAA@PEAVServerSideFontFaceContext@@@Z; ComPtr<ServerSideFontFaceContext>::ComPtr<ServerSideFontFaceContext>(ServerSideFontFaceContext *)
0x1800a730f  mov     rcx, [rdi+40h]
0x1800a7313  mov     rax, [rsp+88h+lpCriticalSection]
0x1800a731b  mov     [rdi+40h], rax
0x1800a731f  mov     [rsp+88h+lpCriticalSection], rcx
0x1800a7327  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a732f  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a7334  mov     [rsp+88h+hObject], 0
0x1800a7340  lea     rcx, [rsp+88h+var_48]
0x1800a7345  call    ?CreateSystemFontFileEnumerator@@YA?AV?$ComPtr@UIInstalledFontFileEnumerator@@@@XZ; CreateSystemFontFileEnumerator(void)
0x1800a734a  mov     rbx, rax
0x1800a734d  lea     rax, aFontcacheSyste; "FontCache-System.dat"
0x1800a7354  mov     [rsp+88h+var_40], rax
0x1800a7359  mov     [rsp+88h+var_38], 14h
0x1800a7362  lea     rdx, [rsp+88h+var_40]
0x1800a7367  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a736f  call    ??$?0PEB_W@RefString@DWrite@@QEAA@AEBV?$StringExpr@PEB_W@@@Z; DWrite::RefString::RefString(StringExpr<wchar_t const *> const &)
0x1800a7374  nop
0x1800a7375  mov     rcx, [rdi+40h]
0x1800a7379  mov     rax, [rcx]
0x1800a737c  mov     rax, [rax+28h]
0x1800a7380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7385  lea     rcx, [rsp+88h+hObject]
0x1800a738d  mov     [rsp+88h+var_50], rcx
0x1800a7392  mov     [rsp+88h+var_58], rbx
0x1800a7397  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a739f  mov     [rsp+88h+var_60], rcx
0x1800a73a4  lea     rcx, [rsp+88h+arg_0]
0x1800a73ac  mov     [rsp+88h+var_68], rcx
0x1800a73b1  mov     r9, rax
0x1800a73b4  mov     r8, [rdi+40h]
0x1800a73b8  xor     edx, edx
0x1800a73ba  lea     rcx, [rsp+88h+arg_18]
0x1800a73c2  call    ?CreateFontSetCache@ServerFactory@@SA?AV?$ComPtr@UIFontSetCache@@@@W4FontSetCacheType@@PEAUIBaseCacheContext@@AEBVFontFileLoaderManager@@AEBVRefString@DWrite@@3$$QEAV?$ComPtr@UIInstalledFontFileEnumerator@@@@$$QEAVWin32Handle@@@Z; ServerFactory::CreateFontSetCache(FontSetCacheType,IBaseCacheContext *,FontFileLoaderManager const &,DWrite::RefString const &,DWrite::RefString const &,ComPtr<IInstalledFontFileEnumerator> &&,Win32Handle &&)
0x1800a73c7  lea     rbx, [rdi+48h]
0x1800a73cb  cmp     rbx, rax
0x1800a73ce  jz      short loc_1800A73E5
0x1800a73d0  mov     rcx, [rbx]
0x1800a73d3  mov     rdx, [rax]
0x1800a73d6  mov     qword ptr [rax], 0
0x1800a73dd  mov     [rbx], rdx
0x1800a73e0  call    ?Deref@?$ComPtr@UIFontSetCache@@@@CAXPEAUIFontSetCache@@@Z; ComPtr<IFontSetCache>::Deref(IFontSetCache *)
0x1800a73e5  lea     rcx, [rsp+88h+arg_18]
0x1800a73ed  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a73f2  nop
0x1800a73f3  mov     rcx, [rsp+88h+lpCriticalSection]; struct DWrite::RefString::Data *
0x1800a73fb  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a7400  nop
0x1800a7401  lea     rcx, [rsp+88h+var_48]
0x1800a7406  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800a740b  nop
0x1800a740c  mov     rcx, [rsp+88h+hObject]; hObject
0x1800a7414  test    rcx, rcx
0x1800a7417  jz      short loc_1800A741F
0x1800a7419  call    cs:__imp_CloseHandle
0x1800a741f  mov     rdx, [rdi+188h]
0x1800a7426  test    rdx, rdx
0x1800a7429  jz      short loc_1800A7445
0x1800a742b  mov     rcx, [rbx]
0x1800a742e  mov     rax, [rcx]
0x1800a7431  lea     r9, ?g_systemFontProviderGuid@@3U_GUID@@B; _GUID const g_systemFontProviderGuid
0x1800a7438  mov     r8, [rdi+38h]
0x1800a743c  mov     rax, [rax+18h]
0x1800a7440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7445  mov     rcx, [rbx]
0x1800a7448  mov     rax, [rcx]
0x1800a744b  mov     rax, [rax+20h]
0x1800a744f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7454  mov     rcx, rsi; this
0x1800a7457  call    ?InitializeUserCacheReferences@FontCacheServer@@AEAAXXZ; FontCacheServer::InitializeUserCacheReferences(void)
0x1800a745c  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a7464  call    ?Now@DateTime@@SA?AV1@XZ; DateTime::Now(void)
0x1800a7469  mov     r8, [rax]
0x1800a746c  xor     edx, edx
0x1800a746e  mov     rcx, rsi
0x1800a7471  call    ?Notify@FontCacheServer@@QEAAXPEAUIDWriteClientConnection@@VDateTime@@@Z; FontCacheServer::Notify(IDWriteClientConnection *,DateTime)
0x1800a7476  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800a747e  call    ?GetLegacyFontCacheDirectory@@YA?AVRefString@DWrite@@XZ; GetLegacyFontCacheDirectory(void)
0x1800a7483  nop
0x1800a7484  mov     rcx, [rsp+88h+lpCriticalSection]
0x1800a748c  cmp     dword ptr [rcx+4], 0
0x1800a7490  jnz     short loc_1800A7494
0x1800a7492  jmp     short loc_1800A74CB
0x1800a7494  xor     r8d, r8d; bool
0x1800a7497  lea     rdx, aFontcacheDat; "FontCache-*.dat"
0x1800a749e  lea     rcx, [rsp+88h+lpCriticalSection]; struct DWrite::RefString *
0x1800a74a6  call    ?DeleteCacheFiles@FontCache@@SAXAEBVRefString@DWrite@@PEB_W_N@Z; FontCache::DeleteCacheFiles(DWrite::RefString const &,wchar_t const *,bool)
0x1800a74ab  xor     r8d, r8d; bool
0x1800a74ae  lea     rdx, aFontcacheDat_0; "~FontCache-*.dat"
0x1800a74b5  lea     rcx, [rsp+88h+lpCriticalSection]; struct DWrite::RefString *
0x1800a74bd  call    ?DeleteCacheFiles@FontCache@@SAXAEBVRefString@DWrite@@PEB_W_N@Z; FontCache::DeleteCacheFiles(DWrite::RefString const &,wchar_t const *,bool)
0x1800a74c2  nop
0x1800a74c3  mov     rcx, [rsp+88h+lpCriticalSection]; struct DWrite::RefString::Data *
0x1800a74cb  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a74d0  nop
0x1800a74d1  mov     rcx, [rsp+88h+arg_0]; struct DWrite::RefString::Data *
0x1800a74d9  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a74de  nop
0x1800a74df  jmp     short loc_1800A74E9
0x1800a74e1  mov     r14d, dword ptr [rsp+88h+arg_0]
0x1800a74e9  mov     eax, r14d
0x1800a74ec  add     rsp, 60h
0x1800a74f0  pop     r15
0x1800a74f2  pop     r14
0x1800a74f4  pop     rdi
0x1800a74f5  pop     rsi
0x1800a74f6  pop     rbx
0x1800a74f7  retn
```
