# Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder(ushort const *,ushort const * *,unsigned __int64,ushort const * *,unsigned __int64)

- ea: `0x180083f24`
- end: `0x180084c9f`
- name: `?DeleteFilesInFolder@Utilities@Appraiser@Compat@Windows@@SAJPEBGPEAPEBG_K12@Z`
- size: `3451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int64, unsigned __int16 **, unsigned __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048504`
- `0x18004ba00`

## callees

- `0x18000147c`
- `0x180008570`
- `0x1800092dc`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180052d0c`
- `0x1800839b8`
- `0x180083f24`
- `0x180087108`
- `0x18008b7b8`
- `0x18008e988`
- `0x1801abfd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084557`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180084557`
- `ntdll!RtlInitUnicodeString` at `0x180084638`
- `ntdll!RtlInitUnicodeString` at `0x180084638`
- `ntdll!NtCreateFile` at `0x1800846ac`
- `ntdll!NtCreateFile` at `0x1800846ac`
- `ntdll!NtClose` at `0x180084718`
- `ntdll!NtClose` at `0x180084718`
- `ntdll!RtlNtStatusToDosError` at `0x1800846b8`
- `ntdll!RtlNtStatusToDosError` at `0x1800846f8`
- `ntdll!RtlNtStatusToDosError` at `0x1800846b8`
- `ntdll!RtlNtStatusToDosError` at `0x1800846f8`
- `ntdll!NtSetInformationFile` at `0x1800846ea`
- `ntdll!NtSetInformationFile` at `0x1800846ea`
- `KERNEL32!FindClose` at `0x180084c4a`
- `KERNEL32!FindClose` at `0x180084c4a`
- `KERNEL32!FindNextFileW` at `0x180084b3b`
- `KERNEL32!FindNextFileW` at `0x180084b3b`
- `KERNEL32!FindFirstFileW` at `0x18008430d`
- `KERNEL32!FindFirstFileW` at `0x18008430d`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180084102`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18008459a`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180084102`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18008459a`
- `KERNEL32!DeleteFileW` at `0x18008494b`
- `KERNEL32!DeleteFileW` at `0x18008494b`
- `KERNEL32!GetSystemTime` at `0x18008488d`
- `KERNEL32!GetSystemTime` at `0x180084aa6`
- `KERNEL32!GetSystemTime` at `0x18008488d`
- `KERNEL32!GetSystemTime` at `0x180084aa6`
- `KERNEL32!CreateFileW` at `0x180084067`
- `KERNEL32!CreateFileW` at `0x180084067`
- `KERNEL32!CloseHandle` at `0x180084c6d`
- `KERNEL32!CloseHandle` at `0x180084c6d`
- `KERNEL32!GetLastError` at `0x18008407b`
- `KERNEL32!GetLastError` at `0x18008410c`
- `KERNEL32!GetLastError` at `0x18008431d`
- `KERNEL32!GetLastError` at `0x180084328`
- `KERNEL32!GetLastError` at `0x180084333`
- `KERNEL32!GetLastError` at `0x180084352`
- `KERNEL32!GetLastError` at `0x1800845a4`
- `KERNEL32!GetLastError` at `0x180084740`
- `KERNEL32!GetLastError` at `0x180084748`
- `KERNEL32!GetLastError` at `0x180084959`
- `KERNEL32!GetLastError` at `0x180084961`
- `KERNEL32!GetLastError` at `0x180084b49`
- `KERNEL32!GetLastError` at `0x180084b58`
- `KERNEL32!GetLastError` at `0x180084b77`
- `KERNEL32!GetLastError` at `0x18008407b`
- `KERNEL32!GetLastError` at `0x18008410c`
- `KERNEL32!GetLastError` at `0x18008431d`
- `KERNEL32!GetLastError` at `0x180084328`
- `KERNEL32!GetLastError` at `0x180084333`
- `KERNEL32!GetLastError` at `0x180084352`
- `KERNEL32!GetLastError` at `0x1800845a4`
- `KERNEL32!GetLastError` at `0x180084740`
- `KERNEL32!GetLastError` at `0x180084748`
- `KERNEL32!GetLastError` at `0x180084959`
- `KERNEL32!GetLastError` at `0x180084961`
- `KERNEL32!GetLastError` at `0x180084b49`
- `KERNEL32!GetLastError` at `0x180084b58`
- `KERNEL32!GetLastError` at `0x180084b77`
- `KERNEL32!SetLastError` at `0x180084700`
- `KERNEL32!SetLastError` at `0x18008473a`
- `KERNEL32!SetLastError` at `0x180084700`
- `KERNEL32!SetLastError` at `0x18008473a`
- `SHLWAPI!PathFileExistsW` at `0x18008401a`
- `SHLWAPI!PathFileExistsW` at `0x1800844c4`
- `SHLWAPI!PathFileExistsW` at `0x18008401a`
- `SHLWAPI!PathFileExistsW` at `0x1800844c4`
- `SHLWAPI!PathFindFileNameW` at `0x1800844eb`
- `SHLWAPI!PathFindFileNameW` at `0x180084531`
- `SHLWAPI!PathFindFileNameW` at `0x180084924`
- `SHLWAPI!PathFindFileNameW` at `0x1800844eb`
- `SHLWAPI!PathFindFileNameW` at `0x180084531`
- `SHLWAPI!PathFindFileNameW` at `0x180084924`

## string_xrefs

- `0x180083fbf`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083fef`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083fb3`: `Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder`
- `0x180083fe3`: `Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder`
- `0x180084094`: `Failed to open directory handle: [0x%x].`
- `0x1800840c2`: `Failed to open directory handle: [0x%x].`
- `0x180084138`: `Windows::Compat::Appraiser::IsDirectoryReparsePoint`
- `0x18008416b`: `Windows::Compat::Appraiser::IsDirectoryReparsePoint`
- `0x1800845d8`: `Windows::Compat::Appraiser::IsDirectoryReparsePoint`
- `0x180084ba7`: `Windows::Compat::Appraiser::IsDirectoryReparsePoint`
- `0x180083fa2`: `Failed to expand search directory: [0x%x].`
- `0x18008426c`: `Failed to copy expanded path: [0x%x].`
- `0x180084361`: `Failed to find first file in directory: [%d].`
- `0x180084195`: `Failed to query directory attributes: [0x%x].`
- `0x1800841f8`: `Failed to query directory attributes: [0x%x].`
- `0x1800841d0`: `Directory is a reparse point; refusing cleanup: %ls [0x%x].`
- `0x180084602`: `Failed to determine if directory is reparse point: [0x%x].`
- `0x180084bf8`: `Failed to determine if directory is reparse point: [0x%x].`
- `0x180084bcb`: `Directory is reparse point, aborting [0x%x].`
- `0x1800844a2`: `Failed to combine filename to delete: [0x%x].`
- `0x180084c13`: `Failed to combine filename to delete: [0x%x].`
- `0x180084b86`: `Failed to find next file in directory: [%d].`
- `0x18008475a`: `Failed to delete file in directory: [%d].`
- `0x180084973`: `Failed to delete file in directory: [%d].`
- `0x1800847b5`: `Failed to delete file on reboot: [0x%x].`
- `0x1800849ce`: `Failed to delete file on reboot: [0x%x].`
- `0x180084b16`: `Failed to delete file on reboot: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int64 a3,
        unsigned __int16 **a4,
        unsigned __int64 a5)
{
  __int64 FileW; // r13
  unsigned int v7; // edx
  int v8; // eax
  signed int v9; // ebx
  char v10; // dl
  signed int LastError; // eax
  signed int v12; // eax
  bool v13; // bl
  __int64 v14; // rax
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // r8
  WCHAR *v18; // rcx
  HRESULT v19; // eax
  unsigned __int64 v20; // rdx
  signed int v21; // eax
  int SystemTimeAsString; // eax
  char v23; // dl
  __int64 v24; // rax
  WCHAR *v25; // rcx
  __int64 v26; // rdx
  WCHAR *v27; // r8
  WCHAR *v28; // rcx
  unsigned __int16 **v29; // r15
  unsigned __int64 v30; // rbx
  const unsigned __int16 *FileNameW; // rax
  LPWSTR v32; // r15
  __int64 v33; // rbx
  signed int v34; // eax
  bool v35; // bl
  int v36; // eax
  ULONG v37; // ecx
  int v38; // eax
  int v39; // ebx
  ULONG v40; // eax
  DWORD v41; // ebx
  signed int v42; // eax
  int v43; // eax
  int v44; // r15d
  volatile signed __int64 *v45; // rcx
  void **v46; // rdx
  int v47; // ebx
  int v48; // r8d
  int v49; // r9d
  unsigned int v50; // ecx
  unsigned __int16 **v51; // rbx
  const unsigned __int16 *v52; // rax
  DWORD v53; // ebx
  signed int v54; // eax
  int v55; // eax
  volatile signed __int64 *v56; // rcx
  void **v57; // rdx
  int v58; // ebx
  int v59; // r8d
  int v60; // r9d
  signed int v61; // eax
  int v62; // r15d
  const char *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  const char *hTemplateFile; // [rsp+30h] [rbp-D0h]
  char v68[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v69; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 FileInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v71; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 **v72; // [rsp+78h] [rbp-88h]
  char *v73; // [rsp+80h] [rbp-80h] BYREF
  const char *v74; // [rsp+88h] [rbp-78h] BYREF
  const char *v75; // [rsp+90h] [rbp-70h] BYREF
  const char *v76; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hFindFile; // [rsp+B0h] [rbp-50h]
  struct _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 **v80; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v81; // [rsp+D8h] [rbp-28h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-10h] BYREF
  struct _SYSTEMTIME v84; // [rsp+120h] [rbp+20h] BYREF
  struct _SYSTEMTIME v85; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v86[144]; // [rsp+140h] [rbp+40h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+1D0h] [rbp+D0h] BYREF
  char v88[144]; // [rsp+420h] [rbp+320h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR pszPath[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  unsigned __int16 v91[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  WCHAR FileName[264]; // [rsp+AE0h] [rbp+9E0h] BYREF

  v81 = a3;
  v80 = a2;
  v72 = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileW = -1;
  memset_0(v91, 0, 0x208u);
  v8 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(pszPath, v7, a1);
  v9 = v8;
  if ( v8 < 0 )
  {
    LODWORD(hTemplateFile) = v8;
    dwFlagsAndAttributes = "Failed to expand search directory: [0x%x].";
    v10 = -104;
LABEL_3:
    LODWORD(dwCreationDisposition) = v9;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v10,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
      dwCreationDisposition,
      (int)dwFlagsAndAttributes,
      hTemplateFile);
    goto LABEL_147;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x198u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
      "Failed to expand search directory: [0x%x].",
      v8);
  if ( !PathFileExistsW(pszPath) )
  {
    v9 = 1;
    goto LABEL_147;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MSRC105182>::GetImpl'::`2'::impl) )
  {
    FileW = (__int64)CreateFileW(pszPath, 0xA0u, 7u, 0, 3u, 0x2200000u, 0);
    if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 < 0 )
      {
        LODWORD(hTemplateFile) = v9;
        dwFlagsAndAttributes = "Failed to open directory handle: [0x%x].";
        v10 = -86;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1AAu,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
          "Failed to open directory handle: [0x%x].",
          v9);
    }
    FileInformation = 0;
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v9 = -2147024890;
      goto LABEL_29;
    }
    if ( !GetFileInformationByHandleEx((HANDLE)FileW, FileAttributeTagInfo, &FileInformation, 8u) )
    {
      v12 = GetLastError();
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      if ( v9 < 0 )
      {
        LODWORD(hTemplateFile) = v9;
        LODWORD(dwCreationDisposition) = v9;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          8,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::IsDirectoryReparsePoint",
          dwCreationDisposition,
          (int)"GetFileInformationByHandleEx Failed: [0x%x].",
          hTemplateFile);
LABEL_29:
        LODWORD(hTemplateFile) = v9;
        dwFlagsAndAttributes = "Failed to query directory attributes: [0x%x].";
        v10 = -78;
        goto LABEL_3;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x108u,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::IsDirectoryReparsePoint",
          "GetFileInformationByHandleEx Failed: [0x%x].",
          v9);
    }
    v13 = (FileInformation & 0x400) != 0;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1B2u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
        "Failed to query directory attributes: [0x%x].",
        0);
    if ( v13 )
    {
      v9 = -2147020501;
      LODWORD(dwCreationDisposition) = -2147020501;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        183,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
        dwCreationDisposition,
        (int)"Directory is a reparse point; refusing cleanup: %ls [0x%x].",
        (const char *)pszPath,
        -2147020501);
      goto LABEL_147;
    }
  }
  v14 = 2147483646;
  v15 = pszPath;
  v16 = 260;
  v17 = FileName;
  do
  {
    if ( !v14 )
      break;
    if ( !*v15 )
      break;
    *v17++ = *v15++;
    --v14;
    --v16;
  }
  while ( v16 );
  v18 = v17 - 1;
  v9 = v16 == 0 ? 0x8007007A : 0;
  if ( v16 )
    v18 = v17;
  *v18 = 0;
  if ( !v16 )
  {
    LODWORD(hTemplateFile) = -2147024774;
    v10 = -67;
    dwFlagsAndAttributes = "Failed to copy expanded path: [0x%x].";
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1BDu,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
      "Failed to copy expanded path: [0x%x].",
      v16 == 0 ? 0x8007007A : 0);
  v19 = PathCchAppend(FileName, 0x104u, L"*");
  v9 = v19;
  if ( v19 < 0 )
  {
    LODWORD(hTemplateFile) = v19;
    v10 = -64;
    dwFlagsAndAttributes = "Failed to expand search directory: [0x%x].";
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1C0u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
      "Failed to expand search directory: [0x%x].",
      v19);
  hFindFile = FindFirstFileW(FileName, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    if ( GetLastError() == 2 || GetLastError() == 3 )
    {
      v9 = 0;
      goto LABEL_147;
    }
    v21 = GetLastError();
    v9 = v21;
    if ( v21 > 0 )
      v9 = (unsigned __int16)v21 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    LODWORD(hTemplateFile) = GetLastError();
    v10 = -52;
    dwFlagsAndAttributes = "Failed to find first file in directory: [%d].";
    goto LABEL_3;
  }
  SystemTimeAsString = Windows::Compat::Appraiser::Utilities::GetSystemTimeAsString(v91, v20);
  v9 = SystemTimeAsString;
  if ( SystemTimeAsString < 0 )
  {
    LODWORD(hTemplateFile) = SystemTimeAsString;
    dwFlagsAndAttributesa = "Failed to get current system time as string: [0x%x].";
    v23 = -48;
    goto LABEL_55;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1D0u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
      "Failed to get current system time as string: [0x%x].",
      SystemTimeAsString);
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      continue;
    v24 = 2147483646;
    v25 = pszPath;
    v26 = 260;
    v27 = ExistingFileName;
    do
    {
      if ( !v24 )
        break;
      if ( !*v25 )
        break;
      *v27++ = *v25++;
      --v24;
      --v26;
    }
    while ( v26 );
    v28 = v27 - 1;
    v9 = v26 == 0 ? 0x8007007A : 0;
    if ( v26 )
      v28 = v27;
    *v28 = 0;
    if ( !v26 )
    {
      LODWORD(hTemplateFile) = -2147024774;
      v23 = -34;
      dwFlagsAndAttributesa = "Failed to copy expanded path: [0x%x].";
      goto LABEL_55;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1DEu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
        "Failed to copy expanded path: [0x%x].",
        v26 == 0 ? 0x8007007A : 0);
    v9 = PathCchAppend(ExistingFileName, 0x104u, FindFileData.cFileName);
    if ( v9 < 0 )
    {
      LODWORD(hTemplateFile) = v9;
      dwFlagsAndAttributesa = "Failed to combine filename to delete: [0x%x].";
      v23 = -31;
      goto LABEL_55;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1E1u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
        "Failed to combine filename to delete: [0x%x].",
        v9);
    if ( !PathFileExistsW(ExistingFileName) )
      continue;
    v29 = v80;
    if ( v80 )
    {
      v30 = v81;
      if ( v81 )
      {
        FileNameW = PathFindFileNameW(ExistingFileName);
        if ( Windows::Compat::Appraiser::Utilities::IsInList(FileNameW, (const unsigned __int16 *const *const)v29, v30) )
          continue;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MSRC105182>::GetImpl'::`2'::impl) )
    {
      if ( v72 )
      {
        v32 = PathFindFileNameW(ExistingFileName);
        v33 = 0;
        if ( !a5 )
          continue;
        while ( (unsigned int)_o__wcsicmp(v32, v72[v33]) )
        {
          if ( ++v33 >= a5 )
            goto LABEL_132;
        }
      }
      v71 = 0;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v9 = -2147024890;
        v62 = -2147024890;
        goto LABEL_142;
      }
      if ( !GetFileInformationByHandleEx((HANDLE)FileW, FileAttributeTagInfo, &v71, 8u) )
      {
        v34 = GetLastError();
        v9 = v34;
        if ( v34 > 0 )
          v9 = (unsigned __int16)v34 | 0x80070000;
        if ( v9 < 0 )
        {
          LODWORD(hTemplateFile) = v9;
          LODWORD(dwCreationDisposition) = v9;
          v62 = v9;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            8,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::IsDirectoryReparsePoint",
            dwCreationDisposition,
            (int)"GetFileInformationByHandleEx Failed: [0x%x].",
            hTemplateFile);
LABEL_142:
          LODWORD(hTemplateFile) = v62;
          LODWORD(dwCreationDisposition) = v62;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            12,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
            dwCreationDisposition,
            (int)"Failed to determine if directory is reparse point: [0x%x].",
            hTemplateFile);
          goto LABEL_146;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x108u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::IsDirectoryReparsePoint",
            "GetFileInformationByHandleEx Failed: [0x%x].",
            v9);
      }
      v35 = (v71 & 0x400) != 0;
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x20Cu,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
          "Failed to determine if directory is reparse point: [0x%x].",
          0);
      if ( v35 )
      {
        LODWORD(hTemplateFile) = -2147020501;
        v9 = -2147020501;
        LODWORD(dwCreationDisposition) = -2147020501;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          17,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
          dwCreationDisposition,
          (int)"Directory is reparse point, aborting [0x%x].",
          hTemplateFile);
        goto LABEL_146;
      }
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, FindFileData.cFileName);
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 4160;
      ObjectAttributes.RootDirectory = (HANDLE)FileW;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      FileInformation = -1;
      IoStatusBlock = 0;
      v36 = NtCreateFile(
              (PHANDLE)&FileInformation,
              0x10080u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              7u,
              1u,
              0x200040u,
              0,
              0);
      if ( v36 >= 0 )
      {
        if ( (unsigned __int64)(FileInformation - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v68[0] = 1;
          v38 = NtSetInformationFile((HANDLE)FileInformation, &IoStatusBlock, v68, 1u, FileDispositionInformation);
          v39 = v38;
          if ( v38 < 0 )
          {
            v40 = RtlNtStatusToDosError(v38);
            SetLastError(v40);
          }
          if ( (unsigned __int64)(FileInformation - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            NtClose((HANDLE)FileInformation);
            FileInformation = -1;
          }
          if ( v39 >= 0 )
            continue;
          goto LABEL_102;
        }
        v37 = 6;
      }
      else
      {
        v37 = RtlNtStatusToDosError(v36);
      }
      SetLastError(v37);
LABEL_102:
      v41 = GetLastError();
      v42 = GetLastError();
      if ( v42 > 0 )
        v42 = (unsigned __int16)v42 | 0x80070000;
      LODWORD(hTemplateFile) = v41;
      LODWORD(dwCreationDisposition) = v42;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        22,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
        dwCreationDisposition,
        (int)"Failed to delete file in directory: [%d].",
        hTemplateFile);
      v43 = Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot(
              FindFileData.cFileName,
              ExistingFileName,
              (char *)pszPath,
              v91);
      v44 = v43;
      if ( v43 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
          continue;
        v50 = 536;
LABEL_131:
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          v50,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
          "Failed to delete file on reboot: [0x%x].",
          v44);
        continue;
      }
      LODWORD(hTemplateFile) = v43;
      LODWORD(dwCreationDisposition) = v43;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        24,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
        dwCreationDisposition,
        (int)"Failed to delete file on reboot: [0x%x].",
        hTemplateFile);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v86);
      v45 = (volatile signed __int64 *)v86;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v45 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v45,
        _InterlockedExchangeAdd64(v45 + 17, 0),
        v88);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v46);
      v47 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v69 = v44;
        v73 = v88;
        v74 = "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder";
        v76 = (const char *)&szValueBuf;
        v75 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        LODWORD(v71) = 536;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        *(_QWORD *)&DestinationString.Length = &v84;
        v84 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v47,
          (unsigned int)&word_1802A2336,
          v48,
          v49,
          (__int64)&DestinationString,
          (__int64)&v76,
          (__int64)&v71,
          (__int64)&v75,
          (__int64)&v74,
          (__int64)&v69,
          (__int64)&v73);
      }
      continue;
    }
    v51 = v72;
    if ( !v72
      || (v52 = PathFindFileNameW(ExistingFileName),
          Windows::Compat::Appraiser::Utilities::IsInList(v52, (const unsigned __int16 *const *const)v51, a5)) )
    {
      if ( !DeleteFileW(ExistingFileName) )
      {
        v53 = GetLastError();
        v54 = GetLastError();
        if ( v54 > 0 )
          v54 = (unsigned __int16)v54 | 0x80070000;
        LODWORD(hTemplateFile) = v53;
        LODWORD(dwCreationDisposition) = v54;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          43,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
          dwCreationDisposition,
          (int)"Failed to delete file in directory: [%d].",
          hTemplateFile);
        v55 = Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot(
                FindFileData.cFileName,
                ExistingFileName,
                (char *)pszPath,
                v91);
        v44 = v55;
        if ( v55 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
            continue;
          v50 = 557;
          goto LABEL_131;
        }
        LODWORD(hTemplateFile) = v55;
        LODWORD(dwCreationDisposition) = v55;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          45,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
          dwCreationDisposition,
          (int)"Failed to delete file on reboot: [0x%x].",
          hTemplateFile);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v86);
        v56 = (volatile signed __int64 *)v86;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v56 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v56,
          _InterlockedExchangeAdd64(v56 + 17, 0),
          v88);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v57);
        v58 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          LODWORD(v71) = v44;
          *(_QWORD *)&DestinationString.Length = v88;
          v76 = "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder";
          v74 = (const char *)&szValueBuf;
          v75 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
          v69 = 557;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v73 = (char *)&v85;
          v85 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v58,
            (unsigned int)byte_1802A22D3,
            v59,
            v60,
            (__int64)&v73,
            (__int64)&v74,
            (__int64)&v69,
            (__int64)&v75,
            (__int64)&v76,
            (__int64)&v71,
            (__int64)&DestinationString);
        }
      }
    }
LABEL_132:
    ;
  }
  while ( FindNextFileW(hFindFile, &FindFileData) );
  if ( GetLastError() == 18 )
  {
    v9 = 0;
  }
  else
  {
    v61 = GetLastError();
    v9 = v61;
    if ( v61 > 0 )
      v9 = (unsigned __int16)v61 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    LODWORD(hTemplateFile) = GetLastError();
    v23 = 53;
    dwFlagsAndAttributesa = "Failed to find next file in directory: [%d].";
LABEL_55:
    LODWORD(dwCreationDisposition) = v9;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v23,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFilesInFolder",
      dwCreationDisposition,
      (int)dwFlagsAndAttributesa,
      hTemplateFile);
  }
LABEL_146:
  FindClose(hFindFile);
LABEL_147:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MSRC105182>::GetImpl'::`2'::impl)
    && (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle((HANDLE)FileW);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180083f24  mov     [rsp-8+arg_8], rbx
0x180083f29  push    rbp
0x180083f2a  push    rsi
0x180083f2b  push    rdi
0x180083f2c  push    r12
0x180083f2e  push    r13
0x180083f30  push    r14
0x180083f32  push    r15
0x180083f34  lea     rbp, [rsp-0C00h]
0x180083f3c  sub     rsp, 0D00h
0x180083f43  mov     rax, cs:__security_cookie
0x180083f4a  xor     rax, rsp
0x180083f4d  mov     [rbp+0C30h+var_40], rax
0x180083f54  mov     [rbp+0C30h+var_C58], r8
0x180083f58  mov     rbx, rcx
0x180083f5b  mov     [rbp+0C30h+var_C60], rdx
0x180083f5f  lea     rcx, [rbp+0C30h+FindFileData]; void *
0x180083f66  xor     edx, edx; Val
0x180083f68  mov     [rsp+0D30h+var_CB8], r9
0x180083f6d  mov     r8d, 250h; Size
0x180083f73  call    memset_0
0x180083f78  xor     edx, edx; Val
0x180083f7a  lea     rcx, [rbp+0C30h+var_460]; void *
0x180083f81  mov     r8d, 208h; Size
0x180083f87  or      r13, 0FFFFFFFFFFFFFFFFh
0x180083f8b  call    memset_0
0x180083f90  mov     r8, rbx; unsigned __int16 *
0x180083f93  lea     rcx, [rbp+0C30h+pszPath]; lpDst
0x180083f9a  call    ?ExpandDirectory@Utilities@Appraiser@Compat@Windows@@SAJPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExpandDirectory(ushort *,ulong,ushort const *)
0x180083f9f  xor     r12d, r12d
0x180083fa2  lea     r15, aFailedToExpand_0; "Failed to expand search directory: [0x%"...
0x180083fa9  mov     ebx, eax
0x180083fab  test    eax, eax
0x180083fad  jns     short loc_180083FDD
0x180083faf  mov     dword ptr [rsp+0D30h+hTemplateFile], eax; char *
0x180083fb3  lea     r9, aWindowsCompatA_162; "Windows::Compat::Appraiser::Utilities::"...
0x180083fba  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], r15; int
0x180083fbf  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083fc6  mov     edx, 198h; bool
0x180083fcb  lea     ecx, [r13+2]; this
0x180083fcf  mov     [rsp+0D30h+dwCreationDisposition], ebx; char *
0x180083fd3  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180083fd8  jmp     loc_180084C50
0x180083fdd  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083fe3  lea     r14, aWindowsCompatA_162; "Windows::Compat::Appraiser::Utilities::"...
0x180083fea  mov     edi, 1
0x180083fef  lea     rsi, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083ff6  and     eax, edi
0x180083ff8  test    al, al
0x180083ffa  jz      short loc_180084013
0x180083ffc  mov     r9, r15; char *
0x180083fff  mov     [rsp+0D30h+dwCreationDisposition], ebx
0x180084003  mov     r8, r14; char *
0x180084006  mov     rdx, rsi; char *
0x180084009  mov     ecx, 198h; unsigned int
0x18008400e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180084013  lea     rcx, [rbp+0C30h+pszPath]; pszPath
0x18008401a  call    cs:__imp_PathFileExistsW
0x180084020  test    eax, eax
0x180084022  jnz     short loc_18008402B
0x180084024  mov     ebx, edi
0x180084026  jmp     loc_180084C50
0x18008402b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MSRC105182@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MSRC105182@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MSRC105182>::GetImpl(void)'::`2'::impl
0x180084032  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MSRC105182@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182>::__private_IsEnabled(void)
0x180084037  test    al, al
0x180084039  jz      loc_180084212
0x18008403f  xor     r9d, r9d; lpSecurityAttributes
0x180084042  mov     [rsp+0D30h+hTemplateFile], r12; hTemplateFile
0x180084047  mov     [rsp+0D30h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18008404f  lea     rcx, [rbp+0C30h+pszPath]; lpFileName
0x180084056  mov     edx, 0A0h; dwDesiredAccess
0x18008405b  mov     [rsp+0D30h+dwCreationDisposition], 3; dwCreationDisposition
0x180084063  lea     r8d, [r9+7]; dwShareMode
0x180084067  call    cs:__imp_CreateFileW
0x18008406d  mov     r13, rax
0x180084070  inc     rax
0x180084073  test    rax, 0FFFFFFFFFFFFFFFEh
0x180084079  jnz     short loc_1800840DD
0x18008407b  call    cs:__imp_GetLastError
0x180084081  mov     ebx, eax
0x180084083  test    eax, eax
0x180084085  jle     short loc_180084090
0x180084087  movzx   ebx, ax
0x18008408a  or      ebx, 80070000h
0x180084090  test    ebx, ebx
0x180084092  jns     short loc_1800840B6
0x180084094  lea     r9, aFailedToOpenDi; "Failed to open directory handle: [0x%x]"...
0x18008409b  mov     dword ptr [rsp+0D30h+hTemplateFile], ebx
0x18008409f  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], r9
0x1800840a4  mov     edx, 1AAh
0x1800840a9  mov     r9, r14
0x1800840ac  mov     r8, rsi
0x1800840af  mov     ecx, edi
0x1800840b1  jmp     loc_180083FCF
0x1800840b6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800840bc  and     eax, edi
0x1800840be  test    al, al
0x1800840c0  jz      short loc_1800840DD
0x1800840c2  lea     r9, aFailedToOpenDi; "Failed to open directory handle: [0x%x]"...
0x1800840c9  mov     [rsp+0D30h+dwCreationDisposition], ebx
0x1800840cd  mov     r8, r14; char *
0x1800840d0  mov     rdx, rsi; char *
0x1800840d3  mov     ecx, 1AAh; unsigned int
0x1800840d8  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800840dd  lea     rax, [r13-1]
0x1800840e1  mov     [rsp+0D30h+FileInformation], r12
0x1800840e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800840ea  ja      loc_1800841F3
0x1800840f0  mov     r9d, 8; dwBufferSize
0x1800840f6  lea     r8, [rsp+0D30h+FileInformation]; lpFileInformation
0x1800840fb  mov     rcx, r13; hFile
0x1800840fe  lea     edx, [r9+1]; FileInformationClass
0x180084102  call    cs:__imp_GetFileInformationByHandleEx
0x180084108  test    eax, eax
0x18008410a  jnz     short loc_18008417F
0x18008410c  call    cs:__imp_GetLastError
0x180084112  mov     ebx, eax
0x180084114  test    eax, eax
0x180084116  jle     short loc_180084121
0x180084118  movzx   ebx, ax
0x18008411b  or      ebx, 80070000h
0x180084121  test    ebx, ebx
0x180084123  jns     short loc_180084154
0x180084125  lea     r9, aGetfileinforma_0; "GetFileInformationByHandleEx Failed: [0"...
0x18008412c  mov     dword ptr [rsp+0D30h+hTemplateFile], ebx; char *
0x180084130  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], r9; int
0x180084135  mov     r8, rsi; unsigned int
0x180084138  lea     r9, aWindowsCompatA_829; "Windows::Compat::Appraiser::IsDirectory"...
0x18008413f  mov     [rsp+0D30h+dwCreationDisposition], ebx; char *
0x180084143  mov     edx, 108h; bool
0x180084148  mov     ecx, edi; this
0x18008414a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008414f  jmp     loc_1800841F8
0x180084154  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008415a  and     eax, edi
0x18008415c  test    al, al
0x18008415e  jz      short loc_18008417F
0x180084160  lea     r9, aGetfileinforma_0; "GetFileInformationByHandleEx Failed: [0"...
0x180084167  mov     [rsp+0D30h+dwCreationDisposition], ebx
0x18008416b  lea     r8, aWindowsCompatA_829; "Windows::Compat::Appraiser::IsDirectory"...
0x180084172  mov     rdx, rsi; char *
0x180084175  mov     ecx, 108h; unsigned int
0x18008417a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008417f  mov     ebx, dword ptr [rsp+0D30h+FileInformation]
0x180084183  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180084189  shr     ebx, 0Ah
0x18008418c  and     eax, edi
0x18008418e  and     bl, dil
0x180084191  test    al, al
0x180084193  jz      short loc_1800841B1
0x180084195  lea     r9, aFailedToQueryD; "Failed to query directory attributes: ["...
0x18008419c  mov     [rsp+0D30h+dwCreationDisposition], r12d
0x1800841a1  mov     r8, r14; char *
0x1800841a4  mov     rdx, rsi; char *
0x1800841a7  mov     ecx, 1B2h; unsigned int
0x1800841ac  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800841b1  test    bl, bl
0x1800841b3  jz      short loc_180084212
0x1800841b5  mov     eax, 8007112Bh
0x1800841ba  lea     rcx, [rbp+0C30h+pszPath]
0x1800841c1  mov     [rsp+0D30h+CreateDisposition], eax
0x1800841c5  mov     r9, r14; char *
0x1800841c8  mov     [rsp+0D30h+hTemplateFile], rcx; char *
0x1800841cd  mov     r8, rsi; unsigned int
0x1800841d0  lea     rcx, aDirectoryIsARe_0; "Directory is a reparse point; refusing "...
0x1800841d7  mov     edx, 1B7h; bool
0x1800841dc  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], rcx; int
0x1800841e1  mov     ebx, eax
0x1800841e3  mov     ecx, edi; this
0x1800841e5  mov     [rsp+0D30h+dwCreationDisposition], eax; char *
0x1800841e9  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800841ee  jmp     loc_180084C50
0x1800841f3  mov     ebx, 80070006h
0x1800841f8  lea     rax, aFailedToQueryD; "Failed to query directory attributes: ["...
0x1800841ff  mov     dword ptr [rsp+0D30h+hTemplateFile], ebx
0x180084203  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], rax
0x180084208  mov     edx, 1B2h
0x18008420d  jmp     loc_1800840A9
0x180084212  mov     eax, 7FFFFFFEh
0x180084217  lea     rcx, [rbp+0C30h+pszPath]
0x18008421e  mov     edx, 104h
0x180084223  lea     r8, [rbp+0C30h+FileName]
0x18008422a  test    rax, rax
0x18008422d  jz      short loc_18008424D
0x18008422f  movzx   r9d, word ptr [rcx]
0x180084233  test    r9w, r9w
0x180084237  jz      short loc_18008424D
0x180084239  mov     [r8], r9w
0x18008423d  add     rcx, 2
0x180084241  add     r8, 2
0x180084245  sub     rax, rdi
0x180084248  sub     rdx, rdi
0x18008424b  jnz     short loc_18008422A
0x18008424d  mov     rax, rdx
0x180084250  lea     rcx, [r8-2]
0x180084254  neg     rax
0x180084257  sbb     ebx, ebx
0x180084259  not     ebx
0x18008425b  and     ebx, 8007007Ah
0x180084261  test    rdx, rdx
0x180084264  cmovnz  rcx, r8
0x180084268  mov     [rcx], r12w
0x18008426c  lea     r12, aFailedToCopyEx_0; "Failed to copy expanded path: [0x%x]."
0x180084273  jnz     short loc_180084288
0x180084275  mov     dword ptr [rsp+0D30h+hTemplateFile], ebx
0x180084279  mov     edx, 1BDh
0x18008427e  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], r12
0x180084283  jmp     loc_1800840A9
0x180084288  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008428e  and     eax, edi
0x180084290  test    al, al
0x180084292  jz      short loc_1800842AB
0x180084294  mov     r9, r12; char *
0x180084297  mov     [rsp+0D30h+dwCreationDisposition], ebx
0x18008429b  mov     r8, r14; char *
0x18008429e  mov     rdx, rsi; char *
0x1800842a1  mov     ecx, 1BDh; unsigned int
0x1800842a6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800842ab  lea     r8, asc_18024084C; "*"
0x1800842b2  mov     edx, 104h; cchPath
0x1800842b7  lea     rcx, [rbp+0C30h+FileName]; pszPath
0x1800842be  call    PathCchAppend
0x1800842c3  mov     ebx, eax
0x1800842c5  test    eax, eax
0x1800842c7  jns     short loc_1800842DC
0x1800842c9  mov     dword ptr [rsp+0D30h+hTemplateFile], eax
0x1800842cd  mov     edx, 1C0h
0x1800842d2  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], r15
0x1800842d7  jmp     loc_1800840A9
0x1800842dc  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800842e2  and     eax, edi
0x1800842e4  test    al, al
0x1800842e6  jz      short loc_1800842FF
0x1800842e8  mov     r9, r15; char *
0x1800842eb  mov     [rsp+0D30h+dwCreationDisposition], ebx
0x1800842ef  mov     r8, r14; char *
0x1800842f2  mov     rdx, rsi; char *
0x1800842f5  mov     ecx, 1C0h; unsigned int
0x1800842fa  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800842ff  lea     rdx, [rbp+0C30h+FindFileData]; lpFindFileData
0x180084306  lea     rcx, [rbp+0C30h+FileName]; lpFileName
0x18008430d  call    cs:__imp_FindFirstFileW
0x180084313  mov     [rbp+0C30h+hFindFile], rax
0x180084317  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008431b  jnz     short loc_18008437D
0x18008431d  call    cs:__imp_GetLastError
0x180084323  cmp     eax, 2
0x180084326  jz      short loc_180084372
0x180084328  call    cs:__imp_GetLastError
0x18008432e  cmp     eax, 3
0x180084331  jz      short loc_180084372
0x180084333  call    cs:__imp_GetLastError
0x180084339  mov     ebx, eax
0x18008433b  test    eax, eax
0x18008433d  jle     short loc_180084348
0x18008433f  movzx   ebx, ax
0x180084342  or      ebx, 80070000h
0x180084348  test    ebx, ebx
0x18008434a  mov     eax, 80004005h
0x18008434f  cmovns  ebx, eax
0x180084352  call    cs:__imp_GetLastError
0x180084358  mov     dword ptr [rsp+0D30h+hTemplateFile], eax
0x18008435c  mov     edx, 1CCh
0x180084361  lea     rax, aFailedToFindFi; "Failed to find first file in directory:"...
0x180084368  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], rax
0x18008436d  jmp     loc_1800840A9
0x180084372  xor     r12d, r12d
0x180084375  mov     ebx, r12d
0x180084378  jmp     loc_180084C50
0x18008437d  lea     rcx, [rbp+0C30h+var_460]; unsigned __int16 *
0x180084384  call    ?GetSystemTimeAsString@Utilities@Appraiser@Compat@Windows@@SAJPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetSystemTimeAsString(ushort *,unsigned __int64)
0x180084389  xor     r15d, r15d
0x18008438c  mov     ebx, eax
0x18008438e  test    eax, eax
0x180084390  jns     short loc_1800843BD
0x180084392  lea     r9, aFailedToGetCur; "Failed to get current system time as st"...
0x180084399  mov     dword ptr [rsp+0D30h+hTemplateFile], eax; char *
0x18008439d  mov     qword ptr [rsp+0D30h+dwFlagsAndAttributes], r9; int
0x1800843a2  mov     edx, 1D0h; bool
0x1800843a7  mov     [rsp+0D30h+dwCreationDisposition], ebx; char *
0x1800843ab  mov     r8, rsi; unsigned int
0x1800843ae  mov     r9, r14; char *
0x1800843b1  mov     ecx, edi; this
0x1800843b3  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800843b8  jmp     loc_180084C46
0x1800843bd  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800843c3  and     eax, edi
0x1800843c5  test    al, al
0x1800843c7  jz      short loc_1800843E4
0x1800843c9  lea     r9, aFailedToGetCur; "Failed to get current system time as st"...
0x1800843d0  mov     [rsp+0D30h+dwCreationDisposition], ebx
0x1800843d4  mov     r8, r14; char *
0x1800843d7  mov     rdx, rsi; char *
0x1800843da  mov     ecx, 1D0h; unsigned int
0x1800843df  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800843e4  test    byte ptr [rbp+0C30h+FindFileData.dwFileAttributes], 10h
0x1800843eb  jnz     loc_180084B30
0x1800843f1  mov     eax, 7FFFFFFEh
0x1800843f6  lea     rcx, [rbp+0C30h+pszPath]
0x1800843fd  mov     edx, 104h
  ... truncated ...
```
