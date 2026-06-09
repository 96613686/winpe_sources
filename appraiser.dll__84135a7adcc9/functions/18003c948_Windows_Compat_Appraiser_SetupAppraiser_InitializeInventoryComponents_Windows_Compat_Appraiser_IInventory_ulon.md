# Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents(Windows::Compat::Appraiser::IInventory * * &,ulong &,Windows::Compat::Appraiser::RunOptions &,Windows::Compat::Appraiser::DataFile &,Windows::Compat::Appraiser::ValidInventoryComponents &)

- ea: `0x18003c948`
- end: `0x18003d6ef`
- name: `?InitializeInventoryComponents@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEAPEAPEAVIInventory@234@AEAKAEAURunOptions@234@AEAVDataFile@234@AEAUValidInventoryComponents@234@@Z`
- size: `3495`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct Windows::Compat::Appraiser::IInventory ***, unsigned int *, struct Windows::Compat::Appraiser::RunOptions *, struct Windows::Compat::Appraiser::DataFile *, struct Windows::Compat::Appraiser::ValidInventoryComponents *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b30c`

## callees

- `0x18000147c`
- `0x180008570`
- `0x18000a594`
- `0x18000a5b8`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180038f10`
- `0x18003c948`
- `0x180046c7c`
- `0x180082f0c`
- `0x180096ef0`
- `0x1800b6d60`
- `0x1800bd43c`
- `0x1800c1db0`
- `0x1800c4970`
- `0x1801ac054`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18003d1f4`
- `KERNEL32!GetSystemTime` at `0x18003d448`
- `KERNEL32!GetSystemTime` at `0x18003d1f4`
- `KERNEL32!GetSystemTime` at `0x18003d448`
- `KERNEL32!GetProcessHeap` at `0x18003c9b0`
- `KERNEL32!GetProcessHeap` at `0x18003c9b0`
- `KERNEL32!HeapFree` at `0x18003d6c4`
- `KERNEL32!HeapFree` at `0x18003d6c4`
- `SHLWAPI!PathFileExistsW` at `0x18003cbe4`
- `SHLWAPI!PathFileExistsW` at `0x18003cc28`
- `SHLWAPI!PathFileExistsW` at `0x18003cbe4`
- `SHLWAPI!PathFileExistsW` at `0x18003cc28`

## string_xrefs

- `0x18003ca6a`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003caa6`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003ca76`: `Failed to copy path: [0x%x].`
- `0x18003cab5`: `Failed to copy path: [0x%x].`
- `0x18003caf2`: `Failed to copy path: [0x%x].`
- `0x18003cb1c`: `Failed to copy path: [0x%x].`
- `0x18003cb73`: `Failed to copy path: [0x%x].`
- `0x18003cbc6`: `Failed to copy path: [0x%x].`
- `0x18003ca63`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents`
- `0x18003ca9f`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents`
- `0x18003ca47`: `%hs_APPRAISER_ApplicationInventory.xml`
- `0x18003cb33`: `compatAppraiserResources.dll`
- `0x18003cacc`: `acres.dll`
- `0x18003cb8a`: `%hs_APPRAISER_DeviceInventory.xml`
- `0x18003ccea`: `String copy failed: [0x%x].`
- `0x18003cd44`: `String copy failed: [0x%x].`
- `0x18003d091`: `Windows::Compat::Appraiser::InboxComponentInventory::Initialize`
- `0x18003d0da`: `Windows::Compat::Appraiser::InboxComponentInventory::Initialize`
- `0x18003d279`: `Windows::Compat::Appraiser::InboxComponentInventory::Initialize`
- `0x18003d08a`: `Failed to copy resource path string: [0x%x].`
- `0x18003d0d1`: `Failed to copy resource path string: [0x%x].`
- `0x18003d272`: `Failed to copy resource path string: [0x%x].`
- `0x18003d098`: `onecore\base\appcompat\appraiser\inventory\inboxcomponentinventory.cpp`
- `0x18003d0e1`: `onecore\base\appcompat\appraiser\inventory\inboxcomponentinventory.cpp`
- `0x18003d280`: `onecore\base\appcompat\appraiser\inventory\inboxcomponentinventory.cpp`
- `0x18003ccfa`: `Windows::Compat::Appraiser::WicaApplicationInventory::Initialize`
- `0x18003cd4b`: `Windows::Compat::Appraiser::WicaApplicationInventory::Initialize`
- `0x18003cd01`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`
- `0x18003cd52`: `onecore\base\appcompat\appraiser\inventory\applicationinventory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::IInventory ***a2,
        unsigned int *a3,
        struct Windows::Compat::Appraiser::RunOptions *a4,
        struct Windows::Compat::Appraiser::DataFile *a5,
        struct Windows::Compat::Appraiser::ValidInventoryComponents *a6)
{
  unsigned __int16 *v9; // r14
  struct _SYSTEMTIME *v10; // rax
  struct _SYSTEMTIME *v11; // rsi
  struct Windows::Compat::Appraiser::IInventory **v12; // rax
  unsigned __int64 v13; // rdx
  HRESULT appended; // ebx
  char v15; // dl
  const char *v16; // rax
  HRESULT v17; // eax
  unsigned __int64 v18; // rdx
  WCHAR *v19; // r9
  __int64 v20; // rcx
  WCHAR *v21; // r8
  __int64 v22; // rdx
  WCHAR v23; // r10
  WCHAR *v24; // rcx
  char v25; // cl
  struct Windows::Compat::Appraiser::IInventory ***v26; // r8
  char v27; // al
  int v28; // r9d
  const unsigned __int16 *v29; // rdx
  char v30; // dl
  int v31; // eax
  int v32; // ecx
  int v33; // ebx
  char v34; // cl
  volatile signed __int64 *v35; // rcx
  void **v36; // rdx
  int v37; // r8d
  int v38; // r9d
  int v39; // eax
  volatile signed __int64 *v40; // rcx
  void **v41; // rdx
  int v42; // ebx
  int v43; // r8d
  int v44; // r9d
  Windows::Compat::Appraiser::SetupAppraiser *v45; // rbx
  char v46; // dl
  const unsigned __int16 *v47; // rax
  Windows::Compat::Appraiser::SetupAppraiser *v48; // rbx
  const unsigned __int16 *v49; // rax
  const char *dwFlags; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsa; // [rsp+20h] [rbp-E0h]
  const char *v53; // [rsp+28h] [rbp-D8h]
  char *v54; // [rsp+30h] [rbp-D0h]
  char *v55; // [rsp+30h] [rbp-D0h]
  char v56; // [rsp+60h] [rbp-A0h]
  bool v57; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v58; // [rsp+68h] [rbp-98h] BYREF
  struct Windows::Compat::Appraiser::IInventory ***v59; // [rsp+70h] [rbp-90h]
  int v60; // [rsp+78h] [rbp-88h] BYREF
  char *v61; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME *v62; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEMTIME *v63; // [rsp+90h] [rbp-70h] BYREF
  const char *v64; // [rsp+98h] [rbp-68h] BYREF
  const char *v65; // [rsp+A0h] [rbp-60h] BYREF
  Windows::Compat::Appraiser::SetupAppraiser *v66; // [rsp+A8h] [rbp-58h]
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  char *v68; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE hHeap[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v70; // [rsp+D8h] [rbp-28h]
  LPVOID lpMem[2]; // [rsp+E8h] [rbp-18h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  struct _SYSTEMTIME v73; // [rsp+100h] [rbp+0h] BYREF
  char v74[144]; // [rsp+110h] [rbp+10h] BYREF
  char v75[144]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR pszPathOut[264]; // [rsp+440h] [rbp+340h] BYREF
  WCHAR v78[264]; // [rsp+650h] [rbp+550h] BYREF
  WCHAR v79[264]; // [rsp+860h] [rbp+760h] BYREF

  v72 = -2;
  v59 = a2;
  v66 = this;
  v61 = (char *)a5;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v70 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v9 = (unsigned __int16 *)*((_QWORD *)a4 + 6);
  v58 = v9;
  v10 = (struct _SYSTEMTIME *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  v62 = v10;
  if ( v10 )
  {
    *(_QWORD *)&v10->wYear = &Windows::Compat::Appraiser::BasicPropertyEnumerator::`vftable';
    *(_QWORD *)&v10->wHour = 0;
    *(_QWORD *)&v10[1].wYear = hHeap;
    LOBYTE(v10[1].wHour) = 1;
    v12 = (struct Windows::Compat::Appraiser::IInventory **)operator new[](
                                                              0x50u,
                                                              (const struct std::nothrow_t *)&std::nothrow);
    *a2 = v12;
    if ( !v12 )
    {
      appended = -2147024882;
LABEL_150:
      (*(void (__fastcall **)(struct _SYSTEMTIME *))(*(_QWORD *)&v11->wYear + 32LL))(v11);
      goto LABEL_152;
    }
    appended = Windows::Compat::Appraiser::SetupAppraiser::CombinePathAndAppendRunId(
                 v78,
                 v13,
                 v9,
                 L"%hs_APPRAISER_ApplicationInventory.xml");
    if ( appended < 0 )
    {
      v15 = 105;
LABEL_6:
      v16 = "Failed to copy path: [0x%x].";
LABEL_7:
      LODWORD(v54) = appended;
      LODWORD(v53) = (_DWORD)v16;
LABEL_8:
      LODWORD(dwFlags) = appended;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v15,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
        dwFlags,
        (int)v53,
        v54);
      goto LABEL_150;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA69u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
        "Failed to copy path: [0x%x].",
        appended);
    v17 = PathCchCombineEx(pszPathOut, 0x104u, *((PCWSTR *)a4 + 5), L"acres.dll", (ULONG)dwFlags);
    appended = v17;
    if ( v17 < 0 )
    {
      LODWORD(v54) = v17;
      v53 = "Failed to copy path: [0x%x].";
      v15 = 111;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA6Fu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
        "Failed to copy path: [0x%x].",
        v17);
    appended = PathCchCombineEx(pszPath, 0x104u, *((PCWSTR *)a4 + 5), L"compatAppraiserResources.dll", (ULONG)dwFlags);
    if ( appended < 0 )
    {
      v15 = 117;
      goto LABEL_6;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA75u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
        "Failed to copy path: [0x%x].",
        appended);
    appended = Windows::Compat::Appraiser::SetupAppraiser::CombinePathAndAppendRunId(
                 v79,
                 v18,
                 v58,
                 L"%hs_APPRAISER_DeviceInventory.xml");
    if ( appended < 0 )
    {
      v15 = 123;
      goto LABEL_6;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA7Bu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
        "Failed to copy path: [0x%x].",
        appended);
    if ( !PathFileExistsW(pszPathOut) )
    {
      appended = -2147019873;
      LODWORD(dwFlags) = -2147019873;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        128,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
        dwFlags,
        (int)"Required Inventory file(s) do(es) not exist: %ls.",
        (const char *)pszPathOut);
      goto LABEL_150;
    }
    if ( !PathFileExistsW(pszPath) )
    {
      appended = -2147019873;
      LODWORD(dwFlags) = -2147019873;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        133,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
        dwFlags,
        (int)"Required Inventory file(s) do(es) not exist: %ls.",
        (const char *)pszPath);
      goto LABEL_150;
    }
    if ( !*((_BYTE *)a4 + 4) && (*((_BYTE *)a4 + 1) || *((_BYTE *)a4 + 3)) )
    {
      v56 = *((_BYTE *)a4 + 6);
      v20 = 2147483646;
      v19 = v78;
      v21 = (WCHAR *)((char *)a6 + 88);
      v22 = 260;
      do
      {
        if ( !v20 )
          break;
        v23 = *v19;
        if ( !*v19 )
          break;
        ++v19;
        *v21++ = v23;
        --v20;
        --v22;
      }
      while ( v22 );
      appended = v22 == 0 ? 0x8007007A : 0;
      v24 = v21 - 1;
      if ( v22 )
        v24 = v21;
      *v24 = 0;
      if ( !v22 )
      {
        LODWORD(v54) = -2147024774;
        LODWORD(dwFlags) = -2147024774;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          102,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
          "Windows::Compat::Appraiser::WicaApplicationInventory::Initialize",
          dwFlags,
          (int)"String copy failed: [0x%x].",
          v54);
        LODWORD(v54) = appended;
        v53 = "Failed to initialize: [0x%x].";
        v15 = -107;
        goto LABEL_8;
      }
      v25 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x66u,
          "onecore\\base\\appcompat\\appraiser\\inventory\\applicationinventory.cpp",
          "Windows::Compat::Appraiser::WicaApplicationInventory::Initialize",
          "String copy failed: [0x%x].",
          v22 == 0 ? 0x8007007A : 0);
        v25 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
      }
      *((_WORD *)a6 + 304) = 1;
      *((_BYTE *)a6 + 610) = 1;
      *((_QWORD *)a6 + 88) = 0;
      *((_BYTE *)a6 + 614) = v56;
      if ( (v25 & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xA95u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
          "Failed to initialize: [0x%x].",
          0);
      v26 = v59;
      (*v59)[(*a3)++] = a6;
    }
    else
    {
      v26 = v59;
    }
    if ( *((_BYTE *)a4 + 4) )
      goto LABEL_129;
    v27 = *((_BYTE *)a4 + 2);
    if ( !v27 && !*(_BYTE *)a4 && !*((_BYTE *)a4 + 1) && !*((_BYTE *)a4 + 3) )
    {
LABEL_63:
      if ( !*((_BYTE *)a4 + 4) )
      {
        if ( *((_BYTE *)a4 + 2) || *((_BYTE *)a4 + 3) )
        {
          v29 = (const unsigned __int16 *)*((_QWORD *)a4 + 9);
          if ( v29 )
          {
            appended = Windows::Compat::Appraiser::DriverInventory::Initialize(
                         (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 1944),
                         v29);
            if ( appended < 0 )
            {
              v16 = "Failed to initialize: [0x%x].";
              v15 = -67;
              goto LABEL_7;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0xABDu,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
                "Failed to initialize: [0x%x].",
                appended);
            v26 = v59;
            (*v59)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 1944);
          }
        }
        if ( !*((_BYTE *)a4 + 4) )
        {
          if ( *(_BYTE *)a4 || *((_BYTE *)a4 + 3) )
          {
            appended = Windows::Compat::Appraiser::SystemInventory::Initialize(
                         (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 2544),
                         *((const unsigned __int16 **)a4 + 8));
            if ( appended < 0 )
            {
              v16 = "Failed to initialize: [0x%x].";
              v15 = -59;
              goto LABEL_7;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0xAC5u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
                "Failed to initialize: [0x%x].",
                appended);
            v26 = v59;
            (*v59)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 2544);
          }
          if ( !*((_BYTE *)a4 + 4) )
          {
            if ( *((_BYTE *)a4 + 1) || *((_BYTE *)a4 + 3) )
              (*v26)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 2480);
            if ( !*((_BYTE *)a4 + 4) )
            {
              v30 = *((_BYTE *)a4 + 1);
              if ( !v30 && !*((_BYTE *)a4 + 2) && !*((_BYTE *)a4 + 3) )
                goto LABEL_113;
              v31 = (*((_BYTE *)a4 + 3) != 0 ? 0xA0 : 0) | 0x41;
              if ( !v30 )
                v31 = *((_BYTE *)a4 + 3) != 0 ? 0xE1 : 0;
              v32 = v31 | 0x20;
              if ( !*((_BYTE *)a4 + 2) )
                v32 = v31;
              LODWORD(v58) = v32;
              v57 = wcscmp_0(L"Server", *((const wchar_t **)a4 + 8)) == 0;
              v33 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc((const unsigned __int16 **)a6 + 314, pszPath);
              if ( v33 >= 0 )
              {
                if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                  Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                    0x88u,
                    "onecore\\base\\appcompat\\appraiser\\inventory\\inboxcomponentinventory.cpp",
                    "Windows::Compat::Appraiser::InboxComponentInventory::Initialize",
                    "Failed to copy resource path string: [0x%x].",
                    v33);
                v33 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc(
                        (const unsigned __int16 **)a6 + 315,
                        pszPathOut);
                if ( v33 >= 0 )
                {
                  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                      0x8Eu,
                      "onecore\\base\\appcompat\\appraiser\\inventory\\inboxcomponentinventory.cpp",
                      "Windows::Compat::Appraiser::InboxComponentInventory::Initialize",
                      "Failed to copy resource path string: [0x%x].",
                      v33);
                  *((_DWORD *)a6 + 632) = (_DWORD)v58;
                  *((_BYTE *)a6 + 2532) = v57;
                  if ( v61 )
                    *((_QWORD *)a6 + 317) = Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                              v61 + 432,
                                              L"MT_GatedDefaultMessageOverrides");
                  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                      0xAEDu,
                      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                      "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
                      "Failed to initialize: [0x%x].",
                      0);
                  (*v59)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 2496);
LABEL_113:
                  if ( !*((_BYTE *)a4 + 4) )
                  {
                    if ( *((_BYTE *)a4 + 3) || *(_BYTE *)a4 )
                    {
                      v39 = (**((__int64 (__fastcall ***)(char *, struct _SYSTEMTIME *, _QWORD, WCHAR *))a6 + 488))(
                              (char *)a6 + 3904,
                              v11,
                              0,
                              v19);
                      LODWORD(v58) = v39;
                      if ( v39 >= 0 )
                      {
                        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                            0xAF7u,
                            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                            "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
                            "Failed to initialize: [0x%x].",
                            v39);
                        (*v59)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 3896);
                      }
                      else
                      {
                        LODWORD(v54) = v39;
                        LODWORD(dwFlags) = v39;
                        Windows::Compat::Appraiser::WriteLog(
                          (Windows::Compat::Appraiser *)1,
                          247,
                          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                          "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
                          dwFlags,
                          (int)"Failed to initialize: [0x%x].",
                          v54);
                        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v74);
                        v40 = (volatile signed __int64 *)v74;
                        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                          v40 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
                        TraceLoggingCorrelationVector::ToStringImpl(
                          (TraceLoggingCorrelationVector *)v40,
                          _InterlockedExchangeAdd64(v40 + 17, 0),
                          v75);
                        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                          UtcThrottle::Throttle(
                            (UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler,
                            v41);
                        v42 = qword_1802C9628;
                        if ( *(_DWORD *)qword_1802C9628 > 5u
                          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
                          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
                        {
                          v61 = v75;
                          v62 = (struct _SYSTEMTIME *)"Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents";
                          v65 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
                          v60 = 2807;
                          v64 = (const char *)&szValueBuf;
                          SystemTime = 0;
                          GetSystemTime(&SystemTime);
                          v73 = SystemTime;
                          v63 = &v73;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                            v42,
                            (unsigned int)&unk_18029E038,
                            v43,
                            v44,
                            (__int64)&v63,
                            (__int64)&v64,
                            (__int64)&v60,
                            (__int64)&v65,
                            (__int64)&v62,
                            (__int64)&v58,
                            (__int64)&v61);
                        }
                      }
                    }
                    if ( !*((_BYTE *)a4 + 4) )
                      goto LABEL_149;
                  }
                  goto LABEL_129;
                }
                v34 = -114;
              }
              else
              {
                v34 = -120;
              }
              LODWORD(v54) = v33;
              LODWORD(dwFlags) = v33;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                v34,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\inboxcomponentinventory.cpp",
                "Windows::Compat::Appraiser::InboxComponentInventory::Initialize",
                dwFlags,
                (int)"Failed to copy resource path string: [0x%x].",
                v54);
              LODWORD(v55) = v33;
              LODWORD(dwFlagsa) = v33;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                237,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
                dwFlagsa,
                (int)"Failed to initialize: [0x%x].",
                v55);
              TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v74);
              v35 = (volatile signed __int64 *)v74;
              if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                v35 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
              TraceLoggingCorrelationVector::ToStringImpl(
                (TraceLoggingCorrelationVector *)v35,
                _InterlockedExchangeAdd64(v35 + 17, 0),
                v75);
              if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v36);
              v61 = (char *)qword_1802C9628;
              if ( *(_DWORD *)qword_1802C9628 > 5u
                && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
                && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
              {
                v68 = v75;
                v60 = v33;
                v63 = (struct _SYSTEMTIME *)"Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents";
                v64 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
                LODWORD(v58) = 2797;
                v65 = (const char *)&szValueBuf;
                SystemTime = 0;
                GetSystemTime(&SystemTime);
                v73 = SystemTime;
                v62 = &v73;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  (_DWORD)v61,
                  (unsigned int)&unk_18029DFD5,
                  v37,
                  v38,
                  (__int64)&v62,
                  (__int64)&v65,
                  (__int64)&v58,
                  (__int64)&v64,
                  (__int64)&v63,
                  (__int64)&v60,
                  (__int64)&v68);
              }
              goto LABEL_113;
            }
          }
        }
      }
LABEL_129:
      if ( *((_BYTE *)a4 + 1) && !*((_BYTE *)a4 + 3) )
      {
        v45 = v66;
        if ( !Windows::Compat::Appraiser::PersistedData::Get((char *)v66 + 152, 5) )
        {
          v46 = 3;
LABEL_133:
          LODWORD(dwFlags) = -2147019873;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            v46,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
            dwFlags,
            (int)"Rescan is missing stored data.",
            v54);
          appended = -2147019873;
          goto LABEL_150;
        }
        v47 = (const unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)v45 + 152, 5);
        appended = Windows::Compat::Appraiser::SetupDeserializer::Initialize(
                     (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 3768),
                     v47);
        if ( appended < 0 )
        {
          v16 = "Failed to initialize: [0x%x].";
          v15 = 7;
          goto LABEL_7;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xB07u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
            "Failed to initialize: [0x%x].",
            appended);
        (*v59)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 3768);
      }
      if ( *((_BYTE *)a4 + 4) && *((_BYTE *)a4 + 2) && !*((_BYTE *)a4 + 3) )
      {
        v48 = v66;
        if ( !Windows::Compat::Appraiser::PersistedData::Get((char *)v66 + 152, 7) )
        {
          v46 = 16;
          goto LABEL_133;
        }
        v49 = (const unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)v48 + 152, 7);
        appended = Windows::Compat::Appraiser::SetupDeserializer::Initialize(
                     (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 3832),
                     v49);
        if ( appended < 0 )
        {
          v16 = "Failed to initialize: [0x%x].";
          v15 = 20;
          goto LABEL_7;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xB14u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
            "Failed to initialize: [0x%x].",
            appended);
        (*v59)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 3832);
      }
LABEL_149:
      appended = 0;
      goto LABEL_150;
    }
    if ( *((_BYTE *)a4 + 3) )
    {
      v28 = 0;
LABEL_58:
      appended = Windows::Compat::Appraiser::WicaDeviceInventory::Initialize(
                   (int)a6 + 712,
                   (_DWORD)v58,
                   (unsigned int)v79,
                   v28,
                   1,
                   0,
                   0,
                   0,
                   *((_BYTE *)a4 + 6));
      if ( appended < 0 )
      {
        v16 = "Failed to initialize: [0x%x].";
        v15 = -75;
        goto LABEL_7;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xAB5u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeInventoryComponents",
          "Failed to initialize: [0x%x].",
          appended);
      v26 = v59;
      (*v59)[(*a3)++] = (struct Windows::Compat::Appraiser::ValidInventoryComponents *)((char *)a6 + 712);
      goto LABEL_63;
    }
    if ( v27 )
    {
      if ( *(_BYTE *)a4 )
      {
        v28 = 3;
        goto LABEL_58;
      }
    }
    else if ( !*((_BYTE *)a4 + 1) )
    {
      v28 = 2;
      goto LABEL_58;
    }
    v28 = 1;
    goto LABEL_58;
  }
  appended = -2147024882;
LABEL_152:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18003c948  push    rbp
0x18003c94a  push    rbx
0x18003c94b  push    rsi
0x18003c94c  push    rdi
0x18003c94d  push    r12
0x18003c94f  push    r13
0x18003c951  push    r14
0x18003c953  push    r15
0x18003c955  lea     rbp, [rsp-988h]
0x18003c95d  sub     rsp, 0A88h
0x18003c964  mov     [rbp+9C0h+var_9C8], 0FFFFFFFFFFFFFFFEh
0x18003c96c  mov     rax, cs:__security_cookie
0x18003c973  xor     rax, rsp
0x18003c976  mov     [rbp+9C0h+var_50], rax
0x18003c97d  mov     rdi, r9
0x18003c980  mov     r12, r8
0x18003c983  mov     rbx, rdx
0x18003c986  mov     [rsp+0AC0h+var_A50], rdx
0x18003c98b  mov     [rbp+9C0h+var_A18], rcx
0x18003c98f  mov     rax, [rbp+9C0h+arg_20]
0x18003c996  mov     [rbp+9C0h+var_A40], rax
0x18003c99a  mov     r13, [rbp+9C0h+arg_28]
0x18003c9a1  xorps   xmm0, xmm0
0x18003c9a4  movups  xmmword ptr [rbp+9C0h+hHeap], xmm0
0x18003c9a8  movups  [rbp+9C0h+var_9E8], xmm0
0x18003c9ac  movups  xmmword ptr [rbp+9C0h+lpMem], xmm0
0x18003c9b0  call    cs:__imp_GetProcessHeap
0x18003c9b6  mov     [rbp+9C0h+hHeap], rax
0x18003c9ba  mov     [rbp+9C0h+lpMem], 10h
0x18003c9c2  xorps   xmm0, xmm0
0x18003c9c5  movdqu  [rbp+9C0h+var_9E8], xmm0
0x18003c9ca  xor     r15d, r15d
0x18003c9cd  mov     [rbp+9C0h+lpMem+8], r15
0x18003c9d1  mov     [rbp+9C0h+hHeap+8], 8
0x18003c9d9  mov     r14, [rdi+30h]
0x18003c9dd  mov     [rsp+0AC0h+var_A58], r14
0x18003c9e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c9e9  lea     ecx, [r15+20h]; unsigned __int64
0x18003c9ed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c9f2  mov     rsi, rax
0x18003c9f5  mov     [rbp+9C0h+var_A38], rax
0x18003c9f9  test    rax, rax
0x18003c9fc  jz      loc_18003D6B0
0x18003ca02  lea     rax, ??_7BasicPropertyEnumerator@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::BasicPropertyEnumerator::`vftable'
0x18003ca09  mov     [rsi], rax
0x18003ca0c  mov     [rsi+8], r15
0x18003ca10  lea     rax, [rbp+9C0h+hHeap]
0x18003ca14  mov     [rsi+10h], rax
0x18003ca18  mov     byte ptr [rsi+18h], 1
0x18003ca1c  test    rsi, rsi
0x18003ca1f  jz      loc_18003D6B0
0x18003ca25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ca2c  lea     ecx, [r15+50h]; unsigned __int64
0x18003ca30  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003ca35  mov     [rbx], rax
0x18003ca38  test    rax, rax
0x18003ca3b  jnz     short loc_18003CA47
0x18003ca3d  mov     ebx, 8007000Eh
0x18003ca42  jmp     loc_18003D69F
0x18003ca47  lea     r9, aHsAppraiserApp; "%hs_APPRAISER_ApplicationInventory.xml"
0x18003ca4e  mov     r8, r14; unsigned __int16 *
0x18003ca51  lea     rcx, [rbp+9C0h+var_470]; pszPathOut
0x18003ca58  call    ?CombinePathAndAppendRunId@SetupAppraiser@Appraiser@Compat@Windows@@CAJPEAG_KPEBG2@Z; Windows::Compat::Appraiser::SetupAppraiser::CombinePathAndAppendRunId(ushort *,unsigned __int64,ushort const *,ushort const *)
0x18003ca5d  mov     ebx, eax
0x18003ca5f  test    eax, eax
0x18003ca61  jns     short loc_18003CA99
0x18003ca63  lea     r9, aWindowsCompatA_542; "Windows::Compat::Appraiser::SetupApprai"...
0x18003ca6a  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003ca71  mov     edx, 0A69h; bool
0x18003ca76  lea     rax, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003ca7d  mov     dword ptr [rsp+0AC0h+var_A90], ebx; char *
0x18003ca81  mov     qword ptr [rsp+0AC0h+var_A98], rax; int
0x18003ca86  mov     [rsp+0AC0h+dwFlags], ebx; char *
0x18003ca8a  mov     ecx, 1; this
0x18003ca8f  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18003ca94  jmp     loc_18003D69F
0x18003ca99  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003ca9f  lea     r14, aWindowsCompatA_542; "Windows::Compat::Appraiser::SetupApprai"...
0x18003caa6  lea     r15, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003caad  test    al, 1
0x18003caaf  jz      short loc_18003CACC
0x18003cab1  mov     [rsp+0AC0h+dwFlags], ebx; dwFlags
0x18003cab5  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003cabc  mov     r8, r14; char *
0x18003cabf  mov     rdx, r15; char *
0x18003cac2  mov     ecx, 0A69h; unsigned int
0x18003cac7  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003cacc  lea     r9, aAcresDll_0; "acres.dll"
0x18003cad3  mov     r8, [rdi+28h]; pszPathIn
0x18003cad7  mov     edx, 104h; cchPathOut
0x18003cadc  lea     rcx, [rbp+9C0h+pszPathOut]; pszPathOut
0x18003cae3  call    PathCchCombineEx
0x18003cae8  mov     ebx, eax
0x18003caea  test    eax, eax
0x18003caec  jns     short loc_18003CB0E
0x18003caee  mov     dword ptr [rsp+0AC0h+var_A90], eax
0x18003caf2  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003caf9  mov     qword ptr [rsp+0AC0h+var_A98], r9
0x18003cafe  mov     r9, r14
0x18003cb01  mov     r8, r15
0x18003cb04  mov     edx, 0A6Fh
0x18003cb09  jmp     loc_18003CA86
0x18003cb0e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003cb14  test    al, 1
0x18003cb16  jz      short loc_18003CB33
0x18003cb18  mov     [rsp+0AC0h+dwFlags], ebx; dwFlags
0x18003cb1c  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003cb23  mov     r8, r14; char *
0x18003cb26  mov     rdx, r15; char *
0x18003cb29  mov     ecx, 0A6Fh; unsigned int
0x18003cb2e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003cb33  lea     r9, aCompatappraise_1; "compatAppraiserResources.dll"
0x18003cb3a  mov     r8, [rdi+28h]; pszPathIn
0x18003cb3e  mov     edx, 104h; cchPathOut
0x18003cb43  lea     rcx, [rbp+9C0h+pszPath]; pszPathOut
0x18003cb4a  call    PathCchCombineEx
0x18003cb4f  mov     ebx, eax
0x18003cb51  test    eax, eax
0x18003cb53  jns     short loc_18003CB65
0x18003cb55  mov     r9, r14
0x18003cb58  mov     r8, r15
0x18003cb5b  mov     edx, 0A75h
0x18003cb60  jmp     loc_18003CA76
0x18003cb65  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003cb6b  test    al, 1
0x18003cb6d  jz      short loc_18003CB8A
0x18003cb6f  mov     [rsp+0AC0h+dwFlags], ebx
0x18003cb73  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003cb7a  mov     r8, r14; char *
0x18003cb7d  mov     rdx, r15; char *
0x18003cb80  mov     ecx, 0A75h; unsigned int
0x18003cb85  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003cb8a  lea     r9, aHsAppraiserDev; "%hs_APPRAISER_DeviceInventory.xml"
0x18003cb91  mov     r8, [rsp+0AC0h+var_A58]; unsigned __int16 *
0x18003cb96  lea     rcx, [rbp+9C0h+var_260]; pszPathOut
0x18003cb9d  call    ?CombinePathAndAppendRunId@SetupAppraiser@Appraiser@Compat@Windows@@CAJPEAG_KPEBG2@Z; Windows::Compat::Appraiser::SetupAppraiser::CombinePathAndAppendRunId(ushort *,unsigned __int64,ushort const *,ushort const *)
0x18003cba2  mov     ebx, eax
0x18003cba4  test    eax, eax
0x18003cba6  jns     short loc_18003CBB8
0x18003cba8  mov     r9, r14
0x18003cbab  mov     r8, r15
0x18003cbae  mov     edx, 0A7Bh
0x18003cbb3  jmp     loc_18003CA76
0x18003cbb8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003cbbe  test    al, 1
0x18003cbc0  jz      short loc_18003CBDD
0x18003cbc2  mov     [rsp+0AC0h+dwFlags], ebx
0x18003cbc6  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003cbcd  mov     r8, r14; char *
0x18003cbd0  mov     rdx, r15; char *
0x18003cbd3  mov     ecx, 0A7Bh; unsigned int
0x18003cbd8  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003cbdd  lea     rcx, [rbp+9C0h+pszPathOut]; pszPath
0x18003cbe4  call    cs:__imp_PathFileExistsW
0x18003cbea  test    eax, eax
0x18003cbec  jnz     short loc_18003CC21
0x18003cbee  mov     edi, 8007139Fh
0x18003cbf3  mov     ebx, edi
0x18003cbf5  lea     rax, [rbp+9C0h+pszPathOut]
0x18003cbfc  mov     [rsp+0AC0h+var_A90], rax
0x18003cc01  lea     rax, aRequiredInvent; "Required Inventory file(s) do(es) not e"...
0x18003cc08  mov     qword ptr [rsp+0AC0h+var_A98], rax
0x18003cc0d  mov     [rsp+0AC0h+dwFlags], edi
0x18003cc11  mov     r9, r14
0x18003cc14  mov     r8, r15
0x18003cc17  mov     edx, 0A80h
0x18003cc1c  jmp     loc_18003CA8A
0x18003cc21  lea     rcx, [rbp+9C0h+pszPath]; pszPath
0x18003cc28  call    cs:__imp_PathFileExistsW
0x18003cc2e  xor     r11d, r11d
0x18003cc31  test    eax, eax
0x18003cc33  jnz     short loc_18003CC68
0x18003cc35  mov     edi, 8007139Fh
0x18003cc3a  mov     ebx, edi
0x18003cc3c  lea     rax, [rbp+9C0h+pszPath]
0x18003cc43  mov     [rsp+0AC0h+var_A90], rax
0x18003cc48  lea     rax, aRequiredInvent; "Required Inventory file(s) do(es) not e"...
0x18003cc4f  mov     qword ptr [rsp+0AC0h+var_A98], rax
0x18003cc54  mov     [rsp+0AC0h+dwFlags], edi
0x18003cc58  mov     r9, r14
0x18003cc5b  mov     r8, r15
0x18003cc5e  mov     edx, 0A85h
0x18003cc63  jmp     loc_18003CA8A
0x18003cc68  mov     eax, 2
0x18003cc6d  cmp     [rdi+4], r11b
0x18003cc71  jnz     loc_18003CDCA
0x18003cc77  cmp     [rdi+1], r11b
0x18003cc7b  jnz     short loc_18003CC87
0x18003cc7d  cmp     [rdi+3], r11b
0x18003cc81  jz      loc_18003CDCA
0x18003cc87  mov     cl, [rdi+6]
0x18003cc8a  mov     [rsp+0AC0h+var_A60], cl
0x18003cc8e  mov     ecx, 7FFFFFFEh
0x18003cc93  lea     r9, [rbp+9C0h+var_470]
0x18003cc9a  lea     r8, [r13+58h]
0x18003cc9e  mov     edx, 104h
0x18003cca3  test    rcx, rcx
0x18003cca6  jz      short loc_18003CCC5
0x18003cca8  movzx   r10d, word ptr [r9]
0x18003ccac  test    r10w, r10w
0x18003ccb0  jz      short loc_18003CCC5
0x18003ccb2  add     r9, rax
0x18003ccb5  mov     [r8], r10w
0x18003ccb9  add     r8, rax
0x18003ccbc  dec     rcx
0x18003ccbf  sub     rdx, 1
0x18003ccc3  jnz     short loc_18003CCA3
0x18003ccc5  mov     rax, rdx
0x18003ccc8  neg     rax
0x18003cccb  sbb     ebx, ebx
0x18003cccd  not     ebx
0x18003cccf  and     ebx, 8007007Ah
0x18003ccd5  lea     rcx, [r8-2]
0x18003ccd9  test    rdx, rdx
0x18003ccdc  cmovnz  rcx, r8
0x18003cce0  mov     [rcx], r11w
0x18003cce4  jnz     short loc_18003CD35
0x18003cce6  mov     dword ptr [rsp+0AC0h+var_A90], ebx; char *
0x18003ccea  lea     r9, aStringCopyFail_0; "String copy failed: [0x%x]."
0x18003ccf1  mov     qword ptr [rsp+0AC0h+var_A98], r9; int
0x18003ccf6  mov     [rsp+0AC0h+dwFlags], ebx; char *
0x18003ccfa  lea     r9, aWindowsCompatA_107; "Windows::Compat::Appraiser::WicaApplica"...
0x18003cd01  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x18003cd08  mov     edx, 66h ; 'f'; bool
0x18003cd0d  lea     ecx, [rdx-65h]; this
0x18003cd10  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18003cd15  mov     dword ptr [rsp+0AC0h+var_A90], ebx
0x18003cd19  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003cd20  mov     qword ptr [rsp+0AC0h+var_A98], r9
0x18003cd25  mov     r9, r14
0x18003cd28  mov     r8, r15
0x18003cd2b  mov     edx, 0A95h
0x18003cd30  jmp     loc_18003CA86
0x18003cd35  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003cd3b  test    cl, 1
0x18003cd3e  jz      short loc_18003CD6C
0x18003cd40  mov     [rsp+0AC0h+dwFlags], ebx
0x18003cd44  lea     r9, aStringCopyFail_0; "String copy failed: [0x%x]."
0x18003cd4b  lea     r8, aWindowsCompatA_107; "Windows::Compat::Appraiser::WicaApplica"...
0x18003cd52  lea     rdx, aOnecoreBaseApp_33; "onecore\\base\\appcompat\\appraiser\\in"...
0x18003cd59  mov     ecx, 66h ; 'f'; unsigned int
0x18003cd5e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003cd63  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003cd69  xor     r11d, r11d
0x18003cd6c  mov     word ptr [r13+260h], 1
0x18003cd76  mov     byte ptr [r13+262h], 1
0x18003cd7e  mov     [r13+2C0h], r11
0x18003cd85  mov     al, [rsp+0AC0h+var_A60]
0x18003cd89  mov     [r13+266h], al
0x18003cd90  test    cl, 1
0x18003cd93  jz      short loc_18003CDB4
0x18003cd95  mov     [rsp+0AC0h+dwFlags], r11d
0x18003cd9a  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003cda1  mov     r8, r14; char *
0x18003cda4  mov     rdx, r15; char *
0x18003cda7  mov     ecx, 0A95h; unsigned int
0x18003cdac  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003cdb1  xor     r11d, r11d
0x18003cdb4  mov     ecx, [r12]
0x18003cdb8  mov     r8, [rsp+0AC0h+var_A50]
0x18003cdbd  mov     rax, [r8]
0x18003cdc0  mov     [rax+rcx*8], r13
0x18003cdc4  inc     dword ptr [r12]
0x18003cdc8  jmp     short loc_18003CDCF
0x18003cdca  mov     r8, [rsp+0AC0h+var_A50]
0x18003cdcf  cmp     [rdi+4], r11b
0x18003cdd3  jnz     loc_18003D4FA
0x18003cdd9  mov     al, [rdi+2]
0x18003cddc  test    al, al
0x18003cdde  jnz     short loc_18003CDF5
0x18003cde0  cmp     [rdi], r11b
0x18003cde3  jnz     short loc_18003CDF5
0x18003cde5  cmp     [rdi+1], r11b
0x18003cde9  jnz     short loc_18003CDF5
0x18003cdeb  cmp     [rdi+3], r11b
0x18003cdef  jz      loc_18003CEBB
0x18003cdf5  cmp     [rdi+3], r11b
0x18003cdf9  jz      short loc_18003CE00
0x18003cdfb  mov     r9d, r11d
0x18003cdfe  jmp     short loc_18003CE25
0x18003ce00  test    al, al
0x18003ce02  jz      short loc_18003CE11
0x18003ce04  cmp     [rdi], r11b
0x18003ce07  jz      short loc_18003CE1F
0x18003ce09  mov     r9d, 3
0x18003ce0f  jmp     short loc_18003CE25
0x18003ce11  cmp     [rdi+1], r11b
0x18003ce15  jnz     short loc_18003CE1F
0x18003ce17  mov     r9d, 2
0x18003ce1d  jmp     short loc_18003CE25
0x18003ce1f  mov     r9d, 1
0x18003ce25  lea     rcx, [r13+2C8h]
0x18003ce2c  mov     al, [rdi+6]
0x18003ce2f  mov     byte ptr [rsp+0AC0h+var_A80], al
0x18003ce33  mov     [rsp+0AC0h+var_A88], r11
0x18003ce38  mov     [rsp+0AC0h+var_A90], r11; char *
0x18003ce3d  mov     byte ptr [rsp+0AC0h+var_A98], r11b
0x18003ce42  mov     byte ptr [rsp+0AC0h+dwFlags], 1
0x18003ce47  lea     r8, [rbp+9C0h+var_260]
0x18003ce4e  mov     rdx, [rsp+0AC0h+var_A58]
  ... truncated ...
```
