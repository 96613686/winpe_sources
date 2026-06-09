# sqlite3DropIndex

- ea: `0x1800730c0`
- end: `0x18007335c`
- name: `sqlite3DropIndex`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1800d8b00`

## callees

- `0x180035790`
- `0x180044640`
- `0x1800658d0`
- `0x1800669c0`
- `0x18006b630`
- `0x18006bad0`
- `0x18006d4b0`
- `0x1800730c0`
- `0x1800743d0`
- `0x18007c060`
- `0x18007e7f0`
- `0x180088ea0`
- `0x180093650`
- `0x18009bde0`
- `0x1800a3b40`
- `0x1800c3f40`

## string_xrefs

- `0x1800731a4`: `sqlite_temp_master`
- `0x180073258`: `DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'`

## pseudocode

```c
__int64 __fastcall sqlite3DropIndex(__int64 *a1, __int64 a2, int a3)
{
  __int64 v3; // r15
  __int64 Index; // rax
  _QWORD *v8; // r14
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  const char *v12; // r8
  _QWORD *v13; // r13
  __int64 v14; // r12
  __int64 v15; // rsi
  int v16; // edx
  __int64 v17; // rsi
  __int64 v18; // r8
  __int64 v19; // r14
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v24; // [rsp+20h] [rbp-38h]

  v3 = *a1;
  if ( !*(_BYTE *)(*a1 + 103) && !(unsigned int)sqlite3ReadSchema(a1) )
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
            v17 = a1[2];
            if ( v17 )
              goto LABEL_24;
            if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
              *((_BYTE *)a1 + 35) = 1;
            v17 = sqlite3VdbeCreate(a1);
            if ( v17 )
            {
LABEL_24:
              sqlite3BeginWriteOperation(a1, 1, v10);
              sqlite3NestedParse(
                a1,
                "DELETE FROM %Q.sqlite_master WHERE name=%Q AND type='index'",
                *(_QWORD *)(*(_QWORD *)(v3 + 32) + 32LL * (int)v10),
                *v8);
              sqlite3ClearStatTables(a1, v10, "idx", *v8);
              sqlite3ChangeCookie(a1, v10);
              destroyRootPage(a1, *((unsigned int *)v8 + 22), v10);
              v18 = *(int *)(v17 + 144);
              v19 = *v8;
              if ( *(_DWORD *)(v17 + 148) > (int)v18 )
              {
                *(_DWORD *)(v17 + 144) = v18 + 1;
                v20 = 3 * v18;
                v21 = *(_QWORD *)(v17 + 136);
                *(_DWORD *)(v21 + 8 * v20) = 152;
                *(_DWORD *)(v21 + 8 * v20 + 4) = v10;
                v22 = v21 + 24 * v18;
                *(_QWORD *)(v22 + 8) = 0;
                *(_QWORD *)(v22 + 16) = 0;
              }
              else
              {
                LODWORD(v24) = 0;
                LODWORD(v18) = growOp3(v17, 152, v10, 0, v24);
              }
              if ( !*(_BYTE *)(*(_QWORD *)v17 + 103LL) )
              {
                if ( (int)v18 < 0 )
                  LODWORD(v18) = *(_DWORD *)(v17 + 144) - 1;
                vdbeChangeP4Full(v17, *(_QWORD *)(v17 + 136) + 24LL * (int)v18, v19, 0);
              }
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
0x1800730c0  push    rbx
0x1800730c2  push    rbp
0x1800730c3  push    rdi
0x1800730c4  push    r15
0x1800730c6  sub     rsp, 38h
0x1800730ca  mov     r15, [rcx]
0x1800730cd  mov     ebx, r8d
0x1800730d0  mov     rbp, rdx
0x1800730d3  mov     rdi, rcx
0x1800730d6  cmp     byte ptr [r15+67h], 0
0x1800730db  jnz     loc_180073348
0x1800730e1  call    sqlite3ReadSchema
0x1800730e6  test    eax, eax
0x1800730e8  jnz     loc_180073348
0x1800730ee  mov     r8, [rbp+10h]
0x1800730f2  mov     rcx, r15
0x1800730f5  mov     rdx, [rbp+18h]
0x1800730f9  mov     [rsp+58h+var_28], r14
0x1800730fe  call    sqlite3FindIndex
0x180073103  mov     r14, rax
0x180073106  test    rax, rax
0x180073109  jnz     short loc_180073145
0x18007310b  mov     rcx, rdi
0x18007310e  test    ebx, ebx
0x180073110  jnz     short loc_18007312B
0x180073112  lea     r8, [rbp+8]
0x180073116  lea     rdx, aNoSuchIndexS; "no such index: %S"
0x18007311d  call    sqlite3ErrorMsg
0x180073122  mov     byte ptr [rdi+1Dh], 1
0x180073126  jmp     loc_180073343
0x18007312b  mov     rdx, [rbp+10h]
0x18007312f  call    sqlite3CodeVerifyNamedSchema
0x180073134  mov     rcx, rdi
0x180073137  call    sqlite3ForceNotReadOnly
0x18007313c  mov     byte ptr [rdi+1Dh], 1
0x180073140  jmp     loc_180073343
0x180073145  test    byte ptr [rax+64h], 3
0x180073149  jz      short loc_180073162
0x18007314b  xor     r8d, r8d
0x18007314e  lea     rdx, aIndexAssociate; "index associated with UNIQUE or PRIMARY"...
0x180073155  mov     rcx, rdi
0x180073158  call    sqlite3ErrorMsg
0x18007315d  jmp     loc_180073343
0x180073162  mov     rcx, [rax+30h]
0x180073166  mov     ebx, 0FFFF8000h
0x18007316b  mov     [rsp+58h+arg_0], rsi
0x180073170  mov     [rsp+58h+arg_8], r12
0x180073175  mov     [rsp+58h+arg_10], r13
0x18007317a  test    rcx, rcx
0x18007317d  jz      short loc_1800731A0
0x18007317f  mov     rdx, [r15+20h]
0x180073183  xor     ebx, ebx
0x180073185  cmp     [rdx+18h], rcx
0x180073189  jz      short loc_1800731A0
0x18007318b  nop     dword ptr [rax+rax+00h]
0x180073190  inc     ebx
0x180073192  movsxd  rax, ebx
0x180073195  shl     rax, 5
0x180073199  cmp     [rax+rdx+18h], rcx
0x18007319e  jnz     short loc_180073190
0x1800731a0  mov     rax, [r15+20h]
0x1800731a4  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x1800731ab  mov     r13, [r14+18h]
0x1800731af  mov     edx, 9
0x1800731b4  movsxd  r12, ebx
0x1800731b7  mov     rcx, rdi
0x1800731ba  shl     r12, 5
0x1800731be  cmp     ebx, 1
0x1800731c1  mov     rsi, [r12+rax]
0x1800731c5  lea     rax, aSqliteMaster; "sqlite_master"
0x1800731cc  cmovnz  r8, rax
0x1800731d0  mov     [rsp+58h+var_38], rsi
0x1800731d5  xor     r9d, r9d
0x1800731d8  call    sqlite3AuthCheck
0x1800731dd  test    eax, eax
0x1800731df  jnz     loc_180073334
0x1800731e5  mov     r9, [r13+0]
0x1800731e9  mov     edx, 0Ch
0x1800731ee  mov     r8, [r14]
0x1800731f1  mov     eax, 0Ah
0x1800731f6  cmp     ebx, 1
0x1800731f9  mov     [rsp+58h+var_38], rsi
0x1800731fe  mov     rcx, rdi
0x180073201  cmovnz  edx, eax
0x180073204  call    sqlite3AuthCheck
0x180073209  test    eax, eax
0x18007320b  jnz     loc_180073334
0x180073211  mov     rsi, [rdi+10h]
0x180073215  test    rsi, rsi
0x180073218  jnz     short loc_180073244
0x18007321a  cmp     [rdi+0A8h], rsi
0x180073221  jnz     short loc_180073230
0x180073223  mov     rax, [rdi]
0x180073226  test    byte ptr [rax+60h], 8
0x18007322a  jnz     short loc_180073230
0x18007322c  mov     byte ptr [rdi+23h], 1
0x180073230  mov     rcx, rdi
0x180073233  call    sqlite3VdbeCreate
0x180073238  mov     rsi, rax
0x18007323b  test    rax, rax
0x18007323e  jz      loc_180073334
0x180073244  mov     r8d, ebx
0x180073247  mov     edx, 1
0x18007324c  mov     rcx, rdi
0x18007324f  call    sqlite3BeginWriteOperation
0x180073254  mov     r8, [r15+20h]
0x180073258  lea     rdx, aDeleteFromQSql; "DELETE FROM %Q.sqlite_master WHERE name"...
0x18007325f  mov     r9, [r14]
0x180073262  mov     rcx, rdi
0x180073265  mov     r8, [r8+r12]
0x180073269  call    sqlite3NestedParse
0x18007326e  mov     r9, [r14]
0x180073271  lea     r8, aIdx; "idx"
0x180073278  mov     edx, ebx
0x18007327a  mov     rcx, rdi
0x18007327d  call    sqlite3ClearStatTables
0x180073282  mov     edx, ebx
0x180073284  mov     rcx, rdi
0x180073287  call    sqlite3ChangeCookie
0x18007328c  mov     edx, [r14+58h]
0x180073290  mov     r8d, ebx
0x180073293  mov     rcx, rdi
0x180073296  call    destroyRootPage
0x18007329b  movsxd  r8, dword ptr [rsi+90h]
0x1800732a2  mov     r14, [r14]
0x1800732a5  cmp     [rsi+94h], r8d
0x1800732ac  jg      short loc_1800732CE
0x1800732ae  xor     r9d, r9d
0x1800732b1  mov     dword ptr [rsp+58h+var_38], 0
0x1800732b9  mov     r8d, ebx
0x1800732bc  mov     edx, 98h
0x1800732c1  mov     rcx, rsi
0x1800732c4  call    growOp3
0x1800732c9  mov     r8d, eax
0x1800732cc  jmp     short loc_1800732FC
0x1800732ce  lea     eax, [r8+1]
0x1800732d2  mov     [rsi+90h], eax
0x1800732d8  lea     rcx, [r8+r8*2]
0x1800732dc  mov     rax, [rsi+88h]
0x1800732e3  mov     dword ptr [rax+rcx*8], 98h
0x1800732ea  mov     [rax+rcx*8+4], ebx
0x1800732ee  lea     rdx, [rax+rcx*8]
0x1800732f2  xor     ecx, ecx
0x1800732f4  mov     [rdx+8], rcx
0x1800732f8  mov     [rdx+10h], rcx
0x1800732fc  mov     rax, [rsi]
0x1800732ff  cmp     byte ptr [rax+67h], 0
0x180073303  jnz     short loc_180073334
0x180073305  test    r8d, r8d
0x180073308  jns     short loc_180073314
0x18007330a  mov     r8d, [rsi+90h]
0x180073311  dec     r8d
0x180073314  movsxd  rax, r8d
0x180073317  xor     r9d, r9d
0x18007331a  mov     r8, r14
0x18007331d  mov     rcx, rsi
0x180073320  lea     rdx, [rax+rax*2]
0x180073324  mov     rax, [rsi+88h]
0x18007332b  lea     rdx, [rax+rdx*8]
0x18007332f  call    vdbeChangeP4Full
0x180073334  mov     r13, [rsp+58h+arg_10]
0x180073339  mov     r12, [rsp+58h+arg_8]
0x18007333e  mov     rsi, [rsp+58h+arg_0]
0x180073343  mov     r14, [rsp+58h+var_28]
0x180073348  mov     rdx, rbp
0x18007334b  mov     rcx, r15
0x18007334e  add     rsp, 38h
0x180073352  pop     r15
0x180073354  pop     rdi
0x180073355  pop     rbp
0x180073356  pop     rbx
0x180073357  jmp     sqlite3SrcListDelete
```
