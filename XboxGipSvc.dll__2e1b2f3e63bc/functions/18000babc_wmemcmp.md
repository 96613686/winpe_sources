# wmemcmp

- ea: `0x18000babc`
- end: `0x18000bbdc`
- name: `wmemcmp`
- size: `288`
- prototype: `int __cdecl(const wchar_t *S1, const wchar_t *S2, size_t N)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b460`
- `0x18000e224`
- `0x180010f28`

## callees

- `0x18000babc`

## pseudocode

```c
int __cdecl wmemcmp(const wchar_t *S1, const wchar_t *S2, size_t N)
{
  size_t v3; // r9
  const __m128i *v7; // r11
  unsigned __int64 v11; // rcx
  int result; // eax
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  bool v17; // cf
  wchar_t v18; // ax

  v3 = 0;
  _R10 = (const __m128i *)S1;
  v7 = (const __m128i *)S2;
  if ( Avx2WmemEnabledWeakValue && N >= 0x10 )
  {
    while ( 1 )
    {
      __asm
      {
        vmovdqu ymm1, ymmword ptr [r10]
        vpcmpeqw ymm1, ymm1, ymmword ptr [r11]
        vpmovmskb eax, ymm1
      }
      if ( _EAX != -1 )
        break;
      v3 += 16LL;
      _R10 += 2;
      v7 += 2;
      if ( v3 + 16 > N )
      {
        __asm { vzeroupper }
        goto LABEL_9;
      }
    }
    _BitScanForward((unsigned int *)&v11, ~_EAX);
    result = S1[(v11 >> 1) + v3] < S2[(v11 >> 1) + v3] ? -1 : 1;
    __asm { vzeroupper }
  }
  else
  {
LABEL_9:
    while ( v3 + 8 <= N )
    {
      LOWORD(v13) = _mm_movemask_epi8(_mm_cmpeq_epi16(_mm_loadu_si128(v7), _mm_loadu_si128(_R10)));
      if ( (_WORD)v13 != 0xFFFF )
      {
        _BitScanForward((unsigned int *)&v13, ~(unsigned __int16)v13);
        v15 = (v13 >> 1) + v3;
        v16 = v15;
LABEL_14:
        v17 = S1[v15] < S2[v16];
        return v17 ? -1 : 1;
      }
      v3 += 8LL;
      ++_R10;
      ++v7;
    }
    if ( v3 + 4 > N )
      goto LABEL_19;
    if ( _R10->m128i_i64[0] != v7->m128i_i64[0] )
    {
      _BitScanForward64(&v14, _R10->m128i_i64[0] ^ v7->m128i_i64[0]);
      v15 = (v14 >> 4) + v3;
      v16 = v15;
      goto LABEL_14;
    }
    v3 += 4LL;
LABEL_19:
    while ( v3 < N )
    {
      v18 = S1[v3];
      v17 = v18 < S2[v3];
      if ( v18 != S2[v3] )
        return v17 ? -1 : 1;
      ++v3;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000babc  mov     [rsp+arg_8], rbx
0x18000bac1  mov     [rsp+arg_10], rdi
0x18000bac6  xor     r9d, r9d
0x18000bac9  mov     rbx, rdx
0x18000bacc  cmp     cs:_Avx2WmemEnabledWeakValue, r9d
0x18000bad3  mov     rdi, rcx
0x18000bad6  mov     r10, rcx
0x18000bad9  mov     r11, rdx
0x18000badc  jz      loc_18000BB64
0x18000bae2  cmp     r8, 10h
0x18000bae6  jb      short loc_18000BB64
0x18000bae8  vmovdqu ymm1, ymmword ptr [r10]
0x18000baed  vpcmpeqw ymm1, ymm1, ymmword ptr [r11]
0x18000baf2  vpmovmskb eax, ymm1
0x18000baf6  cmp     eax, 0FFFFFFFFh
0x18000baf9  jnz     short loc_18000BB15
0x18000bafb  add     r9, 10h
0x18000baff  add     r10, 20h ; ' '
0x18000bb03  add     r11, 20h ; ' '
0x18000bb07  lea     rax, [r9+10h]
0x18000bb0b  cmp     rax, r8
0x18000bb0e  jbe     short loc_18000BAE8
0x18000bb10  vzeroupper
0x18000bb13  jmp     short loc_18000BB64
0x18000bb15  not     eax
0x18000bb17  bsf     ecx, eax
0x18000bb1a  shr     rcx, 1
0x18000bb1d  lea     rax, [rcx+r9]
0x18000bb21  lea     rdx, [rcx+r9]
0x18000bb25  movzx   ecx, word ptr [rbx+rax*2]
0x18000bb29  cmp     [rdi+rdx*2], cx
0x18000bb2d  sbb     eax, eax
0x18000bb2f  and     eax, 0FFFFFFFEh
0x18000bb32  inc     eax
0x18000bb34  vzeroupper
0x18000bb37  jmp     loc_18000BBD1
0x18000bb3c  movdqu  xmm1, xmmword ptr [r11]
0x18000bb41  mov     ecx, 0FFFFh
0x18000bb46  movdqu  xmm0, xmmword ptr [r10]
0x18000bb4b  pcmpeqw xmm1, xmm0
0x18000bb4f  pmovmskb eax, xmm1
0x18000bb53  cmp     ax, cx
0x18000bb56  jnz     short loc_18000BB93
0x18000bb58  add     r9, 8
0x18000bb5c  add     r10, 10h
0x18000bb60  add     r11, 10h
0x18000bb64  lea     rax, [r9+8]
0x18000bb68  cmp     rax, r8
0x18000bb6b  jbe     short loc_18000BB3C
0x18000bb6d  lea     rax, [r9+4]
0x18000bb71  cmp     rax, r8
0x18000bb74  ja      short loc_18000BBCA
0x18000bb76  mov     rcx, [r11]
0x18000bb79  cmp     [r10], rcx
0x18000bb7c  jz      short loc_18000BBB6
0x18000bb7e  xor     rcx, [r10]
0x18000bb81  bsf     rcx, rcx
0x18000bb85  shr     rcx, 4
0x18000bb89  lea     rdx, [rcx+r9]
0x18000bb8d  lea     rax, [rcx+r9]
0x18000bb91  jmp     short loc_18000BBA5
0x18000bb93  movzx   eax, ax
0x18000bb96  not     eax
0x18000bb98  bsf     eax, eax
0x18000bb9b  shr     rax, 1
0x18000bb9e  lea     rdx, [rax+r9]
0x18000bba2  add     rax, r9
0x18000bba5  movzx   ecx, word ptr [rbx+rax*2]
0x18000bba9  cmp     [rdi+rdx*2], cx
0x18000bbad  sbb     eax, eax
0x18000bbaf  and     eax, 0FFFFFFFEh
0x18000bbb2  inc     eax
0x18000bbb4  jmp     short loc_18000BBD1
0x18000bbb6  mov     r9, rax
0x18000bbb9  jmp     short loc_18000BBCA
0x18000bbbb  movzx   eax, word ptr [rdi+r9*2]
0x18000bbc0  cmp     ax, [rdx+r9*2]
0x18000bbc5  jnz     short loc_18000BBAD
0x18000bbc7  inc     r9
0x18000bbca  cmp     r9, r8
0x18000bbcd  jb      short loc_18000BBBB
0x18000bbcf  xor     eax, eax
0x18000bbd1  mov     rbx, [rsp+arg_8]
0x18000bbd6  mov     rdi, [rsp+arg_10]
0x18000bbdb  retn
```
