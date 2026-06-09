# `GEL::TDisplacementMapPixelProgram::Execute(Gfx::IPixelMapWriteLock const &,Gfx::IPixelMapReadLock const &,Gfx::IPixelMapReadLock const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::IAbortSignal const *)'::`2'::_lambda_1_::operator()(Math::TUnits<uint,Math::DevicePixels>,Math::TUnits<uint,Math::DevicePixels>)

- ea: `0x18017814c`
- end: `0x18017842c`
- name: `??R_lambda_1_@?1??Execute@TDisplacementMapPixelProgram@GEL@@UEBAXAEBUIPixelMapWriteLock@Gfx@@AEBUIPixelMapReadLock@5@1AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@2PEBUIAbortSignal@5@@Z@QEBA@V?$TUnits@IUDevicePixels@Math@@@8@4@Z`
- size: `736`
- prototype: `void __fastcall(float *, int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180178010`
- `0x1801a9640`
- `0x1801b11e0`

## callees

- `0x18005f3d4`
- `0x18017814c`
- `0x1801a98ec`
- `0x180207d5a`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180178186`
- `KERNEL32!GetCurrentThreadId` at `0x180178186`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18017836d`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18017839a`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18017836d`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18017839a`

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
0x18017814c  mov     rax, rsp
0x18017814f  mov     [rax+8], rbx
0x180178153  push    rbp
0x180178154  push    rsi
0x180178155  push    rdi
0x180178156  push    r12
0x180178158  push    r13
0x18017815a  push    r14
0x18017815c  push    r15
0x18017815e  sub     rsp, 70h
0x180178162  mov     rbx, [rcx+20h]
0x180178166  xor     r14d, r14d
0x180178169  movaps  xmmword ptr [rax-48h], xmm6
0x18017816d  mov     ebp, r8d
0x180178170  movaps  xmmword ptr [rax-58h], xmm7
0x180178174  mov     edi, edx
0x180178176  movaps  xmmword ptr [rax-68h], xmm12
0x18017817b  mov     r15, rcx
0x18017817e  mov     [rax-80h], rbx
0x180178182  mov     [rax-78h], r14b
0x180178186  call    cs:__imp_GetCurrentThreadId
0x18017818c  movsd   xmm7, cs:__real@406fe00000000000
0x180178194  lea     ecx, [r14+10h]
0x180178198  movsd   xmm12, cs:__real@3fa4b5dcc63f1412
0x1801781a1  test    rbx, rbx
0x1801781a4  mov     [rsp+0A8h+var_74], eax
0x1801781a8  mov     eax, r14d
0x1801781ab  cmovz   eax, ecx
0x1801781ae  mov     [rsp+0A8h+var_88], eax
0x1801781b2  cmp     edi, ebp
0x1801781b4  jnb     loc_180178405
0x1801781ba  mov     rcx, [r15+18h]
0x1801781be  mov     eax, edi
0x1801781c0  mov     esi, r14d
0x1801781c3  imul    eax, [rcx+10h]
0x1801781c7  movsxd  r13, eax
0x1801781ca  mov     eax, edi
0x1801781cc  add     r13, [rcx]
0x1801781cf  mov     rcx, [r15+10h]
0x1801781d3  imul    eax, [rcx+10h]
0x1801781d7  movsxd  r12, eax
0x1801781da  add     r12, [rcx]
0x1801781dd  mov     rax, [r15+18h]
0x1801781e1  cmp     esi, [rax+8]
0x1801781e4  jnb     loc_1801783F4
0x1801781ea  mov     r14, [r15]
0x1801781ed  mov     ebx, [r13+0]
0x1801781f1  add     r13, 4
0x1801781f5  cmp     byte ptr [r14+1Ah], 1
0x1801781fa  jnz     loc_180178329
0x180178200  mov     eax, ebx
0x180178202  shr     eax, 10h
0x180178205  movzx   eax, al
0x180178208  movd    xmm0, eax
0x18017820c  cvtdq2pd xmm0, xmm0
0x180178210  divsd   xmm0, xmm7
0x180178214  comisd  xmm12, xmm0
0x180178219  jb      short loc_180178225
0x18017821b  divsd   xmm0, cs:__real@4029d70a3d70a3d7
0x180178223  jmp     short loc_180178242
0x180178225  addsd   xmm0, cs:__real@3fac28f5c28f5c29
0x18017822d  movsd   xmm1, cs:__real@4003333333333333; Y
0x180178235  divsd   xmm0, cs:__real@3ff0e147ae147ae1; X
0x18017823d  call    pow_0
0x180178242  mulsd   xmm0, xmm7
0x180178246  xorps   xmm1, xmm1
0x180178249  maxsd   xmm1, xmm0
0x18017824d  movaps  xmm0, xmm7
0x180178250  minsd   xmm0, xmm1
0x180178254  cvttsd2si eax, xmm0
0x180178258  mov     byte ptr [rsp+0A8h+arg_8+2], al
0x18017825f  mov     eax, ebx
0x180178261  shr     eax, 8
0x180178264  movzx   eax, al
0x180178267  movd    xmm0, eax
0x18017826b  cvtdq2pd xmm0, xmm0
0x18017826f  divsd   xmm0, xmm7
0x180178273  comisd  xmm12, xmm0
0x180178278  jb      short loc_180178284
0x18017827a  divsd   xmm0, cs:__real@4029d70a3d70a3d7
0x180178282  jmp     short loc_1801782A1
0x180178284  addsd   xmm0, cs:__real@3fac28f5c28f5c29
0x18017828c  movsd   xmm1, cs:__real@4003333333333333; Y
0x180178294  divsd   xmm0, cs:__real@3ff0e147ae147ae1; X
0x18017829c  call    pow_0
0x1801782a1  mulsd   xmm0, xmm7
0x1801782a5  xorps   xmm1, xmm1
0x1801782a8  maxsd   xmm1, xmm0
0x1801782ac  movaps  xmm0, xmm7
0x1801782af  minsd   xmm0, xmm1
0x1801782b3  cvttsd2si eax, xmm0
0x1801782b7  mov     byte ptr [rsp+0A8h+arg_8+1], al
0x1801782be  movzx   eax, bl
0x1801782c1  movd    xmm0, eax
0x1801782c5  cvtdq2pd xmm0, xmm0
0x1801782c9  divsd   xmm0, xmm7
0x1801782cd  comisd  xmm12, xmm0
0x1801782d2  jb      short loc_1801782DE
0x1801782d4  divsd   xmm0, cs:__real@4029d70a3d70a3d7
0x1801782dc  jmp     short loc_1801782FB
0x1801782de  addsd   xmm0, cs:__real@3fac28f5c28f5c29
0x1801782e6  movsd   xmm1, cs:__real@4003333333333333; Y
0x1801782ee  divsd   xmm0, cs:__real@3ff0e147ae147ae1; X
0x1801782f6  call    pow_0
0x1801782fb  mulsd   xmm0, xmm7
0x1801782ff  xorps   xmm1, xmm1
0x180178302  shr     ebx, 18h
0x180178305  mov     byte ptr [rsp+0A8h+arg_8+3], bl
0x18017830c  maxsd   xmm1, xmm0
0x180178310  movaps  xmm0, xmm7
0x180178313  minsd   xmm0, xmm1
0x180178317  cvttsd2si eax, xmm0
0x18017831b  mov     byte ptr [rsp+0A8h+arg_8], al
0x180178322  mov     ebx, [rsp+0A8h+arg_8]
0x180178329  mov     cl, [r14+18h]
0x18017832d  mov     edx, ebx
0x18017832f  call    ?GetChannelValue@TDisplacementMapPixelProgram@GEL@@CAEW4ChannelSelector@2@U?$TBGRA@E$01@ARC@@@Z; GEL::TDisplacementMapPixelProgram::GetChannelValue(GEL::ChannelSelector,ARC::TBGRA<uchar,2>)
0x180178334  mov     rcx, [r15]
0x180178337  mov     edx, ebx
0x180178339  movzx   r14d, al
0x18017833d  mov     cl, [rcx+19h]
0x180178340  call    ?GetChannelValue@TDisplacementMapPixelProgram@GEL@@CAEW4ChannelSelector@2@U?$TBGRA@E$01@ARC@@@Z; GEL::TDisplacementMapPixelProgram::GetChannelValue(GEL::ChannelSelector,ARC::TBGRA<uchar,2>)
0x180178345  xorps   xmm0, xmm0
0x180178348  movd    xmm1, r14d
0x18017834d  cvtdq2ps xmm1, xmm1
0x180178350  mov     ecx, esi
0x180178352  movzx   ebx, al
0x180178355  cvtsi2ss xmm0, rcx
0x18017835a  mulss   xmm1, dword ptr [r15+28h]
0x180178360  addss   xmm1, xmm0
0x180178364  addss   xmm1, dword ptr [r15+2Ch]
0x18017836a  cvtps2pd xmm0, xmm1; X
0x18017836d  call    cs:__imp_round
0x180178373  movd    xmm2, ebx
0x180178377  xorps   xmm1, xmm1
0x18017837a  cvtdq2ps xmm2, xmm2
0x18017837d  mov     eax, edi
0x18017837f  movaps  xmm6, xmm0
0x180178382  mulss   xmm2, dword ptr [r15+30h]
0x180178388  cvtsi2ss xmm1, rax
0x18017838d  addss   xmm2, xmm1
0x180178391  addss   xmm2, dword ptr [r15+34h]
0x180178397  cvtps2pd xmm0, xmm2; X
0x18017839a  call    cs:__imp_round
0x1801783a0  cvttsd2si edx, xmm6
0x1801783a4  xor     r14d, r14d
0x1801783a7  test    edx, edx
0x1801783a9  js      short loc_1801783DA
0x1801783ab  cmp     edx, [r15+38h]
0x1801783af  jge     short loc_1801783DA
0x1801783b1  cvttsd2si eax, xmm0
0x1801783b5  test    eax, eax
0x1801783b7  js      short loc_1801783DA
0x1801783b9  cmp     eax, [r15+3Ch]
0x1801783bd  jge     short loc_1801783DA
0x1801783bf  mov     r8, [r15+8]
0x1801783c3  imul    eax, [r8+10h]
0x1801783c8  movsxd  rcx, eax
0x1801783cb  movsxd  rax, edx
0x1801783ce  lea     rdx, [rcx+rax*4]
0x1801783d2  mov     rax, [r8]
0x1801783d5  mov     eax, [rdx+rax]
0x1801783d8  jmp     short loc_1801783E5
0x1801783da  mov     [rsp+0A8h+arg_10], r14d
0x1801783e2  mov     eax, r14d
0x1801783e5  mov     [r12], eax
0x1801783e9  add     r12, 4
0x1801783ed  inc     esi
0x1801783ef  jmp     loc_1801781DD
0x1801783f4  lea     rcx, [rsp+0A8h+var_88]; this
0x1801783f9  call    ?NextLine@ScanlineAborter@GEL@@QEAAXXZ; GEL::ScanlineAborter::NextLine(void)
0x1801783fe  inc     edi
0x180178400  jmp     loc_1801781B2
0x180178405  movaps  xmm6, [rsp+0A8h+var_48]
0x18017840a  lea     r11, [rsp+0A8h+var_38]
0x18017840f  mov     rbx, [r11+40h]
0x180178413  movaps  xmm12, xmmword ptr [r11-30h]
0x180178418  movaps  xmm7, [rsp+0A8h+var_58]
0x18017841d  mov     rsp, r11
0x180178420  pop     r15
0x180178422  pop     r14
0x180178424  pop     r13
0x180178426  pop     r12
0x180178428  pop     rdi
0x180178429  pop     rsi
0x18017842a  pop     rbp
0x18017842b  retn
```
