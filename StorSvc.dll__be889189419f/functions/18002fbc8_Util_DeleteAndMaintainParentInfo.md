# Util::DeleteAndMaintainParentInfo

- ea: `0x18002fbc8`
- end: `0x18002fd5b`
- name: `Util::DeleteAndMaintainParentInfo`
- size: `403`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x18002f190`
- `0x1800315c4`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180012714`
- `0x180019d4c`
- `0x18001dcf4`
- `0x18002fbc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fc3f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002fc3f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002fcbe`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002fcbe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fc7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fc7c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002fce4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002fce4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002fd1f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002fd1f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18002fc4f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18002fc4f`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002fca8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002fca8`

## string_xrefs

- `0x18002fccf`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002fcf5`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Util::DeleteAndMaintainParentInfo(LPCWSTR lpFileName, char a2)
{
  BOOL FileInformationByHandle; // edi
  HANDLE v5; // rbx
  HANDLE FileW; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  const char *v9; // r9
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  int FileInformation; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+4Ch] [rbp-B4h]
  __int128 v14; // [rsp+5Ch] [rbp-A4h]
  int v15; // [rsp+6Ch] [rbp-94h]
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  memset_0(pszPath, 0, 0x208u);
  FileInformation = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  FileInformationByHandle = 0;
  v5 = 0;
  hFile = 0;
  _o_wcscpy_s(pszPath, 260, lpFileName);
  if ( PathCchRemoveFileSpec(pszPath, 0x104u) >= 0 )
  {
    FileW = CreateFileW(pszPath, 0xC0000000, 3u, 0, 3u, 0x2000000u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    v5 = hFile;
    if ( hFile != (HANDLE)-1LL )
      FileInformationByHandle = GetFileInformationByHandleEx(hFile, FileBasicInfo, &FileInformation, 0x28u);
  }
  if ( a2 )
  {
    if ( !RemoveDirectoryW(lpFileName) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x75A,
                    (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
                    v7);
      goto LABEL_12;
    }
  }
  else if ( !DeleteFileW(lpFileName) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x75E,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
                  v9);
    goto LABEL_12;
  }
  if ( FileInformationByHandle )
    SetFileInformationByHandle(v5, FileBasicInfo, &FileInformation, 0x28u);
  LastError = 0;
LABEL_12:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return LastError;
}

```

## disassembly

```asm
0x18002fbc8  mov     [rsp-8+arg_8], rbx
0x18002fbcd  mov     [rsp-8+arg_10], rsi
0x18002fbd2  push    rbp
0x18002fbd3  push    rdi
0x18002fbd4  push    r14
0x18002fbd6  lea     rbp, [rsp-190h]
0x18002fbde  sub     rsp, 290h
0x18002fbe5  mov     rax, cs:__security_cookie
0x18002fbec  xor     rax, rsp
0x18002fbef  mov     [rbp+1A0h+var_20], rax
0x18002fbf6  mov     r14b, dl
0x18002fbf9  mov     rsi, rcx
0x18002fbfc  xor     edx, edx; Val
0x18002fbfe  mov     r8d, 208h; Size
0x18002fc04  lea     rcx, [rsp+2A0h+pszPath]; void *
0x18002fc09  call    memset_0
0x18002fc0e  mov     [rsp+2A0h+FileInformation], 0
0x18002fc16  xorps   xmm0, xmm0
0x18002fc19  xor     eax, eax
0x18002fc1b  movups  [rsp+2A0h+var_254], xmm0
0x18002fc20  movups  [rsp+2A0h+var_244], xmm0
0x18002fc25  mov     [rsp+2A0h+var_234], eax
0x18002fc29  xor     edi, edi
0x18002fc2b  xor     ebx, ebx
0x18002fc2d  mov     [rsp+2A0h+hFile], rbx
0x18002fc32  mov     r8, rsi
0x18002fc35  mov     edx, 104h
0x18002fc3a  lea     rcx, [rsp+2A0h+pszPath]
0x18002fc3f  call    cs:__imp__o_wcscpy_s
0x18002fc45  mov     edx, 104h; cchPath
0x18002fc4a  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x18002fc4f  call    cs:__imp_PathCchRemoveFileSpec
0x18002fc55  test    eax, eax
0x18002fc57  js      short loc_18002FCB6
0x18002fc59  mov     [rsp+2A0h+hTemplateFile], rbx; hTemplateFile
0x18002fc5e  mov     [rsp+2A0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002fc66  lea     r8d, [rdi+3]; dwShareMode
0x18002fc6a  mov     [rsp+2A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002fc6f  xor     r9d, r9d; lpSecurityAttributes
0x18002fc72  mov     edx, 0C0000000h; dwDesiredAccess
0x18002fc77  lea     rcx, [rsp+2A0h+pszPath]; lpFileName
0x18002fc7c  call    cs:__imp_CreateFileW
0x18002fc82  mov     rdx, rax
0x18002fc85  lea     rcx, [rsp+2A0h+hFile]
0x18002fc8a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002fc8f  mov     rbx, [rsp+2A0h+hFile]
0x18002fc94  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002fc98  jz      short loc_18002FCB6
0x18002fc9a  lea     r9d, [rdi+28h]; dwBufferSize
0x18002fc9e  lea     r8, [rsp+2A0h+FileInformation]; lpFileInformation
0x18002fca3  xor     edx, edx; FileInformationClass
0x18002fca5  mov     rcx, rbx; hFile
0x18002fca8  call    cs:__imp_GetFileInformationByHandleEx
0x18002fcae  lea     ecx, [rdi+1]
0x18002fcb1  test    eax, eax
0x18002fcb3  cmovnz  edi, ecx
0x18002fcb6  mov     rcx, rsi; lpFileName
0x18002fcb9  test    r14b, r14b
0x18002fcbc  jz      short loc_18002FCE4
0x18002fcbe  call    cs:__imp_RemoveDirectoryW
0x18002fcc4  test    eax, eax
0x18002fcc6  jnz     short loc_18002FD0B
0x18002fcc8  mov     rcx, [rbp+1A8h]; this
0x18002fccf  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002fcd6  mov     edx, 75Ah; void *
0x18002fcdb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fce0  mov     ebx, eax
0x18002fce2  jmp     short loc_18002FD28
0x18002fce4  call    cs:__imp_DeleteFileW
0x18002fcea  test    eax, eax
0x18002fcec  jnz     short loc_18002FD0B
0x18002fcee  mov     rcx, [rbp+1A8h]; this
0x18002fcf5  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002fcfc  mov     edx, 75Eh; void *
0x18002fd01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002fd06  nop
0x18002fd07  mov     ebx, eax
0x18002fd09  jmp     short loc_18002FD28
0x18002fd0b  test    edi, edi
0x18002fd0d  jz      short loc_18002FD26
0x18002fd0f  mov     r9d, 28h ; '('; dwBufferSize
0x18002fd15  lea     r8, [rsp+2A0h+FileInformation]; lpFileInformation
0x18002fd1a  xor     edx, edx; FileInformationClass
0x18002fd1c  mov     rcx, rbx; hFile
0x18002fd1f  call    cs:__imp_SetFileInformationByHandle
0x18002fd25  nop
0x18002fd26  xor     ebx, ebx
0x18002fd28  lea     rcx, [rsp+2A0h+hFile]
0x18002fd2d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002fd32  mov     eax, ebx
0x18002fd34  mov     rcx, [rbp+1A0h+var_20]
0x18002fd3b  xor     rcx, rsp; StackCookie
0x18002fd3e  call    __security_check_cookie
0x18002fd43  lea     r11, [rsp+2A0h+var_10]
0x18002fd4b  mov     rbx, [r11+28h]
0x18002fd4f  mov     rsi, [r11+30h]
0x18002fd53  mov     rsp, r11
0x18002fd56  pop     r14
0x18002fd58  pop     rdi
0x18002fd59  pop     rbp
0x18002fd5a  retn
```
