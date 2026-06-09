# sqlite3AlterDropColumn

- ea: `0x18008f450`
- end: `0x18008f951`
- name: `sqlite3AlterDropColumn`
- size: `1281`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x18000213c`

## callees

- `0x18000506c`
- `0x180007190`
- `0x180008be8`
- `0x180009ac0`
- `0x180009fe0`
- `0x18000a754`
- `0x180011bcc`
- `0x1800151f0`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001cb40`
- `0x18001f0f0`
- `0x18001f418`
- `0x18001f530`
- `0x180041d10`
- `0x18004a9b8`
- `0x1800521f4`
- `0x1800729d8`
- `0x180081560`
- `0x180081a84`
- `0x18008d39c`
- `0x18008d51c`
- `0x18008ddc0`
- `0x18008f450`

## string_xrefs

- `0x18008f5db`: `UPDATE "%w".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)`

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
  int v22; // eax
  int v23; // edx
  int v24; // r14d
  int v25; // r12d
  int v26; // ecx
  int v27; // eax
  int v28; // r15d
  int v29; // ebp
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int16 v33; // ax
  int v34; // r11d
  int v35; // r11d
  int v36; // r8d
  int v37; // ecx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v41; // [rsp+20h] [rbp-78h]
  int v42; // [rsp+30h] [rbp-68h]
  int v43; // [rsp+34h] [rbp-64h]
  int v44; // [rsp+38h] [rbp-60h]
  unsigned int v45; // [rsp+3Ch] [rbp-5Ch]
  __int64 v46; // [rsp+48h] [rbp-50h]
  const char *v47; // [rsp+50h] [rbp-48h]
  int v50; // [rsp+B8h] [rbp+20h]
  __int64 v51; // [rsp+B8h] [rbp+20h]
  char v52; // [rsp+B8h] [rbp+20h]

  v3 = *(_QWORD *)a1;
  v4 = 0;
  v46 = *(_QWORD *)a1;
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
  v47 = (const char *)v9;
  v4 = (const char *)v9;
  if ( !v9 )
    goto LABEL_48;
  v10 = sqlite3ColumnIndex(v8, v9);
  v50 = v10;
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
    renameTestSchema((__int64)v6, v15, v14 == 1, (__int64)&Src, 0);
    renameFixQuotes((__int64)v6, v15, v14 == 1);
    LODWORD(v41) = v50;
    sqlite3NestedParse(
      v6,
      "UPDATE \"%w\".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)",
      v15,
      (unsigned int)v14,
      v41,
      *(_QWORD *)v8);
    renameReloadSchema(v6, (unsigned int)v14, 2);
    renameTestSchema((__int64)v6, v15, v14 == 1, (__int64)"after drop column", 1);
    if ( !v6[12] && (*(_BYTE *)(*(_QWORD *)(v8 + 8) + 8 * v11 + 18) & 0x20) == 0 )
    {
      Vdbe = sqlite3GetVdbe(v6);
      v17 = v6[13];
      v42 = v17;
      v18 = Vdbe;
      v6[13] = v17 + 1;
      sqlite3OpenTable((_DWORD)v6, v17, v14, v8, 113);
      v19 = sqlite3VdbeAddOp3(v18, 36, v17, 0, 0);
      ++v6[14];
      v45 = v19;
      v43 = v6[14];
      if ( *(char *)(v8 + 48) < 0 )
      {
        v20 = sqlite3PrimaryKeyIndex(v8);
        v24 = 0;
        v22 = v23 + *(unsigned __int16 *)(v20 + 96);
        v6[14] = v22;
        if ( *(_WORD *)(v20 + 94) )
        {
          v25 = v23 + 1;
          do
          {
            sqlite3VdbeAddOp3(v18, 94, v17, v24, v25 + v24);
            v26 = *(unsigned __int16 *)(v20 + 94);
            ++v24;
          }
          while ( v24 < v26 );
          v22 = v6[14];
          v3 = v46;
        }
        else
        {
          LOWORD(v26) = *(_WORD *)(v20 + 94);
        }
        v21 = (unsigned __int16)v26;
      }
      else
      {
        v20 = 0;
        v21 = 0;
        sqlite3VdbeAddOp3(v18, 135, v17, v6[14], 0);
        v22 = v6[14] + *(__int16 *)(v8 + 54);
      }
      v27 = v22 + 1;
      v28 = 0;
      v6[14] = v27;
      v44 = v27;
      if ( *(__int16 *)(v8 + 54) > 0 )
      {
        v29 = v50;
        while ( 1 )
        {
          if ( v28 != v29 )
          {
            v30 = *(_QWORD *)(v8 + 8);
            v51 = v30;
            v31 = 3LL * v28;
            if ( (*(_BYTE *)(v30 + 24LL * v28 + 18) & 0x20) == 0 )
            {
              if ( !v20 )
              {
                v35 = v21;
                goto LABEL_34;
              }
              if ( (__int16)sqlite3TableColumnToIndex(v20) >= (int)*(unsigned __int16 *)(v20 + 94) )
              {
                v33 = sqlite3TableColumnToIndex(v32);
                v30 = v51;
                v31 = 3LL * v28;
                v35 = v34 - (v34 > v33);
LABEL_34:
                v36 = v43 + v35;
                if ( v28 == *(__int16 *)(v8 + 52) )
                {
                  sqlite3VdbeAddOp3(v18, 75, 0, v36 + 1, 0);
                }
                else
                {
                  v52 = *(_BYTE *)(v30 + 8 * v31 + 12);
                  if ( v52 == 69 )
                    *(_BYTE *)(v30 + 8 * v31 + 12) = 67;
                  sqlite3ExprCodeGetColumnOfTable(v18, v8, v42, v28, v36 + 1);
                  *(_BYTE *)(*(_QWORD *)(v8 + 8) + 24LL * v28 + 12) = v52;
                }
                ++v21;
              }
            }
          }
          if ( ++v28 >= *(__int16 *)(v8 + 54) )
          {
            v6 = a1;
            v4 = v47;
            v3 = v46;
            break;
          }
        }
      }
      if ( !v21 )
      {
        ++v6[14];
        sqlite3VdbeAddOp3(v18, 75, 0, v43 + 1, 0);
        v21 = 1;
      }
      sqlite3VdbeAddOp3(v18, 97, v43 + 1, v21, v44);
      if ( v20 )
        sqlite3VdbeAddOp4Int(v18, 138, v42, v44, v43 + 1, *(unsigned __int16 *)(v20 + 94));
      else
        sqlite3VdbeAddOp3(v18, 128, v42, v44, v43);
      sqlite3VdbeChangeP5(v18, 2);
      sqlite3VdbeAddOp3(v37, 39, v42, v45 + 1, 0);
      *(_DWORD *)(sqlite3VdbeGetOp(v18, v45, v38, v39) + 8) = *(_DWORD *)(v18 + 144);
    }
  }
LABEL_48:
  sqlite3DbFree(v3, v4);
  return sqlite3SrcListDelete(v3, a2);
}

```

## disassembly

```asm
0x18008f450  mov     [rsp+arg_10], rbx
0x18008f455  mov     [rsp+arg_8], rdx
0x18008f45a  mov     [rsp+arg_0], rcx
0x18008f45f  push    rbp
0x18008f460  push    rsi
0x18008f461  push    rdi
0x18008f462  push    r12
0x18008f464  push    r13
0x18008f466  push    r14
0x18008f468  push    r15
0x18008f46a  sub     rsp, 60h
0x18008f46e  mov     r12, [rcx]
0x18008f471  xor     ebp, ebp
0x18008f473  mov     rbx, r8
0x18008f476  mov     [rsp+98h+var_50], r12
0x18008f47b  mov     rdi, rcx
0x18008f47e  cmp     [r12+67h], bpl
0x18008f483  jnz     loc_18008F91F
0x18008f489  lea     r8, [rdx+8]
0x18008f48d  xor     edx, edx
0x18008f48f  call    sqlite3LocateTableItem
0x18008f494  mov     rsi, rax
0x18008f497  test    rax, rax
0x18008f49a  jz      loc_18008F91F
0x18008f4a0  mov     rdx, rax
0x18008f4a3  mov     rcx, rdi
0x18008f4a6  call    isAlterableTable
0x18008f4ab  test    eax, eax
0x18008f4ad  jnz     loc_18008F91F
0x18008f4b3  lea     r15d, [rbp+1]
0x18008f4b7  mov     rdx, rsi
0x18008f4ba  mov     r8d, r15d
0x18008f4bd  mov     rcx, rdi
0x18008f4c0  call    isRealTable
0x18008f4c5  test    eax, eax
0x18008f4c7  jnz     loc_18008F91F
0x18008f4cd  mov     rdx, rbx
0x18008f4d0  mov     rcx, r12
0x18008f4d3  call    sqlite3NameFromToken
0x18008f4d8  mov     [rsp+98h+var_48], rax
0x18008f4dd  mov     rbp, rax
0x18008f4e0  test    rax, rax
0x18008f4e3  jz      loc_18008F91F
0x18008f4e9  mov     rdx, rax
0x18008f4ec  mov     rcx, rsi
0x18008f4ef  call    sqlite3ColumnIndex
0x18008f4f4  mov     dword ptr [rsp+98h+arg_18], eax
0x18008f4fb  test    eax, eax
0x18008f4fd  jns     short loc_18008F516
0x18008f4ff  mov     r8, rbx
0x18008f502  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x18008f509  mov     rcx, rdi
0x18008f50c  call    sqlite3ErrorMsg
0x18008f511  jmp     loc_18008F91F
0x18008f516  cdqe
0x18008f518  lea     r14, [rax+rax*2]
0x18008f51c  mov     rax, [rsi+8]
0x18008f520  test    byte ptr [rax+r14*8+12h], 9
0x18008f526  jz      short loc_18008F556
0x18008f528  test    [rax+r14*8+12h], r15b
0x18008f52d  lea     r8, aPrimaryKey; "PRIMARY KEY"
0x18008f534  lea     rax, aUnique_0; "UNIQUE"
0x18008f53b  mov     r9, rbp
0x18008f53e  cmovz   r8, rax
0x18008f542  lea     rdx, aCannotDropSCol; "cannot drop %s column: \"%s\""
0x18008f549  mov     rcx, rdi
0x18008f54c  call    sqlite3ErrorMsg
0x18008f551  jmp     loc_18008F91F
0x18008f556  cmp     [rsi+36h], r15w
0x18008f55b  jg      short loc_18008F569
0x18008f55d  mov     r8, rbp
0x18008f560  lea     rdx, aCannotDropColu; "cannot drop column \"%s\": no other col"...
0x18008f567  jmp     short loc_18008F509
0x18008f569  mov     rdx, [rsi+60h]
0x18008f56d  mov     rcx, r12
0x18008f570  call    sqlite3SchemaToIndex
0x18008f575  mov     rcx, [r12+20h]
0x18008f57a  mov     r9, [rsi]
0x18008f57d  movsxd  r13, eax
0x18008f580  mov     rdx, r13
0x18008f583  mov     [rsp+98h+var_78], rbp
0x18008f588  shl     rdx, 5
0x18008f58c  mov     r15, [rdx+rcx]
0x18008f590  mov     edx, 1Ah
0x18008f595  mov     r8, r15
0x18008f598  mov     rcx, rdi
0x18008f59b  call    sqlite3AuthCheck
0x18008f5a0  test    eax, eax
0x18008f5a2  jnz     loc_18008F91F
0x18008f5a8  xor     ebx, ebx
0x18008f5aa  mov     dword ptr [rsp+98h+var_78], eax
0x18008f5ae  cmp     r13d, 1
0x18008f5b2  lea     r9, Src
0x18008f5b9  mov     rdx, r15
0x18008f5bc  mov     rcx, rdi
0x18008f5bf  setz    bl
0x18008f5c2  mov     r8d, ebx
0x18008f5c5  call    renameTestSchema
0x18008f5ca  mov     r8d, ebx
0x18008f5cd  mov     rdx, r15
0x18008f5d0  mov     rcx, rdi
0x18008f5d3  call    renameFixQuotes
0x18008f5d8  mov     rax, [rsi]
0x18008f5db  lea     rdx, aUpdateWSqliteM_0; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x18008f5e2  mov     [rsp+98h+var_70], rax
0x18008f5e7  mov     r9d, r13d
0x18008f5ea  mov     eax, dword ptr [rsp+98h+arg_18]
0x18008f5f1  mov     r8, r15
0x18008f5f4  mov     rcx, rdi
0x18008f5f7  mov     dword ptr [rsp+98h+var_78], eax
0x18008f5fb  call    sqlite3NestedParse
0x18008f600  mov     r8d, 2
0x18008f606  mov     edx, r13d
0x18008f609  mov     rcx, rdi
0x18008f60c  call    renameReloadSchema
0x18008f611  lea     r9, aAfterDropColum; "after drop column"
0x18008f618  mov     dword ptr [rsp+98h+var_78], 1
0x18008f620  mov     r8d, ebx
0x18008f623  mov     rdx, r15
0x18008f626  mov     rcx, rdi
0x18008f629  call    renameTestSchema
0x18008f62e  cmp     dword ptr [rdi+30h], 0
0x18008f632  jnz     loc_18008F91F
0x18008f638  mov     rax, [rsi+8]
0x18008f63c  test    byte ptr [rax+r14*8+12h], 20h
0x18008f642  jnz     loc_18008F91F
0x18008f648  mov     rcx, rdi
0x18008f64b  call    sqlite3GetVdbe
0x18008f650  mov     r15d, [rdi+34h]
0x18008f654  mov     r9, rsi
0x18008f657  mov     r8d, r13d
0x18008f65a  mov     [rsp+98h+var_68], r15d
0x18008f65f  mov     edx, r15d
0x18008f662  mov     dword ptr [rsp+98h+var_78], 71h ; 'q'
0x18008f66a  mov     rbx, rax
0x18008f66d  lea     ecx, [r15+1]
0x18008f671  mov     [rdi+34h], ecx
0x18008f674  mov     rcx, rdi
0x18008f677  call    sqlite3OpenTable
0x18008f67c  xor     r9d, r9d
0x18008f67f  mov     dword ptr [rsp+98h+var_78], 0
0x18008f687  mov     r8d, r15d
0x18008f68a  mov     rcx, rbx
0x18008f68d  lea     edx, [r9+24h]
0x18008f691  call    sqlite3VdbeAddOp3
0x18008f696  inc     dword ptr [rdi+38h]
0x18008f699  test    byte ptr [rsi+30h], 80h
0x18008f69d  mov     edx, [rdi+38h]
0x18008f6a0  mov     [rsp+98h+var_5C], eax
0x18008f6a4  mov     [rsp+98h+var_64], edx
0x18008f6a8  jnz     short loc_18008F6D1
0x18008f6aa  mov     r9d, edx
0x18008f6ad  xor     r13d, r13d
0x18008f6b0  mov     edx, 87h
0x18008f6b5  mov     dword ptr [rsp+98h+var_78], r13d
0x18008f6ba  mov     r8d, r15d
0x18008f6bd  mov     rcx, rbx
0x18008f6c0  xor     r14d, r14d
0x18008f6c3  call    sqlite3VdbeAddOp3
0x18008f6c8  movsx   eax, word ptr [rsi+36h]
0x18008f6cc  add     eax, [rdi+38h]
0x18008f6cf  jmp     short loc_18008F730
0x18008f6d1  mov     rcx, rsi
0x18008f6d4  call    sqlite3PrimaryKeyIndex
0x18008f6d9  mov     r13, rax
0x18008f6dc  xor     r14d, r14d
0x18008f6df  xor     ecx, ecx
0x18008f6e1  movzx   eax, word ptr [rax+60h]
0x18008f6e5  add     eax, edx
0x18008f6e7  mov     [rdi+38h], eax
0x18008f6ea  cmp     cx, [r13+5Eh]
0x18008f6ef  jnb     short loc_18008F727
0x18008f6f1  lea     r12d, [rdx+1]
0x18008f6f5  lea     eax, [r12+r14]
0x18008f6f9  mov     r9d, r14d
0x18008f6fc  mov     r8d, r15d
0x18008f6ff  mov     dword ptr [rsp+98h+var_78], eax
0x18008f703  mov     edx, 5Eh ; '^'
0x18008f708  mov     rcx, rbx
0x18008f70b  call    sqlite3VdbeAddOp3
0x18008f710  movzx   ecx, word ptr [r13+5Eh]
0x18008f715  inc     r14d
0x18008f718  cmp     r14d, ecx
0x18008f71b  jl      short loc_18008F6F5
0x18008f71d  mov     eax, [rdi+38h]
0x18008f720  mov     r12, [rsp+98h+var_50]
0x18008f725  jmp     short loc_18008F72C
0x18008f727  movzx   ecx, word ptr [r13+5Eh]
0x18008f72c  movzx   r14d, cx
0x18008f730  inc     eax
0x18008f732  xor     r15d, r15d
0x18008f735  mov     [rdi+38h], eax
0x18008f738  mov     [rsp+98h+var_60], eax
0x18008f73c  xor     eax, eax
0x18008f73e  cmp     ax, [rsi+36h]
0x18008f742  jge     loc_18008F85F
0x18008f748  mov     r12d, [rsp+98h+var_64]
0x18008f74d  mov     edi, [rsp+98h+var_68]
0x18008f751  mov     ebp, dword ptr [rsp+98h+arg_18]
0x18008f758  cmp     r15d, ebp
0x18008f75b  jz      loc_18008F83D
0x18008f761  mov     rdx, [rsi+8]
0x18008f765  movsxd  rax, r15d
0x18008f768  mov     [rsp+98h+arg_18], rdx
0x18008f770  lea     rcx, [rax+rax*2]
0x18008f774  test    byte ptr [rdx+rcx*8+12h], 20h
0x18008f779  mov     [rsp+98h+var_58], rcx
0x18008f77e  jnz     loc_18008F83D
0x18008f784  test    r13, r13
0x18008f787  jz      short loc_18008F7CC
0x18008f789  movzx   edx, r15w
0x18008f78d  mov     rcx, r13
0x18008f790  call    sqlite3TableColumnToIndex
0x18008f795  movsx   r11d, ax
0x18008f799  movzx   eax, word ptr [r13+5Eh]
0x18008f79e  cmp     r11d, eax
0x18008f7a1  jl      loc_18008F83D
0x18008f7a7  movzx   edx, bp
0x18008f7aa  call    sqlite3TableColumnToIndex
0x18008f7af  mov     rdx, [rsp+98h+arg_18]
0x18008f7b7  movsx   ecx, ax
0x18008f7ba  xor     eax, eax
0x18008f7bc  cmp     r11d, ecx
0x18008f7bf  mov     rcx, [rsp+98h+var_58]
0x18008f7c4  setnle  al
0x18008f7c7  sub     r11d, eax
0x18008f7ca  jmp     short loc_18008F7CF
0x18008f7cc  mov     r11d, r14d
0x18008f7cf  movsx   eax, word ptr [rsi+34h]
0x18008f7d3  lea     r8d, [r12+r11]
0x18008f7d7  cmp     r15d, eax
0x18008f7da  jnz     short loc_18008F7F9
0x18008f7dc  lea     r9d, [r8+1]
0x18008f7e0  mov     dword ptr [rsp+98h+var_78], 0
0x18008f7e8  xor     r8d, r8d
0x18008f7eb  mov     rcx, rbx
0x18008f7ee  lea     edx, [r8+4Bh]
0x18008f7f2  call    sqlite3VdbeAddOp3
0x18008f7f7  jmp     short loc_18008F83A
0x18008f7f9  mov     al, [rdx+rcx*8+0Ch]
0x18008f7fd  mov     byte ptr [rsp+98h+arg_18], al
0x18008f804  cmp     al, 45h ; 'E'
0x18008f806  jnz     short loc_18008F80D
0x18008f808  mov     byte ptr [rdx+rcx*8+0Ch], 43h ; 'C'
0x18008f80d  lea     eax, [r8+1]
0x18008f811  mov     r9d, r15d
0x18008f814  mov     r8d, edi
0x18008f817  mov     dword ptr [rsp+98h+var_78], eax
0x18008f81b  mov     rdx, rsi
0x18008f81e  mov     rcx, rbx
0x18008f821  call    sqlite3ExprCodeGetColumnOfTable
0x18008f826  mov     rax, [rsi+8]
0x18008f82a  mov     rcx, [rsp+98h+var_58]
0x18008f82f  mov     dl, byte ptr [rsp+98h+arg_18]
0x18008f836  mov     [rax+rcx*8+0Ch], dl
0x18008f83a  inc     r14d
0x18008f83d  movsx   eax, word ptr [rsi+36h]
0x18008f841  inc     r15d
0x18008f844  cmp     r15d, eax
0x18008f847  jl      loc_18008F758
0x18008f84d  mov     rdi, [rsp+98h+arg_0]
0x18008f855  mov     rbp, [rsp+98h+var_48]
0x18008f85a  mov     r12, [rsp+98h+var_50]
0x18008f85f  mov     esi, [rsp+98h+var_64]
0x18008f863  test    r14d, r14d
0x18008f866  jnz     short loc_18008F889
0x18008f868  inc     dword ptr [rdi+38h]
0x18008f86b  lea     r9d, [rsi+1]
0x18008f86f  xor     r8d, r8d
0x18008f872  mov     dword ptr [rsp+98h+var_78], r14d
0x18008f877  lea     edx, [r14+4Bh]
0x18008f87b  mov     rcx, rbx
0x18008f87e  call    sqlite3VdbeAddOp3
0x18008f883  mov     r14d, 1
0x18008f889  mov     r15d, [rsp+98h+var_60]
0x18008f88e  lea     edi, [rsi+1]
0x18008f891  mov     r8d, edi
0x18008f894  mov     dword ptr [rsp+98h+var_78], r15d
0x18008f899  mov     r9d, r14d
0x18008f89c  mov     edx, 61h ; 'a'
0x18008f8a1  mov     rcx, rbx
0x18008f8a4  call    sqlite3VdbeAddOp3
0x18008f8a9  mov     r8d, [rsp+98h+var_68]
0x18008f8ae  mov     r9d, r15d
0x18008f8b1  mov     rcx, rbx
0x18008f8b4  test    r13, r13
0x18008f8b7  jz      short loc_18008F8D2
0x18008f8b9  movzx   eax, word ptr [r13+5Eh]
0x18008f8be  mov     edx, 8Ah
0x18008f8c3  mov     dword ptr [rsp+98h+var_70], eax
0x18008f8c7  mov     dword ptr [rsp+98h+var_78], edi
0x18008f8cb  call    sqlite3VdbeAddOp4Int
0x18008f8d0  jmp     short loc_18008F8E0
0x18008f8d2  mov     edx, 80h
0x18008f8d7  mov     dword ptr [rsp+98h+var_78], esi
0x18008f8db  call    sqlite3VdbeAddOp3
0x18008f8e0  mov     edx, 2
0x18008f8e5  mov     rcx, rbx
0x18008f8e8  call    sqlite3VdbeChangeP5
0x18008f8ed  mov     edi, [rsp+98h+var_5C]
  ... truncated ...
```
