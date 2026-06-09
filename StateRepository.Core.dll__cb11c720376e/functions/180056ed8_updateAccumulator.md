# updateAccumulator

- ea: `0x180056ed8`
- end: `0x180057337`
- name: `updateAccumulator`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180037194`

## callees

- `0x180005c54`
- `0x1800119e0`
- `0x180011d80`
- `0x180013270`
- `0x18001bdf0`
- `0x18001c1c4`
- `0x18001c220`
- `0x1800352fc`
- `0x1800370c0`
- `0x18003abcc`
- `0x18003e5c0`
- `0x180056ed8`
- `0x1800573d8`
- `0x18005d030`
- `0x180065204`

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
  int v10; // ebx
  unsigned int *v11; // rbx
  __int64 v12; // r12
  int v13; // edi
  int *v14; // rbx
  int v15; // ecx
  int v16; // edx
  int v17; // eax
  unsigned int TempRange; // r12d
  int v19; // eax
  unsigned int v20; // ecx
  unsigned int v21; // edx
  int v22; // ebx
  unsigned int v23; // r15d
  unsigned int v24; // esi
  unsigned int v25; // eax
  __int64 v26; // r9
  unsigned int v27; // eax
  int v28; // ebx
  int v29; // eax
  _QWORD *v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int v34; // edi
  __int64 v35; // r14
  int i; // ebx
  unsigned int v37; // [rsp+40h] [rbp-68h]
  unsigned int v38; // [rsp+44h] [rbp-64h]
  int v39; // [rsp+48h] [rbp-60h]
  unsigned int v40; // [rsp+4Ch] [rbp-5Ch]
  int v41; // [rsp+4Ch] [rbp-5Ch]
  int v42; // [rsp+50h] [rbp-58h]
  unsigned int *v43; // [rsp+58h] [rbp-50h]
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+0h] BYREF
  int v46; // [rsp+B8h] [rbp+10h]

  result = (__int64)&retaddr;
  v46 = a2;
  v5 = a3;
  v6 = (_DWORD *)a1;
  if ( !*(_DWORD *)(a1 + 52) )
  {
    v7 = *(_QWORD *)(a1 + 16);
    v8 = 0;
    v9 = *(_QWORD **)(a3 + 40);
    v10 = 0;
    *(_BYTE *)a3 = 1;
    while ( 1 )
    {
      v42 = v10;
      if ( v10 >= *(_DWORD *)(v5 + 48) )
        break;
      v38 = 0;
      v11 = *(unsigned int **)(*v9 + 32LL);
      v43 = v11;
      if ( (*(_DWORD *)(*v9 + 4LL) & 0x1000000) != 0 )
      {
        v12 = *(_QWORD *)(*(_QWORD *)(*v9 + 64LL) + 72LL);
        if ( *(_DWORD *)(v5 + 36) && (*(_BYTE *)(v9[1] + 4LL) & 0x20) != 0 && a2 )
        {
          if ( !v8 )
            v8 = ++v6[15];
          sqlite3VdbeAddOp3(v7, 80, a2, v8, 0);
        }
        v38 = --v6[18];
        sqlite3ExprIfFalse(v6, v12, v38, 16);
      }
      if ( *((int *)v9 + 6) < 0 )
      {
        v40 = 0;
        if ( v11 )
        {
          v13 = *v11;
          TempRange = sqlite3GetTempRange(v6, *v11);
          sqlite3ExprCodeExprList((_DWORD)v6, (_DWORD)v11, TempRange, 0, 1);
          v20 = TempRange;
        }
        else
        {
          v20 = 0;
          v13 = 0;
          TempRange = 0;
        }
      }
      else
      {
        v13 = *v11;
        v14 = *(int **)(*(_QWORD *)(*v9 + 16LL) + 32LL);
        v15 = *v14 + 1;
        if ( *((_BYTE *)v9 + 29) )
          v15 = *v14;
        v16 = v15 + v13;
        if ( !*((_BYTE *)v9 + 28) )
          v16 = v15;
        v17 = v16 + v13;
        if ( !*((_BYTE *)v9 + 30) )
          v17 = v16;
        v40 = v17 + 1;
        v37 = sqlite3GetTempRange(v6, (unsigned int)(v17 + 1));
        TempRange = v37;
        sqlite3ExprCodeExprList((_DWORD)v6, (_DWORD)v14, v37, 0, 1);
        v19 = *v14;
        v39 = *v14;
        if ( !*((_BYTE *)v9 + 29) )
        {
          sqlite3VdbeAddOp3(v7, 126, *((_DWORD *)v9 + 6), v19 + v37, 0);
          v19 = ++v39;
        }
        v11 = v43;
        if ( *((_BYTE *)v9 + 28) )
        {
          v37 += v19;
          sqlite3ExprCodeExprList((_DWORD)v6, (_DWORD)v43, TempRange + v19, 0, 1);
          v19 = v13 + v39;
        }
        v20 = v37;
        if ( *((_BYTE *)v9 + 30) )
        {
          v21 = TempRange;
          if ( *((_BYTE *)v9 + 28) )
            v21 = v37;
          if ( v13 > 0 )
          {
            v22 = 0;
            v23 = v19 + TempRange;
            v24 = v21;
            do
              sqlite3VdbeAddOp3(v7, 181, v24 + v22++, v23++, 0);
            while ( v22 < v13 );
            v6 = (_DWORD *)a1;
            v5 = a3;
            v11 = v43;
            v20 = v37;
          }
        }
      }
      if ( *((int *)v9 + 4) >= 0 && v11 )
      {
        v25 = v38;
        if ( !v38 )
        {
          v25 = --v6[18];
          v38 = v25;
        }
        *((_DWORD *)v9 + 4) = codeDistinct((_DWORD)v6, a4, *((_DWORD *)v9 + 4), v25, (__int64)v11, v20);
      }
      if ( *((int *)v9 + 6) < 0 )
      {
        if ( (*(_BYTE *)(v9[1] + 4LL) & 0x20) != 0 )
        {
          v29 = 0;
          v41 = 0;
          v30 = v11 + 2;
          while ( v29 < v13 )
          {
            v31 = sqlite3ExprCollSeq(v6, *v30);
            v30 += 4;
            v29 = ++v41;
            if ( v31 )
              goto LABEL_46;
          }
          v31 = *(_QWORD *)(*(_QWORD *)v6 + 16LL);
LABEL_46:
          if ( !v8 && *(_DWORD *)(v5 + 36) )
            v8 = ++v6[15];
          sqlite3VdbeAddOp4(v7, 85, v8, 0, 0, v31, -2);
        }
        v28 = v42;
        sqlite3VdbeAddOp3(v7, 162, 0, TempRange, v42 + *(_DWORD *)(v5 + 12) + *(_DWORD *)(v5 + 32));
        sqlite3VdbeAppendP4(v7, v9[1], 4294967289LL);
        sqlite3VdbeChangeP5(v7, (unsigned __int8)v13, v32, v33);
        v27 = v13;
      }
      else
      {
        sqlite3VdbeAddOp3(v7, 97, TempRange, v40 - 1, TempRange + v40 - 1);
        sqlite3VdbeAddOp4Int(v7, 138, *((_DWORD *)v9 + 6), TempRange + v40 - 1, TempRange, v40 - 1);
        v27 = v40;
        v28 = v42;
      }
      sqlite3ReleaseTempRange(v6, TempRange, v27, v26);
      result = v38;
      if ( v38 )
        result = sqlite3VdbeResolveLabel(v7, v38);
      if ( v6[13] )
        return result;
      a2 = v46;
      v10 = v28 + 1;
      v9 += 4;
    }
    if ( v8 || (v34 = 0, *(_DWORD *)(v5 + 36)) && (v8 = a2) != 0 )
    {
      result = sqlite3VdbeAddOp3(v7, 16, v8, 0, 0);
      v34 = result;
    }
    v35 = *(_QWORD *)(v5 + 24);
    for ( i = 0; i < *(_DWORD *)(v5 + 36); ++i )
    {
      result = sqlite3ExprCode(v6, *(_QWORD *)(v35 + 8), (unsigned int)(i + *(_DWORD *)(v5 + 12)));
      if ( v6[13] )
        return result;
      v35 += 24;
    }
    *(_BYTE *)v5 = 0;
    if ( v34 )
      return sqlite3VdbeJumpHereOrPopInst(v7, v34);
  }
  return result;
}

```

## disassembly

```asm
0x180056ed8  mov     rax, rsp
0x180056edb  mov     [rax+20h], r9d
0x180056edf  mov     [rax+18h], r8
0x180056ee3  mov     [rax+10h], edx
0x180056ee6  mov     [rax+8], rcx
0x180056eea  push    rbx
0x180056eeb  push    rbp
0x180056eec  push    rsi
0x180056eed  push    rdi
0x180056eee  push    r12
0x180056ef0  push    r13
0x180056ef2  push    r14
0x180056ef4  push    r15
0x180056ef6  sub     rsp, 68h
0x180056efa  cmp     dword ptr [rcx+34h], 0
0x180056efe  mov     r15, r8
0x180056f01  mov     rsi, rcx
0x180056f04  jnz     loc_180057326
0x180056f0a  mov     rbp, [rcx+10h]
0x180056f0e  xor     r13d, r13d
0x180056f11  mov     r14, [r8+28h]
0x180056f15  xor     ebx, ebx
0x180056f17  mov     byte ptr [r8], 1
0x180056f1b  mov     [rsp+0A8h+var_58], ebx
0x180056f1f  cmp     ebx, [r15+30h]
0x180056f23  jge     loc_1800572B7
0x180056f29  mov     rax, [r14]
0x180056f2c  mov     [rsp+0A8h+var_64], 0
0x180056f34  test    dword ptr [rax+4], 1000000h
0x180056f3b  mov     rbx, [rax+20h]
0x180056f3f  mov     [rsp+0A8h+var_50], rbx
0x180056f44  jz      short loc_180056FA8
0x180056f46  cmp     dword ptr [r15+24h], 0
0x180056f4b  mov     rax, [rax+40h]
0x180056f4f  mov     r12, [rax+48h]
0x180056f53  jz      short loc_180056F8A
0x180056f55  mov     rax, [r14+8]
0x180056f59  test    byte ptr [rax+4], 20h
0x180056f5d  jz      short loc_180056F8A
0x180056f5f  test    edx, edx
0x180056f61  jz      short loc_180056F8A
0x180056f63  test    r13d, r13d
0x180056f66  jnz     short loc_180056F6F
0x180056f68  inc     dword ptr [rsi+3Ch]
0x180056f6b  mov     r13d, [rsi+3Ch]
0x180056f6f  mov     r8d, edx
0x180056f72  mov     dword ptr [rsp+0A8h+var_88], 0
0x180056f7a  mov     edx, 50h ; 'P'
0x180056f7f  mov     r9d, r13d
0x180056f82  mov     rcx, rbp
0x180056f85  call    sqlite3VdbeAddOp3
0x180056f8a  dec     dword ptr [rsi+48h]
0x180056f8d  mov     r9d, 10h
0x180056f93  mov     edi, [rsi+48h]
0x180056f96  mov     rdx, r12
0x180056f99  mov     r8d, edi
0x180056f9c  mov     [rsp+0A8h+var_64], edi
0x180056fa0  mov     rcx, rsi
0x180056fa3  call    sqlite3ExprIfFalse
0x180056fa8  cmp     dword ptr [r14+18h], 0
0x180056fad  jl      loc_1800570E7
0x180056fb3  cmp     byte ptr [r14+1Dh], 0
0x180056fb8  mov     edi, [rbx]
0x180056fba  mov     rax, [r14]
0x180056fbd  mov     rcx, [rax+10h]
0x180056fc1  mov     rbx, [rcx+20h]
0x180056fc5  mov     eax, [rbx]
0x180056fc7  lea     ecx, [rax+1]
0x180056fca  cmovnz  ecx, eax
0x180056fcd  cmp     byte ptr [r14+1Ch], 0
0x180056fd2  lea     edx, [rcx+rdi]
0x180056fd5  cmovz   edx, ecx
0x180056fd8  cmp     byte ptr [r14+1Eh], 0
0x180056fdd  mov     rcx, rsi
0x180056fe0  lea     eax, [rdx+rdi]
0x180056fe3  cmovz   eax, edx
0x180056fe6  inc     eax
0x180056fe8  mov     edx, eax
0x180056fea  mov     [rsp+0A8h+var_5C], eax
0x180056fee  call    sqlite3GetTempRange
0x180056ff3  xor     r9d, r9d
0x180056ff6  mov     [rsp+0A8h+var_68], eax
0x180056ffa  mov     r8d, eax
0x180056ffd  mov     byte ptr [rsp+0A8h+var_88], 1
0x180057002  mov     rcx, rsi
0x180057005  mov     rdx, rbx
0x180057008  mov     r12d, eax
0x18005700b  call    sqlite3ExprCodeExprList
0x180057010  cmp     byte ptr [r14+1Dh], 0
0x180057015  mov     eax, [rbx]
0x180057017  mov     [rsp+0A8h+var_60], eax
0x18005701b  jnz     short loc_180057044
0x18005701d  mov     r8d, [r14+18h]
0x180057021  lea     r9d, [rax+r12]
0x180057025  mov     edx, 7Eh ; '~'
0x18005702a  mov     dword ptr [rsp+0A8h+var_88], 0
0x180057032  mov     rcx, rbp
0x180057035  call    sqlite3VdbeAddOp3
0x18005703a  mov     eax, [rsp+0A8h+var_60]
0x18005703e  inc     eax
0x180057040  mov     [rsp+0A8h+var_60], eax
0x180057044  cmp     byte ptr [r14+1Ch], 0
0x180057049  mov     rbx, [rsp+0A8h+var_50]
0x18005704e  jz      short loc_180057073
0x180057050  add     eax, r12d
0x180057053  mov     byte ptr [rsp+0A8h+var_88], 1
0x180057058  mov     r8d, eax
0x18005705b  mov     [rsp+0A8h+var_68], eax
0x18005705f  xor     r9d, r9d
0x180057062  mov     rdx, rbx
0x180057065  mov     rcx, rsi
0x180057068  call    sqlite3ExprCodeExprList
0x18005706d  mov     eax, [rsp+0A8h+var_60]
0x180057071  add     eax, edi
0x180057073  cmp     byte ptr [r14+1Eh], 0
0x180057078  mov     ecx, [rsp+0A8h+var_68]
0x18005707c  jz      loc_180057125
0x180057082  cmp     byte ptr [r14+1Ch], 0
0x180057087  mov     edx, r12d
0x18005708a  mov     [rsp+0A8h+var_60], 0
0x180057092  cmovnz  edx, ecx
0x180057095  test    edi, edi
0x180057097  jle     loc_180057125
0x18005709d  mov     ebx, [rsp+0A8h+var_60]
0x1800570a1  lea     r15d, [rax+r12]
0x1800570a5  mov     esi, edx
0x1800570a7  lea     r8d, [rsi+rbx]
0x1800570ab  mov     dword ptr [rsp+0A8h+var_88], 0
0x1800570b3  mov     r9d, r15d
0x1800570b6  mov     edx, 0B5h
0x1800570bb  mov     rcx, rbp
0x1800570be  call    sqlite3VdbeAddOp3
0x1800570c3  inc     ebx
0x1800570c5  inc     r15d
0x1800570c8  cmp     ebx, edi
0x1800570ca  jl      short loc_1800570A7
0x1800570cc  mov     rsi, [rsp+0A8h+arg_0]
0x1800570d4  mov     r15, [rsp+0A8h+arg_10]
0x1800570dc  mov     rbx, [rsp+0A8h+var_50]
0x1800570e1  mov     ecx, [rsp+0A8h+var_68]
0x1800570e5  jmp     short loc_180057125
0x1800570e7  mov     [rsp+0A8h+var_5C], 0
0x1800570ef  test    rbx, rbx
0x1800570f2  jz      short loc_18005711E
0x1800570f4  mov     edi, [rbx]
0x1800570f6  mov     rcx, rsi
0x1800570f9  mov     edx, edi
0x1800570fb  call    sqlite3GetTempRange
0x180057100  xor     r9d, r9d
0x180057103  mov     byte ptr [rsp+0A8h+var_88], 1
0x180057108  mov     r8d, eax
0x18005710b  mov     rcx, rsi
0x18005710e  mov     rdx, rbx
0x180057111  mov     r12d, eax
0x180057114  call    sqlite3ExprCodeExprList
0x180057119  mov     ecx, r12d
0x18005711c  jmp     short loc_180057125
0x18005711e  xor     ecx, ecx
0x180057120  xor     edi, edi
0x180057122  xor     r12d, r12d
0x180057125  cmp     dword ptr [r14+10h], 0
0x18005712a  jl      short loc_180057166
0x18005712c  test    rbx, rbx
0x18005712f  jz      short loc_180057166
0x180057131  mov     eax, [rsp+0A8h+var_64]
0x180057135  test    eax, eax
0x180057137  jnz     short loc_180057143
0x180057139  dec     dword ptr [rsi+48h]
0x18005713c  mov     eax, [rsi+48h]
0x18005713f  mov     [rsp+0A8h+var_64], eax
0x180057143  mov     r8d, [r14+10h]
0x180057147  mov     r9d, eax
0x18005714a  mov     edx, [rsp+0A8h+arg_18]
0x180057151  mov     dword ptr [rsp+0A8h+var_80], ecx
0x180057155  mov     rcx, rsi
0x180057158  mov     [rsp+0A8h+var_88], rbx
0x18005715d  call    codeDistinct
0x180057162  mov     [r14+10h], eax
0x180057166  cmp     dword ptr [r14+18h], 0
0x18005716b  jl      short loc_1800571BB
0x18005716d  mov     eax, [rsp+0A8h+var_5C]
0x180057171  mov     r8d, r12d
0x180057174  mov     edx, 61h ; 'a'
0x180057179  mov     rcx, rbp
0x18005717c  lea     edi, [rax-1]
0x18005717f  lea     ebx, [rax-1]
0x180057182  add     edi, r12d
0x180057185  mov     r9d, ebx
0x180057188  mov     dword ptr [rsp+0A8h+var_88], edi
0x18005718c  call    sqlite3VdbeAddOp3
0x180057191  mov     r8d, [r14+18h]
0x180057195  mov     r9d, edi
0x180057198  mov     edx, 8Ah
0x18005719d  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1800571a1  mov     rcx, rbp
0x1800571a4  mov     dword ptr [rsp+0A8h+var_88], r12d
0x1800571a9  call    sqlite3VdbeAddOp4Int
0x1800571ae  mov     eax, [rsp+0A8h+var_5C]
0x1800571b2  mov     ebx, [rsp+0A8h+var_58]
0x1800571b6  jmp     loc_18005727B
0x1800571bb  mov     rax, [r14+8]
0x1800571bf  test    byte ptr [rax+4], 20h
0x1800571c3  jz      short loc_180057236
0x1800571c5  xor     eax, eax
0x1800571c7  mov     [rsp+0A8h+var_5C], eax
0x1800571cb  add     rbx, 8
0x1800571cf  cmp     eax, edi
0x1800571d1  jge     short loc_1800571F6
0x1800571d3  mov     rdx, [rbx]
0x1800571d6  mov     rcx, rsi
0x1800571d9  call    sqlite3ExprCollSeq
0x1800571de  mov     rcx, rax
0x1800571e1  add     rbx, 20h ; ' '
0x1800571e5  mov     eax, [rsp+0A8h+var_5C]
0x1800571e9  inc     eax
0x1800571eb  mov     [rsp+0A8h+var_5C], eax
0x1800571ef  test    rcx, rcx
0x1800571f2  jz      short loc_1800571CF
0x1800571f4  jmp     short loc_1800571FD
0x1800571f6  mov     rax, [rsi]
0x1800571f9  mov     rcx, [rax+10h]
0x1800571fd  test    r13d, r13d
0x180057200  jnz     short loc_18005720F
0x180057202  cmp     [r15+24h], r13d
0x180057206  jz      short loc_18005720F
0x180057208  inc     dword ptr [rsi+3Ch]
0x18005720b  mov     r13d, [rsi+3Ch]
0x18005720f  xor     r9d, r9d
0x180057212  mov     [rsp+0A8h+var_78], 0FFFFFFFEh
0x18005721a  mov     [rsp+0A8h+var_80], rcx
0x18005721f  mov     r8d, r13d
0x180057222  mov     rcx, rbp
0x180057225  mov     dword ptr [rsp+0A8h+var_88], 0
0x18005722d  lea     edx, [r9+55h]
0x180057231  call    sqlite3VdbeAddOp4
0x180057236  mov     eax, [r15+20h]
0x18005723a  mov     r9d, r12d
0x18005723d  add     eax, [r15+0Ch]
0x180057241  xor     r8d, r8d
0x180057244  mov     ebx, [rsp+0A8h+var_58]
0x180057248  mov     edx, 0A2h
0x18005724d  add     eax, ebx
0x18005724f  mov     rcx, rbp
0x180057252  mov     dword ptr [rsp+0A8h+var_88], eax
0x180057256  call    sqlite3VdbeAddOp3
0x18005725b  mov     rdx, [r14+8]
0x18005725f  mov     r8d, 0FFFFFFF9h
0x180057265  mov     rcx, rbp
0x180057268  call    sqlite3VdbeAppendP4
0x18005726d  movzx   edx, dil
0x180057271  mov     rcx, rbp
0x180057274  call    sqlite3VdbeChangeP5
0x180057279  mov     eax, edi
0x18005727b  mov     r8d, eax
0x18005727e  mov     edx, r12d
0x180057281  mov     rcx, rsi
0x180057284  call    sqlite3ReleaseTempRange
0x180057289  mov     eax, [rsp+0A8h+var_64]
0x18005728d  test    eax, eax
0x18005728f  jz      short loc_18005729B
0x180057291  mov     edx, eax
0x180057293  mov     rcx, rbp
0x180057296  call    sqlite3VdbeResolveLabel
0x18005729b  cmp     dword ptr [rsi+34h], 0
0x18005729f  jnz     loc_180057326
0x1800572a5  mov     edx, [rsp+0A8h+arg_8]
0x1800572ac  inc     ebx
0x1800572ae  add     r14, 20h ; ' '
0x1800572b2  jmp     loc_180056F1B
0x1800572b7  test    r13d, r13d
0x1800572ba  jnz     short loc_1800572CB
0x1800572bc  xor     edi, edi
0x1800572be  cmp     [r15+24h], edi
0x1800572c2  jz      short loc_1800572E7
0x1800572c4  mov     r13d, edx
0x1800572c7  test    edx, edx
0x1800572c9  jz      short loc_1800572E7
0x1800572cb  xor     r9d, r9d
0x1800572ce  mov     dword ptr [rsp+0A8h+var_88], 0
0x1800572d6  mov     r8d, r13d
0x1800572d9  mov     rcx, rbp
0x1800572dc  lea     edx, [r9+10h]
0x1800572e0  call    sqlite3VdbeAddOp3
0x1800572e5  mov     edi, eax
0x1800572e7  mov     r14, [r15+18h]
0x1800572eb  xor     ebx, ebx
0x1800572ed  cmp     ebx, [r15+24h]
0x1800572f1  jge     short loc_180057314
0x1800572f3  mov     r8d, [r15+0Ch]
0x1800572f7  mov     rcx, rsi
0x1800572fa  mov     rdx, [r14+8]
0x1800572fe  add     r8d, ebx
0x180057301  call    sqlite3ExprCode
0x180057306  cmp     dword ptr [rsi+34h], 0
0x18005730a  jnz     short loc_180057326
0x18005730c  inc     ebx
0x18005730e  add     r14, 18h
0x180057312  jmp     short loc_1800572ED
0x180057314  mov     byte ptr [r15], 0
0x180057318  test    edi, edi
  ... truncated ...
```
