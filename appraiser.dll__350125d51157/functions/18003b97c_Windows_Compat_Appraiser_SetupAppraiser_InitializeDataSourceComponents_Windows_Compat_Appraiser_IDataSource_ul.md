# Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents(Windows::Compat::Appraiser::IDataSource * * &,ulong &,Windows::Compat::Appraiser::RunOptions &,Windows::Compat::Appraiser::DataFile &,Windows::Compat::Appraiser::ValidDataSourceComponents &,Windows::Compat::Appraiser::GatingStateInfo &)

- ea: `0x18003b97c`
- end: `0x18003c53a`
- name: `?InitializeDataSourceComponents@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEAPEAPEAVIDataSource@234@AEAKAEAURunOptions@234@AEAVDataFile@234@AEAUValidDataSourceComponents@234@AEAUGatingStateInfo@234@@Z`
- size: `3006`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct IDataSource ***, unsigned int *, struct Windows::Compat::Appraiser::RunOptions *, struct Windows::Compat::Appraiser::DataFile *, struct Windows::Compat::Appraiser::ValidDataSourceComponents *, struct Windows::Compat::Appraiser::GatingStateInfo *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b30c`

## callees

- `0x18000147c`
- `0x180008570`
- `0x18000a5b8`
- `0x180011d94`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18003b97c`
- `0x180082f0c`
- `0x1800b02d8`
- `0x1801ac054`
- `0x1801e1c70`
- `0x1801e4e90`
- `0x1801e5b50`
- `0x1801e9e90`
- `0x1801ec230`
- `0x1801ef610`
- `0x1801f0d50`
- `0x1801f4fa0`
- `0x1802174cc`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18003c452`
- `KERNEL32!GetSystemTime` at `0x18003c452`
- `KERNEL32!GetProcessHeap` at `0x18003b9e0`
- `KERNEL32!GetProcessHeap` at `0x18003b9e0`
- `KERNEL32!HeapFree` at `0x18003c50f`
- `KERNEL32!HeapFree` at `0x18003c50f`
- `SHLWAPI!PathFileExistsW` at `0x18003bb9a`
- `SHLWAPI!PathFileExistsW` at `0x18003bbd8`
- `SHLWAPI!PathFileExistsW` at `0x18003bb9a`
- `SHLWAPI!PathFileExistsW` at `0x18003bbd8`

## string_xrefs

- `0x18003ba6f`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003ba9e`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003bae6`: `Failed to copy path: [0x%x].`
- `0x18003bb1c`: `Failed to copy path: [0x%x].`
- `0x18003bb59`: `Failed to copy path: [0x%x].`
- `0x18003bb7c`: `Failed to copy path: [0x%x].`
- `0x18003bb33`: `compatAppraiserResources.dll`
- `0x18003bac4`: `acres.dll`
- `0x18003ba68`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents`
- `0x18003ba97`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents`
- `0x18003c1e3`: `Failed to copy resource path string: [0x%x].`
- `0x18003c21f`: `Failed to copy resource path string: [0x%x].`
- `0x18003c00a`: `Windows::Compat::Appraiser::InboxRequirementsDataSource::Initialize`
- `0x18003c04e`: `Windows::Compat::Appraiser::InboxRequirementsDataSource::Initialize`
- `0x18003bffa`: `Failed to copy resource xml path string: [0x%x].`
- `0x18003c047`: `Failed to copy resource xml path string: [0x%x].`
- `0x18003c011`: `onecore\base\appcompat\appraiser\datasource\inboxcomponentrequirements.cpp`
- `0x18003c055`: `onecore\base\appcompat\appraiser\datasource\inboxcomponentrequirements.cpp`
- `0x18003c1fa`: `onecore\base\appcompat\appraiser\datasource\antimalware.cpp`
- `0x18003c22d`: `onecore\base\appcompat\appraiser\datasource\antimalware.cpp`
- `0x18003c1f3`: `Windows::Compat::Appraiser::AntiMalwareDataSource::Initialize`
- `0x18003c226`: `Windows::Compat::Appraiser::AntiMalwareDataSource::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct IDataSource ***a2,
        unsigned int *a3,
        struct Windows::Compat::Appraiser::RunOptions *a4,
        struct Windows::Compat::Appraiser::DataFile *a5,
        struct Windows::Compat::Appraiser::ValidDataSourceComponents *a6,
        struct Windows::Compat::Appraiser::GatingStateInfo *a7)
{
  struct IDataSource **v10; // rax
  HRESULT v11; // ebx
  int v12; // eax
  char v13; // dl
  const char *v14; // rax
  HRESULT v15; // eax
  int v16; // eax
  struct IDataSource ***v17; // rbx
  int v18; // eax
  char v19; // cl
  unsigned __int64 v20; // rdx
  bool v21; // zf
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // edi
  volatile signed __int64 *v27; // rcx
  void **v28; // rdx
  __int64 v29; // rbx
  __int64 v30; // r8
  __int64 v31; // r9
  const char *dwFlags; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsa; // [rsp+20h] [rbp-E0h]
  const char *v35; // [rsp+28h] [rbp-D8h]
  char *v36; // [rsp+30h] [rbp-D0h]
  char *v37; // [rsp+30h] [rbp-D0h]
  bool v38; // [rsp+70h] [rbp-90h]
  bool v39; // [rsp+70h] [rbp-90h]
  struct IDataSource ***v40; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  const char *v42; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Compat::Appraiser::DataFile *v43; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hHeap[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v45; // [rsp+A8h] [rbp-58h]
  LPVOID lpMem[2]; // [rsp+B8h] [rbp-48h]
  const char *v47; // [rsp+C8h] [rbp-38h] BYREF
  const size_t *v48; // [rsp+D0h] [rbp-30h] BYREF
  struct _SYSTEMTIME *v49; // [rsp+D8h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-10h]
  _OWORD v52[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+118h] [rbp+18h]
  struct _SYSTEMTIME v54; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v55[144]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR pszPathOut[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v57[2]; // [rsp+3D0h] [rbp+2D0h] BYREF
  char v58[144]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR pszPath[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v51 = -2;
  v40 = a2;
  v42 = (const char *)this;
  v43 = a5;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v45 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  memset(v52, 0, sizeof(v52));
  v53 = 0;
  v10 = (struct IDataSource **)operator new[](0x60u, (const struct std::nothrow_t *)&std::nothrow);
  *a2 = v10;
  if ( !v10 )
  {
    v11 = -2147024882;
    goto LABEL_133;
  }
  v41 = *((_QWORD *)a4 + 4);
  v12 = RtlArray<JsonValue *>::Append(hHeap, &v41);
  v11 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v36) = v12;
    v35 = "RtlArray Append failed: [0x%x].";
    LODWORD(dwFlags) = v12;
    v13 = 50;
LABEL_5:
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v13,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
      dwFlags,
      (int)v35,
      v36);
    goto LABEL_133;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xB32u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
      "RtlArray Append failed: [0x%x].",
      v12);
  v11 = PathCchCombineEx(pszPathOut, 0x104u, *((PCWSTR *)a4 + 5), L"acres.dll", (ULONG)dwFlags);
  if ( v11 < 0 )
  {
    v14 = "Failed to copy path: [0x%x].";
    v13 = 56;
LABEL_10:
    LODWORD(v36) = v11;
    LODWORD(v35) = (_DWORD)v14;
LABEL_11:
    LODWORD(dwFlags) = v11;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xB38u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
      "Failed to copy path: [0x%x].",
      v11);
  v15 = PathCchCombineEx(pszPath, 0x104u, *((PCWSTR *)a4 + 5), L"compatAppraiserResources.dll", (ULONG)dwFlags);
  v11 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v36) = v15;
    v35 = "Failed to copy path: [0x%x].";
    v13 = 62;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xB3Eu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
      "Failed to copy path: [0x%x].",
      v15);
  if ( !PathFileExistsW(pszPathOut) )
  {
    v11 = -2147019873;
    v36 = (char *)pszPathOut;
    v35 = "Required Data Source file(s) do(es) not exist: %ls.";
    LODWORD(dwFlags) = -2147019873;
    v13 = 67;
    goto LABEL_5;
  }
  if ( !PathFileExistsW(pszPath) )
  {
    v11 = -2147019873;
    v36 = (char *)pszPath;
    v35 = "Required Data Source file(s) do(es) not exist: %ls.";
    LODWORD(dwFlags) = -2147019873;
    v13 = 72;
    goto LABEL_5;
  }
  if ( !*((_BYTE *)a4 + 4) && (*(_BYTE *)a4 || *((_BYTE *)a4 + 3)) )
  {
    v16 = Windows::Compat::Appraiser::BiosSdbDataSource::Initialize(
            (char *)a6 + 88,
            *((_QWORD *)a4 + 13),
            pszPathOut,
            hHeap);
    v11 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v36) = v16;
      v35 = "Failed to initialize: [0x%x].";
      v13 = 82;
      goto LABEL_11;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB52u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
        "Failed to initialize: [0x%x].",
        v16);
    v17 = v40;
    (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 88);
  }
  else
  {
    v17 = v40;
  }
  if ( !*((_BYTE *)a4 + 4) )
  {
    if ( *((_BYTE *)a4 + 2) || *((_BYTE *)a4 + 3) )
    {
      v11 = Windows::Compat::Appraiser::DeviceSdbDataSource::Initialize(
              (char *)a6 + 832,
              *((_QWORD *)a4 + 13),
              pszPathOut,
              *((_QWORD *)a4 + 12),
              hHeap);
      if ( v11 < 0 )
      {
        v14 = "Failed to initialize: [0x%x].";
        v13 = 93;
        goto LABEL_10;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xB5Du,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
          "Failed to initialize: [0x%x].",
          v11);
      v17 = v40;
      (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 832);
    }
    if ( !*((_BYTE *)a4 + 4) )
    {
      if ( *((_BYTE *)a4 + 2) || *((_BYTE *)a4 + 3) )
      {
        v11 = Windows::Compat::Appraiser::DriverSdbDataSource::Initialize(
                (struct Windows::Compat::Appraiser::ValidDataSourceComponents *)((char *)a6 + 1584),
                *((void **)a4 + 13),
                (__int64)hHeap);
        if ( v11 < 0 )
        {
          v14 = "Failed to initialize: [0x%x].";
          v13 = 104;
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xB68u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
            "Failed to initialize: [0x%x].",
            v11);
        v17 = v40;
        (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 1584);
      }
      if ( !*((_BYTE *)a4 + 4) )
      {
        if ( *((_BYTE *)a4 + 2) || *((_BYTE *)a4 + 3) )
        {
          v11 = Windows::Compat::Appraiser::MachineSdbDataSource::Initialize(
                  (char *)a6 + 2424,
                  *((_QWORD *)a4 + 13),
                  pszPathOut,
                  *((_QWORD *)a4 + 12),
                  hHeap);
          if ( v11 < 0 )
          {
            v14 = "Failed to initialize: [0x%x].";
            v13 = 115;
            goto LABEL_10;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xB73u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
              "Failed to initialize: [0x%x].",
              v11);
          v17 = v40;
          (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 2424);
        }
        if ( !*((_BYTE *)a4 + 4) && (*((_BYTE *)a4 + 1) || *((_BYTE *)a4 + 3)) )
        {
          v11 = Windows::Compat::Appraiser::OsUpgradeSdbDataSource::Initialize(
                  (char *)a6 + 4256,
                  *((_QWORD *)a4 + 13),
                  (char *)a4 + 112,
                  *((_QWORD *)a4 + 12),
                  pszPathOut,
                  hHeap);
          if ( v11 < 0 )
          {
            v14 = "Failed to initialize: [0x%x].";
            v13 = 126;
            goto LABEL_10;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xB7Eu,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
              "Failed to initialize: [0x%x].",
              v11);
          v17 = v40;
          (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 4256);
        }
      }
    }
  }
  if ( *((_BYTE *)a4 + 1) || *((_BYTE *)a4 + 3) )
  {
    v11 = Windows::Compat::Appraiser::MatchingInfoSdbDataSource::Initialize(
            (char *)a6 + 3176,
            *((_QWORD *)a4 + 13),
            (char *)a4 + 112,
            *((_QWORD *)a4 + 12),
            pszPathOut,
            hHeap,
            *((_BYTE *)a4 + 4));
    if ( v11 < 0 )
    {
      v14 = "Failed to initialize: [0x%x].";
      v13 = -119;
      goto LABEL_10;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB89u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
        "Failed to initialize: [0x%x].",
        v11);
    v17 = v40;
    (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 3176);
  }
  if ( !*((_BYTE *)a4 + 4) )
  {
    if ( *((_BYTE *)a4 + 1) || *((_BYTE *)a4 + 3) )
    {
      v41 = (unsigned __int64)a7 & -(__int64)(*((_BYTE *)a4 + 3) != 0);
      v38 = wcscmp_0(L"Server", *((const wchar_t **)a4 + 8)) == 0;
      if ( *((_QWORD *)a6 + 300) )
      {
        v11 = -2147023649;
LABEL_77:
        v14 = "Failed to initialize: [0x%x].";
        v13 = -106;
        goto LABEL_10;
      }
      v18 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc((const unsigned __int16 **)a6 + 300, pszPath);
      v11 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v36) = v18;
        LODWORD(dwFlags) = v18;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          83,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
          "Windows::Compat::Appraiser::InboxRequirementsDataSource::Initialize",
          dwFlags,
          (int)"Failed to copy resource xml path string: [0x%x].",
          v36);
        goto LABEL_77;
      }
      v19 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x53u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\inboxcomponentrequirements.cpp",
          "Windows::Compat::Appraiser::InboxRequirementsDataSource::Initialize",
          "Failed to copy resource xml path string: [0x%x].",
          v18);
        v19 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
      }
      *((_BYTE *)a6 + 2408) = v38;
      v20 = v41;
      v21 = v41 == 0;
      *((_BYTE *)a6 + 2409) = v41 != 0;
      if ( !v21 )
        *((_QWORD *)a6 + 302) = v20;
      if ( (v19 & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xB96u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
          "Failed to initialize: [0x%x].",
          0);
      v17 = v40;
      (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 2384);
    }
    if ( !*((_BYTE *)a4 + 4) )
    {
      if ( *((_BYTE *)a4 + 2) || *((_BYTE *)a4 + 3) )
        (*v17)[(*a3)++] = (struct IDataSource *)((char *)a6 + 808);
      if ( !*((_BYTE *)a4 + 4) )
      {
        if ( *((_BYTE *)a4 + 2) || *((_BYTE *)a4 + 3) )
          (*v17)[(*a3)++] = (struct IDataSource *)((char *)a6 + 4224);
        if ( !*((_BYTE *)a4 + 4) )
          goto LABEL_138;
      }
    }
  }
  v11 = Windows::Compat::Appraiser::ResolvedProgramsDataSource::Initialize(
          (struct Windows::Compat::Appraiser::ValidDataSourceComponents *)((char *)a6 + 5056),
          (struct RtlStringArray *)(v42 + 152));
  if ( v11 < 0 )
  {
    v14 = "Failed to initialize: [0x%x].";
    v13 = -77;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xBB3u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
      "Failed to initialize: [0x%x].",
      v11);
  v17 = v40;
  (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 5056);
  if ( !*((_BYTE *)a4 + 4) )
  {
LABEL_138:
    if ( *((_BYTE *)a4 + 1) || *((_BYTE *)a4 + 3) )
    {
      v39 = wcscmp_0(L"Server", *((const wchar_t **)a4 + 8)) == 0;
      if ( !*((_QWORD *)a6 + 9) )
      {
        v22 = Windows::Compat::Appraiser::Utilities::CopyStringAlloc((const unsigned __int16 **)a6 + 9, pszPath);
        if ( v22 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x52u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\antimalware.cpp",
              "Windows::Compat::Appraiser::AntiMalwareDataSource::Initialize",
              "Failed to copy resource path string: [0x%x].",
              v22);
          *((_BYTE *)a6 + 80) = v39;
        }
        else
        {
          LODWORD(v36) = v22;
          LODWORD(dwFlags) = v22;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            82,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\antimalware.cpp",
            "Windows::Compat::Appraiser::AntiMalwareDataSource::Initialize",
            dwFlags,
            (int)"Failed to copy resource path string: [0x%x].",
            v36);
        }
      }
      (*v17)[(*a3)++] = (struct IDataSource *)a6;
    }
    if ( !*((_BYTE *)a4 + 4) && (*((_BYTE *)a4 + 2) || *((_BYTE *)a4 + 3)) )
    {
      v23 = StringCchPrintfW((unsigned __int16 *)v57, 0x40u, L"MT_AppraiserTarget_%ls", *((_QWORD *)a4 + 4));
      v11 = v23;
      if ( v23 < 0 )
      {
        LODWORD(v36) = v23;
        v35 = "Failed to print target table: [0x%x].";
        v13 = -56;
        goto LABEL_11;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xBC8u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
          "Failed to print target table: [0x%x].",
          v23);
      v24 = Windows::Compat::Appraiser::AppraiserTarget::Initialize(
              (Windows::Compat::Appraiser::AppraiserTarget *)v52,
              v43,
              v57);
      v11 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v36) = v24;
        v35 = "Failed to initialize target: [0x%x].";
        v13 = -53;
        goto LABEL_11;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xBCBu,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
          "Failed to initialize target: [0x%x].",
          v24);
      v25 = Windows::Compat::Appraiser::WuDriverCoverageDataSource::Initialize(
              (struct Windows::Compat::Appraiser::ValidDataSourceComponents *)((char *)a6 + 5128),
              (const struct Windows::Compat::Appraiser::AppraiserTarget *)v52,
              1,
              0,
              0,
              0,
              0,
              0,
              0,
              0,
              0,
              0,
              0);
      v26 = v25;
      if ( v25 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xBD6u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
            "Failed to initialize, swallowing error: [0x%x].",
            v25);
        if ( !v26 )
          (*v40)[(*a3)++] = (struct IDataSource *)((char *)a6 + 5128);
      }
      else
      {
        LODWORD(v37) = v25;
        LODWORD(dwFlagsa) = v25;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          214,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents",
          dwFlagsa,
          (int)"Failed to initialize, swallowing error: [0x%x].",
          v37);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v55);
        v27 = (volatile signed __int64 *)v55;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v27 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v27,
          _InterlockedExchangeAdd64(v27 + 17, 0),
          v58);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v28);
        v29 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v43 = (struct Windows::Compat::Appraiser::DataFile *)v58;
          LODWORD(v41) = v26;
          v42 = "Windows::Compat::Appraiser::SetupAppraiser::InitializeDataSourceComponents";
          v47 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
          LODWORD(v40) = 3030;
          v48 = &szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v54 = SystemTime;
          v49 = &v54;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v29,
            (__int64)word_18029DF72,
            v30,
            v31,
            (__int64 *)&v49,
            &v48,
            (__int64)&v40,
            &v47,
            &v42,
            (__int64)&v41,
            (const char **)&v43);
        }
      }
    }
  }
  v11 = 0;
LABEL_133:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003b97c  push    rbp
0x18003b97e  push    rbx
0x18003b97f  push    rsi
0x18003b980  push    rdi
0x18003b981  push    r12
0x18003b983  push    r13
0x18003b985  push    r14
0x18003b987  push    r15
0x18003b989  lea     rbp, [rsp-608h]
0x18003b991  sub     rsp, 708h
0x18003b998  mov     [rbp+640h+var_650], 0FFFFFFFFFFFFFFFEh
0x18003b9a0  mov     rax, cs:__security_cookie
0x18003b9a7  xor     rax, rsp
0x18003b9aa  mov     [rbp+640h+var_50], rax
0x18003b9b1  mov     rdi, r9
0x18003b9b4  mov     r14, r8
0x18003b9b7  mov     rbx, rdx
0x18003b9ba  mov     [rsp+740h+var_6C8], rdx
0x18003b9bf  mov     [rbp+640h+var_6B8], rcx
0x18003b9c3  mov     rax, [rbp+640h+arg_20]
0x18003b9ca  mov     [rbp+640h+var_6B0], rax
0x18003b9ce  mov     r13, [rbp+640h+arg_28]
0x18003b9d5  xorps   xmm0, xmm0
0x18003b9d8  movups  xmmword ptr [rbp+640h+hHeap], xmm0
0x18003b9dc  movups  xmmword ptr [rbp+640h+lpMem], xmm0
0x18003b9e0  call    cs:__imp_GetProcessHeap
0x18003b9e6  mov     [rbp+640h+hHeap], rax
0x18003b9ea  mov     [rbp+640h+lpMem], 10h
0x18003b9f2  xorps   xmm0, xmm0
0x18003b9f5  movdqu  [rbp+640h+var_698], xmm0
0x18003b9fa  mov     [rbp+640h+lpMem+8], 0
0x18003ba02  mov     [rbp+640h+hHeap+8], 8
0x18003ba0a  xor     eax, eax
0x18003ba0c  movups  [rbp+640h+var_648], xmm0
0x18003ba10  movups  [rbp+640h+var_638], xmm0
0x18003ba14  mov     [rbp+640h+var_628], rax
0x18003ba18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ba1f  lea     ecx, [rax+60h]; unsigned __int64
0x18003ba22  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003ba27  mov     [rbx], rax
0x18003ba2a  test    rax, rax
0x18003ba2d  jnz     short loc_18003BA39
0x18003ba2f  mov     ebx, 8007000Eh
0x18003ba34  jmp     loc_18003C500
0x18003ba39  mov     rax, [rdi+20h]
0x18003ba3d  mov     [rbp+640h+var_6C0], rax
0x18003ba41  lea     rdx, [rbp+640h+var_6C0]
0x18003ba45  lea     rcx, [rbp+640h+hHeap]
0x18003ba49  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x18003ba4e  mov     ebx, eax
0x18003ba50  test    eax, eax
0x18003ba52  jns     short loc_18003BA8A
0x18003ba54  mov     dword ptr [rsp+740h+var_710], eax; char *
0x18003ba58  lea     r9, aRtlarrayAppend_2; "RtlArray Append failed: [0x%x]."
0x18003ba5f  mov     qword ptr [rsp+740h+var_718], r9; int
0x18003ba64  mov     [rsp+740h+dwFlags], eax; char *
0x18003ba68  lea     r9, aWindowsCompatA_0; "Windows::Compat::Appraiser::SetupApprai"...
0x18003ba6f  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003ba76  mov     edx, 0B32h; bool
0x18003ba7b  mov     ecx, 1; this
0x18003ba80  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18003ba85  jmp     loc_18003C500
0x18003ba8a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003ba90  mov     esi, 1
0x18003ba95  and     eax, esi
0x18003ba97  lea     r15, aWindowsCompatA_0; "Windows::Compat::Appraiser::SetupApprai"...
0x18003ba9e  lea     r12, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003baa5  test    al, al
0x18003baa7  jz      short loc_18003BAC4
0x18003baa9  mov     [rsp+740h+dwFlags], ebx; dwFlags
0x18003baad  lea     r9, aRtlarrayAppend_2; "RtlArray Append failed: [0x%x]."
0x18003bab4  mov     r8, r15; char *
0x18003bab7  mov     rdx, r12; char *
0x18003baba  mov     ecx, 0B32h; unsigned int
0x18003babf  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003bac4  lea     r9, aAcresDll_0; "acres.dll"
0x18003bacb  mov     r8, [rdi+28h]; pszPathIn
0x18003bacf  mov     edx, 104h; cchPathOut
0x18003bad4  lea     rcx, [rbp+640h+pszPathOut]; pszPathOut
0x18003badb  call    PathCchCombineEx
0x18003bae0  mov     ebx, eax
0x18003bae2  test    eax, eax
0x18003bae4  jns     short loc_18003BB0C
0x18003bae6  lea     rax, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003baed  mov     edx, 0B38h
0x18003baf2  mov     dword ptr [rsp+740h+var_710], ebx
0x18003baf6  mov     qword ptr [rsp+740h+var_718], rax
0x18003bafb  mov     [rsp+740h+dwFlags], ebx
0x18003baff  mov     r8, r12
0x18003bb02  mov     r9, r15
0x18003bb05  mov     ecx, esi
0x18003bb07  jmp     loc_18003BA80
0x18003bb0c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003bb12  and     eax, esi
0x18003bb14  test    al, al
0x18003bb16  jz      short loc_18003BB33
0x18003bb18  mov     [rsp+740h+dwFlags], ebx; dwFlags
0x18003bb1c  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003bb23  mov     r8, r15; char *
0x18003bb26  mov     rdx, r12; char *
0x18003bb29  mov     ecx, 0B38h; unsigned int
0x18003bb2e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003bb33  lea     r9, aCompatappraise_1; "compatAppraiserResources.dll"
0x18003bb3a  mov     r8, [rdi+28h]; pszPathIn
0x18003bb3e  mov     edx, 104h; cchPathOut
0x18003bb43  lea     rcx, [rbp+640h+pszPath]; pszPathOut
0x18003bb4a  call    PathCchCombineEx
0x18003bb4f  mov     ebx, eax
0x18003bb51  test    eax, eax
0x18003bb53  jns     short loc_18003BB6C
0x18003bb55  mov     dword ptr [rsp+740h+var_710], eax
0x18003bb59  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003bb60  mov     qword ptr [rsp+740h+var_718], r9
0x18003bb65  mov     edx, 0B3Eh
0x18003bb6a  jmp     short loc_18003BAFB
0x18003bb6c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003bb72  and     eax, esi
0x18003bb74  test    al, al
0x18003bb76  jz      short loc_18003BB93
0x18003bb78  mov     [rsp+740h+dwFlags], ebx
0x18003bb7c  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003bb83  mov     r8, r15; char *
0x18003bb86  mov     rdx, r12; char *
0x18003bb89  mov     ecx, 0B3Eh; unsigned int
0x18003bb8e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003bb93  lea     rcx, [rbp+640h+pszPathOut]; pszPath
0x18003bb9a  call    cs:__imp_PathFileExistsW
0x18003bba0  test    eax, eax
0x18003bba2  jnz     short loc_18003BBD1
0x18003bba4  mov     eax, 8007139Fh
0x18003bba9  mov     ebx, eax
0x18003bbab  lea     rcx, [rbp+640h+pszPathOut]
0x18003bbb2  mov     [rsp+740h+var_710], rcx
0x18003bbb7  lea     rcx, aRequiredDataSo; "Required Data Source file(s) do(es) not"...
0x18003bbbe  mov     qword ptr [rsp+740h+var_718], rcx
0x18003bbc3  mov     [rsp+740h+dwFlags], eax
0x18003bbc7  mov     edx, 0B43h
0x18003bbcc  jmp     loc_18003BAFF
0x18003bbd1  lea     rcx, [rbp+640h+pszPath]; pszPath
0x18003bbd8  call    cs:__imp_PathFileExistsW
0x18003bbde  test    eax, eax
0x18003bbe0  jnz     short loc_18003BC0F
0x18003bbe2  mov     eax, 8007139Fh
0x18003bbe7  mov     ebx, eax
0x18003bbe9  lea     rcx, [rbp+640h+pszPath]
0x18003bbf0  mov     [rsp+740h+var_710], rcx
0x18003bbf5  lea     rcx, aRequiredDataSo; "Required Data Source file(s) do(es) not"...
0x18003bbfc  mov     qword ptr [rsp+740h+var_718], rcx
0x18003bc01  mov     [rsp+740h+dwFlags], eax
0x18003bc05  mov     edx, 0B48h
0x18003bc0a  jmp     loc_18003BAFF
0x18003bc0f  cmp     byte ptr [rdi+4], 0
0x18003bc13  jnz     loc_18003BC9B
0x18003bc19  cmp     byte ptr [rdi], 0
0x18003bc1c  jnz     short loc_18003BC24
0x18003bc1e  cmp     byte ptr [rdi+3], 0
0x18003bc22  jz      short loc_18003BC9B
0x18003bc24  lea     rcx, [r13+58h]
0x18003bc28  lea     r9, [rbp+640h+hHeap]
0x18003bc2c  lea     r8, [rbp+640h+pszPathOut]
0x18003bc33  mov     rdx, [rdi+68h]
0x18003bc37  call    ?Initialize@BiosSdbDataSource@Appraiser@Compat@Windows@@QEAAJPEAXPEBGAEBV?$RtlArray@PEBG@@@Z; Windows::Compat::Appraiser::BiosSdbDataSource::Initialize(void *,ushort const *,RtlArray<ushort const *> const &)
0x18003bc3c  mov     ebx, eax
0x18003bc3e  test    eax, eax
0x18003bc40  jns     short loc_18003BC5C
0x18003bc42  mov     dword ptr [rsp+740h+var_710], eax
0x18003bc46  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003bc4d  mov     qword ptr [rsp+740h+var_718], r9
0x18003bc52  mov     edx, 0B52h
0x18003bc57  jmp     loc_18003BAFB
0x18003bc5c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003bc62  and     eax, esi
0x18003bc64  test    al, al
0x18003bc66  jz      short loc_18003BC83
0x18003bc68  mov     [rsp+740h+dwFlags], ebx
0x18003bc6c  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003bc73  mov     r8, r15; char *
0x18003bc76  mov     rdx, r12; char *
0x18003bc79  mov     ecx, 0B52h; unsigned int
0x18003bc7e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003bc83  mov     ecx, [r14]
0x18003bc86  mov     rbx, [rsp+740h+var_6C8]
0x18003bc8b  mov     rax, [rbx]
0x18003bc8e  lea     rdx, [r13+58h]
0x18003bc92  mov     [rax+rcx*8], rdx
0x18003bc96  add     [r14], esi
0x18003bc99  jmp     short loc_18003BCA0
0x18003bc9b  mov     rbx, [rsp+740h+var_6C8]
0x18003bca0  cmp     byte ptr [rdi+4], 0
0x18003bca4  jnz     loc_18003BEF1
0x18003bcaa  cmp     byte ptr [rdi+2], 0
0x18003bcae  jnz     short loc_18003BCB6
0x18003bcb0  cmp     byte ptr [rdi+3], 0
0x18003bcb4  jz      short loc_18003BD31
0x18003bcb6  lea     rcx, [rbp+640h+hHeap]
0x18003bcba  mov     qword ptr [rsp+740h+dwFlags], rcx
0x18003bcbf  mov     r9, [rdi+60h]
0x18003bcc3  lea     r8, [rbp+640h+pszPathOut]
0x18003bcca  mov     rdx, [rdi+68h]
0x18003bcce  lea     rcx, [r13+340h]
0x18003bcd5  call    ?Initialize@DeviceSdbDataSource@Appraiser@Compat@Windows@@QEAAJPEAXPEBG0AEBV?$RtlArray@PEBG@@@Z; Windows::Compat::Appraiser::DeviceSdbDataSource::Initialize(void *,ushort const *,void *,RtlArray<ushort const *> const &)
0x18003bcda  mov     ebx, eax
0x18003bcdc  test    eax, eax
0x18003bcde  jns     short loc_18003BCF1
0x18003bce0  lea     rax, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003bce7  mov     edx, 0B5Dh
0x18003bcec  jmp     loc_18003BAF2
0x18003bcf1  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003bcf7  and     eax, esi
0x18003bcf9  test    al, al
0x18003bcfb  jz      short loc_18003BD18
0x18003bcfd  mov     [rsp+740h+dwFlags], ebx
0x18003bd01  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003bd08  mov     r8, r15; char *
0x18003bd0b  mov     rdx, r12; char *
0x18003bd0e  mov     ecx, 0B5Dh; unsigned int
0x18003bd13  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003bd18  mov     ecx, [r14]
0x18003bd1b  mov     rbx, [rsp+740h+var_6C8]
0x18003bd20  mov     rax, [rbx]
0x18003bd23  lea     rdx, [r13+340h]
0x18003bd2a  mov     [rax+rcx*8], rdx
0x18003bd2e  add     [r14], esi
0x18003bd31  cmp     byte ptr [rdi+4], 0
0x18003bd35  jnz     loc_18003BEF1
0x18003bd3b  cmp     byte ptr [rdi+2], 0
0x18003bd3f  jnz     short loc_18003BD47
0x18003bd41  cmp     byte ptr [rdi+3], 0
0x18003bd45  jz      short loc_18003BDC2
0x18003bd47  lea     rcx, [rbp+640h+hHeap]
0x18003bd4b  mov     qword ptr [rsp+740h+dwFlags], rcx; __int64
0x18003bd50  mov     r9, [rdi+60h]
0x18003bd54  lea     r8, [rbp+640h+pszPathOut]
0x18003bd5b  mov     rdx, [rdi+68h]; Src
0x18003bd5f  lea     rcx, [r13+630h]; this
0x18003bd66  call    ?Initialize@DriverSdbDataSource@Appraiser@Compat@Windows@@QEAAJPEAXPEBG0AEBV?$RtlArray@PEBG@@@Z; Windows::Compat::Appraiser::DriverSdbDataSource::Initialize(void *,ushort const *,void *,RtlArray<ushort const *> const &)
0x18003bd6b  mov     ebx, eax
0x18003bd6d  test    eax, eax
0x18003bd6f  jns     short loc_18003BD82
0x18003bd71  lea     rax, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003bd78  mov     edx, 0B68h
0x18003bd7d  jmp     loc_18003BAF2
0x18003bd82  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003bd88  and     eax, esi
0x18003bd8a  test    al, al
0x18003bd8c  jz      short loc_18003BDA9
0x18003bd8e  mov     [rsp+740h+dwFlags], ebx
0x18003bd92  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003bd99  mov     r8, r15; char *
0x18003bd9c  mov     rdx, r12; char *
0x18003bd9f  mov     ecx, 0B68h; unsigned int
0x18003bda4  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003bda9  mov     ecx, [r14]
0x18003bdac  mov     rbx, [rsp+740h+var_6C8]
0x18003bdb1  mov     rax, [rbx]
0x18003bdb4  lea     rdx, [r13+630h]
0x18003bdbb  mov     [rax+rcx*8], rdx
0x18003bdbf  add     [r14], esi
0x18003bdc2  cmp     byte ptr [rdi+4], 0
0x18003bdc6  jnz     loc_18003BEF1
0x18003bdcc  cmp     byte ptr [rdi+2], 0
0x18003bdd0  jnz     short loc_18003BDD8
0x18003bdd2  cmp     byte ptr [rdi+3], 0
0x18003bdd6  jz      short loc_18003BE53
0x18003bdd8  lea     rcx, [rbp+640h+hHeap]
0x18003bddc  mov     qword ptr [rsp+740h+dwFlags], rcx
0x18003bde1  mov     r9, [rdi+60h]
0x18003bde5  lea     r8, [rbp+640h+pszPathOut]
0x18003bdec  mov     rdx, [rdi+68h]
0x18003bdf0  lea     rcx, [r13+978h]
0x18003bdf7  call    ?Initialize@MachineSdbDataSource@Appraiser@Compat@Windows@@QEAAJPEAXPEBG0AEBV?$RtlArray@PEBG@@@Z; Windows::Compat::Appraiser::MachineSdbDataSource::Initialize(void *,ushort const *,void *,RtlArray<ushort const *> const &)
0x18003bdfc  mov     ebx, eax
0x18003bdfe  test    eax, eax
0x18003be00  jns     short loc_18003BE13
0x18003be02  lea     rax, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003be09  mov     edx, 0B73h
0x18003be0e  jmp     loc_18003BAF2
0x18003be13  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003be19  and     eax, esi
0x18003be1b  test    al, al
0x18003be1d  jz      short loc_18003BE3A
0x18003be1f  mov     [rsp+740h+dwFlags], ebx
0x18003be23  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003be2a  mov     r8, r15; char *
0x18003be2d  mov     rdx, r12; char *
0x18003be30  mov     ecx, 0B73h; unsigned int
0x18003be35  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003be3a  mov     ecx, [r14]
0x18003be3d  mov     rbx, [rsp+740h+var_6C8]
0x18003be42  mov     rax, [rbx]
0x18003be45  lea     rdx, [r13+978h]
0x18003be4c  mov     [rax+rcx*8], rdx
0x18003be50  add     [r14], esi
0x18003be53  cmp     byte ptr [rdi+4], 0
0x18003be57  jnz     loc_18003BEF1
0x18003be5d  cmp     byte ptr [rdi+1], 0
0x18003be61  jnz     short loc_18003BE6D
0x18003be63  cmp     byte ptr [rdi+3], 0
0x18003be67  jz      loc_18003BEF1
0x18003be6d  lea     r8, [rdi+70h]
  ... truncated ...
```
