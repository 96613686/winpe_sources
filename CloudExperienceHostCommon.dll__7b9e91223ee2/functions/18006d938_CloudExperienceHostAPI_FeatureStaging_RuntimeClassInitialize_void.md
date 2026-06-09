# CloudExperienceHostAPI::FeatureStaging::RuntimeClassInitialize(void)

- ea: `0x18006d938`
- end: `0x18006fa52`
- name: `?RuntimeClassInitialize@FeatureStaging@CloudExperienceHostAPI@@QEAAJXZ`
- size: `8474`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::FeatureStaging *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180060164`

## callees

- `0x180004040`
- `0x180004160`
- `0x180004294`
- `0x180004694`
- `0x1800052ac`
- `0x1800128c4`
- `0x180012d70`
- `0x180012e4c`
- `0x180013020`
- `0x180013178`
- `0x180013a74`
- `0x180013c68`
- `0x18001a540`
- `0x18006d938`

## string_xrefs

- `0x18006d9be`: `RDX_OOBE_Password_Label_Accessibility`
- `0x18006db80`: `RDX_OOBE_Narrator_ScanMode_Activation_Accessibility`
- `0x18006dacc`: `RDX_OOBE_Keyboard_Focus_Accessibility`
- `0x18006db26`: `RDX_OOBE_Link_Hover_Accessibility`
- `0x18006dd1a`: `CommercialBrOOBETelemetry`
- `0x18006dc0c`: `TokenBasedRAAuth`
- `0x18006e263`: `RDX_OOBE_Toggle_Control_Type_Accessibility`
- `0x18006e2bd`: `RDX_OOBE_Accessibility_Improvements`
- `0x18006e3cb`: `RDX_OOBE_Alert_Contrast_Mode_Accessibility`
- `0x18006e425`: `RDX_OOBE_RetailDemoConfirmDlg_Narrator_Accessibility`
- `0x18006e47f`: `RDX_OOBE_Second_Confirmed_Dialog_Accessibility`
- `0x18006e4d9`: `RDX_OOBE_Entry_Dialog_Visibility_Accessibility`
- `0x18006e69b`: `Feature_ExpeditedUpdatePILess`
- `0x18006ea79`: `DeviceNameRebootMove`
- `0x18006efbf`: `AutopilotClearUserEspCacheOnComplete`
- `0x18006f1db`: `RDX_OOBE_Override_Toggle_Accessibility`
- `0x18006f235`: `RDX_OOBE_Edit_Box_Control_Type_Accessibility`
- `0x18006f844`: `PostponeFromLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostAPI::FeatureStaging::RuntimeClassInitialize(
        CloudExperienceHostAPI::FeatureStaging *this)
{
  char *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  _QWORD *v87; // rax
  _QWORD *v88; // rax
  _QWORD *v89; // rax
  __int64 v90; // rcx
  __int64 FeatureVariantUniqueIdentifier; // rdx
  __int64 v92; // rax
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rcx
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rcx
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rcx
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rcx
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rax
  const char *v117; // r9
  __int64 result; // rax
  _BYTE v119[40]; // [rsp+28h] [rbp-C0h] BYREF
  _QWORD v120[7]; // [rsp+50h] [rbp-98h] BYREF
  _QWORD *v121; // [rsp+88h] [rbp-60h]
  _QWORD v122[7]; // [rsp+90h] [rbp-58h] BYREF
  _QWORD *v123; // [rsp+C8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  try
  {
    v2 = (char *)this + 80;
    std::wstring::wstring(v119, L"RDX_DisableAdminAccount");
    v3 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_469a36b6241b61294f91d284de3e935f_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v3);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Password_Label_Accessibility");
    v4 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_4258fa28ef4e40684a6c8fec333b5c9e_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v4);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_TimedShutdown");
    v5 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_a8bab2242e7f8d9f688f8b48feb40940_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v5);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBERACValidation");
    v6 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_a31f93e1fbebc29a7ba6c40ce2767b60_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v6);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Keyboard_Focus_Accessibility");
    v7 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_264ea4da06fa5803825cd78d135b207f_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v7);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Link_Hover_Accessibility");
    v8 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_a8597fa3967f52e5cf3d83635fdcb114_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v8);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Narrator_ScanMode_Activation_Accessibility");
    v9 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_667d2c25b64fbecb1d88ab5f45275c50_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v9);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"ScoobeActivitySyncConsent");
    v10 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    std::function<bool (void)>::operator=<_lambda_27e6d86ac1c57032c9c385d67e49964f_,0>(v10);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"TokenBasedRAAuth");
    v11 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_c766a9467d5f1676226ab22c7e45022e_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v11);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AllowScoobeDeferralByUser");
    v12 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_dfdbe4c277571d0898db5f8c54c9fa48_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v12);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OOBERestoreFlowControlforAAD");
    v13 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_a1b4bc2ea0a35115f39864495e2fd2d9_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v13);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"CommercialBrOOBETelemetry");
    v14 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_052ea036cb479800503aa7f86787a2ce_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v14);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"FSIR_RestoreApi");
    v15 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_b00d941e9471b25c5a338deaec10fe98_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v15);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"FSIR_WamAuth");
    v16 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_cdb8740ed341e212f9a5b6e00d3325d6_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v16);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"GetMicrosoftEntraTenantId");
    v17 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_d34c1a63b0266c6d7e8b34700b09ddb9_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v17);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RestoreCSPIntuneReporting");
    v18 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_fb11beed06a479a7290b6c88b8c21ea6_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v18);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"UseNewSearchAndCortanaApps");
    v19 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_5a6a3981ad8a29a2f564834febbd3196_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v19);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"FamilySettingsAwareness");
    v20 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_e2da439eec536246e8ed85a4428a0e60_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v20);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"SetBrowserAsPDFHandlerInScoobe");
    v21 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_b940132407184bc322abd93116844cde_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v21);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"ShowBrowserOnScoobe");
    v22 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_43618939f6268384adfdd87082d0bfab_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v22);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OobeNetworkReconnect");
    v23 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_26009dbace53a0139ffaa350e0fa0e60_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v23);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OobeRestoreDataLayer");
    v24 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_477ef49635ac701dbd6a43c70c3ea411_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v24);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AADPinResetV2");
    v25 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_c13826d959a6ba141992b170acde5880_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v25);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"DeviceMetaDataBackup");
    v26 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_12f4a3ed793d31ce59efafae4ae096ef_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v26);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"DeviceIntegrationPolicy");
    v27 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_aef81f2c45f2bf98bd66ed951a7d1ef0_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v27);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"WindowsAccountSyncConsent");
    v28 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_1718d430b8a9600027a39e47088cf06b_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v28);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Toggle_Control_Type_Accessibility");
    v29 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_1cf76399618d307a4ccec88a71234ba5_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v29);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Accessibility_Improvements");
    v30 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_2712dd3ae640ae05398635c6879a6e24_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v30);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OobeWindowsAccountSyncConsentPage");
    v31 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_e959759ed488906759b71214f75f1a88_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v31);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Narrator_Leaving_Dialog_In_Scan_Mode");
    v32 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_731b00807f7520a9c8ed51e1de5127ef_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v32);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Alert_Contrast_Mode_Accessibility");
    v33 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_8df75e7ef2ff52a869c98928656c710a_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v33);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_RetailDemoConfirmDlg_Narrator_Accessibility");
    v34 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_6644f1b5a475c9e66f31c81460bf3049_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v34);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Second_Confirmed_Dialog_Accessibility");
    v35 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_fa96a86a01c8c5797ee5e047245f09ad_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v35);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Entry_Dialog_Visibility_Accessibility");
    v36 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_00aa48edf1838241d999388370590371_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v36);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NodeCapabilityForNoInternetPage");
    v37 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_868ca358d6149100bc633d77e3dcabe5_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v37);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"Feature_Servicing_InternetDisconnectFix");
    v38 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_bcc3d78598305006d441df6358f71c21_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v38);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"SnapshotCapture");
    v39 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_17b78f64e672cc6c40e366390aed1d0d_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v39);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"SnapshotCaptureA9Oobe");
    v40 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_7511e9db4ed590841c92f22dfdba5dee_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v40);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"Feature_ExpeditedUpdatePILess");
    v41 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_7139a099002d2bf64b072bb021c48f4f_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v41);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OobeListViewKeyPressSearch");
    v42 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_4ff2ec8dc1ed76ebf622941d8584aa6f_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v42);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"BackNavigationToEulaPage");
    v43 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_0d9bfe41862185d9cd954a88e4726980_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v43);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NewMultiPagePrivacy");
    v44 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_d525eed58a049bc00f815de97c56a004_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v44);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"MissingMultiPagePrivacy");
    v45 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_02cc4ff0107a0bddfcbc2e73d5b54750_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v45);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"MissingAADCRegions");
    v46 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_dad56e5e11a715d697e681773f4b8591_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v46);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"FirstSignInSettings");
    v47 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_fbd89261e2fa96b42b1581c37d743865_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v47);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"MatsOnCancel");
    v48 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_35e6ec23bddfdf69a7e95714fbee592b_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v48);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OobeHostAppInDefaultUserSession");
    v49 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_b0af650990710446f895ef8023be4136_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v49);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"BlockRestrictedFlows");
    v50 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_6130bab15fe34183e66ce136a625dd54_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v50);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"DisableToggleOnArrowKeys");
    v51 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_dc1cca59e848e15f3c38304a4d299eb1_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v51);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"DeviceNameRebootMove");
    v52 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_1def4a3baea6e0ba7d6ec5123cdd7772_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v52);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OobeHelloNarrationFixOnConfirmation");
    v53 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_6645ec14c7da62e36dc7fbbbfaa0c312_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v53);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"PreloadCheckErrorHandling");
    v54 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_f68f654de58b21adca14fb4978d6efb6_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v54);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NDUPCSPBridgeAPI");
    v55 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_68840a367c7304fcc507f42ec494e204_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v55);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NDUPLanguageRemoval");
    v56 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_b318dddafa791fa8dd0f4a4786280bac_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v56);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NDUPLanguageRemovalV2");
    v57 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_000d214dbe3bf7c0ca584d66f9caefd5_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v57);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NDUPCtacTelemetry");
    v58 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_c0ccd63b6f13f0589fdd9113fee7143b_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v58);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OOBEDefaultFolderUserName");
    v59 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_0d38c5042bf7517da4764431b36fc87f_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v59);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NDUPDaysOutOfDate");
    v60 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_bceba5e39f75d4bdd48d36991ec097de_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v60);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RequestRawDA");
    v61 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_8cac1786bf9b9c9c2b6c7af3a7255ca2_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v61);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"WindowsAutopilotDiagnostics");
    v62 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_9fa2fb21623544f566e01e05ac6c479c_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v62);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotDevicePreparation");
    v63 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_290f827c14e8816fa17c6f6980f992cd_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v63);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotDeviceTagging");
    v64 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_2eda6340d208e14ebd65a44f9146c4e0_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v64);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotDppResilience");
    v65 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_1fb0194a3a2fbb27baab19a548efdfbd_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v65);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotDppRebootFix");
    v66 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_b5bad3fdec801ff31241746dd1e9a96c_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v66);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotClearUserEspCacheOnComplete");
    v67 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_aa6fda9604ba0cd95a65843c5ab4912c_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v67);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotPreprovisioningRedGreenBackground");
    v68 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_3d3afda7b974cf7d2fd99aab51df090d_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v68);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotBitlockerOobeDeferral");
    v69 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_cb3da1088ea903f7fca994bde5ee71a5_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v69);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotAcceptEula");
    v70 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_16ff01d09cd0a9fffad96290a099bba7_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v70);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotFastWindowsTelemetry");
    v71 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_1b4ec1cbd1ee6cb1a3e80c5c5039e4df_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v71);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AutopilotDppCrashRecovery");
    v72 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_eda9baab375b7eb7b610b9e60a17d529_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v72);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Override_Toggle_Accessibility");
    v73 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_bdb38c65622a0684143f327e3b52ab7e_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v73);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RDX_OOBE_Edit_Box_Control_Type_Accessibility");
    v74 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_1218a3b0d6265fe105918ee29e9166e3_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v74);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"ShellHostedApplication");
    v75 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_9eab95230724e06654655c1709fb5022_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v75);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"ShellHostedApplication_Wave2");
    v76 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_d52ab34904fc11b358c3391541d2088a_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v76);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"NdupWv2HostedApplication");
    v77 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_f0309d1d002cef42c983f724febd31e4_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v77);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"RecallConsentPage");
    v78 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_807dfd2c921b5a1c9e5c8a5d365a9132_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v78);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"ShowHelloPromptToEnableA9");
    v79 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_4cfb40ec3b67f4dc7cfeaa128e1aec45_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v79);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OOBEDeviceForm");
    v80 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_77801502a98030c9e48d390bc858de7d_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v80);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"GamepadLegendEnabled");
    v81 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_fb5f3877b58ef40dac9d08c09b0796f5_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v81);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"GamepadEnabledOobe");
    v82 = std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](v2, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_ae259f9620e2c9e65e954ad06129e4f9_,bool,>::`vftable';
    v121 = v120;
    std::_Func_class<bool,>::_Swap(v120, v82);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"AllowScoobeDeferralByUser");
    v83 = std::unordered_map<std::wstring,std::function<unsigned short (void)>>::operator[]((char *)this + 144, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_57b9ecbc2e246ab48e68950d299e03f8_,unsigned short,>::`vftable';
    v121 = v120;
    std::function<unsigned short (void)>::swap(v120, v83);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"FamilySettingsAwareness");
    v84 = std::unordered_map<std::wstring,std::function<unsigned short (void)>>::operator[]((char *)this + 144, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_7eb54353c7589c82a0e0184502ab768a_,unsigned short,>::`vftable';
    v121 = v120;
    std::function<unsigned short (void)>::swap(v120, v84);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"ShowBrowserOnScoobe");
    v85 = std::unordered_map<std::wstring,std::function<unsigned short (void)>>::operator[]((char *)this + 144, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_a756f85828aa7910fa677edd64b62614_,unsigned short,>::`vftable';
    v121 = v120;
    std::function<unsigned short (void)>::swap(v120, v85);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v119, L"OobeNetworkReconnect");
    v86 = std::unordered_map<std::wstring,std::function<unsigned short (void)>>::operator[]((char *)this + 144, v119);
    v120[0] = &std::_Func_impl_no_alloc<_lambda_5789e5644b9d2fca607c33503ce43203_,unsigned short,>::`vftable';
    v121 = v120;
    std::function<unsigned short (void)>::swap(v120, v86);
    std::_Func_class<unsigned int,>::_Tidy(v120);
    std::wstring::_Tidy_deallocate(v119);
    std::wstring::wstring(v120, L"AllowScoobeDeferralByUser");
    v87 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::function<unsigned int (void)>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::function<unsigned int (void)>>>,0>>::_Try_emplace<std::wstring,>(
                      (__int64)this + 208,
                      (__int64)v119,
                      (__int64)v120);
    v122[0] = &std::_Func_impl_no_alloc<_lambda_1b1ab0333ac87e188a3ab01b0e73fb21_,unsigned int,>::`vftable';
    v123 = v122;
    std::function<unsigned short (void)>::swap(v122, *v87 + 48LL);
    std::_Func_class<unsigned int,>::_Tidy(v122);
    std::wstring::_Tidy_deallocate(v120);
    std::wstring::wstring(v120, L"FamilySettingsAwareness");
    v88 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::function<unsigned int (void)>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::function<unsigned int (void)>>>,0>>::_Try_emplace<std::wstring,>(
                      (__int64)this + 208,
                      (__int64)v119,
                      (__int64)v120);
    v122[0] = &std::_Func_impl_no_alloc<_lambda_19c37cf9c1aa4e8f714c50fee6504934_,unsigned int,>::`vftable';
    v123 = v122;
    std::function<unsigned short (void)>::swap(v122, *v88 + 48LL);
    std::_Func_class<unsigned int,>::_Tidy(v122);
    std::wstring::_Tidy_deallocate(v120);
    std::wstring::wstring(v120, L"OobeNetworkReconnect");
    v89 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::function<unsigned int (void)>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::function<unsigned int (void)>>>,0>>::_Try_emplace<std::wstring,>(
                      (__int64)this + 208,
                      (__int64)v119,
                      (__int64)v120);
    v122[0] = &std::_Func_impl_no_alloc<_lambda_c9b89a7ae4367bcb778f76af24c7cb97_,unsigned int,>::`vftable';
    v123 = v122;
    std::function<unsigned short (void)>::swap(v122, *v89 + 48LL);
    std::_Func_class<unsigned int,>::_Tidy(v122);
    std::wstring::_Tidy_deallocate(v120);
    FeatureVariantUniqueIdentifier = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
                                       v90,
                                       v120,
                                       L"AllowScoobeDeferralByUser",
                                       1);
    v92 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, FeatureVariantUniqueIdentifier);
    std::wstring::operator=(v92, L"PostponeFromLink");
    std::wstring::_Tidy_deallocate(v120);
    v94 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
            v93,
            v120,
            L"FamilySettingsAwareness",
            1);
    v95 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v94);
    std::wstring::operator=(v95, L"AtFirstLogon_TextVariantA");
    std::wstring::_Tidy_deallocate(v120);
    v97 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
            v96,
            v120,
            L"FamilySettingsAwareness",
            2);
    v98 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v97);
    std::wstring::operator=(v98, L"AtNthLogon_TextVariantA");
    std::wstring::_Tidy_deallocate(v120);
    v100 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
             v99,
             v120,
             L"FamilySettingsAwareness",
             3);
    v101 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v100);
    std::wstring::operator=(v101, L"AtFirstLogon_TextVariantB");
    std::wstring::_Tidy_deallocate(v120);
    v103 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
             v102,
             v120,
             L"FamilySettingsAwareness",
             4);
    v104 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v103);
    std::wstring::operator=(v104, L"AtNthLogon_TextVariantB");
    std::wstring::_Tidy_deallocate(v120);
    v106 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
             v105,
             v120,
             L"FamilySettingsAwareness",
             5);
    v107 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v106);
    std::wstring::operator=(v107, L"AtFirstLogon_TextVariantC");
    std::wstring::_Tidy_deallocate(v120);
    v109 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
             v108,
             v120,
             L"FamilySettingsAwareness",
             6);
    v110 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v109);
    std::wstring::operator=(v110, L"AtNthLogon_TextVariantC");
    std::wstring::_Tidy_deallocate(v120);
    v112 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
             v111,
             v120,
             L"ShowBrowserOnScoobe",
             2);
    v113 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v112);
    std::wstring::operator=(v113, L"ShowBrowserAndSearchDefaults");
    std::wstring::_Tidy_deallocate(v120);
    v115 = CloudExperienceHostAPI::FeatureStaging::GetFeatureVariantUniqueIdentifier(
             v114,
             v120,
             L"OobeNetworkReconnect",
             1);
    v116 = std::unordered_map<std::wstring,std::wstring>::operator[]((char *)this + 272, v115);
    std::wstring::operator=(v116, L"UseCustomReconnectLimit");
    std::wstring::_Tidy_deallocate(v120);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA9,
                           (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\featurestaging.cpp",
                           v117);
  }
  return result;
}

```

## disassembly

```asm
0x18006d938  mov     [rsp+arg_8], rbx
0x18006d93d  mov     [rsp+arg_10], rdi
0x18006d942  push    r14
0x18006d944  sub     rsp, 0E0h
0x18006d94b  mov     rax, cs:__security_cookie
0x18006d952  xor     rax, rsp
0x18006d955  mov     [rsp+0E8h+var_18], rax
0x18006d95d  mov     rdi, rcx
0x18006d960  lea     rbx, [rcx+50h]
0x18006d964  lea     rdx, aRdxDisableadmi; "RDX_DisableAdminAccount"
0x18006d96b  lea     rcx, [rsp+0E8h+var_C0]
0x18006d970  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006d975  nop
0x18006d976  lea     rdx, [rsp+0E8h+var_C0]
0x18006d97b  mov     rcx, rbx
0x18006d97e  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006d983  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_469a36b6241b61294f91d284de3e935f_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_469a36b6241b61294f91d284de3e935f_,bool,>::`vftable'
0x18006d98a  mov     [rsp+0E8h+var_98], rcx
0x18006d98f  lea     rcx, [rsp+0E8h+var_98]
0x18006d994  mov     [rsp+0E8h+var_60], rcx
0x18006d99c  mov     rdx, rax
0x18006d99f  lea     rcx, [rsp+0E8h+var_98]
0x18006d9a4  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006d9a9  lea     rcx, [rsp+0E8h+var_98]
0x18006d9ae  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006d9b3  nop
0x18006d9b4  lea     rcx, [rsp+0E8h+var_C0]
0x18006d9b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d9be  lea     rdx, aRdxOobePasswor; "RDX_OOBE_Password_Label_Accessibility"
0x18006d9c5  lea     rcx, [rsp+0E8h+var_C0]
0x18006d9ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006d9cf  nop
0x18006d9d0  lea     rdx, [rsp+0E8h+var_C0]
0x18006d9d5  mov     rcx, rbx
0x18006d9d8  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006d9dd  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_4258fa28ef4e40684a6c8fec333b5c9e_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_4258fa28ef4e40684a6c8fec333b5c9e_,bool,>::`vftable'
0x18006d9e4  mov     [rsp+0E8h+var_98], rcx
0x18006d9e9  lea     rcx, [rsp+0E8h+var_98]
0x18006d9ee  mov     [rsp+0E8h+var_60], rcx
0x18006d9f6  mov     rdx, rax
0x18006d9f9  lea     rcx, [rsp+0E8h+var_98]
0x18006d9fe  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006da03  lea     rcx, [rsp+0E8h+var_98]
0x18006da08  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006da0d  nop
0x18006da0e  lea     rcx, [rsp+0E8h+var_C0]
0x18006da13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006da18  lea     rdx, aRdxTimedshutdo; "RDX_TimedShutdown"
0x18006da1f  lea     rcx, [rsp+0E8h+var_C0]
0x18006da24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006da29  nop
0x18006da2a  lea     rdx, [rsp+0E8h+var_C0]
0x18006da2f  mov     rcx, rbx
0x18006da32  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006da37  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_a8bab2242e7f8d9f688f8b48feb40940_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a8bab2242e7f8d9f688f8b48feb40940_,bool,>::`vftable'
0x18006da3e  mov     [rsp+0E8h+var_98], rcx
0x18006da43  lea     rcx, [rsp+0E8h+var_98]
0x18006da48  mov     [rsp+0E8h+var_60], rcx
0x18006da50  mov     rdx, rax
0x18006da53  lea     rcx, [rsp+0E8h+var_98]
0x18006da58  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006da5d  lea     rcx, [rsp+0E8h+var_98]
0x18006da62  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006da67  nop
0x18006da68  lea     rcx, [rsp+0E8h+var_C0]
0x18006da6d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006da72  lea     rdx, aRdxOoberacvali; "RDX_OOBERACValidation"
0x18006da79  lea     rcx, [rsp+0E8h+var_C0]
0x18006da7e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006da83  nop
0x18006da84  lea     rdx, [rsp+0E8h+var_C0]
0x18006da89  mov     rcx, rbx
0x18006da8c  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006da91  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_a31f93e1fbebc29a7ba6c40ce2767b60_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a31f93e1fbebc29a7ba6c40ce2767b60_,bool,>::`vftable'
0x18006da98  mov     [rsp+0E8h+var_98], rcx
0x18006da9d  lea     rcx, [rsp+0E8h+var_98]
0x18006daa2  mov     [rsp+0E8h+var_60], rcx
0x18006daaa  mov     rdx, rax
0x18006daad  lea     rcx, [rsp+0E8h+var_98]
0x18006dab2  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006dab7  lea     rcx, [rsp+0E8h+var_98]
0x18006dabc  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006dac1  nop
0x18006dac2  lea     rcx, [rsp+0E8h+var_C0]
0x18006dac7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dacc  lea     rdx, aRdxOobeKeyboar; "RDX_OOBE_Keyboard_Focus_Accessibility"
0x18006dad3  lea     rcx, [rsp+0E8h+var_C0]
0x18006dad8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dadd  nop
0x18006dade  lea     rdx, [rsp+0E8h+var_C0]
0x18006dae3  mov     rcx, rbx
0x18006dae6  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006daeb  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_264ea4da06fa5803825cd78d135b207f_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_264ea4da06fa5803825cd78d135b207f_,bool,>::`vftable'
0x18006daf2  mov     [rsp+0E8h+var_98], rcx
0x18006daf7  lea     rcx, [rsp+0E8h+var_98]
0x18006dafc  mov     [rsp+0E8h+var_60], rcx
0x18006db04  mov     rdx, rax
0x18006db07  lea     rcx, [rsp+0E8h+var_98]
0x18006db0c  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006db11  lea     rcx, [rsp+0E8h+var_98]
0x18006db16  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006db1b  nop
0x18006db1c  lea     rcx, [rsp+0E8h+var_C0]
0x18006db21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006db26  lea     rdx, aRdxOobeLinkHov; "RDX_OOBE_Link_Hover_Accessibility"
0x18006db2d  lea     rcx, [rsp+0E8h+var_C0]
0x18006db32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006db37  nop
0x18006db38  lea     rdx, [rsp+0E8h+var_C0]
0x18006db3d  mov     rcx, rbx
0x18006db40  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006db45  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_a8597fa3967f52e5cf3d83635fdcb114_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a8597fa3967f52e5cf3d83635fdcb114_,bool,>::`vftable'
0x18006db4c  mov     [rsp+0E8h+var_98], rcx
0x18006db51  lea     rcx, [rsp+0E8h+var_98]
0x18006db56  mov     [rsp+0E8h+var_60], rcx
0x18006db5e  mov     rdx, rax
0x18006db61  lea     rcx, [rsp+0E8h+var_98]
0x18006db66  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006db6b  lea     rcx, [rsp+0E8h+var_98]
0x18006db70  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006db75  nop
0x18006db76  lea     rcx, [rsp+0E8h+var_C0]
0x18006db7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006db80  lea     rdx, aRdxOobeNarrato; "RDX_OOBE_Narrator_ScanMode_Activation_A"...
0x18006db87  lea     rcx, [rsp+0E8h+var_C0]
0x18006db8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006db91  nop
0x18006db92  lea     rdx, [rsp+0E8h+var_C0]
0x18006db97  mov     rcx, rbx
0x18006db9a  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006db9f  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_667d2c25b64fbecb1d88ab5f45275c50_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_667d2c25b64fbecb1d88ab5f45275c50_,bool,>::`vftable'
0x18006dba6  mov     [rsp+0E8h+var_98], rcx
0x18006dbab  lea     rcx, [rsp+0E8h+var_98]
0x18006dbb0  mov     [rsp+0E8h+var_60], rcx
0x18006dbb8  mov     rdx, rax
0x18006dbbb  lea     rcx, [rsp+0E8h+var_98]
0x18006dbc0  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006dbc5  lea     rcx, [rsp+0E8h+var_98]
0x18006dbca  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006dbcf  nop
0x18006dbd0  lea     rcx, [rsp+0E8h+var_C0]
0x18006dbd5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dbda  lea     rdx, aScoobeactivity; "ScoobeActivitySyncConsent"
0x18006dbe1  lea     rcx, [rsp+0E8h+var_C0]
0x18006dbe6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dbeb  nop
0x18006dbec  lea     rdx, [rsp+0E8h+var_C0]
0x18006dbf1  mov     rcx, rbx
0x18006dbf4  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dbf9  mov     rcx, rax
0x18006dbfc  call    ??$?4V_lambda_27e6d86ac1c57032c9c385d67e49964f_@@$0A@@?$function@$$A6A_NXZ@std@@QEAAAEAV01@$$QEAV_lambda_27e6d86ac1c57032c9c385d67e49964f_@@@Z; std::function<bool (void)>::operator=<_lambda_27e6d86ac1c57032c9c385d67e49964f_,0>(_lambda_27e6d86ac1c57032c9c385d67e49964f_ &&)
0x18006dc01  nop
0x18006dc02  lea     rcx, [rsp+0E8h+var_C0]
0x18006dc07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dc0c  lea     rdx, aTokenbasedraau; "TokenBasedRAAuth"
0x18006dc13  lea     rcx, [rsp+0E8h+var_C0]
0x18006dc18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dc1d  nop
0x18006dc1e  lea     rdx, [rsp+0E8h+var_C0]
0x18006dc23  mov     rcx, rbx
0x18006dc26  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dc2b  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_c766a9467d5f1676226ab22c7e45022e_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_c766a9467d5f1676226ab22c7e45022e_,bool,>::`vftable'
0x18006dc32  mov     [rsp+0E8h+var_98], rcx
0x18006dc37  lea     rcx, [rsp+0E8h+var_98]
0x18006dc3c  mov     [rsp+0E8h+var_60], rcx
0x18006dc44  mov     rdx, rax
0x18006dc47  lea     rcx, [rsp+0E8h+var_98]
0x18006dc4c  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006dc51  lea     rcx, [rsp+0E8h+var_98]
0x18006dc56  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006dc5b  nop
0x18006dc5c  lea     rcx, [rsp+0E8h+var_C0]
0x18006dc61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dc66  lea     rdx, aAllowscoobedef; "AllowScoobeDeferralByUser"
0x18006dc6d  lea     rcx, [rsp+0E8h+var_C0]
0x18006dc72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dc77  nop
0x18006dc78  lea     rdx, [rsp+0E8h+var_C0]
0x18006dc7d  mov     rcx, rbx
0x18006dc80  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dc85  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_dfdbe4c277571d0898db5f8c54c9fa48_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_dfdbe4c277571d0898db5f8c54c9fa48_,bool,>::`vftable'
0x18006dc8c  mov     [rsp+0E8h+var_98], rcx
0x18006dc91  lea     rcx, [rsp+0E8h+var_98]
0x18006dc96  mov     [rsp+0E8h+var_60], rcx
0x18006dc9e  mov     rdx, rax
0x18006dca1  lea     rcx, [rsp+0E8h+var_98]
0x18006dca6  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006dcab  lea     rcx, [rsp+0E8h+var_98]
0x18006dcb0  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006dcb5  nop
0x18006dcb6  lea     rcx, [rsp+0E8h+var_C0]
0x18006dcbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dcc0  lea     rdx, aOoberestoreflo; "OOBERestoreFlowControlforAAD"
0x18006dcc7  lea     rcx, [rsp+0E8h+var_C0]
0x18006dccc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dcd1  nop
0x18006dcd2  lea     rdx, [rsp+0E8h+var_C0]
0x18006dcd7  mov     rcx, rbx
0x18006dcda  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dcdf  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_a1b4bc2ea0a35115f39864495e2fd2d9_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a1b4bc2ea0a35115f39864495e2fd2d9_,bool,>::`vftable'
0x18006dce6  mov     [rsp+0E8h+var_98], rcx
0x18006dceb  lea     rcx, [rsp+0E8h+var_98]
0x18006dcf0  mov     [rsp+0E8h+var_60], rcx
0x18006dcf8  mov     rdx, rax
0x18006dcfb  lea     rcx, [rsp+0E8h+var_98]
0x18006dd00  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006dd05  lea     rcx, [rsp+0E8h+var_98]
0x18006dd0a  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006dd0f  nop
0x18006dd10  lea     rcx, [rsp+0E8h+var_C0]
0x18006dd15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dd1a  lea     rdx, aCommercialbroo; "CommercialBrOOBETelemetry"
0x18006dd21  lea     rcx, [rsp+0E8h+var_C0]
0x18006dd26  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dd2b  nop
0x18006dd2c  lea     rdx, [rsp+0E8h+var_C0]
0x18006dd31  mov     rcx, rbx
0x18006dd34  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dd39  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_052ea036cb479800503aa7f86787a2ce_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052ea036cb479800503aa7f86787a2ce_,bool,>::`vftable'
0x18006dd40  mov     [rsp+0E8h+var_98], rcx
0x18006dd45  lea     rcx, [rsp+0E8h+var_98]
0x18006dd4a  mov     [rsp+0E8h+var_60], rcx
0x18006dd52  mov     rdx, rax
0x18006dd55  lea     rcx, [rsp+0E8h+var_98]
0x18006dd5a  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006dd5f  lea     rcx, [rsp+0E8h+var_98]
0x18006dd64  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006dd69  nop
0x18006dd6a  lea     rcx, [rsp+0E8h+var_C0]
0x18006dd6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006dd74  lea     rdx, aFsirRestoreapi; "FSIR_RestoreApi"
0x18006dd7b  lea     rcx, [rsp+0E8h+var_C0]
0x18006dd80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dd85  nop
0x18006dd86  lea     rdx, [rsp+0E8h+var_C0]
0x18006dd8b  mov     rcx, rbx
0x18006dd8e  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dd93  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_b00d941e9471b25c5a338deaec10fe98_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_b00d941e9471b25c5a338deaec10fe98_,bool,>::`vftable'
0x18006dd9a  mov     [rsp+0E8h+var_98], rcx
0x18006dd9f  lea     rcx, [rsp+0E8h+var_98]
0x18006dda4  mov     [rsp+0E8h+var_60], rcx
0x18006ddac  mov     rdx, rax
0x18006ddaf  lea     rcx, [rsp+0E8h+var_98]
0x18006ddb4  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006ddb9  lea     rcx, [rsp+0E8h+var_98]
0x18006ddbe  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006ddc3  nop
0x18006ddc4  lea     rcx, [rsp+0E8h+var_C0]
0x18006ddc9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ddce  lea     rdx, aFsirWamauth; "FSIR_WamAuth"
0x18006ddd5  lea     rcx, [rsp+0E8h+var_C0]
0x18006ddda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006dddf  nop
0x18006dde0  lea     rdx, [rsp+0E8h+var_C0]
0x18006dde5  mov     rcx, rbx
0x18006dde8  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dded  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_cdb8740ed341e212f9a5b6e00d3325d6_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_cdb8740ed341e212f9a5b6e00d3325d6_,bool,>::`vftable'
0x18006ddf4  mov     [rsp+0E8h+var_98], rcx
0x18006ddf9  lea     rcx, [rsp+0E8h+var_98]
0x18006ddfe  mov     [rsp+0E8h+var_60], rcx
0x18006de06  mov     rdx, rax
0x18006de09  lea     rcx, [rsp+0E8h+var_98]
0x18006de0e  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006de13  lea     rcx, [rsp+0E8h+var_98]
0x18006de18  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006de1d  nop
0x18006de1e  lea     rcx, [rsp+0E8h+var_C0]
0x18006de23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006de28  lea     rdx, aGetmicrosoften; "GetMicrosoftEntraTenantId"
0x18006de2f  lea     rcx, [rsp+0E8h+var_C0]
0x18006de34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006de39  nop
0x18006de3a  lea     rdx, [rsp+0E8h+var_C0]
0x18006de3f  mov     rcx, rbx
0x18006de42  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006de47  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_d34c1a63b0266c6d7e8b34700b09ddb9_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d34c1a63b0266c6d7e8b34700b09ddb9_,bool,>::`vftable'
0x18006de4e  mov     [rsp+0E8h+var_98], rcx
0x18006de53  lea     rcx, [rsp+0E8h+var_98]
0x18006de58  mov     [rsp+0E8h+var_60], rcx
0x18006de60  mov     rdx, rax
0x18006de63  lea     rcx, [rsp+0E8h+var_98]
0x18006de68  call    ?_Swap@?$_Func_class@_N$$V@std@@IEAAXAEAV12@@Z; std::_Func_class<bool,>::_Swap(std::_Func_class<bool,> &)
0x18006de6d  lea     rcx, [rsp+0E8h+var_98]
0x18006de72  call    ?_Tidy@?$_Func_class@I$$V@std@@IEAAXXZ; std::_Func_class<uint,>::_Tidy(void)
0x18006de77  nop
0x18006de78  lea     rcx, [rsp+0E8h+var_C0]
0x18006de7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006de82  lea     rdx, aRestorecspintu; "RestoreCSPIntuneReporting"
0x18006de89  lea     rcx, [rsp+0E8h+var_C0]
0x18006de8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006de93  nop
0x18006de94  lea     rdx, [rsp+0E8h+var_C0]
0x18006de99  mov     rcx, rbx
0x18006de9c  call    ??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6A_NXZ@2@@std@@@2@@std@@QEAAAEAV?$function@$$A6A_NXZ@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::unordered_map<std::wstring,std::function<bool (void)>>::operator[](std::wstring &&)
0x18006dea1  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_fb11beed06a479a7290b6c88b8c21ea6_@@_N$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_fb11beed06a479a7290b6c88b8c21ea6_,bool,>::`vftable'
0x18006dea8  mov     [rsp+0E8h+var_98], rcx
0x18006dead  lea     rcx, [rsp+0E8h+var_98]
0x18006deb2  mov     [rsp+0E8h+var_60], rcx
0x18006deba  mov     rdx, rax
0x18006debd  lea     rcx, [rsp+0E8h+var_98]
  ... truncated ...
```
