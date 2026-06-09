# updateAccumulator

- ea: `0x180049d94`
- end: `0x18004a1fd`
- name: `updateAccumulator`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180005650`

## callees

- `0x180008be8`
- `0x180009ac0`
- `0x18000d04c`
- `0x180015700`
- `0x1800168c0`
- `0x180016d00`
- `0x18001c170`
- `0x18001e090`
- `0x18001e860`
- `0x180049d94`
- `0x18004a3f8`
- `0x18004a438`
- `0x180052840`
- `0x180062418`
- `0x18007406c`

## pseudocode

```c
__int64 __fastcall updateAccumulator(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 result; // rax
  __int64 v5; // r15
  _DWORD *v6; // rsi
  __int64 v7; // rbp
  int v8; // r13d
  _QWORD *v9; // r14
  unsigned int *v10; // rbx
  __int64 v11; // r12
  int v12; // edi
  int *v13; // rbx
  int v14; // ecx
  int v15; // edx
  int v16; // eax
  unsigned int TempRange; // r12d
  int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // edx
  int v21; // ebx
  unsigned int v22; // r15d
  unsigned int v23; // esi
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // eax
  _QWORD *v27; // rbx
  __int64 v28; // rcx
  _DWORD *v29; // rbx
  unsigned int v30; // r14d
  __int64 v31; // r13
  int i; // edi
  unsigned int v33; // [rsp+40h] [rbp-68h]
  unsigned int v34; // [rsp+44h] [rbp-64h]
  int v35; // [rsp+48h] [rbp-60h]
  unsigned int v36; // [rsp+4Ch] [rbp-5Ch]
  int v37; // [rsp+4Ch] [rbp-5Ch]
  int v38; // [rsp+50h] [rbp-58h]
  unsigned int *v39; // [rsp+58h] [rbp-50h]
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+0h] BYREF
  int v42; // [rsp+B8h] [rbp+10h]

  result = (__int64)&retaddr;
  v42 = a2;
  v5 = a3;
  v6 = (_DWORD *)a1;
  if ( *(_DWORD *)(a1 + 48) )
    return result;
  v7 = *(_QWORD *)(a1 + 16);
  v8 = 0;
  v9 = *(_QWORD **)(a3 + 40);
  *(_BYTE *)a3 = 1;
  v38 = 0;
  if ( *(int *)(a3 + 48) <= 0 )
  {
LABEL_56:
    v30 = 0;
    v29 = (_DWORD *)(v5 + 36);
    if ( !*(_DWORD *)(v5 + 36) )
      goto LABEL_59;
    v8 = a2;
    if ( !a2 )
      goto LABEL_59;
    goto LABEL_58;
  }
  do
  {
    v34 = 0;
    v10 = *(unsigned int **)(*v9 + 32LL);
    v39 = v10;
    if ( (*(_DWORD *)(*v9 + 4LL) & 0x1000000) != 0 )
    {
      v11 = *(_QWORD *)(*(_QWORD *)(*v9 + 64LL) + 72LL);
      if ( *(_DWORD *)(v5 + 36) && (*(_BYTE *)(v9[1] + 4LL) & 0x20) != 0 && a2 )
      {
        if ( !v8 )
          v8 = ++v6[14];
        sqlite3VdbeAddOp3(v7, 80, a2, v8, 0);
      }
      v34 = --v6[17];
      sqlite3ExprIfFalse(v6, v11, v34, 16);
    }
    if ( *((int *)v9 + 6) < 0 )
    {
      v36 = 0;
      if ( v10 )
      {
        v12 = *v10;
        TempRange = sqlite3GetTempRange(v6, *v10);
        sqlite3ExprCodeExprList((_DWORD)v6, (_DWORD)v10, TempRange, 0, 1);
        v19 = TempRange;
      }
      else
      {
        v19 = 0;
        v12 = 0;
        TempRange = 0;
      }
    }
    else
    {
      v12 = *v10;
      v13 = *(int **)(*(_QWORD *)(*v9 + 16LL) + 32LL);
      v14 = *v13 + 1;
      if ( *((_BYTE *)v9 + 29) )
        v14 = *v13;
      v15 = v14 + v12;
      if ( !*((_BYTE *)v9 + 28) )
        v15 = v14;
      v16 = v15 + v12;
      if ( !*((_BYTE *)v9 + 30) )
        v16 = v15;
      v36 = v16 + 1;
      v33 = sqlite3GetTempRange(v6, (unsigned int)(v16 + 1));
      TempRange = v33;
      sqlite3ExprCodeExprList((_DWORD)v6, (_DWORD)v13, v33, 0, 1);
      v18 = *v13;
      v35 = *v13;
      if ( !*((_BYTE *)v9 + 29) )
      {
        sqlite3VdbeAddOp3(v7, 126, *((_DWORD *)v9 + 6), v18 + v33, 0);
        v18 = ++v35;
      }
      v10 = v39;
      if ( *((_BYTE *)v9 + 28) )
      {
        v33 += v18;
        sqlite3ExprCodeExprList((_DWORD)v6, (_DWORD)v39, TempRange + v18, 0, 1);
        v18 = v12 + v35;
      }
      v19 = v33;
      if ( *((_BYTE *)v9 + 30) )
      {
        v20 = TempRange;
        if ( *((_BYTE *)v9 + 28) )
          v20 = v33;
        if ( v12 > 0 )
        {
          v21 = 0;
          v22 = v18 + TempRange;
          v23 = v20;
          do
            sqlite3VdbeAddOp3(v7, 181, v23 + v21++, v22++, 0);
          while ( v21 < v12 );
          v6 = (_DWORD *)a1;
          v5 = a3;
          v10 = v39;
          v19 = v33;
        }
      }
    }
    if ( *((int *)v9 + 4) >= 0 && v10 )
    {
      v24 = v34;
      if ( !v34 )
      {
        v24 = --v6[17];
        v34 = v24;
      }
      *((_DWORD *)v9 + 4) = codeDistinct((_DWORD)v6, a4, *((_DWORD *)v9 + 4), v24, (__int64)v10, v19);
    }
    if ( *((int *)v9 + 6) < 0 )
    {
      if ( (*(_BYTE *)(v9[1] + 4LL) & 0x20) != 0 )
      {
        v26 = 0;
        v37 = 0;
        v27 = v10 + 2;
        while ( v26 < v12 )
        {
          v28 = sqlite3ExprCollSeq(v6, *v27);
          v27 += 4;
          v26 = ++v37;
          if ( v28 )
            goto LABEL_45;
        }
        v28 = *(_QWORD *)(*(_QWORD *)v6 + 16LL);
LABEL_45:
        if ( !v8 && *(_DWORD *)(v5 + 36) )
          v8 = ++v6[14];
        sqlite3VdbeAddOp4(v7, 85, v8, 0, 0, v28, -2);
      }
      sqlite3VdbeAddOp3(v7, 162, 0, TempRange, v38 + *(_DWORD *)(v5 + 12) + *(_DWORD *)(v5 + 32));
      sqlite3VdbeAppendP4(v7, v9[1], 4294967289LL);
      sqlite3VdbeChangeP5(v7, (unsigned __int8)v12);
      v25 = v12;
    }
    else
    {
      sqlite3VdbeAddOp3(v7, 97, TempRange, v36 - 1, TempRange + v36 - 1);
      sqlite3VdbeAddOp4Int(v7, 138, *((_DWORD *)v9 + 6), TempRange + v36 - 1, TempRange, v36 - 1);
      v25 = v36;
    }
    sqlite3ReleaseTempRange(v6, TempRange, v25);
    result = v34;
    if ( v34 )
      result = sqlite3VdbeResolveLabel(v7, v34);
    v9 += 4;
    a2 = v42;
    ++v38;
  }
  while ( v38 < *(_DWORD *)(v5 + 48) );
  if ( !v8 )
  {
    a2 = v42;
    goto LABEL_56;
  }
  v29 = (_DWORD *)(v5 + 36);
LABEL_58:
  result = sqlite3VdbeAddOp3(v7, 16, v8, 0, 0);
  v30 = result;
LABEL_59:
  v31 = *(_QWORD *)(v5 + 24);
  for ( i = 0; i < *v29; v31 += 24 )
  {
    result = sqlite3ExprCode(v6, *(_QWORD *)(v31 + 8), (unsigned int)(i + *(_DWORD *)(v5 + 12)));
    ++i;
  }
  *(_BYTE *)v5 = 0;
  if ( v30 )
    return sqlite3VdbeJumpHereOrPopInst(v7, v30);
  return result;
}

```

## disassembly

```asm
0x180049d94  mov     rax, rsp
0x180049d97  mov     [rax+20h], r9d
0x180049d9b  mov     [rax+18h], r8
0x180049d9f  mov     [rax+10h], edx
0x180049da2  mov     [rax+8], rcx
0x180049da6  push    rbx
0x180049da7  push    rbp
0x180049da8  push    rsi
0x180049da9  push    rdi
0x180049daa  push    r12
0x180049dac  push    r13
0x180049dae  push    r14
0x180049db0  push    r15
0x180049db2  sub     rsp, 68h
0x180049db6  cmp     dword ptr [rcx+30h], 0
0x180049dba  mov     r15, r8
0x180049dbd  mov     rsi, rcx
0x180049dc0  jnz     loc_18004A1EC
0x180049dc6  mov     rbp, [rcx+10h]
0x180049dca  xor     r13d, r13d
0x180049dcd  mov     r14, [r8+28h]
0x180049dd1  mov     byte ptr [r8], 1
0x180049dd5  mov     [rsp+0A8h+var_58], r13d
0x180049dda  cmp     [r8+30h], r13d
0x180049dde  jle     loc_18004A181
0x180049de4  mov     rax, [r14]
0x180049de7  mov     [rsp+0A8h+var_64], 0
0x180049def  test    dword ptr [rax+4], 1000000h
0x180049df6  mov     rbx, [rax+20h]
0x180049dfa  mov     [rsp+0A8h+var_50], rbx
0x180049dff  jz      short loc_180049E63
0x180049e01  cmp     dword ptr [r15+24h], 0
0x180049e06  mov     rax, [rax+40h]
0x180049e0a  mov     r12, [rax+48h]
0x180049e0e  jz      short loc_180049E45
0x180049e10  mov     rax, [r14+8]
0x180049e14  test    byte ptr [rax+4], 20h
0x180049e18  jz      short loc_180049E45
0x180049e1a  test    edx, edx
0x180049e1c  jz      short loc_180049E45
0x180049e1e  test    r13d, r13d
0x180049e21  jnz     short loc_180049E2A
0x180049e23  inc     dword ptr [rsi+38h]
0x180049e26  mov     r13d, [rsi+38h]
0x180049e2a  mov     r8d, edx
0x180049e2d  mov     dword ptr [rsp+0A8h+var_88], 0
0x180049e35  mov     edx, 50h ; 'P'
0x180049e3a  mov     r9d, r13d
0x180049e3d  mov     rcx, rbp
0x180049e40  call    sqlite3VdbeAddOp3
0x180049e45  dec     dword ptr [rsi+44h]
0x180049e48  mov     r9d, 10h
0x180049e4e  mov     edi, [rsi+44h]
0x180049e51  mov     rdx, r12
0x180049e54  mov     r8d, edi
0x180049e57  mov     [rsp+0A8h+var_64], edi
0x180049e5b  mov     rcx, rsi
0x180049e5e  call    sqlite3ExprIfFalse
0x180049e63  cmp     dword ptr [r14+18h], 0
0x180049e68  jl      loc_180049FA2
0x180049e6e  cmp     byte ptr [r14+1Dh], 0
0x180049e73  mov     edi, [rbx]
0x180049e75  mov     rax, [r14]
0x180049e78  mov     rcx, [rax+10h]
0x180049e7c  mov     rbx, [rcx+20h]
0x180049e80  mov     eax, [rbx]
0x180049e82  lea     ecx, [rax+1]
0x180049e85  cmovnz  ecx, eax
0x180049e88  cmp     byte ptr [r14+1Ch], 0
0x180049e8d  lea     edx, [rcx+rdi]
0x180049e90  cmovz   edx, ecx
0x180049e93  cmp     byte ptr [r14+1Eh], 0
0x180049e98  mov     rcx, rsi
0x180049e9b  lea     eax, [rdx+rdi]
0x180049e9e  cmovz   eax, edx
0x180049ea1  inc     eax
0x180049ea3  mov     edx, eax
0x180049ea5  mov     [rsp+0A8h+var_5C], eax
0x180049ea9  call    sqlite3GetTempRange
0x180049eae  xor     r9d, r9d
0x180049eb1  mov     [rsp+0A8h+var_68], eax
0x180049eb5  mov     r8d, eax
0x180049eb8  mov     byte ptr [rsp+0A8h+var_88], 1
0x180049ebd  mov     rcx, rsi
0x180049ec0  mov     rdx, rbx
0x180049ec3  mov     r12d, eax
0x180049ec6  call    sqlite3ExprCodeExprList
0x180049ecb  cmp     byte ptr [r14+1Dh], 0
0x180049ed0  mov     eax, [rbx]
0x180049ed2  mov     [rsp+0A8h+var_60], eax
0x180049ed6  jnz     short loc_180049EFF
0x180049ed8  mov     r8d, [r14+18h]
0x180049edc  lea     r9d, [rax+r12]
0x180049ee0  mov     edx, 7Eh ; '~'
0x180049ee5  mov     dword ptr [rsp+0A8h+var_88], 0
0x180049eed  mov     rcx, rbp
0x180049ef0  call    sqlite3VdbeAddOp3
0x180049ef5  mov     eax, [rsp+0A8h+var_60]
0x180049ef9  inc     eax
0x180049efb  mov     [rsp+0A8h+var_60], eax
0x180049eff  cmp     byte ptr [r14+1Ch], 0
0x180049f04  mov     rbx, [rsp+0A8h+var_50]
0x180049f09  jz      short loc_180049F2E
0x180049f0b  add     eax, r12d
0x180049f0e  mov     byte ptr [rsp+0A8h+var_88], 1
0x180049f13  mov     r8d, eax
0x180049f16  mov     [rsp+0A8h+var_68], eax
0x180049f1a  xor     r9d, r9d
0x180049f1d  mov     rdx, rbx
0x180049f20  mov     rcx, rsi
0x180049f23  call    sqlite3ExprCodeExprList
0x180049f28  mov     eax, [rsp+0A8h+var_60]
0x180049f2c  add     eax, edi
0x180049f2e  cmp     byte ptr [r14+1Eh], 0
0x180049f33  mov     ecx, [rsp+0A8h+var_68]
0x180049f37  jz      loc_180049FE0
0x180049f3d  cmp     byte ptr [r14+1Ch], 0
0x180049f42  mov     edx, r12d
0x180049f45  mov     [rsp+0A8h+var_60], 0
0x180049f4d  cmovnz  edx, ecx
0x180049f50  test    edi, edi
0x180049f52  jle     loc_180049FE0
0x180049f58  mov     ebx, [rsp+0A8h+var_60]
0x180049f5c  lea     r15d, [rax+r12]
0x180049f60  mov     esi, edx
0x180049f62  lea     r8d, [rsi+rbx]
0x180049f66  mov     dword ptr [rsp+0A8h+var_88], 0
0x180049f6e  mov     r9d, r15d
0x180049f71  mov     edx, 0B5h
0x180049f76  mov     rcx, rbp
0x180049f79  call    sqlite3VdbeAddOp3
0x180049f7e  inc     ebx
0x180049f80  inc     r15d
0x180049f83  cmp     ebx, edi
0x180049f85  jl      short loc_180049F62
0x180049f87  mov     rsi, [rsp+0A8h+arg_0]
0x180049f8f  mov     r15, [rsp+0A8h+arg_10]
0x180049f97  mov     rbx, [rsp+0A8h+var_50]
0x180049f9c  mov     ecx, [rsp+0A8h+var_68]
0x180049fa0  jmp     short loc_180049FE0
0x180049fa2  mov     [rsp+0A8h+var_5C], 0
0x180049faa  test    rbx, rbx
0x180049fad  jz      short loc_180049FD9
0x180049faf  mov     edi, [rbx]
0x180049fb1  mov     rcx, rsi
0x180049fb4  mov     edx, edi
0x180049fb6  call    sqlite3GetTempRange
0x180049fbb  xor     r9d, r9d
0x180049fbe  mov     byte ptr [rsp+0A8h+var_88], 1
0x180049fc3  mov     r8d, eax
0x180049fc6  mov     rcx, rsi
0x180049fc9  mov     rdx, rbx
0x180049fcc  mov     r12d, eax
0x180049fcf  call    sqlite3ExprCodeExprList
0x180049fd4  mov     ecx, r12d
0x180049fd7  jmp     short loc_180049FE0
0x180049fd9  xor     ecx, ecx
0x180049fdb  xor     edi, edi
0x180049fdd  xor     r12d, r12d
0x180049fe0  cmp     dword ptr [r14+10h], 0
0x180049fe5  jl      short loc_18004A021
0x180049fe7  test    rbx, rbx
0x180049fea  jz      short loc_18004A021
0x180049fec  mov     eax, [rsp+0A8h+var_64]
0x180049ff0  test    eax, eax
0x180049ff2  jnz     short loc_180049FFE
0x180049ff4  dec     dword ptr [rsi+44h]
0x180049ff7  mov     eax, [rsi+44h]
0x180049ffa  mov     [rsp+0A8h+var_64], eax
0x180049ffe  mov     r8d, [r14+10h]
0x18004a002  mov     r9d, eax
0x18004a005  mov     edx, [rsp+0A8h+arg_18]
0x18004a00c  mov     dword ptr [rsp+0A8h+var_80], ecx
0x18004a010  mov     rcx, rsi
0x18004a013  mov     [rsp+0A8h+var_88], rbx
0x18004a018  call    codeDistinct
0x18004a01d  mov     [r14+10h], eax
0x18004a021  cmp     dword ptr [r14+18h], 0
0x18004a026  jl      short loc_18004A072
0x18004a028  mov     eax, [rsp+0A8h+var_5C]
0x18004a02c  mov     r8d, r12d
0x18004a02f  mov     edx, 61h ; 'a'
0x18004a034  mov     rcx, rbp
0x18004a037  lea     edi, [rax-1]
0x18004a03a  lea     ebx, [rax-1]
0x18004a03d  add     edi, r12d
0x18004a040  mov     r9d, ebx
0x18004a043  mov     dword ptr [rsp+0A8h+var_88], edi
0x18004a047  call    sqlite3VdbeAddOp3
0x18004a04c  mov     r8d, [r14+18h]
0x18004a050  mov     r9d, edi
0x18004a053  mov     edx, 8Ah
0x18004a058  mov     dword ptr [rsp+0A8h+var_80], ebx
0x18004a05c  mov     rcx, rbp
0x18004a05f  mov     dword ptr [rsp+0A8h+var_88], r12d
0x18004a064  call    sqlite3VdbeAddOp4Int
0x18004a069  mov     eax, [rsp+0A8h+var_5C]
0x18004a06d  jmp     loc_18004A130
0x18004a072  mov     rax, [r14+8]
0x18004a076  test    byte ptr [rax+4], 20h
0x18004a07a  jz      short loc_18004A0ED
0x18004a07c  xor     eax, eax
0x18004a07e  mov     [rsp+0A8h+var_5C], eax
0x18004a082  add     rbx, 8
0x18004a086  cmp     eax, edi
0x18004a088  jge     short loc_18004A0AD
0x18004a08a  mov     rdx, [rbx]
0x18004a08d  mov     rcx, rsi
0x18004a090  call    sqlite3ExprCollSeq
0x18004a095  mov     rcx, rax
0x18004a098  add     rbx, 20h ; ' '
0x18004a09c  mov     eax, [rsp+0A8h+var_5C]
0x18004a0a0  inc     eax
0x18004a0a2  mov     [rsp+0A8h+var_5C], eax
0x18004a0a6  test    rcx, rcx
0x18004a0a9  jz      short loc_18004A086
0x18004a0ab  jmp     short loc_18004A0B4
0x18004a0ad  mov     rax, [rsi]
0x18004a0b0  mov     rcx, [rax+10h]
0x18004a0b4  test    r13d, r13d
0x18004a0b7  jnz     short loc_18004A0C6
0x18004a0b9  cmp     [r15+24h], r13d
0x18004a0bd  jz      short loc_18004A0C6
0x18004a0bf  inc     dword ptr [rsi+38h]
0x18004a0c2  mov     r13d, [rsi+38h]
0x18004a0c6  xor     r9d, r9d
0x18004a0c9  mov     [rsp+0A8h+var_78], 0FFFFFFFEh
0x18004a0d1  mov     [rsp+0A8h+var_80], rcx
0x18004a0d6  mov     r8d, r13d
0x18004a0d9  mov     rcx, rbp
0x18004a0dc  mov     dword ptr [rsp+0A8h+var_88], 0
0x18004a0e4  lea     edx, [r9+55h]
0x18004a0e8  call    sqlite3VdbeAddOp4
0x18004a0ed  mov     eax, [r15+20h]
0x18004a0f1  mov     r9d, r12d
0x18004a0f4  add     eax, [r15+0Ch]
0x18004a0f8  xor     r8d, r8d
0x18004a0fb  add     eax, [rsp+0A8h+var_58]
0x18004a0ff  mov     edx, 0A2h
0x18004a104  mov     rcx, rbp
0x18004a107  mov     dword ptr [rsp+0A8h+var_88], eax
0x18004a10b  call    sqlite3VdbeAddOp3
0x18004a110  mov     rdx, [r14+8]
0x18004a114  mov     r8d, 0FFFFFFF9h
0x18004a11a  mov     rcx, rbp
0x18004a11d  call    sqlite3VdbeAppendP4
0x18004a122  movzx   edx, dil
0x18004a126  mov     rcx, rbp
0x18004a129  call    sqlite3VdbeChangeP5
0x18004a12e  mov     eax, edi
0x18004a130  mov     r8d, eax
0x18004a133  mov     edx, r12d
0x18004a136  mov     rcx, rsi
0x18004a139  call    sqlite3ReleaseTempRange
0x18004a13e  mov     eax, [rsp+0A8h+var_64]
0x18004a142  test    eax, eax
0x18004a144  jz      short loc_18004A150
0x18004a146  mov     edx, eax
0x18004a148  mov     rcx, rbp
0x18004a14b  call    sqlite3VdbeResolveLabel
0x18004a150  mov     ecx, [rsp+0A8h+var_58]
0x18004a154  add     r14, 20h ; ' '
0x18004a158  mov     edx, [rsp+0A8h+arg_8]
0x18004a15f  inc     ecx
0x18004a161  mov     [rsp+0A8h+var_58], ecx
0x18004a165  cmp     ecx, [r15+30h]
0x18004a169  jl      loc_180049DE4
0x18004a16f  test    r13d, r13d
0x18004a172  jz      short loc_18004A17A
0x18004a174  lea     rbx, [r15+24h]
0x18004a178  jmp     short loc_18004A194
0x18004a17a  mov     edx, [rsp+0A8h+arg_8]
0x18004a181  xor     r14d, r14d
0x18004a184  lea     rbx, [r15+24h]
0x18004a188  cmp     [rbx], r14d
0x18004a18b  jz      short loc_18004A1B1
0x18004a18d  mov     r13d, edx
0x18004a190  test    edx, edx
0x18004a192  jz      short loc_18004A1B1
0x18004a194  xor     r9d, r9d
0x18004a197  mov     dword ptr [rsp+0A8h+var_88], 0
0x18004a19f  mov     r8d, r13d
0x18004a1a2  mov     rcx, rbp
0x18004a1a5  lea     edx, [r9+10h]
0x18004a1a9  call    sqlite3VdbeAddOp3
0x18004a1ae  mov     r14d, eax
0x18004a1b1  mov     r13, [r15+18h]
0x18004a1b5  xor     edi, edi
0x18004a1b7  cmp     [rbx], edi
0x18004a1b9  jle     short loc_18004A1D8
0x18004a1bb  mov     r8d, [r15+0Ch]
0x18004a1bf  mov     rcx, rsi
0x18004a1c2  mov     rdx, [r13+8]
0x18004a1c6  add     r8d, edi
0x18004a1c9  call    sqlite3ExprCode
0x18004a1ce  inc     edi
0x18004a1d0  lea     r13, [r13+18h]
0x18004a1d4  cmp     edi, [rbx]
0x18004a1d6  jl      short loc_18004A1BB
0x18004a1d8  mov     byte ptr [r15], 0
  ... truncated ...
```
