# memset

- ea: `0x14000dc00`
- end: `0x14000dd07`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x140001154`
- `0x1400015cc`
- `0x1400019d0`
- `0x140001d6c`
- `0x14000301c`
- `0x140005490`
- `0x140005eb0`
- `0x14000678c`
- `0x140006dc8`
- `0x14000c6b4`
- `0x14000c9f0`
- `0x14000cd68`
- `0x14000d370`
- `0x14000f020`
- `0x1400152d0`

## callees

- `0x14000dc00`
- `0x14000dd40`

## pseudocode

```c
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  void *result; // rax
  __int64 v4; // rdx
  __m128 v5; // xmm0
  char *v6; // r8
  __m128 *v7; // rdx
  _OWORD *v8; // r9
  size_t v9; // r8
  __m128 *v10; // r9
  size_t v11; // r8
  _DWORD *v12; // r9
  size_t v13; // r8

  result = a1;
  v4 = 0x101010101010101LL * (unsigned __int8)Val;
  v5 = _mm_movelh_ps((__m128)(unsigned __int64)v4, (__m128)(unsigned __int64)v4);
  if ( Size >= 0x40 )
  {
    if ( (_isa_info & 2) != 0 && Size >= 0x320 )
      return (void *)_memset_repmovs();
    *(__m128 *)a1 = v5;
    v6 = (char *)a1 + Size;
    a1 = (void *)(((unsigned __int64)a1 + 16) & 0xFFFFFFFFFFFFFFF0uLL);
    Size = v6 - (_BYTE *)a1;
    if ( Size >= 0x40 )
    {
      v7 = (__m128 *)((char *)a1 + Size - 16);
      v8 = (_OWORD *)(((unsigned __int64)a1 + Size - 48) & 0xFFFFFFFFFFFFFFF0uLL);
      v9 = Size >> 6;
      do
      {
        *(__m128 *)a1 = v5;
        *((__m128 *)a1 + 1) = v5;
        a1 = (char *)a1 + 64;
        --v9;
        *((__m128 *)a1 - 2) = v5;
        *((__m128 *)a1 - 1) = v5;
      }
      while ( v9 );
      *v8 = v5;
      v8[1] = v5;
      v8[2] = v5;
      *v7 = v5;
      return result;
    }
LABEL_9:
    v10 = (__m128 *)((char *)a1 + Size - 16);
    *(__m128 *)a1 = v5;
    v11 = (Size & 0x20) >> 1;
    *v10 = v5;
    *(__m128 *)((char *)a1 + v11) = v5;
    *(__m128 *)((char *)v10 - v11) = v5;
    return result;
  }
  if ( Size >= 0x10 )
    goto LABEL_9;
  if ( Size < 4 )
  {
    if ( Size )
    {
      *(_BYTE *)a1 = v4;
      if ( Size != 1 )
        *(_WORD *)((char *)a1 + Size - 2) = v4;
    }
  }
  else
  {
    v12 = (char *)a1 + Size - 4;
    *(_DWORD *)a1 = v4;
    v13 = (Size & 8) >> 1;
    *v12 = v4;
    *(_DWORD *)((char *)a1 + v13) = v4;
    *(_DWORD *)((char *)v12 - v13) = v4;
  }
  return result;
}

```

## disassembly

```asm
0x14000dc00  mov     rax, rcx
0x14000dc03  movzx   edx, dl
0x14000dc06  mov     r9, 101010101010101h
0x14000dc10  imul    rdx, r9
0x14000dc14  movq    xmm0, rdx
0x14000dc19  movlhps xmm0, xmm0
0x14000dc1c  cmp     r8, 40h ; '@'
0x14000dc20  jb      short loc_14000DC90
0x14000dc22  test    cs:__isa_info, 2
0x14000dc29  jz      short loc_14000DC38
0x14000dc2b  cmp     r8, 320h
0x14000dc32  jnb     __memset_repmovs
0x14000dc38  movups  xmmword ptr [rcx], xmm0
0x14000dc3b  add     r8, rcx
0x14000dc3e  add     rcx, 10h
0x14000dc42  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000dc46  sub     r8, rcx
0x14000dc49  cmp     r8, 40h ; '@'
0x14000dc4d  jb      short loc_14000DC96
0x14000dc4f  lea     rdx, [rcx+r8-10h]
0x14000dc54  lea     r9, [rcx+r8-30h]
0x14000dc59  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000dc5d  shr     r8, 6
0x14000dc61  movaps  xmmword ptr [rcx], xmm0
0x14000dc64  movaps  xmmword ptr [rcx+10h], xmm0
0x14000dc68  add     rcx, 40h ; '@'
0x14000dc6c  dec     r8
0x14000dc6f  movaps  xmmword ptr [rcx-20h], xmm0
0x14000dc73  movaps  xmmword ptr [rcx-10h], xmm0
0x14000dc77  jnz     short loc_14000DC61
0x14000dc79  movaps  xmmword ptr [r9], xmm0
0x14000dc7d  movaps  xmmword ptr [r9+10h], xmm0
0x14000dc82  movaps  xmmword ptr [r9+20h], xmm0
0x14000dc87  movups  xmmword ptr [rdx], xmm0
0x14000dc8a  retn
0x14000dc90  cmp     r8, 10h
0x14000dc94  jb      short loc_14000DCC0
0x14000dc96  lea     r9, [r8+rcx-10h]
0x14000dc9b  and     r8, 20h
0x14000dc9f  movups  xmmword ptr [rcx], xmm0
0x14000dca2  shr     r8, 1
0x14000dca5  movups  xmmword ptr [r9], xmm0
0x14000dca9  movups  xmmword ptr [rcx+r8], xmm0
0x14000dcae  neg     r8
0x14000dcb1  movups  xmmword ptr [r9+r8], xmm0
0x14000dcb6  retn
0x14000dcc0  cmp     r8, 4
0x14000dcc4  jb      short loc_14000DCF0
0x14000dcc6  lea     r9, [r8+rcx-4]
0x14000dccb  and     r8, 8
0x14000dccf  mov     [rcx], edx
0x14000dcd1  shr     r8, 1
0x14000dcd4  mov     [r9], edx
0x14000dcd7  mov     [rcx+r8], edx
0x14000dcdb  neg     r8
0x14000dcde  mov     [r9+r8], edx
0x14000dce2  retn
0x14000dcf0  test    r8, r8
0x14000dcf3  jz      short locret_14000DD06
0x14000dcf5  mov     [rcx], dl
0x14000dcf7  lea     r9, [rcx+r8-2]
0x14000dcfc  cmp     r8, 1
0x14000dd00  jz      short locret_14000DD06
0x14000dd02  mov     [r9], dx
0x14000dd06  retn
```
