# init_compression_memory

- ea: `0x140004568`
- end: `0x140004762`
- name: `init_compression_memory`
- size: `506`
- prototype: `void *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c888`
- `0x140011270`

## callees

- `0x14000640c`
- `0x14000c754`
- `0x1400119c0`

## pseudocode

```c
void *__fastcall init_compression_memory(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  __m128i v4; // xmm1
  int v5; // ecx
  void *v6; // rcx
  unsigned int mem_window_alloc_size; // eax

  memset(*(void **)(a1 + 16), 0, 0x40000u);
  v2 = *(unsigned int *)(a1 + 8);
  v3 = *(_QWORD *)(a1 + 17272);
  v4 = _mm_loadu_si128((const __m128i *)(a1 + 17280));
  *(_DWORD *)(a1 + 1144) = v2;
  *(_QWORD *)a1 = v3 - v2;
  *(_DWORD *)(a1 + 100) = 1;
  *(_DWORD *)(a1 + 104) = 1;
  *(__m128i *)(a1 + 24) = _mm_sub_epi64(
                            v4,
                            _mm_unpacklo_epi64((__m128i)(unsigned __int64)(4 * v2), (__m128i)(unsigned __int64)(4 * v2)));
  *(_DWORD *)(a1 + 88) = 1;
  *(_DWORD *)(a1 + 92) = 1;
  *(_DWORD *)(a1 + 96) = 1;
  *(_DWORD *)(a1 + 108) = 1;
  LODWORD(v3) = *(_DWORD *)(a1 + 2208);
  *(_DWORD *)(a1 + 2204) = v2;
  *(_BYTE *)(a1 + 2477) = 1;
  *(_DWORD *)(a1 + 2480) = 1;
  *(_BYTE *)(a1 + 44) = 32;
  *(_DWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  memset((void *)(a1 + 14760), 0, 8 * (int)v3 + 256);
  memset((void *)(a1 + 16956), 0, 0xF9u);
  memset((void *)(a1 + 9608), 8, 0x100u);
  memset((void *)(a1 + 9864), 9, 8 * *(_DWORD *)(a1 + 2208));
  memset((void *)(a1 + 10309), 6, 0xF9u);
  *(_QWORD *)(a1 + 17254) = 0x303030303030303LL;
  prevent_far_matches(a1);
  v5 = *(_DWORD *)(a1 + 1144);
  *(_DWORD *)(a1 + 2496) = v5;
  *(_DWORD *)(a1 + 2492) = v5;
  v6 = *(void **)(a1 + 80);
  *(_DWORD *)(a1 + 2200) = 0;
  *(_DWORD *)(a1 + 2484) = 1;
  memset(v6, 0, 0x2000u);
  *(_DWORD *)(a1 + 88) = 1;
  *(_DWORD *)(a1 + 92) = 1;
  *(_DWORD *)(a1 + 96) = 1;
  *(_QWORD *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 2220) = 0;
  *(_DWORD *)(a1 + 2516) = 0;
  *(_DWORD *)(a1 + 17296) = 0;
  memset((void *)(a1 + 10560), 0, 0xAF0u);
  memset((void *)(a1 + 15462), 0, 0x3E4u);
  *(_OWORD *)(a1 + 17206) = 0;
  *(_OWORD *)(a1 + 17222) = 0;
  mem_window_alloc_size = get_mem_window_alloc_size(a1);
  return memset(*(void **)(a1 + 17272), 0, mem_window_alloc_size);
}

```

## disassembly

```asm
0x140004568  mov     [rsp+arg_0], rbx
0x14000456d  mov     [rsp+arg_8], rdi
0x140004572  push    r14
0x140004574  sub     rsp, 20h
0x140004578  mov     rdi, rcx
0x14000457b  xor     edx, edx; Val
0x14000457d  mov     rcx, [rcx+10h]; void *
0x140004581  mov     r8d, 40000h; Size
0x140004587  call    memset
0x14000458c  mov     edx, [rdi+8]
0x14000458f  lea     rcx, [rdi+39A8h]; void *
0x140004596  mov     rax, [rdi+4378h]
0x14000459d  mov     r14d, 1
0x1400045a3  movdqu  xmm1, xmmword ptr [rdi+4380h]
0x1400045ab  mov     [rdi+478h], edx
0x1400045b1  sub     rax, rdx
0x1400045b4  mov     [rdi], rax
0x1400045b7  lea     rax, ds:0[rdx*4]
0x1400045bf  movq    xmm0, rax
0x1400045c4  mov     [rdi+64h], r14d
0x1400045c8  punpcklqdq xmm0, xmm0
0x1400045cc  psubq   xmm1, xmm0
0x1400045d0  mov     [rdi+68h], r14d
0x1400045d4  movdqu  xmmword ptr [rdi+18h], xmm1
0x1400045d9  mov     [rdi+58h], r14d
0x1400045dd  mov     [rdi+5Ch], r14d
0x1400045e1  mov     [rdi+60h], r14d
0x1400045e5  mov     [rdi+6Ch], r14d
0x1400045e9  mov     eax, [rdi+8A0h]
0x1400045ef  mov     [rdi+89Ch], edx
0x1400045f5  xor     edx, edx; Val
0x1400045f7  mov     [rdi+9ADh], r14b
0x1400045fe  mov     [rdi+9B0h], r14d
0x140004605  lea     eax, ds:100h[rax*8]
0x14000460c  mov     byte ptr [rdi+2Ch], 20h ; ' '
0x140004610  movsxd  r8, eax; Size
0x140004613  mov     dword ptr [rdi+28h], 0
0x14000461a  mov     dword ptr [rdi+30h], 0
0x140004621  call    memset
0x140004626  lea     rcx, [rdi+423Ch]; void *
0x14000462d  xor     edx, edx; Val
0x14000462f  mov     r8d, 0F9h; Size
0x140004635  call    memset
0x14000463a  lea     edx, [r14+7]; Val
0x14000463e  mov     r8d, 100h; Size
0x140004644  lea     rcx, [rdi+2588h]; void *
0x14000464b  call    memset
0x140004650  mov     eax, [rdi+8A0h]
0x140004656  lea     rcx, [rdi+2688h]; void *
0x14000465d  shl     eax, 3
0x140004660  lea     edx, [r14+8]; Val
0x140004664  movsxd  r8, eax; Size
0x140004667  call    memset
0x14000466c  lea     rcx, [rdi+2845h]; void *
0x140004673  mov     r8d, 0F9h; Size
0x140004679  lea     edx, [r14+5]; Val
0x14000467d  call    memset
0x140004682  mov     rax, 303030303030303h
0x14000468c  mov     rcx, rdi
0x14000468f  mov     [rdi+4366h], rax
0x140004696  call    prevent_far_matches
0x14000469b  mov     ecx, [rdi+478h]
0x1400046a1  xor     edx, edx; Val
0x1400046a3  mov     [rdi+9C0h], ecx
0x1400046a9  mov     r8d, 2000h; Size
0x1400046af  mov     [rdi+9BCh], ecx
0x1400046b5  mov     rcx, [rdi+50h]; void *
0x1400046b9  mov     dword ptr [rdi+898h], 0
0x1400046c3  mov     [rdi+9B4h], r14d
0x1400046ca  call    memset
0x1400046cf  mov     [rdi+58h], r14d
0x1400046d3  lea     rcx, [rdi+2940h]; void *
0x1400046da  mov     [rdi+5Ch], r14d
0x1400046de  xor     edx, edx; Val
0x1400046e0  mov     [rdi+60h], r14d
0x1400046e4  mov     r8d, 0AF0h; Size
0x1400046ea  mov     qword ptr [rdi+38h], 0
0x1400046f2  mov     byte ptr [rdi+8ACh], 0
0x1400046f9  mov     dword ptr [rdi+9D4h], 0
0x140004703  mov     dword ptr [rdi+4390h], 0
0x14000470d  call    memset
0x140004712  lea     rcx, [rdi+3C66h]; void *
0x140004719  xor     edx, edx; Val
0x14000471b  mov     r8d, 3E4h; Size
0x140004721  call    memset
0x140004726  xorps   xmm0, xmm0
0x140004729  mov     rcx, rdi
0x14000472c  movups  xmmword ptr [rdi+4336h], xmm0
0x140004733  movups  xmmword ptr [rdi+4346h], xmm0
0x14000473a  call    get_mem_window_alloc_size
0x14000473f  mov     rcx, [rdi+4378h]; void *
0x140004746  xor     edx, edx; Val
0x140004748  mov     r8d, eax; Size
0x14000474b  call    memset
0x140004750  mov     rbx, [rsp+28h+arg_0]
0x140004755  mov     rdi, [rsp+28h+arg_8]
0x14000475a  add     rsp, 20h
0x14000475e  pop     r14
0x140004760  retn
```
