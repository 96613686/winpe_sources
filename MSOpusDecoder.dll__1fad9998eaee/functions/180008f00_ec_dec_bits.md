# ec_dec_bits

- ea: `0x180008f00`
- end: `0x180008f6c`
- name: `ec_dec_bits`
- size: `108`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005aa0`
- `0x18000f910`
- `0x18000fa20`
- `0x180010fa0`
- `0x180011100`

## callees

- `0x180008f00`

## pseudocode

```c
__int64 __fastcall ec_dec_bits(__int64 a1, unsigned int a2)
{
  int v2; // r8d
  unsigned int v4; // r10d
  unsigned int v5; // r11d
  unsigned int v6; // ecx
  int v7; // eax
  char v8; // cl

  v2 = *(_DWORD *)(a1 + 20);
  v4 = *(_DWORD *)(a1 + 16);
  if ( v2 < a2 )
  {
    v5 = *(_DWORD *)(a1 + 8);
    do
    {
      v6 = *(_DWORD *)(a1 + 12);
      if ( v6 >= v5 )
      {
        v7 = 0;
      }
      else
      {
        *(_DWORD *)(a1 + 12) = v6 + 1;
        v7 = *(unsigned __int8 *)(v5 - v6 - 1 + *(_QWORD *)a1);
      }
      v8 = v2;
      v2 += 8;
      v4 |= v7 << v8;
    }
    while ( v2 <= 24 );
  }
  *(_DWORD *)(a1 + 24) += a2;
  *(_DWORD *)(a1 + 16) = v4 >> a2;
  *(_DWORD *)(a1 + 20) = v2 - a2;
  return v4 & ((1 << a2) - 1);
}

```

## disassembly

```asm
0x180008f00  mov     r8d, [rcx+14h]
0x180008f04  mov     r9, rcx
0x180008f07  mov     r10d, [rcx+10h]
0x180008f0b  cmp     r8d, edx
0x180008f0e  jnb     short loc_180008F49
0x180008f10  mov     r11d, [rcx+8]
0x180008f14  mov     ecx, [r9+0Ch]
0x180008f18  cmp     ecx, r11d
0x180008f1b  jnb     short loc_180008F35
0x180008f1d  lea     eax, [rcx+1]
0x180008f20  mov     [r9+0Ch], eax
0x180008f24  mov     eax, r11d
0x180008f27  sub     eax, ecx
0x180008f29  lea     ecx, [rax-1]
0x180008f2c  mov     rax, [r9]
0x180008f2f  movzx   eax, byte ptr [rcx+rax]
0x180008f33  jmp     short loc_180008F37
0x180008f35  xor     eax, eax
0x180008f37  mov     ecx, r8d
0x180008f3a  add     r8d, 8
0x180008f3e  shl     eax, cl
0x180008f40  or      r10d, eax
0x180008f43  cmp     r8d, 18h
0x180008f47  jle     short loc_180008F14
0x180008f49  add     [r9+18h], edx
0x180008f4d  mov     ecx, edx
0x180008f4f  mov     eax, r10d
0x180008f52  sub     r8d, edx
0x180008f55  shr     eax, cl
0x180008f57  mov     [r9+10h], eax
0x180008f5b  mov     eax, 1
0x180008f60  shl     eax, cl
0x180008f62  dec     eax
0x180008f64  mov     [r9+14h], r8d
0x180008f68  and     eax, r10d
0x180008f6b  retn
```
