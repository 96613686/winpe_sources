# CCentroid::UpdateWithEdge(CScanner::CChain const &,CScanner::CVertex const &)

- ea: `0x100432d90`
- end: `0x100432e25`
- name: `?UpdateWithEdge@CCentroid@@MEAAXAEBVCChain@CScanner@@AEBVCVertex@3@@Z`
- size: `149`
- prototype: `void __fastcall(CCentroid *__hidden this, const struct CScanner::CChain *, const struct CScanner::CVertex *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x100432d90`

## pseudocode

```c
void __fastcall CCentroid::UpdateWithEdge(
        CCentroid *this,
        const struct CScanner::CChain *a2,
        const struct CScanner::CVertex *a3)
{
  double *v3; // rax
  double v4; // xmm2_8
  double v5; // xmm4_8
  double v6; // xmm5_8
  double v7; // xmm3_8
  double v8; // xmm1_8
  double v9; // xmm3_8

  v3 = (double *)*((_QWORD *)a3 + 3);
  v4 = *(double *)a3;
  v5 = *((double *)a3 + 1);
  v6 = *v3;
  v7 = v3[1];
  v8 = v7 * *(double *)a3 - *v3 * v5;
  if ( (((unsigned __int8)~HIBYTE(*((unsigned __int16 *)a2 + 36))
       ^ (unsigned __int8)~(*((unsigned __int16 *)a2 + 36) >> 12))
      & 1) != 0 )
    *(_QWORD *)&v8 ^= _xmm;
  *((double *)this + 65) = v8 + *((double *)this + 65);
  v9 = (v7 + v5) * v8 + *((double *)this + 67);
  *((double *)this + 66) = (v4 + v6) * v8 + *((double *)this + 66);
  *((double *)this + 67) = v9;
}

```

## disassembly

```asm
0x100432d90  mov     rax, [r8+18h]
0x100432d94  mov     r9, rcx
0x100432d97  movsd   xmm2, qword ptr [r8]
0x100432d9c  movsd   xmm4, qword ptr [r8+8]
0x100432da2  movsd   xmm5, qword ptr [rax]
0x100432da6  movsd   xmm3, qword ptr [rax+8]
0x100432dab  movaps  xmm0, xmm5
0x100432dae  movzx   eax, word ptr [rdx+48h]
0x100432db2  movaps  xmm1, xmm3
0x100432db5  mov     ecx, eax
0x100432db7  mulsd   xmm1, xmm2
0x100432dbb  shr     ecx, 0Ch
0x100432dbe  shr     eax, 8
0x100432dc1  not     ecx
0x100432dc3  mulsd   xmm0, xmm4
0x100432dc7  not     eax
0x100432dc9  xor     ecx, eax
0x100432dcb  subsd   xmm1, xmm0
0x100432dcf  test    cl, 1
0x100432dd2  jz      short loc_100432DDB
0x100432dd4  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x100432ddb  addsd   xmm2, xmm5
0x100432ddf  movaps  xmm0, xmm1
0x100432de2  addsd   xmm0, qword ptr [r9+208h]
0x100432deb  addsd   xmm3, xmm4
0x100432def  mulsd   xmm2, xmm1
0x100432df3  mulsd   xmm3, xmm1
0x100432df7  movsd   qword ptr [r9+208h], xmm0
0x100432e00  addsd   xmm2, qword ptr [r9+210h]
0x100432e09  addsd   xmm3, qword ptr [r9+218h]
0x100432e12  movsd   qword ptr [r9+210h], xmm2
0x100432e1b  movsd   qword ptr [r9+218h], xmm3
0x100432e24  retn
```
