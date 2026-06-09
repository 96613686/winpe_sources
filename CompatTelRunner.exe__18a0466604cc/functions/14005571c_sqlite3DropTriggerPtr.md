# sqlite3DropTriggerPtr

- ea: `0x14005571c`
- end: `0x14005584c`
- name: `sqlite3DropTriggerPtr`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140050a40`
- `0x140055620`

## callees

- `0x14002c1b8`
- `0x14004bdbc`
- `0x140050530`
- `0x14005571c`
- `0x14005f5fc`
- `0x14006348c`
- `0x1400738a0`
- `0x140073ca8`

## string_xrefs

- `0x140055786`: `sqlite_temp_master`
- `0x1400557ef`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='trigger'`

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
0x14005571c  push    rbx
0x14005571e  push    rbp
0x14005571f  push    rsi
0x140055720  push    rdi
0x140055721  push    r12
0x140055723  push    r14
0x140055725  push    r15
0x140055727  sub     rsp, 30h
0x14005572b  mov     r15, [rcx]
0x14005572e  mov     rsi, rcx
0x140055731  mov     rcx, [rdx+28h]
0x140055735  mov     r14, rdx
0x140055738  mov     edi, 0FFFF8000h
0x14005573d  test    rcx, rcx
0x140055740  jz      short loc_14005575E
0x140055742  mov     rdx, [r15+20h]
0x140055746  xor     edi, edi
0x140055748  cmp     [rdx+18h], rcx
0x14005574c  jz      short loc_14005575E
0x14005574e  inc     edi
0x140055750  movsxd  rax, edi
0x140055753  shl     rax, 5
0x140055757  cmp     [rax+rdx+18h], rcx
0x14005575c  jnz     short loc_14005574E
0x14005575e  mov     rcx, [r14+30h]
0x140055762  xor     r8d, r8d
0x140055765  mov     rdx, [r14+8]
0x140055769  add     rcx, 8
0x14005576d  call    findElementWithHash
0x140055772  movsxd  rbx, edi
0x140055775  shl     rbx, 5
0x140055779  mov     r9, [rax+10h]
0x14005577d  test    r9, r9
0x140055780  jz      short loc_1400557DB
0x140055782  mov     rax, [r15+20h]
0x140055786  lea     rbp, aSqliteTempMast; "sqlite_temp_master"
0x14005578d  mov     r9, [r9]
0x140055790  mov     edx, 0Eh
0x140055795  mov     r8, [r14]
0x140055798  cmp     edi, 1
0x14005579b  mov     rcx, rsi
0x14005579e  mov     r12, [rbx+rax]
0x1400557a2  lea     rax, aSqliteMaster; "sqlite_master"
0x1400557a9  cmovnz  rbp, rax
0x1400557ad  mov     [rsp+68h+var_48], r12
0x1400557b2  lea     eax, [rdx+2]
0x1400557b5  cmovnz  edx, eax
0x1400557b8  call    sqlite3AuthCheck
0x1400557bd  test    eax, eax
0x1400557bf  jnz     short loc_14005583D
0x1400557c1  xor     r9d, r9d
0x1400557c4  mov     [rsp+68h+var_48], r12
0x1400557c9  mov     r8, rbp
0x1400557cc  lea     edx, [rax+9]
0x1400557cf  mov     rcx, rsi
0x1400557d2  call    sqlite3AuthCheck
0x1400557d7  test    eax, eax
0x1400557d9  jnz     short loc_14005583D
0x1400557db  mov     rcx, rsi
0x1400557de  call    sqlite3GetVdbe
0x1400557e3  mov     rbp, rax
0x1400557e6  test    rax, rax
0x1400557e9  jz      short loc_14005583D
0x1400557eb  mov     r8, [r15+20h]
0x1400557ef  lea     rdx, aDeleteFromQSql_2; "DELETE FROM %Q.sqlite_master WHERE name"...
0x1400557f6  mov     r9, [r14]
0x1400557f9  mov     rcx, rsi
0x1400557fc  mov     r8, [r8+rbx]
0x140055800  call    sqlite3NestedParse
0x140055805  mov     edx, edi
0x140055807  mov     rcx, rsi
0x14005580a  call    sqlite3ChangeCookie
0x14005580f  mov     rbx, [r14]
0x140055812  xor     r9d, r9d
0x140055815  mov     r8d, edi
0x140055818  mov     dword ptr [rsp+68h+var_48], 0
0x140055820  mov     edx, 9Ah
0x140055825  mov     rcx, rbp
0x140055828  call    sqlite3VdbeAddOp3
0x14005582d  xor     r9d, r9d
0x140055830  mov     r8, rbx
0x140055833  mov     edx, eax
0x140055835  mov     rcx, rbp
0x140055838  call    sqlite3VdbeChangeP4
0x14005583d  add     rsp, 30h
0x140055841  pop     r15
0x140055843  pop     r14
0x140055845  pop     r12
0x140055847  pop     rdi
0x140055848  pop     rsi
0x140055849  pop     rbp
0x14005584a  pop     rbx
0x14005584b  retn
```
