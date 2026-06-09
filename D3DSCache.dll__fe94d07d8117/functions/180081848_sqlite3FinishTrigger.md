# sqlite3FinishTrigger

- ea: `0x180081848`
- end: `0x180081b21`
- name: `sqlite3FinishTrigger`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x18001bc30`

## callees

- `0x18000b4bc`
- `0x180014464`
- `0x18002b81c`
- `0x18002b840`
- `0x1800369e4`
- `0x180039494`
- `0x18003b5b4`
- `0x18003b9c8`
- `0x18003bebc`
- `0x18003c8d4`
- `0x18003cc7c`
- `0x18003d480`
- `0x18003f5a8`
- `0x180042bb0`
- `0x180042c38`
- `0x180042c68`
- `0x180045374`
- `0x18007e48c`
- `0x18007e4fc`
- `0x180081848`
- `0x180081b28`
- `0x180081c24`
- `0x180088ee0`

## string_xrefs

- `0x180081997`: `trigger "%s" may not write to shadow table "%s"`
- `0x1800819ef`: `INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')`

## pseudocode

```c
__int64 __fastcall sqlite3FinishTrigger(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v5; // rbp
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r13
  _BYTE *v13; // r12
  __int64 i; // rbx
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rax
  _QWORD *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int128 v22; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v24[144]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v25; // [rsp+E0h] [rbp+8h]
  __int64 Vdbe; // [rsp+F8h] [rbp+20h]

  v3 = a1[46];
  v5 = *a1;
  v6 = a3;
  memset_0(v23, 0, 0x60u);
  v8 = *((_DWORD *)a1 + 12) == 0;
  v22 = 0;
  a1[46] = 0;
  if ( !v8 )
    goto LABEL_26;
  if ( !v3 )
    goto LABEL_26;
  v9 = *(_QWORD *)v3;
  v25 = *(_QWORD *)v3;
  v12 = (int)sqlite3SchemaToIndex(v5, *(_QWORD *)(v3 + 40));
  *(_QWORD *)(v3 + 56) = a2;
  while ( a2 )
  {
    *(_QWORD *)(a2 + 8) = v3;
    a2 = *(_QWORD *)(a2 + 80);
  }
  *(_QWORD *)&v22 = *(_QWORD *)v3;
  DWORD2(v22) = sqlite3Strlen30(v22, v10, v11);
  sqlite3FixInit((unsigned int)v23, (_DWORD)a1, v12, (unsigned int)"trigger", (__int64)&v22);
  if ( (unsigned int)sqlite3FixTriggerStep(v23, *(_QWORD *)(v3 + 56))
    || (unsigned int)sqlite3WalkExpr(v24, *(_QWORD *)(v3 + 24)) )
  {
    goto LABEL_26;
  }
  v13 = (_BYTE *)(v5 + 197);
  if ( *((_BYTE *)a1 + 308) >= 2u )
  {
    a1[46] = v3;
    v3 = 0;
    goto LABEL_21;
  }
  if ( *v13 )
  {
LABEL_22:
    v18 = (_QWORD *)v3;
    v3 = sqlite3HashInsert(*(_QWORD *)(32 * v12 + *(_QWORD *)(v5 + 32) + 24) + 56LL, v9, v3);
    if ( v3 )
    {
      sqlite3OomFault(v5);
    }
    else
    {
      v19 = v18[6];
      if ( v18[5] == v19 )
      {
        v20 = *(_QWORD *)(findElementWithHash(v19 + 8, v18[1], 0) + 16);
        v18[8] = *(_QWORD *)(v20 + 88);
        *(_QWORD *)(v20 + 88) = v18;
      }
    }
    goto LABEL_26;
  }
  if ( (unsigned int)sqlite3ReadOnlyShadowTables(v5) )
  {
    for ( i = *(_QWORD *)(v3 + 56); i; i = *(_QWORD *)(i + 80) )
    {
      v15 = *(_QWORD *)(i + 24);
      if ( v15 && (unsigned int)sqlite3ShadowTableName(v5, v15) )
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
    sqlite3BeginWriteOperation(a1, 0, (unsigned int)v12);
    v16 = sqlite3DbStrNDup(v5, *(_QWORD *)v6, *(unsigned int *)(v6 + 8));
    sqlite3NestedParse(
      a1,
      "INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')",
      *(_QWORD *)(*(_QWORD *)(v5 + 32) + 32 * v12),
      v25,
      *(_QWORD *)(v3 + 8),
      v16);
    sqlite3DbFree(v5, v16);
    sqlite3VdbeAddOp3(a1[2], 100, v12, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32) + 32 * v12 + 24) + 1);
    v9 = v25;
    v17 = sqlite3MPrintf(v5, "type='trigger' AND name='%q'", v25);
    sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v12, v17, 0);
LABEL_21:
    if ( !*v13 )
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
0x180081848  mov     [rsp+arg_8], rbx
0x18008184d  mov     [rsp+arg_10], r8
0x180081852  push    rbp
0x180081853  push    rsi
0x180081854  push    rdi
0x180081855  push    r12
0x180081857  push    r13
0x180081859  push    r14
0x18008185b  push    r15
0x18008185d  sub     rsp, 0A0h
0x180081864  mov     rsi, [rcx+170h]
0x18008186b  mov     r15, rdx
0x18008186e  mov     rbp, [rcx]
0x180081871  xor     edx, edx; Val
0x180081873  mov     rbx, r8
0x180081876  mov     r14, rcx
0x180081879  lea     rcx, [rsp+0D8h+var_98]; void *
0x18008187e  lea     r8d, [rdx+60h]; Size
0x180081882  call    memset_0
0x180081887  cmp     dword ptr [r14+30h], 0
0x18008188c  xorps   xmm0, xmm0
0x18008188f  movups  [rsp+0D8h+var_A8], xmm0
0x180081894  mov     qword ptr [r14+170h], 0
0x18008189f  jnz     loc_180081AF0
0x1800818a5  test    rsi, rsi
0x1800818a8  jz      loc_180081AF0
0x1800818ae  mov     rdi, [rsi]
0x1800818b1  mov     rcx, rbp
0x1800818b4  mov     rdx, [rsi+28h]
0x1800818b8  mov     [rsp+0D8h+arg_0], rdi
0x1800818c0  call    sqlite3SchemaToIndex
0x1800818c5  movsxd  r13, eax
0x1800818c8  mov     [rsi+38h], r15
0x1800818cc  jmp     short loc_1800818D6
0x1800818ce  mov     [r15+8], rsi
0x1800818d2  mov     r15, [r15+50h]
0x1800818d6  test    r15, r15
0x1800818d9  jnz     short loc_1800818CE
0x1800818db  mov     rcx, [rsi]
0x1800818de  mov     qword ptr [rsp+0D8h+var_A8], rcx
0x1800818e3  call    sqlite3Strlen30
0x1800818e8  mov     dword ptr [rsp+0D8h+var_A8+8], eax
0x1800818ec  lea     r9, aTrigger; "trigger"
0x1800818f3  lea     rax, [rsp+0D8h+var_A8]
0x1800818f8  mov     r8d, r13d
0x1800818fb  mov     rdx, r14
0x1800818fe  mov     [rsp+0D8h+var_B8], rax
0x180081903  lea     rcx, [rsp+0D8h+var_98]
0x180081908  call    sqlite3FixInit
0x18008190d  mov     rdx, [rsi+38h]
0x180081911  lea     rcx, [rsp+0D8h+var_98]
0x180081916  call    sqlite3FixTriggerStep
0x18008191b  test    eax, eax
0x18008191d  jnz     loc_180081AF0
0x180081923  mov     rdx, [rsi+18h]
0x180081927  lea     rcx, [rsp+0D8h+var_90]
0x18008192c  call    sqlite3WalkExpr
0x180081931  test    eax, eax
0x180081933  jnz     loc_180081AF0
0x180081939  cmp     byte ptr [r14+134h], 2
0x180081941  lea     r12, [rbp+0C5h]
0x180081948  jb      short loc_180081958
0x18008194a  mov     [r14+170h], rsi
0x180081951  xor     esi, esi
0x180081953  jmp     loc_180081A8B
0x180081958  cmp     byte ptr [r12], 0
0x18008195d  jnz     loc_180081A92
0x180081963  mov     rcx, rbp
0x180081966  call    sqlite3ReadOnlyShadowTables
0x18008196b  test    eax, eax
0x18008196d  jz      short loc_1800819B6
0x18008196f  mov     rbx, [rsi+38h]
0x180081973  test    rbx, rbx
0x180081976  jz      short loc_1800819AE
0x180081978  mov     rdx, [rbx+18h]
0x18008197c  test    rdx, rdx
0x18008197f  jz      short loc_18008198D
0x180081981  mov     rcx, rbp
0x180081984  call    sqlite3ShadowTableName
0x180081989  test    eax, eax
0x18008198b  jnz     short loc_180081993
0x18008198d  mov     rbx, [rbx+50h]
0x180081991  jmp     short loc_180081973
0x180081993  mov     r9, [rbx+18h]
0x180081997  lea     rdx, aTriggerSMayNot; "trigger \"%s\" may not write to shadow "...
0x18008199e  mov     r8, [rsi]
0x1800819a1  mov     rcx, r14
0x1800819a4  call    sqlite3ErrorMsg
0x1800819a9  jmp     loc_180081AF0
0x1800819ae  mov     rbx, [rsp+0D8h+arg_10]
0x1800819b6  mov     rcx, r14
0x1800819b9  call    sqlite3GetVdbe
0x1800819be  mov     [rsp+0D8h+arg_18], rax
0x1800819c6  test    rax, rax
0x1800819c9  jz      loc_180081AF0
0x1800819cf  mov     r8d, r13d
0x1800819d2  xor     edx, edx
0x1800819d4  mov     rcx, r14
0x1800819d7  call    sqlite3BeginWriteOperation
0x1800819dc  mov     r8d, [rbx+8]
0x1800819e0  mov     rcx, rbp
0x1800819e3  mov     rdx, [rbx]
0x1800819e6  call    sqlite3DbStrNDup
0x1800819eb  mov     rcx, [rsi+8]
0x1800819ef  lea     rdx, aInsertIntoQSql_0; "INSERT INTO %Q.sqlite_master VALUES('tr"...
0x1800819f6  mov     r8, [rbp+20h]
0x1800819fa  mov     rdi, r13
0x1800819fd  mov     r9, [rsp+0D8h+arg_0]
0x180081a05  mov     rbx, rax
0x180081a08  mov     [rsp+0D8h+var_B0], rax
0x180081a0d  mov     [rsp+0D8h+var_B8], rcx
0x180081a12  mov     rcx, r14
0x180081a15  shl     rdi, 5
0x180081a19  mov     r8, [r8+rdi]
0x180081a1d  call    sqlite3NestedParse
0x180081a22  mov     rdx, rbx
0x180081a25  mov     rcx, rbp
0x180081a28  call    sqlite3DbFree
0x180081a2d  mov     rax, [r14]
0x180081a30  mov     r9d, 1
0x180081a36  mov     r8d, r13d
0x180081a39  mov     rcx, [rax+20h]
0x180081a3d  lea     edx, [r9+63h]
0x180081a41  mov     rax, [rcx+rdi+18h]
0x180081a46  mov     ecx, [rax]
0x180081a48  add     ecx, r9d
0x180081a4b  mov     dword ptr [rsp+0D8h+var_B8], ecx
0x180081a4f  mov     rcx, [r14+10h]
0x180081a53  call    sqlite3VdbeAddOp3
0x180081a58  mov     rdi, [rsp+0D8h+arg_0]
0x180081a60  lea     rdx, aTypeTriggerAnd; "type='trigger' AND name='%q'"
0x180081a67  mov     r8, rdi
0x180081a6a  mov     rcx, rbp
0x180081a6d  xor     ebx, ebx
0x180081a6f  call    sqlite3MPrintf
0x180081a74  mov     rcx, [rsp+0D8h+arg_18]
0x180081a7c  mov     r8, rax
0x180081a7f  movzx   r9d, bx
0x180081a83  mov     edx, r13d
0x180081a86  call    sqlite3VdbeAddParseSchemaOp
0x180081a8b  cmp     byte ptr [r12], 0
0x180081a90  jz      short loc_180081AF0
0x180081a92  mov     rax, [rbp+20h]
0x180081a96  mov     rcx, r13
0x180081a99  shl     rcx, 5
0x180081a9d  mov     r8, rsi
0x180081aa0  mov     rdx, rdi
0x180081aa3  mov     rbx, rsi
0x180081aa6  mov     rcx, [rcx+rax+18h]
0x180081aab  add     rcx, 38h ; '8'
0x180081aaf  call    sqlite3HashInsert
0x180081ab4  mov     rsi, rax
0x180081ab7  test    rax, rax
0x180081aba  jz      short loc_180081AC6
0x180081abc  mov     rcx, rbp
0x180081abf  call    sqlite3OomFault
0x180081ac4  jmp     short loc_180081AF0
0x180081ac6  mov     rcx, [rbx+30h]
0x180081aca  cmp     [rbx+28h], rcx
0x180081ace  jnz     short loc_180081AF0
0x180081ad0  mov     rdx, [rbx+8]
0x180081ad4  add     rcx, 8
0x180081ad8  xor     r8d, r8d
0x180081adb  call    findElementWithHash
0x180081ae0  mov     rdx, [rax+10h]
0x180081ae4  mov     rax, [rdx+58h]
0x180081ae8  mov     [rbx+40h], rax
0x180081aec  mov     [rdx+58h], rbx
0x180081af0  mov     rdx, rsi
0x180081af3  mov     rcx, rbp
0x180081af6  call    sqlite3DeleteTrigger
0x180081afb  mov     rdx, r15
0x180081afe  mov     rcx, rbp
0x180081b01  call    sqlite3DeleteTriggerStep
0x180081b06  mov     rbx, [rsp+0D8h+arg_8]
0x180081b0e  add     rsp, 0A0h
0x180081b15  pop     r15
0x180081b17  pop     r14
0x180081b19  pop     r13
0x180081b1b  pop     r12
0x180081b1d  pop     rdi
0x180081b1e  pop     rsi
0x180081b1f  pop     rbp
0x180081b20  retn
```
