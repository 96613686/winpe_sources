# FontCacheServer::FontCacheServer(IFontCacheServiceConfigurationInternal *)

- ea: `0x1800b1734`
- end: `0x1800b193f`
- name: `??0FontCacheServer@@QEAA@PEAUIFontCacheServiceConfigurationInternal@@@Z`
- size: `523`
- prototype: `FontCacheServer *__fastcall(FontCacheServer *__hidden this, struct IFontCacheServiceConfigurationInternal *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b05b8`

## callees

- `0x18000d55c`
- `0x180028c50`
- `0x180068da0`
- `0x1800a4ca0`
- `0x1800b1050`
- `0x1800b16fc`
- `0x1800b1734`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b17cf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b17e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b1805`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b1850`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b17cf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b17e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b1805`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800b1850`

## string_xrefs

- `0x1800b1884`: `SYSTEM\CurrentControlSet\Services\FontCache\Parameters`
- `0x1800b18ee`: `SYSTEM\CurrentControlSet\Services\FontCache\Parameters`
- `0x1800b18e3`: `MaxUserCacheAge`
- `0x1800b1876`: `MaxUserCacheCount`

## pseudocode

```c
FontCacheServer *__fastcall FontCacheServer::FontCacheServer(
        FontCacheServer *this,
        struct IFontCacheServiceConfigurationInternal *a2)
{
  unsigned int *v4; // rcx
  __int64 v5; // rax
  unsigned int FileCacheSizeCap; // eax
  struct DWrite::RefString::Data *v7; // rcx
  int v8; // eax
  int v9; // ecx
  FontCacheServer *result; // rax
  struct DWrite::RefString::Data *v11; // [rsp+30h] [rbp+8h] BYREF

  ComObjectBase<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::ComObjectBase<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>();
  v4 += 6;
  *v4 = _InterlockedIncrement((volatile signed __int32 *)&EventLogger::lastObjectId_);
  *((_QWORD *)this + 4) = 1919906915;
  EventLogger::LogEvent<EventTag>(v4, 0x7265767265536346LL, 0x6574617473LL, 1919906915);
  *(_QWORD *)this = &FontCacheServer::`vftable'{for `IFontCacheServer'};
  *((_QWORD *)this + 1) = &FontCacheServer::`vftable'{for `IFontCacheServerInternal'};
  *((_QWORD *)this + 5) = &FontCacheServer::`vftable'{for `LocalFileLoader::IDeferredCleanup'};
  *((_QWORD *)this + 6) = &FontCacheServer::`vftable'{for `IFontDownloadManagerCallbacks'};
  ComPtr<ServerSideFontFaceContext>::ComPtr<ServerSideFontFaceContext>((char *)this + 56, a2);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 16) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 5);
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  v5 = (*(__int64 (__fastcall **)(struct IFontCacheServiceConfigurationInternal *, struct DWrite::RefString::Data **))(*(_QWORD *)a2 + 120LL))(
         a2,
         &v11);
  FileCacheSizeCap = FontCacheServiceConfiguration::GetFileCacheSizeCap((LPCWSTR)(*(_QWORD *)v5 + 8LL));
  v7 = v11;
  *((_DWORD *)this + 64) = FileCacheSizeCap;
  DWrite::RefString::DecrementRef(v7);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 84) = 0;
  *((_BYTE *)this + 360) = 0;
  *((_QWORD *)this + 43) = (char *)this + 344;
  *((_QWORD *)this + 44) = (char *)this + 344;
  *((_BYTE *)this + 384) = 0;
  *((_QWORD *)this + 46) = (char *)this + 368;
  *((_QWORD *)this + 47) = (char *)this + 368;
  LODWORD(v11) = 0;
  RegistryKey::TryGetNumber(
    2147483650LL,
    L"SYSTEM\\CurrentControlSet\\Services\\FontCache\\Parameters",
    L"MaxUserCacheCount",
    &v11);
  v8 = (int)v11;
  if ( (_DWORD)v11 )
  {
    if ( (unsigned int)v11 > 0x100 )
      v8 = 256;
  }
  else
  {
    v8 = 16;
  }
  *((_DWORD *)this + 98) = v8;
  LODWORD(v11) = 0;
  RegistryKey::TryGetNumber(
    2147483650LL,
    L"SYSTEM\\CurrentControlSet\\Services\\FontCache\\Parameters",
    L"MaxUserCacheAge",
    &v11);
  v9 = 2592000;
  if ( (_DWORD)v11 )
    v9 = (int)v11;
  *((_DWORD *)this + 99) = v9;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = &FontCacheServer::ScheduleCloseCacheContextWorkCallbackImpl::`vftable';
  result = this;
  *((_QWORD *)this + 52) = this;
  return result;
}

```

## disassembly

```asm
0x1800b1734  mov     [rsp+arg_8], rbx
0x1800b1739  mov     [rsp+arg_10], rsi
0x1800b173e  push    rdi
0x1800b173f  sub     rsp, 20h
0x1800b1743  mov     rbx, rdx
0x1800b1746  mov     rdi, rcx
0x1800b1749  call    ??0?$ComObjectBase@V?$ComInterfaceList@VFontCacheServer@@UIFontCacheServer@@UIFontCacheServerInternal@@@@UIFontCacheServer@@UIFontCacheServerInternal@@@@QEAA@XZ; ComObjectBase<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::ComObjectBase<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>(void)
0x1800b174e  mov     eax, 1
0x1800b1753  lock xadd cs:?lastObjectId_@EventLogger@@0IA, eax; uint EventLogger::lastObjectId_
0x1800b175b  add     rcx, 18h
0x1800b175f  inc     eax
0x1800b1761  mov     r9d, 726F7463h
0x1800b1767  mov     rdx, 7265767265536346h
0x1800b1771  mov     r8, 6574617473h
0x1800b177b  mov     [rcx], eax
0x1800b177d  mov     [rdi+20h], r9
0x1800b1781  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x1800b1786  lea     rax, ??_7FontCacheServer@@6BIFontCacheServer@@@; const FontCacheServer::`vftable'{for `IFontCacheServer'}
0x1800b178d  mov     rdx, rbx
0x1800b1790  mov     [rdi], rax
0x1800b1793  lea     rcx, [rdi+38h]
0x1800b1797  lea     rax, ??_7FontCacheServer@@6BIFontCacheServerInternal@@@; const FontCacheServer::`vftable'{for `IFontCacheServerInternal'}
0x1800b179e  mov     [rdi+8], rax
0x1800b17a2  lea     rax, ??_7FontCacheServer@@6BIDeferredCleanup@LocalFileLoader@@@; const FontCacheServer::`vftable'{for `LocalFileLoader::IDeferredCleanup'}
0x1800b17a9  mov     [rdi+28h], rax
0x1800b17ad  lea     rax, ??_7FontCacheServer@@6BIFontDownloadManagerCallbacks@@@; const FontCacheServer::`vftable'{for `IFontDownloadManagerCallbacks'}
0x1800b17b4  mov     [rdi+30h], rax
0x1800b17b8  call    ??0?$ComPtr@VServerSideFontFaceContext@@@@QEAA@PEAVServerSideFontFaceContext@@@Z; ComPtr<ServerSideFontFaceContext>::ComPtr<ServerSideFontFaceContext>(ServerSideFontFaceContext *)
0x1800b17bd  xor     esi, esi
0x1800b17bf  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800b17c3  mov     [rdi+40h], rsi
0x1800b17c7  mov     [rdi+48h], rsi
0x1800b17cb  mov     [rdi+50h], rsi
0x1800b17cf  call    cs:__imp_InitializeCriticalSection
0x1800b17d5  lea     rcx, [rdi+88h]; lpCriticalSection
0x1800b17dc  mov     [rdi+80h], rsi
0x1800b17e3  call    cs:__imp_InitializeCriticalSection
0x1800b17e9  mov     [rdi+0B0h], sil
0x1800b17f0  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x1800b17f7  mov     [rdi+0B8h], rsi
0x1800b17fe  mov     [rdi+0C0h], rsi
0x1800b1805  call    cs:__imp_InitializeCriticalSection
0x1800b180b  mov     [rdi+0F0h], rsi
0x1800b1812  lea     rdx, [rsp+28h+arg_0]
0x1800b1817  mov     [rdi+0F8h], rsi
0x1800b181e  mov     rcx, rbx
0x1800b1821  mov     rax, [rbx]
0x1800b1824  mov     rax, [rax+78h]
0x1800b1828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b182d  mov     rcx, [rax]
0x1800b1830  add     rcx, 8; lpDirectoryName
0x1800b1834  call    ?GetFileCacheSizeCap@FontCacheServiceConfiguration@@SAIPEB_W@Z; FontCacheServiceConfiguration::GetFileCacheSizeCap(wchar_t const *)
0x1800b1839  mov     rcx, [rsp+28h+arg_0]; struct DWrite::RefString::Data *
0x1800b183e  mov     [rdi+100h], eax
0x1800b1844  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800b1849  lea     rcx, [rdi+108h]; lpCriticalSection
0x1800b1850  call    cs:__imp_InitializeCriticalSection
0x1800b1856  mov     [rdi+130h], rsi
0x1800b185d  lea     rax, [rdi+158h]
0x1800b1864  mov     [rdi+138h], esi
0x1800b186a  lea     r9, [rsp+28h+arg_0]
0x1800b186f  mov     [rdi+140h], rsi
0x1800b1876  lea     r8, aMaxusercacheco; "MaxUserCacheCount"
0x1800b187d  mov     [rdi+148h], rsi
0x1800b1884  lea     rdx, ?FontCacheServiceConfigurationKey@@3QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Fo"...
0x1800b188b  mov     [rdi+150h], esi
0x1800b1891  mov     ebx, 80000002h
0x1800b1896  mov     [rax+10h], sil
0x1800b189a  mov     ecx, ebx
0x1800b189c  mov     [rax], rax
0x1800b189f  mov     [rax+8], rax
0x1800b18a3  lea     rax, [rdi+170h]
0x1800b18aa  mov     [rax+10h], sil
0x1800b18ae  mov     [rax], rax
0x1800b18b1  mov     [rax+8], rax
0x1800b18b5  mov     dword ptr [rsp+28h+arg_0], esi
0x1800b18b9  call    ?TryGetNumber@RegistryKey@@SA_NW4RegistryHive@@PEB_W1PEAI@Z; RegistryKey::TryGetNumber(RegistryHive,wchar_t const *,wchar_t const *,uint *)
0x1800b18be  mov     eax, dword ptr [rsp+28h+arg_0]
0x1800b18c2  test    eax, eax
0x1800b18c4  jnz     short loc_1800B18CB
0x1800b18c6  lea     eax, [rsi+10h]
0x1800b18c9  jmp     short loc_1800B18D8
0x1800b18cb  mov     r8d, 100h
0x1800b18d1  cmp     eax, r8d
0x1800b18d4  cmova   eax, r8d
0x1800b18d8  lea     r9, [rsp+28h+arg_0]
0x1800b18dd  mov     [rdi+188h], eax
0x1800b18e3  lea     r8, aMaxusercacheag; "MaxUserCacheAge"
0x1800b18ea  mov     dword ptr [rsp+28h+arg_0], esi
0x1800b18ee  lea     rdx, ?FontCacheServiceConfigurationKey@@3QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Fo"...
0x1800b18f5  mov     ecx, ebx
0x1800b18f7  call    ?TryGetNumber@RegistryKey@@SA_NW4RegistryHive@@PEB_W1PEAI@Z; RegistryKey::TryGetNumber(RegistryHive,wchar_t const *,wchar_t const *,uint *)
0x1800b18fc  mov     eax, dword ptr [rsp+28h+arg_0]
0x1800b1900  mov     ecx, 278D00h
0x1800b1905  mov     rbx, [rsp+28h+arg_8]
0x1800b190a  test    eax, eax
0x1800b190c  cmovnz  ecx, eax
0x1800b190f  lea     rax, ??_7ScheduleCloseCacheContextWorkCallbackImpl@FontCacheServer@@6B@; const FontCacheServer::ScheduleCloseCacheContextWorkCallbackImpl::`vftable'
0x1800b1916  mov     [rdi+18Ch], ecx
0x1800b191c  mov     [rdi+190h], rsi
0x1800b1923  mov     rsi, [rsp+28h+arg_10]
0x1800b1928  mov     [rdi+198h], rax
0x1800b192f  mov     rax, rdi
0x1800b1932  mov     [rdi+1A0h], rdi
0x1800b1939  add     rsp, 20h
0x1800b193d  pop     rdi
0x1800b193e  retn
```
