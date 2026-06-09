# memset

- ea: `0x14001b2c0`
- end: `0x14001b3c7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x140001bd0`
- `0x140001e70`
- `0x140002630`
- `0x14000bd78`
- `0x1400100cc`
- `0x1400126dc`
- `0x140017fe8`
- `0x140018094`
- `0x140018148`
- `0x1400186b0`
- `0x140018740`
- `0x140018b98`
- `0x14001c020`
- `0x1400285d4`
- `0x140029cd0`
- `0x14002a548`
- `0x14002add0`
- `0x14002b5a0`
- `0x14002c1a4`
- `0x14002cb84`
- `0x14002f42c`

## callees

- `0x14001b2c0`
- `0x14001b400`

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
0x14001b2c0  mov     rax, rcx
0x14001b2c3  movzx   edx, dl
0x14001b2c6  mov     r9, 101010101010101h
0x14001b2d0  imul    rdx, r9
0x14001b2d4  movq    xmm0, rdx
0x14001b2d9  movlhps xmm0, xmm0
0x14001b2dc  cmp     r8, 40h ; '@'
0x14001b2e0  jb      short loc_14001B350
0x14001b2e2  test    cs:__isa_info, 2
0x14001b2e9  jz      short loc_14001B2F8
0x14001b2eb  cmp     r8, 320h
0x14001b2f2  jnb     __memset_repmovs
0x14001b2f8  movups  xmmword ptr [rcx], xmm0
0x14001b2fb  add     r8, rcx
0x14001b2fe  add     rcx, 10h
0x14001b302  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14001b306  sub     r8, rcx
0x14001b309  cmp     r8, 40h ; '@'
0x14001b30d  jb      short loc_14001B356
0x14001b30f  lea     rdx, [rcx+r8-10h]
0x14001b314  lea     r9, [rcx+r8-30h]
0x14001b319  and     r9, 0FFFFFFFFFFFFFFF0h
0x14001b31d  shr     r8, 6
0x14001b321  movaps  xmmword ptr [rcx], xmm0
0x14001b324  movaps  xmmword ptr [rcx+10h], xmm0
0x14001b328  add     rcx, 40h ; '@'
0x14001b32c  dec     r8
0x14001b32f  movaps  xmmword ptr [rcx-20h], xmm0
0x14001b333  movaps  xmmword ptr [rcx-10h], xmm0
0x14001b337  jnz     short loc_14001B321
0x14001b339  movaps  xmmword ptr [r9], xmm0
0x14001b33d  movaps  xmmword ptr [r9+10h], xmm0
0x14001b342  movaps  xmmword ptr [r9+20h], xmm0
0x14001b347  movups  xmmword ptr [rdx], xmm0
0x14001b34a  retn
0x14001b350  cmp     r8, 10h
0x14001b354  jb      short loc_14001B380
0x14001b356  lea     r9, [r8+rcx-10h]
0x14001b35b  and     r8, 20h
0x14001b35f  movups  xmmword ptr [rcx], xmm0
0x14001b362  shr     r8, 1
0x14001b365  movups  xmmword ptr [r9], xmm0
0x14001b369  movups  xmmword ptr [rcx+r8], xmm0
0x14001b36e  neg     r8
0x14001b371  movups  xmmword ptr [r9+r8], xmm0
0x14001b376  retn
0x14001b380  cmp     r8, 4
0x14001b384  jb      short loc_14001B3B0
0x14001b386  lea     r9, [r8+rcx-4]
0x14001b38b  and     r8, 8
0x14001b38f  mov     [rcx], edx
0x14001b391  shr     r8, 1
0x14001b394  mov     [r9], edx
0x14001b397  mov     [rcx+r8], edx
0x14001b39b  neg     r8
0x14001b39e  mov     [r9+r8], edx
0x14001b3a2  retn
0x14001b3b0  test    r8, r8
0x14001b3b3  jz      short locret_14001B3C6
0x14001b3b5  mov     [rcx], dl
0x14001b3b7  lea     r9, [rcx+r8-2]
0x14001b3bc  cmp     r8, 1
0x14001b3c0  jz      short locret_14001B3C6
0x14001b3c2  mov     [r9], dx
0x14001b3c6  retn
```
