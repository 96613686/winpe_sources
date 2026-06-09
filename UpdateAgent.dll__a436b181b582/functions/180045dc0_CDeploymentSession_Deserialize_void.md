# CDeploymentSession::Deserialize(void)

- ea: `0x180045dc0`
- end: `0x1800472b1`
- name: `?Deserialize@CDeploymentSession@@QEAAJXZ`
- size: `5361`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006b348`

## callees

- `0x1800059d0`
- `0x180008fbc`
- `0x180023b20`
- `0x180027f3c`
- `0x180039f90`
- `0x1800408d0`
- `0x180045dc0`
- `0x180047c90`
- `0x180047d50`
- `0x180077664`
- `0x180078b9c`
- `0x180092f88`
- `0x1801e3fc0`
- `0x1802b1010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180047227`
- `OLEAUT32!__imp_SysFreeString` at `0x180047242`
- `OLEAUT32!__imp_SysFreeString` at `0x18004725d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004727b`
- `OLEAUT32!__imp_SysFreeString` at `0x180047227`
- `OLEAUT32!__imp_SysFreeString` at `0x180047242`
- `OLEAUT32!__imp_SysFreeString` at `0x18004725d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004727b`

## string_xrefs

- `0x180045e55`: `CDeploymentSession::Deserialize`
- `0x180045ed5`: `CDeploymentSession::Deserialize`
- `0x180045ff5`: `PackageFileListPath`
- `0x1800461f5`: `PreDownloadCheckComplete`
- `0x1800462b3`: `ExpansionComplete`
- `0x180046312`: `StructureAppsComplete`
- `0x1800463d0`: `ComposeComplete`
- `0x18004642f`: `ComposeRequired`
- `0x1800465c3`: `ContainsReinstallCurrentLCU`
- `0x18004662a`: `CompDBsExpanded`
- `0x180046691`: `OsDownloadComplete`
- `0x1800466f8`: `PluginsDownloadComplete`
- `0x18004675f`: `RecreatePackageFileList`
- `0x1800467c6`: `DeletedCorruptFilesCount`
- `0x180046b44`: `UplevelSSUCabPath`
- `0x180046d0f`: `CDeploymentSession: Deserialize SessionId = [%s]`
- `0x180046d39`: `CDeploymentSession: Deserialize SessionData = [%s]`
- `0x180046d58`: `CDeploymentSession: Deserialize UpdateState = [%ld]`
- `0x180046d79`: `CDeploymentSession: Deserialize Scenario = [%ld]`
- `0x180046daf`: `CDeploymentSession: Deserialize RebootRequired = [%s]`
- `0x180046dd7`: `CDeploymentSession: Deserialize PreDownloadChecksComplete = [%s]`
- `0x180046dff`: `CDeploymentSession: Deserialize ExpansionRequired = [%s]`
- `0x180046e27`: `CDeploymentSession: Deserialize ExpansionComplete = [%s]`
- `0x180046e4f`: `CDeploymentSession: Deserialize StructureAppsComplete = [%s]`
- `0x180046e77`: `CDeploymentSession: Deserialize IsRangeRequestSupported = [%s]`
- `0x180046e9f`: `CDeploymentSession: Deserialize ComposeRequired = [%s]`
- `0x180046ec7`: `CDeploymentSession: Deserialize ComposeComplete = [%s]`
- `0x180046eef`: `CDeploymentSession: Deserialize ContainsExpressPackage = [%s]`
- `0x180046f17`: `CDeploymentSession: Deserialize ContainsSafeOSDUPackage = [%s]`
- `0x180046f3f`: `CDeploymentSession: Deserialize ContainsWindowsUpdateBox = [%s]`
- `0x180046f67`: `CDeploymentSession: Deserialize ContainsReinstallCurrentLCU = [%s]`
- `0x180046f8f`: `CDeploymentSession: Deserialize CompDBsExpanded = [%s]`
- `0x180046fb7`: `CDeploymentSession: Deserialize RecreatePackageFileList = [%s]`
- `0x180046fd8`: `CDeploymentSession: Deserialize DeletedCorruptFilesCount = [%lu]`
- `0x180046ff9`: `CDeploymentSession: Deserialize DownloadedExpressFilesCount = [%lu]`
- `0x180047021`: `CDeploymentSession: Deserialize MitigationExecuted = [%s]`
- `0x180047042`: `CDeploymentSession: Deserialize MitigationScenario = [%ld]`
- `0x180047063`: `CDeploymentSession: Deserialize OSDownloadSize = [%llu]`
- `0x18004708b`: `CDeploymentSession: Deserialize WinREServicingDone = [%s]`
- `0x1800470b3`: `CDeploymentSession: Deserialize StagingDone = [%s]`
- `0x1800470db`: `CDeploymentSession: Deserialize StagingPostponed = [%s]`
- `0x180047103`: `CDeploymentSession: Deserialize ContainerServicingDone = [%s]`
- `0x180047124`: `CDeploymentSession: Deserialize UplevelSSUState = [%ld]`
- `0x180047187`: `CDeploymentSession: Deserialize UplevelSSUCabPath = [%s]`
- `0x1800471af`: `CDeploymentSession: Deserialize DownloadingHistoryCIX = [%s]`
- `0x1800471d7`: `CDeploymentSession: Deserialize PostRebootWatsonUploaded = [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDeploymentSession::Deserialize(CDeploymentSession *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rcx
  __int64 updated; // rcx
  __int64 v7; // rdx
  int Internal; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  BSTR v11; // r14
  int StringCch; // eax
  __int64 v13; // rdx
  BSTR v14; // r14
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  _OWORD *v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  const WCHAR *v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  const wchar_t *v36; // r14
  const wchar_t *v37; // r9
  __int64 v38; // rcx
  const wchar_t *v39; // r9
  __int64 v40; // rcx
  const wchar_t *v41; // r9
  __int64 v42; // rcx
  const wchar_t *v43; // r9
  __int64 v44; // rcx
  const wchar_t *v45; // r9
  __int64 v46; // rcx
  const wchar_t *v47; // r9
  __int64 v48; // rcx
  const wchar_t *v49; // r9
  __int64 v50; // rcx
  const wchar_t *v51; // r9
  __int64 v52; // rcx
  const wchar_t *v53; // r9
  __int64 v54; // rcx
  const wchar_t *v55; // r9
  __int64 v56; // rcx
  const wchar_t *v57; // r9
  __int64 v58; // rcx
  const wchar_t *v59; // r9
  __int64 v60; // rcx
  const wchar_t *v61; // r9
  __int64 v62; // rcx
  const wchar_t *v63; // r9
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  const wchar_t *v67; // r9
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  const wchar_t *v71; // r9
  __int64 v72; // rcx
  const wchar_t *v73; // r9
  __int64 v74; // rcx
  const wchar_t *v75; // r9
  __int64 v76; // rcx
  const wchar_t *v77; // r9
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  const wchar_t *v81; // r9
  __int64 v82; // rcx
  UaLiteManager *v83; // rcx
  DeploymentPluginManager *v84; // rcx
  const char *v85; // r9
  __int64 result; // rax
  int v87; // [rsp+20h] [rbp-B8h]
  int v88; // [rsp+28h] [rbp-B0h]
  __int64 v89; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v90; // [rsp+38h] [rbp-A0h]
  _BYTE v91[32]; // [rsp+40h] [rbp-98h] BYREF
  int v92; // [rsp+60h] [rbp-78h] BYREF
  unsigned int v93; // [rsp+64h] [rbp-74h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-70h] BYREF
  BSTR v95; // [rsp+70h] [rbp-68h] BYREF
  BSTR v96; // [rsp+78h] [rbp-60h] BYREF
  __int64 v97; // [rsp+80h] [rbp-58h] BYREF
  BSTR v98; // [rsp+88h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v90 = -2;
  v98 = 0;
  v96 = 0;
  v95 = 0;
  bstrString = 0;
  v92 = 0;
  v93 = 0;
  v97 = 0;
  v2 = *((_QWORD *)this + 76) + 8LL;
  try
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = *((_QWORD *)this + 75);
      if ( !v5 )
      {
LABEL_4:
        updated = 0;
LABEL_8:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_271:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        if ( v95 )
        {
          SysFreeString(v95);
          v95 = 0;
        }
        if ( v96 )
        {
          SysFreeString(v96);
          v96 = 0;
        }
        if ( v98 )
          SysFreeString(v98);
        return (unsigned int)v4;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v5,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::Deserialize",
                                5650,
                                v3);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v7);
      goto LABEL_8;
    }
    Internal = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(0);
    v4 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal, v9);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
    if ( v4 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5651;
      goto LABEL_14;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)(*((_QWORD *)this + 76) + 8LL) + 16LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"SessionData",
           &v96);
    if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5653;
      goto LABEL_14;
    }
    v11 = v96;
    if ( v96 )
    {
      LODWORD(v89) = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v96, &v89);
      v4 = StringCch;
      if ( StringCch < 0
        || (StringCch = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v11),
            v4 = StringCch,
            StringCch < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch, v13);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
      if ( v4 < 0 )
      {
        v10 = *((_QWORD *)this + 75);
        if ( !v10 )
          goto LABEL_4;
        v88 = v4;
        v87 = 5656;
        goto LABEL_14;
      }
    }
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)(*((_QWORD *)this + 76) + 8LL) + 16LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"PackageFileListPath",
           &v95);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5659;
      goto LABEL_14;
    }
    v14 = v95;
    if ( v95 )
    {
      LODWORD(v89) = 0;
      v15 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v95, &v89);
      v4 = v15;
      if ( v15 < 0
        || (v15 = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v14), v4 = v15, v15 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15, v16);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
      if ( v4 < 0 )
      {
        v10 = *((_QWORD *)this + 75);
        if ( !v10 )
          goto LABEL_4;
        v88 = v4;
        v87 = 5662;
        goto LABEL_14;
      }
    }
    v17 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, unsigned int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"State",
            &v93);
    v4 = v17;
    if ( v17 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v17;
      v87 = 5665;
      goto LABEL_14;
    }
    v18 = CDeploymentSession::StateSet(this, v93);
    v4 = v18;
    if ( v18 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v18;
      v87 = 5666;
      goto LABEL_14;
    }
    v92 = 0;
    v19 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"Scenario",
            &v92);
    v4 = v19;
    if ( v19 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v19;
      v87 = 5669;
      goto LABEL_14;
    }
    *((_DWORD *)this + 114) = v92;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"RebootRequired",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5673;
      goto LABEL_14;
    }
    *((_DWORD *)this + 53) = v92 != 0;
    v92 = 0;
    v20 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"PreDownloadCheckComplete",
            &v92);
    v4 = v20;
    if ( v20 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v20;
      v87 = 5677;
      goto LABEL_14;
    }
    *((_DWORD *)this + 55) = v92 != 0;
    v92 = 0;
    v21 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"ExpansionRequired",
            &v92);
    v4 = v21;
    if ( v21 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v21;
      v87 = 5681;
      goto LABEL_14;
    }
    *((_DWORD *)this + 56) = v92 != 0;
    v92 = 0;
    v22 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"ExpansionComplete",
            &v92);
    v4 = v22;
    if ( v22 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v22;
      v87 = 5685;
      goto LABEL_14;
    }
    *((_DWORD *)this + 57) = v92 != 0;
    v92 = 0;
    v23 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"StructureAppsComplete",
            &v92);
    v4 = v23;
    if ( v23 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v23;
      v87 = 5689;
      goto LABEL_14;
    }
    *((_DWORD *)this + 58) = v92 != 0;
    v92 = 0;
    v24 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"IsRangeRequestSupported",
            &v92);
    v4 = v24;
    if ( v24 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v24;
      v87 = 5693;
      goto LABEL_14;
    }
    *((_DWORD *)this + 54) = v92 != 0;
    v92 = 0;
    v25 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"ComposeComplete",
            &v92);
    v4 = v25;
    if ( v25 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v25;
      v87 = 5697;
      goto LABEL_14;
    }
    *((_DWORD *)this + 60) = v92 != 0;
    v92 = 0;
    v26 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"ComposeRequired",
            &v92);
    v4 = v26;
    if ( v26 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v26;
      v87 = 5701;
      goto LABEL_14;
    }
    *((_DWORD *)this + 59) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"ContainsExpressPackage",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5705;
      goto LABEL_14;
    }
    *((_DWORD *)this + 61) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"ContainsSafeOSDUPackage",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5709;
      goto LABEL_14;
    }
    *((_DWORD *)this + 62) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"ContainsWUBox",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5713;
      goto LABEL_14;
    }
    *((_DWORD *)this + 63) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"ContainsReinstallCurrentLCU",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5717;
      goto LABEL_14;
    }
    *((_DWORD *)this + 64) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"CompDBsExpanded",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5721;
      goto LABEL_14;
    }
    *((_DWORD *)this + 65) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"OsDownloadComplete",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5725;
      goto LABEL_14;
    }
    *((_DWORD *)this + 68) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"PluginsDownloadComplete",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5729;
      goto LABEL_14;
    }
    *((_DWORD *)this + 69) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"RecreatePackageFileList",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5733;
      goto LABEL_14;
    }
    *((_DWORD *)this + 66) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"DeletedCorruptFilesCount",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5737;
      goto LABEL_14;
    }
    *((_DWORD *)this + 86) = v92;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"Persist\\DownloadedExpressFilesCount",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5741;
      goto LABEL_14;
    }
    *((_DWORD *)this + 87) = v92;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"MitigationExecuted",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5745;
      goto LABEL_14;
    }
    *((_DWORD *)this + 70) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"WinREServicingDone",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5749;
      goto LABEL_14;
    }
    *((_DWORD *)this + 77) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"StagingDone",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5753;
      goto LABEL_14;
    }
    *((_DWORD *)this + 78) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"StagingPostponed",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5757;
      goto LABEL_14;
    }
    *((_DWORD *)this + 79) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"ContainerServicingDone",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5761;
      goto LABEL_14;
    }
    *((_DWORD *)this + 80) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"MitigationScenario",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5765;
      goto LABEL_14;
    }
    *((_DWORD *)this + 115) = v92;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"UplevelSSUState",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5769;
      goto LABEL_14;
    }
    *((_DWORD *)this + 83) = v92;
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)(*((_QWORD *)this + 76) + 8LL) + 16LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"UplevelSSUCabPath",
           &bstrString);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5772;
      goto LABEL_14;
    }
    if ( bstrString )
    {
      v27 = to_wstring(v91, bstrString);
      v28 = (_OWORD *)((char *)this + 96);
      if ( *((_BYTE *)this + 128) )
      {
        std::wstring::operator=(v28, v27);
      }
      else
      {
        *v28 = 0;
        *((_QWORD *)this + 14) = 0;
        *((_QWORD *)this + 15) = 0;
        *v28 = *(_OWORD *)v27;
        *((_OWORD *)this + 7) = *(_OWORD *)(v27 + 16);
        *(_WORD *)v27 = 0;
        *(_QWORD *)(v27 + 16) = 0;
        *(_QWORD *)(v27 + 24) = 7;
        *((_BYTE *)this + 128) = 1;
      }
      std::wstring::~wstring(v91);
    }
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"DownloadingHistoryCIX",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5780;
      goto LABEL_14;
    }
    *((_BYTE *)this + 337) = v92 != 0;
    v92 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, int *))(*((_QWORD *)this + 76) + 8LL))(
           *((_QWORD *)this + 76) + 8LL,
           L"PostRebootWatsonUploaded",
           &v92);
    if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147023728 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v4;
      v87 = 5784;
      goto LABEL_14;
    }
    *((_DWORD *)this + 85) = v92 != 0;
    v97 = 0;
    v29 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 76) + 8LL)
                                                                         + 8LL))(
            *((_QWORD *)this + 76) + 8LL,
            L"OSDownloadSize",
            &v97);
    v4 = v29;
    if ( v29 == -2147023728 )
    {
      v4 = 0;
    }
    else if ( v29 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      v88 = v29;
      v87 = 5788;
LABEL_14:
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v10,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::Deserialize",
                                v87,
                                v88,
                                v89,
                                v90);
      goto LABEL_6;
    }
    *((_QWORD *)this + 47) = v97;
    v30 = *((_QWORD *)this + 75);
    if ( v30 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v30,
        2,
        L"CDeploymentSession: Deserialize SessionId = [%s]",
        *((_QWORD *)this + 6));
    v31 = *((_QWORD *)this + 75);
    if ( v31 )
    {
      v32 = &String2;
      if ( *((_QWORD *)this + 7) )
        v32 = (const WCHAR *)*((_QWORD *)this + 7);
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v31, 2, L"CDeploymentSession: Deserialize SessionData = [%s]", v32);
    }
    v33 = *((_QWORD *)this + 75);
    if ( v33 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v33, 2, L"CDeploymentSession: Deserialize UpdateState = [%ld]", v93);
    v34 = *((_QWORD *)this + 75);
    if ( v34 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v34,
        2,
        L"CDeploymentSession: Deserialize Scenario = [%ld]",
        *((unsigned int *)this + 114));
    v35 = *((_QWORD *)this + 75);
    v36 = L"TRUE";
    if ( v35 )
    {
      v37 = L"TRUE";
      if ( !*((_DWORD *)this + 53) )
        v37 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v35,
        2,
        L"CDeploymentSession: Deserialize RebootRequired = [%s]",
        v37);
    }
    v38 = *((_QWORD *)this + 75);
    if ( v38 )
    {
      v39 = L"TRUE";
      if ( !*((_DWORD *)this + 55) )
        v39 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v38,
        2,
        L"CDeploymentSession: Deserialize PreDownloadChecksComplete = [%s]",
        v39);
    }
    v40 = *((_QWORD *)this + 75);
    if ( v40 )
    {
      v41 = L"TRUE";
      if ( !*((_DWORD *)this + 56) )
        v41 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v40,
        2,
        L"CDeploymentSession: Deserialize ExpansionRequired = [%s]",
        v41);
    }
    v42 = *((_QWORD *)this + 75);
    if ( v42 )
    {
      v43 = L"TRUE";
      if ( !*((_DWORD *)this + 57) )
        v43 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v42,
        2,
        L"CDeploymentSession: Deserialize ExpansionComplete = [%s]",
        v43);
    }
    v44 = *((_QWORD *)this + 75);
    if ( v44 )
    {
      v45 = L"TRUE";
      if ( !*((_DWORD *)this + 58) )
        v45 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v44,
        2,
        L"CDeploymentSession: Deserialize StructureAppsComplete = [%s]",
        v45);
    }
    v46 = *((_QWORD *)this + 75);
    if ( v46 )
    {
      v47 = L"TRUE";
      if ( !*((_DWORD *)this + 54) )
        v47 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v46,
        2,
        L"CDeploymentSession: Deserialize IsRangeRequestSupported = [%s]",
        v47);
    }
    v48 = *((_QWORD *)this + 75);
    if ( v48 )
    {
      v49 = L"TRUE";
      if ( !*((_DWORD *)this + 59) )
        v49 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v48,
        2,
        L"CDeploymentSession: Deserialize ComposeRequired = [%s]",
        v49);
    }
    v50 = *((_QWORD *)this + 75);
    if ( v50 )
    {
      v51 = L"TRUE";
      if ( !*((_DWORD *)this + 60) )
        v51 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v50,
        2,
        L"CDeploymentSession: Deserialize ComposeComplete = [%s]",
        v51);
    }
    v52 = *((_QWORD *)this + 75);
    if ( v52 )
    {
      v53 = L"TRUE";
      if ( !*((_DWORD *)this + 61) )
        v53 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v52,
        2,
        L"CDeploymentSession: Deserialize ContainsExpressPackage = [%s]",
        v53);
    }
    v54 = *((_QWORD *)this + 75);
    if ( v54 )
    {
      v55 = L"TRUE";
      if ( !*((_DWORD *)this + 62) )
        v55 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v54,
        2,
        L"CDeploymentSession: Deserialize ContainsSafeOSDUPackage = [%s]",
        v55);
    }
    v56 = *((_QWORD *)this + 75);
    if ( v56 )
    {
      v57 = L"TRUE";
      if ( !*((_DWORD *)this + 63) )
        v57 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v56,
        2,
        L"CDeploymentSession: Deserialize ContainsWindowsUpdateBox = [%s]",
        v57);
    }
    v58 = *((_QWORD *)this + 75);
    if ( v58 )
    {
      v59 = L"TRUE";
      if ( !*((_DWORD *)this + 64) )
        v59 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v58,
        2,
        L"CDeploymentSession: Deserialize ContainsReinstallCurrentLCU = [%s]",
        v59);
    }
    v60 = *((_QWORD *)this + 75);
    if ( v60 )
    {
      v61 = L"TRUE";
      if ( !*((_DWORD *)this + 65) )
        v61 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v60,
        2,
        L"CDeploymentSession: Deserialize CompDBsExpanded = [%s]",
        v61);
    }
    v62 = *((_QWORD *)this + 75);
    if ( v62 )
    {
      v63 = L"TRUE";
      if ( !*((_DWORD *)this + 66) )
        v63 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v62,
        2,
        L"CDeploymentSession: Deserialize RecreatePackageFileList = [%s]",
        v63);
    }
    v64 = *((_QWORD *)this + 75);
    if ( v64 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v64,
        2,
        L"CDeploymentSession: Deserialize DeletedCorruptFilesCount = [%lu]",
        *((unsigned int *)this + 86));
    v65 = *((_QWORD *)this + 75);
    if ( v65 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v65,
        2,
        L"CDeploymentSession: Deserialize DownloadedExpressFilesCount = [%lu]",
        *((unsigned int *)this + 87));
    v66 = *((_QWORD *)this + 75);
    if ( v66 )
    {
      v67 = L"TRUE";
      if ( !*((_DWORD *)this + 70) )
        v67 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v66,
        2,
        L"CDeploymentSession: Deserialize MitigationExecuted = [%s]",
        v67);
    }
    v68 = *((_QWORD *)this + 75);
    if ( v68 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v68,
        2,
        L"CDeploymentSession: Deserialize MitigationScenario = [%ld]",
        *((unsigned int *)this + 115));
    v69 = *((_QWORD *)this + 75);
    if ( v69 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v69,
        2,
        L"CDeploymentSession: Deserialize OSDownloadSize = [%llu]",
        *((_QWORD *)this + 47));
    v70 = *((_QWORD *)this + 75);
    if ( v70 )
    {
      v71 = L"TRUE";
      if ( !*((_DWORD *)this + 77) )
        v71 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v70,
        2,
        L"CDeploymentSession: Deserialize WinREServicingDone = [%s]",
        v71);
    }
    v72 = *((_QWORD *)this + 75);
    if ( v72 )
    {
      v73 = L"TRUE";
      if ( !*((_DWORD *)this + 78) )
        v73 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v72, 2, L"CDeploymentSession: Deserialize StagingDone = [%s]", v73);
    }
    v74 = *((_QWORD *)this + 75);
    if ( v74 )
    {
      v75 = L"TRUE";
      if ( !*((_DWORD *)this + 79) )
        v75 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v74,
        2,
        L"CDeploymentSession: Deserialize StagingPostponed = [%s]",
        v75);
    }
    v76 = *((_QWORD *)this + 75);
    if ( v76 )
    {
      v77 = L"TRUE";
      if ( !*((_DWORD *)this + 80) )
        v77 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v76,
        2,
        L"CDeploymentSession: Deserialize ContainerServicingDone = [%s]",
        v77);
    }
    v78 = *((_QWORD *)this + 75);
    if ( v78 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v78,
        2,
        L"CDeploymentSession: Deserialize UplevelSSUState = [%ld]",
        *((unsigned int *)this + 83));
    v79 = *((_QWORD *)this + 75);
    if ( v79 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v79, 2, L"CDeploymentSession: Deserialize UplevelSSUCabPath = [%s]");
    v80 = *((_QWORD *)this + 75);
    if ( v80 )
    {
      v81 = L"TRUE";
      if ( !*((_BYTE *)this + 337) )
        v81 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v80,
        2,
        L"CDeploymentSession: Deserialize DownloadingHistoryCIX = [%s]",
        v81);
    }
    v82 = *((_QWORD *)this + 75);
    if ( v82 )
    {
      if ( !*((_DWORD *)this + 85) )
        v36 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v82,
        2,
        L"CDeploymentSession: Deserialize PostRebootWatsonUploaded = [%s]",
        v36);
    }
    v83 = (UaLiteManager *)*((_QWORD *)this + 82);
    if ( v83 )
      UaLiteManager::Deserialize(v83, *((struct IDlpManager *const *)this + 76));
    v84 = (DeploymentPluginManager *)*((_QWORD *)this + 81);
    if ( v84 )
      DeploymentPluginManager::Deserialize(v84, *((struct IDlpManager *const *)this + 76));
    goto LABEL_271;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x16CD,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v85);
  }
  return result;
}

```

## disassembly

```asm
0x180045dc0  mov     r11, rsp
0x180045dc3  push    rbx
0x180045dc4  push    rsi
0x180045dc5  push    rdi
0x180045dc6  push    r12
0x180045dc8  push    r14
0x180045dca  push    r15
0x180045dcc  sub     rsp, 0A8h
0x180045dd3  mov     [rsp+0D8h+var_A0], 0FFFFFFFFFFFFFFFEh
0x180045ddc  mov     rax, cs:__security_cookie
0x180045de3  xor     rax, rsp
0x180045de6  mov     [rsp+0D8h+var_48], rax
0x180045dee  mov     rdi, rcx
0x180045df1  xor     r12d, r12d
0x180045df4  mov     [r11-50h], r12
0x180045df8  mov     [r11-60h], r12
0x180045dfc  mov     [r11-68h], r12
0x180045e00  mov     [r11-70h], r12
0x180045e04  mov     [r11-78h], r12d
0x180045e08  mov     [r11-74h], r12d
0x180045e0c  mov     [r11-58h], r12
0x180045e10  mov     rcx, [rcx+260h]
0x180045e17  add     rcx, 8
0x180045e1b  mov     rax, [rcx]
0x180045e1e  lea     r8, [r11-50h]
0x180045e22  lea     rdx, aSessionid_0; "SessionId"
0x180045e29  mov     rax, [rax+10h]
0x180045e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e32  mov     ebx, eax
0x180045e34  test    eax, eax
0x180045e36  jns     short loc_180045E82
0x180045e38  mov     rcx, [rdi+258h]
0x180045e3f  test    rcx, rcx
0x180045e42  jnz     short loc_180045E49
0x180045e44  mov     ecx, r12d
0x180045e47  jmp     short loc_180045E78
0x180045e49  mov     [rsp+0D8h+var_B0], eax
0x180045e4d  mov     [rsp+0D8h+var_B8], 1612h
0x180045e55  lea     r9, aCdeploymentses_115; "CDeploymentSession::Deserialize"
0x180045e5c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180045e63  mov     edx, 4
0x180045e68  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180045e6d  mov     ecx, eax
0x180045e6f  test    ecx, ecx
0x180045e71  jns     short loc_180045E78
0x180045e73  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180045e78  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045e7d  jmp     loc_180047215
0x180045e82  mov     rsi, [rsp+0D8h+var_50]
0x180045e8a  test    rsi, rsi
0x180045e8d  jnz     short loc_180045EF4
0x180045e8f  mov     rsi, r12
0x180045e92  mov     edx, r12d
0x180045e95  lea     r8, [rdi+30h]
0x180045e99  mov     rcx, rsi; Src
0x180045e9c  call    ?CreateInternal@?$CImmutableStringsT@_WVCImmutableStringsPolicyDefault@@@@KAJPEB_WKPEAPEA_W@Z; CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(wchar_t const *,ulong,wchar_t * *)
0x180045ea1  mov     ebx, eax
0x180045ea3  test    eax, eax
0x180045ea5  jns     short loc_180045EAE
0x180045ea7  mov     ecx, eax
0x180045ea9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180045eae  mov     ecx, ebx
0x180045eb0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045eb5  test    ebx, ebx
0x180045eb7  jns     short loc_180045F1A
0x180045eb9  mov     rcx, [rdi+258h]
0x180045ec0  test    rcx, rcx
0x180045ec3  jz      loc_180045E44
0x180045ec9  mov     [rsp+0D8h+var_B0], ebx
0x180045ecd  mov     [rsp+0D8h+var_B8], 1613h
0x180045ed5  lea     r9, aCdeploymentses_115; "CDeploymentSession::Deserialize"
0x180045edc  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180045ee3  mov     edx, 4
0x180045ee8  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180045eed  mov     ecx, eax
0x180045eef  jmp     loc_180045E6F
0x180045ef4  mov     dword ptr [rsp+0D8h+var_A8], r12d
0x180045ef9  test    rsi, rsi
0x180045efc  jz      short loc_180045E92
0x180045efe  lea     rdx, [rsp+0D8h+var_A8]
0x180045f03  mov     rcx, rsi
0x180045f06  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEB_WPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(wchar_t const *,ulong *,ulong)
0x180045f0b  mov     ebx, eax
0x180045f0d  test    eax, eax
0x180045f0f  js      short loc_180045EA7
0x180045f11  mov     edx, dword ptr [rsp+0D8h+var_A8]
0x180045f15  jmp     loc_180045E95
0x180045f1a  mov     rcx, [rdi+260h]
0x180045f21  add     rcx, 8
0x180045f25  mov     rax, [rcx]
0x180045f28  lea     r8, [rsp+0D8h+var_60]
0x180045f2d  lea     rdx, aSessiondata_0; "SessionData"
0x180045f34  mov     rax, [rax+10h]
0x180045f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f3d  mov     ebx, eax
0x180045f3f  mov     r15d, 80000000h
0x180045f45  add     eax, r15d
0x180045f48  mov     esi, 80070490h
0x180045f4d  test    r15d, eax
0x180045f50  jnz     short loc_180045F77
0x180045f52  cmp     ebx, esi
0x180045f54  jz      short loc_180045F77
0x180045f56  mov     rcx, [rdi+258h]
0x180045f5d  test    rcx, rcx
0x180045f60  jz      loc_180045E44
0x180045f66  mov     [rsp+0D8h+var_B0], ebx
0x180045f6a  mov     [rsp+0D8h+var_B8], 1615h
0x180045f72  jmp     loc_180045ED5
0x180045f77  mov     r14, [rsp+0D8h+var_60]
0x180045f7c  test    r14, r14
0x180045f7f  jz      short loc_180045FE2
0x180045f81  mov     dword ptr [rsp+0D8h+var_A8], r12d
0x180045f86  lea     rdx, [rsp+0D8h+var_A8]
0x180045f8b  mov     rcx, r14
0x180045f8e  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEB_WPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(wchar_t const *,ulong *,ulong)
0x180045f93  mov     ebx, eax
0x180045f95  test    eax, eax
0x180045f97  js      short loc_180045FAF
0x180045f99  lea     r8, [rdi+38h]
0x180045f9d  mov     edx, dword ptr [rsp+0D8h+var_A8]
0x180045fa1  mov     rcx, r14; Src
0x180045fa4  call    ?CreateInternal@?$CImmutableStringsT@_WVCImmutableStringsPolicyDefault@@@@KAJPEB_WKPEAPEA_W@Z; CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(wchar_t const *,ulong,wchar_t * *)
0x180045fa9  mov     ebx, eax
0x180045fab  test    eax, eax
0x180045fad  jns     short loc_180045FB6
0x180045faf  mov     ecx, eax
0x180045fb1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180045fb6  mov     ecx, ebx
0x180045fb8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045fbd  test    ebx, ebx
0x180045fbf  jns     short loc_180045FE2
0x180045fc1  mov     rcx, [rdi+258h]
0x180045fc8  test    rcx, rcx
0x180045fcb  jz      loc_180045E44
0x180045fd1  mov     [rsp+0D8h+var_B0], ebx
0x180045fd5  mov     [rsp+0D8h+var_B8], 1618h
0x180045fdd  jmp     loc_180045ED5
0x180045fe2  mov     rcx, [rdi+260h]
0x180045fe9  add     rcx, 8
0x180045fed  mov     rax, [rcx]
0x180045ff0  lea     r8, [rsp+0D8h+var_68]
0x180045ff5  lea     rdx, aPackagefilelis_0; "PackageFileListPath"
0x180045ffc  mov     rax, [rax+10h]
0x180046000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046005  mov     ebx, eax
0x180046007  add     eax, r15d
0x18004600a  test    r15d, eax
0x18004600d  jnz     short loc_180046034
0x18004600f  cmp     ebx, esi
0x180046011  jz      short loc_180046034
0x180046013  mov     rcx, [rdi+258h]
0x18004601a  test    rcx, rcx
0x18004601d  jz      loc_180045E44
0x180046023  mov     [rsp+0D8h+var_B0], ebx
0x180046027  mov     [rsp+0D8h+var_B8], 161Bh
0x18004602f  jmp     loc_180045ED5
0x180046034  mov     r14, [rsp+0D8h+var_68]
0x180046039  test    r14, r14
0x18004603c  jz      short loc_1800460A2
0x18004603e  mov     dword ptr [rsp+0D8h+var_A8], r12d
0x180046043  lea     rdx, [rsp+0D8h+var_A8]
0x180046048  mov     rcx, r14
0x18004604b  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEB_WPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(wchar_t const *,ulong *,ulong)
0x180046050  mov     ebx, eax
0x180046052  test    eax, eax
0x180046054  js      short loc_18004606F
0x180046056  lea     r8, [rdi+200h]
0x18004605d  mov     edx, dword ptr [rsp+0D8h+var_A8]
0x180046061  mov     rcx, r14; Src
0x180046064  call    ?CreateInternal@?$CImmutableStringsT@_WVCImmutableStringsPolicyDefault@@@@KAJPEB_WKPEAPEA_W@Z; CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(wchar_t const *,ulong,wchar_t * *)
0x180046069  mov     ebx, eax
0x18004606b  test    eax, eax
0x18004606d  jns     short loc_180046076
0x18004606f  mov     ecx, eax
0x180046071  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180046076  mov     ecx, ebx
0x180046078  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004607d  test    ebx, ebx
0x18004607f  jns     short loc_1800460A2
0x180046081  mov     rcx, [rdi+258h]
0x180046088  test    rcx, rcx
0x18004608b  jz      loc_180045E44
0x180046091  mov     [rsp+0D8h+var_B0], ebx
0x180046095  mov     [rsp+0D8h+var_B8], 161Eh
0x18004609d  jmp     loc_180045ED5
0x1800460a2  mov     rcx, [rdi+260h]
0x1800460a9  add     rcx, 8
0x1800460ad  mov     rax, [rcx]
0x1800460b0  lea     r8, [rsp+0D8h+var_74]
0x1800460b5  lea     rdx, aState; "State"
0x1800460bc  mov     rax, [rax]
0x1800460bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460c4  mov     ebx, eax
0x1800460c6  test    eax, eax
0x1800460c8  jns     short loc_1800460EB
0x1800460ca  mov     rcx, [rdi+258h]
0x1800460d1  test    rcx, rcx
0x1800460d4  jz      loc_180045E44
0x1800460da  mov     [rsp+0D8h+var_B0], eax
0x1800460de  mov     [rsp+0D8h+var_B8], 1621h
0x1800460e6  jmp     loc_180045ED5
0x1800460eb  mov     edx, [rsp+0D8h+var_74]
0x1800460ef  mov     rcx, rdi
0x1800460f2  call    ?StateSet@CDeploymentSession@@AEAAJW4MoUpdateState@@@Z; CDeploymentSession::StateSet(MoUpdateState)
0x1800460f7  mov     ebx, eax
0x1800460f9  test    eax, eax
0x1800460fb  jns     short loc_18004611E
0x1800460fd  mov     rcx, [rdi+258h]
0x180046104  test    rcx, rcx
0x180046107  jz      loc_180045E44
0x18004610d  mov     [rsp+0D8h+var_B0], eax
0x180046111  mov     [rsp+0D8h+var_B8], 1622h
0x180046119  jmp     loc_180045ED5
0x18004611e  mov     [rsp+0D8h+var_78], r12d
0x180046123  mov     rcx, [rdi+260h]
0x18004612a  add     rcx, 8
0x18004612e  mov     rax, [rcx]
0x180046131  lea     r8, [rsp+0D8h+var_78]
0x180046136  lea     rdx, aScenario; "Scenario"
0x18004613d  mov     rax, [rax]
0x180046140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046145  mov     ebx, eax
0x180046147  test    eax, eax
0x180046149  jns     short loc_18004616C
0x18004614b  mov     rcx, [rdi+258h]
0x180046152  test    rcx, rcx
0x180046155  jz      loc_180045E44
0x18004615b  mov     [rsp+0D8h+var_B0], eax
0x18004615f  mov     [rsp+0D8h+var_B8], 1625h
0x180046167  jmp     loc_180045ED5
0x18004616c  mov     eax, [rsp+0D8h+var_78]
0x180046170  mov     [rdi+1C8h], eax
0x180046176  mov     [rsp+0D8h+var_78], r12d
0x18004617b  mov     rcx, [rdi+260h]
0x180046182  add     rcx, 8
0x180046186  mov     rax, [rcx]
0x180046189  lea     r8, [rsp+0D8h+var_78]
0x18004618e  lea     rdx, aRebootrequired_0; "RebootRequired"
0x180046195  mov     rax, [rax]
0x180046198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004619d  mov     ebx, eax
0x18004619f  add     eax, r15d
0x1800461a2  test    r15d, eax
0x1800461a5  jnz     short loc_1800461CC
0x1800461a7  cmp     ebx, esi
0x1800461a9  jz      short loc_1800461CC
0x1800461ab  mov     rcx, [rdi+258h]
0x1800461b2  test    rcx, rcx
0x1800461b5  jz      loc_180045E44
0x1800461bb  mov     [rsp+0D8h+var_B0], ebx
0x1800461bf  mov     [rsp+0D8h+var_B8], 1629h
0x1800461c7  jmp     loc_180045ED5
0x1800461cc  mov     eax, r12d
0x1800461cf  cmp     [rsp+0D8h+var_78], r12d
0x1800461d4  setnz   al
0x1800461d7  mov     [rdi+0D4h], eax
0x1800461dd  mov     [rsp+0D8h+var_78], r12d
0x1800461e2  mov     rcx, [rdi+260h]
0x1800461e9  add     rcx, 8
0x1800461ed  mov     rax, [rcx]
0x1800461f0  lea     r8, [rsp+0D8h+var_78]
0x1800461f5  lea     rdx, aPredownloadche; "PreDownloadCheckComplete"
0x1800461fc  mov     rax, [rax]
0x1800461ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046204  mov     ebx, eax
0x180046206  test    eax, eax
0x180046208  jns     short loc_18004622B
0x18004620a  mov     rcx, [rdi+258h]
0x180046211  test    rcx, rcx
0x180046214  jz      loc_180045E44
0x18004621a  mov     [rsp+0D8h+var_B0], eax
0x18004621e  mov     [rsp+0D8h+var_B8], 162Dh
0x180046226  jmp     loc_180045ED5
0x18004622b  mov     eax, r12d
0x18004622e  cmp     [rsp+0D8h+var_78], r12d
0x180046233  setnz   al
0x180046236  mov     [rdi+0DCh], eax
0x18004623c  mov     [rsp+0D8h+var_78], r12d
0x180046241  mov     rcx, [rdi+260h]
0x180046248  add     rcx, 8
0x18004624c  mov     rax, [rcx]
0x18004624f  lea     r8, [rsp+0D8h+var_78]
0x180046254  lea     rdx, aExpansionrequi; "ExpansionRequired"
0x18004625b  mov     rax, [rax]
0x18004625e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046263  mov     ebx, eax
0x180046265  test    eax, eax
0x180046267  jns     short loc_18004628A
0x180046269  mov     rcx, [rdi+258h]
0x180046270  test    rcx, rcx
0x180046273  jz      loc_180045E44
0x180046279  mov     [rsp+0D8h+var_B0], eax
0x18004627d  mov     [rsp+0D8h+var_B8], 1631h
0x180046285  jmp     loc_180045ED5
0x18004628a  mov     eax, r12d
0x18004628d  cmp     [rsp+0D8h+var_78], r12d
0x180046292  setnz   al
0x180046295  mov     [rdi+0E0h], eax
0x18004629b  mov     [rsp+0D8h+var_78], r12d
0x1800462a0  mov     rcx, [rdi+260h]
  ... truncated ...
```
