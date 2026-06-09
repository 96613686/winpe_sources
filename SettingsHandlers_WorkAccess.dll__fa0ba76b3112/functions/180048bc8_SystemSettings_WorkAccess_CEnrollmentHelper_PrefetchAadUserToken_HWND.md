# SystemSettings::WorkAccess::CEnrollmentHelper::PrefetchAadUserToken(HWND__ *)

- ea: `0x180048bc8`
- end: `0x18004a065`
- name: `?PrefetchAadUserToken@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJPEAUHWND__@@@Z`
- size: `5277`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800317bc`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x180042600`
- `0x1800444b4`
- `0x180044508`
- `0x180044560`
- `0x1800445b8`
- `0x180044610`
- `0x180044718`
- `0x180044770`
- `0x180044870`
- `0x1800448c0`
- `0x180044908`
- `0x180044950`
- `0x180044994`
- `0x180045360`
- `0x180045818`
- `0x1800459f8`
- `0x180048bc8`
- `0x18004d150`
- `0x180052010`

## import_xrefs

- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x180048f8b`
- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x180048f8b`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180048ffe`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180048ffe`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180048c50`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180048c50`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180049062`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180049062`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x180048edc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x180048edc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x180048ef2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x180048ef2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800490ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800490ee`

## string_xrefs

- `0x180048c95`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048d3f`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048dae`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048e5c`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048f34`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048fa7`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004901a`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004907e`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004910a`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004917b`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x1800491e6`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004925c`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x1800492f4`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049372`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049401`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x1800494d5`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049582`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049663`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049744`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004982a`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049948`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049a7c`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049b93`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049ca6`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049dc9`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180049f71`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::PrefetchAadUserToken(HWND Window)
{
  int v2; // esi
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 *); // rbx
  int v5; // eax
  signed int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  HWND DesktopWindow; // rbx
  int v15; // eax
  int EnrollmentPartnerOpaqueID; // eax
  int EnrollmentAadResourceUrl; // eax
  int v18; // eax
  HRESULT v19; // eax
  int v20; // eax
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  _QWORD *v23; // rax
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v27)[26]; // rdx
  _QWORD *v28; // rax
  int v29; // eax
  int v30; // eax
  const unsigned __int16 *v31; // rdx
  _QWORD *v32; // rax
  int v33; // eax
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, __int64, _QWORD, __int64); // rdi
  const unsigned __int16 (*v36)[37]; // rdx
  __int64 v37; // rbx
  const unsigned __int16 (*v38)[1]; // rdx
  _QWORD *v39; // rax
  int v40; // eax
  int v41; // eax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rsi
  __int64 (__fastcall *v45)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v46; // rbx
  const unsigned __int16 (*v47)[26]; // rdx
  _QWORD *v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rsi
  __int64 (__fastcall *v53)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v54; // rbx
  const unsigned __int16 (*v55)[33]; // rdx
  _QWORD *v56; // rax
  int v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rsi
  __int64 (__fastcall *v60)(__int64, _QWORD, HSTRING, _BYTE *); // rdi
  HSTRING v61; // rbx
  const unsigned __int16 (*v62)[9]; // rdx
  _QWORD *v63; // rax
  int v64; // eax
  __int64 v65; // rcx
  __int64 v66; // rdi
  int (__fastcall *v67)(__int64, __int64, HSTRING, HSTRING *); // rbx
  int v68; // eax
  __int64 v69; // rcx
  _QWORD *v70; // rdi
  __int64 v71; // rax
  __int64 (__fastcall *v72)(_QWORD *, HWND, __int64, __int64); // rbx
  int v73; // eax
  __int64 (__fastcall *v74)(_QWORD *, HWND, __int64, GUID *); // rbx
  __int64 v75; // rcx
  __int64 v76; // rdi
  int v77; // eax
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rdi
  __int64 (__fastcall *v81)(__int64, HSTRING *); // rbx
  int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // rcx
  bool v85; // sf
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  GUID *ppvb; // [rsp+20h] [rbp-E0h]
  __int64 v96; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v97; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v98[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v99; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v100; // [rsp+60h] [rbp-A0h] BYREF
  char v101; // [rsp+68h] [rbp-98h] BYREF
  char v102; // [rsp+69h] [rbp-97h] BYREF
  __int64 v103; // [rsp+70h] [rbp-90h] BYREF
  __int64 v104; // [rsp+78h] [rbp-88h] BYREF
  __int64 v105; // [rsp+80h] [rbp-80h] BYREF
  __int64 v106; // [rsp+88h] [rbp-78h] BYREF
  __int64 v107; // [rsp+90h] [rbp-70h] BYREF
  __int64 v108; // [rsp+98h] [rbp-68h] BYREF
  int v109[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v110; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v111; // [rsp+B0h] [rbp-50h] BYREF
  int v112; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v113[6]; // [rsp+C0h] [rbp-40h] BYREF
  char v114; // [rsp+F0h] [rbp-10h]
  LPVOID v115; // [rsp+F8h] [rbp-8h] BYREF
  int v116; // [rsp+100h] [rbp+0h] BYREF
  int v117; // [rsp+104h] [rbp+4h] BYREF
  char *v118; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v119; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v120; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v121[2]; // [rsp+120h] [rbp+20h] BYREF
  HSTRING string[4]; // [rsp+130h] [rbp+30h] BYREF
  HSTRING v123[4]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v124; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v115 = 0;
  v121[0] = 0;
  v102 = 0;
  v101 = 0;
  v120 = 0;
  v119 = 0;
  v113[0] = &v115;
  v113[1] = &v102;
  v113[2] = v121;
  v113[3] = &v101;
  v113[4] = &v120;
  v113[5] = &v119;
  v2 = 1;
  v114 = 1;
  v97 = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
  v5 = v4(DatabaseManagerInstance, 88088672, &v97);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v96 = 0;
    v99 = 0;
    v7 = v97;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v97 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    v9 = v8(v7, &v96);
    v6 = v9;
    if ( v9 == 1 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
LABEL_5:
      v6 = v2;
      goto LABEL_112;
    }
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32A,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v9,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v116 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v96 + 48LL))(v96, &v116);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32F,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v10,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    if ( ((v116 - 24) & 0xFFFFFFFD) == 0 )
    {
      v11 = v97;
      v12 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v97 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      if ( v12(v11, &v99) >= 0 )
      {
        v112 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v99 + 48LL))(v99, &v112);
        v6 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x335,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v13,
            ppv);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
          v114 = 0;
          lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
          goto LABEL_112;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl'::`2'::impl)
          && v112 == 13
          || v112 == 6 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
          Microsoft::WRL::ComPtr<IEnrollmentInfo>::operator=(&v96, &v99);
        }
      }
    }
    if ( !Window )
    {
      DesktopWindow = GetDesktopWindow();
      Window = GetWindow(DesktopWindow, 6u);
      if ( !Window )
        Window = DesktopWindow;
    }
    v124 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v96 + 24LL))(v96, &v124);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x355,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v15,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    *(_OWORD *)string = v124;
    EnrollmentPartnerOpaqueID = GetEnrollmentPartnerOpaqueID(string, &v119);
    v6 = EnrollmentPartnerOpaqueID;
    if ( EnrollmentPartnerOpaqueID < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x357,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)EnrollmentPartnerOpaqueID,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    *(_OWORD *)string = v124;
    EnrollmentAadResourceUrl = GetEnrollmentAadResourceUrl(string, &v120);
    v6 = EnrollmentAadResourceUrl;
    if ( EnrollmentAadResourceUrl < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x358,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)EnrollmentAadResourceUrl,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v18 = RoInitialize(1);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v18,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v101 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115);
    v19 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v115);
    v6 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x360,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v19,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v20 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD *))(*(_QWORD *)v115 + 32LL))(v115, 5, v121);
    v6 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x361,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v20,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v21 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v115 + 24LL))(v115, 5, 1);
    v6 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x362,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v21,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v102 = 1;
    v103 = 0;
    v23 = (_QWORD *)Windows::Internal::StringReference::StringReference(v123, (const unsigned __int16 (*)[70])v22);
    v24 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
            *v23,
            &v103);
    v6 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v24,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v104 = 0;
    v25 = v103;
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v103 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
    v28 = (_QWORD *)Windows::Internal::StringReference::StringReference(v123, v27);
    v29 = v26(v25, *v28, &v104);
    v6 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x369,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v29,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v106 = 0;
    v30 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
            v104,
            &v106);
    v6 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36C,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v30,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v107 = 0;
    v32 = (_QWORD *)Windows::Internal::StringReference::StringReference(v123, (const unsigned __int16 (*)[57])v31);
    v33 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
            *v32,
            &v107);
    v6 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36F,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v33,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v105 = 0;
    v34 = v107;
    v35 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v107 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v37 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v123, v36);
    v39 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v38);
    v40 = v35(v34, v106, *v39, v37);
    v6 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v40,
        0);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      v114 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
      goto LABEL_112;
    }
    v100 = 0;
    v98[0] = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v105 + 80LL))(v105, &v100);
    v6 = v41;
    if ( v41 >= 0 )
    {
      v44 = v100;
      v45 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v100 + 80LL);
      v46 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v123, (const unsigned __int16 (*)[1])v42);
      v48 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v47);
      v49 = v45(v44, *v48, v46, v98);
      v6 = v49;
      if ( v49 >= 0 )
      {
        v52 = v100;
        v53 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v100 + 80LL);
        v54 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v123, (const unsigned __int16 (*)[33])v50);
        v56 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v55);
        v57 = v53(v52, *v56, v54, v98);
        v6 = v57;
        if ( v57 >= 0 )
        {
          v59 = v100;
          v60 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _BYTE *))(*(_QWORD *)v100 + 80LL);
          Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v120);
          v61 = string[0];
          v63 = (_QWORD *)Windows::Internal::StringReference::StringReference(v123, v62);
          v64 = v60(v59, *v63, v61, v98);
          v6 = v64;
          if ( v64 >= 0 )
          {
            v111 = 0;
            if ( v119 )
            {
              string[0] = 0;
              v66 = v103;
              v67 = *(int (__fastcall **)(__int64, __int64, HSTRING, HSTRING *))(*(_QWORD *)v103 + 80LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
              Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v123, v119);
              if ( v67(v66, v106, v123[0], string) >= 0 )
                BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(
                  string[0],
                  &v111);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
            }
            v110 = 0;
            v68 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>::As<IWebAuthenticationCoreManagerInterop>(
                    &v103,
                    &v110);
            v6 = v68;
            if ( v68 >= 0 )
            {
              *(_QWORD *)v109 = 0;
              v70 = v110;
              v71 = *v110;
              if ( v111 )
              {
                v72 = *(__int64 (__fastcall **)(_QWORD *, HWND, __int64, __int64))(v71 + 56);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                ppvb = &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9;
                v73 = v72(v70, Window, v105, v111);
              }
              else
              {
                v74 = *(__int64 (__fastcall **)(_QWORD *, HWND, __int64, GUID *))(v71 + 48);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                ppvb = (GUID *)v109;
                v73 = v74(v70, Window, v105, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
              }
              v2 = v73;
              if ( v73 >= 0 )
              {
                v108 = 0;
                v76 = *(_QWORD *)v109;
                v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(*(_QWORD *)v109);
                if ( v6 < 0
                  || (v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v76 + 64LL))(v76, &v108), v6 < 0) )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x395,
                    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                    (const char *)(unsigned int)v6,
                    (int)ppvb);
                  v90 = v108;
                  if ( v108 )
                  {
                    v108 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                  }
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
                  v91 = v100;
                  if ( v100 )
                  {
                    v100 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                  }
                  goto LABEL_111;
                }
                v117 = 0;
                v77 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v108 + 56LL))(v108, &v117);
                v6 = v77;
                if ( v77 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x398,
                    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                    (const char *)(unsigned int)v77,
                    (int)ppvb);
                  v78 = v108;
                  if ( v108 )
                  {
                    v108 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
                  }
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
                  v79 = v100;
                  if ( v100 )
                  {
                    v100 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
                  }
                  goto LABEL_111;
                }
                if ( v117 )
                {
                  string[0] = 0;
                  v80 = v108;
                  v81 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v108 + 64LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
                  v82 = v81(v80, string);
                  v6 = v82;
                  if ( v82 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x39D,
                      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                      (const char *)(unsigned int)v82,
                      (int)ppvb);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
                    v83 = v108;
                    if ( v108 )
                    {
                      v108 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
                    }
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
                    v84 = v100;
                    if ( v100 )
                    {
                      v100 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                    }
                    goto LABEL_111;
                  }
                  if ( string[0] )
                  {
                    LODWORD(v118) = 0;
                    if ( (*(int (__fastcall **)(HSTRING, char **))(*(_QWORD *)string[0] + 48LL))(string[0], &v118) >= 0 )
                    {
                      v6 = (int)v118;
                      v85 = (int)v118 < 0;
                      if ( (int)v118 > 0 )
                      {
                        v6 = (unsigned __int16)v118 | 0x80070000;
                        v85 = 1;
                      }
                      if ( v85 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x3A3,
                          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                          (const char *)(unsigned int)v6,
                          (int)ppvb);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
                        v86 = v108;
                        if ( v108 )
                        {
                          v108 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
                        }
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
                        v87 = v100;
                        if ( v100 )
                        {
                          v100 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
                        }
                        goto LABEL_111;
                      }
                    }
                  }
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
                }
                v88 = v108;
                if ( v108 )
                {
                  v108 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
                v89 = v100;
                if ( v100 )
                {
                  v100 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x392,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                  (const char *)(unsigned int)v73,
                  (int)ppvb);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v109);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
                v75 = v100;
                if ( v100 )
                {
                  v100 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
                }
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
              v114 = 0;
              lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
              goto LABEL_5;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x38C,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
              (const char *)(unsigned int)v68,
              0);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
            v69 = v100;
            if ( v100 )
            {
              v100 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37E,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
              (const char *)(unsigned int)v64,
              0);
            v65 = v100;
            if ( v100 )
            {
              v100 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37D,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v57,
            0);
          v58 = v100;
          if ( v100 )
          {
            v100 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37C,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
          (const char *)(unsigned int)v49,
          0);
        v51 = v100;
        if ( v100 )
        {
          v100 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37B,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v41,
        0);
      v43 = v100;
      if ( v100 )
      {
        v100 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
    }
LABEL_111:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    v114 = 0;
    lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
    goto LABEL_112;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x320,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)(unsigned int)v5,
    ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
  v114 = 0;
  lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v113);
LABEL_112:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180048bc8  push    rbp
0x180048bca  push    rbx
0x180048bcb  push    rsi
0x180048bcc  push    rdi
0x180048bcd  push    r14
0x180048bcf  push    r15
0x180048bd1  lea     rbp, [rsp-98h]
0x180048bd9  sub     rsp, 198h
0x180048be0  mov     rax, cs:__security_cookie
0x180048be7  xor     rax, rsp
0x180048bea  mov     [rbp+0C0h+var_40], rax
0x180048bf1  mov     r14, rcx
0x180048bf4  xor     r15d, r15d
0x180048bf7  mov     [rbp+0C0h+var_C8], r15
0x180048bfb  mov     [rbp+0C0h+var_A0], r15
0x180048bff  mov     [rsp+1C0h+var_157], r15b
0x180048c04  mov     [rsp+1C0h+var_158], r15b
0x180048c09  mov     [rbp+0C0h+var_A8], r15
0x180048c0d  mov     [rbp+0C0h+var_B0], r15
0x180048c11  lea     rax, [rbp+0C0h+var_C8]
0x180048c15  mov     [rbp+0C0h+var_100], rax
0x180048c19  lea     rax, [rsp+1C0h+var_157]
0x180048c1e  mov     [rbp+0C0h+var_F8], rax
0x180048c22  lea     rax, [rbp+0C0h+var_A0]
0x180048c26  mov     [rbp+0C0h+var_F0], rax
0x180048c2a  lea     rax, [rsp+1C0h+var_158]
0x180048c2f  mov     [rbp+0C0h+var_E8], rax
0x180048c33  lea     rax, [rbp+0C0h+var_A8]
0x180048c37  mov     [rbp+0C0h+var_E0], rax
0x180048c3b  lea     rax, [rbp+0C0h+var_B0]
0x180048c3f  mov     [rbp+0C0h+var_D8], rax
0x180048c43  lea     esi, [r15+1]
0x180048c47  mov     [rbp+0C0h+var_D0], sil
0x180048c4b  mov     [rsp+1C0h+var_178], r15
0x180048c50  call    cs:__imp_GetDatabaseManagerInstance
0x180048c57  nop     dword ptr [rax+rax+00h]
0x180048c5c  mov     rdi, rax
0x180048c5f  mov     rcx, [rax]
0x180048c62  mov     rbx, [rcx+20h]
0x180048c66  lea     rcx, [rsp+1C0h+var_178]
0x180048c6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048c70  lea     r8, [rsp+1C0h+var_178]
0x180048c75  mov     edx, 5402060h
0x180048c7a  mov     rcx, rdi
0x180048c7d  mov     rax, rbx
0x180048c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c85  mov     ebx, eax
0x180048c87  test    eax, eax
0x180048c89  jns     short loc_180048CC5
0x180048c8b  mov     rcx, [rbp+0C8h]; this
0x180048c92  mov     r9d, eax; char *
0x180048c95  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048c9c  mov     edx, 320h; void *
0x180048ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048ca6  nop
0x180048ca7  lea     rcx, [rsp+1C0h+var_178]
0x180048cac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048cb1  nop
0x180048cb2  mov     [rbp+0C0h+var_D0], r15b
0x180048cb6  lea     rcx, [rbp+0C0h+var_100]
0x180048cba  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x180048cbf  nop
0x180048cc0  jmp     loc_18004A03A
0x180048cc5  mov     [rsp+1C0h+var_180], r15
0x180048cca  mov     [rsp+1C0h+var_168], r15
0x180048ccf  mov     rdi, [rsp+1C0h+var_178]
0x180048cd4  mov     rax, [rdi]
0x180048cd7  mov     rbx, [rax+18h]
0x180048cdb  lea     rcx, [rsp+1C0h+var_180]
0x180048ce0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048ce5  lea     rdx, [rsp+1C0h+var_180]
0x180048cea  mov     rcx, rdi
0x180048ced  mov     rax, rbx
0x180048cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cf5  mov     ebx, eax
0x180048cf7  cmp     eax, esi
0x180048cf9  jnz     short loc_180048D31
0x180048cfb  lea     rcx, [rsp+1C0h+var_168]
0x180048d00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048d05  nop
0x180048d06  lea     rcx, [rsp+1C0h+var_180]
0x180048d0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048d10  nop
0x180048d11  lea     rcx, [rsp+1C0h+var_178]
0x180048d16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048d1b  nop
0x180048d1c  mov     [rbp+0C0h+var_D0], r15b
0x180048d20  lea     rcx, [rbp+0C0h+var_100]
0x180048d24  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x180048d29  nop
0x180048d2a  mov     ebx, esi
0x180048d2c  jmp     loc_18004A03A
0x180048d31  test    eax, eax
0x180048d33  jns     short loc_180048D85
0x180048d35  mov     rcx, [rbp+0C8h]; this
0x180048d3c  mov     r9d, eax; char *
0x180048d3f  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048d46  mov     edx, 32Ah; void *
0x180048d4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048d50  nop
0x180048d51  lea     rcx, [rsp+1C0h+var_168]
0x180048d56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048d5b  nop
0x180048d5c  lea     rcx, [rsp+1C0h+var_180]
0x180048d61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048d66  nop
0x180048d67  lea     rcx, [rsp+1C0h+var_178]
0x180048d6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048d71  nop
0x180048d72  mov     [rbp+0C0h+var_D0], r15b
0x180048d76  lea     rcx, [rbp+0C0h+var_100]
0x180048d7a  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x180048d7f  nop
0x180048d80  jmp     loc_18004A03A
0x180048d85  mov     [rbp+0C0h+var_C0], r15d
0x180048d89  mov     rcx, [rsp+1C0h+var_180]
0x180048d8e  mov     rax, [rcx]
0x180048d91  lea     rdx, [rbp+0C0h+var_C0]
0x180048d95  mov     rax, [rax+30h]
0x180048d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d9e  mov     ebx, eax
0x180048da0  test    eax, eax
0x180048da2  jns     short loc_180048DF4
0x180048da4  mov     rcx, [rbp+0C8h]; this
0x180048dab  mov     r9d, eax; char *
0x180048dae  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048db5  mov     edx, 32Fh; void *
0x180048dba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048dbf  nop
0x180048dc0  lea     rcx, [rsp+1C0h+var_168]
0x180048dc5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048dca  nop
0x180048dcb  lea     rcx, [rsp+1C0h+var_180]
0x180048dd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048dd5  nop
0x180048dd6  lea     rcx, [rsp+1C0h+var_178]
0x180048ddb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048de0  nop
0x180048de1  mov     [rbp+0C0h+var_D0], r15b
0x180048de5  lea     rcx, [rbp+0C0h+var_100]
0x180048de9  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x180048dee  nop
0x180048def  jmp     loc_18004A03A
0x180048df4  mov     eax, [rbp+0C0h+var_C0]
0x180048df7  add     eax, 0FFFFFFE8h
0x180048dfa  test    eax, 0FFFFFFFDh
0x180048dff  jnz     loc_180048ED7
0x180048e05  mov     rdi, [rsp+1C0h+var_178]
0x180048e0a  mov     rax, [rdi]
0x180048e0d  mov     rbx, [rax+18h]
0x180048e11  lea     rcx, [rsp+1C0h+var_168]
0x180048e16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048e1b  lea     rdx, [rsp+1C0h+var_168]
0x180048e20  mov     rcx, rdi
0x180048e23  mov     rax, rbx
0x180048e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e2b  test    eax, eax
0x180048e2d  js      loc_180048ED7
0x180048e33  mov     [rbp+0C0h+var_108], r15d
0x180048e37  mov     rcx, [rsp+1C0h+var_168]
0x180048e3c  mov     rax, [rcx]
0x180048e3f  lea     rdx, [rbp+0C0h+var_108]
0x180048e43  mov     rax, [rax+30h]
0x180048e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e4c  mov     ebx, eax
0x180048e4e  test    eax, eax
0x180048e50  jns     short loc_180048EA2
0x180048e52  mov     rcx, [rbp+0C8h]; this
0x180048e59  mov     r9d, eax; char *
0x180048e5c  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048e63  mov     edx, 335h; void *
0x180048e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e6d  nop
0x180048e6e  lea     rcx, [rsp+1C0h+var_168]
0x180048e73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048e78  nop
0x180048e79  lea     rcx, [rsp+1C0h+var_180]
0x180048e7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048e83  nop
0x180048e84  lea     rcx, [rsp+1C0h+var_178]
0x180048e89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048e8e  nop
0x180048e8f  mov     [rbp+0C0h+var_D0], r15b
0x180048e93  lea     rcx, [rbp+0C0h+var_100]
0x180048e97  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x180048e9c  nop
0x180048e9d  jmp     loc_18004A03A
0x180048ea2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment> `wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl(void)'::`2'::impl
0x180048ea9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(void)
0x180048eae  test    al, al
0x180048eb0  jz      short loc_180048EB8
0x180048eb2  cmp     [rbp+0C0h+var_108], 0Dh
0x180048eb6  jz      short loc_180048EBE
0x180048eb8  cmp     [rbp+0C0h+var_108], 6
0x180048ebc  jnz     short loc_180048ED7
0x180048ebe  lea     rcx, [rsp+1C0h+var_180]
0x180048ec3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048ec8  lea     rdx, [rsp+1C0h+var_168]
0x180048ecd  lea     rcx, [rsp+1C0h+var_180]
0x180048ed2  call    ??4?$ComPtr@UIEnrollmentInfo@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IEnrollmentInfo>::operator=(Microsoft::WRL::ComPtr<IEnrollmentInfo> const &)
0x180048ed7  test    r14, r14
0x180048eda  jnz     short loc_180048F08
0x180048edc  call    cs:__imp_GetDesktopWindow
0x180048ee3  nop     dword ptr [rax+rax+00h]
0x180048ee8  mov     rbx, rax
0x180048eeb  lea     edx, [r14+6]; uCmd
0x180048eef  mov     rcx, rax; hWnd
0x180048ef2  call    cs:__imp_GetWindow
0x180048ef9  nop     dword ptr [rax+rax+00h]
0x180048efe  mov     r14, rax
0x180048f01  test    rax, rax
0x180048f04  cmovz   r14, rbx
0x180048f08  xorps   xmm0, xmm0
0x180048f0b  movups  [rbp+0C0h+var_50], xmm0
0x180048f0f  mov     rcx, [rsp+1C0h+var_180]
0x180048f14  mov     rax, [rcx]
0x180048f17  lea     rdx, [rbp+0C0h+var_50]
0x180048f1b  mov     rax, [rax+18h]
0x180048f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f24  mov     ebx, eax
0x180048f26  test    eax, eax
0x180048f28  jns     short loc_180048F7A
0x180048f2a  mov     rcx, [rbp+0C8h]; this
0x180048f31  mov     r9d, eax; char *
0x180048f34  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048f3b  mov     edx, 355h; void *
0x180048f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048f45  nop
0x180048f46  lea     rcx, [rsp+1C0h+var_168]
0x180048f4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048f50  nop
0x180048f51  lea     rcx, [rsp+1C0h+var_180]
0x180048f56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048f5b  nop
0x180048f5c  lea     rcx, [rsp+1C0h+var_178]
0x180048f61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048f66  nop
0x180048f67  mov     [rbp+0C0h+var_D0], r15b
0x180048f6b  lea     rcx, [rbp+0C0h+var_100]
0x180048f6f  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x180048f74  nop
0x180048f75  jmp     loc_18004A03A
0x180048f7a  movaps  xmm0, [rbp+0C0h+var_50]
0x180048f7e  movdqa  xmmword ptr [rbp+0C0h+string], xmm0
0x180048f83  lea     rdx, [rbp+0C0h+var_B0]
0x180048f87  lea     rcx, [rbp+0C0h+string]
0x180048f8b  call    cs:__imp_GetEnrollmentPartnerOpaqueID
0x180048f92  nop     dword ptr [rax+rax+00h]
0x180048f97  mov     ebx, eax
0x180048f99  test    eax, eax
0x180048f9b  jns     short loc_180048FED
0x180048f9d  mov     rcx, [rbp+0C8h]; this
0x180048fa4  mov     r9d, eax; char *
0x180048fa7  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048fae  mov     edx, 357h; void *
0x180048fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048fb8  nop
0x180048fb9  lea     rcx, [rsp+1C0h+var_168]
0x180048fbe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048fc3  nop
0x180048fc4  lea     rcx, [rsp+1C0h+var_180]
0x180048fc9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048fce  nop
0x180048fcf  lea     rcx, [rsp+1C0h+var_178]
0x180048fd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048fd9  nop
0x180048fda  mov     [rbp+0C0h+var_D0], r15b
0x180048fde  lea     rcx, [rbp+0C0h+var_100]
0x180048fe2  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x180048fe7  nop
0x180048fe8  jmp     loc_18004A03A
0x180048fed  movaps  xmm0, [rbp+0C0h+var_50]
0x180048ff1  movdqa  xmmword ptr [rbp+0C0h+string], xmm0
0x180048ff6  lea     rdx, [rbp+0C0h+var_A8]
0x180048ffa  lea     rcx, [rbp+0C0h+string]
0x180048ffe  call    cs:__imp_GetEnrollmentAadResourceUrl
0x180049005  nop     dword ptr [rax+rax+00h]
0x18004900a  mov     ebx, eax
0x18004900c  test    eax, eax
0x18004900e  jns     short loc_180049060
0x180049010  mov     rcx, [rbp+0C8h]; this
0x180049017  mov     r9d, eax; char *
0x18004901a  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180049021  mov     edx, 358h; void *
0x180049026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004902b  nop
0x18004902c  lea     rcx, [rsp+1C0h+var_168]
0x180049031  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049036  nop
0x180049037  lea     rcx, [rsp+1C0h+var_180]
0x18004903c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049041  nop
0x180049042  lea     rcx, [rsp+1C0h+var_178]
0x180049047  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004904c  nop
0x18004904d  mov     [rbp+0C0h+var_D0], r15b
0x180049051  lea     rcx, [rbp+0C0h+var_100]
0x180049055  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004905a  nop
0x18004905b  jmp     loc_18004A03A
  ... truncated ...
```
