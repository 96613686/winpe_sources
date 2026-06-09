# ClientBlock::Apply(ARPFrame *)

- ea: `0x180009550`
- end: `0x180009962`
- name: `?Apply@ClientBlock@@QEAAJPEAVARPFrame@@@Z`
- size: `1042`
- prototype: `__int64 __fastcall(ClientBlock *__hidden this, struct ARPFrame *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009970`

## callees

- `0x180007960`
- `0x180008b98`
- `0x180008f58`
- `0x180009550`
- `0x180009a14`
- `0x18000ac0c`
- `0x18000add0`
- `0x18000af30`
- `0x18000bef0`
- `0x18000dd44`
- `0x18000ddb0`
- `0x18000e990`
- `0x18000eac4`
- `0x18000fa5c`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHCORE!SHSetValueW` at `0x18000984b`
- `SHCORE!SHSetValueW` at `0x18000987a`
- `SHCORE!SHSetValueW` at `0x18000984b`
- `SHCORE!SHSetValueW` at `0x18000987a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009686`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009762`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009686`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009762`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800097aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800097aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009930`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009794`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009794`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800098cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800098cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000981c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000981c`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800096a7`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800097dc`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800096a7`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800097dc`

## string_xrefs

- `0x1800097f6`: `ReinstallCommand`
- `0x1800096c0`: `HideIconsCommand`
- `0x1800096cf`: `ShowIconsCommand`
- `0x18000963b`: `%s\InstallInfo`
- `0x180009754`: `Extensions\ContractId\Windows.Search`
- `0x18000978a`: `ForceCacheRefresh`
- `0x1800097a3`: `ForceCacheRefresh`

## pseudocode

```c
__int64 __fastcall ClientBlock::Apply(ClientBlock *this, struct ARPFrame *a2)
{
  HRESULT v3; // edi
  HKEY v4; // r15
  HKEY v5; // rsi
  unsigned int v6; // r12d
  _DWORD *v7; // rbx
  int v8; // ecx
  _QWORD *v9; // rbx
  __int64 v10; // rbx
  HKEY v11; // rcx
  DirectUI::Element *DescendentByName; // rax
  unsigned __int8 Selected; // al
  int v14; // r14d
  const unsigned __int16 *v15; // r8
  const WCHAR *ClientTypeString; // rax
  DirectUI::Element *v17; // rax
  LPVOID v18; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v22; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  struct DirectUI::Value *v25; // [rsp+50h] [rbp-B0h] BYREF
  ARPFrame *v26; // [rsp+58h] [rbp-A8h]
  _QWORD v27[42]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v29[526]; // [rsp+1B2h] [rbp+B2h] BYREF

  v26 = a2;
  v3 = 0;
  v4 = ClientBlock::_OpenClientKey(this, HKEY_LOCAL_MACHINE, 0x2001Fu, 0);
  v5 = ClientBlock::_OpenClientKey(this, HKEY_LOCAL_MACHINE, 0x2001Fu, 1);
  ppv = 0;
  v6 = 2;
  do
  {
    v7 = (_DWORD *)*((_QWORD *)this + 25);
    v8 = *v7;
    if ( v6 >= (*v7 & 0xFFFFFFFu) )
      break;
    v9 = v7 + 2;
    if ( (v8 & 0x10000000) != 0 )
      v9 = (_QWORD *)*v9;
    v10 = v9[v6];
    wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v27,
      "SPADWizardApply");
    v27[0] = &AppWizLoggingTelemetry::SPADWizardApply::`vftable';
    AppWizLoggingTelemetry::SPADWizardApply::StartActivity((AppWizLoggingTelemetry::SPADWizardApply *)v27);
    SubKey = 0;
    memset_0(v29, 0, 0x206u);
    StringCchPrintfW(&SubKey, 0x104u, L"%s\\InstallInfo", *(_QWORD *)v10);
    v22 = 0;
    v11 = v4;
    if ( *(_BYTE *)(v10 + 40) )
      v11 = v5;
    if ( v11 && !RegOpenKeyExW(v11, &SubKey, 0, 0x20019u, &v22) )
    {
      DescendentByName = FindDescendentByName(*(struct DirectUI::Element **)(v10 + 32), L"show");
      Selected = DirectUI::Element::GetSelected(DescendentByName);
      v14 = Selected;
      if ( Selected != *(_BYTE *)(v10 + 41) )
      {
        v15 = L"ShowIconsCommand";
        if ( !Selected )
          v15 = L"HideIconsCommand";
        if ( CLIENTINFO::GetInstallFile((CLIENTINFO *)v10, v22, v15, &SubKey, phkResult, 0) )
          v3 = ARPFrame::LaunchClientCommandAndWait(
                 v26,
                 (v14 ^ 1u) + 99,
                 *(const unsigned __int16 **)(v10 + 8),
                 &SubKey);
        v25 = 0;
        ClientTypeString = ClientBlock::GetClientTypeString(this, &v25);
        if ( ClientTypeString && AreEnglishStringsEqual(ClientTypeString, L"StartMenuInternet") )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Extensions\\ContractId\\Windows.Search", 0, 2u, &hKey) )
          {
            *(_DWORD *)Data = 0;
            if ( !RegSetValueExW(hKey, L"ForceCacheRefresh", 0, 4u, Data, 4u) )
              RegDeleteValueW(hKey, L"ForceCacheRefresh");
          }
          CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(&hKey);
        }
        CValuePtr::Release((CValuePtr *)&v25);
      }
      v17 = FindDescendentByName(*(struct DirectUI::Element **)(v10 + 32), L"setdefault");
      if ( DirectUI::Element::GetSelected(v17)
        && CLIENTINFO::GetInstallFile((CLIENTINFO *)v10, v22, L"ReinstallCommand", &SubKey, phkResult, 0) )
      {
        hKey = 0;
        GetSystemTimeAsFileTime((LPFILETIME)&hKey);
        if ( v4 )
          SHSetValueW(v4, 0, L"LastUserInitiatedDefaultChange", 3u, &hKey, 8u);
        if ( v5 )
          SHSetValueW(v5, 0, L"LastUserInitiatedDefaultChange", 3u, &hKey, 8u);
        v3 = ARPFrame::LaunchClientCommandAndWait(v26, 0x65u, *(const unsigned __int16 **)(v10 + 8), &SubKey);
        if ( v3 >= 0 && *(_QWORD *)(v10 + 16) && !ppv )
          v3 = CoCreateInstance(
                 &CLSID_ApplicationAssociationRegistration,
                 0,
                 1u,
                 &GUID_a357134e_8c1e_4edd_8474_40a80546f54f,
                 &ppv);
      }
      RegCloseKey(v22);
      wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v27,
        (unsigned int)v3);
    }
    AppWizLoggingTelemetry::SPADWizardApply::~SPADWizardApply((AppWizLoggingTelemetry::SPADWizardApply *)v27);
    ++v6;
  }
  while ( v3 >= 0 );
  v18 = ppv;
  ppv = 0;
  if ( v18 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v4 )
    RegCloseKey(v4);
  if ( v5 )
    RegCloseKey(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009550  mov     [rsp-8+arg_10], rbx
0x180009555  push    rbp
0x180009556  push    rsi
0x180009557  push    rdi
0x180009558  push    r12
0x18000955a  push    r13
0x18000955c  push    r14
0x18000955e  push    r15
0x180009560  lea     rbp, [rsp-2D0h]
0x180009568  sub     rsp, 3D0h
0x18000956f  mov     rax, cs:__security_cookie
0x180009576  xor     rax, rsp
0x180009579  mov     [rbp+300h+var_40], rax
0x180009580  mov     [rsp+400h+var_3A8], rdx
0x180009585  mov     esi, 2001Fh
0x18000958a  mov     rbx, 0FFFFFFFF80000002h
0x180009591  xor     r14d, r14d
0x180009594  mov     r8d, esi; unsigned int
0x180009597  mov     rdx, rbx; HKEY
0x18000959a  xor     r9d, r9d; bool
0x18000959d  mov     r13, rcx
0x1800095a0  mov     edi, r14d
0x1800095a3  call    ?_OpenClientKey@ClientBlock@@AEAAPEAUHKEY__@@PEAU2@K_N@Z; ClientBlock::_OpenClientKey(HKEY__ *,ulong,bool)
0x1800095a8  mov     r9b, 1; bool
0x1800095ab  mov     r8d, esi; unsigned int
0x1800095ae  mov     rdx, rbx; HKEY
0x1800095b1  mov     rcx, r13; this
0x1800095b4  mov     r15, rax
0x1800095b7  call    ?_OpenClientKey@ClientBlock@@AEAAPEAUHKEY__@@PEAU2@K_N@Z; ClientBlock::_OpenClientKey(HKEY__ *,ulong,bool)
0x1800095bc  mov     rsi, rax
0x1800095bf  mov     [rsp+400h+ppv], r14
0x1800095c4  lea     r12d, [r14+2]
0x1800095c8  mov     rbx, [r13+0C8h]
0x1800095cf  mov     ecx, [rbx]
0x1800095d1  mov     eax, ecx
0x1800095d3  and     eax, 0FFFFFFFh
0x1800095d8  cmp     r12d, eax
0x1800095db  jnb     loc_1800098FF
0x1800095e1  add     rbx, 8
0x1800095e5  bt      ecx, 1Ch
0x1800095e9  jnb     short loc_1800095EE
0x1800095eb  mov     rbx, [rbx]
0x1800095ee  mov     eax, r12d
0x1800095f1  lea     rdx, aSpadwizardappl; "SPADWizardApply"
0x1800095f8  lea     rcx, [rsp+400h+var_3A0]
0x1800095fd  mov     rbx, [rbx+rax*8]
0x180009601  call    ??0?$ActivityBase@VAppWizLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180009606  lea     rax, ??_7SPADWizardApply@AppWizLoggingTelemetry@@6B@; const AppWizLoggingTelemetry::SPADWizardApply::`vftable'
0x18000960d  lea     rcx, [rsp+400h+var_3A0]; this
0x180009612  mov     [rsp+400h+var_3A0], rax
0x180009617  call    ?StartActivity@SPADWizardApply@AppWizLoggingTelemetry@@QEAAXXZ; AppWizLoggingTelemetry::SPADWizardApply::StartActivity(void)
0x18000961c  xor     edx, edx; Val
0x18000961e  mov     [rbp+300h+SubKey], r14w
0x180009626  mov     r8d, 206h; Size
0x18000962c  lea     rcx, [rbp+300h+var_24E]; void *
0x180009633  call    memset_0
0x180009638  mov     r9, [rbx]
0x18000963b  lea     r8, aSInstallinfo; "%s\\InstallInfo"
0x180009642  mov     edx, 104h; unsigned __int64
0x180009647  lea     rcx, [rbp+300h+SubKey]; unsigned __int16 *
0x18000964e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009653  mov     [rsp+400h+var_3C8], r14
0x180009658  mov     rcx, r15
0x18000965b  cmp     [rbx+28h], r14b
0x18000965f  cmovnz  rcx, rsi; hKey
0x180009663  test    rcx, rcx
0x180009666  jz      loc_1800098EA
0x18000966c  lea     rax, [rsp+400h+var_3C8]
0x180009671  mov     r9d, 20019h; samDesired
0x180009677  xor     r8d, r8d; ulOptions
0x18000967a  mov     [rsp+400h+phkResult], rax; unsigned int
0x18000967f  lea     rdx, [rbp+300h+SubKey]; lpSubKey
0x180009686  call    cs:__imp_RegOpenKeyExW
0x18000968c  test    eax, eax
0x18000968e  jnz     loc_1800098EA
0x180009694  mov     rcx, [rbx+20h]; struct DirectUI::Element *
0x180009698  lea     rdx, aShow; "show"
0x18000969f  call    ?FindDescendentByName@@YAPEAVElement@DirectUI@@PEAV12@PEBG@Z; FindDescendentByName(DirectUI::Element *,ushort const *)
0x1800096a4  mov     rcx, rax
0x1800096a7  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800096ad  movzx   r14d, al
0x1800096b1  cmp     r14b, [rbx+29h]
0x1800096b5  jz      loc_1800097C6
0x1800096bb  mov     rdx, [rsp+400h+var_3C8]; HKEY
0x1800096c0  lea     rax, aHideiconscomma; "HideIconsCommand"
0x1800096c7  test    r14b, r14b
0x1800096ca  mov     byte ptr [rsp+400h+cbData], 0; bool
0x1800096cf  lea     r8, aShowiconscomma; "ShowIconsCommand"
0x1800096d6  mov     rcx, rbx; this
0x1800096d9  cmovz   r8, rax; unsigned __int16 *
0x1800096dd  lea     r9, [rbp+300h+SubKey]; unsigned __int16 *
0x1800096e4  call    ?GetInstallFile@CLIENTINFO@@QEAA_NPEAUHKEY__@@PEBGPEAGI_N@Z; CLIENTINFO::GetInstallFile(HKEY__ *,ushort const *,ushort *,uint,bool)
0x1800096e9  test    al, al
0x1800096eb  jz      short loc_18000970D
0x1800096ed  mov     r8, [rbx+8]; unsigned __int16 *
0x1800096f1  lea     r9, [rbp+300h+SubKey]; lpCommandLine
0x1800096f8  mov     rcx, [rsp+400h+var_3A8]; this
0x1800096fd  mov     edx, r14d
0x180009700  xor     edx, 1
0x180009703  add     edx, 63h ; 'c'; unsigned int
0x180009706  call    ?LaunchClientCommandAndWait@ARPFrame@@QEAAJIPEBGPEAG@Z; ARPFrame::LaunchClientCommandAndWait(uint,ushort const *,ushort *)
0x18000970b  mov     edi, eax
0x18000970d  xor     r14d, r14d
0x180009710  lea     rdx, [rsp+400h+var_3B0]; struct DirectUI::Value **
0x180009715  mov     rcx, r13; this
0x180009718  mov     [rsp+400h+var_3B0], r14
0x18000971d  call    ?GetClientTypeString@ClientBlock@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z; ClientBlock::GetClientTypeString(DirectUI::Value * *)
0x180009722  test    rax, rax
0x180009725  jz      loc_1800097BA
0x18000972b  lea     rdx, aStartmenuinter; "StartMenuInternet"
0x180009732  mov     rcx, rax; lpString1
0x180009735  call    ?AreEnglishStringsEqual@@YA_NPEBG0@Z; AreEnglishStringsEqual(ushort const *,ushort const *)
0x18000973a  test    al, al
0x18000973c  jz      short loc_1800097BA
0x18000973e  lea     rax, [rsp+400h+hKey]
0x180009743  mov     [rsp+400h+hKey], r14
0x180009748  lea     r9d, [r14+2]; samDesired
0x18000974c  mov     [rsp+400h+phkResult], rax; phkResult
0x180009751  xor     r8d, r8d; ulOptions
0x180009754  lea     rdx, aExtensionsCont; "Extensions\\ContractId\\Windows.Search"
0x18000975b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180009762  call    cs:__imp_RegOpenKeyExW
0x180009768  test    eax, eax
0x18000976a  jnz     short loc_1800097B0
0x18000976c  lea     ecx, [rax+4]
0x18000976f  mov     dword ptr [rsp+400h+Data], r14d
0x180009774  mov     [rsp+400h+cbData], ecx; cbData
0x180009778  lea     rax, [rsp+400h+Data]
0x18000977d  mov     r9d, ecx; dwType
0x180009780  mov     [rsp+400h+phkResult], rax; lpData
0x180009785  mov     rcx, [rsp+400h+hKey]; hKey
0x18000978a  lea     rdx, aForcecacherefr; "ForceCacheRefresh"
0x180009791  xor     r8d, r8d; Reserved
0x180009794  call    cs:__imp_RegSetValueExW
0x18000979a  test    eax, eax
0x18000979c  jnz     short loc_1800097B0
0x18000979e  mov     rcx, [rsp+400h+hKey]; hKey
0x1800097a3  lea     rdx, aForcecacherefr; "ForceCacheRefresh"
0x1800097aa  call    cs:__imp_RegDeleteValueW
0x1800097b0  lea     rcx, [rsp+400h+hKey]
0x1800097b5  call    ?Release@?$CTSmartObj@PEAUHKEY__@@V?$CAutoHandle_Policy@PEAUHKEY__@@@@@@QEAAXXZ; CTSmartObj<HKEY__ *,CAutoHandle_Policy<HKEY__ *>>::Release(void)
0x1800097ba  lea     rcx, [rsp+400h+var_3B0]; this
0x1800097bf  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800097c4  jmp     short loc_1800097C9
0x1800097c6  xor     r14d, r14d
0x1800097c9  mov     rcx, [rbx+20h]; struct DirectUI::Element *
0x1800097cd  lea     rdx, aSetdefault; "setdefault"
0x1800097d4  call    ?FindDescendentByName@@YAPEAVElement@DirectUI@@PEAV12@PEBG@Z; FindDescendentByName(DirectUI::Element *,ushort const *)
0x1800097d9  mov     rcx, rax
0x1800097dc  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800097e2  test    al, al
0x1800097e4  jz      loc_1800098D3
0x1800097ea  mov     rdx, [rsp+400h+var_3C8]; HKEY
0x1800097ef  lea     r9, [rbp+300h+SubKey]; unsigned __int16 *
0x1800097f6  lea     r8, aReinstallcomma; "ReinstallCommand"
0x1800097fd  mov     byte ptr [rsp+400h+cbData], r14b; bool
0x180009802  mov     rcx, rbx; this
0x180009805  call    ?GetInstallFile@CLIENTINFO@@QEAA_NPEAUHKEY__@@PEBGPEAGI_N@Z; CLIENTINFO::GetInstallFile(HKEY__ *,ushort const *,ushort *,uint,bool)
0x18000980a  test    al, al
0x18000980c  jz      loc_1800098D3
0x180009812  lea     rcx, [rsp+400h+hKey]; lpSystemTimeAsFileTime
0x180009817  mov     [rsp+400h+hKey], r14
0x18000981c  call    cs:__imp_GetSystemTimeAsFileTime
0x180009822  test    r15, r15
0x180009825  jz      short loc_180009851
0x180009827  lea     rax, [rsp+400h+hKey]
0x18000982c  mov     [rsp+400h+cbData], 8; cbData
0x180009834  mov     r9d, 3; dwType
0x18000983a  mov     [rsp+400h+phkResult], rax; pvData
0x18000983f  lea     r8, pszValue; "LastUserInitiatedDefaultChange"
0x180009846  xor     edx, edx; pszSubKey
0x180009848  mov     rcx, r15; hkey
0x18000984b  call    cs:__imp_SHSetValueW
0x180009851  test    rsi, rsi
0x180009854  jz      short loc_180009880
0x180009856  lea     rax, [rsp+400h+hKey]
0x18000985b  mov     [rsp+400h+cbData], 8; cbData
0x180009863  mov     r9d, 3; dwType
0x180009869  mov     [rsp+400h+phkResult], rax; pvData
0x18000986e  lea     r8, pszValue; "LastUserInitiatedDefaultChange"
0x180009875  xor     edx, edx; pszSubKey
0x180009877  mov     rcx, rsi; hkey
0x18000987a  call    cs:__imp_SHSetValueW
0x180009880  mov     r8, [rbx+8]; unsigned __int16 *
0x180009884  lea     r9, [rbp+300h+SubKey]; lpCommandLine
0x18000988b  mov     rcx, [rsp+400h+var_3A8]; this
0x180009890  mov     edx, 65h ; 'e'; unsigned int
0x180009895  call    ?LaunchClientCommandAndWait@ARPFrame@@QEAAJIPEBGPEAG@Z; ARPFrame::LaunchClientCommandAndWait(uint,ushort const *,ushort *)
0x18000989a  mov     edi, eax
0x18000989c  test    eax, eax
0x18000989e  js      short loc_1800098D3
0x1800098a0  cmp     [rbx+10h], r14
0x1800098a4  jz      short loc_1800098D3
0x1800098a6  cmp     [rsp+400h+ppv], r14
0x1800098ab  jnz     short loc_1800098D3
0x1800098ad  xor     edx, edx; pUnkOuter
0x1800098af  lea     rax, [rsp+400h+ppv]
0x1800098b4  lea     r9, _GUID_a357134e_8c1e_4edd_8474_40a80546f54f; riid
0x1800098bb  mov     [rsp+400h+phkResult], rax; ppv
0x1800098c0  lea     rcx, CLSID_ApplicationAssociationRegistration; rclsid
0x1800098c7  lea     r8d, [rdx+1]; dwClsContext
0x1800098cb  call    cs:__imp_CoCreateInstance
0x1800098d1  mov     edi, eax
0x1800098d3  mov     rcx, [rsp+400h+var_3C8]; hKey
0x1800098d8  call    cs:__imp_RegCloseKey
0x1800098de  mov     edx, edi
0x1800098e0  lea     rcx, [rsp+400h+var_3A0]
0x1800098e5  call    ?Stop@?$ActivityBase@VAppWizLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800098ea  lea     rcx, [rsp+400h+var_3A0]; this
0x1800098ef  call    ??1SPADWizardApply@AppWizLoggingTelemetry@@QEAA@XZ; AppWizLoggingTelemetry::SPADWizardApply::~SPADWizardApply(void)
0x1800098f4  inc     r12d
0x1800098f7  test    edi, edi
0x1800098f9  jns     loc_1800095C8
0x1800098ff  mov     rcx, [rsp+400h+ppv]
0x180009904  mov     [rsp+400h+ppv], r14
0x180009909  test    rcx, rcx
0x18000990c  jz      short loc_18000991A
0x18000990e  mov     rax, [rcx]
0x180009911  mov     rax, [rax+10h]
0x180009915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991a  test    r15, r15
0x18000991d  jz      short loc_180009928
0x18000991f  mov     rcx, r15; hKey
0x180009922  call    cs:__imp_RegCloseKey
0x180009928  test    rsi, rsi
0x18000992b  jz      short loc_180009936
0x18000992d  mov     rcx, rsi; hKey
0x180009930  call    cs:__imp_RegCloseKey
0x180009936  mov     eax, edi
0x180009938  mov     rcx, [rbp+300h+var_40]
0x18000993f  xor     rcx, rsp; StackCookie
0x180009942  call    __security_check_cookie
0x180009947  mov     rbx, [rsp+400h+arg_10]
0x18000994f  add     rsp, 3D0h
0x180009956  pop     r15
0x180009958  pop     r14
0x18000995a  pop     r13
0x18000995c  pop     r12
0x18000995e  pop     rdi
0x18000995f  pop     rsi
0x180009960  pop     rbp
0x180009961  retn
```
