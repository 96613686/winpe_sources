# TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)

- ea: `0x1801072ac`
- end: `0x180107b3d`
- name: `?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z`
- size: `2193`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180101fe0`

## callees

- `0x18000a594`
- `0x180012c54`
- `0x18001a2f4`
- `0x1800fe8a4`
- `0x1800fef90`
- `0x1800ff90c`
- `0x180106840`
- `0x180106a78`
- `0x180106f1c`
- `0x1801072ac`
- `0x1801091b4`
- `0x18010adf0`
- `0x18010aeec`
- `0x18010b7f0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18010742a`
- `KERNEL32!Sleep` at `0x18010742a`
- `KERNEL32!SetEvent` at `0x180107621`
- `KERNEL32!SetEvent` at `0x1801077ef`
- `KERNEL32!SetEvent` at `0x180107a3d`
- `KERNEL32!SetEvent` at `0x180107a99`
- `KERNEL32!SetEvent` at `0x180107621`
- `KERNEL32!SetEvent` at `0x1801077ef`
- `KERNEL32!SetEvent` at `0x180107a3d`
- `KERNEL32!SetEvent` at `0x180107a99`
- `KERNEL32!LoadLibraryExW` at `0x1801073b7`
- `KERNEL32!LoadLibraryExW` at `0x1801073b7`
- `KERNEL32!FreeLibrary` at `0x18010743d`
- `KERNEL32!FreeLibrary` at `0x18010743d`
- `KERNEL32!GetProcAddress` at `0x1801073e9`
- `KERNEL32!GetProcAddress` at `0x1801073e9`
- `KERNEL32!GetLastError` at `0x1801073ca`
- `KERNEL32!GetLastError` at `0x1801073ca`
- `KERNEL32!ReleaseMutex` at `0x180107617`
- `KERNEL32!ReleaseMutex` at `0x1801077e5`
- `KERNEL32!ReleaseMutex` at `0x180107a33`
- `KERNEL32!ReleaseMutex` at `0x180107a8f`
- `KERNEL32!ReleaseMutex` at `0x180107617`
- `KERNEL32!ReleaseMutex` at `0x1801077e5`
- `KERNEL32!ReleaseMutex` at `0x180107a33`
- `KERNEL32!ReleaseMutex` at `0x180107a8f`
- `KERNEL32!WaitForSingleObject` at `0x1801075ff`
- `KERNEL32!WaitForSingleObject` at `0x1801077cd`
- `KERNEL32!WaitForSingleObject` at `0x180107a1b`
- `KERNEL32!WaitForSingleObject` at `0x180107a77`
- `KERNEL32!WaitForSingleObject` at `0x1801075ff`
- `KERNEL32!WaitForSingleObject` at `0x1801077cd`
- `KERNEL32!WaitForSingleObject` at `0x180107a1b`
- `KERNEL32!WaitForSingleObject` at `0x180107a77`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x180107414`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x180107414`

## string_xrefs

- `0x1801073b0`: `aepic.dll`
- `0x180107308`: `Already initialized [%#x]`
- `0x18010768c`: `ItemTemplate is null or has no schema for SQLite cache provider [%#x]`
- `0x180107526`: `TelCacheProvider::GetVersion failed [%#x]`
- `0x180107486`: `AepicInvCache::Initialize failed [%#x]`
- `0x18010750d`: `TelCacheProvider::GetVersion`
- `0x180107500`: `InventoryCache::GetMetadata [%#x]`
- `0x1801074dd`: `TelCacheProvider::SetVersion [%#x]`
- `0x1801076aa`: `Using SQLite cache provider: %ls.`
- `0x180107943`: `Using SQLite cache provider: %ls.`
- `0x18010776b`: `SqliteInvCache::Initialize failed [%#x]`
- `0x1801079c6`: `SqliteInvCache::Initialize failed [%#x]`
- `0x18010789e`: `RtlArrayCache::Initialize failed [%#x]`
- `0x180107315`: `TelCacheProvider::Initialize`
- `0x18010748d`: `TelCacheProvider::Initialize`
- `0x180107536`: `TelCacheProvider::Initialize`
- `0x18010756d`: `TelCacheProvider::Initialize`
- `0x180107677`: `TelCacheProvider::Initialize`
- `0x180107778`: `TelCacheProvider::Initialize`
- `0x18010788f`: `TelCacheProvider::Initialize`
- `0x180107950`: `TelCacheProvider::Initialize`
- `0x1801079d3`: `TelCacheProvider::Initialize`
- `0x1801078c6`: `Using in-memory cache provider: %ls.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TelCacheProvider::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6)
{
  _QWORD *v6; // rsi
  int v7; // r14d
  Windows::Compat::Inventory::RtlArrayCache *v8; // r12
  struct Windows::Compat::Inventory::InventoryCache *v9; // r13
  Windows::Compat::Inventory::InventorySynchronization *v10; // rbx
  int v11; // edi
  const char *v12; // r9
  __int64 v13; // r8
  int v14; // eax
  struct Windows::Compat::Inventory::InventoryCache *v15; // r14
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v18; // edi
  int v19; // r13d
  char v20; // r14
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  TelCacheProvider *v24; // rcx
  int v25; // eax
  int v26; // eax
  char v27; // cl
  __int64 v28; // rax
  _QWORD *v29; // rax
  char v30; // di
  Windows::Compat::Inventory::SqliteInvCache *v31; // rax
  Windows::Compat::Inventory::SqliteInvCache *v32; // rdi
  const unsigned __int16 *v33; // rdx
  int v34; // eax
  char v35; // cl
  __int64 v36; // rax
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  _QWORD *v39; // rax
  char v40; // dl
  char v41; // di
  Windows::Compat::Inventory::SqliteInvCache *v42; // rax
  Windows::Compat::Inventory::SqliteInvCache *v43; // rdi
  const unsigned __int16 *v44; // rdx
  int v45; // eax
  char v46; // cl
  __int64 v47; // rax
  char v48; // cl
  __int64 v49; // rax
  void (__fastcall ***v50)(_QWORD, __int64); // rcx
  int v52; // [rsp+20h] [rbp-48h]
  unsigned int v53[2]; // [rsp+20h] [rbp-48h]
  unsigned int v54; // [rsp+20h] [rbp-48h]
  unsigned int v55; // [rsp+20h] [rbp-48h]
  HMODULE hLibModule; // [rsp+30h] [rbp-38h]
  _BYTE v57[40]; // [rsp+40h] [rbp-28h] BYREF
  int v59; // [rsp+C8h] [rbp+60h] BYREF

  v6 = (_QWORD *)a1;
  v7 = 0;
  a5 = 0;
  v59 = 0;
  v8 = 0;
  v9 = 0;
  *(_QWORD *)a1 = a3;
  *(_WORD *)(a1 + 8) = 0;
  *(_WORD *)(a1 + 96) = 0;
  v10 = (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 104);
  if ( !*(_QWORD *)(a1 + 88) )
  {
    v14 = Windows::Compat::Inventory::InventorySynchronization::Initialize(
            (Windows::Compat::Inventory::InventorySynchronization *)(a1 + 104),
            a2);
    v11 = v14;
    if ( v14 < 0 )
    {
      v52 = v14;
      v12 = "InventorySynchronization:Initialize [%#x]";
      v13 = 589;
      goto LABEL_3;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
    {
      v15 = (struct Windows::Compat::Inventory::InventoryCache *)operator new(
                                                                   0x20u,
                                                                   (const struct std::nothrow_t *)&std::nothrow);
      if ( v15 )
      {
        *(_QWORD *)v15 = &Windows::Compat::Inventory::AepicInvCache::`vftable';
        *((_QWORD *)v15 + 1) = 0;
        *((_QWORD *)v15 + 2) = 0;
        *((_BYTE *)v15 + 24) = 0;
        Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v10);
        Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
        hLibModule = Library;
        if ( Library )
        {
          if ( GetProcAddress(Library, (LPCSTR)0x64) )
          {
            v19 = 4;
            while ( 1 )
            {
              v18 = InvCacheOpenVerProvider((char *)v15 + 8, 0, L"Mare", 2);
              if ( v18 >= 0 )
                break;
              if ( !--v19 )
                break;
              Sleep(0x64u);
            }
            v6 = (_QWORD *)a1;
            v9 = 0;
          }
          else
          {
            v18 = -2147467262;
          }
          FreeLibrary(hLibModule);
        }
        else
        {
          LastError = GetLastError();
          v18 = LastError;
          if ( LastError > 0 )
            v18 = (unsigned __int16)LastError | 0x80070000;
        }
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
          AslLogCallPrintf(v21, "TelCacheProvider::Initialize", v22, "AepicInvCache::Initialize failed [%#x]", v18);
LABEL_81:
          if ( v6[11] )
          {
LABEL_112:
            v11 = 0;
            v8 = 0;
LABEL_113:
            if ( !v20 )
              goto LABEL_122;
LABEL_114:
            if ( *((_BYTE *)v10 + 36) )
            {
              v48 = 0;
              v49 = *((_QWORD *)v10 + 3);
              if ( *(_DWORD *)(v49 + 4) == 1 )
              {
                *((_BYTE *)v10 + 36) = 0;
                v48 = 1;
              }
              --*(_DWORD *)(v49 + 4);
              if ( !v48 )
              {
LABEL_122:
                if ( v11 >= 0 )
                  goto LABEL_130;
                goto LABEL_123;
              }
            }
            else
            {
              if ( WaitForSingleObject(*(HANDLE *)v10, 0xFFFFFFFF) )
                goto LABEL_122;
              --**((_DWORD **)v10 + 3);
              --*((_DWORD *)v10 + 8);
              ReleaseMutex(*(HANDLE *)v10);
            }
            SetEvent(*((HANDLE *)v10 + 2));
            goto LABEL_122;
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
          {
            v8 = (Windows::Compat::Inventory::RtlArrayCache *)operator new(
                                                                0x38u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
            if ( v8 )
            {
              *(_QWORD *)v8 = &Windows::Compat::Inventory::RtlArrayCache::`vftable';
              *((_QWORD *)v8 + 1) = 0;
              *((_QWORD *)v8 + 2) = 0;
              *((_QWORD *)v8 + 3) = 0;
              *((_QWORD *)v8 + 4) = 0;
              *((_QWORD *)v8 + 5) = 0;
              *((_QWORD *)v8 + 6) = 0;
              v38 = Windows::Compat::Inventory::RtlArrayCache::Initialize(v8, v37);
              v11 = v38;
              if ( v38 < 0 )
              {
                AslLogCallPrintf(1, "TelCacheProvider::Initialize", 783, "RtlArrayCache::Initialize failed [%#x]", v38);
                goto LABEL_113;
              }
              AslLogCallPrintf(3, "TelCacheProvider::Initialize", 787, "Using in-memory cache provider: %ls.", L"Mare");
              v6[11] = v8;
              goto LABEL_112;
            }
            v8 = 0;
LABEL_100:
            v11 = -2147024882;
            goto LABEL_113;
          }
          if ( *v6 )
          {
            v39 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v6 + 64LL))(*v6, v57);
            v40 = a5 | 2;
            if ( *v39 != v39[1] )
            {
              v41 = 1;
              goto LABEL_93;
            }
          }
          else
          {
            v40 = a5;
          }
          v41 = 0;
LABEL_93:
          if ( (v40 & 2) != 0 )
            std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v57);
          if ( !v41 )
            goto LABEL_112;
          AslLogCallPrintf(3, "TelCacheProvider::Initialize", 745, "Using SQLite cache provider: %ls.", L"Mare");
          v42 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                                0xF0u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
          if ( v42 )
            v43 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v42);
          else
            v43 = 0;
          if ( !v43 )
            goto LABEL_100;
          Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v10);
          v20 = 1;
          v45 = Windows::Compat::Inventory::SqliteInvCache::Initialize(
                  v43,
                  v44,
                  (struct IAmiInventoryItem *)*v6,
                  1,
                  v55);
          if ( v45 >= 0 )
          {
            v6[11] = v43;
            goto LABEL_112;
          }
          AslLogCallPrintf(1, "TelCacheProvider::Initialize", 763, "SqliteInvCache::Initialize failed [%#x]", v45);
          (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v43)(v43, 1);
          if ( *((_BYTE *)v10 + 36) )
          {
            v46 = 0;
            v47 = *((_QWORD *)v10 + 3);
            if ( *(_DWORD *)(v47 + 4) == 1 )
            {
              *((_BYTE *)v10 + 36) = 0;
              v46 = 1;
            }
            --*(_DWORD *)(v47 + 4);
            if ( !v46 )
              goto LABEL_111;
          }
          else
          {
            if ( WaitForSingleObject(*(HANDLE *)v10, 0xFFFFFFFF) )
            {
LABEL_111:
              v20 = 0;
              goto LABEL_112;
            }
            --**((_DWORD **)v10 + 3);
            --*((_DWORD *)v10 + 8);
            ReleaseMutex(*(HANDLE *)v10);
          }
          SetEvent(*((HANDLE *)v10 + 2));
          goto LABEL_111;
        }
        v23 = (*(__int64 (__fastcall **)(struct Windows::Compat::Inventory::InventoryCache *, const wchar_t *, int *))(*(_QWORD *)v15 + 72LL))(
                v15,
                L"ProviderVersion",
                &v59);
        v11 = v23;
        if ( v23 == -2147024894 )
        {
          v59 = 0;
          v25 = TelCacheProvider::SetVersion(v24, v15, 0);
          v11 = v25;
          if ( v25 < 0 )
          {
            AslLogCallPrintf(1, "TelCacheProvider::Initialize", 694, "TelCacheProvider::SetVersion [%#x]", v25);
LABEL_33:
            v9 = v15;
            goto LABEL_114;
          }
          v26 = 0;
          v59 = 0;
        }
        else
        {
          if ( v23 < 0 )
          {
            AslLogCallPrintf(1, "TelCacheProvider::GetVersion", 1801, "InventoryCache::GetMetadata [%#x]", v23);
            v53[0] = v11;
            AslLogCallPrintf(
              1,
              "TelCacheProvider::Initialize",
              684,
              "TelCacheProvider::GetVersion failed [%#x]",
              *(_QWORD *)v53);
            goto LABEL_33;
          }
          v26 = v59;
        }
        v9 = v15;
        if ( v26 )
        {
          AslLogCallPrintf(
            3,
            "TelCacheProvider::Initialize",
            702,
            "%ls ProviderVersion did not match RequestedVersion.",
            L"Mare");
        }
        else
        {
          v6[11] = v15;
          v9 = 0;
          a6 = 0;
          if ( *v6
            && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 56LL))(*v6)
            && (*(int (__fastcall **)(_QWORD, int *))(*(_QWORD *)v6[11] + 32LL))(v6[11], &a6) >= 0
            && a6
            && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)v6, L"Mare") )
          {
            *((_BYTE *)v6 + 97) = 1;
          }
        }
        if ( *((_BYTE *)v10 + 36) )
        {
          v27 = 0;
          v28 = *((_QWORD *)v10 + 3);
          if ( *(_DWORD *)(v28 + 4) == 1 )
          {
            *((_BYTE *)v10 + 36) = 0;
            v27 = 1;
          }
          --*(_DWORD *)(v28 + 4);
          if ( !v27 )
            goto LABEL_51;
        }
        else
        {
          if ( WaitForSingleObject(*(HANDLE *)v10, 0xFFFFFFFF) )
          {
LABEL_51:
            v20 = 0;
            goto LABEL_81;
          }
          --**((_DWORD **)v10 + 3);
          --*((_DWORD *)v10 + 8);
          ReleaseMutex(*(HANDLE *)v10);
        }
        SetEvent(*((HANDLE *)v10 + 2));
        goto LABEL_51;
      }
LABEL_63:
      v11 = -2147024882;
      goto LABEL_123;
    }
    if ( !*v6
      || (v29 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v6 + 64LL))(*v6, v57),
          v7 = 1,
          a5 = 1,
          v30 = 0,
          *v29 == v29[1]) )
    {
      v30 = 1;
    }
    if ( (v7 & 1) != 0 )
    {
      a5 = v7 & 0xFFFFFFFE;
      std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(v57);
    }
    if ( v30 )
    {
      v11 = -2147024809;
      v52 = -2147024809;
      v12 = "ItemTemplate is null or has no schema for SQLite cache provider [%#x]";
      v13 = 600;
      goto LABEL_3;
    }
    AslLogCallPrintf(3, "TelCacheProvider::Initialize", 605, "Using SQLite cache provider: %ls.", L"Mare");
    v31 = (Windows::Compat::Inventory::SqliteInvCache *)operator new(
                                                          0xF0u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    if ( v31 )
      v32 = (Windows::Compat::Inventory::SqliteInvCache *)Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(v31);
    else
      v32 = 0;
    if ( !v32 )
      goto LABEL_63;
    Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(v10);
    v34 = Windows::Compat::Inventory::SqliteInvCache::Initialize(v32, v33, (struct IAmiInventoryItem *)*v6, 0, v54);
    if ( v34 < 0 )
    {
      AslLogCallPrintf(1, "TelCacheProvider::Initialize", 638, "SqliteInvCache::Initialize failed [%#x]", v34);
      (**(void (__fastcall ***)(Windows::Compat::Inventory::SqliteInvCache *, __int64))v32)(v32, 1);
    }
    else
    {
      v6[11] = v32;
      a6 = 0;
      if ( *v6
        && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 56LL))(*v6)
        && (*(int (__fastcall **)(_QWORD, int *))(*(_QWORD *)v6[11] + 32LL))(v6[11], &a6) >= 0
        && a6
        && (unsigned int)TelCacheProvider::ShouldForceFullSync((TelCacheProvider *)v6, L"Mare") )
      {
        *((_BYTE *)v6 + 97) = 1;
      }
    }
    if ( *((_BYTE *)v10 + 36) )
    {
      v35 = 0;
      v36 = *((_QWORD *)v10 + 3);
      if ( *(_DWORD *)(v36 + 4) == 1 )
      {
        *((_BYTE *)v10 + 36) = 0;
        v35 = 1;
      }
      --*(_DWORD *)(v36 + 4);
      if ( !v35 )
        goto LABEL_80;
    }
    else
    {
      if ( WaitForSingleObject(*(HANDLE *)v10, 0xFFFFFFFF) )
      {
LABEL_80:
        v20 = 0;
        v9 = 0;
        goto LABEL_81;
      }
      --**((_DWORD **)v10 + 3);
      --*((_DWORD *)v10 + 8);
      ReleaseMutex(*(HANDLE *)v10);
    }
    SetEvent(*((HANDLE *)v10 + 2));
    goto LABEL_80;
  }
  v11 = -2147418113;
  v52 = -2147418113;
  v12 = "Already initialized [%#x]";
  v13 = 582;
LABEL_3:
  AslLogCallPrintf(1, "TelCacheProvider::Initialize", v13, v12, v52);
LABEL_123:
  if ( *((_BYTE *)v6 + 97) )
  {
    TelCacheProvider::SendNewSyncAdds((TelCacheProvider *)v6);
    *((_BYTE *)v6 + 97) = 0;
  }
  if ( *v6 )
  {
    (**(void (__fastcall ***)(_QWORD, __int64))*v6)(*v6, 1);
    *v6 = 0;
  }
  v50 = (void (__fastcall ***)(_QWORD, __int64))v6[11];
  if ( v50 )
  {
    (**v50)(v50, 1);
    v6[11] = 0;
  }
  Windows::Compat::Inventory::InventorySynchronization::Uninitialize(v10);
LABEL_130:
  if ( v9 )
    (**(void (__fastcall ***)(struct Windows::Compat::Inventory::InventoryCache *, __int64))v9)(v9, 1);
  if ( v8 )
    (**(void (__fastcall ***)(Windows::Compat::Inventory::RtlArrayCache *, __int64))v8)(v8, 1);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801072ac  mov     [rsp-40h+arg_18], r9d
0x1801072b1  mov     [rsp-40h+arg_0], rcx
0x1801072b6  push    rbp
0x1801072b7  push    rbx
0x1801072b8  push    rsi
0x1801072b9  push    rdi
0x1801072ba  push    r12
0x1801072bc  push    r13
0x1801072be  push    r14
0x1801072c0  push    r15
0x1801072c2  mov     rbp, rsp
0x1801072c5  sub     rsp, 68h
0x1801072c9  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x1801072d1  mov     rsi, rcx
0x1801072d4  xor     r15d, r15d
0x1801072d7  mov     r14d, r15d
0x1801072da  mov     [rbp+arg_20], r15d
0x1801072de  mov     [rbp+arg_18], r15d
0x1801072e2  mov     r12d, r15d
0x1801072e5  mov     r13d, r15d
0x1801072e8  mov     [rcx], r8
0x1801072eb  mov     [rcx+8], r15w
0x1801072f0  mov     [rcx+60h], r15w
0x1801072f5  lea     rbx, [rcx+68h]
0x1801072f9  cmp     [rcx+58h], r15
0x1801072fd  jz      short loc_18010732B
0x1801072ff  mov     edi, 8000FFFFh
0x180107304  mov     [rsp+68h+var_48], edi
0x180107308  lea     r9, aAlreadyInitial; "Already initialized [%#x]"
0x18010730f  mov     r8d, 246h
0x180107315  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x18010731c  mov     ecx, 1
0x180107321  call    AslLogCallPrintf
0x180107326  jmp     loc_180107AA6
0x18010732b  mov     rcx, rbx; this
0x18010732e  call    ?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z; Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)
0x180107333  mov     edi, eax
0x180107335  test    eax, eax
0x180107337  jns     short loc_18010734C
0x180107339  mov     [rsp+68h+var_48], eax
0x18010733d  lea     r9, aInventorysynch_2; "InventorySynchronization:Initialize [%#"...
0x180107344  mov     r8d, 24Dh
0x18010734a  jmp     short loc_180107315
0x18010734c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180107353  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180107358  test    al, al
0x18010735a  jnz     loc_18010762F
0x180107360  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180107367  mov     ecx, 20h ; ' '; unsigned __int64
0x18010736c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180107371  mov     r14, rax
0x180107374  mov     [rbp+hLibModule], rax
0x180107378  test    rax, rax
0x18010737b  jz      loc_1801076F0
0x180107381  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x180107388  mov     [r14], rax
0x18010738b  mov     [r14+8], r15
0x18010738f  mov     [r14+10h], r15
0x180107393  mov     [r14+18h], r15b
0x180107397  test    r14, r14
0x18010739a  jz      loc_1801076F0
0x1801073a0  mov     rcx, rbx; this
0x1801073a3  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x1801073a8  xor     edx, edx; hFile
0x1801073aa  mov     r8d, 800h; dwFlags
0x1801073b0  lea     rcx, aAepicDll_0; "aepic.dll"
0x1801073b7  call    cs:__imp_LoadLibraryExW
0x1801073bd  mov     [rbp+hLibModule], rax
0x1801073c1  or      r15d, 0FFFFFFFFh
0x1801073c5  test    rax, rax
0x1801073c8  jnz     short loc_1801073E1
0x1801073ca  call    cs:__imp_GetLastError
0x1801073d0  mov     edi, eax
0x1801073d2  test    eax, eax
0x1801073d4  jle     short loc_180107443
0x1801073d6  movzx   edi, ax
0x1801073d9  or      edi, 80070000h
0x1801073df  jmp     short loc_180107443
0x1801073e1  mov     edx, 64h ; 'd'; lpProcName
0x1801073e6  mov     rcx, rax; hModule
0x1801073e9  call    cs:__imp_GetProcAddress
0x1801073ef  test    rax, rax
0x1801073f2  jnz     short loc_1801073FB
0x1801073f4  mov     edi, 80004002h
0x1801073f9  jmp     short loc_180107439
0x1801073fb  mov     r13d, 4
0x180107401  mov     r9d, 2
0x180107407  lea     r8, aMare; "Mare"
0x18010740e  xor     edx, edx
0x180107410  lea     rcx, [r14+8]
0x180107414  call    cs:__imp_InvCacheOpenVerProvider
0x18010741a  mov     edi, eax
0x18010741c  test    eax, eax
0x18010741e  jns     short loc_180107432
0x180107420  add     r13d, r15d
0x180107423  jz      short loc_180107432
0x180107425  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18010742a  call    cs:__imp_Sleep
0x180107430  jmp     short loc_180107401
0x180107432  mov     rsi, [rbp+arg_0]
0x180107436  mov     r13, r12
0x180107439  mov     rcx, [rbp+hLibModule]; hLibModule
0x18010743d  call    cs:__imp_FreeLibrary
0x180107443  test    edi, edi
0x180107445  jns     short loc_18010749E
0x180107447  mov     r14b, 1
0x18010744a  cmp     edi, 80004002h
0x180107450  jz      short loc_180107477
0x180107452  cmp     edi, 80070005h
0x180107458  jz      short loc_180107477
0x18010745a  cmp     edi, 80070020h
0x180107460  jz      short loc_180107477
0x180107462  cmp     edi, 80070522h
0x180107468  jz      short loc_180107477
0x18010746a  mov     ecx, 1
0x18010746f  mov     r8d, 29Dh
0x180107475  jmp     short loc_180107482
0x180107477  mov     ecx, 3
0x18010747c  mov     r8d, 299h
0x180107482  mov     [rsp+68h+var_48], edi
0x180107486  lea     r9, aAepicinvcacheI; "AepicInvCache::Initialize failed [%#x]"
0x18010748d  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x180107494  call    AslLogCallPrintf
0x180107499  jmp     loc_1801077FB
0x18010749e  mov     rax, [r14]
0x1801074a1  lea     r8, [rbp+arg_18]
0x1801074a5  lea     rdx, aProviderversio; "ProviderVersion"
0x1801074ac  mov     rcx, r14
0x1801074af  mov     rax, [rax+48h]
0x1801074b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801074b8  mov     edi, eax
0x1801074ba  cmp     eax, 80070002h
0x1801074bf  jnz     short loc_1801074F8
0x1801074c1  mov     [rbp+arg_18], 0
0x1801074c8  xor     r8d, r8d; unsigned int
0x1801074cb  mov     rdx, r14; struct Windows::Compat::Inventory::InventoryCache *
0x1801074ce  call    ?SetVersion@TelCacheProvider@@AEAAJPEAVInventoryCache@Inventory@Compat@Windows@@K@Z; TelCacheProvider::SetVersion(Windows::Compat::Inventory::InventoryCache *,ulong)
0x1801074d3  mov     edi, eax
0x1801074d5  test    eax, eax
0x1801074d7  jns     short loc_1801074F1
0x1801074d9  mov     [rsp+68h+var_48], eax
0x1801074dd  lea     r9, aTelcacheprovid_11; "TelCacheProvider::SetVersion [%#x]"
0x1801074e4  mov     r8d, 2B6h
0x1801074ea  mov     ecx, 1
0x1801074ef  jmp     short loc_180107536
0x1801074f1  xor     eax, eax
0x1801074f3  mov     [rbp+arg_18], eax
0x1801074f6  jmp     short loc_18010754D
0x1801074f8  test    edi, edi
0x1801074fa  jns     short loc_18010754A
0x1801074fc  mov     [rsp+68h+var_48], edi
0x180107500  lea     r9, aInventorycache_0; "InventoryCache::GetMetadata [%#x]"
0x180107507  mov     r8d, 709h
0x18010750d  lea     rdx, aTelcacheprovid_18; "TelCacheProvider::GetVersion"
0x180107514  mov     r13d, 1
0x18010751a  mov     ecx, r13d
0x18010751d  call    AslLogCallPrintf
0x180107522  mov     [rsp+68h+var_48], edi
0x180107526  lea     r9, aTelcacheprovid_7; "TelCacheProvider::GetVersion failed [%#"...
0x18010752d  mov     r8d, 2ACh
0x180107533  mov     ecx, r13d
0x180107536  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x18010753d  call    AslLogCallPrintf
0x180107542  mov     r13, r14
0x180107545  jmp     loc_180107A50
0x18010754a  mov     eax, [rbp+arg_18]
0x18010754d  mov     r13, r14
0x180107550  test    eax, eax
0x180107552  jz      short loc_180107580
0x180107554  lea     rdx, aMare; "Mare"
0x18010755b  mov     qword ptr [rsp+68h+var_48], rdx
0x180107560  lea     r9, aLsProvidervers; "%ls ProviderVersion did not match Reque"...
0x180107567  mov     r8d, 2BEh
0x18010756d  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x180107574  mov     ecx, 3
0x180107579  call    AslLogCallPrintf
0x18010757e  jmp     short loc_1801075D8
0x180107580  mov     [rsi+58h], r13
0x180107584  xor     r13d, r13d
0x180107587  mov     [rbp+arg_28], r13d
0x18010758b  mov     rcx, [rsi]
0x18010758e  test    rcx, rcx
0x180107591  jz      short loc_1801075D8
0x180107593  mov     rax, [rcx]
0x180107596  mov     rax, [rax+38h]
0x18010759a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010759f  test    al, al
0x1801075a1  jz      short loc_1801075D8
0x1801075a3  mov     rcx, [rsi+58h]
0x1801075a7  mov     rax, [rcx]
0x1801075aa  lea     rdx, [rbp+arg_28]
0x1801075ae  mov     rax, [rax+20h]
0x1801075b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801075b7  test    eax, eax
0x1801075b9  js      short loc_1801075D8
0x1801075bb  cmp     [rbp+arg_28], r13d
0x1801075bf  jbe     short loc_1801075D8
0x1801075c1  lea     rdx, aMare; "Mare"
0x1801075c8  mov     rcx, rsi; this
0x1801075cb  call    ?ShouldForceFullSync@TelCacheProvider@@AEAAHPEBG@Z; TelCacheProvider::ShouldForceFullSync(ushort const *)
0x1801075d0  test    eax, eax
0x1801075d2  jz      short loc_1801075D8
0x1801075d4  mov     byte ptr [rsi+61h], 1
0x1801075d8  cmp     byte ptr [rbx+24h], 0
0x1801075dc  jz      short loc_1801075F9
0x1801075de  xor     cl, cl
0x1801075e0  mov     rax, [rbx+18h]
0x1801075e4  cmp     dword ptr [rax+4], 1
0x1801075e8  jnz     short loc_1801075EF
0x1801075ea  mov     [rbx+24h], cl
0x1801075ed  mov     cl, 1
0x1801075ef  add     [rax+4], r15d
0x1801075f3  test    cl, cl
0x1801075f5  jz      short loc_180107627
0x1801075f7  jmp     short loc_18010761D
0x1801075f9  mov     edx, r15d; dwMilliseconds
0x1801075fc  mov     rcx, [rbx]; hHandle
0x1801075ff  call    cs:__imp_WaitForSingleObject
0x180107605  test    eax, eax
0x180107607  jnz     short loc_180107627
0x180107609  mov     rax, [rbx+18h]
0x18010760d  add     [rax], r15d
0x180107610  add     [rbx+20h], r15d
0x180107614  mov     rcx, [rbx]; hMutex
0x180107617  call    cs:__imp_ReleaseMutex
0x18010761d  mov     rcx, [rbx+10h]; hEvent
0x180107621  call    cs:__imp_SetEvent
0x180107627  xor     r14b, r14b
0x18010762a  jmp     loc_1801077FB
0x18010762f  mov     rcx, [rsi]
0x180107632  test    rcx, rcx
0x180107635  jz      short loc_18010765D
0x180107637  mov     rax, [rcx]
0x18010763a  lea     rdx, [rbp+var_28]
0x18010763e  mov     rax, [rax+40h]
0x180107642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107647  mov     r14d, 1
0x18010764d  mov     [rbp+arg_20], r14d
0x180107651  mov     rcx, [rax+8]
0x180107655  cmp     [rax], rcx
0x180107658  mov     dil, r15b
0x18010765b  jnz     short loc_180107660
0x18010765d  mov     dil, 1
0x180107660  test    r14b, 1
0x180107664  jz      short loc_180107677
0x180107666  and     r14d, 0FFFFFFFEh
0x18010766a  mov     [rbp+arg_20], r14d
0x18010766e  lea     rcx, [rbp+var_28]
0x180107672  call    ??1?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@QEAA@XZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::~vector<IAmiInventoryItem::_CacheItemProperty>(void)
0x180107677  lea     rdx, aTelcacheprovid_13; "TelCacheProvider::Initialize"
0x18010767e  test    dil, dil
0x180107681  jz      short loc_18010769E
0x180107683  mov     edi, 80070057h
0x180107688  mov     [rsp+68h+var_48], edi
0x18010768c  lea     r9, aItemtemplateIs; "ItemTemplate is null or has no schema f"...
0x180107693  mov     r8d, 258h
0x180107699  jmp     loc_18010731C
0x18010769e  lea     r14, aMare; "Mare"
0x1801076a5  mov     qword ptr [rsp+68h+var_48], r14; unsigned int
0x1801076aa  lea     r9, aUsingSqliteCac; "Using SQLite cache provider: %ls."
0x1801076b1  mov     r8d, 25Dh
0x1801076b7  mov     ecx, 3
0x1801076bc  call    AslLogCallPrintf
0x1801076c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801076c8  mov     ecx, 0F0h; unsigned __int64
0x1801076cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801076d2  mov     [rbp+arg_0], rax
0x1801076d6  test    rax, rax
0x1801076d9  jz      short loc_1801076E8
0x1801076db  mov     rcx, rax; this
0x1801076de  call    ??0SqliteInvCache@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::SqliteInvCache::SqliteInvCache(void)
0x1801076e3  mov     rdi, rax
0x1801076e6  jmp     short loc_1801076EB
0x1801076e8  mov     rdi, r15
0x1801076eb  test    rdi, rdi
0x1801076ee  jnz     short loc_1801076FA
0x1801076f0  mov     edi, 8007000Eh
0x1801076f5  jmp     loc_180107AA6
0x1801076fa  mov     rcx, rbx; this
0x1801076fd  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x180107702  xor     r9d, r9d; int
0x180107705  mov     r8, [rsi]; struct IAmiInventoryItem *
0x180107708  mov     rcx, rdi; this
0x18010770b  call    ?Initialize@SqliteInvCache@Inventory@Compat@Windows@@QEAAJPEBGPEAVIAmiInventoryItem@@HK@Z; Windows::Compat::Inventory::SqliteInvCache::Initialize(ushort const *,IAmiInventoryItem *,int,ulong)
0x180107710  test    eax, eax
0x180107712  js      short loc_180107767
0x180107714  mov     [rsi+58h], rdi
0x180107718  mov     [rbp+arg_28], r15d
0x18010771c  mov     rcx, [rsi]
0x18010771f  test    rcx, rcx
0x180107722  jz      short loc_18010779C
0x180107724  mov     rax, [rcx]
0x180107727  mov     rax, [rax+38h]
0x18010772b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107730  test    al, al
0x180107732  jz      short loc_18010779C
0x180107734  mov     rcx, [rsi+58h]
0x180107738  mov     rax, [rcx]
0x18010773b  lea     rdx, [rbp+arg_28]
0x18010773f  mov     rax, [rax+20h]
  ... truncated ...
```
