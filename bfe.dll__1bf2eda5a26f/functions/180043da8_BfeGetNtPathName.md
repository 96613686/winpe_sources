# BfeGetNtPathName

- ea: `0x180043da8`
- end: `0x180043ea4`
- name: `BfeGetNtPathName`
- size: `252`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180043b5c`
- `0x1800606b0`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180012400`
- `0x180018b74`
- `0x18001d91c`
- `0x180043da8`
- `0x1800485bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043dd4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043dd4`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180043e64`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180043e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043e6d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043e25`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043e25`

## string_xrefs

- `0x180043e3d`: `CreateFileW`
- `0x180043e82`: `BfeGetNtPathName`

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
0x180043da8  mov     [rsp+arg_0], rbx
0x180043dad  mov     [rsp+arg_10], rsi
0x180043db2  push    rdi
0x180043db3  sub     rsp, 40h
0x180043db7  mov     rdi, rdx
0x180043dba  mov     qword ptr [rdx], 0
0x180043dc1  lea     rdx, aSystem; "System"
0x180043dc8  mov     [rsp+48h+lpFileName], 0
0x180043dd1  mov     rbx, rcx
0x180043dd4  call    cs:__imp__o__wcsicmp
0x180043dda  test    eax, eax
0x180043ddc  jnz     short loc_180043DEF
0x180043dde  mov     r8, rdi
0x180043de1  lea     rcx, aSystem; "System"
0x180043de8  call    WfpStringCopy
0x180043ded  jmp     short loc_180043E49
0x180043def  lea     rdx, [rsp+48h+lpFileName]
0x180043df4  mov     rcx, rbx; lpSrc
0x180043df7  call    BfeExpandEnvironmentStrings
0x180043dfc  mov     rbx, rax
0x180043dff  test    rax, rax
0x180043e02  jnz     short loc_180043E73
0x180043e04  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x180043e09  mov     edx, 80h; dwDesiredAccess
0x180043e0e  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x180043e13  xor     r9d, r9d; lpSecurityAttributes
0x180043e16  mov     dword ptr [rsp+48h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x180043e1a  xor     r8d, r8d; dwShareMode
0x180043e1d  mov     dword ptr [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180043e25  call    cs:__imp_CreateFileW
0x180043e2b  mov     rsi, rax
0x180043e2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043e32  jnz     short loc_180043E4E
0x180043e34  call    cs:__imp_GetLastError
0x180043e3a  mov     r8d, eax
0x180043e3d  lea     rdx, aCreatefilew; "CreateFileW"
0x180043e44  call    WfpReportSysErrorAsWinError
0x180043e49  mov     rbx, rax
0x180043e4c  jmp     short loc_180043E73
0x180043e4e  mov     rdx, rdi
0x180043e51  mov     rcx, rsi; Handle
0x180043e54  call    BfeQueryObjectName
0x180043e59  mov     rbx, rax
0x180043e5c  test    rax, rax
0x180043e5f  jnz     short loc_180043E6A
0x180043e61  mov     rcx, [rdi]
0x180043e64  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180043e6a  mov     rcx, rsi; hObject
0x180043e6d  call    cs:__imp_CloseHandle
0x180043e73  lea     rcx, [rsp+48h+lpFileName]
0x180043e78  call    WfpMemFree
0x180043e7d  test    rbx, rbx
0x180043e80  jz      short loc_180043E91
0x180043e82  lea     rdx, aBfegetntpathna; "BfeGetNtPathName"
0x180043e89  mov     rcx, rbx
0x180043e8c  call    WfpReportError
0x180043e91  mov     rsi, [rsp+48h+arg_10]
0x180043e96  mov     rax, rbx
0x180043e99  mov     rbx, [rsp+48h+arg_0]
0x180043e9e  add     rsp, 40h
0x180043ea2  pop     rdi
0x180043ea3  retn
```
