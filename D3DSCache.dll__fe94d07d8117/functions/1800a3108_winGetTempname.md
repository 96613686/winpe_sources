# winGetTempname

- ea: `0x1800a3108`
- end: `0x1800a33d6`
- name: `winGetTempname`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180029560`
- `0x1800a2c10`

## callees

- `0x180012470`
- `0x1800293d4`
- `0x18002b81c`
- `0x180034900`
- `0x18003f650`
- `0x180041688`
- `0x180042500`
- `0x180086758`
- `0x180096b00`
- `0x1800a3108`
- `0x1800a4470`
- `0x1800a8010`

## string_xrefs

- `0x1800a3270`: `winGetTempname1`
- `0x1800a31e2`: `winGetTempname2`
- `0x1800a33a9`: `winGetTempname4`
- `0x1800a32f5`: `winGetTempname5`

## pseudocode

```c
__int64 __fastcall winGetTempname(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v3; // rsi
  int v5; // r14d
  int v6; // r12d
  __int64 v7; // rbx
  __int64 result; // rax
  int v9; // r15d
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rdi
  DWORD v15; // edx
  const char *v16; // rax
  const char *v17; // rbp
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  const char *v21; // r9
  __int64 v22; // rax
  const char *v23; // r8
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdi
  __int64 v31; // rsi
  DWORD v32; // r9d
  unsigned __int8 v33; // cl
  int v34; // [rsp+20h] [rbp-58h]

  v3 = *(int *)(a1 + 8);
  v5 = v3 + 2;
  v6 = sqlite3Strlen30("etilqs_", a2, a3);
  v7 = sqlite3MallocZero((int)v3 + 2);
  if ( !v7 )
    return 3082;
  v9 = v3 - v6 - 15;
  v10 = sqlite3MutexAlloc(11);
  sqlite3_mutex_enter(v10);
  if ( sqlite3_temp_directory )
  {
    v20 = sqlite3Strlen30(sqlite3_temp_directory, v11, v12);
    if ( v20 > 0 )
    {
      if ( v21[v20 - 1] != 47 && v21[v20 - 1] != 92 )
        ++v20;
      if ( v20 > v9 )
      {
        v22 = sqlite3MutexAlloc(11);
        sqlite3_mutex_leave(v22);
        sqlite3_free(v7);
        v23 = "winGetTempname1";
        v34 = 51443;
        return winLogErrorAtLine(1, 0, (_DWORD)v23, 0, v34);
      }
      sqlite3_snprintf((unsigned int)v3, v7, "%s", v21);
    }
    v24 = sqlite3MutexAlloc(11);
    sqlite3_mutex_leave(v24);
  }
  else
  {
    v13 = sqlite3MutexAlloc(11);
    sqlite3_mutex_leave(v13);
    v14 = sqlite3MallocZero(2 * v3);
    if ( !v14 )
    {
LABEL_5:
      sqlite3_free(v7);
      return 3082;
    }
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, __int64))off_1800C4158)((unsigned int)v3, v14) )
    {
      sqlite3_free(v14);
      sqlite3_free(v7);
      v15 = off_1800C40C8();
      return winLogErrorAtLine(6410, v15, (unsigned int)"winGetTempname2", 0, 51544);
    }
    v16 = (const char *)winUnicodeToUtf8(v14);
    v17 = v16;
    if ( !v16 )
    {
      sqlite3_free(v14);
      goto LABEL_5;
    }
    sqlite3_snprintf((unsigned int)v3, v7, "%s", v16);
    sqlite3_free(v17);
    sqlite3_free(v14);
  }
  v25 = sqlite3Strlen30(v7, v18, v19);
  if ( v25 <= 0 )
    goto LABEL_29;
  if ( *(_BYTE *)(v25 + v7 - 1) != 47 && *(_BYTE *)(v25 + v7 - 1) != 92 )
  {
    if ( v25 + 1 < v9 + 1 )
    {
      *(_WORD *)(v25 + v7) = 92;
      goto LABEL_24;
    }
LABEL_29:
    sqlite3_free(v7);
    v23 = "winGetTempname4";
    v34 = 51594;
    return winLogErrorAtLine(1, 0, (_DWORD)v23, 0, v34);
  }
LABEL_24:
  v27 = sqlite3Strlen30(v7, v25, v26);
  if ( v6 + v27 + 17 > v5 )
  {
    sqlite3_free(v7);
    v23 = "winGetTempname5";
    v34 = 51612;
    return winLogErrorAtLine(1, 0, (_DWORD)v23, 0, v34);
  }
  sqlite3_snprintf((unsigned int)(v5 - v27 - 16), v7 + v27, "etilqs_");
  v30 = (int)sqlite3Strlen30(v7, v28, v29);
  v31 = 15;
  sqlite3_randomness(15, v7 + v30);
  v32 = off_1800C3FF0();
  do
  {
    v33 = *(_BYTE *)(v7 + v30) + v32;
    v32 >>= 8;
    *(_BYTE *)(v7 + v30++) = aAbcdefghijklmn[v33 % 0x3EuLL];
    --v31;
  }
  while ( v31 );
  *(_WORD *)(v7 + v30) = 0;
  result = 0;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x1800a3108  push    rbx
0x1800a310a  push    rbp
0x1800a310b  push    rsi
0x1800a310c  push    rdi
0x1800a310d  push    r12
0x1800a310f  push    r13
0x1800a3111  push    r14
0x1800a3113  push    r15
0x1800a3115  sub     rsp, 38h
0x1800a3119  movsxd  rsi, dword ptr [rcx+8]
0x1800a311d  mov     r13, rdx
0x1800a3120  lea     rcx, aEtilqs; "etilqs_"
0x1800a3127  call    sqlite3Strlen30
0x1800a312c  lea     r14d, [rsi+2]
0x1800a3130  mov     r12d, eax
0x1800a3133  movsxd  rcx, r14d; Size
0x1800a3136  call    sqlite3MallocZero
0x1800a313b  mov     rbx, rax
0x1800a313e  test    rax, rax
0x1800a3141  jnz     short loc_1800A314D
0x1800a3143  mov     eax, 0C0Ah
0x1800a3148  jmp     loc_1800A33C5
0x1800a314d  mov     r15d, esi
0x1800a3150  mov     edi, 0Bh
0x1800a3155  sub     r15d, r12d
0x1800a3158  mov     ecx, edi
0x1800a315a  add     r15d, 0FFFFFFF1h
0x1800a315e  call    sqlite3MutexAlloc
0x1800a3163  mov     rcx, rax
0x1800a3166  call    sqlite3_mutex_enter
0x1800a316b  mov     r9, cs:sqlite3_temp_directory
0x1800a3172  test    r9, r9
0x1800a3175  jnz     loc_1800A3233
0x1800a317b  mov     ecx, edi
0x1800a317d  call    sqlite3MutexAlloc
0x1800a3182  mov     rcx, rax
0x1800a3185  call    sqlite3_mutex_leave
0x1800a318a  mov     rcx, rsi
0x1800a318d  add     rcx, rcx; Size
0x1800a3190  call    sqlite3MallocZero
0x1800a3195  mov     rdi, rax
0x1800a3198  test    rax, rax
0x1800a319b  jnz     short loc_1800A31A7
0x1800a319d  mov     rcx, rbx
0x1800a31a0  call    sqlite3_free
0x1800a31a5  jmp     short loc_1800A3143
0x1800a31a7  mov     rax, cs:off_1800C4158
0x1800a31ae  mov     rdx, rdi
0x1800a31b1  mov     ecx, esi
0x1800a31b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a31b8  mov     rcx, rdi
0x1800a31bb  test    eax, eax
0x1800a31bd  jnz     short loc_1800A31F3
0x1800a31bf  call    sqlite3_free
0x1800a31c4  mov     rcx, rbx
0x1800a31c7  call    sqlite3_free
0x1800a31cc  mov     rax, cs:off_1800C40C8
0x1800a31d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a31d8  mov     edx, eax
0x1800a31da  mov     [rsp+78h+var_58], 0C958h
0x1800a31e2  lea     r8, aWingettempname_2; "winGetTempname2"
0x1800a31e9  mov     ecx, 190Ah
0x1800a31ee  jmp     loc_1800A33BD
0x1800a31f3  call    winUnicodeToUtf8
0x1800a31f8  mov     rbp, rax
0x1800a31fb  test    rax, rax
0x1800a31fe  jz      short loc_1800A3226
0x1800a3200  mov     r9, rax
0x1800a3203  lea     r8, aS_10; "%s"
0x1800a320a  mov     rdx, rbx
0x1800a320d  mov     ecx, esi
0x1800a320f  call    sqlite3_snprintf
0x1800a3214  mov     rcx, rbp
0x1800a3217  call    sqlite3_free
0x1800a321c  mov     rcx, rdi
0x1800a321f  call    sqlite3_free
0x1800a3224  jmp     short loc_1800A32A4
0x1800a3226  mov     rcx, rdi
0x1800a3229  call    sqlite3_free
0x1800a322e  jmp     loc_1800A319D
0x1800a3233  mov     rcx, r9
0x1800a3236  call    sqlite3Strlen30
0x1800a323b  test    eax, eax
0x1800a323d  jle     short loc_1800A3295
0x1800a323f  movsxd  rcx, eax
0x1800a3242  cmp     byte ptr [rcx+r9-1], 2Fh ; '/'
0x1800a3248  jz      short loc_1800A3254
0x1800a324a  cmp     byte ptr [rcx+r9-1], 5Ch ; '\'
0x1800a3250  jz      short loc_1800A3254
0x1800a3252  inc     eax
0x1800a3254  cmp     eax, r15d
0x1800a3257  jle     short loc_1800A3284
0x1800a3259  mov     ecx, edi
0x1800a325b  call    sqlite3MutexAlloc
0x1800a3260  mov     rcx, rax
0x1800a3263  call    sqlite3_mutex_leave
0x1800a3268  mov     rcx, rbx
0x1800a326b  call    sqlite3_free
0x1800a3270  lea     r8, aWingettempname; "winGetTempname1"
0x1800a3277  mov     [rsp+78h+var_58], 0C8F3h
0x1800a327f  jmp     loc_1800A33B8
0x1800a3284  lea     r8, aS_10; "%s"
0x1800a328b  mov     rdx, rbx
0x1800a328e  mov     ecx, esi
0x1800a3290  call    sqlite3_snprintf
0x1800a3295  mov     ecx, edi
0x1800a3297  call    sqlite3MutexAlloc
0x1800a329c  mov     rcx, rax
0x1800a329f  call    sqlite3_mutex_leave
0x1800a32a4  mov     rcx, rbx
0x1800a32a7  call    sqlite3Strlen30
0x1800a32ac  test    eax, eax
0x1800a32ae  jle     loc_1800A33A1
0x1800a32b4  movsxd  rdx, eax
0x1800a32b7  cmp     byte ptr [rdx+rbx-1], 2Fh ; '/'
0x1800a32bc  jz      short loc_1800A32DA
0x1800a32be  cmp     byte ptr [rdx+rbx-1], 5Ch ; '\'
0x1800a32c3  jz      short loc_1800A32DA
0x1800a32c5  lea     ecx, [rax+1]
0x1800a32c8  lea     eax, [r15+1]
0x1800a32cc  cmp     ecx, eax
0x1800a32ce  jge     loc_1800A33A1
0x1800a32d4  mov     word ptr [rdx+rbx], 5Ch ; '\'
0x1800a32da  mov     rcx, rbx
0x1800a32dd  call    sqlite3Strlen30
0x1800a32e2  lea     ecx, [rax+11h]
0x1800a32e5  add     ecx, r12d
0x1800a32e8  cmp     ecx, r14d
0x1800a32eb  jle     short loc_1800A3309
0x1800a32ed  mov     rcx, rbx
0x1800a32f0  call    sqlite3_free
0x1800a32f5  lea     r8, aWingettempname_1; "winGetTempname5"
0x1800a32fc  mov     [rsp+78h+var_58], 0C99Ch
0x1800a3304  jmp     loc_1800A33B8
0x1800a3309  sub     r14d, eax
0x1800a330c  movsxd  rdx, eax
0x1800a330f  add     rdx, rbx
0x1800a3312  lea     r8, aEtilqs; "etilqs_"
0x1800a3319  lea     ecx, [r14-10h]
0x1800a331d  call    sqlite3_snprintf
0x1800a3322  mov     rcx, rbx
0x1800a3325  call    sqlite3Strlen30
0x1800a332a  movsxd  rdi, eax
0x1800a332d  mov     esi, 0Fh
0x1800a3332  mov     ecx, esi
0x1800a3334  lea     rdx, [rbx+rdi]
0x1800a3338  call    sqlite3_randomness
0x1800a333d  mov     rax, cs:off_1800C3FF0
0x1800a3344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3349  mov     r9d, eax
0x1800a334c  mov     cl, r9b
0x1800a334f  mov     rax, 842108421084211h
0x1800a3359  add     cl, [rbx+rdi]
0x1800a335c  movzx   r8d, cl
0x1800a3360  mul     r8
0x1800a3363  mov     eax, r8d
0x1800a3366  shr     r9d, 8
0x1800a336a  sub     rax, rdx
0x1800a336d  shr     rax, 1
0x1800a3370  add     rax, rdx
0x1800a3373  shr     rax, 5
0x1800a3377  imul    rax, 3Eh ; '>'
0x1800a337b  sub     r8, rax
0x1800a337e  lea     rax, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x1800a3385  mov     al, [r8+rax]
0x1800a3389  mov     [rbx+rdi], al
0x1800a338c  inc     rdi
0x1800a338f  sub     rsi, 1
0x1800a3393  jnz     short loc_1800A334C
0x1800a3395  mov     [rbx+rdi], si
0x1800a3399  xor     eax, eax
0x1800a339b  mov     [r13+0], rbx
0x1800a339f  jmp     short loc_1800A33C5
0x1800a33a1  mov     rcx, rbx
0x1800a33a4  call    sqlite3_free
0x1800a33a9  lea     r8, aWingettempname_0; "winGetTempname4"
0x1800a33b0  mov     [rsp+78h+var_58], 0C98Ah
0x1800a33b8  xor     edx, edx
0x1800a33ba  lea     ecx, [rdx+1]
0x1800a33bd  xor     r9d, r9d
0x1800a33c0  call    winLogErrorAtLine
0x1800a33c5  add     rsp, 38h
0x1800a33c9  pop     r15
0x1800a33cb  pop     r14
0x1800a33cd  pop     r13
0x1800a33cf  pop     r12
0x1800a33d1  pop     rdi
0x1800a33d2  pop     rsi
0x1800a33d3  pop     rbp
0x1800a33d4  pop     rbx
0x1800a33d5  retn
```
