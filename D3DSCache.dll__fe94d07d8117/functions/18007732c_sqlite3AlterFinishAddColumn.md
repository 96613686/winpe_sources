# sqlite3AlterFinishAddColumn

- ea: `0x18007732c`
- end: `0x18007769d`
- name: `sqlite3AlterFinishAddColumn`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x18001bc30`

## callees

- `0x18000b4bc`
- `0x180014464`
- `0x18002817c`
- `0x180037880`
- `0x18003cc7c`
- `0x18003d480`
- `0x18003f5a8`
- `0x18004002c`
- `0x180042bb0`
- `0x180042c38`
- `0x18007387c`
- `0x18007732c`
- `0x18007c408`
- `0x180083968`
- `0x18008982c`
- `0x18008c9c4`
- `0x18008c9f0`

## string_xrefs

- `0x180077558`: `UPDATE "%w".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql))) WHERE type = 'table' AND name = %Q`

## pseudocode

```c
void __fastcall sqlite3AlterFinishAddColumn(_QWORD *a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // r15
  unsigned int v6; // eax
  unsigned __int8 *v7; // rbp
  __int64 v8; // rsi
  __int64 v9; // r12
  __int64 v10; // rbx
  int v11; // r8d
  int v12; // r9d
  const char *v13; // r8
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbx
  _BYTE *i; // rdx
  __int64 Vdbe; // r15
  unsigned int TempReg; // ebx
  int v19; // ecx
  __int64 v20; // rcx
  unsigned int v21; // [rsp+80h] [rbp+8h]
  __int64 v22; // [rsp+90h] [rbp+18h] BYREF
  __int64 Table; // [rsp+98h] [rbp+20h]

  if ( *((_DWORD *)a1 + 12) )
    return;
  v4 = a1[44];
  v5 = *a1;
  v6 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v4 + 96));
  v7 = (unsigned __int8 *)(*(_QWORD *)v4 + 16LL);
  v21 = v6;
  v8 = *(_QWORD *)(32LL * (int)v6 + *(_QWORD *)(v5 + 32));
  v9 = *(_QWORD *)(v4 + 8) + 24LL * *(__int16 *)(v4 + 54);
  v10 = sqlite3ColumnExpr(v4, v9 - 24);
  Table = sqlite3FindTable(v5, v7, v8);
  if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v8, *(_QWORD *)Table, 0) )
    return;
  if ( (*(_BYTE *)(v9 - 6) & 1) != 0 )
  {
    sqlite3ErrorMsg(a1, "Cannot add a PRIMARY KEY column");
    return;
  }
  if ( *(_QWORD *)(v4 + 16) )
  {
    sqlite3ErrorMsg(a1, "Cannot add a UNIQUE column");
    return;
  }
  if ( (*(_BYTE *)(v9 - 6) & 0x60) != 0 )
  {
    if ( (*(_BYTE *)(v9 - 6) & 0x40) != 0 )
    {
      v13 = "cannot add a STORED column";
      goto LABEL_26;
    }
  }
  else
  {
    if ( v10 && **(_BYTE **)(v10 + 16) == 121 )
      v10 = 0;
    if ( (*(_DWORD *)(v5 + 48) & 0x4000LL) != 0 && *(_QWORD *)(v4 + 72) && v10 )
      sqlite3NestedParse(
        a1,
        "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
        "Cannot add a REFERENCES column with non-NULL default value",
        v8,
        v7);
    if ( (*(_BYTE *)(v9 - 16) & 0xF) != 0 )
    {
      if ( !v10 )
      {
        v13 = "Cannot add a NOT NULL column with default value NULL";
LABEL_26:
        sqlite3NestedParse(a1, "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"", v13, v8, v7);
        goto LABEL_27;
      }
LABEL_20:
      v22 = 0;
      LOBYTE(v12) = 65;
      LOBYTE(v11) = 1;
      if ( (unsigned int)sqlite3ValueFromExpr(v5, v10, v11, v12, (__int64)&v22) )
        return;
      if ( !v22 )
        sqlite3NestedParse(
          a1,
          "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
          "Cannot add a column with non-constant default",
          v8,
          v7);
      sqlite3ValueFree();
      goto LABEL_27;
    }
    if ( v10 )
      goto LABEL_20;
  }
LABEL_27:
  v14 = sqlite3DbStrNDup(v5, *(_QWORD *)a2, *(unsigned int *)(a2 + 8));
  v15 = v14;
  if ( v14 )
  {
    for ( i = (_BYTE *)(v14 + (unsigned int)(*(_DWORD *)(a2 + 8) - 1));
          (unsigned __int64)i > v14 && (*i == 59 || (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)*i) & 1) != 0);
          --i )
    {
      *i = 0;
    }
    sqlite3NestedParse(
      a1,
      "UPDATE \"%w\".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql))) W"
      "HERE type = 'table' AND name = %Q",
      v8);
    sqlite3DbFree(v5, v15);
  }
  Vdbe = sqlite3GetVdbe(a1);
  if ( Vdbe )
  {
    TempReg = sqlite3GetTempReg(a1);
    sqlite3VdbeAddOp3(Vdbe, 99, v21, TempReg, 2);
    sqlite3VdbeUsesBtree(Vdbe, v21);
    sqlite3VdbeAddOp3(v19, 86, TempReg, -2, 0);
    sqlite3VdbeAddOp3(Vdbe, 59, TempReg, *(_DWORD *)(Vdbe + 144) + 2, 0);
    sqlite3VdbeAddOp3(Vdbe, 100, v21, 2, 3);
    sqlite3ReleaseTempReg(a1, TempReg);
    renameReloadSchema(v20, v21, 3);
    if ( *(_QWORD *)(v4 + 32)
      || (*(_BYTE *)(v9 - 16) & 0xF) != 0 && (*(_BYTE *)(v9 - 6) & 0x60) != 0
      || (*(_DWORD *)(Table + 48) & 0x10000) != 0 )
    {
      sqlite3NestedParse(
        a1,
        "SELECT CASE WHEN quick_check GLOB 'CHECK*' THEN raise(ABORT,'CHECK constraint failed') WHEN quick_check GLOB 'no"
        "n-* value in*' THEN raise(ABORT,'type mismatch on DEFAULT') ELSE raise(ABORT,'NOT NULL constraint failed') END  "
        "FROM pragma_quick_check(%Q,%Q) WHERE quick_check GLOB 'CHECK*' OR quick_check GLOB 'NULL*' OR quick_check GLOB '"
        "non-* value in*'",
        v7,
        v8);
    }
  }
}

```

## disassembly

```asm
0x18007732c  mov     [rsp+arg_8], rbx
0x180077331  push    rbp
0x180077332  push    rsi
0x180077333  push    rdi
0x180077334  push    r12
0x180077336  push    r13
0x180077338  push    r14
0x18007733a  push    r15
0x18007733c  sub     rsp, 40h
0x180077340  cmp     dword ptr [rcx+30h], 0
0x180077344  mov     r13, rdx
0x180077347  mov     rdi, rcx
0x18007734a  jnz     loc_180077685
0x180077350  mov     r14, [rcx+160h]
0x180077357  mov     r15, [rcx]
0x18007735a  mov     rcx, r15
0x18007735d  mov     rdx, [r14+60h]
0x180077361  call    sqlite3SchemaToIndex
0x180077366  mov     rdx, [r15+20h]
0x18007736a  movsx   rcx, word ptr [r14+36h]
0x18007736f  mov     rbp, [r14]
0x180077372  movsxd  r8, eax
0x180077375  add     rbp, 10h
0x180077379  shl     r8, 5
0x18007737d  mov     [rsp+78h+arg_0], eax
0x180077384  mov     rsi, [r8+rdx]
0x180077388  lea     rdx, [rcx+rcx*2]
0x18007738c  mov     rcx, [r14+8]
0x180077390  lea     r12, [rcx+rdx*8]
0x180077394  mov     rcx, r14
0x180077397  lea     rdx, [r12-18h]
0x18007739c  call    sqlite3ColumnExpr
0x1800773a1  mov     rcx, r15
0x1800773a4  mov     r8, rsi
0x1800773a7  mov     rdx, rbp
0x1800773aa  mov     rbx, rax
0x1800773ad  call    sqlite3FindTable
0x1800773b2  mov     r8, rsi
0x1800773b5  mov     [rsp+78h+arg_18], rax
0x1800773bd  mov     edx, 1Ah
0x1800773c2  mov     [rsp+78h+var_58], 0
0x1800773cb  mov     rcx, rdi
0x1800773ce  mov     r9, [rax]
0x1800773d1  call    sqlite3AuthCheck
0x1800773d6  test    eax, eax
0x1800773d8  jnz     loc_180077685
0x1800773de  test    byte ptr [r12-6], 1
0x1800773e4  jz      short loc_1800773FA
0x1800773e6  lea     rdx, aCannotAddAPrim; "Cannot add a PRIMARY KEY column"
0x1800773ed  mov     rcx, rdi
0x1800773f0  call    sqlite3ErrorMsg
0x1800773f5  jmp     loc_180077685
0x1800773fa  cmp     qword ptr [r14+10h], 0
0x1800773ff  jz      short loc_18007740A
0x180077401  lea     rdx, aCannotAddAUniq; "Cannot add a UNIQUE column"
0x180077408  jmp     short loc_1800773ED
0x18007740a  test    byte ptr [r12-6], 60h
0x180077410  jnz     loc_1800774EB
0x180077416  test    rbx, rbx
0x180077419  jz      short loc_180077428
0x18007741b  mov     rcx, [rbx+10h]
0x18007741f  xor     eax, eax
0x180077421  cmp     byte ptr [rcx], 79h ; 'y'
0x180077424  cmovz   rbx, rax
0x180077428  mov     eax, [r15+30h]
0x18007742c  bt      rax, 0Eh
0x180077431  jnb     short loc_18007745D
0x180077433  cmp     qword ptr [r14+48h], 0
0x180077438  jz      short loc_18007745D
0x18007743a  test    rbx, rbx
0x18007743d  jz      short loc_18007745D
0x18007743f  mov     r9, rsi
0x180077442  mov     [rsp+78h+var_58], rbp
0x180077447  lea     r8, aCannotAddARefe; "Cannot add a REFERENCES column with non"...
0x18007744e  mov     rcx, rdi
0x180077451  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x180077458  call    sqlite3NestedParse
0x18007745d  test    byte ptr [r12-10h], 0Fh
0x180077463  jz      short loc_180077476
0x180077465  test    rbx, rbx
0x180077468  jnz     short loc_18007747F
0x18007746a  lea     r8, aCannotAddANotN; "Cannot add a NOT NULL column with defau"...
0x180077471  jmp     loc_1800774FA
0x180077476  test    rbx, rbx
0x180077479  jz      loc_180077511
0x18007747f  lea     rax, [rsp+78h+arg_10]
0x180077487  mov     [rsp+78h+arg_10], 0
0x180077493  mov     r9b, 41h ; 'A'
0x180077496  mov     [rsp+78h+var_58], rax
0x18007749b  mov     r8b, 1
0x18007749e  mov     rdx, rbx
0x1800774a1  mov     rcx, r15
0x1800774a4  call    sqlite3ValueFromExpr
0x1800774a9  test    eax, eax
0x1800774ab  jnz     loc_180077685
0x1800774b1  mov     rcx, [rsp+78h+arg_10]
0x1800774b9  test    rcx, rcx
0x1800774bc  jnz     short loc_1800774E4
0x1800774be  mov     r9, rsi
0x1800774c1  mov     [rsp+78h+var_58], rbp
0x1800774c6  lea     r8, aCannotAddAColu_0; "Cannot add a column with non-constant d"...
0x1800774cd  mov     rcx, rdi
0x1800774d0  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x1800774d7  call    sqlite3NestedParse
0x1800774dc  mov     rcx, [rsp+78h+arg_10]
0x1800774e4  call    sqlite3ValueFree
0x1800774e9  jmp     short loc_180077511
0x1800774eb  test    byte ptr [r12-6], 40h
0x1800774f1  jz      short loc_180077511
0x1800774f3  lea     r8, aCannotAddAStor; "cannot add a STORED column"
0x1800774fa  mov     r9, rsi
0x1800774fd  mov     [rsp+78h+var_58], rbp
0x180077502  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x180077509  mov     rcx, rdi
0x18007750c  call    sqlite3NestedParse
0x180077511  mov     r8d, [r13+8]
0x180077515  mov     rcx, r15
0x180077518  mov     rdx, [r13+0]
0x18007751c  call    sqlite3DbStrNDup
0x180077521  mov     rbx, rax
0x180077524  test    rax, rax
0x180077527  jz      short loc_180077584
0x180077529  mov     edx, [r13+8]
0x18007752d  dec     edx
0x18007752f  add     rdx, rax
0x180077532  jmp     short loc_18007754F
0x180077534  cmp     byte ptr [rdx], 3Bh ; ';'
0x180077537  jz      short loc_180077549
0x180077539  movzx   eax, byte ptr [rdx]
0x18007753c  lea     rcx, qword_1800ADE90
0x180077543  test    byte ptr [rax+rcx], 1
0x180077547  jz      short loc_180077554
0x180077549  mov     byte ptr [rdx], 0
0x18007754c  dec     rdx
0x18007754f  cmp     rdx, rbx
0x180077552  ja      short loc_180077534
0x180077554  mov     r9d, [r14+40h]
0x180077558  lea     rdx, aUpdateWSqliteM_1; "UPDATE \"%w\".sqlite_master SET sql = p"...
0x18007755f  mov     [rsp+78h+var_48], rbp
0x180077564  mov     r8, rsi
0x180077567  mov     [rsp+78h+var_50], r9d
0x18007756c  mov     rcx, rdi
0x18007756f  mov     [rsp+78h+var_58], rbx
0x180077574  call    sqlite3NestedParse
0x180077579  mov     rdx, rbx
0x18007757c  mov     rcx, r15
0x18007757f  call    sqlite3DbFree
0x180077584  mov     rcx, rdi
0x180077587  call    sqlite3GetVdbe
0x18007758c  mov     r15, rax
0x18007758f  test    rax, rax
0x180077592  jz      loc_180077685
0x180077598  mov     rcx, rdi
0x18007759b  call    sqlite3GetTempReg
0x1800775a0  mov     r13d, [rsp+78h+arg_0]
0x1800775a8  mov     r9d, eax
0x1800775ab  mov     r8d, r13d
0x1800775ae  mov     dword ptr [rsp+78h+var_58], 2
0x1800775b6  mov     edx, 63h ; 'c'
0x1800775bb  mov     rcx, r15
0x1800775be  mov     ebx, eax
0x1800775c0  call    sqlite3VdbeAddOp3
0x1800775c5  mov     edx, r13d
0x1800775c8  mov     rcx, r15
0x1800775cb  call    sqlite3VdbeUsesBtree
0x1800775d0  mov     r9d, 0FFFFFFFEh
0x1800775d6  mov     dword ptr [rsp+78h+var_58], 0
0x1800775de  mov     r8d, ebx
0x1800775e1  lea     edx, [r9+58h]
0x1800775e5  call    sqlite3VdbeAddOp3
0x1800775ea  mov     r9d, [r15+90h]
0x1800775f1  mov     r8d, ebx
0x1800775f4  add     r9d, 2
0x1800775f8  mov     dword ptr [rsp+78h+var_58], 0
0x180077600  mov     edx, 3Bh ; ';'
0x180077605  mov     rcx, r15
0x180077608  call    sqlite3VdbeAddOp3
0x18007760d  mov     r9d, 2
0x180077613  mov     dword ptr [rsp+78h+var_58], 3
0x18007761b  mov     r8d, r13d
0x18007761e  mov     rcx, r15
0x180077621  lea     edx, [r9+62h]
0x180077625  call    sqlite3VdbeAddOp3
0x18007762a  mov     edx, ebx
0x18007762c  mov     rcx, rdi
0x18007762f  call    sqlite3ReleaseTempReg
0x180077634  mov     r8d, 3
0x18007763a  mov     edx, r13d
0x18007763d  call    renameReloadSchema
0x180077642  cmp     qword ptr [r14+20h], 0
0x180077647  jnz     short loc_180077670
0x180077649  test    byte ptr [r12-10h], 0Fh
0x18007764f  setnz   cl
0x180077652  test    byte ptr [r12-6], 60h
0x180077658  setnz   al
0x18007765b  test    al, cl
0x18007765d  jnz     short loc_180077670
0x18007765f  mov     rax, [rsp+78h+arg_18]
0x180077667  test    dword ptr [rax+30h], 10000h
0x18007766e  jz      short loc_180077685
0x180077670  mov     r9, rsi
0x180077673  lea     rdx, aSelectCaseWhen; "SELECT CASE WHEN quick_check GLOB 'CHEC"...
0x18007767a  mov     r8, rbp
0x18007767d  mov     rcx, rdi
0x180077680  call    sqlite3NestedParse
0x180077685  mov     rbx, [rsp+78h+arg_8]
0x18007768d  add     rsp, 40h
0x180077691  pop     r15
0x180077693  pop     r14
0x180077695  pop     r13
0x180077697  pop     r12
0x180077699  pop     rdi
0x18007769a  pop     rsi
0x18007769b  pop     rbp
0x18007769c  retn
```
