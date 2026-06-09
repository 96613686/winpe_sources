# GetFirefoxBookmarksFilePath(ushort *,ulong)

- ea: `0x18001eb88`
- end: `0x18001ed01`
- name: `?GetFirefoxBookmarksFilePath@@YAJPEAGK@Z`
- size: `377`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, service_task`

## callers

- `0x18000c3a0`
- `0x18001f30c`

## callees

- `0x180002ce0`
- `0x180006c90`
- `0x18000d17c`
- `0x18001eb88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eca2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ec06`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ec3d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ec98`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ecc8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ec06`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ec3d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ec98`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001ecc8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001ec74`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18001ec74`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001ebcc`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001ebcc`

## pseudocode

```c
__int64 __fastcall GetFirefoxBookmarksFilePath(unsigned __int16 *a1)
{
  int v2; // ebx
  DWORD PrivateProfileStringW; // ebx
  signed int LastError; // eax
  PWSTR ppszPath[2]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR ReturnedString[264]; // [rsp+250h] [rbp-228h] BYREF

  ppszPath[0] = 0;
  v2 = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0x15000u, 0, ppszPath);
  if ( v2 >= 0 )
  {
    v2 = StringCchCopyW(a1, 0x104u, ppszPath[0]);
    if ( v2 >= 0 )
    {
      v2 = PathCchAppend(a1, 0x104u, L"Mozilla\\Firefox");
      if ( v2 >= 0 )
      {
        v2 = StringCchCopyW(pszPath, 0x104u, a1);
        if ( v2 >= 0 )
        {
          v2 = PathCchAppend(pszPath, 0x104u, L"profiles.ini");
          if ( v2 >= 0 )
          {
            PrivateProfileStringW = GetPrivateProfileStringW(L"Profile0", L"Path", 0, ReturnedString, 0x104u, pszPath);
            if ( GetLastError() == 2 || !PrivateProfileStringW )
            {
              LastError = GetLastError();
              v2 = LastError;
              if ( LastError > 0 )
                v2 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              v2 = PathCchAppend(a1, 0x104u, ReturnedString);
            }
            if ( v2 >= 0 )
              v2 = PathCchAppend(a1, 0x104u, L"places.sqlite");
          }
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
0x18001eb88  mov     [rsp+arg_8], rbx
0x18001eb8d  mov     [rsp+arg_10], rsi
0x18001eb92  push    rdi
0x18001eb93  sub     rsp, 470h
0x18001eb9a  mov     rax, cs:__security_cookie
0x18001eba1  xor     rax, rsp
0x18001eba4  mov     [rsp+478h+var_18], rax
0x18001ebac  mov     rdi, rcx
0x18001ebaf  mov     [rsp+478h+ppszPath], 0
0x18001ebb8  lea     rcx, FOLDERID_RoamingAppData; rfid
0x18001ebbf  xor     r8d, r8d; hToken
0x18001ebc2  lea     r9, [rsp+478h+ppszPath]; ppszPath
0x18001ebc7  mov     edx, 15000h; dwFlags
0x18001ebcc  call    cs:__imp_SHGetKnownFolderPath
0x18001ebd2  mov     ebx, eax
0x18001ebd4  test    eax, eax
0x18001ebd6  js      loc_18001ECD0
0x18001ebdc  mov     r8, [rsp+478h+ppszPath]; unsigned __int16 *
0x18001ebe1  mov     esi, 104h
0x18001ebe6  mov     edx, esi; unsigned __int64
0x18001ebe8  mov     rcx, rdi; unsigned __int16 *
0x18001ebeb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ebf0  mov     ebx, eax
0x18001ebf2  test    eax, eax
0x18001ebf4  js      loc_18001ECD0
0x18001ebfa  lea     r8, aMozillaFirefox; "Mozilla\\Firefox"
0x18001ec01  mov     edx, esi; cchPath
0x18001ec03  mov     rcx, rdi; pszPath
0x18001ec06  call    cs:__imp_PathCchAppend
0x18001ec0c  mov     ebx, eax
0x18001ec0e  test    eax, eax
0x18001ec10  js      loc_18001ECD0
0x18001ec16  mov     r8, rdi; unsigned __int16 *
0x18001ec19  lea     rcx, [rsp+478h+pszPath]; unsigned __int16 *
0x18001ec1e  mov     edx, esi; unsigned __int64
0x18001ec20  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ec25  mov     ebx, eax
0x18001ec27  test    eax, eax
0x18001ec29  js      loc_18001ECD0
0x18001ec2f  lea     r8, aProfilesIni; "profiles.ini"
0x18001ec36  mov     edx, esi; cchPath
0x18001ec38  lea     rcx, [rsp+478h+pszPath]; pszPath
0x18001ec3d  call    cs:__imp_PathCchAppend
0x18001ec43  mov     ebx, eax
0x18001ec45  test    eax, eax
0x18001ec47  js      loc_18001ECD0
0x18001ec4d  lea     rax, [rsp+478h+pszPath]
0x18001ec52  xor     r8d, r8d; lpDefault
0x18001ec55  mov     [rsp+478h+lpFileName], rax; lpFileName
0x18001ec5a  lea     r9, [rsp+478h+ReturnedString]; lpReturnedString
0x18001ec62  lea     rdx, KeyName; "Path"
0x18001ec69  mov     [rsp+478h+nSize], esi; nSize
0x18001ec6d  lea     rcx, AppName; "Profile0"
0x18001ec74  call    cs:__imp_GetPrivateProfileStringW
0x18001ec7a  mov     ebx, eax
0x18001ec7c  call    cs:__imp_GetLastError
0x18001ec82  cmp     eax, 2
0x18001ec85  jz      short loc_18001ECA2
0x18001ec87  test    ebx, ebx
0x18001ec89  jz      short loc_18001ECA2
0x18001ec8b  lea     r8, [rsp+478h+ReturnedString]; pszMore
0x18001ec93  mov     edx, esi; cchPath
0x18001ec95  mov     rcx, rdi; pszPath
0x18001ec98  call    cs:__imp_PathCchAppend
0x18001ec9e  mov     ebx, eax
0x18001eca0  jmp     short loc_18001ECB7
0x18001eca2  call    cs:__imp_GetLastError
0x18001eca8  mov     ebx, eax
0x18001ecaa  test    eax, eax
0x18001ecac  jle     short loc_18001ECB7
0x18001ecae  movzx   ebx, ax
0x18001ecb1  or      ebx, 80070000h
0x18001ecb7  test    ebx, ebx
0x18001ecb9  js      short loc_18001ECD0
0x18001ecbb  lea     r8, aPlacesSqlite; "places.sqlite"
0x18001ecc2  mov     rdx, rsi; cchPath
0x18001ecc5  mov     rcx, rdi; pszPath
0x18001ecc8  call    cs:__imp_PathCchAppend
0x18001ecce  mov     ebx, eax
0x18001ecd0  lea     rcx, [rsp+478h+ppszPath]
0x18001ecd5  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001ecda  mov     eax, ebx
0x18001ecdc  mov     rcx, [rsp+478h+var_18]
0x18001ece4  xor     rcx, rsp; StackCookie
0x18001ece7  call    __security_check_cookie
0x18001ecec  lea     r11, [rsp+478h+var_8]
0x18001ecf4  mov     rbx, [r11+18h]
0x18001ecf8  mov     rsi, [r11+20h]
0x18001ecfc  mov     rsp, r11
0x18001ecff  pop     rdi
0x18001ed00  retn
```
