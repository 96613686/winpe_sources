# DeleteFileEx2

- ea: `0x180053994`
- end: `0x180053e66`
- name: `DeleteFileEx2`
- size: `1234`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180049234`
- `0x18004aca0`
- `0x18004bc94`
- `0x1800538b8`
- `0x180053e6c`

## callees

- `0x1800078b0`
- `0x180008544`
- `0x180052bbc`
- `0x180052f10`
- `0x180053040`
- `0x180053234`
- `0x180053994`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180053bd7`
- `ntdll!NtSetInformationFile` at `0x180053c0b`
- `ntdll!NtSetInformationFile` at `0x180053bd7`
- `ntdll!NtSetInformationFile` at `0x180053c0b`
- `ntdll!RtlNtStatusToDosError` at `0x180053be3`
- `ntdll!RtlNtStatusToDosError` at `0x180053c1e`
- `ntdll!RtlNtStatusToDosError` at `0x180053be3`
- `ntdll!RtlNtStatusToDosError` at `0x180053c1e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180053b18`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180053b18`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180053b6d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180053b6d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180053a51`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180053a51`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180053a92`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180053cbd`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180053a92`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180053cbd`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180053b49`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x180053b49`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180053d83`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180053d83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053a17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053c99`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053a17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053c99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053b61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053d2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053e08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053b61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053d2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053e08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053b53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053d1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053dbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053dfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053b53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053d1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053dbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053dfa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053ac8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053ac8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053e39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053e10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053cef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053cef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053d6b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180053a6e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180053a6e`

## string_xrefs

- `0x180053c31`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x180053cd0`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x180053c59`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x180053b9b`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x180053b75`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x180053ddc`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x180053d95`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x180053e19`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`
- `0x180053d38`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x180053d00`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180053d9e`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180053d47`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall DeleteFileEx2(__int64 a1)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // r12
  const WCHAR *v4; // rax
  WCHAR *v5; // rsi
  HANDLE FileW; // r15
  DWORD LastError; // edi
  int v8; // eax
  ULONG v9; // eax
  int v10; // eax
  DWORD v11; // eax
  const wchar_t *v12; // r8
  DWORD v13; // eax
  const wchar_t *v14; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-99h]
  __int64 dwCreationDispositiona; // [rsp+20h] [rbp-99h]
  char v20[4]; // [rsp+40h] [rbp-79h] BYREF
  DWORD StringLength; // [rsp+44h] [rbp-75h] BYREF
  __int64 v22; // [rsp+48h] [rbp-71h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
  _OWORD v24[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v25; // [rsp+88h] [rbp-31h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-29h] BYREF

  v2 = (unsigned __int16 *)FormLongPathName();
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x", a1, LastError);
    goto LABEL_30;
  }
  v22 = 0;
  v4 = (const WCHAR *)PrepareUnicodePathEx(v2);
  v5 = (WCHAR *)v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x", v3, LastError);
    goto LABEL_28;
  }
  FileW = CreateFileW(v4, 0x10180u, 7u, 0, 3u, 0x2200000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v13 = GetLastError();
    LastError = v13;
    if ( v13 == 5 )
    {
      if ( DeleteFileW(v5) )
        goto LABEL_26;
      v13 = GetLastError();
      LastError = v13;
      v14 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
    }
    else
    {
      v14 = L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x";
    }
    LODWORD(dwCreationDisposition) = v13;
    LibLog(&g_WdsLibLog, 50331648, v14, v5, dwCreationDisposition);
    goto LABEL_26;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  v25 = 0;
  memset(v24, 0, sizeof(v24));
  if ( GetFileInformationByHandle(FileW, &FileInformation)
    && GetFileInformationByHandleEx(FileW, FileBasicInfo, v24, 0x28u) )
  {
    LODWORD(v25) = 0x2000;
    if ( SetFileInformationByHandle(FileW, FileBasicInfo, v24, 0x28u) )
    {
      LastError = 0;
      if ( FileInformation.nNumberOfLinks > 1 )
        LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Will not restore attributes on hardlinks of [%s]", v5);
      v20[0] = 1;
      IoStatusBlock = 0;
      v8 = NtSetInformationFile(FileW, &IoStatusBlock, v20, 1u, FileDispositionInformation);
      if ( v8 < 0 )
      {
        v9 = RtlNtStatusToDosError(v8);
        StringLength = 1;
        LastError = v9;
        v10 = NtSetInformationFile(FileW, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
        if ( v10 >= 0 )
        {
          LastError = 0;
        }
        else
        {
          if ( v10 != -1073741821 )
            LastError = RtlNtStatusToDosError(v10);
          if ( LastError )
          {
            LODWORD(dwCreationDispositiona) = LastError;
            LibLog(
              &g_WdsLibLog,
              50331648,
              L"DeleteFileEx: Unable to remove [%s]; GLE = 0x%x",
              v5,
              dwCreationDispositiona);
          }
        }
      }
      goto LABEL_20;
    }
    v11 = GetLastError();
    v12 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
  }
  else
  {
    v11 = GetLastError();
    v12 = L"DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x";
  }
  LODWORD(dwCreationDisposition) = v11;
  LastError = v11;
  LibLog(&g_WdsLibLog, 50331648, v12, v5, dwCreationDisposition);
LABEL_20:
  CloseHandle(FileW);
LABEL_26:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v5);
LABEL_28:
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v3);
LABEL_30:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180053994  push    rbp
0x180053996  push    rbx
0x180053997  push    rsi
0x180053998  push    rdi
0x180053999  push    r12
0x18005399b  push    r13
0x18005399d  push    r14
0x18005399f  push    r15
0x1800539a1  lea     rbp, [rsp-1Fh]
0x1800539a6  sub     rsp, 0D8h
0x1800539ad  mov     rax, cs:__security_cookie
0x1800539b4  xor     rax, rsp
0x1800539b7  mov     [rbp+57h+var_48], rax
0x1800539bb  mov     rbx, rcx
0x1800539be  call    FormLongPathName
0x1800539c3  mov     r12, rax
0x1800539c6  test    rax, rax
0x1800539c9  jz      loc_180053E10
0x1800539cf  lea     rdx, [rbp+57h+var_C8]
0x1800539d3  mov     [rbp+57h+var_C8], 0
0x1800539db  mov     rcx, rax; unsigned __int16 *
0x1800539de  call    PrepareUnicodePathEx
0x1800539e3  mov     rsi, rax
0x1800539e6  test    rax, rax
0x1800539e9  jz      loc_180053DD3
0x1800539ef  xor     r9d, r9d; lpSecurityAttributes
0x1800539f2  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x1800539fb  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180053a03  mov     edx, 10180h; dwDesiredAccess
0x180053a08  mov     rcx, rax; lpFileName
0x180053a0b  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180053a13  lea     r8d, [r9+7]; dwShareMode
0x180053a17  call    cs:__imp_CreateFileW
0x180053a1d  mov     r15, rax
0x180053a20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180053a24  jz      loc_180053D73
0x180053a2a  xorps   xmm0, xmm0
0x180053a2d  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180053a31  xor     eax, eax
0x180053a33  mov     rcx, r15; hFile
0x180053a36  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180053a3a  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180053a3d  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180053a41  mov     [rbp+57h+var_88], rax
0x180053a45  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180053a49  movups  [rbp+57h+var_A8], xmm0
0x180053a4d  movups  [rbp+57h+var_98], xmm0
0x180053a51  call    cs:__imp_GetFileInformationByHandle
0x180053a57  test    eax, eax
0x180053a59  jz      loc_180053D41
0x180053a5f  mov     r9d, 28h ; '('; dwBufferSize
0x180053a65  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180053a69  xor     edx, edx; FileInformationClass
0x180053a6b  mov     rcx, r15; hFile
0x180053a6e  call    cs:__imp_GetFileInformationByHandleEx
0x180053a74  test    eax, eax
0x180053a76  jz      loc_180053D41
0x180053a7c  mov     r9d, 28h ; '('; dwBufferSize
0x180053a82  mov     dword ptr [rbp+57h+var_88], 2000h
0x180053a89  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180053a8d  xor     edx, edx; FileInformationClass
0x180053a8f  mov     rcx, r15; hFile
0x180053a92  call    cs:__imp_SetFileInformationByHandle
0x180053a98  test    eax, eax
0x180053a9a  jz      loc_180053D32
0x180053aa0  xor     edi, edi
0x180053aa2  cmp     [rbp+57h+var_C8], rdi
0x180053aa6  jz      loc_180053B8F
0x180053aac  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180053ab0  jbe     loc_180053B8F
0x180053ab6  call    cs:__imp_GetProcessHeap
0x180053abc  lea     edx, [rdi+8]; dwFlags
0x180053abf  mov     r8d, 10000h; dwBytes
0x180053ac5  mov     rcx, rax; hHeap
0x180053ac8  call    cs:__imp_HeapAlloc
0x180053ace  mov     r14, rax
0x180053ad1  test    rax, rax
0x180053ad4  jz      loc_180053B75
0x180053ada  mov     rcx, [rbp+57h+var_C8]
0x180053ade  mov     r13d, 8000h
0x180053ae4  sub     rcx, rsi
0x180053ae7  mov     r8, rsi; pszSrc
0x180053aea  sar     rcx, 1
0x180053aed  mov     edx, r13d; cchDest
0x180053af0  mov     ebx, ecx
0x180053af2  mov     r9d, ecx; cchToCopy
0x180053af5  mov     rcx, rax; pszDest
0x180053af8  call    StringCchCopyNW
0x180053afd  lea     rax, [r14+rbx*2]
0x180053b01  sub     r13d, ebx
0x180053b04  mov     r9, rax; LinkName
0x180053b07  mov     [rbp+57h+LinkName], rax
0x180053b0b  lea     r8, [rbp+57h+StringLength]; StringLength
0x180053b0f  mov     [rbp+57h+StringLength], r13d
0x180053b13  xor     edx, edx; dwFlags
0x180053b15  mov     rcx, rsi; lpFileName
0x180053b18  call    cs:__imp_FindFirstFileNameW
0x180053b1e  mov     rbx, rax
0x180053b21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180053b25  jz      loc_180053BB3
0x180053b2b  mov     rdx, rsi; String2
0x180053b2e  mov     rcx, r14; String1
0x180053b31  call    _wcsicmp
0x180053b36  mov     [rbp+57h+StringLength], r13d
0x180053b3a  test    eax, eax
0x180053b3c  jnz     short loc_180053B6A
0x180053b3e  mov     r8, [rbp+57h+LinkName]; LinkName
0x180053b42  lea     rdx, [rbp+57h+StringLength]; StringLength
0x180053b46  mov     rcx, rbx; hFindStream
0x180053b49  call    cs:__imp_FindNextFileNameW
0x180053b4f  test    eax, eax
0x180053b51  jnz     short loc_180053B2B
0x180053b53  call    cs:__imp_GetProcessHeap
0x180053b59  mov     r8, r14; lpMem
0x180053b5c  xor     edx, edx; dwFlags
0x180053b5e  mov     rcx, rax; hHeap
0x180053b61  call    cs:__imp_HeapFree
0x180053b67  xor     r14d, r14d
0x180053b6a  mov     rcx, rbx; hFindFile
0x180053b6d  call    cs:__imp_FindClose
0x180053b73  jmp     short loc_180053BB3
0x180053b75  lea     r8, aDeletefileexUn_6; "DeleteFileEx: Unable to allocate hardli"...
0x180053b7c  mov     edx, 3000000h
0x180053b81  lea     rcx, g_WdsLibLog
0x180053b88  call    LibLog
0x180053b8d  jmp     short loc_180053BB3
0x180053b8f  xor     r14d, r14d
0x180053b92  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180053b96  jbe     short loc_180053BB3
0x180053b98  mov     r9, rsi
0x180053b9b  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x180053ba2  mov     edx, 3000000h
0x180053ba7  lea     rcx, g_WdsLibLog
0x180053bae  call    LibLog
0x180053bb3  xorps   xmm0, xmm0
0x180053bb6  mov     [rbp+57h+var_D0], 1
0x180053bba  mov     r9d, 1; Length
0x180053bc0  mov     dword ptr [rsp+110h+dwCreationDisposition], 0Dh; FileInformationClass
0x180053bc8  lea     r8, [rbp+57h+var_D0]; FileInformation
0x180053bcc  mov     rcx, r15; FileHandle
0x180053bcf  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180053bd3  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180053bd7  call    cs:__imp_NtSetInformationFile
0x180053bdd  test    eax, eax
0x180053bdf  jns     short loc_180053C4D
0x180053be1  mov     ecx, eax; Status
0x180053be3  call    cs:__imp_RtlNtStatusToDosError
0x180053be9  mov     r9d, 4; Length
0x180053bef  mov     [rbp+57h+StringLength], 1
0x180053bf6  lea     r8, [rbp+57h+StringLength]; FileInformation
0x180053bfa  mov     dword ptr [rsp+110h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180053c02  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180053c06  mov     rcx, r15; FileHandle
0x180053c09  mov     edi, eax
0x180053c0b  call    cs:__imp_NtSetInformationFile
0x180053c11  test    eax, eax
0x180053c13  jns     short loc_180053C4B
0x180053c15  cmp     eax, 0C0000003h
0x180053c1a  jz      short loc_180053C26
0x180053c1c  mov     ecx, eax; Status
0x180053c1e  call    cs:__imp_RtlNtStatusToDosError
0x180053c24  mov     edi, eax
0x180053c26  test    edi, edi
0x180053c28  jz      short loc_180053C4D
0x180053c2a  mov     r9, rsi
0x180053c2d  mov     dword ptr [rsp+110h+dwCreationDisposition], edi
0x180053c31  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x180053c38  mov     edx, 3000000h
0x180053c3d  lea     rcx, g_WdsLibLog
0x180053c44  call    LibLog
0x180053c49  jmp     short loc_180053C4D
0x180053c4b  xor     edi, edi
0x180053c4d  test    r14, r14
0x180053c50  jz      loc_180053D68
0x180053c56  mov     r9, r14
0x180053c59  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x180053c60  mov     edx, 4000000h
0x180053c65  lea     rcx, g_WdsLibLog
0x180053c6c  call    LibLog
0x180053c71  xor     r9d, r9d; lpSecurityAttributes
0x180053c74  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x180053c7d  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180053c85  mov     edx, 100h; dwDesiredAccess
0x180053c8a  mov     rcx, r14; lpFileName
0x180053c8d  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180053c95  lea     r8d, [r9+7]; dwShareMode
0x180053c99  call    cs:__imp_CreateFileW
0x180053c9f  mov     rbx, rax
0x180053ca2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180053ca6  jz      short loc_180053CF7
0x180053ca8  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x180053cab  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180053caf  mov     dword ptr [rbp+57h+var_88], ecx
0x180053cb2  mov     r9d, 28h ; '('; dwBufferSize
0x180053cb8  mov     rcx, rax; hFile
0x180053cbb  xor     edx, edx; FileInformationClass
0x180053cbd  call    cs:__imp_SetFileInformationByHandle
0x180053cc3  test    eax, eax
0x180053cc5  jnz     short loc_180053CEC
0x180053cc7  call    cs:__imp_GetLastError
0x180053ccd  mov     r9, r14
0x180053cd0  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x180053cd7  lea     rcx, g_WdsLibLog
0x180053cde  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180053ce2  mov     edx, 3000000h
0x180053ce7  call    LibLog
0x180053cec  mov     rcx, rbx; hObject
0x180053cef  call    cs:__imp_CloseHandle
0x180053cf5  jmp     short loc_180053D1C
0x180053cf7  call    cs:__imp_GetLastError
0x180053cfd  mov     r9, r14
0x180053d00  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x180053d07  lea     rcx, g_WdsLibLog
0x180053d0e  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180053d12  mov     edx, 3000000h
0x180053d17  call    LibLog
0x180053d1c  call    cs:__imp_GetProcessHeap
0x180053d22  mov     r8, r14; lpMem
0x180053d25  xor     edx, edx; dwFlags
0x180053d27  mov     rcx, rax; hHeap
0x180053d2a  call    cs:__imp_HeapFree
0x180053d30  jmp     short loc_180053D68
0x180053d32  call    cs:__imp_GetLastError
0x180053d38  lea     r8, aDeletefileexUn; "DeleteFileEx: Unable to clear out attri"...
0x180053d3f  jmp     short loc_180053D4E
0x180053d41  call    cs:__imp_GetLastError
0x180053d47  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to get information"...
0x180053d4e  mov     r9, rsi
0x180053d51  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180053d55  mov     edx, 3000000h
0x180053d5a  lea     rcx, g_WdsLibLog
0x180053d61  mov     edi, eax
0x180053d63  call    LibLog
0x180053d68  mov     rcx, r15; hObject
0x180053d6b  call    cs:__imp_CloseHandle
0x180053d71  jmp     short loc_180053DBD
0x180053d73  call    cs:__imp_GetLastError
0x180053d79  mov     edi, eax
0x180053d7b  cmp     eax, 5
0x180053d7e  jnz     short loc_180053D9E
0x180053d80  mov     rcx, rsi; lpFileName
0x180053d83  call    cs:__imp_DeleteFileW
0x180053d89  test    eax, eax
0x180053d8b  jnz     short loc_180053DBD
0x180053d8d  call    cs:__imp_GetLastError
0x180053d93  mov     edi, eax
0x180053d95  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to delete [%s]; GL"...
0x180053d9c  jmp     short loc_180053DA5
0x180053d9e  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x180053da5  mov     r9, rsi
0x180053da8  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180053dac  mov     edx, 3000000h
0x180053db1  lea     rcx, g_WdsLibLog
0x180053db8  call    LibLog
0x180053dbd  call    cs:__imp_GetProcessHeap
0x180053dc3  mov     r8, rsi; lpMem
0x180053dc6  xor     edx, edx; dwFlags
0x180053dc8  mov     rcx, rax; hHeap
0x180053dcb  call    cs:__imp_HeapFree
0x180053dd1  jmp     short loc_180053DFA
0x180053dd3  call    cs:__imp_GetLastError
0x180053dd9  mov     r9, r12
0x180053ddc  lea     r8, aDeletefileexUn_3; "DeleteFileEx: Unable to prepare Unicode"...
0x180053de3  lea     rcx, g_WdsLibLog
0x180053dea  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180053dee  mov     edx, 3000000h
0x180053df3  mov     edi, eax
0x180053df5  call    LibLog
0x180053dfa  call    cs:__imp_GetProcessHeap
0x180053e00  mov     r8, r12; lpMem
0x180053e03  xor     edx, edx; dwFlags
0x180053e05  mov     rcx, rax; hHeap
0x180053e08  call    cs:__imp_HeapFree
0x180053e0e  jmp     short loc_180053E37
0x180053e10  call    cs:__imp_GetLastError
0x180053e16  mov     r9, rbx
0x180053e19  lea     r8, aDeletefileexUn_1; "DeleteFileEx: Unable to form long path "...
0x180053e20  lea     rcx, g_WdsLibLog
0x180053e27  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180053e2b  mov     edx, 3000000h
0x180053e30  mov     edi, eax
0x180053e32  call    LibLog
0x180053e37  mov     ecx, edi; dwErrCode
0x180053e39  call    cs:__imp_SetLastError
0x180053e3f  xor     eax, eax
0x180053e41  test    edi, edi
0x180053e43  setz    al
0x180053e46  mov     rcx, [rbp+57h+var_48]
0x180053e4a  xor     rcx, rsp; StackCookie
0x180053e4d  call    __security_check_cookie
0x180053e52  add     rsp, 0D8h
0x180053e59  pop     r15
0x180053e5b  pop     r14
0x180053e5d  pop     r13
0x180053e5f  pop     r12
0x180053e61  pop     rdi
0x180053e62  pop     rsi
0x180053e63  pop     rbx
0x180053e64  pop     rbp
0x180053e65  retn
  ... truncated ...
```
