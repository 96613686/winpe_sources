# Execution::ActivationManagerShim::ActivateViewForApplication(unsigned __int64,ushort const *,ushort const *,unsigned __int64,ACTIVATEOPTIONSINTERNAL,PACKAGEACTIVATIONSETTINGS,ActivationUserInfo const &,_GUID const &,bool,bool,ActivateType,IAAMActivation *,Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *,IInspectable *,uint *,IInspectable * *)

- ea: `0x180020060`
- end: `0x180020a61`
- name: `?ActivateViewForApplication@ActivationManagerShim@Execution@@IEAAJ_KPEBG10W4ACTIVATEOPTIONSINTERNAL@@W4PACKAGEACTIVATIONSETTINGS@@AEBUActivationUserInfo@@AEBU_GUID@@_N6W4ActivateType@@PEAUIAAMActivation@@PEAUIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIInspectable@@PEAIPEAPEAUIInspectable@@@Z`
- size: `2561`
- prototype: `int __high(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, enum ACTIVATEOPTIONSINTERNAL, enum PACKAGEACTIVATIONSETTINGS, const struct ActivationUserInfo *, const struct _GUID *, bool, bool, enum ActivateType, struct IAAMActivation *, struct Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *, struct IInspectable *, unsigned int *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006b040`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180015b7c`
- `0x1800169e4`
- `0x18001ff10`
- `0x180020060`
- `0x180020a68`
- `0x1800210bc`
- `0x180021790`
- `0x180024770`
- `0x180024840`
- `0x18003dd90`
- `0x18005ae90`
- `0x18006e294`
- `0x1800827ac`
- `0x18008442c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002010e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020138`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020162`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002018c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800201b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800201e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002020a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020234`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002025a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002010e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020138`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020162`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002018c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800201b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800201e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002020a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180020234`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002025a`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x1800208af`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x1800208af`

## string_xrefs

- `0x180020101`: `Windows.ComponentUI`
- `0x1800201a9`: `Windows.GameBarUIExtension`
- `0x1800201d3`: `Windows.FileOpenPicker`
- `0x180020227`: `Windows.CachedFileUpdater`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Execution::ActivationManagerShim::ActivateViewForApplication(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        unsigned __int64 a5,
        unsigned int a6,
        char a7,
        __int64 a8,
        __int128 *a9,
        unsigned __int8 a10,
        char a11,
        __int64 a12,
        __int64 a13,
        __int64 (__fastcall ***a14)(_QWORD, GUID *, unsigned int *),
        __int64 a15,
        _DWORD *a16,
        _QWORD *a17)
{
  _DWORD *v19; // r13
  __int64 (__fastcall *v20)(_QWORD, GUID *, unsigned int *); // rbx
  int v21; // r12d
  bool v22; // r12
  int v23; // esi
  unsigned int (__fastcall *v24)(_QWORD, GUID *, unsigned int *); // rbx
  int v25; // eax
  unsigned int v26; // ecx
  unsigned int *v27; // rdx
  unsigned int v28; // eax
  int v29; // ecx
  int v30; // eax
  int v31; // ebx
  __int64 v32; // rcx
  int RPCClientProcessId; // eax
  unsigned int v34; // ebx
  __int64 (__fastcall *v36)(_QWORD, GUID *, __int64 *); // rbx
  int v37; // eax
  unsigned int v38; // ebx
  unsigned __int64 v39; // rbx
  int Instance; // eax
  unsigned int v41; // ebx
  int v42; // eax
  __int64 v43; // rcx
  struct IViewActivatorHelper *v44; // rsi
  __int64 (__fastcall *v45)(struct IViewActivatorHelper *, _QWORD *, __int64 *); // rbx
  int v46; // eax
  unsigned int v47; // ebx
  __int64 v48; // rcx
  struct IViewActivatorHelper *v49; // rcx
  __int64 v50; // rcx
  struct IViewActivatorHelper *v51; // rbx
  unsigned __int64 v52; // rdx
  unsigned __int8 v53; // cl
  AAMTraceProvider *v54; // rcx
  int v55; // eax
  unsigned int v56; // ebx
  bool v57; // bl
  int v58; // ecx
  __int64 v59; // r12
  unsigned int v60; // r15d
  IUnknown *v61; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rdi
  unsigned int v63; // eax
  IUnknown *v64; // rcx
  __int64 v65; // rcx
  struct IViewActivatorHelper *v66; // rcx
  __int64 v67; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v69; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v70[7]; // [rsp+61h] [rbp-9Fh] BYREF
  __int64 v71; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v72[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v73; // [rsp+78h] [rbp-88h] BYREF
  struct IViewActivatorHelper *v74; // [rsp+80h] [rbp-80h] BYREF
  IUnknown *pUnk; // [rsp+88h] [rbp-78h] BYREF
  int v76; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v77; // [rsp+98h] [rbp-68h]
  __int128 *v78; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-58h]
  _DWORD *v80; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v81; // [rsp+B8h] [rbp-48h]
  _QWORD *v82; // [rsp+C0h] [rbp-40h]
  __int128 v83; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v84; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v85; // [rsp+E8h] [rbp-18h]
  int *v86; // [rsp+F0h] [rbp-10h]
  _QWORD v87[2]; // [rsp+F8h] [rbp-8h] BYREF
  char v88; // [rsp+108h] [rbp+8h]
  __int64 v89; // [rsp+110h] [rbp+10h]
  _QWORD v90[6]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v91; // [rsp+150h] [rbp+50h]
  unsigned int v92; // [rsp+160h] [rbp+60h]
  int v93; // [rsp+164h] [rbp+64h]
  int v94; // [rsp+168h] [rbp+68h]
  int v95; // [rsp+16Ch] [rbp+6Ch]
  __int64 v96; // [rsp+170h] [rbp+70h]
  __int64 v97; // [rsp+178h] [rbp+78h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v79 = a3;
  v77 = a2;
  v81 = a8;
  v78 = a9;
  v89 = a13;
  *(_QWORD *)&v83 = a15;
  v80 = a16;
  v82 = a17;
  v19 = (_DWORD *)(a1 + 144);
  *(_DWORD *)(a1 + 144) = 4;
  if ( CompareStringOrdinal(a4, -1, L"Windows.ComponentUI", -1, 1) == 2
    || CompareStringOrdinal(a4, -1, L"Windows.OopWebView", -1, 1) == 2
    || CompareStringOrdinal(a4, -1, L"Windows.PeoplePane", -1, 1) == 2
    || CompareStringOrdinal(a4, -1, L"Windows.ContactPanel", -1, 1) == 2
    || CompareStringOrdinal(a4, -1, L"Windows.GameBarUIExtension", -1, 1) == 2
    || CompareStringOrdinal(a4, -1, L"Windows.FileOpenPicker", -1, 1) == 2
    || CompareStringOrdinal(a4, -1, L"Windows.FileSavePicker", -1, 1) == 2
    || CompareStringOrdinal(a4, -1, L"Windows.CachedFileUpdater", -1, 1) == 2 )
  {
    v22 = 1;
  }
  else if ( CompareStringOrdinal(a4, -1, L"Windows.ShareTarget", -1, 1) == 2 )
  {
    *(_QWORD *)v72 = 0;
    v20 = **a14;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v72);
    v21 = v20(a14, &GUID_88142b7c_1ba3_4f41_b143_8404272b2d4d, v72);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v72);
    v22 = v21 >= 0;
  }
  else
  {
    v22 = 0;
  }
  v70[0] = 0;
  v69 = 0;
  ViewActivator::ReadProperties(a1 + 136, v70, &v69);
  v23 = *(_DWORD *)(a1 + 112);
  *(_QWORD *)v72 = 0;
  if ( a14 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, unsigned int *)))(*a14)[1])(a14);
  v24 = (unsigned int (__fastcall *)(_QWORD, GUID *, unsigned int *))**a14;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v72);
  LODWORD(v24) = v24(a14, &GUID_7ca84d06_f54c_4ba8_bd6f_9abaf9380d51, v72) >> 31;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, unsigned int *)))(*a14)[2])(a14);
  v25 = v23 | 0x40;
  if ( (unsigned __int8)v24 == 1 )
    v25 = v23;
  if ( v22 || (a6 & 0x50000000) != 0 )
    v25 |= 0x10u;
  v26 = v25 | 0x400;
  if ( !v22 )
    v26 = v25;
  v27 = (unsigned int *)v26;
  LODWORD(v27) = v26 | 0x80;
  if ( (a6 & 0x200000) == 0 )
    v27 = (unsigned int *)v26;
  v28 = (unsigned int)v27 | 8;
  if ( !a10 )
    v28 = (unsigned int)v27;
  v29 = v28 | 0x100;
  if ( a11 )
    v29 = v28;
  v30 = v29 | 0xA00;
  if ( !v70[0] )
    v30 = v29;
  v31 = v30 | 0x1000;
  if ( !v69 )
    v31 = v30;
  v32 = *(_QWORD *)v72;
  if ( *(_QWORD *)v72 )
  {
    *(_QWORD *)v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  *(_DWORD *)(a1 + 112) = v31;
  *v80 = -1;
  if ( v82 )
    *v82 = 0;
  if ( !*(_DWORD *)(a1 + 104) && !*(_DWORD *)(a1 + 108) )
  {
    RPCClientProcessId = DevPlat::Shared::GetRPCClientProcessId((DevPlat::Shared *)(a1 + 108), v27);
    v34 = RPCClientProcessId;
    if ( RPCClientProcessId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AD,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)RPCClientProcessId,
        bIgnoreCase);
      return v34;
    }
  }
  v71 = 0;
  if ( a10 && (_QWORD)v83 )
  {
    v36 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v83;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
    v37 = v36(v83, &GUID_cd292360_2763_4085_8a9f_74b224a29175, &v71);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B3,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)v37,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
      return v38;
    }
    v39 = a5;
    goto LABEL_45;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
  v83 = *v78;
  bIgnoreCase = (int)a4;
  v39 = a5;
  v42 = ViewActivator::CreateCoreWindowFactory(v77, v79, &v83, a5);
  v72[0] = v42;
  if ( v42 >= 0 )
  {
LABEL_45:
    v90[0] = v77;
    v90[1] = *(_QWORD *)(v81 + 8);
    v90[2] = *(_QWORD *)(v81 + 16);
    v90[3] = v79;
    v90[4] = a4;
    v91 = *v78;
    v92 = a6;
    v94 = *(_DWORD *)(a1 + 104);
    v95 = *(_DWORD *)(a1 + 108);
    v96 = *(_QWORD *)(a1 + 136);
    v97 = v71;
    v93 = *(_DWORD *)(a1 + 112);
    v90[5] = v39;
    v74 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
    Instance = ViewActivator::GetInstance(&v74);
    v41 = Instance;
    if ( Instance >= 0 )
    {
      v73 = 0;
      v44 = v74;
      v45 = *(__int64 (__fastcall **)(struct IViewActivatorHelper *, _QWORD *, __int64 *))(*(_QWORD *)v74 + 24LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
      v46 = v45(v44, v90, &v73);
      v47 = v46;
      if ( v46 >= 0 )
      {
        v76 = 3;
        v84 = v77;
        v85 = a5;
        v86 = &v76;
        v51 = v74;
        v87[0] = v74;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v87);
        v84 = v77;
        v85 = a5;
        v86 = &v76;
        v87[0] = v51;
        v87[1] = &v80;
        v88 = 1;
        v69 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 40LL))(v73);
        if ( v69 )
          *(_DWORD *)(a1 + 204) |= 0x10u;
        if ( (unsigned __int8)IsActivateAheadAllowed(a6) && !v69 && !a10 )
          goto LABEL_68;
        v72[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 48LL))(v73);
        if ( AAMTraceProvider::IsEnabled(v53, v52) )
        {
          AAMTraceProvider::Instance();
          AAMTraceProvider::ForcedWaitForViewComplete_(v54, v77, a5, v72[0], a6, v69, a10);
        }
        *v19 = 4;
        v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 24LL))(v73);
        v56 = v55;
        if ( v55 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E6,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
            (const char *)(unsigned int)v55,
            bIgnoreCase);
          wil::details::ScopeExitFn__lambda_759863519078f575db8ceafa717fe3bf___::_ScopeExitFn__lambda_759863519078f575db8ceafa717fe3bf___(&v84);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
          return v56;
        }
        else
        {
LABEL_68:
          *v19 = 32;
          v57 = 0;
          pUnk = 0;
          if ( a10 && v71 && (a6 & 4) == 0 )
          {
            v58 = (a6 >> 19) & 0x20 | 0x10;
            if ( (a7 & 2) == 0 )
              v58 = (a6 >> 19) & 0x20;
            v72[0] = v58;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pUnk);
            if ( (int)CreateLegacySplashScreen(v79, v72[0], v71, &pUnk) < 0 )
              v57 = (a6 & 0x1010000) == 0;
            if ( pUnk )
            {
              v78 = 0;
              CoAllowSetForegroundWindow(pUnk, 0);
              ((void (__fastcall *)(IUnknown *, const WCHAR *, _QWORD, __int128 **))pUnk->lpVtbl[1].AddRef)(
                pUnk,
                a4,
                v72[0],
                &v78);
            }
          }
          v59 = v89;
          v60 = (*(__int64 (__fastcall **)(__int64, bool, __int64 (__fastcall ***)(_QWORD, GUID *, unsigned int *), __int64))(*(_QWORD *)v89 + 32LL))(
                  v89,
                  v57,
                  a14,
                  v73);
          v61 = pUnk;
          if ( pUnk )
          {
            Release = pUnk->lpVtbl[1].Release;
            v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 48LL))(v59);
            ((void (__fastcall *)(IUnknown *, _QWORD, _QWORD))Release)(v61, v60, v63);
          }
          if ( (v60 & 0x80000000) == 0 )
          {
            (*(void (__fastcall **)(struct IViewActivatorHelper *, unsigned __int64, unsigned __int64, _DWORD *, __int64))(*(_QWORD *)v74 + 48LL))(
              v74,
              v77,
              a5,
              v80,
              a1 + 152);
            v88 = 0;
            v64 = pUnk;
            if ( pUnk )
            {
              pUnk = 0;
              ((void (__fastcall *)(IUnknown *))v64->lpVtbl->Release)(v64);
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v87);
            v65 = v73;
            if ( v73 )
            {
              v73 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
            }
            v66 = v74;
            if ( v74 )
            {
              v74 = 0;
              (*(void (__fastcall **)(struct IViewActivatorHelper *))(*(_QWORD *)v66 + 16LL))(v66);
            }
            v67 = v71;
            if ( v71 )
            {
              v71 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
            }
            return 0;
          }
          else
          {
            v76 = HamTerminateTypeFromHRESULT(v60);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x614,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
              (const char *)v60,
              (int)v19);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pUnk);
            wil::details::ScopeExitFn__lambda_759863519078f575db8ceafa717fe3bf___::_ScopeExitFn__lambda_759863519078f575db8ceafa717fe3bf___(&v84);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
            return v60;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5CF,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
          (const char *)(unsigned int)v46,
          bIgnoreCase);
        v48 = v73;
        if ( v73 )
        {
          v73 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        }
        v49 = v74;
        if ( v74 )
        {
          v74 = 0;
          (*(void (__fastcall **)(struct IViewActivatorHelper *))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v50 = v71;
        if ( v71 )
        {
          v71 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        }
        return v47;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CC,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)Instance,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
      return v41;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B7,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
    (const char *)(unsigned int)v42,
    (int)a4);
  v43 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  return v72[0];
}

```

## disassembly

```asm
0x180020060  push    rbp
0x180020062  push    rbx
0x180020063  push    rsi
0x180020064  push    rdi
0x180020065  push    r12
0x180020067  push    r13
0x180020069  push    r14
0x18002006b  push    r15
0x18002006d  lea     rbp, [rsp-98h]
0x180020075  sub     rsp, 198h
0x18002007c  mov     rax, cs:__security_cookie
0x180020083  xor     rax, rsp
0x180020086  mov     [rbp+0D0h+var_50], rax
0x18002008d  mov     rdi, r9
0x180020090  mov     [rbp+0D0h+var_128], r8
0x180020094  mov     [rbp+0D0h+var_138], rdx
0x180020098  mov     r14, rcx
0x18002009b  mov     rax, [rbp+0D0h+arg_38]
0x1800200a2  mov     [rbp+0D0h+var_118], rax
0x1800200a6  mov     rax, [rbp+0D0h+arg_40]
0x1800200ad  mov     [rbp+0D0h+var_130], rax
0x1800200b1  mov     rax, [rbp+0D0h+arg_60]
0x1800200b8  mov     [rbp+0D0h+var_C0], rax
0x1800200bc  mov     r15, [rbp+0D0h+arg_68]
0x1800200c3  mov     rax, [rbp+0D0h+arg_70]
0x1800200ca  mov     qword ptr [rbp+0D0h+var_100], rax
0x1800200ce  mov     rax, [rbp+0D0h+arg_78]
0x1800200d5  mov     [rbp+0D0h+var_120], rax
0x1800200d9  mov     rax, [rbp+0D0h+arg_80]
0x1800200e0  mov     [rbp+0D0h+var_110], rax
0x1800200e4  lea     r13, [rcx+90h]
0x1800200eb  mov     dword ptr [r13+0], 4
0x1800200f3  mov     [rsp+1D0h+bIgnoreCase], 1; int
0x1800200fb  mov     r9d, 0FFFFFFFFh; cchCount2
0x180020101  lea     r8, aWindowsCompone; "Windows.ComponentUI"
0x180020108  mov     edx, r9d; cchCount1
0x18002010b  mov     rcx, rdi; lpString1
0x18002010e  call    cs:__imp_CompareStringOrdinal
0x180020114  cmp     eax, 2
0x180020117  jz      loc_1800202B1
0x18002011d  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x180020125  mov     r9d, 0FFFFFFFFh; cchCount2
0x18002012b  lea     r8, aWindowsOopwebv; "Windows.OopWebView"
0x180020132  mov     edx, r9d; cchCount1
0x180020135  mov     rcx, rdi; lpString1
0x180020138  call    cs:__imp_CompareStringOrdinal
0x18002013e  cmp     eax, 2
0x180020141  jz      loc_1800202B1
0x180020147  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x18002014f  mov     r9d, 0FFFFFFFFh; cchCount2
0x180020155  lea     r8, aWindowsPeoplep; "Windows.PeoplePane"
0x18002015c  mov     edx, r9d; cchCount1
0x18002015f  mov     rcx, rdi; lpString1
0x180020162  call    cs:__imp_CompareStringOrdinal
0x180020168  cmp     eax, 2
0x18002016b  jz      loc_1800202B1
0x180020171  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x180020179  mov     r9d, 0FFFFFFFFh; cchCount2
0x18002017f  lea     r8, aWindowsContact; "Windows.ContactPanel"
0x180020186  mov     edx, r9d; cchCount1
0x180020189  mov     rcx, rdi; lpString1
0x18002018c  call    cs:__imp_CompareStringOrdinal
0x180020192  cmp     eax, 2
0x180020195  jz      loc_1800202B1
0x18002019b  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x1800201a3  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800201a9  lea     r8, aWindowsGamebar; "Windows.GameBarUIExtension"
0x1800201b0  mov     edx, r9d; cchCount1
0x1800201b3  mov     rcx, rdi; lpString1
0x1800201b6  call    cs:__imp_CompareStringOrdinal
0x1800201bc  cmp     eax, 2
0x1800201bf  jz      loc_1800202B1
0x1800201c5  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x1800201cd  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800201d3  lea     r8, aWindowsFileope; "Windows.FileOpenPicker"
0x1800201da  mov     edx, r9d; cchCount1
0x1800201dd  mov     rcx, rdi; lpString1
0x1800201e0  call    cs:__imp_CompareStringOrdinal
0x1800201e6  cmp     eax, 2
0x1800201e9  jz      loc_1800202B1
0x1800201ef  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x1800201f7  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800201fd  lea     r8, aWindowsFilesav; "Windows.FileSavePicker"
0x180020204  mov     edx, r9d; cchCount1
0x180020207  mov     rcx, rdi; lpString1
0x18002020a  call    cs:__imp_CompareStringOrdinal
0x180020210  cmp     eax, 2
0x180020213  jz      loc_1800202B1
0x180020219  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x180020221  mov     r9d, 0FFFFFFFFh; cchCount2
0x180020227  lea     r8, aWindowsCachedf; "Windows.CachedFileUpdater"
0x18002022e  mov     edx, r9d; cchCount1
0x180020231  mov     rcx, rdi; lpString1
0x180020234  call    cs:__imp_CompareStringOrdinal
0x18002023a  cmp     eax, 2
0x18002023d  jz      short loc_1800202B1
0x18002023f  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x180020247  mov     r9d, 0FFFFFFFFh; cchCount2
0x18002024d  lea     r8, aWindowsShareta; "Windows.ShareTarget"
0x180020254  mov     edx, r9d; cchCount1
0x180020257  mov     rcx, rdi; lpString1
0x18002025a  call    cs:__imp_CompareStringOrdinal
0x180020260  cmp     eax, 2
0x180020263  jnz     short loc_1800202AC
0x180020265  mov     qword ptr [rsp+1D0h+var_160], 0
0x18002026e  mov     rax, [r15]
0x180020271  mov     rbx, [rax]
0x180020274  lea     rcx, [rsp+1D0h+var_160]
0x180020279  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002027e  lea     r8, [rsp+1D0h+var_160]
0x180020283  lea     rdx, _GUID_88142b7c_1ba3_4f41_b143_8404272b2d4d
0x18002028a  mov     rcx, r15
0x18002028d  mov     rax, rbx
0x180020290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020295  mov     r12d, eax
0x180020298  lea     rcx, [rsp+1D0h+var_160]
0x18002029d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800202a2  shr     r12d, 1Fh
0x1800202a6  xor     r12b, 1
0x1800202aa  jmp     short loc_1800202B4
0x1800202ac  xor     r12b, r12b
0x1800202af  jmp     short loc_1800202B4
0x1800202b1  mov     r12b, 1
0x1800202b4  mov     [rsp+1D0h+var_16F], 0
0x1800202b9  mov     [rsp+1D0h+var_170], 0
0x1800202be  lea     rcx, [r14+88h]
0x1800202c5  lea     r8, [rsp+1D0h+var_170]
0x1800202ca  lea     rdx, [rsp+1D0h+var_16F]
0x1800202cf  call    ?ReadProperties@ViewActivator@@SAXAEAV?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@PEA_N1@Z; ViewActivator::ReadProperties(Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer> &,bool *,bool *)
0x1800202d4  mov     esi, [r14+70h]
0x1800202d8  mov     qword ptr [rsp+1D0h+var_160], 0
0x1800202e1  test    r15, r15
0x1800202e4  jz      short loc_1800202F6
0x1800202e6  mov     rax, [r15]
0x1800202e9  mov     rcx, r15
0x1800202ec  mov     rax, [rax+8]
0x1800202f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202f5  nop
0x1800202f6  mov     rax, [r15]
0x1800202f9  mov     rbx, [rax]
0x1800202fc  lea     rcx, [rsp+1D0h+var_160]
0x180020301  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020306  lea     r8, [rsp+1D0h+var_160]
0x18002030b  lea     rdx, _GUID_7ca84d06_f54c_4ba8_bd6f_9abaf9380d51
0x180020312  mov     rcx, r15
0x180020315  mov     rax, rbx
0x180020318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002031d  mov     ebx, eax
0x18002031f  shr     ebx, 1Fh
0x180020322  mov     rcx, [r15]
0x180020325  mov     rax, [rcx+10h]
0x180020329  mov     rcx, r15
0x18002032c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020331  nop
0x180020332  mov     eax, esi
0x180020334  or      eax, 40h
0x180020337  xor     bl, 1
0x18002033a  cmovz   eax, esi
0x18002033d  mov     esi, [rbp+0D0h+arg_28]
0x180020343  test    r12b, r12b
0x180020346  jnz     short loc_180020350
0x180020348  test    esi, 50000000h
0x18002034e  jz      short loc_180020353
0x180020350  or      eax, 10h
0x180020353  mov     ecx, eax
0x180020355  bts     ecx, 0Ah
0x180020359  test    r12b, r12b
0x18002035c  cmovz   ecx, eax
0x18002035f  mov     edx, ecx
0x180020361  bts     edx, 7
0x180020365  bt      esi, 15h
0x180020369  cmovnb  edx, ecx
0x18002036c  movzx   r12d, [rbp+0D0h+arg_48]
0x180020374  mov     eax, edx
0x180020376  or      eax, 8
0x180020379  test    r12b, r12b
0x18002037c  cmovz   eax, edx
0x18002037f  mov     ecx, eax
0x180020381  bts     ecx, 8
0x180020385  cmp     [rbp+0D0h+arg_50], 0
0x18002038c  cmovnz  ecx, eax
0x18002038f  mov     eax, ecx
0x180020391  or      eax, 0A00h
0x180020396  cmp     [rsp+1D0h+var_16F], 0
0x18002039b  cmovz   eax, ecx
0x18002039e  mov     ebx, eax
0x1800203a0  bts     ebx, 0Ch
0x1800203a4  cmp     [rsp+1D0h+var_170], 0
0x1800203a9  cmovz   ebx, eax
0x1800203ac  mov     rcx, qword ptr [rsp+1D0h+var_160]
0x1800203b1  test    rcx, rcx
0x1800203b4  jz      short loc_1800203CC
0x1800203b6  mov     qword ptr [rsp+1D0h+var_160], 0
0x1800203bf  mov     rax, [rcx]
0x1800203c2  mov     rax, [rax+10h]
0x1800203c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203cb  nop
0x1800203cc  mov     [r14+70h], ebx
0x1800203d0  mov     rax, [rbp+0D0h+var_120]
0x1800203d4  mov     dword ptr [rax], 0FFFFFFFFh
0x1800203da  mov     rax, [rbp+0D0h+var_110]
0x1800203de  test    rax, rax
0x1800203e1  jz      short loc_1800203EA
0x1800203e3  mov     qword ptr [rax], 0
0x1800203ea  cmp     dword ptr [r14+68h], 0
0x1800203ef  jnz     short loc_180020427
0x1800203f1  lea     rcx, [r14+6Ch]; this
0x1800203f5  cmp     dword ptr [rcx], 0
0x1800203f8  jnz     short loc_180020427
0x1800203fa  call    ?GetRPCClientProcessId@Shared@DevPlat@@YAJPEAK@Z; DevPlat::Shared::GetRPCClientProcessId(ulong *)
0x1800203ff  mov     ebx, eax
0x180020401  test    eax, eax
0x180020403  jns     short loc_180020427
0x180020405  mov     rcx, [rbp+0D8h]; this
0x18002040c  mov     r9d, eax; char *
0x18002040f  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180020416  mov     edx, 5ADh; void *
0x18002041b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020420  mov     eax, ebx
0x180020422  jmp     loc_180020A3E
0x180020427  mov     [rsp+1D0h+var_168], 0
0x180020430  test    r12b, r12b
0x180020433  jz      loc_180020564
0x180020439  mov     rax, qword ptr [rbp+0D0h+var_100]
0x18002043d  test    rax, rax
0x180020440  jz      loc_180020564
0x180020446  mov     rax, [rax]
0x180020449  mov     rbx, [rax]
0x18002044c  lea     rcx, [rsp+1D0h+var_168]
0x180020451  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020456  lea     r8, [rsp+1D0h+var_168]
0x18002045b  lea     rdx, _GUID_cd292360_2763_4085_8a9f_74b224a29175
0x180020462  mov     rcx, qword ptr [rbp+0D0h+var_100]
0x180020466  mov     rax, rbx
0x180020469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002046e  mov     ebx, eax
0x180020470  test    eax, eax
0x180020472  jns     short loc_1800204A1
0x180020474  mov     rcx, [rbp+0D8h]; this
0x18002047b  mov     r9d, eax; char *
0x18002047e  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180020485  mov     edx, 5B3h; void *
0x18002048a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002048f  nop
0x180020490  lea     rcx, [rsp+1D0h+var_168]
0x180020495  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002049a  mov     eax, ebx
0x18002049c  jmp     loc_180020A3E
0x1800204a1  mov     rbx, [rbp+0D0h+arg_20]
0x1800204a8  mov     rax, [rbp+0D0h+var_138]
0x1800204ac  mov     [rbp+0D0h+var_B0], rax
0x1800204b0  mov     rcx, [rbp+0D0h+var_118]
0x1800204b4  mov     rax, [rcx+8]
0x1800204b8  mov     [rbp+0D0h+var_A8], rax
0x1800204bc  mov     rax, [rcx+10h]
0x1800204c0  mov     [rbp+0D0h+var_A0], rax
0x1800204c4  mov     rax, [rbp+0D0h+var_128]
0x1800204c8  mov     [rbp+0D0h+var_98], rax
0x1800204cc  mov     [rbp+0D0h+var_90], rdi
0x1800204d0  mov     rax, [rbp+0D0h+var_130]
0x1800204d4  movups  xmm0, xmmword ptr [rax]
0x1800204d7  movaps  [rbp+0D0h+var_80], xmm0
0x1800204db  mov     [rbp+0D0h+var_70], esi
0x1800204de  mov     eax, [r14+68h]
0x1800204e2  mov     [rbp+0D0h+var_68], eax
0x1800204e5  mov     eax, [r14+6Ch]
0x1800204e9  mov     [rbp+0D0h+var_64], eax
0x1800204ec  mov     rax, [r14+88h]
0x1800204f3  mov     [rbp+0D0h+var_60], rax
0x1800204f7  mov     rax, [rsp+1D0h+var_168]
0x1800204fc  mov     [rbp+0D0h+var_58], rax
0x180020500  mov     eax, [r14+70h]
0x180020504  mov     [rbp+0D0h+var_6C], eax
0x180020507  mov     [rbp+0D0h+var_88], rbx
0x18002050b  xor     esi, esi
0x18002050d  mov     [rbp+0D0h+var_150], rsi
0x180020511  lea     rcx, [rbp+0D0h+var_150]
0x180020515  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002051a  lea     rcx, [rbp+0D0h+var_150]; struct IViewActivatorHelper **
0x18002051e  call    ?GetInstance@ViewActivator@@SAJPEAPEAUIViewActivatorHelper@@@Z; ViewActivator::GetInstance(IViewActivatorHelper * *)
0x180020523  mov     ebx, eax
0x180020525  test    eax, eax
0x180020527  jns     loc_18002062A
0x18002052d  mov     rcx, [rbp+0D8h]; this
0x180020534  mov     r9d, eax; char *
0x180020537  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002053e  mov     edx, 5CCh; void *
0x180020543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020548  nop
0x180020549  lea     rcx, [rbp+0D0h+var_150]
0x18002054d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020552  nop
0x180020553  lea     rcx, [rsp+1D0h+var_168]
0x180020558  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002055d  mov     eax, ebx
0x18002055f  jmp     loc_180020A3E
0x180020564  lea     rcx, [rsp+1D0h+var_168]
0x180020569  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002056e  mov     rax, [rbp+0D0h+var_130]
0x180020572  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
