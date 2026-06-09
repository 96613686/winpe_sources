# Windows::WU::WuUpdateInternalImpl::RunInstall(wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy> const &,std::function<void (ProgressCallbackData)> const &,Windows::WU::InstallProperties const &,bool)

- ea: `0x1402e7e5c`
- end: `0x1402e96ea`
- name: `?RunInstall@WuUpdateInternalImpl@WU@Windows@@AEAA?AV?$optional@V?$vector@UInstallResult@WU@Windows@@V?$allocator@UInstallResult@WU@Windows@@@std@@@std@@@std@@AEBV?$com_ptr_t@UIUpdateCollection@@Uerr_exception_policy@wil@@@wil@@AEBV?$function@$$A6AXUProgressCallbackData@@@Z@5@AEBUInstallProperties@23@_N@Z`
- size: `6286`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1402e9730`

## callees

- `0x140024de0`
- `0x140028864`
- `0x140028fa4`
- `0x14003ff28`
- `0x1400413a8`
- `0x140042d04`
- `0x140043284`
- `0x140043814`
- `0x1400447ac`
- `0x140045404`
- `0x1400722b4`
- `0x1400a5558`
- `0x1400a6f74`
- `0x1400c695c`
- `0x1400c7528`
- `0x1400c75e4`
- `0x140102bc8`
- `0x14012a810`
- `0x14012d7d8`
- `0x14012d864`
- `0x14016bf24`
- `0x140183608`
- `0x1402b310c`
- `0x1402dab04`
- `0x1402dab40`
- `0x1402db704`
- `0x1402e7e5c`
- `0x1402ea718`
- `0x1402eba90`
- `0x1402ec95c`
- `0x1402ed250`
- `0x1402ed78c`
- `0x1403742a4`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1402e8c37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1402e8d83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1402e8c37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1402e8d83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1402e8cd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1402e8db1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1402e8cd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1402e8db1`
- `OLEAUT32!__imp_SysFreeString` at `0x1402e898b`
- `OLEAUT32!__imp_SysFreeString` at `0x1402e899f`
- `OLEAUT32!__imp_SysFreeString` at `0x1402e91e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1402e898b`
- `OLEAUT32!__imp_SysFreeString` at `0x1402e899f`
- `OLEAUT32!__imp_SysFreeString` at `0x1402e91e8`
- `OLEAUT32!__imp_SysStringLen` at `0x1402e8046`
- `OLEAUT32!__imp_SysStringLen` at `0x1402e8046`
- `OLEAUT32!__imp_VariantInit` at `0x1402e7f49`
- `OLEAUT32!__imp_VariantInit` at `0x1402e8321`
- `OLEAUT32!__imp_VariantInit` at `0x1402e8a5e`
- `OLEAUT32!__imp_VariantInit` at `0x1402e8b3b`
- `OLEAUT32!__imp_VariantInit` at `0x1402e7f49`
- `OLEAUT32!__imp_VariantInit` at `0x1402e8321`
- `OLEAUT32!__imp_VariantInit` at `0x1402e8a5e`
- `OLEAUT32!__imp_VariantInit` at `0x1402e8b3b`
- `OLEAUT32!__imp_VariantClear` at `0x1402e7fd6`
- `OLEAUT32!__imp_VariantClear` at `0x1402e81b0`
- `OLEAUT32!__imp_VariantClear` at `0x1402e822f`
- `OLEAUT32!__imp_VariantClear` at `0x1402e839b`
- `OLEAUT32!__imp_VariantClear` at `0x1402e843d`
- `OLEAUT32!__imp_VariantClear` at `0x1402e8b2d`
- `OLEAUT32!__imp_VariantClear` at `0x1402e8ded`
- `OLEAUT32!__imp_VariantClear` at `0x1402e949d`
- `OLEAUT32!__imp_VariantClear` at `0x1402e7fd6`
- `OLEAUT32!__imp_VariantClear` at `0x1402e81b0`
- `OLEAUT32!__imp_VariantClear` at `0x1402e822f`
- `OLEAUT32!__imp_VariantClear` at `0x1402e839b`
- `OLEAUT32!__imp_VariantClear` at `0x1402e843d`
- `OLEAUT32!__imp_VariantClear` at `0x1402e8b2d`
- `OLEAUT32!__imp_VariantClear` at `0x1402e8ded`
- `OLEAUT32!__imp_VariantClear` at `0x1402e949d`

## string_xrefs

- `0x1402e953e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402e9583`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402e95cb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402e963b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402e96b6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402e8019`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e8235`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e870e`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e9529`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e9559`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e956e`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e8a72`: `preInstallOperationModeBestEffort`
- `0x1402e8ab2`: `preInstallOperationModeSkip`
- `0x1402e8a92`: `preInstallOperationModeStrict`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
__int64 __fastcall Windows::WU::WuUpdateInternalImpl::RunInstall(
        __int64 **this,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        struct Windows::WU::InstallProperties *a5,
        char a6)
{
  Windows::WU::WuUpdateInternalImpl *v6; // r13
  struct Windows::WU::InstallProperties *v7; // rdi
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // r12d
  int v13; // eax
  __int64 v14; // r8
  char *v15; // rax
  __int64 v16; // r8
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, __int64, VARIANTARG *); // r14
  _QWORD *v19; // rdx
  int v20; // eax
  __int64 v21; // rcx
  char **v22; // rax
  char *v23; // rbx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 (__fastcall *v27)(__int64, __int64, VARIANTARG *); // r9
  int v28; // eax
  char *v29; // r15
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  unsigned int v33; // r12d
  int v34; // eax
  int v35; // eax
  __int64 System; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rax
  char v39; // bl
  int v40; // eax
  _QWORD *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdi
  void (__fastcall *v46)(__int64, __int64 (__fastcall ***)(), char **); // rbx
  const char *v47; // r9
  _QWORD *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 (__fastcall *v51)(__int64, VARIANTARG *, VARIANTARG *); // r9
  __int128 *v52; // rax
  _QWORD *v53; // rax
  int v54; // eax
  _QWORD *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 (__fastcall *v58)(__int64, __int64 (__fastcall ***)(), VARIANTARG *); // r9
  __int128 *v59; // rax
  _QWORD *v60; // rax
  int v61; // eax
  _OWORD *v62; // rax
  char *v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r8
  __int64 v66; // r8
  int v67; // eax
  __int64 v68; // rax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  int v72; // r12d
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rdx
  char v76; // bl
  __int64 v77; // rcx
  __int64 v78; // rbx
  __int64 v79; // rax
  int v80; // eax
  int v81; // eax
  int v82; // eax
  unsigned int v83; // ebx
  __int64 v84; // rax
  int v85; // eax
  int v86; // eax
  int v87; // eax
  int v88; // eax
  int v89; // eax
  int v90; // eax
  BSTR v91; // rcx
  int v92; // eax
  char *v93; // rbx
  __int64 (__fastcall *v94)(char *, __int64); // rdi
  __int64 v95; // rdx
  int v96; // eax
  OLECHAR *v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rdx
  char v100; // al
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // r8
  int v106; // [rsp+20h] [rbp-238h]
  int v107; // [rsp+20h] [rbp-238h]
  int v108; // [rsp+20h] [rbp-238h]
  char *v109; // [rsp+30h] [rbp-228h]
  __int16 v110; // [rsp+40h] [rbp-218h]
  __int128 v112; // [rsp+50h] [rbp-208h]
  __int128 v113; // [rsp+50h] [rbp-208h]
  __int128 v114; // [rsp+50h] [rbp-208h]
  __int128 v115; // [rsp+50h] [rbp-208h]
  char *v116[2]; // [rsp+60h] [rbp-1F8h] BYREF
  _QWORD *v117; // [rsp+70h] [rbp-1E8h]
  VARIANTARG v118; // [rsp+80h] [rbp-1D8h] BYREF
  __int64 v119; // [rsp+98h] [rbp-1C0h]
  struct Windows::WU::InstallProperties *v120; // [rsp+A0h] [rbp-1B8h]
  __int64 v121; // [rsp+A8h] [rbp-1B0h]
  __int128 v122; // [rsp+B0h] [rbp-1A8h] BYREF
  _QWORD v123[2]; // [rsp+C0h] [rbp-198h] BYREF
  _BYTE v124[16]; // [rsp+D0h] [rbp-188h] BYREF
  char *v125; // [rsp+E0h] [rbp-178h]
  __int16 v126[2]; // [rsp+E8h] [rbp-170h] BYREF
  __int16 v127; // [rsp+ECh] [rbp-16Ch] BYREF
  __int64 v128; // [rsp+F0h] [rbp-168h] BYREF
  _QWORD *v129; // [rsp+F8h] [rbp-160h] BYREF
  BSTR v130; // [rsp+100h] [rbp-158h] BYREF
  char *v131; // [rsp+108h] [rbp-150h] BYREF
  BSTR bstrString[2]; // [rsp+110h] [rbp-148h] BYREF
  int v133[2]; // [rsp+120h] [rbp-138h] BYREF
  VARIANTARG pvarg; // [rsp+130h] [rbp-128h] BYREF
  char *v135; // [rsp+150h] [rbp-108h] BYREF
  __int64 v136; // [rsp+158h] [rbp-100h] BYREF
  int v137; // [rsp+160h] [rbp-F8h] BYREF
  Windows::WU::WuUpdateInternalImpl *v138; // [rsp+168h] [rbp-F0h] BYREF
  __int64 *v139; // [rsp+170h] [rbp-E8h] BYREF
  __int128 v140; // [rsp+178h] [rbp-E0h] BYREF
  __int64 v141; // [rsp+188h] [rbp-D0h]
  __int128 v142; // [rsp+190h] [rbp-C8h] BYREF
  __int64 v143; // [rsp+1A0h] [rbp-B8h]
  unsigned __int64 v144; // [rsp+1A8h] [rbp-B0h]
  char v145; // [rsp+1B0h] [rbp-A8h]
  __int64 (__fastcall **v146)(); // [rsp+1B8h] [rbp-A0h] BYREF
  __int128 v147; // [rsp+1C0h] [rbp-98h]
  __int128 v148; // [rsp+1D0h] [rbp-88h] BYREF
  __int128 v149; // [rsp+1E0h] [rbp-78h]
  __int64 (__fastcall ***v150)(); // [rsp+1F0h] [rbp-68h]
  VARIANTARG v151; // [rsp+1F8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v117 = a3;
  v121 = a2;
  v6 = (Windows::WU::WuUpdateInternalImpl *)this;
  v138 = (Windows::WU::WuUpdateInternalImpl *)this;
  v123[0] = a2;
  v7 = a5;
  v120 = a5;
  v129 = 0;
  v8 = this[14];
  v9 = *v8;
  v129 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD **))(v9 + 112))(v8, &v129);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3EA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v10,
      v106);
  v136 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v129)(
          v129,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v136);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v11,
      v106);
  v12 = 64;
  if ( *((_BYTE *)v6 + 12) )
  {
    VariantInit(&pvarg);
    pvarg.vt = 19;
    if ( !*((_BYTE *)v6 + 12) )
      std::_Throw_bad_optional_access();
    pvarg.lVal = *((_DWORD *)v6 + 2) != 1 ? 2 : 0;
    v118 = pvarg;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v136 + 32LL))(v136, 327691, &v118);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F6,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v13,
        v106);
    VariantClear(&pvarg);
  }
  if ( *((_QWORD *)a5 + 8) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) )
    {
      Windows::WU::WuUpdateInternalImpl::InternalProperty(v6, &pvarg, 4);
      if ( pvarg.vt != 8 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3FE,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)0x8024A215LL,
          v106);
      LOBYTE(v106) = SysStringLen(pvarg.bstrVal) == 0;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x3FF,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)0x80070057LL,
        v106,
        (bool)"Session data is empty",
        v109);
      v131 = (char *)a5 + 48;
      if ( *((_QWORD *)a5 + 9) > 7u )
        v131 = (char *)*((_QWORD *)a5 + 6);
      v142 = 0;
      v143 = 0;
      v144 = 0;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(pvarg.llVal + 2 * v14) );
      std::wstring::_Construct<1,wchar_t const *>(&v142, pvarg.llVal, v14);
      v15 = (char *)&v142;
      if ( v144 > 7 )
        v15 = (char *)v142;
      v116[0] = v15;
      memset(&v118, 0, sizeof(v118));
      v119 = 0;
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(pvarg.llVal + 2 * v16) );
      std::wstring::_Construct<1,wchar_t const *>(&v118, pvarg.llVal, v16);
      LOBYTE(v107) = std::operator==<wchar_t>(&v118, (char *)a5 + 48) ^ 1;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x400,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)0x80070057LL,
        v107,
        (bool)"Session data mismatch %s does not equal %s",
        v116[0]);
      std::wstring::~wstring(&v118);
      std::wstring::~wstring(&v142);
      VariantClear(&pvarg);
    }
    else
    {
      v17 = v136;
      v18 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v136 + 32LL);
      v19 = (_QWORD *)((char *)a5 + 48);
      if ( *((_QWORD *)a5 + 9) > 7u )
        v19 = (_QWORD *)*v19;
      pvarg = *(VARIANTARG *)wil::make_variant_bstr(&v118, v19);
      v20 = v18(v17, 327684, &pvarg);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x404,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v20,
          v106);
      VariantClear(&v118);
    }
  }
  v21 = *((_QWORD *)a5 + 4);
  if ( v21 )
  {
    v22 = (char **)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v21 + 8LL))(v21, v116);
  }
  else
  {
    BYTE4(v116[0]) = 0;
    v22 = v116;
  }
  v23 = *v22;
  if ( (unsigned __int8)BYTE4(*v22) && *((_BYTE *)a5 + 84) && !a6 )
  {
    bstrString[0] = 0;
    v24 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, BSTR *))*v129)(
            v129,
            &GUID_83e4294c_e0bb_4e62_ac48_00f226021136,
            bstrString);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v24,
        v106);
    v12 = 320;
    v25 = (*(__int64 (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)bstrString[0] + 24LL))(bstrString[0], (unsigned int)v23);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x40E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v25,
        v106);
    if ( bstrString[0] )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString[0] + 16LL))(bstrString[0]);
  }
  VariantInit(&pvarg);
  pvarg.vt = 19;
  pvarg.lVal = 1;
  v118 = pvarg;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v136 + 32LL))(v136, 327687, &v118);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v26,
      v106);
  VariantClear(&pvarg);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl) )
  {
    v27 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v136 + 32LL);
    pvarg.vt = 11;
    pvarg.iVal = -(*((_BYTE *)a5 + 87) != 0);
    v118 = pvarg;
    v28 = v27(v136, 327692, &v118);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x41C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v28,
        v106);
    VariantClear(&pvarg);
  }
  v29 = (char *)operator new(0x30u);
  v135 = v29;
  *(_OWORD *)v29 = 0;
  *((_OWORD *)v29 + 1) = 0;
  *((_OWORD *)v29 + 2) = 0;
  v30 = 0;
  v31 = 0;
  v32 = *((_QWORD *)v6 + 3);
  if ( v32 )
  {
    v30 = *((_QWORD *)v6 + 2);
    v31 = *((_QWORD *)v6 + 3);
    _InterlockedIncrement((volatile signed __int32 *)(v32 + 12));
  }
  *(_QWORD *)v29 = &Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>::`vftable'{for `IInstallationProgressChangedCallback'};
  v131 = v29 + 8;
  *((_QWORD *)v29 + 1) = &Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>::`vftable'{for `IInstallationCompletedCallback'};
  *((_WORD *)v29 + 8) = 0;
  *((_QWORD *)v29 + 3) = v30;
  *((_QWORD *)v29 + 4) = v31;
  *((_DWORD *)v29 + 10) = 0;
  v125 = v29;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 8LL))(v29);
  v33 = v12 & 0xFFFFFFFE;
  v34 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v129 + 128LL))(v129, *v117);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x421,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v34,
      v106);
  if ( *((_BYTE *)a5 + 85) )
  {
    v35 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v129 + 80LL))(v129, 0xFFFFFFFFLL);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v35,
        v106);
  }
  if ( !*((_BYTE *)a5 + 86)
    || (System = SystemInterface::Providers::GetSystem(bstrString),
        v37 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL),
        v38 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v37 + 88LL))(v37, v116),
        v33 |= 6u,
        v39 = 1,
        !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v38 + 32LL))(*v38)) )
  {
    v39 = 0;
  }
  if ( (v33 & 4) != 0 )
  {
    v33 &= ~4u;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v116);
  }
  if ( (v33 & 2) != 0 )
  {
    v33 &= ~2u;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(bstrString);
  }
  if ( v39 )
  {
    v128 = 0;
    v40 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v129)(
            v129,
            &GUID_885e76f6_f7c1_4869_951a_97613c8caef7,
            &v128);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v40,
        v106);
    v33 |= 0x80u;
    v41 = (_QWORD *)SystemInterface::Service::GetSystem(v124);
    v116[0] = (char *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v41 + 160LL))(*v41);
    Windows::Version::to_wstring(&v142, v116);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v124);
    v42 = SystemInterface::Providers::GetSystem(&v118);
    v43 = *(_QWORD *)v42 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v42 + 8LL) + 4LL);
    v44 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v43 + 40LL))(v43, &v122);
    v45 = *(_QWORD *)v44;
    v46 = *(void (__fastcall **)(__int64, __int64 (__fastcall ***)(), char **))(**(_QWORD **)v44 + 32LL);
    *(_OWORD *)v116 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                   &pvarg,
                                   L"OfframpOsVersion");
    v46(v45, &v146, v116);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v122);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v118);
    if ( (_BYTE)v149 )
    {
      try
      {
        if ( BYTE8(v148) != 2 )
          std::_Throw_bad_variant_access();
        std::wstring::operator=(&v142);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x437,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          v47);
        v29 = v135;
        v6 = v138;
        v121 = v123[0];
        v117 = a3;
      }
    }
    v7 = v120;
    if ( (_BYTE)v149 && SBYTE8(v148) != -1 && BYTE8(v148) && SBYTE8(v148) != 1 )
      std::wstring::~wstring(&v146);
    v130 = 0;
    v48 = (_QWORD *)SystemInterface::Service::GetSystem(v123);
    v49 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v48 + 64LL))(*v48, &v122);
    v50 = *(_QWORD *)v49;
    v51 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, VARIANTARG *))(**(_QWORD **)v49 + 128LL);
    v52 = &v142;
    if ( v144 > 7 )
      v52 = (__int128 *)v142;
    *(_QWORD *)&v112 = v52;
    *((_QWORD *)&v112 + 1) = v143;
    *(_OWORD *)&v118.vt = v112;
    v53 = (_QWORD *)v51(v50, &pvarg, &v118);
    if ( v53[3] > 7u )
      v53 = (_QWORD *)*v53;
    wil::make_bstr(&v130, v53);
    std::wstring::~wstring(&pvarg);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v122);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v123);
    v54 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR))(*(_QWORD *)v128 + 56LL))(v128, 2, v130);
    if ( v54 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v54,
        v106);
    bstrString[0] = 0;
    v55 = (_QWORD *)SystemInterface::Service::GetSystem(v116);
    v56 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v55 + 64LL))(*v55, v124);
    v57 = *(_QWORD *)v56;
    v58 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(), VARIANTARG *))(**(_QWORD **)v56 + 136LL);
    v59 = &v142;
    if ( v144 > 7 )
      v59 = (__int128 *)v142;
    *(_QWORD *)&v113 = v59;
    *((_QWORD *)&v113 + 1) = v143;
    *(_OWORD *)&v118.vt = v113;
    v60 = (_QWORD *)v58(v57, &v146, &v118);
    if ( v60[3] > 7u )
      v60 = (_QWORD *)*v60;
    wil::make_bstr(bstrString, v60);
    std::wstring::~wstring(&v146);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v124);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v116);
    v61 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR))(*(_QWORD *)v128 + 56LL))(v128, 3, bstrString[0]);
    if ( v61 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x440,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v61,
        v106);
    if ( bstrString[0] )
      SysFreeString(bstrString[0]);
    if ( v130 )
      SysFreeString(v130);
    std::wstring::~wstring(&v142);
    if ( v128 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
  {
    v62 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&pvarg, L"na");
    v63 = (char *)v7 + 88;
    if ( *((_QWORD *)v7 + 14) > 7u )
      v63 = (char *)*((_QWORD *)v7 + 11);
    *(_QWORD *)&v114 = v63;
    *((_QWORD *)&v114 + 1) = *((_QWORD *)v7 + 13);
    *(_OWORD *)&v118.vt = *v62;
    v122 = v114;
    if ( !(unsigned __int8)Strings::iequals(&v122, &v118) && *((_QWORD *)v7 + 13) )
    {
      VariantInit(&pvarg);
      pvarg.vt = 19;
      if ( (unsigned __int8)std::operator==<wchar_t>((char *)v7 + 88, L"preInstallOperationModeBestEffort", v64) )
      {
        pvarg.lVal = 1;
      }
      else if ( (unsigned __int8)std::operator==<wchar_t>((char *)v7 + 88, L"preInstallOperationModeStrict", v65) )
      {
        pvarg.lVal = 2;
      }
      else
      {
        pvarg.lVal = 2 * (unsigned __int8)std::operator==<wchar_t>((char *)v7 + 88, L"preInstallOperationModeSkip", v66)
                   + 1;
      }
      v118 = pvarg;
      v67 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v136 + 32LL))(v136, 327693, &v118);
      if ( v67 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x454,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v67,
          v106);
      VariantClear(&pvarg);
    }
  }
  VariantInit(&v151);
  *(_QWORD *)v133 = 0;
  v68 = *v129;
  if ( a6 )
  {
    *(_QWORD *)v133 = 0;
    pvarg = v151;
    v69 = (*(__int64 (__fastcall **)(_QWORD *, char *, char *, VARIANTARG *))(v68 + 144))(v129, v29, v131, &pvarg);
    if ( v69 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x460,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v69,
        (int)v133);
  }
  else
  {
    *(_QWORD *)v133 = 0;
    pvarg = v151;
    v70 = (*(__int64 (__fastcall **)(_QWORD *, char *, char *, VARIANTARG *))(v68 + 136))(v129, v29, v131, &pvarg);
    if ( v70 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x468,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v70,
        (int)v133);
  }
  EnterCriticalSection(&s_installJobLock);
  v128 = 0;
  v71 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v133)(
          *(_QWORD *)v133,
          &GUID_52f15a39_17df_49d3_9617_d59a34631123,
          &v128);
  if ( v71 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v71,
      (int)v133);
  v72 = v33 | 0x20;
  v73 = v128;
  v74 = 0;
  v128 = 0;
  v75 = *((_QWORD *)v6 + 16);
  *((_QWORD *)v6 + 16) = v73;
  if ( v75 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    v74 = v128;
  }
  if ( v74 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
  LeaveCriticalSection(&s_installJobLock);
  *(_QWORD *)&v115 = a4;
  *((_QWORD *)&v115 + 1) = v6;
  v146 = off_1403D70E8;
  v147 = v115;
  v150 = &v146;
  v131 = v29;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 8LL))(v29);
  bstrString[0] = *(BSTR *)v133;
  if ( *(_QWORD *)v133 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v133 + 8LL))(*(_QWORD *)v133);
  v76 = Windows::WU::WuUpdateInternalImpl::WaitForCompletion<IInstallationJob,Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,IInstallationProgress>(
          v6,
          (__int64)v7 + 80);
  EnterCriticalSection(&s_installJobLock);
  v77 = *((_QWORD *)v6 + 16);
  *((_QWORD *)v6 + 16) = 0;
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  LeaveCriticalSection(&s_installJobLock);
  if ( v76 )
  {
    v139 = 0;
    v79 = *v129;
    if ( a6 )
    {
      v139 = 0;
      v80 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 **))(v79 + 160))(v129, *(_QWORD *)v133, &v139);
      if ( v80 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x485,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v80,
          v108);
    }
    else
    {
      v139 = 0;
      v81 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 **))(v79 + 152))(v129, *(_QWORD *)v133, &v139);
      if ( v81 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x489,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v81,
          v108);
    }
    v140 = 0;
    v141 = 0;
    v137 = 0;
    v82 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v117 + 80LL))(*v117, &v137);
    if ( v82 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v82,
        v108);
    v83 = 0;
    for ( LODWORD(v117) = 0; (int)v83 < v137; LODWORD(v117) = v83 )
    {
      v130 = 0;
      v84 = *v139;
      v130 = 0;
      v85 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, BSTR *))(v84 + 80))(v139, v83, &v130);
      if ( v85 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x493,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v85,
          v108);
      LODWORD(v138) = 0;
      v86 = (*(__int64 (__fastcall **)(BSTR, Windows::WU::WuUpdateInternalImpl **))(*(_QWORD *)v130 + 56LL))(
              v130,
              &v138);
      if ( v86 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x496,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v86,
          v108);
      v126[0] = 0;
      v87 = (*(__int64 (__fastcall **)(BSTR, __int16 *))(*(_QWORD *)v130 + 64LL))(v130, v126);
      if ( v87 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x499,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v87,
          v108);
      v131 = 0;
      v88 = (**(__int64 (__fastcall ***)(BSTR, GUID *, char **))v130)(
              v130,
              &GUID_a67b1922_4ca9_4330_81a7_6b5bef1bf0de,
              &v131);
      if ( v88 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v88,
          v108);
      v72 |= 0x10u;
      v127 = 0;
      v89 = (*(__int64 (__fastcall **)(char *, __int16 *))(*(_QWORD *)v131 + 40LL))(v131, &v127);
      if ( v89 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x49E,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v89,
          v108);
      v116[0] = 0;
      v90 = (int)v138;
      if ( (int)v138 >= 0 )
      {
        v116[0] = (char *)Windows::WU::WuUpdateInternalImpl::RebootDowntimeSignal(v6, v7);
        v90 = (int)v138;
      }
      BYTE4(v128) = 0;
      v145 = 0;
      if ( v90 < 0 )
      {
        bstrString[0] = 0;
        (**(void (__fastcall ***)(BSTR, GUID *, BSTR *))v130)(
          v130,
          &GUID_fe26e226_e654_403d_8668_49d9656dd30c,
          bstrString);
        v91 = bstrString[0];
        if ( bstrString[0] )
        {
          LODWORD(v135) = 0;
          v92 = (*(__int64 (__fastcall **)(BSTR, char **))(*(_QWORD *)bstrString[0] + 32LL))(bstrString[0], &v135);
          if ( v92 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4B0,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
              (const char *)(unsigned int)v92,
              v108);
          v91 = bstrString[0];
          if ( (_DWORD)v135 )
          {
            LODWORD(v128) = (_DWORD)v135;
            BYTE4(v128) = 1;
            *(_WORD *)((char *)&v128 + 5) = HIDWORD(a4) >> 8;
            HIBYTE(v128) = HIBYTE(a4);
          }
        }
        if ( v91 )
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v91 + 16LL))(v91);
        v135 = 0;
        (**(void (__fastcall ***)(BSTR, GUID *, void **))v130)(
          v130,
          &GUID_9c0166dd_62d2_4715_8c6d_9521f264d966,
          (void **)&v135);
        v93 = v135;
        if ( v135 )
        {
          bstrString[0] = 0;
          v94 = *(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v135 + 24LL);
          v95 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator&(bstrString);
          v96 = v94(v93, v95);
          if ( v96 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4BC,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
              (const char *)(unsigned int)v96,
              v108);
          v97 = bstrString[0];
          if ( bstrString[0] )
          {
            v98 = Windows::Strings::to_wstring(&v146, bstrString);
            std::optional<std::wstring>::operator=<std::wstring,0>(&v142, v98);
            std::wstring::~wstring(&v146);
            v97 = bstrString[0];
          }
          if ( v97 )
            SysFreeString(v97);
          v7 = v120;
          v93 = v135;
        }
        if ( v93 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v93 + 16LL))(v93);
        v90 = (int)v138;
        v83 = (unsigned int)v117;
      }
      LODWORD(v146) = v90;
      BYTE4(v146) = v126[0] == 0xFFFF;
      BYTE5(v146) = v127 == -1;
      HIWORD(v146) = 0;
      *(_QWORD *)&v147 = gsl::narrow<unsigned __int64,__int64>(v116[0]);
      *((_QWORD *)&v147 + 1) = v128;
      LOBYTE(v150) = 0;
      if ( v145 )
      {
        std::wstring::wstring(&v148, &v142);
        LOBYTE(v150) = 1;
      }
      v99 = *((_QWORD *)&v140 + 1);
      if ( *((_QWORD *)&v140 + 1) == v141 )
      {
        std::vector<Windows::WU::InstallResult>::_Emplace_reallocate<Windows::WU::InstallResult>(
          &v140,
          *((_QWORD *)&v140 + 1),
          &v146);
      }
      else
      {
        **((_DWORD **)&v140 + 1) = (_DWORD)v146;
        *(_WORD *)(v99 + 4) = WORD2(v146);
        *(_OWORD *)(v99 + 8) = v147;
        *(_BYTE *)(v99 + 56) = 0;
        if ( (_BYTE)v150 )
        {
          *(_OWORD *)(v99 + 24) = 0;
          *(_QWORD *)(v99 + 40) = 0;
          *(_QWORD *)(v99 + 48) = 0;
          *(_OWORD *)(v99 + 24) = v148;
          *(_OWORD *)(v99 + 40) = v149;
          *(_QWORD *)&v149 = 0;
          *((_QWORD *)&v149 + 1) = 7;
          LOWORD(v148) = 0;
          *(_BYTE *)(v99 + 56) = 1;
        }
        *((_QWORD *)&v140 + 1) += 64LL;
      }
      if ( (_BYTE)v150 )
        std::wstring::~wstring(&v148);
      if ( v126[0] == -1 || (v100 = 0, v127 == -1) )
        v100 = 1;
      LOBYTE(v110) = v100;
      HIBYTE(v110) = 1;
      *((_WORD *)v6 + 50) = v110;
      if ( v145 )
        std::wstring::~wstring(&v142);
      if ( v131 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v131 + 16LL))(v131);
      if ( v130 )
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v130 + 16LL))(v130);
      ++v83;
    }
    v101 = v141;
    v141 = 0;
    v102 = *((_QWORD *)&v140 + 1);
    v103 = v140;
    v140 = 0u;
    v104 = v121;
    *(_QWORD *)v121 = v103;
    *(_QWORD *)(v104 + 8) = v102;
    *(_QWORD *)(v104 + 16) = v101;
    *(_BYTE *)(v104 + 24) = 1;
    std::vector<Windows::WU::InstallResult>::~vector<Windows::WU::InstallResult>(&v140);
    if ( v139 )
      (*(void (__fastcall **)(__int64 *))(*v139 + 16))(v139);
    if ( *(_QWORD *)v133 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v133 + 16LL))(*(_QWORD *)v133);
    VariantClear(&v151);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v136 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
    if ( v129 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v129 + 16LL))(v129, *v129);
    return v121;
  }
  else
  {
    v78 = v121;
    *(_BYTE *)(v121 + 24) = 0;
    if ( *(_QWORD *)v133 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v133 + 16LL))(*(_QWORD *)v133);
    VariantClear(&v151);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v136 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
    if ( v129 )
      (*(void (__fastcall **)(_QWORD *))(*v129 + 16LL))(v129);
  }
  return v78;
}

```

## disassembly

```asm
0x1402e7e5c  mov     r11, rsp
0x1402e7e5f  mov     [r11+20h], r9
0x1402e7e63  push    rbx
0x1402e7e64  push    rsi
0x1402e7e65  push    rdi
0x1402e7e66  push    r12
0x1402e7e68  push    r13
0x1402e7e6a  push    r14
0x1402e7e6c  push    r15
0x1402e7e6e  sub     rsp, 220h
0x1402e7e75  mov     rax, cs:__security_cookie
0x1402e7e7c  xor     rax, rsp
0x1402e7e7f  mov     [rsp+258h+var_48], rax
0x1402e7e87  mov     [rsp+258h+var_1E8], r8
0x1402e7e8c  mov     [rsp+258h+var_1B0], rdx
0x1402e7e94  mov     r13, rcx
0x1402e7e97  mov     [rsp+258h+var_F0], rcx
0x1402e7e9f  mov     [rsp+258h+var_198], rdx
0x1402e7ea7  mov     qword ptr [rsp+258h+var_208], r8
0x1402e7eac  mov     rdi, [rsp+258h+arg_20]
0x1402e7eb4  mov     [rsp+258h+var_1B8], rdi
0x1402e7ebc  xor     esi, esi
0x1402e7ebe  mov     [rsp+258h+var_214], esi
0x1402e7ec2  mov     [r11-160h], rsi
0x1402e7ec9  mov     rcx, [rcx+70h]
0x1402e7ecd  mov     rax, [rcx]
0x1402e7ed0  mov     [r11-160h], rsi
0x1402e7ed7  lea     rdx, [r11-160h]
0x1402e7ede  mov     rax, [rax+70h]
0x1402e7ee2  call    _guard_dispatch_icall
0x1402e7ee7  mov     rcx, [rsp+258h]; this
0x1402e7eef  test    eax, eax
0x1402e7ef1  js      loc_1402E9526
0x1402e7ef7  mov     rcx, [rsp+258h+var_160]
0x1402e7eff  mov     [rsp+258h+var_100], rsi
0x1402e7f07  mov     rax, [rcx]
0x1402e7f0a  lea     r8, [rsp+258h+var_100]
0x1402e7f12  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x1402e7f19  mov     rax, [rax]
0x1402e7f1c  call    _guard_dispatch_icall
0x1402e7f21  mov     rcx, [rsp+258h]; this
0x1402e7f29  test    eax, eax
0x1402e7f2b  js      loc_1402E953B
0x1402e7f31  mov     r12d, 40h ; '@'
0x1402e7f37  cmp     [r13+0Ch], sil
0x1402e7f3b  jz      loc_1402E7FDC
0x1402e7f41  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1402e7f49  call    cs:__imp_VariantInit
0x1402e7f4f  nop
0x1402e7f50  lea     ebx, [r12-2Dh]
0x1402e7f55  mov     word ptr [rsp+258h+pvarg], bx
0x1402e7f5d  cmp     [r13+0Ch], sil
0x1402e7f61  jz      loc_1402E9550
0x1402e7f67  mov     eax, [r13+8]
0x1402e7f6b  dec     eax
0x1402e7f6d  neg     eax
0x1402e7f6f  sbb     eax, eax
0x1402e7f71  and     eax, 2
0x1402e7f74  mov     dword ptr [rsp+258h+pvarg+8], eax
0x1402e7f7b  movups  xmm0, xmmword ptr [rsp+258h+pvarg]
0x1402e7f83  movaps  xmmword ptr [rsp+258h+var_1D8], xmm0
0x1402e7f8b  movsd   xmm1, qword ptr [rsp+258h+pvarg+10h]
0x1402e7f94  movsd   qword ptr [rsp+258h+var_1D8+10h], xmm1
0x1402e7f9d  mov     rcx, [rsp+258h+var_100]
0x1402e7fa5  mov     rax, [rcx]
0x1402e7fa8  lea     r8, [rsp+258h+var_1D8]
0x1402e7fb0  mov     edx, 5000Bh
0x1402e7fb5  mov     rax, [rax+20h]
0x1402e7fb9  call    _guard_dispatch_icall
0x1402e7fbe  mov     rcx, [rsp+258h]; this
0x1402e7fc6  test    eax, eax
0x1402e7fc8  js      loc_1402E9556
0x1402e7fce  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1402e7fd6  call    cs:__imp_VariantClear
0x1402e7fdc  cmp     [rdi+40h], rsi
0x1402e7fe0  jz      loc_1402E8235
0x1402e7fe6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x1402e7fed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x1402e7ff2  test    al, al
0x1402e7ff4  jz      loc_1402E81BB
0x1402e7ffa  mov     r8d, 4
0x1402e8000  lea     rdx, [rsp+258h+pvarg]
0x1402e8008  mov     rcx, r13
0x1402e800b  call    ?InternalProperty@WuUpdateInternalImpl@WU@Windows@@AEBA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@K@Z; Windows::WU::WuUpdateInternalImpl::InternalProperty(ulong)
0x1402e8010  nop
0x1402e8011  mov     rcx, [rsp+258h]; this
0x1402e8019  lea     r14, aCW1SSrcOrchest_28; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402e8020  cmp     word ptr [rsp+258h+pvarg], 8
0x1402e8029  jz      short loc_1402E803E
0x1402e802b  mov     r9d, 8024A215h; char *
0x1402e8031  mov     r8, r14; unsigned int
0x1402e8034  mov     edx, 3FEh; void *
0x1402e8039  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1402e803e  mov     rcx, qword ptr [rsp+258h+pvarg+8]; pbstr
0x1402e8046  call    cs:__imp_SysStringLen
0x1402e804c  test    eax, eax
0x1402e804e  setz    al
0x1402e8051  mov     rcx, [rsp+258h]; this
0x1402e8059  lea     rdx, aSessionDataIsE; "Session data is empty"
0x1402e8060  mov     qword ptr [rsp+258h+var_230], rdx; bool
0x1402e8065  mov     byte ptr [rsp+258h+var_238], al; int
0x1402e8069  mov     r9d, 80070057h; char *
0x1402e806f  mov     r8, r14; unsigned int
0x1402e8072  mov     edx, 3FFh; void *
0x1402e8077  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1402e807c  lea     rbx, [rdi+30h]
0x1402e8080  mov     [rsp+258h+var_150], rbx
0x1402e8088  cmp     qword ptr [rbx+18h], 7
0x1402e808d  jbe     short loc_1402E809A
0x1402e808f  mov     rax, [rbx]
0x1402e8092  mov     [rsp+258h+var_150], rax
0x1402e809a  xorps   xmm0, xmm0
0x1402e809d  movups  [rsp+258h+var_C8], xmm0
0x1402e80a5  mov     [rsp+258h+var_B8], rsi
0x1402e80ad  mov     [rsp+258h+var_B0], rsi
0x1402e80b5  mov     rdx, qword ptr [rsp+258h+pvarg+8]
0x1402e80bd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1402e80c1  mov     r8, r15
0x1402e80c4  inc     r8
0x1402e80c7  cmp     [rdx+r8*2], si
0x1402e80cc  jnz     short loc_1402E80C4
0x1402e80ce  lea     rcx, [rsp+258h+var_C8]
0x1402e80d6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402e80db  nop
0x1402e80dc  lea     rax, [rsp+258h+var_C8]
0x1402e80e4  cmp     [rsp+258h+var_B0], 7
0x1402e80ed  cmova   rax, qword ptr [rsp+258h+var_C8]
0x1402e80f6  mov     [rsp+258h+var_1F8], rax
0x1402e80fb  xorps   xmm0, xmm0
0x1402e80fe  movups  xmmword ptr [rsp+258h+var_1D8], xmm0
0x1402e8106  mov     qword ptr [rsp+258h+var_1D8+10h], rsi
0x1402e810e  mov     [rsp+258h+var_1C0], rsi
0x1402e8116  mov     rdx, qword ptr [rsp+258h+pvarg+8]
0x1402e811e  mov     r8, r15
0x1402e8121  inc     r8
0x1402e8124  cmp     [rdx+r8*2], si
0x1402e8129  jnz     short loc_1402E8121
0x1402e812b  lea     rcx, [rsp+258h+var_1D8]
0x1402e8133  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402e8138  mov     rdx, rbx
0x1402e813b  lea     rcx, [rsp+258h+var_1D8]
0x1402e8143  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x1402e8148  xor     al, 1
0x1402e814a  mov     rcx, [rsp+258h]; this
0x1402e8152  mov     rdx, [rsp+258h+var_150]
0x1402e815a  mov     [rsp+258h+var_220], rdx
0x1402e815f  mov     rdx, [rsp+258h+var_1F8]
0x1402e8164  mov     [rsp+258h+var_228], rdx; char *
0x1402e8169  lea     rdx, aSessionDataMis; "Session data mismatch %s does not equal"...
0x1402e8170  mov     qword ptr [rsp+258h+var_230], rdx; bool
0x1402e8175  mov     byte ptr [rsp+258h+var_238], al; int
0x1402e8179  mov     r9d, 80070057h; char *
0x1402e817f  mov     r8, r14; unsigned int
0x1402e8182  mov     edx, 400h; void *
0x1402e8187  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1402e818c  lea     rcx, [rsp+258h+var_1D8]
0x1402e8194  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402e8199  nop
0x1402e819a  lea     rcx, [rsp+258h+var_C8]
0x1402e81a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402e81a7  nop
0x1402e81a8  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1402e81b0  call    cs:__imp_VariantClear
0x1402e81b6  jmp     loc_1402E823C
0x1402e81bb  mov     rbx, [rsp+258h+var_100]
0x1402e81c3  mov     rax, [rbx]
0x1402e81c6  mov     r14, [rax+20h]
0x1402e81ca  lea     rdx, [rdi+30h]
0x1402e81ce  cmp     qword ptr [rdi+48h], 7
0x1402e81d3  jbe     short loc_1402E81D8
0x1402e81d5  mov     rdx, [rdx]
0x1402e81d8  lea     rcx, [rsp+258h+var_1D8]
0x1402e81e0  call    ?make_variant_bstr@wil@@YA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@1@PEB_W@Z; wil::make_variant_bstr(wchar_t const *)
0x1402e81e5  nop
0x1402e81e6  movups  xmm0, xmmword ptr [rax]
0x1402e81e9  movaps  xmmword ptr [rsp+258h+pvarg], xmm0
0x1402e81f1  movsd   xmm1, qword ptr [rax+10h]
0x1402e81f6  movsd   qword ptr [rsp+258h+pvarg+10h], xmm1
0x1402e81ff  lea     r8, [rsp+258h+pvarg]
0x1402e8207  mov     edx, 50004h
0x1402e820c  mov     rcx, rbx
0x1402e820f  mov     rax, r14
0x1402e8212  call    _guard_dispatch_icall
0x1402e8217  mov     rcx, [rsp+258h]; this
0x1402e821f  test    eax, eax
0x1402e8221  js      loc_1402E956B
0x1402e8227  lea     rcx, [rsp+258h+var_1D8]; pvarg
0x1402e822f  call    cs:__imp_VariantClear
0x1402e8235  lea     r14, aCW1SSrcOrchest_28; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402e823c  mov     rcx, [rdi+20h]
0x1402e8240  test    rcx, rcx
0x1402e8243  jz      short loc_1402E8258
0x1402e8245  mov     rax, [rcx]
0x1402e8248  lea     rdx, [rsp+258h+var_1F8]
0x1402e824d  mov     rax, [rax+8]
0x1402e8251  call    _guard_dispatch_icall
0x1402e8256  jmp     short loc_1402E8262
0x1402e8258  mov     byte ptr [rsp+258h+var_1F8+4], sil
0x1402e825d  lea     rax, [rsp+258h+var_1F8]
0x1402e8262  mov     rbx, [rax]
0x1402e8265  mov     rax, rbx
0x1402e8268  shr     rax, 20h
0x1402e826c  test    al, al
0x1402e826e  jz      loc_1402E8319
0x1402e8274  cmp     [rdi+54h], sil
0x1402e8278  jz      loc_1402E8319
0x1402e827e  cmp     [rsp+258h+arg_28], sil
0x1402e8286  jnz     loc_1402E8319
0x1402e828c  mov     rcx, [rsp+258h+var_160]
0x1402e8294  mov     [rsp+258h+bstrString], rsi
0x1402e829c  mov     rax, [rcx]
0x1402e829f  lea     r8, [rsp+258h+bstrString]
0x1402e82a7  lea     rdx, _GUID_83e4294c_e0bb_4e62_ac48_00f226021136
0x1402e82ae  mov     rax, [rax]
0x1402e82b1  call    _guard_dispatch_icall
0x1402e82b6  mov     rcx, [rsp+258h]; this
0x1402e82be  test    eax, eax
0x1402e82c0  js      loc_1402E9580
0x1402e82c6  mov     r12d, 140h
0x1402e82cc  mov     rcx, [rsp+258h+bstrString]
0x1402e82d4  mov     rax, [rcx]
0x1402e82d7  mov     edx, ebx
0x1402e82d9  mov     rax, [rax+18h]
0x1402e82dd  call    _guard_dispatch_icall
0x1402e82e2  mov     rcx, [rsp+258h]; this
0x1402e82ea  test    eax, eax
0x1402e82ec  jns     short loc_1402E82FF
0x1402e82ee  mov     r9d, eax; char *
0x1402e82f1  mov     r8, r14; unsigned int
0x1402e82f4  mov     edx, 40Eh; void *
0x1402e82f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1402e82fe  nop
0x1402e82ff  mov     rcx, [rsp+258h+bstrString]
0x1402e8307  test    rcx, rcx
0x1402e830a  jz      short loc_1402E8319
0x1402e830c  mov     rax, [rcx]
0x1402e830f  mov     rax, [rax+10h]
0x1402e8313  call    _guard_dispatch_icall
0x1402e8318  nop
0x1402e8319  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1402e8321  call    cs:__imp_VariantInit
0x1402e8327  nop
0x1402e8328  mov     eax, 13h
0x1402e832d  mov     word ptr [rsp+258h+pvarg], ax
0x1402e8335  mov     dword ptr [rsp+258h+pvarg+8], 1
0x1402e8340  movups  xmm0, xmmword ptr [rsp+258h+pvarg]
0x1402e8348  movaps  xmmword ptr [rsp+258h+var_1D8], xmm0
0x1402e8350  movsd   xmm1, qword ptr [rsp+258h+pvarg+10h]
0x1402e8359  movsd   qword ptr [rsp+258h+var_1D8+10h], xmm1
0x1402e8362  mov     rcx, [rsp+258h+var_100]
0x1402e836a  mov     rax, [rcx]
0x1402e836d  lea     r8, [rsp+258h+var_1D8]
0x1402e8375  mov     edx, 50007h
0x1402e837a  mov     rax, [rax+20h]
0x1402e837e  call    _guard_dispatch_icall
0x1402e8383  mov     rcx, [rsp+258h]; this
0x1402e838b  test    eax, eax
0x1402e838d  js      loc_1402E9595
0x1402e8393  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1402e839b  call    cs:__imp_VariantClear
0x1402e83a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl(void)'::`2'::impl
0x1402e83a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_ModernStandby@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(void)
0x1402e83ad  test    al, al
0x1402e83af  jz      loc_1402E8443
0x1402e83b5  mov     rcx, [rsp+258h+var_100]
0x1402e83bd  mov     rax, [rcx]
0x1402e83c0  mov     r9, [rax+20h]
0x1402e83c4  mov     eax, 0Bh
0x1402e83c9  mov     word ptr [rsp+258h+pvarg], ax
0x1402e83d1  mov     al, [rdi+57h]
0x1402e83d4  neg     al
0x1402e83d6  sbb     dx, dx
0x1402e83d9  mov     word ptr [rsp+258h+pvarg+8], dx
0x1402e83e1  movups  xmm0, xmmword ptr [rsp+258h+pvarg]
0x1402e83e9  movaps  xmmword ptr [rsp+258h+var_1D8], xmm0
0x1402e83f1  movsd   xmm1, qword ptr [rsp+258h+pvarg+10h]
0x1402e83fa  movsd   qword ptr [rsp+258h+var_1D8+10h], xmm1
0x1402e8403  lea     r8, [rsp+258h+var_1D8]
0x1402e840b  mov     edx, 5000Ch
0x1402e8410  mov     rax, r9
0x1402e8413  call    _guard_dispatch_icall
0x1402e8418  mov     rcx, [rsp+258h]; this
0x1402e8420  test    eax, eax
0x1402e8422  jns     short loc_1402E8435
0x1402e8424  mov     r9d, eax; char *
0x1402e8427  mov     r8, r14; unsigned int
0x1402e842a  mov     edx, 41Ch; void *
0x1402e842f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1402e8434  nop
0x1402e8435  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1402e843d  call    cs:__imp_VariantClear
0x1402e8443  mov     ecx, 30h ; '0'; Size
0x1402e8448  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1402e844d  mov     r15, rax
0x1402e8450  mov     [rsp+258h+var_108], rax
0x1402e8458  xorps   xmm0, xmm0
0x1402e845b  movups  xmmword ptr [rax], xmm0
0x1402e845e  movups  xmmword ptr [rax+10h], xmm0
0x1402e8462  movups  xmmword ptr [rax+20h], xmm0
0x1402e8466  mov     rcx, rsi
  ... truncated ...
```
