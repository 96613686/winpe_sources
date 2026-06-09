# Art::CreateColorSchemeEffect(Art::ColorScheme const &,int,int,bool)

- ea: `0x180556c2c`
- end: `0x180556f0b`
- name: `?CreateColorSchemeEffect@Art@@YA?AV?$TCntPtr@UIEffect@GEL@@@Ofc@@AEBVColorScheme@1@HH_N@Z`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18025f02c`

## callees

- `0x180037550`
- `0x180037d30`
- `0x180071720`
- `0x180556c2c`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180556c6d`
- `KERNEL32!MulDiv` at `0x180556c88`
- `KERNEL32!MulDiv` at `0x180556c9a`
- `KERNEL32!MulDiv` at `0x180556cb1`
- `KERNEL32!MulDiv` at `0x180556cce`
- `KERNEL32!MulDiv` at `0x180556c6d`
- `KERNEL32!MulDiv` at `0x180556c88`
- `KERNEL32!MulDiv` at `0x180556c9a`
- `KERNEL32!MulDiv` at `0x180556cb1`
- `KERNEL32!MulDiv` at `0x180556cce`
- `gfx!?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x180556e9f`
- `gfx!?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x180556e9f`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x180556e23`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x180556e23`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180556dde`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x180556dde`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x180556ce0`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x180556ce0`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180556d3d`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x180556d3d`

## pseudocode

```c
_QWORD *__fastcall Art::CreateColorSchemeEffect(_QWORD *a1, __int64 a2, int a3, int a4, unsigned __int8 a5)
{
  int v7; // r14d
  int v8; // esi
  int v9; // edi
  int v10; // ebx
  int v11; // r12d
  int v12; // r13d
  double v13; // xmm7_8
  double v14; // xmm8_8
  __int64 *v15; // r15
  double *v16; // rax
  double v17; // rsi
  Art::Color *PresetSchemeColor; // rax
  unsigned int COLORREF; // eax
  double *v20; // rax
  double v21; // r14
  __int64 v22; // rbx
  void (__fastcall *v23)(__int64, _QWORD); // rdi
  _QWORD *v24; // rax
  __int64 *v25; // rax
  __int64 v26; // rcx
  int v28; // [rsp+28h] [rbp-71h]
  __int64 v29; // [rsp+30h] [rbp-69h] BYREF
  __int64 v30; // [rsp+38h] [rbp-61h] BYREF
  float v31[6]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v32; // [rsp+58h] [rbp-41h] BYREF
  __int64 v33; // [rsp+60h] [rbp-39h] BYREF
  double v34[10]; // [rsp+68h] [rbp-31h] BYREF

  v7 = MulDiv(a3, 6, 64) + 1;
  v8 = MulDiv(a4, 5, 48) + 1;
  v28 = v7 + MulDiv(a3, 1, 64) - 1;
  v9 = MulDiv(a3, 3, 64);
  v10 = MulDiv(a4, 45, 48) + -3 - v8;
  GEL::IEffectContainer::Create(&v29);
  v11 = v9 + (a5 ^ 1) + 2;
  v12 = v11 + v7 - 1;
  v13 = (double)v10;
  v14 = (double)(v10 + v8 - 1);
  v15 = qword_180BF3AB8;
  do
  {
    v34[0] = (double)v11;
    v34[1] = v13;
    v34[2] = (double)v12;
    v34[3] = v14;
    v16 = (double *)GEL::IRectanglePath::Create(&v32, v34);
    v17 = *v16;
    *v16 = 0.0;
    v34[4] = v17;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
    PresetSchemeColor = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, *(unsigned int *)v15);
    COLORREF = Art::Color::GetCOLORREF(PresetSchemeColor);
    v31[0] = (float)(unsigned __int8)COLORREF / 255.0;
    v31[1] = (float)BYTE1(COLORREF) / 255.0;
    v31[2] = (float)BYTE2(COLORREF) / 255.0;
    v31[3] = 1.0;
    v20 = (double *)GEL::IBrushSolid::Create(&v33, v31, 0);
    v21 = *v20;
    *v20 = 0.0;
    v34[5] = v21;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
    v22 = v29;
    v23 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 144LL);
    v24 = (_QWORD *)GEL::IEffectFilledPath::Create(&v30, *(_QWORD *)&v17, *(_QWORD *)&v21, 0);
    v23(v22, *v24);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    v11 += v28;
    v12 += v28;
    if ( v21 != 0.0 )
      (*(void (__fastcall **)(double))(**(_QWORD **)&v21 + 8LL))(COERCE_DOUBLE(*(_QWORD *)&v21));
    if ( v17 != 0.0 )
      (*(void (__fastcall **)(double))(**(_QWORD **)&v17 + 8LL))(COERCE_DOUBLE(*(_QWORD *)&v17));
    v15 = (__int64 *)((char *)v15 + 4);
  }
  while ( (__int64)v15 < (__int64)&Art::TEnumToString<enum Art::AlgorithmStateType>::s_enumStringTable );
  v25 = (__int64 *)GEL::IEffectAliased::Create(&v30, v29);
  v26 = *v25;
  *v25 = 0;
  *a1 = v26;
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  return a1;
}

```

## disassembly

```asm
0x180556c2c  mov     rax, rsp
0x180556c2f  mov     [rax+18h], rbx
0x180556c33  mov     [rax+10h], rdx
0x180556c37  mov     [rax+8], rcx
0x180556c3b  push    rbp
0x180556c3c  push    rsi
0x180556c3d  push    rdi
0x180556c3e  push    r12
0x180556c40  push    r13
0x180556c42  push    r14
0x180556c44  push    r15
0x180556c46  lea     rbp, [rax-57h]
0x180556c4a  sub     rsp, 0B0h
0x180556c51  movaps  xmmword ptr [rax-48h], xmm7
0x180556c55  movaps  xmmword ptr [rax-58h], xmm8
0x180556c5a  mov     r15d, r9d
0x180556c5d  mov     ebx, r8d
0x180556c60  mov     edi, 40h ; '@'
0x180556c65  mov     r8d, edi; nDenominator
0x180556c68  lea     edx, [rdi-3Ah]; nNumerator
0x180556c6b  mov     ecx, ebx; nNumber
0x180556c6d  call    cs:__imp_MulDiv
0x180556c73  lea     r12d, [rdi-3Fh]
0x180556c77  lea     r14d, [r12+rax]
0x180556c7b  lea     r13d, [rdi-10h]
0x180556c7f  mov     r8d, r13d; nDenominator
0x180556c82  lea     edx, [rdi-3Bh]; nNumerator
0x180556c85  mov     ecx, r15d; nNumber
0x180556c88  call    cs:__imp_MulDiv
0x180556c8e  lea     esi, [r12+rax]
0x180556c92  mov     r8d, edi; nDenominator
0x180556c95  mov     edx, r12d; nNumerator
0x180556c98  mov     ecx, ebx; nNumber
0x180556c9a  call    cs:__imp_MulDiv
0x180556ca0  lea     ecx, [rax-1]
0x180556ca3  add     ecx, r14d
0x180556ca6  mov     [rbp+4Fh+var_C0], ecx
0x180556ca9  mov     r8d, edi; nDenominator
0x180556cac  lea     edx, [rdi-3Dh]; nNumerator
0x180556caf  mov     ecx, ebx; nNumber
0x180556cb1  call    cs:__imp_MulDiv
0x180556cb7  mov     edi, eax
0x180556cb9  movzx   ecx, [rbp+4Fh+arg_20]
0x180556cbd  xor     r12d, ecx
0x180556cc0  add     r12d, 2
0x180556cc4  mov     r8d, r13d; nDenominator
0x180556cc7  lea     edx, [r13-3]; nNumerator
0x180556ccb  mov     ecx, r15d; nNumber
0x180556cce  call    cs:__imp_MulDiv
0x180556cd4  lea     ebx, [r13-33h]
0x180556cd8  sub     ebx, esi
0x180556cda  add     ebx, eax
0x180556cdc  lea     rcx, [rbp+4Fh+var_B8]
0x180556ce0  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x180556ce6  lea     ecx, [rsi-1]
0x180556ce9  add     ecx, ebx
0x180556ceb  add     r12d, edi
0x180556cee  lea     r13d, [r14-1]
0x180556cf2  add     r13d, r12d
0x180556cf5  movd    xmm7, ebx
0x180556cf9  cvtdq2pd xmm7, xmm7
0x180556cfd  movd    xmm8, ecx
0x180556d02  cvtdq2pd xmm8, xmm8
0x180556d07  lea     r15, qword_180BF3AB8
0x180556d0e  movd    xmm0, r12d
0x180556d13  cvtdq2pd xmm0, xmm0
0x180556d17  movsd   [rbp+4Fh+var_80], xmm0
0x180556d1c  movsd   [rbp+4Fh+var_78], xmm7
0x180556d21  movd    xmm1, r13d
0x180556d26  cvtdq2pd xmm1, xmm1
0x180556d2a  movsd   [rbp+4Fh+var_70], xmm1
0x180556d2f  movsd   [rbp+4Fh+var_68], xmm8
0x180556d35  lea     rdx, [rbp+4Fh+var_80]
0x180556d39  lea     rcx, [rbp+4Fh+var_90]
0x180556d3d  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x180556d43  mov     rsi, [rax]
0x180556d46  mov     qword ptr [rax], 0
0x180556d4d  mov     [rbp+4Fh+var_60], rsi
0x180556d51  mov     rcx, [rbp+4Fh+var_90]
0x180556d55  test    rcx, rcx
0x180556d58  jz      short loc_180556D67
0x180556d5a  mov     rax, [rcx]
0x180556d5d  mov     rax, [rax+8]
0x180556d61  call    cs:__guard_dispatch_icall_fptr
0x180556d67  mov     edx, [r15]
0x180556d6a  mov     rcx, [rbp+4Fh+arg_8]
0x180556d6e  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180556d73  mov     rcx, rax; this
0x180556d76  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180556d7b  mov     ecx, eax
0x180556d7d  shr     ecx, 10h
0x180556d80  movzx   ecx, cl
0x180556d83  movd    xmm2, ecx
0x180556d87  cvtdq2ps xmm2, xmm2
0x180556d8a  divss   xmm2, cs:__real@437f0000
0x180556d92  movzx   ecx, ax
0x180556d95  shr     cx, 8
0x180556d99  movzx   ecx, cx
0x180556d9c  movd    xmm1, ecx
0x180556da0  cvtdq2ps xmm1, xmm1
0x180556da3  divss   xmm1, cs:__real@437f0000
0x180556dab  movzx   eax, al
0x180556dae  movd    xmm0, eax
0x180556db2  cvtdq2ps xmm0, xmm0
0x180556db5  divss   xmm0, cs:__real@437f0000
0x180556dbd  movss   [rbp+4Fh+var_A8], xmm0
0x180556dc2  movss   [rbp+4Fh+var_A4], xmm1
0x180556dc7  movss   [rbp+4Fh+var_A0], xmm2
0x180556dcc  mov     [rbp+4Fh+var_9C], 3F800000h
0x180556dd3  xor     r8d, r8d
0x180556dd6  lea     rdx, [rbp+4Fh+var_A8]
0x180556dda  lea     rcx, [rbp+4Fh+var_88]
0x180556dde  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x180556de4  mov     r14, [rax]
0x180556de7  mov     qword ptr [rax], 0
0x180556dee  mov     [rbp+4Fh+var_58], r14
0x180556df2  mov     rcx, [rbp+4Fh+var_88]
0x180556df6  test    rcx, rcx
0x180556df9  jz      short loc_180556E08
0x180556dfb  mov     rax, [rcx]
0x180556dfe  mov     rax, [rax+8]
0x180556e02  call    cs:__guard_dispatch_icall_fptr
0x180556e08  mov     rbx, [rbp+4Fh+var_B8]
0x180556e0c  mov     rax, [rbx]
0x180556e0f  mov     rdi, [rax+90h]
0x180556e16  xor     r9d, r9d
0x180556e19  mov     r8, r14
0x180556e1c  mov     rdx, rsi
0x180556e1f  lea     rcx, [rbp+4Fh+var_B0]
0x180556e23  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x180556e29  nop
0x180556e2a  mov     rdx, [rax]
0x180556e2d  mov     rcx, rbx
0x180556e30  mov     rax, rdi
0x180556e33  call    cs:__guard_dispatch_icall_fptr
0x180556e39  nop
0x180556e3a  mov     rcx, [rbp+4Fh+var_B0]
0x180556e3e  test    rcx, rcx
0x180556e41  jz      short loc_180556E50
0x180556e43  mov     rax, [rcx]
0x180556e46  mov     rax, [rax+8]
0x180556e4a  call    cs:__guard_dispatch_icall_fptr
0x180556e50  add     r12d, [rbp+4Fh+var_C0]
0x180556e54  add     r13d, [rbp+4Fh+var_C0]
0x180556e58  test    r14, r14
0x180556e5b  jz      short loc_180556E6E
0x180556e5d  mov     rax, [r14]
0x180556e60  mov     rcx, r14
0x180556e63  mov     rax, [rax+8]
0x180556e67  call    cs:__guard_dispatch_icall_fptr
0x180556e6d  nop
0x180556e6e  test    rsi, rsi
0x180556e71  jz      short loc_180556E83
0x180556e73  mov     rax, [rsi]
0x180556e76  mov     rcx, rsi
0x180556e79  mov     rax, [rax+8]
0x180556e7d  call    cs:__guard_dispatch_icall_fptr
0x180556e83  add     r15, 4
0x180556e87  lea     rax, ?s_enumStringTable@?$TEnumToString@W4AlgorithmStateType@Art@@@Art@@2QBUEnumStringPair@12@B; Art::TEnumToString<Art::AlgorithmStateType>::EnumStringPair const near * const Art::TEnumToString<Art::AlgorithmStateType>::s_enumStringTable
0x180556e8e  cmp     r15, rax
0x180556e91  jl      loc_180556D0E
0x180556e97  mov     rdx, [rbp+4Fh+var_B8]
0x180556e9b  lea     rcx, [rbp+4Fh+var_B0]
0x180556e9f  call    cs:__imp_?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z; GEL::IEffectAliased::Create(GEL::IEffect const &)
0x180556ea5  mov     rcx, [rax]
0x180556ea8  mov     qword ptr [rax], 0
0x180556eaf  mov     rbx, [rbp+4Fh+arg_0]
0x180556eb3  mov     [rbx], rcx
0x180556eb6  mov     rcx, [rbp+4Fh+var_B0]
0x180556eba  test    rcx, rcx
0x180556ebd  jz      short loc_180556ECD
0x180556ebf  mov     rax, [rcx]
0x180556ec2  mov     rax, [rax+8]
0x180556ec6  call    cs:__guard_dispatch_icall_fptr
0x180556ecc  nop
0x180556ecd  mov     rcx, [rbp+4Fh+var_B8]
0x180556ed1  test    rcx, rcx
0x180556ed4  jz      short loc_180556EE3
0x180556ed6  mov     rax, [rcx]
0x180556ed9  mov     rax, [rax+8]
0x180556edd  call    cs:__guard_dispatch_icall_fptr
0x180556ee3  mov     rax, rbx
0x180556ee6  lea     r11, [rsp+0E0h+var_30]
0x180556eee  mov     rbx, [r11+50h]
0x180556ef2  movaps  xmm7, xmmword ptr [r11-10h]
0x180556ef7  movaps  xmm8, xmmword ptr [r11-20h]
0x180556efc  mov     rsp, r11
0x180556eff  pop     r15
0x180556f01  pop     r14
0x180556f03  pop     r13
0x180556f05  pop     r12
0x180556f07  pop     rdi
0x180556f08  pop     rsi
0x180556f09  pop     rbp
0x180556f0a  retn
```
