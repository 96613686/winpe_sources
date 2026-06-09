# CRecursiveRemoveDirectory::RemoveDirectoryW(ulong,wchar_t const * const,wchar_t const * const)

- ea: `0x14001344c`
- end: `0x140013a10`
- name: `?RemoveDirectoryW@CRecursiveRemoveDirectory@@QEAAJKQEB_W0@Z`
- size: `1476`
- prototype: `__int64 __fastcall(CRecursiveRemoveDirectory *this, BOOL, const wchar_t *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1400150ac`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e150`
- `0x14000e66c`
- `0x14000f4f0`
- `0x14001093c`
- `0x140012678`
- `0x140012c58`
- `0x14001344c`
- `0x140013d48`
- `0x140014104`
- `0x1400149ec`
- `0x140017004`
- `0x140017ec8`
- `0x1400240a4`
- `0x1400240f0`
- `0x140024cf8`
- `0x140025e90`
- `0x140025fd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400138b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400138b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140013879`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140013879`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140013744`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140013744`

## string_xrefs

- `0x1400135cb`: `No directory specified`
- `0x1400134f8`: `Cannot use ContentsOnly with MoveToCbsTempBeforeDelete or RenameToTempBeforeDelete or MoveToCbsTempOnFailures`
- `0x140013561`: `Cannot use AllowReparseRoot without ContentsOnly`
- `0x14001368e`: `Deleting the contents of directory: {}`
- `0x14001369c`: `Deleting directory: {}`
- `0x1400136ef`: `Failed to acquire current thread token`
- `0x140013994`: `Deletion of: {} successful; already deleted`
- `0x1400137b8`: `Unable to move directory to temp, will delete in-place instead`
- `0x14001380a`: `Failed getting parent directory: {}`
- `0x1400138e3`: `Deletion of directory failed...moving to CbsTemp`
- `0x14001391a`: `Failed removing directory: {}`

## pseudocode

```c
__int64 __fastcall CRecursiveRemoveDirectory::RemoveDirectoryW(
        CRecursiveRemoveDirectory *this,
        BOOL a2,
        const wchar_t *a3,
        const wchar_t *const a4)
{
  int v6; // r14d
  int v7; // r13d
  unsigned int v8; // r15d
  bool v9; // r12
  int v10; // edi
  int v11; // edx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rdx
  int v16; // edx
  int v17; // eax
  int v18; // edx
  WCHAR *v19; // rbx
  const char *v20; // r9
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // edi
  int v24; // edx
  int v25; // edx
  int v26; // ecx
  void *v27; // rax
  int v28; // eax
  LPCWSTR v29; // rcx
  int v30; // eax
  int v31; // edx
  HANDLE FileW; // rax
  __int64 v33; // rcx
  signed int LastError; // eax
  int v35; // edx
  const char *v36; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-B9h]
  bool v39; // [rsp+40h] [rbp-99h]
  LPCWSTR lpFileName; // [rsp+48h] [rbp-91h] BYREF
  int v41[2]; // [rsp+50h] [rbp-89h] BYREF
  __int64 v42; // [rsp+58h] [rbp-81h]
  CRecursiveRemoveDirectory *v43; // [rsp+60h] [rbp-79h] BYREF
  void *v44; // [rsp+68h] [rbp-71h] BYREF
  LPCWSTR v45; // [rsp+70h] [rbp-69h] BYREF
  __int64 v46; // [rsp+78h] [rbp-61h] BYREF
  const wchar_t *v47; // [rsp+80h] [rbp-59h] BYREF
  LPCWSTR v48; // [rsp+88h] [rbp-51h] BYREF
  __int64 v49; // [rsp+90h] [rbp-49h] BYREF
  char v50; // [rsp+98h] [rbp-41h]
  _BYTE v51[80]; // [rsp+A0h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v43 = this;
  v45 = 0;
  lpFileName = 0;
  v46 = 0;
  v47 = a3;
  AutoThreadPriority::AutoThreadPriority((AutoThreadPriority *)v51, a2);
  v49 = 0;
  v6 = a2 & 0x10;
  v50 = 0;
  v44 = 0;
  v7 = a2 & 0x20;
  LOBYTE(v8) = (a2 & 8) != 0;
  v39 = (a2 & 0x40) != 0;
  v9 = a2;
  if ( a2 && ((a2 & 0x10) != 0 || (a2 & 0x20) != 0 || (a2 & 8) != 0) )
  {
    v10 = -2147024809;
    LODWORD(v48) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot use ContentsOnly with MoveToCbsTempBeforeDelete or RenameToTempBeforeDelete or MoveToCbsTempOnFailures");
      *(_QWORD *)v41 = &v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v41);
    }
    v12 = 2147942487LL;
    v13 = 779;
    goto LABEL_22;
  }
  if ( (a2 & 0x40) != 0 && !v9 )
  {
    v10 = -2147024809;
    LODWORD(v48) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot use AllowReparseRoot without ContentsOnly");
      *(_QWORD *)v41 = &v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)v41);
    }
    v12 = 2147942487LL;
    v13 = 784;
    goto LABEL_22;
  }
  v15 = v47;
  if ( !v47 )
  {
    v10 = -2147024809;
    LODWORD(v48) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        (unsigned int)((_DWORD)v47 + 3),
        "No directory specified");
      *(_QWORD *)v41 = &v48;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        (_DWORD)v47 + 3,
        (unsigned int)": {}",
        (__int64)v41);
    }
    v12 = 2147942487LL;
    v13 = 787;
    goto LABEL_22;
  }
  *((_DWORD *)this + 5) = a2;
  *((_BYTE *)this + 16) = (a2 & 2) != 0;
  if ( (a2 & 4) != 0 )
  {
    AutoThreadPriority::SetPriority(v51, 3);
    v15 = v47;
  }
  v17 = SczAllocFromSz(&lpFileName, v15);
  v10 = v17;
  if ( v17 < 0 )
  {
    v13 = 800;
LABEL_21:
    v12 = (unsigned int)v17;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v12,
      dwCreationDisposition);
    goto LABEL_69;
  }
  v17 = PathPrefix(&lpFileName);
  v10 = v17;
  if ( v17 < 0 )
  {
    v13 = 801;
    goto LABEL_21;
  }
  v19 = (WCHAR *)lpFileName;
  *(_QWORD *)v41 = lpFileName;
  if ( v9 )
  {
    if ( !LogAdapter::g_Logger )
      goto LABEL_31;
    v20 = "Deleting the contents of directory: {}";
  }
  else
  {
    if ( !LogAdapter::g_Logger )
      goto LABEL_31;
    v20 = "Deleting directory: {}";
  }
  LOBYTE(v18) = 1;
  LogAdapter::Logger::LogNumObjects<wchar_t const *>((_DWORD)LogAdapter::g_Logger, v18, 1, (_DWORD)v20, (__int64)v41);
LABEL_31:
  v42 = 3;
  *(_QWORD *)v41 = &RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs;
  v21 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v49, v41);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( GetFileAttributesW(v19) == -1 )
    {
      v26 = (int)LogAdapter::g_Logger;
      *(_QWORD *)v41 = v19;
      if ( LogAdapter::g_Logger )
      {
        v27 = v41;
LABEL_66:
        v36 = "Deletion of: {} successful; already deleted";
        goto LABEL_67;
      }
      goto LABEL_68;
    }
    if ( v6 || v7 )
    {
      v48 = v19;
      lpFileName = 0;
      if ( v6 )
      {
        v28 = MoveToCbsTemp(v19, 0, &lpFileName);
        v8 = (unsigned int)v28 >> 31;
      }
      else
      {
        LOBYTE(v8) = 0;
        v28 = RenameToTemp(v19, &lpFileName);
      }
      if ( v28 >= 0 )
      {
        v19 = (WCHAR *)lpFileName;
      }
      else
      {
        v29 = lpFileName;
        v48 = lpFileName;
        lpFileName = v19;
        LogAdapter::TraceAtLevelIfFailed<long,>(
          v29,
          (unsigned int)v28,
          "Unable to move directory to temp, will delete in-place instead");
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v48);
    }
    v30 = DirectoryFromPath(v19);
    v10 = v30;
    if ( v30 < 0 )
    {
      LODWORD(v48) = v30;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v41 = v19;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed getting parent directory: {}",
          (__int64)v41);
        v43 = (CRecursiveRemoveDirectory *)&v48;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          3,
          (unsigned int)": {}",
          (__int64)&v43);
      }
      v12 = (unsigned int)v10;
      v13 = 866;
      goto LABEL_22;
    }
    FileW = CreateFileW(v45, 0x100080u, 7u, 0, 3u, 0x2200000u, 0);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &v44,
      FileW);
    if ( (char *)v44 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)(v10 + 2147024894) <= 1 )
      {
        v26 = (int)LogAdapter::g_Logger;
        v43 = (CRecursiveRemoveDirectory *)v19;
        if ( LogAdapter::g_Logger )
        {
          v27 = &v43;
          goto LABEL_66;
        }
LABEL_68:
        v10 = 0;
        goto LABEL_69;
      }
    }
    else
    {
      v10 = CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(v43, v39, v9, v44, v19);
    }
    if ( v10 < 0 )
    {
      if ( !(_BYTE)v8
        || (LogAdapter::TraceAtLevelIfFailed<long,>(
              v33,
              (unsigned int)v10,
              "Deletion of directory failed...moving to CbsTemp"),
            v10 = MoveToCbsTemp(v19, 0, 0),
            v10 < 0) )
      {
        LODWORD(v48) = v10;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed removing directory: {}",
            (__int64)&v47);
          v43 = (CRecursiveRemoveDirectory *)&v48;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v35,
            3,
            (unsigned int)": {}",
            (__int64)&v43);
        }
        v12 = (unsigned int)v10;
        v13 = 898;
        goto LABEL_22;
      }
    }
    v26 = (int)LogAdapter::g_Logger;
    *(_QWORD *)v41 = v19;
    if ( LogAdapter::g_Logger )
    {
      v27 = v41;
      v36 = "Deletion of: {} successful";
LABEL_67:
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(v26, v25, 1, (_DWORD)v36, (__int64)v27);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  LODWORD(v48) = v21;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to acquire current thread token");
    *(_QWORD *)v41 = &v48;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v24,
      3,
      (unsigned int)": {}",
      (__int64)v41);
  }
  v10 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x336, v22, (const char *)v23, dwCreationDisposition);
LABEL_69:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v44);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v49);
  AutoThreadPriority::~AutoThreadPriority((AutoThreadPriority *)v51);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v46);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v45);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001344c  mov     [rsp-8+arg_8], rbx
0x140013451  push    rbp
0x140013452  push    rsi
0x140013453  push    rdi
0x140013454  push    r12
0x140013456  push    r13
0x140013458  push    r14
0x14001345a  push    r15
0x14001345c  lea     rbp, [rsp-27h]
0x140013461  sub     rsp, 100h
0x140013468  mov     rax, cs:__security_cookie
0x14001346f  xor     rax, rsp
0x140013472  mov     [rbp+57h+var_40], rax
0x140013476  xor     esi, esi
0x140013478  mov     [rbp+57h+var_D0], rcx
0x14001347c  mov     rdi, rcx
0x14001347f  mov     [rbp+57h+var_C0], rsi
0x140013483  lea     rcx, [rbp+57h+var_90]; this
0x140013487  mov     [rsp+130h+lpFileName], rsi
0x14001348c  mov     [rbp+57h+var_B8], rsi
0x140013490  mov     ebx, edx
0x140013492  mov     [rbp+57h+var_B0], r8
0x140013496  call    ??0AutoThreadPriority@@QEAA@_N@Z; AutoThreadPriority::AutoThreadPriority(bool)
0x14001349b  mov     r14d, ebx
0x14001349e  mov     [rbp+57h+var_A0], rsi
0x1400134a2  and     r14d, 10h
0x1400134a6  mov     [rbp+57h+var_98], sil
0x1400134aa  mov     r13d, ebx
0x1400134ad  mov     [rbp+57h+var_C8], rsi
0x1400134b1  and     r13d, 20h
0x1400134b5  mov     eax, ebx
0x1400134b7  and     eax, 8
0x1400134ba  mov     ecx, ebx
0x1400134bc  mov     r12b, bl
0x1400134bf  setnz   r15b
0x1400134c3  and     ecx, 40h
0x1400134c6  setnz   [rsp+130h+var_F0]
0x1400134cb  and     r12b, 1
0x1400134cf  jz      short loc_14001353F
0x1400134d1  test    r14d, r14d
0x1400134d4  jnz     short loc_1400134DF
0x1400134d6  test    r13d, r13d
0x1400134d9  jnz     short loc_1400134DF
0x1400134db  test    eax, eax
0x1400134dd  jz      short loc_14001353F
0x1400134df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400134e6  mov     edi, 80070057h
0x1400134eb  mov     dword ptr [rbp+57h+var_A8], edi
0x1400134ee  test    rcx, rcx
0x1400134f1  jz      short loc_140013532
0x1400134f3  mov     esi, 3
0x1400134f8  lea     r9, aCannotUseConte; "Cannot use ContentsOnly with MoveToCbsT"...
0x1400134ff  mov     r8d, esi
0x140013502  xor     edx, edx
0x140013504  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140013509  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013510  lea     rax, [rbp+57h+var_A8]
0x140013514  mov     qword ptr [rsp+130h+var_E0], rax
0x140013519  lea     r9, asc_140030534; ": {}"
0x140013520  lea     rax, [rsp+130h+var_E0]
0x140013525  mov     r8d, esi
0x140013528  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x14001352d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013532  mov     r9d, edi
0x140013535  mov     edx, 30Bh
0x14001353a  jmp     loc_140013647
0x14001353f  test    ecx, ecx
0x140013541  jz      short loc_1400135A8
0x140013543  test    r12b, r12b
0x140013546  jnz     short loc_1400135A8
0x140013548  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001354f  mov     edi, 80070057h
0x140013554  mov     dword ptr [rbp+57h+var_A8], edi
0x140013557  test    rcx, rcx
0x14001355a  jz      short loc_14001359B
0x14001355c  mov     esi, 3
0x140013561  lea     r9, aCannotUseAllow; "Cannot use AllowReparseRoot without Con"...
0x140013568  mov     r8d, esi
0x14001356b  xor     edx, edx
0x14001356d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140013572  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013579  lea     rax, [rbp+57h+var_A8]
0x14001357d  mov     qword ptr [rsp+130h+var_E0], rax
0x140013582  lea     r9, asc_140030534; ": {}"
0x140013589  lea     rax, [rsp+130h+var_E0]
0x14001358e  mov     r8d, esi
0x140013591  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x140013596  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001359b  mov     r9d, edi
0x14001359e  mov     edx, 310h
0x1400135a3  jmp     loc_140013647
0x1400135a8  mov     rdx, [rbp+57h+var_B0]
0x1400135ac  test    rdx, rdx
0x1400135af  jnz     short loc_14001360A
0x1400135b1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400135b8  mov     edi, 80070057h
0x1400135bd  mov     dword ptr [rbp+57h+var_A8], edi
0x1400135c0  test    rcx, rcx
0x1400135c3  jz      short loc_140013600
0x1400135c5  lea     esi, [rdx+3]
0x1400135c8  mov     r8d, esi
0x1400135cb  lea     r9, aNoDirectorySpe; "No directory specified"
0x1400135d2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400135d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400135de  lea     rax, [rbp+57h+var_A8]
0x1400135e2  mov     qword ptr [rsp+130h+var_E0], rax
0x1400135e7  lea     r9, asc_140030534; ": {}"
0x1400135ee  lea     rax, [rsp+130h+var_E0]
0x1400135f3  mov     r8d, esi
0x1400135f6  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x1400135fb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013600  mov     r9d, edi
0x140013603  mov     edx, 313h
0x140013608  jmp     short loc_140013647
0x14001360a  mov     eax, ebx
0x14001360c  mov     [rdi+14h], ebx
0x14001360f  shr     eax, 1
0x140013611  mov     esi, 3
0x140013616  and     al, 1
0x140013618  mov     [rdi+10h], al
0x14001361b  test    bl, 4
0x14001361e  jz      short loc_14001362F
0x140013620  mov     edx, esi
0x140013622  lea     rcx, [rbp+57h+var_90]
0x140013626  call    ?SetPriority@AutoThreadPriority@@QEAAXW4PriorityType@1@@Z; AutoThreadPriority::SetPriority(AutoThreadPriority::PriorityType)
0x14001362b  mov     rdx, [rbp+57h+var_B0]
0x14001362f  lea     rcx, [rsp+130h+lpFileName]
0x140013634  call    SczAllocFromSz
0x140013639  mov     edi, eax
0x14001363b  test    eax, eax
0x14001363d  jns     short loc_14001365C
0x14001363f  mov     edx, 320h; void *
0x140013644  mov     r9d, eax; char *
0x140013647  mov     rcx, [rbp+5Fh]; this
0x14001364b  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140013652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013657  jmp     loc_1400139B0
0x14001365c  lea     rcx, [rsp+130h+lpFileName]
0x140013661  call    PathPrefix
0x140013666  mov     edi, eax
0x140013668  test    eax, eax
0x14001366a  jns     short loc_140013673
0x14001366c  mov     edx, 321h
0x140013671  jmp     short loc_140013644
0x140013673  mov     rbx, [rsp+130h+lpFileName]
0x140013678  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001367f  mov     qword ptr [rsp+130h+var_E0], rbx
0x140013684  test    r12b, r12b
0x140013687  jz      short loc_140013697
0x140013689  test    rcx, rcx
0x14001368c  jz      short loc_1400136BB
0x14001368e  lea     r9, aDeletingTheCon; "Deleting the contents of directory: {}"
0x140013695  jmp     short loc_1400136A3
0x140013697  test    rcx, rcx
0x14001369a  jz      short loc_1400136BB
0x14001369c  lea     r9, aDeletingDirect; "Deleting directory: {}"
0x1400136a3  mov     r8d, 1
0x1400136a9  lea     rax, [rsp+130h+var_E0]
0x1400136ae  mov     dl, r8b
0x1400136b1  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x1400136b6  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400136bb  lea     rax, ?Privs@BackupRestorePrivilegeAcquisition@RtlSystemUtil@@0QBJB; long const near * const RtlSystemUtil::BackupRestorePrivilegeAcquisition::Privs
0x1400136c2  mov     [rsp+130h+var_D8], rsi
0x1400136c7  lea     rdx, [rsp+130h+var_E0]
0x1400136cc  mov     qword ptr [rsp+130h+var_E0], rax
0x1400136d1  lea     rcx, [rbp+57h+var_A0]
0x1400136d5  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x1400136da  mov     edi, eax
0x1400136dc  test    eax, eax
0x1400136de  jns     short loc_140013741
0x1400136e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400136e7  mov     dword ptr [rbp+57h+var_A8], eax
0x1400136ea  test    rcx, rcx
0x1400136ed  jz      short loc_140013729
0x1400136ef  lea     r9, aFailedToAcquir_0; "Failed to acquire current thread token"
0x1400136f6  mov     r8d, esi
0x1400136f9  xor     edx, edx
0x1400136fb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140013700  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013707  lea     rax, [rbp+57h+var_A8]
0x14001370b  mov     qword ptr [rsp+130h+var_E0], rax
0x140013710  lea     r9, asc_140030534; ": {}"
0x140013717  lea     rax, [rsp+130h+var_E0]
0x14001371c  mov     r8d, esi
0x14001371f  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; int
0x140013724  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x140013729  mov     rcx, [rbp+5Fh]; this
0x14001372d  mov     r9d, edi; char *
0x140013730  mov     edx, 336h; void *
0x140013735  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14001373a  mov     edi, eax
0x14001373c  jmp     loc_1400139B0
0x140013741  mov     rcx, rbx; lpFileName
0x140013744  call    cs:__imp_GetFileAttributesW
0x14001374a  cmp     eax, 0FFFFFFFFh
0x14001374d  jnz     short loc_14001376E
0x14001374f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013756  mov     qword ptr [rsp+130h+var_E0], rbx
0x14001375b  test    rcx, rcx
0x14001375e  jz      loc_1400139AE
0x140013764  lea     rax, [rsp+130h+var_E0]
0x140013769  jmp     loc_140013994
0x14001376e  test    r14d, r14d
0x140013771  jnz     short loc_140013778
0x140013773  test    r13d, r13d
0x140013776  jz      short loc_1400137DF
0x140013778  mov     [rbp+57h+var_A8], rbx
0x14001377c  mov     rcx, rbx
0x14001377f  mov     [rsp+130h+lpFileName], 0
0x140013788  test    r14d, r14d
0x14001378b  jz      short loc_1400137A2
0x14001378d  lea     r8, [rsp+130h+lpFileName]
0x140013792  xor     edx, edx
0x140013794  call    MoveToCbsTemp
0x140013799  mov     r15d, eax
0x14001379c  shr     r15d, 1Fh
0x1400137a0  jmp     short loc_1400137AF
0x1400137a2  xor     r15b, r15b
0x1400137a5  lea     rdx, [rsp+130h+lpFileName]
0x1400137aa  call    RenameToTemp
0x1400137af  test    eax, eax
0x1400137b1  jns     short loc_1400137D1
0x1400137b3  mov     rcx, [rsp+130h+lpFileName]
0x1400137b8  lea     r8, aUnableToMoveDi; "Unable to move directory to temp, will "...
0x1400137bf  mov     edx, eax
0x1400137c1  mov     [rbp+57h+var_A8], rcx
0x1400137c5  mov     [rsp+130h+lpFileName], rbx
0x1400137ca  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1400137cf  jmp     short loc_1400137D6
0x1400137d1  mov     rbx, [rsp+130h+lpFileName]
0x1400137d6  lea     rcx, [rbp+57h+var_A8]
0x1400137da  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400137df  lea     rdx, [rbp+57h+var_C0]
0x1400137e3  mov     rcx, rbx; wchar_t *
0x1400137e6  call    DirectoryFromPath
0x1400137eb  mov     edi, eax
0x1400137ed  test    eax, eax
0x1400137ef  jns     short loc_140013854
0x1400137f1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400137f8  mov     dword ptr [rbp+57h+var_A8], eax
0x1400137fb  test    rcx, rcx
0x1400137fe  jz      short loc_140013847
0x140013800  lea     rax, [rsp+130h+var_E0]
0x140013805  mov     qword ptr [rsp+130h+var_E0], rbx
0x14001380a  lea     r9, aFailedGettingP; "Failed getting parent directory: {}"
0x140013811  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x140013816  mov     r8d, esi
0x140013819  xor     edx, edx
0x14001381b  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140013820  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140013827  lea     rax, [rbp+57h+var_A8]
0x14001382b  mov     [rbp+57h+var_D0], rax
0x14001382f  lea     r9, asc_140030534; ": {}"
0x140013836  lea     rax, [rbp+57h+var_D0]
0x14001383a  mov     r8d, esi
0x14001383d  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x140013842  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140013847  mov     r9d, edi
0x14001384a  mov     edx, 362h
0x14001384f  jmp     loc_140013647
0x140013854  mov     rcx, [rbp+57h+var_C0]; lpFileName
0x140013858  xor     r9d, r9d; lpSecurityAttributes
0x14001385b  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x140013864  mov     edx, 100080h; dwDesiredAccess
0x140013869  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140013871  mov     [rsp+130h+dwCreationDisposition], esi; dwCreationDisposition
0x140013875  lea     r8d, [r9+7]; dwShareMode
0x140013879  call    cs:__imp_CreateFileW
0x14001387f  mov     rdx, rax
0x140013882  lea     rcx, [rbp+57h+var_C8]
0x140013886  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x14001388b  mov     r9, [rbp+57h+var_C8]; void *
0x14001388f  lea     rax, [r9-1]
0x140013893  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140013897  ja      short loc_1400138B2
0x140013899  mov     dl, [rsp+130h+var_F0]; bool
0x14001389d  mov     r8b, r12b; bool
0x1400138a0  mov     rcx, [rbp+57h+var_D0]; this
0x1400138a4  mov     qword ptr [rsp+130h+dwCreationDisposition], rbx; wchar_t *
0x1400138a9  call    ?RemoveDirectoryHelperEx@CRecursiveRemoveDirectory@@AEAAJ_N0PEAXQEB_W@Z; CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(bool,bool,void *,wchar_t const * const)
0x1400138ae  mov     edi, eax
0x1400138b0  jmp     short loc_1400138D6
0x1400138b2  call    cs:__imp_GetLastError
0x1400138b8  mov     edi, eax
0x1400138ba  test    eax, eax
0x1400138bc  jle     short loc_1400138C7
0x1400138be  movzx   edi, ax
0x1400138c1  or      edi, 80070000h
0x1400138c7  lea     eax, [rdi+7FF8FFFEh]
0x1400138cd  cmp     eax, 1
0x1400138d0  jbe     loc_140013980
0x1400138d6  test    edi, edi
0x1400138d8  jns     loc_140013961
0x1400138de  test    r15b, r15b
0x1400138e1  jz      short loc_140013904
0x1400138e3  lea     r8, aDeletionOfDire; "Deletion of directory failed...moving t"...
0x1400138ea  mov     edx, edi
0x1400138ec  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1400138f1  xor     r8d, r8d
0x1400138f4  xor     edx, edx
  ... truncated ...
```
