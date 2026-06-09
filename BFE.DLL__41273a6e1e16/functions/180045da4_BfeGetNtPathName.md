# BfeGetNtPathName

- ea: `0x180045da4`
- end: `0x180045ec3`
- name: `BfeGetNtPathName`
- size: `287`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180045b18`
- `0x1800629d0`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x180012e20`
- `0x1800197d0`
- `0x180044588`
- `0x180045da4`
- `0x18004a59c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180045e76`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180045e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045e85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045e2b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045e2b`

## string_xrefs

- `0x180045e4f`: `CreateFileW`
- `0x180045ea0`: `BfeGetNtPathName`

## pseudocode

```c
__int64 __fastcall BfeGetNtPathName(LPCWSTR lpSrc, _QWORD *a2)
{
  __int64 v4; // rax
  __int64 ObjectName; // rbx
  HANDLE FileW; // rax
  void *v7; // rsi
  DWORD LastError; // eax
  __int64 v9; // rcx
  char v10; // dl
  __int16 v11; // r8
  int v12; // r9d
  wchar_t dwCreationDisposition; // [rsp+20h] [rbp-28h]
  long double dwFlagsAndAttributes; // [rsp+28h] [rbp-20h]
  LPCWSTR lpFileName; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  lpFileName = 0;
  if ( !(unsigned int)_o__wcsicmp(lpSrc, L"System") )
  {
    v4 = WfpStringCopy(L"System");
LABEL_6:
    ObjectName = v4;
    goto LABEL_10;
  }
  ObjectName = BfeExpandEnvironmentStrings(lpSrc);
  if ( ObjectName )
    goto LABEL_10;
  FileW = CreateFileW(lpFileName, 0x80u, 0, 0, 3u, 0x80u, 0);
  v7 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = WfpReportSysErrorAsWinError(v9, "CreateFileW", LastError);
    goto LABEL_6;
  }
  ObjectName = BfeQueryObjectName(FileW);
  if ( !ObjectName )
    o(*a2, v10, v11, v12, dwCreationDisposition, dwFlagsAndAttributes);
  CloseHandle(v7);
LABEL_10:
  WfpMemFree(&lpFileName);
  if ( ObjectName )
    WfpReportError(ObjectName, "BfeGetNtPathName");
  return ObjectName;
}

```

## disassembly

```asm
0x180045da4  mov     [rsp+arg_0], rbx
0x180045da9  mov     [rsp+arg_10], rsi
0x180045dae  push    rdi
0x180045daf  sub     rsp, 40h
0x180045db3  mov     rdi, rdx
0x180045db6  mov     qword ptr [rdx], 0
0x180045dbd  lea     rdx, aSystem; "System"
0x180045dc4  mov     [rsp+48h+lpFileName], 0
0x180045dcd  mov     rbx, rcx
0x180045dd0  call    cs:__imp__o__wcsicmp
0x180045dd7  nop     dword ptr [rax+rax+00h]
0x180045ddc  test    eax, eax
0x180045dde  jnz     short loc_180045DF1
0x180045de0  mov     r8, rdi
0x180045de3  lea     rcx, aSystem; "System"
0x180045dea  call    WfpStringCopy
0x180045def  jmp     short loc_180045E5B
0x180045df1  lea     rdx, [rsp+48h+lpFileName]
0x180045df6  mov     rcx, rbx; lpSrc
0x180045df9  call    BfeExpandEnvironmentStrings
0x180045dfe  mov     rbx, rax
0x180045e01  test    rax, rax
0x180045e04  jnz     loc_180045E91
0x180045e0a  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x180045e0f  mov     edx, 80h; dwDesiredAccess
0x180045e14  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x180045e19  xor     r9d, r9d; lpSecurityAttributes
0x180045e1c  mov     dword ptr [rsp+48h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x180045e20  xor     r8d, r8d; dwShareMode
0x180045e23  mov     dword ptr [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180045e2b  call    cs:__imp_CreateFileW
0x180045e32  nop     dword ptr [rax+rax+00h]
0x180045e37  mov     rsi, rax
0x180045e3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045e3e  jnz     short loc_180045E60
0x180045e40  call    cs:__imp_GetLastError
0x180045e47  nop     dword ptr [rax+rax+00h]
0x180045e4c  mov     r8d, eax
0x180045e4f  lea     rdx, aCreatefilew; "CreateFileW"
0x180045e56  call    WfpReportSysErrorAsWinError
0x180045e5b  mov     rbx, rax
0x180045e5e  jmp     short loc_180045E91
0x180045e60  mov     rdx, rdi
0x180045e63  mov     rcx, rsi; Handle
0x180045e66  call    BfeQueryObjectName
0x180045e6b  mov     rbx, rax
0x180045e6e  test    rax, rax
0x180045e71  jnz     short loc_180045E82
0x180045e73  mov     rcx, [rdi]
0x180045e76  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180045e7d  nop     dword ptr [rax+rax+00h]
0x180045e82  mov     rcx, rsi; hObject
0x180045e85  call    cs:__imp_CloseHandle
0x180045e8c  nop     dword ptr [rax+rax+00h]
0x180045e91  lea     rcx, [rsp+48h+lpFileName]
0x180045e96  call    WfpMemFree
0x180045e9b  test    rbx, rbx
0x180045e9e  jz      short loc_180045EAF
0x180045ea0  lea     rdx, aBfegetntpathna; "BfeGetNtPathName"
0x180045ea7  mov     rcx, rbx
0x180045eaa  call    WfpReportError
0x180045eaf  mov     rsi, [rsp+48h+arg_10]
0x180045eb4  mov     rax, rbx
0x180045eb7  mov     rbx, [rsp+48h+arg_0]
0x180045ebc  add     rsp, 40h
0x180045ec0  pop     rdi
0x180045ec1  retn
```
