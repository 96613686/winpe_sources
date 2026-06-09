# CloudStoreUtilities::CreateFileEnsureNotLinked(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18003b968`
- end: `0x18003bb29`
- name: `?CreateFileEnsureNotLinked@CloudStoreUtilities@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003b5f4`

## callees

- `0x1800320d4`
- `0x18003b968`
- `0x18003bb30`
- `0x1800a15ac`
- `0x1800c8458`
- `0x1800fc644`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b9b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ba20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b9b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ba20`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18003b9ee`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18003ba4a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18003b9ee`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18003ba4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb1c`

## string_xrefs

- `0x18003bab7`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x18003bad0`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x18003bb01`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`

## pseudocode

```c
__int64 __fastcall CloudStoreUtilities::CreateFileEnsureNotLinked(LPCWSTR lpFileName, void **a2)
{
  HANDLE FileW; // rax
  const char *v5; // r9
  void *v6; // rcx
  HANDLE v7; // rbx
  const char *v8; // r9
  __int64 v10; // rdx
  unsigned int LastError; // edi
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-49h]
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-21h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v15; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    FileW);
  if ( *a2 == (void *)-1LL )
  {
    v10 = 704;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
             v5);
  }
  v6 = *a2;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(v6, &FileInformation) )
  {
    v10 = 706;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
             v5);
  }
  v7 = CreateFileW(lpFileName, 0, 0, 0, 3u, 0x2000000u, 0);
  if ( v7 == (HANDLE)-1LL )
  {
    v10 = 710;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
             v5);
  }
  memset(&v15, 0, sizeof(v15));
  if ( GetFileInformationByHandle(v7, &v15) )
  {
    if ( v7 )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v7);
    v13 = -1;
    if ( FileInformation.nFileIndexLow == v15.nFileIndexLow
      && FileInformation.nFileIndexHigh == v15.nFileIndexHigh
      && FileInformation.dwVolumeSerialNumber == v15.dwVolumeSerialNumber
      && FileInformation.nNumberOfLinks <= 1 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D2,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)0x800700A1LL,
        dwCreationDisposition);
      std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&v13);
      return 2147942561LL;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2C8,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
                  v8);
    if ( v7 )
      CloseHandle(v7);
    return LastError;
  }
}

```

## disassembly

```asm
0x18003b968  mov     [rsp-8+arg_10], rbx
0x18003b96d  mov     [rsp-8+arg_18], rdi
0x18003b972  push    rbp
0x18003b973  lea     rbp, [rsp-57h]
0x18003b978  sub     rsp, 0C0h
0x18003b97f  mov     rax, cs:__security_cookie
0x18003b986  xor     rax, rsp
0x18003b989  mov     [rbp+57h+var_8], rax
0x18003b98d  xor     r9d, r9d; lpSecurityAttributes
0x18003b990  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18003b999  mov     rbx, rdx
0x18003b99c  mov     [rsp+0C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003b9a4  mov     edx, 80000000h; dwDesiredAccess
0x18003b9a9  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003b9b1  mov     rdi, rcx
0x18003b9b4  lea     r8d, [r9+3]; dwShareMode
0x18003b9b8  call    cs:__imp_CreateFileW
0x18003b9be  mov     rdx, rax
0x18003b9c1  mov     rcx, rbx
0x18003b9c4  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003b9c9  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18003b9cd  jz      loc_18003BAC5
0x18003b9d3  mov     rcx, [rbx]; hFile
0x18003b9d6  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18003b9da  xorps   xmm0, xmm0
0x18003b9dd  xor     eax, eax
0x18003b9df  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x18003b9e3  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18003b9e6  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18003b9ea  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x18003b9ee  call    cs:__imp_GetFileInformationByHandle
0x18003b9f4  test    eax, eax
0x18003b9f6  jz      loc_18003BAF6
0x18003b9fc  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18003ba05  xor     r9d, r9d; lpSecurityAttributes
0x18003ba08  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18003ba10  xor     r8d, r8d; dwShareMode
0x18003ba13  xor     edx, edx; dwDesiredAccess
0x18003ba15  mov     [rsp+0C0h+dwCreationDisposition], 3; int
0x18003ba1d  mov     rcx, rdi; lpFileName
0x18003ba20  call    cs:__imp_CreateFileW
0x18003ba26  mov     rbx, rax
0x18003ba29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ba2d  jz      short loc_18003BAAE
0x18003ba2f  xorps   xmm0, xmm0
0x18003ba32  lea     rdx, [rbp+57h+var_40]; lpFileInformation
0x18003ba36  xor     eax, eax
0x18003ba38  mov     rcx, rbx; hFile
0x18003ba3b  movups  xmmword ptr [rbp+57h+var_40.dwFileAttributes], xmm0
0x18003ba3f  mov     [rbp+57h+var_40.nFileIndexLow], eax
0x18003ba42  movups  xmmword ptr [rbp+57h+var_40.ftLastAccessTime.dwHighDateTime], xmm0
0x18003ba46  movups  xmmword ptr [rbp+57h+var_40.nFileSizeHigh], xmm0
0x18003ba4a  call    cs:__imp_GetFileInformationByHandle
0x18003ba50  test    eax, eax
0x18003ba52  jz      loc_18003BAFD
0x18003ba58  test    rbx, rbx
0x18003ba5b  jz      short loc_18003BA65
0x18003ba5d  mov     rcx, rbx; hObject
0x18003ba60  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003ba65  mov     eax, [rbp+57h+var_40.nFileIndexLow]
0x18003ba68  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x18003ba70  cmp     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18003ba73  jnz     short loc_18003BACC
0x18003ba75  mov     eax, [rbp+57h+var_40.nFileIndexHigh]
0x18003ba78  cmp     [rbp+57h+FileInformation.nFileIndexHigh], eax
0x18003ba7b  jnz     short loc_18003BACC
0x18003ba7d  mov     eax, [rbp+57h+var_40.dwVolumeSerialNumber]
0x18003ba80  cmp     [rbp+57h+FileInformation.dwVolumeSerialNumber], eax
0x18003ba83  jnz     short loc_18003BACC
0x18003ba85  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x18003ba89  ja      short loc_18003BACC
0x18003ba8b  xor     eax, eax
0x18003ba8d  mov     rcx, [rbp+57h+var_8]
0x18003ba91  xor     rcx, rsp; StackCookie
0x18003ba94  call    __security_check_cookie
0x18003ba99  lea     r11, [rsp+0C0h+var_s0]
0x18003baa1  mov     rbx, [r11+20h]
0x18003baa5  mov     rdi, [r11+28h]
0x18003baa9  mov     rsp, r11
0x18003baac  pop     rbp
0x18003baad  retn
0x18003baae  mov     edx, 2C6h; void *
0x18003bab3  mov     rcx, [rbp+5Fh]; this
0x18003bab7  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003babe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003bac3  jmp     short loc_18003BA8D
0x18003bac5  mov     edx, 2C0h
0x18003baca  jmp     short loc_18003BAB3
0x18003bacc  mov     rcx, [rbp+5Fh]; this
0x18003bad0  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003bad7  mov     ebx, 800700A1h
0x18003badc  mov     edx, 2D2h; void *
0x18003bae1  mov     r9d, ebx; char *
0x18003bae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bae9  lea     rcx, [rbp+57h+var_80]
0x18003baed  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x18003baf2  mov     eax, ebx
0x18003baf4  jmp     short loc_18003BA8D
0x18003baf6  mov     edx, 2C2h
0x18003bafb  jmp     short loc_18003BAB3
0x18003bafd  mov     rcx, [rbp+5Fh]; this
0x18003bb01  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18003bb08  mov     edx, 2C8h; void *
0x18003bb0d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003bb12  mov     edi, eax
0x18003bb14  test    rbx, rbx
0x18003bb17  jz      short loc_18003BB22
0x18003bb19  mov     rcx, rbx; hObject
0x18003bb1c  call    cs:__imp_CloseHandle
0x18003bb22  mov     eax, edi
0x18003bb24  jmp     loc_18003BA8D
```
