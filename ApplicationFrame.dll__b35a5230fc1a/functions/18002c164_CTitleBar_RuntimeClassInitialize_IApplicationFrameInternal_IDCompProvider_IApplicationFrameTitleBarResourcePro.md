# CTitleBar::RuntimeClassInitialize(IApplicationFrameInternal *,IDCompProvider *,IApplicationFrameTitleBarResourceProviderInternal *,DEVICE_SCALE_FACTOR,double,bool)

- ea: `0x18002c164`
- end: `0x18002c60f`
- name: `?RuntimeClassInitialize@CTitleBar@@QEAAJPEAUIApplicationFrameInternal@@PEAUIDCompProvider@@PEAUIApplicationFrameTitleBarResourceProviderInternal@@W4DEVICE_SCALE_FACTOR@@N_N@Z`
- size: `1195`
- prototype: `__int64 __usercall@<rax>(CTitleBar *__hidden this@<rcx>, struct IApplicationFrameInternal *@<rdx>, struct IDCompProvider *@<r8>, struct IApplicationFrameTitleBarResourceProviderInternal *@<r9>, enum DEVICE_SCALE_FACTOR, double, bool)`
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000e46c`

## callees

- `0x180003e30`
- `0x180004c98`
- `0x180008d90`
- `0x18000b080`
- `0x18000caf0`
- `0x180011bb4`
- `0x180014610`
- `0x18001586c`
- `0x180017870`
- `0x180018cf0`
- `0x18001b644`
- `0x18001da14`
- `0x18001de14`
- `0x180020cb4`
- `0x180023c60`
- `0x180024020`
- `0x180024f98`
- `0x18002c164`
- `0x18002c7f0`
- `0x18002d560`
- `0x1800329e0`
- `0x180033f34`
- `0x1800345ac`
- `0x1800350f0`
- `0x1800363c8`
- `0x180037230`
- `0x180037a40`
- `0x180040270`
- `0x180043c30`
- `0x18005be70`
- `0x180072010`

## import_xrefs

- `SHCORE!SHTaskPoolGetUniqueContext` at `0x18002c1fc`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x18002c208`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x18002c1fc`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x18002c208`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002c3d6`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002c3d6`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18002c2cb`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18002c2cb`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18002c405`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18002c405`

## pseudocode

```c
__int64 __fastcall CTitleBar::RuntimeClassInitialize(
        CTitleBar *this,
        struct IApplicationFrameInternal *a2,
        struct IDCompProvider *a3,
        struct IApplicationFrameTitleBarResourceProviderInternal *a4,
        enum DEVICE_SCALE_FACTOR a5,
        double a6,
        bool a7)
{
  int Instance; // ebx
  __int64 v12; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  HWND *v16; // rsi
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  const struct _GUID *v19; // rdx
  HWND v20; // rcx
  CTitleBar *v21; // rcx
  char v22; // al
  bool v23; // zf
  int v24; // esi
  bool v25; // r15
  __int64 v26; // rax
  _QWORD *v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  _QWORD *v31; // rbx
  char IsEnabled; // al
  __int64 v33; // r8
  __int64 v34; // rdx
  int v35; // [rsp+20h] [rbp-60h]
  __int64 cy; // [rsp+28h] [rbp-58h]
  int v37; // [rsp+40h] [rbp-40h] BYREF
  char *v38; // [rsp+48h] [rbp-38h] BYREF
  int v39; // [rsp+50h] [rbp-30h] BYREF
  struct IApplicationFrameTitleBarResourceProviderInternal *v40; // [rsp+58h] [rbp-28h] BYREF
  CTitleBar *v41; // [rsp+60h] [rbp-20h] BYREF
  struct tagRECT Rect; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *((_BYTE *)this + 558) = a7;
  *((_BYTE *)this + 573) = TabletModeHelpers::IsTabletMode(this);
  Instance = Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>((char *)this + 416);
  if ( Instance < 0 )
  {
    v12 = 183;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)(unsigned int)Instance,
      v35);
    return (unsigned int)Instance;
  }
  Instance = (*(__int64 (__fastcall **)(struct IDCompProvider *, char *))(*(_QWORD *)a3 + 72LL))(a3, (char *)this + 440);
  if ( Instance < 0 )
  {
    v12 = 185;
    goto LABEL_3;
  }
  *((_DWORD *)this + 374) = SHTaskPoolGetUniqueContext();
  *((_DWORD *)this + 376) = SHTaskPoolGetUniqueContext();
  v38 = (char *)this + 104;
  v14 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v38);
  Instance = Microsoft::WRL::AsWeak<IApplicationFrameInternal>(a2, v14);
  if ( Instance < 0 )
  {
    v12 = 190;
    goto LABEL_3;
  }
  v38 = (char *)this + 112;
  v15 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v38);
  Instance = Microsoft::WRL::AsWeak<IDCompProvider>(a3, v15);
  if ( Instance < 0 )
  {
    v12 = 191;
    goto LABEL_3;
  }
  if ( *((struct IApplicationFrameTitleBarResourceProviderInternal **)this + 45) != a4 )
  {
    v40 = a4;
    Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v40);
    v40 = (struct IApplicationFrameTitleBarResourceProviderInternal *)*((_QWORD *)this + 45);
    *((_QWORD *)this + 45) = a4;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v40);
  }
  *((double *)this + 67) = a6;
  CTitleBar::_SetScaleFactors(this, a5);
  v16 = (HWND *)((char *)this + 504);
  (*(void (__fastcall **)(struct IDCompProvider *, char *))(*(_QWORD *)a3 + 48LL))(a3, (char *)this + 504);
  *((_BYTE *)this + 562) = GetForegroundWindow() == *((HWND *)this + 63);
  CTitleBar::UpdateBorderVisibilityAndMargins(this);
  CTitleBar::_UpdateCurrentRestoreGlyph(this);
  CTitleBar::_GetDefaultColors(this, (CTitleBar *)((char *)this + 636), 0);
  *((_DWORD *)this + 187) = 0xFFFFFF;
  *((_DWORD *)this + 188) = 0xFFFFFF;
  *((_DWORD *)this + 189) = 0xFFFFFF;
  *((_DWORD *)this + 190) = 0xFFFFFF;
  *((_DWORD *)this + 191) = 0xFFFFFF;
  *((_DWORD *)this + 193) = 0xFFFFFF;
  *((_DWORD *)this + 194) = 0xFFFFFF;
  *((_DWORD *)this + 196) = 0xFFFFFF;
  v17 = *(_OWORD *)((char *)this + 748);
  *((_DWORD *)this + 183) = 0xFFFFFF;
  v18 = *(_OWORD *)((char *)this + 764);
  *((_DWORD *)this + 184) = 0xFFFFFF;
  *(_OWORD *)((char *)this + 788) = v17;
  *((_DWORD *)this + 185) = 0xFFFFFF;
  *(_QWORD *)&v17 = *(_QWORD *)((char *)this + 780);
  *(_OWORD *)((char *)this + 804) = v18;
  *((_DWORD *)this + 186) = 0xFFFFFF;
  *(_QWORD *)((char *)this + 820) = v17;
  CTitleBar::_UpdateColorsFromApplicationViewAsync(this, 0);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 408);
  Instance = CActionsContextMenuProvider_CreateInstance(
               (enum DEVICE_SCALE_FACTOR)*((_DWORD *)this + 132),
               v19,
               (void **)this + 51);
  if ( Instance < 0 )
  {
    v12 = 210;
    goto LABEL_3;
  }
  Instance = CTitleBar::_InitializeDCompVariables(this);
  if ( Instance < 0 )
  {
    v12 = 212;
    goto LABEL_3;
  }
  v20 = *v16;
  Rect = 0;
  GetWindowRect(v20, &Rect);
  SetWindowPos(*v16, 0, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x30u);
  *((_BYTE *)this + 559) = (unsigned int)Mirror_IsThreadRTL() != 0;
  CTitleBar::_UpdateRtlWindowProp(this);
  CTitleBar::_RegisterTitleBarWindowClass(v21);
  Instance = CTitleBar::_CreateTitleBarWindow(this);
  if ( Instance < 0 )
  {
    v12 = 224;
    goto LABEL_3;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetImpl'::`2'::impl);
  CTitleBar::_UpdateMicaBackdrop(this);
  v39 = 831;
  v37 = 0;
  Instance = CTitleBar::GetVisibleButtons((CTitleBar *)((char *)this + 56), (enum TITLE_BAR_BUTTONS *)&v37);
  if ( Instance < 0 )
  {
    v12 = 234;
    goto LABEL_3;
  }
  v22 = *((_BYTE *)this + 561);
  v23 = (v37 & 0xC0) == 0;
  v24 = v37 & 0xC0;
  v37 = 14;
  v41 = this;
  v25 = !v23;
  LODWORD(v40) = 2 - (v22 != 0);
  v26 = Microsoft::WRL::Details::Make<CTitleBarAcc,CTitleBar *,HWND__ * &,enum TitleBarAccFlags,enum TitleBarPart,enum TITLE_BAR_BUTTONS &>(
          (unsigned int)&v38,
          (unsigned int)&v41,
          (int)this + 8,
          (unsigned int)&v40,
          (__int64)&v37,
          (__int64)&v39);
  v27 = (_QWORD *)((char *)this + 392);
  Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccInternal>::operator=<CTitleBarAcc>((char *)this + 392, v26);
  if ( v38 )
  {
    v38 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::Release();
  }
  if ( !*v27 )
  {
    Instance = -2147024882;
    v12 = 242;
    goto LABEL_3;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl'::`2'::impl) )
    LOBYTE(v29) = *((_BYTE *)this + 572) == 0;
  else
    LOBYTE(v29) = 1;
  LOBYTE(v28) = v24 == 0;
  (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v27 + 80LL))(*v27, v28, v29);
  LODWORD(v40) = 13;
  v39 = 1;
  v41 = this;
  v30 = Microsoft::WRL::Details::Make<CTitleBarAcc,CTitleBar *,HWND__ * &,enum TitleBarAccFlags,enum TitleBarPart,enum TITLE_BAR_BUTTONS const &>(
          (unsigned int)&v38,
          (unsigned int)&v41,
          (int)this + 520,
          (unsigned int)&v39,
          (__int64)&v40,
          cy);
  v31 = (_QWORD *)((char *)this + 400);
  Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccInternal>::operator=<CTitleBarAcc>((char *)this + 400, v30);
  if ( v38 )
  {
    v38 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::Release();
  }
  if ( !*v31 )
  {
    Instance = -2147024882;
    v12 = 257;
    goto LABEL_3;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl'::`2'::impl);
  LOBYTE(v34) = v25;
  if ( IsEnabled )
    LOBYTE(v33) = *((_BYTE *)this + 572) == 0;
  else
    LOBYTE(v33) = 1;
  (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v31 + 80LL))(*v31, v34, v33);
  CTitleBar::OnTitleBarHitTestVisualUpdated((CTitleBar *)((char *)this + 56));
  return 0;
}

```

## disassembly

```asm
0x18002c164  mov     [rsp-28h+arg_18], rbx
0x18002c169  push    rbp
0x18002c16a  push    rsi
0x18002c16b  push    rdi
0x18002c16c  push    r14
0x18002c16e  push    r15
0x18002c170  mov     rbp, rsp
0x18002c173  sub     rsp, 80h
0x18002c17a  mov     rax, cs:__security_cookie
0x18002c181  xor     rax, rsp
0x18002c184  mov     [rbp+var_8], rax
0x18002c188  mov     al, [rbp+arg_30]
0x18002c18b  mov     rsi, r9
0x18002c18e  mov     [rcx+22Eh], al
0x18002c194  mov     r14, r8
0x18002c197  mov     r15, rdx
0x18002c19a  mov     rdi, rcx
0x18002c19d  call    ?IsTabletMode@TabletModeHelpers@@YA_NXZ; TabletModeHelpers::IsTabletMode(void)
0x18002c1a2  lea     rcx, [rdi+1A0h]
0x18002c1a9  mov     [rdi+23Dh], al
0x18002c1af  call    ??$MakeAndInitialize@VCreationThreadDispatcher@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCreationThreadDispatcher@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CreationThreadDispatcher>>)
0x18002c1b4  mov     ebx, eax
0x18002c1b6  test    eax, eax
0x18002c1b8  jns     short loc_18002C1D9
0x18002c1ba  mov     edx, 0B7h; void *
0x18002c1bf  mov     rcx, [rbp+28h]; this
0x18002c1c3  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x18002c1ca  mov     r9d, ebx; char *
0x18002c1cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c1d2  mov     eax, ebx
0x18002c1d4  jmp     loc_18002C5EC
0x18002c1d9  mov     rax, [r14]
0x18002c1dc  lea     rdx, [rdi+1B8h]
0x18002c1e3  mov     rcx, r14
0x18002c1e6  mov     rax, [rax+48h]
0x18002c1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ef  mov     ebx, eax
0x18002c1f1  test    eax, eax
0x18002c1f3  jns     short loc_18002C1FC
0x18002c1f5  mov     edx, 0B9h
0x18002c1fa  jmp     short loc_18002C1BF
0x18002c1fc  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18002c202  mov     [rdi+5D8h], eax
0x18002c208  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18002c20e  mov     [rdi+5E0h], eax
0x18002c214  lea     rcx, [rbp+var_38]
0x18002c218  lea     rax, [rdi+68h]
0x18002c21c  mov     [rbp+var_38], rax
0x18002c220  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18002c225  mov     rdx, rax
0x18002c228  mov     rcx, r15
0x18002c22b  call    ??$AsWeak@UIApplicationFrameInternal@@@WRL@Microsoft@@YAJPEAUIApplicationFrameInternal@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IApplicationFrameInternal>(IApplicationFrameInternal *,Microsoft::WRL::WeakRef *)
0x18002c230  mov     ebx, eax
0x18002c232  test    eax, eax
0x18002c234  jns     short loc_18002C23D
0x18002c236  mov     edx, 0BEh
0x18002c23b  jmp     short loc_18002C1BF
0x18002c23d  lea     rax, [rdi+70h]
0x18002c241  lea     rcx, [rbp+var_38]
0x18002c245  mov     [rbp+var_38], rax
0x18002c249  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18002c24e  mov     rdx, rax
0x18002c251  mov     rcx, r14
0x18002c254  call    ??$AsWeak@UIDCompProvider@@@WRL@Microsoft@@YAJPEAUIDCompProvider@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IDCompProvider>(IDCompProvider *,Microsoft::WRL::WeakRef *)
0x18002c259  mov     ebx, eax
0x18002c25b  test    eax, eax
0x18002c25d  jns     short loc_18002C269
0x18002c25f  mov     edx, 0BFh
0x18002c264  jmp     loc_18002C1BF
0x18002c269  cmp     [rdi+168h], rsi
0x18002c270  jz      short loc_18002C29A
0x18002c272  lea     rcx, [rbp+var_28]
0x18002c276  mov     [rbp+var_28], rsi
0x18002c27a  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x18002c27f  mov     rax, [rdi+168h]
0x18002c286  lea     rcx, [rbp+var_28]
0x18002c28a  mov     [rbp+var_28], rax
0x18002c28e  mov     [rdi+168h], rsi
0x18002c295  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002c29a  movsd   xmm0, [rbp+arg_28]
0x18002c29f  mov     rcx, rdi; this
0x18002c2a2  mov     edx, [rbp+arg_20]; enum DEVICE_SCALE_FACTOR
0x18002c2a5  movsd   qword ptr [rdi+218h], xmm0
0x18002c2ad  call    ?_SetScaleFactors@CTitleBar@@AEAAXW4DEVICE_SCALE_FACTOR@@@Z; CTitleBar::_SetScaleFactors(DEVICE_SCALE_FACTOR)
0x18002c2b2  mov     rax, [r14]
0x18002c2b5  lea     rsi, [rdi+1F8h]
0x18002c2bc  mov     rdx, rsi
0x18002c2bf  mov     rcx, r14
0x18002c2c2  mov     rax, [rax+30h]
0x18002c2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2cb  call    cs:__imp_GetForegroundWindow
0x18002c2d1  cmp     rax, [rsi]
0x18002c2d4  mov     rcx, rdi; this
0x18002c2d7  setz    al
0x18002c2da  mov     [rdi+232h], al
0x18002c2e0  call    ?UpdateBorderVisibilityAndMargins@CTitleBar@@AEAA_NXZ; CTitleBar::UpdateBorderVisibilityAndMargins(void)
0x18002c2e5  mov     rcx, rdi; this
0x18002c2e8  call    ?_UpdateCurrentRestoreGlyph@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateCurrentRestoreGlyph(void)
0x18002c2ed  lea     rdx, [rdi+27Ch]; struct CTitleBar::TitleBarColorSet *
0x18002c2f4  xor     r8d, r8d; bool *
0x18002c2f7  mov     rcx, rdi; this
0x18002c2fa  call    ?_GetDefaultColors@CTitleBar@@AEAAXPEAUTitleBarColorSet@1@PEA_N@Z; CTitleBar::_GetDefaultColors(CTitleBar::TitleBarColorSet *,bool *)
0x18002c2ff  mov     eax, 0FFFFFFh
0x18002c304  xor     edx, edx; bool
0x18002c306  mov     [rdi+2ECh], eax
0x18002c30c  mov     rcx, rdi; this
0x18002c30f  mov     [rdi+2F0h], eax
0x18002c315  mov     [rdi+2F4h], eax
0x18002c31b  mov     [rdi+2F8h], eax
0x18002c321  mov     [rdi+2FCh], eax
0x18002c327  mov     [rdi+304h], eax
0x18002c32d  mov     [rdi+308h], eax
0x18002c333  mov     [rdi+310h], eax
0x18002c339  movups  xmm0, xmmword ptr [rdi+2ECh]
0x18002c340  mov     [rdi+2DCh], eax
0x18002c346  movups  xmm1, xmmword ptr [rdi+2FCh]
0x18002c34d  mov     [rdi+2E0h], eax
0x18002c353  movups  xmmword ptr [rdi+314h], xmm0
0x18002c35a  mov     [rdi+2E4h], eax
0x18002c360  movsd   xmm0, qword ptr [rdi+30Ch]
0x18002c368  movups  xmmword ptr [rdi+324h], xmm1
0x18002c36f  mov     [rdi+2E8h], eax
0x18002c375  movsd   qword ptr [rdi+334h], xmm0
0x18002c37d  call    ?_UpdateColorsFromApplicationViewAsync@CTitleBar@@AEAAJ_N@Z; CTitleBar::_UpdateColorsFromApplicationViewAsync(bool)
0x18002c382  lea     rbx, [rdi+198h]
0x18002c389  mov     rcx, rbx
0x18002c38c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002c391  mov     ecx, [rdi+210h]; enum DEVICE_SCALE_FACTOR
0x18002c397  mov     r8, rbx; void **
0x18002c39a  call    ?CActionsContextMenuProvider_CreateInstance@@YAJW4DEVICE_SCALE_FACTOR@@AEBU_GUID@@PEAPEAX@Z; CActionsContextMenuProvider_CreateInstance(DEVICE_SCALE_FACTOR,_GUID const &,void * *)
0x18002c39f  mov     ebx, eax
0x18002c3a1  test    eax, eax
0x18002c3a3  jns     short loc_18002C3AF
0x18002c3a5  mov     edx, 0D2h
0x18002c3aa  jmp     loc_18002C1BF
0x18002c3af  mov     rcx, rdi; this
0x18002c3b2  call    ?_InitializeDCompVariables@CTitleBar@@AEAAJXZ; CTitleBar::_InitializeDCompVariables(void)
0x18002c3b7  mov     ebx, eax
0x18002c3b9  test    eax, eax
0x18002c3bb  jns     short loc_18002C3C7
0x18002c3bd  mov     edx, 0D4h
0x18002c3c2  jmp     loc_18002C1BF
0x18002c3c7  mov     rcx, [rsi]; hWnd
0x18002c3ca  lea     rdx, [rbp+Rect]; lpRect
0x18002c3ce  xorps   xmm0, xmm0
0x18002c3d1  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x18002c3d6  call    cs:__imp_GetWindowRect
0x18002c3dc  mov     edx, [rbp+Rect.bottom]
0x18002c3df  mov     r9d, [rbp+Rect.top]; Y
0x18002c3e3  sub     edx, r9d
0x18002c3e6  mov     eax, [rbp+Rect.right]
0x18002c3e9  mov     r8d, [rbp+Rect.left]; X
0x18002c3ed  sub     eax, r8d
0x18002c3f0  mov     rcx, [rsi]; hWnd
0x18002c3f3  mov     [rsp+80h+uFlags], 30h ; '0'; uFlags
0x18002c3fb  mov     [rsp+80h+cy], edx; cy
0x18002c3ff  xor     edx, edx; hWndInsertAfter
0x18002c401  mov     [rsp+80h+var_60], eax; cx
0x18002c405  call    cs:__imp_SetWindowPos
0x18002c40b  call    ?Mirror_IsThreadRTL@@YAHXZ; Mirror_IsThreadRTL(void)
0x18002c410  test    eax, eax
0x18002c412  mov     rcx, rdi; this
0x18002c415  setnz   al
0x18002c418  mov     [rdi+22Fh], al
0x18002c41e  call    ?_UpdateRtlWindowProp@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateRtlWindowProp(void)
0x18002c423  call    ?_RegisterTitleBarWindowClass@CTitleBar@@AEAAXXZ; CTitleBar::_RegisterTitleBarWindowClass(void)
0x18002c428  mov     rcx, rdi; this
0x18002c42b  call    ?_CreateTitleBarWindow@CTitleBar@@AEAAJXZ; CTitleBar::_CreateTitleBarWindow(void)
0x18002c430  mov     ebx, eax
0x18002c432  test    eax, eax
0x18002c434  jns     short loc_18002C440
0x18002c436  mov     edx, 0E0h
0x18002c43b  jmp     loc_18002C1BF
0x18002c440  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar> `wil::Feature<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetImpl(void)'::`2'::impl
0x18002c447  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18002c44c  mov     rcx, rdi; this
0x18002c44f  call    ?_UpdateMicaBackdrop@CTitleBar@@AEAAXXZ; CTitleBar::_UpdateMicaBackdrop(void)
0x18002c454  lea     rdx, [rbp+var_40]; enum TITLE_BAR_BUTTONS *
0x18002c458  mov     [rbp+var_30], 33Fh
0x18002c45f  lea     rcx, [rdi+38h]; this
0x18002c463  mov     [rbp+var_40], 0
0x18002c46a  call    ?GetVisibleButtons@CTitleBar@@UEAAJPEAW4TITLE_BAR_BUTTONS@@@Z; CTitleBar::GetVisibleButtons(TITLE_BAR_BUTTONS *)
0x18002c46f  mov     ebx, eax
0x18002c471  test    eax, eax
0x18002c473  jns     short loc_18002C47F
0x18002c475  mov     edx, 0EAh
0x18002c47a  jmp     loc_18002C1BF
0x18002c47f  mov     al, [rdi+231h]
0x18002c485  lea     r8, [rdi+8]
0x18002c489  mov     esi, [rbp+var_40]
0x18002c48c  lea     r9, [rbp+var_28]
0x18002c490  and     esi, 0C0h
0x18002c496  mov     [rbp+var_40], 0Eh
0x18002c49d  lea     rdx, [rbp+var_20]
0x18002c4a1  mov     [rbp+var_20], rdi
0x18002c4a5  setnz   r15b
0x18002c4a9  neg     al
0x18002c4ab  lea     rax, [rbp+var_30]
0x18002c4af  sbb     ecx, ecx
0x18002c4b1  mov     qword ptr [rsp+80h+cy], rax
0x18002c4b6  add     ecx, 2
0x18002c4b9  lea     rax, [rbp+var_40]
0x18002c4bd  mov     dword ptr [rbp+var_28], ecx
0x18002c4c0  lea     rcx, [rbp+var_38]
0x18002c4c4  mov     qword ptr [rsp+80h+var_60], rax
0x18002c4c9  call    ??$Make@VCTitleBarAcc@@PEAVCTitleBar@@AEAPEAUHWND__@@W4TitleBarAccFlags@@W4TitleBarPart@@AEAW4TITLE_BAR_BUTTONS@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCTitleBarAcc@@@12@$$QEAPEAVCTitleBar@@AEAPEAUHWND__@@$$QEAW4TitleBarAccFlags@@$$QEAW4TitleBarPart@@AEAW4TITLE_BAR_BUTTONS@@@Z; Microsoft::WRL::Details::Make<CTitleBarAcc,CTitleBar *,HWND__ * &,TitleBarAccFlags,TitleBarPart,TITLE_BAR_BUTTONS &>(CTitleBar * &&,HWND__ * &,TitleBarAccFlags &&,TitleBarPart &&,TITLE_BAR_BUTTONS &)
0x18002c4ce  lea     rbx, [rdi+188h]
0x18002c4d5  mov     rdx, rax
0x18002c4d8  mov     rcx, rbx
0x18002c4db  call    ??$?4VCTitleBarAcc@@@?$ComPtr@UIApplicationFrameTitleBarAccInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV?$ComPtr@VCTitleBarAcc@@@12@@Z; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccInternal>::operator=<CTitleBarAcc>(Microsoft::WRL::ComPtr<CTitleBarAcc> &&)
0x18002c4e0  mov     rcx, [rbp+var_38]
0x18002c4e4  test    rcx, rcx
0x18002c4e7  jz      short loc_18002C4F6
0x18002c4e9  mov     [rbp+var_38], 0
0x18002c4f1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccInternal@@UIApplicationFrameTitleBarAccRootInternal@@UIValueProvider@@UIRawElementProviderFragmentRoot@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::Release(void)
0x18002c4f6  cmp     qword ptr [rbx], 0
0x18002c4fa  jnz     short loc_18002C50B
0x18002c4fc  mov     ebx, 8007000Eh
0x18002c501  mov     edx, 0F2h
0x18002c506  jmp     loc_18002C1BF
0x18002c50b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode> `wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl(void)'::`2'::impl
0x18002c512  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(void)
0x18002c517  mov     rcx, [rbx]
0x18002c51a  test    al, al
0x18002c51c  mov     rax, [rcx]
0x18002c51f  mov     rax, [rax+50h]
0x18002c523  jz      short loc_18002C532
0x18002c525  cmp     byte ptr [rdi+23Ch], 0
0x18002c52c  setz    r8b
0x18002c530  jmp     short loc_18002C535
0x18002c532  mov     r8b, 1
0x18002c535  test    esi, esi
0x18002c537  setz    dl
0x18002c53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c53f  lea     rax, [rbp+var_28]
0x18002c543  mov     dword ptr [rbp+var_28], 0Dh
0x18002c54a  lea     r8, [rdi+208h]
0x18002c551  mov     qword ptr [rsp+80h+var_60], rax
0x18002c556  lea     r9, [rbp+var_30]
0x18002c55a  mov     [rbp+var_30], 1
0x18002c561  lea     rdx, [rbp+var_20]
0x18002c565  mov     [rbp+var_20], rdi
0x18002c569  lea     rcx, [rbp+var_38]
0x18002c56d  call    ??$Make@VCTitleBarAcc@@PEAVCTitleBar@@AEAPEAUHWND__@@W4TitleBarAccFlags@@W4TitleBarPart@@AEBW4TITLE_BAR_BUTTONS@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCTitleBarAcc@@@12@$$QEAPEAVCTitleBar@@AEAPEAUHWND__@@$$QEAW4TitleBarAccFlags@@$$QEAW4TitleBarPart@@AEBW4TITLE_BAR_BUTTONS@@@Z; Microsoft::WRL::Details::Make<CTitleBarAcc,CTitleBar *,HWND__ * &,TitleBarAccFlags,TitleBarPart,TITLE_BAR_BUTTONS const &>(CTitleBar * &&,HWND__ * &,TitleBarAccFlags &&,TitleBarPart &&,TITLE_BAR_BUTTONS const &)
0x18002c572  lea     rbx, [rdi+190h]
0x18002c579  mov     rdx, rax
0x18002c57c  mov     rcx, rbx
0x18002c57f  call    ??$?4VCTitleBarAcc@@@?$ComPtr@UIApplicationFrameTitleBarAccInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV?$ComPtr@VCTitleBarAcc@@@12@@Z; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccInternal>::operator=<CTitleBarAcc>(Microsoft::WRL::ComPtr<CTitleBarAcc> &&)
0x18002c584  mov     rcx, [rbp+var_38]
0x18002c588  test    rcx, rcx
0x18002c58b  jz      short loc_18002C59A
0x18002c58d  mov     [rbp+var_38], 0
0x18002c595  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccInternal@@UIApplicationFrameTitleBarAccRootInternal@@UIValueProvider@@UIRawElementProviderFragmentRoot@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::Release(void)
0x18002c59a  cmp     qword ptr [rbx], 0
0x18002c59e  jnz     short loc_18002C5AF
0x18002c5a0  mov     ebx, 8007000Eh
0x18002c5a5  mov     edx, 101h
0x18002c5aa  jmp     loc_18002C1BF
0x18002c5af  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode> `wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl(void)'::`2'::impl
0x18002c5b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(void)
0x18002c5bb  mov     rcx, [rbx]
0x18002c5be  test    al, al
0x18002c5c0  mov     dl, r15b
0x18002c5c3  mov     rax, [rcx]
0x18002c5c6  mov     rax, [rax+50h]
0x18002c5ca  jz      short loc_18002C5D9
0x18002c5cc  cmp     byte ptr [rdi+23Ch], 0
0x18002c5d3  setz    r8b
0x18002c5d7  jmp     short loc_18002C5DC
0x18002c5d9  mov     r8b, 1
0x18002c5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5e1  lea     rcx, [rdi+38h]; this
0x18002c5e5  call    ?OnTitleBarHitTestVisualUpdated@CTitleBar@@UEAAJXZ; CTitleBar::OnTitleBarHitTestVisualUpdated(void)
0x18002c5ea  xor     eax, eax
0x18002c5ec  mov     rcx, [rbp+var_8]
0x18002c5f0  xor     rcx, rsp; StackCookie
0x18002c5f3  call    __security_check_cookie
0x18002c5f8  mov     rbx, [rsp+80h+arg_18]
0x18002c600  add     rsp, 80h
0x18002c607  pop     r15
0x18002c609  pop     r14
0x18002c60b  pop     rdi
0x18002c60c  pop     rsi
0x18002c60d  pop     rbp
0x18002c60e  retn
```
