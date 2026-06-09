# SttExperienceManager::AddMessage(HSTRING__ *,HSTRING__ *,Windows::Gaming::UI::GameChatMessageOrigin)

- ea: `0x18034e1d0`
- end: `0x18034edbc`
- name: `?AddMessage@SttExperienceManager@@UEAAJPEAUHSTRING__@@0W4GameChatMessageOrigin@UI@Gaming@Windows@@@Z`
- size: `3052`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18000b314`
- `0x18000b370`
- `0x18000e498`
- `0x18001b190`
- `0x18001c710`
- `0x1800378dc`
- `0x180053740`
- `0x180055268`
- `0x18005d830`
- `0x18008d2f0`
- `0x1800ad4ec`
- `0x1800eb8b4`
- `0x1800f9664`
- `0x180142e10`
- `0x180151814`
- `0x180161390`
- `0x18019be28`
- `0x1802dd900`
- `0x1802dd940`
- `0x18031ce80`
- `0x18032fd5c`
- `0x18032fde4`
- `0x18034d800`
- `0x18034d948`
- `0x18034da04`
- `0x18034dbb4`
- `0x18034de54`
- `0x18034def0`
- `0x18034e1d0`
- `0x18034ef78`
- `0x180350304`
- `0x1803853fc`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034e6fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034e95c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ea4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034eb73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ec54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ecdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ed31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ed6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034e6fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034e95c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ea4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034eb73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ec54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ecdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ed31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18034ed6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall SttExperienceManager::AddMessage(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  bool v5; // si
  _QWORD *v6; // r14
  __int64 v7; // rcx
  _QWORD *v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  HSTRING v11; // rdi
  __int64 (__fastcall *v12)(HSTRING, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rdx
  _QWORD *v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 *v23; // rdi
  __int64 (__fastcall *v24)(__int64 *, PVOID, __int64 *); // rbx
  int v25; // eax
  _QWORD *v26; // rax
  int v27; // eax
  HSTRING v28; // rdi
  __int64 (__fastcall *v29)(HSTRING, __int64, __int64 *); // rbx
  int v30; // eax
  unsigned __int16 **v31; // rdx
  int CallingProcessPackageFamilyName; // eax
  unsigned __int16 **v33; // rdx
  int CallingProcessAppId; // eax
  HSTRING v35; // rbx
  _QWORD *v36; // r14
  int v37; // eax
  int v38; // edi
  __int64 v39; // rsi
  __int64 (__fastcall *v40)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v41; // rdx
  __int64 v42; // rsi
  __int64 (__fastcall *v43)(__int64, _QWORD *); // rdi
  __int64 v44; // rsi
  __int64 (__fastcall *v45)(__int64, __int64 *); // rdi
  __int64 v46; // rdx
  __int64 v47; // rsi
  __int64 (__fastcall *v48)(__int64, _QWORD, __int64 *); // rdi
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, __int64, __int64 **); // rbx
  int v53; // eax
  __int64 *v54; // rbx
  __int64 (__fastcall *v55)(__int64 *, HSTRING *); // rdi
  int v56; // eax
  __int64 v57; // rdx
  HSTRING v58; // rbx
  __int64 (__fastcall *v59)(HSTRING, HSTRING *); // rdi
  char v60; // r14
  __int64 v61; // r12
  __int64 v62; // rcx
  const char *v63; // r9
  __int128 *v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rbx
  HSTRING v67; // rdi
  _QWORD *v68; // rax
  __int64 v69; // rax
  __int64 v70; // rdx
  const char *v71; // r9
  __int64 v72; // rax
  __int64 v73; // r13
  __int64 *v74; // rcx
  bool i; // zf
  __int64 v76; // r14
  void (__fastcall *v77)(__int64, _QWORD, HSTRING, __int64, __int64, unsigned int); // rsi
  HSTRING v78; // rdi
  _QWORD *v79; // rax
  int v80; // [rsp+20h] [rbp-108h]
  HSTRING string; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v82; // [rsp+48h] [rbp-E0h] BYREF
  HSTRING v83; // [rsp+50h] [rbp-D8h] BYREF
  HSTRING v84; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v85; // [rsp+60h] [rbp-C8h] BYREF
  __int64 *v86; // [rsp+68h] [rbp-C0h] BYREF
  char v87[8]; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v88; // [rsp+78h] [rbp-B0h]
  __int64 v89; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v90; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v91; // [rsp+90h] [rbp-98h] BYREF
  __int128 v92; // [rsp+98h] [rbp-90h] BYREF
  __int64 v93; // [rsp+A8h] [rbp-80h]
  __int64 v94; // [rsp+B0h] [rbp-78h]
  __int64 v95; // [rsp+B8h] [rbp-70h]
  HSTRING_HEADER v96; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v97; // [rsp+D8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v88 = a4;
  v94 = a3;
  v95 = a2;
  v5 = 0;
  v6 = a1 + 25;
  wil::EnterCriticalSection(&v86, a1 + 25);
  SttExperienceManager::ResetHideAndCloseTimers((SttExperienceManager *)(a1 - 16));
  v7 = a1[8];
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, 0);
    v21 = SttExperienceManager::TriggerHideAndCloseTimers(a1 - 16);
    v10 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x288,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v21,
        v80);
      goto LABEL_19;
    }
  }
  else
  {
    v83 = 0;
    v8 = (_QWORD *)Windows::Internal::StringReference::StringReference((HSTRING *)&v96, L"Windows.System.Launcher");
    v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(
           *v8,
           &v83);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x276,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v9,
        v80);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
LABEL_19:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v86);
      return v10;
    }
    v82 = 0;
    v11 = v83;
    v12 = *(__int64 (__fastcall **)(HSTRING, _QWORD, __int64 *))(*(_QWORD *)v83 + 104LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v96, &c_AppProtocol);
    v14 = v12(v11, *(_QWORD *)(v13 + 24), &v82);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x278,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v14,
        v80);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      goto LABEL_12;
    }
    v85 = 0;
    v15 = v82;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    v16 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(
            v15,
            &v85);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 634;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v16,
        v80);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      goto LABEL_11;
    }
    LODWORD(v84) = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v85 + 56LL))(v85, &v84);
    v10 = v16;
    if ( v16 < 0 )
    {
      v17 = 637;
      goto LABEL_10;
    }
    v5 = (_DWORD)v84 != 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v86);
  if ( v5 )
  {
    v86 = 0;
    v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&v96,
                      (const unsigned __int16 (*)[23])v18);
    v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            *v19,
            &v86);
    v10 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x290,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v20,
        v80);
LABEL_29:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v86);
      return v10;
    }
    v82 = 0;
    v23 = v86;
    v24 = *(__int64 (__fastcall **)(__int64 *, PVOID, __int64 *))(*v86 + 48);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v82);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&v96, c_AppProtocolUri);
    v25 = v24(v23, v96.Reserved.Reserved1, &v82);
    v10 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x293,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v25,
        v80);
LABEL_28:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v82);
      goto LABEL_29;
    }
    v83 = 0;
    v26 = (_QWORD *)Windows::Internal::StringReference::StringReference((HSTRING *)&v96, L"Windows.System.Launcher");
    v27 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
            *v26,
            &v83);
    v10 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x296,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v27,
        v80);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      goto LABEL_28;
    }
    v85 = 0;
    v28 = v83;
    v29 = *(__int64 (__fastcall **)(HSTRING, __int64, __int64 *))(*(_QWORD *)v83 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    v30 = v29(v28, v82, &v85);
    v10 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v30,
        v80);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      goto LABEL_27;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v82);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v86);
  }
  v85 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v85,
    0);
  CallingProcessPackageFamilyName = CallerIdentity::GetCallingProcessPackageFamilyName((CallerIdentity *)&v85, v31);
  v10 = CallingProcessPackageFamilyName;
  if ( CallingProcessPackageFamilyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
      (const char *)(unsigned int)CallingProcessPackageFamilyName,
      v80);
LABEL_81:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
    return v10;
  }
  v84 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v84,
    0);
  CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&v84, v33);
  v10 = CallingProcessAppId;
  if ( CallingProcessAppId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
      (const char *)(unsigned int)CallingProcessAppId,
      v80);
LABEL_35:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v84);
    goto LABEL_81;
  }
  string = 0;
  v35 = v84;
  if ( v84 )
  {
    wil::EnterCriticalSection(v87, v6);
    v36 = a1 + 12;
    if ( !a1[12] )
    {
      v91 = 0;
      v97 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v96,
        L"WindowsInternal.Shell.UnifiedTile.UnifiedTileManager",
        0x35u,
        0x34u);
      v37 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(
              v97,
              &v91);
      v38 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AE,
          (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
          (const char *)(unsigned int)v37,
          v80);
LABEL_40:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
LABEL_41:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v87);
        WindowsDeleteString(string);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v84);
        v10 = v38;
        goto LABEL_81;
      }
      v90 = 0;
      v39 = v91;
      v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v91 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
      v38 = v40(v39, 3, 3, &v90);
      if ( v38 < 0 )
      {
        v41 = 697;
LABEL_44:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
          (const char *)(unsigned int)v38,
          v80);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
        goto LABEL_40;
      }
      v38 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<WindowsInternal::Shell::UnifiedTile::UnifiedTileManager *> *>(v90);
      if ( v38 < 0 )
      {
        v41 = 698;
        goto LABEL_44;
      }
      v42 = v90;
      v43 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v90 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 12);
      v38 = v43(v42, a1 + 12);
      if ( v38 < 0 )
      {
        v41 = 699;
        goto LABEL_44;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    }
    v89 = 0;
    v44 = *v36;
    v45 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v36 + 80LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v89);
    v38 = v45(v44, &v89);
    if ( v38 < 0 )
    {
      v46 = 704;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v46,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v38,
        v80);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v89);
      goto LABEL_41;
    }
    v38 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v89);
    if ( v38 < 0 )
    {
      v46 = 705;
      goto LABEL_52;
    }
    if ( !a1[10] )
    {
      v97 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v96,
        L"WindowsInternal.Shell.UnifiedTile.PackagedUnifiedTileIdentifier",
        0x40u,
        0x3Fu);
      v38 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifierFactory>>(
              v97,
              a1 + 10);
      if ( v38 < 0 )
      {
        v46 = 710;
        goto LABEL_52;
      }
    }
    v82 = 0;
    v47 = a1[10];
    v48 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    v83 = v35;
    v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v96, &v83);
    v50 = v48(v47, *(_QWORD *)(v49 + 24), &v82);
    v10 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v50,
        v80);
LABEL_60:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v89);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v87);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_35;
    }
    v86 = 0;
    v51 = *v36;
    v52 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)*v36 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    v53 = v52(v51, v82, &v86);
    v10 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CF,
        (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
        (const char *)(unsigned int)v53,
        v80);
LABEL_63:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      goto LABEL_60;
    }
    v54 = v86;
    if ( v86 )
    {
      v83 = 0;
      v55 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v86 + 56);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      v56 = v55(v54, &v83);
      v10 = v56;
      if ( v56 < 0 )
      {
        v57 = 725;
LABEL_67:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v57,
          (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
          (const char *)(unsigned int)v56,
          v80);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
        goto LABEL_63;
      }
      v58 = v83;
      if ( v83 )
      {
        v59 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v83 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v56 = v59(v58, &string);
        v10 = v56;
        if ( v56 < 0 )
        {
          v57 = 729;
          goto LABEL_67;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v89);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v87);
  }
  v60 = 0;
  v92 = 0;
  v61 = 0;
  v93 = 0;
  wil::EnterCriticalSection(v87, a1 + 25);
  v64 = (__int128 *)(a1 + 19);
  if ( (__int64)(a1[20] - a1[19]) >> 3 )
  {
    try
    {
      v60 = 1;
      if ( &v92 != v64 )
      {
        std::vector<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener>>::_Assign_counted_range<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener> *>(
          &v92,
          *(_QWORD *)v64);
        v61 = v93;
      }
      v65 = v85;
    }
    catch ( ... )
    {
      v88 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x2EC,
              (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
              v63);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v87);
      v66 = v92;
      if ( (_QWORD)v92 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener>>>(
          v92,
          *((_QWORD *)&v92 + 1));
        std::_Deallocate<16>(v66, (v93 - v66) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v84);
      v10 = v88;
      goto LABEL_81;
    }
  }
  else
  {
    v67 = string;
    v65 = v85;
    v68 = (_QWORD *)SttExperienceManager::CreateHString(v62, &v83, v85);
    v69 = StoredMessage::StoredMessage(&v96, *v68, v67, v95, v94, v88);
    v70 = a1[23];
    if ( v70 == a1[24] )
    {
      try
      {
        std::vector<StoredMessage>::_Emplace_reallocate<StoredMessage>(a1 + 22);
      }
      catch ( ... )
      {
        v88 = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x2FA,
                (unsigned int)"shell\\twinui\\sttexperiencemanager\\lib\\sttexperiencemanager.cpp",
                v71);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v87);
        WindowsDeleteString(string);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v84);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
        return v88;
      }
    }
    else
    {
      *(_QWORD *)v70 = *(_QWORD *)v69;
      *(_QWORD *)v69 = 0;
      *(_QWORD *)(v70 + 8) = *(_QWORD *)(v69 + 8);
      *(_QWORD *)(v69 + 8) = 0;
      *(_QWORD *)(v70 + 16) = *(_QWORD *)(v69 + 16);
      *(_QWORD *)(v69 + 16) = 0;
      *(_QWORD *)(v70 + 24) = *(_QWORD *)(v69 + 24);
      *(_QWORD *)(v69 + 24) = 0;
      *(_DWORD *)(v70 + 32) = *(_DWORD *)(v69 + 32);
      a1[23] += 40LL;
    }
    StoredMessage::~StoredMessage((StoredMessage *)&v96);
    WindowsDeleteString(v83);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v87);
  v72 = *((_QWORD *)&v92 + 1);
  v73 = v92;
  if ( v60 )
  {
    v74 = (__int64 *)v92;
    for ( i = (_QWORD)v92 == *((_QWORD *)&v92 + 1); ; i = v86 + 1 == *((__int64 **)&v92 + 1) )
    {
      v86 = v74;
      if ( i )
        break;
      v76 = *v74;
      v77 = *(void (__fastcall **)(__int64, _QWORD, HSTRING, __int64, __int64, unsigned int))(*(_QWORD *)*v74 + 48LL);
      v78 = string;
      v79 = (_QWORD *)SttExperienceManager::CreateHString(v74, &v83, v65);
      v77(v76, *v79, v78, v95, v94, v88);
      WindowsDeleteString(v83);
      v83 = 0;
      v74 = v86 + 1;
      v72 = *((_QWORD *)&v92 + 1);
    }
  }
  if ( v73 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SttInternal::IInternalMessageReceivedListener>>>(v73, v72);
    std::_Deallocate<16>(v73, (v61 - v73) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  WindowsDeleteString(string);
  string = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v84);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
  return 0;
}

```

## disassembly

```asm
0x18034e1d0  push    rbx
0x18034e1d2  push    rsi
0x18034e1d3  push    rdi
0x18034e1d4  push    r12
0x18034e1d6  push    r13
0x18034e1d8  push    r14
0x18034e1da  push    r15
0x18034e1dc  sub     rsp, 0F0h
0x18034e1e3  mov     rax, cs:__security_cookie
0x18034e1ea  xor     rax, rsp
0x18034e1ed  mov     [rsp+128h+var_40], rax
0x18034e1f5  mov     [rsp+128h+var_B0], r9d
0x18034e1fa  mov     [rsp+128h+var_78], r8
0x18034e202  mov     [rsp+128h+var_70], rdx
0x18034e20a  mov     r13, rcx
0x18034e20d  xor     r15d, r15d
0x18034e210  movzx   esi, r15b
0x18034e214  lea     r14, [rcx+0C8h]
0x18034e21b  mov     rdx, r14
0x18034e21e  lea     rcx, [rsp+128h+var_C0]
0x18034e223  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18034e228  nop
0x18034e229  lea     rcx, [r13-80h]; this
0x18034e22d  call    ?ResetHideAndCloseTimers@SttExperienceManager@@AEAAXXZ; SttExperienceManager::ResetHideAndCloseTimers(void)
0x18034e232  mov     rcx, [r13+40h]
0x18034e236  test    rcx, rcx
0x18034e239  jnz     loc_18034E40C
0x18034e23f  mov     [rsp+128h+var_D8], r15
0x18034e244  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18034e24b  lea     rcx, [rsp+128h+var_68]; string
0x18034e253  call    ??$?0$0BI@@StringReference@Internal@Windows@@QEAA@AEAY0BI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[24])
0x18034e258  lea     rdx, [rsp+128h+var_D8]
0x18034e25d  mov     rcx, [rax]
0x18034e260  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics2@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics2>>)
0x18034e265  mov     ebx, eax
0x18034e267  test    eax, eax
0x18034e269  jns     short loc_18034E28C
0x18034e26b  mov     rcx, [rsp+128h]; this
0x18034e273  mov     r9d, eax; char *
0x18034e276  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e27d  mov     edx, 276h; void *
0x18034e282  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e287  jmp     loc_18034E376
0x18034e28c  mov     [rsp+128h+var_E0], r15
0x18034e291  mov     rdi, [rsp+128h+var_D8]
0x18034e296  mov     rax, [rdi]
0x18034e299  mov     rbx, [rax+68h]
0x18034e29d  lea     rcx, [rsp+128h+var_E0]
0x18034e2a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e2a7  lea     rdx, ?c_AppProtocol@@3PEBGEB; ushort const * const c_AppProtocol
0x18034e2ae  lea     rcx, [rsp+128h+var_68]
0x18034e2b6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18034e2bb  nop
0x18034e2bc  lea     r8, [rsp+128h+var_E0]
0x18034e2c1  mov     rdx, [rax+18h]
0x18034e2c5  mov     rcx, rdi
0x18034e2c8  mov     rax, rbx
0x18034e2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034e2d0  mov     ebx, eax
0x18034e2d2  test    eax, eax
0x18034e2d4  jns     short loc_18034E2F4
0x18034e2d6  mov     rcx, [rsp+128h]; this
0x18034e2de  mov     r9d, eax; char *
0x18034e2e1  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e2e8  mov     edx, 278h; void *
0x18034e2ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e2f2  jmp     short loc_18034E36B
0x18034e2f4  mov     [rsp+128h+var_C8], r15
0x18034e2f9  mov     rbx, [rsp+128h+var_E0]
0x18034e2fe  lea     rcx, [rsp+128h+var_C8]
0x18034e303  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e308  lea     rdx, [rsp+128h+var_C8]
0x18034e30d  mov     rcx, rbx
0x18034e310  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVAppInfo@ApplicationModel@Windows@@@Collections@12@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> *> *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppInfo *> * *,tagCOWAIT_FLAGS,void *)
0x18034e315  mov     ebx, eax
0x18034e317  test    eax, eax
0x18034e319  jns     short loc_18034E322
0x18034e31b  mov     edx, 27Ah
0x18034e320  jmp     short loc_18034E348
0x18034e322  mov     dword ptr [rsp+128h+var_D0], r15d
0x18034e327  mov     rcx, [rsp+128h+var_C8]
0x18034e32c  mov     rax, [rcx]
0x18034e32f  lea     rdx, [rsp+128h+var_D0]
0x18034e334  mov     rax, [rax+38h]
0x18034e338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034e33d  mov     ebx, eax
0x18034e33f  test    eax, eax
0x18034e341  jns     short loc_18034E385
0x18034e343  mov     edx, 27Dh; void *
0x18034e348  mov     r9d, eax; char *
0x18034e34b  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e352  mov     rcx, [rsp+128h]; this
0x18034e35a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e35f  nop
0x18034e360  lea     rcx, [rsp+128h+var_C8]
0x18034e365  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e36a  nop
0x18034e36b  lea     rcx, [rsp+128h+var_E0]
0x18034e370  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e375  nop
0x18034e376  lea     rcx, [rsp+128h+var_D8]
0x18034e37b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e380  jmp     loc_18034E446
0x18034e385  mov     ebx, 1
0x18034e38a  cmp     dword ptr [rsp+128h+var_D0], r15d
0x18034e38f  cmova   esi, ebx
0x18034e392  lea     rcx, [rsp+128h+var_C8]
0x18034e397  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e39c  nop
0x18034e39d  lea     rcx, [rsp+128h+var_E0]
0x18034e3a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e3a7  nop
0x18034e3a8  lea     rcx, [rsp+128h+var_D8]
0x18034e3ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e3b2  nop
0x18034e3b3  lea     rcx, [rsp+128h+var_C0]
0x18034e3b8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18034e3bd  test    sil, sil
0x18034e3c0  jz      loc_18034E5BD
0x18034e3c6  mov     [rsp+128h+var_C0], r15
0x18034e3cb  lea     rcx, [rsp+128h+var_68]; string
0x18034e3d3  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x18034e3d8  lea     rdx, [rsp+128h+var_C0]
0x18034e3dd  mov     rcx, [rax]
0x18034e3e0  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18034e3e5  mov     ebx, eax
0x18034e3e7  test    eax, eax
0x18034e3e9  jns     short loc_18034E457
0x18034e3eb  mov     rcx, [rsp+128h]; this
0x18034e3f3  mov     r9d, eax; char *
0x18034e3f6  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e3fd  mov     edx, 290h; void *
0x18034e402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e407  jmp     loc_18034E583
0x18034e40c  mov     rax, [rcx]
0x18034e40f  xor     edx, edx
0x18034e411  mov     rax, [rax+28h]
0x18034e415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034e41a  lea     rcx, [r13-80h]; pv
0x18034e41e  call    ?TriggerHideAndCloseTimers@SttExperienceManager@@AEAAJXZ; SttExperienceManager::TriggerHideAndCloseTimers(void)
0x18034e423  mov     ebx, eax
0x18034e425  test    eax, eax
0x18034e427  jns     short loc_18034E3B3
0x18034e429  mov     rcx, [rsp+128h]; this
0x18034e431  mov     r9d, eax; char *
0x18034e434  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e43b  mov     edx, 288h; void *
0x18034e440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e445  nop
0x18034e446  lea     rcx, [rsp+128h+var_C0]
0x18034e44b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18034e450  mov     eax, ebx
0x18034e452  jmp     loc_18034ED98
0x18034e457  mov     [rsp+128h+var_E0], r15
0x18034e45c  mov     rdi, [rsp+128h+var_C0]
0x18034e461  mov     rax, [rdi]
0x18034e464  mov     rbx, [rax+30h]
0x18034e468  lea     rcx, [rsp+128h+var_E0]
0x18034e46d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18034e472  mov     rdx, cs:?c_AppProtocolUri@@3PEBGEB; unsigned __int16 *
0x18034e479  lea     rcx, [rsp+128h+var_68]; this
0x18034e481  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18034e486  lea     r8, [rsp+128h+var_E0]
0x18034e48b  mov     rdx, qword ptr [rsp+128h+var_68]
0x18034e493  mov     rcx, rdi
0x18034e496  mov     rax, rbx
0x18034e499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034e49e  mov     ebx, eax
0x18034e4a0  test    eax, eax
0x18034e4a2  jns     short loc_18034E4C5
0x18034e4a4  mov     rcx, [rsp+128h]; this
0x18034e4ac  mov     r9d, eax; char *
0x18034e4af  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e4b6  mov     edx, 293h; void *
0x18034e4bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e4c0  jmp     loc_18034E578
0x18034e4c5  mov     [rsp+128h+var_D8], r15
0x18034e4ca  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18034e4d1  lea     rcx, [rsp+128h+var_68]; string
0x18034e4d9  call    ??$?0$0BI@@StringReference@Internal@Windows@@QEAA@AEAY0BI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[24])
0x18034e4de  lea     rdx, [rsp+128h+var_D8]
0x18034e4e3  mov     rcx, [rax]
0x18034e4e6  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>)
0x18034e4eb  mov     ebx, eax
0x18034e4ed  test    eax, eax
0x18034e4ef  jns     short loc_18034E50F
0x18034e4f1  mov     rcx, [rsp+128h]; this
0x18034e4f9  mov     r9d, eax; char *
0x18034e4fc  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e503  mov     edx, 296h; void *
0x18034e508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e50d  jmp     short loc_18034E56D
0x18034e50f  mov     [rsp+128h+var_C8], r15
0x18034e514  mov     rdi, [rsp+128h+var_D8]
0x18034e519  mov     rax, [rdi]
0x18034e51c  mov     rbx, [rax+40h]
0x18034e520  lea     rcx, [rsp+128h+var_C8]
0x18034e525  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e52a  lea     r8, [rsp+128h+var_C8]
0x18034e52f  mov     rdx, [rsp+128h+var_E0]
0x18034e534  mov     rcx, rdi
0x18034e537  mov     rax, rbx
0x18034e53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18034e53f  mov     ebx, eax
0x18034e541  test    eax, eax
0x18034e543  jns     short loc_18034E592
0x18034e545  mov     rcx, [rsp+128h]; this
0x18034e54d  mov     r9d, eax; char *
0x18034e550  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e557  mov     edx, 299h; void *
0x18034e55c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e561  nop
0x18034e562  lea     rcx, [rsp+128h+var_C8]
0x18034e567  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e56c  nop
0x18034e56d  lea     rcx, [rsp+128h+var_D8]
0x18034e572  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e577  nop
0x18034e578  lea     rcx, [rsp+128h+var_E0]
0x18034e57d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18034e582  nop
0x18034e583  lea     rcx, [rsp+128h+var_C0]
0x18034e588  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18034e58d  jmp     loc_18034E450
0x18034e592  lea     rcx, [rsp+128h+var_C8]
0x18034e597  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e59c  nop
0x18034e59d  lea     rcx, [rsp+128h+var_D8]
0x18034e5a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18034e5a7  nop
0x18034e5a8  lea     rcx, [rsp+128h+var_E0]
0x18034e5ad  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18034e5b2  nop
0x18034e5b3  lea     rcx, [rsp+128h+var_C0]
0x18034e5b8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18034e5bd  mov     [rsp+128h+var_C8], r15
0x18034e5c2  xor     edx, edx
0x18034e5c4  lea     rcx, [rsp+128h+var_C8]
0x18034e5c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18034e5ce  lea     rcx, [rsp+128h+var_C8]; this
0x18034e5d3  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x18034e5d8  mov     ebx, eax
0x18034e5da  test    eax, eax
0x18034e5dc  jns     short loc_18034E5FF
0x18034e5de  mov     rcx, [rsp+128h]; this
0x18034e5e6  mov     r9d, eax; char *
0x18034e5e9  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e5f0  mov     edx, 29Eh; void *
0x18034e5f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e5fa  jmp     loc_18034EB92
0x18034e5ff  mov     [rsp+128h+var_D0], r15
0x18034e604  xor     edx, edx
0x18034e606  lea     rcx, [rsp+128h+var_D0]
0x18034e60b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18034e610  lea     rcx, [rsp+128h+var_D0]; this
0x18034e615  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x18034e61a  mov     ebx, eax
0x18034e61c  test    eax, eax
0x18034e61e  jns     short loc_18034E64C
0x18034e620  mov     rcx, [rsp+128h]; this
0x18034e628  mov     r9d, eax; char *
0x18034e62b  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e632  mov     edx, 2A1h; void *
0x18034e637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e63c  nop
0x18034e63d  lea     rcx, [rsp+128h+var_D0]
0x18034e642  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18034e647  jmp     loc_18034EB92
0x18034e64c  mov     [rsp+128h+string], r15
0x18034e651  mov     rbx, [rsp+128h+var_D0]
0x18034e656  test    rbx, rbx
0x18034e659  jz      loc_18034EAB2
0x18034e65f  mov     rdx, r14
0x18034e662  lea     rcx, [rsp+128h+var_B8]
0x18034e667  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18034e66c  nop
0x18034e66d  lea     r14, [r13+60h]
0x18034e671  cmp     [r14], r15
0x18034e674  jnz     loc_18034E7FB
0x18034e67a  mov     [rsp+128h+var_98], r15
0x18034e682  mov     [rsp+128h+var_50], r15
0x18034e68a  mov     r9d, 34h ; '4'; unsigned int
0x18034e690  lea     r8d, [r9+1]; unsigned int
0x18034e694  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_UnifiedTileManager@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Unifi"...
0x18034e69b  lea     rcx, [rsp+128h+var_68]; hstringHeader
0x18034e6a3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18034e6a8  lea     rdx, [rsp+128h+var_98]
0x18034e6b0  mov     rcx, [rsp+128h+var_50]
0x18034e6b8  call    ??$GetActivationFactory@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUnifiedTileManagerStatics@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileManagerStatics>>)
0x18034e6bd  mov     edi, eax
0x18034e6bf  test    eax, eax
0x18034e6c1  jns     short loc_18034E720
0x18034e6c3  mov     rcx, [rsp+128h]; this
0x18034e6cb  mov     r9d, eax; char *
0x18034e6ce  lea     r8, aShellTwinuiStt; "shell\\twinui\\sttexperiencemanager\\li"...
0x18034e6d5  mov     edx, 2AEh; void *
0x18034e6da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18034e6df  nop
0x18034e6e0  lea     rcx, [rsp+128h+var_98]
0x18034e6e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
