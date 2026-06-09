# WaasMedic::CWaasRemediation::RunPluginsInCapsule(bool,winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,WaasMedic::ICancellable *,ushort const *,WaasMedic::RunMode,ushort const *,char const *,ulong *,ulong *,bool *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,WaasMedic::CDeferManager &)

- ea: `0x180018d3c`
- end: `0x18001a4f5`
- name: `?RunPluginsInCapsule@CWaasRemediation@WaasMedic@@QEAAJ_NW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@PEAUICancellable@2@PEBGW4RunMode@2@3PEBDPEAK6PEA_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCDeferManager@2@@Z`
- size: `6073`
- prototype: `__int64 __usercall@<rax>(WaasMedic::CWaasRemediation *this@<rcx>, __int64, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `50`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017a60`
- `0x1800184b0`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000f658`
- `0x18000f860`
- `0x1800101c8`
- `0x18001039c`
- `0x18001123c`
- `0x180011fdc`
- `0x180012540`
- `0x1800128ac`
- `0x180012b54`
- `0x180015310`
- `0x1800153f4`
- `0x1800154d8`
- `0x180018d3c`
- `0x18001aa34`
- `0x18001ab9c`
- `0x18001ad04`
- `0x18001ae6c`
- `0x18001afd4`
- `0x18001b110`
- `0x18001b414`
- `0x18001d474`
- `0x18001d5b0`
- `0x18001e6c8`
- `0x18001e780`
- `0x18001e83c`
- `0x18001ecdc`
- `0x18001f178`
- `0x18001f330`
- `0x18001f3e8`
- `0x18001f460`
- `0x18001f668`
- `0x18001fd30`
- `0x1800202d8`
- `0x180020b48`
- `0x180020c18`
- `0x180020e6c`
- `0x180020fd4`
- `0x18002130c`
- `0x180021408`
- `0x1800288a0`
- `0x180029a30`
- `0x18002a4e4`
- `0x18002e56c`
- `0x18002e81c`
- `0x180033894`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f72`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800195cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800195cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800192c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019d87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800192c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019d87`
- `OLEAUT32!__imp_SysAllocString` at `0x1800192fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800194df`
- `OLEAUT32!__imp_SysAllocString` at `0x180019dbd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800192fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800194df`
- `OLEAUT32!__imp_SysAllocString` at `0x180019dbd`
- `OLEAUT32!__imp_VariantInit` at `0x180019133`
- `OLEAUT32!__imp_VariantInit` at `0x18001913e`
- `OLEAUT32!__imp_VariantInit` at `0x180019149`
- `OLEAUT32!__imp_VariantInit` at `0x180019154`
- `OLEAUT32!__imp_VariantInit` at `0x18001915f`
- `OLEAUT32!__imp_VariantInit` at `0x18001916d`
- `OLEAUT32!__imp_VariantInit` at `0x18001917b`
- `OLEAUT32!__imp_VariantInit` at `0x1800192d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800194b2`
- `OLEAUT32!__imp_VariantInit` at `0x180019d91`
- `OLEAUT32!__imp_VariantInit` at `0x180019133`
- `OLEAUT32!__imp_VariantInit` at `0x18001913e`
- `OLEAUT32!__imp_VariantInit` at `0x180019149`
- `OLEAUT32!__imp_VariantInit` at `0x180019154`
- `OLEAUT32!__imp_VariantInit` at `0x18001915f`
- `OLEAUT32!__imp_VariantInit` at `0x18001916d`
- `OLEAUT32!__imp_VariantInit` at `0x18001917b`
- `OLEAUT32!__imp_VariantInit` at `0x1800192d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800194b2`
- `OLEAUT32!__imp_VariantInit` at `0x180019d91`
- `OLEAUT32!__imp_VariantClear` at `0x18001a332`
- `OLEAUT32!__imp_VariantClear` at `0x18001a347`
- `OLEAUT32!__imp_VariantClear` at `0x18001a359`
- `OLEAUT32!__imp_VariantClear` at `0x18001a36b`
- `OLEAUT32!__imp_VariantClear` at `0x18001a37d`
- `OLEAUT32!__imp_VariantClear` at `0x18001a38f`
- `OLEAUT32!__imp_VariantClear` at `0x18001a3a1`
- `OLEAUT32!__imp_VariantClear` at `0x18001a332`
- `OLEAUT32!__imp_VariantClear` at `0x18001a347`
- `OLEAUT32!__imp_VariantClear` at `0x18001a359`
- `OLEAUT32!__imp_VariantClear` at `0x18001a36b`
- `OLEAUT32!__imp_VariantClear` at `0x18001a37d`
- `OLEAUT32!__imp_VariantClear` at `0x18001a38f`
- `OLEAUT32!__imp_VariantClear` at `0x18001a3a1`

## string_xrefs

- `0x180018ec6`: `EnumeratePluginActivity`
- `0x180018f23`: `Initializing plugin`
- `0x180018fa2`: `Failed to initialize plugin. hr = 0x%08x`
- `0x180018fc0`: `Plugin_Init failed. hr = 0x%08x`
- `0x18001a3dc`: `Plugin enumeration failed or nullptr returned. hr=0x%08x`
- `0x18001a3c6`: `Waas Remediation engine received cancellation request for plugin %s.`
- `0x1800191e6`: `Plugin %s will be skipped due to cancel request.`
- `0x18001920a`: `Plugin "%s" is not specified to run. Nothing to do..`
- `0x18001924e`: `Failed while checking for maintenance action for plugin %s. hr = 0x%08x.`
- `0x18001926e`: `No existing maintenance found for the plugin %s. Skipping.`
- `0x1800192ab`: `Failed while checking for deferral action for plugin %s. hr = 0x%08x.`
- `0x1800192ba`: `No existing deferral found for the plugin %s. Skipping.`
- `0x18001941b`: `Plugin is disabled.`
- `0x180019460`: `Plugin %s is MCP-enabled for targeted detection. The standard applicability block is bypassed.`
- `0x180019469`: `Plugin %s is not MCP-enabled. Skipping in targeted detection run.`
- `0x180019499`: `Plugin %s is subject to interval block. The block does not apply on maintenance or deferral runs.`
- `0x18001950c`: `Plugin is %s not applicable. Skipping.`
- `0x180019561`: `Failed to create sandbox process for %s.  hr = 0x%08x`
- `0x1800195bb`: `Failed to load library on the WaaSMedicAgent with hr = 0x%08x.  Trying again...`
- `0x1800195dc`: `Failed to load library by the WaaSMedicAgent hr = 0x%08x`
- `0x180019683`: `Failed to set cV on plugin collection`
- `0x18001983a`: `Plugin "%s" tempStatus = 0x%08x; currPluginDetectionStatus = 0x%08x.`
- `0x180019856`: `Plugin %s was triggered due to manual remediation campaign. No detection performed.`
- `0x18001989f`: `Plugin %s did not detect the remediation condition. Nothing to do.`
- `0x1800198c9`: `Failed to unset an existing maintenance action for plugin %s. hr = 0x%08x`
- `0x1800198f3`: `Failed to unset an existing deferral action for plugin %s. hr = 0x%08x`
- `0x180019917`: `Plugin "%s" detected the remediation condition.`
- `0x180019c8b`: `Plugin %s action execution is being deferred.`
- `0x180019abe`: `Plugin %s remediation requires maintenance. Proceeding since this is maintenance run.`
- `0x180019be8`: `Plugin %s remediation action will be run at next maintenance. Current mode: %d`
- `0x180019a96`: `Future deferral already pending for %s. No action will be performed.`
- `0x180019a13`: `Deferred time for plugin %s passed. This is deferred run, perform action now.`
- `0x180019a4f`: `Deferred task due time %s passed. Skipping as mode required/current %d/%d.`
- `0x180019cc7`: `Plugin %s runs without deferral/maintenance. Will remediate now. Run mode is: %d.`
- `0x180019b38`: `ThreadExecutionTimeoutInSeconds`
- `0x180019bc9`: `Unable to read plugin setting for execution timeout. hr = 0x%08x`
- `0x180019cf8`: `Plugin "%s" is set to detection only. Nothing to do.`
- `0x180019e41`: `Plugin %s was canceled during execution.`
- `0x180019e63`: `Plugin %s failed to perform remediation action with error = 0x%08x`
- `0x180019f2e`: `PluginRunCount`
- `0x180019f94`: `PluginRunCount`
- `0x180019fb8`: `PluginRunCount`
- `0x180019f6d`: `Unexpected VARIANT data retrieved for plugin run count. V_VT=%d`
- `0x18001937d`: `PluginManualRunCount`
- `0x18001a005`: `PluginManualRunCount`
- `0x18001a023`: `PluginManualRunCount`
- `0x180019fe2`: `Unexpected VARIANT data retrieved for plugin manual run count. V_VT=%d`
- `0x18001a0f4`: `Failed to read %s. hr = 0x%08x`
- `0x18001a129`: `Medic engine error encountered when processing plugin %s: hr = 0x%08x`
- `0x18001a40e`: `SandBoxFreePluginLibrary failed. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall WaasMedic::CWaasRemediation::RunPluginsInCapsule(
        WaasMedic::CWaasRemediation *this,
        char a2,
        unsigned int a3,
        unsigned __int8 (__fastcall ***a4)(_QWORD),
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int16 *a7,
        __int64 a8,
        _DWORD *a9,
        _DWORD *a10,
        _BYTE *a11,
        void *a12,
        WaasMedic::CDeferManager *a13)
{
  int v14; // r14d
  signed int HasDeferredAction_State; // edi
  __int64 v16; // rax
  __int64 (*ProcAddress)(void); // rbx
  signed int LastError; // eax
  __int64 v19; // rax
  int v20; // eax
  bool v21; // zf
  int v22; // eax
  int v23; // eax
  bool *v24; // rdx
  int IsProcessAdmin; // eax
  const wchar_t *v26; // r8
  int v27; // eax
  unsigned __int16 *v28; // rsi
  WaasMedic::CWaasRemediation *v29; // rcx
  LONG v30; // ebx
  signed int v31; // r12d
  unsigned __int64 v32; // rdx
  int v33; // ebx
  __int64 v34; // r9
  int v35; // ebx
  signed int v36; // eax
  unsigned __int64 v37; // rdx
  int Sandbox; // eax
  int Library; // eax
  WaasMedic::CSandboxRpcWrapper *v40; // rcx
  const unsigned __int16 *v41; // rdx
  WaasMedic::CSandboxRpcWrapper *v42; // rcx
  unsigned __int16 **v43; // r8
  const unsigned __int16 *v44; // r8
  const unsigned __int16 *v45; // rdx
  WaasMedic::CSandboxRpcWrapper *v46; // rcx
  const unsigned __int16 *v47; // r8
  signed int v48; // ebx
  bool v49; // bl
  unsigned int v50; // ebx
  unsigned int v51; // eax
  BOOL v52; // eax
  WaasMedic::CDeferManager *v53; // rbx
  int v54; // eax
  int v55; // eax
  bool v56; // zf
  void *v57; // rbx
  bool v58; // zf
  WaasMedic::CDeferManager *v59; // rbx
  int v60; // eax
  int v61; // eax
  int v62; // eax
  int v63; // eax
  __int64 v64; // rbx
  __int64 (__fastcall *v65)(__int64, __int128 *, __int128 *, unsigned int *); // rdi
  __int64 v66; // r8
  __int64 v67; // r8
  int v68; // eax
  int v69; // eax
  unsigned __int64 v70; // rdx
  int v71; // ebx
  int v72; // eax
  bool v73; // dl
  int v74; // ebx
  int v75; // eax
  LONG lVal; // ebx
  int v77; // eax
  int v78; // eax
  __int64 v79; // rbx
  __int64 (__fastcall *v80)(__int64, __int128 *, __int128 *, _DWORD *); // r14
  __int64 v81; // r8
  int v82; // r14d
  void *v83; // rdx
  bool v84; // bl
  __int64 v85; // rax
  CJsonHelper *v86; // rcx
  CJsonHelper *v87; // rcx
  CJsonHelper *v88; // rcx
  bool v89; // al
  HRESULT v90; // eax
  HRESULT v91; // eax
  HRESULT v92; // eax
  HRESULT v93; // eax
  HRESULT v94; // eax
  HRESULT v95; // eax
  HRESULT v96; // eax
  int v97; // eax
  int v98; // ebx
  __int64 v100; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v101[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v102; // [rsp+54h] [rbp-ACh]
  bool v103; // [rsp+58h] [rbp-A8h] BYREF
  char v104; // [rsp+59h] [rbp-A7h]
  char v105; // [rsp+5Ah] [rbp-A6h]
  bool v106; // [rsp+5Bh] [rbp-A5h]
  char v107; // [rsp+5Ch] [rbp-A4h]
  char v108; // [rsp+5Dh] [rbp-A3h] BYREF
  char v109; // [rsp+5Eh] [rbp-A2h] BYREF
  bool v110; // [rsp+5Fh] [rbp-A1h] BYREF
  char v111; // [rsp+60h] [rbp-A0h]
  char v112; // [rsp+61h] [rbp-9Fh]
  char v113; // [rsp+62h] [rbp-9Eh]
  char v114; // [rsp+63h] [rbp-9Dh]
  unsigned int v115; // [rsp+64h] [rbp-9Ch] BYREF
  int v116; // [rsp+68h] [rbp-98h]
  int v117; // [rsp+6Ch] [rbp-94h]
  int v118; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v119; // [rsp+74h] [rbp-8Ch] BYREF
  int v120; // [rsp+78h] [rbp-88h] BYREF
  int v121; // [rsp+7Ch] [rbp-84h]
  int v122; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v123; // [rsp+84h] [rbp-7Ch]
  int v124; // [rsp+88h] [rbp-78h]
  WaasMedic::CDeferManager *v125; // [rsp+90h] [rbp-70h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v127; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME v128; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD v129[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v130; // [rsp+C8h] [rbp-38h]
  struct PluginNameAndOrder *v131; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v132[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v133; // [rsp+E0h] [rbp-20h]
  void *Src; // [rsp+E8h] [rbp-18h]
  __int64 v135; // [rsp+F0h] [rbp-10h]
  VARIANTARG v136; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int8 (__fastcall ***v137)(_QWORD); // [rsp+110h] [rbp+10h]
  unsigned __int16 *v138; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v139; // [rsp+120h] [rbp+20h]
  _DWORD *v140; // [rsp+128h] [rbp+28h]
  _DWORD *v141; // [rsp+130h] [rbp+30h]
  _BYTE *v142; // [rsp+138h] [rbp+38h]
  VARIANTARG v143; // [rsp+140h] [rbp+40h] BYREF
  VARIANTARG pvarg; // [rsp+158h] [rbp+58h] BYREF
  VARIANTARG v145; // [rsp+170h] [rbp+70h] BYREF
  VARIANTARG v146; // [rsp+188h] [rbp+88h] BYREF
  VARIANTARG v147; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v148; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v149; // [rsp+1C8h] [rbp+C8h]
  __int128 v150; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v151; // [rsp+1E8h] [rbp+E8h]
  _BYTE v152[8]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v153; // [rsp+208h] [rbp+108h]
  __int128 v154; // [rsp+210h] [rbp+110h]
  __int64 v155; // [rsp+220h] [rbp+120h]
  __int128 v156; // [rsp+228h] [rbp+128h]
  __int64 v157; // [rsp+238h] [rbp+138h]
  __int64 v158; // [rsp+240h] [rbp+140h]
  __int64 v159; // [rsp+248h] [rbp+148h]
  _QWORD v160[42]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v161[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _QWORD v162[42]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _QWORD v163[42]; // [rsp+520h] [rbp+420h] BYREF
  OLECHAR v164[24]; // [rsp+670h] [rbp+570h] BYREF
  OLECHAR v165[24]; // [rsp+6A0h] [rbp+5A0h] BYREF
  OLECHAR psz[24]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v137 = a4;
  v123 = a3;
  v105 = a2;
  Src = a12;
  v135 = a8;
  v139 = a7;
  v138 = a5;
  v140 = a9;
  v141 = a10;
  v142 = a11;
  v125 = a13;
  v121 = 0;
  v14 = 0;
  v116 = 0;
  v120 = 0;
  v152[0] = 0;
  v153 = 0;
  v154 = 0;
  v155 = 0;
  v156 = 0;
  v157 = 0;
  v158 = 7;
  LOWORD(v156) = 0;
  v159 = 0;
  v131 = 0;
  if ( a9 )
    *a9 = 0;
  if ( a11 )
    *a11 = 1;
  if ( a10 )
    *a10 = 0;
  std::wstring::wstring(&v148, *((_QWORD *)this + 3) + 136LL);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v163,
    "SandboxActivity");
  v163[0] = &WaasMedic::TelemetryProvider::SandboxActivity::`vftable';
  WaasMedic::TelemetryProvider::SandboxActivity::StartActivity(v163, a8, a7, &v148);
  std::wstring::~wstring(&v148);
  std::wstring::wstring(v161, *((_QWORD *)this + 3) + 136LL);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v162,
    "EnumeratePluginActivity");
  v162[0] = &WaasMedic::TelemetryProvider::EnumeratePluginActivity::`vftable';
  WaasMedic::TelemetryProvider::EnumeratePluginActivity::StartActivity(v162, a8, a7, v161);
  std::wstring::~wstring(v161);
  if ( !*((_QWORD *)this + 8) )
  {
    HasDeferredAction_State = -2147312566;
LABEL_18:
    v19 = *((_QWORD *)this + 3);
LABEL_19:
    if ( v19 )
      ++*(_DWORD *)(v19 + 124);
    LogLevelW(2u, L"Plugin_Init failed. hr = 0x%08x", (unsigned int)HasDeferredAction_State);
    goto LABEL_272;
  }
  LogLevelW(4u, L"Initializing plugin");
  v16 = WaasMedic::ws2s(&v148, SandboxAction::Plugin::init);
  if ( *(_QWORD *)(v16 + 24) > 0xFu )
    v16 = *(_QWORD *)v16;
  ProcAddress = GetProcAddress(*((HMODULE *)this + 8), (LPCSTR)v16);
  std::string::~string(&v148);
  if ( ProcAddress )
  {
    v20 = ProcAddress();
    HasDeferredAction_State = v20;
    if ( v20 < 0 )
    {
      LogLevelW(2u, L"Failed to initialize plugin. hr = 0x%08x", (unsigned int)v20);
      goto LABEL_18;
    }
    v19 = *((_QWORD *)this + 3);
  }
  else
  {
    LastError = GetLastError();
    HasDeferredAction_State = LastError;
    if ( LastError > 0 )
      HasDeferredAction_State = (unsigned __int16)LastError | 0x80070000;
    v19 = *((_QWORD *)this + 3);
    if ( HasDeferredAction_State < 0 )
      goto LABEL_19;
  }
  if ( v19 )
    ++*(_DWORD *)(v19 + 120);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl) )
    v21 = ((a6 - 1) & 0xFFFFFFFB) == 0;
  else
    v21 = a6 == 1;
  if ( v21 && !a12 )
  {
    LogLevelW(2u, L"For valid Detection run, return string needs to be provided.");
    HasDeferredAction_State = -2147467261;
    goto LABEL_272;
  }
  v22 = WaasMedic::CWaasRemediation::EnumeratePlugins(this, &v120, &v131);
  HasDeferredAction_State = v22;
  if ( v22 < 0 || !v131 )
  {
    LogLevelW(2u, L"Plugin enumeration failed or nullptr returned. hr=0x%08x", (unsigned int)v22);
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v162,
      (unsigned int)HasDeferredAction_State);
    goto LABEL_272;
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v162,
    0);
  v23 = WaasMedic::CSandboxRpcWrapper::Init(
          (WaasMedic::CSandboxRpcWrapper *)v152,
          *((struct TraceLoggingCorrelationVector **)this + 7));
  HasDeferredAction_State = v23;
  if ( v23 < 0 )
  {
    LogLevelW(2u, L"Failed to initialize sandbox. hr = 0x%08x", (unsigned int)v23);
    v14 = HasDeferredAction_State;
    goto LABEL_272;
  }
  v108 = 0;
  IsProcessAdmin = WaasMedic::IsProcessAdmin((WaasMedic *)&v108, v24);
  HasDeferredAction_State = IsProcessAdmin;
  if ( IsProcessAdmin < 0 )
  {
    LogLevelW(2u, L"Failed to determine if caller is Admin. hr = 0x%08x", (unsigned int)IsProcessAdmin);
    goto LABEL_272;
  }
  v107 = 1;
  v26 = &word_180073298;
  if ( v108 != 1 )
    v26 = L"not";
  LogLevelW(5u, L"Caller is %s admin", v26);
  v27 = 0;
  v124 = 0;
  while ( v27 < v120 )
  {
    v28 = (unsigned __int16 *)((char *)v131 + 516 * v27);
    if ( v137 && (**v137)(v137) )
    {
      LogLevelW(4u, L"Waas Remediation engine received cancellation request for plugin %s.", v28);
      break;
    }
    v117 = 0;
    v101[0] = 0;
    v109 = 0;
    v118 = 0;
    v106 = 0;
    VariantInit(&pvarg);
    VariantInit(&v143);
    VariantInit(&v136);
    VariantInit(&v145);
    VariantInit(&v127);
    VariantInit(&v147);
    VariantInit(&v146);
    SystemTimeAsFileTime = 0;
    v30 = 0;
    v102 = 0;
    v130 = 0;
    v129[0] = 0;
    v129[1] = 2;
    v133 = 0;
    v132[0] = 120;
    v132[1] = 2;
    v31 = 2392065;
    v115 = 2392065;
    v119 = 2375681;
    v103 = 0;
    v110 = 0;
    v111 = 0;
    v112 = 0;
    v113 = 0;
    v114 = 0;
    v104 = 0;
    if ( *((_BYTE *)this + 34) )
    {
      LogLevelW(4u, L"Plugin %s will be skipped due to cancel request.", v28);
    }
    else if ( WaasMedic::CWaasRemediation::IsPluginNeedToSkipBasedOnPluginList(v29, v138, v28) )
    {
      LogLevelW(4u, L"Plugin \"%s\" is not specified to run. Nothing to do..", v28);
      v31 = 2375681;
    }
    else
    {
      v104 = 1;
      if ( a6 != 3 )
      {
        if ( a6 != 4 )
          goto LABEL_57;
        HasDeferredAction_State = WaasMedic::CDeferManager::HasDeferredAction_State(v125, v28, &v110);
        if ( HasDeferredAction_State < 0 )
        {
          LogLevelW(
            2u,
            L"Failed while checking for deferral action for plugin %s. hr = 0x%08x.",
            v28,
            (unsigned int)HasDeferredAction_State);
          goto LABEL_63;
        }
        if ( v110 )
        {
LABEL_57:
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          VariantInit(&pvarg);
          pvarg.vt = 8;
          v33 = WaasMedic::TimeHelper::FileTimeToString(psz, v32, &SystemTimeAsFileTime);
          if ( v33 >= 0 )
          {
            pvarg.llVal = (LONGLONG)SysAllocString(psz);
            if ( !pvarg.llVal )
            {
              HasDeferredAction_State = -2147024882;
              v33 = -2147024882;
              LogLevelW(2u, L"Failed to allocate memory for FILETIME string!");
              goto LABEL_61;
            }
          }
          HasDeferredAction_State = v33;
          if ( v33 < 0 )
          {
LABEL_61:
            LogLevelW(2u, L"Failed to convert filetime to string for %s! hr = 0x%08x.", v28, (unsigned int)v33);
            v31 = v33;
LABEL_62:
            v30 = v102;
            goto LABEL_63;
          }
          v111 = 1;
          v35 = 0;
          v104 = 0;
          LOBYTE(v34) = v105;
          v36 = WaasMedic::CWaasRemediation::CheckIfPluginIsRunnable(
                  this,
                  v123,
                  v28,
                  v34,
                  &v115,
                  &v119,
                  &v109,
                  v101,
                  &v118);
          v117 = v36;
          if ( v36 < 0 )
          {
            v115 = v36;
            goto LABEL_62;
          }
          if ( !v109 )
          {
            v31 = 2392068;
            LogLevelW(4u, L"Plugin is disabled.", v28);
            goto LABEL_62;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl)
            && a6 == 5 )
          {
            if ( WaasMedic::CWaasRemediation::IsPluginMcpEnabled(this, v28) )
            {
              LogLevelW(
                4u,
                L"Plugin %s is MCP-enabled for targeted detection. The standard applicability block is bypassed.",
                v28);
              goto LABEL_82;
            }
            LogLevelW(4u, L"Plugin %s is not MCP-enabled. Skipping in targeted detection run.", v28);
LABEL_77:
            v31 = 2375681;
            goto LABEL_62;
          }
          if ( !v101[0] )
          {
            if ( v118 != 3 || a6 - 3 > 1 )
            {
              LogLevelW(4u, L"Plugin is %s not applicable. Skipping.", v28);
              goto LABEL_77;
            }
            LogLevelW(
              4u,
              L"Plugin %s is subject to interval block. The block does not apply on maintenance or deferral runs.",
              v28);
LABEL_82:
            v118 = 0;
          }
          VariantInit(&v143);
          v143.vt = 8;
          v31 = WaasMedic::TimeHelper::FileTimeToString(v164, v37, &SystemTimeAsFileTime);
          if ( v31 >= 0 )
          {
            v143.llVal = (LONGLONG)SysAllocString(v164);
            if ( !v143.llVal )
            {
              v31 = -2147024882;
              LogLevelW(2u, L"Failed to allocate memory for FILETIME string!");
              HasDeferredAction_State = -2147024882;
LABEL_88:
              LogLevelW(2u, L"Failed to convert filetime to string for %s! hr = 0x%08x.", v28, (unsigned int)v31);
              goto LABEL_62;
            }
          }
          HasDeferredAction_State = v31;
          if ( v31 < 0 )
            goto LABEL_88;
          if ( v107 )
          {
            Sandbox = WaasMedic::CSandboxRpcWrapper::CreateSandbox((WaasMedic::CSandboxRpcWrapper *)v152);
            HasDeferredAction_State = Sandbox;
            if ( Sandbox < 0 )
            {
              LogLevelW(2u, L"Failed to create sandbox process for %s.  hr = 0x%08x", v28, (unsigned int)Sandbox);
LABEL_92:
              v31 = HasDeferredAction_State;
              v116 = HasDeferredAction_State;
              goto LABEL_62;
            }
            HasDeferredAction_State = WaasMedic::CSandboxRpcWrapper::ConnectToSandbox((WaasMedic::CSandboxRpcWrapper *)v152);
            if ( HasDeferredAction_State < 0 )
            {
              LogLevelW(2u, L"Unable to establish connection hr = 0x%08x", (unsigned int)HasDeferredAction_State);
              goto LABEL_92;
            }
            while ( 1 )
            {
              Library = WaasMedic::CSandboxRpcWrapper::SandboxLoadLibrary((WaasMedic::CSandboxRpcWrapper *)v152, v139);
              HasDeferredAction_State = Library;
              if ( Library >= 0 )
                break;
              LogLevelW(
                2u,
                L"Failed to load library on the WaaSMedicAgent with hr = 0x%08x.  Trying again...",
                (unsigned int)Library);
              Sleep(0x3E8u);
              if ( (unsigned int)++v35 >= 0x1E )
              {
                LogLevelW(
                  2u,
                  L"Failed to load library by the WaaSMedicAgent hr = 0x%08x",
                  (unsigned int)HasDeferredAction_State);
                goto LABEL_92;
              }
            }
            v107 = 0;
            LogLevelW(4u, L"Sandbox loaded capsule successfully.");
            v103 = 0;
            v41 = (const unsigned __int16 *)&SandboxAction::PluginCollection::setCorrelationVector;
            if ( (unsigned __int64)qword_1800A5978 > 7 )
              v41 = SandboxAction::PluginCollection::setCorrelationVector;
            HasDeferredAction_State = WaasMedic::CSandboxRpcWrapper::SandboxMethodIsPresentOnCollection(v40, v41, &v103);
            if ( HasDeferredAction_State < 0 )
            {
              v43 = &SandboxAction::PluginCollection::setCorrelationVector;
              if ( (unsigned __int64)qword_1800A5978 > 7 )
                v43 = (unsigned __int16 **)SandboxAction::PluginCollection::setCorrelationVector;
LABEL_103:
              LogLevelW(2u, L"Failed to determine if %s method is present on capsule", v43);
              goto LABEL_92;
            }
            if ( v103 )
            {
              v44 = (const unsigned __int16 *)&SandboxAction::PluginCollection::setCorrelationVector;
              if ( (unsigned __int64)qword_1800A5978 > 7 )
                v44 = SandboxAction::PluginCollection::setCorrelationVector;
LABEL_107:
              v101[0] = 0;
              HasDeferredAction_State = WaasMedic::CSandboxRpcWrapper::SandboxPluginAction(
                                          v42,
                                          &word_180073298,
                                          v44,
                                          v101);
              if ( HasDeferredAction_State < 0 )
              {
                LogLevelW(2u, L"Failed to set cV on plugin collection");
                goto LABEL_92;
              }
            }
            else
            {
              v45 = (const unsigned __int16 *)&SandboxAction::PluginCollection::setCorrelationVector_compat;
              if ( (unsigned __int64)qword_1800A5A38 > 7 )
                v45 = SandboxAction::PluginCollection::setCorrelationVector_compat;
              HasDeferredAction_State = WaasMedic::CSandboxRpcWrapper::SandboxMethodIsPresentOnCollection(
                                          v42,
                                          v45,
                                          &v103);
              if ( HasDeferredAction_State < 0 )
              {
                v43 = &SandboxAction::PluginCollection::setCorrelationVector_compat;
                if ( (unsigned __int64)qword_1800A5A38 > 7 )
                  v43 = (unsigned __int16 **)SandboxAction::PluginCollection::setCorrelationVector_compat;
                goto LABEL_103;
              }
              if ( v103 )
              {
                v44 = (const unsigned __int16 *)&SandboxAction::PluginCollection::setCorrelationVector_compat;
                if ( (unsigned __int64)qword_1800A5A38 > 7 )
                  v44 = SandboxAction::PluginCollection::setCorrelationVector_compat;
                goto LABEL_107;
              }
            }
          }
          v31 = 0;
          if ( a6 != 2 && a6 <= 4
            || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl)
            && a6 == 5 )
          {
            v101[0] = 0;
            std::wstring::wstring(&v148, *((_QWORD *)this + 3) + 136LL);
            wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
              v160,
              "DetectionActivity");
            v160[0] = &WaasMedic::TelemetryProvider::DetectionActivity::`vftable';
            WaasMedic::TelemetryProvider::DetectionActivity::StartActivity(v160, v135, v28, &v148);
            std::wstring::~wstring(&v148);
            v47 = (const unsigned __int16 *)&SandboxAction::Plugin::detectCondition;
            if ( (unsigned __int64)qword_1800A5A58 > 7 )
              v47 = SandboxAction::Plugin::detectCondition;
            v48 = WaasMedic::CSandboxRpcWrapper::SandboxPluginAction(v46, v28, v47, v101);
            v117 = v48;
            v112 = 1;
            if ( v48 < 0 )
            {
              v107 = 1;
              LogLevelW(2u, L"DetectCondition for %s failed! hr = 0x%08x.", v28, (unsigned int)v48);
              v115 = v48;
              goto LABEL_127;
            }
            v49 = v101[0] != 0;
            v106 = v101[0] != 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl) )
            {
              v50 = v115;
              LODWORD(v100) = v115;
              LogLevelW(
                4u,
                L"Plugin \"%s\" tempStatus = 0x%08x; currPluginDetectionStatus = 0x%08x.",
                v28,
                2367504,
                v100);
              if ( v50 == 2367504 )
              {
                LogLevelW(
                  4u,
                  L"Plugin %s was triggered due to manual remediation campaign. No detection performed.",
                  v28);
                v51 = 2392072;
                v49 = v106;
                goto LABEL_135;
              }
              v49 = v106;
              v52 = v106;
            }
            else
            {
              v52 = v49;
            }
            v51 = !v52 + 2392066;
LABEL_135:
            v115 = v51;
            WaasMedic::TelemetryProvider::DetectionActivity::Stop(
              (WaasMedic::TelemetryProvider::DetectionActivity *)v160,
              v49);
            if ( !v49 )
            {
              LogLevelW(4u, L"Plugin %s did not detect the remediation condition. Nothing to do.", v28);
              v53 = v125;
              v54 = WaasMedic::CDeferManager::UnsetMaintenanceAction_State(v125, v28);
              if ( v54 < 0 )
                LogLevelW(
                  2u,
                  L"Failed to unset an existing maintenance action for plugin %s. hr = 0x%08x",
                  v28,
                  (unsigned int)v54);
              v55 = WaasMedic::CDeferManager::UnsetDeferredAction_State(v53, v28);
              HasDeferredAction_State = v55;
              if ( v55 < 0 )
                LogLevelW(
                  2u,
                  L"Failed to unset an existing deferral action for plugin %s. hr = 0x%08x",
                  v28,
                  (unsigned int)v55);
              goto LABEL_127;
            }
            if ( v140 )
              ++*v140;
            LogLevelW(4u, L"Plugin \"%s\" detected the remediation condition.", v28);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl) )
              v56 = ((a6 - 1) & 0xFFFFFFFB) == 0;
            else
              v56 = a6 == 1;
            if ( v56 )
            {
              v57 = Src;
              if ( *((_QWORD *)Src + 2) )
                std::wstring::operator+=(Src, L";");
              std::wstring::operator+=(v57, v28);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl) )
              v58 = ((a6 - 1) & 0xFFFFFFFB) == 0;
            else
              v58 = a6 == 1;
            if ( v58 )
              goto LABEL_127;
            if ( v105 )
              goto LABEL_169;
            v122 = 0;
            LogLevelW(5u, L"Calling DeferManager to evaluate remediation schedule.");
            v128 = 0;
            v59 = v125;
            v60 = WaasMedic::CDeferManager::EvaluateSchedule(v125, v28, (enum WaasMedic::DeferralStatus *)&v122, &v128);
            HasDeferredAction_State = v60;
            if ( v60 < 0 )
            {
              LogLevelW(2u, L"Calling DeferManager to evaluate remediation schedule. hr = 0x%08x", (unsigned int)v60);
              goto LABEL_127;
            }
            switch ( v122 )
            {
              case 1:
                LogLevelW(
                  4u,
                  L"Plugin %s runs without deferral/maintenance. Will remediate now. Run mode is: %d.",
                  v28,
                  a6);
                break;
              case 2:
                v115 = 2392070;
                LogLevelW(4u, L"Plugin %s action execution is being deferred.", v28);
                v69 = WaasMedic::CDeferManager::SetDeferredAction_State(v59, v28, v128);
                HasDeferredAction_State = v69;
                if ( v69 < 0 )
                  LogLevelW(2u, L"Failed to set deferred action. hr = 0x%08x", (unsigned int)v69);
                goto LABEL_127;
              case 3:
                if ( a6 != 3 )
                {
                  v115 = 2392070;
                  LogLevelW(
                    4u,
                    L"Plugin %s remediation action will be run at next maintenance. Current mode: %d",
                    v28,
                    a6);
                  LogLevelW(5u, L"CDeferManager asked to add maintenance action: %s.", v28);
                  v150 = 0;
                  v151 = 0;
                  v67 = -1;
                  do
                    ++v67;
                  while ( v28[v67] );
                  std::wstring::_Construct<1,unsigned short const *>(&v150, v28);
                  std::list<std::wstring>::_Emplace<std::wstring>((char *)v59 + 72, *((_QWORD *)v59 + 9), &v150);
                  std::wstring::~wstring(&v150);
                  v68 = WaasMedic::CDeferManager::SetMaintenanceAction_State(v125, v28);
                  HasDeferredAction_State = v68;
                  if ( v68 < 0 )
                    LogLevelW(2u, L"Failed to set maintenance action. hr = 0x%08x", (unsigned int)v68);
                  goto LABEL_127;
                }
                LogLevelW(
                  4u,
                  L"Plugin %s remediation requires maintenance. Proceeding since this is maintenance run.",
                  v28);
                v63 = WaasMedic::CDeferManager::UnsetMaintenanceAction_State(v59, v28);
                if ( v63 < 0 )
                  LogLevelW(2u, L"Failed to unset maintenance action. hr = 0x%08x", (unsigned int)v63);
                break;
              case 4:
                v115 = 2392071;
                LogLevelW(4u, L"Future deferral already pending for %s. No action will be performed.", v28);
                goto LABEL_127;
              case 5:
                if ( a6 == 4 )
                {
                  LogLevelW(4u, L"Deferred time for plugin %s passed. This is deferred run, perform action now.", v28);
                  v61 = WaasMedic::CDeferManager::UnsetDeferredAction_State(v59, v28);
                  if ( v61 < 0 )
                    LogLevelW(2u, L"Failed to unset deferral action. hr = 0x%08x", (unsigned int)v61);
                  break;
                }
                LODWORD(v100) = a6;
                LogLevelW(
                  4u,
                  L"Deferred task due time %s passed. Skipping as mode required/current %d/%d.",
                  v28,
                  4,
                  v100);
                v62 = WaasMedic::CDeferManager::AddDeferredAction(v59, v28, v128);
                HasDeferredAction_State = v62;
                if ( v62 < 0 )
                  LogLevelW(2u, L"Failed to add deferral action. hr = 0x%08x", (unsigned int)v62);
LABEL_127:
                v160[0] = &WaasMedic::TelemetryProvider::DetectionActivity::`vftable';
LABEL_128:
                wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v160);
                wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v160);
                goto LABEL_62;
            }
LABEL_169:
            v160[0] = &WaasMedic::TelemetryProvider::DetectionActivity::`vftable';
            wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v160);
            wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v160);
          }
          v64 = *((_QWORD *)this + 2);
          v65 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, unsigned int *))(*(_QWORD *)v64 + 8LL);
          v148 = 0;
          v149 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v148, L"ThreadExecutionTimeoutInSeconds");
          v150 = 0;
          v151 = 0;
          v66 = -1;
          do
            ++v66;
          while ( v28[v66] );
          std::wstring::_Construct<1,unsigned short const *>(&v150, v28);
          HasDeferredAction_State = v65(v64, &v150, &v148, v132);
          std::wstring::~wstring(&v150);
          std::wstring::~wstring(&v148);
          if ( HasDeferredAction_State < 0 )
          {
            LogLevelW(
              2u,
              L"Unable to read plugin setting for execution timeout. hr = 0x%08x",
              (unsigned int)HasDeferredAction_State);
            goto LABEL_62;
          }
          if ( WaasMedic::CWaasRemediation::IsPluginDetectionOnly(this, v28) )
          {
            LogLevelW(4u, L"Plugin \"%s\" is set to detection only. Nothing to do.", v28);
            goto LABEL_62;
          }
          if ( !v108 )
          {
            HasDeferredAction_State = -2147024891;
            LogLevelW(2u, L"Caller is not admin. Remediation will not be executed. hr = 0x%08x", 2147942405LL);
            goto LABEL_62;
          }
          std::wstring::wstring(&v148, *((_QWORD *)this + 3) + 136LL);
          wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
            v160,
            "RemediationActivity");
          v160[0] = &WaasMedic::TelemetryProvider::RemediationActivity::`vftable';
          WaasMedic::TelemetryProvider::RemediationActivity::StartActivity(v160, v135, v28, &v148);
          std::wstring::~wstring(&v148);
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          VariantInit(&v136);
          v136.vt = 8;
          v71 = WaasMedic::TimeHelper::FileTimeToString(v165, v70, &SystemTimeAsFileTime);
          if ( v71 < 0 || (v136.llVal = (LONGLONG)SysAllocString(v165)) != 0 )
          {
            HasDeferredAction_State = v71;
            if ( v71 >= 0 )
            {
              v113 = 1;
              v72 = WaasMedic::CWaasRemediation::ExecutePerformAction(
                      (WaasMedic *)v28,
                      v132[0],
                      (struct WaasMedic::CSandboxRpcWrapper *)v152);
              v74 = v72;
              v117 = v72;
              if ( v72 >= 0 )
              {
                v74 = 2375683 - (v72 != 0);
                WaasMedic::TelemetryProvider::RemediationActivity::Stop(
                  (WaasMedic::TelemetryProvider::RemediationActivity *)v160,
                  v73);
              }
              else if ( v72 == -2147023673 )
              {
                LogLevelW(4u, L"Plugin %s was canceled during execution.", v28);
                v117 = 0;
                v74 = 2375684;
              }
              else
              {
                LogLevelW(
                  2u,
                  L"Plugin %s failed to perform remediation action with error = 0x%08x",
                  v28,
                  (unsigned int)v72);
                v145.vt = 19;
                v145.lVal = v74;
                v75 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1) + 24LL))(
                        *((_QWORD *)this + 1),
                        v28,
                        L"LastRemediationFailureResult",
                        &v145);
                if ( v75 < 0 )
                {
                  LODWORD(v100) = v75;
                  LogLevelW(2u, L"Failed to save %s for %s! hr = 0x%08x.", L"LastRemediationFailureResult", v28, v100);
                }
                v114 = 1;
              }
              v160[0] = &WaasMedic::TelemetryProvider::RemediationActivity::`vftable';
              v119 = v74;
              wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v160);
              wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v160);
              if ( !v105
                && v74 >= 0
                && v74 != 2375684
                && (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1) + 16LL))(
                     *((_QWORD *)this + 1),
                     v28,
                     L"PluginRunCount",
                     &v127) >= 0 )
              {
                if ( v127.vt == 19 )
                {
                  lVal = v127.lVal;
                }
                else
                {
                  if ( v127.vt )
                    LogLevelW(2u, L"Unexpected VARIANT data retrieved for plugin run count. V_VT=%d", v127.vt);
                  else
                    v127.vt = 19;
                  lVal = v102;
                }
                v30 = lVal + 1;
                v102 = v30;
                v127.lVal = v30;
                v77 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1) + 24LL))(
                        *((_QWORD *)this + 1),
                        v28,
                        L"PluginRunCount",
                        &v127);
                HasDeferredAction_State = v77;
                if ( v77 < 0 )
                {
                  LODWORD(v100) = v77;
                  LogLevelW(2u, L"Failed to save state %s for %s! hr = 0x%08x.", L"PluginRunCount", v28, v100);
                }
                goto LABEL_63;
              }
              goto LABEL_62;
            }
          }
          else
          {
            HasDeferredAction_State = -2147024882;
            v71 = -2147024882;
            LogLevelW(2u, L"Failed to allocate memory for FILETIME string!");
          }
          LogLevelW(2u, L"Failed to convert filetime to string for %s! hr = 0x%08x.", v28, (unsigned int)v71);
          v160[0] = &WaasMedic::TelemetryProvider::RemediationActivity::`vftable';
          goto LABEL_128;
        }
        LogLevelW(4u, L"No existing deferral found for the plugin %s. Skipping.", v28);
        goto LABEL_51;
      }
      HasDeferredAction_State = WaasMedic::CDeferManager::HasMaintenanceAction_State(v125, v28, &v103);
      if ( HasDeferredAction_State >= 0 )
      {
        if ( v103 )
          goto LABEL_57;
        LogLevelW(4u, L"No existing maintenance found for the plugin %s. Skipping.", v28);
LABEL_51:
        v104 = 0;
        goto LABEL_63;
      }
      LogLevelW(
        2u,
        L"Failed while checking for maintenance action for plugin %s. hr = 0x%08x.",
        v28,
        (unsigned int)HasDeferredAction_State);
    }
LABEL_63:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl)
      && v115 == 2392072
      && (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1)
                                                                                          + 16LL))(
           *((_QWORD *)this + 1),
           v28,
           L"PluginManualRunCount",
           &v127) >= 0 )
    {
      if ( v127.vt == 19 )
      {
        v30 = v127.lVal;
      }
      else if ( v127.vt )
      {
        LogLevelW(2u, L"Unexpected VARIANT data retrieved for plugin manual run count. V_VT=%d", v127.vt);
      }
      else
      {
        v127.vt = 19;
      }
      v102 = v30 + 1;
      v127.lVal = v30 + 1;
      v78 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1)
                                                                                                 + 24LL))(
              *((_QWORD *)this + 1),
              v28,
              L"PluginManualRunCount",
              &v127);
      if ( v78 < 0 )
      {
        LODWORD(v100) = v78;
        LogLevelW(2u, L"Failed to save state %s for %s! hr = 0x%08x.", L"PluginManualRunCount", v28, v100);
      }
    }
    v79 = *((_QWORD *)this + 2);
    v80 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, _DWORD *))(*(_QWORD *)v79 + 8LL);
    v150 = 0;
    v151 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v150, L"ACTIONLIMIT");
    v148 = 0;
    v149 = 0;
    v81 = -1;
    do
      ++v81;
    while ( v28[v81] );
    std::wstring::_Construct<1,unsigned short const *>(&v148, v28);
    v82 = v80(v79, &v148, &v150, v129);
    std::wstring::~wstring(&v148);
    std::wstring::~wstring(&v150);
    if ( v82 < 0 )
      LogLevelW(2u, L"Failed to read %s. hr = 0x%08x", L"ACTIONLIMIT", (unsigned int)v82);
    v84 = v129[0] != -1 && v102 == v129[0];
    if ( HasDeferredAction_State < 0 )
    {
      LogLevelW(
        2u,
        L"Medic engine error encountered when processing plugin %s: hr = 0x%08x",
        v28,
        (unsigned int)HasDeferredAction_State);
      v121 = HasDeferredAction_State;
    }
    if ( v117 < 0 && v141 )
      ++*v141;
    if ( v111
      && (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1)
                                                                                          + 24LL))(
           *((_QWORD *)this + 1),
           v28,
           L"LastApplicabilityRunTime",
           &pvarg) < 0 )
    {
      LogLevelW(2u, L"Failed to save state %s for %s!", L"LastApplicabilityRunTime", v28);
    }
    if ( v112
      && (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1)
                                                                                          + 24LL))(
           *((_QWORD *)this + 1),
           v28,
           L"LastDetectionRunTime",
           &v143) < 0 )
    {
      LogLevelW(2u, L"Failed to save state %s for %s!", L"LastDetectionRunTime", v28);
    }
    if ( v113
      && (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1)
                                                                                          + 24LL))(
           *((_QWORD *)this + 1),
           v28,
           L"LastRemediationRunTime",
           &v136) < 0 )
    {
      LogLevelW(2u, L"Failed to save state %s for %s!", L"LastRemediationRunTime", v28);
    }
    if ( v114
      && (*(int (__fastcall **)(_QWORD, unsigned __int16 *, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1)
                                                                                          + 24LL))(
           *((_QWORD *)this + 1),
           v28,
           L"LastRemediationFailedTime",
           &v136) < 0 )
    {
      LogLevelW(2u, L"Failed to save state %s for %s!", L"LastRemediationFailedTime", v28);
    }
    WaasMedic::SafeFree(0, v83);
    v85 = *((_QWORD *)this + 3);
    if ( v85 )
    {
      ++*(_DWORD *)(v85 + 128);
      v86 = (CJsonHelper *)**((_QWORD **)this + 3);
      if ( v86 )
        CJsonHelper::SetValue(v86, v28, v31);
      v87 = *(CJsonHelper **)(*((_QWORD *)this + 3) + 8LL);
      if ( v87 )
        CJsonHelper::SetValue(v87, v28, v115);
      v88 = *(CJsonHelper **)(*((_QWORD *)this + 3) + 32LL);
      if ( v88 )
        CJsonHelper::SetValue(v88, v28, v119);
      if ( v104 )
        ++*(_DWORD *)(*((_QWORD *)this + 3) + 132LL);
      v14 = v116;
      if ( v116 < 0 )
        *(_DWORD *)(*((_QWORD *)this + 3) + 104LL) = v116;
    }
    else
    {
      v14 = v116;
    }
    if ( !v105 )
    {
      v89 = 0;
      if ( HasDeferredAction_State >= 0 && v117 >= 0 && v123 == 3 && v109 && v106 )
        v89 = v84;
      if ( v142 )
        *v142 &= v89;
    }
    v90 = VariantClear(&v146);
    if ( v90 < 0 )
      _com_issue_error(v90);
    v91 = VariantClear(&v147);
    if ( v91 < 0 )
      _com_issue_error(v91);
    v92 = VariantClear(&v127);
    if ( v92 < 0 )
      _com_issue_error(v92);
    v93 = VariantClear(&v145);
    if ( v93 < 0 )
      _com_issue_error(v93);
    v94 = VariantClear(&v136);
    if ( v94 < 0 )
      _com_issue_error(v94);
    v95 = VariantClear(&v143);
    if ( v95 < 0 )
      _com_issue_error(v95);
    v96 = VariantClear(&pvarg);
    if ( v96 < 0 )
      _com_issue_error(v96);
    v27 = v124 + 1;
    v124 = v27;
  }
LABEL_272:
  v97 = WaasMedic::CSandboxRpcWrapper::SandBoxFreePluginLibrary((WaasMedic::CSandboxRpcWrapper *)v152);
  v98 = v97;
  if ( v97 < 0 )
  {
    LogLevelW(3u, L"SandBoxFreePluginLibrary failed. hr = 0x%08x", (unsigned int)v97);
    if ( v14 >= 0 )
      v14 = v98;
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v163,
    (unsigned int)v14);
  if ( v121 < 0 )
    HasDeferredAction_State = v121;
  v162[0] = &WaasMedic::TelemetryProvider::EnumeratePluginActivity::`vftable';
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v162);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v162);
  v163[0] = &WaasMedic::TelemetryProvider::SandboxActivity::`vftable';
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v163);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v163);
  WaasMedic::CSandboxRpcWrapper::~CSandboxRpcWrapper((WaasMedic::CSandboxRpcWrapper *)v152);
  return (unsigned int)HasDeferredAction_State;
}

```

## disassembly

```asm
0x180018d3c  push    rbp
0x180018d3e  push    rbx
0x180018d3f  push    rsi
0x180018d40  push    rdi
0x180018d41  push    r12
0x180018d43  push    r13
0x180018d45  push    r14
0x180018d47  push    r15
0x180018d49  lea     rbp, [rsp-618h]
0x180018d51  sub     rsp, 718h
0x180018d58  mov     rax, cs:__security_cookie
0x180018d5f  xor     rax, rsp
0x180018d62  mov     [rbp+650h+var_50], rax
0x180018d69  mov     [rbp+650h+var_640], r9
0x180018d6d  mov     [rbp+650h+var_6CC], r8d
0x180018d71  mov     [rsp+750h+var_6F6], dl
0x180018d75  mov     r13, rcx
0x180018d78  mov     rsi, [rbp+650h+arg_58]
0x180018d7f  mov     [rbp+650h+Src], rsi
0x180018d83  mov     rbx, [rbp+650h+arg_38]
0x180018d8a  mov     [rbp+650h+var_660], rbx
0x180018d8e  mov     rdi, [rbp+650h+arg_30]
0x180018d95  mov     [rbp+650h+var_630], rdi
0x180018d99  mov     rax, [rbp+650h+arg_20]
0x180018da0  mov     [rbp+650h+var_638], rax
0x180018da4  mov     rdx, [rbp+650h+arg_40]
0x180018dab  mov     [rbp+650h+var_628], rdx
0x180018daf  mov     rcx, [rbp+650h+arg_48]
0x180018db6  mov     [rbp+650h+var_620], rcx
0x180018dba  mov     r12, [rbp+650h+arg_50]
0x180018dc1  mov     [rbp+650h+var_618], r12
0x180018dc5  mov     rax, [rbp+650h+arg_60]
0x180018dcc  mov     [rbp+650h+var_6C0], rax
0x180018dd0  xor     r8d, r8d
0x180018dd3  mov     [rsp+750h+var_6D4], r8d
0x180018dd8  mov     r14d, r8d
0x180018ddb  mov     [rsp+750h+var_6E8], r8d
0x180018de0  mov     [rsp+750h+var_6D8], r8d
0x180018de5  mov     [rbp+650h+var_550], r8b
0x180018dec  mov     [rbp+650h+var_548], r8
0x180018df3  xorps   xmm0, xmm0
0x180018df6  movdqa  [rbp+650h+var_540], xmm0
0x180018dfe  mov     [rbp+650h+var_530], r8
0x180018e05  xorps   xmm1, xmm1
0x180018e08  movups  [rbp+650h+var_528], xmm1
0x180018e0f  mov     [rbp+650h+var_518], r8
0x180018e16  mov     [rbp+650h+var_510], 7
0x180018e21  mov     word ptr [rbp+650h+var_528], r8w
0x180018e29  mov     [rbp+650h+var_508], r8
0x180018e30  mov     [rbp+650h+var_680], r8
0x180018e34  test    rdx, rdx
0x180018e37  jz      short loc_180018E3C
0x180018e39  mov     [rdx], r8d
0x180018e3c  test    r12, r12
0x180018e3f  jz      short loc_180018E46
0x180018e41  mov     byte ptr [r12], 1
0x180018e46  xor     r12d, r12d
0x180018e49  test    rcx, rcx
0x180018e4c  jz      short loc_180018E51
0x180018e4e  mov     [rcx], r12d
0x180018e51  mov     rdx, [r13+18h]
0x180018e55  mov     r15d, 88h
0x180018e5b  add     rdx, r15
0x180018e5e  lea     rcx, [rbp+650h+var_598]
0x180018e65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018e6a  nop
0x180018e6b  lea     rdx, aSandboxactivit; "SandboxActivity"
0x180018e72  lea     rcx, [rbp+650h+var_230]
0x180018e79  call    ??0?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180018e7e  lea     rax, ??_7SandboxActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::SandboxActivity::`vftable'
0x180018e85  mov     [rbp+650h+var_230], rax
0x180018e8c  lea     r9, [rbp+650h+var_598]
0x180018e93  mov     r8, rdi
0x180018e96  mov     rdx, rbx
0x180018e99  lea     rcx, [rbp+650h+var_230]
0x180018ea0  call    ?StartActivity@SandboxActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::TelemetryProvider::SandboxActivity::StartActivity(char const *,ushort const *,std::wstring const &)
0x180018ea5  nop
0x180018ea6  lea     rcx, [rbp+650h+var_598]; void *
0x180018ead  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018eb2  mov     rdx, [r13+18h]
0x180018eb6  add     rdx, r15
0x180018eb9  lea     rcx, [rbp+650h+var_3A0]
0x180018ec0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018ec5  nop
0x180018ec6  lea     rdx, aEnumerateplugi_0; "EnumeratePluginActivity"
0x180018ecd  lea     rcx, [rbp+650h+var_380]
0x180018ed4  call    ??0?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180018ed9  lea     rax, ??_7EnumeratePluginActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::EnumeratePluginActivity::`vftable'
0x180018ee0  mov     [rbp+650h+var_380], rax
0x180018ee7  lea     r9, [rbp+650h+var_3A0]
0x180018eee  mov     r8, rdi
0x180018ef1  mov     rdx, rbx
0x180018ef4  lea     rcx, [rbp+650h+var_380]
0x180018efb  call    ?StartActivity@EnumeratePluginActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::TelemetryProvider::EnumeratePluginActivity::StartActivity(char const *,ushort const *,std::wstring const &)
0x180018f00  nop
0x180018f01  lea     rcx, [rbp+650h+var_3A0]; void *
0x180018f08  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018f0d  mov     r15d, 2
0x180018f13  cmp     [r13+40h], r12
0x180018f17  jnz     short loc_180018F23
0x180018f19  mov     edi, 80029C4Ah
0x180018f1e  jmp     loc_180018FB1
0x180018f23  lea     rdx, aInitializingPl; "Initializing plugin"
0x180018f2a  mov     ecx, 4; unsigned __int8
0x180018f2f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180018f34  lea     rdx, ?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::init
0x180018f3b  lea     rcx, [rbp+650h+var_598]
0x180018f42  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x180018f47  cmp     qword ptr [rax+18h], 0Fh
0x180018f4c  jbe     short loc_180018F51
0x180018f4e  mov     rax, [rax]
0x180018f51  mov     rdx, rax; lpProcName
0x180018f54  mov     rcx, [r13+40h]; hModule
0x180018f58  call    cs:__imp_GetProcAddress
0x180018f5e  mov     rbx, rax
0x180018f61  lea     rcx, [rbp+650h+var_598]
0x180018f68  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018f6d  test    rbx, rbx
0x180018f70  jnz     short loc_180018F91
0x180018f72  call    cs:__imp_GetLastError
0x180018f78  mov     edi, eax
0x180018f7a  test    eax, eax
0x180018f7c  jle     short loc_180018F87
0x180018f7e  movzx   edi, ax
0x180018f81  or      edi, 80070000h
0x180018f87  mov     rax, [r13+18h]
0x180018f8b  test    edi, edi
0x180018f8d  jns     short loc_180018FD8
0x180018f8f  jmp     short loc_180018FB5
0x180018f91  mov     rax, rbx
0x180018f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f99  mov     edi, eax
0x180018f9b  test    eax, eax
0x180018f9d  jns     short loc_180018FD4
0x180018f9f  mov     r8d, eax
0x180018fa2  lea     rdx, aFailedToInitia_2; "Failed to initialize plugin. hr = 0x%08"...
0x180018fa9  mov     ecx, r15d; unsigned __int8
0x180018fac  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180018fb1  mov     rax, [r13+18h]
0x180018fb5  test    rax, rax
0x180018fb8  jz      short loc_180018FBD
0x180018fba  inc     dword ptr [rax+7Ch]
0x180018fbd  mov     r8d, edi
0x180018fc0  lea     rdx, aPluginInitFail; "Plugin_Init failed. hr = 0x%08x"
0x180018fc7  mov     ecx, r15d; unsigned __int8
0x180018fca  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180018fcf  jmp     loc_18001A3F9
0x180018fd4  mov     rax, [r13+18h]
0x180018fd8  mov     ebx, 1
0x180018fdd  test    rax, rax
0x180018fe0  jz      short loc_180018FE5
0x180018fe2  add     [rax+78h], ebx
0x180018fe5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MCPPluginSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport> `wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl(void)'::`2'::impl
0x180018fec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(void)
0x180018ff1  test    al, al
0x180018ff3  jz      short loc_180019022
0x180018ff5  mov     eax, [rbp+650h+arg_28]
0x180018ffb  dec     eax
0x180018ffd  test    eax, 0FFFFFFFBh
0x180019002  jnz     short loc_18001902A
0x180019004  test    rsi, rsi
0x180019007  jnz     short loc_18001902A
0x180019009  lea     rdx, aForValidDetect; "For valid Detection run, return string "...
0x180019010  mov     ecx, r15d; unsigned __int8
0x180019013  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180019018  mov     edi, 80004003h
0x18001901d  jmp     loc_18001A3F9
0x180019022  cmp     [rbp+650h+arg_28], ebx
0x180019028  jmp     short loc_180019002
0x18001902a  lea     r8, [rbp+650h+var_680]; struct PluginNameAndOrder **
0x18001902e  lea     rdx, [rsp+750h+var_6D8]; int *
0x180019033  mov     rcx, r13; this
0x180019036  call    ?EnumeratePlugins@CWaasRemediation@WaasMedic@@AEAAJPEAHPEAPEAUPluginNameAndOrder@@@Z; WaasMedic::CWaasRemediation::EnumeratePlugins(int *,PluginNameAndOrder * *)
0x18001903b  mov     edi, eax
0x18001903d  test    eax, eax
0x18001903f  js      loc_18001A3D9
0x180019045  cmp     [rbp+650h+var_680], r12
0x180019049  jz      loc_18001A3D9
0x18001904f  xor     edx, edx
0x180019051  lea     rcx, [rbp+650h+var_380]
0x180019058  call    ?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001905d  mov     rdx, [r13+38h]; struct TraceLoggingCorrelationVector *
0x180019061  lea     rcx, [rbp+650h+var_550]; this
0x180019068  call    ?Init@CSandboxRpcWrapper@WaasMedic@@QEAAJPEAVTraceLoggingCorrelationVector@@@Z; WaasMedic::CSandboxRpcWrapper::Init(TraceLoggingCorrelationVector *)
0x18001906d  mov     edi, eax
0x18001906f  test    eax, eax
0x180019071  jns     short loc_18001908D
0x180019073  mov     r8d, eax
0x180019076  lea     rdx, aFailedToInitia_1; "Failed to initialize sandbox. hr = 0x%0"...
0x18001907d  mov     ecx, r15d; unsigned __int8
0x180019080  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180019085  mov     r14d, edi
0x180019088  jmp     loc_18001A3F9
0x18001908d  mov     [rsp+750h+var_6F3], r12b
0x180019092  lea     rcx, [rsp+750h+var_6F3]; this
0x180019097  call    ?IsProcessAdmin@WaasMedic@@YAJAEA_N@Z; WaasMedic::IsProcessAdmin(bool &)
0x18001909c  mov     edi, eax
0x18001909e  test    eax, eax
0x1800190a0  jns     short loc_1800190B1
0x1800190a2  mov     r8d, eax
0x1800190a5  lea     rdx, aFailedToDeterm; "Failed to determine if caller is Admin."...
0x1800190ac  jmp     loc_180018FC7
0x1800190b1  mov     [rsp+750h+var_6F4], bl
0x1800190b5  lea     r8, word_180073298
0x1800190bc  lea     rax, aNot; "not"
0x1800190c3  cmp     [rsp+750h+var_6F3], bl
0x1800190c7  cmovnz  r8, rax
0x1800190cb  lea     rdx, aCallerIsSAdmin; "Caller is %s admin"
0x1800190d2  mov     ecx, 5; unsigned __int8
0x1800190d7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800190dc  mov     eax, r12d
0x1800190df  mov     [rbp+650h+var_6C8], eax
0x1800190e2  cmp     [rsp+750h+var_6D8], r12d
0x1800190e7  jle     loc_18001A3F9
0x1800190ed  cdqe
0x1800190ef  imul    rsi, rax, 204h
0x1800190f6  add     rsi, [rbp+650h+var_680]
0x1800190fa  mov     rcx, [rbp+650h+var_640]
0x1800190fe  test    rcx, rcx
0x180019101  jz      short loc_180019116
0x180019103  mov     rax, [rcx]
0x180019106  mov     rax, [rax]
0x180019109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001910e  test    al, al
0x180019110  jnz     loc_18001A3C3
0x180019116  mov     [rsp+750h+var_6E4], r12d
0x18001911b  mov     [rsp+750h+var_700], r12b
0x180019120  mov     [rsp+750h+var_6F2], r12b
0x180019125  mov     [rsp+750h+var_6E0], r12d
0x18001912a  mov     [rsp+750h+var_6F5], r12b
0x18001912f  lea     rcx, [rbp+650h+pvarg]; pvarg
0x180019133  call    cs:__imp_VariantInit
0x180019139  nop
0x18001913a  lea     rcx, [rbp+650h+var_610]; pvarg
0x18001913e  call    cs:__imp_VariantInit
0x180019144  nop
0x180019145  lea     rcx, [rbp+650h+var_658]; pvarg
0x180019149  call    cs:__imp_VariantInit
0x18001914f  nop
0x180019150  lea     rcx, [rbp+650h+var_5E0]; pvarg
0x180019154  call    cs:__imp_VariantInit
0x18001915a  nop
0x18001915b  lea     rcx, [rbp+650h+var_6B0]; pvarg
0x18001915f  call    cs:__imp_VariantInit
0x180019165  nop
0x180019166  lea     rcx, [rbp+650h+var_5B0]; pvarg
0x18001916d  call    cs:__imp_VariantInit
0x180019173  nop
0x180019174  lea     rcx, [rbp+650h+var_5C8]; pvarg
0x18001917b  call    cs:__imp_VariantInit
0x180019181  nop
0x180019182  mov     qword ptr [rbp+650h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180019186  mov     ebx, r12d
0x180019189  mov     [rsp+750h+var_6FC], ebx
0x18001918d  mov     [rbp+650h+var_688], r12b
0x180019191  mov     [rbp+650h+var_690], r12d
0x180019195  mov     [rbp+650h+var_68C], r15d
0x180019199  mov     [rbp+650h+var_670], r12b
0x18001919d  mov     [rbp+650h+var_678], 78h ; 'x'
0x1800191a4  mov     [rbp+650h+var_674], r15d
0x1800191a8  mov     eax, 248001h
0x1800191ad  mov     r12d, eax
0x1800191b0  mov     [rsp+750h+var_6EC], eax
0x1800191b4  mov     r14d, 244001h
0x1800191ba  mov     [rsp+750h+var_6DC], r14d
0x1800191bf  xor     eax, eax
0x1800191c1  mov     [rsp+750h+var_6F8], al
0x1800191c5  mov     [rsp+750h+var_6F1], al
0x1800191c9  mov     [rsp+750h+var_6F0], al
0x1800191cd  mov     [rsp+750h+var_6EF], al
0x1800191d1  mov     [rsp+750h+var_6EE], al
0x1800191d5  mov     [rsp+750h+var_6ED], al
0x1800191d9  mov     [rsp+750h+var_6F7], al
0x1800191dd  mov     r8, rsi; unsigned __int16 *
0x1800191e0  cmp     [r13+22h], al
0x1800191e4  jz      short loc_1800191FA
0x1800191e6  lea     rdx, aPluginSWillBeS; "Plugin %s will be skipped due to cancel"...
0x1800191ed  lea     ecx, [rax+4]; unsigned __int8
0x1800191f0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800191f5  jmp     loc_18001934A
0x1800191fa  mov     rdx, [rbp+650h+var_638]; unsigned __int16 *
0x1800191fe  call    ?IsPluginNeedToSkipBasedOnPluginList@CWaasRemediation@WaasMedic@@AEAA_NPEBG0@Z; WaasMedic::CWaasRemediation::IsPluginNeedToSkipBasedOnPluginList(ushort const *,ushort const *)
0x180019203  test    al, al
0x180019205  jz      short loc_180019223
0x180019207  mov     r8, rsi
0x18001920a  lea     rdx, aPluginSIsNotSp; "Plugin \"%s\" is not specified to run. "...
0x180019211  mov     ecx, 4; unsigned __int8
0x180019216  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001921b  mov     r12d, r14d
0x18001921e  jmp     loc_18001934A
0x180019223  mov     [rsp+750h+var_6F7], 1
0x180019228  mov     r14d, [rbp+650h+arg_28]
0x18001922f  cmp     r14d, 3
0x180019233  jnz     short loc_18001928C
0x180019235  lea     r8, [rsp+750h+var_6F8]; bool *
0x18001923a  mov     rdx, rsi; unsigned __int16 *
0x18001923d  mov     rcx, [rbp+650h+var_6C0]; this
0x180019241  call    ?HasMaintenanceAction_State@CDeferManager@WaasMedic@@QEAAJPEBGAEA_N@Z; WaasMedic::CDeferManager::HasMaintenanceAction_State(ushort const *,bool &)
0x180019246  mov     edi, eax
0x180019248  xor     eax, eax
  ... truncated ...
```
