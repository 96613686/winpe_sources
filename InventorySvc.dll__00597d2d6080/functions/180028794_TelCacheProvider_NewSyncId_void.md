# TelCacheProvider::NewSyncId(void)

- ea: `0x180028794`
- end: `0x1800289a3`
- name: `?NewSyncId@TelCacheProvider@@AEAAXXZ`
- size: `527`
- prototype: `void __fastcall(TelCacheProvider *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002a1bc`

## callees

- `0x180002bf0`
- `0x1800152d0`
- `0x1800178ec`
- `0x180021384`
- `0x180028794`
- `0x18002c1a4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028986`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028986`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002897c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002897c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028966`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028966`
- `RPCRT4!UuidCreate` at `0x1800287e7`
- `RPCRT4!UuidCreate` at `0x1800287e7`

## string_xrefs

- `0x180028836`: `InventoryCache::SetMetadata failed [%#x]`
- `0x1800288ca`: `New syncId generated for a non-empty cache so forcing a full sync`
- `0x180028895`: `InventoryCache::GetItemCount failed [%#x]`
- `0x1800288a6`: `TelCacheProvider::NewSyncId`
- `0x1800288d7`: `TelCacheProvider::NewSyncId`
- `0x18002892a`: `TelCacheProvider::NewSyncId`
- `0x180028906`: `InventoryCache::BatchBegin failed [%#x]`

## pseudocode

```c
void __fastcall TelCacheProvider::NewSyncId(TelCacheProvider *this)
{
  char *v1; // rbx
  __int64 v3; // rdx
  int v4; // eax
  int v5; // eax
  __int64 v6; // r14
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rax
  char v13; // cl
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+20h] [rbp-58h]
  int v17; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  v1 = (char *)this + 104;
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((TelCacheProvider *)((char *)this + 104));
  if ( *(_QWORD *)this && *((_QWORD *)this + 11) )
  {
    Uuid = 0;
    *((_WORD *)this + 4) = 0;
    UuidCreate(&Uuid);
    v4 = AslGuidToString((char *)this + 8, v3, &Uuid);
    if ( v4 )
    {
      v14 = v4;
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1734, "AslGuidToString failed [%d]", v14);
      goto LABEL_16;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 11) + 80LL))(
           *((_QWORD *)this + 11),
           L"ProviderSyncId",
           (char *)this + 8);
    if ( v5 < 0 )
    {
      v15 = v5;
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1742, "InventoryCache::SetMetadata failed [%#x]", v15);
      goto LABEL_16;
    }
    v6 = *(_QWORD *)this;
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 136LL))(*((_QWORD *)this + 11)) )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v6 + 88LL))(v6, (char *)this + 8);
    v7 = *((_QWORD *)this + 11);
    v18 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 32LL))(v7, &v18);
    if ( v8 < 0 )
    {
      AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1757, "InventoryCache::GetItemCount failed [%#x]", v8);
LABEL_11:
      TelCacheProvider::ShouldForceFullSync(this, 0);
      goto LABEL_16;
    }
    if ( !v18 )
      goto LABEL_11;
    AslLogCallPrintf(
      3,
      "TelCacheProvider::NewSyncId",
      1767,
      "New syncId generated for a non-empty cache so forcing a full sync");
    v9 = *((_QWORD *)this + 11);
    LOBYTE(v10) = 1;
    *((_BYTE *)this + 97) = 1;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 104LL))(v9, v10);
    if ( v11 >= 0 )
      goto LABEL_11;
    v16 = v11;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1773, "InventoryCache::BatchBegin failed [%#x]", v16);
  }
  else
  {
    v17 = -2147024809;
    AslLogCallPrintf(1, "TelCacheProvider::NewSyncId", 1719, "Object not yet initialized. [%#x]", v17);
  }
LABEL_16:
  if ( !v1[36] )
  {
    if ( WaitForSingleObject(*(HANDLE *)v1, 0xFFFFFFFF) )
      return;
    --**((_DWORD **)v1 + 3);
    --*((_DWORD *)v1 + 8);
    ReleaseMutex(*(HANDLE *)v1);
    goto LABEL_23;
  }
  v12 = *((_QWORD *)v1 + 3);
  v13 = 0;
  if ( *(_DWORD *)(v12 + 4) == 1 )
  {
    v1[36] = 0;
    v13 = 1;
  }
  --*(_DWORD *)(v12 + 4);
  if ( v13 )
LABEL_23:
    SetEvent(*((HANDLE *)v1 + 2));
}

```

## disassembly

```asm
0x180028794  push    rbx
0x180028796  push    rsi
0x180028797  push    rdi
0x180028798  push    r14
0x18002879a  sub     rsp, 58h
0x18002879e  mov     rax, cs:__security_cookie
0x1800287a5  xor     rax, rsp
0x1800287a8  mov     [rsp+78h+var_30], rax
0x1800287ad  lea     rbx, [rcx+68h]
0x1800287b1  mov     rdi, rcx
0x1800287b4  mov     rcx, rbx; this
0x1800287b7  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x1800287bc  cmp     qword ptr [rdi], 0
0x1800287c0  jz      loc_180028915
0x1800287c6  cmp     qword ptr [rdi+58h], 0
0x1800287cb  jz      loc_180028915
0x1800287d1  xorps   xmm0, xmm0
0x1800287d4  lea     rsi, [rdi+8]
0x1800287d8  xor     eax, eax
0x1800287da  lea     rcx, [rsp+78h+Uuid]; Uuid
0x1800287df  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x1800287e4  mov     [rsi], ax
0x1800287e7  call    cs:__imp_UuidCreate
0x1800287ed  lea     r8, [rsp+78h+Uuid]
0x1800287f2  mov     rcx, rsi
0x1800287f5  call    AslGuidToString
0x1800287fa  test    eax, eax
0x1800287fc  jz      short loc_180028814
0x1800287fe  mov     [rsp+78h+var_58], eax
0x180028802  lea     r9, aAslguidtostrin; "AslGuidToString failed [%d]"
0x180028809  mov     r8d, 6C6h
0x18002880f  jmp     loc_18002892A
0x180028814  mov     rcx, [rdi+58h]
0x180028818  lea     rdx, aProvidersyncid; "ProviderSyncId"
0x18002881f  mov     r8, rsi
0x180028822  mov     rax, [rcx]
0x180028825  mov     rax, [rax+50h]
0x180028829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882e  test    eax, eax
0x180028830  jns     short loc_180028848
0x180028832  mov     [rsp+78h+var_58], eax
0x180028836  lea     r9, aInventorycache_4; "InventoryCache::SetMetadata failed [%#x"...
0x18002883d  mov     r8d, 6CEh
0x180028843  jmp     loc_18002892A
0x180028848  mov     rcx, [rdi+58h]
0x18002884c  mov     r14, [rdi]
0x18002884f  mov     rax, [rcx]
0x180028852  mov     rax, [rax+88h]
0x180028859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002885e  test    eax, eax
0x180028860  jnz     short loc_180028874
0x180028862  mov     rax, [r14]
0x180028865  mov     rdx, rsi
0x180028868  mov     rcx, r14
0x18002886b  mov     rax, [rax+58h]
0x18002886f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028874  mov     rcx, [rdi+58h]
0x180028878  lea     rdx, [rsp+78h+var_48]
0x18002887d  mov     [rsp+78h+var_48], 0
0x180028885  mov     rax, [rcx]
0x180028888  mov     rax, [rax+20h]
0x18002888c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028891  test    eax, eax
0x180028893  jns     short loc_1800288C3
0x180028895  lea     r9, aInventorycache_2; "InventoryCache::GetItemCount failed [%#"...
0x18002889c  mov     [rsp+78h+var_58], eax
0x1800288a0  mov     r8d, 6DDh
0x1800288a6  lea     rdx, aTelcacheprovid_7; "TelCacheProvider::NewSyncId"
0x1800288ad  mov     ecx, 1
0x1800288b2  call    AslLogCallPrintf
0x1800288b7  xor     edx, edx; unsigned __int16 *
0x1800288b9  mov     rcx, rdi; this
0x1800288bc  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x1800288c1  jmp     short loc_18002893B
0x1800288c3  cmp     [rsp+78h+var_48], 0
0x1800288c8  jbe     short loc_1800288B7
0x1800288ca  lea     r9, aNewSyncidGener; "New syncId generated for a non-empty ca"...
0x1800288d1  mov     r8d, 6E7h
0x1800288d7  lea     rdx, aTelcacheprovid_7; "TelCacheProvider::NewSyncId"
0x1800288de  mov     ecx, 3
0x1800288e3  call    AslLogCallPrintf
0x1800288e8  mov     rcx, [rdi+58h]
0x1800288ec  mov     dl, 1
0x1800288ee  mov     byte ptr [rdi+61h], 1
0x1800288f2  mov     rax, [rcx]
0x1800288f5  mov     rax, [rax+68h]
0x1800288f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288fe  test    eax, eax
0x180028900  jns     short loc_1800288B7
0x180028902  mov     [rsp+78h+var_58], eax
0x180028906  lea     r9, aInventorycache_5; "InventoryCache::BatchBegin failed [%#x]"
0x18002890d  mov     r8d, 6EDh
0x180028913  jmp     short loc_18002892A
0x180028915  mov     [rsp+78h+var_58], 80070057h
0x18002891d  lea     r9, aObjectNotYetIn; "Object not yet initialized. [%#x]"
0x180028924  mov     r8d, 6B7h
0x18002892a  lea     rdx, aTelcacheprovid_7; "TelCacheProvider::NewSyncId"
0x180028931  mov     ecx, 1
0x180028936  call    AslLogCallPrintf
0x18002893b  cmp     byte ptr [rbx+24h], 0
0x18002893f  jz      short loc_18002895E
0x180028941  mov     rax, [rbx+18h]
0x180028945  xor     cl, cl
0x180028947  cmp     dword ptr [rax+4], 1
0x18002894b  jnz     short loc_180028952
0x18002894d  mov     [rbx+24h], cl
0x180028950  mov     cl, 1
0x180028952  or      edi, 0FFFFFFFFh
0x180028955  add     [rax+4], edi
0x180028958  test    cl, cl
0x18002895a  jz      short loc_18002898C
0x18002895c  jmp     short loc_180028982
0x18002895e  mov     rcx, [rbx]; hHandle
0x180028961  or      edi, 0FFFFFFFFh
0x180028964  mov     edx, edi; dwMilliseconds
0x180028966  call    cs:__imp_WaitForSingleObject
0x18002896c  test    eax, eax
0x18002896e  jnz     short loc_18002898C
0x180028970  mov     rax, [rbx+18h]
0x180028974  add     [rax], edi
0x180028976  add     [rbx+20h], edi
0x180028979  mov     rcx, [rbx]; hMutex
0x18002897c  call    cs:__imp_ReleaseMutex
0x180028982  mov     rcx, [rbx+10h]; hEvent
0x180028986  call    cs:__imp_SetEvent
0x18002898c  mov     rcx, [rsp+78h+var_30]
0x180028991  xor     rcx, rsp; StackCookie
0x180028994  call    __security_check_cookie
0x180028999  add     rsp, 58h
0x18002899d  pop     r14
0x18002899f  pop     rdi
0x1800289a0  pop     rsi
0x1800289a1  pop     rbx
0x1800289a2  retn
```
