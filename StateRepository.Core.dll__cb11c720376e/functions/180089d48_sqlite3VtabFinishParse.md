# sqlite3VtabFinishParse

- ea: `0x180089d48`
- end: `0x180089f39`
- name: `sqlite3VtabFinishParse`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180031b38`

## callees

- `0x18000a9e0`
- `0x18000c500`
- `0x180010810`
- `0x1800119e0`
- `0x180011d80`
- `0x1800256c4`
- `0x18003f6dc`
- `0x180064ef0`
- `0x180069638`
- `0x180084f4c`
- `0x1800857c4`
- `0x180088234`
- `0x180089d48`

## string_xrefs

- `0x180089dc9`: `CREATE VIRTUAL TABLE %T`
- `0x180089dee`: `UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d`

## pseudocode

```c
void __fastcall sqlite3VtabFinishParse(__int64 *a1, _DWORD *a2)
{
  __int64 *v2; // r15
  __int64 v5; // r13
  _DWORD *v6; // r8
  __int64 *v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rbp
  __int64 Vdbe; // rdi
  __int64 v11; // rax
  int v12; // ebx
  __int64 v13; // rbx
  __int64 v14; // rdi

  v2 = (__int64 *)a1[44];
  if ( v2 )
  {
    v5 = *a1;
    addArgumentToVtab(a1);
    a1[48] = 0;
    if ( *((int *)v2 + 16) >= 1 )
    {
      if ( *(_BYTE *)(v5 + 197) )
      {
        v13 = v2[12];
        v14 = *v2;
        sqlite3MarkAllShadowTablesOf(v5, v2);
        if ( sqlite3HashInsert(v13 + 8, v14, v2) )
          sqlite3OomFault(v5);
        else
          a1[44] = 0;
      }
      else
      {
        v6 = a1 + 34;
        v7 = a1;
        if ( a1[22] )
          v7 = (__int64 *)a1[22];
        *((_BYTE *)v7 + 33) = 1;
        if ( a2 )
          *((_DWORD *)a1 + 70) = *a2 + a2[2] - *v6;
        v8 = sqlite3MPrintf(v5, "CREATE VIRTUAL TABLE %T", v6);
        v9 = (int)sqlite3SchemaToIndex(v5, v2[12]);
        sqlite3NestedParse(
          a1,
          "UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d",
          *(_QWORD *)(*(_QWORD *)(v5 + 32) + 32 * v9));
        Vdbe = sqlite3GetVdbe(a1);
        sqlite3VdbeAddOp3(a1[2], 100, v9, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32) + 32 * v9 + 24) + 1);
        sqlite3VdbeAddOp3(Vdbe, 166, 0, 0, 0);
        v11 = sqlite3MPrintf(v5, "name=%Q AND sql=%Q", *v2, v8);
        sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v9, v11, 0);
        sqlite3DbFree(v5, v8);
        v12 = ++*((_DWORD *)a1 + 15);
        sqlite3VdbeAddOp4(Vdbe, 118, 0, v12, 0, *v2, 0);
        sqlite3VdbeAddOp3(Vdbe, 171, v9, v12, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180089d48  push    rbx
0x180089d4a  push    rbp
0x180089d4b  push    rsi
0x180089d4c  push    rdi
0x180089d4d  push    r13
0x180089d4f  push    r14
0x180089d51  push    r15
0x180089d53  sub     rsp, 40h
0x180089d57  mov     r15, [rcx+160h]
0x180089d5e  mov     rbx, rdx
0x180089d61  mov     r14, rcx
0x180089d64  test    r15, r15
0x180089d67  jz      loc_180089F2A
0x180089d6d  mov     r13, [rcx]
0x180089d70  call    addArgumentToVtab
0x180089d75  mov     qword ptr [r14+180h], 0
0x180089d80  cmp     dword ptr [r15+40h], 1
0x180089d85  jl      loc_180089F2A
0x180089d8b  cmp     byte ptr [r13+0C5h], 0
0x180089d93  jnz     loc_180089EEF
0x180089d99  mov     rax, [r14+0B0h]
0x180089da0  lea     r8, [r14+110h]
0x180089da7  test    rax, rax
0x180089daa  mov     rcx, r14
0x180089dad  cmovnz  rcx, rax
0x180089db1  mov     byte ptr [rcx+21h], 1
0x180089db5  test    rbx, rbx
0x180089db8  jz      short loc_180089DC9
0x180089dba  mov     eax, [rbx+8]
0x180089dbd  sub     eax, [r8]
0x180089dc0  add     eax, [rbx]
0x180089dc2  mov     [r14+118h], eax
0x180089dc9  lea     rdx, aCreateVirtualT; "CREATE VIRTUAL TABLE %T"
0x180089dd0  mov     rcx, r13
0x180089dd3  call    sqlite3MPrintf
0x180089dd8  mov     rdx, [r15+60h]
0x180089ddc  mov     rcx, r13
0x180089ddf  mov     rsi, rax
0x180089de2  call    sqlite3SchemaToIndex
0x180089de7  mov     ecx, [r14+88h]
0x180089dee  lea     rdx, aUpdateQSqliteM; "UPDATE %Q.sqlite_master SET type='table"...
0x180089df5  mov     r8, [r13+20h]
0x180089df9  mov     r9, [r15]
0x180089dfc  mov     [rsp+78h+var_48], ecx
0x180089e00  mov     rcx, r14
0x180089e03  movsxd  rbp, eax
0x180089e06  mov     rbx, rbp
0x180089e09  mov     [rsp+78h+var_50], rsi
0x180089e0e  shl     rbx, 5
0x180089e12  mov     [rsp+78h+var_58], r9
0x180089e17  mov     r8, [r8+rbx]
0x180089e1b  call    sqlite3NestedParse
0x180089e20  mov     rcx, r14
0x180089e23  call    sqlite3GetVdbe
0x180089e28  mov     rcx, [r14]
0x180089e2b  mov     r9d, 1
0x180089e31  mov     r8d, ebp
0x180089e34  mov     rdi, rax
0x180089e37  mov     rdx, [rcx+20h]
0x180089e3b  mov     rcx, [rdx+rbx+18h]
0x180089e40  mov     edx, [rcx]
0x180089e42  mov     rcx, [r14+10h]
0x180089e46  inc     edx
0x180089e48  mov     dword ptr [rsp+78h+var_58], edx
0x180089e4c  lea     edx, [r9+63h]
0x180089e50  call    sqlite3VdbeAddOp3
0x180089e55  xor     r9d, r9d
0x180089e58  mov     dword ptr [rsp+78h+var_58], 0
0x180089e60  xor     r8d, r8d
0x180089e63  mov     edx, 0A6h
0x180089e68  mov     rcx, rdi
0x180089e6b  call    sqlite3VdbeAddOp3
0x180089e70  mov     r8, [r15]
0x180089e73  lea     rdx, aNameQAndSqlQ; "name=%Q AND sql=%Q"
0x180089e7a  mov     r9, rsi
0x180089e7d  mov     rcx, r13
0x180089e80  call    sqlite3MPrintf
0x180089e85  xor     r9d, r9d
0x180089e88  mov     r8, rax
0x180089e8b  mov     edx, ebp
0x180089e8d  mov     rcx, rdi
0x180089e90  call    sqlite3VdbeAddParseSchemaOp
0x180089e95  mov     rdx, rsi
0x180089e98  mov     rcx, r13
0x180089e9b  call    sqlite3DbFree
0x180089ea0  inc     dword ptr [r14+3Ch]
0x180089ea4  xor     r8d, r8d
0x180089ea7  mov     rax, [r15]
0x180089eaa  mov     rcx, rdi
0x180089ead  mov     ebx, [r14+3Ch]
0x180089eb1  mov     r9d, ebx
0x180089eb4  mov     [rsp+78h+var_48], 0
0x180089ebc  mov     [rsp+78h+var_50], rax
0x180089ec1  lea     edx, [r8+76h]
0x180089ec5  mov     dword ptr [rsp+78h+var_58], 0
0x180089ecd  call    sqlite3VdbeAddOp4
0x180089ed2  mov     r9d, ebx
0x180089ed5  mov     dword ptr [rsp+78h+var_58], 0
0x180089edd  mov     r8d, ebp
0x180089ee0  mov     edx, 0ABh
0x180089ee5  mov     rcx, rdi
0x180089ee8  call    sqlite3VdbeAddOp3
0x180089eed  jmp     short loc_180089F2A
0x180089eef  mov     rbx, [r15+60h]
0x180089ef3  mov     rdx, r15
0x180089ef6  mov     rdi, [r15]
0x180089ef9  mov     rcx, r13
0x180089efc  call    sqlite3MarkAllShadowTablesOf
0x180089f01  lea     rcx, [rbx+8]
0x180089f05  mov     r8, r15
0x180089f08  mov     rdx, rdi
0x180089f0b  call    sqlite3HashInsert
0x180089f10  test    rax, rax
0x180089f13  jz      short loc_180089F1F
0x180089f15  mov     rcx, r13
0x180089f18  call    sqlite3OomFault
0x180089f1d  jmp     short loc_180089F2A
0x180089f1f  mov     qword ptr [r14+160h], 0
0x180089f2a  add     rsp, 40h
0x180089f2e  pop     r15
0x180089f30  pop     r14
0x180089f32  pop     r13
0x180089f34  pop     rdi
0x180089f35  pop     rsi
0x180089f36  pop     rbp
0x180089f37  pop     rbx
0x180089f38  retn
```
