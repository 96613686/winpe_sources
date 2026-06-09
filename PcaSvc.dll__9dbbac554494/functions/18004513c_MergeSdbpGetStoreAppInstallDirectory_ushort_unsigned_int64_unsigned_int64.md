# MergeSdbpGetStoreAppInstallDirectory(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x18004513c`
- end: `0x1800468b8`
- name: `?MergeSdbpGetStoreAppInstallDirectory@@YAKPEAG_KPEA_K@Z`
- size: `6012`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043424`

## callees

- `0x18000c018`
- `0x18000dc08`
- `0x180012920`
- `0x18003c608`
- `0x18003ccf8`
- `0x18003d87c`
- `0x18003fd8c`
- `0x18004513c`
- `0x18004eb34`
- `0x18004f958`
- `0x180096f60`
- `0x180097a30`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004520b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004520b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800456fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800452c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004531d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800452c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004531d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004518f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004524a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800452e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180045342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004518f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004524a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800452e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180045342`

## string_xrefs

- `0x1800452df`: `Microsoft.ApplicationCompatibilityEnhancements`
- `0x18004539f`: `FindPackagesByUserSecurityIdNamePublisher failed (%d)`
- `0x1800451a5`: `WindowsCreateString failed (%d)`
- `0x18004526e`: `WindowsCreateString failed (%d)`
- `0x1800451ef`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x180045275`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x1800453ac`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x18004542e`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x1800454a8`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x1800454ee`: `MergeSdbpGetStoreAppInstallDirectory`
- `0x180046507`: `get_Path failed (%d)`
- `0x180045670`: `%ls\AppXManifest.xml`
- `0x180045573`: `Package is installed but not registered, ignoring`
- `0x180046607`: `get_InstalledLocation failed (%d)`
- `0x1800458c0`: `%ls\ApplicationCompatibilityEnhancements.cat`
- `0x180046324`: `CoCreateInstance failed (%d)`
- `0x1800463e1`: `CoCreateInstance failed (%d)`
- `0x18004625d`: `CreateStreamOnFile failed (%d)`
- `0x18004618c`: `CreateManifestReader failed (%d)`
- `0x180045bfd`: `StringCchCopyW failed (%d)`
- `0x1800467dc`: `StringCchCopyW failed (%d)`
- `0x180045bb2`: `MoveNext failed (%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall MergeSdbpGetStoreAppInstallDirectory(unsigned __int16 *a1, __int64 a2, unsigned __int64 *a3)
{
  HRESULT v4; // eax
  const char *v5; // r9
  int v6; // r8d
  int v7; // eax
  unsigned int v8; // ebx
  DWORD LastError; // eax
  HRESULT v10; // eax
  int v11; // r8d
  HSTRING v12; // rbx
  HRESULT v13; // eax
  HSTRING v14; // rbx
  HRESULT v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // edx
  unsigned __int64 v25; // r13
  int v26; // eax
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)); // rbx
  int v33; // eax
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v35)(_QWORD, GUID *, __int64 **); // rdi
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *StringRawBuffer; // r15
  int v40; // eax
  HRESULT v41; // eax
  HRESULT v42; // eax
  LPVOID v43; // rdi
  __int64 (__fastcall *v44)(LPVOID, unsigned __int16 *, __int64, _QWORD, int, __int64 *); // rbx
  int v45; // eax
  LPVOID v46; // rdi
  __int64 (__fastcall *v47)(LPVOID, __int64, __int64 *); // rbx
  int v48; // eax
  int v49; // eax
  int v50; // eax
  __int64 v51; // rcx
  LPVOID v52; // rcx
  LPVOID v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  unsigned __int8 **v56; // r8
  unsigned int *v57; // r9
  unsigned int v58; // eax
  __int64 v59; // rcx
  LPVOID v60; // rcx
  LPVOID v61; // rcx
  __int64 v62; // rcx
  int v63; // eax
  __int64 v64; // rcx
  LPVOID v65; // rcx
  LPVOID v66; // rcx
  __int64 v67; // rcx
  int v68; // eax
  __int64 v69; // rcx
  LPVOID v70; // rcx
  LPVOID v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  LPVOID v75; // rcx
  LPVOID v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  LPVOID v80; // rcx
  LPVOID v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  LPVOID v85; // rcx
  LPVOID v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  LPVOID v90; // rcx
  LPVOID v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rcx
  DWORD v94; // eax
  __int64 v95; // rcx
  LPVOID v96; // rcx
  LPVOID v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  LPVOID v101; // rcx
  LPVOID v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  LPVOID v105; // rcx
  LPVOID v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rcx
  LPVOID v109; // rcx
  LPVOID v110; // rcx
  __int64 v111; // rcx
  __int64 v112; // rcx
  LPVOID v113; // rcx
  LPVOID v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rcx
  LPVOID v117; // rcx
  __int64 v118; // rcx
  __int64 v119; // rcx
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  __int64 v123; // rcx
  __int64 v124; // rcx
  __int64 v125; // rcx
  __int64 v126; // rcx
  __int64 v127; // rcx
  __int64 v128; // rcx
  __int64 v129; // rcx
  DWORD v130; // eax
  __int64 v131; // rcx
  __int64 v132; // rcx
  __int64 v133; // rcx
  __int64 v134; // rcx
  int v135; // eax
  __int64 v136; // rcx
  __int64 v137; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  LPVOID *ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+20h] [rbp-E0h]
  unsigned int v142; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v143; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v144; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v145[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v146; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v147; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v148; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v149; // [rsp+78h] [rbp-88h] BYREF
  __int64 v150; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v151; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v152[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v153; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall ***v154)(_QWORD, GUID *, __int64 **); // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v155; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v156; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v157; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v158; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v159; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v160; // [rsp+D0h] [rbp-30h] BYREF
  int v161; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING string; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v163; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v164[264]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v165[264]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v166[264]; // [rsp+510h] [rbp+410h] BYREF

  v163 = a1;
  v142 = 0;
  v160 = 0;
  string = 0;
  v4 = WindowsCreateString(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &string);
  if ( PcaFailedHr(&v142, v4) )
  {
    v5 = "WindowsCreateString failed (%d)";
    v6 = 882;
LABEL_5:
    v8 = v142;
    AslLogCallPrintf(1, (unsigned int)"MergeSdbpGetStoreAppInstallDirectory", v6, (_DWORD)v5, v142);
    goto LABEL_252;
  }
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v160);
  v7 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(string, &v160);
  if ( PcaFailedHr(&v142, v7) )
  {
    v5 = "ActivateInstance failed (%d)";
    v6 = 888;
    goto LABEL_5;
  }
  if ( !v160 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 14;
    v8 = LastError;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      896,
      (unsigned int)"ActivateInstance produced null (%d)",
      LastError);
    goto LABEL_252;
  }
  v148 = 0;
  v147 = 0;
  v151 = 0;
  v10 = WindowsCreateString(&sourceString, 0, &v151);
  if ( PcaFailedHr(&v142, v10) )
  {
    v11 = 905;
LABEL_13:
    v8 = v142;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      v11,
      (unsigned int)"WindowsCreateString failed (%d)",
      v142);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v147);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v148);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v151);
    goto LABEL_252;
  }
  v12 = v148;
  if ( v148 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v159);
    WindowsDeleteString(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v159);
  }
  v148 = 0;
  v13 = WindowsCreateString(L"Microsoft.ApplicationCompatibilityEnhancements", 0x2Eu, &v148);
  if ( PcaFailedHr(&v142, v13) )
  {
    v11 = 909;
    goto LABEL_13;
  }
  v14 = v147;
  if ( v147 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v159);
    WindowsDeleteString(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v159);
  }
  v147 = 0;
  v15 = WindowsCreateString(
          L"CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US",
          0x50u,
          &v147);
  if ( PcaFailedHr(&v142, v15) )
  {
    v11 = 913;
    goto LABEL_13;
  }
  v144 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v160 + 104LL))(
          v160,
          v148,
          v147,
          &v144);
  if ( PcaFailedHr(&v142, v16) )
  {
    v8 = v142;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      919,
      (unsigned int)"FindPackagesByUserSecurityIdNamePublisher failed (%d)",
      v142);
    v17 = v144;
    if ( v144 )
    {
      v144 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_14;
  }
  v150 = 0;
  v18 = v144;
  v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v144 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
  v20 = v19(v18, &v150);
  if ( PcaFailedHr(&v142, v20) )
  {
    v8 = v142;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      925,
      (unsigned int)"First failed (%d)",
      v142);
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
    v21 = v144;
    if ( v144 )
    {
      v144 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_14;
  }
  v145[0] = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v150 + 56LL))(v150, v145);
  if ( PcaFailedHr(&v142, v22) )
  {
    v8 = v142;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      931,
      (unsigned int)"get_HasCurrent failed (%d)",
      v142);
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
    v23 = v144;
    if ( v144 )
    {
      v144 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_14;
  }
  v24 = 0;
  v25 = 0;
  v164[0] = 0;
  do
  {
    if ( !v145[0] )
      break;
    v143 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v150 + 48LL))(v150, &v143);
    if ( PcaFailedHr(&v142, v26) )
    {
      v8 = v142;
      LODWORD(ppv) = v142;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        947,
        (unsigned int)"get_Current failed (%d)",
        ppv);
      v133 = v143;
      if ( v143 )
      {
        v143 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
      }
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
      v134 = v144;
      if ( v144 )
      {
        v144 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 16LL))(v134);
      }
      goto LABEL_14;
    }
    if ( !v143 )
    {
      v130 = GetLastError();
      if ( !v130 )
        v130 = 14;
      v8 = v130;
      LODWORD(ppv) = v130;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        955,
        (unsigned int)"get_Current produced null (%d)",
        ppv);
      v131 = v143;
      if ( v143 )
      {
        v143 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
      }
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
      v132 = v144;
      if ( v144 )
      {
        v144 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
      }
      goto LABEL_14;
    }
    v152[0] = 0;
    v29 = IsPackageRegistered((unsigned int)&v160, (unsigned int)&v143, v27, v28, (__int64)v152);
    if ( PcaFailedHr(&v142, v29) )
    {
      v8 = v142;
      LODWORD(ppv) = v142;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        961,
        (unsigned int)"Failed to check if package is registered (%d)",
        ppv);
      v128 = v143;
      if ( v143 )
      {
        v143 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
      }
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
      v129 = v144;
      if ( v144 )
      {
        v144 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
      }
      goto LABEL_14;
    }
    if ( v152[0] )
    {
      v154 = 0;
      v31 = v143;
      v32 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)))(*(_QWORD *)v143 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
      v33 = v32(v31, &v154);
      if ( PcaFailedHr(&v142, v33) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          971,
          (unsigned int)"get_InstalledLocation failed (%d)",
          ppv);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v126 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v127 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
        }
        goto LABEL_14;
      }
      v155 = 0;
      v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v154;
      v35 = **v154;
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
      v36 = v35(v34, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v155);
      if ( PcaFailedHr(&v142, v36) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          977,
          (unsigned int)"As failed (%d)",
          ppv);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v124 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v125 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
        }
        goto LABEL_14;
      }
      v156 = 0;
      v37 = *v155;
      v156 = 0;
      v38 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v37 + 96))(v155, &v156);
      if ( PcaFailedHr(&v142, v38) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          983,
          (unsigned int)"get_Path failed (%d)",
          ppv);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v122 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v123 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        }
        goto LABEL_14;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v156, 0);
      v40 = StringCchPrintfW(v165, 0x104u, L"%ls\\AppXManifest.xml", StringRawBuffer);
      if ( PcaFailedHr(&v142, v40) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          995,
          (unsigned int)"StringCchPrintfW failed (%d)",
          ppv);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v120 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v121 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
        }
        goto LABEL_14;
      }
      v146 = 0;
      v41 = CoCreateInstance(
              &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
              0,
              1u,
              &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
              &v146);
      if ( PcaFailedHr(&v142, v41) )
      {
        v8 = v142;
        LODWORD(ppva) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1004,
          (unsigned int)"CoCreateInstance failed (%d)",
          ppva);
        v117 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v117 + 16LL))(v117);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v118 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v119 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
        }
        goto LABEL_14;
      }
      v149 = 0;
      v42 = CoCreateInstance(
              &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
              0,
              1u,
              &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
              &v149);
      if ( PcaFailedHr(&v142, v42) )
      {
        v8 = v142;
        LODWORD(ppvb) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1013,
          (unsigned int)"CoCreateInstance failed (%d)",
          ppvb);
        v113 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v113 + 16LL))(v113);
        }
        v114 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v114 + 16LL))(v114);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v115 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v115 + 16LL))(v115);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v116 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
        }
        goto LABEL_14;
      }
      v157 = 0;
      v43 = v149;
      v44 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64, _QWORD, int, __int64 *))(*(_QWORD *)v149
                                                                                                  + 40LL);
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
      v45 = v44(v43, v165, 1, 0, 128, &v157);
      if ( PcaFailedHr(&v142, v45) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1023,
          (unsigned int)"CreateStreamOnFile failed (%d)",
          ppv);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
        v109 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v109 + 16LL))(v109);
        }
        v110 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v110 + 16LL))(v110);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v111 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v112 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
        }
        goto LABEL_14;
      }
      v158 = 0;
      v46 = v146;
      v47 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v146 + 40LL);
      Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
      v48 = v47(v46, v157, &v158);
      if ( PcaFailedHr(&v142, v48) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1029,
          (unsigned int)"CreateManifestReader failed (%d)",
          ppv);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
        v105 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v105 + 16LL))(v105);
        }
        v106 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v106 + 16LL))(v106);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v107 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v108 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
        }
        goto LABEL_14;
      }
      v153 = 0;
      v49 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v158 + 24LL))(v158, &v153);
      if ( PcaFailedHr(&v142, v49) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1035,
          (unsigned int)"GetPackageId failed (%d)",
          ppv);
        v100 = v153;
        if ( v153 )
        {
          v153 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
        v101 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v101 + 16LL))(v101);
        }
        v102 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v102 + 16LL))(v102);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v103 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v104 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
        }
        goto LABEL_14;
      }
      if ( !v153 )
      {
        v94 = GetLastError();
        if ( !v94 )
          v94 = 14;
        v8 = v94;
        LODWORD(ppv) = v94;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1043,
          (unsigned int)"GetPackageId returned null (%d)",
          ppv);
        v95 = v153;
        if ( v153 )
        {
          v153 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
        v96 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
        }
        v97 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v97 + 16LL))(v97);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v98 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v99 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        }
        goto LABEL_14;
      }
      v161 = 0;
      v50 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v153 + 32LL))(v153, &v161);
      if ( PcaFailedHr(&v142, v50) )
      {
        v8 = v142;
        LODWORD(ppv) = v142;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
          1049,
          (unsigned int)"GetArchitecture failed (%d)",
          ppv);
        v89 = v153;
        if ( v153 )
        {
          v153 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
        v90 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v90 + 16LL))(v90);
        }
        v91 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v91 + 16LL))(v91);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v92 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
        v93 = v144;
        if ( v144 )
        {
          v144 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
        }
        goto LABEL_14;
      }
      if ( v161 == 9 )
      {
        v55 = StringCchPrintfW(v166, 0x104u, L"%ls\\ApplicationCompatibilityEnhancements.cat", StringRawBuffer);
        if ( PcaFailedHr(&v142, v55) )
        {
          v8 = v142;
          LODWORD(ppv) = v142;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
            1083,
            (unsigned int)"StringCchPrintfW failed (%d)",
            ppv);
          v84 = v153;
          if ( v153 )
          {
            v153 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
          }
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
          v85 = v149;
          if ( v149 )
          {
            v149 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v85 + 16LL))(v85);
          }
          v86 = v146;
          if ( v146 )
          {
            v146 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v86 + 16LL))(v86);
          }
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
          v87 = v143;
          if ( v143 )
          {
            v143 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
          }
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
          v88 = v144;
          if ( v144 )
          {
            v144 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
          }
          goto LABEL_14;
        }
        v58 = MergeSdbpVerifySignatureAgainstCatalog(v165, v166, v56, v57);
        v142 = v58;
        if ( v58 )
        {
          LODWORD(ppv) = v58;
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
            1088,
            (unsigned int)"MergeSdbpVerifySignatureAgainstCatalog failed, ignoring this app instance (%d)",
            ppv);
          v59 = v153;
          if ( v153 )
          {
            v153 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          }
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
          v60 = v149;
          if ( v149 )
          {
            v149 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
          }
          v61 = v146;
          if ( v146 )
          {
            v146 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
          }
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
          Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
          v62 = v143;
          if ( v143 )
          {
            v143 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          }
        }
        else
        {
          v159 = 0;
          v63 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v153 + 48LL))(v153, &v159);
          if ( PcaFailedHr(&v142, v63) )
          {
            v8 = v142;
            LODWORD(ppv) = v142;
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
              1094,
              (unsigned int)"GetVersion failed (%d)",
              ppv);
            v79 = v153;
            if ( v153 )
            {
              v153 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
            v80 = v149;
            if ( v149 )
            {
              v149 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
            }
            v81 = v146;
            if ( v146 )
            {
              v146 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v81 + 16LL))(v81);
            }
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
            v82 = v143;
            if ( v143 )
            {
              v143 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
            v83 = v144;
            if ( v144 )
            {
              v144 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
            }
            goto LABEL_14;
          }
          if ( v159 > v25 )
          {
            v68 = StringCchCopyW(v164, 0x104u, StringRawBuffer);
            if ( PcaFailedHr(&v142, v68) )
            {
              v8 = v142;
              LODWORD(ppv) = v142;
              AslLogCallPrintf(
                1,
                (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
                1109,
                (unsigned int)"StringCchCopyW failed (%d)",
                ppv);
              v74 = v153;
              if ( v153 )
              {
                v153 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
              }
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
              v75 = v149;
              if ( v149 )
              {
                v149 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v75 + 16LL))(v75);
              }
              v76 = v146;
              if ( v146 )
              {
                v146 = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v76 + 16LL))(v76);
              }
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
              v77 = v143;
              if ( v143 )
              {
                v143 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
              }
              Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
              v78 = v144;
              if ( v144 )
              {
                v144 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
              }
              goto LABEL_14;
            }
            v25 = v159;
            if ( a3 )
              *a3 = v159;
            v69 = v153;
            if ( v153 )
            {
              v153 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
            v70 = v149;
            if ( v149 )
            {
              v149 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v70 + 16LL))(v70);
            }
            v71 = v146;
            if ( v146 )
            {
              v146 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v71 + 16LL))(v71);
            }
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
            v72 = v143;
            if ( v143 )
            {
              v143 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            }
          }
          else
          {
            v64 = v153;
            if ( v153 )
            {
              v153 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            }
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
            v65 = v149;
            if ( v149 )
            {
              v149 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v65 + 16LL))(v65);
            }
            v66 = v146;
            if ( v146 )
            {
              v146 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
            }
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
            Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
            v67 = v143;
            if ( v143 )
            {
              v143 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
            }
          }
        }
      }
      else
      {
        v51 = v153;
        if ( v153 )
        {
          v153 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v158);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v157);
        v52 = v149;
        if ( v149 )
        {
          v149 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
        }
        v53 = v146;
        if ( v146 )
        {
          v146 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v53 + 16LL))(v53);
        }
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v156);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v155);
        Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v154);
        v54 = v143;
        if ( v143 )
        {
          v143 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        }
      }
    }
    else
    {
      AslLogCallPrintf(
        0,
        (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
        965,
        (unsigned int)"Package is installed but not registered, ignoring");
      v30 = v143;
      if ( v143 )
      {
        v143 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
    }
    v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v150 + 64LL))(v150, v145);
  }
  while ( v24 >= 0 );
  if ( PcaFailedHr(&v142, v24) )
  {
    v8 = v142;
    LODWORD(ppv) = v142;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      1119,
      (unsigned int)"MoveNext failed (%d)",
      ppv);
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
    v73 = v144;
    if ( v144 )
    {
      v144 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    }
    goto LABEL_14;
  }
  v135 = StringCchCopyW(v163, 0x104u, v164);
  if ( PcaFailedHr(&v142, v135) )
  {
    v8 = v142;
    LODWORD(ppv) = v142;
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGetStoreAppInstallDirectory",
      1124,
      (unsigned int)"StringCchCopyW failed (%d)",
      ppv);
    Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
    v136 = v144;
    if ( v144 )
    {
      v144 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
    }
    goto LABEL_14;
  }
  if ( a3 && !v164[0] )
    *a3 = -1;
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v150);
  v137 = v144;
  if ( v144 )
  {
    v144 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v147);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v148);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v151);
  v8 = 0;
LABEL_252:
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(&v160);
  return v8;
}

```

## disassembly

```asm
0x18004513c  mov     [rsp-8+arg_8], rbx
0x180045141  push    rbp
0x180045142  push    rsi
0x180045143  push    rdi
0x180045144  push    r12
0x180045146  push    r13
0x180045148  push    r14
0x18004514a  push    r15
0x18004514c  lea     rbp, [rsp-630h]
0x180045154  sub     rsp, 730h
0x18004515b  mov     rax, cs:__security_cookie
0x180045162  xor     rax, rsp
0x180045165  mov     [rbp+660h+var_40], rax
0x18004516c  mov     r12, r8
0x18004516f  mov     [rbp+660h+var_678], rcx
0x180045173  xor     edi, edi
0x180045175  mov     [rsp+760h+var_720], edi
0x180045179  mov     [rbp+660h+var_690], rdi
0x18004517d  mov     [rbp+660h+string], rdi
0x180045181  lea     r8, [rbp+660h+string]; string
0x180045185  lea     edx, [rdi+2Ch]; length
0x180045188  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18004518f  call    cs:__imp_WindowsCreateString
0x180045195  mov     edx, eax; int
0x180045197  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004519c  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800451a1  test    al, al
0x1800451a3  jz      short loc_1800451B4
0x1800451a5  lea     r9, aWindowscreates_1; "WindowsCreateString failed (%d)"
0x1800451ac  mov     r8d, 372h
0x1800451b2  jmp     short loc_1800451E7
0x1800451b4  lea     rcx, [rbp+660h+var_690]
0x1800451b8  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800451bd  lea     rdx, [rbp+660h+var_690]
0x1800451c1  mov     rcx, [rbp+660h+string]
0x1800451c5  call    ??$ActivateInstance@UIPackageManager@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(HSTRING__ *,Windows::Management::Deployment::IPackageManager * *)
0x1800451ca  mov     edx, eax; int
0x1800451cc  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x1800451d1  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800451d6  test    al, al
0x1800451d8  jz      short loc_180045205
0x1800451da  lea     r9, aActivateinstan; "ActivateInstance failed (%d)"
0x1800451e1  mov     r8d, 378h
0x1800451e7  mov     ebx, [rsp+760h+var_720]
0x1800451eb  mov     dword ptr [rsp+760h+ppv], ebx
0x1800451ef  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800451f6  mov     ecx, 1
0x1800451fb  call    AslLogCallPrintf
0x180045200  jmp     loc_180046879
0x180045205  cmp     [rbp+660h+var_690], rdi
0x180045209  jnz     short loc_18004522F
0x18004520b  call    cs:__imp_GetLastError
0x180045211  test    eax, eax
0x180045213  jnz     short loc_18004521A
0x180045215  mov     eax, 0Eh
0x18004521a  mov     ebx, eax
0x18004521c  mov     dword ptr [rsp+760h+ppv], eax
0x180045220  lea     r9, aActivateinstan_0; "ActivateInstance produced null (%d)"
0x180045227  mov     r8d, 380h
0x18004522d  jmp     short loc_1800451EF
0x18004522f  mov     [rsp+760h+var_6F0], rdi
0x180045234  mov     [rsp+760h+var_6F8], rdi
0x180045239  mov     [rbp+660h+var_6D8], rdi
0x18004523d  lea     r8, [rbp+660h+var_6D8]; string
0x180045241  xor     edx, edx; length
0x180045243  lea     rcx, sourceString; sourceString
0x18004524a  call    cs:__imp_WindowsCreateString
0x180045250  mov     edx, eax; int
0x180045252  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x180045257  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004525c  test    al, al
0x18004525e  jz      short loc_1800452AB
0x180045260  mov     r8d, 389h
0x180045266  mov     ebx, [rsp+760h+var_720]
0x18004526a  mov     dword ptr [rsp+760h+ppv], ebx
0x18004526e  lea     r9, aWindowscreates_1; "WindowsCreateString failed (%d)"
0x180045275  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x18004527c  mov     ecx, 1
0x180045281  call    AslLogCallPrintf
0x180045286  nop
0x180045287  lea     rcx, [rsp+760h+var_6F8]
0x18004528c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180045291  nop
0x180045292  lea     rcx, [rsp+760h+var_6F0]
0x180045297  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18004529c  nop
0x18004529d  lea     rcx, [rbp+660h+var_6D8]
0x1800452a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800452a6  jmp     loc_180046879
0x1800452ab  mov     rbx, [rsp+760h+var_6F0]
0x1800452b0  test    rbx, rbx
0x1800452b3  jz      short loc_1800452D0
0x1800452b5  lea     rcx, [rbp+660h+var_698]; this
0x1800452b9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800452be  mov     rcx, rbx; string
0x1800452c1  call    cs:__imp_WindowsDeleteString
0x1800452c7  lea     rcx, [rbp+660h+var_698]; this
0x1800452cb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800452d0  mov     [rsp+760h+var_6F0], rdi
0x1800452d5  lea     r8, [rsp+760h+var_6F0]; string
0x1800452da  mov     edx, 2Eh ; '.'; length
0x1800452df  lea     rcx, aMicrosoftAppli; "Microsoft.ApplicationCompatibilityEnhan"...
0x1800452e6  call    cs:__imp_WindowsCreateString
0x1800452ec  mov     edx, eax; int
0x1800452ee  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x1800452f3  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800452f8  test    al, al
0x1800452fa  jz      short loc_180045307
0x1800452fc  mov     r8d, 38Dh
0x180045302  jmp     loc_180045266
0x180045307  mov     rbx, [rsp+760h+var_6F8]
0x18004530c  test    rbx, rbx
0x18004530f  jz      short loc_18004532C
0x180045311  lea     rcx, [rbp+660h+var_698]; this
0x180045315  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004531a  mov     rcx, rbx; string
0x18004531d  call    cs:__imp_WindowsDeleteString
0x180045323  lea     rcx, [rbp+660h+var_698]; this
0x180045327  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004532c  mov     [rsp+760h+var_6F8], rdi
0x180045331  lea     r8, [rsp+760h+var_6F8]; string
0x180045336  mov     edx, 50h ; 'P'; length
0x18004533b  lea     rcx, aCnMicrosoftCor; "CN=Microsoft Corporation, O=Microsoft C"...
0x180045342  call    cs:__imp_WindowsCreateString
0x180045348  mov     edx, eax; int
0x18004534a  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004534f  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045354  test    al, al
0x180045356  jz      short loc_180045363
0x180045358  mov     r8d, 391h
0x18004535e  jmp     loc_180045266
0x180045363  mov     [rsp+760h+var_710], rdi
0x180045368  mov     rcx, [rbp+660h+var_690]
0x18004536c  mov     rax, [rcx]
0x18004536f  lea     r9, [rsp+760h+var_710]
0x180045374  mov     r8, [rsp+760h+var_6F8]
0x180045379  mov     rdx, [rsp+760h+var_6F0]
0x18004537e  mov     rax, [rax+68h]
0x180045382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045387  mov     edx, eax; int
0x180045389  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004538e  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045393  test    al, al
0x180045395  jz      short loc_1800453DF
0x180045397  mov     ebx, [rsp+760h+var_720]
0x18004539b  mov     dword ptr [rsp+760h+ppv], ebx
0x18004539f  lea     r9, aFindpackagesby; "FindPackagesByUserSecurityIdNamePublish"...
0x1800453a6  mov     r8d, 397h
0x1800453ac  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800453b3  mov     ecx, 1
0x1800453b8  call    AslLogCallPrintf
0x1800453bd  nop
0x1800453be  mov     rcx, [rsp+760h+var_710]
0x1800453c3  test    rcx, rcx
0x1800453c6  jz      short loc_1800453DA
0x1800453c8  mov     [rsp+760h+var_710], rdi
0x1800453cd  mov     rax, [rcx]
0x1800453d0  mov     rax, [rax+10h]
0x1800453d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453d9  nop
0x1800453da  jmp     loc_180045287
0x1800453df  mov     [rbp+660h+var_6E0], rdi
0x1800453e3  mov     rdi, [rsp+760h+var_710]
0x1800453e8  mov     rax, [rdi]
0x1800453eb  mov     rbx, [rax+30h]
0x1800453ef  lea     rcx, [rbp+660h+var_6E0]
0x1800453f3  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800453f8  lea     rdx, [rbp+660h+var_6E0]
0x1800453fc  mov     rcx, rdi
0x1800453ff  mov     rax, rbx
0x180045402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045407  mov     edx, eax; int
0x180045409  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004540e  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045413  xor     edi, edi
0x180045415  test    al, al
0x180045417  jz      short loc_180045469
0x180045419  mov     ebx, [rsp+760h+var_720]
0x18004541d  mov     dword ptr [rsp+760h+ppv], ebx
0x180045421  lea     r9, aFirstFailedD; "First failed (%d)"
0x180045428  mov     r8d, 39Dh
0x18004542e  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x180045435  lea     ecx, [rdi+1]
0x180045438  call    AslLogCallPrintf
0x18004543d  nop
0x18004543e  lea     rcx, [rbp+660h+var_6E0]
0x180045442  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x180045447  nop
0x180045448  mov     rcx, [rsp+760h+var_710]
0x18004544d  test    rcx, rcx
0x180045450  jz      short loc_180045464
0x180045452  mov     [rsp+760h+var_710], rdi
0x180045457  mov     rax, [rcx]
0x18004545a  mov     rax, [rax+10h]
0x18004545e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045463  nop
0x180045464  jmp     loc_180045287
0x180045469  mov     [rsp+760h+var_708], dil
0x18004546e  mov     rcx, [rbp+660h+var_6E0]
0x180045472  mov     rax, [rcx]
0x180045475  lea     rdx, [rsp+760h+var_708]
0x18004547a  mov     rax, [rax+38h]
0x18004547e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045483  mov     edx, eax; int
0x180045485  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x18004548a  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004548f  test    al, al
0x180045491  jz      short loc_1800454E5
0x180045493  mov     ebx, [rsp+760h+var_720]
0x180045497  mov     dword ptr [rsp+760h+ppv], ebx
0x18004549b  lea     r9, aGetHascurrentF_0; "get_HasCurrent failed (%d)"
0x1800454a2  mov     r8d, 3A3h
0x1800454a8  lea     rdx, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800454af  mov     ecx, 1
0x1800454b4  call    AslLogCallPrintf
0x1800454b9  nop
0x1800454ba  lea     rcx, [rbp+660h+var_6E0]
0x1800454be  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800454c3  nop
0x1800454c4  mov     rcx, [rsp+760h+var_710]
0x1800454c9  test    rcx, rcx
0x1800454cc  jz      short loc_1800454E0
0x1800454ce  mov     [rsp+760h+var_710], rdi
0x1800454d3  mov     rax, [rcx]
0x1800454d6  mov     rax, [rax+10h]
0x1800454da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454df  nop
0x1800454e0  jmp     loc_180045287
0x1800454e5  mov     edx, edi
0x1800454e7  mov     r13, rdi
0x1800454ea  mov     [rbp+660h+var_670], di
0x1800454ee  lea     r14, aMergesdbpgetst_1; "MergeSdbpGetStoreAppInstallDirectory"
0x1800454f5  mov     esi, 1
0x1800454fa  cmp     [rsp+760h+var_708], dil
0x1800454ff  jz      loc_180045B98
0x180045505  mov     [rsp+760h+var_718], rdi
0x18004550a  mov     rcx, [rbp+660h+var_6E0]
0x18004550e  mov     rax, [rcx]
0x180045511  lea     rdx, [rsp+760h+var_718]
0x180045516  mov     rax, [rax+30h]
0x18004551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004551f  mov     edx, eax; int
0x180045521  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x180045526  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004552b  test    al, al
0x18004552d  jnz     loc_18004674B
0x180045533  cmp     [rsp+760h+var_718], rdi
0x180045538  jz      loc_1800466D7
0x18004553e  mov     [rbp+660h+var_6D0], dil
0x180045542  lea     rax, [rbp+660h+var_6D0]
0x180045546  mov     [rsp+760h+ppv], rax
0x18004554b  lea     rdx, [rsp+760h+var_718]
0x180045550  lea     rcx, [rbp+660h+var_690]
0x180045554  call    ?IsPackageRegistered@@YAJAEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@23@PEAXPEBGAEA_N@Z; IsPackageRegistered(Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &,void *,ushort const *,bool &)
0x180045559  mov     edx, eax; int
0x18004555b  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x180045560  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x180045565  test    al, al
0x180045567  jnz     loc_180046670
0x18004556d  cmp     [rbp+660h+var_6D0], dil
0x180045571  jnz     short loc_1800455AC
0x180045573  lea     r9, aPackageIsInsta; "Package is installed but not registered"...
0x18004557a  mov     r8d, 3C5h
0x180045580  mov     rdx, r14
0x180045583  xor     ecx, ecx
0x180045585  call    AslLogCallPrintf
0x18004558a  nop
0x18004558b  mov     rcx, [rsp+760h+var_718]
0x180045590  test    rcx, rcx
0x180045593  jz      short loc_1800455A7
0x180045595  mov     [rsp+760h+var_718], rdi
0x18004559a  mov     rax, [rcx]
0x18004559d  mov     rax, [rax+10h]
0x1800455a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455a6  nop
0x1800455a7  jmp     loc_180045B79
0x1800455ac  mov     [rbp+660h+var_6C0], rdi
0x1800455b0  mov     rdi, [rsp+760h+var_718]
0x1800455b5  mov     rax, [rdi]
0x1800455b8  mov     rbx, [rax+38h]
0x1800455bc  lea     rcx, [rbp+660h+var_6C0]
0x1800455c0  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x1800455c5  lea     rdx, [rbp+660h+var_6C0]
0x1800455c9  mov     rcx, rdi
0x1800455cc  mov     rax, rbx
0x1800455cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455d4  mov     edx, eax; int
0x1800455d6  lea     rcx, [rsp+760h+var_720]; unsigned int *
0x1800455db  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800455e0  xor     edi, edi
0x1800455e2  test    al, al
0x1800455e4  jnz     loc_1800465FF
0x1800455ea  mov     [rbp+660h+var_6B8], rdi
0x1800455ee  mov     rbx, [rbp+660h+var_6C0]
0x1800455f2  mov     rax, [rbx]
0x1800455f5  mov     rdi, [rax]
0x1800455f8  lea     rcx, [rbp+660h+var_6B8]
0x1800455fc  call    ?InternalRelease@?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>::InternalRelease(void)
0x180045601  lea     r8, [rbp+660h+var_6B8]
0x180045605  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
  ... truncated ...
```
