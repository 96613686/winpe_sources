# OpenChromeBookmarksFile(void * *)

- ea: `0x18001f064`
- end: `0x18001f166`
- name: `?OpenChromeBookmarksFile@@YAJPEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x18000b280`

## callees

- `0x180002ce0`
- `0x180006c90`
- `0x18000d17c`
- `0x18001f064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f124`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f115`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f115`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f0e0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f0e0`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f0a3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f0a3`

## pseudocode

```c
__int64 __fastcall OpenChromeBookmarksFile(void **a1)
{
  int v2; // ebx
  unsigned int v3; // r11d
  HANDLE FileW; // rax
  signed int LastError; // eax
  PWSTR ppszPath[2]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-228h] BYREF

  ppszPath[0] = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x15000u, 0, ppszPath);
  if ( v2 >= 0 )
  {
    v2 = StringCchCopyW(pszPath, 0x104u, ppszPath[0]);
    if ( v2 >= 0 )
    {
      v2 = PathCchAppend(pszPath, v3, L"Google\\Chrome\\User Data\\Default\\Bookmarks");
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
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001f064  mov     [rsp+arg_8], rbx
0x18001f069  push    rdi
0x18001f06a  sub     rsp, 270h
0x18001f071  mov     rax, cs:__security_cookie
0x18001f078  xor     rax, rsp
0x18001f07b  mov     [rsp+278h+var_18], rax
0x18001f083  mov     rdi, rcx
0x18001f086  mov     [rsp+278h+ppszPath], 0
0x18001f08f  lea     rcx, FOLDERID_LocalAppData; rfid
0x18001f096  xor     r8d, r8d; hToken
0x18001f099  lea     r9, [rsp+278h+ppszPath]; ppszPath
0x18001f09e  mov     edx, 15000h; dwFlags
0x18001f0a3  call    cs:__imp_SHGetKnownFolderPath
0x18001f0a9  mov     ebx, eax
0x18001f0ab  test    eax, eax
0x18001f0ad  js      loc_18001F139
0x18001f0b3  mov     r8, [rsp+278h+ppszPath]; unsigned __int16 *
0x18001f0b8  lea     rcx, [rsp+278h+pszPath]; unsigned __int16 *
0x18001f0bd  mov     r11d, 104h
0x18001f0c3  mov     edx, r11d; unsigned __int64
0x18001f0c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f0cb  mov     ebx, eax
0x18001f0cd  test    eax, eax
0x18001f0cf  js      short loc_18001F139
0x18001f0d1  lea     r8, aGoogleChromeUs; "Google\\Chrome\\User Data\\Default\\Boo"...
0x18001f0d8  mov     edx, r11d; cchPath
0x18001f0db  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001f0e0  call    cs:__imp_PathCchAppend
0x18001f0e6  mov     ebx, eax
0x18001f0e8  test    eax, eax
0x18001f0ea  js      short loc_18001F139
0x18001f0ec  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x18001f0f5  lea     rcx, [rsp+278h+pszPath]; lpFileName
0x18001f0fa  mov     r8d, 3; dwShareMode
0x18001f100  mov     [rsp+278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001f108  xor     r9d, r9d; lpSecurityAttributes
0x18001f10b  mov     [rsp+278h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001f110  mov     edx, 120089h; dwDesiredAccess
0x18001f115  call    cs:__imp_CreateFileW
0x18001f11b  mov     [rdi], rax
0x18001f11e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f122  jnz     short loc_18001F139
0x18001f124  call    cs:__imp_GetLastError
0x18001f12a  mov     ebx, eax
0x18001f12c  test    eax, eax
0x18001f12e  jle     short loc_18001F139
0x18001f130  movzx   ebx, ax
0x18001f133  or      ebx, 80070000h
0x18001f139  lea     rcx, [rsp+278h+ppszPath]
0x18001f13e  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001f143  mov     eax, ebx
0x18001f145  mov     rcx, [rsp+278h+var_18]
0x18001f14d  xor     rcx, rsp; StackCookie
0x18001f150  call    __security_check_cookie
0x18001f155  mov     rbx, [rsp+278h+arg_8]
0x18001f15d  add     rsp, 270h
0x18001f164  pop     rdi
0x18001f165  retn
```
