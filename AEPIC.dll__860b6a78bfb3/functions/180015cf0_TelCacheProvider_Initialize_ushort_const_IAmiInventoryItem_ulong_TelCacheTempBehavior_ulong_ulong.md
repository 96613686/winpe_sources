# TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)

- ea: `0x180015cf0`
- end: `0x180016329`
- name: `?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z`
- size: `1593`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18000f7cc`
- `0x1800108f8`
- `0x18001f378`
- `0x180021990`
- `0x1800c8770`
- `0x1800d31f0`

## callees

- `0x180005d6c`
- `0x18000d914`
- `0x18000fe40`
- `0x180010d28`
- `0x180015320`
- `0x180015398`
- `0x180015450`
- `0x180015678`
- `0x1800159ec`
- `0x180015cf0`
- `0x1800179fc`
- `0x18001a994`
- `0x18001aa44`
- `0x18001bbfc`
- `0x18001c5ac`
- `0x1800295dc`
- `0x1800eb010`

## string_xrefs

- `0x180015d6f`: `Already initialized [%#x]`
- `0x180015fb7`: `ItemTemplate is null or has no schema for SQLite cache provider [%#x]`
- `0x180015e4d`: `AepicInvCache::Initialize failed [%#x]`
- `0x180015e7b`: `TelCacheProvider::GetVersion failed [%#x]`
- `0x180015eb8`: `TelCacheProvider::SetVersion [%#x]`
- `0x180015fce`: `Using SQLite cache provider: %ls.`
- `0x180016201`: `Using SQLite cache provider: %ls.`
- `0x18001609b`: `SqliteInvCache::Initialize failed [%#x]`
- `0x180016283`: `SqliteInvCache::Initialize failed [%#x]`
- `0x180016171`: `RtlArrayCache::Initialize failed [%#x]`
- `0x180016192`: `Using in-memory cache provider: %ls.`
- `0x180015d4a`: `TelCacheProvider::Initialize`
- `0x180015e58`: `TelCacheProvider::Initialize`
- `0x180015e8c`: `TelCacheProvider::Initialize`
- `0x180015eed`: `TelCacheProvider::Initialize`
- `0x180015fa1`: `TelCacheProvider::Initialize`
- `0x1800160a8`: `TelCacheProvider::Initialize`
- `0x180016162`: `TelCacheProvider::Initialize`
- `0x18001620e`: `TelCacheProvider::Initialize`
- `0x180016290`: `TelCacheProvider::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TelCacheProvider::Initialize(
        _QWORD *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        unsigned int a7)
{
  int v9; // esi
  Windows::Compat::Inventory::RtlArrayCache *v10; // r14
  Windows::Compat::Inventory::SqliteInvCache *v11; // r12
  int v12; // eax
  int v13; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  Windows::Compat::Inventory::InventorySynchronization *v16; // r13
  char v17; // bl
  Windows::Compat::Inventory::SqliteInvCache *v18; // rsi
  int v19; // eax
  TelCacheProvider *v20; // rcx
  char v21; // si
  __int64 v22; // rcx
  __int64 v23; // r8
  int Version; // eax
  TelCacheProvider *v25; // rcx
  const char *v26; // r9
  __int64 v27; // r8
  unsigned int v28; // eax
  _QWORD *v29; // rax
  Windows::Compat::Inventory::SqliteInvCache *v30; // rax
  Windows::Compat::Inventory::SqliteInvCache *v31; // rsi
  int v32; // eax
  bool v33; // bl
  int v34; // eax
  _QWORD *v35; // rax
  char v36; // dl
  Windows::Compat::Inventory::SqliteInvCache *v37; // rax
  Windows::Compat::Inventory::SqliteInvCache *v38; // rbx
  int v39; // eax
  int v41; // [rsp+20h] [rbp-30h]
  unsigned int v42; // [rsp+20h] [rbp-30h]
  unsigned int v43; // [rsp+20h] [rbp-30h]
  _BYTE v44[32]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v45; // [rsp+90h] [rbp+40h] BYREF
  Windows::Compat::Inventory::SqliteInvCache *v46; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v47; // [rsp+A8h] [rbp+58h]

  v9 = 0;
  v47 = 0;
  v45 = 0;
  v10 = 0;
  v11 = 0;
  *a1 = a3;
  *((_WORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 48) = 0;
  if ( a2 )
  {
    if ( a1[11] )
    {
      v13 = -2147418113;
      v41 = -2147418113;
      v14 = "Already initialized [%#x]";
      v15 = 582;
      goto LABEL_4;
    }
    v16 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
    v12 = Windows::Compat::Inventory::InventorySynchronization::Initialize(
            (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13),
            a2);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = "InventorySynchronization:Initialize [%#x]";
      v15 = 589;
      goto LABEL_3;
    }
    v17 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      if ( !*a1
        || (v29 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v44),
            v9 = 1,
            v47 = 1,
            *v29 == v29[1]) )
      {
        v17 = 1;
      }
      if ( (v9 & 1) != 0 )
      {
        v47 = v9 & 0xFFFFFFFE;
        std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v44);
      }
      if ( v17 )
      {
        v13 = -2147024809;
        AslLogCallPrintf(
          1,
          "TelCacheProvider::Initialize",
          600,
          "ItemTemplate is null or has no schema for SQLite cache provider [%#x]",
          -2147024809);
        goto LABEL_86;
      }
      AslLogCallPrintf(3, "TelCacheProvider::Initialize", 605, "Using SQLite cache provider: %ls.", a2);
      v30 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                            0xF0u,
                                                            (const struct std::nothrow_t *)std::nothrow);
      v46 = v30;
      if ( v30 )
        v31 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v30);
      else
        v31 = 0;
      if ( v31 )
      {
        Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
        v32 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v31, a2, (struct IAmiInventoryItem *)*a1, 0, v42);
        v13 = v32;
        if ( v32 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 638, "SqliteInvCache::Initialize failed [%#x]", v32);
          (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v31)(v31, 1);
        }
        else
        {
          a1[11] = v31;
          LODWORD(v46) = 0;
          if ( *a1
            && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
            && (*(int (__fastcall **)(_QWORD, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)a1[11] + 32LL))(
                 a1[11],
                 &v46) >= 0
            && (_DWORD)v46
            && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
          {
            *((_BYTE *)a1 + 97) = 1;
          }
        }
        v21 = 0;
        v11 = 0;
        goto LABEL_58;
      }
    }
    else
    {
      v18 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                            0x20u,
                                                            (const struct std::nothrow_t *)std::nothrow);
      v46 = v18;
      if ( v18 )
      {
        *(_QWORD *)v18 = &Windows::Compat::Inventory::AepicInvCache::`vftable';
        *((_QWORD *)v18 + 1) = 0;
        *((_QWORD *)v18 + 2) = 0;
        *((_BYTE *)v18 + 24) = 0;
        Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
        v19 = Windows::Compat::Inventory::AepicInvCache::Initialize(v18, a2, a6, a7);
        v13 = v19;
        if ( v19 < 0 )
        {
          v21 = 1;
          if ( v19 == -2147467262 || v19 == -2147024891 || v19 == -2147024864 || v19 == -2147023582 )
          {
            v22 = 3;
            v23 = 665;
          }
          else
          {
            v22 = 1;
            v23 = 669;
          }
          AslLogCallPrintf(v22, "TelCacheProvider::Initialize", v23, "AepicInvCache::Initialize failed [%#x]", v19);
LABEL_59:
          if ( a5 == 3 )
          {
LABEL_82:
            if ( !v21 )
              goto LABEL_85;
            v16 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
LABEL_84:
            Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(v16);
LABEL_85:
            if ( v13 >= 0 )
              goto LABEL_87;
            goto LABEL_86;
          }
LABEL_60:
          v33 = 0;
          if ( a1[11] )
            goto LABEL_81;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
          {
            if ( *a1 )
            {
              v35 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v44);
              v36 = v47 | 2;
              v33 = *v35 != v35[1];
            }
            else
            {
              v36 = v47;
            }
            if ( (v36 & 2) != 0 )
              std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v44);
            if ( !v33 )
              goto LABEL_81;
            AslLogCallPrintf(3, "TelCacheProvider::Initialize", 745, "Using SQLite cache provider: %ls.", a2);
            v37 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                                  0xF0u,
                                                                  (const struct std::nothrow_t *)std::nothrow);
            v46 = v37;
            if ( v37 )
              v38 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v37);
            else
              v38 = 0;
            if ( v38 )
            {
              Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
              v39 = Windows::Compat::Inventory::SqliteInvCache::Initialize(
                      v38,
                      a2,
                      (struct IAmiInventoryItem *)*a1,
                      1,
                      v43);
              if ( v39 < 0 )
              {
                AslLogCallPrintf(1, "TelCacheProvider::Initialize", 763, "SqliteInvCache::Initialize failed [%#x]", v39);
                (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v38)(v38, 1);
                Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
                v21 = 0;
              }
              else
              {
                v21 = 1;
                a1[11] = v38;
              }
              goto LABEL_81;
            }
          }
          else
          {
            v10 = (Windows::Compat::Inventory::RtlArrayCache *)operator new(
                                                                 0x38u,
                                                                 (const struct std::nothrow_t *)std::nothrow);
            v46 = v10;
            if ( v10 )
            {
              *(_QWORD *)v10 = &Windows::Compat::Inventory::RtlArrayCache::`vftable';
              *((_QWORD *)v10 + 1) = 0;
              *((_QWORD *)v10 + 2) = 0;
              *((_QWORD *)v10 + 3) = 0;
              *((_QWORD *)v10 + 4) = 0;
              *((_QWORD *)v10 + 5) = 0;
              *((_QWORD *)v10 + 6) = 0;
              v34 = Windows::Compat::Inventory::RtlArrayCache::Initialize(v10, a2);
              v13 = v34;
              if ( v34 < 0 )
              {
                AslLogCallPrintf(1, "TelCacheProvider::Initialize", 783, "RtlArrayCache::Initialize failed [%#x]", v34);
                goto LABEL_82;
              }
              AslLogCallPrintf(3, "TelCacheProvider::Initialize", 787, "Using in-memory cache provider: %ls.", a2);
              a1[11] = v10;
LABEL_81:
              v13 = 0;
              v10 = 0;
              goto LABEL_82;
            }
            v10 = 0;
          }
          v13 = -2147024882;
          goto LABEL_82;
        }
        Version = TelCacheProvider::GetVersion(v20, v18, &v45);
        v13 = Version;
        if ( Version < 0 )
        {
          v26 = "TelCacheProvider::GetVersion failed [%#x]";
          v27 = 684;
LABEL_21:
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", v27, v26, Version);
          v11 = v18;
          goto LABEL_84;
        }
        if ( Version )
        {
          Version = TelCacheProvider::SetVersion(v25, v18, 0);
          v13 = Version;
          if ( Version < 0 )
          {
            v26 = "TelCacheProvider::SetVersion [%#x]";
            v27 = 694;
            goto LABEL_21;
          }
          v28 = 0;
          v45 = 0;
        }
        else
        {
          v28 = v45;
        }
        if ( v28 )
        {
          AslLogCallPrintf(
            3,
            "TelCacheProvider::Initialize",
            702,
            "%ls ProviderVersion did not match RequestedVersion.",
            a2);
          v13 = -2147467262;
          v11 = v18;
        }
        else
        {
          a1[11] = v18;
          LODWORD(v46) = 0;
          if ( *a1
            && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
            && (*(int (__fastcall **)(_QWORD, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)a1[11] + 32LL))(
                 a1[11],
                 &v46) >= 0
            && (_DWORD)v46
            && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
          {
            *((_BYTE *)a1 + 97) = 1;
          }
          v13 = 0;
        }
        v21 = 0;
LABEL_58:
        Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
        if ( v13 >= 0 )
          goto LABEL_60;
        goto LABEL_59;
      }
    }
    v13 = -2147024882;
    goto LABEL_86;
  }
  v12 = -2147024809;
  v13 = -2147024809;
  v14 = "ProviderName argument is null [%#x]";
  v15 = 575;
LABEL_3:
  v41 = v12;
LABEL_4:
  AslLogCallPrintf(1, "TelCacheProvider::Initialize", v15, v14, v41);
LABEL_86:
  TelCacheProvider::Uninitialize((TelCacheProvider *)a1);
LABEL_87:
  if ( v11 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v11)(v11, 1);
  if ( v10 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::RtlArrayCache *, __int64))v10)(v10, 1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180015cf0  mov     [rsp-38h+arg_10], rbx
0x180015cf5  mov     [rsp-38h+arg_18], r9d
0x180015cfa  push    rbp
0x180015cfb  push    rsi
0x180015cfc  push    rdi
0x180015cfd  push    r12
0x180015cff  push    r13
0x180015d01  push    r14
0x180015d03  push    r15
0x180015d05  mov     rbp, rsp
0x180015d08  sub     rsp, 50h
0x180015d0c  mov     r15, rdx
0x180015d0f  mov     rdi, rcx
0x180015d12  xor     esi, esi
0x180015d14  mov     [rbp+arg_18], esi
0x180015d17  mov     [rbp+arg_0], esi
0x180015d1a  xor     r14d, r14d
0x180015d1d  xor     r12d, r12d
0x180015d20  mov     [rcx], r8
0x180015d23  xor     eax, eax
0x180015d25  mov     [rcx+8], ax
0x180015d29  mov     [rcx+60h], ax
0x180015d2d  test    rdx, rdx
0x180015d30  jnz     short loc_180015D60
0x180015d32  mov     eax, 80070057h
0x180015d37  mov     ebx, eax
0x180015d39  lea     r9, aProvidernameAr; "ProviderName argument is null [%#x]"
0x180015d40  mov     r8d, 23Fh
0x180015d46  mov     [rsp+50h+var_30], eax
0x180015d4a  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x180015d51  mov     ecx, 1
0x180015d56  call    AslLogCallPrintf
0x180015d5b  jmp     loc_1800162D6
0x180015d60  cmp     [rcx+58h], rax
0x180015d64  jz      short loc_180015D7E
0x180015d66  mov     ebx, 8000FFFFh
0x180015d6b  mov     [rsp+50h+var_30], ebx
0x180015d6f  lea     r9, aAlreadyInitial; "Already initialized [%#x]"
0x180015d76  mov     r8d, 246h
0x180015d7c  jmp     short loc_180015D4A
0x180015d7e  lea     r13, [rcx+68h]
0x180015d82  mov     rcx, r13; this
0x180015d85  call    ?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)
0x180015d8a  mov     ebx, eax
0x180015d8c  test    eax, eax
0x180015d8e  jns     short loc_180015D9F
0x180015d90  lea     r9, aInventorysynch_2; "InventorySynchronization:Initialize [%#"...
0x180015d97  mov     r8d, 24Dh
0x180015d9d  jmp     short loc_180015D46
0x180015d9f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180015da6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180015dab  xor     ebx, ebx
0x180015dad  test    al, al
0x180015daf  jnz     loc_180015F61
0x180015db5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015dbc  lea     ecx, [rbx+20h]; unsigned __int64
0x180015dbf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015dc4  mov     rsi, rax
0x180015dc7  mov     [rbp+arg_8], rax
0x180015dcb  test    rax, rax
0x180015dce  jz      loc_180016017
0x180015dd4  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x180015ddb  mov     [rsi], rax
0x180015dde  mov     [rsi+8], rbx
0x180015de2  mov     [rsi+10h], rbx
0x180015de6  mov     [rsi+18h], bl
0x180015de9  test    rsi, rsi
0x180015dec  jz      loc_180016017
0x180015df2  mov     rcx, r13; this
0x180015df5  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180015dfa  mov     r9d, [rbp+arg_30]; unsigned int
0x180015dfe  mov     r8d, [rbp+arg_28]; unsigned int
0x180015e02  mov     rdx, r15; unsigned __int16 *
0x180015e05  mov     rcx, rsi; this
0x180015e08  call    ?Initialize@AepicInvCache@Inventory@Compat@Windows@@QEAAJPEBGKK@Z; Windows::Compat::Inventory::AepicInvCache::Initialize(ushort const *,ulong,ulong)
0x180015e0d  mov     ebx, eax
0x180015e0f  test    eax, eax
0x180015e11  jns     short loc_180015E69
0x180015e13  mov     sil, 1
0x180015e16  mov     r13d, 3
0x180015e1c  cmp     eax, 80004002h
0x180015e21  jz      short loc_180015E44
0x180015e23  cmp     eax, 80070005h
0x180015e28  jz      short loc_180015E44
0x180015e2a  cmp     eax, 80070020h
0x180015e2f  jz      short loc_180015E44
0x180015e31  cmp     eax, 80070522h
0x180015e36  jz      short loc_180015E44
0x180015e38  lea     ecx, [r13-2]
0x180015e3c  mov     r8d, 29Dh
0x180015e42  jmp     short loc_180015E4D
0x180015e44  mov     ecx, r13d
0x180015e47  mov     r8d, 299h
0x180015e4d  lea     r9, aAepicinvcacheI; "AepicInvCache::Initialize failed [%#x]"
0x180015e54  mov     [rsp+50h+var_30], eax
0x180015e58  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x180015e5f  call    AslLogCallPrintf
0x180015e64  jmp     loc_1800160E1
0x180015e69  lea     r8, [rbp+arg_0]; unsigned int *
0x180015e6d  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x180015e70  call    ?GetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@AEAK@Z; TelCacheProvider::GetVersion(Windows::Compat::Inventory::InventoryCache *,ulong &)
0x180015e75  mov     ebx, eax
0x180015e77  test    eax, eax
0x180015e79  jns     short loc_180015EA5
0x180015e7b  lea     r9, aTelcacheprovid_10; "TelCacheProvider::GetVersion failed [%#"...
0x180015e82  mov     r8d, 2ACh
0x180015e88  mov     [rsp+50h+var_30], eax
0x180015e8c  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x180015e93  mov     ecx, 1
0x180015e98  call    AslLogCallPrintf
0x180015e9d  mov     r12, rsi
0x180015ea0  jmp     loc_1800162CA
0x180015ea5  jz      short loc_180015ECE
0x180015ea7  xor     r8d, r8d; unsigned int
0x180015eaa  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x180015ead  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x180015eb2  mov     ebx, eax
0x180015eb4  test    eax, eax
0x180015eb6  jns     short loc_180015EC7
0x180015eb8  lea     r9, aTelcacheprovid_17; "TelCacheProvider::SetVersion [%#x]"
0x180015ebf  mov     r8d, 2B6h
0x180015ec5  jmp     short loc_180015E88
0x180015ec7  xor     eax, eax
0x180015ec9  mov     [rbp+arg_0], eax
0x180015ecc  jmp     short loc_180015ED1
0x180015ece  mov     eax, [rbp+arg_0]
0x180015ed1  mov     r13d, 3
0x180015ed7  test    eax, eax
0x180015ed9  jz      short loc_180015F06
0x180015edb  mov     qword ptr [rsp+50h+var_30], r15
0x180015ee0  lea     r9, aLsProvidervers; "%ls ProviderVersion did not match Reque"...
0x180015ee7  mov     r8d, 2BEh
0x180015eed  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x180015ef4  mov     ecx, r13d
0x180015ef7  call    AslLogCallPrintf
0x180015efc  mov     ebx, 80004002h
0x180015f01  mov     r12, rsi
0x180015f04  jmp     short loc_180015F59
0x180015f06  mov     [rdi+58h], rsi
0x180015f0a  mov     dword ptr [rbp+arg_8], r12d
0x180015f0e  mov     rcx, [rdi]
0x180015f11  test    rcx, rcx
0x180015f14  jz      short loc_180015F57
0x180015f16  mov     rax, [rcx]
0x180015f19  mov     rax, [rax+38h]
0x180015f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f22  test    al, al
0x180015f24  jz      short loc_180015F57
0x180015f26  mov     rcx, [rdi+58h]
0x180015f2a  mov     rax, [rcx]
0x180015f2d  lea     rdx, [rbp+arg_8]
0x180015f31  mov     rax, [rax+20h]
0x180015f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f3a  test    eax, eax
0x180015f3c  js      short loc_180015F57
0x180015f3e  cmp     dword ptr [rbp+arg_8], r12d
0x180015f42  jbe     short loc_180015F57
0x180015f44  mov     rdx, r15; unsigned __int16 *
0x180015f47  mov     rcx, rdi; this
0x180015f4a  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x180015f4f  test    eax, eax
0x180015f51  jz      short loc_180015F57
0x180015f53  mov     byte ptr [rdi+61h], 1
0x180015f57  xor     ebx, ebx
0x180015f59  xor     sil, sil
0x180015f5c  jmp     loc_1800160D4
0x180015f61  mov     rcx, [rdi]
0x180015f64  test    rcx, rcx
0x180015f67  jz      short loc_180015F8A
0x180015f69  mov     rax, [rcx]
0x180015f6c  lea     rdx, [rbp+var_20]
0x180015f70  mov     rax, [rax+40h]
0x180015f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f79  mov     esi, 1
0x180015f7e  mov     [rbp+arg_18], esi
0x180015f81  mov     rcx, [rax+8]
0x180015f85  cmp     [rax], rcx
0x180015f88  jnz     short loc_180015F8C
0x180015f8a  mov     bl, 1
0x180015f8c  test    sil, 1
0x180015f90  jz      short loc_180015FA1
0x180015f92  and     esi, 0FFFFFFFEh
0x180015f95  mov     [rbp+arg_18], esi
0x180015f98  lea     rcx, [rbp+var_20]
0x180015f9c  call    ?_Tidy@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXXZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(void)
0x180015fa1  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x180015fa8  test    bl, bl
0x180015faa  jz      short loc_180015FC9
0x180015fac  mov     eax, 80070057h
0x180015fb1  mov     ebx, eax
0x180015fb3  mov     [rsp+50h+var_30], eax
0x180015fb7  lea     r9, aItemtemplateIs; "ItemTemplate is null or has no schema f"...
0x180015fbe  mov     r8d, 258h
0x180015fc4  jmp     loc_180015D51
0x180015fc9  mov     qword ptr [rsp+50h+var_30], r15; unsigned int
0x180015fce  lea     r9, aUsingSqliteCac; "Using SQLite cache provider: %ls."
0x180015fd5  mov     r8d, 25Dh
0x180015fdb  mov     r13d, 3
0x180015fe1  mov     ecx, r13d
0x180015fe4  call    AslLogCallPrintf
0x180015fe9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015ff0  mov     ecx, 0F0h; unsigned __int64
0x180015ff5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015ffa  mov     [rbp+arg_8], rax
0x180015ffe  test    rax, rax
0x180016001  jz      short loc_180016010
0x180016003  mov     rcx, rax; this
0x180016006  call    ??0SqliteInvCache@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(void)
0x18001600b  mov     rsi, rax
0x18001600e  jmp     short loc_180016012
0x180016010  xor     esi, esi
0x180016012  test    rsi, rsi
0x180016015  jnz     short loc_180016021
0x180016017  mov     ebx, 8007000Eh
0x18001601c  jmp     loc_1800162D6
0x180016021  lea     rcx, [rdi+68h]; this
0x180016025  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18001602a  xor     r9d, r9d; int
0x18001602d  mov     r8, [rdi]; struct IAmiInventoryItem *
0x180016030  mov     rdx, r15; unsigned __int16 *
0x180016033  mov     rcx, rsi; this
0x180016036  call    ?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z; Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)
0x18001603b  mov     ebx, eax
0x18001603d  test    eax, eax
0x18001603f  js      short loc_180016097
0x180016041  mov     [rdi+58h], rsi
0x180016045  mov     dword ptr [rbp+arg_8], 0
0x18001604c  mov     rcx, [rdi]
0x18001604f  test    rcx, rcx
0x180016052  jz      short loc_1800160CE
0x180016054  mov     rax, [rcx]
0x180016057  mov     rax, [rax+38h]
0x18001605b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016060  test    al, al
0x180016062  jz      short loc_1800160CE
0x180016064  mov     rcx, [rdi+58h]
0x180016068  mov     rax, [rcx]
0x18001606b  lea     rdx, [rbp+arg_8]
0x18001606f  mov     rax, [rax+20h]
0x180016073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016078  test    eax, eax
0x18001607a  js      short loc_1800160CE
0x18001607c  cmp     dword ptr [rbp+arg_8], 0
0x180016080  jbe     short loc_1800160CE
0x180016082  mov     rdx, r15; unsigned __int16 *
0x180016085  mov     rcx, rdi; this
0x180016088  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18001608d  test    eax, eax
0x18001608f  jz      short loc_1800160CE
0x180016091  mov     byte ptr [rdi+61h], 1
0x180016095  jmp     short loc_1800160CE
0x180016097  mov     [rsp+50h+var_30], eax
0x18001609b  lea     r9, aSqliteinvcache; "SqliteInvCache::Initialize failed [%#x]"
0x1800160a2  mov     r8d, 27Eh
0x1800160a8  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x1800160af  mov     r12d, 1
0x1800160b5  mov     ecx, r12d
0x1800160b8  call    AslLogCallPrintf
0x1800160bd  mov     rax, [rsi]
0x1800160c0  mov     edx, r12d
0x1800160c3  mov     rcx, rsi
0x1800160c6  mov     rax, [rax]
0x1800160c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ce  xor     sil, sil
0x1800160d1  xor     r12d, r12d
0x1800160d4  lea     rcx, [rdi+68h]; this
0x1800160d8  call    ?ReleaseLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(void)
0x1800160dd  test    ebx, ebx
0x1800160df  jns     short loc_1800160EB
0x1800160e1  cmp     [rbp+arg_20], r13d
0x1800160e5  jz      loc_1800162C1
0x1800160eb  xor     ebx, ebx
0x1800160ed  cmp     [rdi+58h], rbx
0x1800160f1  jnz     loc_1800162BC
0x1800160f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x1800160fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180016103  test    al, al
0x180016105  jnz     loc_1800161B8
0x18001610b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016112  lea     ecx, [rbx+38h]; unsigned __int64
0x180016115  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001611a  mov     r14, rax
0x18001611d  mov     [rbp+arg_8], rax
0x180016121  test    rax, rax
0x180016124  jz      loc_1800161B0
0x18001612a  lea     rax, ??_7RtlArrayCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::RtlArrayCache::`vftable'
0x180016131  mov     [r14], rax
0x180016134  mov     [r14+8], rbx
0x180016138  mov     [r14+10h], rbx
0x18001613c  mov     [r14+18h], rbx
0x180016140  mov     [r14+20h], rbx
0x180016144  mov     [r14+28h], rbx
0x180016148  mov     [r14+30h], rbx
0x18001614c  test    r14, r14
0x18001614f  jz      loc_18001624B
0x180016155  mov     rdx, r15; unsigned __int16 *
0x180016158  mov     rcx, r14; this
0x18001615b  call    ?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)
0x180016160  mov     ebx, eax
0x180016162  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
  ... truncated ...
```
