# DeleteFileEx2

- ea: `0x1802236ec`
- end: `0x180223ded`
- name: `DeleteFileEx2`
- size: `1793`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1802235c4`
- `0x180223f9c`
- `0x180224598`
- `0x180224e90`
- `0x1802252d0`
- `0x1802255bc`
- `0x180225ad0`

## callees

- `0x1800059d0`
- `0x180006934`
- `0x180093308`
- `0x1802223bc`
- `0x180222764`
- `0x1802227f8`
- `0x1802236ec`
- `0x180227340`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180223a0e`
- `ntdll!RtlNtStatusToDosError` at `0x180223a5b`
- `ntdll!RtlNtStatusToDosError` at `0x180223abb`
- `ntdll!RtlNtStatusToDosError` at `0x180223a0e`
- `ntdll!RtlNtStatusToDosError` at `0x180223a5b`
- `ntdll!RtlNtStatusToDosError` at `0x180223abb`
- `ntdll!NtSetInformationFile` at `0x1802239f8`
- `ntdll!NtSetInformationFile` at `0x180223a3e`
- `ntdll!NtSetInformationFile` at `0x180223aa5`
- `ntdll!NtSetInformationFile` at `0x1802239f8`
- `ntdll!NtSetInformationFile` at `0x180223a3e`
- `ntdll!NtSetInformationFile` at `0x180223aa5`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1802238ab`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180223b65`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1802238ab`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180223b65`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18022398c`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18022398c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180223953`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180223953`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18022385e`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18022385e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180223cd3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180223cd3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802239c2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802239c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180223787`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180223b37`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180223787`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180223b37`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180223884`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180223884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802238d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022399c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223c1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223c82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223d19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223d68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802238d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022399c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223c1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223c82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223d19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180223d68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802239b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223c31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223c96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223d2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223d7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802239b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223c31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223c96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223d2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180223d7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1802238ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1802238ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180223db9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180223db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802237df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802237df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180223d8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180223b9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180223ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180223b9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180223ca5`

## string_xrefs

- `0x180223a72`: `DeleteFileEx: [%s] is in use; attempting POSIX delete`
- `0x180223ad4`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x180223afa`: `DeleteFileEx: Trying to set back attributes on hardlink given: %s`
- `0x180223b84`: `DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x`
- `0x1802237ee`: `DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x`
- `0x180223bad`: `DeleteFileEx: Unable to allocate hardlink path buffer`
- `0x180223bd6`: `DeleteFileEx: Will not restore attributes on hardlinks of [%s]`
- `0x180223cf1`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x180223d4a`: `DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x`
- `0x180223d99`: `DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x`
- `0x180223c05`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180223cfa`: `DeleteFileEx: Unable to open [%s]; GLE = 0x%x`
- `0x180223c4b`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`
- `0x180223c60`: `DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x`
- `0x18022382b`: `DeleteFileEx: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
_BOOL8 __fastcall DeleteFileEx2(__int64 a1, char a2)
{
  void *v4; // rax
  void *v5; // r15
  WCHAR *v6; // r14
  DWORD v7; // eax
  HANDLE FileW; // rax
  HANDLE v9; // rbx
  void *v10; // r13
  DWORD LastError; // edi
  DWORD v12; // r15d
  HANDLE ProcessHeap; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // r15
  size_t v16; // rbx
  HANDLE FirstFileNameW; // rbx
  int v18; // eax
  HANDLE v19; // rax
  int v20; // eax
  ULONG v21; // eax
  int v22; // eax
  int v23; // eax
  HANDLE v24; // rax
  void *v25; // r12
  HANDLE v26; // rax
  DWORD v27; // eax
  const wchar_t *v28; // r8
  HANDLE v29; // rax
  DWORD v30; // eax
  const wchar_t *v31; // r8
  HANDLE v32; // rax
  HANDLE v33; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-B9h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-B9h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-B9h]
  DWORD StringLength; // [rsp+40h] [rbp-99h] BYREF
  char v39[4]; // [rsp+44h] [rbp-95h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-91h] BYREF
  DWORD dwShareMode; // [rsp+50h] [rbp-89h]
  __int64 v42; // [rsp+58h] [rbp-81h]
  HANDLE FileHandle; // [rsp+60h] [rbp-79h]
  PWSTR LinkName; // [rsp+68h] [rbp-71h]
  LPVOID v45; // [rsp+70h] [rbp-69h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-61h] BYREF
  _OWORD v47[2]; // [rsp+88h] [rbp-51h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-31h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B0h] [rbp-29h] BYREF

  v4 = (void *)FormLongPathName();
  v45 = v4;
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to form long path name for [%s]; GLE = 0x%x", a1, LastError);
    goto LABEL_62;
  }
  v42 = 0;
  v6 = (WCHAR *)PrepareUnicodePathEx((wchar_t *)v4);
  if ( !v6 )
  {
    LastError = GetLastError();
    LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to prepare Unicode path for [%s]; GLE = 0x%x", v5, LastError);
    goto LABEL_60;
  }
  v7 = 0;
  if ( (a2 & 1) == 0 )
    v7 = 7;
  dwShareMode = v7;
  FileW = CreateFileW(v6, 0x10180u, v7, 0, 3u, 0x2200000u, 0);
  FileHandle = FileW;
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v10 = 0;
    StringLength = 1;
    LastError = 0;
    lpMem = 0;
    if ( (a2 & 0x20) != 0 )
    {
      if ( (unsigned int)VerifyPathRedirectionByHandle(FileW, v6, &StringLength, &lpMem) )
      {
        v12 = StringLength;
      }
      else
      {
        v12 = 0;
        dwCreationDisposition[0] = GetLastError();
        LastError = dwCreationDisposition[0];
        LibLog(
          &g_WdsLibLog,
          0x2000000,
          L"DeleteFileEx: Unable to verify path redirection on [%s]; GLE = 0x%x",
          v6,
          *(_QWORD *)dwCreationDisposition);
      }
      v10 = lpMem;
      if ( !v12 )
      {
        if ( !LastError )
        {
          LastError = 681;
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Spoofing detected deleting [%s] -> [%s]", v6, lpMem);
        }
        goto LABEL_49;
      }
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    v48 = 0;
    memset(v47, 0, sizeof(v47));
    if ( GetFileInformationByHandle(v9, &FileInformation) && GetFileInformationByHandleEx(v9, FileBasicInfo, v47, 0x28u) )
    {
      LODWORD(v48) = 0x2000;
      if ( SetFileInformationByHandle(v9, FileBasicInfo, v47, 0x28u) )
      {
        if ( v42 && FileInformation.nNumberOfLinks > 1 )
        {
          ProcessHeap = GetProcessHeap();
          v14 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 0x10000u);
          v15 = v14;
          if ( v14 )
          {
            StringLength = 0;
            v16 = (unsigned int)((v42 - (__int64)v6) >> 1);
            StringCchCopyNW(v14, 0x8000u, v6, v16);
            LinkName = &v15[v16];
            lpMem = (LPVOID)(unsigned int)(0x8000 - v16);
            StringLength = 0x8000 - v16;
            FirstFileNameW = FindFirstFileNameW(v6, 0, &StringLength, LinkName);
            if ( FirstFileNameW != (HANDLE)-1LL )
            {
              while ( 1 )
              {
                v18 = wcsicmp(v15, v6);
                StringLength = (unsigned int)lpMem;
                if ( v18 )
                  break;
                if ( !FindNextFileNameW(FirstFileNameW, &StringLength, LinkName) )
                {
                  v19 = GetProcessHeap();
                  HeapFree(v19, 0, v15);
                  v15 = 0;
                  break;
                }
              }
              FindClose(FirstFileNameW);
            }
            v9 = FileHandle;
          }
          else
          {
            LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Unable to allocate hardlink path buffer");
          }
        }
        else
        {
          v15 = 0;
          if ( FileInformation.nNumberOfLinks > 1 )
            LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Will not restore attributes on hardlinks of [%s]", v6);
        }
        v39[0] = 1;
        IoStatusBlock = 0;
        v20 = NtSetInformationFile(v9, &IoStatusBlock, v39, 1u, FileDispositionInformation);
        if ( v20 >= 0 )
          goto LABEL_31;
        v21 = RtlNtStatusToDosError(v20);
        StringLength = 1;
        LastError = v21;
        v22 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
        if ( v22 < 0 )
        {
          if ( v22 == -1073741821 || (LastError = RtlNtStatusToDosError(v22), (a2 & 0x40) == 0) )
          {
LABEL_31:
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
            goto LABEL_33;
          }
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: [%s] is in use; attempting POSIX delete", v6);
          StringLength |= 2u;
          v23 = NtSetInformationFile(v9, &IoStatusBlock, &StringLength, 4u, (FILE_INFORMATION_CLASS)64);
          if ( v23 < 0 )
          {
            LastError = RtlNtStatusToDosError(v23);
            goto LABEL_31;
          }
        }
        LastError = 0;
LABEL_33:
        if ( v15 )
        {
          if ( (a2 & 4) == 0 )
            LibLog(&g_WdsLibLog, 0x4000000, L"DeleteFileEx: Trying to set back attributes on hardlink given: %s", v15);
          v24 = CreateFileW(v15, 0x100u, dwShareMode, 0, 3u, 0x2200000u, 0);
          v25 = v24;
          if ( v24 == (HANDLE)-1LL )
          {
            dwCreationDispositionb[0] = GetLastError();
            LibLog(
              &g_WdsLibLog,
              50331648,
              L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x",
              v15,
              *(_QWORD *)dwCreationDispositionb);
          }
          else
          {
            LODWORD(v48) = FileInformation.dwFileAttributes;
            if ( !SetFileInformationByHandle(v24, FileBasicInfo, v47, 0x28u) )
            {
              dwCreationDispositionb[0] = GetLastError();
              LibLog(
                &g_WdsLibLog,
                50331648,
                L"DeleteFileEx: Unable to restore attributes on [%s]; GLE = 0x%x",
                v15,
                *(_QWORD *)dwCreationDispositionb);
            }
            CloseHandle(v25);
          }
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v15);
        }
        goto LABEL_49;
      }
      v27 = GetLastError();
      v28 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
    }
    else
    {
      v27 = GetLastError();
      v28 = L"DeleteFileEx: Unable to get information on [%s]; GLE = 0x%x";
    }
    dwCreationDisposition[0] = v27;
    LastError = v27;
    LibLog(&g_WdsLibLog, 50331648, v28, v6, *(_QWORD *)dwCreationDisposition);
LABEL_49:
    if ( v10 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v10);
    }
    CloseHandle(v9);
    v5 = v45;
    goto LABEL_58;
  }
  v30 = GetLastError();
  LastError = v30;
  if ( v30 != 5 || (a2 & 0x20) != 0 )
  {
    v31 = L"DeleteFileEx: Unable to open [%s]; GLE = 0x%x";
    goto LABEL_57;
  }
  if ( !DeleteFileW(v6) )
  {
    v30 = GetLastError();
    LastError = v30;
    v31 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
LABEL_57:
    dwCreationDisposition[0] = v30;
    LibLog(&g_WdsLibLog, 50331648, v31, v6, *(_QWORD *)dwCreationDisposition);
  }
LABEL_58:
  v32 = GetProcessHeap();
  HeapFree(v32, 0, v6);
LABEL_60:
  v33 = GetProcessHeap();
  HeapFree(v33, 0, v5);
LABEL_62:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1802236ec  push    rbp
0x1802236ee  push    rbx
0x1802236ef  push    rsi
0x1802236f0  push    rdi
0x1802236f1  push    r12
0x1802236f3  push    r13
0x1802236f5  push    r14
0x1802236f7  push    r15
0x1802236f9  lea     rbp, [rsp-1Fh]
0x1802236fe  sub     rsp, 0F8h
0x180223705  mov     rax, cs:__security_cookie
0x18022370c  xor     rax, rsp
0x18022370f  mov     [rbp+57h+var_48], rax
0x180223713  mov     r12d, edx
0x180223716  mov     rbx, rcx
0x180223719  call    FormLongPathName
0x18022371e  mov     [rbp+57h+var_C0], rax
0x180223722  mov     r15, rax
0x180223725  test    rax, rax
0x180223728  jz      loc_180223D8A
0x18022372e  lea     rdx, [rsp+130h+var_D8]
0x180223733  mov     [rsp+130h+var_D8], 0
0x18022373c  mov     rcx, rax; wchar_t *
0x18022373f  call    PrepareUnicodePathEx
0x180223744  mov     r14, rax
0x180223747  test    rax, rax
0x18022374a  jz      loc_180223D3B
0x180223750  xor     eax, eax
0x180223752  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x18022375b  test    r12b, 1
0x18022375f  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180223767  mov     rcx, r14; lpFileName
0x18022376a  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x180223772  lea     edx, [rax+7]
0x180223775  cmovz   eax, edx
0x180223778  xor     r9d, r9d; lpSecurityAttributes
0x18022377b  mov     r8d, eax; dwShareMode
0x18022377e  mov     [rsp+130h+dwShareMode], eax
0x180223782  mov     edx, 10180h; dwDesiredAccess
0x180223787  call    cs:__imp_CreateFileW
0x18022378e  nop     dword ptr [rax+rax+00h]
0x180223793  mov     [rbp+57h+FileHandle], rax
0x180223797  mov     rbx, rax
0x18022379a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18022379e  jz      loc_180223CB7
0x1802237a4  xor     r13d, r13d
0x1802237a7  mov     [rsp+130h+StringLength], 1
0x1802237af  xor     edi, edi
0x1802237b1  mov     [rsp+130h+lpMem], r13
0x1802237b6  lea     rsi, g_WdsLibLog
0x1802237bd  test    r12b, 20h
0x1802237c1  jz      short loc_180223837
0x1802237c3  lea     r9, [rsp+130h+lpMem]
0x1802237c8  mov     rdx, r14
0x1802237cb  lea     r8, [rsp+130h+StringLength]
0x1802237d0  mov     rcx, rax
0x1802237d3  call    VerifyPathRedirectionByHandle
0x1802237d8  test    eax, eax
0x1802237da  jnz     short loc_18022380A
0x1802237dc  xor     r15d, r15d
0x1802237df  call    cs:__imp_GetLastError
0x1802237e6  nop     dword ptr [rax+rax+00h]
0x1802237eb  mov     r9, r14
0x1802237ee  lea     r8, aDeletefileexUn_5; "DeleteFileEx: Unable to verify path red"...
0x1802237f5  mov     edx, 2000000h
0x1802237fa  mov     [rsp+130h+dwCreationDisposition], eax
0x1802237fe  mov     rcx, rsi
0x180223801  mov     edi, eax
0x180223803  call    LibLog
0x180223808  jmp     short loc_18022380F
0x18022380a  mov     r15d, [rsp+130h+StringLength]
0x18022380f  mov     r13, [rsp+130h+lpMem]
0x180223814  test    r15d, r15d
0x180223817  jnz     short loc_180223837
0x180223819  test    edi, edi
0x18022381b  jnz     loc_180223C7D
0x180223821  mov     edi, 2A9h
0x180223826  mov     qword ptr [rsp+130h+dwCreationDisposition], r13
0x18022382b  lea     r8, aDeletefileexSp; "DeleteFileEx: Spoofing detected deletin"...
0x180223832  jmp     loc_180223C6D
0x180223837  xorps   xmm0, xmm0
0x18022383a  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18022383e  xor     eax, eax
0x180223840  mov     rcx, rbx; hFile
0x180223843  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180223847  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18022384a  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18022384e  mov     [rbp+57h+var_88], rax
0x180223852  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180223856  movups  [rbp+57h+var_A8], xmm0
0x18022385a  movups  [rbp+57h+var_98], xmm0
0x18022385e  call    cs:__imp_GetFileInformationByHandle
0x180223865  nop     dword ptr [rax+rax+00h]
0x18022386a  test    eax, eax
0x18022386c  jz      loc_180223C54
0x180223872  mov     r15d, 28h ; '('
0x180223878  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x18022387c  mov     r9d, r15d; dwBufferSize
0x18022387f  xor     edx, edx; FileInformationClass
0x180223881  mov     rcx, rbx; hFile
0x180223884  call    cs:__imp_GetFileInformationByHandleEx
0x18022388b  nop     dword ptr [rax+rax+00h]
0x180223890  test    eax, eax
0x180223892  jz      loc_180223C54
0x180223898  mov     r9d, r15d; dwBufferSize
0x18022389b  mov     dword ptr [rbp+57h+var_88], 2000h
0x1802238a2  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x1802238a6  xor     edx, edx; FileInformationClass
0x1802238a8  mov     rcx, rbx; hFile
0x1802238ab  call    cs:__imp_SetFileInformationByHandle
0x1802238b2  nop     dword ptr [rax+rax+00h]
0x1802238b7  test    eax, eax
0x1802238b9  jz      loc_180223C3F
0x1802238bf  cmp     [rsp+130h+var_D8], 0
0x1802238c5  jz      loc_180223BC6
0x1802238cb  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x1802238cf  jbe     loc_180223BC6
0x1802238d5  call    cs:__imp_GetProcessHeap
0x1802238dc  nop     dword ptr [rax+rax+00h]
0x1802238e1  lea     edx, [r15-20h]; dwFlags
0x1802238e5  mov     r8d, 10000h; dwBytes
0x1802238eb  mov     rcx, rax; hHeap
0x1802238ee  call    cs:__imp_HeapAlloc
0x1802238f5  nop     dword ptr [rax+rax+00h]
0x1802238fa  mov     r15, rax
0x1802238fd  test    rax, rax
0x180223900  jz      loc_180223BAD
0x180223906  mov     rcx, [rsp+130h+var_D8]
0x18022390b  mov     r8, r14; pszSrc
0x18022390e  sub     rcx, r14
0x180223911  mov     [rsp+130h+StringLength], 0
0x180223919  sar     rcx, 1
0x18022391c  mov     edx, 8000h; cchDest
0x180223921  mov     ebx, ecx
0x180223923  mov     r9d, ecx; cchToCopy
0x180223926  mov     rcx, rax; pszDest
0x180223929  call    StringCchCopyNW
0x18022392e  lea     rcx, [r15+rbx*2]
0x180223932  mov     eax, 8000h
0x180223937  sub     eax, ebx
0x180223939  mov     [rbp+57h+LinkName], rcx
0x18022393d  mov     r9, rcx; LinkName
0x180223940  mov     [rsp+130h+lpMem], rax
0x180223945  mov     rcx, r14; lpFileName
0x180223948  mov     [rsp+130h+StringLength], eax
0x18022394c  lea     r8, [rsp+130h+StringLength]; StringLength
0x180223951  xor     edx, edx; dwFlags
0x180223953  call    cs:__imp_FindFirstFileNameW
0x18022395a  nop     dword ptr [rax+rax+00h]
0x18022395f  mov     rbx, rax
0x180223962  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180223966  jz      short loc_1802239CE
0x180223968  mov     rdx, r14; String2
0x18022396b  mov     rcx, r15; String1
0x18022396e  call    _wcsicmp
0x180223973  mov     rcx, [rsp+130h+lpMem]
0x180223978  mov     [rsp+130h+StringLength], ecx
0x18022397c  test    eax, eax
0x18022397e  jnz     short loc_1802239BF
0x180223980  mov     r8, [rbp+57h+LinkName]; LinkName
0x180223984  lea     rdx, [rsp+130h+StringLength]; StringLength
0x180223989  mov     rcx, rbx; hFindStream
0x18022398c  call    cs:__imp_FindNextFileNameW
0x180223993  nop     dword ptr [rax+rax+00h]
0x180223998  test    eax, eax
0x18022399a  jnz     short loc_180223968
0x18022399c  call    cs:__imp_GetProcessHeap
0x1802239a3  nop     dword ptr [rax+rax+00h]
0x1802239a8  mov     r8, r15; lpMem
0x1802239ab  xor     edx, edx; dwFlags
0x1802239ad  mov     rcx, rax; hHeap
0x1802239b0  call    cs:__imp_HeapFree
0x1802239b7  nop     dword ptr [rax+rax+00h]
0x1802239bc  xor     r15d, r15d
0x1802239bf  mov     rcx, rbx; hFindFile
0x1802239c2  call    cs:__imp_FindClose
0x1802239c9  nop     dword ptr [rax+rax+00h]
0x1802239ce  mov     rbx, [rbp+57h+FileHandle]
0x1802239d2  xorps   xmm0, xmm0
0x1802239d5  mov     [rsp+130h+var_EC], 1
0x1802239da  mov     r9d, 1; Length
0x1802239e0  mov     [rsp+130h+dwCreationDisposition], 0Dh; FileInformationClass
0x1802239e8  lea     r8, [rsp+130h+var_EC]; FileInformation
0x1802239ed  mov     rcx, rbx; FileHandle
0x1802239f0  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1802239f4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1802239f8  call    cs:__imp_NtSetInformationFile
0x1802239ff  nop     dword ptr [rax+rax+00h]
0x180223a04  test    eax, eax
0x180223a06  jns     loc_180223AC9
0x180223a0c  mov     ecx, eax; Status
0x180223a0e  call    cs:__imp_RtlNtStatusToDosError
0x180223a15  nop     dword ptr [rax+rax+00h]
0x180223a1a  mov     r9d, 4; Length
0x180223a20  mov     [rsp+130h+StringLength], 1
0x180223a28  lea     r8, [rsp+130h+StringLength]; FileInformation
0x180223a2d  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180223a35  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180223a39  mov     rcx, rbx; FileHandle
0x180223a3c  mov     edi, eax
0x180223a3e  call    cs:__imp_NtSetInformationFile
0x180223a45  nop     dword ptr [rax+rax+00h]
0x180223a4a  test    eax, eax
0x180223a4c  jns     loc_180223BEF
0x180223a52  cmp     eax, 0C0000003h
0x180223a57  jz      short loc_180223AC9
0x180223a59  mov     ecx, eax; Status
0x180223a5b  call    cs:__imp_RtlNtStatusToDosError
0x180223a62  nop     dword ptr [rax+rax+00h]
0x180223a67  mov     edi, eax
0x180223a69  test    r12b, 40h
0x180223a6d  jz      short loc_180223AC9
0x180223a6f  mov     r9, r14
0x180223a72  lea     r8, aDeletefileexSI; "DeleteFileEx: [%s] is in use; attemptin"...
0x180223a79  mov     edx, 3000000h
0x180223a7e  mov     rcx, rsi
0x180223a81  call    LibLog
0x180223a86  or      [rsp+130h+StringLength], 2
0x180223a8b  lea     r8, [rsp+130h+StringLength]; FileInformation
0x180223a90  mov     r9d, 4; Length
0x180223a96  mov     [rsp+130h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x180223a9e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180223aa2  mov     rcx, rbx; FileHandle
0x180223aa5  call    cs:__imp_NtSetInformationFile
0x180223aac  nop     dword ptr [rax+rax+00h]
0x180223ab1  test    eax, eax
0x180223ab3  jns     loc_180223BEF
0x180223ab9  mov     ecx, eax; Status
0x180223abb  call    cs:__imp_RtlNtStatusToDosError
0x180223ac2  nop     dword ptr [rax+rax+00h]
0x180223ac7  mov     edi, eax
0x180223ac9  test    edi, edi
0x180223acb  jz      short loc_180223AE8
0x180223acd  mov     r9, r14
0x180223ad0  mov     [rsp+130h+dwCreationDisposition], edi
0x180223ad4  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to remove [%s]; GL"...
0x180223adb  mov     edx, 3000000h
0x180223ae0  mov     rcx, rsi
0x180223ae3  call    LibLog
0x180223ae8  test    r15, r15
0x180223aeb  jz      loc_180223C7D
0x180223af1  test    r12b, 4
0x180223af5  jnz     short loc_180223B0E
0x180223af7  mov     r9, r15
0x180223afa  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
0x180223b01  mov     edx, 4000000h
0x180223b06  mov     rcx, rsi
0x180223b09  call    LibLog
0x180223b0e  mov     r8d, [rsp+130h+dwShareMode]; dwShareMode
0x180223b13  xor     r9d, r9d; lpSecurityAttributes
0x180223b16  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x180223b1f  mov     edx, 100h; dwDesiredAccess
0x180223b24  mov     [rsp+130h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180223b2c  mov     rcx, r15; lpFileName
0x180223b2f  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x180223b37  call    cs:__imp_CreateFileW
0x180223b3e  nop     dword ptr [rax+rax+00h]
0x180223b43  mov     r12, rax
0x180223b46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180223b4a  jz      loc_180223BF6
0x180223b50  mov     ecx, [rbp+57h+FileInformation.dwFileAttributes]
0x180223b53  lea     r8, [rbp+57h+var_A8]; lpFileInformation
0x180223b57  mov     dword ptr [rbp+57h+var_88], ecx
0x180223b5a  mov     r9d, 28h ; '('; dwBufferSize
0x180223b60  mov     rcx, rax; hFile
0x180223b63  xor     edx, edx; FileInformationClass
0x180223b65  call    cs:__imp_SetFileInformationByHandle
0x180223b6c  nop     dword ptr [rax+rax+00h]
0x180223b71  test    eax, eax
0x180223b73  jnz     short loc_180223B9C
0x180223b75  call    cs:__imp_GetLastError
0x180223b7c  nop     dword ptr [rax+rax+00h]
0x180223b81  mov     r9, r15
0x180223b84  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to restore attribu"...
0x180223b8b  mov     edx, 3000000h
0x180223b90  mov     [rsp+130h+dwCreationDisposition], eax
0x180223b94  mov     rcx, rsi
0x180223b97  call    LibLog
0x180223b9c  mov     rcx, r12; hObject
0x180223b9f  call    cs:__imp_CloseHandle
0x180223ba6  nop     dword ptr [rax+rax+00h]
0x180223bab  jmp     short loc_180223C1D
0x180223bad  lea     r8, aDeletefileexUn_7; "DeleteFileEx: Unable to allocate hardli"...
0x180223bb4  mov     edx, 3000000h
0x180223bb9  mov     rcx, rsi
0x180223bbc  call    LibLog
0x180223bc1  jmp     loc_1802239D2
0x180223bc6  xor     r15d, r15d
0x180223bc9  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x180223bcd  jbe     loc_1802239D2
0x180223bd3  mov     r9, r14
0x180223bd6  lea     r8, aDeletefileexWi; "DeleteFileEx: Will not restore attribut"...
0x180223bdd  mov     edx, 3000000h
0x180223be2  mov     rcx, rsi
0x180223be5  call    LibLog
0x180223bea  jmp     loc_1802239D2
0x180223bef  xor     edi, edi
0x180223bf1  jmp     loc_180223AE8
0x180223bf6  call    cs:__imp_GetLastError
0x180223bfd  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
