# sqlite3FinishTrigger

- ea: `0x180045eb8`
- end: `0x1800461d4`
- name: `sqlite3FinishTrigger`
- size: `796`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x180031b38`

## callees

- `0x180005810`
- `0x18000a9e0`
- `0x18000c454`
- `0x18000c500`
- `0x18000e7f0`
- `0x180010810`
- `0x1800119e0`
- `0x1800157d4`
- `0x180016250`
- `0x1800256c4`
- `0x180034bec`
- `0x18003f6dc`
- `0x180045eb8`
- `0x180046630`
- `0x1800466a4`
- `0x180060ce8`
- `0x180064ef0`
- `0x1800655a8`
- `0x18006910e`
- `0x1800857c4`
- `0x1800864b0`
- `0x180088234`

## string_xrefs

- `0x180046098`: `trigger "%s" may not write to shadow table "%s"`
- `0x1800460eb`: `INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')`

## pseudocode

```c
__int64 __fastcall sqlite3FinishTrigger(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rsi
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r13
  __int64 v14; // rcx
  _BYTE *v15; // r12
  __int64 v16; // r14
  _QWORD *v17; // rbx
  __int64 i; // rbx
  __int64 v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 Vdbe; // [rsp+30h] [rbp-59h]
  __int128 v26; // [rsp+38h] [rbp-51h] BYREF
  __int64 *v27; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v28[4]; // [rsp+58h] [rbp-31h] BYREF
  int v29; // [rsp+78h] [rbp-11h]
  __int16 v30; // [rsp+7Ch] [rbp-Dh]
  __int64 **v31; // [rsp+80h] [rbp-9h]
  __int64 v32; // [rsp+88h] [rbp-1h]
  bool v33; // [rsp+90h] [rbp+7h]
  __int64 v34; // [rsp+98h] [rbp+Fh]
  const char *v35; // [rsp+A0h] [rbp+17h]
  __int128 *v36; // [rsp+A8h] [rbp+1Fh]
  unsigned int v37; // [rsp+F0h] [rbp+67h]
  __int64 v39; // [rsp+108h] [rbp+7Fh]

  v3 = a1[46];
  v5 = *a1;
  memset_0(&v27, 0, 0x60u);
  v26 = 0;
  a1[46] = 0;
  if ( *((_DWORD *)a1 + 13) )
    goto LABEL_27;
  if ( !v3 )
    goto LABEL_27;
  v39 = *(_QWORD *)v3;
  v7 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v3 + 40));
  v10 = (int)v7;
  v37 = v7;
  *(_QWORD *)(v3 + 56) = a2;
  while ( a2 )
  {
    *(_QWORD *)(a2 + 8) = v3;
    a2 = *(_QWORD *)(a2 + 80);
  }
  *(_QWORD *)&v26 = *(_QWORD *)v3;
  v11 = sqlite3Strlen30(v26, v8, v9);
  v12 = *a1;
  DWORD2(v26) = v11;
  v27 = a1;
  v13 = 32 * v10;
  v34 = *(_QWORD *)(*(_QWORD *)(v12 + 32) + 32 * v10);
  v14 = *(_QWORD *)(*(_QWORD *)(v12 + 32) + 32 * v10 + 24);
  v35 = "trigger";
  v33 = (_DWORD)v10 == 1;
  v32 = v14;
  v36 = &v26;
  v28[0] = a1;
  v28[1] = fixExprCb;
  v28[2] = fixSelectCb;
  v28[3] = guard_check_icall_nop;
  v31 = &v27;
  v29 = 0;
  v30 = 0;
  if ( (unsigned int)sqlite3FixTriggerStep(&v27, *(_QWORD *)(v3 + 56))
    || (unsigned int)sqlite3WalkExpr(v28, *(_QWORD *)(v3 + 24)) )
  {
    goto LABEL_27;
  }
  if ( *((_BYTE *)a1 + 308) >= 2u )
  {
    a1[46] = v3;
    v3 = 0;
    v15 = (_BYTE *)(v5 + 197);
LABEL_10:
    v16 = v39;
    goto LABEL_11;
  }
  v15 = (_BYTE *)(v5 + 197);
  if ( *(_BYTE *)(v5 + 197) )
    goto LABEL_10;
  if ( (unsigned int)sqlite3ReadOnlyShadowTables(v5) )
  {
    for ( i = *(_QWORD *)(v3 + 56); i; i = *(_QWORD *)(i + 80) )
    {
      v19 = *(_QWORD *)(i + 24);
      if ( v19 && (unsigned int)sqlite3ShadowTableName(v5, v19) )
      {
        sqlite3ErrorMsg(
          a1,
          "trigger \"%s\" may not write to shadow table \"%s\"",
          *(const char **)v3,
          *(const char **)(i + 24));
        goto LABEL_27;
      }
    }
    LODWORD(v10) = v37;
  }
  Vdbe = sqlite3GetVdbe(a1);
  if ( Vdbe )
  {
    sqlite3BeginWriteOperation(a1, 0, (unsigned int)v10);
    v20 = sqlite3DbStrNDup(v5, *(_QWORD *)a3, *(unsigned int *)(a3 + 8));
    sqlite3NestedParse(
      a1,
      "INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')",
      *(_QWORD *)(*(_QWORD *)(v5 + 32) + v13),
      v39,
      *(_QWORD *)(v3 + 8),
      v20);
    sqlite3DbFree(v5, v20);
    sqlite3VdbeAddOp3(a1[2], 100, v37, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32) + v13 + 24) + 1);
    v16 = v39;
    v21 = sqlite3MPrintf(v5, "type='trigger' AND name='%q'", v39);
    sqlite3VdbeAddParseSchemaOp(Vdbe, v37, v21, 0);
LABEL_11:
    if ( *v15 )
    {
      v17 = (_QWORD *)v3;
      v3 = sqlite3HashInsert(*(_QWORD *)(*(_QWORD *)(v5 + 32) + v13 + 24) + 56LL, v16, v3);
      if ( v3 )
      {
        sqlite3OomFault(v5);
      }
      else
      {
        v22 = v17[6];
        if ( v17[5] == v22 )
        {
          v23 = *(_QWORD *)(findElementWithHash(v22 + 8, v17[1], 0) + 16);
          v17[8] = *(_QWORD *)(v23 + 88);
          *(_QWORD *)(v23 + 88) = v17;
        }
      }
    }
  }
LABEL_27:
  sqlite3DeleteTrigger(v5, v3);
  return sqlite3DeleteTriggerStep(v5, a2);
}

```

## disassembly

```asm
0x180045eb8  mov     [rsp-8+arg_8], rbx
0x180045ebd  mov     [rsp-8+arg_10], r8
0x180045ec2  push    rbp
0x180045ec3  push    rsi
0x180045ec4  push    rdi
0x180045ec5  push    r12
0x180045ec7  push    r13
0x180045ec9  push    r14
0x180045ecb  push    r15
0x180045ecd  lea     rbp, [rsp-27h]
0x180045ed2  sub     rsp, 0B0h
0x180045ed9  mov     rdi, [rcx+170h]
0x180045ee0  mov     r15, rdx
0x180045ee3  mov     rsi, [rcx]
0x180045ee6  xor     edx, edx; Val
0x180045ee8  mov     r14, rcx
0x180045eeb  lea     rcx, [rbp+57h+var_90]; void *
0x180045eef  lea     r8d, [rdx+60h]; Size
0x180045ef3  call    memset_0
0x180045ef8  xor     r12d, r12d
0x180045efb  xorps   xmm0, xmm0
0x180045efe  movups  [rbp+57h+var_A8], xmm0
0x180045f02  mov     [r14+170h], r12
0x180045f09  cmp     [r14+34h], r12d
0x180045f0d  jnz     loc_1800461A3
0x180045f13  test    rdi, rdi
0x180045f16  jz      loc_1800461A3
0x180045f1c  mov     rax, [rdi]
0x180045f1f  mov     rcx, rsi
0x180045f22  mov     rdx, [rdi+28h]
0x180045f26  mov     [rbp+57h+arg_18], rax
0x180045f2a  call    sqlite3SchemaToIndex
0x180045f2f  movsxd  rbx, eax
0x180045f32  mov     [rbp+57h+arg_0], ebx
0x180045f35  mov     [rdi+38h], r15
0x180045f39  jmp     short loc_180045F43
0x180045f3b  mov     [r15+8], rdi
0x180045f3f  mov     r15, [r15+50h]
0x180045f43  test    r15, r15
0x180045f46  jnz     short loc_180045F3B
0x180045f48  mov     rcx, [rdi]
0x180045f4b  mov     qword ptr [rbp+57h+var_A8], rcx
0x180045f4f  call    sqlite3Strlen30
0x180045f54  mov     rdx, [r14]
0x180045f57  mov     r13, rbx
0x180045f5a  mov     dword ptr [rbp+57h+var_A8+8], eax
0x180045f5d  mov     [rbp+57h+var_90], r14
0x180045f61  shl     r13, 5
0x180045f65  mov     rax, [rdx+20h]
0x180045f69  cmp     ebx, 1
0x180045f6c  mov     rcx, [rax+r13]
0x180045f70  mov     [rbp+57h+var_48], rcx
0x180045f74  mov     rax, [rdx+20h]
0x180045f78  mov     rcx, [rax+r13+18h]
0x180045f7d  lea     rax, aTrigger; "trigger"
0x180045f84  mov     [rbp+57h+var_40], rax
0x180045f88  setz    [rbp+57h+var_50]
0x180045f8c  mov     [rbp+57h+var_58], rcx
0x180045f90  lea     rax, [rbp+57h+var_A8]
0x180045f94  mov     [rbp+57h+var_38], rax
0x180045f98  lea     rcx, [rbp+57h+var_90]
0x180045f9c  lea     rax, fixExprCb
0x180045fa3  mov     [rbp+57h+var_88], r14
0x180045fa7  mov     [rbp+57h+var_80], rax
0x180045fab  lea     rax, fixSelectCb
0x180045fb2  mov     [rbp+57h+var_78], rax
0x180045fb6  lea     rax, _guard_check_icall_nop
0x180045fbd  mov     [rbp+57h+var_70], rax
0x180045fc1  lea     rax, [rbp+57h+var_90]
0x180045fc5  mov     [rbp+57h+var_60], rax
0x180045fc9  mov     [rbp+57h+var_68], r12d
0x180045fcd  mov     [rbp+57h+var_64], r12w
0x180045fd2  mov     rdx, [rdi+38h]
0x180045fd6  call    sqlite3FixTriggerStep
0x180045fdb  test    eax, eax
0x180045fdd  jnz     loc_1800461A3
0x180045fe3  mov     rdx, [rdi+18h]
0x180045fe7  lea     rcx, [rbp+57h+var_88]
0x180045feb  call    sqlite3WalkExpr
0x180045ff0  test    eax, eax
0x180045ff2  jnz     loc_1800461A3
0x180045ff8  cmp     byte ptr [r14+134h], 2
0x180046000  jb      short loc_180046056
0x180046002  mov     [r14+170h], rdi
0x180046009  mov     rdi, r12
0x18004600c  lea     r12, [rsi+0C5h]
0x180046013  mov     r14, [rbp+57h+arg_18]
0x180046017  cmp     byte ptr [r12], 0
0x18004601c  jz      loc_1800461A3
0x180046022  mov     rax, [rsi+20h]
0x180046026  mov     r8, rdi
0x180046029  mov     rdx, r14
0x18004602c  mov     rbx, rdi
0x18004602f  mov     rcx, [rax+r13+18h]
0x180046034  add     rcx, 38h ; '8'
0x180046038  call    sqlite3HashInsert
0x18004603d  mov     rdi, rax
0x180046040  test    rax, rax
0x180046043  jz      loc_180046179
0x180046049  mov     rcx, rsi
0x18004604c  call    sqlite3OomFault
0x180046051  jmp     loc_1800461A3
0x180046056  lea     r12, [rsi+0C5h]
0x18004605d  cmp     byte ptr [r12], 0
0x180046062  jnz     short loc_180046013
0x180046064  mov     rcx, rsi
0x180046067  call    sqlite3ReadOnlyShadowTables
0x18004606c  test    eax, eax
0x18004606e  jz      short loc_1800460B2
0x180046070  mov     rbx, [rdi+38h]
0x180046074  test    rbx, rbx
0x180046077  jz      short loc_1800460AF
0x180046079  mov     rdx, [rbx+18h]
0x18004607d  test    rdx, rdx
0x180046080  jz      short loc_18004608E
0x180046082  mov     rcx, rsi
0x180046085  call    sqlite3ShadowTableName
0x18004608a  test    eax, eax
0x18004608c  jnz     short loc_180046094
0x18004608e  mov     rbx, [rbx+50h]
0x180046092  jmp     short loc_180046074
0x180046094  mov     r9, [rbx+18h]
0x180046098  lea     rdx, aTriggerSMayNot; "trigger \"%s\" may not write to shadow "...
0x18004609f  mov     r8, [rdi]
0x1800460a2  mov     rcx, r14
0x1800460a5  call    sqlite3ErrorMsg
0x1800460aa  jmp     loc_1800461A3
0x1800460af  mov     ebx, [rbp+57h+arg_0]
0x1800460b2  mov     rcx, r14
0x1800460b5  call    sqlite3GetVdbe
0x1800460ba  mov     [rbp+57h+var_B0], rax
0x1800460be  test    rax, rax
0x1800460c1  jz      loc_1800461A3
0x1800460c7  mov     r8d, ebx
0x1800460ca  xor     edx, edx
0x1800460cc  mov     rcx, r14
0x1800460cf  call    sqlite3BeginWriteOperation
0x1800460d4  mov     rax, [rbp+57h+arg_10]
0x1800460d8  mov     rcx, rsi
0x1800460db  mov     r8d, [rax+8]
0x1800460df  mov     rdx, [rax]
0x1800460e2  call    sqlite3DbStrNDup
0x1800460e7  mov     rcx, [rdi+8]
0x1800460eb  lea     rdx, aInsertIntoQSql_0; "INSERT INTO %Q.sqlite_master VALUES('tr"...
0x1800460f2  mov     r8, [rsi+20h]
0x1800460f6  mov     rbx, rax
0x1800460f9  mov     r9, [rbp+57h+arg_18]
0x1800460fd  mov     [rsp+0E0h+var_B8], rax
0x180046102  mov     [rsp+0E0h+var_C0], rcx
0x180046107  mov     rcx, r14
0x18004610a  mov     r8, [r8+r13]
0x18004610e  call    sqlite3NestedParse
0x180046113  mov     rdx, rbx
0x180046116  mov     rcx, rsi
0x180046119  call    sqlite3DbFree
0x18004611e  mov     rax, [r14]
0x180046121  mov     r9d, 1
0x180046127  mov     r8d, [rbp+57h+arg_0]
0x18004612b  mov     rcx, [rax+20h]
0x18004612f  lea     edx, [r9+63h]
0x180046133  mov     rax, [rcx+r13+18h]
0x180046138  mov     ecx, [rax]
0x18004613a  inc     ecx
0x18004613c  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x180046140  mov     rcx, [r14+10h]
0x180046144  call    sqlite3VdbeAddOp3
0x180046149  mov     r14, [rbp+57h+arg_18]
0x18004614d  lea     rdx, aTypeTriggerAnd; "type='trigger' AND name='%q'"
0x180046154  mov     r8, r14
0x180046157  mov     rcx, rsi
0x18004615a  xor     ebx, ebx
0x18004615c  call    sqlite3MPrintf
0x180046161  mov     edx, [rbp+57h+arg_0]
0x180046164  mov     r8, rax
0x180046167  mov     rcx, [rbp+57h+var_B0]
0x18004616b  movzx   r9d, bx
0x18004616f  call    sqlite3VdbeAddParseSchemaOp
0x180046174  jmp     loc_180046017
0x180046179  mov     rcx, [rbx+30h]
0x18004617d  cmp     [rbx+28h], rcx
0x180046181  jnz     short loc_1800461A3
0x180046183  mov     rdx, [rbx+8]
0x180046187  add     rcx, 8
0x18004618b  xor     r8d, r8d
0x18004618e  call    findElementWithHash
0x180046193  mov     rdx, [rax+10h]
0x180046197  mov     rax, [rdx+58h]
0x18004619b  mov     [rbx+40h], rax
0x18004619f  mov     [rdx+58h], rbx
0x1800461a3  mov     rdx, rdi
0x1800461a6  mov     rcx, rsi
0x1800461a9  call    sqlite3DeleteTrigger
0x1800461ae  mov     rdx, r15
0x1800461b1  mov     rcx, rsi
0x1800461b4  call    sqlite3DeleteTriggerStep
0x1800461b9  mov     rbx, [rsp+0E0h+arg_8]
0x1800461c1  add     rsp, 0B0h
0x1800461c8  pop     r15
0x1800461ca  pop     r14
0x1800461cc  pop     r13
0x1800461ce  pop     r12
0x1800461d0  pop     rdi
0x1800461d1  pop     rsi
0x1800461d2  pop     rbp
0x1800461d3  retn
```
