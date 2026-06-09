# AppReadiness::Tasks::AppxPreRegister::OnExecute(void)

- ea: `0x180066670`
- end: `0x180066e31`
- name: `?OnExecute@AppxPreRegister@Tasks@AppReadiness@@MEAAXXZ`
- size: `1985`
- prototype: `void __fastcall(AppReadiness::Tasks::AppxPreRegister *__hidden this)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002958`
- `0x180002a60`
- `0x180002b0c`
- `0x1800091a0`
- `0x1800148b0`
- `0x1800178d0`
- `0x18001d548`
- `0x1800203d8`
- `0x180026b90`
- `0x1800276e0`
- `0x18002eecc`
- `0x180032610`
- `0x180039eec`
- `0x18003b740`
- `0x18003e210`
- `0x180049310`
- `0x18005f1c0`
- `0x180060310`
- `0x1800664a0`
- `0x180066504`
- `0x180066554`
- `0x18006659c`
- `0x180066670`
- `0x180066f98`
- `0x18006727c`
- `0x180074ebc`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006691a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006691a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066906`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066906`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006676b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006676b`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x1800667cd`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x180066c9f`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x1800667cd`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x180066c9f`

## string_xrefs

- `0x18006697b`: `onecoreuap\shell\appreadiness\src\tasks\appxpreregister.cpp`
- `0x180066e0a`: `onecoreuap\shell\appreadiness\src\tasks\appxpreregister.cpp`
- `0x180066e1f`: `onecoreuap\shell\appreadiness\src\tasks\appxpreregister.cpp`
- `0x180066910`: `MsixPreRegisterUupProducts`
- `0x1800668ff`: `appxdeploymentclient.dll`

## pseudocode

```c
void __fastcall AppReadiness::Tasks::AppxPreRegister::OnExecute(AppReadiness::Tasks::AppxPreRegister *this)
{
  AppReadiness::Impl::BaseTask *v1; // r14
  int v2; // r15d
  _QWORD *v3; // rcx
  _QWORD *v4; // rdx
  _QWORD *v5; // rsi
  __int64 v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // r13
  _QWORD **v9; // rcx
  _QWORD *v10; // rdi
  _QWORD *v11; // r12
  __int64 v12; // rax
  PSRWLOCK v13; // rcx
  __int64 v14; // r8
  int v15; // r12d
  _QWORD *v16; // r14
  _QWORD *v17; // rcx
  int v18; // eax
  int v19; // r15d
  __int64 v20; // r9
  _QWORD *v21; // r8
  __int64 (*ProcAddress)(void); // rax
  int v23; // eax
  int v24; // eax
  _QWORD *v25; // rax
  __int64 v26; // rax
  _QWORD *v27; // rax
  __int64 v28; // rax
  __int64 v29; // r14
  __int64 (__fastcall *v30)(__int64, _QWORD, _QWORD, __int64); // r15
  _QWORD *v31; // rax
  __int64 v32; // rax
  int v33; // r14d
  int v34; // r8d
  int v35; // r9d
  int v36; // r15d
  int v37; // eax
  wil::details::in1diag3 *v38; // rcx
  __int64 v39; // rdx
  _QWORD *v40; // r8
  int v41; // eax
  int v42; // r14d
  int v43; // eax
  __int64 v44; // r8
  int v45; // r14d
  int v46; // r15d
  char *v47; // rdx
  _QWORD *v48; // rbx
  PVOID *v49; // rcx
  AppReadiness::Impl::BaseTask *v50; // r13
  _QWORD *v51; // rdi
  _QWORD *v52; // rcx
  int v53; // r12d
  __int64 v54; // r9
  _QWORD *v55; // r8
  __int64 v56; // [rsp+20h] [rbp-E0h]
  __int64 v57; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v59; // [rsp+50h] [rbp-B0h] BYREF
  AppReadiness::Impl::BaseTask *v60; // [rsp+58h] [rbp-A8h]
  _QWORD *v61; // [rsp+60h] [rbp-A0h]
  _QWORD *v62; // [rsp+68h] [rbp-98h] BYREF
  __int64 v63; // [rsp+70h] [rbp-90h] BYREF
  __int128 v64; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int128 v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h]
  char v68[8]; // [rsp+A8h] [rbp-58h] BYREF
  char v69[8]; // [rsp+B0h] [rbp-50h] BYREF
  char v70[8]; // [rsp+B8h] [rbp-48h] BYREF
  char v71[8]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v72; // [rsp+C8h] [rbp-38h] BYREF
  char v73[8]; // [rsp+D0h] [rbp-30h] BYREF
  char v74[8]; // [rsp+D8h] [rbp-28h] BYREF
  char v75[8]; // [rsp+E0h] [rbp-20h] BYREF
  HMODULE Library; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v78; // [rsp+108h] [rbp+8h]
  char v79[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v1 = this;
  v60 = this;
  v66 = 0;
  v2 = 0;
  v67 = 0;
  v64 = 0;
  v65 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 56);
  v3 = (_QWORD *)((char *)v1 + 248);
  if ( (__int128 *)((char *)v1 + 248) == &v66 )
  {
    v8 = 0;
    v7 = 0;
    v5 = (_QWORD *)*((_QWORD *)&v66 + 1);
    v61 = (_QWORD *)v66;
  }
  else
  {
    v61 = (_QWORD *)*v3;
    v4 = v61;
    *v3 = 0;
    *(_QWORD *)&v66 = v4;
    v5 = (_QWORD *)*((_QWORD *)v1 + 32);
    *((_QWORD *)v1 + 32) = 0;
    *((_QWORD *)&v66 + 1) = v5;
    v6 = *((_QWORD *)v1 + 33);
    *((_QWORD *)v1 + 33) = 0;
    v67 = v6;
    v7 = v4;
    v8 = v5;
  }
  v9 = (_QWORD **)((char *)v1 + 272);
  if ( (__int128 *)((char *)v1 + 272) == &v64 )
  {
    v11 = (_QWORD *)*((_QWORD *)&v64 + 1);
    v10 = (_QWORD *)v64;
  }
  else
  {
    v10 = *v9;
    *v9 = 0;
    *(_QWORD *)&v64 = v10;
    v11 = (_QWORD *)*((_QWORD *)v1 + 35);
    *((_QWORD *)v1 + 35) = 0;
    *((_QWORD *)&v64 + 1) = v11;
    v12 = *((_QWORD *)v1 + 36);
    *((_QWORD *)v1 + 36) = 0;
    v65 = v12;
  }
  v59 = v10;
  v62 = v11;
  v13 = SRWLock;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  LODWORD(v57) = 0;
  v14 = 0;
  if ( v7 == v8 )
  {
    v13 = (PSRWLOCK)WPP_GLOBAL_Control;
  }
  else
  {
    v15 = 0;
    do
    {
      v16 = v7 + 3;
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
        McTemplateU0z_EventWriteTransfer(v13, Package_PreRegistration_Start);
      if ( *v16 <= 7u )
        v17 = v7;
      else
        v17 = (_QWORD *)*v7;
      v18 = AppxPreRegisterPackage(v17, 2);
      v19 = v18;
      v13 = (PSRWLOCK)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *v16 <= 7u )
          LODWORD(v20) = (_DWORD)v7;
        else
          v20 = *v7;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_fb225c8d27f6327f6fb2058d73d6f2b1_Traceguids,
          v20,
          v18);
        v13 = (PSRWLOCK)WPP_GLOBAL_Control;
      }
      if ( v19 < 0 )
      {
        if ( (Microsoft_Windows_AppReadinessEnableBits & 0x40000) != 0 )
        {
          if ( *v16 <= 7u )
            v21 = v7;
          else
            v21 = (_QWORD *)*v7;
          McTemplateU0zd_EventWriteTransfer(v13, Package_PreRegistration_Failure, v21, (unsigned int)v19);
          v13 = (PSRWLOCK)WPP_GLOBAL_Control;
        }
        ++v15;
        v2 = v57;
      }
      else
      {
        v2 = v57 + 1;
        LODWORD(v57) = v57 + 1;
      }
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(v13, Package_PreRegistration_Stop);
        v13 = (PSRWLOCK)WPP_GLOBAL_Control;
      }
      v7 += 4;
    }
    while ( v7 != v8 );
    LODWORD(SRWLock) = v15;
    v10 = v59;
    v11 = v62;
    v1 = v60;
    v14 = (unsigned int)SRWLock;
  }
  if ( v13 != (PSRWLOCK)&WPP_GLOBAL_Control && (BYTE4(v13[3].Ptr) & 4) != 0 )
  {
    LODWORD(v56) = v14 + v2;
    WPP_SF_llll(v13[2].Ptr, 14, v14, ((char *)v5 - (char *)v61) >> 5);
  }
  Library = LoadLibraryExW(L"appxdeploymentclient.dll", 0, 0x800u);
  ProcAddress = GetProcAddress(Library, "MsixPreRegisterUupProducts");
  v23 = ProcAddress();
  if ( v23 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\appxpreregister.cpp",
      (const char *)(unsigned int)v23,
      v56);
  v63 = 0;
  if ( v10 != v11 )
  {
    v78 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Management.Deployment.Internal.PackageManagerInternal",
      0x3Eu,
      0x3Du);
    v24 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
            v78,
            &v63);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\appxpreregister.cpp",
        (const char *)(unsigned int)v24,
        v56);
  }
  while ( v10 != v11 )
  {
    v57 = 0;
    v25 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::ensure_data(&v57);
    tip2::details::shared_data<0,0,0>::start(*v25 + 8LL, &hstringHeader);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(
                             &v57,
                             v68)
              + 276LL) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(v68);
    v26 = tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(
            &v57,
            v69);
    *(_DWORD *)(*(_QWORD *)v26 + 312LL) |= 0x10u;
    tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(v69);
    v27 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(
                      &v57,
                      v70);
    std::wstring::operator=(*v27 + 320LL, v10);
    tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(v70);
    v28 = tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(
            &v57,
            v71);
    _tip_OneTimeRegisterTest::CheckEnvironment((_tip_OneTimeRegisterTest *)(*(_QWORD *)v28 + 256LL));
    tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(v71);
    v59 = 0;
    v29 = v63;
    v30 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v63 + 88LL);
    if ( v10[3] <= 7u )
      v31 = v10;
    else
      v31 = (_QWORD *)*v10;
    v72 = v31;
    v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v79, &v72);
    LODWORD(v56) = 4;
    v33 = v30(v29, *(_QWORD *)(v32 + 24), 0, 512);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(
                             &v57,
                             v73)
              + 272LL) = v33;
    tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(v73);
    if ( v33 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\appxpreregister.cpp",
        (const char *)(unsigned int)v33,
        4);
    v36 = Windows::Management::Deployment::WaitForDeploymentOperation((_DWORD)retaddr, (_DWORD)v59, v34, v35, v56);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(
                             &v57,
                             v74)
              + 272LL) = v36;
    tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(v74);
    v62 = 0;
    LODWORD(SRWLock) = 0;
    v37 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD **))(*v59 + 80LL))(v59, &v62);
    v38 = retaddr;
    if ( v37 >= 0 )
    {
      v37 = (*(__int64 (__fastcall **)(_QWORD *, PSRWLOCK *))(*v62 + 64LL))(v62, &SRWLock);
      v38 = retaddr;
      if ( v37 >= 0 )
        goto LABEL_51;
      v39 = 181;
    }
    else
    {
      v39 = 179;
    }
    wil::details::in1diag3::_Log_Hr(
      v38,
      (void *)v39,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\appxpreregister.cpp",
      (const char *)(unsigned int)v37,
      v56);
LABEL_51:
    if ( v10[3] <= 7u )
      v40 = v10;
    else
      v40 = (_QWORD *)*v10;
    v41 = Common::AppModelTipHelper::SetOtrResultsInRegistryForInboxPackage(
            (unsigned int)v36,
            (unsigned int)SRWLock,
            v40);
    v42 = v41;
    if ( v41 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\appxpreregister.cpp",
        (const char *)(unsigned int)v41,
        v56);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(
                             &v57,
                             v75)
              + 352LL) = v42;
    tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(v75);
    if ( v36 >= 0 )
    {
      v1 = v60;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\appxpreregister.cpp",
        (const char *)(unsigned int)v36,
        v56);
      v1 = v60;
      *((_BYTE *)v60 + 241) = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    wil::com_ptr_t<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>,wil::err_returncode_policy>(&v57);
    v10 += 4;
  }
  v43 = AppReadiness::System::SetAllLogonBlockingOTR(*((_BYTE *)v1 + 241));
  if ( v43 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\appxpreregister.cpp",
      (const char *)(unsigned int)v43,
      v56);
  v45 = 0;
  v46 = 0;
  v47 = (char *)v61;
  v48 = v61;
  v49 = (PVOID *)WPP_GLOBAL_Control;
  v50 = v60;
  if ( v61 != v5 )
  {
    do
    {
      if ( *((_BYTE *)v50 + 240) )
        break;
      v51 = v48 + 3;
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
        McTemplateU0z_EventWriteTransfer(v49, Package_PreRegistration_Start);
      if ( *v51 <= 7u )
        v52 = v48;
      else
        v52 = (_QWORD *)*v48;
      v53 = AppxPreRegisterPackage(v52, 0);
      v49 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *v51 <= 7u )
          LODWORD(v54) = (_DWORD)v48;
        else
          v54 = *v48;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_fb225c8d27f6327f6fb2058d73d6f2b1_Traceguids,
          v54,
          v53);
        v49 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v53 < 0 )
      {
        if ( (Microsoft_Windows_AppReadinessEnableBits & 0x40000) != 0 )
        {
          if ( *v51 <= 7u )
            v55 = v48;
          else
            v55 = (_QWORD *)*v48;
          McTemplateU0zd_EventWriteTransfer(v49, Package_PreRegistration_Failure, v55, (unsigned int)v53);
          v49 = (PVOID *)WPP_GLOBAL_Control;
        }
        ++v46;
      }
      else
      {
        ++v45;
      }
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(v49, Package_PreRegistration_Stop);
        v49 = (PVOID *)WPP_GLOBAL_Control;
      }
      v48 += 4;
    }
    while ( v48 != v5 );
    v47 = (char *)v61;
  }
  if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 4) != 0 )
    WPP_SF_llll(v49[2], 16, v44, (unsigned int)(((char *)v5 - v47) >> 5));
  AppReadiness::Impl::BaseTask::CompleteTask(v50, 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  std::vector<std::wstring>::_Tidy(&v64);
  std::vector<std::wstring>::_Tidy(&v66);
}

```

## disassembly

```asm
0x180066670  push    rbp
0x180066672  push    rbx
0x180066673  push    rsi
0x180066674  push    rdi
0x180066675  push    r12
0x180066677  push    r13
0x180066679  push    r14
0x18006667b  push    r15
0x18006667d  lea     rbp, [rsp-48h]
0x180066682  sub     rsp, 148h
0x180066689  mov     rax, cs:__security_cookie
0x180066690  xor     rax, rsp
0x180066693  mov     [rbp+80h+var_50], rax
0x180066697  mov     r14, rcx
0x18006669a  mov     [rsp+180h+var_128], rcx
0x18006669f  xorps   xmm0, xmm0
0x1800666a2  movdqu  [rbp+80h+var_F0], xmm0
0x1800666a7  xor     r15d, r15d
0x1800666aa  mov     [rbp+80h+var_E0], r15
0x1800666ae  movdqu  [rsp+180h+var_108], xmm0
0x1800666b4  mov     [rbp+80h+var_F8], r15
0x1800666b8  lea     rdx, [rcx+38h]
0x1800666bc  lea     rcx, [rsp+180h+SRWLock]
0x1800666c1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800666c6  lea     rcx, [r14+0F8h]
0x1800666cd  lea     rax, [rbp+80h+var_F0]
0x1800666d1  cmp     rcx, rax
0x1800666d4  jz      short loc_180066705
0x1800666d6  mov     rdx, [rcx]
0x1800666d9  mov     [rsp+180h+var_120], rdx
0x1800666de  mov     [rcx], r15
0x1800666e1  mov     qword ptr [rbp+80h+var_F0], rdx
0x1800666e5  mov     rsi, [rcx+8]
0x1800666e9  mov     [rcx+8], r15
0x1800666ed  mov     qword ptr [rbp+80h+var_F0+8], rsi
0x1800666f1  mov     rax, [rcx+10h]
0x1800666f5  mov     [rcx+10h], r15
0x1800666f9  mov     [rbp+80h+var_E0], rax
0x1800666fd  mov     rbx, rdx
0x180066700  mov     r13, rsi
0x180066703  jmp     short loc_180066718
0x180066705  mov     r13, r15
0x180066708  mov     rbx, r15
0x18006670b  mov     rsi, qword ptr [rbp+80h+var_F0+8]
0x18006670f  mov     rax, qword ptr [rbp+80h+var_F0]
0x180066713  mov     [rsp+180h+var_120], rax
0x180066718  lea     rcx, [r14+110h]
0x18006671f  lea     rax, [rsp+180h+var_108]
0x180066724  cmp     rcx, rax
0x180066727  jz      short loc_18006674E
0x180066729  mov     rdi, [rcx]
0x18006672c  mov     [rcx], r15
0x18006672f  mov     qword ptr [rsp+180h+var_108], rdi
0x180066734  mov     r12, [rcx+8]
0x180066738  mov     [rcx+8], r15
0x18006673c  mov     qword ptr [rbp+80h+var_108+8], r12
0x180066740  mov     rax, [rcx+10h]
0x180066744  mov     [rcx+10h], r15
0x180066748  mov     [rbp+80h+var_F8], rax
0x18006674c  jmp     short loc_180066757
0x18006674e  mov     r12, qword ptr [rbp+80h+var_108+8]
0x180066752  mov     rdi, qword ptr [rsp+180h+var_108]
0x180066757  mov     [rsp+180h+var_130], rdi
0x18006675c  mov     [rsp+180h+var_118], r12
0x180066761  mov     rcx, [rsp+180h+SRWLock]; SRWLock
0x180066766  test    rcx, rcx
0x180066769  jz      short loc_180066771
0x18006676b  call    cs:__imp_ReleaseSRWLockExclusive
0x180066771  mov     dword ptr [rsp+180h+var_140], r15d
0x180066776  xor     r8d, r8d
0x180066779  lea     rax, WPP_GLOBAL_Control
0x180066780  cmp     rbx, r13
0x180066783  jz      loc_1800668B9
0x180066789  mov     r12d, r8d
0x18006678c  lea     rdi, WPP_GLOBAL_Control
0x180066793  lea     r14, [rbx+18h]
0x180066797  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 10h
0x18006679e  jz      short loc_1800667BA
0x1800667a0  cmp     qword ptr [r14], 7
0x1800667a4  jbe     short loc_1800667AB
0x1800667a6  mov     r8, [rbx]
0x1800667a9  jmp     short loc_1800667AE
0x1800667ab  mov     r8, rbx
0x1800667ae  lea     rdx, Package_PreRegistration_Start
0x1800667b5  call    McTemplateU0z_EventWriteTransfer
0x1800667ba  cmp     qword ptr [r14], 7
0x1800667be  jbe     short loc_1800667C5
0x1800667c0  mov     rcx, [rbx]
0x1800667c3  jmp     short loc_1800667C8
0x1800667c5  mov     rcx, rbx
0x1800667c8  mov     edx, 2
0x1800667cd  call    cs:__imp_AppxPreRegisterPackage
0x1800667d3  mov     r15d, eax
0x1800667d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667dd  cmp     rcx, rdi
0x1800667e0  jz      short loc_180066817
0x1800667e2  test    byte ptr [rcx+1Ch], 4
0x1800667e6  jz      short loc_180066817
0x1800667e8  cmp     qword ptr [r14], 7
0x1800667ec  jbe     short loc_1800667F3
0x1800667ee  mov     r9, [rbx]
0x1800667f1  jmp     short loc_1800667F6
0x1800667f3  mov     r9, rbx
0x1800667f6  mov     edx, 0Dh
0x1800667fb  mov     dword ptr [rsp+180h+var_160], r15d
0x180066800  lea     r8, WPP_fb225c8d27f6327f6fb2058d73d6f2b1_Traceguids
0x180066807  mov     rcx, [rcx+10h]
0x18006680b  call    WPP_SF_Sd
0x180066810  mov     rcx, cs:WPP_GLOBAL_Control
0x180066817  test    r15d, r15d
0x18006681a  js      short loc_18006682B
0x18006681c  mov     r15d, dword ptr [rsp+180h+var_140]
0x180066821  inc     r15d
0x180066824  mov     dword ptr [rsp+180h+var_140], r15d
0x180066829  jmp     short loc_180066860
0x18006682b  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 4
0x180066832  jz      short loc_180066858
0x180066834  cmp     qword ptr [r14], 7
0x180066838  jbe     short loc_18006683F
0x18006683a  mov     r8, [rbx]
0x18006683d  jmp     short loc_180066842
0x18006683f  mov     r8, rbx
0x180066842  mov     r9d, r15d
0x180066845  lea     rdx, Package_PreRegistration_Failure
0x18006684c  call    McTemplateU0zd_EventWriteTransfer
0x180066851  mov     rcx, cs:WPP_GLOBAL_Control
0x180066858  inc     r12d
0x18006685b  mov     r15d, dword ptr [rsp+180h+var_140]
0x180066860  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 10h
0x180066867  jz      short loc_18006688A
0x180066869  cmp     qword ptr [r14], 7
0x18006686d  jbe     short loc_180066874
0x18006686f  mov     r8, [rbx]
0x180066872  jmp     short loc_180066877
0x180066874  mov     r8, rbx
0x180066877  lea     rdx, Package_PreRegistration_Stop
0x18006687e  call    McTemplateU0z_EventWriteTransfer
0x180066883  mov     rcx, cs:WPP_GLOBAL_Control
0x18006688a  add     rbx, 20h ; ' '
0x18006688e  cmp     rbx, r13
0x180066891  jnz     loc_180066793
0x180066897  mov     dword ptr [rsp+180h+SRWLock], r12d
0x18006689c  mov     rdi, [rsp+180h+var_130]
0x1800668a1  mov     r12, [rsp+180h+var_118]
0x1800668a6  mov     r14, [rsp+180h+var_128]
0x1800668ab  mov     r8d, dword ptr [rsp+180h+SRWLock]
0x1800668b0  lea     rax, WPP_GLOBAL_Control
0x1800668b7  jmp     short loc_1800668C0
0x1800668b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800668c0  cmp     rcx, rax
0x1800668c3  jz      short loc_1800668F7
0x1800668c5  test    byte ptr [rcx+1Ch], 4
0x1800668c9  jz      short loc_1800668F7
0x1800668cb  lea     eax, [r8+r15]
0x1800668cf  mov     r9, rsi
0x1800668d2  sub     r9, [rsp+180h+var_120]
0x1800668d7  sar     r9, 5
0x1800668db  mov     edx, 0Eh
0x1800668e0  mov     dword ptr [rsp+180h+var_150], r8d
0x1800668e5  mov     dword ptr [rsp+180h+var_158], r15d
0x1800668ea  mov     dword ptr [rsp+180h+var_160], eax; int
0x1800668ee  mov     rcx, [rcx+10h]
0x1800668f2  call    WPP_SF_llll
0x1800668f7  xor     edx, edx; hFile
0x1800668f9  mov     r8d, 800h; dwFlags
0x1800668ff  lea     rcx, aAppxdeployment_1; "appxdeploymentclient.dll"
0x180066906  call    cs:__imp_LoadLibraryExW
0x18006690c  mov     [rbp+80h+var_98], rax
0x180066910  lea     rdx, aMsixpreregiste; "MsixPreRegisterUupProducts"
0x180066917  mov     rcx, rax; hModule
0x18006691a  call    cs:__imp_GetProcAddress
0x180066920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066925  mov     rcx, [rbp+88h]; this
0x18006692c  xor     r13d, r13d
0x18006692f  test    eax, eax
0x180066931  js      loc_180066E07
0x180066937  mov     [rsp+180h+var_110], r13
0x18006693c  cmp     rdi, r12
0x18006693f  jz      short loc_18006697B
0x180066941  mov     [rbp+80h+var_78], r13
0x180066945  lea     r9d, [r13+3Dh]; unsigned int
0x180066949  lea     r8d, [r13+3Eh]; unsigned int
0x18006694d  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x180066954  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x180066958  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006695d  nop
0x18006695e  lea     rdx, [rsp+180h+var_110]
0x180066963  mov     rcx, [rbp+80h+var_78]
0x180066967  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x18006696c  mov     rcx, [rbp+88h]; this
0x180066973  test    eax, eax
0x180066975  js      loc_180066E1C
0x18006697b  lea     rbx, aOnecoreuapShel_25; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180066982  jmp     loc_180066C07
0x180066987  mov     [rsp+180h+var_140], r13
0x18006698c  lea     rcx, [rsp+180h+var_140]
0x180066991  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::ensure_data(void)
0x180066996  mov     rcx, [rax]
0x180066999  add     rcx, 8
0x18006699d  lea     rdx, [rbp+80h+hstringHeader]
0x1800669a1  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800669a6  lea     rdx, [rbp+80h+var_D8]
0x1800669aa  lea     rcx, [rsp+180h+var_140]
0x1800669af  call    ??C?$tip_test@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(void)
0x1800669b4  mov     rcx, [rax]
0x1800669b7  mov     dword ptr [rcx+114h], 2
0x1800669c1  lea     rcx, [rbp+80h+var_D8]
0x1800669c5  call    ??1?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(void)
0x1800669ca  lea     rdx, [rbp+80h+var_D0]
0x1800669ce  lea     rcx, [rsp+180h+var_140]
0x1800669d3  call    ??C?$tip_test@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(void)
0x1800669d8  mov     rcx, [rax]
0x1800669db  or      dword ptr [rcx+138h], 10h
0x1800669e2  lea     rcx, [rbp+80h+var_D0]
0x1800669e6  call    ??1?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(void)
0x1800669eb  lea     rdx, [rbp+80h+var_C8]
0x1800669ef  lea     rcx, [rsp+180h+var_140]
0x1800669f4  call    ??C?$tip_test@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(void)
0x1800669f9  nop
0x1800669fa  mov     rcx, [rax]
0x1800669fd  add     rcx, 140h
0x180066a04  mov     rdx, rdi
0x180066a07  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180066a0c  nop
0x180066a0d  lea     rcx, [rbp+80h+var_C8]
0x180066a11  call    ??1?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(void)
0x180066a16  lea     rdx, [rbp+80h+var_C0]
0x180066a1a  lea     rcx, [rsp+180h+var_140]
0x180066a1f  call    ??C?$tip_test@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(void)
0x180066a24  mov     rcx, [rax]
0x180066a27  add     rcx, 100h; this
0x180066a2e  call    ?CheckEnvironment@_tip_OneTimeRegisterTest@@QEAAXXZ; _tip_OneTimeRegisterTest::CheckEnvironment(void)
0x180066a33  lea     rcx, [rbp+80h+var_C0]
0x180066a37  call    ??1?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(void)
0x180066a3c  mov     [rsp+180h+var_130], r13
0x180066a41  mov     r14, [rsp+180h+var_110]
0x180066a46  mov     rax, [r14]
0x180066a49  mov     r15, [rax+58h]
0x180066a4d  cmp     qword ptr [rdi+18h], 7
0x180066a52  jbe     short loc_180066A59
0x180066a54  mov     rax, [rdi]
0x180066a57  jmp     short loc_180066A5C
0x180066a59  mov     rax, rdi
0x180066a5c  mov     [rbp+80h+var_B8], rax
0x180066a60  lea     rdx, [rbp+80h+var_B8]
0x180066a64  lea     rcx, [rbp+80h+var_70]
0x180066a68  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180066a6d  nop
0x180066a6e  lea     rcx, [rsp+180h+var_130]
0x180066a73  mov     [rsp+180h+var_150], rcx
0x180066a78  mov     [rsp+180h+var_158], r13
0x180066a7d  mov     dword ptr [rsp+180h+var_160], 4; int
0x180066a85  mov     r9d, 200h
0x180066a8b  xor     r8d, r8d
0x180066a8e  mov     rdx, [rax+18h]
0x180066a92  mov     rcx, r14
0x180066a95  mov     rax, r15
0x180066a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a9d  mov     r14d, eax
0x180066aa0  lea     rdx, [rbp+80h+var_B0]
0x180066aa4  lea     rcx, [rsp+180h+var_140]
0x180066aa9  call    ??C?$tip_test@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(void)
0x180066aae  mov     rcx, [rax]
0x180066ab1  mov     [rcx+110h], r14d
0x180066ab8  lea     rcx, [rbp+80h+var_B0]
0x180066abc  call    ??1?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(void)
0x180066ac1  mov     rcx, [rbp+88h]; this
0x180066ac8  test    r14d, r14d
0x180066acb  js      loc_180066DF6
0x180066ad1  mov     rdx, [rsp+180h+var_130]
0x180066ad6  call    ?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z; Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)
0x180066adb  mov     r15d, eax
0x180066ade  lea     rdx, [rbp+80h+var_A8]
0x180066ae2  lea     rcx, [rsp+180h+var_140]
0x180066ae7  call    ??C?$tip_test@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::operator->(void)
0x180066aec  mov     rcx, [rax]
0x180066aef  mov     [rcx+110h], r15d
0x180066af6  lea     rcx, [rbp+80h+var_A8]
0x180066afa  call    ??1?$test_data_control@V?$merged_data@U_tip_OneTimeRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_OneTimeRegisterTest,_tip_OneTimeRegisterTest>>(void)
0x180066aff  mov     [rsp+180h+var_118], r13
0x180066b04  mov     dword ptr [rsp+180h+SRWLock], r13d
0x180066b09  mov     r8, [rsp+180h+var_130]
0x180066b0e  mov     rcx, [r8]
0x180066b11  mov     rax, [rcx+50h]
0x180066b15  lea     rdx, [rsp+180h+var_118]
0x180066b1a  mov     rcx, r8
0x180066b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b22  mov     rcx, [rbp+88h]
0x180066b29  test    eax, eax
0x180066b2b  jns     short loc_180066B34
0x180066b2d  mov     edx, 0B3h
0x180066b32  jmp     short loc_180066B5A
0x180066b34  mov     rcx, [rsp+180h+var_118]
0x180066b39  mov     rax, [rcx]
0x180066b3c  lea     rdx, [rsp+180h+SRWLock]
0x180066b41  mov     rax, [rax+40h]
0x180066b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b4a  mov     rcx, [rbp+88h]; this
0x180066b51  test    eax, eax
0x180066b53  jns     short loc_180066B65
  ... truncated ...
```
