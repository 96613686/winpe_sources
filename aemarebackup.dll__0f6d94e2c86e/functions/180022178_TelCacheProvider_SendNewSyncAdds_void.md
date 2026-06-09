# TelCacheProvider::SendNewSyncAdds(void)

- ea: `0x180022178`
- end: `0x18002232d`
- name: `?SendNewSyncAdds@TelCacheProvider@@AEAAXXZ`
- size: `437`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001459c`
- `0x18001efb4`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180014ed4`
- `0x18001b710`
- `0x180020440`
- `0x180021f2c`
- `0x180022178`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800222ff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800222ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800222f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800222f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800222df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800222df`

## string_xrefs

- `0x18002227b`: `InventoryCache::OpenItem(%ls) failed. [%#x]`
- `0x18002224c`: `TelCacheProvider::SendNewSyncAdds`

## pseudocode

```c
void __fastcall TelCacheProvider::SendNewSyncAdds(TelCacheProvider *this)
{
  __int64 v2; // rcx
  HANDLE *v3; // rdi
  struct IAmiInventoryItem *v4; // r14
  int Item; // eax
  const char *v6; // r9
  __int64 v7; // r8
  void (__fastcall *v8)(struct IAmiInventoryItem *, const unsigned __int16 *, __int64); // rbx
  const unsigned __int16 *SyncId; // rax
  __int64 v10; // rax
  char v11; // cl
  __int64 v12; // [rsp+28h] [rbp-240h]
  _BYTE v13[528]; // [rsp+30h] [rbp-238h] BYREF

  v2 = *((_QWORD *)this + 11);
  if ( !v2 || !*(_QWORD *)this || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 136LL))(v2) )
    return;
  if ( !*((_WORD *)this + 4) )
    TelCacheProvider::NewSyncId(this);
  v3 = (HANDLE *)((char *)this + 104);
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  v4 = *(struct IAmiInventoryItem **)this;
  memset_0(v13, 0, 0x208u);
  while ( (*(int (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 11) + 112LL))(
            *((_QWORD *)this + 11),
            v13,
            260) >= 0 )
  {
    Item = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)v4 + 16LL))(v4, v13);
    if ( Item < 0 )
    {
      v6 = "IAmiInventoryItem::SetItemKey(%ls) failed. [%#x]";
      v7 = 2242;
      goto LABEL_10;
    }
    Item = TelCacheProvider::GetItem(this, v4, 1);
    if ( Item >= 0 )
    {
      v8 = *(void (__fastcall **)(struct IAmiInventoryItem *, const unsigned __int16 *, __int64))(*(_QWORD *)v4 + 72LL);
      SyncId = TelCacheProvider::RetrieveSyncId(this);
      v8(v4, SyncId, 1);
    }
    else
    {
      v6 = "InventoryCache::OpenItem(%ls) failed. [%#x]";
      v7 = 2249;
LABEL_10:
      LODWORD(v12) = Item;
      AslLogCallPrintf(1, "TelCacheProvider::SendNewSyncAdds", v7, v6, v13, v12);
    }
  }
  if ( *((_BYTE *)this + 140) )
  {
    v10 = *((_QWORD *)this + 16);
    v11 = 0;
    if ( *(_DWORD *)(v10 + 4) == 1 )
    {
      *((_BYTE *)this + 140) = 0;
      v11 = 1;
    }
    --*(_DWORD *)(v10 + 4);
    if ( v11 )
LABEL_21:
      SetEvent(*((HANDLE *)this + 15));
  }
  else if ( !WaitForSingleObject(*v3, 0xFFFFFFFF) )
  {
    --**((_DWORD **)this + 16);
    --*((_DWORD *)this + 34);
    ReleaseMutex(*v3);
    goto LABEL_21;
  }
}

```

## disassembly

```asm
0x180022178  mov     [rsp+arg_8], rbx
0x18002217d  mov     [rsp+arg_10], rbp
0x180022182  push    rsi
0x180022183  push    rdi
0x180022184  push    r14
0x180022186  sub     rsp, 250h
0x18002218d  mov     rax, cs:__security_cookie
0x180022194  xor     rax, rsp
0x180022197  mov     [rsp+268h+var_28], rax
0x18002219f  mov     rsi, rcx
0x1800221a2  xor     ebp, ebp
0x1800221a4  mov     rcx, [rcx+58h]
0x1800221a8  test    rcx, rcx
0x1800221ab  jz      loc_180022305
0x1800221b1  cmp     [rsi], rbp
0x1800221b4  jz      loc_180022305
0x1800221ba  mov     rax, [rcx]
0x1800221bd  mov     rax, [rax+88h]
0x1800221c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221c9  test    eax, eax
0x1800221cb  jnz     loc_180022305
0x1800221d1  cmp     [rsi+8], bp
0x1800221d5  jnz     short loc_1800221DF
0x1800221d7  mov     rcx, rsi; this
0x1800221da  call    ?NewSyncId@TelCacheProvider@@AEAAXXZ; TelCacheProvider::NewSyncId(void)
0x1800221df  lea     rdi, [rsi+68h]
0x1800221e3  mov     rcx, rdi; this
0x1800221e6  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x1800221eb  mov     r14, [rsi]
0x1800221ee  lea     rcx, [rsp+268h+var_238]; void *
0x1800221f3  xor     edx, edx; Val
0x1800221f5  mov     r8d, 208h; Size
0x1800221fb  call    memset_0
0x180022200  mov     rcx, [rsi+58h]
0x180022204  lea     rdx, [rsp+268h+var_238]
0x180022209  mov     r8d, 104h
0x18002220f  mov     rax, [rcx]
0x180022212  mov     rax, [rax+70h]
0x180022216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002221b  test    eax, eax
0x18002221d  js      loc_1800222B2
0x180022223  mov     rax, [r14]
0x180022226  lea     rdx, [rsp+268h+var_238]
0x18002222b  mov     rcx, r14
0x18002222e  mov     rax, [rax+10h]
0x180022232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022237  test    eax, eax
0x180022239  jns     short loc_180022269
0x18002223b  lea     r9, aIamiinventoryi_0; "IAmiInventoryItem::SetItemKey(%ls) fail"...
0x180022242  mov     r8d, 8C2h
0x180022248  mov     dword ptr [rsp+268h+var_240], eax
0x18002224c  lea     rdx, aTelcacheprovid_6; "TelCacheProvider::SendNewSyncAdds"
0x180022253  lea     rax, [rsp+268h+var_238]
0x180022258  mov     ecx, 1
0x18002225d  mov     [rsp+268h+var_248], rax
0x180022262  call    AslLogCallPrintf
0x180022267  jmp     short loc_180022200
0x180022269  mov     r8b, 1; bool
0x18002226c  mov     rdx, r14; struct IAmiInventoryItem *
0x18002226f  mov     rcx, rsi; this
0x180022272  call    ?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z; TelCacheProvider::GetItem(IAmiInventoryItem *,bool)
0x180022277  test    eax, eax
0x180022279  jns     short loc_18002228A
0x18002227b  lea     r9, aInventorycache_1; "InventoryCache::OpenItem(%ls) failed. ["...
0x180022282  mov     r8d, 8C9h
0x180022288  jmp     short loc_180022248
0x18002228a  mov     rax, [r14]
0x18002228d  mov     rcx, rsi; this
0x180022290  mov     rbx, [rax+48h]
0x180022294  call    ?RetrieveSyncId@TelCacheProvider@@AEAAPEBGXZ; TelCacheProvider::RetrieveSyncId(void)
0x180022299  mov     rdx, rax
0x18002229c  mov     r8d, 1
0x1800222a2  mov     rax, rbx
0x1800222a5  mov     rcx, r14
0x1800222a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222ad  jmp     loc_180022200
0x1800222b2  cmp     [rdi+24h], bpl
0x1800222b6  jz      short loc_1800222D7
0x1800222b8  mov     rax, [rdi+18h]
0x1800222bc  mov     cl, bpl
0x1800222bf  cmp     dword ptr [rax+4], 1
0x1800222c3  jnz     short loc_1800222CB
0x1800222c5  mov     [rdi+24h], bpl
0x1800222c9  mov     cl, 1
0x1800222cb  or      ebx, 0FFFFFFFFh
0x1800222ce  add     [rax+4], ebx
0x1800222d1  test    cl, cl
0x1800222d3  jz      short loc_180022305
0x1800222d5  jmp     short loc_1800222FB
0x1800222d7  mov     rcx, [rdi]; hHandle
0x1800222da  or      ebx, 0FFFFFFFFh
0x1800222dd  mov     edx, ebx; dwMilliseconds
0x1800222df  call    cs:__imp_WaitForSingleObject
0x1800222e5  test    eax, eax
0x1800222e7  jnz     short loc_180022305
0x1800222e9  mov     rax, [rdi+18h]
0x1800222ed  add     [rax], ebx
0x1800222ef  add     [rdi+20h], ebx
0x1800222f2  mov     rcx, [rdi]; hMutex
0x1800222f5  call    cs:__imp_ReleaseMutex
0x1800222fb  mov     rcx, [rdi+10h]; hEvent
0x1800222ff  call    cs:__imp_SetEvent
0x180022305  mov     rcx, [rsp+268h+var_28]
0x18002230d  xor     rcx, rsp; StackCookie
0x180022310  call    __security_check_cookie
0x180022315  lea     r11, [rsp+268h+var_18]
0x18002231d  mov     rbx, [r11+28h]
0x180022321  mov     rbp, [r11+30h]
0x180022325  mov     rsp, r11
0x180022328  pop     r14
0x18002232a  pop     rdi
0x18002232b  pop     rsi
0x18002232c  retn
```
