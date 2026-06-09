# GetUserTileFolderPath(ushort const *,ushort * *)

- ea: `0x1800d38d8`
- end: `0x1800d39de`
- name: `?GetUserTileFolderPath@@YAJPEBGPEAPEAG@Z`
- size: `262`
- prototype: `__int64 __fastcall(PCWSTR pszMore, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task`

## callers

- `0x1800ca2f8`

## callees

- `0x180014a10`
- `0x180015580`
- `0x18002be34`
- `0x180050ba0`
- `0x1800d38d8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d3987`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800d3987`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800d3962`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800d399b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800d3962`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800d399b`
- `SHELL32!SHGetKnownFolderPath` at `0x1800d3926`
- `SHELL32!SHGetKnownFolderPath` at `0x1800d3926`

## pseudocode

```c
__int64 __fastcall GetUserTileFolderPath(PCWSTR pszMore, LPWSTR *ppwsz)
{
  HRESULT v4; // ebx
  HRESULT CurrentUsersSidString; // eax
  LPWSTR ppwsza; // [rsp+20h] [rbp-238h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  *ppwsz = 0;
  ppszPath = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_PublicUserTiles, 0x9000u, 0, &ppszPath);
  if ( v4 >= 0 )
  {
    v4 = StringCchCopyW(pszPath, 0x104u, ppszPath);
    if ( v4 >= 0 )
    {
      ppwsza = 0;
      if ( pszMore )
        CurrentUsersSidString = SHStrDupW(pszMore, &ppwsza);
      else
        CurrentUsersSidString = GetCurrentUsersSidString(&ppwsza);
      v4 = CurrentUsersSidString;
      if ( CurrentUsersSidString >= 0 )
      {
        v4 = PathCchAppend(pszPath, 0x104u, pszMore);
        if ( v4 >= 0 )
          v4 = SHStrDupW(pszPath, ppwsz);
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppwsza);
    }
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppszPath);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d38d8  mov     [rsp+arg_10], rbx
0x1800d38dd  mov     [rsp+arg_18], rsi
0x1800d38e2  push    rdi
0x1800d38e3  sub     rsp, 250h
0x1800d38ea  mov     rax, cs:__security_cookie
0x1800d38f1  xor     rax, rsp
0x1800d38f4  mov     [rsp+258h+var_18], rax
0x1800d38fc  mov     rsi, rdx
0x1800d38ff  mov     qword ptr [rdx], 0
0x1800d3906  mov     rdi, rcx
0x1800d3909  mov     [rsp+258h+ppszPath], 0
0x1800d3912  mov     edx, 9000h; dwFlags
0x1800d3917  lea     rcx, FOLDERID_PublicUserTiles; rfid
0x1800d391e  lea     r9, [rsp+258h+ppszPath]; ppszPath
0x1800d3923  xor     r8d, r8d; hToken
0x1800d3926  call    cs:__imp_SHGetKnownFolderPath
0x1800d392c  mov     ebx, eax
0x1800d392e  test    eax, eax
0x1800d3930  js      short loc_1800D39AD
0x1800d3932  mov     r8, [rsp+258h+ppszPath]; unsigned __int16 *
0x1800d3937  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800d393c  mov     edx, 104h; unsigned __int64
0x1800d3941  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d3946  mov     ebx, eax
0x1800d3948  test    eax, eax
0x1800d394a  js      short loc_1800D39AD
0x1800d394c  mov     [rsp+258h+ppwsz], 0
0x1800d3955  test    rdi, rdi
0x1800d3958  jz      short loc_1800D396A
0x1800d395a  lea     rdx, [rsp+258h+ppwsz]; ppwsz
0x1800d395f  mov     rcx, rdi; psz
0x1800d3962  call    cs:__imp_SHStrDupW
0x1800d3968  jmp     short loc_1800D3974
0x1800d396a  lea     rcx, [rsp+258h+ppwsz]; ppwsz
0x1800d396f  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x1800d3974  mov     ebx, eax
0x1800d3976  test    eax, eax
0x1800d3978  js      short loc_1800D39A3
0x1800d397a  mov     r8, rdi; pszMore
0x1800d397d  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800d3982  mov     edx, 104h; cchPath
0x1800d3987  call    cs:__imp_PathCchAppend
0x1800d398d  mov     ebx, eax
0x1800d398f  test    eax, eax
0x1800d3991  js      short loc_1800D39A3
0x1800d3993  mov     rdx, rsi; ppwsz
0x1800d3996  lea     rcx, [rsp+258h+pszPath]; psz
0x1800d399b  call    cs:__imp_SHStrDupW
0x1800d39a1  mov     ebx, eax
0x1800d39a3  lea     rcx, [rsp+258h+ppwsz]
0x1800d39a8  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800d39ad  lea     rcx, [rsp+258h+ppszPath]
0x1800d39b2  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800d39b7  mov     eax, ebx
0x1800d39b9  mov     rcx, [rsp+258h+var_18]
0x1800d39c1  xor     rcx, rsp; StackCookie
0x1800d39c4  call    __security_check_cookie
0x1800d39c9  lea     r11, [rsp+258h+var_8]
0x1800d39d1  mov     rbx, [r11+20h]
0x1800d39d5  mov     rsi, [r11+28h]
0x1800d39d9  mov     rsp, r11
0x1800d39dc  pop     rdi
0x1800d39dd  retn
```
