# SystemSettings::WorkAccess::CEnrollmentHelper::PullAadUserTokenEx(HWND__ *,ushort const *,bool,ushort * *)

- ea: `0x18004aff0`
- end: `0x18004c771`
- name: `?PullAadUserTokenEx@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJPEAUHWND__@@PEBG_NPEAPEAG@Z`
- size: `6017`
- prototype: `static int(HWND, const unsigned __int16 *, bool, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180045cfc`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x18001ac98`
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
- `0x180045974`
- `0x18004aff0`
- `0x18004d150`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c58a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c58a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c48c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c59e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c48c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c59e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b0c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b0c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004c332`
- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x18004b125`
- `dmEnrollEngine!GetEnrollmentPartnerOpaqueID` at `0x18004b125`
- `DMCmnUtils!CopyString` at `0x18004c35a`
- `DMCmnUtils!CopyString` at `0x18004c35a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18004c463`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18004c575`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18004c463`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18004c575`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004b168`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18004b168`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x18004b076`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetDesktopWindow` at `0x18004b076`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x18004b08b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindow` at `0x18004b08b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004b0d3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004b0d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b1d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b1d3`

## string_xrefs

- `0x18004b0ef`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b141`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b184`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b1ef`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b23f`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b289`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b2de`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b355`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b3b4`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b425`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b4db`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b56b`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b62e`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b6f1`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b7b8`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b8b9`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004b9d1`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004bacf`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004bbcf`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004bcea`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004beb9`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004bfa7`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004c164`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004c25a`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004c37a`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x18004c691`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::PullAadUserTokenEx(
        HWND a1,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int16 **a4)
{
  HWND Window; // r14
  HWND DesktopWindow; // rbx
  HSTRING v9; // rcx
  const OLECHAR *StringRawBuffer; // rax
  HRESULT v11; // eax
  signed int v12; // ebx
  int EnrollmentPartnerOpaqueID; // eax
  int v14; // eax
  HRESULT v15; // eax
  int v16; // eax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  _QWORD *v19; // rax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v23)[26]; // rdx
  _QWORD *v24; // rax
  int v25; // eax
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  _QWORD *v28; // rax
  int v29; // eax
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, __int64, _QWORD, __int64); // rdi
  const unsigned __int16 (*v32)[37]; // rdx
  __int64 v33; // rbx
  const unsigned __int16 (*v34)[1]; // rdx
  _QWORD *v35; // rax
  int v36; // eax
  int v37; // eax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v42; // rbx
  const unsigned __int16 (*v43)[26]; // rdx
  _QWORD *v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rsi
  __int64 (__fastcall *v49)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v50; // rbx
  const unsigned __int16 (*v51)[33]; // rdx
  _QWORD *v52; // rax
  int v53; // eax
  __int64 v54; // rcx
  __int64 v55; // rsi
  __int64 (__fastcall *v56)(__int64, _QWORD, HSTRING, _BYTE *); // rdi
  HSTRING v57; // rbx
  const unsigned __int16 (*v58)[9]; // rdx
  _QWORD *v59; // rax
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // rdi
  int (__fastcall *v63)(__int64, __int64, HSTRING, HSTRING *); // rbx
  int v64; // eax
  __int64 v65; // rcx
  _QWORD *v66; // rdi
  __int64 v67; // rax
  __int64 (__fastcall *v68)(_QWORD *, HWND, __int64, __int64); // rbx
  int v69; // eax
  __int64 (__fastcall *v70)(_QWORD *, HWND, __int64, GUID *); // rbx
  unsigned int v71; // esi
  __int64 v72; // rcx
  __int64 v73; // rdi
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rdi
  __int64 (__fastcall *v78)(__int64, __int64 *); // rbx
  int v79; // eax
  __int64 v80; // rcx
  __int64 v81; // rcx
  bool v82; // sf
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rdi
  __int64 (__fastcall *v88)(__int64, __int64 *); // rbx
  int v89; // eax
  __int64 v90; // rcx
  __int64 v91; // rcx
  int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rdi
  __int64 (__fastcall *v98)(__int64, _QWORD, __int64 *); // rbx
  int v99; // eax
  __int64 v100; // rcx
  __int64 v101; // rcx
  int v102; // eax
  __int64 v103; // rcx
  __int64 v104; // rcx
  const unsigned __int16 *v105; // rax
  int v106; // eax
  __int64 v107; // rcx
  __int64 v108; // rcx
  void *v109; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v111; // rcx
  __int64 v112; // rcx
  void *v113; // rbx
  HANDLE v114; // rax
  __int64 v116; // rcx
  __int64 v117; // rcx
  __int64 v118; // rcx
  __int64 v119; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  GUID *ppvb; // [rsp+20h] [rbp-E0h]
  __int64 v123; // [rsp+40h] [rbp-C0h] BYREF
  char v124; // [rsp+48h] [rbp-B8h] BYREF
  char v125; // [rsp+49h] [rbp-B7h] BYREF
  _BYTE v126[6]; // [rsp+4Ah] [rbp-B6h] BYREF
  __int64 v127; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v128; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v129; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v130; // [rsp+68h] [rbp-98h] BYREF
  __int64 v131; // [rsp+70h] [rbp-90h] BYREF
  __int64 v132; // [rsp+78h] [rbp-88h] BYREF
  int v133[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v134; // [rsp+88h] [rbp-78h] BYREF
  __int64 v135; // [rsp+90h] [rbp-70h] BYREF
  __int64 v136; // [rsp+98h] [rbp-68h] BYREF
  __int64 v137; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v138; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v139[5]; // [rsp+B0h] [rbp-50h] BYREF
  char v140; // [rsp+D8h] [rbp-28h]
  __int64 v141; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+E8h] [rbp-18h] BYREF
  int v143; // [rsp+F0h] [rbp-10h] BYREF
  int v144; // [rsp+F4h] [rbp-Ch] BYREF
  int v145; // [rsp+F8h] [rbp-8h] BYREF
  UINT32 length; // [rsp+FCh] [rbp-4h] BYREF
  _QWORD v147[2]; // [rsp+100h] [rbp+0h] BYREF
  HSTRING string[4]; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v149[4]; // [rsp+130h] [rbp+30h] BYREF
  GUID pclsid; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  Window = a1;
  v138 = 0;
  v147[0] = 0;
  v124 = 0;
  v125 = 0;
  lpMem = 0;
  v139[0] = &v138;
  v139[1] = &v124;
  v139[2] = v147;
  v139[3] = &v125;
  v139[4] = &lpMem;
  v140 = 1;
  if ( !a1 )
  {
    DesktopWindow = GetDesktopWindow();
    Window = GetWindow(DesktopWindow, 6u);
    if ( !Window )
      Window = DesktopWindow;
  }
  pclsid = 0;
  if ( a3 )
    v9 = *(HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 32);
  else
    v9 = *(HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton + 16);
  StringRawBuffer = WindowsGetStringRawBuffer(v9, 0);
  v11 = CLSIDFromString(StringRawBuffer, &pclsid);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52E,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
LABEL_157:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    return (unsigned int)v12;
  }
  *(GUID *)string = pclsid;
  EnrollmentPartnerOpaqueID = GetEnrollmentPartnerOpaqueID(string, &lpMem);
  v12 = EnrollmentPartnerOpaqueID;
  if ( EnrollmentPartnerOpaqueID < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52F,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)EnrollmentPartnerOpaqueID,
      ppv);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v14 = RoInitialize(1);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x531,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v14,
      ppv);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v125 = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
  v15 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v138);
  v12 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x537,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v15,
      ppva);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v16 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD *))(*(_QWORD *)v138 + 32LL))(v138, 5, v147);
  v12 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x538,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v16,
      ppva);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v138 + 24LL))(v138, 5, 1);
  v12 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x539,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v17,
      ppva);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v124 = 1;
  v128 = 0;
  v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(v149, (const unsigned __int16 (*)[70])v18);
  v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
          *v19,
          &v128);
  v12 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53D,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v20,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v129 = 0;
  v21 = v128;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v128 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
  v24 = (_QWORD *)Windows::Internal::StringReference::StringReference(v149, v23);
  v25 = v22(v21, *v24, &v129);
  v12 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x540,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v25,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v131 = 0;
  v26 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
          v129,
          &v131);
  v12 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x543,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v26,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v132 = 0;
  v28 = (_QWORD *)Windows::Internal::StringReference::StringReference(v149, (const unsigned __int16 (*)[57])v27);
  v29 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
          *v28,
          &v132);
  v12 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x546,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v29,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v130 = 0;
  v30 = v132;
  v31 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v132 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
  v33 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v149, v32);
  v35 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v34);
  v36 = v31(v30, v131, *v35, v33);
  v12 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54E,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v36,
      0);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v123 = 0;
  v126[0] = 0;
  v37 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v130 + 80LL))(v130, &v123);
  v12 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x552,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v37,
      0);
    v39 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
LABEL_156:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    goto LABEL_157;
  }
  v40 = v123;
  v41 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v123 + 80LL);
  v42 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v149, (const unsigned __int16 (*)[1])v38);
  v44 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v43);
  v45 = v41(v40, *v44, v42, v126);
  v12 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x553,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v45,
      0);
    v47 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    goto LABEL_156;
  }
  v48 = v123;
  v49 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v123 + 80LL);
  v50 = *(_QWORD *)Windows::Internal::StringReference::StringReference(v149, (const unsigned __int16 (*)[33])v46);
  v52 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v51);
  v53 = v49(v48, *v52, v50, v126);
  v12 = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x554,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v53,
      0);
    v54 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    goto LABEL_156;
  }
  v55 = v123;
  v56 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _BYTE *))(*(_QWORD *)v123 + 80LL);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, a2);
  v57 = string[0];
  v59 = (_QWORD *)Windows::Internal::StringReference::StringReference(v149, v58);
  v60 = v56(v55, *v59, v57, v126);
  v12 = v60;
  if ( v60 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x555,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v60,
      0);
    v61 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    goto LABEL_156;
  }
  v135 = 0;
  if ( lpMem )
  {
    string[0] = 0;
    v62 = v128;
    v63 = *(int (__fastcall **)(__int64, __int64, HSTRING, HSTRING *))(*(_QWORD *)v128 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v149,
      (const unsigned __int16 *)lpMem);
    if ( v63(v62, v131, v149[0], string) >= 0 )
      BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccount *,Windows::Security::Credentials::IWebAccount>(
        string[0],
        &v135);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(string);
  }
  v134 = 0;
  v64 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>::As<IWebAuthenticationCoreManagerInterop>(
          &v128,
          &v134);
  v12 = v64;
  if ( v64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x563,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v64,
      0);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v65 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    goto LABEL_156;
  }
  *(_QWORD *)v133 = 0;
  v66 = v134;
  v67 = *v134;
  if ( v135 )
  {
    v68 = *(__int64 (__fastcall **)(_QWORD *, HWND, __int64, __int64))(v67 + 56);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    ppvb = &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9;
    v69 = v68(v66, Window, v130, v135);
  }
  else
  {
    v70 = *(__int64 (__fastcall **)(_QWORD *, HWND, __int64, GUID *))(v67 + 48);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    ppvb = (GUID *)v133;
    v69 = v70(v66, Window, v130, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
  }
  v71 = v69;
  if ( v69 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x569,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v69,
      (int)ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v72 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    v12 = v71;
    goto LABEL_157;
  }
  v127 = 0;
  v73 = *(_QWORD *)v133;
  v12 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(*(_QWORD *)v133);
  if ( v12 < 0 || (v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 64LL))(v73, &v127), v12 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56C,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v12,
      (int)ppvb);
    v118 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v119 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
    }
    goto LABEL_156;
  }
  v143 = 0;
  v74 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v127 + 56LL))(v127, &v143);
  v12 = v74;
  if ( v74 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56F,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v74,
      (int)ppvb);
    v75 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v76 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    }
    goto LABEL_156;
  }
  v136 = 0;
  v137 = 0;
  if ( v143 )
  {
    v141 = 0;
    v77 = v127;
    v78 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v127 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141);
    v79 = v78(v77, &v141);
    v12 = v79;
    if ( v79 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x577,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v79,
        (int)ppvb);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
      v80 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
      v81 = v123;
      if ( v123 )
      {
        v123 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
      }
      goto LABEL_156;
    }
    if ( v141 )
    {
      v144 = 0;
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v141 + 48LL))(v141, &v144) >= 0 )
      {
        v12 = v144;
        v82 = v144 < 0;
        if ( v144 > 0 )
        {
          v12 = (unsigned __int16)v144 | 0x80070000;
          v82 = 1;
        }
        if ( v82 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x57D,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v12,
            (int)ppvb);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
          v83 = v127;
          if ( v127 )
          {
            v127 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
          v84 = v123;
          if ( v123 )
          {
            v123 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
          }
          goto LABEL_156;
        }
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v141);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v85 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v86 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    }
LABEL_89:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    v12 = -2147418113;
    goto LABEL_157;
  }
  v145 = 0;
  v87 = v127;
  v88 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v127 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
  v89 = v88(v87, &v136);
  v12 = v89;
  if ( v89 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x587,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v89,
      (int)ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v90 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v91 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    }
    goto LABEL_156;
  }
  v92 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v136 + 56LL))(v136, &v145);
  v12 = v92;
  if ( v92 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x588,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v92,
      (int)ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v93 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v94 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    }
    goto LABEL_156;
  }
  if ( !v145 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v95 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v96 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
    }
    goto LABEL_89;
  }
  v97 = v136;
  v98 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v136 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
  v99 = v98(v97, 0, &v137);
  v12 = v99;
  if ( v99 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58E,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v99,
      (int)ppvb);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v100 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v101 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
    }
    goto LABEL_156;
  }
  string[0] = 0;
  length = 0;
  v102 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v137 + 48LL))(v137, string);
  v12 = v102;
  if ( v102 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x593,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v102,
      (int)ppvb);
    Windows::Internal::String::~String((Windows::Internal::String *)string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v103 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v104 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
    }
    goto LABEL_156;
  }
  v105 = WindowsGetStringRawBuffer(string[0], &length);
  if ( v105 && length )
  {
    v106 = CopyString(v105, 0xFFFFFFFF, a4);
    v12 = v106;
    if ( v106 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59A,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v106,
        (int)ppvb);
      Windows::Internal::String::~String((Windows::Internal::String *)string);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
      v107 = v127;
      if ( v127 )
      {
        v127 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
      v108 = v123;
      if ( v123 )
      {
        v123 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
      if ( v138 && v124 )
        (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v138 + 24LL))(v138, 5, v147[0]);
      if ( v125 )
        RoUninitialize();
      v109 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v109);
      }
      goto LABEL_157;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v111 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v112 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    if ( v138 && v124 )
      (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v138 + 24LL))(v138, 5, v147[0]);
    if ( v125 )
      RoUninitialize();
    v113 = lpMem;
    if ( lpMem )
    {
      v114 = GetProcessHeap();
      HeapFree(v114, 0, v113);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    return v71;
  }
  else
  {
    Windows::Internal::String::~String((Windows::Internal::String *)string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    v116 = v127;
    if ( v127 )
    {
      v127 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v133);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    v117 = v123;
    if ( v123 )
    {
      v123 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
    v140 = 0;
    lambda_154327c85f8c76ffef0330697a9c13c5_::operator()(v139);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18004aff0  mov     [rsp-8+arg_10], rbx
0x18004aff5  push    rbp
0x18004aff6  push    rsi
0x18004aff7  push    rdi
0x18004aff8  push    r12
0x18004affa  push    r13
0x18004affc  push    r14
0x18004affe  push    r15
0x18004b000  lea     rbp, [rsp-70h]
0x18004b005  sub     rsp, 170h
0x18004b00c  mov     rax, cs:__security_cookie
0x18004b013  xor     rax, rsp
0x18004b016  mov     [rbp+0A0h+var_40], rax
0x18004b01a  mov     r12, r9
0x18004b01d  mov     dil, r8b
0x18004b020  mov     r15, rdx
0x18004b023  mov     r14, rcx
0x18004b026  xor     r13d, r13d
0x18004b029  mov     [rbp+0A0h+var_F8], r13
0x18004b02d  mov     [rbp+0A0h+var_A0], r13
0x18004b031  mov     [rsp+1A0h+var_158], r13b
0x18004b036  mov     [rsp+1A0h+var_157], r13b
0x18004b03b  mov     [rbp+0A0h+lpMem], r13
0x18004b03f  lea     rax, [rbp+0A0h+var_F8]
0x18004b043  mov     [rbp+0A0h+var_F0], rax
0x18004b047  lea     rax, [rsp+1A0h+var_158]
0x18004b04c  mov     [rbp+0A0h+var_E8], rax
0x18004b050  lea     rax, [rbp+0A0h+var_A0]
0x18004b054  mov     [rbp+0A0h+var_E0], rax
0x18004b058  lea     rax, [rsp+1A0h+var_157]
0x18004b05d  mov     [rbp+0A0h+var_D8], rax
0x18004b061  lea     rax, [rbp+0A0h+lpMem]
0x18004b065  mov     [rbp+0A0h+var_D0], rax
0x18004b069  lea     esi, [r13+1]
0x18004b06d  mov     [rbp+0A0h+var_C8], sil
0x18004b071  test    rcx, rcx
0x18004b074  jnz     short loc_18004B0A1
0x18004b076  call    cs:__imp_GetDesktopWindow
0x18004b07d  nop     dword ptr [rax+rax+00h]
0x18004b082  mov     rbx, rax
0x18004b085  lea     edx, [rsi+5]; uCmd
0x18004b088  mov     rcx, rax; hWnd
0x18004b08b  call    cs:__imp_GetWindow
0x18004b092  nop     dword ptr [rax+rax+00h]
0x18004b097  mov     r14, rax
0x18004b09a  test    rax, rax
0x18004b09d  cmovz   r14, rbx
0x18004b0a1  xorps   xmm0, xmm0
0x18004b0a4  movups  xmmword ptr [rbp+0A0h+pclsid.Data1], xmm0
0x18004b0a8  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x18004b0af  xor     edx, edx; length
0x18004b0b1  test    dil, dil
0x18004b0b4  jz      short loc_18004B0BC
0x18004b0b6  mov     rcx, [rcx+20h]
0x18004b0ba  jmp     short loc_18004B0C0
0x18004b0bc  mov     rcx, [rcx+10h]; string
0x18004b0c0  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b0c7  nop     dword ptr [rax+rax+00h]
0x18004b0cc  lea     rdx, [rbp+0A0h+pclsid]; pclsid
0x18004b0d0  mov     rcx, rax; lpsz
0x18004b0d3  call    cs:__imp_CLSIDFromString
0x18004b0da  nop     dword ptr [rax+rax+00h]
0x18004b0df  mov     ebx, eax
0x18004b0e1  test    eax, eax
0x18004b0e3  jns     short loc_18004B114
0x18004b0e5  mov     rcx, [rbp+0A8h]; this
0x18004b0ec  mov     r9d, eax; char *
0x18004b0ef  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b0f6  mov     edx, 52Eh; void *
0x18004b0fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b100  nop
0x18004b101  mov     [rbp+0A0h+var_C8], r13b
0x18004b105  lea     rcx, [rbp+0A0h+var_F0]
0x18004b109  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b10e  nop
0x18004b10f  jmp     loc_18004C73E
0x18004b114  movaps  xmm0, xmmword ptr [rbp+0A0h+pclsid.Data1]
0x18004b118  movdqa  xmmword ptr [rbp+0A0h+string], xmm0
0x18004b11d  lea     rdx, [rbp+0A0h+lpMem]
0x18004b121  lea     rcx, [rbp+0A0h+string]
0x18004b125  call    cs:__imp_GetEnrollmentPartnerOpaqueID
0x18004b12c  nop     dword ptr [rax+rax+00h]
0x18004b131  mov     ebx, eax
0x18004b133  test    eax, eax
0x18004b135  jns     short loc_18004B166
0x18004b137  mov     rcx, [rbp+0A8h]; this
0x18004b13e  mov     r9d, eax; char *
0x18004b141  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b148  mov     edx, 52Fh; void *
0x18004b14d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b152  nop
0x18004b153  mov     [rbp+0A0h+var_C8], r13b
0x18004b157  lea     rcx, [rbp+0A0h+var_F0]
0x18004b15b  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b160  nop
0x18004b161  jmp     loc_18004C73E
0x18004b166  mov     ecx, esi
0x18004b168  call    cs:__imp_RoInitialize
0x18004b16f  nop     dword ptr [rax+rax+00h]
0x18004b174  mov     ebx, eax
0x18004b176  test    eax, eax
0x18004b178  jns     short loc_18004B1A9
0x18004b17a  mov     rcx, [rbp+0A8h]; this
0x18004b181  mov     r9d, eax; char *
0x18004b184  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b18b  mov     edx, 531h; void *
0x18004b190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b195  nop
0x18004b196  mov     [rbp+0A0h+var_C8], r13b
0x18004b19a  lea     rcx, [rbp+0A0h+var_F0]
0x18004b19e  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b1a3  nop
0x18004b1a4  jmp     loc_18004C73E
0x18004b1a9  mov     [rsp+1A0h+var_157], sil
0x18004b1ae  lea     rcx, [rbp+0A0h+var_F8]
0x18004b1b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b1b7  lea     rax, [rbp+0A0h+var_F8]
0x18004b1bb  mov     [rsp+1A0h+ppv], rax; int
0x18004b1c0  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18004b1c7  mov     r8d, esi; dwClsContext
0x18004b1ca  xor     edx, edx; pUnkOuter
0x18004b1cc  lea     rcx, CLSID_GlobalOptions; rclsid
0x18004b1d3  call    cs:__imp_CoCreateInstance
0x18004b1da  nop     dword ptr [rax+rax+00h]
0x18004b1df  mov     ebx, eax
0x18004b1e1  test    eax, eax
0x18004b1e3  jns     short loc_18004B214
0x18004b1e5  mov     rcx, [rbp+0A8h]; this
0x18004b1ec  mov     r9d, eax; char *
0x18004b1ef  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b1f6  mov     edx, 537h; void *
0x18004b1fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b200  nop
0x18004b201  mov     [rbp+0A0h+var_C8], r13b
0x18004b205  lea     rcx, [rbp+0A0h+var_F0]
0x18004b209  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b20e  nop
0x18004b20f  jmp     loc_18004C73E
0x18004b214  mov     rcx, [rbp+0A0h+var_F8]
0x18004b218  mov     rax, [rcx]
0x18004b21b  lea     r8, [rbp+0A0h+var_A0]
0x18004b21f  mov     edi, 5
0x18004b224  mov     edx, edi
0x18004b226  mov     rax, [rax+20h]
0x18004b22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b22f  mov     ebx, eax
0x18004b231  test    eax, eax
0x18004b233  jns     short loc_18004B264
0x18004b235  mov     rcx, [rbp+0A8h]; this
0x18004b23c  mov     r9d, eax; char *
0x18004b23f  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b246  mov     edx, 538h; void *
0x18004b24b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b250  nop
0x18004b251  mov     [rbp+0A0h+var_C8], r13b
0x18004b255  lea     rcx, [rbp+0A0h+var_F0]
0x18004b259  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b25e  nop
0x18004b25f  jmp     loc_18004C73E
0x18004b264  mov     rcx, [rbp+0A0h+var_F8]
0x18004b268  mov     rax, [rcx]
0x18004b26b  mov     r8, rsi
0x18004b26e  mov     edx, edi
0x18004b270  mov     rax, [rax+18h]
0x18004b274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b279  mov     ebx, eax
0x18004b27b  test    eax, eax
0x18004b27d  jns     short loc_18004B2AE
0x18004b27f  mov     rcx, [rbp+0A8h]; this
0x18004b286  mov     r9d, eax; char *
0x18004b289  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b290  mov     edx, 539h; void *
0x18004b295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b29a  nop
0x18004b29b  mov     [rbp+0A0h+var_C8], r13b
0x18004b29f  lea     rcx, [rbp+0A0h+var_F0]
0x18004b2a3  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b2a8  nop
0x18004b2a9  jmp     loc_18004C73E
0x18004b2ae  mov     [rsp+1A0h+var_158], sil
0x18004b2b3  mov     [rsp+1A0h+var_148], r13
0x18004b2b8  lea     rcx, [rbp+0A0h+var_70]; string
0x18004b2bc  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x18004b2c1  lea     rdx, [rsp+1A0h+var_148]
0x18004b2c6  mov     rcx, [rax]
0x18004b2c9  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x18004b2ce  mov     ebx, eax
0x18004b2d0  test    eax, eax
0x18004b2d2  jns     short loc_18004B30E
0x18004b2d4  mov     rcx, [rbp+0A8h]; this
0x18004b2db  mov     r9d, eax; char *
0x18004b2de  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b2e5  mov     edx, 53Dh; void *
0x18004b2ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b2ef  nop
0x18004b2f0  lea     rcx, [rsp+1A0h+var_148]
0x18004b2f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b2fa  nop
0x18004b2fb  mov     [rbp+0A0h+var_C8], r13b
0x18004b2ff  lea     rcx, [rbp+0A0h+var_F0]
0x18004b303  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b308  nop
0x18004b309  jmp     loc_18004C73E
0x18004b30e  mov     [rsp+1A0h+var_140], r13
0x18004b313  mov     rdi, [rsp+1A0h+var_148]
0x18004b318  mov     rax, [rdi]
0x18004b31b  mov     rbx, [rax+58h]
0x18004b31f  lea     rcx, [rsp+1A0h+var_140]
0x18004b324  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b329  lea     rcx, [rbp+0A0h+var_70]; string
0x18004b32d  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x18004b332  lea     r8, [rsp+1A0h+var_140]
0x18004b337  mov     rdx, [rax]
0x18004b33a  mov     rcx, rdi
0x18004b33d  mov     rax, rbx
0x18004b340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b345  mov     ebx, eax
0x18004b347  test    eax, eax
0x18004b349  jns     short loc_18004B390
0x18004b34b  mov     rcx, [rbp+0A8h]; this
0x18004b352  mov     r9d, eax; char *
0x18004b355  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b35c  mov     edx, 540h; void *
0x18004b361  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b366  nop
0x18004b367  lea     rcx, [rsp+1A0h+var_140]
0x18004b36c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b371  nop
0x18004b372  lea     rcx, [rsp+1A0h+var_148]
0x18004b377  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b37c  nop
0x18004b37d  mov     [rbp+0A0h+var_C8], r13b
0x18004b381  lea     rcx, [rbp+0A0h+var_F0]
0x18004b385  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b38a  nop
0x18004b38b  jmp     loc_18004C73E
0x18004b390  mov     [rsp+1A0h+var_130], r13
0x18004b395  lea     rdx, [rsp+1A0h+var_130]
0x18004b39a  mov     rcx, [rsp+1A0h+var_140]
0x18004b39f  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x18004b3a4  mov     ebx, eax
0x18004b3a6  test    eax, eax
0x18004b3a8  jns     short loc_18004B3FA
0x18004b3aa  mov     rcx, [rbp+0A8h]; this
0x18004b3b1  mov     r9d, eax; char *
0x18004b3b4  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b3bb  mov     edx, 543h; void *
0x18004b3c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b3c5  nop
0x18004b3c6  lea     rcx, [rsp+1A0h+var_130]
0x18004b3cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b3d0  nop
0x18004b3d1  lea     rcx, [rsp+1A0h+var_140]
0x18004b3d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b3db  nop
0x18004b3dc  lea     rcx, [rsp+1A0h+var_148]
0x18004b3e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b3e6  nop
0x18004b3e7  mov     [rbp+0A0h+var_C8], r13b
0x18004b3eb  lea     rcx, [rbp+0A0h+var_F0]
0x18004b3ef  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b3f4  nop
0x18004b3f5  jmp     loc_18004C73E
0x18004b3fa  mov     [rsp+1A0h+var_128], r13
0x18004b3ff  lea     rcx, [rbp+0A0h+var_70]; string
0x18004b403  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x18004b408  lea     rdx, [rsp+1A0h+var_128]
0x18004b40d  mov     rcx, [rax]
0x18004b410  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x18004b415  mov     ebx, eax
0x18004b417  test    eax, eax
0x18004b419  jns     short loc_18004B476
0x18004b41b  mov     rcx, [rbp+0A8h]; this
0x18004b422  mov     r9d, eax; char *
0x18004b425  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004b42c  mov     edx, 546h; void *
0x18004b431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b436  nop
0x18004b437  lea     rcx, [rsp+1A0h+var_128]
0x18004b43c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b441  nop
0x18004b442  lea     rcx, [rsp+1A0h+var_130]
0x18004b447  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b44c  nop
0x18004b44d  lea     rcx, [rsp+1A0h+var_140]
0x18004b452  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b457  nop
0x18004b458  lea     rcx, [rsp+1A0h+var_148]
0x18004b45d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b462  nop
0x18004b463  mov     [rbp+0A0h+var_C8], r13b
0x18004b467  lea     rcx, [rbp+0A0h+var_F0]
0x18004b46b  call    _lambda_154327c85f8c76ffef0330697a9c13c5___operator__
0x18004b470  nop
0x18004b471  jmp     loc_18004C73E
0x18004b476  mov     [rsp+1A0h+var_138], r13
0x18004b47b  mov     rsi, [rsp+1A0h+var_128]
0x18004b480  mov     rax, [rsi]
0x18004b483  mov     rdi, [rax+38h]
0x18004b487  lea     rcx, [rsp+1A0h+var_138]
  ... truncated ...
```
