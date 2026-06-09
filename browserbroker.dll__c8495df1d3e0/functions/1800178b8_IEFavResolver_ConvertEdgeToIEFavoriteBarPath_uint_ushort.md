# IEFavResolver::ConvertEdgeToIEFavoriteBarPath(uint,ushort *)

- ea: `0x1800178b8`
- end: `0x1800179e9`
- name: `?ConvertEdgeToIEFavoriteBarPath@IEFavResolver@@AEAAJIPEAG@Z`
- size: `305`
- prototype: `__int64 __fastcall(IEFavResolver *this, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180017ff4`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000d17c`
- `0x1800178b8`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180017931`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18001794f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180017931`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x18001794f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800179a1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800179a1`

## string_xrefs

- `0x180017995`: `Links`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IEFavResolver::ConvertEdgeToIEFavoriteBarPath(IEFavResolver *this, __int64 a2, unsigned __int16 *a3)
{
  HRESULT v4; // edi
  unsigned __int16 *v5; // r8
  char v6; // bl
  WCHAR pszPathOut[15]; // [rsp+20h] [rbp-448h] BYREF
  unsigned __int16 v9; // [rsp+3Eh] [rbp-42Ah] BYREF
  char v10; // [rsp+40h] [rbp-428h] BYREF
  WCHAR pszMore[264]; // [rsp+230h] [rbp-238h] BYREF

  memset_0(pszPathOut, 0, 0x208u);
  v4 = StringCchCopyW(pszPathOut, 0x104u, a3);
  if ( v4 < 0 )
    return (unsigned int)v4;
  memset_0(pszMore, 0, 0x208u);
  if ( StrStrW(a3, L"_Favorites_Bar_\\") == a3 )
  {
    v5 = (unsigned __int16 *)&v10;
    goto LABEL_6;
  }
  v6 = 0;
  if ( StrStrW(a3, L"_Favorites_Bar_") == a3 )
  {
    v5 = &v9;
LABEL_6:
    v6 = 1;
    v4 = StringCchCopyW(pszMore, 0x104u, v5);
    if ( v4 < 0 )
      return (unsigned int)v4;
  }
  if ( v6 )
  {
    memset_0(pszPathOut, 0, 0x208u);
    v4 = PathCchCombine(pszPathOut, 0x104u, L"Links", pszMore);
    if ( v4 >= 0 )
      return (unsigned int)StringCchCopyW(a3, 0x104u, pszPathOut);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800178b8  mov     [rsp+arg_0], rbx
0x1800178bd  mov     [rsp+arg_8], rbp
0x1800178c2  push    rsi
0x1800178c3  push    rdi
0x1800178c4  push    r14
0x1800178c6  sub     rsp, 450h
0x1800178cd  mov     rax, cs:__security_cookie
0x1800178d4  xor     rax, rsp
0x1800178d7  mov     [rsp+468h+var_28], rax
0x1800178df  mov     rsi, r8
0x1800178e2  lea     rcx, [rsp+468h+pszPathOut]; void *
0x1800178e7  mov     r14d, 208h
0x1800178ed  xor     edx, edx; Val
0x1800178ef  mov     r8d, r14d; Size
0x1800178f2  call    memset_0
0x1800178f7  mov     ebp, 104h
0x1800178fc  lea     rcx, [rsp+468h+pszPathOut]; unsigned __int16 *
0x180017901  mov     edx, ebp; unsigned __int64
0x180017903  mov     r8, rsi; unsigned __int16 *
0x180017906  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001790b  mov     edi, eax
0x18001790d  test    eax, eax
0x18001790f  js      loc_1800179BF
0x180017915  mov     r8d, r14d; Size
0x180017918  lea     rcx, [rsp+468h+pszMore]; void *
0x180017920  xor     edx, edx; Val
0x180017922  call    memset_0
0x180017927  lea     rdx, pszSrch; "_Favorites_Bar_\\"
0x18001792e  mov     rcx, rsi; pszFirst
0x180017931  call    cs:__imp_StrStrW
0x180017937  cmp     rax, rsi
0x18001793a  jnz     short loc_180017943
0x18001793c  lea     r8, [rsp+468h+var_428]
0x180017941  jmp     short loc_18001795F
0x180017943  lea     rdx, aFavoritesBar_0; "_Favorites_Bar_"
0x18001794a  mov     rcx, rsi; pszFirst
0x18001794d  xor     bl, bl
0x18001794f  call    cs:__imp_StrStrW
0x180017955  cmp     rax, rsi
0x180017958  jnz     short loc_180017977
0x18001795a  lea     r8, [rsp+468h+var_42A]; unsigned __int16 *
0x18001795f  mov     rdx, rbp; unsigned __int64
0x180017962  lea     rcx, [rsp+468h+pszMore]; unsigned __int16 *
0x18001796a  mov     bl, 1
0x18001796c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017971  mov     edi, eax
0x180017973  test    eax, eax
0x180017975  js      short loc_1800179BF
0x180017977  test    bl, bl
0x180017979  jz      short loc_1800179BF
0x18001797b  mov     r8, r14; Size
0x18001797e  lea     rcx, [rsp+468h+pszPathOut]; void *
0x180017983  xor     edx, edx; Val
0x180017985  call    memset_0
0x18001798a  lea     r9, [rsp+468h+pszMore]; pszMore
0x180017992  mov     rdx, rbp; cchPathOut
0x180017995  lea     r8, aLinks; "Links"
0x18001799c  lea     rcx, [rsp+468h+pszPathOut]; pszPathOut
0x1800179a1  call    cs:__imp_PathCchCombine
0x1800179a7  mov     edi, eax
0x1800179a9  test    eax, eax
0x1800179ab  js      short loc_1800179BF
0x1800179ad  lea     r8, [rsp+468h+pszPathOut]; unsigned __int16 *
0x1800179b2  mov     rdx, rbp; unsigned __int64
0x1800179b5  mov     rcx, rsi; unsigned __int16 *
0x1800179b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800179bd  mov     edi, eax
0x1800179bf  mov     eax, edi
0x1800179c1  mov     rcx, [rsp+468h+var_28]
0x1800179c9  xor     rcx, rsp; StackCookie
0x1800179cc  call    __security_check_cookie
0x1800179d1  lea     r11, [rsp+468h+var_18]
0x1800179d9  mov     rbx, [r11+20h]
0x1800179dd  mov     rbp, [r11+28h]
0x1800179e1  mov     rsp, r11
0x1800179e4  pop     r14
0x1800179e6  pop     rdi
0x1800179e7  pop     rsi
0x1800179e8  retn
```
