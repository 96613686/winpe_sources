# sqlite3AddGenerated

- ea: `0x18007fd0c`
- end: `0x18007fe44`
- name: `sqlite3AddGenerated`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031b38`

## callees

- `0x18000c960`
- `0x180010950`
- `0x18004b050`
- `0x180060ce8`
- `0x180064c24`
- `0x180079824`
- `0x18007fd0c`

## string_xrefs

- `0x18007fd38`: `virtual tables cannot use computed columns`

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
      sqlite3ExprDeleteNN(*(_QWORD *)a1, (__int64)a2);
    return;
  }
  if ( !a3 )
    goto LABEL_15;
  if ( *((_DWORD *)a3 + 2) == 7 )
  {
    if ( (unsigned int)sqlite3_strnicmp("virtual", *a3) )
      goto LABEL_8;
LABEL_15:
    --*(_WORD *)(v3 + 56);
    v8 = 32;
    v7 = 32;
    goto LABEL_16;
  }
  if ( *((_DWORD *)a3 + 2) != 6 || (unsigned int)sqlite3_strnicmp("stored", *a3) )
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
    if ( (*a2 != 60 || (a2 = (_BYTE *)sqlite3PExpr(a1, 173, a2)) != 0) && *a2 != 72 )
      a2[1] = *(_BYTE *)(v6 - 12);
  }
  sqlite3ColumnSetExpr(a1, v3, v6 - 24, a2);
}

```

## disassembly

```asm
0x18007fd0c  push    rbx
0x18007fd0e  push    rbp
0x18007fd0f  push    rsi
0x18007fd10  push    rdi
0x18007fd11  push    r14
0x18007fd13  sub     rsp, 20h
0x18007fd17  mov     rbp, [rcx+160h]
0x18007fd1e  xor     r14d, r14d
0x18007fd21  mov     r9, r8
0x18007fd24  mov     rbx, rdx
0x18007fd27  mov     rdi, rcx
0x18007fd2a  test    rbp, rbp
0x18007fd2d  jz      short loc_18007FD95
0x18007fd2f  cmp     byte ptr [rcx+134h], 1
0x18007fd36  jnz     short loc_18007FD46
0x18007fd38  lea     rdx, aVirtualTablesC; "virtual tables cannot use computed colu"...
0x18007fd3f  call    sqlite3ErrorMsg
0x18007fd44  jmp     short loc_18007FD95
0x18007fd46  movsx   rax, word ptr [rbp+36h]
0x18007fd4b  lea     rcx, [rax+rax*2]
0x18007fd4f  mov     rax, [rbp+8]
0x18007fd53  lea     rsi, [rax+rcx*8]
0x18007fd57  cmp     [rsi-8], r14w
0x18007fd5c  ja      short loc_18007FD82
0x18007fd5e  test    r9, r9
0x18007fd61  jz      short loc_18007FDD8
0x18007fd63  mov     r8d, 7
0x18007fd69  cmp     [r9+8], r8d
0x18007fd6d  jnz     short loc_18007FDB0
0x18007fd6f  mov     rdx, [r9]
0x18007fd72  lea     rcx, aVirtual; "virtual"
0x18007fd79  call    sqlite3_strnicmp
0x18007fd7e  test    eax, eax
0x18007fd80  jz      short loc_18007FDD8
0x18007fd82  mov     r8, [rsi-18h]
0x18007fd86  lea     rdx, aErrorInGenerat; "error in generated column \"%s\""
0x18007fd8d  mov     rcx, rdi
0x18007fd90  call    sqlite3ErrorMsg
0x18007fd95  test    rbx, rbx
0x18007fd98  jz      short loc_18007FDA5
0x18007fd9a  mov     rcx, [rdi]
0x18007fd9d  mov     rdx, rbx
0x18007fda0  call    sqlite3ExprDeleteNN
0x18007fda5  add     rsp, 20h
0x18007fda9  pop     r14
0x18007fdab  pop     rdi
0x18007fdac  pop     rsi
0x18007fdad  pop     rbp
0x18007fdae  pop     rbx
0x18007fdaf  retn
0x18007fdb0  mov     r8d, 6
0x18007fdb6  cmp     [r9+8], r8d
0x18007fdba  jnz     short loc_18007FD82
0x18007fdbc  mov     rdx, [r9]
0x18007fdbf  lea     rcx, aStored; "stored"
0x18007fdc6  call    sqlite3_strnicmp
0x18007fdcb  test    eax, eax
0x18007fdcd  jnz     short loc_18007FD82
0x18007fdcf  mov     eax, 40h ; '@'
0x18007fdd4  mov     ecx, eax
0x18007fdd6  jmp     short loc_18007FDE4
0x18007fdd8  dec     word ptr [rbp+38h]
0x18007fddc  mov     ecx, 20h ; ' '
0x18007fde1  movzx   eax, cx
0x18007fde4  or      [rsi-6], ax
0x18007fde8  or      [rbp+30h], ecx
0x18007fdeb  test    byte ptr [rsi-6], 1
0x18007fdef  jz      short loc_18007FDFD
0x18007fdf1  lea     rdx, [rsi-18h]
0x18007fdf5  mov     rcx, rdi
0x18007fdf8  call    makeColumnPartOfPrimaryKey
0x18007fdfd  test    rbx, rbx
0x18007fe00  jz      short loc_18007FE2D
0x18007fe02  cmp     byte ptr [rbx], 3Ch ; '<'
0x18007fe05  jnz     short loc_18007FE22
0x18007fe07  xor     r9d, r9d
0x18007fe0a  mov     r8, rbx
0x18007fe0d  mov     edx, 0ADh
0x18007fe12  mov     rcx, rdi
0x18007fe15  call    sqlite3PExpr
0x18007fe1a  mov     rbx, rax
0x18007fe1d  test    rax, rax
0x18007fe20  jz      short loc_18007FE2D
0x18007fe22  cmp     byte ptr [rbx], 48h ; 'H'
0x18007fe25  jz      short loc_18007FE2D
0x18007fe27  mov     al, [rsi-0Ch]
0x18007fe2a  mov     [rbx+1], al
0x18007fe2d  mov     r9, rbx
0x18007fe30  lea     r8, [rsi-18h]
0x18007fe34  mov     rdx, rbp
0x18007fe37  mov     rcx, rdi
0x18007fe3a  call    sqlite3ColumnSetExpr
0x18007fe3f  jmp     loc_18007FDA5
```
