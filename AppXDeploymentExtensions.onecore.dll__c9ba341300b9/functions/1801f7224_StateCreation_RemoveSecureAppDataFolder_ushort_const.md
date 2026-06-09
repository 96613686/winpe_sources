# StateCreation::RemoveSecureAppDataFolder(ushort const *)

- ea: `0x1801f7224`
- end: `0x1801f7c58`
- name: `?RemoveSecureAppDataFolder@StateCreation@@AEAAJPEBG@Z`
- size: `2612`
- prototype: `__int64 __fastcall(StateCreation *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800a89f4`

## callees

- `0x18000e6e0`
- `0x180051330`
- `0x1800550f4`
- `0x18006cb78`
- `0x180093a18`
- `0x1800a8f80`
- `0x1800aa988`
- `0x1800ac630`
- `0x1800f0260`
- `0x1800f10e4`
- `0x1801e25e0`
- `0x1801e2664`
- `0x1801e7714`
- `0x1801f04a8`
- `0x1801f7224`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f728e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f747f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f7565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f728e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f747f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f7565`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801f7642`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801f76e8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801f775e`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801f7642`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801f76e8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801f775e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f7280`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f7557`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f7280`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f7557`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801f7716`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801f7716`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801f746d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801f746d`

## string_xrefs

- `0x1801f7780`: `Failed to set file delete disposition for folder %ls`
- `0x1801f7410`: `Failed to create full file name for folder %ls`
- `0x1801f7bd3`: `Failed to create full file name for file %ls`
- `0x1801f7a5c`: `Failed to compare file paths %ls, %ls`
- `0x1801f783a`: `Failed to get file hardlink information for file %ls`
- `0x1801f77be`: `File hardlink identified in files %ls`
- `0x1801f7664`: `Failed to set file delete disposition for file %ls`
- `0x1801f78bc`: `Failed to set file delete disposition for file %ls`
- `0x1801f739a`: `Failed to get file final path for folder %ls`
- `0x1801f7adb`: `Failed to get file final path for folder %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall StateCreation::RemoveSecureAppDataFolder(StateCreation *this, const unsigned __int16 *a2)
{
  Common::Deployment *FileW; // r15
  unsigned int *v4; // r8
  const char *v5; // rax
  unsigned int LastErrorMsg; // ebx
  struct Common::StringBuffer *v8; // r8
  const char *v9; // rax
  struct Common::StringBuffer *v10; // r9
  const char *v11; // rax
  const char *v12; // rax
  HANDLE FirstFileW; // rsi
  const unsigned __int16 *v14; // rdx
  const char *v15; // rax
  struct Common::StringBuffer *v16; // r9
  const unsigned __int16 *v17; // rbx
  HANDLE v18; // rdi
  struct Common::StringBuffer *v19; // r8
  int FinalPathFromHandle; // esi
  unsigned int *v21; // r8
  bool *v22; // r8
  const char *v23; // rax
  const char *v24; // rax
  const char *v25; // rax
  const char *v26; // rax
  const char *v27; // rax
  const char *v28; // rax
  const unsigned __int16 *v29; // rbx
  const char *v30; // rax
  const unsigned __int16 *v31; // rbx
  const char *v32; // rax
  const char *v33; // rax
  const char *v34; // rax
  const char *v35; // rax
  _BYTE v36[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+44h] [rbp-BCh] BYREF
  Common::Deployment *v38; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v39; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v40; // [rsp+58h] [rbp-A8h] BYREF
  int FileInformation; // [rsp+60h] [rbp-A0h] BYREF
  DirectoryPaths *v42[2]; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+78h] [rbp-88h]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-80h] BYREF
  int v45; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v46[2]; // [rsp+98h] [rbp-68h] BYREF
  int v47; // [rsp+A8h] [rbp-58h]
  LPCWSTR v48[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v49; // [rsp+C0h] [rbp-40h]
  HANDLE v50; // [rsp+C8h] [rbp-38h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  FileInformation = 1;
  FileW = (Common::Deployment *)CreateFileW(a2, 0xC0010000, 1u, 0, 3u, 0x2200000u, 0);
  v38 = FileW;
  if ( GetLastError() == 2 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    return 0;
  }
  if ( FileW == (Common::Deployment *)-1LL )
  {
    v5 = (const char *)RemovePIIfromFilePath(a2);
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x1019,
                     (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                     "Failed to get file handle for folder %ls",
                     v5);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    return LastErrorMsg;
  }
  v37 = 0;
  LastErrorMsg = Common::Deployment::GetFileAttributesFromHandle(FileW, &v37, v4);
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    v9 = (const char *)RemovePIIfromFilePath(a2);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x101D,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)LastErrorMsg,
      (int)"Failed to get file attributes from handle for folder %ls",
      v9);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    return LastErrorMsg;
  }
  if ( (v37 & 0x400) != 0 || (v37 & 0x10) == 0 )
  {
LABEL_38:
    if ( !SetFileInformationByHandle(FileW, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    {
      v24 = (const char *)RemovePIIfromFilePath(a2);
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x1077,
                       (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                       "Failed to set file delete disposition for folder %ls",
                       v24);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
      return LastErrorMsg;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    return 0;
  }
  *(_OWORD *)v42 = 0;
  v43 = 0;
  LastErrorMsg = Common::Deployment::GetFinalPathFromHandle(FileW, (Common::StringBuffer *)v42, v8);
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    v11 = (const char *)RemovePIIfromFilePath(a2);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1027,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)LastErrorMsg,
      (int)"Failed to get file final path for folder %ls",
      v11);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    return LastErrorMsg;
  }
  *(_OWORD *)lpFileName = 0;
  v45 = 0;
  LastErrorMsg = DirectoryPaths::CreateFullFileName(v42[1], L"*.dat*", (const unsigned __int16 *)lpFileName, v10);
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    v12 = (const char *)RemovePIIfromFilePath(a2);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x102B,
      (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
      (const char *)LastErrorMsg,
      (int)"Failed to create full file name for folder %ls",
      v12);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    return LastErrorMsg;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName[1], &FindFileData);
  v50 = FirstFileW;
  v39 = FirstFileW;
  if ( GetLastError() == 2 )
  {
LABEL_37:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
    goto LABEL_38;
  }
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v15 = (const char *)RemovePIIfromFilePath(lpFileName[1]);
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x1033,
                     (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                     "Failed to get file handle for file %ls",
                     v15);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
    return LastErrorMsg;
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  while ( 1 )
  {
    if ( DirectoryPaths::IsCurOrUpDir(FindFileData.cFileName, v14) )
      goto LABEL_35;
    LastErrorMsg = DirectoryPaths::CreateFullFileName(
                     v42[1],
                     FindFileData.cFileName,
                     (const unsigned __int16 *)v48,
                     v16);
    if ( (LastErrorMsg & 0x80000000) != 0 )
      break;
    v17 = v48[1];
    v18 = CreateFileW(v48[1], 0xC0010000, 1u, 0, 3u, 0x2200000u, 0);
    v40 = v18;
    if ( GetLastError() == 2 )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
    }
    else
    {
      if ( v18 == (HANDLE)-1LL )
      {
        v34 = (const char *)RemovePIIfromFilePath(v17);
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x104F,
                         (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                         "Failed to get file handle for file %ls",
                         v34);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
        return LastErrorMsg;
      }
      *(_OWORD *)v46 = 0;
      v47 = 0;
      FinalPathFromHandle = Common::Deployment::GetFinalPathFromHandle(v18, (Common::StringBuffer *)v46, v19);
      if ( FinalPathFromHandle < 0 )
      {
        v33 = (const char *)RemovePIIfromFilePath(v17);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1054,
          (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
          (const char *)(unsigned int)FinalPathFromHandle,
          (int)"Failed to get file final path for folder %ls",
          v33);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
        return (unsigned int)FinalPathFromHandle;
      }
      v37 = 1;
      FinalPathFromHandle = Common::String::CaseInsensitiveStartsWith(v46[1], (const unsigned __int16 *)v42[1], &v37);
      if ( FinalPathFromHandle < 0 )
      {
        v31 = RemovePIIfromFilePath((const unsigned __int16 *)v42[1]);
        v32 = (const char *)RemovePIIfromFilePath(v46[1]);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1059,
          (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
          (const char *)(unsigned int)FinalPathFromHandle,
          (int)"Failed to compare file paths %ls, %ls",
          v32,
          v31);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
        return (unsigned int)FinalPathFromHandle;
      }
      if ( !v37 )
      {
        v29 = RemovePIIfromFilePath((const unsigned __int16 *)v42[1]);
        v30 = (const char *)RemovePIIfromFilePath(v46[1]);
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x105A,
                         (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                         "File redirection identified in files %ls and %ls",
                         v30,
                         v29);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
        return LastErrorMsg;
      }
      v37 = 0;
      FinalPathFromHandle = Common::Deployment::GetFileAttributesFromHandle((Common::Deployment *)v18, &v37, v21);
      if ( FinalPathFromHandle < 0 )
      {
        v28 = (const char *)RemovePIIfromFilePath(v17);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x105E,
          (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
          (const char *)(unsigned int)FinalPathFromHandle,
          (int)"Failed to get file attributes from handle for folder %ls",
          v28);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
        return (unsigned int)FinalPathFromHandle;
      }
      if ( (v37 & 0x410) != 0 )
      {
        if ( (v37 & 0x400) != 0
          && !SetFileInformationByHandle(v18, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
        {
          v27 = (const char *)RemovePIIfromFilePath(v17);
          LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                           retaddr,
                           (void *)0x1070,
                           (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                           "Failed to set file delete disposition for file %ls",
                           v27);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
          return LastErrorMsg;
        }
      }
      else
      {
        v36[0] = 0;
        FinalPathFromHandle = HardLinkHelpers::GetIsFileHardLinked((HardLinkHelpers *)v18, v36, v22);
        if ( FinalPathFromHandle < 0 )
        {
          v26 = (const char *)RemovePIIfromFilePath(v17);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x1066,
            (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
            (const char *)(unsigned int)FinalPathFromHandle,
            (int)"Failed to get file hardlink information for file %ls",
            v26);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
          return (unsigned int)FinalPathFromHandle;
        }
        if ( v36[0] )
        {
          v25 = (const char *)RemovePIIfromFilePath(v17);
          LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                           retaddr,
                           (void *)0x1067,
                           (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                           "File hardlink identified in files %ls",
                           v25);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
          return LastErrorMsg;
        }
        if ( !SetFileInformationByHandle(v18, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
        {
          v23 = (const char *)RemovePIIfromFilePath(v17);
          LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                           retaddr,
                           (void *)0x106A,
                           (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
                           "Failed to set file delete disposition for file %ls",
                           v23);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
          return LastErrorMsg;
        }
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v40);
      FirstFileW = v50;
    }
LABEL_35:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
      goto LABEL_37;
    }
  }
  v35 = (const char *)RemovePIIfromFilePath((const unsigned __int16 *)v42[1]);
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x103F,
    (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
    (const char *)LastErrorMsg,
    (int)"Failed to create full file name for file %ls",
    v35);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v39);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x1801f7224  push    rbp
0x1801f7226  push    rbx
0x1801f7227  push    rsi
0x1801f7228  push    rdi
0x1801f7229  push    r14
0x1801f722b  push    r15
0x1801f722d  lea     rbp, [rsp-238h]
0x1801f7235  sub     rsp, 338h
0x1801f723c  mov     rax, cs:__security_cookie
0x1801f7243  xor     rax, rsp
0x1801f7246  mov     [rbp+260h+var_40], rax
0x1801f724d  mov     r14, rdx
0x1801f7250  mov     [rsp+360h+FileInformation], 1
0x1801f7258  mov     [rsp+360h+hTemplateFile], 0; hTemplateFile
0x1801f7261  mov     [rsp+360h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1801f7269  mov     [rsp+360h+dwCreationDisposition], 3; dwCreationDisposition
0x1801f7271  xor     r9d, r9d; lpSecurityAttributes
0x1801f7274  mov     edx, 0C0010000h; dwDesiredAccess
0x1801f7279  lea     r8d, [r9+1]; dwShareMode
0x1801f727d  mov     rcx, r14; lpFileName
0x1801f7280  call    cs:__imp_CreateFileW
0x1801f7286  mov     r15, rax
0x1801f7289  mov     [rsp+360h+var_318], rax
0x1801f728e  call    cs:__imp_GetLastError
0x1801f7294  cmp     eax, 2
0x1801f7297  jnz     short loc_1801F72A9
0x1801f7299  lea     rcx, [rsp+360h+var_318]
0x1801f729e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f72a3  nop
0x1801f72a4  jmp     loc_1801F7C37
0x1801f72a9  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1801f72ad  jnz     short loc_1801F72EF
0x1801f72af  mov     rcx, r14; unsigned __int16 *
0x1801f72b2  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801f72b7  mov     rcx, [rbp+268h]; this
0x1801f72be  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; char *
0x1801f72c3  lea     r9, aFailedToGetFil; "Failed to get file handle for folder %l"...
0x1801f72ca  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1801f72d1  mov     edx, 1019h; void *
0x1801f72d6  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1801f72db  mov     ebx, eax
0x1801f72dd  lea     rcx, [rsp+360h+var_318]
0x1801f72e2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f72e7  nop
0x1801f72e8  mov     eax, ebx
0x1801f72ea  jmp     loc_1801F7C39
0x1801f72ef  mov     [rsp+360h+var_31C], 0
0x1801f72f7  lea     rdx, [rsp+360h+var_31C]; void *
0x1801f72fc  mov     rcx, r15; this
0x1801f72ff  call    ?GetFileAttributesFromHandle@Deployment@Common@@YAJPEAXPEAK@Z; Common::Deployment::GetFileAttributesFromHandle(void *,ulong *)
0x1801f7304  mov     ebx, eax
0x1801f7306  test    eax, eax
0x1801f7308  jns     short loc_1801F734C
0x1801f730a  mov     rcx, r14; unsigned __int16 *
0x1801f730d  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801f7312  mov     rcx, [rbp+268h]; this
0x1801f7319  mov     qword ptr [rsp+360h+dwFlagsAndAttributes], rax; char *
0x1801f731e  lea     rax, aFailedToGetFil_2; "Failed to get file attributes from hand"...
0x1801f7325  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; int
0x1801f732a  mov     r9d, ebx; char *
0x1801f732d  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1801f7334  mov     edx, 101Dh; void *
0x1801f7339  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801f733e  nop
0x1801f733f  lea     rcx, [rsp+360h+var_318]
0x1801f7344  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f7349  nop
0x1801f734a  jmp     short loc_1801F72E8
0x1801f734c  test    [rsp+360h+var_31C], 400h
0x1801f7354  jnz     loc_1801F774C
0x1801f735a  test    byte ptr [rsp+360h+var_31C], 10h
0x1801f735f  jz      loc_1801F774C
0x1801f7365  xor     eax, eax
0x1801f7367  xorps   xmm0, xmm0
0x1801f736a  movups  xmmword ptr [rsp+360h+var_2F8], xmm0
0x1801f736f  mov     [rsp+360h+var_2E8], eax
0x1801f7373  lea     rdx, [rsp+360h+var_2F8]; this
0x1801f7378  mov     rcx, r15; hFile
0x1801f737b  call    ?GetFinalPathFromHandle@Deployment@Common@@YAJPEAXAEAVStringBuffer@2@@Z; Common::Deployment::GetFinalPathFromHandle(void *,Common::StringBuffer &)
0x1801f7380  mov     ebx, eax
0x1801f7382  test    eax, eax
0x1801f7384  jns     short loc_1801F73D5
0x1801f7386  mov     rcx, r14; unsigned __int16 *
0x1801f7389  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801f738e  mov     rcx, [rbp+268h]; this
0x1801f7395  mov     qword ptr [rsp+360h+dwFlagsAndAttributes], rax; char *
0x1801f739a  lea     rax, aFailedToGetFil_1; "Failed to get file final path for folde"...
0x1801f73a1  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; int
0x1801f73a6  mov     r9d, ebx; char *
0x1801f73a9  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1801f73b0  mov     edx, 1027h; void *
0x1801f73b5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801f73ba  lea     rcx, [rsp+360h+var_2F8]; this
0x1801f73bf  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f73c4  nop
0x1801f73c5  lea     rcx, [rsp+360h+var_318]
0x1801f73ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f73cf  nop
0x1801f73d0  jmp     loc_1801F72E8
0x1801f73d5  xor     eax, eax
0x1801f73d7  xorps   xmm0, xmm0
0x1801f73da  movups  xmmword ptr [rbp+260h+lpFileName], xmm0
0x1801f73de  mov     [rbp+260h+var_2D0], eax
0x1801f73e1  lea     r8, [rbp+260h+lpFileName]; unsigned __int16 *
0x1801f73e5  lea     rdx, aDat; "*.dat*"
0x1801f73ec  mov     rcx, [rsp+360h+var_2F8+8]; this
0x1801f73f1  call    ?CreateFullFileName@DirectoryPaths@@YAJPEBG0PEAVStringBuffer@Common@@@Z; DirectoryPaths::CreateFullFileName(ushort const *,ushort const *,Common::StringBuffer *)
0x1801f73f6  mov     ebx, eax
0x1801f73f8  test    eax, eax
0x1801f73fa  jns     short loc_1801F7454
0x1801f73fc  mov     rcx, r14; unsigned __int16 *
0x1801f73ff  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801f7404  mov     rcx, [rbp+268h]; this
0x1801f740b  mov     qword ptr [rsp+360h+dwFlagsAndAttributes], rax; char *
0x1801f7410  lea     rax, aFailedToCreate_0; "Failed to create full file name for fol"...
0x1801f7417  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; int
0x1801f741c  mov     r9d, ebx; char *
0x1801f741f  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1801f7426  mov     edx, 102Bh; void *
0x1801f742b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801f7430  lea     rcx, [rbp+260h+lpFileName]; this
0x1801f7434  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f7439  lea     rcx, [rsp+360h+var_2F8]; this
0x1801f743e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f7443  nop
0x1801f7444  lea     rcx, [rsp+360h+var_318]
0x1801f7449  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f744e  nop
0x1801f744f  jmp     loc_1801F72E8
0x1801f7454  xor     edx, edx; Val
0x1801f7456  mov     r8d, 250h; Size
0x1801f745c  lea     rcx, [rbp+260h+FindFileData]; void *
0x1801f7460  call    memset_0
0x1801f7465  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x1801f7469  mov     rcx, [rbp+260h+lpFileName+8]; lpFileName
0x1801f746d  call    cs:__imp_FindFirstFileW
0x1801f7473  mov     rsi, rax
0x1801f7476  mov     [rbp+260h+var_298], rax
0x1801f747a  mov     [rsp+360h+var_310], rax
0x1801f747f  call    cs:__imp_GetLastError
0x1801f7485  cmp     eax, 2
0x1801f7488  jz      loc_1801F772E
0x1801f748e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1801f7492  jnz     short loc_1801F74F2
0x1801f7494  mov     rcx, [rbp+260h+lpFileName+8]; unsigned __int16 *
0x1801f7498  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801f749d  mov     rcx, [rbp+268h]; this
0x1801f74a4  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; char *
0x1801f74a9  lea     r9, aFailedToGetFil_0; "Failed to get file handle for file %ls"
0x1801f74b0  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1801f74b7  mov     edx, 1033h; void *
0x1801f74bc  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1801f74c1  mov     ebx, eax
0x1801f74c3  lea     rcx, [rsp+360h+var_310]
0x1801f74c8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801f74cd  nop
0x1801f74ce  lea     rcx, [rbp+260h+lpFileName]; this
0x1801f74d2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f74d7  lea     rcx, [rsp+360h+var_2F8]; this
0x1801f74dc  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f74e1  nop
0x1801f74e2  lea     rcx, [rsp+360h+var_318]
0x1801f74e7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f74ec  nop
0x1801f74ed  jmp     loc_1801F72E8
0x1801f74f2  xor     eax, eax
0x1801f74f4  xorps   xmm0, xmm0
0x1801f74f7  movups  xmmword ptr [rbp+260h+var_2B0], xmm0
0x1801f74fb  mov     [rbp+260h+var_2A0], eax
0x1801f74fe  lea     rcx, [rbp+260h+FindFileData.cFileName]; lpString1
0x1801f7502  call    ?IsCurOrUpDir@DirectoryPaths@@YA_NPEBG@Z; DirectoryPaths::IsCurOrUpDir(ushort const *)
0x1801f7507  test    al, al
0x1801f7509  jnz     loc_1801F770F
0x1801f750f  lea     r8, [rbp+260h+var_2B0]; unsigned __int16 *
0x1801f7513  lea     rdx, [rbp+260h+FindFileData.cFileName]; unsigned __int16 *
0x1801f7517  mov     rcx, [rsp+360h+var_2F8+8]; this
0x1801f751c  call    ?CreateFullFileName@DirectoryPaths@@YAJPEBG0PEAVStringBuffer@Common@@@Z; DirectoryPaths::CreateFullFileName(ushort const *,ushort const *,Common::StringBuffer *)
0x1801f7521  mov     ebx, eax
0x1801f7523  test    eax, eax
0x1801f7525  js      loc_1801F7BBD
0x1801f752b  mov     [rsp+360h+hTemplateFile], 0; hTemplateFile
0x1801f7534  mov     [rsp+360h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1801f753c  mov     [rsp+360h+dwCreationDisposition], 3; dwCreationDisposition
0x1801f7544  xor     r9d, r9d; lpSecurityAttributes
0x1801f7547  mov     edx, 0C0010000h; dwDesiredAccess
0x1801f754c  lea     r8d, [r9+1]; dwShareMode
0x1801f7550  mov     rbx, [rbp+260h+var_2B0+8]
0x1801f7554  mov     rcx, rbx; lpFileName
0x1801f7557  call    cs:__imp_CreateFileW
0x1801f755d  mov     rdi, rax
0x1801f7560  mov     [rsp+360h+var_308], rax
0x1801f7565  call    cs:__imp_GetLastError
0x1801f756b  cmp     eax, 2
0x1801f756e  jnz     short loc_1801F7580
0x1801f7570  lea     rcx, [rsp+360h+var_308]
0x1801f7575  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f757a  nop
0x1801f757b  jmp     loc_1801F770F
0x1801f7580  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1801f7584  jz      loc_1801F7B4B
0x1801f758a  xor     eax, eax
0x1801f758c  xorps   xmm0, xmm0
0x1801f758f  movups  xmmword ptr [rbp+260h+var_2C8], xmm0
0x1801f7593  mov     [rbp+260h+var_2B8], eax
0x1801f7596  lea     rdx, [rbp+260h+var_2C8]; this
0x1801f759a  mov     rcx, rdi; hFile
0x1801f759d  call    ?GetFinalPathFromHandle@Deployment@Common@@YAJPEAXAEAVStringBuffer@2@@Z; Common::Deployment::GetFinalPathFromHandle(void *,Common::StringBuffer &)
0x1801f75a2  mov     esi, eax
0x1801f75a4  test    eax, eax
0x1801f75a6  js      loc_1801F7AC7
0x1801f75ac  mov     [rsp+360h+var_31C], 1
0x1801f75b4  lea     r8, [rsp+360h+var_31C]; int *
0x1801f75b9  mov     rdx, [rsp+360h+var_2F8+8]; unsigned __int16 *
0x1801f75be  mov     rcx, [rbp+260h+var_2C8+8]; unsigned __int16 *
0x1801f75c2  call    ?CaseInsensitiveStartsWith@String@Common@@SAJPEBG0PEAH@Z; Common::String::CaseInsensitiveStartsWith(ushort const *,ushort const *,int *)
0x1801f75c7  mov     esi, eax
0x1801f75c9  test    eax, eax
0x1801f75cb  js      loc_1801F7A35
0x1801f75d1  cmp     [rsp+360h+var_31C], 0
0x1801f75d6  jz      loc_1801F79A6
0x1801f75dc  mov     [rsp+360h+var_31C], 0
0x1801f75e4  lea     rdx, [rsp+360h+var_31C]; void *
0x1801f75e9  mov     rcx, rdi; this
0x1801f75ec  call    ?GetFileAttributesFromHandle@Deployment@Common@@YAJPEAXPEAK@Z; Common::Deployment::GetFileAttributesFromHandle(void *,ulong *)
0x1801f75f1  mov     esi, eax
0x1801f75f3  test    eax, eax
0x1801f75f5  js      loc_1801F7924
0x1801f75fb  test    [rsp+360h+var_31C], 410h
0x1801f7603  jnz     loc_1801F76CC
0x1801f7609  mov     [rsp+360h+var_320], 0
0x1801f760e  lea     rdx, [rsp+360h+var_320]; void *
0x1801f7613  mov     rcx, rdi; this
0x1801f7616  call    ?GetIsFileHardLinked@HardLinkHelpers@@YAJPEAXPEA_N@Z; HardLinkHelpers::GetIsFileHardLinked(void *,bool *)
0x1801f761b  mov     esi, eax
0x1801f761d  test    eax, eax
0x1801f761f  js      loc_1801F7826
0x1801f7625  cmp     [rsp+360h+var_320], 0
0x1801f762a  jnz     loc_1801F77AA
0x1801f7630  mov     r9d, 4; dwBufferSize
0x1801f7636  lea     r8, [rsp+360h+FileInformation]; lpFileInformation
0x1801f763b  lea     edx, [r9+11h]; FileInformationClass
0x1801f763f  mov     rcx, rdi; hFile
0x1801f7642  call    cs:__imp_SetFileInformationByHandle
0x1801f7648  test    eax, eax
0x1801f764a  jnz     loc_1801F76F6
0x1801f7650  mov     rcx, rbx; unsigned __int16 *
0x1801f7653  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801f7658  mov     rcx, [rbp+268h]; this
0x1801f765f  mov     qword ptr [rsp+360h+dwCreationDisposition], rax; char *
0x1801f7664  lea     r9, aFailedToSetFil; "Failed to set file delete disposition f"...
0x1801f766b  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1801f7672  mov     edx, 106Ah; void *
0x1801f7677  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1801f767c  mov     ebx, eax
0x1801f767e  lea     rcx, [rbp+260h+var_2C8]; this
0x1801f7682  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f7687  nop
0x1801f7688  lea     rcx, [rsp+360h+var_308]
0x1801f768d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f7692  nop
0x1801f7693  lea     rcx, [rbp+260h+var_2B0]; this
0x1801f7697  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f769c  nop
0x1801f769d  lea     rcx, [rsp+360h+var_310]
0x1801f76a2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801f76a7  nop
0x1801f76a8  lea     rcx, [rbp+260h+lpFileName]; this
0x1801f76ac  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f76b1  lea     rcx, [rsp+360h+var_2F8]; this
0x1801f76b6  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f76bb  nop
0x1801f76bc  lea     rcx, [rsp+360h+var_318]
0x1801f76c1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f76c6  nop
0x1801f76c7  jmp     loc_1801F72E8
0x1801f76cc  test    [rsp+360h+var_31C], 400h
0x1801f76d4  jz      short loc_1801F76F6
0x1801f76d6  mov     r9d, 4; dwBufferSize
0x1801f76dc  lea     r8, [rsp+360h+FileInformation]; lpFileInformation
0x1801f76e1  lea     edx, [r9+11h]; FileInformationClass
0x1801f76e5  mov     rcx, rdi; hFile
0x1801f76e8  call    cs:__imp_SetFileInformationByHandle
0x1801f76ee  test    eax, eax
0x1801f76f0  jz      loc_1801F78A8
0x1801f76f6  lea     rcx, [rbp+260h+var_2C8]; this
0x1801f76fa  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f76ff  nop
0x1801f7700  lea     rcx, [rsp+360h+var_308]
0x1801f7705  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801f770a  nop
0x1801f770b  mov     rsi, [rbp+260h+var_298]
0x1801f770f  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x1801f7713  mov     rcx, rsi; hFindFile
0x1801f7716  call    cs:__imp_FindNextFileW
0x1801f771c  test    eax, eax
0x1801f771e  jnz     loc_1801F74FE
0x1801f7724  lea     rcx, [rbp+260h+var_2B0]; this
0x1801f7728  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801f772d  nop
0x1801f772e  lea     rcx, [rsp+360h+var_310]
  ... truncated ...
```
