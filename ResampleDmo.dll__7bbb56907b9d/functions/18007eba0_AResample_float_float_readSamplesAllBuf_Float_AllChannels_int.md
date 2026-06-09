# AResample<float,float>::readSamplesAllBuf_Float_AllChannels(int)

- ea: `0x18007eba0`
- end: `0x18007ec14`
- name: `?readSamplesAllBuf_Float_AllChannels@?$AResample@MM@@IEAAHH@Z`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180085010`

## pseudocode

```c
__int64 __fastcall AResample<float,float>::readSamplesAllBuf_Float_AllChannels(__int64 a1, int a2)
{
  int v2; // ebx
  __int64 result; // rax
  _QWORD v5[3]; // [rsp+20h] [rbp-18h]

  v2 = *(_DWORD *)(a1 + 92) - *(_DWORD *)(a1 + 88);
  v5[0] = MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::AVX2Math>;
  if ( a2 < v2 )
    v2 = a2;
  v5[1] = MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::SSEMath>;
  ((void (__fastcall *)(__int64, _QWORD, _QWORD))v5[AudioMathSpace::X64SIMDMath::s_SIMDFeatures < 4])(
    a1 + 120,
    *(_QWORD *)(a1 + 104),
    (unsigned int)v2);
  result = (unsigned int)v2;
  *(_QWORD *)(a1 + 104) += 4 * v2 * (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 16) + 48LL);
  return result;
}

```

## disassembly

```asm
0x18007eba0  mov     [rsp+arg_0], rbx
0x18007eba5  push    rdi
0x18007eba6  sub     rsp, 30h
0x18007ebaa  mov     ebx, [rcx+5Ch]
0x18007ebad  lea     rax, ??$insert1EndFull_AllChannels_interleavedinput_Impl@VAVX2Math@AudioMathSpace@@@?$MultiChannel_Deinterleaved_CircularBuffer@M@@QEAAXPEBMI@Z; MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::AVX2Math>(float const *,uint)
0x18007ebb4  sub     ebx, [rcx+58h]
0x18007ebb7  mov     rdi, rcx
0x18007ebba  mov     [rsp+38h+var_18], rax
0x18007ebbf  cmp     edx, ebx
0x18007ebc1  lea     rax, ??$insert1EndFull_AllChannels_interleavedinput_Impl@VSSEMath@AudioMathSpace@@@?$MultiChannel_Deinterleaved_CircularBuffer@M@@QEAAXPEBMI@Z; MultiChannel_Deinterleaved_CircularBuffer<float>::insert1EndFull_AllChannels_interleavedinput_Impl<AudioMathSpace::SSEMath>(float const *,uint)
0x18007ebc8  cmovl   ebx, edx
0x18007ebcb  mov     [rsp+38h+var_10], rax
0x18007ebd0  mov     rdx, [rdi+68h]
0x18007ebd4  xor     eax, eax
0x18007ebd6  cmp     cs:?s_SIMDFeatures@X64SIMDMath@AudioMathSpace@@2W4SIMDFeatures@12@B, 4; AudioMathSpace::X64SIMDMath::SIMDFeatures const AudioMathSpace::X64SIMDMath::s_SIMDFeatures
0x18007ebdd  mov     r8d, ebx
0x18007ebe0  setl    al
0x18007ebe3  add     rcx, 78h ; 'x'
0x18007ebe7  mov     rax, [rsp+rax*8+38h+var_18]
0x18007ebec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebf1  mov     rcx, [rdi+10h]
0x18007ebf5  mov     eax, ebx
0x18007ebf7  mov     edx, [rcx+30h]
0x18007ebfa  movsxd  rcx, ebx
0x18007ebfd  mov     rbx, [rsp+38h+arg_0]
0x18007ec02  imul    rdx, rcx
0x18007ec06  shl     rdx, 2
0x18007ec0a  add     [rdi+68h], rdx
0x18007ec0e  add     rsp, 30h
0x18007ec12  pop     rdi
0x18007ec13  retn
```
