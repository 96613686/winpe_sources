# AnimationHelpers::LoadTranslateAnimation(IDCompositionDevice3 *,int,int,ushort const *,tagPOINT *,tagPOINT *,ulong *,IDCompositionTranslateTransform * *)

- ea: `0x18000ecc4`
- end: `0x18000f364`
- name: `?LoadTranslateAnimation@AnimationHelpers@@YAJPEAUIDCompositionDevice3@@HHPEBGPEAUtagPOINT@@2PEAKPEAPEAUIDCompositionTranslateTransform@@@Z`
- size: `1696`
- prototype: `int(AnimationHelpers *__hidden this, struct IDCompositionDevice3 *, int, int, const unsigned __int16 *, struct tagPOINT *, struct tagPOINT *, unsigned int *, struct IDCompositionTranslateTransform **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e69c`

## callees

- `0x180004c98`
- `0x18000ecc4`
- `0x18000f36c`
- `0x18000fa70`
- `0x180010478`
- `0x1800105f8`
- `0x180010728`
- `0x180010b58`
- `0x1800386bc`
- `0x180040270`
- `0x18004159c`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `UxTheme!GetThemeTimingFunction` at `0x18000efd2`
- `UxTheme!GetThemeTimingFunction` at `0x18000efd2`
- `UxTheme!CloseThemeData` at `0x18000effc`
- `UxTheme!CloseThemeData` at `0x18000f005`
- `UxTheme!CloseThemeData` at `0x18000f292`
- `UxTheme!CloseThemeData` at `0x18000f2a0`
- `UxTheme!CloseThemeData` at `0x18000effc`
- `UxTheme!CloseThemeData` at `0x18000f005`
- `UxTheme!CloseThemeData` at `0x18000f292`
- `UxTheme!CloseThemeData` at `0x18000f2a0`
- `UxTheme!OpenThemeData` at `0x18000ef0f`
- `UxTheme!OpenThemeData` at `0x18000ef26`
- `UxTheme!OpenThemeData` at `0x18000ef0f`
- `UxTheme!OpenThemeData` at `0x18000ef26`
- `UxTheme!GetThemeAnimationTransform` at `0x18000ef76`
- `UxTheme!GetThemeAnimationTransform` at `0x18000ef76`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AnimationHelpers::LoadTranslateAnimation(
        AnimationHelpers *this,
        struct IDCompositionDevice3 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct tagPOINT *a6,
        struct tagPOINT *a7,
        unsigned int *a8)
{
  unsigned int v9; // r13d
  __int64 (__fastcall *v11)(AnimationHelpers *, AnimationHelpers **); // rbx
  int v12; // eax
  int v13; // esi
  AnimationHelpers *v14; // rcx
  __int64 (__fastcall *v15)(AnimationHelpers *, AnimationHelpers **); // rbx
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(AnimationHelpers *, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rcx
  AnimationHelpers *v22; // rcx
  AnimationHelpers *v23; // rcx
  HTHEME v24; // rdi
  HTHEME v25; // rax
  void *v26; // rbx
  int ThemeAnimationTransform; // eax
  int ThemeTimingFunction; // eax
  int v29; // eax
  __int64 v30; // rcx
  AnimationHelpers *v31; // rcx
  AnimationHelpers *v32; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  AnimationHelpers *v36; // rcx
  AnimationHelpers *v37; // rcx
  __int64 v38; // rcx
  AnimationHelpers *v39; // rcx
  AnimationHelpers *v40; // rcx
  int v41; // [rsp+28h] [rbp-E0h]
  int *v42; // [rsp+28h] [rbp-E0h]
  int v43; // [rsp+28h] [rbp-E0h]
  struct IDCompositionAnimation *v44; // [rsp+50h] [rbp-B8h]
  struct IDCompositionAnimation *v45; // [rsp+50h] [rbp-B8h]
  __int64 v46; // [rsp+58h] [rbp-B0h] BYREF
  AnimationHelpers *v47; // [rsp+60h] [rbp-A8h] BYREF
  AnimationHelpers *v48; // [rsp+68h] [rbp-A0h] BYREF
  int v49[2]; // [rsp+70h] [rbp-98h] BYREF
  HTHEME v50; // [rsp+78h] [rbp-90h] BYREF
  HTHEME v51; // [rsp+80h] [rbp-88h] BYREF
  unsigned int *v52; // [rsp+88h] [rbp-80h]
  struct tagPOINT *v53; // [rsp+90h] [rbp-78h]
  __int128 v54; // [rsp+98h] [rbp-70h] BYREF
  float v55; // [rsp+A8h] [rbp-60h]
  int v56[4]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v57[28]; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v58[42]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+290h] [rbp+188h]

  v9 = (unsigned int)a2;
  v53 = a7;
  v52 = a8;
  a7->x = 0;
  *(_QWORD *)a8 = 0;
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v58,
    "LoadAnimation");
  v58[0] = &SystemVisualTelemetry::LoadAnimation::`vftable';
  SystemVisualTelemetry::LoadAnimation::StartActivity((SystemVisualTelemetry::LoadAnimation *)v58, a4, v9, 1);
  v48 = 0;
  v47 = 0;
  v46 = 0;
  v11 = *(__int64 (__fastcall **)(AnimationHelpers *, AnimationHelpers **))(*(_QWORD *)this + 184LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v48);
  v12 = v11(this, &v48);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v15 = *(__int64 (__fastcall **)(AnimationHelpers *, AnimationHelpers **))(*(_QWORD *)this + 184LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v47);
    v16 = v15(this, &v47);
    v17 = v16;
    if ( v16 < 0 )
    {
      v18 = 115;
      goto LABEL_32;
    }
    v19 = *(__int64 (__fastcall **)(AnimationHelpers *, __int64 *))(*(_QWORD *)this + 80LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v46);
    v20 = v19(this, &v46);
    v13 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
        (const char *)(unsigned int)v20,
        v41);
      v21 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v47;
      if ( v47 )
      {
        v47 = 0;
        (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v23 + 16LL))(v23);
      }
      goto LABEL_50;
    }
    *(_OWORD *)v56 = 0;
    memset(v57, 0, sizeof(v57));
    v54 = 0;
    v55 = 0.0;
    v24 = OpenThemeData(0, L"Animations");
    v51 = v24;
    v25 = OpenThemeData(0, L"TimingFunction");
    v26 = v25;
    v50 = v25;
    if ( v24 && v25 )
    {
      v49[0] = 0;
      ThemeAnimationTransform = GetThemeAnimationTransform(v24, v9, 1);
      v13 = ThemeAnimationTransform;
      if ( ThemeAnimationTransform >= 0 )
      {
        v42 = v49;
        ThemeTimingFunction = GetThemeTimingFunction(v26, (unsigned int)v56[1], &v54, 20);
        v13 = ThemeTimingFunction;
        if ( ThemeTimingFunction < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
            (const char *)(unsigned int)ThemeTimingFunction,
            (int)v49);
        CloseThemeData(v26);
        CloseThemeData(v24);
        if ( v13 >= 0 )
        {
          v29 = AnimationHelpers::PopulateCubicBezierAnimationFromWAM(
                  v48,
                  (double)*(int *)a5,
                  (double)a6->x,
                  *((float *)&v54 + 1),
                  *((float *)&v54 + 2),
                  *((float *)&v54 + 3),
                  v55,
                  a4,
                  (const unsigned __int16 *)v48,
                  v44);
          v13 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8F,
              (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
              (const char *)(unsigned int)v29,
              v43);
            v30 = v46;
            if ( v46 )
            {
              v46 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
            v31 = v47;
            if ( v47 )
            {
              v47 = 0;
              (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v31 + 16LL))(v31);
            }
            v32 = v48;
            if ( v48 )
            {
              v48 = 0;
              (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v32 + 16LL))(v32);
            }
            goto LABEL_50;
          }
          v16 = AnimationHelpers::PopulateCubicBezierAnimationFromWAM(
                  v47,
                  (double)*((int *)a5 + 1),
                  (double)a6->y,
                  *((float *)&v54 + 1),
                  *((float *)&v54 + 2),
                  *((float *)&v54 + 3),
                  v55,
                  a4,
                  (const unsigned __int16 *)v47,
                  v45);
          v17 = v16;
          if ( v16 >= 0 )
          {
            (*(void (__fastcall **)(__int64, AnimationHelpers *))(*(_QWORD *)v46 + 24LL))(v46, v48);
            (*(void (__fastcall **)(__int64, AnimationHelpers *))(*(_QWORD *)v46 + 40LL))(v46, v47);
            v34 = v46;
            v46 = 0;
            *(_QWORD *)v52 = v34;
            v53->x = v56[3];
            wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v58);
            v35 = v46;
            if ( v46 )
            {
              v46 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            }
            v36 = v47;
            if ( v47 )
            {
              v47 = 0;
              (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v36 + 16LL))(v36);
            }
            v37 = v48;
            if ( v48 )
            {
              v48 = 0;
              (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v37 + 16LL))(v37);
            }
            v13 = 0;
            goto LABEL_50;
          }
          v18 = 154;
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
            (const char *)(unsigned int)v16,
            v41);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v46);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v47);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v48);
          SystemVisualTelemetry::LoadAnimation::~LoadAnimation((SystemVisualTelemetry::LoadAnimation *)v58);
          return v17;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
          (const char *)(unsigned int)ThemeAnimationTransform,
          (int)v56);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v50);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
      }
    }
    else
    {
      v13 = -2147467260;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
        (const char *)0x80004004LL,
        v41);
      if ( v26 )
        CloseThemeData(v26);
      if ( v24 )
        CloseThemeData(v24);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
      (const char *)(unsigned int)v13,
      (int)v42);
    v38 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v40 + 16LL))(v40);
    }
    goto LABEL_50;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72,
    (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\animationhelpers.cpp",
    (const char *)(unsigned int)v12,
    v41);
  v14 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(AnimationHelpers *))(*(_QWORD *)v14 + 16LL))(v14);
  }
LABEL_50:
  v58[0] = &SystemVisualTelemetry::LoadAnimation::`vftable';
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v58);
  wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v58);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000ecc4  mov     rax, rsp
0x18000ecc7  mov     [rax+18h], rbx
0x18000eccb  push    rbp
0x18000eccc  push    rsi
0x18000eccd  push    rdi
0x18000ecce  push    r12
0x18000ecd0  push    r13
0x18000ecd2  push    r14
0x18000ecd4  push    r15
0x18000ecd6  lea     rbp, [rax-188h]
0x18000ecdd  sub     rsp, 250h
0x18000ece4  movaps  xmmword ptr [rax-48h], xmm6
0x18000ece8  mov     rax, cs:__security_cookie
0x18000ecef  xor     rax, rsp
0x18000ecf2  mov     [rbp+180h+var_50], rax
0x18000ecf9  mov     r14, r9
0x18000ecfc  mov     r13d, edx
0x18000ecff  mov     rdi, rcx
0x18000ed02  mov     r15, [rbp+180h+arg_20]
0x18000ed09  mov     r12, [rbp+180h+arg_28]
0x18000ed10  mov     rax, [rbp+180h+arg_30]
0x18000ed17  mov     [rbp+180h+var_1F8], rax
0x18000ed1b  mov     rcx, [rbp+180h+arg_38]
0x18000ed22  mov     [rbp+180h+var_200], rcx
0x18000ed26  mov     dword ptr [rax], 0
0x18000ed2c  mov     qword ptr [rcx], 0
0x18000ed33  lea     rdx, aLoadanimation; "LoadAnimation"
0x18000ed3a  lea     rcx, [rbp+180h+var_1A0]
0x18000ed3e  call    ??0?$ActivityBase@VCApplicationFrameLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ed43  lea     rax, ??_7LoadAnimation@SystemVisualTelemetry@@6B@; const SystemVisualTelemetry::LoadAnimation::`vftable'
0x18000ed4a  mov     [rbp+180h+var_1A0], rax
0x18000ed4e  mov     r9d, 1; int
0x18000ed54  mov     r8d, r13d; int
0x18000ed57  mov     rdx, r14; unsigned __int16 *
0x18000ed5a  lea     rcx, [rbp+180h+var_1A0]; this
0x18000ed5e  call    ?StartActivity@LoadAnimation@SystemVisualTelemetry@@QEAAXPEBGHH@Z; SystemVisualTelemetry::LoadAnimation::StartActivity(ushort const *,int,int)
0x18000ed63  nop
0x18000ed64  mov     [rsp+280h+var_220], 0
0x18000ed6d  mov     [rsp+280h+var_228], 0
0x18000ed76  mov     [rsp+280h+var_230], 0
0x18000ed7f  mov     rax, [rdi]
0x18000ed82  mov     rbx, [rax+0B8h]
0x18000ed89  lea     rcx, [rsp+280h+var_220]
0x18000ed8e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000ed93  lea     rdx, [rsp+280h+var_220]
0x18000ed98  mov     rcx, rdi
0x18000ed9b  mov     rax, rbx
0x18000ed9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda3  mov     esi, eax
0x18000eda5  xor     ebx, ebx
0x18000eda7  test    eax, eax
0x18000eda9  jns     short loc_18000EE1E
0x18000edab  mov     rcx, [rbp+188h]; this
0x18000edb2  mov     r9d, eax; char *
0x18000edb5  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000edbc  lea     edx, [rbx+72h]; void *
0x18000edbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000edc4  nop
0x18000edc5  mov     rcx, [rsp+280h+var_230]
0x18000edca  test    rcx, rcx
0x18000edcd  jz      short loc_18000EDE1
0x18000edcf  mov     [rsp+280h+var_230], rbx
0x18000edd4  mov     rax, [rcx]
0x18000edd7  mov     rax, [rax+10h]
0x18000eddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ede0  nop
0x18000ede1  mov     rcx, [rsp+280h+var_228]
0x18000ede6  test    rcx, rcx
0x18000ede9  jz      short loc_18000EDFD
0x18000edeb  mov     [rsp+280h+var_228], rbx
0x18000edf0  mov     rax, [rcx]
0x18000edf3  mov     rax, [rax+10h]
0x18000edf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edfc  nop
0x18000edfd  mov     rcx, [rsp+280h+var_220]
0x18000ee02  test    rcx, rcx
0x18000ee05  jz      short loc_18000EE19
0x18000ee07  mov     [rsp+280h+var_220], rbx
0x18000ee0c  mov     rax, [rcx]
0x18000ee0f  mov     rax, [rax+10h]
0x18000ee13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee18  nop
0x18000ee19  jmp     loc_18000F316
0x18000ee1e  mov     rax, [rdi]
0x18000ee21  mov     rbx, [rax+0B8h]
0x18000ee28  lea     rcx, [rsp+280h+var_228]
0x18000ee2d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000ee32  lea     rdx, [rsp+280h+var_228]
0x18000ee37  mov     rcx, rdi
0x18000ee3a  mov     rax, rbx
0x18000ee3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee42  mov     ebx, eax
0x18000ee44  test    eax, eax
0x18000ee46  jns     short loc_18000EE52
0x18000ee48  mov     edx, 73h ; 's'
0x18000ee4d  jmp     loc_18000F173
0x18000ee52  mov     rax, [rdi]
0x18000ee55  mov     rbx, [rax+50h]
0x18000ee59  lea     rcx, [rsp+280h+var_230]
0x18000ee5e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000ee63  lea     rdx, [rsp+280h+var_230]
0x18000ee68  mov     rcx, rdi
0x18000ee6b  mov     rax, rbx
0x18000ee6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee73  mov     esi, eax
0x18000ee75  xor     ebx, ebx
0x18000ee77  test    eax, eax
0x18000ee79  jns     short loc_18000EEEE
0x18000ee7b  mov     rcx, [rbp+188h]; this
0x18000ee82  mov     r9d, eax; char *
0x18000ee85  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000ee8c  lea     edx, [rbx+74h]; void *
0x18000ee8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee94  nop
0x18000ee95  mov     rcx, [rsp+280h+var_230]
0x18000ee9a  test    rcx, rcx
0x18000ee9d  jz      short loc_18000EEB1
0x18000ee9f  mov     [rsp+280h+var_230], rbx
0x18000eea4  mov     rax, [rcx]
0x18000eea7  mov     rax, [rax+10h]
0x18000eeab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeb0  nop
0x18000eeb1  mov     rcx, [rsp+280h+var_228]
0x18000eeb6  test    rcx, rcx
0x18000eeb9  jz      short loc_18000EECD
0x18000eebb  mov     [rsp+280h+var_228], rbx
0x18000eec0  mov     rax, [rcx]
0x18000eec3  mov     rax, [rax+10h]
0x18000eec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eecc  nop
0x18000eecd  mov     rcx, [rsp+280h+var_220]
0x18000eed2  test    rcx, rcx
0x18000eed5  jz      short loc_18000EEE9
0x18000eed7  mov     [rsp+280h+var_220], rbx
0x18000eedc  mov     rax, [rcx]
0x18000eedf  mov     rax, [rax+10h]
0x18000eee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eee8  nop
0x18000eee9  jmp     loc_18000F316
0x18000eeee  xorps   xmm0, xmm0
0x18000eef1  xor     eax, eax
0x18000eef3  movups  xmmword ptr [rbp+180h+var_1D8], xmm0
0x18000eef7  movups  xmmword ptr [rbp+180h+var_1C8], xmm0
0x18000eefb  movups  xmmword ptr [rbp+180h+var_1C8+0Ch], xmm0
0x18000eeff  movups  [rbp+180h+var_1F0], xmm0
0x18000ef03  mov     [rbp+180h+var_1E0], eax
0x18000ef06  lea     rdx, pszClassList; "Animations"
0x18000ef0d  xor     ecx, ecx; hwnd
0x18000ef0f  call    cs:__imp_OpenThemeData
0x18000ef15  mov     rdi, rax
0x18000ef18  mov     [rsp+280h+var_208], rax
0x18000ef1d  lea     rdx, aTimingfunction; "TimingFunction"
0x18000ef24  xor     ecx, ecx; hwnd
0x18000ef26  call    cs:__imp_OpenThemeData
0x18000ef2c  mov     rbx, rax
0x18000ef2f  mov     [rsp+280h+var_210], rax
0x18000ef34  test    rdi, rdi
0x18000ef37  jz      loc_18000F267
0x18000ef3d  test    rax, rax
0x18000ef40  jz      loc_18000F267
0x18000ef46  mov     [rsp+280h+var_218], 0
0x18000ef4e  lea     rax, [rsp+280h+var_218]
0x18000ef53  mov     [rsp+280h+var_250], rax
0x18000ef58  mov     dword ptr [rsp+280h+var_258], 2Ch ; ','
0x18000ef60  lea     rax, [rbp+180h+var_1D8]
0x18000ef64  mov     qword ptr [rsp+280h+var_260], rax; int
0x18000ef69  xor     r9d, r9d
0x18000ef6c  lea     r8d, [r9+1]
0x18000ef70  mov     edx, r13d
0x18000ef73  mov     rcx, rdi
0x18000ef76  call    cs:__imp_GetThemeAnimationTransform
0x18000ef7c  mov     esi, eax
0x18000ef7e  xor     r13d, r13d
0x18000ef81  test    eax, eax
0x18000ef83  jns     short loc_18000EFB8
0x18000ef85  mov     rcx, [rbp+188h]; this
0x18000ef8c  mov     r9d, eax; char *
0x18000ef8f  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000ef96  lea     edx, [r13+20h]; void *
0x18000ef9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef9f  lea     rcx, [rsp+280h+var_210]
0x18000efa4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?CloseThemeData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000efa9  lea     rcx, [rsp+280h+var_208]
0x18000efae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?CloseThemeData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&CloseThemeData(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000efb3  jmp     loc_18000F2A6
0x18000efb8  lea     rax, [rsp+280h+var_218]
0x18000efbd  mov     qword ptr [rsp+280h+var_260], rax; int
0x18000efc2  mov     r9d, 14h
0x18000efc8  lea     r8, [rbp+180h+var_1F0]
0x18000efcc  mov     edx, [rbp+180h+var_1D8+4]
0x18000efcf  mov     rcx, rbx
0x18000efd2  call    cs:__imp_GetThemeTimingFunction
0x18000efd8  mov     esi, eax
0x18000efda  test    eax, eax
0x18000efdc  jns     short loc_18000EFF9
0x18000efde  mov     rcx, [rbp+188h]; this
0x18000efe5  mov     r9d, eax; char *
0x18000efe8  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000efef  mov     edx, 24h ; '$'; void *
0x18000eff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eff9  mov     rcx, rbx; hTheme
0x18000effc  call    cs:__imp_CloseThemeData
0x18000f002  mov     rcx, rdi; hTheme
0x18000f005  call    cs:__imp_CloseThemeData
0x18000f00b  test    esi, esi
0x18000f00d  js      loc_18000F2A6
0x18000f013  mov     rcx, [rsp+280h+var_220]; this
0x18000f018  movss   xmm4, [rbp+180h+var_1E0]
0x18000f01d  cvtps2pd xmm4, xmm4
0x18000f020  movss   xmm5, dword ptr [rbp+180h+var_1F0+0Ch]
0x18000f025  cvtps2pd xmm5, xmm5
0x18000f028  movss   xmm6, dword ptr [rbp+180h+var_1F0+8]
0x18000f02d  cvtps2pd xmm6, xmm6
0x18000f030  movss   xmm3, dword ptr [rbp+180h+var_1F0+4]
0x18000f035  cvtps2pd xmm3, xmm3; double
0x18000f038  movd    xmm2, dword ptr [r12]
0x18000f03e  cvtdq2pd xmm2, xmm2; double
0x18000f042  movd    xmm1, dword ptr [r15]
0x18000f047  cvtdq2pd xmm1, xmm1; double
0x18000f04b  mov     eax, [rbp+180h+var_1D8+0Ch]
0x18000f04e  xorps   xmm0, xmm0
0x18000f051  cvtsi2sd xmm0, rax
0x18000f056  divsd   xmm0, cs:__real@408f400000000000
0x18000f05e  mov     [rsp+280h+var_240], rcx; unsigned __int16 *
0x18000f063  mov     [rsp+280h+var_248], r14; unsigned __int16 *
0x18000f068  movsd   [rsp+280h+var_250], xmm4; double
0x18000f06e  movsd   [rsp+280h+var_258], xmm5; double
0x18000f074  movsd   qword ptr [rsp+280h+var_260], xmm6; int
0x18000f07a  call    ?PopulateCubicBezierAnimationFromWAM@AnimationHelpers@@YAJNNNNNNNPEBGPEAUIDCompositionAnimation@@@Z; AnimationHelpers::PopulateCubicBezierAnimationFromWAM(double,double,double,double,double,double,double,ushort const *,IDCompositionAnimation *)
0x18000f07f  mov     esi, eax
0x18000f081  test    eax, eax
0x18000f083  jns     short loc_18000F0FA
0x18000f085  mov     rcx, [rbp+188h]; this
0x18000f08c  mov     r9d, eax; char *
0x18000f08f  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000f096  mov     edx, 8Fh; void *
0x18000f09b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f0a0  nop
0x18000f0a1  mov     rcx, [rsp+280h+var_230]
0x18000f0a6  test    rcx, rcx
0x18000f0a9  jz      short loc_18000F0BD
0x18000f0ab  mov     [rsp+280h+var_230], r13
0x18000f0b0  mov     rax, [rcx]
0x18000f0b3  mov     rax, [rax+10h]
0x18000f0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0bc  nop
0x18000f0bd  mov     rcx, [rsp+280h+var_228]
0x18000f0c2  test    rcx, rcx
0x18000f0c5  jz      short loc_18000F0D9
0x18000f0c7  mov     [rsp+280h+var_228], r13
0x18000f0cc  mov     rax, [rcx]
0x18000f0cf  mov     rax, [rax+10h]
0x18000f0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0d8  nop
0x18000f0d9  mov     rcx, [rsp+280h+var_220]
0x18000f0de  test    rcx, rcx
0x18000f0e1  jz      short loc_18000F0F5
0x18000f0e3  mov     [rsp+280h+var_220], r13
0x18000f0e8  mov     rax, [rcx]
0x18000f0eb  mov     rax, [rax+10h]
0x18000f0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0f4  nop
0x18000f0f5  jmp     loc_18000F316
0x18000f0fa  mov     rcx, [rsp+280h+var_228]; this
0x18000f0ff  movss   xmm4, [rbp+180h+var_1E0]
0x18000f104  cvtps2pd xmm4, xmm4
0x18000f107  movss   xmm5, dword ptr [rbp+180h+var_1F0+0Ch]
0x18000f10c  cvtps2pd xmm5, xmm5
0x18000f10f  movss   xmm6, dword ptr [rbp+180h+var_1F0+8]
0x18000f114  cvtps2pd xmm6, xmm6
0x18000f117  movss   xmm3, dword ptr [rbp+180h+var_1F0+4]
0x18000f11c  cvtps2pd xmm3, xmm3; double
0x18000f11f  movd    xmm2, dword ptr [r12+4]
0x18000f126  cvtdq2pd xmm2, xmm2; double
0x18000f12a  movd    xmm1, dword ptr [r15+4]
0x18000f130  cvtdq2pd xmm1, xmm1; double
0x18000f134  mov     eax, [rbp+180h+var_1D8+0Ch]
0x18000f137  xorps   xmm0, xmm0
0x18000f13a  cvtsi2sd xmm0, rax
0x18000f13f  divsd   xmm0, cs:__real@408f400000000000
0x18000f147  mov     [rsp+280h+var_240], rcx; unsigned __int16 *
0x18000f14c  mov     [rsp+280h+var_248], r14; unsigned __int16 *
0x18000f151  movsd   [rsp+280h+var_250], xmm4; double
0x18000f157  movsd   [rsp+280h+var_258], xmm5; double
0x18000f15d  movsd   qword ptr [rsp+280h+var_260], xmm6; int
0x18000f163  call    ?PopulateCubicBezierAnimationFromWAM@AnimationHelpers@@YAJNNNNNNNPEBGPEAUIDCompositionAnimation@@@Z; AnimationHelpers::PopulateCubicBezierAnimationFromWAM(double,double,double,double,double,double,double,ushort const *,IDCompositionAnimation *)
0x18000f168  mov     ebx, eax
0x18000f16a  test    eax, eax
0x18000f16c  jns     short loc_18000F1BB
0x18000f16e  mov     edx, 9Ah; void *
0x18000f173  mov     r9d, eax; char *
0x18000f176  lea     r8, aPcshellShellAp_11; "pcshell\\shell\\applicationframe\\frame"...
0x18000f17d  mov     rcx, [rbp+188h]; this
0x18000f184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f189  nop
0x18000f18a  lea     rcx, [rsp+280h+var_230]
0x18000f18f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000f194  nop
0x18000f195  lea     rcx, [rsp+280h+var_228]
0x18000f19a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
  ... truncated ...
```
