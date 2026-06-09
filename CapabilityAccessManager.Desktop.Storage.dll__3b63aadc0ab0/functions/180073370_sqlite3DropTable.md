# sqlite3DropTable

- ea: `0x180073370`
- end: `0x180073666`
- name: `sqlite3DropTable`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1800d8b00`

## callees

- `0x1800658d0`
- `0x1800669c0`
- `0x18006bad0`
- `0x18006bf80`
- `0x18006d4b0`
- `0x180073370`
- `0x1800743d0`
- `0x18007dea0`
- `0x18007e7f0`
- `0x180087d40`
- `0x180093650`
- `0x18009bde0`
- `0x1800a3b40`
- `0x1800c1120`
- `0x1800c8710`

## string_xrefs

- `0x18007349d`: `sqlite_temp_master`
- `0x18007359c`: `use DROP TABLE to delete table %s`
- `0x1800735b9`: `use DROP VIEW to delete view %s`

## pseudocode

```c
__int64 __fastcall sqlite3DropTable(__int64 *a1, _QWORD *a2, unsigned int a3, int a4)
{
  __int64 v4; // rbp
  __int64 v9; // rdx
  int v10; // ecx
  __int64 v11; // r8
  _QWORD *v12; // rdi
  __int64 v13; // r9
  __int64 Table; // rax
  const char **v15; // rsi
  __int64 v16; // rcx
  unsigned int v17; // edi
  __int64 v18; // rdx
  const char *v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r14
  __int64 v22; // r9
  int i; // edx
  const char *v24; // rax

  v4 = *a1;
  if ( !*(_BYTE *)(*a1 + 103) && !(unsigned int)sqlite3ReadSchema(a1) )
  {
    if ( a4 )
      ++*(_BYTE *)(v4 + 107);
    v9 = a2[1];
    if ( v9 )
    {
      v10 = 0;
      v11 = *(_QWORD *)(*a1 + 32);
      if ( *(_QWORD *)(v11 + 24) != v9 )
      {
        do
          ++v10;
        while ( *(_QWORD *)(32LL * v10 + v11 + 24) != v9 );
      }
      v12 = a2 + 2;
      v13 = *(_QWORD *)(32LL * v10 + v11);
    }
    else
    {
      v13 = a2[2];
      v12 = a2 + 2;
    }
    Table = sqlite3LocateTable(a1, a3, a2[3], v13);
    v15 = (const char **)Table;
    if ( a4 )
      --*(_BYTE *)(v4 + 107);
    if ( Table )
    {
      v16 = *(_QWORD *)(Table + 96);
      v17 = -32768;
      if ( v16 )
      {
        v18 = *(_QWORD *)(v4 + 32);
        v17 = 0;
        if ( *(_QWORD *)(v18 + 24) != v16 )
        {
          do
            ++v17;
          while ( *(_QWORD *)(32LL * (int)v17 + v18 + 24) != v16 );
        }
      }
      if ( *(_BYTE *)(Table + 63) != 1 || !(unsigned int)viewGetColumnNames(a1, Table) )
      {
        v19 = "sqlite_temp_master";
        v20 = 32LL * (int)v17;
        v21 = *(_QWORD *)(v20 + *(_QWORD *)(v4 + 32));
        if ( v17 != 1 )
          v19 = "sqlite_master";
        if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v19, 0, *(_QWORD *)(v20 + *(_QWORD *)(v4 + 32))) )
        {
          LODWORD(v22) = 0;
          if ( a3 )
          {
            i = 15;
            if ( v17 != 1 )
              i = 17;
          }
          else if ( *((_BYTE *)v15 + 63) == 1 )
          {
            v24 = v15[10];
            for ( i = 30; v24; v24 = (const char *)*((_QWORD *)v24 + 5) )
            {
              if ( *(_QWORD *)v24 == v4 )
                break;
            }
            v22 = *(_QWORD *)(*((_QWORD *)v24 + 1) + 8LL);
          }
          else
          {
            i = 11;
            if ( v17 == 1 )
              i = 13;
          }
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, i, (unsigned int)*v15, v22, v21)
            && !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (unsigned int)*v15, 0, v21) )
          {
            if ( (unsigned int)tableMayNotBeDropped(v4, v15) )
            {
              sqlite3ErrorMsg(a1, "table %s may not be dropped", *v15);
            }
            else
            {
              if ( a3 )
              {
                if ( *((_BYTE *)v15 + 63) != 2 )
                {
                  sqlite3ErrorMsg(a1, "use DROP TABLE to delete table %s", *v15);
                  return sqlite3SrcListDelete(v4, a2);
                }
              }
              else if ( *((_BYTE *)v15 + 63) == 2 )
              {
                sqlite3ErrorMsg(a1, "use DROP VIEW to delete view %s", *v15);
                return sqlite3SrcListDelete(v4, a2);
              }
              if ( a1[2] )
                goto LABEL_48;
              if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
                *((_BYTE *)a1 + 35) = 1;
              if ( sqlite3VdbeCreate(a1) )
              {
LABEL_48:
                sqlite3BeginWriteOperation(a1, 1, v17);
                if ( !a3 )
                {
                  sqlite3ClearStatTables(a1, v17, "tbl", *v15);
                  sqlite3FkDropTable(a1, a2, v15);
                }
                sqlite3CodeDropTable(a1, v15, v17, a3);
              }
            }
          }
        }
      }
    }
    else if ( a4 )
    {
      sqlite3CodeVerifyNamedSchema(a1, *v12);
      sqlite3ForceNotReadOnly(a1);
    }
  }
  return sqlite3SrcListDelete(v4, a2);
}

```

## disassembly

```asm
0x180073370  mov     [rsp+arg_10], rbx
0x180073375  mov     [rsp+arg_18], rbp
0x18007337a  push    r12
0x18007337c  push    r14
0x18007337e  push    r15
0x180073380  sub     rsp, 30h
0x180073384  mov     rbp, [rcx]
0x180073387  mov     r14d, r9d
0x18007338a  mov     r12d, r8d
0x18007338d  mov     r15, rdx
0x180073390  mov     rbx, rcx
0x180073393  cmp     byte ptr [rbp+67h], 0
0x180073397  jnz     loc_180073647
0x18007339d  call    sqlite3ReadSchema
0x1800733a2  test    eax, eax
0x1800733a4  jnz     loc_180073647
0x1800733aa  mov     [rsp+48h+arg_0], rsi
0x1800733af  test    r14d, r14d
0x1800733b2  jz      short loc_1800733B7
0x1800733b4  inc     byte ptr [rbp+6Bh]
0x1800733b7  mov     rdx, [r15+8]
0x1800733bb  mov     [rsp+48h+arg_8], rdi
0x1800733c0  test    rdx, rdx
0x1800733c3  jz      short loc_180073401
0x1800733c5  mov     rax, [rbx]
0x1800733c8  xor     ecx, ecx
0x1800733ca  mov     r8, [rax+20h]
0x1800733ce  cmp     [r8+18h], rdx
0x1800733d2  jz      short loc_1800733F0
0x1800733d4  nop     dword ptr [rax+00h]
0x1800733d8  nop     dword ptr [rax+rax+00000000h]
0x1800733e0  inc     ecx
0x1800733e2  movsxd  rax, ecx
0x1800733e5  shl     rax, 5
0x1800733e9  cmp     [rax+r8+18h], rdx
0x1800733ee  jnz     short loc_1800733E0
0x1800733f0  movsxd  rax, ecx
0x1800733f3  lea     rdi, [r15+10h]
0x1800733f7  shl     rax, 5
0x1800733fb  mov     r9, [rax+r8]
0x1800733ff  jmp     short loc_180073409
0x180073401  mov     r9, [r15+10h]
0x180073405  lea     rdi, [r15+10h]
0x180073409  mov     r8, [r15+18h]
0x18007340d  mov     edx, r12d
0x180073410  mov     rcx, rbx
0x180073413  call    sqlite3LocateTable
0x180073418  mov     rsi, rax
0x18007341b  test    r14d, r14d
0x18007341e  jz      short loc_180073423
0x180073420  dec     byte ptr [rbp+6Bh]
0x180073423  test    rsi, rsi
0x180073426  jnz     short loc_180073449
0x180073428  test    r14d, r14d
0x18007342b  jz      loc_18007363D
0x180073431  mov     rdx, [rdi]
0x180073434  mov     rcx, rbx
0x180073437  call    sqlite3CodeVerifyNamedSchema
0x18007343c  mov     rcx, rbx
0x18007343f  call    sqlite3ForceNotReadOnly
0x180073444  jmp     loc_18007363D
0x180073449  mov     rcx, [rax+60h]
0x18007344d  mov     edi, 0FFFF8000h
0x180073452  test    rcx, rcx
0x180073455  jz      short loc_180073480
0x180073457  mov     rdx, [rbp+20h]
0x18007345b  xor     edi, edi
0x18007345d  cmp     [rdx+18h], rcx
0x180073461  jz      short loc_180073480
0x180073463  nop     dword ptr [rax+00h]
0x180073467  nop     word ptr [rax+rax+00000000h]
0x180073470  inc     edi
0x180073472  movsxd  rax, edi
0x180073475  shl     rax, 5
0x180073479  cmp     [rax+rdx+18h], rcx
0x18007347e  jnz     short loc_180073470
0x180073480  cmp     byte ptr [rsi+3Fh], 1
0x180073484  jnz     short loc_180073499
0x180073486  mov     rdx, rsi
0x180073489  mov     rcx, rbx
0x18007348c  call    viewGetColumnNames
0x180073491  test    eax, eax
0x180073493  jnz     loc_18007363D
0x180073499  mov     rax, [rbp+20h]
0x18007349d  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x1800734a4  movsxd  rcx, edi
0x1800734a7  mov     edx, 9
0x1800734ac  shl     rcx, 5
0x1800734b0  cmp     edi, 1
0x1800734b3  mov     r14, [rcx+rax]
0x1800734b7  lea     rax, aSqliteMaster; "sqlite_master"
0x1800734be  cmovnz  r8, rax
0x1800734c2  mov     [rsp+48h+var_28], r14
0x1800734c7  xor     r9d, r9d
0x1800734ca  mov     rcx, rbx
0x1800734cd  call    sqlite3AuthCheck
0x1800734d2  test    eax, eax
0x1800734d4  jnz     loc_18007363D
0x1800734da  xor     r9d, r9d
0x1800734dd  test    r12d, r12d
0x1800734e0  jz      short loc_1800734F4
0x1800734e2  cmp     edi, 1
0x1800734e5  mov     edx, 0Fh
0x1800734ea  mov     eax, 11h
0x1800734ef  cmovnz  edx, eax
0x1800734f2  jmp     short loc_180073530
0x1800734f4  cmp     byte ptr [rsi+3Fh], 1
0x1800734f8  jnz     short loc_180073520
0x1800734fa  mov     rax, [rsi+50h]
0x1800734fe  mov     edx, 1Eh
0x180073503  test    rax, rax
0x180073506  jz      short loc_180073516
0x180073508  cmp     [rax], rbp
0x18007350b  jz      short loc_180073516
0x18007350d  mov     rax, [rax+28h]
0x180073511  test    rax, rax
0x180073514  jnz     short loc_180073508
0x180073516  mov     rax, [rax+8]
0x18007351a  mov     r9, [rax+8]
0x18007351e  jmp     short loc_180073530
0x180073520  cmp     edi, 1
0x180073523  mov     edx, 0Bh
0x180073528  mov     eax, 0Dh
0x18007352d  cmovz   edx, eax
0x180073530  mov     r8, [rsi]
0x180073533  mov     rcx, rbx
0x180073536  mov     [rsp+48h+var_28], r14
0x18007353b  call    sqlite3AuthCheck
0x180073540  test    eax, eax
0x180073542  jnz     loc_18007363D
0x180073548  mov     r8, [rsi]
0x18007354b  xor     r9d, r9d
0x18007354e  mov     edx, 9
0x180073553  mov     [rsp+48h+var_28], r14
0x180073558  mov     rcx, rbx
0x18007355b  call    sqlite3AuthCheck
0x180073560  test    eax, eax
0x180073562  jnz     loc_18007363D
0x180073568  mov     rdx, rsi
0x18007356b  mov     rcx, rbp
0x18007356e  call    tableMayNotBeDropped
0x180073573  test    eax, eax
0x180073575  jz      short loc_18007358E
0x180073577  mov     r8, [rsi]
0x18007357a  lea     rdx, aTableSMayNotBe_1; "table %s may not be dropped"
0x180073581  mov     rcx, rbx
0x180073584  call    sqlite3ErrorMsg
0x180073589  jmp     loc_18007363D
0x18007358e  test    r12d, r12d
0x180073591  jz      short loc_1800735B0
0x180073593  cmp     byte ptr [rsi+3Fh], 2
0x180073597  jz      short loc_1800735CA
0x180073599  mov     r8, [rsi]
0x18007359c  lea     rdx, aUseDropTableTo; "use DROP TABLE to delete table %s"
0x1800735a3  mov     rcx, rbx
0x1800735a6  call    sqlite3ErrorMsg
0x1800735ab  jmp     loc_18007363D
0x1800735b0  cmp     byte ptr [rsi+3Fh], 2
0x1800735b4  jnz     short loc_1800735CA
0x1800735b6  mov     r8, [rsi]
0x1800735b9  lea     rdx, aUseDropViewToD; "use DROP VIEW to delete view %s"
0x1800735c0  mov     rcx, rbx
0x1800735c3  call    sqlite3ErrorMsg
0x1800735c8  jmp     short loc_18007363D
0x1800735ca  cmp     qword ptr [rbx+10h], 0
0x1800735cf  jnz     short loc_1800735F5
0x1800735d1  cmp     qword ptr [rbx+0A8h], 0
0x1800735d9  jnz     short loc_1800735E8
0x1800735db  mov     rax, [rbx]
0x1800735de  test    byte ptr [rax+60h], 8
0x1800735e2  jnz     short loc_1800735E8
0x1800735e4  mov     byte ptr [rbx+23h], 1
0x1800735e8  mov     rcx, rbx
0x1800735eb  call    sqlite3VdbeCreate
0x1800735f0  test    rax, rax
0x1800735f3  jz      short loc_18007363D
0x1800735f5  mov     r8d, edi
0x1800735f8  mov     edx, 1
0x1800735fd  mov     rcx, rbx
0x180073600  call    sqlite3BeginWriteOperation
0x180073605  test    r12d, r12d
0x180073608  jnz     short loc_18007362C
0x18007360a  mov     r9, [rsi]
0x18007360d  lea     r8, aTbl; "tbl"
0x180073614  mov     edx, edi
0x180073616  mov     rcx, rbx
0x180073619  call    sqlite3ClearStatTables
0x18007361e  mov     r8, rsi
0x180073621  mov     rdx, r15
0x180073624  mov     rcx, rbx
0x180073627  call    sqlite3FkDropTable
0x18007362c  mov     r9d, r12d
0x18007362f  mov     r8d, edi
0x180073632  mov     rdx, rsi
0x180073635  mov     rcx, rbx
0x180073638  call    sqlite3CodeDropTable
0x18007363d  mov     rdi, [rsp+48h+arg_8]
0x180073642  mov     rsi, [rsp+48h+arg_0]
0x180073647  mov     rdx, r15
0x18007364a  mov     rcx, rbp
0x18007364d  mov     rbx, [rsp+48h+arg_10]
0x180073652  mov     rbp, [rsp+48h+arg_18]
0x180073657  add     rsp, 30h
0x18007365b  pop     r15
0x18007365d  pop     r14
0x18007365f  pop     r12
0x180073661  jmp     sqlite3SrcListDelete
```
