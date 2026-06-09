# sqlite3DropTriggerPtr

- ea: `0x18007ebd8`
- end: `0x18007ed0f`
- name: `sqlite3DropTriggerPtr`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18007b6a8`
- `0x18007eadc`

## callees

- `0x18000b4bc`
- `0x18002b840`
- `0x18003be78`
- `0x18003cc7c`
- `0x18003d480`
- `0x18004002c`
- `0x180042c38`
- `0x18007ebd8`

## string_xrefs

- `0x18007ec27`: `sqlite_temp_master`
- `0x18007ec95`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='trigger'`

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
0x18007ebd8  push    rbx
0x18007ebda  push    rbp
0x18007ebdb  push    rsi
0x18007ebdc  push    rdi
0x18007ebdd  push    r12
0x18007ebdf  push    r14
0x18007ebe1  push    r15
0x18007ebe3  sub     rsp, 40h
0x18007ebe7  mov     rbx, [rcx]
0x18007ebea  mov     rsi, rcx
0x18007ebed  mov     r14, rdx
0x18007ebf0  mov     rcx, rbx
0x18007ebf3  mov     rdx, [rdx+28h]
0x18007ebf7  call    sqlite3SchemaToIndex
0x18007ebfc  mov     rcx, [r14+30h]
0x18007ec00  xor     r8d, r8d
0x18007ec03  mov     rdx, [r14+8]
0x18007ec07  add     rcx, 8
0x18007ec0b  movsxd  r15, eax
0x18007ec0e  call    findElementWithHash
0x18007ec13  mov     rdi, r15
0x18007ec16  shl     rdi, 5
0x18007ec1a  mov     r9, [rax+10h]
0x18007ec1e  test    r9, r9
0x18007ec21  jz      short loc_18007EC81
0x18007ec23  mov     rax, [rbx+20h]
0x18007ec27  lea     rbp, aSqliteTempMast; "sqlite_temp_master"
0x18007ec2e  mov     r9, [r9]
0x18007ec31  mov     edx, 0Eh
0x18007ec36  mov     r8, [r14]
0x18007ec39  cmp     r15d, 1
0x18007ec3d  mov     rcx, rsi
0x18007ec40  mov     r12, [rdi+rax]
0x18007ec44  lea     rax, aSqliteMaster; "sqlite_master"
0x18007ec4b  cmovnz  rbp, rax
0x18007ec4f  mov     [rsp+78h+var_58], r12
0x18007ec54  lea     eax, [rdx+2]
0x18007ec57  cmovnz  edx, eax
0x18007ec5a  call    sqlite3AuthCheck
0x18007ec5f  test    eax, eax
0x18007ec61  jnz     loc_18007ED00
0x18007ec67  xor     r9d, r9d
0x18007ec6a  mov     [rsp+78h+var_58], r12
0x18007ec6f  mov     r8, rbp
0x18007ec72  lea     edx, [rax+9]
0x18007ec75  mov     rcx, rsi
0x18007ec78  call    sqlite3AuthCheck
0x18007ec7d  test    eax, eax
0x18007ec7f  jnz     short loc_18007ED00
0x18007ec81  mov     rcx, rsi
0x18007ec84  call    sqlite3GetVdbe
0x18007ec89  mov     rbp, rax
0x18007ec8c  test    rax, rax
0x18007ec8f  jz      short loc_18007ED00
0x18007ec91  mov     r8, [rbx+20h]
0x18007ec95  lea     rdx, aDeleteFromQSql_2; "DELETE FROM %Q.sqlite_master WHERE name"...
0x18007ec9c  mov     r9, [r14]
0x18007ec9f  mov     rcx, rsi
0x18007eca2  mov     r8, [r8+rdi]
0x18007eca6  call    sqlite3NestedParse
0x18007ecab  mov     rcx, [rsi]
0x18007ecae  mov     r9d, 1
0x18007ecb4  mov     r8d, r15d
0x18007ecb7  mov     rdx, [rcx+20h]
0x18007ecbb  mov     rcx, [rdx+rdi+18h]
0x18007ecc0  mov     edx, [rcx]
0x18007ecc2  mov     rcx, [rsi+10h]
0x18007ecc6  inc     edx
0x18007ecc8  mov     dword ptr [rsp+78h+var_58], edx
0x18007eccc  lea     edx, [r9+63h]
0x18007ecd0  call    sqlite3VdbeAddOp3
0x18007ecd5  mov     rax, [r14]
0x18007ecd8  xor     r9d, r9d
0x18007ecdb  mov     [rsp+78h+var_48], 0
0x18007ece3  mov     r8d, r15d
0x18007ece6  mov     [rsp+78h+var_50], rax
0x18007eceb  mov     edx, 9Ah
0x18007ecf0  mov     rcx, rbp
0x18007ecf3  mov     dword ptr [rsp+78h+var_58], 0
0x18007ecfb  call    sqlite3VdbeAddOp4
0x18007ed00  add     rsp, 40h
0x18007ed04  pop     r15
0x18007ed06  pop     r14
0x18007ed08  pop     r12
0x18007ed0a  pop     rdi
0x18007ed0b  pop     rsi
0x18007ed0c  pop     rbp
0x18007ed0d  pop     rbx
0x18007ed0e  retn
```
