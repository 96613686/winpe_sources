# SplashScreen::CSplashScreenDCompVisual::BeginLoadVisual(std::function<void (void)>,_GUID const &,void * *,ID2D1Bitmap1 *)

- ea: `0x180005f5c`
- end: `0x180006359`
- name: `?BeginLoadVisual@CSplashScreenDCompVisual@SplashScreen@@QEAAXV?$function@$$A6AXXZ@std@@AEBU_GUID@@PEAPEAXPEAUID2D1Bitmap1@@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800040cc`

## callees

- `0x180003e30`
- `0x180004698`
- `0x1800046c4`
- `0x180004c98`
- `0x180004e8c`
- `0x180005f5c`
- `0x180006c3c`
- `0x180007b00`
- `0x180014ec4`
- `0x18003f458`
- `0x180040b98`
- `0x180040ef4`
- `0x180043c30`
- `0x18004bb84`
- `0x18006eac8`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800062c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800062c1`

## string_xrefs

- `0x180005fd5`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`
- `0x180006018`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`
- `0x180006049`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`
- `0x18000608d`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`
- `0x1800060c8`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`
- `0x18000619a`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`
- `0x1800061c2`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`
- `0x1800062a7`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SplashScreen::CSplashScreenDCompVisual::BeginLoadVisual(
        SplashScreen::CSplashScreenDCompVisual *this,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5)
{
  unsigned int v8; // eax
  __int64 v9; // rdx
  int SinglePixelSurfaceFrom; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 *v20; // r14
  __int64 v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // ebx
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v37; // [rsp+20h] [rbp-81h]
  __int64 v38; // [rsp+30h] [rbp-71h] BYREF
  __int64 v39; // [rsp+38h] [rbp-69h] BYREF
  __int64 v40; // [rsp+40h] [rbp-61h] BYREF
  _QWORD v41[3]; // [rsp+48h] [rbp-59h] BYREF
  _BYTE v42[80]; // [rsp+60h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v41[2] = a2;
  *a4 = 0;
  v41[0] = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(v41);
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 16LL))(*((_QWORD *)this + 11));
  SinglePixelSurfaceFrom = DCompUtil::CreateSinglePixelSurfaceFromColor<IDCompositionDevice>(
                             *((_QWORD *)this + 6),
                             v9,
                             v8,
                             v41);
  if ( SinglePixelSurfaceFrom < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
      (const char *)(unsigned int)SinglePixelSurfaceFrom,
      v37);
  v39 = 0;
  v11 = *((_QWORD *)this + 6);
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 56LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v39);
  v13 = v12(v11, &v39);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
      (const char *)(unsigned int)v13,
      v37);
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 120LL))(v39, v41[0]);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
      (const char *)(unsigned int)v14,
      v37);
  v40 = 0;
  v15 = *((_QWORD *)this + 6);
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 56LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v40);
  v17 = v16(v15, &v40);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
      (const char *)(unsigned int)v17,
      v37);
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v40 + 128LL))(v40, v39, 1);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
      (const char *)(unsigned int)v18,
      v37);
  LOBYTE(v19) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::GetImpl'::`2'::impl,
    v19);
  v20 = (__int64 *)((char *)this + 56);
  AcquireSRWLockExclusive((PSRWLOCK)this + 20);
  v41[1] = (char *)this + 160;
  if ( a5 )
  {
    v29 = v40;
    if ( *v20 != v40 )
    {
      v38 = v40;
      Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v38);
      v38 = *v20;
      *v20 = v29;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v38);
    }
    v30 = v39;
    if ( *((_QWORD *)this + 8) != v39 )
    {
      v38 = v39;
      Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v38);
      v38 = *((_QWORD *)this + 8);
      *((_QWORD *)this + 8) = v30;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v38);
    }
    SplashScreen::CSplashScreenDCompVisual::ReconcileVisual(this);
    Microsoft::WRL::ComPtr<ID2D1Bitmap1>::operator=((char *)this + 80, a5);
    *((_DWORD *)this + 36) = (int)*(float *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a5 + 32LL))(
                                              a5,
                                              &v38);
    *((_DWORD *)this + 37) = (int)*(float *)((*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a5 + 32LL))(
                                               a5,
                                               &v38)
                                           + 4);
    v32 = Microsoft::WRL::ComPtr<IDCompositionVisual>::CopyTo((char *)this + 56, v31, a4);
    if ( v32 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
        (const char *)(unsigned int)v32,
        v37);
    if ( this != (SplashScreen::CSplashScreenDCompVisual *)-160LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 20);
    std::_Func_class<void,>::operator()(a2);
  }
  else
  {
    v21 = v40;
    if ( *v20 != v40 )
    {
      v38 = v40;
      Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v38);
      v38 = *v20;
      *v20 = v21;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v38);
    }
    v22 = v39;
    if ( *((_QWORD *)this + 8) != v39 )
    {
      v38 = v39;
      Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v38);
      v38 = *((_QWORD *)this + 8);
      *((_QWORD *)this + 8) = v22;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v38);
    }
    SplashScreen::CSplashScreenDCompVisual::ReconcileVisual(this);
    v23 = lambda_da2275e54fc1f0666cf165c961738c3f_::_lambda_da2275e54fc1f0666cf165c961738c3f_(v42, a2, this);
    v26 = Windows::Internal::ComTaskPool::QueueTask__lambda_da2275e54fc1f0666cf165c961738c3f___(
            v25,
            v24,
            *((unsigned int *)this + 38),
            v23);
    std::_Func_class<void,>::_Tidy(v42);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
        (const char *)(unsigned int)v26,
        v37);
    v28 = Microsoft::WRL::ComPtr<IDCompositionVisual>::CopyTo((char *)this + 56, v27, a4);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
        (const char *)(unsigned int)v28,
        v37);
    if ( this != (SplashScreen::CSplashScreenDCompVisual *)-160LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 20);
  }
  v33 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v41[0];
  if ( v41[0] )
  {
    v41[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  return std::_Func_class<void,>::_Tidy(a2);
}

```

## disassembly

```asm
0x180005f5c  mov     [rsp-8+arg_10], rbx
0x180005f61  push    rbp
0x180005f62  push    rsi
0x180005f63  push    rdi
0x180005f64  push    r12
0x180005f66  push    r13
0x180005f68  push    r14
0x180005f6a  push    r15
0x180005f6c  lea     rbp, [rsp-1Fh]
0x180005f71  sub     rsp, 0C0h
0x180005f78  mov     rax, cs:__security_cookie
0x180005f7f  xor     rax, rsp
0x180005f82  mov     [rbp+4Fh+var_40], rax
0x180005f86  mov     r13, r9
0x180005f89  mov     r15, rdx
0x180005f8c  mov     rsi, rcx
0x180005f8f  mov     [rbp+4Fh+var_98], rdx
0x180005f93  mov     r12, [rbp+4Fh+arg_20]
0x180005f97  xor     r14d, r14d
0x180005f9a  mov     [r9], r14
0x180005f9d  mov     [rbp+4Fh+var_A8], r14
0x180005fa1  lea     rcx, [rbp+4Fh+var_A8]
0x180005fa5  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180005faa  mov     rcx, [rsi+58h]
0x180005fae  mov     rax, [rcx]
0x180005fb1  mov     rax, [rax+10h]
0x180005fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fba  lea     r9, [rbp+4Fh+var_A8]
0x180005fbe  mov     r8d, eax
0x180005fc1  mov     rcx, [rsi+30h]
0x180005fc5  call    ??$CreateSinglePixelSurfaceFromColor@UIDCompositionDevice@@@DCompUtil@@YAJPEAUIDCompositionDevice@@W4DXGI_ALPHA_MODE@@KPEAPEAUIDCompositionSurface@@@Z; DCompUtil::CreateSinglePixelSurfaceFromColor<IDCompositionDevice>(IDCompositionDevice *,DXGI_ALPHA_MODE,ulong,IDCompositionSurface * *)
0x180005fca  mov     rcx, [rbp+57h]; this
0x180005fce  test    eax, eax
0x180005fd0  jns     short loc_180005FE6
0x180005fd2  mov     r9d, eax; char *
0x180005fd5  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x180005fdc  lea     edx, [r14+48h]; void *
0x180005fe0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005fe6  mov     [rbp+4Fh+var_B8], r14
0x180005fea  mov     rdi, [rsi+30h]
0x180005fee  mov     rax, [rdi]
0x180005ff1  mov     rbx, [rax+38h]
0x180005ff5  lea     rcx, [rbp+4Fh+var_B8]
0x180005ff9  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180005ffe  lea     rdx, [rbp+4Fh+var_B8]
0x180006002  mov     rcx, rdi
0x180006005  mov     rax, rbx
0x180006008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600d  mov     rcx, [rbp+57h]; this
0x180006011  test    eax, eax
0x180006013  jns     short loc_18000602A
0x180006015  mov     r9d, eax; char *
0x180006018  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x18000601f  mov     edx, 4Ch ; 'L'; void *
0x180006024  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000602a  mov     rcx, [rbp+4Fh+var_B8]
0x18000602e  mov     rax, [rcx]
0x180006031  mov     rdx, [rbp+4Fh+var_A8]
0x180006035  mov     rax, [rax+78h]
0x180006039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000603e  mov     rcx, [rbp+57h]; this
0x180006042  test    eax, eax
0x180006044  jns     short loc_18000605B
0x180006046  mov     r9d, eax; char *
0x180006049  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x180006050  mov     edx, 4Dh ; 'M'; void *
0x180006055  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000605b  mov     [rbp+4Fh+var_B0], r14
0x18000605f  mov     rdi, [rsi+30h]
0x180006063  mov     rax, [rdi]
0x180006066  mov     rbx, [rax+38h]
0x18000606a  lea     rcx, [rbp+4Fh+var_B0]
0x18000606e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006073  lea     rdx, [rbp+4Fh+var_B0]
0x180006077  mov     rcx, rdi
0x18000607a  mov     rax, rbx
0x18000607d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006082  mov     rcx, [rbp+57h]; this
0x180006086  test    eax, eax
0x180006088  jns     short loc_18000609F
0x18000608a  mov     r9d, eax; char *
0x18000608d  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x180006094  mov     edx, 51h ; 'Q'; void *
0x180006099  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000609f  mov     rcx, [rbp+4Fh+var_B0]
0x1800060a3  mov     rax, [rcx]
0x1800060a6  xor     r9d, r9d
0x1800060a9  lea     r8d, [r9+1]
0x1800060ad  mov     rdx, [rbp+4Fh+var_B8]
0x1800060b1  mov     rax, [rax+80h]
0x1800060b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060bd  mov     rcx, [rbp+57h]; this
0x1800060c1  test    eax, eax
0x1800060c3  jns     short loc_1800060DA
0x1800060c5  mov     r9d, eax; char *
0x1800060c8  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x1800060cf  mov     edx, 54h ; 'T'; void *
0x1800060d4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800060da  mov     dl, 1
0x1800060dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens> `wil::Feature<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::GetImpl(void)'::`2'::impl
0x1800060e3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeAwareSplashScreens@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeAwareSplashScreens>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800060e8  lea     rdi, [rsi+0A0h]
0x1800060ef  lea     r14, [rsi+38h]
0x1800060f3  mov     rcx, rdi; SRWLock
0x1800060f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800060fc  mov     [rbp+4Fh+var_A0], rdi
0x180006100  test    r12, r12
0x180006103  jnz     loc_1800061EB
0x180006109  mov     rbx, [rbp+4Fh+var_B0]
0x18000610d  cmp     [r14], rbx
0x180006110  jz      short loc_180006132
0x180006112  mov     [rbp+4Fh+var_C0], rbx
0x180006116  lea     rcx, [rbp+4Fh+var_C0]
0x18000611a  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x18000611f  mov     rax, [r14]
0x180006122  mov     [rbp+4Fh+var_C0], rax
0x180006126  mov     [r14], rbx
0x180006129  lea     rcx, [rbp+4Fh+var_C0]
0x18000612d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006132  mov     rbx, [rbp+4Fh+var_B8]
0x180006136  cmp     [rsi+40h], rbx
0x18000613a  jz      short loc_18000615E
0x18000613c  mov     [rbp+4Fh+var_C0], rbx
0x180006140  lea     rcx, [rbp+4Fh+var_C0]
0x180006144  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x180006149  mov     rax, [rsi+40h]
0x18000614d  mov     [rbp+4Fh+var_C0], rax
0x180006151  mov     [rsi+40h], rbx
0x180006155  lea     rcx, [rbp+4Fh+var_C0]
0x180006159  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18000615e  mov     rcx, rsi; this
0x180006161  call    ?ReconcileVisual@CSplashScreenDCompVisual@SplashScreen@@AEAAXXZ; SplashScreen::CSplashScreenDCompVisual::ReconcileVisual(void)
0x180006166  mov     r8, rsi
0x180006169  mov     rdx, r15
0x18000616c  lea     rcx, [rbp+4Fh+var_90]
0x180006170  call    _lambda_da2275e54fc1f0666cf165c961738c3f____lambda_da2275e54fc1f0666cf165c961738c3f_
0x180006175  mov     r9, rax
0x180006178  mov     r8d, [rsi+98h]
0x18000617f  call    Windows__Internal__ComTaskPool__QueueTask__lambda_da2275e54fc1f0666cf165c961738c3f___
0x180006184  mov     ebx, eax
0x180006186  lea     rcx, [rbp+4Fh+var_90]
0x18000618a  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18000618f  mov     rcx, [rbp+57h]; this
0x180006193  test    ebx, ebx
0x180006195  jns     short loc_1800061AC
0x180006197  mov     r9d, ebx; char *
0x18000619a  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x1800061a1  mov     edx, 69h ; 'i'; void *
0x1800061a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800061ac  mov     r8, r13
0x1800061af  mov     rcx, r14
0x1800061b2  call    ?CopyTo@?$ComPtr@UIDCompositionVisual@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IDCompositionVisual>::CopyTo(_GUID const &,void * *)
0x1800061b7  mov     rcx, [rbp+57h]; this
0x1800061bb  test    eax, eax
0x1800061bd  jns     short loc_1800061D4
0x1800061bf  mov     r9d, eax; char *
0x1800061c2  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x1800061c9  mov     edx, 6Bh ; 'k'; void *
0x1800061ce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800061d4  test    rdi, rdi
0x1800061d7  jz      loc_1800062D0
0x1800061dd  mov     rcx, rdi; SRWLock
0x1800061e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800061e6  jmp     loc_1800062D0
0x1800061eb  mov     rbx, [rbp+4Fh+var_B0]
0x1800061ef  cmp     [r14], rbx
0x1800061f2  jz      short loc_180006214
0x1800061f4  mov     [rbp+4Fh+var_C0], rbx
0x1800061f8  lea     rcx, [rbp+4Fh+var_C0]
0x1800061fc  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x180006201  mov     rax, [r14]
0x180006204  mov     [rbp+4Fh+var_C0], rax
0x180006208  mov     [r14], rbx
0x18000620b  lea     rcx, [rbp+4Fh+var_C0]
0x18000620f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006214  mov     rbx, [rbp+4Fh+var_B8]
0x180006218  cmp     [rsi+40h], rbx
0x18000621c  jz      short loc_180006240
0x18000621e  mov     [rbp+4Fh+var_C0], rbx
0x180006222  lea     rcx, [rbp+4Fh+var_C0]
0x180006226  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x18000622b  mov     rax, [rsi+40h]
0x18000622f  mov     [rbp+4Fh+var_C0], rax
0x180006233  mov     [rsi+40h], rbx
0x180006237  lea     rcx, [rbp+4Fh+var_C0]
0x18000623b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180006240  mov     rcx, rsi; this
0x180006243  call    ?ReconcileVisual@CSplashScreenDCompVisual@SplashScreen@@AEAAXXZ; SplashScreen::CSplashScreenDCompVisual::ReconcileVisual(void)
0x180006248  lea     rcx, [rsi+50h]
0x18000624c  mov     rdx, r12
0x18000624f  call    ??4?$ComPtr@UID2D1Bitmap1@@@WRL@Microsoft@@QEAAAEAV012@PEAUID2D1Bitmap1@@@Z; Microsoft::WRL::ComPtr<ID2D1Bitmap1>::operator=(ID2D1Bitmap1 *)
0x180006254  mov     rax, [r12]
0x180006258  lea     rdx, [rbp+4Fh+var_C0]
0x18000625c  mov     rcx, r12
0x18000625f  mov     rax, [rax+20h]
0x180006263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006268  cvttss2si ecx, dword ptr [rax]
0x18000626c  mov     [rsi+90h], ecx
0x180006272  mov     rax, [r12]
0x180006276  lea     rdx, [rbp+4Fh+var_C0]
0x18000627a  mov     rcx, r12
0x18000627d  mov     rax, [rax+20h]
0x180006281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006286  cvttss2si ecx, dword ptr [rax+4]
0x18000628b  mov     [rsi+94h], ecx
0x180006291  mov     r8, r13
0x180006294  mov     rcx, r14
0x180006297  call    ?CopyTo@?$ComPtr@UIDCompositionVisual@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IDCompositionVisual>::CopyTo(_GUID const &,void * *)
0x18000629c  mov     rcx, [rbp+57h]; this
0x1800062a0  test    eax, eax
0x1800062a2  jns     short loc_1800062B9
0x1800062a4  mov     r9d, eax; char *
0x1800062a7  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x1800062ae  mov     edx, 7Ch ; '|'; void *
0x1800062b3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800062b9  test    rdi, rdi
0x1800062bc  jz      short loc_1800062C7
0x1800062be  mov     rcx, rdi; SRWLock
0x1800062c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800062c7  mov     rcx, r15
0x1800062ca  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1800062cf  nop
0x1800062d0  mov     rcx, [rbp+4Fh+var_B0]
0x1800062d4  test    rcx, rcx
0x1800062d7  jz      short loc_1800062EE
0x1800062d9  mov     [rbp+4Fh+var_B0], 0
0x1800062e1  mov     rax, [rcx]
0x1800062e4  mov     rax, [rax+10h]
0x1800062e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ed  nop
0x1800062ee  mov     rcx, [rbp+4Fh+var_B8]
0x1800062f2  test    rcx, rcx
0x1800062f5  jz      short loc_18000630C
0x1800062f7  mov     [rbp+4Fh+var_B8], 0
0x1800062ff  mov     rax, [rcx]
0x180006302  mov     rax, [rax+10h]
0x180006306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000630b  nop
0x18000630c  mov     rcx, [rbp+4Fh+var_A8]
0x180006310  test    rcx, rcx
0x180006313  jz      short loc_18000632A
0x180006315  mov     [rbp+4Fh+var_A8], 0
0x18000631d  mov     rax, [rcx]
0x180006320  mov     rax, [rax+10h]
0x180006324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006329  nop
0x18000632a  mov     rcx, r15
0x18000632d  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180006332  mov     rcx, [rbp+4Fh+var_40]
0x180006336  xor     rcx, rsp; StackCookie
0x180006339  call    __security_check_cookie
0x18000633e  mov     rbx, [rsp+0F0h+arg_10]
0x180006346  add     rsp, 0C0h
0x18000634d  pop     r15
0x18000634f  pop     r14
0x180006351  pop     r13
0x180006353  pop     r12
0x180006355  pop     rdi
0x180006356  pop     rsi
0x180006357  pop     rbp
0x180006358  retn
```
