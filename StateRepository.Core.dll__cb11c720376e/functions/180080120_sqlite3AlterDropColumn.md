# sqlite3AlterDropColumn

- ea: `0x180080120`
- end: `0x180080621`
- name: `sqlite3AlterDropColumn`
- size: `1281`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x180031b38`

## callees

- `0x180005c54`
- `0x18000a9e0`
- `0x18000ca30`
- `0x18000fd7c`
- `0x180010810`
- `0x1800119e0`
- `0x180013bc0`
- `0x1800351c8`
- `0x180036688`
- `0x1800398f0`
- `0x18003ab18`
- `0x18003abcc`
- `0x18003f6dc`
- `0x180060ce8`
- `0x180062484`
- `0x180067de4`
- `0x18007222c`
- `0x180072788`
- `0x18007e02c`
- `0x18007e1ac`
- `0x18007ea64`
- `0x180080120`
- `0x18008299c`
- `0x1800857c4`

## string_xrefs

- `0x1800802ab`: `UPDATE "%w".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)`

## pseudocode

```c
__int64 __fastcall sqlite3AlterDropColumn(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r12
  const char *v4; // rbp
  _DWORD *v6; // rdi
  __int64 TableItem; // rax
  __int64 v8; // rsi
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r14
  __int64 v12; // rax
  const char *v13; // r8
  __int64 v14; // r13
  __int64 v15; // r15
  __int64 Vdbe; // rax
  int v17; // r15d
  __int64 v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // r13
  int v21; // r14d
  __int64 v22; // r8
  int v23; // eax
  int v24; // edx
  int v25; // r14d
  int v26; // r12d
  int v27; // ecx
  int v28; // eax
  int v29; // r15d
  int v30; // ebp
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int16 v34; // ax
  int v35; // r11d
  int v36; // r11d
  int v37; // r8d
  __int64 v38; // r8
  __int64 v39; // r9
  int v40; // ecx
  __int64 v42; // [rsp+20h] [rbp-78h]
  int v43; // [rsp+30h] [rbp-68h]
  int v44; // [rsp+34h] [rbp-64h]
  int v45; // [rsp+38h] [rbp-60h]
  unsigned int v46; // [rsp+3Ch] [rbp-5Ch]
  __int64 v47; // [rsp+48h] [rbp-50h]
  const char *v48; // [rsp+50h] [rbp-48h]
  int v51; // [rsp+B8h] [rbp+20h]
  __int64 v52; // [rsp+B8h] [rbp+20h]
  char v53; // [rsp+B8h] [rbp+20h]

  v3 = *(_QWORD *)a1;
  v4 = 0;
  v47 = *(_QWORD *)a1;
  v6 = a1;
  if ( *(_BYTE *)(*(_QWORD *)a1 + 103LL) )
    goto LABEL_48;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v8 = TableItem;
  if ( !TableItem )
    goto LABEL_48;
  if ( (unsigned int)isAlterableTable(v6, TableItem) )
    goto LABEL_48;
  if ( (unsigned int)isRealTable((__int64)v6, v8, 1) )
    goto LABEL_48;
  v9 = sqlite3NameFromToken(v3, a3);
  v48 = (const char *)v9;
  v4 = (const char *)v9;
  if ( !v9 )
    goto LABEL_48;
  v10 = sqlite3ColumnIndex(v8, v9);
  v51 = v10;
  if ( v10 < 0 )
  {
    sqlite3ErrorMsg(v6, "no such column: \"%T\"", a3);
    goto LABEL_48;
  }
  v11 = 3LL * v10;
  v12 = *(_QWORD *)(v8 + 8);
  if ( (*(_BYTE *)(v12 + 8 * v11 + 18) & 9) != 0 )
  {
    v13 = "PRIMARY KEY";
    if ( (*(_BYTE *)(v12 + 8 * v11 + 18) & 1) == 0 )
      v13 = "UNIQUE";
    sqlite3ErrorMsg(v6, "cannot drop %s column: \"%s\"", v13, v4);
    goto LABEL_48;
  }
  if ( *(__int16 *)(v8 + 54) <= 1 )
  {
    sqlite3ErrorMsg(v6, "cannot drop column \"%s\": no other columns exist", v4);
    goto LABEL_48;
  }
  v14 = (int)sqlite3SchemaToIndex(v3, *(_QWORD *)(v8 + 96));
  v15 = *(_QWORD *)(32 * v14 + *(_QWORD *)(v3 + 32));
  if ( !(unsigned int)sqlite3AuthCheck((_DWORD)v6, 26, v15, *(_QWORD *)v8, (__int64)v4) )
  {
    renameTestSchema((__int64)v6, v15, v14 == 1, (__int64)qword_18009EEF0, 0);
    renameFixQuotes((__int64)v6, v15, v14 == 1);
    LODWORD(v42) = v51;
    sqlite3NestedParse(
      v6,
      "UPDATE \"%w\".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)",
      v15,
      (unsigned int)v14,
      v42,
      *(_QWORD *)v8);
    renameReloadSchema(v6, (unsigned int)v14, 2);
    renameTestSchema((__int64)v6, v15, v14 == 1, (__int64)"after drop column", 1);
    if ( !v6[13] && (*(_BYTE *)(*(_QWORD *)(v8 + 8) + 8 * v11 + 18) & 0x20) == 0 )
    {
      Vdbe = sqlite3GetVdbe(v6);
      v17 = v6[14];
      v43 = v17;
      v18 = Vdbe;
      v6[14] = v17 + 1;
      sqlite3OpenTable((_DWORD)v6, v17, v14, v8, 113);
      v19 = sqlite3VdbeAddOp3(v18, 36, v17, 0, 0);
      ++v6[15];
      v46 = v19;
      v44 = v6[15];
      if ( *(char *)(v8 + 48) < 0 )
      {
        v20 = sqlite3PrimaryKeyIndex(v8);
        v25 = 0;
        v23 = v24 + *(unsigned __int16 *)(v20 + 96);
        v6[15] = v23;
        if ( *(_WORD *)(v20 + 94) )
        {
          v26 = v24 + 1;
          do
          {
            sqlite3VdbeAddOp3(v18, 94, v17, v25, v26 + v25);
            v27 = *(unsigned __int16 *)(v20 + 94);
            ++v25;
          }
          while ( v25 < v27 );
          v23 = v6[15];
          v3 = v47;
        }
        else
        {
          LOWORD(v27) = *(_WORD *)(v20 + 94);
        }
        v21 = (unsigned __int16)v27;
      }
      else
      {
        v20 = 0;
        v21 = 0;
        sqlite3VdbeAddOp3(v18, 135, v17, v6[15], 0);
        v23 = v6[15] + *(__int16 *)(v8 + 54);
      }
      v28 = v23 + 1;
      v29 = 0;
      v6[15] = v28;
      v45 = v28;
      if ( *(__int16 *)(v8 + 54) > 0 )
      {
        v30 = v51;
        while ( 1 )
        {
          if ( v29 != v30 )
          {
            v31 = *(_QWORD *)(v8 + 8);
            v52 = v31;
            v32 = 3LL * v29;
            if ( (*(_BYTE *)(v31 + 24LL * v29 + 18) & 0x20) == 0 )
            {
              if ( !v20 )
              {
                v36 = v21;
                goto LABEL_34;
              }
              if ( (__int16)sqlite3TableColumnToIndex(v20, (unsigned __int16)v29, v22) >= (int)*(unsigned __int16 *)(v20 + 94) )
              {
                v34 = sqlite3TableColumnToIndex(v33, (unsigned __int16)v30, v22);
                v31 = v52;
                v32 = 3LL * v29;
                v36 = v35 - (v35 > v34);
LABEL_34:
                v37 = v44 + v36;
                if ( v29 == *(__int16 *)(v8 + 52) )
                {
                  sqlite3VdbeAddOp3(v18, 75, 0, v37 + 1, 0);
                }
                else
                {
                  v53 = *(_BYTE *)(v31 + 8 * v32 + 12);
                  if ( v53 == 69 )
                    *(_BYTE *)(v31 + 8 * v32 + 12) = 67;
                  sqlite3ExprCodeGetColumnOfTable(v18, v8, v43, v29, v37 + 1);
                  *(_BYTE *)(*(_QWORD *)(v8 + 8) + 24LL * v29 + 12) = v53;
                }
                ++v21;
              }
            }
          }
          if ( ++v29 >= *(__int16 *)(v8 + 54) )
          {
            v6 = a1;
            v4 = v48;
            v3 = v47;
            break;
          }
        }
      }
      if ( !v21 )
      {
        ++v6[15];
        sqlite3VdbeAddOp3(v18, 75, 0, v44 + 1, 0);
        v21 = 1;
      }
      sqlite3VdbeAddOp3(v18, 97, v44 + 1, v21, v45);
      if ( v20 )
        sqlite3VdbeAddOp4Int(v18, 138, v43, v45, v44 + 1, *(unsigned __int16 *)(v20 + 94));
      else
        sqlite3VdbeAddOp3(v18, 128, v43, v45, v44);
      sqlite3VdbeChangeP5(v18, 2, v38, v39);
      sqlite3VdbeAddOp3(v40, 39, v43, v46 + 1, 0);
      *(_DWORD *)(sqlite3VdbeGetOp(v18, v46) + 8) = *(_DWORD *)(v18 + 144);
    }
  }
LABEL_48:
  sqlite3DbFree(v3, v4);
  return sqlite3SrcListDelete(v3, a2);
}

```

## disassembly

```asm
0x180080120  mov     [rsp+arg_10], rbx
0x180080125  mov     [rsp+arg_8], rdx
0x18008012a  mov     [rsp+arg_0], rcx
0x18008012f  push    rbp
0x180080130  push    rsi
0x180080131  push    rdi
0x180080132  push    r12
0x180080134  push    r13
0x180080136  push    r14
0x180080138  push    r15
0x18008013a  sub     rsp, 60h
0x18008013e  mov     r12, [rcx]
0x180080141  xor     ebp, ebp
0x180080143  mov     rbx, r8
0x180080146  mov     [rsp+98h+var_50], r12
0x18008014b  mov     rdi, rcx
0x18008014e  cmp     [r12+67h], bpl
0x180080153  jnz     loc_1800805EF
0x180080159  lea     r8, [rdx+8]
0x18008015d  xor     edx, edx
0x18008015f  call    sqlite3LocateTableItem
0x180080164  mov     rsi, rax
0x180080167  test    rax, rax
0x18008016a  jz      loc_1800805EF
0x180080170  mov     rdx, rax
0x180080173  mov     rcx, rdi
0x180080176  call    isAlterableTable
0x18008017b  test    eax, eax
0x18008017d  jnz     loc_1800805EF
0x180080183  lea     r15d, [rbp+1]
0x180080187  mov     rdx, rsi
0x18008018a  mov     r8d, r15d
0x18008018d  mov     rcx, rdi
0x180080190  call    isRealTable
0x180080195  test    eax, eax
0x180080197  jnz     loc_1800805EF
0x18008019d  mov     rdx, rbx
0x1800801a0  mov     rcx, r12
0x1800801a3  call    sqlite3NameFromToken
0x1800801a8  mov     [rsp+98h+var_48], rax
0x1800801ad  mov     rbp, rax
0x1800801b0  test    rax, rax
0x1800801b3  jz      loc_1800805EF
0x1800801b9  mov     rdx, rax
0x1800801bc  mov     rcx, rsi
0x1800801bf  call    sqlite3ColumnIndex
0x1800801c4  mov     dword ptr [rsp+98h+arg_18], eax
0x1800801cb  test    eax, eax
0x1800801cd  jns     short loc_1800801E6
0x1800801cf  mov     r8, rbx
0x1800801d2  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x1800801d9  mov     rcx, rdi
0x1800801dc  call    sqlite3ErrorMsg
0x1800801e1  jmp     loc_1800805EF
0x1800801e6  cdqe
0x1800801e8  lea     r14, [rax+rax*2]
0x1800801ec  mov     rax, [rsi+8]
0x1800801f0  test    byte ptr [rax+r14*8+12h], 9
0x1800801f6  jz      short loc_180080226
0x1800801f8  test    [rax+r14*8+12h], r15b
0x1800801fd  lea     r8, aPrimaryKey; "PRIMARY KEY"
0x180080204  lea     rax, aUnique_0; "UNIQUE"
0x18008020b  mov     r9, rbp
0x18008020e  cmovz   r8, rax
0x180080212  lea     rdx, aCannotDropSCol; "cannot drop %s column: \"%s\""
0x180080219  mov     rcx, rdi
0x18008021c  call    sqlite3ErrorMsg
0x180080221  jmp     loc_1800805EF
0x180080226  cmp     [rsi+36h], r15w
0x18008022b  jg      short loc_180080239
0x18008022d  mov     r8, rbp
0x180080230  lea     rdx, aCannotDropColu; "cannot drop column \"%s\": no other col"...
0x180080237  jmp     short loc_1800801D9
0x180080239  mov     rdx, [rsi+60h]
0x18008023d  mov     rcx, r12
0x180080240  call    sqlite3SchemaToIndex
0x180080245  mov     rcx, [r12+20h]
0x18008024a  mov     r9, [rsi]
0x18008024d  movsxd  r13, eax
0x180080250  mov     rdx, r13
0x180080253  mov     [rsp+98h+var_78], rbp
0x180080258  shl     rdx, 5
0x18008025c  mov     r15, [rdx+rcx]
0x180080260  mov     edx, 1Ah
0x180080265  mov     r8, r15
0x180080268  mov     rcx, rdi
0x18008026b  call    sqlite3AuthCheck
0x180080270  test    eax, eax
0x180080272  jnz     loc_1800805EF
0x180080278  xor     ebx, ebx
0x18008027a  mov     dword ptr [rsp+98h+var_78], eax
0x18008027e  cmp     r13d, 1
0x180080282  lea     r9, qword_18009EEF0
0x180080289  mov     rdx, r15
0x18008028c  mov     rcx, rdi
0x18008028f  setz    bl
0x180080292  mov     r8d, ebx
0x180080295  call    renameTestSchema
0x18008029a  mov     r8d, ebx
0x18008029d  mov     rdx, r15
0x1800802a0  mov     rcx, rdi
0x1800802a3  call    renameFixQuotes
0x1800802a8  mov     rax, [rsi]
0x1800802ab  lea     rdx, aUpdateWSqliteM_0; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1800802b2  mov     [rsp+98h+var_70], rax
0x1800802b7  mov     r9d, r13d
0x1800802ba  mov     eax, dword ptr [rsp+98h+arg_18]
0x1800802c1  mov     r8, r15
0x1800802c4  mov     rcx, rdi
0x1800802c7  mov     dword ptr [rsp+98h+var_78], eax
0x1800802cb  call    sqlite3NestedParse
0x1800802d0  mov     r8d, 2
0x1800802d6  mov     edx, r13d
0x1800802d9  mov     rcx, rdi
0x1800802dc  call    renameReloadSchema
0x1800802e1  lea     r9, aAfterDropColum; "after drop column"
0x1800802e8  mov     dword ptr [rsp+98h+var_78], 1
0x1800802f0  mov     r8d, ebx
0x1800802f3  mov     rdx, r15
0x1800802f6  mov     rcx, rdi
0x1800802f9  call    renameTestSchema
0x1800802fe  cmp     dword ptr [rdi+34h], 0
0x180080302  jnz     loc_1800805EF
0x180080308  mov     rax, [rsi+8]
0x18008030c  test    byte ptr [rax+r14*8+12h], 20h
0x180080312  jnz     loc_1800805EF
0x180080318  mov     rcx, rdi
0x18008031b  call    sqlite3GetVdbe
0x180080320  mov     r15d, [rdi+38h]
0x180080324  mov     r9, rsi
0x180080327  mov     r8d, r13d
0x18008032a  mov     [rsp+98h+var_68], r15d
0x18008032f  mov     edx, r15d
0x180080332  mov     dword ptr [rsp+98h+var_78], 71h ; 'q'
0x18008033a  mov     rbx, rax
0x18008033d  lea     ecx, [r15+1]
0x180080341  mov     [rdi+38h], ecx
0x180080344  mov     rcx, rdi
0x180080347  call    sqlite3OpenTable
0x18008034c  xor     r9d, r9d
0x18008034f  mov     dword ptr [rsp+98h+var_78], 0
0x180080357  mov     r8d, r15d
0x18008035a  mov     rcx, rbx
0x18008035d  lea     edx, [r9+24h]
0x180080361  call    sqlite3VdbeAddOp3
0x180080366  inc     dword ptr [rdi+3Ch]
0x180080369  test    byte ptr [rsi+30h], 80h
0x18008036d  mov     edx, [rdi+3Ch]
0x180080370  mov     [rsp+98h+var_5C], eax
0x180080374  mov     [rsp+98h+var_64], edx
0x180080378  jnz     short loc_1800803A1
0x18008037a  mov     r9d, edx
0x18008037d  xor     r13d, r13d
0x180080380  mov     edx, 87h
0x180080385  mov     dword ptr [rsp+98h+var_78], r13d
0x18008038a  mov     r8d, r15d
0x18008038d  mov     rcx, rbx
0x180080390  xor     r14d, r14d
0x180080393  call    sqlite3VdbeAddOp3
0x180080398  movsx   eax, word ptr [rsi+36h]
0x18008039c  add     eax, [rdi+3Ch]
0x18008039f  jmp     short loc_180080400
0x1800803a1  mov     rcx, rsi
0x1800803a4  call    sqlite3PrimaryKeyIndex
0x1800803a9  mov     r13, rax
0x1800803ac  xor     r14d, r14d
0x1800803af  xor     ecx, ecx
0x1800803b1  movzx   eax, word ptr [rax+60h]
0x1800803b5  add     eax, edx
0x1800803b7  mov     [rdi+3Ch], eax
0x1800803ba  cmp     cx, [r13+5Eh]
0x1800803bf  jnb     short loc_1800803F7
0x1800803c1  lea     r12d, [rdx+1]
0x1800803c5  lea     eax, [r12+r14]
0x1800803c9  mov     r9d, r14d
0x1800803cc  mov     r8d, r15d
0x1800803cf  mov     dword ptr [rsp+98h+var_78], eax
0x1800803d3  mov     edx, 5Eh ; '^'
0x1800803d8  mov     rcx, rbx
0x1800803db  call    sqlite3VdbeAddOp3
0x1800803e0  movzx   ecx, word ptr [r13+5Eh]
0x1800803e5  inc     r14d
0x1800803e8  cmp     r14d, ecx
0x1800803eb  jl      short loc_1800803C5
0x1800803ed  mov     eax, [rdi+3Ch]
0x1800803f0  mov     r12, [rsp+98h+var_50]
0x1800803f5  jmp     short loc_1800803FC
0x1800803f7  movzx   ecx, word ptr [r13+5Eh]
0x1800803fc  movzx   r14d, cx
0x180080400  inc     eax
0x180080402  xor     r15d, r15d
0x180080405  mov     [rdi+3Ch], eax
0x180080408  mov     [rsp+98h+var_60], eax
0x18008040c  xor     eax, eax
0x18008040e  cmp     ax, [rsi+36h]
0x180080412  jge     loc_18008052F
0x180080418  mov     r12d, [rsp+98h+var_64]
0x18008041d  mov     edi, [rsp+98h+var_68]
0x180080421  mov     ebp, dword ptr [rsp+98h+arg_18]
0x180080428  cmp     r15d, ebp
0x18008042b  jz      loc_18008050D
0x180080431  mov     rdx, [rsi+8]
0x180080435  movsxd  rax, r15d
0x180080438  mov     [rsp+98h+arg_18], rdx
0x180080440  lea     rcx, [rax+rax*2]
0x180080444  test    byte ptr [rdx+rcx*8+12h], 20h
0x180080449  mov     [rsp+98h+var_58], rcx
0x18008044e  jnz     loc_18008050D
0x180080454  test    r13, r13
0x180080457  jz      short loc_18008049C
0x180080459  movzx   edx, r15w
0x18008045d  mov     rcx, r13
0x180080460  call    sqlite3TableColumnToIndex
0x180080465  movsx   r11d, ax
0x180080469  movzx   eax, word ptr [r13+5Eh]
0x18008046e  cmp     r11d, eax
0x180080471  jl      loc_18008050D
0x180080477  movzx   edx, bp
0x18008047a  call    sqlite3TableColumnToIndex
0x18008047f  mov     rdx, [rsp+98h+arg_18]
0x180080487  movsx   ecx, ax
0x18008048a  xor     eax, eax
0x18008048c  cmp     r11d, ecx
0x18008048f  mov     rcx, [rsp+98h+var_58]
0x180080494  setnle  al
0x180080497  sub     r11d, eax
0x18008049a  jmp     short loc_18008049F
0x18008049c  mov     r11d, r14d
0x18008049f  movsx   eax, word ptr [rsi+34h]
0x1800804a3  lea     r8d, [r12+r11]
0x1800804a7  cmp     r15d, eax
0x1800804aa  jnz     short loc_1800804C9
0x1800804ac  lea     r9d, [r8+1]
0x1800804b0  mov     dword ptr [rsp+98h+var_78], 0
0x1800804b8  xor     r8d, r8d
0x1800804bb  mov     rcx, rbx
0x1800804be  lea     edx, [r8+4Bh]
0x1800804c2  call    sqlite3VdbeAddOp3
0x1800804c7  jmp     short loc_18008050A
0x1800804c9  mov     al, [rdx+rcx*8+0Ch]
0x1800804cd  mov     byte ptr [rsp+98h+arg_18], al
0x1800804d4  cmp     al, 45h ; 'E'
0x1800804d6  jnz     short loc_1800804DD
0x1800804d8  mov     byte ptr [rdx+rcx*8+0Ch], 43h ; 'C'
0x1800804dd  lea     eax, [r8+1]
0x1800804e1  mov     r9d, r15d
0x1800804e4  mov     r8d, edi
0x1800804e7  mov     dword ptr [rsp+98h+var_78], eax
0x1800804eb  mov     rdx, rsi
0x1800804ee  mov     rcx, rbx
0x1800804f1  call    sqlite3ExprCodeGetColumnOfTable
0x1800804f6  mov     rax, [rsi+8]
0x1800804fa  mov     rcx, [rsp+98h+var_58]
0x1800804ff  mov     dl, byte ptr [rsp+98h+arg_18]
0x180080506  mov     [rax+rcx*8+0Ch], dl
0x18008050a  inc     r14d
0x18008050d  movsx   eax, word ptr [rsi+36h]
0x180080511  inc     r15d
0x180080514  cmp     r15d, eax
0x180080517  jl      loc_180080428
0x18008051d  mov     rdi, [rsp+98h+arg_0]
0x180080525  mov     rbp, [rsp+98h+var_48]
0x18008052a  mov     r12, [rsp+98h+var_50]
0x18008052f  mov     esi, [rsp+98h+var_64]
0x180080533  test    r14d, r14d
0x180080536  jnz     short loc_180080559
0x180080538  inc     dword ptr [rdi+3Ch]
0x18008053b  lea     r9d, [rsi+1]
0x18008053f  xor     r8d, r8d
0x180080542  mov     dword ptr [rsp+98h+var_78], r14d
0x180080547  lea     edx, [r14+4Bh]
0x18008054b  mov     rcx, rbx
0x18008054e  call    sqlite3VdbeAddOp3
0x180080553  mov     r14d, 1
0x180080559  mov     r15d, [rsp+98h+var_60]
0x18008055e  lea     edi, [rsi+1]
0x180080561  mov     r8d, edi
0x180080564  mov     dword ptr [rsp+98h+var_78], r15d
0x180080569  mov     r9d, r14d
0x18008056c  mov     edx, 61h ; 'a'
0x180080571  mov     rcx, rbx
0x180080574  call    sqlite3VdbeAddOp3
0x180080579  mov     r8d, [rsp+98h+var_68]
0x18008057e  mov     r9d, r15d
0x180080581  mov     rcx, rbx
0x180080584  test    r13, r13
0x180080587  jz      short loc_1800805A2
0x180080589  movzx   eax, word ptr [r13+5Eh]
0x18008058e  mov     edx, 8Ah
0x180080593  mov     dword ptr [rsp+98h+var_70], eax
0x180080597  mov     dword ptr [rsp+98h+var_78], edi
0x18008059b  call    sqlite3VdbeAddOp4Int
0x1800805a0  jmp     short loc_1800805B0
0x1800805a2  mov     edx, 80h
0x1800805a7  mov     dword ptr [rsp+98h+var_78], esi
0x1800805ab  call    sqlite3VdbeAddOp3
0x1800805b0  mov     edx, 2
0x1800805b5  mov     rcx, rbx
0x1800805b8  call    sqlite3VdbeChangeP5
0x1800805bd  mov     edi, [rsp+98h+var_5C]
  ... truncated ...
```
