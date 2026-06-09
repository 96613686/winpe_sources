# GetUserTileFolderPath_NoCreatePublicTilesFolder(ushort const *,ushort * *)

- ea: `0x1800c2fa0`
- end: `0x1800c30a7`
- name: `?GetUserTileFolderPath_NoCreatePublicTilesFolder@@YAJPEBGPEAPEAG@Z`
- size: `263`
- prototype: `__int64 __fastcall(PCWSTR pszMore, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task`

## callers

- `0x18004c994`

## callees

- `0x180014a10`
- `0x180015580`
- `0x18002be34`
- `0x180050ba0`
- `0x1800c2fa0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800c304f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800c304f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c302a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c3063`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c302a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c3063`
- `SHELL32!SHGetKnownFolderPath` at `0x1800c2fee`
- `SHELL32!SHGetKnownFolderPath` at `0x1800c2fee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserTileFolderPath_NoCreatePublicTilesFolder(PCWSTR pszMore, LPWSTR *ppwsz)
{
  HRESULT v4; // ebx
  HRESULT CurrentUsersSidString; // eax
  LPWSTR ppwsza; // [rsp+20h] [rbp-238h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  *ppwsz = 0;
  ppszPath = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_PublicUserTiles, 0x1000u, 0, &ppszPath);
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
0x1800c2fa0  mov     [rsp+arg_10], rbx
0x1800c2fa5  mov     [rsp+arg_18], rsi
0x1800c2faa  push    rdi
0x1800c2fab  sub     rsp, 250h
0x1800c2fb2  mov     rax, cs:__security_cookie
0x1800c2fb9  xor     rax, rsp
0x1800c2fbc  mov     [rsp+258h+var_18], rax
0x1800c2fc4  mov     rsi, rdx
0x1800c2fc7  mov     rdi, rcx
0x1800c2fca  mov     qword ptr [rdx], 0
0x1800c2fd1  mov     [rsp+258h+ppszPath], 0
0x1800c2fda  lea     r9, [rsp+258h+ppszPath]; ppszPath
0x1800c2fdf  xor     r8d, r8d; hToken
0x1800c2fe2  mov     edx, 1000h; dwFlags
0x1800c2fe7  lea     rcx, FOLDERID_PublicUserTiles; rfid
0x1800c2fee  call    cs:__imp_SHGetKnownFolderPath
0x1800c2ff4  mov     ebx, eax
0x1800c2ff6  test    eax, eax
0x1800c2ff8  js      short loc_1800C3076
0x1800c2ffa  mov     r8, [rsp+258h+ppszPath]; unsigned __int16 *
0x1800c2fff  mov     edx, 104h; unsigned __int64
0x1800c3004  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800c3009  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c300e  mov     ebx, eax
0x1800c3010  test    eax, eax
0x1800c3012  js      short loc_1800C3076
0x1800c3014  mov     [rsp+258h+ppwsz], 0
0x1800c301d  test    rdi, rdi
0x1800c3020  jz      short loc_1800C3032
0x1800c3022  lea     rdx, [rsp+258h+ppwsz]; ppwsz
0x1800c3027  mov     rcx, rdi; psz
0x1800c302a  call    cs:__imp_SHStrDupW
0x1800c3030  jmp     short loc_1800C303C
0x1800c3032  lea     rcx, [rsp+258h+ppwsz]; ppwsz
0x1800c3037  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x1800c303c  mov     ebx, eax
0x1800c303e  test    eax, eax
0x1800c3040  js      short loc_1800C306B
0x1800c3042  mov     r8, rdi; pszMore
0x1800c3045  mov     edx, 104h; cchPath
0x1800c304a  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800c304f  call    cs:__imp_PathCchAppend
0x1800c3055  mov     ebx, eax
0x1800c3057  test    eax, eax
0x1800c3059  js      short loc_1800C306B
0x1800c305b  mov     rdx, rsi; ppwsz
0x1800c305e  lea     rcx, [rsp+258h+pszPath]; psz
0x1800c3063  call    cs:__imp_SHStrDupW
0x1800c3069  mov     ebx, eax
0x1800c306b  lea     rcx, [rsp+258h+ppwsz]
0x1800c3070  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c3075  nop
0x1800c3076  lea     rcx, [rsp+258h+ppszPath]
0x1800c307b  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800c3080  mov     eax, ebx
0x1800c3082  mov     rcx, [rsp+258h+var_18]
0x1800c308a  xor     rcx, rsp; StackCookie
0x1800c308d  call    __security_check_cookie
0x1800c3092  lea     r11, [rsp+258h+var_8]
0x1800c309a  mov     rbx, [r11+20h]
0x1800c309e  mov     rsi, [r11+28h]
0x1800c30a2  mov     rsp, r11
0x1800c30a5  pop     rdi
0x1800c30a6  retn
```
