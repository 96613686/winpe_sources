# DavAsyncCreateQueryParentDirectory

- ea: `0x18001832c`
- end: `0x180019238`
- name: `DavAsyncCreateQueryParentDirectory`
- size: `3852`
- prototype: `__int64 __fastcall(char *pvCallbackContext)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001507c`
- `0x180017624`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b81c`
- `0x18000b93c`
- `0x18000bbec`
- `0x18000bc5c`
- `0x18000d9e4`
- `0x18001832c`
- `0x180019240`
- `0x180019454`
- `0x18001ad0c`
- `0x18001befc`
- `0x18001c390`
- `0x1800297e4`
- `0x180029bec`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!_wtoi` at `0x180018dc8`
- `msvcrt!_wtoi` at `0x180018dc8`
- `msvcrt!_wcsnicmp` at `0x180018d7b`
- `msvcrt!_wcsnicmp` at `0x180018d7b`
- `ntdll!RtlFreeHeap` at `0x1800191c7`
- `ntdll!RtlFreeHeap` at `0x1800191c7`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001859a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001859a`
- `ntdll!NtCreateFile` at `0x18001877e`
- `ntdll!NtCreateFile` at `0x18001877e`
- `ntdll!RtlNtStatusToDosError` at `0x18001878d`
- `ntdll!RtlNtStatusToDosError` at `0x18001878d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001899c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001907e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001912b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001899c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001907e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001912b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180018900`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180018f5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180018900`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180018f5e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800183ab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800186ff`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800183ab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800186ff`
- `KERNEL32!SystemTimeToFileTime` at `0x180018941`
- `KERNEL32!SystemTimeToFileTime` at `0x18001897c`
- `KERNEL32!SystemTimeToFileTime` at `0x180018f9f`
- `KERNEL32!SystemTimeToFileTime` at `0x180018fb1`
- `KERNEL32!SystemTimeToFileTime` at `0x180018941`
- `KERNEL32!SystemTimeToFileTime` at `0x18001897c`
- `KERNEL32!SystemTimeToFileTime` at `0x180018f9f`
- `KERNEL32!SystemTimeToFileTime` at `0x180018fb1`
- `ADVAPI32!EncryptFileW` at `0x180018662`
- `ADVAPI32!EncryptFileW` at `0x180018662`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x18001891d`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180018f7b`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x18001891d`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180018f7b`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x18001892f`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x180018f8d`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x18001892f`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x180018f8d`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180018b33`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180019121`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180018b33`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180019121`
- `WINHTTP!WinHttpSetOption` at `0x180018b0b`
- `WINHTTP!WinHttpSetOption` at `0x1800190d4`
- `WINHTTP!WinHttpSetOption` at `0x180018b0b`
- `WINHTTP!WinHttpSetOption` at `0x1800190d4`
- `WINHTTP!WinHttpCloseHandle` at `0x1800189d3`
- `WINHTTP!WinHttpCloseHandle` at `0x180018b9a`
- `WINHTTP!WinHttpCloseHandle` at `0x180018eba`
- `WINHTTP!WinHttpCloseHandle` at `0x1800189d3`
- `WINHTTP!WinHttpCloseHandle` at `0x180018b9a`
- `WINHTTP!WinHttpCloseHandle` at `0x180018eba`
- `WINHTTP!WinHttpQueryHeaders` at `0x180018d2e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180018e00`
- `WINHTTP!WinHttpQueryHeaders` at `0x180018d2e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180018e00`

## string_xrefs

- `0x180018de0`: `Lock-Token`
- `0x180018abe`: `DavAsyncQueryParentDirectory`
- `0x180018be2`: `DavAsyncQueryParentDirectory`
- `0x180019049`: `DavAsyncQueryParentDirectory`

## pseudocode

```c
__int64 __fastcall DavAsyncCreateQueryParentDirectory(char *pvCallbackContext)
{
  int v1; // r12d
  int v2; // r12d
  int v4; // r13d
  DWORD UrlCacheEntry; // eax
  DWORD v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  const WCHAR *v10; // rcx
  char v11; // al
  void *v12; // rcx
  void *v13; // rax
  ACCESS_MASK v14; // edx
  NTSTATUS v15; // eax
  int v16; // r8d
  unsigned int v17; // r15d
  _QWORD *v18; // rcx
  void *v19; // rax
  int v20; // eax
  struct _FILETIME v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rbx
  DWORD v24; // eax
  HINTERNET *v25; // r12
  BOOL v26; // r14d
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r9
  void *v30; // rcx
  DWORD v31; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  DWORD v36; // eax
  void *v37; // rcx
  void *v38; // rcx
  HINTERNET *v39; // r15
  void *v40; // rcx
  int v41; // eax
  struct _FILETIME v42; // rax
  __int64 v43; // rbx
  DWORD LastError; // eax
  void *v45; // rcx
  DWORD v46; // eax
  DWORD v47; // eax
  DWORD v48; // edi
  int AllocationSize; // [rsp+20h] [rbp-E0h]
  int AllocationSizea; // [rsp+20h] [rbp-E0h]
  int AllocationSizeb; // [rsp+20h] [rbp-E0h]
  int FileAttributes; // [rsp+28h] [rbp-D8h]
  int FileAttributesa; // [rsp+28h] [rbp-D8h]
  int FileAttributesb; // [rsp+28h] [rbp-D8h]
  ULONG ShareAccess; // [rsp+30h] [rbp-D0h]
  ULONG ShareAccessa; // [rsp+30h] [rbp-D0h]
  ULONG ShareAccessb; // [rsp+30h] [rbp-D0h]
  int v59; // [rsp+70h] [rbp-90h]
  DWORD dwBufferLength; // [rsp+74h] [rbp-8Ch] BYREF
  int Buffer; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME FileTime; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+88h] [rbp-78h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-20h] BYREF
  int v68; // [rsp+E8h] [rbp-18h]
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-10h] BYREF
  SYSTEMTIME pst; // [rsp+100h] [rbp+0h] BYREF
  WCHAR pwszTime[7]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t String[57]; // [rsp+11Eh] [rbp+1Eh] BYREF

  v1 = *((_DWORD *)pvCallbackContext + 1376);
  FileHandle = (void *)-1LL;
  v2 = v1 & 0x4000;
  v67 = 0;
  v68 = 0;
  *(_QWORD *)&NtPathName.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  Buffer = 0;
  NtPathName.Buffer = 0;
  IoStatusBlock = 0;
  if ( (pvCallbackContext[716] & 1) != 0 )
  {
    v4 = 1;
    FileTime = 0;
    v39 = (HINTERNET *)(pvCallbackContext + 592);
    v40 = (void *)*((_QWORD *)pvCallbackContext + 74);
    SystemTime = 0;
    pst = 0;
    if ( v40 )
    {
      WinHttpCloseHandle(v40);
      *v39 = 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
    *((_DWORD *)pvCallbackContext + 128) = 3;
    *((_DWORD *)pvCallbackContext + 13) = 1;
    v41 = *((_DWORD *)pvCallbackContext + 176) | 0x10;
    pvCallbackContext[5533] = 1;
    *((_DWORD *)pvCallbackContext + 1376) = v41;
    *((_DWORD *)pvCallbackContext + 968) = 1;
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
      *((_DWORD *)pvCallbackContext + 1376) |= 0x4000u;
    }
    GetSystemTime(&SystemTime);
    memset_0(pwszTime, 0, 0x7Cu);
    if ( WinHttpTimeFromSystemTime(&SystemTime, pwszTime)
      && WinHttpTimeToSystemTime(pwszTime, &pst)
      && SystemTimeToFileTime(&pst, &FileTime)
      || SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      v42 = FileTime;
      *((struct _FILETIME *)pvCallbackContext + 684) = FileTime;
      *((struct _FILETIME *)pvCallbackContext + 685) = v42;
      *((struct _FILETIME *)pvCallbackContext + 686) = v42;
      *((struct _FILETIME *)pvCallbackContext + 687) = v42;
      *((_DWORD *)pvCallbackContext + 969) = 1;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v43 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v43, 181, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, LastError);
    }
    if ( (unsigned int)DavHttpOpenRequestW(
                         *(_QWORD *)(*((_QWORD *)pvCallbackContext + 62) + 32LL),
                         *(_QWORD *)(*((_QWORD *)pvCallbackContext + 62) + 40LL),
                         (unsigned int)L"MKCOL",
                         *((_QWORD *)pvCallbackContext + 71),
                         AllocationSize,
                         FileAttributes,
                         ShareAccess,
                         0) )
    {
      v45 = *v39;
      if ( *v39 )
      {
        Buffer = 1;
        if ( !g_DisableCookies || WinHttpSetOption(v45, 0x3Fu, &Buffer, 4u) )
        {
          if ( WinHttpAddRequestHeaders(*v39, L"Content-Length: 0", 0xFFFFFFFF, 0xA0000000) )
          {
            v46 = DavAsyncCommonStates((unsigned int *)pvCallbackContext);
            v6 = v46;
            if ( v46
              && v46 != 997
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v46);
            }
          }
          else
          {
            UrlCacheEntry = GetLastError();
            v6 = UrlCacheEntry;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 184;
              goto LABEL_6;
            }
          }
        }
        else
        {
          UrlCacheEntry = GetLastError();
          v6 = UrlCacheEntry;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 183;
            goto LABEL_6;
          }
        }
      }
      else
      {
        UrlCacheEntry = GetLastError();
        v6 = UrlCacheEntry;
        if ( UrlCacheEntry != 997 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 182;
            goto LABEL_6;
          }
        }
      }
    }
    else
    {
      v6 = GetLastError();
    }
    goto LABEL_193;
  }
  RevertToSelf();
  v4 = 0;
  UrlCacheEntry = DavCreateUrlCacheEntry(pvCallbackContext);
  v6 = UrlCacheEntry;
  if ( UrlCacheEntry )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 151;
LABEL_6:
      v9 = UrlCacheEntry;
LABEL_7:
      WPP_SF_d(v7[2], v8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v9);
      goto LABEL_193;
    }
    goto LABEL_193;
  }
  UrlCacheEntry = DavCommitUrlCacheEntry(pvCallbackContext);
  v6 = UrlCacheEntry;
  if ( !UrlCacheEntry )
  {
    if ( v2 )
    {
      v6 = DavSetAclForEncryptedFile(*((LPCWSTR *)pvCallbackContext + 72));
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            153,
            (unsigned int)WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
            v6,
            *((_QWORD *)pvCallbackContext + 72));
        goto LABEL_193;
      }
    }
    UrlCacheEntry = UMReflectorImpersonate(pvCallbackContext, *((_QWORD *)pvCallbackContext + 9));
    v6 = UrlCacheEntry;
    if ( UrlCacheEntry )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 154;
        goto LABEL_6;
      }
      goto LABEL_193;
    }
    v4 = 1;
    v59 = 1;
    if ( *((_DWORD *)pvCallbackContext + 178) == 5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          155,
          WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
          *((_QWORD *)pvCallbackContext + 72));
      *((_DWORD *)pvCallbackContext + 970) = 1;
    }
    if ( (*((_DWORD *)pvCallbackContext + 179) & 0x1000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          156,
          WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
          *((_QWORD *)pvCallbackContext + 72));
      *((_DWORD *)pvCallbackContext + 971) = 1;
    }
    v10 = (const WCHAR *)*((_QWORD *)pvCallbackContext + 72);
    v6 = 0;
    HIDWORD(v67) = *((_DWORD *)pvCallbackContext + 171);
    v11 = pvCallbackContext[688] & 2;
    LODWORD(v67) = 12;
    BYTE1(v68) = v11;
    LOBYTE(v68) = 0;
    if ( !RtlDosPathNameToNtPathName_U(v10, &NtPathName, 0, 0) )
    {
      v6 = 161;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 157;
        v9 = 161;
        goto LABEL_7;
      }
      goto LABEL_193;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtPathName;
    v12 = 0;
    v13 = (void *)*((_QWORD *)pvCallbackContext + 84);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    if ( v13 )
      v12 = v13;
    ObjectAttributes.SecurityQualityOfService = &v67;
    ObjectAttributes.SecurityDescriptor = v12;
    if ( *((_DWORD *)pvCallbackContext + 178) == 2 )
      *((_DWORD *)pvCallbackContext + 178) = 3;
    if ( v2 )
    {
      if ( (pvCallbackContext[5504] & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
        v6 = 6009;
        goto LABEL_193;
      }
      if ( !EncryptFileW(*((LPCWSTR *)pvCallbackContext + 72)) )
      {
        UrlCacheEntry = GetLastError();
        v6 = UrlCacheEntry;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 160;
          goto LABEL_6;
        }
        goto LABEL_193;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, &NtPathName);
      *((_DWORD *)pvCallbackContext + 1376) |= 0x4000u;
      *((_DWORD *)pvCallbackContext + 973) = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, &NtPathName);
      RevertToSelf();
      v4 = 0;
      v59 = 0;
    }
    v14 = *((_DWORD *)pvCallbackContext + 173) & 0xFFFFFFF9 | 2;
    if ( (pvCallbackContext[692] & 0x21) == 0 )
      v14 = *((_DWORD *)pvCallbackContext + 173) & 0xFFFFFFFB;
    v15 = NtCreateFile(
            &FileHandle,
            v14,
            &ObjectAttributes,
            &IoStatusBlock,
            (PLARGE_INTEGER)pvCallbackContext + 87,
            *((_DWORD *)pvCallbackContext + 176) & 0xFFFFFFFE,
            7u,
            *((_DWORD *)pvCallbackContext + 178),
            *((_DWORD *)pvCallbackContext + 179),
            *((PVOID *)pvCallbackContext + 90),
            *((_DWORD *)pvCallbackContext + 182));
    v17 = v15;
    if ( v15 )
    {
      v6 = RtlNtStatusToDosError(v15);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v17);
      *((_QWORD *)pvCallbackContext + 682) = 0;
      *((_QWORD *)pvCallbackContext + 683) = 0;
      goto LABEL_193;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
          pvCallbackContext);
        v18 = WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
        WPP_SF_q(v18[2], 164, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, FileHandle);
    }
    v19 = FileHandle;
    *((_QWORD *)pvCallbackContext + 682) = FileHandle;
    *((_QWORD *)pvCallbackContext + 683) = v19;
    if ( *((_DWORD *)pvCallbackContext + 136) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
      goto LABEL_193;
    }
    FileTime = 0;
    SystemTime = 0;
    pst = 0;
    if ( *((_DWORD *)pvCallbackContext + 176) )
    {
      *((_DWORD *)pvCallbackContext + 968) = 1;
      v20 = *((_DWORD *)pvCallbackContext + 176);
      *((_DWORD *)pvCallbackContext + 1376) = v20;
      if ( v2 )
        *((_DWORD *)pvCallbackContext + 1376) = v20 | 0x4000;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_DDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        166,
        v16,
        *((_DWORD *)pvCallbackContext + 176),
        *((_DWORD *)pvCallbackContext + 1376),
        *((_QWORD *)pvCallbackContext + 72));
    GetSystemTime(&SystemTime);
    memset_0(pwszTime, 0, 0x7Cu);
    if ( WinHttpTimeFromSystemTime(&SystemTime, pwszTime)
      && WinHttpTimeToSystemTime(pwszTime, &pst)
      && SystemTimeToFileTime(&pst, &FileTime)
      || SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      v21 = FileTime;
      *((struct _FILETIME *)pvCallbackContext + 684) = FileTime;
      *((struct _FILETIME *)pvCallbackContext + 685) = v21;
      *((struct _FILETIME *)pvCallbackContext + 686) = v21;
      *((struct _FILETIME *)pvCallbackContext + 687) = v21;
      *((_DWORD *)pvCallbackContext + 969) = 1;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_89:
        v25 = (HINTERNET *)(pvCallbackContext + 592);
        if ( *((_QWORD *)pvCallbackContext + 74) )
        {
          WinHttpCloseHandle(*v25);
          *v25 = 0;
          v22 = WPP_GLOBAL_Control;
        }
        if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 )
          WPP_SF_(v22[2], 168, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids);
        if ( !v4 )
        {
          UrlCacheEntry = UMReflectorImpersonate(pvCallbackContext, *((_QWORD *)pvCallbackContext + 9));
          v6 = UrlCacheEntry;
          if ( UrlCacheEntry )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 169;
              goto LABEL_6;
            }
            goto LABEL_193;
          }
          v59 = 1;
        }
        v26 = 0;
        dwBufferLength = 0;
        if ( *(_DWORD *)&DavSupportLockingOfFiles
          && *((_DWORD *)pvCallbackContext + 177) <= 1u
          && (*((_DWORD *)pvCallbackContext + 173) & 0x50000006) != 0 )
        {
          v27 = *((_QWORD *)pvCallbackContext + 63);
          dwBufferLength = 1;
          v26 = *(_DWORD *)(v27 + 40) != 0;
        }
        v28 = *((_QWORD *)pvCallbackContext + 62);
        v29 = *((_QWORD *)pvCallbackContext + 71);
        *((_DWORD *)pvCallbackContext + 13) = 1;
        *((_DWORD *)pvCallbackContext + 128) = 4;
        if ( !(unsigned int)DavHttpOpenRequestW(
                              *(_QWORD *)(v28 + 32),
                              *(_QWORD *)(v28 + 40),
                              (unsigned int)L"PUT",
                              v29,
                              AllocationSizea,
                              FileAttributesa,
                              ShareAccessa,
                              0) )
        {
LABEL_117:
          v32 = GetLastError();
          v6 = v32;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v32);
          goto LABEL_120;
        }
        while ( 1 )
        {
          v30 = *v25;
          if ( !*v25 )
          {
            v33 = GetLastError();
            v6 = v33;
            if ( v33 != 997 )
            {
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v35 = 171;
                goto LABEL_151;
              }
              goto LABEL_120;
            }
LABEL_192:
            v4 = v59;
            goto LABEL_193;
          }
          Buffer = 1;
          if ( g_DisableCookies )
          {
            if ( !WinHttpSetOption(v30, 0x3Fu, &Buffer, 4u) )
              break;
          }
          if ( v26 && !WinHttpAddRequestHeaders(*v25, L"X-MSDAVEXTLockTimeout: Second-3600\n", 0xFFFFFFFF, 0xA0000000) )
          {
            v33 = GetLastError();
            v6 = v33;
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v35 = 173;
              goto LABEL_151;
            }
            goto LABEL_120;
          }
          v31 = DavAsyncCommonStates((unsigned int *)pvCallbackContext);
          v6 = v31;
          if ( !v31 || v31 == 997 )
          {
            if ( dwBufferLength )
            {
              if ( !v26 )
              {
                v36 = DavLockTheFileOnTheServer((__int64)pvCallbackContext);
                v6 = v36;
                if ( v36 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      175,
                      WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
                      v36);
                  }
                  goto LABEL_120;
                }
                goto LABEL_192;
              }
            }
            else if ( !v26 )
            {
              goto LABEL_192;
            }
            *((_QWORD *)pvCallbackContext + 681) = 0;
            v37 = *v25;
            dwBufferLength = 64;
            if ( WinHttpQueryHeaders(v37, 0xFFFFu, L"X-MSDAVEXTLockTimeout", pwszTime, &dwBufferLength, 0) )
            {
              if ( _wcsnicmp(pwszTime, L"Second-", 7u) )
              {
                v6 = 87;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    177,
                    WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
                    pwszTime);
                }
              }
              else
              {
                *((_DWORD *)pvCallbackContext + 1361) = _wtoi(String);
                v38 = *v25;
                dwBufferLength = 520;
                if ( WinHttpQueryHeaders(v38, 0xFFFFu, L"Lock-Token", pvCallbackContext + 3896, &dwBufferLength, 0) )
                {
                  *((_DWORD *)pvCallbackContext + 1362) = 1;
                  goto LABEL_120;
                }
                v33 = GetLastError();
                v6 = v33;
                v34 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v35 = 178;
                  goto LABEL_151;
                }
              }
            }
            else
            {
              v33 = GetLastError();
              v6 = v33;
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v35 = 176;
                goto LABEL_151;
              }
            }
            goto LABEL_120;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v31);
          if ( !v26 )
            goto LABEL_192;
          v26 = 0;
          WinHttpCloseHandle(*v25);
          *v25 = 0;
          *((_DWORD *)pvCallbackContext + 13) = 1;
          *((_DWORD *)pvCallbackContext + 128) = 4;
          if ( !(unsigned int)DavHttpOpenRequestW(
                                *(_QWORD *)(*((_QWORD *)pvCallbackContext + 62) + 32LL),
                                *(_QWORD *)(*((_QWORD *)pvCallbackContext + 62) + 40LL),
                                (unsigned int)L"PUT",
                                *((_QWORD *)pvCallbackContext + 71),
                                AllocationSizeb,
                                FileAttributesb,
                                ShareAccessb,
                                0) )
            goto LABEL_117;
        }
        v33 = GetLastError();
        v6 = v33;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v35 = 172;
LABEL_151:
          WPP_SF_d(v34[2], v35, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v33);
        }
LABEL_120:
        v4 = v59;
        goto LABEL_193;
      }
      v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v24 = GetLastError();
      WPP_SF_d(v23, 167, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v24);
    }
    v22 = WPP_GLOBAL_Control;
    goto LABEL_89;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 152;
    goto LABEL_6;
  }
LABEL_193:
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( !v4 )
  {
    v47 = UMReflectorImpersonate(pvCallbackContext, *((_QWORD *)pvCallbackContext + 9));
    v48 = v47;
    if ( v47 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v47);
      if ( !v6 )
        return v48;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001832c  push    rbp
0x18001832e  push    rbx
0x18001832f  push    rsi
0x180018330  push    rdi
0x180018331  push    r12
0x180018333  push    r13
0x180018335  push    r14
0x180018337  push    r15
0x180018339  lea     rbp, [rsp-0A8h]
0x180018341  sub     rsp, 1A8h
0x180018348  mov     rax, cs:__security_cookie
0x18001834f  xor     rax, rsp
0x180018352  mov     [rbp+0E0h+var_50], rax
0x180018359  mov     r12d, [rcx+1580h]
0x180018360  xor     eax, eax
0x180018362  xorps   xmm0, xmm0
0x180018365  mov     [rbp+0E0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18001836d  and     r12d, 4000h
0x180018374  mov     [rbp+0E0h+var_100], rax
0x180018378  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.ObjectName], xmm0
0x18001837c  lea     r15d, [rax+1]
0x180018380  mov     [rbp+0E0h+var_F8], eax
0x180018383  mov     rdi, rcx
0x180018386  mov     qword ptr [rbp+0E0h+NtPathName.Length], rax
0x18001838a  movups  xmmword ptr [rbp+0E0h+ObjectAttributes.Length], xmm0
0x18001838e  mov     [rsp+1E0h+Buffer], eax
0x180018392  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+1Ch], xmm0
0x180018396  mov     [rbp+0E0h+NtPathName.Buffer], rax
0x18001839a  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x18001839e  test    [rcx+2CCh], r15b
0x1800183a5  jnz     loc_180018E99
0x1800183ab  call    cs:__imp_RevertToSelf
0x1800183b1  mov     rcx, rdi
0x1800183b4  xor     r13d, r13d
0x1800183b7  call    DavCreateUrlCacheEntry
0x1800183bc  mov     ebx, eax
0x1800183be  test    eax, eax
0x1800183c0  jz      short loc_180018400
0x1800183c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183c9  lea     rsi, WPP_GLOBAL_Control
0x1800183d0  cmp     rcx, rsi
0x1800183d3  jz      loc_1800191AD
0x1800183d9  test    [rcx+1Ch], r15b
0x1800183dd  jz      loc_1800191AD
0x1800183e3  mov     edx, 97h
0x1800183e8  mov     r9d, eax
0x1800183eb  mov     rcx, [rcx+10h]
0x1800183ef  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800183f6  call    WPP_SF_d
0x1800183fb  jmp     loc_1800191AD
0x180018400  mov     rcx, rdi
0x180018403  call    DavCommitUrlCacheEntry
0x180018408  mov     ebx, eax
0x18001840a  test    eax, eax
0x18001840c  jz      short loc_180018436
0x18001840e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018415  lea     rsi, WPP_GLOBAL_Control
0x18001841c  cmp     rcx, rsi
0x18001841f  jz      loc_1800191AD
0x180018425  test    [rcx+1Ch], r15b
0x180018429  jz      loc_1800191AD
0x18001842f  mov     edx, 98h
0x180018434  jmp     short loc_1800183E8
0x180018436  test    r12d, r12d
0x180018439  jz      short loc_180018497
0x18001843b  mov     rcx, [rdi+240h]; lpFileName
0x180018442  call    DavSetAclForEncryptedFile
0x180018447  mov     ebx, eax
0x180018449  test    eax, eax
0x18001844b  jz      short loc_180018497
0x18001844d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018454  lea     rsi, WPP_GLOBAL_Control
0x18001845b  cmp     rcx, rsi
0x18001845e  jz      loc_1800191AD
0x180018464  test    [rcx+1Ch], r15b
0x180018468  jz      loc_1800191AD
0x18001846e  mov     rax, [rdi+240h]
0x180018475  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001847c  mov     rcx, [rcx+10h]
0x180018480  mov     edx, 99h
0x180018485  mov     r9d, ebx
0x180018488  mov     [rsp+1E0h+AllocationSize], rax
0x18001848d  call    WPP_SF_dS
0x180018492  jmp     loc_1800191AD
0x180018497  mov     rdx, [rdi+48h]
0x18001849b  mov     rcx, rdi
0x18001849e  call    UMReflectorImpersonate
0x1800184a3  mov     ebx, eax
0x1800184a5  test    eax, eax
0x1800184a7  jz      short loc_1800184D4
0x1800184a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184b0  lea     rsi, WPP_GLOBAL_Control
0x1800184b7  cmp     rcx, rsi
0x1800184ba  jz      loc_1800191AD
0x1800184c0  test    [rcx+1Ch], r15b
0x1800184c4  jz      loc_1800191AD
0x1800184ca  mov     edx, 9Ah
0x1800184cf  jmp     loc_1800183E8
0x1800184d4  cmp     dword ptr [rdi+2C8h], 5
0x1800184db  lea     rsi, WPP_GLOBAL_Control
0x1800184e2  mov     r13d, r15d
0x1800184e5  mov     [rsp+1E0h+var_170], r15d
0x1800184ea  mov     r14d, 2
0x1800184f0  jnz     short loc_180018527
0x1800184f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184f9  cmp     rcx, rsi
0x1800184fc  jz      short loc_180018520
0x1800184fe  test    [rcx+1Ch], r14b
0x180018502  jz      short loc_180018520
0x180018504  mov     r9, [rdi+240h]
0x18001850b  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180018512  mov     rcx, [rcx+10h]
0x180018516  mov     edx, 9Bh
0x18001851b  call    WPP_SF_S
0x180018520  mov     [rdi+0F28h], r15d
0x180018527  test    dword ptr [rdi+2CCh], 1000h
0x180018531  jz      short loc_180018568
0x180018533  mov     rcx, cs:WPP_GLOBAL_Control
0x18001853a  cmp     rcx, rsi
0x18001853d  jz      short loc_180018561
0x18001853f  test    [rcx+1Ch], r14b
0x180018543  jz      short loc_180018561
0x180018545  mov     r9, [rdi+240h]
0x18001854c  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180018553  mov     rcx, [rcx+10h]
0x180018557  mov     edx, 9Ch
0x18001855c  call    WPP_SF_S
0x180018561  mov     [rdi+0F2Ch], r15d
0x180018568  mov     eax, [rdi+2ACh]
0x18001856e  lea     rdx, [rbp+0E0h+NtPathName]; NtPathName
0x180018572  mov     rcx, [rdi+240h]; DosPathName
0x180018579  xor     ebx, ebx
0x18001857b  mov     dword ptr [rbp+0E0h+var_100+4], eax
0x18001857e  xor     r9d, r9d; DirectoryInfo
0x180018581  mov     al, [rdi+2B0h]
0x180018587  xor     r8d, r8d; NtFileNamePart
0x18001858a  and     al, r14b
0x18001858d  mov     dword ptr [rbp+0E0h+var_100], 0Ch
0x180018594  mov     byte ptr [rbp+0E0h+var_F8+1], al
0x180018597  mov     byte ptr [rbp+0E0h+var_F8], bl
0x18001859a  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800185a0  test    al, al
0x1800185a2  jnz     short loc_1800185CE
0x1800185a4  mov     ebx, 0A1h
0x1800185a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185b0  cmp     rcx, rsi
0x1800185b3  jz      loc_1800191AD
0x1800185b9  test    [rcx+1Ch], r15b
0x1800185bd  jz      loc_1800191AD
0x1800185c3  lea     edx, [rbx-4]
0x1800185c6  mov     r9d, ebx
0x1800185c9  jmp     loc_1800183EB
0x1800185ce  lea     rax, [rbp+0E0h+NtPathName]
0x1800185d2  mov     [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x1800185d9  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x1800185dd  mov     rcx, rbx
0x1800185e0  mov     rax, [rdi+2A0h]
0x1800185e7  test    rax, rax
0x1800185ea  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], rbx
0x1800185ee  mov     [rbp+0E0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800185f5  cmovnz  rcx, rax
0x1800185f9  lea     rax, [rbp+0E0h+var_100]
0x1800185fd  mov     [rbp+0E0h+ObjectAttributes.SecurityQualityOfService], rax
0x180018601  mov     [rbp+0E0h+ObjectAttributes.SecurityDescriptor], rcx
0x180018605  cmp     [rdi+2C8h], r14d
0x18001860c  jnz     short loc_180018618
0x18001860e  mov     dword ptr [rdi+2C8h], 3
0x180018618  test    r12d, r12d
0x18001861b  jz      loc_1800186D4
0x180018621  test    [rdi+1580h], r15b
0x180018628  jz      short loc_18001865B
0x18001862a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018631  cmp     rcx, rsi
0x180018634  jz      short loc_180018651
0x180018636  test    [rcx+1Ch], r14b
0x18001863a  jz      short loc_180018651
0x18001863c  mov     rcx, [rcx+10h]
0x180018640  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180018647  mov     edx, 9Eh
0x18001864c  call    WPP_SF_
0x180018651  mov     ebx, 1779h
0x180018656  jmp     loc_1800191AD
0x18001865b  mov     rcx, [rdi+240h]; lpFileName
0x180018662  call    cs:__imp_EncryptFileW
0x180018668  test    eax, eax
0x18001866a  jz      short loc_1800186A8
0x18001866c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018673  cmp     rcx, rsi
0x180018676  jz      short loc_180018697
0x180018678  test    [rcx+1Ch], r14b
0x18001867c  jz      short loc_180018697
0x18001867e  mov     rcx, [rcx+10h]
0x180018682  lea     r9, [rbp+0E0h+NtPathName]
0x180018686  mov     edx, 9Fh
0x18001868b  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180018692  call    WPP_SF_Z
0x180018697  bts     dword ptr [rdi+1580h], 0Eh
0x18001869f  mov     [rdi+0F34h], r15d
0x1800186a6  jmp     short loc_18001870C
0x1800186a8  call    cs:__imp_GetLastError
0x1800186ae  mov     ebx, eax
0x1800186b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186b7  cmp     rcx, rsi
0x1800186ba  jz      loc_1800191AD
0x1800186c0  test    [rcx+1Ch], r15b
0x1800186c4  jz      loc_1800191AD
0x1800186ca  mov     edx, 0A0h
0x1800186cf  jmp     loc_1800183E8
0x1800186d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186db  cmp     rcx, rsi
0x1800186de  jz      short loc_1800186FF
0x1800186e0  test    [rcx+1Ch], r14b
0x1800186e4  jz      short loc_1800186FF
0x1800186e6  mov     rcx, [rcx+10h]
0x1800186ea  lea     r9, [rbp+0E0h+NtPathName]
0x1800186ee  mov     edx, 0A1h
0x1800186f3  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800186fa  call    WPP_SF_Z
0x1800186ff  call    cs:__imp_RevertToSelf
0x180018705  mov     r13d, ebx
0x180018708  mov     [rsp+1E0h+var_170], ebx
0x18001870c  mov     ecx, [rdi+2B4h]
0x180018712  lea     r8, [rdi+2B8h]
0x180018719  mov     eax, [rdi+2D8h]
0x18001871f  and     ecx, 0FFFFFFFBh
0x180018722  mov     r9d, [rdi+2C0h]
0x180018729  mov     edx, ecx
0x18001872b  mov     [rsp+1E0h+EaLength], eax; EaLength
0x18001872f  and     r9d, 0FFFFFFFEh
0x180018733  mov     rax, [rdi+2D0h]
0x18001873a  or      edx, r14d
0x18001873d  test    byte ptr [rdi+2B4h], 21h
0x180018744  mov     [rsp+1E0h+EaBuffer], rax; EaBuffer
0x180018749  mov     eax, [rdi+2CCh]
0x18001874f  cmovz   edx, ecx; DesiredAccess
0x180018752  mov     [rsp+1E0h+CreateOptions], eax; CreateOptions
0x180018756  lea     rcx, [rbp+0E0h+FileHandle]; FileHandle
0x18001875a  mov     eax, [rdi+2C8h]
0x180018760  mov     [rsp+1E0h+CreateDisposition], eax; CreateDisposition
0x180018764  mov     [rsp+1E0h+ShareAccess], 7; ShareAccess
0x18001876c  mov     [rsp+1E0h+FileAttributes], r9d; FileAttributes
0x180018771  lea     r9, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x180018775  mov     [rsp+1E0h+AllocationSize], r8; AllocationSize
0x18001877a  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x18001877e  call    cs:__imp_NtCreateFile
0x180018784  mov     r15d, eax
0x180018787  test    eax, eax
0x180018789  jz      short loc_1800187DA
0x18001878b  mov     ecx, eax; Status
0x18001878d  call    cs:__imp_RtlNtStatusToDosError
0x180018793  mov     ebx, eax
0x180018795  mov     rcx, cs:WPP_GLOBAL_Control
0x18001879c  cmp     rcx, rsi
0x18001879f  jz      short loc_1800187BF
0x1800187a1  test    byte ptr [rcx+1Ch], 1
0x1800187a5  jz      short loc_1800187BF
0x1800187a7  mov     rcx, [rcx+10h]
0x1800187ab  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800187b2  mov     edx, 0A2h
0x1800187b7  mov     r9d, r15d
0x1800187ba  call    WPP_SF_d
0x1800187bf  mov     qword ptr [rdi+1550h], 0
0x1800187ca  mov     qword ptr [rdi+1558h], 0
0x1800187d5  jmp     loc_1800191A7
0x1800187da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187e1  cmp     rcx, rsi
0x1800187e4  jz      short loc_18001882F
0x1800187e6  test    [rcx+1Ch], r14b
0x1800187ea  jz      short loc_18001880B
0x1800187ec  mov     rcx, [rcx+10h]
0x1800187f0  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800187f7  mov     edx, 0A3h
0x1800187fc  mov     r9, rdi
0x1800187ff  call    WPP_SF_q
0x180018804  mov     rcx, cs:WPP_GLOBAL_Control
0x18001880b  cmp     rcx, rsi
0x18001880e  jz      short loc_18001882F
0x180018810  test    [rcx+1Ch], r14b
0x180018814  jz      short loc_18001882F
0x180018816  mov     r9, [rbp+0E0h+FileHandle]
0x18001881a  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x180018821  mov     rcx, [rcx+10h]
0x180018825  mov     edx, 0A4h
0x18001882a  call    WPP_SF_q
0x18001882f  mov     rax, [rbp+0E0h+FileHandle]
0x180018833  mov     [rdi+1550h], rax
0x18001883a  mov     [rdi+1558h], rax
0x180018841  cmp     [rdi+220h], ebx
0x180018847  jz      short loc_18001887D
0x180018849  mov     rcx, cs:WPP_GLOBAL_Control
0x180018850  cmp     rcx, rsi
0x180018853  jz      loc_1800191A7
0x180018859  test    [rcx+1Ch], r14b
0x18001885d  jz      loc_1800191A7
0x180018863  mov     rcx, [rcx+10h]
0x180018867  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001886e  mov     edx, 0A5h
0x180018873  call    WPP_SF_
0x180018878  jmp     loc_1800191A7
0x18001887d  xorps   xmm0, xmm0
  ... truncated ...
```
