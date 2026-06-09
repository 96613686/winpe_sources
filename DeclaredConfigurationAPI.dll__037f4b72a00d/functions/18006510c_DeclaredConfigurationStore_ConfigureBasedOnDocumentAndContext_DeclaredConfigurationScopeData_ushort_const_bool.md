# DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext(DeclaredConfigurationScopeData *,ushort const *,bool,long *)

- ea: `0x18006510c`
- end: `0x180065ccf`
- name: `?DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext@@YAJPEAUDeclaredConfigurationScopeData@@PEBG_NPEAJ@Z`
- size: `3011`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, const unsigned __int16 *, bool, int *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007f370`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x180018cc4`
- `0x180019d38`
- `0x18001c32c`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18001d37c`
- `0x180060854`
- `0x180060dec`
- `0x180061a38`
- `0x1800641a0`
- `0x18006510c`
- `0x1800725e0`
- `0x180076c10`
- `0x180085938`
- `0x180086c10`
- `0x180098e10`
- `0x18009a2e4`
- `0x1800a0138`
- `0x1800aab60`
- `0x1800f5c8c`
- `0x1800f9c1c`
- `0x1800f9cb4`
- `0x1800f9d70`
- `0x1800f9e64`
- `0x180100ad8`
- `0x180119490`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `DeclaredConfiguration!DMOrchestratorProcessDocsBasedOnState` at `0x180065b4f`
- `DeclaredConfiguration!DMOrchestratorProcessDocsBasedOnState` at `0x180065b4f`
- `OLEAUT32!__imp_VariantInit` at `0x1800654be`
- `OLEAUT32!__imp_VariantInit` at `0x18006566e`
- `OLEAUT32!__imp_VariantInit` at `0x180065802`
- `OLEAUT32!__imp_VariantInit` at `0x1800654be`
- `OLEAUT32!__imp_VariantInit` at `0x18006566e`
- `OLEAUT32!__imp_VariantInit` at `0x180065802`
- `OLEAUT32!__imp_VariantClear` at `0x18006553c`
- `OLEAUT32!__imp_VariantClear` at `0x1800655db`
- `OLEAUT32!__imp_VariantClear` at `0x18006561b`
- `OLEAUT32!__imp_VariantClear` at `0x180065706`
- `OLEAUT32!__imp_VariantClear` at `0x180065772`
- `OLEAUT32!__imp_VariantClear` at `0x1800657b1`
- `OLEAUT32!__imp_VariantClear` at `0x180065885`
- `OLEAUT32!__imp_VariantClear` at `0x1800658f0`
- `OLEAUT32!__imp_VariantClear` at `0x18006553c`
- `OLEAUT32!__imp_VariantClear` at `0x1800655db`
- `OLEAUT32!__imp_VariantClear` at `0x18006561b`
- `OLEAUT32!__imp_VariantClear` at `0x180065706`
- `OLEAUT32!__imp_VariantClear` at `0x180065772`
- `OLEAUT32!__imp_VariantClear` at `0x1800657b1`
- `OLEAUT32!__imp_VariantClear` at `0x180065885`
- `OLEAUT32!__imp_VariantClear` at `0x1800658f0`

## string_xrefs

- `0x1800656f0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x1800651d4`: `DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey`
- `0x180065326`: `DeclaredConfigurationStore_GetPersistedDocument`
- `0x180065a26`: `DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc`
- `0x180065a94`: `DeclaredConfigurationExtension_PolicyCSPConfigureGivenCurrentDoc`
- `0x1800653ab`: `DeclaredConfigurationStore_GetRefreshFlag`
- `0x1800659b4`: `DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc`
- `0x18006515c`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x18006586d`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x1800658af`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x1800658d3`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x18006591a`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x18006592f`: `DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext`
- `0x180065248`: `DCCDNUtil_GetRegistryString:Get MostRecentVersion`
- `0x18006544c`: `DeclaredConfigurationStore_CheckIfAllInstanceDataPresent`
- `0x180065521`: `DeclaredConfigurationStore_WriteResultData update doc state to DocMissingInstanceData`
- `0x1800656c8`: `DeclaredConfigurationStore_WriteResultData update doc instance variable substitute state`
- `0x1800656e1`: `failed to update doc instance variable substitue state`
- `0x180065758`: `DeclaredConfigurationStore_SubstituteInstanceData`
- `0x180065866`: `DeclaredConfigurationStore_WriteResultData update doc state to PrecheckNotFulfilled`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        int *a4)
{
  CDeclaredConfigurationLogger *Logger; // rax
  CDeclaredConfigurationLogger *v8; // rax
  int RefreshFlag; // ebx
  CDeclaredConfigurationLogger *v10; // rax
  CDeclaredConfigurationLogger *v11; // rax
  CDeclaredConfigurationLogger *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // r8
  _WORD *v15; // rdx
  __int64 v16; // r8
  CDeclaredConfigurationLogger *v17; // rax
  CDeclaredConfigurationLogger *v18; // rax
  CDeclaredConfigurationLogger *v19; // rax
  CDeclaredConfigurationLogger *v20; // rax
  unsigned int v21; // eax
  CDeclaredConfigurationLogger *v22; // rax
  CDeclaredConfigurationLogger *v23; // rax
  int v24; // eax
  CDeclaredConfigurationLogger *v25; // rax
  CDeclaredConfigurationLogger *v26; // rax
  CDeclaredConfigurationLogger *v27; // rax
  __int64 v28; // rdx
  int v29; // ecx
  CDeclaredConfigurationLogger *v30; // rax
  CDeclaredConfigurationLogger *v31; // rax
  CDeclaredConfigurationLogger *v32; // rax
  CDeclaredConfigurationLogger *v33; // rax
  CDeclaredConfigurationLogger *v34; // rax
  _QWORD *v35; // rbx
  _QWORD *v36; // r14
  CDeclaredConfigurationLogger *v37; // rax
  CDeclaredConfigurationLogger *v38; // rax
  CDeclaredConfigurationLogger *v39; // rax
  CDeclaredConfigurationLogger *v40; // rax
  CDeclaredConfigurationLogger *v41; // rax
  CDeclaredConfigurationLogger *v42; // rax
  CDeclaredConfigurationLogger *v43; // rax
  CDeclaredConfigurationLogger *v44; // rax
  CDeclaredConfigurationLogger *v45; // rax
  CDeclaredConfigurationLogger *v46; // rax
  int v47; // ecx
  int v48; // eax
  __int64 v49; // rbx
  CDeclaredConfigurationLogger *v50; // rax
  int v51; // ebx
  CDeclaredConfigurationLogger *v52; // rax
  int *v53; // rax
  CDeclaredConfigurationLogger *v54; // rax
  CDeclaredConfigurationLogger *v56; // rax
  char *v57; // [rsp+28h] [rbp-D8h]
  int EnrollmentIdSidStateDocIdKey; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  bool v60; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v61; // [rsp+54h] [rbp-ACh] BYREF
  HKEY v62; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v63; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v65; // [rsp+90h] [rbp-70h] BYREF
  void **p_Block; // [rsp+A8h] [rbp-58h]
  int *v67; // [rsp+B0h] [rbp-50h]
  char v68; // [rsp+B8h] [rbp-48h]
  char *v69[8]; // [rsp+C0h] [rbp-40h] BYREF
  char *v70; // [rsp+100h] [rbp+0h] BYREF
  char *v71; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v72; // [rsp+190h] [rbp+90h]
  _QWORD *v73; // [rsp+198h] [rbp+98h]
  _QWORD *v74; // [rsp+1A8h] [rbp+A8h]
  _QWORD *v75; // [rsp+1B0h] [rbp+B0h]
  int v76; // [rsp+1D0h] [rbp+D0h]
  int v77; // [rsp+1D8h] [rbp+D8h]
  unsigned int v78; // [rsp+364h] [rbp+264h]
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  EnrollmentIdSidStateDocIdKey = 0;
  Block = 0;
  v62 = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(
    Logger,
    L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext");
  p_Block = &Block;
  v67 = &EnrollmentIdSidStateDocIdKey;
  v68 = 1;
  *(_QWORD *)&v63.vt = &v62;
  v63.llVal = 0;
  *((_BYTE *)&v63.decVal + 16) = 1;
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(
                                   a1,
                                   a2,
                                   (HKEY *)&v63.llVal,
                                   0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v63);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    v8 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v8,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      L"DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey",
      &word_180142E98,
      EnrollmentIdSidStateDocIdKey);
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
    operator delete(Block);
    Block = 0;
    v10 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v10,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_81;
  }
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v62, 0, L"MostRecentVersion", (unsigned __int16 **)&Block);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    v11 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v11,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      L"DCCDNUtil_GetRegistryString:Get MostRecentVersion",
      &word_180142E98,
      EnrollmentIdSidStateDocIdKey);
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
    operator delete(Block);
    Block = 0;
    v12 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v12,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_81;
  }
  DCDocument::DCDocument((DCDocument *)v69);
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  std::wstring::_Assign<unsigned short>(v69, a2, (char *)v14);
  v15 = (_WORD *)*((_QWORD *)a1 + 1);
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  std::wstring::_Assign<unsigned short>(&v70, v15, (char *)v16);
  do
    ++v13;
  while ( *((_WORD *)Block + v13) );
  std::wstring::_Assign<unsigned short>(&v71, Block, (char *)v13);
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetPersistedDocument(
                                   a1,
                                   v62,
                                   (__int64)Block,
                                   0,
                                   (__int64)v69,
                                   2);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    v17 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v17,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      L"DeclaredConfigurationStore_GetPersistedDocument",
      &word_180142E98,
      EnrollmentIdSidStateDocIdKey);
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
    DCDocument::~DCDocument((DCDocument *)v69);
    operator delete(Block);
    Block = 0;
    v18 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v18,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_81;
  }
  v61 = 0;
  RefreshFlag = DeclaredConfigurationStore_GetRefreshFlag(*(OLECHAR **)a1, a2, &v61);
  if ( (int)(RefreshFlag + 0x80000000) >= 0 && RefreshFlag != -2147024894 )
  {
    v19 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
      v19,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      L"DeclaredConfigurationStore_GetRefreshFlag",
      &word_180142E98,
      RefreshFlag);
    DCDocument::~DCDocument((DCDocument *)v69);
    operator delete(Block);
    Block = 0;
    v20 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v20,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_81;
  }
  if ( v76 != 2 )
  {
    LOBYTE(v21) = v78;
    if ( (v78 & 1) != 0 || (v78 & 2) != 0 || (v78 & 0x20) != 0 )
    {
      v60 = 0;
      EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(
                                       a1,
                                       (struct DCDocument *)v69,
                                       &v60);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v22 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v22,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"DeclaredConfigurationStore_CheckIfAllInstanceDataPresent",
          &word_180142E98,
          EnrollmentIdSidStateDocIdKey);
        RefreshFlag = EnrollmentIdSidStateDocIdKey;
        DCDocument::~DCDocument((DCDocument *)v69);
        operator delete(Block);
        Block = 0;
        v23 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v23,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_81;
      }
      if ( v60 )
      {
        if ( (v78 & 0x20) != 0 )
          v21 = v78 & 0xFFFFFF3F | 0x80;
        else
          v21 = v78 & 0xFFFFFFF9 | 4;
        v78 = v21;
      }
      else
      {
        if ( (v78 & 0x20) != 0 )
          v24 = v78 | 0x40;
        else
          v24 = v78 | 2;
        v78 = v24;
        VariantInit(&pvarg);
        pvarg.vt = 3;
        pvarg.lVal = 41;
        EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_WriteResultData(
                                         a1,
                                         a2,
                                         (const unsigned __int16 *)Block,
                                         0,
                                         0,
                                         0,
                                         L"state",
                                         &pvarg);
        if ( EnrollmentIdSidStateDocIdKey < 0 )
        {
          v25 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v25,
            L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
            L"DeclaredConfigurationStore_WriteResultData update doc state to DocMissingInstanceData",
            &word_180142E98,
            EnrollmentIdSidStateDocIdKey);
          RefreshFlag = EnrollmentIdSidStateDocIdKey;
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v69);
          operator delete(Block);
          Block = 0;
          v26 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v26,
            L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
            EnrollmentIdSidStateDocIdKey);
          goto LABEL_81;
        }
        v27 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
          v27,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"NotAllInstanceDataAreAvailable",
          &word_180142E98);
        EnrollmentIdSidStateDocIdKey = -2147024875;
        if ( byte_180189FC1 < 0 )
          McTemplateU0zzd_EventWriteTransfer(
            v29,
            (unsigned int)OrchestratorGenericWarning,
            (unsigned int)L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
            (unsigned int)L"NotAllInstanceDataAreAvailable",
            21);
        LOBYTE(v28) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
          v28);
        if ( !v61 )
        {
          RefreshFlag = EnrollmentIdSidStateDocIdKey;
          VariantClear(&pvarg);
          DCDocument::~DCDocument((DCDocument *)v69);
          operator delete(Block);
          Block = 0;
          v30 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
            v30,
            L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
            EnrollmentIdSidStateDocIdKey);
          goto LABEL_81;
        }
        VariantClear(&pvarg);
        LOBYTE(v21) = v78;
      }
    }
    if ( (v21 & 4) != 0 || (v21 & 0x80u) != 0 )
    {
      EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_SubstituteInstanceDataOld(a1, (struct DCDocument *)v69);
      VariantInit(&v65);
      v65.vt = 3;
      v65.lVal = EnrollmentIdSidStateDocIdKey;
      RefreshFlag = DeclaredConfigurationStore_WriteResultData(
                      a1,
                      a2,
                      (const unsigned __int16 *)Block,
                      0,
                      0,
                      0,
                      L"instanceDataSubstituteState",
                      &v65);
      if ( RefreshFlag < 0 )
      {
        v31 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v31,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"DeclaredConfigurationStore_WriteResultData update doc instance variable substitute state",
          &word_180142E98,
          RefreshFlag);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3D42,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)RefreshFlag,
          (int)"failed to update doc instance variable substitue state",
          v57);
        VariantClear(&v65);
        DCDocument::~DCDocument((DCDocument *)v69);
        operator delete(Block);
        Block = 0;
        v32 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v32,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_81;
      }
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v33 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v33,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"DeclaredConfigurationStore_SubstituteInstanceData",
          &word_180142E98,
          EnrollmentIdSidStateDocIdKey);
        RefreshFlag = EnrollmentIdSidStateDocIdKey;
        VariantClear(&v65);
        DCDocument::~DCDocument((DCDocument *)v69);
        operator delete(Block);
        Block = 0;
        v34 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v34,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_81;
      }
      VariantClear(&v65);
    }
    if ( v76 != 2 )
    {
      v35 = v74;
      v36 = v75;
      if ( v75 != v74 )
      {
        while ( v35 != v36 )
        {
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v35 + 8LL))(*v35) )
          {
            VariantInit(&v63);
            v63.vt = 3;
            v63.lVal = 43;
            EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_WriteResultData(
                                             a1,
                                             a2,
                                             (const unsigned __int16 *)Block,
                                             0,
                                             0,
                                             0,
                                             L"state",
                                             &v63);
            if ( EnrollmentIdSidStateDocIdKey >= 0 )
            {
              v39 = CDeclaredConfigurationLogger::GetLogger();
              CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
                v39,
                L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
                L"PrecheckNotFulfilled",
                &word_180142E98);
              RefreshFlag = -2147024875;
              EnrollmentIdSidStateDocIdKey = -2147024875;
            }
            else
            {
              v37 = CDeclaredConfigurationLogger::GetLogger();
              CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                v37,
                L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
                L"DeclaredConfigurationStore_WriteResultData update doc state to PrecheckNotFulfilled",
                &word_180142E98,
                EnrollmentIdSidStateDocIdKey);
              RefreshFlag = EnrollmentIdSidStateDocIdKey;
            }
            VariantClear(&v63);
            DCDocument::~DCDocument((DCDocument *)v69);
            operator delete(Block);
            Block = 0;
            v38 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
              v38,
              L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
              EnrollmentIdSidStateDocIdKey);
            goto LABEL_81;
          }
          v35 += 2;
        }
      }
    }
  }
  switch ( v76 )
  {
    case 1:
      EnrollmentIdSidStateDocIdKey = DeclaredConfigurationExtension_PolicyCSPConfigureGivenCurrentDoc(
                                       a1,
                                       (struct DCDocument *)v69);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v45 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v45,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"DeclaredConfigurationExtension_PolicyCSPConfigureGivenCurrentDoc",
          &word_180142E98,
          EnrollmentIdSidStateDocIdKey);
        RefreshFlag = EnrollmentIdSidStateDocIdKey;
        DCDocument::~DCDocument((DCDocument *)v69);
        operator delete(Block);
        Block = 0;
        v46 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v46,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_81;
      }
      break;
    case 2:
      EnrollmentIdSidStateDocIdKey = DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc(
                                       a1,
                                       (struct DCDocument *)v69);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v43 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v43,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"DeclaredConfigurationExtension_DeleteConfigurationsGivenCurrentDoc",
          &word_180142E98,
          EnrollmentIdSidStateDocIdKey);
        RefreshFlag = EnrollmentIdSidStateDocIdKey;
        DCDocument::~DCDocument((DCDocument *)v69);
        operator delete(Block);
        Block = 0;
        v44 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v44,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_81;
      }
      break;
    case 4:
      EnrollmentIdSidStateDocIdKey = DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc(
                                       a1,
                                       (struct DCDocument *)v69);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        v41 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          v41,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          L"DeclaredConfigurationExtension_GetSettingsGivenInventoryDoc",
          &word_180142E98,
          EnrollmentIdSidStateDocIdKey);
        RefreshFlag = EnrollmentIdSidStateDocIdKey;
        DCDocument::~DCDocument((DCDocument *)v69);
        operator delete(Block);
        Block = 0;
        v42 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
          v42,
          L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
          EnrollmentIdSidStateDocIdKey);
        goto LABEL_81;
      }
      break;
    default:
      DCDocument::~DCDocument((DCDocument *)v69);
      operator delete(Block);
      Block = 0;
      v40 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
        v40,
        L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
        EnrollmentIdSidStateDocIdKey);
      RefreshFlag = -2147418113;
      goto LABEL_81;
  }
  if ( v73 == v72 )
    goto LABEL_74;
  if ( (**(unsigned int (__fastcall ***)(_QWORD))*v72)(*v72) == 2 )
  {
    if ( *(_BYTE *)(_RTDynamicCast_0(
                      *v72,
                      0,
                      &DCProviderOrchestration `RTTI Type Descriptor',
                      &DCNativeProviderOrchestration `RTTI Type Descriptor',
                      0)
                  + 177) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DllRefactored>::GetImpl'::`2'::impl) )
      {
        v48 = DMOrchestratorProcessDocsBasedOnState(43);
      }
      else
      {
        v49 = *(_QWORD *)&qword_18018A6C8;
        if ( !*(_QWORD *)&qword_18018A6C8 )
        {
          InitOrchestratorEngine();
          v49 = *(_QWORD *)&qword_18018A6C8;
          if ( EnrollmentIdSidStateDocIdKey < 0 )
          {
            v50 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v50,
              L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
              L"GetOrchestratorEngine",
              &word_180142E98,
              EnrollmentIdSidStateDocIdKey);
          }
          if ( !v49 )
            goto LABEL_74;
        }
        v48 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 40LL))(v49, 43);
      }
      v51 = v48;
      v52 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v52,
        L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
        L"ProcessDocsBasedOnState",
        &word_180142E98,
        v51);
    }
LABEL_74:
    if ( a4 )
    {
      v53 = (int *)qword_180189910;
      do
      {
        if ( *v53 == v77 )
          break;
        ++v53;
      }
      while ( v53 != &dword_18018993C );
      if ( v53 != &dword_18018993C )
        *a4 = -2100297714;
    }
    RefreshFlag = EnrollmentIdSidStateDocIdKey;
    DCDocument::~DCDocument((DCDocument *)v69);
    operator delete(Block);
    Block = 0;
    v54 = CDeclaredConfigurationLogger::GetLogger();
    CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
      v54,
      L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
      EnrollmentIdSidStateDocIdKey);
    goto LABEL_81;
  }
  RefreshFlag = -2147024809;
  if ( byte_180189FC1 < 0 )
    McTemplateU0zzd_EventWriteTransfer(
      v47,
      (unsigned int)OrchestratorGenericFailure,
      (unsigned int)L"MsftProcessOrchestrationInfoActivity::Execute",
      (unsigned int)L"Wrong Provider Type",
      87);
  DCDocument::~DCDocument((DCDocument *)v69);
  operator delete(Block);
  Block = 0;
  v56 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorExitFunction(
    v56,
    L"DeclaredConfigurationStore_ConfigureBasedOnDocumentAndContext",
    EnrollmentIdSidStateDocIdKey);
LABEL_81:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
  return (unsigned int)RefreshFlag;
}

```

## disassembly

```asm
0x18006510c  mov     [rsp-8+arg_10], rbx
0x180065111  push    rbp
0x180065112  push    rsi
0x180065113  push    rdi
0x180065114  push    r12
0x180065116  push    r13
0x180065118  push    r14
0x18006511a  push    r15
0x18006511c  lea     rbp, [rsp-2C0h]
0x180065124  sub     rsp, 3C0h
0x18006512b  mov     rax, cs:__security_cookie
0x180065132  xor     rax, rsp
0x180065135  mov     [rbp+2F0h+var_40], rax
0x18006513c  mov     r12, r9
0x18006513f  mov     r15, rdx
0x180065142  mov     rsi, rcx
0x180065145  xor     r13d, r13d
0x180065148  mov     [rsp+3F0h+var_3B0], r13d
0x18006514d  mov     [rsp+3F0h+Block], r13
0x180065152  mov     [rsp+3F0h+var_398], r13
0x180065157  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18006515c  lea     r14, aDeclaredconfig_153; "DeclaredConfigurationStore_ConfigureBas"...
0x180065163  mov     rdx, r14; unsigned __int16 *
0x180065166  mov     rcx, rax; this
0x180065169  call    ?LogOrchestratorEnterFunction@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(ushort const *)
0x18006516e  lea     rax, [rsp+3F0h+Block]
0x180065173  mov     [rbp+2F0h+var_348], rax
0x180065177  lea     rax, [rsp+3F0h+var_3B0]
0x18006517c  mov     [rbp+2F0h+var_340], rax
0x180065180  mov     [rbp+2F0h+var_338], 1
0x180065184  lea     rax, [rsp+3F0h+var_398]
0x180065189  mov     qword ptr [rsp+3F0h+var_390], rax
0x18006518e  mov     qword ptr [rsp+3F0h+var_390+8], r13
0x180065193  mov     byte ptr [rsp+3F0h+var_390+10h], 1
0x180065198  xor     r9d, r9d; int
0x18006519b  lea     r8, [rsp+3F0h+var_390+8]; HKEY *
0x1800651a0  mov     rdx, r15; unsigned __int16 *
0x1800651a3  mov     rcx, rsi; struct DeclaredConfigurationScopeData *
0x1800651a6  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x1800651ab  mov     [rsp+3F0h+var_3B0], eax
0x1800651af  lea     rcx, [rsp+3F0h+var_390]
0x1800651b4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800651b9  cmp     [rsp+3F0h+var_3B0], r13d
0x1800651be  jge     short loc_180065214
0x1800651c0  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800651c5  mov     ecx, [rsp+3F0h+var_3B0]
0x1800651c9  mov     dword ptr [rsp+3F0h+var_3D0], ecx; int
0x1800651cd  lea     r9, word_180142E98; unsigned __int16 *
0x1800651d4  lea     r8, aDeclaredconfig_208; "DeclaredConfigurationStore_GetEnrollmen"...
0x1800651db  mov     rdx, r14; unsigned __int16 *
0x1800651de  mov     rcx, rax; this
0x1800651e1  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800651e6  mov     ebx, [rsp+3F0h+var_3B0]
0x1800651ea  mov     rcx, [rsp+3F0h+Block]; Block
0x1800651ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800651f4  mov     [rsp+3F0h+Block], r13
0x1800651f9  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800651fe  mov     r8d, [rsp+3F0h+var_3B0]; int
0x180065203  mov     rdx, r14; unsigned __int16 *
0x180065206  mov     rcx, rax; this
0x180065209  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18006520e  nop
0x18006520f  jmp     loc_180065C37
0x180065214  lea     r9, [rsp+3F0h+Block]; unsigned __int16 **
0x180065219  lea     r8, aMostrecentvers; "MostRecentVersion"
0x180065220  xor     edx, edx; unsigned __int16 *
0x180065222  mov     rcx, [rsp+3F0h+var_398]; HKEY
0x180065227  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18006522c  mov     [rsp+3F0h+var_3B0], eax
0x180065230  test    eax, eax
0x180065232  jns     short loc_180065288
0x180065234  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180065239  mov     ecx, [rsp+3F0h+var_3B0]
0x18006523d  mov     dword ptr [rsp+3F0h+var_3D0], ecx; int
0x180065241  lea     r9, word_180142E98; unsigned __int16 *
0x180065248  lea     r8, aDccdnutilGetre_4; "DCCDNUtil_GetRegistryString:Get MostRec"...
0x18006524f  mov     rdx, r14; unsigned __int16 *
0x180065252  mov     rcx, rax; this
0x180065255  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18006525a  mov     ebx, [rsp+3F0h+var_3B0]
0x18006525e  mov     rcx, [rsp+3F0h+Block]; Block
0x180065263  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065268  mov     [rsp+3F0h+Block], r13
0x18006526d  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180065272  mov     r8d, [rsp+3F0h+var_3B0]; int
0x180065277  mov     rdx, r14; unsigned __int16 *
0x18006527a  mov     rcx, rax; this
0x18006527d  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180065282  nop
0x180065283  jmp     loc_180065C37
0x180065288  lea     rcx, [rbp+2F0h+var_330]; this
0x18006528c  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x180065291  nop
0x180065292  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180065296  mov     r8, rbx
0x180065299  inc     r8
0x18006529c  cmp     [r15+r8*2], r13w
0x1800652a1  jnz     short loc_180065299
0x1800652a3  mov     rdx, r15
0x1800652a6  lea     rcx, [rbp+2F0h+var_330]
0x1800652aa  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800652af  mov     rdx, [rsi+8]
0x1800652b3  mov     r8, rbx
0x1800652b6  inc     r8
0x1800652b9  cmp     [rdx+r8*2], r13w
0x1800652be  jnz     short loc_1800652B6
0x1800652c0  lea     rcx, [rbp+2F0h+var_2F0]
0x1800652c4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800652c9  mov     rdx, [rsp+3F0h+Block]
0x1800652ce  inc     rbx
0x1800652d1  cmp     [rdx+rbx*2], r13w
0x1800652d6  jnz     short loc_1800652CE
0x1800652d8  mov     r8, rbx
0x1800652db  lea     rcx, [rbp+2F0h+var_2D0]
0x1800652df  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800652e4  mov     dword ptr [rsp+3F0h+var_3C8], 2
0x1800652ec  lea     rax, [rbp+2F0h+var_330]
0x1800652f0  mov     [rsp+3F0h+var_3D0], rax
0x1800652f5  xor     r9d, r9d
0x1800652f8  mov     r8, [rsp+3F0h+Block]
0x1800652fd  mov     rdx, [rsp+3F0h+var_398]
0x180065302  mov     rcx, rsi
0x180065305  call    ?DeclaredConfigurationStore_GetPersistedDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@PEBG2PEAVDCDocument@@W4DCPersistedDocType@@@Z; DeclaredConfigurationStore_GetPersistedDocument(DeclaredConfigurationScopeData *,HKEY__ *,ushort const *,ushort const *,DCDocument *,DCPersistedDocType)
0x18006530a  mov     [rsp+3F0h+var_3B0], eax
0x18006530e  test    eax, eax
0x180065310  jns     short loc_180065370
0x180065312  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180065317  mov     ecx, [rsp+3F0h+var_3B0]
0x18006531b  mov     dword ptr [rsp+3F0h+var_3D0], ecx; int
0x18006531f  lea     r9, word_180142E98; unsigned __int16 *
0x180065326  lea     r8, aDeclaredconfig_143; "DeclaredConfigurationStore_GetPersisted"...
0x18006532d  mov     rdx, r14; unsigned __int16 *
0x180065330  mov     rcx, rax; this
0x180065333  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180065338  mov     ebx, [rsp+3F0h+var_3B0]
0x18006533c  lea     rcx, [rbp+2F0h+var_330]; this
0x180065340  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x180065345  nop
0x180065346  mov     rcx, [rsp+3F0h+Block]; Block
0x18006534b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065350  mov     [rsp+3F0h+Block], r13
0x180065355  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18006535a  mov     r8d, [rsp+3F0h+var_3B0]; int
0x18006535f  mov     rdx, r14; unsigned __int16 *
0x180065362  mov     rcx, rax; this
0x180065365  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x18006536a  nop
0x18006536b  jmp     loc_180065C37
0x180065370  mov     [rsp+3F0h+var_39C], r13d
0x180065375  lea     r8, [rsp+3F0h+var_39C]; unsigned int *
0x18006537a  mov     rdx, r15; unsigned __int16 *
0x18006537d  mov     rcx, [rsi]; psz
0x180065380  call    ?DeclaredConfigurationStore_GetRefreshFlag@@YAJPEBG0PEAK@Z; DeclaredConfigurationStore_GetRefreshFlag(ushort const *,ushort const *,ulong *)
0x180065385  mov     ebx, eax
0x180065387  mov     eax, 80000000h
0x18006538c  lea     ecx, [rbx+rax]
0x18006538f  test    eax, ecx
0x180065391  jnz     short loc_1800653F2
0x180065393  cmp     ebx, 80070002h
0x180065399  jz      short loc_1800653F2
0x18006539b  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800653a0  mov     dword ptr [rsp+3F0h+var_3D0], ebx; int
0x1800653a4  lea     r9, word_180142E98; unsigned __int16 *
0x1800653ab  lea     r8, aDeclaredconfig_237; "DeclaredConfigurationStore_GetRefreshFl"...
0x1800653b2  mov     rdx, r14; unsigned __int16 *
0x1800653b5  mov     rcx, rax; this
0x1800653b8  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800653bd  nop
0x1800653be  lea     rcx, [rbp+2F0h+var_330]; this
0x1800653c2  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x1800653c7  nop
0x1800653c8  mov     rcx, [rsp+3F0h+Block]; Block
0x1800653cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800653d2  mov     [rsp+3F0h+Block], r13
0x1800653d7  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800653dc  mov     r8d, [rsp+3F0h+var_3B0]; int
0x1800653e1  mov     rdx, r14; unsigned __int16 *
0x1800653e4  mov     rcx, rax; this
0x1800653e7  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x1800653ec  nop
0x1800653ed  jmp     loc_180065C37
0x1800653f2  lea     rdi, word_180142E98
0x1800653f9  cmp     [rbp+2F0h+var_220], 2
0x180065400  jz      loc_180065936
0x180065406  mov     eax, [rbp+2F0h+var_8C]
0x18006540c  mov     bl, 20h ; ' '
0x18006540e  test    al, 1
0x180065410  jnz     short loc_18006541E
0x180065412  test    al, 2
0x180065414  jnz     short loc_18006541E
0x180065416  test    bl, al
0x180065418  jz      loc_180065649
0x18006541e  mov     [rsp+3F0h+var_3A0], r13b
0x180065423  lea     r8, [rsp+3F0h+var_3A0]; bool *
0x180065428  lea     rdx, [rbp+2F0h+var_330]; struct DCDocument *
0x18006542c  mov     rcx, rsi; struct DeclaredConfigurationScopeData *
0x18006542f  call    ?DeclaredConfigurationStore_CheckIfAllInstanceDataPresent@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEA_N@Z; DeclaredConfigurationStore_CheckIfAllInstanceDataPresent(DeclaredConfigurationScopeData *,DCDocument *,bool *)
0x180065434  mov     [rsp+3F0h+var_3B0], eax
0x180065438  test    eax, eax
0x18006543a  jns     short loc_180065496
0x18006543c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180065441  mov     ecx, [rsp+3F0h+var_3B0]
0x180065445  mov     dword ptr [rsp+3F0h+var_3D0], ecx; int
0x180065449  mov     r9, rdi; unsigned __int16 *
0x18006544c  lea     r8, aDeclaredconfig_122; "DeclaredConfigurationStore_CheckIfAllIn"...
0x180065453  mov     rdx, r14; unsigned __int16 *
0x180065456  mov     rcx, rax; this
0x180065459  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18006545e  mov     ebx, [rsp+3F0h+var_3B0]
0x180065462  lea     rcx, [rbp+2F0h+var_330]; this
0x180065466  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18006546b  nop
0x18006546c  mov     rcx, [rsp+3F0h+Block]; Block
0x180065471  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065476  mov     [rsp+3F0h+Block], r13
0x18006547b  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180065480  mov     r8d, [rsp+3F0h+var_3B0]; int
0x180065485  mov     rdx, r14; unsigned __int16 *
0x180065488  mov     rcx, rax; this
0x18006548b  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180065490  nop
0x180065491  jmp     loc_180065C37
0x180065496  mov     eax, [rbp+2F0h+var_8C]
0x18006549c  cmp     [rsp+3F0h+var_3A0], r13b
0x1800654a1  jnz     loc_180065629
0x1800654a7  test    bl, al
0x1800654a9  jz      short loc_1800654B0
0x1800654ab  or      eax, 40h
0x1800654ae  jmp     short loc_1800654B3
0x1800654b0  or      eax, 2
0x1800654b3  mov     [rbp+2F0h+var_8C], eax
0x1800654b9  lea     rcx, [rsp+3F0h+pvarg]; pvarg
0x1800654be  call    cs:__imp_VariantInit
0x1800654c4  nop
0x1800654c5  mov     ebx, 3
0x1800654ca  mov     word ptr [rsp+3F0h+pvarg], bx
0x1800654cf  mov     dword ptr [rbp+2F0h+pvarg+8], 29h ; ')'
0x1800654d6  lea     rax, [rsp+3F0h+pvarg]
0x1800654db  mov     [rsp+3F0h+var_3B8], rax; struct tagVARIANT *
0x1800654e0  lea     rax, ValueName; "state"
0x1800654e7  mov     [rsp+3F0h+lpValueName], rax; lpValueName
0x1800654ec  mov     [rsp+3F0h+var_3C8], r13; unsigned __int16 *
0x1800654f1  mov     [rsp+3F0h+var_3D0], r13; unsigned __int16 *
0x1800654f6  xor     r9d, r9d; unsigned __int16 *
0x1800654f9  mov     r8, [rsp+3F0h+Block]; unsigned __int16 *
0x1800654fe  mov     rdx, r15; unsigned __int16 *
0x180065501  mov     rcx, rsi; struct DeclaredConfigurationScopeData *
0x180065504  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x180065509  mov     [rsp+3F0h+var_3B0], eax
0x18006550d  test    eax, eax
0x18006550f  jns     short loc_180065577
0x180065511  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180065516  mov     ecx, [rsp+3F0h+var_3B0]
0x18006551a  mov     dword ptr [rsp+3F0h+var_3D0], ecx; int
0x18006551e  mov     r9, rdi; unsigned __int16 *
0x180065521  lea     r8, aDeclaredconfig_216; "DeclaredConfigurationStore_WriteResultD"...
0x180065528  mov     rdx, r14; unsigned __int16 *
0x18006552b  mov     rcx, rax; this
0x18006552e  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180065533  mov     ebx, [rsp+3F0h+var_3B0]
0x180065537  lea     rcx, [rsp+3F0h+pvarg]; pvarg
0x18006553c  call    cs:__imp_VariantClear
0x180065542  nop
0x180065543  lea     rcx, [rbp+2F0h+var_330]; this
0x180065547  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18006554c  nop
0x18006554d  mov     rcx, [rsp+3F0h+Block]; Block
0x180065552  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065557  mov     [rsp+3F0h+Block], r13
0x18006555c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180065561  mov     r8d, [rsp+3F0h+var_3B0]; int
0x180065566  mov     rdx, r14; unsigned __int16 *
0x180065569  mov     rcx, rax; this
0x18006556c  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180065571  nop
0x180065572  jmp     loc_180065C37
0x180065577  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18006557c  mov     r9, rdi; unsigned __int16 *
0x18006557f  lea     r8, aNotallinstance_0; "NotAllInstanceDataAreAvailable"
0x180065586  mov     rdx, r14; unsigned __int16 *
0x180065589  mov     rcx, rax; this
0x18006558c  call    ?LogOrchestratorGenericInfo@CDeclaredConfigurationLogger@@QEAAXPEBG00@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(ushort const *,ushort const *,ushort const *)
0x180065591  mov     eax, 80070015h
0x180065596  mov     [rsp+3F0h+var_3B0], eax
0x18006559a  cmp     cs:byte_180189FC1, r13b
0x1800655a1  jge     short loc_1800655BD
0x1800655a3  mov     dword ptr [rsp+3F0h+var_3D0], eax
0x1800655a7  lea     r9, aNotallinstance_0; "NotAllInstanceDataAreAvailable"
0x1800655ae  mov     r8, r14
0x1800655b1  lea     rdx, OrchestratorGenericWarning
0x1800655b8  call    McTemplateU0zzd_EventWriteTransfer
0x1800655bd  mov     dl, 1
0x1800655bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl(void)'::`2'::impl
0x1800655c6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800655cb  cmp     [rsp+3F0h+var_39C], r13d
0x1800655d0  jnz     short loc_180065616
0x1800655d2  mov     ebx, [rsp+3F0h+var_3B0]
0x1800655d6  lea     rcx, [rsp+3F0h+pvarg]; pvarg
0x1800655db  call    cs:__imp_VariantClear
0x1800655e1  nop
  ... truncated ...
```
