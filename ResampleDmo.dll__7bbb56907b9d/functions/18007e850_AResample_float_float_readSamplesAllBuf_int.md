# AResample<float,float>::readSamplesAllBuf(int)

- ea: `0x18007e850`
- end: `0x18007e9be`
- name: `?readSamplesAllBuf@?$AResample@MM@@IEAAHH@Z`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18007e850`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall AResample<float,float>::readSamplesAllBuf(__int64 a1, int a2)
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
  __int64 v13; // rdx
  _QWORD v15[5]; // [rsp+20h] [rbp-28h]

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
      v13 = *(_QWORD *)(a1 + 48);
      v15[0] = MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::AVX2Math>;
      v15[1] = MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::SSEMath>;
      ((void (__fastcall *)(__int64, __int64, __int64))v15[AudioMathSpace::X64SIMDMath::s_SIMDFeatures < 4])(
        a1 + 120,
        v13,
        1);
      ++v4;
      *(_QWORD *)(a1 + 104) += *(int *)(*(_QWORD *)(a1 + 16) + 84LL);
      if ( (int)v4 >= v3 )
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
0x18007e850  push    rbx
0x18007e852  push    rsi
0x18007e853  push    rdi
0x18007e854  sub     rsp, 30h
0x18007e858  mov     esi, [rcx+5Ch]
0x18007e85b  mov     rbx, rcx
0x18007e85e  sub     esi, [rcx+58h]
0x18007e861  cmp     edx, esi
0x18007e863  cmovl   esi, edx
0x18007e866  xor     edi, edi
0x18007e868  test    esi, esi
0x18007e86a  jle     loc_18007E9B4
0x18007e870  mov     [rsp+48h+arg_0], rbp
0x18007e875  mov     [rsp+48h+arg_8], r14
0x18007e87a  lea     r14, ??$insert1EndFull_AllChannels_interleavedinput_Impl@VAVX2Math@AudioMathSpace@@@?$MultiChannel_Deinterleaved_CircularBuffer@M@@QEAAXPEBMI@Z; MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::AVX2Math>(float const *,uint)
0x18007e881  mov     [rsp+48h+arg_10], r15
0x18007e886  lea     r15, ??$insert1EndFull_AllChannels_interleavedinput_Impl@VSSEMath@AudioMathSpace@@@?$MultiChannel_Deinterleaved_CircularBuffer@M@@QEAAXPEBMI@Z; MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::SSEMath>(float const *,uint)
0x18007e88d  nop     dword ptr [rax]
0x18007e890  mov     r8, [rbx+10h]
0x18007e894  cmp     dword ptr [r8+30h], 0
0x18007e899  jbe     loc_18007E961
0x18007e89f  xor     r10d, r10d
0x18007e8a2  mov     eax, [r8+64h]
0x18007e8a6  mov     r9, [rbx+68h]
0x18007e8aa  test    eax, eax
0x18007e8ac  jnz     short loc_18007E912
0x18007e8ae  mov     ecx, [r8+3Ch]
0x18007e8b2  xor     edx, edx
0x18007e8b4  sub     ecx, 1
0x18007e8b7  jz      short loc_18007E8F3
0x18007e8b9  sub     ecx, 1
0x18007e8bc  jz      short loc_18007E8ED
0x18007e8be  sub     ecx, 1
0x18007e8c1  jz      short loc_18007E8CD
0x18007e8c3  cmp     ecx, 1
0x18007e8c6  jnz     short loc_18007E8FA
0x18007e8c8  mov     edx, [r9]
0x18007e8cb  jmp     short loc_18007E8FA
0x18007e8cd  movzx   eax, byte ptr [r9+1]
0x18007e8d2  movzx   edx, byte ptr [r9+2]
0x18007e8d7  shl     edx, 8
0x18007e8da  or      edx, eax
0x18007e8dc  movzx   eax, byte ptr [r9]
0x18007e8e0  shl     edx, 8
0x18007e8e3  or      edx, eax
0x18007e8e5  shl     edx, 8
0x18007e8e8  sar     edx, 8
0x18007e8eb  jmp     short loc_18007E8FA
0x18007e8ed  movsx   edx, word ptr [r9]
0x18007e8f1  jmp     short loc_18007E8FA
0x18007e8f3  movzx   edx, byte ptr [r9]
0x18007e8f7  add     edx, 0FFFFFF80h
0x18007e8fa  mov     ecx, [r8+88h]
0x18007e901  test    ecx, ecx
0x18007e903  jns     short loc_18007E909
0x18007e905  neg     ecx
0x18007e907  shl     edx, cl
0x18007e909  movd    xmm0, edx
0x18007e90d  cvtdq2ps xmm0, xmm0
0x18007e910  jmp     short loc_18007E93E
0x18007e912  cmp     eax, 1
0x18007e915  jnz     short loc_18007E93B
0x18007e917  mov     eax, [r8+68h]
0x18007e91b  test    eax, eax
0x18007e91d  jnz     short loc_18007E92F
0x18007e91f  movss   xmm0, dword ptr [r8+84h]
0x18007e928  mulss   xmm0, dword ptr [r9]
0x18007e92d  jmp     short loc_18007E93E
0x18007e92f  cmp     eax, 1
0x18007e932  jnz     short loc_18007E93B
0x18007e934  movss   xmm0, dword ptr [r9]
0x18007e939  jmp     short loc_18007E93E
0x18007e93b  xorps   xmm0, xmm0
0x18007e93e  mov     rax, [rbx+30h]
0x18007e942  movss   dword ptr [rax+r10*4], xmm0
0x18007e948  inc     r10d
0x18007e94b  mov     r8, [rbx+10h]
0x18007e94f  movsxd  rax, dword ptr [r8+3Ch]
0x18007e953  add     [rbx+68h], rax
0x18007e957  cmp     r10d, [r8+30h]
0x18007e95b  jb      loc_18007E8A2
0x18007e961  mov     rdx, [rbx+30h]
0x18007e965  lea     rcx, [rbx+78h]
0x18007e969  xor     eax, eax
0x18007e96b  mov     [rsp+48h+var_28], r14
0x18007e970  cmp     cs:?s_SIMDFeatures@X64SIMDMath@AudioMathSpace@@2W4SIMDFeatures@12@B, 4; AudioMathSpace::X64SIMDMath::SIMDFeatures const AudioMathSpace::X64SIMDMath::s_SIMDFeatures
0x18007e977  mov     r8d, 1
0x18007e97d  mov     [rsp+48h+var_20], r15
0x18007e982  setl    al
0x18007e985  mov     rax, [rsp+rax*8+48h+var_28]
0x18007e98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e98f  mov     rcx, [rbx+10h]
0x18007e993  inc     edi
0x18007e995  movsxd  rdx, dword ptr [rcx+54h]
0x18007e999  add     [rbx+68h], rdx
0x18007e99d  cmp     edi, esi
0x18007e99f  jl      loc_18007E890
0x18007e9a5  mov     r15, [rsp+48h+arg_10]
0x18007e9aa  mov     r14, [rsp+48h+arg_8]
0x18007e9af  mov     rbp, [rsp+48h+arg_0]
0x18007e9b4  mov     eax, edi
0x18007e9b6  add     rsp, 30h
0x18007e9ba  pop     rdi
0x18007e9bb  pop     rsi
0x18007e9bc  pop     rbx
0x18007e9bd  retn
```
