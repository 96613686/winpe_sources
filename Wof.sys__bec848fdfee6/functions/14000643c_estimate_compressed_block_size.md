# estimate_compressed_block_size

- ea: `0x14000643c`
- end: `0x1400064ff`
- name: `estimate_compressed_block_size`
- size: `195`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005870`
- `0x14000c8a0`

## callees

- `0x14000643c`

## pseudocode

```c
__int64 __fastcall estimate_compressed_block_size(__int64 a1)
{
  int v2; // r8d
  __int64 i; // rcx
  int v4; // edx
  int v5; // eax
  unsigned int v6; // r11d
  unsigned __int8 j; // r10
  int v8; // edi
  int v9; // ebx
  __int64 v10; // rax
  __int64 k; // rdx
  int v12; // ecx
  int v13; // eax

  v2 = 1200;
  for ( i = 0; i != 256; ++i )
  {
    v4 = *(unsigned __int16 *)(a1 + 2 * i + 10560);
    v5 = *(unsigned __int8 *)(a1 + i + 9608);
    v2 += v5 * v4;
  }
  v6 = *(_DWORD *)(a1 + 2208);
  for ( j = 0; j < v6; ++j )
  {
    v8 = 8;
    v9 = 8 * j + 256;
    do
    {
      v10 = v9++;
      v2 += ((unsigned __int8)dec_extra_bits[j] + *(unsigned __int8 *)(v10 + a1 + 9608))
          * *(unsigned __int16 *)(a1 + 2 * v10 + 10560);
      --v8;
    }
    while ( v8 );
  }
  for ( k = 0; k != 249; ++k )
  {
    v12 = *(unsigned __int16 *)(a1 + 2 * k + 15462);
    v13 = *(unsigned __int8 *)(a1 + k + 10309);
    v2 += v13 * v12;
  }
  return (unsigned int)(v2 + 7) >> 3;
}

```

## disassembly

```asm
0x14000643c  push    rbx
0x14000643e  push    rsi
0x14000643f  push    rdi
0x140006440  mov     r9, rcx
0x140006443  mov     r8d, 4B0h
0x140006449  xor     ecx, ecx
0x14000644b  movzx   edx, word ptr [r9+rcx*2+2940h]
0x140006454  movzx   eax, byte ptr [r9+rcx+2588h]
0x14000645d  inc     rcx
0x140006460  imul    edx, eax
0x140006463  add     r8d, edx
0x140006466  cmp     rcx, 100h
0x14000646d  jnz     short loc_14000644B
0x14000646f  mov     r11d, [r9+8A0h]
0x140006476  xor     r10b, r10b
0x140006479  test    r11d, r11d
0x14000647c  jz      short loc_1400064CD
0x14000647e  movzx   eax, r10b
0x140006482  lea     rcx, dec_extra_bits
0x140006489  mov     edi, 8
0x14000648e  lea     ebx, ds:100h[rax*8]
0x140006495  movzx   eax, r10b
0x140006499  movzx   esi, byte ptr [rax+rcx]
0x14000649d  movsxd  rax, ebx
0x1400064a0  inc     ebx
0x1400064a2  movzx   ecx, byte ptr [rax+r9+2588h]
0x1400064ab  movzx   edx, word ptr [r9+rax*2+2940h]
0x1400064b4  add     ecx, esi
0x1400064b6  imul    edx, ecx
0x1400064b9  add     r8d, edx
0x1400064bc  sub     edi, 1
0x1400064bf  jnz     short loc_14000649D
0x1400064c1  inc     r10b
0x1400064c4  movzx   eax, r10b
0x1400064c8  cmp     eax, r11d
0x1400064cb  jb      short loc_14000647E
0x1400064cd  xor     edx, edx
0x1400064cf  movzx   ecx, word ptr [r9+rdx*2+3C66h]
0x1400064d8  movzx   eax, byte ptr [r9+rdx+2845h]
0x1400064e1  inc     rdx
0x1400064e4  imul    ecx, eax
0x1400064e7  add     r8d, ecx
0x1400064ea  cmp     rdx, 0F9h
0x1400064f1  jnz     short loc_1400064CF
0x1400064f3  lea     eax, [r8+7]
0x1400064f7  shr     eax, 3
0x1400064fa  pop     rdi
0x1400064fb  pop     rsi
0x1400064fc  pop     rbx
0x1400064fd  retn
```
