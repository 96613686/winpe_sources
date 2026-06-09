# sqlite3DropTable

- ea: `0x18007e8bc`
- end: `0x18007ead6`
- name: `sqlite3DropTable`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x18001bc30`

## callees

- `0x180014464`
- `0x180027e60`
- `0x1800369e4`
- `0x18003713c`
- `0x18003c5f4`
- `0x18003d480`
- `0x18003f960`
- `0x18004002c`
- `0x180041894`
- `0x180042c38`
- `0x18007b4bc`
- `0x18007b6a8`
- `0x18007c1ec`
- `0x18007e8bc`
- `0x180082408`
- `0x1800829d8`
- `0x18009ac90`

## string_xrefs

- `0x18007e963`: `sqlite_temp_master`
- `0x18007ea50`: `use DROP TABLE to delete table %s`
- `0x18007ea5f`: `use DROP VIEW to delete view %s`

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
      sqlite3CodeVerifyNamedSchema(a1, *(_QWORD *)(a2 + 16));
      sqlite3ForceNotReadOnly(a1);
    }
  }
  return sqlite3SrcListDelete(v4, a2);
}

```

## disassembly

```asm
0x18007e8bc  push    rbx
0x18007e8be  push    rbp
0x18007e8bf  push    rsi
0x18007e8c0  push    rdi
0x18007e8c1  push    r12
0x18007e8c3  push    r14
0x18007e8c5  push    r15
0x18007e8c7  sub     rsp, 30h
0x18007e8cb  mov     rsi, [rcx]
0x18007e8ce  mov     ebp, r9d
0x18007e8d1  mov     r14d, r8d
0x18007e8d4  mov     r15, rdx
0x18007e8d7  mov     rbx, rcx
0x18007e8da  cmp     byte ptr [rsi+67h], 0
0x18007e8de  jnz     loc_18007EABD
0x18007e8e4  call    sqlite3ReadSchema
0x18007e8e9  test    eax, eax
0x18007e8eb  jnz     loc_18007EABD
0x18007e8f1  test    ebp, ebp
0x18007e8f3  jz      short loc_18007E8F8
0x18007e8f5  inc     byte ptr [rsi+6Bh]
0x18007e8f8  lea     r8, [r15+8]
0x18007e8fc  mov     edx, r14d
0x18007e8ff  mov     rcx, rbx
0x18007e902  call    sqlite3LocateTableItem
0x18007e907  mov     rdi, rax
0x18007e90a  test    ebp, ebp
0x18007e90c  jz      short loc_18007E911
0x18007e90e  dec     byte ptr [rsi+6Bh]
0x18007e911  test    rdi, rdi
0x18007e914  jnz     short loc_18007E937
0x18007e916  test    ebp, ebp
0x18007e918  jz      loc_18007EABD
0x18007e91e  mov     rdx, [r15+10h]
0x18007e922  mov     rcx, rbx
0x18007e925  call    sqlite3CodeVerifyNamedSchema
0x18007e92a  mov     rcx, rbx
0x18007e92d  call    sqlite3ForceNotReadOnly
0x18007e932  jmp     loc_18007EABD
0x18007e937  mov     rdx, [rax+60h]
0x18007e93b  mov     rcx, rsi
0x18007e93e  call    sqlite3SchemaToIndex
0x18007e943  cmp     byte ptr [rdi+3Fh], 1
0x18007e947  movsxd  rbp, eax
0x18007e94a  jnz     short loc_18007E95F
0x18007e94c  mov     rdx, rdi
0x18007e94f  mov     rcx, rbx
0x18007e952  call    sqlite3ViewGetColumnNames
0x18007e957  test    eax, eax
0x18007e959  jnz     loc_18007EABD
0x18007e95f  mov     rax, [rsi+20h]
0x18007e963  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18007e96a  mov     rcx, rbp
0x18007e96d  shl     rcx, 5
0x18007e971  cmp     ebp, 1
0x18007e974  mov     r12, [rcx+rax]
0x18007e978  lea     rax, aSqliteMaster; "sqlite_master"
0x18007e97f  cmovnz  r8, rax
0x18007e983  mov     [rsp+68h+var_48], r12
0x18007e988  xor     r9d, r9d
0x18007e98b  mov     rcx, rbx
0x18007e98e  lea     edx, [r9+9]
0x18007e992  call    sqlite3AuthCheck
0x18007e997  test    eax, eax
0x18007e999  jnz     loc_18007EABD
0x18007e99f  xor     r9d, r9d
0x18007e9a2  test    r14d, r14d
0x18007e9a5  jz      short loc_18007E9B8
0x18007e9a7  cmp     ebp, 1
0x18007e9aa  lea     eax, [r9+11h]
0x18007e9ae  lea     r10d, [r9+0Fh]
0x18007e9b2  cmovnz  r10d, eax
0x18007e9b6  jmp     short loc_18007E9E9
0x18007e9b8  cmp     byte ptr [rdi+3Fh], 1
0x18007e9bc  jnz     short loc_18007E9D9
0x18007e9be  mov     rdx, rdi
0x18007e9c1  mov     rcx, rsi
0x18007e9c4  mov     r10d, 1Eh
0x18007e9ca  call    sqlite3GetVTable
0x18007e9cf  mov     rcx, [rax+8]
0x18007e9d3  mov     r9, [rcx+8]
0x18007e9d7  jmp     short loc_18007E9E9
0x18007e9d9  mov     eax, 0Dh
0x18007e9de  cmp     ebp, 1
0x18007e9e1  lea     r10d, [rax-2]
0x18007e9e5  cmovz   r10d, eax
0x18007e9e9  mov     r8, [rdi]
0x18007e9ec  mov     edx, r10d
0x18007e9ef  mov     rcx, rbx
0x18007e9f2  mov     [rsp+68h+var_48], r12
0x18007e9f7  call    sqlite3AuthCheck
0x18007e9fc  test    eax, eax
0x18007e9fe  jnz     loc_18007EABD
0x18007ea04  mov     r8, [rdi]
0x18007ea07  lea     edx, [rax+9]
0x18007ea0a  xor     r9d, r9d
0x18007ea0d  mov     [rsp+68h+var_48], r12
0x18007ea12  mov     rcx, rbx
0x18007ea15  call    sqlite3AuthCheck
0x18007ea1a  test    eax, eax
0x18007ea1c  jnz     loc_18007EABD
0x18007ea22  mov     rdx, rdi
0x18007ea25  mov     rcx, rsi
0x18007ea28  call    tableMayNotBeDropped
0x18007ea2d  test    eax, eax
0x18007ea2f  jz      short loc_18007EA45
0x18007ea31  lea     rdx, aTableSMayNotBe_1; "table %s may not be dropped"
0x18007ea38  mov     r8, [rdi]
0x18007ea3b  mov     rcx, rbx
0x18007ea3e  call    sqlite3ErrorMsg
0x18007ea43  jmp     short loc_18007EABD
0x18007ea45  test    r14d, r14d
0x18007ea48  jz      short loc_18007EA59
0x18007ea4a  cmp     byte ptr [rdi+3Fh], 2
0x18007ea4e  jz      short loc_18007EA68
0x18007ea50  lea     rdx, aUseDropTableTo; "use DROP TABLE to delete table %s"
0x18007ea57  jmp     short loc_18007EA38
0x18007ea59  cmp     byte ptr [rdi+3Fh], 2
0x18007ea5d  jnz     short loc_18007EA68
0x18007ea5f  lea     rdx, aUseDropViewToD; "use DROP VIEW to delete view %s"
0x18007ea66  jmp     short loc_18007EA38
0x18007ea68  mov     rcx, rbx
0x18007ea6b  call    sqlite3GetVdbe
0x18007ea70  test    rax, rax
0x18007ea73  jz      short loc_18007EABD
0x18007ea75  mov     r8d, ebp
0x18007ea78  mov     edx, 1
0x18007ea7d  mov     rcx, rbx
0x18007ea80  call    sqlite3BeginWriteOperation
0x18007ea85  test    r14d, r14d
0x18007ea88  jnz     short loc_18007EAAC
0x18007ea8a  mov     r9, [rdi]
0x18007ea8d  lea     r8, aTbl; "tbl"
0x18007ea94  mov     edx, ebp
0x18007ea96  mov     rcx, rbx
0x18007ea99  call    sqlite3ClearStatTables
0x18007ea9e  mov     r8, rdi
0x18007eaa1  mov     rdx, r15
0x18007eaa4  mov     rcx, rbx
0x18007eaa7  call    sqlite3FkDropTable
0x18007eaac  mov     r9d, r14d
0x18007eaaf  mov     r8d, ebp
0x18007eab2  mov     rdx, rdi
0x18007eab5  mov     rcx, rbx
0x18007eab8  call    sqlite3CodeDropTable
0x18007eabd  mov     rdx, r15
0x18007eac0  mov     rcx, rsi
0x18007eac3  add     rsp, 30h
0x18007eac7  pop     r15
0x18007eac9  pop     r14
0x18007eacb  pop     r12
0x18007eacd  pop     rdi
0x18007eace  pop     rsi
0x18007eacf  pop     rbp
0x18007ead0  pop     rbx
0x18007ead1  jmp     sqlite3SrcListDelete
```
