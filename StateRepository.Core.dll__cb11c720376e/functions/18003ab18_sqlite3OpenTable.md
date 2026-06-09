# sqlite3OpenTable

- ea: `0x18003ab18`
- end: `0x18003abc6`
- name: `sqlite3OpenTable`
- size: `174`
- prototype: ``
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f134`
- `0x1800158e8`
- `0x18003e944`
- `0x18004036c`
- `0x18004e8ec`
- `0x180050420`
- `0x180069e7c`
- `0x18006f8a4`
- `0x180080120`
- `0x1800866d4`
- `0x180098bfc`

## callees

- `0x18000fa9c`
- `0x1800119e0`
- `0x18003ab18`
- `0x18003abcc`
- `0x180053ecc`
- `0x180067de4`

## pseudocode

```c
__int64 __fastcall sqlite3OpenTable(_QWORD *a1, int a2, unsigned int a3, __int64 a4, int a5)
{
  __int64 v5; // rdi
  __int64 v6; // r12
  __int64 v11; // rbx

  v5 = a4;
  v6 = a1[2];
  if ( !*(_BYTE *)(*a1 + 111LL) )
  {
    LOBYTE(a4) = a5 == 113;
    sqlite3TableLock(a1, a3, *(unsigned int *)(v5 + 40), a4, *(_QWORD *)v5);
  }
  if ( *(char *)(v5 + 48) >= 0 )
    return sqlite3VdbeAddOp4Int(v6, a5, a2, *(_DWORD *)(v5 + 40), a3, *(__int16 *)(v5 + 56));
  v11 = sqlite3PrimaryKeyIndex(v5);
  sqlite3VdbeAddOp3(v6, a5, a2, *(_DWORD *)(v11 + 88), a3);
  return sqlite3VdbeSetP4KeyInfo(a1, v11);
}

```

## disassembly

```asm
0x18003ab18  push    rbx
0x18003ab1a  push    rbp
0x18003ab1b  push    rsi
0x18003ab1c  push    rdi
0x18003ab1d  push    r12
0x18003ab1f  push    r15
0x18003ab21  sub     rsp, 38h
0x18003ab25  mov     rax, [rcx]
0x18003ab28  mov     rdi, r9
0x18003ab2b  mov     r12, [rcx+10h]
0x18003ab2f  mov     ebp, r8d
0x18003ab32  mov     r15d, edx
0x18003ab35  mov     rsi, rcx
0x18003ab38  cmp     byte ptr [rax+6Fh], 0
0x18003ab3c  jz      short loc_18003AB73
0x18003ab3e  test    byte ptr [rdi+30h], 80h
0x18003ab42  jnz     short loc_18003AB94
0x18003ab44  movsx   eax, word ptr [rdi+38h]
0x18003ab48  mov     r8d, r15d
0x18003ab4b  mov     r9d, [rdi+28h]
0x18003ab4f  mov     rcx, r12
0x18003ab52  mov     edx, [rsp+68h+arg_20]
0x18003ab59  mov     [rsp+68h+var_40], eax
0x18003ab5d  mov     dword ptr [rsp+68h+var_48], ebp
0x18003ab61  call    sqlite3VdbeAddOp4Int
0x18003ab66  add     rsp, 38h
0x18003ab6a  pop     r15
0x18003ab6c  pop     r12
0x18003ab6e  pop     rdi
0x18003ab6f  pop     rsi
0x18003ab70  pop     rbp
0x18003ab71  pop     rbx
0x18003ab72  retn
0x18003ab73  cmp     [rsp+68h+arg_20], 71h ; 'q'
0x18003ab7b  mov     edx, ebp
0x18003ab7d  mov     rax, [rdi]
0x18003ab80  mov     r8d, [rdi+28h]
0x18003ab84  setz    r9b
0x18003ab88  mov     [rsp+68h+var_48], rax
0x18003ab8d  call    sqlite3TableLock
0x18003ab92  jmp     short loc_18003AB3E
0x18003ab94  mov     rcx, rdi
0x18003ab97  call    sqlite3PrimaryKeyIndex
0x18003ab9c  mov     edx, [rsp+68h+arg_20]
0x18003aba3  mov     r8d, r15d
0x18003aba6  mov     rcx, r12
0x18003aba9  mov     dword ptr [rsp+68h+var_48], ebp
0x18003abad  mov     rbx, rax
0x18003abb0  mov     r9d, [rax+58h]
0x18003abb4  call    sqlite3VdbeAddOp3
0x18003abb9  mov     rdx, rbx
0x18003abbc  mov     rcx, rsi
0x18003abbf  call    sqlite3VdbeSetP4KeyInfo
0x18003abc4  jmp     short loc_18003AB66
```
