# CLegacyHandlerShim::~CLegacyHandlerShim(void)

- ea: `0x18001cb54`
- end: `0x18001cc5b`
- name: `??1CLegacyHandlerShim@@AEAA@XZ`
- size: `263`
- prototype: `void __fastcall(CLegacyHandlerShim *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001e220`

## callees

- `0x180007f44`
- `0x18000926c`
- `0x180009940`
- `0x18001cb54`
- `0x18001cddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cc43`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cc43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc08`

## pseudocode

```c
void __fastcall CLegacyHandlerShim::~CLegacyHandlerShim(CLegacyHandlerShim *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &CLegacyHandlerShim::`vftable'{for `ISyncMgrHandler'};
  *((_QWORD *)this + 1) = &CLegacyHandlerShim::`vftable'{for `ISyncMgrHandlerInfo'};
  *((_QWORD *)this + 2) = &CLegacyHandlerShim::`vftable'{for `ISyncMgrSyncItemContainer'};
  *((_QWORD *)this + 3) = &CLegacyHandlerShim::`vftable'{for `ISyncMgrSynchronizeCallback'};
  *((_QWORD *)this + 4) = &CLegacyHandlerShim::`vftable'{for `ISyncMgrEventLinkUIOperation'};
  v2 = (void *)*((_QWORD *)this + 27);
  if ( v2 )
  {
    CZeroInitNew::operator delete(v2);
    *((_QWORD *)this + 27) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 32);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 32) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 31);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 31) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 36);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 36) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 37);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 37) = 0;
  }
  CDPA<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::DestroyCallback((char *)this + 304);
  SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)this + 29);
  SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)this + 30);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>((__int64 *)this + 38);
}

```

## disassembly

```asm
0x18001cb54  mov     [rsp+arg_0], rbx
0x18001cb59  push    rdi
0x18001cb5a  sub     rsp, 20h
0x18001cb5e  lea     rax, ??_7CLegacyHandlerShim@@6BISyncMgrHandler@@@; const CLegacyHandlerShim::`vftable'{for `ISyncMgrHandler'}
0x18001cb65  mov     rdi, rcx
0x18001cb68  mov     [rcx], rax
0x18001cb6b  xor     ebx, ebx
0x18001cb6d  lea     rax, ??_7CLegacyHandlerShim@@6BISyncMgrHandlerInfo@@@; const CLegacyHandlerShim::`vftable'{for `ISyncMgrHandlerInfo'}
0x18001cb74  mov     [rcx+8], rax
0x18001cb78  lea     rax, ??_7CLegacyHandlerShim@@6BISyncMgrSyncItemContainer@@@; const CLegacyHandlerShim::`vftable'{for `ISyncMgrSyncItemContainer'}
0x18001cb7f  mov     [rcx+10h], rax
0x18001cb83  lea     rax, ??_7CLegacyHandlerShim@@6BISyncMgrSynchronizeCallback@@@; const CLegacyHandlerShim::`vftable'{for `ISyncMgrSynchronizeCallback'}
0x18001cb8a  mov     [rcx+18h], rax
0x18001cb8e  lea     rax, ??_7CLegacyHandlerShim@@6BISyncMgrEventLinkUIOperation@@@; const CLegacyHandlerShim::`vftable'{for `ISyncMgrEventLinkUIOperation'}
0x18001cb95  mov     [rcx+20h], rax
0x18001cb99  mov     rcx, [rcx+0D8h]; lpMem
0x18001cba0  test    rcx, rcx
0x18001cba3  jz      short loc_18001CBB1
0x18001cba5  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18001cbaa  mov     [rdi+0D8h], rbx
0x18001cbb1  mov     rcx, [rdi+100h]; hObject
0x18001cbb8  test    rcx, rcx
0x18001cbbb  jz      short loc_18001CBCA
0x18001cbbd  call    cs:__imp_CloseHandle
0x18001cbc3  mov     [rdi+100h], rbx
0x18001cbca  mov     rcx, [rdi+0F8h]; hObject
0x18001cbd1  test    rcx, rcx
0x18001cbd4  jz      short loc_18001CBE3
0x18001cbd6  call    cs:__imp_CloseHandle
0x18001cbdc  mov     [rdi+0F8h], rbx
0x18001cbe3  mov     rcx, [rdi+120h]; hObject
0x18001cbea  test    rcx, rcx
0x18001cbed  jz      short loc_18001CBFC
0x18001cbef  call    cs:__imp_CloseHandle
0x18001cbf5  mov     [rdi+120h], rbx
0x18001cbfc  mov     rcx, [rdi+128h]; hObject
0x18001cc03  test    rcx, rcx
0x18001cc06  jz      short loc_18001CC15
0x18001cc08  call    cs:__imp_CloseHandle
0x18001cc0e  mov     [rdi+128h], rbx
0x18001cc15  lea     rbx, [rdi+130h]
0x18001cc1c  mov     rcx, rbx
0x18001cc1f  call    ?DestroyCallback@?$CDPA@VCSyncItemRequestState@@V?$CTContainer_PolicyUnOwned@VCSyncItemRequestState@@@@@@QEAAXP6AHPEAVCSyncItemRequestState@@PEAX@Z1@Z; CDPA<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::DestroyCallback(int (*)(CSyncItemRequestState *,void *),void *)
0x18001cc24  lea     rcx, [rdi+0E8h]
0x18001cc2b  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18001cc30  lea     rcx, [rdi+0F0h]
0x18001cc37  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18001cc3c  lea     rcx, [rdi+0B0h]; lpCriticalSection
0x18001cc43  call    cs:__imp_DeleteCriticalSection
0x18001cc49  mov     rcx, rbx
0x18001cc4c  mov     rbx, [rsp+28h+arg_0]
0x18001cc51  add     rsp, 20h
0x18001cc55  pop     rdi
0x18001cc56  jmp     ??1?$CDPA_Base@VCSyncItemRequestState@@V?$CTContainer_PolicyUnOwned@VCSyncItemRequestState@@@@@@QEAA@XZ; CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>::~CDPA_Base<CSyncItemRequestState,CTContainer_PolicyUnOwned<CSyncItemRequestState>>(void)
```
