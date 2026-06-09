# CConflictPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180033a80`
- end: `0x180033c0d`
- name: `?GetValue@CConflictPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(CConflictPropertyStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180033a80`
- `0x1800367cc`
- `0x180036bd8`
- `0x180036e94`
- `0x18003840c`
- `0x1800388e0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033bb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033bb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033a95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033b7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033a95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033b7b`

## pseudocode

```c
__int64 __fastcall CConflictPropertyStore::GetValue(
        CConflictPropertyStore *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3)
{
  __int64 v6; // r9
  int SyncHandlerID; // ebx
  unsigned __int16 *v8; // rcx
  DWORD pid; // eax
  __int64 v10; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  struct ISyncMgrConflict *v15; // rcx
  CConflictPropertyStore *v16; // rcx
  __int64 v17; // rax
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  PropVariantClear(a3);
  v6 = *((_QWORD *)this + 3);
  SyncHandlerID = 0;
  if ( v6 )
  {
    v8 = (unsigned __int16 *)*((_QWORD *)this + 2);
    if ( v8 )
    {
      pid = a2->pid;
      if ( pid == 10 )
      {
        v10 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
          v10 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
        if ( !v10 )
          return (unsigned int)InitPropVariantFromStringEx(v8, 8u, (struct tagPROPVARIANT *)a3);
        return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v6 + 24LL))(
                               *((_QWORD *)this + 3),
                               a2,
                               a3);
      }
      if ( pid == 4 )
      {
        v12 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1;
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1 )
          v12 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ItemTypeText.fmtid.Data4;
        if ( !v12 )
          return (unsigned int)CConflictPropertyStore::_GetConflictTypeProperty(this, (struct tagPROPVARIANT *)a3);
        return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v6 + 24LL))(
                               *((_QWORD *)this + 3),
                               a2,
                               a3);
      }
      if ( pid == 12 )
      {
        v13 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Size.fmtid.Data1;
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Size.fmtid.Data1 )
          v13 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Size.fmtid.Data4;
        if ( v13 )
          return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v6 + 24LL))(
                                 *((_QWORD *)this + 3),
                                 a2,
                                 a3);
        *(_WORD *)a3 = 21;
        a3[1] = 0;
      }
      else
      {
        if ( pid != 2 )
        {
          if ( pid == 3 )
          {
            v17 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Sync_ItemName.fmtid.Data1;
            if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Sync_ItemName.fmtid.Data1 )
              v17 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Sync_ItemName.fmtid.Data4;
            if ( !v17 )
              return (unsigned int)CConflictPropertyStore::_GetSyncItemName(this, a3);
          }
          return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v6 + 24LL))(
                                 *((_QWORD *)this + 3),
                                 a2,
                                 a3);
        }
        v14 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Sync_HandlerName.fmtid.Data1;
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Sync_HandlerName.fmtid.Data1 )
          v14 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Sync_HandlerName.fmtid.Data4;
        if ( v14 )
          return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v6 + 24LL))(
                                 *((_QWORD *)this + 3),
                                 a2,
                                 a3);
        PropVariantClear(a3);
        v15 = (struct ISyncMgrConflict *)*((_QWORD *)this + 3);
        pv = 0;
        SyncHandlerID = CConflictPropertyStore::s_GetSyncHandlerID(v15, (unsigned __int16 **)&pv);
        if ( SyncHandlerID >= 0 )
        {
          SyncHandlerID = CConflictPropertyStore::_GetNameForItem(
                            v16,
                            (const unsigned __int16 *)pv,
                            &String2,
                            (struct tagPROPVARIANT *)a3);
          CoTaskMemFree(pv);
        }
      }
    }
  }
  return (unsigned int)SyncHandlerID;
}

```

## disassembly

```asm
0x180033a80  push    rbx
0x180033a82  push    rbp
0x180033a83  push    rsi
0x180033a84  push    rdi
0x180033a85  sub     rsp, 28h
0x180033a89  mov     rbp, rcx
0x180033a8c  mov     rsi, r8
0x180033a8f  mov     rcx, r8; pvar
0x180033a92  mov     rdi, rdx
0x180033a95  call    cs:__imp_PropVariantClear
0x180033a9b  mov     r9, [rbp+18h]
0x180033a9f  xor     ebx, ebx
0x180033aa1  test    r9, r9
0x180033aa4  jz      loc_180033C02
0x180033aaa  mov     rcx, [rbp+10h]; unsigned __int16 *
0x180033aae  test    rcx, rcx
0x180033ab1  jz      loc_180033C02
0x180033ab7  mov     eax, [rdi+10h]
0x180033aba  cmp     eax, 0Ah
0x180033abd  jnz     short loc_180033AEF
0x180033abf  mov     rax, [rdi]
0x180033ac2  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x180033ac9  jnz     short loc_180033AD6
0x180033acb  mov     rax, [rdi+8]
0x180033acf  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x180033ad6  test    rax, rax
0x180033ad9  jnz     loc_180033BEB
0x180033adf  lea     edx, [rax+8]
0x180033ae2  mov     r8, rsi
0x180033ae5  call    InitPropVariantFromStringEx
0x180033aea  jmp     loc_180033C00
0x180033aef  cmp     eax, 4
0x180033af2  jnz     short loc_180033B24
0x180033af4  mov     rax, [rdi]
0x180033af7  sub     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data1
0x180033afe  jnz     short loc_180033B0B
0x180033b00  mov     rax, [rdi+8]
0x180033b04  sub     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data4
0x180033b0b  test    rax, rax
0x180033b0e  jnz     loc_180033BEB
0x180033b14  mov     rdx, rsi; struct tagPROPVARIANT *
0x180033b17  mov     rcx, rbp; this
0x180033b1a  call    ?_GetConflictTypeProperty@CConflictPropertyStore@@AEAAJPEAUtagPROPVARIANT@@@Z; CConflictPropertyStore::_GetConflictTypeProperty(tagPROPVARIANT *)
0x180033b1f  jmp     loc_180033C00
0x180033b24  cmp     eax, 0Ch
0x180033b27  jnz     short loc_180033B57
0x180033b29  mov     rax, [rdi]
0x180033b2c  sub     rax, qword ptr cs:PKEY_Size.fmtid.Data1
0x180033b33  jnz     short loc_180033B40
0x180033b35  mov     rax, [rdi+8]
0x180033b39  sub     rax, qword ptr cs:PKEY_Size.fmtid.Data4
0x180033b40  test    rax, rax
0x180033b43  jnz     loc_180033BEB
0x180033b49  mov     word ptr [rsi], 15h
0x180033b4e  mov     [rsi+8], rbx
0x180033b52  jmp     loc_180033C02
0x180033b57  cmp     eax, 2
0x180033b5a  jnz     short loc_180033BBD
0x180033b5c  mov     rax, [rdi]
0x180033b5f  sub     rax, qword ptr cs:PKEY_Sync_HandlerName.fmtid.Data1
0x180033b66  jnz     short loc_180033B73
0x180033b68  mov     rax, [rdi+8]
0x180033b6c  sub     rax, qword ptr cs:PKEY_Sync_HandlerName.fmtid.Data4
0x180033b73  test    rax, rax
0x180033b76  jnz     short loc_180033BEB
0x180033b78  mov     rcx, rsi; pvar
0x180033b7b  call    cs:__imp_PropVariantClear
0x180033b81  mov     rcx, [rbp+18h]; struct ISyncMgrConflict *
0x180033b85  lea     rdx, [rsp+48h+pv]; unsigned __int16 **
0x180033b8a  mov     [rsp+48h+pv], rbx
0x180033b8f  call    ?s_GetSyncHandlerID@CConflictPropertyStore@@SAJPEAUISyncMgrConflict@@PEAPEAG@Z; CConflictPropertyStore::s_GetSyncHandlerID(ISyncMgrConflict *,ushort * *)
0x180033b94  mov     ebx, eax
0x180033b96  test    eax, eax
0x180033b98  js      short loc_180033C02
0x180033b9a  mov     rdx, [rsp+48h+pv]; unsigned __int16 *
0x180033b9f  lea     r8, String2; unsigned __int16 *
0x180033ba6  mov     r9, rsi; struct tagPROPVARIANT *
0x180033ba9  call    ?_GetNameForItem@CConflictPropertyStore@@AEAAJPEBG0PEAUtagPROPVARIANT@@@Z; CConflictPropertyStore::_GetNameForItem(ushort const *,ushort const *,tagPROPVARIANT *)
0x180033bae  mov     rcx, [rsp+48h+pv]; pv
0x180033bb3  mov     ebx, eax
0x180033bb5  call    cs:__imp_CoTaskMemFree
0x180033bbb  jmp     short loc_180033C02
0x180033bbd  cmp     eax, 3
0x180033bc0  jnz     short loc_180033BEB
0x180033bc2  mov     rax, [rdi]
0x180033bc5  sub     rax, qword ptr cs:PKEY_Sync_ItemName.fmtid.Data1
0x180033bcc  jnz     short loc_180033BD9
0x180033bce  mov     rax, [rdi+8]
0x180033bd2  sub     rax, qword ptr cs:PKEY_Sync_ItemName.fmtid.Data4
0x180033bd9  test    rax, rax
0x180033bdc  jnz     short loc_180033BEB
0x180033bde  mov     rdx, rsi; struct tagPROPVARIANT *
0x180033be1  mov     rcx, rbp; this
0x180033be4  call    ?_GetSyncItemName@CConflictPropertyStore@@AEAAJPEAUtagPROPVARIANT@@@Z; CConflictPropertyStore::_GetSyncItemName(tagPROPVARIANT *)
0x180033be9  jmp     short loc_180033C00
0x180033beb  mov     rax, [r9]
0x180033bee  mov     r8, rsi
0x180033bf1  mov     rdx, rdi
0x180033bf4  mov     rcx, r9
0x180033bf7  mov     rax, [rax+18h]
0x180033bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c00  mov     ebx, eax
0x180033c02  mov     eax, ebx
0x180033c04  add     rsp, 28h
0x180033c08  pop     rdi
0x180033c09  pop     rsi
0x180033c0a  pop     rbp
0x180033c0b  pop     rbx
0x180033c0c  retn
```
