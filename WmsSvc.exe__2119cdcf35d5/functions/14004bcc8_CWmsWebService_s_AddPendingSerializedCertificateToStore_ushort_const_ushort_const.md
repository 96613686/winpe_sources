# CWmsWebService::s_AddPendingSerializedCertificateToStore(ushort const *,ushort const *)

- ea: `0x14004bcc8`
- end: `0x14004c22d`
- name: `?s_AddPendingSerializedCertificateToStore@CWmsWebService@@CAJPEBG0@Z`
- size: `1381`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x14004cdb0`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14004bcc8`
- `0x1400599e4`
- `0x14005b418`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14004c20d`
- `KERNEL32!CloseHandle` at `0x14004c20d`
- `KERNEL32!GetFileSizeEx` at `0x14004be07`
- `KERNEL32!GetFileSizeEx` at `0x14004be07`
- `KERNEL32!CreateFileW` at `0x14004bd24`
- `KERNEL32!CreateFileW` at `0x14004bd24`
- `KERNEL32!GetLastError` at `0x14004bd37`
- `KERNEL32!GetLastError` at `0x14004be15`
- `KERNEL32!GetLastError` at `0x14004c006`
- `KERNEL32!GetLastError` at `0x14004bd37`
- `KERNEL32!GetLastError` at `0x14004be15`
- `KERNEL32!GetLastError` at `0x14004c006`
- `KERNEL32!IsDebuggerPresent` at `0x14004bd8e`
- `KERNEL32!IsDebuggerPresent` at `0x14004be6c`
- `KERNEL32!IsDebuggerPresent` at `0x14004bf01`
- `KERNEL32!IsDebuggerPresent` at `0x14004bf9f`
- `KERNEL32!IsDebuggerPresent` at `0x14004c05d`
- `KERNEL32!IsDebuggerPresent` at `0x14004c0d8`
- `KERNEL32!IsDebuggerPresent` at `0x14004c17d`
- `KERNEL32!IsDebuggerPresent` at `0x14004bd8e`
- `KERNEL32!IsDebuggerPresent` at `0x14004be6c`
- `KERNEL32!IsDebuggerPresent` at `0x14004bf01`
- `KERNEL32!IsDebuggerPresent` at `0x14004bf9f`
- `KERNEL32!IsDebuggerPresent` at `0x14004c05d`
- `KERNEL32!IsDebuggerPresent` at `0x14004c0d8`
- `KERNEL32!IsDebuggerPresent` at `0x14004c17d`
- `KERNEL32!ReadFile` at `0x14004bff8`
- `KERNEL32!ReadFile` at `0x14004bff8`
- `OLEAUT32!__imp_SysAllocString` at `0x14004c12c`
- `OLEAUT32!__imp_SysAllocString` at `0x14004c12c`
- `OLEAUT32!__imp_SysFreeString` at `0x14004c1fa`
- `OLEAUT32!__imp_SysFreeString` at `0x14004c1fa`

## string_xrefs

- `0x14004bd61`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004be38`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004bee6`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004bf83`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004c029`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004c0b3`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004c161`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004bce4`: `CWmsWebService::s_AddPendingSerializedCertificateToStore\n`
- `0x14004bd5a`: `CWmsWebService::s_AddPendingSerializedCertificateToStore`
- `0x14004be2f`: `CWmsWebService::s_AddPendingSerializedCertificateToStore`
- `0x14004bed1`: `CWmsWebService::s_AddPendingSerializedCertificateToStore`
- `0x14004bf77`: `CWmsWebService::s_AddPendingSerializedCertificateToStore`
- `0x14004c020`: `CWmsWebService::s_AddPendingSerializedCertificateToStore`
- `0x14004c0a8`: `CWmsWebService::s_AddPendingSerializedCertificateToStore`
- `0x14004c155`: `CWmsWebService::s_AddPendingSerializedCertificateToStore`
- `0x14004beb6`: `CWmsWebService::s_AddPendingSerializedCertificateToStorePending certificate "%s" file size of %d is out of range.\n`
- `0x14004c0a1`: `cbSslCertificate == cbRead`
- `0x14004c0e0`: `cbSslCertificate == cbRead`
- `0x14004c1d7`: `CWmsWebService::s_AddPendingSerializedCertificateToStoreAdding pending certificate "%s" to the certificate store.\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::s_AddPendingSerializedCertificateToStore(OLECHAR *psz, LPCWSTR lpFileName)
{
  unsigned __int8 *v3; // r15
  OLECHAR *v4; // r12
  char *FileW; // rax
  char *v7; // r13
  signed int LastError; // eax
  signed int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // r8
  signed int v12; // eax
  DWORD LowPart; // edi
  unsigned __int8 *v14; // rax
  signed int v15; // eax
  wchar_t *v16; // rax
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-48h]
  const unsigned __int16 *hTemplateFilea; // [rsp+30h] [rbp-48h]
  signed int v21; // [rsp+38h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+20h] BYREF

  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  v3 = 0;
  v4 = 0;
  DEBUGMSG(L"CWmsWebService::s_AddPendingSerializedCertificateToStore\n");
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v7 = FileW;
  if ( FileW == (char *)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x969u,
      L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
      L"CBRAEx",
      L"hFile != ((HANDLE)(LONG_PTR)-1)",
      v9);
    if ( IsDebuggerPresent() )
    {
      v21 = v9;
      v10 = 2409;
      hTemplateFilea = L"hFile != ((HANDLE)(LONG_PTR)-1)";
LABEL_8:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v10,
        L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
        L"CBRAEx",
        hTemplateFilea,
        v21);
      goto LABEL_47;
    }
    LODWORD(hTemplateFile) = v9;
    v11 = 2409;
    dwFlagsAndAttributes = L"hFile != ((HANDLE)(LONG_PTR)-1)";
    goto LABEL_11;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x96Cu,
      L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
      L"CBRAEx",
      L"fSuccess",
      v9);
    if ( IsDebuggerPresent() )
    {
      v21 = v9;
      v10 = 2412;
      hTemplateFilea = L"fSuccess";
      goto LABEL_8;
    }
    LODWORD(hTemplateFile) = v9;
    v11 = 2412;
    dwFlagsAndAttributes = L"fSuccess";
    goto LABEL_11;
  }
  LowPart = FileSize.LowPart;
  if ( FileSize.LowPart - 1 <= 0x7FF )
  {
    v14 = (unsigned __int8 *)operator new(FileSize.LowPart);
    v3 = v14;
    if ( v14 )
    {
      if ( !ReadFile(v7, v14, LowPart, &NumberOfBytesRead, 0) )
      {
        v15 = GetLastError();
        v9 = v15;
        if ( v15 > 0 )
          v9 = (unsigned __int16)v15 | 0x80070000;
        if ( v9 >= 0 )
          v9 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          0x97Au,
          L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
          L"CBRAEx",
          L"fSuccess",
          v9);
        if ( IsDebuggerPresent() )
        {
          v21 = v9;
          v10 = 2426;
          hTemplateFilea = L"fSuccess";
          goto LABEL_8;
        }
        LODWORD(hTemplateFile) = v9;
        v11 = 2426;
        dwFlagsAndAttributes = L"fSuccess";
LABEL_11:
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          v11,
          L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
          L"CBRAEx",
          dwFlagsAndAttributes,
          hTemplateFile);
        goto LABEL_47;
      }
      if ( LowPart == NumberOfBytesRead )
      {
        v16 = SysAllocString(psz);
        v4 = v16;
        if ( v16 )
        {
          v9 = VerifySslCertificate(v16, v3, LowPart);
          if ( v9 >= 0 )
          {
            DEBUGMSG(
              L"CWmsWebService::s_AddPendingSerializedCertificateToStoreAdding pending certificate \"%s\" to the certificate store.\n",
              lpFileName);
            v9 = AddSerializedCertificateToStore(v3, LowPart);
          }
        }
        else
        {
          v9 = -2147024882;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
            0x97Fu,
            L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
            L"CPR",
            L"bstrHostName",
            -2147024882);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              2431,
              L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
              L"CPR",
              L"bstrHostName",
              -2147024882);
          }
          else
          {
            LODWORD(hTemplateFile) = -2147024882;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
              2431,
              L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
              L"CPR",
              L"bstrHostName",
              hTemplateFile);
          }
        }
      }
      else
      {
        v9 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          0x97Bu,
          L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
          L"CBRA",
          L"cbSslCertificate == cbRead",
          -2147467259);
        if ( IsDebuggerPresent() )
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
            2427,
            L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
            L"CBRA",
            L"cbSslCertificate == cbRead",
            -2147467259);
        }
        else
        {
          LODWORD(hTemplateFile) = -2147467259;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
            2427,
            L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
            L"CBRA",
            L"cbSslCertificate == cbRead",
            hTemplateFile);
        }
      }
    }
    else
    {
      v9 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        0x977u,
        L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
        L"CPR",
        L"pSslCertificate",
        -2147024882);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          2423,
          L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
          L"CPR",
          L"pSslCertificate",
          -2147024882);
      }
      else
      {
        LODWORD(hTemplateFile) = -2147024882;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
          2423,
          L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
          L"CPR",
          L"pSslCertificate",
          hTemplateFile);
      }
    }
  }
  else
  {
    DEBUGMSG(
      L"CWmsWebService::s_AddPendingSerializedCertificateToStorePending certificate \"%s\" file size of %d is out of range.\n",
      lpFileName,
      FileSize.LowPart);
    v9 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x973u,
      L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
      L"CHRA",
      L"((HRESULT)0x80070057L)",
      -2147024809);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2419,
        L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
        L"CHRA",
        L"((HRESULT)0x80070057L)",
        -2147024809);
    }
    else
    {
      LODWORD(hTemplateFile) = -2147024809;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        2419,
        L"CWmsWebService::s_AddPendingSerializedCertificateToStore",
        L"CHRA",
        L"((HRESULT)0x80070057L)",
        hTemplateFile);
    }
  }
LABEL_47:
  operator delete(v3);
  SysFreeString(v4);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004bcc8  mov     rax, rsp
0x14004bccb  mov     [rax+8], rbx
0x14004bccf  push    rbp
0x14004bcd0  push    rsi
0x14004bcd1  push    rdi
0x14004bcd2  push    r12
0x14004bcd4  push    r13
0x14004bcd6  push    r14
0x14004bcd8  push    r15
0x14004bcda  sub     rsp, 40h
0x14004bcde  xor     r14d, r14d
0x14004bce1  mov     rbx, rcx
0x14004bce4  lea     rcx, aCwmswebservice_25; "CWmsWebService::s_AddPendingSerializedC"...
0x14004bceb  mov     [rax+20h], r14
0x14004bcef  mov     [rax+18h], r14d
0x14004bcf3  mov     r15d, r14d
0x14004bcf6  mov     r12d, r14d
0x14004bcf9  mov     rsi, rdx
0x14004bcfc  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004bd01  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x14004bd06  xor     r9d, r9d; lpSecurityAttributes
0x14004bd09  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14004bd11  xor     r8d, r8d; dwShareMode
0x14004bd14  mov     edx, 80000000h; dwDesiredAccess
0x14004bd19  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x14004bd21  mov     rcx, rsi; lpFileName
0x14004bd24  call    cs:__imp_CreateFileW
0x14004bd2a  mov     r13, rax
0x14004bd2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004bd31  jnz     loc_14004BDFC
0x14004bd37  call    cs:__imp_GetLastError
0x14004bd3d  mov     ebx, eax
0x14004bd3f  test    eax, eax
0x14004bd41  jle     short loc_14004BD4C
0x14004bd43  movzx   ebx, ax
0x14004bd46  or      ebx, 80070000h
0x14004bd4c  mov     ebp, 80004005h
0x14004bd51  lea     rax, aHfileHandleLon; "hFile != ((HANDLE)(LONG_PTR)-1)"
0x14004bd58  test    ebx, ebx
0x14004bd5a  lea     rsi, aCwmswebservice_46; "CWmsWebService::s_AddPendingSerializedC"...
0x14004bd61  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004bd68  mov     r8, rsi; unsigned __int16 *
0x14004bd6b  cmovns  ebx, ebp
0x14004bd6e  mov     edx, 969h; unsigned int
0x14004bd73  lea     rbp, aCbraex; "CBRAEx"
0x14004bd7a  mov     [rsp+78h+dwFlagsAndAttributes], ebx; int
0x14004bd7e  mov     r9, rbp; unsigned __int16 *
0x14004bd81  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned __int16 *
0x14004bd86  mov     rcx, rdi; unsigned __int16 *
0x14004bd89  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004bd8e  call    cs:__imp_IsDebuggerPresent
0x14004bd94  test    eax, eax
0x14004bd96  lea     rax, aHfileHandleLon; "hFile != ((HANDLE)(LONG_PTR)-1)"
0x14004bd9d  jz      short loc_14004BDD1
0x14004bd9f  mov     [rsp+78h+var_40], ebx
0x14004bda3  mov     r9d, 969h
0x14004bda9  mov     [rsp+78h+hTemplateFile], rax
0x14004bdae  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rbp
0x14004bdb3  mov     r8, rdi
0x14004bdb6  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi
0x14004bdbb  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004bdc2  mov     ecx, 2; unsigned __int8
0x14004bdc7  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004bdcc  jmp     loc_14004C1EF
0x14004bdd1  mov     dword ptr [rsp+78h+hTemplateFile], ebx
0x14004bdd5  mov     r8d, 969h
0x14004bddb  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14004bde0  mov     qword ptr [rsp+78h+dwCreationDisposition], rbp
0x14004bde5  mov     r9, rsi
0x14004bde8  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004bdef  mov     rdx, rdi
0x14004bdf2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004bdf7  jmp     loc_14004C1EF
0x14004bdfc  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x14004be04  mov     rcx, r13; hFile
0x14004be07  call    cs:__imp_GetFileSizeEx
0x14004be0d  test    eax, eax
0x14004be0f  jnz     loc_14004BE9E
0x14004be15  call    cs:__imp_GetLastError
0x14004be1b  mov     ebx, eax
0x14004be1d  test    eax, eax
0x14004be1f  jle     short loc_14004BE2A
0x14004be21  movzx   ebx, ax
0x14004be24  or      ebx, 80070000h
0x14004be2a  mov     ebp, 80004005h
0x14004be2f  lea     rsi, aCwmswebservice_46; "CWmsWebService::s_AddPendingSerializedC"...
0x14004be36  test    ebx, ebx
0x14004be38  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004be3f  lea     r14, aFsuccess; "fSuccess"
0x14004be46  mov     r8, rsi; unsigned __int16 *
0x14004be49  cmovns  ebx, ebp
0x14004be4c  mov     edx, 96Ch; unsigned int
0x14004be51  lea     rbp, aCbraex; "CBRAEx"
0x14004be58  mov     [rsp+78h+dwFlagsAndAttributes], ebx; int
0x14004be5c  mov     r9, rbp; unsigned __int16 *
0x14004be5f  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; unsigned __int16 *
0x14004be64  mov     rcx, rdi; unsigned __int16 *
0x14004be67  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004be6c  call    cs:__imp_IsDebuggerPresent
0x14004be72  test    eax, eax
0x14004be74  jz      short loc_14004BE8A
0x14004be76  mov     [rsp+78h+var_40], ebx
0x14004be7a  mov     r9d, 96Ch
0x14004be80  mov     [rsp+78h+hTemplateFile], r14
0x14004be85  jmp     loc_14004BDAE
0x14004be8a  mov     dword ptr [rsp+78h+hTemplateFile], ebx
0x14004be8e  mov     r8d, 96Ch
0x14004be94  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r14
0x14004be99  jmp     loc_14004BDE0
0x14004be9e  mov     edi, dword ptr [rsp+78h+FileSize]
0x14004bea5  lea     eax, [rdi-1]
0x14004bea8  cmp     eax, 7FFh
0x14004bead  jbe     loc_14004BF4C
0x14004beb3  mov     r8d, edi
0x14004beb6  lea     rcx, aCwmswebservice_11; "CWmsWebService::s_AddPendingSerializedC"...
0x14004bebd  mov     rdx, rsi
0x14004bec0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004bec5  lea     rax, aHresult0x80070; "((HRESULT)0x80070057L)"
0x14004becc  mov     ebx, 80070057h
0x14004bed1  lea     rsi, aCwmswebservice_46; "CWmsWebService::s_AddPendingSerializedC"...
0x14004bed8  mov     [rsp+78h+dwFlagsAndAttributes], ebx; int
0x14004bedc  mov     ebp, 973h
0x14004bee1  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned __int16 *
0x14004bee6  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004beed  mov     r8, rsi; unsigned __int16 *
0x14004bef0  mov     edx, ebp; unsigned int
0x14004bef2  lea     r9, aChra; "CHRA"
0x14004bef9  mov     rcx, rdi; unsigned __int16 *
0x14004befc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004bf01  call    cs:__imp_IsDebuggerPresent
0x14004bf07  test    eax, eax
0x14004bf09  lea     rax, aHresult0x80070; "((HRESULT)0x80070057L)"
0x14004bf10  jz      short loc_14004BF2F
0x14004bf12  mov     [rsp+78h+var_40], ebx
0x14004bf16  mov     r9d, ebp
0x14004bf19  mov     [rsp+78h+hTemplateFile], rax
0x14004bf1e  lea     rax, aChra; "CHRA"
0x14004bf25  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14004bf2a  jmp     loc_14004BDB3
0x14004bf2f  mov     dword ptr [rsp+78h+hTemplateFile], ebx
0x14004bf33  mov     r8d, ebp
0x14004bf36  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14004bf3b  lea     rax, aChra; "CHRA"
0x14004bf42  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x14004bf47  jmp     loc_14004BDE5
0x14004bf4c  mov     rcx, rdi; Size
0x14004bf4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004bf54  mov     r15, rax
0x14004bf57  test    rax, rax
0x14004bf5a  jnz     loc_14004BFE2
0x14004bf60  mov     ebp, 8007000Eh
0x14004bf65  lea     rax, aPsslcertificat; "pSslCertificate"
0x14004bf6c  lea     r14, aCpr; "CPR"
0x14004bf73  mov     [rsp+78h+dwFlagsAndAttributes], ebp; int
0x14004bf77  lea     rsi, aCwmswebservice_46; "CWmsWebService::s_AddPendingSerializedC"...
0x14004bf7e  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned __int16 *
0x14004bf83  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004bf8a  mov     r9, r14; unsigned __int16 *
0x14004bf8d  mov     r8, rsi; unsigned __int16 *
0x14004bf90  mov     rcx, rdi; unsigned __int16 *
0x14004bf93  mov     edx, 977h; unsigned int
0x14004bf98  mov     ebx, ebp
0x14004bf9a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004bf9f  call    cs:__imp_IsDebuggerPresent
0x14004bfa5  test    eax, eax
0x14004bfa7  lea     rax, aPsslcertificat; "pSslCertificate"
0x14004bfae  jz      short loc_14004BFC9
0x14004bfb0  mov     [rsp+78h+var_40], ebp
0x14004bfb4  mov     r9d, 977h
0x14004bfba  mov     [rsp+78h+hTemplateFile], rax
0x14004bfbf  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r14
0x14004bfc4  jmp     loc_14004BDB3
0x14004bfc9  mov     dword ptr [rsp+78h+hTemplateFile], ebp
0x14004bfcd  mov     r8d, 977h
0x14004bfd3  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14004bfd8  mov     qword ptr [rsp+78h+dwCreationDisposition], r14
0x14004bfdd  jmp     loc_14004BDE5
0x14004bfe2  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14004bfea  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOverlapped
0x14004bfef  mov     r8d, edi; nNumberOfBytesToRead
0x14004bff2  mov     rdx, r15; lpBuffer
0x14004bff5  mov     rcx, r13; hFile
0x14004bff8  call    cs:__imp_ReadFile
0x14004bffe  test    eax, eax
0x14004c000  jnz     loc_14004C08F
0x14004c006  call    cs:__imp_GetLastError
0x14004c00c  mov     ebx, eax
0x14004c00e  test    eax, eax
0x14004c010  jle     short loc_14004C01B
0x14004c012  movzx   ebx, ax
0x14004c015  or      ebx, 80070000h
0x14004c01b  mov     ebp, 80004005h
0x14004c020  lea     rsi, aCwmswebservice_46; "CWmsWebService::s_AddPendingSerializedC"...
0x14004c027  test    ebx, ebx
0x14004c029  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004c030  lea     r14, aFsuccess; "fSuccess"
0x14004c037  mov     r8, rsi; unsigned __int16 *
0x14004c03a  cmovns  ebx, ebp
0x14004c03d  mov     edx, 97Ah; unsigned int
0x14004c042  lea     rbp, aCbraex; "CBRAEx"
0x14004c049  mov     [rsp+78h+dwFlagsAndAttributes], ebx; int
0x14004c04d  mov     r9, rbp; unsigned __int16 *
0x14004c050  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; unsigned __int16 *
0x14004c055  mov     rcx, rdi; unsigned __int16 *
0x14004c058  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004c05d  call    cs:__imp_IsDebuggerPresent
0x14004c063  test    eax, eax
0x14004c065  jz      short loc_14004C07B
0x14004c067  mov     [rsp+78h+var_40], ebx
0x14004c06b  mov     r9d, 97Ah
0x14004c071  mov     [rsp+78h+hTemplateFile], r14
0x14004c076  jmp     loc_14004BDAE
0x14004c07b  mov     dword ptr [rsp+78h+hTemplateFile], ebx
0x14004c07f  mov     r8d, 97Ah
0x14004c085  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r14
0x14004c08a  jmp     loc_14004BDE0
0x14004c08f  cmp     edi, [rsp+78h+NumberOfBytesRead]
0x14004c096  jz      loc_14004C129
0x14004c09c  mov     ebp, 80004005h
0x14004c0a1  lea     rax, aCbsslcertifica; "cbSslCertificate == cbRead"
0x14004c0a8  lea     rsi, aCwmswebservice_46; "CWmsWebService::s_AddPendingSerializedC"...
0x14004c0af  mov     [rsp+78h+dwFlagsAndAttributes], ebp; int
0x14004c0b3  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004c0ba  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned __int16 *
0x14004c0bf  mov     r8, rsi; unsigned __int16 *
0x14004c0c2  lea     r9, aCbra; "CBRA"
0x14004c0c9  mov     rcx, rdi; unsigned __int16 *
0x14004c0cc  mov     edx, 97Bh; unsigned int
0x14004c0d1  mov     ebx, ebp
0x14004c0d3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004c0d8  call    cs:__imp_IsDebuggerPresent
0x14004c0de  test    eax, eax
0x14004c0e0  lea     rax, aCbsslcertifica; "cbSslCertificate == cbRead"
0x14004c0e7  jz      short loc_14004C109
0x14004c0e9  mov     [rsp+78h+var_40], ebp
0x14004c0ed  mov     r9d, 97Bh
0x14004c0f3  mov     [rsp+78h+hTemplateFile], rax
0x14004c0f8  lea     rax, aCbra; "CBRA"
0x14004c0ff  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14004c104  jmp     loc_14004BDB3
0x14004c109  mov     dword ptr [rsp+78h+hTemplateFile], ebp
0x14004c10d  mov     r8d, 97Bh
0x14004c113  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14004c118  lea     rax, aCbra; "CBRA"
0x14004c11f  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x14004c124  jmp     loc_14004BDE5
0x14004c129  mov     rcx, rbx; psz
0x14004c12c  call    cs:__imp_SysAllocString
0x14004c132  mov     r12, rax
0x14004c135  test    rax, rax
0x14004c138  jnz     loc_14004C1C0
0x14004c13e  mov     ebp, 8007000Eh
0x14004c143  lea     rax, aBstrhostname; "bstrHostName"
0x14004c14a  lea     r14, aCpr; "CPR"
0x14004c151  mov     [rsp+78h+dwFlagsAndAttributes], ebp; int
0x14004c155  lea     rsi, aCwmswebservice_46; "CWmsWebService::s_AddPendingSerializedC"...
0x14004c15c  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; unsigned __int16 *
0x14004c161  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004c168  mov     r9, r14; unsigned __int16 *
0x14004c16b  mov     r8, rsi; unsigned __int16 *
0x14004c16e  mov     rcx, rdi; unsigned __int16 *
0x14004c171  mov     edx, 97Fh; unsigned int
0x14004c176  mov     ebx, ebp
0x14004c178  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004c17d  call    cs:__imp_IsDebuggerPresent
0x14004c183  test    eax, eax
0x14004c185  lea     rax, aBstrhostname; "bstrHostName"
0x14004c18c  jz      short loc_14004C1A7
0x14004c18e  mov     [rsp+78h+var_40], ebp
0x14004c192  mov     r9d, 97Fh
0x14004c198  mov     [rsp+78h+hTemplateFile], rax
0x14004c19d  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r14
0x14004c1a2  jmp     loc_14004BDB3
0x14004c1a7  mov     dword ptr [rsp+78h+hTemplateFile], ebp
0x14004c1ab  mov     r8d, 97Fh
0x14004c1b1  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x14004c1b6  mov     qword ptr [rsp+78h+dwCreationDisposition], r14
0x14004c1bb  jmp     loc_14004BDE5
0x14004c1c0  mov     r8d, edi; unsigned int
0x14004c1c3  mov     rdx, r15; unsigned __int8 *
0x14004c1c6  mov     rcx, rax; String1
0x14004c1c9  call    ?VerifySslCertificate@@YAJPEAGPEBEK@Z; VerifySslCertificate(ushort *,uchar const *,ulong)
0x14004c1ce  mov     ebx, eax
0x14004c1d0  test    eax, eax
0x14004c1d2  js      short loc_14004C1EF
0x14004c1d4  mov     rdx, rsi
0x14004c1d7  lea     rcx, aCwmswebservice_63; "CWmsWebService::s_AddPendingSerializedC"...
0x14004c1de  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004c1e3  mov     edx, edi; cbCertEncoded
0x14004c1e5  mov     rcx, r15; pbCertEncoded
0x14004c1e8  call    ?AddSerializedCertificateToStore@@YAJPEBEK@Z; AddSerializedCertificateToStore(uchar const *,ulong)
0x14004c1ed  mov     ebx, eax
0x14004c1ef  mov     rcx, r15; Block
0x14004c1f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004c1f7  mov     rcx, r12; bstrString
0x14004c1fa  call    cs:__imp_SysFreeString
0x14004c200  lea     rax, [r13-1]
0x14004c204  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004c208  ja      short loc_14004C213
0x14004c20a  mov     rcx, r13; hObject
  ... truncated ...
```
