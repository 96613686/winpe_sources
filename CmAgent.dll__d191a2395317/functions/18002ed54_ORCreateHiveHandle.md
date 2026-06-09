# ORCreateHiveHandle

- ea: `0x18002ed54`
- end: `0x18002eef0`
- name: `ORCreateHiveHandle`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002c164`

## callees

- `0x180002b28`
- `0x180002b34`
- `0x180002c48`
- `0x18002ed54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002edc9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002edc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002eebc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002eebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edd9`

## pseudocode

```c
__int64 __fastcall ORCreateHiveHandle(__int64 a1, unsigned __int64 a2, __int64 a3, _QWORD *a4)
{
  char *v7; // rax
  char *v8; // rbx
  DWORD LastError; // edi
  __int64 v10; // r9
  __m128i v11; // xmm3
  __int64 v12; // r8
  __m128i v13; // xmm2
  __int64 v14; // rax
  unsigned __int64 v15; // xmm0_8
  void *v17; // rcx

  *a4 = 0;
  v7 = (char *)o__aligned_malloc_0(0x118u, 0x10u);
  v8 = v7;
  if ( !v7 )
    return 8;
  memset_0(v7, 0, 0x118u);
  *((_QWORD *)v8 + 2) = a1;
  *(_DWORD *)v8 = -1092567328;
  *((_DWORD *)v8 + 6) = *(_DWORD *)(a1 + 24) - 4096 + (*(_DWORD *)(a1 + 20) << 12);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v8 + 136), 0x80000400) )
  {
    LastError = GetLastError();
LABEL_10:
    v17 = (void *)*((_QWORD *)v8 + 5);
    if ( v17 )
      aligned_free(v17);
    aligned_free(v8);
    return LastError;
  }
  if ( a2 > 0xFFFFFFFF )
  {
    *((_DWORD *)v8 + 12) = -1;
    DeleteCriticalSection((LPCRITICAL_SECTION)(v8 + 136));
    LastError = 534;
    goto LABEL_10;
  }
  *((_DWORD *)v8 + 12) = a2;
  *((_QWORD *)v8 + 11) = v8 + 80;
  v10 = 0;
  *((_QWORD *)v8 + 10) = v8 + 80;
  v11 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)(v8 + 184), (__m128i)(unsigned __int64)(v8 + 184));
  do
  {
    v12 = 2LL * (unsigned int)v10;
    v13 = _mm_add_epi64(
            _mm_slli_epi64(
              _mm_unpacklo_epi32(
                _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v10), 0), _mm_loadl_epi64((const __m128i *)&_xmm)),
                (__m128i)0LL),
              4u),
            v11);
    *(_QWORD *)&v8[16 * v10 + 192] = v13.m128i_i64[0];
    v14 = (unsigned int)(v10 + 1);
    v15 = _mm_srli_si128(v13, 8).m128i_u64[0];
    v10 = (unsigned int)(v10 + 2);
    *(_QWORD *)&v8[8 * v12 + 184] = v13.m128i_i64[0];
    *(_QWORD *)&v8[16 * v14 + 192] = v15;
    *(_QWORD *)&v8[16 * v14 + 184] = v15;
  }
  while ( (unsigned int)v10 < 6 );
  *a4 = v8;
  *((_QWORD *)v8 + 13) = v8 + 96;
  *((_QWORD *)v8 + 12) = v8 + 96;
  *((_QWORD *)v8 + 15) = v8 + 112;
  *((_QWORD *)v8 + 14) = v8 + 112;
  *((_QWORD *)v8 + 9) = v8 + 64;
  *((_QWORD *)v8 + 8) = v8 + 64;
  return 0;
}

```

## disassembly

```asm
0x18002ed54  push    rbx
0x18002ed56  push    rsi
0x18002ed57  push    rdi
0x18002ed58  push    r14
0x18002ed5a  sub     rsp, 28h
0x18002ed5e  mov     rsi, rdx
0x18002ed61  mov     qword ptr [r9], 0
0x18002ed68  mov     rdi, rcx
0x18002ed6b  mov     edx, 10h; Alignment
0x18002ed70  mov     ecx, 118h; Size
0x18002ed75  mov     r14, r9
0x18002ed78  call    _o__aligned_malloc_0
0x18002ed7d  mov     rbx, rax
0x18002ed80  test    rax, rax
0x18002ed83  jnz     short loc_18002ED8D
0x18002ed85  lea     edi, [rax+8]
0x18002ed88  jmp     loc_18002EEE3
0x18002ed8d  xor     edx, edx; Val
0x18002ed8f  mov     r8d, 118h; Size
0x18002ed95  mov     rcx, rbx; void *
0x18002ed98  call    memset_0
0x18002ed9d  mov     [rbx+10h], rdi
0x18002eda1  mov     edx, 80000400h; dwSpinCount
0x18002eda6  mov     dword ptr [rbx], 0BEE0BEE0h
0x18002edac  mov     ecx, [rdi+14h]
0x18002edaf  mov     eax, [rdi+18h]
0x18002edb2  lea     rdi, [rbx+88h]
0x18002edb9  shl     ecx, 0Ch
0x18002edbc  add     eax, 0FFFFF000h
0x18002edc1  add     ecx, eax
0x18002edc3  mov     [rbx+18h], ecx
0x18002edc6  mov     rcx, rdi; lpCriticalSection
0x18002edc9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002edd0  nop     dword ptr [rax+rax+00h]
0x18002edd5  test    eax, eax
0x18002edd7  jnz     short loc_18002EDEC
0x18002edd9  call    cs:__imp_GetLastError
0x18002ede0  nop     dword ptr [rax+rax+00h]
0x18002ede5  mov     edi, eax
0x18002ede7  jmp     loc_18002EECD
0x18002edec  mov     eax, 0FFFFFFFFh
0x18002edf1  cmp     rsi, rax
0x18002edf4  ja      loc_18002EEB6
0x18002edfa  lea     rax, [rbx+50h]
0x18002edfe  mov     [rbx+30h], esi
0x18002ee01  mov     [rax+8], rax
0x18002ee05  xor     r9d, r9d
0x18002ee08  mov     [rax], rax
0x18002ee0b  lea     rax, [rbx+0B8h]
0x18002ee12  movq    xmm3, rax
0x18002ee17  punpcklqdq xmm3, xmm3
0x18002ee1b  movq    xmm0, cs:__xmm@00000003000000020000000100000000
0x18002ee23  lea     rax, [r9+0Ch]
0x18002ee27  add     rax, rax
0x18002ee2a  movd    xmm2, r9d
0x18002ee2f  pshufd  xmm2, xmm2, 0
0x18002ee34  xorps   xmm1, xmm1
0x18002ee37  paddd   xmm2, xmm0
0x18002ee3b  mov     r8d, r9d
0x18002ee3e  punpckldq xmm2, xmm1
0x18002ee42  add     r8, r8
0x18002ee45  psllq   xmm2, 4
0x18002ee4a  paddq   xmm2, xmm3
0x18002ee4e  movq    qword ptr [rbx+rax*8], xmm2
0x18002ee53  movdqa  xmm0, xmm2
0x18002ee57  lea     eax, [r9+1]
0x18002ee5b  psrldq  xmm0, 8
0x18002ee60  mov     edx, eax
0x18002ee62  add     r9d, 2
0x18002ee66  add     rax, 0Ch
0x18002ee6a  movq    qword ptr [rbx+r8*8+0B8h], xmm2
0x18002ee74  add     rax, rax
0x18002ee77  add     rdx, rdx
0x18002ee7a  movq    qword ptr [rbx+rax*8], xmm0
0x18002ee7f  movq    qword ptr [rbx+rdx*8+0B8h], xmm0
0x18002ee88  cmp     r9d, 6
0x18002ee8c  jb      short loc_18002EE1B
0x18002ee8e  lea     rax, [rbx+60h]
0x18002ee92  mov     [r14], rbx
0x18002ee95  mov     [rax+8], rax
0x18002ee99  mov     [rax], rax
0x18002ee9c  lea     rax, [rbx+70h]
0x18002eea0  mov     [rax+8], rax
0x18002eea4  mov     [rax], rax
0x18002eea7  lea     rax, [rbx+40h]
0x18002eeab  mov     [rax+8], rax
0x18002eeaf  mov     [rax], rax
0x18002eeb2  xor     eax, eax
0x18002eeb4  jmp     short loc_18002EEE5
0x18002eeb6  mov     rcx, rdi; lpCriticalSection
0x18002eeb9  mov     [rbx+30h], eax
0x18002eebc  call    cs:__imp_DeleteCriticalSection
0x18002eec3  nop     dword ptr [rax+rax+00h]
0x18002eec8  mov     edi, 216h
0x18002eecd  mov     rcx, [rbx+28h]; Block
0x18002eed1  test    rcx, rcx
0x18002eed4  jz      short loc_18002EEDB
0x18002eed6  call    _aligned_free
0x18002eedb  mov     rcx, rbx; Block
0x18002eede  call    _aligned_free
0x18002eee3  mov     eax, edi
0x18002eee5  add     rsp, 28h
0x18002eee9  pop     r14
0x18002eeeb  pop     rdi
0x18002eeec  pop     rsi
0x18002eeed  pop     rbx
0x18002eeee  retn
```
