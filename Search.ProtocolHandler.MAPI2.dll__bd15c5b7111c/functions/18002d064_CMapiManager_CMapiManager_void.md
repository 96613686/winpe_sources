# CMapiManager::~CMapiManager(void)

- ea: `0x18002d064`
- end: `0x18002d14e`
- name: `??1CMapiManager@@EEAA@XZ`
- size: `234`
- prototype: `void __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002d300`

## callees

- `0x1800113ec`
- `0x18002d064`
- `0x18002d938`
- `0x18002f660`
- `0x18002f6fc`
- `0x180030104`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d121`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d12e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d121`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d12e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d09f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d10b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d09f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d10b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002d0f9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002d0f9`

## pseudocode

```c
void __fastcall CMapiManager::~CMapiManager(CMapiManager *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  const void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CMapiManager::`vftable';
  CLogger::Info(L"CMapiManager::~CMapiManager() Enter");
  CMapiManager::UnInitialize(this);
  CMapiManager::CleanupStoreWatchers(this, 1);
  CloseHandle(*((HANDLE *)this + 17));
  v2 = (void *)*((_QWORD *)this + 22);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 23);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 33);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 34);
  if ( v5 )
    CloseHandle(v5);
  v6 = (const void *)*((_QWORD *)this + 26);
  if ( v6 )
    UnmapViewOfFile(v6);
  v7 = (void *)*((_QWORD *)this + 25);
  if ( v7 )
    CloseHandle(v7);
  CLogger::Info(L"CMapiManager::~CMapiManager() Exit");
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::RemoveAll((char *)this + 280);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll((char *)this + 16);
}

```

## disassembly

```asm
0x18002d064  push    rbx
0x18002d066  sub     rsp, 20h
0x18002d06a  mov     rbx, rcx
0x18002d06d  lea     rax, ??_7CMapiManager@@6B@; const CMapiManager::`vftable'
0x18002d074  mov     [rcx], rax
0x18002d077  lea     rcx, aCmapimanagerCm_0; "CMapiManager::~CMapiManager() Enter"
0x18002d07e  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002d083  mov     rcx, rbx; this
0x18002d086  call    ?UnInitialize@CMapiManager@@AEAAJXZ; CMapiManager::UnInitialize(void)
0x18002d08b  mov     edx, 1; int
0x18002d090  mov     rcx, rbx; this
0x18002d093  call    ?CleanupStoreWatchers@CMapiManager@@AEAAXH@Z; CMapiManager::CleanupStoreWatchers(int)
0x18002d098  mov     rcx, [rbx+88h]; hObject
0x18002d09f  call    cs:__imp_CloseHandle
0x18002d0a5  mov     rcx, [rbx+0B0h]; hObject
0x18002d0ac  test    rcx, rcx
0x18002d0af  jz      short loc_18002D0B7
0x18002d0b1  call    cs:__imp_CloseHandle
0x18002d0b7  mov     rcx, [rbx+0B8h]; hObject
0x18002d0be  test    rcx, rcx
0x18002d0c1  jz      short loc_18002D0C9
0x18002d0c3  call    cs:__imp_CloseHandle
0x18002d0c9  mov     rcx, [rbx+108h]; hObject
0x18002d0d0  test    rcx, rcx
0x18002d0d3  jz      short loc_18002D0DB
0x18002d0d5  call    cs:__imp_CloseHandle
0x18002d0db  mov     rcx, [rbx+110h]; hObject
0x18002d0e2  test    rcx, rcx
0x18002d0e5  jz      short loc_18002D0ED
0x18002d0e7  call    cs:__imp_CloseHandle
0x18002d0ed  mov     rcx, [rbx+0D0h]; lpBaseAddress
0x18002d0f4  test    rcx, rcx
0x18002d0f7  jz      short loc_18002D0FF
0x18002d0f9  call    cs:__imp_UnmapViewOfFile
0x18002d0ff  mov     rcx, [rbx+0C8h]; hObject
0x18002d106  test    rcx, rcx
0x18002d109  jz      short loc_18002D111
0x18002d10b  call    cs:__imp_CloseHandle
0x18002d111  lea     rcx, aCmapimanagerCm_1; "CMapiManager::~CMapiManager() Exit"
0x18002d118  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002d11d  lea     rcx, [rbx+58h]; lpCriticalSection
0x18002d121  call    cs:__imp_DeleteCriticalSection
0x18002d127  lea     rcx, [rbx+160h]; lpCriticalSection
0x18002d12e  call    cs:__imp_DeleteCriticalSection
0x18002d134  lea     rcx, [rbx+118h]
0x18002d13b  call    ?RemoveAll@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::RemoveAll(void)
0x18002d140  lea     rcx, [rbx+10h]
0x18002d144  add     rsp, 20h
0x18002d148  pop     rbx
0x18002d149  jmp     ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiStore@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiStore@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll(void)
```
