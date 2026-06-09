# sqlite3AddGenerated

- ea: `0x180076818`
- end: `0x18007694d`
- name: `sqlite3AddGenerated`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001bc30`

## callees

- `0x180014464`
- `0x180015e80`
- `0x1800367a0`
- `0x18004221c`
- `0x180076818`
- `0x18007c52c`
- `0x180086d48`

## string_xrefs

- `0x180076844`: `virtual tables cannot use computed columns`

## pseudocode

```c
__int64 __fastcall sqlite3AddGenerated(__int64 a1, _BYTE *a2, _QWORD *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rsi
  __int16 v8; // ax
  int v9; // ecx

  v3 = *(_QWORD *)(a1 + 352);
  if ( !v3 )
    return sqlite3ExprDeleteGeneric(*(_QWORD *)a1, (__int64)a2);
  if ( *(_BYTE *)(a1 + 308) == 1 )
  {
    sqlite3ErrorMsg(a1, "virtual tables cannot use computed columns", a3, a3);
    return sqlite3ExprDeleteGeneric(*(_QWORD *)a1, (__int64)a2);
  }
  v6 = *(_QWORD *)(v3 + 8) + 24LL * *(__int16 *)(v3 + 54);
  if ( *(_WORD *)(v6 - 8) )
  {
LABEL_8:
    sqlite3ErrorMsg(a1, "error in generated column \"%s\"", *(const char **)(v6 - 24));
    return sqlite3ExprDeleteGeneric(*(_QWORD *)a1, (__int64)a2);
  }
  if ( a3 )
  {
    if ( *((_DWORD *)a3 + 2) != 7 )
    {
      if ( *((_DWORD *)a3 + 2) != 6 || (unsigned int)sqlite3_strnicmp("stored", *a3, 6) )
        goto LABEL_8;
      v8 = 64;
      v9 = 64;
      goto LABEL_14;
    }
    if ( (unsigned int)sqlite3_strnicmp("virtual", *a3, 7) )
      goto LABEL_8;
  }
  --*(_WORD *)(v3 + 56);
  v9 = 32;
  v8 = 32;
LABEL_14:
  *(_WORD *)(v6 - 6) |= v8;
  *(_DWORD *)(v3 + 48) |= v9;
  if ( (*(_BYTE *)(v6 - 6) & 1) != 0 )
    makeColumnPartOfPrimaryKey(a1, v6 - 24);
  if ( a2 )
  {
    if ( (*a2 != 59 || (a2 = (_BYTE *)sqlite3PExpr(a1, 173, a2, 0)) != 0) && *a2 != 71 )
      a2[1] = *(_BYTE *)(v6 - 12);
  }
  sqlite3ColumnSetExpr(a1, v3, v6 - 24, a2);
  a2 = 0;
  return sqlite3ExprDeleteGeneric(*(_QWORD *)a1, (__int64)a2);
}

```

## disassembly

```asm
0x180076818  push    rbx
0x18007681a  push    rbp
0x18007681b  push    rsi
0x18007681c  push    rdi
0x18007681d  push    r14
0x18007681f  sub     rsp, 20h
0x180076823  mov     rbp, [rcx+160h]
0x18007682a  xor     r14d, r14d
0x18007682d  mov     r9, r8
0x180076830  mov     rbx, rdx
0x180076833  mov     rdi, rcx
0x180076836  test    rbp, rbp
0x180076839  jz      short loc_1800768A1
0x18007683b  cmp     byte ptr [rcx+134h], 1
0x180076842  jnz     short loc_180076852
0x180076844  lea     rdx, aVirtualTablesC; "virtual tables cannot use computed colu"...
0x18007684b  call    sqlite3ErrorMsg
0x180076850  jmp     short loc_1800768A1
0x180076852  movsx   rax, word ptr [rbp+36h]
0x180076857  lea     rcx, [rax+rax*2]
0x18007685b  mov     rax, [rbp+8]
0x18007685f  lea     rsi, [rax+rcx*8]
0x180076863  cmp     [rsi-8], r14w
0x180076868  ja      short loc_18007688E
0x18007686a  test    r9, r9
0x18007686d  jz      short loc_1800768DE
0x18007686f  mov     r8d, 7
0x180076875  cmp     [r9+8], r8d
0x180076879  jnz     short loc_1800768B6
0x18007687b  mov     rdx, [r9]
0x18007687e  lea     rcx, aVirtual; "virtual"
0x180076885  call    sqlite3_strnicmp
0x18007688a  test    eax, eax
0x18007688c  jz      short loc_1800768DE
0x18007688e  mov     r8, [rsi-18h]
0x180076892  lea     rdx, aErrorInGenerat; "error in generated column \"%s\""
0x180076899  mov     rcx, rdi
0x18007689c  call    sqlite3ErrorMsg
0x1800768a1  mov     rcx, [rdi]
0x1800768a4  mov     rdx, rbx
0x1800768a7  add     rsp, 20h
0x1800768ab  pop     r14
0x1800768ad  pop     rdi
0x1800768ae  pop     rsi
0x1800768af  pop     rbp
0x1800768b0  pop     rbx
0x1800768b1  jmp     sqlite3ExprDeleteGeneric
0x1800768b6  mov     r8d, 6
0x1800768bc  cmp     [r9+8], r8d
0x1800768c0  jnz     short loc_18007688E
0x1800768c2  mov     rdx, [r9]
0x1800768c5  lea     rcx, aStored; "stored"
0x1800768cc  call    sqlite3_strnicmp
0x1800768d1  test    eax, eax
0x1800768d3  jnz     short loc_18007688E
0x1800768d5  mov     eax, 40h ; '@'
0x1800768da  mov     ecx, eax
0x1800768dc  jmp     short loc_1800768EA
0x1800768de  dec     word ptr [rbp+38h]
0x1800768e2  mov     ecx, 20h ; ' '
0x1800768e7  movzx   eax, cx
0x1800768ea  or      [rsi-6], ax
0x1800768ee  or      [rbp+30h], ecx
0x1800768f1  test    byte ptr [rsi-6], 1
0x1800768f5  jz      short loc_180076903
0x1800768f7  lea     rdx, [rsi-18h]
0x1800768fb  mov     rcx, rdi
0x1800768fe  call    makeColumnPartOfPrimaryKey
0x180076903  test    rbx, rbx
0x180076906  jz      short loc_180076933
0x180076908  cmp     byte ptr [rbx], 3Bh ; ';'
0x18007690b  jnz     short loc_180076928
0x18007690d  xor     r9d, r9d
0x180076910  mov     r8, rbx
0x180076913  mov     edx, 0ADh
0x180076918  mov     rcx, rdi
0x18007691b  call    sqlite3PExpr
0x180076920  mov     rbx, rax
0x180076923  test    rax, rax
0x180076926  jz      short loc_180076933
0x180076928  cmp     byte ptr [rbx], 47h ; 'G'
0x18007692b  jz      short loc_180076933
0x18007692d  mov     al, [rsi-0Ch]
0x180076930  mov     [rbx+1], al
0x180076933  mov     r9, rbx
0x180076936  lea     r8, [rsi-18h]
0x18007693a  mov     rdx, rbp
0x18007693d  mov     rcx, rdi
0x180076940  call    sqlite3ColumnSetExpr
0x180076945  mov     rbx, r14
0x180076948  jmp     loc_1800768A1
```
