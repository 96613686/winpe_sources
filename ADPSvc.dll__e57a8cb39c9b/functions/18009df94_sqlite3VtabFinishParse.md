# sqlite3VtabFinishParse

- ea: `0x18009df94`
- end: `0x18009e15f`
- name: `sqlite3VtabFinishParse`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1800c3bd8`

## callees

- `0x180035668`
- `0x18006db58`
- `0x1800716fc`
- `0x18007d478`
- `0x18007d618`
- `0x180080b64`
- `0x180080d04`
- `0x1800817f4`
- `0x180081a3c`
- `0x1800923d8`
- `0x180092638`
- `0x18009a768`
- `0x18009df94`

## string_xrefs

- `0x18009e011`: `CREATE VIRTUAL TABLE %T`
- `0x18009e051`: `UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d`

## pseudocode

```c
void __fastcall sqlite3VtabFinishParse(__int64 *a1, _DWORD *a2)
{
  int *v2; // r14
  __int64 v5; // rbp
  _DWORD *v6; // r8
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rbx
  int v11; // edi
  __int64 v12; // rdx
  __int64 Vdbe; // r15
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rdi

  v2 = (int *)a1[44];
  if ( v2 )
  {
    v5 = *a1;
    addArgumentToVtab();
    a1[48] = 0;
    if ( v2[16] >= 1 )
    {
      if ( *(_BYTE *)(v5 + 197) )
      {
        v16 = *((_QWORD *)v2 + 12);
        v17 = *(_QWORD *)v2;
        sqlite3MarkAllShadowTablesOf(v5, v2);
        if ( sqlite3HashInsert(v16 + 8, v17, v2) )
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
        v9 = *((_QWORD *)v2 + 12);
        v10 = v8;
        v11 = -32768;
        if ( v9 )
        {
          v12 = *(_QWORD *)(v5 + 32);
          v11 = 0;
          if ( *(_QWORD *)(v12 + 24) != v9 )
          {
            do
              ++v11;
            while ( *(_QWORD *)(32LL * v11 + v12 + 24) != v9 );
          }
        }
        sqlite3NestedParse(
          a1,
          "UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d",
          *(_QWORD *)(32LL * v11 + *(_QWORD *)(v5 + 32)));
        Vdbe = sqlite3GetVdbe(a1);
        sqlite3ChangeCookie(a1, (unsigned int)v11);
        sqlite3VdbeAddOp3(Vdbe, 166, 0, 0, 0);
        v14 = sqlite3MPrintf(v5, "name=%Q AND sql=%Q", *(_QWORD *)v2, v10);
        sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v11, v14, 0);
        if ( v10 )
          sqlite3DbFreeNN(v5);
        v15 = ++*((_DWORD *)a1 + 14);
        sqlite3VdbeLoadString(Vdbe, v15, *(_QWORD *)v2);
        sqlite3VdbeAddOp3(Vdbe, 171, v11, v15, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x18009df94  push    rbx
0x18009df96  push    rbp
0x18009df97  push    rsi
0x18009df98  push    rdi
0x18009df99  push    r14
0x18009df9b  push    r15
0x18009df9d  sub     rsp, 48h
0x18009dfa1  mov     r14, [rcx+160h]
0x18009dfa8  mov     rbx, rdx
0x18009dfab  mov     rsi, rcx
0x18009dfae  test    r14, r14
0x18009dfb1  jz      loc_18009E152
0x18009dfb7  mov     rbp, [rcx]
0x18009dfba  call    addArgumentToVtab
0x18009dfbf  mov     qword ptr [rsi+180h], 0
0x18009dfca  cmp     dword ptr [r14+40h], 1
0x18009dfcf  jl      loc_18009E152
0x18009dfd5  cmp     byte ptr [rbp+0C5h], 0
0x18009dfdc  jnz     loc_18009E117
0x18009dfe2  mov     rax, [rsi+0B0h]
0x18009dfe9  lea     r8, [rsi+110h]
0x18009dff0  test    rax, rax
0x18009dff3  mov     rcx, rsi
0x18009dff6  cmovnz  rcx, rax
0x18009dffa  mov     byte ptr [rcx+21h], 1
0x18009dffe  test    rbx, rbx
0x18009e001  jz      short loc_18009E011
0x18009e003  mov     eax, [rbx+8]
0x18009e006  sub     eax, [r8]
0x18009e009  add     eax, [rbx]
0x18009e00b  mov     [rsi+118h], eax
0x18009e011  lea     rdx, aCreateVirtualT; "CREATE VIRTUAL TABLE %T"
0x18009e018  mov     rcx, rbp
0x18009e01b  call    sqlite3MPrintf
0x18009e020  mov     rcx, [r14+60h]
0x18009e024  mov     rbx, rax
0x18009e027  mov     edi, 0FFFF8000h
0x18009e02c  test    rcx, rcx
0x18009e02f  jz      short loc_18009E04D
0x18009e031  mov     rdx, [rbp+20h]
0x18009e035  xor     edi, edi
0x18009e037  cmp     [rdx+18h], rcx
0x18009e03b  jz      short loc_18009E04D
0x18009e03d  inc     edi
0x18009e03f  movsxd  rax, edi
0x18009e042  shl     rax, 5
0x18009e046  cmp     [rax+rdx+18h], rcx
0x18009e04b  jnz     short loc_18009E03D
0x18009e04d  mov     r8, [rbp+20h]
0x18009e051  lea     rdx, aUpdateQSqliteM; "UPDATE %Q.sqlite_master SET type='table"...
0x18009e058  mov     eax, [rsi+88h]
0x18009e05e  mov     r9, [r14]
0x18009e061  mov     [rsp+78h+var_48], eax
0x18009e065  movsxd  rcx, edi
0x18009e068  shl     rcx, 5
0x18009e06c  mov     [rsp+78h+var_50], rbx
0x18009e071  mov     [rsp+78h+var_58], r9
0x18009e076  mov     r8, [rcx+r8]
0x18009e07a  mov     rcx, rsi
0x18009e07d  call    sqlite3NestedParse
0x18009e082  mov     rcx, rsi
0x18009e085  call    sqlite3GetVdbe
0x18009e08a  mov     edx, edi
0x18009e08c  mov     rcx, rsi
0x18009e08f  mov     r15, rax
0x18009e092  call    sqlite3ChangeCookie
0x18009e097  xor     r9d, r9d
0x18009e09a  mov     dword ptr [rsp+78h+var_58], 0
0x18009e0a2  xor     r8d, r8d
0x18009e0a5  mov     edx, 0A6h
0x18009e0aa  mov     rcx, r15
0x18009e0ad  call    sqlite3VdbeAddOp3
0x18009e0b2  mov     r8, [r14]
0x18009e0b5  lea     rdx, aNameQAndSqlQ; "name=%Q AND sql=%Q"
0x18009e0bc  mov     r9, rbx
0x18009e0bf  mov     rcx, rbp
0x18009e0c2  call    sqlite3MPrintf
0x18009e0c7  xor     r9d, r9d
0x18009e0ca  mov     r8, rax
0x18009e0cd  mov     edx, edi
0x18009e0cf  mov     rcx, r15
0x18009e0d2  call    sqlite3VdbeAddParseSchemaOp
0x18009e0d7  test    rbx, rbx
0x18009e0da  jz      short loc_18009E0E7
0x18009e0dc  mov     rdx, rbx
0x18009e0df  mov     rcx, rbp
0x18009e0e2  call    sqlite3DbFreeNN
0x18009e0e7  inc     dword ptr [rsi+38h]
0x18009e0ea  mov     rcx, r15
0x18009e0ed  mov     ebx, [rsi+38h]
0x18009e0f0  mov     edx, ebx
0x18009e0f2  mov     r8, [r14]
0x18009e0f5  call    sqlite3VdbeLoadString
0x18009e0fa  mov     r9d, ebx
0x18009e0fd  mov     dword ptr [rsp+78h+var_58], 0
0x18009e105  mov     r8d, edi
0x18009e108  mov     edx, 0ABh
0x18009e10d  mov     rcx, r15
0x18009e110  call    sqlite3VdbeAddOp3
0x18009e115  jmp     short loc_18009E152
0x18009e117  mov     rbx, [r14+60h]
0x18009e11b  mov     rdx, r14
0x18009e11e  mov     rdi, [r14]
0x18009e121  mov     rcx, rbp
0x18009e124  call    sqlite3MarkAllShadowTablesOf
0x18009e129  lea     rcx, [rbx+8]
0x18009e12d  mov     r8, r14
0x18009e130  mov     rdx, rdi
0x18009e133  call    sqlite3HashInsert
0x18009e138  test    rax, rax
0x18009e13b  jz      short loc_18009E147
0x18009e13d  mov     rcx, rbp
0x18009e140  call    sqlite3OomFault
0x18009e145  jmp     short loc_18009E152
0x18009e147  mov     qword ptr [rsi+160h], 0
0x18009e152  add     rsp, 48h
0x18009e156  pop     r15
0x18009e158  pop     r14
0x18009e15a  pop     rdi
0x18009e15b  pop     rsi
0x18009e15c  pop     rbp
0x18009e15d  pop     rbx
0x18009e15e  retn
```
