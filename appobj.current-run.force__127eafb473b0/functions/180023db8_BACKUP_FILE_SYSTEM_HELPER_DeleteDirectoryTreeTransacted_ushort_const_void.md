# BACKUP_FILE_SYSTEM_HELPER::DeleteDirectoryTreeTransacted(ushort const *,void *)

- ea: `0x180023db8`
- end: `0x180024084`
- name: `?DeleteDirectoryTreeTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAX@Z`
- size: `716`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180023d04`
- `0x180023db8`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e60`
- `0x180023db8`
- `0x180033bc4`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023ef9`
- `msvcrt!_wcsicmp` at `0x180023f12`
- `msvcrt!_wcsicmp` at `0x180023ef9`
- `msvcrt!_wcsicmp` at `0x180023f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024027`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002403f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002403f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180023fec`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180023fec`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x180023fa5`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x180023fa5`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x180023ec1`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x180023ec1`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18002401d`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18002401d`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::DeleteDirectoryTreeTransacted(const unsigned __int16 *a1, void *a2)
{
  signed int PathCanonicalizationProof; // ebx
  HANDLE FirstFileTransactedW; // r14
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  _QWORD v11[4]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+68h] [rbp-98h]
  __int16 v14; // [rsp+6Ch] [rbp-94h]
  int v15; // [rsp+70h] [rbp-90h]
  _QWORD v16[4]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpPathName; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+A0h] [rbp-60h]
  __int16 v19; // [rsp+A4h] [rbp-5Ch]
  int v20; // [rsp+A8h] [rbp-58h]
  _QWORD v21[4]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpFileName; // [rsp+D0h] [rbp-30h]
  int v23; // [rsp+D8h] [rbp-28h]
  __int16 v24; // [rsp+DCh] [rbp-24h]
  int v25; // [rsp+E0h] [rbp-20h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+F0h] [rbp-10h] BYREF

  v16[0] = 0;
  lpPathName = (LPCWSTR)v16;
  v18 = 32;
  lpFileName = (LPCWSTR)v21;
  v19 = 256;
  v20 = 0;
  v21[0] = 0;
  v23 = 32;
  v24 = 256;
  v25 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 || a2 == (void *)-1LL )
  {
    PathCanonicalizationProof = -2147024809;
  }
  else
  {
    PathCanonicalizationProof = MakePathCanonicalizationProof(a1, (struct STRU *)v16);
    if ( PathCanonicalizationProof >= 0 )
    {
      PathCanonicalizationProof = STRU::Copy((STRU *)v21, (const struct STRU *)v16);
      if ( PathCanonicalizationProof >= 0 )
      {
        PathCanonicalizationProof = STRU::Append((STRU *)v21, L"\\*");
        if ( PathCanonicalizationProof >= 0 )
        {
          FirstFileTransactedW = FindFirstFileTransactedW(
                                   lpFileName,
                                   FindExInfoStandard,
                                   &FindFileData,
                                   FindExSearchNameMatch,
                                   0,
                                   0,
                                   a2);
          if ( FirstFileTransactedW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            PathCanonicalizationProof = LastError;
            if ( LastError > 0 )
              PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            do
            {
              if ( _wcsicmp(FindFileData.cFileName, L".")
                && _wcsicmp(FindFileData.cFileName, L"..")
                && (FindFileData.dwFileAttributes & 0x400) == 0 )
              {
                v11[0] = 0;
                v12 = (LPCWSTR)v11;
                v13 = 32;
                v14 = 256;
                v15 = 0;
                PathCanonicalizationProof = STRU::Copy((STRU *)v11, (const struct STRU *)v16);
                if ( PathCanonicalizationProof < 0 )
                  goto LABEL_19;
                PathCanonicalizationProof = STRU::Append((STRU *)v11, L"\\");
                if ( PathCanonicalizationProof < 0 )
                  goto LABEL_19;
                PathCanonicalizationProof = STRU::Append((STRU *)v11, FindFileData.cFileName);
                if ( PathCanonicalizationProof < 0 )
                  goto LABEL_19;
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  PathCanonicalizationProof = BACKUP_FILE_SYSTEM_HELPER::DeleteDirectoryTreeTransacted(v12, a2);
                  if ( PathCanonicalizationProof < 0 )
                    goto LABEL_19;
                }
                else if ( !DeleteFileTransactedW(v12, a2) )
                {
                  v7 = GetLastError();
                  PathCanonicalizationProof = v7;
                  if ( v7 > 0 )
                    PathCanonicalizationProof = (unsigned __int16)v7 | 0x80070000;
LABEL_19:
                  BUFFER::~BUFFER((BUFFER *)v11);
                  goto LABEL_30;
                }
                BUFFER::~BUFFER((BUFFER *)v11);
              }
            }
            while ( FindNextFileW(FirstFileTransactedW, &FindFileData) );
            v8 = GetLastError();
            if ( v8 != 18 )
            {
              if ( v8 > 0 )
                PathCanonicalizationProof = (unsigned __int16)v8 | 0x80070000;
              else
                PathCanonicalizationProof = v8;
            }
            if ( !RemoveDirectoryTransactedW(lpPathName, a2) )
            {
              v9 = GetLastError();
              PathCanonicalizationProof = v9;
              if ( v9 > 0 )
                PathCanonicalizationProof = (unsigned __int16)v9 | 0x80070000;
            }
LABEL_30:
            FindClose(FirstFileTransactedW);
          }
        }
      }
    }
  }
  BUFFER::~BUFFER((BUFFER *)v21);
  BUFFER::~BUFFER((BUFFER *)v16);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180023db8  mov     [rsp-8+arg_10], rbx
0x180023dbd  push    rbp
0x180023dbe  push    rsi
0x180023dbf  push    r14
0x180023dc1  lea     rbp, [rsp-250h]
0x180023dc9  sub     rsp, 350h
0x180023dd0  mov     rax, cs:__security_cookie
0x180023dd7  xor     rax, rsp
0x180023dda  mov     [rbp+260h+var_20], rax
0x180023de1  lea     rax, [rsp+360h+var_2E8]
0x180023de6  mov     [rsp+360h+var_2E8], 0
0x180023def  mov     [rbp+260h+lpPathName], rax
0x180023df3  mov     rsi, rdx
0x180023df6  lea     rax, [rbp+260h+var_2B0]
0x180023dfa  mov     [rbp+260h+var_2C0], 20h ; ' '
0x180023e01  mov     rbx, rcx
0x180023e04  mov     [rbp+260h+lpFileName], rax
0x180023e08  xor     edx, edx; Val
0x180023e0a  mov     [rbp+260h+var_2BC], 100h
0x180023e10  mov     r8d, 250h; Size
0x180023e16  mov     [rbp+260h+var_2B8], 0
0x180023e1d  lea     rcx, [rbp+260h+FindFileData]; void *
0x180023e21  mov     [rbp+260h+var_2B0], 0
0x180023e29  mov     [rbp+260h+var_288], 20h ; ' '
0x180023e30  mov     [rbp+260h+var_284], 100h
0x180023e36  mov     [rbp+260h+var_280], 0
0x180023e3d  call    memset_0
0x180023e42  test    rbx, rbx
0x180023e45  jz      loc_180024047
0x180023e4b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180023e4f  jz      loc_180024047
0x180023e55  lea     rdx, [rsp+360h+var_2E8]; this
0x180023e5a  mov     rcx, rbx; unsigned __int16 *
0x180023e5d  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180023e62  mov     ebx, eax
0x180023e64  test    eax, eax
0x180023e66  js      loc_18002404C
0x180023e6c  lea     rdx, [rsp+360h+var_2E8]; struct STRU *
0x180023e71  lea     rcx, [rbp+260h+var_2B0]; this
0x180023e75  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180023e7a  mov     ebx, eax
0x180023e7c  test    eax, eax
0x180023e7e  js      loc_18002404C
0x180023e84  lea     rdx, asc_18004D864; "\\*"
0x180023e8b  lea     rcx, [rbp+260h+var_2B0]; this
0x180023e8f  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180023e94  mov     ebx, eax
0x180023e96  test    eax, eax
0x180023e98  js      loc_18002404C
0x180023e9e  mov     rcx, [rbp+260h+lpFileName]; lpFileName
0x180023ea2  lea     r8, [rbp+260h+FindFileData]; lpFindFileData
0x180023ea6  mov     [rsp+360h+hTransaction], rsi; hTransaction
0x180023eab  xor     r9d, r9d; fSearchOp
0x180023eae  mov     [rsp+360h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180023eb6  xor     edx, edx; fInfoLevelId
0x180023eb8  mov     [rsp+360h+lpSearchFilter], 0; lpSearchFilter
0x180023ec1  call    cs:__imp_FindFirstFileTransactedW
0x180023ec7  mov     r14, rax
0x180023eca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023ece  jnz     short loc_180023EEE
0x180023ed0  call    cs:__imp_GetLastError
0x180023ed6  mov     ebx, eax
0x180023ed8  test    eax, eax
0x180023eda  jle     loc_18002404C
0x180023ee0  movzx   ebx, ax
0x180023ee3  or      ebx, 80070000h
0x180023ee9  jmp     loc_18002404C
0x180023eee  lea     rdx, asc_180039808; "."
0x180023ef5  lea     rcx, [rbp+260h+String1]; String1
0x180023ef9  call    cs:__imp__wcsicmp
0x180023eff  test    eax, eax
0x180023f01  jz      loc_180023FE5
0x180023f07  lea     rdx, asc_18004D86C; ".."
0x180023f0e  lea     rcx, [rbp+260h+String1]; String1
0x180023f12  call    cs:__imp__wcsicmp
0x180023f18  test    eax, eax
0x180023f1a  jz      loc_180023FE5
0x180023f20  test    [rbp+260h+FindFileData], 400h
0x180023f27  jnz     loc_180023FE5
0x180023f2d  lea     rax, [rsp+360h+var_320]
0x180023f32  mov     [rsp+360h+var_320], 0
0x180023f3b  lea     rdx, [rsp+360h+var_2E8]; struct STRU *
0x180023f40  mov     [rsp+360h+var_300], rax
0x180023f45  lea     rcx, [rsp+360h+var_320]; this
0x180023f4a  mov     [rsp+360h+var_2F8], 20h ; ' '
0x180023f52  mov     [rsp+360h+var_2F4], 100h
0x180023f59  mov     [rsp+360h+var_2F0], 0
0x180023f61  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180023f66  mov     ebx, eax
0x180023f68  test    eax, eax
0x180023f6a  js      short loc_180023FC4
0x180023f6c  lea     rdx, asc_180039420; "\\"
0x180023f73  lea     rcx, [rsp+360h+var_320]; this
0x180023f78  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180023f7d  mov     ebx, eax
0x180023f7f  test    eax, eax
0x180023f81  js      short loc_180023FC4
0x180023f83  lea     rdx, [rbp+260h+String1]; unsigned __int16 *
0x180023f87  lea     rcx, [rsp+360h+var_320]; this
0x180023f8c  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180023f91  mov     ebx, eax
0x180023f93  test    eax, eax
0x180023f95  js      short loc_180023FC4
0x180023f97  test    byte ptr [rbp+260h+FindFileData], 10h
0x180023f9b  mov     rdx, rsi; void *
0x180023f9e  mov     rcx, [rsp+360h+var_300]; unsigned __int16 *
0x180023fa3  jnz     short loc_180023FD0
0x180023fa5  call    cs:__imp_DeleteFileTransactedW
0x180023fab  test    eax, eax
0x180023fad  jnz     short loc_180023FDB
0x180023faf  call    cs:__imp_GetLastError
0x180023fb5  mov     ebx, eax
0x180023fb7  test    eax, eax
0x180023fb9  jle     short loc_180023FC4
0x180023fbb  movzx   ebx, ax
0x180023fbe  or      ebx, 80070000h
0x180023fc4  lea     rcx, [rsp+360h+var_320]; this
0x180023fc9  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023fce  jmp     short loc_18002403C
0x180023fd0  call    ?DeleteDirectoryTreeTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAX@Z; BACKUP_FILE_SYSTEM_HELPER::DeleteDirectoryTreeTransacted(ushort const *,void *)
0x180023fd5  mov     ebx, eax
0x180023fd7  test    eax, eax
0x180023fd9  js      short loc_180023FC4
0x180023fdb  lea     rcx, [rsp+360h+var_320]; this
0x180023fe0  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023fe5  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x180023fe9  mov     rcx, r14; hFindFile
0x180023fec  call    cs:__imp_FindNextFileW
0x180023ff2  test    eax, eax
0x180023ff4  jnz     loc_180023EEE
0x180023ffa  call    cs:__imp_GetLastError
0x180024000  cmp     eax, 12h
0x180024003  jz      short loc_180024016
0x180024005  test    eax, eax
0x180024007  jg      short loc_18002400D
0x180024009  mov     ebx, eax
0x18002400b  jmp     short loc_180024016
0x18002400d  movzx   ebx, ax
0x180024010  or      ebx, 80070000h
0x180024016  mov     rcx, [rbp+260h+lpPathName]; lpPathName
0x18002401a  mov     rdx, rsi; hTransaction
0x18002401d  call    cs:__imp_RemoveDirectoryTransactedW
0x180024023  test    eax, eax
0x180024025  jnz     short loc_18002403C
0x180024027  call    cs:__imp_GetLastError
0x18002402d  mov     ebx, eax
0x18002402f  test    eax, eax
0x180024031  jle     short loc_18002403C
0x180024033  movzx   ebx, ax
0x180024036  or      ebx, 80070000h
0x18002403c  mov     rcx, r14; hFindFile
0x18002403f  call    cs:__imp_FindClose
0x180024045  jmp     short loc_18002404C
0x180024047  mov     ebx, 80070057h
0x18002404c  lea     rcx, [rbp+260h+var_2B0]; this
0x180024050  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024055  lea     rcx, [rsp+360h+var_2E8]; this
0x18002405a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002405f  mov     eax, ebx
0x180024061  mov     rcx, [rbp+260h+var_20]
0x180024068  xor     rcx, rsp; StackCookie
0x18002406b  call    __security_check_cookie
0x180024070  mov     rbx, [rsp+360h+arg_10]
0x180024078  add     rsp, 350h
0x18002407f  pop     r14
0x180024081  pop     rsi
0x180024082  pop     rbp
0x180024083  retn
```
