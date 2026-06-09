# sqlite3VtabFinishParse

- ea: `0x18008fce0`
- end: `0x18008fed1`
- name: `sqlite3VtabFinishParse`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18001bc30`

## callees

- `0x18000b4bc`
- `0x18003b5b4`
- `0x18003b9c8`
- `0x18003be78`
- `0x18003bebc`
- `0x18003c8d4`
- `0x18003cc7c`
- `0x18003d480`
- `0x180042bb0`
- `0x180042c38`
- `0x180052514`
- `0x180085e9c`
- `0x18008fce0`

## string_xrefs

- `0x18008fd61`: `CREATE VIRTUAL TABLE %T`
- `0x18008fd86`: `UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d`

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
    addArgumentToVtab(a1, a2);
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
        v12 = ++*((_DWORD *)a1 + 14);
        sqlite3VdbeAddOp4(Vdbe, 117, 0, v12, 0, *v2, 0);
        sqlite3VdbeAddOp3(Vdbe, 171, v9, v12, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x18008fce0  push    rbx
0x18008fce2  push    rbp
0x18008fce3  push    rsi
0x18008fce4  push    rdi
0x18008fce5  push    r13
0x18008fce7  push    r14
0x18008fce9  push    r15
0x18008fceb  sub     rsp, 40h
0x18008fcef  mov     r15, [rcx+160h]
0x18008fcf6  mov     rbx, rdx
0x18008fcf9  mov     r14, rcx
0x18008fcfc  test    r15, r15
0x18008fcff  jz      loc_18008FEC2
0x18008fd05  mov     r13, [rcx]
0x18008fd08  call    addArgumentToVtab
0x18008fd0d  mov     qword ptr [r14+180h], 0
0x18008fd18  cmp     dword ptr [r15+40h], 1
0x18008fd1d  jl      loc_18008FEC2
0x18008fd23  cmp     byte ptr [r13+0C5h], 0
0x18008fd2b  jnz     loc_18008FE87
0x18008fd31  mov     rax, [r14+0B0h]
0x18008fd38  lea     r8, [r14+110h]
0x18008fd3f  test    rax, rax
0x18008fd42  mov     rcx, r14
0x18008fd45  cmovnz  rcx, rax
0x18008fd49  mov     byte ptr [rcx+21h], 1
0x18008fd4d  test    rbx, rbx
0x18008fd50  jz      short loc_18008FD61
0x18008fd52  mov     eax, [rbx+8]
0x18008fd55  sub     eax, [r8]
0x18008fd58  add     eax, [rbx]
0x18008fd5a  mov     [r14+118h], eax
0x18008fd61  lea     rdx, aCreateVirtualT; "CREATE VIRTUAL TABLE %T"
0x18008fd68  mov     rcx, r13
0x18008fd6b  call    sqlite3MPrintf
0x18008fd70  mov     rdx, [r15+60h]
0x18008fd74  mov     rcx, r13
0x18008fd77  mov     rsi, rax
0x18008fd7a  call    sqlite3SchemaToIndex
0x18008fd7f  mov     ecx, [r14+88h]
0x18008fd86  lea     rdx, aUpdateQSqliteM; "UPDATE %Q.sqlite_master SET type='table"...
0x18008fd8d  mov     r8, [r13+20h]
0x18008fd91  mov     r9, [r15]
0x18008fd94  mov     [rsp+78h+var_48], ecx
0x18008fd98  mov     rcx, r14
0x18008fd9b  movsxd  rbp, eax
0x18008fd9e  mov     rbx, rbp
0x18008fda1  mov     [rsp+78h+var_50], rsi
0x18008fda6  shl     rbx, 5
0x18008fdaa  mov     [rsp+78h+var_58], r9
0x18008fdaf  mov     r8, [r8+rbx]
0x18008fdb3  call    sqlite3NestedParse
0x18008fdb8  mov     rcx, r14
0x18008fdbb  call    sqlite3GetVdbe
0x18008fdc0  mov     rcx, [r14]
0x18008fdc3  mov     r9d, 1
0x18008fdc9  mov     r8d, ebp
0x18008fdcc  mov     rdi, rax
0x18008fdcf  mov     rdx, [rcx+20h]
0x18008fdd3  mov     rcx, [rdx+rbx+18h]
0x18008fdd8  mov     edx, [rcx]
0x18008fdda  mov     rcx, [r14+10h]
0x18008fdde  inc     edx
0x18008fde0  mov     dword ptr [rsp+78h+var_58], edx
0x18008fde4  lea     edx, [r9+63h]
0x18008fde8  call    sqlite3VdbeAddOp3
0x18008fded  xor     r9d, r9d
0x18008fdf0  mov     dword ptr [rsp+78h+var_58], 0
0x18008fdf8  xor     r8d, r8d
0x18008fdfb  mov     edx, 0A6h
0x18008fe00  mov     rcx, rdi
0x18008fe03  call    sqlite3VdbeAddOp3
0x18008fe08  mov     r8, [r15]
0x18008fe0b  lea     rdx, aNameQAndSqlQ; "name=%Q AND sql=%Q"
0x18008fe12  mov     r9, rsi
0x18008fe15  mov     rcx, r13
0x18008fe18  call    sqlite3MPrintf
0x18008fe1d  xor     r9d, r9d
0x18008fe20  mov     r8, rax
0x18008fe23  mov     edx, ebp
0x18008fe25  mov     rcx, rdi
0x18008fe28  call    sqlite3VdbeAddParseSchemaOp
0x18008fe2d  mov     rdx, rsi
0x18008fe30  mov     rcx, r13
0x18008fe33  call    sqlite3DbFree
0x18008fe38  inc     dword ptr [r14+38h]
0x18008fe3c  xor     r8d, r8d
0x18008fe3f  mov     rax, [r15]
0x18008fe42  mov     rcx, rdi
0x18008fe45  mov     ebx, [r14+38h]
0x18008fe49  mov     r9d, ebx
0x18008fe4c  mov     [rsp+78h+var_48], 0
0x18008fe54  mov     [rsp+78h+var_50], rax
0x18008fe59  lea     edx, [r8+75h]
0x18008fe5d  mov     dword ptr [rsp+78h+var_58], 0
0x18008fe65  call    sqlite3VdbeAddOp4
0x18008fe6a  mov     r9d, ebx
0x18008fe6d  mov     dword ptr [rsp+78h+var_58], 0
0x18008fe75  mov     r8d, ebp
0x18008fe78  mov     edx, 0ABh
0x18008fe7d  mov     rcx, rdi
0x18008fe80  call    sqlite3VdbeAddOp3
0x18008fe85  jmp     short loc_18008FEC2
0x18008fe87  mov     rbx, [r15+60h]
0x18008fe8b  mov     rdx, r15
0x18008fe8e  mov     rdi, [r15]
0x18008fe91  mov     rcx, r13
0x18008fe94  call    sqlite3MarkAllShadowTablesOf
0x18008fe99  lea     rcx, [rbx+8]
0x18008fe9d  mov     r8, r15
0x18008fea0  mov     rdx, rdi
0x18008fea3  call    sqlite3HashInsert
0x18008fea8  test    rax, rax
0x18008feab  jz      short loc_18008FEB7
0x18008fead  mov     rcx, r13
0x18008feb0  call    sqlite3OomFault
0x18008feb5  jmp     short loc_18008FEC2
0x18008feb7  mov     qword ptr [r14+160h], 0
0x18008fec2  add     rsp, 40h
0x18008fec6  pop     r15
0x18008fec8  pop     r14
0x18008feca  pop     r13
0x18008fecc  pop     rdi
0x18008fecd  pop     rsi
0x18008fece  pop     rbp
0x18008fecf  pop     rbx
0x18008fed0  retn
```
