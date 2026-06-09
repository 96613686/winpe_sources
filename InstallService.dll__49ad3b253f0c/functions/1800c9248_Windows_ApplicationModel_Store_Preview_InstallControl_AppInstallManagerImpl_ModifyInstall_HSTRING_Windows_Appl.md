# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall(HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::ModifyInstallAction,ulong,ulong,HSTRING__ *)

- ea: `0x1800c9248`
- end: `0x1800c9c25`
- name: `?_ModifyInstall@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUHSTRING__@@W4ModifyInstallAction@123456@KK0@Z`
- size: `2525`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c9c2c`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x18001c844`
- `0x180037200`
- `0x1800380fc`
- `0x18003814c`
- `0x18003b08c`
- `0x180044f4c`
- `0x1800453bc`
- `0x180045588`
- `0x18004c5d8`
- `0x18006cc00`
- `0x18006e510`
- `0x18008fc28`
- `0x1800bdd84`
- `0x1800bde08`
- `0x1800c893c`
- `0x1800c9248`
- `0x1800cd008`
- `0x1800d630c`
- `0x1801473f4`
- `0x180149670`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c9454`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c972e`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c9aac`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c9b49`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c9454`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c972e`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c9aac`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c9b49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c92c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c92c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c9295`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c9295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c92e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c99af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c92e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c99af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9356`

## string_xrefs

- `0x1800c9319`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c93e4`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c940d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c9a3d`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c9a65`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c92f9`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall`
- `0x1800c93d7`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall`
- `0x1800c9401`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall`
- `0x1800c9a30`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall`
- `0x1800c9a59`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall(
        RTL_SRWLOCK *a1,
        HSTRING a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        WindowsUpdate::CommonTelemetry *a6)
{
  RTL_SRWLOCK *v10; // r13
  PVOID Ptr; // rbx
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v12; // rcx
  char *v13; // r8
  HSTRING ClientIdIfMissing; // rbx
  int CallingProcessAndFunction; // eax
  unsigned int v16; // ebx
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v19; // rdx
  bool v20; // r8
  char *v21; // r8
  char v22; // bl
  int v23; // edi
  int v24; // edi
  int v25; // edi
  const char *v26; // r8
  int v27; // ebx
  HSTRING *v28; // rcx
  __int64 *InstallControl2; // rbx
  _QWORD *v30; // rax
  __int64 v31; // rcx
  unsigned int v32; // eax
  const char *v33; // r8
  int v34; // ebx
  __int64 *v35; // rdi
  __int64 v36; // rbx
  _QWORD *v37; // rax
  __int64 v38; // rcx
  unsigned int v39; // eax
  __int64 *v40; // rdi
  __int64 v41; // rbx
  _QWORD *v42; // rax
  __int64 v43; // rcx
  unsigned int v44; // eax
  __int64 *v45; // rdi
  __int64 v46; // rbx
  _QWORD *v47; // rax
  __int64 v48; // rcx
  unsigned int v49; // eax
  unsigned int v50; // esi
  int v51; // edi
  int v52; // edi
  int v53; // edi
  const char *v54; // r8
  __int64 (__fastcall *v55)(PVOID, HSTRING, _QWORD, _QWORD, HSTRING, __int64); // rsi
  __int64 v56; // rdi
  HSTRING v57; // rax
  __int64 (__fastcall *v58)(PVOID, HSTRING, WindowsUpdate::CommonTelemetry *); // rax
  const char *v59; // r8
  HSTRING v60; // rsi
  bool v61; // al
  __int64 (__fastcall *v62)(PVOID, HSTRING, HSTRING, __int64); // rdi
  __int64 v63; // rax
  __int64 v64; // r9
  int v65; // [rsp+20h] [rbp-2C8h]
  int v66; // [rsp+28h] [rbp-2C0h]
  int v67; // [rsp+28h] [rbp-2C0h]
  HSTRING v68; // [rsp+50h] [rbp-298h] BYREF
  char v69[8]; // [rsp+58h] [rbp-290h] BYREF
  HSTRING v70; // [rsp+60h] [rbp-288h] BYREF
  char v71[8]; // [rsp+68h] [rbp-280h] BYREF
  WindowsUpdate::CommonTelemetry *v72; // [rsp+70h] [rbp-278h] BYREF
  HSTRING string; // [rsp+78h] [rbp-270h] BYREF
  char v74[8]; // [rsp+80h] [rbp-268h] BYREF
  __int64 v75; // [rsp+88h] [rbp-260h] BYREF
  __int128 v76; // [rsp+90h] [rbp-258h]
  PVOID v77; // [rsp+A8h] [rbp-240h] BYREF
  HSTRING v78; // [rsp+B0h] [rbp-238h] BYREF
  _QWORD v79[5]; // [rsp+B8h] [rbp-230h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-208h] BYREF
  HSTRING__ v81; // [rsp+100h] [rbp-1E8h] BYREF
  WCHAR sourceString[136]; // [rsp+190h] [rbp-158h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v68 = a2;
  v72 = a6;
  v10 = a1 + 30;
  AcquireSRWLockShared(a1 + 30);
  Ptr = a1[33].Ptr;
  v77 = Ptr;
  if ( Ptr )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
  ReleaseSRWLockShared(v10);
  if ( Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(v12) )
  {
    ClientIdIfMissing = CreateClientIdIfMissing(0);
    WindowsDeleteString(0);
    string = 0;
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  ClientIdIfMissing,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall",
                                  &string);
    v16 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v65);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v77);
      return v16;
    }
    StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
    LOBYTE(v19) = 1;
    v22 = 0;
    if ( Utils::IsCallerInteractive(StringRawBuffer, v19, v20) && (a4 & 1) == 0 )
    {
      a4 |= 1u;
      v22 = 1;
    }
    if ( a3 )
    {
      v23 = a3 - 1;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( !v25 )
          {
            InstallControl2 = (__int64 *)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                                           a1,
                                           v69);
            winrt::param::hstring::hstring((winrt::param::hstring *)&hstringHeader, sourceString);
            v30 = (_QWORD *)ToWinRTType<HSTRING__ *>(&v70, &v68);
            v31 = *InstallControl2;
            LODWORD(v75) = 0;
            v76 = 0;
            v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, PVOID))(*(_QWORD *)v31 + 128LL))(
                    v31,
                    *v30,
                    hstringHeader.Reserved.Reserved1);
            winrt::check_hresult(&v68, v32, &v75);
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v70);
            v28 = (HSTRING *)v69;
            goto LABEL_25;
          }
          if ( v25 != 1 )
          {
            LogMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
              0x3D9u,
              "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall",
              -1,
              L"Assert (%s): %s",
              0,
              0);
            TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
              0x3DAu,
              "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall",
              "hr",
              0,
              v66);
LABEL_26:
            v50 = 0;
            WindowsDeleteString(string);
            goto LABEL_42;
          }
          WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a6, &v81, v21);
          WindowsUpdate::CommonTelemetry::ResumeOperationRequest(a2, &v81, v26);
          _o_mbstowcs(sourceString, &v81, 129);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::GetImpl'::`2'::impl)
            && EnableInteractiveResumeDisallowListFromOneSettings() )
          {
            v27 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                    a1,
                    &v70);
            v78 = CreateClientIdIfMissing(0);
            v75 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v69, &v78);
            v79[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v71, &v72);
            hstringHeader.Reserved.Reserved1 = *(PVOID *)ToWinRTType<HSTRING__ *>(v74, &v68);
            winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ResumeWithFlags2(
              v27,
              (unsigned int)&hstringHeader,
              a4,
              a5,
              (__int64)v79,
              (__int64)&v75);
            winrt::handle_type<winrt::impl::hstring_traits>::close(v74);
            winrt::handle_type<winrt::impl::hstring_traits>::close(v71);
            winrt::handle_type<winrt::impl::hstring_traits>::close(v69);
            v28 = &v70;
LABEL_25:
            winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v28);
            goto LABEL_26;
          }
        }
        else
        {
          WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a6, &v81, v21);
          WindowsUpdate::CommonTelemetry::ResumeOperationRequest(a2, &v81, v33);
          _o_mbstowcs(sourceString, &v81, 129);
          if ( !v22 )
          {
            v35 = (__int64 *)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                               a1,
                               v74);
            winrt::param::hstring::hstring((winrt::param::hstring *)&hstringHeader, sourceString);
            v70 = CreateClientIdIfMissing(0);
            v36 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v71, &v70);
            v37 = (_QWORD *)ToWinRTType<HSTRING__ *>(v69, &v68);
            v38 = *v35;
            LODWORD(v75) = 0;
            v76 = 0;
            v39 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, PVOID))(*(_QWORD *)v38 + 120LL))(
                    v38,
                    *v37,
                    v36,
                    hstringHeader.Reserved.Reserved1);
            winrt::check_hresult(&v68, v39, &v75);
            winrt::handle_type<winrt::impl::hstring_traits>::close(v69);
            winrt::handle_type<winrt::impl::hstring_traits>::close(v71);
            v28 = (HSTRING *)v74;
            goto LABEL_25;
          }
        }
        v34 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                a1,
                v71);
        hstringHeader.Reserved.Reserved1 = *(PVOID *)ToWinRTType<HSTRING__ *>(v69, &v72);
        v79[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(&v70, &v68);
        winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ResumeWithFlags(
          v34,
          (unsigned int)v79,
          a4,
          a5,
          (__int64)&hstringHeader);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v70);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v69);
      }
      else
      {
        v40 = (__int64 *)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                           a1,
                           v71);
        v41 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v69, &v72);
        v42 = (_QWORD *)ToWinRTType<HSTRING__ *>(&v70, &v68);
        v43 = *v40;
        LODWORD(v75) = 0;
        v76 = 0;
        v44 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v43 + 112LL))(v43, *v42, v41);
        winrt::check_hresult(&v68, v44, &v75);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v70);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v69);
      }
    }
    else
    {
      v45 = (__int64 *)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                         a1,
                         v71);
      v46 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v69, &v72);
      v47 = (_QWORD *)ToWinRTType<HSTRING__ *>(&v70, &v68);
      v48 = *v45;
      LODWORD(v75) = 0;
      v76 = 0;
      v49 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v48 + 104LL))(v48, *v47, v46);
      winrt::check_hresult(&v68, v49, &v75);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v70);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v69);
    }
    v28 = (HSTRING *)v71;
    goto LABEL_25;
  }
  v50 = -2147024809;
  if ( Ptr )
  {
    if ( a3 )
    {
      v51 = a3 - 1;
      if ( v51 )
      {
        v52 = v51 - 1;
        if ( !v52 )
        {
          WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a6, &v81, v13);
          WindowsUpdate::CommonTelemetry::ResumeOperationRequest(a2, &v81, v59);
          _o_mbstowcs(sourceString, &v81, 129);
          v60 = CreateClientIdIfMissing(0);
          v61 = StringHelpers::Equal(v60, L"Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy", 1);
          v62 = *(__int64 (__fastcall **)(PVOID, HSTRING, HSTRING, __int64))(*(_QWORD *)Ptr + 56LL);
          if ( v61 )
          {
            v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
            v50 = v62(Ptr, a2, v60, *(_QWORD *)(v63 + 24));
          }
          else
          {
            v64 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString)
                            + 24);
            v50 = v62(Ptr, a2, v60, v64);
          }
          goto LABEL_42;
        }
        v53 = v52 - 1;
        if ( v53 )
        {
          if ( v53 == 1 )
          {
            WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a6, &v81, v13);
            WindowsUpdate::CommonTelemetry::ResumeOperationRequest(a2, &v81, v54);
            _o_mbstowcs(sourceString, &v81, 129);
            v55 = *(__int64 (__fastcall **)(PVOID, HSTRING, _QWORD, _QWORD, HSTRING, __int64))(*(_QWORD *)Ptr + 136LL);
            v56 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString)
                            + 24);
            v57 = CreateClientIdIfMissing(0);
            v50 = v55(Ptr, a2, a4, a5, v57, v56);
          }
          else
          {
            LogMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
              0x40Du,
              "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall",
              -1,
              L"Assert (%s): %s",
              0,
              0);
            TraceHR(
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
              0x40Eu,
              "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ModifyInstall",
              "hr",
              -2147024809,
              v67);
          }
          goto LABEL_42;
        }
        v58 = *(__int64 (__fastcall **)(PVOID, HSTRING, WindowsUpdate::CommonTelemetry *))(*(_QWORD *)Ptr + 72LL);
      }
      else
      {
        v58 = *(__int64 (__fastcall **)(PVOID, HSTRING, WindowsUpdate::CommonTelemetry *))(*(_QWORD *)Ptr + 48LL);
      }
    }
    else
    {
      v58 = *(__int64 (__fastcall **)(PVOID, HSTRING, WindowsUpdate::CommonTelemetry *))(*(_QWORD *)Ptr + 64LL);
    }
    v50 = v58(Ptr, a2, a6);
  }
LABEL_42:
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v77);
  return v50;
}

```

## disassembly

```asm
0x1800c9248  push    rbx
0x1800c924a  push    rsi
0x1800c924b  push    rdi
0x1800c924c  push    r12
0x1800c924e  push    r13
0x1800c9250  push    r14
0x1800c9252  push    r15
0x1800c9254  sub     rsp, 2B0h
0x1800c925b  mov     rax, cs:__security_cookie
0x1800c9262  xor     rax, rsp
0x1800c9265  mov     [rsp+2E8h+var_48], rax
0x1800c926d  mov     r12d, r9d
0x1800c9270  mov     edi, r8d
0x1800c9273  mov     r14, rdx
0x1800c9276  mov     rsi, rcx
0x1800c9279  mov     [rsp+2E8h+var_298], rdx
0x1800c927e  mov     r15, [rsp+2E8h+arg_28]
0x1800c9286  mov     [rsp+2E8h+var_278], r15
0x1800c928b  lea     r13, [rcx+0F0h]
0x1800c9292  mov     rcx, r13; SRWLock
0x1800c9295  call    cs:__imp_AcquireSRWLockShared
0x1800c929b  mov     rbx, [rsi+108h]
0x1800c92a2  mov     [rsp+2E8h+var_240], rbx
0x1800c92aa  test    rbx, rbx
0x1800c92ad  jz      short loc_1800C92BF
0x1800c92af  mov     rax, [rbx]
0x1800c92b2  mov     rcx, rbx
0x1800c92b5  mov     rax, [rax+8]
0x1800c92b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c92be  nop
0x1800c92bf  mov     rcx, r13; SRWLock
0x1800c92c2  call    cs:__imp_ReleaseSRWLockShared
0x1800c92c8  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x1800c92cd  xor     r13d, r13d
0x1800c92d0  test    al, al
0x1800c92d2  jz      loc_1800C99C4
0x1800c92d8  xor     ecx, ecx; HSTRING
0x1800c92da  call    ?CreateClientIdIfMissing@@YAPEAUHSTRING__@@PEAU1@@Z; CreateClientIdIfMissing(HSTRING__ *)
0x1800c92df  mov     rbx, rax
0x1800c92e2  mov     [rsp+2E8h+string], r13
0x1800c92e7  xor     ecx, ecx; string
0x1800c92e9  call    cs:__imp_WindowsDeleteString
0x1800c92ef  mov     [rsp+2E8h+string], r13
0x1800c92f4  lea     r8, [rsp+2E8h+string]; HSTRING *
0x1800c92f9  lea     rdx, aWindowsApplica_118; "Windows::ApplicationModel::Store::Previ"...
0x1800c9300  mov     rcx, rbx; HSTRING
0x1800c9303  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c9308  mov     ebx, eax
0x1800c930a  test    eax, eax
0x1800c930c  jns     short loc_1800C934F
0x1800c930e  mov     rcx, [rsp+2E8h]; this
0x1800c9316  mov     r9d, eax; char *
0x1800c9319  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c9320  mov     edx, 3A2h; void *
0x1800c9325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c932a  nop
0x1800c932b  mov     rcx, [rsp+2E8h+string]; string
0x1800c9330  call    cs:__imp_WindowsDeleteString
0x1800c9336  mov     [rsp+2E8h+string], r13
0x1800c933b  lea     rcx, [rsp+2E8h+var_240]
0x1800c9343  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c9348  mov     eax, ebx
0x1800c934a  jmp     loc_1800C9C02
0x1800c934f  xor     edx, edx; length
0x1800c9351  mov     rcx, [rsp+2E8h+string]; string
0x1800c9356  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c935c  mov     rcx, rax; Str
0x1800c935f  mov     dl, 1; unsigned __int16 *
0x1800c9361  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c9366  mov     bl, r13b
0x1800c9369  test    al, al
0x1800c936b  jz      short loc_1800C9379
0x1800c936d  test    r12b, 1
0x1800c9371  jnz     short loc_1800C9379
0x1800c9373  or      r12d, 1
0x1800c9377  mov     bl, 1
0x1800c9379  test    edi, edi
0x1800c937b  jz      loc_1800C9913
0x1800c9381  sub     edi, 1
0x1800c9384  jz      loc_1800C9885
0x1800c938a  sub     edi, 1
0x1800c938d  jz      loc_1800C96F8
0x1800c9393  sub     edi, 1
0x1800c9396  jz      loc_1800C9666
0x1800c939c  cmp     edi, 1
0x1800c939f  jz      short loc_1800C941E
0x1800c93a1  lea     rax, aFailed_1; "Failed"
0x1800c93a8  mov     [rsp+2E8h+var_2A0], rax
0x1800c93ad  lea     rax, aFalse_0; "false"
0x1800c93b4  mov     [rsp+2E8h+var_2A8], rax
0x1800c93b9  mov     [rsp+2E8h+var_2B0], r13; unsigned __int16 *
0x1800c93be  mov     [rsp+2E8h+var_2B8], r13; char *
0x1800c93c3  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800c93ca  mov     [rsp+2E8h+var_2C0], rax; int
0x1800c93cf  mov     [rsp+2E8h+var_2C8], 0FFFFFFFFh; int
0x1800c93d7  lea     r9, aWindowsApplica_103; "Windows::ApplicationModel::Store::Previ"...
0x1800c93de  mov     r8d, 3D9h; unsigned int
0x1800c93e4  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c93eb  mov     ecx, 1; unsigned int
0x1800c93f0  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c93f5  mov     [rsp+2E8h+var_2C8], r13d; int
0x1800c93fa  lea     r9, aHr; "hr"
0x1800c9401  lea     r8, aWindowsApplica_103; "Windows::ApplicationModel::Store::Previ"...
0x1800c9408  mov     edx, 3DAh; unsigned int
0x1800c940d  lea     rcx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c9414  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800c9419  jmp     loc_1800C99A7
0x1800c941e  lea     rdx, [rsp+2E8h+var_1E8]; HSTRING
0x1800c9426  mov     rcx, r15; this
0x1800c9429  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c942e  lea     rdx, [rsp+2E8h+var_1E8]; HSTRING
0x1800c9436  mov     rcx, r14; string
0x1800c9439  call    ?ResumeOperationRequest@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@PEBD@Z; WindowsUpdate::CommonTelemetry::ResumeOperationRequest(HSTRING__ *,char const *)
0x1800c943e  mov     r8d, 81h
0x1800c9444  lea     rdx, [rsp+2E8h+var_1E8]
0x1800c944c  lea     rcx, [rsp+2E8h+sourceString]
0x1800c9454  call    cs:__imp__o_mbstowcs
0x1800c945a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InteractivityRegulationForResume@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InteractivityRegulationForResume@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InteractivityRegulationForResume> `wil::Feature<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::GetImpl(void)'::`2'::impl
0x1800c9461  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InteractivityRegulationForResume@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::__private_IsEnabled(void)
0x1800c9466  test    al, al
0x1800c9468  jz      loc_1800C95DC
0x1800c946e  call    ?EnableInteractiveResumeDisallowListFromOneSettings@@YA_NXZ; EnableInteractiveResumeDisallowListFromOneSettings(void)
0x1800c9473  mov     rcx, rsi
0x1800c9476  test    al, al
0x1800c9478  jz      loc_1800C9555
0x1800c947e  lea     rdx, [rsp+2E8h+var_288]
0x1800c9483  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800c9488  mov     rbx, rax
0x1800c948b  xor     ecx, ecx; HSTRING
0x1800c948d  call    ?CreateClientIdIfMissing@@YAPEAUHSTRING__@@PEAU1@@Z; CreateClientIdIfMissing(HSTRING__ *)
0x1800c9492  mov     [rsp+2E8h+var_238], rax
0x1800c949a  lea     rdx, [rsp+2E8h+var_238]
0x1800c94a2  lea     rcx, [rsp+2E8h+var_290]
0x1800c94a7  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c94ac  nop
0x1800c94ad  mov     rax, [rax]
0x1800c94b0  mov     [rsp+2E8h+var_260], rax
0x1800c94b8  lea     rdx, [rsp+2E8h+var_278]
0x1800c94bd  lea     rcx, [rsp+2E8h+var_280]
0x1800c94c2  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c94c7  nop
0x1800c94c8  mov     rax, [rax]
0x1800c94cb  mov     [rsp+2E8h+var_230], rax
0x1800c94d3  lea     rdx, [rsp+2E8h+var_298]
0x1800c94d8  lea     rcx, [rsp+2E8h+var_268]
0x1800c94e0  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c94e5  nop
0x1800c94e6  mov     rax, [rax]
0x1800c94e9  mov     qword ptr [rsp+2E8h+hstringHeader.Reserved], rax
0x1800c94f1  lea     rax, [rsp+2E8h+var_260]
0x1800c94f9  mov     [rsp+2E8h+var_2C0], rax
0x1800c94fe  lea     rax, [rsp+2E8h+var_230]
0x1800c9506  mov     qword ptr [rsp+2E8h+var_2C8], rax
0x1800c950b  mov     r9d, [rsp+2E8h+arg_20]
0x1800c9513  mov     r8d, r12d
0x1800c9516  lea     rdx, [rsp+2E8h+hstringHeader]
0x1800c951e  mov     rcx, rbx
0x1800c9521  call    ?ResumeWithFlags2@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@II00@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ResumeWithFlags2(winrt::param::hstring const &,uint,uint,winrt::param::hstring const &,winrt::param::hstring const &)
0x1800c9526  nop
0x1800c9527  lea     rcx, [rsp+2E8h+var_268]
0x1800c952f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c9534  nop
0x1800c9535  lea     rcx, [rsp+2E8h+var_280]
0x1800c953a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c953f  nop
0x1800c9540  lea     rcx, [rsp+2E8h+var_290]
0x1800c9545  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c954a  nop
0x1800c954b  lea     rcx, [rsp+2E8h+var_288]
0x1800c9550  jmp     loc_1800C99A1
0x1800c9555  lea     rdx, [rsp+2E8h+var_280]
0x1800c955a  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800c955f  mov     rbx, rax
0x1800c9562  lea     rdx, [rsp+2E8h+var_278]
0x1800c9567  lea     rcx, [rsp+2E8h+var_290]
0x1800c956c  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c9571  nop
0x1800c9572  mov     rax, [rax]
0x1800c9575  mov     qword ptr [rsp+2E8h+hstringHeader.Reserved], rax
0x1800c957d  lea     rdx, [rsp+2E8h+var_298]
0x1800c9582  lea     rcx, [rsp+2E8h+var_288]
0x1800c9587  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c958c  nop
0x1800c958d  mov     rax, [rax]
0x1800c9590  mov     [rsp+2E8h+var_230], rax
0x1800c9598  lea     rax, [rsp+2E8h+hstringHeader]
0x1800c95a0  mov     qword ptr [rsp+2E8h+var_2C8], rax
0x1800c95a5  mov     r9d, [rsp+2E8h+arg_20]
0x1800c95ad  mov     r8d, r12d
0x1800c95b0  lea     rdx, [rsp+2E8h+var_230]
0x1800c95b8  mov     rcx, rbx
0x1800c95bb  call    ?ResumeWithFlags@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@II0@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ResumeWithFlags(winrt::param::hstring const &,uint,uint,winrt::param::hstring const &)
0x1800c95c0  nop
0x1800c95c1  lea     rcx, [rsp+2E8h+var_288]
0x1800c95c6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c95cb  nop
0x1800c95cc  lea     rcx, [rsp+2E8h+var_290]
0x1800c95d1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c95d6  nop
0x1800c95d7  jmp     loc_1800C999C
0x1800c95dc  lea     rdx, [rsp+2E8h+var_280]
0x1800c95e1  mov     rcx, rsi
0x1800c95e4  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800c95e9  mov     rbx, rax
0x1800c95ec  lea     rdx, [rsp+2E8h+var_278]
0x1800c95f1  lea     rcx, [rsp+2E8h+var_290]
0x1800c95f6  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c95fb  nop
0x1800c95fc  mov     rax, [rax]
0x1800c95ff  mov     qword ptr [rsp+2E8h+hstringHeader.Reserved], rax
0x1800c9607  lea     rdx, [rsp+2E8h+var_298]
0x1800c960c  lea     rcx, [rsp+2E8h+var_288]
0x1800c9611  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c9616  nop
0x1800c9617  mov     rax, [rax]
0x1800c961a  mov     [rsp+2E8h+var_230], rax
0x1800c9622  lea     rax, [rsp+2E8h+hstringHeader]
0x1800c962a  mov     qword ptr [rsp+2E8h+var_2C8], rax
0x1800c962f  mov     r9d, [rsp+2E8h+arg_20]
0x1800c9637  mov     r8d, r12d
0x1800c963a  lea     rdx, [rsp+2E8h+var_230]
0x1800c9642  mov     rcx, rbx
0x1800c9645  call    ?ResumeWithFlags@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@II0@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ResumeWithFlags(winrt::param::hstring const &,uint,uint,winrt::param::hstring const &)
0x1800c964a  nop
0x1800c964b  lea     rcx, [rsp+2E8h+var_288]
0x1800c9650  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c9655  nop
0x1800c9656  lea     rcx, [rsp+2E8h+var_290]
0x1800c965b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c9660  nop
0x1800c9661  jmp     loc_1800C999C
0x1800c9666  lea     rdx, [rsp+2E8h+var_290]
0x1800c966b  mov     rcx, rsi
0x1800c966e  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800c9673  mov     rbx, rax
0x1800c9676  lea     rdx, [rsp+2E8h+sourceString]; unsigned __int16 *
0x1800c967e  lea     rcx, [rsp+2E8h+hstringHeader]; this
0x1800c9686  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800c968b  lea     rdx, [rsp+2E8h+var_298]
0x1800c9690  lea     rcx, [rsp+2E8h+var_288]
0x1800c9695  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c969a  mov     r9, rax
0x1800c969d  mov     rcx, [rbx]
0x1800c96a0  mov     dword ptr [rsp+2E8h+var_260], r13d
0x1800c96a8  xorps   xmm0, xmm0
0x1800c96ab  movdqu  [rsp+2E8h+var_258], xmm0
0x1800c96b4  mov     rdx, [rcx]
0x1800c96b7  mov     rax, [rdx+80h]
0x1800c96be  mov     r8, qword ptr [rsp+2E8h+hstringHeader.Reserved]
0x1800c96c6  mov     rdx, [r9]
0x1800c96c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c96ce  lea     r8, [rsp+2E8h+var_260]
0x1800c96d6  mov     edx, eax
0x1800c96d8  lea     rcx, [rsp+2E8h+var_298]
0x1800c96dd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800c96e2  nop
0x1800c96e3  lea     rcx, [rsp+2E8h+var_288]
0x1800c96e8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c96ed  nop
0x1800c96ee  lea     rcx, [rsp+2E8h+var_290]
0x1800c96f3  jmp     loc_1800C99A1
0x1800c96f8  lea     rdx, [rsp+2E8h+var_1E8]; HSTRING
0x1800c9700  mov     rcx, r15; this
0x1800c9703  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c9708  lea     rdx, [rsp+2E8h+var_1E8]; HSTRING
0x1800c9710  mov     rcx, r14; string
0x1800c9713  call    ?ResumeOperationRequest@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@PEBD@Z; WindowsUpdate::CommonTelemetry::ResumeOperationRequest(HSTRING__ *,char const *)
0x1800c9718  mov     r8d, 81h
0x1800c971e  lea     rdx, [rsp+2E8h+var_1E8]
0x1800c9726  lea     rcx, [rsp+2E8h+sourceString]
0x1800c972e  call    cs:__imp__o_mbstowcs
0x1800c9734  mov     rcx, rsi
0x1800c9737  test    bl, bl
0x1800c9739  jz      loc_1800C97C6
0x1800c973f  lea     rdx, [rsp+2E8h+var_280]
0x1800c9744  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800c9749  mov     rbx, rax
0x1800c974c  lea     rdx, [rsp+2E8h+var_278]
0x1800c9751  lea     rcx, [rsp+2E8h+var_290]
0x1800c9756  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c975b  nop
0x1800c975c  mov     rax, [rax]
0x1800c975f  mov     qword ptr [rsp+2E8h+hstringHeader.Reserved], rax
0x1800c9767  lea     rdx, [rsp+2E8h+var_298]
0x1800c976c  lea     rcx, [rsp+2E8h+var_288]
0x1800c9771  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c9776  nop
0x1800c9777  mov     rax, [rax]
0x1800c977a  mov     [rsp+2E8h+var_230], rax
0x1800c9782  lea     rax, [rsp+2E8h+hstringHeader]
0x1800c978a  mov     qword ptr [rsp+2E8h+var_2C8], rax
0x1800c978f  mov     r9d, [rsp+2E8h+arg_20]
0x1800c9797  mov     r8d, r12d
0x1800c979a  lea     rdx, [rsp+2E8h+var_230]
0x1800c97a2  mov     rcx, rbx
0x1800c97a5  call    ?ResumeWithFlags@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@II0@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::ResumeWithFlags(winrt::param::hstring const &,uint,uint,winrt::param::hstring const &)
0x1800c97aa  nop
0x1800c97ab  lea     rcx, [rsp+2E8h+var_288]
0x1800c97b0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c97b5  nop
  ... truncated ...
```
