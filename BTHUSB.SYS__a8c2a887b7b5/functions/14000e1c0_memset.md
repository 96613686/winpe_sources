# memset

- ea: `0x14000e1c0`
- end: `0x14000e2c7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e74`
- `0x140001f44`
- `0x140002738`
- `0x1400030e0`
- `0x140004de0`
- `0x140004fc8`
- `0x14000509c`
- `0x14000a290`
- `0x14000ac54`
- `0x14000da68`
- `0x14000f020`
- `0x140017858`
- `0x1400179ac`
- `0x140017f30`
- `0x140019008`
- `0x14001946c`
- `0x140019894`
- `0x140019b00`
- `0x140019ea0`
- `0x14001a054`
- `0x14001a4a8`
- `0x14001a6e8`
- `0x14001b73c`
- `0x14001c478`

## callees

- `0x14000e1c0`
- `0x14000e300`

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
0x14000e1c0  mov     rax, rcx
0x14000e1c3  movzx   edx, dl
0x14000e1c6  mov     r9, 101010101010101h
0x14000e1d0  imul    rdx, r9
0x14000e1d4  movq    xmm0, rdx
0x14000e1d9  movlhps xmm0, xmm0
0x14000e1dc  cmp     r8, 40h ; '@'
0x14000e1e0  jb      short loc_14000E250
0x14000e1e2  test    cs:__isa_info, 2
0x14000e1e9  jz      short loc_14000E1F8
0x14000e1eb  cmp     r8, 320h
0x14000e1f2  jnb     __memset_repmovs
0x14000e1f8  movups  xmmword ptr [rcx], xmm0
0x14000e1fb  add     r8, rcx
0x14000e1fe  add     rcx, 10h
0x14000e202  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000e206  sub     r8, rcx
0x14000e209  cmp     r8, 40h ; '@'
0x14000e20d  jb      short loc_14000E256
0x14000e20f  lea     rdx, [rcx+r8-10h]
0x14000e214  lea     r9, [rcx+r8-30h]
0x14000e219  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000e21d  shr     r8, 6
0x14000e221  movaps  xmmword ptr [rcx], xmm0
0x14000e224  movaps  xmmword ptr [rcx+10h], xmm0
0x14000e228  add     rcx, 40h ; '@'
0x14000e22c  dec     r8
0x14000e22f  movaps  xmmword ptr [rcx-20h], xmm0
0x14000e233  movaps  xmmword ptr [rcx-10h], xmm0
0x14000e237  jnz     short loc_14000E221
0x14000e239  movaps  xmmword ptr [r9], xmm0
0x14000e23d  movaps  xmmword ptr [r9+10h], xmm0
0x14000e242  movaps  xmmword ptr [r9+20h], xmm0
0x14000e247  movups  xmmword ptr [rdx], xmm0
0x14000e24a  retn
0x14000e250  cmp     r8, 10h
0x14000e254  jb      short loc_14000E280
0x14000e256  lea     r9, [r8+rcx-10h]
0x14000e25b  and     r8, 20h
0x14000e25f  movups  xmmword ptr [rcx], xmm0
0x14000e262  shr     r8, 1
0x14000e265  movups  xmmword ptr [r9], xmm0
0x14000e269  movups  xmmword ptr [rcx+r8], xmm0
0x14000e26e  neg     r8
0x14000e271  movups  xmmword ptr [r9+r8], xmm0
0x14000e276  retn
0x14000e280  cmp     r8, 4
0x14000e284  jb      short loc_14000E2B0
0x14000e286  lea     r9, [r8+rcx-4]
0x14000e28b  and     r8, 8
0x14000e28f  mov     [rcx], edx
0x14000e291  shr     r8, 1
0x14000e294  mov     [r9], edx
0x14000e297  mov     [rcx+r8], edx
0x14000e29b  neg     r8
0x14000e29e  mov     [r9+r8], edx
0x14000e2a2  retn
0x14000e2b0  test    r8, r8
0x14000e2b3  jz      short locret_14000E2C6
0x14000e2b5  mov     [rcx], dl
0x14000e2b7  lea     r9, [rcx+r8-2]
0x14000e2bc  cmp     r8, 1
0x14000e2c0  jz      short locret_14000E2C6
0x14000e2c2  mov     [r9], dx
0x14000e2c6  retn
```
