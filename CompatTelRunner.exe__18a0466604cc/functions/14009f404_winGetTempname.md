# winGetTempname

- ea: `0x14009f404`
- end: `0x14009f748`
- name: `winGetTempname`
- size: `836`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14009ed20`
- `0x14009ff30`

## callees

- `0x140062d60`
- `0x14008ac90`
- `0x14008bf00`
- `0x14008ccd0`
- `0x14009f404`
- `0x14009fa4c`
- `0x1400a1220`
- `0x1400a8010`

## string_xrefs

- `0x14009f50d`: `winGetTempname2`
- `0x14009f5bd`: `winGetTempname1`
- `0x14009f71b`: `winGetTempname4`
- `0x14009f667`: `winGetTempname5`

## pseudocode

```c
__int64 __fastcall winGetTempname(__int64 a1, __int64 *a2)
{
  __int64 v2; // rbp
  int v4; // r15d
  __int64 v5; // rbx
  __int64 result; // rax
  char v7; // cl
  int v8; // r13d
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rsi
  DWORD v13; // edx
  const char *v14; // rax
  const char *v15; // r14
  __int64 v16; // rdx
  unsigned int v17; // edx
  __int64 v18; // rax
  const char *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // ecx
  char v23; // al
  __int64 v24; // rcx
  unsigned int v25; // ecx
  __int64 v26; // rdi
  __int64 v27; // rsi
  DWORD v28; // r9d
  unsigned __int8 v29; // cl
  int v30; // [rsp+20h] [rbp-58h]

  v2 = *(int *)(a1 + 8);
  v4 = v2 + 2;
  v5 = sqlite3MallocZero((int)v2 + 2);
  if ( !v5 )
    return 3082;
  v7 = word_1400C84B4;
  v8 = v2 - 22;
  if ( (_BYTE)word_1400C84B4 )
  {
    v9 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(11);
    if ( v9 )
      ((void (__fastcall *)(__int64))xmmword_1400C8530)(v9);
    v7 = word_1400C84B4;
  }
  v10 = -1;
  if ( sqlite3_temp_directory )
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_BYTE *)(sqlite3_temp_directory + v16) );
    v17 = v16 & 0x3FFFFFFF;
    if ( v17 )
    {
      if ( *(_BYTE *)(v17 + sqlite3_temp_directory - 1) != 47 && *(_BYTE *)(v17 + sqlite3_temp_directory - 1) != 92 )
        ++v17;
      if ( (int)v17 > v8 )
      {
        if ( v7 )
        {
          v18 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(11);
          if ( v18 )
            ((void (__fastcall *)(__int64))xmmword_1400C8540)(v18);
        }
        sqlite3_free(v5);
        v19 = "winGetTempname1";
        v30 = 50580;
        return winLogErrorAtLine(1, 0, (_DWORD)v19, 0, v30);
      }
      sqlite3_snprintf((unsigned int)v2, v5, "%s", (const char *)sqlite3_temp_directory);
      v7 = word_1400C84B4;
    }
    if ( v7 )
    {
      v20 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(11);
      if ( v20 )
        ((void (__fastcall *)(__int64))xmmword_1400C8540)(v20);
    }
  }
  else
  {
    if ( v7 )
    {
      v11 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(11);
      if ( v11 )
        ((void (__fastcall *)(__int64))xmmword_1400C8540)(v11);
    }
    v12 = sqlite3MallocZero(2 * v2);
    if ( !v12 )
      goto LABEL_12;
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, __int64))off_1400C5CF8)((unsigned int)v2, v12) )
    {
      sqlite3_free(v12);
      sqlite3_free(v5);
      v13 = off_1400C5C68();
      return winLogErrorAtLine(6410, v13, (unsigned int)"winGetTempname2", 0, 50681);
    }
    v14 = (const char *)winUnicodeToUtf8(v12);
    v15 = v14;
    if ( !v14 )
    {
      sqlite3_free(v12);
LABEL_12:
      sqlite3_free(v5);
      return 3082;
    }
    sqlite3_snprintf((unsigned int)v2, v5, "%s", v14);
    sqlite3_free(v15);
    sqlite3_free(v12);
  }
  v21 = -1;
  do
    ++v21;
  while ( *(_BYTE *)(v5 + v21) );
  v22 = v21 & 0x3FFFFFFF;
  if ( !v22 )
    goto LABEL_49;
  v23 = *(_BYTE *)(v22 + v5 - 1);
  if ( v23 != 47 && v23 != 92 )
  {
    if ( (int)(v22 + 1) < v8 + 1 )
    {
      *(_WORD *)(v22 + v5) = 92;
      goto LABEL_40;
    }
LABEL_49:
    sqlite3_free(v5);
    v19 = "winGetTempname4";
    v30 = 50731;
    return winLogErrorAtLine(1, 0, (_DWORD)v19, 0, v30);
  }
LABEL_40:
  v24 = -1;
  do
    ++v24;
  while ( *(_BYTE *)(v5 + v24) );
  v25 = v24 & 0x3FFFFFFF;
  if ( (int)(v25 + 24) > v4 )
  {
    sqlite3_free(v5);
    v19 = "winGetTempname5";
    v30 = 50749;
    return winLogErrorAtLine(1, 0, (_DWORD)v19, 0, v30);
  }
  sqlite3_snprintf(v4 - v25 - 16, v5 + v25, "etilqs_");
  do
    ++v10;
  while ( *(_BYTE *)(v5 + v10) );
  v26 = v10 & 0x3FFFFFFF;
  v27 = 15;
  sqlite3_randomness(15, v5 + v26);
  v28 = off_1400C5B90();
  do
  {
    v29 = *(_BYTE *)(v5 + v26) + v28;
    v28 >>= 8;
    *(_BYTE *)(v5 + v26++) = aAbcdefghijklmn[v29 % 0x3EuLL];
    --v27;
  }
  while ( v27 );
  *(_WORD *)(v5 + v26) = 0;
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x14009f404  push    rbx
0x14009f406  push    rbp
0x14009f407  push    rsi
0x14009f408  push    rdi
0x14009f409  push    r12
0x14009f40b  push    r13
0x14009f40d  push    r14
0x14009f40f  push    r15
0x14009f411  sub     rsp, 38h
0x14009f415  movsxd  rbp, dword ptr [rcx+8]
0x14009f419  mov     r12, rdx
0x14009f41c  lea     r15d, [rbp+2]
0x14009f420  movsxd  rcx, r15d; Size
0x14009f423  call    sqlite3MallocZero
0x14009f428  xor     r14d, r14d
0x14009f42b  mov     rbx, rax
0x14009f42e  test    rax, rax
0x14009f431  jnz     short loc_14009F43D
0x14009f433  mov     eax, 0C0Ah
0x14009f438  jmp     loc_14009F737
0x14009f43d  mov     cl, byte ptr cs:word_1400C84B4
0x14009f443  lea     r13d, [rbp-16h]
0x14009f447  mov     esi, 0Bh
0x14009f44c  test    cl, cl
0x14009f44e  jz      short loc_14009F478
0x14009f450  mov     rax, qword ptr cs:xmmword_1400C8520
0x14009f457  mov     ecx, esi
0x14009f459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f45e  test    rax, rax
0x14009f461  jz      short loc_14009F472
0x14009f463  mov     rcx, rax
0x14009f466  mov     rax, qword ptr cs:xmmword_1400C8530
0x14009f46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f472  mov     cl, byte ptr cs:word_1400C84B4
0x14009f478  mov     r9, cs:sqlite3_temp_directory
0x14009f47f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14009f483  test    r9, r9
0x14009f486  jnz     loc_14009F564
0x14009f48c  test    cl, cl
0x14009f48e  jz      short loc_14009F4B2
0x14009f490  mov     rax, qword ptr cs:xmmword_1400C8520
0x14009f497  mov     ecx, esi
0x14009f499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f49e  test    rax, rax
0x14009f4a1  jz      short loc_14009F4B2
0x14009f4a3  mov     rcx, rax
0x14009f4a6  mov     rax, qword ptr cs:xmmword_1400C8540
0x14009f4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f4b2  mov     rcx, rbp
0x14009f4b5  add     rcx, rcx; Size
0x14009f4b8  call    sqlite3MallocZero
0x14009f4bd  mov     rsi, rax
0x14009f4c0  test    rax, rax
0x14009f4c3  jnz     short loc_14009F4D2
0x14009f4c5  mov     rcx, rbx
0x14009f4c8  call    sqlite3_free
0x14009f4cd  jmp     loc_14009F433
0x14009f4d2  mov     rax, cs:off_1400C5CF8
0x14009f4d9  mov     rdx, rsi
0x14009f4dc  mov     ecx, ebp
0x14009f4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f4e3  mov     rcx, rsi
0x14009f4e6  test    eax, eax
0x14009f4e8  jnz     short loc_14009F51E
0x14009f4ea  call    sqlite3_free
0x14009f4ef  mov     rcx, rbx
0x14009f4f2  call    sqlite3_free
0x14009f4f7  mov     rax, cs:off_1400C5C68
0x14009f4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f503  mov     edx, eax
0x14009f505  mov     [rsp+78h+var_58], 0C5F9h
0x14009f50d  lea     r8, aWingettempname_2; "winGetTempname2"
0x14009f514  mov     ecx, 190Ah
0x14009f519  jmp     loc_14009F72F
0x14009f51e  call    winUnicodeToUtf8
0x14009f523  mov     r14, rax
0x14009f526  test    rax, rax
0x14009f529  jz      short loc_14009F557
0x14009f52b  mov     r9, rax
0x14009f52e  lea     r8, aS_6; "%s"
0x14009f535  mov     rdx, rbx
0x14009f538  mov     ecx, ebp
0x14009f53a  call    sqlite3_snprintf
0x14009f53f  mov     rcx, r14
0x14009f542  call    sqlite3_free
0x14009f547  mov     rcx, rsi
0x14009f54a  call    sqlite3_free
0x14009f54f  xor     r14d, r14d
0x14009f552  jmp     loc_14009F60E
0x14009f557  mov     rcx, rsi
0x14009f55a  call    sqlite3_free
0x14009f55f  jmp     loc_14009F4C5
0x14009f564  mov     rdx, rdi
0x14009f567  inc     rdx
0x14009f56a  cmp     [r9+rdx], r14b
0x14009f56e  jnz     short loc_14009F567
0x14009f570  and     edx, 3FFFFFFFh
0x14009f576  jbe     short loc_14009F5E8
0x14009f578  cmp     byte ptr [rdx+r9-1], 2Fh ; '/'
0x14009f57e  jz      short loc_14009F58A
0x14009f580  cmp     byte ptr [rdx+r9-1], 5Ch ; '\'
0x14009f586  jz      short loc_14009F58A
0x14009f588  inc     edx
0x14009f58a  cmp     edx, r13d
0x14009f58d  jle     short loc_14009F5D1
0x14009f58f  test    cl, cl
0x14009f591  jz      short loc_14009F5B5
0x14009f593  mov     rax, qword ptr cs:xmmword_1400C8520
0x14009f59a  mov     ecx, esi
0x14009f59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f5a1  test    rax, rax
0x14009f5a4  jz      short loc_14009F5B5
0x14009f5a6  mov     rcx, rax
0x14009f5a9  mov     rax, qword ptr cs:xmmword_1400C8540
0x14009f5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f5b5  mov     rcx, rbx
0x14009f5b8  call    sqlite3_free
0x14009f5bd  lea     r8, aWingettempname; "winGetTempname1"
0x14009f5c4  mov     [rsp+78h+var_58], 0C594h
0x14009f5cc  jmp     loc_14009F72A
0x14009f5d1  lea     r8, aS_6; "%s"
0x14009f5d8  mov     rdx, rbx
0x14009f5db  mov     ecx, ebp
0x14009f5dd  call    sqlite3_snprintf
0x14009f5e2  mov     cl, byte ptr cs:word_1400C84B4
0x14009f5e8  test    cl, cl
0x14009f5ea  jz      short loc_14009F60E
0x14009f5ec  mov     rax, qword ptr cs:xmmword_1400C8520
0x14009f5f3  mov     ecx, esi
0x14009f5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f5fa  test    rax, rax
0x14009f5fd  jz      short loc_14009F60E
0x14009f5ff  mov     rcx, rax
0x14009f602  mov     rax, qword ptr cs:xmmword_1400C8540
0x14009f609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f60e  mov     rcx, rdi
0x14009f611  inc     rcx
0x14009f614  cmp     [rbx+rcx], r14b
0x14009f618  jnz     short loc_14009F611
0x14009f61a  mov     esi, 3FFFFFFFh
0x14009f61f  and     ecx, esi
0x14009f621  jbe     loc_14009F713
0x14009f627  mov     al, [rcx+rbx-1]
0x14009f62b  mov     edx, ecx
0x14009f62d  cmp     al, 2Fh ; '/'
0x14009f62f  jz      short loc_14009F649
0x14009f631  cmp     al, 5Ch ; '\'
0x14009f633  jz      short loc_14009F649
0x14009f635  inc     ecx
0x14009f637  lea     eax, [r13+1]
0x14009f63b  cmp     ecx, eax
0x14009f63d  jge     loc_14009F713
0x14009f643  mov     word ptr [rdx+rbx], 5Ch ; '\'
0x14009f649  mov     rcx, rdi
0x14009f64c  inc     rcx
0x14009f64f  cmp     [rbx+rcx], r14b
0x14009f653  jnz     short loc_14009F64C
0x14009f655  and     ecx, esi
0x14009f657  lea     eax, [rcx+18h]
0x14009f65a  cmp     eax, r15d
0x14009f65d  jle     short loc_14009F67B
0x14009f65f  mov     rcx, rbx
0x14009f662  call    sqlite3_free
0x14009f667  lea     r8, aWingettempname_1; "winGetTempname5"
0x14009f66e  mov     [rsp+78h+var_58], 0C63Dh
0x14009f676  jmp     loc_14009F72A
0x14009f67b  mov     edx, ecx
0x14009f67d  lea     r8, aEtilqs; "etilqs_"
0x14009f684  sub     r15d, ecx
0x14009f687  add     rdx, rbx
0x14009f68a  lea     ecx, [r15-10h]
0x14009f68e  call    sqlite3_snprintf
0x14009f693  inc     rdi
0x14009f696  cmp     [rbx+rdi], r14b
0x14009f69a  jnz     short loc_14009F693
0x14009f69c  and     rdi, rsi
0x14009f69f  mov     esi, 0Fh
0x14009f6a4  mov     ecx, esi
0x14009f6a6  lea     rdx, [rbx+rdi]
0x14009f6aa  call    sqlite3_randomness
0x14009f6af  mov     rax, cs:off_1400C5B90
0x14009f6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009f6bb  mov     r9d, eax
0x14009f6be  mov     cl, r9b
0x14009f6c1  mov     rax, 842108421084211h
0x14009f6cb  add     cl, [rbx+rdi]
0x14009f6ce  movzx   r8d, cl
0x14009f6d2  mul     r8
0x14009f6d5  mov     eax, r8d
0x14009f6d8  shr     r9d, 8
0x14009f6dc  sub     rax, rdx
0x14009f6df  shr     rax, 1
0x14009f6e2  add     rax, rdx
0x14009f6e5  shr     rax, 5
0x14009f6e9  imul    rax, 3Eh ; '>'
0x14009f6ed  sub     r8, rax
0x14009f6f0  lea     rax, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x14009f6f7  mov     al, [r8+rax]
0x14009f6fb  mov     [rbx+rdi], al
0x14009f6fe  inc     rdi
0x14009f701  sub     rsi, 1
0x14009f705  jnz     short loc_14009F6BE
0x14009f707  mov     [rbx+rdi], si
0x14009f70b  xor     eax, eax
0x14009f70d  mov     [r12], rbx
0x14009f711  jmp     short loc_14009F737
0x14009f713  mov     rcx, rbx
0x14009f716  call    sqlite3_free
0x14009f71b  lea     r8, aWingettempname_0; "winGetTempname4"
0x14009f722  mov     [rsp+78h+var_58], 0C62Bh
0x14009f72a  xor     edx, edx
0x14009f72c  lea     ecx, [rdx+1]
0x14009f72f  xor     r9d, r9d
0x14009f732  call    winLogErrorAtLine
0x14009f737  add     rsp, 38h
0x14009f73b  pop     r15
0x14009f73d  pop     r14
0x14009f73f  pop     r13
0x14009f741  pop     r12
0x14009f743  pop     rdi
0x14009f744  pop     rsi
0x14009f745  pop     rbp
0x14009f746  pop     rbx
0x14009f747  retn
```
