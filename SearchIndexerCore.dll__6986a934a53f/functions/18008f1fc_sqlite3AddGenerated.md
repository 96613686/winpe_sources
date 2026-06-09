# sqlite3AddGenerated

- ea: `0x18008f1fc`
- end: `0x18008f334`
- name: `sqlite3AddGenerated`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000213c`

## callees

- `0x180011bcc`
- `0x180015540`
- `0x18001bb70`
- `0x18003d760`
- `0x1800583d0`
- `0x18005db04`
- `0x18008f1fc`

## string_xrefs

- `0x18008f228`: `virtual tables cannot use computed columns`

## pseudocode

```c
void __fastcall sqlite3AddGenerated(__int64 a1, _BYTE *a2, _QWORD *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rsi
  __int16 v7; // ax
  int v8; // ecx

  v3 = *(_QWORD *)(a1 + 352);
  if ( !v3 )
    goto LABEL_9;
  if ( *(_BYTE *)(a1 + 308) == 1 )
  {
    sqlite3ErrorMsg(a1, "virtual tables cannot use computed columns", a3, a3);
    goto LABEL_9;
  }
  v6 = *(_QWORD *)(v3 + 8) + 24LL * *(__int16 *)(v3 + 54);
  if ( *(_WORD *)(v6 - 8) )
  {
LABEL_8:
    sqlite3ErrorMsg(a1, "error in generated column \"%s\"", *(const char **)(v6 - 24));
LABEL_9:
    if ( a2 )
      sqlite3ExprDeleteNN(*(_QWORD **)a1, (__int64)a2);
    return;
  }
  if ( !a3 )
    goto LABEL_15;
  if ( *((_DWORD *)a3 + 2) == 7 )
  {
    if ( (unsigned int)sqlite3_strnicmp("virtual", *a3, 7) )
      goto LABEL_8;
LABEL_15:
    --*(_WORD *)(v3 + 56);
    v8 = 32;
    v7 = 32;
    goto LABEL_16;
  }
  if ( *((_DWORD *)a3 + 2) != 6 || (unsigned int)sqlite3_strnicmp("stored", *a3, 6) )
    goto LABEL_8;
  v7 = 64;
  v8 = 64;
LABEL_16:
  *(_WORD *)(v6 - 6) |= v7;
  *(_DWORD *)(v3 + 48) |= v8;
  if ( (*(_BYTE *)(v6 - 6) & 1) != 0 )
    makeColumnPartOfPrimaryKey(a1, v6 - 24);
  if ( a2 )
  {
    if ( (*a2 != 59 || (a2 = (_BYTE *)sqlite3PExpr(a1, 173, a2, 0)) != 0) && *a2 != 71 )
      a2[1] = *(_BYTE *)(v6 - 12);
  }
  sqlite3ColumnSetExpr(a1, v3, v6 - 24, a2);
}

```

## disassembly

```asm
0x18008f1fc  push    rbx
0x18008f1fe  push    rbp
0x18008f1ff  push    rsi
0x18008f200  push    rdi
0x18008f201  push    r14
0x18008f203  sub     rsp, 20h
0x18008f207  mov     rbp, [rcx+160h]
0x18008f20e  xor     r14d, r14d
0x18008f211  mov     r9, r8
0x18008f214  mov     rbx, rdx
0x18008f217  mov     rdi, rcx
0x18008f21a  test    rbp, rbp
0x18008f21d  jz      short loc_18008F285
0x18008f21f  cmp     byte ptr [rcx+134h], 1
0x18008f226  jnz     short loc_18008F236
0x18008f228  lea     rdx, aVirtualTablesC; "virtual tables cannot use computed colu"...
0x18008f22f  call    sqlite3ErrorMsg
0x18008f234  jmp     short loc_18008F285
0x18008f236  movsx   rax, word ptr [rbp+36h]
0x18008f23b  lea     rcx, [rax+rax*2]
0x18008f23f  mov     rax, [rbp+8]
0x18008f243  lea     rsi, [rax+rcx*8]
0x18008f247  cmp     [rsi-8], r14w
0x18008f24c  ja      short loc_18008F272
0x18008f24e  test    r9, r9
0x18008f251  jz      short loc_18008F2C8
0x18008f253  mov     r8d, 7
0x18008f259  cmp     [r9+8], r8d
0x18008f25d  jnz     short loc_18008F2A0
0x18008f25f  mov     rdx, [r9]
0x18008f262  lea     rcx, aVirtual; "virtual"
0x18008f269  call    sqlite3_strnicmp
0x18008f26e  test    eax, eax
0x18008f270  jz      short loc_18008F2C8
0x18008f272  mov     r8, [rsi-18h]
0x18008f276  lea     rdx, aErrorInGenerat; "error in generated column \"%s\""
0x18008f27d  mov     rcx, rdi
0x18008f280  call    sqlite3ErrorMsg
0x18008f285  test    rbx, rbx
0x18008f288  jz      short loc_18008F295
0x18008f28a  mov     rcx, [rdi]
0x18008f28d  mov     rdx, rbx
0x18008f290  call    sqlite3ExprDeleteNN
0x18008f295  add     rsp, 20h
0x18008f299  pop     r14
0x18008f29b  pop     rdi
0x18008f29c  pop     rsi
0x18008f29d  pop     rbp
0x18008f29e  pop     rbx
0x18008f29f  retn
0x18008f2a0  mov     r8d, 6
0x18008f2a6  cmp     [r9+8], r8d
0x18008f2aa  jnz     short loc_18008F272
0x18008f2ac  mov     rdx, [r9]
0x18008f2af  lea     rcx, aStored; "stored"
0x18008f2b6  call    sqlite3_strnicmp
0x18008f2bb  test    eax, eax
0x18008f2bd  jnz     short loc_18008F272
0x18008f2bf  mov     eax, 40h ; '@'
0x18008f2c4  mov     ecx, eax
0x18008f2c6  jmp     short loc_18008F2D4
0x18008f2c8  dec     word ptr [rbp+38h]
0x18008f2cc  mov     ecx, 20h ; ' '
0x18008f2d1  movzx   eax, cx
0x18008f2d4  or      [rsi-6], ax
0x18008f2d8  or      [rbp+30h], ecx
0x18008f2db  test    byte ptr [rsi-6], 1
0x18008f2df  jz      short loc_18008F2ED
0x18008f2e1  lea     rdx, [rsi-18h]
0x18008f2e5  mov     rcx, rdi
0x18008f2e8  call    makeColumnPartOfPrimaryKey
0x18008f2ed  test    rbx, rbx
0x18008f2f0  jz      short loc_18008F31D
0x18008f2f2  cmp     byte ptr [rbx], 3Bh ; ';'
0x18008f2f5  jnz     short loc_18008F312
0x18008f2f7  xor     r9d, r9d
0x18008f2fa  mov     r8, rbx
0x18008f2fd  mov     edx, 0ADh
0x18008f302  mov     rcx, rdi
0x18008f305  call    sqlite3PExpr
0x18008f30a  mov     rbx, rax
0x18008f30d  test    rax, rax
0x18008f310  jz      short loc_18008F31D
0x18008f312  cmp     byte ptr [rbx], 47h ; 'G'
0x18008f315  jz      short loc_18008F31D
0x18008f317  mov     al, [rsi-0Ch]
0x18008f31a  mov     [rbx+1], al
0x18008f31d  mov     r9, rbx
0x18008f320  lea     r8, [rsi-18h]
0x18008f324  mov     rdx, rbp
0x18008f327  mov     rcx, rdi
0x18008f32a  call    sqlite3ColumnSetExpr
0x18008f32f  jmp     loc_18008F295
```
