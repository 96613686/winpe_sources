# memset

- ea: `0x140004fc0`
- end: `0x1400050c7`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x140002904`
- `0x140003adc`
- `0x140004820`
- `0x140004be0`
- `0x140007090`
- `0x140011a00`
- `0x140011fb4`
- `0x1400149a8`
- `0x140014b20`
- `0x1400150f0`
- `0x140018b60`
- `0x14001bbb4`
- `0x1400207f0`
- `0x14002184c`
- `0x140022edc`

## callees

- `0x140004fc0`
- `0x140005100`

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
0x140004fc0  mov     rax, rcx
0x140004fc3  movzx   edx, dl
0x140004fc6  mov     r9, 101010101010101h
0x140004fd0  imul    rdx, r9
0x140004fd4  movq    xmm0, rdx
0x140004fd9  movlhps xmm0, xmm0
0x140004fdc  cmp     r8, 40h ; '@'
0x140004fe0  jb      short loc_140005050
0x140004fe2  test    cs:__isa_info, 2
0x140004fe9  jz      short loc_140004FF8
0x140004feb  cmp     r8, 320h
0x140004ff2  jnb     __memset_repmovs
0x140004ff8  movups  xmmword ptr [rcx], xmm0
0x140004ffb  add     r8, rcx
0x140004ffe  add     rcx, 10h
0x140005002  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140005006  sub     r8, rcx
0x140005009  cmp     r8, 40h ; '@'
0x14000500d  jb      short loc_140005056
0x14000500f  lea     rdx, [rcx+r8-10h]
0x140005014  lea     r9, [rcx+r8-30h]
0x140005019  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000501d  shr     r8, 6
0x140005021  movaps  xmmword ptr [rcx], xmm0
0x140005024  movaps  xmmword ptr [rcx+10h], xmm0
0x140005028  add     rcx, 40h ; '@'
0x14000502c  dec     r8
0x14000502f  movaps  xmmword ptr [rcx-20h], xmm0
0x140005033  movaps  xmmword ptr [rcx-10h], xmm0
0x140005037  jnz     short loc_140005021
0x140005039  movaps  xmmword ptr [r9], xmm0
0x14000503d  movaps  xmmword ptr [r9+10h], xmm0
0x140005042  movaps  xmmword ptr [r9+20h], xmm0
0x140005047  movups  xmmword ptr [rdx], xmm0
0x14000504a  retn
0x140005050  cmp     r8, 10h
0x140005054  jb      short loc_140005080
0x140005056  lea     r9, [r8+rcx-10h]
0x14000505b  and     r8, 20h
0x14000505f  movups  xmmword ptr [rcx], xmm0
0x140005062  shr     r8, 1
0x140005065  movups  xmmword ptr [r9], xmm0
0x140005069  movups  xmmword ptr [rcx+r8], xmm0
0x14000506e  neg     r8
0x140005071  movups  xmmword ptr [r9+r8], xmm0
0x140005076  retn
0x140005080  cmp     r8, 4
0x140005084  jb      short loc_1400050B0
0x140005086  lea     r9, [r8+rcx-4]
0x14000508b  and     r8, 8
0x14000508f  mov     [rcx], edx
0x140005091  shr     r8, 1
0x140005094  mov     [r9], edx
0x140005097  mov     [rcx+r8], edx
0x14000509b  neg     r8
0x14000509e  mov     [r9+r8], edx
0x1400050a2  retn
0x1400050b0  test    r8, r8
0x1400050b3  jz      short locret_1400050C6
0x1400050b5  mov     [rcx], dl
0x1400050b7  lea     r9, [rcx+r8-2]
0x1400050bc  cmp     r8, 1
0x1400050c0  jz      short locret_1400050C6
0x1400050c2  mov     [r9], dx
0x1400050c6  retn
```
