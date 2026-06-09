# attachFunc

- ea: `0x180069970`
- end: `0x180069e0f`
- name: `attachFunc`
- size: `1183`
- prototype: `_OWORD *__fastcall(__int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x18000126c`
- `0x180001ef4`
- `0x180004dfc`
- `0x180005ab4`
- `0x180005bc0`
- `0x18000a9e0`
- `0x18000aac0`
- `0x180010390`
- `0x1800151b4`
- `0x180023b30`
- `0x180024440`
- `0x1800256c4`
- `0x180028540`
- `0x18003fe98`
- `0x180046938`
- `0x180047bbc`
- `0x180047c2c`
- `0x180048d20`
- `0x18005a7a0`
- `0x18005bbe8`
- `0x180064384`
- `0x180064ef0`
- `0x180065930`
- `0x1800675fc`
- `0x180067f68`
- `0x180068380`
- `0x180069970`
- `0x18008f3f0`

## string_xrefs

- `0x180069b12`: `database %s is already in use`
- `0x180069c51`: `database is already attached`
- `0x180069ddb`: `unable to open database: %s`

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
  __int64 *v12; // rbx
  __int64 v13; // rax
  __int64 *v14; // r15
  __int64 *v15; // rcx
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
  __int64 *v29; // rdx
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
  __int64 v40; // [rsp+30h] [rbp-20h] BYREF
  __int64 v41; // [rsp+38h] [rbp-18h] BYREF
  __int64 v42; // [rsp+40h] [rbp-10h] BYREF
  __int64 *v43; // [rsp+48h] [rbp-8h]
  __int64 v44; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v45; // [rsp+A8h] [rbp+58h] BYREF

  v5 = sqlite3_context_db_handle();
  v6 = *a3;
  LOBYTE(v7) = 1;
  v41 = 0;
  v8 = 0;
  v40 = 0;
  v45 = 0;
  v9 = v5;
  v42 = 0;
  v10 = sqlite3ValueText(v6, v7);
  LOBYTE(v11) = 1;
  v12 = (__int64 *)v10;
  v13 = sqlite3ValueText(a3[1], v11);
  v14 = qword_18009EEF0;
  v15 = qword_18009EEF0;
  if ( v12 )
    v15 = v12;
  v43 = v15;
  if ( v13 )
    v14 = (__int64 *)v13;
  if ( (*(_BYTE *)(v9 + 200) & 4) != 0 )
  {
    v44 = 0;
    result = (_OWORD *)sqlite3_vfs_find("memdb");
    if ( !result )
      return result;
    v17 = sqlite3BtreeOpen(result, "x", v9, &v44, 0, 256);
    if ( v17 )
      goto LABEL_13;
    v18 = v44;
    v19 = sqlite3SchemaGet(v9, v44);
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
      v45 = (__int64)result;
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
    v29 = v43;
    *(_OWORD *)v20 = 0;
    *(_OWORD *)(v20 + 16) = 0;
    v30 = *(_QWORD *)v9;
    LODWORD(v44) = *(_DWORD *)(v9 + 76);
    v31 = sqlite3ParseUri(*(_QWORD *)(v30 + 24), v29, &v44, &v42, &v41, &v40);
    if ( v31 )
    {
      if ( v31 == 7 )
        sqlite3OomFault(v9);
      sqlite3_result_error(a1, v40, 0xFFFFFFFFLL);
      return (_OWORD *)sqlite3_free(v40);
    }
    v8 = v41;
    v32 = sqlite3BtreeOpen(v42, v41, v9, v20 + 8, 0, (unsigned int)v44 | 0x100);
    ++*(_DWORD *)(v9 + 40);
    v17 = v32;
    *(_QWORD *)v20 = sqlite3DbStrDup(v9, v14);
  }
  *(_BYTE *)(v9 + 111) = 0;
  if ( v17 == 19 )
  {
    v17 = 1;
    v45 = sqlite3MPrintf(v9, "database is already attached");
  }
  else if ( !v17 )
  {
    v33 = sqlite3SchemaGet(v9, *(_QWORD *)(v20 + 8));
    *(_QWORD *)(v20 + 24) = v33;
    if ( v33 )
    {
      if ( *(_BYTE *)(v33 + 112) && *(_BYTE *)(v33 + 113) != *(_BYTE *)(v9 + 100) )
      {
        v45 = sqlite3MPrintf(v9, "attached databases must use the same text encoding as main database");
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
    v17 = sqlite3Init(v9, &v45);
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
        sqlite3DbFree(v9, v45);
        result = (_OWORD *)sqlite3MPrintf(v9, "out of memory");
      }
      else
      {
        result = (_OWORD *)v45;
        if ( v45 )
        {
LABEL_15:
          sqlite3_result_error(a1, result, 0xFFFFFFFFLL);
          result = (_OWORD *)sqlite3DbFree(v9, v45);
LABEL_16:
          if ( v17 )
            return (_OWORD *)sqlite3_result_error_code(a1, v17);
          return result;
        }
        result = (_OWORD *)sqlite3MPrintf(v9, "unable to open database: %s", v43);
      }
      goto LABEL_21;
    }
LABEL_13:
    result = (_OWORD *)v45;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x180069970  mov     [rsp-38h+arg_0], rbx
0x180069975  push    rbp
0x180069976  push    rsi
0x180069977  push    rdi
0x180069978  push    r12
0x18006997a  push    r13
0x18006997c  push    r14
0x18006997e  push    r15
0x180069980  mov     rbp, rsp
0x180069983  sub     rsp, 50h
0x180069987  mov     rdi, r8
0x18006998a  mov     r13, rcx
0x18006998d  call    sqlite3_context_db_handle
0x180069992  mov     rcx, [rdi]
0x180069995  xor     r14d, r14d
0x180069998  mov     dl, 1
0x18006999a  mov     [rbp+var_18], r14
0x18006999e  mov     r12d, r14d
0x1800699a1  mov     [rbp+var_20], r14
0x1800699a5  mov     [rbp+arg_18], r14
0x1800699a9  mov     rsi, rax
0x1800699ac  mov     [rbp+var_10], r14
0x1800699b0  call    sqlite3ValueText
0x1800699b5  mov     rcx, [rdi+8]
0x1800699b9  mov     dl, 1
0x1800699bb  mov     rbx, rax
0x1800699be  call    sqlite3ValueText
0x1800699c3  test    rbx, rbx
0x1800699c6  lea     r15, qword_18009EEF0
0x1800699cd  mov     rcx, r15
0x1800699d0  cmovnz  rcx, rbx
0x1800699d4  test    rax, rax
0x1800699d7  mov     [rbp+var_8], rcx
0x1800699db  cmovnz  r15, rax
0x1800699df  test    byte ptr [rsi+0C8h], 4
0x1800699e6  jz      loc_180069AC7
0x1800699ec  lea     rcx, aMemdb; "memdb"
0x1800699f3  mov     [rbp+arg_10], r14
0x1800699f7  call    sqlite3_vfs_find
0x1800699fc  test    rax, rax
0x1800699ff  jz      loc_180069AAF
0x180069a05  mov     dword ptr [rsp+50h+var_28], 100h
0x180069a0d  lea     r9, [rbp+arg_10]
0x180069a11  mov     r8, rsi
0x180069a14  mov     dword ptr [rsp+50h+var_30], r14d
0x180069a19  lea     rdx, asc_1800A2E24; "x"
0x180069a20  mov     rcx, rax
0x180069a23  call    sqlite3BtreeOpen
0x180069a28  mov     edi, eax
0x180069a2a  test    eax, eax
0x180069a2c  jnz     short loc_180069A7D
0x180069a2e  mov     rbx, [rbp+arg_10]
0x180069a32  mov     rcx, rsi
0x180069a35  mov     rdx, rbx
0x180069a38  call    sqlite3SchemaGet
0x180069a3d  mov     r15, rax
0x180069a40  test    rax, rax
0x180069a43  jz      short loc_180069A70
0x180069a45  movzx   r14d, byte ptr [rsi+0C4h]
0x180069a4d  shl     r14, 5
0x180069a51  add     r14, [rsi+20h]
0x180069a55  mov     rcx, [r14+8]
0x180069a59  test    rcx, rcx
0x180069a5c  jz      short loc_180069A63
0x180069a5e  call    sqlite3BtreeClose
0x180069a63  mov     [r14+8], rbx
0x180069a67  mov     [r14+18h], r15
0x180069a6b  jmp     loc_180069C42
0x180069a70  mov     rcx, rbx
0x180069a73  call    sqlite3BtreeClose
0x180069a78  mov     edi, 7
0x180069a7d  mov     rax, [rbp+arg_18]
0x180069a81  test    rax, rax
0x180069a84  jz      short loc_180069AA1
0x180069a86  or      r8d, 0FFFFFFFFh
0x180069a8a  mov     rdx, rax
0x180069a8d  mov     rcx, r13
0x180069a90  call    sqlite3_result_error
0x180069a95  mov     rdx, [rbp+arg_18]
0x180069a99  mov     rcx, rsi
0x180069a9c  call    sqlite3DbFree
0x180069aa1  test    edi, edi
0x180069aa3  jz      short loc_180069AAF
0x180069aa5  mov     edx, edi
0x180069aa7  mov     rcx, r13
0x180069aaa  call    sqlite3_result_error_code
0x180069aaf  mov     rbx, [rsp+50h+arg_0]
0x180069ab7  add     rsp, 50h
0x180069abb  pop     r15
0x180069abd  pop     r14
0x180069abf  pop     r13
0x180069ac1  pop     r12
0x180069ac3  pop     rdi
0x180069ac4  pop     rsi
0x180069ac5  pop     rbp
0x180069ac6  retn
0x180069ac7  mov     r8d, [rsi+0A4h]
0x180069ace  mov     edi, r14d
0x180069ad1  mov     r14d, [rsi+28h]
0x180069ad5  lea     eax, [r8+2]
0x180069ad9  cmp     r14d, eax
0x180069adc  jl      short loc_180069AF3
0x180069ade  lea     rdx, aTooManyAttache; "too many attached databases - max %d"
0x180069ae5  mov     rcx, rsi
0x180069ae8  call    sqlite3MPrintf
0x180069aed  mov     [rbp+arg_18], rax
0x180069af1  jmp     short loc_180069A81
0x180069af3  xor     ebx, ebx
0x180069af5  mov     rcx, rsi
0x180069af8  cmp     ebx, r14d
0x180069afb  jge     short loc_180069B23
0x180069afd  mov     r8, r15
0x180069b00  mov     edx, ebx
0x180069b02  call    sqlite3DbIsNamed
0x180069b07  test    eax, eax
0x180069b09  jnz     short loc_180069B0F
0x180069b0b  inc     ebx
0x180069b0d  jmp     short loc_180069AF5
0x180069b0f  mov     r8, r15
0x180069b12  lea     rdx, aDatabaseSIsAlr; "database %s is already in use"
0x180069b19  mov     rcx, rsi
0x180069b1c  call    sqlite3MPrintf
0x180069b21  jmp     short loc_180069AED
0x180069b23  mov     rdx, [rsi+20h]
0x180069b27  lea     rax, [rsi+2A0h]
0x180069b2e  cmp     rdx, rax
0x180069b31  jnz     short loc_180069B6D
0x180069b33  mov     edx, 60h ; '`'
0x180069b38  call    sqlite3DbMallocRawNN
0x180069b3d  mov     rdx, rax
0x180069b40  test    rax, rax
0x180069b43  jz      loc_180069AAF
0x180069b49  mov     rcx, [rsi+20h]
0x180069b4d  movups  xmm0, xmmword ptr [rcx]
0x180069b50  movups  xmmword ptr [rax], xmm0
0x180069b53  movups  xmm1, xmmword ptr [rcx+10h]
0x180069b57  movups  xmmword ptr [rax+10h], xmm1
0x180069b5b  movups  xmm0, xmmword ptr [rcx+20h]
0x180069b5f  movups  xmmword ptr [rax+20h], xmm0
0x180069b63  movups  xmm1, xmmword ptr [rcx+30h]
0x180069b67  movups  xmmword ptr [rax+30h], xmm1
0x180069b6b  jmp     short loc_180069B89
0x180069b6d  lea     eax, [r14+1]
0x180069b71  movsxd  r8, eax
0x180069b74  shl     r8, 5
0x180069b78  call    sqlite3DbRealloc
0x180069b7d  mov     rdx, rax
0x180069b80  test    rax, rax
0x180069b83  jz      loc_180069AAF
0x180069b89  movsxd  r14, dword ptr [rsi+28h]
0x180069b8d  lea     r9, [rbp+var_10]
0x180069b91  mov     [rsi+20h], rdx
0x180069b95  lea     r8, [rbp+arg_10]
0x180069b99  xorps   xmm0, xmm0
0x180069b9c  shl     r14, 5
0x180069ba0  add     r14, rdx
0x180069ba3  mov     rdx, [rbp+var_8]
0x180069ba7  movups  xmmword ptr [r14], xmm0
0x180069bab  movups  xmmword ptr [r14+10h], xmm0
0x180069bb0  mov     eax, [rsi+4Ch]
0x180069bb3  mov     rcx, [rsi]
0x180069bb6  mov     dword ptr [rbp+arg_10], eax
0x180069bb9  lea     rax, [rbp+var_20]
0x180069bbd  mov     [rsp+50h+var_28], rax
0x180069bc2  lea     rax, [rbp+var_18]
0x180069bc6  mov     [rsp+50h+var_30], rax
0x180069bcb  mov     rcx, [rcx+18h]
0x180069bcf  call    sqlite3ParseUri
0x180069bd4  test    eax, eax
0x180069bd6  jz      short loc_180069C09
0x180069bd8  mov     r15d, 7
0x180069bde  cmp     eax, r15d
0x180069be1  jnz     short loc_180069BEB
0x180069be3  mov     rcx, rsi
0x180069be6  call    sqlite3OomFault
0x180069beb  mov     rdx, [rbp+var_20]
0x180069bef  or      r8d, 0FFFFFFFFh
0x180069bf3  mov     rcx, r13
0x180069bf6  call    sqlite3_result_error
0x180069bfb  mov     rcx, [rbp+var_20]
0x180069bff  call    sqlite3_free
0x180069c04  jmp     loc_180069AAF
0x180069c09  mov     eax, dword ptr [rbp+arg_10]
0x180069c0c  lea     r9, [r14+8]
0x180069c10  mov     r12, [rbp+var_18]
0x180069c14  bts     eax, 8
0x180069c18  mov     rcx, [rbp+var_10]
0x180069c1c  mov     r8, rsi
0x180069c1f  mov     dword ptr [rsp+50h+var_28], eax
0x180069c23  mov     rdx, r12
0x180069c26  mov     dword ptr [rsp+50h+var_30], edi
0x180069c2a  call    sqlite3BtreeOpen
0x180069c2f  inc     dword ptr [rsi+28h]
0x180069c32  mov     rdx, r15
0x180069c35  mov     rcx, rsi
0x180069c38  mov     edi, eax
0x180069c3a  call    sqlite3DbStrDup
0x180069c3f  mov     [r14], rax
0x180069c42  mov     byte ptr [rsi+6Fh], 0
0x180069c46  mov     r15d, 7
0x180069c4c  cmp     edi, 13h
0x180069c4f  jnz     short loc_180069C6D
0x180069c51  lea     rdx, aDatabaseIsAlre; "database is already attached"
0x180069c58  mov     rcx, rsi
0x180069c5b  lea     edi, [r15-6]
0x180069c5f  call    sqlite3MPrintf
0x180069c64  mov     [rbp+arg_18], rax
0x180069c68  jmp     loc_180069D0E
0x180069c6d  test    edi, edi
0x180069c6f  jnz     loc_180069D0E
0x180069c75  mov     rdx, [r14+8]
0x180069c79  mov     rcx, rsi
0x180069c7c  call    sqlite3SchemaGet
0x180069c81  mov     [r14+18h], rax
0x180069c85  mov     rcx, rax
0x180069c88  test    rax, rax
0x180069c8b  jnz     short loc_180069C92
0x180069c8d  mov     edi, r15d
0x180069c90  jmp     short loc_180069CB8
0x180069c92  cmp     byte ptr [rax+70h], 0
0x180069c96  jz      short loc_180069CB8
0x180069c98  mov     al, [rsi+64h]
0x180069c9b  cmp     [rcx+71h], al
0x180069c9e  jz      short loc_180069CB8
0x180069ca0  lea     rdx, aAttachedDataba; "attached databases must use the same te"...
0x180069ca7  mov     rcx, rsi
0x180069caa  call    sqlite3MPrintf
0x180069caf  mov     [rbp+arg_18], rax
0x180069cb3  mov     edi, 1
0x180069cb8  mov     rcx, [r14+8]
0x180069cbc  call    sqlite3BtreeEnter
0x180069cc1  mov     rax, [r14+8]
0x180069cc5  movzx   edx, byte ptr [rsi+69h]
0x180069cc9  mov     rcx, [rax+8]
0x180069ccd  mov     rcx, [rcx]
0x180069cd0  call    sqlite3PagerLockingMode
0x180069cd5  mov     rcx, [rsi+20h]
0x180069cd9  or      edx, 0FFFFFFFFh
0x180069cdc  mov     rbx, [r14+8]
0x180069ce0  mov     rcx, [rcx+8]
0x180069ce4  call    sqlite3BtreeSecureDelete
0x180069ce9  mov     edx, eax
0x180069ceb  mov     rcx, rbx
0x180069cee  call    sqlite3BtreeSecureDelete
0x180069cf3  mov     edx, [rsi+30h]
0x180069cf6  mov     rcx, [r14+8]
0x180069cfa  and     edx, 38h
0x180069cfd  or      edx, 3
0x180069d00  call    sqlite3BtreeSetPagerFlags
0x180069d05  mov     rcx, [r14+8]
0x180069d09  call    sqlite3BtreeLeave
0x180069d0e  mov     byte ptr [r14+10h], 3
0x180069d13  test    edi, edi
0x180069d15  jnz     short loc_180069D1F
0x180069d17  cmp     qword ptr [r14], 0
0x180069d1b  cmovz   edi, r15d
0x180069d1f  mov     rcx, r12
0x180069d22  call    sqlite3_free_filename
0x180069d27  xor     r14d, r14d
0x180069d2a  test    edi, edi
0x180069d2c  jnz     short loc_180069D68
0x180069d2e  mov     rcx, rsi
0x180069d31  call    sqlite3BtreeEnterAll
0x180069d36  and     dword ptr [rsi+2Ch], 0FFFFFFEFh
0x180069d3a  test    byte ptr [rsi+0C8h], 4
0x180069d41  mov     [rsi+0C4h], r14b
0x180069d48  jnz     short loc_180069D58
0x180069d4a  lea     rdx, [rbp+arg_18]
0x180069d4e  mov     rcx, rsi
0x180069d51  call    sqlite3Init
0x180069d56  mov     edi, eax
0x180069d58  mov     rcx, rsi
0x180069d5b  call    sqlite3BtreeLeaveAll
0x180069d60  test    edi, edi
0x180069d62  jz      loc_180069AAF
0x180069d68  test    byte ptr [rsi+0C8h], 4
0x180069d6f  jnz     loc_180069A7D
0x180069d75  movsxd  rax, dword ptr [rsi+28h]
0x180069d79  mov     rbx, rax
0x180069d7c  shl     rbx, 5
0x180069d80  lea     r14d, [rax-1]
0x180069d84  mov     rax, [rsi+20h]
0x180069d88  mov     rcx, [rbx+rax-18h]
0x180069d8d  test    rcx, rcx
0x180069d90  jz      short loc_180069DB1
0x180069d92  call    sqlite3BtreeClose
0x180069d97  mov     rax, [rsi+20h]
0x180069d9b  mov     qword ptr [rbx+rax-18h], 0
0x180069da4  mov     rax, [rsi+20h]
0x180069da8  mov     qword ptr [rbx+rax-8], 0
0x180069db1  mov     rcx, rsi
0x180069db4  call    sqlite3ResetAllSchemasOfConnection
0x180069db9  mov     [rsi+28h], r14d
0x180069dbd  cmp     edi, r15d
0x180069dc0  jz      short loc_180069DE7
0x180069dc2  cmp     edi, 0C0Ah
0x180069dc8  jz      short loc_180069DE7
0x180069dca  mov     rax, [rbp+arg_18]
0x180069dce  test    rax, rax
0x180069dd1  jnz     loc_180069A86
  ... truncated ...
```
