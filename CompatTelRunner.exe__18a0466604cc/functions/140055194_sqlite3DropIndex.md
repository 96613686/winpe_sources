# sqlite3DropIndex

- ea: `0x140055194`
- end: `0x14005537a`
- name: `sqlite3DropIndex`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1400a40bc`

## callees

- `0x140027e14`
- `0x14004bdbc`
- `0x14004c754`
- `0x140050530`
- `0x1400507bc`
- `0x140051668`
- `0x140055194`
- `0x1400560c4`
- `0x14005ae08`
- `0x14005c598`
- `0x14005f5fc`
- `0x14006348c`
- `0x14006aa04`
- `0x14006f6b0`
- `0x1400738a0`
- `0x140073ca8`

## string_xrefs

- `0x14005525e`: `sqlite_temp_master`
- `0x1400552ee`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'`

## pseudocode

```c
__int64 __fastcall sqlite3DropIndex(_BYTE *a1, __int64 a2, int a3)
{
  __int64 v3; // rbp
  __int64 Index; // rax
  _QWORD *v8; // r14
  __int64 v9; // rcx
  int v10; // edi
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
            while ( *(_QWORD *)(32LL * v10 + v11 + 24) != v9 );
          }
        }
        v12 = "sqlite_temp_master";
        v13 = *(_QWORD **)(Index + 24);
        v14 = 32LL * v10;
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
              sqlite3BeginWriteOperation(a1, 1, (unsigned int)v10);
              sqlite3NestedParse(
                a1,
                "DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'",
                *(_QWORD *)(*(_QWORD *)(v3 + 32) + 32LL * v10),
                *v8);
              sqlite3ClearStatTables(a1, (unsigned int)v10, "idx", *v8);
              sqlite3ChangeCookie(a1, (unsigned int)v10);
              destroyRootPage((__int64)a1, *((_DWORD *)v8 + 22), v10);
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
0x140055194  push    rbx
0x140055196  push    rbp
0x140055197  push    rsi
0x140055198  push    rdi
0x140055199  push    r12
0x14005519b  push    r13
0x14005519d  push    r14
0x14005519f  push    r15
0x1400551a1  sub     rsp, 38h
0x1400551a5  mov     rbp, [rcx]
0x1400551a8  mov     edi, r8d
0x1400551ab  mov     rsi, rdx
0x1400551ae  mov     rbx, rcx
0x1400551b1  cmp     byte ptr [rbp+67h], 0
0x1400551b5  jnz     loc_14005535F
0x1400551bb  call    sqlite3ReadSchema
0x1400551c0  test    eax, eax
0x1400551c2  jnz     loc_14005535F
0x1400551c8  mov     r8, [rsi+10h]
0x1400551cc  mov     rcx, rbp
0x1400551cf  mov     rdx, [rsi+18h]
0x1400551d3  call    sqlite3FindIndex
0x1400551d8  mov     r14, rax
0x1400551db  test    rax, rax
0x1400551de  jnz     short loc_140055213
0x1400551e0  mov     rcx, rbx
0x1400551e3  test    edi, edi
0x1400551e5  jnz     short loc_1400551F9
0x1400551e7  lea     r8, [rsi+8]
0x1400551eb  lea     rdx, aNoSuchIndexS; "no such index: %S"
0x1400551f2  call    sqlite3ErrorMsg
0x1400551f7  jmp     short loc_14005520A
0x1400551f9  mov     rdx, [rsi+10h]
0x1400551fd  call    sqlite3CodeVerifyNamedSchema
0x140055202  mov     rcx, rbx
0x140055205  call    sqlite3ForceNotReadOnly
0x14005520a  mov     byte ptr [rbx+1Dh], 1
0x14005520e  jmp     loc_14005535F
0x140055213  test    byte ptr [rax+64h], 3
0x140055217  jz      short loc_140055230
0x140055219  xor     r8d, r8d
0x14005521c  lea     rdx, aIndexAssociate; "index associated with UNIQUE or PRIMARY"...
0x140055223  mov     rcx, rbx
0x140055226  call    sqlite3ErrorMsg
0x14005522b  jmp     loc_14005535F
0x140055230  mov     rcx, [rax+30h]
0x140055234  mov     edi, 0FFFF8000h
0x140055239  test    rcx, rcx
0x14005523c  jz      short loc_14005525A
0x14005523e  mov     rdx, [rbp+20h]
0x140055242  xor     edi, edi
0x140055244  cmp     [rdx+18h], rcx
0x140055248  jz      short loc_14005525A
0x14005524a  inc     edi
0x14005524c  movsxd  rax, edi
0x14005524f  shl     rax, 5
0x140055253  cmp     [rax+rdx+18h], rcx
0x140055258  jnz     short loc_14005524A
0x14005525a  mov     rax, [rbp+20h]
0x14005525e  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x140055265  mov     r13, [r14+18h]
0x140055269  mov     rcx, rbx
0x14005526c  movsxd  r15, edi
0x14005526f  shl     r15, 5
0x140055273  cmp     edi, 1
0x140055276  mov     r12, [r15+rax]
0x14005527a  lea     rax, aSqliteMaster; "sqlite_master"
0x140055281  cmovnz  r8, rax
0x140055285  mov     [rsp+78h+var_58], r12
0x14005528a  xor     r9d, r9d
0x14005528d  lea     edx, [r9+9]
0x140055291  call    sqlite3AuthCheck
0x140055296  test    eax, eax
0x140055298  jnz     loc_14005535F
0x14005529e  mov     r9, [r13+0]
0x1400552a2  lea     edx, [rax+0Ch]
0x1400552a5  mov     r8, [r14]
0x1400552a8  lea     eax, [rdx-2]
0x1400552ab  cmp     edi, 1
0x1400552ae  mov     [rsp+78h+var_58], r12
0x1400552b3  mov     rcx, rbx
0x1400552b6  cmovnz  edx, eax
0x1400552b9  call    sqlite3AuthCheck
0x1400552be  test    eax, eax
0x1400552c0  jnz     loc_14005535F
0x1400552c6  mov     rcx, rbx
0x1400552c9  call    sqlite3GetVdbe
0x1400552ce  mov     r12, rax
0x1400552d1  test    rax, rax
0x1400552d4  jz      loc_14005535F
0x1400552da  mov     r8d, edi
0x1400552dd  mov     edx, 1
0x1400552e2  mov     rcx, rbx
0x1400552e5  call    sqlite3BeginWriteOperation
0x1400552ea  mov     r8, [rbp+20h]
0x1400552ee  lea     rdx, aDeleteFromQSql; "DELETE FROM %Q.sqlite_master WHERE name"...
0x1400552f5  mov     r9, [r14]
0x1400552f8  mov     rcx, rbx
0x1400552fb  mov     r8, [r8+r15]
0x1400552ff  call    sqlite3NestedParse
0x140055304  mov     r9, [r14]
0x140055307  lea     r8, aIdx; "idx"
0x14005530e  mov     edx, edi
0x140055310  mov     rcx, rbx
0x140055313  call    sqlite3ClearStatTables
0x140055318  mov     edx, edi
0x14005531a  mov     rcx, rbx
0x14005531d  call    sqlite3ChangeCookie
0x140055322  mov     edx, [r14+58h]
0x140055326  mov     r8d, edi
0x140055329  mov     rcx, rbx
0x14005532c  call    destroyRootPage
0x140055331  mov     rbx, [r14]
0x140055334  xor     r9d, r9d
0x140055337  mov     r8d, edi
0x14005533a  mov     dword ptr [rsp+78h+var_58], 0
0x140055342  mov     edx, 98h
0x140055347  mov     rcx, r12
0x14005534a  call    sqlite3VdbeAddOp3
0x14005534f  xor     r9d, r9d
0x140055352  mov     r8, rbx
0x140055355  mov     edx, eax
0x140055357  mov     rcx, r12
0x14005535a  call    sqlite3VdbeChangeP4
0x14005535f  mov     rdx, rsi
0x140055362  mov     rcx, rbp
0x140055365  add     rsp, 38h
0x140055369  pop     r15
0x14005536b  pop     r14
0x14005536d  pop     r13
0x14005536f  pop     r12
0x140055371  pop     rdi
0x140055372  pop     rsi
0x140055373  pop     rbp
0x140055374  pop     rbx
0x140055375  jmp     sqlite3SrcListDelete
```
