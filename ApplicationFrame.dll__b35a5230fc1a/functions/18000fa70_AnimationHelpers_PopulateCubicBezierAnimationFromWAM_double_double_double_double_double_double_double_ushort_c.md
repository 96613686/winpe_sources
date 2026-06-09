# AnimationHelpers::PopulateCubicBezierAnimationFromWAM(double,double,double,double,double,double,double,ushort const *,IDCompositionAnimation *)

- ea: `0x18000fa70`
- end: `0x1800101c8`
- name: `?PopulateCubicBezierAnimationFromWAM@AnimationHelpers@@YAJNNNNNNNPEBGPEAUIDCompositionAnimation@@@Z`
- size: `1880`
- prototype: `__int64 __fastcall(AnimationHelpers *__hidden this, double, double, double, double, double, double, unsigned __int16 *, const unsigned __int16 *, struct IDCompositionAnimation *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005298`
- `0x18000ecc4`

## callees

- `0x180004c98`
- `0x18000fa70`
- `0x180010478`
- `0x1800105f8`
- `0x180010684`
- `0x180010b58`
- `0x180040270`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fbbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fbfb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fbbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fbfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall AnimationHelpers::PopulateCubicBezierAnimationFromWAM(
        AnimationHelpers *this,
        double a2,
        double a3,
        double a4,
        double a5,
        double a6,
        double a7,
        unsigned __int16 *a8,
        const unsigned __int16 *a9)
{
  HRESULT v9; // eax
  int v10; // ebx
  HRESULT v11; // eax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID); // rbx
  int v14; // eax
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int64 *); // rbx
  int v17; // eax
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, __int64, _QWORD *); // rbx
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  LPVOID v28; // rcx
  LPVOID v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  LPVOID v32; // rcx
  LPVOID v33; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  LPVOID v38; // rcx
  LPVOID v39; // rcx
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  LPVOID v44; // rcx
  LPVOID v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  LPVOID v49; // rcx
  LPVOID v50; // rcx
  __int64 v51; // rdx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  LPVOID v54; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID v55; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v58[2]; // [rsp+78h] [rbp-90h] BYREF
  void **v59; // [rsp+88h] [rbp-80h] BYREF
  int v60; // [rsp+90h] [rbp-78h] BYREF
  char v61; // [rsp+94h] [rbp-74h]
  int v62; // [rsp+B8h] [rbp-50h] BYREF
  const char *v63; // [rsp+C0h] [rbp-48h]
  __int64 v64; // [rsp+C8h] [rbp-40h]
  char v65; // [rsp+D0h] [rbp-38h]
  int v66; // [rsp+D8h] [rbp-30h]
  __int128 v67; // [rsp+E0h] [rbp-28h]
  __int128 v68; // [rsp+F0h] [rbp-18h]
  __int128 v69; // [rsp+100h] [rbp-8h]
  __int128 v70; // [rsp+110h] [rbp+8h]
  __int128 v71; // [rsp+120h] [rbp+18h]
  __int128 v72; // [rsp+130h] [rbp+28h]
  __int128 v73; // [rsp+140h] [rbp+38h]
  __int128 v74; // [rsp+150h] [rbp+48h]
  __int128 v75; // [rsp+160h] [rbp+58h]
  __int64 v76; // [rsp+170h] [rbp+68h]
  __int128 v77; // [rsp+178h] [rbp+70h]
  int v78; // [rsp+188h] [rbp+80h]
  __int64 v79; // [rsp+190h] [rbp+88h]
  int *v80; // [rsp+198h] [rbp+90h]
  __int64 v81; // [rsp+1A0h] [rbp+98h]
  __int64 v82; // [rsp+1A8h] [rbp+A0h]
  void ***v83; // [rsp+1B0h] [rbp+A8h]
  __int64 v84; // [rsp+1B8h] [rbp+B0h]
  int v85; // [rsp+1C0h] [rbp+B8h]
  int *v86; // [rsp+1C8h] [rbp+C0h]
  char v87; // [rsp+1D0h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  v60 = 0;
  v61 = 0;
  v65 = 0;
  v62 = 0;
  v63 = "PopulateAnimationFromWAM";
  v64 = 0;
  v66 = 0;
  v77 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v78 = 1;
  v79 = 0;
  v80 = &v60;
  v81 = 0;
  v82 = 0;
  v83 = &v59;
  v84 = 0;
  v85 = 0;
  v86 = &v62;
  v87 = 0;
  v59 = &SystemVisualTelemetry::PopulateAnimationFromWAM::`vftable';
  SystemVisualTelemetry::PopulateAnimationFromWAM::StartActivity(
    (SystemVisualTelemetry::PopulateAnimationFromWAM *)&v59,
    a8);
  v54 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
  v9 = CoCreateInstance(&CLSID_UIAnimationManager2, 0, 1u, &GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1, &v54);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v9,
      ppv);
LABEL_66:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v54);
LABEL_27:
    v59 = &SystemVisualTelemetry::PopulateAnimationFromWAM::`vftable';
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v59);
    wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v59);
    return (unsigned int)v10;
  }
  v55 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
  v11 = CoCreateInstance(&CLSID_UIAnimationTransitionLibrary2, 0, 1u, &GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a, &v55);
  v10 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v11,
      ppva);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    goto LABEL_66;
  }
  v57 = 0;
  v12 = v55;
  v13 = *(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 160LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
  v14 = v13(v12);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v14,
      SLODWORD(a5));
LABEL_65:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    goto LABEL_66;
  }
  v56 = 0;
  v15 = v54;
  v16 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v54 + 48LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
  v17 = v16(v15, &v56);
  v10 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v17,
      SLODWORD(a5));
    v30 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_27;
  }
  v58[0] = 0;
  v18 = v54;
  v19 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD *))(*(_QWORD *)v54 + 32LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v58);
  v21 = v19(v18, v20, v58);
  v10 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v21,
      SLODWORD(a5));
    v35 = v58[0];
    if ( v58[0] )
    {
      v58[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
    }
    goto LABEL_27;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v56 + 24LL))(v56, v58[0], v57);
  if ( v10 < 0 )
  {
    v51 = 192;
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v51,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v10,
      SLODWORD(a5));
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v58);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v56);
    goto LABEL_65;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v56 + 96LL))(v56, v22, 0);
  v10 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v23,
      SLODWORD(a5));
    v25 = v58[0];
    if ( v58[0] )
    {
      v58[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
    }
    goto LABEL_27;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v54 + 72LL))(v54, v24, 0);
  if ( v10 < 0 )
  {
    v51 = 198;
    goto LABEL_70;
  }
  v40 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(*(_QWORD *)v58[0] + 48LL))(v58[0], a9);
  v10 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v40,
      SLODWORD(a5));
    v41 = v58[0];
    if ( v58[0] )
    {
      v58[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 16LL))(v45);
    }
    goto LABEL_27;
  }
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v59);
  v46 = v58[0];
  if ( v58[0] )
  {
    v58[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v59 = &SystemVisualTelemetry::PopulateAnimationFromWAM::`vftable';
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v59);
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v59);
  return 0;
}

```

## disassembly

```asm
0x18000fa70  mov     rax, rsp
0x18000fa73  push    rbp
0x18000fa74  push    rbx
0x18000fa75  push    rsi
0x18000fa76  push    rdi
0x18000fa77  push    r14
0x18000fa79  push    r15
0x18000fa7b  lea     rbp, [rax-158h]
0x18000fa82  sub     rsp, 228h
0x18000fa89  movaps  xmmword ptr [rax-48h], xmm6
0x18000fa8d  movaps  xmmword ptr [rax-58h], xmm7
0x18000fa91  movaps  xmmword ptr [rax-68h], xmm8
0x18000fa96  movaps  xmmword ptr [rax-78h], xmm9
0x18000fa9b  mov     rax, cs:__security_cookie
0x18000faa2  xor     rax, rsp
0x18000faa5  mov     [rbp+150h+var_80], rax
0x18000faac  movaps  xmm8, xmm3
0x18000fab0  movaps  xmm7, xmm2
0x18000fab3  movaps  xmm9, xmm1
0x18000fab7  movaps  xmm6, xmm0
0x18000faba  mov     rdx, [rbp+150h+arg_38]; unsigned __int16 *
0x18000fac1  mov     rsi, [rbp+150h+arg_40]
0x18000fac8  xor     r14d, r14d
0x18000facb  mov     [rbp+150h+var_1C8], r14d
0x18000facf  mov     [rbp+150h+var_1C4], r14b
0x18000fad3  mov     [rbp+150h+var_188], r14b
0x18000fad7  mov     [rbp+150h+var_1A0], r14d
0x18000fadb  lea     rax, aPopulateanimat; "PopulateAnimationFromWAM"
0x18000fae2  mov     [rbp+150h+var_198], rax
0x18000fae6  mov     [rbp+150h+var_190], r14
0x18000faea  mov     [rbp+150h+var_180], r14d
0x18000faee  xorps   xmm0, xmm0
0x18000faf1  movdqa  [rbp+150h+var_E0], xmm0
0x18000faf6  xorps   xmm1, xmm1
0x18000faf9  xor     eax, eax
0x18000fafb  movups  [rbp+150h+var_178], xmm1
0x18000faff  movups  [rbp+150h+var_168], xmm1
0x18000fb03  movups  [rbp+150h+var_158], xmm1
0x18000fb07  movups  [rbp+150h+var_148], xmm1
0x18000fb0b  movups  [rbp+150h+var_138], xmm1
0x18000fb0f  movups  [rbp+150h+var_128], xmm1
0x18000fb13  movups  [rbp+150h+var_118], xmm1
0x18000fb17  movups  [rbp+150h+var_108], xmm1
0x18000fb1b  movups  [rbp+150h+var_F8], xmm1
0x18000fb1f  mov     [rbp+150h+var_E8], rax
0x18000fb23  mov     [rbp+150h+var_D0], 1
0x18000fb2d  mov     [rbp+150h+var_C8], rax
0x18000fb34  lea     rax, [rbp+150h+var_1C8]
0x18000fb38  mov     [rbp+150h+var_C0], rax
0x18000fb3f  mov     [rbp+150h+var_B8], r14
0x18000fb46  mov     [rbp+150h+var_B0], r14
0x18000fb4d  lea     rax, [rbp+150h+var_1D0]
0x18000fb51  mov     [rbp+150h+var_A8], rax
0x18000fb58  mov     [rbp+150h+var_A0], r14
0x18000fb5f  mov     [rbp+150h+var_98], r14d
0x18000fb66  lea     rax, [rbp+150h+var_1A0]
0x18000fb6a  mov     [rbp+150h+var_90], rax
0x18000fb71  mov     [rbp+150h+var_88], r14b
0x18000fb78  lea     r15, ??_7PopulateAnimationFromWAM@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::PopulateAnimationFromWAM::`vftable'
0x18000fb7f  mov     [rbp+150h+var_1D0], r15
0x18000fb83  lea     rcx, [rbp+150h+var_1D0]; this
0x18000fb87  call    ?StartActivity@PopulateAnimationFromWAM@SystemVisualTelemetry@@QEAAXPEBG@Z; SystemVisualTelemetry::PopulateAnimationFromWAM::StartActivity(ushort const *)
0x18000fb8c  nop
0x18000fb8d  mov     [rsp+250h+var_200], r14
0x18000fb92  lea     rcx, [rsp+250h+var_200]
0x18000fb97  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000fb9c  lea     rax, [rsp+250h+var_200]
0x18000fba1  mov     [rsp+250h+ppv], rax; int
0x18000fba6  lea     r9, _GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1; riid
0x18000fbad  xor     edx, edx; pUnkOuter
0x18000fbaf  mov     r8d, 1; dwClsContext
0x18000fbb5  lea     rcx, CLSID_UIAnimationManager2; rclsid
0x18000fbbc  call    cs:__imp_CoCreateInstance
0x18000fbc2  mov     ebx, eax
0x18000fbc4  test    eax, eax
0x18000fbc6  js      loc_180010104
0x18000fbcc  mov     [rsp+250h+var_1F8], r14
0x18000fbd1  lea     rcx, [rsp+250h+var_1F8]
0x18000fbd6  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000fbdb  lea     rax, [rsp+250h+var_1F8]
0x18000fbe0  mov     [rsp+250h+ppv], rax; int
0x18000fbe5  lea     r9, _GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a; riid
0x18000fbec  xor     edx, edx; pUnkOuter
0x18000fbee  mov     r8d, 1; dwClsContext
0x18000fbf4  lea     rcx, CLSID_UIAnimationTransitionLibrary2; rclsid
0x18000fbfb  call    cs:__imp_CoCreateInstance
0x18000fc01  mov     ebx, eax
0x18000fc03  test    eax, eax
0x18000fc05  js      loc_180010162
0x18000fc0b  mov     [rsp+250h+var_1E8], r14
0x18000fc10  mov     rdi, [rsp+250h+var_1F8]
0x18000fc15  mov     rax, [rdi]
0x18000fc18  mov     rbx, [rax+0A0h]
0x18000fc1f  lea     rcx, [rsp+250h+var_1E8]
0x18000fc24  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000fc29  lea     rax, [rsp+250h+var_1E8]
0x18000fc2e  mov     [rsp+250h+var_218], rax
0x18000fc33  movsd   xmm0, [rbp+150h+arg_30]
0x18000fc3b  movsd   qword ptr [rsp+250h+var_228+8], xmm0
0x18000fc41  movsd   xmm4, [rbp+150h+arg_28]
0x18000fc49  movsd   qword ptr [rsp+250h+var_228], xmm4
0x18000fc4f  movsd   xmm0, [rbp+150h+arg_20]
0x18000fc57  movsd   [rsp+250h+ppv], xmm0; int
0x18000fc5d  movaps  xmm3, xmm8
0x18000fc61  movaps  xmm2, xmm7
0x18000fc64  movaps  xmm1, xmm6
0x18000fc67  mov     rcx, rdi
0x18000fc6a  mov     rax, rbx
0x18000fc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc72  mov     ebx, eax
0x18000fc74  test    eax, eax
0x18000fc76  js      loc_180010121
0x18000fc7c  mov     [rsp+250h+var_1F0], r14
0x18000fc81  mov     rdi, [rsp+250h+var_200]
0x18000fc86  mov     rax, [rdi]
0x18000fc89  mov     rbx, [rax+30h]
0x18000fc8d  lea     rcx, [rsp+250h+var_1F0]
0x18000fc92  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000fc97  lea     rdx, [rsp+250h+var_1F0]
0x18000fc9c  mov     rcx, rdi
0x18000fc9f  mov     rax, rbx
0x18000fca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fca7  mov     ebx, eax
0x18000fca9  test    eax, eax
0x18000fcab  js      loc_18000FDDD
0x18000fcb1  mov     [rsp+250h+var_1E0], r14
0x18000fcb6  mov     rdi, [rsp+250h+var_200]
0x18000fcbb  mov     rax, [rdi]
0x18000fcbe  mov     rbx, [rax+20h]
0x18000fcc2  lea     rcx, [rsp+250h+var_1E0]
0x18000fcc7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000fccc  lea     r8, [rsp+250h+var_1E0]
0x18000fcd1  movaps  xmm1, xmm9
0x18000fcd5  mov     rcx, rdi
0x18000fcd8  mov     rax, rbx
0x18000fcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fce0  mov     ebx, eax
0x18000fce2  test    eax, eax
0x18000fce4  js      loc_18000FEB8
0x18000fcea  mov     rcx, [rsp+250h+var_1F0]
0x18000fcef  mov     rax, [rcx]
0x18000fcf2  mov     r8, [rsp+250h+var_1E8]
0x18000fcf7  mov     rdx, [rsp+250h+var_1E0]
0x18000fcfc  mov     rax, [rax+18h]
0x18000fd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd05  mov     ebx, eax
0x18000fd07  test    eax, eax
0x18000fd09  js      loc_18001018A
0x18000fd0f  mov     rcx, [rsp+250h+var_1F0]
0x18000fd14  mov     rax, [rcx]
0x18000fd17  xor     r8d, r8d
0x18000fd1a  xorps   xmm1, xmm1
0x18000fd1d  mov     rax, [rax+60h]
0x18000fd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd26  mov     ebx, eax
0x18000fd28  test    eax, eax
0x18000fd2a  jns     loc_18000FF65
0x18000fd30  mov     rcx, [rbp+158h]; this
0x18000fd37  mov     r9d, eax; char *
0x18000fd3a  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000fd41  mov     edx, 0C4h; void *
0x18000fd46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd4b  nop
0x18000fd4c  mov     rcx, [rsp+250h+var_1E0]
0x18000fd51  test    rcx, rcx
0x18000fd54  jz      short loc_18000FD68
0x18000fd56  mov     [rsp+250h+var_1E0], r14
0x18000fd5b  mov     rax, [rcx]
0x18000fd5e  mov     rax, [rax+10h]
0x18000fd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd67  nop
0x18000fd68  mov     rcx, [rsp+250h+var_1F0]
0x18000fd6d  test    rcx, rcx
0x18000fd70  jz      short loc_18000FD84
0x18000fd72  mov     [rsp+250h+var_1F0], r14
0x18000fd77  mov     rax, [rcx]
0x18000fd7a  mov     rax, [rax+10h]
0x18000fd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd83  nop
0x18000fd84  mov     rcx, [rsp+250h+var_1E8]
0x18000fd89  test    rcx, rcx
0x18000fd8c  jz      short loc_18000FDA0
0x18000fd8e  mov     [rsp+250h+var_1E8], r14
0x18000fd93  mov     rax, [rcx]
0x18000fd96  mov     rax, [rax+10h]
0x18000fd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd9f  nop
0x18000fda0  mov     rcx, [rsp+250h+var_1F8]
0x18000fda5  test    rcx, rcx
0x18000fda8  jz      short loc_18000FDBC
0x18000fdaa  mov     [rsp+250h+var_1F8], r14
0x18000fdaf  mov     rax, [rcx]
0x18000fdb2  mov     rax, [rax+10h]
0x18000fdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdbb  nop
0x18000fdbc  mov     rcx, [rsp+250h+var_200]
0x18000fdc1  test    rcx, rcx
0x18000fdc4  jz      short loc_18000FDD8
0x18000fdc6  mov     [rsp+250h+var_200], r14
0x18000fdcb  mov     rax, [rcx]
0x18000fdce  mov     rax, [rax+10h]
0x18000fdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd7  nop
0x18000fdd8  jmp     loc_18000FE69
0x18000fddd  mov     rcx, [rbp+158h]; this
0x18000fde4  mov     r9d, ebx; char *
0x18000fde7  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000fdee  mov     edx, 0BBh; void *
0x18000fdf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fdf8  nop
0x18000fdf9  mov     rcx, [rsp+250h+var_1F0]
0x18000fdfe  test    rcx, rcx
0x18000fe01  jz      short loc_18000FE15
0x18000fe03  mov     [rsp+250h+var_1F0], r14
0x18000fe08  mov     rax, [rcx]
0x18000fe0b  mov     rax, [rax+10h]
0x18000fe0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe14  nop
0x18000fe15  mov     rcx, [rsp+250h+var_1E8]
0x18000fe1a  test    rcx, rcx
0x18000fe1d  jz      short loc_18000FE31
0x18000fe1f  mov     [rsp+250h+var_1E8], r14
0x18000fe24  mov     rax, [rcx]
0x18000fe27  mov     rax, [rax+10h]
0x18000fe2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe30  nop
0x18000fe31  mov     rcx, [rsp+250h+var_1F8]
0x18000fe36  test    rcx, rcx
0x18000fe39  jz      short loc_18000FE4D
0x18000fe3b  mov     [rsp+250h+var_1F8], r14
0x18000fe40  mov     rax, [rcx]
0x18000fe43  mov     rax, [rax+10h]
0x18000fe47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe4c  nop
0x18000fe4d  mov     rcx, [rsp+250h+var_200]
0x18000fe52  test    rcx, rcx
0x18000fe55  jz      short loc_18000FE69
0x18000fe57  mov     [rsp+250h+var_200], r14
0x18000fe5c  mov     rax, [rcx]
0x18000fe5f  mov     rax, [rax+10h]
0x18000fe63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe68  nop
0x18000fe69  mov     [rbp+150h+var_1D0], r15
0x18000fe6d  lea     rcx, [rbp+150h+var_1D0]
0x18000fe71  call    ?Destroy@?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000fe76  lea     rcx, [rbp+150h+var_1D0]
0x18000fe7a  call    ??1?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000fe7f  mov     eax, ebx
0x18000fe81  mov     rcx, [rbp+150h+var_80]
0x18000fe88  xor     rcx, rsp; StackCookie
0x18000fe8b  call    __security_check_cookie
0x18000fe90  lea     r11, [rsp+250h+var_28]
0x18000fe98  movaps  xmm6, xmmword ptr [r11-18h]
0x18000fe9d  movaps  xmm7, xmmword ptr [r11-28h]
0x18000fea2  movaps  xmm8, xmmword ptr [r11-38h]
0x18000fea7  movaps  xmm9, xmmword ptr [r11-48h]
0x18000feac  mov     rsp, r11
0x18000feaf  pop     r15
0x18000feb1  pop     r14
0x18000feb3  pop     rdi
0x18000feb4  pop     rsi
0x18000feb5  pop     rbx
0x18000feb6  pop     rbp
0x18000feb7  retn
0x18000feb8  mov     rcx, [rbp+158h]; this
0x18000febf  mov     r9d, ebx; char *
0x18000fec2  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000fec9  mov     edx, 0BEh; void *
0x18000fece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fed3  nop
0x18000fed4  mov     rcx, [rsp+250h+var_1E0]
0x18000fed9  test    rcx, rcx
0x18000fedc  jz      short loc_18000FEF0
0x18000fede  mov     [rsp+250h+var_1E0], r14
0x18000fee3  mov     rax, [rcx]
0x18000fee6  mov     rax, [rax+10h]
0x18000feea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feef  nop
0x18000fef0  mov     rcx, [rsp+250h+var_1F0]
0x18000fef5  test    rcx, rcx
0x18000fef8  jz      short loc_18000FF0C
0x18000fefa  mov     [rsp+250h+var_1F0], r14
0x18000feff  mov     rax, [rcx]
0x18000ff02  mov     rax, [rax+10h]
0x18000ff06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff0b  nop
0x18000ff0c  mov     rcx, [rsp+250h+var_1E8]
0x18000ff11  test    rcx, rcx
0x18000ff14  jz      short loc_18000FF28
0x18000ff16  mov     [rsp+250h+var_1E8], r14
0x18000ff1b  mov     rax, [rcx]
0x18000ff1e  mov     rax, [rax+10h]
0x18000ff22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff27  nop
0x18000ff28  mov     rcx, [rsp+250h+var_1F8]
0x18000ff2d  test    rcx, rcx
0x18000ff30  jz      short loc_18000FF44
0x18000ff32  mov     [rsp+250h+var_1F8], r14
0x18000ff37  mov     rax, [rcx]
0x18000ff3a  mov     rax, [rax+10h]
  ... truncated ...
```
