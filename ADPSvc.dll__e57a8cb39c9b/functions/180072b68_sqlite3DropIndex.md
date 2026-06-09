# sqlite3DropIndex

- ea: `0x180072b68`
- end: `0x180072d4e`
- name: `sqlite3DropIndex`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1800c3bd8`

## callees

- `0x1800427c4`
- `0x1800693b0`
- `0x180069d64`
- `0x18006db58`
- `0x18006dde4`
- `0x18006ecc8`
- `0x180072b68`
- `0x180073aec`
- `0x180078bec`
- `0x18007a3e4`
- `0x18007d478`
- `0x1800817f4`
- `0x1800892e4`
- `0x18008e124`
- `0x1800923d8`
- `0x1800927e0`

## string_xrefs

- `0x180072c32`: `sqlite_temp_master`
- `0x180072cc2`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'`

## pseudocode

```c
__int64 __fastcall sqlite3DropIndex(_BYTE *a1, __int64 a2, int a3)
{
  __int64 v3; // rbp
  __int64 Index; // rax
  _QWORD *v8; // r14
  __int64 v9; // rcx
  unsigned int v10; // edi
  __int64 v11; // rdx
  const char *v12; // r8
  _QWORD *v13; // r13
  __int64 v14; // r15
  __int64 v15; // r12
  int v16; // edx
  __int64 Vdbe; // r12
  __int64 v18; // rbx
  unsigned int v19; // eax

  v3 = *(_QWORD *)a1;
  if ( !*(_BYTE *)(*(_QWORD *)a1 + 103LL) && !(unsigned int)sqlite3ReadSchema(a1) )
  {
    Index = sqlite3FindIndex(v3, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 16));
    v8 = (_QWORD *)Index;
    if ( Index )
    {
      if ( (*(_BYTE *)(Index + 100) & 3) != 0 )
      {
        sqlite3ErrorMsg(a1, "index associated with UNIQUE or PRIMARY KEY constraint cannot be dropped", 0);
      }
      else
      {
        v9 = *(_QWORD *)(Index + 48);
        v10 = -32768;
        if ( v9 )
        {
          v11 = *(_QWORD *)(v3 + 32);
          v10 = 0;
          if ( *(_QWORD *)(v11 + 24) != v9 )
          {
            do
              ++v10;
            while ( *(_QWORD *)(32LL * (int)v10 + v11 + 24) != v9 );
          }
        }
        v12 = "sqlite_temp_master";
        v13 = *(_QWORD **)(Index + 24);
        v14 = 32LL * (int)v10;
        v15 = *(_QWORD *)(v14 + *(_QWORD *)(v3 + 32));
        if ( v10 != 1 )
          v12 = "sqlite_master";
        if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v12, 0, *(_QWORD *)(v14 + *(_QWORD *)(v3 + 32))) )
        {
          v16 = 12;
          if ( v10 != 1 )
            v16 = 10;
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v16, *v8, *v13, v15) )
          {
            Vdbe = sqlite3GetVdbe(a1);
            if ( Vdbe )
            {
              sqlite3BeginWriteOperation(a1, 1, v10);
              sqlite3NestedParse(
                a1,
                "DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'",
                *(_QWORD *)(*(_QWORD *)(v3 + 32) + 32LL * (int)v10),
                *v8);
              sqlite3ClearStatTables(a1, v10, "idx", *v8);
              sqlite3ChangeCookie(a1, v10);
              destroyRootPage(a1, *((unsigned int *)v8 + 22), v10);
              v18 = *v8;
              v19 = sqlite3VdbeAddOp3(Vdbe, 152, v10, 0, 0);
              sqlite3VdbeChangeP4(Vdbe, v19, v18, 0);
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
      a1[29] = 1;
    }
  }
  return sqlite3SrcListDelete(v3, a2);
}

```

## disassembly

```asm
0x180072b68  push    rbx
0x180072b6a  push    rbp
0x180072b6b  push    rsi
0x180072b6c  push    rdi
0x180072b6d  push    r12
0x180072b6f  push    r13
0x180072b71  push    r14
0x180072b73  push    r15
0x180072b75  sub     rsp, 38h
0x180072b79  mov     rbp, [rcx]
0x180072b7c  mov     edi, r8d
0x180072b7f  mov     rsi, rdx
0x180072b82  mov     rbx, rcx
0x180072b85  cmp     byte ptr [rbp+67h], 0
0x180072b89  jnz     loc_180072D33
0x180072b8f  call    sqlite3ReadSchema
0x180072b94  test    eax, eax
0x180072b96  jnz     loc_180072D33
0x180072b9c  mov     r8, [rsi+10h]
0x180072ba0  mov     rcx, rbp
0x180072ba3  mov     rdx, [rsi+18h]
0x180072ba7  call    sqlite3FindIndex
0x180072bac  mov     r14, rax
0x180072baf  test    rax, rax
0x180072bb2  jnz     short loc_180072BE7
0x180072bb4  mov     rcx, rbx
0x180072bb7  test    edi, edi
0x180072bb9  jnz     short loc_180072BCD
0x180072bbb  lea     r8, [rsi+8]
0x180072bbf  lea     rdx, aNoSuchIndexS; "no such index: %S"
0x180072bc6  call    sqlite3ErrorMsg
0x180072bcb  jmp     short loc_180072BDE
0x180072bcd  mov     rdx, [rsi+10h]
0x180072bd1  call    sqlite3CodeVerifyNamedSchema
0x180072bd6  mov     rcx, rbx
0x180072bd9  call    sqlite3ForceNotReadOnly
0x180072bde  mov     byte ptr [rbx+1Dh], 1
0x180072be2  jmp     loc_180072D33
0x180072be7  test    byte ptr [rax+64h], 3
0x180072beb  jz      short loc_180072C04
0x180072bed  xor     r8d, r8d
0x180072bf0  lea     rdx, aIndexAssociate; "index associated with UNIQUE or PRIMARY"...
0x180072bf7  mov     rcx, rbx
0x180072bfa  call    sqlite3ErrorMsg
0x180072bff  jmp     loc_180072D33
0x180072c04  mov     rcx, [rax+30h]
0x180072c08  mov     edi, 0FFFF8000h
0x180072c0d  test    rcx, rcx
0x180072c10  jz      short loc_180072C2E
0x180072c12  mov     rdx, [rbp+20h]
0x180072c16  xor     edi, edi
0x180072c18  cmp     [rdx+18h], rcx
0x180072c1c  jz      short loc_180072C2E
0x180072c1e  inc     edi
0x180072c20  movsxd  rax, edi
0x180072c23  shl     rax, 5
0x180072c27  cmp     [rax+rdx+18h], rcx
0x180072c2c  jnz     short loc_180072C1E
0x180072c2e  mov     rax, [rbp+20h]
0x180072c32  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180072c39  mov     r13, [r14+18h]
0x180072c3d  mov     rcx, rbx
0x180072c40  movsxd  r15, edi
0x180072c43  shl     r15, 5
0x180072c47  cmp     edi, 1
0x180072c4a  mov     r12, [r15+rax]
0x180072c4e  lea     rax, aSqliteMaster; "sqlite_master"
0x180072c55  cmovnz  r8, rax
0x180072c59  mov     [rsp+78h+var_58], r12
0x180072c5e  xor     r9d, r9d
0x180072c61  lea     edx, [r9+9]
0x180072c65  call    sqlite3AuthCheck
0x180072c6a  test    eax, eax
0x180072c6c  jnz     loc_180072D33
0x180072c72  mov     r9, [r13+0]
0x180072c76  lea     edx, [rax+0Ch]
0x180072c79  mov     r8, [r14]
0x180072c7c  lea     eax, [rdx-2]
0x180072c7f  cmp     edi, 1
0x180072c82  mov     [rsp+78h+var_58], r12
0x180072c87  mov     rcx, rbx
0x180072c8a  cmovnz  edx, eax
0x180072c8d  call    sqlite3AuthCheck
0x180072c92  test    eax, eax
0x180072c94  jnz     loc_180072D33
0x180072c9a  mov     rcx, rbx
0x180072c9d  call    sqlite3GetVdbe
0x180072ca2  mov     r12, rax
0x180072ca5  test    rax, rax
0x180072ca8  jz      loc_180072D33
0x180072cae  mov     r8d, edi
0x180072cb1  mov     edx, 1
0x180072cb6  mov     rcx, rbx
0x180072cb9  call    sqlite3BeginWriteOperation
0x180072cbe  mov     r8, [rbp+20h]
0x180072cc2  lea     rdx, aDeleteFromQSql; "DELETE FROM %Q.sqlite_master WHERE name"...
0x180072cc9  mov     r9, [r14]
0x180072ccc  mov     rcx, rbx
0x180072ccf  mov     r8, [r8+r15]
0x180072cd3  call    sqlite3NestedParse
0x180072cd8  mov     r9, [r14]
0x180072cdb  lea     r8, aIdx; "idx"
0x180072ce2  mov     edx, edi
0x180072ce4  mov     rcx, rbx
0x180072ce7  call    sqlite3ClearStatTables
0x180072cec  mov     edx, edi
0x180072cee  mov     rcx, rbx
0x180072cf1  call    sqlite3ChangeCookie
0x180072cf6  mov     edx, [r14+58h]
0x180072cfa  mov     r8d, edi
0x180072cfd  mov     rcx, rbx
0x180072d00  call    destroyRootPage
0x180072d05  mov     rbx, [r14]
0x180072d08  xor     r9d, r9d
0x180072d0b  mov     r8d, edi
0x180072d0e  mov     dword ptr [rsp+78h+var_58], 0
0x180072d16  mov     edx, 98h
0x180072d1b  mov     rcx, r12
0x180072d1e  call    sqlite3VdbeAddOp3
0x180072d23  xor     r9d, r9d
0x180072d26  mov     r8, rbx
0x180072d29  mov     edx, eax
0x180072d2b  mov     rcx, r12
0x180072d2e  call    sqlite3VdbeChangeP4
0x180072d33  mov     rdx, rsi
0x180072d36  mov     rcx, rbp
0x180072d39  add     rsp, 38h
0x180072d3d  pop     r15
0x180072d3f  pop     r14
0x180072d41  pop     r13
0x180072d43  pop     r12
0x180072d45  pop     rdi
0x180072d46  pop     rsi
0x180072d47  pop     rbp
0x180072d48  pop     rbx
0x180072d49  jmp     sqlite3SrcListDelete
```
