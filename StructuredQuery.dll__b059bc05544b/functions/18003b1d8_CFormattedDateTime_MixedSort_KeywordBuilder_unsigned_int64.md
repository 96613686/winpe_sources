# CFormattedDateTime::MixedSort(KeywordBuilder *,unsigned __int64)

- ea: `0x18003b1d8`
- end: `0x18003b757`
- name: `?MixedSort@CFormattedDateTime@@AEAAXPEAVKeywordBuilder@@_K@Z`
- size: `1407`
- prototype: `void __fastcall(CFormattedDateTime *__hidden this, struct KeywordBuilder *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d250`
- `0x18003b1d8`

## callees

- `0x18003b1d8`
- `0x18003b760`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003b36a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003b4df`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003b566`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003b36a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003b4df`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18003b566`

## pseudocode

```c
void __fastcall CFormattedDateTime::MixedSort(CFormattedDateTime *this, struct KeywordBuilder *a2, unsigned __int64 a3)
{
  unsigned __int64 i; // r13
  const wchar_t *v6; // r15
  struct KeywordBuilder *v7; // rdi
  const wchar_t *v8; // r14
  const wchar_t *v9; // rsi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // rsi
  __int64 lpString2; // rbp
  __int64 v18; // r8
  unsigned __int64 cchCount2; // rax
  unsigned __int64 v20; // r9
  _QWORD *v21; // r9
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rcx
  const wchar_t *v25; // r8
  const wchar_t *v26; // rdx
  struct KeywordBuilder *v27; // r9
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int64 v31; // rsi
  __int64 v32; // rdx
  unsigned __int64 v33; // r9
  __int64 v34; // r8
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rbp
  __int64 v37; // r8
  unsigned __int64 v38; // r9
  __int64 v39; // rdx
  unsigned __int64 v40; // rax
  struct KeywordBuilder *v41; // rdi
  struct KeywordBuilder *v42; // r9
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned __int64 v49; // [rsp+50h] [rbp-48h]
  unsigned __int64 v51; // [rsp+B0h] [rbp+18h]
  unsigned __int64 v52; // [rsp+B0h] [rbp+18h]
  _QWORD *v53; // [rsp+B8h] [rbp+20h]
  unsigned __int64 v54; // [rsp+B8h] [rbp+20h]

  v51 = a3;
  for ( i = a3; i >= 2; v51 = i )
  {
    if ( i < 0xA )
    {
      v13 = 0;
      v52 = 0;
      while ( 2 )
      {
        while ( 1 )
        {
          v14 = v13 + 1;
          v15 = v13;
          v49 = v13 + 1;
          v16 = v13 + 1;
          v53 = (_QWORD *)((char *)a2 + 56 * v13);
          lpString2 = v53[2];
          if ( v13 + 1 < i )
            break;
LABEL_10:
          v52 = v14;
          v13 = v14;
          if ( v14 >= i )
            return;
        }
LABEL_12:
        v18 = *((_QWORD *)a2 + 7 * v16 + 2);
        cchCount2 = -1;
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(v18 + 2 * v20) );
        do
          ++cchCount2;
        while ( *(_WORD *)(lpString2 + 2 * cchCount2) );
        if ( *((_DWORD *)this + 45) == 1028
          && v20 >= 2
          && cchCount2 >= 2
          && *(_WORD *)(v18 + 2) == 21320
          && *(_WORD *)(lpString2 + 2) == 21320 )
        {
          if ( *(_WORD *)v18 == 19978 )
          {
            if ( *(_WORD *)lpString2 != 19979 )
              break;
LABEL_17:
            v15 = v16;
            lpString2 = *((_QWORD *)a2 + 7 * v16 + 2);
LABEL_18:
            if ( ++v16 >= i )
            {
              v14 = v13 + 1;
              if ( v15 == v52 )
                goto LABEL_10;
              v21 = (_QWORD *)((char *)a2 + 56 * v15);
              if ( v21 == v53 )
                goto LABEL_10;
              ++v13;
              v22 = v21[2];
              v23 = v21[3];
              v24 = v21[4];
              v21[2] = v53[2];
              v21[3] = v53[3];
              v21[4] = v53[4];
              v53[2] = v22;
              v53[3] = v23;
              v53[4] = v24;
              v52 = v49;
              continue;
            }
            goto LABEL_12;
          }
          if ( *(_WORD *)v18 == 19979 && *(_WORD *)lpString2 == 19978 )
            goto LABEL_18;
        }
        break;
      }
      if ( CompareStringEx(
             (LPCWSTR)this + 4,
             *((_DWORD *)this + 47),
             (LPCWCH)v18,
             v20,
             (LPCWCH)lpString2,
             cchCount2,
             0,
             0,
             0) == 1 )
        goto LABEL_17;
      goto LABEL_18;
    }
    v6 = (const wchar_t *)*((_QWORD *)a2 + 2);
    v7 = (struct KeywordBuilder *)((char *)a2 + 56 * (i >> 1));
    v8 = (const wchar_t *)*((_QWORD *)v7 + 2);
    v9 = (const wchar_t *)*((_QWORD *)a2 + 7 * i - 5);
    if ( CFormattedDateTime::CompareKeywords(this, v6, v8) == 1 )
    {
      if ( CFormattedDateTime::CompareKeywords(this, v8, v9) == 1 )
        goto LABEL_6;
      v25 = v9;
      v26 = v6;
    }
    else
    {
      if ( CFormattedDateTime::CompareKeywords(this, v9, v8) == 1 )
      {
LABEL_6:
        if ( a2 != v7 )
        {
          v10 = *((_QWORD *)a2 + 2);
          v11 = *((_QWORD *)a2 + 3);
          v12 = *((_QWORD *)a2 + 4);
          *((_QWORD *)a2 + 2) = *((_QWORD *)v7 + 2);
          *((_QWORD *)a2 + 3) = *((_QWORD *)v7 + 3);
          *((_QWORD *)a2 + 4) = *((_QWORD *)v7 + 4);
          *((_QWORD *)v7 + 2) = v10;
          *((_QWORD *)v7 + 3) = v11;
          *((_QWORD *)v7 + 4) = v12;
        }
        goto LABEL_27;
      }
      v25 = v6;
      v26 = v9;
    }
    if ( CFormattedDateTime::CompareKeywords(this, v26, v25) == 1 )
    {
      v27 = (struct KeywordBuilder *)((char *)a2 + 56 * i - 56);
      if ( a2 != v27 )
      {
        v28 = *((_QWORD *)a2 + 2);
        *((_QWORD *)a2 + 2) = *((_QWORD *)v27 + 2);
        v29 = *((_QWORD *)a2 + 3);
        *((_QWORD *)a2 + 3) = *((_QWORD *)v27 + 3);
        v30 = *((_QWORD *)a2 + 4);
        *((_QWORD *)a2 + 4) = *((_QWORD *)v27 + 4);
        *((_QWORD *)v27 + 4) = v30;
        *((_QWORD *)v27 + 3) = v29;
        *((_QWORD *)v27 + 2) = v28;
      }
    }
LABEL_27:
    v54 = i;
    v31 = 0;
    while ( 2 )
    {
      while ( ++v31 < i )
      {
        _mm_lfence();
        v32 = *((_QWORD *)a2 + 2);
        v33 = -1;
        v34 = *((_QWORD *)a2 + 7 * v31 + 2);
        do
          ++v33;
        while ( *(_WORD *)(v34 + 2 * v33) );
        v35 = -1;
        do
          ++v35;
        while ( *(_WORD *)(v32 + 2 * v35) );
        if ( *((_DWORD *)this + 45) != 1028
          || v33 < 2
          || v35 < 2
          || *(_WORD *)(v34 + 2) != 21320
          || *(_WORD *)(v32 + 2) != 21320 )
        {
          goto LABEL_34;
        }
        if ( *(_WORD *)v34 == 19978 )
        {
          if ( *(_WORD *)v32 != 19979 )
            goto LABEL_34;
        }
        else
        {
          if ( *(_WORD *)v34 == 19979 && *(_WORD *)v32 == 19978 )
            break;
LABEL_34:
          if ( CompareStringEx((LPCWSTR)this + 4, *((_DWORD *)this + 47), (LPCWCH)v34, v33, (LPCWCH)v32, v35, 0, 0, 0) != 1 )
            break;
        }
      }
      v36 = v54;
      while ( 1 )
      {
        v37 = *((_QWORD *)a2 + 2);
        --v36;
        v38 = -1;
        v39 = *((_QWORD *)a2 + 7 * v36 + 2);
        do
          ++v38;
        while ( *(_WORD *)(v37 + 2 * v38) );
        v40 = -1;
        do
          ++v40;
        while ( *(_WORD *)(v39 + 2 * v40) );
        if ( *((_DWORD *)this + 45) != 1028
          || v38 < 2
          || v40 < 2
          || *(_WORD *)(v37 + 2) != 21320
          || *(_WORD *)(v39 + 2) != 21320 )
        {
          goto LABEL_41;
        }
        if ( *(_WORD *)v37 != 19978 )
          break;
        if ( *(_WORD *)v39 == 19979 )
          continue;
LABEL_41:
        if ( CompareStringEx((LPCWSTR)this + 4, *((_DWORD *)this + 47), (LPCWCH)v37, v38, (LPCWCH)v39, v40, 0, 0, 0) != 1 )
          goto LABEL_42;
      }
      if ( *(_WORD *)v37 != 19979 || *(_WORD *)v39 != 19978 )
        goto LABEL_41;
LABEL_42:
      i = v51;
      v54 = v36;
      v41 = (struct KeywordBuilder *)((char *)a2 + 56 * v36);
      if ( v31 < v36 )
      {
        v42 = (struct KeywordBuilder *)((char *)a2 + 56 * v31);
        if ( v42 != v41 )
        {
          v43 = *((_QWORD *)v42 + 2);
          v44 = *((_QWORD *)v42 + 3);
          v45 = *((_QWORD *)v42 + 4);
          *((_QWORD *)v42 + 2) = *((_QWORD *)v41 + 2);
          *((_QWORD *)v42 + 3) = *((_QWORD *)v41 + 3);
          *((_QWORD *)v42 + 4) = *((_QWORD *)v41 + 4);
          *((_QWORD *)v41 + 2) = v43;
          *((_QWORD *)v41 + 3) = v44;
          *((_QWORD *)v41 + 4) = v45;
        }
        continue;
      }
      break;
    }
    if ( a2 != v41 )
    {
      v46 = *((_QWORD *)a2 + 2);
      v47 = *((_QWORD *)a2 + 3);
      v48 = *((_QWORD *)a2 + 4);
      *((_QWORD *)a2 + 2) = *((_QWORD *)v41 + 2);
      *((_QWORD *)a2 + 3) = *((_QWORD *)v41 + 3);
      *((_QWORD *)a2 + 4) = *((_QWORD *)v41 + 4);
      *((_QWORD *)v41 + 2) = v46;
      *((_QWORD *)v41 + 3) = v47;
      *((_QWORD *)v41 + 4) = v48;
    }
    CFormattedDateTime::MixedSort(this, a2, v36);
    a2 = (struct KeywordBuilder *)((char *)v41 + 56);
    i = -1LL - v36 + v51;
  }
}

```

## disassembly

```asm
0x18003b1d8  mov     [rsp+arg_8], rbx
0x18003b1dd  mov     [rsp+arg_10], r8
0x18003b1e2  mov     [rsp+arg_0], rcx
0x18003b1e7  push    rbp
0x18003b1e8  push    rsi
0x18003b1e9  push    rdi
0x18003b1ea  push    r12
0x18003b1ec  push    r13
0x18003b1ee  push    r14
0x18003b1f0  push    r15
0x18003b1f2  sub     rsp, 60h
0x18003b1f6  mov     r13, r8
0x18003b1f9  mov     rbx, rdx
0x18003b1fc  mov     r12, rcx
0x18003b1ff  xor     r14d, r14d
0x18003b202  cmp     r13, 2
0x18003b206  jb      loc_18003B2E2
0x18003b20c  cmp     r13, 0Ah
0x18003b210  jb      loc_18003B2A0
0x18003b216  mov     r15, [rbx+10h]
0x18003b21a  mov     rax, r13
0x18003b21d  shr     rax, 1
0x18003b220  mov     rdx, r15; wchar_t *
0x18003b223  imul    rdi, rax, 38h ; '8'
0x18003b227  imul    rbp, r13, 38h ; '8'
0x18003b22b  add     rdi, rbx
0x18003b22e  mov     rcx, r12; this
0x18003b231  mov     r14, [rdi+10h]
0x18003b235  mov     r8, r14; wchar_t *
0x18003b238  mov     rsi, [rbx+rbp-28h]
0x18003b23d  call    ?CompareKeywords@CFormattedDateTime@@AEAAHPEB_W0@Z; CFormattedDateTime::CompareKeywords(wchar_t const *,wchar_t const *)
0x18003b242  mov     rcx, r12; this
0x18003b245  cmp     eax, 1
0x18003b248  jnz     loc_18003B3F4
0x18003b24e  mov     r8, rsi; wchar_t *
0x18003b251  mov     rdx, r14; wchar_t *
0x18003b254  call    ?CompareKeywords@CFormattedDateTime@@AEAAHPEB_W0@Z; CFormattedDateTime::CompareKeywords(wchar_t const *,wchar_t const *)
0x18003b259  cmp     eax, 1
0x18003b25c  jnz     loc_18003B5DB
0x18003b262  cmp     rbx, rdi
0x18003b265  jz      loc_18003B457
0x18003b26b  mov     rax, [rdi+10h]
0x18003b26f  mov     r8, [rbx+10h]
0x18003b273  mov     rdx, [rbx+18h]
0x18003b277  mov     rcx, [rbx+20h]
0x18003b27b  mov     [rbx+10h], rax
0x18003b27f  mov     rax, [rdi+18h]
0x18003b283  mov     [rbx+18h], rax
0x18003b287  mov     rax, [rdi+20h]
0x18003b28b  mov     [rbx+20h], rax
0x18003b28f  mov     [rdi+10h], r8
0x18003b293  mov     [rdi+18h], rdx
0x18003b297  mov     [rdi+20h], rcx
0x18003b29b  jmp     loc_18003B457
0x18003b2a0  mov     rdi, r14
0x18003b2a3  mov     [rsp+98h+arg_10], r14
0x18003b2ab  lea     r12, [rdi+1]
0x18003b2af  mov     r15, rdi
0x18003b2b2  imul    r14, rdi, 38h ; '8'
0x18003b2b6  mov     [rsp+98h+var_48], r12
0x18003b2bb  mov     rsi, r12
0x18003b2be  add     r14, rbx
0x18003b2c1  mov     [rsp+98h+arg_18], r14
0x18003b2c9  mov     rbp, [r14+10h]
0x18003b2cd  cmp     r12, r13
0x18003b2d0  jb      short loc_18003B2FA
0x18003b2d2  mov     [rsp+98h+arg_10], r12
0x18003b2da  mov     rdi, r12
0x18003b2dd  cmp     r12, r13
0x18003b2e0  jb      short loc_18003B2AB
0x18003b2e2  mov     rbx, [rsp+98h+arg_8]
0x18003b2ea  add     rsp, 60h
0x18003b2ee  pop     r15
0x18003b2f0  pop     r14
0x18003b2f2  pop     r13
0x18003b2f4  pop     r12
0x18003b2f6  pop     rdi
0x18003b2f7  pop     rsi
0x18003b2f8  pop     rbp
0x18003b2f9  retn
0x18003b2fa  mov     r12, [rsp+98h+arg_0]
0x18003b302  mov     edi, 4E0Bh
0x18003b307  mov     r14d, 5348h
0x18003b30d  imul    rax, rsi, 38h ; '8'
0x18003b311  mov     r8, [rax+rbx+10h]; lpString1
0x18003b316  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b31a  mov     r9, rax
0x18003b31d  xor     edx, edx
0x18003b31f  inc     r9; cchCount1
0x18003b322  cmp     [r8+r9*2], dx
0x18003b327  jnz     short loc_18003B31F
0x18003b329  inc     rax
0x18003b32c  cmp     [rbp+rax*2+0], dx
0x18003b331  jnz     short loc_18003B329
0x18003b333  cmp     dword ptr [r12+0B4h], 404h
0x18003b33f  jz      loc_18003B5E6
0x18003b345  mov     [rsp+98h+lParam], rdx; lParam
0x18003b34a  lea     rcx, [r12+8]; lpLocaleName
0x18003b34f  mov     [rsp+98h+lpReserved], rdx; lpReserved
0x18003b354  mov     [rsp+98h+lpVersionInformation], rdx; lpVersionInformation
0x18003b359  mov     edx, [r12+0BCh]; dwCmpFlags
0x18003b361  mov     [rsp+98h+cchCount2], eax; cchCount2
0x18003b365  mov     [rsp+98h+lpString2], rbp; lpString2
0x18003b36a  call    cs:__imp_CompareStringEx
0x18003b370  cmp     eax, 1
0x18003b373  jnz     short loc_18003B381
0x18003b375  imul    rax, rsi, 38h ; '8'
0x18003b379  mov     r15, rsi
0x18003b37c  mov     rbp, [rax+rbx+10h]
0x18003b381  inc     rsi
0x18003b384  cmp     rsi, r13
0x18003b387  jb      short loc_18003B30D
0x18003b389  mov     r14, [rsp+98h+arg_18]
0x18003b391  mov     r12, [rsp+98h+var_48]
0x18003b396  cmp     r15, [rsp+98h+arg_10]
0x18003b39e  jz      loc_18003B2D2
0x18003b3a4  imul    r9, r15, 38h ; '8'
0x18003b3a8  add     r9, rbx
0x18003b3ab  cmp     r9, r14
0x18003b3ae  jz      loc_18003B2D2
0x18003b3b4  mov     rax, [r14+10h]
0x18003b3b8  mov     rdi, r12
0x18003b3bb  mov     r8, [r9+10h]
0x18003b3bf  mov     rdx, [r9+18h]
0x18003b3c3  mov     rcx, [r9+20h]
0x18003b3c7  mov     [r9+10h], rax
0x18003b3cb  mov     rax, [r14+18h]
0x18003b3cf  mov     [r9+18h], rax
0x18003b3d3  mov     rax, [r14+20h]
0x18003b3d7  mov     [r9+20h], rax
0x18003b3db  mov     [r14+10h], r8
0x18003b3df  mov     [r14+18h], rdx
0x18003b3e3  mov     [r14+20h], rcx
0x18003b3e7  mov     [rsp+98h+arg_10], r12
0x18003b3ef  jmp     loc_18003B2AB
0x18003b3f4  mov     r8, r14; wchar_t *
0x18003b3f7  mov     rdx, rsi; wchar_t *
0x18003b3fa  call    ?CompareKeywords@CFormattedDateTime@@AEAAHPEB_W0@Z; CFormattedDateTime::CompareKeywords(wchar_t const *,wchar_t const *)
0x18003b3ff  cmp     eax, 1
0x18003b402  jz      loc_18003B262
0x18003b408  mov     r8, r15; wchar_t *
0x18003b40b  mov     rdx, rsi; wchar_t *
0x18003b40e  mov     rcx, r12; this
0x18003b411  call    ?CompareKeywords@CFormattedDateTime@@AEAAHPEB_W0@Z; CFormattedDateTime::CompareKeywords(wchar_t const *,wchar_t const *)
0x18003b416  cmp     eax, 1
0x18003b419  jnz     short loc_18003B457
0x18003b41b  lea     r9, [rbp-38h]
0x18003b41f  add     r9, rbx
0x18003b422  cmp     rbx, r9
0x18003b425  jz      short loc_18003B457
0x18003b427  mov     rax, [r9+10h]
0x18003b42b  mov     r8, [rbx+10h]
0x18003b42f  mov     [rbx+10h], rax
0x18003b433  mov     rax, [r9+18h]
0x18003b437  mov     rdx, [rbx+18h]
0x18003b43b  mov     [rbx+18h], rax
0x18003b43f  mov     rax, [r9+20h]
0x18003b443  mov     rcx, [rbx+20h]
0x18003b447  mov     [rbx+20h], rax
0x18003b44b  mov     [r9+20h], rcx
0x18003b44f  mov     [r9+18h], rdx
0x18003b453  mov     [r9+10h], r8
0x18003b457  xor     r14d, r14d
0x18003b45a  mov     [rsp+98h+arg_18], r13
0x18003b462  mov     esi, r14d
0x18003b465  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003b469  mov     ebp, 4E0Bh
0x18003b46e  mov     edi, 5348h
0x18003b473  lea     ecx, [rbp-1]
0x18003b476  inc     rsi
0x18003b479  cmp     rsi, r13
0x18003b47c  jnb     short loc_18003B4EF
0x18003b47e  lfence
0x18003b481  mov     rdx, [rbx+10h]
0x18003b485  mov     r9, r15
0x18003b488  imul    rax, rsi, 38h ; '8'
0x18003b48c  mov     r8, [rax+rbx+10h]; lpString1
0x18003b491  inc     r9; cchCount1
0x18003b494  cmp     [r8+r9*2], r14w
0x18003b499  jnz     short loc_18003B491
0x18003b49b  mov     rax, r15
0x18003b49e  inc     rax
0x18003b4a1  cmp     [rdx+rax*2], r14w
0x18003b4a6  jnz     short loc_18003B49E
0x18003b4a8  cmp     dword ptr [r12+0B4h], 404h
0x18003b4b4  jz      loc_18003B670
0x18003b4ba  mov     [rsp+98h+lParam], r14; lParam
0x18003b4bf  lea     rcx, [r12+8]; lpLocaleName
0x18003b4c4  mov     [rsp+98h+lpReserved], r14; lpReserved
0x18003b4c9  mov     [rsp+98h+lpVersionInformation], r14; lpVersionInformation
0x18003b4ce  mov     [rsp+98h+cchCount2], eax; cchCount2
0x18003b4d2  mov     [rsp+98h+lpString2], rdx; lpString2
0x18003b4d7  mov     edx, [r12+0BCh]; dwCmpFlags
0x18003b4df  call    cs:__imp_CompareStringEx
0x18003b4e5  mov     ecx, 4E0Ah
0x18003b4ea  cmp     eax, 1
0x18003b4ed  jz      short loc_18003B476
0x18003b4ef  mov     rbp, [rsp+98h+arg_18]
0x18003b4f7  mov     [rsp+98h+var_48], rsi
0x18003b4fc  mov     esi, 4E0Ah
0x18003b501  lea     r13d, [rsi+1]
0x18003b505  mov     r8, [rbx+10h]; lpString1
0x18003b509  dec     rbp
0x18003b50c  imul    rax, rbp, 38h ; '8'
0x18003b510  mov     r9, r15
0x18003b513  mov     rdx, [rax+rbx+10h]
0x18003b518  inc     r9; cchCount1
0x18003b51b  cmp     [r8+r9*2], r14w
0x18003b520  jnz     short loc_18003B518
0x18003b522  mov     rax, r15
0x18003b525  inc     rax
0x18003b528  cmp     [rdx+rax*2], r14w
0x18003b52d  jnz     short loc_18003B525
0x18003b52f  cmp     dword ptr [r12+0B4h], 404h
0x18003b53b  jz      loc_18003B62E
0x18003b541  mov     [rsp+98h+lParam], r14; lParam
0x18003b546  lea     rcx, [r12+8]; lpLocaleName
0x18003b54b  mov     [rsp+98h+lpReserved], r14; lpReserved
0x18003b550  mov     [rsp+98h+lpVersionInformation], r14; lpVersionInformation
0x18003b555  mov     [rsp+98h+cchCount2], eax; cchCount2
0x18003b559  mov     [rsp+98h+lpString2], rdx; lpString2
0x18003b55e  mov     edx, [r12+0BCh]; dwCmpFlags
0x18003b566  call    cs:__imp_CompareStringEx
0x18003b56c  cmp     eax, 1
0x18003b56f  jz      short loc_18003B505
0x18003b571  mov     rsi, [rsp+98h+var_48]
0x18003b576  mov     r13, [rsp+98h+arg_10]
0x18003b57e  imul    rdi, rbp, 38h ; '8'
0x18003b582  mov     [rsp+98h+arg_18], rbp
0x18003b58a  add     rdi, rbx
0x18003b58d  cmp     rsi, rbp
0x18003b590  jnb     loc_18003B6B1
0x18003b596  imul    r9, rsi, 38h ; '8'
0x18003b59a  add     r9, rbx
0x18003b59d  cmp     r9, rdi
0x18003b5a0  jz      loc_18003B469
0x18003b5a6  mov     rax, [rdi+10h]
0x18003b5aa  mov     r8, [r9+10h]
0x18003b5ae  mov     rdx, [r9+18h]
0x18003b5b2  mov     rcx, [r9+20h]
0x18003b5b6  mov     [r9+10h], rax
0x18003b5ba  mov     rax, [rdi+18h]
0x18003b5be  mov     [r9+18h], rax
0x18003b5c2  mov     rax, [rdi+20h]
0x18003b5c6  mov     [r9+20h], rax
0x18003b5ca  mov     [rdi+10h], r8
0x18003b5ce  mov     [rdi+18h], rdx
0x18003b5d2  mov     [rdi+20h], rcx
0x18003b5d6  jmp     loc_18003B469
0x18003b5db  mov     r8, rsi
0x18003b5de  mov     rdx, r15
0x18003b5e1  jmp     loc_18003B40E
0x18003b5e6  cmp     r9, 2
0x18003b5ea  jb      loc_18003B345
0x18003b5f0  cmp     rax, 2
0x18003b5f4  jb      loc_18003B345
0x18003b5fa  cmp     [r8+2], r14w
0x18003b5ff  jnz     loc_18003B345
0x18003b605  cmp     [rbp+2], r14w
0x18003b60a  jnz     loc_18003B345
0x18003b610  mov     ecx, 4E0Ah
0x18003b615  cmp     [r8], cx
0x18003b619  jnz     loc_18003B70E
0x18003b61f  cmp     [rbp+0], di
0x18003b623  jz      loc_18003B375
0x18003b629  jmp     loc_18003B345
0x18003b62e  cmp     r9, 2
0x18003b632  jb      loc_18003B541
0x18003b638  cmp     rax, 2
0x18003b63c  jb      loc_18003B541
0x18003b642  cmp     [r8+2], di
0x18003b647  jnz     loc_18003B541
0x18003b64d  cmp     [rdx+2], di
0x18003b651  jnz     loc_18003B541
0x18003b657  cmp     [r8], si
0x18003b65b  jnz     loc_18003B727
0x18003b661  cmp     [rdx], r13w
0x18003b665  jz      loc_18003B505
0x18003b66b  jmp     loc_18003B541
0x18003b670  cmp     r9, 2
0x18003b674  jb      loc_18003B4BA
0x18003b67a  cmp     rax, 2
0x18003b67e  jb      loc_18003B4BA
0x18003b684  cmp     [r8+2], di
0x18003b689  jnz     loc_18003B4BA
0x18003b68f  cmp     [rdx+2], di
0x18003b693  jnz     loc_18003B4BA
0x18003b699  cmp     [r8], cx
0x18003b69d  jnz     loc_18003B73F
0x18003b6a3  cmp     [rdx], bp
0x18003b6a6  jz      loc_18003B476
0x18003b6ac  jmp     loc_18003B4BA
0x18003b6b1  cmp     rbx, rdi
0x18003b6b4  jz      short loc_18003B6E6
0x18003b6b6  mov     rax, [rdi+10h]
0x18003b6ba  mov     r8, [rbx+10h]
0x18003b6be  mov     rdx, [rbx+18h]
0x18003b6c2  mov     rcx, [rbx+20h]
0x18003b6c6  mov     [rbx+10h], rax
0x18003b6ca  mov     rax, [rdi+18h]
  ... truncated ...
```
