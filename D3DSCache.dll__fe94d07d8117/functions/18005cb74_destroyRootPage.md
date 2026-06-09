# destroyRootPage

- ea: `0x18005cb74`
- end: `0x18005cc16`
- name: `destroyRootPage`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18007b6a8`
- `0x18007e6c8`

## callees

- `0x18000b4bc`
- `0x180014464`
- `0x18003cc7c`
- `0x18003d480`
- `0x18005cb74`
- `0x180083968`
- `0x18008982c`

## string_xrefs

- `0x18005cbc8`: `UPDATE %Q.sqlite_master SET rootpage=%d WHERE #%d AND rootpage=#%d`

## pseudocode

```c
__int64 __fastcall destroyRootPage(_QWORD *a1, int a2, int a3)
{
  __int64 v3; // rbp
  int Vdbe; // r14d
  __int64 v7; // rcx
  int TempReg; // esi
  _QWORD *v9; // rcx
  __int64 v11; // [rsp+20h] [rbp-38h]

  v3 = a3;
  Vdbe = sqlite3GetVdbe(a1);
  TempReg = sqlite3GetTempReg((__int64)a1);
  if ( a2 < 2 )
    sqlite3ErrorMsg(v7, "corrupt schema");
  sqlite3VdbeAddOp3(Vdbe, 144, a2, TempReg, v3);
  v9 = a1;
  LODWORD(v11) = TempReg;
  if ( a1[22] )
    v9 = (_QWORD *)a1[22];
  *((_BYTE *)v9 + 33) = 1;
  sqlite3NestedParse(
    a1,
    "UPDATE %Q.sqlite_master SET rootpage=%d WHERE #%d AND rootpage=#%d",
    *(_QWORD *)(32 * v3 + *(_QWORD *)(*a1 + 32LL)),
    (unsigned int)a2,
    v11,
    TempReg);
  return sqlite3ReleaseTempReg((__int64)a1, TempReg);
}

```

## disassembly

```asm
0x18005cb74  push    rbx
0x18005cb76  push    rbp
0x18005cb77  push    rsi
0x18005cb78  push    rdi
0x18005cb79  push    r14
0x18005cb7b  sub     rsp, 30h
0x18005cb7f  movsxd  rbp, r8d
0x18005cb82  mov     edi, edx
0x18005cb84  mov     rbx, rcx
0x18005cb87  call    sqlite3GetVdbe
0x18005cb8c  mov     rcx, rbx
0x18005cb8f  mov     r14, rax
0x18005cb92  call    sqlite3GetTempReg
0x18005cb97  mov     esi, eax
0x18005cb99  cmp     edi, 2
0x18005cb9c  jge     short loc_18005CBAA
0x18005cb9e  lea     rdx, aCorruptSchema; "corrupt schema"
0x18005cba5  call    sqlite3ErrorMsg
0x18005cbaa  mov     r9d, esi
0x18005cbad  mov     dword ptr [rsp+58h+var_38], ebp
0x18005cbb1  mov     r8d, edi
0x18005cbb4  mov     edx, 90h
0x18005cbb9  mov     rcx, r14
0x18005cbbc  call    sqlite3VdbeAddOp3
0x18005cbc1  mov     rax, [rbx+0B0h]
0x18005cbc8  lea     rdx, aUpdateQSqliteM_1; "UPDATE %Q.sqlite_master SET rootpage=%d"...
0x18005cbcf  test    rax, rax
0x18005cbd2  mov     [rsp+58h+var_30], esi
0x18005cbd6  mov     rcx, rbx
0x18005cbd9  mov     dword ptr [rsp+58h+var_38], esi
0x18005cbdd  cmovnz  rcx, rax
0x18005cbe1  mov     r9d, edi
0x18005cbe4  mov     byte ptr [rcx+21h], 1
0x18005cbe8  mov     rcx, rbp
0x18005cbeb  mov     rax, [rbx]
0x18005cbee  shl     rcx, 5
0x18005cbf2  mov     r8, [rax+20h]
0x18005cbf6  mov     r8, [rcx+r8]
0x18005cbfa  mov     rcx, rbx
0x18005cbfd  call    sqlite3NestedParse
0x18005cc02  mov     edx, esi
0x18005cc04  mov     rcx, rbx
0x18005cc07  add     rsp, 30h
0x18005cc0b  pop     r14
0x18005cc0d  pop     rdi
0x18005cc0e  pop     rsi
0x18005cc0f  pop     rbp
0x18005cc10  pop     rbx
0x18005cc11  jmp     sqlite3ReleaseTempReg
```
