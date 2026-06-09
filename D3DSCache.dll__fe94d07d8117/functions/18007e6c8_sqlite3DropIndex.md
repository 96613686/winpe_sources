# sqlite3DropIndex

- ea: `0x18007e6c8`
- end: `0x18007e8b3`
- name: `sqlite3DropIndex`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x18001bc30`

## callees

- `0x18000b4bc`
- `0x180014464`
- `0x1800369e4`
- `0x18003be78`
- `0x18003cc7c`
- `0x18003d480`
- `0x18003f960`
- `0x18004002c`
- `0x180041894`
- `0x180042c38`
- `0x18005cb74`
- `0x18007b4bc`
- `0x18007c1ec`
- `0x18007e6c8`
- `0x1800817c0`
- `0x1800829d8`

## string_xrefs

- `0x18007e775`: `sqlite_temp_master`
- `0x18007e80a`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'`

## pseudocode

```c
__int64 __fastcall sqlite3DropIndex(__int64 *a1, __int64 a2, int a3)
{
  __int64 v3; // rbp
  __int64 Index; // rax
  __int64 *v8; // rsi
  int v9; // eax
  const char *v10; // r8
  _QWORD *v11; // r13
  __int64 v12; // r14
  __int64 v13; // r15
  __int64 v14; // r12
  int v15; // edx
  __int64 Vdbe; // r12

  v3 = *a1;
  if ( !*(_BYTE *)(*a1 + 103) && !(unsigned int)sqlite3ReadSchema(a1) )
  {
    Index = sqlite3FindIndex(v3, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 16));
    v8 = (__int64 *)Index;
    if ( Index )
    {
      if ( (*(_BYTE *)(Index + 100) & 3) != 0 )
      {
        sqlite3ErrorMsg(a1, "index associated with UNIQUE or PRIMARY KEY constraint cannot be dropped", 0);
      }
      else
      {
        v9 = sqlite3SchemaToIndex(v3, *(_QWORD *)(Index + 48));
        v10 = "sqlite_temp_master";
        v11 = (_QWORD *)v8[3];
        v12 = v9;
        v13 = 32LL * v9;
        if ( v9 != 1 )
          v10 = "sqlite_master";
        v14 = *(_QWORD *)(v13 + *(_QWORD *)(v3 + 32));
        if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v10, 0, v14) )
        {
          v15 = 12;
          if ( (_DWORD)v12 != 1 )
            v15 = 10;
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v15, *v8, *v11, v14) )
          {
            Vdbe = sqlite3GetVdbe(a1);
            if ( Vdbe )
            {
              sqlite3BeginWriteOperation(a1, 1, (unsigned int)v12);
              sqlite3NestedParse(
                a1,
                "DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'",
                *(_QWORD *)(*(_QWORD *)(v3 + 32) + 32 * v12),
                *v8);
              sqlite3ClearStatTables(a1, (unsigned int)v12, "idx", *v8);
              sqlite3VdbeAddOp3(a1[2], 100, v12, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32) + v13 + 24) + 1);
              destroyRootPage(a1, *((unsigned int *)v8 + 22), (unsigned int)v12);
              sqlite3VdbeAddOp4(Vdbe, 152, v12, 0, 0, *v8, 0);
            }
          }
        }
      }
    }
    else
    {
      if ( a3 )
      {
        sqlite3CodeVerifyNamedSchema(a1, *(_QWORD *)(a2 + 16));
        sqlite3ForceNotReadOnly(a1);
      }
      else
      {
        sqlite3ErrorMsg(a1, "no such index: %S", (const wchar_t *)(a2 + 8));
      }
      *((_BYTE *)a1 + 29) = 1;
    }
  }
  return sqlite3SrcListDelete(v3, a2);
}

```

## disassembly

```asm
0x18007e6c8  push    rbx
0x18007e6ca  push    rbp
0x18007e6cb  push    rsi
0x18007e6cc  push    rdi
0x18007e6cd  push    r12
0x18007e6cf  push    r13
0x18007e6d1  push    r14
0x18007e6d3  push    r15
0x18007e6d5  sub     rsp, 48h
0x18007e6d9  mov     rbp, [rcx]
0x18007e6dc  mov     r14d, r8d
0x18007e6df  mov     rdi, rdx
0x18007e6e2  mov     rbx, rcx
0x18007e6e5  cmp     byte ptr [rbp+67h], 0
0x18007e6e9  jnz     loc_18007E898
0x18007e6ef  call    sqlite3ReadSchema
0x18007e6f4  test    eax, eax
0x18007e6f6  jnz     loc_18007E898
0x18007e6fc  mov     r8, [rdi+10h]
0x18007e700  mov     rcx, rbp
0x18007e703  mov     rdx, [rdi+18h]
0x18007e707  call    sqlite3FindIndex
0x18007e70c  mov     rsi, rax
0x18007e70f  test    rax, rax
0x18007e712  jnz     short loc_18007E748
0x18007e714  mov     rcx, rbx
0x18007e717  test    r14d, r14d
0x18007e71a  jnz     short loc_18007E72E
0x18007e71c  lea     r8, [rdi+8]
0x18007e720  lea     rdx, aNoSuchIndexS; "no such index: %S"
0x18007e727  call    sqlite3ErrorMsg
0x18007e72c  jmp     short loc_18007E73F
0x18007e72e  mov     rdx, [rdi+10h]
0x18007e732  call    sqlite3CodeVerifyNamedSchema
0x18007e737  mov     rcx, rbx
0x18007e73a  call    sqlite3ForceNotReadOnly
0x18007e73f  mov     byte ptr [rbx+1Dh], 1
0x18007e743  jmp     loc_18007E898
0x18007e748  test    byte ptr [rax+64h], 3
0x18007e74c  jz      short loc_18007E765
0x18007e74e  xor     r8d, r8d
0x18007e751  lea     rdx, aIndexAssociate; "index associated with UNIQUE or PRIMARY"...
0x18007e758  mov     rcx, rbx
0x18007e75b  call    sqlite3ErrorMsg
0x18007e760  jmp     loc_18007E898
0x18007e765  mov     rdx, [rax+30h]
0x18007e769  mov     rcx, rbp
0x18007e76c  call    sqlite3SchemaToIndex
0x18007e771  mov     rcx, [rbp+20h]
0x18007e775  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18007e77c  mov     r13, [rsi+18h]
0x18007e780  movsxd  r14, eax
0x18007e783  lea     rax, aSqliteMaster; "sqlite_master"
0x18007e78a  mov     r15, r14
0x18007e78d  shl     r15, 5
0x18007e791  cmp     r14d, 1
0x18007e795  cmovnz  r8, rax
0x18007e799  xor     r9d, r9d
0x18007e79c  mov     r12, [r15+rcx]
0x18007e7a0  mov     rcx, rbx
0x18007e7a3  mov     [rsp+88h+var_68], r12
0x18007e7a8  lea     edx, [r9+9]
0x18007e7ac  call    sqlite3AuthCheck
0x18007e7b1  test    eax, eax
0x18007e7b3  jnz     loc_18007E898
0x18007e7b9  mov     r9, [r13+0]
0x18007e7bd  lea     edx, [rax+0Ch]
0x18007e7c0  mov     r8, [rsi]
0x18007e7c3  lea     eax, [rdx-2]
0x18007e7c6  cmp     r14d, 1
0x18007e7ca  mov     [rsp+88h+var_68], r12
0x18007e7cf  mov     rcx, rbx
0x18007e7d2  cmovnz  edx, eax
0x18007e7d5  call    sqlite3AuthCheck
0x18007e7da  test    eax, eax
0x18007e7dc  jnz     loc_18007E898
0x18007e7e2  mov     rcx, rbx
0x18007e7e5  call    sqlite3GetVdbe
0x18007e7ea  mov     r12, rax
0x18007e7ed  test    rax, rax
0x18007e7f0  jz      loc_18007E898
0x18007e7f6  mov     r8d, r14d
0x18007e7f9  mov     edx, 1
0x18007e7fe  mov     rcx, rbx
0x18007e801  call    sqlite3BeginWriteOperation
0x18007e806  mov     r8, [rbp+20h]
0x18007e80a  lea     rdx, aDeleteFromQSql; "DELETE FROM %Q.sqlite_master WHERE name"...
0x18007e811  mov     r9, [rsi]
0x18007e814  mov     rcx, rbx
0x18007e817  mov     r8, [r8+r15]
0x18007e81b  call    sqlite3NestedParse
0x18007e820  mov     r9, [rsi]
0x18007e823  lea     r8, aIdx_0; "idx"
0x18007e82a  mov     edx, r14d
0x18007e82d  mov     rcx, rbx
0x18007e830  call    sqlite3ClearStatTables
0x18007e835  mov     rax, [rbx]
0x18007e838  mov     r9d, 1
0x18007e83e  mov     r8d, r14d
0x18007e841  mov     rcx, [rax+20h]
0x18007e845  lea     edx, [r9+63h]
0x18007e849  mov     rax, [rcx+r15+18h]
0x18007e84e  mov     ecx, [rax]
0x18007e850  inc     ecx
0x18007e852  mov     dword ptr [rsp+88h+var_68], ecx
0x18007e856  mov     rcx, [rbx+10h]
0x18007e85a  call    sqlite3VdbeAddOp3
0x18007e85f  mov     edx, [rsi+58h]
0x18007e862  mov     r8d, r14d
0x18007e865  mov     rcx, rbx
0x18007e868  call    destroyRootPage
0x18007e86d  mov     rax, [rsi]
0x18007e870  xor     r9d, r9d
0x18007e873  mov     [rsp+88h+var_58], 0
0x18007e87b  mov     r8d, r14d
0x18007e87e  mov     [rsp+88h+var_60], rax
0x18007e883  mov     edx, 98h
0x18007e888  mov     rcx, r12
0x18007e88b  mov     dword ptr [rsp+88h+var_68], 0
0x18007e893  call    sqlite3VdbeAddOp4
0x18007e898  mov     rdx, rdi
0x18007e89b  mov     rcx, rbp
0x18007e89e  add     rsp, 48h
0x18007e8a2  pop     r15
0x18007e8a4  pop     r14
0x18007e8a6  pop     r13
0x18007e8a8  pop     r12
0x18007e8aa  pop     rdi
0x18007e8ab  pop     rsi
0x18007e8ac  pop     rbp
0x18007e8ad  pop     rbx
0x18007e8ae  jmp     sqlite3SrcListDelete
```
