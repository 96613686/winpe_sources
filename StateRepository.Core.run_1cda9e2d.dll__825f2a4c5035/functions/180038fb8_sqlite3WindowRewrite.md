# sqlite3WindowRewrite

- ea: `0x180038fb8`
- end: `0x180039487`
- name: `sqlite3WindowRewrite`
- size: `1231`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180037194`

## callees

- `0x1800055cc`
- `0x18000c850`
- `0x18000c930`
- `0x18000e5c0`
- `0x18000e790`
- `0x18000f720`
- `0x18000f820`
- `0x18000fe40`
- `0x180010810`
- `0x1800119e0`
- `0x180016748`
- `0x18003465c`
- `0x180038fb8`
- `0x180039490`
- `0x18003e1e0`
- `0x18004c6b0`
- `0x180060c3c`
- `0x180063a58`
- `0x1800680fc`
- `0x18006e7ec`
- `0x18007f694`

## pseudocode

```c
__int64 __fastcall sqlite3WindowRewrite(__int64 a1, __int64 a2)
{
  unsigned int v4; // r12d
  __int64 Vdbe; // rax
  __int64 v7; // r13
  __int64 v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rdx
  __int64 appended; // rax
  _DWORD *v12; // rax
  _DWORD *v13; // r15
  _DWORD *v14; // rcx
  int v15; // esi
  int v16; // r8d
  _DWORD *v17; // rdx
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // r12d
  _DWORD *v23; // rsi
  int v24; // ebx
  __int64 v25; // r15
  __int64 v26; // r8
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // ecx
  int v32; // eax
  int v33; // eax
  int v34; // r9d
  __int64 v35; // rax
  __int64 v36; // rsi
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // rcx
  _DWORD *v40; // [rsp+50h] [rbp-49h] BYREF
  __int64 v41; // [rsp+58h] [rbp-41h]
  __int64 v42; // [rsp+60h] [rbp-39h]
  __int128 v43; // [rsp+68h] [rbp-31h] BYREF
  __int128 v44; // [rsp+78h] [rbp-21h]
  __int128 v45; // [rsp+88h] [rbp-11h]
  __int64 v46; // [rsp+98h] [rbp-1h]
  _DWORD *v47; // [rsp+A0h] [rbp+7h]
  __int64 v48; // [rsp+A8h] [rbp+Fh]
  __int64 v49; // [rsp+B0h] [rbp+17h]
  __int64 v50; // [rsp+B8h] [rbp+1Fh]
  int v52; // [rsp+118h] [rbp+7Fh]

  v4 = 0;
  if ( !*(_QWORD *)(a2 + 112)
    || *(_QWORD *)(a2 + 80)
    || (*(_DWORD *)(a2 + 4) & 0x100000) != 0
    || *(_BYTE *)(a1 + 308) >= 2u )
  {
    return v4;
  }
  Vdbe = sqlite3GetVdbe(a1);
  v7 = *(_QWORD *)a1;
  v8 = *(_QWORD *)(a2 + 112);
  v46 = Vdbe;
  v42 = *(_QWORD *)(a2 + 40);
  v50 = *(_QWORD *)(a2 + 48);
  v49 = *(_QWORD *)(a2 + 56);
  v48 = *(_QWORD *)(a2 + 64);
  v52 = *(_DWORD *)(a2 + 4);
  v40 = 0;
  v41 = v8;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v9 = sqlite3DbMallocZero(v7, 104);
  if ( v9 )
  {
    *((_QWORD *)&v44 + 1) = 0;
    *((_QWORD *)&v43 + 1) = agginfoPersistExprCb;
    *(_QWORD *)&v43 = a1;
    *(_QWORD *)&v44 = _scrt_stub_for_is_c_termination_complete;
    v45 = 0;
    sqlite3WalkSelect(&v43, a2);
    if ( (*(_BYTE *)(a2 + 4) & 8) == 0 )
    {
      v10 = *(_QWORD *)(a2 + 72);
      *((_QWORD *)&v43 + 1) = disallowAggregatesInOrderByCb;
      *(_QWORD *)&v44 = 0;
      sqlite3WalkExprList(&v43, v10);
    }
    *(_DWORD *)(a2 + 4) &= ~8u;
    *(_DWORD *)(a2 + 4) |= 0x100000u;
    *(_QWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    appended = exprListAppendList(a1, 0, *(_QWORD *)(v8 + 16), 1);
    v12 = (_DWORD *)exprListAppendList(a1, appended, *(_QWORD *)(v8 + 24), 1);
    v47 = v12;
    v13 = v12;
    if ( v12 )
    {
      v14 = *(_DWORD **)(a2 + 72);
      if ( v14 )
      {
        v15 = *v12;
        if ( *v14 <= *v12 )
        {
          *v12 = *v14;
          if ( !(unsigned int)sqlite3ExprListCompare(v12, *(_QWORD *)(a2 + 72), 0xFFFFFFFFLL) )
          {
            sqlite3ExprListDeleteGeneric(v7, *(_QWORD *)(a2 + 72));
            *(_QWORD *)(a2 + 72) = 0;
          }
          *v13 = v15;
        }
        v8 = v41;
      }
    }
    v16 = v42;
    *(_DWORD *)(v8 + 88) = *(_DWORD *)(a1 + 56);
    *(_DWORD *)(a1 + 56) += 4;
    selectWindowRewriteEList(a1, v8, v16, *(_QWORD *)(a2 + 32), v9, (__int64)&v40);
    selectWindowRewriteEList(a1, v8, v42, *(_QWORD *)(a2 + 72), v9, (__int64)&v40);
    v17 = v40;
    if ( v40 )
      v18 = *v40;
    else
      v18 = 0;
    v19 = *(_QWORD *)(v8 + 16);
    *(_DWORD *)(v8 + 120) = v18;
    v20 = exprListAppendList(a1, v17, v19, 0);
    v21 = exprListAppendList(a1, v20, *(_QWORD *)(v8 + 24), 0);
    v22 = v41;
    v23 = (_DWORD *)v21;
    v24 = v42;
    v25 = v41;
    v40 = (_DWORD *)v21;
    do
    {
      v26 = *(_QWORD *)(*(_QWORD *)(v25 + 112) + 32LL);
      if ( (*(_DWORD *)(*(_QWORD *)(v25 + 80) + 4LL) & 0x100000) != 0 )
      {
        selectWindowRewriteEList(a1, v22, v24, *(_QWORD *)(*(_QWORD *)(v25 + 112) + 32LL), v9, (__int64)&v40);
        v23 = v40;
        if ( v40 )
          v27 = *v40;
        else
          v27 = 0;
        *(_DWORD *)(v25 + 124) = v27;
        *(_BYTE *)(v25 + 140) = 1;
      }
      else
      {
        if ( v23 )
          v28 = *v23;
        else
          v28 = 0;
        *(_DWORD *)(v25 + 124) = v28;
        v23 = (_DWORD *)exprListAppendList(a1, v23, v26, 0);
        v40 = v23;
      }
      v29 = *(_QWORD *)(v25 + 72);
      if ( v29 )
      {
        v30 = sqlite3ExprDup(v7, v29, 0);
        v23 = (_DWORD *)sqlite3ExprListAppend(a1, v23, v30);
        v40 = v23;
      }
      v31 = v46;
      v32 = *(_DWORD *)(a1 + 60) + 1;
      *(_DWORD *)(a1 + 60) = v32;
      *(_DWORD *)(v25 + 92) = v32;
      v33 = *(_DWORD *)(a1 + 60) + 1;
      *(_DWORD *)(a1 + 60) = v33;
      v34 = *(_DWORD *)(v25 + 92);
      *(_DWORD *)(v25 + 96) = v33;
      sqlite3VdbeAddOp3(v31, 75, 0, v34, 0);
      v25 = *(_QWORD *)(v25 + 64);
    }
    while ( v25 );
    v4 = 0;
    if ( !v23 )
    {
      v35 = sqlite3Expr(v7, 156, "0");
      LODWORD(v23) = sqlite3ExprListAppend(a1, 0, v35);
    }
    v36 = sqlite3SelectNew(a1, (_DWORD)v23, v42, v50, v49, v48, (__int64)v47, 0, 0);
    v37 = sqlite3SrcListAppend(a1, 0, 0, 0);
    *(_QWORD *)(a2 + 40) = v37;
    if ( v37 )
    {
      if ( (unsigned int)sqlite3SrcItemAttachSubquery(a1, v37 + 8, v36, 0) )
      {
        *(_DWORD *)(*(_QWORD *)(a2 + 40) + 36LL) |= 0x10u;
        sqlite3SrcListAssignCursors(a1, *(_QWORD *)(a2 + 40));
        *(_DWORD *)(v36 + 4) |= 0x8000040u;
        LOBYTE(v38) = 64;
        v39 = sqlite3ResultSetOfSelect(a1, v36, v38);
        *(_DWORD *)(v36 + 4) |= v52 & 8;
        if ( v39 )
        {
          *(_OWORD *)v9 = *(_OWORD *)v39;
          *(_OWORD *)(v9 + 16) = *(_OWORD *)(v39 + 16);
          *(_OWORD *)(v9 + 32) = *(_OWORD *)(v39 + 32);
          *(_OWORD *)(v9 + 48) = *(_OWORD *)(v39 + 48);
          *(_OWORD *)(v9 + 64) = *(_OWORD *)(v39 + 64);
          *(_OWORD *)(v9 + 80) = *(_OWORD *)(v39 + 80);
          *(_QWORD *)(v9 + 96) = *(_QWORD *)(v39 + 96);
          *(_DWORD *)(v9 + 48) |= 0x4000u;
          *(_QWORD *)(*(_QWORD *)(a2 + 40) + 24LL) = v9;
          *((_QWORD *)&v43 + 1) = sqlite3WindowExtraAggFuncDepth;
          v9 = v39;
          *(_QWORD *)&v43 = 0;
          *(_QWORD *)&v44 = sqlite3WalkerDepthIncrease;
          *((_QWORD *)&v44 + 1) = sqlite3WalkerDepthDecrease;
          v45 = 0;
          sqlite3WalkSelect(&v43, v36);
        }
        else
        {
          v4 = 7;
        }
      }
    }
    else
    {
      sqlite3SelectDelete(v7, v36);
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
0x180038fb8  mov     [rsp-8+arg_0], rbx
0x180038fbd  mov     [rsp-8+arg_8], rdx
0x180038fc2  push    rbp
0x180038fc3  push    rsi
0x180038fc4  push    rdi
0x180038fc5  push    r12
0x180038fc7  push    r13
0x180038fc9  push    r14
0x180038fcb  push    r15
0x180038fcd  lea     rbp, [rsp-27h]
0x180038fd2  sub     rsp, 0C0h
0x180038fd9  xor     r15d, r15d
0x180038fdc  mov     rbx, rdx
0x180038fdf  mov     rdi, rcx
0x180038fe2  mov     r12d, r15d
0x180038fe5  mov     [rbp+57h+arg_10], r15d
0x180038fe9  cmp     [rdx+70h], r15
0x180038fed  jnz     short loc_18003900D
0x180038fef  mov     eax, r12d
0x180038ff2  mov     rbx, [rsp+0F0h+arg_0]
0x180038ffa  add     rsp, 0C0h
0x180039001  pop     r15
0x180039003  pop     r14
0x180039005  pop     r13
0x180039007  pop     r12
0x180039009  pop     rdi
0x18003900a  pop     rsi
0x18003900b  pop     rbp
0x18003900c  retn
0x18003900d  cmp     [rdx+50h], r15
0x180039011  jnz     short loc_180038FEF
0x180039013  test    dword ptr [rdx+4], 100000h
0x18003901a  jnz     short loc_180038FEF
0x18003901c  cmp     byte ptr [rcx+134h], 2
0x180039023  jnb     short loc_180038FEF
0x180039025  call    sqlite3GetVdbe
0x18003902a  mov     r13, [rdi]
0x18003902d  xorps   xmm0, xmm0
0x180039030  mov     rsi, [rbx+70h]
0x180039034  mov     edx, 68h ; 'h'
0x180039039  mov     [rbp+57h+var_58], rax
0x18003903d  mov     rcx, r13
0x180039040  mov     rax, [rbx+28h]
0x180039044  mov     [rbp+57h+var_90], rax
0x180039048  mov     rax, [rbx+30h]
0x18003904c  mov     [rbp+57h+var_38], rax
0x180039050  mov     rax, [rbx+38h]
0x180039054  mov     [rbp+57h+var_40], rax
0x180039058  mov     rax, [rbx+40h]
0x18003905c  mov     [rbp+57h+var_48], rax
0x180039060  mov     eax, [rbx+4]
0x180039063  mov     [rbp+57h+arg_18], eax
0x180039066  mov     [rbp+57h+var_A0], r15
0x18003906a  mov     [rbp+57h+var_98], rsi
0x18003906e  movups  [rbp+57h+var_88], xmm0
0x180039072  movups  [rbp+57h+var_78], xmm0
0x180039076  movups  [rbp+57h+var_68], xmm0
0x18003907a  call    sqlite3DbMallocZero
0x18003907f  mov     r14, rax
0x180039082  test    rax, rax
0x180039085  jnz     short loc_180039097
0x180039087  lea     edx, [rax+7]
0x18003908a  mov     rcx, r13
0x18003908d  call    sqlite3ErrorToParser
0x180039092  jmp     loc_180038FF2
0x180039097  lea     rax, agginfoPersistExprCb
0x18003909e  mov     qword ptr [rbp+57h+var_78+8], r15
0x1800390a2  mov     qword ptr [rbp+57h+var_88+8], rax
0x1800390a6  lea     rcx, [rbp+57h+var_88]
0x1800390aa  lea     rax, __scrt_stub_for_is_c_termination_complete
0x1800390b1  mov     qword ptr [rbp+57h+var_88], rdi
0x1800390b5  xorps   xmm0, xmm0
0x1800390b8  mov     qword ptr [rbp+57h+var_78], rax
0x1800390bc  mov     rdx, rbx
0x1800390bf  movdqu  [rbp+57h+var_68], xmm0
0x1800390c4  call    sqlite3WalkSelect
0x1800390c9  test    byte ptr [rbx+4], 8
0x1800390cd  jnz     short loc_1800390EB
0x1800390cf  mov     rdx, [rbx+48h]
0x1800390d3  lea     rax, disallowAggregatesInOrderByCb
0x1800390da  lea     rcx, [rbp+57h+var_88]
0x1800390de  mov     qword ptr [rbp+57h+var_88+8], rax
0x1800390e2  mov     qword ptr [rbp+57h+var_78], r15
0x1800390e6  call    sqlite3WalkExprList
0x1800390eb  and     dword ptr [rbx+4], 0FFFFFFF7h
0x1800390ef  xor     edx, edx
0x1800390f1  bts     dword ptr [rbx+4], 14h
0x1800390f6  mov     rcx, rdi
0x1800390f9  mov     [rbx+28h], r15
0x1800390fd  mov     [rbx+30h], r15
0x180039101  mov     [rbx+38h], r15
0x180039105  mov     [rbx+40h], r15
0x180039109  mov     r15d, 1
0x18003910f  mov     r8, [rsi+10h]
0x180039113  mov     r9d, r15d
0x180039116  call    exprListAppendList
0x18003911b  mov     r8, [rsi+18h]
0x18003911f  mov     r9d, r15d
0x180039122  mov     rdx, rax
0x180039125  mov     rcx, rdi
0x180039128  call    exprListAppendList
0x18003912d  mov     [rbp+57h+var_50], rax
0x180039131  mov     r15, rax
0x180039134  test    rax, rax
0x180039137  jz      short loc_180039177
0x180039139  mov     rcx, [rbx+48h]
0x18003913d  test    rcx, rcx
0x180039140  jz      short loc_180039177
0x180039142  mov     esi, [rax]
0x180039144  mov     edx, [rcx]
0x180039146  cmp     edx, esi
0x180039148  jg      short loc_180039173
0x18003914a  mov     [rax], edx
0x18003914c  or      r8d, 0FFFFFFFFh
0x180039150  mov     rdx, [rbx+48h]
0x180039154  mov     rcx, rax
0x180039157  call    sqlite3ExprListCompare
0x18003915c  test    eax, eax
0x18003915e  jnz     short loc_180039170
0x180039160  mov     rdx, [rbx+48h]
0x180039164  mov     rcx, r13
0x180039167  call    sqlite3ExprListDeleteGeneric
0x18003916c  mov     [rbx+48h], r12
0x180039170  mov     [r15], esi
0x180039173  mov     rsi, [rbp+57h+var_98]
0x180039177  mov     eax, [rdi+38h]
0x18003917a  mov     rdx, rsi
0x18003917d  mov     r8, [rbp+57h+var_90]
0x180039181  mov     rcx, rdi
0x180039184  mov     [rsi+58h], eax
0x180039187  lea     rax, [rbp+57h+var_A0]
0x18003918b  add     dword ptr [rdi+38h], 4
0x18003918f  mov     r9, [rbx+20h]
0x180039193  mov     [rsp+0F0h+var_C8], rax
0x180039198  mov     [rsp+0F0h+var_D0], r14
0x18003919d  call    selectWindowRewriteEList
0x1800391a2  mov     r9, [rbx+48h]
0x1800391a6  lea     rax, [rbp+57h+var_A0]
0x1800391aa  mov     r8, [rbp+57h+var_90]
0x1800391ae  mov     rdx, rsi
0x1800391b1  mov     [rsp+0F0h+var_C8], rax
0x1800391b6  mov     rcx, rdi
0x1800391b9  mov     [rsp+0F0h+var_D0], r14
0x1800391be  call    selectWindowRewriteEList
0x1800391c3  mov     rdx, [rbp+57h+var_A0]
0x1800391c7  test    rdx, rdx
0x1800391ca  jz      short loc_1800391D0
0x1800391cc  mov     eax, [rdx]
0x1800391ce  jmp     short loc_1800391D2
0x1800391d0  xor     eax, eax
0x1800391d2  mov     r8, [rsi+10h]
0x1800391d6  xor     r9d, r9d
0x1800391d9  mov     rcx, rdi
0x1800391dc  mov     [rsi+78h], eax
0x1800391df  call    exprListAppendList
0x1800391e4  mov     r8, [rsi+18h]
0x1800391e8  xor     r9d, r9d
0x1800391eb  mov     rdx, rax
0x1800391ee  mov     rcx, rdi
0x1800391f1  call    exprListAppendList
0x1800391f6  mov     r12, [rbp+57h+var_98]
0x1800391fa  mov     rsi, rax
0x1800391fd  mov     rbx, [rbp+57h+var_90]
0x180039201  mov     r15, r12
0x180039204  mov     [rbp+57h+var_A0], rax
0x180039208  mov     rax, [r15+70h]
0x18003920c  mov     r8, [rax+20h]
0x180039210  mov     rax, [r15+50h]
0x180039214  test    dword ptr [rax+4], 100000h
0x18003921b  jz      short loc_180039259
0x18003921d  lea     rax, [rbp+57h+var_A0]
0x180039221  mov     r9, r8
0x180039224  mov     [rsp+0F0h+var_C8], rax
0x180039229  mov     r8, rbx
0x18003922c  mov     rdx, r12
0x18003922f  mov     [rsp+0F0h+var_D0], r14
0x180039234  mov     rcx, rdi
0x180039237  call    selectWindowRewriteEList
0x18003923c  mov     rsi, [rbp+57h+var_A0]
0x180039240  test    rsi, rsi
0x180039243  jz      short loc_180039249
0x180039245  mov     eax, [rsi]
0x180039247  jmp     short loc_18003924B
0x180039249  xor     eax, eax
0x18003924b  mov     [r15+7Ch], eax
0x18003924f  mov     byte ptr [r15+8Ch], 1
0x180039257  jmp     short loc_18003927D
0x180039259  test    rsi, rsi
0x18003925c  jz      short loc_180039262
0x18003925e  mov     eax, [rsi]
0x180039260  jmp     short loc_180039264
0x180039262  xor     eax, eax
0x180039264  xor     r9d, r9d
0x180039267  mov     [r15+7Ch], eax
0x18003926b  mov     rdx, rsi
0x18003926e  mov     rcx, rdi
0x180039271  call    exprListAppendList
0x180039276  mov     rsi, rax
0x180039279  mov     [rbp+57h+var_A0], rax
0x18003927d  mov     rdx, [r15+48h]
0x180039281  test    rdx, rdx
0x180039284  jz      short loc_1800392A6
0x180039286  xor     r8d, r8d
0x180039289  mov     rcx, r13
0x18003928c  call    sqlite3ExprDup
0x180039291  mov     r8, rax
0x180039294  mov     rdx, rsi
0x180039297  mov     rcx, rdi
0x18003929a  call    sqlite3ExprListAppend
0x18003929f  mov     rsi, rax
0x1800392a2  mov     [rbp+57h+var_A0], rax
0x1800392a6  mov     eax, [rdi+3Ch]
0x1800392a9  xor     r8d, r8d
0x1800392ac  mov     rcx, [rbp+57h+var_58]
0x1800392b0  inc     eax
0x1800392b2  mov     [rdi+3Ch], eax
0x1800392b5  mov     [r15+5Ch], eax
0x1800392b9  mov     eax, [rdi+3Ch]
0x1800392bc  lea     edx, [r8+4Bh]
0x1800392c0  inc     eax
0x1800392c2  mov     dword ptr [rsp+0F0h+var_D0], 0
0x1800392ca  mov     [rdi+3Ch], eax
0x1800392cd  mov     r9d, [r15+5Ch]
0x1800392d1  mov     [r15+60h], eax
0x1800392d5  call    sqlite3VdbeAddOp3
0x1800392da  mov     r15, [r15+40h]
0x1800392de  test    r15, r15
0x1800392e1  jnz     loc_180039208
0x1800392e7  mov     rbx, [rbp+57h+arg_8]
0x1800392eb  mov     r12d, [rbp+57h+arg_10]
0x1800392ef  test    rsi, rsi
0x1800392f2  jnz     short loc_180039318
0x1800392f4  lea     r8, a0; "0"
0x1800392fb  mov     edx, 9Ch
0x180039300  mov     rcx, r13
0x180039303  call    sqlite3Expr
0x180039308  mov     r8, rax
0x18003930b  xor     edx, edx
0x18003930d  mov     rcx, rdi
0x180039310  call    sqlite3ExprListAppend
0x180039315  mov     rsi, rax
0x180039318  mov     rax, [rbp+57h+var_50]
0x18003931c  mov     rdx, rsi
0x18003931f  mov     r9, [rbp+57h+var_38]
0x180039323  mov     rcx, rdi
0x180039326  mov     r8, [rbp+57h+var_90]
0x18003932a  mov     [rsp+0F0h+var_B0], r12
0x18003932f  mov     [rsp+0F0h+var_B8], r12d
0x180039334  mov     [rsp+0F0h+var_C0], rax
0x180039339  mov     rax, [rbp+57h+var_48]
0x18003933d  mov     [rsp+0F0h+var_C8], rax
0x180039342  mov     rax, [rbp+57h+var_40]
0x180039346  mov     [rsp+0F0h+var_D0], rax
0x18003934b  call    sqlite3SelectNew
0x180039350  xor     r9d, r9d
0x180039353  xor     r8d, r8d
0x180039356  xor     edx, edx
0x180039358  mov     rcx, rdi
0x18003935b  mov     rsi, rax
0x18003935e  call    sqlite3SrcListAppend
0x180039363  mov     [rbx+28h], rax
0x180039367  mov     r15d, 7
0x18003936d  test    rax, rax
0x180039370  jnz     short loc_180039382
0x180039372  mov     rdx, rsi
0x180039375  mov     rcx, r13
0x180039378  call    sqlite3SelectDelete
0x18003937d  jmp     loc_180039467
0x180039382  lea     rdx, [rax+8]
0x180039386  xor     r9d, r9d
0x180039389  mov     r8, rsi
0x18003938c  mov     rcx, rdi
0x18003938f  call    sqlite3SrcItemAttachSubquery
0x180039394  test    eax, eax
0x180039396  jz      loc_180039467
0x18003939c  mov     rax, [rbx+28h]
0x1800393a0  mov     rcx, rdi
0x1800393a3  or      dword ptr [rax+24h], 10h
0x1800393a7  mov     rdx, [rbx+28h]
0x1800393ab  call    sqlite3SrcListAssignCursors
0x1800393b0  or      dword ptr [rsi+4], 8000040h
0x1800393b7  mov     rdx, rsi
0x1800393ba  mov     rcx, rdi
0x1800393bd  mov     r8b, 40h ; '@'
0x1800393c0  call    sqlite3ResultSetOfSelect
0x1800393c5  mov     rcx, rax
0x1800393c8  mov     eax, [rbp+57h+arg_18]
0x1800393cb  and     eax, 8
0x1800393ce  or      [rsi+4], eax
0x1800393d1  test    rcx, rcx
0x1800393d4  jnz     short loc_1800393DE
0x1800393d6  mov     r12d, r15d
0x1800393d9  jmp     loc_180039467
0x1800393de  movups  xmm0, xmmword ptr [rcx]
0x1800393e1  mov     rdx, rsi
0x1800393e4  movups  xmmword ptr [r14], xmm0
0x1800393e8  movups  xmm1, xmmword ptr [rcx+10h]
0x1800393ec  movups  xmmword ptr [r14+10h], xmm1
0x1800393f1  movups  xmm0, xmmword ptr [rcx+20h]
0x1800393f5  movups  xmmword ptr [r14+20h], xmm0
  ... truncated ...
```
