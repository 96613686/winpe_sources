# ec_tell_frac

- ea: `0x18000a920`
- end: `0x18000a95e`
- name: `ec_tell_frac`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005aa0`
- `0x18000d040`
- `0x18000e400`

## pseudocode

```c
__int64 __fastcall ec_tell_frac(__int64 a1)
{
  unsigned int v1; // edx
  unsigned int v2; // r9d

  v1 = *(_DWORD *)(a1 + 32);
  _BitScanReverse(&v2, v1);
  return (unsigned int)(((__PAIR64__(8 * *(_DWORD *)(a1 + 24), dword_18002D4E0[(v1 >> (v2 - 15) >> 12) - 8])
                        - (v1 >> (v2 - 15))) >> 32)
                      - 8 * v2
                      - (v1 >> (v2 - 15) >> 12));
}

```

## disassembly

```asm
0x18000a920  mov     edx, [rcx+20h]
0x18000a923  lea     r11, dword_18002D4E0
0x18000a92a  mov     eax, [rcx+18h]
0x18000a92d  bsr     r9d, edx
0x18000a931  lea     ecx, [r9-0Fh]
0x18000a935  shr     edx, cl
0x18000a937  xor     ecx, ecx
0x18000a939  mov     r8d, edx
0x18000a93c  shr     r8d, 0Ch
0x18000a940  add     r8d, 0FFFFFFF8h
0x18000a944  cmp     edx, [r11+r8*4]
0x18000a948  setnbe  cl
0x18000a94b  shl     eax, 3
0x18000a94e  sub     eax, ecx
0x18000a950  lea     ecx, ds:8[r9*8]
0x18000a958  sub     eax, ecx
0x18000a95a  sub     eax, r8d
0x18000a95d  retn
```
