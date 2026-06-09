# IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)

- ea: `0x180018080`
- end: `0x1800181ce`
- name: `?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z`
- size: `334`
- prototype: `int(IEFavResolver *__hidden this, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180018c10`
- `0x180018d94`
- `0x180018f0c`
- `0x180019088`
- `0x1800192f8`
- `0x180019984`
- `0x18001a410`
- `0x18001aaf4`

## callees

- `0x180002ce0`
- `0x18000d17c`
- `0x180018080`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180018167`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180018167`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRelativePathToW` at `0x180018116`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRelativePathToW` at `0x180018116`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800180d2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800180d2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180018139`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001817d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180018139`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001817d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18001819f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x18001819f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180018158`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180018158`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001818d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001818d`

## pseudocode

```c
__int64 __fastcall IEFavResolver::GetUnifiedFolderPath(
        const WCHAR *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  HRESULT v6; // ebx
  const WCHAR *ExtensionW; // rax
  WCHAR pszStr1[264]; // [rsp+30h] [rbp-458h] BYREF
  WCHAR pszPath[264]; // [rsp+240h] [rbp-248h] BYREF

  v6 = StringCchCopyW(pszStr1, 0x104u, a2);
  if ( v6 >= 0 )
  {
    if ( StrCmpICW(pszStr1, this + 24) )
    {
      v6 = -2147467259;
      if ( PathRelativePathToW(pszPath, this + 24, 0x10u, pszStr1, 0x10u) )
      {
        if ( !StrCmpNICW(pszPath, L".\\", 2) )
        {
          v6 = PathCchCombine(a3, 0x104u, L"ROOT", pszPath);
          if ( v6 >= 0 )
          {
            ExtensionW = PathFindExtensionW(a2);
            if ( StrCmpNICW(ExtensionW, L".url", 4) || (v6 = PathCchRemoveFileSpec(a3, 0x104u), v6 >= 0) )
            {
              v6 = PathCchRemoveBackslash(a3, 0x104u);
              if ( v6 == 1 )
                return 0;
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)StringCchCopyW(a3, 0x104u, L"ROOT");
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018080  push    rbx
0x180018082  push    rbp
0x180018083  push    rsi
0x180018084  push    rdi
0x180018085  push    r14
0x180018087  sub     rsp, 460h
0x18001808e  mov     rax, cs:__security_cookie
0x180018095  xor     rax, rsp
0x180018098  mov     [rsp+488h+var_38], rax
0x1800180a0  mov     rdi, r8
0x1800180a3  mov     rbp, rdx
0x1800180a6  mov     r8, rdx; unsigned __int16 *
0x1800180a9  mov     rsi, rcx
0x1800180ac  mov     r14d, 104h
0x1800180b2  lea     rcx, [rsp+488h+pszStr1]; unsigned __int16 *
0x1800180b7  mov     edx, r14d; unsigned __int64
0x1800180ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800180bf  mov     ebx, eax
0x1800180c1  test    eax, eax
0x1800180c3  js      loc_1800181AE
0x1800180c9  lea     rdx, [rsi+30h]; pszStr2
0x1800180cd  lea     rcx, [rsp+488h+pszStr1]; pszStr1
0x1800180d2  call    cs:__imp_StrCmpICW
0x1800180d8  test    eax, eax
0x1800180da  jnz     short loc_1800180F5
0x1800180dc  lea     r8, aRoot_1; "ROOT"
0x1800180e3  mov     edx, r14d; unsigned __int64
0x1800180e6  mov     rcx, rdi; unsigned __int16 *
0x1800180e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800180ee  mov     ebx, eax
0x1800180f0  jmp     loc_1800181AE
0x1800180f5  mov     r8d, 10h; dwAttrFrom
0x1800180fb  lea     r9, [rsp+488h+pszStr1]; pszTo
0x180018100  lea     rdx, [rsi+30h]; pszFrom
0x180018104  mov     [rsp+488h+dwAttrTo], r8d; dwAttrTo
0x180018109  lea     rcx, [rsp+488h+pszPath]; pszPath
0x180018111  mov     ebx, 80004005h
0x180018116  call    cs:__imp_PathRelativePathToW
0x18001811c  test    eax, eax
0x18001811e  jz      loc_1800181AE
0x180018124  mov     r8d, 2; nChar
0x18001812a  lea     rdx, asc_1800324BC; ".\\"
0x180018131  lea     rcx, [rsp+488h+pszPath]; pszStr1
0x180018139  call    cs:__imp_StrCmpNICW
0x18001813f  test    eax, eax
0x180018141  jnz     short loc_1800181AE
0x180018143  lea     r9, [rsp+488h+pszPath]; pszMore
0x18001814b  mov     rdx, r14; cchPathOut
0x18001814e  lea     r8, aRoot_1; "ROOT"
0x180018155  mov     rcx, rdi; pszPathOut
0x180018158  call    cs:__imp_PathCchCombine
0x18001815e  mov     ebx, eax
0x180018160  test    eax, eax
0x180018162  js      short loc_1800181AE
0x180018164  mov     rcx, rbp; pszPath
0x180018167  call    cs:__imp_PathFindExtensionW
0x18001816d  mov     r8d, 4; nChar
0x180018173  lea     rdx, aUrl; ".url"
0x18001817a  mov     rcx, rax; pszStr1
0x18001817d  call    cs:__imp_StrCmpNICW
0x180018183  test    eax, eax
0x180018185  jnz     short loc_180018199
0x180018187  mov     rdx, r14; cchPath
0x18001818a  mov     rcx, rdi; pszPath
0x18001818d  call    cs:__imp_PathCchRemoveFileSpec
0x180018193  mov     ebx, eax
0x180018195  test    eax, eax
0x180018197  js      short loc_1800181AE
0x180018199  mov     rdx, r14; cchPath
0x18001819c  mov     rcx, rdi; pszPath
0x18001819f  call    cs:__imp_PathCchRemoveBackslash
0x1800181a5  mov     ebx, eax
0x1800181a7  cmp     eax, 1
0x1800181aa  jnz     short loc_1800181AE
0x1800181ac  xor     ebx, ebx
0x1800181ae  mov     eax, ebx
0x1800181b0  mov     rcx, [rsp+488h+var_38]
0x1800181b8  xor     rcx, rsp; StackCookie
0x1800181bb  call    __security_check_cookie
0x1800181c0  add     rsp, 460h
0x1800181c7  pop     r14
0x1800181c9  pop     rdi
0x1800181ca  pop     rsi
0x1800181cb  pop     rbp
0x1800181cc  pop     rbx
0x1800181cd  retn
```
