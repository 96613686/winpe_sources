# Art::ChartRectangleHandleFactoryState::CreateEffect(void)

- ea: `0x1807a38c0`
- end: `0x1807a3b32`
- name: `?CreateEffect@ChartRectangleHandleFactoryState@Art@@UEBA?AV?$TCntPtr@UIEffect@GEL@@@Ofc@@XZ`
- size: `626`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180071720`
- `0x1807a38c0`

## import_xrefs

- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a3930`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a3974`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a39b5`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a39e2`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a3930`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a3974`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a39b5`
- `gfx!?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z` at `0x1807a39e2`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1807a39f2`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1807a39f2`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x1807a3a21`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x1807a3a21`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1807a38e3`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1807a38e3`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1807a3a4a`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1807a3a4a`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1807a3aa2`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1807a3aa2`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1807a3a83`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1807a3a83`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1807a3a2b`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1807a3a2b`

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
0x1807a38c0  mov     [rsp-8+arg_8], rdx
0x1807a38c5  push    rbp
0x1807a38c6  push    rbx
0x1807a38c7  push    rsi
0x1807a38c8  push    rdi
0x1807a38c9  push    r14
0x1807a38cb  push    r15
0x1807a38cd  lea     rbp, [rsp-2Fh]
0x1807a38d2  sub     rsp, 0F8h
0x1807a38d9  mov     r15, rdx
0x1807a38dc  mov     r14, rcx
0x1807a38df  lea     rcx, [rbp+57h+var_78]
0x1807a38e3  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x1807a38e9  movsd   xmm3, qword ptr [r14+38h]
0x1807a38ef  movsd   xmm2, qword ptr [r14+28h]
0x1807a38f5  movaps  xmm0, xmm2
0x1807a38f8  subsd   xmm0, xmm3
0x1807a38fc  movsd   [rsp+120h+var_F8], xmm0
0x1807a3902  movsd   xmm1, qword ptr [r14+30h]
0x1807a3908  subsd   xmm1, xmm3
0x1807a390c  movsd   [rsp+120h+var_F0], xmm1
0x1807a3912  addsd   xmm2, xmm3
0x1807a3916  movsd   [rsp+120h+var_E8], xmm2
0x1807a391c  addsd   xmm3, qword ptr [r14+30h]
0x1807a3922  movsd   [rsp+120h+var_E0], xmm3
0x1807a3928  lea     rdx, [rsp+120h+var_F8]
0x1807a392d  mov     rcx, rax
0x1807a3930  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807a3936  movsd   xmm3, qword ptr [r14+38h]
0x1807a393c  movsd   xmm2, qword ptr [r14+28h]
0x1807a3942  movaps  xmm1, xmm3
0x1807a3945  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x1807a394c  movaps  xmm0, xmm2
0x1807a394f  subsd   xmm0, xmm3
0x1807a3953  movsd   [rsp+120h+var_D8], xmm0
0x1807a3959  movsd   [rbp+57h+var_D0], xmm1
0x1807a395e  addsd   xmm2, xmm3
0x1807a3962  movsd   [rbp+57h+var_C8], xmm2
0x1807a3967  movsd   [rbp+57h+var_C0], xmm3
0x1807a396c  lea     rdx, [rsp+120h+var_D8]
0x1807a3971  mov     rcx, rax
0x1807a3974  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807a397a  movsd   xmm2, qword ptr [r14+38h]
0x1807a3980  movaps  xmm0, xmm2
0x1807a3983  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1807a398a  movsd   [rbp+57h+var_B8], xmm0
0x1807a398f  movsd   xmm1, qword ptr [r14+30h]
0x1807a3995  subsd   xmm1, xmm2
0x1807a3999  movsd   [rbp+57h+var_B0], xmm1
0x1807a399e  movsd   [rbp+57h+var_A8], xmm2
0x1807a39a3  addsd   xmm2, qword ptr [r14+30h]
0x1807a39a9  movsd   [rbp+57h+var_A0], xmm2
0x1807a39ae  lea     rdx, [rbp+57h+var_B8]
0x1807a39b2  mov     rcx, rax
0x1807a39b5  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807a39bb  movsd   xmm1, qword ptr [r14+38h]
0x1807a39c1  unpcklpd xmm1, xmm1
0x1807a39c5  movaps  xmm0, xmm1
0x1807a39c8  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x1807a39cf  unpcklpd xmm0, xmm0
0x1807a39d3  movups  [rbp+57h+var_98], xmm0
0x1807a39d7  movups  [rbp+57h+var_88], xmm1
0x1807a39db  lea     rdx, [rbp+57h+var_98]
0x1807a39df  mov     rcx, rax
0x1807a39e2  call    cs:__imp_?AddEllipse@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TRect@N@Math@@@Z; GEL::PathBuilder::AddEllipse(Math::TRect<double> const &)
0x1807a39e8  xor     r8d, r8d
0x1807a39eb  lea     rdx, [rbp+57h+arg_10]
0x1807a39ef  mov     rcx, rax
0x1807a39f2  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x1807a39f8  mov     rsi, [rax]
0x1807a39fb  mov     qword ptr [rax], 0
0x1807a3a02  mov     [rbp+57h+arg_18], rsi
0x1807a3a06  mov     rcx, [rbp+57h+arg_10]
0x1807a3a0a  test    rcx, rcx
0x1807a3a0d  jz      short loc_1807A3A1D
0x1807a3a0f  mov     rax, [rcx]
0x1807a3a12  mov     rax, [rax+8]
0x1807a3a16  call    cs:__guard_dispatch_icall_fptr
0x1807a3a1c  nop
0x1807a3a1d  lea     rcx, [rbp+57h+var_78]
0x1807a3a21  call    cs:__imp_??1PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::~PathBuilder(void)
0x1807a3a27  lea     rcx, [rbp+57h+arg_8]
0x1807a3a2b  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1807a3a31  mov     rbx, [rbp+57h+arg_8]
0x1807a3a35  mov     rax, [rbx]
0x1807a3a38  mov     rdi, [rax+90h]
0x1807a3a3f  lea     r8, [r14+18h]
0x1807a3a43  mov     rdx, rsi
0x1807a3a46  lea     rcx, [rbp+57h+arg_10]
0x1807a3a4a  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::Color const &)
0x1807a3a50  mov     rdx, [rax]
0x1807a3a53  mov     rcx, rbx
0x1807a3a56  mov     rax, rdi
0x1807a3a59  call    cs:__guard_dispatch_icall_fptr
0x1807a3a5f  mov     rcx, [rbp+57h+arg_10]
0x1807a3a63  test    rcx, rcx
0x1807a3a66  jz      short loc_1807A3A75
0x1807a3a68  mov     rax, [rcx]
0x1807a3a6b  mov     rax, [rax+8]
0x1807a3a6f  call    cs:__guard_dispatch_icall_fptr
0x1807a3a75  lea     r8, [r14+8]
0x1807a3a79  movsd   xmm1, qword ptr [r14+40h]
0x1807a3a7f  lea     rcx, [rbp+57h+arg_0]
0x1807a3a83  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x1807a3a89  mov     rbx, [rbp+57h+arg_8]
0x1807a3a8d  mov     rax, [rbx]
0x1807a3a90  mov     rdi, [rax+90h]
0x1807a3a97  mov     r8, [rbp+57h+arg_0]
0x1807a3a9b  mov     rdx, rsi
0x1807a3a9e  lea     rcx, [rbp+57h+arg_10]
0x1807a3aa2  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x1807a3aa8  mov     rdx, [rax]
0x1807a3aab  mov     rcx, rbx
0x1807a3aae  mov     rax, rdi
0x1807a3ab1  call    cs:__guard_dispatch_icall_fptr
0x1807a3ab7  mov     rcx, [rbp+57h+arg_10]
0x1807a3abb  test    rcx, rcx
0x1807a3abe  jz      short loc_1807A3ACD
0x1807a3ac0  mov     rax, [rcx]
0x1807a3ac3  mov     rax, [rax+8]
0x1807a3ac7  call    cs:__guard_dispatch_icall_fptr
0x1807a3acd  mov     rax, [rbp+57h+arg_8]
0x1807a3ad1  xor     ecx, ecx
0x1807a3ad3  mov     [rbp+57h+arg_8], rcx
0x1807a3ad7  mov     [r15], rax
0x1807a3ada  mov     rdx, [rbp+57h+arg_0]
0x1807a3ade  test    rdx, rdx
0x1807a3ae1  jz      short loc_1807A3AF7
0x1807a3ae3  mov     rax, [rdx]
0x1807a3ae6  mov     rcx, rdx
0x1807a3ae9  mov     rax, [rax+8]
0x1807a3aed  call    cs:__guard_dispatch_icall_fptr
0x1807a3af3  mov     rcx, [rbp+57h+arg_8]
0x1807a3af7  test    rcx, rcx
0x1807a3afa  jz      short loc_1807A3B0A
0x1807a3afc  mov     rax, [rcx]
0x1807a3aff  mov     rax, [rax+8]
0x1807a3b03  call    cs:__guard_dispatch_icall_fptr
0x1807a3b09  nop
0x1807a3b0a  test    rsi, rsi
0x1807a3b0d  jz      short loc_1807A3B1F
0x1807a3b0f  mov     rax, [rsi]
0x1807a3b12  mov     rcx, rsi
0x1807a3b15  mov     rax, [rax+8]
0x1807a3b19  call    cs:__guard_dispatch_icall_fptr
0x1807a3b1f  mov     rax, r15
0x1807a3b22  add     rsp, 0F8h
0x1807a3b29  pop     r15
0x1807a3b2b  pop     r14
0x1807a3b2d  pop     rdi
0x1807a3b2e  pop     rsi
0x1807a3b2f  pop     rbx
0x1807a3b30  pop     rbp
0x1807a3b31  retn
```
