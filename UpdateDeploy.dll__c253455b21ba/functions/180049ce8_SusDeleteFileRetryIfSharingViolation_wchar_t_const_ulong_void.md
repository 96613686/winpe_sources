# SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)

- ea: `0x180049ce8`
- end: `0x180049e81`
- name: `?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z`
- size: `409`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int, void *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180048c80`
- `0x180051d7c`
- `0x180052ac4`
- `0x1800530e4`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180049984`
- `0x180049ce8`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049da1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049dd8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180049dd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049e04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049e04`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049d32`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180049d32`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180049df5`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180049df5`

## string_xrefs

- `0x180049e41`: `Failed to delete file %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    WUTrace(0, 0, 32, 3, dwCreationDisposition, L"Failed to delete file %ls", lpString1);
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
0x180049ce8  mov     [rsp+arg_8], rbx
0x180049ced  mov     [rsp+arg_10], rbp
0x180049cf2  push    rsi
0x180049cf3  push    rdi
0x180049cf4  push    r14
0x180049cf6  sub     rsp, 50h
0x180049cfa  mov     rax, cs:__security_cookie
0x180049d01  xor     rax, rsp
0x180049d04  mov     [rsp+68h+var_20], rax
0x180049d09  xor     esi, esi
0x180049d0b  mov     r14d, edx
0x180049d0e  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x180049d13  xor     r9d, r9d; lpSecurityAttributes
0x180049d16  mov     [rsp+68h+dwFlagsAndAttributes], 200000h; dwFlagsAndAttributes
0x180049d1e  mov     edx, 80010000h; dwDesiredAccess
0x180049d23  mov     rbp, rcx
0x180049d26  mov     dword ptr [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180049d2e  lea     r8d, [rsi+1]; dwShareMode
0x180049d32  call    cs:__imp_CreateFileW
0x180049d38  mov     rbx, rax
0x180049d3b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049d3f  jnz     short loc_180049D83
0x180049d41  call    cs:__imp_GetLastError
0x180049d47  movzx   edi, ax
0x180049d4a  or      edi, 80070000h
0x180049d50  test    eax, eax
0x180049d52  cmovle  edi, eax
0x180049d55  test    edi, edi
0x180049d57  js      short loc_180049D60
0x180049d59  mov     edi, 8000FFFFh
0x180049d5e  jmp     short loc_180049D79
0x180049d60  mov     eax, edi
0x180049d62  cmp     edi, 80070002h
0x180049d68  jz      loc_180049E79
0x180049d6e  cmp     eax, 80070003h
0x180049d73  jz      loc_180049E79
0x180049d79  mov     edx, 6E0h
0x180049d7e  jmp     loc_180049E65
0x180049d83  mov     rdx, rbp; lpString1
0x180049d86  mov     rcx, rbx; hFile
0x180049d89  call    ?VerifyFinalFilePath@@YAJPEAXPEB_W@Z; VerifyFinalFilePath(void *,wchar_t const *)
0x180049d8e  mov     edi, eax
0x180049d90  test    eax, eax
0x180049d92  jns     short loc_180049DDE
0x180049d94  mov     r9d, eax
0x180049d97  mov     edx, 6E3h
0x180049d9c  jmp     loc_180049E68
0x180049da1  call    cs:__imp_GetLastError
0x180049da7  movzx   edi, ax
0x180049daa  or      edi, 80070000h
0x180049db0  test    eax, eax
0x180049db2  cmovle  edi, eax
0x180049db5  test    edi, edi
0x180049db7  jns     short loc_180049E35
0x180049db9  mov     eax, edi
0x180049dbb  cmp     edi, 80070005h
0x180049dc1  jz      short loc_180049DCA
0x180049dc3  cmp     eax, 80070020h
0x180049dc8  jnz     short loc_180049E3A
0x180049dca  mov     eax, esi
0x180049dcc  inc     esi
0x180049dce  cmp     r14d, eax
0x180049dd1  jz      short loc_180049E2E
0x180049dd3  mov     ecx, 1F4h; dwMilliseconds
0x180049dd8  call    cs:__imp_Sleep
0x180049dde  mov     r9d, 1; dwBufferSize
0x180049de4  mov     [rsp+68h+FileInformation], 1
0x180049de9  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x180049dee  mov     rcx, rbx; hFile
0x180049df1  lea     edx, [r9+3]; FileInformationClass
0x180049df5  call    cs:__imp_SetFileInformationByHandle
0x180049dfb  test    eax, eax
0x180049dfd  jz      short loc_180049DA1
0x180049dff  xor     edi, edi
0x180049e01  mov     rcx, rbx; hObject
0x180049e04  call    cs:__imp_CloseHandle
0x180049e0a  mov     eax, edi
0x180049e0c  mov     rcx, [rsp+68h+var_20]
0x180049e11  xor     rcx, rsp; StackCookie
0x180049e14  call    __security_check_cookie
0x180049e19  lea     r11, [rsp+68h+var_18]
0x180049e1e  mov     rbx, [r11+28h]
0x180049e22  mov     rbp, [r11+30h]
0x180049e26  mov     rsp, r11
0x180049e29  pop     r14
0x180049e2b  pop     rdi
0x180049e2c  pop     rsi
0x180049e2d  retn
0x180049e2e  mov     edx, 711h
0x180049e33  jmp     short loc_180049E65
0x180049e35  mov     edi, 8000FFFFh
0x180049e3a  xor     edx, edx
0x180049e3c  mov     [rsp+68h+hTemplateFile], rbp
0x180049e41  lea     rax, aFailedToDelete; "Failed to delete file %ls"
0x180049e48  xor     ecx, ecx
0x180049e4a  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rax
0x180049e4f  mov     dword ptr [rsp+68h+dwCreationDisposition], edi; int
0x180049e53  lea     r9d, [rdx+3]
0x180049e57  lea     r8d, [rdx+20h]
0x180049e5b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180049e60  mov     edx, 702h; void *
0x180049e65  mov     r9d, edi; char *
0x180049e68  mov     rcx, [rsp+68h]; this
0x180049e6d  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180049e74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e79  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180049e7d  jz      short loc_180049E0A
0x180049e7f  jmp     short loc_180049E01
```
