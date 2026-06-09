# CbsDirectoryTreeWalk

- ea: `0x18004ce4c`
- end: `0x18004da1d`
- name: `CbsDirectoryTreeWalk`
- size: `3025`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044b34`
- `0x18004bb30`

## callees

- `0x180020440`
- `0x180026c90`
- `0x18002d2b0`
- `0x18002e118`
- `0x180046650`
- `0x1800468fc`
- `0x180046ca4`
- `0x18004728c`
- `0x1800473d4`
- `0x180047d5c`
- `0x1800498dc`
- `0x180049c18`
- `0x18004a078`
- `0x18004a130`
- `0x18004b0c0`
- `0x18004b28c`
- `0x18004c808`
- `0x18004ce4c`
- `0x18004f780`
- `0x18004fb00`
- `0x1800504d0`
- `0x180050980`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x18004d338`
- `KERNEL32!FindFirstFileW` at `0x18004d338`
- `KERNEL32!FindNextFileW` at `0x18004d46a`
- `KERNEL32!FindNextFileW` at `0x18004d46a`

## string_xrefs

- `0x18004d62e`: `Unable to complete 'begin' directory callback`
- `0x18004cef4`: `No directory specified`
- `0x18004d009`: `Failed adding top level directory to stack`
- `0x18004d95b`: `Failed popping next directory from stack`
- `0x18004d59f`: `Failed finding parent directory`
- `0x18004d6fd`: `Failed 'begin' directory callback`
- `0x18004d232`: `Failed 'end' directory callback`
- `0x18004d2d4`: `Failed 'end' directory callback`
- `0x18004d7dc`: `Failed 'end' directory callback`
- `0x18004d3f3`: `Failed adding directory: {} to stack`

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
  int v11; // edx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // edx
  int v15; // eax
  signed int v16; // eax
  int v17; // edx
  __int64 v18; // r12
  wchar_t *v19; // rax
  unsigned __int64 v20; // rcx
  int v21; // eax
  unsigned __int64 v22; // rcx
  wchar_t *v23; // r10
  wchar_t *v24; // r11
  __int64 (__fastcall *v25)(_QWORD, wchar_t *, wchar_t *, __int64); // rax
  signed int v26; // eax
  int v27; // edx
  __int64 v28; // rdx
  signed int v29; // eax
  int v30; // edx
  int v31; // eax
  HANDLE FirstFileW; // rax
  int v33; // edx
  HANDLE v34; // rbx
  int v35; // eax
  signed int v36; // eax
  int v37; // edx
  int v38; // r8d
  int v39; // edx
  unsigned __int64 v40; // r9
  __int64 v41; // rdx
  int v42; // edx
  int v43; // edx
  unsigned int v44; // eax
  __int64 v45; // rcx
  signed int v46; // eax
  int v47; // edx
  int v48; // edx
  int v49; // edx
  int v50; // edx
  int v51; // edx
  unsigned __int64 v52; // r9
  int v53; // edx
  int v54; // edx
  int v55; // edx
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
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No directory specified");
      hFindFile = &v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
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
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No search pattern specified");
      hFindFile = &v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
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
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed adding top level directory to stack");
      hFindFile = &v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {}",
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
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed popping next directory from stack");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v55,
            3,
            (unsigned int)": {}",
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
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed progress callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v47,
            3,
            (unsigned int)": {}",
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
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed finding parent directory");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v43,
            3,
            (unsigned int)": {}",
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
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to convert size_t to DWORD");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v42,
            3,
            (unsigned int)": {}",
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
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed pushing parent delimiter");
        *(_QWORD *)v59 = &v66;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v54,
          3,
          (unsigned int)": {}",
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
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to convert size_t to DWORD");
        *(_QWORD *)v59 = &v66;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v53,
          3,
          (unsigned int)": {}",
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
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed 'begin' directory callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v48,
            3,
            (unsigned int)": {}",
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
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed 'end' directory callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v27,
            3,
            (unsigned int)": {}",
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
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed 'end' directory callback");
        *(_QWORD *)v59 = &v66;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v30,
          3,
          (unsigned int)": {}",
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
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed 'end' directory callback");
          *(_QWORD *)v59 = &v66;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v50,
            3,
            (unsigned int)": {}",
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
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed progress callback");
              *(_QWORD *)v59 = &v66;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v51,
                3,
                (unsigned int)": {}",
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
          (_DWORD)LogAdapter::g_Logger,
          v39,
          3,
          (unsigned int)": {}",
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
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed file callback");
    *(_QWORD *)v59 = &v66;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v49,
      3,
      (unsigned int)": {}",
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
0x18004ce4c  push    rbp
0x18004ce4e  push    rbx
0x18004ce4f  push    rsi
0x18004ce50  push    rdi
0x18004ce51  push    r12
0x18004ce53  push    r13
0x18004ce55  push    r14
0x18004ce57  push    r15
0x18004ce59  lea     rbp, [rsp-2A8h]
0x18004ce61  sub     rsp, 3A8h
0x18004ce68  mov     rax, cs:__security_cookie
0x18004ce6f  xor     rax, rsp
0x18004ce72  mov     [rbp+2E0h+var_50], rax
0x18004ce79  mov     rax, [rbp+2E0h+arg_20]
0x18004ce80  xor     r14d, r14d
0x18004ce83  mov     r15, [rbp+2E0h+arg_28]
0x18004ce8a  mov     r13, rdx
0x18004ce8d  mov     rbx, rcx
0x18004ce90  mov     [rbp+2E0h+var_358], r8
0x18004ce94  xor     edx, edx; Val
0x18004ce96  mov     [rbp+2E0h+var_360], rax
0x18004ce9a  mov     r8d, 250h; Size
0x18004cea0  mov     [rbp+2E0h+Str], r14
0x18004cea4  lea     rcx, [rbp+2E0h+FindFileData]; void *
0x18004cea8  mov     [rsp+3E0h+var_3A0], r14d
0x18004cead  mov     esi, r14d
0x18004ceb0  mov     [rbp+2E0h+var_350], r9
0x18004ceb4  call    memset
0x18004ceb9  lea     rcx, [rbp+2E0h+var_320]; this
0x18004cebd  call    ??0CCbsDirStack@@QEAA@XZ; CCbsDirStack::CCbsDirStack(void)
0x18004cec2  mov     [rbp+2E0h+var_330], r14
0x18004cec6  mov     [rbp+2E0h+var_338], r14d
0x18004ceca  mov     [rbp+2E0h+var_344], r14d
0x18004cece  mov     [rbp+2E0h+var_348], r14d
0x18004ced2  test    rbx, rbx
0x18004ced5  jnz     short loc_18004CF33
0x18004ced7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004cede  mov     edi, 80070057h
0x18004cee3  mov     [rbp+2E0h+var_348], edi
0x18004cee6  test    rcx, rcx
0x18004cee9  jz      short loc_18004CF29
0x18004ceeb  lea     ebx, [r14+3]
0x18004ceef  xor     edx, edx
0x18004cef1  mov     r8d, ebx
0x18004cef4  lea     r9, aNoDirectorySpe; "No directory specified"
0x18004cefb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004cf00  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004cf07  lea     rax, [rbp+2E0h+var_348]
0x18004cf0b  mov     [rsp+3E0h+hFindFile], rax
0x18004cf10  lea     r9, asc_1800AFAD8; ": {}"
0x18004cf17  lea     rax, [rsp+3E0h+hFindFile]
0x18004cf1c  mov     r8d, ebx
0x18004cf1f  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18004cf24  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004cf29  mov     r9d, edi
0x18004cf2c  mov     edx, 1Ch
0x18004cf31  jmp     short loc_18004CFAE
0x18004cf33  test    r13, r13
0x18004cf36  jnz     short loc_18004CF94
0x18004cf38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004cf3f  mov     edi, 80070057h
0x18004cf44  mov     [rbp+2E0h+var_348], edi
0x18004cf47  test    rcx, rcx
0x18004cf4a  jz      short loc_18004CF8A
0x18004cf4c  lea     ebx, [r13+3]
0x18004cf50  xor     edx, edx
0x18004cf52  mov     r8d, ebx
0x18004cf55  lea     r9, aNoSearchPatter; "No search pattern specified"
0x18004cf5c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004cf61  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004cf68  lea     rax, [rbp+2E0h+var_348]
0x18004cf6c  mov     [rsp+3E0h+hFindFile], rax
0x18004cf71  lea     r9, asc_1800AFAD8; ": {}"
0x18004cf78  lea     rax, [rsp+3E0h+hFindFile]
0x18004cf7d  mov     r8d, ebx
0x18004cf80  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18004cf85  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004cf8a  mov     r9d, edi
0x18004cf8d  mov     edx, 1Dh
0x18004cf92  jmp     short loc_18004CFAE
0x18004cf94  mov     rdx, rbx
0x18004cf97  lea     rcx, [rbp+2E0h+Str]
0x18004cf9b  call    SczAllocFromSz
0x18004cfa0  xor     ebx, ebx
0x18004cfa2  mov     edi, eax
0x18004cfa4  test    eax, eax
0x18004cfa6  jns     short loc_18004CFC6
0x18004cfa8  lea     edx, [rbx+23h]; void *
0x18004cfab  mov     r9d, eax; char *
0x18004cfae  mov     rcx, [rbp+2E8h]; this
0x18004cfb5  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18004cfbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cfc1  jmp     loc_18004D9DC
0x18004cfc6  lea     rcx, [rbp+2E0h+Str]
0x18004cfca  call    SczEnsureBackslashTerminated
0x18004cfcf  mov     edi, eax
0x18004cfd1  test    eax, eax
0x18004cfd3  jns     short loc_18004CFDC
0x18004cfd5  mov     edx, 24h ; '$'
0x18004cfda  jmp     short loc_18004CFAB
0x18004cfdc  xor     r8d, r8d; unsigned int
0x18004cfdf  lea     rdx, asc_1800B07A0; "."
0x18004cfe6  lea     rcx, [rbp+2E0h+var_320]; this
0x18004cfea  call    ?Push@CCbsDirStack@@QEAAJPEB_WK@Z; CCbsDirStack::Push(wchar_t const *,ulong)
0x18004cfef  mov     edi, eax
0x18004cff1  test    eax, eax
0x18004cff3  jns     short loc_18004D050
0x18004cff5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004cffc  mov     [rbp+2E0h+var_348], eax
0x18004cfff  test    rcx, rcx
0x18004d002  jz      short loc_18004D043
0x18004d004  mov     ebx, 3
0x18004d009  lea     r9, aFailedAddingTo; "Failed adding top level directory to st"...
0x18004d010  mov     r8d, ebx
0x18004d013  xor     edx, edx
0x18004d015  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004d01a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004d021  lea     rax, [rbp+2E0h+var_348]
0x18004d025  mov     [rsp+3E0h+hFindFile], rax
0x18004d02a  lea     r9, asc_1800AFAD8; ": {}"
0x18004d031  lea     rax, [rsp+3E0h+hFindFile]
0x18004d036  mov     r8d, ebx
0x18004d039  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18004d03e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004d043  mov     r9d, edi
0x18004d046  mov     edx, 25h ; '%'
0x18004d04b  jmp     loc_18004CFAE
0x18004d050  lea     rax, [rbp+2E0h+var_350]
0x18004d054  mov     [rsp+3E0h+var_368], 1
0x18004d059  mov     [rsp+3E0h+var_398], rax
0x18004d05e  mov     r12, rbx
0x18004d061  lea     rax, [rbp+2E0h+var_338]
0x18004d065  mov     [rsp+3E0h+var_390], rax
0x18004d06a  lea     rax, [rbp+2E0h+var_344]
0x18004d06e  mov     [rsp+3E0h+var_388], rax
0x18004d073  lea     rax, [rbp+2E0h+Str]
0x18004d077  mov     [rsp+3E0h+var_380], rax
0x18004d07c  lea     rax, [rbp+2E0h+var_330]
0x18004d080  mov     [rsp+3E0h+var_378], rax
0x18004d085  lea     rax, [rbp+2E0h+var_358]
0x18004d089  mov     [rsp+3E0h+var_370], rax
0x18004d08e  cmp     [rbp+2E0h+var_308], rbx
0x18004d092  jz      loc_18004D64B
0x18004d098  lea     r8, [rbp+2E0h+var_348]; unsigned int *
0x18004d09c  mov     [rsp+3E0h+hFindFile], rbx
0x18004d0a1  lea     rdx, [rbp+2E0h+var_330]; wchar_t **
0x18004d0a5  lea     rcx, [rbp+2E0h+var_320]; this
0x18004d0a9  call    ?Pop@CCbsDirStack@@QEAAJPEAPEA_WPEAK@Z; CCbsDirStack::Pop(wchar_t * *,ulong *)
0x18004d0ae  mov     edi, eax
0x18004d0b0  test    eax, eax
0x18004d0b2  js      loc_18004D947
0x18004d0b8  mov     rcx, [rbp+2E0h+var_330]
0x18004d0bc  mov     eax, 2Eh ; '.'
0x18004d0c1  cmp     ax, [rcx]
0x18004d0c4  jnz     short loc_18004D145
0x18004d0c6  cmp     ax, [rcx+2]
0x18004d0ca  jnz     short loc_18004D145
0x18004d0cc  cmp     bx, [rcx+4]
0x18004d0d0  jnz     short loc_18004D145
0x18004d0d2  cmp     [rbp+2E0h+var_308], rbx
0x18004d0d6  jz      loc_18004D641
0x18004d0dc  test    esi, esi
0x18004d0de  jz      loc_18004D641
0x18004d0e4  mov     rax, [rbp+2E0h+Str]
0x18004d0e8  lea     edx, [rsi-1]
0x18004d0eb  dec     [rbp+2E0h+var_344]
0x18004d0ee  mov     [rax+rdx*2], bx
0x18004d0f2  mov     edx, 5Ch ; '\'; Ch
0x18004d0f7  mov     rcx, [rbp+2E0h+Str]; Str
0x18004d0fb  call    wcsrchr
0x18004d100  test    rax, rax
0x18004d103  jz      loc_18004D586
0x18004d109  mov     [rax+2], bx
0x18004d10d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d111  mov     rax, [rbp+2E0h+Str]
0x18004d115  inc     rcx; unsigned __int64
0x18004d118  cmp     [rax+rcx*2], bx
0x18004d11c  jnz     short loc_18004D115
0x18004d11e  lea     rdx, [rsp+3E0h+var_3A0]; unsigned int *
0x18004d123  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004d128  mov     edi, eax
0x18004d12a  test    eax, eax
0x18004d12c  js      loc_18004D52C
0x18004d132  lea     rcx, [rsp+3E0h+hFindFile]
0x18004d137  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x18004d13c  mov     esi, [rsp+3E0h+var_3A0]
0x18004d140  jmp     loc_18004D08E
0x18004d145  inc     [rbp+2E0h+var_344]
0x18004d148  lea     rdx, PathName; ".."
0x18004d14f  xor     r8d, r8d; unsigned int
0x18004d152  lea     rcx, [rbp+2E0h+var_320]; this
0x18004d156  call    ?Push@CCbsDirStack@@QEAAJPEB_WK@Z; CCbsDirStack::Push(wchar_t const *,ulong)
0x18004d15b  mov     edi, eax
0x18004d15d  test    eax, eax
0x18004d15f  js      loc_18004D8F0
0x18004d165  mov     r10, [rbp+2E0h+var_330]
0x18004d169  mov     eax, 2Eh ; '.'
0x18004d16e  cmp     [r10], ax
0x18004d172  jnz     short loc_18004D17B
0x18004d174  cmp     [r10+2], bx
0x18004d179  jz      short loc_18004D19C
0x18004d17b  lea     r8, asc_1800AE8E8; "\\"
0x18004d182  mov     rdx, r10
0x18004d185  lea     rcx, [rbp+2E0h+Str]
0x18004d189  call    SczAllocConcat2Sz
0x18004d18e  mov     edi, eax
0x18004d190  test    eax, eax
0x18004d192  js      loc_18004D8E3
0x18004d198  mov     r10, [rbp+2E0h+var_330]
0x18004d19c  mov     r11, [rbp+2E0h+Str]
0x18004d1a0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d1a4  inc     rcx; unsigned __int64
0x18004d1a7  cmp     [r11+rcx*2], bx
0x18004d1ac  jnz     short loc_18004D1A4
0x18004d1ae  lea     rdx, [rsp+3E0h+var_3A0]; unsigned int *
0x18004d1b3  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004d1b8  mov     edi, eax
0x18004d1ba  test    eax, eax
0x18004d1bc  js      loc_18004D889
0x18004d1c2  mov     rax, [rbp+2E0h+var_350]
0x18004d1c6  test    rax, rax
0x18004d1c9  jz      loc_18004D287
0x18004d1cf  mov     r9, [rbp+2E0h+var_358]
0x18004d1d3  mov     r8, r10
0x18004d1d6  mov     ecx, [rbp+2E0h+var_344]
0x18004d1d9  mov     rdx, r11
0x18004d1dc  mov     [rsp+3E0h+var_3C0], 1; int
0x18004d1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1e9  mov     edi, eax
0x18004d1eb  test    eax, eax
0x18004d1ed  js      loc_18004D6E9
0x18004d1f3  mov     rax, [rbp+2E0h+var_350]
0x18004d1f7  cmp     edi, 1
0x18004d1fa  jnz     short loc_18004D278
0x18004d1fc  mov     r9, [rbp+2E0h+var_358]
0x18004d200  mov     r8, [rbp+2E0h+var_330]
0x18004d204  mov     rdx, [rbp+2E0h+Str]
0x18004d208  mov     ecx, [rbp+2E0h+var_344]
0x18004d20b  mov     [rsp+3E0h+var_3C0], ebx
0x18004d20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d214  mov     edi, eax
0x18004d216  test    eax, eax
0x18004d218  jns     loc_18004D132
0x18004d21e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004d225  mov     [rbp+2E0h+var_348], eax
0x18004d228  test    rcx, rcx
0x18004d22b  jz      short loc_18004D26E
0x18004d22d  mov     ebx, 3
0x18004d232  lea     r9, aFailedEndDirec; "Failed 'end' directory callback"
0x18004d239  mov     r8d, ebx
0x18004d23c  xor     edx, edx
0x18004d23e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004d243  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004d24a  lea     rax, [rbp+2E0h+var_348]
0x18004d24e  mov     qword ptr [rsp+3E0h+var_3A8], rax
0x18004d253  lea     r9, asc_1800AFAD8; ": {}"
0x18004d25a  lea     rax, [rsp+3E0h+var_3A8]
0x18004d25f  mov     r8d, ebx
0x18004d262  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18004d267  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004d26c  xor     ebx, ebx
0x18004d26e  mov     edx, 63h ; 'c'
0x18004d273  jmp     loc_18004D99C
0x18004d278  mov     r11, [rbp+2E0h+Str]
0x18004d27c  mov     r10, [rbp+2E0h+var_330]
0x18004d280  mov     [rbp+2E0h+var_338], 1
0x18004d287  test    [rbp+2E0h+var_348], 400h
0x18004d28e  jz      loc_18004D31A
0x18004d294  test    rax, rax
0x18004d297  jz      loc_18004D132
0x18004d29d  mov     r9, [rbp+2E0h+var_358]
0x18004d2a1  mov     r8, r10
0x18004d2a4  mov     ecx, [rbp+2E0h+var_344]
0x18004d2a7  mov     rdx, r11
0x18004d2aa  mov     [rbp+2E0h+var_338], ebx
0x18004d2ad  mov     [rsp+3E0h+var_3C0], ebx
0x18004d2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2b6  mov     edi, eax
0x18004d2b8  test    eax, eax
0x18004d2ba  jns     loc_18004D132
0x18004d2c0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004d2c7  mov     [rbp+2E0h+var_348], eax
0x18004d2ca  test    rcx, rcx
0x18004d2cd  jz      short loc_18004D310
0x18004d2cf  mov     ebx, 3
0x18004d2d4  lea     r9, aFailedEndDirec; "Failed 'end' directory callback"
0x18004d2db  mov     r8d, ebx
0x18004d2de  xor     edx, edx
0x18004d2e0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004d2e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004d2ec  lea     rax, [rbp+2E0h+var_348]
0x18004d2f0  mov     qword ptr [rsp+3E0h+var_3A8], rax
0x18004d2f5  lea     r9, asc_1800AFAD8; ": {}"
0x18004d2fc  lea     rax, [rsp+3E0h+var_3A8]
0x18004d301  mov     r8d, ebx
0x18004d304  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18004d309  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004d30e  xor     ebx, ebx
0x18004d310  mov     edx, 75h ; 'u'
0x18004d315  jmp     loc_18004D99C
  ... truncated ...
```
