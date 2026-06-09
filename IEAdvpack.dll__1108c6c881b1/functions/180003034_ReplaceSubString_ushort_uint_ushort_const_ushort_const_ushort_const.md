# ReplaceSubString(ushort *,uint,ushort const *,ushort const *,ushort const *)

- ea: `0x180003034`
- end: `0x180003177`
- name: `?ReplaceSubString@@YAHPEAGIPEBG11@Z`
- size: `323`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000279c`

## callees

- `0x180003034`
- `0x180003218`
- `0x1800033a8`

## import_xrefs

- `SHLWAPI!StrStrIW` at `0x18000306f`
- `SHLWAPI!StrStrIW` at `0x180003115`
- `SHLWAPI!StrStrIW` at `0x18000306f`
- `SHLWAPI!StrStrIW` at `0x180003115`

## pseudocode

```c
__int64 __fastcall ReplaceSubString(
        STRSAFE_LPWSTR pszDest,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  wchar_t *v5; // rdi
  size_t v6; // rbx
  unsigned int v7; // r12d
  int v8; // r15d
  const unsigned __int16 *v10; // rsi
  PWSTR v11; // r14
  __int64 v12; // rax
  PWSTR v13; // rax
  unsigned __int64 v15; // [rsp+80h] [rbp+40h] BYREF
  STRSAFE_LPWSTR pszDesta; // [rsp+90h] [rbp+50h] BYREF

  pszDesta = pszDest;
  v5 = pszDest;
  v6 = 260;
  v15 = 260;
  v7 = 0;
  v8 = 0;
  v10 = a3;
  v11 = StrStrIW(a3, a4);
  if ( !v11 )
    goto LABEL_11;
  do
  {
    if ( !v6 )
      break;
    if ( v8 < 0 )
      return v7;
    v8 = StringCchCopyNExW(v5, v6, v10, v11 - v10, &pszDesta, &v15, 0x200u);
    if ( v8 >= 0 )
    {
      v8 = StringCchCopyExW(pszDesta, v15, a5, &pszDesta, &v15, 0x200u);
      v12 = -1;
      do
        ++v12;
      while ( a4[v12] );
      v10 = &v11[v12];
    }
    v7 = 1;
    v13 = StrStrIW(v10, a4);
    v5 = pszDesta;
    v11 = v13;
    v6 = v15;
  }
  while ( v13 );
  if ( v8 >= 0 && v6 )
LABEL_11:
    StringCchCopyExW(v5, v6, v10, &pszDesta, &v15, 0x200u);
  return v7;
}

```

## disassembly

```asm
0x180003034  mov     [rsp-38h+arg_8], rbx
0x180003039  push    rbp
0x18000303a  push    rsi
0x18000303b  push    rdi
0x18000303c  push    r12
0x18000303e  push    r13
0x180003040  push    r14
0x180003042  push    r15
0x180003044  mov     rbp, rsp
0x180003047  sub     rsp, 40h
0x18000304b  xor     eax, eax
0x18000304d  mov     [rbp+pszDest], rcx
0x180003051  mov     rdi, rcx
0x180003054  mov     ebx, 104h
0x180003059  mov     rcx, r8; pszFirst
0x18000305c  mov     [rbp+arg_0], rbx
0x180003060  mov     rdx, r9; pszSrch
0x180003063  mov     r12d, eax
0x180003066  mov     r15d, eax
0x180003069  mov     r13, r9
0x18000306c  mov     rsi, r8
0x18000306f  call    cs:__imp_StrStrIW
0x180003075  mov     r14, rax
0x180003078  test    rax, rax
0x18000307b  jz      loc_180003139
0x180003081  test    rbx, rbx
0x180003084  jz      loc_18000312F
0x18000308a  test    r15d, r15d
0x18000308d  js      loc_18000315C
0x180003093  lea     rax, [rbp+arg_0]
0x180003097  mov     [rsp+40h+var_10], 200h; unsigned int
0x18000309f  mov     [rsp+40h+var_18], rax; unsigned __int64 *
0x1800030a4  mov     r9, r14
0x1800030a7  sub     r9, rsi
0x1800030aa  lea     rax, [rbp+pszDest]
0x1800030ae  sar     r9, 1; unsigned __int64
0x1800030b1  mov     r8, rsi; unsigned __int16 *
0x1800030b4  mov     rdx, rbx; cchDest
0x1800030b7  mov     [rsp+40h+var_20], rax; unsigned __int16 **
0x1800030bc  mov     rcx, rdi; pszDest
0x1800030bf  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800030c4  xor     ebx, ebx
0x1800030c6  mov     r15d, eax
0x1800030c9  test    eax, eax
0x1800030cb  js      short loc_180003109
0x1800030cd  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x1800030d1  lea     rax, [rbp+arg_0]
0x1800030d5  mov     rdx, [rbp+arg_0]; unsigned __int64
0x1800030d9  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x1800030dd  mov     rcx, [rbp+pszDest]; pszDest
0x1800030e1  mov     dword ptr [rsp+40h+var_18], 200h; unsigned int
0x1800030e9  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x1800030ee  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800030f3  mov     r15d, eax
0x1800030f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800030fa  inc     rax
0x1800030fd  cmp     [r13+rax*2+0], bx
0x180003103  jnz     short loc_1800030FA
0x180003105  lea     rsi, [r14+rax*2]
0x180003109  mov     rdx, r13; pszSrch
0x18000310c  mov     rcx, rsi; pszFirst
0x18000310f  mov     r12d, 1
0x180003115  call    cs:__imp_StrStrIW
0x18000311b  mov     rdi, [rbp+pszDest]
0x18000311f  mov     r14, rax
0x180003122  mov     rbx, [rbp+arg_0]
0x180003126  test    rax, rax
0x180003129  jnz     loc_180003081
0x18000312f  test    r15d, r15d
0x180003132  js      short loc_18000315C
0x180003134  test    rbx, rbx
0x180003137  jz      short loc_18000315C
0x180003139  lea     rax, [rbp+arg_0]
0x18000313d  mov     dword ptr [rsp+40h+var_18], 200h; unsigned int
0x180003145  lea     r9, [rbp+pszDest]; unsigned __int16 **
0x180003149  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x18000314e  mov     r8, rsi; unsigned __int16 *
0x180003151  mov     rdx, rbx; unsigned __int64
0x180003154  mov     rcx, rdi; pszDest
0x180003157  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000315c  mov     rbx, [rsp+40h+arg_8]
0x180003164  mov     eax, r12d
0x180003167  add     rsp, 40h
0x18000316b  pop     r15
0x18000316d  pop     r14
0x18000316f  pop     r13
0x180003171  pop     r12
0x180003173  pop     rdi
0x180003174  pop     rsi
0x180003175  pop     rbp
0x180003176  retn
```
