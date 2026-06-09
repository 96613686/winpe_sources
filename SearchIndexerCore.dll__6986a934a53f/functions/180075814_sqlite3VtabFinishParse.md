# sqlite3VtabFinishParse

- ea: `0x180075814`
- end: `0x180075a05`
- name: `sqlite3VtabFinishParse`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000213c`

## callees

- `0x180015700`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001f418`
- `0x18003bc90`
- `0x180040e00`
- `0x180041d10`
- `0x18004a9b8`
- `0x180058730`
- `0x18006dc30`
- `0x180075814`
- `0x1800770f8`
- `0x18009326c`

## string_xrefs

- `0x180075895`: `CREATE VIRTUAL TABLE %T`
- `0x1800758ba`: `UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d`

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
0x180075814  push    rbx
0x180075816  push    rbp
0x180075817  push    rsi
0x180075818  push    rdi
0x180075819  push    r13
0x18007581b  push    r14
0x18007581d  push    r15
0x18007581f  sub     rsp, 40h
0x180075823  mov     r15, [rcx+160h]
0x18007582a  mov     rbx, rdx
0x18007582d  mov     r14, rcx
0x180075830  test    r15, r15
0x180075833  jz      loc_1800759F6
0x180075839  mov     r13, [rcx]
0x18007583c  call    addArgumentToVtab
0x180075841  mov     qword ptr [r14+180h], 0
0x18007584c  cmp     dword ptr [r15+40h], 1
0x180075851  jl      loc_1800759F6
0x180075857  cmp     byte ptr [r13+0C5h], 0
0x18007585f  jnz     loc_1800759BB
0x180075865  mov     rax, [r14+0B0h]
0x18007586c  lea     r8, [r14+110h]
0x180075873  test    rax, rax
0x180075876  mov     rcx, r14
0x180075879  cmovnz  rcx, rax
0x18007587d  mov     byte ptr [rcx+21h], 1
0x180075881  test    rbx, rbx
0x180075884  jz      short loc_180075895
0x180075886  mov     eax, [rbx+8]
0x180075889  sub     eax, [r8]
0x18007588c  add     eax, [rbx]
0x18007588e  mov     [r14+118h], eax
0x180075895  lea     rdx, aCreateVirtualT; "CREATE VIRTUAL TABLE %T"
0x18007589c  mov     rcx, r13
0x18007589f  call    sqlite3MPrintf
0x1800758a4  mov     rdx, [r15+60h]
0x1800758a8  mov     rcx, r13
0x1800758ab  mov     rsi, rax
0x1800758ae  call    sqlite3SchemaToIndex
0x1800758b3  mov     ecx, [r14+88h]
0x1800758ba  lea     rdx, aUpdateQSqliteM; "UPDATE %Q.sqlite_master SET type='table"...
0x1800758c1  mov     r8, [r13+20h]
0x1800758c5  mov     r9, [r15]
0x1800758c8  mov     [rsp+78h+var_48], ecx
0x1800758cc  mov     rcx, r14
0x1800758cf  movsxd  rbp, eax
0x1800758d2  mov     rbx, rbp
0x1800758d5  mov     [rsp+78h+var_50], rsi
0x1800758da  shl     rbx, 5
0x1800758de  mov     [rsp+78h+var_58], r9
0x1800758e3  mov     r8, [r8+rbx]
0x1800758e7  call    sqlite3NestedParse
0x1800758ec  mov     rcx, r14
0x1800758ef  call    sqlite3GetVdbe
0x1800758f4  mov     rcx, [r14]
0x1800758f7  mov     r9d, 1
0x1800758fd  mov     r8d, ebp
0x180075900  mov     rdi, rax
0x180075903  mov     rdx, [rcx+20h]
0x180075907  mov     rcx, [rdx+rbx+18h]
0x18007590c  mov     edx, [rcx]
0x18007590e  mov     rcx, [r14+10h]
0x180075912  inc     edx
0x180075914  mov     dword ptr [rsp+78h+var_58], edx
0x180075918  lea     edx, [r9+63h]
0x18007591c  call    sqlite3VdbeAddOp3
0x180075921  xor     r9d, r9d
0x180075924  mov     dword ptr [rsp+78h+var_58], 0
0x18007592c  xor     r8d, r8d
0x18007592f  mov     edx, 0A6h
0x180075934  mov     rcx, rdi
0x180075937  call    sqlite3VdbeAddOp3
0x18007593c  mov     r8, [r15]
0x18007593f  lea     rdx, aNameQAndSqlQ; "name=%Q AND sql=%Q"
0x180075946  mov     r9, rsi
0x180075949  mov     rcx, r13
0x18007594c  call    sqlite3MPrintf
0x180075951  xor     r9d, r9d
0x180075954  mov     r8, rax
0x180075957  mov     edx, ebp
0x180075959  mov     rcx, rdi
0x18007595c  call    sqlite3VdbeAddParseSchemaOp
0x180075961  mov     rdx, rsi
0x180075964  mov     rcx, r13
0x180075967  call    sqlite3DbFree
0x18007596c  inc     dword ptr [r14+38h]
0x180075970  xor     r8d, r8d
0x180075973  mov     rax, [r15]
0x180075976  mov     rcx, rdi
0x180075979  mov     ebx, [r14+38h]
0x18007597d  mov     r9d, ebx
0x180075980  mov     [rsp+78h+var_48], 0
0x180075988  mov     [rsp+78h+var_50], rax
0x18007598d  lea     edx, [r8+75h]
0x180075991  mov     dword ptr [rsp+78h+var_58], 0
0x180075999  call    sqlite3VdbeAddOp4
0x18007599e  mov     r9d, ebx
0x1800759a1  mov     dword ptr [rsp+78h+var_58], 0
0x1800759a9  mov     r8d, ebp
0x1800759ac  mov     edx, 0ABh
0x1800759b1  mov     rcx, rdi
0x1800759b4  call    sqlite3VdbeAddOp3
0x1800759b9  jmp     short loc_1800759F6
0x1800759bb  mov     rbx, [r15+60h]
0x1800759bf  mov     rdx, r15
0x1800759c2  mov     rdi, [r15]
0x1800759c5  mov     rcx, r13
0x1800759c8  call    sqlite3MarkAllShadowTablesOf
0x1800759cd  lea     rcx, [rbx+8]
0x1800759d1  mov     r8, r15
0x1800759d4  mov     rdx, rdi
0x1800759d7  call    sqlite3HashInsert
0x1800759dc  test    rax, rax
0x1800759df  jz      short loc_1800759EB
0x1800759e1  mov     rcx, r13
0x1800759e4  call    sqlite3OomFault
0x1800759e9  jmp     short loc_1800759F6
0x1800759eb  mov     qword ptr [r14+160h], 0
0x1800759f6  add     rsp, 40h
0x1800759fa  pop     r15
0x1800759fc  pop     r14
0x1800759fe  pop     r13
0x180075a00  pop     rdi
0x180075a01  pop     rsi
0x180075a02  pop     rbp
0x180075a03  pop     rbx
0x180075a04  retn
```
