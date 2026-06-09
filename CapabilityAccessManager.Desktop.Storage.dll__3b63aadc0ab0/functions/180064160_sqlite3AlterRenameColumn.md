# sqlite3AlterRenameColumn

- ea: `0x180064160`
- end: `0x180064602`
- name: `sqlite3AlterRenameColumn`
- size: `1186`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x1800d8b00`

## callees

- `0x180005980`
- `0x180045f70`
- `0x18004dba0`
- `0x18005acd0`
- `0x18005b0a0`
- `0x18005b6f0`
- `0x180064160`
- `0x1800658d0`
- `0x1800743d0`
- `0x180087d40`
- `0x180088db0`
- `0x180088ea0`
- `0x18009bde0`

## string_xrefs

- `0x1800643a0`: `SELECT 1 FROM "%w".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL `
- `0x1800643ec`: `SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL `
- `0x1800644db`: `after rename`
- `0x18006422e`: `rename columns of`
- `0x180064462`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`
- `0x18006449b`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameColumn(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r10
  __int64 *v5; // rsi
  _QWORD *v6; // rdi
  __int64 *v7; // r15
  _QWORD *v9; // r12
  __int64 v11; // r8
  int v12; // r9d
  __int64 v13; // r9
  __int64 Table; // rax
  __int64 v15; // rbx
  const char *v16; // r9
  __int64 result; // rax
  __int64 v18; // rcx
  int v19; // r14d
  __int64 v20; // rdx
  int v21; // r10d
  int i; // ebp
  __int64 *v23; // r9
  _BYTE *j; // r8
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // [rsp+B0h] [rbp+8h]

  v4 = a2[1];
  v5 = 0;
  v6 = *(_QWORD **)a1;
  v7 = 0;
  v9 = a2;
  if ( v4 )
  {
    v11 = v6[4];
    v12 = 0;
    if ( *(_QWORD *)(v11 + 24) != v4 )
    {
      do
        ++v12;
      while ( *(_QWORD *)(32LL * v12 + v11 + 24) != v4 );
    }
    v13 = *(_QWORD *)(32LL * v12 + v11);
  }
  else
  {
    v13 = a2[2];
  }
  Table = sqlite3LocateTable(a1, 0, a2[3], v13);
  v15 = Table;
  if ( Table && !(unsigned int)isAlterableTable(a1, Table) )
  {
    v16 = "view";
    if ( *(_BYTE *)(v15 + 63) != 2 )
      v16 = 0;
    if ( *(_BYTE *)(v15 + 63) == 1 )
    {
      v16 = "virtual table";
LABEL_13:
      sqlite3ErrorMsg(a1, "cannot %s %s \"%s\"", "rename columns of", v16, *(const char **)v15);
      return sqlite3SrcListDelete(v6, v9);
    }
    if ( v16 )
      goto LABEL_13;
    v18 = *(_QWORD *)(v15 + 96);
    v19 = -32768;
    if ( v18 )
    {
      v20 = v6[4];
      v19 = 0;
      if ( *(_QWORD *)(v20 + 24) != v18 )
      {
        do
          ++v19;
        while ( *(_QWORD *)(32LL * v19 + v20 + 24) != v18 );
      }
    }
    v28 = *(_QWORD *)(32LL * v19 + v6[4]);
    if ( !(unsigned int)sqlite3AuthCheck(a1, 26, v28, *(_QWORD *)v15, 0) )
    {
      v5 = (__int64 *)sqlite3NameFromToken(v6, a3);
      if ( v5 )
      {
        v21 = *(__int16 *)(v15 + 54);
        for ( i = 0; i < v21; ++i )
        {
          v23 = v5;
          for ( j = *(_BYTE **)(*(_QWORD *)(v15 + 8) + 24LL * i); ; ++j )
          {
            while ( 1 )
            {
              v25 = (unsigned __int8)*j;
              v26 = *(unsigned __int8 *)v23;
              if ( (_DWORD)v25 != (_DWORD)v26 )
                break;
              if ( !*j )
                goto LABEL_27;
              ++j;
              v23 = (__int64 *)((char *)v23 + 1);
            }
            if ( *((unsigned __int8 *)qword_180114680 + v25) != *((unsigned __int8 *)qword_180114680 + v26) )
              break;
            v23 = (__int64 *)((char *)v23 + 1);
          }
        }
LABEL_27:
        if ( i == v21 )
        {
          sqlite3ErrorMsg(a1, "no such column: \"%T\"", a3);
          sqlite3SrcListDelete(v6, v9);
          goto LABEL_37;
        }
        *(_BYTE *)(a1 + 28) = 1;
        sqlite3NestedParse(
          a1,
          "SELECT 1 FROM \"%w\".sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtua"
          "l%%' AND sqlite_rename_test(%Q, sql, type, name, %d, %Q, %d)=NULL ",
          v28);
        if ( v19 != 1 )
          sqlite3NestedParse(
            a1,
            "SELECT 1 FROM temp.sqlite_master WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtua"
            "l%%' AND sqlite_rename_test(%Q, sql, type, name, 1, %Q, %d)=NULL ",
            v28);
        renameFixQuotes(a1, v28, v19 == 1);
        v27 = a1;
        if ( *(_QWORD *)(a1 + 168) )
          v27 = *(_QWORD *)(a1 + 168);
        *(_BYTE *)(v27 + 33) = 1;
        v7 = (__int64 *)sqlite3NameFromToken(v6, a4);
        if ( v7 )
        {
          sqlite3NestedParse(
            a1,
            "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE na"
            "me NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)",
            v28);
          sqlite3NestedParse(
            a1,
            "UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type "
            "IN ('trigger', 'view')",
            v28);
          renameReloadSchema(a1, (unsigned int)v19, 1);
          renameTestSchema(a1, v28, v19 == 1, (unsigned int)"after rename", 1);
          sqlite3SrcListDelete(v6, a2);
          goto LABEL_37;
        }
        v9 = a2;
      }
    }
  }
  result = sqlite3SrcListDelete(v6, v9);
  if ( v5 )
  {
LABEL_37:
    if ( v6 )
    {
      if ( (unsigned __int64)v5 < v6[62] )
      {
        if ( (unsigned __int64)v5 >= v6[60] )
        {
          result = v6[59];
          *v5 = result;
          v6[59] = v5;
          goto LABEL_46;
        }
        if ( (unsigned __int64)v5 >= v6[61] )
        {
          result = v6[57];
          *v5 = result;
          v6[57] = v5;
          goto LABEL_46;
        }
      }
      if ( v6[97] )
      {
        result = measureAllocationSize(v6, v5);
        goto LABEL_46;
      }
    }
    result = sqlite3_free(v5);
  }
LABEL_46:
  if ( !v7 )
    return result;
  if ( !v6 )
    return sqlite3_free(v7);
  if ( (unsigned __int64)v7 < v6[62] )
  {
    if ( (unsigned __int64)v7 >= v6[60] )
    {
      result = v6[59];
      *v7 = result;
      v6[59] = v7;
      return result;
    }
    if ( (unsigned __int64)v7 >= v6[61] )
    {
      result = v6[57];
      *v7 = result;
      v6[57] = v7;
      return result;
    }
  }
  if ( v6[97] )
    return measureAllocationSize(v6, v7);
  else
    return sqlite3_free(v7);
}

```

## disassembly

```asm
0x180064160  mov     [rsp+arg_18], r9
0x180064165  mov     [rsp+arg_10], r8
0x18006416a  mov     [rsp+arg_8], rdx
0x18006416f  push    rbx
0x180064170  push    rbp
0x180064171  push    rsi
0x180064172  push    rdi
0x180064173  push    r12
0x180064175  push    r13
0x180064177  push    r15
0x180064179  sub     rsp, 70h
0x18006417d  mov     r10, [rdx+8]
0x180064181  xor     esi, esi
0x180064183  mov     rdi, [rcx]
0x180064186  xor     r15d, r15d
0x180064189  mov     rbp, r8
0x18006418c  mov     r12, rdx
0x18006418f  mov     r13, rcx
0x180064192  test    r10, r10
0x180064195  jz      short loc_1800641CE
0x180064197  mov     r8, [rdi+20h]
0x18006419b  xor     r9d, r9d
0x18006419e  cmp     [r8+18h], r10
0x1800641a2  jz      short loc_1800641C1
0x1800641a4  nop     dword ptr [rax+00h]
0x1800641a8  nop     dword ptr [rax+rax+00000000h]
0x1800641b0  inc     r9d
0x1800641b3  movsxd  rax, r9d
0x1800641b6  shl     rax, 5
0x1800641ba  cmp     [rax+r8+18h], r10
0x1800641bf  jnz     short loc_1800641B0
0x1800641c1  movsxd  rax, r9d
0x1800641c4  shl     rax, 5
0x1800641c8  mov     r9, [rax+r8]
0x1800641cc  jmp     short loc_1800641D2
0x1800641ce  mov     r9, [rdx+10h]
0x1800641d2  mov     r8, [rdx+18h]
0x1800641d6  xor     edx, edx
0x1800641d8  mov     [rsp+0A8h+var_40], r14
0x1800641dd  call    sqlite3LocateTable
0x1800641e2  mov     [rsp+0A8h+var_58], rax
0x1800641e7  mov     rbx, rax
0x1800641ea  test    rax, rax
0x1800641ed  jz      loc_18006450F
0x1800641f3  mov     rdx, rax
0x1800641f6  mov     rcx, r13
0x1800641f9  call    isAlterableTable
0x1800641fe  test    eax, eax
0x180064200  jnz     loc_18006450F
0x180064206  xor     eax, eax
0x180064208  lea     r9, aView_0; "view"
0x18006420f  cmp     byte ptr [rbx+3Fh], 2
0x180064213  cmovnz  r9, rax
0x180064217  cmp     byte ptr [rbx+3Fh], 1
0x18006421b  jnz     short loc_180064226
0x18006421d  lea     r9, aVirtualTable; "virtual table"
0x180064224  jmp     short loc_18006422B
0x180064226  test    r9, r9
0x180064229  jz      short loc_180064259
0x18006422b  mov     rax, [rbx]
0x18006422e  lea     r8, aRenameColumnsO; "rename columns of"
0x180064235  lea     rdx, aCannotSSS; "cannot %s %s \"%s\""
0x18006423c  mov     [rsp+0A8h+var_88], rax
0x180064241  mov     rcx, r13
0x180064244  call    sqlite3ErrorMsg
0x180064249  mov     rdx, r12
0x18006424c  mov     rcx, rdi
0x18006424f  call    sqlite3SrcListDelete
0x180064254  jmp     loc_1800645EE
0x180064259  mov     rcx, [rbx+60h]
0x18006425d  mov     r14d, 0FFFF8000h
0x180064263  test    rcx, rcx
0x180064266  jz      short loc_180064291
0x180064268  mov     rdx, [rdi+20h]
0x18006426c  xor     r14d, r14d
0x18006426f  cmp     [rdx+18h], rcx
0x180064273  jz      short loc_180064291
0x180064275  nop     word ptr [rax+rax+00000000h]
0x180064280  inc     r14d
0x180064283  movsxd  rax, r14d
0x180064286  shl     rax, 5
0x18006428a  cmp     [rax+rdx+18h], rcx
0x18006428f  jnz     short loc_180064280
0x180064291  mov     rax, [rdi+20h]
0x180064295  mov     edx, 1Ah
0x18006429a  mov     r9, [rbx]
0x18006429d  movsxd  rcx, r14d
0x1800642a0  shl     rcx, 5
0x1800642a4  mov     [rsp+0A8h+var_88], rsi
0x1800642a9  mov     rax, [rcx+rax]
0x1800642ad  mov     rcx, r13
0x1800642b0  mov     r8, rax
0x1800642b3  mov     [rsp+0A8h+arg_0], rax
0x1800642bb  call    sqlite3AuthCheck
0x1800642c0  test    eax, eax
0x1800642c2  jnz     loc_18006450F
0x1800642c8  mov     rdx, rbp
0x1800642cb  mov     rcx, rdi
0x1800642ce  call    sqlite3NameFromToken
0x1800642d3  mov     rsi, rax
0x1800642d6  test    rax, rax
0x1800642d9  jz      loc_18006450F
0x1800642df  movsx   r10d, word ptr [rbx+36h]
0x1800642e4  lea     rdx, cs:180000000h
0x1800642eb  xor     ebp, ebp
0x1800642ed  test    r10d, r10d
0x1800642f0  jle     short loc_18006436C
0x1800642f2  mov     r11, [rbx+8]
0x1800642f6  jmp     short loc_180064307
0x180064300  lea     rdx, cs:180000000h
0x180064307  movsxd  rax, ebp
0x18006430a  mov     r9, rsi
0x18006430d  lea     rcx, [rax+rax*2]
0x180064311  mov     r8, [r11+rcx*8]
0x180064315  nop     word ptr [rax+rax+00000000h]
0x180064320  movzx   eax, byte ptr [r8]
0x180064324  movzx   ecx, byte ptr [r9]
0x180064328  cmp     eax, ecx
0x18006432a  jnz     short loc_180064338
0x18006432c  test    eax, eax
0x18006432e  jz      short loc_18006436C
0x180064330  inc     r8
0x180064333  inc     r9
0x180064336  jmp     short loc_180064320
0x180064338  movzx   edx, byte ptr [rcx+rdx+114680h]
0x180064340  mov     rcx, rax
0x180064343  lea     rax, cs:180000000h
0x18006434a  movzx   eax, byte ptr [rcx+rax+114680h]
0x180064352  cmp     eax, edx
0x180064354  jnz     short loc_180064365
0x180064356  inc     r8
0x180064359  lea     rdx, cs:180000000h
0x180064360  inc     r9
0x180064363  jmp     short loc_180064320
0x180064365  inc     ebp
0x180064367  cmp     ebp, r10d
0x18006436a  jl      short loc_180064300
0x18006436c  mov     rcx, r13
0x18006436f  cmp     ebp, r10d
0x180064372  jnz     short loc_180064398
0x180064374  mov     r8, [rsp+0A8h+arg_10]
0x18006437c  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x180064383  call    sqlite3ErrorMsg
0x180064388  mov     rdx, r12
0x18006438b  mov     rcx, rdi
0x18006438e  call    sqlite3SrcListDelete
0x180064393  jmp     loc_18006451F
0x180064398  mov     rbx, [rsp+0A8h+arg_0]
0x1800643a0  lea     rdx, aSelect1FromWSq; "SELECT 1 FROM \"%w\".sqlite_master WHER"...
0x1800643a7  xor     r12d, r12d
0x1800643aa  mov     dword ptr [rsp+0A8h+var_78], r15d
0x1800643af  cmp     r14d, 1
0x1800643b3  mov     byte ptr [r13+1Ch], 1
0x1800643b8  lea     r15, byte_180122168
0x1800643bf  mov     r9, rbx
0x1800643c2  setz    r12b
0x1800643c6  mov     [rsp+0A8h+var_80], r15
0x1800643cb  mov     r8, rbx
0x1800643ce  mov     dword ptr [rsp+0A8h+var_88], r12d
0x1800643d3  call    sqlite3NestedParse
0x1800643d8  cmp     r14d, 1
0x1800643dc  jz      short loc_1800643FB
0x1800643de  mov     r9, r15
0x1800643e1  mov     dword ptr [rsp+0A8h+var_88], 0
0x1800643e9  mov     r8, rbx
0x1800643ec  lea     rdx, aSelect1FromTem; "SELECT 1 FROM temp.sqlite_master WHERE "...
0x1800643f3  mov     rcx, r13
0x1800643f6  call    sqlite3NestedParse
0x1800643fb  mov     r8d, r12d
0x1800643fe  mov     rdx, rbx
0x180064401  mov     rcx, r13
0x180064404  call    renameFixQuotes
0x180064409  mov     rax, [r13+0A8h]
0x180064410  mov     rcx, r13
0x180064413  mov     rbx, [rsp+0A8h+arg_18]
0x18006441b  test    rax, rax
0x18006441e  mov     rdx, rbx
0x180064421  cmovnz  rcx, rax
0x180064425  mov     byte ptr [rcx+21h], 1
0x180064429  mov     rcx, rdi
0x18006442c  call    sqlite3NameFromToken
0x180064431  mov     r15, rax
0x180064434  test    rax, rax
0x180064437  jz      loc_180064507
0x18006443d  mov     rcx, [rbx]
0x180064440  lea     rax, cs:180000000h
0x180064447  mov     r9, [rsp+0A8h+arg_0]
0x18006444f  mov     r8, r9
0x180064452  movzx   edx, byte ptr [rcx]
0x180064455  mov     rcx, [rsp+0A8h+var_58]
0x18006445a  movzx   ebx, byte ptr [rdx+rax+1147A0h]
0x180064462  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180064469  mov     rcx, [rcx]
0x18006446c  and     ebx, 80h
0x180064472  mov     [rsp+0A8h+var_60], rcx
0x180064477  mov     [rsp+0A8h+var_68], r12d
0x18006447c  mov     [rsp+0A8h+var_70], ebx
0x180064480  mov     [rsp+0A8h+var_78], r15
0x180064485  mov     dword ptr [rsp+0A8h+var_80], ebp
0x180064489  mov     [rsp+0A8h+var_88], rcx
0x18006448e  mov     rcx, r13
0x180064491  call    sqlite3NestedParse
0x180064496  mov     rax, [rsp+0A8h+var_58]
0x18006449b  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x1800644a2  mov     r8, [rsp+0A8h+arg_0]
0x1800644aa  mov     rcx, r13
0x1800644ad  mov     dword ptr [rsp+0A8h+var_78], ebx
0x1800644b1  mov     [rsp+0A8h+var_80], r15
0x1800644b6  mov     r9, [rax]
0x1800644b9  mov     dword ptr [rsp+0A8h+var_88], ebp
0x1800644bd  call    sqlite3NestedParse
0x1800644c2  mov     r8d, 1
0x1800644c8  mov     edx, r14d
0x1800644cb  mov     rcx, r13
0x1800644ce  call    renameReloadSchema
0x1800644d3  mov     rdx, [rsp+0A8h+arg_0]
0x1800644db  lea     r9, aAfterRename; "after rename"
0x1800644e2  mov     r8d, r12d
0x1800644e5  mov     dword ptr [rsp+0A8h+var_88], 1
0x1800644ed  mov     rcx, r13
0x1800644f0  call    renameTestSchema
0x1800644f5  mov     rdx, [rsp+0A8h+arg_8]
0x1800644fd  mov     rcx, rdi
0x180064500  call    sqlite3SrcListDelete
0x180064505  jmp     short loc_18006451F
0x180064507  mov     r12, [rsp+0A8h+arg_8]
0x18006450f  mov     rdx, r12
0x180064512  mov     rcx, rdi
0x180064515  call    sqlite3SrcListDelete
0x18006451a  test    rsi, rsi
0x18006451d  jz      short loc_180064584
0x18006451f  test    rdi, rdi
0x180064522  jz      short loc_18006457C
0x180064524  cmp     rsi, [rdi+1F0h]
0x18006452b  jnb     short loc_180064565
0x18006452d  cmp     rsi, [rdi+1E0h]
0x180064534  jb      short loc_180064549
0x180064536  mov     rax, [rdi+1D8h]
0x18006453d  mov     [rsi], rax
0x180064540  mov     [rdi+1D8h], rsi
0x180064547  jmp     short loc_180064584
0x180064549  cmp     rsi, [rdi+1E8h]
0x180064550  jb      short loc_180064565
0x180064552  mov     rax, [rdi+1C8h]
0x180064559  mov     [rsi], rax
0x18006455c  mov     [rdi+1C8h], rsi
0x180064563  jmp     short loc_180064584
0x180064565  cmp     qword ptr [rdi+308h], 0
0x18006456d  jz      short loc_18006457C
0x18006456f  mov     rdx, rsi
0x180064572  mov     rcx, rdi
0x180064575  call    measureAllocationSize
0x18006457a  jmp     short loc_180064584
0x18006457c  mov     rcx, rsi
0x18006457f  call    sqlite3_free
0x180064584  test    r15, r15
0x180064587  jz      short loc_1800645EE
0x180064589  test    rdi, rdi
0x18006458c  jz      short loc_1800645E6
0x18006458e  cmp     r15, [rdi+1F0h]
0x180064595  jnb     short loc_1800645CF
0x180064597  cmp     r15, [rdi+1E0h]
0x18006459e  jb      short loc_1800645B3
0x1800645a0  mov     rax, [rdi+1D8h]
0x1800645a7  mov     [r15], rax
0x1800645aa  mov     [rdi+1D8h], r15
0x1800645b1  jmp     short loc_1800645EE
0x1800645b3  cmp     r15, [rdi+1E8h]
0x1800645ba  jb      short loc_1800645CF
0x1800645bc  mov     rax, [rdi+1C8h]
0x1800645c3  mov     [r15], rax
0x1800645c6  mov     [rdi+1C8h], r15
0x1800645cd  jmp     short loc_1800645EE
0x1800645cf  cmp     qword ptr [rdi+308h], 0
0x1800645d7  jz      short loc_1800645E6
0x1800645d9  mov     rdx, r15
0x1800645dc  mov     rcx, rdi
0x1800645df  call    measureAllocationSize
0x1800645e4  jmp     short loc_1800645EE
0x1800645e6  mov     rcx, r15
0x1800645e9  call    sqlite3_free
0x1800645ee  mov     r14, [rsp+0A8h+var_40]
0x1800645f3  add     rsp, 70h
0x1800645f7  pop     r15
0x1800645f9  pop     r13
0x1800645fb  pop     r12
0x1800645fd  pop     rdi
0x1800645fe  pop     rsi
0x1800645ff  pop     rbp
0x180064600  pop     rbx
0x180064601  retn
```
