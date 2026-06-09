# sqlite3AlterFinishAddColumn

- ea: `0x180080628`
- end: `0x180080999`
- name: `sqlite3AlterFinishAddColumn`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x180031b38`

## callees

- `0x18000a7a0`
- `0x18000a9e0`
- `0x180010810`
- `0x1800119e0`
- `0x180014434`
- `0x180034bec`
- `0x1800398f0`
- `0x18003f6dc`
- `0x18003ff00`
- `0x180048130`
- `0x18004cfa0`
- `0x18004d11c`
- `0x180060ce8`
- `0x18006170c`
- `0x18007e1ac`
- `0x180080628`
- `0x1800857c4`

## string_xrefs

- `0x180080854`: `UPDATE "%w".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql))) WHERE type = 'table' AND name = %Q`

## pseudocode

```c
void __fastcall sqlite3AlterFinishAddColumn(_QWORD *a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // r15
  unsigned int v6; // eax
  _BYTE *v7; // rbp
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

  if ( *((_DWORD *)a1 + 13) )
    return;
  v4 = a1[44];
  v5 = *a1;
  v6 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v4 + 96));
  v7 = (_BYTE *)(*(_QWORD *)v4 + 16LL);
  v21 = v6;
  v8 = *(_QWORD *)(32LL * (int)v6 + *(_QWORD *)(v5 + 32));
  v9 = *(_QWORD *)(v4 + 8) + 24LL * *(__int16 *)(v4 + 54);
  v10 = sqlite3ColumnExpr(v4);
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
    if ( v10 && **(_BYTE **)(v10 + 16) == 122 )
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
          (unsigned __int64)i > v14 && (*i == 59 || (*((_BYTE *)&qword_18009E630 + (unsigned __int8)*i) & 1) != 0);
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
    sqlite3VdbeAddOp3(Vdbe, 50, TempReg, *(_DWORD *)(Vdbe + 144) + 2, 0);
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
0x180080628  mov     [rsp+arg_8], rbx
0x18008062d  push    rbp
0x18008062e  push    rsi
0x18008062f  push    rdi
0x180080630  push    r12
0x180080632  push    r13
0x180080634  push    r14
0x180080636  push    r15
0x180080638  sub     rsp, 40h
0x18008063c  cmp     dword ptr [rcx+34h], 0
0x180080640  mov     r13, rdx
0x180080643  mov     rdi, rcx
0x180080646  jnz     loc_180080981
0x18008064c  mov     r14, [rcx+160h]
0x180080653  mov     r15, [rcx]
0x180080656  mov     rcx, r15
0x180080659  mov     rdx, [r14+60h]
0x18008065d  call    sqlite3SchemaToIndex
0x180080662  mov     rdx, [r15+20h]
0x180080666  movsx   rcx, word ptr [r14+36h]
0x18008066b  mov     rbp, [r14]
0x18008066e  movsxd  r8, eax
0x180080671  add     rbp, 10h
0x180080675  shl     r8, 5
0x180080679  mov     [rsp+78h+arg_0], eax
0x180080680  mov     rsi, [r8+rdx]
0x180080684  lea     rdx, [rcx+rcx*2]
0x180080688  mov     rcx, [r14+8]
0x18008068c  lea     r12, [rcx+rdx*8]
0x180080690  mov     rcx, r14
0x180080693  lea     rdx, [r12-18h]
0x180080698  call    sqlite3ColumnExpr
0x18008069d  mov     rcx, r15
0x1800806a0  mov     r8, rsi
0x1800806a3  mov     rdx, rbp
0x1800806a6  mov     rbx, rax
0x1800806a9  call    sqlite3FindTable
0x1800806ae  mov     r8, rsi
0x1800806b1  mov     [rsp+78h+arg_18], rax
0x1800806b9  mov     edx, 1Ah
0x1800806be  mov     [rsp+78h+var_58], 0
0x1800806c7  mov     rcx, rdi
0x1800806ca  mov     r9, [rax]
0x1800806cd  call    sqlite3AuthCheck
0x1800806d2  test    eax, eax
0x1800806d4  jnz     loc_180080981
0x1800806da  test    byte ptr [r12-6], 1
0x1800806e0  jz      short loc_1800806F6
0x1800806e2  lea     rdx, aCannotAddAPrim; "Cannot add a PRIMARY KEY column"
0x1800806e9  mov     rcx, rdi
0x1800806ec  call    sqlite3ErrorMsg
0x1800806f1  jmp     loc_180080981
0x1800806f6  cmp     qword ptr [r14+10h], 0
0x1800806fb  jz      short loc_180080706
0x1800806fd  lea     rdx, aCannotAddAUniq; "Cannot add a UNIQUE column"
0x180080704  jmp     short loc_1800806E9
0x180080706  test    byte ptr [r12-6], 60h
0x18008070c  jnz     loc_1800807E7
0x180080712  test    rbx, rbx
0x180080715  jz      short loc_180080724
0x180080717  mov     rcx, [rbx+10h]
0x18008071b  xor     eax, eax
0x18008071d  cmp     byte ptr [rcx], 7Ah ; 'z'
0x180080720  cmovz   rbx, rax
0x180080724  mov     eax, [r15+30h]
0x180080728  bt      rax, 0Eh
0x18008072d  jnb     short loc_180080759
0x18008072f  cmp     qword ptr [r14+48h], 0
0x180080734  jz      short loc_180080759
0x180080736  test    rbx, rbx
0x180080739  jz      short loc_180080759
0x18008073b  mov     r9, rsi
0x18008073e  mov     [rsp+78h+var_58], rbp
0x180080743  lea     r8, aCannotAddARefe; "Cannot add a REFERENCES column with non"...
0x18008074a  mov     rcx, rdi
0x18008074d  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x180080754  call    sqlite3NestedParse
0x180080759  test    byte ptr [r12-10h], 0Fh
0x18008075f  jz      short loc_180080772
0x180080761  test    rbx, rbx
0x180080764  jnz     short loc_18008077B
0x180080766  lea     r8, aCannotAddANotN; "Cannot add a NOT NULL column with defau"...
0x18008076d  jmp     loc_1800807F6
0x180080772  test    rbx, rbx
0x180080775  jz      loc_18008080D
0x18008077b  lea     rax, [rsp+78h+arg_10]
0x180080783  mov     [rsp+78h+arg_10], 0
0x18008078f  mov     r9b, 41h ; 'A'
0x180080792  mov     [rsp+78h+var_58], rax
0x180080797  mov     r8b, 1
0x18008079a  mov     rdx, rbx
0x18008079d  mov     rcx, r15
0x1800807a0  call    sqlite3ValueFromExpr
0x1800807a5  test    eax, eax
0x1800807a7  jnz     loc_180080981
0x1800807ad  mov     rcx, [rsp+78h+arg_10]
0x1800807b5  test    rcx, rcx
0x1800807b8  jnz     short loc_1800807E0
0x1800807ba  mov     r9, rsi
0x1800807bd  mov     [rsp+78h+var_58], rbp
0x1800807c2  lea     r8, aCannotAddAColu_0; "Cannot add a column with non-constant d"...
0x1800807c9  mov     rcx, rdi
0x1800807cc  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x1800807d3  call    sqlite3NestedParse
0x1800807d8  mov     rcx, [rsp+78h+arg_10]
0x1800807e0  call    sqlite3ValueFree
0x1800807e5  jmp     short loc_18008080D
0x1800807e7  test    byte ptr [r12-6], 40h
0x1800807ed  jz      short loc_18008080D
0x1800807ef  lea     r8, aCannotAddAStor; "cannot add a STORED column"
0x1800807f6  mov     r9, rsi
0x1800807f9  mov     [rsp+78h+var_58], rbp
0x1800807fe  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x180080805  mov     rcx, rdi
0x180080808  call    sqlite3NestedParse
0x18008080d  mov     r8d, [r13+8]
0x180080811  mov     rcx, r15
0x180080814  mov     rdx, [r13+0]
0x180080818  call    sqlite3DbStrNDup
0x18008081d  mov     rbx, rax
0x180080820  test    rax, rax
0x180080823  jz      short loc_180080880
0x180080825  mov     edx, [r13+8]
0x180080829  dec     edx
0x18008082b  add     rdx, rax
0x18008082e  jmp     short loc_18008084B
0x180080830  cmp     byte ptr [rdx], 3Bh ; ';'
0x180080833  jz      short loc_180080845
0x180080835  movzx   eax, byte ptr [rdx]
0x180080838  lea     rcx, qword_18009E630
0x18008083f  test    byte ptr [rax+rcx], 1
0x180080843  jz      short loc_180080850
0x180080845  mov     byte ptr [rdx], 0
0x180080848  dec     rdx
0x18008084b  cmp     rdx, rbx
0x18008084e  ja      short loc_180080830
0x180080850  mov     r9d, [r14+40h]
0x180080854  lea     rdx, aUpdateWSqliteM_1; "UPDATE \"%w\".sqlite_master SET sql = p"...
0x18008085b  mov     [rsp+78h+var_48], rbp
0x180080860  mov     r8, rsi
0x180080863  mov     [rsp+78h+var_50], r9d
0x180080868  mov     rcx, rdi
0x18008086b  mov     [rsp+78h+var_58], rbx
0x180080870  call    sqlite3NestedParse
0x180080875  mov     rdx, rbx
0x180080878  mov     rcx, r15
0x18008087b  call    sqlite3DbFree
0x180080880  mov     rcx, rdi
0x180080883  call    sqlite3GetVdbe
0x180080888  mov     r15, rax
0x18008088b  test    rax, rax
0x18008088e  jz      loc_180080981
0x180080894  mov     rcx, rdi
0x180080897  call    sqlite3GetTempReg
0x18008089c  mov     r13d, [rsp+78h+arg_0]
0x1800808a4  mov     r9d, eax
0x1800808a7  mov     r8d, r13d
0x1800808aa  mov     dword ptr [rsp+78h+var_58], 2
0x1800808b2  mov     edx, 63h ; 'c'
0x1800808b7  mov     rcx, r15
0x1800808ba  mov     ebx, eax
0x1800808bc  call    sqlite3VdbeAddOp3
0x1800808c1  mov     edx, r13d
0x1800808c4  mov     rcx, r15
0x1800808c7  call    sqlite3VdbeUsesBtree
0x1800808cc  mov     r9d, 0FFFFFFFEh
0x1800808d2  mov     dword ptr [rsp+78h+var_58], 0
0x1800808da  mov     r8d, ebx
0x1800808dd  lea     edx, [r9+58h]
0x1800808e1  call    sqlite3VdbeAddOp3
0x1800808e6  mov     r9d, [r15+90h]
0x1800808ed  mov     r8d, ebx
0x1800808f0  add     r9d, 2
0x1800808f4  mov     dword ptr [rsp+78h+var_58], 0
0x1800808fc  mov     edx, 32h ; '2'
0x180080901  mov     rcx, r15
0x180080904  call    sqlite3VdbeAddOp3
0x180080909  mov     r9d, 2
0x18008090f  mov     dword ptr [rsp+78h+var_58], 3
0x180080917  mov     r8d, r13d
0x18008091a  mov     rcx, r15
0x18008091d  lea     edx, [r9+62h]
0x180080921  call    sqlite3VdbeAddOp3
0x180080926  mov     edx, ebx
0x180080928  mov     rcx, rdi
0x18008092b  call    sqlite3ReleaseTempReg
0x180080930  mov     r8d, 3
0x180080936  mov     edx, r13d
0x180080939  call    renameReloadSchema
0x18008093e  cmp     qword ptr [r14+20h], 0
0x180080943  jnz     short loc_18008096C
0x180080945  test    byte ptr [r12-10h], 0Fh
0x18008094b  setnz   cl
0x18008094e  test    byte ptr [r12-6], 60h
0x180080954  setnz   al
0x180080957  test    al, cl
0x180080959  jnz     short loc_18008096C
0x18008095b  mov     rax, [rsp+78h+arg_18]
0x180080963  test    dword ptr [rax+30h], 10000h
0x18008096a  jz      short loc_180080981
0x18008096c  mov     r9, rsi
0x18008096f  lea     rdx, aSelectCaseWhen; "SELECT CASE WHEN quick_check GLOB 'CHEC"...
0x180080976  mov     r8, rbp
0x180080979  mov     rcx, rdi
0x18008097c  call    sqlite3NestedParse
0x180080981  mov     rbx, [rsp+78h+arg_8]
0x180080989  add     rsp, 40h
0x18008098d  pop     r15
0x18008098f  pop     r14
0x180080991  pop     r13
0x180080993  pop     r12
0x180080995  pop     rdi
0x180080996  pop     rsi
0x180080997  pop     rbp
0x180080998  retn
```
