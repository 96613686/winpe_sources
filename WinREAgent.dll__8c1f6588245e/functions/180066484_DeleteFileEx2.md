# DeleteFileEx2

- ea: `0x180066484`
- end: `0x180066a80`
- name: `DeleteFileEx2`
- size: `1532`
- prototype: `_BOOL8 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18004c418`
- `0x180065bf0`
- `0x180066c74`
- `0x180066d8c`

## callees

- `0x18000318d`
- `0x18006631c`
- `0x180066484`
- `0x180066bd0`
- `0x180066ffc`
- `0x1800673b0`
- `0x180068ae8`
- `0x18006c690`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800668e7`
- `KERNEL32!CloseHandle` at `0x18006697b`
- `KERNEL32!CloseHandle` at `0x1800668e7`
- `KERNEL32!CloseHandle` at `0x18006697b`
- `KERNEL32!SetLastError` at `0x180066a53`
- `KERNEL32!SetLastError` at `0x180066a53`
- `KERNEL32!GetLastError` at `0x18006656d`
- `KERNEL32!GetLastError` at `0x1800668c3`
- `KERNEL32!GetLastError` at `0x1800668f6`
- `KERNEL32!GetLastError` at `0x18006692d`
- `KERNEL32!GetLastError` at `0x18006693c`
- `KERNEL32!GetLastError` at `0x180066987`
- `KERNEL32!GetLastError` at `0x1800669a7`
- `KERNEL32!GetLastError` at `0x1800669ed`
- `KERNEL32!GetLastError` at `0x180066a2a`
- `KERNEL32!GetLastError` at `0x18006656d`
- `KERNEL32!GetLastError` at `0x1800668c3`
- `KERNEL32!GetLastError` at `0x1800668f6`
- `KERNEL32!GetLastError` at `0x18006692d`
- `KERNEL32!GetLastError` at `0x18006693c`
- `KERNEL32!GetLastError` at `0x180066987`
- `KERNEL32!GetLastError` at `0x1800669a7`
- `KERNEL32!GetLastError` at `0x1800669ed`
- `KERNEL32!GetLastError` at `0x180066a2a`
- `KERNEL32!HeapFree` at `0x180066708`
- `KERNEL32!HeapFree` at `0x180066925`
- `KERNEL32!HeapFree` at `0x180066972`
- `KERNEL32!HeapFree` at `0x1800669e5`
- `KERNEL32!HeapFree` at `0x180066a22`
- `KERNEL32!HeapFree` at `0x180066708`
- `KERNEL32!HeapFree` at `0x180066925`
- `KERNEL32!HeapFree` at `0x180066972`
- `KERNEL32!HeapFree` at `0x1800669e5`
- `KERNEL32!HeapFree` at `0x180066a22`
- `KERNEL32!HeapAlloc` at `0x18006665e`
- `KERNEL32!HeapAlloc` at `0x18006665e`
- `KERNEL32!GetProcessHeap` at `0x18006664b`
- `KERNEL32!GetProcessHeap` at `0x1800666fa`
- `KERNEL32!GetProcessHeap` at `0x180066917`
- `KERNEL32!GetProcessHeap` at `0x180066964`
- `KERNEL32!GetProcessHeap` at `0x1800669d7`
- `KERNEL32!GetProcessHeap` at `0x180066a14`
- `KERNEL32!GetProcessHeap` at `0x18006664b`
- `KERNEL32!GetProcessHeap` at `0x1800666fa`
- `KERNEL32!GetProcessHeap` at `0x180066917`
- `KERNEL32!GetProcessHeap` at `0x180066964`
- `KERNEL32!GetProcessHeap` at `0x1800669d7`
- `KERNEL32!GetProcessHeap` at `0x180066a14`
- `KERNEL32!DeleteFileW` at `0x18006699d`
- `KERNEL32!DeleteFileW` at `0x18006699d`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180066606`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180066606`
- `KERNEL32!FindFirstFileNameW` at `0x1800666b6`
- `KERNEL32!FindFirstFileNameW` at `0x1800666b6`
- `KERNEL32!SetFileInformationByHandle` at `0x180066627`
- `KERNEL32!SetFileInformationByHandle` at `0x1800668b9`
- `KERNEL32!SetFileInformationByHandle` at `0x180066627`
- `KERNEL32!SetFileInformationByHandle` at `0x1800668b9`
- `KERNEL32!FindNextFileNameW` at `0x1800666f0`
- `KERNEL32!FindNextFileNameW` at `0x1800666f0`
- `KERNEL32!CreateFileW` at `0x18006651f`
- `KERNEL32!CreateFileW` at `0x180066895`
- `KERNEL32!CreateFileW` at `0x18006651f`
- `KERNEL32!CreateFileW` at `0x180066895`
- `KERNEL32!FindClose` at `0x180066716`
- `KERNEL32!FindClose` at `0x180066716`
- `KERNEL32!GetFileInformationByHandle` at `0x1800665e6`
- `KERNEL32!GetFileInformationByHandle` at `0x1800665e6`
- `ntdll!NtSetInformationFile` at `0x18006677a`
- `ntdll!NtSetInformationFile` at `0x1800667b4`
- `ntdll!NtSetInformationFile` at `0x18006680f`
- `ntdll!NtSetInformationFile` at `0x18006677a`
- `ntdll!NtSetInformationFile` at `0x1800667b4`
- `ntdll!NtSetInformationFile` at `0x18006680f`
- `ntdll!RtlNtStatusToDosError` at `0x18006678a`
- `ntdll!RtlNtStatusToDosError` at `0x1800667cb`
- `ntdll!RtlNtStatusToDosError` at `0x18006681f`
- `ntdll!RtlNtStatusToDosError` at `0x18006678a`
- `ntdll!RtlNtStatusToDosError` at `0x1800667cb`
- `ntdll!RtlNtStatusToDosError` at `0x18006681f`

## string_xrefs

- `0x180066576`: `DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x`
- `0x180066740`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x18006671e`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x180066832`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x1800667dc`: `DeleteFileEx: [%s] is in use; attempting POSIX delete`
- `0x1800668cc`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x180066858`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x180066933`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x1800668ff`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x1800669b8`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x1800665b3`: `DeleteFileEx: Spoofing detected deleting [%s] -> [%s]`
- `0x180066942`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x1800669f6`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x1800669af`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x180066a33`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_BOOL8 __fastcall DeleteFileEx2(__int64 a1, char a2)
{
  void *v4; // rax
  void *v5; // r14
  WCHAR *v6; // rsi
  DWORD v7; // eax
  HANDLE FileW; // rax
  void *v9; // r13
  DWORD LastError; // ebx
  DWORD v11; // r14d
  int v12; // eax
  ULONG v13; // eax
  int v14; // eax
  int v15; // eax
  DWORD v16; // eax
  const wchar_t *v17; // r8
  DWORD v18; // eax
  const wchar_t *v19; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v21; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-B9h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-B9h]
  DWORD StringLength; // [rsp+40h] [rbp-99h] BYREF
  char v26[4]; // [rsp+44h] [rbp-95h] BYREF
  HANDLE hFindStream; // [rsp+48h] [rbp-91h]
  DWORD dwShareMode; // [rsp+50h] [rbp-89h]
  __int64 v29; // [rsp+58h] [rbp-81h]
  LPVOID lpMem; // [rsp+70h] [rbp-69h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-61h] BYREF
  _OWORD v32[2]; // [rsp+88h] [rbp-51h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-31h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B0h] [rbp-29h] BYREF

  v4 = (void *)FormLongPathName();
  lpMem = v4;
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x", a1, LastError);
    goto LABEL_42;
  }
  v29 = 0;
  v6 = (WCHAR *)PrepareUnicodePathEx((unsigned __int16 *)v4);
  if ( !v6 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x", v5, LastError);
    goto LABEL_40;
  }
  v7 = 0;
  if ( (a2 & 1) == 0 )
    v7 = 7;
  dwShareMode = v7;
  FileW = CreateFileW(v6, 0x10180u, v7, 0, 3u, 0x2200000u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v18 = GetLastError();
    LastError = v18;
    if ( v18 != 5 || (a2 & 0x20) != 0 )
    {
      v19 = L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x";
    }
    else
    {
      if ( DeleteFileW(v6) )
        goto LABEL_38;
      v18 = GetLastError();
      LastError = v18;
      v19 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
    }
    dwCreationDisposition[0] = v18;
    LibLog(&g_WdsLibLog, 50331648, v19, v6, *(_QWORD *)dwCreationDisposition);
    goto LABEL_38;
  }
  StringLength = 1;
  LastError = 0;
  hFindStream = 0;
  if ( (a2 & 0x20) != 0 )
  {
    if ( (unsigned int)VerifyPathRedirectionByHandle(FileW, v6) )
    {
      v11 = StringLength;
    }
    else
    {
      v11 = 0;
      dwCreationDisposition[0] = GetLastError();
      LastError = dwCreationDisposition[0];
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x",
        v6,
        *(_QWORD *)dwCreationDisposition);
    }
    if ( !v11 )
    {
      if ( !LastError )
      {
        LastError = 681;
        LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Spoofing detected deleting [%s] -> [%s]", v6, hFindStream);
      }
      goto LABEL_31;
    }
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  v33 = 0;
  memset(v32, 0, sizeof(v32));
  if ( !GetFileInformationByHandle(v9, &FileInformation) || !GetFileInformationByHandleEx(v9, FileBasicInfo, v32, 0x28u) )
  {
    v16 = GetLastError();
    v17 = L"DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x";
    goto LABEL_30;
  }
  LODWORD(v33) = 0x2000;
  if ( !SetFileInformationByHandle(v9, FileBasicInfo, v32, 0x28u) )
  {
    v16 = GetLastError();
    v17 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
LABEL_30:
    dwCreationDisposition[0] = v16;
    LastError = v16;
    LibLog(&g_WdsLibLog, 50331648, v17, v6, *(_QWORD *)dwCreationDisposition);
    goto LABEL_31;
  }
  if ( FileInformation.nNumberOfLinks > 1 )
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Will not restore attributes on hardlinks of [%s]", v6);
  v26[0] = 1;
  IoStatusBlock = 0;
  v12 = NtSetInformationFile(v9, &IoStatusBlock, v26, 1u, FileDispositionInformation);
  if ( v12 >= 0 )
    goto LABEL_24;
  v13 = RtlNtStatusToDosError(v12);
  StringLength = 1;
  LastError = v13;
  v14 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
  if ( v14 < 0 )
  {
    if ( v14 == -1073741821 || (LastError = RtlNtStatusToDosError(v14), (a2 & 0x40) == 0) )
    {
LABEL_24:
      if ( LastError )
      {
        dwCreationDispositiona[0] = LastError;
        LibLog(
          &g_WdsLibLog,
          50331648,
          L"DeleteFileEx: Unable to remove [%s]; GLE = 0x%x",
          v6,
          *(_QWORD *)dwCreationDispositiona);
      }
      goto LABEL_31;
    }
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: [%s] is in use; attempting POSIX delete", v6);
    StringLength |= 2u;
    v15 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
    if ( v15 < 0 )
    {
      LastError = RtlNtStatusToDosError(v15);
      goto LABEL_24;
    }
  }
  LastError = 0;
LABEL_31:
  CloseHandle(v9);
  v5 = lpMem;
LABEL_38:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v6);
LABEL_40:
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v5);
LABEL_42:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180066484  push    rbp
0x180066486  push    rbx
0x180066487  push    rsi
0x180066488  push    rdi
0x180066489  push    r12
0x18006648b  push    r13
0x18006648d  push    r14
0x18006648f  push    r15
0x180066491  lea     rbp, [rsp-1Fh]
0x180066496  sub     rsp, 0F8h
0x18006649d  mov     rax, cs:__security_cookie
0x1800664a4  xor     rax, rsp
0x1800664a7  mov     [rbp+57h+var_48], rax
0x1800664ab  mov     r15d, edx
0x1800664ae  mov     rdi, rcx
0x1800664b1  call    FormLongPathName
0x1800664b6  mov     [rbp+57h+lpMem], rax
0x1800664ba  mov     r14, rax
0x1800664bd  test    rax, rax
0x1800664c0  jz      loc_180066A2A
0x1800664c6  lea     rdx, [rsp+130h+var_D8]
0x1800664cb  mov     [rsp+130h+var_D8], 0
0x1800664d4  mov     rcx, rax; unsigned __int16 *
0x1800664d7  call    PrepareUnicodePathEx
0x1800664dc  mov     rsi, rax
0x1800664df  test    rax, rax
0x1800664e2  jz      loc_1800669ED
0x1800664e8  xor     eax, eax
0x1800664ea  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x1800664f3  test    r15b, 1
0x1800664f7  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800664ff  mov     rcx, rsi; lpFileName
0x180066502  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x18006650a  lea     edx, [rax+7]
0x18006650d  cmovz   eax, edx
0x180066510  xor     r9d, r9d; lpSecurityAttributes
0x180066513  mov     r8d, eax; dwShareMode
0x180066516  mov     [rsp+130h+dwShareMode], eax
0x18006651a  mov     edx, 10180h; dwDesiredAccess
0x18006651f  call    cs:__imp_CreateFileW
0x180066525  mov     r13, rax
0x180066528  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006652c  jz      loc_180066987
0x180066532  xor     r12d, r12d
0x180066535  mov     [rsp+130h+StringLength], 1
0x18006653d  xor     ebx, ebx
0x18006653f  mov     [rsp+130h+hFindStream], r12
0x180066544  lea     rdi, g_WdsLibLog
0x18006654b  test    r15b, 20h
0x18006654f  jz      short loc_1800665BF
0x180066551  lea     r9, [rsp+130h+hFindStream]
0x180066556  mov     rdx, rsi; lpFileName
0x180066559  lea     r8, [rsp+130h+StringLength]
0x18006655e  mov     rcx, rax; hFile
0x180066561  call    VerifyPathRedirectionByHandle
0x180066566  test    eax, eax
0x180066568  jnz     short loc_180066592
0x18006656a  xor     r14d, r14d
0x18006656d  call    cs:__imp_GetLastError
0x180066573  mov     r9, rsi
0x180066576  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to verify path red"...
0x18006657d  mov     edx, 2000000h
0x180066582  mov     [rsp+130h+dwCreationDisposition], eax
0x180066586  mov     rcx, rdi
0x180066589  mov     ebx, eax
0x18006658b  call    LibLog
0x180066590  jmp     short loc_180066597
0x180066592  mov     r14d, [rsp+130h+StringLength]
0x180066597  mov     r12, [rsp+130h+hFindStream]
0x18006659c  test    r14d, r14d
0x18006659f  jnz     short loc_1800665BF
0x1800665a1  test    ebx, ebx
0x1800665a3  jnz     loc_18006695F
0x1800665a9  mov     ebx, 2A9h
0x1800665ae  mov     qword ptr [rsp+130h+dwCreationDisposition], r12
0x1800665b3  lea     r8, aDeletefileexSp; "DeleteFileEx: Spoofing detected deletin"...
0x1800665ba  jmp     loc_18006694F
0x1800665bf  xorps   xmm0, xmm0
0x1800665c2  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800665c6  xor     eax, eax
0x1800665c8  mov     rcx, r13; hFile
0x1800665cb  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800665cf  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800665d2  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800665d6  mov     [rbp+57h+var_88], rax
0x1800665da  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800665de  movups  [rbp+57h+var_A8], xmm0
0x1800665e2  movups  [rbp+57h+var_98], xmm0
0x1800665e6  call    cs:__imp_GetFileInformationByHandle
0x1800665ec  test    eax, eax
0x1800665ee  jz      loc_18006693C
0x1800665f4  mov     r14d, 28h ; '('
0x1800665fa  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x1800665fe  mov     r9d, r14d; dwBufferSize
0x180066601  xor     edx, edx; FileInformationClass
0x180066603  mov     rcx, r13; hFile
0x180066606  call    cs:__imp_GetFileInformationByHandleEx
0x18006660c  test    eax, eax
0x18006660e  jz      loc_18006693C
0x180066614  mov     r9d, r14d; dwBufferSize
0x180066617  mov     dword ptr [rbp+57h+var_88], 2000h
0x18006661e  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180066622  xor     edx, edx; FileInformationClass
0x180066624  mov     rcx, r13; hFile
0x180066627  call    cs:__imp_SetFileInformationByHandle
0x18006662d  test    eax, eax
0x18006662f  jz      loc_18006692D
0x180066635  cmp     [rsp+130h+var_D8], 0
0x18006663b  jz      loc_180066734
0x180066641  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180066645  jbe     loc_180066734
0x18006664b  call    cs:__imp_GetProcessHeap
0x180066651  lea     edx, [r14-20h]; dwFlags
0x180066655  mov     r8d, 10000h; dwBytes
0x18006665b  mov     rcx, rax; hHeap
0x18006665e  call    cs:__imp_HeapAlloc
0x180066664  mov     r14, rax
0x180066667  test    rax, rax
0x18006666a  jz      loc_18006671E
0x180066670  mov     rcx, [rsp+130h+var_D8]
0x180066675  mov     r8, rsi; pszSrc
0x180066678  sub     rcx, rsi
0x18006667b  mov     edx, 8000h; cchDest
0x180066680  sar     rcx, 1
0x180066683  mov     r11d, ecx
0x180066686  mov     r9d, ecx; cchToCopy
0x180066689  mov     rcx, rax; pszDest
0x18006668c  call    StringCchCopyNW
0x180066691  lea     rcx, [r14+r11*2]
0x180066695  mov     eax, 8000h
0x18006669a  sub     eax, r11d
0x18006669d  mov     [rbp+57h+LinkName], rcx
0x1800666a1  mov     r9, rcx; LinkName
0x1800666a4  mov     [rbp+57h+var_D0], rax
0x1800666a8  mov     rcx, rsi; lpFileName
0x1800666ab  mov     [rsp+130h+StringLength], eax
0x1800666af  lea     r8, [rsp+130h+StringLength]; StringLength
0x1800666b4  xor     edx, edx; dwFlags
0x1800666b6  call    cs:__imp_FindFirstFileNameW
0x1800666bc  mov     [rsp+130h+hFindStream], rax
0x1800666c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800666c5  jz      loc_180066754
0x1800666cb  mov     rdx, rsi; String2
0x1800666ce  mov     rcx, r14; String1
0x1800666d1  call    _wcsicmp_0
0x1800666d6  mov     rcx, [rbp+57h+var_D0]
0x1800666da  mov     [rsp+130h+StringLength], ecx
0x1800666de  test    eax, eax
0x1800666e0  jnz     short loc_180066711
0x1800666e2  mov     r8, [rbp+57h+LinkName]; LinkName
0x1800666e6  lea     rdx, [rsp+130h+StringLength]; StringLength
0x1800666eb  mov     rcx, [rsp+130h+hFindStream]; hFindStream
0x1800666f0  call    cs:__imp_FindNextFileNameW
0x1800666f6  test    eax, eax
0x1800666f8  jnz     short loc_1800666CB
0x1800666fa  call    cs:__imp_GetProcessHeap
0x180066700  mov     r8, r14; lpMem
0x180066703  xor     edx, edx; dwFlags
0x180066705  mov     rcx, rax; hHeap
0x180066708  call    cs:__imp_HeapFree
0x18006670e  xor     r14d, r14d
0x180066711  mov     rcx, [rsp+130h+hFindStream]; hFindFile
0x180066716  call    cs:__imp_FindClose
0x18006671c  jmp     short loc_180066754
0x18006671e  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to allocate hardli"...
0x180066725  mov     edx, 3000000h
0x18006672a  mov     rcx, rdi
0x18006672d  call    LibLog
0x180066732  jmp     short loc_180066754
0x180066734  xor     r14d, r14d
0x180066737  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x18006673b  jbe     short loc_180066754
0x18006673d  mov     r9, rsi
0x180066740  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x180066747  mov     edx, 3000000h
0x18006674c  mov     rcx, rdi
0x18006674f  call    LibLog
0x180066754  xorps   xmm0, xmm0
0x180066757  mov     [rsp+130h+var_EC], 1
0x18006675c  mov     r9d, 1; Length
0x180066762  mov     [rsp+130h+dwCreationDisposition], 0Dh; FileInformationClass
0x18006676a  lea     r8, [rsp+130h+var_EC]; FileInformation
0x18006676f  mov     rcx, r13; FileHandle
0x180066772  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180066776  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18006677a  call    cs:__imp_NtSetInformationFile
0x180066780  test    eax, eax
0x180066782  jns     loc_180066827
0x180066788  mov     ecx, eax; Status
0x18006678a  call    cs:__imp_RtlNtStatusToDosError
0x180066790  mov     r9d, 4; Length
0x180066796  mov     [rsp+130h+StringLength], 1
0x18006679e  lea     r8, [rsp+130h+StringLength]; FileInformation
0x1800667a3  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x1800667ab  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800667af  mov     rcx, r13; FileHandle
0x1800667b2  mov     ebx, eax
0x1800667b4  call    cs:__imp_NtSetInformationFile
0x1800667ba  test    eax, eax
0x1800667bc  jns     loc_1800668EF
0x1800667c2  cmp     eax, 0C0000003h
0x1800667c7  jz      short loc_180066827
0x1800667c9  mov     ecx, eax; Status
0x1800667cb  call    cs:__imp_RtlNtStatusToDosError
0x1800667d1  mov     ebx, eax
0x1800667d3  test    r15b, 40h
0x1800667d7  jz      short loc_180066827
0x1800667d9  mov     r9, rsi
0x1800667dc  lea     r8, aDeletefileexSI; "DeleteFileEx: [%s] is in use; attemptin"...
0x1800667e3  mov     edx, 3000000h
0x1800667e8  mov     rcx, rdi
0x1800667eb  call    LibLog
0x1800667f0  or      [rsp+130h+StringLength], 2
0x1800667f5  lea     r8, [rsp+130h+StringLength]; FileInformation
0x1800667fa  mov     r9d, 4; Length
0x180066800  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180066808  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18006680c  mov     rcx, r13; FileHandle
0x18006680f  call    cs:__imp_NtSetInformationFile
0x180066815  test    eax, eax
0x180066817  jns     loc_1800668EF
0x18006681d  mov     ecx, eax; Status
0x18006681f  call    cs:__imp_RtlNtStatusToDosError
0x180066825  mov     ebx, eax
0x180066827  test    ebx, ebx
0x180066829  jz      short loc_180066846
0x18006682b  mov     r9, rsi
0x18006682e  mov     [rsp+130h+dwCreationDisposition], ebx
0x180066832  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x180066839  mov     edx, 3000000h
0x18006683e  mov     rcx, rdi
0x180066841  call    LibLog
0x180066846  test    r14, r14
0x180066849  jz      loc_18006695F
0x18006684f  test    r15b, 4
0x180066853  jnz     short loc_18006686C
0x180066855  mov     r9, r14
0x180066858  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x18006685f  mov     edx, 4000000h
0x180066864  mov     rcx, rdi
0x180066867  call    LibLog
0x18006686c  mov     r8d, [rsp+130h+dwShareMode]; dwShareMode
0x180066871  xor     r9d, r9d; lpSecurityAttributes
0x180066874  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x18006687d  mov     edx, 100h; dwDesiredAccess
0x180066882  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18006688a  mov     rcx, r14; lpFileName
0x18006688d  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x180066895  call    cs:__imp_CreateFileW
0x18006689b  mov     r15, rax
0x18006689e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800668a2  jz      short loc_1800668F6
0x1800668a4  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x1800668a7  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x1800668ab  mov     dword ptr [rbp+57h+var_88], ecx
0x1800668ae  mov     r9d, 28h ; '('; dwBufferSize
0x1800668b4  mov     rcx, rax; hFile
0x1800668b7  xor     edx, edx; FileInformationClass
0x1800668b9  call    cs:__imp_SetFileInformationByHandle
0x1800668bf  test    eax, eax
0x1800668c1  jnz     short loc_1800668E4
0x1800668c3  call    cs:__imp_GetLastError
0x1800668c9  mov     r9, r14
0x1800668cc  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x1800668d3  mov     edx, 3000000h
0x1800668d8  mov     [rsp+130h+dwCreationDisposition], eax
0x1800668dc  mov     rcx, rdi
0x1800668df  call    LibLog
0x1800668e4  mov     rcx, r15; hObject
0x1800668e7  call    cs:__imp_CloseHandle
0x1800668ed  jmp     short loc_180066917
0x1800668ef  xor     ebx, ebx
0x1800668f1  jmp     loc_180066846
0x1800668f6  call    cs:__imp_GetLastError
0x1800668fc  mov     r9, r14
0x1800668ff  lea     r8, aDeletefileexUn_4; "DeleteFileEx: Unable to open [%s]; GLE "...
0x180066906  mov     edx, 3000000h
0x18006690b  mov     [rsp+130h+dwCreationDisposition], eax
0x18006690f  mov     rcx, rdi
0x180066912  call    LibLog
0x180066917  call    cs:__imp_GetProcessHeap
0x18006691d  mov     r8, r14; lpMem
0x180066920  xor     edx, edx; dwFlags
0x180066922  mov     rcx, rax; hHeap
0x180066925  call    cs:__imp_HeapFree
0x18006692b  jmp     short loc_18006695F
0x18006692d  call    cs:__imp_GetLastError
0x180066933  lea     r8, aDeletefileexUn; "DeleteFileEx: Unable to clear out attri"...
0x18006693a  jmp     short loc_180066949
0x18006693c  call    cs:__imp_GetLastError
0x180066942  lea     r8, aDeletefileexUn_6; "DeleteFileEx: Unable to get information"...
0x180066949  mov     [rsp+130h+dwCreationDisposition], eax
0x18006694d  mov     ebx, eax
0x18006694f  mov     r9, rsi
0x180066952  mov     edx, 3000000h
0x180066957  mov     rcx, rdi
0x18006695a  call    LibLog
0x18006695f  test    r12, r12
0x180066962  jz      short loc_180066978
0x180066964  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
