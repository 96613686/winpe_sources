# destroyRootPage

- ea: `0x18006dca4`
- end: `0x18006dd46`
- name: `destroyRootPage`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180082718`
- `0x1800830cc`

## callees

- `0x180010810`
- `0x1800119e0`
- `0x18003ff00`
- `0x18004cfa0`
- `0x180060ce8`
- `0x18006dca4`
- `0x1800857c4`

## string_xrefs

- `0x18006dcf8`: `UPDATE %Q.sqlite_master SET rootpage=%d WHERE #%d AND rootpage=#%d`

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
0x18006dca4  push    rbx
0x18006dca6  push    rbp
0x18006dca7  push    rsi
0x18006dca8  push    rdi
0x18006dca9  push    r14
0x18006dcab  sub     rsp, 30h
0x18006dcaf  movsxd  rbp, r8d
0x18006dcb2  mov     edi, edx
0x18006dcb4  mov     rbx, rcx
0x18006dcb7  call    sqlite3GetVdbe
0x18006dcbc  mov     rcx, rbx
0x18006dcbf  mov     r14, rax
0x18006dcc2  call    sqlite3GetTempReg
0x18006dcc7  mov     esi, eax
0x18006dcc9  cmp     edi, 2
0x18006dccc  jge     short loc_18006DCDA
0x18006dcce  lea     rdx, aCorruptSchema; "corrupt schema"
0x18006dcd5  call    sqlite3ErrorMsg
0x18006dcda  mov     r9d, esi
0x18006dcdd  mov     dword ptr [rsp+58h+var_38], ebp
0x18006dce1  mov     r8d, edi
0x18006dce4  mov     edx, 90h
0x18006dce9  mov     rcx, r14
0x18006dcec  call    sqlite3VdbeAddOp3
0x18006dcf1  mov     rax, [rbx+0B0h]
0x18006dcf8  lea     rdx, aUpdateQSqliteM_1; "UPDATE %Q.sqlite_master SET rootpage=%d"...
0x18006dcff  test    rax, rax
0x18006dd02  mov     [rsp+58h+var_30], esi
0x18006dd06  mov     rcx, rbx
0x18006dd09  mov     dword ptr [rsp+58h+var_38], esi
0x18006dd0d  cmovnz  rcx, rax
0x18006dd11  mov     r9d, edi
0x18006dd14  mov     byte ptr [rcx+21h], 1
0x18006dd18  mov     rcx, rbp
0x18006dd1b  mov     rax, [rbx]
0x18006dd1e  shl     rcx, 5
0x18006dd22  mov     r8, [rax+20h]
0x18006dd26  mov     r8, [rcx+r8]
0x18006dd2a  mov     rcx, rbx
0x18006dd2d  call    sqlite3NestedParse
0x18006dd32  mov     edx, esi
0x18006dd34  mov     rcx, rbx
0x18006dd37  add     rsp, 30h
0x18006dd3b  pop     r14
0x18006dd3d  pop     rdi
0x18006dd3e  pop     rsi
0x18006dd3f  pop     rbp
0x18006dd40  pop     rbx
0x18006dd41  jmp     sqlite3ReleaseTempReg
```
