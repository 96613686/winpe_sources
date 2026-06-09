# attachFunc

- ea: `0x18007a180`
- end: `0x18007a716`
- name: `attachFunc`
- size: `1430`
- prototype: `_OWORD *__fastcall(__int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `34`
- tags: `broker_com_uri`

## callees

- `0x18000e818`
- `0x180015460`
- `0x18001fe1c`
- `0x1800208bc`
- `0x180024b60`
- `0x180031d50`
- `0x180031fd0`
- `0x180035d1c`
- `0x180038910`
- `0x18003c1a0`
- `0x18003f8d0`
- `0x18003fb44`
- `0x180040e00`
- `0x180041d10`
- `0x180041eb0`
- `0x180046be0`
- `0x18004789c`
- `0x180054e70`
- `0x180054ef4`
- `0x18005987c`
- `0x180059d90`
- `0x18005e810`
- `0x18005ecf8`
- `0x18006620c`
- `0x18006dc30`
- `0x180070500`
- `0x180072b8c`
- `0x1800777a0`
- `0x18007a180`
- `0x180091060`
- `0x1800911a0`
- `0x1800911e8`
- `0x1800938ac`
- `0x18009d650`

## string_xrefs

- `0x18007a319`: `database %s is already in use`
- `0x18007a453`: `database is already attached`
- `0x18007a6b8`: `unable to open database: %s`

## pseudocode

```c
_OWORD *__fastcall attachFunc(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r13
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  const wchar_t *v12; // rbx
  __int64 v13; // rax
  const wchar_t *v14; // r12
  const wchar_t *v15; // rcx
  _OWORD *result; // rax
  unsigned int v17; // esi
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // r15
  __int64 v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rbx
  int v24; // r8d
  int v25; // r14d
  unsigned int i; // ebx
  __int64 v27; // rdx
  _OWORD *v28; // rdx
  _OWORD *v29; // rcx
  __int64 v30; // r14
  const wchar_t *v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  unsigned int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rbx
  unsigned int v37; // eax
  unsigned int v38; // ebx
  __int64 v39; // r8
  bool v40; // zf
  __int64 v41; // rbx
  int v42; // r14d
  __int64 v43; // rcx
  __int64 v44; // [rsp+30h] [rbp-30h] BYREF
  __int64 v45; // [rsp+38h] [rbp-28h] BYREF
  __int64 v46; // [rsp+40h] [rbp-20h] BYREF
  __int64 v47; // [rsp+48h] [rbp-18h] BYREF
  const wchar_t *v48; // [rsp+50h] [rbp-10h]
  __int64 v51; // [rsp+B8h] [rbp+58h] BYREF

  v5 = sqlite3_context_db_handle(a1);
  v6 = *a3;
  LOBYTE(v7) = 1;
  v46 = 0;
  v8 = 0;
  v45 = 0;
  v44 = 0;
  v9 = v5;
  v47 = 0;
  v10 = sqlite3ValueText(v6, v7);
  LOBYTE(v11) = 1;
  v12 = (const wchar_t *)v10;
  v13 = sqlite3ValueText(a3[1], v11);
  v14 = &Src;
  v15 = &Src;
  if ( v12 )
    v15 = v12;
  v48 = v15;
  if ( v13 )
    v14 = (const wchar_t *)v13;
  if ( (*(_BYTE *)(v9 + 200) & 4) != 0 )
  {
    v51 = 0;
    result = (_OWORD *)sqlite3_vfs_find("memdb");
    if ( !result )
      return result;
    v17 = sqlite3BtreeOpen(result, "x", v9, &v51, 0, 256);
    if ( v17 )
      goto LABEL_13;
    v18 = v51;
    v20 = sqlite3SchemaGet(v9, v51);
    if ( !v20 )
    {
      sqlite3BtreeClose(v18);
      v17 = 7;
      goto LABEL_13;
    }
    v21 = *(_QWORD *)(v9 + 32) + 32LL * *(unsigned __int8 *)(v9 + 196);
    v22 = *(_QWORD *)(v21 + 8);
    if ( v22 )
      sqlite3BtreeClose(v22);
    *(_QWORD *)(v21 + 24) = v20;
    *(_QWORD *)(v21 + 8) = v18;
  }
  else
  {
    v24 = *(_DWORD *)(v9 + 164);
    v17 = 0;
    v25 = *(_DWORD *)(v9 + 40);
    if ( v25 >= v24 + 2 )
    {
      result = (_OWORD *)sqlite3MPrintf(v9, "too many attached databases - max %d", v24);
LABEL_18:
      v44 = (__int64)result;
LABEL_14:
      if ( !result )
      {
        v23 = a1;
LABEL_71:
        if ( v17 )
          return (_OWORD *)sqlite3_result_error_code(v23, v17);
        return result;
      }
LABEL_15:
      v23 = a1;
      sqlite3_result_error(a1, result, 0xFFFFFFFFLL);
      result = (_OWORD *)sqlite3DbFree(v9, v44);
      goto LABEL_71;
    }
    for ( i = 0; (int)i < v25; ++i )
    {
      if ( (unsigned int)sqlite3DbIsNamed(v9, i, v14) )
      {
        result = (_OWORD *)sqlite3MPrintf(v9, "database %s is already in use", v14);
        goto LABEL_18;
      }
    }
    v27 = *(_QWORD *)(v9 + 32);
    if ( v27 == v9 + 672 )
    {
      result = (_OWORD *)sqlite3DbMallocRawNN(v9, 96);
      v28 = result;
      if ( !result )
        return result;
      v29 = *(_OWORD **)(v9 + 32);
      *result = *v29;
      result[1] = v29[1];
      result[2] = v29[2];
      result[3] = v29[3];
    }
    else
    {
      result = (_OWORD *)sqlite3DbRealloc(v9, v27, 32LL * (v25 + 1));
      v28 = result;
      if ( !result )
        return result;
    }
    v30 = *(int *)(v9 + 40);
    *(_QWORD *)(v9 + 32) = v28;
    v21 = (__int64)&v28[2 * v30];
    v31 = v48;
    *(_OWORD *)v21 = 0;
    *(_OWORD *)(v21 + 16) = 0;
    v32 = *(_QWORD *)v9;
    LODWORD(v51) = *(_DWORD *)(v9 + 76);
    v33 = sqlite3ParseUri(*(_QWORD *)(v32 + 24), v31, &v51, &v47, &v46, &v45);
    if ( v33 )
    {
      if ( v33 == 7 )
        sqlite3OomFault(v9);
      sqlite3_result_error(a1, v45, 0xFFFFFFFFLL);
      return (_OWORD *)sqlite3_free(v45);
    }
    v8 = v46;
    v34 = sqlite3BtreeOpen(v47, v46, v9, v21 + 8, 0, (unsigned int)v51 | 0x100);
    ++*(_DWORD *)(v9 + 40);
    v17 = v34;
    *(_QWORD *)v21 = sqlite3DbStrDup(v9, v14);
  }
  *(_BYTE *)(v9 + 111) = 0;
  if ( v17 == 19 )
  {
    v17 = 1;
    v44 = sqlite3MPrintf(v9, "database is already attached");
  }
  else if ( !v17 )
  {
    v35 = sqlite3SchemaGet(v9, *(_QWORD *)(v21 + 8));
    *(_QWORD *)(v21 + 24) = v35;
    if ( v35 )
    {
      if ( *(_BYTE *)(v35 + 112) && *(_BYTE *)(v35 + 113) != *(_BYTE *)(v9 + 100) )
      {
        v44 = sqlite3MPrintf(v9, "attached databases must use the same text encoding as main database");
        v17 = 1;
      }
    }
    else
    {
      v17 = 7;
    }
    sqlite3BtreeEnter(*(_QWORD *)(v21 + 8));
    sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(v21 + 8) + 8LL));
    v36 = *(_QWORD *)(v21 + 8);
    v37 = sqlite3BtreeSecureDelete(*(_QWORD *)(*(_QWORD *)(v9 + 32) + 8LL), 0xFFFFFFFFLL);
    sqlite3BtreeSecureDelete(v36, v37);
    sqlite3BtreeSetPagerFlags(*(_QWORD *)(v21 + 8), *(_DWORD *)(v9 + 48) & 0x38 | 3u);
    sqlite3BtreeLeave(*(_QWORD *)(v21 + 8));
  }
  *(_BYTE *)(v21 + 16) = 3;
  if ( !v17 )
  {
    if ( *(_QWORD *)v21 )
    {
      LODWORD(v51) = 0;
      v47 = 0;
      if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a3[2] + 20) & 0x3F)) == 1
        || *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a3[2] + 20) & 0x3F)) == 2 )
      {
        v44 = sqlite3DbStrDup(v9, "Invalid key value");
        v17 = 1;
      }
      else
      {
        if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a3[2] + 20) & 0x3F)) == 3
          || *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a3[2] + 20) & 0x3F)) == 4 )
        {
          LOBYTE(v19) = 1;
          v38 = sqlite3ValueBytes(a3[2], v19);
          v39 = sqlite3_value_blob(a3[2]);
        }
        else
        {
          if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(a3[2] + 20) & 0x3F)) != 5 )
            goto LABEL_58;
          if ( (unsigned int)sqlite3CodecQueryParameters(v9, v14, v8) )
            goto LABEL_58;
          sqlite3CodecGetKey(v9, 0, &v47, &v51);
          v38 = v51;
          if ( !(_DWORD)v51 && (int)sqlite3BtreeGetRequestedReserve(*(_QWORD *)(*(_QWORD *)(v9 + 32) + 8LL)) <= 0 )
            goto LABEL_58;
          v39 = v47;
        }
        v17 = sqlite3CodecAttach(v9, (unsigned int)(*(_DWORD *)(v9 + 40) - 1), v39, v38);
      }
    }
    else
    {
      v17 = 7;
    }
  }
LABEL_58:
  sqlite3_free_filename(v8);
  if ( v17 )
    goto LABEL_62;
  sqlite3BtreeEnterAll(v9);
  *(_DWORD *)(v9 + 44) &= ~0x10u;
  v40 = (*(_BYTE *)(v9 + 200) & 4) == 0;
  *(_BYTE *)(v9 + 196) = 0;
  if ( v40 )
    v17 = sqlite3Init(v9, &v44);
  result = (_OWORD *)sqlite3BtreeLeaveAll(v9);
  if ( v17 )
  {
LABEL_62:
    if ( (*(_BYTE *)(v9 + 200) & 4) == 0 )
    {
      v41 = 32LL * *(int *)(v9 + 40);
      v42 = *(_DWORD *)(v9 + 40) - 1;
      v43 = *(_QWORD *)(v41 + *(_QWORD *)(v9 + 32) - 24);
      if ( v43 )
      {
        sqlite3BtreeClose(v43);
        *(_QWORD *)(v41 + *(_QWORD *)(v9 + 32) - 24) = 0;
        *(_QWORD *)(v41 + *(_QWORD *)(v9 + 32) - 8) = 0;
      }
      sqlite3ResetAllSchemasOfConnection(v9);
      *(_DWORD *)(v9 + 40) = v42;
      if ( v17 == 7 || v17 == 3082 )
      {
        sqlite3OomFault(v9);
        sqlite3DbFree(v9, v44);
        result = (_OWORD *)sqlite3MPrintf(v9, "out of memory");
      }
      else
      {
        result = (_OWORD *)v44;
        if ( v44 )
          goto LABEL_15;
        result = (_OWORD *)sqlite3MPrintf(v9, "unable to open database: %s", v48);
      }
      goto LABEL_18;
    }
LABEL_13:
    result = (_OWORD *)v44;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x18007a180  mov     [rsp-38h+arg_8], rbx
0x18007a185  mov     [rsp-38h+arg_10], r8
0x18007a18a  mov     [rsp-38h+arg_0], rcx
0x18007a18f  push    rbp
0x18007a190  push    rsi
0x18007a191  push    rdi
0x18007a192  push    r12
0x18007a194  push    r13
0x18007a196  push    r14
0x18007a198  push    r15
0x18007a19a  mov     rbp, rsp
0x18007a19d  sub     rsp, 60h
0x18007a1a1  mov     rsi, r8
0x18007a1a4  mov     r15, rcx
0x18007a1a7  call    sqlite3_context_db_handle
0x18007a1ac  mov     rcx, [rsi]
0x18007a1af  xor     r14d, r14d
0x18007a1b2  mov     dl, 1
0x18007a1b4  mov     [rbp+var_20], r14
0x18007a1b8  mov     r13d, r14d
0x18007a1bb  mov     [rbp+var_28], r14
0x18007a1bf  mov     [rbp+var_30], r14
0x18007a1c3  mov     rdi, rax
0x18007a1c6  mov     [rbp+var_18], r14
0x18007a1ca  call    sqlite3ValueText
0x18007a1cf  mov     rcx, [rsi+8]
0x18007a1d3  mov     dl, 1
0x18007a1d5  mov     rbx, rax
0x18007a1d8  call    sqlite3ValueText
0x18007a1dd  test    rbx, rbx
0x18007a1e0  lea     r12, Src
0x18007a1e7  mov     rcx, r12
0x18007a1ea  cmovnz  rcx, rbx
0x18007a1ee  test    rax, rax
0x18007a1f1  mov     [rbp+var_10], rcx
0x18007a1f5  cmovnz  r12, rax
0x18007a1f9  test    byte ptr [rdi+0C8h], 4
0x18007a200  jz      loc_18007A2CE
0x18007a206  lea     rcx, aMemdb; "memdb"
0x18007a20d  mov     [rbp+arg_18], r14
0x18007a211  call    sqlite3_vfs_find
0x18007a216  test    rax, rax
0x18007a219  jz      loc_18007A6FE
0x18007a21f  mov     dword ptr [rsp+60h+var_38], 100h
0x18007a227  lea     r9, [rbp+arg_18]
0x18007a22b  mov     r8, rdi
0x18007a22e  mov     dword ptr [rsp+60h+var_40], r13d
0x18007a233  lea     rdx, asc_1800BA3DC; "x"
0x18007a23a  mov     rcx, rax
0x18007a23d  call    sqlite3BtreeOpen
0x18007a242  mov     esi, eax
0x18007a244  test    eax, eax
0x18007a246  jnz     short loc_18007A29D
0x18007a248  mov     rbx, [rbp+arg_18]
0x18007a24c  mov     rcx, rdi
0x18007a24f  mov     rdx, rbx
0x18007a252  call    sqlite3SchemaGet
0x18007a257  mov     r15, rax
0x18007a25a  test    rax, rax
0x18007a25d  jz      short loc_18007A290
0x18007a25f  movzx   r14d, byte ptr [rdi+0C4h]
0x18007a267  shl     r14, 5
0x18007a26b  add     r14, [rdi+20h]
0x18007a26f  mov     rcx, [r14+8]
0x18007a273  test    rcx, rcx
0x18007a276  jz      short loc_18007A27D
0x18007a278  call    sqlite3BtreeClose
0x18007a27d  mov     [r14+18h], r15
0x18007a281  mov     r15d, 1
0x18007a287  mov     [r14+8], rbx
0x18007a28b  jmp     loc_18007A44A
0x18007a290  mov     rcx, rbx
0x18007a293  call    sqlite3BtreeClose
0x18007a298  mov     esi, 7
0x18007a29d  mov     rax, [rbp+var_30]
0x18007a2a1  test    rax, rax
0x18007a2a4  jz      loc_18007A6EC
0x18007a2aa  mov     rbx, [rbp+arg_0]
0x18007a2ae  or      r8d, 0FFFFFFFFh
0x18007a2b2  mov     rcx, rbx
0x18007a2b5  mov     rdx, rax
0x18007a2b8  call    sqlite3_result_error
0x18007a2bd  mov     rdx, [rbp+var_30]
0x18007a2c1  mov     rcx, rdi
0x18007a2c4  call    sqlite3DbFree
0x18007a2c9  jmp     loc_18007A6F0
0x18007a2ce  mov     r8d, [rdi+0A4h]
0x18007a2d5  mov     esi, r14d
0x18007a2d8  mov     r14d, [rdi+28h]
0x18007a2dc  lea     eax, [r8+2]
0x18007a2e0  cmp     r14d, eax
0x18007a2e3  jl      short loc_18007A2FA
0x18007a2e5  lea     rdx, aTooManyAttache; "too many attached databases - max %d"
0x18007a2ec  mov     rcx, rdi
0x18007a2ef  call    sqlite3MPrintf
0x18007a2f4  mov     [rbp+var_30], rax
0x18007a2f8  jmp     short loc_18007A2A1
0x18007a2fa  xor     ebx, ebx
0x18007a2fc  mov     rcx, rdi
0x18007a2ff  cmp     ebx, r14d
0x18007a302  jge     short loc_18007A32A
0x18007a304  mov     r8, r12
0x18007a307  mov     edx, ebx
0x18007a309  call    sqlite3DbIsNamed
0x18007a30e  test    eax, eax
0x18007a310  jnz     short loc_18007A316
0x18007a312  inc     ebx
0x18007a314  jmp     short loc_18007A2FC
0x18007a316  mov     r8, r12
0x18007a319  lea     rdx, aDatabaseSIsAlr; "database %s is already in use"
0x18007a320  mov     rcx, rdi
0x18007a323  call    sqlite3MPrintf
0x18007a328  jmp     short loc_18007A2F4
0x18007a32a  mov     rdx, [rdi+20h]
0x18007a32e  lea     rax, [rdi+2A0h]
0x18007a335  cmp     rdx, rax
0x18007a338  jnz     short loc_18007A374
0x18007a33a  mov     edx, 60h ; '`'
0x18007a33f  call    sqlite3DbMallocRawNN
0x18007a344  mov     rdx, rax
0x18007a347  test    rax, rax
0x18007a34a  jz      loc_18007A6FE
0x18007a350  mov     rcx, [rdi+20h]
0x18007a354  movups  xmm0, xmmword ptr [rcx]
0x18007a357  movups  xmmword ptr [rax], xmm0
0x18007a35a  movups  xmm1, xmmword ptr [rcx+10h]
0x18007a35e  movups  xmmword ptr [rax+10h], xmm1
0x18007a362  movups  xmm0, xmmword ptr [rcx+20h]
0x18007a366  movups  xmmword ptr [rax+20h], xmm0
0x18007a36a  movups  xmm1, xmmword ptr [rcx+30h]
0x18007a36e  movups  xmmword ptr [rax+30h], xmm1
0x18007a372  jmp     short loc_18007A390
0x18007a374  lea     eax, [r14+1]
0x18007a378  movsxd  r8, eax
0x18007a37b  shl     r8, 5
0x18007a37f  call    sqlite3DbRealloc
0x18007a384  mov     rdx, rax
0x18007a387  test    rax, rax
0x18007a38a  jz      loc_18007A6FE
0x18007a390  movsxd  r14, dword ptr [rdi+28h]
0x18007a394  lea     r9, [rbp+var_18]
0x18007a398  mov     [rdi+20h], rdx
0x18007a39c  lea     r8, [rbp+arg_18]
0x18007a3a0  xorps   xmm0, xmm0
0x18007a3a3  shl     r14, 5
0x18007a3a7  add     r14, rdx
0x18007a3aa  mov     rdx, [rbp+var_10]
0x18007a3ae  movups  xmmword ptr [r14], xmm0
0x18007a3b2  movups  xmmword ptr [r14+10h], xmm0
0x18007a3b7  mov     eax, [rdi+4Ch]
0x18007a3ba  mov     rcx, [rdi]
0x18007a3bd  mov     dword ptr [rbp+arg_18], eax
0x18007a3c0  lea     rax, [rbp+var_28]
0x18007a3c4  mov     [rsp+60h+var_38], rax
0x18007a3c9  lea     rax, [rbp+var_20]
0x18007a3cd  mov     [rsp+60h+var_40], rax
0x18007a3d2  mov     rcx, [rcx+18h]
0x18007a3d6  call    sqlite3ParseUri
0x18007a3db  test    eax, eax
0x18007a3dd  jz      short loc_18007A40A
0x18007a3df  cmp     eax, 7
0x18007a3e2  jnz     short loc_18007A3EC
0x18007a3e4  mov     rcx, rdi
0x18007a3e7  call    sqlite3OomFault
0x18007a3ec  mov     rdx, [rbp+var_28]
0x18007a3f0  or      r8d, 0FFFFFFFFh
0x18007a3f4  mov     rcx, r15
0x18007a3f7  call    sqlite3_result_error
0x18007a3fc  mov     rcx, [rbp+var_28]
0x18007a400  call    sqlite3_free
0x18007a405  jmp     loc_18007A6FE
0x18007a40a  mov     eax, dword ptr [rbp+arg_18]
0x18007a40d  lea     r9, [r14+8]
0x18007a411  mov     r13, [rbp+var_20]
0x18007a415  bts     eax, 8
0x18007a419  mov     rcx, [rbp+var_18]
0x18007a41d  mov     r8, rdi
0x18007a420  mov     dword ptr [rsp+60h+var_38], eax
0x18007a424  mov     rdx, r13
0x18007a427  mov     dword ptr [rsp+60h+var_40], esi
0x18007a42b  call    sqlite3BtreeOpen
0x18007a430  mov     r15d, 1
0x18007a436  mov     rdx, r12
0x18007a439  add     [rdi+28h], r15d
0x18007a43d  mov     rcx, rdi
0x18007a440  mov     esi, eax
0x18007a442  call    sqlite3DbStrDup
0x18007a447  mov     [r14], rax
0x18007a44a  mov     byte ptr [rdi+6Fh], 0
0x18007a44e  cmp     esi, 13h
0x18007a451  jnz     short loc_18007A46E
0x18007a453  lea     rdx, aDatabaseIsAlre; "database is already attached"
0x18007a45a  mov     rcx, rdi
0x18007a45d  mov     esi, r15d
0x18007a460  call    sqlite3MPrintf
0x18007a465  mov     [rbp+var_30], rax
0x18007a469  jmp     loc_18007A50D
0x18007a46e  test    esi, esi
0x18007a470  jnz     loc_18007A50D
0x18007a476  mov     rdx, [r14+8]
0x18007a47a  mov     rcx, rdi
0x18007a47d  call    sqlite3SchemaGet
0x18007a482  mov     [r14+18h], rax
0x18007a486  mov     rcx, rax
0x18007a489  test    rax, rax
0x18007a48c  jnz     short loc_18007A493
0x18007a48e  lea     esi, [rax+7]
0x18007a491  jmp     short loc_18007A4B7
0x18007a493  cmp     byte ptr [rax+70h], 0
0x18007a497  jz      short loc_18007A4B7
0x18007a499  mov     al, [rdi+64h]
0x18007a49c  cmp     [rcx+71h], al
0x18007a49f  jz      short loc_18007A4B7
0x18007a4a1  lea     rdx, aAttachedDataba; "attached databases must use the same te"...
0x18007a4a8  mov     rcx, rdi
0x18007a4ab  call    sqlite3MPrintf
0x18007a4b0  mov     [rbp+var_30], rax
0x18007a4b4  mov     esi, r15d
0x18007a4b7  mov     rcx, [r14+8]
0x18007a4bb  call    sqlite3BtreeEnter
0x18007a4c0  mov     rax, [r14+8]
0x18007a4c4  movzx   edx, byte ptr [rdi+69h]
0x18007a4c8  mov     rcx, [rax+8]
0x18007a4cc  mov     rcx, [rcx]
0x18007a4cf  call    sqlite3PagerLockingMode
0x18007a4d4  mov     rcx, [rdi+20h]
0x18007a4d8  or      edx, 0FFFFFFFFh
0x18007a4db  mov     rbx, [r14+8]
0x18007a4df  mov     rcx, [rcx+8]
0x18007a4e3  call    sqlite3BtreeSecureDelete
0x18007a4e8  mov     edx, eax
0x18007a4ea  mov     rcx, rbx
0x18007a4ed  call    sqlite3BtreeSecureDelete
0x18007a4f2  mov     edx, [rdi+30h]
0x18007a4f5  mov     rcx, [r14+8]
0x18007a4f9  and     edx, 38h
0x18007a4fc  or      edx, 3
0x18007a4ff  call    sqlite3BtreeSetPagerFlags
0x18007a504  mov     rcx, [r14+8]
0x18007a508  call    sqlite3BtreeLeave
0x18007a50d  mov     byte ptr [r14+10h], 3
0x18007a512  test    esi, esi
0x18007a514  jnz     loc_18007A5FF
0x18007a51a  cmp     qword ptr [r14], 0
0x18007a51e  jnz     short loc_18007A52A
0x18007a520  mov     esi, 7
0x18007a525  jmp     loc_18007A5FF
0x18007a52a  mov     r14, [rbp+arg_10]
0x18007a52e  lea     rcx, qword_1800B5270
0x18007a535  mov     dword ptr [rbp+arg_18], 0
0x18007a53c  mov     [rbp+var_18], 0
0x18007a544  mov     r8, [r14+10h]
0x18007a548  movzx   eax, word ptr [r8+14h]
0x18007a54d  and     eax, 3Fh
0x18007a550  movzx   ecx, byte ptr [rax+rcx]
0x18007a554  sub     ecx, 1
0x18007a557  jz      loc_18007A5E9
0x18007a55d  sub     ecx, 1
0x18007a560  jz      loc_18007A5E9
0x18007a566  sub     ecx, 1
0x18007a569  jz      short loc_18007A5BB
0x18007a56b  sub     ecx, 1
0x18007a56e  jz      short loc_18007A5BB
0x18007a570  cmp     ecx, 1
0x18007a573  jnz     loc_18007A5FF
0x18007a579  mov     r8, r13
0x18007a57c  mov     rdx, r12
0x18007a57f  mov     rcx, rdi
0x18007a582  call    sqlite3CodecQueryParameters
0x18007a587  test    eax, eax
0x18007a589  jnz     short loc_18007A5FF
0x18007a58b  lea     r9, [rbp+arg_18]
0x18007a58f  xor     edx, edx
0x18007a591  lea     r8, [rbp+var_18]
0x18007a595  mov     rcx, rdi
0x18007a598  call    sqlite3CodecGetKey
0x18007a59d  mov     ebx, dword ptr [rbp+arg_18]
0x18007a5a0  test    ebx, ebx
0x18007a5a2  jnz     short loc_18007A5B5
0x18007a5a4  mov     rcx, [rdi+20h]
0x18007a5a8  mov     rcx, [rcx+8]
0x18007a5ac  call    sqlite3BtreeGetRequestedReserve
0x18007a5b1  test    eax, eax
0x18007a5b3  jle     short loc_18007A5FF
0x18007a5b5  mov     r8, [rbp+var_18]
0x18007a5b9  jmp     short loc_18007A5D4
0x18007a5bb  mov     dl, r15b
0x18007a5be  mov     rcx, r8
0x18007a5c1  call    sqlite3ValueBytes
0x18007a5c6  mov     rcx, [r14+10h]
0x18007a5ca  mov     ebx, eax
0x18007a5cc  call    sqlite3_value_blob
0x18007a5d1  mov     r8, rax
0x18007a5d4  mov     edx, [rdi+28h]
0x18007a5d7  mov     r9d, ebx
0x18007a5da  sub     edx, r15d
0x18007a5dd  mov     rcx, rdi
0x18007a5e0  call    sqlite3CodecAttach
0x18007a5e5  mov     esi, eax
0x18007a5e7  jmp     short loc_18007A5FF
  ... truncated ...
```
