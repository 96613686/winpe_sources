# Mso::SVG::TextRenderer::ApplyInverseTransformToBrush(GEL::IBrush const &,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &,Mso::TCntPtr<GEL::IBrush> &)

- ea: `0x180133288`
- end: `0x18013356d`
- name: `?ApplyInverseTransformToBrush@TextRenderer@SVG@Mso@@CAXAEBUIBrush@GEL@@AEBU?$TAffine3x3@N@Math@@AEA_NAEAU67@AEAV?$TCntPtr@UIBrush@GEL@@@3@@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180133570`

## callees

- `0x1801331ec`
- `0x180133288`
- `0x18013e074`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180133349`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180133349`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180133383`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180133383`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180133354`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180133354`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1801333ec`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1801333ec`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x18013330b`
- `gfx!?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x18013330b`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x180133395`
- `gfx!?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z` at `0x180133395`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x1801334c7`
- `gfx!?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z` at `0x1801334c7`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@AEBU01@@Z` at `0x18013333d`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@AEBU01@@Z` at `0x18013333d`

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
0x180133288  mov     [rsp-8+arg_8], rbx
0x18013328d  mov     [rsp-8+arg_10], rsi
0x180133292  push    rbp
0x180133293  push    rdi
0x180133294  push    r14
0x180133296  lea     rbp, [rsp-40h]
0x18013329b  sub     rsp, 140h
0x1801332a2  mov     rbx, r9
0x1801332a5  mov     rsi, r8
0x1801332a8  mov     r14, rdx
0x1801332ab  mov     rdi, rcx
0x1801332ae  mov     rax, [rcx]
0x1801332b1  mov     rax, [rax+20h]
0x1801332b5  call    cs:__guard_dispatch_icall_fptr
0x1801332bb  cmp     al, 4
0x1801332bd  jnz     short loc_180133316
0x1801332bf  mov     rcx, [rdi]
0x1801332c2  call    __castguard_check_failure_user_handled
0x1801332c7  mov     rax, [rdi]
0x1801332ca  mov     rcx, rdi
0x1801332cd  mov     rax, [rax+38h]
0x1801332d1  call    cs:__guard_dispatch_icall_fptr
0x1801332d7  mov     [rsp+150h+var_130], rbx
0x1801332dc  mov     r9, rsi
0x1801332df  mov     r8, r14
0x1801332e2  mov     rdx, rax
0x1801332e5  lea     rcx, [rsp+150h+var_F0]
0x1801332ea  call    ?ApplyInverseTransform@TextRenderer@SVG@Mso@@CA?AU?$TAffine3x3@N@Math@@PEBU45@AEBU45@AEA_NAEAU45@@Z; Mso::SVG::TextRenderer::ApplyInverseTransform(Math::TAffine3x3<double> const *,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &)
0x1801332ef  mov     r9, [rdi]
0x1801332f2  mov     rcx, rdi
0x1801332f5  mov     rax, [r9+40h]
0x1801332f9  call    cs:__guard_dispatch_icall_fptr
0x1801332ff  mov     rdx, rax
0x180133302  lea     r8, [rsp+150h+var_F0]
0x180133307  lea     rcx, [rbp+50h+arg_0]
0x18013330b  call    cs:__imp_?Create@IBrushLinearGradient@GEL@@SA?AV?$TCntPtr@UIBrushLinearGradient@GEL@@@Ofc@@AEBULinearGradientInfo@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IBrushLinearGradient::Create(GEL::LinearGradientInfo const &,Math::TAffine3x3<double> const *)
0x180133311  jmp     loc_1801334CD
0x180133316  cmp     al, 5
0x180133318  jnz     loc_1801333F7
0x18013331e  mov     rcx, [rdi]
0x180133321  call    __castguard_check_failure_user_handled
0x180133326  mov     rax, [rdi]
0x180133329  mov     rcx, rdi
0x18013332c  mov     rax, [rax+38h]
0x180133330  call    cs:__guard_dispatch_icall_fptr
0x180133336  mov     rdx, rax
0x180133339  lea     rcx, [rbp+50h+var_C0]
0x18013333d  call    cs:__imp_??0RadialGradientInfo@GEL@@QEAA@AEBU01@@Z; GEL::RadialGradientInfo::RadialGradientInfo(GEL::RadialGradientInfo const &)
0x180133343  nop
0x180133344  xor     edx, edx
0x180133346  lea     ecx, [rdx+30h]
0x180133349  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18013334f  test    rax, rax
0x180133352  jnz     short loc_18013335B
0x180133354  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18013335a  int     3; Trap to Debugger
0x18013335b  mov     [rsp+150h+var_130], rbx
0x180133360  mov     r9, rsi
0x180133363  mov     r8, r14
0x180133366  mov     rdx, [rbp+50h+var_50]
0x18013336a  mov     rcx, rax
0x18013336d  call    ?ApplyInverseTransform@TextRenderer@SVG@Mso@@CA?AU?$TAffine3x3@N@Math@@PEBU45@AEBU45@AEA_NAEAU45@@Z; Mso::SVG::TextRenderer::ApplyInverseTransform(Math::TAffine3x3<double> const *,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &)
0x180133372  mov     rbx, rax
0x180133375  mov     rcx, [rbp+50h+var_50]
0x180133379  cmp     rcx, rax
0x18013337c  jz      short loc_18013338D
0x18013337e  test    rcx, rcx
0x180133381  jz      short loc_180133389
0x180133383  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180133389  mov     [rbp+50h+var_50], rbx
0x18013338d  lea     rdx, [rbp+50h+var_C0]
0x180133391  lea     rcx, [rbp+50h+arg_0]
0x180133395  call    cs:__imp_?Create@IBrushRadialGradient@GEL@@SA?AV?$TCntPtr@UIBrushRadialGradient@GEL@@@Ofc@@AEBURadialGradientInfo@2@@Z; GEL::IBrushRadialGradient::Create(GEL::RadialGradientInfo const &)
0x18013339b  mov     rbx, [rax]
0x18013339e  test    rbx, rbx
0x1801333a1  jz      short loc_1801333B2
0x1801333a3  mov     rax, [rbx]
0x1801333a6  mov     rcx, rbx
0x1801333a9  mov     rax, [rax]
0x1801333ac  call    cs:__guard_dispatch_icall_fptr
0x1801333b2  mov     rax, [rbp+50h+arg_20]
0x1801333b9  mov     rcx, [rax]
0x1801333bc  mov     [rax], rbx
0x1801333bf  test    rcx, rcx
0x1801333c2  jz      short loc_1801333D1
0x1801333c4  mov     rax, [rcx]
0x1801333c7  mov     rax, [rax+8]
0x1801333cb  call    cs:__guard_dispatch_icall_fptr
0x1801333d1  mov     rcx, [rbp+50h+arg_0]
0x1801333d5  test    rcx, rcx
0x1801333d8  jz      short loc_1801333E8
0x1801333da  mov     rax, [rcx]
0x1801333dd  mov     rax, [rax+8]
0x1801333e1  call    cs:__guard_dispatch_icall_fptr
0x1801333e7  nop
0x1801333e8  lea     rcx, [rbp+50h+var_C0]
0x1801333ec  call    cs:__imp_??1RadialGradientInfo@GEL@@UEAA@XZ; GEL::RadialGradientInfo::~RadialGradientInfo(void)
0x1801333f2  jmp     loc_180133555
0x1801333f7  cmp     al, 7
0x1801333f9  jnz     loc_18013351B
0x1801333ff  mov     rcx, [rdi]
0x180133402  call    __castguard_check_failure_user_handled
0x180133407  movdqa  xmm0, cs:__xmm@000000000000000040c29a8000000000
0x18013340f  movups  [rsp+150h+var_F0], xmm0
0x180133414  movdqa  xmm1, cs:__xmm@40c29a80000000000000000000000000
0x18013341c  movups  [rsp+150h+var_E0], xmm1
0x180133421  xorps   xmm0, xmm0
0x180133424  movups  [rbp+50h+var_D0], xmm0
0x180133428  movdqa  xmm1, cs:__xmm@00000000000000003ff0000000000000
0x180133430  movups  [rsp+150h+var_120], xmm1
0x180133435  movdqa  xmm0, cs:__xmm@3ff00000000000000000000000000000
0x18013343d  movups  [rsp+150h+var_110], xmm0
0x180133442  xorps   xmm0, xmm0
0x180133445  movups  [rsp+150h+var_100], xmm0
0x18013344a  mov     rax, [rdi]
0x18013344d  mov     rcx, rdi
0x180133450  mov     rax, [rax+48h]
0x180133454  call    cs:__guard_dispatch_icall_fptr
0x18013345a  mov     rdx, rax
0x18013345d  mov     [rsp+150h+var_130], rbx
0x180133462  mov     r9, rsi
0x180133465  mov     r8, r14
0x180133468  lea     rcx, [rbp+50h+var_40]
0x18013346c  call    ?ApplyInverseTransform@TextRenderer@SVG@Mso@@CA?AU?$TAffine3x3@N@Math@@PEBU45@AEBU45@AEA_NAEAU45@@Z; Mso::SVG::TextRenderer::ApplyInverseTransform(Math::TAffine3x3<double> const *,Math::TAffine3x3<double> const &,bool &,Math::TAffine3x3<double> &)
0x180133471  movups  xmm0, xmmword ptr [rax]
0x180133474  movups  [rsp+150h+var_120], xmm0
0x180133479  movups  xmm1, xmmword ptr [rax+10h]
0x18013347d  movups  [rsp+150h+var_110], xmm1
0x180133482  movups  xmm0, xmmword ptr [rax+20h]
0x180133486  movups  [rsp+150h+var_100], xmm0
0x18013348b  mov     rax, [rdi]
0x18013348e  mov     rcx, rdi
0x180133491  mov     rax, [rax+40h]
0x180133495  call    cs:__guard_dispatch_icall_fptr
0x18013349b  mov     rbx, rax
0x18013349e  mov     rcx, [rdi]
0x1801334a1  mov     rax, [rcx+38h]
0x1801334a5  mov     rcx, rdi
0x1801334a8  call    cs:__guard_dispatch_icall_fptr
0x1801334ae  lea     rcx, [rsp+150h+var_120]
0x1801334b3  mov     [rsp+150h+var_130], rcx
0x1801334b8  lea     r9, [rsp+150h+var_F0]
0x1801334bd  mov     r8, rbx
0x1801334c0  mov     rdx, rax
0x1801334c3  lea     rcx, [rbp+50h+arg_0]
0x1801334c7  call    cs:__imp_?Create@IBrushEffect@GEL@@SA?AV?$TCntPtr@UIBrushEffect@GEL@@@Ofc@@AEBU?$TRect@N@Math@@AEBUIEffect@2@AEBU?$TAffine3x3@N@6@PEBU86@@Z; GEL::IBrushEffect::Create(Math::TRect<double> const &,GEL::IEffect const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x1801334cd  mov     rbx, [rax]
0x1801334d0  test    rbx, rbx
0x1801334d3  jz      short loc_1801334E4
0x1801334d5  mov     rax, [rbx]
0x1801334d8  mov     rcx, rbx
0x1801334db  mov     rax, [rax]
0x1801334de  call    cs:__guard_dispatch_icall_fptr
0x1801334e4  mov     rax, [rbp+50h+arg_20]
0x1801334eb  mov     rcx, [rax]
0x1801334ee  test    rcx, rcx
0x1801334f1  mov     [rax], rbx
0x1801334f4  jz      short loc_180133503
0x1801334f6  mov     rax, [rcx]
0x1801334f9  mov     rax, [rax+8]
0x1801334fd  call    cs:__guard_dispatch_icall_fptr
0x180133503  mov     rcx, [rbp+50h+arg_0]
0x180133507  test    rcx, rcx
0x18013350a  jz      short loc_180133555
0x18013350c  mov     rax, [rcx]
0x18013350f  mov     rax, [rax+8]
0x180133513  call    cs:__guard_dispatch_icall_fptr
0x180133519  jmp     short loc_180133555
0x18013351b  mov     rbx, [rbp+50h+arg_20]
0x180133522  cmp     [rbx], rdi
0x180133525  jz      short loc_180133555
0x180133527  mov     rax, [rdi]
0x18013352a  mov     rcx, rdi
0x18013352d  mov     rax, [rax]
0x180133530  call    cs:__guard_dispatch_icall_fptr
0x180133536  mov     rcx, [rbx]
0x180133539  test    rcx, rcx
0x18013353c  jz      short loc_180133552
0x18013353e  mov     qword ptr [rbx], 0
0x180133545  mov     rax, [rcx]
0x180133548  mov     rax, [rax+8]
0x18013354c  call    cs:__guard_dispatch_icall_fptr
0x180133552  mov     [rbx], rdi
0x180133555  lea     r11, [rsp+150h+var_10]
0x18013355d  mov     rbx, [r11+28h]
0x180133561  mov     rsi, [r11+30h]
0x180133565  mov     rsp, r11
0x180133568  pop     r14
0x18013356a  pop     rdi
0x18013356b  pop     rbp
0x18013356c  retn
```
