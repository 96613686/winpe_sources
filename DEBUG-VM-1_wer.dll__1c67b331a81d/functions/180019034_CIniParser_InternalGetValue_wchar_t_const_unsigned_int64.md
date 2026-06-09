# CIniParser::InternalGetValue(wchar_t const *,unsigned __int64 *)

- ea: `0x180019034`
- end: `0x180019164`
- name: `?InternalGetValue@CIniParser@@AEAAJPEB_WPEA_K@Z`
- size: `304`
- prototype: `__int64 __fastcall(CIniParser *__hidden this, const wchar_t *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800351c4`
- `0x180035328`

## callees

- `0x180019034`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180019151`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180019151`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800190af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001910f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800190af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001910f`

## pseudocode

```c
__int64 __fastcall CIniParser::InternalGetValue(CIniParser **this, const wchar_t *a2, unsigned __int64 *a3)
{
  __int64 v3; // rbx
  __int64 v5; // r14
  CIniParser *v7; // rsi
  CIniParser **v8; // rbp
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rax
  CIniParser *v13; // r9
  __int64 v14; // r8
  unsigned __int64 v15; // rax
  CIniParser **v17; // rcx

  v3 = -1;
  v5 = (__int64)a2;
  do
    ++v3;
  while ( a2[v3] );
  if ( this[5] == (CIniParser *)(this + 3) )
    goto LABEL_22;
  v7 = this[3];
  v8 = this + 3;
  do
  {
    v9 = *((_QWORD *)v7 + 4);
    if ( (v3 | v9) > 0x7FFFFFFF )
      __int2c();
    v10 = v5;
    v11 = 2;
    if ( !v5 )
      v10 = 2;
    if ( *((_QWORD *)v7 + 3) )
      v11 = *((_QWORD *)v7 + 3);
    if ( CompareStringOrdinal((LPCWCH)v11, v9, (LPCWCH)v10, v3, 1) == 1 )
    {
      v12 = 16;
    }
    else
    {
      v8 = (CIniParser **)v7;
      v12 = 8;
    }
    v7 = *(CIniParser **)((char *)v7 + v12);
  }
  while ( v7 != (CIniParser *)&utl::_TreeSentinel );
  if ( v8 == this + 3 )
    goto LABEL_22;
  v13 = v8[4];
  if ( (v3 | (unsigned __int64)v13) > 0x7FFFFFFF )
    __int2c();
  v14 = 2;
  if ( v8[3] )
    v14 = (__int64)v8[3];
  if ( !v5 )
    v5 = 2;
  if ( CompareStringOrdinal((LPCWCH)v5, v3, (LPCWCH)v14, (int)v13, 1) == 1 || (v17 = (CIniParser **)v8[5], v17 == this) )
LABEL_22:
    v15 = 0;
  else
    v15 = _o__wcstoui64(v17[6], 0, 10);
  *a3 = v15;
  return 0;
}

```

## disassembly

```asm
0x180019034  push    rbx
0x180019036  push    rbp
0x180019037  push    rsi
0x180019038  push    rdi
0x180019039  push    r12
0x18001903b  push    r13
0x18001903d  push    r14
0x18001903f  push    r15
0x180019041  sub     rsp, 38h
0x180019045  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019049  mov     r12, r8
0x18001904c  xor     r13d, r13d
0x18001904f  mov     r14, rdx
0x180019052  mov     r15, rcx
0x180019055  inc     rbx
0x180019058  cmp     [rdx+rbx*2], r13w
0x18001905d  jnz     short loc_180019055
0x18001905f  lea     rdi, [rcx+18h]
0x180019063  cmp     [rdi+10h], rdi
0x180019067  jz      loc_18001911A
0x18001906d  mov     rsi, [rdi]
0x180019070  mov     rbp, rdi
0x180019073  mov     edi, 2
0x180019078  mov     rdx, [rsi+20h]; cchCount1
0x18001907c  mov     rax, rdx
0x18001907f  or      rax, rbx
0x180019082  cmp     rax, 7FFFFFFFh
0x180019088  ja      loc_180019159
0x18001908e  test    r14, r14
0x180019091  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180019099  mov     r8, r14
0x18001909c  mov     rcx, rdi
0x18001909f  cmovz   r8, rdi; lpString2
0x1800190a3  mov     r9d, ebx; cchCount2
0x1800190a6  cmp     [rsi+18h], r13
0x1800190aa  cmovnz  rcx, [rsi+18h]; lpString1
0x1800190af  call    cs:__imp_CompareStringOrdinal
0x1800190b5  cmp     eax, 1
0x1800190b8  jnz     short loc_180019134
0x1800190ba  mov     eax, 10h
0x1800190bf  mov     rsi, [rax+rsi]
0x1800190c3  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800190ca  cmp     rsi, rax
0x1800190cd  jnz     short loc_180019078
0x1800190cf  lea     rdi, [r15+18h]
0x1800190d3  cmp     rbp, rdi
0x1800190d6  jz      short loc_18001911A
0x1800190d8  mov     r9, [rbp+20h]; cchCount2
0x1800190dc  mov     rax, r9
0x1800190df  or      rax, rbx
0x1800190e2  cmp     rax, 7FFFFFFFh
0x1800190e8  ja      short loc_180019160
0x1800190ea  cmp     [rbp+18h], r13
0x1800190ee  mov     eax, 2
0x1800190f3  mov     r8d, eax
0x1800190f6  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800190fe  cmovnz  r8, [rbp+18h]; lpString2
0x180019103  mov     edx, ebx; cchCount1
0x180019105  test    r14, r14
0x180019108  cmovz   r14, rax
0x18001910c  mov     rcx, r14; lpString1
0x18001910f  call    cs:__imp_CompareStringOrdinal
0x180019115  cmp     eax, 1
0x180019118  jnz     short loc_18001913E
0x18001911a  mov     rax, r13
0x18001911d  mov     [r12], rax
0x180019121  xor     eax, eax
0x180019123  add     rsp, 38h
0x180019127  pop     r15
0x180019129  pop     r14
0x18001912b  pop     r13
0x18001912d  pop     r12
0x18001912f  pop     rdi
0x180019130  pop     rsi
0x180019131  pop     rbp
0x180019132  pop     rbx
0x180019133  retn
0x180019134  mov     rbp, rsi
0x180019137  mov     eax, 8
0x18001913c  jmp     short loc_1800190BF
0x18001913e  mov     rcx, [rbp+28h]
0x180019142  cmp     rcx, r15
0x180019145  jz      short loc_18001911A
0x180019147  mov     rcx, [rcx+30h]
0x18001914b  xor     edx, edx
0x18001914d  lea     r8d, [rdx+0Ah]
0x180019151  call    cs:__imp__o__wcstoui64
0x180019157  jmp     short loc_18001911D
0x180019159  int     2Ch; Windows NT - assertion failure
0x18001915b  jmp     loc_18001908E
0x180019160  int     2Ch; Windows NT - assertion failure
0x180019162  jmp     short loc_1800190EA
```
