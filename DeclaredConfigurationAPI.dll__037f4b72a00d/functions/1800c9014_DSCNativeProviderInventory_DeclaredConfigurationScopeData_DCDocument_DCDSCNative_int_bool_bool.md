# DSCNativeProviderInventory(DeclaredConfigurationScopeData *,DCDocument *,DCDSCNative *,int,bool *,bool *)

- ea: `0x1800c9014`
- end: `0x1800c9f30`
- name: `?DSCNativeProviderInventory@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEAVDCDSCNative@@HPEA_N3@Z`
- size: `3868`
- prototype: `__int64 __usercall@<rax>(struct DeclaredConfigurationScopeData *@<rcx>, struct DCDocument *@<rdx>, struct DCDSCNative *@<r8>, int@<r9d>, bool *, bool *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180060dec`

## callees

- `0x18000b9e0`
- `0x180011fe0`
- `0x180014348`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180019208`
- `0x1800192b4`
- `0x18001a048`
- `0x18001b488`
- `0x18001bdd0`
- `0x18001c488`
- `0x18001d0b0`
- `0x18001d4a8`
- `0x18001dea8`
- `0x18001def8`
- `0x18001df78`
- `0x18004abf8`
- `0x18005fb3c`
- `0x18005fde0`
- `0x180086c10`
- `0x180090c18`
- `0x1800c6040`
- `0x1800c9014`
- `0x1800ca2d8`
- `0x1800f5c8c`
- `0x1800f718c`
- `0x1800f72c8`
- `0x1800f83d0`
- `0x1800f9d70`
- `0x1800f9e64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c92de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c93ee`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c92de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c93ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c939d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c939d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c9393`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c9393`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c9306`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c9306`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9a52`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9b99`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9c34`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9a52`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9b99`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9c34`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c9413`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c9413`
- `OLEAUT32!__imp_VariantInit` at `0x1800c9072`
- `OLEAUT32!__imp_VariantInit` at `0x1800c9b7d`
- `OLEAUT32!__imp_VariantInit` at `0x1800c9072`
- `OLEAUT32!__imp_VariantInit` at `0x1800c9b7d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c90a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9121`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9857`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9901`
- `OLEAUT32!__imp_VariantClear` at `0x1800c998e`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9a2c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9c15`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9cb0`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9d3f`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9dcc`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9e1e`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9e5b`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9f02`
- `OLEAUT32!__imp_VariantClear` at `0x1800c90a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9121`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9857`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9901`
- `OLEAUT32!__imp_VariantClear` at `0x1800c998e`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9a2c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9c15`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9cb0`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9d3f`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9dcc`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9e1e`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9e5b`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9f02`

## string_xrefs

- `0x1800c91a4`: `DeclaredConfigurationStore_WriteResultData`
- `0x1800c919d`: `Update doc State to DCCSPURIState::ConfigInprogress`
- `0x1800c95a0`: `invalid configrequest type`
- `0x1800c98f0`: `DeclaredConfigurationStore_WriteResultData: udpate doc state`
- `0x1800c9a06`: `DeclaredConfigurationStore_WriteResultData: udpate doc hresult`
- `0x1800c997d`: `DeclaredConfigurationStore_WriteResultData: udpate doc httpstatus`
- `0x1800c9ac8`: `DSCNativeProviderConfiguration`
- `0x1800c932a`: `WellKnownSidFailure`
- `0x1800c9335`: `DeclaredConfigurationStore_UserSidConfiguration`
- `0x1800c94cf`: `DeclaredConfigurationStore_UserSidConfiguration`
- `0x1800c93b7`: `ConvertSidToStringSidFailure`
- `0x1800c953e`: `NoUserSidKeyFound`
- `0x1800c94c8`: `SidPopulatedSuccessfully`
- `0x1800c9ab9`: `DeclaredConfigurationStore_WriteResultData: udpate doc error message`
- `0x1800c9b12`: `DeclaredConfigurationStore_DeleteResultData: udpate doc error message`
- `0x1800c9e9e`: `DeclaredConfigurationStore_WriteResultData: StringCchPrintf failure`
- `0x1800c9e84`: `DeclaredConfigurationStore_WriteResultData: udpate Key Value`
- `0x1800c9e76`: `DeclaredConfigurationStore_WriteResultData: udpate Key Name`
- `0x1800c9e68`: `DeclaredConfigurationStore_WriteResultData: udpate Key State`
- `0x1800c9e30`: `DeclaredConfigurationStore_WriteResultData: udpate Key Reg Type`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DSCNativeProviderInventory(
        const unsigned __int16 **a1,
        struct DCDocument *a2,
        struct DCDSCNative *a3,
        unsigned int a4,
        bool *a5,
        bool *a6)
{
  signed int v10; // ebx
  __int64 v12; // rax
  __int64 v13; // rax
  const unsigned __int16 **v14; // r15
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // rdx
  struct DeclaredConfigurationScopeData *v17; // rcx
  CDeclaredConfigurationLogger *Logger; // rax
  CDeclaredConfigurationLogger *v19; // rax
  const unsigned __int16 *v20; // r13
  __int64 v21; // rdi
  unsigned __int16 *v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // rax
  char *v25; // rbx
  char *v26; // rcx
  signed int LastError; // eax
  CDeclaredConfigurationLogger *v28; // rax
  const unsigned __int16 *v29; // r9
  signed int v30; // eax
  __int64 v31; // rax
  OLECHAR *v32; // rcx
  UINT v33; // eax
  __int64 v34; // rbx
  struct DCDSCNative *v35; // rbx
  _QWORD *v36; // rcx
  CDeclaredConfigurationLogger *v37; // rax
  CDeclaredConfigurationLogger *v38; // rax
  CDeclaredConfigurationLogger *v39; // r10
  const unsigned __int16 *v40; // rcx
  const unsigned __int16 *v41; // r13
  const unsigned __int16 *v42; // rax
  const unsigned __int16 *v43; // r8
  const unsigned __int16 *v44; // rdx
  int v45; // esi
  int v46; // edi
  int v47; // ebx
  int v48; // eax
  int v49; // edi
  struct DCDSCNative *v50; // rsi
  CDeclaredConfigurationLogger *v51; // r10
  const unsigned __int16 *v52; // r9
  const unsigned __int16 *v53; // rcx
  const unsigned __int16 *v54; // rax
  const unsigned __int16 *v55; // r8
  const unsigned __int16 *v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  CDeclaredConfigurationLogger *v60; // rax
  unsigned __int16 *v61; // r9
  const unsigned __int16 *v62; // r8
  const unsigned __int16 *v63; // rdx
  LONG v64; // r13d
  const unsigned __int16 *v65; // r8
  const unsigned __int16 *v66; // rdx
  const unsigned __int16 *v67; // r8
  const unsigned __int16 *v68; // rdx
  const unsigned __int16 *v69; // r8
  const unsigned __int16 *v70; // rdx
  int v71; // r9d
  const OLECHAR *v72; // rcx
  const unsigned __int16 *v73; // r8
  const unsigned __int16 *v74; // rdx
  const unsigned __int16 *v75; // r8
  __int64 v76; // rdx
  unsigned int v77; // r13d
  unsigned __int16 *v78; // rbx
  int v79; // edi
  const OLECHAR *v80; // rcx
  const unsigned __int16 *v81; // r8
  const unsigned __int16 *v82; // rdx
  const OLECHAR *v83; // rcx
  const unsigned __int16 *v84; // r8
  const unsigned __int16 *v85; // rdx
  const unsigned __int16 *v86; // r8
  const unsigned __int16 *v87; // rdx
  const unsigned __int16 *v88; // r8
  const unsigned __int16 *v89; // rdx
  CDeclaredConfigurationLogger *v90; // rax
  const unsigned __int16 *v91; // r8
  CDeclaredConfigurationLogger *v92; // rax
  int v93; // [rsp+20h] [rbp-328h]
  const WCHAR *lpSubKey; // [rsp+28h] [rbp-320h]
  char v95; // [rsp+50h] [rbp-2F8h]
  __int64 v96; // [rsp+58h] [rbp-2F0h] BYREF
  DWORD cbSid; // [rsp+60h] [rbp-2E8h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-2E0h] BYREF
  _BYTE *v99; // [rsp+80h] [rbp-2C8h] BYREF
  VARIANTARG v100; // [rsp+88h] [rbp-2C0h] BYREF
  struct DCDSCNative *v101; // [rsp+A8h] [rbp-2A0h]
  unsigned __int16 **v102; // [rsp+B0h] [rbp-298h]
  LPWSTR StringSid; // [rsp+B8h] [rbp-290h] BYREF
  bool *v104; // [rsp+C0h] [rbp-288h]
  bool *v105; // [rsp+C8h] [rbp-280h]
  std::_Ref_count_base *v106[2]; // [rsp+D0h] [rbp-278h] BYREF
  _BYTE v107[32]; // [rsp+E0h] [rbp-268h] BYREF
  _BYTE v108[32]; // [rsp+100h] [rbp-248h] BYREF
  _BYTE v109[32]; // [rsp+120h] [rbp-228h] BYREF
  _BYTE v110[32]; // [rsp+140h] [rbp-208h] BYREF
  unsigned __int16 *v111[4]; // [rsp+160h] [rbp-1E8h] BYREF
  unsigned __int16 v112[16]; // [rsp+180h] [rbp-1C8h] BYREF
  _BYTE v113[32]; // [rsp+1A0h] [rbp-1A8h] BYREF
  _BYTE v114[112]; // [rsp+1C0h] [rbp-188h] BYREF
  _BYTE v115[16]; // [rsp+230h] [rbp-118h] BYREF
  __int64 v116; // [rsp+240h] [rbp-108h]
  unsigned __int16 v117[16]; // [rsp+290h] [rbp-B8h] BYREF
  _BYTE pSid[80]; // [rsp+2B0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  v101 = a3;
  v104 = a5;
  v105 = a6;
  VariantInit(&pvarg);
  v117[0] = 0;
  v10 = StringCchPrintfW(v117, 0xFu, L"CSP%d", a4);
  if ( v10 < 0 )
    goto LABEL_2;
  std::wstring::wstring((__int64)v113);
  try
  {
    v12 = std::wstring::wstring((__int64)v112, (__int64)L"cooked\\");
    v13 = std::operator+<unsigned short>(v111, v12, v117);
    std::wstring::operator=(v113, v13);
    std::wstring::_Tidy_deallocate(v111);
    std::wstring::_Tidy_deallocate(v112);
    VariantClear(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 2;
    v14 = (const unsigned __int16 **)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) <= 7u )
      v15 = (const unsigned __int16 *)((char *)a2 + 96);
    else
      v15 = *v14;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v16 = (const unsigned __int16 *)a2;
    else
      v16 = *(const unsigned __int16 **)a2;
    v17 = (struct DeclaredConfigurationScopeData *)a1;
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7FD,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
      (const char *)0x8007000ELL,
      v93);
    std::wstring::_Tidy_deallocate(v113);
    VariantClear(&pvarg);
    return 2147942414LL;
  }
  v10 = DeclaredConfigurationStore_WriteResultData(v17, v16, v15, 0, v117, 0, L"state", &pvarg);
  if ( v10 < 0 )
  {
    Logger = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      Logger,
      L"DSCNativeProviderInventory",
      L"DeclaredConfigurationStore_WriteResultData",
      L"Update doc State to DCCSPURIState::ConfigInprogress",
      v10);
LABEL_183:
    std::wstring::_Tidy_deallocate(v113);
LABEL_2:
    VariantClear(&pvarg);
    return (unsigned int)v10;
  }
  cbSid = 0;
  LODWORD(v99) = 63;
  if ( (int)DCIsValidEnrollment((RPC_WSTR)*a1, (int *)&cbSid, (enum EnrollmentStateTag *)&v99) >= 0
    && (!cbSid || (_DWORD)v99 == 4) )
  {
    v19 = CDeclaredConfigurationLogger::GetLogger();
    v10 = -2147418113;
    CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(v19, *a1, -2147418113);
    goto LABEL_183;
  }
  v96 = 0;
  DCNativeProviderOrchestration::DCNativeProviderOrchestration((DCNativeProviderOrchestration *)v114);
  v102 = v111;
  v20 = (const unsigned __int16 *)((char *)a3 + 80);
  v21 = std::wstring::wstring((__int64)v111, (_QWORD *)a3 + 10);
  StringSid = v112;
  v22 = (unsigned __int16 *)((char *)a3 + 48);
  v23 = std::wstring::wstring((__int64)v112, v22);
  v24 = std::wstring::wstring((__int64)&v100, (__int64)*a1);
  if ( (int)DCNativeProviderOrchestration::PopulateFromRegistry(v114, v24, v23, v21) >= 0 && v116 )
  {
    std::wstring::wstring((__int64)v111);
    v25 = (char *)a2 + 32;
    if ( *((_QWORD *)a2 + 7) <= 7u )
      v26 = (char *)a2 + 32;
    else
      v26 = *(char **)v25;
    if ( (unsigned int)_o__wcsicmp(v26, L"device") )
    {
      if ( *((_QWORD *)a2 + 7) > 7u )
        v25 = *(char **)v25;
      if ( (unsigned int)_o__wcsicmp(v25, L"user") )
      {
        std::wstring::_Tidy_deallocate(v111);
        DCNativeProviderOrchestration::~DCNativeProviderOrchestration((DCNativeProviderOrchestration *)v114);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v96);
        v10 = -2147418113;
        goto LABEL_183;
      }
      v32 = (OLECHAR *)a1[1];
      if ( !v32 || !*v32 )
      {
        v28 = CDeclaredConfigurationLogger::GetLogger();
        v10 = -2147024809;
        v29 = L"NoUserSidKeyFound";
LABEL_27:
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v28,
          L"DSCNativeProviderInventory",
          L"DeclaredConfigurationStore_UserSidConfiguration",
          v29,
          v10);
LABEL_28:
        std::wstring::_Tidy_deallocate(v111);
LABEL_29:
        DCNativeProviderOrchestration::~DCNativeProviderOrchestration((DCNativeProviderOrchestration *)v114);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v96);
        goto LABEL_183;
      }
      v33 = SysStringLen(v32);
      v31 = std::wstring::wstring(v112, a1[1], v33);
    }
    else
    {
      cbSid = 68;
      if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v28 = CDeclaredConfigurationLogger::GetLogger();
        v29 = L"WellKnownSidFailure";
        goto LABEL_27;
      }
      StringSid = 0;
      if ( !ConvertSidToStringSidW(pSid, &StringSid) )
      {
        v30 = GetLastError();
        v10 = v30;
        if ( v30 > 0 )
          v10 = (unsigned __int16)v30 | 0x80070000;
        v28 = CDeclaredConfigurationLogger::GetLogger();
        v29 = L"ConvertSidToStringSidFailure";
        goto LABEL_27;
      }
      v31 = std::wstring::wstring((__int64)v112, (__int64)StringSid);
    }
    std::wstring::operator=(v111, v31);
    std::wstring::_Tidy_deallocate(v112);
    std::make_shared<DCDSCNativeKeyValue,>(&v100);
    v34 = *(_QWORD *)&v100.vt;
    std::wstring::operator=(*(_QWORD *)&v100.vt + 32LL, v115);
    std::wstring::operator=(v34, v111);
    v35 = v101;
    v36 = (_QWORD *)*((_QWORD *)v101 + 3);
    if ( v36 == *((_QWORD **)v101 + 4) )
    {
      std::vector<std::shared_ptr<DCDSCNativeKeyValue>>::_Emplace_reallocate<std::shared_ptr<DCDSCNativeKeyValue> const &>(
        (char *)v101 + 16,
        *((_QWORD *)v101 + 3),
        &v100);
    }
    else
    {
      std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v36, &v100);
      *((_QWORD *)v35 + 3) += 16LL;
    }
    v37 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
      v37,
      L"DeclaredConfigurationStore_UserSidConfiguration",
      L"SidPopulatedSuccessfully",
      &word_180142E98);
    *(_OWORD *)v106 = 0;
    std::shared_ptr<DCURI>::operator=(&v100, v106);
    if ( v106[1] )
      std::_Ref_count_base::_Decref(v106[1]);
    if ( v100.llVal )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v100.llVal);
    std::wstring::_Tidy_deallocate(v111);
  }
  else
  {
    v35 = v101;
  }
  if ( *((_DWORD *)v35 + 39) != 4 )
  {
    v38 = CDeclaredConfigurationLogger::GetLogger();
    v10 = -2147418113;
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v38,
      L"DSCNativeProviderInventory",
      L"invalid configrequest type",
      &word_180142E98,
      -2147418113);
    goto LABEL_29;
  }
  v95 = 0;
  v39 = CDeclaredConfigurationLogger::GetLogger();
  if ( *((_QWORD *)v20 + 3) <= 7u )
    v40 = v20;
  else
    v40 = *(const unsigned __int16 **)v20;
  if ( *((_QWORD *)v22 + 3) > 7u )
    v22 = *(unsigned __int16 **)v22;
  v41 = (const unsigned __int16 *)((char *)a2 + 128);
  if ( *((_QWORD *)a2 + 19) <= 7u )
    v42 = (const unsigned __int16 *)((char *)a2 + 128);
  else
    v42 = *(const unsigned __int16 **)v41;
  if ( (unsigned __int64)v14[3] <= 7 )
    v43 = (const unsigned __int16 *)v14;
  else
    v43 = *v14;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v44 = (const unsigned __int16 *)a2;
  else
    v44 = *(const unsigned __int16 **)a2;
  CDeclaredConfigurationLogger::LogDeclaredConfigurationNativeDSCProviderBeginOperationEvent(
    v39,
    v44,
    v43,
    *a1,
    v42,
    L"get",
    v22,
    v40);
  std::wstring::wstring((__int64)v111);
  v102 = (unsigned __int16 **)v107;
  v45 = std::wstring::wstring((__int64)v107, (_QWORD *)v35 + 10);
  v99 = v108;
  v46 = std::wstring::wstring((__int64)v108, (_QWORD *)v35 + 6);
  v106[0] = (std::_Ref_count_base *)v109;
  v47 = std::wstring::wstring((__int64)v109, v14);
  v48 = std::wstring::wstring((__int64)v110, a2);
  v102 = (unsigned __int16 **)((char *)v101 + 16);
  v49 = InvokeGet(v48, v47, v46, v45, (__int64)v101 + 16, (__int64)v111);
  if ( v49 >= 0 )
  {
    v50 = v101;
  }
  else
  {
    *v104 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl)
      && v49 != -2147217406 )
    {
      *v105 = 1;
    }
    v95 = 1;
    v50 = v101;
    std::wstring::operator=((char *)v101 + 120, v111);
  }
  v51 = CDeclaredConfigurationLogger::GetLogger();
  v52 = (const unsigned __int16 *)v111;
  if ( v111[3] > (unsigned __int16 *)7 )
    v52 = v111[0];
  v53 = (const unsigned __int16 *)((char *)v50 + 80);
  if ( *((_QWORD *)v50 + 13) > 7u )
    v53 = *(const unsigned __int16 **)v53;
  v54 = (const unsigned __int16 *)((char *)v50 + 48);
  if ( *((_QWORD *)v50 + 9) > 7u )
    v54 = *(const unsigned __int16 **)v54;
  if ( *((_QWORD *)a2 + 19) > 7u )
    v41 = *(const unsigned __int16 **)v41;
  if ( (unsigned __int64)v14[3] <= 7 )
    v55 = (const unsigned __int16 *)v14;
  else
    v55 = *v14;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v56 = (const unsigned __int16 *)a2;
  else
    v56 = *(const unsigned __int16 **)a2;
  CDeclaredConfigurationLogger::LogDeclaredConfigurationNativeDSCProviderEndOperationEvent(
    v51,
    v56,
    v55,
    *a1,
    v41,
    L"get",
    v54,
    v53,
    v52,
    v49);
  LODWORD(v99) = 0;
  v10 = DCGetSyncmlHttpResponseCode((unsigned int)v49, v57, v58, v59, &v99);
  if ( v10 < 0 )
  {
    v60 = CDeclaredConfigurationLogger::GetLogger();
    v61 = (unsigned __int16 *)&word_180142E98;
    v62 = L"DCGetSyncmlHttpResponseCode";
LABEL_90:
    v63 = L"DSCNativeProviderInventory";
LABEL_91:
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(v60, v63, v62, v61, v10);
    goto LABEL_28;
  }
  v64 = (int)v99;
  *((_DWORD *)v50 + 38) = (_DWORD)v99;
  VariantClear(&pvarg);
  pvarg.vt = 3;
  if ( v49 == -2046820333 )
    pvarg.lVal = 200;
  else
    pvarg.lVal = (v95 != 0) + 80;
  if ( (unsigned __int64)v14[3] <= 7 )
    v65 = (const unsigned __int16 *)v14;
  else
    v65 = *v14;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v66 = (const unsigned __int16 *)a2;
  else
    v66 = *(const unsigned __int16 **)a2;
  v10 = DeclaredConfigurationStore_WriteResultData(
          (struct DeclaredConfigurationScopeData *)a1,
          v66,
          v65,
          0,
          v117,
          0,
          L"state",
          &pvarg);
  if ( v10 < 0 )
  {
    v60 = CDeclaredConfigurationLogger::GetLogger();
    v61 = v117;
    v62 = L"DeclaredConfigurationStore_WriteResultData: udpate doc state";
    goto LABEL_90;
  }
  VariantClear(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = v64;
  if ( (unsigned __int64)v14[3] <= 7 )
    v67 = (const unsigned __int16 *)v14;
  else
    v67 = *v14;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v68 = (const unsigned __int16 *)a2;
  else
    v68 = *(const unsigned __int16 **)a2;
  v10 = DeclaredConfigurationStore_WriteResultData(
          (struct DeclaredConfigurationScopeData *)a1,
          v68,
          v67,
          0,
          v117,
          0,
          L"httpstatus",
          &pvarg);
  if ( v10 < 0 )
  {
    v60 = CDeclaredConfigurationLogger::GetLogger();
    v61 = v117;
    v62 = L"DeclaredConfigurationStore_WriteResultData: udpate doc httpstatus";
    goto LABEL_90;
  }
  VariantClear(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = v49;
  if ( (unsigned __int64)v14[3] <= 7 )
    v69 = (const unsigned __int16 *)v14;
  else
    v69 = *v14;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v70 = (const unsigned __int16 *)a2;
  else
    v70 = *(const unsigned __int16 **)a2;
  v10 = DeclaredConfigurationStore_WriteResultData(
          (struct DeclaredConfigurationScopeData *)a1,
          v70,
          v69,
          0,
          v117,
          0,
          L"hresult",
          &pvarg);
  if ( v10 < 0 )
  {
    v60 = CDeclaredConfigurationLogger::GetLogger();
    v61 = v117;
    v62 = L"DeclaredConfigurationStore_WriteResultData: udpate doc hresult";
    goto LABEL_90;
  }
  if ( v49 < 0 && *((_QWORD *)v50 + 17) )
  {
    VariantClear(&pvarg);
    pvarg.vt = 8;
    v72 = (const OLECHAR *)((char *)v101 + 120);
    if ( *((_QWORD *)v101 + 18) > 7u )
      v72 = *(const OLECHAR **)v72;
    pvarg.llVal = (LONGLONG)SysAllocString(v72);
    if ( (unsigned __int64)v14[3] <= 7 )
      v73 = (const unsigned __int16 *)v14;
    else
      v73 = *v14;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v74 = (const unsigned __int16 *)a2;
    else
      v74 = *(const unsigned __int16 **)a2;
    v10 = DeclaredConfigurationStore_WriteResultData(
            (struct DeclaredConfigurationScopeData *)a1,
            v74,
            v73,
            0,
            v117,
            0,
            L"errorMessage",
            &pvarg);
    if ( v10 < 0 )
    {
      v60 = CDeclaredConfigurationLogger::GetLogger();
      v62 = L"DeclaredConfigurationStore_WriteResultData: udpate doc error message";
LABEL_131:
      v61 = v117;
      v63 = L"DSCNativeProviderConfiguration";
      goto LABEL_91;
    }
  }
  else
  {
    if ( (unsigned __int64)v14[3] <= 7 )
      LODWORD(v75) = (_DWORD)v14;
    else
      v75 = *v14;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      LODWORD(v76) = (_DWORD)a2;
    else
      v76 = *(_QWORD *)a2;
    v10 = DeclaredConfigurationStore_DeleteResultData((int)a1, v76, (int)v75, v71, (__int64)v117, lpSubKey);
    if ( v10 < 0 )
    {
      v60 = CDeclaredConfigurationLogger::GetLogger();
      v62 = L"DeclaredConfigurationStore_DeleteResultData: udpate doc error message";
      goto LABEL_131;
    }
  }
  v112[0] = 0;
  v77 = 1;
  v78 = *v102;
  v102 = (unsigned __int16 **)v102[1];
  if ( v78 != (unsigned __int16 *)v102 )
  {
    while ( 1 )
    {
      v79 = StringCchPrintfW(v112, 0xFu, L"KeyValue%d", v77);
      if ( v79 < 0 )
        break;
      VariantInit(&v100);
      v100.vt = 8;
      v80 = *(const OLECHAR **)v78;
      if ( *(_QWORD *)(*(_QWORD *)v78 + 24LL) > 7u )
        v80 = *(const OLECHAR **)v80;
      v100.llVal = (LONGLONG)SysAllocString(v80);
      if ( *((_QWORD *)a2 + 15) <= 7u )
        v81 = (const unsigned __int16 *)v14;
      else
        v81 = *v14;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v82 = (const unsigned __int16 *)a2;
      else
        v82 = *(const unsigned __int16 **)a2;
      v79 = DeclaredConfigurationStore_WriteResultData(
              (struct DeclaredConfigurationScopeData *)a1,
              v82,
              v81,
              0,
              v117,
              v112,
              L"value",
              &v100);
      if ( v79 < 0 )
      {
        v90 = CDeclaredConfigurationLogger::GetLogger();
        v91 = L"DeclaredConfigurationStore_WriteResultData: udpate Key Value";
        goto LABEL_177;
      }
      VariantClear(&v100);
      v100.vt = 8;
      v83 = (const OLECHAR *)(*(_QWORD *)v78 + 32LL);
      if ( *(_QWORD *)(*(_QWORD *)v78 + 56LL) > 7u )
        v83 = *(const OLECHAR **)v83;
      v100.llVal = (LONGLONG)SysAllocString(v83);
      if ( *((_QWORD *)a2 + 15) <= 7u )
        v84 = (const unsigned __int16 *)v14;
      else
        v84 = *v14;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v85 = (const unsigned __int16 *)a2;
      else
        v85 = *(const unsigned __int16 **)a2;
      v79 = DeclaredConfigurationStore_WriteResultData(
              (struct DeclaredConfigurationScopeData *)a1,
              v85,
              v84,
              0,
              v117,
              v112,
              L"Name",
              &v100);
      if ( v79 < 0 )
      {
        v90 = CDeclaredConfigurationLogger::GetLogger();
        v91 = L"DeclaredConfigurationStore_WriteResultData: udpate Key Name";
        goto LABEL_177;
      }
      VariantClear(&v100);
      v100.vt = 3;
      v100.lVal = *(unsigned __int8 *)(*(_QWORD *)v78 + 68LL);
      if ( *((_QWORD *)a2 + 15) <= 7u )
        v86 = (const unsigned __int16 *)v14;
      else
        v86 = *v14;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v87 = (const unsigned __int16 *)a2;
      else
        v87 = *(const unsigned __int16 **)a2;
      v79 = DeclaredConfigurationStore_WriteResultData(
              (struct DeclaredConfigurationScopeData *)a1,
              v87,
              v86,
              0,
              v117,
              v112,
              L"Key",
              &v100);
      if ( v79 < 0 )
      {
        v90 = CDeclaredConfigurationLogger::GetLogger();
        v91 = L"DeclaredConfigurationStore_WriteResultData: udpate Key State";
        goto LABEL_177;
      }
      VariantClear(&v100);
      v100.vt = 3;
      v100.lVal = *(_DWORD *)(*(_QWORD *)v78 + 104LL);
      if ( *((_QWORD *)a2 + 15) <= 7u )
        v88 = (const unsigned __int16 *)v14;
      else
        v88 = *v14;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v89 = (const unsigned __int16 *)a2;
      else
        v89 = *(const unsigned __int16 **)a2;
      v79 = DeclaredConfigurationStore_WriteResultData(
              (struct DeclaredConfigurationScopeData *)a1,
              v89,
              v88,
              0,
              v117,
              v112,
              L"typeStored",
              &v100);
      if ( v79 < 0 )
      {
        v90 = CDeclaredConfigurationLogger::GetLogger();
        v91 = L"DeclaredConfigurationStore_WriteResultData: udpate Key Reg Type";
LABEL_177:
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(v90, L"DSCNativeProviderInventory", v91, v117, v79);
        VariantClear(&v100);
        goto LABEL_182;
      }
      ++v77;
      VariantClear(&v100);
      v78 += 8;
      if ( v78 == (unsigned __int16 *)v102 )
        goto LABEL_175;
    }
    v92 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v92,
      L"DSCNativeProviderInventory",
      L"DeclaredConfigurationStore_WriteResultData: StringCchPrintf failure",
      v117,
      v79);
LABEL_182:
    std::wstring::_Tidy_deallocate(v111);
    DCNativeProviderOrchestration::~DCNativeProviderOrchestration((DCNativeProviderOrchestration *)v114);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v96);
    v10 = v79;
    goto LABEL_183;
  }
LABEL_175:
  std::wstring::_Tidy_deallocate(v111);
  DCNativeProviderOrchestration::~DCNativeProviderOrchestration((DCNativeProviderOrchestration *)v114);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v96);
  std::wstring::_Tidy_deallocate(v113);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1800c9014  push    rbx
0x1800c9016  push    rsi
0x1800c9017  push    rdi
0x1800c9018  push    r12
0x1800c901a  push    r13
0x1800c901c  push    r14
0x1800c901e  push    r15
0x1800c9020  sub     rsp, 310h
0x1800c9027  mov     rax, cs:__security_cookie
0x1800c902e  xor     rax, rsp
0x1800c9031  mov     [rsp+348h+var_48], rax
0x1800c9039  mov     ebx, r9d
0x1800c903c  mov     rsi, r8
0x1800c903f  mov     [rsp+348h+var_2A0], r8
0x1800c9047  mov     r14, rdx
0x1800c904a  mov     r12, rcx
0x1800c904d  mov     rax, [rsp+348h+arg_20]
0x1800c9055  mov     [rsp+348h+var_288], rax
0x1800c905d  mov     rax, [rsp+348h+arg_28]
0x1800c9065  mov     [rsp+348h+var_280], rax
0x1800c906d  lea     rcx, [rsp+348h+pvarg]; pvarg
0x1800c9072  call    cs:__imp_VariantInit
0x1800c9078  nop
0x1800c9079  xor     edi, edi
0x1800c907b  mov     [rsp+348h+var_B8], di
0x1800c9083  mov     r9d, ebx
0x1800c9086  lea     r8, aCspD; "CSP%d"
0x1800c908d  lea     edx, [rdi+0Fh]; unsigned __int64
0x1800c9090  lea     rcx, [rsp+348h+var_B8]; unsigned __int16 *
0x1800c9098  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c909d  mov     ebx, eax
0x1800c909f  test    eax, eax
0x1800c90a1  jns     short loc_1800C90B5
0x1800c90a3  lea     rcx, [rsp+348h+pvarg]; pvarg
0x1800c90a8  call    cs:__imp_VariantClear
0x1800c90ae  mov     eax, ebx
0x1800c90b0  jmp     loc_1800C9F0D
0x1800c90b5  lea     rcx, [rsp+348h+var_1A8]
0x1800c90bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c90c2  nop
0x1800c90c3  lea     rdx, aCooked_0; "cooked\\"
0x1800c90ca  lea     rcx, [rsp+348h+var_1C8]
0x1800c90d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c90d7  nop
0x1800c90d8  lea     r8, [rsp+348h+var_B8]
0x1800c90e0  mov     rdx, rax
0x1800c90e3  lea     rcx, [rsp+348h+var_1E8]
0x1800c90eb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800c90f0  mov     rdx, rax
0x1800c90f3  lea     rcx, [rsp+348h+var_1A8]
0x1800c90fb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c9100  lea     rcx, [rsp+348h+var_1E8]
0x1800c9108  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c910d  nop
0x1800c910e  lea     rcx, [rsp+348h+var_1C8]
0x1800c9116  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c911b  nop
0x1800c911c  lea     rcx, [rsp+348h+pvarg]; pvarg
0x1800c9121  call    cs:__imp_VariantClear
0x1800c9127  mov     eax, 3
0x1800c912c  mov     word ptr [rsp+348h+pvarg], ax
0x1800c9131  mov     dword ptr [rsp+348h+pvarg+8], 2
0x1800c9139  lea     r15, [r14+60h]
0x1800c913d  cmp     qword ptr [r15+18h], 7
0x1800c9142  jbe     short loc_1800C9149
0x1800c9144  mov     r8, [r15]
0x1800c9147  jmp     short loc_1800C914C
0x1800c9149  mov     r8, r15; unsigned __int16 *
0x1800c914c  cmp     qword ptr [r14+18h], 7
0x1800c9151  jbe     short loc_1800C9158
0x1800c9153  mov     rdx, [r14]
0x1800c9156  jmp     short loc_1800C915B
0x1800c9158  mov     rdx, r14; unsigned __int16 *
0x1800c915b  lea     rax, [rsp+348h+pvarg]
0x1800c9160  mov     [rsp+348h+var_310], rax; struct tagVARIANT *
0x1800c9165  lea     rax, ValueName; "state"
0x1800c916c  mov     [rsp+348h+lpValueName], rax; lpValueName
0x1800c9171  mov     [rsp+348h+lpSubKey], rdi; unsigned __int16 *
0x1800c9176  lea     rax, [rsp+348h+var_B8]
0x1800c917e  mov     [rsp+348h+var_328], rax; unsigned __int16 *
0x1800c9183  xor     r9d, r9d; unsigned __int16 *
0x1800c9186  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x1800c9189  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x1800c918e  mov     ebx, eax
0x1800c9190  test    eax, eax
0x1800c9192  jns     short loc_1800C91BF
0x1800c9194  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c9199  mov     dword ptr [rsp+348h+var_328], ebx; int
0x1800c919d  lea     r9, aUpdateDocState_0; "Update doc State to DCCSPURIState::Conf"...
0x1800c91a4  lea     r8, aDeclaredconfig_203; "DeclaredConfigurationStore_WriteResultD"...
0x1800c91ab  lea     rdx, aDscnativeprovi; "DSCNativeProviderInventory"
0x1800c91b2  mov     rcx, rax; this
0x1800c91b5  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800c91ba  jmp     loc_1800C9EDD
0x1800c91bf  mov     [rsp+348h+cbSid], edi
0x1800c91c3  mov     dword ptr [rsp+348h+var_2C8], 3Fh ; '?'
0x1800c91ce  lea     r8, [rsp+348h+var_2C8]; enum EnrollmentStateTag *
0x1800c91d6  lea     rdx, [rsp+348h+cbSid]; int *
0x1800c91db  mov     rcx, [r12]; StringUuid
0x1800c91df  call    ?DCIsValidEnrollment@@YAJPEBGPEAHPEAW4EnrollmentStateTag@@@Z; DCIsValidEnrollment(ushort const *,int *,EnrollmentStateTag *)
0x1800c91e4  test    eax, eax
0x1800c91e6  js      short loc_1800C9216
0x1800c91e8  cmp     [rsp+348h+cbSid], edi
0x1800c91ec  jz      short loc_1800C91F8
0x1800c91ee  cmp     dword ptr [rsp+348h+var_2C8], 4
0x1800c91f6  jnz     short loc_1800C9216
0x1800c91f8  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c91fd  mov     ebx, 8000FFFFh
0x1800c9202  mov     r8d, ebx; int
0x1800c9205  mov     rdx, [r12]; unsigned __int16 *
0x1800c9209  mov     rcx, rax; this
0x1800c920c  call    ?LogEnrollmentInvalidOrUnenrolling@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogEnrollmentInvalidOrUnenrolling(ushort const *,long)
0x1800c9211  jmp     loc_1800C9EDD
0x1800c9216  mov     [rsp+348h+var_2F0], rdi
0x1800c921b  lea     rcx, [rsp+348h+var_188]; this
0x1800c9223  call    ??0DCNativeProviderOrchestration@@QEAA@XZ; DCNativeProviderOrchestration::DCNativeProviderOrchestration(void)
0x1800c9228  nop
0x1800c9229  lea     rax, [rsp+348h+var_1E8]
0x1800c9231  mov     [rsp+348h+var_298], rax
0x1800c9239  lea     r13, [rsi+50h]
0x1800c923d  mov     rdx, r13
0x1800c9240  lea     rcx, [rsp+348h+var_1E8]
0x1800c9248  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c924d  mov     rdi, rax
0x1800c9250  lea     rax, [rsp+348h+var_1C8]
0x1800c9258  mov     [rsp+348h+StringSid], rax
0x1800c9260  add     rsi, 30h ; '0'
0x1800c9264  mov     rdx, rsi
0x1800c9267  lea     rcx, [rsp+348h+var_1C8]
0x1800c926f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c9274  mov     rbx, rax
0x1800c9277  mov     rdx, [r12]
0x1800c927b  lea     rcx, [rsp+348h+var_2C0]
0x1800c9283  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c9288  nop
0x1800c9289  mov     r9, rdi
0x1800c928c  mov     r8, rbx
0x1800c928f  mov     rdx, rax
0x1800c9292  lea     rcx, [rsp+348h+var_188]
0x1800c929a  call    ?PopulateFromRegistry@DCNativeProviderOrchestration@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; DCNativeProviderOrchestration::PopulateFromRegistry(std::wstring,std::wstring,std::wstring)
0x1800c929f  test    eax, eax
0x1800c92a1  js      loc_1800C957A
0x1800c92a7  cmp     [rsp+348h+var_108], 0
0x1800c92b0  jz      loc_1800C957A
0x1800c92b6  lea     rcx, [rsp+348h+var_1E8]
0x1800c92be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c92c3  nop
0x1800c92c4  lea     rbx, [r14+20h]
0x1800c92c8  cmp     qword ptr [rbx+18h], 7
0x1800c92cd  jbe     short loc_1800C92D4
0x1800c92cf  mov     rcx, [rbx]
0x1800c92d2  jmp     short loc_1800C92D7
0x1800c92d4  mov     rcx, rbx
0x1800c92d7  lea     rdx, aDevice_4; "device"
0x1800c92de  call    cs:__imp__o__wcsicmp
0x1800c92e4  test    eax, eax
0x1800c92e6  jnz     loc_1800C93DA
0x1800c92ec  mov     [rsp+348h+cbSid], 44h ; 'D'
0x1800c92f4  lea     r9, [rsp+348h+cbSid]; cbSid
0x1800c92f9  lea     r8, [rsp+348h+pSid]; pSid
0x1800c9301  xor     edx, edx; DomainSid
0x1800c9303  lea     ecx, [rax+16h]; WellKnownSidType
0x1800c9306  call    cs:__imp_CreateWellKnownSid
0x1800c930c  test    eax, eax
0x1800c930e  jnz     short loc_1800C9377
0x1800c9310  call    cs:__imp_GetLastError
0x1800c9316  mov     ebx, eax
0x1800c9318  test    eax, eax
0x1800c931a  jle     short loc_1800C9325
0x1800c931c  movzx   ebx, ax
0x1800c931f  or      ebx, 80070000h
0x1800c9325  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c932a  lea     r9, aWellknownsidfa; "WellKnownSidFailure"
0x1800c9331  mov     dword ptr [rsp+348h+var_328], ebx; int
0x1800c9335  lea     r8, aDeclaredconfig_247; "DeclaredConfigurationStore_UserSidConfi"...
0x1800c933c  lea     rdx, aDscnativeprovi; "DSCNativeProviderInventory"
0x1800c9343  mov     rcx, rax; this
0x1800c9346  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800c934b  nop
0x1800c934c  lea     rcx, [rsp+348h+var_1E8]
0x1800c9354  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9359  nop
0x1800c935a  lea     rcx, [rsp+348h+var_188]; this
0x1800c9362  call    ??1DCNativeProviderOrchestration@@QEAA@XZ; DCNativeProviderOrchestration::~DCNativeProviderOrchestration(void)
0x1800c9367  nop
0x1800c9368  lea     rcx, [rsp+348h+var_2F0]
0x1800c936d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c9372  jmp     loc_1800C9EDD
0x1800c9377  mov     [rsp+348h+StringSid], 0
0x1800c9383  lea     rdx, [rsp+348h+StringSid]; StringSid
0x1800c938b  lea     rcx, [rsp+348h+pSid]; Sid
0x1800c9393  call    cs:__imp_ConvertSidToStringSidW
0x1800c9399  test    eax, eax
0x1800c939b  jnz     short loc_1800C93C3
0x1800c939d  call    cs:__imp_GetLastError
0x1800c93a3  mov     ebx, eax
0x1800c93a5  test    eax, eax
0x1800c93a7  jle     short loc_1800C93B2
0x1800c93a9  movzx   ebx, ax
0x1800c93ac  or      ebx, 80070000h
0x1800c93b2  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c93b7  lea     r9, aConvertsidtost; "ConvertSidToStringSidFailure"
0x1800c93be  jmp     loc_1800C9331
0x1800c93c3  mov     rdx, [rsp+348h+StringSid]
0x1800c93cb  lea     rcx, [rsp+348h+var_1C8]
0x1800c93d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c93d8  jmp     short loc_1800C942E
0x1800c93da  cmp     qword ptr [rbx+18h], 7
0x1800c93df  jbe     short loc_1800C93E4
0x1800c93e1  mov     rbx, [rbx]
0x1800c93e4  lea     rdx, aUser_0; "user"
0x1800c93eb  mov     rcx, rbx
0x1800c93ee  call    cs:__imp__o__wcsicmp
0x1800c93f4  test    eax, eax
0x1800c93f6  jnz     loc_1800C954A
0x1800c93fc  mov     rcx, [r12+8]; pbstr
0x1800c9401  test    rcx, rcx
0x1800c9404  jz      loc_1800C9534
0x1800c940a  cmp     ax, [rcx]
0x1800c940d  jz      loc_1800C9534
0x1800c9413  call    cs:__imp_SysStringLen
0x1800c9419  mov     r8d, eax
0x1800c941c  mov     rdx, [r12+8]
0x1800c9421  lea     rcx, [rsp+348h+var_1C8]
0x1800c9429  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800c942e  mov     rdx, rax
0x1800c9431  lea     rcx, [rsp+348h+var_1E8]
0x1800c9439  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c943e  lea     rcx, [rsp+348h+var_1C8]
0x1800c9446  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c944b  lea     rcx, [rsp+348h+var_2C0]
0x1800c9453  call    ??$make_shared@VDCDSCNativeKeyValue@@$$V@std@@YA?AV?$shared_ptr@VDCDSCNativeKeyValue@@@0@XZ; std::make_shared<DCDSCNativeKeyValue,>(void)
0x1800c9458  nop
0x1800c9459  mov     rbx, qword ptr [rsp+348h+var_2C0]
0x1800c9461  lea     rcx, [rbx+20h]
0x1800c9465  lea     rdx, [rsp+348h+var_118]
0x1800c946d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800c9472  lea     rdx, [rsp+348h+var_1E8]
0x1800c947a  mov     rcx, rbx
0x1800c947d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800c9482  mov     rbx, [rsp+348h+var_2A0]
0x1800c948a  mov     rcx, [rbx+18h]
0x1800c948e  cmp     rcx, [rbx+20h]
0x1800c9492  jz      short loc_1800C94A8
0x1800c9494  lea     rdx, [rsp+348h+var_2C0]
0x1800c949c  call    ??0?$shared_ptr@VSCDSetting@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(std::shared_ptr<SCDSetting> const &)
0x1800c94a1  add     qword ptr [rbx+18h], 10h
0x1800c94a6  jmp     short loc_1800C94BC
0x1800c94a8  lea     r8, [rsp+348h+var_2C0]
0x1800c94b0  mov     rdx, rcx
0x1800c94b3  lea     rcx, [rbx+10h]
0x1800c94b7  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VDCDSCNativeKeyValue@@@std@@@?$vector@V?$shared_ptr@VDCDSCNativeKeyValue@@@std@@V?$allocator@V?$shared_ptr@VDCDSCNativeKeyValue@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VDCDSCNativeKeyValue@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<DCDSCNativeKeyValue>>::_Emplace_reallocate<std::shared_ptr<DCDSCNativeKeyValue> const &>(std::shared_ptr<DCDSCNativeKeyValue> * const,std::shared_ptr<DCDSCNativeKeyValue> const &)
0x1800c94bc  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c94c1  lea     r9, word_180142E98; unsigned __int16 *
0x1800c94c8  lea     r8, aSidpopulatedsu; "SidPopulatedSuccessfully"
0x1800c94cf  lea     rdx, aDeclaredconfig_247; "DeclaredConfigurationStore_UserSidConfi"...
0x1800c94d6  mov     rcx, rax; this
0x1800c94d9  call    ?LogOrchestratorGenericInfo@CDeclaredConfigurationLogger@@QEAAXPEBG00@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(ushort const *,ushort const *,ushort const *)
0x1800c94de  xorps   xmm0, xmm0
0x1800c94e1  movdqu  xmmword ptr [rsp+348h+var_278], xmm0
0x1800c94ea  lea     rdx, [rsp+348h+var_278]
0x1800c94f2  lea     rcx, [rsp+348h+var_2C0]
0x1800c94fa  call    ??4?$shared_ptr@VDCURI@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DCURI>::operator=(std::shared_ptr<DCURI> &&)
0x1800c94ff  mov     rcx, [rsp+348h+var_278+8]; this
0x1800c9507  test    rcx, rcx
0x1800c950a  jz      short loc_1800C9512
0x1800c950c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9511  nop
0x1800c9512  mov     rcx, qword ptr [rsp+348h+var_2C0+8]; this
0x1800c951a  test    rcx, rcx
0x1800c951d  jz      short loc_1800C9525
0x1800c951f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9524  nop
0x1800c9525  lea     rcx, [rsp+348h+var_1E8]
0x1800c952d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9532  jmp     short loc_1800C9582
0x1800c9534  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c9539  mov     ebx, 80070057h
0x1800c953e  lea     r9, aNousersidkeyfo; "NoUserSidKeyFound"
0x1800c9545  jmp     loc_1800C9331
0x1800c954a  lea     rcx, [rsp+348h+var_1E8]
0x1800c9552  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9557  nop
0x1800c9558  lea     rcx, [rsp+348h+var_188]; this
0x1800c9560  call    ??1DCNativeProviderOrchestration@@QEAA@XZ; DCNativeProviderOrchestration::~DCNativeProviderOrchestration(void)
0x1800c9565  nop
0x1800c9566  lea     rcx, [rsp+348h+var_2F0]
0x1800c956b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c9570  mov     ebx, 8000FFFFh
0x1800c9575  jmp     loc_1800C9EDD
0x1800c957a  mov     rbx, [rsp+348h+var_2A0]
0x1800c9582  cmp     dword ptr [rbx+9Ch], 4
0x1800c9589  jz      short loc_1800C95BB
0x1800c958b  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c9590  mov     ebx, 8000FFFFh
0x1800c9595  mov     dword ptr [rsp+348h+var_328], ebx; int
0x1800c9599  lea     r9, word_180142E98; unsigned __int16 *
0x1800c95a0  lea     r8, aInvalidConfigr; "invalid configrequest type"
0x1800c95a7  lea     rdx, aDscnativeprovi; "DSCNativeProviderInventory"
0x1800c95ae  mov     rcx, rax; this
  ... truncated ...
```
