# sqlite3DropTable

- ea: `0x1800832c0`
- end: `0x1800834da`
- name: `sqlite3DropTable`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x180031b38`

## callees

- `0x18000ca30`
- `0x180010810`
- `0x1800139a4`
- `0x180013bc0`
- `0x1800157d4`
- `0x180018600`
- `0x1800398f0`
- `0x18003f6dc`
- `0x180060ce8`
- `0x180060e90`
- `0x1800825e0`
- `0x180082718`
- `0x180082938`
- `0x1800832c0`
- `0x180083f28`
- `0x1800842a4`
- `0x180092294`

## string_xrefs

- `0x180083367`: `sqlite_temp_master`
- `0x180083454`: `use DROP TABLE to delete table %s`
- `0x180083463`: `use DROP VIEW to delete view %s`

## pseudocode

```c
__int64 __fastcall sqlite3DropTable(__int64 *a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v4; // rsi
  __int64 TableItem; // rax
  _QWORD *v10; // rdi
  __int64 v11; // rbp
  const char *v12; // r8
  __int64 v13; // r12
  __int64 v14; // r9
  int v15; // r10d

  v4 = *a1;
  if ( !*(_BYTE *)(*a1 + 103) && !(unsigned int)sqlite3ReadSchema(a1) )
  {
    if ( a4 )
      ++*(_BYTE *)(v4 + 107);
    TableItem = sqlite3LocateTableItem(a1, a3, a2 + 8);
    v10 = (_QWORD *)TableItem;
    if ( a4 )
      --*(_BYTE *)(v4 + 107);
    if ( TableItem )
    {
      v11 = (int)sqlite3SchemaToIndex(v4, *(_QWORD *)(TableItem + 96));
      if ( *((_BYTE *)v10 + 63) != 1 || !(unsigned int)sqlite3ViewGetColumnNames(a1, v10) )
      {
        v12 = "sqlite_temp_master";
        v13 = *(_QWORD *)(32 * v11 + *(_QWORD *)(v4 + 32));
        if ( (_DWORD)v11 != 1 )
          v12 = "sqlite_master";
        if ( !(unsigned int)sqlite3AuthCheck(
                              (_DWORD)a1,
                              9,
                              (_DWORD)v12,
                              0,
                              *(_QWORD *)(32 * v11 + *(_QWORD *)(v4 + 32))) )
        {
          LODWORD(v14) = 0;
          if ( a3 )
          {
            v15 = 15;
            if ( (_DWORD)v11 != 1 )
              v15 = 17;
          }
          else if ( *((_BYTE *)v10 + 63) == 1 )
          {
            v14 = *(_QWORD *)(*(_QWORD *)(sqlite3GetVTable(v4, v10) + 8) + 8LL);
          }
          else
          {
            v15 = 11;
            if ( (_DWORD)v11 == 1 )
              v15 = 13;
          }
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v15, *v10, v14, v13)
            && !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, *v10, 0, v13) )
          {
            if ( (unsigned int)tableMayNotBeDropped(v4, v10) )
            {
              sqlite3ErrorMsg(a1, "table %s may not be dropped", *v10);
              return sqlite3SrcListDelete(v4, a2);
            }
            if ( a3 )
            {
              if ( *((_BYTE *)v10 + 63) != 2 )
              {
                sqlite3ErrorMsg(a1, "use DROP TABLE to delete table %s", *v10);
                return sqlite3SrcListDelete(v4, a2);
              }
            }
            else if ( *((_BYTE *)v10 + 63) == 2 )
            {
              sqlite3ErrorMsg(a1, "use DROP VIEW to delete view %s", *v10);
              return sqlite3SrcListDelete(v4, a2);
            }
            if ( sqlite3GetVdbe(a1) )
            {
              sqlite3BeginWriteOperation(a1, 1, (unsigned int)v11);
              if ( !a3 )
              {
                sqlite3ClearStatTables(a1, (unsigned int)v11, "tbl", *v10);
                sqlite3FkDropTable(a1, a2, v10);
              }
              sqlite3CodeDropTable(a1, v10, (unsigned int)v11, a3);
            }
          }
        }
      }
    }
    else if ( a4 )
    {
      sqlite3CodeVerifyNamedSchema(a1, *(_QWORD *)(a2 + 80));
      sqlite3ForceNotReadOnly(a1);
    }
  }
  return sqlite3SrcListDelete(v4, a2);
}

```

## disassembly

```asm
0x1800832c0  push    rbx
0x1800832c2  push    rbp
0x1800832c3  push    rsi
0x1800832c4  push    rdi
0x1800832c5  push    r12
0x1800832c7  push    r14
0x1800832c9  push    r15
0x1800832cb  sub     rsp, 30h
0x1800832cf  mov     rsi, [rcx]
0x1800832d2  mov     ebp, r9d
0x1800832d5  mov     r14d, r8d
0x1800832d8  mov     r15, rdx
0x1800832db  mov     rbx, rcx
0x1800832de  cmp     byte ptr [rsi+67h], 0
0x1800832e2  jnz     loc_1800834C1
0x1800832e8  call    sqlite3ReadSchema
0x1800832ed  test    eax, eax
0x1800832ef  jnz     loc_1800834C1
0x1800832f5  test    ebp, ebp
0x1800832f7  jz      short loc_1800832FC
0x1800832f9  inc     byte ptr [rsi+6Bh]
0x1800832fc  lea     r8, [r15+8]
0x180083300  mov     edx, r14d
0x180083303  mov     rcx, rbx
0x180083306  call    sqlite3LocateTableItem
0x18008330b  mov     rdi, rax
0x18008330e  test    ebp, ebp
0x180083310  jz      short loc_180083315
0x180083312  dec     byte ptr [rsi+6Bh]
0x180083315  test    rdi, rdi
0x180083318  jnz     short loc_18008333B
0x18008331a  test    ebp, ebp
0x18008331c  jz      loc_1800834C1
0x180083322  mov     rdx, [r15+50h]
0x180083326  mov     rcx, rbx
0x180083329  call    sqlite3CodeVerifyNamedSchema
0x18008332e  mov     rcx, rbx
0x180083331  call    sqlite3ForceNotReadOnly
0x180083336  jmp     loc_1800834C1
0x18008333b  mov     rdx, [rax+60h]
0x18008333f  mov     rcx, rsi
0x180083342  call    sqlite3SchemaToIndex
0x180083347  cmp     byte ptr [rdi+3Fh], 1
0x18008334b  movsxd  rbp, eax
0x18008334e  jnz     short loc_180083363
0x180083350  mov     rdx, rdi
0x180083353  mov     rcx, rbx
0x180083356  call    sqlite3ViewGetColumnNames
0x18008335b  test    eax, eax
0x18008335d  jnz     loc_1800834C1
0x180083363  mov     rax, [rsi+20h]
0x180083367  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18008336e  mov     rcx, rbp
0x180083371  shl     rcx, 5
0x180083375  cmp     ebp, 1
0x180083378  mov     r12, [rcx+rax]
0x18008337c  lea     rax, aSqliteMaster; "sqlite_master"
0x180083383  cmovnz  r8, rax
0x180083387  mov     [rsp+68h+var_48], r12
0x18008338c  xor     r9d, r9d
0x18008338f  mov     rcx, rbx
0x180083392  lea     edx, [r9+9]
0x180083396  call    sqlite3AuthCheck
0x18008339b  test    eax, eax
0x18008339d  jnz     loc_1800834C1
0x1800833a3  xor     r9d, r9d
0x1800833a6  test    r14d, r14d
0x1800833a9  jz      short loc_1800833BC
0x1800833ab  cmp     ebp, 1
0x1800833ae  lea     eax, [r9+11h]
0x1800833b2  lea     r10d, [r9+0Fh]
0x1800833b6  cmovnz  r10d, eax
0x1800833ba  jmp     short loc_1800833ED
0x1800833bc  cmp     byte ptr [rdi+3Fh], 1
0x1800833c0  jnz     short loc_1800833DD
0x1800833c2  mov     rdx, rdi
0x1800833c5  mov     rcx, rsi
0x1800833c8  mov     r10d, 1Eh
0x1800833ce  call    sqlite3GetVTable
0x1800833d3  mov     rcx, [rax+8]
0x1800833d7  mov     r9, [rcx+8]
0x1800833db  jmp     short loc_1800833ED
0x1800833dd  mov     eax, 0Dh
0x1800833e2  cmp     ebp, 1
0x1800833e5  lea     r10d, [rax-2]
0x1800833e9  cmovz   r10d, eax
0x1800833ed  mov     r8, [rdi]
0x1800833f0  mov     edx, r10d
0x1800833f3  mov     rcx, rbx
0x1800833f6  mov     [rsp+68h+var_48], r12
0x1800833fb  call    sqlite3AuthCheck
0x180083400  test    eax, eax
0x180083402  jnz     loc_1800834C1
0x180083408  mov     r8, [rdi]
0x18008340b  lea     edx, [rax+9]
0x18008340e  xor     r9d, r9d
0x180083411  mov     [rsp+68h+var_48], r12
0x180083416  mov     rcx, rbx
0x180083419  call    sqlite3AuthCheck
0x18008341e  test    eax, eax
0x180083420  jnz     loc_1800834C1
0x180083426  mov     rdx, rdi
0x180083429  mov     rcx, rsi
0x18008342c  call    tableMayNotBeDropped
0x180083431  test    eax, eax
0x180083433  jz      short loc_180083449
0x180083435  lea     rdx, aTableSMayNotBe_1; "table %s may not be dropped"
0x18008343c  mov     r8, [rdi]
0x18008343f  mov     rcx, rbx
0x180083442  call    sqlite3ErrorMsg
0x180083447  jmp     short loc_1800834C1
0x180083449  test    r14d, r14d
0x18008344c  jz      short loc_18008345D
0x18008344e  cmp     byte ptr [rdi+3Fh], 2
0x180083452  jz      short loc_18008346C
0x180083454  lea     rdx, aUseDropTableTo; "use DROP TABLE to delete table %s"
0x18008345b  jmp     short loc_18008343C
0x18008345d  cmp     byte ptr [rdi+3Fh], 2
0x180083461  jnz     short loc_18008346C
0x180083463  lea     rdx, aUseDropViewToD; "use DROP VIEW to delete view %s"
0x18008346a  jmp     short loc_18008343C
0x18008346c  mov     rcx, rbx
0x18008346f  call    sqlite3GetVdbe
0x180083474  test    rax, rax
0x180083477  jz      short loc_1800834C1
0x180083479  mov     r8d, ebp
0x18008347c  mov     edx, 1
0x180083481  mov     rcx, rbx
0x180083484  call    sqlite3BeginWriteOperation
0x180083489  test    r14d, r14d
0x18008348c  jnz     short loc_1800834B0
0x18008348e  mov     r9, [rdi]
0x180083491  lea     r8, aTbl; "tbl"
0x180083498  mov     edx, ebp
0x18008349a  mov     rcx, rbx
0x18008349d  call    sqlite3ClearStatTables
0x1800834a2  mov     r8, rdi
0x1800834a5  mov     rdx, r15
0x1800834a8  mov     rcx, rbx
0x1800834ab  call    sqlite3FkDropTable
0x1800834b0  mov     r9d, r14d
0x1800834b3  mov     r8d, ebp
0x1800834b6  mov     rdx, rdi
0x1800834b9  mov     rcx, rbx
0x1800834bc  call    sqlite3CodeDropTable
0x1800834c1  mov     rdx, r15
0x1800834c4  mov     rcx, rsi
0x1800834c7  add     rsp, 30h
0x1800834cb  pop     r15
0x1800834cd  pop     r14
0x1800834cf  pop     r12
0x1800834d1  pop     rdi
0x1800834d2  pop     rsi
0x1800834d3  pop     rbp
0x1800834d4  pop     rbx
0x1800834d5  jmp     sqlite3SrcListDelete
```
