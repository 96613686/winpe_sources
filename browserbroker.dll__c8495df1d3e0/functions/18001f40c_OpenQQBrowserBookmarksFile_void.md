# OpenQQBrowserBookmarksFile(void * *)

- ea: `0x18001f40c`
- end: `0x18001f5ac`
- name: `?OpenQQBrowserBookmarksFile@@YAJPEAPEAX@Z`
- size: `416`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x18000b280`

## callees

- `0x180002ce0`
- `0x180006c90`
- `0x18000d17c`
- `0x18001f40c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f4fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f56f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f4e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f4e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f560`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f560`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f493`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f516`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f52b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f493`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f516`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f52b`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f452`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f452`

## pseudocode

```c
__int64 __fastcall OpenQQBrowserBookmarksFile(void **a1)
{
  int v2; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszMore[264]; // [rsp+260h] [rbp+160h] BYREF

  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x15000u, 0, &ppszPath);
  if ( v2 >= 0 )
  {
    v2 = StringCchCopyW(pszPath, 0x104u, ppszPath);
    if ( v2 >= 0 )
    {
      v2 = PathCchAppend(pszPath, 0x104u, L"Tencent\\QQBrowser\\User Data\\Default");
      if ( v2 >= 0 )
      {
        pcbData = 520;
        if ( !RegGetValueW(
                HKEY_CURRENT_USER,
                L"Software\\Tencent\\QQBrowser\\Login",
                L"CcLoginUer",
                2u,
                0,
                pszMore,
                &pcbData)
          && (unsigned int)_o__wcsicmp(pszMore, L"0") )
        {
          PathCchAppend(pszPath, 0x104u, pszMore);
        }
        v2 = PathCchAppend(pszPath, 0x104u, L"Bookmarks");
        if ( v2 >= 0 )
        {
          FileW = CreateFileW(pszPath, 0x120089u, 3u, 0, 3u, 0x80u, 0);
          *a1 = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            v2 = LastError;
            if ( LastError > 0 )
              v2 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001f40c  push    rbp
0x18001f40e  push    rbx
0x18001f40f  push    rdi
0x18001f410  push    r14
0x18001f412  lea     rbp, [rsp-388h]
0x18001f41a  sub     rsp, 488h
0x18001f421  mov     rax, cs:__security_cookie
0x18001f428  xor     rax, rsp
0x18001f42b  mov     [rbp+3A0h+var_30], rax
0x18001f432  mov     rdi, rcx
0x18001f435  mov     [rsp+4A0h+ppszPath], 0
0x18001f43e  lea     rcx, FOLDERID_LocalAppData; rfid
0x18001f445  xor     r8d, r8d; hToken
0x18001f448  lea     r9, [rsp+4A0h+ppszPath]; ppszPath
0x18001f44d  mov     edx, 15000h; dwFlags
0x18001f452  call    cs:__imp_SHGetKnownFolderPath
0x18001f458  mov     ebx, eax
0x18001f45a  test    eax, eax
0x18001f45c  js      loc_18001F584
0x18001f462  mov     r8, [rsp+4A0h+ppszPath]; unsigned __int16 *
0x18001f467  lea     rcx, [rsp+4A0h+pszPath]; unsigned __int16 *
0x18001f46c  mov     r14d, 104h
0x18001f472  mov     edx, r14d; unsigned __int64
0x18001f475  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f47a  mov     ebx, eax
0x18001f47c  test    eax, eax
0x18001f47e  js      loc_18001F584
0x18001f484  lea     r8, aTencentQqbrows; "Tencent\\QQBrowser\\User Data\\Default"
0x18001f48b  mov     edx, r14d; cchPath
0x18001f48e  lea     rcx, [rsp+4A0h+pszPath]; pszPath
0x18001f493  call    cs:__imp_PathCchAppend
0x18001f499  mov     ebx, eax
0x18001f49b  test    eax, eax
0x18001f49d  js      loc_18001F584
0x18001f4a3  lea     rax, [rsp+4A0h+var_460]
0x18001f4a8  mov     [rsp+4A0h+var_460], 208h
0x18001f4b0  mov     [rsp+4A0h+pcbData], rax; pcbData
0x18001f4b5  lea     r8, aCcloginuer; "CcLoginUer"
0x18001f4bc  lea     rax, [rbp+3A0h+pszMore]
0x18001f4c3  mov     r9d, 2; dwFlags
0x18001f4c9  mov     [rsp+4A0h+pvData], rax; pvData
0x18001f4ce  lea     rdx, SubKey; "Software\\Tencent\\QQBrowser\\Login"
0x18001f4d5  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001f4dc  mov     [rsp+4A0h+pdwType], 0; pdwType
0x18001f4e5  call    cs:__imp_RegGetValueW
0x18001f4eb  test    eax, eax
0x18001f4ed  jnz     short loc_18001F51C
0x18001f4ef  lea     rdx, a0; "0"
0x18001f4f6  lea     rcx, [rbp+3A0h+pszMore]
0x18001f4fd  call    cs:__imp__o__wcsicmp
0x18001f503  test    eax, eax
0x18001f505  jz      short loc_18001F51C
0x18001f507  lea     r8, [rbp+3A0h+pszMore]; pszMore
0x18001f50e  mov     edx, r14d; cchPath
0x18001f511  lea     rcx, [rsp+4A0h+pszPath]; pszPath
0x18001f516  call    cs:__imp_PathCchAppend
0x18001f51c  lea     r8, aBookmarks; "Bookmarks"
0x18001f523  mov     rdx, r14; cchPath
0x18001f526  lea     rcx, [rsp+4A0h+pszPath]; pszPath
0x18001f52b  call    cs:__imp_PathCchAppend
0x18001f531  mov     ebx, eax
0x18001f533  test    eax, eax
0x18001f535  js      short loc_18001F584
0x18001f537  mov     [rsp+4A0h+pcbData], 0; hTemplateFile
0x18001f540  lea     rcx, [rsp+4A0h+pszPath]; lpFileName
0x18001f545  mov     r8d, 3; dwShareMode
0x18001f54b  mov     dword ptr [rsp+4A0h+pvData], 80h; dwFlagsAndAttributes
0x18001f553  xor     r9d, r9d; lpSecurityAttributes
0x18001f556  mov     dword ptr [rsp+4A0h+pdwType], r8d; dwCreationDisposition
0x18001f55b  mov     edx, 120089h; dwDesiredAccess
0x18001f560  call    cs:__imp_CreateFileW
0x18001f566  mov     [rdi], rax
0x18001f569  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f56d  jnz     short loc_18001F584
0x18001f56f  call    cs:__imp_GetLastError
0x18001f575  mov     ebx, eax
0x18001f577  test    eax, eax
0x18001f579  jle     short loc_18001F584
0x18001f57b  movzx   ebx, ax
0x18001f57e  or      ebx, 80070000h
0x18001f584  lea     rcx, [rsp+4A0h+ppszPath]
0x18001f589  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001f58e  mov     eax, ebx
0x18001f590  mov     rcx, [rbp+3A0h+var_30]
0x18001f597  xor     rcx, rsp; StackCookie
0x18001f59a  call    __security_check_cookie
0x18001f59f  add     rsp, 488h
0x18001f5a6  pop     r14
0x18001f5a8  pop     rdi
0x18001f5a9  pop     rbx
0x18001f5aa  pop     rbp
0x18001f5ab  retn
```
