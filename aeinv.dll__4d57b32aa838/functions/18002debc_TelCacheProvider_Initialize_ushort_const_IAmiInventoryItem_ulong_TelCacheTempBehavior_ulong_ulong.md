# TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)

- ea: `0x18002debc`
- end: `0x18002e4fe`
- name: `?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z`
- size: `1602`
- prototype: `__int64 __fastcall(_QWORD *, const unsigned __int16 *, __int64, __int64, int, unsigned int, unsigned int)`
- caller_count: `13`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18002d624`
- `0x180031a40`
- `0x180035dc0`
- `0x180045740`
- `0x180055dcc`
- `0x180057730`
- `0x180058940`
- `0x180060460`
- `0x180061288`
- `0x180061a00`
- `0x1800629a0`
- `0x1800f98e8`
- `0x18010dd68`

## callees

- `0x18000fb00`
- `0x18000fbf4`
- `0x180015224`
- `0x1800197d4`
- `0x180028a84`
- `0x18002949c`
- `0x18002b264`
- `0x18002bc50`
- `0x18002debc`
- `0x180046f38`
- `0x180052eb8`
- `0x18005326c`
- `0x180059db4`
- `0x18005e14c`
- `0x1800643a4`
- `0x180066814`
- `0x180130010`

## string_xrefs

- `0x18002df44`: `Already initialized [%#x]`
- `0x18002e18c`: `ItemTemplate is null or has no schema for SQLite cache provider [%#x]`
- `0x18002e022`: `AepicInvCache::Initialize failed [%#x]`
- `0x18002e050`: `TelCacheProvider::GetVersion failed [%#x]`
- `0x18002e08d`: `TelCacheProvider::SetVersion [%#x]`
- `0x18002e1a3`: `Using SQLite cache provider: %ls.`
- `0x18002e3d6`: `Using SQLite cache provider: %ls.`
- `0x18002e270`: `SqliteInvCache::Initialize failed [%#x]`
- `0x18002e458`: `SqliteInvCache::Initialize failed [%#x]`
- `0x18002e346`: `RtlArrayCache::Initialize failed [%#x]`
- `0x18002e367`: `Using in-memory cache provider: %ls.`
- `0x18002df1f`: `TelCacheProvider::Initialize`
- `0x18002e02d`: `TelCacheProvider::Initialize`
- `0x18002e061`: `TelCacheProvider::Initialize`
- `0x18002e0c2`: `TelCacheProvider::Initialize`
- `0x18002e176`: `TelCacheProvider::Initialize`
- `0x18002e27d`: `TelCacheProvider::Initialize`
- `0x18002e337`: `TelCacheProvider::Initialize`
- `0x18002e3e3`: `TelCacheProvider::Initialize`
- `0x18002e465`: `TelCacheProvider::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
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
  int v12; // ebx
  const char *v13; // r9
  int v14; // r8d
  Windows::Compat::Inventory::InventorySynchronization *v15; // r13
  char v16; // bl
  Windows::Compat::Inventory::SqliteInvCache *v17; // rsi
  int v18; // eax
  TelCacheProvider *v19; // rcx
  char v20; // si
  int v21; // ecx
  int v22; // r8d
  int Version; // eax
  TelCacheProvider *v24; // rcx
  const char *v25; // r9
  int v26; // r8d
  unsigned int v27; // eax
  _QWORD *v28; // rax
  Windows::Compat::Inventory::SqliteInvCache *v29; // rax
  struct sqlite3 **v30; // rsi
  bool v31; // bl
  _QWORD *v32; // rax
  char v33; // dl
  Windows::Compat::Inventory::SqliteInvCache *v34; // rax
  struct sqlite3 **v35; // rbx
  _BYTE v37[24]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v38; // [rsp+90h] [rbp+40h] BYREF
  Windows::Compat::Inventory::SqliteInvCache *v39; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v40; // [rsp+A8h] [rbp+58h]

  v9 = 0;
  v40 = 0;
  v38 = 0;
  v10 = 0;
  v11 = 0;
  *a1 = a3;
  *((_WORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 48) = 0;
  if ( a2 )
  {
    if ( a1[11] )
    {
      v12 = -2147418113;
      v13 = "Already initialized [%#x]";
      v14 = 582;
      goto LABEL_3;
    }
    v15 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
    v12 = Windows::Compat::Inventory::InventorySynchronization::Initialize(
            (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13),
            a2);
    if ( v12 < 0 )
    {
      v13 = "InventorySynchronization:Initialize [%#x]";
      v14 = 589;
      goto LABEL_3;
    }
    v16 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      if ( !*a1
        || (v28 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v37),
            v9 = 1,
            v40 = 1,
            *v28 == v28[1]) )
      {
        v16 = 1;
      }
      if ( (v9 & 1) != 0 )
      {
        v40 = v9 & 0xFFFFFFFE;
        std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v37);
      }
      if ( v16 )
      {
        v12 = -2147024809;
        v13 = "ItemTemplate is null or has no schema for SQLite cache provider [%#x]";
        v14 = 600;
        goto LABEL_3;
      }
      AslLogCallPrintf(
        3,
        (unsigned int)"TelCacheProvider::Initialize",
        605,
        (unsigned int)"Using SQLite cache provider: %ls.");
      v29 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                            0xF0u,
                                                            (const struct std::nothrow_t *)&std::nothrow);
      v39 = v29;
      if ( v29 )
        v30 = (struct sqlite3 **)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v29);
      else
        v30 = 0;
      if ( v30 )
      {
        Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
        v12 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v30, a2, (struct IAmiInventoryItem *)*a1, 0);
        if ( v12 < 0 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"TelCacheProvider::Initialize",
            638,
            (unsigned int)"SqliteInvCache::Initialize failed [%#x]");
          (*(void (__fastcall **)(struct sqlite3 **, __int64))*v30)(v30, 1);
        }
        else
        {
          a1[11] = v30;
          LODWORD(v39) = 0;
          if ( *a1
            && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
            && (*(int (__fastcall **)(_QWORD, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)a1[11] + 32LL))(
                 a1[11],
                 &v39) >= 0
            && (_DWORD)v39
            && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
          {
            *((_BYTE *)a1 + 97) = 1;
          }
        }
        v20 = 0;
        v11 = 0;
        goto LABEL_57;
      }
    }
    else
    {
      v17 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                            0x20u,
                                                            (const struct std::nothrow_t *)&std::nothrow);
      v39 = v17;
      if ( v17 )
      {
        *(_QWORD *)v17 = &Windows::Compat::Inventory::AepicInvCache::`vftable';
        *((_QWORD *)v17 + 1) = 0;
        *((_QWORD *)v17 + 2) = 0;
        *((_BYTE *)v17 + 24) = 0;
        Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v15);
        v18 = Windows::Compat::Inventory::AepicInvCache::Initialize(v17, a2, a6, a7);
        v12 = v18;
        if ( v18 < 0 )
        {
          v20 = 1;
          if ( v18 == -2147467262 || v18 == -2147024891 || v18 == -2147024864 || v18 == -2147023582 )
          {
            v21 = 3;
            v22 = 665;
          }
          else
          {
            v21 = 1;
            v22 = 669;
          }
          AslLogCallPrintf(
            v21,
            (unsigned int)"TelCacheProvider::Initialize",
            v22,
            (unsigned int)"AepicInvCache::Initialize failed [%#x]");
LABEL_58:
          if ( a5 == 3 )
          {
LABEL_81:
            if ( !v20 )
              goto LABEL_84;
            v15 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
LABEL_83:
            Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(v15);
LABEL_84:
            if ( v12 >= 0 )
              goto LABEL_86;
            goto LABEL_85;
          }
LABEL_59:
          v31 = 0;
          if ( a1[11] )
            goto LABEL_80;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
          {
            if ( *a1 )
            {
              v32 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v37);
              v33 = v40 | 2;
              v31 = *v32 != v32[1];
            }
            else
            {
              v33 = v40;
            }
            if ( (v33 & 2) != 0 )
              std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(v37);
            if ( !v31 )
              goto LABEL_80;
            AslLogCallPrintf(
              3,
              (unsigned int)"TelCacheProvider::Initialize",
              745,
              (unsigned int)"Using SQLite cache provider: %ls.");
            v34 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                                  0xF0u,
                                                                  (const struct std::nothrow_t *)&std::nothrow);
            v39 = v34;
            if ( v34 )
              v35 = (struct sqlite3 **)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v34);
            else
              v35 = 0;
            if ( v35 )
            {
              Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
              if ( (int)Windows::Compat::Inventory::SqliteInvCache::Initialize(
                          v35,
                          a2,
                          (struct IAmiInventoryItem *)*a1,
                          1) < 0 )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"TelCacheProvider::Initialize",
                  763,
                  (unsigned int)"SqliteInvCache::Initialize failed [%#x]");
                (*(void (__fastcall **)(struct sqlite3 **, __int64))*v35)(v35, 1);
                Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
                v20 = 0;
              }
              else
              {
                v20 = 1;
                a1[11] = v35;
              }
              goto LABEL_80;
            }
          }
          else
          {
            v10 = (Windows::Compat::Inventory::RtlArrayCache *)operator new(
                                                                 0x38u,
                                                                 (const struct std::nothrow_t *)&std::nothrow);
            v39 = v10;
            if ( v10 )
            {
              *(_QWORD *)v10 = &Windows::Compat::Inventory::RtlArrayCache::`vftable';
              *((_QWORD *)v10 + 1) = 0;
              *((_QWORD *)v10 + 2) = 0;
              *((_QWORD *)v10 + 3) = 0;
              *((_QWORD *)v10 + 4) = 0;
              *((_QWORD *)v10 + 5) = 0;
              *((_QWORD *)v10 + 6) = 0;
              v12 = Windows::Compat::Inventory::RtlArrayCache::Initialize(v10, a2);
              if ( v12 < 0 )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"TelCacheProvider::Initialize",
                  783,
                  (unsigned int)"RtlArrayCache::Initialize failed [%#x]");
                goto LABEL_81;
              }
              AslLogCallPrintf(
                3,
                (unsigned int)"TelCacheProvider::Initialize",
                787,
                (unsigned int)"Using in-memory cache provider: %ls.");
              a1[11] = v10;
LABEL_80:
              v12 = 0;
              v10 = 0;
              goto LABEL_81;
            }
            v10 = 0;
          }
          v12 = -2147024882;
          goto LABEL_81;
        }
        Version = TelCacheProvider::GetVersion(v19, v17, &v38);
        v12 = Version;
        if ( Version < 0 )
        {
          v25 = "TelCacheProvider::GetVersion failed [%#x]";
          v26 = 684;
LABEL_20:
          AslLogCallPrintf(1, (unsigned int)"TelCacheProvider::Initialize", v26, (_DWORD)v25);
          v11 = v17;
          goto LABEL_83;
        }
        if ( Version )
        {
          v12 = TelCacheProvider::SetVersion(v24, v17, 0);
          if ( v12 < 0 )
          {
            v25 = "TelCacheProvider::SetVersion [%#x]";
            v26 = 694;
            goto LABEL_20;
          }
          v27 = 0;
          v38 = 0;
        }
        else
        {
          v27 = v38;
        }
        if ( v27 )
        {
          AslLogCallPrintf(
            3,
            (unsigned int)"TelCacheProvider::Initialize",
            702,
            (unsigned int)"%ls ProviderVersion did not match RequestedVersion.");
          v12 = -2147467262;
          v11 = v17;
        }
        else
        {
          a1[11] = v17;
          LODWORD(v39) = 0;
          if ( *a1
            && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
            && (*(int (__fastcall **)(_QWORD, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)a1[11] + 32LL))(
                 a1[11],
                 &v39) >= 0
            && (_DWORD)v39
            && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
          {
            *((_BYTE *)a1 + 97) = 1;
          }
          v12 = 0;
        }
        v20 = 0;
LABEL_57:
        Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
        if ( v12 >= 0 )
          goto LABEL_59;
        goto LABEL_58;
      }
    }
    v12 = -2147024882;
    goto LABEL_85;
  }
  v12 = -2147024809;
  v13 = "ProviderName argument is null [%#x]";
  v14 = 575;
LABEL_3:
  AslLogCallPrintf(1, (unsigned int)"TelCacheProvider::Initialize", v14, (_DWORD)v13);
LABEL_85:
  TelCacheProvider::Uninitialize((TelCacheProvider *)a1);
LABEL_86:
  if ( v11 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v11)(v11, 1);
  if ( v10 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::RtlArrayCache *, __int64))v10)(v10, 1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002debc  mov     rax, rsp
0x18002debf  mov     [rax+20h], r9d
0x18002dec3  push    rbp
0x18002dec4  push    rsi
0x18002dec5  push    rdi
0x18002dec6  push    r12
0x18002dec8  push    r13
0x18002deca  push    r14
0x18002decc  push    r15
0x18002dece  mov     rbp, rsp
0x18002ded1  sub     rsp, 50h
0x18002ded5  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x18002dedd  mov     [rax+18h], rbx
0x18002dee1  mov     r15, rdx
0x18002dee4  mov     rdi, rcx
0x18002dee7  xor     esi, esi
0x18002dee9  mov     [rbp+arg_18], esi
0x18002deec  mov     [rbp+arg_0], esi
0x18002deef  xor     r14d, r14d
0x18002def2  xor     r12d, r12d
0x18002def5  mov     [rcx], r8
0x18002def8  xor     eax, eax
0x18002defa  mov     [rcx+8], ax
0x18002defe  mov     [rcx+60h], ax
0x18002df02  test    rdx, rdx
0x18002df05  jnz     short loc_18002DF35
0x18002df07  mov     eax, 80070057h
0x18002df0c  mov     ebx, eax
0x18002df0e  lea     r9, aProvidernameAr; "ProviderName argument is null [%#x]"
0x18002df15  mov     r8d, 23Fh
0x18002df1b  mov     [rsp+50h+var_30], eax
0x18002df1f  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x18002df26  mov     ecx, 1
0x18002df2b  call    AslLogCallPrintf
0x18002df30  jmp     loc_18002E4AB
0x18002df35  cmp     [rcx+58h], rax
0x18002df39  jz      short loc_18002DF53
0x18002df3b  mov     ebx, 8000FFFFh
0x18002df40  mov     [rsp+50h+var_30], ebx
0x18002df44  lea     r9, aAlreadyInitial; "Already initialized [%#x]"
0x18002df4b  mov     r8d, 246h
0x18002df51  jmp     short loc_18002DF1F
0x18002df53  lea     r13, [rcx+68h]
0x18002df57  mov     rcx, r13; this
0x18002df5a  call    ?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)
0x18002df5f  mov     ebx, eax
0x18002df61  test    eax, eax
0x18002df63  jns     short loc_18002DF74
0x18002df65  lea     r9, aInventorysynch_2; "InventorySynchronization:Initialize [%#"...
0x18002df6c  mov     r8d, 24Dh
0x18002df72  jmp     short loc_18002DF1B
0x18002df74  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18002df7b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18002df80  xor     ebx, ebx
0x18002df82  test    al, al
0x18002df84  jnz     loc_18002E136
0x18002df8a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002df91  lea     ecx, [rbx+20h]; unsigned __int64
0x18002df94  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002df99  mov     rsi, rax
0x18002df9c  mov     [rbp+arg_8], rax
0x18002dfa0  test    rax, rax
0x18002dfa3  jz      loc_18002E1EC
0x18002dfa9  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x18002dfb0  mov     [rsi], rax
0x18002dfb3  mov     [rsi+8], rbx
0x18002dfb7  mov     [rsi+10h], rbx
0x18002dfbb  mov     [rsi+18h], bl
0x18002dfbe  test    rsi, rsi
0x18002dfc1  jz      loc_18002E1EC
0x18002dfc7  mov     rcx, r13; this
0x18002dfca  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18002dfcf  mov     r9d, [rbp+arg_30]; unsigned int
0x18002dfd3  mov     r8d, [rbp+arg_28]; unsigned int
0x18002dfd7  mov     rdx, r15; unsigned __int16 *
0x18002dfda  mov     rcx, rsi; this
0x18002dfdd  call    ?Initialize@AepicInvCache@Inventory@Compat@Windows@@QEAAJPEBGKK@Z; Windows::Compat::Inventory::AepicInvCache::Initialize(ushort const *,ulong,ulong)
0x18002dfe2  mov     ebx, eax
0x18002dfe4  test    eax, eax
0x18002dfe6  jns     short loc_18002E03E
0x18002dfe8  mov     sil, 1
0x18002dfeb  mov     r13d, 3
0x18002dff1  cmp     eax, 80004002h
0x18002dff6  jz      short loc_18002E019
0x18002dff8  cmp     eax, 80070005h
0x18002dffd  jz      short loc_18002E019
0x18002dfff  cmp     eax, 80070020h
0x18002e004  jz      short loc_18002E019
0x18002e006  cmp     eax, 80070522h
0x18002e00b  jz      short loc_18002E019
0x18002e00d  lea     ecx, [r13-2]
0x18002e011  mov     r8d, 29Dh
0x18002e017  jmp     short loc_18002E022
0x18002e019  mov     ecx, r13d
0x18002e01c  mov     r8d, 299h
0x18002e022  lea     r9, aAepicinvcacheI; "AepicInvCache::Initialize failed [%#x]"
0x18002e029  mov     [rsp+50h+var_30], eax
0x18002e02d  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x18002e034  call    AslLogCallPrintf
0x18002e039  jmp     loc_18002E2B6
0x18002e03e  lea     r8, [rbp+arg_0]; unsigned int *
0x18002e042  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x18002e045  call    ?GetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@AEAK@Z; TelCacheProvider::GetVersion(Windows::Compat::Inventory::InventoryCache *,ulong &)
0x18002e04a  mov     ebx, eax
0x18002e04c  test    eax, eax
0x18002e04e  jns     short loc_18002E07A
0x18002e050  lea     r9, aTelcacheprovid_11; "TelCacheProvider::GetVersion failed [%#"...
0x18002e057  mov     r8d, 2ACh
0x18002e05d  mov     [rsp+50h+var_30], eax
0x18002e061  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x18002e068  mov     ecx, 1
0x18002e06d  call    AslLogCallPrintf
0x18002e072  mov     r12, rsi
0x18002e075  jmp     loc_18002E49F
0x18002e07a  jz      short loc_18002E0A3
0x18002e07c  xor     r8d, r8d; unsigned int
0x18002e07f  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x18002e082  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x18002e087  mov     ebx, eax
0x18002e089  test    eax, eax
0x18002e08b  jns     short loc_18002E09C
0x18002e08d  lea     r9, aTelcacheprovid_17; "TelCacheProvider::SetVersion [%#x]"
0x18002e094  mov     r8d, 2B6h
0x18002e09a  jmp     short loc_18002E05D
0x18002e09c  xor     eax, eax
0x18002e09e  mov     [rbp+arg_0], eax
0x18002e0a1  jmp     short loc_18002E0A6
0x18002e0a3  mov     eax, [rbp+arg_0]
0x18002e0a6  mov     r13d, 3
0x18002e0ac  test    eax, eax
0x18002e0ae  jz      short loc_18002E0DB
0x18002e0b0  mov     qword ptr [rsp+50h+var_30], r15
0x18002e0b5  lea     r9, aLsProvidervers; "%ls ProviderVersion did not match Reque"...
0x18002e0bc  mov     r8d, 2BEh
0x18002e0c2  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x18002e0c9  mov     ecx, r13d
0x18002e0cc  call    AslLogCallPrintf
0x18002e0d1  mov     ebx, 80004002h
0x18002e0d6  mov     r12, rsi
0x18002e0d9  jmp     short loc_18002E12E
0x18002e0db  mov     [rdi+58h], rsi
0x18002e0df  mov     dword ptr [rbp+arg_8], r12d
0x18002e0e3  mov     rcx, [rdi]
0x18002e0e6  test    rcx, rcx
0x18002e0e9  jz      short loc_18002E12C
0x18002e0eb  mov     rax, [rcx]
0x18002e0ee  mov     rax, [rax+38h]
0x18002e0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0f7  test    al, al
0x18002e0f9  jz      short loc_18002E12C
0x18002e0fb  mov     rcx, [rdi+58h]
0x18002e0ff  mov     rax, [rcx]
0x18002e102  lea     rdx, [rbp+arg_8]
0x18002e106  mov     rax, [rax+20h]
0x18002e10a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e10f  test    eax, eax
0x18002e111  js      short loc_18002E12C
0x18002e113  cmp     dword ptr [rbp+arg_8], r12d
0x18002e117  jbe     short loc_18002E12C
0x18002e119  mov     rdx, r15; unsigned __int16 *
0x18002e11c  mov     rcx, rdi; this
0x18002e11f  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18002e124  test    eax, eax
0x18002e126  jz      short loc_18002E12C
0x18002e128  mov     byte ptr [rdi+61h], 1
0x18002e12c  xor     ebx, ebx
0x18002e12e  xor     sil, sil
0x18002e131  jmp     loc_18002E2A9
0x18002e136  mov     rcx, [rdi]
0x18002e139  test    rcx, rcx
0x18002e13c  jz      short loc_18002E15F
0x18002e13e  mov     rax, [rcx]
0x18002e141  lea     rdx, [rbp+var_18]
0x18002e145  mov     rax, [rax+40h]
0x18002e149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e14e  mov     esi, 1
0x18002e153  mov     [rbp+arg_18], esi
0x18002e156  mov     rcx, [rax+8]
0x18002e15a  cmp     [rax], rcx
0x18002e15d  jnz     short loc_18002E161
0x18002e15f  mov     bl, 1
0x18002e161  test    sil, 1
0x18002e165  jz      short loc_18002E176
0x18002e167  and     esi, 0FFFFFFFEh
0x18002e16a  mov     [rbp+arg_18], esi
0x18002e16d  lea     rcx, [rbp+var_18]
0x18002e171  call    ?_Tidy@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@AEAAXXZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Tidy(void)
0x18002e176  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x18002e17d  test    bl, bl
0x18002e17f  jz      short loc_18002E19E
0x18002e181  mov     eax, 80070057h
0x18002e186  mov     ebx, eax
0x18002e188  mov     [rsp+50h+var_30], eax
0x18002e18c  lea     r9, aItemtemplateIs; "ItemTemplate is null or has no schema f"...
0x18002e193  mov     r8d, 258h
0x18002e199  jmp     loc_18002DF26
0x18002e19e  mov     qword ptr [rsp+50h+var_30], r15; unsigned int
0x18002e1a3  lea     r9, aUsingSqliteCac; "Using SQLite cache provider: %ls."
0x18002e1aa  mov     r8d, 25Dh
0x18002e1b0  mov     r13d, 3
0x18002e1b6  mov     ecx, r13d
0x18002e1b9  call    AslLogCallPrintf
0x18002e1be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e1c5  mov     ecx, 0F0h; unsigned __int64
0x18002e1ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e1cf  mov     [rbp+arg_8], rax
0x18002e1d3  test    rax, rax
0x18002e1d6  jz      short loc_18002E1E5
0x18002e1d8  mov     rcx, rax; this
0x18002e1db  call    ??0SqliteInvCache@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(void)
0x18002e1e0  mov     rsi, rax
0x18002e1e3  jmp     short loc_18002E1E7
0x18002e1e5  xor     esi, esi
0x18002e1e7  test    rsi, rsi
0x18002e1ea  jnz     short loc_18002E1F6
0x18002e1ec  mov     ebx, 8007000Eh
0x18002e1f1  jmp     loc_18002E4AB
0x18002e1f6  lea     rcx, [rdi+68h]; this
0x18002e1fa  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18002e1ff  xor     r9d, r9d; int
0x18002e202  mov     r8, [rdi]; struct IAmiInventoryItem *
0x18002e205  mov     rdx, r15; unsigned __int16 *
0x18002e208  mov     rcx, rsi; this
0x18002e20b  call    ?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z; Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)
0x18002e210  mov     ebx, eax
0x18002e212  test    eax, eax
0x18002e214  js      short loc_18002E26C
0x18002e216  mov     [rdi+58h], rsi
0x18002e21a  mov     dword ptr [rbp+arg_8], 0
0x18002e221  mov     rcx, [rdi]
0x18002e224  test    rcx, rcx
0x18002e227  jz      short loc_18002E2A3
0x18002e229  mov     rax, [rcx]
0x18002e22c  mov     rax, [rax+38h]
0x18002e230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e235  test    al, al
0x18002e237  jz      short loc_18002E2A3
0x18002e239  mov     rcx, [rdi+58h]
0x18002e23d  mov     rax, [rcx]
0x18002e240  lea     rdx, [rbp+arg_8]
0x18002e244  mov     rax, [rax+20h]
0x18002e248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e24d  test    eax, eax
0x18002e24f  js      short loc_18002E2A3
0x18002e251  cmp     dword ptr [rbp+arg_8], 0
0x18002e255  jbe     short loc_18002E2A3
0x18002e257  mov     rdx, r15; unsigned __int16 *
0x18002e25a  mov     rcx, rdi; this
0x18002e25d  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18002e262  test    eax, eax
0x18002e264  jz      short loc_18002E2A3
0x18002e266  mov     byte ptr [rdi+61h], 1
0x18002e26a  jmp     short loc_18002E2A3
0x18002e26c  mov     [rsp+50h+var_30], eax
0x18002e270  lea     r9, aSqliteinvcache; "SqliteInvCache::Initialize failed [%#x]"
0x18002e277  mov     r8d, 27Eh
0x18002e27d  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::Initialize"
0x18002e284  mov     r12d, 1
0x18002e28a  mov     ecx, r12d
0x18002e28d  call    AslLogCallPrintf
0x18002e292  mov     rax, [rsi]
0x18002e295  mov     edx, r12d
0x18002e298  mov     rcx, rsi
0x18002e29b  mov     rax, [rax]
0x18002e29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2a3  xor     sil, sil
0x18002e2a6  xor     r12d, r12d
0x18002e2a9  lea     rcx, [rdi+68h]; this
0x18002e2ad  call    ?ReleaseLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::ReleaseLock(void)
0x18002e2b2  test    ebx, ebx
0x18002e2b4  jns     short loc_18002E2C0
0x18002e2b6  cmp     [rbp+arg_20], r13d
0x18002e2ba  jz      loc_18002E496
0x18002e2c0  xor     ebx, ebx
0x18002e2c2  cmp     [rdi+58h], rbx
0x18002e2c6  jnz     loc_18002E491
0x18002e2cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18002e2d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18002e2d8  test    al, al
0x18002e2da  jnz     loc_18002E38D
0x18002e2e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e2e7  lea     ecx, [rbx+38h]; unsigned __int64
0x18002e2ea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e2ef  mov     r14, rax
0x18002e2f2  mov     [rbp+arg_8], rax
0x18002e2f6  test    rax, rax
0x18002e2f9  jz      loc_18002E385
0x18002e2ff  lea     rax, ??_7RtlArrayCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::RtlArrayCache::`vftable'
0x18002e306  mov     [r14], rax
0x18002e309  mov     [r14+8], rbx
0x18002e30d  mov     [r14+10h], rbx
0x18002e311  mov     [r14+18h], rbx
0x18002e315  mov     [r14+20h], rbx
0x18002e319  mov     [r14+28h], rbx
0x18002e31d  mov     [r14+30h], rbx
0x18002e321  test    r14, r14
0x18002e324  jz      loc_18002E420
0x18002e32a  mov     rdx, r15; unsigned __int16 *
0x18002e32d  mov     rcx, r14; this
0x18002e330  call    ?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)
  ... truncated ...
```
