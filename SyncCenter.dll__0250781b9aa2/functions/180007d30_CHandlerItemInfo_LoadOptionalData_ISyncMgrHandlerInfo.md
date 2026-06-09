# CHandlerItemInfo::_LoadOptionalData(ISyncMgrHandlerInfo *)

- ea: `0x180007d30`
- end: `0x180007f3d`
- name: `?_LoadOptionalData@CHandlerItemInfo@@AEAAXPEAUISyncMgrHandlerInfo@@@Z`
- size: `525`
- prototype: `void __fastcall(CHandlerItemInfo *__hidden this, struct ISyncMgrHandlerInfo *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007964`

## callees

- `0x180007d30`
- `0x18000b2b8`
- `0x18000b5f0`
- `0x18001c430`
- `0x18001c72c`
- `0x180024194`
- `0x180024510`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f2f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007dec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007e12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007dec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007e12`

## pseudocode

```c
void __fastcall CHandlerItemInfo::_LoadOptionalData(CHandlerItemInfo *this, struct ISyncMgrHandlerInfo *a2)
{
  struct ISyncMgrHandlerInfoVtbl *lpVtbl; // rax
  struct ISyncMgrHandlerInfoVtbl *v5; // rax
  struct ISyncMgrHandlerInfoVtbl *v6; // rax
  struct ISyncMgrHandlerInfoVtbl *v7; // rax
  int v8; // ebx
  struct _FILETIME v9; // rax
  struct _FILETIME v10; // rcx
  unsigned __int64 v11; // rcx
  bool v12; // zf
  struct _FILETIME *v13; // rcx
  __int64 v14; // rcx
  struct _FILETIME *p_pvData; // rdx
  struct _FILETIME pvData; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME v17; // [rsp+28h] [rbp-8h] BYREF
  SYNCMGR_HANDLER_TYPE v18; // [rsp+50h] [rbp+20h] BYREF
  struct _FILETIME v19; // [rsp+58h] [rbp+28h] BYREF
  LPCWSTR lpString1; // [rsp+60h] [rbp+30h] BYREF
  LPCWSTR v21; // [rsp+68h] [rbp+38h] BYREF

  lpVtbl = a2->lpVtbl;
  v18 = SYNCMGR_HT_UNSPECIFIED;
  ((void (__fastcall *)(struct ISyncMgrHandlerInfo *, SYNCMGR_HANDLER_TYPE *))lpVtbl->GetType)(a2, &v18);
  v5 = a2->lpVtbl;
  lpString1 = 0;
  ((void (__fastcall *)(struct ISyncMgrHandlerInfo *, LPCWSTR *))v5->GetTypeLabel)(a2, &lpString1);
  v6 = a2->lpVtbl;
  v21 = 0;
  ((void (__fastcall *)(struct ISyncMgrHandlerInfo *, LPCWSTR *))v6->GetComment)(a2, &v21);
  v7 = a2->lpVtbl;
  v19 = 0;
  v8 = ((__int64 (__fastcall *)(struct ISyncMgrHandlerInfo *, struct _FILETIME *))v7->GetLastSyncTime)(a2, &v19);
  if ( v8 < 0 )
    v19 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
  if ( (unsigned int)v18 <= SYNCMGR_HT_COMPUTER && v18 != *((_DWORD *)this + 211) )
    CItemInfo::SetHandlerType(this, v18);
  if ( lpString1 && lstrcmpW(lpString1, (LPCWSTR)this + 294) )
    CItemInfo::SetTypeLabel(this, lpString1);
  if ( v21 && lstrcmpW(v21, (LPCWSTR)this + 710) )
    CItemInfo::SetComment(this, v21);
  v9 = v19;
  v10 = v19;
  *((_BYTE *)this + 1976) = 0;
  v11 = HIDWORD(*(unsigned __int64 *)&v10);
  pvData = v9;
  if ( v8 < 0 )
  {
    *((_BYTE *)this + 1942) = 0;
    if ( !(_DWORD)v11 && !v9.dwLowDateTime )
    {
      CSyncMgrSettings::GetSyncTime((const unsigned __int16 *)this + 38, (const unsigned __int16 *)this + 102, &pvData);
      v9 = pvData;
    }
    v17 = v9;
    if ( *(_QWORD *)((char *)this + 852) != v9 )
    {
      *(struct _FILETIME *)((char *)this + 852) = v9;
      CItemState::MarkChangeState((char *)this + 8, 2);
      CSyncMgrSettings::SetSyncTime((const unsigned __int16 *)this + 38, (const unsigned __int16 *)this + 102, &v17);
    }
    v14 = *((_QWORD *)this + 5);
    if ( v14 )
    {
      p_pvData = &v17;
      goto LABEL_25;
    }
  }
  else
  {
    v12 = *((_DWORD *)this + 214) == (_DWORD)v11;
    v13 = (struct _FILETIME *)((char *)this + 852);
    *((_BYTE *)this + 1942) = 1;
    if ( !v12 || v13->dwLowDateTime != v9.dwLowDateTime )
    {
      *v13 = v9;
      CItemState::MarkChangeState((char *)this + 8, 2);
      CSyncMgrSettings::SetSyncTime((const unsigned __int16 *)this + 38, (const unsigned __int16 *)this + 102, &pvData);
    }
    v14 = *((_QWORD *)this + 5);
    if ( v14 )
    {
      p_pvData = &pvData;
LABEL_25:
      (*(void (__fastcall **)(__int64, struct _FILETIME *))(*(_QWORD *)v14 + 32LL))(v14, p_pvData);
    }
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
  CoTaskMemFree((LPVOID)lpString1);
  CoTaskMemFree((LPVOID)v21);
}

```

## disassembly

```asm
0x180007d30  push    rbp
0x180007d32  push    rbx
0x180007d33  push    rdi
0x180007d34  mov     rbp, rsp
0x180007d37  sub     rsp, 30h
0x180007d3b  mov     rax, [rdx]
0x180007d3e  mov     rbx, rdx
0x180007d41  mov     rdi, rcx
0x180007d44  mov     [rbp+arg_0], 0
0x180007d4b  lea     rdx, [rbp+arg_0]
0x180007d4f  mov     rcx, rbx
0x180007d52  mov     rax, [rax+18h]
0x180007d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d5b  mov     rax, [rbx]
0x180007d5e  lea     rdx, [rbp+lpString1]
0x180007d62  mov     rcx, rbx
0x180007d65  mov     [rbp+lpString1], 0
0x180007d6d  mov     rax, [rax+20h]
0x180007d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d76  mov     rax, [rbx]
0x180007d79  lea     rdx, [rbp+arg_18]
0x180007d7d  mov     rcx, rbx
0x180007d80  mov     [rbp+arg_18], 0
0x180007d88  mov     rax, [rax+28h]
0x180007d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d91  mov     rax, [rbx]
0x180007d94  lea     rdx, [rbp+arg_8]
0x180007d98  mov     rcx, rbx
0x180007d9b  mov     [rbp+arg_8], 0
0x180007da3  mov     rax, [rax+30h]
0x180007da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dac  mov     ebx, eax
0x180007dae  test    eax, eax
0x180007db0  jns     short loc_180007DBA
0x180007db2  mov     [rbp+arg_8], 0
0x180007dba  mov     rcx, [rdi+18h]; lpCriticalSection
0x180007dbe  call    cs:__imp_EnterCriticalSection
0x180007dc4  mov     edx, [rbp+arg_0]; enum SYNCMGR_HANDLER_TYPE
0x180007dc7  cmp     edx, 5
0x180007dca  ja      short loc_180007DDC
0x180007dcc  cmp     edx, [rdi+34Ch]
0x180007dd2  jz      short loc_180007DDC
0x180007dd4  mov     rcx, rdi; this
0x180007dd7  call    ?SetHandlerType@CItemInfo@@IEAAXW4SYNCMGR_HANDLER_TYPE@@@Z; CItemInfo::SetHandlerType(SYNCMGR_HANDLER_TYPE)
0x180007ddc  mov     rcx, [rbp+lpString1]; lpString1
0x180007de0  test    rcx, rcx
0x180007de3  jz      short loc_180007E02
0x180007de5  lea     rdx, [rdi+24Ch]; lpString2
0x180007dec  call    cs:__imp_lstrcmpW
0x180007df2  test    eax, eax
0x180007df4  jz      short loc_180007E02
0x180007df6  mov     rdx, [rbp+lpString1]; unsigned __int16 *
0x180007dfa  mov     rcx, rdi; this
0x180007dfd  call    ?SetTypeLabel@CItemInfo@@IEAAXPEBG@Z; CItemInfo::SetTypeLabel(ushort const *)
0x180007e02  mov     rcx, [rbp+arg_18]; lpString1
0x180007e06  test    rcx, rcx
0x180007e09  jz      short loc_180007E28
0x180007e0b  lea     rdx, [rdi+58Ch]; lpString2
0x180007e12  call    cs:__imp_lstrcmpW
0x180007e18  test    eax, eax
0x180007e1a  jz      short loc_180007E28
0x180007e1c  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x180007e20  mov     rcx, rdi; this
0x180007e23  call    ?SetComment@CItemInfo@@IEAAXPEBG@Z; CItemInfo::SetComment(ushort const *)
0x180007e28  mov     rax, [rbp+arg_8]
0x180007e2c  mov     rcx, rax
0x180007e2f  mov     byte ptr [rdi+7B8h], 0
0x180007e36  shr     rcx, 20h
0x180007e3a  mov     qword ptr [rbp+pvData.dwLowDateTime], rax
0x180007e3e  test    ebx, ebx
0x180007e40  js      short loc_180007E94
0x180007e42  cmp     [rdi+358h], ecx
0x180007e48  lea     rcx, [rdi+354h]
0x180007e4f  mov     byte ptr [rdi+796h], 1
0x180007e56  jnz     short loc_180007E5C
0x180007e58  cmp     [rcx], eax
0x180007e5a  jz      short loc_180007E81
0x180007e5c  mov     [rcx], rax
0x180007e5f  mov     edx, 2
0x180007e64  lea     rcx, [rdi+8]
0x180007e68  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x180007e6d  lea     rdx, [rdi+0CCh]; unsigned __int16 *
0x180007e74  lea     rcx, [rdi+4Ch]; unsigned __int16 *
0x180007e78  lea     r8, [rbp+pvData]; pvData
0x180007e7c  call    ?SetSyncTime@CSyncMgrSettings@@SAJPEBG0PEAU_FILETIME@@@Z; CSyncMgrSettings::SetSyncTime(ushort const *,ushort const *,_FILETIME *)
0x180007e81  mov     rcx, [rdi+28h]
0x180007e85  test    rcx, rcx
0x180007e88  jz      loc_180007F17
0x180007e8e  lea     rdx, [rbp+pvData]
0x180007e92  jmp     short loc_180007F0B
0x180007e94  mov     byte ptr [rdi+796h], 0
0x180007e9b  test    ecx, ecx
0x180007e9d  jnz     short loc_180007EBB
0x180007e9f  test    eax, eax
0x180007ea1  jnz     short loc_180007EBB
0x180007ea3  lea     rdx, [rdi+0CCh]; unsigned __int16 *
0x180007eaa  lea     rcx, [rdi+4Ch]; unsigned __int16 *
0x180007eae  lea     r8, [rbp+pvData]; pvData
0x180007eb2  call    ?GetSyncTime@CSyncMgrSettings@@SAJPEBG0PEAU_FILETIME@@@Z; CSyncMgrSettings::GetSyncTime(ushort const *,ushort const *,_FILETIME *)
0x180007eb7  mov     rax, qword ptr [rbp+pvData.dwLowDateTime]
0x180007ebb  mov     rcx, rax
0x180007ebe  mov     [rbp+var_8], rax
0x180007ec2  shr     rcx, 20h
0x180007ec6  cmp     [rdi+358h], ecx
0x180007ecc  lea     rcx, [rdi+354h]
0x180007ed3  jnz     short loc_180007ED9
0x180007ed5  cmp     [rcx], eax
0x180007ed7  jz      short loc_180007EFE
0x180007ed9  mov     [rcx], rax
0x180007edc  mov     edx, 2
0x180007ee1  lea     rcx, [rdi+8]
0x180007ee5  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x180007eea  lea     rdx, [rdi+0CCh]; unsigned __int16 *
0x180007ef1  lea     rcx, [rdi+4Ch]; unsigned __int16 *
0x180007ef5  lea     r8, [rbp+var_8]; pvData
0x180007ef9  call    ?SetSyncTime@CSyncMgrSettings@@SAJPEBG0PEAU_FILETIME@@@Z; CSyncMgrSettings::SetSyncTime(ushort const *,ushort const *,_FILETIME *)
0x180007efe  mov     rcx, [rdi+28h]
0x180007f02  test    rcx, rcx
0x180007f05  jz      short loc_180007F17
0x180007f07  lea     rdx, [rbp+var_8]
0x180007f0b  mov     rax, [rcx]
0x180007f0e  mov     rax, [rax+20h]
0x180007f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f17  mov     rcx, [rdi+18h]; lpCriticalSection
0x180007f1b  call    cs:__imp_LeaveCriticalSection
0x180007f21  mov     rcx, [rbp+lpString1]; pv
0x180007f25  call    cs:__imp_CoTaskMemFree
0x180007f2b  mov     rcx, [rbp+arg_18]; pv
0x180007f2f  call    cs:__imp_CoTaskMemFree
0x180007f35  add     rsp, 30h
0x180007f39  pop     rdi
0x180007f3a  pop     rbx
0x180007f3b  pop     rbp
0x180007f3c  retn
```
