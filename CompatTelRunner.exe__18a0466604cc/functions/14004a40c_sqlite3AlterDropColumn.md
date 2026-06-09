# sqlite3AlterDropColumn

- ea: `0x14004a40c`
- end: `0x14004a91f`
- name: `sqlite3AlterDropColumn`
- size: `1299`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x1400a40bc`

## callees

- `0x1400315b4`
- `0x140031fb8`
- `0x140043d90`
- `0x140044904`
- `0x14004a40c`
- `0x14004bdbc`
- `0x1400518f8`
- `0x140053e3c`
- `0x1400560c4`
- `0x140056d98`
- `0x14005f5fc`
- `0x14006280c`
- `0x14006345c`
- `0x14006348c`
- `0x140063770`
- `0x14006f6b0`
- `0x140070858`
- `0x1400738a0`
- `0x14007399c`
- `0x14007b574`

## string_xrefs

- `0x14004a5ba`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x14004a5a3`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x14004a5cc`: `UPDATE "%w".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)`

## pseudocode

```c
__int64 __fastcall sqlite3AlterDropColumn(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v5; // rbp
  _DWORD *v6; // rbx
  __int64 TableItem; // rax
  __int64 v8; // rdi
  __int64 v9; // rax
  const char *v10; // r12
  int v11; // eax
  __int64 v12; // r15
  __int64 v13; // rax
  const char *v14; // r8
  __int64 v15; // rcx
  int v16; // esi
  __int64 v17; // rdx
  __int64 v18; // rbp
  __int64 Vdbe; // rax
  int v20; // r14d
  __int64 v21; // rbp
  unsigned int v22; // eax
  int v23; // edx
  __int64 i; // rsi
  int v25; // r15d
  int v26; // ecx
  int v27; // r14d
  int v28; // r13d
  int v29; // eax
  int v30; // r14d
  __int64 v31; // rcx
  __int16 v32; // ax
  int v33; // r11d
  int v34; // r11d
  int v35; // ecx
  __int64 v36; // rax
  __int64 v38; // [rsp+20h] [rbp-68h]
  int v39; // [rsp+30h] [rbp-58h]
  int v40; // [rsp+34h] [rbp-54h]
  int v41; // [rsp+38h] [rbp-50h]
  unsigned int v42; // [rsp+3Ch] [rbp-4Ch]
  __int64 v43; // [rsp+40h] [rbp-48h]
  int v46; // [rsp+A8h] [rbp+20h]

  v3 = *(_QWORD *)a1;
  v5 = a2;
  v43 = *(_QWORD *)a1;
  v6 = a1;
  if ( !*(_BYTE *)(*(_QWORD *)a1 + 103LL) )
  {
    TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
    v8 = TableItem;
    if ( TableItem )
    {
      if ( !(unsigned int)isAlterableTable(v6, TableItem) && !(unsigned int)isRealTable(v6, v8, 1) )
      {
        v9 = sqlite3NameFromToken(v3, a3);
        v10 = (const char *)v9;
        if ( v9 )
        {
          v11 = sqlite3ColumnIndex(v8, v9);
          v40 = v11;
          if ( v11 < 0 )
          {
            sqlite3ErrorMsg(v6, "no such column: \"%T\"", a3);
LABEL_56:
            sqlite3DbFreeNN(v3);
            return sqlite3SrcListDelete(v3, v5);
          }
          v12 = 3LL * v11;
          v13 = *(_QWORD *)(v8 + 8);
          if ( (*(_BYTE *)(v13 + 8 * v12 + 18) & 9) != 0 )
          {
            v14 = "PRIMARY KEY";
            if ( (*(_BYTE *)(v13 + 8 * v12 + 18) & 1) == 0 )
              v14 = "UNIQUE";
            sqlite3ErrorMsg(v6, "cannot drop %s column: \"%s\"", v14, v10);
            goto LABEL_56;
          }
          if ( *(__int16 *)(v8 + 54) <= 1 )
          {
            sqlite3ErrorMsg(v6, "cannot drop column \"%s\": no other columns exist", v10);
            goto LABEL_56;
          }
          v15 = *(_QWORD *)(v8 + 96);
          v16 = -32768;
          if ( v15 )
          {
            v17 = *(_QWORD *)(v3 + 32);
            v16 = 0;
            if ( *(_QWORD *)(v17 + 24) != v15 )
            {
              do
                ++v16;
              while ( *(_QWORD *)(32LL * v16 + v17 + 24) != v15 );
            }
          }
          v18 = *(_QWORD *)(32LL * v16 + *(_QWORD *)(v3 + 32));
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)v6, 26, v18, *(_QWORD *)v8, (__int64)v10) )
          {
            renameTestSchema((_DWORD)v6, v18, v16 == 1, (unsigned int)&dword_1400ACDEC, 0);
            sqlite3NestedParse(
              v6,
              "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCA"
              "PE 'X' AND sql NOT LIKE 'create virtual%%'",
              v18,
              v18);
            if ( v16 != 1 )
              sqlite3NestedParse(
                v6,
                "UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' "
                "ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'");
            LODWORD(v38) = v40;
            sqlite3NestedParse(
              v6,
              "UPDATE \"%w\".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q"
              " COLLATE nocase)",
              v18,
              (unsigned int)v16,
              v38,
              *(_QWORD *)v8);
            renameReloadSchema(v6, (unsigned int)v16, 2);
            renameTestSchema((_DWORD)v6, v18, v16 == 1, (unsigned int)"after drop column", 1);
            if ( !v6[12] && (*(_BYTE *)(*(_QWORD *)(v8 + 8) + 8 * v12 + 18) & 0x20) == 0 )
            {
              Vdbe = sqlite3GetVdbe(v6);
              v20 = v6[13];
              v46 = v20;
              v21 = Vdbe;
              v6[13] = v20 + 1;
              sqlite3OpenTable((_DWORD)v6, v20, v16, v8, 113);
              v22 = sqlite3VdbeAddOp3(v21, 36, v20, 0, 0);
              v23 = ++v6[14];
              v42 = v22;
              v39 = v23;
              if ( *(char *)(v8 + 48) < 0 )
              {
                for ( i = *(_QWORD *)(v8 + 16); i && (*(_DWORD *)(i + 100) & 3) != 2; i = *(_QWORD *)(i + 40) )
                  ;
                v27 = 0;
                v26 = v23 + *(unsigned __int16 *)(i + 96);
                v6[14] = v26;
                if ( *(_WORD *)(i + 94) )
                {
                  v28 = v23 + 1;
                  do
                  {
                    sqlite3VdbeAddOp3(v21, 94, v46, v27, v27 + v28);
                    v29 = *(unsigned __int16 *)(i + 94);
                    ++v27;
                  }
                  while ( v27 < v29 );
                  v26 = v6[14];
                  v3 = v43;
                }
                else
                {
                  LOWORD(v29) = *(_WORD *)(i + 94);
                }
                v25 = (unsigned __int16)v29;
              }
              else
              {
                i = 0;
                v25 = 0;
                sqlite3VdbeAddOp3(v21, 135, v20, v23, 0);
                v26 = v6[14] + *(__int16 *)(v8 + 54);
              }
              v30 = 0;
              v6[14] = v26 + 1;
              v41 = v26 + 1;
              if ( *(__int16 *)(v8 + 54) > 0 )
              {
                while ( 1 )
                {
                  if ( v30 != v40 && (*(_BYTE *)(*(_QWORD *)(v8 + 8) + 24LL * v30 + 18) & 0x20) == 0 )
                  {
                    if ( !i )
                    {
                      v34 = v25;
                      goto LABEL_41;
                    }
                    if ( (__int16)sqlite3TableColumnToIndex(i, (unsigned __int16)v30) >= (int)*(unsigned __int16 *)(i + 94) )
                    {
                      v32 = sqlite3TableColumnToIndex(v31, (unsigned __int16)v40);
                      v34 = v33 - (v33 > v32);
LABEL_41:
                      v35 = v34 + v39 + 1;
                      if ( v30 == *(__int16 *)(v8 + 52) )
                        sqlite3VdbeAddOp3(v21, 75, 0, v35, 0);
                      else
                        sqlite3ExprCodeGetColumnOfTable(v21, v8, v46, v30, v35);
                      ++v25;
                    }
                  }
                  if ( ++v30 >= *(__int16 *)(v8 + 54) )
                  {
                    v6 = a1;
                    v3 = v43;
                    break;
                  }
                }
              }
              if ( !v25 )
              {
                ++v6[14];
                sqlite3VdbeAddOp3(v21, 75, 0, v39 + 1, 0);
                v25 = 1;
              }
              sqlite3VdbeAddOp3(v21, 97, v39 + 1, v25, v41);
              if ( i )
                sqlite3VdbeAddOp4Int(v21, 138, v46, v41, v39 + 1, *(unsigned __int16 *)(i + 94));
              else
                sqlite3VdbeAddOp3(v21, 128, v46, v41, v39);
              v36 = *(int *)(v21 + 144);
              if ( (int)v36 > 0 )
                *(_WORD *)(*(_QWORD *)(v21 + 136) + 24 * v36 - 22) = 2;
              sqlite3VdbeAddOp3(v21, 39, v46, v42 + 1, 0);
              sqlite3VdbeJumpHere(v21, v42);
            }
          }
          v5 = a2;
          goto LABEL_56;
        }
      }
    }
  }
  return sqlite3SrcListDelete(v3, v5);
}

```

## disassembly

```asm
0x14004a40c  mov     [rsp+arg_10], rbx
0x14004a411  mov     [rsp+arg_8], rdx
0x14004a416  mov     [rsp+arg_0], rcx
0x14004a41b  push    rbp
0x14004a41c  push    rsi
0x14004a41d  push    rdi
0x14004a41e  push    r12
0x14004a420  push    r13
0x14004a422  push    r14
0x14004a424  push    r15
0x14004a426  sub     rsp, 50h
0x14004a42a  mov     r13, [rcx]
0x14004a42d  mov     rsi, r8
0x14004a430  mov     rbp, rdx
0x14004a433  mov     [rsp+88h+var_48], r13
0x14004a438  mov     rbx, rcx
0x14004a43b  cmp     byte ptr [r13+67h], 0
0x14004a440  jnz     loc_14004A8FD
0x14004a446  lea     r8, [rdx+8]
0x14004a44a  xor     edx, edx
0x14004a44c  call    sqlite3LocateTableItem
0x14004a451  mov     rdi, rax
0x14004a454  test    rax, rax
0x14004a457  jz      loc_14004A8FD
0x14004a45d  mov     rdx, rax
0x14004a460  mov     rcx, rbx
0x14004a463  call    isAlterableTable
0x14004a468  test    eax, eax
0x14004a46a  jnz     loc_14004A8FD
0x14004a470  lea     r14d, [rax+1]
0x14004a474  mov     rdx, rdi
0x14004a477  mov     r8d, r14d
0x14004a47a  mov     rcx, rbx
0x14004a47d  call    isRealTable
0x14004a482  test    eax, eax
0x14004a484  jnz     loc_14004A8FD
0x14004a48a  mov     rdx, rsi
0x14004a48d  mov     rcx, r13
0x14004a490  call    sqlite3NameFromToken
0x14004a495  mov     [rsp+88h+var_40], rax
0x14004a49a  mov     r12, rax
0x14004a49d  test    rax, rax
0x14004a4a0  jz      loc_14004A8FD
0x14004a4a6  mov     rdx, rax
0x14004a4a9  mov     rcx, rdi
0x14004a4ac  call    sqlite3ColumnIndex
0x14004a4b1  mov     [rsp+88h+var_54], eax
0x14004a4b5  test    eax, eax
0x14004a4b7  jns     short loc_14004A4D0
0x14004a4b9  mov     r8, rsi
0x14004a4bc  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x14004a4c3  mov     rcx, rbx
0x14004a4c6  call    sqlite3ErrorMsg
0x14004a4cb  jmp     loc_14004A8F2
0x14004a4d0  cdqe
0x14004a4d2  lea     r15, [rax+rax*2]
0x14004a4d6  mov     rax, [rdi+8]
0x14004a4da  test    byte ptr [rax+r15*8+12h], 9
0x14004a4e0  jz      short loc_14004A510
0x14004a4e2  test    [rax+r15*8+12h], r14b
0x14004a4e7  lea     r8, aPrimaryKey; "PRIMARY KEY"
0x14004a4ee  lea     rax, aUnique_0; "UNIQUE"
0x14004a4f5  mov     r9, r12
0x14004a4f8  cmovz   r8, rax
0x14004a4fc  lea     rdx, aCannotDropSCol; "cannot drop %s column: \"%s\""
0x14004a503  mov     rcx, rbx
0x14004a506  call    sqlite3ErrorMsg
0x14004a50b  jmp     loc_14004A8F2
0x14004a510  cmp     [rdi+36h], r14w
0x14004a515  jg      short loc_14004A523
0x14004a517  mov     r8, r12
0x14004a51a  lea     rdx, aCannotDropColu; "cannot drop column \"%s\": no other col"...
0x14004a521  jmp     short loc_14004A4C3
0x14004a523  mov     rcx, [rdi+60h]
0x14004a527  mov     esi, 0FFFF8000h
0x14004a52c  test    rcx, rcx
0x14004a52f  jz      short loc_14004A54E
0x14004a531  mov     rdx, [r13+20h]
0x14004a535  xor     esi, esi
0x14004a537  cmp     [rdx+18h], rcx
0x14004a53b  jz      short loc_14004A54E
0x14004a53d  add     esi, r14d
0x14004a540  movsxd  rax, esi
0x14004a543  shl     rax, 5
0x14004a547  cmp     [rax+rdx+18h], rcx
0x14004a54c  jnz     short loc_14004A53D
0x14004a54e  mov     rax, [r13+20h]
0x14004a552  mov     edx, 1Ah
0x14004a557  mov     r9, [rdi]
0x14004a55a  movsxd  rcx, esi
0x14004a55d  shl     rcx, 5
0x14004a561  mov     [rsp+88h+var_68], r12
0x14004a566  mov     rbp, [rcx+rax]
0x14004a56a  mov     rcx, rbx
0x14004a56d  mov     r8, rbp
0x14004a570  call    sqlite3AuthCheck
0x14004a575  test    eax, eax
0x14004a577  jnz     loc_14004A8EA
0x14004a57d  xor     r14d, r14d
0x14004a580  mov     dword ptr [rsp+88h+var_68], eax
0x14004a584  cmp     esi, 1
0x14004a587  lea     r9, dword_1400ACDEC
0x14004a58e  mov     rdx, rbp
0x14004a591  mov     rcx, rbx
0x14004a594  setz    r14b
0x14004a598  mov     r8d, r14d
0x14004a59b  call    renameTestSchema
0x14004a5a0  mov     r9, rbp
0x14004a5a3  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x14004a5aa  mov     r8, rbp
0x14004a5ad  mov     rcx, rbx
0x14004a5b0  call    sqlite3NestedParse
0x14004a5b5  cmp     esi, 1
0x14004a5b8  jz      short loc_14004A5C9
0x14004a5ba  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x14004a5c1  mov     rcx, rbx
0x14004a5c4  call    sqlite3NestedParse
0x14004a5c9  mov     rax, [rdi]
0x14004a5cc  lea     rdx, aUpdateWSqliteM_0; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x14004a5d3  mov     [rsp+88h+var_60], rax
0x14004a5d8  mov     r9d, esi
0x14004a5db  mov     eax, [rsp+88h+var_54]
0x14004a5df  mov     r8, rbp
0x14004a5e2  mov     rcx, rbx
0x14004a5e5  mov     dword ptr [rsp+88h+var_68], eax
0x14004a5e9  call    sqlite3NestedParse
0x14004a5ee  mov     r8d, 2
0x14004a5f4  mov     edx, esi
0x14004a5f6  mov     rcx, rbx
0x14004a5f9  call    renameReloadSchema
0x14004a5fe  lea     r9, aAfterDropColum; "after drop column"
0x14004a605  mov     dword ptr [rsp+88h+var_68], 1
0x14004a60d  mov     r8d, r14d
0x14004a610  mov     rdx, rbp
0x14004a613  mov     rcx, rbx
0x14004a616  call    renameTestSchema
0x14004a61b  cmp     dword ptr [rbx+30h], 0
0x14004a61f  jnz     loc_14004A8EA
0x14004a625  mov     rax, [rdi+8]
0x14004a629  test    byte ptr [rax+r15*8+12h], 20h
0x14004a62f  jnz     loc_14004A8EA
0x14004a635  mov     rcx, rbx
0x14004a638  call    sqlite3GetVdbe
0x14004a63d  mov     r14d, [rbx+34h]
0x14004a641  mov     r9, rdi
0x14004a644  mov     r8d, esi
0x14004a647  mov     [rsp+88h+arg_18], r14d
0x14004a64f  mov     edx, r14d
0x14004a652  mov     dword ptr [rsp+88h+var_68], 71h ; 'q'
0x14004a65a  mov     rbp, rax
0x14004a65d  lea     ecx, [r14+1]
0x14004a661  mov     [rbx+34h], ecx
0x14004a664  mov     rcx, rbx
0x14004a667  call    sqlite3OpenTable
0x14004a66c  xor     r9d, r9d
0x14004a66f  mov     dword ptr [rsp+88h+var_68], 0
0x14004a677  mov     r8d, r14d
0x14004a67a  mov     rcx, rbp
0x14004a67d  lea     edx, [r9+24h]
0x14004a681  call    sqlite3VdbeAddOp3
0x14004a686  inc     dword ptr [rbx+38h]
0x14004a689  test    byte ptr [rdi+30h], 80h
0x14004a68d  mov     edx, [rbx+38h]
0x14004a690  mov     [rsp+88h+var_4C], eax
0x14004a694  mov     [rsp+88h+var_58], edx
0x14004a698  jnz     short loc_14004A6BF
0x14004a69a  mov     r9d, edx
0x14004a69d  xor     esi, esi
0x14004a69f  mov     edx, 87h
0x14004a6a4  mov     dword ptr [rsp+88h+var_68], esi
0x14004a6a8  mov     r8d, r14d
0x14004a6ab  mov     rcx, rbp
0x14004a6ae  xor     r15d, r15d
0x14004a6b1  call    sqlite3VdbeAddOp3
0x14004a6b6  movsx   ecx, word ptr [rdi+36h]
0x14004a6ba  add     ecx, [rbx+38h]
0x14004a6bd  jmp     short loc_14004A730
0x14004a6bf  mov     rsi, [rdi+10h]
0x14004a6c3  jmp     short loc_14004A6D2
0x14004a6c5  mov     eax, [rsi+64h]
0x14004a6c8  and     al, 3
0x14004a6ca  cmp     al, 2
0x14004a6cc  jz      short loc_14004A6D7
0x14004a6ce  mov     rsi, [rsi+28h]
0x14004a6d2  test    rsi, rsi
0x14004a6d5  jnz     short loc_14004A6C5
0x14004a6d7  movzx   ecx, word ptr [rsi+60h]
0x14004a6db  xor     r14d, r14d
0x14004a6de  add     ecx, edx
0x14004a6e0  xor     eax, eax
0x14004a6e2  mov     [rbx+38h], ecx
0x14004a6e5  cmp     ax, [rsi+5Eh]
0x14004a6e9  jnb     short loc_14004A728
0x14004a6eb  mov     r15d, [rsp+88h+arg_18]
0x14004a6f3  lea     r13d, [rdx+1]
0x14004a6f7  lea     eax, [r14+r13]
0x14004a6fb  mov     r9d, r14d
0x14004a6fe  mov     r8d, r15d
0x14004a701  mov     dword ptr [rsp+88h+var_68], eax
0x14004a705  mov     edx, 5Eh ; '^'
0x14004a70a  mov     rcx, rbp
0x14004a70d  call    sqlite3VdbeAddOp3
0x14004a712  movzx   eax, word ptr [rsi+5Eh]
0x14004a716  inc     r14d
0x14004a719  cmp     r14d, eax
0x14004a71c  jl      short loc_14004A6F7
0x14004a71e  mov     ecx, [rbx+38h]
0x14004a721  mov     r13, [rsp+88h+var_48]
0x14004a726  jmp     short loc_14004A72C
0x14004a728  movzx   eax, word ptr [rsi+5Eh]
0x14004a72c  movzx   r15d, ax
0x14004a730  lea     eax, [rcx+1]
0x14004a733  xor     r14d, r14d
0x14004a736  mov     [rbx+38h], eax
0x14004a739  mov     [rsp+88h+var_50], eax
0x14004a73d  xor     eax, eax
0x14004a73f  cmp     ax, [rdi+36h]
0x14004a743  jge     loc_14004A814
0x14004a749  mov     r13d, [rsp+88h+var_58]
0x14004a74e  mov     r12d, [rsp+88h+arg_18]
0x14004a756  mov     ebx, [rsp+88h+var_54]
0x14004a75a  cmp     r14d, ebx
0x14004a75d  jz      loc_14004A7F2
0x14004a763  movsxd  rax, r14d
0x14004a766  lea     rcx, [rax+rax*2]
0x14004a76a  mov     rax, [rdi+8]
0x14004a76e  test    byte ptr [rax+rcx*8+12h], 20h
0x14004a773  jnz     short loc_14004A7F2
0x14004a775  test    rsi, rsi
0x14004a778  jz      short loc_14004A7AB
0x14004a77a  movzx   edx, r14w
0x14004a77e  mov     rcx, rsi
0x14004a781  call    sqlite3TableColumnToIndex
0x14004a786  movsx   r11d, ax
0x14004a78a  movzx   eax, word ptr [rsi+5Eh]
0x14004a78e  cmp     r11d, eax
0x14004a791  jl      short loc_14004A7F2
0x14004a793  movzx   edx, bx
0x14004a796  call    sqlite3TableColumnToIndex
0x14004a79b  movsx   ecx, ax
0x14004a79e  xor     eax, eax
0x14004a7a0  cmp     r11d, ecx
0x14004a7a3  setnle  al
0x14004a7a6  sub     r11d, eax
0x14004a7a9  jmp     short loc_14004A7AE
0x14004a7ab  mov     r11d, r15d
0x14004a7ae  movsx   eax, word ptr [rdi+34h]
0x14004a7b2  lea     ecx, [r13+1]
0x14004a7b6  add     ecx, r11d
0x14004a7b9  cmp     r14d, eax
0x14004a7bc  jnz     short loc_14004A7DA
0x14004a7be  xor     r8d, r8d
0x14004a7c1  mov     dword ptr [rsp+88h+var_68], 0
0x14004a7c9  mov     r9d, ecx
0x14004a7cc  mov     rcx, rbp
0x14004a7cf  lea     edx, [r8+4Bh]
0x14004a7d3  call    sqlite3VdbeAddOp3
0x14004a7d8  jmp     short loc_14004A7EF
0x14004a7da  mov     dword ptr [rsp+88h+var_68], ecx
0x14004a7de  mov     r9d, r14d
0x14004a7e1  mov     rcx, rbp
0x14004a7e4  mov     r8d, r12d
0x14004a7e7  mov     rdx, rdi
0x14004a7ea  call    sqlite3ExprCodeGetColumnOfTable
0x14004a7ef  inc     r15d
0x14004a7f2  movsx   eax, word ptr [rdi+36h]
0x14004a7f6  inc     r14d
0x14004a7f9  cmp     r14d, eax
0x14004a7fc  jl      loc_14004A75A
0x14004a802  mov     rbx, [rsp+88h+arg_0]
0x14004a80a  mov     r13, [rsp+88h+var_48]
0x14004a80f  mov     r12, [rsp+88h+var_40]
0x14004a814  mov     edi, [rsp+88h+var_58]
0x14004a818  test    r15d, r15d
0x14004a81b  jnz     short loc_14004A83E
0x14004a81d  inc     dword ptr [rbx+38h]
0x14004a820  lea     r9d, [rdi+1]
0x14004a824  xor     r8d, r8d
0x14004a827  mov     dword ptr [rsp+88h+var_68], r15d
0x14004a82c  lea     edx, [r15+4Bh]
0x14004a830  mov     rcx, rbp
0x14004a833  call    sqlite3VdbeAddOp3
0x14004a838  mov     r15d, 1
0x14004a83e  mov     r14d, [rsp+88h+var_50]
0x14004a843  lea     ebx, [rdi+1]
0x14004a846  mov     r8d, ebx
0x14004a849  mov     dword ptr [rsp+88h+var_68], r14d
0x14004a84e  mov     r9d, r15d
0x14004a851  mov     edx, 61h ; 'a'
0x14004a856  mov     rcx, rbp
0x14004a859  call    sqlite3VdbeAddOp3
0x14004a85e  mov     r9d, r14d
0x14004a861  mov     rcx, rbp
0x14004a864  test    rsi, rsi
0x14004a867  jz      short loc_14004A88B
0x14004a869  movzx   eax, word ptr [rsi+5Eh]
0x14004a86d  mov     edx, 8Ah
0x14004a872  mov     dword ptr [rsp+88h+var_60], eax
0x14004a876  mov     dword ptr [rsp+88h+var_68], ebx
0x14004a87a  mov     ebx, [rsp+88h+arg_18]
  ... truncated ...
```
