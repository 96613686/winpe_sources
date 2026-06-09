# DeleteFileEx2

- ea: `0x140012810`
- end: `0x140012ce5`
- name: `DeleteFileEx2`
- size: `1237`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140009fd4`
- `0x14000bd28`
- `0x14000cfc0`
- `0x140012cec`

## callees

- `0x140001864`
- `0x140011670`
- `0x140011978`
- `0x140011a88`
- `0x140011b18`
- `0x140012810`
- `0x140026650`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140012cb8`
- `KERNEL32!SetLastError` at `0x140012cb8`
- `KERNEL32!GetLastError` at `0x140012b46`
- `KERNEL32!GetLastError` at `0x140012b76`
- `KERNEL32!GetLastError` at `0x140012bb1`
- `KERNEL32!GetLastError` at `0x140012bc0`
- `KERNEL32!GetLastError` at `0x140012bf2`
- `KERNEL32!GetLastError` at `0x140012c0c`
- `KERNEL32!GetLastError` at `0x140012c52`
- `KERNEL32!GetLastError` at `0x140012c8f`
- `KERNEL32!GetLastError` at `0x140012b46`
- `KERNEL32!GetLastError` at `0x140012b76`
- `KERNEL32!GetLastError` at `0x140012bb1`
- `KERNEL32!GetLastError` at `0x140012bc0`
- `KERNEL32!GetLastError` at `0x140012bf2`
- `KERNEL32!GetLastError` at `0x140012c0c`
- `KERNEL32!GetLastError` at `0x140012c52`
- `KERNEL32!GetLastError` at `0x140012c8f`
- `KERNEL32!HeapFree` at `0x1400129e0`
- `KERNEL32!HeapFree` at `0x140012ba9`
- `KERNEL32!HeapFree` at `0x140012c4a`
- `KERNEL32!HeapFree` at `0x140012c87`
- `KERNEL32!HeapFree` at `0x1400129e0`
- `KERNEL32!HeapFree` at `0x140012ba9`
- `KERNEL32!HeapFree` at `0x140012c4a`
- `KERNEL32!HeapFree` at `0x140012c87`
- `KERNEL32!HeapAlloc` at `0x140012944`
- `KERNEL32!HeapAlloc` at `0x140012944`
- `KERNEL32!GetProcessHeap` at `0x140012932`
- `KERNEL32!GetProcessHeap` at `0x1400129d2`
- `KERNEL32!GetProcessHeap` at `0x140012b9b`
- `KERNEL32!GetProcessHeap` at `0x140012c3c`
- `KERNEL32!GetProcessHeap` at `0x140012c79`
- `KERNEL32!GetProcessHeap` at `0x140012932`
- `KERNEL32!GetProcessHeap` at `0x1400129d2`
- `KERNEL32!GetProcessHeap` at `0x140012b9b`
- `KERNEL32!GetProcessHeap` at `0x140012c3c`
- `KERNEL32!GetProcessHeap` at `0x140012c79`
- `KERNEL32!SetFileInformationByHandle` at `0x14001290e`
- `KERNEL32!SetFileInformationByHandle` at `0x140012b3c`
- `KERNEL32!SetFileInformationByHandle` at `0x14001290e`
- `KERNEL32!SetFileInformationByHandle` at `0x140012b3c`
- `KERNEL32!CreateFileW` at `0x140012893`
- `KERNEL32!CreateFileW` at `0x140012b18`
- `KERNEL32!CreateFileW` at `0x140012893`
- `KERNEL32!CreateFileW` at `0x140012b18`
- `KERNEL32!CloseHandle` at `0x140012b6e`
- `KERNEL32!CloseHandle` at `0x140012bea`
- `KERNEL32!CloseHandle` at `0x140012b6e`
- `KERNEL32!CloseHandle` at `0x140012bea`
- `KERNEL32!FindFirstFileNameW` at `0x140012997`
- `KERNEL32!FindFirstFileNameW` at `0x140012997`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400128ea`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400128ea`
- `KERNEL32!DeleteFileW` at `0x140012c02`
- `KERNEL32!DeleteFileW` at `0x140012c02`
- `KERNEL32!FindNextFileNameW` at `0x1400129c8`
- `KERNEL32!FindNextFileNameW` at `0x1400129c8`
- `KERNEL32!FindClose` at `0x1400129ec`
- `KERNEL32!FindClose` at `0x1400129ec`
- `KERNEL32!GetFileInformationByHandle` at `0x1400128cd`
- `KERNEL32!GetFileInformationByHandle` at `0x1400128cd`
- `ntdll!NtSetInformationFile` at `0x140012a56`
- `ntdll!NtSetInformationFile` at `0x140012a8a`
- `ntdll!NtSetInformationFile` at `0x140012a56`
- `ntdll!NtSetInformationFile` at `0x140012a8a`
- `ntdll!RtlNtStatusToDosError` at `0x140012a62`
- `ntdll!RtlNtStatusToDosError` at `0x140012a9d`
- `ntdll!RtlNtStatusToDosError` at `0x140012a62`
- `ntdll!RtlNtStatusToDosError` at `0x140012a9d`

## string_xrefs

- `0x140012ad8`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x140012b4f`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x140012b7f`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x140012c1d`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x140012bb7`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x1400129f4`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x140012a1a`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x140012ab0`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x140012c98`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`
- `0x140012bc6`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x140012c14`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x140012c5b`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`

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
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
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
0x140012810  push    rbp
0x140012812  push    rbx
0x140012813  push    rsi
0x140012814  push    rdi
0x140012815  push    r12
0x140012817  push    r13
0x140012819  push    r14
0x14001281b  push    r15
0x14001281d  lea     rbp, [rsp-1Fh]
0x140012822  sub     rsp, 0D8h
0x140012829  mov     rax, cs:__security_cookie
0x140012830  xor     rax, rsp
0x140012833  mov     [rbp+57h+var_48], rax
0x140012837  mov     rbx, rcx
0x14001283a  call    FormLongPathName
0x14001283f  mov     r12, rax
0x140012842  test    rax, rax
0x140012845  jz      loc_140012C8F
0x14001284b  lea     rdx, [rbp+57h+var_C8]
0x14001284f  mov     [rbp+57h+var_C8], 0
0x140012857  mov     rcx, rax; pszSrc
0x14001285a  call    PrepareUnicodePathEx
0x14001285f  mov     rsi, rax
0x140012862  test    rax, rax
0x140012865  jz      loc_140012C52
0x14001286b  xor     r9d, r9d; lpSecurityAttributes
0x14001286e  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x140012877  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x14001287f  mov     edx, 10180h; dwDesiredAccess
0x140012884  mov     rcx, rax; lpFileName
0x140012887  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x14001288f  lea     r8d, [r9+7]; dwShareMode
0x140012893  call    cs:__imp_CreateFileW
0x140012899  mov     r15, rax
0x14001289c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400128a0  jz      loc_140012BF2
0x1400128a6  xorps   xmm0, xmm0
0x1400128a9  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1400128ad  xor     eax, eax
0x1400128af  mov     rcx, r15; hFile
0x1400128b2  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1400128b6  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1400128b9  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1400128bd  mov     [rbp+57h+var_88], rax
0x1400128c1  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1400128c5  movups  [rbp+57h+var_A8], xmm0
0x1400128c9  movups  [rbp+57h+var_98], xmm0
0x1400128cd  call    cs:__imp_GetFileInformationByHandle
0x1400128d3  test    eax, eax
0x1400128d5  jz      loc_140012BC0
0x1400128db  mov     r9d, 28h ; '('; dwBufferSize
0x1400128e1  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x1400128e5  xor     edx, edx; FileInformationClass
0x1400128e7  mov     rcx, r15; hFile
0x1400128ea  call    cs:__imp_GetFileInformationByHandleEx
0x1400128f0  test    eax, eax
0x1400128f2  jz      loc_140012BC0
0x1400128f8  mov     r9d, 28h ; '('; dwBufferSize
0x1400128fe  mov     dword ptr [rbp+57h+var_88], 2000h
0x140012905  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x140012909  xor     edx, edx; FileInformationClass
0x14001290b  mov     rcx, r15; hFile
0x14001290e  call    cs:__imp_SetFileInformationByHandle
0x140012914  test    eax, eax
0x140012916  jz      loc_140012BB1
0x14001291c  xor     edi, edi
0x14001291e  cmp     [rbp+57h+var_C8], rdi
0x140012922  jz      loc_140012A0E
0x140012928  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x14001292c  jbe     loc_140012A0E
0x140012932  call    cs:__imp_GetProcessHeap
0x140012938  lea     edx, [rdi+8]; dwFlags
0x14001293b  mov     r8d, 10000h; dwBytes
0x140012941  mov     rcx, rax; hHeap
0x140012944  call    cs:__imp_HeapAlloc
0x14001294a  mov     r14, rax
0x14001294d  test    rax, rax
0x140012950  jz      loc_1400129F4
0x140012956  mov     rcx, [rbp+57h+var_C8]
0x14001295a  mov     r13d, 8000h
0x140012960  sub     rcx, rsi
0x140012963  mov     [rbp+57h+StringLength], edi
0x140012966  sar     rcx, 1
0x140012969  mov     r8, rsi; pszSrc
0x14001296c  mov     ebx, ecx
0x14001296e  mov     edx, r13d; cchDest
0x140012971  mov     r9d, ecx; cchToCopy
0x140012974  mov     rcx, rax; pszDest
0x140012977  call    StringCchCopyNW
0x14001297c  lea     rax, [r14+rbx*2]
0x140012980  sub     r13d, ebx
0x140012983  mov     r9, rax; LinkName
0x140012986  mov     [rbp+57h+LinkName], rax
0x14001298a  lea     r8, [rbp+57h+StringLength]; StringLength
0x14001298e  mov     [rbp+57h+StringLength], r13d
0x140012992  xor     edx, edx; dwFlags
0x140012994  mov     rcx, rsi; lpFileName
0x140012997  call    cs:__imp_FindFirstFileNameW
0x14001299d  mov     rbx, rax
0x1400129a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400129a4  jz      loc_140012A32
0x1400129aa  mov     rdx, rsi; String2
0x1400129ad  mov     rcx, r14; String1
0x1400129b0  call    _wcsicmp_0
0x1400129b5  mov     [rbp+57h+StringLength], r13d
0x1400129b9  test    eax, eax
0x1400129bb  jnz     short loc_1400129E9
0x1400129bd  mov     r8, [rbp+57h+LinkName]; LinkName
0x1400129c1  lea     rdx, [rbp+57h+StringLength]; StringLength
0x1400129c5  mov     rcx, rbx; hFindStream
0x1400129c8  call    cs:__imp_FindNextFileNameW
0x1400129ce  test    eax, eax
0x1400129d0  jnz     short loc_1400129AA
0x1400129d2  call    cs:__imp_GetProcessHeap
0x1400129d8  mov     r8, r14; lpMem
0x1400129db  xor     edx, edx; dwFlags
0x1400129dd  mov     rcx, rax; hHeap
0x1400129e0  call    cs:__imp_HeapFree
0x1400129e6  xor     r14d, r14d
0x1400129e9  mov     rcx, rbx; hFindFile
0x1400129ec  call    cs:__imp_FindClose
0x1400129f2  jmp     short loc_140012A32
0x1400129f4  lea     r8, aDeletefileexUn_6; "DeleteFileEx: Unable to allocate hardli"...
0x1400129fb  mov     edx, 3000000h
0x140012a00  lea     rcx, g_WdsLibLog
0x140012a07  call    LibLog
0x140012a0c  jmp     short loc_140012A32
0x140012a0e  xor     r14d, r14d
0x140012a11  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x140012a15  jbe     short loc_140012A32
0x140012a17  mov     r9, rsi
0x140012a1a  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x140012a21  mov     edx, 3000000h
0x140012a26  lea     rcx, g_WdsLibLog
0x140012a2d  call    LibLog
0x140012a32  xorps   xmm0, xmm0
0x140012a35  mov     [rbp+57h+var_D0], 1
0x140012a39  mov     r9d, 1; Length
0x140012a3f  mov     dword ptr [rsp+110h+dwCreationDisposition], 0Dh; FileInformationClass
0x140012a47  lea     r8, [rbp+57h+var_D0]; FileInformation
0x140012a4b  mov     rcx, r15; FileHandle
0x140012a4e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140012a52  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140012a56  call    cs:__imp_NtSetInformationFile
0x140012a5c  test    eax, eax
0x140012a5e  jns     short loc_140012ACC
0x140012a60  mov     ecx, eax; Status
0x140012a62  call    cs:__imp_RtlNtStatusToDosError
0x140012a68  mov     r9d, 4; Length
0x140012a6e  mov     [rbp+57h+StringLength], 1
0x140012a75  lea     r8, [rbp+57h+StringLength]; FileInformation
0x140012a79  mov     dword ptr [rsp+110h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x140012a81  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140012a85  mov     rcx, r15; FileHandle
0x140012a88  mov     edi, eax
0x140012a8a  call    cs:__imp_NtSetInformationFile
0x140012a90  test    eax, eax
0x140012a92  jns     short loc_140012ACA
0x140012a94  cmp     eax, 0C0000003h
0x140012a99  jz      short loc_140012AA5
0x140012a9b  mov     ecx, eax; Status
0x140012a9d  call    cs:__imp_RtlNtStatusToDosError
0x140012aa3  mov     edi, eax
0x140012aa5  test    edi, edi
0x140012aa7  jz      short loc_140012ACC
0x140012aa9  mov     r9, rsi
0x140012aac  mov     dword ptr [rsp+110h+dwCreationDisposition], edi
0x140012ab0  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x140012ab7  mov     edx, 3000000h
0x140012abc  lea     rcx, g_WdsLibLog
0x140012ac3  call    LibLog
0x140012ac8  jmp     short loc_140012ACC
0x140012aca  xor     edi, edi
0x140012acc  test    r14, r14
0x140012acf  jz      loc_140012BE7
0x140012ad5  mov     r9, r14
0x140012ad8  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x140012adf  mov     edx, 4000000h
0x140012ae4  lea     rcx, g_WdsLibLog
0x140012aeb  call    LibLog
0x140012af0  xor     r9d, r9d; lpSecurityAttributes
0x140012af3  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x140012afc  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140012b04  mov     edx, 100h; dwDesiredAccess
0x140012b09  mov     rcx, r14; lpFileName
0x140012b0c  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x140012b14  lea     r8d, [r9+7]; dwShareMode
0x140012b18  call    cs:__imp_CreateFileW
0x140012b1e  mov     rbx, rax
0x140012b21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140012b25  jz      short loc_140012B76
0x140012b27  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x140012b2a  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x140012b2e  mov     dword ptr [rbp+57h+var_88], ecx
0x140012b31  mov     r9d, 28h ; '('; dwBufferSize
0x140012b37  mov     rcx, rax; hFile
0x140012b3a  xor     edx, edx; FileInformationClass
0x140012b3c  call    cs:__imp_SetFileInformationByHandle
0x140012b42  test    eax, eax
0x140012b44  jnz     short loc_140012B6B
0x140012b46  call    cs:__imp_GetLastError
0x140012b4c  mov     r9, r14
0x140012b4f  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x140012b56  lea     rcx, g_WdsLibLog
0x140012b5d  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x140012b61  mov     edx, 3000000h
0x140012b66  call    LibLog
0x140012b6b  mov     rcx, rbx; hObject
0x140012b6e  call    cs:__imp_CloseHandle
0x140012b74  jmp     short loc_140012B9B
0x140012b76  call    cs:__imp_GetLastError
0x140012b7c  mov     r9, r14
0x140012b7f  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x140012b86  lea     rcx, g_WdsLibLog
0x140012b8d  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x140012b91  mov     edx, 3000000h
0x140012b96  call    LibLog
0x140012b9b  call    cs:__imp_GetProcessHeap
0x140012ba1  mov     r8, r14; lpMem
0x140012ba4  xor     edx, edx; dwFlags
0x140012ba6  mov     rcx, rax; hHeap
0x140012ba9  call    cs:__imp_HeapFree
0x140012baf  jmp     short loc_140012BE7
0x140012bb1  call    cs:__imp_GetLastError
0x140012bb7  lea     r8, aDeletefileexUn; "DeleteFileEx: Unable to clear out attri"...
0x140012bbe  jmp     short loc_140012BCD
0x140012bc0  call    cs:__imp_GetLastError
0x140012bc6  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to get information"...
0x140012bcd  mov     r9, rsi
0x140012bd0  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x140012bd4  mov     edx, 3000000h
0x140012bd9  lea     rcx, g_WdsLibLog
0x140012be0  mov     edi, eax
0x140012be2  call    LibLog
0x140012be7  mov     rcx, r15; hObject
0x140012bea  call    cs:__imp_CloseHandle
0x140012bf0  jmp     short loc_140012C3C
0x140012bf2  call    cs:__imp_GetLastError
0x140012bf8  mov     edi, eax
0x140012bfa  cmp     eax, 5
0x140012bfd  jnz     short loc_140012C1D
0x140012bff  mov     rcx, rsi; lpFileName
0x140012c02  call    cs:__imp_DeleteFileW
0x140012c08  test    eax, eax
0x140012c0a  jnz     short loc_140012C3C
0x140012c0c  call    cs:__imp_GetLastError
0x140012c12  mov     edi, eax
0x140012c14  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to delete [%s]; GL"...
0x140012c1b  jmp     short loc_140012C24
0x140012c1d  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x140012c24  mov     r9, rsi
0x140012c27  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x140012c2b  mov     edx, 3000000h
0x140012c30  lea     rcx, g_WdsLibLog
0x140012c37  call    LibLog
0x140012c3c  call    cs:__imp_GetProcessHeap
0x140012c42  mov     r8, rsi; lpMem
0x140012c45  xor     edx, edx; dwFlags
0x140012c47  mov     rcx, rax; hHeap
0x140012c4a  call    cs:__imp_HeapFree
0x140012c50  jmp     short loc_140012C79
0x140012c52  call    cs:__imp_GetLastError
0x140012c58  mov     r9, r12
0x140012c5b  lea     r8, aDeletefileexUn_3; "DeleteFileEx: Unable to prepare Unicode"...
0x140012c62  lea     rcx, g_WdsLibLog
0x140012c69  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x140012c6d  mov     edx, 3000000h
0x140012c72  mov     edi, eax
0x140012c74  call    LibLog
0x140012c79  call    cs:__imp_GetProcessHeap
0x140012c7f  mov     r8, r12; lpMem
0x140012c82  xor     edx, edx; dwFlags
0x140012c84  mov     rcx, rax; hHeap
0x140012c87  call    cs:__imp_HeapFree
0x140012c8d  jmp     short loc_140012CB6
0x140012c8f  call    cs:__imp_GetLastError
0x140012c95  mov     r9, rbx
0x140012c98  lea     r8, aDeletefileexUn_1; "DeleteFileEx: Unable to form long path "...
0x140012c9f  lea     rcx, g_WdsLibLog
0x140012ca6  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x140012caa  mov     edx, 3000000h
0x140012caf  mov     edi, eax
0x140012cb1  call    LibLog
0x140012cb6  mov     ecx, edi; dwErrCode
0x140012cb8  call    cs:__imp_SetLastError
0x140012cbe  xor     eax, eax
0x140012cc0  test    edi, edi
0x140012cc2  setz    al
0x140012cc5  mov     rcx, [rbp+57h+var_48]
0x140012cc9  xor     rcx, rsp; StackCookie
0x140012ccc  call    __security_check_cookie
0x140012cd1  add     rsp, 0D8h
0x140012cd8  pop     r15
0x140012cda  pop     r14
0x140012cdc  pop     r13
0x140012cde  pop     r12
0x140012ce0  pop     rdi
0x140012ce1  pop     rsi
0x140012ce2  pop     rbx
0x140012ce3  pop     rbp
  ... truncated ...
```
