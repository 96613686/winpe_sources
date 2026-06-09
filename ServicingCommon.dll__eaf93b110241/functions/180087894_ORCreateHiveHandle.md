# ORCreateHiveHandle

- ea: `0x180087894`
- end: `0x180087a97`
- name: `ORCreateHiveHandle`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180086410`

## callees

- `0x180033760`
- `0x1800862ec`
- `0x180087894`
- `0x180087aa0`
- `0x180099cb0`
- `0x18009a070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180087921`
- `KERNEL32!GetLastError` at `0x180087921`
- `KERNEL32!DeleteCriticalSection` at `0x180087a68`
- `KERNEL32!DeleteCriticalSection` at `0x180087a68`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180087911`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180087911`

## pseudocode

```c
__int64 __fastcall ORCreateHiveHandle(__int64 a1, unsigned __int64 a2, _WORD *a3, _QWORD *a4)
{
  char *v8; // rax
  char *v9; // rbx
  DWORD LastError; // edi
  __int64 v11; // rcx
  unsigned __int16 *v12; // rdx
  size_t v13; // rdi
  void *v14; // rax
  unsigned int v15; // r9d
  __m128i v16; // xmm3
  __m128i v17; // xmm2
  __int64 v18; // r8
  unsigned __int64 v19; // xmm0_8
  __int64 v20; // rax

  *a4 = 0;
  v8 = (char *)aligned_malloc(0x118u, 0x10u);
  v9 = v8;
  if ( !v8 )
    return 8;
  memset(v8, 0, 0x118u);
  *(_DWORD *)v9 = -1092567328;
  *((_QWORD *)v9 + 2) = a1;
  *((_DWORD *)v9 + 6) = *(_DWORD *)(a1 + 24) - 4096 + (*(_DWORD *)(a1 + 20) << 12);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v9 + 136), 0x80000400) )
  {
    LastError = GetLastError();
LABEL_19:
    ORFree(*((_QWORD *)v9 + 5));
    ORFree(v9);
    return LastError;
  }
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    if ( (int)RtlULongPtrToUShort(2 * v11, v9 + 32) < 0 )
    {
      LastError = 87;
LABEL_18:
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 136));
      goto LABEL_19;
    }
    v13 = *v12;
    *((_WORD *)v9 + 17) = v13;
    v14 = aligned_malloc((unsigned int)v13, 0x10u);
    *((_QWORD *)v9 + 5) = v14;
    if ( !v14 )
    {
      LastError = 8;
      goto LABEL_18;
    }
    memmove(v14, a3, v13);
  }
  if ( a2 > 0xFFFFFFFF )
  {
    *((_DWORD *)v9 + 12) = -1;
    LastError = 534;
    goto LABEL_18;
  }
  *((_DWORD *)v9 + 12) = a2;
  *((_QWORD *)v9 + 11) = v9 + 80;
  v15 = 0;
  *((_QWORD *)v9 + 10) = v9 + 80;
  v16 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)(v9 + 184), (__m128i)(unsigned __int64)(v9 + 184));
  do
  {
    v17 = _mm_add_epi64(
            _mm_slli_epi64(
              _mm_unpacklo_epi32(
                _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v15), 0), _mm_loadl_epi64((const __m128i *)&_xmm)),
                (__m128i)0LL),
              4u),
            v16);
    v18 = 2LL * v15;
    v19 = _mm_srli_si128(v17, 8).m128i_u64[0];
    *(_QWORD *)&v9[16 * v15 + 192] = v17.m128i_i64[0];
    v20 = v15 + 1;
    v15 += 2;
    *(_QWORD *)&v9[8 * v18 + 184] = v17.m128i_i64[0];
    *(_QWORD *)&v9[16 * v20 + 192] = v19;
    *(_QWORD *)&v9[16 * v20 + 184] = v19;
  }
  while ( v15 < 6 );
  *a4 = v9;
  *((_QWORD *)v9 + 13) = v9 + 96;
  *((_QWORD *)v9 + 12) = v9 + 96;
  *((_QWORD *)v9 + 15) = v9 + 112;
  *((_QWORD *)v9 + 14) = v9 + 112;
  *((_QWORD *)v9 + 9) = v9 + 64;
  *((_QWORD *)v9 + 8) = v9 + 64;
  return 0;
}

```

## disassembly

```asm
0x180087894  push    rbx
0x180087896  push    rbp
0x180087897  push    rsi
0x180087898  push    rdi
0x180087899  push    r12
0x18008789b  push    r14
0x18008789d  push    r15
0x18008789f  sub     rsp, 20h
0x1800878a3  xor     r12d, r12d
0x1800878a6  mov     rbp, rdx
0x1800878a9  mov     rdi, rcx
0x1800878ac  mov     [r9], r12
0x1800878af  mov     r15d, 118h
0x1800878b5  mov     r14, r9
0x1800878b8  mov     ecx, r15d; Size
0x1800878bb  mov     rsi, r8
0x1800878be  lea     edx, [r12+10h]; Alignment
0x1800878c3  call    _aligned_malloc
0x1800878c8  mov     rbx, rax
0x1800878cb  test    rax, rax
0x1800878ce  jnz     short loc_1800878D8
0x1800878d0  lea     edi, [rax+8]
0x1800878d3  jmp     loc_180087A85
0x1800878d8  mov     r8, r15; Size
0x1800878db  xor     edx, edx; Val
0x1800878dd  mov     rcx, rbx; void *
0x1800878e0  call    memset
0x1800878e5  mov     dword ptr [rbx], 0BEE0BEE0h
0x1800878eb  lea     r15, [rbx+88h]
0x1800878f2  mov     [rbx+10h], rdi
0x1800878f6  mov     edx, 80000400h; dwSpinCount
0x1800878fb  mov     ecx, [rdi+14h]
0x1800878fe  mov     eax, [rdi+18h]
0x180087901  shl     ecx, 0Ch
0x180087904  add     eax, 0FFFFF000h
0x180087909  add     ecx, eax
0x18008790b  mov     [rbx+18h], ecx
0x18008790e  mov     rcx, r15; lpCriticalSection
0x180087911  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180087918  nop     dword ptr [rax+rax+00h]
0x18008791d  test    eax, eax
0x18008791f  jnz     short loc_180087934
0x180087921  call    cs:__imp_GetLastError
0x180087928  nop     dword ptr [rax+rax+00h]
0x18008792d  mov     edi, eax
0x18008792f  jmp     loc_180087A74
0x180087934  test    rsi, rsi
0x180087937  jz      short loc_180087993
0x180087939  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008793d  inc     rcx
0x180087940  cmp     [rsi+rcx*2], r12w
0x180087945  jnz     short loc_18008793D
0x180087947  lea     rdx, [rbx+20h]
0x18008794b  add     rcx, rcx
0x18008794e  call    RtlULongPtrToUShort
0x180087953  test    eax, eax
0x180087955  jns     short loc_180087961
0x180087957  mov     edi, 57h ; 'W'
0x18008795c  jmp     loc_180087A65
0x180087961  movzx   edi, word ptr [rdx]
0x180087964  mov     edx, 10h; Alignment
0x180087969  mov     ecx, edi; Size
0x18008796b  mov     [rbx+22h], di
0x18008796f  call    _aligned_malloc
0x180087974  mov     [rbx+28h], rax
0x180087978  test    rax, rax
0x18008797b  jnz     short loc_180087985
0x18008797d  lea     edi, [rax+8]
0x180087980  jmp     loc_180087A65
0x180087985  mov     r8, rdi; Size
0x180087988  mov     rdx, rsi; Src
0x18008798b  mov     rcx, rax; void *
0x18008798e  call    memmove
0x180087993  mov     eax, 0FFFFFFFFh
0x180087998  cmp     rbp, rax
0x18008799b  ja      loc_180087A5D
0x1800879a1  lea     rax, [rbx+50h]
0x1800879a5  mov     [rbx+30h], ebp
0x1800879a8  mov     [rax+8], rax
0x1800879ac  mov     r9d, r12d
0x1800879af  mov     [rax], rax
0x1800879b2  lea     rax, [rbx+0B8h]
0x1800879b9  movq    xmm3, rax
0x1800879be  punpcklqdq xmm3, xmm3
0x1800879c2  movq    xmm0, qword ptr cs:__xmm@00000003000000020000000100000000
0x1800879ca  xorps   xmm1, xmm1
0x1800879cd  mov     r8d, r9d
0x1800879d0  movd    xmm2, r9d
0x1800879d5  pshufd  xmm2, xmm2, 0
0x1800879da  paddd   xmm2, xmm0
0x1800879de  lea     rax, [r8+0Ch]
0x1800879e2  punpckldq xmm2, xmm1
0x1800879e6  add     rax, rax
0x1800879e9  psllq   xmm2, 4
0x1800879ee  paddq   xmm2, xmm3
0x1800879f2  add     r8, r8
0x1800879f5  movdqa  xmm0, xmm2
0x1800879f9  psrldq  xmm0, 8
0x1800879fe  movq    qword ptr [rbx+rax*8], xmm2
0x180087a03  lea     eax, [r9+1]
0x180087a07  mov     edx, eax
0x180087a09  add     r9d, 2
0x180087a0d  add     rax, 0Ch
0x180087a11  movq    qword ptr [rbx+r8*8+0B8h], xmm2
0x180087a1b  add     rax, rax
0x180087a1e  add     rdx, rdx
0x180087a21  movq    qword ptr [rbx+rax*8], xmm0
0x180087a26  movq    qword ptr [rbx+rdx*8+0B8h], xmm0
0x180087a2f  cmp     r9d, 6
0x180087a33  jb      short loc_1800879C2
0x180087a35  lea     rax, [rbx+60h]
0x180087a39  mov     [r14], rbx
0x180087a3c  mov     [rax+8], rax
0x180087a40  mov     [rax], rax
0x180087a43  lea     rax, [rbx+70h]
0x180087a47  mov     [rax+8], rax
0x180087a4b  mov     [rax], rax
0x180087a4e  lea     rax, [rbx+40h]
0x180087a52  mov     [rax+8], rax
0x180087a56  mov     [rax], rax
0x180087a59  xor     eax, eax
0x180087a5b  jmp     short loc_180087A87
0x180087a5d  mov     [rbx+30h], eax
0x180087a60  mov     edi, 216h
0x180087a65  mov     rcx, r15; lpCriticalSection
0x180087a68  call    cs:__imp_DeleteCriticalSection
0x180087a6f  nop     dword ptr [rax+rax+00h]
0x180087a74  mov     rcx, [rbx+28h]
0x180087a78  call    ORFree
0x180087a7d  mov     rcx, rbx
0x180087a80  call    ORFree
0x180087a85  mov     eax, edi
0x180087a87  add     rsp, 20h
0x180087a8b  pop     r15
0x180087a8d  pop     r14
0x180087a8f  pop     r12
0x180087a91  pop     rdi
0x180087a92  pop     rsi
0x180087a93  pop     rbp
0x180087a94  pop     rbx
0x180087a95  retn
```
