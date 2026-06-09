# BfsGetFileName

- ea: `0x140006c84`
- end: `0x140006d19`
- name: `BfsGetFileName`
- size: `149`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ba0`
- `0x140002d30`
- `0x140005768`
- `0x140005edc`
- `0x1400067c0`
- `0x140009d2c`
- `0x14000a930`

## callees

- `0x140006c84`

## pseudocode

```c
__int64 __fastcall BfsGetFileName(__int64 a1, __int64 a2)
{
  unsigned int v2; // r10d
  unsigned __int16 v3; // r8
  __int64 v5; // rax
  unsigned __int16 v6; // r8
  __int64 v7; // r11
  unsigned __int16 v8; // ax
  unsigned __int16 v9; // cx

  v2 = *(unsigned __int16 *)(a2 + 24);
  v3 = *(_WORD *)(a2 + 8);
  *(_OWORD *)a1 = 0;
  if ( v3 > (unsigned __int16)v2 )
  {
    v5 = *(_QWORD *)(a2 + 16);
    v6 = v3 - *(_WORD *)(a2 + 72) - v2;
    *(_WORD *)a1 = v6;
    v7 = v5 + 2 * ((unsigned __int64)v2 >> 1);
    *(_QWORD *)(a1 + 8) = v7;
    if ( v6 < 2u || (v6 -= 2, *(_QWORD *)(a1 + 8) = v7 + 2, *(_WORD *)a1 = v6, v6 < 2u) )
    {
      v9 = v6;
    }
    else
    {
      v8 = v6;
      do
      {
        v9 = v8;
        if ( *(_WORD *)(v7 + 2 + 2LL * (unsigned __int16)((v8 >> 1) - 1)) != 92 )
          break;
        v6 -= 2;
        *(_WORD *)a1 = v6;
        v8 = v6;
        v9 = v6;
      }
      while ( v6 >= 2u );
    }
    *(_WORD *)(a1 + 2) = v9;
  }
  return a1;
}

```

## disassembly

```asm
0x140006c84  movzx   r10d, word ptr [rdx+18h]
0x140006c89  xorps   xmm0, xmm0
0x140006c8c  movzx   r8d, word ptr [rdx+8]
0x140006c91  mov     r9, rcx
0x140006c94  movups  xmmword ptr [rcx], xmm0
0x140006c97  cmp     r8w, r10w
0x140006c9b  jbe     short loc_140006D15
0x140006c9d  sub     r8w, [rdx+48h]
0x140006ca2  mov     ecx, r10d
0x140006ca5  mov     rax, [rdx+10h]
0x140006ca9  sub     r8w, r10w
0x140006cad  shr     rcx, 1
0x140006cb0  mov     r10w, 2
0x140006cb5  mov     [r9], r8w
0x140006cb9  lea     r11, [rax+rcx*2]
0x140006cbd  mov     [r9+8], r11
0x140006cc1  cmp     r8w, r10w
0x140006cc5  jb      short loc_140006D0C
0x140006cc7  sub     r8w, r10w
0x140006ccb  lea     rdx, [r11+2]
0x140006ccf  mov     [r9+8], rdx
0x140006cd3  mov     [r9], r8w
0x140006cd7  cmp     r8w, r10w
0x140006cdb  jb      short loc_140006D0C
0x140006cdd  movzx   eax, r8w
0x140006ce1  movzx   ecx, ax
0x140006ce4  shr     ax, 1
0x140006ce7  dec     ax
0x140006cea  movzx   eax, ax
0x140006ced  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x140006cf2  jnz     short loc_140006D10
0x140006cf4  sub     r8w, r10w
0x140006cf8  mov     [r9], r8w
0x140006cfc  movzx   eax, r8w
0x140006d00  movzx   ecx, r8w
0x140006d04  cmp     r8w, r10w
0x140006d08  jnb     short loc_140006CE1
0x140006d0a  jmp     short loc_140006D10
0x140006d0c  movzx   ecx, r8w
0x140006d10  mov     [r9+2], cx
0x140006d15  mov     rax, r9
0x140006d18  retn
```
