# CONFIG_HISTORY_ENTITY::DeleteDirectory(ushort const *)

- ea: `0x180004528`
- end: `0x18000473d`
- name: `?DeleteDirectory@CONFIG_HISTORY_ENTITY@@QEAAJPEBG@Z`
- size: `533`
- prototype: `__int64 __fastcall(CONFIG_HISTORY_ENTITY *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180004528`
- `0x180004b0c`
- `0x180005110`

## callees

- `0x180004528`
- `0x180008c1f`
- `0x180008c50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800046b8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800046b8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000464b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000468d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000464b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000468d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000466b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000466b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000465a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000465a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800045c9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800045c9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000469a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000469a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004588`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180004588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004702`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000470e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004702`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000470e`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800046f6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800046f6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800045a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800045a9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800045bb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800045ff`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004611`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004620`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800045bb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800045ff`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004611`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004620`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004561`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000456d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004561`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000456d`

## pseudocode

```c
__int64 __fastcall CONFIG_HISTORY_ENTITY::DeleteDirectory(CONFIG_HISTORY_ENTITY *this, const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // eax
  signed int LastError; // ebx
  __int64 FirstFileW; // rsi
  bool v7; // zf
  const unsigned __int16 *v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+68h] [rbp-98h]
  _BYTE v13[32]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR v14; // [rsp+90h] [rbp-70h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  STRU::STRU((STRU *)v13);
  STRU::STRU((STRU *)v10);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    FirstFileW = -1;
    LastError = 3;
  }
  else
  {
    LastError = 0;
    STRU::Copy((STRU *)v13, a2);
    STRU::Append((STRU *)v13, L"\\*.*");
    FirstFileW = (__int64)FindFirstFileW(v14, &FindFileData);
    if ( FirstFileW != -1 )
    {
      do
      {
        if ( FindFileData.cFileName[0] != 46 || (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          *lpFileName = 0;
          v12 = 0;
          STRU::Append((STRU *)v10, a2);
          STRU::Append((STRU *)v10, L"\\");
          STRU::Append((STRU *)v10, FindFileData.cFileName);
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            LastError = CONFIG_HISTORY_ENTITY::DeleteDirectory(this, lpFileName);
            if ( LastError )
              goto LABEL_17;
          }
          else if ( !SetFileAttributesW(lpFileName, 0x80u) || !DeleteFileW(lpFileName) )
          {
            goto LABEL_15;
          }
        }
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
      LastError = GetLastError();
      if ( LastError == 18 && (!SetFileAttributesW(a2, 0x80u) || !RemoveDirectoryW(a2)) )
LABEL_15:
        LastError = GetLastError();
    }
  }
LABEL_17:
  FindClose((HANDLE)FirstFileW);
  v7 = LastError == 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError == 0;
  }
  if ( !v7 )
  {
    v9 = a2;
    EVENT_LOG::LogEvent((APP_HOST_SERVICE *)((char *)g_pAppHostService + 136), 0x80002331, 1u, &v9, LastError);
  }
  STRU::~STRU((STRU *)v10);
  STRU::~STRU((STRU *)v13);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180004528  mov     [rsp-8+arg_10], rbx
0x18000452d  mov     [rsp-8+arg_18], rsi
0x180004532  push    rbp
0x180004533  push    rdi
0x180004534  push    r14
0x180004536  lea     rbp, [rsp-210h]
0x18000453e  sub     rsp, 310h
0x180004545  mov     rax, cs:__security_cookie
0x18000454c  xor     rax, rsp
0x18000454f  mov     [rbp+220h+var_20], rax
0x180004556  mov     rdi, rdx
0x180004559  mov     r14, rcx
0x18000455c  lea     rcx, [rsp+320h+var_2B0]
0x180004561  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004567  nop
0x180004568  lea     rcx, [rsp+320h+var_2E8]
0x18000456d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004573  nop
0x180004574  xor     edx, edx; Val
0x180004576  mov     r8d, 250h; Size
0x18000457c  lea     rcx, [rbp+220h+FindFileData]; void *
0x180004580  call    memset_0
0x180004585  mov     rcx, rdi; lpFileName
0x180004588  call    cs:__imp_GetFileAttributesW
0x18000458e  cmp     eax, 0FFFFFFFFh
0x180004591  jz      loc_1800046AE
0x180004597  test    al, 10h
0x180004599  jz      loc_1800046AE
0x18000459f  xor     ebx, ebx
0x1800045a1  mov     rdx, rdi
0x1800045a4  lea     rcx, [rsp+320h+var_2B0]
0x1800045a9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800045af  lea     rdx, asc_18000C3A8; "\\*.*"
0x1800045b6  lea     rcx, [rsp+320h+var_2B0]
0x1800045bb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800045c1  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x1800045c5  mov     rcx, [rbp+220h+var_290]; lpFileName
0x1800045c9  call    cs:__imp_FindFirstFileW
0x1800045cf  mov     rsi, rax
0x1800045d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800045d6  jz      loc_1800046B5
0x1800045dc  cmp     [rbp+220h+FindFileData.cFileName], 2Eh ; '.'
0x1800045e1  jnz     short loc_1800045E9
0x1800045e3  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x1800045e7  jnz     short loc_180004664
0x1800045e9  xor     ecx, ecx
0x1800045eb  mov     rax, [rsp+320h+lpFileName]
0x1800045f0  mov     [rax], cx
0x1800045f3  mov     [rsp+320h+var_2B8], ecx
0x1800045f7  mov     rdx, rdi
0x1800045fa  lea     rcx, [rsp+320h+var_2E8]
0x1800045ff  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004605  lea     rdx, asc_18000BAE0; "\\"
0x18000460c  lea     rcx, [rsp+320h+var_2E8]
0x180004611  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004617  lea     rdx, [rbp+220h+FindFileData.cFileName]
0x18000461b  lea     rcx, [rsp+320h+var_2E8]
0x180004620  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004626  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x18000462a  jz      short loc_180004641
0x18000462c  mov     rdx, [rsp+320h+lpFileName]; unsigned __int16 *
0x180004631  mov     rcx, r14; this
0x180004634  call    ?DeleteDirectory@CONFIG_HISTORY_ENTITY@@QEAAJPEBG@Z; CONFIG_HISTORY_ENTITY::DeleteDirectory(ushort const *)
0x180004639  mov     ebx, eax
0x18000463b  test    eax, eax
0x18000463d  jnz     short loc_1800046B5
0x18000463f  jmp     short loc_180004664
0x180004641  mov     edx, 80h; dwFileAttributes
0x180004646  mov     rcx, [rsp+320h+lpFileName]; lpFileName
0x18000464b  call    cs:__imp_SetFileAttributesW
0x180004651  test    eax, eax
0x180004653  jz      short loc_1800046A4
0x180004655  mov     rcx, [rsp+320h+lpFileName]; lpFileName
0x18000465a  call    cs:__imp_DeleteFileW
0x180004660  test    eax, eax
0x180004662  jz      short loc_1800046A4
0x180004664  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x180004668  mov     rcx, rsi; hFindFile
0x18000466b  call    cs:__imp_FindNextFileW
0x180004671  cmp     eax, 1
0x180004674  jz      loc_1800045DC
0x18000467a  call    cs:__imp_GetLastError
0x180004680  mov     ebx, eax
0x180004682  cmp     eax, 12h
0x180004685  jnz     short loc_1800046B5
0x180004687  lea     edx, [rax+6Eh]; dwFileAttributes
0x18000468a  mov     rcx, rdi; lpFileName
0x18000468d  call    cs:__imp_SetFileAttributesW
0x180004693  test    eax, eax
0x180004695  jz      short loc_1800046A4
0x180004697  mov     rcx, rdi; lpPathName
0x18000469a  call    cs:__imp_RemoveDirectoryW
0x1800046a0  test    eax, eax
0x1800046a2  jnz     short loc_1800046B5
0x1800046a4  call    cs:__imp_GetLastError
0x1800046aa  mov     ebx, eax
0x1800046ac  jmp     short loc_1800046B5
0x1800046ae  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800046b2  lea     ebx, [rsi+4]
0x1800046b5  mov     rcx, rsi; hFindFile
0x1800046b8  call    cs:__imp_FindClose
0x1800046be  test    ebx, ebx
0x1800046c0  jle     short loc_1800046CD
0x1800046c2  movzx   ebx, bx
0x1800046c5  or      ebx, 80070000h
0x1800046cb  test    ebx, ebx
0x1800046cd  jz      short loc_1800046FD
0x1800046cf  mov     [rsp+320h+var_2F0], rdi
0x1800046d4  mov     r8d, 1
0x1800046da  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800046e1  add     rcx, 88h
0x1800046e8  mov     [rsp+320h+var_300], ebx
0x1800046ec  lea     r9, [rsp+320h+var_2F0]
0x1800046f1  mov     edx, 80002331h
0x1800046f6  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800046fc  nop
0x1800046fd  lea     rcx, [rsp+320h+var_2E8]
0x180004702  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004708  nop
0x180004709  lea     rcx, [rsp+320h+var_2B0]
0x18000470e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004714  mov     eax, ebx
0x180004716  mov     rcx, [rbp+220h+var_20]
0x18000471d  xor     rcx, rsp; StackCookie
0x180004720  call    __security_check_cookie
0x180004725  lea     r11, [rsp+320h+var_10]
0x18000472d  mov     rbx, [r11+30h]
0x180004731  mov     rsi, [r11+38h]
0x180004735  mov     rsp, r11
0x180004738  pop     r14
0x18000473a  pop     rdi
0x18000473b  pop     rbp
0x18000473c  retn
```
