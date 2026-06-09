# CbsDirectoryTreeWalk

- ea: `0x180049d2c`
- end: `0x18004a8fd`
- name: `CbsDirectoryTreeWalk`
- size: `3025`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180042b60`
- `0x180048a10`

## callees

- `0x18001e51c`
- `0x180022d80`
- `0x1800293a0`
- `0x18002a208`
- `0x180041a74`
- `0x180041c30`
- `0x180041de8`
- `0x18004255c`
- `0x1800442a0`
- `0x180044bcc`
- `0x1800467ac`
- `0x180046ae8`
- `0x180046f48`
- `0x180047000`
- `0x180047fa0`
- `0x18004816c`
- `0x1800496e8`
- `0x180049d2c`
- `0x18004c660`
- `0x18004c9e0`
- `0x18004d3a0`
- `0x18004d850`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x18004a218`
- `KERNEL32!FindFirstFileW` at `0x18004a218`
- `KERNEL32!FindNextFileW` at `0x18004a34a`
- `KERNEL32!FindNextFileW` at `0x18004a34a`

## string_xrefs

- `0x18004a50e`: `Unable to complete 'begin' directory callback`
- `0x180049dd4`: `No directory specified`
- `0x180049ee9`: `Failed adding top level directory to stack`
- `0x18004a83b`: `Failed popping next directory from stack`
- `0x18004a47f`: `Failed finding parent directory`
- `0x18004a5dd`: `Failed 'begin' directory callback`
- `0x18004a112`: `Failed 'end' directory callback`
- `0x18004a1b4`: `Failed 'end' directory callback`
- `0x18004a6bc`: `Failed 'end' directory callback`
- `0x18004a2d3`: `Failed adding directory: {} to stack`

## pseudocode

```c
__int64 __fastcall CbsDirectoryTreeWalk(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 (__fastcall *a4)(_QWORD, wchar_t *, wchar_t *, __int64),
        __int64 (__fastcall *a5)(wchar_t *, struct _WIN32_FIND_DATAW *, __int64),
        __int64 (__fastcall *a6)(__int64, __int64, __int64))
{
  __int64 v6; // r14
  __int64 v9; // rsi
  signed int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v15; // eax
  signed int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r12
  wchar_t *v19; // rax
  unsigned __int64 v20; // rcx
  int v21; // eax
  unsigned __int64 v22; // rcx
  wchar_t *v23; // r10
  wchar_t *v24; // r11
  __int64 (__fastcall *v25)(_QWORD, wchar_t *, wchar_t *, __int64); // rax
  signed int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  signed int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  HANDLE FirstFileW; // rax
  int v33; // edx
  HANDLE v34; // rbx
  int v35; // eax
  signed int v36; // eax
  int v37; // edx
  int v38; // r8d
  __int64 v39; // rdx
  unsigned __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  unsigned int v44; // eax
  __int64 v45; // rcx
  signed int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  unsigned __int64 v52; // r9
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  int v57; // [rsp+20h] [rbp-E0h]
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  int v59[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v60; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v61[6]; // [rsp+48h] [rbp-B8h] BYREF
  char v62; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v63)(wchar_t *, struct _WIN32_FIND_DATAW *, __int64); // [rsp+80h] [rbp-80h]
  __int64 v64; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall *v65)(_QWORD, wchar_t *, wchar_t *, __int64); // [rsp+90h] [rbp-70h] BYREF
  unsigned int v66; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v67; // [rsp+9Ch] [rbp-64h] BYREF
  wchar_t *Str; // [rsp+A0h] [rbp-60h] BYREF
  int v69; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v70[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v71[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v72; // [rsp+D8h] [rbp-28h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  v6 = 0;
  v64 = a3;
  v63 = a5;
  Str = 0;
  v60 = 0;
  LODWORD(v9) = 0;
  v65 = a4;
  memset(&FindFileData, 0, sizeof(FindFileData));
  CCbsDirStack::CCbsDirStack((CCbsDirStack *)v71);
  v70[0] = 0;
  v69 = 0;
  v67 = 0;
  v66 = 0;
  if ( !a1 )
  {
    v10 = -2147024809;
    v66 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No directory specified");
      hFindFile = &v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v11,
        3,
        (__int64)": {}",
        (__int64)&hFindFile);
    }
    v12 = 2147942487LL;
    v13 = 28;
    goto LABEL_12;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
    v66 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No search pattern specified");
      hFindFile = &v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v14,
        3,
        (__int64)": {}",
        (__int64)&hFindFile);
    }
    v12 = 2147942487LL;
    v13 = 29;
    goto LABEL_12;
  }
  v15 = SczAllocFromSz(&Str, a1);
  v10 = v15;
  if ( v15 < 0 )
  {
    v13 = 35;
LABEL_11:
    v12 = (unsigned int)v15;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
      (const char *)v12,
      v57);
    goto LABEL_125;
  }
  v15 = SczEnsureBackslashTerminated(&Str);
  v10 = v15;
  if ( v15 < 0 )
  {
    v13 = 36;
    goto LABEL_11;
  }
  v16 = CCbsDirStack::Push((CCbsDirStack *)v71, L".", 0);
  v10 = v16;
  if ( v16 < 0 )
  {
    v66 = v16;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding top level directory to stack");
      hFindFile = &v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v17,
        3,
        (__int64)": {}",
        (__int64)&hFindFile);
    }
    v12 = (unsigned int)v10;
    v13 = 37;
    goto LABEL_12;
  }
  v62 = 1;
  v61[0] = &v65;
  v18 = 0;
  v61[1] = &v69;
  v61[2] = &v67;
  v61[3] = &Str;
  v61[4] = v70;
  v61[5] = &v64;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v72 )
        goto LABEL_89;
      hFindFile = 0;
      v10 = CCbsDirStack::Pop((CCbsDirStack *)v71, v70, &v66);
      if ( v10 < 0 )
      {
        v66 = v10;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed popping next directory from stack");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v55,
            3,
            (__int64)": {}",
            (__int64)v59);
        }
        v28 = 52;
        goto LABEL_120;
      }
      if ( *v70[0] != 46 || v70[0][1] != 46 || v70[0][2] )
        break;
      if ( !v72 || !(_DWORD)v9 )
      {
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
LABEL_89:
        if ( !a6 || !v6 || (v46 = a6(v6, v6, v64), v10 = v46, v46 >= 0) )
        {
          v62 = 0;
          CbsDirectoryTreeWalk_::_2_::_lambda_1_::operator()(v61);
          v10 = 0;
          goto LABEL_125;
        }
        v66 = v46;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed progress callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v47,
            3,
            (__int64)": {}",
            (__int64)v59);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD0,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
          (const char *)(unsigned int)v10,
          v57);
LABEL_122:
        v62 = 0;
        goto LABEL_123;
      }
      --v67;
      Str[(unsigned int)(v9 - 1)] = 0;
      v19 = wcsrchr(Str, 0x5Cu);
      if ( !v19 )
      {
        v10 = -2147024809;
        v66 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed finding parent directory");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v43,
            3,
            (__int64)": {}",
            (__int64)v59);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
          (const char *)0x80070057LL,
          v57);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
        if ( v65 && v69 )
        {
          v44 = ((__int64 (__fastcall *)(_QWORD, wchar_t *, wchar_t *, __int64, _DWORD))v65)(v67, Str, v70[0], v64, 0);
          LogAdapter::TraceAtLevelIfFailed<long,>(v45, v44, "Unable to complete 'begin' directory callback");
        }
        goto LABEL_125;
      }
      v19[1] = 0;
      v20 = -1;
      do
        ++v20;
      while ( Str[v20] );
      v10 = ULongLongToULong(v20, &v60);
      if ( v10 < 0 )
      {
        v66 = v10;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert size_t to DWORD");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v42,
            3,
            (__int64)": {}",
            (__int64)v59);
        }
        v28 = 75;
LABEL_120:
        v52 = (unsigned int)v10;
        goto LABEL_121;
      }
LABEL_31:
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
      LODWORD(v9) = v60;
    }
    ++v67;
    v10 = CCbsDirStack::Push((CCbsDirStack *)v71, L"..", 0);
    if ( v10 < 0 )
    {
      v66 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed pushing parent delimiter");
        *(_QWORD *)v59 = &v66;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v54,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v28 = 81;
      goto LABEL_120;
    }
    if ( *v70[0] != 46 || v70[0][1] )
    {
      v21 = SczAllocConcat2Sz(&Str, v70[0], L"\\");
      v10 = v21;
      if ( v21 < 0 )
      {
        v52 = (unsigned int)v21;
        v28 = 85;
        goto LABEL_121;
      }
    }
    v22 = -1;
    do
      ++v22;
    while ( Str[v22] );
    v10 = ULongLongToULong(v22, &v60);
    if ( v10 < 0 )
    {
      v66 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert size_t to DWORD");
        *(_QWORD *)v59 = &v66;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v53,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v28 = 88;
      goto LABEL_120;
    }
    v25 = v65;
    if ( v65 )
    {
      v57 = 1;
      v10 = v65(v67, v24, v23, v64);
      if ( v10 < 0 )
      {
        v66 = v10;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed 'begin' directory callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v48,
            3,
            (__int64)": {}",
            (__int64)v59);
        }
        v28 = 93;
        goto LABEL_120;
      }
      v25 = v65;
      if ( v10 == 1 )
      {
        v57 = 0;
        v26 = v65(v67, Str, v70[0], v64);
        v10 = v26;
        if ( v26 >= 0 )
          goto LABEL_31;
        v66 = v26;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed 'end' directory callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v27,
            3,
            (__int64)": {}",
            (__int64)v59);
        }
        v28 = 99;
        goto LABEL_120;
      }
      v24 = Str;
      v23 = v70[0];
      v69 = 1;
    }
    if ( (v66 & 0x400) != 0 )
    {
      if ( !v25 )
        goto LABEL_31;
      v69 = 0;
      v57 = 0;
      v29 = v25(v67, v24, v23, v64);
      v10 = v29;
      if ( v29 >= 0 )
        goto LABEL_31;
      v66 = v29;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed 'end' directory callback");
        *(_QWORD *)v59 = &v66;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v30,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v28 = 117;
      goto LABEL_120;
    }
    v31 = SczAllocConcatSz(&Str, a2);
    v10 = v31;
    if ( v31 < 0 )
    {
      v52 = (unsigned int)v31;
      v28 = 126;
LABEL_121:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
        (const char *)v52,
        v57);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
      goto LABEL_122;
    }
    FirstFileW = FindFirstFileW(Str, &FindFileData);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &hFindFile,
      FirstFileW);
    v34 = hFindFile;
    v9 = v60;
    if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      break;
    *(_QWORD *)v59 = Str;
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v33) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t *>(
        (_DWORD)LogAdapter::g_Logger,
        v33,
        1,
        (unsigned int)"Unable to find search pattern: {}",
        (__int64)v59);
    }
LABEL_73:
    Str[v9] = 0;
    if ( v65 )
    {
      v69 = 0;
      v57 = 0;
      v10 = v65(v67, Str, v70[0], v64);
      if ( v10 < 0 )
      {
        v66 = v10;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed 'end' directory callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v50,
            3,
            (__int64)": {}",
            (__int64)v59);
        }
        v28 = 189;
        goto LABEL_120;
      }
    }
    if ( v67 == 2 )
    {
      ++v18;
      if ( a6 )
      {
        if ( v6 )
        {
          v10 = a6(v18, v6, v64);
          if ( v10 < 0 )
          {
            v66 = v10;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed progress callback");
              *(_QWORD *)v59 = &v66;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v51,
                3,
                (__int64)": {}",
                (__int64)v59);
            }
            v28 = 201;
            goto LABEL_120;
          }
        }
      }
    }
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
  }
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_69;
    }
    Str[v9] = 0;
    v35 = SczAllocConcatSz(&Str, FindFileData.cFileName);
    v10 = v35;
    if ( v35 < 0 )
    {
      v40 = (unsigned int)v35;
      v41 = 148;
      goto LABEL_102;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    if ( v67 == 1 )
      ++v6;
    v36 = CCbsDirStack::Push((CCbsDirStack *)v71, FindFileData.cFileName, FindFileData.dwFileAttributes);
    v10 = v36;
    if ( v36 < 0 )
    {
      v66 = v36;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t [260]>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          v38,
          (unsigned int)"Failed adding directory: {} to stack",
          (__int64)FindFileData.cFileName);
        *(_QWORD *)v59 = &v66;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v39,
          3,
          (__int64)": {}",
          (__int64)v59);
      }
      v40 = (unsigned int)v10;
      v41 = 164;
      goto LABEL_102;
    }
LABEL_69:
    if ( !FindNextFileW(v34, &FindFileData) )
      goto LABEL_73;
  }
  if ( !v63 )
    goto LABEL_69;
  v10 = v63(Str, &FindFileData, v64);
  if ( v10 >= 0 )
    goto LABEL_69;
  v66 = v10;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed file callback");
    *(_QWORD *)v59 = &v66;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v49,
      3,
      (__int64)": {}",
      (__int64)v59);
  }
  v40 = (unsigned int)v10;
  v41 = 170;
LABEL_102:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v41,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
    (const char *)v40,
    v57);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(&hFindFile);
  v62 = 0;
LABEL_123:
  CbsDirectoryTreeWalk_::_2_::_lambda_1_::operator()(v61);
LABEL_125:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v70);
  CCbsDirStack::~CCbsDirStack((CCbsDirStack *)v71);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180049d2c  push    rbp
0x180049d2e  push    rbx
0x180049d2f  push    rsi
0x180049d30  push    rdi
0x180049d31  push    r12
0x180049d33  push    r13
0x180049d35  push    r14
0x180049d37  push    r15
0x180049d39  lea     rbp, [rsp-2A8h]
0x180049d41  sub     rsp, 3A8h
0x180049d48  mov     rax, cs:__security_cookie
0x180049d4f  xor     rax, rsp
0x180049d52  mov     [rbp+2E0h+var_50], rax
0x180049d59  mov     rax, [rbp+2E0h+arg_20]
0x180049d60  xor     r14d, r14d
0x180049d63  mov     r15, [rbp+2E0h+arg_28]
0x180049d6a  mov     r13, rdx
0x180049d6d  mov     rbx, rcx
0x180049d70  mov     [rbp+2E0h+var_358], r8
0x180049d74  xor     edx, edx; Val
0x180049d76  mov     [rbp+2E0h+var_360], rax
0x180049d7a  mov     r8d, 250h; Size
0x180049d80  mov     [rbp+2E0h+Str], r14
0x180049d84  lea     rcx, [rbp+2E0h+FindFileData]; void *
0x180049d88  mov     [rsp+3E0h+var_3A0], r14d
0x180049d8d  mov     esi, r14d
0x180049d90  mov     [rbp+2E0h+var_350], r9
0x180049d94  call    memset
0x180049d99  lea     rcx, [rbp+2E0h+var_320]; this
0x180049d9d  call    ??0CCbsDirStack@@QEAA@XZ; CCbsDirStack::CCbsDirStack(void)
0x180049da2  mov     [rbp+2E0h+var_330], r14
0x180049da6  mov     [rbp+2E0h+var_338], r14d
0x180049daa  mov     [rbp+2E0h+var_344], r14d
0x180049dae  mov     [rbp+2E0h+var_348], r14d
0x180049db2  test    rbx, rbx
0x180049db5  jnz     short loc_180049E13
0x180049db7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049dbe  mov     edi, 80070057h
0x180049dc3  mov     [rbp+2E0h+var_348], edi
0x180049dc6  test    rcx, rcx
0x180049dc9  jz      short loc_180049E09
0x180049dcb  lea     ebx, [r14+3]
0x180049dcf  xor     edx, edx
0x180049dd1  mov     r8d, ebx
0x180049dd4  lea     r9, aNoDirectorySpe; "No directory specified"
0x180049ddb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180049de0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049de7  lea     rax, [rbp+2E0h+var_348]
0x180049deb  mov     [rsp+3E0h+hFindFile], rax
0x180049df0  lea     r9, asc_1800AFB70; ": {}"
0x180049df7  lea     rax, [rsp+3E0h+hFindFile]
0x180049dfc  mov     r8d, ebx
0x180049dff  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x180049e04  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180049e09  mov     r9d, edi
0x180049e0c  mov     edx, 1Ch
0x180049e11  jmp     short loc_180049E8E
0x180049e13  test    r13, r13
0x180049e16  jnz     short loc_180049E74
0x180049e18  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049e1f  mov     edi, 80070057h
0x180049e24  mov     [rbp+2E0h+var_348], edi
0x180049e27  test    rcx, rcx
0x180049e2a  jz      short loc_180049E6A
0x180049e2c  lea     ebx, [r13+3]
0x180049e30  xor     edx, edx
0x180049e32  mov     r8d, ebx
0x180049e35  lea     r9, aNoSearchPatter; "No search pattern specified"
0x180049e3c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180049e41  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049e48  lea     rax, [rbp+2E0h+var_348]
0x180049e4c  mov     [rsp+3E0h+hFindFile], rax
0x180049e51  lea     r9, asc_1800AFB70; ": {}"
0x180049e58  lea     rax, [rsp+3E0h+hFindFile]
0x180049e5d  mov     r8d, ebx
0x180049e60  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x180049e65  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180049e6a  mov     r9d, edi
0x180049e6d  mov     edx, 1Dh
0x180049e72  jmp     short loc_180049E8E
0x180049e74  mov     rdx, rbx
0x180049e77  lea     rcx, [rbp+2E0h+Str]
0x180049e7b  call    SczAllocFromSz
0x180049e80  xor     ebx, ebx
0x180049e82  mov     edi, eax
0x180049e84  test    eax, eax
0x180049e86  jns     short loc_180049EA6
0x180049e88  lea     edx, [rbx+23h]; void *
0x180049e8b  mov     r9d, eax; char *
0x180049e8e  mov     rcx, [rbp+2E8h]; this
0x180049e95  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x180049e9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049ea1  jmp     loc_18004A8BC
0x180049ea6  lea     rcx, [rbp+2E0h+Str]
0x180049eaa  call    SczEnsureBackslashTerminated
0x180049eaf  mov     edi, eax
0x180049eb1  test    eax, eax
0x180049eb3  jns     short loc_180049EBC
0x180049eb5  mov     edx, 24h ; '$'
0x180049eba  jmp     short loc_180049E8B
0x180049ebc  xor     r8d, r8d; unsigned int
0x180049ebf  lea     rdx, asc_1800B0D58; "."
0x180049ec6  lea     rcx, [rbp+2E0h+var_320]; this
0x180049eca  call    ?Push@CCbsDirStack@@QEAAJPEB_WK@Z; CCbsDirStack::Push(wchar_t const *,ulong)
0x180049ecf  mov     edi, eax
0x180049ed1  test    eax, eax
0x180049ed3  jns     short loc_180049F30
0x180049ed5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049edc  mov     [rbp+2E0h+var_348], eax
0x180049edf  test    rcx, rcx
0x180049ee2  jz      short loc_180049F23
0x180049ee4  mov     ebx, 3
0x180049ee9  lea     r9, aFailedAddingTo; "Failed adding top level directory to st"...
0x180049ef0  mov     r8d, ebx
0x180049ef3  xor     edx, edx
0x180049ef5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180049efa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049f01  lea     rax, [rbp+2E0h+var_348]
0x180049f05  mov     [rsp+3E0h+hFindFile], rax
0x180049f0a  lea     r9, asc_1800AFB70; ": {}"
0x180049f11  lea     rax, [rsp+3E0h+hFindFile]
0x180049f16  mov     r8d, ebx
0x180049f19  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x180049f1e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180049f23  mov     r9d, edi
0x180049f26  mov     edx, 25h ; '%'
0x180049f2b  jmp     loc_180049E8E
0x180049f30  lea     rax, [rbp+2E0h+var_350]
0x180049f34  mov     [rsp+3E0h+var_368], 1
0x180049f39  mov     [rsp+3E0h+var_398], rax
0x180049f3e  mov     r12, rbx
0x180049f41  lea     rax, [rbp+2E0h+var_338]
0x180049f45  mov     [rsp+3E0h+var_390], rax
0x180049f4a  lea     rax, [rbp+2E0h+var_344]
0x180049f4e  mov     [rsp+3E0h+var_388], rax
0x180049f53  lea     rax, [rbp+2E0h+Str]
0x180049f57  mov     [rsp+3E0h+var_380], rax
0x180049f5c  lea     rax, [rbp+2E0h+var_330]
0x180049f60  mov     [rsp+3E0h+var_378], rax
0x180049f65  lea     rax, [rbp+2E0h+var_358]
0x180049f69  mov     [rsp+3E0h+var_370], rax
0x180049f6e  cmp     [rbp+2E0h+var_308], rbx
0x180049f72  jz      loc_18004A52B
0x180049f78  lea     r8, [rbp+2E0h+var_348]; unsigned int *
0x180049f7c  mov     [rsp+3E0h+hFindFile], rbx
0x180049f81  lea     rdx, [rbp+2E0h+var_330]; wchar_t **
0x180049f85  lea     rcx, [rbp+2E0h+var_320]; this
0x180049f89  call    ?Pop@CCbsDirStack@@QEAAJPEAPEA_WPEAK@Z; CCbsDirStack::Pop(wchar_t * *,ulong *)
0x180049f8e  mov     edi, eax
0x180049f90  test    eax, eax
0x180049f92  js      loc_18004A827
0x180049f98  mov     rcx, [rbp+2E0h+var_330]
0x180049f9c  mov     eax, 2Eh ; '.'
0x180049fa1  cmp     ax, [rcx]
0x180049fa4  jnz     short loc_18004A025
0x180049fa6  cmp     ax, [rcx+2]
0x180049faa  jnz     short loc_18004A025
0x180049fac  cmp     bx, [rcx+4]
0x180049fb0  jnz     short loc_18004A025
0x180049fb2  cmp     [rbp+2E0h+var_308], rbx
0x180049fb6  jz      loc_18004A521
0x180049fbc  test    esi, esi
0x180049fbe  jz      loc_18004A521
0x180049fc4  mov     rax, [rbp+2E0h+Str]
0x180049fc8  lea     edx, [rsi-1]
0x180049fcb  dec     [rbp+2E0h+var_344]
0x180049fce  mov     [rax+rdx*2], bx
0x180049fd2  mov     edx, 5Ch ; '\'; Ch
0x180049fd7  mov     rcx, [rbp+2E0h+Str]; Str
0x180049fdb  call    wcsrchr
0x180049fe0  test    rax, rax
0x180049fe3  jz      loc_18004A466
0x180049fe9  mov     [rax+2], bx
0x180049fed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180049ff1  mov     rax, [rbp+2E0h+Str]
0x180049ff5  inc     rcx; unsigned __int64
0x180049ff8  cmp     [rax+rcx*2], bx
0x180049ffc  jnz     short loc_180049FF5
0x180049ffe  lea     rdx, [rsp+3E0h+var_3A0]; unsigned int *
0x18004a003  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004a008  mov     edi, eax
0x18004a00a  test    eax, eax
0x18004a00c  js      loc_18004A40C
0x18004a012  lea     rcx, [rsp+3E0h+hFindFile]
0x18004a017  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x18004a01c  mov     esi, [rsp+3E0h+var_3A0]
0x18004a020  jmp     loc_180049F6E
0x18004a025  inc     [rbp+2E0h+var_344]
0x18004a028  lea     rdx, PathName; ".."
0x18004a02f  xor     r8d, r8d; unsigned int
0x18004a032  lea     rcx, [rbp+2E0h+var_320]; this
0x18004a036  call    ?Push@CCbsDirStack@@QEAAJPEB_WK@Z; CCbsDirStack::Push(wchar_t const *,ulong)
0x18004a03b  mov     edi, eax
0x18004a03d  test    eax, eax
0x18004a03f  js      loc_18004A7D0
0x18004a045  mov     r10, [rbp+2E0h+var_330]
0x18004a049  mov     eax, 2Eh ; '.'
0x18004a04e  cmp     [r10], ax
0x18004a052  jnz     short loc_18004A05B
0x18004a054  cmp     [r10+2], bx
0x18004a059  jz      short loc_18004A07C
0x18004a05b  lea     r8, asc_1800AEE08; "\\"
0x18004a062  mov     rdx, r10
0x18004a065  lea     rcx, [rbp+2E0h+Str]
0x18004a069  call    SczAllocConcat2Sz
0x18004a06e  mov     edi, eax
0x18004a070  test    eax, eax
0x18004a072  js      loc_18004A7C3
0x18004a078  mov     r10, [rbp+2E0h+var_330]
0x18004a07c  mov     r11, [rbp+2E0h+Str]
0x18004a080  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004a084  inc     rcx; unsigned __int64
0x18004a087  cmp     [r11+rcx*2], bx
0x18004a08c  jnz     short loc_18004A084
0x18004a08e  lea     rdx, [rsp+3E0h+var_3A0]; unsigned int *
0x18004a093  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004a098  mov     edi, eax
0x18004a09a  test    eax, eax
0x18004a09c  js      loc_18004A769
0x18004a0a2  mov     rax, [rbp+2E0h+var_350]
0x18004a0a6  test    rax, rax
0x18004a0a9  jz      loc_18004A167
0x18004a0af  mov     r9, [rbp+2E0h+var_358]
0x18004a0b3  mov     r8, r10
0x18004a0b6  mov     ecx, [rbp+2E0h+var_344]
0x18004a0b9  mov     rdx, r11
0x18004a0bc  mov     [rsp+3E0h+var_3C0], 1; int
0x18004a0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0c9  mov     edi, eax
0x18004a0cb  test    eax, eax
0x18004a0cd  js      loc_18004A5C9
0x18004a0d3  mov     rax, [rbp+2E0h+var_350]
0x18004a0d7  cmp     edi, 1
0x18004a0da  jnz     short loc_18004A158
0x18004a0dc  mov     r9, [rbp+2E0h+var_358]
0x18004a0e0  mov     r8, [rbp+2E0h+var_330]
0x18004a0e4  mov     rdx, [rbp+2E0h+Str]
0x18004a0e8  mov     ecx, [rbp+2E0h+var_344]
0x18004a0eb  mov     [rsp+3E0h+var_3C0], ebx
0x18004a0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0f4  mov     edi, eax
0x18004a0f6  test    eax, eax
0x18004a0f8  jns     loc_18004A012
0x18004a0fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004a105  mov     [rbp+2E0h+var_348], eax
0x18004a108  test    rcx, rcx
0x18004a10b  jz      short loc_18004A14E
0x18004a10d  mov     ebx, 3
0x18004a112  lea     r9, aFailedEndDirec; "Failed 'end' directory callback"
0x18004a119  mov     r8d, ebx
0x18004a11c  xor     edx, edx
0x18004a11e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004a123  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004a12a  lea     rax, [rbp+2E0h+var_348]
0x18004a12e  mov     qword ptr [rsp+3E0h+var_3A8], rax
0x18004a133  lea     r9, asc_1800AFB70; ": {}"
0x18004a13a  lea     rax, [rsp+3E0h+var_3A8]
0x18004a13f  mov     r8d, ebx
0x18004a142  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18004a147  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004a14c  xor     ebx, ebx
0x18004a14e  mov     edx, 63h ; 'c'
0x18004a153  jmp     loc_18004A87C
0x18004a158  mov     r11, [rbp+2E0h+Str]
0x18004a15c  mov     r10, [rbp+2E0h+var_330]
0x18004a160  mov     [rbp+2E0h+var_338], 1
0x18004a167  test    [rbp+2E0h+var_348], 400h
0x18004a16e  jz      loc_18004A1FA
0x18004a174  test    rax, rax
0x18004a177  jz      loc_18004A012
0x18004a17d  mov     r9, [rbp+2E0h+var_358]
0x18004a181  mov     r8, r10
0x18004a184  mov     ecx, [rbp+2E0h+var_344]
0x18004a187  mov     rdx, r11
0x18004a18a  mov     [rbp+2E0h+var_338], ebx
0x18004a18d  mov     [rsp+3E0h+var_3C0], ebx
0x18004a191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a196  mov     edi, eax
0x18004a198  test    eax, eax
0x18004a19a  jns     loc_18004A012
0x18004a1a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004a1a7  mov     [rbp+2E0h+var_348], eax
0x18004a1aa  test    rcx, rcx
0x18004a1ad  jz      short loc_18004A1F0
0x18004a1af  mov     ebx, 3
0x18004a1b4  lea     r9, aFailedEndDirec; "Failed 'end' directory callback"
0x18004a1bb  mov     r8d, ebx
0x18004a1be  xor     edx, edx
0x18004a1c0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004a1c5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004a1cc  lea     rax, [rbp+2E0h+var_348]
0x18004a1d0  mov     qword ptr [rsp+3E0h+var_3A8], rax
0x18004a1d5  lea     r9, asc_1800AFB70; ": {}"
0x18004a1dc  lea     rax, [rsp+3E0h+var_3A8]
0x18004a1e1  mov     r8d, ebx
0x18004a1e4  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18004a1e9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004a1ee  xor     ebx, ebx
0x18004a1f0  mov     edx, 75h ; 'u'
0x18004a1f5  jmp     loc_18004A87C
  ... truncated ...
```
