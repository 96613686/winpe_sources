# sqlite3DropIndex

- ea: `0x180074d48`
- end: `0x180074f33`
- name: `sqlite3DropIndex`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x18000213c`

## callees

- `0x18000968c`
- `0x180009e04`
- `0x18000a6bc`
- `0x18000a754`
- `0x180011bcc`
- `0x180015700`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001f0f0`
- `0x18001f418`
- `0x18004a34c`
- `0x18004a9b8`
- `0x18004ad90`
- `0x180060b38`
- `0x180074d48`
- `0x180090ffc`

## string_xrefs

- `0x180074df5`: `sqlite_temp_master`
- `0x180074e8a`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'`

## pseudocode

```c
__int64 __fastcall sqlite3DropIndex(_QWORD *a1, __int64 a2, int a3)
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
  __int64 v16; // r9
  __int64 Vdbe; // r12

  v3 = *a1;
  if ( !*(_BYTE *)(*a1 + 103LL) && !(unsigned int)sqlite3ReadSchema(a1) )
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
              sqlite3BeginWriteOperation(a1, 1, (unsigned int)v12, v16);
              sqlite3NestedParse(
                a1,
                "DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'",
                *(_QWORD *)(*(_QWORD *)(v3 + 32) + 32 * v12),
                *v8);
              sqlite3ClearStatTables(a1, (unsigned int)v12, "idx", *v8);
              sqlite3VdbeAddOp3(a1[2], 100, v12, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32LL) + v13 + 24) + 1);
              destroyRootPage(a1, *((_DWORD *)v8 + 22), v12);
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
0x180074d48  push    rbx
0x180074d4a  push    rbp
0x180074d4b  push    rsi
0x180074d4c  push    rdi
0x180074d4d  push    r12
0x180074d4f  push    r13
0x180074d51  push    r14
0x180074d53  push    r15
0x180074d55  sub     rsp, 48h
0x180074d59  mov     rbp, [rcx]
0x180074d5c  mov     r14d, r8d
0x180074d5f  mov     rdi, rdx
0x180074d62  mov     rbx, rcx
0x180074d65  cmp     byte ptr [rbp+67h], 0
0x180074d69  jnz     loc_180074F18
0x180074d6f  call    sqlite3ReadSchema
0x180074d74  test    eax, eax
0x180074d76  jnz     loc_180074F18
0x180074d7c  mov     r8, [rdi+10h]
0x180074d80  mov     rcx, rbp
0x180074d83  mov     rdx, [rdi+18h]
0x180074d87  call    sqlite3FindIndex
0x180074d8c  mov     rsi, rax
0x180074d8f  test    rax, rax
0x180074d92  jnz     short loc_180074DC8
0x180074d94  mov     rcx, rbx
0x180074d97  test    r14d, r14d
0x180074d9a  jnz     short loc_180074DAE
0x180074d9c  lea     r8, [rdi+8]
0x180074da0  lea     rdx, aNoSuchIndexS; "no such index: %S"
0x180074da7  call    sqlite3ErrorMsg
0x180074dac  jmp     short loc_180074DBF
0x180074dae  mov     rdx, [rdi+10h]
0x180074db2  call    sqlite3CodeVerifyNamedSchema
0x180074db7  mov     rcx, rbx
0x180074dba  call    sqlite3ForceNotReadOnly
0x180074dbf  mov     byte ptr [rbx+1Dh], 1
0x180074dc3  jmp     loc_180074F18
0x180074dc8  test    byte ptr [rax+64h], 3
0x180074dcc  jz      short loc_180074DE5
0x180074dce  xor     r8d, r8d
0x180074dd1  lea     rdx, aIndexAssociate; "index associated with UNIQUE or PRIMARY"...
0x180074dd8  mov     rcx, rbx
0x180074ddb  call    sqlite3ErrorMsg
0x180074de0  jmp     loc_180074F18
0x180074de5  mov     rdx, [rax+30h]
0x180074de9  mov     rcx, rbp
0x180074dec  call    sqlite3SchemaToIndex
0x180074df1  mov     rcx, [rbp+20h]
0x180074df5  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180074dfc  mov     r13, [rsi+18h]
0x180074e00  movsxd  r14, eax
0x180074e03  lea     rax, aSqliteMaster; "sqlite_master"
0x180074e0a  mov     r15, r14
0x180074e0d  shl     r15, 5
0x180074e11  cmp     r14d, 1
0x180074e15  cmovnz  r8, rax
0x180074e19  xor     r9d, r9d
0x180074e1c  mov     r12, [r15+rcx]
0x180074e20  mov     rcx, rbx
0x180074e23  mov     [rsp+88h+var_68], r12
0x180074e28  lea     edx, [r9+9]
0x180074e2c  call    sqlite3AuthCheck
0x180074e31  test    eax, eax
0x180074e33  jnz     loc_180074F18
0x180074e39  mov     r9, [r13+0]
0x180074e3d  lea     edx, [rax+0Ch]
0x180074e40  mov     r8, [rsi]
0x180074e43  lea     eax, [rdx-2]
0x180074e46  cmp     r14d, 1
0x180074e4a  mov     [rsp+88h+var_68], r12
0x180074e4f  mov     rcx, rbx
0x180074e52  cmovnz  edx, eax
0x180074e55  call    sqlite3AuthCheck
0x180074e5a  test    eax, eax
0x180074e5c  jnz     loc_180074F18
0x180074e62  mov     rcx, rbx
0x180074e65  call    sqlite3GetVdbe
0x180074e6a  mov     r12, rax
0x180074e6d  test    rax, rax
0x180074e70  jz      loc_180074F18
0x180074e76  mov     r8d, r14d
0x180074e79  mov     edx, 1
0x180074e7e  mov     rcx, rbx
0x180074e81  call    sqlite3BeginWriteOperation
0x180074e86  mov     r8, [rbp+20h]
0x180074e8a  lea     rdx, aDeleteFromQSql; "DELETE FROM %Q.sqlite_master WHERE name"...
0x180074e91  mov     r9, [rsi]
0x180074e94  mov     rcx, rbx
0x180074e97  mov     r8, [r8+r15]
0x180074e9b  call    sqlite3NestedParse
0x180074ea0  mov     r9, [rsi]
0x180074ea3  lea     r8, aIdx; "idx"
0x180074eaa  mov     edx, r14d
0x180074ead  mov     rcx, rbx
0x180074eb0  call    sqlite3ClearStatTables
0x180074eb5  mov     rax, [rbx]
0x180074eb8  mov     r9d, 1
0x180074ebe  mov     r8d, r14d
0x180074ec1  mov     rcx, [rax+20h]
0x180074ec5  lea     edx, [r9+63h]
0x180074ec9  mov     rax, [rcx+r15+18h]
0x180074ece  mov     ecx, [rax]
0x180074ed0  inc     ecx
0x180074ed2  mov     dword ptr [rsp+88h+var_68], ecx
0x180074ed6  mov     rcx, [rbx+10h]
0x180074eda  call    sqlite3VdbeAddOp3
0x180074edf  mov     edx, [rsi+58h]
0x180074ee2  mov     r8d, r14d
0x180074ee5  mov     rcx, rbx
0x180074ee8  call    destroyRootPage
0x180074eed  mov     rax, [rsi]
0x180074ef0  xor     r9d, r9d
0x180074ef3  mov     [rsp+88h+var_58], 0
0x180074efb  mov     r8d, r14d
0x180074efe  mov     [rsp+88h+var_60], rax
0x180074f03  mov     edx, 98h
0x180074f08  mov     rcx, r12
0x180074f0b  mov     dword ptr [rsp+88h+var_68], 0
0x180074f13  call    sqlite3VdbeAddOp4
0x180074f18  mov     rdx, rdi
0x180074f1b  mov     rcx, rbp
0x180074f1e  add     rsp, 48h
0x180074f22  pop     r15
0x180074f24  pop     r14
0x180074f26  pop     r13
0x180074f28  pop     r12
0x180074f2a  pop     rdi
0x180074f2b  pop     rsi
0x180074f2c  pop     rbp
0x180074f2d  pop     rbx
0x180074f2e  jmp     sqlite3SrcListDelete
```
