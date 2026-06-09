# Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier(ushort *,unsigned __int64,ushort const *)

- ea: `0x1801fc370`
- end: `0x1801fc62e`
- name: `?GetLegacySdbIdentifier@SdbUtils@Appraiser@Compat@Windows@@SAJPEAG_KPEBG@Z`
- size: `702`
- prototype: `static int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801fd5c0`

## callees

- `0x180008570`
- `0x180011d94`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1801fc370`

## import_xrefs

- `KERNEL32!GetFileTime` at `0x1801fc455`
- `KERNEL32!GetFileTime` at `0x1801fc455`
- `KERNEL32!GetFileSizeEx` at `0x1801fc50a`
- `KERNEL32!GetFileSizeEx` at `0x1801fc50a`
- `KERNEL32!FileTimeToSystemTime` at `0x1801fc4c2`
- `KERNEL32!FileTimeToSystemTime` at `0x1801fc4c2`
- `KERNEL32!CreateFileW` at `0x1801fc3da`
- `KERNEL32!CreateFileW` at `0x1801fc3da`
- `KERNEL32!CloseHandle` at `0x1801fc5ff`
- `KERNEL32!CloseHandle` at `0x1801fc5ff`
- `KERNEL32!GetLastError` at `0x1801fc3e9`
- `KERNEL32!GetLastError` at `0x1801fc408`
- `KERNEL32!GetLastError` at `0x1801fc45f`
- `KERNEL32!GetLastError` at `0x1801fc47e`
- `KERNEL32!GetLastError` at `0x1801fc4cc`
- `KERNEL32!GetLastError` at `0x1801fc4eb`
- `KERNEL32!GetLastError` at `0x1801fc514`
- `KERNEL32!GetLastError` at `0x1801fc533`
- `KERNEL32!GetLastError` at `0x1801fc3e9`
- `KERNEL32!GetLastError` at `0x1801fc408`
- `KERNEL32!GetLastError` at `0x1801fc45f`
- `KERNEL32!GetLastError` at `0x1801fc47e`
- `KERNEL32!GetLastError` at `0x1801fc4cc`
- `KERNEL32!GetLastError` at `0x1801fc4eb`
- `KERNEL32!GetLastError` at `0x1801fc514`
- `KERNEL32!GetLastError` at `0x1801fc533`
- `SHLWAPI!PathFindFileNameW` at `0x1801fc56d`
- `SHLWAPI!PathFindFileNameW` at `0x1801fc56d`

## string_xrefs

- `0x1801fc434`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fc499`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fc5ee`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fc412`: `Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier`
- `0x1801fc4a4`: `Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier`
- `0x1801fc5e2`: `Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier`
- `0x1801fc423`: `Error opening Sdb %ls: [%d].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  HANDLE FileW; // rax
  void *v5; // r13
  signed int v6; // eax
  signed int v7; // ebx
  signed int v8; // eax
  char v9; // dl
  const char *v10; // rax
  signed int v11; // eax
  signed int LastError; // eax
  int wSecond; // ebx
  int wMinute; // edi
  int wHour; // esi
  int wDay; // r14d
  int wMonth; // r15d
  DWORD wYear; // r12d
  LPWSTR FileNameW; // rax
  int v20; // eax
  const char *dwCreationDisposition; // [rsp+20h] [rbp-59h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-51h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-51h]
  const char *hTemplateFile; // [rsp+30h] [rbp-49h]
  DWORD v26; // [rsp+38h] [rbp-41h]
  struct _FILETIME LastWriteTime; // [rsp+60h] [rbp-19h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp-11h] BYREF
  LPCWSTR pszPath; // [rsp+70h] [rbp-9h]
  unsigned __int16 *v30; // [rsp+78h] [rbp-1h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp+7h] BYREF

  pszPath = a3;
  v30 = a1;
  LastWriteTime = 0;
  FileSize.QuadPart = 0;
  SystemTime = 0;
  FileW = CreateFileW(a3, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
    {
      if ( FileTimeToSystemTime(&LastWriteTime, &SystemTime) )
      {
        if ( GetFileSizeEx(v5, &FileSize) )
        {
          wSecond = SystemTime.wSecond;
          wMinute = SystemTime.wMinute;
          wHour = SystemTime.wHour;
          wDay = SystemTime.wDay;
          wMonth = SystemTime.wMonth;
          wYear = SystemTime.wYear;
          FileNameW = PathFindFileNameW(pszPath);
          LODWORD(hTemplateFile) = wMonth;
          dwFlagsAndAttributes[0] = wYear;
          LODWORD(dwCreationDisposition) = FileSize.LowPart;
          v20 = StringCchPrintfW(
                  v30,
                  0x104u,
                  L"Sdb FileName: [%ls] Size: [%d] Modified: [%.4d-%.2d-%.2dT%.2d:%.2d:%.2d]",
                  FileNameW,
                  dwCreationDisposition,
                  *(_QWORD *)dwFlagsAndAttributes,
                  hTemplateFile,
                  wDay,
                  wHour,
                  wMinute,
                  wSecond);
          v7 = v20;
          if ( v20 >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x82Du,
                "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
                "Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier",
                "Error formatting string: [0x%x].",
                v20);
            v7 = 0;
            goto LABEL_32;
          }
          LODWORD(hTemplateFile) = v20;
          dwFlagsAndAttributesa = "Error formatting string: [0x%x].";
          v9 = 45;
LABEL_14:
          LODWORD(dwCreationDisposition) = v7;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            v9,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier",
            dwCreationDisposition,
            (int)dwFlagsAndAttributesa,
            hTemplateFile);
LABEL_32:
          CloseHandle(v5);
          return (unsigned int)v7;
        }
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2147467259;
        LODWORD(hTemplateFile) = GetLastError();
        v9 = 31;
        v10 = "GetFileSizeEx failed: [%d].";
      }
      else
      {
        v11 = GetLastError();
        v7 = v11;
        if ( v11 > 0 )
          v7 = (unsigned __int16)v11 | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2147467259;
        LODWORD(hTemplateFile) = GetLastError();
        v9 = 26;
        v10 = "FileTimeToSystemTime failed: [%d].";
      }
    }
    else
    {
      v8 = GetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      LODWORD(hTemplateFile) = GetLastError();
      v9 = 21;
      v10 = "GetFileTime failed: [%d].";
    }
    LODWORD(dwFlagsAndAttributesa) = (_DWORD)v10;
    goto LABEL_14;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2147467259;
  v26 = GetLastError();
  LODWORD(dwCreationDisposition) = v7;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    16,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
    "Windows::Compat::Appraiser::SdbUtils::GetLegacySdbIdentifier",
    dwCreationDisposition,
    (int)"Error opening Sdb %ls: [%d].",
    (const char *)a3,
    v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801fc370  mov     [rsp-8+arg_8], rbx
0x1801fc375  push    rbp
0x1801fc376  push    rsi
0x1801fc377  push    rdi
0x1801fc378  push    r12
0x1801fc37a  push    r13
0x1801fc37c  push    r14
0x1801fc37e  push    r15
0x1801fc380  lea     rbp, [rsp-27h]
0x1801fc385  sub     rsp, 0A0h
0x1801fc38c  mov     rax, cs:__security_cookie
0x1801fc393  xor     rax, rsp
0x1801fc396  mov     [rbp+57h+var_40], rax
0x1801fc39a  xor     esi, esi
0x1801fc39c  mov     [rbp+57h+pszPath], r8
0x1801fc3a0  mov     rdi, r8
0x1801fc3a3  mov     [rbp+57h+var_58], rcx
0x1801fc3a7  xorps   xmm0, xmm0
0x1801fc3aa  mov     [rsp+0D0h+hTemplateFile], rsi; hTemplateFile
0x1801fc3af  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801fc3b7  xor     r9d, r9d; lpSecurityAttributes
0x1801fc3ba  lea     r8d, [rsi+7]; dwShareMode
0x1801fc3be  mov     qword ptr [rbp+57h+LastWriteTime.dwLowDateTime], rsi
0x1801fc3c2  mov     edx, 80000000h; dwDesiredAccess
0x1801fc3c7  mov     qword ptr [rbp+57h+FileSize], rsi
0x1801fc3cb  mov     rcx, rdi; lpFileName
0x1801fc3ce  mov     dword ptr [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1801fc3d6  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1801fc3da  call    cs:__imp_CreateFileW
0x1801fc3e0  mov     r13, rax
0x1801fc3e3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801fc3e7  jnz     short loc_1801FC449
0x1801fc3e9  call    cs:__imp_GetLastError
0x1801fc3ef  mov     ebx, eax
0x1801fc3f1  test    eax, eax
0x1801fc3f3  jle     short loc_1801FC3FE
0x1801fc3f5  movzx   ebx, ax
0x1801fc3f8  or      ebx, 80070000h
0x1801fc3fe  mov     eax, 80004005h
0x1801fc403  test    ebx, ebx
0x1801fc405  cmovns  ebx, eax
0x1801fc408  call    cs:__imp_GetLastError
0x1801fc40e  mov     [rsp+0D0h+var_98], eax
0x1801fc412  lea     r9, aWindowsCompatA_149; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fc419  mov     [rsp+0D0h+hTemplateFile], rdi; char *
0x1801fc41e  mov     edx, 810h; bool
0x1801fc423  lea     rax, aErrorOpeningSd; "Error opening Sdb %ls: [%d]."
0x1801fc42a  mov     ecx, 1; this
0x1801fc42f  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; int
0x1801fc434  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fc43b  mov     dword ptr [rsp+0D0h+dwCreationDisposition], ebx; char *
0x1801fc43f  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fc444  jmp     loc_1801FC605
0x1801fc449  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x1801fc44d  xor     r8d, r8d; lpLastAccessTime
0x1801fc450  xor     edx, edx; lpCreationTime
0x1801fc452  mov     rcx, r13; hFile
0x1801fc455  call    cs:__imp_GetFileTime
0x1801fc45b  test    eax, eax
0x1801fc45d  jnz     short loc_1801FC4BA
0x1801fc45f  call    cs:__imp_GetLastError
0x1801fc465  mov     ebx, eax
0x1801fc467  test    eax, eax
0x1801fc469  jle     short loc_1801FC474
0x1801fc46b  movzx   ebx, ax
0x1801fc46e  or      ebx, 80070000h
0x1801fc474  test    ebx, ebx
0x1801fc476  mov     eax, 80004005h
0x1801fc47b  cmovns  ebx, eax
0x1801fc47e  call    cs:__imp_GetLastError
0x1801fc484  mov     dword ptr [rsp+0D0h+hTemplateFile], eax; char *
0x1801fc488  mov     edx, 815h; bool
0x1801fc48d  lea     rax, aGetfiletimeFai; "GetFileTime failed: [%d]."
0x1801fc494  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; int
0x1801fc499  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fc4a0  mov     dword ptr [rsp+0D0h+dwCreationDisposition], ebx; char *
0x1801fc4a4  lea     r9, aWindowsCompatA_149; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fc4ab  mov     ecx, 1; this
0x1801fc4b0  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fc4b5  jmp     loc_1801FC5FC
0x1801fc4ba  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1801fc4be  lea     rcx, [rbp+57h+LastWriteTime]; lpFileTime
0x1801fc4c2  call    cs:__imp_FileTimeToSystemTime
0x1801fc4c8  test    eax, eax
0x1801fc4ca  jnz     short loc_1801FC503
0x1801fc4cc  call    cs:__imp_GetLastError
0x1801fc4d2  mov     ebx, eax
0x1801fc4d4  test    eax, eax
0x1801fc4d6  jle     short loc_1801FC4E1
0x1801fc4d8  movzx   ebx, ax
0x1801fc4db  or      ebx, 80070000h
0x1801fc4e1  test    ebx, ebx
0x1801fc4e3  mov     eax, 80004005h
0x1801fc4e8  cmovns  ebx, eax
0x1801fc4eb  call    cs:__imp_GetLastError
0x1801fc4f1  mov     dword ptr [rsp+0D0h+hTemplateFile], eax
0x1801fc4f5  mov     edx, 81Ah
0x1801fc4fa  lea     rax, aFiletimetosyst; "FileTimeToSystemTime failed: [%d]."
0x1801fc501  jmp     short loc_1801FC494
0x1801fc503  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1801fc507  mov     rcx, r13; hFile
0x1801fc50a  call    cs:__imp_GetFileSizeEx
0x1801fc510  test    eax, eax
0x1801fc512  jnz     short loc_1801FC54E
0x1801fc514  call    cs:__imp_GetLastError
0x1801fc51a  mov     ebx, eax
0x1801fc51c  test    eax, eax
0x1801fc51e  jle     short loc_1801FC529
0x1801fc520  movzx   ebx, ax
0x1801fc523  or      ebx, 80070000h
0x1801fc529  test    ebx, ebx
0x1801fc52b  mov     eax, 80004005h
0x1801fc530  cmovns  ebx, eax
0x1801fc533  call    cs:__imp_GetLastError
0x1801fc539  mov     dword ptr [rsp+0D0h+hTemplateFile], eax
0x1801fc53d  mov     edx, 81Fh
0x1801fc542  lea     rax, aGetfilesizeexF; "GetFileSizeEx failed: [%d]."
0x1801fc549  jmp     loc_1801FC494
0x1801fc54e  mov     rcx, [rbp+57h+pszPath]; pszPath
0x1801fc552  movzx   ebx, [rbp+57h+SystemTime.wSecond]
0x1801fc556  movzx   edi, [rbp+57h+SystemTime.wMinute]
0x1801fc55a  movzx   esi, [rbp+57h+SystemTime.wHour]
0x1801fc55e  movzx   r14d, [rbp+57h+SystemTime.wDay]
0x1801fc563  movzx   r15d, [rbp+57h+SystemTime.wMonth]
0x1801fc568  movzx   r12d, [rbp+57h+SystemTime.wYear]
0x1801fc56d  call    cs:__imp_PathFindFileNameW
0x1801fc573  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x1801fc577  lea     r8, aSdbFilenameLsS; "Sdb FileName: [%ls] Size: [%d] Modified"...
0x1801fc57e  mov     [rsp+0D0h+var_80], ebx
0x1801fc582  mov     r9, rax
0x1801fc585  mov     eax, dword ptr [rbp+57h+FileSize]
0x1801fc588  mov     edx, 104h; unsigned __int64
0x1801fc58d  mov     [rsp+0D0h+var_88], edi
0x1801fc591  mov     [rsp+0D0h+var_90], esi
0x1801fc595  mov     [rsp+0D0h+var_98], r14d
0x1801fc59a  mov     dword ptr [rsp+0D0h+hTemplateFile], r15d
0x1801fc59f  mov     [rsp+0D0h+dwFlagsAndAttributes], r12d
0x1801fc5a4  mov     dword ptr [rsp+0D0h+dwCreationDisposition], eax
0x1801fc5a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801fc5ad  mov     ebx, eax
0x1801fc5af  test    eax, eax
0x1801fc5b1  jns     short loc_1801FC5CD
0x1801fc5b3  lea     r9, aErrorFormattin; "Error formatting string: [0x%x]."
0x1801fc5ba  mov     dword ptr [rsp+0D0h+hTemplateFile], eax
0x1801fc5be  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], r9
0x1801fc5c3  mov     edx, 82Dh
0x1801fc5c8  jmp     loc_1801FC499
0x1801fc5cd  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fc5d3  test    al, 1
0x1801fc5d5  jz      short loc_1801FC5FA
0x1801fc5d7  lea     r9, aErrorFormattin; "Error formatting string: [0x%x]."
0x1801fc5de  mov     dword ptr [rsp+0D0h+dwCreationDisposition], ebx
0x1801fc5e2  lea     r8, aWindowsCompatA_149; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fc5e9  mov     ecx, 82Dh; unsigned int
0x1801fc5ee  lea     rdx, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fc5f5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fc5fa  xor     ebx, ebx
0x1801fc5fc  mov     rcx, r13; hObject
0x1801fc5ff  call    cs:__imp_CloseHandle
0x1801fc605  mov     eax, ebx
0x1801fc607  mov     rcx, [rbp+57h+var_40]
0x1801fc60b  xor     rcx, rsp; StackCookie
0x1801fc60e  call    __security_check_cookie
0x1801fc613  mov     rbx, [rsp+0D0h+arg_8]
0x1801fc61b  add     rsp, 0A0h
0x1801fc622  pop     r15
0x1801fc624  pop     r14
0x1801fc626  pop     r13
0x1801fc628  pop     r12
0x1801fc62a  pop     rdi
0x1801fc62b  pop     rsi
0x1801fc62c  pop     rbp
0x1801fc62d  retn
```
