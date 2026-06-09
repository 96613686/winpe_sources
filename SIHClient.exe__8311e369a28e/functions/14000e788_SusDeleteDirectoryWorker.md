# SusDeleteDirectoryWorker

- ea: `0x14000e788`
- end: `0x14000eaa0`
- name: `SusDeleteDirectoryWorker`
- size: `792`
- prototype: `__int64 __fastcall(PCNZWCH *, unsigned __int64 *, __int64, __int64, int, LPWIN32_FIND_DATAW lpFindFileData)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x14000e788`
- `0x14000eaa8`

## callees

- `0x14000e568`
- `0x14000e788`
- `0x14000f0c4`
- `0x14000f2cc`
- `0x14000f5ac`
- `0x14000f910`
- `0x140010148`
- `0x1400154b4`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e9bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ea71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ea71`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000e9b2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14000e9b2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000ea1b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000ea1b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000ea36`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000ea36`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x14000e83a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x14000e83a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000e7fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000e7fe`

## string_xrefs

- `0x14000e855`: `Found reparse point at: %ws`
- `0x14000e896`: `Final path verification failed for %ws`
- `0x14000ea40`: `SusDeleteDirectoryWorker failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SusDeleteDirectoryWorker(
        PCNZWCH *a1,
        unsigned __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        LPWIN32_FIND_DATAW lpFindFileData)
{
  __int64 v7; // rsi
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
    WUTrace(0, 0, 32, 2, *(_QWORD *)dwCreationDisposition, L"Found reparse point at: %ws");
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
        if ( (int)SusDeleteFileRetryIfSharingViolation(*a1, 3u, v17) >= 0 )
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
0x14000e788  mov     [rsp-8+arg_10], rbx
0x14000e78d  push    rbp
0x14000e78e  push    rsi
0x14000e78f  push    rdi
0x14000e790  push    r12
0x14000e792  push    r13
0x14000e794  push    r14
0x14000e796  push    r15
0x14000e798  lea     rbp, [rsp-7]
0x14000e79d  sub     rsp, 0C0h
0x14000e7a4  mov     rax, cs:__security_cookie
0x14000e7ab  xor     rax, rsp
0x14000e7ae  mov     [rbp+37h+var_40], rax
0x14000e7b2  mov     [rbp+37h+var_90], rdx
0x14000e7b6  mov     r14, rcx
0x14000e7b9  mov     r15, [rbp+37h+lpFindFileData]
0x14000e7bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e7c1  mov     rsi, rax
0x14000e7c4  mov     [rbp+37h+hFindFile], rax
0x14000e7c8  xor     edi, edi
0x14000e7ca  mov     r12d, edi
0x14000e7cd  mov     rcx, [rcx]; lpFileName
0x14000e7d0  mov     r13, rax
0x14000e7d3  inc     r13
0x14000e7d6  cmp     [rcx+r13*2], di
0x14000e7db  jnz     short loc_14000E7D3
0x14000e7dd  mov     [rsp+0F0h+hTemplateFile], rdi; hTemplateFile
0x14000e7e2  mov     [rsp+0F0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x14000e7ea  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x14000e7f2  xor     r9d, r9d; lpSecurityAttributes
0x14000e7f5  mov     edx, 80010000h; dwDesiredAccess
0x14000e7fa  lea     r8d, [r9+1]; dwShareMode
0x14000e7fe  call    cs:__imp_CreateFileW
0x14000e804  mov     rbx, rax
0x14000e807  mov     [rbp+37h+var_88], rax
0x14000e80b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000e80f  setz    [rbp+37h+var_A0]
0x14000e813  jnz     short loc_14000E81F
0x14000e815  mov     edi, 1
0x14000e81a  jmp     loc_14000EA07
0x14000e81f  xorps   xmm0, xmm0
0x14000e822  xor     eax, eax
0x14000e824  movups  xmmword ptr [rbp+37h+FileInformation.dwFileAttributes], xmm0
0x14000e828  movups  xmmword ptr [rbp+37h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x14000e82c  movups  xmmword ptr [rbp+37h+FileInformation.nFileSizeHigh], xmm0
0x14000e830  mov     [rbp+37h+FileInformation.nFileIndexLow], eax
0x14000e833  lea     rdx, [rbp+37h+FileInformation]; lpFileInformation
0x14000e837  mov     rcx, rbx; hFile
0x14000e83a  call    cs:__imp_GetFileInformationByHandle
0x14000e840  test    eax, eax
0x14000e842  jz      short loc_14000E815
0x14000e844  mov     rdx, [r14]; lpString1
0x14000e847  test    [rbp+37h+FileInformation.dwFileAttributes], 400h
0x14000e84e  jz      short loc_14000E87C
0x14000e850  mov     [rsp+0F0h+hTemplateFile], rdx
0x14000e855  lea     rax, aFoundReparsePo; "Found reparse point at: %ws"
0x14000e85c  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax
0x14000e861  mov     [rsp+0F0h+dwCreationDisposition], 1
0x14000e869  xor     edx, edx
0x14000e86b  xor     ecx, ecx
0x14000e86d  lea     r9d, [rdx+2]
0x14000e871  lea     r8d, [rdx+20h]
0x14000e875  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000e87a  jmp     short loc_14000E815
0x14000e87c  mov     rcx, rbx; hFile
0x14000e87f  call    ?VerifyFinalFilePath@@YAJPEAXPEB_W@Z; VerifyFinalFilePath(void *,wchar_t const *)
0x14000e884  mov     edi, eax
0x14000e886  test    eax, eax
0x14000e888  jns     short loc_14000E8BE
0x14000e88a  mov     rcx, [rbp+3Fh]; this
0x14000e88e  mov     rax, [r14]
0x14000e891  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax; char *
0x14000e896  lea     rax, aFinalPathVerif; "Final path verification failed for %ws"
0x14000e89d  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; int
0x14000e8a2  mov     r9d, edi; char *
0x14000e8a5  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000e8ac  mov     edx, 1DFh; void *
0x14000e8b1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000e8b6  xor     r14d, r14d
0x14000e8b9  jmp     loc_14000EA62
0x14000e8be  lea     r8, asc_14005458C; "*"
0x14000e8c5  mov     rdx, [rbp+37h+var_90]; unsigned __int64 *
0x14000e8c9  mov     rcx, r14; wchar_t **
0x14000e8cc  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x14000e8d1  mov     edi, eax
0x14000e8d3  test    eax, eax
0x14000e8d5  js      loc_14000EA07
0x14000e8db  xor     edx, edx; Val
0x14000e8dd  mov     r8d, 250h; Size
0x14000e8e3  mov     rcx, r15; void *
0x14000e8e6  call    memset
0x14000e8eb  lea     r8, [rbp+37h+hFindFile]; void **
0x14000e8ef  mov     rdx, r15; struct _WIN32_FIND_DATAW *
0x14000e8f2  mov     rcx, [r14]; wchar_t *
0x14000e8f5  call    ?SusFindFirstFile@@YAJPEB_WPEAU_WIN32_FIND_DATAW@@PEAPEAX@Z; SusFindFirstFile(wchar_t const *,_WIN32_FIND_DATAW *,void * *)
0x14000e8fa  mov     edi, eax
0x14000e8fc  xor     esi, esi
0x14000e8fe  test    eax, eax
0x14000e900  jns     short loc_14000E921
0x14000e902  add     eax, 7FF8FFFEh
0x14000e907  test    eax, 0FFFFFFEEh
0x14000e90c  jnz     short loc_14000E918
0x14000e90e  cmp     edi, 80070013h
0x14000e914  jz      short loc_14000E918
0x14000e916  mov     edi, esi
0x14000e918  mov     rsi, [rbp+37h+hFindFile]
0x14000e91c  jmp     loc_14000EA07
0x14000e921  mov     rsi, [rbp+37h+hFindFile]
0x14000e925  mov     rax, [r14]
0x14000e928  xor     edi, edi
0x14000e92a  mov     [rax+r13*2], di
0x14000e92f  lea     r8, [r15+2Ch]; wchar_t *
0x14000e933  mov     rdi, [rbp+37h+var_90]
0x14000e937  mov     rdx, rdi; unsigned __int64 *
0x14000e93a  mov     rcx, r14; wchar_t **
0x14000e93d  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x14000e942  xor     ecx, ecx
0x14000e944  test    eax, eax
0x14000e946  js      loc_14000E9D5
0x14000e94c  test    byte ptr [r15], 10h
0x14000e950  jz      short loc_14000E9A4
0x14000e952  test    dword ptr [r15], 400h
0x14000e959  jz      short loc_14000E965
0x14000e95b  cmp     dword ptr [r15+24h], 0A0000003h
0x14000e963  jz      short loc_14000E9D5
0x14000e965  mov     [rsp+0F0h+var_A8], rcx
0x14000e96a  mov     [rsp+0F0h+var_B0], 3
0x14000e972  mov     [rsp+0F0h+var_B8], ecx
0x14000e976  mov     dword ptr [rsp+0F0h+hTemplateFile], ecx
0x14000e97a  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r15; lpFindFileData
0x14000e97f  mov     [rsp+0F0h+dwCreationDisposition], ecx; int
0x14000e983  mov     eax, 1
0x14000e988  mov     r9d, eax; int
0x14000e98b  mov     r8d, eax; int
0x14000e98e  mov     rdx, rdi; int
0x14000e991  mov     rcx, r14; int
0x14000e994  call    SusDeleteDirectoryWorker
0x14000e999  test    eax, eax
0x14000e99b  js      short loc_14000E9D5
0x14000e99d  cmp     eax, 1
0x14000e9a0  jnz     short loc_14000E9DB
0x14000e9a2  jmp     short loc_14000E9D5
0x14000e9a4  test    byte ptr [r15], 1
0x14000e9a8  jz      short loc_14000E9C4
0x14000e9aa  mov     edx, 80h; dwFileAttributes
0x14000e9af  mov     rcx, [r14]; lpFileName
0x14000e9b2  call    cs:__imp_SetFileAttributesW
0x14000e9b8  test    eax, eax
0x14000e9ba  jnz     short loc_14000E9C4
0x14000e9bc  call    cs:__imp_GetLastError
0x14000e9c2  jmp     short loc_14000E9D5
0x14000e9c4  mov     edx, 3; unsigned int
0x14000e9c9  mov     rcx, [r14]; lpString1
0x14000e9cc  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x14000e9d1  test    eax, eax
0x14000e9d3  jns     short loc_14000E9DB
0x14000e9d5  mov     r12d, 1
0x14000e9db  mov     rdx, r15; lpFindFileData
0x14000e9de  mov     rcx, rsi; hFindFile
0x14000e9e1  call    ?SusFindNextFile@@YAJPEAXPEAU_WIN32_FIND_DATAW@@@Z; SusFindNextFile(void *,_WIN32_FIND_DATAW *)
0x14000e9e6  mov     edi, eax
0x14000e9e8  xor     eax, eax
0x14000e9ea  test    edi, edi
0x14000e9ec  jns     loc_14000E925
0x14000e9f2  cmp     edi, 80070012h
0x14000e9f8  mov     rbx, [rbp+37h+var_88]
0x14000e9fc  jnz     short loc_14000EA07
0x14000e9fe  mov     edi, eax
0x14000ea00  test    r12d, r12d
0x14000ea03  setnz   dil
0x14000ea07  mov     rax, [r14]
0x14000ea0a  xor     r14d, r14d
0x14000ea0d  mov     [rax+r13*2], r14w
0x14000ea12  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000ea16  jz      short loc_14000EA21
0x14000ea18  mov     rcx, rsi; hFindFile
0x14000ea1b  call    cs:__imp_FindClose
0x14000ea21  mov     [rbp+37h+var_80], 1
0x14000ea25  mov     r9d, 1; dwBufferSize
0x14000ea2b  lea     r8, [rbp+37h+var_80]; lpFileInformation
0x14000ea2f  lea     edx, [r9+3]; FileInformationClass
0x14000ea33  mov     rcx, rbx; hFile
0x14000ea36  call    cs:__imp_SetFileInformationByHandle
0x14000ea3c  test    edi, edi
0x14000ea3e  jns     short loc_14000EA62
0x14000ea40  lea     rax, aSusdeletedirec_0; "SusDeleteDirectoryWorker failed"
0x14000ea47  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rax
0x14000ea4c  mov     [rsp+0F0h+dwCreationDisposition], edi
0x14000ea50  xor     edx, edx
0x14000ea52  xor     ecx, ecx
0x14000ea54  lea     r9d, [rdx+1]
0x14000ea58  lea     r8d, [rdx+20h]
0x14000ea5c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000ea61  nop
0x14000ea62  cmp     [rbp+37h+var_A0], r14b
0x14000ea66  jnz     short loc_14000EA77
0x14000ea68  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000ea6c  jz      short loc_14000EA77
0x14000ea6e  mov     rcx, rbx; hObject
0x14000ea71  call    cs:__imp_CloseHandle
0x14000ea77  mov     eax, edi
0x14000ea79  mov     rcx, [rbp+37h+var_40]
0x14000ea7d  xor     rcx, rsp; StackCookie
0x14000ea80  call    __security_check_cookie
0x14000ea85  mov     rbx, [rsp+0F0h+arg_10]
0x14000ea8d  add     rsp, 0C0h
0x14000ea94  pop     r15
0x14000ea96  pop     r14
0x14000ea98  pop     r13
0x14000ea9a  pop     r12
0x14000ea9c  pop     rdi
0x14000ea9d  pop     rsi
0x14000ea9e  pop     rbp
0x14000ea9f  retn
```
