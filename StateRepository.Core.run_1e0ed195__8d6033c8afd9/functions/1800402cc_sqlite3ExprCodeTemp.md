# sqlite3ExprCodeTemp

- ea: `0x1800402cc`
- end: `0x180040366`
- name: `sqlite3ExprCodeTemp`
- size: `154`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x1800355c0`
- `0x18003b070`
- `0x18003e5c0`
- `0x18004022c`
- `0x180058070`
- `0x18005c310`
- `0x18006ec88`

## callees

- `0x18000e4d4`
- `0x1800355c0`
- `0x18003ff00`
- `0x1800402cc`
- `0x18004cfa0`
- `0x18006244c`
- `0x180062894`

## pseudocode

```c
__int64 __fastcall sqlite3ExprCodeTemp(__int64 a1, __int64 a2, _DWORD *a3)
{
  _BYTE *v5; // rax
  _BYTE *v6; // rbx
  unsigned int v7; // r8d
  __int64 TempReg; // rsi
  __int64 v10; // rcx

  v5 = (_BYTE *)sqlite3ExprSkipCollateAndLikely(a2);
  v6 = v5;
  if ( *(_BYTE *)(a1 + 35) && v5 && *v5 != 0xB0 && (unsigned int)exprIsConst(a1, v5, 2) )
  {
    *a3 = 0;
    return (unsigned int)sqlite3ExprCodeRunJustOnce(a1, v6, 0xFFFFFFFFLL);
  }
  else
  {
    TempReg = (unsigned int)sqlite3GetTempReg(a1);
    v7 = sqlite3ExprCodeTarget(v10, v6, TempReg);
    if ( v7 == (_DWORD)TempReg )
    {
      *a3 = TempReg;
    }
    else
    {
      sqlite3ReleaseTempReg(a1, TempReg);
      *a3 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800402cc  push    rbx
0x1800402ce  push    rsi
0x1800402cf  push    rdi
0x1800402d0  push    r14
0x1800402d2  sub     rsp, 28h
0x1800402d6  mov     rdi, rcx
0x1800402d9  mov     r14, r8
0x1800402dc  mov     rcx, rdx
0x1800402df  call    sqlite3ExprSkipCollateAndLikely
0x1800402e4  cmp     byte ptr [rdi+23h], 0
0x1800402e8  mov     rbx, rax
0x1800402eb  jz      short loc_180040332
0x1800402ed  test    rax, rax
0x1800402f0  jz      short loc_180040332
0x1800402f2  cmp     byte ptr [rax], 0B0h
0x1800402f5  jz      short loc_180040332
0x1800402f7  mov     r8d, 2
0x1800402fd  mov     rdx, rax
0x180040300  mov     rcx, rdi
0x180040303  call    exprIsConst
0x180040308  test    eax, eax
0x18004030a  jz      short loc_180040332
0x18004030c  or      r8d, 0FFFFFFFFh
0x180040310  mov     dword ptr [r14], 0
0x180040317  mov     rdx, rbx
0x18004031a  mov     rcx, rdi
0x18004031d  call    sqlite3ExprCodeRunJustOnce
0x180040322  mov     r8d, eax
0x180040325  mov     eax, r8d
0x180040328  add     rsp, 28h
0x18004032c  pop     r14
0x18004032e  pop     rdi
0x18004032f  pop     rsi
0x180040330  pop     rbx
0x180040331  retn
0x180040332  mov     rcx, rdi
0x180040335  call    sqlite3GetTempReg
0x18004033a  mov     r8d, eax
0x18004033d  mov     rdx, rbx
0x180040340  mov     esi, eax
0x180040342  call    sqlite3ExprCodeTarget
0x180040347  mov     r8d, eax
0x18004034a  cmp     eax, esi
0x18004034c  jnz     short loc_180040353
0x18004034e  mov     [r14], esi
0x180040351  jmp     short loc_180040325
0x180040353  mov     edx, esi
0x180040355  mov     rcx, rdi
0x180040358  call    sqlite3ReleaseTempReg
0x18004035d  mov     dword ptr [r14], 0
0x180040364  jmp     short loc_180040325
```
