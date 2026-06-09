# _lambda_e1f13c38772327f39a5e0eaf753ddbac_::operator()

- ea: `0x18006bcf8`
- end: `0x18006c489`
- name: `_lambda_e1f13c38772327f39a5e0eaf753ddbac_::operator()`
- size: `1937`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006fba0`

## callees

- `0x18000abf0`
- `0x18000b5c0`
- `0x180011328`
- `0x180014040`
- `0x180015b7c`
- `0x1800210bc`
- `0x180021790`
- `0x180027c60`
- `0x180031590`
- `0x180032d40`
- `0x1800352dc`
- `0x1800367e4`
- `0x180038190`
- `0x180038c70`
- `0x18003dc20`
- `0x180041768`
- `0x180043f90`
- `0x18004fc3c`
- `0x18005ae90`
- `0x18005ba40`
- `0x18006871c`
- `0x18006bcf8`
- `0x18006e4f8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bd7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bde8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006be5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bebf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c45e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bd7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bde8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006be5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bebf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c45e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006bfc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006bfc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall lambda_e1f13c38772327f39a5e0eaf753ddbac_::operator()(__int64 a1)
{
  __int64 v2; // rdx
  const unsigned __int16 *v4; // rdx
  unsigned __int16 **v5; // r9
  int v6; // eax
  int v7; // ebx
  LPCWSTR v8; // rbx
  const struct _GUID *v9; // r8
  int PsmKey; // eax
  unsigned __int64 *v11; // rdx
  unsigned int v12; // edi
  unsigned __int16 *v13; // rdi
  int HostIdForSingleInstanceFgActivation; // esi
  __int64 v15; // rdx
  __int64 v16; // rdx
  HSTRING v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rdx
  Execution::ActivationManagerShim *v20; // r11
  __int64 v21; // rsi
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // r14
  __int64 (__fastcall *v25)(__int64, _QWORD *, _QWORD, __int64 *); // rsi
  __int64 v26; // rdx
  _QWORD *v27; // rsi
  _QWORD *v28; // rbx
  __int64 *v29; // rdi
  _QWORD *v30; // r14
  _QWORD *v31; // r15
  __int64 v32; // rdx
  unsigned __int16 **v33; // [rsp+20h] [rbp-E0h]
  struct Windows::Foundation::IExtensionRegistration **v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  struct Windows::Foundation::IExtensionRegistration **v37; // [rsp+20h] [rbp-E0h]
  bool v38; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpValue; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v40; // [rsp+80h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-50h] BYREF
  int v47; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v48; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING string[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v50; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+E8h] [rbp-18h] BYREF
  __int128 *v52; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v53; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR v54[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v55[6]; // [rsp+110h] [rbp+10h] BYREF
  GUID v56; // [rsp+140h] [rbp+40h]
  int v57; // [rsp+150h] [rbp+50h]
  int v58; // [rsp+154h] [rbp+54h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  _OWORD v60[2]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  CAutoSRWExclusiveLock::CAutoSRWExclusiveLock(
    (CAutoSRWExclusiveLock *)&SRWLock,
    (struct CSRWLock *)(*(_QWORD *)a1 + 96LL));
  if ( **(_DWORD **)(a1 + 8) )
  {
    v2 = 233;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)0x80070057LL,
      (int)v33);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147942487LL;
  }
  if ( **(_QWORD **)(a1 + 16) )
  {
    v2 = 234;
    goto LABEL_5;
  }
  lpValue = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (void **)&lpValue,
    0);
  v6 = DevPlat::Shared::PraidAndPackageInfoFromAppId(**(PCWSTR **)(a1 + 24), v4, (unsigned __int16 **)&lpValue, v5, v33);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v6,
      (int)v34);
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpValue);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return (unsigned int)v7;
  }
  v40 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (void **)&v40,
    0);
  v8 = lpValue;
  PsmKey = Execution::ActivationManagerShim::GetPsmKey(**(const unsigned __int16 ***)(a1 + 24), lpValue, v9, &v40);
  v12 = PsmKey;
  if ( PsmKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)PsmKey,
      (int)v34);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v40);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpValue);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return v12;
  }
  v13 = v40;
  HostIdForSingleInstanceFgActivation = Execution::ActivationManagerShim::GetHostIdForSingleInstanceFgActivation(
                                          *(Execution::ActivationManagerShim **)a1,
                                          v11,
                                          v40,
                                          *(unsigned __int64 **)(a1 + 32));
  if ( HostIdForSingleInstanceFgActivation < 0 )
  {
    v15 = 241;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)HostIdForSingleInstanceFgActivation,
      (int)v34);
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v40);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpValue);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return (unsigned int)HostIdForSingleInstanceFgActivation;
  }
  HostIdForSingleInstanceFgActivation = (*(__int64 (__fastcall **)(struct IApplicationInstanceManager *, _QWORD, _QWORD))(*(_QWORD *)Execution::ActivationManagerShim::s_applicationInstanceManager + 48LL))(
                                          Execution::ActivationManagerShim::s_applicationInstanceManager,
                                          **(_QWORD **)(a1 + 32),
                                          **(_QWORD **)(a1 + 40));
  if ( HostIdForSingleInstanceFgActivation < 0 )
  {
    v15 = 242;
    goto LABEL_19;
  }
  v42 = 0;
  v46 = **(__int64 (__fastcall *****)(_QWORD, GUID *, __int64 *))(a1 + 40);
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v46);
  HostIdForSingleInstanceFgActivation = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>(
                                          &v46,
                                          &v42);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
  if ( HostIdForSingleInstanceFgActivation < 0 )
  {
    v16 = 245;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)HostIdForSingleInstanceFgActivation,
      (int)v34);
LABEL_28:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    goto LABEL_20;
  }
  v34 = **(struct Windows::Foundation::IExtensionRegistration ****)(a1 + 64);
  HostIdForSingleInstanceFgActivation = Execution::ActivationManagerShim::_InitializeActivatedEventArgs(
                                          v42,
                                          **(_QWORD **)(a1 + 48),
                                          **(unsigned int **)(a1 + 8),
                                          **(_QWORD **)(a1 + 56));
  if ( HostIdForSingleInstanceFgActivation < 0 )
  {
    v16 = 246;
    goto LABEL_27;
  }
  v48 = 0;
  *(_OWORD *)string = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(string);
  WindowsDeleteString(string[1]);
  string[1] = 0;
  v17 = **(HSTRING **)(a1 + 88);
  v46 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v8;
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v60, &v46);
  HostIdForSingleInstanceFgActivation = GetExtensionRegistrationForApplication(
                                          **(HSTRING **)(a1 + 80),
                                          *(HSTRING *)(v18 + 24),
                                          v17,
                                          &string[1],
                                          (struct Windows::Foundation::IExtensionRegistration **)string);
  if ( HostIdForSingleInstanceFgActivation < 0 )
  {
    v19 = 254;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)HostIdForSingleInstanceFgActivation,
      v35);
LABEL_34:
    ActivateByExtensionArgs::~ActivateByExtensionArgs((ActivateByExtensionArgs *)&v48);
    goto LABEL_28;
  }
  *(_DWORD *)(*(_QWORD *)a1 + 144LL) = 4;
  v38 = 0;
  HostIdForSingleInstanceFgActivation = QuirkUseUAPForLegacyImmersiveApplication(
                                          **(const unsigned __int16 ***)(a1 + 24),
                                          v8,
                                          &v38);
  if ( HostIdForSingleInstanceFgActivation < 0 )
  {
    v19 = 259;
    goto LABEL_33;
  }
  if ( v38 )
    *(_DWORD *)(*(_QWORD *)a1 + 112LL) |= 8u;
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
  v20 = *(Execution::ActivationManagerShim **)a1;
  v21 = **(_QWORD **)(a1 + 56);
  v60[0] = GUID_NULL;
  v22 = ViewActivator::CreateCoreWindowFactory(
          **(_QWORD **)(a1 + 64),
          **(_QWORD **)(a1 + 24),
          v60,
          **(_QWORD **)(a1 + 32),
          **(_QWORD **)(a1 + 48),
          v21,
          v21,
          0,
          *((_DWORD *)v20 + 28),
          **(_DWORD **)(a1 + 96),
          *((_QWORD *)v20 + 16),
          &v44);
  HostIdForSingleInstanceFgActivation = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v22,
      v36);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
    goto LABEL_34;
  }
  memset_0(v55, 0, 0x60u);
  v55[0] = **(_QWORD **)(a1 + 64);
  v23 = *(_QWORD **)(a1 + 56);
  v55[1] = *v23;
  v55[2] = *v23;
  v55[3] = **(_QWORD **)(a1 + 24);
  v55[4] = **(_QWORD **)(a1 + 48);
  v56 = GUID_NULL;
  v57 = 0;
  v58 = *(_DWORD *)(*(_QWORD *)a1 + 112LL);
  v59 = v44;
  v55[5] = **(_QWORD **)(a1 + 32);
  v43 = 0;
  v24 = **(_QWORD **)(a1 + 104);
  v25 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64 *))(*(_QWORD *)v24 + 32LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  HostIdForSingleInstanceFgActivation = v25(v24, v55, **(unsigned int **)(a1 + 96), &v43);
  if ( HostIdForSingleInstanceFgActivation < 0 )
  {
    v26 = 284;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)HostIdForSingleInstanceFgActivation,
      v36);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    goto LABEL_41;
  }
  **(_BYTE **)(a1 + 112) = 1;
  if ( !(unsigned __int8)IsActivateAheadAllowed(**(unsigned int **)(a1 + 8)) )
  {
    HostIdForSingleInstanceFgActivation = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 24LL))(v43);
    if ( HostIdForSingleInstanceFgActivation < 0 )
    {
      v26 = 292;
      goto LABEL_44;
    }
  }
  *(_DWORD *)(*(_QWORD *)a1 + 144LL) = 32;
  v47 = 0;
  GetPackageActivationSettings(v8, (enum PACKAGEACTIVATIONSETTINGS *)&v47);
  v45 = 0;
  v51 = *CWRLObjectWithGITSite::Site<IUnknown>(*(_QWORD *)a1, v60);
  v52 = &v48;
  v50 = 1;
  LODWORD(v46) = 0;
  v27 = *(_QWORD **)(a1 + 32);
  v53 = v13;
  v54[0] = v8;
  v28 = *(_QWORD **)(a1 + 48);
  v29 = *(__int64 **)(a1 + 24);
  v30 = *(_QWORD **)(a1 + 56);
  v31 = *(_QWORD **)(a1 + 64);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<AppActivation,IAAMActivation,unsigned __int64 &,unsigned __int64 &,unsigned short const * &,unsigned short const * &,unsigned short *,unsigned short *,_GUID const &,unsigned __int64 &,enum ACTIVATEOPTIONSINTERNAL &,enum PACKAGEACTIVATIONSETTINGS &,enum ActivateType,ActivateByExtensionArgs *,IUnknown *>(
         &v45,
         v31,
         v30,
         v29,
         v28,
         v54,
         &v53,
         (__int64)&GUID_NULL,
         v27,
         &v46,
         &v47,
         &v50,
         &v52,
         &v51);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v60);
  if ( v7 < 0 )
  {
    v32 = 314;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v7,
      (int)v37);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
    ActivateByExtensionArgs::~ActivateByExtensionArgs((ActivateByExtensionArgs *)&v48);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v40);
    goto LABEL_10;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 24LL))(
         v45,
         Execution::ActivationManagerShim::s_hamViewHacks);
  if ( v7 < 0 )
  {
    v32 = 316;
    goto LABEL_50;
  }
  v37 = (struct Windows::Foundation::IExtensionRegistration **)(*(_QWORD *)a1 + 144LL);
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v45 + 32LL))(v45, 0, v42, v43);
  ***(_DWORD ***)(a1 + 120) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 48LL))(v45);
  if ( v7 < 0 )
  {
    v32 = 327;
    goto LABEL_50;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
  ActivateByExtensionArgs::~ActivateByExtensionArgs((ActivateByExtensionArgs *)&v48);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v40);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpValue);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x18006bcf8  push    rbp
0x18006bcfa  push    rbx
0x18006bcfb  push    rsi
0x18006bcfc  push    rdi
0x18006bcfd  push    r12
0x18006bcff  push    r13
0x18006bd01  push    r14
0x18006bd03  push    r15
0x18006bd05  lea     rbp, [rsp-0A8h]
0x18006bd0d  sub     rsp, 1A8h
0x18006bd14  mov     rax, cs:__security_cookie
0x18006bd1b  xor     rax, rsp
0x18006bd1e  mov     [rbp+0E0h+var_50], rax
0x18006bd25  mov     r12, rcx
0x18006bd28  mov     rdx, [rcx]
0x18006bd2b  add     rdx, 60h ; '`'; struct CSRWLock *
0x18006bd2f  lea     rcx, [rbp+0E0h+SRWLock]; this
0x18006bd33  call    ??0CAutoSRWExclusiveLock@@QEAA@AEAVCSRWLock@@@Z; CAutoSRWExclusiveLock::CAutoSRWExclusiveLock(CSRWLock &)
0x18006bd38  nop
0x18006bd39  mov     rax, [r12+8]
0x18006bd3e  xor     r13d, r13d
0x18006bd41  cmp     [rax], r13d
0x18006bd44  jz      short loc_18006BD4D
0x18006bd46  mov     edx, 0E9h
0x18006bd4b  jmp     short loc_18006BD5C
0x18006bd4d  mov     rax, [r12+10h]
0x18006bd52  cmp     [rax], r13
0x18006bd55  jz      short loc_18006BD8F
0x18006bd57  mov     edx, 0EAh; void *
0x18006bd5c  mov     r9d, 80070057h; char *
0x18006bd62  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006bd69  mov     rcx, [rbp+0E8h]; this
0x18006bd70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bd75  nop
0x18006bd76  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x18006bd7a  test    rcx, rcx
0x18006bd7d  jz      short loc_18006BD85
0x18006bd7f  call    cs:__imp_ReleaseSRWLockExclusive
0x18006bd85  mov     eax, 80070057h
0x18006bd8a  jmp     loc_18006C466
0x18006bd8f  mov     [rsp+1E0h+lpValue], r13
0x18006bd94  xor     edx, edx
0x18006bd96  lea     rcx, [rsp+1E0h+lpValue]
0x18006bd9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006bda0  mov     rcx, [r12+18h]
0x18006bda5  lea     r8, [rsp+1E0h+lpValue]; unsigned __int16 **
0x18006bdaa  mov     rcx, [rcx]; applicationUserModelId
0x18006bdad  call    ?PraidAndPackageInfoFromAppId@Shared@DevPlat@@YAJPEBGPEAPEAG11@Z; DevPlat::Shared::PraidAndPackageInfoFromAppId(ushort const *,ushort * *,ushort * *,ushort * *)
0x18006bdb2  mov     ebx, eax
0x18006bdb4  test    eax, eax
0x18006bdb6  jns     short loc_18006BDF5
0x18006bdb8  mov     rcx, [rbp+0E8h]; this
0x18006bdbf  mov     r9d, eax; char *
0x18006bdc2  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006bdc9  mov     edx, 0EDh; void *
0x18006bdce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bdd3  nop
0x18006bdd4  lea     rcx, [rsp+1E0h+lpValue]
0x18006bdd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006bdde  nop
0x18006bddf  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x18006bde3  test    rcx, rcx
0x18006bde6  jz      short loc_18006BDEE
0x18006bde8  call    cs:__imp_ReleaseSRWLockExclusive
0x18006bdee  mov     eax, ebx
0x18006bdf0  jmp     loc_18006C466
0x18006bdf5  mov     [rbp+0E0h+var_160], r13
0x18006bdf9  xor     edx, edx
0x18006bdfb  lea     rcx, [rbp+0E0h+var_160]
0x18006bdff  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006be04  mov     rcx, [r12+18h]
0x18006be09  lea     r9, [rbp+0E0h+var_160]; unsigned __int16 **
0x18006be0d  mov     rbx, [rsp+1E0h+lpValue]
0x18006be12  mov     rdx, rbx; unsigned __int16 *
0x18006be15  mov     rcx, [rcx]; unsigned __int16 *
0x18006be18  call    ?GetPsmKey@ActivationManagerShim@Execution@@CAJPEBG0PEBU_GUID@@PEAPEAG@Z; Execution::ActivationManagerShim::GetPsmKey(ushort const *,ushort const *,_GUID const *,ushort * *)
0x18006be1d  mov     edi, eax
0x18006be1f  test    eax, eax
0x18006be21  jns     short loc_18006BE6A
0x18006be23  mov     rcx, [rbp+0E8h]; this
0x18006be2a  mov     r9d, eax; char *
0x18006be2d  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006be34  mov     edx, 0F0h; void *
0x18006be39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be3e  nop
0x18006be3f  lea     rcx, [rbp+0E0h+var_160]
0x18006be43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006be48  nop
0x18006be49  lea     rcx, [rsp+1E0h+lpValue]
0x18006be4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006be53  nop
0x18006be54  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x18006be58  test    rcx, rcx
0x18006be5b  jz      short loc_18006BE63
0x18006be5d  call    cs:__imp_ReleaseSRWLockExclusive
0x18006be63  mov     eax, edi
0x18006be65  jmp     loc_18006C466
0x18006be6a  mov     r9, [r12+20h]; unsigned __int64 *
0x18006be6f  mov     rdi, [rbp+0E0h+var_160]
0x18006be73  mov     r8, rdi; unsigned __int16 *
0x18006be76  mov     rcx, [r12]; this
0x18006be7a  call    ?GetHostIdForSingleInstanceFgActivation@ActivationManagerShim@Execution@@AEAAJPEA_KPEBG0@Z; Execution::ActivationManagerShim::GetHostIdForSingleInstanceFgActivation(unsigned __int64 *,ushort const *,unsigned __int64 *)
0x18006be7f  mov     esi, eax
0x18006be81  test    eax, eax
0x18006be83  jns     short loc_18006BECC
0x18006be85  mov     edx, 0F1h; void *
0x18006be8a  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006be91  mov     r9d, esi; char *
0x18006be94  mov     rcx, [rbp+0E8h]; this
0x18006be9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bea0  nop
0x18006bea1  lea     rcx, [rbp+0E0h+var_160]
0x18006bea5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006beaa  nop
0x18006beab  lea     rcx, [rsp+1E0h+lpValue]
0x18006beb0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006beb5  nop
0x18006beb6  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x18006beba  test    rcx, rcx
0x18006bebd  jz      short loc_18006BEC5
0x18006bebf  call    cs:__imp_ReleaseSRWLockExclusive
0x18006bec5  mov     eax, esi
0x18006bec7  jmp     loc_18006C466
0x18006becc  mov     rcx, cs:?s_applicationInstanceManager@ActivationManagerShim@Execution@@0V?$ComPtr@UIApplicationInstanceManager@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IApplicationInstanceManager> Execution::ActivationManagerShim::s_applicationInstanceManager
0x18006bed3  mov     rax, [rcx]
0x18006bed6  mov     r8, [r12+28h]
0x18006bedb  mov     rdx, [r12+20h]
0x18006bee0  mov     r8, [r8]
0x18006bee3  mov     rdx, [rdx]
0x18006bee6  mov     rax, [rax+30h]
0x18006beea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006beef  mov     esi, eax
0x18006bef1  test    eax, eax
0x18006bef3  jns     short loc_18006BEFC
0x18006bef5  mov     edx, 0F2h
0x18006befa  jmp     short loc_18006BE8A
0x18006befc  mov     [rbp+0E0h+var_150], r13
0x18006bf00  mov     rax, [r12+28h]
0x18006bf05  mov     rcx, [rax]
0x18006bf08  mov     [rbp+0E0h+var_130], rcx
0x18006bf0c  lea     rcx, [rbp+0E0h+var_130]
0x18006bf10  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006bf15  lea     rdx, [rbp+0E0h+var_150]
0x18006bf19  lea     rcx, [rbp+0E0h+var_130]
0x18006bf1d  call    ??$As@UIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>>)
0x18006bf22  mov     esi, eax
0x18006bf24  lea     rcx, [rbp+0E0h+var_130]
0x18006bf28  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006bf2d  test    esi, esi
0x18006bf2f  jns     short loc_18006BF5B
0x18006bf31  mov     edx, 0F5h; void *
0x18006bf36  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006bf3d  mov     r9d, esi; char *
0x18006bf40  mov     rcx, [rbp+0E8h]; this
0x18006bf47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bf4c  nop
0x18006bf4d  lea     rcx, [rbp+0E0h+var_150]
0x18006bf51  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006bf56  jmp     loc_18006BEA1
0x18006bf5b  mov     rax, [r12+48h]
0x18006bf60  mov     r10, [rax+110h]
0x18006bf67  add     r10, 8
0x18006bf6b  mov     rax, [r12+40h]
0x18006bf70  mov     r9, [r12+38h]
0x18006bf75  mov     r8, [r12+8]
0x18006bf7a  mov     rdx, [r12+30h]
0x18006bf7f  mov     [rsp+1E0h+var_1B8], r10
0x18006bf84  mov     rax, [rax]
0x18006bf87  mov     [rsp+1E0h+var_1C0], rax
0x18006bf8c  mov     r9, [r9]
0x18006bf8f  mov     r8d, [r8]
0x18006bf92  mov     rdx, [rdx]
0x18006bf95  mov     rcx, [rbp+0E0h+var_150]
0x18006bf99  call    ?_InitializeActivatedEventArgs@ActivationManagerShim@Execution@@CAJPEAUIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@PEBGW4ACTIVATEOPTIONSINTERNAL@@_K3AEBU_GUID@@@Z; Execution::ActivationManagerShim::_InitializeActivatedEventArgs(Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *,ushort const *,ACTIVATEOPTIONSINTERNAL,unsigned __int64,unsigned __int64,_GUID const &)
0x18006bf9e  mov     esi, eax
0x18006bfa0  test    eax, eax
0x18006bfa2  jns     short loc_18006BFAB
0x18006bfa4  mov     edx, 0F6h
0x18006bfa9  jmp     short loc_18006BF36
0x18006bfab  xorps   xmm0, xmm0
0x18006bfae  movups  [rbp+0E0h+var_120], xmm0
0x18006bfb2  xorps   xmm1, xmm1
0x18006bfb5  movdqu  xmmword ptr [rbp+0E0h+string], xmm1
0x18006bfba  lea     rcx, [rbp+0E0h+string]
0x18006bfbe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006bfc3  mov     rcx, [rbp+0E0h+string+8]; string
0x18006bfc7  call    cs:__imp_WindowsDeleteString
0x18006bfcd  mov     [rbp+0E0h+string+8], r13
0x18006bfd1  mov     rax, [r12+58h]
0x18006bfd6  mov     rsi, [rax]
0x18006bfd9  mov     [rbp+0E0h+var_130], rbx
0x18006bfdd  lea     rdx, [rbp+0E0h+var_130]
0x18006bfe1  lea     rcx, [rbp+0E0h+var_70]
0x18006bfe5  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18006bfea  nop
0x18006bfeb  mov     rcx, [r12+50h]
0x18006bff0  lea     rdx, [rbp+0E0h+string]
0x18006bff4  mov     [rsp+1E0h+var_1C0], rdx; int
0x18006bff9  lea     r9, [rbp+0E0h+string+8]; HSTRING *
0x18006bffd  mov     r8, rsi; HSTRING
0x18006c000  mov     rdx, [rax+18h]; HSTRING
0x18006c004  mov     rcx, [rcx]; HSTRING
0x18006c007  call    ?GetExtensionRegistrationForApplication@@YAJPEAUHSTRING__@@00PEAPEAU1@PEAPEAUIExtensionRegistration@Foundation@Windows@@@Z; GetExtensionRegistrationForApplication(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *,Windows::Foundation::IExtensionRegistration * *)
0x18006c00c  mov     esi, eax
0x18006c00e  test    eax, eax
0x18006c010  jns     short loc_18006C03C
0x18006c012  mov     edx, 0FEh; void *
0x18006c017  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006c01e  mov     r9d, esi; char *
0x18006c021  mov     rcx, [rbp+0E8h]; this
0x18006c028  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c02d  nop
0x18006c02e  lea     rcx, [rbp+0E0h+var_120]; this
0x18006c032  call    ??1ActivateByExtensionArgs@@QEAA@XZ; ActivateByExtensionArgs::~ActivateByExtensionArgs(void)
0x18006c037  jmp     loc_18006BF4D
0x18006c03c  mov     rax, [r12]
0x18006c040  mov     dword ptr [rax+90h], 4
0x18006c04a  mov     [rsp+1E0h+var_170], r13b
0x18006c04f  mov     rcx, [r12+18h]
0x18006c054  lea     r8, [rsp+1E0h+var_170]; bool *
0x18006c059  mov     rdx, rbx; unsigned __int16 *
0x18006c05c  mov     rcx, [rcx]; unsigned __int16 *
0x18006c05f  call    ?QuirkUseUAPForLegacyImmersiveApplication@@YAJPEBG0PEA_N@Z; QuirkUseUAPForLegacyImmersiveApplication(ushort const *,ushort const *,bool *)
0x18006c064  mov     esi, eax
0x18006c066  test    eax, eax
0x18006c068  jns     short loc_18006C071
0x18006c06a  mov     edx, 103h
0x18006c06f  jmp     short loc_18006C017
0x18006c071  cmp     [rsp+1E0h+var_170], r13b
0x18006c076  jz      short loc_18006C080
0x18006c078  mov     rax, [r12]
0x18006c07c  or      dword ptr [rax+70h], 8
0x18006c080  mov     [rbp+0E0h+var_140], r13
0x18006c084  lea     rcx, [rbp+0E0h+var_140]
0x18006c088  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006c08d  mov     r11, [r12]
0x18006c091  mov     rax, [r12+38h]
0x18006c096  mov     rsi, [rax]
0x18006c099  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006c0a0  movdqu  [rbp+0E0h+var_70], xmm0
0x18006c0a5  mov     r8, [r12+60h]
0x18006c0aa  mov     r10, [r12+30h]
0x18006c0af  mov     r9, [r12+20h]
0x18006c0b4  mov     rdx, [r12+18h]
0x18006c0b9  mov     rcx, [r12+40h]
0x18006c0be  lea     rax, [rbp+0E0h+var_140]
0x18006c0c2  mov     [rsp+1E0h+var_188], rax
0x18006c0c7  mov     rax, [r11+80h]
0x18006c0ce  mov     [rsp+1E0h+var_190], rax
0x18006c0d3  mov     eax, [r8]
0x18006c0d6  mov     dword ptr [rsp+1E0h+var_198], eax
0x18006c0da  mov     eax, [r11+70h]
0x18006c0de  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x18006c0e2  mov     dword ptr [rsp+1E0h+var_1A8], r13d
0x18006c0e7  mov     [rsp+1E0h+var_1B0], rsi
0x18006c0ec  mov     [rsp+1E0h+var_1B8], rsi
0x18006c0f1  mov     rax, [r10]
0x18006c0f4  mov     [rsp+1E0h+var_1C0], rax; int
0x18006c0f9  mov     r9, [r9]
0x18006c0fc  lea     r8, [rbp+0E0h+var_70]
0x18006c100  mov     rdx, [rdx]
0x18006c103  mov     rcx, [rcx]
0x18006c106  call    ?CreateCoreWindowFactory@ViewActivator@@SAJ_KPEBGU_GUID@@0100W4ACTIVATEOPTIONSINTERNAL@@W4ViewActivationFlags@Navigation@@KPEAUICoreWindowFactoryPrivCallbackSink@@PEAPEAUICoreWindowFactory@Core@UI@Windows@@@Z; ViewActivator::CreateCoreWindowFactory(unsigned __int64,ushort const *,_GUID,unsigned __int64,ushort const *,unsigned __int64,unsigned __int64,ACTIVATEOPTIONSINTERNAL,Navigation::ViewActivationFlags,ulong,ICoreWindowFactoryPrivCallbackSink *,Windows::UI::Core::ICoreWindowFactory * *)
0x18006c10b  mov     esi, eax
0x18006c10d  test    eax, eax
0x18006c10f  jns     short loc_18006C13B
0x18006c111  mov     rcx, [rbp+0E8h]; this
0x18006c118  mov     r9d, eax; char *
0x18006c11b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006c122  mov     edx, 10Ah; void *
0x18006c127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c12c  nop
0x18006c12d  lea     rcx, [rbp+0E0h+var_140]
0x18006c131  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006c136  jmp     loc_18006C02E
0x18006c13b  xor     edx, edx; Val
0x18006c13d  lea     r8d, [rdx+60h]; Size
0x18006c141  lea     rcx, [rbp+0E0h+var_D0]; void *
0x18006c145  call    memset_0
0x18006c14a  mov     rax, [r12+40h]
0x18006c14f  mov     rcx, [rax]
0x18006c152  mov     [rbp+0E0h+var_D0], rcx
0x18006c156  mov     rcx, [r12+38h]
0x18006c15b  mov     rax, [rcx]
0x18006c15e  mov     [rbp+0E0h+var_C8], rax
0x18006c162  mov     rax, [rcx]
0x18006c165  mov     [rbp+0E0h+var_C0], rax
0x18006c169  mov     rax, [r12+18h]
0x18006c16e  mov     rcx, [rax]
0x18006c171  mov     [rbp+0E0h+var_B8], rcx
0x18006c175  mov     rax, [r12+30h]
0x18006c17a  mov     rcx, [rax]
0x18006c17d  mov     [rbp+0E0h+var_B0], rcx
0x18006c181  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006c188  movdqu  [rbp+0E0h+var_A0], xmm0
0x18006c18d  mov     [rbp+0E0h+var_90], r13d
0x18006c191  mov     rax, [r12]
0x18006c195  mov     ecx, [rax+70h]
0x18006c198  mov     [rbp+0E0h+var_8C], ecx
0x18006c19b  mov     rax, [rbp+0E0h+var_140]
  ... truncated ...
```
