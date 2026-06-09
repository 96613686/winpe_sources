# BfsGetFileName

- ea: `0x140006af4`
- end: `0x140006b89`
- name: `BfsGetFileName`
- size: `149`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140001460`
- `0x140001fb0`
- `0x1400055d8`
- `0x140005d4c`
- `0x140006630`
- `0x140009b9c`
- `0x14000a7a0`

## callees

- `0x140006af4`

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
0x140006af4  movzx   r10d, word ptr [rdx+18h]
0x140006af9  xorps   xmm0, xmm0
0x140006afc  movzx   r8d, word ptr [rdx+8]
0x140006b01  mov     r9, rcx
0x140006b04  movups  xmmword ptr [rcx], xmm0
0x140006b07  cmp     r8w, r10w
0x140006b0b  jbe     short loc_140006B85
0x140006b0d  sub     r8w, [rdx+48h]
0x140006b12  mov     ecx, r10d
0x140006b15  mov     rax, [rdx+10h]
0x140006b19  sub     r8w, r10w
0x140006b1d  shr     rcx, 1
0x140006b20  mov     r10w, 2
0x140006b25  mov     [r9], r8w
0x140006b29  lea     r11, [rax+rcx*2]
0x140006b2d  mov     [r9+8], r11
0x140006b31  cmp     r8w, r10w
0x140006b35  jb      short loc_140006B7C
0x140006b37  sub     r8w, r10w
0x140006b3b  lea     rdx, [r11+2]
0x140006b3f  mov     [r9+8], rdx
0x140006b43  mov     [r9], r8w
0x140006b47  cmp     r8w, r10w
0x140006b4b  jb      short loc_140006B7C
0x140006b4d  movzx   eax, r8w
0x140006b51  movzx   ecx, ax
0x140006b54  shr     ax, 1
0x140006b57  dec     ax
0x140006b5a  movzx   eax, ax
0x140006b5d  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x140006b62  jnz     short loc_140006B80
0x140006b64  sub     r8w, r10w
0x140006b68  mov     [r9], r8w
0x140006b6c  movzx   eax, r8w
0x140006b70  movzx   ecx, r8w
0x140006b74  cmp     r8w, r10w
0x140006b78  jnb     short loc_140006B51
0x140006b7a  jmp     short loc_140006B80
0x140006b7c  movzx   ecx, r8w
0x140006b80  mov     [r9+2], cx
0x140006b85  mov     rax, r9
0x140006b88  retn
```
