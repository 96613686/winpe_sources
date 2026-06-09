# Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(GEL::IBrush const &,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &,Mso::TCntPtr<GEL::IBrush> &)

- ea: `0x180133248`
- end: `0x18013352d`
- name: `?ApplyInverseTransformToBrush@TextRenderer@SVG@Mso@@CAXAEBUIBrush@GEL@@AEBU?$TAffine3x3@N@Math@@AEA_NAEAU67@AEAV?$TCntPtr@UIBrush@GEL@@@3@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180133530`

## callees

- `0x1801331ac`
- `0x180133248`
- `0x18013dfc4`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180133309`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180133309`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180133343`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180133343`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180133314`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180133314`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1801333ac`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1801333ac`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1801332cb`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1801332cb`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x180133355`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x180133355`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x180133487`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x180133487`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@AEBU01@@Z` at `0x1801332fd`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@AEBU01@@Z` at `0x1801332fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(
        _QWORD *a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 *a5)
{
  char v9; // al
  int v10; // eax
  __int64 v11; // rax
  _QWORD *v12; // rax
  const struct GEL::RadialGradientInfo *v13; // rax
  unsigned int v14; // r8d
  void *v15; // rax
  void *v16; // rdx
  Mso::Memory *v17; // rbx
  _QWORD *v18; // rax
  void (__fastcall ***v19)(_QWORD); // rbx
  __int64 v20; // rcx
  int v21; // eax
  __m128i *v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  void (__fastcall ***v25)(_QWORD); // rbx
  __int64 v26; // rcx
  bool v27; // zf
  __int64 *v28; // rbx
  __int64 v29; // rcx
  __m128i si128; // [rsp+30h] [rbp-D0h] BYREF
  __m128i v31; // [rsp+40h] [rbp-C0h]
  __m128i v32; // [rsp+50h] [rbp-B0h]
  _OWORD v33[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[112]; // [rsp+90h] [rbp-70h] BYREF
  Mso::Memory *v35; // [rsp+100h] [rbp+0h]
  char v36; // [rsp+110h] [rbp+10h] BYREF
  __int64 v37; // [rsp+160h] [rbp+60h] BYREF

  v9 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 32LL))(a1);
  switch ( v9 )
  {
    case 4:
      _castguard_check_failure_user_handled(*a1);
      v10 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
      Mso::SVG::TextRenderer::ApplyInverseTransform((unsigned int)v33, v10, a2, a3, a4);
      v11 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 64LL))(a1);
      v12 = (_QWORD *)GEL::IBrushLinearGradient::Create(&v37, v11, v33);
LABEL_19:
      v25 = (void (__fastcall ***)(_QWORD))*v12;
      if ( *v12 )
        (**v25)(*v12);
      v26 = *a5;
      v27 = *a5 == 0;
      *a5 = (__int64)v25;
      if ( !v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
      return;
    case 5:
      _castguard_check_failure_user_handled(*a1);
      v13 = (const struct GEL::RadialGradientInfo *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
      GEL::RadialGradientInfo::RadialGradientInfo((GEL::RadialGradientInfo *)v34, v13);
      v15 = Mso::Memory::AllocateEx((Mso::Memory *)0x30, 0, v14);
      if ( !v15 )
      {
        ThrowOOM();
        __debugbreak();
      }
      v17 = (Mso::Memory *)Mso::SVG::TextRenderer::ApplyInverseTransform((_DWORD)v15, (_DWORD)v35, a2, a3, a4);
      if ( v35 != v17 )
      {
        if ( v35 )
          Mso::Memory::Free(v35, v16);
        v35 = v17;
      }
      v18 = (_QWORD *)GEL::IBrushRadialGradient::Create(&v37, v34);
      v19 = (void (__fastcall ***)(_QWORD))*v18;
      if ( *v18 )
        (**v19)(*v18);
      v20 = *a5;
      *a5 = (__int64)v19;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
      GEL::RadialGradientInfo::~RadialGradientInfo((GEL::RadialGradientInfo *)v34);
      break;
    case 7:
      _castguard_check_failure_user_handled(*a1);
      v33[0] = _mm_load_si128((const __m128i *)&_xmm);
      v33[1] = _mm_load_si128((const __m128i *)&_xmm);
      v33[2] = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v31 = _mm_load_si128((const __m128i *)&_xmm);
      v32 = 0;
      v21 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 72LL))(a1);
      v22 = (__m128i *)Mso::SVG::TextRenderer::ApplyInverseTransform((unsigned int)&v36, v21, a2, a3, a4);
      si128 = *v22;
      v31 = v22[1];
      v32 = v22[2];
      v23 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 64LL))(a1);
      v24 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
      v12 = (_QWORD *)GEL::IBrushEffect::Create(&v37, v24, v23, v33, &si128);
      goto LABEL_19;
    default:
      v28 = a5;
      if ( (_QWORD *)*a5 != a1 )
      {
        (*(void (__fastcall **)(_QWORD *))*a1)(a1);
        v29 = *v28;
        if ( *v28 )
        {
          *v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
        }
        *v28 = (__int64)a1;
      }
      break;
  }
}

```

## disassembly

```asm
0x180133248  mov     [rsp-8+arg_8], rbx
0x18013324d  mov     [rsp-8+arg_10], rsi
0x180133252  push    rbp
0x180133253  push    rdi
0x180133254  push    r14
0x180133256  lea     rbp, [rsp-40h]
0x18013325b  sub     rsp, 140h
0x180133262  mov     rbx, r9
0x180133265  mov     rsi, r8
0x180133268  mov     r14, rdx
0x18013326b  mov     rdi, rcx
0x18013326e  mov     rax, [rcx]
0x180133271  mov     rax, [rax+20h]
0x180133275  call    cs:__guard_dispatch_icall_fptr
0x18013327b  cmp     al, 4
0x18013327d  jnz     short loc_1801332D6
0x18013327f  mov     rcx, [rdi]
0x180133282  call    __castguard_check_failure_user_handled
0x180133287  mov     rax, [rdi]
0x18013328a  mov     rcx, rdi
0x18013328d  mov     rax, [rax+38h]
0x180133291  call    cs:__guard_dispatch_icall_fptr
0x180133297  mov     [rsp+150h+var_130], rbx
0x18013329c  mov     r9, rsi
0x18013329f  mov     r8, r14
0x1801332a2  mov     rdx, rax
0x1801332a5  lea     rcx, [rsp+150h+var_F0]
0x1801332aa  call    ?ApplyInverseTransform@TextRenderer@SVG@Mso@@CA?AU?$TAffine3x3@N@Math@@PEBU45@AEBU45@AEA_NAEAU45@@Z; Mso::SVG::TextRenderer::ApplyInverseTransform(Math::TAffine3x3<double> const *,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &)
0x1801332af  mov     r9, [rdi]
0x1801332b2  mov     rcx, rdi
0x1801332b5  mov     rax, [r9+40h]
0x1801332b9  call    cs:__guard_dispatch_icall_fptr
0x1801332bf  mov     rdx, rax
0x1801332c2  lea     r8, [rsp+150h+var_F0]
0x1801332c7  lea     rcx, [rbp+50h+arg_0]
0x1801332cb  call    cs:__imp_?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IBrushLinearGradient::Create(GEL::LinearGradientInfo const &,Math::TAffine3x3<double> const *)
0x1801332d1  jmp     loc_18013348D
0x1801332d6  cmp     al, 5
0x1801332d8  jnz     loc_1801333B7
0x1801332de  mov     rcx, [rdi]
0x1801332e1  call    __castguard_check_failure_user_handled
0x1801332e6  mov     rax, [rdi]
0x1801332e9  mov     rcx, rdi
0x1801332ec  mov     rax, [rax+38h]
0x1801332f0  call    cs:__guard_dispatch_icall_fptr
0x1801332f6  mov     rdx, rax
0x1801332f9  lea     rcx, [rbp+50h+var_C0]
0x1801332fd  call    cs:__imp_??0RadialGradientInfo@GEL@@QEAA@AEBU01@@Z; GEL::RadialGradientInfo::RadialGradientInfo(GEL::RadialGradientInfo const &)
0x180133303  nop
0x180133304  xor     edx, edx
0x180133306  lea     ecx, [rdx+30h]
0x180133309  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18013330f  test    rax, rax
0x180133312  jnz     short loc_18013331B
0x180133314  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18013331a  int     3; Trap to Debugger
0x18013331b  mov     [rsp+150h+var_130], rbx
0x180133320  mov     r9, rsi
0x180133323  mov     r8, r14
0x180133326  mov     rdx, [rbp+50h+var_50]
0x18013332a  mov     rcx, rax
0x18013332d  call    ?ApplyInverseTransform@TextRenderer@SVG@Mso@@CA?AU?$TAffine3x3@N@Math@@PEBU45@AEBU45@AEA_NAEAU45@@Z; Mso::SVG::TextRenderer::ApplyInverseTransform(Math::TAffine3x3<double> const *,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &)
0x180133332  mov     rbx, rax
0x180133335  mov     rcx, [rbp+50h+var_50]
0x180133339  cmp     rcx, rax
0x18013333c  jz      short loc_18013334D
0x18013333e  test    rcx, rcx
0x180133341  jz      short loc_180133349
0x180133343  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180133349  mov     [rbp+50h+var_50], rbx
0x18013334d  lea     rdx, [rbp+50h+var_C0]
0x180133351  lea     rcx, [rbp+50h+arg_0]
0x180133355  call    cs:__imp_?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z; GEL::IBrushRadialGradient::Create(GEL::RadialGradientInfo const &)
0x18013335b  mov     rbx, [rax]
0x18013335e  test    rbx, rbx
0x180133361  jz      short loc_180133372
0x180133363  mov     rax, [rbx]
0x180133366  mov     rcx, rbx
0x180133369  mov     rax, [rax]
0x18013336c  call    cs:__guard_dispatch_icall_fptr
0x180133372  mov     rax, [rbp+50h+arg_20]
0x180133379  mov     rcx, [rax]
0x18013337c  mov     [rax], rbx
0x18013337f  test    rcx, rcx
0x180133382  jz      short loc_180133391
0x180133384  mov     rax, [rcx]
0x180133387  mov     rax, [rax+8]
0x18013338b  call    cs:__guard_dispatch_icall_fptr
0x180133391  mov     rcx, [rbp+50h+arg_0]
0x180133395  test    rcx, rcx
0x180133398  jz      short loc_1801333A8
0x18013339a  mov     rax, [rcx]
0x18013339d  mov     rax, [rax+8]
0x1801333a1  call    cs:__guard_dispatch_icall_fptr
0x1801333a7  nop
0x1801333a8  lea     rcx, [rbp+50h+var_C0]
0x1801333ac  call    cs:__imp_??1RadialGradientInfo@GEL@@UEAA@XZ; GEL::RadialGradientInfo::~RadialGradientInfo(void)
0x1801333b2  jmp     loc_180133515
0x1801333b7  cmp     al, 7
0x1801333b9  jnz     loc_1801334DB
0x1801333bf  mov     rcx, [rdi]
0x1801333c2  call    __castguard_check_failure_user_handled
0x1801333c7  movdqa  xmm0, cs:__xmm@000000000000000040c29a8000000000
0x1801333cf  movups  [rsp+150h+var_F0], xmm0
0x1801333d4  movdqa  xmm1, cs:__xmm@40c29a80000000000000000000000000
0x1801333dc  movups  [rsp+150h+var_E0], xmm1
0x1801333e1  xorps   xmm0, xmm0
0x1801333e4  movups  [rbp+50h+var_D0], xmm0
0x1801333e8  movdqa  xmm1, cs:__xmm@00000000000000003ff0000000000000
0x1801333f0  movups  [rsp+150h+var_120], xmm1
0x1801333f5  movdqa  xmm0, cs:__xmm@3ff00000000000000000000000000000
0x1801333fd  movups  [rsp+150h+var_110], xmm0
0x180133402  xorps   xmm0, xmm0
0x180133405  movups  [rsp+150h+var_100], xmm0
0x18013340a  mov     rax, [rdi]
0x18013340d  mov     rcx, rdi
0x180133410  mov     rax, [rax+48h]
0x180133414  call    cs:__guard_dispatch_icall_fptr
0x18013341a  mov     rdx, rax
0x18013341d  mov     [rsp+150h+var_130], rbx
0x180133422  mov     r9, rsi
0x180133425  mov     r8, r14
0x180133428  lea     rcx, [rbp+50h+var_40]
0x18013342c  call    ?ApplyInverseTransform@TextRenderer@SVG@Mso@@CA?AU?$TAffine3x3@N@Math@@PEBU45@AEBU45@AEA_NAEAU45@@Z; Mso::SVG::TextRenderer::ApplyInverseTransform(Math::TAffine3x3<double> const *,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &)
0x180133431  movups  xmm0, xmmword ptr [rax]
0x180133434  movups  [rsp+150h+var_120], xmm0
0x180133439  movups  xmm1, xmmword ptr [rax+10h]
0x18013343d  movups  [rsp+150h+var_110], xmm1
0x180133442  movups  xmm0, xmmword ptr [rax+20h]
0x180133446  movups  [rsp+150h+var_100], xmm0
0x18013344b  mov     rax, [rdi]
0x18013344e  mov     rcx, rdi
0x180133451  mov     rax, [rax+40h]
0x180133455  call    cs:__guard_dispatch_icall_fptr
0x18013345b  mov     rbx, rax
0x18013345e  mov     rcx, [rdi]
0x180133461  mov     rax, [rcx+38h]
0x180133465  mov     rcx, rdi
0x180133468  call    cs:__guard_dispatch_icall_fptr
0x18013346e  lea     rcx, [rsp+150h+var_120]
0x180133473  mov     [rsp+150h+var_130], rcx
0x180133478  lea     r9, [rsp+150h+var_F0]
0x18013347d  mov     r8, rbx
0x180133480  mov     rdx, rax
0x180133483  lea     rcx, [rbp+50h+arg_0]
0x180133487  call    cs:__imp_?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z; GEL::IBrushEffect::Create(Math::TRect<double> const &,GEL::IEffect const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x18013348d  mov     rbx, [rax]
0x180133490  test    rbx, rbx
0x180133493  jz      short loc_1801334A4
0x180133495  mov     rax, [rbx]
0x180133498  mov     rcx, rbx
0x18013349b  mov     rax, [rax]
0x18013349e  call    cs:__guard_dispatch_icall_fptr
0x1801334a4  mov     rax, [rbp+50h+arg_20]
0x1801334ab  mov     rcx, [rax]
0x1801334ae  test    rcx, rcx
0x1801334b1  mov     [rax], rbx
0x1801334b4  jz      short loc_1801334C3
0x1801334b6  mov     rax, [rcx]
0x1801334b9  mov     rax, [rax+8]
0x1801334bd  call    cs:__guard_dispatch_icall_fptr
0x1801334c3  mov     rcx, [rbp+50h+arg_0]
0x1801334c7  test    rcx, rcx
0x1801334ca  jz      short loc_180133515
0x1801334cc  mov     rax, [rcx]
0x1801334cf  mov     rax, [rax+8]
0x1801334d3  call    cs:__guard_dispatch_icall_fptr
0x1801334d9  jmp     short loc_180133515
0x1801334db  mov     rbx, [rbp+50h+arg_20]
0x1801334e2  cmp     [rbx], rdi
0x1801334e5  jz      short loc_180133515
0x1801334e7  mov     rax, [rdi]
0x1801334ea  mov     rcx, rdi
0x1801334ed  mov     rax, [rax]
0x1801334f0  call    cs:__guard_dispatch_icall_fptr
0x1801334f6  mov     rcx, [rbx]
0x1801334f9  test    rcx, rcx
0x1801334fc  jz      short loc_180133512
0x1801334fe  mov     qword ptr [rbx], 0
0x180133505  mov     rax, [rcx]
0x180133508  mov     rax, [rax+8]
0x18013350c  call    cs:__guard_dispatch_icall_fptr
0x180133512  mov     [rbx], rdi
0x180133515  lea     r11, [rsp+150h+var_10]
0x18013351d  mov     rbx, [r11+28h]
0x180133521  mov     rsi, [r11+30h]
0x180133525  mov     rsp, r11
0x180133528  pop     r14
0x18013352a  pop     rdi
0x18013352b  pop     rbp
0x18013352c  retn
```
