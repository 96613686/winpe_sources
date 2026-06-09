# sqlite3WindowRewrite

- ea: `0x180007b00`
- end: `0x180007fc4`
- name: `sqlite3WindowRewrite`
- size: `1220`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008860`

## callees

- `0x180007b00`
- `0x18000b4bc`
- `0x18001ece0`
- `0x18001ed34`
- `0x18002b8ec`
- `0x18003b8a0`
- `0x18003bcbc`
- `0x18003c328`
- `0x18003d480`
- `0x18003e5b4`
- `0x18003fb88`
- `0x1800415f0`
- `0x180042110`
- `0x180042c90`
- `0x18005e2dc`
- `0x180075d54`
- `0x18007f0e8`
- `0x180080d8c`
- `0x180088718`
- `0x180089ccc`

## pseudocode

```c
__int64 __fastcall sqlite3WindowRewrite(__int64 *a1, __int64 a2)
{
  unsigned int v4; // r12d
  __int64 Vdbe; // rax
  __int64 v6; // r13
  __int64 v7; // rsi
  __int64 v8; // r14
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
  if ( *(_QWORD *)(a2 + 112)
    && !*(_QWORD *)(a2 + 80)
    && (*(_DWORD *)(a2 + 4) & 0x100000) == 0
    && *((_BYTE *)a1 + 308) < 2u )
  {
    Vdbe = sqlite3GetVdbe(a1);
    v6 = *a1;
    v7 = *(_QWORD *)(a2 + 112);
    v46 = Vdbe;
    v42 = *(_QWORD *)(a2 + 40);
    v50 = *(_QWORD *)(a2 + 48);
    v49 = *(_QWORD *)(a2 + 56);
    v48 = *(_QWORD *)(a2 + 64);
    v52 = *(_DWORD *)(a2 + 4);
    v40 = 0;
    v41 = v7;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v8 = sqlite3DbMallocZero(v6, 104);
    if ( !v8 )
      return sqlite3ErrorToParser(v6, 7);
    *((_QWORD *)&v44 + 1) = 0;
    *((_QWORD *)&v43 + 1) = agginfoPersistExprCb;
    *(_QWORD *)&v43 = a1;
    *(_QWORD *)&v44 = ShaderCacheDiskCleanupImpl::UpdateRegistry;
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
    appended = exprListAppendList(a1, 0, *(_QWORD *)(v7 + 16), 1);
    v12 = (_DWORD *)exprListAppendList(a1, appended, *(_QWORD *)(v7 + 24), 1);
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
            sqlite3ExprListDeleteGeneric(v6, *(_QWORD *)(a2 + 72));
            *(_QWORD *)(a2 + 72) = 0;
          }
          *v13 = v15;
        }
        v7 = v41;
      }
    }
    v16 = v42;
    *(_DWORD *)(v7 + 88) = *((_DWORD *)a1 + 13);
    *((_DWORD *)a1 + 13) += 4;
    selectWindowRewriteEList((_DWORD)a1, v7, v16, *(_QWORD *)(a2 + 32), v8, (__int64)&v40);
    selectWindowRewriteEList((_DWORD)a1, v7, v42, *(_QWORD *)(a2 + 72), v8, (__int64)&v40);
    v17 = v40;
    if ( v40 )
      v18 = *v40;
    else
      v18 = 0;
    v19 = *(_QWORD *)(v7 + 16);
    *(_DWORD *)(v7 + 120) = v18;
    v20 = exprListAppendList(a1, v17, v19, 0);
    v21 = exprListAppendList(a1, v20, *(_QWORD *)(v7 + 24), 0);
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
        selectWindowRewriteEList((_DWORD)a1, v22, v24, *(_QWORD *)(*(_QWORD *)(v25 + 112) + 32LL), v8, (__int64)&v40);
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
        v30 = sqlite3ExprDup(v6, v29, 0);
        v23 = (_DWORD *)sqlite3ExprListAppend(a1, v23, v30);
        v40 = v23;
      }
      v31 = v46;
      v32 = *((_DWORD *)a1 + 14) + 1;
      *((_DWORD *)a1 + 14) = v32;
      *(_DWORD *)(v25 + 92) = v32;
      v33 = *((_DWORD *)a1 + 14) + 1;
      *((_DWORD *)a1 + 14) = v33;
      v34 = *(_DWORD *)(v25 + 92);
      *(_DWORD *)(v25 + 96) = v33;
      sqlite3VdbeAddOp3(v31, 75, 0, v34, 0);
      v25 = *(_QWORD *)(v25 + 64);
    }
    while ( v25 );
    v4 = 0;
    if ( !v23 )
    {
      v35 = sqlite3Expr(v6, 155, "0");
      LODWORD(v23) = sqlite3ExprListAppend(a1, 0, v35);
    }
    v36 = sqlite3SelectNew((_DWORD)a1, (_DWORD)v23, v42, v50, v49, v48, (__int64)v47, 0, 0);
    v37 = sqlite3SrcListAppend(a1, 0, 0, 0);
    *(_QWORD *)(a2 + 40) = v37;
    if ( v37 )
    {
      *(_QWORD *)(v37 + 48) = v36;
      *(_DWORD *)(*(_QWORD *)(a2 + 40) + 72LL) |= 8u;
      sqlite3SrcListAssignCursors(a1, *(_QWORD *)(a2 + 40));
      *(_DWORD *)(v36 + 4) |= 0x8000040u;
      LOBYTE(v38) = 64;
      v39 = sqlite3ResultSetOfSelect(a1, v36, v38);
      *(_DWORD *)(v36 + 4) |= v52 & 8;
      if ( v39 )
      {
        *(_OWORD *)v8 = *(_OWORD *)v39;
        *(_OWORD *)(v8 + 16) = *(_OWORD *)(v39 + 16);
        *(_OWORD *)(v8 + 32) = *(_OWORD *)(v39 + 32);
        *(_OWORD *)(v8 + 48) = *(_OWORD *)(v39 + 48);
        *(_OWORD *)(v8 + 64) = *(_OWORD *)(v39 + 64);
        *(_OWORD *)(v8 + 80) = *(_OWORD *)(v39 + 80);
        *(_QWORD *)(v8 + 96) = *(_QWORD *)(v39 + 96);
        *(_DWORD *)(v8 + 48) |= 0x4000u;
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 40LL) = v8;
        *((_QWORD *)&v43 + 1) = sqlite3WindowExtraAggFuncDepth;
        v8 = v39;
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
    else
    {
      sqlite3SelectDeleteGeneric(v6, v36);
    }
    if ( *(_BYTE *)(v6 + 103) )
      v4 = 7;
    sqlite3ParserAddCleanup(a1, sqlite3DbFree, v8);
  }
  return v4;
}

```

## disassembly

```asm
0x180007b00  mov     [rsp-8+arg_0], rbx
0x180007b05  mov     [rsp-8+arg_8], rdx
0x180007b0a  push    rbp
0x180007b0b  push    rsi
0x180007b0c  push    rdi
0x180007b0d  push    r12
0x180007b0f  push    r13
0x180007b11  push    r14
0x180007b13  push    r15
0x180007b15  lea     rbp, [rsp-27h]
0x180007b1a  sub     rsp, 0C0h
0x180007b21  xor     r15d, r15d
0x180007b24  mov     rbx, rdx
0x180007b27  mov     rdi, rcx
0x180007b2a  mov     r12d, r15d
0x180007b2d  mov     [rbp+57h+arg_10], r15d
0x180007b31  cmp     [rdx+70h], r15
0x180007b35  jz      loc_180007FA6
0x180007b3b  cmp     [rdx+50h], r15
0x180007b3f  jnz     loc_180007FA6
0x180007b45  test    dword ptr [rdx+4], 100000h
0x180007b4c  jnz     loc_180007FA6
0x180007b52  cmp     byte ptr [rcx+134h], 2
0x180007b59  jnb     loc_180007FA6
0x180007b5f  call    sqlite3GetVdbe
0x180007b64  mov     r13, [rdi]
0x180007b67  lea     edx, [r15+68h]
0x180007b6b  mov     rsi, [rbx+70h]
0x180007b6f  xorps   xmm0, xmm0
0x180007b72  mov     [rbp+57h+var_58], rax
0x180007b76  mov     rcx, r13
0x180007b79  mov     rax, [rbx+28h]
0x180007b7d  mov     [rbp+57h+var_90], rax
0x180007b81  mov     rax, [rbx+30h]
0x180007b85  mov     [rbp+57h+var_38], rax
0x180007b89  mov     rax, [rbx+38h]
0x180007b8d  mov     [rbp+57h+var_40], rax
0x180007b91  mov     rax, [rbx+40h]
0x180007b95  mov     [rbp+57h+var_48], rax
0x180007b99  mov     eax, [rbx+4]
0x180007b9c  mov     [rbp+57h+arg_18], eax
0x180007b9f  mov     [rbp+57h+var_A0], r15
0x180007ba3  mov     [rbp+57h+var_98], rsi
0x180007ba7  movups  [rbp+57h+var_88], xmm0
0x180007bab  movups  [rbp+57h+var_78], xmm0
0x180007baf  movups  [rbp+57h+var_68], xmm0
0x180007bb3  call    sqlite3DbMallocZero
0x180007bb8  mov     r14, rax
0x180007bbb  test    rax, rax
0x180007bbe  jnz     short loc_180007BD0
0x180007bc0  lea     edx, [rax+7]
0x180007bc3  mov     rcx, r13
0x180007bc6  call    sqlite3ErrorToParser
0x180007bcb  jmp     loc_180007FA9
0x180007bd0  lea     rax, agginfoPersistExprCb
0x180007bd7  mov     qword ptr [rbp+57h+var_78+8], r15
0x180007bdb  mov     qword ptr [rbp+57h+var_88+8], rax
0x180007bdf  lea     rcx, [rbp+57h+var_88]
0x180007be3  lea     rax, ?UpdateRegistry@ShaderCacheDiskCleanupImpl@@SAJH@Z; ShaderCacheDiskCleanupImpl::UpdateRegistry(int)
0x180007bea  mov     qword ptr [rbp+57h+var_88], rdi
0x180007bee  xorps   xmm0, xmm0
0x180007bf1  mov     qword ptr [rbp+57h+var_78], rax
0x180007bf5  mov     rdx, rbx
0x180007bf8  movdqu  [rbp+57h+var_68], xmm0
0x180007bfd  call    sqlite3WalkSelect
0x180007c02  test    byte ptr [rbx+4], 8
0x180007c06  jnz     short loc_180007C24
0x180007c08  mov     rdx, [rbx+48h]
0x180007c0c  lea     rax, disallowAggregatesInOrderByCb
0x180007c13  lea     rcx, [rbp+57h+var_88]
0x180007c17  mov     qword ptr [rbp+57h+var_88+8], rax
0x180007c1b  mov     qword ptr [rbp+57h+var_78], r15
0x180007c1f  call    sqlite3WalkExprList
0x180007c24  and     dword ptr [rbx+4], 0FFFFFFF7h
0x180007c28  xor     edx, edx
0x180007c2a  bts     dword ptr [rbx+4], 14h
0x180007c2f  mov     rcx, rdi
0x180007c32  mov     [rbx+28h], r15
0x180007c36  mov     [rbx+30h], r15
0x180007c3a  mov     [rbx+38h], r15
0x180007c3e  mov     [rbx+40h], r15
0x180007c42  mov     r15d, 1
0x180007c48  mov     r8, [rsi+10h]
0x180007c4c  mov     r9d, r15d
0x180007c4f  call    exprListAppendList
0x180007c54  mov     r8, [rsi+18h]
0x180007c58  mov     r9d, r15d
0x180007c5b  mov     rdx, rax
0x180007c5e  mov     rcx, rdi
0x180007c61  call    exprListAppendList
0x180007c66  mov     [rbp+57h+var_50], rax
0x180007c6a  mov     r15, rax
0x180007c6d  test    rax, rax
0x180007c70  jz      short loc_180007CB0
0x180007c72  mov     rcx, [rbx+48h]
0x180007c76  test    rcx, rcx
0x180007c79  jz      short loc_180007CB0
0x180007c7b  mov     esi, [rax]
0x180007c7d  mov     edx, [rcx]
0x180007c7f  cmp     edx, esi
0x180007c81  jg      short loc_180007CAC
0x180007c83  mov     [rax], edx
0x180007c85  or      r8d, 0FFFFFFFFh
0x180007c89  mov     rdx, [rbx+48h]
0x180007c8d  mov     rcx, rax
0x180007c90  call    sqlite3ExprListCompare
0x180007c95  test    eax, eax
0x180007c97  jnz     short loc_180007CA9
0x180007c99  mov     rdx, [rbx+48h]
0x180007c9d  mov     rcx, r13
0x180007ca0  call    sqlite3ExprListDeleteGeneric
0x180007ca5  mov     [rbx+48h], r12
0x180007ca9  mov     [r15], esi
0x180007cac  mov     rsi, [rbp+57h+var_98]
0x180007cb0  mov     eax, [rdi+34h]
0x180007cb3  mov     rdx, rsi
0x180007cb6  mov     r8, [rbp+57h+var_90]
0x180007cba  mov     rcx, rdi
0x180007cbd  mov     [rsi+58h], eax
0x180007cc0  lea     rax, [rbp+57h+var_A0]
0x180007cc4  add     dword ptr [rdi+34h], 4
0x180007cc8  mov     r9, [rbx+20h]
0x180007ccc  mov     [rsp+0F0h+var_C8], rax
0x180007cd1  mov     [rsp+0F0h+var_D0], r14
0x180007cd6  call    selectWindowRewriteEList
0x180007cdb  mov     r9, [rbx+48h]
0x180007cdf  lea     rax, [rbp+57h+var_A0]
0x180007ce3  mov     r8, [rbp+57h+var_90]
0x180007ce7  mov     rdx, rsi
0x180007cea  mov     [rsp+0F0h+var_C8], rax
0x180007cef  mov     rcx, rdi
0x180007cf2  mov     [rsp+0F0h+var_D0], r14
0x180007cf7  call    selectWindowRewriteEList
0x180007cfc  mov     rdx, [rbp+57h+var_A0]
0x180007d00  test    rdx, rdx
0x180007d03  jz      short loc_180007D09
0x180007d05  mov     eax, [rdx]
0x180007d07  jmp     short loc_180007D0B
0x180007d09  xor     eax, eax
0x180007d0b  mov     r8, [rsi+10h]
0x180007d0f  xor     r9d, r9d
0x180007d12  mov     rcx, rdi
0x180007d15  mov     [rsi+78h], eax
0x180007d18  call    exprListAppendList
0x180007d1d  mov     r8, [rsi+18h]
0x180007d21  xor     r9d, r9d
0x180007d24  mov     rdx, rax
0x180007d27  mov     rcx, rdi
0x180007d2a  call    exprListAppendList
0x180007d2f  mov     r12, [rbp+57h+var_98]
0x180007d33  mov     rsi, rax
0x180007d36  mov     rbx, [rbp+57h+var_90]
0x180007d3a  mov     r15, r12
0x180007d3d  mov     [rbp+57h+var_A0], rax
0x180007d41  mov     rax, [r15+70h]
0x180007d45  mov     r8, [rax+20h]
0x180007d49  mov     rax, [r15+50h]
0x180007d4d  test    dword ptr [rax+4], 100000h
0x180007d54  jz      short loc_180007D92
0x180007d56  lea     rax, [rbp+57h+var_A0]
0x180007d5a  mov     r9, r8
0x180007d5d  mov     [rsp+0F0h+var_C8], rax
0x180007d62  mov     r8, rbx
0x180007d65  mov     rdx, r12
0x180007d68  mov     [rsp+0F0h+var_D0], r14
0x180007d6d  mov     rcx, rdi
0x180007d70  call    selectWindowRewriteEList
0x180007d75  mov     rsi, [rbp+57h+var_A0]
0x180007d79  test    rsi, rsi
0x180007d7c  jz      short loc_180007D82
0x180007d7e  mov     eax, [rsi]
0x180007d80  jmp     short loc_180007D84
0x180007d82  xor     eax, eax
0x180007d84  mov     [r15+7Ch], eax
0x180007d88  mov     byte ptr [r15+8Ch], 1
0x180007d90  jmp     short loc_180007DB6
0x180007d92  test    rsi, rsi
0x180007d95  jz      short loc_180007D9B
0x180007d97  mov     eax, [rsi]
0x180007d99  jmp     short loc_180007D9D
0x180007d9b  xor     eax, eax
0x180007d9d  xor     r9d, r9d
0x180007da0  mov     [r15+7Ch], eax
0x180007da4  mov     rdx, rsi
0x180007da7  mov     rcx, rdi
0x180007daa  call    exprListAppendList
0x180007daf  mov     rsi, rax
0x180007db2  mov     [rbp+57h+var_A0], rax
0x180007db6  mov     rdx, [r15+48h]
0x180007dba  test    rdx, rdx
0x180007dbd  jz      short loc_180007DDF
0x180007dbf  xor     r8d, r8d
0x180007dc2  mov     rcx, r13
0x180007dc5  call    sqlite3ExprDup
0x180007dca  mov     r8, rax
0x180007dcd  mov     rdx, rsi
0x180007dd0  mov     rcx, rdi
0x180007dd3  call    sqlite3ExprListAppend
0x180007dd8  mov     rsi, rax
0x180007ddb  mov     [rbp+57h+var_A0], rax
0x180007ddf  mov     eax, [rdi+38h]
0x180007de2  xor     r8d, r8d
0x180007de5  mov     rcx, [rbp+57h+var_58]
0x180007de9  inc     eax
0x180007deb  mov     [rdi+38h], eax
0x180007dee  mov     [r15+5Ch], eax
0x180007df2  mov     eax, [rdi+38h]
0x180007df5  lea     edx, [r8+4Bh]
0x180007df9  inc     eax
0x180007dfb  mov     dword ptr [rsp+0F0h+var_D0], 0
0x180007e03  mov     [rdi+38h], eax
0x180007e06  mov     r9d, [r15+5Ch]
0x180007e0a  mov     [r15+60h], eax
0x180007e0e  call    sqlite3VdbeAddOp3
0x180007e13  mov     r15, [r15+40h]
0x180007e17  test    r15, r15
0x180007e1a  jnz     loc_180007D41
0x180007e20  mov     rbx, [rbp+57h+arg_8]
0x180007e24  mov     r12d, [rbp+57h+arg_10]
0x180007e28  test    rsi, rsi
0x180007e2b  jnz     short loc_180007E51
0x180007e2d  lea     r8, a0; "0"
0x180007e34  mov     edx, 9Bh
0x180007e39  mov     rcx, r13
0x180007e3c  call    sqlite3Expr
0x180007e41  mov     r8, rax
0x180007e44  xor     edx, edx
0x180007e46  mov     rcx, rdi
0x180007e49  call    sqlite3ExprListAppend
0x180007e4e  mov     rsi, rax
0x180007e51  mov     rax, [rbp+57h+var_50]
0x180007e55  mov     rdx, rsi
0x180007e58  mov     r9, [rbp+57h+var_38]
0x180007e5c  mov     rcx, rdi
0x180007e5f  mov     r8, [rbp+57h+var_90]
0x180007e63  mov     [rsp+0F0h+var_B0], r12
0x180007e68  mov     [rsp+0F0h+var_B8], r12d
0x180007e6d  mov     [rsp+0F0h+var_C0], rax
0x180007e72  mov     rax, [rbp+57h+var_48]
0x180007e76  mov     [rsp+0F0h+var_C8], rax
0x180007e7b  mov     rax, [rbp+57h+var_40]
0x180007e7f  mov     [rsp+0F0h+var_D0], rax
0x180007e84  call    sqlite3SelectNew
0x180007e89  xor     r9d, r9d
0x180007e8c  xor     r8d, r8d
0x180007e8f  xor     edx, edx
0x180007e91  mov     rcx, rdi
0x180007e94  mov     rsi, rax
0x180007e97  call    sqlite3SrcListAppend
0x180007e9c  mov     [rbx+28h], rax
0x180007ea0  mov     r15d, 7
0x180007ea6  test    rax, rax
0x180007ea9  jz      loc_180007F80
0x180007eaf  mov     [rax+30h], rsi
0x180007eb3  mov     rcx, rdi
0x180007eb6  mov     rax, [rbx+28h]
0x180007eba  or      dword ptr [rax+48h], 8
0x180007ebe  mov     rdx, [rbx+28h]
0x180007ec2  call    sqlite3SrcListAssignCursors
0x180007ec7  or      dword ptr [rsi+4], 8000040h
0x180007ece  mov     rdx, rsi
0x180007ed1  mov     rcx, rdi
0x180007ed4  mov     r8b, 40h ; '@'
0x180007ed7  call    sqlite3ResultSetOfSelect
0x180007edc  mov     rcx, rax
0x180007edf  mov     eax, [rbp+57h+arg_18]
0x180007ee2  and     eax, 8
0x180007ee5  or      [rsi+4], eax
0x180007ee8  test    rcx, rcx
0x180007eeb  jnz     short loc_180007EF5
0x180007eed  mov     r12d, r15d
0x180007ef0  jmp     loc_180007F8B
0x180007ef5  movups  xmm0, xmmword ptr [rcx]
0x180007ef8  mov     rdx, rsi
0x180007efb  movups  xmmword ptr [r14], xmm0
0x180007eff  movups  xmm1, xmmword ptr [rcx+10h]
0x180007f03  movups  xmmword ptr [r14+10h], xmm1
0x180007f08  movups  xmm0, xmmword ptr [rcx+20h]
0x180007f0c  movups  xmmword ptr [r14+20h], xmm0
0x180007f11  movups  xmm1, xmmword ptr [rcx+30h]
0x180007f15  movups  xmmword ptr [r14+30h], xmm1
0x180007f1a  movups  xmm0, xmmword ptr [rcx+40h]
0x180007f1e  movups  xmmword ptr [r14+40h], xmm0
0x180007f23  movups  xmm1, xmmword ptr [rcx+50h]
0x180007f27  movups  xmmword ptr [r14+50h], xmm1
0x180007f2c  movsd   xmm0, qword ptr [rcx+60h]
0x180007f31  movsd   qword ptr [r14+60h], xmm0
0x180007f37  xorps   xmm0, xmm0
0x180007f3a  bts     dword ptr [r14+30h], 0Eh
0x180007f40  mov     rax, [rbx+28h]
0x180007f44  mov     [rax+28h], r14
0x180007f48  lea     rax, sqlite3WindowExtraAggFuncDepth
0x180007f4f  mov     qword ptr [rbp+57h+var_88+8], rax
0x180007f53  mov     r14, rcx
0x180007f56  lea     rax, sqlite3WalkerDepthIncrease
0x180007f5d  mov     qword ptr [rbp+57h+var_88], r12
0x180007f61  mov     qword ptr [rbp+57h+var_78], rax
0x180007f65  lea     rcx, [rbp+57h+var_88]
0x180007f69  lea     rax, sqlite3WalkerDepthDecrease
0x180007f70  mov     qword ptr [rbp+57h+var_78+8], rax
  ... truncated ...
```
