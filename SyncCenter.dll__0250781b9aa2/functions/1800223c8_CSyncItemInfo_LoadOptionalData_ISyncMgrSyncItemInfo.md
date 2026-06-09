# CSyncItemInfo::_LoadOptionalData(ISyncMgrSyncItemInfo *)

- ea: `0x1800223c8`
- end: `0x1800224d9`
- name: `?_LoadOptionalData@CSyncItemInfo@@AEAAXPEAUISyncMgrSyncItemInfo@@@Z`
- size: `273`
- prototype: `void __fastcall(CSyncItemInfo *__hidden this, struct ISyncMgrSyncItemInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021e20`

## callees

- `0x18000abf4`
- `0x18000acd0`
- `0x18001c430`
- `0x18001c72c`
- `0x1800223c8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002243c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002243c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224cb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180022452`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180022478`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180022452`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180022478`

## pseudocode

```c
void __fastcall CSyncItemInfo::_LoadOptionalData(CSyncItemInfo *this, struct ISyncMgrSyncItemInfo *a2)
{
  struct ISyncMgrSyncItemInfoVtbl *lpVtbl; // rax
  struct ISyncMgrSyncItemInfoVtbl *v5; // rax
  struct ISyncMgrSyncItemInfoVtbl *v6; // rax
  int v7; // ebx
  struct _FILETIME v8; // rdx
  struct _FILETIME v9; // [rsp+40h] [rbp+20h] BYREF
  LPCWSTR lpString1; // [rsp+48h] [rbp+28h] BYREF
  LPCWSTR v11; // [rsp+50h] [rbp+30h] BYREF

  lpVtbl = a2->lpVtbl;
  lpString1 = 0;
  ((void (__fastcall *)(struct ISyncMgrSyncItemInfo *, LPCWSTR *))lpVtbl->GetTypeLabel)(a2, &lpString1);
  v5 = a2->lpVtbl;
  v11 = 0;
  ((void (__fastcall *)(struct ISyncMgrSyncItemInfo *, LPCWSTR *))v5->GetComment)(a2, &v11);
  v6 = a2->lpVtbl;
  v9 = 0;
  v7 = ((__int64 (__fastcall *)(struct ISyncMgrSyncItemInfo *, struct _FILETIME *))v6->GetLastSyncTime)(a2, &v9);
  if ( v7 < 0 )
    v9 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
  if ( lpString1 && lstrcmpW(lpString1, (LPCWSTR)this + 294) )
    CItemInfo::SetTypeLabel(this, lpString1);
  if ( v11 && lstrcmpW(v11, (LPCWSTR)this + 710) )
    CItemInfo::SetComment(this, v11);
  v8 = v9;
  if ( v7 < 0 )
  {
    *((_BYTE *)this + 1942) = 0;
    CItemInfo::SetLastSyncFinishedTime(this, v8);
  }
  else
  {
    *((_BYTE *)this + 1942) = 1;
    CItemInfo::_SetLastSyncFinishedTime(this, v8);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
  CoTaskMemFree((LPVOID)lpString1);
  CoTaskMemFree((LPVOID)v11);
}

```

## disassembly

```asm
0x1800223c8  push    rbp
0x1800223ca  push    rbx
0x1800223cb  push    rdi
0x1800223cc  mov     rbp, rsp
0x1800223cf  sub     rsp, 20h
0x1800223d3  mov     rax, [rdx]
0x1800223d6  mov     rbx, rdx
0x1800223d9  mov     rdi, rcx
0x1800223dc  mov     [rbp+lpString1], 0
0x1800223e4  lea     rdx, [rbp+lpString1]
0x1800223e8  mov     rcx, rbx
0x1800223eb  mov     rax, [rax+18h]
0x1800223ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223f4  mov     rax, [rbx]
0x1800223f7  lea     rdx, [rbp+arg_10]
0x1800223fb  mov     rcx, rbx
0x1800223fe  mov     [rbp+arg_10], 0
0x180022406  mov     rax, [rax+20h]
0x18002240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002240f  mov     rax, [rbx]
0x180022412  lea     rdx, [rbp+arg_0]
0x180022416  mov     rcx, rbx
0x180022419  mov     qword ptr [rbp+arg_0.dwLowDateTime], 0
0x180022421  mov     rax, [rax+28h]
0x180022425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002242a  mov     ebx, eax
0x18002242c  test    eax, eax
0x18002242e  jns     short loc_180022438
0x180022430  mov     qword ptr [rbp+arg_0.dwLowDateTime], 0
0x180022438  mov     rcx, [rdi+18h]; lpCriticalSection
0x18002243c  call    cs:__imp_EnterCriticalSection
0x180022442  mov     rcx, [rbp+lpString1]; lpString1
0x180022446  test    rcx, rcx
0x180022449  jz      short loc_180022468
0x18002244b  lea     rdx, [rdi+24Ch]; lpString2
0x180022452  call    cs:__imp_lstrcmpW
0x180022458  test    eax, eax
0x18002245a  jz      short loc_180022468
0x18002245c  mov     rdx, [rbp+lpString1]; unsigned __int16 *
0x180022460  mov     rcx, rdi; this
0x180022463  call    ?SetTypeLabel@CItemInfo@@IEAAXPEBG@Z; CItemInfo::SetTypeLabel(ushort const *)
0x180022468  mov     rcx, [rbp+arg_10]; lpString1
0x18002246c  test    rcx, rcx
0x18002246f  jz      short loc_18002248E
0x180022471  lea     rdx, [rdi+58Ch]; lpString2
0x180022478  call    cs:__imp_lstrcmpW
0x18002247e  test    eax, eax
0x180022480  jz      short loc_18002248E
0x180022482  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x180022486  mov     rcx, rdi; this
0x180022489  call    ?SetComment@CItemInfo@@IEAAXPEBG@Z; CItemInfo::SetComment(ushort const *)
0x18002248e  mov     rdx, qword ptr [rbp+arg_0.dwLowDateTime]; struct _FILETIME
0x180022492  mov     rcx, rdi; this
0x180022495  test    ebx, ebx
0x180022497  js      short loc_1800224A7
0x180022499  mov     byte ptr [rdi+796h], 1
0x1800224a0  call    ?_SetLastSyncFinishedTime@CItemInfo@@AEAAXU_FILETIME@@@Z; CItemInfo::_SetLastSyncFinishedTime(_FILETIME)
0x1800224a5  jmp     short loc_1800224B3
0x1800224a7  mov     byte ptr [rdi+796h], 0
0x1800224ae  call    ?SetLastSyncFinishedTime@CItemInfo@@QEAAXU_FILETIME@@@Z; CItemInfo::SetLastSyncFinishedTime(_FILETIME)
0x1800224b3  mov     rcx, [rdi+18h]; lpCriticalSection
0x1800224b7  call    cs:__imp_LeaveCriticalSection
0x1800224bd  mov     rcx, [rbp+lpString1]; pv
0x1800224c1  call    cs:__imp_CoTaskMemFree
0x1800224c7  mov     rcx, [rbp+arg_10]; pv
0x1800224cb  call    cs:__imp_CoTaskMemFree
0x1800224d1  add     rsp, 20h
0x1800224d5  pop     rdi
0x1800224d6  pop     rbx
0x1800224d7  pop     rbp
0x1800224d8  retn
```
