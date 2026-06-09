# wil::CreateFileAndEnsureNotLinked(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18001934c`
- end: `0x1800194f7`
- name: `?CreateFileAndEnsureNotLinked@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `427`
- prototype: `HRESULT __fastcall(const wchar_t *path, wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *fileHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180019240`

## callees

- `0x18001934c`
- `0x180019580`
- `0x180021efc`
- `0x180022460`
- `0x180022528`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001939c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019423`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001939c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019423`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800193ee`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001945c`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800193ee`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001945c`

## string_xrefs

- `0x1800193c5`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x18001946f`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800194b2`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
HRESULT __fastcall wil::CreateFileAndEnsureNotLinked(
        const wchar_t *path,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *fileHandle)
{
  HANDLE FileW; // rax
  void *m_ptr; // rcx
  unsigned int v6; // edx
  HANDLE v8; // rax
  unsigned int v9; // edx
  HRESULT LastError; // ebx
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > finalPathHandle; // [rsp+40h] [rbp-29h] BYREF
  _BY_HANDLE_FILE_INFORMATION fileInfo; // [rsp+48h] [rbp-21h] BYREF
  _BY_HANDLE_FILE_INFORMATION finalFileInfo; // [rsp+80h] [rbp+17h] BYREF
  void *retaddr; // [rsp+C8h] [rbp+5Fh]

  FileW = CreateFileW(path, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    fileHandle,
    FileW);
  m_ptr = fileHandle->m_ptr;
  if ( (((unsigned __int64)fileHandle->m_ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = 1086;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             v6,
             "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h");
  }
  memset(&fileInfo, 0, sizeof(fileInfo));
  if ( !GetFileInformationByHandle(m_ptr, &fileInfo) )
  {
    v6 = 1088;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             v6,
             "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h");
  }
  v8 = CreateFileW(path, 0, 0, 0, 3u, 0x2000000u, 0);
  finalPathHandle.m_ptr = v8;
  if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    memset(&finalFileInfo, 0, sizeof(finalFileInfo));
    if ( GetFileInformationByHandle(v8, &finalFileInfo) )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &finalPathHandle,
        (void *)0xFFFFFFFFFFFFFFFFLL);
      if ( fileInfo.nFileIndexLow == finalFileInfo.nFileIndexLow
        && fileInfo.nFileIndexHigh == finalFileInfo.nFileIndexHigh
        && fileInfo.dwVolumeSerialNumber == finalFileInfo.dwVolumeSerialNumber
        && fileInfo.nNumberOfLinks <= 1 )
      {
        LastError = 0;
      }
      else
      {
        LastError = -2147024735;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0x44Fu,
          "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
          -2147024735);
      }
      goto LABEL_17;
    }
    v9 = 1094;
  }
  else
  {
    v9 = 1092;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                v9,
                "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h");
LABEL_17:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&finalPathHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001934c  mov     [rsp-8+arg_10], rbx
0x180019351  mov     [rsp-8+arg_18], rdi
0x180019356  push    rbp
0x180019357  lea     rbp, [rsp-57h]
0x18001935c  sub     rsp, 0C0h
0x180019363  mov     rax, cs:__security_cookie
0x18001936a  xor     rax, rsp
0x18001936d  mov     [rbp+57h+var_8], rax
0x180019371  xor     r9d, r9d; lpSecurityAttributes
0x180019374  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18001937d  mov     rbx, fileHandle
0x180019380  mov     [rsp+0C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180019388  mov     edx, 80000000h; dwDesiredAccess
0x18001938d  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180019395  mov     rdi, path
0x180019398  lea     r8d, [r9+3]; dwShareMode
0x18001939c  call    cs:__imp_CreateFileW
0x1800193a2  mov     fileHandle, rax; ptr
0x1800193a5  mov     path, rbx; this
0x1800193a8  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800193ad  mov     path, [rbx]; hFile
0x1800193b0  lea     rax, [path+1]
0x1800193b4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800193ba  jnz     short loc_1800193D6
0x1800193bc  mov     edx, 43Eh; lineNumber
0x1800193c1  mov     path, [rbp+5Fh]; callerReturnAddress
0x1800193c5  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800193cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800193d1  jmp     loc_1800194D6
0x1800193d6  xorps   xmm0, xmm0
0x1800193d9  lea     fileHandle, [rbp+57h+fileInfo]; lpFileInformation
0x1800193dd  xor     eax, eax
0x1800193df  movups  xmmword ptr [rbp+57h+fileInfo.dwFileAttributes], xmm0
0x1800193e3  mov     [rbp+57h+fileInfo.nFileIndexLow], eax
0x1800193e6  movups  xmmword ptr [rbp+57h+fileInfo.ftLastAccessTime.dwHighDateTime], xmm0
0x1800193ea  movups  xmmword ptr [rbp+57h+fileInfo.nFileSizeHigh], xmm0
0x1800193ee  call    cs:__imp_GetFileInformationByHandle
0x1800193f4  test    eax, eax
0x1800193f6  jnz     short loc_1800193FF
0x1800193f8  mov     edx, 440h
0x1800193fd  jmp     short loc_1800193C1
0x1800193ff  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180019408  xor     r9d, r9d; lpSecurityAttributes
0x18001940b  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180019413  xor     r8d, r8d; dwShareMode
0x180019416  xor     edx, edx; dwDesiredAccess
0x180019418  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180019420  mov     path, rdi; lpFileName
0x180019423  call    cs:__imp_CreateFileW
0x180019429  mov     [rbp+57h+finalPathHandle.m_ptr], rax
0x18001942d  lea     path, [rax+1]
0x180019431  test    path, 0FFFFFFFFFFFFFFFEh
0x180019438  jnz     short loc_180019441
0x18001943a  mov     edx, 444h
0x18001943f  jmp     short loc_18001946B
0x180019441  xorps   xmm0, xmm0
0x180019444  lea     fileHandle, [rbp+57h+finalFileInfo]; lpFileInformation
0x180019448  xor     ecx, ecx
0x18001944a  mov     [rbp+57h+finalFileInfo.nFileIndexLow], ecx
0x18001944d  mov     path, rax; hFile
0x180019450  movups  xmmword ptr [rbp+57h+finalFileInfo.dwFileAttributes], xmm0
0x180019454  movups  xmmword ptr [rbp+57h+finalFileInfo.ftLastAccessTime.dwHighDateTime], xmm0
0x180019458  movups  xmmword ptr [rbp+57h+finalFileInfo.nFileSizeHigh], xmm0
0x18001945c  call    cs:__imp_GetFileInformationByHandle
0x180019462  test    eax, eax
0x180019464  jnz     short loc_18001947F
0x180019466  mov     edx, 446h; lineNumber
0x18001946b  mov     path, [rbp+5Fh]; callerReturnAddress
0x18001946f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180019476  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001947b  mov     ebx, eax
0x18001947d  jmp     short loc_1800194CB
0x18001947f  or      fileHandle, 0FFFFFFFFFFFFFFFFh; ptr
0x180019483  lea     path, [rbp+57h+finalPathHandle]; this
0x180019487  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001948c  mov     eax, [rbp+57h+finalFileInfo.nFileIndexLow]
0x18001948f  cmp     [rbp+57h+fileInfo.nFileIndexLow], eax
0x180019492  jnz     short loc_1800194AE
0x180019494  mov     eax, [rbp+57h+finalFileInfo.nFileIndexHigh]
0x180019497  cmp     [rbp+57h+fileInfo.nFileIndexHigh], eax
0x18001949a  jnz     short loc_1800194AE
0x18001949c  mov     eax, [rbp+57h+finalFileInfo.dwVolumeSerialNumber]
0x18001949f  cmp     [rbp+57h+fileInfo.dwVolumeSerialNumber], eax
0x1800194a2  jnz     short loc_1800194AE
0x1800194a4  cmp     [rbp+57h+fileInfo.nNumberOfLinks], 1
0x1800194a8  ja      short loc_1800194AE
0x1800194aa  xor     ebx, ebx
0x1800194ac  jmp     short loc_1800194CB
0x1800194ae  mov     path, [rbp+5Fh]; callerReturnAddress
0x1800194b2  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800194b9  mov     ebx, 800700A1h
0x1800194be  mov     edx, 44Fh; lineNumber
0x1800194c3  mov     r9d, ebx; hr
0x1800194c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194cb  lea     path, [rbp+57h+finalPathHandle]; this
0x1800194cf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800194d4  mov     eax, ebx
0x1800194d6  mov     path, [rbp+57h+var_8]
0x1800194da  xor     path, rsp; StackCookie
0x1800194dd  call    __security_check_cookie
0x1800194e2  lea     r11, [rsp+0C0h+var_s0]
0x1800194ea  mov     rbx, [r11+20h]
0x1800194ee  mov     rdi, [r11+28h]
0x1800194f2  mov     rsp, r11
0x1800194f5  pop     rbp
0x1800194f6  retn
```
