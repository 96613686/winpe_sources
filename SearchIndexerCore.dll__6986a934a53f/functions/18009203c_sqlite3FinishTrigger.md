# sqlite3FinishTrigger

- ea: `0x18009203c`
- end: `0x180092315`
- name: `sqlite3FinishTrigger`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x18000213c`

## callees

- `0x180009760`
- `0x180009e04`
- `0x180009f6c`
- `0x180011bcc`
- `0x180015eb0`
- `0x1800168c0`
- `0x1800191d0`
- `0x18001eb90`
- `0x18001f418`
- `0x18003bc90`
- `0x180040e00`
- `0x180041d10`
- `0x18004a9b8`
- `0x18004b010`
- `0x18004bfc0`
- `0x18005166c`
- `0x180058730`
- `0x180061d60`
- `0x18006dc30`
- `0x180076a98`
- `0x180078968`
- `0x18009203c`
- `0x18009231c`

## string_xrefs

- `0x18009218b`: `trigger "%s" may not write to shadow table "%s"`
- `0x1800921e3`: `INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')`

## pseudocode

```c
__int64 __fastcall sqlite3FinishTrigger(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v5; // rbp
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rdi
  __int64 v10; // r13
  _BYTE *v11; // r12
  __int64 i; // rbx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rbx
  __int64 v16; // rax
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int128 v21; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v22[8]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v23[144]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v24; // [rsp+E0h] [rbp+8h]
  __int64 Vdbe; // [rsp+F8h] [rbp+20h]

  v3 = a1[46];
  v5 = *a1;
  v6 = a3;
  memset_0(v22, 0, 0x60u);
  v8 = *((_DWORD *)a1 + 12) == 0;
  v21 = 0;
  a1[46] = 0;
  if ( !v8 )
    goto LABEL_26;
  if ( !v3 )
    goto LABEL_26;
  v9 = *(_QWORD *)v3;
  v24 = *(_QWORD *)v3;
  v10 = (int)sqlite3SchemaToIndex(v5, *(_QWORD *)(v3 + 40));
  *(_QWORD *)(v3 + 56) = a2;
  while ( a2 )
  {
    *(_QWORD *)(a2 + 8) = v3;
    a2 = *(_QWORD *)(a2 + 80);
  }
  *(_QWORD *)&v21 = *(_QWORD *)v3;
  DWORD2(v21) = sqlite3Strlen30(v21);
  sqlite3FixInit((unsigned int)v22, (_DWORD)a1, v10, (unsigned int)"trigger", (__int64)&v21);
  if ( (unsigned int)sqlite3FixTriggerStep(v22, *(_QWORD *)(v3 + 56))
    || (unsigned int)sqlite3WalkExpr(v23, *(_QWORD *)(v3 + 24)) )
  {
    goto LABEL_26;
  }
  v11 = (_BYTE *)(v5 + 197);
  if ( *((_BYTE *)a1 + 308) >= 2u )
  {
    a1[46] = v3;
    v3 = 0;
    goto LABEL_21;
  }
  if ( *v11 )
  {
LABEL_22:
    v17 = (_QWORD *)v3;
    v3 = sqlite3HashInsert(*(_QWORD *)(32 * v10 + *(_QWORD *)(v5 + 32) + 24) + 56LL, v9, v3);
    if ( v3 )
    {
      sqlite3OomFault(v5);
    }
    else
    {
      v18 = v17[6];
      if ( v17[5] == v18 )
      {
        v19 = *(_QWORD *)(findElementWithHash(v18 + 8, v17[1], 0) + 16);
        v17[8] = *(_QWORD *)(v19 + 88);
        *(_QWORD *)(v19 + 88) = v17;
      }
    }
    goto LABEL_26;
  }
  if ( (unsigned int)sqlite3ReadOnlyShadowTables(v5) )
  {
    for ( i = *(_QWORD *)(v3 + 56); i; i = *(_QWORD *)(i + 80) )
    {
      v13 = *(_QWORD *)(i + 24);
      if ( v13 && (unsigned int)sqlite3ShadowTableName(v5, v13) )
      {
        sqlite3ErrorMsg(
          a1,
          "trigger \"%s\" may not write to shadow table \"%s\"",
          *(const char **)v3,
          *(const char **)(i + 24));
        goto LABEL_26;
      }
    }
    v6 = a3;
  }
  Vdbe = sqlite3GetVdbe(a1);
  if ( Vdbe )
  {
    sqlite3BeginWriteOperation(a1, 0, (unsigned int)v10, v14);
    v15 = sqlite3DbStrNDup(v5, *(_QWORD *)v6, *(unsigned int *)(v6 + 8));
    sqlite3NestedParse(
      a1,
      "INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')",
      *(_QWORD *)(*(_QWORD *)(v5 + 32) + 32 * v10),
      v24,
      *(_QWORD *)(v3 + 8),
      v15);
    sqlite3DbFree(v5, v15);
    sqlite3VdbeAddOp3(a1[2], 100, v10, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32) + 32 * v10 + 24) + 1);
    v9 = v24;
    v16 = sqlite3MPrintf(v5, "type='trigger' AND name='%q'", v24);
    sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v10, v16, 0);
LABEL_21:
    if ( !*v11 )
      goto LABEL_26;
    goto LABEL_22;
  }
LABEL_26:
  sqlite3DeleteTrigger(v5, v3);
  return sqlite3DeleteTriggerStep(v5, a2);
}

```

## disassembly

```asm
0x18009203c  mov     [rsp+arg_8], rbx
0x180092041  mov     [rsp+arg_10], r8
0x180092046  push    rbp
0x180092047  push    rsi
0x180092048  push    rdi
0x180092049  push    r12
0x18009204b  push    r13
0x18009204d  push    r14
0x18009204f  push    r15
0x180092051  sub     rsp, 0A0h
0x180092058  mov     rsi, [rcx+170h]
0x18009205f  mov     r15, rdx
0x180092062  mov     rbp, [rcx]
0x180092065  xor     edx, edx; Val
0x180092067  mov     rbx, r8
0x18009206a  mov     r14, rcx
0x18009206d  lea     rcx, [rsp+0D8h+var_98]; void *
0x180092072  lea     r8d, [rdx+60h]; Size
0x180092076  call    memset_0
0x18009207b  cmp     dword ptr [r14+30h], 0
0x180092080  xorps   xmm0, xmm0
0x180092083  movups  [rsp+0D8h+var_A8], xmm0
0x180092088  mov     qword ptr [r14+170h], 0
0x180092093  jnz     loc_1800922E4
0x180092099  test    rsi, rsi
0x18009209c  jz      loc_1800922E4
0x1800920a2  mov     rdi, [rsi]
0x1800920a5  mov     rcx, rbp
0x1800920a8  mov     rdx, [rsi+28h]
0x1800920ac  mov     [rsp+0D8h+arg_0], rdi
0x1800920b4  call    sqlite3SchemaToIndex
0x1800920b9  movsxd  r13, eax
0x1800920bc  mov     [rsi+38h], r15
0x1800920c0  jmp     short loc_1800920CA
0x1800920c2  mov     [r15+8], rsi
0x1800920c6  mov     r15, [r15+50h]
0x1800920ca  test    r15, r15
0x1800920cd  jnz     short loc_1800920C2
0x1800920cf  mov     rcx, [rsi]
0x1800920d2  mov     qword ptr [rsp+0D8h+var_A8], rcx
0x1800920d7  call    sqlite3Strlen30
0x1800920dc  mov     dword ptr [rsp+0D8h+var_A8+8], eax
0x1800920e0  lea     r9, aTrigger; "trigger"
0x1800920e7  lea     rax, [rsp+0D8h+var_A8]
0x1800920ec  mov     r8d, r13d
0x1800920ef  mov     rdx, r14
0x1800920f2  mov     [rsp+0D8h+var_B8], rax
0x1800920f7  lea     rcx, [rsp+0D8h+var_98]
0x1800920fc  call    sqlite3FixInit
0x180092101  mov     rdx, [rsi+38h]
0x180092105  lea     rcx, [rsp+0D8h+var_98]
0x18009210a  call    sqlite3FixTriggerStep
0x18009210f  test    eax, eax
0x180092111  jnz     loc_1800922E4
0x180092117  mov     rdx, [rsi+18h]
0x18009211b  lea     rcx, [rsp+0D8h+var_90]
0x180092120  call    sqlite3WalkExpr
0x180092125  test    eax, eax
0x180092127  jnz     loc_1800922E4
0x18009212d  cmp     byte ptr [r14+134h], 2
0x180092135  lea     r12, [rbp+0C5h]
0x18009213c  jb      short loc_18009214C
0x18009213e  mov     [r14+170h], rsi
0x180092145  xor     esi, esi
0x180092147  jmp     loc_18009227F
0x18009214c  cmp     byte ptr [r12], 0
0x180092151  jnz     loc_180092286
0x180092157  mov     rcx, rbp
0x18009215a  call    sqlite3ReadOnlyShadowTables
0x18009215f  test    eax, eax
0x180092161  jz      short loc_1800921AA
0x180092163  mov     rbx, [rsi+38h]
0x180092167  test    rbx, rbx
0x18009216a  jz      short loc_1800921A2
0x18009216c  mov     rdx, [rbx+18h]
0x180092170  test    rdx, rdx
0x180092173  jz      short loc_180092181
0x180092175  mov     rcx, rbp
0x180092178  call    sqlite3ShadowTableName
0x18009217d  test    eax, eax
0x18009217f  jnz     short loc_180092187
0x180092181  mov     rbx, [rbx+50h]
0x180092185  jmp     short loc_180092167
0x180092187  mov     r9, [rbx+18h]
0x18009218b  lea     rdx, aTriggerSMayNot; "trigger \"%s\" may not write to shadow "...
0x180092192  mov     r8, [rsi]
0x180092195  mov     rcx, r14
0x180092198  call    sqlite3ErrorMsg
0x18009219d  jmp     loc_1800922E4
0x1800921a2  mov     rbx, [rsp+0D8h+arg_10]
0x1800921aa  mov     rcx, r14
0x1800921ad  call    sqlite3GetVdbe
0x1800921b2  mov     [rsp+0D8h+arg_18], rax
0x1800921ba  test    rax, rax
0x1800921bd  jz      loc_1800922E4
0x1800921c3  mov     r8d, r13d
0x1800921c6  xor     edx, edx
0x1800921c8  mov     rcx, r14
0x1800921cb  call    sqlite3BeginWriteOperation
0x1800921d0  mov     r8d, [rbx+8]
0x1800921d4  mov     rcx, rbp
0x1800921d7  mov     rdx, [rbx]
0x1800921da  call    sqlite3DbStrNDup
0x1800921df  mov     rcx, [rsi+8]
0x1800921e3  lea     rdx, aInsertIntoQSql_0; "INSERT INTO %Q.sqlite_master VALUES('tr"...
0x1800921ea  mov     r8, [rbp+20h]
0x1800921ee  mov     rdi, r13
0x1800921f1  mov     r9, [rsp+0D8h+arg_0]
0x1800921f9  mov     rbx, rax
0x1800921fc  mov     [rsp+0D8h+var_B0], rax
0x180092201  mov     [rsp+0D8h+var_B8], rcx
0x180092206  mov     rcx, r14
0x180092209  shl     rdi, 5
0x18009220d  mov     r8, [r8+rdi]
0x180092211  call    sqlite3NestedParse
0x180092216  mov     rdx, rbx
0x180092219  mov     rcx, rbp
0x18009221c  call    sqlite3DbFree
0x180092221  mov     rax, [r14]
0x180092224  mov     r9d, 1
0x18009222a  mov     r8d, r13d
0x18009222d  mov     rcx, [rax+20h]
0x180092231  lea     edx, [r9+63h]
0x180092235  mov     rax, [rcx+rdi+18h]
0x18009223a  mov     ecx, [rax]
0x18009223c  add     ecx, r9d
0x18009223f  mov     dword ptr [rsp+0D8h+var_B8], ecx
0x180092243  mov     rcx, [r14+10h]
0x180092247  call    sqlite3VdbeAddOp3
0x18009224c  mov     rdi, [rsp+0D8h+arg_0]
0x180092254  lea     rdx, aTypeTriggerAnd; "type='trigger' AND name='%q'"
0x18009225b  mov     r8, rdi
0x18009225e  mov     rcx, rbp
0x180092261  xor     ebx, ebx
0x180092263  call    sqlite3MPrintf
0x180092268  mov     rcx, [rsp+0D8h+arg_18]
0x180092270  mov     r8, rax
0x180092273  movzx   r9d, bx
0x180092277  mov     edx, r13d
0x18009227a  call    sqlite3VdbeAddParseSchemaOp
0x18009227f  cmp     byte ptr [r12], 0
0x180092284  jz      short loc_1800922E4
0x180092286  mov     rax, [rbp+20h]
0x18009228a  mov     rcx, r13
0x18009228d  shl     rcx, 5
0x180092291  mov     r8, rsi
0x180092294  mov     rdx, rdi
0x180092297  mov     rbx, rsi
0x18009229a  mov     rcx, [rcx+rax+18h]
0x18009229f  add     rcx, 38h ; '8'
0x1800922a3  call    sqlite3HashInsert
0x1800922a8  mov     rsi, rax
0x1800922ab  test    rax, rax
0x1800922ae  jz      short loc_1800922BA
0x1800922b0  mov     rcx, rbp
0x1800922b3  call    sqlite3OomFault
0x1800922b8  jmp     short loc_1800922E4
0x1800922ba  mov     rcx, [rbx+30h]
0x1800922be  cmp     [rbx+28h], rcx
0x1800922c2  jnz     short loc_1800922E4
0x1800922c4  mov     rdx, [rbx+8]
0x1800922c8  add     rcx, 8
0x1800922cc  xor     r8d, r8d
0x1800922cf  call    findElementWithHash
0x1800922d4  mov     rdx, [rax+10h]
0x1800922d8  mov     rax, [rdx+58h]
0x1800922dc  mov     [rbx+40h], rax
0x1800922e0  mov     [rdx+58h], rbx
0x1800922e4  mov     rdx, rsi
0x1800922e7  mov     rcx, rbp
0x1800922ea  call    sqlite3DeleteTrigger
0x1800922ef  mov     rdx, r15
0x1800922f2  mov     rcx, rbp
0x1800922f5  call    sqlite3DeleteTriggerStep
0x1800922fa  mov     rbx, [rsp+0D8h+arg_8]
0x180092302  add     rsp, 0A0h
0x180092309  pop     r15
0x18009230b  pop     r14
0x18009230d  pop     r13
0x18009230f  pop     r12
0x180092311  pop     rdi
0x180092312  pop     rsi
0x180092313  pop     rbp
0x180092314  retn
```
