# sqlite3DropTriggerPtr

- ea: `0x1800835e4`
- end: `0x18008371b`
- name: `sqlite3DropTriggerPtr`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180082718`
- `0x1800834e0`

## callees

- `0x180010810`
- `0x1800119e0`
- `0x180011d80`
- `0x180016250`
- `0x1800398f0`
- `0x18003f6dc`
- `0x1800835e4`
- `0x1800857c4`

## string_xrefs

- `0x180083633`: `sqlite_temp_master`
- `0x1800836a1`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='trigger'`

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
        return sqlite3VdbeAddOp4(v13, 153, v5, 0, 0, *a2, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800835e4  push    rbx
0x1800835e6  push    rbp
0x1800835e7  push    rsi
0x1800835e8  push    rdi
0x1800835e9  push    r12
0x1800835eb  push    r14
0x1800835ed  push    r15
0x1800835ef  sub     rsp, 40h
0x1800835f3  mov     rbx, [rcx]
0x1800835f6  mov     rsi, rcx
0x1800835f9  mov     r14, rdx
0x1800835fc  mov     rcx, rbx
0x1800835ff  mov     rdx, [rdx+28h]
0x180083603  call    sqlite3SchemaToIndex
0x180083608  mov     rcx, [r14+30h]
0x18008360c  xor     r8d, r8d
0x18008360f  mov     rdx, [r14+8]
0x180083613  add     rcx, 8
0x180083617  movsxd  r15, eax
0x18008361a  call    findElementWithHash
0x18008361f  mov     rdi, r15
0x180083622  shl     rdi, 5
0x180083626  mov     r9, [rax+10h]
0x18008362a  test    r9, r9
0x18008362d  jz      short loc_18008368D
0x18008362f  mov     rax, [rbx+20h]
0x180083633  lea     rbp, aSqliteTempMast; "sqlite_temp_master"
0x18008363a  mov     r9, [r9]
0x18008363d  mov     edx, 0Eh
0x180083642  mov     r8, [r14]
0x180083645  cmp     r15d, 1
0x180083649  mov     rcx, rsi
0x18008364c  mov     r12, [rdi+rax]
0x180083650  lea     rax, aSqliteMaster; "sqlite_master"
0x180083657  cmovnz  rbp, rax
0x18008365b  mov     [rsp+78h+var_58], r12
0x180083660  lea     eax, [rdx+2]
0x180083663  cmovnz  edx, eax
0x180083666  call    sqlite3AuthCheck
0x18008366b  test    eax, eax
0x18008366d  jnz     loc_18008370C
0x180083673  xor     r9d, r9d
0x180083676  mov     [rsp+78h+var_58], r12
0x18008367b  mov     r8, rbp
0x18008367e  lea     edx, [rax+9]
0x180083681  mov     rcx, rsi
0x180083684  call    sqlite3AuthCheck
0x180083689  test    eax, eax
0x18008368b  jnz     short loc_18008370C
0x18008368d  mov     rcx, rsi
0x180083690  call    sqlite3GetVdbe
0x180083695  mov     rbp, rax
0x180083698  test    rax, rax
0x18008369b  jz      short loc_18008370C
0x18008369d  mov     r8, [rbx+20h]
0x1800836a1  lea     rdx, aDeleteFromQSql_2; "DELETE FROM %Q.sqlite_master WHERE name"...
0x1800836a8  mov     r9, [r14]
0x1800836ab  mov     rcx, rsi
0x1800836ae  mov     r8, [r8+rdi]
0x1800836b2  call    sqlite3NestedParse
0x1800836b7  mov     rcx, [rsi]
0x1800836ba  mov     r9d, 1
0x1800836c0  mov     r8d, r15d
0x1800836c3  mov     rdx, [rcx+20h]
0x1800836c7  mov     rcx, [rdx+rdi+18h]
0x1800836cc  mov     edx, [rcx]
0x1800836ce  mov     rcx, [rsi+10h]
0x1800836d2  inc     edx
0x1800836d4  mov     dword ptr [rsp+78h+var_58], edx
0x1800836d8  lea     edx, [r9+63h]
0x1800836dc  call    sqlite3VdbeAddOp3
0x1800836e1  mov     rax, [r14]
0x1800836e4  xor     r9d, r9d
0x1800836e7  mov     [rsp+78h+var_48], 0
0x1800836ef  mov     r8d, r15d
0x1800836f2  mov     [rsp+78h+var_50], rax
0x1800836f7  mov     edx, 99h
0x1800836fc  mov     rcx, rbp
0x1800836ff  mov     dword ptr [rsp+78h+var_58], 0
0x180083707  call    sqlite3VdbeAddOp4
0x18008370c  add     rsp, 40h
0x180083710  pop     r15
0x180083712  pop     r14
0x180083714  pop     r12
0x180083716  pop     rdi
0x180083717  pop     rsi
0x180083718  pop     rbp
0x180083719  pop     rbx
0x18008371a  retn
```
