# CArea::UpdateWithEdge(CScanner::CChain const &,CScanner::CVertex const &)

- ea: `0x100430580`
- end: `0x1004305df`
- name: `?UpdateWithEdge@CArea@@MEAAXAEBVCChain@CScanner@@AEBVCVertex@3@@Z`
- size: `95`
- prototype: `void __fastcall(CArea *__hidden this, const struct CScanner::CChain *, const struct CScanner::CVertex *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x100430580`

## pseudocode

```c
void __fastcall CArea::UpdateWithEdge(
        CArea *this,
        const struct CScanner::CChain *a2,
        const struct CScanner::CVertex *a3)
{
  double v3; // xmm2_8
  double v4; // xmm0_8
  double v5; // xmm0_8

  v3 = *(double *)(*((_QWORD *)a3 + 3) + 8LL) * *(double *)a3
     - **((double **)a3 + 3) * _mm_unpackhi_pd(*(__m128d *)a3, *(__m128d *)a3).m128d_f64[0];
  v4 = *((double *)this + 65);
  if ( (((unsigned __int8)~HIBYTE(*((unsigned __int16 *)a2 + 36))
       ^ (unsigned __int8)~(*((unsigned __int16 *)a2 + 36) >> 12))
      & 1) != 0 )
    v5 = v4 - v3;
  else
    v5 = v4 + v3;
  *((double *)this + 65) = v5;
}

```

## disassembly

```asm
0x100430580  mov     rax, [r8+18h]
0x100430584  mov     r9, rcx
0x100430587  movups  xmm1, xmmword ptr [r8]
0x10043058b  movzx   ecx, word ptr [rdx+48h]
0x10043058f  movsd   xmm0, qword ptr [rax]
0x100430593  movsd   xmm2, qword ptr [rax+8]
0x100430598  mov     eax, ecx
0x10043059a  shr     eax, 0Ch
0x10043059d  mulsd   xmm2, xmm1
0x1004305a1  not     eax
0x1004305a3  shr     ecx, 8
0x1004305a6  unpckhpd xmm1, xmm1
0x1004305aa  not     ecx
0x1004305ac  mulsd   xmm0, xmm1
0x1004305b0  xor     eax, ecx
0x1004305b2  subsd   xmm2, xmm0
0x1004305b6  movsd   xmm0, qword ptr [r9+208h]
0x1004305bf  test    al, 1
0x1004305c1  jz      short loc_1004305D1
0x1004305c3  subsd   xmm0, xmm2
0x1004305c7  movsd   qword ptr [r9+208h], xmm0
0x1004305d0  retn
0x1004305d1  addsd   xmm0, xmm2
0x1004305d5  movsd   qword ptr [r9+208h], xmm0
0x1004305de  retn
```
