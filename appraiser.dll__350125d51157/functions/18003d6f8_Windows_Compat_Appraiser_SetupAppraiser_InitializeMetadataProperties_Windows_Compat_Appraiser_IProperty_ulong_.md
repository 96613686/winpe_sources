# Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties(Windows::Compat::Appraiser::IProperty * * &,ulong &,Windows::Compat::Appraiser::RunOptions &,Windows::Compat::Appraiser::DataFile &)

- ea: `0x18003d6f8`
- end: `0x18003f0b1`
- name: `?InitializeMetadataProperties@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEAPEAPEAVIProperty@234@AEAKAEAURunOptions@234@AEAVDataFile@234@@Z`
- size: `6585`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct Windows::Compat::Appraiser::IProperty ***, unsigned int *, struct Windows::Compat::Appraiser::RunOptions *, struct Windows::Compat::Appraiser::DataFile *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b30c`

## callees

- `0x180008570`
- `0x18000a594`
- `0x18000a5b8`
- `0x180011d94`
- `0x180013f90`
- `0x18001a558`
- `0x18002a8b4`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18003d6f8`
- `0x180082830`
- `0x18008aea4`
- `0x18008b018`
- `0x18008f1e8`
- `0x18008f7e4`
- `0x180096f80`
- `0x1800af9cc`
- `0x1801ac054`
- `0x1801fc634`
- `0x1802174cc`
- `0x1802174d8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18003d7df`
- `KERNEL32!InitOnceExecuteOnce` at `0x18003ee5a`
- `KERNEL32!InitOnceExecuteOnce` at `0x18003d7df`
- `KERNEL32!InitOnceExecuteOnce` at `0x18003ee5a`
- `KERNEL32!GetComputerNameW` at `0x18003e0fd`
- `KERNEL32!GetComputerNameW` at `0x18003e0fd`
- `KERNEL32!GetProductInfo` at `0x18003ec00`
- `KERNEL32!GetProductInfo` at `0x18003ec00`
- `KERNEL32!GetProcessHeap` at `0x18003d75d`
- `KERNEL32!GetProcessHeap` at `0x18003d76e`
- `KERNEL32!GetProcessHeap` at `0x18003d793`
- `KERNEL32!GetProcessHeap` at `0x18003d7a5`
- `KERNEL32!GetProcessHeap` at `0x18003d75d`
- `KERNEL32!GetProcessHeap` at `0x18003d76e`
- `KERNEL32!GetProcessHeap` at `0x18003d793`
- `KERNEL32!GetProcessHeap` at `0x18003d7a5`
- `KERNEL32!GetLastError` at `0x18003e107`
- `KERNEL32!GetLastError` at `0x18003e126`
- `KERNEL32!GetLastError` at `0x18003ec0a`
- `KERNEL32!GetLastError` at `0x18003ec29`
- `KERNEL32!GetLastError` at `0x18003e107`
- `KERNEL32!GetLastError` at `0x18003e126`
- `KERNEL32!GetLastError` at `0x18003ec0a`
- `KERNEL32!GetLastError` at `0x18003ec29`
- `KERNEL32!HeapFree` at `0x18003f060`
- `KERNEL32!HeapFree` at `0x18003f07f`
- `KERNEL32!HeapFree` at `0x18003f060`
- `KERNEL32!HeapFree` at `0x18003f07f`

## string_xrefs

- `0x18003d867`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003d89e`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003d950`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003da0f`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003dac9`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003db83`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003dc3c`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003dcf6`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003ddb0`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003de68`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003df1f`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003df75`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e02f`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e085`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e189`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e256`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e2fc`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e352`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e413`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e4c4`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e51a`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e5c7`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e6b0`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e701`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e745`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e79e`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e8b4`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e977`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003e9f2`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003eaee`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003ebca`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003ec94`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003ecea`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003edb3`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003ee2a`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003eeb9`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003efd3`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003f025`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003d86e`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003d897`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003d949`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003da08`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003dac2`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003db7c`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003dc35`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003dcef`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003dda9`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003de61`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003df18`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003df6e`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e028`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e07e`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e182`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e24f`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e2f5`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e34b`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e40c`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e4bd`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e513`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e5c0`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e6a9`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e6fa`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e73e`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e797`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e8ad`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e970`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e9eb`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003eae7`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003ebc3`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003ec8d`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003ece3`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003edac`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003ee23`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003eeb2`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003efcc`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003f01e`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties`
- `0x18003e14b`: `ComputerName`
- `0x18003e130`: `Error getting computer name: [%d].`
- `0x18003e680`: `Failed to copy path: [0x%x].`
- `0x18003e6a2`: `Failed to copy path: [0x%x].`
- `0x18003edd6`: `%lsDataExpDateExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::IProperty ***a2,
        unsigned int *a3,
        struct Windows::Compat::Appraiser::RunOptions *a4,
        struct Windows::Compat::Appraiser::DataFile *a5)
{
  struct Windows::Compat::Appraiser::RunOptions *v5; // r12
  unsigned __int64 v8; // rax
  struct Windows::Compat::Appraiser::IProperty **v9; // rax
  int v10; // eax
  int OsCaption; // ebx
  char v12; // dl
  struct _OSVERSIONINFOEXW *v13; // rdi
  const char *v14; // r9
  char v15; // dl
  const unsigned __int16 *v16; // rbx
  const char *v17; // rax
  signed int LastError; // eax
  int v19; // eax
  const unsigned __int16 *v20; // r8
  unsigned __int64 v21; // rdx
  bool IsVirtualMachine; // al
  const unsigned __int16 *v23; // r8
  char v24; // al
  const WCHAR *v25; // r9
  const WCHAR *v26; // r8
  unsigned __int64 v27; // rdx
  int SdbGuid; // eax
  unsigned __int64 v29; // r14
  __int64 *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // r10
  const unsigned __int16 **v34; // rdx
  unsigned __int64 v35; // rax
  const unsigned __int16 *v36; // rdx
  int v37; // eax
  unsigned __int64 v38; // r14
  unsigned __int64 v39; // r15
  char *v40; // r12
  char *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  const unsigned __int16 *v44; // r8
  const unsigned __int16 **v45; // rdx
  unsigned __int64 v46; // rax
  int OsVersionInfo; // eax
  signed int v48; // eax
  unsigned __int64 v49; // rax
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  unsigned __int64 v53; // r14
  unsigned __int64 v54; // r15
  char *v55; // r12
  const wchar_t **v56; // rcx
  __int64 v57; // rax
  const wchar_t *v58; // rdx
  size_t v59; // r8
  char *v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  const char *dwFlags; // [rsp+28h] [rbp-E0h]
  const char *v65; // [rsp+30h] [rbp-D8h]
  const char *v66; // [rsp+30h] [rbp-D8h]
  char *v67; // [rsp+38h] [rbp-D0h]
  struct _OSVERSIONINFOEXW *v68; // [rsp+48h] [rbp-C0h] BYREF
  DWORD nSize[2]; // [rsp+50h] [rbp-B8h] BYREF
  struct Windows::Compat::Appraiser::DataFile *v70; // [rsp+58h] [rbp-B0h]
  struct _OSVERSIONINFOEXW *v71; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE hHeap[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v73[4]; // [rsp+78h] [rbp-90h]
  char *lpMem_8; // [rsp+98h] [rbp-70h]
  HANDLE v75[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v76; // [rsp+B0h] [rbp-58h]
  LPVOID v77[2]; // [rsp+C0h] [rbp-48h]
  __int64 v78; // [rsp+D0h] [rbp-38h]
  WCHAR Buffer[264]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 v80[40]; // [rsp+2E8h] [rbp+1E0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+338h] [rbp+230h] BYREF

  v78 = -2;
  v5 = a4;
  hHeap[0] = a4;
  v70 = a5;
  nSize[0] = 0;
  nSize[1] = 0;
  LODWORD(v68) = 0;
  GetProcessHeap();
  v75[0] = GetProcessHeap();
  v77[0] = (LPVOID)16;
  v76 = 0;
  v77[1] = 0;
  v75[1] = (HANDLE)8;
  GetProcessHeap();
  hHeap[1] = GetProcessHeap();
  v73[3] = 16;
  *(_OWORD *)&v73[1] = 0;
  lpMem_8 = 0;
  v73[0] = 8;
  v71 = 0;
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
    Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
    0,
    0);
  v8 = 8 * (xmmword_1802CB3B8 + 32);
  if ( !is_mul_ok(xmmword_1802CB3B8 + 32, 8u) )
    v8 = -1;
  v9 = (struct Windows::Compat::Appraiser::IProperty **)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  *a2 = v9;
  if ( !v9 )
    goto LABEL_259;
  if ( (int)Windows::Compat::Appraiser::DataFile::GetInboxDataFileVersion((unsigned int *)&v68) >= 0 )
  {
    v10 = StringCchPrintfW(Buffer, 0x104u, L"%lu", (unsigned int)v68);
    OsCaption = v10;
    if ( v10 < 0 )
    {
      LODWORD(v67) = v10;
      v65 = "Printf failed: [0x%x].";
      v12 = -42;
LABEL_7:
      LODWORD(dwFlags) = OsCaption;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v12,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        dwFlags,
        (int)v65,
        v67);
      goto LABEL_260;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x8D6u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Printf failed: [0x%x].",
        v10);
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"InboxDataVersion",
                  Buffer,
                  0);
    if ( OsCaption < 0 )
    {
      v14 = "Failed to initialize: [0x%x].";
      v15 = -36;
LABEL_13:
      LODWORD(v67) = OsCaption;
      LODWORD(v66) = (_DWORD)v14;
      goto LABEL_257;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x8DCu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  v16 = Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
  if ( v16 )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"AppraiserVersion",
                  v16,
                  0);
    if ( OsCaption < 0 )
    {
      v15 = -24;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x8E8u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  if ( *((_BYTE *)v5 + 1) )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"Category",
                  L"Application",
                  0);
    if ( OsCaption < 0 )
    {
      v15 = -13;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x8F3u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  if ( *((_BYTE *)v5 + 2) )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"Category",
                  L"Device",
                  0);
    if ( OsCaption < 0 )
    {
      v15 = -2;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x8FEu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  if ( *(_BYTE *)v5 )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"Category",
                  L"System",
                  0);
    if ( OsCaption < 0 )
    {
      v15 = 9;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x909u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  if ( *((_BYTE *)v5 + 3) )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"Category",
                  L"Gated",
                  0);
    if ( OsCaption < 0 )
    {
      v15 = 20;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x914u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  if ( *((_BYTE *)v5 + 4) )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"Category",
                  L"Rescan",
                  0);
    if ( OsCaption < 0 )
    {
      v15 = 31;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x91Fu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  if ( *((_QWORD *)v5 + 7) )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"Namespace",
                  *((const unsigned __int16 **)v5 + 7),
                  0);
    if ( OsCaption < 0 )
    {
      v15 = 42;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x92Au,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsCaption = StringCchPrintfW(Buffer, 0x104u, L"%d", *(unsigned int *)((char *)v5 + 9));
  if ( OsCaption < 0 )
  {
    v14 = "Printf failed: [0x%x].";
    v15 = 55;
    goto LABEL_13;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x937u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Printf failed: [0x%x].",
      OsCaption);
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"OSDownlevelVersionMajor",
                Buffer,
                0);
  if ( OsCaption < 0 )
  {
    v15 = 58;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x93Au,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsCaption = StringCchPrintfW(Buffer, 0x104u, L"%d", *(unsigned int *)((char *)v5 + 13));
  if ( OsCaption < 0 )
  {
    v15 = 70;
LABEL_78:
    v17 = "Printf failed: [0x%x].";
    goto LABEL_255;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x946u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Printf failed: [0x%x].",
      OsCaption);
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"OSDownlevelVersionMinor",
                Buffer,
                0);
  if ( OsCaption < 0 )
  {
    v15 = 73;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x949u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  nSize[0] = 260;
  if ( !GetComputerNameW(Buffer, nSize) )
  {
    LastError = GetLastError();
    OsCaption = LastError;
    if ( LastError > 0 )
      OsCaption = (unsigned __int16)LastError | 0x80070000;
    if ( OsCaption >= 0 )
      OsCaption = -2147467259;
    LODWORD(v67) = GetLastError();
    v17 = "Error getting computer name: [%d].";
    v15 = 87;
    goto LABEL_256;
  }
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"ComputerName",
                Buffer,
                0);
  if ( OsCaption < 0 )
  {
    v15 = 91;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x95Bu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  v19 = wcscmp_0(L"Server", *((const wchar_t **)v5 + 8));
  v20 = L"Windows Server 2025";
  if ( v19 )
    v20 = L"Windows 11";
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"UplevelEdition",
                v20,
                0);
  if ( OsCaption < 0 )
  {
    v15 = 104;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x968u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsCaption = Windows::Compat::Appraiser::Utilities::GetOsCaption((LPBYTE)Buffer, v21);
  if ( OsCaption < 0 )
  {
    v14 = "GetOsCaption failed: [0x%x].";
    v15 = 116;
    goto LABEL_13;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x974u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "GetOsCaption failed: [0x%x].",
      OsCaption);
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"DownlevelEdition",
                Buffer,
                0);
  if ( OsCaption < 0 )
  {
    v15 = 119;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x977u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  IsVirtualMachine = Windows::Compat::Appraiser::Utilities::IsVirtualMachine();
  v23 = L"TRUE";
  if ( !IsVirtualMachine )
    v23 = L"FALSE";
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"IsVirtualMachine",
                v23,
                0);
  if ( OsCaption < 0 )
  {
    v15 = -123;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x985u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsCaption = StringCchPrintfW(Buffer, 0x104u, L"%hu", *((unsigned __int16 *)v5 + 44));
  if ( OsCaption < 0 )
  {
    v15 = -111;
    goto LABEL_78;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x991u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Printf failed: [0x%x].",
      OsCaption);
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"Architecture",
                Buffer,
                0);
  if ( OsCaption < 0 )
  {
    v15 = -108;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x994u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"ProductType",
                *((const unsigned __int16 **)v5 + 8),
                0);
  if ( OsCaption < 0 )
  {
    v15 = -96;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x9A0u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  if ( !*((_BYTE *)v5 + 4) )
  {
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v68 = v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    v24 = *((_BYTE *)v5 + 8);
    v25 = L"InboxAlternateData\\appraiser.sdb";
    if ( !v24 )
      v25 = L"appraiser.sdb";
    if ( *((_BYTE *)v5 + 7) || v24 )
      v26 = (const WCHAR *)*((_QWORD *)v5 + 6);
    else
      v26 = (const WCHAR *)*((_QWORD *)v5 + 5);
    OsCaption = PathCchCombineEx(pszPathOut, 0x104u, v26, v25, (ULONG)dwFlags);
    if ( OsCaption < 0 )
    {
      v14 = "Failed to copy path: [0x%x].";
      v15 = -79;
      goto LABEL_13;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9B1u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to copy path: [0x%x].",
        OsCaption);
    SdbGuid = Windows::Compat::Appraiser::SdbUtils::GetSdbGuid(v80, v27, pszPathOut);
    OsCaption = SdbGuid;
    if ( SdbGuid < 0 )
    {
      LODWORD(dwFlags) = SdbGuid;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        180,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        dwFlags,
        (int)"Failed to get Sdb guid from %ls: [0x%x].",
        (const char *)pszPathOut,
        SdbGuid,
        v68);
      goto LABEL_258;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9B4u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to get Sdb guid from %ls: [0x%x].",
        pszPathOut,
        SdbGuid);
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  L"SdbDbGuid",
                  v80,
                  0);
    if ( OsCaption < 0 )
    {
      v15 = -73;
      goto LABEL_254;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9B7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  }
  v29 = 0;
  if ( (_QWORD)xmmword_1802CB3B8 )
  {
    do
    {
      v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      v68 = v13;
      if ( !v13 )
        goto LABEL_259;
      *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
      *(_QWORD *)&v13->dwMinorVersion = 0;
      *(_QWORD *)&v13->dwPlatformId = 0;
      *(_QWORD *)&v13->szCSDVersion[2] = 0;
      *(_DWORD *)&v13->szCSDVersion[6] = 0;
      LOBYTE(v13->szCSDVersion[8]) = 0;
      v30 = 0;
      if ( v29 < (unsigned __int64)xmmword_1802CB3B8 )
      {
        if ( !is_mul_ok(
                (unsigned __int64)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupProperties + 1),
                v29)
          || (v30 = (__int64 *)(*((_QWORD *)&xmmword_1802CB3C8 + 1)
                              + (_QWORD)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupProperties + 1)
                              * v29),
              (unsigned __int64)v30 < *((_QWORD *)&xmmword_1802CB3C8 + 1)) )
        {
          v30 = 0;
        }
      }
      v31 = *v30;
      v32 = -1;
      do
        ++v32;
      while ( *(_WORD *)(v31 + 2 * v32) );
      v33 = v31 + 2 * v32;
      v34 = 0;
      if ( v29 < (unsigned __int64)xmmword_1802CB3B8 )
      {
        v35 = (_QWORD)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupProperties + 1) * v29;
        if ( !is_mul_ok(
                (unsigned __int64)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupProperties + 1),
                v29)
          || (v34 = (const unsigned __int16 **)(v35 + *((_QWORD *)&xmmword_1802CB3C8 + 1)),
              v35 + *((_QWORD *)&xmmword_1802CB3C8 + 1) < *((_QWORD *)&xmmword_1802CB3C8 + 1)) )
        {
          v34 = 0;
        }
      }
      OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                    (Windows::Compat::Appraiser::BasicProperty *)v13,
                    *v34,
                    (const unsigned __int16 *)(v33 + 2),
                    0);
      if ( OsCaption < 0 )
      {
        v15 = -57;
        goto LABEL_254;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x9C7u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
          "Failed to initialize: [0x%x].",
          OsCaption);
      (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
    }
    while ( ++v29 < (unsigned __int64)xmmword_1802CB3B8 );
  }
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"ApplicableTargetVersion",
                *((const unsigned __int16 **)v5 + 4),
                0);
  if ( OsCaption < 0 )
  {
    v15 = -39;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x9D9u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v37 = RtlNameValueArray::Insert((RtlNameValueArray *)&hHeap[1], v36, L"SVOverrideTargetXY", L"XY30H1", 0);
  OsCaption = v37;
  if ( v37 < 0 )
  {
    LODWORD(v67) = v37;
    v65 = "RtlArray Append failed: [0x%x].";
    v12 = -31;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x9E1u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "RtlArray Append failed: [0x%x].",
      v37);
  v38 = 0;
  v39 = v73[1];
  if ( v73[1] )
  {
    v40 = lpMem_8;
    do
    {
      v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      v68 = v13;
      if ( !v13 )
        goto LABEL_259;
      *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
      *(_QWORD *)&v13->dwMinorVersion = 0;
      *(_QWORD *)&v13->dwPlatformId = 0;
      *(_QWORD *)&v13->szCSDVersion[2] = 0;
      *(_DWORD *)&v13->szCSDVersion[6] = 0;
      LOBYTE(v13->szCSDVersion[8]) = 0;
      v41 = 0;
      if ( v38 < v39 )
      {
        if ( !is_mul_ok(v73[0], v38) || (v41 = &v40[v73[0] * v38], v41 < v40) )
          v41 = 0;
      }
      v42 = *(_QWORD *)v41;
      v43 = -1;
      do
        ++v43;
      while ( *(_WORD *)(v42 + 2 * v43) );
      v44 = (const unsigned __int16 *)(v42 + 2 * (v43 + 1));
      v45 = 0;
      if ( v38 < v39 )
      {
        v46 = v73[0] * v38;
        if ( !is_mul_ok(v73[0], v38) || (v45 = (const unsigned __int16 **)&v40[v46], &v40[v46] < v40) )
          v45 = 0;
      }
      OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                    (Windows::Compat::Appraiser::BasicProperty *)v13,
                    *v45,
                    v44,
                    0);
      if ( OsCaption < 0 )
      {
        v15 = -24;
        goto LABEL_254;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x9E8u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
          "Failed to initialize: [0x%x].",
          OsCaption);
      (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
      ++v38;
    }
    while ( v38 < v39 );
    v5 = (struct Windows::Compat::Appraiser::RunOptions *)hHeap[0];
  }
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = v13;
  if ( !v13 )
    goto LABEL_259;
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsVersionInfo = Windows::Compat::Appraiser::Utilities::GetOsVersionInfo((const struct _OSVERSIONINFOEXW **)&v71);
  OsCaption = OsVersionInfo;
  if ( OsVersionInfo < 0 )
  {
    LODWORD(v67) = OsVersionInfo;
    v66 = "Error getting os version: [0x%x].";
    v15 = -11;
    goto LABEL_257;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x9F5u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Error getting os version: [0x%x].",
      OsVersionInfo);
  if ( !GetProductInfo(
          v71->dwMajorVersion,
          v71->dwMinorVersion,
          v71->wServicePackMajor,
          v71->wServicePackMinor,
          &nSize[1]) )
  {
    v48 = GetLastError();
    OsCaption = v48;
    if ( v48 > 0 )
      OsCaption = (unsigned __int16)v48 | 0x80070000;
    if ( OsCaption >= 0 )
      OsCaption = -2147467259;
    LODWORD(v67) = GetLastError();
    v17 = "Error getting OS SKU: [%d].";
    v15 = -2;
    goto LABEL_256;
  }
  OsCaption = StringCchPrintfW(Buffer, 0x104u, L"0x%08X", nSize[1]);
  if ( OsCaption < 0 )
  {
    v14 = "Error printing value: [0x%x].";
    v15 = 2;
    goto LABEL_13;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA02u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Error printing value: [0x%x].",
      OsCaption);
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"HostOsSku",
                Buffer,
                0);
  if ( OsCaption < 0 )
  {
    v15 = 5;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA05u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v49 = Windows::Compat::Appraiser::Utilities::NowEpochCheckTestHookOverride();
  StringCchPrintfW(Buffer, 0x104u, L"%llu", v49);
  v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v71 = v13;
  if ( !v13 )
  {
LABEL_259:
    OsCaption = -2147024882;
    goto LABEL_260;
  }
  *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
  *(_QWORD *)&v13->dwMinorVersion = 0;
  *(_QWORD *)&v13->dwPlatformId = 0;
  *(_QWORD *)&v13->szCSDVersion[2] = 0;
  *(_DWORD *)&v13->szCSDVersion[6] = 0;
  LOBYTE(v13->szCSDVersion[8]) = 0;
  OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                (Windows::Compat::Appraiser::BasicProperty *)v13,
                L"NowTimeEpoch",
                Buffer,
                0);
  if ( OsCaption < 0 )
  {
    v15 = 20;
    goto LABEL_254;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA14u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to initialize: [0x%x].",
      OsCaption);
  (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
  v50 = StringCchPrintfW(Buffer, 0x104u, L"%lsDataExpDateExtension", *((_QWORD *)v5 + 4));
  OsCaption = v50;
  if ( v50 < 0 )
  {
    LODWORD(v67) = v50;
    v65 = "Failed to print string: [0x%x].";
    v12 = 33;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA21u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Failed to print string: [0x%x].",
      v50);
  v51 = *((_DWORD *)v70 + 162);
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
    Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
    0,
    0);
  v52 = Windows::Compat::Appraiser::Utilities::CalculateSdbVerExpDateExtensionProperties(
          (struct RtlNameValueArray *)v75,
          (const struct RtlNameValueArray *)&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAdditionalInitProperties,
          L"SETUPINIT_",
          v51);
  OsCaption = v52;
  if ( v52 < 0 )
  {
    LODWORD(v67) = v52;
    v65 = "Error calculating sdb ver expiration properties: [0x%x].";
    v12 = 39;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA27u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
      "Error calculating sdb ver expiration properties: [0x%x].",
      v52);
  v53 = 0;
  v54 = v76;
  OsCaption = 0;
  if ( !(_QWORD)v76 )
    goto LABEL_260;
  v55 = (char *)v77[1];
  while ( 1 )
  {
    v56 = 0;
    if ( v53 < v54 )
    {
      v57 = (unsigned __int64)v75[1] * v53;
      if ( !is_mul_ok((unsigned __int64)v75[1], v53) || (v56 = (const wchar_t **)&v55[v57], &v55[v57] < v55) )
        v56 = 0;
    }
    v58 = (const wchar_t *)*((_QWORD *)hHeap[0] + 4);
    v59 = -1;
    do
      ++v59;
    while ( v58[v59] );
    if ( wcsncmp_0(*v56, v58, v59) )
      goto LABEL_251;
    v13 = (struct _OSVERSIONINFOEXW *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v70 = (struct Windows::Compat::Appraiser::DataFile *)v13;
    if ( !v13 )
      goto LABEL_259;
    *(_QWORD *)&v13->dwOSVersionInfoSize = &Windows::Compat::Appraiser::BasicProperty::`vftable';
    *(_QWORD *)&v13->dwMinorVersion = 0;
    *(_QWORD *)&v13->dwPlatformId = 0;
    *(_QWORD *)&v13->szCSDVersion[2] = 0;
    *(_DWORD *)&v13->szCSDVersion[6] = 0;
    LOBYTE(v13->szCSDVersion[8]) = 0;
    v60 = 0;
    if ( v53 < v54 )
    {
      if ( !is_mul_ok((unsigned __int64)v75[1], v53) || (v60 = &v55[(unsigned __int64)v75[1] * v53], v60 < v55) )
        v60 = 0;
    }
    v61 = *(_QWORD *)v60;
    v62 = -1;
    do
      ++v62;
    while ( *(_WORD *)(v61 + 2 * v62) );
    OsCaption = Windows::Compat::Appraiser::BasicProperty::SetProperties(
                  (Windows::Compat::Appraiser::BasicProperty *)v13,
                  Buffer,
                  (const unsigned __int16 *)(v61 + 2 * (v62 + 1)),
                  0);
    if ( OsCaption < 0 )
      break;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA31u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
        "Failed to initialize: [0x%x].",
        OsCaption);
    (*a2)[(*a3)++] = (struct Windows::Compat::Appraiser::IProperty *)v13;
    OsCaption = 0;
LABEL_251:
    if ( ++v53 >= v54 )
      goto LABEL_260;
  }
  v15 = 49;
LABEL_254:
  v17 = "Failed to initialize: [0x%x].";
LABEL_255:
  LODWORD(v67) = OsCaption;
LABEL_256:
  LODWORD(v66) = (_DWORD)v17;
LABEL_257:
  LODWORD(dwFlags) = OsCaption;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v15,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::InitializeMetadataProperties",
    dwFlags,
    (int)v66,
    v67);
LABEL_258:
  (**(void (__fastcall ***)(struct _OSVERSIONINFOEXW *))&v13->dwOSVersionInfoSize)(v13);
LABEL_260:
  RtlStringArray::Clear((RtlStringArray *)&hHeap[1]);
  if ( lpMem_8 )
    HeapFree(hHeap[1], 0, lpMem_8);
  RtlStringArray::Clear((RtlStringArray *)v75);
  if ( v77[1] )
    HeapFree(v75[0], 0, v77[1]);
  return (unsigned int)OsCaption;
}

```

## disassembly

```asm
0x18003d6f8  mov     rax, rsp
0x18003d6fb  push    rbp
0x18003d6fc  push    rsi
0x18003d6fd  push    rdi
0x18003d6fe  push    r12
0x18003d700  push    r13
0x18003d702  push    r14
0x18003d704  push    r15
0x18003d706  lea     rbp, [rax-488h]
0x18003d70d  sub     rsp, 550h
0x18003d714  mov     [rbp+480h+var_4B8], 0FFFFFFFFFFFFFFFEh
0x18003d71c  mov     [rax+8], rbx
0x18003d720  mov     rax, cs:__security_cookie
0x18003d727  xor     rax, rsp
0x18003d72a  mov     [rbp+480h+var_40], rax
0x18003d731  mov     r12, r9
0x18003d734  mov     [rsp+580h+hHeap], r9
0x18003d739  mov     rsi, r8
0x18003d73c  mov     r13, rdx
0x18003d73f  mov     rax, [rbp+480h+arg_20]
0x18003d746  mov     [rsp+580h+var_530], rax
0x18003d74b  xor     r15d, r15d
0x18003d74e  mov     [rsp+580h+nSize], r15d
0x18003d753  mov     [rsp+580h+nSize+4], r15d
0x18003d758  mov     [rsp+580h+var_540], r15d
0x18003d75d  call    cs:__imp_GetProcessHeap
0x18003d763  xorps   xmm0, xmm0
0x18003d766  movups  xmmword ptr [rbp+480h+var_4E8], xmm0
0x18003d76a  movups  xmmword ptr [rbp+480h+var_4C8], xmm0
0x18003d76e  call    cs:__imp_GetProcessHeap
0x18003d774  mov     [rbp+480h+var_4E8], rax
0x18003d778  lea     ebx, [r15+10h]
0x18003d77c  mov     [rbp+480h+var_4C8], rbx
0x18003d780  xorps   xmm0, xmm0
0x18003d783  movdqu  [rbp+480h+var_4D8], xmm0
0x18003d788  mov     [rbp+480h+var_4C8+8], r15
0x18003d78c  lea     edi, [rbx-8]
0x18003d78f  mov     [rbp+480h+var_4E8+8], rdi
0x18003d793  call    cs:__imp_GetProcessHeap
0x18003d799  xorps   xmm0, xmm0
0x18003d79c  movups  xmmword ptr [rsp+580h+hHeap+8], xmm0
0x18003d7a1  movups  xmmword ptr [rbp+480h+lpMem], xmm0
0x18003d7a5  call    cs:__imp_GetProcessHeap
0x18003d7ab  mov     [rsp+580h+hHeap+8], rax
0x18003d7b0  mov     [rbp+480h+lpMem], rbx
0x18003d7b4  xorps   xmm0, xmm0
0x18003d7b7  movdqu  xmmword ptr [rsp+580h+var_510+8], xmm0
0x18003d7bd  mov     [rbp+480h+lpMem+8], r15
0x18003d7c1  mov     qword ptr [rsp+580h+var_510], rdi
0x18003d7c6  mov     [rsp+580h+var_528], r15
0x18003d7cb  xor     r9d, r9d; Context
0x18003d7ce  xor     r8d, r8d; Parameter
0x18003d7d1  lea     rdx, ?InitOnceCallback@AppraiserSettings@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003d7d8  lea     rcx, ?InitOnce@AppraiserSettings@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x18003d7df  call    cs:__imp_InitOnceExecuteOnce
0x18003d7e5  mov     rcx, qword ptr cs:xmmword_1802CB3B8
0x18003d7ec  add     rcx, 20h ; ' '
0x18003d7f0  mov     eax, edi
0x18003d7f2  mul     rcx
0x18003d7f5  lea     rcx, [rbx-11h]
0x18003d7f9  cmovb   rax, rcx
0x18003d7fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d804  mov     rcx, rax; unsigned __int64
0x18003d807  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003d80c  mov     [r13+0], rax
0x18003d810  test    rax, rax
0x18003d813  jz      loc_18003F041
0x18003d819  lea     rcx, [rsp+580h+var_540]; unsigned int *
0x18003d81e  call    ?GetInboxDataFileVersion@DataFile@Appraiser@Compat@Windows@@SAJAEAK@Z; Windows::Compat::Appraiser::DataFile::GetInboxDataFileVersion(ulong &)
0x18003d823  lea     rdi, aPrintfFailed0x; "Printf failed: [0x%x]."
0x18003d82a  lea     r14d, [r15+1]
0x18003d82e  test    eax, eax
0x18003d830  js      loc_18003D96E
0x18003d836  mov     r9d, [rsp+580h+var_540]
0x18003d83b  lea     r8, aLu; "%lu"
0x18003d842  mov     edx, 104h; unsigned __int64
0x18003d847  lea     rcx, [rbp+480h+Buffer]; unsigned __int16 *
0x18003d84b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d850  mov     ebx, eax
0x18003d852  test    eax, eax
0x18003d854  jns     short loc_18003D883
0x18003d856  mov     dword ptr [rsp+580h+var_550], eax; char *
0x18003d85a  mov     qword ptr [rsp+580h+var_558], rdi; int
0x18003d85f  mov     edx, 8D6h; bool
0x18003d864  mov     ecx, r14d; this
0x18003d867  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003d86e  lea     r9, aWindowsCompatA_776; "Windows::Compat::Appraiser::SetupApprai"...
0x18003d875  mov     [rsp+580h+dwFlags], ebx; char *
0x18003d879  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18003d87e  jmp     loc_18003F046
0x18003d883  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003d889  and     eax, r14d
0x18003d88c  test    al, al
0x18003d88e  jz      short loc_18003D8AF
0x18003d890  mov     [rsp+580h+dwFlags], ebx
0x18003d894  mov     r9, rdi; char *
0x18003d897  lea     r8, aWindowsCompatA_776; "Windows::Compat::Appraiser::SetupApprai"...
0x18003d89e  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003d8a5  mov     ecx, 8D6h; unsigned int
0x18003d8aa  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003d8af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d8b6  mov     ecx, 28h ; '('; unsigned __int64
0x18003d8bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d8c0  mov     rdi, rax
0x18003d8c3  mov     qword ptr [rsp+580h+var_540], rax
0x18003d8c8  test    rax, rax
0x18003d8cb  jz      loc_18003F041
0x18003d8d1  lea     rax, ??_7BasicProperty@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::BasicProperty::`vftable'
0x18003d8d8  mov     [rdi], rax
0x18003d8db  mov     [rdi+8], r15
0x18003d8df  mov     [rdi+10h], r15
0x18003d8e3  mov     [rdi+18h], r15
0x18003d8e7  mov     [rdi+20h], r15d
0x18003d8eb  mov     [rdi+24h], r15b
0x18003d8ef  test    rdi, rdi
0x18003d8f2  jz      loc_18003F041
0x18003d8f8  xor     r9d, r9d; unsigned int *
0x18003d8fb  lea     r8, [rbp+480h+Buffer]; unsigned __int16 *
0x18003d8ff  lea     rdx, aInboxdataversi; "InboxDataVersion"
0x18003d906  mov     rcx, rdi; this
0x18003d909  call    ?SetProperties@BasicProperty@Appraiser@Compat@Windows@@QEAAJPEBG0PEAK@Z; Windows::Compat::Appraiser::BasicProperty::SetProperties(ushort const *,ushort const *,ulong *)
0x18003d90e  mov     ebx, eax
0x18003d910  test    eax, eax
0x18003d912  jns     short loc_18003D931
0x18003d914  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003d91b  mov     edx, 8DCh
0x18003d920  mov     dword ptr [rsp+580h+var_550], ebx
0x18003d924  mov     qword ptr [rsp+580h+var_558], r9
0x18003d929  mov     ecx, r14d
0x18003d92c  jmp     loc_18003F01A
0x18003d931  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003d937  and     eax, r14d
0x18003d93a  test    al, al
0x18003d93c  jz      short loc_18003D961
0x18003d93e  mov     [rsp+580h+dwFlags], ebx
0x18003d942  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003d949  lea     r8, aWindowsCompatA_776; "Windows::Compat::Appraiser::SetupApprai"...
0x18003d950  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003d957  mov     ecx, 8DCh; unsigned int
0x18003d95c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003d961  mov     ecx, [rsi]
0x18003d963  mov     rax, [r13+0]
0x18003d967  mov     [rax+rcx*8], rdi
0x18003d96b  add     [rsi], r14d
0x18003d96e  call    ?AppraiserVersion@WicaFactory@Appraiser@Compat@Windows@@SAPEBGXZ; Windows::Compat::Appraiser::WicaFactory::AppraiserVersion(void)
0x18003d973  mov     rbx, rax
0x18003d976  test    rax, rax
0x18003d979  jz      loc_18003DA2D
0x18003d97f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d986  mov     ecx, 28h ; '('; unsigned __int64
0x18003d98b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d990  mov     rdi, rax
0x18003d993  mov     qword ptr [rsp+580h+var_540], rax
0x18003d998  test    rax, rax
0x18003d99b  jz      loc_18003F041
0x18003d9a1  lea     rax, ??_7BasicProperty@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::BasicProperty::`vftable'
0x18003d9a8  mov     [rdi], rax
0x18003d9ab  mov     [rdi+8], r15
0x18003d9af  mov     [rdi+10h], r15
0x18003d9b3  mov     [rdi+18h], r15
0x18003d9b7  mov     [rdi+20h], r15d
0x18003d9bb  mov     [rdi+24h], r15b
0x18003d9bf  test    rdi, rdi
0x18003d9c2  jz      loc_18003F041
0x18003d9c8  xor     r9d, r9d; unsigned int *
0x18003d9cb  mov     r8, rbx; unsigned __int16 *
0x18003d9ce  lea     rdx, aAppraiserversi; "AppraiserVersion"
0x18003d9d5  mov     rcx, rdi; this
0x18003d9d8  call    ?SetProperties@BasicProperty@Appraiser@Compat@Windows@@QEAAJPEBG0PEAK@Z; Windows::Compat::Appraiser::BasicProperty::SetProperties(ushort const *,ushort const *,ulong *)
0x18003d9dd  mov     ebx, eax
0x18003d9df  test    eax, eax
0x18003d9e1  jns     short loc_18003D9F0
0x18003d9e3  mov     edx, 8E8h
0x18003d9e8  mov     ecx, r14d
0x18003d9eb  jmp     loc_18003F00A
0x18003d9f0  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003d9f6  and     eax, r14d
0x18003d9f9  test    al, al
0x18003d9fb  jz      short loc_18003DA20
0x18003d9fd  mov     [rsp+580h+dwFlags], ebx
0x18003da01  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003da08  lea     r8, aWindowsCompatA_776; "Windows::Compat::Appraiser::SetupApprai"...
0x18003da0f  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003da16  mov     ecx, 8E8h; unsigned int
0x18003da1b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003da20  mov     ecx, [rsi]
0x18003da22  mov     rax, [r13+0]
0x18003da26  mov     [rax+rcx*8], rdi
0x18003da2a  add     [rsi], r14d
0x18003da2d  cmp     [r12+1], r15b
0x18003da32  jz      loc_18003DAE7
0x18003da38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003da3f  mov     ecx, 28h ; '('; unsigned __int64
0x18003da44  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003da49  mov     rdi, rax
0x18003da4c  mov     qword ptr [rsp+580h+var_540], rax
0x18003da51  test    rax, rax
0x18003da54  jz      loc_18003F041
0x18003da5a  lea     rax, ??_7BasicProperty@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::BasicProperty::`vftable'
0x18003da61  mov     [rdi], rax
0x18003da64  mov     [rdi+8], r15
0x18003da68  mov     [rdi+10h], r15
0x18003da6c  mov     [rdi+18h], r15
0x18003da70  mov     [rdi+20h], r15d
0x18003da74  mov     [rdi+24h], r15b
0x18003da78  test    rdi, rdi
0x18003da7b  jz      loc_18003F041
0x18003da81  xor     r9d, r9d; unsigned int *
0x18003da84  lea     r8, aApplication; "Application"
0x18003da8b  lea     rdx, aCategory; "Category"
0x18003da92  mov     rcx, rdi; this
0x18003da95  call    ?SetProperties@BasicProperty@Appraiser@Compat@Windows@@QEAAJPEBG0PEAK@Z; Windows::Compat::Appraiser::BasicProperty::SetProperties(ushort const *,ushort const *,ulong *)
0x18003da9a  mov     ebx, eax
0x18003da9c  test    eax, eax
0x18003da9e  jns     short loc_18003DAAA
0x18003daa0  mov     edx, 8F3h
0x18003daa5  jmp     loc_18003D9E8
0x18003daaa  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003dab0  and     eax, r14d
0x18003dab3  test    al, al
0x18003dab5  jz      short loc_18003DADA
0x18003dab7  mov     [rsp+580h+dwFlags], ebx
0x18003dabb  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003dac2  lea     r8, aWindowsCompatA_776; "Windows::Compat::Appraiser::SetupApprai"...
0x18003dac9  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003dad0  mov     ecx, 8F3h; unsigned int
0x18003dad5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003dada  mov     ecx, [rsi]
0x18003dadc  mov     rax, [r13+0]
0x18003dae0  mov     [rax+rcx*8], rdi
0x18003dae4  add     [rsi], r14d
0x18003dae7  cmp     [r12+2], r15b
0x18003daec  jz      loc_18003DBA1
0x18003daf2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003daf9  mov     ecx, 28h ; '('; unsigned __int64
0x18003dafe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003db03  mov     rdi, rax
0x18003db06  mov     qword ptr [rsp+580h+var_540], rax
0x18003db0b  test    rax, rax
0x18003db0e  jz      loc_18003F041
0x18003db14  lea     rax, ??_7BasicProperty@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::BasicProperty::`vftable'
0x18003db1b  mov     [rdi], rax
0x18003db1e  mov     [rdi+8], r15
0x18003db22  mov     [rdi+10h], r15
0x18003db26  mov     [rdi+18h], r15
0x18003db2a  mov     [rdi+20h], r15d
0x18003db2e  mov     [rdi+24h], r15b
0x18003db32  test    rdi, rdi
0x18003db35  jz      loc_18003F041
0x18003db3b  xor     r9d, r9d; unsigned int *
0x18003db3e  lea     r8, aDevice_0; "Device"
0x18003db45  lea     rdx, aCategory; "Category"
0x18003db4c  mov     rcx, rdi; this
0x18003db4f  call    ?SetProperties@BasicProperty@Appraiser@Compat@Windows@@QEAAJPEBG0PEAK@Z; Windows::Compat::Appraiser::BasicProperty::SetProperties(ushort const *,ushort const *,ulong *)
0x18003db54  mov     ebx, eax
0x18003db56  test    eax, eax
0x18003db58  jns     short loc_18003DB64
0x18003db5a  mov     edx, 8FEh
0x18003db5f  jmp     loc_18003D9E8
0x18003db64  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003db6a  and     eax, r14d
0x18003db6d  test    al, al
0x18003db6f  jz      short loc_18003DB94
0x18003db71  mov     [rsp+580h+dwFlags], ebx
0x18003db75  lea     r9, aFailedToInitia_13; "Failed to initialize: [0x%x]."
0x18003db7c  lea     r8, aWindowsCompatA_776; "Windows::Compat::Appraiser::SetupApprai"...
0x18003db83  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003db8a  mov     ecx, 8FEh; unsigned int
0x18003db8f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003db94  mov     ecx, [rsi]
0x18003db96  mov     rax, [r13+0]
0x18003db9a  mov     [rax+rcx*8], rdi
0x18003db9e  add     [rsi], r14d
0x18003dba1  cmp     [r12], r15b
0x18003dba5  jz      loc_18003DC5A
0x18003dbab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003dbb2  mov     ecx, 28h ; '('; unsigned __int64
0x18003dbb7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003dbbc  mov     rdi, rax
0x18003dbbf  mov     qword ptr [rsp+580h+var_540], rax
0x18003dbc4  test    rax, rax
0x18003dbc7  jz      loc_18003F041
0x18003dbcd  lea     rax, ??_7BasicProperty@Appraiser@Compat@Windows@@6B@; const Windows::Compat::Appraiser::BasicProperty::`vftable'
0x18003dbd4  mov     [rdi], rax
0x18003dbd7  mov     [rdi+8], r15
0x18003dbdb  mov     [rdi+10h], r15
0x18003dbdf  mov     [rdi+18h], r15
0x18003dbe3  mov     [rdi+20h], r15d
0x18003dbe7  mov     [rdi+24h], r15b
0x18003dbeb  test    rdi, rdi
0x18003dbee  jz      loc_18003F041
0x18003dbf4  xor     r9d, r9d; unsigned int *
0x18003dbf7  lea     r8, aSystem; "System"
0x18003dbfe  lea     rdx, aCategory; "Category"
0x18003dc05  mov     rcx, rdi; this
0x18003dc08  call    ?SetProperties@BasicProperty@Appraiser@Compat@Windows@@QEAAJPEBG0PEAK@Z; Windows::Compat::Appraiser::BasicProperty::SetProperties(ushort const *,ushort const *,ulong *)
0x18003dc0d  mov     ebx, eax
0x18003dc0f  test    eax, eax
0x18003dc11  jns     short loc_18003DC1D
0x18003dc13  mov     edx, 909h
  ... truncated ...
```
