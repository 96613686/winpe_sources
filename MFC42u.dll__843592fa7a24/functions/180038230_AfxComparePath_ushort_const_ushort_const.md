# AfxComparePath(ushort const *,ushort const *)

- ea: `0x180038230`
- end: `0x180038355`
- name: `?AfxComparePath@@YAHPEBG0@Z`
- size: `293`
- prototype: `__int64 __fastcall(LPCWCH lpSrcStr, LPCWCH)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002caa0`
- `0x1800610f0`
- `0x180071e80`
- `0x18008f590`
- `0x180098720`

## callees

- `0x180038230`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180038296`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180038296`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x1800382b8`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x1800382d5`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x1800382f5`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x1800382b8`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x1800382d5`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x1800382f5`
- `KERNEL32!lstrcmpiW` at `0x180038258`
- `KERNEL32!lstrcmpiW` at `0x180038258`
- `KERNEL32!lstrlenW` at `0x18003827d`
- `KERNEL32!lstrlenW` at `0x180038288`
- `KERNEL32!lstrlenW` at `0x18003827d`
- `KERNEL32!lstrlenW` at `0x180038288`
- `USER32!GetSystemMetrics` at `0x18003826c`
- `USER32!GetSystemMetrics` at `0x18003826c`

## pseudocode

```c
__int64 __fastcall AfxComparePath(LPCWCH lpSrcStr, LPCWCH a2)
{
  const WCHAR *v3; // rdi
  int v4; // ebx
  LCID ThreadLocale; // ebx
  int v6; // edx
  WORD lpCharType[264]; // [rsp+30h] [rbp-658h] BYREF
  WORD v9[264]; // [rsp+240h] [rbp-448h] BYREF
  WORD CharType[264]; // [rsp+450h] [rbp-238h] BYREF

  v3 = lpSrcStr;
  if ( !lstrcmpiW(lpSrcStr, a2) )
  {
    if ( !GetSystemMetrics(42) )
      return 1;
    v4 = lstrlenW(v3);
    if ( v4 == lstrlenW(a2) )
    {
      ThreadLocale = GetThreadLocale();
      GetStringTypeExW(ThreadLocale, 1u, v3, -1, CharType);
      GetStringTypeExW(ThreadLocale, 4u, v3, -1, lpCharType);
      GetStringTypeExW(ThreadLocale, 1u, a2, -1, v9);
      v6 = 0;
      while ( *v3 )
      {
        if ( SLOBYTE(lpCharType[v6]) < 0 && CharType[v6] != v9[v6] )
          return 0;
        ++v6;
        ++v3;
      }
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180038230  mov     [rsp+arg_10], rbx
0x180038235  push    rsi
0x180038236  push    rdi
0x180038237  push    r14
0x180038239  sub     rsp, 670h
0x180038240  mov     rax, cs:__security_cookie
0x180038247  xor     rax, rsp
0x18003824a  mov     [rsp+688h+var_28], rax
0x180038252  mov     rsi, rdx
0x180038255  mov     rdi, rcx
0x180038258  call    cs:__imp_lstrcmpiW
0x18003825e  xor     r14d, r14d
0x180038261  test    eax, eax
0x180038263  jnz     loc_18003832F
0x180038269  lea     ecx, [rax+2Ah]; nIndex
0x18003826c  call    cs:__imp_GetSystemMetrics
0x180038272  test    eax, eax
0x180038274  jz      loc_180038328
0x18003827a  mov     rcx, rdi; lpString
0x18003827d  call    cs:__imp_lstrlenW
0x180038283  mov     rcx, rsi; lpString
0x180038286  mov     ebx, eax
0x180038288  call    cs:__imp_lstrlenW
0x18003828e  cmp     ebx, eax
0x180038290  jnz     loc_18003832F
0x180038296  call    cs:__imp_GetThreadLocale
0x18003829c  or      r9d, 0FFFFFFFFh; cchSrc
0x1800382a0  lea     edx, [r14+1]; dwInfoType
0x1800382a4  mov     ebx, eax
0x1800382a6  mov     r8, rdi; lpSrcStr
0x1800382a9  lea     rax, [rsp+688h+CharType]
0x1800382b1  mov     ecx, ebx; Locale
0x1800382b3  mov     [rsp+688h+lpCharType], rax; lpCharType
0x1800382b8  call    cs:__imp_GetStringTypeExW
0x1800382be  lea     rax, [rsp+688h+var_658]
0x1800382c3  or      r9d, 0FFFFFFFFh; cchSrc
0x1800382c7  mov     r8, rdi; lpSrcStr
0x1800382ca  mov     [rsp+688h+lpCharType], rax; lpCharType
0x1800382cf  lea     edx, [r14+4]; dwInfoType
0x1800382d3  mov     ecx, ebx; Locale
0x1800382d5  call    cs:__imp_GetStringTypeExW
0x1800382db  lea     rax, [rsp+688h+var_448]
0x1800382e3  or      r9d, 0FFFFFFFFh; cchSrc
0x1800382e7  mov     r8, rsi; lpSrcStr
0x1800382ea  mov     [rsp+688h+lpCharType], rax; lpCharType
0x1800382ef  lea     edx, [r14+1]; dwInfoType
0x1800382f3  mov     ecx, ebx; Locale
0x1800382f5  call    cs:__imp_GetStringTypeExW
0x1800382fb  mov     edx, r14d
0x1800382fe  cmp     [rdi], r14w
0x180038302  jz      short loc_180038328
0x180038304  movsxd  rcx, edx
0x180038307  test    byte ptr [rsp+rcx*2+688h+var_658], 80h
0x18003830c  jz      short loc_180038320
0x18003830e  movzx   eax, [rsp+rcx*2+688h+var_448]
0x180038316  cmp     [rsp+rcx*2+688h+CharType], ax
0x18003831e  jnz     short loc_18003832F
0x180038320  inc     edx
0x180038322  add     rdi, 2
0x180038326  jmp     short loc_1800382FE
0x180038328  mov     eax, 1
0x18003832d  jmp     short loc_180038331
0x18003832f  xor     eax, eax
0x180038331  mov     rcx, [rsp+688h+var_28]
0x180038339  xor     rcx, rsp; StackCookie
0x18003833c  call    __security_check_cookie
0x180038341  mov     rbx, [rsp+688h+arg_10]
0x180038349  add     rsp, 670h
0x180038350  pop     r14
0x180038352  pop     rdi
0x180038353  pop     rsi
0x180038354  retn
```
