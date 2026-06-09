# sqlite3AlterRenameColumn

- ea: `0x1800fc990`
- end: `0x1800fccdc`
- name: `sqlite3AlterRenameColumn`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180174050`

## callees

- `0x1800da2a0`
- `0x1800f30d0`
- `0x1800f3430`
- `0x1800f3b20`
- `0x1800fc990`
- `0x1800fdf90`
- `0x180108840`
- `0x18010b290`
- `0x18011d960`
- `0x18011eaa0`
- `0x18011ec20`
- `0x180130eb0`

## string_xrefs

- `0x1800fcc6c`: `after rename`
- `0x1800fca18`: `rename columns of`
- `0x1800fcbfc`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`
- `0x1800fcc2d`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameColumn(_QWORD *a1, __int64 a2, __int64 a3, unsigned __int8 **a4)
{
  __int64 v4; // r15
  __int64 v6; // rdi
  __int64 v7; // rbp
  __int64 v9; // r14
  __int64 TableItem; // rax
  _QWORD *v11; // r13
  const char *v12; // r9
  __int64 result; // rax
  __int64 v14; // rcx
  int v15; // esi
  _QWORD *i; // rax
  __int16 v17; // dx
  int v18; // r12d
  _QWORD *v19; // r11
  __int64 v20; // r10
  unsigned __int8 *v21; // rax
  __int64 v22; // r9
  unsigned __int8 v23; // r8
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // [rsp+20h] [rbp-88h]
  int v27; // [rsp+38h] [rbp-70h]
  __int64 v28; // [rsp+50h] [rbp-58h]

  v4 = *a1;
  v6 = a2;
  v7 = 0;
  v9 = 0;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v11 = (_QWORD *)TableItem;
  if ( !TableItem || (unsigned int)isAlterableTable(a1, TableItem) )
    goto LABEL_31;
  v12 = "view";
  if ( *((_BYTE *)v11 + 63) != 2 )
    v12 = 0;
  if ( *((_BYTE *)v11 + 63) == 1 )
  {
    v12 = "virtual table";
LABEL_8:
    sqlite3ErrorMsg(a1, "cannot %s %s \"%s\"", "rename columns of", v12, (const char *)*v11);
    return sqlite3SrcListDelete(v4, v6);
  }
  if ( v12 )
    goto LABEL_8;
  v14 = v11[12];
  v15 = -32768;
  if ( v14 )
  {
    v15 = 0;
    for ( i = (_QWORD *)(*(_QWORD *)(v4 + 32) + 24LL); *i != v14; i += 4 )
      ++v15;
  }
  v28 = *(_QWORD *)(32LL * v15 + *(_QWORD *)(v4 + 32));
  if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v28, *v11, 0) )
    goto LABEL_31;
  v9 = sqlite3NameFromToken(v4, a3);
  if ( !v9 )
    goto LABEL_31;
  v17 = *((_WORD *)v11 + 27);
  v18 = 0;
  if ( v17 > 0 )
  {
    v19 = (_QWORD *)v11[1];
    v20 = 0;
    do
    {
      v21 = (unsigned __int8 *)v9;
      v22 = *v19 - v9;
      while ( 1 )
      {
        while ( 1 )
        {
          v23 = v21[v22];
          v24 = *v21;
          if ( v23 != (_BYTE)v24 )
            break;
          if ( !v23 )
            goto LABEL_23;
          ++v21;
        }
        if ( *((unsigned __int8 *)qword_18026E880 + v21[v22]) != *((unsigned __int8 *)qword_18026E880 + v24) )
          break;
        ++v21;
      }
      ++v18;
      ++v20;
      v19 += 3;
    }
    while ( v20 < *((__int16 *)v11 + 27) );
LABEL_23:
    v6 = a2;
    v17 = *((_WORD *)v11 + 27);
  }
  if ( v18 != v17 )
  {
    renameTestSchema((_DWORD)a1, v28, v15 == 1, (unsigned int)&byte_1802990D8, 0);
    renameFixQuotes(a1, v28, v15 == 1);
    v25 = a1;
    if ( a1[21] )
      v25 = (_QWORD *)a1[21];
    *((_BYTE *)v25 + 33) = 1;
    v7 = sqlite3NameFromToken(v4, a4);
    if ( v7 )
    {
      v27 = *((_BYTE *)&qword_18026E9A0 + **a4) & 0x80;
      v26 = *v11;
      sqlite3NestedParse(
        a1,
        "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name N"
        "OT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)",
        v28);
      LODWORD(v26) = v18;
      sqlite3NestedParse(
        a1,
        "UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ("
        "'trigger', 'view')",
        v28,
        *v11,
        v26,
        v7,
        __PAIR64__(HIDWORD(v7), v27));
      renameReloadSchema(a1, (unsigned int)v15, 1);
      renameTestSchema((_DWORD)a1, v28, v15 == 1, (unsigned int)"after rename", 1);
      sqlite3SrcListDelete(v4, a2);
      goto LABEL_32;
    }
    v6 = a2;
LABEL_31:
    result = sqlite3SrcListDelete(v4, v6);
    if ( !v9 )
      goto LABEL_33;
    goto LABEL_32;
  }
  sqlite3ErrorMsg(a1, "no such column: \"%T\"", a3);
  sqlite3SrcListDelete(v4, v6);
LABEL_32:
  result = sqlite3DbFreeNN(v4);
LABEL_33:
  if ( v7 )
    return sqlite3DbFreeNN(v4);
  return result;
}

```

## disassembly

```asm
0x1800fc990  mov     [rsp+arg_18], r9
0x1800fc995  mov     [rsp+arg_10], r8
0x1800fc99a  mov     [rsp+arg_8], rdx
0x1800fc99f  mov     [rsp+arg_0], rcx
0x1800fc9a4  push    rbx
0x1800fc9a5  push    rbp
0x1800fc9a6  push    rsi
0x1800fc9a7  push    rdi
0x1800fc9a8  push    r12
0x1800fc9aa  push    r13
0x1800fc9ac  push    r14
0x1800fc9ae  push    r15
0x1800fc9b0  sub     rsp, 68h
0x1800fc9b4  mov     r15, [rcx]
0x1800fc9b7  mov     r12, r8
0x1800fc9ba  lea     r8, [rdx+8]
0x1800fc9be  mov     rdi, rdx
0x1800fc9c1  xor     ebp, ebp
0x1800fc9c3  xor     edx, edx
0x1800fc9c5  mov     rbx, rcx
0x1800fc9c8  mov     r14d, ebp
0x1800fc9cb  call    sqlite3LocateTableItem
0x1800fc9d0  mov     r13, rax
0x1800fc9d3  test    rax, rax
0x1800fc9d6  jz      loc_1800FCCA0
0x1800fc9dc  mov     rdx, rax
0x1800fc9df  mov     rcx, rbx
0x1800fc9e2  call    isAlterableTable
0x1800fc9e7  test    eax, eax
0x1800fc9e9  jnz     loc_1800FCCA0
0x1800fc9ef  cmp     byte ptr [r13+3Fh], 2
0x1800fc9f4  lea     r9, aView_0; "view"
0x1800fc9fb  cmovnz  r9, rbp
0x1800fc9ff  cmp     byte ptr [r13+3Fh], 1
0x1800fca04  jnz     short loc_1800FCA0F
0x1800fca06  lea     r9, aVirtualTable; "virtual table"
0x1800fca0d  jmp     short loc_1800FCA14
0x1800fca0f  test    r9, r9
0x1800fca12  jz      short loc_1800FCA43
0x1800fca14  mov     rax, [r13+0]
0x1800fca18  lea     r8, aRenameColumnsO; "rename columns of"
0x1800fca1f  lea     rdx, aCannotSSS; "cannot %s %s \"%s\""
0x1800fca26  mov     [rsp+0A8h+var_88], rax
0x1800fca2b  mov     rcx, rbx
0x1800fca2e  call    sqlite3ErrorMsg
0x1800fca33  mov     rdx, rdi
0x1800fca36  mov     rcx, r15
0x1800fca39  call    sqlite3SrcListDelete
0x1800fca3e  jmp     loc_1800FCCCB
0x1800fca43  mov     rcx, [r13+60h]
0x1800fca47  mov     esi, 0FFFF8000h
0x1800fca4c  test    rcx, rcx
0x1800fca4f  jz      short loc_1800FCA6B
0x1800fca51  mov     rax, [r15+20h]
0x1800fca55  mov     esi, ebp
0x1800fca57  add     rax, 18h
0x1800fca5b  cmp     [rax], rcx
0x1800fca5e  jz      short loc_1800FCA6B
0x1800fca60  inc     esi
0x1800fca62  lea     rax, [rax+20h]
0x1800fca66  cmp     [rax], rcx
0x1800fca69  jnz     short loc_1800FCA60
0x1800fca6b  mov     rax, [r15+20h]
0x1800fca6f  mov     edx, 1Ah
0x1800fca74  mov     r9, [r13+0]
0x1800fca78  movsxd  rcx, esi
0x1800fca7b  shl     rcx, 5
0x1800fca7f  mov     [rsp+0A8h+var_88], rbp
0x1800fca84  mov     rax, [rcx+rax]
0x1800fca88  mov     rcx, rbx
0x1800fca8b  mov     r8, rax
0x1800fca8e  mov     [rsp+0A8h+var_58], rax
0x1800fca93  call    sqlite3AuthCheck
0x1800fca98  test    eax, eax
0x1800fca9a  jnz     loc_1800FCCA0
0x1800fcaa0  mov     rdx, r12
0x1800fcaa3  mov     rcx, r15
0x1800fcaa6  call    sqlite3NameFromToken
0x1800fcaab  mov     r14, rax
0x1800fcaae  test    rax, rax
0x1800fcab1  jz      loc_1800FCCA0
0x1800fcab7  movsx   rdx, word ptr [r13+36h]
0x1800fcabc  mov     r12d, ebp
0x1800fcabf  cmp     bp, dx
0x1800fcac2  jge     short loc_1800FCB3E
0x1800fcac4  mov     r11, [r13+8]
0x1800fcac8  mov     rdi, rdx
0x1800fcacb  mov     r10, rbp
0x1800fcace  xchg    ax, ax
0x1800fcad0  mov     r9, [r11]
0x1800fcad3  mov     rax, r14
0x1800fcad6  sub     r9, r14
0x1800fcad9  nop     dword ptr [rax+00000000h]
0x1800fcae0  movzx   r8d, byte ptr [r9+rax]
0x1800fcae5  movzx   ecx, byte ptr [rax]
0x1800fcae8  cmp     r8b, cl
0x1800fcaeb  jnz     short loc_1800FCAF7
0x1800fcaed  test    r8b, r8b
0x1800fcaf0  jz      short loc_1800FCB31
0x1800fcaf2  inc     rax
0x1800fcaf5  jmp     short loc_1800FCAE0
0x1800fcaf7  lea     rdx, cs:180000000h
0x1800fcafe  movzx   edx, byte ptr [rcx+rdx+26E880h]
0x1800fcb06  mov     rcx, r8
0x1800fcb09  lea     r8, cs:180000000h
0x1800fcb10  movzx   ecx, byte ptr [rcx+r8+26E880h]
0x1800fcb19  cmp     ecx, edx
0x1800fcb1b  jnz     short loc_1800FCB22
0x1800fcb1d  inc     rax
0x1800fcb20  jmp     short loc_1800FCAE0
0x1800fcb22  inc     r12d
0x1800fcb25  inc     r10
0x1800fcb28  add     r11, 18h
0x1800fcb2c  cmp     r10, rdi
0x1800fcb2f  jl      short loc_1800FCAD0
0x1800fcb31  mov     rdi, [rsp+0A8h+arg_8]
0x1800fcb39  movzx   edx, word ptr [r13+36h]
0x1800fcb3e  movsx   eax, dx
0x1800fcb41  mov     rcx, rbx
0x1800fcb44  cmp     r12d, eax
0x1800fcb47  jnz     short loc_1800FCB6D
0x1800fcb49  mov     r8, [rsp+0A8h+arg_10]
0x1800fcb51  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x1800fcb58  call    sqlite3ErrorMsg
0x1800fcb5d  mov     rdx, rdi
0x1800fcb60  mov     rcx, r15
0x1800fcb63  call    sqlite3SrcListDelete
0x1800fcb68  jmp     loc_1800FCCB0
0x1800fcb6d  mov     rdx, [rsp+0A8h+var_58]
0x1800fcb72  lea     r9, byte_1802990D8
0x1800fcb79  mov     edi, ebp
0x1800fcb7b  mov     dword ptr [rsp+0A8h+var_88], ebp
0x1800fcb7f  cmp     esi, 1
0x1800fcb82  setz    dil
0x1800fcb86  mov     r8d, edi
0x1800fcb89  call    renameTestSchema
0x1800fcb8e  mov     rdx, [rsp+0A8h+var_58]
0x1800fcb93  mov     r8d, edi
0x1800fcb96  mov     rcx, rbx
0x1800fcb99  call    renameFixQuotes
0x1800fcb9e  mov     rax, [rbx+0A8h]
0x1800fcba5  mov     rcx, rbx
0x1800fcba8  mov     rbx, [rsp+0A8h+arg_18]
0x1800fcbb0  test    rax, rax
0x1800fcbb3  mov     rdx, rbx
0x1800fcbb6  cmovnz  rcx, rax
0x1800fcbba  mov     byte ptr [rcx+21h], 1
0x1800fcbbe  mov     rcx, r15
0x1800fcbc1  call    sqlite3NameFromToken
0x1800fcbc6  mov     rbp, rax
0x1800fcbc9  test    rax, rax
0x1800fcbcc  jz      loc_1800FCC98
0x1800fcbd2  mov     rcx, [rbx]
0x1800fcbd5  lea     rax, cs:180000000h
0x1800fcbdc  mov     r9, [rsp+0A8h+var_58]
0x1800fcbe1  mov     r8, r9
0x1800fcbe4  movzx   edx, byte ptr [rcx]
0x1800fcbe7  mov     rcx, [r13+0]
0x1800fcbeb  mov     [rsp+0A8h+var_60], rcx
0x1800fcbf0  mov     [rsp+0A8h+var_68], edi
0x1800fcbf4  movzx   ebx, byte ptr [rdx+rax+26E9A0h]
0x1800fcbfc  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1800fcc03  and     ebx, 80h
0x1800fcc09  mov     [rsp+0A8h+var_70], ebx
0x1800fcc0d  mov     [rsp+0A8h+var_78], rbp
0x1800fcc12  mov     dword ptr [rsp+0A8h+var_80], r12d
0x1800fcc17  mov     [rsp+0A8h+var_88], rcx
0x1800fcc1c  mov     rcx, [rsp+0A8h+arg_0]
0x1800fcc24  call    sqlite3NestedParse
0x1800fcc29  mov     r9, [r13+0]
0x1800fcc2d  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x1800fcc34  mov     r8, [rsp+0A8h+var_58]
0x1800fcc39  mov     dword ptr [rsp+0A8h+var_78], ebx
0x1800fcc3d  mov     rbx, [rsp+0A8h+arg_0]
0x1800fcc45  mov     rcx, rbx
0x1800fcc48  mov     [rsp+0A8h+var_80], rbp
0x1800fcc4d  mov     dword ptr [rsp+0A8h+var_88], r12d
0x1800fcc52  call    sqlite3NestedParse
0x1800fcc57  mov     r8d, 1
0x1800fcc5d  mov     edx, esi
0x1800fcc5f  mov     rcx, rbx
0x1800fcc62  call    renameReloadSchema
0x1800fcc67  mov     rdx, [rsp+0A8h+var_58]
0x1800fcc6c  lea     r9, aAfterRename; "after rename"
0x1800fcc73  mov     r8d, edi
0x1800fcc76  mov     dword ptr [rsp+0A8h+var_88], 1
0x1800fcc7e  mov     rcx, rbx
0x1800fcc81  call    renameTestSchema
0x1800fcc86  mov     rdx, [rsp+0A8h+arg_8]
0x1800fcc8e  mov     rcx, r15
0x1800fcc91  call    sqlite3SrcListDelete
0x1800fcc96  jmp     short loc_1800FCCB0
0x1800fcc98  mov     rdi, [rsp+0A8h+arg_8]
0x1800fcca0  mov     rdx, rdi
0x1800fcca3  mov     rcx, r15
0x1800fcca6  call    sqlite3SrcListDelete
0x1800fccab  test    r14, r14
0x1800fccae  jz      short loc_1800FCCBB
0x1800fccb0  mov     rdx, r14
0x1800fccb3  mov     rcx, r15
0x1800fccb6  call    sqlite3DbFreeNN
0x1800fccbb  test    rbp, rbp
0x1800fccbe  jz      short loc_1800FCCCB
0x1800fccc0  mov     rdx, rbp
0x1800fccc3  mov     rcx, r15
0x1800fccc6  call    sqlite3DbFreeNN
0x1800fcccb  add     rsp, 68h
0x1800fcccf  pop     r15
0x1800fccd1  pop     r14
0x1800fccd3  pop     r13
0x1800fccd5  pop     r12
0x1800fccd7  pop     rdi
0x1800fccd8  pop     rsi
0x1800fccd9  pop     rbp
0x1800fccda  pop     rbx
0x1800fccdb  retn
```
