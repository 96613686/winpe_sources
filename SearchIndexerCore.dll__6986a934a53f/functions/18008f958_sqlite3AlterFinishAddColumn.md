# sqlite3AlterFinishAddColumn

- ea: `0x18008f958`
- end: `0x18008fcc9`
- name: `sqlite3AlterFinishAddColumn`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x18000213c`

## callees

- `0x18000a180`
- `0x180011bcc`
- `0x180014690`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001f0f0`
- `0x18001f418`
- `0x180024770`
- `0x180041d10`
- `0x18004a418`
- `0x18004a478`
- `0x18004a9b8`
- `0x18004bfc0`
- `0x180051fd0`
- `0x1800587c8`
- `0x18008d51c`
- `0x18008f958`

## string_xrefs

- `0x18008fb84`: `UPDATE "%w".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql))) WHERE type = 'table' AND name = %Q`

## pseudocode

```c
void __fastcall sqlite3AlterFinishAddColumn(_QWORD *a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // r15
  unsigned int v6; // eax
  unsigned __int8 *v7; // rbp
  __int64 v8; // r8
  _BYTE *v9; // rsi
  __int64 v10; // r12
  __int64 v11; // r9
  __int64 v12; // rbx
  int v13; // r8d
  int v14; // r9d
  const char *v15; // r8
  __int64 v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rbx
  _BYTE *i; // rdx
  __int64 v20; // rdx
  __int64 Vdbe; // r15
  unsigned int TempReg; // ebx
  int v23; // ecx
  __int64 v24; // rcx
  unsigned int v25; // [rsp+80h] [rbp+8h]
  __int64 v26; // [rsp+90h] [rbp+18h] BYREF
  __int64 Table; // [rsp+98h] [rbp+20h]

  if ( *((_DWORD *)a1 + 12) )
    return;
  v4 = a1[44];
  v5 = *a1;
  v6 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v4 + 96));
  v7 = (unsigned __int8 *)(*(_QWORD *)v4 + 16LL);
  v8 = 32LL * (int)v6;
  v25 = v6;
  v9 = *(_BYTE **)(v8 + *(_QWORD *)(v5 + 32));
  v10 = *(_QWORD *)(v4 + 8) + 24LL * *(__int16 *)(v4 + 54);
  v12 = sqlite3ColumnExpr(v4, v10 - 24, v8, v11);
  Table = sqlite3FindTable(v5, v7, v9);
  if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, (_DWORD)v9, *(_QWORD *)Table, 0) )
    return;
  if ( (*(_BYTE *)(v10 - 6) & 1) != 0 )
  {
    sqlite3ErrorMsg(a1, "Cannot add a PRIMARY KEY column");
    return;
  }
  if ( *(_QWORD *)(v4 + 16) )
  {
    sqlite3ErrorMsg(a1, "Cannot add a UNIQUE column");
    return;
  }
  if ( (*(_BYTE *)(v10 - 6) & 0x60) != 0 )
  {
    if ( (*(_BYTE *)(v10 - 6) & 0x40) != 0 )
    {
      v15 = "cannot add a STORED column";
      goto LABEL_26;
    }
  }
  else
  {
    if ( v12 && **(_BYTE **)(v12 + 16) == 121 )
      v12 = 0;
    if ( (*(_DWORD *)(v5 + 48) & 0x4000LL) != 0 && *(_QWORD *)(v4 + 72) && v12 )
      sqlite3NestedParse(
        a1,
        "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
        "Cannot add a REFERENCES column with non-NULL default value",
        v9,
        v7);
    if ( (*(_BYTE *)(v10 - 16) & 0xF) != 0 )
    {
      if ( !v12 )
      {
        v15 = "Cannot add a NOT NULL column with default value NULL";
LABEL_26:
        sqlite3NestedParse(a1, "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"", v15, v9, v7);
        goto LABEL_27;
      }
LABEL_20:
      v26 = 0;
      LOBYTE(v14) = 65;
      LOBYTE(v13) = 1;
      if ( (unsigned int)sqlite3ValueFromExpr(v5, v12, v13, v14, (__int64)&v26) )
        return;
      v16 = v26;
      if ( !v26 )
      {
        sqlite3NestedParse(
          a1,
          "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
          "Cannot add a column with non-constant default",
          v9,
          v7);
        v16 = v26;
      }
      sqlite3ValueFree(v16);
      goto LABEL_27;
    }
    if ( v12 )
      goto LABEL_20;
  }
LABEL_27:
  v17 = sqlite3DbStrNDup(v5, *(_QWORD *)a2, *(unsigned int *)(a2 + 8));
  v18 = v17;
  if ( v17 )
  {
    for ( i = (_BYTE *)(v17 + (unsigned int)(*(_DWORD *)(a2 + 8) - 1));
          (unsigned __int64)i > v17 && (*i == 59 || (*((_BYTE *)&qword_1800B4FF0 + (unsigned __int8)*i) & 1) != 0);
          --i )
    {
      *i = 0;
    }
    sqlite3NestedParse(
      a1,
      "UPDATE \"%w\".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql))) W"
      "HERE type = 'table' AND name = %Q",
      v9);
    sqlite3DbFree(v5, v18);
  }
  Vdbe = sqlite3GetVdbe(a1);
  if ( Vdbe )
  {
    TempReg = sqlite3GetTempReg(a1, v20);
    sqlite3VdbeAddOp3(Vdbe, 99, v25, TempReg, 2);
    sqlite3VdbeUsesBtree(Vdbe, v25);
    sqlite3VdbeAddOp3(v23, 86, TempReg, -2, 0);
    sqlite3VdbeAddOp3(Vdbe, 59, TempReg, *(_DWORD *)(Vdbe + 144) + 2, 0);
    sqlite3VdbeAddOp3(Vdbe, 100, v25, 2, 3);
    sqlite3ReleaseTempReg(a1, TempReg);
    renameReloadSchema(v24, v25, 3);
    if ( *(_QWORD *)(v4 + 32)
      || (*(_BYTE *)(v10 - 16) & 0xF) != 0 && (*(_BYTE *)(v10 - 6) & 0x60) != 0
      || (*(_DWORD *)(Table + 48) & 0x10000) != 0 )
    {
      sqlite3NestedParse(
        a1,
        "SELECT CASE WHEN quick_check GLOB 'CHECK*' THEN raise(ABORT,'CHECK constraint failed') WHEN quick_check GLOB 'no"
        "n-* value in*' THEN raise(ABORT,'type mismatch on DEFAULT') ELSE raise(ABORT,'NOT NULL constraint failed') END  "
        "FROM pragma_quick_check(%Q,%Q) WHERE quick_check GLOB 'CHECK*' OR quick_check GLOB 'NULL*' OR quick_check GLOB '"
        "non-* value in*'",
        v7,
        v9);
    }
  }
}

```

## disassembly

```asm
0x18008f958  mov     [rsp+arg_8], rbx
0x18008f95d  push    rbp
0x18008f95e  push    rsi
0x18008f95f  push    rdi
0x18008f960  push    r12
0x18008f962  push    r13
0x18008f964  push    r14
0x18008f966  push    r15
0x18008f968  sub     rsp, 40h
0x18008f96c  cmp     dword ptr [rcx+30h], 0
0x18008f970  mov     r13, rdx
0x18008f973  mov     rdi, rcx
0x18008f976  jnz     loc_18008FCB1
0x18008f97c  mov     r14, [rcx+160h]
0x18008f983  mov     r15, [rcx]
0x18008f986  mov     rcx, r15
0x18008f989  mov     rdx, [r14+60h]
0x18008f98d  call    sqlite3SchemaToIndex
0x18008f992  mov     rdx, [r15+20h]
0x18008f996  movsx   rcx, word ptr [r14+36h]
0x18008f99b  mov     rbp, [r14]
0x18008f99e  movsxd  r8, eax
0x18008f9a1  add     rbp, 10h
0x18008f9a5  shl     r8, 5
0x18008f9a9  mov     [rsp+78h+arg_0], eax
0x18008f9b0  mov     rsi, [r8+rdx]
0x18008f9b4  lea     rdx, [rcx+rcx*2]
0x18008f9b8  mov     rcx, [r14+8]
0x18008f9bc  lea     r12, [rcx+rdx*8]
0x18008f9c0  mov     rcx, r14
0x18008f9c3  lea     rdx, [r12-18h]
0x18008f9c8  call    sqlite3ColumnExpr
0x18008f9cd  mov     r8, rsi
0x18008f9d0  mov     rcx, r15
0x18008f9d3  mov     rdx, rbp
0x18008f9d6  mov     rbx, rax
0x18008f9d9  call    sqlite3FindTable
0x18008f9de  mov     r8, rsi
0x18008f9e1  mov     [rsp+78h+arg_18], rax
0x18008f9e9  mov     edx, 1Ah
0x18008f9ee  mov     [rsp+78h+var_58], 0
0x18008f9f7  mov     rcx, rdi
0x18008f9fa  mov     r9, [rax]
0x18008f9fd  call    sqlite3AuthCheck
0x18008fa02  test    eax, eax
0x18008fa04  jnz     loc_18008FCB1
0x18008fa0a  test    byte ptr [r12-6], 1
0x18008fa10  jz      short loc_18008FA26
0x18008fa12  lea     rdx, aCannotAddAPrim; "Cannot add a PRIMARY KEY column"
0x18008fa19  mov     rcx, rdi
0x18008fa1c  call    sqlite3ErrorMsg
0x18008fa21  jmp     loc_18008FCB1
0x18008fa26  cmp     qword ptr [r14+10h], 0
0x18008fa2b  jz      short loc_18008FA36
0x18008fa2d  lea     rdx, aCannotAddAUniq; "Cannot add a UNIQUE column"
0x18008fa34  jmp     short loc_18008FA19
0x18008fa36  test    byte ptr [r12-6], 60h
0x18008fa3c  jnz     loc_18008FB17
0x18008fa42  test    rbx, rbx
0x18008fa45  jz      short loc_18008FA54
0x18008fa47  mov     rcx, [rbx+10h]
0x18008fa4b  xor     eax, eax
0x18008fa4d  cmp     byte ptr [rcx], 79h ; 'y'
0x18008fa50  cmovz   rbx, rax
0x18008fa54  mov     eax, [r15+30h]
0x18008fa58  bt      rax, 0Eh
0x18008fa5d  jnb     short loc_18008FA89
0x18008fa5f  cmp     qword ptr [r14+48h], 0
0x18008fa64  jz      short loc_18008FA89
0x18008fa66  test    rbx, rbx
0x18008fa69  jz      short loc_18008FA89
0x18008fa6b  mov     r9, rsi
0x18008fa6e  mov     [rsp+78h+var_58], rbp
0x18008fa73  lea     r8, aCannotAddARefe; "Cannot add a REFERENCES column with non"...
0x18008fa7a  mov     rcx, rdi
0x18008fa7d  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x18008fa84  call    sqlite3NestedParse
0x18008fa89  test    byte ptr [r12-10h], 0Fh
0x18008fa8f  jz      short loc_18008FAA2
0x18008fa91  test    rbx, rbx
0x18008fa94  jnz     short loc_18008FAAB
0x18008fa96  lea     r8, aCannotAddANotN; "Cannot add a NOT NULL column with defau"...
0x18008fa9d  jmp     loc_18008FB26
0x18008faa2  test    rbx, rbx
0x18008faa5  jz      loc_18008FB3D
0x18008faab  lea     rax, [rsp+78h+arg_10]
0x18008fab3  mov     [rsp+78h+arg_10], 0
0x18008fabf  mov     r9b, 41h ; 'A'
0x18008fac2  mov     [rsp+78h+var_58], rax
0x18008fac7  mov     r8b, 1
0x18008faca  mov     rdx, rbx
0x18008facd  mov     rcx, r15
0x18008fad0  call    sqlite3ValueFromExpr
0x18008fad5  test    eax, eax
0x18008fad7  jnz     loc_18008FCB1
0x18008fadd  mov     rcx, [rsp+78h+arg_10]
0x18008fae5  test    rcx, rcx
0x18008fae8  jnz     short loc_18008FB10
0x18008faea  mov     r9, rsi
0x18008faed  mov     [rsp+78h+var_58], rbp
0x18008faf2  lea     r8, aCannotAddAColu_0; "Cannot add a column with non-constant d"...
0x18008faf9  mov     rcx, rdi
0x18008fafc  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x18008fb03  call    sqlite3NestedParse
0x18008fb08  mov     rcx, [rsp+78h+arg_10]
0x18008fb10  call    sqlite3ValueFree
0x18008fb15  jmp     short loc_18008FB3D
0x18008fb17  test    byte ptr [r12-6], 40h
0x18008fb1d  jz      short loc_18008FB3D
0x18008fb1f  lea     r8, aCannotAddAStor; "cannot add a STORED column"
0x18008fb26  mov     r9, rsi
0x18008fb29  mov     [rsp+78h+var_58], rbp
0x18008fb2e  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x18008fb35  mov     rcx, rdi
0x18008fb38  call    sqlite3NestedParse
0x18008fb3d  mov     r8d, [r13+8]
0x18008fb41  mov     rcx, r15
0x18008fb44  mov     rdx, [r13+0]
0x18008fb48  call    sqlite3DbStrNDup
0x18008fb4d  mov     rbx, rax
0x18008fb50  test    rax, rax
0x18008fb53  jz      short loc_18008FBB0
0x18008fb55  mov     edx, [r13+8]
0x18008fb59  dec     edx
0x18008fb5b  add     rdx, rax
0x18008fb5e  jmp     short loc_18008FB7B
0x18008fb60  cmp     byte ptr [rdx], 3Bh ; ';'
0x18008fb63  jz      short loc_18008FB75
0x18008fb65  movzx   eax, byte ptr [rdx]
0x18008fb68  lea     rcx, qword_1800B4FF0
0x18008fb6f  test    byte ptr [rax+rcx], 1
0x18008fb73  jz      short loc_18008FB80
0x18008fb75  mov     byte ptr [rdx], 0
0x18008fb78  dec     rdx
0x18008fb7b  cmp     rdx, rbx
0x18008fb7e  ja      short loc_18008FB60
0x18008fb80  mov     r9d, [r14+40h]
0x18008fb84  lea     rdx, aUpdateWSqliteM_1; "UPDATE \"%w\".sqlite_master SET sql = p"...
0x18008fb8b  mov     [rsp+78h+var_48], rbp
0x18008fb90  mov     r8, rsi
0x18008fb93  mov     [rsp+78h+var_50], r9d
0x18008fb98  mov     rcx, rdi
0x18008fb9b  mov     [rsp+78h+var_58], rbx
0x18008fba0  call    sqlite3NestedParse
0x18008fba5  mov     rdx, rbx
0x18008fba8  mov     rcx, r15
0x18008fbab  call    sqlite3DbFree
0x18008fbb0  mov     rcx, rdi
0x18008fbb3  call    sqlite3GetVdbe
0x18008fbb8  mov     r15, rax
0x18008fbbb  test    rax, rax
0x18008fbbe  jz      loc_18008FCB1
0x18008fbc4  mov     rcx, rdi
0x18008fbc7  call    sqlite3GetTempReg
0x18008fbcc  mov     r13d, [rsp+78h+arg_0]
0x18008fbd4  mov     r9d, eax
0x18008fbd7  mov     r8d, r13d
0x18008fbda  mov     dword ptr [rsp+78h+var_58], 2
0x18008fbe2  mov     edx, 63h ; 'c'
0x18008fbe7  mov     rcx, r15
0x18008fbea  mov     ebx, eax
0x18008fbec  call    sqlite3VdbeAddOp3
0x18008fbf1  mov     edx, r13d
0x18008fbf4  mov     rcx, r15
0x18008fbf7  call    sqlite3VdbeUsesBtree
0x18008fbfc  mov     r9d, 0FFFFFFFEh
0x18008fc02  mov     dword ptr [rsp+78h+var_58], 0
0x18008fc0a  mov     r8d, ebx
0x18008fc0d  lea     edx, [r9+58h]
0x18008fc11  call    sqlite3VdbeAddOp3
0x18008fc16  mov     r9d, [r15+90h]
0x18008fc1d  mov     r8d, ebx
0x18008fc20  add     r9d, 2
0x18008fc24  mov     dword ptr [rsp+78h+var_58], 0
0x18008fc2c  mov     edx, 3Bh ; ';'
0x18008fc31  mov     rcx, r15
0x18008fc34  call    sqlite3VdbeAddOp3
0x18008fc39  mov     r9d, 2
0x18008fc3f  mov     dword ptr [rsp+78h+var_58], 3
0x18008fc47  mov     r8d, r13d
0x18008fc4a  mov     rcx, r15
0x18008fc4d  lea     edx, [r9+62h]
0x18008fc51  call    sqlite3VdbeAddOp3
0x18008fc56  mov     edx, ebx
0x18008fc58  mov     rcx, rdi
0x18008fc5b  call    sqlite3ReleaseTempReg
0x18008fc60  mov     r8d, 3
0x18008fc66  mov     edx, r13d
0x18008fc69  call    renameReloadSchema
0x18008fc6e  cmp     qword ptr [r14+20h], 0
0x18008fc73  jnz     short loc_18008FC9C
0x18008fc75  test    byte ptr [r12-10h], 0Fh
0x18008fc7b  setnz   cl
0x18008fc7e  test    byte ptr [r12-6], 60h
0x18008fc84  setnz   al
0x18008fc87  test    al, cl
0x18008fc89  jnz     short loc_18008FC9C
0x18008fc8b  mov     rax, [rsp+78h+arg_18]
0x18008fc93  test    dword ptr [rax+30h], 10000h
0x18008fc9a  jz      short loc_18008FCB1
0x18008fc9c  mov     r9, rsi
0x18008fc9f  lea     rdx, aSelectCaseWhen; "SELECT CASE WHEN quick_check GLOB 'CHEC"...
0x18008fca6  mov     r8, rbp
0x18008fca9  mov     rcx, rdi
0x18008fcac  call    sqlite3NestedParse
0x18008fcb1  mov     rbx, [rsp+78h+arg_8]
0x18008fcb9  add     rsp, 40h
0x18008fcbd  pop     r15
0x18008fcbf  pop     r14
0x18008fcc1  pop     r13
0x18008fcc3  pop     r12
0x18008fcc5  pop     rdi
0x18008fcc6  pop     rsi
0x18008fcc7  pop     rbp
0x18008fcc8  retn
```
