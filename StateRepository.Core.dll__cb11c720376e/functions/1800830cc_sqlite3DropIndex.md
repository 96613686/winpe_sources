# sqlite3DropIndex

- ea: `0x1800830cc`
- end: `0x1800832b7`
- name: `sqlite3DropIndex`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x180031b38`

## callees

- `0x18000ca30`
- `0x180010810`
- `0x1800119e0`
- `0x180011d80`
- `0x1800139a4`
- `0x180013a00`
- `0x1800157d4`
- `0x1800398f0`
- `0x18003f6dc`
- `0x180060ce8`
- `0x18006dca4`
- `0x1800825e0`
- `0x180082938`
- `0x1800830cc`
- `0x1800842a4`
- `0x1800857c4`

## string_xrefs

- `0x180083179`: `sqlite_temp_master`
- `0x18008320e`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'`

## pseudocode

```c
__int64 __fastcall sqlite3DropIndex(_QWORD *a1, __int64 a2, int a3)
{
  __int64 v3; // rsi
  __int64 Index; // rax
  __int64 *v8; // rdi
  int v9; // eax
  const char *v10; // r8
  _QWORD *v11; // r13
  __int64 v12; // r14
  __int64 v13; // r15
  __int64 v14; // r12
  int v15; // edx
  __int64 Vdbe; // r12

  v3 = *a1;
  if ( !*(_BYTE *)(*a1 + 103LL) && !(unsigned int)sqlite3ReadSchema(a1) )
  {
    Index = sqlite3FindIndex(v3, *(_QWORD *)(a2 + 8), *(_QWORD *)(a2 + 80));
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
        sqlite3CodeVerifyNamedSchema(a1, *(_QWORD *)(a2 + 80));
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
0x1800830cc  push    rbx
0x1800830ce  push    rbp
0x1800830cf  push    rsi
0x1800830d0  push    rdi
0x1800830d1  push    r12
0x1800830d3  push    r13
0x1800830d5  push    r14
0x1800830d7  push    r15
0x1800830d9  sub     rsp, 48h
0x1800830dd  mov     rsi, [rcx]
0x1800830e0  mov     r15d, r8d
0x1800830e3  mov     rbp, rdx
0x1800830e6  mov     rbx, rcx
0x1800830e9  cmp     byte ptr [rsi+67h], 0
0x1800830ed  jnz     loc_18008329C
0x1800830f3  call    sqlite3ReadSchema
0x1800830f8  test    eax, eax
0x1800830fa  jnz     loc_18008329C
0x180083100  mov     r8, [rbp+50h]
0x180083104  mov     rcx, rsi
0x180083107  mov     rdx, [rbp+8]
0x18008310b  call    sqlite3FindIndex
0x180083110  mov     rdi, rax
0x180083113  test    rax, rax
0x180083116  jnz     short loc_18008314C
0x180083118  mov     rcx, rbx
0x18008311b  test    r15d, r15d
0x18008311e  jnz     short loc_180083132
0x180083120  lea     r8, [rbp+8]
0x180083124  lea     rdx, aNoSuchIndexS; "no such index: %S"
0x18008312b  call    sqlite3ErrorMsg
0x180083130  jmp     short loc_180083143
0x180083132  mov     rdx, [rbp+50h]
0x180083136  call    sqlite3CodeVerifyNamedSchema
0x18008313b  mov     rcx, rbx
0x18008313e  call    sqlite3ForceNotReadOnly
0x180083143  mov     byte ptr [rbx+1Dh], 1
0x180083147  jmp     loc_18008329C
0x18008314c  test    byte ptr [rax+64h], 3
0x180083150  jz      short loc_180083169
0x180083152  xor     r8d, r8d
0x180083155  lea     rdx, aIndexAssociate; "index associated with UNIQUE or PRIMARY"...
0x18008315c  mov     rcx, rbx
0x18008315f  call    sqlite3ErrorMsg
0x180083164  jmp     loc_18008329C
0x180083169  mov     rdx, [rax+30h]
0x18008316d  mov     rcx, rsi
0x180083170  call    sqlite3SchemaToIndex
0x180083175  mov     rcx, [rsi+20h]
0x180083179  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180083180  mov     r13, [rdi+18h]
0x180083184  movsxd  r14, eax
0x180083187  lea     rax, aSqliteMaster; "sqlite_master"
0x18008318e  mov     r15, r14
0x180083191  shl     r15, 5
0x180083195  cmp     r14d, 1
0x180083199  cmovnz  r8, rax
0x18008319d  xor     r9d, r9d
0x1800831a0  mov     r12, [r15+rcx]
0x1800831a4  mov     rcx, rbx
0x1800831a7  mov     [rsp+88h+var_68], r12
0x1800831ac  lea     edx, [r9+9]
0x1800831b0  call    sqlite3AuthCheck
0x1800831b5  test    eax, eax
0x1800831b7  jnz     loc_18008329C
0x1800831bd  mov     r9, [r13+0]
0x1800831c1  lea     edx, [rax+0Ch]
0x1800831c4  mov     r8, [rdi]
0x1800831c7  lea     eax, [rdx-2]
0x1800831ca  cmp     r14d, 1
0x1800831ce  mov     [rsp+88h+var_68], r12
0x1800831d3  mov     rcx, rbx
0x1800831d6  cmovnz  edx, eax
0x1800831d9  call    sqlite3AuthCheck
0x1800831de  test    eax, eax
0x1800831e0  jnz     loc_18008329C
0x1800831e6  mov     rcx, rbx
0x1800831e9  call    sqlite3GetVdbe
0x1800831ee  mov     r12, rax
0x1800831f1  test    rax, rax
0x1800831f4  jz      loc_18008329C
0x1800831fa  mov     r8d, r14d
0x1800831fd  mov     edx, 1
0x180083202  mov     rcx, rbx
0x180083205  call    sqlite3BeginWriteOperation
0x18008320a  mov     r8, [rsi+20h]
0x18008320e  lea     rdx, aDeleteFromQSql; "DELETE FROM %Q.sqlite_master WHERE name"...
0x180083215  mov     r9, [rdi]
0x180083218  mov     rcx, rbx
0x18008321b  mov     r8, [r8+r15]
0x18008321f  call    sqlite3NestedParse
0x180083224  mov     r9, [rdi]
0x180083227  lea     r8, aIdx; "idx"
0x18008322e  mov     edx, r14d
0x180083231  mov     rcx, rbx
0x180083234  call    sqlite3ClearStatTables
0x180083239  mov     rax, [rbx]
0x18008323c  mov     r9d, 1
0x180083242  mov     r8d, r14d
0x180083245  mov     rcx, [rax+20h]
0x180083249  lea     edx, [r9+63h]
0x18008324d  mov     rax, [rcx+r15+18h]
0x180083252  mov     ecx, [rax]
0x180083254  inc     ecx
0x180083256  mov     dword ptr [rsp+88h+var_68], ecx
0x18008325a  mov     rcx, [rbx+10h]
0x18008325e  call    sqlite3VdbeAddOp3
0x180083263  mov     edx, [rdi+58h]
0x180083266  mov     r8d, r14d
0x180083269  mov     rcx, rbx
0x18008326c  call    destroyRootPage
0x180083271  mov     rax, [rdi]
0x180083274  xor     r9d, r9d
0x180083277  mov     [rsp+88h+var_58], 0
0x18008327f  mov     r8d, r14d
0x180083282  mov     [rsp+88h+var_60], rax
0x180083287  mov     edx, 98h
0x18008328c  mov     rcx, r12
0x18008328f  mov     dword ptr [rsp+88h+var_68], 0
0x180083297  call    sqlite3VdbeAddOp4
0x18008329c  mov     rdx, rbp
0x18008329f  mov     rcx, rsi
0x1800832a2  add     rsp, 48h
0x1800832a6  pop     r15
0x1800832a8  pop     r14
0x1800832aa  pop     r13
0x1800832ac  pop     r12
0x1800832ae  pop     rdi
0x1800832af  pop     rsi
0x1800832b0  pop     rbp
0x1800832b1  pop     rbx
0x1800832b2  jmp     sqlite3SrcListDelete
```
