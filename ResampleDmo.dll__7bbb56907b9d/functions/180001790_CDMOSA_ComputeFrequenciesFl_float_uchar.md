# CDMOSA::ComputeFrequenciesFl(float *,uchar *)

- ea: `0x180001790`
- end: `0x180001ac0`
- name: `?ComputeFrequenciesFl@CDMOSA@@IEAAXPEAMPEAE@Z`
- size: `816`
- prototype: `void(CDMOSA *__hidden this, float *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`

## callees

- `0x180001790`
- `0x180001ad0`
- `0x18000b79c`
- `0x180084690`

## pseudocode

```c
void __fastcall CDMOSA::ComputeFrequenciesFl(CDMOSA *this, float *a2, unsigned __int8 *a3)
{
  int v3; // edi
  bool v6; // r8
  int v7; // r8d
  int i; // edx
  __int64 v9; // rcx
  float v10; // xmm0_4
  __int64 v11; // rax
  float v12; // xmm8_4
  float v13; // xmm9_4
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  float v17; // xmm2_4
  float v18; // xmm9_4
  int v19; // ecx
  float v20; // xmm4_4
  float v21; // xmm3_4
  float v22; // xmm1_4
  bool v23; // cf
  int v24; // eax
  __int64 v25; // rcx
  int j; // r8d
  __int64 v27; // r9
  __m128i v28; // xmm0
  unsigned int v29; // eax
  int v30; // edx
  int k; // r8d
  int v32; // edx

  v3 = *((_DWORD *)this + 175);
  memcpy_0(*((void **)this + 82), a2, 8LL * v3);
  FFTWrapper::ComputeFFT((CDMOSA *)((char *)this + 448), *((float **)this + 82), v6);
  v7 = *((_DWORD *)this + 175);
  if ( v7 > 1 )
  {
    for ( i = 1; i < v7; ++i )
    {
      v9 = *((_QWORD *)this + 82);
      v10 = *(float *)(v9 + 4LL * (2 * v7 - i));
      v11 = i;
      *(float *)(v9 + 4 * v11) = (float)((float)(*(float *)(v9 + 4 * v11) * *(float *)(v9 + 4 * v11))
                                       + (float)(v10 * v10))
                               * (float)(1.0 / (float)(4 * v3 * v3));
      v7 = *((_DWORD *)this + 175);
    }
  }
  if ( *((_DWORD *)this + 174) )
  {
    v12 = (float)*((int *)this + 166) / (float)(2 * v7);
    v13 = 22050.0 / (float)v7;
    if ( (float)(v13 - v12) < -0.001 || (float)(v13 - v12) > 0.001 )
    {
      memset_0(*((void **)this + 81), 0, 4LL * v7);
      v14 = *((_DWORD *)this + 175);
      if ( v14 <= 0 )
      {
        v19 = *((_DWORD *)this + 175);
      }
      else
      {
        v15 = 0;
        v16 = 0;
        v17 = FLOAT_1_0;
        v18 = v13 / v12;
        do
        {
          v19 = v14;
          if ( v15 >= v14 )
            break;
          v20 = 0.0;
          if ( v18 > 0.0 )
          {
            v21 = v18;
            do
            {
              v22 = fminf(1.0, fminf(v17, v21));
              v17 = v17 - v22;
              v21 = v21 - v22;
              v23 = v17 > 0.0;
              v20 = v20 + (float)(v22 * *(float *)(*((_QWORD *)this + 82) + 4LL * v15));
              if ( v17 <= 0.0 )
                v17 = FLOAT_1_0;
              v24 = v15 + 1;
              if ( v23 )
                v24 = v15;
              v15 = v24;
            }
            while ( v21 > 0.0 );
          }
          v25 = v16++;
          *(float *)(*((_QWORD *)this + 81) + 4 * v25) = v20;
          v14 = *((_DWORD *)this + 175);
          v19 = v14;
        }
        while ( v16 < v14 );
      }
      memcpy_0(*((void **)this + 82), *((const void **)this + 81), 4LL * v19);
    }
    for ( j = 0; j < *((_DWORD *)this + 175); a3[v27] = v30 )
    {
      v27 = j;
      v28 = (__m128i)*(unsigned int *)(*((_QWORD *)this + 82) + 4LL * j);
      if ( *(float *)v28.m128i_i32 <= 0.0 )
        v28 = (__m128i)LODWORD(FLOAT_1_0);
      v29 = _mm_cvtsi128_si32(v28);
      v30 = *((_DWORD *)&g_mpiExponentTable + (unsigned __int8)((unsigned __int64)v29 >> 23))
          + *((_DWORD *)&g_mpiMantissaTable + ((v29 >> 12) & 0x7FF));
      if ( v30 > 255 )
      {
        LOBYTE(v30) = -1;
      }
      else if ( v30 < 0 )
      {
        LOBYTE(v30) = 0;
      }
      ++j;
    }
  }
  else
  {
    memset_0(a3, 0, v7);
    for ( k = 0; k < *((_DWORD *)this + 175) - 1; ++k )
    {
      v32 = *((_DWORD *)&g_mpiExponentTable
            + (unsigned __int8)((unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 82) + 4LL * k + 4) >> 23))
          + *((_DWORD *)&g_mpiMantissaTable + ((*(_DWORD *)(*((_QWORD *)this + 82) + 4LL * k + 4) >> 12) & 0x7FF));
      if ( v32 <= 255 )
      {
        if ( v32 < 0 )
          LOBYTE(v32) = 0;
      }
      else
      {
        LOBYTE(v32) = -1;
      }
      a3[k] = v32;
    }
  }
}

```

## disassembly

```asm
0x180001790  mov     [rsp+arg_0], rbx
0x180001795  mov     [rsp+arg_8], rsi
0x18000179a  push    rdi
0x18000179b  sub     rsp, 60h
0x18000179f  mov     edi, [rcx+2BCh]
0x1800017a5  mov     rsi, r8
0x1800017a8  mov     rbx, rcx
0x1800017ab  movaps  [rsp+68h+var_28], xmm7
0x1800017b0  mov     rcx, [rcx+290h]; void *
0x1800017b7  lea     eax, [rdi+rdi]
0x1800017ba  movsxd  r8, eax
0x1800017bd  shl     r8, 2; Size
0x1800017c1  call    memcpy_0
0x1800017c6  mov     rdx, [rbx+290h]; float *
0x1800017cd  lea     rcx, [rbx+1C0h]; this
0x1800017d4  call    ?ComputeFFT@FFTWrapper@@QEAAXPEAM_N@Z; FFTWrapper::ComputeFFT(float *,bool)
0x1800017d9  mov     r8d, [rbx+2BCh]
0x1800017e0  movss   xmm7, cs:__real@3f800000
0x1800017e8  cmp     r8d, 1
0x1800017ec  jle     short loc_18000184F
0x1800017ee  imul    edi, edi
0x1800017f1  movaps  xmm2, xmm7
0x1800017f4  mov     edx, 1
0x1800017f9  shl     edi, 2
0x1800017fc  movd    xmm0, edi
0x180001800  cvtdq2ps xmm0, xmm0
0x180001803  divss   xmm2, xmm0
0x180001807  nop     word ptr [rax+rax+00000000h]
0x180001810  mov     rcx, [rbx+290h]
0x180001817  lea     eax, [r8+r8]
0x18000181b  sub     eax, edx
0x18000181d  cdqe
0x18000181f  movss   xmm0, dword ptr [rcx+rax*4]
0x180001824  movsxd  rax, edx
0x180001827  inc     edx
0x180001829  mulss   xmm0, xmm0
0x18000182d  movss   xmm1, dword ptr [rcx+rax*4]
0x180001832  mulss   xmm1, xmm1
0x180001836  addss   xmm1, xmm0
0x18000183a  mulss   xmm1, xmm2
0x18000183e  movss   dword ptr [rcx+rax*4], xmm1
0x180001843  mov     r8d, [rbx+2BCh]
0x18000184a  cmp     edx, r8d
0x18000184d  jl      short loc_180001810
0x18000184f  cmp     dword ptr [rbx+2B8h], 0
0x180001856  jz      loc_180001A21
0x18000185c  mov     eax, [rbx+298h]
0x180001862  xorps   xmm0, xmm0
0x180001865  movaps  [rsp+68h+var_18], xmm6
0x18000186a  xorps   xmm1, xmm1
0x18000186d  movaps  [rsp+68h+var_38], xmm8
0x180001873  xor     edi, edi
0x180001875  xorps   xmm8, xmm8
0x180001879  movaps  [rsp+68h+var_48], xmm9
0x18000187f  movss   xmm9, cs:__real@46ac4400
0x180001888  xorps   xmm6, xmm6
0x18000188b  cvtsi2ss xmm8, rax
0x180001890  lea     eax, [r8+r8]
0x180001894  cvtsi2ss xmm0, eax
0x180001898  cvtsi2ss xmm1, r8d
0x18000189d  divss   xmm8, xmm0
0x1800018a2  movss   xmm0, cs:__real@ba83126f
0x1800018aa  divss   xmm9, xmm1
0x1800018af  movaps  xmm2, xmm9
0x1800018b3  subss   xmm2, xmm8
0x1800018b8  comiss  xmm0, xmm2
0x1800018bb  jbe     loc_180001AAE
0x1800018c1  mov     rcx, [rbx+288h]; void *
0x1800018c8  xor     edx, edx; Val
0x1800018ca  movsxd  r8, r8d
0x1800018cd  shl     r8, 2; Size
0x1800018d1  call    memset_0
0x1800018d6  mov     eax, [rbx+2BCh]
0x1800018dc  test    eax, eax
0x1800018de  jle     loc_180001A89
0x1800018e4  mov     edx, edi
0x1800018e6  mov     r8d, edi
0x1800018e9  movaps  xmm2, xmm7
0x1800018ec  divss   xmm9, xmm8
0x1800018f1  mov     ecx, eax
0x1800018f3  cmp     edx, eax
0x1800018f5  jge     short loc_180001964
0x1800018f7  comiss  xmm9, xmm6
0x1800018fb  movaps  xmm4, xmm6
0x1800018fe  jbe     short loc_180001945
0x180001900  mov     rcx, [rbx+290h]
0x180001907  movaps  xmm3, xmm9
0x18000190b  movaps  xmm0, xmm2
0x18000190e  movsxd  rax, edx
0x180001911  minss   xmm0, xmm3
0x180001915  movaps  xmm1, xmm7
0x180001918  minss   xmm1, xmm0
0x18000191c  movaps  xmm0, xmm1
0x18000191f  subss   xmm2, xmm1
0x180001923  mulss   xmm0, dword ptr [rcx+rax*4]
0x180001928  subss   xmm3, xmm1
0x18000192c  comiss  xmm6, xmm2
0x18000192f  addss   xmm4, xmm0
0x180001933  jb      short loc_180001938
0x180001935  movaps  xmm2, xmm7
0x180001938  lea     eax, [rdx+1]
0x18000193b  cmovb   eax, edx
0x18000193e  comiss  xmm3, xmm6
0x180001941  mov     edx, eax
0x180001943  ja      short loc_18000190B
0x180001945  mov     rax, [rbx+288h]
0x18000194c  movsxd  rcx, r8d
0x18000194f  inc     r8d
0x180001952  movss   dword ptr [rax+rcx*4], xmm4
0x180001957  mov     eax, [rbx+2BCh]
0x18000195d  mov     ecx, eax
0x18000195f  cmp     r8d, eax
0x180001962  jl      short loc_1800018F1
0x180001964  mov     rdx, [rbx+288h]; Src
0x18000196b  movsxd  r8, ecx
0x18000196e  mov     rcx, [rbx+290h]; void *
0x180001975  shl     r8, 2; Size
0x180001979  call    memcpy_0
0x18000197e  mov     r8d, edi
0x180001981  movaps  xmm9, [rsp+68h+var_48]
0x180001987  movaps  xmm8, [rsp+68h+var_38]
0x18000198d  cmp     [rbx+2BCh], edi
0x180001993  jle     short loc_1800019FB
0x180001995  lea     r10, __ImageBase
0x18000199c  nop     dword ptr [rax+00h]
0x1800019a0  mov     rax, [rbx+290h]
0x1800019a7  movsxd  r9, r8d
0x1800019aa  movss   xmm0, dword ptr [rax+r9*4]
0x1800019b0  comiss  xmm6, xmm0
0x1800019b3  jnb     short loc_180001A15
0x1800019b5  movd    eax, xmm0
0x1800019b9  mov     edx, eax
0x1800019bb  shr     rdx, 0Ch
0x1800019bf  and     edx, 7FFh
0x1800019c5  mov     ecx, eax
0x1800019c7  shr     rcx, 17h
0x1800019cb  movzx   eax, cl
0x1800019ce  mov     edx, ds:rva ?g_mpiMantissaTable@@3PAHA[r10+rdx*4]; int near * g_mpiMantissaTable ...
0x1800019d6  add     edx, ds:rva ?g_mpiExponentTable@@3PAHA[r10+rax*4]; int near * g_mpiExponentTable ...
0x1800019de  cmp     edx, 0FFh
0x1800019e4  jg      short loc_180001A1A
0x1800019e6  test    edx, edx
0x1800019e8  cmovs   edx, edi
0x1800019eb  inc     r8d
0x1800019ee  mov     [r9+rsi], dl
0x1800019f2  cmp     r8d, [rbx+2BCh]
0x1800019f9  jl      short loc_1800019A0
0x1800019fb  movaps  xmm6, [rsp+68h+var_18]
0x180001a00  mov     rbx, [rsp+68h+arg_0]
0x180001a05  mov     rsi, [rsp+68h+arg_8]
0x180001a0a  movaps  xmm7, [rsp+68h+var_28]
0x180001a0f  add     rsp, 60h
0x180001a13  pop     rdi
0x180001a14  retn
0x180001a15  movaps  xmm0, xmm7
0x180001a18  jmp     short loc_1800019B5
0x180001a1a  mov     edx, 0FFh
0x180001a1f  jmp     short loc_1800019EB
0x180001a21  movsxd  r8, r8d; Size
0x180001a24  xor     edx, edx; Val
0x180001a26  mov     rcx, rsi; void *
0x180001a29  call    memset_0
0x180001a2e  mov     eax, [rbx+2BCh]
0x180001a34  xor     edi, edi
0x180001a36  dec     eax
0x180001a38  mov     r8d, edi
0x180001a3b  test    eax, eax
0x180001a3d  jle     short loc_180001A00
0x180001a3f  lea     r10, __ImageBase
0x180001a46  mov     rax, [rbx+290h]
0x180001a4d  movsxd  r9, r8d
0x180001a50  mov     eax, [rax+r9*4+4]
0x180001a55  mov     edx, eax
0x180001a57  mov     ecx, eax
0x180001a59  shr     rdx, 0Ch
0x180001a5d  and     edx, 7FFh
0x180001a63  shr     rcx, 17h
0x180001a67  movzx   eax, cl
0x180001a6a  mov     edx, ds:rva ?g_mpiMantissaTable@@3PAHA[r10+rdx*4]; int near * g_mpiMantissaTable ...
0x180001a72  add     edx, ds:rva ?g_mpiExponentTable@@3PAHA[r10+rax*4]; int near * g_mpiExponentTable ...
0x180001a7a  cmp     edx, 0FFh
0x180001a80  jle     short loc_180001A90
0x180001a82  mov     edx, 0FFh
0x180001a87  jmp     short loc_180001A95
0x180001a89  mov     ecx, eax
0x180001a8b  jmp     loc_180001964
0x180001a90  test    edx, edx
0x180001a92  cmovs   edx, edi
0x180001a95  mov     [r9+rsi], dl
0x180001a99  inc     r8d
0x180001a9c  mov     eax, [rbx+2BCh]
0x180001aa2  dec     eax
0x180001aa4  cmp     r8d, eax
0x180001aa7  jl      short loc_180001A46
0x180001aa9  jmp     loc_180001A00
0x180001aae  comiss  xmm2, cs:__real@3a83126f
0x180001ab5  jbe     loc_18000197E
0x180001abb  jmp     loc_1800018C1
```
