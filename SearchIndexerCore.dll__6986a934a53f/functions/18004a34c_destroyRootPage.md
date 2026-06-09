# destroyRootPage

- ea: `0x18004a34c`
- end: `0x18004a3f0`
- name: `destroyRootPage`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD *, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18004a2d0`
- `0x180074d48`

## callees

- `0x180011bcc`
- `0x180015eb0`
- `0x1800168c0`
- `0x18004a34c`
- `0x18004a418`
- `0x18004a478`
- `0x18004a9b8`

## string_xrefs

- `0x18004a394`: `UPDATE %Q.sqlite_master SET rootpage=%d WHERE #%d AND rootpage=#%d`

## pseudocode

```c
__int64 __fastcall destroyRootPage(_QWORD *a1, int a2, int a3)
{
  __int64 v3; // rbp
  int Vdbe; // r14d
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int TempReg; // esi
  _QWORD *v10; // rcx

  v3 = a3;
  Vdbe = sqlite3GetVdbe();
  TempReg = sqlite3GetTempReg(a1, v7);
  if ( a2 < 2 )
    sqlite3ErrorMsg(v8, "corrupt schema");
  sqlite3VdbeAddOp3(Vdbe, 144, a2, TempReg, v3);
  v10 = a1;
  if ( a1[22] )
    v10 = (_QWORD *)a1[22];
  *((_BYTE *)v10 + 33) = 1;
  sqlite3NestedParse(
    a1,
    "UPDATE %Q.sqlite_master SET rootpage=%d WHERE #%d AND rootpage=#%d",
    *(_QWORD *)(32 * v3 + *(_QWORD *)(*a1 + 32LL)),
    (unsigned int)a2,
    TempReg,
    TempReg);
  return sqlite3ReleaseTempReg(a1, TempReg);
}

```

## disassembly

```asm
0x18004a34c  push    rbx
0x18004a34e  push    rbp
0x18004a34f  push    rsi
0x18004a350  push    rdi
0x18004a351  push    r14
0x18004a353  sub     rsp, 30h
0x18004a357  movsxd  rbp, r8d
0x18004a35a  mov     edi, edx
0x18004a35c  mov     rbx, rcx
0x18004a35f  call    sqlite3GetVdbe
0x18004a364  mov     rcx, rbx
0x18004a367  mov     r14, rax
0x18004a36a  call    sqlite3GetTempReg
0x18004a36f  mov     esi, eax
0x18004a371  cmp     edi, 2
0x18004a374  jl      short loc_18004A3E2
0x18004a376  mov     r9d, esi
0x18004a379  mov     [rsp+58h+var_38], ebp
0x18004a37d  mov     r8d, edi
0x18004a380  mov     edx, 90h
0x18004a385  mov     rcx, r14
0x18004a388  call    sqlite3VdbeAddOp3
0x18004a38d  mov     rax, [rbx+0B0h]
0x18004a394  lea     rdx, aUpdateQSqliteM_1; "UPDATE %Q.sqlite_master SET rootpage=%d"...
0x18004a39b  test    rax, rax
0x18004a39e  mov     [rsp+58h+var_30], esi
0x18004a3a2  mov     rcx, rbx
0x18004a3a5  mov     [rsp+58h+var_38], esi
0x18004a3a9  cmovnz  rcx, rax
0x18004a3ad  mov     r9d, edi
0x18004a3b0  mov     byte ptr [rcx+21h], 1
0x18004a3b4  mov     rcx, rbp
0x18004a3b7  mov     rax, [rbx]
0x18004a3ba  shl     rcx, 5
0x18004a3be  mov     r8, [rax+20h]
0x18004a3c2  mov     r8, [rcx+r8]
0x18004a3c6  mov     rcx, rbx
0x18004a3c9  call    sqlite3NestedParse
0x18004a3ce  mov     edx, esi
0x18004a3d0  mov     rcx, rbx
0x18004a3d3  add     rsp, 30h
0x18004a3d7  pop     r14
0x18004a3d9  pop     rdi
0x18004a3da  pop     rsi
0x18004a3db  pop     rbp
0x18004a3dc  pop     rbx
0x18004a3dd  jmp     sqlite3ReleaseTempReg
0x18004a3e2  lea     rdx, aCorruptSchema; "corrupt schema"
0x18004a3e9  call    sqlite3ErrorMsg
0x18004a3ee  jmp     short loc_18004A376
```
