# sqlite3CodeDropTable

- ea: `0x18004a7fc`
- end: `0x18004a9af`
- name: `sqlite3CodeDropTable`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18004a49c`

## callees

- `0x180009e04`
- `0x180015700`
- `0x180015eb0`
- `0x1800168c0`
- `0x180016c60`
- `0x18004a2d0`
- `0x18004a7fc`
- `0x18004a9b8`
- `0x18004ab20`
- `0x18006d2b8`
- `0x1800918cc`

## string_xrefs

- `0x18004a875`: `DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'`
- `0x18004a997`: `DELETE FROM %Q.sqlite_sequence WHERE name=%Q`

## pseudocode

```c
__int64 __fastcall sqlite3CodeDropTable(_QWORD *a1, __int64 *a2, unsigned int a3, int a4)
{
  __int64 v8; // rbp
  __int64 v9; // r15
  __int64 Vdbe; // r14
  __int64 v11; // r9
  __int64 i; // rsi
  __int64 v13; // rbx
  unsigned int v14; // eax
  _QWORD *v16; // rcx
  __int64 v17; // [rsp+90h] [rbp+8h]

  v17 = *a1;
  v8 = 32LL * (int)a3;
  v9 = *(_QWORD *)(*a1 + 32LL);
  Vdbe = sqlite3GetVdbe(a1);
  sqlite3BeginWriteOperation(a1, 1, a3, v11);
  if ( *((_BYTE *)a2 + 63) == 1 )
    sqlite3VdbeAddOp3(Vdbe, 170, 0, 0, 0);
  for ( i = sqlite3TriggerList(a1, a2); i; i = *(_QWORD *)(i + 64) )
    sqlite3DropTriggerPtr(a1, i);
  if ( (a2[6] & 8) != 0 )
    sqlite3NestedParse(a1, "DELETE FROM %Q.sqlite_sequence WHERE name=%Q", *(_QWORD *)(v9 + v8), *a2);
  sqlite3NestedParse(
    a1,
    "DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'",
    *(_QWORD *)(v9 + v8),
    *a2);
  if ( a4 )
  {
LABEL_9:
    if ( *((_BYTE *)a2 + 63) != 1 )
      goto LABEL_10;
    goto LABEL_11;
  }
  if ( *((_BYTE *)a2 + 63) != 1 )
  {
    destroyTable(a1, a2);
    goto LABEL_9;
  }
LABEL_11:
  sqlite3VdbeAddOp4(Vdbe, 172, a3, 0, 0, *a2, 0);
  v16 = a1;
  if ( a1[22] )
    v16 = (_QWORD *)a1[22];
  *((_BYTE *)v16 + 33) = 1;
LABEL_10:
  v13 = *a2;
  v14 = sqlite3VdbeAddOp3(Vdbe, 151, a3, 0, 0);
  sqlite3VdbeChangeP4(Vdbe, v14, v13, 0);
  sqlite3VdbeAddOp3(a1[2], 100, a3, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32LL) + v8 + 24) + 1);
  return sqliteViewResetAll(v17, a3);
}

```

## disassembly

```asm
0x18004a7fc  push    rbx
0x18004a7fe  push    rbp
0x18004a7ff  push    rsi
0x18004a800  push    rdi
0x18004a801  push    r12
0x18004a803  push    r13
0x18004a805  push    r14
0x18004a807  push    r15
0x18004a809  sub     rsp, 48h
0x18004a80d  mov     rax, [rcx]
0x18004a810  mov     r13d, r9d
0x18004a813  movsxd  r12, r8d
0x18004a816  mov     rbx, rdx
0x18004a819  mov     rbp, r12
0x18004a81c  mov     [rsp+88h+arg_0], rax
0x18004a824  mov     rdi, rcx
0x18004a827  shl     rbp, 5
0x18004a82b  mov     r15, [rax+20h]
0x18004a82f  call    sqlite3GetVdbe
0x18004a834  mov     r8d, r12d
0x18004a837  mov     edx, 1
0x18004a83c  mov     rcx, rdi
0x18004a83f  mov     r14, rax
0x18004a842  call    sqlite3BeginWriteOperation
0x18004a847  cmp     byte ptr [rbx+3Fh], 1
0x18004a84b  jz      loc_18004A95B
0x18004a851  mov     rdx, rbx
0x18004a854  mov     rcx, rdi
0x18004a857  call    sqlite3TriggerList
0x18004a85c  mov     rsi, rax
0x18004a85f  test    rax, rax
0x18004a862  jnz     loc_18004A97B
0x18004a868  test    byte ptr [rbx+30h], 8
0x18004a86c  jnz     loc_18004A994
0x18004a872  mov     r9, [rbx]
0x18004a875  lea     rdx, aDeleteFromQSql_1; "DELETE FROM %Q.sqlite_master WHERE tbl_"...
0x18004a87c  mov     r8, [r15+rbp]
0x18004a880  mov     rcx, rdi
0x18004a883  call    sqlite3NestedParse
0x18004a888  xor     esi, esi
0x18004a88a  test    r13d, r13d
0x18004a88d  jnz     short loc_18004A8A4
0x18004a88f  cmp     byte ptr [rbx+3Fh], 1
0x18004a893  jz      loc_18004A91E
0x18004a899  mov     rdx, rbx
0x18004a89c  mov     rcx, rdi
0x18004a89f  call    destroyTable
0x18004a8a4  cmp     byte ptr [rbx+3Fh], 1
0x18004a8a8  jz      short loc_18004A91E
0x18004a8aa  mov     rbx, [rbx]
0x18004a8ad  xor     r9d, r9d
0x18004a8b0  mov     r8d, r12d
0x18004a8b3  mov     [rsp+88h+var_68], esi
0x18004a8b7  mov     edx, 97h
0x18004a8bc  mov     rcx, r14
0x18004a8bf  call    sqlite3VdbeAddOp3
0x18004a8c4  xor     r9d, r9d
0x18004a8c7  mov     r8, rbx
0x18004a8ca  mov     edx, eax
0x18004a8cc  mov     rcx, r14
0x18004a8cf  call    sqlite3VdbeChangeP4
0x18004a8d4  mov     rax, [rdi]
0x18004a8d7  mov     r9d, 1
0x18004a8dd  mov     rcx, [rdi+10h]
0x18004a8e1  mov     r8d, r12d
0x18004a8e4  mov     rdx, [rax+20h]
0x18004a8e8  mov     rax, [rdx+rbp+18h]
0x18004a8ed  mov     edx, [rax]
0x18004a8ef  inc     edx
0x18004a8f1  mov     [rsp+88h+var_68], edx
0x18004a8f5  lea     edx, [r9+63h]
0x18004a8f9  call    sqlite3VdbeAddOp3
0x18004a8fe  mov     rcx, [rsp+88h+arg_0]
0x18004a906  mov     edx, r12d
0x18004a909  add     rsp, 48h
0x18004a90d  pop     r15
0x18004a90f  pop     r14
0x18004a911  pop     r13
0x18004a913  pop     r12
0x18004a915  pop     rdi
0x18004a916  pop     rsi
0x18004a917  pop     rbp
0x18004a918  pop     rbx
0x18004a919  jmp     sqliteViewResetAll
0x18004a91e  mov     rax, [rbx]
0x18004a921  xor     r9d, r9d
0x18004a924  mov     [rsp+88h+var_58], esi
0x18004a928  mov     r8d, r12d
0x18004a92b  mov     [rsp+88h+var_60], rax
0x18004a930  mov     edx, 0ACh
0x18004a935  mov     rcx, r14
0x18004a938  mov     [rsp+88h+var_68], esi
0x18004a93c  call    sqlite3VdbeAddOp4
0x18004a941  mov     rax, [rdi+0B0h]
0x18004a948  mov     rcx, rdi
0x18004a94b  test    rax, rax
0x18004a94e  cmovnz  rcx, rax
0x18004a952  mov     byte ptr [rcx+21h], 1
0x18004a956  jmp     loc_18004A8AA
0x18004a95b  xor     r9d, r9d
0x18004a95e  mov     [rsp+88h+var_68], 0
0x18004a966  xor     r8d, r8d
0x18004a969  mov     edx, 0AAh
0x18004a96e  mov     rcx, r14
0x18004a971  call    sqlite3VdbeAddOp3
0x18004a976  jmp     loc_18004A851
0x18004a97b  mov     rdx, rsi
0x18004a97e  mov     rcx, rdi
0x18004a981  call    sqlite3DropTriggerPtr
0x18004a986  mov     rsi, [rsi+40h]
0x18004a98a  test    rsi, rsi
0x18004a98d  jnz     short loc_18004A97B
0x18004a98f  jmp     loc_18004A868
0x18004a994  mov     r9, [rbx]
0x18004a997  lea     rdx, aDeleteFromQSql_0; "DELETE FROM %Q.sqlite_sequence WHERE na"...
0x18004a99e  mov     r8, [r15+rbp]
0x18004a9a2  mov     rcx, rdi
0x18004a9a5  call    sqlite3NestedParse
0x18004a9aa  jmp     loc_18004A872
```
