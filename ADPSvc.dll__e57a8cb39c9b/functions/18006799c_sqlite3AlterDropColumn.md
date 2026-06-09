# sqlite3AlterDropColumn

- ea: `0x18006799c`
- end: `0x180067ef1`
- name: `sqlite3AlterDropColumn`
- size: `1365`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x1800c3bd8`

## callees

- `0x18004c564`
- `0x18004cf78`
- `0x180061040`
- `0x180061bb4`
- `0x18006799c`
- `0x1800693b0`
- `0x18006f1c0`
- `0x1800716fc`
- `0x180073aec`
- `0x180074ab0`
- `0x18007d478`
- `0x180080774`
- `0x180081754`
- `0x1800817f4`
- `0x180081ad0`
- `0x18008e124`
- `0x18008f318`
- `0x1800923d8`
- `0x1800924d4`
- `0x18009a3b4`

## string_xrefs

- `0x180067b36`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x180067b4d`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x180067b5f`: `UPDATE "%w".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)`

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
  int v20; // r15d
  __int64 v21; // rbp
  unsigned int v22; // eax
  int v23; // edx
  __int64 i; // rsi
  int v25; // r14d
  int v26; // ecx
  int v27; // r14d
  int v28; // r13d
  int v29; // eax
  int v30; // r15d
  int v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int16 v35; // ax
  int v36; // r11d
  int v37; // r11d
  int v38; // r8d
  __int64 v39; // rax
  __int64 v41; // [rsp+20h] [rbp-78h]
  int v42; // [rsp+30h] [rbp-68h]
  int v43; // [rsp+34h] [rbp-64h]
  int v44; // [rsp+38h] [rbp-60h]
  unsigned int v45; // [rsp+3Ch] [rbp-5Ch]
  __int64 v46; // [rsp+48h] [rbp-50h]
  int v49; // [rsp+B8h] [rbp+20h]
  __int64 v50; // [rsp+B8h] [rbp+20h]
  char v51; // [rsp+B8h] [rbp+20h]

  v3 = *(_QWORD *)a1;
  v5 = a2;
  v46 = *(_QWORD *)a1;
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
          v49 = v11;
          if ( v11 < 0 )
          {
            sqlite3ErrorMsg(v6, "no such column: \"%T\"", a3);
LABEL_59:
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
            goto LABEL_59;
          }
          if ( *(__int16 *)(v8 + 54) <= 1 )
          {
            sqlite3ErrorMsg(v6, "cannot drop column \"%s\": no other columns exist", v10);
            goto LABEL_59;
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
            renameTestSchema((_DWORD)v6, v18, v16 == 1, (unsigned int)&Src, 0);
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
            LODWORD(v41) = v49;
            sqlite3NestedParse(
              v6,
              "UPDATE \"%w\".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q"
              " COLLATE nocase)",
              v18,
              (unsigned int)v16,
              v41,
              *(_QWORD *)v8);
            renameReloadSchema(v6, (unsigned int)v16, 2);
            renameTestSchema((_DWORD)v6, v18, v16 == 1, (unsigned int)"after drop column", 1);
            if ( !v6[12] && (*(_BYTE *)(*(_QWORD *)(v8 + 8) + 8 * v12 + 18) & 0x20) == 0 )
            {
              Vdbe = sqlite3GetVdbe(v6);
              v20 = v6[13];
              v43 = v20;
              v21 = Vdbe;
              v6[13] = v20 + 1;
              sqlite3OpenTable((_DWORD)v6, v20, v16, v8, 113);
              v22 = sqlite3VdbeAddOp3(v21, 36, v20, 0, 0);
              v23 = ++v6[14];
              v45 = v22;
              v42 = v23;
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
                    sqlite3VdbeAddOp3(v21, 94, v20, v27, v27 + v28);
                    v29 = *(unsigned __int16 *)(i + 94);
                    ++v27;
                  }
                  while ( v27 < v29 );
                  v26 = v6[14];
                  v3 = v46;
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
              v44 = v26 + 1;
              if ( *(__int16 *)(v8 + 54) > 0 )
              {
                v31 = v49;
                while ( 1 )
                {
                  if ( v30 != v31 )
                  {
                    v32 = *(_QWORD *)(v8 + 8);
                    v50 = v32;
                    v33 = 3LL * v30;
                    if ( (*(_BYTE *)(v32 + 24LL * v30 + 18) & 0x20) == 0 )
                    {
                      if ( !i )
                      {
                        v37 = v25;
                        goto LABEL_42;
                      }
                      if ( (__int16)sqlite3TableColumnToIndex(i, (unsigned __int16)v30) >= (int)*(unsigned __int16 *)(i + 94) )
                      {
                        v35 = sqlite3TableColumnToIndex(v34, (unsigned __int16)v31);
                        v32 = v50;
                        v33 = 3LL * v30;
                        v37 = v36 - (v36 > v35);
LABEL_42:
                        v38 = v37 + v42;
                        if ( v30 == *(__int16 *)(v8 + 52) )
                        {
                          sqlite3VdbeAddOp3(v21, 75, 0, v38 + 1, 0);
                        }
                        else
                        {
                          v51 = *(_BYTE *)(v32 + 8 * v33 + 12);
                          if ( v51 == 69 )
                            *(_BYTE *)(v32 + 8 * v33 + 12) = 67;
                          sqlite3ExprCodeGetColumnOfTable(v21, v8, v43, v30, v38 + 1);
                          *(_BYTE *)(*(_QWORD *)(v8 + 8) + 24LL * v30 + 12) = v51;
                        }
                        ++v25;
                      }
                    }
                  }
                  if ( ++v30 >= *(__int16 *)(v8 + 54) )
                  {
                    v6 = a1;
                    v3 = v46;
                    break;
                  }
                }
              }
              if ( !v25 )
              {
                ++v6[14];
                sqlite3VdbeAddOp3(v21, 75, 0, v42 + 1, 0);
                v25 = 1;
              }
              sqlite3VdbeAddOp3(v21, 97, v42 + 1, v25, v44);
              if ( i )
                sqlite3VdbeAddOp4Int(v21, 138, v43, v44, v42 + 1, *(unsigned __int16 *)(i + 94));
              else
                sqlite3VdbeAddOp3(v21, 128, v43, v44, v42);
              v39 = *(int *)(v21 + 144);
              if ( (int)v39 > 0 )
                *(_WORD *)(*(_QWORD *)(v21 + 136) + 24 * v39 - 22) = 2;
              sqlite3VdbeAddOp3(v21, 39, v43, v45 + 1, 0);
              sqlite3VdbeJumpHere(v21, v45);
            }
          }
          v5 = a2;
          goto LABEL_59;
        }
      }
    }
  }
  return sqlite3SrcListDelete(v3, v5);
}

```

## disassembly

```asm
0x18006799c  mov     [rsp+arg_10], rbx
0x1800679a1  mov     [rsp+arg_8], rdx
0x1800679a6  mov     [rsp+arg_0], rcx
0x1800679ab  push    rbp
0x1800679ac  push    rsi
0x1800679ad  push    rdi
0x1800679ae  push    r12
0x1800679b0  push    r13
0x1800679b2  push    r14
0x1800679b4  push    r15
0x1800679b6  sub     rsp, 60h
0x1800679ba  mov     r13, [rcx]
0x1800679bd  mov     rsi, r8
0x1800679c0  mov     rbp, rdx
0x1800679c3  mov     [rsp+98h+var_50], r13
0x1800679c8  mov     rbx, rcx
0x1800679cb  cmp     byte ptr [r13+67h], 0
0x1800679d0  jnz     loc_180067ECF
0x1800679d6  lea     r8, [rdx+8]
0x1800679da  xor     edx, edx
0x1800679dc  call    sqlite3LocateTableItem
0x1800679e1  mov     rdi, rax
0x1800679e4  test    rax, rax
0x1800679e7  jz      loc_180067ECF
0x1800679ed  mov     rdx, rax
0x1800679f0  mov     rcx, rbx
0x1800679f3  call    isAlterableTable
0x1800679f8  test    eax, eax
0x1800679fa  jnz     loc_180067ECF
0x180067a00  lea     r14d, [rax+1]
0x180067a04  mov     rdx, rdi
0x180067a07  mov     r8d, r14d
0x180067a0a  mov     rcx, rbx
0x180067a0d  call    isRealTable
0x180067a12  test    eax, eax
0x180067a14  jnz     loc_180067ECF
0x180067a1a  mov     rdx, rsi
0x180067a1d  mov     rcx, r13
0x180067a20  call    sqlite3NameFromToken
0x180067a25  mov     [rsp+98h+var_48], rax
0x180067a2a  mov     r12, rax
0x180067a2d  test    rax, rax
0x180067a30  jz      loc_180067ECF
0x180067a36  mov     rdx, rax
0x180067a39  mov     rcx, rdi
0x180067a3c  call    sqlite3ColumnIndex
0x180067a41  mov     dword ptr [rsp+98h+arg_18], eax
0x180067a48  test    eax, eax
0x180067a4a  jns     short loc_180067A63
0x180067a4c  mov     r8, rsi
0x180067a4f  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x180067a56  mov     rcx, rbx
0x180067a59  call    sqlite3ErrorMsg
0x180067a5e  jmp     loc_180067EC4
0x180067a63  cdqe
0x180067a65  lea     r15, [rax+rax*2]
0x180067a69  mov     rax, [rdi+8]
0x180067a6d  test    byte ptr [rax+r15*8+12h], 9
0x180067a73  jz      short loc_180067AA3
0x180067a75  test    [rax+r15*8+12h], r14b
0x180067a7a  lea     r8, aPrimaryKey; "PRIMARY KEY"
0x180067a81  lea     rax, aUnique_0; "UNIQUE"
0x180067a88  mov     r9, r12
0x180067a8b  cmovz   r8, rax
0x180067a8f  lea     rdx, aCannotDropSCol; "cannot drop %s column: \"%s\""
0x180067a96  mov     rcx, rbx
0x180067a99  call    sqlite3ErrorMsg
0x180067a9e  jmp     loc_180067EC4
0x180067aa3  cmp     [rdi+36h], r14w
0x180067aa8  jg      short loc_180067AB6
0x180067aaa  mov     r8, r12
0x180067aad  lea     rdx, aCannotDropColu; "cannot drop column \"%s\": no other col"...
0x180067ab4  jmp     short loc_180067A56
0x180067ab6  mov     rcx, [rdi+60h]
0x180067aba  mov     esi, 0FFFF8000h
0x180067abf  test    rcx, rcx
0x180067ac2  jz      short loc_180067AE1
0x180067ac4  mov     rdx, [r13+20h]
0x180067ac8  xor     esi, esi
0x180067aca  cmp     [rdx+18h], rcx
0x180067ace  jz      short loc_180067AE1
0x180067ad0  add     esi, r14d
0x180067ad3  movsxd  rax, esi
0x180067ad6  shl     rax, 5
0x180067ada  cmp     [rax+rdx+18h], rcx
0x180067adf  jnz     short loc_180067AD0
0x180067ae1  mov     rax, [r13+20h]
0x180067ae5  mov     edx, 1Ah
0x180067aea  mov     r9, [rdi]
0x180067aed  movsxd  rcx, esi
0x180067af0  shl     rcx, 5
0x180067af4  mov     [rsp+98h+var_78], r12
0x180067af9  mov     rbp, [rcx+rax]
0x180067afd  mov     rcx, rbx
0x180067b00  mov     r8, rbp
0x180067b03  call    sqlite3AuthCheck
0x180067b08  test    eax, eax
0x180067b0a  jnz     loc_180067EBC
0x180067b10  xor     r14d, r14d
0x180067b13  mov     dword ptr [rsp+98h+var_78], eax
0x180067b17  cmp     esi, 1
0x180067b1a  lea     r9, Src
0x180067b21  mov     rdx, rbp
0x180067b24  mov     rcx, rbx
0x180067b27  setz    r14b
0x180067b2b  mov     r8d, r14d
0x180067b2e  call    renameTestSchema
0x180067b33  mov     r9, rbp
0x180067b36  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180067b3d  mov     r8, rbp
0x180067b40  mov     rcx, rbx
0x180067b43  call    sqlite3NestedParse
0x180067b48  cmp     esi, 1
0x180067b4b  jz      short loc_180067B5C
0x180067b4d  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x180067b54  mov     rcx, rbx
0x180067b57  call    sqlite3NestedParse
0x180067b5c  mov     rax, [rdi]
0x180067b5f  lea     rdx, aUpdateWSqliteM_0; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180067b66  mov     [rsp+98h+var_70], rax
0x180067b6b  mov     r9d, esi
0x180067b6e  mov     eax, dword ptr [rsp+98h+arg_18]
0x180067b75  mov     r8, rbp
0x180067b78  mov     rcx, rbx
0x180067b7b  mov     dword ptr [rsp+98h+var_78], eax
0x180067b7f  call    sqlite3NestedParse
0x180067b84  mov     r8d, 2
0x180067b8a  mov     edx, esi
0x180067b8c  mov     rcx, rbx
0x180067b8f  call    renameReloadSchema
0x180067b94  lea     r9, aAfterDropColum; "after drop column"
0x180067b9b  mov     dword ptr [rsp+98h+var_78], 1
0x180067ba3  mov     r8d, r14d
0x180067ba6  mov     rdx, rbp
0x180067ba9  mov     rcx, rbx
0x180067bac  call    renameTestSchema
0x180067bb1  cmp     dword ptr [rbx+30h], 0
0x180067bb5  jnz     loc_180067EBC
0x180067bbb  mov     rax, [rdi+8]
0x180067bbf  test    byte ptr [rax+r15*8+12h], 20h
0x180067bc5  jnz     loc_180067EBC
0x180067bcb  mov     rcx, rbx
0x180067bce  call    sqlite3GetVdbe
0x180067bd3  mov     r15d, [rbx+34h]
0x180067bd7  mov     r9, rdi
0x180067bda  mov     r8d, esi
0x180067bdd  mov     [rsp+98h+var_64], r15d
0x180067be2  mov     edx, r15d
0x180067be5  mov     dword ptr [rsp+98h+var_78], 71h ; 'q'
0x180067bed  mov     rbp, rax
0x180067bf0  lea     ecx, [r15+1]
0x180067bf4  mov     [rbx+34h], ecx
0x180067bf7  mov     rcx, rbx
0x180067bfa  call    sqlite3OpenTable
0x180067bff  xor     r9d, r9d
0x180067c02  mov     dword ptr [rsp+98h+var_78], 0
0x180067c0a  mov     r8d, r15d
0x180067c0d  mov     rcx, rbp
0x180067c10  lea     edx, [r9+24h]
0x180067c14  call    sqlite3VdbeAddOp3
0x180067c19  inc     dword ptr [rbx+38h]
0x180067c1c  test    byte ptr [rdi+30h], 80h
0x180067c20  mov     edx, [rbx+38h]
0x180067c23  mov     [rsp+98h+var_5C], eax
0x180067c27  mov     [rsp+98h+var_68], edx
0x180067c2b  jnz     short loc_180067C52
0x180067c2d  mov     r9d, edx
0x180067c30  xor     esi, esi
0x180067c32  mov     edx, 87h
0x180067c37  mov     dword ptr [rsp+98h+var_78], esi
0x180067c3b  mov     r8d, r15d
0x180067c3e  mov     rcx, rbp
0x180067c41  xor     r14d, r14d
0x180067c44  call    sqlite3VdbeAddOp3
0x180067c49  movsx   ecx, word ptr [rdi+36h]
0x180067c4d  add     ecx, [rbx+38h]
0x180067c50  jmp     short loc_180067CBB
0x180067c52  mov     rsi, [rdi+10h]
0x180067c56  jmp     short loc_180067C65
0x180067c58  mov     eax, [rsi+64h]
0x180067c5b  and     al, 3
0x180067c5d  cmp     al, 2
0x180067c5f  jz      short loc_180067C6A
0x180067c61  mov     rsi, [rsi+28h]
0x180067c65  test    rsi, rsi
0x180067c68  jnz     short loc_180067C58
0x180067c6a  movzx   ecx, word ptr [rsi+60h]
0x180067c6e  xor     r14d, r14d
0x180067c71  add     ecx, edx
0x180067c73  xor     eax, eax
0x180067c75  mov     [rbx+38h], ecx
0x180067c78  cmp     ax, [rsi+5Eh]
0x180067c7c  jnb     short loc_180067CB3
0x180067c7e  lea     r13d, [rdx+1]
0x180067c82  lea     eax, [r14+r13]
0x180067c86  mov     r9d, r14d
0x180067c89  mov     r8d, r15d
0x180067c8c  mov     dword ptr [rsp+98h+var_78], eax
0x180067c90  mov     edx, 5Eh ; '^'
0x180067c95  mov     rcx, rbp
0x180067c98  call    sqlite3VdbeAddOp3
0x180067c9d  movzx   eax, word ptr [rsi+5Eh]
0x180067ca1  inc     r14d
0x180067ca4  cmp     r14d, eax
0x180067ca7  jl      short loc_180067C82
0x180067ca9  mov     ecx, [rbx+38h]
0x180067cac  mov     r13, [rsp+98h+var_50]
0x180067cb1  jmp     short loc_180067CB7
0x180067cb3  movzx   eax, word ptr [rsi+5Eh]
0x180067cb7  movzx   r14d, ax
0x180067cbb  lea     eax, [rcx+1]
0x180067cbe  xor     r15d, r15d
0x180067cc1  mov     [rbx+38h], eax
0x180067cc4  mov     [rsp+98h+var_60], eax
0x180067cc8  xor     eax, eax
0x180067cca  cmp     ax, [rdi+36h]
0x180067cce  jge     loc_180067DEB
0x180067cd4  mov     r13d, [rsp+98h+var_68]
0x180067cd9  mov     r12d, [rsp+98h+var_64]
0x180067cde  mov     ebx, dword ptr [rsp+98h+arg_18]
0x180067ce5  cmp     r15d, ebx
0x180067ce8  jz      loc_180067DC9
0x180067cee  mov     rdx, [rdi+8]
0x180067cf2  movsxd  rax, r15d
0x180067cf5  mov     [rsp+98h+arg_18], rdx
0x180067cfd  lea     rcx, [rax+rax*2]
0x180067d01  test    byte ptr [rdx+rcx*8+12h], 20h
0x180067d06  mov     [rsp+98h+var_58], rcx
0x180067d0b  jnz     loc_180067DC9
0x180067d11  test    rsi, rsi
0x180067d14  jz      short loc_180067D58
0x180067d16  movzx   edx, r15w
0x180067d1a  mov     rcx, rsi
0x180067d1d  call    sqlite3TableColumnToIndex
0x180067d22  movsx   r11d, ax
0x180067d26  movzx   eax, word ptr [rsi+5Eh]
0x180067d2a  cmp     r11d, eax
0x180067d2d  jl      loc_180067DC9
0x180067d33  movzx   edx, bx
0x180067d36  call    sqlite3TableColumnToIndex
0x180067d3b  mov     rdx, [rsp+98h+arg_18]
0x180067d43  movsx   ecx, ax
0x180067d46  xor     eax, eax
0x180067d48  cmp     r11d, ecx
0x180067d4b  mov     rcx, [rsp+98h+var_58]
0x180067d50  setnle  al
0x180067d53  sub     r11d, eax
0x180067d56  jmp     short loc_180067D5B
0x180067d58  mov     r11d, r14d
0x180067d5b  movsx   eax, word ptr [rdi+34h]
0x180067d5f  lea     r8d, [r11+r13]
0x180067d63  cmp     r15d, eax
0x180067d66  jnz     short loc_180067D85
0x180067d68  lea     r9d, [r8+1]
0x180067d6c  mov     dword ptr [rsp+98h+var_78], 0
0x180067d74  xor     r8d, r8d
0x180067d77  mov     rcx, rbp
0x180067d7a  lea     edx, [r8+4Bh]
0x180067d7e  call    sqlite3VdbeAddOp3
0x180067d83  jmp     short loc_180067DC6
0x180067d85  mov     al, [rdx+rcx*8+0Ch]
0x180067d89  mov     byte ptr [rsp+98h+arg_18], al
0x180067d90  cmp     al, 45h ; 'E'
0x180067d92  jnz     short loc_180067D99
0x180067d94  mov     byte ptr [rdx+rcx*8+0Ch], 43h ; 'C'
0x180067d99  lea     eax, [r8+1]
0x180067d9d  mov     r9d, r15d
0x180067da0  mov     r8d, r12d
0x180067da3  mov     dword ptr [rsp+98h+var_78], eax
0x180067da7  mov     rdx, rdi
0x180067daa  mov     rcx, rbp
0x180067dad  call    sqlite3ExprCodeGetColumnOfTable
0x180067db2  mov     rax, [rdi+8]
0x180067db6  mov     rcx, [rsp+98h+var_58]
0x180067dbb  mov     dl, byte ptr [rsp+98h+arg_18]
0x180067dc2  mov     [rax+rcx*8+0Ch], dl
0x180067dc6  inc     r14d
0x180067dc9  movsx   eax, word ptr [rdi+36h]
0x180067dcd  inc     r15d
0x180067dd0  cmp     r15d, eax
0x180067dd3  jl      loc_180067CE5
0x180067dd9  mov     rbx, [rsp+98h+arg_0]
0x180067de1  mov     r13, [rsp+98h+var_50]
0x180067de6  mov     r12, [rsp+98h+var_48]
0x180067deb  mov     r15d, [rsp+98h+var_68]
0x180067df0  test    r14d, r14d
0x180067df3  jnz     short loc_180067E16
0x180067df5  inc     dword ptr [rbx+38h]
0x180067df8  lea     r9d, [r15+1]
0x180067dfc  xor     r8d, r8d
0x180067dff  mov     dword ptr [rsp+98h+var_78], r14d
0x180067e04  lea     edx, [r14+4Bh]
0x180067e08  mov     rcx, rbp
0x180067e0b  call    sqlite3VdbeAddOp3
0x180067e10  mov     r14d, 1
0x180067e16  mov     edi, [rsp+98h+var_60]
0x180067e1a  lea     ebx, [r15+1]
0x180067e1e  mov     r8d, ebx
0x180067e21  mov     dword ptr [rsp+98h+var_78], edi
0x180067e25  mov     r9d, r14d
  ... truncated ...
```
