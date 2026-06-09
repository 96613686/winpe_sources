# OpenFavoritesFolderOrderKeyX(_ITEMIDLIST const *,HKEY__ * *,ushort const *)

- ea: `0x180015948`
- end: `0x180015a99`
- name: `?OpenFavoritesFolderOrderKeyX@@YAJPEFBU_ITEMIDLIST@@PEAPEAUHKEY__@@PEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, PHKEY phkResult, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180015774`

## callees

- `0x180002ce0`
- `0x18000d17c`
- `0x180015948`
- `0x1800216e0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18001598f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18001598f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x1800159ba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x1800159ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015a5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015a5d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180015a14`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180015a14`

## pseudocode

```c
HRESULT __fastcall OpenFavoritesFolderOrderKeyX(LPCITEMIDLIST pidl, PHKEY phkResult, const unsigned __int16 *a3)
{
  HRESULT result; // eax
  __int64 v6; // rax
  __int64 v7; // rcx
  WCHAR pszPath[264]; // [rsp+50h] [rbp-658h] BYREF
  WCHAR v9[264]; // [rsp+260h] [rbp-448h] BYREF
  WCHAR pszPathOut[264]; // [rsp+470h] [rbp-238h] BYREF

  result = StringCchCopyW(pszPath, 0x104u, a3);
  if ( result >= 0 )
  {
    PathRemoveBackslashW(pszPath);
    result = IEGetNameAndFlagsEx(pidl);
    if ( result >= 0 )
    {
      if ( PathIsPrefixW(pszPath, v9) )
      {
        v6 = -1;
        v7 = -1;
        do
          ++v7;
        while ( pszPath[v7] );
        do
          ++v6;
        while ( v9[v6] );
        if ( (int)v7 >= (int)v6 )
          result = StringCchCopyW(
                     pszPathOut,
                     0x104u,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\MenuOrder\\Favorites");
        else
          result = PathCchCombine(
                     pszPathOut,
                     0x104u,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\MenuOrder\\Favorites",
                     &v9[(int)v7 + 1]);
        if ( result >= 0 )
        {
          result = RegCreateKeyExW(HKEY_CURRENT_USER, pszPathOut, 0, 0, 0, 0x20019u, 0, phkResult, 0);
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
      else
      {
        return -2147418113;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015948  mov     [rsp+arg_18], rbx
0x18001594d  push    rbp
0x18001594e  push    rsi
0x18001594f  push    rdi
0x180015950  sub     rsp, 690h
0x180015957  mov     rax, cs:__security_cookie
0x18001595e  xor     rax, rsp
0x180015961  mov     [rsp+6A8h+var_28], rax
0x180015969  mov     rdi, rdx
0x18001596c  mov     rbx, rcx
0x18001596f  mov     ebp, 104h
0x180015974  lea     rcx, [rsp+6A8h+pszPath]; unsigned __int16 *
0x180015979  mov     edx, ebp; unsigned __int64
0x18001597b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015980  xor     esi, esi
0x180015982  test    eax, eax
0x180015984  js      loc_180015A76
0x18001598a  lea     rcx, [rsp+6A8h+pszPath]; pszPath
0x18001598f  call    cs:__imp_PathRemoveBackslashW
0x180015995  lea     r9, [rsp+6A8h+var_448]
0x18001599d  mov     rcx, rbx; pidl
0x1800159a0  call    IEGetNameAndFlagsEx
0x1800159a5  test    eax, eax
0x1800159a7  js      loc_180015A76
0x1800159ad  lea     rdx, [rsp+6A8h+var_448]; pszPath
0x1800159b5  lea     rcx, [rsp+6A8h+pszPath]; pszPrefix
0x1800159ba  call    cs:__imp_PathIsPrefixW
0x1800159c0  test    eax, eax
0x1800159c2  jz      loc_180015A71
0x1800159c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800159cc  lea     rdx, [rsp+6A8h+pszPath]
0x1800159d1  mov     rcx, rax
0x1800159d4  inc     rcx
0x1800159d7  cmp     [rdx+rcx*2], si
0x1800159db  jnz     short loc_1800159D4
0x1800159dd  lea     r8, [rsp+6A8h+var_448]
0x1800159e5  inc     rax
0x1800159e8  cmp     [r8+rax*2], si
0x1800159ed  jnz     short loc_1800159E5
0x1800159ef  lea     r8, pszPathIn; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800159f6  mov     rdx, rbp; unsigned __int64
0x1800159f9  cmp     ecx, eax
0x1800159fb  jge     short loc_180015A1C
0x1800159fd  movsxd  rax, ecx
0x180015a00  lea     r9, [rsp+6A8h+var_446]
0x180015a08  lea     rcx, [rsp+6A8h+pszPathOut]; pszPathOut
0x180015a10  lea     r9, [r9+rax*2]; pszMore
0x180015a14  call    cs:__imp_PathCchCombine
0x180015a1a  jmp     short loc_180015A29
0x180015a1c  lea     rcx, [rsp+6A8h+pszPathOut]; unsigned __int16 *
0x180015a24  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015a29  test    eax, eax
0x180015a2b  js      short loc_180015A76
0x180015a2d  mov     [rsp+6A8h+lpdwDisposition], rsi; lpdwDisposition
0x180015a32  lea     rdx, [rsp+6A8h+pszPathOut]; lpSubKey
0x180015a3a  mov     [rsp+6A8h+phkResult], rdi; phkResult
0x180015a3f  xor     r9d, r9d; lpClass
0x180015a42  mov     [rsp+6A8h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180015a47  xor     r8d, r8d; Reserved
0x180015a4a  mov     [rsp+6A8h+samDesired], 20019h; samDesired
0x180015a52  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180015a59  mov     [rsp+6A8h+dwOptions], esi; dwOptions
0x180015a5d  call    cs:__imp_RegCreateKeyExW
0x180015a63  test    eax, eax
0x180015a65  jle     short loc_180015A76
0x180015a67  movzx   eax, ax
0x180015a6a  or      eax, 80070000h
0x180015a6f  jmp     short loc_180015A76
0x180015a71  mov     eax, 8000FFFFh
0x180015a76  mov     rcx, [rsp+6A8h+var_28]
0x180015a7e  xor     rcx, rsp; StackCookie
0x180015a81  call    __security_check_cookie
0x180015a86  mov     rbx, [rsp+6A8h+arg_18]
0x180015a8e  add     rsp, 690h
0x180015a95  pop     rdi
0x180015a96  pop     rsi
0x180015a97  pop     rbp
0x180015a98  retn
```
