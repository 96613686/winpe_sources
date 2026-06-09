# CDateRuleReader::ReadRulePath(RULE_PATH_INFO const *,CReadResult * *)

- ea: `0x18000c300`
- end: `0x18000c583`
- name: `?ReadRulePath@CDateRuleReader@@UEAAJPEBURULE_PATH_INFO@@PEAPEAVCReadResult@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(CDateRuleReader *__hidden this, const struct RULE_PATH_INFO *, struct CReadResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000c300`
- `0x18000c58c`
- `0x18000c7bc`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c433`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c504`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c433`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c504`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c38f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c3fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c406`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c411`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c38f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c3fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c406`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c411`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDateRuleReader::ReadRulePath(
        CDateRuleReader *this,
        const struct RULE_PATH_INFO *a2,
        struct CReadResult **a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  char *v11; // rax
  __int128 v12; // xmm0
  BYTE *v13; // xmm1_8
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rdx
  char *v17; // rax
  __int128 v18; // xmm0
  BYTE *pData; // xmm1_8
  PROPVARIANT v20; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-11h] BYREF
  PROPVARIANT v22; // [rsp+60h] [rbp+7h] BYREF

  memset(&v22, 0, sizeof(v22));
  *a3 = 0;
  v6 = *((_DWORD *)a2 + 3);
  if ( v6 == 4 || v6 == 9 )
  {
    memset(&pvar, 0, sizeof(pvar));
    memset(&v20, 0, sizeof(v20));
    v9 = (*(__int64 (__fastcall **)(CDateRuleReader *, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
           this,
           *((_QWORD *)a2 + 3),
           *((unsigned int *)a2 + 2),
           0,
           &pvar);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( !g_doStackCaptures )
      {
LABEL_10:
        PropVariantClear(&v20);
        PropVariantClear(&pvar);
        goto LABEL_11;
      }
      goto LABEL_16;
    }
    v16 = *((_QWORD *)a2 + 4);
    if ( v16 )
      (*(void (__fastcall **)(CDateRuleReader *, __int64, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
        this,
        v16,
        *((unsigned int *)a2 + 2),
        0,
        &v20);
    if ( *((_DWORD *)a2 + 3) == 9 )
    {
      v9 = ConvertIPTCDateTimeStringsOnRead(&pvar, &v20, &v22);
      v8 = v9;
      if ( v9 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_10;
        goto LABEL_16;
      }
    }
    else
    {
      v9 = ConvertExifDateStringsOnRead(&pvar, &v20, &v22);
      v8 = v9;
      if ( v9 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_10;
LABEL_16:
        v15 = v9;
LABEL_17:
        DoStackCapture(v15);
        goto LABEL_10;
      }
    }
    v17 = (char *)LocalAlloc(0x40u, 0x20u);
    if ( v17 )
    {
      v18 = *(_OWORD *)&v22.vt;
      pData = v22.bstrblobVal.pData;
      *(_QWORD *)v17 = &CReadResult::`vftable';
      *(_OWORD *)(v17 + 8) = v18;
      *((_QWORD *)v17 + 3) = pData;
      *a3 = (struct CReadResult *)v17;
      memset(&v22, 0, sizeof(v22));
      goto LABEL_10;
    }
    *a3 = 0;
    v8 = -2147024882;
    if ( !g_doStackCaptures )
      goto LABEL_10;
    v15 = -2147024882;
    goto LABEL_17;
  }
  memset(&pvar, 0, sizeof(pvar));
  v7 = (*(__int64 (__fastcall **)(CDateRuleReader *, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
         this,
         *((_QWORD *)a2 + 3),
         *((unsigned int *)a2 + 2),
         *((unsigned int *)a2 + 3),
         &pvar);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v11 = (char *)LocalAlloc(0x40u, 0x20u);
    if ( v11 )
    {
      v12 = *(_OWORD *)&pvar.vt;
      v13 = pvar.bstrblobVal.pData;
      *(_QWORD *)v11 = &CReadResult::`vftable';
      *(_OWORD *)(v11 + 8) = v12;
      *((_QWORD *)v11 + 3) = v13;
      *a3 = (struct CReadResult *)v11;
      memset(&pvar, 0, sizeof(pvar));
      goto LABEL_5;
    }
    *a3 = 0;
    v8 = -2147024882;
    if ( !g_doStackCaptures )
      goto LABEL_5;
    v14 = -2147024882;
LABEL_15:
    DoStackCapture(v14);
    goto LABEL_5;
  }
  if ( g_doStackCaptures )
  {
    v14 = v7;
    goto LABEL_15;
  }
LABEL_5:
  PropVariantClear(&pvar);
  if ( v8 < 0 && g_doStackCaptures )
    DoStackCapture(v8);
LABEL_11:
  PropVariantClear(&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c300  push    rbp
0x18000c302  push    rbx
0x18000c303  push    rsi
0x18000c304  push    rdi
0x18000c305  push    r14
0x18000c307  push    r15
0x18000c309  lea     rbp, [rsp-2Fh]
0x18000c30e  sub     rsp, 88h
0x18000c315  mov     rsi, r8
0x18000c318  mov     rdi, rdx
0x18000c31b  mov     r14, rcx
0x18000c31e  xorps   xmm0, xmm0
0x18000c321  xor     eax, eax
0x18000c323  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000c327  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18000c32b  xor     r15d, r15d
0x18000c32e  mov     [r8], r15
0x18000c331  mov     eax, [rdx+0Ch]
0x18000c334  cmp     eax, 4
0x18000c337  jz      short loc_18000C3AB
0x18000c339  cmp     eax, 9
0x18000c33c  jz      short loc_18000C3AB
0x18000c33e  xor     eax, eax
0x18000c340  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000c344  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000c348  mov     rax, [rcx]
0x18000c34b  lea     rcx, [rbp+57h+pvar]
0x18000c34f  mov     [rsp+0B0h+var_90], rcx
0x18000c354  mov     r9d, [rdx+0Ch]
0x18000c358  mov     r8d, [rdx+8]
0x18000c35c  mov     rdx, [rdx+18h]
0x18000c360  mov     rcx, r14
0x18000c363  mov     rax, [rax+40h]
0x18000c367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c36c  mov     ebx, eax
0x18000c36e  test    eax, eax
0x18000c370  jns     loc_18000C429
0x18000c376  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000c37d  jnz     loc_18000C473
0x18000c383  test    eax, eax
0x18000c385  jns     loc_18000C429
0x18000c38b  lea     rcx, [rbp+57h+pvar]; pvar
0x18000c38f  call    cs:__imp_PropVariantClear
0x18000c395  test    ebx, ebx
0x18000c397  jns     short loc_18000C40D
0x18000c399  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c3a0  jz      short loc_18000C40D
0x18000c3a2  mov     ecx, ebx; int
0x18000c3a4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c3a9  jmp     short loc_18000C40D
0x18000c3ab  xor     eax, eax
0x18000c3ad  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000c3b1  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000c3b5  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18000c3b9  mov     qword ptr [rbp+57h+var_80+10h], rax
0x18000c3bd  mov     rax, [rcx]
0x18000c3c0  lea     rcx, [rbp+57h+pvar]
0x18000c3c4  mov     [rsp+0B0h+var_90], rcx
0x18000c3c9  xor     r9d, r9d
0x18000c3cc  mov     r8d, [rdx+8]
0x18000c3d0  mov     rdx, [rdx+18h]
0x18000c3d4  mov     rcx, r14
0x18000c3d7  mov     rax, [rax+40h]
0x18000c3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e0  mov     ebx, eax
0x18000c3e2  test    eax, eax
0x18000c3e4  jns     loc_18000C4A4
0x18000c3ea  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c3f1  jnz     loc_18000C47F
0x18000c3f7  lea     rcx, [rbp+57h+var_80]; pvar
0x18000c3fb  call    cs:__imp_PropVariantClear
0x18000c401  nop
0x18000c402  lea     rcx, [rbp+57h+pvar]; pvar
0x18000c406  call    cs:__imp_PropVariantClear
0x18000c40c  nop
0x18000c40d  lea     rcx, [rbp+57h+var_50]; pvar
0x18000c411  call    cs:__imp_PropVariantClear
0x18000c417  mov     eax, ebx
0x18000c419  add     rsp, 88h
0x18000c420  pop     r15
0x18000c422  pop     r14
0x18000c424  pop     rdi
0x18000c425  pop     rsi
0x18000c426  pop     rbx
0x18000c427  pop     rbp
0x18000c428  retn
0x18000c429  mov     edx, 20h ; ' '; uBytes
0x18000c42e  mov     ecx, 40h ; '@'; uFlags
0x18000c433  call    cs:__imp_LocalAlloc
0x18000c439  mov     [rbp+57h+arg_8], rax
0x18000c43d  test    rax, rax
0x18000c440  jz      short loc_18000C48B
0x18000c442  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x18000c446  movsd   xmm1, qword ptr [rbp+57h+pvar+10h]
0x18000c44b  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x18000c452  mov     [rax], rcx
0x18000c455  movups  xmmword ptr [rax+8], xmm0
0x18000c459  movsd   qword ptr [rax+18h], xmm1
0x18000c45e  mov     [rsi], rax
0x18000c461  xorps   xmm0, xmm0
0x18000c464  xor     eax, eax
0x18000c466  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000c46a  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000c46e  jmp     loc_18000C38B
0x18000c473  mov     ecx, eax; int
0x18000c475  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c47a  jmp     loc_18000C38B
0x18000c47f  mov     ecx, eax; int
0x18000c481  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c486  jmp     loc_18000C3F7
0x18000c48b  mov     [rsi], r15
0x18000c48e  mov     ebx, 8007000Eh
0x18000c493  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c49a  jz      loc_18000C38B
0x18000c4a0  mov     ecx, ebx
0x18000c4a2  jmp     short loc_18000C475
0x18000c4a4  mov     rdx, [rdi+20h]
0x18000c4a8  test    rdx, rdx
0x18000c4ab  jz      short loc_18000C4CC
0x18000c4ad  mov     rax, [r14]
0x18000c4b0  lea     rcx, [rbp+57h+var_80]
0x18000c4b4  mov     [rsp+0B0h+var_90], rcx
0x18000c4b9  xor     r9d, r9d
0x18000c4bc  mov     r8d, [rdi+8]
0x18000c4c0  mov     rcx, r14
0x18000c4c3  mov     rax, [rax+40h]
0x18000c4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4cc  lea     r8, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18000c4d0  lea     rdx, [rbp+57h+var_80]; struct tagPROPVARIANT *
0x18000c4d4  lea     rcx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18000c4d8  cmp     dword ptr [rdi+0Ch], 9
0x18000c4dc  jnz     short loc_18000C544
0x18000c4de  call    ?ConvertIPTCDateTimeStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z; ConvertIPTCDateTimeStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000c4e3  mov     ebx, eax
0x18000c4e5  test    eax, eax
0x18000c4e7  jns     short loc_18000C4FA
0x18000c4e9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c4f0  jnz     short loc_18000C47F
0x18000c4f2  test    eax, eax
0x18000c4f4  js      loc_18000C3F7
0x18000c4fa  mov     edx, 20h ; ' '; uBytes
0x18000c4ff  mov     ecx, 40h ; '@'; uFlags
0x18000c504  call    cs:__imp_LocalAlloc
0x18000c50a  mov     [rbp+57h+arg_8], rax
0x18000c50e  test    rax, rax
0x18000c511  jz      short loc_18000C566
0x18000c513  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x18000c517  movsd   xmm1, qword ptr [rbp+57h+var_50+10h]
0x18000c51c  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x18000c523  mov     [rax], rcx
0x18000c526  movups  xmmword ptr [rax+8], xmm0
0x18000c52a  movsd   qword ptr [rax+18h], xmm1
0x18000c52f  mov     [rsi], rax
0x18000c532  xorps   xmm0, xmm0
0x18000c535  xor     eax, eax
0x18000c537  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000c53b  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18000c53f  jmp     loc_18000C3F7
0x18000c544  call    ?ConvertExifDateStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z; ConvertExifDateStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000c549  mov     ebx, eax
0x18000c54b  test    eax, eax
0x18000c54d  jns     short loc_18000C4FA
0x18000c54f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c556  jnz     loc_18000C47F
0x18000c55c  test    eax, eax
0x18000c55e  js      loc_18000C3F7
0x18000c564  jmp     short loc_18000C4FA
0x18000c566  mov     [rsi], r15
0x18000c569  mov     ebx, 8007000Eh
0x18000c56e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c575  jz      loc_18000C3F7
0x18000c57b  mov     ecx, ebx
0x18000c57d  jmp     loc_18000C481
```
