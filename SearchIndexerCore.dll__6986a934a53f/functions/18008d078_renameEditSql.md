# renameEditSql

- ea: `0x18008d078`
- end: `0x18008d394`
- name: `renameEditSql`
- size: `796`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x1800774f0`
- `0x18008ca10`
- `0x18008d8d0`

## callees

- `0x18001eb90`
- `0x18003d310`
- `0x18003d380`
- `0x180040e00`
- `0x180041d10`
- `0x180041eb0`
- `0x18004ae40`
- `0x180070500`
- `0x18008d078`
- `0x18009d7b0`
- `0x1800af620`
- `0x1800af62c`

## pseudocode

```c
__int64 __fastcall renameEditSql(__int64 a1, __int64 *a2, const void *a3, const void *a4, int a5)
{
  const void *v6; // r14
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  const void *v10; // rsi
  __int64 v12; // r13
  char *v13; // rbx
  void *v14; // rbp
  void *v15; // r12
  __int64 v16; // rax
  unsigned int v17; // r15d
  _QWORD *v18; // rdx
  __int64 v19; // rdi
  int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  unsigned __int8 *v24; // rcx
  unsigned int v25; // ebp
  const void *v26; // rdx
  _DWORD *v27; // r14
  const char *v28; // rdx
  unsigned int v29; // eax
  int v30; // r12d
  int v31; // [rsp+30h] [rbp-78h]
  int v32; // [rsp+34h] [rbp-74h]
  unsigned int Size; // [rsp+38h] [rbp-70h]
  void *v34; // [rsp+40h] [rbp-68h]
  void *v35; // [rsp+48h] [rbp-60h]
  void *v36; // [rsp+50h] [rbp-58h]
  __int64 v37; // [rsp+58h] [rbp-50h]

  v6 = a4;
  Size = sqlite3Strlen30(a4);
  v32 = sqlite3Strlen30(v7);
  v37 = sqlite3_context_db_handle(v8);
  if ( v6 )
  {
    v9 = sqlite3MPrintf(v37, "\"%w\" ", v6);
    v10 = (const void *)v9;
    if ( !v9 )
      return 7;
    v12 = (int)(sqlite3Strlen30(v9) - 1);
    v13 = (char *)sqlite3DbMallocZero(v37, v32 + v12 * *((int *)a2 + 2) + 1);
    if ( v13 )
    {
      v14 = 0;
      v15 = 0;
LABEL_8:
      v17 = 0;
      v36 = v15;
      v35 = v14;
      memcpy_0(v13, a3, v32);
      v18 = a2;
      v19 = *a2;
      if ( *a2 )
      {
        v20 = v32;
        v31 = v32;
        do
        {
          v21 = *(_QWORD *)(v19 + 24);
          if ( v21 )
          {
            do
            {
              if ( *(_QWORD *)(v21 + 8) > *(_QWORD *)(v19 + 8) )
                v19 = v21;
              v21 = *(_QWORD *)(v21 + 24);
            }
            while ( v21 );
            v35 = v14;
            v36 = v15;
          }
          v22 = *v18;
          if ( *v18 == v19 )
          {
            v23 = v18;
          }
          else
          {
            do
            {
              v23 = (_QWORD *)(v22 + 24);
              v22 = *(_QWORD *)(v22 + 24);
            }
            while ( v22 != v19 );
          }
          *v23 = *(_QWORD *)(v19 + 24);
          if ( v6 )
          {
            v24 = *(unsigned __int8 **)(v19 + 8);
            if ( a5 || (*((_BYTE *)&qword_1800B4FF0 + *v24) & 0x46) == 0 )
            {
              v27 = (_DWORD *)(v19 + 16);
              v26 = v10;
              v25 = v12;
              v34 = (void *)v10;
              if ( v24[*(unsigned int *)(v19 + 16)] == 34 )
                v25 = v12 + 1;
            }
            else
            {
              v25 = Size;
              v26 = v6;
              v34 = (void *)v6;
              v27 = (_DWORD *)(v19 + 16);
            }
          }
          else
          {
            v27 = (_DWORD *)(v19 + 16);
            memcpy_0(v14, *(const void **)(v19 + 8), *(unsigned int *)(v19 + 16));
            *((_BYTE *)v14 + *(unsigned int *)(v19 + 16)) = 0;
            sqlite3Dequote(v14);
            v28 = " ";
            if ( *(_BYTE *)(*(unsigned int *)(v19 + 16) + *(_QWORD *)(v19 + 8)) != 39 )
              v28 = (const char *)&Src;
            sqlite3_snprintf((unsigned int)(2 * v32), v15, "%Q%s", v14, v28);
            v34 = v15;
            v29 = sqlite3Strlen30(v15);
            v20 = v31;
            v25 = v29;
          }
          v30 = *(_DWORD *)(v19 + 8) - (_DWORD)a3;
          if ( *v27 != v25 )
          {
            memmove_0(&v13[v30 + v25], &v13[v30 + *v27], (unsigned int)(v20 - v30 - *v27));
            v26 = v34;
            v31 += v25 - *v27;
            v13[v31] = 0;
          }
          memcpy_0(&v13[v30], v26, v25);
          sqlite3DbFree(v37, v19);
          v18 = a2;
          v14 = v35;
          v15 = v36;
          v6 = a4;
          v19 = *a2;
          v20 = v31;
        }
        while ( *a2 );
        v17 = 0;
      }
      sqlite3_result_text(a1, v13, -1, -1);
      sqlite3DbFree(v37, v13);
      goto LABEL_34;
    }
  }
  else
  {
    v10 = 0;
    v16 = sqlite3DbMallocZero(v37, 6LL * v32 + 3);
    v13 = (char *)v16;
    if ( v16 )
    {
      LODWORD(v12) = 0;
      v14 = (void *)(v16 + 2LL * v32 + 1);
      v15 = (void *)(v16 + 4LL * v32 + 2);
      goto LABEL_8;
    }
  }
  v17 = 7;
LABEL_34:
  sqlite3_free(v10);
  return v17;
}

```

## disassembly

```asm
0x18008d078  mov     rax, rsp
0x18008d07b  mov     [rax+20h], r9
0x18008d07f  mov     [rax+18h], r8
0x18008d083  mov     [rax+10h], rdx
0x18008d087  mov     [rax+8], rcx
0x18008d08b  push    rbx
0x18008d08c  push    rbp
0x18008d08d  push    rsi
0x18008d08e  push    rdi
0x18008d08f  push    r12
0x18008d091  push    r13
0x18008d093  push    r14
0x18008d095  push    r15
0x18008d097  sub     rsp, 68h
0x18008d09b  mov     r15, rdx
0x18008d09e  mov     r14, r9
0x18008d0a1  mov     rdx, rcx
0x18008d0a4  mov     rcx, r9
0x18008d0a7  call    sqlite3Strlen30
0x18008d0ac  mov     rcx, r8
0x18008d0af  mov     dword ptr [rsp+0A8h+Size], eax
0x18008d0b3  call    sqlite3Strlen30
0x18008d0b8  mov     rcx, rdx
0x18008d0bb  mov     [rsp+0A8h+var_74], eax
0x18008d0bf  movsxd  rdi, eax
0x18008d0c2  call    sqlite3_context_db_handle
0x18008d0c7  mov     [rsp+0A8h+var_50], rax
0x18008d0cc  mov     rbx, rax
0x18008d0cf  mov     rcx, rax
0x18008d0d2  test    r14, r14
0x18008d0d5  jz      short loc_18008D12C
0x18008d0d7  mov     r8, r14
0x18008d0da  lea     rdx, aW; "\"%w\" "
0x18008d0e1  call    sqlite3MPrintf
0x18008d0e6  mov     rsi, rax
0x18008d0e9  test    rax, rax
0x18008d0ec  jnz     short loc_18008D0F6
0x18008d0ee  lea     eax, [rsi+7]
0x18008d0f1  jmp     loc_18008D383
0x18008d0f6  mov     rcx, rax
0x18008d0f9  call    sqlite3Strlen30
0x18008d0fe  movsxd  rdx, dword ptr [r15+8]
0x18008d102  dec     eax
0x18008d104  movsxd  r13, eax
0x18008d107  mov     rcx, rbx
0x18008d10a  imul    rdx, r13
0x18008d10e  inc     rdx
0x18008d111  add     rdx, rdi
0x18008d114  call    sqlite3DbMallocZero
0x18008d119  mov     rbx, rax
0x18008d11c  test    rax, rax
0x18008d11f  jz      loc_18008D372
0x18008d125  xor     ebp, ebp
0x18008d127  xor     r12d, r12d
0x18008d12a  jmp     short loc_18008D164
0x18008d12c  lea     rdx, [rdi+rdi*2]
0x18008d130  xor     esi, esi
0x18008d132  lea     rdx, ds:3[rdx*2]
0x18008d13a  call    sqlite3DbMallocZero
0x18008d13f  mov     rbx, rax
0x18008d142  test    rax, rax
0x18008d145  jz      loc_18008D372
0x18008d14b  lea     rbp, ds:1[rdi*2]
0x18008d153  xor     r13d, r13d
0x18008d156  add     rbp, rax
0x18008d159  lea     r12, ds:2[rdi*4]
0x18008d161  add     r12, rax
0x18008d164  mov     rdx, [rsp+0A8h+Src]; Src
0x18008d16c  xor     r15d, r15d
0x18008d16f  mov     r8, rdi; Size
0x18008d172  mov     dword ptr [rsp+0A8h+Size+4], r15d
0x18008d177  mov     rcx, rbx; void *
0x18008d17a  mov     [rsp+0A8h+var_58], r12
0x18008d17f  mov     [rsp+0A8h+var_60], rbp
0x18008d184  call    memcpy_0
0x18008d189  mov     rdx, [rsp+0A8h+arg_8]
0x18008d191  mov     rdi, [rdx]
0x18008d194  test    rdi, rdi
0x18008d197  jz      loc_18008D34C
0x18008d19d  mov     r8d, [rsp+0A8h+var_74]
0x18008d1a2  mov     r15, [rsp+0A8h+var_50]
0x18008d1a7  mov     [rsp+0A8h+var_78], r8d
0x18008d1ac  mov     rcx, [rdi+18h]
0x18008d1b0  test    rcx, rcx
0x18008d1b3  jz      short loc_18008D1D4
0x18008d1b5  mov     rax, [rdi+8]
0x18008d1b9  cmp     [rcx+8], rax
0x18008d1bd  cmova   rdi, rcx
0x18008d1c1  mov     rcx, [rcx+18h]
0x18008d1c5  test    rcx, rcx
0x18008d1c8  jnz     short loc_18008D1B5
0x18008d1ca  mov     [rsp+0A8h+var_60], rbp
0x18008d1cf  mov     [rsp+0A8h+var_58], r12
0x18008d1d4  mov     rax, [rdx]
0x18008d1d7  cmp     rax, rdi
0x18008d1da  jz      short loc_18008D1EA
0x18008d1dc  lea     rcx, [rax+18h]
0x18008d1e0  mov     rax, [rcx]
0x18008d1e3  cmp     rax, rdi
0x18008d1e6  jnz     short loc_18008D1DC
0x18008d1e8  jmp     short loc_18008D1ED
0x18008d1ea  mov     rcx, rdx
0x18008d1ed  mov     rax, [rdi+18h]
0x18008d1f1  mov     [rcx], rax
0x18008d1f4  test    r14, r14
0x18008d1f7  jz      short loc_18008D248
0x18008d1f9  cmp     [rsp+0A8h+arg_20], 0
0x18008d201  mov     rcx, [rdi+8]
0x18008d205  jnz     short loc_18008D22C
0x18008d207  movzx   eax, byte ptr [rcx]
0x18008d20a  lea     rdx, qword_1800B4FF0
0x18008d211  test    byte ptr [rax+rdx], 46h
0x18008d215  jz      short loc_18008D22C
0x18008d217  mov     ebp, dword ptr [rsp+0A8h+Size]
0x18008d21b  mov     rdx, r14
0x18008d21e  mov     [rsp+0A8h+var_68], rdx
0x18008d223  lea     r14, [rdi+10h]
0x18008d227  jmp     loc_18008D2BC
0x18008d22c  lea     r14, [rdi+10h]
0x18008d230  mov     rdx, rsi
0x18008d233  mov     eax, [r14]
0x18008d236  mov     ebp, r13d
0x18008d239  mov     [rsp+0A8h+var_68], rdx
0x18008d23e  cmp     byte ptr [rax+rcx], 22h ; '"'
0x18008d242  jnz     short loc_18008D2BC
0x18008d244  inc     ebp
0x18008d246  jmp     short loc_18008D2BC
0x18008d248  mov     rdx, [rdi+8]; Src
0x18008d24c  lea     r14, [rdi+10h]
0x18008d250  mov     r8d, [r14]; Size
0x18008d253  mov     rcx, rbp; void *
0x18008d256  call    memcpy_0
0x18008d25b  mov     eax, [r14]
0x18008d25e  mov     rcx, rbp
0x18008d261  mov     byte ptr [rax+rbp], 0
0x18008d265  call    sqlite3Dequote
0x18008d26a  mov     ecx, [r14]
0x18008d26d  lea     r8, Src
0x18008d274  mov     rax, [rdi+8]
0x18008d278  lea     rdx, asc_1800BA114; " "
0x18008d27f  mov     r9, rbp
0x18008d282  cmp     byte ptr [rcx+rax], 27h ; '''
0x18008d286  mov     eax, [rsp+0A8h+var_74]
0x18008d28a  cmovnz  rdx, r8
0x18008d28e  lea     r8, aQS; "%Q%s"
0x18008d295  mov     [rsp+0A8h+var_88], rdx
0x18008d29a  mov     rdx, r12
0x18008d29d  lea     ecx, [rax+rax]
0x18008d2a0  call    sqlite3_snprintf
0x18008d2a5  mov     rdx, r12
0x18008d2a8  mov     rcx, r12
0x18008d2ab  mov     [rsp+0A8h+var_68], rdx
0x18008d2b0  call    sqlite3Strlen30
0x18008d2b5  mov     r8d, [rsp+0A8h+var_78]
0x18008d2ba  mov     ebp, eax
0x18008d2bc  mov     r12d, [rdi+8]
0x18008d2c0  sub     r12d, dword ptr [rsp+0A8h+Src]
0x18008d2c8  mov     eax, [r14]
0x18008d2cb  cmp     eax, ebp
0x18008d2cd  jz      short loc_18008D303
0x18008d2cf  sub     r8d, r12d
0x18008d2d2  lea     edx, [r12+rax]
0x18008d2d6  lea     ecx, [r12+rbp]
0x18008d2da  sub     r8d, eax; Size
0x18008d2dd  add     rdx, rbx; Src
0x18008d2e0  add     rcx, rbx; void *
0x18008d2e3  call    memmove_0
0x18008d2e8  mov     ecx, [rsp+0A8h+var_78]
0x18008d2ec  mov     eax, ebp
0x18008d2ee  sub     eax, [r14]
0x18008d2f1  mov     rdx, [rsp+0A8h+var_68]; Src
0x18008d2f6  add     ecx, eax
0x18008d2f8  movsxd  rax, ecx
0x18008d2fb  mov     [rsp+0A8h+var_78], ecx
0x18008d2ff  mov     byte ptr [rax+rbx], 0
0x18008d303  movsxd  rcx, r12d
0x18008d306  add     rcx, rbx; void *
0x18008d309  mov     r8d, ebp; Size
0x18008d30c  call    memcpy_0
0x18008d311  mov     rdx, rdi
0x18008d314  mov     rcx, r15
0x18008d317  call    sqlite3DbFree
0x18008d31c  mov     rdx, [rsp+0A8h+arg_8]
0x18008d324  mov     rbp, [rsp+0A8h+var_60]
0x18008d329  mov     r12, [rsp+0A8h+var_58]
0x18008d32e  mov     r14, [rsp+0A8h+arg_18]
0x18008d336  mov     rdi, [rdx]
0x18008d339  mov     r8d, [rsp+0A8h+var_78]
0x18008d33e  test    rdi, rdi
0x18008d341  jnz     loc_18008D1AC
0x18008d347  mov     r15d, dword ptr [rsp+0A8h+Size+4]
0x18008d34c  mov     rcx, [rsp+0A8h+arg_0]
0x18008d354  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008d358  mov     r9, r8
0x18008d35b  mov     rdx, rbx
0x18008d35e  call    sqlite3_result_text
0x18008d363  mov     rcx, [rsp+0A8h+var_50]
0x18008d368  mov     rdx, rbx
0x18008d36b  call    sqlite3DbFree
0x18008d370  jmp     short loc_18008D378
0x18008d372  mov     r15d, 7
0x18008d378  mov     rcx, rsi
0x18008d37b  call    sqlite3_free
0x18008d380  mov     eax, r15d
0x18008d383  add     rsp, 68h
0x18008d387  pop     r15
0x18008d389  pop     r14
0x18008d38b  pop     r13
0x18008d38d  pop     r12
0x18008d38f  pop     rdi
0x18008d390  pop     rsi
0x18008d391  pop     rbp
0x18008d392  pop     rbx
0x18008d393  retn
```
