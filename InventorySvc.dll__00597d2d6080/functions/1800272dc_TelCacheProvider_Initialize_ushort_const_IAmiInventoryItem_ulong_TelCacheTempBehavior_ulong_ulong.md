# TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)

- ea: `0x1800272dc`
- end: `0x180027bc0`
- name: `?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z`
- size: `2276`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800264ec`
- `0x180029a44`

## callees

- `0x18000514c`
- `0x180010ad4`
- `0x1800152d0`
- `0x1800200a8`
- `0x1800208f0`
- `0x180021384`
- `0x180026818`
- `0x180026a40`
- `0x180026f28`
- `0x1800272dc`
- `0x18002a1bc`
- `0x18002c0a8`
- `0x18002c1a4`
- `0x18002d088`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027600`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027600`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800275ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800275ce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027656`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027656`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027564`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002784e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027a06`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027b0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027564`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002784e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027a06`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027b0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002755a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180027844`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800279fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180027b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002755a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180027844`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800279fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180027b00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027542`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002782c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800279e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027ae8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027542`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002782c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800279e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275e1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027640`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027640`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18002762a`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18002762a`

## string_xrefs

- `0x180027365`: `Already initialized [%#x]`
- `0x180027400`: `ItemTemplate is null or has no schema for SQLite cache provider [%#x]`
- `0x1800275c7`: `aepic.dll`
- `0x180027743`: `TelCacheProvider::GetVersion failed [%#x]`
- `0x18002769b`: `AepicInvCache::Initialize failed [%#x]`
- `0x18002772e`: `TelCacheProvider::GetVersion`
- `0x180027721`: `InventoryCache::GetMetadata [%#x]`
- `0x180027700`: `TelCacheProvider::SetVersion [%#x]`
- `0x180027417`: `Using SQLite cache provider: %ls.`
- `0x1800278d3`: `Using SQLite cache provider: %ls.`
- `0x1800274e2`: `SqliteInvCache::Initialize failed [%#x]`
- `0x180027992`: `SqliteInvCache::Initialize failed [%#x]`
- `0x180027abb`: `Using in-memory cache provider: %ls.`
- `0x180027a96`: `RtlArrayCache::Initialize failed [%#x]`
- `0x180027341`: `TelCacheProvider::Initialize`
- `0x1800273ea`: `TelCacheProvider::Initialize`
- `0x1800274ef`: `TelCacheProvider::Initialize`
- `0x1800276a6`: `TelCacheProvider::Initialize`
- `0x180027750`: `TelCacheProvider::Initialize`
- `0x180027793`: `TelCacheProvider::Initialize`
- `0x1800278e0`: `TelCacheProvider::Initialize`
- `0x18002799f`: `TelCacheProvider::Initialize`
- `0x180027a87`: `TelCacheProvider::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TelCacheProvider::Initialize(
        _QWORD *a1,
        const unsigned __int16 *a2,
        Windows::Compat::Inventory::SqliteInvCache *a3,
        int a4,
        int a5,
        int a6,
        unsigned int a7)
{
  int v9; // esi
  Windows::Compat::Inventory::RtlArrayCache *v10; // r13
  _QWORD *v11; // r14
  int v12; // eax
  signed int v13; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  Windows::Compat::Inventory::InventorySynchronization *v16; // rdi
  char v17; // bl
  _QWORD *v18; // rax
  Windows::Compat::Inventory::SqliteInvCache *v19; // rax
  struct sqlite3 **v20; // rsi
  int v21; // eax
  char v22; // cl
  __int64 v23; // rax
  char v24; // si
  struct Windows::Compat::Inventory::InventoryCache *v25; // rsi
  HMODULE Library; // rax
  signed int LastError; // eax
  int v28; // edi
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // eax
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  char v35; // cl
  __int64 v36; // rax
  _QWORD *v37; // rax
  char v38; // dl
  char v39; // bl
  Windows::Compat::Inventory::SqliteInvCache *v40; // rax
  struct sqlite3 **v41; // rbx
  int v42; // eax
  char v43; // cl
  __int64 v44; // rax
  char v45; // cl
  __int64 v46; // rax
  int v47; // eax
  int v49; // [rsp+20h] [rbp-38h]
  unsigned int v50[2]; // [rsp+20h] [rbp-38h]
  HMODULE hLibModule; // [rsp+30h] [rbp-28h]
  _BYTE v52[32]; // [rsp+38h] [rbp-20h] BYREF
  struct Windows::Compat::Inventory::InventoryCache *v53; // [rsp+A0h] [rbp+48h]
  Windows::Compat::Inventory::SqliteInvCache *v55; // [rsp+B0h] [rbp+58h] BYREF
  TelCacheProvider *v56; // [rsp+B8h] [rbp+60h]

  LODWORD(v56) = a4;
  v55 = a3;
  v9 = 0;
  a7 = 0;
  a6 = 0;
  v10 = 0;
  v53 = 0;
  *a1 = 0;
  *((_WORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 48) = 0;
  v11 = a1 + 11;
  if ( !a2 )
  {
    v12 = -2147024809;
    v13 = -2147024809;
    v14 = "ProviderName argument is null [%#x]";
    v15 = 575;
LABEL_3:
    v49 = v12;
LABEL_4:
    AslLogCallPrintf(1, "TelCacheProvider::Initialize", v15, v14, v49);
    goto LABEL_133;
  }
  if ( *v11 )
  {
    v13 = -2147418113;
    v49 = -2147418113;
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
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    v25 = (struct Windows::Compat::Inventory::InventoryCache *)operator new(
                                                                 0x20u,
                                                                 (const struct std::nothrow_t *)&std::nothrow);
    if ( !v25 )
      goto LABEL_132;
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
        while ( 1 )
        {
          v13 = InvCacheOpenVerProvider((char *)v25 + 8, 0, a2, 2);
          if ( v13 >= 0 )
            break;
          if ( !--v28 )
            break;
          Sleep(0x64u);
        }
        v16 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13);
        v11 = a1 + 11;
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
        v29 = 3;
        v30 = 665;
      }
      else
      {
        v29 = 1;
        v30 = 669;
      }
      AslLogCallPrintf(v29, "TelCacheProvider::Initialize", v30, "AepicInvCache::Initialize failed [%#x]", v13);
LABEL_88:
      if ( a5 == 3 )
        goto LABEL_107;
LABEL_89:
      if ( !*v11 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
        {
          if ( *a1 )
          {
            v37 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v52);
            v38 = a7 | 2;
            if ( *v37 != v37[1] )
            {
              v39 = 1;
              goto LABEL_96;
            }
          }
          else
          {
            v38 = a7;
          }
          v39 = 0;
LABEL_96:
          if ( (v38 & 2) != 0 )
            std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v52);
          if ( !v39 )
            goto LABEL_106;
          AslLogCallPrintf(3, "TelCacheProvider::Initialize", 745, "Using SQLite cache provider: %ls.", a2);
          v40 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                                0xF0u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
          v55 = v40;
          if ( v40 )
            v41 = (struct sqlite3 **)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v40);
          else
            v41 = 0;
          if ( !v41 )
            goto LABEL_103;
          Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
          v24 = 1;
          v42 = Windows::Compat::Inventory::SqliteInvCache::Initialize(
                  v41,
                  a2,
                  (struct IAmiInventoryItem *)*a1,
                  1,
                  (unsigned int)v56);
          if ( v42 >= 0 )
          {
            *v11 = v41;
            goto LABEL_106;
          }
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 763, "SqliteInvCache::Initialize failed [%#x]", v42);
          (*(void (__fastcall **)(struct sqlite3 **, __int64))*v41)(v41, 1);
          if ( *((_BYTE *)v16 + 36) )
          {
            v45 = 0;
            v46 = *((_QWORD *)v16 + 3);
            if ( *(_DWORD *)(v46 + 4) == 1 )
            {
              *((_BYTE *)v16 + 36) = 0;
              v45 = 1;
            }
            --*(_DWORD *)(v46 + 4);
            if ( !v45 )
              goto LABEL_121;
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
            {
LABEL_121:
              v24 = 0;
              goto LABEL_106;
            }
            --**((_DWORD **)v16 + 3);
            --*((_DWORD *)v16 + 8);
            ReleaseMutex(*(HANDLE *)v16);
          }
          SetEvent(*((HANDLE *)v16 + 2));
          goto LABEL_121;
        }
        v10 = (Windows::Compat::Inventory::RtlArrayCache *)operator new(
                                                             0x38u,
                                                             (const struct std::nothrow_t *)&std::nothrow);
        v55 = v10;
        if ( !v10 )
        {
          v10 = 0;
LABEL_103:
          v13 = -2147024882;
          goto LABEL_107;
        }
        *(_QWORD *)v10 = &Windows::Compat::Inventory::RtlArrayCache::`vftable';
        *((_QWORD *)v10 + 1) = 0;
        *((_QWORD *)v10 + 2) = 0;
        *((_QWORD *)v10 + 3) = 0;
        *((_QWORD *)v10 + 4) = 0;
        *((_QWORD *)v10 + 5) = 0;
        *((_QWORD *)v10 + 6) = 0;
        v47 = Windows::Compat::Inventory::RtlArrayCache::Initialize(v10, a2);
        v13 = v47;
        if ( v47 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 783, "RtlArrayCache::Initialize failed [%#x]", v47);
LABEL_107:
          if ( !v24 )
            goto LABEL_130;
LABEL_108:
          if ( *((_BYTE *)v16 + 36) )
          {
            v43 = 0;
            v44 = *((_QWORD *)v16 + 3);
            if ( *(_DWORD *)(v44 + 4) == 1 )
            {
              *((_BYTE *)v16 + 36) = 0;
              v43 = 1;
            }
            --*(_DWORD *)(v44 + 4);
            if ( !v43 )
            {
LABEL_130:
              if ( v13 >= 0 )
                goto LABEL_140;
              goto LABEL_133;
            }
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
              goto LABEL_130;
            --**((_DWORD **)v16 + 3);
            --*((_DWORD *)v16 + 8);
            ReleaseMutex(*(HANDLE *)v16);
          }
          SetEvent(*((HANDLE *)v16 + 2));
          goto LABEL_130;
        }
        AslLogCallPrintf(3, "TelCacheProvider::Initialize", 787, "Using in-memory cache provider: %ls.", a2);
        *v11 = v10;
      }
LABEL_106:
      v13 = 0;
      v10 = 0;
      goto LABEL_107;
    }
    v31 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCache *, const wchar_t *, int *))(*(_QWORD *)v25 + 72LL))(
            v25,
            L"ProviderVersion",
            &a6);
    v13 = v31;
    if ( v31 == -2147024894 )
    {
      v32 = 0;
      a6 = 0;
      v33 = (int)v56;
      if ( (_DWORD)v56 != -1 )
      {
        v34 = TelCacheProvider::SetVersion((TelCacheProvider *)(unsigned int)v56, v25, (unsigned int)v56);
        v13 = v34;
        if ( v34 < 0 )
        {
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 694, "TelCacheProvider::SetVersion [%#x]", v34);
LABEL_66:
          v53 = v25;
          goto LABEL_108;
        }
        v33 = (int)v56;
        v32 = (int)v56;
        a6 = (int)v56;
      }
    }
    else
    {
      if ( v31 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::GetVersion", 1801, "InventoryCache::GetMetadata [%#x]", v31);
        v50[0] = v13;
        AslLogCallPrintf(
          1,
          "TelCacheProvider::Initialize",
          684,
          "TelCacheProvider::GetVersion failed [%#x]",
          *(_QWORD *)v50);
        goto LABEL_66;
      }
      v32 = a6;
      v33 = (int)v56;
    }
    v53 = v25;
    if ( v33 == v32 || v33 == -1 )
    {
      *v11 = v25;
      v53 = 0;
      LODWORD(v55) = 0;
      if ( *a1
        && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
        && (*(int (__fastcall **)(_QWORD, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)*v11 + 32LL))(
             *v11,
             &v55) >= 0
        && (_DWORD)v55
        && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)a1, a2) )
      {
        *((_BYTE *)a1 + 97) = 1;
      }
      v13 = 0;
    }
    else
    {
      AslLogCallPrintf(
        3,
        "TelCacheProvider::Initialize",
        702,
        "%ls ProviderVersion did not match RequestedVersion.",
        a2);
      v13 = -2147467262;
    }
    if ( *((_BYTE *)v16 + 36) )
    {
      v35 = 0;
      v36 = *((_QWORD *)v16 + 3);
      if ( *(_DWORD *)(v36 + 4) == 1 )
      {
        *((_BYTE *)v16 + 36) = 0;
        v35 = 1;
      }
      --*(_DWORD *)(v36 + 4);
      if ( !v35 )
        goto LABEL_86;
    }
    else
    {
      if ( WaitForSingleObject(*(HANDLE *)v16, 0xFFFFFFFF) )
      {
LABEL_86:
        v24 = 0;
LABEL_87:
        if ( v13 >= 0 )
          goto LABEL_89;
        goto LABEL_88;
      }
      --**((_DWORD **)v16 + 3);
      --*((_DWORD *)v16 + 8);
      ReleaseMutex(*(HANDLE *)v16);
    }
    SetEvent(*((HANDLE *)v16 + 2));
    goto LABEL_86;
  }
  if ( !*a1
    || (v18 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 64LL))(*a1, v52),
        v9 = 1,
        a7 = 1,
        *v18 == v18[1]) )
  {
    v17 = 1;
  }
  if ( (v9 & 1) != 0 )
  {
    a7 = v9 & 0xFFFFFFFE;
    std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v52);
  }
  if ( !v17 )
  {
    AslLogCallPrintf(3, "TelCacheProvider::Initialize", 605, "Using SQLite cache provider: %ls.", a2);
    v19 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                          0xF0u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    v55 = v19;
    if ( v19 )
      v20 = (struct sqlite3 **)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v19);
    else
      v20 = 0;
    if ( v20 )
    {
      Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v16);
      v21 = Windows::Compat::Inventory::SqliteInvCache::Initialize(
              v20,
              a2,
              (struct IAmiInventoryItem *)*a1,
              0,
              (unsigned int)v56);
      v13 = v21;
      if ( v21 < 0 )
      {
        AslLogCallPrintf(1, "TelCacheProvider::Initialize", 638, "SqliteInvCache::Initialize failed [%#x]", v21);
        (*(void (__fastcall **)(struct sqlite3 **, __int64))*v20)(v20, 1);
      }
      else
      {
        *v11 = v20;
        LODWORD(v55) = 0;
        if ( *a1
          && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 56LL))(*a1)
          && (*(int (__fastcall **)(_QWORD, Windows::Compat::Inventory::SqliteInvCache **))(*(_QWORD *)*v11 + 32LL))(
               *v11,
               &v55) >= 0
          && (_DWORD)v55
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
          v53 = 0;
          goto LABEL_87;
        }
        --**((_DWORD **)v16 + 3);
        --*((_DWORD *)v16 + 8);
        ReleaseMutex(*(HANDLE *)v16);
      }
      SetEvent(*((HANDLE *)v16 + 2));
      goto LABEL_38;
    }
LABEL_132:
    v13 = -2147024882;
    goto LABEL_133;
  }
  v13 = -2147024809;
  AslLogCallPrintf(
    1,
    "TelCacheProvider::Initialize",
    600,
    "ItemTemplate is null or has no schema for SQLite cache provider [%#x]",
    -2147024809);
LABEL_133:
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
    (**(void (__fastcall ***)(_QWORD, __int64))*v11)(*v11, 1);
    *v11 = 0;
  }
  Windows::Compat::Inventory::InventorySynchronization::Uninitialize((Windows::Compat::Inventory::InventorySynchronization *)(a1 + 13));
LABEL_140:
  if ( v53 )
    (**(void (__fastcall ***)(struct Windows::Compat::Inventory::InventoryCache *, __int64))v53)(v53, 1);
  if ( v10 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::RtlArrayCache *, __int64))v10)(v10, 1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800272dc  mov     dword ptr [rsp-40h+arg_18], r9d
0x1800272e1  mov     [rsp-40h+arg_10], r8
0x1800272e6  mov     [rsp-40h+Src], rdx
0x1800272eb  push    rbp
0x1800272ec  push    rbx
0x1800272ed  push    rsi
0x1800272ee  push    rdi
0x1800272ef  push    r12
0x1800272f1  push    r13
0x1800272f3  push    r14
0x1800272f5  push    r15
0x1800272f7  mov     rbp, rsp
0x1800272fa  sub     rsp, 58h
0x1800272fe  mov     r15, rdx
0x180027301  mov     r12, rcx
0x180027304  xor     esi, esi
0x180027306  mov     [rbp+arg_30], esi
0x180027309  mov     [rbp+arg_28], esi
0x18002730c  xor     r13d, r13d
0x18002730f  xor     eax, eax
0x180027311  mov     [rbp+arg_0], rax
0x180027315  mov     [rcx], rax
0x180027318  mov     [rcx+8], ax
0x18002731c  mov     [rcx+60h], ax
0x180027320  lea     r14, [rcx+58h]
0x180027324  test    rdx, rdx
0x180027327  jnz     short loc_180027357
0x180027329  mov     eax, 80070057h
0x18002732e  mov     ebx, eax
0x180027330  lea     r9, aProvidernameAr; "ProviderName argument is null [%#x]"
0x180027337  mov     r8d, 23Fh
0x18002733d  mov     [rsp+58h+var_38], eax
0x180027341  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x180027348  mov     ecx, 1
0x18002734d  call    AslLogCallPrintf
0x180027352  jmp     loc_180027B1B
0x180027357  cmp     [r14], rax
0x18002735a  jz      short loc_180027374
0x18002735c  mov     ebx, 8000FFFFh
0x180027361  mov     [rsp+58h+var_38], ebx
0x180027365  lea     r9, aAlreadyInitial; "Already initialized [%#x]"
0x18002736c  mov     r8d, 246h
0x180027372  jmp     short loc_180027341
0x180027374  lea     rdi, [rcx+68h]
0x180027378  mov     rcx, rdi; this
0x18002737b  call    ?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)
0x180027380  mov     ebx, eax
0x180027382  test    eax, eax
0x180027384  jns     short loc_180027395
0x180027386  lea     r9, aInventorysynch_2; "InventorySynchronization:Initialize [%#"...
0x18002738d  mov     r8d, 24Dh
0x180027393  jmp     short loc_18002733D
0x180027395  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x18002739c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x1800273a1  xor     ebx, ebx
0x1800273a3  test    al, al
0x1800273a5  jz      loc_180027578
0x1800273ab  mov     rcx, [r12]
0x1800273af  test    rcx, rcx
0x1800273b2  jz      short loc_1800273D3
0x1800273b4  mov     rax, [rcx]
0x1800273b7  lea     rdx, [rbp+var_20]
0x1800273bb  mov     rax, [rax+40h]
0x1800273bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273c4  lea     esi, [rbx+1]
0x1800273c7  mov     [rbp+arg_30], esi
0x1800273ca  mov     rcx, [rax+8]
0x1800273ce  cmp     [rax], rcx
0x1800273d1  jnz     short loc_1800273D5
0x1800273d3  mov     bl, 1
0x1800273d5  test    sil, 1
0x1800273d9  jz      short loc_1800273EA
0x1800273db  and     esi, 0FFFFFFFEh
0x1800273de  mov     [rbp+arg_30], esi
0x1800273e1  lea     rcx, [rbp+var_20]
0x1800273e5  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x1800273ea  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x1800273f1  test    bl, bl
0x1800273f3  jz      short loc_180027412
0x1800273f5  mov     eax, 80070057h
0x1800273fa  mov     ebx, eax
0x1800273fc  mov     [rsp+58h+var_38], eax
0x180027400  lea     r9, aItemtemplateIs; "ItemTemplate is null or has no schema f"...
0x180027407  mov     r8d, 258h
0x18002740d  jmp     loc_180027348
0x180027412  mov     qword ptr [rsp+58h+var_38], r15
0x180027417  lea     r9, aUsingSqliteCac; "Using SQLite cache provider: %ls."
0x18002741e  mov     r8d, 25Dh
0x180027424  mov     ecx, 3
0x180027429  call    AslLogCallPrintf
0x18002742e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027435  mov     ecx, 0F0h; unsigned __int64
0x18002743a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002743f  mov     [rbp+arg_10], rax
0x180027443  test    rax, rax
0x180027446  jz      short loc_180027455
0x180027448  mov     rcx, rax; this
0x18002744b  call    ??0SqliteInvCache@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(void)
0x180027450  mov     rsi, rax
0x180027453  jmp     short loc_180027457
0x180027455  xor     esi, esi
0x180027457  test    rsi, rsi
0x18002745a  jz      loc_180027B16
0x180027460  mov     rcx, rdi; this
0x180027463  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180027468  mov     eax, dword ptr [rbp+arg_18]
0x18002746b  mov     [rsp+58h+var_38], eax; unsigned int
0x18002746f  xor     r9d, r9d; int
0x180027472  mov     r8, [r12]; struct IAmiInventoryItem *
0x180027476  mov     rdx, r15; Src
0x180027479  mov     rcx, rsi; this
0x18002747c  call    ?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z; Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)
0x180027481  mov     ebx, eax
0x180027483  test    eax, eax
0x180027485  js      short loc_1800274DE
0x180027487  mov     [r14], rsi
0x18002748a  mov     dword ptr [rbp+arg_10], 0
0x180027491  mov     rcx, [r12]
0x180027495  test    rcx, rcx
0x180027498  jz      short loc_180027513
0x18002749a  mov     rax, [rcx]
0x18002749d  mov     rax, [rax+38h]
0x1800274a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274a6  test    al, al
0x1800274a8  jz      short loc_180027513
0x1800274aa  mov     rcx, [r14]
0x1800274ad  mov     rax, [rcx]
0x1800274b0  lea     rdx, [rbp+arg_10]
0x1800274b4  mov     rax, [rax+20h]
0x1800274b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274bd  test    eax, eax
0x1800274bf  js      short loc_180027513
0x1800274c1  cmp     dword ptr [rbp+arg_10], 0
0x1800274c5  jbe     short loc_180027513
0x1800274c7  mov     rdx, r15; unsigned __int16 *
0x1800274ca  mov     rcx, r12; this
0x1800274cd  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x1800274d2  test    eax, eax
0x1800274d4  jz      short loc_180027513
0x1800274d6  mov     byte ptr [r12+61h], 1
0x1800274dc  jmp     short loc_180027513
0x1800274de  mov     [rsp+58h+var_38], eax
0x1800274e2  lea     r9, aSqliteinvcache; "SqliteInvCache::Initialize failed [%#x]"
0x1800274e9  mov     r8d, 27Eh
0x1800274ef  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x1800274f6  mov     ecx, 1
0x1800274fb  call    AslLogCallPrintf
0x180027500  mov     rax, [rsi]
0x180027503  mov     edx, 1
0x180027508  mov     rcx, rsi
0x18002750b  mov     rax, [rax]
0x18002750e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027513  cmp     byte ptr [rdi+24h], 0
0x180027517  jz      short loc_180027538
0x180027519  xor     cl, cl
0x18002751b  mov     rax, [rdi+18h]
0x18002751f  cmp     dword ptr [rax+4], 1
0x180027523  jnz     short loc_18002752A
0x180027525  mov     [rdi+24h], cl
0x180027528  mov     cl, 1
0x18002752a  or      r15d, 0FFFFFFFFh
0x18002752e  add     [rax+4], r15d
0x180027532  test    cl, cl
0x180027534  jz      short loc_18002756A
0x180027536  jmp     short loc_180027560
0x180027538  or      r15d, 0FFFFFFFFh
0x18002753c  mov     edx, r15d; dwMilliseconds
0x18002753f  mov     rcx, [rdi]; hHandle
0x180027542  call    cs:__imp_WaitForSingleObject
0x180027548  test    eax, eax
0x18002754a  jnz     short loc_18002756A
0x18002754c  mov     rax, [rdi+18h]
0x180027550  add     [rax], r15d
0x180027553  add     [rdi+20h], r15d
0x180027557  mov     rcx, [rdi]; hMutex
0x18002755a  call    cs:__imp_ReleaseMutex
0x180027560  mov     rcx, [rdi+10h]; hEvent
0x180027564  call    cs:__imp_SetEvent
0x18002756a  xor     sil, sil
0x18002756d  xor     eax, eax
0x18002756f  mov     [rbp+arg_0], rax
0x180027573  jmp     loc_180027857
0x180027578  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002757f  mov     ecx, 20h ; ' '; unsigned __int64
0x180027584  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027589  mov     rsi, rax
0x18002758c  mov     [rbp+hLibModule], rax
0x180027590  test    rax, rax
0x180027593  jz      loc_180027B16
0x180027599  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x1800275a0  mov     [rsi], rax
0x1800275a3  mov     [rsi+8], rbx
0x1800275a7  mov     [rsi+10h], rbx
0x1800275ab  mov     [rsi+18h], bl
0x1800275ae  test    rsi, rsi
0x1800275b1  jz      loc_180027B16
0x1800275b7  mov     rcx, rdi; this
0x1800275ba  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x1800275bf  xor     edx, edx; hFile
0x1800275c1  mov     r8d, 800h; dwFlags
0x1800275c7  lea     rcx, aAepicDll_0; "aepic.dll"
0x1800275ce  call    cs:__imp_LoadLibraryExW
0x1800275d4  mov     [rbp+hLibModule], rax
0x1800275d8  or      r15d, 0FFFFFFFFh
0x1800275dc  test    rax, rax
0x1800275df  jnz     short loc_1800275F8
0x1800275e1  call    cs:__imp_GetLastError
0x1800275e7  mov     ebx, eax
0x1800275e9  test    eax, eax
0x1800275eb  jle     short loc_18002765C
0x1800275ed  movzx   ebx, ax
0x1800275f0  or      ebx, 80070000h
0x1800275f6  jmp     short loc_18002765C
0x1800275f8  mov     edx, 64h ; 'd'; lpProcName
0x1800275fd  mov     rcx, rax; hModule
0x180027600  call    cs:__imp_GetProcAddress
0x180027606  test    rax, rax
0x180027609  jnz     short loc_180027612
0x18002760b  mov     ebx, 80004002h
0x180027610  jmp     short loc_180027652
0x180027612  mov     edi, 4
0x180027617  mov     r14, [rbp+Src]
0x18002761b  mov     r9d, 2
0x180027621  mov     r8, r14
0x180027624  xor     edx, edx
0x180027626  lea     rcx, [rsi+8]
0x18002762a  call    cs:__imp_InvCacheOpenVerProvider
0x180027630  mov     ebx, eax
0x180027632  test    eax, eax
0x180027634  jns     short loc_180027648
0x180027636  add     edi, r15d
0x180027639  jz      short loc_180027648
0x18002763b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180027640  call    cs:__imp_Sleep
0x180027646  jmp     short loc_18002761B
0x180027648  lea     rdi, [r12+68h]
0x18002764d  lea     r14, [r12+58h]
0x180027652  mov     rcx, [rbp+hLibModule]; hLibModule
0x180027656  call    cs:__imp_FreeLibrary
0x18002765c  test    ebx, ebx
0x18002765e  jns     short loc_1800276B7
0x180027660  mov     sil, 1
0x180027663  cmp     ebx, 80004002h
0x180027669  jz      short loc_180027690
0x18002766b  cmp     ebx, 80070005h
0x180027671  jz      short loc_180027690
0x180027673  cmp     ebx, 80070020h
0x180027679  jz      short loc_180027690
0x18002767b  cmp     ebx, 80070522h
0x180027681  jz      short loc_180027690
0x180027683  mov     ecx, 1
0x180027688  mov     r8d, 29Dh
0x18002768e  jmp     short loc_18002769B
0x180027690  mov     ecx, 3
0x180027695  mov     r8d, 299h
0x18002769b  lea     r9, aAepicinvcacheI; "AepicInvCache::Initialize failed [%#x]"
0x1800276a2  mov     [rsp+58h+var_38], ebx
0x1800276a6  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x1800276ad  call    AslLogCallPrintf
0x1800276b2  jmp     loc_18002785B
0x1800276b7  mov     rax, [rsi]
0x1800276ba  lea     r8, [rbp+arg_28]
0x1800276be  lea     rdx, aProviderversio; "ProviderVersion"
0x1800276c5  mov     rcx, rsi
0x1800276c8  mov     rax, [rax+48h]
0x1800276cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276d1  mov     ebx, eax
0x1800276d3  cmp     eax, 80070002h
0x1800276d8  jnz     short loc_180027719
0x1800276da  xor     eax, eax
0x1800276dc  mov     [rbp+arg_28], eax
0x1800276df  mov     ecx, dword ptr [rbp+arg_18]; this
0x1800276e2  cmp     ecx, r15d
0x1800276e5  jz      loc_180027770
0x1800276eb  mov     r8d, ecx; unsigned int
0x1800276ee  mov     rdx, rsi; struct Windows::Compat::Inventory::InventoryCache *
0x1800276f1  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x1800276f6  mov     ebx, eax
0x1800276f8  test    eax, eax
0x1800276fa  jns     short loc_18002770F
0x1800276fc  mov     [rsp+58h+var_38], eax
0x180027700  lea     r9, aTelcacheprovid_11; "TelCacheProvider::SetVersion [%#x]"
0x180027707  mov     r8d, 2B6h
0x18002770d  jmp     short loc_180027750
0x18002770f  mov     ecx, dword ptr [rbp+arg_18]
0x180027712  mov     eax, ecx
0x180027714  mov     [rbp+arg_28], ecx
0x180027717  jmp     short loc_180027770
0x180027719  test    ebx, ebx
0x18002771b  jns     short loc_18002776A
0x18002771d  mov     [rsp+58h+var_38], ebx
0x180027721  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x180027728  mov     r8d, 709h
0x18002772e  lea     rdx, aTelcacheprovid_17; "TelCacheProvider::GetVersion"
0x180027735  mov     ecx, 1
0x18002773a  call    AslLogCallPrintf
0x18002773f  mov     [rsp+58h+var_38], ebx
0x180027743  lea     r9, aTelcacheprovid_6; "TelCacheProvider::GetVersion failed [%#"...
0x18002774a  mov     r8d, 2ACh
0x180027750  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
  ... truncated ...
```
