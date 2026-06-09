# generateSortTail

- ea: `0x18007fcec`
- end: `0x180080259`
- name: `generateSortTail`
- size: `1389`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180005650`

## callees

- `0x18000506c`
- `0x180008be8`
- `0x180009ac0`
- `0x180015700`
- `0x1800168c0`
- `0x18001e090`
- `0x18004a3f8`
- `0x18004a418`
- `0x18004a438`
- `0x18004a478`
- `0x18005998c`
- `0x18006e790`
- `0x18007fcec`

## string_xrefs

- `0x18007fd94`: `USE TEMP B-TREE FOR %sORDER BY`
- `0x18007fd6c`: `USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY`

## pseudocode

```c
__int64 __fastcall generateSortTail(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned __int8 *a5)
{
  __int64 v8; // rbx
  __int64 v9; // r12
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // r13d
  int v13; // r15d
  const char *v14; // r9
  int v15; // r9d
  unsigned int v16; // edx
  int v17; // r10d
  __int64 v18; // rdx
  unsigned int TempReg; // r13d
  unsigned int TempRange; // esi
  unsigned int v21; // ebp
  __int64 v22; // r8
  int v23; // r9d
  int v24; // ebp
  __int64 v25; // r9
  int v26; // r8d
  int v27; // ebp
  unsigned int i; // edx
  int v29; // ecx
  int v30; // r15d
  int v31; // ecx
  int v32; // r9d
  char v33; // dl
  int v34; // r8d
  unsigned int v35; // r9d
  int v36; // edx
  int v37; // r15d
  int v38; // ebp
  int v39; // r8d
  int v41; // [rsp+40h] [rbp-68h]
  int v42; // [rsp+44h] [rbp-64h]
  unsigned int v43; // [rsp+48h] [rbp-60h]
  unsigned int v44; // [rsp+4Ch] [rbp-5Ch]
  int v45; // [rsp+50h] [rbp-58h]
  __int64 v46; // [rsp+58h] [rbp-50h]
  int v47; // [rsp+B0h] [rbp+8h]
  int v49; // [rsp+B8h] [rbp+10h]
  int v50; // [rsp+B8h] [rbp+10h]
  int v52; // [rsp+C8h] [rbp+20h]

  --*(_DWORD *)(a1 + 68);
  v8 = *(_QWORD *)(a1 + 16);
  v9 = a3;
  v43 = *(_DWORD *)(a3 + 28);
  v10 = *(_DWORD *)(a1 + 68);
  v11 = *(_DWORD *)(a3 + 8);
  v12 = *a5;
  v44 = v10;
  v41 = *((_DWORD *)a5 + 1);
  v52 = v12;
  v46 = *(_QWORD *)(a2 + 32) + 8LL;
  v13 = **(_DWORD **)a3 - v11;
  if ( !v11 || v13 == 1 )
  {
    v14 = "LAST TERM OF ";
    if ( !v11 )
      v14 = (const char *)&Src;
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %sORDER BY", v14);
  }
  else
  {
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR LAST %d TERMS OF ORDER BY", v13);
  }
  v15 = *(_DWORD *)(v9 + 20);
  v16 = 0;
  if ( v15 )
  {
    sqlite3VdbeAddOp3(v8, 10, *(_DWORD *)(v9 + 16), v15, 0);
    sqlite3VdbeAddOp3(v8, 9, 0, v43, 0);
    sqlite3VdbeResolveLabel(v8, *(unsigned int *)(v9 + 20));
    v16 = 0;
  }
  v17 = *(_DWORD *)(v9 + 12);
  v42 = v17;
  if ( ((v12 - 9) & 0xFFFFFFFB) == 0 )
    goto LABEL_16;
  if ( v12 == 10 )
  {
    if ( *(_DWORD *)(a2 + 12) )
    {
      sqlite3VdbeAddOp3(v8, 75, 0, *((_DWORD *)a5 + 3), 0);
      v17 = v42;
      v16 = 0;
    }
LABEL_16:
    TempRange = *((_DWORD *)a5 + 3);
    TempReg = 0;
    goto LABEL_17;
  }
  TempReg = sqlite3GetTempReg(a1, 0);
  if ( ((v52 - 12) & 0xFFFFFFFD) != 0 )
  {
    TempRange = sqlite3GetTempRange(a1, a4);
    v16 = 0;
  }
  else
  {
    TempRange = sqlite3GetTempReg(a1, v18);
    a4 = v16;
  }
LABEL_17:
  if ( (*(_BYTE *)(v9 + 36) & 1) != 0 )
  {
    ++*(_DWORD *)(a1 + 56);
    v21 = v16;
    v49 = *(_DWORD *)(a1 + 56);
    v47 = *(_DWORD *)(a1 + 52);
    *(_DWORD *)(a1 + 52) = v47 + 1;
    if ( *(_DWORD *)(v9 + 20) != v16 )
      v21 = sqlite3VdbeAddOp3(v8, 15, 0, 0, v16);
    sqlite3VdbeAddOp3(v8, 121, v47, v49, a4 + v13 + 1);
    v23 = 0;
    if ( v21 )
      *(_DWORD *)(sqlite3VdbeGetOp(v8, v21, v22, 0) + 8) = *(_DWORD *)(v8 + 144);
    v45 = sqlite3VdbeAddOp3(v8, 34, v42, v43, v23) + 1;
    sqlite3VdbeAddOp3(v8, 133, v42, v49, v47);
    v24 = 0;
  }
  else
  {
    v45 = sqlite3VdbeAddOp3(v8, 35, v17, v43, v16) + 1;
    codeOffset(v8, *(unsigned int *)(a2 + 12), v44);
    v24 = 1;
    v47 = v42;
    if ( *(int *)(a2 + 12) > 0 )
      sqlite3VdbeAddOp3(v8, 86, *(_DWORD *)(a2 + 8), -1, 0);
  }
  v25 = v46;
  v26 = v13 + v24;
  v50 = v13 + v24;
  v27 = v13 + v24 - 1;
  for ( i = 0; (int)i < (int)a4; v27 = v29 )
  {
    v29 = v27 + 1;
    if ( *(_WORD *)(32LL * i + v46 + 24) )
      v29 = v27;
    ++i;
  }
  v30 = a4 - 1;
  if ( (int)(a4 - 1) >= 0 )
  {
    do
    {
      v31 = *(unsigned __int16 *)(32LL * (unsigned int)v30 + v25 + 24);
      if ( (_WORD)v31 )
        v32 = v31 - 1;
      else
        v32 = v27--;
      sqlite3VdbeAddOp3(v8, 94, v47, v32, v30 + TempRange);
      --v30;
      v25 = v46;
    }
    while ( v30 >= 0 );
    v9 = a3;
    v26 = v50;
  }
  v33 = v52;
  if ( v52 != 10 )
  {
    switch ( v52 )
    {
      case 11:
        sqlite3VdbeAddOp4(v8, 97, TempRange, a4, TempReg, *((_QWORD *)a5 + 3), a4);
        sqlite3VdbeAddOp4Int(v8, 138, v41, TempReg, TempRange, a4);
        break;
      case 12:
      case 14:
        sqlite3VdbeAddOp3(v8, 94, v47, v26, TempRange);
        sqlite3VdbeAddOp3(v8, 127, v41, TempReg, 0);
        sqlite3VdbeAddOp3(v8, 128, v41, TempRange, TempReg);
        sqlite3VdbeChangeP5(v8, 8);
        break;
      case 15:
        v37 = *((_DWORD *)a5 + 2);
        v38 = sqlite3GetTempReg(a1, 15);
        sqlite3VdbeAddOp3(v8, 97, ((unsigned int)v37 >> 31) + TempRange, a4 - ((unsigned int)v37 >> 31), v38);
        if ( v37 >= 0 )
          sqlite3VdbeAddOp4Int(v8, 138, v41, v38, TempRange, v37);
        else
          sqlite3VdbeAddOp3(v8, 128, v41, v38, TempRange);
        break;
      default:
        if ( (_BYTE)v52 == 9 )
        {
          v34 = *((_DWORD *)a5 + 3);
          v35 = a4;
          v36 = 84;
        }
        else
        {
          v34 = *((_DWORD *)a5 + 1);
          v35 = 0;
          v36 = 12;
        }
        sqlite3VdbeAddOp3(v8, v36, v34, v35, 0);
        break;
    }
    v33 = v52;
  }
  if ( TempReg )
  {
    if ( v33 == 11 )
      sqlite3ReleaseTempRange(a1, TempRange, a4);
    else
      sqlite3ReleaseTempReg(a1, TempRange);
    sqlite3ReleaseTempReg(a1, TempReg);
  }
  sqlite3VdbeResolveLabel(v8, v44);
  sqlite3VdbeAddOp3(v8, 2 * ((*(_BYTE *)(v9 + 36) & 1) == 0) + 37, v42, v45, 0);
  v39 = *(_DWORD *)(v9 + 16);
  if ( v39 )
    sqlite3VdbeAddOp3(v8, 67, v39, 0, 0);
  return sqlite3VdbeResolveLabel(v8, v43);
}

```

## disassembly

```asm
0x18007fcec  mov     [rsp+arg_10], r8
0x18007fcf1  mov     [rsp+arg_8], rdx
0x18007fcf6  push    rbx
0x18007fcf7  push    rbp
0x18007fcf8  push    rsi
0x18007fcf9  push    rdi
0x18007fcfa  push    r12
0x18007fcfc  push    r13
0x18007fcfe  push    r14
0x18007fd00  push    r15
0x18007fd02  sub     rsp, 68h
0x18007fd06  dec     dword ptr [rcx+44h]
0x18007fd09  mov     rdi, rcx
0x18007fd0c  mov     eax, [r8+1Ch]
0x18007fd10  mov     rbp, rdx
0x18007fd13  mov     rsi, [rsp+0A8h+arg_20]
0x18007fd1b  mov     r14d, r9d
0x18007fd1e  mov     rbx, [rcx+10h]
0x18007fd22  mov     r12, r8
0x18007fd25  mov     [rsp+0A8h+var_60], eax
0x18007fd29  mov     eax, [rcx+44h]
0x18007fd2c  mov     ecx, [r8+8]
0x18007fd30  movzx   r13d, byte ptr [rsi]
0x18007fd34  mov     [rsp+0A8h+var_5C], eax
0x18007fd38  mov     eax, [rsi+4]
0x18007fd3b  mov     [rsp+0A8h+var_68], eax
0x18007fd3f  mov     rax, [rdx+20h]
0x18007fd43  xor     edx, edx
0x18007fd45  add     rax, 8
0x18007fd49  mov     [rsp+0A8h+arg_18], r13d
0x18007fd51  mov     [rsp+0A8h+var_50], rax
0x18007fd56  mov     rax, [r8]
0x18007fd59  mov     r15d, [rax]
0x18007fd5c  sub     r15d, ecx
0x18007fd5f  test    ecx, ecx
0x18007fd61  jz      short loc_18007FD7D
0x18007fd63  cmp     r15d, 1
0x18007fd67  jz      short loc_18007FD7D
0x18007fd69  mov     r9d, r15d
0x18007fd6c  lea     r8, aUseTempBTreeFo; "USE TEMP B-TREE FOR LAST %d TERMS OF OR"...
0x18007fd73  mov     rcx, rdi
0x18007fd76  call    sqlite3VdbeExplain
0x18007fd7b  jmp     short loc_18007FDA0
0x18007fd7d  test    ecx, ecx
0x18007fd7f  lea     rax, Src
0x18007fd86  lea     r9, aLastTermOf; "LAST TERM OF "
0x18007fd8d  mov     rcx, rdi
0x18007fd90  cmovz   r9, rax
0x18007fd94  lea     r8, aUseTempBTreeFo_1; "USE TEMP B-TREE FOR %sORDER BY"
0x18007fd9b  call    sqlite3VdbeExplain
0x18007fda0  mov     r9d, [r12+14h]
0x18007fda5  xor     edx, edx
0x18007fda7  test    r9d, r9d
0x18007fdaa  jz      short loc_18007FDED
0x18007fdac  mov     r8d, [r12+10h]
0x18007fdb1  mov     rcx, rbx
0x18007fdb4  mov     [rsp+0A8h+var_88], edx
0x18007fdb8  mov     edx, 0Ah
0x18007fdbd  call    sqlite3VdbeAddOp3
0x18007fdc2  xor     r9d, r9d
0x18007fdc5  xor     r8d, r8d
0x18007fdc8  mov     [rsp+0A8h+var_88], r9d
0x18007fdcd  mov     rcx, rbx
0x18007fdd0  mov     r9d, [rsp+0A8h+var_60]
0x18007fdd5  lea     edx, [r8+9]
0x18007fdd9  call    sqlite3VdbeAddOp3
0x18007fdde  mov     edx, [r12+14h]
0x18007fde3  mov     rcx, rbx
0x18007fde6  call    sqlite3VdbeResolveLabel
0x18007fdeb  xor     edx, edx
0x18007fded  mov     r10d, [r12+0Ch]
0x18007fdf2  lea     eax, [r13-9]
0x18007fdf6  mov     [rsp+0A8h+var_64], r10d
0x18007fdfb  test    eax, 0FFFFFFFBh
0x18007fe00  jz      short loc_18007FE65
0x18007fe02  cmp     r13d, 0Ah
0x18007fe06  jz      short loc_18007FE42
0x18007fe08  mov     rcx, rdi
0x18007fe0b  call    sqlite3GetTempReg
0x18007fe10  mov     ecx, [rsp+0A8h+arg_18]
0x18007fe17  mov     r13d, eax
0x18007fe1a  add     ecx, 0FFFFFFF4h
0x18007fe1d  test    ecx, 0FFFFFFFDh
0x18007fe23  mov     rcx, rdi
0x18007fe26  jz      short loc_18007FE36
0x18007fe28  mov     edx, r14d
0x18007fe2b  call    sqlite3GetTempRange
0x18007fe30  mov     esi, eax
0x18007fe32  xor     edx, edx
0x18007fe34  jmp     short loc_18007FE6B
0x18007fe36  call    sqlite3GetTempReg
0x18007fe3b  mov     esi, eax
0x18007fe3d  mov     r14d, edx
0x18007fe40  jmp     short loc_18007FE6B
0x18007fe42  cmp     [rbp+0Ch], edx
0x18007fe45  jz      short loc_18007FE65
0x18007fe47  mov     r9d, [rsi+0Ch]
0x18007fe4b  xor     r8d, r8d
0x18007fe4e  mov     [rsp+0A8h+var_88], edx
0x18007fe52  mov     rcx, rbx
0x18007fe55  lea     edx, [r8+4Bh]
0x18007fe59  call    sqlite3VdbeAddOp3
0x18007fe5e  mov     r10d, [rsp+0A8h+var_64]
0x18007fe63  xor     edx, edx
0x18007fe65  mov     esi, [rsi+0Ch]
0x18007fe68  mov     r13d, edx
0x18007fe6b  test    byte ptr [r12+24h], 1
0x18007fe71  jz      loc_18007FF45
0x18007fe77  inc     dword ptr [rdi+38h]
0x18007fe7a  mov     ebp, edx
0x18007fe7c  mov     eax, [rdi+38h]
0x18007fe7f  mov     dword ptr [rsp+0A8h+arg_8], eax
0x18007fe86  mov     eax, [rdi+34h]
0x18007fe89  mov     [rsp+0A8h+arg_0], eax
0x18007fe90  inc     eax
0x18007fe92  mov     [rdi+34h], eax
0x18007fe95  cmp     [r12+14h], edx
0x18007fe9a  jz      short loc_18007FEB4
0x18007fe9c  xor     r9d, r9d
0x18007fe9f  mov     [rsp+0A8h+var_88], edx
0x18007fea3  xor     r8d, r8d
0x18007fea6  mov     rcx, rbx
0x18007fea9  lea     edx, [r9+0Fh]
0x18007fead  call    sqlite3VdbeAddOp3
0x18007feb2  mov     ebp, eax
0x18007feb4  mov     r9d, dword ptr [rsp+0A8h+arg_8]
0x18007febc  lea     ecx, [r15+1]
0x18007fec0  mov     r8d, [rsp+0A8h+arg_0]
0x18007fec8  add     ecx, r14d
0x18007fecb  mov     [rsp+0A8h+var_88], ecx
0x18007fecf  mov     edx, 79h ; 'y'
0x18007fed4  mov     rcx, rbx
0x18007fed7  call    sqlite3VdbeAddOp3
0x18007fedc  xor     r9d, r9d
0x18007fedf  test    ebp, ebp
0x18007fee1  jz      short loc_18007FEF6
0x18007fee3  mov     edx, ebp
0x18007fee5  mov     rcx, rbx
0x18007fee8  call    sqlite3VdbeGetOp
0x18007feed  mov     ecx, [rbx+90h]
0x18007fef3  mov     [rax+8], ecx
0x18007fef6  mov     r8d, [rsp+0A8h+var_64]
0x18007fefb  mov     edx, 22h ; '"'
0x18007ff00  mov     [rsp+0A8h+var_88], r9d
0x18007ff05  mov     rcx, rbx
0x18007ff08  mov     r9d, [rsp+0A8h+var_60]
0x18007ff0d  call    sqlite3VdbeAddOp3
0x18007ff12  mov     r9d, dword ptr [rsp+0A8h+arg_8]
0x18007ff1a  inc     eax
0x18007ff1c  mov     r8d, [rsp+0A8h+var_64]
0x18007ff21  mov     edx, 85h
0x18007ff26  mov     [rsp+0A8h+var_58], eax
0x18007ff2a  mov     rcx, rbx
0x18007ff2d  mov     eax, [rsp+0A8h+arg_0]
0x18007ff34  mov     [rsp+0A8h+var_88], eax
0x18007ff38  call    sqlite3VdbeAddOp3
0x18007ff3d  xor     r10d, r10d
0x18007ff40  mov     ebp, r10d
0x18007ff43  jmp     short loc_18007FFB0
0x18007ff45  mov     r9d, [rsp+0A8h+var_60]
0x18007ff4a  mov     r8d, r10d
0x18007ff4d  mov     [rsp+0A8h+var_88], edx
0x18007ff51  mov     rcx, rbx
0x18007ff54  mov     edx, 23h ; '#'
0x18007ff59  call    sqlite3VdbeAddOp3
0x18007ff5e  mov     r8d, [rsp+0A8h+var_5C]
0x18007ff63  inc     eax
0x18007ff65  mov     edx, [rbp+0Ch]
0x18007ff68  mov     rcx, rbx
0x18007ff6b  mov     [rsp+0A8h+var_58], eax
0x18007ff6f  call    codeOffset
0x18007ff74  mov     r8, [rsp+0A8h+arg_8]
0x18007ff7c  xor     r10d, r10d
0x18007ff7f  mov     eax, [rsp+0A8h+var_64]
0x18007ff83  mov     ebp, 1
0x18007ff88  mov     [rsp+0A8h+arg_0], eax
0x18007ff8f  cmp     [r8+0Ch], r10d
0x18007ff93  jle     short loc_18007FFB0
0x18007ff95  mov     r8d, [r8+8]
0x18007ff99  lea     edx, [rbp+55h]
0x18007ff9c  or      r9d, 0FFFFFFFFh
0x18007ffa0  mov     [rsp+0A8h+var_88], r10d
0x18007ffa5  mov     rcx, rbx
0x18007ffa8  call    sqlite3VdbeAddOp3
0x18007ffad  xor     r10d, r10d
0x18007ffb0  mov     r9, [rsp+0A8h+var_50]
0x18007ffb5  lea     r8d, [r15+rbp]
0x18007ffb9  mov     dword ptr [rsp+0A8h+arg_8], r8d
0x18007ffc1  lea     ebp, [r8-1]
0x18007ffc5  mov     edx, r10d
0x18007ffc8  test    r14d, r14d
0x18007ffcb  jle     short loc_18007FFE8
0x18007ffcd  mov     eax, edx
0x18007ffcf  lea     ecx, [rbp+1]
0x18007ffd2  shl     rax, 5
0x18007ffd6  cmp     [rax+r9+18h], r10w
0x18007ffdc  cmovnz  ecx, ebp
0x18007ffdf  inc     edx
0x18007ffe1  mov     ebp, ecx
0x18007ffe3  cmp     edx, r14d
0x18007ffe6  jl      short loc_18007FFCD
0x18007ffe8  lea     r15d, [r14-1]
0x18007ffec  test    r15d, r15d
0x18007ffef  js      short loc_18008004F
0x18007fff1  mov     r12d, [rsp+0A8h+arg_0]
0x18007fff9  mov     eax, r15d
0x18007fffc  shl     rax, 5
0x180080000  movzx   ecx, word ptr [rax+r9+18h]
0x180080006  test    cx, cx
0x180080009  jz      short loc_180080011
0x18008000b  lea     r9d, [rcx-1]
0x18008000f  jmp     short loc_180080016
0x180080011  mov     r9d, ebp
0x180080014  dec     ebp
0x180080016  lea     eax, [r15+rsi]
0x18008001a  mov     r8d, r12d
0x18008001d  mov     edx, 5Eh ; '^'
0x180080022  mov     [rsp+0A8h+var_88], eax
0x180080026  mov     rcx, rbx
0x180080029  call    sqlite3VdbeAddOp3
0x18008002e  sub     r15d, 1
0x180080032  mov     r9, [rsp+0A8h+var_50]
0x180080037  mov     r10d, 0
0x18008003d  jns     short loc_18007FFF9
0x18008003f  mov     r12, [rsp+0A8h+arg_10]
0x180080047  mov     r8d, dword ptr [rsp+0A8h+arg_8]
0x18008004f  mov     edx, [rsp+0A8h+arg_18]
0x180080056  mov     ecx, edx
0x180080058  sub     ecx, 0Ah
0x18008005b  jz      loc_1800801C2
0x180080061  sub     ecx, 1
0x180080064  jz      loc_18008016F
0x18008006a  sub     ecx, 1
0x18008006d  jz      loc_18008010D
0x180080073  sub     ecx, 2
0x180080076  jz      loc_18008010D
0x18008007c  mov     rax, [rsp+0A8h+arg_20]
0x180080084  cmp     ecx, 1
0x180080087  jz      short loc_1800800B9
0x180080089  mov     [rsp+0A8h+var_88], r10d
0x18008008e  mov     rcx, rbx
0x180080091  cmp     dl, 9
0x180080094  jnz     short loc_1800800AC
0x180080096  mov     r8d, [rax+0Ch]
0x18008009a  mov     r9d, r14d
0x18008009d  mov     edx, 54h ; 'T'
0x1800800a2  call    sqlite3VdbeAddOp3
0x1800800a7  jmp     loc_1800801BB
0x1800800ac  mov     r8d, [rax+4]
0x1800800b0  xor     r9d, r9d
0x1800800b3  lea     edx, [r9+0Ch]
0x1800800b7  jmp     short loc_1800800A2
0x1800800b9  mov     r15d, [rax+8]
0x1800800bd  mov     rcx, rdi
0x1800800c0  call    sqlite3GetTempReg
0x1800800c5  mov     ecx, r15d
0x1800800c8  mov     [rsp+0A8h+var_88], eax
0x1800800cc  shr     ecx, 1Fh
0x1800800cf  mov     r9d, r14d
0x1800800d2  sub     r9d, ecx
0x1800800d5  mov     edx, 61h ; 'a'
0x1800800da  mov     ebp, eax
0x1800800dc  lea     r8d, [rcx+rsi]
0x1800800e0  mov     rcx, rbx
0x1800800e3  call    sqlite3VdbeAddOp3
0x1800800e8  mov     r8d, [rsp+0A8h+var_68]
0x1800800ed  mov     r9d, ebp
0x1800800f0  mov     rcx, rbx
0x1800800f3  test    r15d, r15d
0x1800800f6  jns     short loc_180080103
0x1800800f8  mov     [rsp+0A8h+var_88], esi
0x1800800fc  mov     edx, 80h
0x180080101  jmp     short loc_1800800A2
0x180080103  mov     dword ptr [rsp+0A8h+var_80], r15d
0x180080108  jmp     loc_1800801AD
0x18008010d  mov     r9d, r8d
0x180080110  mov     [rsp+0A8h+var_88], esi
0x180080114  mov     r8d, [rsp+0A8h+arg_0]
0x18008011c  mov     edx, 5Eh ; '^'
0x180080121  mov     rcx, rbx
0x180080124  call    sqlite3VdbeAddOp3
0x180080129  mov     r8d, [rsp+0A8h+var_68]
0x18008012e  xor     r9d, r9d
0x180080131  mov     [rsp+0A8h+var_88], r9d
0x180080136  mov     edx, 7Fh
0x18008013b  mov     r9d, r13d
0x18008013e  mov     rcx, rbx
0x180080141  call    sqlite3VdbeAddOp3
0x180080146  mov     r8d, [rsp+0A8h+var_68]
0x18008014b  mov     r9d, esi
0x18008014e  mov     edx, 80h
0x180080153  mov     [rsp+0A8h+var_88], r13d
0x180080158  mov     rcx, rbx
0x18008015b  call    sqlite3VdbeAddOp3
0x180080160  mov     edx, 8
0x180080165  mov     rcx, rbx
0x180080168  call    sqlite3VdbeChangeP5
0x18008016d  jmp     short loc_1800801BB
0x18008016f  mov     rax, [rsp+0A8h+arg_20]
0x180080177  mov     r9d, r14d
  ... truncated ...
```
