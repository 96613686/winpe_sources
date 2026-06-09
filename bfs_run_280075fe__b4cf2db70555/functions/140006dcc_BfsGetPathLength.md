# BfsGetPathLength

- ea: `0x140006dcc`
- end: `0x140006e0b`
- name: `BfsGetPathLength`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005424`
- `0x1400061a0`

## callees

- `0x140006dcc`

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
0x140006dcc  mov     r9, [rcx]
0x140006dcf  xor     r11d, r11d
0x140006dd2  mov     eax, r11d
0x140006dd5  jmp     short loc_140006DEE
0x140006dd7  movzx   r10d, word ptr [r9+18h]
0x140006ddc  test    r10w, r10w
0x140006de0  jz      short loc_140006DEB
0x140006de2  add     r10w, 2
0x140006de7  add     ax, r10w
0x140006deb  mov     r9, [r9]
0x140006dee  cmp     r9, rcx
0x140006df1  jnz     short loc_140006DD7
0x140006df3  movzx   ecx, word ptr [r8]
0x140006df7  test    cx, cx
0x140006dfa  jz      short loc_140006E03
0x140006dfc  add     cx, 2
0x140006e00  add     ax, cx
0x140006e03  add     ax, 2
0x140006e07  add     ax, [rdx]
0x140006e0a  retn
```
