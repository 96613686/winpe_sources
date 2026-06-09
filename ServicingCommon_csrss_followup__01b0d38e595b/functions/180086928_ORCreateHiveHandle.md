# ORCreateHiveHandle

- ea: `0x180086928`
- end: `0x180086b2b`
- name: `ORCreateHiveHandle`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800854a4`

## callees

- `0x180037670`
- `0x180085380`
- `0x180086928`
- `0x180086b34`
- `0x180097e20`
- `0x1800981e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800869b5`
- `KERNEL32!GetLastError` at `0x1800869b5`
- `KERNEL32!DeleteCriticalSection` at `0x180086afc`
- `KERNEL32!DeleteCriticalSection` at `0x180086afc`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800869a5`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800869a5`

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
0x180086928  push    rbx
0x18008692a  push    rbp
0x18008692b  push    rsi
0x18008692c  push    rdi
0x18008692d  push    r12
0x18008692f  push    r14
0x180086931  push    r15
0x180086933  sub     rsp, 20h
0x180086937  xor     r12d, r12d
0x18008693a  mov     rbp, rdx
0x18008693d  mov     rdi, rcx
0x180086940  mov     [r9], r12
0x180086943  mov     r15d, 118h
0x180086949  mov     r14, r9
0x18008694c  mov     ecx, r15d; Size
0x18008694f  mov     rsi, r8
0x180086952  lea     edx, [r12+10h]; Alignment
0x180086957  call    _aligned_malloc
0x18008695c  mov     rbx, rax
0x18008695f  test    rax, rax
0x180086962  jnz     short loc_18008696C
0x180086964  lea     edi, [rax+8]
0x180086967  jmp     loc_180086B19
0x18008696c  mov     r8, r15; Size
0x18008696f  xor     edx, edx; Val
0x180086971  mov     rcx, rbx; void *
0x180086974  call    memset
0x180086979  mov     dword ptr [rbx], 0BEE0BEE0h
0x18008697f  lea     r15, [rbx+88h]
0x180086986  mov     [rbx+10h], rdi
0x18008698a  mov     edx, 80000400h; dwSpinCount
0x18008698f  mov     ecx, [rdi+14h]
0x180086992  mov     eax, [rdi+18h]
0x180086995  shl     ecx, 0Ch
0x180086998  add     eax, 0FFFFF000h
0x18008699d  add     ecx, eax
0x18008699f  mov     [rbx+18h], ecx
0x1800869a2  mov     rcx, r15; lpCriticalSection
0x1800869a5  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800869ac  nop     dword ptr [rax+rax+00h]
0x1800869b1  test    eax, eax
0x1800869b3  jnz     short loc_1800869C8
0x1800869b5  call    cs:__imp_GetLastError
0x1800869bc  nop     dword ptr [rax+rax+00h]
0x1800869c1  mov     edi, eax
0x1800869c3  jmp     loc_180086B08
0x1800869c8  test    rsi, rsi
0x1800869cb  jz      short loc_180086A27
0x1800869cd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800869d1  inc     rcx
0x1800869d4  cmp     [rsi+rcx*2], r12w
0x1800869d9  jnz     short loc_1800869D1
0x1800869db  lea     rdx, [rbx+20h]
0x1800869df  add     rcx, rcx
0x1800869e2  call    RtlULongPtrToUShort
0x1800869e7  test    eax, eax
0x1800869e9  jns     short loc_1800869F5
0x1800869eb  mov     edi, 57h ; 'W'
0x1800869f0  jmp     loc_180086AF9
0x1800869f5  movzx   edi, word ptr [rdx]
0x1800869f8  mov     edx, 10h; Alignment
0x1800869fd  mov     ecx, edi; Size
0x1800869ff  mov     [rbx+22h], di
0x180086a03  call    _aligned_malloc
0x180086a08  mov     [rbx+28h], rax
0x180086a0c  test    rax, rax
0x180086a0f  jnz     short loc_180086A19
0x180086a11  lea     edi, [rax+8]
0x180086a14  jmp     loc_180086AF9
0x180086a19  mov     r8, rdi; Size
0x180086a1c  mov     rdx, rsi; Src
0x180086a1f  mov     rcx, rax; void *
0x180086a22  call    memmove
0x180086a27  mov     eax, 0FFFFFFFFh
0x180086a2c  cmp     rbp, rax
0x180086a2f  ja      loc_180086AF1
0x180086a35  lea     rax, [rbx+50h]
0x180086a39  mov     [rbx+30h], ebp
0x180086a3c  mov     [rax+8], rax
0x180086a40  mov     r9d, r12d
0x180086a43  mov     [rax], rax
0x180086a46  lea     rax, [rbx+0B8h]
0x180086a4d  movq    xmm3, rax
0x180086a52  punpcklqdq xmm3, xmm3
0x180086a56  movq    xmm0, qword ptr cs:__xmm@00000003000000020000000100000000
0x180086a5e  xorps   xmm1, xmm1
0x180086a61  mov     r8d, r9d
0x180086a64  movd    xmm2, r9d
0x180086a69  pshufd  xmm2, xmm2, 0
0x180086a6e  paddd   xmm2, xmm0
0x180086a72  lea     rax, [r8+0Ch]
0x180086a76  punpckldq xmm2, xmm1
0x180086a7a  add     rax, rax
0x180086a7d  psllq   xmm2, 4
0x180086a82  paddq   xmm2, xmm3
0x180086a86  add     r8, r8
0x180086a89  movdqa  xmm0, xmm2
0x180086a8d  psrldq  xmm0, 8
0x180086a92  movq    qword ptr [rbx+rax*8], xmm2
0x180086a97  lea     eax, [r9+1]
0x180086a9b  mov     edx, eax
0x180086a9d  add     r9d, 2
0x180086aa1  add     rax, 0Ch
0x180086aa5  movq    qword ptr [rbx+r8*8+0B8h], xmm2
0x180086aaf  add     rax, rax
0x180086ab2  add     rdx, rdx
0x180086ab5  movq    qword ptr [rbx+rax*8], xmm0
0x180086aba  movq    qword ptr [rbx+rdx*8+0B8h], xmm0
0x180086ac3  cmp     r9d, 6
0x180086ac7  jb      short loc_180086A56
0x180086ac9  lea     rax, [rbx+60h]
0x180086acd  mov     [r14], rbx
0x180086ad0  mov     [rax+8], rax
0x180086ad4  mov     [rax], rax
0x180086ad7  lea     rax, [rbx+70h]
0x180086adb  mov     [rax+8], rax
0x180086adf  mov     [rax], rax
0x180086ae2  lea     rax, [rbx+40h]
0x180086ae6  mov     [rax+8], rax
0x180086aea  mov     [rax], rax
0x180086aed  xor     eax, eax
0x180086aef  jmp     short loc_180086B1B
0x180086af1  mov     [rbx+30h], eax
0x180086af4  mov     edi, 216h
0x180086af9  mov     rcx, r15; lpCriticalSection
0x180086afc  call    cs:__imp_DeleteCriticalSection
0x180086b03  nop     dword ptr [rax+rax+00h]
0x180086b08  mov     rcx, [rbx+28h]
0x180086b0c  call    ORFree
0x180086b11  mov     rcx, rbx
0x180086b14  call    ORFree
0x180086b19  mov     eax, edi
0x180086b1b  add     rsp, 20h
0x180086b1f  pop     r15
0x180086b21  pop     r14
0x180086b23  pop     r12
0x180086b25  pop     rdi
0x180086b26  pop     rsi
0x180086b27  pop     rbp
0x180086b28  pop     rbx
0x180086b29  retn
```
