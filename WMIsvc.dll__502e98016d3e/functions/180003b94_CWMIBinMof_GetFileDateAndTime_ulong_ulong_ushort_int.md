# CWMIBinMof::GetFileDateAndTime(ulong &,ulong &,ushort *,int)

- ea: `0x180003b94`
- end: `0x180003da3`
- name: `?GetFileDateAndTime@CWMIBinMof@@AEAAHAEAK0PEAGH@Z`
- size: `527`
- prototype: `int(CWMIBinMof *__hidden this, unsigned int *, unsigned int *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002a5c`

## callees

- `0x180003b94`
- `0x180003e10`
- `0x180004120`
- `0x18000ca20`
- `0x180010df0`
- `0x18001855c`
- `0x180018fb4`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d90`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180003d35`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180003d35`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180003c33`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180003c33`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180003d0f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180003d0f`
- `wbemcomn!ErrorTrace` at `0x180003c55`
- `wbemcomn!ErrorTrace` at `0x180003c74`
- `wbemcomn!ErrorTrace` at `0x180003ccf`
- `wbemcomn!ErrorTrace` at `0x180003cee`
- `wbemcomn!ErrorTrace` at `0x180003d69`
- `wbemcomn!ErrorTrace` at `0x180003d88`
- `wbemcomn!ErrorTrace` at `0x180003c55`
- `wbemcomn!ErrorTrace` at `0x180003c74`
- `wbemcomn!ErrorTrace` at `0x180003ccf`
- `wbemcomn!ErrorTrace` at `0x180003cee`
- `wbemcomn!ErrorTrace` at `0x180003d69`
- `wbemcomn!ErrorTrace` at `0x180003d88`

## string_xrefs

- `0x180003d5d`: `GetFullPathName FAILED for filename: \n`
- `0x180003d96`: `CreateFile FAILED for filename:\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWMIBinMof::GetFileDateAndTime(
        CWMIBinMof *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned __int16 *a4)
{
  unsigned int v7; // r14d
  __int64 v8; // rcx
  __int64 v9; // r9
  WCHAR *v10; // rcx
  DWORD v11; // ebx
  DWORD LastError; // eax
  const char *v14; // rdx
  DWORD v15; // ebx
  DWORD v16; // ebx
  LPCWSTR lpFileName; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE hFile; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME CreationTime; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR FilePart; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[1040]; // [rsp+60h] [rbp-A0h] BYREF

  hFile = 0;
  CreationTime = 0;
  LastAccessTime = 0;
  LastWriteTime = 0;
  LocalFileTime = 0;
  v7 = 0;
  CWbemTime::CWbemTime((CWbemTime *)&lpFileName);
  if ( !(unsigned int)CWMIBinMof::ExtractFileNameFromKey(v8, &lpFileName, v9) )
  {
    LastError = GetLastError();
    v14 = "Can't extract filename: \n";
LABEL_8:
    v15 = LastError;
    ErrorTrace(10, v14);
    TranslateAndLog(a4, 0);
    ErrorTrace(10, ": GetlastError returned %ld\n", v15);
    goto LABEL_6;
  }
  if ( (int)CWMIBinMof::OpenFileAndLookForItIfItDoesNotExist(v10, &lpFileName, &hFile) < 0 )
  {
    LastError = GetLastError();
    v14 = "CreateFile FAILED for filename:\n";
    goto LABEL_8;
  }
  if ( GetFileTime(hFile, &CreationTime, &LastAccessTime, &LastWriteTime) )
  {
    FilePart = 0;
    if ( GetFullPathNameW(lpFileName, 0x410u, Buffer, &FilePart) )
    {
      StringCchCopyW(a4, 0x410u, Buffer);
    }
    else
    {
      v16 = GetLastError();
      ErrorTrace(10, "GetFullPathName FAILED for filename: \n");
      TranslateAndLog(a4, 0);
      ErrorTrace(10, ": GetlastError returned %ld\n", v16);
    }
    FileTimeToLocalFileTime(&LastWriteTime, &LocalFileTime);
    *a2 = LocalFileTime.dwLowDateTime;
    *a3 = LocalFileTime.dwHighDateTime;
    v7 = 1;
  }
  else
  {
    v11 = GetLastError();
    ErrorTrace(10, "GetFileTime FAILED for filename:\n");
    TranslateAndLog(a4, 0);
    ErrorTrace(10, ": GetlastError returned %ld\n", v11);
  }
  CloseHandle(hFile);
LABEL_6:
  CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(&lpFileName);
  return v7;
}

```

## disassembly

```asm
0x180003b94  mov     [rsp-8+arg_0], rbx
0x180003b99  push    rbp
0x180003b9a  push    rsi
0x180003b9b  push    r12
0x180003b9d  push    r14
0x180003b9f  push    r15
0x180003ba1  lea     rbp, [rsp-790h]
0x180003ba9  sub     rsp, 890h
0x180003bb0  mov     rax, cs:__security_cookie
0x180003bb7  xor     rax, rsp
0x180003bba  mov     [rbp+7B0h+var_30], rax
0x180003bc1  mov     rsi, r9
0x180003bc4  mov     r12, r8
0x180003bc7  mov     r15, rdx
0x180003bca  xor     ebx, ebx
0x180003bcc  mov     [rsp+8B0h+hFile], rbx
0x180003bd1  mov     qword ptr [rsp+8B0h+CreationTime.dwLowDateTime], rbx
0x180003bd6  mov     qword ptr [rsp+8B0h+LastAccessTime.dwLowDateTime], rbx
0x180003bdb  mov     qword ptr [rsp+8B0h+LastWriteTime.dwLowDateTime], rbx
0x180003be0  mov     qword ptr [rsp+8B0h+LocalFileTime.dwLowDateTime], rbx
0x180003be5  mov     r14d, ebx
0x180003be8  lea     rcx, [rsp+8B0h+lpFileName]; this
0x180003bed  call    ??0CWbemTime@@QEAA@XZ; CWbemTime::CWbemTime(void)
0x180003bf2  nop
0x180003bf3  mov     r8, r9
0x180003bf6  lea     rdx, [rsp+8B0h+lpFileName]
0x180003bfb  call    ?ExtractFileNameFromKey@CWMIBinMof@@AEAAHAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@PEAG@Z; CWMIBinMof::ExtractFileNameFromKey(std::unique_ptr<ushort [0]> &,ushort *)
0x180003c00  test    eax, eax
0x180003c02  jz      loc_180003CBA
0x180003c08  lea     r8, [rsp+8B0h+hFile]
0x180003c0d  lea     rdx, [rsp+8B0h+lpFileName]
0x180003c12  call    ?OpenFileAndLookForItIfItDoesNotExist@CWMIBinMof@@AEAAJAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@AEAPEAX@Z; CWMIBinMof::OpenFileAndLookForItIfItDoesNotExist(std::unique_ptr<ushort [0]> &,void * &)
0x180003c17  test    eax, eax
0x180003c19  js      loc_180003D90
0x180003c1f  lea     r9, [rsp+8B0h+LastWriteTime]; lpLastWriteTime
0x180003c24  lea     r8, [rsp+8B0h+LastAccessTime]; lpLastAccessTime
0x180003c29  lea     rdx, [rsp+8B0h+CreationTime]; lpCreationTime
0x180003c2e  mov     rcx, [rsp+8B0h+hFile]; hFile
0x180003c33  call    cs:__imp_GetFileTime
0x180003c39  test    eax, eax
0x180003c3b  jnz     loc_180003CF6
0x180003c41  call    cs:__imp_GetLastError
0x180003c47  mov     ebx, eax
0x180003c49  lea     rdx, aGetfiletimeFai; "GetFileTime FAILED for filename:\n"
0x180003c50  mov     ecx, 0Ah
0x180003c55  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180003c5b  xor     edx, edx; int
0x180003c5d  mov     rcx, rsi; lpWideCharStr
0x180003c60  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x180003c65  mov     r8d, ebx
0x180003c68  lea     rdx, aGetlasterrorRe_0; ": GetlastError returned %ld\n"
0x180003c6f  mov     ecx, 0Ah
0x180003c74  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180003c7a  mov     rcx, [rsp+8B0h+hFile]; hObject
0x180003c7f  call    cs:__imp_CloseHandle
0x180003c85  nop
0x180003c86  lea     rcx, [rsp+8B0h+lpFileName]
0x180003c8b  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x180003c90  mov     eax, r14d
0x180003c93  mov     rcx, [rbp+7B0h+var_30]
0x180003c9a  xor     rcx, rsp; StackCookie
0x180003c9d  call    __security_check_cookie
0x180003ca2  mov     rbx, [rsp+8B0h+arg_0]
0x180003caa  add     rsp, 890h
0x180003cb1  pop     r15
0x180003cb3  pop     r14
0x180003cb5  pop     r12
0x180003cb7  pop     rsi
0x180003cb8  pop     rbp
0x180003cb9  retn
0x180003cba  call    cs:__imp_GetLastError
0x180003cc0  nop
0x180003cc1  lea     rdx, aCanTExtractFil; "Can't extract filename: \n"
0x180003cc8  mov     ebx, eax
0x180003cca  mov     ecx, 0Ah
0x180003ccf  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180003cd5  xor     edx, edx; int
0x180003cd7  mov     rcx, rsi; lpWideCharStr
0x180003cda  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x180003cdf  mov     r8d, ebx
0x180003ce2  lea     rdx, aGetlasterrorRe_0; ": GetlastError returned %ld\n"
0x180003ce9  mov     ecx, 0Ah
0x180003cee  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180003cf4  jmp     short loc_180003C86
0x180003cf6  mov     [rsp+8B0h+FilePart], rbx
0x180003cfb  lea     r9, [rsp+8B0h+FilePart]; lpFilePart
0x180003d00  lea     r8, [rsp+8B0h+Buffer]; lpBuffer
0x180003d05  mov     edx, 410h; nBufferLength
0x180003d0a  mov     rcx, [rsp+8B0h+lpFileName]; lpFileName
0x180003d0f  call    cs:__imp_GetFullPathNameW
0x180003d15  test    eax, eax
0x180003d17  jz      short loc_180003D55
0x180003d19  lea     r8, [rsp+8B0h+Buffer]; unsigned __int16 *
0x180003d1e  mov     edx, 410h; unsigned __int64
0x180003d23  mov     rcx, rsi; unsigned __int16 *
0x180003d26  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003d2b  lea     rdx, [rsp+8B0h+LocalFileTime]; lpLocalFileTime
0x180003d30  lea     rcx, [rsp+8B0h+LastWriteTime]; lpFileTime
0x180003d35  call    cs:__imp_FileTimeToLocalFileTime
0x180003d3b  mov     eax, [rsp+8B0h+LocalFileTime.dwLowDateTime]
0x180003d3f  mov     [r15], eax
0x180003d42  mov     eax, [rsp+8B0h+LocalFileTime.dwHighDateTime]
0x180003d46  mov     [r12], eax
0x180003d4a  mov     r14d, 1
0x180003d50  jmp     loc_180003C7A
0x180003d55  call    cs:__imp_GetLastError
0x180003d5b  mov     ebx, eax
0x180003d5d  lea     rdx, aGetfullpathnam; "GetFullPathName FAILED for filename: \n"
0x180003d64  mov     ecx, 0Ah
0x180003d69  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180003d6f  xor     edx, edx; int
0x180003d71  mov     rcx, rsi; lpWideCharStr
0x180003d74  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x180003d79  mov     r8d, ebx
0x180003d7c  lea     rdx, aGetlasterrorRe_0; ": GetlastError returned %ld\n"
0x180003d83  mov     ecx, 0Ah
0x180003d88  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180003d8e  jmp     short loc_180003D2B
0x180003d90  call    cs:__imp_GetLastError
0x180003d96  lea     rdx, aCreatefileFail; "CreateFile FAILED for filename:\n"
0x180003d9d  jmp     loc_180003CC8
```
