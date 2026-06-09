# AResample<float,float>::readSamplesAllBufMtx(int)

- ea: `0x18007e9d0`
- end: `0x18007eb91`
- name: `?readSamplesAllBufMtx@?$AResample@MM@@IEAAHH@Z`
- size: `449`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18007e9d0`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall AResample<float,float>::readSamplesAllBufMtx(__int64 a1, int a2)
{
  int v3; // esi
  unsigned int v4; // edi
  __int64 v5; // r8
  __int64 v6; // r10
  int v7; // eax
  unsigned __int8 *v8; // r9
  int v9; // edx
  int v10; // ecx
  float v11; // xmm0_4
  int v12; // eax
  __int64 v13; // r10
  unsigned int v14; // r9d
  float v15; // xmm1_4
  __int64 v16; // rdx
  __int64 v17; // r8
  float v18; // xmm0_4
  __int64 v19; // rdx
  _QWORD v21[5]; // [rsp+20h] [rbp-28h]

  v3 = *(_DWORD *)(a1 + 92) - *(_DWORD *)(a1 + 88);
  if ( a2 < v3 )
    v3 = a2;
  v4 = 0;
  if ( v3 > 0 )
  {
    while ( 1 )
    {
      v5 = *(_QWORD *)(a1 + 16);
      if ( *(_DWORD *)(v5 + 48) )
        break;
LABEL_25:
      *(_QWORD *)(a1 + 104) += *(int *)(v5 + 84);
      if ( *(_DWORD *)(v5 + 56) )
      {
        v13 = 0;
        do
        {
          v14 = *(_DWORD *)(v5 + 48);
          v15 = 0.0;
          if ( v14 )
          {
            v16 = 0;
            v17 = *(_QWORD *)v5 + 4LL * (unsigned int)v13 * v14;
            do
            {
              v18 = *(float *)(v17 + 4 * v16) * *(float *)(*(_QWORD *)(a1 + 48) + 4 * v16);
              v16 = (unsigned int)(v16 + 1);
              v15 = v15 + v18;
            }
            while ( (unsigned int)v16 < v14 );
          }
          *(float *)(*(_QWORD *)(a1 + 80) + 4 * v13) = v15;
          v13 = (unsigned int)(v13 + 1);
          v5 = *(_QWORD *)(a1 + 16);
        }
        while ( (unsigned int)v13 < *(_DWORD *)(v5 + 56) );
      }
      v19 = *(_QWORD *)(a1 + 80);
      v21[0] = MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::AVX2Math>;
      v21[1] = MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::SSEMath>;
      ((void (__fastcall *)(__int64, __int64, __int64))v21[AudioMathSpace::X64SIMDMath::s_SIMDFeatures < 4])(
        a1 + 120,
        v19,
        1);
      if ( (int)++v4 >= v3 )
        return v4;
    }
    v6 = 0;
    while ( 1 )
    {
      v7 = *(_DWORD *)(v5 + 100);
      v8 = *(unsigned __int8 **)(a1 + 104);
      if ( !v7 )
      {
        v9 = 0;
        switch ( *(_DWORD *)(v5 + 60) )
        {
          case 1:
            v9 = *v8 - 128;
            break;
          case 2:
            v9 = *(__int16 *)v8;
            break;
          case 3:
            v9 = (*v8 | (*(unsigned __int16 *)(v8 + 1) << 8)) << 8 >> 8;
            break;
          case 4:
            v9 = *(_DWORD *)v8;
            break;
        }
        v10 = *(_DWORD *)(v5 + 136);
        if ( v10 < 0 )
          v9 <<= -(char)v10;
        v11 = (float)v9;
        goto LABEL_24;
      }
      if ( v7 != 1 )
        break;
      v12 = *(_DWORD *)(v5 + 104);
      if ( v12 )
      {
        if ( v12 != 1 )
          break;
        v11 = *(float *)v8;
      }
      else
      {
        v11 = *(float *)(v5 + 132) * *(float *)v8;
      }
LABEL_24:
      *(float *)(*(_QWORD *)(a1 + 48) + 4 * v6) = v11;
      v6 = (unsigned int)(v6 + 1);
      v5 = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 104) += *(int *)(v5 + 60);
      if ( (unsigned int)v6 >= *(_DWORD *)(v5 + 48) )
        goto LABEL_25;
    }
    v11 = 0.0;
    goto LABEL_24;
  }
  return v4;
}

```

## disassembly

```asm
0x18007e9d0  push    rbx
0x18007e9d2  push    rsi
0x18007e9d3  push    rdi
0x18007e9d4  sub     rsp, 30h
0x18007e9d8  mov     esi, [rcx+5Ch]
0x18007e9db  mov     rbx, rcx
0x18007e9de  sub     esi, [rcx+58h]
0x18007e9e1  cmp     edx, esi
0x18007e9e3  cmovl   esi, edx
0x18007e9e6  xor     edi, edi
0x18007e9e8  test    esi, esi
0x18007e9ea  jle     loc_18007EB87
0x18007e9f0  mov     [rsp+48h+arg_0], rbp
0x18007e9f5  mov     [rsp+48h+arg_8], r14
0x18007e9fa  lea     r14, ??$insert1EndFull_AllChannels_interleavedinput_Impl@VAVX2Math@AudioMathSpace@@@?$MultiChannel_Deinterleaved_CircularBuffer@M@@QEAAXPEBMI@Z; MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::AVX2Math>(float const *,uint)
0x18007ea01  mov     [rsp+48h+arg_10], r15
0x18007ea06  lea     r15, ??$insert1EndFull_AllChannels_interleavedinput_Impl@VSSEMath@AudioMathSpace@@@?$MultiChannel_Deinterleaved_CircularBuffer@M@@QEAAXPEBMI@Z; MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::SSEMath>(float const *,uint)
0x18007ea0d  nop     dword ptr [rax]
0x18007ea10  mov     r8, [rbx+10h]
0x18007ea14  cmp     dword ptr [r8+30h], 0
0x18007ea19  jbe     loc_18007EAE1
0x18007ea1f  xor     r10d, r10d
0x18007ea22  mov     eax, [r8+64h]
0x18007ea26  mov     r9, [rbx+68h]
0x18007ea2a  test    eax, eax
0x18007ea2c  jnz     short loc_18007EA92
0x18007ea2e  mov     ecx, [r8+3Ch]
0x18007ea32  xor     edx, edx
0x18007ea34  sub     ecx, 1
0x18007ea37  jz      short loc_18007EA73
0x18007ea39  sub     ecx, 1
0x18007ea3c  jz      short loc_18007EA6D
0x18007ea3e  sub     ecx, 1
0x18007ea41  jz      short loc_18007EA4D
0x18007ea43  cmp     ecx, 1
0x18007ea46  jnz     short loc_18007EA7A
0x18007ea48  mov     edx, [r9]
0x18007ea4b  jmp     short loc_18007EA7A
0x18007ea4d  movzx   eax, byte ptr [r9+1]
0x18007ea52  movzx   edx, byte ptr [r9+2]
0x18007ea57  shl     edx, 8
0x18007ea5a  or      edx, eax
0x18007ea5c  movzx   eax, byte ptr [r9]
0x18007ea60  shl     edx, 8
0x18007ea63  or      edx, eax
0x18007ea65  shl     edx, 8
0x18007ea68  sar     edx, 8
0x18007ea6b  jmp     short loc_18007EA7A
0x18007ea6d  movsx   edx, word ptr [r9]
0x18007ea71  jmp     short loc_18007EA7A
0x18007ea73  movzx   edx, byte ptr [r9]
0x18007ea77  add     edx, 0FFFFFF80h
0x18007ea7a  mov     ecx, [r8+88h]
0x18007ea81  test    ecx, ecx
0x18007ea83  jns     short loc_18007EA89
0x18007ea85  neg     ecx
0x18007ea87  shl     edx, cl
0x18007ea89  movd    xmm0, edx
0x18007ea8d  cvtdq2ps xmm0, xmm0
0x18007ea90  jmp     short loc_18007EABE
0x18007ea92  cmp     eax, 1
0x18007ea95  jnz     short loc_18007EABB
0x18007ea97  mov     eax, [r8+68h]
0x18007ea9b  test    eax, eax
0x18007ea9d  jnz     short loc_18007EAAF
0x18007ea9f  movss   xmm0, dword ptr [r8+84h]
0x18007eaa8  mulss   xmm0, dword ptr [r9]
0x18007eaad  jmp     short loc_18007EABE
0x18007eaaf  cmp     eax, 1
0x18007eab2  jnz     short loc_18007EABB
0x18007eab4  movss   xmm0, dword ptr [r9]
0x18007eab9  jmp     short loc_18007EABE
0x18007eabb  xorps   xmm0, xmm0
0x18007eabe  mov     rax, [rbx+30h]
0x18007eac2  movss   dword ptr [rax+r10*4], xmm0
0x18007eac8  inc     r10d
0x18007eacb  mov     r8, [rbx+10h]
0x18007eacf  movsxd  rax, dword ptr [r8+3Ch]
0x18007ead3  add     [rbx+68h], rax
0x18007ead7  cmp     r10d, [r8+30h]
0x18007eadb  jb      loc_18007EA22
0x18007eae1  movsxd  rax, dword ptr [r8+54h]
0x18007eae5  add     [rbx+68h], rax
0x18007eae9  cmp     dword ptr [r8+38h], 0
0x18007eaee  jbe     short loc_18007EB40
0x18007eaf0  xor     r10d, r10d
0x18007eaf3  mov     r9d, [r8+30h]
0x18007eaf7  xorps   xmm1, xmm1
0x18007eafa  test    r9d, r9d
0x18007eafd  jz      short loc_18007EB29
0x18007eaff  mov     rax, [r8]
0x18007eb02  mov     ecx, r9d
0x18007eb05  xor     edx, edx
0x18007eb07  imul    ecx, r10d
0x18007eb0b  lea     r8, [rax+rcx*4]
0x18007eb0f  mov     rcx, [rbx+30h]
0x18007eb13  movss   xmm0, dword ptr [r8+rdx*4]
0x18007eb19  mulss   xmm0, dword ptr [rcx+rdx*4]
0x18007eb1e  inc     edx
0x18007eb20  addss   xmm1, xmm0
0x18007eb24  cmp     edx, r9d
0x18007eb27  jb      short loc_18007EB13
0x18007eb29  mov     rax, [rbx+50h]
0x18007eb2d  movss   dword ptr [rax+r10*4], xmm1
0x18007eb33  inc     r10d
0x18007eb36  mov     r8, [rbx+10h]
0x18007eb3a  cmp     r10d, [r8+38h]
0x18007eb3e  jb      short loc_18007EAF3
0x18007eb40  mov     rdx, [rbx+50h]
0x18007eb44  xor     ecx, ecx
0x18007eb46  cmp     cs:?s_SIMDFeatures@X64SIMDMath@AudioMathSpace@@2W4SIMDFeatures@12@B, 4; AudioMathSpace::X64SIMDMath::SIMDFeatures const AudioMathSpace::X64SIMDMath::s_SIMDFeatures
0x18007eb4d  mov     r8d, 1
0x18007eb53  mov     [rsp+48h+var_28], r14
0x18007eb58  setl    cl
0x18007eb5b  mov     [rsp+48h+var_20], r15
0x18007eb60  mov     rax, [rsp+rcx*8+48h+var_28]
0x18007eb65  lea     rcx, [rbx+78h]
0x18007eb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb6e  inc     edi
0x18007eb70  cmp     edi, esi
0x18007eb72  jl      loc_18007EA10
0x18007eb78  mov     r15, [rsp+48h+arg_10]
0x18007eb7d  mov     r14, [rsp+48h+arg_8]
0x18007eb82  mov     rbp, [rsp+48h+arg_0]
0x18007eb87  mov     eax, edi
0x18007eb89  add     rsp, 30h
0x18007eb8d  pop     rdi
0x18007eb8e  pop     rsi
0x18007eb8f  pop     rbx
0x18007eb90  retn
```
