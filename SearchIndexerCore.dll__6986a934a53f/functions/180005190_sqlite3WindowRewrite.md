# sqlite3WindowRewrite

- ea: `0x180005190`
- end: `0x18000564a`
- name: `sqlite3WindowRewrite`
- size: `1210`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180005650`

## callees

- `0x180001980`
- `0x180005190`
- `0x180014270`
- `0x1800142d0`
- `0x180015eb0`
- `0x1800168c0`
- `0x180018f60`
- `0x180018fd0`
- `0x18001b16c`
- `0x18001b818`
- `0x18001bc40`
- `0x18001f8f0`
- `0x18003d380`
- `0x180055fc0`
- `0x1800579e4`
- `0x180057c70`
- `0x18005ddec`
- `0x180070e90`
- `0x18007e270`
- `0x18008ece4`

## pseudocode

```c
__int64 __fastcall sqlite3WindowRewrite(__int64 *a1, __int64 a2)
{
  unsigned int v4; // r12d
  __int64 Vdbe; // rax
  __int64 v7; // r13
  __int64 v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rdx
  __int64 appended; // rax
  _DWORD *v12; // rax
  __int64 v13; // r9
  _DWORD *v14; // r15
  _DWORD *v15; // rcx
  int v16; // esi
  int v17; // r8d
  _DWORD *v18; // rdx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // r12d
  _DWORD *v24; // rsi
  int v25; // ebx
  __int64 v26; // r15
  __int64 v27; // r8
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  int v32; // ecx
  int v33; // eax
  int v34; // eax
  int v35; // r9d
  __int64 v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // rcx
  _DWORD *v41; // [rsp+50h] [rbp-49h] BYREF
  __int64 v42; // [rsp+58h] [rbp-41h]
  __int64 v43; // [rsp+60h] [rbp-39h]
  __int128 v44; // [rsp+68h] [rbp-31h] BYREF
  __int128 v45; // [rsp+78h] [rbp-21h]
  __int128 v46; // [rsp+88h] [rbp-11h]
  __int64 v47; // [rsp+98h] [rbp-1h]
  _DWORD *v48; // [rsp+A0h] [rbp+7h]
  __int64 v49; // [rsp+A8h] [rbp+Fh]
  __int64 v50; // [rsp+B0h] [rbp+17h]
  __int64 v51; // [rsp+B8h] [rbp+1Fh]
  int v53; // [rsp+118h] [rbp+7Fh]

  v4 = 0;
  if ( !*(_QWORD *)(a2 + 112)
    || *(_QWORD *)(a2 + 80)
    || (*(_DWORD *)(a2 + 4) & 0x100000) != 0
    || *((_BYTE *)a1 + 308) >= 2u )
  {
    return v4;
  }
  Vdbe = sqlite3GetVdbe(a1);
  v7 = *a1;
  v8 = *(_QWORD *)(a2 + 112);
  v47 = Vdbe;
  v43 = *(_QWORD *)(a2 + 40);
  v51 = *(_QWORD *)(a2 + 48);
  v50 = *(_QWORD *)(a2 + 56);
  v49 = *(_QWORD *)(a2 + 64);
  v53 = *(_DWORD *)(a2 + 4);
  v41 = 0;
  v42 = v8;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v9 = sqlite3DbMallocZero(v7, 104);
  if ( v9 )
  {
    *((_QWORD *)&v45 + 1) = 0;
    *((_QWORD *)&v44 + 1) = agginfoPersistExprCb;
    *(_QWORD *)&v44 = a1;
    *(_QWORD *)&v45 = _scrt_stub_for_is_c_termination_complete;
    v46 = 0;
    sqlite3WalkSelect(&v44, a2);
    if ( (*(_BYTE *)(a2 + 4) & 8) == 0 )
    {
      v10 = *(_QWORD *)(a2 + 72);
      *((_QWORD *)&v44 + 1) = disallowAggregatesInOrderByCb;
      *(_QWORD *)&v45 = 0;
      sqlite3WalkExprList(&v44, v10);
    }
    *(_DWORD *)(a2 + 4) &= ~8u;
    *(_DWORD *)(a2 + 4) |= 0x100000u;
    *(_QWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    appended = exprListAppendList(a1, 0, *(_QWORD *)(v8 + 16), 1);
    v12 = (_DWORD *)exprListAppendList(a1, appended, *(_QWORD *)(v8 + 24), 1);
    v48 = v12;
    v14 = v12;
    if ( v12 )
    {
      v15 = *(_DWORD **)(a2 + 72);
      if ( v15 )
      {
        v16 = *v12;
        if ( *v15 <= *v12 )
        {
          *v12 = *v15;
          if ( !(unsigned int)sqlite3ExprListCompare(v12, *(_QWORD *)(a2 + 72), 0xFFFFFFFFLL, v13) )
          {
            sqlite3ExprListDeleteGeneric(v7, *(_QWORD *)(a2 + 72));
            *(_QWORD *)(a2 + 72) = 0;
          }
          *v14 = v16;
        }
        v8 = v42;
      }
    }
    v17 = v43;
    *(_DWORD *)(v8 + 88) = *((_DWORD *)a1 + 13);
    *((_DWORD *)a1 + 13) += 4;
    selectWindowRewriteEList((_DWORD)a1, v8, v17, *(_QWORD *)(a2 + 32), v9, (__int64)&v41);
    selectWindowRewriteEList((_DWORD)a1, v8, v43, *(_QWORD *)(a2 + 72), v9, (__int64)&v41);
    v18 = v41;
    if ( v41 )
      v19 = *v41;
    else
      v19 = 0;
    v20 = *(_QWORD *)(v8 + 16);
    *(_DWORD *)(v8 + 120) = v19;
    v21 = exprListAppendList(a1, v18, v20, 0);
    v22 = exprListAppendList(a1, v21, *(_QWORD *)(v8 + 24), 0);
    v23 = v42;
    v24 = (_DWORD *)v22;
    v25 = v43;
    v26 = v42;
    v41 = (_DWORD *)v22;
    do
    {
      v27 = *(_QWORD *)(*(_QWORD *)(v26 + 112) + 32LL);
      if ( (*(_DWORD *)(*(_QWORD *)(v26 + 80) + 4LL) & 0x100000) != 0 )
      {
        selectWindowRewriteEList((_DWORD)a1, v23, v25, *(_QWORD *)(*(_QWORD *)(v26 + 112) + 32LL), v9, (__int64)&v41);
        v24 = v41;
        if ( v41 )
          v28 = *v41;
        else
          v28 = 0;
        *(_DWORD *)(v26 + 124) = v28;
        *(_BYTE *)(v26 + 140) = 1;
      }
      else
      {
        if ( v24 )
          v29 = *v24;
        else
          v29 = 0;
        *(_DWORD *)(v26 + 124) = v29;
        v24 = (_DWORD *)exprListAppendList(a1, v24, v27, 0);
        v41 = v24;
      }
      v30 = *(_QWORD *)(v26 + 72);
      if ( v30 )
      {
        v31 = sqlite3ExprDup(v7, v30, 0);
        v24 = (_DWORD *)sqlite3ExprListAppend(a1, v24, v31);
        v41 = v24;
      }
      v32 = v47;
      v33 = *((_DWORD *)a1 + 14) + 1;
      *((_DWORD *)a1 + 14) = v33;
      *(_DWORD *)(v26 + 92) = v33;
      v34 = *((_DWORD *)a1 + 14) + 1;
      *((_DWORD *)a1 + 14) = v34;
      v35 = *(_DWORD *)(v26 + 92);
      *(_DWORD *)(v26 + 96) = v34;
      sqlite3VdbeAddOp3(v32, 75, 0, v35, 0);
      v26 = *(_QWORD *)(v26 + 64);
    }
    while ( v26 );
    v4 = 0;
    if ( !v24 )
    {
      v36 = sqlite3Expr(v7, 155, "0");
      LODWORD(v24) = sqlite3ExprListAppend(a1, 0, v36);
    }
    v37 = sqlite3SelectNew((_DWORD)a1, (_DWORD)v24, v43, v51, v50, v49, (__int64)v48, 0, 0);
    v38 = sqlite3SrcListAppend(a1, 0, 0, 0);
    *(_QWORD *)(a2 + 40) = v38;
    if ( v38 )
    {
      *(_QWORD *)(v38 + 48) = v37;
      *(_DWORD *)(*(_QWORD *)(a2 + 40) + 72LL) |= 8u;
      sqlite3SrcListAssignCursors(a1, *(_QWORD *)(a2 + 40));
      *(_DWORD *)(v37 + 4) |= 0x8000040u;
      LOBYTE(v39) = 64;
      v40 = sqlite3ResultSetOfSelect(a1, v37, v39);
      *(_DWORD *)(v37 + 4) |= v53 & 8;
      if ( v40 )
      {
        *(_OWORD *)v9 = *(_OWORD *)v40;
        *(_OWORD *)(v9 + 16) = *(_OWORD *)(v40 + 16);
        *(_OWORD *)(v9 + 32) = *(_OWORD *)(v40 + 32);
        *(_OWORD *)(v9 + 48) = *(_OWORD *)(v40 + 48);
        *(_OWORD *)(v9 + 64) = *(_OWORD *)(v40 + 64);
        *(_OWORD *)(v9 + 80) = *(_OWORD *)(v40 + 80);
        *(_QWORD *)(v9 + 96) = *(_QWORD *)(v40 + 96);
        *(_DWORD *)(v9 + 48) |= 0x4000u;
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 40LL) = v9;
        *((_QWORD *)&v44 + 1) = sqlite3WindowExtraAggFuncDepth;
        v9 = v40;
        *(_QWORD *)&v44 = 0;
        *(_QWORD *)&v45 = sqlite3WalkerDepthIncrease;
        *((_QWORD *)&v45 + 1) = sqlite3WalkerDepthDecrease;
        v46 = 0;
        sqlite3WalkSelect(&v44, v37);
      }
      else
      {
        v4 = 7;
      }
    }
    else
    {
      sqlite3SelectDelete((_QWORD *)v7, (__int64 *)v37);
    }
    if ( *(_BYTE *)(v7 + 103) )
      v4 = 7;
    sqlite3ParserAddCleanup(a1, sqlite3DbFree, v9);
    return v4;
  }
  return sqlite3ErrorToParser(v7, 7);
}

```

## disassembly

```asm
0x180005190  mov     [rsp-8+arg_0], rbx
0x180005195  mov     [rsp-8+arg_8], rdx
0x18000519a  push    rbp
0x18000519b  push    rsi
0x18000519c  push    rdi
0x18000519d  push    r12
0x18000519f  push    r13
0x1800051a1  push    r14
0x1800051a3  push    r15
0x1800051a5  lea     rbp, [rsp-27h]
0x1800051aa  sub     rsp, 0C0h
0x1800051b1  xor     r15d, r15d
0x1800051b4  mov     rbx, rdx
0x1800051b7  mov     rdi, rcx
0x1800051ba  mov     r12d, r15d
0x1800051bd  mov     [rbp+57h+arg_10], r15d
0x1800051c1  cmp     [rdx+70h], r15
0x1800051c5  jnz     short loc_1800051E5
0x1800051c7  mov     eax, r12d
0x1800051ca  mov     rbx, [rsp+0F0h+arg_0]
0x1800051d2  add     rsp, 0C0h
0x1800051d9  pop     r15
0x1800051db  pop     r14
0x1800051dd  pop     r13
0x1800051df  pop     r12
0x1800051e1  pop     rdi
0x1800051e2  pop     rsi
0x1800051e3  pop     rbp
0x1800051e4  retn
0x1800051e5  cmp     [rdx+50h], r15
0x1800051e9  jnz     short loc_1800051C7
0x1800051eb  test    dword ptr [rdx+4], 100000h
0x1800051f2  jnz     short loc_1800051C7
0x1800051f4  cmp     byte ptr [rcx+134h], 2
0x1800051fb  jnb     short loc_1800051C7
0x1800051fd  call    sqlite3GetVdbe
0x180005202  mov     r13, [rdi]
0x180005205  xorps   xmm0, xmm0
0x180005208  mov     rsi, [rbx+70h]
0x18000520c  mov     edx, 68h ; 'h'
0x180005211  mov     [rbp+57h+var_58], rax
0x180005215  mov     rcx, r13
0x180005218  mov     rax, [rbx+28h]
0x18000521c  mov     [rbp+57h+var_90], rax
0x180005220  mov     rax, [rbx+30h]
0x180005224  mov     [rbp+57h+var_38], rax
0x180005228  mov     rax, [rbx+38h]
0x18000522c  mov     [rbp+57h+var_40], rax
0x180005230  mov     rax, [rbx+40h]
0x180005234  mov     [rbp+57h+var_48], rax
0x180005238  mov     eax, [rbx+4]
0x18000523b  mov     [rbp+57h+arg_18], eax
0x18000523e  mov     [rbp+57h+var_A0], r15
0x180005242  mov     [rbp+57h+var_98], rsi
0x180005246  movups  [rbp+57h+var_88], xmm0
0x18000524a  movups  [rbp+57h+var_78], xmm0
0x18000524e  movups  [rbp+57h+var_68], xmm0
0x180005252  call    sqlite3DbMallocZero
0x180005257  mov     r14, rax
0x18000525a  test    rax, rax
0x18000525d  jnz     short loc_18000526F
0x18000525f  lea     edx, [rax+7]
0x180005262  mov     rcx, r13
0x180005265  call    sqlite3ErrorToParser
0x18000526a  jmp     loc_1800051CA
0x18000526f  lea     rax, agginfoPersistExprCb
0x180005276  mov     qword ptr [rbp+57h+var_78+8], r15
0x18000527a  mov     qword ptr [rbp+57h+var_88+8], rax
0x18000527e  lea     rcx, [rbp+57h+var_88]
0x180005282  lea     rax, __scrt_stub_for_is_c_termination_complete
0x180005289  mov     qword ptr [rbp+57h+var_88], rdi
0x18000528d  xorps   xmm0, xmm0
0x180005290  mov     qword ptr [rbp+57h+var_78], rax
0x180005294  mov     rdx, rbx
0x180005297  movdqu  [rbp+57h+var_68], xmm0
0x18000529c  call    sqlite3WalkSelect
0x1800052a1  test    byte ptr [rbx+4], 8
0x1800052a5  jnz     short loc_1800052C3
0x1800052a7  mov     rdx, [rbx+48h]
0x1800052ab  lea     rax, disallowAggregatesInOrderByCb
0x1800052b2  lea     rcx, [rbp+57h+var_88]
0x1800052b6  mov     qword ptr [rbp+57h+var_88+8], rax
0x1800052ba  mov     qword ptr [rbp+57h+var_78], r15
0x1800052be  call    sqlite3WalkExprList
0x1800052c3  and     dword ptr [rbx+4], 0FFFFFFF7h
0x1800052c7  xor     edx, edx
0x1800052c9  bts     dword ptr [rbx+4], 14h
0x1800052ce  mov     rcx, rdi
0x1800052d1  mov     [rbx+28h], r15
0x1800052d5  mov     [rbx+30h], r15
0x1800052d9  mov     [rbx+38h], r15
0x1800052dd  mov     [rbx+40h], r15
0x1800052e1  mov     r15d, 1
0x1800052e7  mov     r8, [rsi+10h]
0x1800052eb  mov     r9d, r15d
0x1800052ee  call    exprListAppendList
0x1800052f3  mov     r8, [rsi+18h]
0x1800052f7  mov     r9d, r15d
0x1800052fa  mov     rdx, rax
0x1800052fd  mov     rcx, rdi
0x180005300  call    exprListAppendList
0x180005305  mov     [rbp+57h+var_50], rax
0x180005309  mov     r15, rax
0x18000530c  test    rax, rax
0x18000530f  jz      short loc_18000534F
0x180005311  mov     rcx, [rbx+48h]
0x180005315  test    rcx, rcx
0x180005318  jz      short loc_18000534F
0x18000531a  mov     esi, [rax]
0x18000531c  mov     edx, [rcx]
0x18000531e  cmp     edx, esi
0x180005320  jg      short loc_18000534B
0x180005322  mov     [rax], edx
0x180005324  or      r8d, 0FFFFFFFFh
0x180005328  mov     rdx, [rbx+48h]
0x18000532c  mov     rcx, rax
0x18000532f  call    sqlite3ExprListCompare
0x180005334  test    eax, eax
0x180005336  jnz     short loc_180005348
0x180005338  mov     rdx, [rbx+48h]
0x18000533c  mov     rcx, r13
0x18000533f  call    sqlite3ExprListDeleteGeneric
0x180005344  mov     [rbx+48h], r12
0x180005348  mov     [r15], esi
0x18000534b  mov     rsi, [rbp+57h+var_98]
0x18000534f  mov     eax, [rdi+34h]
0x180005352  mov     rdx, rsi
0x180005355  mov     r8, [rbp+57h+var_90]
0x180005359  mov     rcx, rdi
0x18000535c  mov     [rsi+58h], eax
0x18000535f  lea     rax, [rbp+57h+var_A0]
0x180005363  add     dword ptr [rdi+34h], 4
0x180005367  mov     r9, [rbx+20h]
0x18000536b  mov     [rsp+0F0h+var_C8], rax
0x180005370  mov     [rsp+0F0h+var_D0], r14
0x180005375  call    selectWindowRewriteEList
0x18000537a  mov     r9, [rbx+48h]
0x18000537e  lea     rax, [rbp+57h+var_A0]
0x180005382  mov     r8, [rbp+57h+var_90]
0x180005386  mov     rdx, rsi
0x180005389  mov     [rsp+0F0h+var_C8], rax
0x18000538e  mov     rcx, rdi
0x180005391  mov     [rsp+0F0h+var_D0], r14
0x180005396  call    selectWindowRewriteEList
0x18000539b  mov     rdx, [rbp+57h+var_A0]
0x18000539f  test    rdx, rdx
0x1800053a2  jz      short loc_1800053A8
0x1800053a4  mov     eax, [rdx]
0x1800053a6  jmp     short loc_1800053AA
0x1800053a8  xor     eax, eax
0x1800053aa  mov     r8, [rsi+10h]
0x1800053ae  xor     r9d, r9d
0x1800053b1  mov     rcx, rdi
0x1800053b4  mov     [rsi+78h], eax
0x1800053b7  call    exprListAppendList
0x1800053bc  mov     r8, [rsi+18h]
0x1800053c0  xor     r9d, r9d
0x1800053c3  mov     rdx, rax
0x1800053c6  mov     rcx, rdi
0x1800053c9  call    exprListAppendList
0x1800053ce  mov     r12, [rbp+57h+var_98]
0x1800053d2  mov     rsi, rax
0x1800053d5  mov     rbx, [rbp+57h+var_90]
0x1800053d9  mov     r15, r12
0x1800053dc  mov     [rbp+57h+var_A0], rax
0x1800053e0  mov     rax, [r15+70h]
0x1800053e4  mov     r8, [rax+20h]
0x1800053e8  mov     rax, [r15+50h]
0x1800053ec  test    dword ptr [rax+4], 100000h
0x1800053f3  jz      short loc_180005431
0x1800053f5  lea     rax, [rbp+57h+var_A0]
0x1800053f9  mov     r9, r8
0x1800053fc  mov     [rsp+0F0h+var_C8], rax
0x180005401  mov     r8, rbx
0x180005404  mov     rdx, r12
0x180005407  mov     [rsp+0F0h+var_D0], r14
0x18000540c  mov     rcx, rdi
0x18000540f  call    selectWindowRewriteEList
0x180005414  mov     rsi, [rbp+57h+var_A0]
0x180005418  test    rsi, rsi
0x18000541b  jz      short loc_180005421
0x18000541d  mov     eax, [rsi]
0x18000541f  jmp     short loc_180005423
0x180005421  xor     eax, eax
0x180005423  mov     [r15+7Ch], eax
0x180005427  mov     byte ptr [r15+8Ch], 1
0x18000542f  jmp     short loc_180005455
0x180005431  test    rsi, rsi
0x180005434  jz      short loc_18000543A
0x180005436  mov     eax, [rsi]
0x180005438  jmp     short loc_18000543C
0x18000543a  xor     eax, eax
0x18000543c  xor     r9d, r9d
0x18000543f  mov     [r15+7Ch], eax
0x180005443  mov     rdx, rsi
0x180005446  mov     rcx, rdi
0x180005449  call    exprListAppendList
0x18000544e  mov     rsi, rax
0x180005451  mov     [rbp+57h+var_A0], rax
0x180005455  mov     rdx, [r15+48h]
0x180005459  test    rdx, rdx
0x18000545c  jz      short loc_18000547E
0x18000545e  xor     r8d, r8d
0x180005461  mov     rcx, r13
0x180005464  call    sqlite3ExprDup
0x180005469  mov     r8, rax
0x18000546c  mov     rdx, rsi
0x18000546f  mov     rcx, rdi
0x180005472  call    sqlite3ExprListAppend
0x180005477  mov     rsi, rax
0x18000547a  mov     [rbp+57h+var_A0], rax
0x18000547e  mov     eax, [rdi+38h]
0x180005481  xor     r8d, r8d
0x180005484  mov     rcx, [rbp+57h+var_58]
0x180005488  inc     eax
0x18000548a  mov     [rdi+38h], eax
0x18000548d  mov     [r15+5Ch], eax
0x180005491  mov     eax, [rdi+38h]
0x180005494  lea     edx, [r8+4Bh]
0x180005498  inc     eax
0x18000549a  mov     dword ptr [rsp+0F0h+var_D0], 0
0x1800054a2  mov     [rdi+38h], eax
0x1800054a5  mov     r9d, [r15+5Ch]
0x1800054a9  mov     [r15+60h], eax
0x1800054ad  call    sqlite3VdbeAddOp3
0x1800054b2  mov     r15, [r15+40h]
0x1800054b6  test    r15, r15
0x1800054b9  jnz     loc_1800053E0
0x1800054bf  mov     rbx, [rbp+57h+arg_8]
0x1800054c3  mov     r12d, [rbp+57h+arg_10]
0x1800054c7  test    rsi, rsi
0x1800054ca  jnz     short loc_1800054F0
0x1800054cc  lea     r8, a0; "0"
0x1800054d3  mov     edx, 9Bh
0x1800054d8  mov     rcx, r13
0x1800054db  call    sqlite3Expr
0x1800054e0  mov     r8, rax
0x1800054e3  xor     edx, edx
0x1800054e5  mov     rcx, rdi
0x1800054e8  call    sqlite3ExprListAppend
0x1800054ed  mov     rsi, rax
0x1800054f0  mov     rax, [rbp+57h+var_50]
0x1800054f4  mov     rdx, rsi
0x1800054f7  mov     r9, [rbp+57h+var_38]
0x1800054fb  mov     rcx, rdi
0x1800054fe  mov     r8, [rbp+57h+var_90]
0x180005502  mov     [rsp+0F0h+var_B0], r12
0x180005507  mov     [rsp+0F0h+var_B8], r12d
0x18000550c  mov     [rsp+0F0h+var_C0], rax
0x180005511  mov     rax, [rbp+57h+var_48]
0x180005515  mov     [rsp+0F0h+var_C8], rax
0x18000551a  mov     rax, [rbp+57h+var_40]
0x18000551e  mov     [rsp+0F0h+var_D0], rax
0x180005523  call    sqlite3SelectNew
0x180005528  xor     r9d, r9d
0x18000552b  xor     r8d, r8d
0x18000552e  xor     edx, edx
0x180005530  mov     rcx, rdi
0x180005533  mov     rsi, rax
0x180005536  call    sqlite3SrcListAppend
0x18000553b  mov     [rbx+28h], rax
0x18000553f  mov     r15d, 7
0x180005545  test    rax, rax
0x180005548  jz      loc_18000561F
0x18000554e  mov     [rax+30h], rsi
0x180005552  mov     rcx, rdi
0x180005555  mov     rax, [rbx+28h]
0x180005559  or      dword ptr [rax+48h], 8
0x18000555d  mov     rdx, [rbx+28h]
0x180005561  call    sqlite3SrcListAssignCursors
0x180005566  or      dword ptr [rsi+4], 8000040h
0x18000556d  mov     rdx, rsi
0x180005570  mov     rcx, rdi
0x180005573  mov     r8b, 40h ; '@'
0x180005576  call    sqlite3ResultSetOfSelect
0x18000557b  mov     rcx, rax
0x18000557e  mov     eax, [rbp+57h+arg_18]
0x180005581  and     eax, 8
0x180005584  or      [rsi+4], eax
0x180005587  test    rcx, rcx
0x18000558a  jnz     short loc_180005594
0x18000558c  mov     r12d, r15d
0x18000558f  jmp     loc_18000562A
0x180005594  movups  xmm0, xmmword ptr [rcx]
0x180005597  mov     rdx, rsi
0x18000559a  movups  xmmword ptr [r14], xmm0
0x18000559e  movups  xmm1, xmmword ptr [rcx+10h]
0x1800055a2  movups  xmmword ptr [r14+10h], xmm1
0x1800055a7  movups  xmm0, xmmword ptr [rcx+20h]
0x1800055ab  movups  xmmword ptr [r14+20h], xmm0
0x1800055b0  movups  xmm1, xmmword ptr [rcx+30h]
0x1800055b4  movups  xmmword ptr [r14+30h], xmm1
0x1800055b9  movups  xmm0, xmmword ptr [rcx+40h]
0x1800055bd  movups  xmmword ptr [r14+40h], xmm0
0x1800055c2  movups  xmm1, xmmword ptr [rcx+50h]
0x1800055c6  movups  xmmword ptr [r14+50h], xmm1
0x1800055cb  movsd   xmm0, qword ptr [rcx+60h]
0x1800055d0  movsd   qword ptr [r14+60h], xmm0
0x1800055d6  xorps   xmm0, xmm0
0x1800055d9  bts     dword ptr [r14+30h], 0Eh
  ... truncated ...
```
