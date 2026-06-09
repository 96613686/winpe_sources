# sqlite3AlterDropColumn

- ea: `0x180076e24`
- end: `0x180077325`
- name: `sqlite3AlterDropColumn`
- size: `1281`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x18001bc30`

## callees

- `0x18000b4bc`
- `0x180014464`
- `0x180027e60`
- `0x18003183c`
- `0x180038974`
- `0x18003cc7c`
- `0x18003d480`
- `0x18003e68c`
- `0x18003f960`
- `0x18004002c`
- `0x180041574`
- `0x180042130`
- `0x180042260`
- `0x180042bb0`
- `0x180042c38`
- `0x180042cd4`
- `0x18006415c`
- `0x18006497c`
- `0x1800736fc`
- `0x18007387c`
- `0x180074120`
- `0x180076e24`
- `0x18007c43c`
- `0x18008b5c4`

## string_xrefs

- `0x180076faf`: `UPDATE "%w".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)`

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
  int v38; // ecx
  __int64 v40; // [rsp+20h] [rbp-78h]
  int v41; // [rsp+30h] [rbp-68h]
  int v42; // [rsp+34h] [rbp-64h]
  int v43; // [rsp+38h] [rbp-60h]
  unsigned int v44; // [rsp+3Ch] [rbp-5Ch]
  __int64 v45; // [rsp+48h] [rbp-50h]
  const char *v46; // [rsp+50h] [rbp-48h]
  int v49; // [rsp+B8h] [rbp+20h]
  __int64 v50; // [rsp+B8h] [rbp+20h]
  char v51; // [rsp+B8h] [rbp+20h]

  v3 = *(_QWORD *)a1;
  v4 = 0;
  v45 = *(_QWORD *)a1;
  v6 = a1;
  if ( *(_BYTE *)(*(_QWORD *)a1 + 103LL) )
    goto LABEL_48;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v8 = TableItem;
  if ( !TableItem )
    goto LABEL_48;
  if ( (unsigned int)isAlterableTable(v6, TableItem) )
    goto LABEL_48;
  if ( (unsigned int)isRealTable(v6, v8, 1) )
    goto LABEL_48;
  v9 = sqlite3NameFromToken(v3, a3);
  v46 = (const char *)v9;
  v4 = (const char *)v9;
  if ( !v9 )
    goto LABEL_48;
  v10 = sqlite3ColumnIndex(v8, v9);
  v49 = v10;
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
    LODWORD(v40) = v49;
    sqlite3NestedParse(
      v6,
      "UPDATE \"%w\".sqlite_master SET sql = sqlite_drop_column(%d, sql, %d) WHERE (type=='table' AND tbl_name=%Q COLLATE nocase)",
      v15,
      (unsigned int)v14,
      v40,
      *(_QWORD *)v8);
    renameReloadSchema(v6, (unsigned int)v14, 2);
    renameTestSchema((__int64)v6, v15, v14 == 1, (__int64)"after drop column", 1);
    if ( !v6[12] && (*(_BYTE *)(*(_QWORD *)(v8 + 8) + 8 * v11 + 18) & 0x20) == 0 )
    {
      Vdbe = sqlite3GetVdbe(v6);
      v17 = v6[13];
      v41 = v17;
      v18 = Vdbe;
      v6[13] = v17 + 1;
      sqlite3OpenTable((_DWORD)v6, v17, v14, v8, 113);
      v19 = sqlite3VdbeAddOp3(v18, 36, v17, 0, 0);
      ++v6[14];
      v44 = v19;
      v42 = v6[14];
      if ( *(char *)(v8 + 48) < 0 )
      {
        v20 = sqlite3PrimaryKeyIndex(v8);
        v25 = 0;
        v23 = v24 + *(unsigned __int16 *)(v20 + 96);
        v6[14] = v23;
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
          v23 = v6[14];
          v3 = v45;
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
        sqlite3VdbeAddOp3(v18, 135, v17, v6[14], 0);
        v23 = v6[14] + *(__int16 *)(v8 + 54);
      }
      v28 = v23 + 1;
      v29 = 0;
      v6[14] = v28;
      v43 = v28;
      if ( *(__int16 *)(v8 + 54) > 0 )
      {
        v30 = v49;
        while ( 1 )
        {
          if ( v29 != v30 )
          {
            v31 = *(_QWORD *)(v8 + 8);
            v50 = v31;
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
                v31 = v50;
                v32 = 3LL * v29;
                v36 = v35 - (v35 > v34);
LABEL_34:
                v37 = v42 + v36;
                if ( v29 == *(__int16 *)(v8 + 52) )
                {
                  sqlite3VdbeAddOp3(v18, 75, 0, v37 + 1, 0);
                }
                else
                {
                  v51 = *(_BYTE *)(v31 + 8 * v32 + 12);
                  if ( v51 == 69 )
                    *(_BYTE *)(v31 + 8 * v32 + 12) = 67;
                  sqlite3ExprCodeGetColumnOfTable(v18, v8, v41, v29, v37 + 1);
                  *(_BYTE *)(*(_QWORD *)(v8 + 8) + 24LL * v29 + 12) = v51;
                }
                ++v21;
              }
            }
          }
          if ( ++v29 >= *(__int16 *)(v8 + 54) )
          {
            v6 = a1;
            v4 = v46;
            v3 = v45;
            break;
          }
        }
      }
      if ( !v21 )
      {
        ++v6[14];
        sqlite3VdbeAddOp3(v18, 75, 0, v42 + 1, 0);
        v21 = 1;
      }
      sqlite3VdbeAddOp3(v18, 97, v42 + 1, v21, v43);
      if ( v20 )
        sqlite3VdbeAddOp4Int(v18, 138, v41, v43, v42 + 1, *(unsigned __int16 *)(v20 + 94));
      else
        sqlite3VdbeAddOp3(v18, 128, v41, v43, v42);
      sqlite3VdbeChangeP5(v18, 2);
      sqlite3VdbeAddOp3(v38, 39, v41, v44 + 1, 0);
      *(_DWORD *)(sqlite3VdbeGetOp(v18, v44) + 8) = *(_DWORD *)(v18 + 144);
    }
  }
LABEL_48:
  sqlite3DbFree(v3, v4);
  return sqlite3SrcListDelete(v3, a2);
}

```

## disassembly

```asm
0x180076e24  mov     [rsp+arg_10], rbx
0x180076e29  mov     [rsp+arg_8], rdx
0x180076e2e  mov     [rsp+arg_0], rcx
0x180076e33  push    rbp
0x180076e34  push    rsi
0x180076e35  push    rdi
0x180076e36  push    r12
0x180076e38  push    r13
0x180076e3a  push    r14
0x180076e3c  push    r15
0x180076e3e  sub     rsp, 60h
0x180076e42  mov     r12, [rcx]
0x180076e45  xor     ebp, ebp
0x180076e47  mov     rbx, r8
0x180076e4a  mov     [rsp+98h+var_50], r12
0x180076e4f  mov     rdi, rcx
0x180076e52  cmp     [r12+67h], bpl
0x180076e57  jnz     loc_1800772F3
0x180076e5d  lea     r8, [rdx+8]
0x180076e61  xor     edx, edx
0x180076e63  call    sqlite3LocateTableItem
0x180076e68  mov     rsi, rax
0x180076e6b  test    rax, rax
0x180076e6e  jz      loc_1800772F3
0x180076e74  mov     rdx, rax
0x180076e77  mov     rcx, rdi
0x180076e7a  call    isAlterableTable
0x180076e7f  test    eax, eax
0x180076e81  jnz     loc_1800772F3
0x180076e87  lea     r15d, [rbp+1]
0x180076e8b  mov     rdx, rsi
0x180076e8e  mov     r8d, r15d
0x180076e91  mov     rcx, rdi
0x180076e94  call    isRealTable
0x180076e99  test    eax, eax
0x180076e9b  jnz     loc_1800772F3
0x180076ea1  mov     rdx, rbx
0x180076ea4  mov     rcx, r12
0x180076ea7  call    sqlite3NameFromToken
0x180076eac  mov     [rsp+98h+var_48], rax
0x180076eb1  mov     rbp, rax
0x180076eb4  test    rax, rax
0x180076eb7  jz      loc_1800772F3
0x180076ebd  mov     rdx, rax
0x180076ec0  mov     rcx, rsi
0x180076ec3  call    sqlite3ColumnIndex
0x180076ec8  mov     dword ptr [rsp+98h+arg_18], eax
0x180076ecf  test    eax, eax
0x180076ed1  jns     short loc_180076EEA
0x180076ed3  mov     r8, rbx
0x180076ed6  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x180076edd  mov     rcx, rdi
0x180076ee0  call    sqlite3ErrorMsg
0x180076ee5  jmp     loc_1800772F3
0x180076eea  cdqe
0x180076eec  lea     r14, [rax+rax*2]
0x180076ef0  mov     rax, [rsi+8]
0x180076ef4  test    byte ptr [rax+r14*8+12h], 9
0x180076efa  jz      short loc_180076F2A
0x180076efc  test    [rax+r14*8+12h], r15b
0x180076f01  lea     r8, aPrimaryKey; "PRIMARY KEY"
0x180076f08  lea     rax, aUnique_0; "UNIQUE"
0x180076f0f  mov     r9, rbp
0x180076f12  cmovz   r8, rax
0x180076f16  lea     rdx, aCannotDropSCol; "cannot drop %s column: \"%s\""
0x180076f1d  mov     rcx, rdi
0x180076f20  call    sqlite3ErrorMsg
0x180076f25  jmp     loc_1800772F3
0x180076f2a  cmp     [rsi+36h], r15w
0x180076f2f  jg      short loc_180076F3D
0x180076f31  mov     r8, rbp
0x180076f34  lea     rdx, aCannotDropColu; "cannot drop column \"%s\": no other col"...
0x180076f3b  jmp     short loc_180076EDD
0x180076f3d  mov     rdx, [rsi+60h]
0x180076f41  mov     rcx, r12
0x180076f44  call    sqlite3SchemaToIndex
0x180076f49  mov     rcx, [r12+20h]
0x180076f4e  mov     r9, [rsi]
0x180076f51  movsxd  r13, eax
0x180076f54  mov     rdx, r13
0x180076f57  mov     [rsp+98h+var_78], rbp
0x180076f5c  shl     rdx, 5
0x180076f60  mov     r15, [rdx+rcx]
0x180076f64  mov     edx, 1Ah
0x180076f69  mov     r8, r15
0x180076f6c  mov     rcx, rdi
0x180076f6f  call    sqlite3AuthCheck
0x180076f74  test    eax, eax
0x180076f76  jnz     loc_1800772F3
0x180076f7c  xor     ebx, ebx
0x180076f7e  mov     dword ptr [rsp+98h+var_78], eax
0x180076f82  cmp     r13d, 1
0x180076f86  lea     r9, Src
0x180076f8d  mov     rdx, r15
0x180076f90  mov     rcx, rdi
0x180076f93  setz    bl
0x180076f96  mov     r8d, ebx
0x180076f99  call    renameTestSchema
0x180076f9e  mov     r8d, ebx
0x180076fa1  mov     rdx, r15
0x180076fa4  mov     rcx, rdi
0x180076fa7  call    renameFixQuotes
0x180076fac  mov     rax, [rsi]
0x180076faf  lea     rdx, aUpdateWSqliteM_0; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180076fb6  mov     [rsp+98h+var_70], rax
0x180076fbb  mov     r9d, r13d
0x180076fbe  mov     eax, dword ptr [rsp+98h+arg_18]
0x180076fc5  mov     r8, r15
0x180076fc8  mov     rcx, rdi
0x180076fcb  mov     dword ptr [rsp+98h+var_78], eax
0x180076fcf  call    sqlite3NestedParse
0x180076fd4  mov     r8d, 2
0x180076fda  mov     edx, r13d
0x180076fdd  mov     rcx, rdi
0x180076fe0  call    renameReloadSchema
0x180076fe5  lea     r9, aAfterDropColum; "after drop column"
0x180076fec  mov     dword ptr [rsp+98h+var_78], 1
0x180076ff4  mov     r8d, ebx
0x180076ff7  mov     rdx, r15
0x180076ffa  mov     rcx, rdi
0x180076ffd  call    renameTestSchema
0x180077002  cmp     dword ptr [rdi+30h], 0
0x180077006  jnz     loc_1800772F3
0x18007700c  mov     rax, [rsi+8]
0x180077010  test    byte ptr [rax+r14*8+12h], 20h
0x180077016  jnz     loc_1800772F3
0x18007701c  mov     rcx, rdi
0x18007701f  call    sqlite3GetVdbe
0x180077024  mov     r15d, [rdi+34h]
0x180077028  mov     r9, rsi
0x18007702b  mov     r8d, r13d
0x18007702e  mov     [rsp+98h+var_68], r15d
0x180077033  mov     edx, r15d
0x180077036  mov     dword ptr [rsp+98h+var_78], 71h ; 'q'
0x18007703e  mov     rbx, rax
0x180077041  lea     ecx, [r15+1]
0x180077045  mov     [rdi+34h], ecx
0x180077048  mov     rcx, rdi
0x18007704b  call    sqlite3OpenTable
0x180077050  xor     r9d, r9d
0x180077053  mov     dword ptr [rsp+98h+var_78], 0
0x18007705b  mov     r8d, r15d
0x18007705e  mov     rcx, rbx
0x180077061  lea     edx, [r9+24h]
0x180077065  call    sqlite3VdbeAddOp3
0x18007706a  inc     dword ptr [rdi+38h]
0x18007706d  test    byte ptr [rsi+30h], 80h
0x180077071  mov     edx, [rdi+38h]
0x180077074  mov     [rsp+98h+var_5C], eax
0x180077078  mov     [rsp+98h+var_64], edx
0x18007707c  jnz     short loc_1800770A5
0x18007707e  mov     r9d, edx
0x180077081  xor     r13d, r13d
0x180077084  mov     edx, 87h
0x180077089  mov     dword ptr [rsp+98h+var_78], r13d
0x18007708e  mov     r8d, r15d
0x180077091  mov     rcx, rbx
0x180077094  xor     r14d, r14d
0x180077097  call    sqlite3VdbeAddOp3
0x18007709c  movsx   eax, word ptr [rsi+36h]
0x1800770a0  add     eax, [rdi+38h]
0x1800770a3  jmp     short loc_180077104
0x1800770a5  mov     rcx, rsi
0x1800770a8  call    sqlite3PrimaryKeyIndex
0x1800770ad  mov     r13, rax
0x1800770b0  xor     r14d, r14d
0x1800770b3  xor     ecx, ecx
0x1800770b5  movzx   eax, word ptr [rax+60h]
0x1800770b9  add     eax, edx
0x1800770bb  mov     [rdi+38h], eax
0x1800770be  cmp     cx, [r13+5Eh]
0x1800770c3  jnb     short loc_1800770FB
0x1800770c5  lea     r12d, [rdx+1]
0x1800770c9  lea     eax, [r12+r14]
0x1800770cd  mov     r9d, r14d
0x1800770d0  mov     r8d, r15d
0x1800770d3  mov     dword ptr [rsp+98h+var_78], eax
0x1800770d7  mov     edx, 5Eh ; '^'
0x1800770dc  mov     rcx, rbx
0x1800770df  call    sqlite3VdbeAddOp3
0x1800770e4  movzx   ecx, word ptr [r13+5Eh]
0x1800770e9  inc     r14d
0x1800770ec  cmp     r14d, ecx
0x1800770ef  jl      short loc_1800770C9
0x1800770f1  mov     eax, [rdi+38h]
0x1800770f4  mov     r12, [rsp+98h+var_50]
0x1800770f9  jmp     short loc_180077100
0x1800770fb  movzx   ecx, word ptr [r13+5Eh]
0x180077100  movzx   r14d, cx
0x180077104  inc     eax
0x180077106  xor     r15d, r15d
0x180077109  mov     [rdi+38h], eax
0x18007710c  mov     [rsp+98h+var_60], eax
0x180077110  xor     eax, eax
0x180077112  cmp     ax, [rsi+36h]
0x180077116  jge     loc_180077233
0x18007711c  mov     r12d, [rsp+98h+var_64]
0x180077121  mov     edi, [rsp+98h+var_68]
0x180077125  mov     ebp, dword ptr [rsp+98h+arg_18]
0x18007712c  cmp     r15d, ebp
0x18007712f  jz      loc_180077211
0x180077135  mov     rdx, [rsi+8]
0x180077139  movsxd  rax, r15d
0x18007713c  mov     [rsp+98h+arg_18], rdx
0x180077144  lea     rcx, [rax+rax*2]
0x180077148  test    byte ptr [rdx+rcx*8+12h], 20h
0x18007714d  mov     [rsp+98h+var_58], rcx
0x180077152  jnz     loc_180077211
0x180077158  test    r13, r13
0x18007715b  jz      short loc_1800771A0
0x18007715d  movzx   edx, r15w
0x180077161  mov     rcx, r13
0x180077164  call    sqlite3TableColumnToIndex
0x180077169  movsx   r11d, ax
0x18007716d  movzx   eax, word ptr [r13+5Eh]
0x180077172  cmp     r11d, eax
0x180077175  jl      loc_180077211
0x18007717b  movzx   edx, bp
0x18007717e  call    sqlite3TableColumnToIndex
0x180077183  mov     rdx, [rsp+98h+arg_18]
0x18007718b  movsx   ecx, ax
0x18007718e  xor     eax, eax
0x180077190  cmp     r11d, ecx
0x180077193  mov     rcx, [rsp+98h+var_58]
0x180077198  setnle  al
0x18007719b  sub     r11d, eax
0x18007719e  jmp     short loc_1800771A3
0x1800771a0  mov     r11d, r14d
0x1800771a3  movsx   eax, word ptr [rsi+34h]
0x1800771a7  lea     r8d, [r12+r11]
0x1800771ab  cmp     r15d, eax
0x1800771ae  jnz     short loc_1800771CD
0x1800771b0  lea     r9d, [r8+1]
0x1800771b4  mov     dword ptr [rsp+98h+var_78], 0
0x1800771bc  xor     r8d, r8d
0x1800771bf  mov     rcx, rbx
0x1800771c2  lea     edx, [r8+4Bh]
0x1800771c6  call    sqlite3VdbeAddOp3
0x1800771cb  jmp     short loc_18007720E
0x1800771cd  mov     al, [rdx+rcx*8+0Ch]
0x1800771d1  mov     byte ptr [rsp+98h+arg_18], al
0x1800771d8  cmp     al, 45h ; 'E'
0x1800771da  jnz     short loc_1800771E1
0x1800771dc  mov     byte ptr [rdx+rcx*8+0Ch], 43h ; 'C'
0x1800771e1  lea     eax, [r8+1]
0x1800771e5  mov     r9d, r15d
0x1800771e8  mov     r8d, edi
0x1800771eb  mov     dword ptr [rsp+98h+var_78], eax
0x1800771ef  mov     rdx, rsi
0x1800771f2  mov     rcx, rbx
0x1800771f5  call    sqlite3ExprCodeGetColumnOfTable
0x1800771fa  mov     rax, [rsi+8]
0x1800771fe  mov     rcx, [rsp+98h+var_58]
0x180077203  mov     dl, byte ptr [rsp+98h+arg_18]
0x18007720a  mov     [rax+rcx*8+0Ch], dl
0x18007720e  inc     r14d
0x180077211  movsx   eax, word ptr [rsi+36h]
0x180077215  inc     r15d
0x180077218  cmp     r15d, eax
0x18007721b  jl      loc_18007712C
0x180077221  mov     rdi, [rsp+98h+arg_0]
0x180077229  mov     rbp, [rsp+98h+var_48]
0x18007722e  mov     r12, [rsp+98h+var_50]
0x180077233  mov     esi, [rsp+98h+var_64]
0x180077237  test    r14d, r14d
0x18007723a  jnz     short loc_18007725D
0x18007723c  inc     dword ptr [rdi+38h]
0x18007723f  lea     r9d, [rsi+1]
0x180077243  xor     r8d, r8d
0x180077246  mov     dword ptr [rsp+98h+var_78], r14d
0x18007724b  lea     edx, [r14+4Bh]
0x18007724f  mov     rcx, rbx
0x180077252  call    sqlite3VdbeAddOp3
0x180077257  mov     r14d, 1
0x18007725d  mov     r15d, [rsp+98h+var_60]
0x180077262  lea     edi, [rsi+1]
0x180077265  mov     r8d, edi
0x180077268  mov     dword ptr [rsp+98h+var_78], r15d
0x18007726d  mov     r9d, r14d
0x180077270  mov     edx, 61h ; 'a'
0x180077275  mov     rcx, rbx
0x180077278  call    sqlite3VdbeAddOp3
0x18007727d  mov     r8d, [rsp+98h+var_68]
0x180077282  mov     r9d, r15d
0x180077285  mov     rcx, rbx
0x180077288  test    r13, r13
0x18007728b  jz      short loc_1800772A6
0x18007728d  movzx   eax, word ptr [r13+5Eh]
0x180077292  mov     edx, 8Ah
0x180077297  mov     dword ptr [rsp+98h+var_70], eax
0x18007729b  mov     dword ptr [rsp+98h+var_78], edi
0x18007729f  call    sqlite3VdbeAddOp4Int
0x1800772a4  jmp     short loc_1800772B4
0x1800772a6  mov     edx, 80h
0x1800772ab  mov     dword ptr [rsp+98h+var_78], esi
0x1800772af  call    sqlite3VdbeAddOp3
0x1800772b4  mov     edx, 2
0x1800772b9  mov     rcx, rbx
0x1800772bc  call    sqlite3VdbeChangeP5
0x1800772c1  mov     edi, [rsp+98h+var_5C]
  ... truncated ...
```
