# AslPathClean

- ea: `0x180015258`
- end: `0x180015497`
- name: `AslPathClean`
- size: `575`
- prototype: `__int64 __fastcall(wchar_t *String1, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800136f4`

## callees

- `0x180015258`
- `0x18001622e`
- `0x180016252`

## import_xrefs

- `msvcrt!wcschr` at `0x180015299`
- `msvcrt!wcschr` at `0x1800152eb`
- `msvcrt!wcschr` at `0x180015299`
- `msvcrt!wcschr` at `0x1800152eb`

## pseudocode

```c
__int64 __fastcall AslPathClean(wchar_t *String1, void *a2)
{
  unsigned __int64 v2; // rsi
  wchar_t *v6; // rbx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  wchar_t v11; // ax
  unsigned __int64 v12; // rax
  wchar_t v13; // ax
  __int16 v14; // cx
  __int16 v15; // cx
  unsigned __int64 v16; // rax
  wchar_t v17; // ax

  v2 = -1;
  do
    ++v2;
  while ( String1[v2] );
  if ( v2 + 1 > 0x104 )
    return 3221225507LL;
  v6 = wcschr(String1, 0x3Au);
  if ( v6 )
    goto LABEL_10;
  v7 = 4;
  if ( !wcsncmp_0(String1, L"\\??\\", 4u) )
    goto LABEL_12;
  if ( !wcsncmp_0(String1, L"\\\\", 2u) )
  {
    v7 = 2;
    goto LABEL_12;
  }
  v6 = wcschr(String1, 0x5Cu);
  if ( v6 )
LABEL_10:
    v7 = ((unsigned __int64)((char *)v6 - (char *)String1) >> 1) + 1;
  else
    v7 = 1;
LABEL_12:
  memmove_0(a2, String1, 2 * v7);
  v8 = v7;
  v9 = v7;
  if ( v7 < v2 )
  {
    while ( 1 )
    {
      if ( String1[v9] == 92 || String1[v9] == 47 )
      {
        if ( !v8 || *((_WORD *)a2 + v8 - 1) != 92 )
          *((_WORD *)a2 + v8++) = 92;
        goto LABEL_54;
      }
      if ( String1[v9] != 46 )
        break;
      v10 = v9 + 1;
      if ( v9 + 1 == v2 )
        goto LABEL_55;
      v11 = String1[v9 + 1];
      if ( v11 == 92 || v11 == 47 )
      {
        ++v9;
        goto LABEL_54;
      }
      if ( v11 == 46 )
      {
        v12 = v9 + 2;
        if ( v9 + 2 == v2 || String1[v12] == 92 || String1[v12] == 47 )
        {
          while ( v8 >= v7 )
          {
            v14 = *((_WORD *)a2 + v8);
            *((_WORD *)a2 + v8) = 0;
            if ( v14 == 92 )
            {
              do
              {
                v15 = *((_WORD *)a2 + v8);
                *((_WORD *)a2 + v8) = 0;
                if ( v15 == 92 )
                  break;
                --v8;
              }
              while ( v8 >= v7 );
              break;
            }
            --v8;
          }
          v16 = v8 + 1;
          v9 = v10;
          if ( v8 >= v7 )
            v16 = v8;
          v8 = v16;
          goto LABEL_54;
        }
      }
      if ( String1[v9 + 2] != 92 && String1[v9 + 2] != 47 )
      {
        while ( v9 < v2 )
        {
          v17 = String1[v9];
          if ( v17 == 92 || v17 == 47 )
            goto LABEL_31;
          *((_WORD *)a2 + v8++) = v17;
          ++v9;
        }
LABEL_35:
        --v9;
      }
LABEL_54:
      if ( ++v9 >= v2 )
        goto LABEL_55;
    }
    while ( v9 < v2 )
    {
      v13 = String1[v9];
      if ( v13 == 92 || v13 == 47 )
      {
LABEL_31:
        if ( v8 >= 2 && *((_WORD *)a2 + v8 - 1) == 46 && *((_WORD *)a2 + v8 - 2) != 46 )
          --v8;
        goto LABEL_35;
      }
      *((_WORD *)a2 + v8++) = v13;
      ++v9;
    }
    goto LABEL_35;
  }
LABEL_55:
  *((_WORD *)a2 + v8) = 0;
  return 0;
}

```

## disassembly

```asm
0x180015258  push    rbx
0x18001525a  push    rbp
0x18001525b  push    rsi
0x18001525c  push    rdi
0x18001525d  push    r12
0x18001525f  push    r14
0x180015261  push    r15
0x180015263  sub     rsp, 20h
0x180015267  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001526b  mov     r14, rdx
0x18001526e  xor     r15d, r15d
0x180015271  mov     rdi, rcx
0x180015274  inc     rsi
0x180015277  cmp     [rcx+rsi*2], r15w
0x18001527c  jnz     short loc_180015274
0x18001527e  lea     rax, [rsi+1]
0x180015282  cmp     rax, 104h
0x180015288  jbe     short loc_180015294
0x18001528a  mov     eax, 0C0000023h
0x18001528f  jmp     loc_180015488
0x180015294  mov     edx, 3Ah ; ':'; Ch
0x180015299  call    cs:__imp_wcschr
0x18001529f  mov     ebp, 1
0x1800152a4  mov     rbx, rax
0x1800152a7  lea     r12d, [rbp+5Bh]
0x1800152ab  test    rax, rax
0x1800152ae  jnz     short loc_1800152F9
0x1800152b0  lea     ebx, [rax+4]
0x1800152b3  mov     rcx, rdi; String1
0x1800152b6  mov     r8d, ebx; MaxCount
0x1800152b9  lea     rdx, asc_18001C530; "\\??\\"
0x1800152c0  call    wcsncmp_0
0x1800152c5  test    eax, eax
0x1800152c7  jz      short loc_180015307
0x1800152c9  lea     r8d, [rbp+1]; MaxCount
0x1800152cd  mov     rcx, rdi; String1
0x1800152d0  lea     rdx, asc_180019BC8; "\\\\"
0x1800152d7  call    wcsncmp_0
0x1800152dc  test    eax, eax
0x1800152de  jnz     short loc_1800152E5
0x1800152e0  lea     ebx, [rbp+1]
0x1800152e3  jmp     short loc_180015307
0x1800152e5  mov     edx, r12d; Ch
0x1800152e8  mov     rcx, rdi; Str
0x1800152eb  call    cs:__imp_wcschr
0x1800152f1  mov     rbx, rax
0x1800152f4  test    rax, rax
0x1800152f7  jz      short loc_180015304
0x1800152f9  sub     rbx, rdi
0x1800152fc  shr     rbx, 1
0x1800152ff  add     rbx, rbp
0x180015302  jmp     short loc_180015307
0x180015304  mov     rbx, rbp
0x180015307  lea     r8, [rbx+rbx]; Size
0x18001530b  mov     rdx, rdi; Src
0x18001530e  mov     rcx, r14; void *
0x180015311  call    memmove_0
0x180015316  mov     rdx, rbx
0x180015319  mov     rcx, rbx
0x18001531c  cmp     rbx, rsi
0x18001531f  jnb     loc_180015480
0x180015325  mov     r10w, 2Fh ; '/'
0x18001532a  mov     r9w, 2Eh ; '.'
0x18001532f  cmp     [rdi+rcx*2], r12w
0x180015334  jz      loc_18001545F
0x18001533a  cmp     [rdi+rcx*2], r10w
0x18001533f  jz      loc_18001545F
0x180015345  cmp     [rdi+rcx*2], r9w
0x18001534a  jnz     short loc_1800153CB
0x18001534c  lea     r8, [rcx+1]
0x180015350  cmp     r8, rsi
0x180015353  jz      loc_180015480
0x180015359  movzx   eax, word ptr [rdi+rcx*2+2]
0x18001535e  cmp     ax, r12w
0x180015362  jz      loc_18001545A
0x180015368  cmp     ax, r10w
0x18001536c  jz      loc_18001545A
0x180015372  cmp     ax, r9w
0x180015376  jnz     short loc_180015393
0x180015378  lea     rax, [rcx+2]
0x18001537c  cmp     rax, rsi
0x18001537f  jz      loc_180015406
0x180015385  cmp     [rdi+rax*2], r12w
0x18001538a  jz      short loc_180015406
0x18001538c  cmp     [rdi+rax*2], r10w
0x180015391  jz      short loc_180015406
0x180015393  cmp     [rdi+rcx*2+4], r12w
0x180015399  jz      loc_180015474
0x18001539f  cmp     [rdi+rcx*2+4], r10w
0x1800153a5  jz      loc_180015474
0x1800153ab  jmp     loc_180015453
0x1800153b0  movzx   eax, word ptr [rdi+rcx*2]
0x1800153b4  cmp     ax, r12w
0x1800153b8  jz      short loc_1800153D2
0x1800153ba  cmp     ax, r10w
0x1800153be  jz      short loc_1800153D2
0x1800153c0  mov     [r14+rdx*2], ax
0x1800153c5  add     rdx, rbp
0x1800153c8  add     rcx, rbp
0x1800153cb  cmp     rcx, rsi
0x1800153ce  jb      short loc_1800153B0
0x1800153d0  jmp     short loc_1800153EB
0x1800153d2  cmp     rdx, 2
0x1800153d6  jb      short loc_1800153EB
0x1800153d8  cmp     [r14+rdx*2-2], r9w
0x1800153de  jnz     short loc_1800153EB
0x1800153e0  cmp     [r14+rdx*2-4], r9w
0x1800153e6  jz      short loc_1800153EB
0x1800153e8  sub     rdx, rbp
0x1800153eb  sub     rcx, rbp
0x1800153ee  jmp     loc_180015474
0x1800153f3  movzx   ecx, word ptr [r14+rdx*2]
0x1800153f8  mov     [r14+rdx*2], r15w
0x1800153fd  cmp     cx, r12w
0x180015401  jz      short loc_18001540D
0x180015403  sub     rdx, rbp
0x180015406  cmp     rdx, rbx
0x180015409  jnb     short loc_1800153F3
0x18001540b  jmp     short loc_180015425
0x18001540d  movzx   ecx, word ptr [r14+rdx*2]
0x180015412  mov     [r14+rdx*2], r15w
0x180015417  cmp     cx, r12w
0x18001541b  jz      short loc_180015425
0x18001541d  sub     rdx, rbp
0x180015420  cmp     rdx, rbx
0x180015423  jnb     short loc_18001540D
0x180015425  cmp     rdx, rbx
0x180015428  lea     rax, [rdx+1]
0x18001542c  mov     rcx, r8
0x18001542f  cmovnb  rax, rdx
0x180015433  mov     rdx, rax
0x180015436  jmp     short loc_180015474
0x180015438  movzx   eax, word ptr [rdi+rcx*2]
0x18001543c  cmp     ax, r12w
0x180015440  jz      short loc_1800153D2
0x180015442  cmp     ax, r10w
0x180015446  jz      short loc_1800153D2
0x180015448  mov     [r14+rdx*2], ax
0x18001544d  add     rdx, rbp
0x180015450  add     rcx, rbp
0x180015453  cmp     rcx, rsi
0x180015456  jb      short loc_180015438
0x180015458  jmp     short loc_1800153EB
0x18001545a  mov     rcx, r8
0x18001545d  jmp     short loc_180015474
0x18001545f  test    rdx, rdx
0x180015462  jz      short loc_18001546C
0x180015464  cmp     [r14+rdx*2-2], r12w
0x18001546a  jz      short loc_180015474
0x18001546c  mov     [r14+rdx*2], r12w
0x180015471  add     rdx, rbp
0x180015474  add     rcx, rbp
0x180015477  cmp     rcx, rsi
0x18001547a  jb      loc_18001532F
0x180015480  mov     [r14+rdx*2], r15w
0x180015485  mov     eax, r15d
0x180015488  add     rsp, 20h
0x18001548c  pop     r15
0x18001548e  pop     r14
0x180015490  pop     r12
0x180015492  pop     rdi
0x180015493  pop     rsi
0x180015494  pop     rbp
0x180015495  pop     rbx
0x180015496  retn
```
