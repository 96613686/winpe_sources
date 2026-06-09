# RetailDemoUserAgent::LaunchAppWithoutForeground(ushort const *,ushort const *,LaunchOptionsUA,tagRECT *)

- ea: `0x18003e41c`
- end: `0x18003e95d`
- name: `?LaunchAppWithoutForeground@RetailDemoUserAgent@@AEAAJPEBG0W4LaunchOptionsUA@@PEAUtagRECT@@@Z`
- size: `1345`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003e3b0`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x1800181b0`
- `0x18003873c`
- `0x18003d934`
- `0x18003e41c`
- `0x18003eca8`
- `0x180041ad4`
- `0x1800421cc`
- `0x180049698`
- `0x180050010`

## import_xrefs

- `USER32!GetForegroundWindow` at `0x18003e4a7`
- `USER32!GetForegroundWindow` at `0x18003e4a7`
- `USER32!SetWindowPos` at `0x18003e4d5`
- `USER32!SetWindowPos` at `0x18003e4d5`
- `USER32!LockSetForegroundWindow` at `0x18003e4e0`
- `USER32!LockSetForegroundWindow` at `0x18003e4e0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e46c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e46c`

## string_xrefs

- `0x18003e47f`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e51b`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e58a`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e647`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e6b9`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e7c2`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e837`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e8ab`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall RetailDemoUserAgent::LaunchAppWithoutForeground(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  HRESULT v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  HWND ForegroundWindow; // rax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, SID *, GUID *, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdi
  int (__fastcall *v28)(__int64, const unsigned __int16 *, __int64 *); // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  LPVOID v33; // rdi
  __int64 (__fastcall *v34)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r8
  char IsEnabled; // al
  __int64 v50; // rdx
  __int64 v51; // r8
  LPVOID v52; // rdi
  int (__fastcall *v53)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  RetailDemoUserAgent *v58; // rcx
  int v59; // eax
  RetailDemoUserAgent *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // r8
  int HwndForView; // eax
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // rdx
  __int64 v82; // r8
  int v83; // eax
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // rdx
  __int64 v99; // r8
  int ppv; // [rsp+20h] [rbp-61h]
  __int64 v102; // [rsp+40h] [rbp-41h] BYREF
  __int64 v103; // [rsp+48h] [rbp-39h] BYREF
  __int64 v104; // [rsp+50h] [rbp-31h] BYREF
  struct IApplicationView *v105; // [rsp+58h] [rbp-29h] BYREF
  __int64 v106; // [rsp+60h] [rbp-21h] BYREF
  LPVOID v107; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v108[2]; // [rsp+70h] [rbp-11h] BYREF
  char v109; // [rsp+80h] [rbp-1h]
  HWND v110; // [rsp+88h] [rbp+7h] BYREF
  HWND v111[8]; // [rsp+90h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]
  __int64 v113; // [rsp+E0h] [rbp+5Fh] BYREF

  v113 = a1;
  v107 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107, a2, a3);
  v8 = CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v107);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v110 = 0;
    LOBYTE(v9) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
      v9);
    ForegroundWindow = GetForegroundWindow();
    v110 = ForegroundWindow;
    if ( ForegroundWindow )
      SetWindowPos(ForegroundWindow, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x4013u);
    LockSetForegroundWindow(1u);
    v108[0] = &v110;
    v108[1] = &v107;
    v109 = 1;
    v14 = ActivateApplicationForLaunch(a2, a3, a2, 16777218);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v14,
        ppv);
      v109 = 0;
      lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
      goto LABEL_33;
    }
    v104 = 0;
    v103 = 0;
    v102 = 0;
    v17 = v107;
    v18 = *(__int64 (__fastcall **)(LPVOID, SID *, GUID *, __int64 *))(*(_QWORD *)v107 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v15, v16);
    v19 = v18(v17, &SID_ImmersiveApplicationArrayService, &GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a, &v102);
    v10 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D6,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
        (const char *)(unsigned int)v19,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v21, v22);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v23, v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v25, v26);
      v109 = 0;
      lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
      goto LABEL_33;
    }
    LOBYTE(v20) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
      v20);
    v27 = v102;
    v28 = *(int (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v102 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v29, v30);
    if ( v28(v27, a2, &v104) >= 0 )
    {
      v33 = v107;
      v34 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v107 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v31, v32);
      v35 = v34(v33, &IID_IImmersiveApplicationManager, &GUID_bf63999f_7411_40da_861c_df72c0ffee84, &v103);
      v10 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DE,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v35,
          ppv);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v36, v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v38, v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v40, v41);
        v109 = 0;
        lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
        goto LABEL_33;
      }
      ppv = 0;
      v42 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v103 + 56LL))(v103, v104, 0, 1);
      v10 = v42;
      if ( v42 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DF,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v42,
          0);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v43, v44);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v45, v46);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v47, v48);
        v109 = 0;
        lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
        goto LABEL_33;
      }
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality>::GetImpl'::`2'::impl);
    if ( !a5 && a4 != 4 )
    {
      if ( IsEnabled )
      {
        if ( a4 != 2 && a4 - 5 > 1 )
          goto LABEL_32;
      }
      else if ( a4 != 2 )
      {
        goto LABEL_32;
      }
    }
    v106 = 0;
    LODWORD(v113) = 0;
    v52 = v107;
    v53 = *(int (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v107 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106, v50, v51);
    if ( v53(v52, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a, &v106) < 0
      || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v106 + 24LL))(v106, &v113) < 0
      || (_DWORD)v113 != 1 )
    {
      LOBYTE(v54) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
        v54);
      v105 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105, v56, v57);
      v59 = RetailDemoUserAgent::WaitOnViewForAumid(v58, a2, &v105);
      v10 = v59;
      if ( v59 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x407,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v59,
          ppv);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105, v61, v62);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106, v63, v64);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v65, v66);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v67, v68);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v69, v70);
        v109 = 0;
        lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
        goto LABEL_33;
      }
      v111[0] = 0;
      HwndForView = RetailDemoUserAgent::GetHwndForView(v60, v105, v111);
      v10 = HwndForView;
      if ( HwndForView < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x409,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)HwndForView,
          ppv);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105, v73, v74);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106, v75, v76);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v77, v78);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v79, v80);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v81, v82);
        v109 = 0;
        lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
        goto LABEL_33;
      }
      v83 = RetailDemoUserAgent::MoveApplication(v72, v111, a5, a4);
      v10 = v83;
      if ( v83 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40A,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v83,
          ppv);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105, v86, v87);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106, v88, v89);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v90, v91);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v92, v93);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v94, v95);
        v109 = 0;
        lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
        goto LABEL_33;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105, v84, v85);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106, v54, v55);
LABEL_32:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102, v50, v51);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103, v96, v97);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104, v98, v99);
    v109 = 0;
    lambda_bcaf2436dda692779287984cad87a0fb_::operator()(v108);
    v10 = 0;
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x389,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
    (const char *)(unsigned int)v8,
    ppv);
LABEL_33:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107, v11, v12);
  return v10;
}

```

## disassembly

```asm
0x18003e41c  mov     [rsp-8+arg_0], rcx
0x18003e421  push    rbp
0x18003e422  push    rbx
0x18003e423  push    rsi
0x18003e424  push    rdi
0x18003e425  push    r12
0x18003e427  push    r15
0x18003e429  lea     rbp, [rsp-27h]
0x18003e42e  sub     rsp, 0A8h
0x18003e435  mov     esi, r9d
0x18003e438  mov     rdi, r8
0x18003e43b  mov     r15, rdx
0x18003e43e  xor     r12d, r12d
0x18003e441  mov     [rbp+4Fh+var_68], r12
0x18003e445  lea     rcx, [rbp+4Fh+var_68]
0x18003e449  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e44e  lea     rax, [rbp+4Fh+var_68]
0x18003e452  mov     [rsp+0D0h+ppv], rax; int
0x18003e457  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18003e45e  xor     edx, edx; pUnkOuter
0x18003e460  lea     r8d, [r12+4]; dwClsContext
0x18003e465  lea     rcx, CLSID_ImmersiveShell; rclsid
0x18003e46c  call    cs:__imp_CoCreateInstance
0x18003e472  mov     ebx, eax
0x18003e474  test    eax, eax
0x18003e476  jns     short loc_18003E495
0x18003e478  mov     rcx, [rbp+57h]; this
0x18003e47c  mov     r9d, eax; char *
0x18003e47f  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e486  mov     edx, 389h; void *
0x18003e48b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e490  jmp     loc_18003E942
0x18003e495  mov     [rbp+4Fh+var_48], r12
0x18003e499  mov     dl, 1
0x18003e49b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x18003e4a2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e4a7  call    cs:__imp_GetForegroundWindow
0x18003e4ad  mov     [rbp+4Fh+var_48], rax
0x18003e4b1  test    rax, rax
0x18003e4b4  jz      short loc_18003E4DB
0x18003e4b6  mov     [rsp+0D0h+uFlags], 4013h; uFlags
0x18003e4be  mov     [rsp+0D0h+cy], r12d; cy
0x18003e4c3  mov     dword ptr [rsp+0D0h+ppv], r12d; int
0x18003e4c8  xor     r9d, r9d; Y
0x18003e4cb  xor     r8d, r8d; X
0x18003e4ce  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18003e4d2  mov     rcx, rax; hWnd
0x18003e4d5  call    cs:__imp_SetWindowPos
0x18003e4db  mov     ecx, 1; uLockCode
0x18003e4e0  call    cs:__imp_LockSetForegroundWindow
0x18003e4e6  lea     rax, [rbp+4Fh+var_48]
0x18003e4ea  mov     [rbp+4Fh+var_60], rax
0x18003e4ee  lea     rax, [rbp+4Fh+var_68]
0x18003e4f2  mov     [rbp+4Fh+var_58], rax
0x18003e4f6  mov     [rbp+4Fh+var_50], 1
0x18003e4fa  mov     r9d, 1000002h
0x18003e500  mov     r8, r15
0x18003e503  mov     rdx, rdi
0x18003e506  mov     rcx, r15
0x18003e509  call    ?ActivateApplicationForLaunch@@YAJPEBG00W4ACTIVATEOPTIONSINTERNAL@@PEAUHMONITOR__@@PEAK@Z; ActivateApplicationForLaunch(ushort const *,ushort const *,ushort const *,ACTIVATEOPTIONSINTERNAL,HMONITOR__ *,ulong *)
0x18003e50e  mov     ebx, eax
0x18003e510  test    eax, eax
0x18003e512  jns     short loc_18003E540
0x18003e514  mov     rcx, [rbp+57h]; this
0x18003e518  mov     r9d, eax; char *
0x18003e51b  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e522  mov     edx, 3D0h; void *
0x18003e527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e52c  nop
0x18003e52d  mov     [rbp+4Fh+var_50], r12b
0x18003e531  lea     rcx, [rbp+4Fh+var_60]
0x18003e535  call    _lambda_bcaf2436dda692779287984cad87a0fb___operator__
0x18003e53a  nop
0x18003e53b  jmp     loc_18003E942
0x18003e540  mov     [rbp+4Fh+var_80], r12
0x18003e544  mov     [rbp+4Fh+var_88], r12
0x18003e548  mov     [rbp+4Fh+var_90], r12
0x18003e54c  mov     rdi, [rbp+4Fh+var_68]
0x18003e550  mov     rax, [rdi]
0x18003e553  mov     rbx, [rax+18h]
0x18003e557  lea     rcx, [rbp+4Fh+var_90]
0x18003e55b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e560  lea     r9, [rbp+4Fh+var_90]
0x18003e564  lea     r8, _GUID_a3c23ab7_6be2_4778_8eb0_1adb7977f76a
0x18003e56b  lea     rdx, SID_ImmersiveApplicationArrayService
0x18003e572  mov     rcx, rdi
0x18003e575  mov     rax, rbx
0x18003e578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e57d  mov     ebx, eax
0x18003e57f  test    eax, eax
0x18003e581  jns     short loc_18003E5CD
0x18003e583  mov     rcx, [rbp+57h]; this
0x18003e587  mov     r9d, eax; char *
0x18003e58a  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e591  mov     edx, 3D6h; void *
0x18003e596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e59b  nop
0x18003e59c  lea     rcx, [rbp+4Fh+var_90]
0x18003e5a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e5a5  nop
0x18003e5a6  lea     rcx, [rbp+4Fh+var_88]
0x18003e5aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e5af  nop
0x18003e5b0  lea     rcx, [rbp+4Fh+var_80]
0x18003e5b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e5b9  nop
0x18003e5ba  mov     [rbp+4Fh+var_50], r12b
0x18003e5be  lea     rcx, [rbp+4Fh+var_60]
0x18003e5c2  call    _lambda_bcaf2436dda692779287984cad87a0fb___operator__
0x18003e5c7  nop
0x18003e5c8  jmp     loc_18003E942
0x18003e5cd  mov     dl, 1
0x18003e5cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x18003e5d6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e5db  mov     rdi, [rbp+4Fh+var_90]
0x18003e5df  mov     rax, [rdi]
0x18003e5e2  mov     rbx, [rax+20h]
0x18003e5e6  lea     rcx, [rbp+4Fh+var_80]
0x18003e5ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e5ef  lea     r8, [rbp+4Fh+var_80]
0x18003e5f3  mov     rdx, r15
0x18003e5f6  mov     rcx, rdi
0x18003e5f9  mov     rax, rbx
0x18003e5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e601  test    eax, eax
0x18003e603  js      loc_18003E6FC
0x18003e609  mov     rdi, [rbp+4Fh+var_68]
0x18003e60d  mov     rax, [rdi]
0x18003e610  mov     rbx, [rax+18h]
0x18003e614  lea     rcx, [rbp+4Fh+var_88]
0x18003e618  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e61d  lea     r9, [rbp+4Fh+var_88]
0x18003e621  lea     r8, _GUID_bf63999f_7411_40da_861c_df72c0ffee84
0x18003e628  lea     rdx, IID_IImmersiveApplicationManager
0x18003e62f  mov     rcx, rdi
0x18003e632  mov     rax, rbx
0x18003e635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e63a  mov     ebx, eax
0x18003e63c  test    eax, eax
0x18003e63e  jns     short loc_18003E68A
0x18003e640  mov     rcx, [rbp+57h]; this
0x18003e644  mov     r9d, eax; char *
0x18003e647  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e64e  mov     edx, 3DEh; void *
0x18003e653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e658  nop
0x18003e659  lea     rcx, [rbp+4Fh+var_90]
0x18003e65d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e662  nop
0x18003e663  lea     rcx, [rbp+4Fh+var_88]
0x18003e667  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e66c  nop
0x18003e66d  lea     rcx, [rbp+4Fh+var_80]
0x18003e671  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e676  nop
0x18003e677  mov     [rbp+4Fh+var_50], r12b
0x18003e67b  lea     rcx, [rbp+4Fh+var_60]
0x18003e67f  call    _lambda_bcaf2436dda692779287984cad87a0fb___operator__
0x18003e684  nop
0x18003e685  jmp     loc_18003E942
0x18003e68a  mov     rcx, [rbp+4Fh+var_88]
0x18003e68e  mov     rax, [rcx]
0x18003e691  mov     [rsp+0D0h+ppv], r12; int
0x18003e696  mov     r9d, 1
0x18003e69c  xor     r8d, r8d
0x18003e69f  mov     rdx, [rbp+4Fh+var_80]
0x18003e6a3  mov     rax, [rax+38h]
0x18003e6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6ac  mov     ebx, eax
0x18003e6ae  test    eax, eax
0x18003e6b0  jns     short loc_18003E6FC
0x18003e6b2  mov     rcx, [rbp+57h]; this
0x18003e6b6  mov     r9d, eax; char *
0x18003e6b9  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e6c0  mov     edx, 3DFh; void *
0x18003e6c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e6ca  nop
0x18003e6cb  lea     rcx, [rbp+4Fh+var_90]
0x18003e6cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e6d4  nop
0x18003e6d5  lea     rcx, [rbp+4Fh+var_88]
0x18003e6d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e6de  nop
0x18003e6df  lea     rcx, [rbp+4Fh+var_80]
0x18003e6e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e6e8  nop
0x18003e6e9  mov     [rbp+4Fh+var_50], r12b
0x18003e6ed  lea     rcx, [rbp+4Fh+var_60]
0x18003e6f1  call    _lambda_bcaf2436dda692779287984cad87a0fb___operator__
0x18003e6f6  nop
0x18003e6f7  jmp     loc_18003E942
0x18003e6fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality> `wil::Feature<__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality>::GetImpl(void)'::`2'::impl
0x18003e703  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_Prelaunch_Functionality>::__private_IsEnabled(void)
0x18003e708  cmp     [rbp+4Fh+arg_20], r12
0x18003e70c  jnz     short loc_18003E733
0x18003e70e  cmp     esi, 4
0x18003e711  jz      short loc_18003E733
0x18003e713  test    al, al
0x18003e715  jz      short loc_18003E72A
0x18003e717  cmp     esi, 2
0x18003e71a  jz      short loc_18003E733
0x18003e71c  lea     eax, [rsi-5]
0x18003e71f  cmp     eax, 1
0x18003e722  ja      loc_18003E913
0x18003e728  jmp     short loc_18003E733
0x18003e72a  cmp     esi, 2
0x18003e72d  jnz     loc_18003E913
0x18003e733  mov     [rbp+4Fh+var_70], r12
0x18003e737  mov     dword ptr [rbp+4Fh+arg_0], r12d
0x18003e73b  mov     rdi, [rbp+4Fh+var_68]
0x18003e73f  mov     rax, [rdi]
0x18003e742  mov     rbx, [rax+18h]
0x18003e746  lea     rcx, [rbp+4Fh+var_70]
0x18003e74a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e74f  lea     r9, [rbp+4Fh+var_70]
0x18003e753  lea     rdx, _GUID_4fda780a_acd2_41f7_b4f2_ebe674c9bf2a
0x18003e75a  mov     r8, rdx
0x18003e75d  mov     rcx, rdi
0x18003e760  mov     rax, rbx
0x18003e763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e768  test    eax, eax
0x18003e76a  js      short loc_18003E78E
0x18003e76c  mov     rcx, [rbp+4Fh+var_70]
0x18003e770  mov     rax, [rcx]
0x18003e773  lea     rdx, [rbp+4Fh+arg_0]
0x18003e777  mov     rax, [rax+18h]
0x18003e77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e780  test    eax, eax
0x18003e782  js      short loc_18003E78E
0x18003e784  cmp     dword ptr [rbp+4Fh+arg_0], 1
0x18003e788  jz      loc_18003E909
0x18003e78e  mov     dl, 1
0x18003e790  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x18003e797  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e79c  mov     [rbp+4Fh+var_78], r12
0x18003e7a0  lea     rcx, [rbp+4Fh+var_78]
0x18003e7a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e7a9  lea     r8, [rbp+4Fh+var_78]; struct IApplicationView **
0x18003e7ad  mov     rdx, r15; unsigned __int16 *
0x18003e7b0  call    ?WaitOnViewForAumid@RetailDemoUserAgent@@AEAAJPEBGPEAPEAUIApplicationView@@@Z; RetailDemoUserAgent::WaitOnViewForAumid(ushort const *,IApplicationView * *)
0x18003e7b5  mov     ebx, eax
0x18003e7b7  test    eax, eax
0x18003e7b9  jns     short loc_18003E819
0x18003e7bb  mov     rcx, [rbp+57h]; this
0x18003e7bf  mov     r9d, eax; char *
0x18003e7c2  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e7c9  mov     edx, 407h; void *
0x18003e7ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e7d3  nop
0x18003e7d4  lea     rcx, [rbp+4Fh+var_78]
0x18003e7d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e7dd  nop
0x18003e7de  lea     rcx, [rbp+4Fh+var_70]
0x18003e7e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e7e7  nop
0x18003e7e8  lea     rcx, [rbp+4Fh+var_90]
0x18003e7ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e7f1  nop
0x18003e7f2  lea     rcx, [rbp+4Fh+var_88]
0x18003e7f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e7fb  nop
0x18003e7fc  lea     rcx, [rbp+4Fh+var_80]
0x18003e800  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e805  nop
0x18003e806  mov     [rbp+4Fh+var_50], r12b
0x18003e80a  lea     rcx, [rbp+4Fh+var_60]
0x18003e80e  call    _lambda_bcaf2436dda692779287984cad87a0fb___operator__
0x18003e813  nop
0x18003e814  jmp     loc_18003E942
0x18003e819  mov     [rbp+4Fh+var_40], r12
0x18003e81d  lea     r8, [rbp+4Fh+var_40]; HWND *
0x18003e821  mov     rdx, [rbp+4Fh+var_78]; struct IApplicationView *
0x18003e825  call    ?GetHwndForView@RetailDemoUserAgent@@AEAAJPEAUIApplicationView@@PEAPEAUHWND__@@@Z; RetailDemoUserAgent::GetHwndForView(IApplicationView *,HWND__ * *)
0x18003e82a  mov     ebx, eax
0x18003e82c  test    eax, eax
0x18003e82e  jns     short loc_18003E88E
0x18003e830  mov     rcx, [rbp+57h]; this
0x18003e834  mov     r9d, eax; char *
0x18003e837  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e83e  mov     edx, 409h; void *
0x18003e843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e848  nop
0x18003e849  lea     rcx, [rbp+4Fh+var_78]
0x18003e84d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e852  nop
0x18003e853  lea     rcx, [rbp+4Fh+var_70]
0x18003e857  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e85c  nop
0x18003e85d  lea     rcx, [rbp+4Fh+var_90]
0x18003e861  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e866  nop
0x18003e867  lea     rcx, [rbp+4Fh+var_88]
0x18003e86b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e870  nop
0x18003e871  lea     rcx, [rbp+4Fh+var_80]
0x18003e875  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e87a  nop
0x18003e87b  mov     [rbp+4Fh+var_50], r12b
0x18003e87f  lea     rcx, [rbp+4Fh+var_60]
0x18003e883  call    _lambda_bcaf2436dda692779287984cad87a0fb___operator__
  ... truncated ...
```
