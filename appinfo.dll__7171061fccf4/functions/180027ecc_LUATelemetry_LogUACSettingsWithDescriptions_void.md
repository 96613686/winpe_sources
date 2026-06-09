# LUATelemetry::LogUACSettingsWithDescriptions(void)

- ea: `0x180027ecc`
- end: `0x1800281d6`
- name: `?LogUACSettingsWithDescriptions@LUATelemetry@@SAXXZ`
- size: `778`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180028270`

## callees

- `0x180001a4c`
- `0x1800110e0`
- `0x180011fd0`
- `0x18001b23c`
- `0x180027ecc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027f0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028061`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027f0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028061`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800281bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800281bc`

## string_xrefs

- `0x180027f9f`: `EnableSecureUIAPaths`
- `0x180027f8c`: `EnableInstallerDetection`
- `0x180028024`: `EnableLinkedConnections`

## pseudocode

```c
void LUATelemetry::LogUACSettingsWithDescriptions(void)
{
  unsigned int v0; // r8d
  unsigned int LUARegValue; // edi
  unsigned int v2; // r8d
  unsigned int v3; // esi
  unsigned int v4; // r8d
  unsigned int v5; // r14d
  unsigned int v6; // r8d
  unsigned int v7; // r15d
  unsigned int v8; // r8d
  unsigned int v9; // r12d
  unsigned int v10; // r8d
  unsigned int v11; // r13d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  unsigned int v21; // ebx
  unsigned int v22; // r8d
  const struct _tlgProvider_t *v23; // rax
  int v24; // r8d
  int v25; // r9d
  HKEY hKey; // [rsp+B0h] [rbp-80h] BYREF
  unsigned int v27; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v28; // [rsp+BCh] [rbp-74h] BYREF
  unsigned int v29; // [rsp+C0h] [rbp-70h] BYREF
  unsigned int v30; // [rsp+C4h] [rbp-6Ch] BYREF
  unsigned int v31; // [rsp+C8h] [rbp-68h] BYREF
  unsigned int v32; // [rsp+CCh] [rbp-64h] BYREF
  unsigned int v33; // [rsp+D0h] [rbp-60h] BYREF
  unsigned int v34; // [rsp+D4h] [rbp-5Ch] BYREF
  unsigned int v35; // [rsp+D8h] [rbp-58h] BYREF
  unsigned int v36; // [rsp+DCh] [rbp-54h] BYREF
  unsigned int v37; // [rsp+E0h] [rbp-50h] BYREF
  unsigned int v38; // [rsp+E4h] [rbp-4Ch] BYREF
  HKEY phkResult; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v40[10]; // [rsp+F0h] [rbp-40h] BYREF
  unsigned int v41; // [rsp+150h] [rbp+20h] BYREF
  unsigned int v42; // [rsp+158h] [rbp+28h] BYREF
  unsigned int v43; // [rsp+160h] [rbp+30h] BYREF
  unsigned int v44; // [rsp+168h] [rbp+38h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          0,
          0x20019u,
          &hKey) )
  {
    LUARegValue = LUATelemetry::QueryLUARegValue(hKey, L"EnableLUA", v0);
    v3 = LUATelemetry::QueryLUARegValue(hKey, L"ConsentPromptBehaviorUser", v2);
    v5 = LUATelemetry::QueryLUARegValue(hKey, L"ConsentPromptBehaviorAdmin", v4);
    v7 = LUATelemetry::QueryLUARegValue(hKey, L"ConsentPromptBehaviorEnhancedAdmin", v6);
    v9 = LUATelemetry::QueryLUARegValue(hKey, L"PromptOnSecureDesktop", v8);
    v11 = LUATelemetry::QueryLUARegValue(hKey, L"EnableVirtualization", v10);
    v31 = LUATelemetry::QueryLUARegValue(hKey, L"EnableInstallerDetection", v12);
    v30 = LUATelemetry::QueryLUARegValue(hKey, L"EnableSecureUIAPaths", v13);
    v29 = LUATelemetry::QueryLUARegValue(hKey, L"EnableUIADesktopToggle", v14);
    v28 = LUATelemetry::QueryLUARegValue(hKey, L"ValidateAdminCodeSignatures", v15);
    v27 = LUATelemetry::QueryLUARegValue(hKey, L"EnableRestrictedAutoApprove", v16);
    v44 = LUATelemetry::QueryLUARegValue(hKey, L"TypeOfAdminApprovalMode", v17);
    v43 = LUATelemetry::QueryLUARegValue(hKey, L"EnableAutoApproveIntegrityContinuity", v18);
    v42 = LUATelemetry::QueryLUARegValue(hKey, L"EnableAutomaticAdmin", v19);
    v41 = LUATelemetry::QueryLUARegValue(hKey, L"EnableLinkedConnections", v20);
    phkResult = 0;
    v21 = -1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\CredUI",
            0,
            0x20019u,
            &phkResult) )
      v21 = LUATelemetry::QueryLUARegValue(phkResult, L"EnableSecureCredentialPrompting", v22);
    v23 = LUATelemetry::Provider();
    if ( *(_DWORD *)v23 > 5u )
    {
      if ( (unsigned __int8)tlgKeywordOn(v23, 0x800000000000LL) )
      {
        v40[0] = 2048;
        v32 = v21;
        v33 = v11;
        v34 = v9;
        v35 = v7;
        v36 = v5;
        v37 = v3;
        v38 = LUARegValue;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v24,
          (unsigned int)&unk_180054690,
          v24,
          v25,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&v32,
          (__int64)v40);
      }
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180027ecc  push    rbp
0x180027ece  push    rbx
0x180027ecf  push    rsi
0x180027ed0  push    rdi
0x180027ed1  push    r12
0x180027ed3  push    r13
0x180027ed5  push    r14
0x180027ed7  push    r15
0x180027ed9  lea     rbp, [rsp+28h]
0x180027ede  sub     rsp, 108h
0x180027ee5  lea     rax, [rbp+10h+hKey]
0x180027ee9  mov     [rbp+10h+hKey], 0
0x180027ef1  mov     r9d, 20019h; samDesired
0x180027ef7  mov     [rsp+140h+phkResult], rax; phkResult
0x180027efc  xor     r8d, r8d; ulOptions
0x180027eff  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027f06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027f0d  call    cs:__imp_RegOpenKeyExW
0x180027f13  test    eax, eax
0x180027f15  jnz     loc_1800281C2
0x180027f1b  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f1f  lea     rdx, aEnablelua; "EnableLUA"
0x180027f26  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027f2b  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f2f  lea     rdx, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x180027f36  mov     edi, eax
0x180027f38  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027f3d  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f41  lea     rdx, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180027f48  mov     esi, eax
0x180027f4a  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027f4f  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f53  lea     rdx, aConsentpromptb_1; "ConsentPromptBehaviorEnhancedAdmin"
0x180027f5a  mov     r14d, eax
0x180027f5d  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027f62  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f66  lea     rdx, aPromptonsecure; "PromptOnSecureDesktop"
0x180027f6d  mov     r15d, eax
0x180027f70  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027f75  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f79  lea     rdx, aEnablevirtuali; "EnableVirtualization"
0x180027f80  mov     r12d, eax
0x180027f83  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027f88  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f8c  lea     rdx, aEnableinstalle; "EnableInstallerDetection"
0x180027f93  mov     r13d, eax
0x180027f96  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027f9b  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027f9f  lea     rdx, aEnablesecureui; "EnableSecureUIAPaths"
0x180027fa6  mov     [rbp+10h+var_78], eax
0x180027fa9  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027fae  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027fb2  lea     rdx, aEnableuiadeskt; "EnableUIADesktopToggle"
0x180027fb9  mov     [rbp+10h+var_7C], eax
0x180027fbc  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027fc1  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027fc5  lea     rdx, aValidateadminc; "ValidateAdminCodeSignatures"
0x180027fcc  mov     [rbp+10h+var_80], eax
0x180027fcf  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027fd4  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027fd8  lea     rdx, aEnablerestrict; "EnableRestrictedAutoApprove"
0x180027fdf  mov     [rbp+10h+var_84], eax
0x180027fe2  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027fe7  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027feb  lea     rdx, aTypeofadminapp; "TypeOfAdminApprovalMode"
0x180027ff2  mov     [rbp+10h+var_88], eax
0x180027ff5  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027ffa  mov     rcx, [rbp+10h+hKey]; HKEY
0x180027ffe  lea     rdx, aEnableautoappr; "EnableAutoApproveIntegrityContinuity"
0x180028005  mov     [rbp+10h+arg_18], eax
0x180028008  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x18002800d  mov     rcx, [rbp+10h+hKey]; HKEY
0x180028011  lea     rdx, aEnableautomati; "EnableAutomaticAdmin"
0x180028018  mov     [rbp+10h+arg_10], eax
0x18002801b  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180028020  mov     rcx, [rbp+10h+hKey]; HKEY
0x180028024  lea     rdx, aEnablelinkedco; "EnableLinkedConnections"
0x18002802b  mov     [rbp+10h+arg_8], eax
0x18002802e  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180028033  mov     [rbp+10h+arg_0], eax
0x180028036  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002803d  lea     rax, [rbp+10h+var_58]
0x180028041  mov     [rbp+10h+var_58], 0
0x180028049  mov     r9d, 20019h; samDesired
0x18002804f  mov     [rsp+140h+phkResult], rax; phkResult
0x180028054  xor     r8d, r8d; ulOptions
0x180028057  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002805e  or      ebx, 0FFFFFFFFh
0x180028061  call    cs:__imp_RegOpenKeyExW
0x180028067  test    eax, eax
0x180028069  jnz     short loc_18002807D
0x18002806b  mov     rcx, [rbp+10h+var_58]; HKEY
0x18002806f  lea     rdx, aEnablesecurecr; "EnableSecureCredentialPrompting"
0x180028076  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x18002807b  mov     ebx, eax
0x18002807d  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180028082  mov     r8, rax
0x180028085  mov     ecx, [rax]
0x180028087  cmp     ecx, 5
0x18002808a  jbe     loc_1800281B8
0x180028090  mov     rdx, 800000000000h
0x18002809a  mov     rcx, rax
0x18002809d  call    _tlgKeywordOn
0x1800280a2  test    al, al
0x1800280a4  jz      loc_1800281B8
0x1800280aa  mov     eax, [rbp+10h+arg_0]
0x1800280ad  lea     rdx, unk_180054690
0x1800280b4  mov     [rbp+10h+arg_0], eax
0x1800280b7  mov     rcx, r8
0x1800280ba  mov     eax, [rbp+10h+arg_8]
0x1800280bd  mov     [rbp+10h+arg_8], eax
0x1800280c0  mov     eax, [rbp+10h+arg_10]
0x1800280c3  mov     [rbp+10h+arg_10], eax
0x1800280c6  mov     eax, [rbp+10h+arg_18]
0x1800280c9  mov     [rbp+10h+arg_18], eax
0x1800280cc  mov     eax, [rbp+10h+var_88]
0x1800280cf  mov     [rbp+10h+var_88], eax
0x1800280d2  mov     eax, [rbp+10h+var_84]
0x1800280d5  mov     [rbp+10h+var_84], eax
0x1800280d8  mov     eax, [rbp+10h+var_80]
0x1800280db  mov     [rbp+10h+var_80], eax
0x1800280de  mov     eax, [rbp+10h+var_7C]
0x1800280e1  mov     [rbp+10h+var_7C], eax
0x1800280e4  mov     eax, [rbp+10h+var_78]
0x1800280e7  mov     [rbp+10h+var_78], eax
0x1800280ea  lea     rax, [rbp+10h+var_50]
0x1800280ee  mov     [rsp+140h+var_A0], rax
0x1800280f6  lea     rax, [rbp+10h+var_74]
0x1800280fa  mov     [rsp+140h+var_A8], rax
0x180028102  lea     rax, [rbp+10h+arg_0]
0x180028106  mov     [rsp+140h+var_B0], rax
0x18002810e  lea     rax, [rbp+10h+arg_8]
0x180028112  mov     [rsp+140h+var_B8], rax
0x18002811a  lea     rax, [rbp+10h+arg_10]
0x18002811e  mov     [rsp+140h+var_C0], rax
0x180028126  lea     rax, [rbp+10h+arg_18]
0x18002812a  mov     [rsp+140h+var_C8], rax
0x18002812f  lea     rax, [rbp+10h+var_88]
0x180028133  mov     [rsp+140h+var_D0], rax
0x180028138  lea     rax, [rbp+10h+var_84]
0x18002813c  mov     [rsp+140h+var_D8], rax
0x180028141  lea     rax, [rbp+10h+var_80]
0x180028145  mov     [rsp+140h+var_E0], rax
0x18002814a  lea     rax, [rbp+10h+var_7C]
0x18002814e  mov     [rsp+140h+var_E8], rax
0x180028153  lea     rax, [rbp+10h+var_78]
0x180028157  mov     [rsp+140h+var_F0], rax
0x18002815c  lea     rax, [rbp+10h+var_70]
0x180028160  mov     [rsp+140h+var_F8], rax
0x180028165  lea     rax, [rbp+10h+var_6C]
0x180028169  mov     [rsp+140h+var_100], rax
0x18002816e  lea     rax, [rbp+10h+var_68]
0x180028172  mov     [rsp+140h+var_108], rax
0x180028177  lea     rax, [rbp+10h+var_64]
0x18002817b  mov     [rsp+140h+var_110], rax
0x180028180  lea     rax, [rbp+10h+var_60]
0x180028184  mov     [rsp+140h+var_118], rax
0x180028189  lea     rax, [rbp+10h+var_5C]
0x18002818d  mov     [rsp+140h+phkResult], rax
0x180028192  mov     [rbp+10h+var_50], 800h
0x18002819a  mov     [rbp+10h+var_74], ebx
0x18002819d  mov     [rbp+10h+var_70], r13d
0x1800281a1  mov     [rbp+10h+var_6C], r12d
0x1800281a5  mov     [rbp+10h+var_68], r15d
0x1800281a9  mov     [rbp+10h+var_64], r14d
0x1800281ad  mov     [rbp+10h+var_60], esi
0x1800281b0  mov     [rbp+10h+var_5C], edi
0x1800281b3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333333333333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800281b8  mov     rcx, [rbp+10h+hKey]; hKey
0x1800281bc  call    cs:__imp_RegCloseKey
0x1800281c2  add     rsp, 108h
0x1800281c9  pop     r15
0x1800281cb  pop     r14
0x1800281cd  pop     r13
0x1800281cf  pop     r12
0x1800281d1  pop     rdi
0x1800281d2  pop     rsi
0x1800281d3  pop     rbx
0x1800281d4  pop     rbp
0x1800281d5  retn
```
