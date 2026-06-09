# attachFunc

- ea: `0x180017460`
- end: `0x180017d32`
- name: `attachFunc`
- size: `2258`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x180005980`
- `0x18000c240`
- `0x1800118a0`
- `0x180017460`
- `0x18002aef0`
- `0x18002b2d0`
- `0x18002b330`
- `0x180034a20`
- `0x18004dba0`
- `0x180067750`
- `0x180069890`
- `0x18006a920`
- `0x180071360`
- `0x180071400`
- `0x180084210`
- `0x180088530`
- `0x180089210`
- `0x18008b950`
- `0x1800950a0`
- `0x180097010`
- `0x1800af350`
- `0x1800af900`
- `0x1800c1b30`
- `0x1800c3e10`
- `0x1800c5960`
- `0x1800e4dce`
- `0x1800e4dfe`
- `0x18010d010`

## string_xrefs

- `0x1800176e8`: `database %s is already in use`
- `0x1800179b6`: `database is already attached`
- `0x180017c30`: `unable to open database: %s`

## pseudocode

```c
__int64 __fastcall attachFunc(__int64 *a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v6; // rcx
  __int64 *v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  const char *v14; // r15
  const char *v15; // r13
  __int64 result; // rax
  unsigned int v17; // esi
  __int64 v18; // r9
  __int64 v19; // r15
  __int64 v20; // r12
  __int64 v21; // r14
  __int64 v22; // rcx
  _BYTE *v23; // r13
  __int64 *v24; // rdi
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  int v27; // r8d
  int v28; // r14d
  unsigned __int64 v29; // rdx
  _OWORD *v30; // rcx
  unsigned __int64 v31; // r8
  __int64 v32; // r14
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rdx
  char *v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // rax
  int v39; // r14d
  signed __int64 v40; // rax
  __int64 v41; // rdx
  int v42; // esi
  size_t v43; // r14
  __int64 v44; // rdx
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // r12
  size_t v48; // r13
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // r15
  __int16 v55; // r12
  unsigned __int16 v56; // r12
  bool v57; // zf
  __int64 v58; // r15
  __int64 v59; // rcx
  __int64 v60; // rdi
  int v61; // r14d
  __int64 v62; // rcx
  _QWORD *v63; // rcx
  __int64 v64; // [rsp+20h] [rbp-30h]
  char *Str; // [rsp+30h] [rbp-20h] BYREF
  __int64 v66; // [rsp+38h] [rbp-18h] BYREF
  __int64 v67; // [rsp+40h] [rbp-10h] BYREF
  const char *v68; // [rsp+48h] [rbp-8h]
  __int64 v70; // [rsp+A0h] [rbp+50h] BYREF
  _QWORD *v71; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *a1;
  v4 = 0;
  v66 = 0;
  v6 = *a3;
  Str = 0;
  v8 = *(__int64 **)(v3 + 24);
  v71 = 0;
  if ( v6 )
  {
    v10 = *(unsigned __int16 *)(v6 + 20);
    if ( (v10 & 0x202) == 0x202 && *(_BYTE *)(v6 + 22) == 1 )
    {
      v9 = *(_QWORD *)(v6 + 8);
    }
    else if ( (v10 & 1) != 0 )
    {
      v9 = 0;
    }
    else
    {
      LOBYTE(v10) = 1;
      v9 = valueToText(v6, v10);
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = a3[1];
  if ( v11 )
  {
    v13 = *(unsigned __int16 *)(v11 + 20);
    if ( (v13 & 0x202) == 0x202 && *(_BYTE *)(v11 + 22) == 1 )
    {
      v12 = *(_QWORD *)(v11 + 8);
    }
    else if ( (v13 & 1) != 0 )
    {
      v12 = 0;
    }
    else
    {
      LOBYTE(v13) = 1;
      v12 = valueToText(v11, v13);
    }
  }
  else
  {
    v12 = 0;
  }
  v14 = byte_180122168;
  v15 = byte_180122168;
  if ( v9 )
    v15 = (const char *)v9;
  v68 = v15;
  if ( v12 )
    v14 = (const char *)v12;
  if ( (v8[25] & 4) != 0 )
  {
    v70 = 0;
    result = sqlite3_vfs_find("memdb");
    if ( !result )
      return result;
    v17 = sqlite3BtreeOpen(result, "x", v8, &v70, 0, 256);
    if ( v17 )
      goto LABEL_29;
    v19 = v70;
    v20 = sqlite3SchemaGet(v8, v70);
    if ( !v20 )
    {
      sqlite3BtreeClose(v19);
      v17 = 7;
      goto LABEL_29;
    }
    v21 = v8[4] + 32LL * *((unsigned __int8 *)v8 + 196);
    v22 = *(_QWORD *)(v21 + 8);
    if ( v22 )
      sqlite3BtreeClose(v22);
    v23 = (char *)v8 + 111;
    *(_QWORD *)(v21 + 8) = v19;
    *(_QWORD *)(v21 + 24) = v20;
    *((_BYTE *)v8 + 111) = 0;
LABEL_92:
    v49 = sqlite3SchemaGet(v8, *(_QWORD *)(v21 + 8));
    *(_QWORD *)(v21 + 24) = v49;
    if ( v49 )
    {
      if ( *(_BYTE *)(v49 + 112) && *(_BYTE *)(v49 + 113) != *((_BYTE *)v8 + 100) )
      {
        v71 = (_QWORD *)sqlite3MPrintf(v8, "attached databases must use the same text encoding as main database");
        v17 = 1;
      }
    }
    else
    {
      v17 = 7;
    }
    v50 = *(_QWORD *)(v21 + 8);
    if ( *(_BYTE *)(v50 + 17) )
    {
      ++*(_DWORD *)(v50 + 20);
      if ( !*(_BYTE *)(v50 + 18) )
        btreeLockCarefully(v50);
    }
    v51 = *(__int64 **)(*(_QWORD *)(v21 + 8) + 8LL);
    v52 = *v51;
    if ( !*(_BYTE *)(*v51 + 16) )
    {
      v53 = *(_QWORD *)(v52 + 296);
      if ( !v53 || *(_BYTE *)(v53 + 63) != 2 )
        *(_BYTE *)(v52 + 8) = *((_BYTE *)v8 + 105);
    }
    v54 = *(_QWORD *)(v8[4] + 8);
    if ( v54 )
    {
      if ( *(_BYTE *)(v54 + 17) )
      {
        ++*(_DWORD *)(v54 + 20);
        if ( !*(_BYTE *)(v54 + 18) )
          btreeLockCarefully(v54);
      }
      v56 = *(_WORD *)(*(_QWORD *)(v54 + 8) + 40LL);
      if ( *(_BYTE *)(v54 + 17) )
      {
        v57 = (*(_DWORD *)(v54 + 20))-- == 1;
        if ( v57 )
          unlockBtreeMutex(v54);
      }
      v55 = (v56 >> 2) & 3;
    }
    else
    {
      v55 = 0;
    }
    v58 = *(_QWORD *)(v21 + 8);
    if ( v58 )
    {
      if ( *(_BYTE *)(v58 + 17) )
      {
        ++*(_DWORD *)(v58 + 20);
        if ( !*(_BYTE *)(v58 + 18) )
          btreeLockCarefully(v58);
      }
      *(_WORD *)(*(_QWORD *)(v58 + 8) + 40LL) &= 0xFFF3u;
      *(_WORD *)(*(_QWORD *)(v58 + 8) + 40LL) |= 4 * v55;
      if ( *(_BYTE *)(v58 + 17) )
      {
        v57 = (*(_DWORD *)(v58 + 20))-- == 1;
        if ( v57 )
          unlockBtreeMutex(v58);
      }
    }
    result = sqlite3BtreeSetPagerFlags(*(_QWORD *)(v21 + 8), v8[6] & 0x38 | 3);
    v59 = *(_QWORD *)(v21 + 8);
    if ( *(_BYTE *)(v59 + 17) )
    {
      v57 = (*(_DWORD *)(v59 + 20))-- == 1;
      if ( v57 )
        result = unlockBtreeMutex(v59);
    }
    goto LABEL_123;
  }
  v27 = *((_DWORD *)v8 + 41);
  v17 = 0;
  v28 = *((_DWORD *)v8 + 10);
  if ( v28 >= v27 + 2 )
  {
    result = sqlite3MPrintf(v8, "too many attached databases - max %d", v27);
    v71 = (_QWORD *)result;
    goto LABEL_30;
  }
  if ( v28 > 0 )
  {
    while ( !(unsigned int)sqlite3DbIsNamed(v8, (unsigned int)v4, v14) )
    {
      LODWORD(v4) = v4 + 1;
      if ( (int)v4 >= v28 )
        goto LABEL_40;
    }
    result = sqlite3MPrintf(v8, "database %s is already in use", v14);
    v71 = (_QWORD *)result;
    goto LABEL_30;
  }
LABEL_40:
  v29 = v8[4];
  if ( (__int64 *)v29 == v8 + 84 )
  {
    result = sqlite3DbMallocRawNN(v8, 96);
    v29 = result;
    if ( !result )
      return result;
    v30 = (_OWORD *)v8[4];
    *(_OWORD *)result = *v30;
    *(_OWORD *)(result + 16) = v30[1];
    *(_OWORD *)(result + 32) = v30[2];
    *(_OWORD *)(result + 48) = v30[3];
  }
  else
  {
    v31 = 32LL * (v28 + 1);
    if ( v29 )
    {
      if ( v29 < v8[62] )
      {
        if ( v29 < v8[60] )
        {
          if ( v29 >= v8[61] && v31 <= *((unsigned __int16 *)v8 + 211) )
            goto LABEL_54;
        }
        else if ( v31 <= 0x80 )
        {
          goto LABEL_54;
        }
      }
      result = dbReallocFinish(v8, v29, v31);
    }
    else
    {
      result = sqlite3DbMallocRawNN(v8, 32LL * (v28 + 1));
    }
    v29 = result;
    if ( !result )
      return result;
  }
LABEL_54:
  v32 = *((int *)v8 + 10);
  v8[4] = v29;
  v21 = v29 + 32 * v32;
  *(_OWORD *)v21 = 0;
  *(_OWORD *)(v21 + 16) = 0;
  v33 = *v8;
  LODWORD(v70) = *((_DWORD *)v8 + 19);
  v34 = sqlite3ParseUri(*(char **)(v33 + 24), v15, (unsigned int *)&v70, &v67, (char **)&v66, (__int64 *)&Str);
  if ( v34 )
  {
    if ( v34 == 7 )
      sqlite3OomFault(v8);
    v36 = Str;
    v37 = *a1;
    *((_DWORD *)a1 + 9) = 1;
    if ( v36 )
    {
      v38 = *(_QWORD *)(v37 + 24);
      if ( v38 )
        v39 = *(_DWORD *)(v38 + 136);
      else
        v39 = 1000000000;
      v40 = strlen_0(v36);
      v42 = v40;
      if ( v40 > v39 )
      {
        if ( (*(_WORD *)(v37 + 20) & 0x9000) != 0 )
          vdbeMemClearExternAndSetNull(v37, v41);
        else
          *(_WORD *)(v37 + 20) = 1;
        result = *(_QWORD *)(v37 + 24);
        if ( result )
        {
          result = *(_QWORD *)(result + 352);
          if ( result )
          {
            ++*(_DWORD *)(result + 48);
            *(_DWORD *)(result + 24) = 18;
          }
        }
        goto LABEL_78;
      }
      v43 = v40 + 1;
      v44 = 32;
      if ( v40 + 1 > 32 )
        v44 = (unsigned int)v43;
      if ( *(_DWORD *)(v37 + 32) >= (int)v44 )
      {
        v45 = *(_QWORD *)(v37 + 40);
        *(_WORD *)(v37 + 20) &= 0x2Du;
        *(_QWORD *)(v37 + 8) = v45;
      }
      else
      {
        result = sqlite3VdbeMemGrow(v37, v44, 0);
        if ( (_DWORD)result )
          goto LABEL_78;
      }
      result = (__int64)memcpy_0(*(void **)(v37 + 8), v36, v43);
      *(_WORD *)(v37 + 20) = 514;
      *(_DWORD *)(v37 + 16) = v42 & 0x7FFFFFFF;
      *(_BYTE *)(v37 + 22) = 1;
    }
    else
    {
      result = 36864;
      if ( (*(_WORD *)(v37 + 20) & 0x9000) != 0 )
        result = vdbeMemClearExternAndSetNull(v37, v35);
      else
        *(_WORD *)(v37 + 20) = 1;
    }
LABEL_78:
    if ( v36 )
    {
      if ( dword_18013C1B0 )
      {
        if ( (_QWORD)xmmword_18013FC60 )
          ((void (*)(void))xmmword_18013C230)();
        v46 = ((__int64 (__fastcall *)(char *))xmmword_18013C1E8)(v36);
        --qword_18013FBE8;
        qword_18013FBA0 -= v46;
        result = ((__int64 (__fastcall *)(char *))xmmword_18013C1D8)(v36);
        if ( (_QWORD)xmmword_18013FC60 )
          return ((__int64 (*)(void))xmmword_18013C240)();
      }
      else
      {
        return ((__int64 (__fastcall *)(char *))xmmword_18013C1D8)(v36);
      }
    }
    return result;
  }
  v4 = v66;
  LODWORD(v64) = 0;
  result = sqlite3BtreeOpen(v67, v66, v8, v21 + 8, v64, (unsigned int)v70 | 0x100);
  ++*((_DWORD *)v8 + 10);
  v17 = result;
  if ( v14 )
  {
    v48 = strlen_0(v14) + 1;
    result = sqlite3DbMallocRawNN(v8, v48);
    v47 = result;
    if ( result )
      result = (__int64)memcpy_0((void *)result, v14, v48);
  }
  else
  {
    v47 = 0;
  }
  *(_QWORD *)v21 = v47;
  v23 = (char *)v8 + 111;
  *((_BYTE *)v8 + 111) = 0;
  if ( v17 == 19 )
  {
    v17 = 1;
    result = sqlite3MPrintf(v8, "database is already attached");
    v71 = (_QWORD *)result;
    *(_BYTE *)(v21 + 16) = 3;
    goto LABEL_126;
  }
  if ( !v17 )
    goto LABEL_92;
LABEL_123:
  *(_BYTE *)(v21 + 16) = 3;
  if ( !v17 )
  {
    result = 7;
    if ( !*(_QWORD *)v21 )
      v17 = 7;
  }
LABEL_126:
  if ( v4 )
  {
    while ( *(_BYTE *)(v4 - 1) || *(_BYTE *)(v4 - 2) || *(_BYTE *)(v4 - 3) || *(_BYTE *)(v4 - 4) )
      --v4;
    result = sqlite3_free(v4 - 4);
  }
  if ( v17 )
    goto LABEL_141;
  if ( !*v23 )
    result = btreeEnterAll(v8);
  *((_DWORD *)v8 + 11) &= ~0x10u;
  v57 = (v8[25] & 4) == 0;
  *((_BYTE *)v8 + 196) = 0;
  if ( v57 )
  {
    result = sqlite3Init(v8, &v71);
    v17 = result;
  }
  if ( !*v23 )
    result = btreeLeaveAll(v8);
  if ( v17 )
  {
LABEL_141:
    if ( (v8[25] & 4) == 0 )
    {
      v60 = 32LL * *((int *)v8 + 10);
      v61 = *((_DWORD *)v8 + 10) - 1;
      v62 = *(_QWORD *)(v60 + v8[4] - 24);
      if ( v62 )
      {
        sqlite3BtreeClose(v62);
        *(_QWORD *)(v60 + v8[4] - 24) = 0;
        *(_QWORD *)(v60 + v8[4] - 8) = 0;
      }
      sqlite3ResetAllSchemasOfConnection(v8);
      *((_DWORD *)v8 + 10) = v61;
      if ( v17 != 7 && v17 != 3082 )
      {
        result = (__int64)v71;
        if ( v71 )
          goto LABEL_31;
        result = sqlite3MPrintf(v8, "unable to open database: %s", v68);
        v71 = (_QWORD *)result;
LABEL_30:
        if ( !result )
        {
          v24 = a1;
          goto LABEL_164;
        }
LABEL_31:
        v24 = a1;
        LOBYTE(v18) = 1;
        v25 = *a1;
        *((_DWORD *)a1 + 9) = 1;
        result = sqlite3VdbeMemSetStr(v25, result, -1, v18, -1);
        v26 = v71;
        if ( !v71 )
          goto LABEL_164;
        if ( (unsigned __int64)v71 >= v8[62] )
          goto LABEL_168;
        if ( (unsigned __int64)v71 >= v8[60] )
        {
          result = v8[59];
          *v71 = result;
          v8[59] = (__int64)v26;
          goto LABEL_164;
        }
        if ( (unsigned __int64)v71 < v8[61] )
        {
LABEL_168:
          if ( v8[97] )
            result = measureAllocationSize(v8, v71);
          else
            result = sqlite3_free(v71);
          goto LABEL_164;
        }
        result = v8[57];
        *v71 = result;
        v8[57] = (__int64)v26;
LABEL_164:
        if ( v17 )
          return sqlite3_result_error_code(v24, v17);
        return result;
      }
      sqlite3OomFault(v8);
      v63 = v71;
      if ( v71 )
      {
        if ( (unsigned __int64)v71 < v8[62] )
        {
          if ( (unsigned __int64)v71 >= v8[60] )
          {
            *v71 = v8[59];
            v8[59] = (__int64)v63;
            goto LABEL_157;
          }
          if ( (unsigned __int64)v71 >= v8[61] )
          {
            *v71 = v8[57];
            v8[57] = (__int64)v63;
            goto LABEL_157;
          }
        }
        if ( v8[97] )
          measureAllocationSize(v8, v71);
        else
          sqlite3_free(v71);
      }
LABEL_157:
      result = sqlite3MPrintf(v8, "out of memory");
      v71 = (_QWORD *)result;
      goto LABEL_30;
    }
LABEL_29:
    result = (__int64)v71;
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x180017460  mov     [rsp-38h+arg_8], rbx
0x180017465  mov     [rsp-38h+arg_0], rcx
0x18001746a  push    rbp
0x18001746b  push    rsi
0x18001746c  push    rdi
0x18001746d  push    r12
0x18001746f  push    r13
0x180017471  push    r14
0x180017473  push    r15
0x180017475  mov     rbp, rsp
0x180017478  sub     rsp, 50h
0x18001747c  mov     rax, [rcx]
0x18001747f  xor     edi, edi
0x180017481  mov     r12, rcx
0x180017484  mov     [rbp+var_18], rdi
0x180017488  mov     rcx, [r8]
0x18001748b  mov     r14, r8
0x18001748e  mov     [rbp+Str], rdi
0x180017492  mov     r8d, 202h
0x180017498  mov     rbx, [rax+18h]
0x18001749c  mov     [rbp+arg_18], rdi
0x1800174a0  test    rcx, rcx
0x1800174a3  jnz     short loc_1800174A9
0x1800174a5  xor     esi, esi
0x1800174a7  jmp     short loc_1800174DF
0x1800174a9  movzx   edx, word ptr [rcx+14h]
0x1800174ad  movzx   eax, dx
0x1800174b0  and     ax, r8w
0x1800174b4  cmp     ax, r8w
0x1800174b8  jnz     short loc_1800174C6
0x1800174ba  cmp     byte ptr [rcx+16h], 1
0x1800174be  jnz     short loc_1800174C6
0x1800174c0  mov     rsi, [rcx+8]
0x1800174c4  jmp     short loc_1800174DF
0x1800174c6  test    dl, 1
0x1800174c9  jz      short loc_1800174CF
0x1800174cb  xor     esi, esi
0x1800174cd  jmp     short loc_1800174DF
0x1800174cf  mov     dl, 1
0x1800174d1  call    valueToText
0x1800174d6  mov     rsi, rax
0x1800174d9  mov     r8d, 202h
0x1800174df  mov     rcx, [r14+8]
0x1800174e3  test    rcx, rcx
0x1800174e6  jnz     short loc_1800174EC
0x1800174e8  xor     eax, eax
0x1800174ea  jmp     short loc_180017519
0x1800174ec  movzx   edx, word ptr [rcx+14h]
0x1800174f0  movzx   eax, dx
0x1800174f3  and     ax, r8w
0x1800174f7  cmp     ax, r8w
0x1800174fb  jnz     short loc_180017509
0x1800174fd  cmp     byte ptr [rcx+16h], 1
0x180017501  jnz     short loc_180017509
0x180017503  mov     rax, [rcx+8]
0x180017507  jmp     short loc_180017519
0x180017509  test    dl, 1
0x18001750c  jz      short loc_180017512
0x18001750e  xor     eax, eax
0x180017510  jmp     short loc_180017519
0x180017512  mov     dl, 1
0x180017514  call    valueToText
0x180017519  test    rsi, rsi
0x18001751c  lea     r15, byte_180122168
0x180017523  mov     r13, r15
0x180017526  cmovnz  r13, rsi
0x18001752a  test    rax, rax
0x18001752d  mov     [rbp+var_8], r13
0x180017531  cmovnz  r15, rax
0x180017535  test    byte ptr [rbx+0C8h], 4
0x18001753c  jz      loc_18001764D
0x180017542  lea     rcx, Str1; "memdb"
0x180017549  mov     [rbp+arg_10], rdi
0x18001754d  call    sqlite3_vfs_find
0x180017552  test    rax, rax
0x180017555  jz      loc_180017D1A
0x18001755b  mov     dword ptr [rsp+50h+var_28], 100h
0x180017563  lea     r9, [rbp+arg_10]
0x180017567  mov     r8, rbx
0x18001756a  mov     dword ptr [rsp+50h+var_30], edi
0x18001756e  lea     rdx, asc_18011BC1C; "x"
0x180017575  mov     rcx, rax
0x180017578  call    sqlite3BtreeOpen
0x18001757d  mov     esi, eax
0x18001757f  test    eax, eax
0x180017581  jnz     short loc_1800175DA
0x180017583  mov     r15, [rbp+arg_10]
0x180017587  mov     rcx, rbx
0x18001758a  mov     rdx, r15
0x18001758d  call    sqlite3SchemaGet
0x180017592  mov     r12, rax
0x180017595  test    rax, rax
0x180017598  jz      short loc_1800175CD
0x18001759a  movzx   r14d, byte ptr [rbx+0C4h]
0x1800175a2  shl     r14, 5
0x1800175a6  add     r14, [rbx+20h]
0x1800175aa  mov     rcx, [r14+8]
0x1800175ae  test    rcx, rcx
0x1800175b1  jz      short loc_1800175B8
0x1800175b3  call    sqlite3BtreeClose
0x1800175b8  lea     r13, [rbx+6Fh]
0x1800175bc  mov     [r14+8], r15
0x1800175c0  mov     [r14+18h], r12
0x1800175c4  mov     [r13+0], dil
0x1800175c8  jmp     loc_1800179E0
0x1800175cd  mov     rcx, r15
0x1800175d0  call    sqlite3BtreeClose
0x1800175d5  mov     esi, 7
0x1800175da  mov     rax, [rbp+arg_18]
0x1800175de  test    rax, rax
0x1800175e1  jz      loc_180017D08
0x1800175e7  mov     rdi, [rbp+arg_0]
0x1800175eb  mov     r9b, 1
0x1800175ee  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800175f5  mov     [rsp+50h+var_30], 0FFFFFFFFFFFFFFFFh
0x1800175fe  mov     rdx, rax
0x180017601  mov     rcx, [rdi]
0x180017604  mov     dword ptr [rdi+24h], 1
0x18001760b  call    sqlite3VdbeMemSetStr
0x180017610  mov     rcx, [rbp+arg_18]
0x180017614  test    rcx, rcx
0x180017617  jz      loc_180017D0C
0x18001761d  cmp     rcx, [rbx+1F0h]
0x180017624  jnb     loc_180017CEA
0x18001762a  cmp     rcx, [rbx+1E0h]
0x180017631  jb      loc_180017CCE
0x180017637  mov     rax, [rbx+1D8h]
0x18001763e  mov     [rcx], rax
0x180017641  mov     [rbx+1D8h], rcx
0x180017648  jmp     loc_180017D0C
0x18001764d  mov     r8d, [rbx+0A4h]
0x180017654  xor     esi, esi
0x180017656  mov     r14d, [rbx+28h]
0x18001765a  lea     eax, [r8+2]
0x18001765e  cmp     r14d, eax
0x180017661  jl      short loc_18001767B
0x180017663  lea     rdx, aTooManyAttache; "too many attached databases - max %d"
0x18001766a  mov     rcx, rbx
0x18001766d  call    sqlite3MPrintf
0x180017672  mov     [rbp+arg_18], rax
0x180017676  jmp     loc_1800175DE
0x18001767b  test    r14d, r14d
0x18001767e  jle     short loc_180017698
0x180017680  mov     r8, r15
0x180017683  mov     edx, edi
0x180017685  mov     rcx, rbx
0x180017688  call    sqlite3DbIsNamed
0x18001768d  test    eax, eax
0x18001768f  jnz     short loc_1800176E5
0x180017691  inc     edi
0x180017693  cmp     edi, r14d
0x180017696  jl      short loc_180017680
0x180017698  mov     rdx, [rbx+20h]
0x18001769c  lea     rax, [rbx+2A0h]
0x1800176a3  cmp     rdx, rax
0x1800176a6  jnz     short loc_180017700
0x1800176a8  mov     edx, 60h ; '`'
0x1800176ad  mov     rcx, rbx
0x1800176b0  call    sqlite3DbMallocRawNN
0x1800176b5  mov     rdx, rax
0x1800176b8  test    rax, rax
0x1800176bb  jz      loc_180017D1A
0x1800176c1  mov     rcx, [rbx+20h]
0x1800176c5  movups  xmm0, xmmword ptr [rcx]
0x1800176c8  movups  xmmword ptr [rax], xmm0
0x1800176cb  movups  xmm1, xmmword ptr [rcx+10h]
0x1800176cf  movups  xmmword ptr [rax+10h], xmm1
0x1800176d3  movups  xmm0, xmmword ptr [rcx+20h]
0x1800176d7  movups  xmmword ptr [rax+20h], xmm0
0x1800176db  movups  xmm1, xmmword ptr [rcx+30h]
0x1800176df  movups  xmmword ptr [rax+30h], xmm1
0x1800176e3  jmp     short loc_180017763
0x1800176e5  mov     r8, r15
0x1800176e8  lea     rdx, aDatabaseSIsAlr; "database %s is already in use"
0x1800176ef  mov     rcx, rbx
0x1800176f2  call    sqlite3MPrintf
0x1800176f7  mov     [rbp+arg_18], rax
0x1800176fb  jmp     loc_1800175DE
0x180017700  lea     eax, [r14+1]
0x180017704  movsxd  r8, eax
0x180017707  shl     r8, 5
0x18001770b  test    rdx, rdx
0x18001770e  jnz     short loc_18001771D
0x180017710  mov     rdx, r8
0x180017713  mov     rcx, rbx
0x180017716  call    sqlite3DbMallocRawNN
0x18001771b  jmp     short loc_180017757
0x18001771d  cmp     rdx, [rbx+1F0h]
0x180017724  jnb     short loc_18001774F
0x180017726  cmp     rdx, [rbx+1E0h]
0x18001772d  jb      short loc_18001773A
0x18001772f  cmp     r8, 80h
0x180017736  ja      short loc_18001774F
0x180017738  jmp     short loc_180017763
0x18001773a  cmp     rdx, [rbx+1E8h]
0x180017741  jb      short loc_18001774F
0x180017743  movzx   eax, word ptr [rbx+1A6h]
0x18001774a  cmp     r8, rax
0x18001774d  jbe     short loc_180017763
0x18001774f  mov     rcx, rbx
0x180017752  call    dbReallocFinish
0x180017757  mov     rdx, rax
0x18001775a  test    rax, rax
0x18001775d  jz      loc_180017D1A
0x180017763  movsxd  r14, dword ptr [rbx+28h]
0x180017767  lea     r9, [rbp+var_10]
0x18001776b  mov     [rbx+20h], rdx
0x18001776f  lea     r8, [rbp+arg_10]
0x180017773  xorps   xmm0, xmm0
0x180017776  shl     r14, 5
0x18001777a  add     r14, rdx
0x18001777d  mov     rdx, r13; Src
0x180017780  movups  xmmword ptr [r14], xmm0
0x180017784  movups  xmmword ptr [r14+10h], xmm0
0x180017789  mov     eax, [rbx+4Ch]
0x18001778c  mov     rcx, [rbx]
0x18001778f  mov     dword ptr [rbp+arg_10], eax
0x180017792  lea     rax, [rbp+Str]
0x180017796  mov     [rsp+50h+var_28], rax; __int64
0x18001779b  lea     rax, [rbp+var_18]
0x18001779f  mov     [rsp+50h+var_30], rax; __int64
0x1800177a4  mov     rcx, [rcx+18h]; Str1
0x1800177a8  call    sqlite3ParseUri
0x1800177ad  test    eax, eax
0x1800177af  jz      loc_180017943
0x1800177b5  cmp     eax, 7
0x1800177b8  jnz     short loc_1800177C2
0x1800177ba  mov     rcx, rbx
0x1800177bd  call    sqlite3OomFault
0x1800177c2  mov     rdi, [rbp+Str]
0x1800177c6  mov     r15d, 1
0x1800177cc  mov     rbx, [r12]
0x1800177d0  mov     [r12+24h], r15d
0x1800177d5  test    rdi, rdi
0x1800177d8  jnz     short loc_1800177FC
0x1800177da  mov     eax, 9000h
0x1800177df  test    [rbx+14h], ax
0x1800177e3  jz      short loc_1800177F2
0x1800177e5  mov     rcx, rbx
0x1800177e8  call    vdbeMemClearExternAndSetNull
0x1800177ed  jmp     loc_1800178B5
0x1800177f2  mov     [rbx+14h], r15w
0x1800177f7  jmp     loc_1800178B5
0x1800177fc  mov     rax, [rbx+18h]
0x180017800  test    rax, rax
0x180017803  jz      short loc_18001780E
0x180017805  mov     r14d, [rax+88h]
0x18001780c  jmp     short loc_180017814
0x18001780e  mov     r14d, 3B9ACA00h
0x180017814  mov     rcx, rdi; Str
0x180017817  call    strlen_0
0x18001781c  movsxd  rcx, r14d
0x18001781f  mov     rsi, rax
0x180017822  cmp     rax, rcx
0x180017825  jle     short loc_180017862
0x180017827  mov     eax, 9000h
0x18001782c  test    [rbx+14h], ax
0x180017830  jz      short loc_18001783C
0x180017832  mov     rcx, rbx
0x180017835  call    vdbeMemClearExternAndSetNull
0x18001783a  jmp     short loc_180017841
0x18001783c  mov     [rbx+14h], r15w
0x180017841  mov     rax, [rbx+18h]
0x180017845  test    rax, rax
0x180017848  jz      short loc_1800178B5
0x18001784a  mov     rax, [rax+160h]
0x180017851  test    rax, rax
0x180017854  jz      short loc_1800178B5
0x180017856  inc     dword ptr [rax+30h]
0x180017859  mov     dword ptr [rax+18h], 12h
0x180017860  jmp     short loc_1800178B5
0x180017862  lea     r14, [rax+1]
0x180017866  mov     edx, 20h ; ' '
0x18001786b  cmp     r14, rdx
0x18001786e  cmovg   edx, r14d
0x180017872  cmp     [rbx+20h], edx
0x180017875  jge     short loc_180017888
0x180017877  xor     r8d, r8d
0x18001787a  mov     rcx, rbx
0x18001787d  call    sqlite3VdbeMemGrow
0x180017882  test    eax, eax
0x180017884  jnz     short loc_1800178B5
0x180017886  jmp     short loc_180017895
0x180017888  mov     rax, [rbx+28h]
0x18001788c  and     word ptr [rbx+14h], 2Dh
0x180017891  mov     [rbx+8], rax
0x180017895  mov     rcx, [rbx+8]; void *
0x180017899  mov     r8, r14; Size
0x18001789c  mov     rdx, rdi; Src
0x18001789f  call    memcpy_0
0x1800178a4  btr     esi, 1Fh
0x1800178a8  mov     word ptr [rbx+14h], 202h
0x1800178ae  mov     [rbx+10h], esi
0x1800178b1  mov     [rbx+16h], r15b
0x1800178b5  test    rdi, rdi
0x1800178b8  jz      loc_180017D1A
0x1800178be  cmp     cs:dword_18013C1B0, 0
0x1800178c5  jz      short loc_18001792F
0x1800178c7  mov     rcx, qword ptr cs:xmmword_18013FC60
0x1800178ce  test    rcx, rcx
  ... truncated ...
```
