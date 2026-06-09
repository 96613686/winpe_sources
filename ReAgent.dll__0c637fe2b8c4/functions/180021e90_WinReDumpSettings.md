# WinReDumpSettings

- ea: `0x180021e90`
- end: `0x1800224ea`
- name: `WinReDumpSettings`
- size: `1626`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x180001f94`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x180011378`
- `0x180012430`
- `0x1800124e0`
- `0x180015800`
- `0x18001c5e0`
- `0x18001ef90`
- `0x180021e90`
- `0x180047024`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180022491`
- `KERNEL32!HeapFree` at `0x180022491`
- `KERNEL32!HeapAlloc` at `0x180021f9b`
- `KERNEL32!HeapAlloc` at `0x180021f9b`
- `KERNEL32!GetProcessHeap` at `0x180021f85`
- `KERNEL32!GetProcessHeap` at `0x180022483`
- `KERNEL32!GetProcessHeap` at `0x180021f85`
- `KERNEL32!GetProcessHeap` at `0x180022483`
- `KERNEL32!SetLastError` at `0x1800224b2`
- `KERNEL32!SetLastError` at `0x1800224b2`

## string_xrefs

- `0x180022162`: `failed to copy ssid`
- `0x1800221cd`: `failed to copy password`
- `0x180021fa9`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180022169`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002242a`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180021ff5`: `Failed to create settings object. Error: 0x%x`
- `0x180021f32`: `Parameters: xml file: %s`
- `0x1800223b8`: `Failed to initialize xml parser`
- `0x18002211f`: `Get wifi setting: SSID: %s`
- `0x18002238f`: `Write settings to file`
- `0x1800223c1`: `Write settings to handle`
- `0x180022403`: `Failed to copy recovery settings to parser`
- `0x180022423`: `Failed to update settings to file`

## pseudocode

```c
__int64 __fastcall WinReDumpSettings(unsigned __int16 *a1, void *a2)
{
  unsigned int v2; // edi
  _DWORD *v5; // rsi
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v8; // rax
  struct SrSettings::ISrSettings **v9; // rdx
  int SrSettings; // eax
  __int64 v11; // r14
  int v12; // r15d
  int v13; // r15d
  unsigned __int64 v14; // r11
  int v15; // r12d
  const wchar_t *v16; // r8
  int v17; // eax
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r8
  int v20; // eax
  const unsigned __int16 *v21; // r8
  unsigned int v22; // eax
  int v23; // eax
  unsigned int v24; // eax
  unsigned __int16 *v25; // rbx
  const wchar_t *v26; // r8
  HANDLE v27; // rax
  int v29; // [rsp+28h] [rbp-81h]
  int v30; // [rsp+28h] [rbp-81h]
  __int64 v31; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int16 *v32; // [rsp+40h] [rbp-69h]
  void *Block; // [rsp+48h] [rbp-61h] BYREF
  unsigned __int16 *v34; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int8 v35; // [rsp+58h] [rbp-51h] BYREF
  char v36; // [rsp+59h] [rbp-50h] BYREF
  _BYTE v37[2]; // [rsp+5Ah] [rbp-4Fh] BYREF
  unsigned int v38; // [rsp+5Ch] [rbp-4Dh] BYREF
  void **v39; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 *v40[3]; // [rsp+70h] [rbp-39h] BYREF
  int v41; // [rsp+88h] [rbp-21h]
  __int128 v42; // [rsp+90h] [rbp-19h]
  __int128 v43; // [rsp+A0h] [rbp-9h]
  __int128 v44; // [rsp+B0h] [rbp+7h]

  v2 = 0;
  v32 = a1;
  v31 = 0;
  v39 = &ReAgentLogcallback::`vftable';
  v40[1] = 0;
  v40[0] = (unsigned __int16 *)&SettingXmlParser::`vftable';
  v40[2] = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v36 = 0;
  v37[0] = 0;
  v35 = 0;
  v38 = 0;
  Block = 0;
  v34 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReDumpSettings");
  UnattendLogW(0, L"Parameters: xml file: %s", a1);
  if ( a1 )
  {
    if ( !a2 )
      goto LABEL_7;
  }
  else if ( (((unsigned __int64)a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = 0;
    v6 = 87;
    UnattendLogW(1, L"Invalid parameter");
    v2 = 0;
    goto LABEL_65;
  }
  if ( a2 != (void *)-1LL )
    UnattendLogW(0, L"Will dump setting to handle");
LABEL_7:
  ProcessHeap = GetProcessHeap();
  v6 = 8;
  v8 = HeapAlloc(ProcessHeap, 8u, 0x4D0u);
  v5 = v8;
  if ( !v8 )
  {
    UnattendLogW(
      2,
      L"WinReDumpSettings %s (0x%x) in file %S line %d",
      L"failed to allocate memory",
      8,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      8766);
    goto LABEL_65;
  }
  v8[307] = 0;
  SrSettings = SrSettings::CreateSrSettings((SrSettings *)&v31, v9);
  v11 = v31;
  LOWORD(v12) = SrSettings;
  if ( SrSettings < 0 )
  {
    UnattendLogW(1, L"Failed to create settings object. Error: 0x%x", (unsigned int)SrSettings);
LABEL_11:
    v6 = (unsigned __int16)v12;
    goto LABEL_63;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, void ***, _QWORD, _QWORD))(*(_QWORD *)v31 + 8LL))(v31, &v39, 0, 0);
  if ( v12 < 0 )
  {
    UnattendLogW(1, L"Failed to initialize settings object. Error: 0x%x", (unsigned int)v12);
    goto LABEL_11;
  }
  v36 = 0;
  v2 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetImpl'::`2'::impl) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v11 + 136LL))(v11, &v36, 0);
    if ( v13 < 0 )
      goto LABEL_16;
    if ( !v36 )
    {
LABEL_20:
      v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int8 *))(*(_QWORD *)v11 + 72LL))(
              v11,
              L"CloudRemediation",
              &v35);
      if ( v13 < 0 )
      {
        UnattendLogW(1, L"Failed to get cloud remediation setting. Error: 0x%x", (unsigned int)v13);
        goto LABEL_17;
      }
      v17 = v35;
      v5[307] |= 0x20u;
      v5[305] = v17;
      v18 = L"on";
      if ( !v35 )
        v18 = L"off";
      UnattendLogW(0, L"Get cloud remediation setting: %s", v18);
      v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int8 *))(*(_QWORD *)v11 + 72LL))(
              v11,
              L"AutoRemediation",
              &v35);
      if ( v13 < 0 )
      {
        UnattendLogW(1, L"Failed to get auto remediation setting. Error: 0x%x", (unsigned int)v13);
        goto LABEL_17;
      }
      v5[304] = v35;
      v5[307] |= 2u;
      v19 = L"on";
      if ( !v35 )
        v19 = L"off";
      UnattendLogW(0, L"Get auto remediation setting: %s", v19);
      v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int8 *))(*(_QWORD *)v11 + 72LL))(
              v11,
              L"HeadlessMode",
              &v35);
      if ( v15 < 0 )
      {
        UnattendLogW(1, L"Failed to get headless setting. Error: 0x%x", (unsigned int)v15);
        goto LABEL_31;
      }
      v20 = v35;
      v21 = L"on";
      v5[307] |= 4u;
      v5[306] = v20;
      if ( !v35 )
        v21 = L"off";
      UnattendLogW(0, L"Get headless setting: %s", v21);
      v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v11 + 24LL))(
              v11,
              L"TotalWaitTime",
              &v38);
      if ( v15 < 0 )
      {
        UnattendLogW(1, L"Failed to get total wait time setting. Error: 0x%x", (unsigned int)v15);
        goto LABEL_31;
      }
      v22 = v38;
      v5[307] |= 8u;
      v5[302] = v22;
      UnattendLogW(0, L"Get total wait time setting: %d", v38);
      v23 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v11 + 24LL))(
              v11,
              L"WaitInterval",
              &v38);
      LOWORD(v6) = v23;
      if ( v23 < 0 )
      {
        UnattendLogW(1, L"Failed to get wait interval setting. Error: 0x%x", (unsigned int)v23);
        v6 = (unsigned __int16)v6;
        goto LABEL_62;
      }
      v24 = v38;
      v5[307] |= 0x10u;
      v5[303] = v24;
      UnattendLogW(0, L"Get wait interval setting: %d", v38);
      v25 = v32;
      if ( v32 )
      {
        UnattendLogW(0, L"Write settings to file");
        v6 = SettingXmlParser::Init((SettingXmlParser *)v40, v25, 0);
        if ( v6 )
        {
          v30 = 8910;
LABEL_54:
          v26 = L"Failed to initialize xml parser";
LABEL_61:
          UnattendLogW(
            2,
            L"WinReDumpSettings %s (0x%x) in file %S line %d",
            v26,
            v6,
            "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
            v30);
          goto LABEL_62;
        }
      }
      else
      {
        UnattendLogW(0, L"Write settings to handle");
        v6 = SettingXmlParser::Init((SettingXmlParser *)v40, a2);
        if ( v6 )
        {
          v30 = 8915;
          goto LABEL_54;
        }
      }
      v6 = SettingXmlParser::CopySettings((SettingXmlParser *)v40, (struct RecoverySettingInfo *)v5);
      if ( v6 )
      {
        v30 = 8917;
        v26 = L"Failed to copy recovery settings to parser";
      }
      else
      {
        v6 = SettingXmlParser::Update(v40);
        if ( !v6 )
          goto LABEL_63;
        v30 = 8918;
        v26 = L"Failed to update settings to file";
      }
      goto LABEL_61;
    }
LABEL_24:
    v13 = (*(__int64 (__fastcall **)(__int64, void **, unsigned __int16 **))(*(_QWORD *)v11 + 128LL))(v11, &Block, &v34);
    if ( v13 < 0 )
    {
      UnattendLogW(1, L"Failed to get wifi setting. Error: 0x%x", (unsigned int)v13);
      goto LABEL_17;
    }
    v5[307] |= 1u;
    UnattendLogW(0, L"Get wifi setting: SSID: %s", Block);
    v14 = 302;
    if ( Block
      && *(_WORD *)Block
      && (v15 = StringCchCopyW((unsigned __int16 *)v5, 0x12Eu, (const unsigned __int16 *)Block), v15 < 0) )
    {
      v29 = 8831;
      v16 = L"failed to copy ssid";
    }
    else
    {
      if ( !v34 )
        goto LABEL_20;
      if ( !*v34 )
        goto LABEL_20;
      v15 = StringCchCopyW((unsigned __int16 *)v5 + 302, v14, v34);
      if ( v15 >= 0 )
        goto LABEL_20;
      v29 = 8836;
      v16 = L"failed to copy password";
    }
    UnattendLogW(
      2,
      L"WinReDumpSettings %s (0x%x) in file %S line %d",
      v16,
      (unsigned int)v15,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v29);
LABEL_31:
    v6 = (unsigned __int16)v15;
    goto LABEL_62;
  }
  v37[0] = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, char *, _BYTE *))(*(_QWORD *)v11 + 136LL))(v11, &v36, v37);
  if ( v13 >= 0 )
  {
    if ( !v36 && !v37[0] )
      goto LABEL_20;
    goto LABEL_24;
  }
LABEL_16:
  UnattendLogW(1, L"Failed to query wifi setting. Error: 0x%x", (unsigned int)v13);
LABEL_17:
  v6 = (unsigned __int16)v13;
LABEL_62:
  v2 = 0;
LABEL_63:
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 168LL))(v11);
LABEL_65:
  if ( Block )
    operator delete(Block);
  if ( v34 )
    operator delete(v34);
  if ( v5 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v5);
  }
  UnattendLogW(0, L"Exit WinReDumpSettings return value: %d, last error: 0x%x", v2, v6);
  UnattendFinalizeLog();
  SetLastError(v6);
  SettingXmlParser::~SettingXmlParser((SettingXmlParser *)v40);
  return v2;
}

```

## disassembly

```asm
0x180021e90  mov     [rsp-8+arg_10], rbx
0x180021e95  push    rbp
0x180021e96  push    rsi
0x180021e97  push    rdi
0x180021e98  push    r12
0x180021e9a  push    r13
0x180021e9c  push    r14
0x180021e9e  push    r15
0x180021ea0  lea     rbp, [rsp-27h]
0x180021ea5  sub     rsp, 0D0h
0x180021eac  mov     rax, cs:__security_cookie
0x180021eb3  xor     rax, rsp
0x180021eb6  mov     [rbp+57h+var_40], rax
0x180021eba  xor     edi, edi
0x180021ebc  mov     [rbp+57h+var_C0], rcx
0x180021ec0  xorps   xmm0, xmm0
0x180021ec3  mov     [rbp+57h+var_D0], edi
0x180021ec6  lea     rax, ??_7ReAgentLogcallback@@6B@; const ReAgentLogcallback::`vftable'
0x180021ecd  mov     [rbp+57h+var_C8], rdi
0x180021ed1  mov     [rbp+57h+var_A0], rax
0x180021ed5  mov     rbx, rcx
0x180021ed8  lea     rax, ??_7SettingXmlParser@@6B@; const SettingXmlParser::`vftable'
0x180021edf  mov     [rbp+57h+var_88], rdi
0x180021ee3  xorps   xmm1, xmm1
0x180021ee6  mov     [rbp+57h+var_90], rax
0x180021eea  xor     ecx, ecx
0x180021eec  mov     [rbp+57h+var_80], rdi
0x180021ef0  mov     r13, rdx
0x180021ef3  mov     [rbp+57h+var_78], edi
0x180021ef6  movdqa  [rbp+57h+var_70], xmm0
0x180021efb  movdqa  [rbp+57h+var_60], xmm1
0x180021f00  movdqa  [rbp+57h+var_50], xmm0
0x180021f05  mov     [rbp+57h+var_A7], dil
0x180021f09  mov     [rbp+57h+var_A6], dil
0x180021f0d  mov     [rbp+57h+var_A8], dil
0x180021f11  mov     [rbp+57h+var_A4], edi
0x180021f14  mov     [rbp+57h+Block], rdi
0x180021f18  mov     [rbp+57h+var_B0], rdi
0x180021f1c  call    UnattendInitializeLogEx2
0x180021f21  lea     rdx, aEnterWinredump; "Enter WinReDumpSettings"
0x180021f28  xor     ecx, ecx
0x180021f2a  call    UnattendLogW
0x180021f2f  mov     r8, rbx
0x180021f32  lea     rdx, aParametersXmlF; "Parameters: xml file: %s"
0x180021f39  xor     ecx, ecx
0x180021f3b  call    UnattendLogW
0x180021f40  test    rbx, rbx
0x180021f43  jnz     short loc_180021F6C
0x180021f45  lea     rax, [r13+1]
0x180021f49  test    rax, 0FFFFFFFFFFFFFFFEh
0x180021f4f  jnz     short loc_180021F71
0x180021f51  xor     esi, esi
0x180021f53  lea     rdx, aInvalidParamet_6; "Invalid parameter"
0x180021f5a  lea     ecx, [rdi+1]
0x180021f5d  lea     ebx, [rdi+57h]
0x180021f60  call    UnattendLogW
0x180021f65  mov     edi, esi
0x180021f67  jmp     loc_180022462
0x180021f6c  test    r13, r13
0x180021f6f  jz      short loc_180021F85
0x180021f71  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180021f75  jz      short loc_180021F85
0x180021f77  lea     rdx, aWillDumpSettin; "Will dump setting to handle"
0x180021f7e  xor     ecx, ecx
0x180021f80  call    UnattendLogW
0x180021f85  call    cs:__imp_GetProcessHeap
0x180021f8b  mov     ebx, 8
0x180021f90  mov     r8d, 4D0h; dwBytes
0x180021f96  mov     rcx, rax; hHeap
0x180021f99  mov     edx, ebx; dwFlags
0x180021f9b  call    cs:__imp_HeapAlloc
0x180021fa1  mov     rsi, rax
0x180021fa4  test    rax, rax
0x180021fa7  jnz     short loc_180021FDB
0x180021fa9  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180021fb0  mov     [rsp+100h+var_D8], 223Eh
0x180021fb8  mov     r9d, ebx
0x180021fbb  mov     [rsp+100h+var_E0], rax
0x180021fc0  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x180021fc7  lea     rdx, aWinredumpsetti_0; "WinReDumpSettings %s (0x%x) in file %S "...
0x180021fce  lea     ecx, [rbx-6]
0x180021fd1  call    UnattendLogW
0x180021fd6  jmp     loc_180022462
0x180021fdb  lea     rcx, [rbp+57h+var_C8]; this
0x180021fdf  mov     [rax+4CCh], edi
0x180021fe5  call    ?CreateSrSettings@SrSettings@@YAJPEAPEAUISrSettings@1@@Z; SrSettings::CreateSrSettings(SrSettings::ISrSettings * *)
0x180021fea  mov     r14, [rbp+57h+var_C8]
0x180021fee  mov     r15d, eax
0x180021ff1  test    eax, eax
0x180021ff3  jns     short loc_180022012
0x180021ff5  lea     rdx, aFailedToCreate_9; "Failed to create settings object. Error"...
0x180021ffc  mov     r8d, r15d
0x180021fff  mov     ecx, 1
0x180022004  call    UnattendLogW
0x180022009  movzx   ebx, r15w
0x18002200d  jmp     loc_18002244B
0x180022012  mov     rax, [r14]
0x180022015  lea     rdx, [rbp+57h+var_A0]
0x180022019  xor     r9d, r9d
0x18002201c  xor     r8d, r8d
0x18002201f  mov     rcx, r14
0x180022022  mov     rax, [rax+8]
0x180022026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002202b  mov     r15d, eax
0x18002202e  test    eax, eax
0x180022030  jns     short loc_18002203B
0x180022032  lea     rdx, aFailedToInitia; "Failed to initialize settings object. E"...
0x180022039  jmp     short loc_180021FFC
0x18002203b  mov     [rbp+57h+var_A7], dil
0x18002203f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetImpl(void)'::`2'::impl
0x180022046  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::__private_IsEnabled(void)
0x18002204b  lea     rdx, [rbp+57h+var_A7]
0x18002204f  mov     edi, 1
0x180022054  mov     rcx, r14
0x180022057  test    al, al
0x180022059  jz      short loc_1800220CD
0x18002205b  mov     [rbp+57h+var_A6], 0
0x18002205f  lea     r8, [rbp+57h+var_A6]
0x180022063  mov     rax, [r14]
0x180022066  mov     rax, [rax+88h]
0x18002206d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022072  mov     r15d, eax
0x180022075  test    eax, eax
0x180022077  jns     short loc_180022093
0x180022079  lea     rdx, aFailedToQueryW_1; "Failed to query wifi setting. Error: 0x"...
0x180022080  mov     r8d, r15d
0x180022083  mov     ecx, edi
0x180022085  call    UnattendLogW
0x18002208a  movzx   ebx, r15w
0x18002208e  jmp     loc_180022448
0x180022093  cmp     [rbp+57h+var_A7], 0
0x180022097  jnz     short loc_1800220EC
0x180022099  cmp     [rbp+57h+var_A6], 0
0x18002209d  jnz     short loc_1800220EC
0x18002209f  mov     rax, [r14]
0x1800220a2  lea     r8, [rbp+57h+var_A8]
0x1800220a6  lea     rdx, aCloudremediati_0; "CloudRemediation"
0x1800220ad  mov     rcx, r14
0x1800220b0  mov     rax, [rax+48h]
0x1800220b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b9  mov     r15d, eax
0x1800220bc  test    eax, eax
0x1800220be  jns     loc_1800221D6
0x1800220c4  lea     rdx, aFailedToGetClo; "Failed to get cloud remediation setting"...
0x1800220cb  jmp     short loc_180022080
0x1800220cd  mov     rax, [r14]
0x1800220d0  xor     r8d, r8d
0x1800220d3  mov     rax, [rax+88h]
0x1800220da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220df  mov     r15d, eax
0x1800220e2  test    eax, eax
0x1800220e4  js      short loc_180022079
0x1800220e6  cmp     [rbp+57h+var_A7], 0
0x1800220ea  jz      short loc_18002209F
0x1800220ec  mov     rax, [r14]
0x1800220ef  lea     r8, [rbp+57h+var_B0]
0x1800220f3  lea     rdx, [rbp+57h+Block]
0x1800220f7  mov     rcx, r14
0x1800220fa  mov     rax, [rax+80h]
0x180022101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022106  mov     r15d, eax
0x180022109  test    eax, eax
0x18002210b  jns     short loc_180022119
0x18002210d  lea     rdx, aFailedToGetWif; "Failed to get wifi setting. Error: 0x%x"
0x180022114  jmp     loc_180022080
0x180022119  or      [rsi+4CCh], edi
0x18002211f  lea     rdx, aGetWifiSetting; "Get wifi setting: SSID: %s"
0x180022126  mov     r8, [rbp+57h+Block]
0x18002212a  xor     ecx, ecx
0x18002212c  call    UnattendLogW
0x180022131  mov     r8, [rbp+57h+Block]; unsigned __int16 *
0x180022135  mov     r11d, 12Eh
0x18002213b  test    r8, r8
0x18002213e  jz      short loc_180022192
0x180022140  xor     eax, eax
0x180022142  cmp     ax, [r8]
0x180022146  jz      short loc_180022192
0x180022148  mov     edx, r11d; unsigned __int64
0x18002214b  mov     rcx, rsi; unsigned __int16 *
0x18002214e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022153  mov     r12d, eax
0x180022156  test    eax, eax
0x180022158  jns     short loc_180022192
0x18002215a  mov     [rsp+100h+var_D8], 227Fh
0x180022162  lea     r8, aFailedToCopySs; "failed to copy ssid"
0x180022169  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180022170  mov     r9d, r12d
0x180022173  lea     rdx, aWinredumpsetti_0; "WinReDumpSettings %s (0x%x) in file %S "...
0x18002217a  mov     [rsp+100h+var_E0], rax
0x18002217f  mov     ecx, 2
0x180022184  call    UnattendLogW
0x180022189  movzx   ebx, r12w
0x18002218d  jmp     loc_180022448
0x180022192  mov     r8, [rbp+57h+var_B0]; unsigned __int16 *
0x180022196  test    r8, r8
0x180022199  jz      loc_18002209F
0x18002219f  xor     eax, eax
0x1800221a1  cmp     ax, [r8]
0x1800221a5  jz      loc_18002209F
0x1800221ab  lea     rcx, [rsi+25Ch]; unsigned __int16 *
0x1800221b2  mov     rdx, r11; unsigned __int64
0x1800221b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800221ba  mov     r12d, eax
0x1800221bd  test    eax, eax
0x1800221bf  jns     loc_18002209F
0x1800221c5  mov     [rsp+100h+var_D8], 2284h
0x1800221cd  lea     r8, aFailedToCopyPa_0; "failed to copy password"
0x1800221d4  jmp     short loc_180022169
0x1800221d6  movzx   eax, [rbp+57h+var_A8]
0x1800221da  lea     r12, aOn_0; "on"
0x1800221e1  or      dword ptr [rsi+4CCh], 20h
0x1800221e8  lea     rdx, aGetCloudRemedi; "Get cloud remediation setting: %s"
0x1800221ef  mov     [rsi+4C4h], eax
0x1800221f5  mov     r8, r12
0x1800221f8  cmp     [rbp+57h+var_A8], 0
0x1800221fc  lea     rax, aOff_0; "off"
0x180022203  cmovz   r8, rax
0x180022207  xor     ecx, ecx
0x180022209  call    UnattendLogW
0x18002220e  mov     rax, [r14]
0x180022211  lea     r8, [rbp+57h+var_A8]
0x180022215  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18002221c  mov     rcx, r14
0x18002221f  mov     rax, [rax+48h]
0x180022223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022228  mov     r15d, eax
0x18002222b  test    eax, eax
0x18002222d  jns     short loc_18002223B
0x18002222f  lea     rdx, aFailedToGetAut; "Failed to get auto remediation setting."...
0x180022236  jmp     loc_180022080
0x18002223b  movzx   eax, [rbp+57h+var_A8]
0x18002223f  lea     rdx, aGetAutoRemedia; "Get auto remediation setting: %s"
0x180022246  mov     [rsi+4C0h], eax
0x18002224c  mov     r15d, 2
0x180022252  or      [rsi+4CCh], r15d
0x180022259  lea     rax, aOff_0; "off"
0x180022260  cmp     [rbp+57h+var_A8], 0
0x180022264  mov     r8, r12
0x180022267  cmovz   r8, rax
0x18002226b  xor     ecx, ecx
0x18002226d  call    UnattendLogW
0x180022272  mov     rax, [r14]
0x180022275  lea     r8, [rbp+57h+var_A8]
0x180022279  lea     rdx, aHeadlessmode; "HeadlessMode"
0x180022280  mov     rcx, r14
0x180022283  mov     rax, [rax+48h]
0x180022287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002228c  mov     r12d, eax
0x18002228f  test    eax, eax
0x180022291  jns     short loc_1800222A9
0x180022293  lea     rdx, aFailedToGetHea; "Failed to get headless setting. Error: "...
0x18002229a  mov     r8d, r12d
0x18002229d  mov     ecx, edi
0x18002229f  call    UnattendLogW
0x1800222a4  jmp     loc_180022189
0x1800222a9  movzx   eax, [rbp+57h+var_A8]
0x1800222ad  lea     r8, aOn_0; "on"
0x1800222b4  or      dword ptr [rsi+4CCh], 4
0x1800222bb  lea     rdx, aGetHeadlessSet; "Get headless setting: %s"
0x1800222c2  mov     [rsi+4C8h], eax
0x1800222c8  lea     rax, aOff_0; "off"
0x1800222cf  cmp     [rbp+57h+var_A8], 0
0x1800222d3  cmovz   r8, rax
0x1800222d7  xor     ecx, ecx
0x1800222d9  call    UnattendLogW
0x1800222de  mov     rax, [r14]
0x1800222e1  lea     r8, [rbp+57h+var_A4]
0x1800222e5  lea     rdx, aTotalwaittime_0; "TotalWaitTime"
0x1800222ec  mov     rcx, r14
0x1800222ef  mov     rax, [rax+18h]
0x1800222f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222f8  mov     r12d, eax
0x1800222fb  test    eax, eax
0x1800222fd  jns     short loc_180022308
0x1800222ff  lea     rdx, aFailedToGetTot; "Failed to get total wait time setting. "...
0x180022306  jmp     short loc_18002229A
0x180022308  mov     eax, [rbp+57h+var_A4]
0x18002230b  lea     rdx, aGetTotalWaitTi; "Get total wait time setting: %d"
0x180022312  or      [rsi+4CCh], ebx
0x180022318  xor     ecx, ecx
0x18002231a  mov     [rsi+4B8h], eax
0x180022320  mov     r8d, [rbp+57h+var_A4]
0x180022324  call    UnattendLogW
0x180022329  mov     rax, [r14]
0x18002232c  lea     r8, [rbp+57h+var_A4]
0x180022330  lea     rdx, aWaitinterval; "WaitInterval"
0x180022337  mov     rcx, r14
0x18002233a  mov     rax, [rax+18h]
0x18002233e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022343  mov     ebx, eax
0x180022345  test    eax, eax
0x180022347  jns     short loc_180022362
0x180022349  mov     r8d, eax
0x18002234c  lea     rdx, aFailedToGetWai; "Failed to get wait interval setting. Er"...
0x180022353  mov     ecx, edi
0x180022355  call    UnattendLogW
0x18002235a  movzx   ebx, bx
0x18002235d  jmp     loc_180022448
0x180022362  mov     eax, [rbp+57h+var_A4]
0x180022365  lea     rdx, aGetWaitInterva; "Get wait interval setting: %d"
  ... truncated ...
```
