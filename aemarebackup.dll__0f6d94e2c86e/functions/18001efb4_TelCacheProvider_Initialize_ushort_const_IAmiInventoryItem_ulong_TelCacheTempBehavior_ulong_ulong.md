# TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)

- ea: `0x18001efb4`
- end: `0x18001f85f`
- name: `?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z`
- size: `2219`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012618`
- `0x180015030`
- `0x180015840`
- `0x180015fd0`
- `0x18003ce10`
- `0x180042170`

## callees

- `0x180006d30`
- `0x1800129dc`
- `0x180013a58`
- `0x180014ed4`
- `0x18001e2e0`
- `0x18001e770`
- `0x18001ec10`
- `0x18001efb4`
- `0x180022178`
- `0x18002435c`
- `0x180024458`
- `0x1800256d8`
- `0x18002772c`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f2c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f31a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f31a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f296`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f296`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f22c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f4fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f6aa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f7ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f22c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f4fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f6aa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f7ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f222`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f4f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f6a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f7a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f222`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f4f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f6a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001f7a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f20a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f4d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f688`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f78c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f20a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f4d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f688`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f78c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2a9`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18001f2f2`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18001f2f2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f306`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f306`

## string_xrefs

- `0x18001f038`: `Already initialized [%#x]`
- `0x18001f0d2`: `ItemTemplate is null or has no schema for SQLite cache provider [%#x]`
- `0x18001f28f`: `aepic.dll`
- `0x18001f35f`: `AepicInvCache::Initialize failed [%#x]`
- `0x18001f3fa`: `TelCacheProvider::GetVersion failed [%#x]`
- `0x18001f3d8`: `InventoryCache::GetMetadata [%#x]`
- `0x18001f3e5`: `TelCacheProvider::GetVersion`
- `0x18001f3ba`: `TelCacheProvider::SetVersion [%#x]`
- `0x18001f0e9`: `Using SQLite cache provider: %ls.`
- `0x18001f57f`: `Using SQLite cache provider: %ls.`
- `0x18001f1aa`: `SqliteInvCache::Initialize failed [%#x]`
- `0x18001f636`: `SqliteInvCache::Initialize failed [%#x]`
- `0x18001f73a`: `RtlArrayCache::Initialize failed [%#x]`
- `0x18001f75f`: `Using in-memory cache provider: %ls.`
- `0x18001f014`: `TelCacheProvider::Initialize`
- `0x18001f0bc`: `TelCacheProvider::Initialize`
- `0x18001f1b7`: `TelCacheProvider::Initialize`
- `0x18001f36a`: `TelCacheProvider::Initialize`
- `0x18001f407`: `TelCacheProvider::Initialize`
- `0x18001f442`: `TelCacheProvider::Initialize`
- `0x18001f58c`: `TelCacheProvider::Initialize`
- `0x18001f643`: `TelCacheProvider::Initialize`
- `0x18001f72b`: `TelCacheProvider::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TelCacheProvider::Initialize(
        _QWORD *a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        DWORD dwMilliseconds)
{
  int v9; // esi
  Windows::Compat::Inventory::RtlArrayCache *v10; // r13
  Windows::Compat::Inventory::SqliteInvCache **v11; // r14
  int v12; // eax
  signed int v13; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  Windows::Compat::Inventory::InventorySynchronization *v16; // rdi
  char v17; // bl
  _QWORD *v18; // rax
  Windows::Compat::Inventory::SqliteInvCache *v19; // rax
  Windows::Compat::Inventory::SqliteInvCache *v20; // rsi
  int v21; // eax
  char v22; // cl
  __int64 v23; // rax
  char v24; // si
  struct Windows::Compat::Inventory::InventoryCache *v25; // rsi
  HMODULE Library; // rax
  signed int LastError; // eax
  int v28; // edi
  unsigned __int16 *v29; // r14
  __int64 v30; // rcx
  __int64 v31; // r8
  int v32; // eax
  TelCacheProvider *v33; // rcx
  int v34; // eax
  int v35; // eax
  char v36; // cl
  __int64 v37; // rax
  _QWORD *v38; // rax
  char v39; // dl
  char v40; // bl
  Windows::Compat::Inventory::SqliteInvCache *v41; // rax
  Windows::Compat::Inventory::SqliteInvCache *v42; // rbx
  int v43; // eax
  char v44; // cl
  __int64 v45; // rax
  char v46; // cl
  __int64 v47; // rax
  int v48; // eax
  int v50; // [rsp+20h] [rbp-38h]
  unsigned int v51; // [rsp+20h] [rbp-38h]
  unsigned int v52[2]; // [rsp+20h] [rbp-38h]
  unsigned int v53; // [rsp+20h] [rbp-38h]
  HMODULE hLibModule; // [rsp+30h] [rbp-28h]
  char *v55[4]; // [rsp+38h] [rbp-20h] BYREF
  Windows::Compat::Inventory::SqliteInvCache *v56; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int16 *Src; // [rsp+A8h] [rbp+50h]
  struct Windows::Compat::Inventory::InventoryCache *v58; // [rsp+B0h] [rbp+58h]
  int v59; // [rsp+B8h] [rbp+60h] BYREF

  Src = a2;
  v9 = 0;
  a6 = 0;
  v59 = 0;
  v10 = 0;
  v58 = 0;
  *a1 = a3;
  *((_WORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 48) = 0;
  v11 = (Windows::Compat::Inventory::SqliteInvCache **)(a1 + 11);
  if ( !a2 )
  {
    v12 = -2147024809;
    v13 = -2147024809;
    v14 = "ProviderName argument is null [%#x]";
    v15 = 575;
LABEL_3:
    v50 = v12;
LABEL_4:
    AslLogCallPrintf(1, "TelCacheProvider::Initialize", v15, v14, v50);
    goto LABEL_131;
  }
  if ( *v11 )
  {
    v13 = -2147418113;
    v50 = -2147418113;
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
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v25 = (struct Windows::Compat::Inventory::InventoryCache *)operator new(
                                                                 0x20u,
                                                                 (const struct std::nothrow_t *)&std::nothrow);
    if ( !v25 )
      goto LABEL_130;
    *(_QWORD *)v25 = &Windows::Compat::Inventory::AepicInvCache::`vftable';
    *((_QWORD *)v25 + 1) = 0;
    *((_QWORD *)v25 + 2) = 0;
    *((_BYTE *)v25 + 24) = 0;
    Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
    Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
    hLibModule = Library;
    if ( Library )
    {
      if ( GetProcAddress(Library, (LPCSTR)0x64) )
      {
        v28 = 4;
        v29 = Src;
        while ( 1 )
        {
          v13 = InvCacheOpenVerProvider((char *)v25 + 8, 0, v29, 2);
          if ( v13 >= 0 )
            break;
          if ( !--v28 )
            break;
          Sleep(dwMilliseconds);
        }
        v16 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
        v11 = (Windows::Compat::Inventory::SqliteInvCache **)(a1 + 11);
      }
      else
      {
        v13 = -2147467262;
      }
      FreeLibrary(hLibModule);
    }
    else
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v13 < 0 )
    {
      v24 = 1;
      if ( v13 == -2147467262 || v13 == -2147024891 || v13 == -2147024864 || v13 == -2147023582 )
      {
        v30 = 3;
        v31 = 665;
      }
      else
      {
        v30 = 1;
        v31 = 669;
      }
      AslLogCallPrintf(v30, "TelCacheProvider::Initialize", v31, "AepicInvCache::Initialize failed [%#x]", v13);
LABEL_86:
      if ( a5 == 3 )
        goto LABEL_105;
LABEL_87:
      if ( !*v11 )
      {
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
        {
          if ( *a1 )
          {
            v38 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(*(_QWORD *)*a1 + 64LL))(*a1, v55);
            v39 = a6 | 2;
            if ( *v38 != v38[1] )
            {
              v40 = 1;
              goto LABEL_94;
            }
          }
          else
          {
            v39 = a6;
          }
          v40 = 0;
LABEL_94:
          if ( (v39 & 2) != 0 )
            std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v55);
          if ( !v40 )
            goto LABEL_104;
          AslLogCallPrintf(3, "TelCacheProvider::Initialize", 745, "Using SQLite cache provider: %ls.", Src);
          v41 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                                0xF0u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
          v56 = v41;
          if ( v41 )
            v42 = Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v41);
          else
            v42 = 0;
          if ( !v42 )
            goto LABEL_101;
          Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
          v24 = 1;
          v43 = Windows::Compat::Inventory::SqliteInvCache::Initialize(
                  v42,
                  Src,
                  (struct IAmiInventoryItem *)*a1,
                  1,
                  v53);
          if ( v43 >= 0 )
          {
            *v11 = v42;
            goto LABEL_104;
          }
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 763, "SqliteInvCache::Initialize failed [%#x]", v43);
          (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v42)(v42, 1);
          if ( *((_BYTE *)v16 + 36) )
          {
            v46 = 0;
            v47 = *((_QWORD *)v16 + 3);
            if ( *(_DWORD *)(v47 + 4) == 1 )
            {
              *((_BYTE *)v16 + 36) = 0;
              v46 = 1;
            }
            --*(_DWORD *)(v47 + 4);
            if ( !v46 )
              goto LABEL_119;
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
            {
LABEL_119:
              v24 = 0;
              goto LABEL_104;
            }
            --**((_DWORD **)v16 + 3);
            --*((_DWORD *)v16 + 8);
            ReleaseMutex(*(HANDLE *)v16);
          }
          SetEvent(*((HANDLE *)v16 + 2));
          goto LABEL_119;
        }
        v10 = (Windows::Compat::Inventory::RtlArrayCache *)operator new(
                                                             0x38u,
                                                             (const struct std::nothrow_t *)&std::nothrow);
        v56 = v10;
        if ( !v10 )
        {
          v10 = 0;
LABEL_101:
          v13 = -2147024882;
          goto LABEL_105;
        }
        *(_QWORD *)v10 = &Windows::Compat::Inventory::RtlArrayCache::`vftable';
        *((_QWORD *)v10 + 1) = 0;
        *((_QWORD *)v10 + 2) = 0;
        *((_QWORD *)v10 + 3) = 0;
        *((_QWORD *)v10 + 4) = 0;
        *((_QWORD *)v10 + 5) = 0;
        *((_QWORD *)v10 + 6) = 0;
        v48 = Windows::Compat::Inventory::RtlArrayCache::Initialize(v10, Src);
        v13 = v48;
        if ( v48 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 783, "RtlArrayCache::Initialize failed [%#x]", v48);
LABEL_105:
          if ( !v24 )
            goto LABEL_128;
LABEL_106:
          if ( *((_BYTE *)v16 + 36) )
          {
            v44 = 0;
            v45 = *((_QWORD *)v16 + 3);
            if ( *(_DWORD *)(v45 + 4) == 1 )
            {
              *((_BYTE *)v16 + 36) = 0;
              v44 = 1;
            }
            --*(_DWORD *)(v45 + 4);
            if ( !v44 )
            {
LABEL_128:
              if ( v13 >= 0 )
                goto LABEL_138;
              goto LABEL_131;
            }
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
              goto LABEL_128;
            --**((_DWORD **)v16 + 3);
            --*((_DWORD *)v16 + 8);
            ReleaseMutex(*(HANDLE *)v16);
          }
          SetEvent(*((HANDLE *)v16 + 2));
          goto LABEL_128;
        }
        AslLogCallPrintf(3, "TelCacheProvider::Initialize", 787, "Using in-memory cache provider: %ls.", Src);
        *v11 = v10;
      }
LABEL_104:
      v13 = 0;
      v10 = 0;
      goto LABEL_105;
    }
    v32 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCache *, const wchar_t *, int *))(*(_QWORD *)v25 + 72LL))(
            v25,
            L"ProviderVersion",
            &v59);
    v13 = v32;
    if ( v32 == -2147024894 )
    {
      v59 = 0;
      v34 = TelCacheProvider::SetVersion(v33, v25, 0);
      v13 = v34;
      if ( v34 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::Initialize", 694, "TelCacheProvider::SetVersion [%#x]", v34);
LABEL_65:
        v58 = v25;
        goto LABEL_106;
      }
      v35 = 0;
      v59 = 0;
    }
    else
    {
      if ( v32 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::GetVersion", 1801, "InventoryCache::GetMetadata [%#x]", v32);
        v52[0] = v13;
        AslLogCallPrintf(
          1,
          "TelCacheProvider::Initialize",
          684,
          "TelCacheProvider::GetVersion failed [%#x]",
          *(_QWORD *)v52);
        goto LABEL_65;
      }
      v35 = v59;
    }
    v58 = v25;
    if ( v35 )
    {
      AslLogCallPrintf(
        3,
        "TelCacheProvider::Initialize",
        702,
        "%ls ProviderVersion did not match RequestedVersion.",
        Src);
      v13 = -2147467262;
    }
    else
    {
      *v11 = v25;
      v58 = 0;
      LODWORD(v56) = 0;
      if ( *a1
        && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
        && (*(int (__fastcall **)(Windows::Compat::Inventory::SqliteInvCache *, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)*v11 + 32LL))(
             *v11,
             &v56) >= 0
        && (_DWORD)v56
        && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, Src) )
      {
        *((_BYTE *)a1 + 97) = 1;
      }
      v13 = 0;
    }
    if ( *((_BYTE *)v16 + 36) )
    {
      v36 = 0;
      v37 = *((_QWORD *)v16 + 3);
      if ( *(_DWORD *)(v37 + 4) == 1 )
      {
        *((_BYTE *)v16 + 36) = 0;
        v36 = 1;
      }
      --*(_DWORD *)(v37 + 4);
      if ( !v36 )
        goto LABEL_84;
    }
    else
    {
      if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
      {
LABEL_84:
        v24 = 0;
LABEL_85:
        if ( v13 >= 0 )
          goto LABEL_87;
        goto LABEL_86;
      }
      --**((_DWORD **)v16 + 3);
      --*((_DWORD *)v16 + 8);
      ReleaseMutex(*(HANDLE *)v16);
    }
    SetEvent(*((HANDLE *)v16 + 2));
    goto LABEL_84;
  }
  if ( !*a1
    || (v18 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(*(_QWORD *)*a1 + 64LL))(*a1, v55),
        v9 = 1,
        a6 = 1,
        *v18 == v18[1]) )
  {
    v17 = 1;
  }
  if ( (v9 & 1) != 0 )
  {
    a6 = v9 & 0xFFFFFFFE;
    std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v55);
  }
  if ( !v17 )
  {
    AslLogCallPrintf(3, "TelCacheProvider::Initialize", 605, "Using SQLite cache provider: %ls.", a2);
    v19 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                          0xF0u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    v56 = v19;
    if ( v19 )
      v20 = Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v19);
    else
      v20 = 0;
    if ( v20 )
    {
      Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
      v21 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v20, a2, (struct IAmiInventoryItem *)*a1, 0, v51);
      v13 = v21;
      if ( v21 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::Initialize", 638, "SqliteInvCache::Initialize failed [%#x]", v21);
        (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v20)(v20, 1);
      }
      else
      {
        *v11 = v20;
        LODWORD(v56) = 0;
        if ( *a1
          && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
          && (*(int (__fastcall **)(Windows::Compat::Inventory::SqliteInvCache *, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)*v11 + 32LL))(
               *v11,
               &v56) >= 0
          && (_DWORD)v56
          && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
        {
          *((_BYTE *)a1 + 97) = 1;
        }
      }
      if ( *((_BYTE *)v16 + 36) )
      {
        v22 = 0;
        v23 = *((_QWORD *)v16 + 3);
        if ( *(_DWORD *)(v23 + 4) == 1 )
        {
          *((_BYTE *)v16 + 36) = 0;
          v22 = 1;
        }
        --*(_DWORD *)(v23 + 4);
        if ( !v22 )
          goto LABEL_38;
      }
      else
      {
        if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
        {
LABEL_38:
          v24 = 0;
          v58 = 0;
          goto LABEL_85;
        }
        --**((_DWORD **)v16 + 3);
        --*((_DWORD *)v16 + 8);
        ReleaseMutex(*(HANDLE *)v16);
      }
      SetEvent(*((HANDLE *)v16 + 2));
      goto LABEL_38;
    }
LABEL_130:
    v13 = -2147024882;
    goto LABEL_131;
  }
  v13 = -2147024809;
  AslLogCallPrintf(
    1,
    "TelCacheProvider::Initialize",
    600,
    "ItemTemplate is null or has no schema for SQLite cache provider [%#x]",
    -2147024809);
LABEL_131:
  if ( *((_BYTE *)a1 + 97) )
  {
    TelCacheProvider::SendNewSyncAdds((TelCacheProvider *)a1);
    *((_BYTE *)a1 + 97) = 0;
  }
  if ( *a1 )
  {
    (**(void (__fastcall ***)(_QWORD, __int64))*a1)(*a1, 1);
    *a1 = 0;
  }
  if ( *v11 )
  {
    (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))*v11)(*v11, 1);
    *v11 = 0;
  }
  Windows::Compat::Inventory::InventorySynchronization::Uninitialize((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
LABEL_138:
  if ( v58 )
    (**(void (__fastcall ***)(struct Windows::Compat::Inventory::InventoryCache *, __int64))v58)(v58, 1);
  if ( v10 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::RtlArrayCache *, __int64))v10)(v10, 1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001efb4  mov     [rsp-40h+arg_18], r9d
0x18001efb9  mov     [rsp-40h+Src], rdx
0x18001efbe  push    rbp
0x18001efbf  push    rbx
0x18001efc0  push    rsi
0x18001efc1  push    rdi
0x18001efc2  push    r12
0x18001efc4  push    r13
0x18001efc6  push    r14
0x18001efc8  push    r15
0x18001efca  mov     rbp, rsp
0x18001efcd  sub     rsp, 58h
0x18001efd1  mov     r12, rdx
0x18001efd4  mov     r15, rcx
0x18001efd7  xor     esi, esi
0x18001efd9  mov     [rbp+arg_28], esi
0x18001efdc  mov     [rbp+arg_18], esi
0x18001efdf  xor     r13d, r13d
0x18001efe2  xor     eax, eax
0x18001efe4  mov     [rbp+arg_10], rax
0x18001efe8  mov     [rcx], r8
0x18001efeb  mov     [rcx+8], ax
0x18001efef  mov     [rcx+60h], ax
0x18001eff3  lea     r14, [rcx+58h]
0x18001eff7  test    rdx, rdx
0x18001effa  jnz     short loc_18001F02A
0x18001effc  mov     eax, 80070057h
0x18001f001  mov     ebx, eax
0x18001f003  lea     r9, aProvidernameAr; "ProviderName argument is null [%#x]"
0x18001f00a  mov     r8d, 23Fh
0x18001f010  mov     [rsp+58h+var_38], eax
0x18001f014  lea     rdx, aTelcacheprovid_22; "TelCacheProvider::Initialize"
0x18001f01b  mov     ecx, 1
0x18001f020  call    AslLogCallPrintf
0x18001f025  jmp     loc_18001F7BF
0x18001f02a  cmp     [r14], rax
0x18001f02d  jz      short loc_18001F047
0x18001f02f  mov     ebx, 8000FFFFh
0x18001f034  mov     [rsp+58h+var_38], ebx
0x18001f038  lea     r9, aAlreadyInitial; "Already initialized [%#x]"
0x18001f03f  mov     r8d, 246h
0x18001f045  jmp     short loc_18001F014
0x18001f047  lea     rdi, [rcx+68h]
0x18001f04b  mov     rcx, rdi; this
0x18001f04e  call    ?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)
0x18001f053  mov     ebx, eax
0x18001f055  test    eax, eax
0x18001f057  jns     short loc_18001F068
0x18001f059  lea     r9, aInventorysynch_2; "InventorySynchronization:Initialize [%#"...
0x18001f060  mov     r8d, 24Dh
0x18001f066  jmp     short loc_18001F010
0x18001f068  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18001f06f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18001f074  xor     ebx, ebx
0x18001f076  test    al, al
0x18001f078  jz      loc_18001F240
0x18001f07e  mov     rcx, [r15]
0x18001f081  test    rcx, rcx
0x18001f084  jz      short loc_18001F0A5
0x18001f086  mov     rax, [rcx]
0x18001f089  lea     rdx, [rbp+var_20]
0x18001f08d  mov     rax, [rax+40h]
0x18001f091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f096  lea     esi, [rbx+1]
0x18001f099  mov     [rbp+arg_28], esi
0x18001f09c  mov     rcx, [rax+8]
0x18001f0a0  cmp     [rax], rcx
0x18001f0a3  jnz     short loc_18001F0A7
0x18001f0a5  mov     bl, 1
0x18001f0a7  test    sil, 1
0x18001f0ab  jz      short loc_18001F0BC
0x18001f0ad  and     esi, 0FFFFFFFEh
0x18001f0b0  mov     [rbp+arg_28], esi
0x18001f0b3  lea     rcx, [rbp+var_20]
0x18001f0b7  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x18001f0bc  lea     rdx, aTelcacheprovid_22; "TelCacheProvider::Initialize"
0x18001f0c3  test    bl, bl
0x18001f0c5  jz      short loc_18001F0E4
0x18001f0c7  mov     eax, 80070057h
0x18001f0cc  mov     ebx, eax
0x18001f0ce  mov     [rsp+58h+var_38], eax
0x18001f0d2  lea     r9, aItemtemplateIs; "ItemTemplate is null or has no schema f"...
0x18001f0d9  mov     r8d, 258h
0x18001f0df  jmp     loc_18001F01B
0x18001f0e4  mov     qword ptr [rsp+58h+var_38], r12; unsigned int
0x18001f0e9  lea     r9, aUsingSqliteCac; "Using SQLite cache provider: %ls."
0x18001f0f0  mov     r8d, 25Dh
0x18001f0f6  mov     ecx, 3
0x18001f0fb  call    AslLogCallPrintf
0x18001f100  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f107  mov     ecx, 0F0h; unsigned __int64
0x18001f10c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f111  mov     [rbp+arg_0], rax
0x18001f115  test    rax, rax
0x18001f118  jz      short loc_18001F127
0x18001f11a  mov     rcx, rax; this
0x18001f11d  call    ??0SqliteInvCache@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(void)
0x18001f122  mov     rsi, rax
0x18001f125  jmp     short loc_18001F129
0x18001f127  xor     esi, esi
0x18001f129  test    rsi, rsi
0x18001f12c  jz      loc_18001F7BA
0x18001f132  mov     rcx, rdi; this
0x18001f135  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18001f13a  xor     r9d, r9d; int
0x18001f13d  mov     r8, [r15]; struct IAmiInventoryItem *
0x18001f140  mov     rdx, r12; Src
0x18001f143  mov     rcx, rsi; this
0x18001f146  call    ?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z; Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)
0x18001f14b  mov     ebx, eax
0x18001f14d  test    eax, eax
0x18001f14f  js      short loc_18001F1A6
0x18001f151  mov     [r14], rsi
0x18001f154  mov     dword ptr [rbp+arg_0], 0
0x18001f15b  mov     rcx, [r15]
0x18001f15e  test    rcx, rcx
0x18001f161  jz      short loc_18001F1DB
0x18001f163  mov     rax, [rcx]
0x18001f166  mov     rax, [rax+38h]
0x18001f16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f16f  test    al, al
0x18001f171  jz      short loc_18001F1DB
0x18001f173  mov     rcx, [r14]
0x18001f176  mov     rax, [rcx]
0x18001f179  lea     rdx, [rbp+arg_0]
0x18001f17d  mov     rax, [rax+20h]
0x18001f181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f186  test    eax, eax
0x18001f188  js      short loc_18001F1DB
0x18001f18a  cmp     dword ptr [rbp+arg_0], 0
0x18001f18e  jbe     short loc_18001F1DB
0x18001f190  mov     rdx, r12; unsigned __int16 *
0x18001f193  mov     rcx, r15; this
0x18001f196  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x18001f19b  test    eax, eax
0x18001f19d  jz      short loc_18001F1DB
0x18001f19f  mov     byte ptr [r15+61h], 1
0x18001f1a4  jmp     short loc_18001F1DB
0x18001f1a6  mov     [rsp+58h+var_38], eax
0x18001f1aa  lea     r9, aSqliteinvcache; "SqliteInvCache::Initialize failed [%#x]"
0x18001f1b1  mov     r8d, 27Eh
0x18001f1b7  lea     rdx, aTelcacheprovid_22; "TelCacheProvider::Initialize"
0x18001f1be  mov     ecx, 1
0x18001f1c3  call    AslLogCallPrintf
0x18001f1c8  mov     rax, [rsi]
0x18001f1cb  mov     edx, 1
0x18001f1d0  mov     rcx, rsi
0x18001f1d3  mov     rax, [rax]
0x18001f1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1db  cmp     byte ptr [rdi+24h], 0
0x18001f1df  jz      short loc_18001F200
0x18001f1e1  xor     cl, cl
0x18001f1e3  mov     rax, [rdi+18h]
0x18001f1e7  cmp     dword ptr [rax+4], 1
0x18001f1eb  jnz     short loc_18001F1F2
0x18001f1ed  mov     [rdi+24h], cl
0x18001f1f0  mov     cl, 1
0x18001f1f2  or      r12d, 0FFFFFFFFh
0x18001f1f6  add     [rax+4], r12d
0x18001f1fa  test    cl, cl
0x18001f1fc  jz      short loc_18001F232
0x18001f1fe  jmp     short loc_18001F228
0x18001f200  or      r12d, 0FFFFFFFFh
0x18001f204  mov     edx, r12d; dwMilliseconds
0x18001f207  mov     rcx, [rdi]; hHandle
0x18001f20a  call    cs:__imp_WaitForSingleObject
0x18001f210  test    eax, eax
0x18001f212  jnz     short loc_18001F232
0x18001f214  mov     rax, [rdi+18h]
0x18001f218  add     [rax], r12d
0x18001f21b  add     [rdi+20h], r12d
0x18001f21f  mov     rcx, [rdi]; hMutex
0x18001f222  call    cs:__imp_ReleaseMutex
0x18001f228  mov     rcx, [rdi+10h]; hEvent
0x18001f22c  call    cs:__imp_SetEvent
0x18001f232  xor     sil, sil
0x18001f235  xor     eax, eax
0x18001f237  mov     [rbp+arg_10], rax
0x18001f23b  jmp     loc_18001F504
0x18001f240  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f247  mov     ecx, 20h ; ' '; unsigned __int64
0x18001f24c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f251  mov     rsi, rax
0x18001f254  mov     [rbp+hLibModule], rax
0x18001f258  test    rax, rax
0x18001f25b  jz      loc_18001F7BA
0x18001f261  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x18001f268  mov     [rsi], rax
0x18001f26b  mov     [rsi+8], rbx
0x18001f26f  mov     [rsi+10h], rbx
0x18001f273  mov     [rsi+18h], bl
0x18001f276  test    rsi, rsi
0x18001f279  jz      loc_18001F7BA
0x18001f27f  mov     rcx, rdi; this
0x18001f282  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18001f287  xor     edx, edx; hFile
0x18001f289  mov     r8d, 800h; dwFlags
0x18001f28f  lea     rcx, aAepicDll_0; "aepic.dll"
0x18001f296  call    cs:__imp_LoadLibraryExW
0x18001f29c  mov     [rbp+hLibModule], rax
0x18001f2a0  or      r12d, 0FFFFFFFFh
0x18001f2a4  test    rax, rax
0x18001f2a7  jnz     short loc_18001F2C0
0x18001f2a9  call    cs:__imp_GetLastError
0x18001f2af  mov     ebx, eax
0x18001f2b1  test    eax, eax
0x18001f2b3  jle     short loc_18001F320
0x18001f2b5  movzx   ebx, ax
0x18001f2b8  or      ebx, 80070000h
0x18001f2be  jmp     short loc_18001F320
0x18001f2c0  mov     edx, 64h ; 'd'; lpProcName
0x18001f2c5  mov     rcx, rax; hModule
0x18001f2c8  call    cs:__imp_GetProcAddress
0x18001f2ce  test    rax, rax
0x18001f2d1  jnz     short loc_18001F2DA
0x18001f2d3  mov     ebx, 80004002h
0x18001f2d8  jmp     short loc_18001F316
0x18001f2da  mov     edi, 4
0x18001f2df  mov     r14, [rbp+Src]
0x18001f2e3  mov     r9d, 2
0x18001f2e9  mov     r8, r14
0x18001f2ec  xor     edx, edx
0x18001f2ee  lea     rcx, [rsi+8]
0x18001f2f2  call    cs:__imp_InvCacheOpenVerProvider
0x18001f2f8  mov     ebx, eax
0x18001f2fa  test    eax, eax
0x18001f2fc  jns     short loc_18001F30E
0x18001f2fe  add     edi, r12d
0x18001f301  jz      short loc_18001F30E
0x18001f303  mov     ecx, [rbp+dwMilliseconds]; dwMilliseconds
0x18001f306  call    cs:__imp_Sleep
0x18001f30c  jmp     short loc_18001F2E3
0x18001f30e  lea     rdi, [r15+68h]
0x18001f312  lea     r14, [r15+58h]
0x18001f316  mov     rcx, [rbp+hLibModule]; hLibModule
0x18001f31a  call    cs:__imp_FreeLibrary
0x18001f320  test    ebx, ebx
0x18001f322  jns     short loc_18001F37B
0x18001f324  mov     sil, 1
0x18001f327  cmp     ebx, 80004002h
0x18001f32d  jz      short loc_18001F354
0x18001f32f  cmp     ebx, 80070005h
0x18001f335  jz      short loc_18001F354
0x18001f337  cmp     ebx, 80070020h
0x18001f33d  jz      short loc_18001F354
0x18001f33f  cmp     ebx, 80070522h
0x18001f345  jz      short loc_18001F354
0x18001f347  mov     ecx, 1
0x18001f34c  mov     r8d, 29Dh
0x18001f352  jmp     short loc_18001F35F
0x18001f354  mov     ecx, 3
0x18001f359  mov     r8d, 299h
0x18001f35f  lea     r9, aAepicinvcacheI; "AepicInvCache::Initialize failed [%#x]"
0x18001f366  mov     [rsp+58h+var_38], ebx
0x18001f36a  lea     rdx, aTelcacheprovid_22; "TelCacheProvider::Initialize"
0x18001f371  call    AslLogCallPrintf
0x18001f376  jmp     loc_18001F508
0x18001f37b  mov     rax, [rsi]
0x18001f37e  lea     r8, [rbp+arg_18]
0x18001f382  lea     rdx, aProviderversio; "ProviderVersion"
0x18001f389  mov     rcx, rsi
0x18001f38c  mov     rax, [rax+48h]
0x18001f390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f395  mov     ebx, eax
0x18001f397  cmp     eax, 80070002h
0x18001f39c  jnz     short loc_18001F3D0
0x18001f39e  mov     [rbp+arg_18], 0
0x18001f3a5  xor     r8d, r8d; unsigned int
0x18001f3a8  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x18001f3ab  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x18001f3b0  mov     ebx, eax
0x18001f3b2  test    eax, eax
0x18001f3b4  jns     short loc_18001F3C9
0x18001f3b6  mov     [rsp+58h+var_38], eax
0x18001f3ba  lea     r9, aTelcacheprovid_20; "TelCacheProvider::SetVersion [%#x]"
0x18001f3c1  mov     r8d, 2B6h
0x18001f3c7  jmp     short loc_18001F407
0x18001f3c9  xor     eax, eax
0x18001f3cb  mov     [rbp+arg_18], eax
0x18001f3ce  jmp     short loc_18001F424
0x18001f3d0  test    ebx, ebx
0x18001f3d2  jns     short loc_18001F421
0x18001f3d4  mov     [rsp+58h+var_38], ebx
0x18001f3d8  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x18001f3df  mov     r8d, 709h
0x18001f3e5  lea     rdx, aTelcacheprovid_30; "TelCacheProvider::GetVersion"
0x18001f3ec  mov     ecx, 1
0x18001f3f1  call    AslLogCallPrintf
0x18001f3f6  mov     [rsp+58h+var_38], ebx
0x18001f3fa  lea     r9, aTelcacheprovid_13; "TelCacheProvider::GetVersion failed [%#"...
0x18001f401  mov     r8d, 2ACh
0x18001f407  lea     rdx, aTelcacheprovid_22; "TelCacheProvider::Initialize"
0x18001f40e  mov     ecx, 1
0x18001f413  call    AslLogCallPrintf
0x18001f418  mov     [rbp+arg_10], rsi
0x18001f41c  jmp     loc_18001F606
0x18001f421  mov     eax, [rbp+arg_18]
0x18001f424  mov     [rbp+arg_10], rsi
0x18001f428  test    eax, eax
0x18001f42a  jz      short loc_18001F45A
  ... truncated ...
```
