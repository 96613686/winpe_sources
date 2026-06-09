# CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(bool,bool,void *,wchar_t const * const)

- ea: `0x140012c58`
- end: `0x140013444`
- name: `?RemoveDirectoryHelperEx@CRecursiveRemoveDirectory@@AEAAJ_N0PEAXQEB_W@Z`
- size: `2028`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *this, char, char, void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops`

## callers

- `0x14001344c`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x1400053c0`
- `0x140006514`
- `0x140006950`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e0d4`
- `0x14000e63c`
- `0x14000e66c`
- `0x14000ebb4`
- `0x14000f4f0`
- `0x14001219c`
- `0x140012328`
- `0x1400124cc`
- `0x140012528`
- `0x140012558`
- `0x1400129b8`
- `0x140012c58`
- `0x140013a18`
- `0x1400141ac`
- `0x140014290`
- `0x140014490`
- `0x140017464`
- `0x140017ec8`
- `0x140018740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140012fa5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140012fa5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140012f60`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140012f60`

## string_xrefs

- `0x140012ce3`: `No directory specified`
- `0x140012db5`: `Failed to open {} for deletion`
- `0x140013305`: `Failed to open {} for deletion`
- `0x140012e3a`: `Failed to add item to directory stack`
- `0x1400131d2`: `Failed to add item to directory stack`
- `0x140012edc`: `Failed to backslash-terminate directory path.`
- `0x140013184`: `Unable to remove directory {}.`
- `0x140013256`: `Failed to backslash-terminate subdirectory path.`

## pseudocode

```c
__int64 __fastcall CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(
        CRecursiveRemoveDirectory *this,
        char a2,
        char a3,
        void *a4,
        const wchar_t *a5)
{
  int v5; // edi
  int v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  __int64 InitPointer; // rax
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  int v16; // edx
  __int64 v17; // rdi
  int v18; // esi
  __int64 v19; // rdx
  int v20; // eax
  int v21; // edx
  __int64 v22; // r12
  __int64 v23; // r14
  char *v24; // rcx
  __int64 v25; // rdx
  HANDLE FirstFileW; // rax
  bool v27; // r9
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // esi
  __int64 v32; // rax
  int v33; // r8d
  int v34; // r9d
  int v35; // eax
  int v36; // edx
  int v37; // r8d
  __int64 v38; // rdx
  int v39; // eax
  int v40; // edi
  LPCWSTR *v41; // rsi
  bool v42; // zf
  LPCWSTR v43; // rax
  int v44; // eax
  int v45; // edi
  int v46; // edx
  int v47; // edx
  int v48; // edx
  int v49; // edx
  int v51; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  int v54[2]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v55; // [rsp+48h] [rbp-B8h] BYREF
  int v56; // [rsp+50h] [rbp-B0h] BYREF
  int v57[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+78h] [rbp-88h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v5 = (int)a4;
  v55 = a5;
  v58 = 0;
  v60 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( !a5 )
  {
    v8 = -2147024809;
    v56 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No directory specified");
      *(_QWORD *)v57 = &v56;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v57);
    }
    v10 = 1145;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v8,
      v51);
    goto LABEL_76;
  }
  InitPointer = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&v58);
  v14 = OpenFileRelativeToParent(v5, (_DWORD)v55, v12, v13, a2, InitPointer);
  v8 = v14;
  if ( (unsigned int)(v14 + 2147024894) <= 1
    || v14 == -2147024773
    || v14 == -2147022975
    || (unsigned int)(v14 + 805306317) <= 1
    || v14 == -805306310
    || v14 == -805305728 )
  {
    utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(&si128);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v58);
    return 0;
  }
  if ( v14 < 0 )
  {
    v56 = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to open {} for deletion",
        (__int64)&v55);
      *(_QWORD *)v57 = &v56;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)v57);
    }
    v10 = 1166;
    goto LABEL_15;
  }
  if ( !(unsigned __int8)utl::vector<DeleteContext,utl::allocator<DeleteContext>>::emplace_back<Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>,0>(
                           &si128,
                           &v58) )
  {
    v8 = -2147024882;
    v56 = -2147024882;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add item to directory stack");
      *(_QWORD *)v57 = &v56;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)v57);
    }
    v10 = 1169;
    goto LABEL_15;
  }
  v17 = si128.m128i_i64[1];
  v18 = SczAllocFromSz(si128.m128i_i64[1] - 16, v55);
  if ( v18 < 0 )
  {
    v19 = 1171;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v18,
      v51);
    goto LABEL_75;
  }
  v20 = SczEnsureBackslashTerminated(v17 - 16);
  v18 = v20;
  if ( v20 < 0 )
  {
    v56 = v20;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to backslash-terminate directory path.");
      *(_QWORD *)v57 = &v56;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)v57);
    }
    v19 = 1175;
    goto LABEL_22;
  }
  v22 = si128.m128i_i64[0];
  while ( 1 )
  {
    if ( CRecursiveRemoveDirectory::WasRequestCancelled(this) )
      goto LABEL_76;
    v23 = v17 - 24;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v24 = *(char **)(v17 - 24 + 16);
    if ( (unsigned __int64)(v24 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      break;
    if ( !FindNextFileW(v24, &FindFileData) )
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithFindClose(void *)>>::Close(v23 + 16);
LABEL_34:
    if ( (unsigned __int64)(*(_QWORD *)(v17 - 24 + 16) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( 0xAAAAAAAAAAAAAAABuLL * ((v17 - v22) >> 3) > 1 || !a3 )
      {
        v44 = CRecursiveRemoveDirectory::UnlinkOrDelete(this, *(void **)v23);
        v45 = v44;
        lpFileName = *(LPCWSTR *)(v23 + 8);
        if ( v44 < 0 )
        {
          LogAdapter::TraceAtLevelHr<long,wchar_t *>(
            1,
            (unsigned int)v44,
            "Unable to remove directory {}.",
            &lpFileName);
          if ( v8 >= 0 )
            v8 = v45;
        }
      }
      si128.m128i_i64[1] = v23;
      v17 = v23;
      DeleteContext::~DeleteContext((DeleteContext *)v23);
    }
    else if ( !IsDotFile(FindFileData.cFileName) )
    {
      if ( (FindFileData.dwFileAttributes & 0x410) == 0x10 )
      {
        *(_QWORD *)v57 = 0;
        v32 = Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(v57);
        v35 = OpenFileRelativeToParent(*(_QWORD *)v23, (unsigned int)FindFileData.cFileName, v33, v34, 0, v32);
        v18 = v35;
        if ( (unsigned int)(v35 + 2147024894) <= 1
          || v35 == -2147024773
          || v35 == -2147022975
          || (unsigned int)(v35 + 805306317) <= 1
          || v35 == -805306310
          || v35 == -805305728 )
        {
          Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v57);
        }
        else
        {
          if ( v35 < 0 )
          {
            v56 = v35;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t [260]>(
                (_DWORD)LogAdapter::g_Logger,
                v36,
                v37,
                (unsigned int)"Failed to open {} for deletion",
                (__int64)FindFileData.cFileName);
              *(_QWORD *)v54 = &v56;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v48,
                3,
                (unsigned int)": {}",
                (__int64)v54);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4F9,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
              (const char *)(unsigned int)v18,
              v51);
            goto LABEL_71;
          }
          v38 = *(_QWORD *)(v23 + 8);
          lpFileName = 0;
          v39 = SczAllocConcat2Sz(&lpFileName, v38, FindFileData.cFileName);
          v40 = v39;
          if ( v39 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4FC,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
              (const char *)(unsigned int)v39,
              v51);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
            Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v57);
            v8 = v40;
            goto LABEL_76;
          }
          v18 = SczEnsureBackslashTerminated(&lpFileName);
          if ( v18 < 0 )
          {
            v56 = v18;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to backslash-terminate subdirectory path.");
              *(_QWORD *)v54 = &v56;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v47,
                3,
                (unsigned int)": {}",
                (__int64)v54);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4FE,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
              (const char *)(unsigned int)v18,
              v51);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
LABEL_71:
            Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v57);
            goto LABEL_75;
          }
          if ( !(unsigned __int8)utl::vector<DeleteContext,utl::allocator<DeleteContext>>::emplace_back<Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>,0>(
                                   &si128,
                                   v57) )
          {
            v8 = -2147024882;
            v56 = -2147024882;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add item to directory stack");
              *(_QWORD *)v54 = &v56;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v46,
                3,
                (unsigned int)": {}",
                (__int64)v54);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x508,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
              (const char *)0x8007000ELL,
              v51);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
            Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v57);
            goto LABEL_76;
          }
          v17 = si128.m128i_i64[1];
          v41 = (LPCWSTR *)(si128.m128i_i64[1] - 16);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(si128.m128i_i64[1] - 16);
          v42 = *v41 == 0;
          v43 = lpFileName;
          lpFileName = 0;
          if ( !v42 )
            INTERNAL_ERROR_ACTION(-1073741595);
          *v41 = v43;
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
          Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v57);
          v22 = si128.m128i_i64[0];
        }
      }
      else
      {
        v28 = CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(this, *(void **)v23, FindFileData.cFileName, v27);
        v31 = v28;
        if ( v28 < 0 )
        {
          LogAdapter::TraceAtLevelHr<long,wchar_t [260]>(v29, (unsigned int)v28, v30, FindFileData.cFileName);
          if ( v8 >= 0 )
            v8 = v31;
        }
      }
    }
    if ( v22 == v17 )
      goto LABEL_76;
  }
  v25 = *(_QWORD *)(v23 + 8);
  lpFileName = 0;
  v18 = SczAllocConcat2Sz(&lpFileName, v25, L"*.*");
  if ( v18 >= 0 )
  {
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      v23 + 16,
      FirstFileW);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    goto LABEL_34;
  }
  v56 = v18;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to append wildcard to search pattern.");
    *(_QWORD *)v54 = &v56;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v49,
      3,
      (unsigned int)": {}",
      (__int64)v54);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4AA,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)(unsigned int)v18,
    v51);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
LABEL_75:
  v8 = v18;
LABEL_76:
  utl::vector<DeleteContext,utl::allocator<DeleteContext>>::_Uninit(&si128);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v58);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140012c58  mov     [rsp-8+arg_10], rbx
0x140012c5d  push    rbp
0x140012c5e  push    rsi
0x140012c5f  push    rdi
0x140012c60  push    r12
0x140012c62  push    r13
0x140012c64  push    r14
0x140012c66  push    r15
0x140012c68  lea     rbp, [rsp-1E0h]
0x140012c70  sub     rsp, 2E0h
0x140012c77  mov     rax, cs:__security_cookie
0x140012c7e  xor     rax, rsp
0x140012c81  mov     [rbp+210h+var_40], rax
0x140012c88  mov     rax, [rbp+210h+arg_20]
0x140012c8f  mov     rdi, r9
0x140012c92  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140012c9a  mov     bl, dl
0x140012c9c  mov     [rsp+310h+var_2E0], r8b
0x140012ca1  mov     r13, rcx
0x140012ca4  mov     [rsp+310h+var_2C8], rax
0x140012ca9  mov     [rsp+310h+var_2B0], 0
0x140012cb2  mov     [rsp+310h+var_298], 0FFFFFFFFFFFFFFFFh
0x140012cbb  movdqu  [rsp+310h+var_2A8], xmm0
0x140012cc1  test    rax, rax
0x140012cc4  jnz     short loc_140012D23
0x140012cc6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012ccd  mov     ebx, 80070057h
0x140012cd2  mov     [rsp+310h+var_2C0], ebx
0x140012cd6  test    rcx, rcx
0x140012cd9  jz      short loc_140012D19
0x140012cdb  lea     edi, [rax+3]
0x140012cde  xor     edx, edx
0x140012ce0  mov     r8d, edi
0x140012ce3  lea     r9, aNoDirectorySpe; "No directory specified"
0x140012cea  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012cef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012cf6  lea     rax, [rsp+310h+var_2C0]
0x140012cfb  mov     qword ptr [rsp+310h+var_2B8], rax
0x140012d00  lea     r9, asc_140030534; ": {}"
0x140012d07  lea     rax, [rsp+310h+var_2B8]
0x140012d0c  mov     r8d, edi
0x140012d0f  mov     qword ptr [rsp+310h+var_2F0], rax
0x140012d14  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012d19  mov     edx, 479h
0x140012d1e  jmp     loc_140012DF2
0x140012d23  lea     rcx, [rsp+310h+var_2B0]
0x140012d28  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x140012d2d  mov     rdx, [rsp+310h+var_2C8]
0x140012d32  mov     rcx, rdi
0x140012d35  mov     [rsp+310h+var_2E8], rax
0x140012d3a  mov     byte ptr [rsp+310h+var_2F0], bl; int
0x140012d3e  call    OpenFileRelativeToParent
0x140012d43  mov     ebx, eax
0x140012d45  lea     ecx, [rax+7FF8FFFEh]
0x140012d4b  cmp     ecx, 1
0x140012d4e  jbe     loc_1400133F9
0x140012d54  cmp     eax, 8007007Bh
0x140012d59  jz      loc_1400133F9
0x140012d5f  cmp     eax, 80070781h
0x140012d64  jz      loc_1400133F9
0x140012d6a  lea     ecx, [rax+2FFFFFCDh]
0x140012d70  cmp     ecx, 1
0x140012d73  jbe     loc_1400133F9
0x140012d79  cmp     eax, 0D000003Ah
0x140012d7e  jz      loc_1400133F9
0x140012d84  cmp     eax, 0D0000280h
0x140012d89  jz      loc_1400133F9
0x140012d8f  test    eax, eax
0x140012d91  jns     short loc_140012E0D
0x140012d93  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012d9a  mov     [rsp+310h+var_2C0], eax
0x140012d9e  test    rcx, rcx
0x140012da1  jz      short loc_140012DED
0x140012da3  lea     rax, [rsp+310h+var_2C8]
0x140012da8  mov     edi, 3
0x140012dad  mov     r8d, edi
0x140012db0  mov     qword ptr [rsp+310h+var_2F0], rax
0x140012db5  lea     r9, aFailedToOpenFo; "Failed to open {} for deletion"
0x140012dbc  xor     edx, edx
0x140012dbe  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140012dc3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012dca  lea     rax, [rsp+310h+var_2C0]
0x140012dcf  mov     qword ptr [rsp+310h+var_2B8], rax
0x140012dd4  lea     r9, asc_140030534; ": {}"
0x140012ddb  lea     rax, [rsp+310h+var_2B8]
0x140012de0  mov     r8d, edi
0x140012de3  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x140012de8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012ded  mov     edx, 48Eh; void *
0x140012df2  mov     rcx, [rbp+218h]; this
0x140012df9  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140012e00  mov     r9d, ebx; char *
0x140012e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012e08  jmp     loc_1400133E1
0x140012e0d  lea     rdx, [rsp+310h+var_2B0]
0x140012e12  lea     rcx, [rsp+310h+var_2A8]
0x140012e17  call    ??$emplace_back@V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@$0A@@?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA_N$$QEAV?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Z; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::emplace_back<Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>,0>(Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)> &&)
0x140012e1c  test    al, al
0x140012e1e  jnz     short loc_140012E7F
0x140012e20  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012e27  mov     ebx, 8007000Eh
0x140012e2c  mov     [rsp+310h+var_2C0], ebx
0x140012e30  test    rcx, rcx
0x140012e33  jz      short loc_140012E75
0x140012e35  mov     edi, 3
0x140012e3a  lea     r9, aFailedToAddIte; "Failed to add item to directory stack"
0x140012e41  mov     r8d, edi
0x140012e44  xor     edx, edx
0x140012e46  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012e4b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012e52  lea     rax, [rsp+310h+var_2C0]
0x140012e57  mov     qword ptr [rsp+310h+var_2B8], rax
0x140012e5c  lea     r9, asc_140030534; ": {}"
0x140012e63  lea     rax, [rsp+310h+var_2B8]
0x140012e68  mov     r8d, edi
0x140012e6b  mov     qword ptr [rsp+310h+var_2F0], rax
0x140012e70  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012e75  mov     edx, 491h
0x140012e7a  jmp     loc_140012DF2
0x140012e7f  mov     rdi, qword ptr [rsp+310h+var_2A8+8]
0x140012e84  mov     rdx, [rsp+310h+var_2C8]
0x140012e89  lea     rcx, [rdi-10h]
0x140012e8d  call    SczAllocFromSz
0x140012e92  mov     esi, eax
0x140012e94  test    eax, eax
0x140012e96  jns     short loc_140012EB8
0x140012e98  mov     edx, 493h; void *
0x140012e9d  mov     rcx, [rbp+218h]; this
0x140012ea4  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140012eab  mov     r9d, esi; char *
0x140012eae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012eb3  jmp     loc_1400133DF
0x140012eb8  lea     rcx, [rdi-10h]
0x140012ebc  call    SczEnsureBackslashTerminated
0x140012ec1  mov     esi, eax
0x140012ec3  test    eax, eax
0x140012ec5  jns     short loc_140012F21
0x140012ec7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012ece  mov     [rsp+310h+var_2C0], eax
0x140012ed2  test    rcx, rcx
0x140012ed5  jz      short loc_140012F17
0x140012ed7  mov     edi, 3
0x140012edc  lea     r9, aFailedToBacksl_0; "Failed to backslash-terminate directory"...
0x140012ee3  mov     r8d, edi
0x140012ee6  xor     edx, edx
0x140012ee8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140012eed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012ef4  lea     rax, [rsp+310h+var_2C0]
0x140012ef9  mov     qword ptr [rsp+310h+var_2B8], rax
0x140012efe  lea     r9, asc_140030534; ": {}"
0x140012f05  lea     rax, [rsp+310h+var_2B8]
0x140012f0a  mov     r8d, edi
0x140012f0d  mov     qword ptr [rsp+310h+var_2F0], rax
0x140012f12  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012f17  mov     edx, 497h
0x140012f1c  jmp     loc_140012E9D
0x140012f21  mov     r12, qword ptr [rsp+310h+var_2A8]
0x140012f26  mov     rcx, r13; this
0x140012f29  call    ?WasRequestCancelled@CRecursiveRemoveDirectory@@AEAA_NXZ; CRecursiveRemoveDirectory::WasRequestCancelled(void)
0x140012f2e  test    al, al
0x140012f30  jnz     loc_1400133E1
0x140012f36  xor     edx, edx; Val
0x140012f38  lea     rcx, [rbp+210h+FindFileData]; void *
0x140012f3c  mov     r8d, 250h; Size
0x140012f42  lea     r14, [rdi-18h]
0x140012f46  call    memset_0
0x140012f4b  lea     r15, [r14+10h]
0x140012f4f  mov     rcx, [r15]; hFindFile
0x140012f52  lea     rax, [rcx-1]
0x140012f56  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140012f5a  ja      short loc_140012F74
0x140012f5c  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x140012f60  call    cs:__imp_FindNextFileW
0x140012f66  test    eax, eax
0x140012f68  jnz     short loc_140012FC0
0x140012f6a  mov     rcx, r15
0x140012f6d  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithFindClose@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithFindClose(void *)>>::Close(void)
0x140012f72  jmp     short loc_140012FC0
0x140012f74  mov     rdx, [r14+8]
0x140012f78  lea     r8, asc_140032BF8; "*.*"
0x140012f7f  lea     rcx, [rsp+310h+lpFileName]
0x140012f84  mov     [rsp+310h+lpFileName], 0
0x140012f8d  call    SczAllocConcat2Sz
0x140012f92  mov     esi, eax
0x140012f94  test    eax, eax
0x140012f96  js      loc_14001336A
0x140012f9c  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x140012fa1  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x140012fa5  call    cs:__imp_FindFirstFileW
0x140012fab  mov     rdx, rax
0x140012fae  mov     rcx, r15
0x140012fb1  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x140012fb6  lea     rcx, [rsp+310h+lpFileName]
0x140012fbb  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140012fc0  mov     rax, [r15]
0x140012fc3  dec     rax
0x140012fc6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140012fca  ja      loc_140013141
0x140012fd0  lea     rcx, [rbp+210h+FindFileData.cFileName]; wchar_t *
0x140012fd4  call    ?IsDotFile@@YA_NPEB_W@Z; IsDotFile(wchar_t const *)
0x140012fd9  test    al, al
0x140012fdb  jnz     loc_1400131AA
0x140012fe1  mov     eax, [rbp+210h+FindFileData.dwFileAttributes]
0x140012fe4  and     eax, 410h
0x140012fe9  cmp     eax, 10h
0x140012fec  jz      short loc_140013021
0x140012fee  mov     rdx, [r14]; void *
0x140012ff1  lea     r8, [rbp+210h+FindFileData.cFileName]; wchar_t *
0x140012ff5  mov     rcx, r13; this
0x140012ff8  call    ?RemoveFileOrDirectoryEntryEx@CRecursiveRemoveDirectory@@AEAAJPEAXPEB_W_N@Z; CRecursiveRemoveDirectory::RemoveFileOrDirectoryEntryEx(void *,wchar_t const *,bool)
0x140012ffd  mov     esi, eax
0x140012fff  test    eax, eax
0x140013001  jns     loc_1400131AA
0x140013007  lea     r9, [rbp+210h+FindFileData.cFileName]
0x14001300b  mov     edx, eax
0x14001300d  call    ??$TraceAtLevelHr@J$$BY0BAE@_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEAY0BAE@$$CB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t [260]>(LogAdapter::LogLevel,long,char const * const,wchar_t const (&)[260])
0x140013012  test    ebx, ebx
0x140013014  js      loc_1400131AA
0x14001301a  mov     ebx, esi
0x14001301c  jmp     loc_1400131AA
0x140013021  lea     rcx, [rsp+310h+var_2B8]
0x140013026  mov     qword ptr [rsp+310h+var_2B8], 0
0x14001302f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x140013034  mov     rcx, [r14]
0x140013037  lea     rdx, [rbp+210h+FindFileData.cFileName]
0x14001303b  mov     [rsp+310h+var_2E8], rax
0x140013040  mov     byte ptr [rsp+310h+var_2F0], 0; int
0x140013045  call    OpenFileRelativeToParent
0x14001304a  mov     esi, eax
0x14001304c  lea     ecx, [rax+7FF8FFFEh]
0x140013052  cmp     ecx, 1
0x140013055  jbe     loc_140013135
0x14001305b  cmp     eax, 8007007Bh
0x140013060  jz      loc_140013135
0x140013066  cmp     eax, 80070781h
0x14001306b  jz      loc_140013135
0x140013071  lea     ecx, [rax+2FFFFFCDh]
0x140013077  cmp     ecx, 1
0x14001307a  jbe     loc_140013135
0x140013080  cmp     eax, 0D000003Ah
0x140013085  jz      loc_140013135
0x14001308b  cmp     eax, 0D0000280h
0x140013090  jz      loc_140013135
0x140013096  test    eax, eax
0x140013098  js      loc_1400132F1
0x14001309e  mov     rdx, [r14+8]
0x1400130a2  lea     r8, [rbp+210h+FindFileData.cFileName]
0x1400130a6  lea     rcx, [rsp+310h+lpFileName]
0x1400130ab  mov     [rsp+310h+lpFileName], 0
0x1400130b4  call    SczAllocConcat2Sz
0x1400130b9  mov     edi, eax
0x1400130bb  test    eax, eax
0x1400130bd  js      loc_1400132BB
0x1400130c3  lea     rcx, [rsp+310h+lpFileName]
0x1400130c8  call    SczEnsureBackslashTerminated
0x1400130cd  mov     esi, eax
0x1400130cf  test    eax, eax
0x1400130d1  js      loc_140013241
0x1400130d7  lea     rdx, [rsp+310h+var_2B8]
0x1400130dc  lea     rcx, [rsp+310h+var_2A8]
0x1400130e1  call    ??$emplace_back@V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@$0A@@?$vector@UDeleteContext@@V?$allocator@UDeleteContext@@@utl@@@utl@@QEAA_N$$QEAV?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Z; utl::vector<DeleteContext,utl::allocator<DeleteContext>>::emplace_back<Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>,0>(Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)> &&)
0x1400130e6  test    al, al
0x1400130e8  jz      loc_1400131B8
0x1400130ee  mov     rdi, qword ptr [rsp+310h+var_2A8+8]
0x1400130f3  lea     rsi, [rdi-10h]
0x1400130f7  mov     rcx, rsi
0x1400130fa  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400130ff  cmp     qword ptr [rsi], 0
0x140013103  mov     rax, [rsp+310h+lpFileName]
0x140013108  mov     [rsp+310h+lpFileName], 0
0x140013111  jnz     loc_140013439
0x140013117  lea     rcx, [rsp+310h+lpFileName]
0x14001311c  mov     [rsi], rax
0x14001311f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140013124  lea     rcx, [rsp+310h+var_2B8]
0x140013129  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x14001312e  mov     r12, qword ptr [rsp+310h+var_2A8]
0x140013133  jmp     short loc_1400131AA
0x140013135  lea     rcx, [rsp+310h+var_2B8]
0x14001313a  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x14001313f  jmp     short loc_1400131AA
0x140013141  sub     rdi, r12
0x140013144  mov     rax, 0AAAAAAAAAAAAAAABh
0x14001314e  sar     rdi, 3
0x140013152  imul    rdi, rax
0x140013156  cmp     rdi, 1
0x14001315a  ja      short loc_140013163
0x14001315c  cmp     [rsp+310h+var_2E0], 0
0x140013161  jnz     short loc_14001319A
0x140013163  mov     rdx, [r14]; void *
0x140013166  mov     rcx, r13; this
0x140013169  call    ?UnlinkOrDelete@CRecursiveRemoveDirectory@@AEAAJPEAX@Z; CRecursiveRemoveDirectory::UnlinkOrDelete(void *)
0x14001316e  mov     rcx, [r14+8]
0x140013172  mov     edi, eax
0x140013174  mov     [rsp+310h+lpFileName], rcx
0x140013179  test    eax, eax
0x14001317b  jns     short loc_14001319A
0x14001317d  lea     r9, [rsp+310h+lpFileName]
0x140013182  mov     edx, eax
0x140013184  lea     r8, aUnableToRemove; "Unable to remove directory {}."
  ... truncated ...
```
