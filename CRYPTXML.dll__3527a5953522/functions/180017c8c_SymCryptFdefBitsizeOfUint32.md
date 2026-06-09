# SymCryptFdefBitsizeOfUint32

- ea: `0x180017c8c`
- end: `0x180017d51`
- name: `SymCryptFdefBitsizeOfUint32`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180014590`
- `0x180017fec`

## pseudocode

```c
unsigned __int64 __fastcall SymCryptFdefBitsizeOfUint32(int a1)
{
  unsigned __int64 v1; // rbx
  unsigned int v2; // edx
  unsigned int v3; // r11d
  unsigned int v4; // ecx
  unsigned int v5; // r10d
  unsigned int v6; // edx
  unsigned int v7; // r9d
  unsigned int v8; // r8d

  v1 = (unsigned __int64)-(__int64)(a1 & 0xFFFF0000) >> 32;
  v2 = (unsigned __int16)(a1 & ~(unsigned __int16)((unsigned __int64)-(__int64)(a1 & 0xFFFF0000) >> 32))
     | v1 & ((a1 & 0xFFFF0000) >> 16);
  v3 = -(v2 & 0xFF00) >> 16;
  v4 = v3 & (v2 >> 8) | v2 & (unsigned __int8)~(unsigned __int8)(-(v2 & 0xFF00) >> 16);
  v5 = -(v4 & 0xF0) >> 16;
  v6 = v4 & ~v5 | v5 & (v4 >> 4);
  v7 = -((v4 & (unsigned __int8)~(_BYTE)v5 | v5 & (unsigned __int8)(v4 >> 4)) & 0xC) >> 16;
  v8 = (unsigned __int8)v6 & (unsigned __int8)~(unsigned __int8)(-(v6 & 0xC) >> 16) & 3 | v7 & (v6 >> 2);
  return (v8 & 1 | ((v8 & 2) != 0)) + ((v8 >> 1) & 1 | v1 & 0x10 | v3 & 8 | v5 & 4 | v7 & 2);
}

```

## disassembly

```asm
0x180017c8c  mov     [rsp+arg_0], rbx
0x180017c91  mov     eax, ecx
0x180017c93  and     eax, 0FFFF0000h
0x180017c98  mov     ebx, eax
0x180017c9a  mov     edx, eax
0x180017c9c  neg     rbx
0x180017c9f  shr     edx, 10h
0x180017ca2  shr     rbx, 20h
0x180017ca6  and     edx, ebx
0x180017ca8  mov     eax, ebx
0x180017caa  not     eax
0x180017cac  and     ebx, 10h
0x180017caf  and     eax, ecx
0x180017cb1  movzx   eax, ax
0x180017cb4  or      edx, eax
0x180017cb6  mov     r11d, edx
0x180017cb9  and     r11d, 0FF00h
0x180017cc0  neg     r11d
0x180017cc3  shr     r11d, 10h
0x180017cc7  mov     eax, r11d
0x180017cca  not     eax
0x180017ccc  and     eax, edx
0x180017cce  shr     edx, 8
0x180017cd1  movzx   ecx, al
0x180017cd4  and     edx, r11d
0x180017cd7  or      ecx, edx
0x180017cd9  and     r11d, 8
0x180017cdd  mov     r10d, ecx
0x180017ce0  mov     edx, ecx
0x180017ce2  and     r10d, 0F0h
0x180017ce9  shr     edx, 4
0x180017cec  neg     r10d
0x180017cef  shr     r10d, 10h
0x180017cf3  mov     eax, r10d
0x180017cf6  and     edx, r10d
0x180017cf9  not     eax
0x180017cfb  and     r10d, 4
0x180017cff  and     eax, ecx
0x180017d01  or      edx, eax
0x180017d03  mov     r9d, edx
0x180017d06  mov     r8d, edx
0x180017d09  and     r9d, 0Ch
0x180017d0d  shr     r8d, 2
0x180017d11  neg     r9d
0x180017d14  shr     r9d, 10h
0x180017d18  mov     eax, r9d
0x180017d1b  and     r8d, r9d
0x180017d1e  and     r9d, 2
0x180017d22  not     eax
0x180017d24  or      r9d, r10d
0x180017d27  and     eax, edx
0x180017d29  or      r9d, r11d
0x180017d2c  and     eax, 3
0x180017d2f  or      r8d, eax
0x180017d32  or      r9d, ebx
0x180017d35  mov     rbx, [rsp+arg_0]
0x180017d3a  mov     ecx, r8d
0x180017d3d  shr     ecx, 1
0x180017d3f  and     ecx, 1
0x180017d42  or      r9d, ecx
0x180017d45  or      ecx, r8d
0x180017d48  and     ecx, 1
0x180017d4b  lea     eax, [rcx+r9]
0x180017d4f  retn
```
