# CConflictPropertyStore::_GetSyncItemName(tagPROPVARIANT *)

- ea: `0x180036e94`
- end: `0x180036f28`
- name: `?_GetSyncItemName@CConflictPropertyStore@@AEAAJPEAUtagPROPVARIANT@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(CConflictPropertyStore *this, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180033a80`

## callees

- `0x180036bd8`
- `0x180036e94`
- `0x18003840c`
- `0x18003849c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036f10`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180036eac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180036eac`

## pseudocode

```c
__int64 __fastcall CConflictPropertyStore::_GetSyncItemName(CConflictPropertyStore *this, PROPVARIANT *a2)
{
  struct ISyncMgrConflict *v4; // rcx
  int SyncHandlerID; // ebx
  struct ISyncMgrConflict *v6; // rcx
  CConflictPropertyStore *v7; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 *v10; // [rsp+40h] [rbp+18h] BYREF

  PropVariantClear(a2);
  v4 = (struct ISyncMgrConflict *)*((_QWORD *)this + 3);
  v10 = 0;
  SyncHandlerID = CConflictPropertyStore::s_GetSyncHandlerID(v4, &v10);
  if ( SyncHandlerID >= 0 )
  {
    v6 = (struct ISyncMgrConflict *)*((_QWORD *)this + 3);
    pv = 0;
    SyncHandlerID = CConflictPropertyStore::s_GetSyncItemID(v6, (unsigned __int16 **)&pv);
    if ( SyncHandlerID >= 0 )
    {
      SyncHandlerID = CConflictPropertyStore::_GetNameForItem(
                        v7,
                        v10,
                        (const unsigned __int16 *)pv,
                        (struct tagPROPVARIANT *)a2);
      CoTaskMemFree(pv);
    }
    CoTaskMemFree(v10);
  }
  return (unsigned int)SyncHandlerID;
}

```

## disassembly

```asm
0x180036e94  mov     [rsp+arg_8], rbx
0x180036e99  mov     [rsp+arg_18], rsi
0x180036e9e  push    rdi
0x180036e9f  sub     rsp, 20h
0x180036ea3  mov     rdi, rcx
0x180036ea6  mov     rsi, rdx
0x180036ea9  mov     rcx, rdx; pvar
0x180036eac  call    cs:__imp_PropVariantClear
0x180036eb2  mov     rcx, [rdi+18h]; struct ISyncMgrConflict *
0x180036eb6  lea     rdx, [rsp+28h+arg_10]; unsigned __int16 **
0x180036ebb  mov     [rsp+28h+arg_10], 0
0x180036ec4  call    ?s_GetSyncHandlerID@CConflictPropertyStore@@SAJPEAUISyncMgrConflict@@PEAPEAG@Z; CConflictPropertyStore::s_GetSyncHandlerID(ISyncMgrConflict *,ushort * *)
0x180036ec9  mov     ebx, eax
0x180036ecb  test    eax, eax
0x180036ecd  js      short loc_180036F16
0x180036ecf  mov     rcx, [rdi+18h]; struct ISyncMgrConflict *
0x180036ed3  lea     rdx, [rsp+28h+pv]; unsigned __int16 **
0x180036ed8  mov     [rsp+28h+pv], 0
0x180036ee1  call    ?s_GetSyncItemID@CConflictPropertyStore@@SAJPEAUISyncMgrConflict@@PEAPEAG@Z; CConflictPropertyStore::s_GetSyncItemID(ISyncMgrConflict *,ushort * *)
0x180036ee6  mov     ebx, eax
0x180036ee8  test    eax, eax
0x180036eea  js      short loc_180036F0B
0x180036eec  mov     r8, [rsp+28h+pv]; unsigned __int16 *
0x180036ef1  mov     r9, rsi; struct tagPROPVARIANT *
0x180036ef4  mov     rdx, [rsp+28h+arg_10]; unsigned __int16 *
0x180036ef9  call    ?_GetNameForItem@CConflictPropertyStore@@AEAAJPEBG0PEAUtagPROPVARIANT@@@Z; CConflictPropertyStore::_GetNameForItem(ushort const *,ushort const *,tagPROPVARIANT *)
0x180036efe  mov     rcx, [rsp+28h+pv]; pv
0x180036f03  mov     ebx, eax
0x180036f05  call    cs:__imp_CoTaskMemFree
0x180036f0b  mov     rcx, [rsp+28h+arg_10]; pv
0x180036f10  call    cs:__imp_CoTaskMemFree
0x180036f16  mov     rsi, [rsp+28h+arg_18]
0x180036f1b  mov     eax, ebx
0x180036f1d  mov     rbx, [rsp+28h+arg_8]
0x180036f22  add     rsp, 20h
0x180036f26  pop     rdi
0x180036f27  retn
```
