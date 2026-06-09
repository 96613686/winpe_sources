# memset

- ea: `0x140002ac0`
- end: `0x140002bc7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140001670`
- `0x140001730`
- `0x140003020`
- `0x14000c18c`
- `0x14000cc54`
- `0x14000d52c`
- `0x14000d5f0`
- `0x14000d7c8`
- `0x14000dd04`
- `0x14000e7a4`
- `0x14000e918`
- `0x14000ec90`
- `0x140012530`

## callees

- `0x140002ac0`
- `0x140002c00`

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
0x140002ac0  mov     rax, rcx
0x140002ac3  movzx   edx, dl
0x140002ac6  mov     r9, 101010101010101h
0x140002ad0  imul    rdx, r9
0x140002ad4  movq    xmm0, rdx
0x140002ad9  movlhps xmm0, xmm0
0x140002adc  cmp     r8, 40h ; '@'
0x140002ae0  jb      short loc_140002B50
0x140002ae2  test    cs:__isa_info, 2
0x140002ae9  jz      short loc_140002AF8
0x140002aeb  cmp     r8, 320h
0x140002af2  jnb     __memset_repmovs
0x140002af8  movups  xmmword ptr [rcx], xmm0
0x140002afb  add     r8, rcx
0x140002afe  add     rcx, 10h
0x140002b02  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140002b06  sub     r8, rcx
0x140002b09  cmp     r8, 40h ; '@'
0x140002b0d  jb      short loc_140002B56
0x140002b0f  lea     rdx, [rcx+r8-10h]
0x140002b14  lea     r9, [rcx+r8-30h]
0x140002b19  and     r9, 0FFFFFFFFFFFFFFF0h
0x140002b1d  shr     r8, 6
0x140002b21  movaps  xmmword ptr [rcx], xmm0
0x140002b24  movaps  xmmword ptr [rcx+10h], xmm0
0x140002b28  add     rcx, 40h ; '@'
0x140002b2c  dec     r8
0x140002b2f  movaps  xmmword ptr [rcx-20h], xmm0
0x140002b33  movaps  xmmword ptr [rcx-10h], xmm0
0x140002b37  jnz     short loc_140002B21
0x140002b39  movaps  xmmword ptr [r9], xmm0
0x140002b3d  movaps  xmmword ptr [r9+10h], xmm0
0x140002b42  movaps  xmmword ptr [r9+20h], xmm0
0x140002b47  movups  xmmword ptr [rdx], xmm0
0x140002b4a  retn
0x140002b50  cmp     r8, 10h
0x140002b54  jb      short loc_140002B80
0x140002b56  lea     r9, [r8+rcx-10h]
0x140002b5b  and     r8, 20h
0x140002b5f  movups  xmmword ptr [rcx], xmm0
0x140002b62  shr     r8, 1
0x140002b65  movups  xmmword ptr [r9], xmm0
0x140002b69  movups  xmmword ptr [rcx+r8], xmm0
0x140002b6e  neg     r8
0x140002b71  movups  xmmword ptr [r9+r8], xmm0
0x140002b76  retn
0x140002b80  cmp     r8, 4
0x140002b84  jb      short loc_140002BB0
0x140002b86  lea     r9, [r8+rcx-4]
0x140002b8b  and     r8, 8
0x140002b8f  mov     [rcx], edx
0x140002b91  shr     r8, 1
0x140002b94  mov     [r9], edx
0x140002b97  mov     [rcx+r8], edx
0x140002b9b  neg     r8
0x140002b9e  mov     [r9+r8], edx
0x140002ba2  retn
0x140002bb0  test    r8, r8
0x140002bb3  jz      short locret_140002BC6
0x140002bb5  mov     [rcx], dl
0x140002bb7  lea     r9, [rcx+r8-2]
0x140002bbc  cmp     r8, 1
0x140002bc0  jz      short locret_140002BC6
0x140002bc2  mov     [r9], dx
0x140002bc6  retn
```
