# sqlite3_serialize

- ea: `0x1800ab640`
- end: `0x1800ab8a3`
- name: `sqlite3_serialize`
- size: `611`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002cf8`
- `0x1800034f2`
- `0x180056004`
- `0x180078398`
- `0x1800807c0`
- `0x18008394c`
- `0x1800a7030`
- `0x1800a7070`
- `0x1800a90e0`
- `0x1800a97e0`
- `0x1800a98a0`
- `0x1800aa490`
- `0x1800aa540`
- `0x1800aaff0`
- `0x1800ab640`
- `0x1800abe70`
- `0x1800ca010`

## string_xrefs

- `0x1800ab7a3`: `BEGIN IMMEDIATE; COMMIT;`

## pseudocode

```c
__int64 __fastcall sqlite3_serialize(__int64 a1, __int64 a2, _QWORD *a3, char a4)
{
  __int64 v4; // rsi
  __int64 v7; // rbp
  __int64 v9; // r15
  int DbName; // eax
  size_t *v11; // rbx
  void *v12; // rdi
  void *v13; // rax
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
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64 *, _QWORD); // rax
  int v27; // eax
  __int64 v28; // r14
  void *v29; // rcx
  __int64 v30; // [rsp+98h] [rbp+10h] BYREF

  v4 = 0;
  v30 = 0;
  v7 = a2;
  if ( !a2 )
    v7 = **(_QWORD **)(a1 + 32);
  v9 = memdbFromDbSchema(a1, v7);
  DbName = sqlite3FindDbName(a1, v7);
  if ( a3 )
    *a3 = -1;
  if ( DbName < 0 )
    return 0;
  if ( v9 )
  {
    v11 = *(size_t **)(v9 + 8);
    if ( a3 )
      *a3 = *v11;
    if ( (a4 & 1) != 0 )
      return v11[3];
    v13 = (void *)sqlite3_malloc64(*v11);
    v12 = v13;
    if ( v13 )
      memcpy_0(v13, (const void *)v11[3], *v11);
    return (__int64)v12;
  }
  _mm_lfence();
  v15 = *(_QWORD *)(32LL * DbName + *(_QWORD *)(a1 + 32) + 8);
  if ( !v15 )
    return 0;
  v16 = *(int *)(*(_QWORD *)(v15 + 8) + 52LL);
  v17 = sqlite3_mprintf("PRAGMA \"%w\".page_count", v7);
  if ( v17 )
  {
    v18 = sqlite3LockAndPrepare(a1, v17, -1, 128, 0, (__int64)&v30, 0);
    v4 = v30;
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
    goto LABEL_26;
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
          v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v25 + 272);
          v30 = 0;
          v27 = v26(v25, (unsigned int)v23, &v30, 0);
          v28 = v30;
          v29 = (void *)(v22 + v20 * (v23 - 1));
          if ( v27 )
            memset_0(v29, 0, v20);
          else
            memcpy_0(v29, *(const void **)(v30 + 8), v20);
          if ( v28 )
            sqlite3PagerUnrefNotNull(v28);
          ++v23;
        }
        while ( v23 <= v24 );
      }
    }
  }
  else
  {
LABEL_26:
    v22 = 0;
  }
  sqlite3_finalize(v4);
  return v22;
}

```

## disassembly

```asm
0x1800ab640  mov     rax, rsp
0x1800ab643  push    rbx
0x1800ab644  push    rbp
0x1800ab645  push    rsi
0x1800ab646  push    rdi
0x1800ab647  push    r12
0x1800ab649  push    r13
0x1800ab64b  push    r14
0x1800ab64d  push    r15
0x1800ab64f  sub     rsp, 48h
0x1800ab653  xor     esi, esi
0x1800ab655  mov     r12d, r9d
0x1800ab658  mov     [rax+10h], rsi
0x1800ab65c  mov     rdi, r8
0x1800ab65f  mov     rbp, rdx
0x1800ab662  mov     r14, rcx
0x1800ab665  test    rdx, rdx
0x1800ab668  jnz     short loc_1800AB671
0x1800ab66a  mov     rax, [rcx+20h]
0x1800ab66e  mov     rbp, [rax]
0x1800ab671  mov     rdx, rbp
0x1800ab674  call    memdbFromDbSchema
0x1800ab679  mov     rdx, rbp
0x1800ab67c  mov     rcx, r14
0x1800ab67f  mov     r15, rax
0x1800ab682  call    sqlite3FindDbName
0x1800ab687  test    rdi, rdi
0x1800ab68a  jz      short loc_1800AB693
0x1800ab68c  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800ab693  test    eax, eax
0x1800ab695  js      loc_1800AB890
0x1800ab69b  test    r15, r15
0x1800ab69e  jz      short loc_1800AB6E2
0x1800ab6a0  mov     rbx, [r15+8]
0x1800ab6a4  test    rdi, rdi
0x1800ab6a7  jz      short loc_1800AB6AF
0x1800ab6a9  mov     rax, [rbx]
0x1800ab6ac  mov     [rdi], rax
0x1800ab6af  test    r12b, 1
0x1800ab6b3  jz      short loc_1800AB6BB
0x1800ab6b5  mov     rdi, [rbx+18h]
0x1800ab6b9  jmp     short loc_1800AB6DA
0x1800ab6bb  mov     rcx, [rbx]
0x1800ab6be  call    sqlite3_malloc64
0x1800ab6c3  mov     rdi, rax
0x1800ab6c6  test    rax, rax
0x1800ab6c9  jz      short loc_1800AB6DA
0x1800ab6cb  mov     r8, [rbx]; Size
0x1800ab6ce  mov     rcx, rax; void *
0x1800ab6d1  mov     rdx, [rbx+18h]; Src
0x1800ab6d5  call    memcpy_0
0x1800ab6da  mov     rax, rdi
0x1800ab6dd  jmp     loc_1800AB892
0x1800ab6e2  lfence
0x1800ab6e5  movsxd  rcx, eax
0x1800ab6e8  mov     rax, [r14+20h]
0x1800ab6ec  shl     rcx, 5
0x1800ab6f0  mov     r15, [rcx+rax+8]
0x1800ab6f5  test    r15, r15
0x1800ab6f8  jz      loc_1800AB890
0x1800ab6fe  mov     rax, [r15+8]
0x1800ab702  lea     rcx, aPragmaWPageCou; "PRAGMA \"%w\".page_count"
0x1800ab709  mov     rdx, rbp
0x1800ab70c  movsxd  r13, dword ptr [rax+34h]
0x1800ab710  call    sqlite3_mprintf
0x1800ab715  mov     rbx, rax
0x1800ab718  test    rax, rax
0x1800ab71b  jz      short loc_1800AB755
0x1800ab71d  lea     rax, [rsp+88h+arg_8]
0x1800ab725  mov     [rsp+88h+var_58], rsi
0x1800ab72a  mov     [rsp+88h+var_60], rax
0x1800ab72f  mov     r9d, 80h
0x1800ab735  or      r8d, 0FFFFFFFFh
0x1800ab739  mov     [rsp+88h+var_68], rsi
0x1800ab73e  mov     rdx, rbx
0x1800ab741  mov     rcx, r14
0x1800ab744  call    sqlite3LockAndPrepare
0x1800ab749  mov     rsi, [rsp+88h+arg_8]
0x1800ab751  mov     ebp, eax
0x1800ab753  jmp     short loc_1800AB75A
0x1800ab755  mov     ebp, 7
0x1800ab75a  mov     rcx, rbx
0x1800ab75d  call    sqlite3_free
0x1800ab762  test    ebp, ebp
0x1800ab764  jnz     loc_1800AB890
0x1800ab76a  mov     rcx, rsi
0x1800ab76d  call    sqlite3_step
0x1800ab772  cmp     eax, 64h ; 'd'
0x1800ab775  jnz     short loc_1800AB7DE
0x1800ab777  xor     edx, edx
0x1800ab779  mov     rcx, rsi
0x1800ab77c  mov     rbp, r13
0x1800ab77f  call    sqlite3_column_int64
0x1800ab784  mov     rbx, rax
0x1800ab787  imul    rbx, r13
0x1800ab78b  test    rbx, rbx
0x1800ab78e  jnz     short loc_1800AB7D0
0x1800ab790  mov     rcx, rsi
0x1800ab793  call    sqlite3_reset
0x1800ab798  xor     r9d, r9d
0x1800ab79b  mov     [rsp+88h+var_68], rbx
0x1800ab7a0  xor     r8d, r8d
0x1800ab7a3  lea     rdx, aBeginImmediate; "BEGIN IMMEDIATE; COMMIT;"
0x1800ab7aa  mov     rcx, r14
0x1800ab7ad  call    sqlite3_exec
0x1800ab7b2  mov     rcx, rsi
0x1800ab7b5  call    sqlite3_step
0x1800ab7ba  cmp     eax, 64h ; 'd'
0x1800ab7bd  jnz     short loc_1800AB7D0
0x1800ab7bf  xor     edx, edx
0x1800ab7c1  mov     rcx, rsi
0x1800ab7c4  call    sqlite3_column_int64
0x1800ab7c9  mov     rbx, rax
0x1800ab7cc  imul    rbx, rbp
0x1800ab7d0  test    rdi, rdi
0x1800ab7d3  jz      short loc_1800AB7D8
0x1800ab7d5  mov     [rdi], rbx
0x1800ab7d8  test    r12b, 1
0x1800ab7dc  jz      short loc_1800AB7E5
0x1800ab7de  xor     ebx, ebx
0x1800ab7e0  jmp     loc_1800AB883
0x1800ab7e5  mov     rcx, rbx
0x1800ab7e8  call    sqlite3_malloc64
0x1800ab7ed  mov     rbx, rax
0x1800ab7f0  test    rax, rax
0x1800ab7f3  jz      loc_1800AB883
0x1800ab7f9  xor     edx, edx
0x1800ab7fb  mov     rcx, rsi
0x1800ab7fe  call    sqlite3_column_int
0x1800ab803  mov     rcx, [r15+8]
0x1800ab807  mov     edi, 1
0x1800ab80c  mov     r12d, eax
0x1800ab80f  mov     r13, [rcx]
0x1800ab812  cmp     eax, edi
0x1800ab814  jl      short loc_1800AB883
0x1800ab816  mov     rax, [r13+110h]
0x1800ab81d  lea     ecx, [rdi-1]
0x1800ab820  movsxd  r15, ecx
0x1800ab823  lea     r8, [rsp+88h+arg_8]
0x1800ab82b  imul    r15, rbp
0x1800ab82f  xor     r9d, r9d
0x1800ab832  mov     [rsp+88h+arg_8], 0
0x1800ab83e  mov     edx, edi
0x1800ab840  mov     rcx, r13
0x1800ab843  add     r15, rbx
0x1800ab846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab84b  mov     r14, [rsp+88h+arg_8]
0x1800ab853  mov     r8, rbp; Size
0x1800ab856  mov     rcx, r15; void *
0x1800ab859  test    eax, eax
0x1800ab85b  jnz     short loc_1800AB868
0x1800ab85d  mov     rdx, [r14+8]; Src
0x1800ab861  call    memcpy_0
0x1800ab866  jmp     short loc_1800AB86F
0x1800ab868  xor     edx, edx; Val
0x1800ab86a  call    memset_0
0x1800ab86f  test    r14, r14
0x1800ab872  jz      short loc_1800AB87C
0x1800ab874  mov     rcx, r14
0x1800ab877  call    sqlite3PagerUnrefNotNull
0x1800ab87c  inc     edi
0x1800ab87e  cmp     edi, r12d
0x1800ab881  jle     short loc_1800AB816
0x1800ab883  mov     rcx, rsi
0x1800ab886  call    sqlite3_finalize
0x1800ab88b  mov     rax, rbx
0x1800ab88e  jmp     short loc_1800AB892
0x1800ab890  xor     eax, eax
0x1800ab892  add     rsp, 48h
0x1800ab896  pop     r15
0x1800ab898  pop     r14
0x1800ab89a  pop     r13
0x1800ab89c  pop     r12
0x1800ab89e  pop     rdi
0x1800ab89f  pop     rsi
0x1800ab8a0  pop     rbp
0x1800ab8a1  pop     rbx
0x1800ab8a2  retn
```
