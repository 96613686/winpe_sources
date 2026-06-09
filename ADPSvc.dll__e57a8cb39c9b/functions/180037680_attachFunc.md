# attachFunc

- ea: `0x180037680`
- end: `0x180037c80`
- name: `attachFunc`
- size: `1536`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `broker_com_uri`

## callees

- `0x180037680`
- `0x18003aafc`
- `0x18003adec`
- `0x18003ae40`
- `0x18006a7c8`
- `0x18006b4d4`
- `0x18006c5c8`
- `0x18006d044`
- `0x18006d2a8`
- `0x18006ed68`
- `0x18006eebc`
- `0x1800716fc`
- `0x18007175c`
- `0x1800717b0`
- `0x180071954`
- `0x180071a38`
- `0x18007dc18`
- `0x180080b64`
- `0x180081a3c`
- `0x180083b60`
- `0x18008a024`
- `0x18008b698`
- `0x180092290`
- `0x18009b4ec`
- `0x1800a98a0`
- `0x1800a9930`
- `0x1800ab230`
- `0x1800ae6c0`
- `0x1800ae720`
- `0x1800aea30`
- `0x1800b2174`

## string_xrefs

- `0x180037895`: `database %s is already in use`
- `0x180037995`: `database is already attached`
- `0x180037c47`: `unable to open database: %s`

## pseudocode

```c
_OWORD *__fastcall attachFunc(__int64 *a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  __int64 *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rdx
  const char *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  const wchar_t *v15; // r12
  const char *v16; // r15
  unsigned int v17; // ebx
  _OWORD *result; // rax
  unsigned int v19; // esi
  __int64 v20; // r9
  __int64 v21; // rbx
  __int64 v22; // r15
  __int64 v23; // r14
  __int64 v24; // rcx
  __int64 v25; // r15
  int v26; // r8d
  int v27; // r14d
  __int64 *v28; // rdx
  _OWORD *v29; // rdx
  _OWORD *v30; // rcx
  __int64 v31; // r14
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rbx
  unsigned int v44; // eax
  __int64 v45; // rcx
  bool v46; // zf
  _QWORD *v47; // r14
  __int64 v48; // rax
  __int64 v49; // r9
  __int64 v50; // r8
  unsigned int v51; // ebx
  __int64 v52; // rax
  __int64 v53; // rbx
  int v54; // r14d
  __int64 v55; // rcx
  __int64 v56; // [rsp+20h] [rbp-30h]
  __int64 v57; // [rsp+30h] [rbp-20h] BYREF
  __int64 v58; // [rsp+38h] [rbp-18h] BYREF
  __int64 v59; // [rsp+40h] [rbp-10h] BYREF
  const char *v60; // [rsp+48h] [rbp-8h]
  __int64 v61; // [rsp+90h] [rbp+40h] BYREF
  _QWORD *v62; // [rsp+A0h] [rbp+50h]
  __int64 v63; // [rsp+A8h] [rbp+58h] BYREF

  v62 = a3;
  v3 = *a1;
  v58 = 0;
  v5 = *a3;
  LOBYTE(a2) = 1;
  v57 = 0;
  v7 = *(__int64 **)(v3 + 24);
  v63 = 0;
  v59 = 0;
  v8 = sqlite3ValueText(v5, a2);
  LOBYTE(v9) = 1;
  v10 = (const char *)v8;
  v11 = sqlite3ValueText(a3[1], v9);
  v15 = &Src;
  v16 = (const char *)&Src;
  if ( v10 )
    v16 = v10;
  v17 = 0;
  v60 = v16;
  if ( v11 )
    v15 = (const wchar_t *)v11;
  if ( (v7[25] & 4) != 0 )
  {
    v61 = 0;
    result = (_OWORD *)sqlite3_vfs_find("memdb", v12, v13, v14);
    if ( !result )
      return result;
    v19 = sqlite3BtreeOpen(result, "x", v7, &v61, 0, 256);
    if ( v19 )
      goto LABEL_13;
    v21 = v61;
    v22 = sqlite3SchemaGet(v7, v61);
    if ( !v22 )
    {
      sqlite3BtreeClose(v21);
      v19 = 7;
      goto LABEL_13;
    }
    v23 = v7[4] + 32LL * *((unsigned __int8 *)v7 + 196);
    v24 = *(_QWORD *)(v23 + 8);
    if ( v24 )
      sqlite3BtreeClose(v24);
    *(_QWORD *)(v23 + 8) = v21;
    *(_QWORD *)(v23 + 24) = v22;
    v25 = v58;
    goto LABEL_37;
  }
  v26 = *((_DWORD *)v7 + 41);
  v19 = 0;
  v27 = *((_DWORD *)v7 + 10);
  if ( v27 >= v26 + 2 )
  {
    result = (_OWORD *)sqlite3MPrintf(v7, "too many attached databases - max %d", v26);
LABEL_22:
    v63 = (__int64)result;
LABEL_14:
    if ( !result )
    {
LABEL_17:
      if ( v19 )
        return (_OWORD *)sqlite3_result_error_code(a1, v19);
      return result;
    }
LABEL_15:
    *((_DWORD *)a1 + 9) = 1;
    LOBYTE(v20) = 1;
    result = (_OWORD *)sqlite3VdbeMemSetStr(*a1, result, -1, v20, -1);
    if ( v63 )
      result = (_OWORD *)sqlite3DbFreeNN(v7);
    goto LABEL_17;
  }
  if ( v27 > 0 )
  {
    while ( !(unsigned int)sqlite3DbIsNamed(v7, v17, v15) )
    {
      if ( (int)++v17 >= v27 )
        goto LABEL_26;
    }
    result = (_OWORD *)sqlite3MPrintf(v7, "database %s is already in use", v15);
    goto LABEL_22;
  }
LABEL_26:
  v28 = (__int64 *)v7[4];
  if ( v28 == v7 + 84 )
  {
    result = (_OWORD *)sqlite3DbMallocRawNN(v7, 96);
    v29 = result;
    if ( !result )
      return result;
    v30 = (_OWORD *)v7[4];
    *result = *v30;
    result[1] = v30[1];
    result[2] = v30[2];
    result[3] = v30[3];
  }
  else
  {
    result = (_OWORD *)sqlite3DbRealloc(v7, v28, 32LL * (v27 + 1));
    v29 = result;
    if ( !result )
      return result;
  }
  v31 = *((int *)v7 + 10);
  v7[4] = (__int64)v29;
  v23 = (__int64)&v29[2 * v31];
  *(_OWORD *)v23 = 0;
  *(_OWORD *)(v23 + 16) = 0;
  v32 = *v7;
  LODWORD(v61) = *((_DWORD *)v7 + 19);
  v33 = sqlite3ParseUri(*(const char **)(v32 + 24), v16, (unsigned int *)&v61, &v59, &v58, &v57);
  if ( v33 )
  {
    if ( v33 == 7 )
      sqlite3OomFault(v7);
    v35 = v57;
    v36 = *a1;
    LOBYTE(v34) = 1;
    *((_DWORD *)a1 + 9) = 1;
    sqlite3VdbeMemSetStr(v36, v35, -1, v34, -1);
    return (_OWORD *)sqlite3_free(v57);
  }
  v25 = v58;
  LODWORD(v56) = 0;
  v37 = sqlite3BtreeOpen(v59, v58, v7, v23 + 8, v56, (unsigned int)v61 | 0x100);
  ++*((_DWORD *)v7 + 10);
  v19 = v37;
  *(_QWORD *)v23 = sqlite3DbStrDup(v7, v15);
LABEL_37:
  *((_BYTE *)v7 + 111) = 0;
  if ( v19 == 19 )
  {
    v19 = 1;
    v63 = sqlite3MPrintf(v7, "database is already attached");
  }
  else if ( !v19 )
  {
    v38 = sqlite3SchemaGet(v7, *(_QWORD *)(v23 + 8));
    *(_QWORD *)(v23 + 24) = v38;
    if ( v38 )
    {
      if ( *(_BYTE *)(v38 + 112) && *(_BYTE *)(v38 + 113) != *((_BYTE *)v7 + 100) )
      {
        v63 = sqlite3MPrintf(v7, "attached databases must use the same text encoding as main database");
        v19 = 1;
      }
    }
    else
    {
      v19 = 7;
    }
    v39 = *(_QWORD *)(v23 + 8);
    if ( *(_BYTE *)(v39 + 17) )
    {
      ++*(_DWORD *)(v39 + 20);
      if ( !*(_BYTE *)(v39 + 18) )
        btreeLockCarefully(v39);
    }
    v40 = *(__int64 **)(*(_QWORD *)(v23 + 8) + 8LL);
    v41 = *v40;
    if ( !*(_BYTE *)(*v40 + 16) )
    {
      v42 = *(_QWORD *)(v41 + 328);
      if ( !v42 || *(_BYTE *)(v42 + 63) != 2 )
        *(_BYTE *)(v41 + 8) = *((_BYTE *)v7 + 105);
    }
    v43 = *(_QWORD *)(v23 + 8);
    v44 = sqlite3BtreeSecureDelete(*(_QWORD *)(v7[4] + 8), 0xFFFFFFFFLL);
    sqlite3BtreeSecureDelete(v43, v44);
    sqlite3BtreeSetPagerFlags(*(_QWORD *)(v23 + 8), v7[6] & 0x38 | 3);
    v45 = *(_QWORD *)(v23 + 8);
    if ( *(_BYTE *)(v45 + 17) )
    {
      v46 = (*(_DWORD *)(v45 + 20))-- == 1;
      if ( v46 )
        unlockBtreeMutex();
    }
  }
  *(_BYTE *)(v23 + 16) = 3;
  if ( !v19 )
  {
    if ( *(_QWORD *)v23 )
    {
      v47 = v62;
      if ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(v62[2] + 20LL) & 0x3F)) == 1
        || *((_BYTE *)qword_1800FE430 + (*(_WORD *)(v62[2] + 20LL) & 0x3F)) == 2 )
      {
        v63 = sqlite3DbStrDup(v7, "Invalid key value");
        v19 = 1;
        goto LABEL_72;
      }
      if ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(v62[2] + 20LL) & 0x3F)) == 3
        || *((_BYTE *)qword_1800FE430 + (*(_WORD *)(v62[2] + 20LL) & 0x3F)) == 4 )
      {
        v51 = sqlite3_value_bytes(v62[2]);
        v52 = sqlite3_value_blob(v47[2]);
        v19 = sqlite3CodecAttach(v7, (unsigned int)(*((_DWORD *)v7 + 10) - 1), v52, v51);
        goto LABEL_72;
      }
      if ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(v62[2] + 20LL) & 0x3F)) != 5
        || (unsigned int)sqlite3CodecQueryParameters(v7, v15, v25) )
      {
        goto LABEL_72;
      }
      v48 = *(_QWORD *)(**(_QWORD **)(*(_QWORD *)(v7[4] + 8) + 8LL) + 304LL);
      if ( v48 && *(_QWORD *)(v48 + 8) )
      {
        v49 = 32;
        v50 = v48 + 56;
      }
      else
      {
        if ( (int)sqlite3BtreeGetRequestedReserve(*(_QWORD *)(v7[4] + 8)) <= 0 )
          goto LABEL_72;
        v49 = 0;
        v50 = 0;
      }
      v19 = sqlite3CodecAttach(v7, (unsigned int)(*((_DWORD *)v7 + 10) - 1), v50, v49);
      goto LABEL_72;
    }
    v19 = 7;
  }
LABEL_72:
  result = (_OWORD *)sqlite3_free_filename(v25);
  if ( v19 )
    goto LABEL_80;
  if ( !*((_BYTE *)v7 + 111) )
    result = (_OWORD *)btreeEnterAll(v7);
  *((_DWORD *)v7 + 11) &= ~0x10u;
  v46 = (v7[25] & 4) == 0;
  *((_BYTE *)v7 + 196) = 0;
  if ( v46 )
  {
    result = (_OWORD *)sqlite3Init(v7, &v63);
    v19 = (unsigned int)result;
  }
  if ( !*((_BYTE *)v7 + 111) )
    result = (_OWORD *)btreeLeaveAll(v7);
  if ( v19 )
  {
LABEL_80:
    if ( (v7[25] & 4) == 0 )
    {
      v53 = 32LL * *((int *)v7 + 10);
      v54 = *((_DWORD *)v7 + 10) - 1;
      v55 = *(_QWORD *)(v7[4] + v53 - 24);
      if ( v55 )
      {
        sqlite3BtreeClose(v55);
        *(_QWORD *)(v7[4] + v53 - 24) = 0;
        *(_QWORD *)(v7[4] + v53 - 8) = 0;
      }
      sqlite3ResetAllSchemasOfConnection(v7);
      *((_DWORD *)v7 + 10) = v54;
      if ( v19 == 7 || v19 == 3082 )
      {
        sqlite3OomFault(v7);
        if ( v63 )
          sqlite3DbFreeNN(v7);
        result = (_OWORD *)sqlite3MPrintf(v7, "out of memory");
      }
      else
      {
        result = (_OWORD *)v63;
        if ( v63 )
          goto LABEL_15;
        result = (_OWORD *)sqlite3MPrintf(v7, "unable to open database: %s", v60);
      }
      goto LABEL_22;
    }
LABEL_13:
    result = (_OWORD *)v63;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x180037680  mov     [rsp-38h+arg_8], rbx
0x180037685  mov     [rsp-38h+arg_10], r8
0x18003768a  push    rbp
0x18003768b  push    rsi
0x18003768c  push    rdi
0x18003768d  push    r12
0x18003768f  push    r13
0x180037691  push    r14
0x180037693  push    r15
0x180037695  mov     rbp, rsp
0x180037698  sub     rsp, 50h
0x18003769c  mov     rax, [rcx]
0x18003769f  xor     r14d, r14d
0x1800376a2  mov     r13, rcx
0x1800376a5  mov     [rbp+var_18], r14
0x1800376a9  mov     rcx, [r8]
0x1800376ac  mov     dl, 1
0x1800376ae  mov     rsi, r8
0x1800376b1  mov     [rbp+var_20], r14
0x1800376b5  mov     rdi, [rax+18h]
0x1800376b9  mov     [rbp+arg_18], r14
0x1800376bd  mov     [rbp+var_10], r14
0x1800376c1  call    sqlite3ValueText
0x1800376c6  mov     rcx, [rsi+8]
0x1800376ca  mov     dl, 1
0x1800376cc  mov     rbx, rax
0x1800376cf  call    sqlite3ValueText
0x1800376d4  test    rbx, rbx
0x1800376d7  lea     r12, Src
0x1800376de  mov     r15, r12
0x1800376e1  cmovnz  r15, rbx
0x1800376e5  xor     ebx, ebx
0x1800376e7  test    rax, rax
0x1800376ea  mov     [rbp+var_8], r15
0x1800376ee  cmovnz  r12, rax
0x1800376f2  test    byte ptr [rdi+0C8h], 4
0x1800376f9  jz      loc_1800377F8
0x1800376ff  lea     rcx, aMemdb; "memdb"
0x180037706  mov     [rbp+arg_0], rbx
0x18003770a  call    sqlite3_vfs_find
0x18003770f  test    rax, rax
0x180037712  jz      loc_1800377E0
0x180037718  mov     dword ptr [rsp+50h+var_28], 100h
0x180037720  lea     r9, [rbp+arg_0]
0x180037724  mov     r8, rdi
0x180037727  mov     dword ptr [rsp+50h+var_30], ebx
0x18003772b  lea     rdx, asc_1800F6650; "x"
0x180037732  mov     rcx, rax
0x180037735  call    sqlite3BtreeOpen
0x18003773a  mov     esi, eax
0x18003773c  test    eax, eax
0x18003773e  jnz     short loc_180037795
0x180037740  mov     rbx, [rbp+arg_0]
0x180037744  mov     rcx, rdi
0x180037747  mov     rdx, rbx
0x18003774a  call    sqlite3SchemaGet
0x18003774f  mov     r15, rax
0x180037752  test    rax, rax
0x180037755  jz      short loc_180037788
0x180037757  movzx   r14d, byte ptr [rdi+0C4h]
0x18003775f  shl     r14, 5
0x180037763  add     r14, [rdi+20h]
0x180037767  mov     rcx, [r14+8]
0x18003776b  test    rcx, rcx
0x18003776e  jz      short loc_180037775
0x180037770  call    sqlite3BtreeClose
0x180037775  mov     [r14+8], rbx
0x180037779  xor     ebx, ebx
0x18003777b  mov     [r14+18h], r15
0x18003777f  mov     r15, [rbp+var_18]
0x180037783  jmp     loc_18003798D
0x180037788  mov     rcx, rbx
0x18003778b  call    sqlite3BtreeClose
0x180037790  mov     esi, 7
0x180037795  mov     rax, [rbp+arg_18]
0x180037799  test    rax, rax
0x18003779c  jz      short loc_1800377D2
0x18003779e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800377a2  mov     dword ptr [r13+24h], 1
0x1800377aa  mov     [rsp+50h+var_30], rcx
0x1800377af  mov     r8, rcx
0x1800377b2  mov     rcx, [r13+0]
0x1800377b6  mov     r9b, 1
0x1800377b9  mov     rdx, rax
0x1800377bc  call    sqlite3VdbeMemSetStr
0x1800377c1  mov     rdx, [rbp+arg_18]
0x1800377c5  test    rdx, rdx
0x1800377c8  jz      short loc_1800377D2
0x1800377ca  mov     rcx, rdi
0x1800377cd  call    sqlite3DbFreeNN
0x1800377d2  test    esi, esi
0x1800377d4  jz      short loc_1800377E0
0x1800377d6  mov     edx, esi
0x1800377d8  mov     rcx, r13
0x1800377db  call    sqlite3_result_error_code
0x1800377e0  mov     rbx, [rsp+50h+arg_8]
0x1800377e8  add     rsp, 50h
0x1800377ec  pop     r15
0x1800377ee  pop     r14
0x1800377f0  pop     r13
0x1800377f2  pop     r12
0x1800377f4  pop     rdi
0x1800377f5  pop     rsi
0x1800377f6  pop     rbp
0x1800377f7  retn
0x1800377f8  mov     r8d, [rdi+0A4h]
0x1800377ff  mov     esi, ebx
0x180037801  mov     r14d, [rdi+28h]
0x180037805  lea     eax, [r8+2]
0x180037809  cmp     r14d, eax
0x18003780c  jl      short loc_180037826
0x18003780e  lea     rdx, aTooManyAttache; "too many attached databases - max %d"
0x180037815  mov     rcx, rdi
0x180037818  call    sqlite3MPrintf
0x18003781d  mov     [rbp+arg_18], rax
0x180037821  jmp     loc_180037799
0x180037826  test    r14d, r14d
0x180037829  jle     short loc_180037843
0x18003782b  mov     r8, r12
0x18003782e  mov     edx, ebx
0x180037830  mov     rcx, rdi
0x180037833  call    sqlite3DbIsNamed
0x180037838  test    eax, eax
0x18003783a  jnz     short loc_180037892
0x18003783c  inc     ebx
0x18003783e  cmp     ebx, r14d
0x180037841  jl      short loc_18003782B
0x180037843  mov     rdx, [rdi+20h]
0x180037847  lea     rax, [rdi+2A0h]
0x18003784e  mov     rcx, rdi
0x180037851  cmp     rdx, rax
0x180037854  jnz     short loc_1800378A9
0x180037856  mov     edx, 60h ; '`'
0x18003785b  call    sqlite3DbMallocRawNN
0x180037860  xor     ebx, ebx
0x180037862  mov     rdx, rax
0x180037865  test    rax, rax
0x180037868  jz      loc_1800377E0
0x18003786e  mov     rcx, [rdi+20h]
0x180037872  movups  xmm0, xmmword ptr [rcx]
0x180037875  movups  xmmword ptr [rax], xmm0
0x180037878  movups  xmm1, xmmword ptr [rcx+10h]
0x18003787c  movups  xmmword ptr [rax+10h], xmm1
0x180037880  movups  xmm0, xmmword ptr [rcx+20h]
0x180037884  movups  xmmword ptr [rax+20h], xmm0
0x180037888  movups  xmm1, xmmword ptr [rcx+30h]
0x18003788c  movups  xmmword ptr [rax+30h], xmm1
0x180037890  jmp     short loc_1800378C7
0x180037892  mov     r8, r12
0x180037895  lea     rdx, aDatabaseSIsAlr; "database %s is already in use"
0x18003789c  mov     rcx, rdi
0x18003789f  call    sqlite3MPrintf
0x1800378a4  jmp     loc_18003781D
0x1800378a9  lea     eax, [r14+1]
0x1800378ad  movsxd  r8, eax
0x1800378b0  shl     r8, 5
0x1800378b4  call    sqlite3DbRealloc
0x1800378b9  xor     ebx, ebx
0x1800378bb  mov     rdx, rax
0x1800378be  test    rax, rax
0x1800378c1  jz      loc_1800377E0
0x1800378c7  movsxd  r14, dword ptr [rdi+28h]
0x1800378cb  lea     r9, [rbp+var_10]
0x1800378cf  mov     [rdi+20h], rdx
0x1800378d3  lea     r8, [rbp+arg_0]
0x1800378d7  xorps   xmm0, xmm0
0x1800378da  shl     r14, 5
0x1800378de  add     r14, rdx
0x1800378e1  mov     rdx, r15
0x1800378e4  movups  xmmword ptr [r14], xmm0
0x1800378e8  movups  xmmword ptr [r14+10h], xmm0
0x1800378ed  mov     eax, [rdi+4Ch]
0x1800378f0  mov     rcx, [rdi]
0x1800378f3  mov     dword ptr [rbp+arg_0], eax
0x1800378f6  lea     rax, [rbp+var_20]
0x1800378fa  mov     [rsp+50h+var_28], rax
0x1800378ff  lea     rax, [rbp+var_18]
0x180037903  mov     [rsp+50h+var_30], rax
0x180037908  mov     rcx, [rcx+18h]
0x18003790c  call    sqlite3ParseUri
0x180037911  test    eax, eax
0x180037913  jz      short loc_180037954
0x180037915  cmp     eax, 7
0x180037918  jnz     short loc_180037922
0x18003791a  mov     rcx, rdi
0x18003791d  call    sqlite3OomFault
0x180037922  mov     rdx, [rbp+var_20]
0x180037926  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003792a  mov     rcx, [r13+0]
0x18003792e  mov     r8, rax
0x180037931  mov     r9b, 1
0x180037934  mov     dword ptr [r13+24h], 1
0x18003793c  mov     [rsp+50h+var_30], rax
0x180037941  call    sqlite3VdbeMemSetStr
0x180037946  mov     rcx, [rbp+var_20]
0x18003794a  call    sqlite3_free
0x18003794f  jmp     loc_1800377E0
0x180037954  mov     eax, dword ptr [rbp+arg_0]
0x180037957  lea     r9, [r14+8]
0x18003795b  mov     r15, [rbp+var_18]
0x18003795f  bts     eax, 8
0x180037963  mov     rcx, [rbp+var_10]
0x180037967  mov     r8, rdi
0x18003796a  mov     dword ptr [rsp+50h+var_28], eax
0x18003796e  mov     rdx, r15
0x180037971  mov     dword ptr [rsp+50h+var_30], ebx
0x180037975  call    sqlite3BtreeOpen
0x18003797a  inc     dword ptr [rdi+28h]
0x18003797d  mov     rdx, r12
0x180037980  mov     rcx, rdi
0x180037983  mov     esi, eax
0x180037985  call    sqlite3DbStrDup
0x18003798a  mov     [r14], rax
0x18003798d  mov     [rdi+6Fh], bl
0x180037990  cmp     esi, 13h
0x180037993  jnz     short loc_1800379B2
0x180037995  lea     rdx, aDatabaseIsAlre; "database is already attached"
0x18003799c  mov     rcx, rdi
0x18003799f  mov     esi, 1
0x1800379a4  call    sqlite3MPrintf
0x1800379a9  mov     [rbp+arg_18], rax
0x1800379ad  jmp     loc_180037A80
0x1800379b2  test    esi, esi
0x1800379b4  jnz     loc_180037A80
0x1800379ba  mov     rdx, [r14+8]
0x1800379be  mov     rcx, rdi
0x1800379c1  call    sqlite3SchemaGet
0x1800379c6  mov     [r14+18h], rax
0x1800379ca  mov     rcx, rax
0x1800379cd  test    rax, rax
0x1800379d0  jnz     short loc_1800379D7
0x1800379d2  lea     esi, [rax+7]
0x1800379d5  jmp     short loc_1800379FC
0x1800379d7  cmp     [rax+70h], bl
0x1800379da  jz      short loc_1800379FC
0x1800379dc  mov     al, [rdi+64h]
0x1800379df  cmp     [rcx+71h], al
0x1800379e2  jz      short loc_1800379FC
0x1800379e4  lea     rdx, aAttachedDataba; "attached databases must use the same te"...
0x1800379eb  mov     rcx, rdi
0x1800379ee  call    sqlite3MPrintf
0x1800379f3  mov     [rbp+arg_18], rax
0x1800379f7  mov     esi, 1
0x1800379fc  mov     rcx, [r14+8]
0x180037a00  cmp     [rcx+11h], bl
0x180037a03  jz      short loc_180037A12
0x180037a05  inc     dword ptr [rcx+14h]
0x180037a08  cmp     [rcx+12h], bl
0x180037a0b  jnz     short loc_180037A12
0x180037a0d  call    btreeLockCarefully
0x180037a12  mov     rax, [r14+8]
0x180037a16  mov     rcx, [rax+8]
0x180037a1a  mov     rdx, [rcx]
0x180037a1d  cmp     [rdx+10h], bl
0x180037a20  jnz     short loc_180037A3A
0x180037a22  mov     rax, [rdx+148h]
0x180037a29  test    rax, rax
0x180037a2c  jz      short loc_180037A34
0x180037a2e  cmp     byte ptr [rax+3Fh], 2
0x180037a32  jz      short loc_180037A3A
0x180037a34  mov     al, [rdi+69h]
0x180037a37  mov     [rdx+8], al
0x180037a3a  mov     rcx, [rdi+20h]
0x180037a3e  or      edx, 0FFFFFFFFh
0x180037a41  mov     rbx, [r14+8]
0x180037a45  mov     rcx, [rcx+8]
0x180037a49  call    sqlite3BtreeSecureDelete
0x180037a4e  mov     edx, eax
0x180037a50  mov     rcx, rbx
0x180037a53  call    sqlite3BtreeSecureDelete
0x180037a58  mov     edx, [rdi+30h]
0x180037a5b  mov     rcx, [r14+8]
0x180037a5f  and     edx, 38h
0x180037a62  or      edx, 3
0x180037a65  call    sqlite3BtreeSetPagerFlags
0x180037a6a  mov     rcx, [r14+8]
0x180037a6e  xor     ebx, ebx
0x180037a70  cmp     [rcx+11h], bl
0x180037a73  jz      short loc_180037A80
0x180037a75  sub     dword ptr [rcx+14h], 1
0x180037a79  jnz     short loc_180037A80
0x180037a7b  call    unlockBtreeMutex
0x180037a80  mov     byte ptr [r14+10h], 3
0x180037a85  test    esi, esi
0x180037a87  jnz     loc_180037B85
0x180037a8d  cmp     [r14], rbx
0x180037a90  jnz     short loc_180037A9C
0x180037a92  mov     esi, 7
0x180037a97  jmp     loc_180037B85
0x180037a9c  mov     r14, [rbp+arg_10]
0x180037aa0  lea     rcx, qword_1800FE430
0x180037aa7  mov     rdx, [r14+10h]
0x180037aab  movzx   eax, word ptr [rdx+14h]
0x180037aaf  and     eax, 3Fh
0x180037ab2  movzx   ecx, byte ptr [rax+rcx]
0x180037ab6  sub     ecx, 1
0x180037ab9  jz      loc_180037B6D
0x180037abf  sub     ecx, 1
0x180037ac2  jz      loc_180037B6D
0x180037ac8  sub     ecx, 1
  ... truncated ...
```
