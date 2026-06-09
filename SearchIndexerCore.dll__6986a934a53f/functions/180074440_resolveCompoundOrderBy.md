# resolveCompoundOrderBy

- ea: `0x180074440`
- end: `0x1800746e4`
- name: `resolveCompoundOrderBy`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180060fc0`

## callees

- `0x180011bcc`
- `0x180013fac`
- `0x18001b16c`
- `0x18001bb70`
- `0x18001f8f0`
- `0x18004f610`
- `0x180053e84`
- `0x18006f1fc`
- `0x180074440`
- `0x18008e550`

## pseudocode

```c
__int64 __fastcall resolveCompoundOrderBy(_BYTE *a1, __int64 a2)
{
  _DWORD *v2; // rsi
  __int64 v3; // rbx
  int v6; // ecx
  int i; // edx
  __int64 v8; // rax
  _DWORD *v9; // r14
  int j; // r13d
  bool v11; // zf
  __int64 v12; // rax
  __int64 v13; // r12
  __int64 v14; // rcx
  _QWORD *v15; // r9
  int *v16; // r10
  int v17; // ebp
  __int64 v18; // rax
  __int64 v19; // r13
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  int k; // eax
  __int64 v24; // [rsp+30h] [rbp-48h]
  int v25; // [rsp+88h] [rbp+10h]
  int v26; // [rsp+90h] [rbp+18h] BYREF
  int v27; // [rsp+98h] [rbp+20h]

  v2 = *(_DWORD **)(a2 + 72);
  v3 = a2;
  if ( v2 )
  {
    v24 = *(_QWORD *)a1;
    if ( *v2 > *(_DWORD *)(*(_QWORD *)a1 + 144LL) )
    {
      sqlite3ErrorMsg(a1, "too many terms in ORDER BY clause");
      return 1;
    }
    v6 = 0;
    for ( i = 1; v6 < *v2; v2[8 * v8 + 7] &= ~4u )
      v8 = v6++;
    *(_QWORD *)(v3 + 88) = 0;
    while ( *(_QWORD *)(v3 + 80) )
    {
      *(_QWORD *)(*(_QWORD *)(v3 + 80) + 88LL) = v3;
      v3 = *(_QWORD *)(v3 + 80);
    }
LABEL_9:
    if ( v3 && i )
    {
      v9 = v2 + 2;
      i = 0;
      v27 = 0;
      for ( j = 0; ; ++j )
      {
        v25 = j;
        if ( j >= *v2 )
        {
          v3 = *(_QWORD *)(v3 + 88);
          goto LABEL_9;
        }
        v11 = (v9[5] & 4) == 0;
        v26 = -1;
        if ( v11 )
        {
          v12 = sqlite3ExprSkipCollateAndLikely(*(_QWORD *)v9);
          v13 = v12;
          if ( v12 )
            break;
        }
LABEL_41:
        v9 += 8;
      }
      if ( (unsigned int)sqlite3ExprIsInteger(v12, &v26) )
      {
        v17 = v26;
        if ( v26 <= 0 || v26 > *v16 )
        {
          resolveOutOfRangeError((_DWORD)a1, (unsigned int)"ORDER", j + 1, *v16, v13);
          return 1;
        }
        goto LABEL_29;
      }
      v17 = resolveAsName(v14, v16, v13);
      if ( !v17 )
      {
        v18 = sqlite3ExprDup(v24, v13, 0);
        v15 = (_QWORD *)v24;
        v19 = v18;
        if ( !*(_BYTE *)(v24 + 103) )
        {
          v20 = resolveOrderByTermToExprList(a1, v3, v18);
          v17 = v20;
          if ( a1[308] >= 2u && v20 > 0 )
            resolveOrderByTermToExprList(a1, v3, v13);
          v15 = (_QWORD *)v24;
        }
        if ( !v19 )
        {
          j = v25;
LABEL_29:
          if ( v17 <= 0 )
          {
            i = 1;
            v27 = 1;
          }
          else
          {
            if ( a1[308] < 2u )
            {
              v21 = sqlite3Expr(v15, 155, 0);
              if ( !v21 )
                return 1;
              *(_DWORD *)(v21 + 4) |= 0x800u;
              *(_DWORD *)(v21 + 8) = v17;
              v22 = *(_QWORD *)v9;
              if ( *(_QWORD *)v9 == v13 )
              {
                *(_QWORD *)v9 = v21;
              }
              else
              {
                while ( **(_BYTE **)(v22 + 16) == 113 )
                  v22 = *(_QWORD *)(v22 + 16);
                *(_QWORD *)(v22 + 16) = v21;
              }
              sqlite3ExprDeleteNN((_QWORD *)v24, v13);
              *((_WORD *)v9 + 12) = v17;
            }
            v9[5] |= 4u;
            i = v27;
          }
          goto LABEL_41;
        }
        sqlite3ExprDeleteNN(v15, v19);
        j = v25;
      }
      v15 = (_QWORD *)v24;
      goto LABEL_29;
    }
    for ( k = 0; k < *v2; ++k )
    {
      if ( (v2[8 * k + 7] & 4) == 0 )
      {
        sqlite3ErrorMsg(a1, "%r ORDER BY term does not match any column in the result set", (unsigned int)(k + 1));
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180074440  mov     [rsp+arg_0], rbx
0x180074445  push    rbp
0x180074446  push    rsi
0x180074447  push    rdi
0x180074448  push    r12
0x18007444a  push    r13
0x18007444c  push    r14
0x18007444e  push    r15
0x180074450  sub     rsp, 40h
0x180074454  mov     rsi, [rdx+48h]
0x180074458  mov     rbx, rdx
0x18007445b  mov     r15, rcx
0x18007445e  test    rsi, rsi
0x180074461  jz      loc_1800746CA
0x180074467  mov     r9, [rcx]
0x18007446a  mov     eax, [rsi]
0x18007446c  mov     [rsp+78h+var_48], r9
0x180074471  cmp     eax, [r9+90h]
0x180074478  jle     short loc_180074490
0x18007447a  lea     rdx, aTooManyTermsIn_0; "too many terms in ORDER BY clause"
0x180074481  call    sqlite3ErrorMsg
0x180074486  mov     eax, 1
0x18007448b  jmp     loc_1800746CC
0x180074490  xor     ecx, ecx
0x180074492  mov     edi, 1
0x180074497  mov     edx, edi
0x180074499  test    eax, eax
0x18007449b  jle     short loc_1800744AF
0x18007449d  movsxd  rax, ecx
0x1800744a0  add     ecx, edi
0x1800744a2  shl     rax, 5
0x1800744a6  and     dword ptr [rax+rsi+1Ch], 0FFFFFFFBh
0x1800744ab  cmp     ecx, [rsi]
0x1800744ad  jl      short loc_18007449D
0x1800744af  mov     qword ptr [rbx+58h], 0
0x1800744b7  jmp     short loc_1800744C5
0x1800744b9  mov     rax, [rbx+50h]
0x1800744bd  mov     [rax+58h], rbx
0x1800744c1  mov     rbx, [rbx+50h]
0x1800744c5  cmp     qword ptr [rbx+50h], 0
0x1800744ca  jnz     short loc_1800744B9
0x1800744cc  test    rbx, rbx
0x1800744cf  jz      loc_18007469A
0x1800744d5  test    edx, edx
0x1800744d7  jz      loc_18007469A
0x1800744dd  mov     r10, [rbx+20h]
0x1800744e1  lea     r14, [rsi+8]
0x1800744e5  xor     edx, edx
0x1800744e7  mov     [rsp+78h+var_40], r10
0x1800744ec  mov     [rsp+78h+arg_18], edx
0x1800744f3  xor     r13d, r13d
0x1800744f6  mov     [rsp+78h+arg_8], r13d
0x1800744fe  cmp     r13d, [rsi]
0x180074501  jge     loc_180074691
0x180074507  test    byte ptr [r14+14h], 4
0x18007450c  mov     [rsp+78h+arg_10], 0FFFFFFFFh
0x180074517  jnz     loc_18007467B
0x18007451d  mov     rcx, [r14]
0x180074520  call    sqlite3ExprSkipCollateAndLikely
0x180074525  mov     r12, rax
0x180074528  test    rax, rax
0x18007452b  jz      loc_18007467B
0x180074531  lea     rdx, [rsp+78h+arg_10]
0x180074539  mov     rcx, rax
0x18007453c  call    sqlite3ExprIsInteger
0x180074541  test    eax, eax
0x180074543  jz      short loc_18007457B
0x180074545  mov     ebp, [rsp+78h+arg_10]
0x18007454c  test    ebp, ebp
0x18007454e  jle     short loc_180074559
0x180074550  cmp     ebp, [r10]
0x180074553  jle     loc_1800745F8
0x180074559  mov     r9d, [r10]
0x18007455c  lea     r8d, [r13+1]
0x180074560  lea     rdx, aOrder; "ORDER"
0x180074567  mov     [rsp+78h+var_58], r12
0x18007456c  mov     rcx, r15
0x18007456f  call    resolveOutOfRangeError
0x180074574  mov     eax, edi
0x180074576  jmp     loc_1800746CC
0x18007457b  mov     r8, r12
0x18007457e  mov     rdx, r10
0x180074581  call    resolveAsName
0x180074586  mov     ebp, eax
0x180074588  test    eax, eax
0x18007458a  jnz     short loc_1800745F3
0x18007458c  mov     rcx, [rsp+78h+var_48]
0x180074591  xor     r8d, r8d
0x180074594  mov     rdx, r12
0x180074597  call    sqlite3ExprDup
0x18007459c  mov     r9, [rsp+78h+var_48]
0x1800745a1  mov     r13, rax
0x1800745a4  cmp     [r9+67h], bpl
0x1800745a8  jnz     short loc_1800745DB
0x1800745aa  mov     r8, rax
0x1800745ad  mov     rdx, rbx
0x1800745b0  mov     rcx, r15
0x1800745b3  call    resolveOrderByTermToExprList
0x1800745b8  cmp     byte ptr [r15+134h], 2
0x1800745c0  mov     ebp, eax
0x1800745c2  jb      short loc_1800745D6
0x1800745c4  test    eax, eax
0x1800745c6  jle     short loc_1800745D6
0x1800745c8  mov     r8, r12
0x1800745cb  mov     rdx, rbx
0x1800745ce  mov     rcx, r15
0x1800745d1  call    resolveOrderByTermToExprList
0x1800745d6  mov     r9, [rsp+78h+var_48]
0x1800745db  test    r13, r13
0x1800745de  jz      short loc_180074637
0x1800745e0  mov     rdx, r13
0x1800745e3  mov     rcx, r9
0x1800745e6  call    sqlite3ExprDeleteNN
0x1800745eb  mov     r13d, [rsp+78h+arg_8]
0x1800745f3  mov     r9, [rsp+78h+var_48]
0x1800745f8  test    ebp, ebp
0x1800745fa  jle     short loc_180074672
0x1800745fc  cmp     byte ptr [r15+134h], 2
0x180074604  jnb     short loc_180074664
0x180074606  xor     r8d, r8d
0x180074609  mov     edx, 9Bh
0x18007460e  mov     rcx, r9
0x180074611  call    sqlite3Expr
0x180074616  mov     rdx, rax
0x180074619  test    rax, rax
0x18007461c  jz      loc_180074574
0x180074622  bts     dword ptr [rax+4], 0Bh
0x180074627  mov     [rax+8], ebp
0x18007462a  mov     rcx, [r14]
0x18007462d  cmp     rcx, r12
0x180074630  jnz     short loc_180074645
0x180074632  mov     [r14], rax
0x180074635  jmp     short loc_180074652
0x180074637  mov     r13d, [rsp+78h+arg_8]
0x18007463f  jmp     short loc_1800745F8
0x180074641  mov     rcx, [rcx+10h]
0x180074645  mov     rax, [rcx+10h]
0x180074649  cmp     byte ptr [rax], 71h ; 'q'
0x18007464c  jz      short loc_180074641
0x18007464e  mov     [rcx+10h], rdx
0x180074652  mov     rcx, [rsp+78h+var_48]
0x180074657  mov     rdx, r12
0x18007465a  call    sqlite3ExprDeleteNN
0x18007465f  mov     [r14+18h], bp
0x180074664  or      dword ptr [r14+14h], 4
0x180074669  mov     edx, [rsp+78h+arg_18]
0x180074670  jmp     short loc_18007467B
0x180074672  mov     edx, edi
0x180074674  mov     [rsp+78h+arg_18], edx
0x18007467b  mov     r9, [rsp+78h+var_48]
0x180074680  add     r13d, edi
0x180074683  mov     r10, [rsp+78h+var_40]
0x180074688  add     r14, 20h ; ' '
0x18007468c  jmp     loc_1800744F6
0x180074691  mov     rbx, [rbx+58h]
0x180074695  jmp     loc_1800744CC
0x18007469a  xor     eax, eax
0x18007469c  cmp     eax, [rsi]
0x18007469e  jge     short loc_1800746CA
0x1800746a0  lea     r8d, [rax+1]
0x1800746a4  cdqe
0x1800746a6  shl     rax, 5
0x1800746aa  test    byte ptr [rax+rsi+1Ch], 4
0x1800746af  jz      short loc_1800746B6
0x1800746b1  mov     eax, r8d
0x1800746b4  jmp     short loc_18007469C
0x1800746b6  lea     rdx, aROrderByTermDo; "%r ORDER BY term does not match any col"...
0x1800746bd  mov     rcx, r15
0x1800746c0  call    sqlite3ErrorMsg
0x1800746c5  jmp     loc_180074574
0x1800746ca  xor     eax, eax
0x1800746cc  mov     rbx, [rsp+78h+arg_0]
0x1800746d4  add     rsp, 40h
0x1800746d8  pop     r15
0x1800746da  pop     r14
0x1800746dc  pop     r13
0x1800746de  pop     r12
0x1800746e0  pop     rdi
0x1800746e1  pop     rsi
0x1800746e2  pop     rbp
0x1800746e3  retn
```
