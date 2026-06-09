# attachFunc

- ea: `0x180053c70`
- end: `0x18005410f`
- name: `attachFunc`
- size: `1183`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x180007a00`
- `0x180012470`
- `0x180020330`
- `0x180020410`
- `0x1800283fc`
- `0x18003540c`
- `0x180036770`
- `0x1800379c8`
- `0x18003b5b4`
- `0x18003c8d4`
- `0x180042350`
- `0x1800423e0`
- `0x1800427d0`
- `0x180042b88`
- `0x180042bb0`
- `0x180042bcc`
- `0x180042dc4`
- `0x180053c70`
- `0x1800798dc`
- `0x18007ac0c`
- `0x18007adf8`
- `0x18007d92c`
- `0x1800873cc`
- `0x18008821c`
- `0x180089a6c`
- `0x180094470`
- `0x180096df0`
- `0x180098d40`

## string_xrefs

- `0x180053e12`: `database %s is already in use`
- `0x180053f51`: `database is already attached`
- `0x1800540db`: `unable to open database: %s`

## pseudocode

```c
_OWORD *__fastcall attachFunc(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r12
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rbx
  __int64 v13; // rax
  const unsigned __int16 *v14; // r15
  const unsigned __int16 *v15; // rcx
  _OWORD *result; // rax
  unsigned int v17; // edi
  __int64 v18; // rbx
  __int64 v19; // r15
  __int64 v20; // r14
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // r14d
  unsigned int i; // ebx
  __int64 v25; // rdx
  _OWORD *v26; // rdx
  _OWORD *v27; // rcx
  __int64 v28; // r14
  const char *v29; // rdx
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rbx
  unsigned int v35; // eax
  bool v36; // zf
  __int64 v37; // rbx
  int v38; // r14d
  __int64 v39; // rcx
  __int64 v40; // [rsp+20h] [rbp-30h]
  __int64 v41; // [rsp+30h] [rbp-20h] BYREF
  __int64 v42; // [rsp+38h] [rbp-18h] BYREF
  __int64 v43; // [rsp+40h] [rbp-10h] BYREF
  const unsigned __int16 *v44; // [rsp+48h] [rbp-8h]
  __int64 v45; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v46; // [rsp+A8h] [rbp+58h] BYREF

  v5 = sqlite3_context_db_handle();
  v6 = *a3;
  LOBYTE(v7) = 1;
  v42 = 0;
  v8 = 0;
  v41 = 0;
  v46 = 0;
  v9 = v5;
  v43 = 0;
  v10 = sqlite3ValueText(v6, v7);
  LOBYTE(v11) = 1;
  v12 = (const unsigned __int16 *)v10;
  v13 = sqlite3ValueText(a3[1], v11);
  v14 = &Src;
  v15 = &Src;
  if ( v12 )
    v15 = v12;
  v44 = v15;
  if ( v13 )
    v14 = (const unsigned __int16 *)v13;
  if ( (*(_BYTE *)(v9 + 200) & 4) != 0 )
  {
    v45 = 0;
    result = (_OWORD *)sqlite3_vfs_find("memdb");
    if ( !result )
      return result;
    v17 = sqlite3BtreeOpen(result, "x", v9, &v45, 0, 256);
    if ( v17 )
      goto LABEL_13;
    v18 = v45;
    v19 = sqlite3SchemaGet(v9, v45);
    if ( !v19 )
    {
      sqlite3BtreeClose(v18);
      v17 = 7;
      goto LABEL_13;
    }
    v20 = *(_QWORD *)(v9 + 32) + 32LL * *(unsigned __int8 *)(v9 + 196);
    v21 = *(_QWORD *)(v20 + 8);
    if ( v21 )
      sqlite3BtreeClose(v21);
    *(_QWORD *)(v20 + 8) = v18;
    *(_QWORD *)(v20 + 24) = v19;
  }
  else
  {
    v22 = *(_DWORD *)(v9 + 164);
    v17 = 0;
    v23 = *(_DWORD *)(v9 + 40);
    if ( v23 >= v22 + 2 )
    {
      result = (_OWORD *)sqlite3MPrintf(v9, "too many attached databases - max %d", v22);
LABEL_21:
      v46 = (__int64)result;
LABEL_14:
      if ( !result )
        goto LABEL_16;
      goto LABEL_15;
    }
    for ( i = 0; (int)i < v23; ++i )
    {
      if ( (unsigned int)sqlite3DbIsNamed(v9, i, v14) )
      {
        result = (_OWORD *)sqlite3MPrintf(v9, "database %s is already in use", v14);
        goto LABEL_21;
      }
    }
    v25 = *(_QWORD *)(v9 + 32);
    if ( v25 == v9 + 672 )
    {
      result = (_OWORD *)sqlite3DbMallocRawNN(v9, 96);
      v26 = result;
      if ( !result )
        return result;
      v27 = *(_OWORD **)(v9 + 32);
      *result = *v27;
      result[1] = v27[1];
      result[2] = v27[2];
      result[3] = v27[3];
    }
    else
    {
      result = (_OWORD *)sqlite3DbRealloc(v9, v25, 32LL * (v23 + 1));
      v26 = result;
      if ( !result )
        return result;
    }
    v28 = *(int *)(v9 + 40);
    *(_QWORD *)(v9 + 32) = v26;
    v20 = (__int64)&v26[2 * v28];
    v29 = (const char *)v44;
    *(_OWORD *)v20 = 0;
    *(_OWORD *)(v20 + 16) = 0;
    v30 = *(_QWORD *)v9;
    LODWORD(v45) = *(_DWORD *)(v9 + 76);
    v31 = sqlite3ParseUri(*(const char **)(v30 + 24), v29, (unsigned int *)&v45, &v43, &v42, &v41);
    if ( v31 )
    {
      if ( v31 == 7 )
        sqlite3OomFault(v9);
      sqlite3_result_error(a1, v41, 0xFFFFFFFFLL);
      return (_OWORD *)sqlite3_free(v41);
    }
    v8 = v42;
    LODWORD(v40) = 0;
    v32 = sqlite3BtreeOpen(v43, v42, v9, v20 + 8, v40, (unsigned int)v45 | 0x100);
    ++*(_DWORD *)(v9 + 40);
    v17 = v32;
    *(_QWORD *)v20 = sqlite3DbStrDup(v9, v14);
  }
  *(_BYTE *)(v9 + 111) = 0;
  if ( v17 == 19 )
  {
    v17 = 1;
    v46 = sqlite3MPrintf(v9, "database is already attached");
  }
  else if ( !v17 )
  {
    v33 = sqlite3SchemaGet(v9, *(_QWORD *)(v20 + 8));
    *(_QWORD *)(v20 + 24) = v33;
    if ( v33 )
    {
      if ( *(_BYTE *)(v33 + 112) && *(_BYTE *)(v33 + 113) != *(_BYTE *)(v9 + 100) )
      {
        v46 = sqlite3MPrintf(v9, "attached databases must use the same text encoding as main database");
        v17 = 1;
      }
    }
    else
    {
      v17 = 7;
    }
    sqlite3BtreeEnter(*(_QWORD *)(v20 + 8));
    sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(v20 + 8) + 8LL), *(unsigned __int8 *)(v9 + 105));
    v34 = *(_QWORD *)(v20 + 8);
    v35 = sqlite3BtreeSecureDelete(*(_QWORD *)(*(_QWORD *)(v9 + 32) + 8LL), 0xFFFFFFFFLL);
    sqlite3BtreeSecureDelete(v34, v35);
    sqlite3BtreeSetPagerFlags(*(_QWORD *)(v20 + 8), *(_DWORD *)(v9 + 48) & 0x38 | 3u);
    sqlite3BtreeLeave(*(_QWORD *)(v20 + 8));
  }
  *(_BYTE *)(v20 + 16) = 3;
  if ( !v17 && !*(_QWORD *)v20 )
    v17 = 7;
  sqlite3_free_filename(v8);
  if ( v17 )
    goto LABEL_53;
  sqlite3BtreeEnterAll(v9);
  *(_DWORD *)(v9 + 44) &= ~0x10u;
  v36 = (*(_BYTE *)(v9 + 200) & 4) == 0;
  *(_BYTE *)(v9 + 196) = 0;
  if ( v36 )
    v17 = sqlite3Init(v9, &v46);
  result = (_OWORD *)sqlite3BtreeLeaveAll(v9);
  if ( v17 )
  {
LABEL_53:
    if ( (*(_BYTE *)(v9 + 200) & 4) == 0 )
    {
      v37 = 32LL * *(int *)(v9 + 40);
      v38 = *(_DWORD *)(v9 + 40) - 1;
      v39 = *(_QWORD *)(v37 + *(_QWORD *)(v9 + 32) - 24);
      if ( v39 )
      {
        sqlite3BtreeClose(v39);
        *(_QWORD *)(v37 + *(_QWORD *)(v9 + 32) - 24) = 0;
        *(_QWORD *)(v37 + *(_QWORD *)(v9 + 32) - 8) = 0;
      }
      sqlite3ResetAllSchemasOfConnection(v9);
      *(_DWORD *)(v9 + 40) = v38;
      if ( v17 == 7 || v17 == 3082 )
      {
        sqlite3OomFault(v9);
        sqlite3DbFree(v9, v46);
        result = (_OWORD *)sqlite3MPrintf(v9, "out of memory");
      }
      else
      {
        result = (_OWORD *)v46;
        if ( v46 )
        {
LABEL_15:
          sqlite3_result_error(a1, result, 0xFFFFFFFFLL);
          result = (_OWORD *)sqlite3DbFree(v9, v46);
LABEL_16:
          if ( v17 )
            return (_OWORD *)sqlite3_result_error_code(a1, v17);
          return result;
        }
        result = (_OWORD *)sqlite3MPrintf(v9, "unable to open database: %s", v44);
      }
      goto LABEL_21;
    }
LABEL_13:
    result = (_OWORD *)v46;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x180053c70  mov     [rsp-38h+arg_0], rbx
0x180053c75  push    rbp
0x180053c76  push    rsi
0x180053c77  push    rdi
0x180053c78  push    r12
0x180053c7a  push    r13
0x180053c7c  push    r14
0x180053c7e  push    r15
0x180053c80  mov     rbp, rsp
0x180053c83  sub     rsp, 50h
0x180053c87  mov     rdi, r8
0x180053c8a  mov     r13, rcx
0x180053c8d  call    sqlite3_context_db_handle
0x180053c92  mov     rcx, [rdi]
0x180053c95  xor     r14d, r14d
0x180053c98  mov     dl, 1
0x180053c9a  mov     [rbp+var_18], r14
0x180053c9e  mov     r12d, r14d
0x180053ca1  mov     [rbp+var_20], r14
0x180053ca5  mov     [rbp+arg_18], r14
0x180053ca9  mov     rsi, rax
0x180053cac  mov     [rbp+var_10], r14
0x180053cb0  call    sqlite3ValueText
0x180053cb5  mov     rcx, [rdi+8]
0x180053cb9  mov     dl, 1
0x180053cbb  mov     rbx, rax
0x180053cbe  call    sqlite3ValueText
0x180053cc3  test    rbx, rbx
0x180053cc6  lea     r15, Src
0x180053ccd  mov     rcx, r15
0x180053cd0  cmovnz  rcx, rbx
0x180053cd4  test    rax, rax
0x180053cd7  mov     [rbp+var_8], rcx
0x180053cdb  cmovnz  r15, rax
0x180053cdf  test    byte ptr [rsi+0C8h], 4
0x180053ce6  jz      loc_180053DC7
0x180053cec  lea     rcx, aMemdb; "memdb"
0x180053cf3  mov     [rbp+arg_10], r14
0x180053cf7  call    sqlite3_vfs_find
0x180053cfc  test    rax, rax
0x180053cff  jz      loc_180053DAF
0x180053d05  mov     dword ptr [rsp+50h+var_28], 100h
0x180053d0d  lea     r9, [rbp+arg_10]
0x180053d11  mov     r8, rsi
0x180053d14  mov     dword ptr [rsp+50h+var_30], r14d
0x180053d19  lea     rdx, asc_1800B266C; "x"
0x180053d20  mov     rcx, rax
0x180053d23  call    sqlite3BtreeOpen
0x180053d28  mov     edi, eax
0x180053d2a  test    eax, eax
0x180053d2c  jnz     short loc_180053D7D
0x180053d2e  mov     rbx, [rbp+arg_10]
0x180053d32  mov     rcx, rsi
0x180053d35  mov     rdx, rbx
0x180053d38  call    sqlite3SchemaGet
0x180053d3d  mov     r15, rax
0x180053d40  test    rax, rax
0x180053d43  jz      short loc_180053D70
0x180053d45  movzx   r14d, byte ptr [rsi+0C4h]
0x180053d4d  shl     r14, 5
0x180053d51  add     r14, [rsi+20h]
0x180053d55  mov     rcx, [r14+8]
0x180053d59  test    rcx, rcx
0x180053d5c  jz      short loc_180053D63
0x180053d5e  call    sqlite3BtreeClose
0x180053d63  mov     [r14+8], rbx
0x180053d67  mov     [r14+18h], r15
0x180053d6b  jmp     loc_180053F42
0x180053d70  mov     rcx, rbx
0x180053d73  call    sqlite3BtreeClose
0x180053d78  mov     edi, 7
0x180053d7d  mov     rax, [rbp+arg_18]
0x180053d81  test    rax, rax
0x180053d84  jz      short loc_180053DA1
0x180053d86  or      r8d, 0FFFFFFFFh
0x180053d8a  mov     rdx, rax
0x180053d8d  mov     rcx, r13
0x180053d90  call    sqlite3_result_error
0x180053d95  mov     rdx, [rbp+arg_18]
0x180053d99  mov     rcx, rsi
0x180053d9c  call    sqlite3DbFree
0x180053da1  test    edi, edi
0x180053da3  jz      short loc_180053DAF
0x180053da5  mov     edx, edi
0x180053da7  mov     rcx, r13
0x180053daa  call    sqlite3_result_error_code
0x180053daf  mov     rbx, [rsp+50h+arg_0]
0x180053db7  add     rsp, 50h
0x180053dbb  pop     r15
0x180053dbd  pop     r14
0x180053dbf  pop     r13
0x180053dc1  pop     r12
0x180053dc3  pop     rdi
0x180053dc4  pop     rsi
0x180053dc5  pop     rbp
0x180053dc6  retn
0x180053dc7  mov     r8d, [rsi+0A4h]
0x180053dce  mov     edi, r14d
0x180053dd1  mov     r14d, [rsi+28h]
0x180053dd5  lea     eax, [r8+2]
0x180053dd9  cmp     r14d, eax
0x180053ddc  jl      short loc_180053DF3
0x180053dde  lea     rdx, aTooManyAttache; "too many attached databases - max %d"
0x180053de5  mov     rcx, rsi
0x180053de8  call    sqlite3MPrintf
0x180053ded  mov     [rbp+arg_18], rax
0x180053df1  jmp     short loc_180053D81
0x180053df3  xor     ebx, ebx
0x180053df5  mov     rcx, rsi
0x180053df8  cmp     ebx, r14d
0x180053dfb  jge     short loc_180053E23
0x180053dfd  mov     r8, r15
0x180053e00  mov     edx, ebx
0x180053e02  call    sqlite3DbIsNamed
0x180053e07  test    eax, eax
0x180053e09  jnz     short loc_180053E0F
0x180053e0b  inc     ebx
0x180053e0d  jmp     short loc_180053DF5
0x180053e0f  mov     r8, r15
0x180053e12  lea     rdx, aDatabaseSIsAlr; "database %s is already in use"
0x180053e19  mov     rcx, rsi
0x180053e1c  call    sqlite3MPrintf
0x180053e21  jmp     short loc_180053DED
0x180053e23  mov     rdx, [rsi+20h]
0x180053e27  lea     rax, [rsi+2A0h]
0x180053e2e  cmp     rdx, rax
0x180053e31  jnz     short loc_180053E6D
0x180053e33  mov     edx, 60h ; '`'
0x180053e38  call    sqlite3DbMallocRawNN
0x180053e3d  mov     rdx, rax
0x180053e40  test    rax, rax
0x180053e43  jz      loc_180053DAF
0x180053e49  mov     rcx, [rsi+20h]
0x180053e4d  movups  xmm0, xmmword ptr [rcx]
0x180053e50  movups  xmmword ptr [rax], xmm0
0x180053e53  movups  xmm1, xmmword ptr [rcx+10h]
0x180053e57  movups  xmmword ptr [rax+10h], xmm1
0x180053e5b  movups  xmm0, xmmword ptr [rcx+20h]
0x180053e5f  movups  xmmword ptr [rax+20h], xmm0
0x180053e63  movups  xmm1, xmmword ptr [rcx+30h]
0x180053e67  movups  xmmword ptr [rax+30h], xmm1
0x180053e6b  jmp     short loc_180053E89
0x180053e6d  lea     eax, [r14+1]
0x180053e71  movsxd  r8, eax
0x180053e74  shl     r8, 5
0x180053e78  call    sqlite3DbRealloc
0x180053e7d  mov     rdx, rax
0x180053e80  test    rax, rax
0x180053e83  jz      loc_180053DAF
0x180053e89  movsxd  r14, dword ptr [rsi+28h]
0x180053e8d  lea     r9, [rbp+var_10]
0x180053e91  mov     [rsi+20h], rdx
0x180053e95  lea     r8, [rbp+arg_10]
0x180053e99  xorps   xmm0, xmm0
0x180053e9c  shl     r14, 5
0x180053ea0  add     r14, rdx
0x180053ea3  mov     rdx, [rbp+var_8]
0x180053ea7  movups  xmmword ptr [r14], xmm0
0x180053eab  movups  xmmword ptr [r14+10h], xmm0
0x180053eb0  mov     eax, [rsi+4Ch]
0x180053eb3  mov     rcx, [rsi]
0x180053eb6  mov     dword ptr [rbp+arg_10], eax
0x180053eb9  lea     rax, [rbp+var_20]
0x180053ebd  mov     [rsp+50h+var_28], rax
0x180053ec2  lea     rax, [rbp+var_18]
0x180053ec6  mov     [rsp+50h+var_30], rax
0x180053ecb  mov     rcx, [rcx+18h]
0x180053ecf  call    sqlite3ParseUri
0x180053ed4  test    eax, eax
0x180053ed6  jz      short loc_180053F09
0x180053ed8  mov     r15d, 7
0x180053ede  cmp     eax, r15d
0x180053ee1  jnz     short loc_180053EEB
0x180053ee3  mov     rcx, rsi
0x180053ee6  call    sqlite3OomFault
0x180053eeb  mov     rdx, [rbp+var_20]
0x180053eef  or      r8d, 0FFFFFFFFh
0x180053ef3  mov     rcx, r13
0x180053ef6  call    sqlite3_result_error
0x180053efb  mov     rcx, [rbp+var_20]
0x180053eff  call    sqlite3_free
0x180053f04  jmp     loc_180053DAF
0x180053f09  mov     eax, dword ptr [rbp+arg_10]
0x180053f0c  lea     r9, [r14+8]
0x180053f10  mov     r12, [rbp+var_18]
0x180053f14  bts     eax, 8
0x180053f18  mov     rcx, [rbp+var_10]
0x180053f1c  mov     r8, rsi
0x180053f1f  mov     dword ptr [rsp+50h+var_28], eax
0x180053f23  mov     rdx, r12
0x180053f26  mov     dword ptr [rsp+50h+var_30], edi
0x180053f2a  call    sqlite3BtreeOpen
0x180053f2f  inc     dword ptr [rsi+28h]
0x180053f32  mov     rdx, r15
0x180053f35  mov     rcx, rsi
0x180053f38  mov     edi, eax
0x180053f3a  call    sqlite3DbStrDup
0x180053f3f  mov     [r14], rax
0x180053f42  mov     byte ptr [rsi+6Fh], 0
0x180053f46  mov     r15d, 7
0x180053f4c  cmp     edi, 13h
0x180053f4f  jnz     short loc_180053F6D
0x180053f51  lea     rdx, aDatabaseIsAlre; "database is already attached"
0x180053f58  mov     rcx, rsi
0x180053f5b  lea     edi, [r15-6]
0x180053f5f  call    sqlite3MPrintf
0x180053f64  mov     [rbp+arg_18], rax
0x180053f68  jmp     loc_18005400E
0x180053f6d  test    edi, edi
0x180053f6f  jnz     loc_18005400E
0x180053f75  mov     rdx, [r14+8]
0x180053f79  mov     rcx, rsi
0x180053f7c  call    sqlite3SchemaGet
0x180053f81  mov     [r14+18h], rax
0x180053f85  mov     rcx, rax
0x180053f88  test    rax, rax
0x180053f8b  jnz     short loc_180053F92
0x180053f8d  mov     edi, r15d
0x180053f90  jmp     short loc_180053FB8
0x180053f92  cmp     byte ptr [rax+70h], 0
0x180053f96  jz      short loc_180053FB8
0x180053f98  mov     al, [rsi+64h]
0x180053f9b  cmp     [rcx+71h], al
0x180053f9e  jz      short loc_180053FB8
0x180053fa0  lea     rdx, aAttachedDataba; "attached databases must use the same te"...
0x180053fa7  mov     rcx, rsi
0x180053faa  call    sqlite3MPrintf
0x180053faf  mov     [rbp+arg_18], rax
0x180053fb3  mov     edi, 1
0x180053fb8  mov     rcx, [r14+8]
0x180053fbc  call    sqlite3BtreeEnter
0x180053fc1  mov     rax, [r14+8]
0x180053fc5  movzx   edx, byte ptr [rsi+69h]
0x180053fc9  mov     rcx, [rax+8]
0x180053fcd  mov     rcx, [rcx]
0x180053fd0  call    sqlite3PagerLockingMode
0x180053fd5  mov     rcx, [rsi+20h]
0x180053fd9  or      edx, 0FFFFFFFFh
0x180053fdc  mov     rbx, [r14+8]
0x180053fe0  mov     rcx, [rcx+8]
0x180053fe4  call    sqlite3BtreeSecureDelete
0x180053fe9  mov     edx, eax
0x180053feb  mov     rcx, rbx
0x180053fee  call    sqlite3BtreeSecureDelete
0x180053ff3  mov     edx, [rsi+30h]
0x180053ff6  mov     rcx, [r14+8]
0x180053ffa  and     edx, 38h
0x180053ffd  or      edx, 3
0x180054000  call    sqlite3BtreeSetPagerFlags
0x180054005  mov     rcx, [r14+8]
0x180054009  call    sqlite3BtreeLeave
0x18005400e  mov     byte ptr [r14+10h], 3
0x180054013  test    edi, edi
0x180054015  jnz     short loc_18005401F
0x180054017  cmp     qword ptr [r14], 0
0x18005401b  cmovz   edi, r15d
0x18005401f  mov     rcx, r12
0x180054022  call    sqlite3_free_filename
0x180054027  xor     r14d, r14d
0x18005402a  test    edi, edi
0x18005402c  jnz     short loc_180054068
0x18005402e  mov     rcx, rsi
0x180054031  call    sqlite3BtreeEnterAll
0x180054036  and     dword ptr [rsi+2Ch], 0FFFFFFEFh
0x18005403a  test    byte ptr [rsi+0C8h], 4
0x180054041  mov     [rsi+0C4h], r14b
0x180054048  jnz     short loc_180054058
0x18005404a  lea     rdx, [rbp+arg_18]
0x18005404e  mov     rcx, rsi
0x180054051  call    sqlite3Init
0x180054056  mov     edi, eax
0x180054058  mov     rcx, rsi
0x18005405b  call    sqlite3BtreeLeaveAll
0x180054060  test    edi, edi
0x180054062  jz      loc_180053DAF
0x180054068  test    byte ptr [rsi+0C8h], 4
0x18005406f  jnz     loc_180053D7D
0x180054075  movsxd  rax, dword ptr [rsi+28h]
0x180054079  mov     rbx, rax
0x18005407c  shl     rbx, 5
0x180054080  lea     r14d, [rax-1]
0x180054084  mov     rax, [rsi+20h]
0x180054088  mov     rcx, [rbx+rax-18h]
0x18005408d  test    rcx, rcx
0x180054090  jz      short loc_1800540B1
0x180054092  call    sqlite3BtreeClose
0x180054097  mov     rax, [rsi+20h]
0x18005409b  mov     qword ptr [rbx+rax-18h], 0
0x1800540a4  mov     rax, [rsi+20h]
0x1800540a8  mov     qword ptr [rbx+rax-8], 0
0x1800540b1  mov     rcx, rsi
0x1800540b4  call    sqlite3ResetAllSchemasOfConnection
0x1800540b9  mov     [rsi+28h], r14d
0x1800540bd  cmp     edi, r15d
0x1800540c0  jz      short loc_1800540E7
0x1800540c2  cmp     edi, 0C0Ah
0x1800540c8  jz      short loc_1800540E7
0x1800540ca  mov     rax, [rbp+arg_18]
0x1800540ce  test    rax, rax
0x1800540d1  jnz     loc_180053D86
  ... truncated ...
```
