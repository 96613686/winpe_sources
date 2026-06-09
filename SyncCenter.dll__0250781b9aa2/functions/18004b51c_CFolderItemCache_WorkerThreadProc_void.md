# CFolderItemCache::_WorkerThreadProc(void *)

- ea: `0x18004b51c`
- end: `0x18004b6be`
- name: `?_WorkerThreadProc@CFolderItemCache@@AEAAXPEAX@Z`
- size: `418`
- prototype: `void __fastcall(CFolderItemCache *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004b760`

## callees

- `0x180007f44`
- `0x18004aa14`
- `0x18004b218`
- `0x18004b32c`
- `0x18004b47c`
- `0x18004b51c`
- `0x18004b6c4`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b683`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b690`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b614`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b614`

## pseudocode

```c
void __fastcall CFolderItemCache::_WorkerThreadProc(CFolderItemCache *this, void *a2)
{
  __int64 v2; // rdx
  CFolderItemCache *v3; // rcx
  int v4; // r8d
  CFolderItemCache *v5; // rcx
  __int64 v6; // rdx
  int v7; // r8d
  char v8; // bl
  __int64 v9; // rcx
  unsigned int v10; // [rsp+30h] [rbp-79h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-71h] BYREF
  struct IPrivSyncMgrHandlerDataStore *v12[2]; // [rsp+40h] [rbp-69h] BYREF
  int v13; // [rsp+50h] [rbp-59h] BYREF
  WCHAR v14[64]; // [rsp+54h] [rbp-55h] BYREF
  int v15; // [rsp+D4h] [rbp+2Bh]
  __int64 v16; // [rsp+D8h] [rbp+2Fh]
  __int64 v17; // [rsp+E0h] [rbp+37h]
  LPITEMIDLIST v18; // [rsp+E8h] [rbp+3Fh]

  v12[0] = 0;
  v10 = 0;
  if ( (int)CFolderItemCache::_WorkerSetupAdvise(this, (LPVOID *)v12, &v10) < 0 )
  {
    SetEvent(hEvent);
    goto LABEL_20;
  }
  if ( (int)CFolderItemCache::_EnumData(v3, v2, v4) >= 0 )
  {
    while ( 1 )
    {
      v13 = 0;
      memset_0(v14, 0, sizeof(v14));
      v16 = 0;
      v15 = 0;
      v17 = 0;
      v18 = 0;
      CFolderItemCache::_WorkerGetNextOperation(v5, (struct CFolderItemCache::CACHE_THREAD_DATA *)&v13);
      v8 = 0;
      if ( v13 == 1 )
      {
        v8 = 1;
      }
      else
      {
        if ( v13 == 2 )
        {
          CFolderItemCache::_EnumData(0, v6, v7);
          ppv = 0;
          if ( CoCreateInstance(&CLSID_SyncMgrp, 0, 4u, &GUID_1df997e7_21c2_4258_a795_49c5d8869bd2, &ppv) >= 0 )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 72LL))(ppv);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        else
        {
          v9 = (unsigned int)(v13 - 3);
          if ( v13 == 3 )
          {
            CFolderItemCache::_WorkerRegisterForUpdates(v9, v14, v16, v17, v18);
          }
          else
          {
            if ( v13 != 4 )
              goto LABEL_13;
            CFolderItemCache::_WorkerUnregisterForUpdates(v9, v14, v16, (unsigned int)v17);
          }
        }
        v13 = 0;
      }
LABEL_13:
      if ( !qword_180070DA8 || !*(_DWORD *)qword_180070DA8 || v8 )
      {
        if ( v10 )
          (*(void (__fastcall **)(struct IPrivSyncMgrHandlerDataStore *))(*(_QWORD *)v12[0] + 104LL))(v12[0]);
        SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)v12);
        break;
      }
    }
  }
LABEL_20:
  CloseHandle(qword_180070D28);
  qword_180070D28 = 0;
}

```

## disassembly

```asm
0x18004b51c  mov     [rsp-8+arg_0], rbx
0x18004b521  mov     [rsp-8+arg_8], rdi
0x18004b526  push    rbp
0x18004b527  lea     rbp, [rsp-57h]
0x18004b52c  sub     rsp, 100h
0x18004b533  mov     rax, cs:__security_cookie
0x18004b53a  xor     rax, rsp
0x18004b53d  mov     [rbp+57h+var_10], rax
0x18004b541  xor     edi, edi
0x18004b543  lea     r8, [rbp+57h+var_D0]; unsigned int *
0x18004b547  lea     rdx, [rbp+57h+var_C0]; struct IPrivSyncMgrHandlerDataStore **
0x18004b54b  mov     [rbp+57h+var_C0], rdi
0x18004b54f  mov     [rbp+57h+var_D0], edi
0x18004b552  call    ?_WorkerSetupAdvise@CFolderItemCache@@AEAAJPEAPEAUIPrivSyncMgrHandlerDataStore@@PEAK@Z; CFolderItemCache::_WorkerSetupAdvise(IPrivSyncMgrHandlerDataStore * *,ulong *)
0x18004b557  test    eax, eax
0x18004b559  js      loc_18004B67C
0x18004b55f  call    ?_EnumData@CFolderItemCache@@AEAAJXZ; CFolderItemCache::_EnumData(void)
0x18004b564  test    eax, eax
0x18004b566  js      loc_18004B689
0x18004b56c  xor     edx, edx; Val
0x18004b56e  mov     [rbp+57h+var_B0], edi
0x18004b571  mov     r8d, 80h; Size
0x18004b577  lea     rcx, [rbp+57h+var_AC]; void *
0x18004b57b  call    memset_0
0x18004b580  xor     eax, eax
0x18004b582  mov     [rbp+57h+var_28], rdi
0x18004b586  lea     rdx, [rbp+57h+var_B0]; struct CFolderItemCache::CACHE_THREAD_DATA *
0x18004b58a  mov     [rbp+57h+var_2C], eax
0x18004b58d  mov     [rbp+57h+var_20], rdi
0x18004b591  mov     [rbp+57h+var_18], rdi
0x18004b595  call    ?_WorkerGetNextOperation@CFolderItemCache@@AEAAXPEAUCACHE_THREAD_DATA@1@@Z; CFolderItemCache::_WorkerGetNextOperation(CFolderItemCache::CACHE_THREAD_DATA *)
0x18004b59a  mov     ecx, [rbp+57h+var_B0]
0x18004b59d  mov     bl, dil
0x18004b5a0  sub     ecx, 1
0x18004b5a3  jz      loc_18004B640
0x18004b5a9  sub     ecx, 1; this
0x18004b5ac  jz      short loc_18004B5EE
0x18004b5ae  sub     ecx, 1
0x18004b5b1  jz      short loc_18004B5CF
0x18004b5b3  cmp     ecx, 1
0x18004b5b6  jnz     loc_18004B642
0x18004b5bc  mov     r9d, dword ptr [rbp+57h+var_20]
0x18004b5c0  lea     rdx, [rbp+57h+var_AC]
0x18004b5c4  mov     r8, [rbp+57h+var_28]
0x18004b5c8  call    ?_WorkerUnregisterForUpdates@CFolderItemCache@@AEAAJPEBGPEAUHWND__@@W4SYNCMGR_UPDATE_VIEW_ID@@@Z; CFolderItemCache::_WorkerUnregisterForUpdates(ushort const *,HWND__ *,SYNCMGR_UPDATE_VIEW_ID)
0x18004b5cd  jmp     short loc_18004B5E9
0x18004b5cf  mov     rax, [rbp+57h+var_18]
0x18004b5d3  lea     rdx, [rbp+57h+var_AC]
0x18004b5d7  mov     r9d, dword ptr [rbp+57h+var_20]
0x18004b5db  mov     r8, [rbp+57h+var_28]
0x18004b5df  mov     [rsp+100h+ppv], rax
0x18004b5e4  call    ?_WorkerRegisterForUpdates@CFolderItemCache@@AEAAJPEBGPEAUHWND__@@W4SYNCMGR_UPDATE_VIEW_ID@@PEAU_ITEMIDLIST_ABSOLUTE@@@Z; CFolderItemCache::_WorkerRegisterForUpdates(ushort const *,HWND__ *,SYNCMGR_UPDATE_VIEW_ID,_ITEMIDLIST_ABSOLUTE *)
0x18004b5e9  mov     [rbp+57h+var_B0], edi
0x18004b5ec  jmp     short loc_18004B642
0x18004b5ee  call    ?_EnumData@CFolderItemCache@@AEAAJXZ; CFolderItemCache::_EnumData(void)
0x18004b5f3  xor     edx, edx; pUnkOuter
0x18004b5f5  mov     [rbp+57h+var_C8], rdi
0x18004b5f9  lea     rax, [rbp+57h+var_C8]
0x18004b5fd  lea     r9, _GUID_1df997e7_21c2_4258_a795_49c5d8869bd2; riid
0x18004b604  mov     [rsp+100h+ppv], rax; ppv
0x18004b609  lea     rcx, CLSID_SyncMgrp; rclsid
0x18004b610  lea     r8d, [rdx+4]; dwClsContext
0x18004b614  call    cs:__imp_CoCreateInstance
0x18004b61a  test    eax, eax
0x18004b61c  js      short loc_18004B5E9
0x18004b61e  mov     rcx, [rbp+57h+var_C8]
0x18004b622  mov     rax, [rcx]
0x18004b625  mov     rax, [rax+48h]
0x18004b629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b62e  mov     rcx, [rbp+57h+var_C8]
0x18004b632  mov     rax, [rcx]
0x18004b635  mov     rax, [rax+10h]
0x18004b639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b63e  jmp     short loc_18004B5E9
0x18004b640  mov     bl, 1
0x18004b642  mov     rax, cs:qword_180070DA8
0x18004b649  test    rax, rax
0x18004b64c  jz      short loc_18004B65A
0x18004b64e  cmp     [rax], edi
0x18004b650  jz      short loc_18004B65A
0x18004b652  test    bl, bl
0x18004b654  jz      loc_18004B56C
0x18004b65a  mov     edx, [rbp+57h+var_D0]
0x18004b65d  test    edx, edx
0x18004b65f  jz      short loc_18004B671
0x18004b661  mov     rcx, [rbp+57h+var_C0]
0x18004b665  mov     rax, [rcx]
0x18004b668  mov     rax, [rax+68h]
0x18004b66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b671  lea     rcx, [rbp+57h+var_C0]
0x18004b675  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18004b67a  jmp     short loc_18004B689
0x18004b67c  mov     rcx, cs:hEvent; hEvent
0x18004b683  call    cs:__imp_SetEvent
0x18004b689  mov     rcx, cs:qword_180070D28; hObject
0x18004b690  call    cs:__imp_CloseHandle
0x18004b696  mov     cs:qword_180070D28, rdi
0x18004b69d  mov     rcx, [rbp+57h+var_10]
0x18004b6a1  xor     rcx, rsp; StackCookie
0x18004b6a4  call    __security_check_cookie
0x18004b6a9  lea     r11, [rsp+100h+var_s0]
0x18004b6b1  mov     rbx, [r11+10h]
0x18004b6b5  mov     rdi, [r11+18h]
0x18004b6b9  mov     rsp, r11
0x18004b6bc  pop     rbp
0x18004b6bd  retn
```
