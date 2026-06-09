# resolveCompoundOrderBy

- ea: `0x1800597b4`
- end: `0x180059a50`
- name: `resolveCompoundOrderBy`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180002a30`

## callees

- `0x1800024dc`
- `0x1800055cc`
- `0x18000c960`
- `0x1800136e4`
- `0x1800148c4`
- `0x18003e1e0`
- `0x1800597b4`
- `0x180060ce8`
- `0x18006244c`
- `0x18007f16c`

## pseudocode

```c
__int64 __fastcall resolveCompoundOrderBy(_BYTE *a1, _QWORD *a2)
{
  _DWORD *v2; // rsi
  _QWORD *v3; // rbx
  int v6; // ecx
  int i; // edx
  __int64 v8; // rax
  int *v9; // rbp
  _DWORD *v10; // r14
  int j; // r13d
  bool v12; // zf
  __int64 v13; // rax
  __int64 v14; // r12
  __int64 v15; // rcx
  int v16; // ebp
  __int64 v17; // r13
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  int k; // eax
  __int64 v23; // [rsp+30h] [rbp-48h]
  int *v24; // [rsp+38h] [rbp-40h]
  int v25; // [rsp+88h] [rbp+10h]
  int v26; // [rsp+90h] [rbp+18h] BYREF
  int v27; // [rsp+98h] [rbp+20h]

  v2 = (_DWORD *)a2[9];
  v3 = a2;
  if ( v2 )
  {
    v23 = *(_QWORD *)a1;
    if ( *v2 > *(_DWORD *)(*(_QWORD *)a1 + 144LL) )
    {
      sqlite3ErrorMsg(a1, "too many terms in ORDER BY clause");
      return 1;
    }
    v6 = 0;
    for ( i = 1; v6 < *v2; v2[8 * v8 + 7] &= ~4u )
      v8 = v6++;
    v3[11] = 0;
    while ( v3[10] )
    {
      *(_QWORD *)(v3[10] + 88LL) = v3;
      v3 = (_QWORD *)v3[10];
    }
    while ( v3 && i )
    {
      v9 = (int *)v3[4];
      v10 = v2 + 2;
      i = 0;
      v24 = v9;
      v27 = 0;
      for ( j = 0; ; ++j )
      {
        v25 = j;
        if ( j >= *v2 )
          break;
        v12 = (v10[5] & 4) == 0;
        v26 = -1;
        if ( v12 )
        {
          v13 = sqlite3ExprSkipCollateAndLikely(*(_QWORD *)v10);
          v14 = v13;
          if ( v13 )
          {
            if ( (unsigned int)sqlite3ExprIsInteger(v13, &v26, 0) )
            {
              v16 = v26;
              if ( v26 <= 0 || v26 > *v24 )
              {
                resolveOutOfRangeError((_DWORD)a1, (unsigned int)"ORDER", j + 1, *v24, v14);
                return 1;
              }
            }
            else
            {
              v16 = resolveAsName(v15, v9, v14);
              if ( !v16 )
              {
                v17 = sqlite3ExprDup(v23, v14, 0);
                v18 = v23;
                if ( !*(_BYTE *)(v23 + 103) )
                {
                  v19 = resolveOrderByTermToExprList(a1, v3, v17);
                  v16 = v19;
                  if ( a1[308] >= 2u && v19 > 0 )
                    resolveOrderByTermToExprList(a1, v3, v14);
                  v18 = v23;
                }
                if ( v17 )
                  sqlite3ExprDeleteNN(v18, v17);
                j = v25;
              }
            }
            if ( v16 <= 0 )
            {
              i = 1;
              v27 = 1;
            }
            else
            {
              if ( a1[308] < 2u )
              {
                v20 = sqlite3Expr(v23, 156, 0);
                if ( !v20 )
                  return 1;
                *(_DWORD *)(v20 + 4) |= 0x800u;
                *(_DWORD *)(v20 + 8) = v16;
                v21 = *(_QWORD *)v10;
                if ( *(_QWORD *)v10 == v14 )
                {
                  *(_QWORD *)v10 = v20;
                }
                else
                {
                  while ( **(_BYTE **)(v21 + 16) == 114 )
                    v21 = *(_QWORD *)(v21 + 16);
                  *(_QWORD *)(v21 + 16) = v20;
                }
                sqlite3ExprDeleteNN(v23, v14);
                *((_WORD *)v10 + 12) = v16;
              }
              v10[5] |= 4u;
              i = v27;
            }
            v9 = v24;
          }
        }
        v10 += 8;
      }
      v3 = (_QWORD *)v3[11];
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
0x1800597b4  mov     [rsp+arg_0], rbx
0x1800597b9  push    rbp
0x1800597ba  push    rsi
0x1800597bb  push    rdi
0x1800597bc  push    r12
0x1800597be  push    r13
0x1800597c0  push    r14
0x1800597c2  push    r15
0x1800597c4  sub     rsp, 40h
0x1800597c8  mov     rsi, [rdx+48h]
0x1800597cc  mov     rbx, rdx
0x1800597cf  mov     r15, rcx
0x1800597d2  test    rsi, rsi
0x1800597d5  jz      loc_180059A36
0x1800597db  mov     rcx, [rcx]
0x1800597de  mov     eax, [rsi]
0x1800597e0  mov     [rsp+78h+var_48], rcx
0x1800597e5  cmp     eax, [rcx+90h]
0x1800597eb  jle     short loc_180059806
0x1800597ed  lea     rdx, aTooManyTermsIn_0; "too many terms in ORDER BY clause"
0x1800597f4  mov     rcx, r15
0x1800597f7  call    sqlite3ErrorMsg
0x1800597fc  mov     eax, 1
0x180059801  jmp     loc_180059A38
0x180059806  xor     ecx, ecx
0x180059808  mov     edi, 1
0x18005980d  mov     edx, edi
0x18005980f  test    eax, eax
0x180059811  jle     short loc_180059825
0x180059813  movsxd  rax, ecx
0x180059816  add     ecx, edi
0x180059818  shl     rax, 5
0x18005981c  and     dword ptr [rax+rsi+1Ch], 0FFFFFFFBh
0x180059821  cmp     ecx, [rsi]
0x180059823  jl      short loc_180059813
0x180059825  mov     qword ptr [rbx+58h], 0
0x18005982d  jmp     short loc_18005983B
0x18005982f  mov     rax, [rbx+50h]
0x180059833  mov     [rax+58h], rbx
0x180059837  mov     rbx, [rbx+50h]
0x18005983b  cmp     qword ptr [rbx+50h], 0
0x180059840  jnz     short loc_18005982F
0x180059842  test    rbx, rbx
0x180059845  jz      loc_180059A06
0x18005984b  test    edx, edx
0x18005984d  jz      loc_180059A06
0x180059853  mov     rbp, [rbx+20h]
0x180059857  lea     r14, [rsi+8]
0x18005985b  xor     edx, edx
0x18005985d  mov     [rsp+78h+var_40], rbp
0x180059862  mov     [rsp+78h+arg_18], edx
0x180059869  xor     r13d, r13d
0x18005986c  mov     [rsp+78h+arg_8], r13d
0x180059874  cmp     r13d, [rsi]
0x180059877  jge     loc_1800599FD
0x18005987d  test    byte ptr [r14+14h], 4
0x180059882  mov     [rsp+78h+arg_10], 0FFFFFFFFh
0x18005988d  jnz     loc_1800599F1
0x180059893  mov     rcx, [r14]
0x180059896  call    sqlite3ExprSkipCollateAndLikely
0x18005989b  mov     r12, rax
0x18005989e  test    rax, rax
0x1800598a1  jz      loc_1800599F1
0x1800598a7  xor     r8d, r8d
0x1800598aa  lea     rdx, [rsp+78h+arg_10]
0x1800598b2  mov     rcx, rax
0x1800598b5  call    sqlite3ExprIsInteger
0x1800598ba  test    eax, eax
0x1800598bc  jz      short loc_1800598F9
0x1800598be  mov     ebp, [rsp+78h+arg_10]
0x1800598c5  mov     r9, [rsp+78h+var_40]
0x1800598ca  test    ebp, ebp
0x1800598cc  jle     short loc_1800598D7
0x1800598ce  cmp     ebp, [r9]
0x1800598d1  jle     loc_180059971
0x1800598d7  mov     r9d, [r9]
0x1800598da  lea     r8d, [r13+1]
0x1800598de  lea     rdx, aOrder; "ORDER"
0x1800598e5  mov     [rsp+78h+var_58], r12
0x1800598ea  mov     rcx, r15
0x1800598ed  call    resolveOutOfRangeError
0x1800598f2  mov     eax, edi
0x1800598f4  jmp     loc_180059A38
0x1800598f9  mov     r8, r12
0x1800598fc  mov     rdx, rbp
0x1800598ff  call    resolveAsName
0x180059904  mov     ebp, eax
0x180059906  test    eax, eax
0x180059908  jnz     short loc_180059971
0x18005990a  mov     rcx, [rsp+78h+var_48]
0x18005990f  xor     r8d, r8d
0x180059912  mov     rdx, r12
0x180059915  call    sqlite3ExprDup
0x18005991a  mov     r13, rax
0x18005991d  mov     rax, [rsp+78h+var_48]
0x180059922  cmp     [rax+67h], bpl
0x180059926  jnz     short loc_180059959
0x180059928  mov     r8, r13
0x18005992b  mov     rdx, rbx
0x18005992e  mov     rcx, r15
0x180059931  call    resolveOrderByTermToExprList
0x180059936  cmp     byte ptr [r15+134h], 2
0x18005993e  mov     ebp, eax
0x180059940  jb      short loc_180059954
0x180059942  test    eax, eax
0x180059944  jle     short loc_180059954
0x180059946  mov     r8, r12
0x180059949  mov     rdx, rbx
0x18005994c  mov     rcx, r15
0x18005994f  call    resolveOrderByTermToExprList
0x180059954  mov     rax, [rsp+78h+var_48]
0x180059959  test    r13, r13
0x18005995c  jz      short loc_180059969
0x18005995e  mov     rdx, r13
0x180059961  mov     rcx, rax
0x180059964  call    sqlite3ExprDeleteNN
0x180059969  mov     r13d, [rsp+78h+arg_8]
0x180059971  test    ebp, ebp
0x180059973  jle     short loc_1800599E3
0x180059975  cmp     byte ptr [r15+134h], 2
0x18005997d  jnb     short loc_1800599D5
0x18005997f  mov     rcx, [rsp+78h+var_48]
0x180059984  xor     r8d, r8d
0x180059987  mov     edx, 9Ch
0x18005998c  call    sqlite3Expr
0x180059991  mov     rdx, rax
0x180059994  test    rax, rax
0x180059997  jz      loc_1800598F2
0x18005999d  bts     dword ptr [rax+4], 0Bh
0x1800599a2  mov     [rax+8], ebp
0x1800599a5  mov     rcx, [r14]
0x1800599a8  cmp     rcx, r12
0x1800599ab  jnz     short loc_1800599B6
0x1800599ad  mov     [r14], rax
0x1800599b0  jmp     short loc_1800599C3
0x1800599b2  mov     rcx, [rcx+10h]
0x1800599b6  mov     rax, [rcx+10h]
0x1800599ba  cmp     byte ptr [rax], 72h ; 'r'
0x1800599bd  jz      short loc_1800599B2
0x1800599bf  mov     [rcx+10h], rdx
0x1800599c3  mov     rcx, [rsp+78h+var_48]
0x1800599c8  mov     rdx, r12
0x1800599cb  call    sqlite3ExprDeleteNN
0x1800599d0  mov     [r14+18h], bp
0x1800599d5  or      dword ptr [r14+14h], 4
0x1800599da  mov     edx, [rsp+78h+arg_18]
0x1800599e1  jmp     short loc_1800599EC
0x1800599e3  mov     edx, edi
0x1800599e5  mov     [rsp+78h+arg_18], edx
0x1800599ec  mov     rbp, [rsp+78h+var_40]
0x1800599f1  add     r13d, edi
0x1800599f4  add     r14, 20h ; ' '
0x1800599f8  jmp     loc_18005986C
0x1800599fd  mov     rbx, [rbx+58h]
0x180059a01  jmp     loc_180059842
0x180059a06  xor     eax, eax
0x180059a08  cmp     eax, [rsi]
0x180059a0a  jge     short loc_180059A36
0x180059a0c  lea     r8d, [rax+1]
0x180059a10  cdqe
0x180059a12  shl     rax, 5
0x180059a16  test    byte ptr [rax+rsi+1Ch], 4
0x180059a1b  jz      short loc_180059A22
0x180059a1d  mov     eax, r8d
0x180059a20  jmp     short loc_180059A08
0x180059a22  lea     rdx, aROrderByTermDo; "%r ORDER BY term does not match any col"...
0x180059a29  mov     rcx, r15
0x180059a2c  call    sqlite3ErrorMsg
0x180059a31  jmp     loc_1800598F2
0x180059a36  xor     eax, eax
0x180059a38  mov     rbx, [rsp+78h+arg_0]
0x180059a40  add     rsp, 40h
0x180059a44  pop     r15
0x180059a46  pop     r14
0x180059a48  pop     r13
0x180059a4a  pop     r12
0x180059a4c  pop     rdi
0x180059a4d  pop     rsi
0x180059a4e  pop     rbp
0x180059a4f  retn
```
