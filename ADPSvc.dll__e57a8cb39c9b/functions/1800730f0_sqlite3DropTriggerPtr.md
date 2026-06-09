# sqlite3DropTriggerPtr

- ea: `0x1800730f0`
- end: `0x180073220`
- name: `sqlite3DropTriggerPtr`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18006e0a0`
- `0x180072ff4`

## callees

- `0x180047054`
- `0x1800693b0`
- `0x18006db58`
- `0x1800730f0`
- `0x18007d478`
- `0x1800817f4`
- `0x1800923d8`
- `0x1800927e0`

## string_xrefs

- `0x18007315a`: `sqlite_temp_master`
- `0x1800731c3`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='trigger'`

## pseudocode

```c
__int64 __fastcall sqlite3DropTriggerPtr(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // r15
  __int64 v4; // rcx
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 *v9; // r9
  const char *v10; // rbp
  __int64 v11; // r9
  int v12; // edx
  __int64 v13; // r12
  __int64 result; // rax
  __int64 v15; // rbp
  __int64 v16; // rbx
  unsigned int v17; // eax

  v2 = *a1;
  v4 = a2[5];
  v6 = -32768;
  if ( v4 )
  {
    v7 = *(_QWORD *)(v2 + 32);
    v6 = 0;
    if ( *(_QWORD *)(v7 + 24) != v4 )
    {
      do
        ++v6;
      while ( *(_QWORD *)(32LL * v6 + v7 + 24) != v4 );
    }
  }
  v8 = 32LL * v6;
  v9 = *(__int64 **)(findElementWithHash(a2[6] + 8LL, a2[1], 0) + 16);
  if ( !v9 )
    goto LABEL_9;
  v10 = "sqlite_temp_master";
  v11 = *v9;
  v12 = 14;
  v13 = *(_QWORD *)(v8 + *(_QWORD *)(v2 + 32));
  if ( v6 != 1 )
  {
    v10 = "sqlite_master";
    v12 = 16;
  }
  result = sqlite3AuthCheck((_DWORD)a1, v12, *a2, v11, *(_QWORD *)(v8 + *(_QWORD *)(v2 + 32)));
  if ( !(_DWORD)result )
  {
    result = sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v10, 0, v13);
    if ( !(_DWORD)result )
    {
LABEL_9:
      result = sqlite3GetVdbe(a1);
      v15 = result;
      if ( result )
      {
        sqlite3NestedParse(
          a1,
          "DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='trigger'",
          *(_QWORD *)(*(_QWORD *)(v2 + 32) + 32LL * v6),
          *a2);
        sqlite3ChangeCookie(a1, (unsigned int)v6);
        v16 = *a2;
        v17 = sqlite3VdbeAddOp3(v15, 154, v6, 0, 0);
        return sqlite3VdbeChangeP4(v15, v17, v16, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800730f0  push    rbx
0x1800730f2  push    rbp
0x1800730f3  push    rsi
0x1800730f4  push    rdi
0x1800730f5  push    r12
0x1800730f7  push    r14
0x1800730f9  push    r15
0x1800730fb  sub     rsp, 30h
0x1800730ff  mov     r15, [rcx]
0x180073102  mov     rsi, rcx
0x180073105  mov     rcx, [rdx+28h]
0x180073109  mov     r14, rdx
0x18007310c  mov     edi, 0FFFF8000h
0x180073111  test    rcx, rcx
0x180073114  jz      short loc_180073132
0x180073116  mov     rdx, [r15+20h]
0x18007311a  xor     edi, edi
0x18007311c  cmp     [rdx+18h], rcx
0x180073120  jz      short loc_180073132
0x180073122  inc     edi
0x180073124  movsxd  rax, edi
0x180073127  shl     rax, 5
0x18007312b  cmp     [rax+rdx+18h], rcx
0x180073130  jnz     short loc_180073122
0x180073132  mov     rcx, [r14+30h]
0x180073136  xor     r8d, r8d
0x180073139  mov     rdx, [r14+8]
0x18007313d  add     rcx, 8
0x180073141  call    findElementWithHash
0x180073146  movsxd  rbx, edi
0x180073149  shl     rbx, 5
0x18007314d  mov     r9, [rax+10h]
0x180073151  test    r9, r9
0x180073154  jz      short loc_1800731AF
0x180073156  mov     rax, [r15+20h]
0x18007315a  lea     rbp, aSqliteTempMast; "sqlite_temp_master"
0x180073161  mov     r9, [r9]
0x180073164  mov     edx, 0Eh
0x180073169  mov     r8, [r14]
0x18007316c  cmp     edi, 1
0x18007316f  mov     rcx, rsi
0x180073172  mov     r12, [rbx+rax]
0x180073176  lea     rax, aSqliteMaster; "sqlite_master"
0x18007317d  cmovnz  rbp, rax
0x180073181  mov     [rsp+68h+var_48], r12
0x180073186  lea     eax, [rdx+2]
0x180073189  cmovnz  edx, eax
0x18007318c  call    sqlite3AuthCheck
0x180073191  test    eax, eax
0x180073193  jnz     short loc_180073211
0x180073195  xor     r9d, r9d
0x180073198  mov     [rsp+68h+var_48], r12
0x18007319d  mov     r8, rbp
0x1800731a0  lea     edx, [rax+9]
0x1800731a3  mov     rcx, rsi
0x1800731a6  call    sqlite3AuthCheck
0x1800731ab  test    eax, eax
0x1800731ad  jnz     short loc_180073211
0x1800731af  mov     rcx, rsi
0x1800731b2  call    sqlite3GetVdbe
0x1800731b7  mov     rbp, rax
0x1800731ba  test    rax, rax
0x1800731bd  jz      short loc_180073211
0x1800731bf  mov     r8, [r15+20h]
0x1800731c3  lea     rdx, aDeleteFromQSql_2; "DELETE FROM %Q.sqlite_master WHERE name"...
0x1800731ca  mov     r9, [r14]
0x1800731cd  mov     rcx, rsi
0x1800731d0  mov     r8, [r8+rbx]
0x1800731d4  call    sqlite3NestedParse
0x1800731d9  mov     edx, edi
0x1800731db  mov     rcx, rsi
0x1800731de  call    sqlite3ChangeCookie
0x1800731e3  mov     rbx, [r14]
0x1800731e6  xor     r9d, r9d
0x1800731e9  mov     r8d, edi
0x1800731ec  mov     dword ptr [rsp+68h+var_48], 0
0x1800731f4  mov     edx, 9Ah
0x1800731f9  mov     rcx, rbp
0x1800731fc  call    sqlite3VdbeAddOp3
0x180073201  xor     r9d, r9d
0x180073204  mov     r8, rbx
0x180073207  mov     edx, eax
0x180073209  mov     rcx, rbp
0x18007320c  call    sqlite3VdbeChangeP4
0x180073211  add     rsp, 30h
0x180073215  pop     r15
0x180073217  pop     r14
0x180073219  pop     r12
0x18007321b  pop     rdi
0x18007321c  pop     rsi
0x18007321d  pop     rbp
0x18007321e  pop     rbx
0x18007321f  retn
```
