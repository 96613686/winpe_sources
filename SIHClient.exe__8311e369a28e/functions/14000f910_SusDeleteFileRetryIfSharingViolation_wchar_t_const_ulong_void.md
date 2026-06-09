# SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)

- ea: `0x14000f910`
- end: `0x14000faa9`
- name: `?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z`
- size: `409`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, unsigned int, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000e788`
- `0x140020d28`
- `0x1400333b4`

## callees

- `0x140008de4`
- `0x14000f5ac`
- `0x14000f910`
- `0x1400154b4`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f9c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000fa00`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000fa00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fa2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fa2c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000fa1d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x14000fa1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000f95a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000f95a`

## string_xrefs

- `0x14000fa69`: `Failed to delete file %ls`

## pseudocode

```c
__int64 __fastcall SusDeleteFileRetryIfSharingViolation(PCNZWCH lpString1, int a2, void *a3)
{
  int v3; // esi
  HANDLE FileW; // rax
  void *v7; // rbx
  signed int v8; // eax
  signed int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // r9
  signed int LastError; // eax
  int v14; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-48h]
  char FileInformation[4]; // [rsp+44h] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = 0;
  FileW = CreateFileW(lpString1, 0x80010000, 1u, 0, 3u, 0x200000u, 0);
  v7 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v11 = VerifyFinalFilePath(FileW, lpString1);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v10 = 1763;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v12,
        dwCreationDisposition);
      goto LABEL_27;
    }
    while ( 1 )
    {
      FileInformation[0] = 1;
      if ( SetFileInformationByHandle(v7, FileDispositionInfo, FileInformation, 1u) )
      {
        v9 = 0;
        goto LABEL_20;
      }
      LastError = GetLastError();
      v9 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v9 = LastError;
      if ( v9 >= 0 )
        break;
      if ( v9 != -2147024891 && v9 != -2147024864 )
        goto LABEL_24;
      v14 = v3++;
      if ( a2 == v14 )
      {
        v10 = 1809;
        goto LABEL_25;
      }
      Sleep(0x1F4u);
    }
    v9 = -2147418113;
LABEL_24:
    LODWORD(dwCreationDisposition) = v9;
    WUTrace(0, 0, 32, 3, dwCreationDisposition, L"Failed to delete file %ls");
    v10 = 1794;
LABEL_25:
    v12 = (unsigned int)v9;
    goto LABEL_26;
  }
  v8 = GetLastError();
  v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 <= 0 )
    v9 = v8;
  if ( v9 >= 0 )
  {
    v9 = -2147418113;
LABEL_8:
    v10 = 1760;
    goto LABEL_25;
  }
  if ( v9 != -2147024894 && v9 != -2147024893 )
    goto LABEL_8;
LABEL_27:
  if ( v7 != (void *)-1LL )
LABEL_20:
    CloseHandle(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000f910  mov     [rsp+arg_8], rbx
0x14000f915  mov     [rsp+arg_10], rbp
0x14000f91a  push    rsi
0x14000f91b  push    rdi
0x14000f91c  push    r14
0x14000f91e  sub     rsp, 50h
0x14000f922  mov     rax, cs:__security_cookie
0x14000f929  xor     rax, rsp
0x14000f92c  mov     [rsp+68h+var_20], rax
0x14000f931  xor     esi, esi
0x14000f933  mov     r14d, edx
0x14000f936  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x14000f93b  xor     r9d, r9d; lpSecurityAttributes
0x14000f93e  mov     [rsp+68h+dwFlagsAndAttributes], 200000h; dwFlagsAndAttributes
0x14000f946  mov     edx, 80010000h; dwDesiredAccess
0x14000f94b  mov     rbp, rcx
0x14000f94e  mov     dword ptr [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x14000f956  lea     r8d, [rsi+1]; dwShareMode
0x14000f95a  call    cs:__imp_CreateFileW
0x14000f960  mov     rbx, rax
0x14000f963  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000f967  jnz     short loc_14000F9AB
0x14000f969  call    cs:__imp_GetLastError
0x14000f96f  movzx   edi, ax
0x14000f972  or      edi, 80070000h
0x14000f978  test    eax, eax
0x14000f97a  cmovle  edi, eax
0x14000f97d  test    edi, edi
0x14000f97f  js      short loc_14000F988
0x14000f981  mov     edi, 8000FFFFh
0x14000f986  jmp     short loc_14000F9A1
0x14000f988  mov     eax, edi
0x14000f98a  cmp     edi, 80070002h
0x14000f990  jz      loc_14000FAA1
0x14000f996  cmp     eax, 80070003h
0x14000f99b  jz      loc_14000FAA1
0x14000f9a1  mov     edx, 6E0h
0x14000f9a6  jmp     loc_14000FA8D
0x14000f9ab  mov     rdx, rbp; lpString1
0x14000f9ae  mov     rcx, rbx; hFile
0x14000f9b1  call    ?VerifyFinalFilePath@@YAJPEAXPEB_W@Z; VerifyFinalFilePath(void *,wchar_t const *)
0x14000f9b6  mov     edi, eax
0x14000f9b8  test    eax, eax
0x14000f9ba  jns     short loc_14000FA06
0x14000f9bc  mov     r9d, eax
0x14000f9bf  mov     edx, 6E3h
0x14000f9c4  jmp     loc_14000FA90
0x14000f9c9  call    cs:__imp_GetLastError
0x14000f9cf  movzx   edi, ax
0x14000f9d2  or      edi, 80070000h
0x14000f9d8  test    eax, eax
0x14000f9da  cmovle  edi, eax
0x14000f9dd  test    edi, edi
0x14000f9df  jns     short loc_14000FA5D
0x14000f9e1  mov     eax, edi
0x14000f9e3  cmp     edi, 80070005h
0x14000f9e9  jz      short loc_14000F9F2
0x14000f9eb  cmp     eax, 80070020h
0x14000f9f0  jnz     short loc_14000FA62
0x14000f9f2  mov     eax, esi
0x14000f9f4  inc     esi
0x14000f9f6  cmp     r14d, eax
0x14000f9f9  jz      short loc_14000FA56
0x14000f9fb  mov     ecx, 1F4h; dwMilliseconds
0x14000fa00  call    cs:__imp_Sleep
0x14000fa06  mov     r9d, 1; dwBufferSize
0x14000fa0c  mov     [rsp+68h+FileInformation], 1
0x14000fa11  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x14000fa16  mov     rcx, rbx; hFile
0x14000fa19  lea     edx, [r9+3]; FileInformationClass
0x14000fa1d  call    cs:__imp_SetFileInformationByHandle
0x14000fa23  test    eax, eax
0x14000fa25  jz      short loc_14000F9C9
0x14000fa27  xor     edi, edi
0x14000fa29  mov     rcx, rbx; hObject
0x14000fa2c  call    cs:__imp_CloseHandle
0x14000fa32  mov     eax, edi
0x14000fa34  mov     rcx, [rsp+68h+var_20]
0x14000fa39  xor     rcx, rsp; StackCookie
0x14000fa3c  call    __security_check_cookie
0x14000fa41  lea     r11, [rsp+68h+var_18]
0x14000fa46  mov     rbx, [r11+28h]
0x14000fa4a  mov     rbp, [r11+30h]
0x14000fa4e  mov     rsp, r11
0x14000fa51  pop     r14
0x14000fa53  pop     rdi
0x14000fa54  pop     rsi
0x14000fa55  retn
0x14000fa56  mov     edx, 711h
0x14000fa5b  jmp     short loc_14000FA8D
0x14000fa5d  mov     edi, 8000FFFFh
0x14000fa62  xor     edx, edx
0x14000fa64  mov     [rsp+68h+hTemplateFile], rbp
0x14000fa69  lea     rax, aFailedToDelete; "Failed to delete file %ls"
0x14000fa70  xor     ecx, ecx
0x14000fa72  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rax
0x14000fa77  mov     dword ptr [rsp+68h+dwCreationDisposition], edi; int
0x14000fa7b  lea     r9d, [rdx+3]
0x14000fa7f  lea     r8d, [rdx+20h]
0x14000fa83  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000fa88  mov     edx, 702h; void *
0x14000fa8d  mov     r9d, edi; char *
0x14000fa90  mov     rcx, [rsp+68h]; this
0x14000fa95  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000fa9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000faa1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000faa5  jz      short loc_14000FA32
0x14000faa7  jmp     short loc_14000FA29
```
