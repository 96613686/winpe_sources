# WaasMedic::CWaasRemediation::CheckIfPluginIsRunnable(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,ushort const *,bool,long &,long &,bool &,bool &,tagPluginActionApplicability &)

- ea: `0x180011fdc`
- end: `0x180012329`
- name: `?CheckIfPluginIsRunnable@CWaasRemediation@WaasMedic@@AEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@PEBG_NAEAJ3AEA_N4AEAW4tagPluginActionApplicability@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180018d3c`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18001039c`
- `0x180011fdc`
- `0x180015da8`
- `0x1800160ac`
- `0x18001d5b0`
- `0x18002e56c`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120c4`

## string_xrefs

- `0x180012233`: `Inapplicable due to Service Managed`
- `0x1800122d1`: `Inapplicable due to plugin specific logical condition`
- `0x180012112`: `Plugin "%s" is not enabled. Nothing to do.`
- `0x18001215f`: `Plugin "%s" is interactive only. Nothing to do..`
- `0x1800122f6`: `Plugin %s has inapplicability reason: %s`
- `0x180012074`: `Plugin_IsEnabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CWaasRemediation::CheckIfPluginIsRunnable(
        HMODULE *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        char a4,
        int *a5,
        int *a6,
        _BYTE *a7,
        bool *a8,
        int *a9)
{
  signed int LastError; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  FARPROC ProcAddress; // rdi
  char v15; // r12
  int IsInteractiveOnly; // eax
  int IsActionApplicable; // eax
  bool v18; // zf
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  const wchar_t *v26; // r9
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  bool v34; // [rsp+30h] [rbp-61h] BYREF
  char v35; // [rsp+31h] [rbp-60h]
  unsigned int v36; // [rsp+34h] [rbp-5Dh]
  int *v37; // [rsp+38h] [rbp-59h]
  _OWORD v38[2]; // [rsp+40h] [rbp-51h] BYREF
  _BYTE v39[32]; // [rsp+60h] [rbp-31h] BYREF

  v35 = a4;
  v36 = a2;
  v37 = a6;
  v34 = 0;
  *a9 = 12;
  *a8 = 0;
  if ( !a1[8] )
  {
    LastError = -2147312566;
    v12 = -2147312566;
LABEL_10:
    LogLevelW(2u, L"IsEnabled for %s failed! hr = 0x%08x.", a3, (unsigned int)LastError);
    return v12;
  }
  LogLevelW(4u, L"Checking if %s is enabled");
  memset(v38, 0, sizeof(v38));
  std::wstring::_Construct<1,unsigned short const *>(v38, L"Plugin_IsEnabled", 16);
  v13 = WaasMedic::ws2s(v39, v38);
  if ( *(_QWORD *)(v13 + 24) > 0xFu )
    v13 = *(_QWORD *)v13;
  ProcAddress = GetProcAddress(a1[8], (LPCSTR)v13);
  std::string::~string(v39);
  std::wstring::~wstring(v38);
  if ( ProcAddress )
  {
    LastError = ((__int64 (__fastcall *)(const unsigned __int16 *, _BYTE *))ProcAddress)(a3, a7);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v12 = LastError;
  if ( LastError < 0 )
    goto LABEL_10;
  if ( !*a7 )
  {
    LogLevelW(4u, L"Plugin \"%s\" is not enabled. Nothing to do.", a3);
    *a5 = 2392068;
    return v12;
  }
  v15 = v35;
  if ( !v35 )
  {
    IsInteractiveOnly = WaasMedic::CWaasRemediation::Plugin_IsInteractiveOnly(
                          (WaasMedic::CWaasRemediation *)a1,
                          a3,
                          &v34);
    v12 = IsInteractiveOnly;
    if ( IsInteractiveOnly < 0 )
    {
      LogLevelW(2u, L"IsInteractiveOnly for %s failed! hr = 0x%08x.", a3, (unsigned int)IsInteractiveOnly);
      return v12;
    }
    if ( v34 )
    {
      LogLevelW(4u, L"Plugin \"%s\" is interactive only. Nothing to do..", a3);
      *a5 = 2392069;
      *a8 = 0;
      return v12;
    }
  }
  IsActionApplicable = WaasMedic::CWaasRemediation::Plugin_IsActionApplicable(
                         (__int64)a1,
                         (__int64)a3,
                         v36,
                         v15,
                         (__int64)a9);
  v12 = IsActionApplicable;
  if ( IsActionApplicable < 0 )
  {
    LogLevelW(2u, L"IsActionApplicable for %s failed! hr = 0x%08x.", a3, (unsigned int)IsActionApplicable);
    return v12;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl) )
    v18 = (*a9 & 0xFFFFFFEF) == 0;
  else
    v18 = *a9 == 0;
  *a8 = v18;
  *a5 = *a9 | 0x242000;
  *v37 = *a9 | 0x242000;
  if ( !*a8 )
  {
    v19 = *a9;
    if ( *a9 > 8 )
    {
      v27 = v19 - 9;
      if ( !v27 )
      {
        v26 = L"Inapplicable due to insufficient disk space";
        goto LABEL_59;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        v26 = L"Inapplicable due to running only in auto runs";
        goto LABEL_59;
      }
      v29 = v28 - 1;
      if ( !v29 )
      {
        v26 = L"Inapplicable due to running only on interactive runs";
        goto LABEL_59;
      }
      v30 = v29 - 1;
      if ( !v30 )
      {
        v26 = L"Inapplicable due to plugin specific logical condition";
        goto LABEL_59;
      }
      v31 = v30 - 1;
      if ( !v31 )
      {
        v26 = L"Inapplicable due to build version";
        goto LABEL_59;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
        v26 = L"Inapplicable due to IPU in progress condition";
        goto LABEL_59;
      }
      if ( v32 == 1 )
      {
        v26 = L"Inapplicable due to cloud based IPU in progress condition";
        goto LABEL_59;
      }
    }
    else
    {
      if ( v19 == 8 )
      {
        v26 = L"Inapplicable due to Max Uptime";
        goto LABEL_59;
      }
      if ( !v19 )
      {
        v26 = L"Applicable";
        goto LABEL_59;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v26 = L"Inapplicable due to action limit";
        goto LABEL_59;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v26 = L"Inapplicable due to Impact Level";
        goto LABEL_59;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v26 = L"Inapplicable due to Interval";
        goto LABEL_59;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v26 = L"Inapplicable due to Connectivity";
        goto LABEL_59;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v26 = L"Inapplicable due to Server SKU";
        goto LABEL_59;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v26 = L"Inapplicable due to Service Managed";
        goto LABEL_59;
      }
      if ( v25 == 1 )
      {
        v26 = L"Inapplicable due to Min Uptime";
LABEL_59:
        LogLevelW(4u, L"Plugin %s has inapplicability reason: %s", a3, v26);
        return v12;
      }
    }
    v26 = &word_180073298;
    goto LABEL_59;
  }
  return v12;
}

```

## disassembly

```asm
0x180011fdc  push    rbp
0x180011fde  push    rbx
0x180011fdf  push    rsi
0x180011fe0  push    rdi
0x180011fe1  push    r12
0x180011fe3  push    r13
0x180011fe5  push    r14
0x180011fe7  push    r15
0x180011fe9  lea     rbp, [rsp-7]
0x180011fee  sub     rsp, 98h
0x180011ff5  mov     rax, cs:__security_cookie
0x180011ffc  xor     rax, rsp
0x180011fff  mov     [rbp+3Fh+var_50], rax
0x180012003  mov     [rbp+3Fh+var_9F], r9b
0x180012007  mov     rbx, r8
0x18001200a  mov     [rbp+3Fh+var_9C], edx
0x18001200d  mov     r13, rcx
0x180012010  mov     r15, [rbp+3Fh+arg_20]
0x180012014  mov     rax, [rbp+3Fh+arg_28]
0x180012018  mov     [rbp+3Fh+var_98], rax
0x18001201c  mov     r12, [rbp+3Fh+arg_30]
0x180012020  mov     r14, [rbp+3Fh+arg_38]
0x180012027  mov     rsi, [rbp+3Fh+arg_40]
0x18001202e  xor     eax, eax
0x180012030  mov     [rbp+3Fh+var_A0], al
0x180012033  mov     dword ptr [rsi], 0Ch
0x180012039  mov     [r14], al
0x18001203c  cmp     [rcx+40h], rax
0x180012040  jnz     short loc_18001204E
0x180012042  mov     eax, 80029C4Ah
0x180012047  mov     edi, eax
0x180012049  jmp     loc_1800120EC
0x18001204e  lea     rdx, aCheckingIfSIsE; "Checking if %s is enabled"
0x180012055  mov     ecx, 4; unsigned __int8
0x18001205a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001205f  xorps   xmm0, xmm0
0x180012062  movups  [rbp+3Fh+var_90], xmm0
0x180012066  xorps   xmm1, xmm1
0x180012069  movdqu  [rbp+3Fh+var_80], xmm1
0x18001206e  mov     r8d, 10h
0x180012074  lea     rdx, aPluginIsenable; "Plugin_IsEnabled"
0x18001207b  lea     rcx, [rbp+3Fh+var_90]
0x18001207f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180012084  nop
0x180012085  lea     rdx, [rbp+3Fh+var_90]
0x180012089  lea     rcx, [rbp+3Fh+var_70]
0x18001208d  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x180012092  cmp     qword ptr [rax+18h], 0Fh
0x180012097  jbe     short loc_18001209C
0x180012099  mov     rax, [rax]
0x18001209c  mov     rdx, rax; lpProcName
0x18001209f  mov     rcx, [r13+40h]; hModule
0x1800120a3  call    cs:__imp_GetProcAddress
0x1800120a9  mov     rdi, rax
0x1800120ac  lea     rcx, [rbp+3Fh+var_70]
0x1800120b0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800120b5  nop
0x1800120b6  lea     rcx, [rbp+3Fh+var_90]; void *
0x1800120ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800120bf  test    rdi, rdi
0x1800120c2  jnz     short loc_1800120D8
0x1800120c4  call    cs:__imp_GetLastError
0x1800120ca  test    eax, eax
0x1800120cc  jle     short loc_1800120E6
0x1800120ce  movzx   eax, ax
0x1800120d1  or      eax, 80070000h
0x1800120d6  jmp     short loc_1800120E6
0x1800120d8  mov     rdx, r12
0x1800120db  mov     rcx, rbx
0x1800120de  mov     rax, rdi
0x1800120e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e6  mov     edi, eax
0x1800120e8  test    eax, eax
0x1800120ea  jns     short loc_180012108
0x1800120ec  lea     rdx, aIsenabledForSF; "IsEnabled for %s failed! hr = 0x%08x."
0x1800120f3  mov     r9d, eax
0x1800120f6  mov     r8, rbx
0x1800120f9  mov     ecx, 2; unsigned __int8
0x1800120fe  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012103  jmp     loc_180012307
0x180012108  cmp     byte ptr [r12], 0
0x18001210d  jnz     short loc_18001212F
0x18001210f  mov     r8, rbx
0x180012112  lea     rdx, aPluginSIsNotEn; "Plugin \"%s\" is not enabled. Nothing t"...
0x180012119  mov     ecx, 4; unsigned __int8
0x18001211e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012123  mov     dword ptr [r15], 248004h
0x18001212a  jmp     loc_180012307
0x18001212f  mov     r12b, [rbp+3Fh+var_9F]
0x180012133  test    r12b, r12b
0x180012136  jnz     short loc_180012180
0x180012138  lea     r8, [rbp+3Fh+var_A0]; bool *
0x18001213c  mov     rdx, rbx; unsigned __int16 *
0x18001213f  mov     rcx, r13; this
0x180012142  call    ?Plugin_IsInteractiveOnly@CWaasRemediation@WaasMedic@@AEAAJPEBGPEA_N@Z; WaasMedic::CWaasRemediation::Plugin_IsInteractiveOnly(ushort const *,bool *)
0x180012147  mov     edi, eax
0x180012149  test    eax, eax
0x18001214b  jns     short loc_180012156
0x18001214d  lea     rdx, aIsinteractiveo; "IsInteractiveOnly for %s failed! hr = 0"...
0x180012154  jmp     short loc_1800120F3
0x180012156  cmp     [rbp+3Fh+var_A0], 0
0x18001215a  jz      short loc_180012180
0x18001215c  mov     r8, rbx
0x18001215f  lea     rdx, aPluginSIsInter; "Plugin \"%s\" is interactive only. Noth"...
0x180012166  mov     ecx, 4; unsigned __int8
0x18001216b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012170  mov     dword ptr [r15], 248005h
0x180012177  mov     byte ptr [r14], 0
0x18001217b  jmp     loc_180012307
0x180012180  mov     [rsp+0D0h+var_B0], rsi
0x180012185  mov     r9b, r12b
0x180012188  mov     r8d, [rbp+3Fh+var_9C]
0x18001218c  mov     rdx, rbx
0x18001218f  mov     rcx, r13
0x180012192  call    ?Plugin_IsActionApplicable@CWaasRemediation@WaasMedic@@AEAAJPEBGW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CWaasRemediation::Plugin_IsActionApplicable(ushort const *,winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)
0x180012197  mov     edi, eax
0x180012199  test    eax, eax
0x18001219b  jns     short loc_1800121A9
0x18001219d  lea     rdx, aIsactionapplic; "IsActionApplicable for %s failed! hr = "...
0x1800121a4  jmp     loc_1800120F3
0x1800121a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x1800121b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x1800121b5  test    al, al
0x1800121b7  jz      short loc_1800121C1
0x1800121b9  test    dword ptr [rsi], 0FFFFFFEFh
0x1800121bf  jmp     short loc_1800121C5
0x1800121c1  xor     eax, eax
0x1800121c3  cmp     [rsi], eax
0x1800121c5  setz    al
0x1800121c8  mov     [r14], al
0x1800121cb  mov     eax, [rsi]
0x1800121cd  mov     ecx, 242000h
0x1800121d2  or      eax, ecx
0x1800121d4  mov     [r15], eax
0x1800121d7  mov     eax, [rsi]
0x1800121d9  or      eax, ecx
0x1800121db  mov     rcx, [rbp+3Fh+var_98]
0x1800121df  mov     [rcx], eax
0x1800121e1  cmp     byte ptr [r14], 0
0x1800121e5  jnz     loc_180012307
0x1800121eb  mov     ecx, [rsi]
0x1800121ed  cmp     ecx, 8
0x1800121f0  jg      loc_18001228A
0x1800121f6  jz      loc_180012281
0x1800121fc  test    ecx, ecx
0x1800121fe  jz      short loc_180012278
0x180012200  sub     ecx, 1
0x180012203  jz      short loc_18001226F
0x180012205  sub     ecx, 1
0x180012208  jz      short loc_180012263
0x18001220a  sub     ecx, 1
0x18001220d  jz      short loc_180012257
0x18001220f  sub     ecx, 1
0x180012212  jz      short loc_18001224B
0x180012214  sub     ecx, 1
0x180012217  jz      short loc_18001223F
0x180012219  sub     ecx, 1
0x18001221c  jz      short loc_180012233
0x18001221e  cmp     ecx, 1
0x180012221  jnz     loc_1800122AD
0x180012227  lea     r9, aInapplicableDu_7; "Inapplicable due to Min Uptime"
0x18001222e  jmp     loc_1800122F3
0x180012233  lea     r9, aInapplicableDu_2; "Inapplicable due to Service Managed"
0x18001223a  jmp     loc_1800122F3
0x18001223f  lea     r9, aInapplicableDu_13; "Inapplicable due to Server SKU"
0x180012246  jmp     loc_1800122F3
0x18001224b  lea     r9, aInapplicableDu_9; "Inapplicable due to Connectivity"
0x180012252  jmp     loc_1800122F3
0x180012257  lea     r9, aInapplicableDu_1; "Inapplicable due to Interval"
0x18001225e  jmp     loc_1800122F3
0x180012263  lea     r9, aInapplicableDu_0; "Inapplicable due to Impact Level"
0x18001226a  jmp     loc_1800122F3
0x18001226f  lea     r9, aInapplicableDu_12; "Inapplicable due to action limit"
0x180012276  jmp     short loc_1800122F3
0x180012278  lea     r9, aApplicable; "Applicable"
0x18001227f  jmp     short loc_1800122F3
0x180012281  lea     r9, aInapplicableDu; "Inapplicable due to Max Uptime"
0x180012288  jmp     short loc_1800122F3
0x18001228a  sub     ecx, 9
0x18001228d  jz      short loc_1800122EC
0x18001228f  sub     ecx, 1
0x180012292  jz      short loc_1800122E3
0x180012294  sub     ecx, 1
0x180012297  jz      short loc_1800122DA
0x180012299  sub     ecx, 1
0x18001229c  jz      short loc_1800122D1
0x18001229e  sub     ecx, 1
0x1800122a1  jz      short loc_1800122C8
0x1800122a3  sub     ecx, 1
0x1800122a6  jz      short loc_1800122BF
0x1800122a8  cmp     ecx, 1
0x1800122ab  jz      short loc_1800122B6
0x1800122ad  lea     r9, word_180073298
0x1800122b4  jmp     short loc_1800122F3
0x1800122b6  lea     r9, aInapplicableDu_6; "Inapplicable due to cloud based IPU in "...
0x1800122bd  jmp     short loc_1800122F3
0x1800122bf  lea     r9, aInapplicableDu_5; "Inapplicable due to IPU in progress con"...
0x1800122c6  jmp     short loc_1800122F3
0x1800122c8  lea     r9, aInapplicableDu_4; "Inapplicable due to build version"
0x1800122cf  jmp     short loc_1800122F3
0x1800122d1  lea     r9, aInapplicableDu_10; "Inapplicable due to plugin specific log"...
0x1800122d8  jmp     short loc_1800122F3
0x1800122da  lea     r9, aInapplicableDu_8; "Inapplicable due to running only on int"...
0x1800122e1  jmp     short loc_1800122F3
0x1800122e3  lea     r9, aInapplicableDu_3; "Inapplicable due to running only in aut"...
0x1800122ea  jmp     short loc_1800122F3
0x1800122ec  lea     r9, aInapplicableDu_11; "Inapplicable due to insufficient disk s"...
0x1800122f3  mov     r8, rbx
0x1800122f6  lea     rdx, aPluginSHasInap; "Plugin %s has inapplicability reason: %"...
0x1800122fd  mov     ecx, 4; unsigned __int8
0x180012302  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012307  mov     eax, edi
0x180012309  mov     rcx, [rbp+3Fh+var_50]
0x18001230d  xor     rcx, rsp; StackCookie
0x180012310  call    __security_check_cookie
0x180012315  add     rsp, 98h
0x18001231c  pop     r15
0x18001231e  pop     r14
0x180012320  pop     r13
0x180012322  pop     r12
0x180012324  pop     rdi
0x180012325  pop     rsi
0x180012326  pop     rbx
0x180012327  pop     rbp
0x180012328  retn
```
