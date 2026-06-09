# DeleteFileEx2

- ea: `0x140023dcc`
- end: `0x140024509`
- name: `DeleteFileEx2`
- size: `1853`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140005ec0`
- `0x140023c8c`
- `0x1400246b4`
- `0x140024cac`
- `0x140025a80`
- `0x140025c80`
- `0x140025f90`
- `0x140026520`
- `0x140057a08`
- `0x14005aa68`
- `0x14005b208`

## callees

- `0x140001c34`
- `0x140022594`
- `0x140022960`
- `0x140022c14`
- `0x140023dcc`
- `0x14002840c`
- `0x140080d70`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400243e2`
- `KERNEL32!DeleteFileW` at `0x1400243e2`
- `KERNEL32!CloseHandle` at `0x1400242e5`
- `KERNEL32!CloseHandle` at `0x1400243b4`
- `KERNEL32!CloseHandle` at `0x1400242e5`
- `KERNEL32!CloseHandle` at `0x1400243b4`
- `KERNEL32!HeapFree` at `0x1400240d0`
- `KERNEL32!HeapFree` at `0x14002433c`
- `KERNEL32!HeapFree` at `0x1400243a5`
- `KERNEL32!HeapFree` at `0x14002443c`
- `KERNEL32!HeapFree` at `0x14002448b`
- `KERNEL32!HeapFree` at `0x1400240d0`
- `KERNEL32!HeapFree` at `0x14002433c`
- `KERNEL32!HeapFree` at `0x1400243a5`
- `KERNEL32!HeapFree` at `0x14002443c`
- `KERNEL32!HeapFree` at `0x14002448b`
- `KERNEL32!HeapAlloc` at `0x140023fdf`
- `KERNEL32!HeapAlloc` at `0x140023fdf`
- `KERNEL32!GetProcessHeap` at `0x140023fc5`
- `KERNEL32!GetProcessHeap` at `0x1400240bc`
- `KERNEL32!GetProcessHeap` at `0x140024328`
- `KERNEL32!GetProcessHeap` at `0x140024391`
- `KERNEL32!GetProcessHeap` at `0x140024428`
- `KERNEL32!GetProcessHeap` at `0x140024477`
- `KERNEL32!GetProcessHeap` at `0x140023fc5`
- `KERNEL32!GetProcessHeap` at `0x1400240bc`
- `KERNEL32!GetProcessHeap` at `0x140024328`
- `KERNEL32!GetProcessHeap` at `0x140024391`
- `KERNEL32!GetProcessHeap` at `0x140024428`
- `KERNEL32!GetProcessHeap` at `0x140024477`
- `KERNEL32!FindNextFileNameW` at `0x1400240ac`
- `KERNEL32!FindNextFileNameW` at `0x1400240ac`
- `KERNEL32!SetFileInformationByHandle` at `0x140023f97`
- `KERNEL32!SetFileInformationByHandle` at `0x1400242ab`
- `KERNEL32!SetFileInformationByHandle` at `0x140023f97`
- `KERNEL32!SetFileInformationByHandle` at `0x1400242ab`
- `KERNEL32!FindFirstFileNameW` at `0x140024072`
- `KERNEL32!FindFirstFileNameW` at `0x140024072`
- `KERNEL32!GetFileInformationByHandleEx` at `0x140023f70`
- `KERNEL32!GetFileInformationByHandleEx` at `0x140023f70`
- `KERNEL32!GetLastError` at `0x140023ebd`
- `KERNEL32!GetLastError` at `0x1400242bb`
- `KERNEL32!GetLastError` at `0x140024301`
- `KERNEL32!GetLastError` at `0x14002434a`
- `KERNEL32!GetLastError` at `0x14002435f`
- `KERNEL32!GetLastError` at `0x1400243c6`
- `KERNEL32!GetLastError` at `0x1400243f2`
- `KERNEL32!GetLastError` at `0x14002444a`
- `KERNEL32!GetLastError` at `0x140024499`
- `KERNEL32!GetLastError` at `0x140023ebd`
- `KERNEL32!GetLastError` at `0x1400242bb`
- `KERNEL32!GetLastError` at `0x140024301`
- `KERNEL32!GetLastError` at `0x14002434a`
- `KERNEL32!GetLastError` at `0x14002435f`
- `KERNEL32!GetLastError` at `0x1400243c6`
- `KERNEL32!GetLastError` at `0x1400243f2`
- `KERNEL32!GetLastError` at `0x14002444a`
- `KERNEL32!GetLastError` at `0x140024499`
- `KERNEL32!GetFileInformationByHandle` at `0x140023f4a`
- `KERNEL32!GetFileInformationByHandle` at `0x140023f4a`
- `KERNEL32!CreateFileW` at `0x140023e6a`
- `KERNEL32!CreateFileW` at `0x140024281`
- `KERNEL32!CreateFileW` at `0x140023e6a`
- `KERNEL32!CreateFileW` at `0x140024281`
- `KERNEL32!FindClose` at `0x1400240e2`
- `KERNEL32!FindClose` at `0x1400240e2`
- `KERNEL32!SetLastError` at `0x1400244c8`
- `KERNEL32!SetLastError` at `0x1400244c8`
- `ntdll!NtSetInformationFile` at `0x14002414b`
- `ntdll!NtSetInformationFile` at `0x14002418f`
- `ntdll!NtSetInformationFile` at `0x1400241f4`
- `ntdll!NtSetInformationFile` at `0x14002414b`
- `ntdll!NtSetInformationFile` at `0x14002418f`
- `ntdll!NtSetInformationFile` at `0x1400241f4`
- `ntdll!RtlNtStatusToDosError` at `0x140024161`
- `ntdll!RtlNtStatusToDosError` at `0x1400241ac`
- `ntdll!RtlNtStatusToDosError` at `0x14002420a`
- `ntdll!RtlNtStatusToDosError` at `0x140024161`
- `ntdll!RtlNtStatusToDosError` at `0x1400241ac`
- `ntdll!RtlNtStatusToDosError` at `0x14002420a`

## string_xrefs

- `0x140023ecc`: `DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x`
- `0x1400240f0`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x14002410f`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x1400241c3`: `DeleteFileEx: [%s] is in use; attempting POSIX delete`
- `0x140024223`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x140024249`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x1400242ca`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x140024310`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x140024409`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x140024356`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x14002436b`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x140023f05`: `DeleteFileEx: Spoofing detected deleting [%s] -> [%s]`
- `0x140024400`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x140024459`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x1400244a8`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteFileEx2(__int64 a1, char a2)
{
  unsigned int v2; // ebx
  DWORD LastError; // edi
  void *v6; // rax
  void *v7; // r15
  const WCHAR *v8; // rax
  WCHAR *v9; // r14
  DWORD v10; // ecx
  HANDLE FileW; // rax
  HANDLE v12; // r13
  DWORD v13; // r15d
  void *v14; // r15
  __int64 v15; // r13
  wchar_t *v16; // r15
  HANDLE ProcessHeap; // rax
  wchar_t *v18; // rax
  __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  wchar_t v23; // r9
  HANDLE FirstFileNameW; // r13
  int v25; // eax
  HANDLE v26; // rax
  int v27; // eax
  ULONG v28; // eax
  int v29; // eax
  int v30; // eax
  HANDLE v31; // r12
  HANDLE v32; // rax
  DWORD v33; // eax
  const wchar_t *v34; // r8
  HANDLE v35; // rax
  DWORD v36; // eax
  const wchar_t *v37; // r8
  HANDLE v38; // rax
  HANDLE v39; // rax
  __int64 dwCreationDisposition; // [rsp+28h] [rbp-99h]
  __int64 dwCreationDispositiona; // [rsp+28h] [rbp-99h]
  __int64 dwCreationDispositionb; // [rsp+28h] [rbp-99h]
  DWORD StringLength; // [rsp+48h] [rbp-79h] BYREF
  char v45[4]; // [rsp+4Ch] [rbp-75h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-71h] BYREF
  __int64 v47; // [rsp+58h] [rbp-69h]
  DWORD dwShareMode; // [rsp+60h] [rbp-61h]
  PWSTR LinkName; // [rsp+68h] [rbp-59h]
  HANDLE FileHandle; // [rsp+70h] [rbp-51h]
  LPVOID v51; // [rsp+78h] [rbp-49h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-41h] BYREF
  _OWORD v53[2]; // [rsp+90h] [rbp-31h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-11h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B8h] [rbp-9h] BYREF

  v2 = 0;
  LastError = 0;
  v6 = (void *)FormLongPathName();
  v51 = v6;
  v7 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x", a1, LastError);
    goto LABEL_70;
  }
  v47 = 0;
  v8 = (const WCHAR *)PrepareUnicodePathEx((unsigned __int16 *)v6);
  v9 = (WCHAR *)v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x", v7, LastError);
    goto LABEL_68;
  }
  v10 = 0;
  if ( (a2 & 1) == 0 )
    v10 = 7;
  dwShareMode = v10;
  FileW = CreateFileW(v8, 0x10180u, v10, 0, 3u, 0x2200000u, 0);
  FileHandle = FileW;
  v12 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    StringLength = 1;
    lpMem = 0;
    if ( (a2 & 0x20) != 0 )
    {
      if ( (unsigned int)VerifyPathRedirectionByHandle(FileW, v9, &StringLength, &lpMem) )
      {
        v13 = StringLength;
      }
      else
      {
        v13 = 0;
        LODWORD(dwCreationDisposition) = GetLastError();
        LastError = dwCreationDisposition;
        LibLog(
          &g_WdsLibLog,
          0x2000000,
          L"DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x",
          v9,
          dwCreationDisposition);
      }
      if ( !v13 )
      {
        v14 = lpMem;
        if ( !LastError )
        {
          LastError = 681;
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Spoofing detected deleting [%s] -> [%s]", v9, lpMem);
        }
        goto LABEL_57;
      }
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    v54 = 0;
    memset(v53, 0, sizeof(v53));
    if ( GetFileInformationByHandle(v12, &FileInformation)
      && GetFileInformationByHandleEx(v12, FileBasicInfo, v53, 0x28u) )
    {
      LODWORD(v54) = 0x2000;
      if ( SetFileInformationByHandle(v12, FileBasicInfo, v53, 0x28u) )
      {
        v15 = v47;
        v16 = 0;
        if ( v47 )
        {
          if ( FileInformation.nNumberOfLinks > 1 )
          {
            ProcessHeap = GetProcessHeap();
            v18 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 0x10000u);
            v16 = v18;
            if ( v18 )
            {
              v19 = (v15 - (__int64)v9) >> 1;
              if ( (unsigned int)v19 <= 0x7FFFFFFEuLL )
              {
                v20 = (unsigned int)v19;
                v21 = 0x8000;
                v22 = v16;
                do
                {
                  if ( !v20 )
                    break;
                  v23 = *(wchar_t *)((char *)v22 + (char *)v9 - (char *)v16);
                  if ( !v23 )
                    break;
                  *v22 = v23;
                  --v20;
                  ++v22;
                  --v21;
                }
                while ( v21 );
                v18 = v22 - 1;
                if ( v21 )
                  v18 = v22;
              }
              *v18 = 0;
              v47 = (unsigned int)(0x8000 - v19);
              StringLength = 0x8000 - v19;
              LinkName = &v16[(unsigned int)v19];
              FirstFileNameW = FindFirstFileNameW(v9, 0, &StringLength, LinkName);
              if ( FirstFileNameW != (HANDLE)-1LL )
              {
                while ( 1 )
                {
                  v25 = wcsicmp_0(v16, v9);
                  StringLength = v47;
                  if ( v25 )
                    break;
                  if ( !FindNextFileNameW(FirstFileNameW, &StringLength, LinkName) )
                  {
                    v26 = GetProcessHeap();
                    HeapFree(v26, 0, v16);
                    v16 = 0;
                    break;
                  }
                }
                FindClose(FirstFileNameW);
              }
            }
            else
            {
              LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to allocate hardlink path buffer");
            }
          }
        }
        else if ( FileInformation.nNumberOfLinks > 1 )
        {
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Will not restore attributes on hardlinks of [%s]", v9);
        }
        v12 = FileHandle;
        v45[0] = 1;
        IoStatusBlock = 0;
        v27 = NtSetInformationFile(FileHandle, &IoStatusBlock, v45, 1u, FileDispositionInformation);
        if ( v27 < 0 )
        {
          v28 = RtlNtStatusToDosError(v27);
          StringLength = 1;
          LastError = v28;
          v29 = NtSetInformationFile(v12, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
          if ( v29 >= 0 )
          {
            LastError = 0;
LABEL_42:
            if ( v16 )
            {
              if ( (a2 & 4) == 0 )
                LibLog(
                  &g_WdsLibLog,
                  0x4000000,
                  L"DeleteFileEx: Trying to set back attributes on hardlink given: %s",
                  v16);
              v31 = CreateFileW(v16, 0x100u, dwShareMode, 0, 3u, 0x2200000u, 0);
              if ( v31 == (HANDLE)-1LL )
              {
                LODWORD(dwCreationDispositionb) = GetLastError();
                LibLog(
                  &g_WdsLibLog,
                  50331648,
                  L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x",
                  v16,
                  dwCreationDispositionb);
              }
              else
              {
                LODWORD(v54) = FileInformation.dwFileAttributes;
                if ( !SetFileInformationByHandle(v31, FileBasicInfo, v53, 0x28u) )
                {
                  LODWORD(dwCreationDispositionb) = GetLastError();
                  LibLog(
                    &g_WdsLibLog,
                    50331648,
                    L"DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x",
                    v16,
                    dwCreationDispositionb);
                }
                CloseHandle(v31);
              }
              v32 = GetProcessHeap();
              HeapFree(v32, 0, v16);
            }
            goto LABEL_56;
          }
          if ( v29 != -1073741821 )
          {
            LastError = RtlNtStatusToDosError(v29);
            if ( (a2 & 0x40) != 0 )
            {
              LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: [%s] is in use; attempting POSIX delete", v9);
              StringLength |= 2u;
              v30 = NtSetInformationFile(v12, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
              if ( v30 >= 0 )
                LastError = 0;
              else
                LastError = RtlNtStatusToDosError(v30);
            }
          }
        }
        if ( LastError )
        {
          LODWORD(dwCreationDispositiona) = LastError;
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to remove [%s]; GLE = 0x%x", v9, dwCreationDispositiona);
        }
        goto LABEL_42;
      }
      v33 = GetLastError();
      v34 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
    }
    else
    {
      v33 = GetLastError();
      v34 = L"DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x";
    }
    LODWORD(dwCreationDisposition) = v33;
    LastError = v33;
    LibLog(&g_WdsLibLog, 50331648, v34, v9, dwCreationDisposition);
LABEL_56:
    v14 = lpMem;
LABEL_57:
    if ( v14 )
    {
      v35 = GetProcessHeap();
      HeapFree(v35, 0, v14);
    }
    CloseHandle(v12);
    v7 = v51;
    goto LABEL_66;
  }
  v36 = GetLastError();
  LastError = v36;
  if ( v36 != 5 || (a2 & 0x20) != 0 )
  {
    v37 = L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x";
    goto LABEL_65;
  }
  if ( !DeleteFileW(v9) )
  {
    v36 = GetLastError();
    LastError = v36;
    v37 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
LABEL_65:
    LODWORD(dwCreationDisposition) = v36;
    LibLog(&g_WdsLibLog, 50331648, v37, v9, dwCreationDisposition);
  }
LABEL_66:
  v38 = GetProcessHeap();
  HeapFree(v38, 0, v9);
LABEL_68:
  v39 = GetProcessHeap();
  HeapFree(v39, 0, v7);
LABEL_70:
  SetLastError(LastError);
  LOBYTE(v2) = LastError == 0;
  return v2;
}

```

## disassembly

```asm
0x140023dcc  mov     rax, rsp
0x140023dcf  mov     [rax+10h], rbx
0x140023dd3  mov     [rax+18h], rsi
0x140023dd7  mov     [rax+20h], rdi
0x140023ddb  push    rbp
0x140023ddc  push    r12
0x140023dde  push    r13
0x140023de0  push    r14
0x140023de2  push    r15
0x140023de4  lea     rbp, [rax-5Fh]
0x140023de8  sub     rsp, 0F0h
0x140023def  mov     rax, cs:__security_cookie
0x140023df6  xor     rax, rsp
0x140023df9  mov     [rbp+57h+var_28], rax
0x140023dfd  xor     ebx, ebx
0x140023dff  mov     r12d, edx
0x140023e02  mov     edi, ebx
0x140023e04  mov     rsi, rcx
0x140023e07  call    FormLongPathName
0x140023e0c  mov     [rbp+57h+var_A0], rax
0x140023e10  mov     r15, rax
0x140023e13  test    rax, rax
0x140023e16  jz      loc_140024499
0x140023e1c  lea     rdx, [rbp+57h+var_C0]
0x140023e20  mov     [rbp+57h+var_C0], rbx
0x140023e24  mov     rcx, rax; unsigned __int16 *
0x140023e27  call    PrepareUnicodePathEx
0x140023e2c  mov     r14, rax
0x140023e2f  test    rax, rax
0x140023e32  jz      loc_14002444A
0x140023e38  lea     edx, [rbx+7]
0x140023e3b  mov     [rsp+110h+hTemplateFile], rbx; hTemplateFile
0x140023e40  mov     ecx, ebx
0x140023e42  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140023e4a  test    r12b, 1
0x140023e4e  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x140023e56  cmovz   ecx, edx
0x140023e59  xor     r9d, r9d; lpSecurityAttributes
0x140023e5c  mov     [rbp+57h+dwShareMode], ecx
0x140023e5f  mov     r8d, ecx; dwShareMode
0x140023e62  mov     rcx, rax; lpFileName
0x140023e65  mov     edx, 10180h; dwDesiredAccess
0x140023e6a  call    cs:__imp_CreateFileW
0x140023e71  nop     dword ptr [rax+rax+00h]
0x140023e76  mov     [rbp+57h+FileHandle], rax
0x140023e7a  mov     r13, rax
0x140023e7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140023e81  jz      loc_1400243C6
0x140023e87  mov     [rbp+57h+StringLength], 1
0x140023e8e  lea     rsi, g_WdsLibLog
0x140023e95  mov     [rbp+57h+lpMem], rbx
0x140023e99  test    r12b, 20h
0x140023e9d  jz      loc_140023F23
0x140023ea3  lea     r9, [rbp+57h+lpMem]
0x140023ea7  mov     rdx, r14
0x140023eaa  lea     r8, [rbp+57h+StringLength]
0x140023eae  mov     rcx, rax
0x140023eb1  call    VerifyPathRedirectionByHandle
0x140023eb6  test    eax, eax
0x140023eb8  jnz     short loc_140023EE8
0x140023eba  mov     r15d, ebx
0x140023ebd  call    cs:__imp_GetLastError
0x140023ec4  nop     dword ptr [rax+rax+00h]
0x140023ec9  mov     r9, r14
0x140023ecc  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to verify path red"...
0x140023ed3  mov     edx, 2000000h
0x140023ed8  mov     dword ptr [rsp+110h+dwCreationDisposition], eax
0x140023edc  mov     rcx, rsi
0x140023edf  mov     edi, eax
0x140023ee1  call    LibLog
0x140023ee6  jmp     short loc_140023EEC
0x140023ee8  mov     r15d, [rbp+57h+StringLength]
0x140023eec  test    r15d, r15d
0x140023eef  jnz     short loc_140023F23
0x140023ef1  mov     r15, [rbp+57h+lpMem]
0x140023ef5  test    edi, edi
0x140023ef7  jnz     loc_14002438C
0x140023efd  mov     r9, r14
0x140023f00  mov     [rsp+110h+dwCreationDisposition], r15
0x140023f05  lea     r8, aDeletefileexSp; "DeleteFileEx: Spoofing detected deletin"...
0x140023f0c  mov     edx, 3000000h
0x140023f11  mov     rcx, rsi
0x140023f14  mov     edi, 2A9h
0x140023f19  call    LibLog
0x140023f1e  jmp     loc_14002438C
0x140023f23  xorps   xmm0, xmm0
0x140023f26  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x140023f2a  xor     eax, eax
0x140023f2c  mov     rcx, r13; hFile
0x140023f2f  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x140023f33  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x140023f36  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x140023f3a  mov     [rbp+57h+var_68], rax
0x140023f3e  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x140023f42  movups  [rbp+57h+var_88], xmm0
0x140023f46  movups  [rbp+57h+var_78], xmm0
0x140023f4a  call    cs:__imp_GetFileInformationByHandle
0x140023f51  nop     dword ptr [rax+rax+00h]
0x140023f56  test    eax, eax
0x140023f58  jz      loc_14002435F
0x140023f5e  mov     r15d, 28h ; '('
0x140023f64  lea     r8, [rbp+57h+var_88]; lpFileInformation
0x140023f68  mov     r9d, r15d; dwBufferSize
0x140023f6b  xor     edx, edx; FileInformationClass
0x140023f6d  mov     rcx, r13; hFile
0x140023f70  call    cs:__imp_GetFileInformationByHandleEx
0x140023f77  nop     dword ptr [rax+rax+00h]
0x140023f7c  test    eax, eax
0x140023f7e  jz      loc_14002435F
0x140023f84  mov     r9d, r15d; dwBufferSize
0x140023f87  mov     dword ptr [rbp+57h+var_68], 2000h
0x140023f8e  lea     r8, [rbp+57h+var_88]; lpFileInformation
0x140023f92  xor     edx, edx; FileInformationClass
0x140023f94  mov     rcx, r13; hFile
0x140023f97  call    cs:__imp_SetFileInformationByHandle
0x140023f9e  nop     dword ptr [rax+rax+00h]
0x140023fa3  test    eax, eax
0x140023fa5  jz      loc_14002434A
0x140023fab  mov     r13, [rbp+57h+var_C0]
0x140023faf  mov     r15, rbx
0x140023fb2  test    r13, r13
0x140023fb5  jz      loc_140024106
0x140023fbb  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x140023fbf  jbe     loc_140024123
0x140023fc5  call    cs:__imp_GetProcessHeap
0x140023fcc  nop     dword ptr [rax+rax+00h]
0x140023fd1  mov     edx, 8; dwFlags
0x140023fd6  mov     r8d, 10000h; dwBytes
0x140023fdc  mov     rcx, rax; hHeap
0x140023fdf  call    cs:__imp_HeapAlloc
0x140023fe6  nop     dword ptr [rax+rax+00h]
0x140023feb  mov     r15, rax
0x140023fee  test    rax, rax
0x140023ff1  jz      loc_1400240F0
0x140023ff7  sub     r13, r14
0x140023ffa  mov     r9d, 8000h
0x140024000  sar     r13, 1
0x140024003  mov     r10d, r13d
0x140024006  cmp     r10, 7FFFFFFEh
0x14002400d  ja      short loc_140024050
0x14002400f  mov     r8, r14
0x140024012  mov     eax, r10d
0x140024015  sub     r8, r15
0x140024018  mov     edx, r9d
0x14002401b  mov     rcx, r15
0x14002401e  test    rax, rax
0x140024021  jz      short loc_14002403F
0x140024023  movzx   r9d, word ptr [r8+rcx]
0x140024028  test    r9w, r9w
0x14002402c  jz      short loc_14002403F
0x14002402e  mov     [rcx], r9w
0x140024032  dec     rax
0x140024035  add     rcx, 2
0x140024039  sub     rdx, 1
0x14002403d  jnz     short loc_14002401E
0x14002403f  test    rdx, rdx
0x140024042  lea     rax, [rcx-2]
0x140024046  mov     r9d, 8000h
0x14002404c  cmovnz  rax, rcx
0x140024050  sub     r9d, r10d
0x140024053  mov     [rax], bx
0x140024056  lea     rax, [r15+r10*2]
0x14002405a  mov     [rbp+57h+var_C0], r9
0x14002405e  mov     [rbp+57h+StringLength], r9d
0x140024062  lea     r8, [rbp+57h+StringLength]; StringLength
0x140024066  mov     r9, rax; LinkName
0x140024069  mov     [rbp+57h+LinkName], rax
0x14002406d  xor     edx, edx; dwFlags
0x14002406f  mov     rcx, r14; lpFileName
0x140024072  call    cs:__imp_FindFirstFileNameW
0x140024079  nop     dword ptr [rax+rax+00h]
0x14002407e  mov     r13, rax
0x140024081  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140024085  jz      loc_140024123
0x14002408b  mov     rdx, r14; String2
0x14002408e  mov     rcx, r15; String1
0x140024091  call    _wcsicmp_0
0x140024096  mov     rcx, [rbp+57h+var_C0]
0x14002409a  mov     [rbp+57h+StringLength], ecx
0x14002409d  test    eax, eax
0x14002409f  jnz     short loc_1400240DF
0x1400240a1  mov     r8, [rbp+57h+LinkName]; LinkName
0x1400240a5  lea     rdx, [rbp+57h+StringLength]; StringLength
0x1400240a9  mov     rcx, r13; hFindStream
0x1400240ac  call    cs:__imp_FindNextFileNameW
0x1400240b3  nop     dword ptr [rax+rax+00h]
0x1400240b8  test    eax, eax
0x1400240ba  jnz     short loc_14002408B
0x1400240bc  call    cs:__imp_GetProcessHeap
0x1400240c3  nop     dword ptr [rax+rax+00h]
0x1400240c8  mov     r8, r15; lpMem
0x1400240cb  xor     edx, edx; dwFlags
0x1400240cd  mov     rcx, rax; hHeap
0x1400240d0  call    cs:__imp_HeapFree
0x1400240d7  nop     dword ptr [rax+rax+00h]
0x1400240dc  mov     r15, rbx
0x1400240df  mov     rcx, r13; hFindFile
0x1400240e2  call    cs:__imp_FindClose
0x1400240e9  nop     dword ptr [rax+rax+00h]
0x1400240ee  jmp     short loc_140024123
0x1400240f0  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to allocate hardli"...
0x1400240f7  mov     edx, 3000000h
0x1400240fc  mov     rcx, rsi
0x1400240ff  call    LibLog
0x140024104  jmp     short loc_140024123
0x140024106  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x14002410a  jbe     short loc_140024123
0x14002410c  mov     r9, r14
0x14002410f  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x140024116  mov     edx, 3000000h
0x14002411b  mov     rcx, rsi
0x14002411e  call    LibLog
0x140024123  mov     r13, [rbp+57h+FileHandle]
0x140024127  lea     r8, [rbp+57h+var_CC]; FileInformation
0x14002412b  xorps   xmm0, xmm0
0x14002412e  mov     [rbp+57h+var_CC], 1
0x140024132  mov     rcx, r13; FileHandle
0x140024135  mov     dword ptr [rsp+110h+dwCreationDisposition], 0Dh; FileInformationClass
0x14002413d  mov     r9d, 1; Length
0x140024143  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140024147  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14002414b  call    cs:__imp_NtSetInformationFile
0x140024152  nop     dword ptr [rax+rax+00h]
0x140024157  test    eax, eax
0x140024159  jns     loc_140024218
0x14002415f  mov     ecx, eax; Status
0x140024161  call    cs:__imp_RtlNtStatusToDosError
0x140024168  nop     dword ptr [rax+rax+00h]
0x14002416d  mov     r9d, 4; Length
0x140024173  mov     [rbp+57h+StringLength], 1
0x14002417a  lea     r8, [rbp+57h+StringLength]; FileInformation
0x14002417e  mov     dword ptr [rsp+110h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x140024186  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14002418a  mov     rcx, r13; FileHandle
0x14002418d  mov     edi, eax
0x14002418f  call    cs:__imp_NtSetInformationFile
0x140024196  nop     dword ptr [rax+rax+00h]
0x14002419b  test    eax, eax
0x14002419d  jns     loc_1400242FA
0x1400241a3  cmp     eax, 0C0000003h
0x1400241a8  jz      short loc_140024218
0x1400241aa  mov     ecx, eax; Status
0x1400241ac  call    cs:__imp_RtlNtStatusToDosError
0x1400241b3  nop     dword ptr [rax+rax+00h]
0x1400241b8  mov     edi, eax
0x1400241ba  test    r12b, 40h
0x1400241be  jz      short loc_140024218
0x1400241c0  mov     r9, r14
0x1400241c3  lea     r8, aDeletefileexSI; "DeleteFileEx: [%s] is in use; attemptin"...
0x1400241ca  mov     edx, 3000000h
0x1400241cf  mov     rcx, rsi
0x1400241d2  call    LibLog
0x1400241d7  or      [rbp+57h+StringLength], 2
0x1400241db  lea     r8, [rbp+57h+StringLength]; FileInformation
0x1400241df  mov     r9d, 4; Length
0x1400241e5  mov     dword ptr [rsp+110h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x1400241ed  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400241f1  mov     rcx, r13; FileHandle
0x1400241f4  call    cs:__imp_NtSetInformationFile
0x1400241fb  nop     dword ptr [rax+rax+00h]
0x140024200  test    eax, eax
0x140024202  jns     loc_1400242F3
0x140024208  mov     ecx, eax; Status
0x14002420a  call    cs:__imp_RtlNtStatusToDosError
0x140024211  nop     dword ptr [rax+rax+00h]
0x140024216  mov     edi, eax
0x140024218  test    edi, edi
0x14002421a  jz      short loc_140024237
0x14002421c  mov     r9, r14
0x14002421f  mov     dword ptr [rsp+110h+dwCreationDisposition], edi
0x140024223  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x14002422a  mov     edx, 3000000h
0x14002422f  mov     rcx, rsi
0x140024232  call    LibLog
0x140024237  test    r15, r15
0x14002423a  jz      loc_140024388
0x140024240  test    r12b, 4
0x140024244  jnz     short loc_14002425D
0x140024246  mov     r9, r15
0x140024249  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x140024250  mov     edx, 4000000h
0x140024255  mov     rcx, rsi
0x140024258  call    LibLog
0x14002425d  mov     r8d, [rbp+57h+dwShareMode]; dwShareMode
0x140024261  xor     r9d, r9d; lpSecurityAttributes
0x140024264  mov     [rsp+110h+hTemplateFile], rbx; hTemplateFile
0x140024269  mov     edx, 100h; dwDesiredAccess
0x14002426e  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140024276  mov     rcx, r15; lpFileName
0x140024279  mov     dword ptr [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x140024281  call    cs:__imp_CreateFileW
0x140024288  nop     dword ptr [rax+rax+00h]
0x14002428d  mov     r12, rax
0x140024290  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140024294  jz      short loc_140024301
0x140024296  mov     eax, [rbp+57h+FileInformation.dwFileAttributes]
0x140024299  lea     r8, [rbp+57h+var_88]; lpFileInformation
0x14002429d  mov     r9d, 28h ; '('; dwBufferSize
0x1400242a3  mov     dword ptr [rbp+57h+var_68], eax
0x1400242a6  xor     edx, edx; FileInformationClass
  ... truncated ...
```
