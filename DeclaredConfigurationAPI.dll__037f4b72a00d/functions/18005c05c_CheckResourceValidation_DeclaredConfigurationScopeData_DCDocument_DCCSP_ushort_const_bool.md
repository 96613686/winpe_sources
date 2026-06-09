# CheckResourceValidation(DeclaredConfigurationScopeData *,DCDocument *,DCCSP *,ushort const *,bool *)

- ea: `0x18005c05c`
- end: `0x18005d187`
- name: `?CheckResourceValidation@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEAVDCCSP@@PEBGPEA_N@Z`
- size: `4395`
- prototype: `int(struct DeclaredConfigurationScopeData *, struct DCDocument *, struct DCCSP *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ae150`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180014348`
- `0x1800143c8`
- `0x180014568`
- `0x1800145d8`
- `0x180018160`
- `0x1800185d4`
- `0x1800186b8`
- `0x180018ac0`
- `0x180018cc4`
- `0x1800192b4`
- `0x180019d38`
- `0x18001aaec`
- `0x18001bc98`
- `0x18001d090`
- `0x18001dea8`
- `0x18004b520`
- `0x18004bc88`
- `0x18004cb4c`
- `0x18004d158`
- `0x18004eb9c`
- `0x18004ec50`
- `0x180055f7c`
- `0x180056cf0`
- `0x18005adc8`
- `0x18005c05c`
- `0x18005d190`
- `0x18005ec48`
- `0x18005efe8`
- `0x180086c10`
- `0x180098e10`
- `0x18009a2e4`
- `0x1800a155c`
- `0x1800a21f0`
- `0x1800aa260`
- `0x1800f5c8c`
- `0x1800f9828`
- `0x1800f9d70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c402`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c84f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c402`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c84f`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18005c7ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18005c7ca`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005c29b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005c796`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005c7da`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005c796`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005c7da`
- `OLEAUT32!__imp_SysAllocString` at `0x18005c59a`
- `OLEAUT32!__imp_SysAllocString` at `0x18005c61c`
- `OLEAUT32!__imp_SysAllocString` at `0x18005c59a`
- `OLEAUT32!__imp_SysAllocString` at `0x18005c61c`
- `OLEAUT32!__imp_VariantInit` at `0x18005c0b2`
- `OLEAUT32!__imp_VariantInit` at `0x18005c52d`
- `OLEAUT32!__imp_VariantInit` at `0x18005c0b2`
- `OLEAUT32!__imp_VariantInit` at `0x18005c52d`
- `OLEAUT32!__imp_VariantClear` at `0x18005c387`
- `OLEAUT32!__imp_VariantClear` at `0x18005c4e3`
- `OLEAUT32!__imp_VariantClear` at `0x18005c4ff`
- `OLEAUT32!__imp_VariantClear` at `0x18005c5e4`
- `OLEAUT32!__imp_VariantClear` at `0x18005c920`
- `OLEAUT32!__imp_VariantClear` at `0x18005ca82`
- `OLEAUT32!__imp_VariantClear` at `0x18005cbeb`
- `OLEAUT32!__imp_VariantClear` at `0x18005cd8b`
- `OLEAUT32!__imp_VariantClear` at `0x18005ce70`
- `OLEAUT32!__imp_VariantClear` at `0x18005ceb1`
- `OLEAUT32!__imp_VariantClear` at `0x18005cfab`
- `OLEAUT32!__imp_VariantClear` at `0x18005d109`
- `OLEAUT32!__imp_VariantClear` at `0x18005d14e`
- `OLEAUT32!__imp_VariantClear` at `0x18005c387`
- `OLEAUT32!__imp_VariantClear` at `0x18005c4e3`
- `OLEAUT32!__imp_VariantClear` at `0x18005c4ff`
- `OLEAUT32!__imp_VariantClear` at `0x18005c5e4`
- `OLEAUT32!__imp_VariantClear` at `0x18005c920`
- `OLEAUT32!__imp_VariantClear` at `0x18005ca82`
- `OLEAUT32!__imp_VariantClear` at `0x18005cbeb`
- `OLEAUT32!__imp_VariantClear` at `0x18005cd8b`
- `OLEAUT32!__imp_VariantClear` at `0x18005ce70`
- `OLEAUT32!__imp_VariantClear` at `0x18005ceb1`
- `OLEAUT32!__imp_VariantClear` at `0x18005cfab`
- `OLEAUT32!__imp_VariantClear` at `0x18005d109`
- `OLEAUT32!__imp_VariantClear` at `0x18005d14e`
- `dmEnrollEngine!__imp_GetProviderID` at `0x18005c587`
- `dmEnrollEngine!__imp_GetProviderID` at `0x18005c587`

## string_xrefs

- `0x18005c427`: `OMADM::TargetedUserSID`
- `0x18005c343`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005c4c9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005c5b6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005d0d3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005c31d`: `configManager.Initialize`
- `0x18005c32f`: `Failed to initialize ConfigManager`
- `0x18005c3c3`: `configManager.SetAccountId`
- `0x18005c3d5`: `Failed to set AccountId for ConfigManager`
- `0x18005c5ff`: `Failed to find valid UserSid`
- `0x18005c4a0`: `configManager.SetSessionVariable`
- `0x18005c692`: `configManager.SetSessionVariable`
- `0x18005c4ba`: `Failed to set SetSessionVariable for configManager targetUser`
- `0x18005c78f`: `clientcertificateinstall`
- `0x18005cfc8`: `DeclaredConfigurationStore_GetDriftControlCertificateExpirationThreshold`
- `0x18005cfdd`: `update doc state`
- `0x18005d035`: `update doc state`
- `0x18005d05e`: `update doc state`
- `0x18005d0a6`: `update doc state`
- `0x18005cfe4`: `DeclaredConfigurationStore_WriteResultData`
- `0x18005d03c`: `DeclaredConfigurationStore_WriteResultData`
- `0x18005d065`: `DeclaredConfigurationStore_WriteResultData`
- `0x18005d0ad`: `DeclaredConfigurationStore_WriteResultData`
- `0x18005d0c4`: `Failed to update doc status`
- `0x18005c99d`: `State:Complete`
- `0x18005d015`: `No URIs available to use`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CheckResourceValidation(
        const unsigned __int16 **a1,
        struct DCDocument *a2,
        struct DCCSP *a3,
        unsigned __int16 *a4,
        bool *a5)
{
  bool *v8; // rbx
  _QWORD *v9; // rax
  _WORD *v10; // rdx
  __int64 v11; // r8
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  wchar_t **v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  wchar_t **v21; // r9
  _QWORD *v22; // rax
  int v23; // r9d
  wchar_t **v24; // rdx
  int v25; // ecx
  _QWORD *v26; // r9
  int v27; // eax
  int DriftControlCertificateExpirationThreshold; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  const char *v30; // rax
  __int64 v31; // rdx
  CDeclaredConfigurationLogger *v33; // rax
  char *v34; // r12
  char *v35; // rdx
  const unsigned __int16 *v36; // rcx
  CDeclaredConfigurationLogger *v37; // rax
  unsigned __int16 **v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  CDeclaredConfigurationLogger *v41; // rax
  wchar_t *v42; // r14
  char v43; // bl
  __int64 v44; // rax
  __int64 v45; // rax
  wchar_t *v46; // r8
  const unsigned __int16 *v47; // rdx
  const wchar_t *v48; // rcx
  int v49; // ecx
  char v50; // dl
  __int16 v51; // r8
  int v52; // r9d
  __int64 v53; // rcx
  const wchar_t *v54; // rax
  wchar_t *v55; // rax
  __int64 v56; // rdi
  wchar_t *v57; // rbx
  __int64 v58; // rax
  char *v59; // rdx
  bool v60; // di
  const unsigned __int16 *v61; // rdx
  int v62; // eax
  unsigned __int16 **v63; // r9
  const unsigned __int16 *v64; // r8
  const unsigned __int16 *v65; // rdx
  __int64 v66; // rcx
  const wchar_t *v67; // r9
  unsigned __int16 **v68; // r8
  bool *v69; // rdi
  __int64 v70; // rax
  const unsigned __int16 *v71; // rdx
  int v72; // ecx
  unsigned __int16 **v73; // r9
  const unsigned __int16 *v74; // r8
  const unsigned __int16 *v75; // rdx
  __int64 v76; // rax
  wchar_t *v77; // r8
  const unsigned __int16 *v78; // rdx
  unsigned __int16 **v79; // r9
  const unsigned __int16 *v80; // r8
  const unsigned __int16 *v81; // rdx
  unsigned __int16 **v82; // r8
  __int64 v83; // rax
  wchar_t *v84; // r8
  const unsigned __int16 *v85; // rdx
  int v86; // ecx
  unsigned __int16 **v87; // r9
  const unsigned __int16 *v88; // r8
  const unsigned __int16 *v89; // rdx
  __int64 v90; // rcx
  unsigned __int16 **v91; // r8
  CDeclaredConfigurationLogger *v92; // rax
  const unsigned __int16 *v93; // r8
  const unsigned __int16 *v94; // r9
  CDeclaredConfigurationLogger *v95; // rax
  const unsigned __int16 *v96; // rdx
  const unsigned __int16 *v97; // rcx
  CDeclaredConfigurationLogger *v98; // rax
  __int64 v99; // rdx
  CDeclaredConfigurationLogger *v100; // rax
  const unsigned __int16 *v101; // r8
  CDeclaredConfigurationLogger *v102; // rax
  CDeclaredConfigurationLogger *v103; // rax
  CDeclaredConfigurationLogger *v104; // rax
  int v105; // [rsp+20h] [rbp-1D8h]
  int v106; // [rsp+20h] [rbp-1D8h]
  char *v107; // [rsp+28h] [rbp-1D0h]
  OLECHAR *psz; // [rsp+40h] [rbp-1B8h] BYREF
  unsigned __int16 *v109; // [rsp+48h] [rbp-1B0h] BYREF
  bool *v110; // [rsp+50h] [rbp-1A8h]
  __int16 v111; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 v112; // [rsp+60h] [rbp-198h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-190h] BYREF
  VARIANTARG v114; // [rsp+80h] [rbp-178h] BYREF
  unsigned int v115; // [rsp+98h] [rbp-160h] BYREF
  unsigned __int16 *v116; // [rsp+A0h] [rbp-158h]
  unsigned __int16 *v117; // [rsp+A8h] [rbp-150h] BYREF
  wchar_t *v118; // [rsp+B0h] [rbp-148h] BYREF
  wchar_t *v119; // [rsp+B8h] [rbp-140h]
  unsigned __int16 *v120[3]; // [rsp+C8h] [rbp-130h] BYREF
  unsigned __int64 v121; // [rsp+E0h] [rbp-118h]
  wchar_t *Str[3]; // [rsp+E8h] [rbp-110h] BYREF
  unsigned __int64 v123; // [rsp+100h] [rbp-F8h]
  unsigned __int16 *Src[3]; // [rsp+108h] [rbp-F0h] BYREF
  unsigned __int64 v125; // [rsp+120h] [rbp-D8h]
  struct tagVARIANT v126; // [rsp+130h] [rbp-C8h] BYREF
  _QWORD v127[4]; // [rsp+150h] [rbp-A8h] BYREF
  _BYTE v128[32]; // [rsp+170h] [rbp-88h] BYREF
  VARIANTARG v129; // [rsp+190h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v116 = a4;
  v8 = a5;
  v110 = a5;
  v111 = 0;
  v112 = 0;
  VariantInit(&pvarg);
  std::wstring::wstring((__int64)Str);
  std::wstring::wstring((__int64)v127);
  std::wstring::wstring((__int64)v120);
  v9 = (_QWORD *)((char *)a3 + 88);
  if ( *((_QWORD *)a3 + 14) > 7u )
    v9 = (_QWORD *)*v9;
  v10 = (_WORD *)v9 + 2;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  try
  {
    std::wstring::_Assign<unsigned short>((char **)Str, v10, (char *)v11);
    v12 = (const unsigned __int16 *)Str;
    if ( v123 > 7 )
      v12 = Str[0];
    if ( (unsigned int)DCDoesCspNeedPrefix(v12) )
    {
      v16 = Str;
      if ( v123 > 7 )
        v16 = (wchar_t **)Str[0];
      v17 = std::operator+<unsigned short>(v128, L"./", (char *)a2 + 32);
      v18 = std::operator+<unsigned short>(&v126, v17, L"/");
      v19 = std::operator+<unsigned short>(&v129, v18, v16);
      v20 = std::operator+<unsigned short>(Src, v19, L"/");
      std::wstring::operator=(v127, v20);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(&v129);
      std::wstring::_Tidy_deallocate(&v126);
      std::wstring::_Tidy_deallocate(v128);
      v8 = v110;
    }
    else
    {
      v13 = std::operator+<unsigned short>(&v129, L"./", Str);
      v14 = std::operator+<unsigned short>(Src, v13, L"/");
      std::wstring::operator=(v127, v14);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(&v129);
    }
    v21 = Str;
    if ( v123 > 7 )
      v21 = (wchar_t **)Str[0];
    v22 = (_QWORD *)std::wstring::end(Str, &v126, v15, v21);
    v24 = Str;
    if ( v123 > 7 )
      LODWORD(v24) = Str[0];
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)&v117,
      (_DWORD)v24,
      *v22,
      v23,
      *(__int64 *)&_o_towlower);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      v26 = v127;
      if ( v127[3] > 7u )
        LODWORD(v26) = v127[0];
      McTemplateU0zzd_EventWriteTransfer(
        v25,
        (unsigned int)OrchestratorGenericInformation,
        (unsigned int)L"CheckResourceValidation",
        (_DWORD)v26,
        0);
    }
    *v8 = 0;
    v27 = DCConfigManagerWrap::Initialize((DCConfigManagerWrap *)&v111);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3567,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      v105);
    std::wstring::_Tidy_deallocate(v120);
    std::wstring::_Tidy_deallocate(v127);
    std::wstring::_Tidy_deallocate(Str);
    VariantClear(&pvarg);
    DCConfigManagerWrap::~DCConfigManagerWrap((DCConfigManagerWrap *)&v111);
    return 2147942414LL;
  }
  DriftControlCertificateExpirationThreshold = v27;
  if ( v27 < 0 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"CheckResourceValidation",
      L"configManager.Initialize",
      &word_180142E98,
      DriftControlCertificateExpirationThreshold);
    v30 = "Failed to initialize ConfigManager";
    v31 = 13687;
LABEL_24:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)DriftControlCertificateExpirationThreshold,
      (int)v30,
      v107);
    goto LABEL_25;
  }
  DriftControlCertificateExpirationThreshold = DCConfigManagerWrap::SetAccountId((DCConfigManagerWrap *)&v111, *a1);
  if ( DriftControlCertificateExpirationThreshold < 0 )
  {
    v33 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v33,
      L"CheckResourceValidation",
      L"configManager.SetAccountId",
      &word_180142E98,
      DriftControlCertificateExpirationThreshold);
    v30 = "Failed to set AccountId for ConfigManager";
    v31 = 13697;
    goto LABEL_24;
  }
  v34 = (char *)a2 + 32;
  if ( *((_QWORD *)a2 + 7) <= 7u )
    v35 = (char *)a2 + 32;
  else
    v35 = *(char **)v34;
  if ( !(unsigned int)_o__wcsicmp(L"User", v35) )
  {
    v36 = a1[1];
    if ( !v36 || !*v36 )
    {
      v30 = "Failed to find valid UserSid";
      DriftControlCertificateExpirationThreshold = -2147024809;
      v31 = 13704;
      goto LABEL_24;
    }
    wil::make_bstr(&v117, L"OMADM::TargetedUserSID");
    _variant_t::_variant_t((_variant_t *)&v129, a1[1]);
    v126 = v129;
    DriftControlCertificateExpirationThreshold = DCConfigManagerWrap::SetSessionVariable(
                                                   (DCConfigManagerWrap *)&v111,
                                                   v117,
                                                   &v126);
    if ( DriftControlCertificateExpirationThreshold < 0 )
    {
      v37 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v37,
        L"CheckResourceValidation",
        L"configManager.SetSessionVariable",
        L"targetUser",
        DriftControlCertificateExpirationThreshold);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3594,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)DriftControlCertificateExpirationThreshold,
        (int)"Failed to set SetSessionVariable for configManager targetUser",
        v107);
      VariantClear(&v129);
      v38 = &v117;
LABEL_183:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v38);
      goto LABEL_25;
    }
    VariantClear(&v129);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v117);
  }
  wil::make_bstr(&v109, L"OMADM::ServerID");
  VariantInit(&v114);
  psz = 0;
  *(_OWORD *)&v126.vt = 0;
  if ( (int)DCGetGuidFromEnrollmentId(*a1, (struct _GUID *)&v126) < 0
    || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &psz,
          0),
        (int)GetProviderID(&v126, &psz) < 0) )
  {
    v114.llVal = (LONGLONG)SysAllocString(L"Microsoft Device Management");
    if ( !v114.llVal )
    {
      v39 = 13736;
      goto LABEL_41;
    }
  }
  else
  {
    v114.llVal = (LONGLONG)SysAllocString(psz);
    if ( !v114.llVal )
    {
      v39 = 13730;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8007000ELL,
        v106);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
      VariantClear(&v114);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v109);
      DriftControlCertificateExpirationThreshold = -2147024882;
      goto LABEL_25;
    }
  }
  v114.vt = 8;
  v126 = v114;
  DriftControlCertificateExpirationThreshold = DCConfigManagerWrap::SetSessionVariable(
                                                 (DCConfigManagerWrap *)&v111,
                                                 v109,
                                                 &v126);
  if ( DriftControlCertificateExpirationThreshold < 0 )
  {
    v41 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v41,
      L"CheckResourceValidation",
      L"configManager.SetSessionVariable",
      L"OMADM_SERVERID_VARIABLE_NAME",
      DriftControlCertificateExpirationThreshold);
LABEL_182:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    VariantClear(&v114);
    v38 = &v109;
    goto LABEL_183;
  }
  LOBYTE(v40) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
    v40);
  std::vector<ResourceValidationUrisAndValues>::vector<ResourceValidationUrisAndValues>(&v118, (__int64)a3 + 40);
  v42 = v118;
  *(_QWORD *)&v126.vt = v119;
  if ( v118 == v119 )
  {
LABEL_157:
    std::vector<ResourceValidationUrisAndValues>::_Tidy(&v118);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    VariantClear(&v114);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v109);
    std::wstring::_Tidy_deallocate(v120);
    std::wstring::_Tidy_deallocate(v127);
    std::wstring::_Tidy_deallocate(Str);
    VariantClear(&pvarg);
    DCConfigManagerWrap::~DCConfigManagerWrap((DCConfigManagerWrap *)&v111);
    return 0;
  }
  while ( 1 )
  {
    v43 = 0;
    v44 = *((_QWORD *)v42 + 2);
    if ( *((_QWORD *)v42 + 6) )
      break;
    if ( !v44 )
      goto LABEL_104;
    v70 = std::operator+<unsigned short>(v128, v127, v42);
    std::wstring::operator=(v120, v70);
    std::wstring::_Tidy_deallocate(v128);
    v71 = (const unsigned __int16 *)v120;
    if ( v121 > 7 )
      v71 = v120[0];
    if ( (int)CheckValidationURIValues((struct DCConfigManagerWrap *)&v111, v71, 0) < 0 )
      goto LABEL_104;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      v73 = v120;
      if ( v121 > 7 )
        LODWORD(v73) = v120[0];
      McTemplateU0zzd_EventWriteTransfer(
        v72,
        (unsigned int)OrchestratorGenericInformation,
        (unsigned int)L"CheckResourceValidation:Found Existing Resource and skip refresh",
        (_DWORD)v73,
        0);
    }
    VariantClear(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 60;
    v74 = (const unsigned __int16 *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v74 = *(const unsigned __int16 **)v74;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v75 = (const unsigned __int16 *)a2;
    else
      v75 = *(const unsigned __int16 **)a2;
    DriftControlCertificateExpirationThreshold = DeclaredConfigurationStore_WriteResultData(
                                                   (struct DeclaredConfigurationScopeData *)a1,
                                                   v75,
                                                   v74,
                                                   0,
                                                   v116,
                                                   0,
                                                   L"state",
                                                   &pvarg);
    if ( DriftControlCertificateExpirationThreshold < 0 )
    {
      v102 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v102,
        L"CheckResourceValidation",
        L"DeclaredConfigurationStore_WriteResultData",
        L"update doc state",
        DriftControlCertificateExpirationThreshold);
      v99 = 14092;
      goto LABEL_180;
    }
    v43 = 1;
    if ( (byte_180189FC1 & 4) != 0 )
    {
      v67 = L"State:Success";
LABEL_84:
      v68 = v120;
      if ( v121 > 7 )
        v68 = (unsigned __int16 **)v120[0];
      McTemplateU0zz_EventWriteTransfer(v66, DcSvcResourceAlreadyInstalled, v68, v67);
    }
LABEL_87:
    v69 = v110;
    *v110 = 1;
LABEL_105:
    if ( *((_QWORD *)v42 + 14) && !v43 )
    {
      if ( *((_QWORD *)v42 + 10) )
      {
        v76 = std::operator+<unsigned short>(v128, v127, v42 + 32);
        std::wstring::operator=(v120, v76);
        std::wstring::_Tidy_deallocate(v128);
      }
      else if ( !*((_QWORD *)v42 + 2) )
      {
        v100 = CDeclaredConfigurationLogger::GetLogger();
        v101 = L"Check Failures";
        goto LABEL_174;
      }
      v77 = v42 + 48;
      if ( *((_QWORD *)v42 + 15) > 7u )
        v77 = *(wchar_t **)v77;
      v78 = (const unsigned __int16 *)v120;
      if ( v121 > 7 )
        v78 = v120[0];
      if ( (int)CheckValidationURIValues((struct DCConfigManagerWrap *)&v111, v78, v77) >= 0 )
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          v79 = v120;
          if ( v121 > 7 )
            LODWORD(v79) = v120[0];
          McTemplateU0zzd_EventWriteTransfer(
            0,
            (unsigned int)OrchestratorGenericInformation,
            (unsigned int)L"CheckResourceValidation:Found Resource Failed.  Perform refresh",
            (_DWORD)v79,
            0);
        }
        VariantClear(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = 61;
        v80 = (const unsigned __int16 *)((char *)a2 + 96);
        if ( *((_QWORD *)a2 + 15) > 7u )
          v80 = *(const unsigned __int16 **)v80;
        if ( *((_QWORD *)a2 + 3) <= 7u )
          v81 = (const unsigned __int16 *)a2;
        else
          v81 = *(const unsigned __int16 **)a2;
        DriftControlCertificateExpirationThreshold = DeclaredConfigurationStore_WriteResultData(
                                                       (struct DeclaredConfigurationScopeData *)a1,
                                                       v81,
                                                       v80,
                                                       0,
                                                       v116,
                                                       0,
                                                       L"state",
                                                       &pvarg);
        if ( DriftControlCertificateExpirationThreshold < 0 )
        {
          v103 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v103,
            L"CheckResourceValidation",
            L"DeclaredConfigurationStore_WriteResultData",
            L"update doc state",
            DriftControlCertificateExpirationThreshold);
          v99 = 14145;
LABEL_180:
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)v99,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)DriftControlCertificateExpirationThreshold,
            (int)"Failed to update doc status",
            v107);
          goto LABEL_181;
        }
        v43 = 1;
        if ( (byte_180189FC1 & 4) != 0 )
        {
          v82 = v120;
          if ( v121 > 7 )
            v82 = (unsigned __int16 **)v120[0];
          McTemplateU0zz_EventWriteTransfer(0, DcSvcResourceAlreadyInstalled, v82, L"State:Failed");
        }
        *v69 = 0;
      }
    }
    if ( !*((_QWORD *)v42 + 22) || v43 )
      goto LABEL_156;
    if ( !*((_QWORD *)v42 + 18) )
    {
      if ( *((_QWORD *)v42 + 10) || *((_QWORD *)v42 + 2) )
        goto LABEL_136;
      v100 = CDeclaredConfigurationLogger::GetLogger();
      v101 = L"Check InProgress";
LABEL_174:
      DriftControlCertificateExpirationThreshold = -2147024809;
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v100,
        L"CheckResourceValidation",
        v101,
        L"No URIs available to use",
        -2147024809);
      goto LABEL_181;
    }
    v83 = std::operator+<unsigned short>(v128, v127, v42 + 64);
    std::wstring::operator=(v120, v83);
    std::wstring::_Tidy_deallocate(v128);
LABEL_136:
    v84 = v42 + 80;
    if ( *((_QWORD *)v42 + 23) > 7u )
      v84 = *(wchar_t **)v84;
    v85 = (const unsigned __int16 *)v120;
    if ( v121 > 7 )
      v85 = v120[0];
    if ( (int)CheckValidationURIValues((struct DCConfigManagerWrap *)&v111, v85, v84) < 0 )
      goto LABEL_156;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      v87 = v120;
      if ( v121 > 7 )
        LODWORD(v87) = v120[0];
      McTemplateU0zzd_EventWriteTransfer(
        v86,
        (unsigned int)OrchestratorGenericInformation,
        (unsigned int)L"CheckResourceValidation:Found Resource InProgress and skip refresh",
        (_DWORD)v87,
        0);
    }
    VariantClear(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 2;
    v88 = (const unsigned __int16 *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v88 = *(const unsigned __int16 **)v88;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v89 = (const unsigned __int16 *)a2;
    else
      v89 = *(const unsigned __int16 **)a2;
    DriftControlCertificateExpirationThreshold = DeclaredConfigurationStore_WriteResultData(
                                                   (struct DeclaredConfigurationScopeData *)a1,
                                                   v89,
                                                   v88,
                                                   0,
                                                   v116,
                                                   0,
                                                   L"state",
                                                   &pvarg);
    if ( DriftControlCertificateExpirationThreshold < 0 )
    {
      v104 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v104,
        L"CheckResourceValidation",
        L"DeclaredConfigurationStore_WriteResultData",
        L"update doc state",
        DriftControlCertificateExpirationThreshold);
      v99 = 14198;
      goto LABEL_180;
    }
    if ( (byte_180189FC1 & 4) != 0 )
    {
      v91 = v120;
      if ( v121 > 7 )
        v91 = (unsigned __int16 **)v120[0];
      McTemplateU0zz_EventWriteTransfer(v90, DcSvcResourceAlreadyInstalled, v91, L"State:InProgress");
    }
    *v69 = 1;
LABEL_156:
    v42 += 96;
    if ( v42 == *(wchar_t **)&v126.vt )
      goto LABEL_157;
  }
  if ( !v44 )
  {
    v100 = CDeclaredConfigurationLogger::GetLogger();
    v101 = L"Check Success";
    goto LABEL_174;
  }
  v45 = std::operator+<unsigned short>(v128, v127, v42);
  std::wstring::operator=(v120, v45);
  std::wstring::_Tidy_deallocate(v128);
  v46 = v42 + 16;
  if ( *((_QWORD *)v42 + 7) > 7u )
    v46 = *(wchar_t **)v46;
  v47 = (const unsigned __int16 *)v120;
  if ( v121 > 7 )
    v47 = v120[0];
  if ( (int)CheckValidationURIValues((struct DCConfigManagerWrap *)&v111, v47, v46) < 0 )
  {
LABEL_104:
    v69 = v110;
    goto LABEL_105;
  }
  v48 = (const wchar_t *)Str;
  if ( v123 > 7 )
    v48 = Str[0];
  if ( !wcsstr(v48, L"clientcertificateinstall") )
  {
LABEL_72:
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      v63 = v120;
      if ( v121 > 7 )
        LODWORD(v63) = v120[0];
      McTemplateU0zzd_EventWriteTransfer(
        v49,
        (unsigned int)OrchestratorGenericInformation,
        (unsigned int)L"CheckResourceValidation:Found Existing Resource and skip refresh",
        (_DWORD)v63,
        0);
    }
    VariantClear(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 60;
    v64 = (const unsigned __int16 *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v64 = *(const unsigned __int16 **)v64;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v65 = (const unsigned __int16 *)a2;
    else
      v65 = *(const unsigned __int16 **)a2;
    DriftControlCertificateExpirationThreshold = DeclaredConfigurationStore_WriteResultData(
                                                   (struct DeclaredConfigurationScopeData *)a1,
                                                   v65,
                                                   v64,
                                                   0,
                                                   v116,
                                                   0,
                                                   L"state",
                                                   &pvarg);
    if ( DriftControlCertificateExpirationThreshold < 0 )
    {
      v98 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v98,
        L"CheckResourceValidation",
        L"DeclaredConfigurationStore_WriteResultData",
        L"update doc state",
        DriftControlCertificateExpirationThreshold);
      v99 = 14042;
      goto LABEL_180;
    }
    v43 = 1;
    if ( (byte_180189FC1 & 4) == 0 )
      goto LABEL_87;
    v67 = L"State:Complete";
    goto LABEL_84;
  }
  std::wstring::wstring((__int64)Src, v120);
  if ( *((_QWORD *)v42 + 3) <= 7u )
    LOWORD(v53) = (_WORD)v42;
  else
    v53 = *(_QWORD *)v42;
  v54 = (const wchar_t *)o(v53, v50, v51, v52, v106, *(long double *)&v107);
  v55 = wcsstr(v54, L"scep");
  v56 = v55 != 0 ? 14LL : 10LL;
  v57 = L"certthumbprint";
  if ( !v55 )
    v57 = L"thumbprint";
  v58 = std::wstring::find(Src, L"status", 0);
  std::wstring::_Replace<unsigned short>(Src, v58, 6u, (char *)v57, v56);
  v59 = (char *)a2 + 32;
  if ( *((_QWORD *)a2 + 7) > 7u )
    v59 = *(char **)v34;
  v60 = (unsigned int)_o__wcsicmp(L"User", v59) == 0;
  v115 = 0;
  DriftControlCertificateExpirationThreshold = DeclaredConfigurationStore_GetDriftControlCertificateExpirationThreshold(
                                                 *a1,
                                                 0,
                                                 &v115);
  if ( DriftControlCertificateExpirationThreshold < 0 )
  {
    v92 = CDeclaredConfigurationLogger::GetLogger();
    v93 = L"DeclaredConfigurationStore_GetDriftControlCertificateExpirationThreshold";
LABEL_159:
    v94 = (const unsigned __int16 *)Src;
    if ( v125 > 7 )
      v94 = Src[0];
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v92,
      L"CheckResourceValidation",
      v93,
      v94,
      DriftControlCertificateExpirationThreshold);
    std::wstring::_Tidy_deallocate(Src);
LABEL_181:
    std::vector<ResourceValidationUrisAndValues>::_Tidy(&v118);
    goto LABEL_182;
  }
  v61 = (const unsigned __int16 *)Src;
  if ( v125 > 7 )
    v61 = Src[0];
  v62 = CheckCertificateExpiration((struct DCConfigManagerWrap *)&v111, v61, v60, v115);
  DriftControlCertificateExpirationThreshold = v62;
  if ( v62 != -2147024894 && v62 != -2146762495 )
  {
    if ( v62 < 0 )
    {
      v92 = CDeclaredConfigurationLogger::GetLogger();
      v93 = L"CheckCertificateExpiration";
      goto LABEL_159;
    }
    std::wstring::_Tidy_deallocate(Src);
    goto LABEL_72;
  }
  v95 = CDeclaredConfigurationLogger::GetLogger();
  v96 = (const unsigned __int16 *)Src;
  if ( v125 > 7 )
    v96 = Src[0];
  v97 = (const unsigned __int16 *)((char *)a2 + 96);
  if ( *((_QWORD *)a2 + 15) > 7u )
    v97 = *(const unsigned __int16 **)v97;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(struct DCDocument **)a2;
  if ( *((_QWORD *)v34 + 3) > 7u )
    v34 = *(char **)v34;
  CDeclaredConfigurationLogger::LogOrchestratorDriftControlDriftDetected(
    v95,
    *a1,
    (const unsigned __int16 *)v34,
    (const unsigned __int16 *)a2,
    v97,
    v96,
    DriftControlCertificateExpirationThreshold);
  *v110 = 0;
  std::wstring::_Tidy_deallocate(Src);
  std::vector<ResourceValidationUrisAndValues>::_Tidy(&v118);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
  VariantClear(&v114);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v109);
  DriftControlCertificateExpirationThreshold = 0;
LABEL_25:
  std::wstring::_Tidy_deallocate(v120);
  std::wstring::_Tidy_deallocate(v127);
  std::wstring::_Tidy_deallocate(Str);
  VariantClear(&pvarg);
  DCConfigManagerWrap::~DCConfigManagerWrap((DCConfigManagerWrap *)&v111);
  return (unsigned int)DriftControlCertificateExpirationThreshold;
}

```

## disassembly

```asm
0x18005c05c  push    rbx
0x18005c05e  push    rsi
0x18005c05f  push    rdi
0x18005c060  push    r12
0x18005c062  push    r13
0x18005c064  push    r14
0x18005c066  push    r15
0x18005c068  sub     rsp, 1C0h
0x18005c06f  mov     rax, cs:__security_cookie
0x18005c076  xor     rax, rsp
0x18005c079  mov     [rsp+1F8h+var_48], rax
0x18005c081  mov     [rsp+1F8h+var_158], r9
0x18005c089  mov     rdi, r8
0x18005c08c  mov     rsi, rdx
0x18005c08f  mov     r13, rcx
0x18005c092  mov     rbx, [rsp+1F8h+arg_20]
0x18005c09a  mov     [rsp+1F8h+var_1A8], rbx
0x18005c09f  xor     r14d, r14d
0x18005c0a2  mov     [rsp+1F8h+var_1A0], r14w
0x18005c0a8  mov     [rsp+1F8h+var_198], r14
0x18005c0ad  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x18005c0b2  call    cs:__imp_VariantInit
0x18005c0b8  nop
0x18005c0b9  lea     rcx, [rsp+1F8h+Str]
0x18005c0c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005c0c6  nop
0x18005c0c7  lea     rcx, [rsp+1F8h+var_A8]
0x18005c0cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005c0d4  nop
0x18005c0d5  lea     rcx, [rsp+1F8h+var_130]
0x18005c0dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005c0e2  nop
0x18005c0e3  lea     rax, [rdi+58h]
0x18005c0e7  cmp     qword ptr [rax+18h], 7
0x18005c0ec  jbe     short loc_18005C0F1
0x18005c0ee  mov     rax, [rax]
0x18005c0f1  lea     rdx, [rax+4]
0x18005c0f5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005c0f9  inc     r8
0x18005c0fc  cmp     [rdx+r8*2], r14w
0x18005c101  jnz     short loc_18005C0F9
0x18005c103  lea     rcx, [rsp+1F8h+Str]
0x18005c10b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005c110  lea     rcx, [rsp+1F8h+Str]
0x18005c118  cmp     [rsp+1F8h+var_F8], 7
0x18005c121  cmova   rcx, [rsp+1F8h+Str]; unsigned __int16 *
0x18005c12a  call    ?DCDoesCspNeedPrefix@@YAHPEBG@Z; DCDoesCspNeedPrefix(ushort const *)
0x18005c12f  lea     rdx, asc_180142BE8; "./"
0x18005c136  test    eax, eax
0x18005c138  jnz     short loc_18005C197
0x18005c13a  lea     r8, [rsp+1F8h+Str]
0x18005c142  lea     rcx, [rsp+1F8h+var_68]
0x18005c14a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18005c14f  nop
0x18005c150  lea     r8, asc_18013EB9C; "/"
0x18005c157  mov     rdx, rax
0x18005c15a  lea     rcx, [rsp+1F8h+Src]
0x18005c162  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18005c167  mov     rdx, rax
0x18005c16a  lea     rcx, [rsp+1F8h+var_A8]
0x18005c172  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005c177  lea     rcx, [rsp+1F8h+Src]
0x18005c17f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c184  nop
0x18005c185  lea     rcx, [rsp+1F8h+var_68]
0x18005c18d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c192  jmp     loc_18005C252
0x18005c197  lea     rbx, [rsp+1F8h+Str]
0x18005c19f  cmp     [rsp+1F8h+var_F8], 7
0x18005c1a8  cmova   rbx, [rsp+1F8h+Str]
0x18005c1b1  lea     r8, [rsi+20h]
0x18005c1b5  lea     rcx, [rsp+1F8h+var_88]
0x18005c1bd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18005c1c2  nop
0x18005c1c3  lea     r8, asc_18013EB9C; "/"
0x18005c1ca  mov     rdx, rax
0x18005c1cd  lea     rcx, [rsp+1F8h+var_C8]
0x18005c1d5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18005c1da  nop
0x18005c1db  mov     r8, rbx
0x18005c1de  mov     rdx, rax
0x18005c1e1  lea     rcx, [rsp+1F8h+var_68]
0x18005c1e9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18005c1ee  nop
0x18005c1ef  lea     r8, asc_18013EB9C; "/"
0x18005c1f6  mov     rdx, rax
0x18005c1f9  lea     rcx, [rsp+1F8h+Src]
0x18005c201  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18005c206  mov     rdx, rax
0x18005c209  lea     rcx, [rsp+1F8h+var_A8]
0x18005c211  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005c216  lea     rcx, [rsp+1F8h+Src]
0x18005c21e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c223  nop
0x18005c224  lea     rcx, [rsp+1F8h+var_68]
0x18005c22c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c231  nop
0x18005c232  lea     rcx, [rsp+1F8h+var_C8]
0x18005c23a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c23f  nop
0x18005c240  lea     rcx, [rsp+1F8h+var_88]
0x18005c248  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c24d  mov     rbx, [rsp+1F8h+var_1A8]
0x18005c252  lea     r9, [rsp+1F8h+Str]
0x18005c25a  cmp     [rsp+1F8h+var_F8], 7
0x18005c263  cmova   r9, [rsp+1F8h+Str]
0x18005c26c  lea     rdx, [rsp+1F8h+var_C8]
0x18005c274  lea     rcx, [rsp+1F8h+Str]
0x18005c27c  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18005c281  lea     rdx, [rsp+1F8h+Str]
0x18005c289  cmp     [rsp+1F8h+var_F8], 7
0x18005c292  cmova   rdx, [rsp+1F8h+Str]
0x18005c29b  mov     rcx, cs:__imp__o_towlower
0x18005c2a2  mov     [rsp+1F8h+var_1D8], rcx
0x18005c2a7  mov     r8, [rax]
0x18005c2aa  lea     rcx, [rsp+1F8h+var_150]
0x18005c2b2  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18005c2b7  nop
0x18005c2b8  lea     r15, aCheckresourcev_1; "CheckResourceValidation"
0x18005c2bf  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x18005c2c6  jz      short loc_18005C2F6
0x18005c2c8  lea     r9, [rsp+1F8h+var_A8]
0x18005c2d0  cmp     [rsp+1F8h+var_90], 7
0x18005c2d9  cmova   r9, [rsp+1F8h+var_A8]
0x18005c2e2  mov     dword ptr [rsp+1F8h+var_1D8], r14d; int
0x18005c2e7  mov     r8, r15
0x18005c2ea  lea     rdx, OrchestratorGenericInformation
0x18005c2f1  call    McTemplateU0zzd_EventWriteTransfer
0x18005c2f6  mov     [rbx], r14b
0x18005c2f9  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18005c2fe  call    ?Initialize@DCConfigManagerWrap@@QEAAJXZ; DCConfigManagerWrap::Initialize(void)
0x18005c303  mov     ebx, eax
0x18005c305  test    eax, eax
0x18005c307  jns     loc_18005C39F
0x18005c30d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18005c312  mov     dword ptr [rsp+1F8h+var_1D8], ebx; int
0x18005c316  lea     r9, word_180142E98; unsigned __int16 *
0x18005c31d  lea     r8, aConfigmanagerI_0; "configManager.Initialize"
0x18005c324  mov     rdx, r15; unsigned __int16 *
0x18005c327  mov     rcx, rax; this
0x18005c32a  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18005c32f  lea     rax, aFailedToInitia; "Failed to initialize ConfigManager"
0x18005c336  mov     edx, 3577h; void *
0x18005c33b  mov     [rsp+1F8h+var_1D8], rax; int
0x18005c340  mov     r9d, ebx; char *
0x18005c343  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005c34a  mov     rcx, [rsp+1F8h]; this
0x18005c352  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005c357  nop
0x18005c358  lea     rcx, [rsp+1F8h+var_130]
0x18005c360  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c365  nop
0x18005c366  lea     rcx, [rsp+1F8h+var_A8]
0x18005c36e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c373  nop
0x18005c374  lea     rcx, [rsp+1F8h+Str]
0x18005c37c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c381  nop
0x18005c382  lea     rcx, [rsp+1F8h+pvarg]; pvarg
0x18005c387  call    cs:__imp_VariantClear
0x18005c38d  nop
0x18005c38e  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18005c393  call    ??1DCConfigManagerWrap@@QEAA@XZ; DCConfigManagerWrap::~DCConfigManagerWrap(void)
0x18005c398  mov     eax, ebx
0x18005c39a  jmp     loc_18005D164
0x18005c39f  mov     rdx, [r13+0]; unsigned __int16 *
0x18005c3a3  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18005c3a8  call    ?SetAccountId@DCConfigManagerWrap@@QEBAJPEBG@Z; DCConfigManagerWrap::SetAccountId(ushort const *)
0x18005c3ad  mov     ebx, eax
0x18005c3af  test    eax, eax
0x18005c3b1  jns     short loc_18005C3E6
0x18005c3b3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18005c3b8  mov     dword ptr [rsp+1F8h+var_1D8], ebx; int
0x18005c3bc  lea     r9, word_180142E98; unsigned __int16 *
0x18005c3c3  lea     r8, aConfigmanagerS_4; "configManager.SetAccountId"
0x18005c3ca  mov     rdx, r15; unsigned __int16 *
0x18005c3cd  mov     rcx, rax; this
0x18005c3d0  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18005c3d5  lea     rax, aFailedToSetAcc; "Failed to set AccountId for ConfigManag"...
0x18005c3dc  mov     edx, 3581h
0x18005c3e1  jmp     loc_18005C33B
0x18005c3e6  lea     r12, [rsi+20h]
0x18005c3ea  cmp     qword ptr [r12+18h], 7
0x18005c3f0  jbe     short loc_18005C3F8
0x18005c3f2  mov     rdx, [r12]
0x18005c3f6  jmp     short loc_18005C3FB
0x18005c3f8  mov     rdx, r12
0x18005c3fb  lea     rcx, aUser_4; "User"
0x18005c402  call    cs:__imp__o__wcsicmp
0x18005c408  test    eax, eax
0x18005c40a  jnz     loc_18005C513
0x18005c410  mov     rcx, [r13+8]
0x18005c414  test    rcx, rcx
0x18005c417  jz      loc_18005C5FF
0x18005c41d  cmp     r14w, [rcx]
0x18005c421  jz      loc_18005C5FF
0x18005c427  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x18005c42e  lea     rcx, [rsp+1F8h+var_150]
0x18005c436  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005c43b  nop
0x18005c43c  mov     rdx, [r13+8]; unsigned __int16 *
0x18005c440  lea     rcx, [rsp+1F8h+var_68]; this
0x18005c448  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18005c44d  nop
0x18005c44e  movups  xmm0, xmmword ptr [rsp+1F8h+var_68]
0x18005c456  movsd   xmm1, qword ptr [rsp+1F8h+var_68+10h]
0x18005c45f  movaps  xmmword ptr [rsp+1F8h+var_C8], xmm0
0x18005c467  movsd   qword ptr [rsp+1F8h+var_C8+10h], xmm1
0x18005c470  lea     r8, [rsp+1F8h+var_C8]; struct tagVARIANT
0x18005c478  mov     rdx, [rsp+1F8h+var_150]; unsigned __int16 *
0x18005c480  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18005c485  call    ?SetSessionVariable@DCConfigManagerWrap@@QEBAJPEAGUtagVARIANT@@@Z; DCConfigManagerWrap::SetSessionVariable(ushort *,tagVARIANT)
0x18005c48a  mov     ebx, eax
0x18005c48c  test    eax, eax
0x18005c48e  jns     short loc_18005C4F7
0x18005c490  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18005c495  mov     dword ptr [rsp+1F8h+var_1D8], ebx; int
0x18005c499  lea     r9, aTargetuser; "targetUser"
0x18005c4a0  lea     r8, aConfigmanagerS_0; "configManager.SetSessionVariable"
0x18005c4a7  mov     rdx, r15; unsigned __int16 *
0x18005c4aa  mov     rcx, rax; this
0x18005c4ad  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18005c4b2  mov     rcx, [rsp+1F8h]; this
0x18005c4ba  lea     rax, aFailedToSetSet; "Failed to set SetSessionVariable for co"...
0x18005c4c1  mov     [rsp+1F8h+var_1D8], rax; int
0x18005c4c6  mov     r9d, ebx; char *
0x18005c4c9  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005c4d0  mov     edx, 3594h; void *
0x18005c4d5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005c4da  nop
0x18005c4db  lea     rcx, [rsp+1F8h+var_68]; pvarg
0x18005c4e3  call    cs:__imp_VariantClear
0x18005c4e9  nop
0x18005c4ea  lea     rcx, [rsp+1F8h+var_150]
0x18005c4f2  jmp     loc_18005D115
0x18005c4f7  lea     rcx, [rsp+1F8h+var_68]; pvarg
0x18005c4ff  call    cs:__imp_VariantClear
0x18005c505  nop
0x18005c506  lea     rcx, [rsp+1F8h+var_150]
0x18005c50e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c513  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x18005c51a  lea     rcx, [rsp+1F8h+var_1B0]
0x18005c51f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005c524  nop
0x18005c525  lea     rcx, [rsp+1F8h+var_178]; pvarg
0x18005c52d  call    cs:__imp_VariantInit
0x18005c533  nop
0x18005c534  mov     [rsp+1F8h+psz], r14
0x18005c539  xorps   xmm0, xmm0
0x18005c53c  movups  xmmword ptr [rsp+1F8h+var_C8], xmm0
0x18005c544  lea     rdx, [rsp+1F8h+var_C8]; struct _GUID *
0x18005c54c  mov     rcx, [r13+0]; unsigned __int16 *
0x18005c550  call    ?DCGetGuidFromEnrollmentId@@YAJPEBGPEAU_GUID@@@Z; DCGetGuidFromEnrollmentId(ushort const *,_GUID *)
0x18005c555  test    eax, eax
0x18005c557  js      loc_18005C615
0x18005c55d  xor     edx, edx
0x18005c55f  lea     rcx, [rsp+1F8h+psz]
0x18005c564  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005c569  movaps  xmm0, xmmword ptr [rsp+1F8h+var_C8]
0x18005c571  movdqa  xmmword ptr [rsp+1F8h+var_C8], xmm0
0x18005c57a  lea     rdx, [rsp+1F8h+psz]
0x18005c57f  lea     rcx, [rsp+1F8h+var_C8]
0x18005c587  call    cs:__imp_GetProviderID
0x18005c58d  test    eax, eax
0x18005c58f  js      loc_18005C615
0x18005c595  mov     rcx, [rsp+1F8h+psz]; psz
0x18005c59a  call    cs:__imp_SysAllocString
0x18005c5a0  mov     qword ptr [rsp+1F8h+var_178+8], rax
0x18005c5a8  test    rax, rax
0x18005c5ab  jnz     loc_18005C636
0x18005c5b1  mov     edx, 35A2h; void *
0x18005c5b6  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005c5bd  mov     r9d, 8007000Eh; char *
0x18005c5c3  mov     rcx, [rsp+1F8h]; this
0x18005c5cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5d0  nop
0x18005c5d1  lea     rcx, [rsp+1F8h+psz]
0x18005c5d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c5db  nop
0x18005c5dc  lea     rcx, [rsp+1F8h+var_178]; pvarg
0x18005c5e4  call    cs:__imp_VariantClear
0x18005c5ea  nop
0x18005c5eb  lea     rcx, [rsp+1F8h+var_1B0]
0x18005c5f0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005c5f5  mov     ebx, 8007000Eh
0x18005c5fa  jmp     loc_18005C358
0x18005c5ff  lea     rax, aFailedToFindVa; "Failed to find valid UserSid"
0x18005c606  mov     ebx, 80070057h
0x18005c60b  mov     edx, 3588h
0x18005c610  jmp     loc_18005C33B
0x18005c615  lea     rcx, aMicrosoftDevic; "Microsoft Device Management"
0x18005c61c  call    cs:__imp_SysAllocString
0x18005c622  mov     qword ptr [rsp+1F8h+var_178+8], rax
0x18005c62a  test    rax, rax
0x18005c62d  jnz     short loc_18005C636
0x18005c62f  mov     edx, 35A8h
0x18005c634  jmp     short loc_18005C5B6
0x18005c636  mov     eax, 8
0x18005c63b  mov     word ptr [rsp+1F8h+var_178], ax
0x18005c643  movups  xmm0, xmmword ptr [rsp+1F8h+var_178]
  ... truncated ...
```
