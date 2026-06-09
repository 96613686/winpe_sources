# Microsoft::Diagnostics::Utils::FileSystem::CopyFiles(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState *,bool,ulong,ulong *,ulong,bool,int *,std::function<bool (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> *,std::function<long (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> *)

- ea: `0x1800f8674`
- end: `0x1800f9434`
- name: `?CopyFiles@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00PEAVEscalationWorkItemState@34@_NKPEAKK2PEAHPEAV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@6@PEAV?$function@$$A6AJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z@6@@Z`
- size: `3520`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, __int64, char, unsigned int, int *, DWORD dwCopyFlags, char, WINBOOL *, __int64, __int64)`
- caller_count: `5`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800f8674`
- `0x1801618f4`
- `0x1801db280`
- `0x1802b95cc`
- `0x180315410`

## callees

- `0x180020150`
- `0x180027c28`
- `0x180027e50`
- `0x18002b318`
- `0x18002be90`
- `0x18002cae0`
- `0x18002df00`
- `0x18003119c`
- `0x180064e6c`
- `0x180064e8c`
- `0x18008a4ec`
- `0x18009c7e4`
- `0x18009c8c0`
- `0x1800afab0`
- `0x1800c4b14`
- `0x1800c5130`
- `0x1800f8674`
- `0x1800f943c`
- `0x1800f9c5c`
- `0x180122958`
- `0x1801b7bd0`
- `0x1801df82c`
- `0x18020aac0`
- `0x18020bab8`
- `0x180369010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800f8fbc`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800f8fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f90c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f929a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f90c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f929a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f8775`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800f8775`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f8863`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f93d8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f8863`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f93d8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f8df5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f9228`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f9257`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f8df5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f9228`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800f9257`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f8b46`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f8b46`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9277`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f9277`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f928c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800f928c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f8e15`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800f8e15`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800f90ba`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x1800f90ba`

## string_xrefs

- `0x1800f8c06`: `Created directory: `
- `0x1800f8b71`: `Path exceeded maximum length. Failed to create directory: `
- `0x1800f90e3`: `Failed to copy file due to sharing violation: `

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::CopyFiles(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        char a5,
        unsigned int a6,
        int *a7,
        DWORD dwCopyFlags,
        char a9,
        WINBOOL *a10,
        __int64 a11,
        __int64 a12)
{
  int v16; // eax
  const WCHAR *v17; // rcx
  char *FirstFileW; // r15
  __int64 v19; // rdx
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  int appended; // eax
  unsigned int v31; // ebx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  unsigned int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // r8
  __int64 v51; // r8
  const WCHAR *v52; // rcx
  unsigned int v53; // ebx
  __int64 v54; // r8
  __int64 v55; // r8
  __int128 v56; // xmm6
  __int64 v57; // r8
  __int128 v58; // xmm7
  __int64 v59; // rax
  __int64 v60; // r8
  int v61; // ebx
  const WCHAR *v62; // rcx
  const WCHAR *v63; // rcx
  LPCWSTR *v64; // rax
  LPCWSTR *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // r8
  __int64 v70; // rcx
  int v71; // eax
  __int64 v72; // r8
  void *v73; // rbx
  __int64 v74; // r8
  char *v75; // rdx
  const WCHAR *v76; // rdx
  const WCHAR *v77; // rcx
  const char *v78; // r9
  unsigned int v79; // ebx
  __int64 v80; // r8
  const WCHAR *v81; // rcx
  const WCHAR *v82; // rcx
  const WCHAR *v83; // rcx
  const char *v84; // r9
  unsigned int v85; // ebx
  unsigned int LastError; // ebx
  int pbCancel; // [rsp+20h] [rbp-548h]
  int pbCancela; // [rsp+20h] [rbp-548h]
  __int64 v89; // [rsp+60h] [rbp-508h] BYREF
  char *v90; // [rsp+68h] [rbp-500h] BYREF
  int v91[4]; // [rsp+70h] [rbp-4F8h] BYREF
  int v92[4]; // [rsp+80h] [rbp-4E8h] BYREF
  __int64 v93; // [rsp+90h] [rbp-4D8h]
  __int64 v94; // [rsp+98h] [rbp-4D0h]
  LPBOOL v95; // [rsp+A0h] [rbp-4C8h]
  int v96[4]; // [rsp+B0h] [rbp-4B8h] BYREF
  _QWORD v97[2]; // [rsp+C0h] [rbp-4A8h] BYREF
  _QWORD v98[2]; // [rsp+D0h] [rbp-498h] BYREF
  _QWORD v99[2]; // [rsp+E0h] [rbp-488h] BYREF
  _QWORD v100[2]; // [rsp+F0h] [rbp-478h] BYREF
  _QWORD v101[2]; // [rsp+100h] [rbp-468h] BYREF
  _QWORD v102[2]; // [rsp+110h] [rbp-458h] BYREF
  _QWORD v103[2]; // [rsp+120h] [rbp-448h] BYREF
  _QWORD v104[2]; // [rsp+130h] [rbp-438h] BYREF
  _QWORD v105[2]; // [rsp+140h] [rbp-428h] BYREF
  __int128 v106; // [rsp+150h] [rbp-418h] BYREF
  __int128 v107; // [rsp+160h] [rbp-408h] BYREF
  _BYTE v108[16]; // [rsp+170h] [rbp-3F8h] BYREF
  _BYTE v109[16]; // [rsp+180h] [rbp-3E8h] BYREF
  _BYTE v110[16]; // [rsp+190h] [rbp-3D8h] BYREF
  _BYTE v111[16]; // [rsp+1A0h] [rbp-3C8h] BYREF
  _BYTE v112[16]; // [rsp+1B0h] [rbp-3B8h] BYREF
  _BYTE v113[16]; // [rsp+1C0h] [rbp-3A8h] BYREF
  _BYTE v114[16]; // [rsp+1D0h] [rbp-398h] BYREF
  _BYTE v115[16]; // [rsp+1E0h] [rbp-388h] BYREF
  char v116; // [rsp+1F0h] [rbp-378h] BYREF
  char v117; // [rsp+200h] [rbp-368h] BYREF
  _BYTE v118[16]; // [rsp+210h] [rbp-358h] BYREF
  _BYTE v119[16]; // [rsp+220h] [rbp-348h] BYREF
  LPCWSTR lpExistingFileName[3]; // [rsp+230h] [rbp-338h] BYREF
  unsigned __int64 v121; // [rsp+248h] [rbp-320h]
  LPCWSTR lpPathName[3]; // [rsp+250h] [rbp-318h] BYREF
  unsigned __int64 v123; // [rsp+268h] [rbp-300h]
  LPCWSTR lpFileName[2]; // [rsp+270h] [rbp-2F8h] BYREF
  __int128 v125; // [rsp+280h] [rbp-2E8h]
  _BYTE v126[32]; // [rsp+290h] [rbp-2D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+2B0h] [rbp-2B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+0h]

  v95 = a10;
  v94 = a11;
  v93 = a12;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  std::wstring::wstring(lpExistingFileName);
  std::wstring::wstring(lpPathName);
  if ( a7 )
    v16 = *a7;
  else
    v16 = 0;
  LODWORD(v89) = v16;
  *(_OWORD *)lpFileName = 0;
  v125 = 0;
  std::wstring::_Construct<1,wchar_t *>(lpFileName, *a1, a1[1]);
  v17 = (const WCHAR *)lpFileName;
  if ( *((_QWORD *)&v125 + 1) > 7u )
    v17 = lpFileName[0];
  FirstFileW = (char *)FindFirstFileW(v17, &FindFileData);
  v90 = FirstFileW;
  std::wstring::_Tidy_deallocate(lpFileName);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x40A,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                  v21);
    std::wstring::_Tidy_deallocate(lpPathName);
    std::wstring::_Tidy_deallocate(lpExistingFileName);
    return LastError;
  }
  while ( 1 )
  {
    v22 = std::_WChar_traits<wchar_t>::length(L"<>:\"/\\|?*", v19, v20, v21);
    v25 = std::_WChar_traits<wchar_t>::length(FindFileData.cFileName, v23, v22, v24);
    pbCancel = v26;
    if ( std::_Traits_find_first_of<std::char_traits<wchar_t>>(FindFileData.cFileName, v25, v26, L"<>:\"/\\|?*") != -1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x414,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)0x8007007BLL,
        pbCancel);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
      std::wstring::_Tidy_deallocate(lpPathName);
      std::wstring::_Tidy_deallocate(lpExistingFileName);
      return 2147942523LL;
    }
    std::wstring::_Assign<wchar_t>(lpExistingFileName, *a2, a2[1]);
    v97[0] = FindFileData.cFileName;
    v97[1] = std::_WChar_traits<wchar_t>::length(FindFileData.cFileName, v27, v28, v29);
    appended = Microsoft::Diagnostics::Utils::String::AppendPath(lpExistingFileName, v97);
    v31 = appended;
    if ( appended < 0 )
      break;
    std::wstring::_Assign<wchar_t>(lpPathName, *a3, a3[1]);
    v98[0] = FindFileData.cFileName;
    v98[1] = std::_WChar_traits<wchar_t>::length(FindFileData.cFileName, v33, v34, v35);
    v36 = Microsoft::Diagnostics::Utils::String::AppendPath(lpPathName, v98);
    v40 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)(unsigned int)v36,
        pbCancel);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
      std::wstring::_Tidy_deallocate(lpPathName);
      std::wstring::_Tidy_deallocate(lpExistingFileName);
      return v40;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      v99[0] = L".";
      v99[1] = std::_WChar_traits<wchar_t>::length(L".", v37, v38, v39);
      v100[0] = FindFileData.cFileName;
      v100[1] = std::_WChar_traits<wchar_t>::length(FindFileData.cFileName, v41, v42, v43);
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v100, v99) )
        goto LABEL_78;
      v101[0] = L"..";
      v101[1] = std::_WChar_traits<wchar_t>::length(L"..", v44, v45, v46);
      v102[0] = FindFileData.cFileName;
      v102[1] = std::_WChar_traits<wchar_t>::length(FindFileData.cFileName, v47, v48, v49);
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v102, v101) )
        goto LABEL_78;
      *(_OWORD *)v96 = *(_OWORD *)a2;
      *(_OWORD *)v92 = *(_OWORD *)std::wstring::operator std::wstring_view(lpExistingFileName, v108, v50);
      if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v92, v96) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          (const char *)0x8007010BLL,
          pbCancel);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
        std::wstring::_Tidy_deallocate(lpPathName);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        return 2147942667LL;
      }
      *(_OWORD *)v92 = *(_OWORD *)a3;
      *(_OWORD *)v96 = *(_OWORD *)std::wstring::operator std::wstring_view(lpPathName, v109, v51);
      if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v96, v92) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x430,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          (const char *)0x8007010BLL,
          pbCancel);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
        std::wstring::_Tidy_deallocate(lpPathName);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        return 2147942667LL;
      }
      Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(lpPathName);
      v52 = (const WCHAR *)lpPathName;
      if ( v123 > 7 )
        v52 = lpPathName[0];
      if ( CreateDirectoryW(v52, 0) )
      {
        if ( a4 )
        {
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          *(_OWORD *)v92 = *(_OWORD *)std::wstring::operator std::wstring_view(lpExistingFileName, v110, v54);
          Microsoft::Diagnostics::WideStringStream::AppendString((void *)(a4 + 168));
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        }
        std::wstring::append(lpPathName, L"\\");
        std::wstring::append(lpExistingFileName, L"\\");
        v56 = *(_OWORD *)std::wstring::operator std::wstring_view(lpPathName, v111, v55);
        v58 = *(_OWORD *)std::wstring::operator std::wstring_view(lpExistingFileName, v112, v57);
        v59 = std::operator+<wchar_t>(v126, lpExistingFileName, L"*");
        *(_OWORD *)v92 = v56;
        *(_OWORD *)v96 = v58;
        *(_OWORD *)v91 = *(_OWORD *)std::wstring::operator std::wstring_view(v59, v113, v60);
        LOBYTE(pbCancel) = a5;
        v61 = Microsoft::Diagnostics::Utils::FileSystem::CopyFiles(
                (int)v91,
                (int)v96,
                (int)v92,
                a4,
                pbCancel,
                a6,
                (__int64)&v89,
                dwCopyFlags,
                a9,
                (__int64)v95,
                v94,
                v93);
        std::wstring::_Tidy_deallocate(v126);
        if ( v61 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x456,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)(unsigned int)v61,
            pbCancela);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
          std::wstring::_Tidy_deallocate(lpPathName);
          std::wstring::_Tidy_deallocate(lpExistingFileName);
          return (unsigned int)v61;
        }
        if ( a5 )
        {
          v62 = (const WCHAR *)lpExistingFileName;
          if ( v121 > 7 )
            v62 = lpExistingFileName[0];
          SetFileAttributesW(v62, 0x10u);
          v63 = (const WCHAR *)lpExistingFileName;
          if ( v121 > 7 )
            v63 = lpExistingFileName[0];
          RemoveDirectoryW(v63);
        }
        goto LABEL_78;
      }
      if ( GetLastError() != 206 )
      {
        v53 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x446,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                v21);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
        std::wstring::_Tidy_deallocate(lpPathName);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        return v53;
      }
      if ( a4 )
      {
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
      }
    }
    else
    {
      v64 = lpExistingFileName;
      if ( v121 > 7 )
        v64 = (LPCWSTR *)lpExistingFileName[0];
      *(_OWORD *)v91 = *(_OWORD *)a2;
      v103[0] = v64;
      v103[1] = lpExistingFileName[2];
      if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v103, v91) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x475,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          (const char *)0x8007010BLL,
          pbCancel);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
        std::wstring::_Tidy_deallocate(lpPathName);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        return 2147942667LL;
      }
      v65 = lpPathName;
      if ( v123 > 7 )
        v65 = (LPCWSTR *)lpPathName[0];
      *(_OWORD *)v91 = *(_OWORD *)a3;
      v104[0] = v65;
      v104[1] = lpPathName[2];
      if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(v104, v91) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x476,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
          (const char *)0x8007010BLL,
          pbCancel);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
        std::wstring::_Tidy_deallocate(lpPathName);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        return 2147942667LL;
      }
      if ( v93 )
      {
        v106 = *(_OWORD *)std::wstring::operator std::wstring_view(lpExistingFileName, v114, v93);
        v105[0] = FindFileData.cFileName;
        v105[1] = std::_WChar_traits<wchar_t>::length(FindFileData.cFileName, v66, v67, v68);
        v70 = *(_QWORD *)(v69 + 56);
        if ( !v70 )
          std::_Xbad_function_call();
        v71 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *))(*(_QWORD *)v70 + 16LL))(v70, v105, &v106);
        if ( v71 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x47B,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
            (const char *)(unsigned int)v71,
            pbCancel);
      }
      if ( v94 )
      {
        v107 = *(_OWORD *)std::wstring::operator std::wstring_view(lpExistingFileName, v115, v94);
        if ( !(unsigned __int8)std::_Func_class<bool,std::wstring_view>::operator()(v72, &v107) )
        {
          if ( !a4 )
            goto LABEL_78;
          v73 = (void *)(a4 + 168);
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          v75 = &v116;
          goto LABEL_63;
        }
      }
      v76 = (const WCHAR *)lpPathName;
      if ( v123 > 7 )
        v76 = lpPathName[0];
      v77 = (const WCHAR *)lpExistingFileName;
      if ( v121 > 7 )
        v77 = lpExistingFileName[0];
      if ( CopyFileExW(v77, v76, 0, 0, v95, dwCopyFlags) )
      {
        if ( a4 )
        {
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          *(_OWORD *)v91 = *(_OWORD *)std::wstring::operator std::wstring_view(lpExistingFileName, v118, v80);
          Microsoft::Diagnostics::WideStringStream::AppendString((void *)(a4 + 168));
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          *(_OWORD *)v91 = *(_OWORD *)std::wstring::operator std::wstring_view(lpPathName, v119, 0xFFFF);
          Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(a4, v91);
        }
        if ( a9 )
        {
          v81 = (const WCHAR *)lpPathName;
          if ( v123 > 7 )
            v81 = lpPathName[0];
          SetFileAttributesW(v81, 0x80u);
        }
        if ( a5 )
        {
          v82 = (const WCHAR *)lpExistingFileName;
          if ( v121 > 7 )
            v82 = lpExistingFileName[0];
          SetFileAttributesW(v82, 0x80u);
          v83 = (const WCHAR *)lpExistingFileName;
          if ( v121 > 7 )
            v83 = lpExistingFileName[0];
          DeleteFileW(v83);
        }
        LODWORD(v89) = v89 + 1;
      }
      else
      {
        if ( GetLastError() != 32 )
        {
          v79 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x498,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                  v78);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
          std::wstring::_Tidy_deallocate(lpPathName);
          std::wstring::_Tidy_deallocate(lpExistingFileName);
          return v79;
        }
        if ( a4 )
        {
          v73 = (void *)(a4 + 168);
          Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          v75 = &v117;
LABEL_63:
          *(_OWORD *)v91 = *(_OWORD *)std::wstring::operator std::wstring_view(lpExistingFileName, v75, v74);
          Microsoft::Diagnostics::WideStringStream::AppendString(v73);
          Microsoft::Diagnostics::WideStringStream::operator<<(v73);
        }
      }
LABEL_78:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        if ( GetLastError() != 18 )
        {
          v85 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4D0,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
                  v84);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
          std::wstring::_Tidy_deallocate(lpPathName);
          std::wstring::_Tidy_deallocate(lpExistingFileName);
          return v85;
        }
        if ( a7 )
          *a7 = v89;
        goto LABEL_83;
      }
      if ( (unsigned int)v89 >= a6 )
      {
        if ( a7 )
          *a7 = v89;
LABEL_83:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v90);
        std::wstring::_Tidy_deallocate(lpPathName);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        return 0;
      }
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x417,
    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
    (const char *)(unsigned int)appended,
    pbCancel);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  std::wstring::_Tidy_deallocate(lpPathName);
  std::wstring::_Tidy_deallocate(lpExistingFileName);
  return v31;
}

```

## disassembly

```asm
0x1800f8674  mov     rax, rsp
0x1800f8677  push    rbx
0x1800f8678  push    rsi
0x1800f8679  push    rdi
0x1800f867a  push    r12
0x1800f867c  push    r13
0x1800f867e  push    r14
0x1800f8680  push    r15
0x1800f8682  sub     rsp, 530h
0x1800f8689  movaps  xmmword ptr [rax-48h], xmm6
0x1800f868d  movaps  xmmword ptr [rax-58h], xmm7
0x1800f8691  mov     rax, cs:__security_cookie
0x1800f8698  xor     rax, rsp
0x1800f869b  mov     [rsp+568h+var_68], rax
0x1800f86a3  mov     rsi, r9
0x1800f86a6  mov     r13, r8
0x1800f86a9  mov     r12, rdx
0x1800f86ac  mov     rbx, rcx
0x1800f86af  mov     r14, [rsp+568h+arg_30]
0x1800f86b7  mov     rax, [rsp+568h+arg_48]
0x1800f86bf  mov     [rsp+568h+var_4C8], rax
0x1800f86c7  mov     rax, [rsp+568h+arg_50]
0x1800f86cf  mov     [rsp+568h+var_4D0], rax
0x1800f86d7  mov     rax, [rsp+568h+arg_58]
0x1800f86df  mov     [rsp+568h+var_4D8], rax
0x1800f86e7  xor     edx, edx; Val
0x1800f86e9  mov     r8d, 250h; Size
0x1800f86ef  lea     rcx, [rsp+568h+FindFileData]; void *
0x1800f86f7  call    memset_0
0x1800f86fc  lea     rcx, [rsp+568h+lpExistingFileName]; void *
0x1800f8704  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800f8709  nop
0x1800f870a  lea     rcx, [rsp+568h+lpPathName]; void *
0x1800f8712  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800f8717  nop
0x1800f8718  test    r14, r14
0x1800f871b  jnz     short loc_1800F8721
0x1800f871d  xor     eax, eax
0x1800f871f  jmp     short loc_1800F8724
0x1800f8721  mov     eax, [r14]
0x1800f8724  mov     dword ptr [rsp+568h+var_508], eax
0x1800f8728  xorps   xmm0, xmm0
0x1800f872b  movups  xmmword ptr [rsp+568h+lpFileName], xmm0
0x1800f8733  xorps   xmm1, xmm1
0x1800f8736  movdqu  [rsp+568h+var_2E8], xmm1
0x1800f873f  mov     r8, [rbx+8]
0x1800f8743  mov     rdx, [rbx]
0x1800f8746  lea     rcx, [rsp+568h+lpFileName]
0x1800f874e  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800f8753  lea     rcx, [rsp+568h+lpFileName]
0x1800f875b  cmp     qword ptr [rsp+568h+var_2E8+8], 7
0x1800f8764  cmova   rcx, [rsp+568h+lpFileName]; lpFileName
0x1800f876d  lea     rdx, [rsp+568h+FindFileData]; lpFindFileData
0x1800f8775  call    cs:__imp_FindFirstFileW
0x1800f877b  mov     r15, rax
0x1800f877e  mov     [rsp+568h+var_500], rax
0x1800f8783  lea     rcx, [rsp+568h+lpFileName]
0x1800f878b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8790  lea     rax, [r15-1]
0x1800f8794  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f8798  ja      loc_1800F93B0
0x1800f879e  lea     rdi, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x1800f87a5  lea     rcx, asc_18039F850; "<>:\"/\\|?*"
0x1800f87ac  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f87b1  mov     r8, rax
0x1800f87b4  lea     rcx, [rsp+568h+FindFileData.cFileName]
0x1800f87bc  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f87c1  mov     rdx, rax
0x1800f87c4  mov     [rsp+568h+pbCancel], r8; int
0x1800f87c9  lea     r9, asc_18039F850; "<>:\"/\\|?*"
0x1800f87d0  lea     rcx, [rsp+568h+FindFileData.cFileName]
0x1800f87d8  call    ??$_Traits_find_first_of@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K101@Z; std::_Traits_find_first_of<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800f87dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f87e1  jnz     loc_1800F9368
0x1800f87e7  mov     r8, [r12+8]
0x1800f87ec  mov     rdx, [r12]
0x1800f87f0  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f87f8  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800f87fd  lea     rax, [rsp+568h+FindFileData.cFileName]
0x1800f8805  mov     [rsp+568h+var_4A8], rax
0x1800f880d  lea     rcx, [rsp+568h+FindFileData.cFileName]
0x1800f8815  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f881a  mov     [rsp+568h+var_4A0], rax
0x1800f8822  lea     rdx, [rsp+568h+var_4A8]
0x1800f882a  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8832  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1800f8837  mov     ebx, eax
0x1800f8839  test    eax, eax
0x1800f883b  jns     short loc_1800F888C
0x1800f883d  mov     rcx, [rsp+568h]; this
0x1800f8845  mov     r9d, eax; char *
0x1800f8848  mov     r8, rdi; unsigned int
0x1800f884b  mov     edx, 417h; void *
0x1800f8850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8855  nop
0x1800f8856  lea     rdx, [r15-1]
0x1800f885a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800f885e  ja      short loc_1800F886A
0x1800f8860  mov     rcx, r15; hFindFile
0x1800f8863  call    cs:__imp_FindClose
0x1800f8869  nop
0x1800f886a  lea     rcx, [rsp+568h+lpPathName]
0x1800f8872  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8877  nop
0x1800f8878  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8880  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8885  mov     eax, ebx
0x1800f8887  jmp     loc_1800F9402
0x1800f888c  mov     r8, [r13+8]
0x1800f8890  mov     rdx, [r13+0]
0x1800f8894  lea     rcx, [rsp+568h+lpPathName]
0x1800f889c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800f88a1  lea     rax, [rsp+568h+FindFileData.cFileName]
0x1800f88a9  mov     [rsp+568h+var_498], rax
0x1800f88b1  lea     rcx, [rsp+568h+FindFileData.cFileName]
0x1800f88b9  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f88be  mov     [rsp+568h+var_490], rax
0x1800f88c6  lea     rdx, [rsp+568h+var_498]
0x1800f88ce  lea     rcx, [rsp+568h+lpPathName]
0x1800f88d6  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1800f88db  mov     ebx, eax
0x1800f88dd  test    eax, eax
0x1800f88df  jns     short loc_1800F8927
0x1800f88e1  mov     rcx, [rsp+568h]; this
0x1800f88e9  mov     r9d, eax; char *
0x1800f88ec  mov     r8, rdi; unsigned int
0x1800f88ef  mov     edx, 41Ah; void *
0x1800f88f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f88f9  nop
0x1800f88fa  lea     rcx, [rsp+568h+var_500]
0x1800f88ff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800f8904  nop
0x1800f8905  lea     rcx, [rsp+568h+lpPathName]
0x1800f890d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8912  nop
0x1800f8913  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f891b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8920  mov     eax, ebx
0x1800f8922  jmp     loc_1800F9402
0x1800f8927  test    byte ptr [rsp+568h+FindFileData.dwFileAttributes], 10h
0x1800f892f  jz      loc_1800F8E20
0x1800f8935  lea     rbx, PathName; "."
0x1800f893c  mov     [rsp+568h+var_488], rbx
0x1800f8944  mov     rcx, rbx
0x1800f8947  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f894c  mov     [rsp+568h+var_480], rax
0x1800f8954  lea     rax, [rsp+568h+FindFileData.cFileName]
0x1800f895c  mov     [rsp+568h+var_478], rax
0x1800f8964  lea     rcx, [rsp+568h+FindFileData.cFileName]
0x1800f896c  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f8971  mov     [rsp+568h+var_470], rax
0x1800f8979  lea     rdx, [rsp+568h+var_488]
0x1800f8981  lea     rcx, [rsp+568h+var_478]
0x1800f8989  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800f898e  test    eax, eax
0x1800f8990  jz      loc_1800F9281
0x1800f8996  lea     rbx, asc_1803BE688; ".."
0x1800f899d  mov     [rsp+568h+var_468], rbx
0x1800f89a5  mov     rcx, rbx
0x1800f89a8  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f89ad  mov     [rsp+568h+var_460], rax
0x1800f89b5  lea     rax, [rsp+568h+FindFileData.cFileName]
0x1800f89bd  mov     [rsp+568h+var_458], rax
0x1800f89c5  lea     rcx, [rsp+568h+FindFileData.cFileName]
0x1800f89cd  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800f89d2  mov     [rsp+568h+var_450], rax
0x1800f89da  lea     rdx, [rsp+568h+var_468]
0x1800f89e2  lea     rcx, [rsp+568h+var_458]
0x1800f89ea  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800f89ef  test    eax, eax
0x1800f89f1  jz      loc_1800F9281
0x1800f89f7  movups  xmm0, xmmword ptr [r12]
0x1800f89fc  movdqu  xmmword ptr [rsp+568h+var_4B8], xmm0
0x1800f8a05  lea     rdx, [rsp+568h+var_3F8]
0x1800f8a0d  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8a15  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800f8a1a  movups  xmm0, xmmword ptr [rax]
0x1800f8a1d  movdqu  xmmword ptr [rsp+568h+var_4E8], xmm0
0x1800f8a26  lea     rdx, [rsp+568h+var_4B8]
0x1800f8a2e  lea     rcx, [rsp+568h+var_4E8]
0x1800f8a36  call    ?ValidatePathStartsWith@FileSystem@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(std::wstring_view,std::wstring_view)
0x1800f8a3b  test    al, al
0x1800f8a3d  jnz     short loc_1800F8A8A
0x1800f8a3f  mov     rcx, [rsp+568h]; this
0x1800f8a47  mov     ebx, 8007010Bh
0x1800f8a4c  mov     r9d, ebx; char *
0x1800f8a4f  mov     r8, rdi; unsigned int
0x1800f8a52  mov     edx, 42Fh; void *
0x1800f8a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8a5c  nop
0x1800f8a5d  lea     rcx, [rsp+568h+var_500]
0x1800f8a62  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800f8a67  nop
0x1800f8a68  lea     rcx, [rsp+568h+lpPathName]
0x1800f8a70  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8a75  nop
0x1800f8a76  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8a7e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8a83  mov     eax, ebx
0x1800f8a85  jmp     loc_1800F9402
0x1800f8a8a  movups  xmm0, xmmword ptr [r13+0]
0x1800f8a8f  movdqu  xmmword ptr [rsp+568h+var_4E8], xmm0
0x1800f8a98  lea     rdx, [rsp+568h+var_3E8]
0x1800f8aa0  lea     rcx, [rsp+568h+lpPathName]
0x1800f8aa8  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800f8aad  movups  xmm0, xmmword ptr [rax]
0x1800f8ab0  movdqu  xmmword ptr [rsp+568h+var_4B8], xmm0
0x1800f8ab9  lea     rdx, [rsp+568h+var_4E8]
0x1800f8ac1  lea     rcx, [rsp+568h+var_4B8]
0x1800f8ac9  call    ?ValidatePathStartsWith@FileSystem@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::FileSystem::ValidatePathStartsWith(std::wstring_view,std::wstring_view)
0x1800f8ace  test    al, al
0x1800f8ad0  jnz     short loc_1800F8B1D
0x1800f8ad2  mov     rcx, [rsp+568h]; this
0x1800f8ada  mov     ebx, 8007010Bh
0x1800f8adf  mov     r9d, ebx; char *
0x1800f8ae2  mov     r8, rdi; unsigned int
0x1800f8ae5  mov     edx, 430h; void *
0x1800f8aea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8aef  nop
0x1800f8af0  lea     rcx, [rsp+568h+var_500]
0x1800f8af5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800f8afa  nop
0x1800f8afb  lea     rcx, [rsp+568h+lpPathName]
0x1800f8b03  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8b08  nop
0x1800f8b09  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8b11  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8b16  mov     eax, ebx
0x1800f8b18  jmp     loc_1800F9402
0x1800f8b1d  lea     rcx, [rsp+568h+lpPathName]; Src
0x1800f8b25  call    ?PrependLongPathUnicodePrefix@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(std::wstring &)
0x1800f8b2a  lea     rcx, [rsp+568h+lpPathName]
0x1800f8b32  cmp     [rsp+568h+var_300], 7
0x1800f8b3b  cmova   rcx, [rsp+568h+lpPathName]; lpPathName
0x1800f8b44  xor     edx, edx; lpSecurityAttributes
0x1800f8b46  call    cs:__imp_CreateDirectoryW
0x1800f8b4c  test    eax, eax
0x1800f8b4e  jnz     loc_1800F8BFA
0x1800f8b54  call    cs:__imp_GetLastError
0x1800f8b5a  cmp     eax, 0CEh
0x1800f8b5f  jnz     short loc_1800F8BB6
0x1800f8b61  test    rsi, rsi
0x1800f8b64  jz      loc_1800F87A5
0x1800f8b6a  lea     rbx, [rsi+0A8h]
0x1800f8b71  lea     rdx, aPathExceededMa; "Path exceeded maximum length. Failed to"...
0x1800f8b78  mov     rcx, rbx; Src
0x1800f8b7b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800f8b80  lea     rdx, [rsp+568h+lpPathName]
0x1800f8b88  cmp     [rsp+568h+var_300], 7
0x1800f8b91  cmova   rdx, [rsp+568h+lpPathName]
0x1800f8b9a  mov     rcx, rbx; Src
0x1800f8b9d  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800f8ba2  lea     rdx, asc_1803A0C7C; "\r\n"
0x1800f8ba9  mov     rcx, rbx; Src
0x1800f8bac  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800f8bb1  jmp     loc_1800F87A5
0x1800f8bb6  mov     rcx, [rsp+568h]; this
0x1800f8bbe  mov     r8, rdi; unsigned int
0x1800f8bc1  mov     edx, 446h; void *
0x1800f8bc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f8bcb  mov     ebx, eax
0x1800f8bcd  lea     rcx, [rsp+568h+var_500]
0x1800f8bd2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800f8bd7  nop
0x1800f8bd8  lea     rcx, [rsp+568h+lpPathName]
0x1800f8be0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8be5  nop
0x1800f8be6  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8bee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f8bf3  mov     eax, ebx
0x1800f8bf5  jmp     loc_1800F9402
0x1800f8bfa  test    rsi, rsi
0x1800f8bfd  jz      short loc_1800F8C55
0x1800f8bff  lea     rbx, [rsi+0A8h]
0x1800f8c06  lea     rdx, aCreatedDirecto; "Created directory: "
0x1800f8c0d  mov     rcx, rbx; Src
0x1800f8c10  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800f8c15  lea     rdx, [rsp+568h+var_3D8]
0x1800f8c1d  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8c25  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800f8c2a  movups  xmm0, xmmword ptr [rax]
0x1800f8c2d  movdqu  xmmword ptr [rsp+568h+var_4E8], xmm0
0x1800f8c36  lea     rdx, [rsp+568h+var_4E8]
0x1800f8c3e  mov     rcx, rbx; Src
0x1800f8c41  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1800f8c46  lea     rdx, asc_1803A0C7C; "\r\n"
0x1800f8c4d  mov     rcx, rbx; Src
0x1800f8c50  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800f8c55  lea     rdx, asc_18039BCF0; "\\"
0x1800f8c5c  lea     rcx, [rsp+568h+lpPathName]
0x1800f8c64  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800f8c69  lea     rdx, asc_18039BCF0; "\\"
0x1800f8c70  lea     rcx, [rsp+568h+lpExistingFileName]
0x1800f8c78  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800f8c7d  lea     rdx, [rsp+568h+var_3C8]
0x1800f8c85  lea     rcx, [rsp+568h+lpPathName]
0x1800f8c8d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800f8c92  movups  xmm6, xmmword ptr [rax]
0x1800f8c95  lea     rdx, [rsp+568h+var_3B8]
0x1800f8c9d  lea     rcx, [rsp+568h+lpExistingFileName]
  ... truncated ...
```
