# Art::ChartRectangleHandleFactoryState::CreateEffect(void)

- ea: `0x1807b3850`
- end: `0x1807b3ac2`
- name: `?CreateEffect@ChartRectangleHandleFactoryState@Art@@UEBA?AV?$TCntPtr@UIEffect@GEL@@@Ofc@@XZ`
- size: `626`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180279050`
- `0x1807b3850`

## import_xrefs

- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b38c0`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b3904`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b3945`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b3972`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b38c0`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b3904`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b3945`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807b3972`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1807b3982`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1807b3982`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x1807b39b1`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x1807b39b1`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1807b3873`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1807b3873`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1807b39da`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1807b39da`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1807b3a32`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1807b3a32`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1807b3a13`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1807b3a13`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1807b39bb`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1807b39bb`

## pseudocode

```c
_QWORD *__fastcall Art::ChartRectangleHandleFactoryState::CreateEffect(double *a1, _QWORD *a2)
{
  __int64 v4; // rax
  double v5; // xmm3_8
  double v6; // xmm2_8
  __int64 v7; // rax
  double v8; // xmm3_8
  double v9; // xmm2_8
  __int64 v10; // rax
  double v11; // xmm2_8
  __int64 v12; // rax
  __m128 v13; // xmm1
  __m128d v14; // xmm0
  __int64 v15; // rax
  __int64 *v16; // rax
  __int64 v17; // rsi
  _QWORD *v18; // rbx
  void (__fastcall *v19)(_QWORD *, _QWORD); // rdi
  _QWORD *v20; // rax
  __int64 v21; // rdx
  _QWORD *v22; // rbx
  void (__fastcall *v23)(_QWORD *, _QWORD); // rdi
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  double v28[4]; // [rsp+28h] [rbp-A1h] BYREF
  double v29[4]; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v30[4]; // [rsp+68h] [rbp-61h] BYREF
  _OWORD v31[2]; // [rsp+88h] [rbp-41h] BYREF
  _BYTE v32[120]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v33; // [rsp+130h] [rbp+67h] BYREF
  _QWORD *v34; // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v35; // [rsp+140h] [rbp+77h] BYREF
  __int64 v36; // [rsp+148h] [rbp+7Fh]

  v34 = a2;
  v4 = GEL::PathBuilder::PathBuilder((GEL::PathBuilder *)v32);
  v5 = a1[7];
  v6 = a1[5];
  v28[0] = v6 - v5;
  v28[1] = a1[6] - v5;
  v28[2] = v6 + v5;
  v28[3] = v5 + a1[6];
  v7 = GEL::PathBuilder::AddEllipse(v4, v28);
  v8 = a1[7];
  v9 = a1[5];
  v29[0] = v9 - v8;
  *(_QWORD *)&v29[1] = *(_QWORD *)&v8 ^ _xmm;
  v29[2] = v9 + v8;
  v29[3] = v8;
  v10 = GEL::PathBuilder::AddEllipse(v7, v29);
  v11 = a1[7];
  v30[0] = *(_QWORD *)&v11 ^ _xmm;
  *(double *)&v30[1] = a1[6] - v11;
  *(double *)&v30[2] = v11;
  *(double *)&v30[3] = v11 + a1[6];
  v12 = GEL::PathBuilder::AddEllipse(v10, v30);
  v13 = (__m128)_mm_unpacklo_pd((__m128d)*((unsigned __int64 *)a1 + 7), (__m128d)*((unsigned __int64 *)a1 + 7));
  v14 = (__m128d)_mm_xor_ps(v13, (__m128)_xmm);
  v31[0] = _mm_unpacklo_pd(v14, v14);
  v31[1] = v13;
  v15 = GEL::PathBuilder::AddEllipse(v12, v31);
  v16 = (__int64 *)GEL::PathBuilder::Finish(v15, &v35, 0);
  v17 = *v16;
  *v16 = 0;
  v36 = v17;
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  GEL::PathBuilder::~PathBuilder((GEL::PathBuilder *)v32);
  GEL::IEffectContainer::Create(&v34);
  v18 = v34;
  v19 = *(void (__fastcall **)(_QWORD *, _QWORD))(*v34 + 144LL);
  v20 = (_QWORD *)GEL::IEffectFilledPath::Create(&v35, v17, a1 + 3);
  v19(v18, *v20);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  GEL::IPen::Create(&v33, v21, a1 + 1);
  v22 = v34;
  v23 = *(void (__fastcall **)(_QWORD *, _QWORD))(*v34 + 144LL);
  v24 = (_QWORD *)GEL::IEffectPennedPath::Create(&v35, v17, v33);
  v23(v22, *v24);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  v25 = v34;
  v26 = 0;
  v34 = 0;
  *a2 = v25;
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
    v26 = v34;
  }
  if ( v26 )
    (*(void (__fastcall **)(_QWORD *))(*v26 + 8LL))(v26);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  return a2;
}

```

## disassembly

```asm
0x1807b3850  mov     [rsp-8+arg_8], rdx
0x1807b3855  push    rbp
0x1807b3856  push    rbx
0x1807b3857  push    rsi
0x1807b3858  push    rdi
0x1807b3859  push    r14
0x1807b385b  push    r15
0x1807b385d  lea     rbp, [rsp-2Fh]
0x1807b3862  sub     rsp, 0F8h
0x1807b3869  mov     r15, rdx
0x1807b386c  mov     r14, rcx
0x1807b386f  lea     rcx, [rbp+57h+var_78]
0x1807b3873  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x1807b3879  movsd   xmm3, qword ptr [r14+38h]
0x1807b387f  movsd   xmm2, qword ptr [r14+28h]
0x1807b3885  movaps  xmm0, xmm2
0x1807b3888  subsd   xmm0, xmm3
0x1807b388c  movsd   [rsp+120h+var_F8], xmm0
0x1807b3892  movsd   xmm1, qword ptr [r14+30h]
0x1807b3898  subsd   xmm1, xmm3
0x1807b389c  movsd   [rsp+120h+var_F0], xmm1
0x1807b38a2  addsd   xmm2, xmm3
0x1807b38a6  movsd   [rsp+120h+var_E8], xmm2
0x1807b38ac  addsd   xmm3, qword ptr [r14+30h]
0x1807b38b2  movsd   [rsp+120h+var_E0], xmm3
0x1807b38b8  lea     rdx, [rsp+120h+var_F8]
0x1807b38bd  mov     rcx, rax
0x1807b38c0  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807b38c6  movsd   xmm3, qword ptr [r14+38h]
0x1807b38cc  movsd   xmm2, qword ptr [r14+28h]
0x1807b38d2  movaps  xmm1, xmm3
0x1807b38d5  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x1807b38dc  movaps  xmm0, xmm2
0x1807b38df  subsd   xmm0, xmm3
0x1807b38e3  movsd   [rsp+120h+var_D8], xmm0
0x1807b38e9  movsd   [rbp+57h+var_D0], xmm1
0x1807b38ee  addsd   xmm2, xmm3
0x1807b38f2  movsd   [rbp+57h+var_C8], xmm2
0x1807b38f7  movsd   [rbp+57h+var_C0], xmm3
0x1807b38fc  lea     rdx, [rsp+120h+var_D8]
0x1807b3901  mov     rcx, rax
0x1807b3904  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807b390a  movsd   xmm2, qword ptr [r14+38h]
0x1807b3910  movaps  xmm0, xmm2
0x1807b3913  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1807b391a  movsd   [rbp+57h+var_B8], xmm0
0x1807b391f  movsd   xmm1, qword ptr [r14+30h]
0x1807b3925  subsd   xmm1, xmm2
0x1807b3929  movsd   [rbp+57h+var_B0], xmm1
0x1807b392e  movsd   [rbp+57h+var_A8], xmm2
0x1807b3933  addsd   xmm2, qword ptr [r14+30h]
0x1807b3939  movsd   [rbp+57h+var_A0], xmm2
0x1807b393e  lea     rdx, [rbp+57h+var_B8]
0x1807b3942  mov     rcx, rax
0x1807b3945  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807b394b  movsd   xmm1, qword ptr [r14+38h]
0x1807b3951  unpcklpd xmm1, xmm1
0x1807b3955  movaps  xmm0, xmm1
0x1807b3958  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1807b395f  unpcklpd xmm0, xmm0
0x1807b3963  movups  [rbp+57h+var_98], xmm0
0x1807b3967  movups  [rbp+57h+var_88], xmm1
0x1807b396b  lea     rdx, [rbp+57h+var_98]
0x1807b396f  mov     rcx, rax
0x1807b3972  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807b3978  xor     r8d, r8d
0x1807b397b  lea     rdx, [rbp+57h+arg_10]
0x1807b397f  mov     rcx, rax
0x1807b3982  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x1807b3988  mov     rsi, [rax]
0x1807b398b  mov     qword ptr [rax], 0
0x1807b3992  mov     [rbp+57h+arg_18], rsi
0x1807b3996  mov     rcx, [rbp+57h+arg_10]
0x1807b399a  test    rcx, rcx
0x1807b399d  jz      short loc_1807B39AD
0x1807b399f  mov     rax, [rcx]
0x1807b39a2  mov     rax, [rax+8]
0x1807b39a6  call    cs:__guard_dispatch_icall_fptr
0x1807b39ac  nop
0x1807b39ad  lea     rcx, [rbp+57h+var_78]
0x1807b39b1  call    cs:__imp_??1PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::~PathBuilder(void)
0x1807b39b7  lea     rcx, [rbp+57h+arg_8]
0x1807b39bb  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1807b39c1  mov     rbx, [rbp+57h+arg_8]
0x1807b39c5  mov     rax, [rbx]
0x1807b39c8  mov     rdi, [rax+90h]
0x1807b39cf  lea     r8, [r14+18h]
0x1807b39d3  mov     rdx, rsi
0x1807b39d6  lea     rcx, [rbp+57h+arg_10]
0x1807b39da  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::Color const &)
0x1807b39e0  mov     rdx, [rax]
0x1807b39e3  mov     rcx, rbx
0x1807b39e6  mov     rax, rdi
0x1807b39e9  call    cs:__guard_dispatch_icall_fptr
0x1807b39ef  mov     rcx, [rbp+57h+arg_10]
0x1807b39f3  test    rcx, rcx
0x1807b39f6  jz      short loc_1807B3A05
0x1807b39f8  mov     rax, [rcx]
0x1807b39fb  mov     rax, [rax+8]
0x1807b39ff  call    cs:__guard_dispatch_icall_fptr
0x1807b3a05  lea     r8, [r14+8]
0x1807b3a09  movsd   xmm1, qword ptr [r14+40h]
0x1807b3a0f  lea     rcx, [rbp+57h+arg_0]
0x1807b3a13  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x1807b3a19  mov     rbx, [rbp+57h+arg_8]
0x1807b3a1d  mov     rax, [rbx]
0x1807b3a20  mov     rdi, [rax+90h]
0x1807b3a27  mov     r8, [rbp+57h+arg_0]
0x1807b3a2b  mov     rdx, rsi
0x1807b3a2e  lea     rcx, [rbp+57h+arg_10]
0x1807b3a32  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x1807b3a38  mov     rdx, [rax]
0x1807b3a3b  mov     rcx, rbx
0x1807b3a3e  mov     rax, rdi
0x1807b3a41  call    cs:__guard_dispatch_icall_fptr
0x1807b3a47  mov     rcx, [rbp+57h+arg_10]
0x1807b3a4b  test    rcx, rcx
0x1807b3a4e  jz      short loc_1807B3A5D
0x1807b3a50  mov     rax, [rcx]
0x1807b3a53  mov     rax, [rax+8]
0x1807b3a57  call    cs:__guard_dispatch_icall_fptr
0x1807b3a5d  mov     rax, [rbp+57h+arg_8]
0x1807b3a61  xor     ecx, ecx
0x1807b3a63  mov     [rbp+57h+arg_8], rcx
0x1807b3a67  mov     [r15], rax
0x1807b3a6a  mov     rdx, [rbp+57h+arg_0]
0x1807b3a6e  test    rdx, rdx
0x1807b3a71  jz      short loc_1807B3A87
0x1807b3a73  mov     rax, [rdx]
0x1807b3a76  mov     rcx, rdx
0x1807b3a79  mov     rax, [rax+8]
0x1807b3a7d  call    cs:__guard_dispatch_icall_fptr
0x1807b3a83  mov     rcx, [rbp+57h+arg_8]
0x1807b3a87  test    rcx, rcx
0x1807b3a8a  jz      short loc_1807B3A9A
0x1807b3a8c  mov     rax, [rcx]
0x1807b3a8f  mov     rax, [rax+8]
0x1807b3a93  call    cs:__guard_dispatch_icall_fptr
0x1807b3a99  nop
0x1807b3a9a  test    rsi, rsi
0x1807b3a9d  jz      short loc_1807B3AAF
0x1807b3a9f  mov     rax, [rsi]
0x1807b3aa2  mov     rcx, rsi
0x1807b3aa5  mov     rax, [rax+8]
0x1807b3aa9  call    cs:__guard_dispatch_icall_fptr
0x1807b3aaf  mov     rax, r15
0x1807b3ab2  add     rsp, 0F8h
0x1807b3ab9  pop     r15
0x1807b3abb  pop     r14
0x1807b3abd  pop     rdi
0x1807b3abe  pop     rsi
0x1807b3abf  pop     rbx
0x1807b3ac0  pop     rbp
0x1807b3ac1  retn
```
