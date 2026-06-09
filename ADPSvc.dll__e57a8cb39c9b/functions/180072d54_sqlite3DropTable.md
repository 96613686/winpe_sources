# sqlite3DropTable

- ea: `0x180072d54`
- end: `0x180072feb`
- name: `sqlite3DropTable`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1800c3bd8`

## callees

- `0x1800693b0`
- `0x180069d64`
- `0x18006dde4`
- `0x18006e0a0`
- `0x18006ecc8`
- `0x180072d54`
- `0x180073aec`
- `0x180079dfc`
- `0x18007a3e4`
- `0x18007d478`
- `0x180080774`
- `0x1800892a0`
- `0x1800892e4`
- `0x18008e124`
- `0x1800ada30`
- `0x1800b6a40`

## string_xrefs

- `0x180072e18`: `sqlite_temp_master`
- `0x180072f72`: `use DROP VIEW to delete view %s`
- `0x180072f31`: `use DROP TABLE to delete table %s`

## pseudocode

```c
__int64 __fastcall sqlite3DropTable(__int64 *a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v4; // rsi
  __int64 TableItem; // rax
  _QWORD *v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // ebp
  __int64 v13; // rdx
  const char *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // r9
  int v18; // edx
  _QWORD *v19; // rax
  __int64 v20; // r14

  v4 = *a1;
  if ( *(_BYTE *)(*a1 + 103) || (unsigned int)sqlite3ReadSchema(a1) )
    return sqlite3SrcListDelete(v4, a2);
  if ( a4 )
    ++*(_BYTE *)(v4 + 107);
  TableItem = sqlite3LocateTableItem(a1, a3, a2 + 8);
  v10 = (_QWORD *)TableItem;
  if ( a4 )
    --*(_BYTE *)(v4 + 107);
  if ( !TableItem )
  {
    if ( a4 )
    {
      sqlite3CodeVerifyNamedSchema(a1, *(_QWORD *)(a2 + 16));
      sqlite3ForceNotReadOnly(a1);
    }
    return sqlite3SrcListDelete(v4, a2);
  }
  v11 = *(_QWORD *)(TableItem + 96);
  v12 = -32768;
  if ( v11 )
  {
    v13 = *(_QWORD *)(v4 + 32);
    v12 = 0;
    if ( *(_QWORD *)(v13 + 24) != v11 )
    {
      do
        ++v12;
      while ( *(_QWORD *)(32LL * (int)v12 + v13 + 24) != v11 );
    }
  }
  if ( *(_BYTE *)(TableItem + 63) != 1 || !(unsigned int)viewGetColumnNames(a1, TableItem) )
  {
    v14 = "sqlite_temp_master";
    v15 = 32LL * (int)v12;
    v16 = *(_QWORD *)(v15 + *(_QWORD *)(v4 + 32));
    if ( v12 != 1 )
      v14 = "sqlite_master";
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v14, 0, *(_QWORD *)(v15 + *(_QWORD *)(v4 + 32))) )
    {
      LODWORD(v17) = 0;
      if ( a3 )
      {
        v18 = 15;
        if ( v12 != 1 )
          v18 = 17;
      }
      else if ( *((_BYTE *)v10 + 63) == 1 )
      {
        v19 = (_QWORD *)v10[10];
        v18 = 30;
        while ( v19 && *v19 != v4 )
          v19 = (_QWORD *)v19[5];
        v17 = *(_QWORD *)(v19[1] + 8LL);
      }
      else
      {
        v18 = 11;
        if ( v12 == 1 )
          v18 = 13;
      }
      if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v18, *v10, v17, v16)
        && !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, *v10, 0, v16) )
      {
        v20 = *v10;
        if ( (unsigned int)sqlite3_strnicmp(*v10, "sqlite_", 7) )
        {
          if ( ((v10[6] & 0x1000) == 0 || !(unsigned int)sqlite3ReadOnlyShadowTables(v4)) && (v10[6] & 0x8000) == 0 )
            goto LABEL_35;
        }
        else if ( !(unsigned int)sqlite3_strnicmp(v20 + 7, "stat", 4)
               || !(unsigned int)sqlite3_strnicmp(v20 + 7, "parameters", 10) )
        {
LABEL_35:
          if ( a3 )
          {
            if ( *((_BYTE *)v10 + 63) != 2 )
            {
              sqlite3ErrorMsg(a1, "use DROP TABLE to delete table %s", v20);
              return sqlite3SrcListDelete(v4, a2);
            }
          }
          else if ( *((_BYTE *)v10 + 63) == 2 )
          {
            sqlite3ErrorMsg(a1, "use DROP VIEW to delete view %s", v20);
            return sqlite3SrcListDelete(v4, a2);
          }
          if ( sqlite3GetVdbe(a1) )
          {
            sqlite3BeginWriteOperation(a1, 1, v12);
            if ( !a3 )
            {
              sqlite3ClearStatTables(a1, v12, "tbl", *v10);
              sqlite3FkDropTable(a1, a2, v10);
            }
            sqlite3CodeDropTable(a1, v10, v12, a3);
          }
          return sqlite3SrcListDelete(v4, a2);
        }
        sqlite3ErrorMsg(a1, "table %s may not be dropped", v20);
      }
    }
  }
  return sqlite3SrcListDelete(v4, a2);
}

```

## disassembly

```asm
0x180072d54  push    rbx
0x180072d56  push    rbp
0x180072d57  push    rsi
0x180072d58  push    rdi
0x180072d59  push    r12
0x180072d5b  push    r13
0x180072d5d  push    r14
0x180072d5f  push    r15
0x180072d61  sub     rsp, 38h
0x180072d65  mov     rsi, [rcx]
0x180072d68  mov     ebp, r9d
0x180072d6b  mov     r15d, r8d
0x180072d6e  mov     r13, rdx
0x180072d71  mov     rbx, rcx
0x180072d74  cmp     byte ptr [rsi+67h], 0
0x180072d78  jnz     loc_180072FD0
0x180072d7e  call    sqlite3ReadSchema
0x180072d83  test    eax, eax
0x180072d85  jnz     loc_180072FD0
0x180072d8b  test    ebp, ebp
0x180072d8d  jz      short loc_180072D92
0x180072d8f  inc     byte ptr [rsi+6Bh]
0x180072d92  lea     r8, [r13+8]
0x180072d96  mov     edx, r15d
0x180072d99  mov     rcx, rbx
0x180072d9c  call    sqlite3LocateTableItem
0x180072da1  mov     rdi, rax
0x180072da4  test    ebp, ebp
0x180072da6  jz      short loc_180072DAB
0x180072da8  dec     byte ptr [rsi+6Bh]
0x180072dab  test    rdi, rdi
0x180072dae  jnz     short loc_180072DD1
0x180072db0  test    ebp, ebp
0x180072db2  jz      loc_180072FD0
0x180072db8  mov     rdx, [r13+10h]
0x180072dbc  mov     rcx, rbx
0x180072dbf  call    sqlite3CodeVerifyNamedSchema
0x180072dc4  mov     rcx, rbx
0x180072dc7  call    sqlite3ForceNotReadOnly
0x180072dcc  jmp     loc_180072FD0
0x180072dd1  mov     rcx, [rax+60h]
0x180072dd5  mov     ebp, 0FFFF8000h
0x180072dda  test    rcx, rcx
0x180072ddd  jz      short loc_180072DFB
0x180072ddf  mov     rdx, [rsi+20h]
0x180072de3  xor     ebp, ebp
0x180072de5  cmp     [rdx+18h], rcx
0x180072de9  jz      short loc_180072DFB
0x180072deb  inc     ebp
0x180072ded  movsxd  rax, ebp
0x180072df0  shl     rax, 5
0x180072df4  cmp     [rax+rdx+18h], rcx
0x180072df9  jnz     short loc_180072DEB
0x180072dfb  cmp     byte ptr [rdi+3Fh], 1
0x180072dff  jnz     short loc_180072E14
0x180072e01  mov     rdx, rdi
0x180072e04  mov     rcx, rbx
0x180072e07  call    viewGetColumnNames
0x180072e0c  test    eax, eax
0x180072e0e  jnz     loc_180072FD0
0x180072e14  mov     rax, [rsi+20h]
0x180072e18  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180072e1f  movsxd  rcx, ebp
0x180072e22  shl     rcx, 5
0x180072e26  cmp     ebp, 1
0x180072e29  mov     r14, [rcx+rax]
0x180072e2d  lea     rax, aSqliteMaster; "sqlite_master"
0x180072e34  cmovnz  r8, rax
0x180072e38  mov     [rsp+78h+var_58], r14
0x180072e3d  xor     r9d, r9d
0x180072e40  mov     rcx, rbx
0x180072e43  lea     r12d, [r9+9]
0x180072e47  mov     edx, r12d
0x180072e4a  call    sqlite3AuthCheck
0x180072e4f  test    eax, eax
0x180072e51  jnz     loc_180072FD0
0x180072e57  xor     r9d, r9d
0x180072e5a  test    r15d, r15d
0x180072e5d  jz      short loc_180072E6D
0x180072e5f  lea     edx, [rax+0Fh]
0x180072e62  cmp     ebp, 1
0x180072e65  lea     eax, [rdx+2]
0x180072e68  cmovnz  edx, eax
0x180072e6b  jmp     short loc_180072EA4
0x180072e6d  cmp     byte ptr [rdi+3Fh], 1
0x180072e71  jnz     short loc_180072E96
0x180072e73  mov     rax, [rdi+50h]
0x180072e77  mov     edx, 1Eh
0x180072e7c  jmp     short loc_180072E87
0x180072e7e  cmp     [rax], rsi
0x180072e81  jz      short loc_180072E8C
0x180072e83  mov     rax, [rax+28h]
0x180072e87  test    rax, rax
0x180072e8a  jnz     short loc_180072E7E
0x180072e8c  mov     rax, [rax+8]
0x180072e90  mov     r9, [rax+8]
0x180072e94  jmp     short loc_180072EA4
0x180072e96  mov     edx, 0Bh
0x180072e9b  cmp     ebp, 1
0x180072e9e  lea     eax, [rdx+2]
0x180072ea1  cmovz   edx, eax
0x180072ea4  mov     r8, [rdi]
0x180072ea7  mov     rcx, rbx
0x180072eaa  mov     [rsp+78h+var_58], r14
0x180072eaf  call    sqlite3AuthCheck
0x180072eb4  test    eax, eax
0x180072eb6  jnz     loc_180072FD0
0x180072ebc  mov     r8, [rdi]
0x180072ebf  xor     r9d, r9d
0x180072ec2  mov     edx, r12d
0x180072ec5  mov     [rsp+78h+var_58], r14
0x180072eca  mov     rcx, rbx
0x180072ecd  call    sqlite3AuthCheck
0x180072ed2  test    eax, eax
0x180072ed4  jnz     loc_180072FD0
0x180072eda  mov     r14, [rdi]
0x180072edd  lea     r8d, [rax+7]
0x180072ee1  mov     rcx, r14
0x180072ee4  lea     rdx, aSqlite_0; "sqlite_"
0x180072eeb  call    sqlite3_strnicmp
0x180072ef0  test    eax, eax
0x180072ef2  jnz     short loc_180072F3A
0x180072ef4  lea     r8d, [rax+4]
0x180072ef8  lea     rdx, aStat; "stat"
0x180072eff  lea     rcx, [r14+7]
0x180072f03  call    sqlite3_strnicmp
0x180072f08  test    eax, eax
0x180072f0a  jz      short loc_180072F26
0x180072f0c  mov     r8d, 0Ah
0x180072f12  lea     rdx, aParameters; "parameters"
0x180072f19  lea     rcx, [r14+7]
0x180072f1d  call    sqlite3_strnicmp
0x180072f22  test    eax, eax
0x180072f24  jnz     short loc_180072F58
0x180072f26  test    r15d, r15d
0x180072f29  jz      short loc_180072F6C
0x180072f2b  cmp     byte ptr [rdi+3Fh], 2
0x180072f2f  jz      short loc_180072F7B
0x180072f31  lea     rdx, aUseDropTableTo; "use DROP TABLE to delete table %s"
0x180072f38  jmp     short loc_180072F5F
0x180072f3a  test    dword ptr [rdi+30h], 1000h
0x180072f41  jz      short loc_180072F4F
0x180072f43  mov     rcx, rsi
0x180072f46  call    sqlite3ReadOnlyShadowTables
0x180072f4b  test    eax, eax
0x180072f4d  jnz     short loc_180072F58
0x180072f4f  test    dword ptr [rdi+30h], 8000h
0x180072f56  jz      short loc_180072F26
0x180072f58  lea     rdx, aTableSMayNotBe_1; "table %s may not be dropped"
0x180072f5f  mov     r8, r14
0x180072f62  mov     rcx, rbx
0x180072f65  call    sqlite3ErrorMsg
0x180072f6a  jmp     short loc_180072FD0
0x180072f6c  cmp     byte ptr [rdi+3Fh], 2
0x180072f70  jnz     short loc_180072F7B
0x180072f72  lea     rdx, aUseDropViewToD; "use DROP VIEW to delete view %s"
0x180072f79  jmp     short loc_180072F5F
0x180072f7b  mov     rcx, rbx
0x180072f7e  call    sqlite3GetVdbe
0x180072f83  test    rax, rax
0x180072f86  jz      short loc_180072FD0
0x180072f88  mov     r8d, ebp
0x180072f8b  mov     edx, 1
0x180072f90  mov     rcx, rbx
0x180072f93  call    sqlite3BeginWriteOperation
0x180072f98  test    r15d, r15d
0x180072f9b  jnz     short loc_180072FBF
0x180072f9d  mov     r9, [rdi]
0x180072fa0  lea     r8, aTbl; "tbl"
0x180072fa7  mov     edx, ebp
0x180072fa9  mov     rcx, rbx
0x180072fac  call    sqlite3ClearStatTables
0x180072fb1  mov     r8, rdi
0x180072fb4  mov     rdx, r13
0x180072fb7  mov     rcx, rbx
0x180072fba  call    sqlite3FkDropTable
0x180072fbf  mov     r9d, r15d
0x180072fc2  mov     r8d, ebp
0x180072fc5  mov     rdx, rdi
0x180072fc8  mov     rcx, rbx
0x180072fcb  call    sqlite3CodeDropTable
0x180072fd0  mov     rdx, r13
0x180072fd3  mov     rcx, rsi
0x180072fd6  add     rsp, 38h
0x180072fda  pop     r15
0x180072fdc  pop     r14
0x180072fde  pop     r13
0x180072fe0  pop     r12
0x180072fe2  pop     rdi
0x180072fe3  pop     rsi
0x180072fe4  pop     rbp
0x180072fe5  pop     rbx
0x180072fe6  jmp     sqlite3SrcListDelete
```
