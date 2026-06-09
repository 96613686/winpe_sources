# CModelDownloadComponent::DownloadModelsFromServer(void)

- ea: `0x14000d890`
- end: `0x14000dd45`
- name: `?DownloadModelsFromServer@CModelDownloadComponent@@QEAAJXZ`
- size: `1205`
- prototype: `__int64 __fastcall(WCHAR *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140009698`

## callees

- `0x140002600`
- `0x140004f38`
- `0x14000985c`
- `0x14000af50`
- `0x14000cd18`
- `0x14000d890`
- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`
- `0x14000f4d4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000d9fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000d9fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d90d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d90d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x14000d9b1`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryValueW` at `0x14000d9b1`

## string_xrefs

- `0x14000d94f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(273)`
- `0x14000d918`: `CModelDownloadComponent::DownloadModelsFromServer`
- `0x14000dbae`: `CModelDownloadComponent::DownloadModelsFromServer`
- `0x14000dc54`: `CModelDownloadComponent::DownloadModelsFromServer`
- `0x14000dcfa`: `CModelDownloadComponent::DownloadModelsFromServer`
- `0x14000d9d1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(274)`
- `0x14000da6b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(280)`
- `0x14000daa2`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(285)`
- `0x14000dad9`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(290)`
- `0x14000db08`: `ModelUpdateNotAllowed`
- `0x14000dba3`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(298)`
- `0x14000dc49`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(299)`
- `0x14000dcef`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(300)`
- `0x14000db34`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1442)`
- `0x14000db88`: `CModelDownloadComponent::CleanupOldSRModels`
- `0x14000db62`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1446)`
- `0x14000db7e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1449)`
- `0x14000dbda`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1472)`
- `0x14000dc2e`: `CModelDownloadComponent::CleanupOldTTSModels`
- `0x14000dc08`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1476)`
- `0x14000dc24`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1479)`
- `0x14000dc80`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1502)`
- `0x14000dcd4`: `CModelDownloadComponent::CleanupOldVAModels`
- `0x14000dcae`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1506)`
- `0x14000dcca`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1509)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::DownloadModelsFromServer(WCHAR *this)
{
  int ValueW; // eax
  bool v3; // si
  bool v4; // sf
  signed int PersistedRegistryValueW; // eax
  bool v6; // sf
  bool v7; // di
  int v8; // eax
  int v9; // eax
  int v10; // eax
  SPTelemetry::ModelUpdate *v11; // rcx
  const char *v12; // rdx
  int ModelFilesRootPathExists; // esi
  const wchar_t *v14; // rax
  int v15; // esi
  const wchar_t *v16; // rax
  int v17; // esi
  const wchar_t *v18; // rax
  unsigned __int64 pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v23[264]; // [rsp+60h] [rbp-A0h] BYREF

  LODWORD(pvData) = 0;
  pcbData[0] = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Speech_OneCore\\Preferences",
             L"ModelDownloadAllowed",
             0x18u,
             0,
             &pvData,
             pcbData);
  v3 = (_DWORD)pvData == 1;
  v4 = ValueW < 0;
  if ( ValueW )
  {
    if ( ValueW > 0 )
    {
      ValueW = (unsigned __int16)ValueW | 0x80070000;
      v4 = ValueW < 0;
    }
    if ( v4 )
      DoTraceMessage(
        2,
        "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::DownloadModelsFromServer",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(273)",
        ValueW);
  }
  pvData = 0;
  PersistedRegistryValueW = GetPersistedRegistryValueW(
                              L"OCUAP_Speech_CloudSettings_Storage",
                              L"SOFTWARE\\Microsoft\\Speech_OneCore\\CloudSettings",
                              L"LastCheck",
                              72,
                              0,
                              &pvData,
                              8,
                              0);
  v6 = PersistedRegistryValueW < 0;
  if ( !PersistedRegistryValueW )
    goto LABEL_11;
  if ( PersistedRegistryValueW > 0 )
  {
    PersistedRegistryValueW = (unsigned __int16)PersistedRegistryValueW | 0x80070000;
    v6 = PersistedRegistryValueW < 0;
  }
  if ( v6 )
  {
    v7 = 0;
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(274)",
      PersistedRegistryValueW);
  }
  else
  {
LABEL_11:
    *(_QWORD *)pcbData = 0;
    GetSystemTimeAsFileTime((LPFILETIME)pcbData);
    v22 = *(_QWORD *)pcbData;
    v7 = pvData > *(_QWORD *)pcbData || *(_QWORD *)pcbData - pvData < 0x1600A3910000LL;
  }
  if ( v3 && v7 )
  {
    if ( *((_DWORD *)this + 8) == 1 )
    {
      v8 = CModelDownloadComponent::DownloadSRModelsFromServer((CModelDownloadComponent *)this);
      if ( v8 < 0 )
        DoTraceMessage(
          2,
          "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::DownloadModelsFromServer",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(280)",
          v8);
    }
    if ( *((_DWORD *)this + 10) == 1 )
    {
      v9 = CModelDownloadComponent::DownloadTTSModelsFromServer((CModelDownloadComponent *)this);
      if ( v9 < 0 )
        DoTraceMessage(
          2,
          "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::DownloadModelsFromServer",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(285)",
          v9);
    }
    if ( *((_DWORD *)this + 9) == 1 )
    {
      v10 = CModelDownloadComponent::DownloadVAModelsFromServer((CModelDownloadComponent *)this);
      if ( v10 < 0 )
        DoTraceMessage(
          2,
          "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::DownloadModelsFromServer",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(290)",
          v10);
    }
  }
  else
  {
    v11 = (SPTelemetry::ModelUpdate *)*((_QWORD *)this + 3);
    if ( v11 )
    {
      v12 = "ModelUpdateNotAllowed";
      if ( !v7 )
        v12 = "NoSpeechUsage";
      SPTelemetry::ModelUpdate::Abort(v11, v12);
    }
  }
  ModelFilesRootPathExists = CModelDownloadComponent::GetModelFilesRootPathExists(this + 582);
  if ( ModelFilesRootPathExists >= 0 )
  {
    if ( (unsigned int)swprintf_s<261>(v23, L"%s\\%s", this + 582, L"SR") == -1 )
    {
      ModelFilesRootPathExists = -2147418113;
      v14 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1446)";
    }
    else
    {
      ModelFilesRootPathExists = CModelDownloadComponent::CleanupOldModelsFromRoot((CModelDownloadComponent *)this, v23);
      if ( ModelFilesRootPathExists >= 0 )
        goto LABEL_37;
      v14 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1449)";
    }
  }
  else
  {
    v14 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1442)";
  }
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"CModelDownloadComponent::CleanupOldSRModels",
    v14,
    ModelFilesRootPathExists);
  DoTraceMessage(
    2,
    "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"CModelDownloadComponent::DownloadModelsFromServer",
    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(298)",
    ModelFilesRootPathExists);
LABEL_37:
  v15 = CModelDownloadComponent::GetModelFilesRootPathExists(this + 582);
  if ( v15 >= 0 )
  {
    if ( (unsigned int)swprintf_s<261>(v23, L"%s\\%s", this + 582, L"TTS") == -1 )
    {
      v15 = -2147418113;
      v16 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1476)";
    }
    else
    {
      v15 = CModelDownloadComponent::CleanupOldModelsFromRoot((CModelDownloadComponent *)this, v23);
      if ( v15 >= 0 )
        goto LABEL_44;
      v16 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1479)";
    }
  }
  else
  {
    v16 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1472)";
  }
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"CModelDownloadComponent::CleanupOldTTSModels",
    v16,
    v15);
  DoTraceMessage(
    2,
    "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"CModelDownloadComponent::DownloadModelsFromServer",
    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(299)",
    v15);
LABEL_44:
  v17 = CModelDownloadComponent::GetModelFilesRootPathExists(this + 582);
  if ( v17 < 0 )
  {
    v18 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1502)";
LABEL_50:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanupOldVAModels",
      v18,
      v17);
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(300)",
      v17);
    return 0;
  }
  if ( (unsigned int)swprintf_s<261>(v23, L"%s\\%s", this + 582, L"VA") == -1 )
  {
    v17 = -2147418113;
    v18 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1506)";
    goto LABEL_50;
  }
  v17 = CModelDownloadComponent::CleanupOldModelsFromRoot((CModelDownloadComponent *)this, v23);
  if ( v17 < 0 )
  {
    v18 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1509)";
    goto LABEL_50;
  }
  return 0;
}

```

## disassembly

```asm
0x14000d890  mov     [rsp-8+arg_8], rbx
0x14000d895  mov     [rsp-8+arg_10], rsi
0x14000d89a  push    rbp
0x14000d89b  push    rdi
0x14000d89c  push    r12
0x14000d89e  push    r13
0x14000d8a0  push    r14
0x14000d8a2  lea     rbp, [rsp-180h]
0x14000d8aa  sub     rsp, 280h
0x14000d8b1  mov     rax, cs:__security_cookie
0x14000d8b8  xor     rax, rsp
0x14000d8bb  mov     [rbp+1A0h+var_30], rax
0x14000d8c2  mov     rbx, rcx
0x14000d8c5  lea     rax, [rsp+2A0h+var_258]
0x14000d8ca  mov     dword ptr [rsp+2A0h+var_260], 0
0x14000d8d2  mov     [rsp+2A0h+pcbData], rax; pcbData
0x14000d8d7  lea     r8, Value; "ModelDownloadAllowed"
0x14000d8de  lea     rax, [rsp+2A0h+var_260]
0x14000d8e3  mov     [rsp+2A0h+var_258], 4
0x14000d8eb  mov     [rsp+2A0h+pvData], rax; pvData
0x14000d8f0  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Speech_OneCore\\Pr"...
0x14000d8f7  mov     r9d, 18h; dwFlags
0x14000d8fd  mov     [rsp+2A0h+pdwType], 0; pdwType
0x14000d906  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000d90d  call    cs:__imp_RegGetValueW
0x14000d913  cmp     dword ptr [rsp+2A0h+var_260], 1
0x14000d918  lea     r14, aCmodeldownload_5; "CModelDownloadComponent::DownloadModels"...
0x14000d91f  lea     r12, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000d926  mov     edi, 80070000h
0x14000d92b  setz    sil
0x14000d92f  mov     r13d, 2
0x14000d935  test    eax, eax
0x14000d937  jz      short loc_14000D969
0x14000d939  jle     short loc_14000D942
0x14000d93b  movzx   eax, ax
0x14000d93e  or      eax, edi
0x14000d940  test    eax, eax
0x14000d942  jns     short loc_14000D969
0x14000d944  mov     dword ptr [rsp+2A0h+pvData], eax
0x14000d948  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000d94f  lea     rax, aOnecoreuapEndu_133; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d956  mov     r9, r14
0x14000d959  mov     r8, r12
0x14000d95c  mov     [rsp+2A0h+pdwType], rax
0x14000d961  mov     ecx, r13d; int
0x14000d964  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d969  mov     [rsp+2A0h+var_268], 0
0x14000d972  lea     rax, [rsp+2A0h+var_260]
0x14000d977  mov     dword ptr [rsp+2A0h+pcbData], 8
0x14000d97f  lea     r8, aLastcheck; "LastCheck"
0x14000d986  mov     [rsp+2A0h+pvData], rax
0x14000d98b  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Speech_OneCore\\Cl"...
0x14000d992  mov     r9d, 48h ; 'H'
0x14000d998  mov     [rsp+2A0h+pdwType], 0
0x14000d9a1  lea     rcx, aOcuapSpeechClo; "OCUAP_Speech_CloudSettings_Storage"
0x14000d9a8  mov     [rsp+2A0h+var_260], 0
0x14000d9b1  call    cs:__imp_GetPersistedRegistryValueW
0x14000d9b7  test    eax, eax
0x14000d9b9  jz      short loc_14000D9F0
0x14000d9bb  jle     short loc_14000D9C4
0x14000d9bd  movzx   eax, ax
0x14000d9c0  or      eax, edi
0x14000d9c2  test    eax, eax
0x14000d9c4  jns     short loc_14000D9F0
0x14000d9c6  mov     dword ptr [rsp+2A0h+pvData], eax
0x14000d9ca  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000d9d1  lea     rax, aOnecoreuapEndu_32; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d9d8  xor     dil, dil
0x14000d9db  mov     r9, r14
0x14000d9de  mov     [rsp+2A0h+pdwType], rax
0x14000d9e3  mov     r8, r12
0x14000d9e6  mov     ecx, r13d; int
0x14000d9e9  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d9ee  jmp     short loc_14000DA3C
0x14000d9f0  lea     rcx, [rsp+2A0h+var_258]; lpSystemTimeAsFileTime
0x14000d9f5  mov     qword ptr [rsp+2A0h+var_258], 0
0x14000d9fe  call    cs:__imp_GetSystemTimeAsFileTime
0x14000da04  mov     eax, [rsp+2A0h+var_258+4]
0x14000da08  mov     dword ptr [rsp+2A0h+var_250+4], eax
0x14000da0c  mov     eax, [rsp+2A0h+var_258]
0x14000da10  mov     dword ptr [rsp+2A0h+var_250], eax
0x14000da14  mov     rax, [rsp+2A0h+var_250]
0x14000da19  cmp     [rsp+2A0h+var_260], rax
0x14000da1e  ja      short loc_14000DA39
0x14000da20  sub     rax, [rsp+2A0h+var_260]
0x14000da25  mov     rcx, 1600A3910000h
0x14000da2f  cmp     rax, rcx
0x14000da32  jb      short loc_14000DA39
0x14000da34  xor     dil, dil
0x14000da37  jmp     short loc_14000DA3C
0x14000da39  mov     dil, 1
0x14000da3c  test    sil, sil
0x14000da3f  jz      loc_14000DAF5
0x14000da45  test    dil, dil
0x14000da48  jz      loc_14000DAF5
0x14000da4e  cmp     dword ptr [rbx+20h], 1
0x14000da52  jnz     short loc_14000DA85
0x14000da54  mov     rcx, rbx; this
0x14000da57  call    ?DownloadSRModelsFromServer@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::DownloadSRModelsFromServer(void)
0x14000da5c  test    eax, eax
0x14000da5e  jns     short loc_14000DA85
0x14000da60  mov     dword ptr [rsp+2A0h+pvData], eax
0x14000da64  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000da6b  lea     rax, aOnecoreuapEndu_145; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000da72  mov     r9, r14
0x14000da75  mov     r8, r12
0x14000da78  mov     [rsp+2A0h+pdwType], rax
0x14000da7d  mov     ecx, r13d; int
0x14000da80  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000da85  cmp     dword ptr [rbx+28h], 1
0x14000da89  jnz     short loc_14000DABC
0x14000da8b  mov     rcx, rbx; this
0x14000da8e  call    ?DownloadTTSModelsFromServer@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::DownloadTTSModelsFromServer(void)
0x14000da93  test    eax, eax
0x14000da95  jns     short loc_14000DABC
0x14000da97  mov     dword ptr [rsp+2A0h+pvData], eax
0x14000da9b  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000daa2  lea     rax, aOnecoreuapEndu_4; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000daa9  mov     r9, r14
0x14000daac  mov     r8, r12
0x14000daaf  mov     [rsp+2A0h+pdwType], rax
0x14000dab4  mov     ecx, r13d; int
0x14000dab7  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dabc  cmp     dword ptr [rbx+24h], 1
0x14000dac0  jnz     short loc_14000DB18
0x14000dac2  mov     rcx, rbx; this
0x14000dac5  call    ?DownloadVAModelsFromServer@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::DownloadVAModelsFromServer(void)
0x14000daca  test    eax, eax
0x14000dacc  jns     short loc_14000DB18
0x14000dace  mov     dword ptr [rsp+2A0h+pvData], eax
0x14000dad2  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000dad9  lea     rax, aOnecoreuapEndu_6; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dae0  mov     r9, r14
0x14000dae3  mov     r8, r12
0x14000dae6  mov     [rsp+2A0h+pdwType], rax
0x14000daeb  mov     ecx, r13d; int
0x14000daee  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000daf3  jmp     short loc_14000DB18
0x14000daf5  mov     rcx, [rbx+18h]; this
0x14000daf9  test    rcx, rcx
0x14000dafc  jz      short loc_14000DB18
0x14000dafe  test    dil, dil
0x14000db01  lea     rax, aNospeechusage; "NoSpeechUsage"
0x14000db08  lea     rdx, aModelupdatenot; "ModelUpdateNotAllowed"
0x14000db0f  cmovz   rdx, rax; char *
0x14000db13  call    ?Abort@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z; SPTelemetry::ModelUpdate::Abort(char const *)
0x14000db18  lea     r14, [rbx+48Ch]
0x14000db1f  mov     rcx, r14; lpDst
0x14000db22  call    ?GetModelFilesRootPathExists@CModelDownloadComponent@@CAJPEAG@Z; CModelDownloadComponent::GetModelFilesRootPathExists(ushort *)
0x14000db27  lea     rdi, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000db2e  mov     esi, eax
0x14000db30  test    eax, eax
0x14000db32  jns     short loc_14000DB3D
0x14000db34  lea     rax, aOnecoreuapEndu_38; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000db3b  jmp     short loc_14000DB85
0x14000db3d  lea     r9, aSr_0; "SR"
0x14000db44  mov     r8, r14
0x14000db47  lea     rdx, aSS; "%s\\%s"
0x14000db4e  lea     rcx, [rsp+2A0h+var_240]
0x14000db53  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000db58  cmp     eax, 0FFFFFFFFh
0x14000db5b  jnz     short loc_14000DB6B
0x14000db5d  mov     esi, 8000FFFFh
0x14000db62  lea     rax, aOnecoreuapEndu_129; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000db69  jmp     short loc_14000DB85
0x14000db6b  lea     rdx, [rsp+2A0h+var_240]; unsigned __int16 *
0x14000db70  mov     rcx, rbx; this
0x14000db73  call    ?CleanupOldModelsFromRoot@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::CleanupOldModelsFromRoot(ushort const *)
0x14000db78  mov     esi, eax
0x14000db7a  test    eax, eax
0x14000db7c  jns     short loc_14000DBCC
0x14000db7e  lea     rax, aOnecoreuapEndu_150; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000db85  mov     ecx, r13d; int
0x14000db88  lea     r9, aCmodeldownload_6; "CModelDownloadComponent::CleanupOldSRMo"...
0x14000db8f  mov     rdx, rdi; char *
0x14000db92  mov     r8, r12
0x14000db95  mov     dword ptr [rsp+2A0h+pvData], esi
0x14000db99  mov     [rsp+2A0h+pdwType], rax
0x14000db9e  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dba3  lea     rax, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dbaa  mov     dword ptr [rsp+2A0h+pvData], esi
0x14000dbae  lea     r9, aCmodeldownload_5; "CModelDownloadComponent::DownloadModels"...
0x14000dbb5  mov     [rsp+2A0h+pdwType], rax
0x14000dbba  mov     r8, r12
0x14000dbbd  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000dbc4  mov     ecx, r13d; int
0x14000dbc7  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dbcc  mov     rcx, r14; lpDst
0x14000dbcf  call    ?GetModelFilesRootPathExists@CModelDownloadComponent@@CAJPEAG@Z; CModelDownloadComponent::GetModelFilesRootPathExists(ushort *)
0x14000dbd4  mov     esi, eax
0x14000dbd6  test    eax, eax
0x14000dbd8  jns     short loc_14000DBE3
0x14000dbda  lea     rax, aOnecoreuapEndu_101; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dbe1  jmp     short loc_14000DC2B
0x14000dbe3  lea     r9, aTts; "TTS"
0x14000dbea  mov     r8, r14
0x14000dbed  lea     rdx, aSS; "%s\\%s"
0x14000dbf4  lea     rcx, [rsp+2A0h+var_240]
0x14000dbf9  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000dbfe  cmp     eax, 0FFFFFFFFh
0x14000dc01  jnz     short loc_14000DC11
0x14000dc03  mov     esi, 8000FFFFh
0x14000dc08  lea     rax, aOnecoreuapEndu_68; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dc0f  jmp     short loc_14000DC2B
0x14000dc11  lea     rdx, [rsp+2A0h+var_240]; unsigned __int16 *
0x14000dc16  mov     rcx, rbx; this
0x14000dc19  call    ?CleanupOldModelsFromRoot@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::CleanupOldModelsFromRoot(ushort const *)
0x14000dc1e  mov     esi, eax
0x14000dc20  test    eax, eax
0x14000dc22  jns     short loc_14000DC72
0x14000dc24  lea     rax, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dc2b  mov     ecx, r13d; int
0x14000dc2e  lea     r9, aCmodeldownload; "CModelDownloadComponent::CleanupOldTTSM"...
0x14000dc35  mov     rdx, rdi; char *
0x14000dc38  mov     r8, r12
0x14000dc3b  mov     dword ptr [rsp+2A0h+pvData], esi
0x14000dc3f  mov     [rsp+2A0h+pdwType], rax
0x14000dc44  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dc49  lea     rax, aOnecoreuapEndu_82; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dc50  mov     dword ptr [rsp+2A0h+pvData], esi
0x14000dc54  lea     r9, aCmodeldownload_5; "CModelDownloadComponent::DownloadModels"...
0x14000dc5b  mov     [rsp+2A0h+pdwType], rax
0x14000dc60  mov     r8, r12
0x14000dc63  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000dc6a  mov     ecx, r13d; int
0x14000dc6d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dc72  mov     rcx, r14; lpDst
0x14000dc75  call    ?GetModelFilesRootPathExists@CModelDownloadComponent@@CAJPEAG@Z; CModelDownloadComponent::GetModelFilesRootPathExists(ushort *)
0x14000dc7a  mov     esi, eax
0x14000dc7c  test    eax, eax
0x14000dc7e  jns     short loc_14000DC89
0x14000dc80  lea     rax, aOnecoreuapEndu_17; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dc87  jmp     short loc_14000DCD1
0x14000dc89  lea     r9, aVa; "VA"
0x14000dc90  mov     r8, r14
0x14000dc93  lea     rdx, aSS; "%s\\%s"
0x14000dc9a  lea     rcx, [rsp+2A0h+var_240]
0x14000dc9f  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000dca4  cmp     eax, 0FFFFFFFFh
0x14000dca7  jnz     short loc_14000DCB7
0x14000dca9  mov     esi, 8000FFFFh
0x14000dcae  lea     rax, aOnecoreuapEndu_113; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dcb5  jmp     short loc_14000DCD1
0x14000dcb7  lea     rdx, [rsp+2A0h+var_240]; unsigned __int16 *
0x14000dcbc  mov     rcx, rbx; this
0x14000dcbf  call    ?CleanupOldModelsFromRoot@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::CleanupOldModelsFromRoot(ushort const *)
0x14000dcc4  mov     esi, eax
0x14000dcc6  test    eax, eax
0x14000dcc8  jns     short loc_14000DD18
0x14000dcca  lea     rax, aOnecoreuapEndu_114; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dcd1  mov     ecx, r13d; int
0x14000dcd4  lea     r9, aCmodeldownload_23; "CModelDownloadComponent::CleanupOldVAMo"...
0x14000dcdb  mov     r8, r12
0x14000dcde  mov     dword ptr [rsp+2A0h+pvData], esi
0x14000dce2  mov     rdx, rdi; char *
0x14000dce5  mov     [rsp+2A0h+pdwType], rax
0x14000dcea  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dcef  lea     rax, aOnecoreuapEndu_147; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dcf6  mov     dword ptr [rsp+2A0h+pvData], esi
0x14000dcfa  lea     r9, aCmodeldownload_5; "CModelDownloadComponent::DownloadModels"...
0x14000dd01  mov     [rsp+2A0h+pdwType], rax
0x14000dd06  mov     r8, r12
0x14000dd09  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000dd10  mov     ecx, r13d; int
0x14000dd13  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dd18  xor     eax, eax
0x14000dd1a  mov     rcx, [rbp+1A0h+var_30]
0x14000dd21  xor     rcx, rsp; StackCookie
0x14000dd24  call    __security_check_cookie
0x14000dd29  lea     r11, [rsp+2A0h+var_20]
0x14000dd31  mov     rbx, [r11+38h]
0x14000dd35  mov     rsi, [r11+40h]
0x14000dd39  mov     rsp, r11
0x14000dd3c  pop     r14
0x14000dd3e  pop     r13
0x14000dd40  pop     r12
0x14000dd42  pop     rdi
0x14000dd43  pop     rbp
0x14000dd44  retn
```
