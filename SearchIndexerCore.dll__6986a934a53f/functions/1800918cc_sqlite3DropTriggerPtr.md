# sqlite3DropTriggerPtr

- ea: `0x1800918cc`
- end: `0x180091a03`
- name: `sqlite3DropTriggerPtr`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18004a7fc`
- `0x18007498c`

## callees

- `0x180009760`
- `0x180015700`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001f0f0`
- `0x18001f418`
- `0x18004a9b8`
- `0x1800918cc`

## string_xrefs

- `0x18009191b`: `sqlite_temp_master`
- `0x180091989`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='trigger'`

## pseudocode

```c
__int64 __fastcall sqlite3DropTriggerPtr(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rbx
  __int64 v5; // r15
  __int64 v6; // rdi
  __int64 *v7; // r9
  const char *v8; // rbp
  __int64 v9; // r9
  int v10; // edx
  __int64 v11; // r12
  __int64 result; // rax
  int v13; // ebp

  v2 = *a1;
  v5 = (int)sqlite3SchemaToIndex(*a1, a2[5]);
  v6 = 32 * v5;
  v7 = *(__int64 **)(findElementWithHash(a2[6] + 8, a2[1], 0) + 16);
  if ( !v7 )
    goto LABEL_6;
  v8 = "sqlite_temp_master";
  v9 = *v7;
  v10 = 14;
  v11 = *(_QWORD *)(v6 + *(_QWORD *)(v2 + 32));
  if ( (_DWORD)v5 != 1 )
  {
    v8 = "sqlite_master";
    v10 = 16;
  }
  result = sqlite3AuthCheck((_DWORD)a1, v10, *a2, v9, *(_QWORD *)(v6 + *(_QWORD *)(v2 + 32)));
  if ( !(_DWORD)result )
  {
    result = sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v8, 0, v11);
    if ( !(_DWORD)result )
    {
LABEL_6:
      result = sqlite3GetVdbe(a1);
      v13 = result;
      if ( result )
      {
        sqlite3NestedParse(
          a1,
          "DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='trigger'",
          *(_QWORD *)(*(_QWORD *)(v2 + 32) + 32 * v5),
          *a2);
        sqlite3VdbeAddOp3(a1[2], 100, v5, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32LL) + v6 + 24) + 1);
        return sqlite3VdbeAddOp4(v13, 154, v5, 0, 0, *a2, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800918cc  push    rbx
0x1800918ce  push    rbp
0x1800918cf  push    rsi
0x1800918d0  push    rdi
0x1800918d1  push    r12
0x1800918d3  push    r14
0x1800918d5  push    r15
0x1800918d7  sub     rsp, 40h
0x1800918db  mov     rbx, [rcx]
0x1800918de  mov     rsi, rcx
0x1800918e1  mov     r14, rdx
0x1800918e4  mov     rcx, rbx
0x1800918e7  mov     rdx, [rdx+28h]
0x1800918eb  call    sqlite3SchemaToIndex
0x1800918f0  mov     rcx, [r14+30h]
0x1800918f4  xor     r8d, r8d
0x1800918f7  mov     rdx, [r14+8]
0x1800918fb  add     rcx, 8
0x1800918ff  movsxd  r15, eax
0x180091902  call    findElementWithHash
0x180091907  mov     rdi, r15
0x18009190a  shl     rdi, 5
0x18009190e  mov     r9, [rax+10h]
0x180091912  test    r9, r9
0x180091915  jz      short loc_180091975
0x180091917  mov     rax, [rbx+20h]
0x18009191b  lea     rbp, aSqliteTempMast; "sqlite_temp_master"
0x180091922  mov     r9, [r9]
0x180091925  mov     edx, 0Eh
0x18009192a  mov     r8, [r14]
0x18009192d  cmp     r15d, 1
0x180091931  mov     rcx, rsi
0x180091934  mov     r12, [rdi+rax]
0x180091938  lea     rax, aSqliteMaster; "sqlite_master"
0x18009193f  cmovnz  rbp, rax
0x180091943  mov     [rsp+78h+var_58], r12
0x180091948  lea     eax, [rdx+2]
0x18009194b  cmovnz  edx, eax
0x18009194e  call    sqlite3AuthCheck
0x180091953  test    eax, eax
0x180091955  jnz     loc_1800919F4
0x18009195b  xor     r9d, r9d
0x18009195e  mov     [rsp+78h+var_58], r12
0x180091963  mov     r8, rbp
0x180091966  lea     edx, [rax+9]
0x180091969  mov     rcx, rsi
0x18009196c  call    sqlite3AuthCheck
0x180091971  test    eax, eax
0x180091973  jnz     short loc_1800919F4
0x180091975  mov     rcx, rsi
0x180091978  call    sqlite3GetVdbe
0x18009197d  mov     rbp, rax
0x180091980  test    rax, rax
0x180091983  jz      short loc_1800919F4
0x180091985  mov     r8, [rbx+20h]
0x180091989  lea     rdx, aDeleteFromQSql_2; "DELETE FROM %Q.sqlite_master WHERE name"...
0x180091990  mov     r9, [r14]
0x180091993  mov     rcx, rsi
0x180091996  mov     r8, [r8+rdi]
0x18009199a  call    sqlite3NestedParse
0x18009199f  mov     rcx, [rsi]
0x1800919a2  mov     r9d, 1
0x1800919a8  mov     r8d, r15d
0x1800919ab  mov     rdx, [rcx+20h]
0x1800919af  mov     rcx, [rdx+rdi+18h]
0x1800919b4  mov     edx, [rcx]
0x1800919b6  mov     rcx, [rsi+10h]
0x1800919ba  inc     edx
0x1800919bc  mov     dword ptr [rsp+78h+var_58], edx
0x1800919c0  lea     edx, [r9+63h]
0x1800919c4  call    sqlite3VdbeAddOp3
0x1800919c9  mov     rax, [r14]
0x1800919cc  xor     r9d, r9d
0x1800919cf  mov     [rsp+78h+var_48], 0
0x1800919d7  mov     r8d, r15d
0x1800919da  mov     [rsp+78h+var_50], rax
0x1800919df  mov     edx, 9Ah
0x1800919e4  mov     rcx, rbp
0x1800919e7  mov     dword ptr [rsp+78h+var_58], 0
0x1800919ef  call    sqlite3VdbeAddOp4
0x1800919f4  add     rsp, 40h
0x1800919f8  pop     r15
0x1800919fa  pop     r14
0x1800919fc  pop     r12
0x1800919fe  pop     rdi
0x1800919ff  pop     rsi
0x180091a00  pop     rbp
0x180091a01  pop     rbx
0x180091a02  retn
```
