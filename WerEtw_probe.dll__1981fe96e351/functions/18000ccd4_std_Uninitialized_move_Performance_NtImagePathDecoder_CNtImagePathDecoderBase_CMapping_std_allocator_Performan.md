# std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)

- ea: `0x18000ccd4`
- end: `0x18000cd77`
- name: `??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf98`

## callees

- `0x18000ccd4`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 v4; // r10
  __int64 v5; // r11

  v3 = a1;
  if ( a1 != a2 )
  {
    v4 = a3 + 32;
    v5 = a1 + 32;
    do
    {
      *(_OWORD *)a3 = 0;
      *(_QWORD *)(a3 + 16) = 0;
      *(_QWORD *)(a3 + 24) = 0;
      *(_OWORD *)a3 = *(_OWORD *)v3;
      *(_OWORD *)(a3 + 16) = *(_OWORD *)(v3 + 16);
      *(_QWORD *)(v3 + 16) = 0;
      a3 += 64;
      *(_QWORD *)(v3 + 24) = 7;
      *(_WORD *)v3 = 0;
      v3 += 64;
      *(_OWORD *)v4 = 0;
      *(_QWORD *)(v4 + 16) = 0;
      *(_QWORD *)(v4 + 24) = 0;
      *(_OWORD *)v4 = *(_OWORD *)v5;
      v4 += 64;
      *(_OWORD *)(v4 - 48) = *(_OWORD *)(v5 + 16);
      *(_QWORD *)(v5 + 16) = 0;
      *(_QWORD *)(v5 + 24) = 7;
      *(_WORD *)v5 = 0;
      v5 += 64;
    }
    while ( v3 != a2 );
  }
  return a3;
}

```

## disassembly

```asm
0x18000ccd4  mov     r9, rcx
0x18000ccd7  cmp     rcx, rdx
0x18000ccda  jz      loc_18000CD73
0x18000cce0  lea     r10, [r8+20h]
0x18000cce4  lea     r11, [rcx+20h]
0x18000cce8  xor     eax, eax
0x18000ccea  xorps   xmm0, xmm0
0x18000cced  movups  xmmword ptr [r8], xmm0
0x18000ccf1  mov     qword ptr [r8+10h], 0
0x18000ccf9  xor     ecx, ecx
0x18000ccfb  mov     qword ptr [r8+18h], 0
0x18000cd03  movups  xmm0, xmmword ptr [r9]
0x18000cd07  movups  xmmword ptr [r8], xmm0
0x18000cd0b  movups  xmm1, xmmword ptr [r9+10h]
0x18000cd10  xorps   xmm0, xmm0
0x18000cd13  movups  xmmword ptr [r8+10h], xmm1
0x18000cd18  mov     qword ptr [r9+10h], 0
0x18000cd20  add     r8, 40h ; '@'
0x18000cd24  mov     qword ptr [r9+18h], 7
0x18000cd2c  mov     [r9], ax
0x18000cd30  add     r9, 40h ; '@'
0x18000cd34  movups  xmmword ptr [r10], xmm0
0x18000cd38  mov     [r10+10h], rax
0x18000cd3c  mov     [r10+18h], rax
0x18000cd40  movups  xmm0, xmmword ptr [r11]
0x18000cd44  movups  xmmword ptr [r10], xmm0
0x18000cd48  lea     r10, [r10+40h]
0x18000cd4c  movups  xmm1, xmmword ptr [r11+10h]
0x18000cd51  movups  xmmword ptr [r10-30h], xmm1
0x18000cd56  mov     [r11+10h], rax
0x18000cd5a  mov     qword ptr [r11+18h], 7
0x18000cd62  mov     [r11], cx
0x18000cd66  lea     r11, [r11+40h]
0x18000cd6a  cmp     r9, rdx
0x18000cd6d  jnz     loc_18000CCE8
0x18000cd73  mov     rax, r8
0x18000cd76  retn
```
