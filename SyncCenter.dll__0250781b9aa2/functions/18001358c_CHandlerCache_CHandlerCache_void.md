# CHandlerCache::~CHandlerCache(void)

- ea: `0x18001358c`
- end: `0x180013670`
- name: `??1CHandlerCache@@AEAA@XZ`
- size: `228`
- prototype: `void __fastcall(CHandlerCache *lpCriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180004c70`

## callees

- `0x18000926c`
- `0x180009310`
- `0x1800097e4`
- `0x18000b1fc`
- `0x18001358c`
- `0x180015c6c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001361e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001361e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800135d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001362d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001362d`

## pseudocode

```c
void __fastcall CHandlerCache::~CHandlerCache(CHandlerCache *lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG v2; // rcx
  HANDLE v3; // rcx

  CHandlerCache::_UpdateAutoStartKey(lpCriticalSection);
  CloseHandle(*((HANDLE *)lpCriticalSection + 13));
  CloseHandle(*((HANDLE *)lpCriticalSection + 51));
  CloseHandle(*((HANDLE *)lpCriticalSection + 52));
  CloseHandle(*((HANDLE *)lpCriticalSection + 53));
  CloseHandle(*((HANDLE *)lpCriticalSection + 54));
  CDPA<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::DestroyCallback((char *)lpCriticalSection + 40);
  CDPA<CAdviseSet,CTContainer_PolicyUnOwned<CAdviseSet>>::DestroyCallback((char *)lpCriticalSection + 48);
  CDPA<CHandlerInfo,CTContainer_PolicyUnOwned<CHandlerInfo>>::DestroyCallback((char *)lpCriticalSection + 56);
  v2 = (PRTL_CRITICAL_SECTION_DEBUG)*((_QWORD *)lpCriticalSection + 55);
  *((_QWORD *)lpCriticalSection + 55) = 0;
  if ( v2 )
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&v2->Type + 16LL))(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  v3 = (HANDLE)*((_QWORD *)lpCriticalSection + 8);
  if ( v3 )
  {
    LocalFree(v3);
    *((_QWORD *)lpCriticalSection + 8) = 0;
  }
  *((_QWORD *)lpCriticalSection + 9) = 0;
  *((_QWORD *)lpCriticalSection + 11) = 0;
  CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>((__int64 *)lpCriticalSection + 7);
  CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>((__int64 *)lpCriticalSection + 6);
  CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>((__int64 *)lpCriticalSection + 5);
}

```

## disassembly

```asm
0x18001358c  push    rbx
0x18001358e  push    rbp
0x18001358f  push    rsi
0x180013590  push    rdi
0x180013591  push    r14
0x180013593  sub     rsp, 20h
0x180013597  mov     rbx, rcx
0x18001359a  call    ?_UpdateAutoStartKey@CHandlerCache@@AEAAXXZ; CHandlerCache::_UpdateAutoStartKey(void)
0x18001359f  mov     rcx, [rbx+68h]; hObject
0x1800135a3  call    cs:__imp_CloseHandle
0x1800135a9  mov     rcx, [rbx+198h]; hObject
0x1800135b0  call    cs:__imp_CloseHandle
0x1800135b6  mov     rcx, [rbx+1A0h]; hObject
0x1800135bd  call    cs:__imp_CloseHandle
0x1800135c3  mov     rcx, [rbx+1A8h]; hObject
0x1800135ca  call    cs:__imp_CloseHandle
0x1800135d0  mov     rcx, [rbx+1B0h]; hObject
0x1800135d7  call    cs:__imp_CloseHandle
0x1800135dd  lea     rcx, [rbx+28h]
0x1800135e1  call    ?DestroyCallback@?$CDPA@VCHandlerCollectionInfo@@V?$CTContainer_PolicyUnOwned@VCHandlerCollectionInfo@@@@@@QEAAXP6AHPEAVCHandlerCollectionInfo@@PEAX@Z1@Z; CDPA<CHandlerCollectionInfo,CTContainer_PolicyUnOwned<CHandlerCollectionInfo>>::DestroyCallback(int (*)(CHandlerCollectionInfo *,void *),void *)
0x1800135e6  lea     rcx, [rbx+30h]
0x1800135ea  call    ?DestroyCallback@?$CDPA@VCAdviseSet@@V?$CTContainer_PolicyUnOwned@VCAdviseSet@@@@@@QEAAXP6AHPEAVCAdviseSet@@PEAX@Z1@Z; CDPA<CAdviseSet,CTContainer_PolicyUnOwned<CAdviseSet>>::DestroyCallback(int (*)(CAdviseSet *,void *),void *)
0x1800135ef  lea     rcx, [rbx+38h]
0x1800135f3  call    ?DestroyCallback@?$CDPA@VCHandlerInfo@@V?$CTContainer_PolicyUnOwned@VCHandlerInfo@@@@@@QEAAXP6AHPEAVCHandlerInfo@@PEAX@Z1@Z; CDPA<CHandlerInfo,CTContainer_PolicyUnOwned<CHandlerInfo>>::DestroyCallback(int (*)(CHandlerInfo *,void *),void *)
0x1800135f8  mov     rcx, [rbx+1B8h]
0x1800135ff  mov     qword ptr [rbx+1B8h], 0
0x18001360a  test    rcx, rcx
0x18001360d  jz      short loc_18001361B
0x18001360f  mov     rax, [rcx]
0x180013612  mov     rax, [rax+10h]
0x180013616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001361b  mov     rcx, rbx; lpCriticalSection
0x18001361e  call    cs:__imp_DeleteCriticalSection
0x180013624  mov     rcx, [rbx+40h]; hMem
0x180013628  test    rcx, rcx
0x18001362b  jz      short loc_18001363B
0x18001362d  call    cs:__imp_LocalFree
0x180013633  mov     qword ptr [rbx+40h], 0
0x18001363b  lea     rcx, [rbx+38h]
0x18001363f  mov     qword ptr [rbx+48h], 0
0x180013647  mov     qword ptr [rbx+58h], 0
0x18001364f  call    ??1?$CDPA_Base@VCSyncItemRequestState@@V?$CTContainer_PolicyUnOwned@VCSyncItemRequestState@@@@@@QEAA@XZ; CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>(void)
0x180013654  lea     rcx, [rbx+30h]
0x180013658  call    ??1?$CDPA_Base@VCSyncItemRequestState@@V?$CTContainer_PolicyUnOwned@VCSyncItemRequestState@@@@@@QEAA@XZ; CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>(void)
0x18001365d  lea     rcx, [rbx+28h]
0x180013661  add     rsp, 20h
0x180013665  pop     r14
0x180013667  pop     rdi
0x180013668  pop     rsi
0x180013669  pop     rbp
0x18001366a  pop     rbx
0x18001366b  jmp     ??1?$CDPA_Base@VCSyncItemRequestState@@V?$CTContainer_PolicyUnOwned@VCSyncItemRequestState@@@@@@QEAA@XZ; CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>(void)
```
