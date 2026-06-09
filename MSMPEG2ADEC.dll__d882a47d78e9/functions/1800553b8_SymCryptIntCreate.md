# SymCryptIntCreate

- ea: `0x1800553b8`
- end: `0x1800553ee`
- name: `SymCryptIntCreate`
- size: `54`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18005158c`
- `0x1800519f4`
- `0x180051c08`
- `0x180053918`
- `0x180053e58`
- `0x180054008`
- `0x1800561d0`
- `0x18005668c`
- `0x1800567d4`
- `0x180056dc0`
- `0x180057e90`

## callees

- `0x1800553b8`

## pseudocode

```c
_DWORD *__fastcall SymCryptIntCreate(_DWORD *a1, unsigned __int64 a2, int a3)
{
  _DWORD *v3; // r9

  v3 = 0;
  if ( (unsigned int)(a3 - 1) <= 0x7FF && a2 >= (unsigned int)((a3 << 6) + 32) )
  {
    v3 = a1;
    *a1 = 1732837376;
    a1[1] = a3;
    a1[2] = (a3 << 6) + 32;
  }
  return v3;
}

```

## disassembly

```asm
0x1800553b8  xor     r9d, r9d
0x1800553bb  lea     eax, [r8-1]
0x1800553bf  cmp     eax, 7FFh
0x1800553c4  ja      short loc_1800553EA
0x1800553c6  mov     r10d, r8d
0x1800553c9  shl     r10d, 6
0x1800553cd  add     r10d, 20h ; ' '
0x1800553d1  mov     eax, r10d
0x1800553d4  cmp     rdx, rax
0x1800553d7  jb      short loc_1800553EA
0x1800553d9  mov     r9, rcx
0x1800553dc  mov     dword ptr [rcx], 67490000h
0x1800553e2  mov     [rcx+4], r8d
0x1800553e6  mov     [rcx+8], r10d
0x1800553ea  mov     rax, r9
0x1800553ed  retn
```
