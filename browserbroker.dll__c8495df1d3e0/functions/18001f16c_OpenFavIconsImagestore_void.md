# OpenFavIconsImagestore(void * *)

- ea: `0x18001f16c`
- end: `0x18001f303`
- name: `?OpenFavIconsImagestore@@YAJPEAPEAX@Z`
- size: `407`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x18000b280`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006c90`
- `0x18001f16c`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18001f218`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHRegGetValueW` at `0x18001f218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f2b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f2b8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f268`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f283`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f268`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001f283`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f249`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001f249`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f1b2`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f1b2`

## pseudocode

```c
__int64 __fastcall OpenFavIconsImagestore(void **a1)
{
  int v2; // ebx
  LSTATUS ValueW; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszMore[264]; // [rsp+260h] [rbp+160h] BYREF

  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x15000u, 0, &ppszPath);
  if ( v2 >= 0 )
  {
    pcbData = 260;
    memset_0(pszMore, 0, 0x104u);
    ValueW = SHRegGetValueW(
               HKEY_CURRENT_USER,
               L"Software\\Microsoft\\Internet Explorer\\Main",
               L"ImageStoreRandomFolder",
               2,
               0,
               pszMore,
               &pcbData);
    v2 = ValueW;
    if ( ValueW > 0 )
      v2 = (unsigned __int16)ValueW | 0x80070000;
    if ( v2 >= 0 )
    {
      v2 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"Microsoft\\Internet Explorer\\imagestore\\");
      if ( v2 >= 0 )
      {
        v2 = PathCchAppend(pszPathOut, 0x104u, pszMore);
        if ( v2 >= 0 )
        {
          v2 = PathCchAppend(pszPathOut, 0x104u, L"imagestore.dat");
          if ( v2 >= 0 )
          {
            FileW = CreateFileW(pszPathOut, 0x120089u, 3u, 0, 3u, 0x80u, 0);
            *a1 = FileW;
            if ( !FileW )
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
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppszPath);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001f16c  push    rbp
0x18001f16e  push    rbx
0x18001f16f  push    rdi
0x18001f170  push    r14
0x18001f172  lea     rbp, [rsp-388h]
0x18001f17a  sub     rsp, 488h
0x18001f181  mov     rax, cs:__security_cookie
0x18001f188  xor     rax, rsp
0x18001f18b  mov     [rbp+3A0h+var_30], rax
0x18001f192  mov     rdi, rcx
0x18001f195  mov     [rsp+4A0h+ppszPath], 0
0x18001f19e  lea     rcx, FOLDERID_LocalAppData; rfid
0x18001f1a5  xor     r8d, r8d; hToken
0x18001f1a8  lea     r9, [rsp+4A0h+ppszPath]; ppszPath
0x18001f1ad  mov     edx, 15000h; dwFlags
0x18001f1b2  call    cs:__imp_SHGetKnownFolderPath
0x18001f1b8  mov     ebx, eax
0x18001f1ba  test    eax, eax
0x18001f1bc  js      loc_18001F2DB
0x18001f1c2  mov     r14d, 104h
0x18001f1c8  lea     rcx, [rbp+3A0h+pszMore]; void *
0x18001f1cf  mov     r8d, r14d; Size
0x18001f1d2  mov     [rsp+4A0h+var_460], r14d
0x18001f1d7  xor     edx, edx; Val
0x18001f1d9  call    memset_0
0x18001f1de  lea     rax, [rsp+4A0h+var_460]
0x18001f1e3  mov     r9d, 2; srrfFlags
0x18001f1e9  mov     [rsp+4A0h+pcbData], rax; pcbData
0x18001f1ee  lea     r8, aImagestorerand; "ImageStoreRandomFolder"
0x18001f1f5  lea     rax, [rbp+3A0h+pszMore]
0x18001f1fc  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001f203  mov     [rsp+4A0h+pvData], rax; pvData
0x18001f208  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x18001f20f  mov     [rsp+4A0h+pdwType], 0; pdwType
0x18001f218  call    cs:__imp_SHRegGetValueW
0x18001f21e  mov     ebx, eax
0x18001f220  test    eax, eax
0x18001f222  jle     short loc_18001F22D
0x18001f224  movzx   ebx, ax
0x18001f227  or      ebx, 80070000h
0x18001f22d  test    ebx, ebx
0x18001f22f  js      loc_18001F2DB
0x18001f235  mov     r8, [rsp+4A0h+ppszPath]; pszPathIn
0x18001f23a  lea     r9, aMicrosoftInter; "Microsoft\\Internet Explorer\\imagestor"...
0x18001f241  mov     rdx, r14; cchPathOut
0x18001f244  lea     rcx, [rsp+4A0h+pszPathOut]; pszPathOut
0x18001f249  call    cs:__imp_PathCchCombine
0x18001f24f  mov     ebx, eax
0x18001f251  test    eax, eax
0x18001f253  js      loc_18001F2DB
0x18001f259  lea     r8, [rbp+3A0h+pszMore]; pszMore
0x18001f260  mov     rdx, r14; cchPath
0x18001f263  lea     rcx, [rsp+4A0h+pszPathOut]; pszPath
0x18001f268  call    cs:__imp_PathCchAppend
0x18001f26e  mov     ebx, eax
0x18001f270  test    eax, eax
0x18001f272  js      short loc_18001F2DB
0x18001f274  lea     r8, aImagestoreDat; "imagestore.dat"
0x18001f27b  mov     rdx, r14; cchPath
0x18001f27e  lea     rcx, [rsp+4A0h+pszPathOut]; pszPath
0x18001f283  call    cs:__imp_PathCchAppend
0x18001f289  mov     ebx, eax
0x18001f28b  test    eax, eax
0x18001f28d  js      short loc_18001F2DB
0x18001f28f  mov     [rsp+4A0h+pcbData], 0; hTemplateFile
0x18001f298  lea     rcx, [rsp+4A0h+pszPathOut]; lpFileName
0x18001f29d  mov     r8d, 3; dwShareMode
0x18001f2a3  mov     dword ptr [rsp+4A0h+pvData], 80h; dwFlagsAndAttributes
0x18001f2ab  xor     r9d, r9d; lpSecurityAttributes
0x18001f2ae  mov     dword ptr [rsp+4A0h+pdwType], r8d; dwCreationDisposition
0x18001f2b3  mov     edx, 120089h; dwDesiredAccess
0x18001f2b8  call    cs:__imp_CreateFileW
0x18001f2be  mov     [rdi], rax
0x18001f2c1  test    rax, rax
0x18001f2c4  jnz     short loc_18001F2DB
0x18001f2c6  call    cs:__imp_GetLastError
0x18001f2cc  mov     ebx, eax
0x18001f2ce  test    eax, eax
0x18001f2d0  jle     short loc_18001F2DB
0x18001f2d2  movzx   ebx, ax
0x18001f2d5  or      ebx, 80070000h
0x18001f2db  lea     rcx, [rsp+4A0h+ppszPath]
0x18001f2e0  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001f2e5  mov     eax, ebx
0x18001f2e7  mov     rcx, [rbp+3A0h+var_30]
0x18001f2ee  xor     rcx, rsp; StackCookie
0x18001f2f1  call    __security_check_cookie
0x18001f2f6  add     rsp, 488h
0x18001f2fd  pop     r14
0x18001f2ff  pop     rdi
0x18001f300  pop     rbx
0x18001f301  pop     rbp
0x18001f302  retn
```
