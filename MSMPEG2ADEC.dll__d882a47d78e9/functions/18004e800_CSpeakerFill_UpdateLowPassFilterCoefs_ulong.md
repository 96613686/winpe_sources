# CSpeakerFill::UpdateLowPassFilterCoefs(ulong)

- ea: `0x18004e800`
- end: `0x18004eb14`
- name: `?UpdateLowPassFilterCoefs@CSpeakerFill@@AEAAXK@Z`
- size: `788`
- prototype: `void __fastcall(CSpeakerFill *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18004dad0`

## callees

- `0x18004e800`
- `0x18004eb20`

## pseudocode

```c
void __fastcall CSpeakerFill::UpdateLowPassFilterCoefs(CSpeakerFill *this, rsize_t a2, __int64 a3, rsize_t a4)
{
  double v4; // xmm6_8
  double v5; // xmm12_8
  double v6; // xmm8_8
  double v7; // xmm11_8
  double v8; // xmm3_8
  double v9; // xmm2_8
  double v10; // xmm12_8
  double v11; // xmm1_8
  double v12; // xmm8_8
  double v13; // xmm9_8
  double v14; // xmm11_8

  if ( (unsigned int)a2 <= 0x5DC0 )
  {
    switch ( (_DWORD)a2 )
    {
      case 0x5DC0:
        memcpy_s_0((char *)this + 80, a2, qword_180098C70, a4);
        return;
      case 0:
        *((_OWORD *)this + 5) = 0;
        *((_OWORD *)this + 6) = 0;
        *((_OWORD *)this + 7) = 0;
        *((_OWORD *)this + 8) = 0;
        return;
      case 0x1F40:
        memcpy_s_0((char *)this + 80, a2, qword_180098B70, a4);
        return;
      case 0x2B11:
        memcpy_s_0((char *)this + 80, a2, qword_180098BB0, a4);
        return;
      case 0x3E80:
        memcpy_s_0((char *)this + 80, a2, qword_180098BF0, a4);
        return;
      case 0x5622:
        memcpy_s_0((char *)this + 80, a2, qword_180098C30, a4);
        return;
    }
    goto LABEL_18;
  }
  switch ( (_DWORD)a2 )
  {
    case 0x7D00:
      memcpy_s_0((char *)this + 80, a2, qword_180098CB0, a4);
      break;
    case 0xAC44:
      memcpy_s_0((char *)this + 80, a2, qword_180098CF0, a4);
      break;
    case 0xBB80:
      memcpy_s_0((char *)this + 80, a2, qword_180098D30, a4);
      break;
    case 0x17700:
      memcpy_s_0((char *)this + 80, a2, qword_180098D70, a4);
      break;
    default:
LABEL_18:
      *((_QWORD *)this + 14) = 0x3FF0000000000000LL;
      v4 = (double)(int)a2 * 0.003978873577297383;
      v5 = (double)(int)a2 * (double)(int)a2 * 0.00001583143494411528;
      v6 = 0.8049844718999243 - v5;
      v7 = v5 * 1.007230589874905;
      v8 = (v4 + 1.006230589874905) * v4 + 0.8049844718999243;
      v9 = (0.001 - v4) / (v4 + 0.001);
      v10 = (v5 - v4 * 1.006230589874905 + 0.8049844718999243) / v8;
      v11 = (v7 + v4 * 0.8059844718999243 + 0.0008049844718999243) * (1.0 / v8) * (1.0 / (v4 + 0.001));
      v12 = (v6 + v6) / v8;
      v13 = (0.0008049844718999243 - v7 + 0.0008049844718999243 - v7) * (1.0 / v8) * (1.0 / (v4 + 0.001));
      v14 = (v7 - v4 * 0.8059844718999243 + 0.0008049844718999243) * (1.0 / v8) * (1.0 / (v4 + 0.001));
      *((double *)this + 10) = v11;
      *((double *)this + 13) = v14;
      *((double *)this + 11) = v13 + v11;
      *((double *)this + 12) = v14 + v13;
      *((double *)this + 16) = v9 * v12 + v10;
      *((double *)this + 15) = v9 + v12;
      *((double *)this + 17) = v9 * v10;
      return;
  }
}

```

## disassembly

```asm
0x18004e800  sub     rsp, 88h
0x18004e807  cmp     edx, 5DC0h
0x18004e80d  ja      loc_18004E8D7
0x18004e813  jz      loc_18004E8C0
0x18004e819  test    edx, edx
0x18004e81b  jz      loc_18004E8A1
0x18004e821  cmp     edx, 1F40h
0x18004e827  jz      short loc_18004E88A
0x18004e829  cmp     edx, 2B11h
0x18004e82f  jz      short loc_18004E873
0x18004e831  cmp     edx, 3E80h
0x18004e837  jz      short loc_18004E85C
0x18004e839  cmp     edx, 5622h
0x18004e83f  jnz     loc_18004E907
0x18004e845  lea     r8, qword_180098C30
0x18004e84c  add     rcx, 50h ; 'P'
0x18004e850  add     rsp, 88h
0x18004e857  jmp     memcpy_s_0
0x18004e85c  lea     r8, qword_180098BF0
0x18004e863  add     rcx, 50h ; 'P'
0x18004e867  add     rsp, 88h
0x18004e86e  jmp     memcpy_s_0
0x18004e873  lea     r8, qword_180098BB0
0x18004e87a  add     rcx, 50h ; 'P'
0x18004e87e  add     rsp, 88h
0x18004e885  jmp     memcpy_s_0
0x18004e88a  lea     r8, qword_180098B70
0x18004e891  add     rcx, 50h ; 'P'
0x18004e895  add     rsp, 88h
0x18004e89c  jmp     memcpy_s_0
0x18004e8a1  xorps   xmm0, xmm0
0x18004e8a4  movups  xmmword ptr [rcx+50h], xmm0
0x18004e8a8  movups  xmmword ptr [rcx+60h], xmm0
0x18004e8ac  movups  xmmword ptr [rcx+70h], xmm0
0x18004e8b0  movups  xmmword ptr [rcx+80h], xmm0
0x18004e8b7  add     rsp, 88h
0x18004e8be  retn
0x18004e8c0  lea     r8, qword_180098C70
0x18004e8c7  add     rcx, 50h ; 'P'
0x18004e8cb  add     rsp, 88h
0x18004e8d2  jmp     memcpy_s_0
0x18004e8d7  cmp     edx, 7D00h
0x18004e8dd  jz      loc_18004EAFD
0x18004e8e3  cmp     edx, 0AC44h
0x18004e8e9  jz      loc_18004EAE6
0x18004e8ef  cmp     edx, 0BB80h
0x18004e8f5  jz      loc_18004EACF
0x18004e8fb  cmp     edx, 17700h
0x18004e901  jz      loc_18004EAB8
0x18004e907  movsd   xmm1, cs:__real@3fe9c26ecb9322dd
0x18004e90f  movsd   xmm2, cs:__real@3f50624dd2f1a9fc
0x18004e917  movsd   xmm5, cs:__real@3ff0000000000000
0x18004e91f  movaps  [rsp+88h+var_18], xmm6
0x18004e924  movaps  xmm4, xmm5
0x18004e927  movaps  [rsp+88h+var_28], xmm8
0x18004e92d  movaps  xmm8, xmm1
0x18004e931  movaps  [rsp+88h+var_38], xmm9
0x18004e937  movsd   xmm9, cs:__real@3f4a60b2fd843c47
0x18004e940  movaps  [rsp+88h+var_48], xmm10
0x18004e946  movaps  [rsp+88h+var_58], xmm11
0x18004e94c  movaps  [rsp+88h+var_68], xmm12
0x18004e952  xorps   xmm12, xmm12
0x18004e956  mov     eax, edx
0x18004e958  cvtsi2sd xmm12, rax
0x18004e95d  mov     rax, 3FF0000000000000h
0x18004e967  mov     [rcx+70h], rax
0x18004e96b  movaps  xmm6, xmm12
0x18004e96f  mulsd   xmm12, xmm12
0x18004e974  mulsd   xmm6, cs:__real@3f704c26be3b06cf
0x18004e97c  mulsd   xmm12, cs:__real@3ef099b7ece30ecd
0x18004e985  movaps  xmm0, xmm6
0x18004e988  movaps  xmm3, xmm6
0x18004e98b  mulsd   xmm0, cs:__real@3ff019853f3bf5ca
0x18004e993  movaps  xmm10, xmm6
0x18004e997  addsd   xmm3, cs:__real@3ff019853f3bf5ca
0x18004e99f  mulsd   xmm10, cs:__real@3fe9ca9ff27c9bb2
0x18004e9a8  subsd   xmm8, xmm12
0x18004e9ad  movaps  xmm11, xmm12
0x18004e9b1  subsd   xmm12, xmm0
0x18004e9b6  mulsd   xmm11, cs:__real@3ff01d9dd2b0b234
0x18004e9bf  movaps  xmm0, xmm6
0x18004e9c2  addsd   xmm0, xmm2
0x18004e9c6  mulsd   xmm3, xmm6
0x18004e9ca  subsd   xmm2, xmm6
0x18004e9ce  movaps  xmm6, [rsp+88h+var_18]
0x18004e9d3  addsd   xmm12, xmm1
0x18004e9d8  subsd   xmm9, xmm11
0x18004e9dd  addsd   xmm3, xmm1
0x18004e9e1  movaps  xmm1, xmm11
0x18004e9e5  divsd   xmm5, xmm0
0x18004e9e9  divsd   xmm2, xmm0
0x18004e9ed  addsd   xmm1, xmm10
0x18004e9f2  subsd   xmm11, xmm10
0x18004e9f7  movaps  xmm10, [rsp+88h+var_48]
0x18004e9fd  divsd   xmm4, xmm3
0x18004ea01  addsd   xmm1, cs:__real@3f4a60b2fd843c47
0x18004ea09  addsd   xmm11, cs:__real@3f4a60b2fd843c47
0x18004ea12  addsd   xmm9, xmm9
0x18004ea17  divsd   xmm12, xmm3
0x18004ea1c  mulsd   xmm1, xmm4
0x18004ea20  addsd   xmm8, xmm8
0x18004ea25  mulsd   xmm9, xmm4
0x18004ea2a  mulsd   xmm11, xmm4
0x18004ea2f  mulsd   xmm1, xmm5
0x18004ea33  divsd   xmm8, xmm3
0x18004ea38  mulsd   xmm9, xmm5
0x18004ea3d  mulsd   xmm11, xmm5
0x18004ea42  movsd   qword ptr [rcx+50h], xmm1
0x18004ea47  movaps  xmm0, xmm9
0x18004ea4b  addsd   xmm0, xmm1
0x18004ea4f  movaps  xmm1, xmm2
0x18004ea52  mulsd   xmm1, xmm8
0x18004ea57  movsd   qword ptr [rcx+68h], xmm11
0x18004ea5d  movsd   qword ptr [rcx+58h], xmm0
0x18004ea62  movaps  xmm0, xmm11
0x18004ea66  movaps  xmm11, [rsp+88h+var_58]
0x18004ea6c  addsd   xmm0, xmm9
0x18004ea71  movaps  xmm9, [rsp+88h+var_38]
0x18004ea77  addsd   xmm1, xmm12
0x18004ea7c  movsd   qword ptr [rcx+60h], xmm0
0x18004ea81  movaps  xmm0, xmm2
0x18004ea84  addsd   xmm0, xmm8
0x18004ea89  mulsd   xmm2, xmm12
0x18004ea8e  movaps  xmm12, [rsp+88h+var_68]
0x18004ea94  movaps  xmm8, [rsp+88h+var_28]
0x18004ea9a  movsd   qword ptr [rcx+80h], xmm1
0x18004eaa2  movsd   qword ptr [rcx+78h], xmm0
0x18004eaa7  movsd   qword ptr [rcx+88h], xmm2
0x18004eaaf  add     rsp, 88h
0x18004eab6  retn
0x18004eab8  lea     r8, qword_180098D70
0x18004eabf  add     rcx, 50h ; 'P'
0x18004eac3  add     rsp, 88h
0x18004eaca  jmp     memcpy_s_0
0x18004eacf  lea     r8, qword_180098D30
0x18004ead6  add     rcx, 50h ; 'P'
0x18004eada  add     rsp, 88h
0x18004eae1  jmp     memcpy_s_0
0x18004eae6  lea     r8, qword_180098CF0
0x18004eaed  add     rcx, 50h ; 'P'
0x18004eaf1  add     rsp, 88h
0x18004eaf8  jmp     memcpy_s_0
0x18004eafd  lea     r8, qword_180098CB0
0x18004eb04  add     rcx, 50h ; 'P'
0x18004eb08  add     rsp, 88h
0x18004eb0f  jmp     memcpy_s_0
```
