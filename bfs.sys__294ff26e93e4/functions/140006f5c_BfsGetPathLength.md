# BfsGetPathLength

- ea: `0x140006f5c`
- end: `0x140006f9b`
- name: `BfsGetPathLength`
- size: `63`
- prototype: `__int16 __fastcall(__int64 **, _WORD *, _WORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400055b4`
- `0x140006330`

## callees

- `0x140006f5c`

## pseudocode

```c
__int16 __fastcall BfsGetPathLength(__int64 **a1, _WORD *a2, _WORD *a3)
{
  __int64 *v3; // r9
  __int16 v4; // ax
  __int16 v5; // r10

  v3 = *a1;
  v4 = 0;
  while ( v3 != (__int64 *)a1 )
  {
    v5 = *((_WORD *)v3 + 12);
    if ( v5 )
      v4 += v5 + 2;
    v3 = (__int64 *)*v3;
  }
  if ( *a3 )
    v4 += *a3 + 2;
  return *a2 + v4 + 2;
}

```

## disassembly

```asm
0x140006f5c  mov     r9, [rcx]
0x140006f5f  xor     r11d, r11d
0x140006f62  mov     eax, r11d
0x140006f65  jmp     short loc_140006F7E
0x140006f67  movzx   r10d, word ptr [r9+18h]
0x140006f6c  test    r10w, r10w
0x140006f70  jz      short loc_140006F7B
0x140006f72  add     r10w, 2
0x140006f77  add     ax, r10w
0x140006f7b  mov     r9, [r9]
0x140006f7e  cmp     r9, rcx
0x140006f81  jnz     short loc_140006F67
0x140006f83  movzx   ecx, word ptr [r8]
0x140006f87  test    cx, cx
0x140006f8a  jz      short loc_140006F93
0x140006f8c  add     cx, 2
0x140006f90  add     ax, cx
0x140006f93  add     ax, 2
0x140006f97  add     ax, [rdx]
0x140006f9a  retn
```
