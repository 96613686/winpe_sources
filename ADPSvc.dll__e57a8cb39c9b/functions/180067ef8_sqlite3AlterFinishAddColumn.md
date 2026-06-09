# sqlite3AlterFinishAddColumn

- ea: `0x180067ef8`
- end: `0x18006829d`
- name: `sqlite3AlterFinishAddColumn`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1800c3bd8`

## callees

- `0x180061040`
- `0x180067ef8`
- `0x1800693b0`
- `0x18006f18c`
- `0x1800716fc`
- `0x180071aac`
- `0x180073aec`
- `0x180078c74`
- `0x18007d478`
- `0x1800817f4`
- `0x180092224`
- `0x1800923d8`
- `0x18009d734`
- `0x1800b3298`

## string_xrefs

- `0x180068145`: `UPDATE "%w".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql))) WHERE type = 'table' AND name = %Q`

## pseudocode

```c
void __fastcall sqlite3AlterFinishAddColumn(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r14
  int v6; // esi
  __int64 v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r12
  __int64 v11; // r15
  __int64 v12; // r13
  __int64 v13; // rdi
  int v14; // r8d
  int v15; // r9d
  const char *v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // rax
  _BYTE *i; // rdx
  __int64 Vdbe; // rbp
  char v21; // cl
  int v22; // edi
  unsigned __int8 v23; // cl
  int v24; // ecx
  __int64 v25; // [rsp+80h] [rbp+8h] BYREF
  __int64 v26; // [rsp+88h] [rbp+10h]
  __int64 Table; // [rsp+90h] [rbp+18h]

  v26 = a2;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = *(_QWORD *)(a1 + 352);
    v6 = -32768;
    v7 = *(_QWORD *)a1;
    v8 = *(_QWORD *)(v5 + 96);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v7 + 32);
      v6 = 0;
      if ( *(_QWORD *)(v9 + 24) != v8 )
      {
        do
          ++v6;
        while ( *(_QWORD *)(32LL * v6 + v9 + 24) != v8 );
      }
    }
    v10 = *(_QWORD *)v5 + 16LL;
    v11 = *(_QWORD *)(32LL * v6 + *(_QWORD *)(v7 + 32));
    v12 = *(_QWORD *)(v5 + 8) + 24LL * *(__int16 *)(v5 + 54);
    v13 = sqlite3ColumnExpr(v5, v12 - 24, a3, a4);
    Table = sqlite3FindTable(v7, v10, v11);
    if ( !(unsigned int)sqlite3AuthCheck(a1, 26, v11, *(_QWORD *)Table, 0) )
    {
      if ( (*(_BYTE *)(v12 - 6) & 1) != 0 )
      {
        sqlite3ErrorMsg(a1, "Cannot add a PRIMARY KEY column");
        return;
      }
      if ( *(_QWORD *)(v5 + 16) )
      {
        sqlite3ErrorMsg(a1, "Cannot add a UNIQUE column");
        return;
      }
      if ( (*(_BYTE *)(v12 - 6) & 0x60) != 0 )
      {
        if ( (*(_BYTE *)(v12 - 6) & 0x40) != 0 )
        {
          v16 = "cannot add a STORED column";
          goto LABEL_29;
        }
      }
      else
      {
        if ( v13 && **(_BYTE **)(v13 + 16) == 121 )
          v13 = 0;
        if ( (*(_DWORD *)(v7 + 48) & 0x4000LL) != 0 && *(_QWORD *)(v5 + 72) && v13 )
          sqlite3NestedParse(
            a1,
            "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
            "Cannot add a REFERENCES column with non-NULL default value",
            v11,
            v10);
        if ( (*(_BYTE *)(v12 - 16) & 0xF) != 0 )
        {
          if ( !v13 )
          {
            v16 = "Cannot add a NOT NULL column with default value NULL";
LABEL_29:
            sqlite3NestedParse(a1, "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"", v16, v11, v10);
            goto LABEL_30;
          }
LABEL_23:
          v25 = 0;
          LOBYTE(v15) = 65;
          LOBYTE(v14) = 1;
          if ( (unsigned int)valueFromExpr(v7, v13, v14, v15, (__int64)&v25) )
            return;
          v17 = v25;
          if ( !v25 )
          {
            sqlite3NestedParse(
              a1,
              "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
              "Cannot add a column with non-constant default",
              v11,
              v10);
            v17 = v25;
          }
          sqlite3ValueFree(v17);
          goto LABEL_30;
        }
        if ( v13 )
          goto LABEL_23;
      }
LABEL_30:
      v18 = sqlite3DbStrNDup(v7, *(_QWORD *)v26, *(unsigned int *)(v26 + 8));
      if ( v18 )
      {
        for ( i = (_BYTE *)(v18 + (unsigned int)(*(_DWORD *)(v26 + 8) - 1));
              (unsigned __int64)i > v18 && (*i == 59 || (*((_BYTE *)&qword_1800FB500 + (unsigned __int8)*i) & 1) != 0);
              --i )
        {
          *i = 0;
        }
        sqlite3NestedParse(
          a1,
          "UPDATE \"%w\".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql)"
          ")) WHERE type = 'table' AND name = %Q",
          v11);
        sqlite3DbFreeNN(v7);
      }
      Vdbe = sqlite3GetVdbe(a1);
      if ( Vdbe )
      {
        v21 = *(_BYTE *)(a1 + 31);
        if ( v21 )
        {
          v23 = v21 - 1;
          *(_BYTE *)(a1 + 31) = v23;
          v22 = *(_DWORD *)(a1 + 4LL * v23 + 232);
        }
        else
        {
          v22 = ++*(_DWORD *)(a1 + 56);
        }
        sqlite3VdbeAddOp3(Vdbe, 99, v6, v22, 2);
        sqlite3VdbeUsesBtree(Vdbe, (unsigned int)v6);
        sqlite3VdbeAddOp3(v24, 86, v22, -2, 0);
        sqlite3VdbeAddOp3(Vdbe, 59, v22, *(_DWORD *)(Vdbe + 144) + 2, 0);
        sqlite3VdbeAddOp3(Vdbe, 100, v6, 2, 3);
        if ( v22 && *(_BYTE *)(a1 + 31) < 8u )
          *(_DWORD *)(a1 + 4LL * (unsigned __int8)(*(_BYTE *)(a1 + 31))++ + 232) = v22;
        renameReloadSchema(a1, (unsigned int)v6, 3);
        if ( *(_QWORD *)(v5 + 32)
          || (*(_BYTE *)(v12 - 16) & 0xF) != 0 && (*(_BYTE *)(v12 - 6) & 0x60) != 0
          || (*(_DWORD *)(Table + 48) & 0x10000) != 0 )
        {
          sqlite3NestedParse(
            a1,
            "SELECT CASE WHEN quick_check GLOB 'CHECK*' THEN raise(ABORT,'CHECK constraint failed') WHEN quick_check GLOB"
            " 'non-* value in*' THEN raise(ABORT,'type mismatch on DEFAULT') ELSE raise(ABORT,'NOT NULL constraint failed"
            "') END  FROM pragma_quick_check(%Q,%Q) WHERE quick_check GLOB 'CHECK*' OR quick_check GLOB 'NULL*' OR quick_"
            "check GLOB 'non-* value in*'",
            v10,
            v11);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180067ef8  mov     [rsp+arg_18], rbx
0x180067efd  mov     [rsp+arg_8], rdx
0x180067f02  push    rbp
0x180067f03  push    rsi
0x180067f04  push    rdi
0x180067f05  push    r12
0x180067f07  push    r13
0x180067f09  push    r14
0x180067f0b  push    r15
0x180067f0d  sub     rsp, 40h
0x180067f11  cmp     dword ptr [rcx+30h], 0
0x180067f15  mov     rbx, rcx
0x180067f18  jnz     loc_180068285
0x180067f1e  mov     r14, [rcx+160h]
0x180067f25  mov     esi, 0FFFF8000h
0x180067f2a  mov     rbp, [rcx]
0x180067f2d  mov     rcx, [r14+60h]
0x180067f31  test    rcx, rcx
0x180067f34  jz      short loc_180067F52
0x180067f36  mov     rdx, [rbp+20h]
0x180067f3a  xor     esi, esi
0x180067f3c  cmp     [rdx+18h], rcx
0x180067f40  jz      short loc_180067F52
0x180067f42  inc     esi
0x180067f44  movsxd  rax, esi
0x180067f47  shl     rax, 5
0x180067f4b  cmp     [rax+rdx+18h], rcx
0x180067f50  jnz     short loc_180067F42
0x180067f52  mov     rax, [rbp+20h]
0x180067f56  mov     r12, [r14]
0x180067f59  movsxd  rcx, esi
0x180067f5c  add     r12, 10h
0x180067f60  shl     rcx, 5
0x180067f64  mov     r15, [rcx+rax]
0x180067f68  movsx   rax, word ptr [r14+36h]
0x180067f6d  lea     rcx, [rax+rax*2]
0x180067f71  mov     rax, [r14+8]
0x180067f75  lea     r13, [rax+rcx*8]
0x180067f79  mov     rcx, r14
0x180067f7c  lea     rdx, [r13-18h]
0x180067f80  call    sqlite3ColumnExpr
0x180067f85  mov     rcx, rbp
0x180067f88  mov     r8, r15
0x180067f8b  mov     rdx, r12
0x180067f8e  mov     rdi, rax
0x180067f91  call    sqlite3FindTable
0x180067f96  mov     r8, r15
0x180067f99  mov     [rsp+78h+arg_10], rax
0x180067fa1  mov     edx, 1Ah
0x180067fa6  mov     [rsp+78h+var_58], 0
0x180067faf  mov     rcx, rbx
0x180067fb2  mov     r9, [rax]
0x180067fb5  call    sqlite3AuthCheck
0x180067fba  test    eax, eax
0x180067fbc  jnz     loc_180068285
0x180067fc2  test    byte ptr [r13-6], 1
0x180067fc7  jz      short loc_180067FDD
0x180067fc9  lea     rdx, aCannotAddAPrim; "Cannot add a PRIMARY KEY column"
0x180067fd0  mov     rcx, rbx
0x180067fd3  call    sqlite3ErrorMsg
0x180067fd8  jmp     loc_180068285
0x180067fdd  cmp     qword ptr [r14+10h], 0
0x180067fe2  jz      short loc_180067FED
0x180067fe4  lea     rdx, aCannotAddAUniq; "Cannot add a UNIQUE column"
0x180067feb  jmp     short loc_180067FD0
0x180067fed  test    byte ptr [r13-6], 60h
0x180067ff2  jnz     loc_1800680CB
0x180067ff8  test    rdi, rdi
0x180067ffb  jz      short loc_18006800A
0x180067ffd  mov     rcx, [rdi+10h]
0x180068001  xor     eax, eax
0x180068003  cmp     byte ptr [rcx], 79h ; 'y'
0x180068006  cmovz   rdi, rax
0x18006800a  mov     eax, [rbp+30h]
0x18006800d  bt      rax, 0Eh
0x180068012  jnb     short loc_18006803E
0x180068014  cmp     qword ptr [r14+48h], 0
0x180068019  jz      short loc_18006803E
0x18006801b  test    rdi, rdi
0x18006801e  jz      short loc_18006803E
0x180068020  mov     r9, r15
0x180068023  mov     [rsp+78h+var_58], r12
0x180068028  lea     r8, aCannotAddARefe; "Cannot add a REFERENCES column with non"...
0x18006802f  mov     rcx, rbx
0x180068032  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x180068039  call    sqlite3NestedParse
0x18006803e  test    byte ptr [r13-10h], 0Fh
0x180068043  jz      short loc_180068056
0x180068045  test    rdi, rdi
0x180068048  jnz     short loc_18006805F
0x18006804a  lea     r8, aCannotAddANotN; "Cannot add a NOT NULL column with defau"...
0x180068051  jmp     loc_1800680D9
0x180068056  test    rdi, rdi
0x180068059  jz      loc_1800680F0
0x18006805f  lea     rax, [rsp+78h+arg_0]
0x180068067  mov     [rsp+78h+arg_0], 0
0x180068073  mov     r9b, 41h ; 'A'
0x180068076  mov     [rsp+78h+var_58], rax
0x18006807b  mov     r8b, 1
0x18006807e  mov     rdx, rdi
0x180068081  mov     rcx, rbp
0x180068084  call    valueFromExpr
0x180068089  test    eax, eax
0x18006808b  jnz     loc_180068285
0x180068091  mov     rcx, [rsp+78h+arg_0]
0x180068099  test    rcx, rcx
0x18006809c  jnz     short loc_1800680C4
0x18006809e  mov     r9, r15
0x1800680a1  mov     [rsp+78h+var_58], r12
0x1800680a6  lea     r8, aCannotAddAColu_0; "Cannot add a column with non-constant d"...
0x1800680ad  mov     rcx, rbx
0x1800680b0  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x1800680b7  call    sqlite3NestedParse
0x1800680bc  mov     rcx, [rsp+78h+arg_0]
0x1800680c4  call    sqlite3ValueFree
0x1800680c9  jmp     short loc_1800680F0
0x1800680cb  test    byte ptr [r13-6], 40h
0x1800680d0  jz      short loc_1800680F0
0x1800680d2  lea     r8, aCannotAddAStor; "cannot add a STORED column"
0x1800680d9  mov     r9, r15
0x1800680dc  mov     [rsp+78h+var_58], r12
0x1800680e1  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x1800680e8  mov     rcx, rbx
0x1800680eb  call    sqlite3NestedParse
0x1800680f0  mov     rax, [rsp+78h+arg_8]
0x1800680f8  mov     rcx, rbp
0x1800680fb  mov     r8d, [rax+8]
0x1800680ff  mov     rdx, [rax]
0x180068102  call    sqlite3DbStrNDup
0x180068107  mov     rdi, rax
0x18006810a  test    rax, rax
0x18006810d  jz      short loc_180068171
0x18006810f  mov     rdx, [rsp+78h+arg_8]
0x180068117  mov     edx, [rdx+8]
0x18006811a  dec     edx
0x18006811c  add     rdx, rax
0x18006811f  jmp     short loc_18006813C
0x180068121  cmp     byte ptr [rdx], 3Bh ; ';'
0x180068124  jz      short loc_180068136
0x180068126  movzx   eax, byte ptr [rdx]
0x180068129  lea     rcx, qword_1800FB500
0x180068130  test    byte ptr [rax+rcx], 1
0x180068134  jz      short loc_180068141
0x180068136  mov     byte ptr [rdx], 0
0x180068139  dec     rdx
0x18006813c  cmp     rdx, rdi
0x18006813f  ja      short loc_180068121
0x180068141  mov     r9d, [r14+40h]
0x180068145  lea     rdx, aUpdateWSqliteM_1; "UPDATE \"%w\".sqlite_master SET sql = p"...
0x18006814c  mov     [rsp+78h+var_48], r12
0x180068151  mov     r8, r15
0x180068154  mov     [rsp+78h+var_50], r9d
0x180068159  mov     rcx, rbx
0x18006815c  mov     [rsp+78h+var_58], rdi
0x180068161  call    sqlite3NestedParse
0x180068166  mov     rdx, rdi
0x180068169  mov     rcx, rbp
0x18006816c  call    sqlite3DbFreeNN
0x180068171  mov     rcx, rbx
0x180068174  call    sqlite3GetVdbe
0x180068179  mov     rbp, rax
0x18006817c  test    rax, rax
0x18006817f  jz      loc_180068285
0x180068185  mov     cl, [rbx+1Fh]
0x180068188  test    cl, cl
0x18006818a  jnz     short loc_180068194
0x18006818c  inc     dword ptr [rbx+38h]
0x18006818f  mov     edi, [rbx+38h]
0x180068192  jmp     short loc_1800681A3
0x180068194  dec     cl
0x180068196  movzx   eax, cl
0x180068199  mov     [rbx+1Fh], al
0x18006819c  mov     edi, [rbx+rax*4+0E8h]
0x1800681a3  mov     r9d, edi
0x1800681a6  mov     dword ptr [rsp+78h+var_58], 2
0x1800681ae  mov     r8d, esi
0x1800681b1  mov     edx, 63h ; 'c'
0x1800681b6  mov     rcx, rbp
0x1800681b9  call    sqlite3VdbeAddOp3
0x1800681be  mov     edx, esi
0x1800681c0  mov     rcx, rbp
0x1800681c3  call    sqlite3VdbeUsesBtree
0x1800681c8  mov     r9d, 0FFFFFFFEh
0x1800681ce  mov     dword ptr [rsp+78h+var_58], 0
0x1800681d6  mov     r8d, edi
0x1800681d9  lea     edx, [r9+58h]
0x1800681dd  call    sqlite3VdbeAddOp3
0x1800681e2  mov     r9d, [rbp+90h]
0x1800681e9  mov     r8d, edi
0x1800681ec  add     r9d, 2
0x1800681f0  mov     dword ptr [rsp+78h+var_58], 0
0x1800681f8  mov     edx, 3Bh ; ';'
0x1800681fd  mov     rcx, rbp
0x180068200  call    sqlite3VdbeAddOp3
0x180068205  mov     r9d, 2
0x18006820b  mov     dword ptr [rsp+78h+var_58], 3
0x180068213  mov     r8d, esi
0x180068216  mov     rcx, rbp
0x180068219  lea     edx, [r9+62h]
0x18006821d  call    sqlite3VdbeAddOp3
0x180068222  test    edi, edi
0x180068224  jz      short loc_18006823A
0x180068226  cmp     byte ptr [rbx+1Fh], 8
0x18006822a  jnb     short loc_18006823A
0x18006822c  movzx   eax, byte ptr [rbx+1Fh]
0x180068230  mov     [rbx+rax*4+0E8h], edi
0x180068237  inc     byte ptr [rbx+1Fh]
0x18006823a  mov     r8d, 3
0x180068240  mov     edx, esi
0x180068242  mov     rcx, rbx
0x180068245  call    renameReloadSchema
0x18006824a  cmp     qword ptr [r14+20h], 0
0x18006824f  jnz     short loc_180068270
0x180068251  test    byte ptr [r13-10h], 0Fh
0x180068256  jz      short loc_18006825F
0x180068258  test    byte ptr [r13-6], 60h
0x18006825d  jnz     short loc_180068270
0x18006825f  mov     rax, [rsp+78h+arg_10]
0x180068267  test    dword ptr [rax+30h], 10000h
0x18006826e  jz      short loc_180068285
0x180068270  mov     r9, r15
0x180068273  lea     rdx, aSelectCaseWhen; "SELECT CASE WHEN quick_check GLOB 'CHEC"...
0x18006827a  mov     r8, r12
0x18006827d  mov     rcx, rbx
0x180068280  call    sqlite3NestedParse
0x180068285  mov     rbx, [rsp+78h+arg_18]
0x18006828d  add     rsp, 40h
0x180068291  pop     r15
0x180068293  pop     r14
0x180068295  pop     r13
0x180068297  pop     r12
0x180068299  pop     rdi
0x18006829a  pop     rsi
0x18006829b  pop     rbp
0x18006829c  retn
```
