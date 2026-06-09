# CInputBitStream::peekBits(ulong)

- ea: `0x180011120`
- end: `0x1800111b6`
- name: `?peekBits@CInputBitStream@@QEAAKK@Z`
- size: `150`
- prototype: `unsigned int __fastcall(CInputBitStream *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ddf4`
- `0x18000ebd0`
- `0x180011938`
- `0x180011a44`
- `0x18001f53c`
- `0x180034274`
- `0x180035770`
- `0x180035e90`

## callees

- `0x180011120`
- `0x1800176e4`

## pseudocode

```c
unsigned int __fastcall CInputBitStream::peekBits(CInputBitStream *this, unsigned int a2)
{
  __int64 v2; // r9
  __int64 v3; // rdx
  int v4; // r8d
  unsigned int v5; // r10d
  unsigned int v7; // r10d
  __int64 v8; // r9

  v2 = a2;
  if ( *((_DWORD *)this + 5) )
    return 0;
  v3 = *((unsigned int *)this + 4);
  v4 = *((_DWORD *)this + 2);
  if ( (int)v3 + 8 * v4 < (unsigned int)v2 )
    return 0;
  v5 = *((_DWORD *)this + 3);
  if ( (unsigned int)v2 <= (unsigned int)v3 )
    return *((_DWORD *)&GetMask + v2) & (v5 >> (v3 - v2));
  v7 = *((_DWORD *)&GetMask + v3) & v5;
  v8 = (unsigned int)(v2 - v3);
  if ( v4 < 4 )
    return CInputBitStream::finalLoadPeek(this, v7, v8);
  else
    return (v7 << v8)
         | *((_DWORD *)&GetMask + v8)
         & ((((*(unsigned __int8 *)(*(_QWORD *)this + 2LL)
             | ((*(unsigned __int8 *)(*(_QWORD *)this + 1LL) | (**(unsigned __int8 **)this << 8)) << 8)) << 8)
           | (unsigned int)*(unsigned __int8 *)(*(_QWORD *)this + 3LL)) >> (32 - v8));
}

```

## disassembly

```asm
0x180011120  cmp     dword ptr [rcx+14h], 0
0x180011124  mov     r9d, edx
0x180011127  jnz     short loc_1800111A7
0x180011129  mov     edx, [rcx+10h]
0x18001112c  mov     r8d, [rcx+8]
0x180011130  lea     eax, [rdx+r8*8]
0x180011134  cmp     eax, r9d
0x180011137  jb      short loc_1800111A7
0x180011139  mov     r10d, [rcx+0Ch]
0x18001113d  lea     r11, ?GetMask@@3QBKB; ulong const near * const GetMask
0x180011144  cmp     r9d, edx
0x180011147  ja      short loc_18001115A
0x180011149  sub     edx, r9d
0x18001114c  movzx   ecx, dl
0x18001114f  shr     r10d, cl
0x180011152  and     r10d, [r11+r9*4]
0x180011156  mov     eax, r10d
0x180011159  retn
0x18001115a  and     r10d, [r11+rdx*4]
0x18001115e  sub     r9d, edx
0x180011161  cmp     r8d, 4
0x180011165  jl      short loc_1800111AB
0x180011167  mov     rdx, [rcx]
0x18001116a  mov     ecx, 20h ; ' '
0x18001116f  sub     ecx, r9d
0x180011172  movzx   eax, byte ptr [rdx+1]
0x180011176  movzx   r8d, byte ptr [rdx]
0x18001117a  shl     r8d, 8
0x18001117e  or      r8d, eax
0x180011181  movzx   eax, byte ptr [rdx+2]
0x180011185  shl     r8d, 8
0x180011189  or      r8d, eax
0x18001118c  movzx   eax, byte ptr [rdx+3]
0x180011190  shl     r8d, 8
0x180011194  or      eax, r8d
0x180011197  shr     eax, cl
0x180011199  mov     ecx, r9d; this
0x18001119c  and     eax, [r11+r9*4]
0x1800111a0  shl     r10d, cl
0x1800111a3  or      eax, r10d
0x1800111a6  retn
0x1800111a7  xor     eax, eax
0x1800111a9  jmp     short locret_180011159
0x1800111ab  mov     r8d, r9d; unsigned int
0x1800111ae  mov     edx, r10d; unsigned int
0x1800111b1  jmp     ?finalLoadPeek@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoadPeek(ulong,ulong)
```
