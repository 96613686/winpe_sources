# av_rescale_rnd

- ea: `0x180044120`
- end: `0x180044315`
- name: `av_rescale_rnd`
- size: `501`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180040560`
- `0x180043d80`
- `0x180043ef0`
- `0x180043f00`
- `0x1800440c0`
- `0x1800440f0`
- `0x180044120`
- `0x18004d950`

## callees

- `0x180044120`

## pseudocode

```c
__int64 __fastcall av_rescale_rnd(unsigned __int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned __int64 v6; // r9
  unsigned __int64 v8; // rcx
  __int64 v10; // rcx
  int v11; // r8d
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rbp
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rdx

  v6 = 0;
  if ( a3 <= 0 || a2 < 0 || (a4 & 0xFFFFDFFF) > 5 || (a4 & 0xFFFFDFFF) == 4 )
    return 0x8000000000000000uLL;
  if ( (a4 & 0x2000) != 0 )
  {
    if ( a1 + 0x7FFFFFFFFFFFFFFFLL > 0xFFFFFFFFFFFFFFFDuLL )
      return a1;
    a4 -= 0x2000;
  }
  if ( (a1 & 0x8000000000000000uLL) == 0LL )
  {
    if ( a4 == 5 )
    {
      v6 = (unsigned __int64)a3 >> 1;
    }
    else if ( (a4 & 1) != 0 )
    {
      v6 = a3 - 1;
    }
    if ( a2 > 0x7FFFFFFF || a3 > 0x7FFFFFFF )
    {
      v11 = 63;
      v12 = HIDWORD(a1) * (unsigned int)a2 + HIDWORD(a2) * (unsigned int)a1;
      v13 = (unsigned int)a1 * (unsigned __int64)(unsigned int)a2 + (v12 << 32);
      v14 = v13 + v6;
      v15 = HIDWORD(v12) + HIDWORD(a1) * HIDWORD(a2) + (v13 < v12 << 32) + (unsigned __int64)(v13 + v6 < v6);
      do
      {
        v17 = 2 * v12;
        v12 = 2 * v12 + 1;
        v18 = ((v14 >> v11) & 1) + 2 * v15;
        v16 = v18;
        if ( a3 > v18 )
          v12 = v17;
        v15 = v18 - a3;
        if ( a3 > v16 )
          v15 = v16;
        --v11;
      }
      while ( v11 >= 0 );
      if ( v12 <= 0x7FFFFFFFFFFFFFFFLL )
      {
        _mm_lfence();
        return v12;
      }
    }
    else
    {
      if ( (__int64)a1 <= 0x7FFFFFFF )
      {
        _mm_lfence();
        return (__int64)(v6 + a2 * a1) / a3;
      }
      v10 = a1 / a3;
      if ( (__int64)(a1 / a3) < 0x7FFFFFFF
        || !a2
        || v10 <= (0x7FFFFFFFFFFFFFFFLL - (__int64)(v6 + a2 * (a1 % a3)) / a3) / a2 )
      {
        _mm_lfence();
        return (__int64)(v6 + a2 * (a1 % a3)) / a3 + a2 * v10;
      }
    }
    return 0x8000000000000000uLL;
  }
  _mm_lfence();
  v8 = 0x8000000000000001uLL;
  if ( a1 != 0x8000000000000000uLL && a1 != 0x8000000000000001uLL )
    v8 = a1;
  return -av_rescale_rnd(-(__int64)v8, a2, a3, a4 ^ (a4 >> 1) & 1u);
}

```

## disassembly

```asm
0x180044120  mov     [rsp+arg_0], rbx
0x180044125  mov     [rsp+arg_8], rbp
0x18004412a  mov     [rsp+arg_10], rsi
0x18004412f  push    rdi
0x180044130  sub     rsp, 20h
0x180044134  mov     ebx, r9d
0x180044137  mov     rdi, r8
0x18004413a  xor     r9d, r9d
0x18004413d  mov     r11, rdx
0x180044140  mov     r10, rcx
0x180044143  test    r8, r8
0x180044146  jle     loc_1800442F6
0x18004414c  test    rdx, rdx
0x18004414f  js      loc_1800442F6
0x180044155  mov     eax, ebx
0x180044157  btr     eax, 0Dh
0x18004415b  cmp     eax, 5
0x18004415e  ja      loc_1800442F6
0x180044164  mov     eax, ebx
0x180044166  btr     eax, 0Dh
0x18004416a  cmp     eax, 4
0x18004416d  jz      loc_1800442F6
0x180044173  mov     ecx, 2000h
0x180044178  mov     rsi, 7FFFFFFFFFFFFFFFh
0x180044182  test    ecx, ebx
0x180044184  jz      short loc_180044192
0x180044186  lea     rax, [r10+rsi]
0x18004418a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004418e  ja      short loc_1800441C8
0x180044190  sub     ebx, ecx
0x180044192  test    r10, r10
0x180044195  jns     short loc_1800441D0
0x180044197  lfence
0x18004419a  mov     r9d, ebx
0x18004419d  mov     rcx, 8000000000000001h
0x1800441a7  sar     r9d, 1
0x1800441aa  and     r9d, 1
0x1800441ae  xor     r9d, ebx
0x1800441b1  cmp     r10, rcx
0x1800441b4  cmovg   rcx, r10
0x1800441b8  neg     rcx
0x1800441bb  call    av_rescale_rnd
0x1800441c0  neg     rax
0x1800441c3  jmp     loc_180044300
0x1800441c8  mov     rax, r10
0x1800441cb  jmp     loc_180044300
0x1800441d0  cmp     ebx, 5
0x1800441d3  jnz     short loc_1800441DD
0x1800441d5  mov     r9, rdi
0x1800441d8  shr     r9, 1
0x1800441db  jmp     short loc_1800441E6
0x1800441dd  test    bl, 1
0x1800441e0  jz      short loc_1800441E6
0x1800441e2  lea     r9, [r8-1]
0x1800441e6  mov     ebx, 7FFFFFFFh
0x1800441eb  cmp     r11, rbx
0x1800441ee  jg      short loc_180044260
0x1800441f0  cmp     rdi, rbx
0x1800441f3  jg      short loc_180044260
0x1800441f5  cmp     r10, rbx
0x1800441f8  jg      short loc_18004420F
0x1800441fa  lfence
0x1800441fd  imul    r10, r11
0x180044201  lea     rax, [r9+r10]
0x180044205  cqo
0x180044207  idiv    rdi
0x18004420a  jmp     loc_180044300
0x18004420f  xor     edx, edx
0x180044211  mov     rax, r10
0x180044214  div     rdi
0x180044217  xor     edx, edx
0x180044219  mov     rcx, rax
0x18004421c  mov     rax, r10
0x18004421f  div     rdi
0x180044222  imul    rdx, r11
0x180044226  lea     rax, [r9+rdx]
0x18004422a  cqo
0x18004422c  idiv    rdi
0x18004422f  mov     r8, rax
0x180044232  cmp     rcx, rbx
0x180044235  jl      short loc_180044250
0x180044237  test    r11, r11
0x18004423a  jz      short loc_180044250
0x18004423c  sub     rsi, rax
0x18004423f  mov     rax, rsi
0x180044242  cqo
0x180044244  idiv    r11
0x180044247  cmp     rcx, rax
0x18004424a  jg      loc_1800442F6
0x180044250  lfence
0x180044253  imul    rcx, r11
0x180044257  lea     rax, [r8+rcx]
0x18004425b  jmp     loc_180044300
0x180044260  mov     r8d, r10d
0x180044263  shr     r10, 20h
0x180044267  mov     ebx, r8d
0x18004426a  mov     edx, r11d
0x18004426d  mov     eax, edx
0x18004426f  shr     r11, 20h
0x180044273  imul    rdx, r8
0x180044277  imul    rax, r10
0x18004427b  imul    rbx, r11
0x18004427f  mov     r8d, 3Fh ; '?'
0x180044285  add     rbx, rax
0x180044288  mov     rcx, rbx
0x18004428b  shl     rcx, 20h
0x18004428f  lea     rax, [rdx+rcx]
0x180044293  xor     edx, edx
0x180044295  lea     rbp, [rax+r9]
0x180044299  cmp     rbp, r9
0x18004429c  setb    dl
0x18004429f  cmp     rax, rcx
0x1800442a2  mov     rax, rbx
0x1800442a5  adc     rdx, 0
0x1800442a9  shr     rax, 20h
0x1800442ad  imul    r11, r10
0x1800442b1  add     rdx, r11
0x1800442b4  add     rdx, rax
0x1800442b7  mov     ecx, r8d
0x1800442ba  mov     rax, rbp
0x1800442bd  shr     rax, cl
0x1800442c0  and     eax, 1
0x1800442c3  lea     rcx, [rax+rdx*2]
0x1800442c7  cmp     rdi, rcx
0x1800442ca  lea     rax, [rbx+rbx]
0x1800442ce  lea     rbx, [rax+1]
0x1800442d2  mov     rdx, rcx
0x1800442d5  cmova   rbx, rax
0x1800442d9  sub     rdx, rdi
0x1800442dc  cmp     rdi, rcx
0x1800442df  cmova   rdx, rcx
0x1800442e3  sub     r8d, 1
0x1800442e7  jns     short loc_1800442B7
0x1800442e9  cmp     rbx, rsi
0x1800442ec  ja      short loc_1800442F6
0x1800442ee  lfence
0x1800442f1  mov     rax, rbx
0x1800442f4  jmp     short loc_180044300
0x1800442f6  mov     rax, 8000000000000000h
0x180044300  mov     rbx, [rsp+28h+arg_0]
0x180044305  mov     rbp, [rsp+28h+arg_8]
0x18004430a  mov     rsi, [rsp+28h+arg_10]
0x18004430f  add     rsp, 20h
0x180044313  pop     rdi
0x180044314  retn
```
