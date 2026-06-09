# DeleteFileEx2

- ea: `0x1800128a0`
- end: `0x180012d75`
- name: `DeleteFileEx2`
- size: `1237`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180006a60`

## callees

- `0x180002143`
- `0x1800128a0`
- `0x180012e1c`
- `0x180012eac`
- `0x18001320c`
- `0x18001331c`
- `0x180014310`

## import_xrefs

- `KERNEL32!FindNextFileNameW` at `0x180012a58`
- `KERNEL32!FindNextFileNameW` at `0x180012a58`
- `KERNEL32!SetFileInformationByHandle` at `0x18001299e`
- `KERNEL32!SetFileInformationByHandle` at `0x180012bcc`
- `KERNEL32!SetFileInformationByHandle` at `0x18001299e`
- `KERNEL32!SetFileInformationByHandle` at `0x180012bcc`
- `KERNEL32!GetFileInformationByHandle` at `0x18001295d`
- `KERNEL32!GetFileInformationByHandle` at `0x18001295d`
- `KERNEL32!FindClose` at `0x180012a7c`
- `KERNEL32!FindClose` at `0x180012a7c`
- `KERNEL32!GetLastError` at `0x180012bd6`
- `KERNEL32!GetLastError` at `0x180012c06`
- `KERNEL32!GetLastError` at `0x180012c41`
- `KERNEL32!GetLastError` at `0x180012c50`
- `KERNEL32!GetLastError` at `0x180012c82`
- `KERNEL32!GetLastError` at `0x180012c9c`
- `KERNEL32!GetLastError` at `0x180012ce2`
- `KERNEL32!GetLastError` at `0x180012d1f`
- `KERNEL32!GetLastError` at `0x180012bd6`
- `KERNEL32!GetLastError` at `0x180012c06`
- `KERNEL32!GetLastError` at `0x180012c41`
- `KERNEL32!GetLastError` at `0x180012c50`
- `KERNEL32!GetLastError` at `0x180012c82`
- `KERNEL32!GetLastError` at `0x180012c9c`
- `KERNEL32!GetLastError` at `0x180012ce2`
- `KERNEL32!GetLastError` at `0x180012d1f`
- `KERNEL32!FindFirstFileNameW` at `0x180012a27`
- `KERNEL32!FindFirstFileNameW` at `0x180012a27`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18001297a`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18001297a`
- `KERNEL32!GetProcessHeap` at `0x1800129c2`
- `KERNEL32!GetProcessHeap` at `0x180012a62`
- `KERNEL32!GetProcessHeap` at `0x180012c2b`
- `KERNEL32!GetProcessHeap` at `0x180012ccc`
- `KERNEL32!GetProcessHeap` at `0x180012d09`
- `KERNEL32!GetProcessHeap` at `0x1800129c2`
- `KERNEL32!GetProcessHeap` at `0x180012a62`
- `KERNEL32!GetProcessHeap` at `0x180012c2b`
- `KERNEL32!GetProcessHeap` at `0x180012ccc`
- `KERNEL32!GetProcessHeap` at `0x180012d09`
- `KERNEL32!HeapAlloc` at `0x1800129d4`
- `KERNEL32!HeapAlloc` at `0x1800129d4`
- `KERNEL32!CloseHandle` at `0x180012bfe`
- `KERNEL32!CloseHandle` at `0x180012c7a`
- `KERNEL32!CloseHandle` at `0x180012bfe`
- `KERNEL32!CloseHandle` at `0x180012c7a`
- `KERNEL32!DeleteFileW` at `0x180012c92`
- `KERNEL32!DeleteFileW` at `0x180012c92`
- `KERNEL32!CreateFileW` at `0x180012923`
- `KERNEL32!CreateFileW` at `0x180012ba8`
- `KERNEL32!CreateFileW` at `0x180012923`
- `KERNEL32!CreateFileW` at `0x180012ba8`
- `KERNEL32!HeapFree` at `0x180012a70`
- `KERNEL32!HeapFree` at `0x180012c39`
- `KERNEL32!HeapFree` at `0x180012cda`
- `KERNEL32!HeapFree` at `0x180012d17`
- `KERNEL32!HeapFree` at `0x180012a70`
- `KERNEL32!HeapFree` at `0x180012c39`
- `KERNEL32!HeapFree` at `0x180012cda`
- `KERNEL32!HeapFree` at `0x180012d17`
- `KERNEL32!SetLastError` at `0x180012d48`
- `KERNEL32!SetLastError` at `0x180012d48`
- `ntdll!RtlNtStatusToDosError` at `0x180012af2`
- `ntdll!RtlNtStatusToDosError` at `0x180012b2d`
- `ntdll!RtlNtStatusToDosError` at `0x180012af2`
- `ntdll!RtlNtStatusToDosError` at `0x180012b2d`
- `ntdll!NtSetInformationFile` at `0x180012ae6`
- `ntdll!NtSetInformationFile` at `0x180012b1a`
- `ntdll!NtSetInformationFile` at `0x180012ae6`
- `ntdll!NtSetInformationFile` at `0x180012b1a`

## string_xrefs

- `0x180012a84`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x180012aaa`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x180012b40`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x180012b68`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x180012bdf`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x180012c0f`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180012cad`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180012c47`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x180012c56`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x180012ca4`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x180012ceb`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x180012d28`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall DeleteFileEx2(__int64 a1)
{
  const wchar_t *v2; // rax
  wchar_t *v3; // r12
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
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
  _OWORD v24[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v25; // [rsp+88h] [rbp-31h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-29h] BYREF

  v2 = (const wchar_t *)FormLongPathName();
  v3 = (wchar_t *)v2;
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
0x1800128a0  push    rbp
0x1800128a2  push    rbx
0x1800128a3  push    rsi
0x1800128a4  push    rdi
0x1800128a5  push    r12
0x1800128a7  push    r13
0x1800128a9  push    r14
0x1800128ab  push    r15
0x1800128ad  lea     rbp, [rsp-1Fh]
0x1800128b2  sub     rsp, 0D8h
0x1800128b9  mov     rax, cs:__security_cookie
0x1800128c0  xor     rax, rsp
0x1800128c3  mov     [rbp+57h+var_48], rax
0x1800128c7  mov     rbx, rcx
0x1800128ca  call    FormLongPathName
0x1800128cf  mov     r12, rax
0x1800128d2  test    rax, rax
0x1800128d5  jz      loc_180012D1F
0x1800128db  lea     rdx, [rbp+57h+var_C8]
0x1800128df  mov     [rbp+57h+var_C8], 0
0x1800128e7  mov     rcx, rax; pszSrc
0x1800128ea  call    PrepareUnicodePathEx
0x1800128ef  mov     rsi, rax
0x1800128f2  test    rax, rax
0x1800128f5  jz      loc_180012CE2
0x1800128fb  xor     r9d, r9d; lpSecurityAttributes
0x1800128fe  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x180012907  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001290f  mov     edx, 10180h; dwDesiredAccess
0x180012914  mov     rcx, rax; lpFileName
0x180012917  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x18001291f  lea     r8d, [r9+7]; dwShareMode
0x180012923  call    cs:__imp_CreateFileW
0x180012929  mov     r15, rax
0x18001292c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012930  jz      loc_180012C82
0x180012936  xorps   xmm0, xmm0
0x180012939  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18001293d  xor     eax, eax
0x18001293f  mov     rcx, r15; hFile
0x180012942  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180012946  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180012949  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18001294d  mov     [rbp+57h+var_88], rax
0x180012951  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180012955  movups  [rbp+57h+var_A8], xmm0
0x180012959  movups  [rbp+57h+var_98], xmm0
0x18001295d  call    cs:__imp_GetFileInformationByHandle
0x180012963  test    eax, eax
0x180012965  jz      loc_180012C50
0x18001296b  mov     r9d, 28h ; '('; dwBufferSize
0x180012971  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180012975  xor     edx, edx; FileInformationClass
0x180012977  mov     rcx, r15; hFile
0x18001297a  call    cs:__imp_GetFileInformationByHandleEx
0x180012980  test    eax, eax
0x180012982  jz      loc_180012C50
0x180012988  mov     r9d, 28h ; '('; dwBufferSize
0x18001298e  mov     dword ptr [rbp+57h+var_88], 2000h
0x180012995  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180012999  xor     edx, edx; FileInformationClass
0x18001299b  mov     rcx, r15; hFile
0x18001299e  call    cs:__imp_SetFileInformationByHandle
0x1800129a4  test    eax, eax
0x1800129a6  jz      loc_180012C41
0x1800129ac  xor     edi, edi
0x1800129ae  cmp     [rbp+57h+var_C8], rdi
0x1800129b2  jz      loc_180012A9E
0x1800129b8  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x1800129bc  jbe     loc_180012A9E
0x1800129c2  call    cs:__imp_GetProcessHeap
0x1800129c8  lea     edx, [rdi+8]; dwFlags
0x1800129cb  mov     r8d, 10000h; dwBytes
0x1800129d1  mov     rcx, rax; hHeap
0x1800129d4  call    cs:__imp_HeapAlloc
0x1800129da  mov     r14, rax
0x1800129dd  test    rax, rax
0x1800129e0  jz      loc_180012A84
0x1800129e6  mov     rcx, [rbp+57h+var_C8]
0x1800129ea  mov     r13d, 8000h
0x1800129f0  sub     rcx, rsi
0x1800129f3  mov     [rbp+57h+StringLength], edi
0x1800129f6  sar     rcx, 1
0x1800129f9  mov     r8, rsi; pszSrc
0x1800129fc  mov     ebx, ecx
0x1800129fe  mov     edx, r13d; cchDest
0x180012a01  mov     r9d, ecx; cchToCopy
0x180012a04  mov     rcx, rax; pszDest
0x180012a07  call    StringCchCopyNW
0x180012a0c  lea     rax, [r14+rbx*2]
0x180012a10  sub     r13d, ebx
0x180012a13  mov     r9, rax; LinkName
0x180012a16  mov     [rbp+57h+LinkName], rax
0x180012a1a  lea     r8, [rbp+57h+StringLength]; StringLength
0x180012a1e  mov     [rbp+57h+StringLength], r13d
0x180012a22  xor     edx, edx; dwFlags
0x180012a24  mov     rcx, rsi; lpFileName
0x180012a27  call    cs:__imp_FindFirstFileNameW
0x180012a2d  mov     rbx, rax
0x180012a30  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012a34  jz      loc_180012AC2
0x180012a3a  mov     rdx, rsi; String2
0x180012a3d  mov     rcx, r14; String1
0x180012a40  call    _wcsicmp_0
0x180012a45  mov     [rbp+57h+StringLength], r13d
0x180012a49  test    eax, eax
0x180012a4b  jnz     short loc_180012A79
0x180012a4d  mov     r8, [rbp+57h+LinkName]; LinkName
0x180012a51  lea     rdx, [rbp+57h+StringLength]; StringLength
0x180012a55  mov     rcx, rbx; hFindStream
0x180012a58  call    cs:__imp_FindNextFileNameW
0x180012a5e  test    eax, eax
0x180012a60  jnz     short loc_180012A3A
0x180012a62  call    cs:__imp_GetProcessHeap
0x180012a68  mov     r8, r14; lpMem
0x180012a6b  xor     edx, edx; dwFlags
0x180012a6d  mov     rcx, rax; hHeap
0x180012a70  call    cs:__imp_HeapFree
0x180012a76  xor     r14d, r14d
0x180012a79  mov     rcx, rbx; hFindFile
0x180012a7c  call    cs:__imp_FindClose
0x180012a82  jmp     short loc_180012AC2
0x180012a84  lea     r8, aDeletefileexUn_6; "DeleteFileEx: Unable to allocate hardli"...
0x180012a8b  mov     edx, 3000000h
0x180012a90  lea     rcx, g_WdsLibLog
0x180012a97  call    LibLog
0x180012a9c  jmp     short loc_180012AC2
0x180012a9e  xor     r14d, r14d
0x180012aa1  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180012aa5  jbe     short loc_180012AC2
0x180012aa7  mov     r9, rsi
0x180012aaa  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x180012ab1  mov     edx, 3000000h
0x180012ab6  lea     rcx, g_WdsLibLog
0x180012abd  call    LibLog
0x180012ac2  xorps   xmm0, xmm0
0x180012ac5  mov     [rbp+57h+var_D0], 1
0x180012ac9  mov     r9d, 1; Length
0x180012acf  mov     dword ptr [rsp+110h+dwCreationDisposition], 0Dh; FileInformationClass
0x180012ad7  lea     r8, [rbp+57h+var_D0]; FileInformation
0x180012adb  mov     rcx, r15; FileHandle
0x180012ade  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180012ae2  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180012ae6  call    cs:__imp_NtSetInformationFile
0x180012aec  test    eax, eax
0x180012aee  jns     short loc_180012B5C
0x180012af0  mov     ecx, eax; Status
0x180012af2  call    cs:__imp_RtlNtStatusToDosError
0x180012af8  mov     r9d, 4; Length
0x180012afe  mov     [rbp+57h+StringLength], 1
0x180012b05  lea     r8, [rbp+57h+StringLength]; FileInformation
0x180012b09  mov     dword ptr [rsp+110h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180012b11  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180012b15  mov     rcx, r15; FileHandle
0x180012b18  mov     edi, eax
0x180012b1a  call    cs:__imp_NtSetInformationFile
0x180012b20  test    eax, eax
0x180012b22  jns     short loc_180012B5A
0x180012b24  cmp     eax, 0C0000003h
0x180012b29  jz      short loc_180012B35
0x180012b2b  mov     ecx, eax; Status
0x180012b2d  call    cs:__imp_RtlNtStatusToDosError
0x180012b33  mov     edi, eax
0x180012b35  test    edi, edi
0x180012b37  jz      short loc_180012B5C
0x180012b39  mov     r9, rsi
0x180012b3c  mov     dword ptr [rsp+110h+dwCreationDisposition], edi
0x180012b40  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x180012b47  mov     edx, 3000000h
0x180012b4c  lea     rcx, g_WdsLibLog
0x180012b53  call    LibLog
0x180012b58  jmp     short loc_180012B5C
0x180012b5a  xor     edi, edi
0x180012b5c  test    r14, r14
0x180012b5f  jz      loc_180012C77
0x180012b65  mov     r9, r14
0x180012b68  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x180012b6f  mov     edx, 4000000h
0x180012b74  lea     rcx, g_WdsLibLog
0x180012b7b  call    LibLog
0x180012b80  xor     r9d, r9d; lpSecurityAttributes
0x180012b83  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x180012b8c  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180012b94  mov     edx, 100h; dwDesiredAccess
0x180012b99  mov     rcx, r14; lpFileName
0x180012b9c  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180012ba4  lea     r8d, [r9+7]; dwShareMode
0x180012ba8  call    cs:__imp_CreateFileW
0x180012bae  mov     rbx, rax
0x180012bb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012bb5  jz      short loc_180012C06
0x180012bb7  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x180012bba  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180012bbe  mov     dword ptr [rbp+57h+var_88], ecx
0x180012bc1  mov     r9d, 28h ; '('; dwBufferSize
0x180012bc7  mov     rcx, rax; hFile
0x180012bca  xor     edx, edx; FileInformationClass
0x180012bcc  call    cs:__imp_SetFileInformationByHandle
0x180012bd2  test    eax, eax
0x180012bd4  jnz     short loc_180012BFB
0x180012bd6  call    cs:__imp_GetLastError
0x180012bdc  mov     r9, r14
0x180012bdf  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x180012be6  lea     rcx, g_WdsLibLog
0x180012bed  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180012bf1  mov     edx, 3000000h
0x180012bf6  call    LibLog
0x180012bfb  mov     rcx, rbx; hObject
0x180012bfe  call    cs:__imp_CloseHandle
0x180012c04  jmp     short loc_180012C2B
0x180012c06  call    cs:__imp_GetLastError
0x180012c0c  mov     r9, r14
0x180012c0f  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x180012c16  lea     rcx, g_WdsLibLog
0x180012c1d  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180012c21  mov     edx, 3000000h
0x180012c26  call    LibLog
0x180012c2b  call    cs:__imp_GetProcessHeap
0x180012c31  mov     r8, r14; lpMem
0x180012c34  xor     edx, edx; dwFlags
0x180012c36  mov     rcx, rax; hHeap
0x180012c39  call    cs:__imp_HeapFree
0x180012c3f  jmp     short loc_180012C77
0x180012c41  call    cs:__imp_GetLastError
0x180012c47  lea     r8, aDeletefileexUn; "DeleteFileEx: Unable to clear out attri"...
0x180012c4e  jmp     short loc_180012C5D
0x180012c50  call    cs:__imp_GetLastError
0x180012c56  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to get information"...
0x180012c5d  mov     r9, rsi
0x180012c60  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180012c64  mov     edx, 3000000h
0x180012c69  lea     rcx, g_WdsLibLog
0x180012c70  mov     edi, eax
0x180012c72  call    LibLog
0x180012c77  mov     rcx, r15; hObject
0x180012c7a  call    cs:__imp_CloseHandle
0x180012c80  jmp     short loc_180012CCC
0x180012c82  call    cs:__imp_GetLastError
0x180012c88  mov     edi, eax
0x180012c8a  cmp     eax, 5
0x180012c8d  jnz     short loc_180012CAD
0x180012c8f  mov     rcx, rsi; lpFileName
0x180012c92  call    cs:__imp_DeleteFileW
0x180012c98  test    eax, eax
0x180012c9a  jnz     short loc_180012CCC
0x180012c9c  call    cs:__imp_GetLastError
0x180012ca2  mov     edi, eax
0x180012ca4  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to delete [%s]; GL"...
0x180012cab  jmp     short loc_180012CB4
0x180012cad  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x180012cb4  mov     r9, rsi
0x180012cb7  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180012cbb  mov     edx, 3000000h
0x180012cc0  lea     rcx, g_WdsLibLog
0x180012cc7  call    LibLog
0x180012ccc  call    cs:__imp_GetProcessHeap
0x180012cd2  mov     r8, rsi; lpMem
0x180012cd5  xor     edx, edx; dwFlags
0x180012cd7  mov     rcx, rax; hHeap
0x180012cda  call    cs:__imp_HeapFree
0x180012ce0  jmp     short loc_180012D09
0x180012ce2  call    cs:__imp_GetLastError
0x180012ce8  mov     r9, r12
0x180012ceb  lea     r8, aDeletefileexUn_3; "DeleteFileEx: Unable to prepare Unicode"...
0x180012cf2  lea     rcx, g_WdsLibLog
0x180012cf9  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180012cfd  mov     edx, 3000000h
0x180012d02  mov     edi, eax
0x180012d04  call    LibLog
0x180012d09  call    cs:__imp_GetProcessHeap
0x180012d0f  mov     r8, r12; lpMem
0x180012d12  xor     edx, edx; dwFlags
0x180012d14  mov     rcx, rax; hHeap
0x180012d17  call    cs:__imp_HeapFree
0x180012d1d  jmp     short loc_180012D46
0x180012d1f  call    cs:__imp_GetLastError
0x180012d25  mov     r9, rbx
0x180012d28  lea     r8, aDeletefileexUn_1; "DeleteFileEx: Unable to form long path "...
0x180012d2f  lea     rcx, g_WdsLibLog
0x180012d36  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x180012d3a  mov     edx, 3000000h
0x180012d3f  mov     edi, eax
0x180012d41  call    LibLog
0x180012d46  mov     ecx, edi; dwErrCode
0x180012d48  call    cs:__imp_SetLastError
0x180012d4e  xor     eax, eax
0x180012d50  test    edi, edi
0x180012d52  setz    al
0x180012d55  mov     rcx, [rbp+57h+var_48]
0x180012d59  xor     rcx, rsp; StackCookie
0x180012d5c  call    __security_check_cookie
0x180012d61  add     rsp, 0D8h
0x180012d68  pop     r15
0x180012d6a  pop     r14
0x180012d6c  pop     r13
0x180012d6e  pop     r12
0x180012d70  pop     rdi
0x180012d71  pop     rsi
0x180012d72  pop     rbx
0x180012d73  pop     rbp
  ... truncated ...
```
