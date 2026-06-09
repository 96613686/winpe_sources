# TelCacheProvider::SendNewSyncAdds(void)

- ea: `0x18002a1bc`
- end: `0x18002a432`
- name: `?SendNewSyncAdds@TelCacheProvider@@AEAAXXZ`
- size: `630`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020d94`
- `0x1800272dc`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x1800152d0`
- `0x180021384`
- `0x180021450`
- `0x180023d94`
- `0x180028794`
- `0x18002a1bc`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a396`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a400`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a396`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a400`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a38c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a3f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a38c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a3f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a374`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a3de`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a374`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a3de`

## string_xrefs

- `0x18002a2c9`: `InventoryCache::OpenItem(%ls) failed. [%#x]`
- `0x18002a29d`: `TelCacheProvider::SendNewSyncAdds`
- `0x18002a329`: `InventoryCache::GetMetadata failed [%#x]`
- `0x18002a33a`: `TelCacheProvider::RetrieveSyncId`

## pseudocode

```c
void __fastcall TelCacheProvider::SendNewSyncAdds(TelCacheProvider *this)
{
  __int64 v2; // rcx
  HANDLE *v3; // rbx
  struct IAmiInventoryItem *v4; // r14
  int Item; // eax
  const char *v6; // r9
  __int64 v7; // r8
  void (__fastcall *v8)(struct IAmiInventoryItem *, char *, __int64); // rbp
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  char v12; // cl
  __int64 v13; // rax
  char v14; // cl
  __int64 v15; // [rsp+28h] [rbp-260h]
  int v16[4]; // [rsp+30h] [rbp-258h] BYREF
  _BYTE v17[528]; // [rsp+40h] [rbp-248h] BYREF

  v2 = *((_QWORD *)this + 11);
  if ( !v2 || !*(_QWORD *)this || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 136LL))(v2) )
    return;
  if ( !*((_WORD *)this + 4) )
    TelCacheProvider::NewSyncId(this);
  v3 = (HANDLE *)((char *)this + 104);
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  v4 = *(struct IAmiInventoryItem **)this;
  memset_0(v17, 0, 0x208u);
  while ( (*(int (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 11) + 112LL))(
            *((_QWORD *)this + 11),
            v17,
            260) >= 0 )
  {
    Item = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)v4 + 16LL))(v4, v17);
    if ( Item < 0 )
    {
      v6 = "IAmiInventoryItem::SetItemKey(%ls) failed. [%#x]";
      v7 = 2242;
      goto LABEL_10;
    }
    Item = TelCacheProvider::GetItem(this, v4);
    if ( Item >= 0 )
    {
      v8 = *(void (__fastcall **)(struct IAmiInventoryItem *, char *, __int64))(*(_QWORD *)v4 + 72LL);
      Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
      if ( !*((_WORD *)this + 4) )
      {
        v9 = *((_QWORD *)this + 11);
        v16[0] = 39;
        v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, int *))(*(_QWORD *)v9 + 56LL))(
                v9,
                L"ProviderSyncId",
                (char *)this + 8,
                v16);
        if ( v10 == -2147024894 )
        {
          TelCacheProvider::NewSyncId(this);
        }
        else if ( v10 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::RetrieveSyncId", 1701, "InventoryCache::GetMetadata failed [%#x]", v10);
        }
      }
      if ( !*((_BYTE *)this + 140) )
      {
        if ( WaitForSingleObject(*v3, 0xFFFFFFFF) )
          goto LABEL_26;
        --**((_DWORD **)this + 16);
        --*((_DWORD *)this + 34);
        ReleaseMutex(*v3);
LABEL_25:
        SetEvent(*((HANDLE *)this + 15));
        goto LABEL_26;
      }
      v11 = *((_QWORD *)this + 16);
      v12 = 0;
      if ( *(_DWORD *)(v11 + 4) == 1 )
      {
        *((_BYTE *)this + 140) = 0;
        v12 = 1;
      }
      --*(_DWORD *)(v11 + 4);
      if ( v12 )
        goto LABEL_25;
LABEL_26:
      v8(v4, (char *)this + 8, 1);
    }
    else
    {
      v6 = "InventoryCache::OpenItem(%ls) failed. [%#x]";
      v7 = 2249;
LABEL_10:
      LODWORD(v15) = Item;
      AslLogCallPrintf(1, "TelCacheProvider::SendNewSyncAdds", v7, v6, v17, v15);
    }
  }
  if ( *((_BYTE *)this + 140) )
  {
    v13 = *((_QWORD *)this + 16);
    v14 = 0;
    if ( *(_DWORD *)(v13 + 4) == 1 )
    {
      *((_BYTE *)this + 140) = 0;
      v14 = 1;
    }
    --*(_DWORD *)(v13 + 4);
    if ( v14 )
LABEL_34:
      SetEvent(*((HANDLE *)this + 15));
  }
  else if ( !WaitForSingleObject(*v3, 0xFFFFFFFF) )
  {
    --**((_DWORD **)this + 16);
    --*((_DWORD *)this + 34);
    ReleaseMutex(*v3);
    goto LABEL_34;
  }
}

```

## disassembly

```asm
0x18002a1bc  mov     [rsp+arg_8], rbx
0x18002a1c1  mov     [rsp+arg_10], rbp
0x18002a1c6  push    rsi
0x18002a1c7  push    rdi
0x18002a1c8  push    r12
0x18002a1ca  push    r14
0x18002a1cc  push    r15
0x18002a1ce  sub     rsp, 260h
0x18002a1d5  mov     rax, cs:__security_cookie
0x18002a1dc  xor     rax, rsp
0x18002a1df  mov     [rsp+288h+var_38], rax
0x18002a1e7  mov     rdi, rcx
0x18002a1ea  xor     r15d, r15d
0x18002a1ed  mov     rcx, [rcx+58h]
0x18002a1f1  test    rcx, rcx
0x18002a1f4  jz      loc_18002A406
0x18002a1fa  cmp     [rdi], r15
0x18002a1fd  jz      loc_18002A406
0x18002a203  mov     rax, [rcx]
0x18002a206  mov     rax, [rax+88h]
0x18002a20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a212  test    eax, eax
0x18002a214  jnz     loc_18002A406
0x18002a21a  lea     rsi, [rdi+8]
0x18002a21e  cmp     [rsi], r15w
0x18002a222  jnz     short loc_18002A22C
0x18002a224  mov     rcx, rdi; this
0x18002a227  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x18002a22c  lea     rbx, [rdi+68h]
0x18002a230  mov     rcx, rbx; this
0x18002a233  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18002a238  mov     r14, [rdi]
0x18002a23b  lea     rcx, [rsp+288h+var_248]; void *
0x18002a240  xor     edx, edx; Val
0x18002a242  mov     r8d, 208h; Size
0x18002a248  call    memset_0
0x18002a24d  or      r12d, 0FFFFFFFFh
0x18002a251  mov     rcx, [rdi+58h]
0x18002a255  lea     rdx, [rsp+288h+var_248]
0x18002a25a  mov     r8d, 104h
0x18002a260  mov     rax, [rcx]
0x18002a263  mov     rax, [rax+70h]
0x18002a267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a26c  test    eax, eax
0x18002a26e  js      loc_18002A3B5
0x18002a274  mov     rax, [r14]
0x18002a277  lea     rdx, [rsp+288h+var_248]
0x18002a27c  mov     rcx, r14
0x18002a27f  mov     rax, [rax+10h]
0x18002a283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a288  test    eax, eax
0x18002a28a  jns     short loc_18002A2BA
0x18002a28c  lea     r9, aIamiinventoryi; "IAmiInventoryItem::SetItemKey(%ls) fail"...
0x18002a293  mov     r8d, 8C2h
0x18002a299  mov     dword ptr [rsp+288h+var_260], eax
0x18002a29d  lea     rdx, aTelcacheprovid_4; "TelCacheProvider::SendNewSyncAdds"
0x18002a2a4  lea     rax, [rsp+288h+var_248]
0x18002a2a9  mov     ecx, 1
0x18002a2ae  mov     [rsp+288h+var_268], rax
0x18002a2b3  call    AslLogCallPrintf
0x18002a2b8  jmp     short loc_18002A251
0x18002a2ba  mov     rdx, r14; struct IAmiInventoryItem *
0x18002a2bd  mov     rcx, rdi; this
0x18002a2c0  call    ?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z; TelCacheProvider::GetItem(IAmiInventoryItem *,bool)
0x18002a2c5  test    eax, eax
0x18002a2c7  jns     short loc_18002A2D8
0x18002a2c9  lea     r9, aInventorycache_1; "InventoryCache::OpenItem(%ls) failed. ["...
0x18002a2d0  mov     r8d, 8C9h
0x18002a2d6  jmp     short loc_18002A299
0x18002a2d8  mov     rax, [r14]
0x18002a2db  mov     rcx, rbx; this
0x18002a2de  mov     rbp, [rax+48h]
0x18002a2e2  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x18002a2e7  cmp     [rsi], r15w
0x18002a2eb  jnz     short loc_18002A34B
0x18002a2ed  mov     rcx, [rdi+58h]
0x18002a2f1  lea     r9, [rsp+288h+var_258]
0x18002a2f6  mov     [rsp+288h+var_258], 27h ; '''
0x18002a2fe  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x18002a305  mov     r8, rsi
0x18002a308  mov     rax, [rcx]
0x18002a30b  mov     rax, [rax+38h]
0x18002a30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a314  cmp     eax, 80070002h
0x18002a319  jnz     short loc_18002A325
0x18002a31b  mov     rcx, rdi; this
0x18002a31e  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x18002a323  jmp     short loc_18002A34B
0x18002a325  test    eax, eax
0x18002a327  jns     short loc_18002A34B
0x18002a329  lea     r9, aInventorycache_3; "InventoryCache::GetMetadata failed [%#x"...
0x18002a330  mov     dword ptr [rsp+288h+var_268], eax
0x18002a334  mov     r8d, 6A5h
0x18002a33a  lea     rdx, aTelcacheprovid_14; "TelCacheProvider::RetrieveSyncId"
0x18002a341  mov     ecx, 1
0x18002a346  call    AslLogCallPrintf
0x18002a34b  cmp     [rbx+24h], r15b
0x18002a34f  jz      short loc_18002A36E
0x18002a351  mov     rax, [rbx+18h]
0x18002a355  mov     cl, r15b
0x18002a358  cmp     dword ptr [rax+4], 1
0x18002a35c  jnz     short loc_18002A364
0x18002a35e  mov     [rbx+24h], r15b
0x18002a362  mov     cl, 1
0x18002a364  add     [rax+4], r12d
0x18002a368  test    cl, cl
0x18002a36a  jz      short loc_18002A39C
0x18002a36c  jmp     short loc_18002A392
0x18002a36e  mov     rcx, [rbx]; hHandle
0x18002a371  mov     edx, r12d; dwMilliseconds
0x18002a374  call    cs:__imp_WaitForSingleObject
0x18002a37a  test    eax, eax
0x18002a37c  jnz     short loc_18002A39C
0x18002a37e  mov     rax, [rbx+18h]
0x18002a382  add     [rax], r12d
0x18002a385  add     [rbx+20h], r12d
0x18002a389  mov     rcx, [rbx]; hMutex
0x18002a38c  call    cs:__imp_ReleaseMutex
0x18002a392  mov     rcx, [rbx+10h]; hEvent
0x18002a396  call    cs:__imp_SetEvent
0x18002a39c  mov     r8d, 1
0x18002a3a2  mov     rdx, rsi
0x18002a3a5  mov     rcx, r14
0x18002a3a8  mov     rax, rbp
0x18002a3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3b0  jmp     loc_18002A251
0x18002a3b5  cmp     [rbx+24h], r15b
0x18002a3b9  jz      short loc_18002A3D8
0x18002a3bb  mov     rax, [rbx+18h]
0x18002a3bf  mov     cl, r15b
0x18002a3c2  cmp     dword ptr [rax+4], 1
0x18002a3c6  jnz     short loc_18002A3CE
0x18002a3c8  mov     [rbx+24h], r15b
0x18002a3cc  mov     cl, 1
0x18002a3ce  add     [rax+4], r12d
0x18002a3d2  test    cl, cl
0x18002a3d4  jz      short loc_18002A406
0x18002a3d6  jmp     short loc_18002A3FC
0x18002a3d8  mov     rcx, [rbx]; hHandle
0x18002a3db  mov     edx, r12d; dwMilliseconds
0x18002a3de  call    cs:__imp_WaitForSingleObject
0x18002a3e4  test    eax, eax
0x18002a3e6  jnz     short loc_18002A406
0x18002a3e8  mov     rax, [rbx+18h]
0x18002a3ec  add     [rax], r12d
0x18002a3ef  add     [rbx+20h], r12d
0x18002a3f3  mov     rcx, [rbx]; hMutex
0x18002a3f6  call    cs:__imp_ReleaseMutex
0x18002a3fc  mov     rcx, [rbx+10h]; hEvent
0x18002a400  call    cs:__imp_SetEvent
0x18002a406  mov     rcx, [rsp+288h+var_38]
0x18002a40e  xor     rcx, rsp; StackCookie
0x18002a411  call    __security_check_cookie
0x18002a416  lea     r11, [rsp+288h+var_28]
0x18002a41e  mov     rbx, [r11+38h]
0x18002a422  mov     rbp, [r11+40h]
0x18002a426  mov     rsp, r11
0x18002a429  pop     r15
0x18002a42b  pop     r14
0x18002a42d  pop     r12
0x18002a42f  pop     rdi
0x18002a430  pop     rsi
0x18002a431  retn
```
