# CInputBitStream::finalLoadPeek(ulong,ulong)

- ea: `0x1800176e4`
- end: `0x18001773a`
- name: `?finalLoadPeek@CInputBitStream@@AEAAKKK@Z`
- size: `86`
- prototype: `__int64 __fastcall(CInputBitStream *this, int, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003620`
- `0x180004f10`
- `0x180010e00`
- `0x180011120`
- `0x180017570`
- `0x180017640`

## callees

- `0x1800176e4`

## pseudocode

```c
__int64 __fastcall CInputBitStream::finalLoadPeek(CInputBitStream *this, int a2, unsigned int a3)
{
  int v3; // r11d
  unsigned int v4; // r9d
  unsigned __int8 *v5; // rbx
  char i; // r10
  int v7; // eax

  v3 = *((_DWORD *)this + 2);
  v4 = 0;
  v5 = *(unsigned __int8 **)this;
  for ( i = 0; v3; --v3 )
  {
    v7 = *v5;
    i += 8;
    ++v5;
    v4 = v7 | (v4 << 8);
  }
  return (a2 << a3) | *((_DWORD *)&GetMask + a3) & (v4 >> (i - a3));
}

```

## disassembly

```asm
0x1800176e4  mov     [rsp+arg_0], rbx
0x1800176e9  mov     r11d, [rcx+8]
0x1800176ed  xor     r9d, r9d
0x1800176f0  mov     rbx, [rcx]
0x1800176f3  xor     r10d, r10d
0x1800176f6  test    r11d, r11d
0x1800176f9  jz      short loc_180017712
0x1800176fb  movzx   eax, byte ptr [rbx]
0x1800176fe  add     r10d, 8
0x180017702  shl     r9d, 8
0x180017706  inc     rbx
0x180017709  or      r9d, eax
0x18001770c  sub     r11d, 1
0x180017710  jnz     short loc_1800176FB
0x180017712  mov     rbx, [rsp+arg_0]
0x180017717  lea     rax, ?GetMask@@3QBKB; ulong const near * const GetMask
0x18001771e  sub     r10d, r8d
0x180017721  mov     cl, r10b
0x180017724  shr     r9d, cl
0x180017727  mov     ecx, r8d
0x18001772a  and     r9d, [rax+rcx*4]
0x18001772e  mov     ecx, r8d
0x180017731  shl     edx, cl
0x180017733  or      r9d, edx
0x180017736  mov     eax, r9d
0x180017739  retn
```
