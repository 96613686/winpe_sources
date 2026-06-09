# WaasMedic::CWaasRemediation::RunEx(WaasMedic::ICancellable *,WaasMedic::RunMode,ushort const *,ushort * *)

- ea: `0x1800184b0`
- end: `0x180018d34`
- name: `?RunEx@CWaasRemediation@WaasMedic@@UEAAJPEAUICancellable@2@W4RunMode@2@PEBGPEAPEAG@Z`
- size: `2180`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x180005bbc`
- `0x180008c2c`
- `0x180008d99`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18000de58`
- `0x18000e7cc`
- `0x18000ea1c`
- `0x18000f860`
- `0x18000f9cc`
- `0x180010db4`
- `0x180013998`
- `0x1800141e8`
- `0x180014938`
- `0x180014dac`
- `0x18001558c`
- `0x180017778`
- `0x1800184b0`
- `0x180018d3c`
- `0x18001c554`
- `0x18001d474`
- `0x18001d650`
- `0x18001d898`
- `0x18001facc`
- `0x18001fccc`
- `0x180020718`
- `0x180020cf0`
- `0x180020dc8`
- `0x18002109c`
- `0x180025424`
- `0x18002a32c`
- `0x18002c844`
- `0x18002e81c`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018c88`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c92`
- `OLEAUT32!__imp_VariantInit` at `0x180018551`
- `OLEAUT32!__imp_VariantInit` at `0x180018551`
- `OLEAUT32!__imp_VariantClear` at `0x180018b6c`
- `OLEAUT32!__imp_VariantClear` at `0x180018cc6`
- `OLEAUT32!__imp_VariantClear` at `0x180018b6c`
- `OLEAUT32!__imp_VariantClear` at `0x180018cc6`

## string_xrefs

- `0x180018953`: `%windir%\System32\`
- `0x1800189bf`: `Full path to capsule: %s`
- `0x180018bc5`: `LoadLibrary failed for capsule = %s. hr = 0x%08x`
- `0x180018a70`: `RunPluginsInCapsule failed.  Capsule = %s. hr = 0x%08x`
- `0x180018a9d`: `FreePluginLibrary failed. hr = 0x%08x`
- `0x180018c73`: `Signaling completion, will set m_xhCompleted event.`
- `0x180018ca7`: `Failed to Set completed/cancelled event! hr = 0x%08x`
- `0x1800185e2`: `'ppszPluginsWithIssueDetected' can't be nullptr when detection only mode `
- `0x180018b1d`: `Could not signal maintenance completion. hr = 0x%08x`
- `0x180018c14`: `Failed to allocate string for 'ppszPluginsWithIssueDetected'.  hr = 0x%08x.`
- `0x180018c2b`: `All plugins didn't detect any issue. Sending WER report now.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WaasMedic::CWaasRemediation::RunEx(
        __int64 a1,
        unsigned __int8 (__fastcall ***a2)(_QWORD),
        unsigned int a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  const unsigned __int16 *v8; // rdi
  int v9; // r15d
  char *v10; // r14
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  bool v13; // zf
  const unsigned __int16 *v14; // rdx
  volatile signed __int64 *v15; // rax
  TraceLoggingCorrelationVector *v16; // rax
  int UnifiedImpactLevel; // eax
  int v18; // eax
  __int64 v19; // r8
  char v20; // r12
  __int64 v21; // rax
  __int64 v22; // rbx
  const wchar_t *v23; // rax
  __int64 v24; // r8
  char *v25; // rdi
  char *i; // r15
  unsigned __int128 v27; // kr00_16
  char v28; // bl
  unsigned int v29; // r8d
  _QWORD *v30; // r8
  const struct std::filesystem::path *v31; // rdx
  __int64 v32; // r8
  void **v33; // r9
  unsigned __int64 v34; // rdx
  LPCWSTR *v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  LPCWSTR *v38; // r8
  const WCHAR *v39; // rdx
  int PluginLibrary; // eax
  unsigned __int16 *v41; // rax
  int v42; // eax
  int v43; // ebx
  LPCWSTR *v44; // r8
  int v45; // eax
  int v46; // eax
  int v47; // eax
  WaasMedic::CDeferManager *v48; // rcx
  unsigned __int16 **v49; // r8
  int v50; // ebx
  int v51; // eax
  HRESULT v52; // eax
  LPCWSTR *v53; // r8
  LPCWSTR *v54; // r8
  WaasMedic *v55; // rcx
  int v56; // eax
  const unsigned __int16 *v57; // rdx
  const unsigned __int16 *v58; // rcx
  int v59; // r8d
  int v60; // eax
  signed int LastError; // eax
  HRESULT v62; // eax
  int *v64; // [rsp+20h] [rbp-E0h]
  __int64 v65; // [rsp+28h] [rbp-D8h]
  __int64 v66; // [rsp+30h] [rbp-D0h]
  char v67; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+74h] [rbp-8Ch]
  int v69; // [rsp+78h] [rbp-88h] BYREF
  int v70; // [rsp+7Ch] [rbp-84h] BYREF
  __int16 v71; // [rsp+80h] [rbp-80h]
  unsigned int v72; // [rsp+84h] [rbp-7Ch] BYREF
  char *v73; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v74; // [rsp+90h] [rbp-70h]
  char *v75; // [rsp+98h] [rbp-68h]
  __int64 v76; // [rsp+A0h] [rbp-60h]
  __int64 v77; // [rsp+A8h] [rbp-58h]
  unsigned __int8 (__fastcall ***v78)(_QWORD); // [rsp+B0h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v80[8]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpSrc[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v82; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v83; // [rsp+F0h] [rbp-10h]
  void *Src[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v85; // [rsp+108h] [rbp+8h]
  unsigned __int64 v86; // [rsp+110h] [rbp+10h]
  WaasMedic *v87[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v88; // [rsp+128h] [rbp+28h]
  unsigned __int64 v89; // [rsp+130h] [rbp+30h]
  _QWORD v90[4]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v91[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v92[12]; // [rsp+180h] [rbp+80h] BYREF
  char v93[144]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v77 = a4;
  v78 = a2;
  v8 = a5;
  v74 = a5;
  v9 = 0;
  v68 = 0;
  memset_0(v93, 0, 0x81u);
  *(_OWORD *)v87 = 0;
  v88 = 0;
  v89 = 7;
  LOWORD(v87[0]) = 0;
  v69 = 0;
  v72 = 0;
  WaasMedic::CDeferManager::CDeferManager((WaasMedic::CDeferManager *)v92);
  v10 = 0;
  v75 = 0;
  VariantInit(&pvarg);
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)(a1 + 8) + 16LL))(
         *(_QWORD *)(a1 + 8),
         0,
         L"Cancel",
         &pvarg) >= 0 )
  {
    if ( pvarg.vt )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**(_QWORD **)(a1 + 8) + 48LL))(
              *(_QWORD *)(a1 + 8),
              0,
              L"Cancel");
      if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024894 )
      {
        v12 = L"Waas Remediation failed to clean up prior cancelation flag.";
LABEL_6:
        LogLevelW(2u, v12);
        goto LABEL_80;
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl) )
  {
    if ( !a5 )
    {
      v13 = ((a3 - 1) & 0xFFFFFFFB) == 0;
      goto LABEL_10;
    }
  }
  else if ( !a5 )
  {
    v13 = a3 == 1;
LABEL_10:
    if ( v13 )
    {
      v12 = L"'ppszPluginsWithIssueDetected' can't be nullptr when detection only mode ";
      goto LABEL_6;
    }
    goto LABEL_14;
  }
  *(_QWORD *)a5 = 0;
LABEL_14:
  if ( a2 && (**a2)(a2) )
  {
    LogLevelW(4u, L"Waas Remediation engine received a cancellation request.");
    goto LABEL_80;
  }
  if ( !*(_BYTE *)(a1 + 32) )
  {
    v14 = L"Waas Remediation engine was not initialized before calling Run. hr = 0x%08x";
LABEL_20:
    LogLevelW(2u, v14, 2147549183LL);
    goto LABEL_80;
  }
  v15 = *(volatile signed __int64 **)(a1 + 56);
  if ( v15
    || ((v16 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow),
         (v73 = (char *)v16) == 0)
      ? (v15 = 0)
      : (v15 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v16)),
        (*(_QWORD *)(a1 + 56) = v15) != 0) )
  {
    if ( !TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v15,
            _InterlockedExchangeAdd64(v15 + 17, 0),
            v93) )
    {
      v14 = L"Failed to get cV in WaasMedic engine. hr = 0x%08x";
      goto LABEL_20;
    }
  }
  else
  {
    v93[0] = 0;
  }
  UnifiedImpactLevel = WaasMedic::CWaasRemediation::GetUnifiedImpactLevel(
                         (WaasMedic::CWaasRemediation *)a1,
                         (enum winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel *)&v72);
  if ( UnifiedImpactLevel < 0 )
  {
    LogLevelW(2u, L"Failed to get unified impact level. hr = 0x%08x", (unsigned int)UnifiedImpactLevel);
    goto LABEL_80;
  }
  v18 = WaasMedic::CDeferManager::Initialize((WaasMedic::CDeferManager *)v92);
  if ( v18 < 0 )
  {
    LogLevelW(2u, L"Failed in CDeferManager.Initialize() with error hr = 0x%08x.", (unsigned int)v18);
LABEL_80:
    v47 = WaasMedic::CDeferManager::FinalizeSchedule((WaasMedic::CDeferManager *)v92);
    v50 = v47;
    if ( v47 < 0 )
      LogLevelW(2u, L"Failed in FinalizeSchedule with error hr = 0x%08X.", (unsigned int)v47);
    if ( a3 == 3 )
    {
      v51 = WaasMedic::CDeferManager::SignalMaintenanceCompleted(v48);
      v50 = v51;
      if ( v51 < 0 )
        LogLevelW(2u, L"Could not signal maintenance completion. hr = 0x%08x", (unsigned int)v51);
    }
    else if ( a3 == 1 )
    {
      v55 = (WaasMedic *)v87;
      if ( v89 > 7 )
        v55 = v87[0];
      v56 = WaasMedic::SafeAllocString(v55, v8, v49);
      v50 = v56;
      if ( v56 < 0 )
        LogLevelW(2u, L"Failed to allocate string for 'ppszPluginsWithIssueDetected'.  hr = 0x%08x.", (unsigned int)v56);
      if ( !v69 )
      {
        LogLevelW(4u, L"All plugins didn't detect any issue. Sending WER report now.");
        v60 = WaasMedic::CWERReporter::ReportError(v58, v57, v59, *(struct WaasMedic::IStateProvider **)(a1 + 8));
        v50 = v60;
        if ( v60 < 0 )
        {
          LogLevelW(2u, L"Failed to call CWERReporter::ReportError with error hr=0x%08X", (unsigned int)v60);
          LogLevelW(2u, L"Failed to send WER report with error hr = 0x%08X.", (unsigned int)v50);
        }
      }
    }
    LogLevelW(5u, L"Signaling completion, will set m_xhCompleted event.");
    if ( !SetEvent(*(HANDLE *)(a1 + 40)) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"Failed to Set completed/cancelled event! hr = 0x%08x", (unsigned int)LastError);
    }
    *(_BYTE *)(a1 + 33) = 0;
    if ( v50 >= 0 )
      v50 = v9;
    v62 = VariantClear(&pvarg);
    if ( v62 < 0 )
      _com_issue_error(v62);
    if ( v10 )
      goto LABEL_112;
    goto LABEL_113;
  }
  *(_OWORD *)Src = 0;
  v85 = 0;
  v86 = 0;
  v19 = -1;
  do
    ++v19;
  while ( v93[v19] );
  std::string::_Construct<1,char const *>(Src, v93);
  WaasMedic::CDeferManager::SetCV(v92, Src);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl'::`2'::impl) )
  {
    v20 = a3 == 1 || a3 == 2;
    if ( a3 == 5 )
      v20 = 1;
  }
  else
  {
    v20 = a3 == 1 || a3 == 2;
  }
  *(_WORD *)(a1 + 33) = 1;
  v10 = (char *)operator new(0x10u);
  v73 = v10;
  *(_QWORD *)v10 = &uus::Session::`vftable';
  v21 = uus::Utility::GetFirstBrainSession<uus::Brain3>(L"waasmedic.engine.runex", 0);
  *((_QWORD *)v10 + 1) = v21;
  v75 = v10;
  v22 = *(_QWORD *)(a1 + 24);
  if ( v21 )
    v23 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
  else
    v23 = L"0.0.0.0";
  *(_OWORD *)Src = 0;
  v85 = 0;
  v86 = 0;
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  std::wstring::_Construct<1,unsigned short const *>(Src, v23);
  WaasMedic::SummaryEvent::SetUUSVersion(v22, Src);
  v25 = (char *)*((_QWORD *)&WaasMedic::pluginCapsuleCollection + 1);
  v27 = WaasMedic::pluginCapsuleCollection;
  v73 = (char *)(v27 >> 64);
  for ( i = (char *)v27; ; i += 40 )
  {
    if ( i == v25 )
      goto LABEL_79;
    *(_OWORD *)lpSrc = 0;
    v82 = 0;
    v83 = 7;
    LOWORD(lpSrc[0]) = 0;
    std::wstring::wstring(v90, i + 8);
    v28 = *i;
    v67 = *i;
    if ( !i[1] )
    {
      *(_OWORD *)Src = 0;
      v85 = 0;
      v86 = 0;
      std::wstring::_Construct<1,unsigned short const *>(Src, L"%windir%\\System32\\", 18);
      v37 = std::wstring::append(Src);
      v91[0] = *(_OWORD *)v37;
      v91[1] = *(_OWORD *)(v37 + 16);
      *(_QWORD *)(v37 + 16) = 0;
      *(_QWORD *)(v37 + 24) = 7;
      *(_WORD *)v37 = 0;
      std::wstring::operator=(lpSrc, v91);
      std::wstring::~wstring(v91);
      goto LABEL_62;
    }
    v29 = *(_DWORD *)Feature_UUS_WaasMedic_Capsule__descriptor;
    if ( (*(_DWORD *)Feature_UUS_WaasMedic_Capsule__descriptor & 4) == 0 )
    {
      v76 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UUS_WaasMedic_Capsule>::GetCachedFeatureEnabledState(
                         0,
                         v80);
      v29 = v76;
    }
    v70 = 0;
    v71 = 3;
    LODWORD(v66) = 3;
    LODWORD(v65) = 1;
    v64 = &v70;
    wil::details::ReportUsageToService(&qword_1800A5A98, 36612934, (v29 >> 10) & 1, (v29 >> 11) & 1);
    v30 = v90;
    if ( v90[3] > 7u )
      v30 = (_QWORD *)v90[0];
    uus::Session::GetFullPath(v10, Src, v30);
    if ( !std::filesystem::exists((std::filesystem *)Src, v31) )
      break;
    v33 = Src;
    if ( v86 > 7 )
      v33 = (void **)Src[0];
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    if ( v34 > v83 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        lpSrc,
        v34,
        v32,
        v33);
    }
    else
    {
      v35 = lpSrc;
      if ( v83 > 7 )
        v35 = (LPCWSTR *)lpSrc[0];
      v82 = v34;
      v36 = 2 * v34;
      memmove_0(v35, v33, 2 * v34);
      *(_WORD *)((char *)v35 + v36) = 0;
      v28 = v67;
      v25 = v73;
    }
LABEL_62:
    std::wstring::~wstring(Src);
    v38 = lpSrc;
    if ( v83 > 7 )
      v38 = (LPCWSTR *)lpSrc[0];
    LogLevelW(4u, L"Full path to capsule: %s", v38);
    v39 = (const WCHAR *)lpSrc;
    if ( v83 > 7 )
      v39 = lpSrc[0];
    PluginLibrary = WaasMedic::CWaasRemediation::LoadPluginLibrary((WaasMedic::CWaasRemediation *)a1, v39);
    if ( PluginLibrary < 0 )
    {
      if ( PluginLibrary == -2147024894 && v28 )
      {
        v53 = lpSrc;
        if ( v83 > 7 )
          v53 = (LPCWSTR *)lpSrc[0];
        LogLevelW(4u, L"Optional capsule (%s) doesn't exist.", v53);
      }
      else
      {
        v54 = lpSrc;
        if ( v83 > 7 )
          v54 = (LPCWSTR *)lpSrc[0];
        LogLevelW(
          2u,
          L"LoadLibrary failed for capsule = %s. hr = 0x%08x",
          v54,
          (unsigned int)PluginLibrary,
          v64,
          v65,
          v66);
      }
      std::wstring::~wstring(v90);
      std::wstring::~wstring(lpSrc);
LABEL_79:
      v8 = v74;
      v9 = v68;
      goto LABEL_80;
    }
    v41 = (unsigned __int16 *)lpSrc;
    if ( v83 > 7 )
      v41 = (unsigned __int16 *)lpSrc[0];
    v42 = WaasMedic::CWaasRemediation::RunPluginsInCapsule(
            (WaasMedic::CWaasRemediation *)a1,
            v20,
            v72,
            v78,
            (unsigned __int16 *)v77,
            a3,
            v41,
            (__int64)v93,
            &v69,
            0,
            0,
            v87,
            (WaasMedic::CDeferManager *)v92);
    v43 = v42;
    if ( v42 < 0 )
    {
      v44 = lpSrc;
      if ( v83 > 7 )
        v44 = (LPCWSTR *)lpSrc[0];
      LogLevelW(2u, L"RunPluginsInCapsule failed.  Capsule = %s. hr = 0x%08x", v44, (unsigned int)v42);
      v45 = v68;
      if ( v68 >= 0 )
        v45 = v43;
      v68 = v45;
    }
    v46 = WaasMedic::CWaasRemediation::FreePluginLibrary((WaasMedic::CWaasRemediation *)a1);
    if ( v46 < 0 )
      LogLevelW(2u, L"FreePluginLibrary failed. hr = 0x%08x", (unsigned int)v46);
    std::wstring::~wstring(v90);
    std::wstring::~wstring(lpSrc);
  }
  v50 = -2147024894;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x27E,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\engine\\waasremediation.cpp",
    (const char *)0x80070002LL,
    (int)&v70);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v90);
  std::wstring::~wstring(lpSrc);
  v52 = VariantClear(&pvarg);
  if ( v52 < 0 )
    _com_issue_error(v52);
LABEL_112:
  (**(void (__fastcall ***)(char *, __int64))v10)(v10, 1);
LABEL_113:
  WaasMedic::CDeferManager::~CDeferManager((WaasMedic::CDeferManager *)v92);
  std::wstring::~wstring(v87);
  return (unsigned int)v50;
}

```

## disassembly

```asm
0x1800184b0  push    rbp
0x1800184b2  push    rbx
0x1800184b3  push    rsi
0x1800184b4  push    rdi
0x1800184b5  push    r12
0x1800184b7  push    r13
0x1800184b9  push    r14
0x1800184bb  push    r15
0x1800184bd  lea     rbp, [rsp-188h]
0x1800184c5  sub     rsp, 288h
0x1800184cc  mov     rax, cs:__security_cookie
0x1800184d3  xor     rax, rsp
0x1800184d6  mov     [rbp+1C0h+var_50], rax
0x1800184dd  mov     [rbp+1C0h+var_218], r9
0x1800184e1  mov     r13d, r8d
0x1800184e4  mov     rbx, rdx
0x1800184e7  mov     [rbp+1C0h+var_210], rdx
0x1800184eb  mov     rsi, rcx
0x1800184ee  mov     rdi, [rbp+1C0h+arg_20]
0x1800184f5  mov     [rbp+1C0h+var_230], rdi
0x1800184f9  xor     r12d, r12d
0x1800184fc  mov     r15d, r12d
0x1800184ff  mov     [rsp+2C0h+var_24C], r12d
0x180018504  xor     edx, edx; Val
0x180018506  mov     r8d, 81h; Size
0x18001850c  lea     rcx, [rbp+1C0h+var_E0]; void *
0x180018513  call    memset_0
0x180018518  xorps   xmm0, xmm0
0x18001851b  movups  xmmword ptr [rbp+1C0h+var_1A8], xmm0
0x18001851f  mov     [rbp+1C0h+var_198], r12
0x180018523  mov     [rbp+1C0h+var_190], 7
0x18001852b  mov     word ptr [rbp+1C0h+var_1A8], r12w
0x180018530  mov     dword ptr [rsp+2C0h+var_248], r12d
0x180018535  mov     [rbp+1C0h+var_23C], r12d
0x180018539  lea     rcx, [rbp+1C0h+var_140]; this
0x180018540  call    ??0CDeferManager@WaasMedic@@QEAA@XZ; WaasMedic::CDeferManager::CDeferManager(void)
0x180018545  nop
0x180018546  mov     r14d, r12d
0x180018549  mov     [rbp+1C0h+var_228], r12
0x18001854d  lea     rcx, [rbp+1C0h+pvarg]; pvarg
0x180018551  call    cs:__imp_VariantInit
0x180018557  nop
0x180018558  mov     rcx, [rsi+8]
0x18001855c  mov     rax, [rcx]
0x18001855f  lea     r9, [rbp+1C0h+pvarg]
0x180018563  lea     r8, aCancel; "Cancel"
0x18001856a  xor     edx, edx
0x18001856c  mov     rax, [rax+10h]
0x180018570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018575  test    eax, eax
0x180018577  js      short loc_1800185C2
0x180018579  cmp     word ptr [rbp+1C0h+pvarg], r12w
0x18001857e  jz      short loc_1800185C2
0x180018580  mov     rcx, [rsi+8]
0x180018584  mov     rax, [rcx]
0x180018587  lea     r8, aCancel; "Cancel"
0x18001858e  xor     edx, edx
0x180018590  mov     rax, [rax+30h]
0x180018594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018599  mov     edx, 80000000h
0x18001859e  lea     ecx, [rax+rdx]
0x1800185a1  test    edx, ecx
0x1800185a3  jnz     short loc_1800185C2
0x1800185a5  cmp     eax, 80070002h
0x1800185aa  jz      short loc_1800185C2
0x1800185ac  lea     rdx, aWaasRemediatio_6; "Waas Remediation failed to clean up pri"...
0x1800185b3  mov     ecx, 2; unsigned __int8
0x1800185b8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800185bd  jmp     loc_180018ADB
0x1800185c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MCPPluginSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport> `wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl(void)'::`2'::impl
0x1800185c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(void)
0x1800185ce  test    al, al
0x1800185d0  jz      short loc_1800185EB
0x1800185d2  test    rdi, rdi
0x1800185d5  jnz     short loc_1800185F0
0x1800185d7  lea     eax, [r13-1]
0x1800185db  test    eax, 0FFFFFFFBh
0x1800185e0  jnz     short loc_1800185F3
0x1800185e2  lea     rdx, aPpszpluginswit; "'ppszPluginsWithIssueDetected' can't be"...
0x1800185e9  jmp     short loc_1800185B3
0x1800185eb  test    rdi, rdi
0x1800185ee  jz      short loc_180018618
0x1800185f0  mov     [rdi], r12
0x1800185f3  test    rbx, rbx
0x1800185f6  jz      short loc_18001861E
0x1800185f8  mov     rax, [rbx]
0x1800185fb  mov     rcx, rbx
0x1800185fe  mov     rax, [rax]
0x180018601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018606  test    al, al
0x180018608  jz      short loc_18001861E
0x18001860a  lea     rdx, aWaasRemediatio_7; "Waas Remediation engine received a canc"...
0x180018611  mov     ecx, 4
0x180018616  jmp     short loc_1800185B8
0x180018618  cmp     r13d, 1
0x18001861c  jmp     short loc_1800185E0
0x18001861e  cmp     [rsi+20h], r12b
0x180018622  jnz     short loc_180018640
0x180018624  lea     rdx, aWaasRemediatio_2; "Waas Remediation engine was not initial"...
0x18001862b  mov     r8d, 8000FFFFh
0x180018631  mov     ecx, 2; unsigned __int8
0x180018636  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001863b  jmp     loc_180018ADB
0x180018640  mov     rax, [rsi+38h]
0x180018644  test    rax, rax
0x180018647  jnz     short loc_18001869C
0x180018649  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018650  mov     ecx, 90h; unsigned __int64
0x180018655  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001865a  mov     [rbp+1C0h+var_238], rax
0x18001865e  test    rax, rax
0x180018661  jz      short loc_18001866D
0x180018663  mov     rcx, rax; this
0x180018666  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18001866b  jmp     short loc_180018670
0x18001866d  mov     rax, r12
0x180018670  mov     [rsi+38h], rax
0x180018674  test    rax, rax
0x180018677  jnz     short loc_18001869C
0x180018679  mov     [rbp+1C0h+var_E0], r12b
0x180018680  lea     rdx, [rbp+1C0h+var_23C]; enum winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel *
0x180018684  mov     rcx, rsi; this
0x180018687  call    ?GetUnifiedImpactLevel@CWaasRemediation@WaasMedic@@QEAAJAEAW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@@Z; WaasMedic::CWaasRemediation::GetUnifiedImpactLevel(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel &)
0x18001868c  test    eax, eax
0x18001868e  jns     short loc_1800186C7
0x180018690  mov     r8d, eax
0x180018693  lea     rdx, aFailedToGetUni; "Failed to get unified impact level. hr "...
0x18001869a  jmp     short loc_180018631
0x18001869c  mov     rdx, r12
0x18001869f  lock xadd [rax+88h], rdx; unsigned __int64
0x1800186a8  lea     r8, [rbp+1C0h+var_E0]; char *
0x1800186af  mov     rcx, rax; this
0x1800186b2  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800186b7  test    al, al
0x1800186b9  jnz     short loc_180018680
0x1800186bb  lea     rdx, aFailedToGetCvI; "Failed to get cV in WaasMedic engine. h"...
0x1800186c2  jmp     loc_18001862B
0x1800186c7  lea     rcx, [rbp+1C0h+var_140]; this
0x1800186ce  call    ?Initialize@CDeferManager@WaasMedic@@QEAAJXZ; WaasMedic::CDeferManager::Initialize(void)
0x1800186d3  test    eax, eax
0x1800186d5  jns     short loc_1800186E6
0x1800186d7  mov     r8d, eax
0x1800186da  lea     rdx, aFailedInCdefer; "Failed in CDeferManager.Initialize() wi"...
0x1800186e1  jmp     loc_180018631
0x1800186e6  xorps   xmm0, xmm0
0x1800186e9  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x1800186ed  mov     [rbp+1C0h+var_1B8], r12
0x1800186f1  mov     [rbp+1C0h+var_1B0], r12
0x1800186f5  lea     rax, [rbp+1C0h+var_E0]
0x1800186fc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180018700  mov     r8, r15
0x180018703  inc     r8
0x180018706  cmp     [rax+r8], r12b
0x18001870a  jnz     short loc_180018703
0x18001870c  lea     rdx, [rbp+1C0h+var_E0]
0x180018713  lea     rcx, [rbp+1C0h+Src]
0x180018717  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001871c  lea     rdx, [rbp+1C0h+Src]
0x180018720  lea     rcx, [rbp+1C0h+var_140]
0x180018727  call    ?SetCV@CDeferManager@WaasMedic@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WaasMedic::CDeferManager::SetCV(std::string)
0x18001872c  cmp     r13d, 2
0x180018730  setz    bl
0x180018733  mov     edi, 1
0x180018738  cmp     r13d, edi
0x18001873b  setz    al
0x18001873e  or      bl, al
0x180018740  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MCPPluginSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport> `wil::Feature<__WilFeatureTraits_Feature_MCPPluginSupport>::GetImpl(void)'::`2'::impl
0x180018747  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MCPPluginSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MCPPluginSupport>::__private_IsEnabled(void)
0x18001874c  test    al, al
0x18001874e  jz      short loc_18001875E
0x180018750  movzx   r12d, bl
0x180018754  cmp     r13d, 5
0x180018758  cmovz   r12d, edi
0x18001875c  jmp     short loc_180018761
0x18001875e  mov     r12b, bl
0x180018761  mov     [rsi+21h], di
0x180018765  xor     edi, edi
0x180018767  lea     ecx, [rdi+10h]; Size
0x18001876a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001876f  mov     r14, rax
0x180018772  mov     [rbp+1C0h+var_238], rax
0x180018776  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x18001877d  mov     [r14], rax
0x180018780  xor     edx, edx
0x180018782  lea     rcx, aWaasmedicEngin_1; "waasmedic.engine.runex"
0x180018789  call    ??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z; uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)
0x18001878e  mov     rdx, rax
0x180018791  mov     [r14+8], rax
0x180018795  mov     [rbp+1C0h+var_228], r14
0x180018799  mov     rbx, [rsi+18h]
0x18001879d  test    rax, rax
0x1800187a0  jz      short loc_1800187B3
0x1800187a2  mov     rcx, [rax]
0x1800187a5  mov     rax, [rcx+20h]
0x1800187a9  mov     rcx, rdx
0x1800187ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187b1  jmp     short loc_1800187BA
0x1800187b3  lea     rax, a0000; "0.0.0.0"
0x1800187ba  xorps   xmm0, xmm0
0x1800187bd  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x1800187c1  mov     [rbp+1C0h+var_1B8], rdi
0x1800187c5  mov     [rbp+1C0h+var_1B0], rdi
0x1800187c9  mov     r8, r15
0x1800187cc  inc     r8
0x1800187cf  cmp     [rax+r8*2], di
0x1800187d4  jnz     short loc_1800187CC
0x1800187d6  mov     rdx, rax
0x1800187d9  lea     rcx, [rbp+1C0h+Src]
0x1800187dd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800187e2  nop
0x1800187e3  lea     rdx, [rbp+1C0h+Src]
0x1800187e7  mov     rcx, rbx
0x1800187ea  call    ?SetUUSVersion@SummaryEvent@WaasMedic@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::SummaryEvent::SetUUSVersion(std::wstring)
0x1800187ef  mov     r15, qword ptr cs:?pluginCapsuleCollection@WaasMedic@@3V?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@@2@@std@@A; std::vector<std::tuple<std::wstring,bool,bool>> WaasMedic::pluginCapsuleCollection
0x1800187f6  mov     rdi, qword ptr cs:?pluginCapsuleCollection@WaasMedic@@3V?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N_N@std@@@2@@std@@A+8; std::vector<std::tuple<std::wstring,bool,bool>> WaasMedic::pluginCapsuleCollection
0x1800187fd  mov     [rbp+1C0h+var_238], rdi
0x180018801  jmp     loc_180018AC6
0x180018806  xorps   xmm0, xmm0
0x180018809  movups  xmmword ptr [rbp+1C0h+lpSrc], xmm0
0x18001880d  xor     eax, eax
0x18001880f  mov     [rbp+1C0h+var_1D8], rax
0x180018813  mov     [rbp+1C0h+var_1D0], 7
0x18001881b  mov     word ptr [rbp+1C0h+lpSrc], ax
0x18001881f  lea     rdx, [r15+8]
0x180018823  lea     rcx, [rbp+1C0h+var_188]
0x180018827  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001882c  nop
0x18001882d  mov     bl, [r15]
0x180018830  mov     [rsp+2C0h+var_250], bl
0x180018834  xor     ecx, ecx
0x180018836  cmp     [r15+1], cl
0x18001883a  jz      loc_18001893E
0x180018840  mov     rax, cs:Feature_UUS_WaasMedic_Capsule__descriptor
0x180018847  mov     r8d, [rax]
0x18001884a  test    r8b, 4
0x18001884e  jnz     short loc_180018863
0x180018850  lea     rdx, [rbp+1C0h+var_1F0]
0x180018854  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UUS_WaasMedic_Capsule@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UUS_WaasMedic_Capsule>::GetCachedFeatureEnabledState(void)
0x180018859  mov     rcx, [rax]
0x18001885c  mov     [rbp+1C0h+var_220], rcx
0x180018860  mov     r8d, ecx
0x180018863  mov     dword ptr [rsp+2C0h+var_248+4], 0
0x18001886b  mov     [rbp+1C0h+var_240], 3
0x180018871  mov     r9d, r8d
0x180018874  shr     r9d, 0Bh
0x180018878  mov     eax, 1
0x18001887d  and     r9d, eax
0x180018880  shr     r8d, 0Ah
0x180018884  and     r8d, eax
0x180018887  mov     dword ptr [rsp+2C0h+var_290], 3
0x18001888f  mov     dword ptr [rsp+2C0h+var_298], eax
0x180018893  lea     rax, [rsp+2C0h+var_248+4]
0x180018898  mov     [rsp+2C0h+var_2A0], rax; int
0x18001889d  mov     edx, 22EAB46h
0x1800188a2  lea     rcx, qword_1800A5A98
0x1800188a9  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800188ae  lea     r8, [rbp+1C0h+var_188]
0x1800188b2  cmp     [rbp+1C0h+var_170], 7
0x1800188b7  cmova   r8, [rbp+1C0h+var_188]
0x1800188bc  lea     rdx, [rbp+1C0h+Src]
0x1800188c0  mov     rcx, r14
0x1800188c3  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z; uus::Session::GetFullPath(ushort const *)
0x1800188c8  nop
0x1800188c9  lea     rcx, [rbp+1C0h+Src]; this
0x1800188cd  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800188d2  xor     ecx, ecx
0x1800188d4  test    al, al
0x1800188d6  jz      loc_180018B29
0x1800188dc  lea     r9, [rbp+1C0h+Src]
0x1800188e0  cmp     [rbp+1C0h+var_1B0], 7
0x1800188e5  cmova   r9, [rbp+1C0h+Src]
0x1800188ea  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800188ee  inc     rdx
0x1800188f1  cmp     [r9+rdx*2], cx
0x1800188f6  jnz     short loc_1800188EE
0x1800188f8  cmp     rdx, [rbp+1C0h+var_1D0]
0x1800188fc  ja      short loc_180018932
0x1800188fe  lea     rdi, [rbp+1C0h+lpSrc]
0x180018902  cmp     [rbp+1C0h+var_1D0], 7
0x180018907  cmova   rdi, [rbp+1C0h+lpSrc]
0x18001890c  mov     [rbp+1C0h+var_1D8], rdx
0x180018910  lea     rbx, [rdx+rdx]
0x180018914  mov     r8, rbx; Size
0x180018917  mov     rdx, r9; Src
0x18001891a  mov     rcx, rdi; void *
0x18001891d  call    memmove_0
0x180018922  xor     eax, eax
0x180018924  mov     [rbx+rdi], ax
0x180018928  mov     bl, [rsp+2C0h+var_250]
0x18001892c  mov     rdi, [rbp+1C0h+var_238]
0x180018930  jmp     short loc_18001893C
0x180018932  lea     rcx, [rbp+1C0h+lpSrc]
0x180018936  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001893b  nop
0x18001893c  jmp     short loc_1800189A8
0x18001893e  xorps   xmm0, xmm0
0x180018941  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x180018945  mov     [rbp+1C0h+var_1B8], rcx
0x180018949  mov     [rbp+1C0h+var_1B0], rcx
0x18001894d  mov     r8d, 12h
  ... truncated ...
```
