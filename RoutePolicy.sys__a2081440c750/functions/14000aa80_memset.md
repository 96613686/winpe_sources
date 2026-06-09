# memset

- ea: `0x14000aa80`
- end: `0x14000ab87`
- name: `memset`
- size: `263`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e68`
- `0x140002ff0`
- `0x140005610`
- `0x140005b60`
- `0x140009b00`
- `0x14000b020`
- `0x1400174bc`
- `0x140017580`
- `0x140017758`
- `0x140017ca4`
- `0x14001870c`
- `0x140018880`

## callees

- `0x14000aa80`
- `0x14000abc0`

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
0x14000aa80  mov     rax, rcx
0x14000aa83  movzx   edx, dl
0x14000aa86  mov     r9, 101010101010101h
0x14000aa90  imul    rdx, r9
0x14000aa94  movq    xmm0, rdx
0x14000aa99  movlhps xmm0, xmm0
0x14000aa9c  cmp     r8, 40h ; '@'
0x14000aaa0  jb      short loc_14000AB10
0x14000aaa2  test    cs:__isa_info, 2
0x14000aaa9  jz      short loc_14000AAB8
0x14000aaab  cmp     r8, 320h
0x14000aab2  jnb     __memset_repmovs
0x14000aab8  movups  xmmword ptr [rcx], xmm0
0x14000aabb  add     r8, rcx
0x14000aabe  add     rcx, 10h
0x14000aac2  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000aac6  sub     r8, rcx
0x14000aac9  cmp     r8, 40h ; '@'
0x14000aacd  jb      short loc_14000AB16
0x14000aacf  lea     rdx, [rcx+r8-10h]
0x14000aad4  lea     r9, [rcx+r8-30h]
0x14000aad9  and     r9, 0FFFFFFFFFFFFFFF0h
0x14000aadd  shr     r8, 6
0x14000aae1  movaps  xmmword ptr [rcx], xmm0
0x14000aae4  movaps  xmmword ptr [rcx+10h], xmm0
0x14000aae8  add     rcx, 40h ; '@'
0x14000aaec  dec     r8
0x14000aaef  movaps  xmmword ptr [rcx-20h], xmm0
0x14000aaf3  movaps  xmmword ptr [rcx-10h], xmm0
0x14000aaf7  jnz     short loc_14000AAE1
0x14000aaf9  movaps  xmmword ptr [r9], xmm0
0x14000aafd  movaps  xmmword ptr [r9+10h], xmm0
0x14000ab02  movaps  xmmword ptr [r9+20h], xmm0
0x14000ab07  movups  xmmword ptr [rdx], xmm0
0x14000ab0a  retn
0x14000ab10  cmp     r8, 10h
0x14000ab14  jb      short loc_14000AB40
0x14000ab16  lea     r9, [r8+rcx-10h]
0x14000ab1b  and     r8, 20h
0x14000ab1f  movups  xmmword ptr [rcx], xmm0
0x14000ab22  shr     r8, 1
0x14000ab25  movups  xmmword ptr [r9], xmm0
0x14000ab29  movups  xmmword ptr [rcx+r8], xmm0
0x14000ab2e  neg     r8
0x14000ab31  movups  xmmword ptr [r9+r8], xmm0
0x14000ab36  retn
0x14000ab40  cmp     r8, 4
0x14000ab44  jb      short loc_14000AB70
0x14000ab46  lea     r9, [r8+rcx-4]
0x14000ab4b  and     r8, 8
0x14000ab4f  mov     [rcx], edx
0x14000ab51  shr     r8, 1
0x14000ab54  mov     [r9], edx
0x14000ab57  mov     [rcx+r8], edx
0x14000ab5b  neg     r8
0x14000ab5e  mov     [r9+r8], edx
0x14000ab62  retn
0x14000ab70  test    r8, r8
0x14000ab73  jz      short locret_14000AB86
0x14000ab75  mov     [rcx], dl
0x14000ab77  lea     r9, [rcx+r8-2]
0x14000ab7c  cmp     r8, 1
0x14000ab80  jz      short locret_14000AB86
0x14000ab82  mov     [r9], dx
0x14000ab86  retn
```
