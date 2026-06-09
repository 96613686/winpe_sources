# CInputBitStream::finalLoad(ulong,ulong)

- ea: `0x180002cc0`
- end: `0x180002d3d`
- name: `?finalLoad@CInputBitStream@@AEAAKKK@Z`
- size: `125`
- prototype: `__int64 __fastcall(CInputBitStream *this, int, unsigned int)`
- caller_count: `35`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e0`
- `0x1800014c0`
- `0x180002e90`
- `0x1800038e0`
- `0x180004f10`
- `0x1800065b0`
- `0x180006fe0`
- `0x1800081b0`
- `0x180009780`
- `0x18000de44`
- `0x18000ebd0`
- `0x180010e00`
- `0x180011938`
- `0x180011a44`
- `0x180019d60`
- `0x18001ab70`
- `0x18001cd34`
- `0x18001d948`
- `0x18001f53c`
- `0x180025f7c`
- `0x18002ee34`
- `0x18002f27c`
- `0x18002f614`
- `0x180032950`
- `0x180033324`
- `0x180033ed0`
- `0x180034274`
- `0x180034844`
- `0x180034998`
- `0x180034b30`
- `0x180034ce0`
- `0x1800350e0`
- `0x180035268`
- `0x180035770`
- `0x180035e90`

## callees

- `0x180002cc0`

## pseudocode

```c
__int64 __fastcall CInputBitStream::finalLoad(CInputBitStream *this, int a2, unsigned int a3)
{
  int v3; // r11d
  __int64 v5; // r9
  unsigned __int8 *v6; // rbx
  unsigned int v7; // r8d
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // eax
  int v11; // eax
  int v12; // edx

  v3 = *((_DWORD *)this + 2);
  v5 = a3;
  *(_QWORD *)((char *)this + 12) = 0;
  if ( v3 )
  {
    v6 = *(unsigned __int8 **)this;
    v7 = 0;
    v8 = 0;
    do
    {
      v9 = v7 << 8;
      v8 += 8;
      *((_DWORD *)this + 3) = v9;
      v10 = *v6++;
      v7 = v10 | v9;
      *(_QWORD *)this = v6;
      --v3;
      *((_DWORD *)this + 3) = v7;
      *((_DWORD *)this + 2) = v3;
      *((_DWORD *)this + 4) = v8;
    }
    while ( v3 );
  }
  else
  {
    v8 = 0;
    v7 = 0;
  }
  v11 = *((_DWORD *)&GetMask + v5);
  v12 = v8 - v5;
  *((_DWORD *)this + 4) = v12;
  return (a2 << v5) | (v7 >> v12) & v11;
}

```

## disassembly

```asm
0x180002cc0  mov     [rsp+arg_0], rbx
0x180002cc5  mov     r11d, [rcx+8]
0x180002cc9  mov     r10d, edx
0x180002ccc  mov     r9d, r8d
0x180002ccf  mov     qword ptr [rcx+0Ch], 0
0x180002cd7  test    r11d, r11d
0x180002cda  jz      short loc_180002D36
0x180002cdc  mov     rbx, [rcx]
0x180002cdf  xor     r8d, r8d
0x180002ce2  xor     edx, edx
0x180002ce4  shl     r8d, 8
0x180002ce8  add     edx, 8
0x180002ceb  mov     [rcx+0Ch], r8d
0x180002cef  movzx   eax, byte ptr [rbx]
0x180002cf2  inc     rbx
0x180002cf5  or      r8d, eax
0x180002cf8  mov     [rcx], rbx
0x180002cfb  dec     r11d
0x180002cfe  mov     [rcx+0Ch], r8d
0x180002d02  mov     [rcx+8], r11d
0x180002d06  mov     [rcx+10h], edx
0x180002d09  test    r11d, r11d
0x180002d0c  jnz     short loc_180002CE4
0x180002d0e  mov     rbx, [rsp+arg_0]
0x180002d13  lea     r11, ?GetMask@@3QBKB; ulong const near * const GetMask
0x180002d1a  mov     eax, [r11+r9*4]
0x180002d1e  sub     edx, r9d
0x180002d21  mov     [rcx+10h], edx
0x180002d24  mov     ecx, edx
0x180002d26  shr     r8d, cl
0x180002d29  mov     ecx, r9d
0x180002d2c  shl     r10d, cl
0x180002d2f  and     eax, r8d
0x180002d32  or      eax, r10d
0x180002d35  retn
0x180002d36  xor     edx, edx
0x180002d38  xor     r8d, r8d
0x180002d3b  jmp     short loc_180002D0E
```
