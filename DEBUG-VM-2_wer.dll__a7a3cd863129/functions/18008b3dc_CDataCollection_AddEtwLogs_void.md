# CDataCollection::AddEtwLogs(void)

- ea: `0x18008b3dc`
- end: `0x18008bea9`
- name: `?AddEtwLogs@CDataCollection@@QEAAJXZ`
- size: `2765`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008fec`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x180008568`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x180013730`
- `0x1800157c4`
- `0x18001abd8`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001da80`
- `0x18001dc24`
- `0x18001fe24`
- `0x18002ffc4`
- `0x18003d990`
- `0x180044230`
- `0x180045bdc`
- `0x180046d74`
- `0x1800475e4`
- `0x18004ac98`
- `0x180050db0`
- `0x1800517cc`
- `0x18006493c`
- `0x180065d04`
- `0x18007076c`
- `0x18008b3dc`
- `0x1800a9fb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b888`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bcbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bcbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd7c`
- `ntdll!wcsrchr` at `0x18008ba5b`
- `ntdll!wcsrchr` at `0x18008ba5b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18008be47`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18008be47`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b636`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b636`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008bb1f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008bb1f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008b862`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008b862`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008b92b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008b92b`

## string_xrefs

- `0x18008bddd`: `onecore\windows\feedback\core\werdll\lib\datacollection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CDataCollection::AddEtwLogs(CReport **this)
{
  __int64 FirstFileW; // r14
  wchar_t *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  int PathOfWERTempDirectory; // eax
  DWORD LastError; // eax
  int v9; // eax
  const wchar_t *v10; // rcx
  int v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  int TempFile; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  wchar_t *v18; // rax
  wchar_t *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD v22; // eax
  unsigned int v23; // eax
  DWORD v24; // eax
  int v25; // eax
  wchar_t *v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  wchar_t *v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpPathName[4]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h]
  _QWORD v34[2]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v35[5]; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v37; // [rsp+E8h] [rbp-18h]
  __int128 v38; // [rsp+F8h] [rbp-8h]
  __int64 v39; // [rsp+108h] [rbp+8h]
  __int128 v40; // [rsp+110h] [rbp+10h]
  wchar_t *v41[4]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *v42[4]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v43[4]; // [rsp+160h] [rbp+60h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+180h] [rbp+80h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1A0h] [rbp+A0h] BYREF
  _DWORD v46[12]; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t v47[680]; // [rsp+420h] [rbp+320h] BYREF
  __int16 v48; // [rsp+970h] [rbp+870h] BYREF
  _BYTE v49[38]; // [rsp+972h] [rbp+872h] BYREF
  int v50; // [rsp+998h] [rbp+898h]
  int v51; // [rsp+99Ch] [rbp+89Ch]
  int v52; // [rsp+BA8h] [rbp+AA8h]
  WCHAR NewFileName[264]; // [rsp+EF0h] [rbp+DF0h] BYREF
  WCHAR v54[264]; // [rsp+1100h] [rbp+1000h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1368h] [rbp+1268h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpPathName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpExistingFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v43);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v42);
  LOWORD(v46[0]) = 0;
  memset_0((char *)v46 + 2, 0, 0x576u);
  v48 = 0;
  memset_0(v49, 0, 0x576u);
  FirstFileW = -1;
  v33 = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  v30 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  SecurityAttributes.nLength = 24;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v41);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !*this )
  {
    v4 = -2147024809;
    if ( v3 == (wchar_t *)&WPP_GLOBAL_Control || (v3[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 66;
LABEL_8:
    v6 = v4;
    goto LABEL_135;
  }
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v54, 260);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 67;
LABEL_134:
    v6 = (unsigned int)PathOfWERTempDirectory;
    goto LABEL_135;
  }
  PathOfWERTempDirectory = CReport::GetUniqueIdentifier(*this, v35);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 68;
    goto LABEL_134;
  }
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpPathName,
                             L"%ws\\%ws",
                             v54,
                             v35[0]);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 69;
    goto LABEL_134;
  }
  PathOfWERTempDirectory = CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(
                             (struct CSecurityAttributes *)&SecurityAttributes,
                             0);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 70;
    goto LABEL_134;
  }
  if ( !CreateDirectoryW(lpPathName[0], &SecurityAttributes) )
  {
    LastError = GetLastError();
    PathOfWERTempDirectory = ERROR_HR_FROM_WIN32(LastError);
    v4 = PathOfWERTempDirectory;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 71;
    goto LABEL_134;
  }
  v9 = UtilAddAccessToPath(lpPathName[0], 0x10000000u);
  if ( v9 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, (unsigned int)v9);
  v46[0] = 91751760;
  v46[10] = -268369918;
  if ( (int)StringCchCopyW(v47, 0x104u, v35[0]) < 0 )
  {
    v6 = 2147942606LL;
    v4 = -2147024690;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 73;
LABEL_135:
    WPP_SF_d(*((_QWORD *)v3 + 2), v5, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v6);
    goto LABEL_136;
  }
  PathOfWERTempDirectory = UtilSendMessageToWersvc(v10, (struct _WERSVC_MSG *)v46, (struct _WERSVC_MSG *)&v48, 0xEA60u);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 74;
    goto LABEL_134;
  }
  if ( v50 != -268369920 )
  {
    if ( v52 )
    {
      v4 = -2147467259;
      v3 = WPP_GLOBAL_Control;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          v51 | 0x10000000u);
        v3 = WPP_GLOBAL_Control;
      }
      v4 = 1;
    }
    if ( v3 == (wchar_t *)&WPP_GLOBAL_Control || (v3[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 76;
    goto LABEL_8;
  }
  v11 = UtilVerifyAndLockDirectory((wchar_t *)lpPathName[0], (__int64)&v30);
  v4 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        lpPathName[0],
        v11);
    goto LABEL_136;
  }
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpFileName,
                             L"%s\\*etl",
                             lpPathName[0]);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 78;
    goto LABEL_134;
  }
  FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
  v33 = FirstFileW;
  if ( FirstFileW == -1 )
  {
    v24 = GetLastError();
    PathOfWERTempDirectory = ERROR_HR_FROM_WIN32(v24);
    v4 = PathOfWERTempDirectory;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 79;
    goto LABEL_134;
  }
  while ( 1 )
  {
    v12 = (wchar_t *)HeapAlloc(g_hWerheap, 0, 0x208u);
    v13 = v12;
    if ( v12 )
      memset_0(v12, 0, 0x208u);
    else
      v13 = 0;
    v29 = v13;
    if ( !v13 )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 80;
LABEL_129:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v21);
      goto LABEL_130;
    }
    TempFile = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 lpExistingFileName,
                 L"%ls\\%ls",
                 lpPathName[0],
                 FindFileData.cFileName);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 81;
      goto LABEL_125;
    }
    TempFile = UtilGetTempFile(0, v54, (const size_t *)L".etl", NewFileName, (__int64)v27, &SecurityAttributes, 0, 0);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 82;
      goto LABEL_125;
    }
    if ( !MoveFileExW(lpExistingFileName[0], NewFileName, 1u) )
      break;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             lpExistingFileName,
                             NewFileName) )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 84;
      goto LABEL_129;
    }
    v34[0] = FindFileData.cFileName;
    v15 = -1;
    do
      ++v15;
    while ( FindFileData.cFileName[v15] );
    v34[1] = v15;
    if ( (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                            v34,
                            L"HostTrace_")
      || (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                            v34,
                            L"GuestTrace_") )
    {
      goto LABEL_86;
    }
    v16 = lpExistingFileName[1] - lpExistingFileName[0];
    v17 = v16 - 1;
    if ( !v16 )
    {
LABEL_75:
      v4 = -2147024773;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          lpExistingFileName[0],
          123);
      goto LABEL_130;
    }
    while ( lpExistingFileName[0][v17] != 92 )
    {
      if ( --v17 == -1 )
        goto LABEL_75;
    }
    if ( v16 <= v17 + 1 )
    {
      v4 = -2147418113;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          lpExistingFileName[0]);
      goto LABEL_130;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v41,
                             &lpExistingFileName[0][v17 + 1]) )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 87;
      goto LABEL_129;
    }
    if ( (int)StringCchCopyW(v13, 0x104u, v41[0]) < 0 )
    {
      v21 = 2147942606LL;
      v4 = -2147024690;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 88;
      goto LABEL_129;
    }
    v18 = wcsrchr(FindFileData.cFileName, 0x2Eu);
    if ( !v18 )
    {
      TempFile = -2147024773;
      v4 = -2147024773;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 89;
      goto LABEL_125;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v42,
                             FindFileData.cFileName,
                             v18 - FindFileData.cFileName) )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 90;
      goto LABEL_129;
    }
    TempFile = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 v43,
                 L"%s_inject.etl",
                 v42[0]);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 91;
      goto LABEL_125;
    }
    TempFile = CReport::AddFileCallback(
                 *this,
                 WerFileTypeEtlTrace,
                 0,
                 (int (*)(void *, void *, void *, unsigned int, int (*)(void *, union _LARGE_INTEGER, union _LARGE_INTEGER *, unsigned int, void *), int (*)(void *, const void *, unsigned int, void *), void (*)(void *, unsigned int, const wchar_t *, char *)))CDataCollection::MergeEtlRoutine,
                 v13,
                 v43[0],
                 0);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 92;
      goto LABEL_125;
    }
    v29 = 0;
LABEL_86:
    TempFile = CReport::AddFile(*this, WerFileTypeEtlTrace, 1u, lpExistingFileName[0], FindFileData.cFileName, 0);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 93;
LABEL_125:
      v21 = (unsigned int)TempFile;
      goto LABEL_129;
    }
    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      goto LABEL_130;
    utl::unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>::~unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>(&v29);
  }
  v22 = GetLastError();
  v23 = ERROR_HR_FROM_WIN32(v22);
  v4 = v23;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      83,
      (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      lpExistingFileName[0],
      (__int64)NewFileName,
      v23);
LABEL_130:
  utl::unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>::~unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>(&v29);
LABEL_136:
  tlx::unique_any<tlx::file_handle_traits>::reset(&v30, 0);
  v25 = UtilRecursiveRemoveDirectory(lpPathName[0], 0, 0, 0, (int)v27);
  if ( v25 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8C0,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\datacollection.cpp",
      (const char *)(unsigned int)v25,
      v28);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v4);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v41);
  CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&SecurityAttributes);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v30);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v43);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpPathName);
  return v4;
}

```

## disassembly

```asm
0x18008b3dc  push    rbp
0x18008b3de  push    rbx
0x18008b3df  push    rsi
0x18008b3e0  push    rdi
0x18008b3e1  push    r12
0x18008b3e3  push    r13
0x18008b3e5  push    r14
0x18008b3e7  push    r15
0x18008b3e9  lea     rbp, [rsp-1228h]
0x18008b3f1  mov     eax, 1328h
0x18008b3f6  call    _alloca_probe
0x18008b3fb  sub     rsp, rax
0x18008b3fe  mov     rax, cs:__security_cookie
0x18008b405  xor     rax, rsp
0x18008b408  mov     [rbp+1260h+var_50], rax
0x18008b40f  mov     rsi, rcx
0x18008b412  lea     rcx, [rsp+1360h+lpPathName]; void *
0x18008b417  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b41c  nop
0x18008b41d  lea     rcx, [rbp+1260h+lpFileName]; void *
0x18008b424  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b429  nop
0x18008b42a  lea     rcx, [rsp+1360h+lpExistingFileName]; void *
0x18008b42f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b434  nop
0x18008b435  lea     rcx, [rbp+1260h+var_1200]; void *
0x18008b439  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b43e  nop
0x18008b43f  lea     rcx, [rbp+1260h+var_1220]; void *
0x18008b443  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b448  nop
0x18008b449  xor     r15d, r15d
0x18008b44c  mov     word ptr [rbp+1260h+var_F70], r15w
0x18008b454  mov     ebx, 576h
0x18008b459  mov     r8d, ebx; Size
0x18008b45c  xor     edx, edx; Val
0x18008b45e  lea     rcx, [rbp+1260h+var_F70+2]; void *
0x18008b465  call    memset_0
0x18008b46a  mov     [rbp+1260h+var_9F0], r15w
0x18008b472  mov     r8d, ebx; Size
0x18008b475  xor     edx, edx; Val
0x18008b477  lea     rcx, [rbp+1260h+var_9EE]; void *
0x18008b47e  call    memset_0
0x18008b483  or      r14, 0FFFFFFFFFFFFFFFFh
0x18008b487  mov     [rbp+1260h+var_12D0], r14
0x18008b48b  xor     edx, edx; Val
0x18008b48d  mov     r8d, 250h; Size
0x18008b493  lea     rcx, [rbp+1260h+FindFileData]; void *
0x18008b49a  call    memset_0
0x18008b49f  lea     rcx, [rbp+1260h+var_12B8]; void *
0x18008b4a3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b4a8  nop
0x18008b4a9  mov     [rsp+1360h+var_1318], r15
0x18008b4ae  xorps   xmm0, xmm0
0x18008b4b1  xor     eax, eax
0x18008b4b3  movups  xmmword ptr [rbp+1260h+SecurityAttributes.nLength], xmm0
0x18008b4b7  mov     qword ptr [rbp+1260h+SecurityAttributes.bInheritHandle], rax
0x18008b4bb  xorps   xmm1, xmm1
0x18008b4be  movups  [rbp+1260h+var_1278], xmm1
0x18008b4c2  movups  [rbp+1260h+var_1268], xmm1
0x18008b4c6  mov     [rbp+1260h+var_1258], rax
0x18008b4ca  movdqa  [rbp+1260h+var_1250], xmm0
0x18008b4cf  mov     [rbp+1260h+SecurityAttributes.nLength], 18h
0x18008b4d6  lea     rcx, [rbp+1260h+var_1240]; void *
0x18008b4da  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b4df  nop
0x18008b4e0  lea     r12, WPP_GLOBAL_Control
0x18008b4e7  lea     r13, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008b4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b4f5  cmp     rcx, r12
0x18008b4f8  jz      short loc_18008B517
0x18008b4fa  test    byte ptr [rcx+1Ch], 4
0x18008b4fe  jz      short loc_18008B517
0x18008b500  lea     edx, [r15+41h]
0x18008b504  mov     r8, r13
0x18008b507  mov     rcx, [rcx+10h]
0x18008b50b  call    WPP_SF_
0x18008b510  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b517  cmp     [rsi], r15
0x18008b51a  jnz     short loc_18008B541
0x18008b51c  mov     ebx, 80070057h
0x18008b521  cmp     rcx, r12
0x18008b524  jz      loc_18008BDB1
0x18008b52a  test    byte ptr [rcx+1Ch], 1
0x18008b52e  jz      loc_18008BDB1
0x18008b534  mov     edx, 42h ; 'B'
0x18008b539  mov     r9d, ebx
0x18008b53c  jmp     loc_18008BDA5
0x18008b541  mov     edx, 104h
0x18008b546  lea     rcx, [rbp+1260h+var_260]
0x18008b54d  call    WerpGetPathOfWERTempDirectory
0x18008b552  mov     ebx, eax
0x18008b554  test    eax, eax
0x18008b556  jns     short loc_18008B57C
0x18008b558  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b55f  cmp     rcx, r12
0x18008b562  jz      loc_18008BDB1
0x18008b568  test    byte ptr [rcx+1Ch], 1
0x18008b56c  jz      loc_18008BDB1
0x18008b572  mov     edx, 43h ; 'C'
0x18008b577  jmp     loc_18008BDA2
0x18008b57c  lea     rdx, [rbp+1260h+var_12B8]
0x18008b580  mov     rcx, [rsi]
0x18008b583  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008b588  mov     ebx, eax
0x18008b58a  test    eax, eax
0x18008b58c  jns     short loc_18008B5B2
0x18008b58e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b595  cmp     rcx, r12
0x18008b598  jz      loc_18008BDB1
0x18008b59e  test    byte ptr [rcx+1Ch], 1
0x18008b5a2  jz      loc_18008BDB1
0x18008b5a8  mov     edx, 44h ; 'D'
0x18008b5ad  jmp     loc_18008BDA2
0x18008b5b2  mov     r9, [rbp+1260h+var_12B8]
0x18008b5b6  lea     r8, [rbp+1260h+var_260]
0x18008b5bd  lea     rdx, aWsWs_0; "%ws\\%ws"
0x18008b5c4  lea     rcx, [rsp+1360h+lpPathName]
0x18008b5c9  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008b5ce  mov     ebx, eax
0x18008b5d0  test    eax, eax
0x18008b5d2  jns     short loc_18008B5F8
0x18008b5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b5db  cmp     rcx, r12
0x18008b5de  jz      loc_18008BDB1
0x18008b5e4  test    byte ptr [rcx+1Ch], 1
0x18008b5e8  jz      loc_18008BDB1
0x18008b5ee  mov     edx, 45h ; 'E'
0x18008b5f3  jmp     loc_18008BDA2
0x18008b5f8  xor     edx, edx; bool
0x18008b5fa  lea     rcx, [rbp+1260h+SecurityAttributes]; this
0x18008b5fe  call    ?GetNewRestrictedFileOrDirectorySecurityAttributes@CSecurityAttributes@@SAJAEAV1@_N@Z; CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(CSecurityAttributes &,bool)
0x18008b603  mov     ebx, eax
0x18008b605  test    eax, eax
0x18008b607  jns     short loc_18008B62D
0x18008b609  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b610  cmp     rcx, r12
0x18008b613  jz      loc_18008BDB1
0x18008b619  test    byte ptr [rcx+1Ch], 1
0x18008b61d  jz      loc_18008BDB1
0x18008b623  mov     edx, 46h ; 'F'
0x18008b628  jmp     loc_18008BDA2
0x18008b62d  lea     rdx, [rbp+1260h+SecurityAttributes]; lpSecurityAttributes
0x18008b631  mov     rcx, [rsp+1360h+lpPathName]; lpPathName
0x18008b636  call    cs:__imp_CreateDirectoryW
0x18008b63c  test    eax, eax
0x18008b63e  jnz     short loc_18008B673
0x18008b640  call    cs:__imp_GetLastError
0x18008b646  mov     ecx, eax; unsigned int
0x18008b648  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008b64d  mov     ebx, eax
0x18008b64f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b656  cmp     rcx, r12
0x18008b659  jz      loc_18008BDB1
0x18008b65f  test    byte ptr [rcx+1Ch], 1
0x18008b663  jz      loc_18008BDB1
0x18008b669  mov     edx, 47h ; 'G'
0x18008b66e  jmp     loc_18008BDA2
0x18008b673  mov     edi, 10000000h
0x18008b678  mov     edx, edi; unsigned int
0x18008b67a  mov     rcx, [rsp+1360h+lpPathName]; wchar_t *
0x18008b67f  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x18008b684  test    eax, eax
0x18008b686  jns     short loc_18008B6AE
0x18008b688  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b68f  cmp     rcx, r12
0x18008b692  jz      short loc_18008B6AE
0x18008b694  test    byte ptr [rcx+1Ch], 2
0x18008b698  jz      short loc_18008B6AE
0x18008b69a  mov     edx, 48h ; 'H'
0x18008b69f  mov     r9d, eax
0x18008b6a2  mov     r8, r13
0x18008b6a5  mov     rcx, [rcx+10h]
0x18008b6a9  call    WPP_SF_d
0x18008b6ae  mov     [rbp+1260h+var_F70], 5780550h
0x18008b6b8  mov     [rbp+1260h+var_F48], 0F0010002h
0x18008b6c2  mov     r8, [rbp+1260h+var_12B8]; wchar_t *
0x18008b6c6  mov     edx, 104h; unsigned __int64
0x18008b6cb  lea     rcx, [rbp+1260h+var_F40]; wchar_t *
0x18008b6d2  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18008b6d7  test    eax, eax
0x18008b6d9  jns     short loc_18008B708
0x18008b6db  mov     r9d, 800700CEh
0x18008b6e1  mov     ebx, r9d
0x18008b6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b6eb  cmp     rcx, r12
0x18008b6ee  jz      loc_18008BDB1
0x18008b6f4  test    byte ptr [rcx+1Ch], 1
0x18008b6f8  jz      loc_18008BDB1
0x18008b6fe  mov     edx, 49h ; 'I'
0x18008b703  jmp     loc_18008BDA5
0x18008b708  mov     r9d, 0EA60h; unsigned int
0x18008b70e  lea     r8, [rbp+1260h+var_9F0]; struct _WERSVC_MSG *
0x18008b715  lea     rdx, [rbp+1260h+var_F70]; struct _WERSVC_MSG *
0x18008b71c  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18008b721  mov     ebx, eax
0x18008b723  test    eax, eax
0x18008b725  jns     short loc_18008B74B
0x18008b727  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b72e  cmp     rcx, r12
0x18008b731  jz      loc_18008BDB1
0x18008b737  test    byte ptr [rcx+1Ch], 1
0x18008b73b  jz      loc_18008BDB1
0x18008b741  mov     edx, 4Ah ; 'J'
0x18008b746  jmp     loc_18008BDA2
0x18008b74b  cmp     [rbp+1260h+var_9C8], 0F0010000h
0x18008b755  jz      short loc_18008B7C4
0x18008b757  cmp     [rbp+1260h+var_7B8], r15d
0x18008b75e  jnz     short loc_18008B79B
0x18008b760  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b767  cmp     rcx, r12
0x18008b76a  jz      short loc_18008B794
0x18008b76c  test    byte ptr [rcx+1Ch], 2
0x18008b770  jz      short loc_18008B794
0x18008b772  mov     r9d, [rbp+1260h+var_9C4]
0x18008b779  or      r9d, edi
0x18008b77c  mov     edx, 4Bh ; 'K'
0x18008b781  mov     r8, r13
0x18008b784  mov     rcx, [rcx+10h]
0x18008b788  call    WPP_SF_d
0x18008b78d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b794  mov     ebx, 1
0x18008b799  jmp     short loc_18008B7A7
0x18008b79b  mov     ebx, 80004005h
0x18008b7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b7a7  cmp     rcx, r12
0x18008b7aa  jz      loc_18008BDB1
0x18008b7b0  test    byte ptr [rcx+1Ch], 1
0x18008b7b4  jz      loc_18008BDB1
0x18008b7ba  mov     edx, 4Ch ; 'L'
0x18008b7bf  jmp     loc_18008B539
0x18008b7c4  lea     rdx, [rsp+1360h+var_1318]
0x18008b7c9  mov     rcx, [rsp+1360h+lpPathName]; wchar_t *
0x18008b7ce  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x18008b7d3  mov     ebx, eax
0x18008b7d5  test    eax, eax
0x18008b7d7  jns     short loc_18008B812
0x18008b7d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b7e0  cmp     rcx, r12
0x18008b7e3  jz      loc_18008BDB1
0x18008b7e9  test    byte ptr [rcx+1Ch], 1
0x18008b7ed  jz      loc_18008BDB1
0x18008b7f3  mov     edx, 4Dh ; 'M'
0x18008b7f8  mov     dword ptr [rsp+1360h+var_1340], eax
0x18008b7fc  mov     r9, [rsp+1360h+lpPathName]
0x18008b801  mov     r8, r13
0x18008b804  mov     rcx, [rcx+10h]
0x18008b808  call    WPP_SF_Sd
0x18008b80d  jmp     loc_18008BDB1
0x18008b812  mov     r8, [rsp+1360h+lpPathName]
0x18008b817  lea     rdx, aSEtl; "%s\\*etl"
0x18008b81e  lea     rcx, [rbp+1260h+lpFileName]
0x18008b825  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008b82a  mov     ebx, eax
0x18008b82c  test    eax, eax
0x18008b82e  jns     short loc_18008B854
0x18008b830  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b837  cmp     rcx, r12
0x18008b83a  jz      loc_18008BDB1
0x18008b840  test    byte ptr [rcx+1Ch], 1
0x18008b844  jz      loc_18008BDB1
0x18008b84a  mov     edx, 4Eh ; 'N'
0x18008b84f  jmp     loc_18008BDA2
0x18008b854  lea     rdx, [rbp+1260h+FindFileData]; lpFindFileData
0x18008b85b  mov     rcx, [rbp+1260h+lpFileName]; lpFileName
0x18008b862  call    cs:__imp_FindFirstFileW
0x18008b868  mov     r14, rax
0x18008b86b  mov     [rbp+1260h+var_12D0], rax
0x18008b86f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008b873  jz      loc_18008BD7C
0x18008b879  xor     edx, edx; dwFlags
0x18008b87b  mov     r8d, 208h; dwBytes
0x18008b881  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18008b888  call    cs:__imp_HeapAlloc
0x18008b88e  mov     rdi, rax
0x18008b891  test    rax, rax
0x18008b894  jz      short loc_18008B8A8
0x18008b896  xor     edx, edx; Val
0x18008b898  mov     r8d, 208h; Size
0x18008b89e  mov     rcx, rax; void *
0x18008b8a1  call    memset_0
0x18008b8a6  jmp     short loc_18008B8AB
0x18008b8a8  mov     rdi, r15
0x18008b8ab  mov     [rsp+1360h+var_1320], rdi
0x18008b8b0  test    rdi, rdi
0x18008b8b3  jz      loc_18008BD43
0x18008b8b9  lea     r9, [rbp+1260h+FindFileData.cFileName]
0x18008b8c0  mov     r8, [rsp+1360h+lpPathName]
0x18008b8c5  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18008b8cc  lea     rcx, [rsp+1360h+lpExistingFileName]
0x18008b8d1  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008b8d6  mov     ebx, eax
0x18008b8d8  test    eax, eax
0x18008b8da  js      loc_18008BD27
0x18008b8e0  mov     [rsp+1360h+var_1328], r15d
0x18008b8e5  mov     dword ptr [rsp+1360h+var_1330], r15d
0x18008b8ea  lea     rax, [rbp+1260h+SecurityAttributes]
0x18008b8ee  mov     [rsp+1360h+var_1338], rax
0x18008b8f3  lea     r9, [rbp+1260h+NewFileName]
0x18008b8fa  lea     r8, aEtl; ".etl"
  ... truncated ...
```
