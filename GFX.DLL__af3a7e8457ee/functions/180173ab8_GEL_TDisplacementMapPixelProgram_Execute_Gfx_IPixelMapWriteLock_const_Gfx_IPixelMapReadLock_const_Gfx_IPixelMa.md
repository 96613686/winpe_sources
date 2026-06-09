# `GEL::TDisplacementMapPixelProgram::Execute(Gfx::IPixelMapWriteLock const &,Gfx::IPixelMapReadLock const &,Gfx::IPixelMapReadLock const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::IAbortSignal const *)'::`2'::_lambda_1_::operator()(Math::TUnits<uint,Math::DevicePixels>,Math::TUnits<uint,Math::DevicePixels>)

- ea: `0x180173ab8`
- end: `0x180173d98`
- name: `??R_lambda_1_@?1??Execute@TDisplacementMapPixelProgram@GEL@@UEBAXAEBUIPixelMapWriteLock@Gfx@@AEBUIPixelMapReadLock@5@1AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@2PEBUIAbortSignal@5@@Z@QEBA@V?$TUnits@IUDevicePixels@Math@@@8@4@Z`
- size: `736`
- prototype: `void __fastcall(float *, int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18017397c`
- `0x1801a59f0`
- `0x1801ad5c0`

## callees

- `0x1800f8c04`
- `0x180173ab8`
- `0x1801a5c9c`
- `0x180204a2a`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180173af2`
- `KERNEL32!GetCurrentThreadId` at `0x180173af2`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180173cd9`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180173d06`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180173cd9`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180173d06`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall `GEL::TDisplacementMapPixelProgram::Execute'::`2'::_lambda_1_::operator()(
        float *a1,
        int a2,
        unsigned int a3)
{
  int v6; // eax
  int v7; // esi
  unsigned int *v8; // r13
  __int64 v9; // rcx
  _DWORD *v10; // r12
  __int64 v11; // r14
  unsigned int v12; // ebx
  double v13; // xmm0_8
  double v14; // xmm0_8
  double v15; // xmm0_8
  double v16; // xmm0_8
  double v17; // xmm0_8
  double v18; // xmm0_8
  unsigned __int8 ChannelValue; // al
  __int64 v20; // rcx
  float v21; // xmm1_4
  int v22; // ebx
  double v23; // xmm6_8
  double v24; // xmm0_8
  int v25; // edx
  int v26; // eax
  __int64 v27; // r8
  int v28; // eax
  int v29; // [rsp+20h] [rbp-88h] BYREF
  __int64 v30; // [rsp+28h] [rbp-80h]
  char v31; // [rsp+30h] [rbp-78h]
  DWORD CurrentThreadId; // [rsp+34h] [rbp-74h]
  unsigned int v33; // [rsp+B8h] [rbp+10h]

  v30 = *((_QWORD *)a1 + 4);
  v31 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = 0;
  if ( !v30 )
    v6 = 16;
  v29 = v6;
  while ( a2 < a3 )
  {
    v7 = 0;
    v8 = (unsigned int *)(**((_QWORD **)a1 + 3) + *(_DWORD *)(*((_QWORD *)a1 + 3) + 16LL) * a2);
    v9 = *((_QWORD *)a1 + 2);
    v10 = (_DWORD *)(*(_QWORD *)v9 + *(_DWORD *)(v9 + 16) * a2);
    while ( (unsigned int)v7 < *(_DWORD *)(*((_QWORD *)a1 + 3) + 8LL) )
    {
      v11 = *(_QWORD *)a1;
      v12 = *v8++;
      if ( *(_BYTE *)(*(_QWORD *)a1 + 26LL) == 1 )
      {
        v13 = (double)BYTE2(v12) / 255.0;
        if ( v13 > 0.04045 )
          v14 = pow_0((v13 + 0.055) / 1.055, 2.4);
        else
          v14 = v13 / 12.92;
        BYTE2(v33) = (int)fmin(255.0, fmax(0.0, v14 * 255.0));
        v15 = (double)BYTE1(v12) / 255.0;
        if ( v15 > 0.04045 )
          v16 = pow_0((v15 + 0.055) / 1.055, 2.4);
        else
          v16 = v15 / 12.92;
        BYTE1(v33) = (int)fmin(255.0, fmax(0.0, v16 * 255.0));
        v17 = (double)(unsigned __int8)v12 / 255.0;
        if ( v17 > 0.04045 )
          v18 = pow_0((v17 + 0.055) / 1.055, 2.4);
        else
          v18 = v17 / 12.92;
        HIBYTE(v33) = HIBYTE(v12);
        LOBYTE(v33) = (int)fmin(255.0, fmax(0.0, v18 * 255.0));
        v12 = v33;
      }
      LOBYTE(v9) = *(_BYTE *)(v11 + 24);
      ChannelValue = GEL::TDisplacementMapPixelProgram::GetChannelValue(v9, v12);
      v20 = *(_QWORD *)a1;
      LOBYTE(v20) = *(_BYTE *)(*(_QWORD *)a1 + 25LL);
      v21 = (float)ChannelValue;
      v22 = (unsigned __int8)GEL::TDisplacementMapPixelProgram::GetChannelValue(v20, v12);
      v23 = round((float)((float)((float)(v21 * a1[10]) + (float)v7) + a1[11]));
      v24 = round((float)((float)((float)((float)v22 * a1[12]) + (float)a2) + a1[13]));
      v25 = (int)v23;
      if ( (int)v23 < 0 || v25 >= *((_DWORD *)a1 + 14) || (v26 = (int)v24, (int)v24 < 0) || v26 >= *((_DWORD *)a1 + 15) )
      {
        v28 = 0;
      }
      else
      {
        v27 = *((_QWORD *)a1 + 1);
        v9 = *(_DWORD *)(v27 + 16) * v26;
        v28 = *(_DWORD *)(v9 + 4LL * v25 + *(_QWORD *)v27);
      }
      *v10++ = v28;
      ++v7;
    }
    GEL::ScanlineAborter::NextLine((GEL::ScanlineAborter *)&v29);
    ++a2;
  }
}

```

## disassembly

```asm
0x180173ab8  mov     rax, rsp
0x180173abb  mov     [rax+8], rbx
0x180173abf  push    rbp
0x180173ac0  push    rsi
0x180173ac1  push    rdi
0x180173ac2  push    r12
0x180173ac4  push    r13
0x180173ac6  push    r14
0x180173ac8  push    r15
0x180173aca  sub     rsp, 70h
0x180173ace  mov     rbx, [rcx+20h]
0x180173ad2  xor     r14d, r14d
0x180173ad5  movaps  xmmword ptr [rax-48h], xmm6
0x180173ad9  mov     ebp, r8d
0x180173adc  movaps  xmmword ptr [rax-58h], xmm7
0x180173ae0  mov     edi, edx
0x180173ae2  movaps  xmmword ptr [rax-68h], xmm12
0x180173ae7  mov     r15, rcx
0x180173aea  mov     [rax-80h], rbx
0x180173aee  mov     [rax-78h], r14b
0x180173af2  call    cs:__imp_GetCurrentThreadId
0x180173af8  movsd   xmm7, cs:__real@406fe00000000000
0x180173b00  lea     ecx, [r14+10h]
0x180173b04  movsd   xmm12, cs:__real@3fa4b5dcc63f1412
0x180173b0d  test    rbx, rbx
0x180173b10  mov     [rsp+0A8h+var_74], eax
0x180173b14  mov     eax, r14d
0x180173b17  cmovz   eax, ecx
0x180173b1a  mov     [rsp+0A8h+var_88], eax
0x180173b1e  cmp     edi, ebp
0x180173b20  jnb     loc_180173D71
0x180173b26  mov     rcx, [r15+18h]
0x180173b2a  mov     eax, edi
0x180173b2c  mov     esi, r14d
0x180173b2f  imul    eax, [rcx+10h]
0x180173b33  movsxd  r13, eax
0x180173b36  mov     eax, edi
0x180173b38  add     r13, [rcx]
0x180173b3b  mov     rcx, [r15+10h]
0x180173b3f  imul    eax, [rcx+10h]
0x180173b43  movsxd  r12, eax
0x180173b46  add     r12, [rcx]
0x180173b49  mov     rax, [r15+18h]
0x180173b4d  cmp     esi, [rax+8]
0x180173b50  jnb     loc_180173D60
0x180173b56  mov     r14, [r15]
0x180173b59  mov     ebx, [r13+0]
0x180173b5d  add     r13, 4
0x180173b61  cmp     byte ptr [r14+1Ah], 1
0x180173b66  jnz     loc_180173C95
0x180173b6c  mov     eax, ebx
0x180173b6e  shr     eax, 10h
0x180173b71  movzx   eax, al
0x180173b74  movd    xmm0, eax
0x180173b78  cvtdq2pd xmm0, xmm0
0x180173b7c  divsd   xmm0, xmm7
0x180173b80  comisd  xmm12, xmm0
0x180173b85  jb      short loc_180173B91
0x180173b87  divsd   xmm0, cs:__real@4029d70a3d70a3d7
0x180173b8f  jmp     short loc_180173BAE
0x180173b91  addsd   xmm0, cs:__real@3fac28f5c28f5c29
0x180173b99  movsd   xmm1, cs:__real@4003333333333333; Y
0x180173ba1  divsd   xmm0, cs:__real@3ff0e147ae147ae1; X
0x180173ba9  call    pow_0
0x180173bae  mulsd   xmm0, xmm7
0x180173bb2  xorps   xmm1, xmm1
0x180173bb5  maxsd   xmm1, xmm0
0x180173bb9  movaps  xmm0, xmm7
0x180173bbc  minsd   xmm0, xmm1
0x180173bc0  cvttsd2si eax, xmm0
0x180173bc4  mov     byte ptr [rsp+0A8h+arg_8+2], al
0x180173bcb  mov     eax, ebx
0x180173bcd  shr     eax, 8
0x180173bd0  movzx   eax, al
0x180173bd3  movd    xmm0, eax
0x180173bd7  cvtdq2pd xmm0, xmm0
0x180173bdb  divsd   xmm0, xmm7
0x180173bdf  comisd  xmm12, xmm0
0x180173be4  jb      short loc_180173BF0
0x180173be6  divsd   xmm0, cs:__real@4029d70a3d70a3d7
0x180173bee  jmp     short loc_180173C0D
0x180173bf0  addsd   xmm0, cs:__real@3fac28f5c28f5c29
0x180173bf8  movsd   xmm1, cs:__real@4003333333333333; Y
0x180173c00  divsd   xmm0, cs:__real@3ff0e147ae147ae1; X
0x180173c08  call    pow_0
0x180173c0d  mulsd   xmm0, xmm7
0x180173c11  xorps   xmm1, xmm1
0x180173c14  maxsd   xmm1, xmm0
0x180173c18  movaps  xmm0, xmm7
0x180173c1b  minsd   xmm0, xmm1
0x180173c1f  cvttsd2si eax, xmm0
0x180173c23  mov     byte ptr [rsp+0A8h+arg_8+1], al
0x180173c2a  movzx   eax, bl
0x180173c2d  movd    xmm0, eax
0x180173c31  cvtdq2pd xmm0, xmm0
0x180173c35  divsd   xmm0, xmm7
0x180173c39  comisd  xmm12, xmm0
0x180173c3e  jb      short loc_180173C4A
0x180173c40  divsd   xmm0, cs:__real@4029d70a3d70a3d7
0x180173c48  jmp     short loc_180173C67
0x180173c4a  addsd   xmm0, cs:__real@3fac28f5c28f5c29
0x180173c52  movsd   xmm1, cs:__real@4003333333333333; Y
0x180173c5a  divsd   xmm0, cs:__real@3ff0e147ae147ae1; X
0x180173c62  call    pow_0
0x180173c67  mulsd   xmm0, xmm7
0x180173c6b  xorps   xmm1, xmm1
0x180173c6e  shr     ebx, 18h
0x180173c71  mov     byte ptr [rsp+0A8h+arg_8+3], bl
0x180173c78  maxsd   xmm1, xmm0
0x180173c7c  movaps  xmm0, xmm7
0x180173c7f  minsd   xmm0, xmm1
0x180173c83  cvttsd2si eax, xmm0
0x180173c87  mov     byte ptr [rsp+0A8h+arg_8], al
0x180173c8e  mov     ebx, [rsp+0A8h+arg_8]
0x180173c95  mov     cl, [r14+18h]
0x180173c99  mov     edx, ebx
0x180173c9b  call    ?GetChannelValue@TDisplacementMapPixelProgram@GEL@@CAEW4ChannelSelector@2@U?$TBGRA@E$01@ARC@@@Z; GEL::TDisplacementMapPixelProgram::GetChannelValue(GEL::ChannelSelector,ARC::TBGRA<uchar,2>)
0x180173ca0  mov     rcx, [r15]
0x180173ca3  mov     edx, ebx
0x180173ca5  movzx   r14d, al
0x180173ca9  mov     cl, [rcx+19h]
0x180173cac  call    ?GetChannelValue@TDisplacementMapPixelProgram@GEL@@CAEW4ChannelSelector@2@U?$TBGRA@E$01@ARC@@@Z; GEL::TDisplacementMapPixelProgram::GetChannelValue(GEL::ChannelSelector,ARC::TBGRA<uchar,2>)
0x180173cb1  xorps   xmm0, xmm0
0x180173cb4  movd    xmm1, r14d
0x180173cb9  cvtdq2ps xmm1, xmm1
0x180173cbc  mov     ecx, esi
0x180173cbe  movzx   ebx, al
0x180173cc1  cvtsi2ss xmm0, rcx
0x180173cc6  mulss   xmm1, dword ptr [r15+28h]
0x180173ccc  addss   xmm1, xmm0
0x180173cd0  addss   xmm1, dword ptr [r15+2Ch]
0x180173cd6  cvtps2pd xmm0, xmm1; X
0x180173cd9  call    cs:__imp_round
0x180173cdf  movd    xmm2, ebx
0x180173ce3  xorps   xmm1, xmm1
0x180173ce6  cvtdq2ps xmm2, xmm2
0x180173ce9  mov     eax, edi
0x180173ceb  movaps  xmm6, xmm0
0x180173cee  mulss   xmm2, dword ptr [r15+30h]
0x180173cf4  cvtsi2ss xmm1, rax
0x180173cf9  addss   xmm2, xmm1
0x180173cfd  addss   xmm2, dword ptr [r15+34h]
0x180173d03  cvtps2pd xmm0, xmm2; X
0x180173d06  call    cs:__imp_round
0x180173d0c  cvttsd2si edx, xmm6
0x180173d10  xor     r14d, r14d
0x180173d13  test    edx, edx
0x180173d15  js      short loc_180173D46
0x180173d17  cmp     edx, [r15+38h]
0x180173d1b  jge     short loc_180173D46
0x180173d1d  cvttsd2si eax, xmm0
0x180173d21  test    eax, eax
0x180173d23  js      short loc_180173D46
0x180173d25  cmp     eax, [r15+3Ch]
0x180173d29  jge     short loc_180173D46
0x180173d2b  mov     r8, [r15+8]
0x180173d2f  imul    eax, [r8+10h]
0x180173d34  movsxd  rcx, eax
0x180173d37  movsxd  rax, edx
0x180173d3a  lea     rdx, [rcx+rax*4]
0x180173d3e  mov     rax, [r8]
0x180173d41  mov     eax, [rdx+rax]
0x180173d44  jmp     short loc_180173D51
0x180173d46  mov     [rsp+0A8h+arg_10], r14d
0x180173d4e  mov     eax, r14d
0x180173d51  mov     [r12], eax
0x180173d55  add     r12, 4
0x180173d59  inc     esi
0x180173d5b  jmp     loc_180173B49
0x180173d60  lea     rcx, [rsp+0A8h+var_88]; this
0x180173d65  call    ?NextLine@ScanlineAborter@GEL@@QEAAXXZ; GEL::ScanlineAborter::NextLine(void)
0x180173d6a  inc     edi
0x180173d6c  jmp     loc_180173B1E
0x180173d71  movaps  xmm6, [rsp+0A8h+var_48]
0x180173d76  lea     r11, [rsp+0A8h+var_38]
0x180173d7b  mov     rbx, [r11+40h]
0x180173d7f  movaps  xmm12, xmmword ptr [r11-30h]
0x180173d84  movaps  xmm7, [rsp+0A8h+var_58]
0x180173d89  mov     rsp, r11
0x180173d8c  pop     r15
0x180173d8e  pop     r14
0x180173d90  pop     r13
0x180173d92  pop     r12
0x180173d94  pop     rdi
0x180173d95  pop     rsi
0x180173d96  pop     rbp
0x180173d97  retn
```
