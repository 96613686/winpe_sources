# sqlite3_serialize

- ea: `0x18008f680`
- end: `0x18008f8e2`
- name: `sqlite3_serialize`
- size: `610`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, char)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180001110`
- `0x180005b90`
- `0x18000aac0`
- `0x180014928`
- `0x180024dd8`
- `0x180027aa0`
- `0x180028170`
- `0x180028260`
- `0x180028c94`
- `0x1800291c0`
- `0x1800293e0`
- `0x180029bd0`
- `0x1800303e0`
- `0x18004aa70`
- `0x180060134`
- `0x18006910e`
- `0x180079b9c`
- `0x18008f680`
- `0x180099814`

## string_xrefs

- `0x18008f80b`: `BEGIN IMMEDIATE; COMMIT;`

## pseudocode

```c
__int64 __fastcall sqlite3_serialize(__int64 a1, __int64 a2, _QWORD *a3, char a4)
{
  __int64 v4; // rsi
  __int64 v10; // r15
  int DbName; // eax
  size_t *v12; // rbx
  void *v13; // rdi
  void *v14; // rax
  __int64 v15; // r15
  size_t v16; // r13
  __int64 v17; // rbx
  int v18; // eax
  int v19; // ebp
  size_t v20; // rbp
  __int64 v21; // rbx
  __int64 v22; // rbx
  int v23; // edi
  int v24; // r12d
  __int64 v25; // r13
  int v26; // eax
  __int64 v27; // r14
  void *v28; // rcx
  _QWORD v29[11]; // [rsp+40h] [rbp-58h] BYREF

  v4 = 0;
  v29[0] = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk() )
  {
    sqlite3ReportError(21, 53729, "misuse");
    return 0;
  }
  if ( !a2 )
    a2 = **(_QWORD **)(a1 + 32);
  v10 = memdbFromDbSchema(a1, a2);
  DbName = sqlite3FindDbName(a1, a2);
  if ( a3 )
    *a3 = -1;
  if ( DbName < 0 )
    return 0;
  if ( v10 )
  {
    v12 = *(size_t **)(v10 + 8);
    if ( a3 )
      *a3 = *v12;
    if ( (a4 & 1) != 0 )
      return v12[3];
    v14 = (void *)sqlite3_malloc64(*v12);
    v13 = v14;
    if ( v14 )
      memcpy_0(v14, (const void *)v12[3], *v12);
    return (__int64)v13;
  }
  else
  {
    _mm_lfence();
    v15 = *(_QWORD *)(32LL * DbName + *(_QWORD *)(a1 + 32) + 8);
    if ( !v15 )
      return 0;
    v16 = *(int *)(*(_QWORD *)(v15 + 8) + 52LL);
    v17 = sqlite3_mprintf("PRAGMA \"%w\".page_count", a2);
    if ( v17 )
    {
      v18 = sqlite3LockAndPrepare(a1, v17, -1, 128, 0, (__int64)v29, 0);
      v4 = v29[0];
      v19 = v18;
    }
    else
    {
      v19 = 7;
    }
    sqlite3_free(v17);
    if ( v19 )
      return 0;
    if ( (unsigned int)sqlite3_step(v4) != 100 )
      goto LABEL_29;
    v20 = v16;
    v21 = v16 * sqlite3_column_int64(v4, 0);
    if ( !v21 )
    {
      sqlite3_reset(v4);
      sqlite3_exec(a1, (unsigned int)"BEGIN IMMEDIATE; COMMIT;", 0, 0, 0);
      if ( (unsigned int)sqlite3_step(v4) == 100 )
        v21 = v16 * sqlite3_column_int64(v4, 0);
    }
    if ( a3 )
      *a3 = v21;
    if ( (a4 & 1) == 0 )
    {
      v22 = sqlite3_malloc64(v21);
      if ( v22 )
      {
        v23 = 1;
        v24 = sqlite3_column_int(v4, 0);
        v25 = **(_QWORD **)(v15 + 8);
        if ( v24 >= 1 )
        {
          do
          {
            v29[0] = 0;
            v26 = sqlite3PagerGet(v25, (unsigned int)v23, v29, 0);
            v27 = v29[0];
            v28 = (void *)(v22 + v20 * (v23 - 1));
            if ( v26 )
              memset_0(v28, 0, v20);
            else
              memcpy_0(v28, *(const void **)(v29[0] + 8LL), v20);
            sqlite3PagerUnref(v27);
            ++v23;
          }
          while ( v23 <= v24 );
        }
      }
    }
    else
    {
LABEL_29:
      v22 = 0;
    }
    sqlite3_finalize(v4);
    return v22;
  }
}

```

## disassembly

```asm
0x18008f680  push    rbx
0x18008f682  push    rbp
0x18008f683  push    rsi
0x18008f684  push    rdi
0x18008f685  push    r12
0x18008f687  push    r13
0x18008f689  push    r14
0x18008f68b  push    r15
0x18008f68d  sub     rsp, 58h
0x18008f691  xor     esi, esi
0x18008f693  mov     r12d, r9d
0x18008f696  mov     [rsp+98h+var_58], rsi
0x18008f69b  mov     rdi, r8
0x18008f69e  mov     rbp, rdx
0x18008f6a1  mov     r14, rcx
0x18008f6a4  call    sqlite3SafetyCheckOk
0x18008f6a9  test    eax, eax
0x18008f6ab  jnz     short loc_18008F6D4
0x18008f6ad  lea     r8, aMisuse; "misuse"
0x18008f6b4  mov     edx, 0D1E1h
0x18008f6b9  lea     ecx, [rsi+15h]
0x18008f6bc  call    sqlite3ReportError
0x18008f6c1  xor     eax, eax
0x18008f6c3  add     rsp, 58h
0x18008f6c7  pop     r15
0x18008f6c9  pop     r14
0x18008f6cb  pop     r13
0x18008f6cd  pop     r12
0x18008f6cf  pop     rdi
0x18008f6d0  pop     rsi
0x18008f6d1  pop     rbp
0x18008f6d2  pop     rbx
0x18008f6d3  retn
0x18008f6d4  test    rbp, rbp
0x18008f6d7  jnz     short loc_18008F6E0
0x18008f6d9  mov     rax, [r14+20h]
0x18008f6dd  mov     rbp, [rax]
0x18008f6e0  mov     rdx, rbp
0x18008f6e3  mov     rcx, r14
0x18008f6e6  call    memdbFromDbSchema
0x18008f6eb  mov     rdx, rbp
0x18008f6ee  mov     rcx, r14
0x18008f6f1  mov     r15, rax
0x18008f6f4  call    sqlite3FindDbName
0x18008f6f9  test    rdi, rdi
0x18008f6fc  jz      short loc_18008F705
0x18008f6fe  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18008f705  test    eax, eax
0x18008f707  js      short loc_18008F6C1
0x18008f709  test    r15, r15
0x18008f70c  jz      short loc_18008F750
0x18008f70e  mov     rbx, [r15+8]
0x18008f712  test    rdi, rdi
0x18008f715  jz      short loc_18008F71D
0x18008f717  mov     rax, [rbx]
0x18008f71a  mov     [rdi], rax
0x18008f71d  test    r12b, 1
0x18008f721  jz      short loc_18008F729
0x18008f723  mov     rdi, [rbx+18h]
0x18008f727  jmp     short loc_18008F748
0x18008f729  mov     rcx, [rbx]
0x18008f72c  call    sqlite3_malloc64
0x18008f731  mov     rdi, rax
0x18008f734  test    rax, rax
0x18008f737  jz      short loc_18008F748
0x18008f739  mov     r8, [rbx]; Size
0x18008f73c  mov     rcx, rax; void *
0x18008f73f  mov     rdx, [rbx+18h]; Src
0x18008f743  call    memcpy_0
0x18008f748  mov     rax, rdi
0x18008f74b  jmp     loc_18008F6C3
0x18008f750  lfence
0x18008f753  movsxd  rcx, eax
0x18008f756  mov     rax, [r14+20h]
0x18008f75a  shl     rcx, 5
0x18008f75e  mov     r15, [rcx+rax+8]
0x18008f763  test    r15, r15
0x18008f766  jz      loc_18008F6C1
0x18008f76c  mov     rax, [r15+8]
0x18008f770  lea     rcx, aPragmaWPageCou; "PRAGMA \"%w\".page_count"
0x18008f777  mov     rdx, rbp
0x18008f77a  movsxd  r13, dword ptr [rax+34h]
0x18008f77e  call    sqlite3_mprintf
0x18008f783  mov     rbx, rax
0x18008f786  test    rax, rax
0x18008f789  jz      short loc_18008F7BD
0x18008f78b  lea     rax, [rsp+98h+var_58]
0x18008f790  mov     [rsp+98h+var_68], rsi
0x18008f795  mov     [rsp+98h+var_70], rax
0x18008f79a  mov     r9d, 80h
0x18008f7a0  or      r8d, 0FFFFFFFFh
0x18008f7a4  mov     [rsp+98h+var_78], rsi
0x18008f7a9  mov     rdx, rbx
0x18008f7ac  mov     rcx, r14
0x18008f7af  call    sqlite3LockAndPrepare
0x18008f7b4  mov     rsi, [rsp+98h+var_58]
0x18008f7b9  mov     ebp, eax
0x18008f7bb  jmp     short loc_18008F7C2
0x18008f7bd  mov     ebp, 7
0x18008f7c2  mov     rcx, rbx
0x18008f7c5  call    sqlite3_free
0x18008f7ca  test    ebp, ebp
0x18008f7cc  jnz     loc_18008F6C1
0x18008f7d2  mov     rcx, rsi
0x18008f7d5  call    sqlite3_step
0x18008f7da  cmp     eax, 64h ; 'd'
0x18008f7dd  jnz     short loc_18008F846
0x18008f7df  xor     edx, edx
0x18008f7e1  mov     rcx, rsi
0x18008f7e4  mov     rbp, r13
0x18008f7e7  call    sqlite3_column_int64
0x18008f7ec  mov     rbx, rax
0x18008f7ef  imul    rbx, r13
0x18008f7f3  test    rbx, rbx
0x18008f7f6  jnz     short loc_18008F838
0x18008f7f8  mov     rcx, rsi
0x18008f7fb  call    sqlite3_reset
0x18008f800  xor     r9d, r9d
0x18008f803  mov     [rsp+98h+var_78], rbx
0x18008f808  xor     r8d, r8d
0x18008f80b  lea     rdx, aBeginImmediate; "BEGIN IMMEDIATE; COMMIT;"
0x18008f812  mov     rcx, r14
0x18008f815  call    sqlite3_exec
0x18008f81a  mov     rcx, rsi
0x18008f81d  call    sqlite3_step
0x18008f822  cmp     eax, 64h ; 'd'
0x18008f825  jnz     short loc_18008F838
0x18008f827  xor     edx, edx
0x18008f829  mov     rcx, rsi
0x18008f82c  call    sqlite3_column_int64
0x18008f831  mov     rbx, rax
0x18008f834  imul    rbx, rbp
0x18008f838  test    rdi, rdi
0x18008f83b  jz      short loc_18008F840
0x18008f83d  mov     [rdi], rbx
0x18008f840  test    r12b, 1
0x18008f844  jz      short loc_18008F84D
0x18008f846  xor     ebx, ebx
0x18008f848  jmp     loc_18008F8D2
0x18008f84d  mov     rcx, rbx
0x18008f850  call    sqlite3_malloc64
0x18008f855  mov     rbx, rax
0x18008f858  test    rax, rax
0x18008f85b  jz      short loc_18008F8D2
0x18008f85d  xor     edx, edx
0x18008f85f  mov     rcx, rsi
0x18008f862  call    sqlite3_column_int
0x18008f867  mov     rcx, [r15+8]
0x18008f86b  mov     edi, 1
0x18008f870  mov     r12d, eax
0x18008f873  mov     r13, [rcx]
0x18008f876  cmp     eax, edi
0x18008f878  jl      short loc_18008F8D2
0x18008f87a  lea     ecx, [rdi-1]
0x18008f87d  mov     [rsp+98h+var_58], 0
0x18008f886  movsxd  r15, ecx
0x18008f889  lea     r8, [rsp+98h+var_58]
0x18008f88e  imul    r15, rbp
0x18008f892  xor     r9d, r9d
0x18008f895  mov     edx, edi
0x18008f897  mov     rcx, r13
0x18008f89a  add     r15, rbx
0x18008f89d  call    sqlite3PagerGet
0x18008f8a2  mov     r14, [rsp+98h+var_58]
0x18008f8a7  mov     r8, rbp; Size
0x18008f8aa  mov     rcx, r15; void *
0x18008f8ad  test    eax, eax
0x18008f8af  jnz     short loc_18008F8BC
0x18008f8b1  mov     rdx, [r14+8]; Src
0x18008f8b5  call    memcpy_0
0x18008f8ba  jmp     short loc_18008F8C3
0x18008f8bc  xor     edx, edx; Val
0x18008f8be  call    memset_0
0x18008f8c3  mov     rcx, r14
0x18008f8c6  call    sqlite3PagerUnref
0x18008f8cb  inc     edi
0x18008f8cd  cmp     edi, r12d
0x18008f8d0  jle     short loc_18008F87A
0x18008f8d2  mov     rcx, rsi
0x18008f8d5  call    sqlite3_finalize
0x18008f8da  mov     rax, rbx
0x18008f8dd  jmp     loc_18008F6C3
```
