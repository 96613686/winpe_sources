# SystemSettings::WorkAccess::CEnrollmentHelper::PrefetchAadUserTokenEx(HWND__ *,bool)

- ea: `0x18004a06c`
- end: `0x18004afea`
- name: `?PrefetchAadUserTokenEx@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJPEAUHWND__@@_N@Z`
- size: `3966`
- prototype: `__int64 __fastcall(HWND, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002454c`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
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
- `0x1800459f8`
- `0x18004a06c`
- `0x18004d150`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a152`
- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x18004a1b7`
- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x18004a1b7`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x18004a209`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x18004a209`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004a24c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004a24c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x18004a108`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x18004a108`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x18004a11d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x18004a11d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a165`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a165`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a2b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a2b7`

## string_xrefs

- `0x18004a181`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a1d3`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a225`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a268`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a2d3`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a323`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a36d`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a3c2`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a439`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a498`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a509`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a5bf`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a64f`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a712`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a7d5`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a89d`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004a99e`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004aab6`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004abb1`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004aca6`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004adab`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004af17`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::PrefetchAadUserTokenEx(HWND Window, char a2)
{
  __int64 v4; // rcx
  HWND DesktopWindow; // rbx
  HSTRING v7; // rcx
  const OLECHAR *StringRawBuffer; // rax
  HRESULT v9; // eax
  signed int v10; // ebx
  int EnrollmentPartnerOpaqueID; // eax
  int EnrollmentAadResourceUrl; // eax
  int v13; // eax
  HRESULT v14; // eax
  int v15; // eax
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  _QWORD *v18; // rax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v22)[26]; // rdx
  _QWORD *v23; // rax
  int v24; // eax
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  _QWORD *v27; // rax
  int v28; // eax
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, __int64, _QWORD, __int64); // rdi
  const unsigned __int16 (*v31)[37]; // rdx
  __int64 v32; // rbx
  const unsigned __int16 (*v33)[1]; // rdx
  _QWORD *v34; // rax
  int v35; // eax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rsi
  __int64 (__fastcall *v40)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v41; // rbx
  const unsigned __int16 (*v42)[26]; // rdx
  _QWORD *v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rsi
  __int64 (__fastcall *v48)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v49; // rbx
  const unsigned __int16 (*v50)[33]; // rdx
  _QWORD *v51; // rax
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rsi
  __int64 (__fastcall *v55)(__int64, _QWORD, HSTRING, _BYTE *); // rdi
  HSTRING v56; // rbx
  const unsigned __int16 (*v57)[9]; // rdx
  _QWORD *v58; // rax
  int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rdi
  int (__fastcall *v62)(__int64, __int64, HSTRING, HSTRING *); // rbx
  int v63; // eax
  __int64 v64; // rcx
  _QWORD *v65; // rdi
  __int64 v66; // rax
  __int64 (__fastcall *v67)(_QWORD *, HWND, __int64, __int64); // rbx
  int v68; // eax
  __int64 (__fastcall *v69)(_QWORD *, HWND, __int64, GUID *); // rbx
  signed int v70; // esi
  __int64 v71; // rcx
  __int64 v72; // rdi
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rdi
  __int64 (__fastcall *v77)(__int64, HSTRING *); // rbx
  int v78; // eax
  __int64 v79; // rcx
  __int64 v80; // rcx
  bool v81; // sf
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  GUID *ppvb; // [rsp+20h] [rbp-E0h]
  _BYTE v91[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v92; // [rsp+48h] [rbp-B8h] BYREF
  char v93; // [rsp+50h] [rbp-B0h] BYREF
  char v94; // [rsp+51h] [rbp-AFh] BYREF
  __int64 v95; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v96; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v97; // [rsp+68h] [rbp-98h] BYREF
  __int64 v98; // [rsp+70h] [rbp-90h] BYREF
  __int64 v99; // [rsp+78h] [rbp-88h] BYREF
  __int64 v100; // [rsp+80h] [rbp-80h] BYREF
  int v101[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v102; // [rsp+90h] [rbp-70h] BYREF
  __int64 v103; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v104[6]; // [rsp+A0h] [rbp-60h] BYREF
  char v105; // [rsp+D0h] [rbp-30h]
  LPVOID v106; // [rsp+D8h] [rbp-28h] BYREF
  int v107; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v108[3]; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned __int16 *v109; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v110; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING string[4]; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v112[4]; // [rsp+120h] [rbp+20h] BYREF
  GUID pclsid; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v4 = SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton;
  if ( !SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton )
    return 2147942487LL;
  v106 = 0;
  v110 = 0;
  v94 = 0;
  v93 = 0;
  v109 = 0;
  *(_QWORD *)&v108[1] = 0;
  v104[0] = &v106;
  v104[1] = &v94;
  v104[2] = &v110;
  v104[3] = &v93;
  v104[4] = &v109;
  v104[5] = &v108[1];
  v105 = 1;
  if ( !Window )
  {
    DesktopWindow = GetDesktopWindow();
    Window = GetWindow(DesktopWindow, 6u);
    if ( !Window )
      Window = DesktopWindow;
    v4 = SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton;
  }
  pclsid = 0;
  if ( a2 )
    v7 = *(HSTRING *)(v4 + 32);
  else
    v7 = *(HSTRING *)(v4 + 16);
  StringRawBuffer = WindowsGetStringRawBuffer(v7, 0);
  v9 = CLSIDFromString(StringRawBuffer, &pclsid);
  v10 = v9;
  if ( v9 >= 0 )
  {
    *(GUID *)string = pclsid;
    EnrollmentPartnerOpaqueID = GetEnrollmentPartnerOpaqueID(string, &v108[1]);
    v10 = EnrollmentPartnerOpaqueID;
    if ( EnrollmentPartnerOpaqueID < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E7,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)EnrollmentPartnerOpaqueID,
        ppv);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    *(GUID *)string = pclsid;
    EnrollmentAadResourceUrl = GetEnrollmentAadResourceUrl(string, &v109);
    v10 = EnrollmentAadResourceUrl;
    if ( EnrollmentAadResourceUrl < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E8,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)EnrollmentAadResourceUrl,
        ppv);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v13 = RoInitialize(1);
    v10 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3EA,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v13,
        ppv);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v93 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
    v14 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v106);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F0,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v14,
        ppva);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v106 + 32LL))(v106, 5, &v110);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F1,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v15,
        ppva);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v16 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v106 + 24LL))(v106, 5, 1);
    v10 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F2,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v16,
        ppva);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v94 = 1;
    v95 = 0;
    v18 = (_QWORD *)Windows::Internal::StringReference::StringReference(v112, (const unsigned __int16 (*)[70])v17);
    v19 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
            *v18,
            &v95);
    v10 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F6,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v19,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v96 = 0;
    v20 = v95;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v95 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    v23 = (_QWORD *)Windows::Internal::StringReference::StringReference(v112, v22);
    v24 = v21(v20, *v23, &v96);
    v10 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F9,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v24,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v98 = 0;
    v25 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
            v96,
            &v98);
    v10 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FC,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v25,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v99 = 0;
    v27 = (_QWORD *)Windows::Internal::StringReference::StringReference(v112, (const unsigned __int16 (*)[57])v26);
    v28 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
            *v27,
            &v99);
    v10 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FF,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v28,
        ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v97 = 0;
    v29 = v99;
    v30 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v99 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    v32 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v112, v31);
    v34 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v33);
    v35 = v30(v29, v98, *v34, v32);
    v10 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x407,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v35,
        0);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v92 = 0;
    v91[0] = 0;
    v36 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v97 + 80LL))(v97, &v92);
    v10 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40B,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v36,
        0);
      v38 = v92;
      if ( v92 )
      {
        v92 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
      v105 = 0;
      lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
      goto LABEL_101;
    }
    v39 = v92;
    v40 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v92 + 80LL);
    v41 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v112, (const unsigned __int16 (*)[1])v37);
    v43 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v42);
    v44 = v40(v39, *v43, v41, v91);
    v10 = v44;
    if ( v44 >= 0 )
    {
      v47 = v92;
      v48 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v92 + 80LL);
      v49 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v112, (const unsigned __int16 (*)[33])v45);
      v51 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v50);
      v52 = v48(v47, *v51, v49, v91);
      v10 = v52;
      if ( v52 >= 0 )
      {
        v54 = v92;
        v55 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _BYTE *))(*(_QWORD *)v92 + 80LL);
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v109);
        v56 = string[0];
        v58 = (_QWORD *)Windows::Internal::StringReference::StringReference(v112, v57);
        v59 = v55(v54, *v58, v56, v91);
        v10 = v59;
        if ( v59 >= 0 )
        {
          v103 = 0;
          if ( *(_QWORD *)&v108[1] )
          {
            string[0] = 0;
            v61 = v95;
            v62 = *(int (__fastcall **)(__int64, __int64, HSTRING, HSTRING *))(*(_QWORD *)v95 + 80LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
            Windows::Internal::StringReference::_ConstructorHelper(
              (Windows::Internal::StringReference *)v112,
              *(const unsigned __int16 **)&v108[1]);
            if ( v62(v61, v98, v112[0], string) >= 0 )
              BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(
                string[0],
                &v103);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
          }
          v102 = 0;
          v63 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>::As<IWebAuthenticationCoreManagerInterop>(
                  &v95,
                  &v102);
          v10 = v63;
          if ( v63 >= 0 )
          {
            *(_QWORD *)v101 = 0;
            v65 = v102;
            v66 = *v102;
            if ( v103 )
            {
              v67 = *(__int64 (__fastcall **)(_QWORD *, HWND, __int64, __int64))(v66 + 56);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
              ppvb = &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9;
              v68 = v67(v65, Window, v97, v103);
            }
            else
            {
              v69 = *(__int64 (__fastcall **)(_QWORD *, HWND, __int64, GUID *))(v66 + 48);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
              ppvb = (GUID *)v101;
              v68 = v69(v65, Window, v97, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
            }
            v70 = v68;
            if ( v68 >= 0 )
            {
              v100 = 0;
              v72 = *(_QWORD *)v101;
              v10 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(*(_QWORD *)v101);
              if ( v10 < 0
                || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 64LL))(v72, &v100), v10 < 0) )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x425,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                  (const char *)(unsigned int)v10,
                  (int)ppvb);
                v86 = v100;
                if ( v100 )
                {
                  v100 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
                v87 = v92;
                if ( v92 )
                {
                  v92 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
                }
                goto LABEL_100;
              }
              v107 = 0;
              v73 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v100 + 56LL))(v100, &v107);
              v10 = v73;
              if ( v73 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x428,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                  (const char *)(unsigned int)v73,
                  (int)ppvb);
                v74 = v100;
                if ( v100 )
                {
                  v100 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
                v75 = v92;
                if ( v92 )
                {
                  v92 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
                }
                goto LABEL_100;
              }
              if ( v107 )
              {
                string[0] = 0;
                v76 = v100;
                v77 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v100 + 64LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
                v78 = v77(v76, string);
                v10 = v78;
                if ( v78 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x42D,
                    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                    (const char *)(unsigned int)v78,
                    (int)ppvb);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
                  v79 = v100;
                  if ( v100 )
                  {
                    v100 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
                  }
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
                  v80 = v92;
                  if ( v92 )
                  {
                    v92 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
                  }
                  goto LABEL_100;
                }
                if ( string[0] )
                {
                  v108[0] = 0;
                  if ( (*(int (__fastcall **)(HSTRING, _DWORD *))(*(_QWORD *)string[0] + 48LL))(string[0], v108) >= 0 )
                  {
                    v10 = v108[0];
                    v81 = v108[0] < 0;
                    if ( v108[0] > 0 )
                    {
                      v10 = LOWORD(v108[0]) | 0x80070000;
                      v81 = 1;
                    }
                    if ( v81 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x433,
                        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                        (const char *)(unsigned int)v10,
                        (int)ppvb);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
                      v82 = v100;
                      if ( v100 )
                      {
                        v100 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
                      }
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
                      v83 = v92;
                      if ( v92 )
                      {
                        v92 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
                      }
                      goto LABEL_100;
                    }
                  }
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
              }
              v84 = v100;
              if ( v100 )
              {
                v100 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
              v85 = v92;
              if ( v92 )
              {
                v92 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x422,
                (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
                (const char *)(unsigned int)v68,
                (int)ppvb);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v101);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
              v71 = v92;
              if ( v92 )
              {
                v92 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
              }
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
            v105 = 0;
            lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
            v10 = v70;
            goto LABEL_101;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x41C,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v63,
            0);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
          v64 = v92;
          if ( v92 )
          {
            v92 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x40E,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v59,
            0);
          v60 = v92;
          if ( v92 )
          {
            v92 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40D,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
          (const char *)(unsigned int)v52,
          0);
        v53 = v92;
        if ( v92 )
        {
          v92 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40C,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v44,
        0);
      v46 = v92;
      if ( v92 )
      {
        v92 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
    }
LABEL_100:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v105 = 0;
    lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
    goto LABEL_101;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E5,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)(unsigned int)v9,
    ppv);
  v105 = 0;
  lambda_7668554cbe82c623da48595a3a518cfe_::operator()(v104);
LABEL_101:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004a06c  push    rbp
0x18004a06e  push    rbx
0x18004a06f  push    rsi
0x18004a070  push    rdi
0x18004a071  push    r14
0x18004a073  push    r15
0x18004a075  lea     rbp, [rsp-68h]
0x18004a07a  sub     rsp, 168h
0x18004a081  mov     rax, cs:__security_cookie
0x18004a088  xor     rax, rsp
0x18004a08b  mov     [rbp+90h+var_40], rax
0x18004a08f  mov     dil, dl
0x18004a092  mov     r14, rcx
0x18004a095  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x18004a09c  xor     r15d, r15d
0x18004a09f  test    rcx, rcx
0x18004a0a2  jnz     short loc_18004A0AE
0x18004a0a4  mov     eax, 80070057h
0x18004a0a9  jmp     loc_18004AFCD
0x18004a0ae  mov     [rbp+90h+var_B8], r15
0x18004a0b2  mov     [rbp+90h+var_98], r15
0x18004a0b6  mov     [rsp+190h+var_13F], r15b
0x18004a0bb  mov     [rsp+190h+var_140], r15b
0x18004a0c0  mov     [rbp+90h+var_A0], r15
0x18004a0c4  mov     qword ptr [rbp+90h+var_AC+4], r15
0x18004a0c8  lea     rax, [rbp+90h+var_B8]
0x18004a0cc  mov     [rbp+90h+var_F0], rax
0x18004a0d0  lea     rax, [rsp+190h+var_13F]
0x18004a0d5  mov     [rbp+90h+var_E8], rax
0x18004a0d9  lea     rax, [rbp+90h+var_98]
0x18004a0dd  mov     [rbp+90h+var_E0], rax
0x18004a0e1  lea     rax, [rsp+190h+var_140]
0x18004a0e6  mov     [rbp+90h+var_D8], rax
0x18004a0ea  lea     rax, [rbp+90h+var_A0]
0x18004a0ee  mov     [rbp+90h+var_D0], rax
0x18004a0f2  lea     rax, [rbp+90h+var_AC+4]
0x18004a0f6  mov     [rbp+90h+var_C8], rax
0x18004a0fa  mov     esi, 1
0x18004a0ff  mov     [rbp+90h+var_C0], sil
0x18004a103  test    r14, r14
0x18004a106  jnz     short loc_18004A13A
0x18004a108  call    cs:__imp_GetDesktopWindow
0x18004a10f  nop     dword ptr [rax+rax+00h]
0x18004a114  mov     rbx, rax
0x18004a117  lea     edx, [rsi+5]; uCmd
0x18004a11a  mov     rcx, rax; hWnd
0x18004a11d  call    cs:__imp_GetWindow
0x18004a124  nop     dword ptr [rax+rax+00h]
0x18004a129  mov     r14, rax
0x18004a12c  test    rax, rax
0x18004a12f  cmovz   r14, rbx
0x18004a133  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x18004a13a  xorps   xmm0, xmm0
0x18004a13d  movups  xmmword ptr [rbp+90h+pclsid.Data1], xmm0
0x18004a141  xor     edx, edx; length
0x18004a143  test    dil, dil
0x18004a146  jz      short loc_18004A14E
0x18004a148  mov     rcx, [rcx+20h]
0x18004a14c  jmp     short loc_18004A152
0x18004a14e  mov     rcx, [rcx+10h]; string
0x18004a152  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a159  nop     dword ptr [rax+rax+00h]
0x18004a15e  lea     rdx, [rbp+90h+pclsid]; pclsid
0x18004a162  mov     rcx, rax; lpsz
0x18004a165  call    cs:__imp_CLSIDFromString
0x18004a16c  nop     dword ptr [rax+rax+00h]
0x18004a171  mov     ebx, eax
0x18004a173  test    eax, eax
0x18004a175  jns     short loc_18004A1A6
0x18004a177  mov     rcx, [rbp+98h]; this
0x18004a17e  mov     r9d, eax; char *
0x18004a181  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a188  mov     edx, 3E5h; void *
0x18004a18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a192  nop
0x18004a193  mov     [rbp+90h+var_C0], r15b
0x18004a197  lea     rcx, [rbp+90h+var_F0]
0x18004a19b  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a1a0  nop
0x18004a1a1  jmp     loc_18004AFC2
0x18004a1a6  movaps  xmm0, xmmword ptr [rbp+90h+pclsid.Data1]
0x18004a1aa  movdqa  xmmword ptr [rbp+90h+string], xmm0
0x18004a1af  lea     rdx, [rbp+90h+var_AC+4]
0x18004a1b3  lea     rcx, [rbp+90h+string]
0x18004a1b7  call    cs:__imp_GetEnrollmentPartnerOpaqueID
0x18004a1be  nop     dword ptr [rax+rax+00h]
0x18004a1c3  mov     ebx, eax
0x18004a1c5  test    eax, eax
0x18004a1c7  jns     short loc_18004A1F8
0x18004a1c9  mov     rcx, [rbp+98h]; this
0x18004a1d0  mov     r9d, eax; char *
0x18004a1d3  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a1da  mov     edx, 3E7h; void *
0x18004a1df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a1e4  nop
0x18004a1e5  mov     [rbp+90h+var_C0], r15b
0x18004a1e9  lea     rcx, [rbp+90h+var_F0]
0x18004a1ed  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a1f2  nop
0x18004a1f3  jmp     loc_18004AFC2
0x18004a1f8  movaps  xmm0, xmmword ptr [rbp+90h+pclsid.Data1]
0x18004a1fc  movdqa  xmmword ptr [rbp+90h+string], xmm0
0x18004a201  lea     rdx, [rbp+90h+var_A0]
0x18004a205  lea     rcx, [rbp+90h+string]
0x18004a209  call    cs:__imp_GetEnrollmentAadResourceUrl
0x18004a210  nop     dword ptr [rax+rax+00h]
0x18004a215  mov     ebx, eax
0x18004a217  test    eax, eax
0x18004a219  jns     short loc_18004A24A
0x18004a21b  mov     rcx, [rbp+98h]; this
0x18004a222  mov     r9d, eax; char *
0x18004a225  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a22c  mov     edx, 3E8h; void *
0x18004a231  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a236  nop
0x18004a237  mov     [rbp+90h+var_C0], r15b
0x18004a23b  lea     rcx, [rbp+90h+var_F0]
0x18004a23f  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a244  nop
0x18004a245  jmp     loc_18004AFC2
0x18004a24a  mov     ecx, esi
0x18004a24c  call    cs:__imp_RoInitialize
0x18004a253  nop     dword ptr [rax+rax+00h]
0x18004a258  mov     ebx, eax
0x18004a25a  test    eax, eax
0x18004a25c  jns     short loc_18004A28D
0x18004a25e  mov     rcx, [rbp+98h]; this
0x18004a265  mov     r9d, eax; char *
0x18004a268  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a26f  mov     edx, 3EAh; void *
0x18004a274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a279  nop
0x18004a27a  mov     [rbp+90h+var_C0], r15b
0x18004a27e  lea     rcx, [rbp+90h+var_F0]
0x18004a282  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a287  nop
0x18004a288  jmp     loc_18004AFC2
0x18004a28d  mov     [rsp+190h+var_140], sil
0x18004a292  lea     rcx, [rbp+90h+var_B8]
0x18004a296  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a29b  lea     rax, [rbp+90h+var_B8]
0x18004a29f  mov     [rsp+190h+ppv], rax; int
0x18004a2a4  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18004a2ab  mov     r8d, esi; dwClsContext
0x18004a2ae  xor     edx, edx; pUnkOuter
0x18004a2b0  lea     rcx, CLSID_GlobalOptions; rclsid
0x18004a2b7  call    cs:__imp_CoCreateInstance
0x18004a2be  nop     dword ptr [rax+rax+00h]
0x18004a2c3  mov     ebx, eax
0x18004a2c5  test    eax, eax
0x18004a2c7  jns     short loc_18004A2F8
0x18004a2c9  mov     rcx, [rbp+98h]; this
0x18004a2d0  mov     r9d, eax; char *
0x18004a2d3  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a2da  mov     edx, 3F0h; void *
0x18004a2df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a2e4  nop
0x18004a2e5  mov     [rbp+90h+var_C0], r15b
0x18004a2e9  lea     rcx, [rbp+90h+var_F0]
0x18004a2ed  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a2f2  nop
0x18004a2f3  jmp     loc_18004AFC2
0x18004a2f8  mov     rcx, [rbp+90h+var_B8]
0x18004a2fc  mov     rax, [rcx]
0x18004a2ff  lea     r8, [rbp+90h+var_98]
0x18004a303  mov     edi, 5
0x18004a308  mov     edx, edi
0x18004a30a  mov     rax, [rax+20h]
0x18004a30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a313  mov     ebx, eax
0x18004a315  test    eax, eax
0x18004a317  jns     short loc_18004A348
0x18004a319  mov     rcx, [rbp+98h]; this
0x18004a320  mov     r9d, eax; char *
0x18004a323  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a32a  mov     edx, 3F1h; void *
0x18004a32f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a334  nop
0x18004a335  mov     [rbp+90h+var_C0], r15b
0x18004a339  lea     rcx, [rbp+90h+var_F0]
0x18004a33d  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a342  nop
0x18004a343  jmp     loc_18004AFC2
0x18004a348  mov     rcx, [rbp+90h+var_B8]
0x18004a34c  mov     rax, [rcx]
0x18004a34f  mov     r8, rsi
0x18004a352  mov     edx, edi
0x18004a354  mov     rax, [rax+18h]
0x18004a358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a35d  mov     ebx, eax
0x18004a35f  test    eax, eax
0x18004a361  jns     short loc_18004A392
0x18004a363  mov     rcx, [rbp+98h]; this
0x18004a36a  mov     r9d, eax; char *
0x18004a36d  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a374  mov     edx, 3F2h; void *
0x18004a379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a37e  nop
0x18004a37f  mov     [rbp+90h+var_C0], r15b
0x18004a383  lea     rcx, [rbp+90h+var_F0]
0x18004a387  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a38c  nop
0x18004a38d  jmp     loc_18004AFC2
0x18004a392  mov     [rsp+190h+var_13F], sil
0x18004a397  mov     [rsp+190h+var_138], r15
0x18004a39c  lea     rcx, [rbp+90h+var_70]; string
0x18004a3a0  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x18004a3a5  lea     rdx, [rsp+190h+var_138]
0x18004a3aa  mov     rcx, [rax]
0x18004a3ad  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x18004a3b2  mov     ebx, eax
0x18004a3b4  test    eax, eax
0x18004a3b6  jns     short loc_18004A3F2
0x18004a3b8  mov     rcx, [rbp+98h]; this
0x18004a3bf  mov     r9d, eax; char *
0x18004a3c2  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a3c9  mov     edx, 3F6h; void *
0x18004a3ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a3d3  nop
0x18004a3d4  lea     rcx, [rsp+190h+var_138]
0x18004a3d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a3de  nop
0x18004a3df  mov     [rbp+90h+var_C0], r15b
0x18004a3e3  lea     rcx, [rbp+90h+var_F0]
0x18004a3e7  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a3ec  nop
0x18004a3ed  jmp     loc_18004AFC2
0x18004a3f2  mov     [rsp+190h+var_130], r15
0x18004a3f7  mov     rdi, [rsp+190h+var_138]
0x18004a3fc  mov     rax, [rdi]
0x18004a3ff  mov     rbx, [rax+58h]
0x18004a403  lea     rcx, [rsp+190h+var_130]
0x18004a408  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a40d  lea     rcx, [rbp+90h+var_70]; string
0x18004a411  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x18004a416  lea     r8, [rsp+190h+var_130]
0x18004a41b  mov     rdx, [rax]
0x18004a41e  mov     rcx, rdi
0x18004a421  mov     rax, rbx
0x18004a424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a429  mov     ebx, eax
0x18004a42b  test    eax, eax
0x18004a42d  jns     short loc_18004A474
0x18004a42f  mov     rcx, [rbp+98h]; this
0x18004a436  mov     r9d, eax; char *
0x18004a439  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a440  mov     edx, 3F9h; void *
0x18004a445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a44a  nop
0x18004a44b  lea     rcx, [rsp+190h+var_130]
0x18004a450  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a455  nop
0x18004a456  lea     rcx, [rsp+190h+var_138]
0x18004a45b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a460  nop
0x18004a461  mov     [rbp+90h+var_C0], r15b
0x18004a465  lea     rcx, [rbp+90h+var_F0]
0x18004a469  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a46e  nop
0x18004a46f  jmp     loc_18004AFC2
0x18004a474  mov     [rsp+190h+var_120], r15
0x18004a479  lea     rdx, [rsp+190h+var_120]
0x18004a47e  mov     rcx, [rsp+190h+var_130]
0x18004a483  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x18004a488  mov     ebx, eax
0x18004a48a  test    eax, eax
0x18004a48c  jns     short loc_18004A4DE
0x18004a48e  mov     rcx, [rbp+98h]; this
0x18004a495  mov     r9d, eax; char *
0x18004a498  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a49f  mov     edx, 3FCh; void *
0x18004a4a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a4a9  nop
0x18004a4aa  lea     rcx, [rsp+190h+var_120]
0x18004a4af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a4b4  nop
0x18004a4b5  lea     rcx, [rsp+190h+var_130]
0x18004a4ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a4bf  nop
0x18004a4c0  lea     rcx, [rsp+190h+var_138]
0x18004a4c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a4ca  nop
0x18004a4cb  mov     [rbp+90h+var_C0], r15b
0x18004a4cf  lea     rcx, [rbp+90h+var_F0]
0x18004a4d3  call    _lambda_7668554cbe82c623da48595a3a518cfe___operator__
0x18004a4d8  nop
0x18004a4d9  jmp     loc_18004AFC2
0x18004a4de  mov     [rsp+190h+var_118], r15
0x18004a4e3  lea     rcx, [rbp+90h+var_70]; string
0x18004a4e7  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x18004a4ec  lea     rdx, [rsp+190h+var_118]
0x18004a4f1  mov     rcx, [rax]
0x18004a4f4  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x18004a4f9  mov     ebx, eax
0x18004a4fb  test    eax, eax
0x18004a4fd  jns     short loc_18004A55A
0x18004a4ff  mov     rcx, [rbp+98h]; this
0x18004a506  mov     r9d, eax; char *
0x18004a509  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004a510  mov     edx, 3FFh; void *
  ... truncated ...
```
