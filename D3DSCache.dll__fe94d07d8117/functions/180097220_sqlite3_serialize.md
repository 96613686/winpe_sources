# sqlite3_serialize

- ea: `0x180097220`
- end: `0x180097482`
- name: `sqlite3_serialize`
- size: `610`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180012470`
- `0x18002e150`
- `0x1800334f0`
- `0x1800337f4`
- `0x180038710`
- `0x180038a64`
- `0x180038d50`
- `0x18003a860`
- `0x18003ad5c`
- `0x1800424e4`
- `0x180045374`
- `0x18006bdcc`
- `0x180093a00`
- `0x180093a40`
- `0x180095c50`
- `0x1800964a0`
- `0x180096550`
- `0x180097220`
- `0x1800a6d08`

## string_xrefs

- `0x1800973ab`: `BEGIN IMMEDIATE; COMMIT;`

## pseudocode

```c
__int64 __fastcall sqlite3_serialize(__int64 a1, __int64 a2, _QWORD *a3, char a4)
{
  __int64 v4; // rsi
  __int64 v10; // r15
  int DbName; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  size_t *v14; // rbx
  void *v15; // rdi
  void *v16; // rax
  __int64 v17; // r15
  size_t v18; // r13
  __int64 v19; // rbx
  int v20; // eax
  int v21; // ebp
  size_t v22; // rbp
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // r8
  __int64 v26; // rbx
  int v27; // edi
  int v28; // r12d
  __int64 v29; // r13
  int v30; // eax
  __int64 v31; // r14
  void *v32; // rcx
  _QWORD v33[11]; // [rsp+40h] [rbp-58h] BYREF

  v4 = 0;
  v33[0] = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) )
  {
    sqlite3ReportError(21, 53633, "misuse");
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
    v14 = *(size_t **)(v10 + 8);
    if ( a3 )
      *a3 = *v14;
    if ( (a4 & 1) != 0 )
      return v14[3];
    v16 = (void *)sqlite3_malloc64(*v14, v12, v13);
    v15 = v16;
    if ( v16 )
      memcpy_0(v16, (const void *)v14[3], *v14);
    return (__int64)v15;
  }
  else
  {
    _mm_lfence();
    v17 = *(_QWORD *)(32LL * DbName + *(_QWORD *)(a1 + 32) + 8);
    if ( !v17 )
      return 0;
    v18 = *(int *)(*(_QWORD *)(v17 + 8) + 52LL);
    v19 = sqlite3_mprintf("PRAGMA \"%w\".page_count", a2);
    if ( v19 )
    {
      v20 = sqlite3LockAndPrepare(a1, v19, -1, 128, 0, (__int64)v33, 0);
      v4 = v33[0];
      v21 = v20;
    }
    else
    {
      v21 = 7;
    }
    sqlite3_free(v19);
    if ( v21 )
      return 0;
    if ( (unsigned int)sqlite3_step(v4) != 100 )
      goto LABEL_29;
    v22 = v18;
    v24 = v18 * sqlite3_column_int64(v4, 0);
    if ( !v24 )
    {
      sqlite3_reset(v4);
      sqlite3_exec(a1, (unsigned int)"BEGIN IMMEDIATE; COMMIT;", 0, 0, 0);
      if ( (unsigned int)sqlite3_step(v4) == 100 )
        v24 = v18 * sqlite3_column_int64(v4, 0);
    }
    if ( a3 )
      *a3 = v24;
    if ( (a4 & 1) == 0 )
    {
      v26 = sqlite3_malloc64(v24, v23, v25);
      if ( v26 )
      {
        v27 = 1;
        v28 = sqlite3_column_int(v4, 0);
        v29 = **(_QWORD **)(v17 + 8);
        if ( v28 >= 1 )
        {
          do
          {
            v33[0] = 0;
            v30 = sqlite3PagerGet(v29, (unsigned int)v27, v33, 0);
            v31 = v33[0];
            v32 = (void *)(v26 + v22 * (v27 - 1));
            if ( v30 )
              memset_0(v32, 0, v22);
            else
              memcpy_0(v32, *(const void **)(v33[0] + 8LL), v22);
            sqlite3PagerUnref(v31);
            ++v27;
          }
          while ( v27 <= v28 );
        }
      }
    }
    else
    {
LABEL_29:
      v26 = 0;
    }
    sqlite3_finalize(v4);
    return v26;
  }
}

```

## disassembly

```asm
0x180097220  push    rbx
0x180097222  push    rbp
0x180097223  push    rsi
0x180097224  push    rdi
0x180097225  push    r12
0x180097227  push    r13
0x180097229  push    r14
0x18009722b  push    r15
0x18009722d  sub     rsp, 58h
0x180097231  xor     esi, esi
0x180097233  mov     r12d, r9d
0x180097236  mov     [rsp+98h+var_58], rsi
0x18009723b  mov     rdi, r8
0x18009723e  mov     rbp, rdx
0x180097241  mov     r14, rcx
0x180097244  call    sqlite3SafetyCheckOk
0x180097249  test    eax, eax
0x18009724b  jnz     short loc_180097274
0x18009724d  lea     r8, aMisuse; "misuse"
0x180097254  mov     edx, 0D181h
0x180097259  lea     ecx, [rsi+15h]
0x18009725c  call    sqlite3ReportError
0x180097261  xor     eax, eax
0x180097263  add     rsp, 58h
0x180097267  pop     r15
0x180097269  pop     r14
0x18009726b  pop     r13
0x18009726d  pop     r12
0x18009726f  pop     rdi
0x180097270  pop     rsi
0x180097271  pop     rbp
0x180097272  pop     rbx
0x180097273  retn
0x180097274  test    rbp, rbp
0x180097277  jnz     short loc_180097280
0x180097279  mov     rax, [r14+20h]
0x18009727d  mov     rbp, [rax]
0x180097280  mov     rdx, rbp
0x180097283  mov     rcx, r14
0x180097286  call    memdbFromDbSchema
0x18009728b  mov     rdx, rbp
0x18009728e  mov     rcx, r14
0x180097291  mov     r15, rax
0x180097294  call    sqlite3FindDbName
0x180097299  test    rdi, rdi
0x18009729c  jz      short loc_1800972A5
0x18009729e  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800972a5  test    eax, eax
0x1800972a7  js      short loc_180097261
0x1800972a9  test    r15, r15
0x1800972ac  jz      short loc_1800972F0
0x1800972ae  mov     rbx, [r15+8]
0x1800972b2  test    rdi, rdi
0x1800972b5  jz      short loc_1800972BD
0x1800972b7  mov     rax, [rbx]
0x1800972ba  mov     [rdi], rax
0x1800972bd  test    r12b, 1
0x1800972c1  jz      short loc_1800972C9
0x1800972c3  mov     rdi, [rbx+18h]
0x1800972c7  jmp     short loc_1800972E8
0x1800972c9  mov     rcx, [rbx]
0x1800972cc  call    sqlite3_malloc64
0x1800972d1  mov     rdi, rax
0x1800972d4  test    rax, rax
0x1800972d7  jz      short loc_1800972E8
0x1800972d9  mov     r8, [rbx]; Size
0x1800972dc  mov     rcx, rax; void *
0x1800972df  mov     rdx, [rbx+18h]; Src
0x1800972e3  call    memcpy_0
0x1800972e8  mov     rax, rdi
0x1800972eb  jmp     loc_180097263
0x1800972f0  lfence
0x1800972f3  movsxd  rcx, eax
0x1800972f6  mov     rax, [r14+20h]
0x1800972fa  shl     rcx, 5
0x1800972fe  mov     r15, [rcx+rax+8]
0x180097303  test    r15, r15
0x180097306  jz      loc_180097261
0x18009730c  mov     rax, [r15+8]
0x180097310  lea     rcx, aPragmaWPageCou; "PRAGMA \"%w\".page_count"
0x180097317  mov     rdx, rbp
0x18009731a  movsxd  r13, dword ptr [rax+34h]
0x18009731e  call    sqlite3_mprintf
0x180097323  mov     rbx, rax
0x180097326  test    rax, rax
0x180097329  jz      short loc_18009735D
0x18009732b  lea     rax, [rsp+98h+var_58]
0x180097330  mov     [rsp+98h+var_68], rsi
0x180097335  mov     [rsp+98h+var_70], rax
0x18009733a  mov     r9d, 80h
0x180097340  or      r8d, 0FFFFFFFFh
0x180097344  mov     [rsp+98h+var_78], rsi
0x180097349  mov     rdx, rbx
0x18009734c  mov     rcx, r14
0x18009734f  call    sqlite3LockAndPrepare
0x180097354  mov     rsi, [rsp+98h+var_58]
0x180097359  mov     ebp, eax
0x18009735b  jmp     short loc_180097362
0x18009735d  mov     ebp, 7
0x180097362  mov     rcx, rbx
0x180097365  call    sqlite3_free
0x18009736a  test    ebp, ebp
0x18009736c  jnz     loc_180097261
0x180097372  mov     rcx, rsi
0x180097375  call    sqlite3_step
0x18009737a  cmp     eax, 64h ; 'd'
0x18009737d  jnz     short loc_1800973E6
0x18009737f  xor     edx, edx
0x180097381  mov     rcx, rsi
0x180097384  mov     rbp, r13
0x180097387  call    sqlite3_column_int64
0x18009738c  mov     rbx, rax
0x18009738f  imul    rbx, r13
0x180097393  test    rbx, rbx
0x180097396  jnz     short loc_1800973D8
0x180097398  mov     rcx, rsi
0x18009739b  call    sqlite3_reset
0x1800973a0  xor     r9d, r9d
0x1800973a3  mov     [rsp+98h+var_78], rbx
0x1800973a8  xor     r8d, r8d
0x1800973ab  lea     rdx, aBeginImmediate; "BEGIN IMMEDIATE; COMMIT;"
0x1800973b2  mov     rcx, r14
0x1800973b5  call    sqlite3_exec
0x1800973ba  mov     rcx, rsi
0x1800973bd  call    sqlite3_step
0x1800973c2  cmp     eax, 64h ; 'd'
0x1800973c5  jnz     short loc_1800973D8
0x1800973c7  xor     edx, edx
0x1800973c9  mov     rcx, rsi
0x1800973cc  call    sqlite3_column_int64
0x1800973d1  mov     rbx, rax
0x1800973d4  imul    rbx, rbp
0x1800973d8  test    rdi, rdi
0x1800973db  jz      short loc_1800973E0
0x1800973dd  mov     [rdi], rbx
0x1800973e0  test    r12b, 1
0x1800973e4  jz      short loc_1800973ED
0x1800973e6  xor     ebx, ebx
0x1800973e8  jmp     loc_180097472
0x1800973ed  mov     rcx, rbx
0x1800973f0  call    sqlite3_malloc64
0x1800973f5  mov     rbx, rax
0x1800973f8  test    rax, rax
0x1800973fb  jz      short loc_180097472
0x1800973fd  xor     edx, edx
0x1800973ff  mov     rcx, rsi
0x180097402  call    sqlite3_column_int
0x180097407  mov     rcx, [r15+8]
0x18009740b  mov     edi, 1
0x180097410  mov     r12d, eax
0x180097413  mov     r13, [rcx]
0x180097416  cmp     eax, edi
0x180097418  jl      short loc_180097472
0x18009741a  lea     ecx, [rdi-1]
0x18009741d  mov     [rsp+98h+var_58], 0
0x180097426  movsxd  r15, ecx
0x180097429  lea     r8, [rsp+98h+var_58]
0x18009742e  imul    r15, rbp
0x180097432  xor     r9d, r9d
0x180097435  mov     edx, edi
0x180097437  mov     rcx, r13
0x18009743a  add     r15, rbx
0x18009743d  call    sqlite3PagerGet
0x180097442  mov     r14, [rsp+98h+var_58]
0x180097447  mov     r8, rbp; Size
0x18009744a  mov     rcx, r15; void *
0x18009744d  test    eax, eax
0x18009744f  jnz     short loc_18009745C
0x180097451  mov     rdx, [r14+8]; Src
0x180097455  call    memcpy_0
0x18009745a  jmp     short loc_180097463
0x18009745c  xor     edx, edx; Val
0x18009745e  call    memset_0
0x180097463  mov     rcx, r14
0x180097466  call    sqlite3PagerUnref
0x18009746b  inc     edi
0x18009746d  cmp     edi, r12d
0x180097470  jle     short loc_18009741A
0x180097472  mov     rcx, rsi
0x180097475  call    sqlite3_finalize
0x18009747a  mov     rax, rbx
0x18009747d  jmp     loc_180097263
```
