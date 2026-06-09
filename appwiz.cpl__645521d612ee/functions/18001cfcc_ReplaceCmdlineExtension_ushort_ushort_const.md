# _ReplaceCmdlineExtension(ushort *,ushort const *)

- ea: `0x18001cfcc`
- end: `0x18001d091`
- name: `?_ReplaceCmdlineExtension@@YAXPEAGPEBG@Z`
- size: `197`
- prototype: `void __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001ce3c`

## callees

- `0x180007828`
- `0x18000791c`
- `0x18001cfcc`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!PathUnquoteSpacesW` at `0x18001d02e`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18001d02e`
- `SHLWAPI!PathQuoteSpacesW` at `0x18001d053`
- `SHLWAPI!PathQuoteSpacesW` at `0x18001d053`
- `SHLWAPI!PathGetArgsW` at `0x18001cff9`
- `SHLWAPI!PathGetArgsW` at `0x18001cff9`
- `SHLWAPI!PathFindExtensionW` at `0x18001d037`
- `SHLWAPI!PathFindExtensionW` at `0x18001d037`

## pseudocode

```c
void __fastcall _ReplaceCmdlineExtension(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  LPWSTR ArgsW; // rax
  const unsigned __int16 *v5; // rbx
  unsigned __int16 v6[264]; // [rsp+20h] [rbp-238h] BYREF

  ArgsW = PathGetArgsW(a1);
  if ( ArgsW )
  {
    v5 = ArgsW - 1;
    if ( !*ArgsW )
      v5 = ArgsW;
    StringCchCopyW(v6, 0x104u, v5);
    *v5 = 0;
    PathUnquoteSpacesW(a1);
    if ( !*PathFindExtensionW(a1) )
      StringCchCatW(a1, 0x104u, a2);
    PathQuoteSpacesW(a1);
    StringCchCatW(a1, 0x104u, v6);
  }
}

```

## disassembly

```asm
0x18001cfcc  mov     [rsp+arg_10], rbx
0x18001cfd1  mov     [rsp+arg_18], rbp
0x18001cfd6  push    rsi
0x18001cfd7  push    rdi
0x18001cfd8  push    r14
0x18001cfda  sub     rsp, 240h
0x18001cfe1  mov     rax, cs:__security_cookie
0x18001cfe8  xor     rax, rsp
0x18001cfeb  mov     [rsp+258h+var_28], rax
0x18001cff3  mov     rsi, rdx
0x18001cff6  mov     rdi, rcx
0x18001cff9  call    cs:__imp_PathGetArgsW
0x18001cfff  xor     r14d, r14d
0x18001d002  test    rax, rax
0x18001d005  jz      short loc_18001D069
0x18001d007  cmp     [rax], r14w
0x18001d00b  lea     rbx, [rax-2]
0x18001d00f  mov     ebp, 104h
0x18001d014  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x18001d019  cmovz   rbx, rax
0x18001d01d  mov     edx, ebp; unsigned __int64
0x18001d01f  mov     r8, rbx; unsigned __int16 *
0x18001d022  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d027  mov     rcx, rdi; lpsz
0x18001d02a  mov     [rbx], r14w
0x18001d02e  call    cs:__imp_PathUnquoteSpacesW
0x18001d034  mov     rcx, rdi; pszPath
0x18001d037  call    cs:__imp_PathFindExtensionW
0x18001d03d  cmp     [rax], r14w
0x18001d041  jnz     short loc_18001D050
0x18001d043  mov     r8, rsi; unsigned __int16 *
0x18001d046  mov     edx, ebp; unsigned __int64
0x18001d048  mov     rcx, rdi; unsigned __int16 *
0x18001d04b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d050  mov     rcx, rdi; lpsz
0x18001d053  call    cs:__imp_PathQuoteSpacesW
0x18001d059  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x18001d05e  mov     rdx, rbp; unsigned __int64
0x18001d061  mov     rcx, rdi; unsigned __int16 *
0x18001d064  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d069  mov     rcx, [rsp+258h+var_28]
0x18001d071  xor     rcx, rsp; StackCookie
0x18001d074  call    __security_check_cookie
0x18001d079  lea     r11, [rsp+258h+var_18]
0x18001d081  mov     rbx, [r11+30h]
0x18001d085  mov     rbp, [r11+38h]
0x18001d089  mov     rsp, r11
0x18001d08c  pop     r14
0x18001d08e  pop     rdi
0x18001d08f  pop     rsi
0x18001d090  retn
```
