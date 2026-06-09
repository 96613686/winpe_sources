# RecursiveUtil::RecursiveScanDirectory(ushort const *,RecursiveUtil::NtObjectPath const &,ulong,int,_FILETIME *,__int64 *,__int64 *)

- ea: `0x18003b474`
- end: `0x18003be7c`
- name: `?RecursiveScanDirectory@RecursiveUtil@@YAJPEBGAEBVNtObjectPath@1@KHPEAU_FILETIME@@PEA_J3@Z`
- size: `2568`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const struct RecursiveUtil::NtObjectPath *, int, FILETIME *, struct _FILETIME *, __int64 *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b1b4`
- `0x18003b474`

## callees

- `0x18000d030`
- `0x180012714`
- `0x180012734`
- `0x180019cd4`
- `0x180019cec`
- `0x180019d04`
- `0x180019d4c`
- `0x180019d70`
- `0x18001c208`
- `0x18001dcf4`
- `0x18002e740`
- `0x18003a8f8`
- `0x18003a964`
- `0x18003a9a4`
- `0x18003a9c4`
- `0x18003af94`
- `0x18003b474`
- `0x18003bf34`
- `0x18003c058`
- `0x18003c10c`
- `0x18003c168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcf7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b528`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b528`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b69e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b746`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ba33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003baef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bbe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bc86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bda2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bde3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b69e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b746`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ba33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003baef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bbe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bc86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bda2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bde3`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x18003b9bb`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x18003b9bb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003bce7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003bce7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003b5cb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003b7e4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003b5cb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003b7e4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003bb4d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003bb63`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003bb4d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003bb63`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003bd83`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003bd83`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003b556`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003b556`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003b706`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003b891`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003b706`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18003b891`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18003b5bd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18003b5bd`

## string_xrefs

- `0x18003b56d`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003b721`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003b795`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003b8a8`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003b938`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003b9fb`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003bab7`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003bbb0`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003bd0a`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`
- `0x18003be20`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`

## pseudocode

```c
__int64 __fastcall RecursiveUtil::RecursiveScanDirectory(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const struct RecursiveUtil::NtObjectPath *a3,
        int a4,
        FILETIME *a5,
        struct _FILETIME *a6,
        __int64 *a7)
{
  char v7; // r14
  struct _WIN32_FIND_DATAW *v9; // rdi
  HRESULT v10; // eax
  unsigned int v11; // esi
  __int64 v12; // rdx
  DWORD dwFileAttributes; // r13d
  bool v14; // r14
  int v15; // r13d
  unsigned int *CanRecurseIntoDirectory; // rsi
  const WCHAR *v17; // rdx
  HRESULT v18; // eax
  signed int LastError; // eax
  HANDLE FirstFileW; // rax
  FILETIME *v21; // rsi
  BOOL NextFileW; // eax
  __int64 v23; // rcx
  HRESULT v24; // eax
  unsigned int v25; // esi
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  bool v30; // si
  int v31; // eax
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-148h]
  __int64 *v35; // [rsp+38h] [rbp-130h]
  char FileInformation[8]; // [rsp+40h] [rbp-128h] BYREF
  PCWSTR pszPathIn; // [rsp+48h] [rbp-120h] BYREF
  PWSTR ppszPathOut; // [rsp+50h] [rbp-118h] BYREF
  HANDLE hFindFile; // [rsp+58h] [rbp-110h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-108h]
  bool v41; // [rsp+68h] [rbp-100h]
  unsigned int v42[3]; // [rsp+6Ch] [rbp-FCh] BYREF
  FILETIME *v43; // [rsp+78h] [rbp-F0h] BYREF
  int v44; // [rsp+80h] [rbp-E8h]
  int v45; // [rsp+88h] [rbp-E0h]
  FILETIME *lpFileTime1; // [rsp+90h] [rbp-D8h]
  const unsigned __int16 *v47; // [rsp+98h] [rbp-D0h]
  FILETIME FileTime1; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 *v49; // [rsp+A8h] [rbp-C0h]
  struct _FILETIME *v50; // [rsp+B0h] [rbp-B8h]
  FILETIME *v51; // [rsp+B8h] [rbp-B0h]
  struct _FILETIME *v52; // [rsp+C0h] [rbp-A8h]
  __int64 *v53; // [rsp+C8h] [rbp-A0h]
  const unsigned __int16 *v54; // [rsp+D0h] [rbp-98h]
  unsigned __int16 v55[16]; // [rsp+E0h] [rbp-88h] BYREF
  _BYTE v56[32]; // [rsp+100h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v7 = (char)a3;
  v42[0] = (unsigned int)a3;
  v47 = a2;
  v51 = a5;
  v52 = a6;
  v53 = a7;
  v54 = a2;
  v44 = (int)a3;
  lpFileTime1 = a5;
  v50 = a6;
  v49 = a7;
  *(_QWORD *)&v42[1] = -1;
  pszPathIn = 0;
  ppszPathOut = 0;
  v9 = (struct _WIN32_FIND_DATAW *)LocalAlloc(0x40u, 0x250u);
  hMem = v9;
  if ( v9 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v10 = PathAllocCanonicalize(this, 0x10u, &ppszPathOut);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
        (const char *)(unsigned int)v10,
        v34);
      hMem = 0;
      LocalFree(v9);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
LABEL_72:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42[1]);
      return v11;
    }
    v12 = -1;
    do
      ++v12;
    while ( ppszPathOut[v12] );
    PathCchRemoveBackslash(ppszPathOut, v12 + 1);
    hFindFile = FindFirstFileW(ppszPathOut, v9);
    if ( (char *)hFindFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
      hMem = 0;
      LocalFree(v9);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
      goto LABEL_71;
    }
    dwFileAttributes = v9->dwFileAttributes;
    v14 = (v7 & 4) != 0;
    FileInformation[0] = v14;
    v15 = dwFileAttributes & 0x10;
    if ( v15 )
    {
      CanRecurseIntoDirectory = (unsigned int *)wil::TryCreateFileCanRecurseIntoDirectory(&v43, this, v9);
      if ( &v42[1] != CanRecurseIntoDirectory )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v42[1],
          *(_QWORD *)CanRecurseIntoDirectory);
        *(_QWORD *)CanRecurseIntoDirectory = -1;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v43);
      if ( (unsigned __int64)(*(_QWORD *)&v42[1] - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( v14 )
        {
          v11 = 0;
        }
        else
        {
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError > 0 )
            v11 = (unsigned __int16)LastError | 0x80070000;
          if ( (v11 & 0x80000000) != 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x162,
              (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
              (const char *)v11,
              v34);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
        hMem = 0;
        LocalFree(v9);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
        goto LABEL_72;
      }
      RecursiveUtil::NtObjectPath::NtObjectPath((RecursiveUtil::NtObjectPath *)v56, *(void **)&v42[1]);
      if ( !(unsigned __int8)RecursiveUtil::operator==(v56, v47) )
      {
        std::wstring::_Tidy_deallocate(v56);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
        hMem = 0;
        LocalFree(v9);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
LABEL_71:
        v11 = 0;
        goto LABEL_72;
      }
      std::wstring::_Tidy_deallocate(v56);
    }
    v45 = v15;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPathIn,
      0);
    v17 = L"*";
    if ( !v15 )
      v17 = &word_180092AF0;
    v18 = PathAllocCombine(ppszPathOut, v17, 0x10u, (PWSTR *)&pszPathIn);
    v11 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
        (const char *)(unsigned int)v18,
        v34);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
      hMem = 0;
      LocalFree(v9);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
      goto LABEL_72;
    }
    FirstFileW = FindFirstFileW(pszPathIn, v9);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::reset(
      &hFindFile,
      FirstFileW);
    if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v21 = lpFileTime1;
      v43 = lpFileTime1;
      NextFileW = 1;
      while ( NextFileW )
      {
        if ( v9->cFileName[0] != 46 || v9->cFileName[1] && (v9->cFileName[1] != 46 || v9->cFileName[2]) )
        {
          std::wstring::wstring(v55, v47);
          if ( v15 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &pszPathIn,
              0);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &pszPathIn,
              0);
            v24 = PathAllocCombine(ppszPathOut, v9->cFileName, 0x10u, (PWSTR *)&pszPathIn);
            v25 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x186,
                (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
                (const char *)(unsigned int)v24,
                v34);
              SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v55);
              wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>(&hFindFile);
              hMem = 0;
              LocalFree(v9);
LABEL_56:
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPathIn);
              wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(&v42[1]);
              return v25;
            }
            v26 = RecursiveUtil::NtObjectPath::append((RecursiveUtil::NtObjectPath *)v55, v9->cFileName);
            v25 = v26;
            if ( v26 < 0 )
            {
              if ( v14 )
                v25 = 0;
              else
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x18B,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
                  (const char *)(unsigned int)v26,
                  v34);
              SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v55);
              wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>(&hFindFile);
              hMem = 0;
              LocalFree(v9);
              goto LABEL_56;
            }
            v21 = v43;
          }
          if ( (v9->dwFileAttributes & 0x10) != 0 )
          {
            if ( (v9->dwFileAttributes & 0x400) == 0
              || (unsigned __int8)RtlIsNonEmptyDirectoryReparsePointAllowed(v9->dwReserved0) )
            {
              v29 = RecursiveUtil::RecursiveScanDirectory(
                      (RecursiveUtil *)pszPathIn,
                      v55,
                      (const struct RecursiveUtil::NtObjectPath *)v42[0],
                      0,
                      (__int64)lpFileTime1,
                      v50,
                      v49,
                      v35);
              v25 = v29;
              if ( v29 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x19C,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
                  (const char *)(unsigned int)v29,
                  v34);
                SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v55);
                wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>(&hFindFile);
                hMem = 0;
                LocalFree(v9);
                goto LABEL_56;
              }
            }
            else
            {
              v28 = RecursiveUtil::DeleteCallback(v27, pszPathIn, (__int64)v55, v9, v42[0]);
              v25 = v28;
              if ( v28 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x197,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
                  (const char *)(unsigned int)v28,
                  v34);
                SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v55);
                wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>(&hFindFile);
                hMem = 0;
                LocalFree(v9);
                goto LABEL_56;
              }
            }
          }
          else
          {
            v30 = v21 == 0;
            v41 = v30;
            if ( v51 )
            {
              FileTime1.dwLowDateTime = 0;
              FileTime1.dwHighDateTime = 0;
              if ( CompareFileTime(&FileTime1, &v9->ftLastWriteTime) )
              {
                if ( CompareFileTime(lpFileTime1, &v9->ftLastWriteTime) == 1 )
                  v30 = 1;
                v41 = v30;
              }
            }
            if ( v30 )
            {
              v31 = RecursiveUtil::DeleteCallback(v23, pszPathIn, (__int64)v55, v9, v42[0]);
              v25 = v31;
              if ( v31 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1B5,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
                  (const char *)(unsigned int)v31,
                  v34);
                SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v55);
                wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>(&hFindFile);
                hMem = 0;
                LocalFree(v9);
                goto LABEL_56;
              }
              if ( v53 )
                *v49 += v9->nFileSizeLow | ((unsigned __int64)v9->nFileSizeHigh << 32);
            }
            if ( v52 )
              *(_QWORD *)v50 += v9->nFileSizeLow | ((unsigned __int64)v9->nFileSizeHigh << 32);
          }
          SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v55);
        }
        NextFileW = FindNextFileW(hFindFile, v9);
        v21 = v43;
      }
      if ( GetLastError() != 18 )
      {
        v11 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1D5,
                (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
                v33);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
        hMem = 0;
        LocalFree(v9);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
        goto LABEL_72;
      }
    }
    if ( v15 && (!a4 || (v42[0] & 2) == 0) )
    {
      FileInformation[0] = 1;
      SetFileInformationByHandle(*(HANDLE *)&v42[1], FileDispositionInfo, FileInformation, 1u);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&hFindFile);
    hMem = 0;
    LocalFree(v9);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42[1]);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
      (const char *)0x8007000ELL,
      v34);
    hMem = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42[1]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18003b474  mov     [rsp+arg_18], r9d
0x18003b479  push    rbx
0x18003b47a  push    rsi
0x18003b47b  push    rdi
0x18003b47c  push    r12
0x18003b47e  push    r13
0x18003b480  push    r14
0x18003b482  push    r15
0x18003b484  sub     rsp, 130h
0x18003b48b  mov     rax, cs:__security_cookie
0x18003b492  xor     rax, rsp
0x18003b495  mov     [rsp+168h+var_48], rax
0x18003b49d  mov     r14d, r8d
0x18003b4a0  mov     dword ptr [rsp+168h+var_FC], r8d
0x18003b4a5  mov     rax, rdx
0x18003b4a8  mov     [rsp+168h+var_D0], rdx
0x18003b4b0  mov     r15, rcx
0x18003b4b3  mov     r8, [rsp+168h+arg_20]
0x18003b4bb  mov     [rsp+168h+var_B0], r8
0x18003b4c3  mov     rcx, [rsp+168h+arg_28]
0x18003b4cb  mov     [rsp+168h+var_A8], rcx
0x18003b4d3  mov     rdx, [rsp+168h+arg_30]
0x18003b4db  mov     [rsp+168h+var_A0], rdx
0x18003b4e3  mov     [rsp+168h+var_98], rax
0x18003b4eb  mov     [rsp+168h+var_E8], r14d
0x18003b4f3  mov     [rsp+168h+lpFileTime1], r8
0x18003b4fb  mov     [rsp+168h+var_B8], rcx
0x18003b503  mov     [rsp+168h+var_C0], rdx
0x18003b50b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003b50f  mov     qword ptr [rsp+168h+var_FC+4], r12
0x18003b514  xor     ebx, ebx
0x18003b516  mov     [rsp+168h+pszPathIn], rbx
0x18003b51b  mov     [rsp+168h+ppszPathOut], rbx
0x18003b520  mov     edx, 250h; uBytes
0x18003b525  lea     ecx, [rbx+40h]; uFlags
0x18003b528  call    cs:__imp_LocalAlloc
0x18003b52e  mov     rdi, rax
0x18003b531  mov     [rsp+168h+hMem], rax
0x18003b536  test    rax, rax
0x18003b539  jz      loc_18003BE10
0x18003b53f  xor     edx, edx
0x18003b541  lea     rcx, [rsp+168h+ppszPathOut]
0x18003b546  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003b54b  lea     r8, [rsp+168h+ppszPathOut]; ppszPathOut
0x18003b550  lea     edx, [rbx+10h]; dwFlags
0x18003b553  mov     rcx, r15; pszPathIn
0x18003b556  call    cs:__imp_PathAllocCanonicalize
0x18003b55c  mov     esi, eax
0x18003b55e  test    eax, eax
0x18003b560  jns     short loc_18003B5A9
0x18003b562  mov     rcx, [rsp+168h]; this
0x18003b56a  mov     r9d, eax; char *
0x18003b56d  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b574  mov     edx, 14Ch; void *
0x18003b579  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b57e  nop
0x18003b57f  mov     [rsp+168h+hMem], rbx
0x18003b584  mov     rcx, rdi; hMem
0x18003b587  call    cs:__imp_LocalFree
0x18003b58d  nop
0x18003b58e  lea     rcx, [rsp+168h+ppszPathOut]
0x18003b593  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b598  nop
0x18003b599  lea     rcx, [rsp+168h+pszPathIn]
0x18003b59e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b5a3  nop
0x18003b5a4  jmp     loc_18003BE02
0x18003b5a9  mov     rcx, [rsp+168h+ppszPathOut]; pszPath
0x18003b5ae  mov     rdx, r12
0x18003b5b1  inc     rdx
0x18003b5b4  cmp     [rcx+rdx*2], bx
0x18003b5b8  jnz     short loc_18003B5B1
0x18003b5ba  inc     rdx; cchPath
0x18003b5bd  call    cs:__imp_PathCchRemoveBackslash
0x18003b5c3  mov     rdx, rdi; lpFindFileData
0x18003b5c6  mov     rcx, [rsp+168h+ppszPathOut]; lpFileName
0x18003b5cb  call    cs:__imp_FindFirstFileW
0x18003b5d1  mov     [rsp+168h+hFindFile], rax
0x18003b5d6  mov     rax, [rsp+168h+hFindFile]
0x18003b5db  dec     rax
0x18003b5de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b5e2  ja      loc_18003BDD0
0x18003b5e8  mov     r13d, [rdi]
0x18003b5eb  shr     r14b, 2
0x18003b5ef  mov     r12d, 1
0x18003b5f5  and     r14b, r12b
0x18003b5f8  mov     [rsp+168h+FileInformation], r14b
0x18003b5fd  and     r13d, 10h
0x18003b601  jz      loc_18003B6CD
0x18003b607  mov     r8, rdi
0x18003b60a  mov     rdx, r15
0x18003b60d  lea     rcx, [rsp+168h+var_F0]
0x18003b612  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x18003b617  mov     rsi, rax
0x18003b61a  lea     rax, [rsp+168h+var_FC+4]
0x18003b61f  cmp     rax, rsi
0x18003b622  jz      short loc_18003B638
0x18003b624  mov     rdx, [rsi]
0x18003b627  lea     rcx, [rsp+168h+var_FC+4]
0x18003b62c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003b631  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18003b638  lea     rcx, [rsp+168h+var_F0]
0x18003b63d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003b642  mov     rdx, qword ptr [rsp+168h+var_FC+4]; void *
0x18003b647  lea     rax, [rdx-1]
0x18003b64b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b64f  ja      loc_18003B768
0x18003b655  lea     rcx, [rsp+168h+var_68]; this
0x18003b65d  call    ??0NtObjectPath@RecursiveUtil@@QEAA@PEAX@Z; RecursiveUtil::NtObjectPath::NtObjectPath(void *)
0x18003b662  nop
0x18003b663  mov     rdx, [rsp+168h+var_D0]
0x18003b66b  lea     rcx, [rsp+168h+var_68]
0x18003b673  call    ??8RecursiveUtil@@YA_NAEBVNtObjectPath@0@0@Z; RecursiveUtil::operator==(RecursiveUtil::NtObjectPath const &,RecursiveUtil::NtObjectPath const &)
0x18003b678  nop
0x18003b679  test    al, al
0x18003b67b  jnz     short loc_18003B6C0
0x18003b67d  lea     rcx, [rsp+168h+var_68]
0x18003b685  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b68a  nop
0x18003b68b  lea     rcx, [rsp+168h+hFindFile]
0x18003b690  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003b695  nop
0x18003b696  mov     [rsp+168h+hMem], rbx
0x18003b69b  mov     rcx, rdi; hMem
0x18003b69e  call    cs:__imp_LocalFree
0x18003b6a4  nop
0x18003b6a5  lea     rcx, [rsp+168h+ppszPathOut]
0x18003b6aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b6af  nop
0x18003b6b0  lea     rcx, [rsp+168h+pszPathIn]
0x18003b6b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b6ba  nop
0x18003b6bb  jmp     loc_18003BE00
0x18003b6c0  lea     rcx, [rsp+168h+var_68]
0x18003b6c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b6cd  mov     [rsp+168h+var_E0], r13d
0x18003b6d5  xor     edx, edx
0x18003b6d7  lea     rcx, [rsp+168h+pszPathIn]
0x18003b6dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003b6e1  lea     rax, word_180092AF0
0x18003b6e8  lea     rdx, Query; "*"
0x18003b6ef  test    r13d, r13d
0x18003b6f2  cmovz   rdx, rax; pszMore
0x18003b6f6  lea     r9, [rsp+168h+pszPathIn]; ppszPathOut
0x18003b6fb  mov     r8d, 10h; dwFlags
0x18003b701  mov     rcx, [rsp+168h+ppszPathOut]; pszPathIn
0x18003b706  call    cs:__imp_PathAllocCombine
0x18003b70c  mov     esi, eax
0x18003b70e  test    eax, eax
0x18003b710  jns     loc_18003B7DC
0x18003b716  mov     rcx, [rsp+168h]; this
0x18003b71e  mov     r9d, eax; char *
0x18003b721  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b728  mov     edx, 16Eh; void *
0x18003b72d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b732  nop
0x18003b733  lea     rcx, [rsp+168h+hFindFile]
0x18003b738  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003b73d  nop
0x18003b73e  mov     [rsp+168h+hMem], rbx
0x18003b743  mov     rcx, rdi; hMem
0x18003b746  call    cs:__imp_LocalFree
0x18003b74c  nop
0x18003b74d  lea     rcx, [rsp+168h+ppszPathOut]
0x18003b752  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b757  nop
0x18003b758  lea     rcx, [rsp+168h+pszPathIn]
0x18003b75d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b762  nop
0x18003b763  jmp     loc_18003BE02
0x18003b768  test    r14b, r14b
0x18003b76b  jz      short loc_18003B771
0x18003b76d  mov     esi, ebx
0x18003b76f  jmp     short loc_18003B7A7
0x18003b771  call    cs:__imp_GetLastError
0x18003b777  mov     esi, eax
0x18003b779  test    eax, eax
0x18003b77b  jle     short loc_18003B786
0x18003b77d  movzx   esi, ax
0x18003b780  or      esi, 80070000h
0x18003b786  test    esi, esi
0x18003b788  jns     short loc_18003B7A7
0x18003b78a  mov     rcx, [rsp+168h]; this
0x18003b792  mov     r9d, esi; char *
0x18003b795  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b79c  mov     edx, 162h; void *
0x18003b7a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b7a6  nop
0x18003b7a7  lea     rcx, [rsp+168h+hFindFile]
0x18003b7ac  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003b7b1  nop
0x18003b7b2  mov     [rsp+168h+hMem], rbx
0x18003b7b7  mov     rcx, rdi; hMem
0x18003b7ba  call    cs:__imp_LocalFree
0x18003b7c0  nop
0x18003b7c1  lea     rcx, [rsp+168h+ppszPathOut]
0x18003b7c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b7cb  nop
0x18003b7cc  lea     rcx, [rsp+168h+pszPathIn]
0x18003b7d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b7d6  nop
0x18003b7d7  jmp     loc_18003BE02
0x18003b7dc  mov     rdx, rdi; lpFindFileData
0x18003b7df  mov     rcx, [rsp+168h+pszPathIn]; lpFileName
0x18003b7e4  call    cs:__imp_FindFirstFileW
0x18003b7ea  mov     rdx, rax
0x18003b7ed  lea     rcx, [rsp+168h+hFindFile]
0x18003b7f2  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::reset(void *)
0x18003b7f7  mov     rax, [rsp+168h+hFindFile]
0x18003b7fc  dec     rax
0x18003b7ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b803  ja      loc_18003BD57
0x18003b809  mov     rsi, [rsp+168h+lpFileTime1]
0x18003b811  mov     [rsp+168h+var_F0], rsi
0x18003b816  mov     eax, r12d
0x18003b819  test    eax, eax
0x18003b81b  jz      loc_18003BCF7
0x18003b821  lea     r15, [rdi+2Ch]
0x18003b825  cmp     word ptr [r15], 2Eh ; '.'
0x18003b82a  jnz     short loc_18003B847
0x18003b82c  cmp     [rdi+2Eh], bx
0x18003b830  jz      loc_18003BC68
0x18003b836  cmp     word ptr [rdi+2Eh], 2Eh ; '.'
0x18003b83b  jnz     short loc_18003B847
0x18003b83d  cmp     [rdi+30h], bx
0x18003b841  jz      loc_18003BC68
0x18003b847  mov     rdx, [rsp+168h+var_D0]
0x18003b84f  lea     rcx, [rsp+168h+var_88]
0x18003b857  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003b85c  nop
0x18003b85d  test    r13d, r13d
0x18003b860  jz      loc_18003B9A3
0x18003b866  xor     edx, edx
0x18003b868  lea     rcx, [rsp+168h+pszPathIn]
0x18003b86d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003b872  xor     edx, edx
0x18003b874  lea     rcx, [rsp+168h+pszPathIn]
0x18003b879  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003b87e  lea     r9, [rsp+168h+pszPathIn]; ppszPathOut
0x18003b883  mov     r8d, 10h; dwFlags
0x18003b889  mov     rdx, r15; pszMore
0x18003b88c  mov     rcx, [rsp+168h+ppszPathOut]; pszPathIn
0x18003b891  call    cs:__imp_PathAllocCombine
0x18003b897  mov     esi, eax
0x18003b899  test    eax, eax
0x18003b89b  jns     short loc_18003B90E
0x18003b89d  mov     rcx, [rsp+168h]; this
0x18003b8a5  mov     r9d, eax; char *
0x18003b8a8  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b8af  mov     edx, 186h; void *
0x18003b8b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b8b9  nop
0x18003b8ba  lea     rcx, [rsp+168h+var_88]; this
0x18003b8c2  call    ??1SYNC_ROOT_INFO@@QEAA@XZ; SYNC_ROOT_INFO::~SYNC_ROOT_INFO(void)
0x18003b8c7  nop
0x18003b8c8  lea     rcx, [rsp+168h+hFindFile]
0x18003b8cd  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>>(void)
0x18003b8d2  nop
0x18003b8d3  mov     [rsp+168h+hMem], rbx
0x18003b8d8  test    rdi, rdi
0x18003b8db  jz      short loc_18003B8E7
0x18003b8dd  mov     rcx, rdi; hMem
0x18003b8e0  call    cs:__imp_LocalFree
0x18003b8e6  nop
0x18003b8e7  lea     rcx, [rsp+168h+ppszPathOut]
0x18003b8ec  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003b8f1  nop
0x18003b8f2  lea     rcx, [rsp+168h+pszPathIn]
0x18003b8f7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003b8fc  nop
0x18003b8fd  lea     rcx, [rsp+168h+var_FC+4]
0x18003b902  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x18003b907  mov     eax, esi
0x18003b909  jmp     loc_18003BE59
0x18003b90e  mov     rdx, r15; unsigned __int16 *
0x18003b911  lea     rcx, [rsp+168h+var_88]; this
0x18003b919  call    ?append@NtObjectPath@RecursiveUtil@@QEAAJPEBG@Z; RecursiveUtil::NtObjectPath::append(ushort const *)
0x18003b91e  mov     esi, eax
0x18003b920  test    eax, eax
0x18003b922  jns     short loc_18003B99E
0x18003b924  test    r14b, r14b
0x18003b927  jz      short loc_18003B92D
0x18003b929  mov     esi, ebx
0x18003b92b  jmp     short loc_18003B94A
0x18003b92d  mov     rcx, [rsp+168h]; this
0x18003b935  mov     r9d, eax; char *
0x18003b938  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003b93f  mov     edx, 18Bh; void *
0x18003b944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b949  nop
0x18003b94a  lea     rcx, [rsp+168h+var_88]; this
0x18003b952  call    ??1SYNC_ROOT_INFO@@QEAA@XZ; SYNC_ROOT_INFO::~SYNC_ROOT_INFO(void)
0x18003b957  nop
0x18003b958  lea     rcx, [rsp+168h+hFindFile]
0x18003b95d  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>>(void)
0x18003b962  nop
0x18003b963  mov     [rsp+168h+hMem], rbx
0x18003b968  test    rdi, rdi
0x18003b96b  jz      short loc_18003B977
0x18003b96d  mov     rcx, rdi; hMem
  ... truncated ...
```
