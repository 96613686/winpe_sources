# LEQ_UpdateAttack

- ea: `0x18004c070`
- end: `0x18004c0dd`
- name: `LEQ_UpdateAttack`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001f1a0`
- `0x18004c250`

## callees

- `0x18004c070`

## pseudocode

```c
__int64 __fastcall LEQ_UpdateAttack(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int v2; // edx
  __m128 v3; // xmm3
  __m128d v4; // xmm0
  __int64 result; // rax

  v1 = 0;
  v2 = *(_DWORD *)(a1 + 228);
  v3 = (__m128)LODWORD(FLOAT_1_0);
  if ( v2 )
  {
    do
    {
      v4 = _mm_cvtps_pd(v3);
      ++v1;
      v4.m128d_f64[0] = v4.m128d_f64[0] * 0.9;
      v3 = _mm_cvtpd_ps(v4);
    }
    while ( v1 < v2 );
  }
  result = *(unsigned int *)(a1 + 68);
  *(float *)(a1 + 48) = fminf(
                          (float)(44100.0 / (float)*(int *)(a1 + 72))
                        * (float)((float)((float)(int)result * 0.001953125) * v3.m128_f32[0]),
                          1.0);
  return result;
}

```

## disassembly

```asm
0x18004c070  movss   xmm4, cs:__real@3f800000
0x18004c078  xor     eax, eax
0x18004c07a  mov     edx, [rcx+0E4h]
0x18004c080  movaps  xmm3, xmm4
0x18004c083  test    edx, edx
0x18004c085  jz      short loc_18004C0A1
0x18004c087  movsd   xmm1, cs:__real@3feccccccccccccd
0x18004c08f  nop
0x18004c090  cvtps2pd xmm0, xmm3
0x18004c093  inc     eax
0x18004c095  mulsd   xmm0, xmm1
0x18004c099  cvtpd2ps xmm3, xmm0
0x18004c09d  cmp     eax, edx
0x18004c09f  jb      short loc_18004C090
0x18004c0a1  mov     eax, [rcx+48h]
0x18004c0a4  xorps   xmm1, xmm1
0x18004c0a7  movss   xmm2, cs:__real@472c4400
0x18004c0af  xorps   xmm0, xmm0
0x18004c0b2  cvtsi2ss xmm0, rax
0x18004c0b7  mov     eax, [rcx+44h]
0x18004c0ba  cvtsi2ss xmm1, rax
0x18004c0bf  divss   xmm2, xmm0
0x18004c0c3  mulss   xmm1, cs:__real@3b000000
0x18004c0cb  mulss   xmm1, xmm3
0x18004c0cf  mulss   xmm2, xmm1
0x18004c0d3  minss   xmm2, xmm4
0x18004c0d7  movss   dword ptr [rcx+30h], xmm2
0x18004c0dc  retn
```
