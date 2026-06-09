# _lambda_77cf094aea33988ccb229d7365e0e1b2_::operator()

- ea: `0x180037bb8`
- end: `0x18003842e`
- name: `_lambda_77cf094aea33988ccb229d7365e0e1b2_::operator()`
- size: `2166`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800406f0`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000aa5c`
- `0x18000aa7c`
- `0x18000e3bc`
- `0x180010a60`
- `0x180022ad8`
- `0x180025ee4`
- `0x180037bb8`
- `0x18003ebe8`
- `0x180050010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180038175`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180038175`
- `SHLWAPI!PathFindExtensionW` at `0x18003815c`
- `SHLWAPI!PathFindExtensionW` at `0x18003815c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037c59`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037cb6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037d6d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037e87`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037c59`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037cb6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037d6d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180037e87`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037d2b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037dd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037efb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037d2b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037dd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037efb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037ff5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180037ff5`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180037fb9`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180037fb9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038049`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038049`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180037c02`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180037e21`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180037c02`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180037e21`

## string_xrefs

- `0x180037c19`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037c70`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037ccd`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037d84`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037e38`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037e9e`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180037f27`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180038060`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800380bd`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800381e0`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003823e`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800382b2`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003833c`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x1800383a9`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 lambda_77cf094aea33988ccb229d7365e0e1b2_::operator()()
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // r15d
  HRESULT v6; // eax
  unsigned int v7; // ebx
  bool v8; // si
  HANDLE FileW; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  HANDLE v12; // rdi
  HRESULT v13; // eax
  unsigned int v14; // ebx
  HANDLE v15; // rax
  HRESULT v16; // eax
  unsigned int v17; // ebx
  HRESULT v18; // eax
  unsigned int v19; // ebx
  HANDLE v20; // rax
  const char *v21; // r9
  unsigned int LastError; // ebx
  bool v23; // r14
  char v24; // r12
  PWSTR v25; // rbx
  LONG v26; // eax
  HRESULT v27; // eax
  unsigned int v28; // edi
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // eax
  unsigned int v32; // edi
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  LPWSTR ExtensionW; // rax
  LPVOID v38; // rsi
  __int64 (__fastcall *v39)(LPVOID, _QWORD, WCHAR *, _QWORD); // rdi
  int v40; // eax
  unsigned int v41; // edi
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  int v46; // eax
  unsigned int v47; // edi
  __int64 v48; // rdx
  __int64 v49; // r8
  int v50; // eax
  unsigned int v51; // edi
  __int64 v52; // rdx
  __int64 v53; // r8
  const char *v54; // rdi
  __int64 v55; // rdx
  __int64 v56; // r8
  int dwCreationDisposition; // [rsp+20h] [rbp-4F8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-4F8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-4F8h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-4F8h]
  PWSTR *dwFlagsAndAttributes; // [rsp+28h] [rbp-4F0h]
  HANDLE hFile; // [rsp+40h] [rbp-4D8h] BYREF
  PWSTR v63; // [rsp+48h] [rbp-4D0h] BYREF
  PWSTR ppszPath; // [rsp+50h] [rbp-4C8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-4C0h] BYREF
  int v66; // [rsp+60h] [rbp-4B8h] BYREF
  int v67; // [rsp+64h] [rbp-4B4h] BYREF
  FILETIME FileTime1; // [rsp+68h] [rbp-4B0h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+70h] [rbp-4A8h] BYREF
  WCHAR FileName[264]; // [rsp+B0h] [rbp-468h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2C0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+0h]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v0 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A1,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v0,
      dwCreationDisposition);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return v1;
  }
  v3 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"Microsoft\\Windows\\RetailDemo\\Theme");
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A4,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v3,
      dwCreationDisposition);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return v4;
  }
  v5 = -1;
  hFile = (HANDLE)-1LL;
  v6 = PathCchCombine(FileName, 0x104u, pszPathOut, L"RDX.deskthemepack");
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8AB,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v6,
      dwCreationDisposition);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return v7;
  }
  v8 = 1;
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    FileW);
  v12 = hFile;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v13 = PathCchCombine(FileName, 0x104u, pszPathOut, L"RDX.theme");
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8AF,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v13,
        dwCreationDispositiona);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      return v14;
    }
    v15 = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      v15);
    v12 = hFile;
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v63 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v63,
        0);
      v16 = SHGetKnownFolderPath(&FOLDERID_ResourceDir, 0, 0, &v63);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B4,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v16,
          dwCreationDispositionb);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
        return v17;
      }
      v18 = PathCchCombine(FileName, 0x104u, v63, L"Themes\\aero.theme");
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B5,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v18,
          dwCreationDispositionb);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
        return v19;
      }
      v20 = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        v20);
      v12 = hFile;
      if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x8B8,
                      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retail"
                                    "demouseragent.cpp",
                      v21);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
        return LastError;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
    }
  }
  v23 = 1;
  v24 = 0;
  FileTime1 = 0;
  v25 = 0;
  v63 = 0;
  if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(v12, &FileInformation) )
    {
      v24 = 1;
      FileTime1 = FileInformation.ftLastWriteTime;
      v63 = (PWSTR)__PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow);
      v26 = CompareFileTime(&FileTime1, &RetailDemoUserAgent::s_lastWriteTime);
      v25 = v63;
      if ( !v26 )
        v23 = v63 != (PWSTR)RetailDemoUserAgent::s_lastFileSize.QuadPart;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      -1);
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v10, v11);
  v27 = CoCreateInstance(
          &GUID_9324da94_50ec_4a14_a770_e90ca03e7c8f,
          0,
          1u,
          &GUID_c1e8c83e_845d_4d95_81db_e283fdffc000,
          &ppv);
  v28 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D8,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v27,
      dwCreationDispositionc);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v29, v30);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return v28;
  }
  v31 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
  v32 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D9,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v31,
      dwCreationDispositionc);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v33, v34);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return v32;
  }
  v67 = 0;
  if ( (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 88LL))(ppv, &v67) >= 0 )
    v8 = v67 != RetailDemoUserAgent::s_lastAppliedThemeId;
  if ( !v23 && !v8 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v35, v36);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    return 0;
  }
  ExtensionW = PathFindExtensionW(FileName);
  if ( !ExtensionW || (unsigned int)_o__wcsicmp(ExtensionW, L".deskthemepack") )
  {
    v50 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, WCHAR *, __int64))(*(_QWORD *)ppv + 160LL))(ppv, 0, FileName, 64);
    v51 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8FA,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v50,
        0);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v52, v53);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      return v51;
    }
  }
  else
  {
    v63 = 0;
    v38 = ppv;
    v39 = *(__int64 (__fastcall **)(LPVOID, _QWORD, WCHAR *, _QWORD))(*(_QWORD *)ppv + 136LL);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v63,
      0);
    dwFlagsAndAttributes = &v63;
    v40 = v39(v38, 0, FileName, 0);
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F3,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v40,
        0);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v42, v43);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      return v41;
    }
    if ( !v63 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F4,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)0x80004003LL,
        0);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v44, v45);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      return 2147500035LL;
    }
    v46 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, PWSTR, __int64))(*(_QWORD *)ppv + 160LL))(ppv, 0, v63, 64);
    v47 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F5,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v46,
        0);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v48, v49);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
      return v47;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v63);
  }
  v66 = 0;
  v54 = (const char *)(*(unsigned int (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 88LL))(ppv, &v66);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x8FF,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
    v54,
    (int)"Failed to get current theme ID after successful theme application",
    (const char *)dwFlagsAndAttributes);
  if ( v24 )
  {
    RetailDemoUserAgent::s_lastWriteTime = FileTime1;
    RetailDemoUserAgent::s_lastFileSize.QuadPart = (LONGLONG)v25;
  }
  if ( (int)v54 >= 0 )
    v5 = v66;
  RetailDemoUserAgent::s_lastAppliedThemeId = v5;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v55, v56);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  return 0;
}

```

## disassembly

```asm
0x180037bb8  push    rbx
0x180037bba  push    rsi
0x180037bbb  push    rdi
0x180037bbc  push    r12
0x180037bbe  push    r13
0x180037bc0  push    r14
0x180037bc2  push    r15
0x180037bc4  sub     rsp, 4E0h
0x180037bcb  mov     rax, cs:__security_cookie
0x180037bd2  xor     rax, rsp
0x180037bd5  mov     [rsp+518h+var_48], rax
0x180037bdd  xor     r13d, r13d
0x180037be0  mov     [rsp+518h+ppszPath], r13
0x180037be5  xor     edx, edx
0x180037be7  lea     rcx, [rsp+518h+ppszPath]
0x180037bec  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180037bf1  lea     r9, [rsp+518h+ppszPath]; ppszPath
0x180037bf6  xor     r8d, r8d; hToken
0x180037bf9  xor     edx, edx; dwFlags
0x180037bfb  lea     rcx, FOLDERID_ProgramData; rfid
0x180037c02  call    cs:__imp_SHGetKnownFolderPath
0x180037c08  mov     ebx, eax
0x180037c0a  test    eax, eax
0x180037c0c  jns     short loc_180037C3C
0x180037c0e  mov     rcx, [rsp+518h]; this
0x180037c16  mov     r9d, eax; char *
0x180037c19  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037c20  mov     edx, 8A1h; void *
0x180037c25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c2a  nop
0x180037c2b  lea     rcx, [rsp+518h+ppszPath]
0x180037c30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037c35  mov     eax, ebx
0x180037c37  jmp     loc_18003840A
0x180037c3c  lea     r9, aMicrosoftWindo_0; "Microsoft\\Windows\\RetailDemo\\Theme"
0x180037c43  mov     r8, [rsp+518h+ppszPath]; pszPathIn
0x180037c48  mov     r14d, 104h
0x180037c4e  mov     edx, r14d; cchPathOut
0x180037c51  lea     rcx, [rsp+518h+pszPathOut]; pszPathOut
0x180037c59  call    cs:__imp_PathCchCombine
0x180037c5f  mov     ebx, eax
0x180037c61  test    eax, eax
0x180037c63  jns     short loc_180037C93
0x180037c65  mov     rcx, [rsp+518h]; this
0x180037c6d  mov     r9d, eax; char *
0x180037c70  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037c77  mov     edx, 8A4h; void *
0x180037c7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c81  nop
0x180037c82  lea     rcx, [rsp+518h+ppszPath]
0x180037c87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037c8c  mov     eax, ebx
0x180037c8e  jmp     loc_18003840A
0x180037c93  or      r15, 0FFFFFFFFFFFFFFFFh
0x180037c97  mov     [rsp+518h+hFile], r15
0x180037c9c  lea     r9, aRdxDeskthemepa; "RDX.deskthemepack"
0x180037ca3  lea     r8, [rsp+518h+pszPathOut]; pszPathIn
0x180037cab  mov     rdx, r14; cchPathOut
0x180037cae  lea     rcx, [rsp+518h+FileName]; pszPathOut
0x180037cb6  call    cs:__imp_PathCchCombine
0x180037cbc  mov     ebx, eax
0x180037cbe  test    eax, eax
0x180037cc0  jns     short loc_180037CFB
0x180037cc2  mov     rcx, [rsp+518h]; this
0x180037cca  mov     r9d, eax; char *
0x180037ccd  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037cd4  mov     edx, 8ABh; void *
0x180037cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037cde  nop
0x180037cdf  lea     rcx, [rsp+518h+hFile]
0x180037ce4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180037ce9  nop
0x180037cea  lea     rcx, [rsp+518h+ppszPath]
0x180037cef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037cf4  mov     eax, ebx
0x180037cf6  jmp     loc_18003840A
0x180037cfb  mov     [rsp+518h+hTemplateFile], r13; hTemplateFile
0x180037d00  mov     r12d, 80h
0x180037d06  mov     [rsp+518h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180037d0b  mov     [rsp+518h+dwCreationDisposition], 3; int
0x180037d13  xor     r9d, r9d; lpSecurityAttributes
0x180037d16  lea     esi, [r12-7Fh]
0x180037d1b  mov     r8d, esi; dwShareMode
0x180037d1e  mov     edx, 80000000h; dwDesiredAccess
0x180037d23  lea     rcx, [rsp+518h+FileName]; lpFileName
0x180037d2b  call    cs:__imp_CreateFileW
0x180037d31  mov     rdx, rax
0x180037d34  lea     rcx, [rsp+518h+hFile]
0x180037d39  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180037d3e  mov     rdi, [rsp+518h+hFile]
0x180037d43  lea     rax, [rdi+1]
0x180037d47  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037d4d  jnz     loc_180037F6B
0x180037d53  lea     r9, aRdxTheme; "RDX.theme"
0x180037d5a  lea     r8, [rsp+518h+pszPathOut]; pszPathIn
0x180037d62  mov     rdx, r14; cchPathOut
0x180037d65  lea     rcx, [rsp+518h+FileName]; pszPathOut
0x180037d6d  call    cs:__imp_PathCchCombine
0x180037d73  mov     ebx, eax
0x180037d75  test    eax, eax
0x180037d77  jns     short loc_180037DB2
0x180037d79  mov     rcx, [rsp+518h]; this
0x180037d81  mov     r9d, eax; char *
0x180037d84  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037d8b  mov     edx, 8AFh; void *
0x180037d90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037d95  nop
0x180037d96  lea     rcx, [rsp+518h+hFile]
0x180037d9b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180037da0  nop
0x180037da1  lea     rcx, [rsp+518h+ppszPath]
0x180037da6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037dab  mov     eax, ebx
0x180037dad  jmp     loc_18003840A
0x180037db2  mov     [rsp+518h+hTemplateFile], r13; hTemplateFile
0x180037db7  mov     [rsp+518h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180037dbc  mov     [rsp+518h+dwCreationDisposition], 3; int
0x180037dc4  xor     r9d, r9d; lpSecurityAttributes
0x180037dc7  mov     r8d, esi; dwShareMode
0x180037dca  mov     edx, 80000000h; dwDesiredAccess
0x180037dcf  lea     rcx, [rsp+518h+FileName]; lpFileName
0x180037dd7  call    cs:__imp_CreateFileW
0x180037ddd  mov     rdx, rax
0x180037de0  lea     rcx, [rsp+518h+hFile]
0x180037de5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180037dea  mov     rdi, [rsp+518h+hFile]
0x180037def  lea     rax, [rdi+1]
0x180037df3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037df9  jnz     loc_180037F6B
0x180037dff  mov     [rsp+518h+var_4D0], r13
0x180037e04  xor     edx, edx
0x180037e06  lea     rcx, [rsp+518h+var_4D0]
0x180037e0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180037e10  lea     r9, [rsp+518h+var_4D0]; ppszPath
0x180037e15  xor     r8d, r8d; hToken
0x180037e18  xor     edx, edx; dwFlags
0x180037e1a  lea     rcx, FOLDERID_ResourceDir; rfid
0x180037e21  call    cs:__imp_SHGetKnownFolderPath
0x180037e27  mov     ebx, eax
0x180037e29  test    eax, eax
0x180037e2b  jns     short loc_180037E70
0x180037e2d  mov     rcx, [rsp+518h]; this
0x180037e35  mov     r9d, eax; char *
0x180037e38  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037e3f  mov     edx, 8B4h; void *
0x180037e44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e49  lea     rcx, [rsp+518h+var_4D0]
0x180037e4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037e53  nop
0x180037e54  lea     rcx, [rsp+518h+hFile]
0x180037e59  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180037e5e  nop
0x180037e5f  lea     rcx, [rsp+518h+ppszPath]
0x180037e64  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037e69  mov     eax, ebx
0x180037e6b  jmp     loc_18003840A
0x180037e70  lea     r9, aThemesAeroThem; "Themes\\aero.theme"
0x180037e77  mov     r8, [rsp+518h+var_4D0]; pszPathIn
0x180037e7c  mov     rdx, r14; cchPathOut
0x180037e7f  lea     rcx, [rsp+518h+FileName]; pszPathOut
0x180037e87  call    cs:__imp_PathCchCombine
0x180037e8d  mov     ebx, eax
0x180037e8f  test    eax, eax
0x180037e91  jns     short loc_180037ED6
0x180037e93  mov     rcx, [rsp+518h]; this
0x180037e9b  mov     r9d, eax; char *
0x180037e9e  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037ea5  mov     edx, 8B5h; void *
0x180037eaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037eaf  lea     rcx, [rsp+518h+var_4D0]
0x180037eb4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037eb9  nop
0x180037eba  lea     rcx, [rsp+518h+hFile]
0x180037ebf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180037ec4  nop
0x180037ec5  lea     rcx, [rsp+518h+ppszPath]
0x180037eca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037ecf  mov     eax, ebx
0x180037ed1  jmp     loc_18003840A
0x180037ed6  mov     [rsp+518h+hTemplateFile], r13; hTemplateFile
0x180037edb  mov     [rsp+518h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180037ee0  mov     [rsp+518h+dwCreationDisposition], 3; dwCreationDisposition
0x180037ee8  xor     r9d, r9d; lpSecurityAttributes
0x180037eeb  mov     r8d, esi; dwShareMode
0x180037eee  mov     edx, 80000000h; dwDesiredAccess
0x180037ef3  lea     rcx, [rsp+518h+FileName]; lpFileName
0x180037efb  call    cs:__imp_CreateFileW
0x180037f01  mov     rdx, rax
0x180037f04  lea     rcx, [rsp+518h+hFile]
0x180037f09  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180037f0e  mov     rdi, [rsp+518h+hFile]
0x180037f13  lea     rax, [rdi+1]
0x180037f17  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037f1d  jnz     short loc_180037F61
0x180037f1f  mov     rcx, [rsp+518h]; this
0x180037f27  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180037f2e  mov     edx, 8B8h; void *
0x180037f33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037f38  mov     ebx, eax
0x180037f3a  lea     rcx, [rsp+518h+var_4D0]
0x180037f3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037f44  nop
0x180037f45  lea     rcx, [rsp+518h+hFile]
0x180037f4a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180037f4f  nop
0x180037f50  lea     rcx, [rsp+518h+ppszPath]
0x180037f55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037f5a  mov     eax, ebx
0x180037f5c  jmp     loc_18003840A
0x180037f61  lea     rcx, [rsp+518h+var_4D0]
0x180037f66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037f6b  mov     rax, rdi
0x180037f6e  mov     r14b, sil
0x180037f71  mov     r12b, r13b
0x180037f74  mov     qword ptr [rsp+518h+FileTime1.dwLowDateTime], r13
0x180037f79  mov     rbx, r13
0x180037f7c  mov     [rsp+518h+var_4D0], rbx
0x180037f81  inc     rax
0x180037f84  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037f8a  jz      loc_18003801D
0x180037f90  xorps   xmm0, xmm0
0x180037f93  xor     eax, eax
0x180037f95  movups  xmmword ptr [rsp+518h+FileInformation.dwFileAttributes], xmm0
0x180037f9a  movups  xmmword ptr [rsp+518h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180037fa2  movups  xmmword ptr [rsp+518h+FileInformation.nFileSizeHigh], xmm0
0x180037faa  mov     [rsp+518h+FileInformation.nFileIndexLow], eax
0x180037fb1  lea     rdx, [rsp+518h+FileInformation]; lpFileInformation
0x180037fb6  mov     rcx, rdi; hFile
0x180037fb9  call    cs:__imp_GetFileInformationByHandle
0x180037fbf  test    eax, eax
0x180037fc1  jz      short loc_180038010
0x180037fc3  mov     r12b, sil
0x180037fc6  mov     rax, qword ptr [rsp+518h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x180037fce  mov     qword ptr [rsp+518h+FileTime1.dwLowDateTime], rax
0x180037fd3  mov     eax, [rsp+518h+FileInformation.nFileSizeLow]
0x180037fda  mov     dword ptr [rsp+518h+var_4D0], eax
0x180037fde  mov     eax, [rsp+518h+FileInformation.nFileSizeHigh]
0x180037fe5  mov     dword ptr [rsp+518h+var_4D0+4], eax
0x180037fe9  lea     rdx, ?s_lastWriteTime@RetailDemoUserAgent@@0U_FILETIME@@A; lpFileTime2
0x180037ff0  lea     rcx, [rsp+518h+FileTime1]; lpFileTime1
0x180037ff5  call    cs:__imp_CompareFileTime
0x180037ffb  mov     rbx, [rsp+518h+var_4D0]
0x180038000  test    eax, eax
0x180038002  jnz     short loc_180038010
0x180038004  cmp     rbx, cs:?s_lastFileSize@RetailDemoUserAgent@@0T_LARGE_INTEGER@@A; _LARGE_INTEGER RetailDemoUserAgent::s_lastFileSize
0x18003800b  jnz     short loc_180038010
0x18003800d  mov     r14b, r13b
0x180038010  mov     rdx, r15
0x180038013  lea     rcx, [rsp+518h+hFile]
0x180038018  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003801d  mov     [rsp+518h+ppv], r13
0x180038022  lea     rcx, [rsp+518h+ppv]
0x180038027  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003802c  lea     rax, [rsp+518h+ppv]
0x180038031  mov     qword ptr [rsp+518h+dwCreationDisposition], rax; int
0x180038036  lea     r9, _GUID_c1e8c83e_845d_4d95_81db_e283fdffc000; riid
0x18003803d  mov     r8d, esi; dwClsContext
0x180038040  xor     edx, edx; pUnkOuter
0x180038042  lea     rcx, _GUID_9324da94_50ec_4a14_a770_e90ca03e7c8f; rclsid
0x180038049  call    cs:__imp_CoCreateInstance
0x18003804f  mov     edi, eax
0x180038051  test    eax, eax
0x180038053  jns     short loc_180038099
0x180038055  mov     rcx, [rsp+518h]; this
0x18003805d  mov     r9d, eax; char *
0x180038060  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180038067  mov     edx, 8D8h; void *
0x18003806c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038071  nop
0x180038072  lea     rcx, [rsp+518h+ppv]
0x180038077  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003807c  nop
0x18003807d  lea     rcx, [rsp+518h+hFile]
0x180038082  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180038087  nop
0x180038088  lea     rcx, [rsp+518h+ppszPath]
0x18003808d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180038092  mov     eax, edi
0x180038094  jmp     loc_18003840A
0x180038099  mov     rcx, [rsp+518h+ppv]
0x18003809e  mov     rax, [rcx]
0x1800380a1  xor     edx, edx
0x1800380a3  mov     rax, [rax+18h]
0x1800380a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380ac  mov     edi, eax
0x1800380ae  test    eax, eax
0x1800380b0  jns     short loc_1800380F6
0x1800380b2  mov     rcx, [rsp+518h]; this
0x1800380ba  mov     r9d, eax; char *
0x1800380bd  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800380c4  mov     edx, 8D9h; void *
0x1800380c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800380ce  nop
0x1800380cf  lea     rcx, [rsp+518h+ppv]
0x1800380d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800380d9  nop
0x1800380da  lea     rcx, [rsp+518h+hFile]
0x1800380df  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800380e4  nop
0x1800380e5  lea     rcx, [rsp+518h+ppszPath]
  ... truncated ...
```
