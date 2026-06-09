# EdgeUiHint::ShowForApp(IUnknown *,IImmersiveApplication *,bool)

- ea: `0x1801f9f60`
- end: `0x1801fa36d`
- name: `?ShowForApp@EdgeUiHint@@UEAAJPEAUIUnknown@@PEAUIImmersiveApplication@@_N@Z`
- size: `1037`
- prototype: `int(EdgeUiHint *__hidden this, struct IUnknown *, struct IImmersiveApplication *, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18002576c`
- `0x1800378dc`
- `0x18004cf78`
- `0x180055f0c`
- `0x1800b9d70`
- `0x1800f1a00`
- `0x180142e10`
- `0x180154228`
- `0x1801f9f60`
- `0x1803bb010`

## import_xrefs

- `USER32!UpdateWindow` at `0x1801fa2ea`
- `USER32!UpdateWindow` at `0x1801fa2ea`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1801fa319`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1801fa319`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1801fa2db`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1801fa2db`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetTimer` at `0x1801fa33c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetTimer` at `0x1801fa33c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1801fa286`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x1801fa286`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801f9fd1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801f9ffe`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801f9fd1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1801f9ffe`
- `ext-ms-win-ntuser-private-l1-1-1!CreateWindowInBand` at `0x1801fa254`
- `ext-ms-win-ntuser-private-l1-1-1!CreateWindowInBand` at `0x1801fa254`
- `dwmapi!__imp_DwmpBeginTransitionRequest` at `0x1801fa2a7`
- `dwmapi!__imp_DwmpBeginTransitionRequest` at `0x1801fa2a7`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x1801fa2c5`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x1801fa2c5`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x1801fa2fd`
- `dwmapi!__imp_DwmpEndTransitionRequest` at `0x1801fa2fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EdgeUiHint::ShowForApp(
        EdgeUiHint *this,
        struct IUnknown *a2,
        struct IImmersiveApplication *a3,
        char a4)
{
  IUnknown *v6; // rbx
  int v8; // edi
  __int64 v9; // rcx
  HRESULT Service; // eax
  unsigned int v11; // ebx
  int Site; // eax
  __int64 v13; // rdx
  HWND v15; // rcx
  int v16; // eax
  float v17; // xmm1_4
  float v18; // xmm0_4
  int v19; // edi
  int v20; // ebx
  int IsThreadRTL; // eax
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // eax
  __int64 WindowInBand; // rax
  const char *v28; // r9
  HWND *v29; // rbx
  int v30; // [rsp+20h] [rbp-49h]
  void *v31; // [rsp+70h] [rbp+7h] BYREF
  void *ppvOut[2]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = a2;
  v8 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::GetImpl'::`2'::impl,
    a2);
  v9 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( IUnknown_QueryService(v6, &stru_180428778, &GUID_af855df0_7bbf_47b3_ae2e_85ba3869660f, (void **)this + 7) >= 0 )
  {
    ppvOut[0] = 0;
    Service = IUnknown_QueryService(
                v6,
                &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                &GUID_880b26f8_9197_43d0_8045_8702d0d72000,
                ppvOut);
    v11 = Service;
    if ( Service < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
        (const char *)(unsigned int)Service,
        v30);
LABEL_11:
      wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(ppvOut);
      return v11;
    }
    v31 = 0;
    Site = CWRLObjectWithSite::GetSite(
             (EdgeUiHint *)((char *)this - 24),
             &GUID_49233ba3_27b2_46b6_9601_446910c8c663,
             &v31);
    v11 = Site;
    if ( Site < 0 )
    {
      v13 = 144;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
        (const char *)(unsigned int)Site,
        v30);
      wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(&v31);
      goto LABEL_11;
    }
    Site = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, void *))(**((_QWORD **)this + 7) + 32LL))(
             *((_QWORD *)this + 7),
             *((unsigned int *)this + 4),
             ppvOut[0],
             v31);
    v11 = Site;
    if ( Site < 0 )
    {
      v13 = 145;
      goto LABEL_10;
    }
    wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(&v31);
    wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(ppvOut);
    return (unsigned int)v8;
  }
  v15 = (HWND)*((_QWORD *)this + 3);
  if ( v15 )
  {
    v29 = (HWND *)((char *)this + 24);
    if ( IsWindowVisible(v15) )
    {
LABEL_41:
      if ( a4 )
        *((_QWORD *)this + 4) = SetTimer(*v29, 1u, 0x1388u, 0);
      return (unsigned int)v8;
    }
LABEL_36:
    v8 = DwmpBeginTransitionRequest(4);
    if ( v8 >= 0 )
    {
      v29 = (HWND *)((char *)this + 24);
      v8 = DwmpTransitionWindow(*((_QWORD *)this + 3), 1048601);
    }
    ShowWindow(*v29, 8);
    UpdateWindow(*v29);
    if ( v8 < 0 )
    {
      SendMessageW(*v29, 0x32Au, 4u, 4);
      v8 = 0;
    }
    else
    {
      DwmpEndTransitionRequest(4);
    }
    goto LABEL_41;
  }
  IUnknown_GetScaleFactor(v6, (enum DEVICE_SCALE_FACTOR *)this + 12);
  *(_OWORD *)ppvOut = 0;
  v16 = (*(__int64 (__fastcall **)(struct IImmersiveApplication *, void **))(*(_QWORD *)a3 + 200LL))(a3, ppvOut);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
      (const char *)(unsigned int)v16,
      v30);
    return v11;
  }
  v17 = (float)(16 * *((_DWORD *)this + 12)) / 100.0;
  if ( (unsigned int)(*((_DWORD *)this + 4) - 2) > 1 )
  {
    v18 = (float)(16 * *((_DWORD *)this + 12)) / 100.0;
    v17 = (float)(80 * *((_DWORD *)this + 12)) / 100.0;
  }
  else
  {
    v18 = (float)(80 * *((_DWORD *)this + 12)) / 100.0;
  }
  v19 = (int)v17;
  v20 = (int)v18;
  IsThreadRTL = Mirror_IsThreadRTL();
  v22 = *((_DWORD *)this + 4);
  if ( !v22 )
  {
    if ( IsThreadRTL )
    {
      v25 = LODWORD(ppvOut[1]) - v20 - LODWORD(ppvOut[0]);
      goto LABEL_32;
    }
    goto LABEL_30;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    if ( !IsThreadRTL )
    {
      v25 = LODWORD(ppvOut[1]) - v20;
LABEL_32:
      v26 = HIDWORD(ppvOut[0]) + (HIDWORD(ppvOut[1]) - v19 - HIDWORD(ppvOut[0])) / 2;
LABEL_33:
      WindowInBand = CreateWindowInBand(
                       134742144,
                       L"EdgeUiInputHintWndClass",
                       0,
                       0x80000000LL,
                       v25,
                       v26,
                       v20,
                       (int)v17,
                       0,
                       0,
                       &_ImageBase,
                       (char *)this - 24,
                       7);
      v29 = (HWND *)((char *)this + 24);
      *((_QWORD *)this + 3) = WindowInBand;
      if ( !WindowInBand )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0xE6,
                 (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
                 v28);
      goto LABEL_36;
    }
LABEL_30:
    v25 = (int)ppvOut[0];
    goto LABEL_32;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    v25 = LODWORD(ppvOut[0]) + (LODWORD(ppvOut[1]) - v20 - LODWORD(ppvOut[0])) / 2;
    v26 = HIDWORD(ppvOut[0]);
    goto LABEL_33;
  }
  if ( v24 == 1 )
  {
    v25 = LODWORD(ppvOut[0]) + (LODWORD(ppvOut[1]) - v20 - LODWORD(ppvOut[0])) / 2;
    v26 = HIDWORD(ppvOut[1]) - v19;
    goto LABEL_33;
  }
  v8 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x110,
    (unsigned int)"shell\\twinui\\edgeui\\lib\\edgeuihint.cpp",
    (const char *)0x8000FFFFLL,
    v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801f9f60  push    rbp
0x1801f9f62  push    rbx
0x1801f9f63  push    rsi
0x1801f9f64  push    rdi
0x1801f9f65  push    r12
0x1801f9f67  push    r14
0x1801f9f69  push    r15
0x1801f9f6b  lea     rbp, [rsp-27h]
0x1801f9f70  sub     rsp, 90h
0x1801f9f77  mov     rax, cs:__security_cookie
0x1801f9f7e  xor     rax, rsp
0x1801f9f81  mov     [rbp+57h+var_38], rax
0x1801f9f85  mov     r12b, r9b
0x1801f9f88  mov     r15, r8
0x1801f9f8b  mov     rbx, rdx
0x1801f9f8e  mov     rsi, rcx
0x1801f9f91  xor     edi, edi
0x1801f9f93  mov     dl, 1
0x1801f9f95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputDrivenEdgeAnimations@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputDrivenEdgeAnimations@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations> `wil::Feature<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::GetImpl(void)'::`2'::impl
0x1801f9f9c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InputDrivenEdgeAnimations@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputDrivenEdgeAnimations>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801f9fa1  lea     r14, [rsi+38h]
0x1801f9fa5  mov     rcx, [r14]
0x1801f9fa8  mov     [r14], rdi
0x1801f9fab  test    rcx, rcx
0x1801f9fae  jz      short loc_1801F9FBD
0x1801f9fb0  mov     rax, [rcx]
0x1801f9fb3  mov     rax, [rax+10h]
0x1801f9fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f9fbc  nop
0x1801f9fbd  mov     r9, r14; ppvOut
0x1801f9fc0  lea     r8, _GUID_af855df0_7bbf_47b3_ae2e_85ba3869660f; riid
0x1801f9fc7  lea     rdx, stru_180428778; guidService
0x1801f9fce  mov     rcx, rbx; punk
0x1801f9fd1  call    cs:__imp_IUnknown_QueryService
0x1801f9fd8  nop     dword ptr [rax+rax+00h]
0x1801f9fdd  test    eax, eax
0x1801f9fdf  js      loc_1801FA0BE
0x1801f9fe5  mov     [rbp+57h+ppvOut], 0
0x1801f9fed  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1801f9ff1  lea     rdx, _GUID_880b26f8_9197_43d0_8045_8702d0d72000; guidService
0x1801f9ff8  mov     r8, rdx; riid
0x1801f9ffb  mov     rcx, rbx; punk
0x1801f9ffe  call    cs:__imp_IUnknown_QueryService
0x1801fa005  nop     dword ptr [rax+rax+00h]
0x1801fa00a  mov     ebx, eax
0x1801fa00c  test    eax, eax
0x1801fa00e  jns     short loc_1801FA02A
0x1801fa010  mov     rcx, [rbp+5Fh]; this
0x1801fa014  mov     r9d, eax; char *
0x1801fa017  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801fa01e  mov     edx, 8Eh; void *
0x1801fa023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa028  jmp     short loc_1801FA096
0x1801fa02a  mov     [rbp+57h+var_50], 0
0x1801fa032  lea     rcx, [rsi-18h]; this
0x1801fa036  lea     r8, [rbp+57h+var_50]; void **
0x1801fa03a  lea     rdx, _GUID_49233ba3_27b2_46b6_9601_446910c8c663; struct _GUID *
0x1801fa041  call    ?GetSite@CWRLObjectWithSite@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWRLObjectWithSite::GetSite(_GUID const &,void * *)
0x1801fa046  mov     ebx, eax
0x1801fa048  test    eax, eax
0x1801fa04a  jns     short loc_1801FA053
0x1801fa04c  mov     edx, 90h
0x1801fa051  jmp     short loc_1801FA078
0x1801fa053  mov     rcx, [r14]
0x1801fa056  mov     rax, [rcx]
0x1801fa059  mov     r9, [rbp+57h+var_50]
0x1801fa05d  mov     r8, [rbp+57h+ppvOut]
0x1801fa061  mov     edx, [rsi+10h]
0x1801fa064  mov     rax, [rax+20h]
0x1801fa068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa06d  mov     ebx, eax
0x1801fa06f  test    eax, eax
0x1801fa071  jns     short loc_1801FA0A6
0x1801fa073  mov     edx, 91h; void *
0x1801fa078  mov     r9d, eax; char *
0x1801fa07b  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801fa082  mov     rcx, [rbp+5Fh]; this
0x1801fa086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa08b  nop
0x1801fa08c  lea     rcx, [rbp+57h+var_50]
0x1801fa090  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801fa095  nop
0x1801fa096  lea     rcx, [rbp+57h+ppvOut]
0x1801fa09a  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801fa09f  mov     eax, ebx
0x1801fa0a1  jmp     loc_1801FA34E
0x1801fa0a6  lea     rcx, [rbp+57h+var_50]
0x1801fa0aa  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801fa0af  nop
0x1801fa0b0  lea     rcx, [rbp+57h+ppvOut]
0x1801fa0b4  call    ??1?$com_ptr_t@UICoreWindowSite@Core@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Core::ICoreWindowSite,wil::err_returncode_policy>(void)
0x1801fa0b9  jmp     loc_1801FA34C
0x1801fa0be  lea     r14, [rsi-18h]
0x1801fa0c2  mov     rcx, [r14+30h]; hWnd
0x1801fa0c6  test    rcx, rcx
0x1801fa0c9  jnz     loc_1801FA286
0x1801fa0cf  lea     rdx, [rsi+30h]; enum DEVICE_SCALE_FACTOR *
0x1801fa0d3  mov     rcx, rbx; punk
0x1801fa0d6  call    ?IUnknown_GetScaleFactor@@YAJPEAUIUnknown@@PEAW4DEVICE_SCALE_FACTOR@@@Z; IUnknown_GetScaleFactor(IUnknown *,DEVICE_SCALE_FACTOR *)
0x1801fa0db  xorps   xmm0, xmm0
0x1801fa0de  movdqu  xmmword ptr [rbp+57h+ppvOut], xmm0
0x1801fa0e3  mov     rax, [r15]
0x1801fa0e6  lea     rdx, [rbp+57h+ppvOut]
0x1801fa0ea  mov     rcx, r15
0x1801fa0ed  mov     rax, [rax+0C8h]
0x1801fa0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa0f9  mov     ebx, eax
0x1801fa0fb  test    eax, eax
0x1801fa0fd  jns     short loc_1801FA119
0x1801fa0ff  mov     rcx, [rbp+5Fh]; this
0x1801fa103  mov     r9d, eax; char *
0x1801fa106  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801fa10d  mov     edx, 9Ch; void *
0x1801fa112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa117  jmp     short loc_1801FA09F
0x1801fa119  mov     eax, [rsi+10h]
0x1801fa11c  mov     r15d, 2
0x1801fa122  sub     eax, r15d
0x1801fa125  cmp     eax, 1
0x1801fa128  setbe   dl
0x1801fa12b  mov     ecx, [rsi+30h]
0x1801fa12e  mov     eax, ecx
0x1801fa130  shl     eax, 4
0x1801fa133  movd    xmm1, eax
0x1801fa137  cvtdq2ps xmm1, xmm1
0x1801fa13a  divss   xmm1, cs:__real@42c80000
0x1801fa142  lea     eax, [rcx+rcx*4]
0x1801fa145  shl     eax, 4
0x1801fa148  movd    xmm2, eax
0x1801fa14c  cvtdq2ps xmm2, xmm2
0x1801fa14f  divss   xmm2, cs:__real@42c80000
0x1801fa157  test    dl, dl
0x1801fa159  jz      short loc_1801FA160
0x1801fa15b  movaps  xmm0, xmm2
0x1801fa15e  jmp     short loc_1801FA166
0x1801fa160  movaps  xmm0, xmm1
0x1801fa163  movaps  xmm1, xmm2
0x1801fa166  cvttss2si edi, xmm1
0x1801fa16a  cvttss2si ebx, xmm0
0x1801fa16e  call    Mirror_IsThreadRTL
0x1801fa173  mov     ecx, [rsi+10h]
0x1801fa176  test    ecx, ecx
0x1801fa178  jz      short loc_1801FA1E4
0x1801fa17a  sub     ecx, 1
0x1801fa17d  jz      short loc_1801FA1D9
0x1801fa17f  sub     ecx, 1
0x1801fa182  jz      short loc_1801FA1C3
0x1801fa184  cmp     ecx, 1
0x1801fa187  jz      short loc_1801FA1AB
0x1801fa189  mov     rcx, [rbp+5Fh]; this
0x1801fa18d  mov     edi, 8000FFFFh
0x1801fa192  mov     r9d, edi; char *
0x1801fa195  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801fa19c  mov     edx, 110h; void *
0x1801fa1a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fa1a6  jmp     loc_1801FA34C
0x1801fa1ab  mov     eax, dword ptr [rbp+57h+ppvOut+8]
0x1801fa1ae  sub     eax, ebx
0x1801fa1b0  sub     eax, dword ptr [rbp+57h+ppvOut]
0x1801fa1b3  cdq
0x1801fa1b4  idiv    r15d
0x1801fa1b7  mov     ecx, eax
0x1801fa1b9  add     ecx, dword ptr [rbp+57h+ppvOut]
0x1801fa1bc  mov     eax, dword ptr [rbp+57h+ppvOut+0Ch]
0x1801fa1bf  sub     eax, edi
0x1801fa1c1  jmp     short loc_1801FA204
0x1801fa1c3  mov     eax, dword ptr [rbp+57h+ppvOut+8]
0x1801fa1c6  sub     eax, ebx
0x1801fa1c8  sub     eax, dword ptr [rbp+57h+ppvOut]
0x1801fa1cb  cdq
0x1801fa1cc  idiv    r15d
0x1801fa1cf  mov     ecx, eax
0x1801fa1d1  add     ecx, dword ptr [rbp+57h+ppvOut]
0x1801fa1d4  mov     eax, dword ptr [rbp+57h+ppvOut+4]
0x1801fa1d7  jmp     short loc_1801FA204
0x1801fa1d9  test    eax, eax
0x1801fa1db  jnz     short loc_1801FA1E8
0x1801fa1dd  mov     ecx, dword ptr [rbp+57h+ppvOut+8]
0x1801fa1e0  sub     ecx, ebx
0x1801fa1e2  jmp     short loc_1801FA1F5
0x1801fa1e4  test    eax, eax
0x1801fa1e6  jnz     short loc_1801FA1ED
0x1801fa1e8  mov     ecx, dword ptr [rbp+57h+ppvOut]
0x1801fa1eb  jmp     short loc_1801FA1F5
0x1801fa1ed  mov     ecx, dword ptr [rbp+57h+ppvOut+8]
0x1801fa1f0  sub     ecx, ebx
0x1801fa1f2  sub     ecx, dword ptr [rbp+57h+ppvOut]
0x1801fa1f5  mov     eax, dword ptr [rbp+57h+ppvOut+0Ch]
0x1801fa1f8  sub     eax, edi
0x1801fa1fa  sub     eax, dword ptr [rbp+57h+ppvOut+4]
0x1801fa1fd  cdq
0x1801fa1fe  idiv    r15d
0x1801fa201  add     eax, dword ptr [rbp+57h+ppvOut+4]
0x1801fa204  mov     [rsp+0C0h+var_60], 7
0x1801fa20c  mov     [rsp+0C0h+var_68], r14
0x1801fa211  lea     rdx, __ImageBase
0x1801fa218  mov     [rsp+0C0h+var_70], rdx
0x1801fa21d  mov     [rsp+0C0h+var_78], 0
0x1801fa226  mov     [rsp+0C0h+var_80], 0
0x1801fa22f  mov     [rsp+0C0h+var_88], edi
0x1801fa233  mov     [rsp+0C0h+var_90], ebx
0x1801fa237  mov     [rsp+0C0h+var_98], eax
0x1801fa23b  mov     [rsp+0C0h+var_A0], ecx
0x1801fa23f  mov     r9d, 80000000h
0x1801fa245  xor     r8d, r8d
0x1801fa248  lea     rdx, aEdgeuiinputhin; "EdgeUiInputHintWndClass"
0x1801fa24f  mov     ecx, 8080080h
0x1801fa254  call    cs:__imp_CreateWindowInBand
0x1801fa25b  nop     dword ptr [rax+rax+00h]
0x1801fa260  lea     rbx, [rsi+18h]
0x1801fa264  mov     [rbx], rax
0x1801fa267  test    rax, rax
0x1801fa26a  jnz     short loc_1801FA29E
0x1801fa26c  mov     rcx, [rbp+5Fh]; this
0x1801fa270  lea     r8, aShellTwinuiEdg_0; "shell\\twinui\\edgeui\\lib\\edgeuihint."...
0x1801fa277  mov     edx, 0E6h; void *
0x1801fa27c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801fa281  jmp     loc_1801FA34E
0x1801fa286  call    cs:__imp_IsWindowVisible
0x1801fa28d  nop     dword ptr [rax+rax+00h]
0x1801fa292  lea     rbx, [rsi+18h]
0x1801fa296  test    eax, eax
0x1801fa298  jnz     loc_1801FA327
0x1801fa29e  mov     r14d, 4
0x1801fa2a4  mov     ecx, r14d
0x1801fa2a7  call    cs:__imp_DwmpBeginTransitionRequest
0x1801fa2ae  nop     dword ptr [rax+rax+00h]
0x1801fa2b3  mov     edi, eax
0x1801fa2b5  test    eax, eax
0x1801fa2b7  js      short loc_1801FA2D3
0x1801fa2b9  lea     rbx, [rsi+18h]
0x1801fa2bd  mov     edx, 100019h
0x1801fa2c2  mov     rcx, [rbx]
0x1801fa2c5  call    cs:__imp_DwmpTransitionWindow
0x1801fa2cc  nop     dword ptr [rax+rax+00h]
0x1801fa2d1  mov     edi, eax
0x1801fa2d3  mov     edx, 8; nCmdShow
0x1801fa2d8  mov     rcx, [rbx]; hWnd
0x1801fa2db  call    cs:__imp_ShowWindow
0x1801fa2e2  nop     dword ptr [rax+rax+00h]
0x1801fa2e7  mov     rcx, [rbx]; hWnd
0x1801fa2ea  call    cs:__imp_UpdateWindow
0x1801fa2f1  nop     dword ptr [rax+rax+00h]
0x1801fa2f6  test    edi, edi
0x1801fa2f8  js      short loc_1801FA30B
0x1801fa2fa  mov     ecx, r14d
0x1801fa2fd  call    cs:__imp_DwmpEndTransitionRequest
0x1801fa304  nop     dword ptr [rax+rax+00h]
0x1801fa309  jmp     short loc_1801FA327
0x1801fa30b  mov     r9, r14; lParam
0x1801fa30e  mov     r8, r14; wParam
0x1801fa311  mov     edx, 32Ah; Msg
0x1801fa316  mov     rcx, [rbx]; hWnd
0x1801fa319  call    cs:__imp_SendMessageW
0x1801fa320  nop     dword ptr [rax+rax+00h]
0x1801fa325  xor     edi, edi
0x1801fa327  test    r12b, r12b
0x1801fa32a  jz      short loc_1801FA34C
0x1801fa32c  xor     r9d, r9d; lpTimerFunc
0x1801fa32f  lea     edx, [r9+1]; nIDEvent
0x1801fa333  mov     r8d, 1388h; uElapse
0x1801fa339  mov     rcx, [rbx]; hWnd
0x1801fa33c  call    cs:__imp_SetTimer
0x1801fa343  nop     dword ptr [rax+rax+00h]
0x1801fa348  mov     [rsi+20h], rax
0x1801fa34c  mov     eax, edi
0x1801fa34e  mov     rcx, [rbp+57h+var_38]
0x1801fa352  xor     rcx, rsp; StackCookie
0x1801fa355  call    __security_check_cookie
0x1801fa35a  add     rsp, 90h
0x1801fa361  pop     r15
0x1801fa363  pop     r14
0x1801fa365  pop     r12
0x1801fa367  pop     rdi
0x1801fa368  pop     rsi
0x1801fa369  pop     rbx
0x1801fa36a  pop     rbp
0x1801fa36b  retn
```
