# SusDeleteDirectoryWorker

- ea: `0x180048c80`
- end: `0x180048f91`
- name: `SusDeleteDirectoryWorker`
- size: `785`
- prototype: `__int64 __fastcall(PCNZWCH *, unsigned __int64 *, __int64, __int64, int, LPWIN32_FIND_DATAW lpFindFileData)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x180048c80`
- `0x180048f98`

## callees

- `0x1800110fc`
- `0x180048980`
- `0x180048c80`
- `0x180049508`
- `0x1800495f4`
- `0x180049984`
- `0x180049ce8`
- `0x18004a234`
- `0x180061960`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048f62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048cf6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048cf6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180048f0c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180048f0c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180048ea7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180048ea7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180048d32`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180048d32`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180048f27`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180048f27`

## string_xrefs

- `0x180048d8e`: `Final path verification failed for %ws`
- `0x180048d4d`: `Found reparse point at: %ws`
- `0x180048f31`: `SusDeleteDirectoryWorker failed`

## pseudocode

```c
__int64 __fastcall SusDeleteDirectoryWorker(
        PCNZWCH *a1,
        unsigned __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        LPWIN32_FIND_DATAW lpFindFileData)
{
  __int64 v7; // r14
  int v8; // r12d
  const WCHAR *v9; // rcx
  __int64 v10; // r13
  char *FileW; // rbx
  int NextFile; // edi
  unsigned __int64 v13; // r9
  int FirstFile; // eax
  unsigned __int64 v15; // r9
  int v16; // edi
  void *v17; // r8
  int v18; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-99h]
  bool v21; // [rsp+50h] [rbp-69h]
  HANDLE hFindFile; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int64 *v23; // [rsp+60h] [rbp-59h]
  char *v24; // [rsp+68h] [rbp-51h]
  char v25[8]; // [rsp+70h] [rbp-49h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+3Fh]

  v23 = a2;
  v7 = -1;
  hFindFile = (HANDLE)-1LL;
  v8 = 0;
  v9 = *a1;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  FileW = (char *)CreateFileW(v9, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  v24 = FileW;
  v21 = FileW + 1 == 0;
  if ( FileW == (char *)-1LL )
    goto LABEL_4;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
    goto LABEL_4;
  if ( (FileInformation.dwFileAttributes & 0x400) != 0 )
  {
    dwCreationDisposition[0] = 1;
    WUTrace(0, 0, 32, 2, *(_QWORD *)dwCreationDisposition, L"Found reparse point at: %ws", *a1);
LABEL_4:
    NextFile = 1;
    goto LABEL_32;
  }
  NextFile = VerifyFinalFilePath(FileW, *a1);
  if ( NextFile < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
      (const char *)(unsigned int)NextFile,
      (int)"Final path verification failed for %ws",
      (const char *)*a1);
    goto LABEL_36;
  }
  NextFile = WUAppendPathReAlloc((wchar_t **)a1, v23, L"*", v13);
  if ( NextFile < 0 )
    goto LABEL_32;
  memset(lpFindFileData, 0, sizeof(struct _WIN32_FIND_DATAW));
  FirstFile = SusFindFirstFile(*a1, lpFindFileData, &hFindFile);
  NextFile = FirstFile;
  if ( FirstFile < 0 )
  {
    if ( ((FirstFile + 2147024894) & 0xFFFFFFEE) == 0 && FirstFile != -2147024877 )
      NextFile = 0;
    v7 = (__int64)hFindFile;
    goto LABEL_32;
  }
  v7 = (__int64)hFindFile;
  do
  {
    (*a1)[v10] = 0;
    v16 = (int)v23;
    if ( WUAppendPathReAlloc((wchar_t **)a1, v23, lpFindFileData->cFileName, v15) < 0 )
      goto LABEL_28;
    if ( (lpFindFileData->dwFileAttributes & 0x10) == 0 )
    {
      if ( (lpFindFileData->dwFileAttributes & 1) == 0 || SetFileAttributesW(*a1, 0x80u) )
      {
        if ( (int)SusDeleteFileRetryIfSharingViolation(*a1, 0, v17) >= 0 )
          goto LABEL_29;
      }
      else
      {
        GetLastError();
      }
LABEL_28:
      v8 = 1;
      goto LABEL_29;
    }
    if ( (lpFindFileData->dwFileAttributes & 0x400) != 0 && lpFindFileData->dwReserved0 == -1610612733 )
      goto LABEL_28;
    v18 = SusDeleteDirectoryWorker((int)a1, v16, 1, 1, 0, lpFindFileData);
    if ( v18 < 0 || v18 == 1 )
      goto LABEL_28;
LABEL_29:
    NextFile = SusFindNextFile((HANDLE)v7, lpFindFileData);
  }
  while ( NextFile >= 0 );
  FileW = v24;
  if ( NextFile == -2147024878 )
    NextFile = v8 != 0;
LABEL_32:
  (*a1)[v10] = 0;
  if ( v7 != -1 )
    FindClose((HANDLE)v7);
  v25[0] = 1;
  SetFileInformationByHandle(FileW, FileDispositionInfo, v25, 1u);
  if ( NextFile < 0 )
  {
    dwCreationDisposition[0] = NextFile;
    WUTrace(0, 0, 32, 1, *(_QWORD *)dwCreationDisposition, L"SusDeleteDirectoryWorker failed");
  }
LABEL_36:
  if ( !v21 && FileW != (char *)-1LL )
    CloseHandle(FileW);
  return (unsigned int)NextFile;
}

```

## disassembly

```asm
0x180048c80  mov     [rsp-8+arg_10], rbx
0x180048c85  push    rbp
0x180048c86  push    rsi
0x180048c87  push    rdi
0x180048c88  push    r12
0x180048c8a  push    r13
0x180048c8c  push    r14
0x180048c8e  push    r15
0x180048c90  lea     rbp, [rsp-7]
0x180048c95  sub     rsp, 0C0h
0x180048c9c  mov     rax, cs:__security_cookie
0x180048ca3  xor     rax, rsp
0x180048ca6  mov     [rbp+37h+var_40], rax
0x180048caa  mov     [rbp+37h+var_90], rdx
0x180048cae  mov     rsi, rcx
0x180048cb1  mov     r15, [rbp+37h+lpFindFileData]
0x180048cb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048cb9  mov     r14, rax
0x180048cbc  mov     [rbp+37h+hFindFile], rax
0x180048cc0  xor     edi, edi
0x180048cc2  mov     r12d, edi
0x180048cc5  mov     rcx, [rcx]; lpFileName
0x180048cc8  mov     r13, rax
0x180048ccb  inc     r13
0x180048cce  cmp     [rcx+r13*2], di
0x180048cd3  jnz     short loc_180048CCB
0x180048cd5  mov     [rsp+0F0h+hTemplateFile], rdi; hTemplateFile
0x180048cda  mov     [rsp+0F0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180048ce2  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x180048cea  xor     r9d, r9d; lpSecurityAttributes
0x180048ced  mov     edx, 80010000h; dwDesiredAccess
0x180048cf2  lea     r8d, [r9+1]; dwShareMode
0x180048cf6  call    cs:__imp_CreateFileW
0x180048cfc  mov     rbx, rax
0x180048cff  mov     [rbp+37h+var_88], rax
0x180048d03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180048d07  setz    [rbp+37h+var_A0]
0x180048d0b  jnz     short loc_180048D17
0x180048d0d  mov     edi, 1
0x180048d12  jmp     loc_180048EF9
0x180048d17  xorps   xmm0, xmm0
0x180048d1a  xor     eax, eax
0x180048d1c  movups  xmmword ptr [rbp+37h+FileInformation.dwFileAttributes], xmm0
0x180048d20  movups  xmmword ptr [rbp+37h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180048d24  movups  xmmword ptr [rbp+37h+FileInformation.nFileSizeHigh], xmm0
0x180048d28  mov     [rbp+37h+FileInformation.nFileIndexLow], eax
0x180048d2b  lea     rdx, [rbp+37h+FileInformation]; lpFileInformation
0x180048d2f  mov     rcx, rbx; hFile
0x180048d32  call    cs:__imp_GetFileInformationByHandle
0x180048d38  test    eax, eax
0x180048d3a  jz      short loc_180048D0D
0x180048d3c  mov     rdx, [rsi]; lpString1
0x180048d3f  test    [rbp+37h+FileInformation.dwFileAttributes], 400h
0x180048d46  jz      short loc_180048D74
0x180048d48  mov     [rsp+0F0h+hTemplateFile], rdx
0x180048d4d  lea     rax, aFoundReparsePo; "Found reparse point at: %ws"
0x180048d54  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax
0x180048d59  mov     [rsp+0F0h+dwCreationDisposition], 1
0x180048d61  xor     edx, edx
0x180048d63  xor     ecx, ecx
0x180048d65  lea     r9d, [rdx+2]
0x180048d69  lea     r8d, [rdx+20h]
0x180048d6d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180048d72  jmp     short loc_180048D0D
0x180048d74  mov     rcx, rbx; hFile
0x180048d77  call    ?VerifyFinalFilePath@@YAJPEAXPEB_W@Z; VerifyFinalFilePath(void *,wchar_t const *)
0x180048d7c  mov     edi, eax
0x180048d7e  test    eax, eax
0x180048d80  jns     short loc_180048DB5
0x180048d82  mov     rcx, [rbp+3Fh]; this
0x180048d86  mov     rax, [rsi]
0x180048d89  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; char *
0x180048d8e  lea     rax, aFinalPathVerif; "Final path verification failed for %ws"
0x180048d95  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; int
0x180048d9a  mov     r9d, edi; char *
0x180048d9d  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180048da4  mov     edx, 1DFh; void *
0x180048da9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048dae  xor     esi, esi
0x180048db0  jmp     loc_180048F53
0x180048db5  lea     r8, asc_18007E744; "*"
0x180048dbc  mov     rdx, [rbp+37h+var_90]; unsigned __int64 *
0x180048dc0  mov     rcx, rsi; wchar_t **
0x180048dc3  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x180048dc8  mov     edi, eax
0x180048dca  test    eax, eax
0x180048dcc  js      loc_180048EF9
0x180048dd2  xor     edx, edx; Val
0x180048dd4  mov     r8d, 250h; Size
0x180048dda  mov     rcx, r15; void *
0x180048ddd  call    memset
0x180048de2  lea     r8, [rbp+37h+hFindFile]; void **
0x180048de6  mov     rdx, r15; struct _WIN32_FIND_DATAW *
0x180048de9  mov     rcx, [rsi]; wchar_t *
0x180048dec  call    ?SusFindFirstFile@@YAJPEB_WPEAU_WIN32_FIND_DATAW@@PEAPEAX@Z; SusFindFirstFile(wchar_t const *,_WIN32_FIND_DATAW *,void * *)
0x180048df1  mov     edi, eax
0x180048df3  xor     ecx, ecx
0x180048df5  test    eax, eax
0x180048df7  jns     short loc_180048E18
0x180048df9  add     eax, 7FF8FFFEh
0x180048dfe  test    eax, 0FFFFFFEEh
0x180048e03  jnz     short loc_180048E0F
0x180048e05  cmp     edi, 80070013h
0x180048e0b  jz      short loc_180048E0F
0x180048e0d  mov     edi, ecx
0x180048e0f  mov     r14, [rbp+37h+hFindFile]
0x180048e13  jmp     loc_180048EF9
0x180048e18  mov     r14, [rbp+37h+hFindFile]
0x180048e1c  jmp     short loc_180048E20
0x180048e1e  xor     ecx, ecx
0x180048e20  mov     rax, [rsi]
0x180048e23  mov     [rax+r13*2], cx
0x180048e28  lea     r8, [r15+2Ch]; wchar_t *
0x180048e2c  mov     rdi, [rbp+37h+var_90]
0x180048e30  mov     rdx, rdi; unsigned __int64 *
0x180048e33  mov     rcx, rsi; wchar_t **
0x180048e36  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x180048e3b  xor     ecx, ecx
0x180048e3d  test    eax, eax
0x180048e3f  js      loc_180048EC7
0x180048e45  test    byte ptr [r15], 10h
0x180048e49  jz      short loc_180048E99
0x180048e4b  test    dword ptr [r15], 400h
0x180048e52  jz      short loc_180048E5E
0x180048e54  cmp     dword ptr [r15+24h], 0A0000003h
0x180048e5c  jz      short loc_180048EC7
0x180048e5e  mov     [rsp+0F0h+var_A8], rcx
0x180048e63  mov     [rsp+0F0h+var_B0], ecx
0x180048e67  mov     [rsp+0F0h+var_B8], ecx
0x180048e6b  mov     dword ptr [rsp+0F0h+hTemplateFile], ecx
0x180048e6f  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r15; lpFindFileData
0x180048e74  mov     [rsp+0F0h+dwCreationDisposition], ecx; int
0x180048e78  mov     eax, 1
0x180048e7d  mov     r9d, eax; int
0x180048e80  mov     r8d, eax; int
0x180048e83  mov     rdx, rdi; int
0x180048e86  mov     rcx, rsi; int
0x180048e89  call    SusDeleteDirectoryWorker
0x180048e8e  test    eax, eax
0x180048e90  js      short loc_180048EC7
0x180048e92  cmp     eax, 1
0x180048e95  jnz     short loc_180048ECD
0x180048e97  jmp     short loc_180048EC7
0x180048e99  test    byte ptr [r15], 1
0x180048e9d  jz      short loc_180048EB9
0x180048e9f  mov     edx, 80h; dwFileAttributes
0x180048ea4  mov     rcx, [rsi]; lpFileName
0x180048ea7  call    cs:__imp_SetFileAttributesW
0x180048ead  test    eax, eax
0x180048eaf  jnz     short loc_180048EB9
0x180048eb1  call    cs:__imp_GetLastError
0x180048eb7  jmp     short loc_180048EC7
0x180048eb9  xor     edx, edx; unsigned int
0x180048ebb  mov     rcx, [rsi]; lpString1
0x180048ebe  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x180048ec3  test    eax, eax
0x180048ec5  jns     short loc_180048ECD
0x180048ec7  mov     r12d, 1
0x180048ecd  mov     rdx, r15; lpFindFileData
0x180048ed0  mov     rcx, r14; hFindFile
0x180048ed3  call    ?SusFindNextFile@@YAJPEAXPEAU_WIN32_FIND_DATAW@@@Z; SusFindNextFile(void *,_WIN32_FIND_DATAW *)
0x180048ed8  mov     edi, eax
0x180048eda  xor     eax, eax
0x180048edc  test    edi, edi
0x180048ede  jns     loc_180048E1E
0x180048ee4  cmp     edi, 80070012h
0x180048eea  mov     rbx, [rbp+37h+var_88]
0x180048eee  jnz     short loc_180048EF9
0x180048ef0  mov     edi, eax
0x180048ef2  test    r12d, r12d
0x180048ef5  setnz   dil
0x180048ef9  mov     rax, [rsi]
0x180048efc  xor     esi, esi
0x180048efe  mov     [rax+r13*2], si
0x180048f03  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180048f07  jz      short loc_180048F12
0x180048f09  mov     rcx, r14; hFindFile
0x180048f0c  call    cs:__imp_FindClose
0x180048f12  mov     [rbp+37h+var_80], 1
0x180048f16  mov     r9d, 1; dwBufferSize
0x180048f1c  lea     r8, [rbp+37h+var_80]; lpFileInformation
0x180048f20  lea     edx, [r9+3]; FileInformationClass
0x180048f24  mov     rcx, rbx; hFile
0x180048f27  call    cs:__imp_SetFileInformationByHandle
0x180048f2d  test    edi, edi
0x180048f2f  jns     short loc_180048F53
0x180048f31  lea     rax, aSusdeletedirec_0; "SusDeleteDirectoryWorker failed"
0x180048f38  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax
0x180048f3d  mov     [rsp+0F0h+dwCreationDisposition], edi
0x180048f41  xor     edx, edx
0x180048f43  xor     ecx, ecx
0x180048f45  lea     r9d, [rdx+1]
0x180048f49  lea     r8d, [rdx+20h]
0x180048f4d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180048f52  nop
0x180048f53  cmp     [rbp+37h+var_A0], sil
0x180048f57  jnz     short loc_180048F68
0x180048f59  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180048f5d  jz      short loc_180048F68
0x180048f5f  mov     rcx, rbx; hObject
0x180048f62  call    cs:__imp_CloseHandle
0x180048f68  mov     eax, edi
0x180048f6a  mov     rcx, [rbp+37h+var_40]
0x180048f6e  xor     rcx, rsp; StackCookie
0x180048f71  call    __security_check_cookie
0x180048f76  mov     rbx, [rsp+0F0h+arg_10]
0x180048f7e  add     rsp, 0C0h
0x180048f85  pop     r15
0x180048f87  pop     r14
0x180048f89  pop     r13
0x180048f8b  pop     r12
0x180048f8d  pop     rdi
0x180048f8e  pop     rsi
0x180048f8f  pop     rbp
0x180048f90  retn
```
