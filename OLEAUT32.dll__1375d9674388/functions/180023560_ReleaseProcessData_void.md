# ReleaseProcessData(void)

- ea: `0x180023560`
- end: `0x18002362c`
- name: `?ReleaseProcessData@@YAXXZ`
- size: `204`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18007a2bc`

## callees

- `0x180022838`
- `0x180023560`
- `0x18002394c`
- `0x180023f54`
- `0x18009a618`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800235ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800235ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023619`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023619`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800235fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800235fb`

## pseudocode

```c
void ReleaseProcessData(void)
{
  InitDateInfo(0);
  InitNumInfo(0);
  OaDeleteCriticalSection(&CVtableSizeCache::critsec);
  CVtableSizeCache::pCache = 0;
  CVtableSizeCache::cSize = 0;
  CVtableSizeCache::cPopulationLimit = 0;
  CVtableSizeCache::cPopulation = 0;
  TlsFree(g_itlsAppData);
  if ( g_hinstMPRDLL && !g_bProcessShutdown )
  {
    FreeLibrary(g_hinstMPRDLL);
    g_hinstMPRDLL = 0;
  }
  OaDeleteCriticalSection(&g_OletmgrCriticalSection);
  OaDeleteCriticalSection(&g_OldFormatCriticalSection);
  if ( memcmp_0(&Buf1, `IsCriticalSectionZeroed'::`2'::z, 0x28u) )
    DeleteCriticalSection(&Buf1);
  g_bPerUserNlsCache = 0;
}

```

## disassembly

```asm
0x180023560  sub     rsp, 28h
0x180023564  xor     ecx, ecx; int
0x180023566  call    ?InitDateInfo@@YAJH@Z; InitDateInfo(int)
0x18002356b  xor     ecx, ecx; int
0x18002356d  call    ?InitNumInfo@@YAJH@Z; InitNumInfo(int)
0x180023572  lea     rcx, ?critsec@CVtableSizeCache@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023579  call    OaDeleteCriticalSection
0x18002357e  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180023584  mov     cs:?pCache@CVtableSizeCache@@0PEAUVtableSize@1@EA, 0; CVtableSizeCache::VtableSize * CVtableSizeCache::pCache
0x18002358f  mov     cs:?cSize@CVtableSizeCache@@0KA, 0; ulong CVtableSizeCache::cSize
0x180023599  mov     cs:?cPopulationLimit@CVtableSizeCache@@0KA, 0; ulong CVtableSizeCache::cPopulationLimit
0x1800235a3  mov     cs:?cPopulation@CVtableSizeCache@@0KA, 0; ulong CVtableSizeCache::cPopulation
0x1800235ad  call    cs:__imp_TlsFree
0x1800235b3  mov     rcx, cs:g_hinstMPRDLL; hLibModule
0x1800235ba  test    rcx, rcx
0x1800235bd  jnz     short loc_180023610
0x1800235bf  lea     rcx, ?g_OletmgrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800235c6  call    OaDeleteCriticalSection
0x1800235cb  lea     rcx, ?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800235d2  call    OaDeleteCriticalSection
0x1800235d7  mov     r8d, 28h ; '('; Size
0x1800235dd  lea     rdx, ?z@?1??IsCriticalSectionZeroed@@YAHPEAU_RTL_CRITICAL_SECTION@@@Z@4U2@A; Buf2
0x1800235e4  lea     rcx, Buf1; Buf1
0x1800235eb  call    memcmp_0
0x1800235f0  test    eax, eax
0x1800235f2  jz      short loc_180023601
0x1800235f4  lea     rcx, Buf1; lpCriticalSection
0x1800235fb  call    cs:__imp_DeleteCriticalSection
0x180023601  mov     cs:?g_bPerUserNlsCache@@3KA, 0; ulong g_bPerUserNlsCache
0x18002360b  add     rsp, 28h
0x18002360f  retn
0x180023610  cmp     cs:?g_bProcessShutdown@@3HA, 0; int g_bProcessShutdown
0x180023617  jnz     short loc_1800235BF
0x180023619  call    cs:__imp_FreeLibrary
0x18002361f  mov     cs:g_hinstMPRDLL, 0
0x18002362a  jmp     short loc_1800235BF
```
