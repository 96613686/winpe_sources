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
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64, VARIANTARG *); // r14
  _QWORD *v21; // rdx
  int v22; // eax
  __int64 v23; // rcx
  char **v24; // rax
  char *v25; // rbx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 (__fastcall *v29)(__int64, __int64, VARIANTARG *); // r9
  int v30; // eax
  char *v31; // r15
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rax
  unsigned int v35; // r12d
  int v36; // eax
  int v37; // eax
  __int64 System; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  char v41; // bl
  int v42; // eax
  _QWORD *v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdi
  void (__fastcall *v48)(__int64, __int64 (__fastcall ***)(), char **); // rbx
  __int64 v49; // rdx
  const char *v50; // r9
  _QWORD *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 (__fastcall *v54)(__int64, VARIANTARG *, VARIANTARG *); // r9
  __int128 *v55; // rax
  _QWORD *v56; // rax
  __int64 v57; // rdx
  int v58; // eax
  _QWORD *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 (__fastcall *v62)(__int64, __int64 (__fastcall ***)(), VARIANTARG *); // r9
  __int128 *v63; // rax
  _QWORD *v64; // rax
  __int64 v65; // rdx
  int v66; // eax
  __int64 v67; // rdx
  _OWORD *v68; // rax
  char *v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r8
  __int64 v72; // r8
  int v73; // eax
  __int64 v74; // rax
  int v75; // eax
  int v76; // eax
  int v77; // eax
  int v78; // r12d
  __int64 v79; // rax
  __int64 v80; // rcx
  __int64 v81; // rdx
  char v82; // bl
  __int64 v83; // rcx
  __int64 v84; // rbx
  __int64 v85; // rax
  int v86; // eax
  int v87; // eax
  int v88; // eax
  unsigned int v89; // ebx
  __int64 v90; // rax
  int v91; // eax
  int v92; // eax
  int v93; // eax
  int v94; // eax
  int v95; // eax
  int v96; // eax
  BSTR v97; // rcx
  int v98; // eax
  char *v99; // rbx
  __int64 (__fastcall *v100)(char *, __int64); // rdi
  __int64 v101; // rdx
  int v102; // eax
  OLECHAR *v103; // rcx
  __int64 v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rdx
  char v107; // al
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // rax
  __int64 v111; // r8
  int v113; // [rsp+20h] [rbp-238h]
  int v114; // [rsp+20h] [rbp-238h]
  int v115; // [rsp+20h] [rbp-238h]
  char *v116; // [rsp+30h] [rbp-228h]
  __int16 v117; // [rsp+40h] [rbp-218h]
  __int128 v119; // [rsp+50h] [rbp-208h]
  __int128 v120; // [rsp+50h] [rbp-208h]
  __int128 v121; // [rsp+50h] [rbp-208h]
  __int128 v122; // [rsp+50h] [rbp-208h]
  char *v123[2]; // [rsp+60h] [rbp-1F8h] BYREF
  _QWORD *v124; // [rsp+70h] [rbp-1E8h]
  VARIANTARG v125; // [rsp+80h] [rbp-1D8h] BYREF
  __int64 v126; // [rsp+98h] [rbp-1C0h]
  struct Windows::WU::InstallProperties *v127; // [rsp+A0h] [rbp-1B8h]
  __int64 v128; // [rsp+A8h] [rbp-1B0h]
  __int128 v129; // [rsp+B0h] [rbp-1A8h] BYREF
  _QWORD v130[2]; // [rsp+C0h] [rbp-198h] BYREF
  _BYTE v131[16]; // [rsp+D0h] [rbp-188h] BYREF
  char *v132; // [rsp+E0h] [rbp-178h]
  __int16 v133[2]; // [rsp+E8h] [rbp-170h] BYREF
  __int16 v134; // [rsp+ECh] [rbp-16Ch] BYREF
  __int64 v135; // [rsp+F0h] [rbp-168h] BYREF
  _QWORD *v136; // [rsp+F8h] [rbp-160h] BYREF
  BSTR v137; // [rsp+100h] [rbp-158h] BYREF
  char *v138; // [rsp+108h] [rbp-150h] BYREF
  BSTR bstrString[2]; // [rsp+110h] [rbp-148h] BYREF
  int v140[2]; // [rsp+120h] [rbp-138h] BYREF
  VARIANTARG pvarg; // [rsp+130h] [rbp-128h] BYREF
  char *v142; // [rsp+150h] [rbp-108h] BYREF
  __int64 v143; // [rsp+158h] [rbp-100h] BYREF
  int v144; // [rsp+160h] [rbp-F8h] BYREF
  Windows::WU::WuUpdateInternalImpl *v145; // [rsp+168h] [rbp-F0h] BYREF
  __int64 *v146; // [rsp+170h] [rbp-E8h] BYREF
  __int128 v147; // [rsp+178h] [rbp-E0h] BYREF
  __int64 v148; // [rsp+188h] [rbp-D0h]
  __int128 v149; // [rsp+190h] [rbp-C8h] BYREF
  __int64 v150; // [rsp+1A0h] [rbp-B8h]
  unsigned __int64 v151; // [rsp+1A8h] [rbp-B0h]
  char v152; // [rsp+1B0h] [rbp-A8h]
  __int64 (__fastcall **v153)(); // [rsp+1B8h] [rbp-A0h] BYREF
  __int128 v154; // [rsp+1C0h] [rbp-98h]
  __int128 v155; // [rsp+1D0h] [rbp-88h] BYREF
  __int128 v156; // [rsp+1E0h] [rbp-78h]
  __int64 (__fastcall ***v157)(); // [rsp+1F0h] [rbp-68h]
  VARIANTARG v158; // [rsp+1F8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v124 = a3;
  v128 = a2;
  v6 = (Windows::WU::WuUpdateInternalImpl *)this;
  v145 = (Windows::WU::WuUpdateInternalImpl *)this;
  v130[0] = a2;
  v7 = a5;
  v127 = a5;
  v136 = 0;
  v8 = this[14];
  v9 = *v8;
  v136 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD **))(v9 + 112))(v8, &v136);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3EA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v10,
      v113);
  v143 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v136)(
          v136,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          &v143);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v11,
      v113);
  v12 = 64;
  if ( *((_BYTE *)v6 + 12) )
  {
    VariantInit(&pvarg);
    pvarg.vt = 19;
    if ( !*((_BYTE *)v6 + 12) )
      std::_Throw_bad_optional_access();
    pvarg.lVal = *((_DWORD *)v6 + 2) != 1 ? 2 : 0;
    v125 = pvarg;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v143 + 32LL))(v143, 327691, &v125);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F6,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v13,
        v113);
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
          v113);
      LOBYTE(v113) = SysStringLen(pvarg.bstrVal) == 0;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x3FF,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)0x80070057LL,
        v113,
        (bool)"Session data is empty",
        v116);
      v138 = (char *)a5 + 48;
      if ( *((_QWORD *)a5 + 9) > 7u )
        v138 = (char *)*((_QWORD *)a5 + 6);
      v149 = 0;
      v150 = 0;
      v151 = 0;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(pvarg.llVal + 2 * v14) );
      std::wstring::_Construct<1,wchar_t const *>(&v149, pvarg.llVal, v14);
      v15 = (char *)&v149;
      if ( v151 > 7 )
        v15 = (char *)v149;
      v123[0] = v15;
      memset(&v125, 0, sizeof(v125));
      v126 = 0;
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(pvarg.llVal + 2 * v16) );
      std::wstring::_Construct<1,wchar_t const *>(&v125, pvarg.llVal, v16);
      LOBYTE(v114) = std::operator==<wchar_t>(&v125, (char *)a5 + 48) ^ 1;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x400,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)0x80070057LL,
        v114,
        (bool)"Session data mismatch %s does not equal %s",
        v123[0]);
      std::wstring::~wstring(&v125, v17);
      std::wstring::~wstring(&v149, v18);
      VariantClear(&pvarg);
    }
    else
    {
      v19 = v143;
      v20 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v143 + 32LL);
      v21 = (_QWORD *)((char *)a5 + 48);
      if ( *((_QWORD *)a5 + 9) > 7u )
        v21 = (_QWORD *)*v21;
      pvarg = *(VARIANTARG *)wil::make_variant_bstr(&v125, v21);
      v22 = v20(v19, 327684, &pvarg);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x404,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v22,
          v113);
      VariantClear(&v125);
    }
  }
  v23 = *((_QWORD *)a5 + 4);
  if ( v23 )
  {
    v24 = (char **)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v23 + 8LL))(v23, v123);
  }
  else
  {
    BYTE4(v123[0]) = 0;
    v24 = v123;
  }
  v25 = *v24;
  if ( (unsigned __int8)BYTE4(*v24) && *((_BYTE *)a5 + 84) && !a6 )
  {
    bstrString[0] = 0;
    v26 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, BSTR *))*v136)(
            v136,
            &GUID_83e4294c_e0bb_4e62_ac48_00f226021136,
            bstrString);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v26,
        v113);
    v12 = 320;
    v27 = (*(__int64 (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)bstrString[0] + 24LL))(bstrString[0], (unsigned int)v25);
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x40E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v27,
        v113);
    if ( bstrString[0] )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString[0] + 16LL))(bstrString[0]);
  }
  VariantInit(&pvarg);
  pvarg.vt = 19;
  pvarg.lVal = 1;
  v125 = pvarg;
  v28 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v143 + 32LL))(v143, 327687, &v125);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v28,
      v113);
  VariantClear(&pvarg);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_ModernStandby>::GetImpl'::`2'::impl) )
  {
    v29 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v143 + 32LL);
    pvarg.vt = 11;
    pvarg.iVal = -(*((_BYTE *)a5 + 87) != 0);
    v125 = pvarg;
    v30 = v29(v143, 327692, &v125);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x41C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v30,
        v113);
    VariantClear(&pvarg);
  }
  v31 = (char *)operator new(0x30u);
  v142 = v31;
  *(_OWORD *)v31 = 0;
  *((_OWORD *)v31 + 1) = 0;
  *((_OWORD *)v31 + 2) = 0;
  v32 = 0;
  v33 = 0;
  v34 = *((_QWORD *)v6 + 3);
  if ( v34 )
  {
    v32 = *((_QWORD *)v6 + 2);
    v33 = *((_QWORD *)v6 + 3);
    _InterlockedIncrement((volatile signed __int32 *)(v34 + 12));
  }
  *(_QWORD *)v31 = &Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>::`vftable'{for `IInstallationProgressChangedCallback'};
  v138 = v31 + 8;
  *((_QWORD *)v31 + 1) = &Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>::`vftable'{for `IInstallationCompletedCallback'};
  *((_WORD *)v31 + 8) = 0;
  *((_QWORD *)v31 + 3) = v32;
  *((_QWORD *)v31 + 4) = v33;
  *((_DWORD *)v31 + 10) = 0;
  v132 = v31;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 8LL))(v31);
  v35 = v12 & 0xFFFFFFFE;
  v36 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v136 + 128LL))(v136, *v124);
  if ( v36 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x421,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v36,
      v113);
  if ( *((_BYTE *)a5 + 85) )
  {
    v37 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v136 + 80LL))(v136, 0xFFFFFFFFLL);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v37,
        v113);
  }
  if ( !*((_BYTE *)a5 + 86)
    || (System = SystemInterface::Providers::GetSystem(bstrString),
        v39 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL),
        v40 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v39 + 88LL))(v39, v123),
        v35 |= 6u,
        v41 = 1,
        !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 32LL))(*v40)) )
  {
    v41 = 0;
  }
  if ( (v35 & 4) != 0 )
  {
    v35 &= ~4u;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v123);
  }
  if ( (v35 & 2) != 0 )
  {
    v35 &= ~2u;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(bstrString);
  }
  if ( v41 )
  {
    v135 = 0;
    v42 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v136)(
            v136,
            &GUID_885e76f6_f7c1_4869_951a_97613c8caef7,
            &v135);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v42,
        v113);
    v35 |= 0x80u;
    v43 = (_QWORD *)SystemInterface::Service::GetSystem(v131);
    v123[0] = (char *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 160LL))(*v43);
    Windows::Version::to_wstring(&v149, v123);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v131);
    v44 = SystemInterface::Providers::GetSystem(&v125);
    v45 = *(_QWORD *)v44 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v44 + 8LL) + 4LL);
    v46 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v45 + 40LL))(v45, &v129);
    v47 = *(_QWORD *)v46;
    v48 = *(void (__fastcall **)(__int64, __int64 (__fastcall ***)(), char **))(**(_QWORD **)v46 + 32LL);
    *(_OWORD *)v123 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                   &pvarg,
                                   L"OfframpOsVersion");
    v48(v47, &v153, v123);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v129);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v125);
    if ( (_BYTE)v156 )
    {
      try
      {
        if ( BYTE8(v155) != 2 )
          std::_Throw_bad_variant_access();
        std::wstring::operator=(&v149);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x437,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          v50);
        v31 = v142;
        v6 = v145;
        v128 = v130[0];
        v124 = a3;
      }
    }
    v7 = v127;
    if ( (_BYTE)v156 && SBYTE8(v155) != -1 && BYTE8(v155) && SBYTE8(v155) != 1 )
      std::wstring::~wstring(&v153, v49);
    v137 = 0;
    v51 = (_QWORD *)SystemInterface::Service::GetSystem(v130);
    v52 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v51 + 64LL))(*v51, &v129);
    v53 = *(_QWORD *)v52;
    v54 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, VARIANTARG *))(**(_QWORD **)v52 + 128LL);
    v55 = &v149;
    if ( v151 > 7 )
      v55 = (__int128 *)v149;
    *(_QWORD *)&v119 = v55;
    *((_QWORD *)&v119 + 1) = v150;
    *(_OWORD *)&v125.vt = v119;
    v56 = (_QWORD *)v54(v53, &pvarg, &v125);
    if ( v56[3] > 7u )
      v56 = (_QWORD *)*v56;
    wil::make_bstr(&v137, v56);
    std::wstring::~wstring(&pvarg, v57);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v129);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v130);
    v58 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR))(*(_QWORD *)v135 + 56LL))(v135, 2, v137);
    if ( v58 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v58,
        v113);
    bstrString[0] = 0;
    v59 = (_QWORD *)SystemInterface::Service::GetSystem(v123);
    v60 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v59 + 64LL))(*v59, v131);
    v61 = *(_QWORD *)v60;
    v62 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(), VARIANTARG *))(**(_QWORD **)v60 + 136LL);
    v63 = &v149;
    if ( v151 > 7 )
      v63 = (__int128 *)v149;
    *(_QWORD *)&v120 = v63;
    *((_QWORD *)&v120 + 1) = v150;
    *(_OWORD *)&v125.vt = v120;
    v64 = (_QWORD *)v62(v61, &v153, &v125);
    if ( v64[3] > 7u )
      v64 = (_QWORD *)*v64;
    wil::make_bstr(bstrString, v64);
    std::wstring::~wstring(&v153, v65);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v131);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v123);
    v66 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR))(*(_QWORD *)v135 + 56LL))(v135, 3, bstrString[0]);
    if ( v66 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x440,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v66,
        v113);
    if ( bstrString[0] )
      SysFreeString(bstrString[0]);
    if ( v137 )
      SysFreeString(v137);
    std::wstring::~wstring(&v149, v67);
    if ( v135 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
  {
    v68 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(&pvarg, L"na");
    v69 = (char *)v7 + 88;
    if ( *((_QWORD *)v7 + 14) > 7u )
      v69 = (char *)*((_QWORD *)v7 + 11);
    *(_QWORD *)&v121 = v69;
    *((_QWORD *)&v121 + 1) = *((_QWORD *)v7 + 13);
    *(_OWORD *)&v125.vt = *v68;
    v129 = v121;
    if ( !(unsigned __int8)Strings::iequals(&v129, &v125) && *((_QWORD *)v7 + 13) )
    {
      VariantInit(&pvarg);
      pvarg.vt = 19;
      if ( (unsigned __int8)std::operator==<wchar_t>((char *)v7 + 88, L"preInstallOperationModeBestEffort", v70) )
      {
        pvarg.lVal = 1;
      }
      else if ( (unsigned __int8)std::operator==<wchar_t>((char *)v7 + 88, L"preInstallOperationModeStrict", v71) )
      {
        pvarg.lVal = 2;
      }
      else
      {
        pvarg.lVal = 2 * (unsigned __int8)std::operator==<wchar_t>((char *)v7 + 88, L"preInstallOperationModeSkip", v72)
                   + 1;
      }
      v125 = pvarg;
      v73 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v143 + 32LL))(v143, 327693, &v125);
      if ( v73 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x454,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v73,
          v113);
      VariantClear(&pvarg);
    }
  }
  VariantInit(&v158);
  *(_QWORD *)v140 = 0;
  v74 = *v136;
  if ( a6 )
  {
    *(_QWORD *)v140 = 0;
    pvarg = v158;
    v75 = (*(__int64 (__fastcall **)(_QWORD *, char *, char *, VARIANTARG *))(v74 + 144))(v136, v31, v138, &pvarg);
    if ( v75 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x460,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v75,
        (int)v140);
  }
  else
  {
    *(_QWORD *)v140 = 0;
    pvarg = v158;
    v76 = (*(__int64 (__fastcall **)(_QWORD *, char *, char *, VARIANTARG *))(v74 + 136))(v136, v31, v138, &pvarg);
    if ( v76 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x468,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v76,
        (int)v140);
  }
  EnterCriticalSection(&s_installJobLock);
  v135 = 0;
  v77 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v140)(
          *(_QWORD *)v140,
          &GUID_52f15a39_17df_49d3_9617_d59a34631123,
          &v135);
  if ( v77 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v77,
      (int)v140);
  v78 = v35 | 0x20;
  v79 = v135;
  v80 = 0;
  v135 = 0;
  v81 = *((_QWORD *)v6 + 16);
  *((_QWORD *)v6 + 16) = v79;
  if ( v81 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    v80 = v135;
  }
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  LeaveCriticalSection(&s_installJobLock);
  *(_QWORD *)&v122 = a4;
  *((_QWORD *)&v122 + 1) = v6;
  v153 = off_1403D70E8;
  v154 = v122;
  v157 = &v153;
  v138 = v31;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 8LL))(v31);
  bstrString[0] = *(BSTR *)v140;
  if ( *(_QWORD *)v140 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v140 + 8LL))(*(_QWORD *)v140);
  v82 = Windows::WU::WuUpdateInternalImpl::WaitForCompletion<IInstallationJob,Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,IInstallationProgress>(
          v6,
          (__int64)v7 + 80);
  EnterCriticalSection(&s_installJobLock);
  v83 = *((_QWORD *)v6 + 16);
  *((_QWORD *)v6 + 16) = 0;
  if ( v83 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  LeaveCriticalSection(&s_installJobLock);
  if ( v82 )
  {
    v146 = 0;
    v85 = *v136;
    if ( a6 )
    {
      v146 = 0;
      v86 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 **))(v85 + 160))(v136, *(_QWORD *)v140, &v146);
      if ( v86 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x485,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v86,
          v115);
    }
    else
    {
      v146 = 0;
      v87 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 **))(v85 + 152))(v136, *(_QWORD *)v140, &v146);
      if ( v87 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x489,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v87,
          v115);
    }
    v147 = 0;
    v148 = 0;
    v144 = 0;
    v88 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v124 + 80LL))(*v124, &v144);
    if ( v88 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v88,
        v115);
    v89 = 0;
    for ( LODWORD(v124) = 0; (int)v89 < v144; LODWORD(v124) = v89 )
    {
      v137 = 0;
      v90 = *v146;
      v137 = 0;
      v91 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, BSTR *))(v90 + 80))(v146, v89, &v137);
      if ( v91 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x493,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v91,
          v115);
      LODWORD(v145) = 0;
      v92 = (*(__int64 (__fastcall **)(BSTR, Windows::WU::WuUpdateInternalImpl **))(*(_QWORD *)v137 + 56LL))(
              v137,
              &v145);
      if ( v92 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x496,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v92,
          v115);
      v133[0] = 0;
      v93 = (*(__int64 (__fastcall **)(BSTR, __int16 *))(*(_QWORD *)v137 + 64LL))(v137, v133);
      if ( v93 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x499,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v93,
          v115);
      v138 = 0;
      v94 = (**(__int64 (__fastcall ***)(BSTR, GUID *, char **))v137)(
              v137,
              &GUID_a67b1922_4ca9_4330_81a7_6b5bef1bf0de,
              &v138);
      if ( v94 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v94,
          v115);
      v78 |= 0x10u;
      v134 = 0;
      v95 = (*(__int64 (__fastcall **)(char *, __int16 *))(*(_QWORD *)v138 + 40LL))(v138, &v134);
      if ( v95 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x49E,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v95,
          v115);
      v123[0] = 0;
      v96 = (int)v145;
      if ( (int)v145 >= 0 )
      {
        v123[0] = (char *)Windows::WU::WuUpdateInternalImpl::RebootDowntimeSignal(v6, v7);
        v96 = (int)v145;
      }
      BYTE4(v135) = 0;
      v152 = 0;
      if ( v96 < 0 )
      {
        bstrString[0] = 0;
        (**(void (__fastcall ***)(BSTR, GUID *, BSTR *))v137)(
          v137,
          &GUID_fe26e226_e654_403d_8668_49d9656dd30c,
          bstrString);
        v97 = bstrString[0];
        if ( bstrString[0] )
        {
          LODWORD(v142) = 0;
          v98 = (*(__int64 (__fastcall **)(BSTR, char **))(*(_QWORD *)bstrString[0] + 32LL))(bstrString[0], &v142);
          if ( v98 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4B0,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
              (const char *)(unsigned int)v98,
              v115);
          v97 = bstrString[0];
          if ( (_DWORD)v142 )
          {
            LODWORD(v135) = (_DWORD)v142;
            BYTE4(v135) = 1;
            *(_WORD *)((char *)&v135 + 5) = HIDWORD(a4) >> 8;
            HIBYTE(v135) = HIBYTE(a4);
          }
        }
        if ( v97 )
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v97 + 16LL))(v97);
        v142 = 0;
        (**(void (__fastcall ***)(BSTR, GUID *, void **))v137)(
          v137,
          &GUID_9c0166dd_62d2_4715_8c6d_9521f264d966,
          (void **)&v142);
        v99 = v142;
        if ( v142 )
        {
          bstrString[0] = 0;
          v100 = *(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v142 + 24LL);
          v101 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator&(bstrString);
          v102 = v100(v99, v101);
          if ( v102 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4BC,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
              (const char *)(unsigned int)v102,
              v115);
          v103 = bstrString[0];
          if ( bstrString[0] )
          {
            v104 = Windows::Strings::to_wstring(&v153, bstrString);
            std::optional<std::wstring>::operator=<std::wstring,0>(&v149, v104);
            std::wstring::~wstring(&v153, v105);
            v103 = bstrString[0];
          }
          if ( v103 )
            SysFreeString(v103);
          v7 = v127;
          v99 = v142;
        }
        if ( v99 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v99 + 16LL))(v99);
        v96 = (int)v145;
        v89 = (unsigned int)v124;
      }
      LODWORD(v153) = v96;
      BYTE4(v153) = v133[0] == 0xFFFF;
      BYTE5(v153) = v134 == -1;
      HIWORD(v153) = 0;
      *(_QWORD *)&v154 = gsl::narrow<unsigned __int64,__int64>(v123[0]);
      *((_QWORD *)&v154 + 1) = v135;
      LOBYTE(v157) = 0;
      if ( v152 )
      {
        std::wstring::wstring(&v155, &v149);
        LOBYTE(v157) = 1;
      }
      v106 = *((_QWORD *)&v147 + 1);
      if ( *((_QWORD *)&v147 + 1) == v148 )
      {
        std::vector<Windows::WU::InstallResult>::_Emplace_reallocate<Windows::WU::InstallResult>(
          &v147,
          *((_QWORD *)&v147 + 1),
          &v153);
      }
      else
      {
        **((_DWORD **)&v147 + 1) = (_DWORD)v153;
        *(_WORD *)(v106 + 4) = WORD2(v153);
        *(_OWORD *)(v106 + 8) = v154;
        *(_BYTE *)(v106 + 56) = 0;
        if ( (_BYTE)v157 )
        {
          *(_OWORD *)(v106 + 24) = 0;
          *(_QWORD *)(v106 + 40) = 0;
          *(_QWORD *)(v106 + 48) = 0;
          *(_OWORD *)(v106 + 24) = v155;
          *(_OWORD *)(v106 + 40) = v156;
          *(_QWORD *)&v156 = 0;
          *((_QWORD *)&v156 + 1) = 7;
          LOWORD(v155) = 0;
          *(_BYTE *)(v106 + 56) = 1;
        }
        *((_QWORD *)&v147 + 1) += 64LL;
      }
      if ( (_BYTE)v157 )
        std::wstring::~wstring(&v155, v106);
      if ( v133[0] == -1 || (v107 = 0, v134 == -1) )
        v107 = 1;
      LOBYTE(v117) = v107;
      HIBYTE(v117) = 1;
      *((_WORD *)v6 + 50) = v117;
      if ( v152 )
        std::wstring::~wstring(&v149, v106);
      if ( v138 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v138 + 16LL))(v138);
      if ( v137 )
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v137 + 16LL))(v137);
      ++v89;
    }
    v108 = v148;
    v148 = 0;
    v109 = *((_QWORD *)&v147 + 1);
    v110 = v147;
    v147 = 0u;
    v111 = v128;
    *(_QWORD *)v128 = v110;
    *(_QWORD *)(v111 + 8) = v109;
    *(_QWORD *)(v111 + 16) = v108;
    *(_BYTE *)(v111 + 24) = 1;
    std::vector<Windows::WU::InstallResult>::~vector<Windows::WU::InstallResult>(&v147);
    if ( v146 )
      (*(void (__fastcall **)(__int64 *))(*v146 + 16))(v146);
    if ( *(_QWORD *)v140 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v140 + 16LL))(*(_QWORD *)v140);
    VariantClear(&v158);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v143 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v143 + 16LL))(v143);
    if ( v136 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v136 + 16LL))(v136, *v136);
    return v128;
  }
  else
  {
    v84 = v128;
    *(_BYTE *)(v128 + 24) = 0;
    if ( *(_QWORD *)v140 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v140 + 16LL))(*(_QWORD *)v140);
    VariantClear(&v158);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v143 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v143 + 16LL))(v143);
    if ( v136 )
      (*(void (__fastcall **)(_QWORD *))(*v136 + 16LL))(v136);
  }
  return v84;
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
