# LUATelemetry::LogUACSettings(void)

- ea: `0x180027bd0`
- end: `0x180027ec6`
- name: `?LogUACSettings@LUATelemetry@@SAXXZ`
- size: `758`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180028270`

## callees

- `0x1800018c0`
- `0x1800110e0`
- `0x180011fd0`
- `0x18001b23c`
- `0x180027bd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027eac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027eac`

## string_xrefs

- `0x180027ca3`: `EnableSecureUIAPaths`
- `0x180027c90`: `EnableInstallerDetection`
- `0x180027d28`: `EnableLinkedConnections`

## pseudocode

```c
void LUATelemetry::LogUACSettings(void)
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
  __int64 v24; // r8
  __int64 v25; // r9
  HKEY hKey; // [rsp+A0h] [rbp-29h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp-21h] BYREF
  unsigned int v28; // [rsp+ACh] [rbp-1Dh] BYREF
  unsigned int v29; // [rsp+B0h] [rbp-19h] BYREF
  unsigned int v30; // [rsp+B4h] [rbp-15h] BYREF
  unsigned int v31; // [rsp+B8h] [rbp-11h] BYREF
  unsigned int v32; // [rsp+BCh] [rbp-Dh] BYREF
  unsigned int v33; // [rsp+C0h] [rbp-9h] BYREF
  unsigned int v34; // [rsp+C4h] [rbp-5h] BYREF
  unsigned int v35; // [rsp+C8h] [rbp-1h] BYREF
  unsigned int v36; // [rsp+CCh] [rbp+3h] BYREF
  unsigned int v37; // [rsp+D0h] [rbp+7h] BYREF
  unsigned int v38; // [rsp+D4h] [rbp+Bh] BYREF
  HKEY phkResult; // [rsp+D8h] [rbp+Fh] BYREF
  unsigned int v40; // [rsp+130h] [rbp+67h] BYREF
  unsigned int v41; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned int v42; // [rsp+140h] [rbp+77h] BYREF
  unsigned int v43; // [rsp+148h] [rbp+7Fh] BYREF

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
    v43 = LUATelemetry::QueryLUARegValue(hKey, L"TypeOfAdminApprovalMode", v17);
    v42 = LUATelemetry::QueryLUARegValue(hKey, L"EnableAutoApproveIntegrityContinuity", v18);
    v41 = LUATelemetry::QueryLUARegValue(hKey, L"EnableAutomaticAdmin", v19);
    v40 = LUATelemetry::QueryLUARegValue(hKey, L"EnableLinkedConnections", v20);
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
      if ( (unsigned __int8)tlgKeywordOn(v23, 0x400000000000LL) )
      {
        v32 = v21;
        v33 = v11;
        v34 = v9;
        v35 = v7;
        v36 = v5;
        v37 = v3;
        v38 = LUARegValue;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v24,
          (__int64)byte_1800544D1,
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
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v32);
      }
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180027bd0  push    rbp
0x180027bd2  push    rbx
0x180027bd3  push    rsi
0x180027bd4  push    rdi
0x180027bd5  push    r12
0x180027bd7  push    r13
0x180027bd9  push    r14
0x180027bdb  push    r15
0x180027bdd  lea     rbp, [rsp-1Fh]
0x180027be2  sub     rsp, 0E8h
0x180027be9  lea     rax, [rbp+57h+hKey]
0x180027bed  mov     [rbp+57h+hKey], 0
0x180027bf5  mov     r9d, 20019h; samDesired
0x180027bfb  mov     [rsp+120h+phkResult], rax; phkResult
0x180027c00  xor     r8d, r8d; ulOptions
0x180027c03  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027c0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027c11  call    cs:__imp_RegOpenKeyExW
0x180027c17  test    eax, eax
0x180027c19  jnz     loc_180027EB2
0x180027c1f  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027c23  lea     rdx, aEnablelua; "EnableLUA"
0x180027c2a  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027c2f  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027c33  lea     rdx, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x180027c3a  mov     edi, eax
0x180027c3c  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027c41  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027c45  lea     rdx, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180027c4c  mov     esi, eax
0x180027c4e  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027c53  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027c57  lea     rdx, aConsentpromptb_1; "ConsentPromptBehaviorEnhancedAdmin"
0x180027c5e  mov     r14d, eax
0x180027c61  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027c66  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027c6a  lea     rdx, aPromptonsecure; "PromptOnSecureDesktop"
0x180027c71  mov     r15d, eax
0x180027c74  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027c79  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027c7d  lea     rdx, aEnablevirtuali; "EnableVirtualization"
0x180027c84  mov     r12d, eax
0x180027c87  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027c8c  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027c90  lea     rdx, aEnableinstalle; "EnableInstallerDetection"
0x180027c97  mov     r13d, eax
0x180027c9a  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027c9f  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027ca3  lea     rdx, aEnablesecureui; "EnableSecureUIAPaths"
0x180027caa  mov     [rbp+57h+var_68], eax
0x180027cad  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027cb2  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027cb6  lea     rdx, aEnableuiadeskt; "EnableUIADesktopToggle"
0x180027cbd  mov     [rbp+57h+var_6C], eax
0x180027cc0  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027cc5  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027cc9  lea     rdx, aValidateadminc; "ValidateAdminCodeSignatures"
0x180027cd0  mov     [rbp+57h+var_70], eax
0x180027cd3  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027cd8  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027cdc  lea     rdx, aEnablerestrict; "EnableRestrictedAutoApprove"
0x180027ce3  mov     [rbp+57h+var_74], eax
0x180027ce6  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027ceb  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027cef  lea     rdx, aTypeofadminapp; "TypeOfAdminApprovalMode"
0x180027cf6  mov     [rbp+57h+var_78], eax
0x180027cf9  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027cfe  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027d02  lea     rdx, aEnableautoappr; "EnableAutoApproveIntegrityContinuity"
0x180027d09  mov     [rbp+57h+arg_18], eax
0x180027d0c  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027d11  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027d15  lea     rdx, aEnableautomati; "EnableAutomaticAdmin"
0x180027d1c  mov     [rbp+57h+arg_10], eax
0x180027d1f  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027d24  mov     rcx, [rbp+57h+hKey]; HKEY
0x180027d28  lea     rdx, aEnablelinkedco; "EnableLinkedConnections"
0x180027d2f  mov     [rbp+57h+arg_8], eax
0x180027d32  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027d37  mov     [rbp+57h+arg_0], eax
0x180027d3a  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180027d41  lea     rax, [rbp+57h+var_48]
0x180027d45  mov     [rbp+57h+var_48], 0
0x180027d4d  mov     r9d, 20019h; samDesired
0x180027d53  mov     [rsp+120h+phkResult], rax; phkResult
0x180027d58  xor     r8d, r8d; ulOptions
0x180027d5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027d62  or      ebx, 0FFFFFFFFh
0x180027d65  call    cs:__imp_RegOpenKeyExW
0x180027d6b  test    eax, eax
0x180027d6d  jnz     short loc_180027D81
0x180027d6f  mov     rcx, [rbp+57h+var_48]; HKEY
0x180027d73  lea     rdx, aEnablesecurecr; "EnableSecureCredentialPrompting"
0x180027d7a  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180027d7f  mov     ebx, eax
0x180027d81  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180027d86  mov     r8, rax
0x180027d89  mov     ecx, [rax]
0x180027d8b  cmp     ecx, 5
0x180027d8e  jbe     loc_180027EA8
0x180027d94  mov     rdx, 400000000000h
0x180027d9e  mov     rcx, rax
0x180027da1  call    _tlgKeywordOn
0x180027da6  test    al, al
0x180027da8  jz      loc_180027EA8
0x180027dae  mov     eax, [rbp+57h+arg_0]
0x180027db1  lea     rdx, byte_1800544D1
0x180027db8  mov     [rbp+57h+arg_0], eax
0x180027dbb  mov     rcx, r8
0x180027dbe  mov     eax, [rbp+57h+arg_8]
0x180027dc1  mov     [rbp+57h+arg_8], eax
0x180027dc4  mov     eax, [rbp+57h+arg_10]
0x180027dc7  mov     [rbp+57h+arg_10], eax
0x180027dca  mov     eax, [rbp+57h+arg_18]
0x180027dcd  mov     [rbp+57h+arg_18], eax
0x180027dd0  mov     eax, [rbp+57h+var_78]
0x180027dd3  mov     [rbp+57h+var_78], eax
0x180027dd6  mov     eax, [rbp+57h+var_74]
0x180027dd9  mov     [rbp+57h+var_74], eax
0x180027ddc  mov     eax, [rbp+57h+var_70]
0x180027ddf  mov     [rbp+57h+var_70], eax
0x180027de2  mov     eax, [rbp+57h+var_6C]
0x180027de5  mov     [rbp+57h+var_6C], eax
0x180027de8  mov     eax, [rbp+57h+var_68]
0x180027deb  mov     [rbp+57h+var_68], eax
0x180027dee  lea     rax, [rbp+57h+var_64]
0x180027df2  mov     [rsp+120h+var_88], rax
0x180027dfa  lea     rax, [rbp+57h+arg_0]
0x180027dfe  mov     [rsp+120h+var_90], rax
0x180027e06  lea     rax, [rbp+57h+arg_8]
0x180027e0a  mov     [rsp+120h+var_98], rax
0x180027e12  lea     rax, [rbp+57h+arg_10]
0x180027e16  mov     [rsp+120h+var_A0], rax
0x180027e1e  lea     rax, [rbp+57h+arg_18]
0x180027e22  mov     [rsp+120h+var_A8], rax
0x180027e27  lea     rax, [rbp+57h+var_78]
0x180027e2b  mov     [rsp+120h+var_B0], rax
0x180027e30  lea     rax, [rbp+57h+var_74]
0x180027e34  mov     [rsp+120h+var_B8], rax
0x180027e39  lea     rax, [rbp+57h+var_70]
0x180027e3d  mov     [rsp+120h+var_C0], rax
0x180027e42  lea     rax, [rbp+57h+var_6C]
0x180027e46  mov     [rsp+120h+var_C8], rax
0x180027e4b  lea     rax, [rbp+57h+var_68]
0x180027e4f  mov     [rsp+120h+var_D0], rax
0x180027e54  lea     rax, [rbp+57h+var_60]
0x180027e58  mov     [rsp+120h+var_D8], rax
0x180027e5d  lea     rax, [rbp+57h+var_5C]
0x180027e61  mov     [rsp+120h+var_E0], rax
0x180027e66  lea     rax, [rbp+57h+var_58]
0x180027e6a  mov     [rsp+120h+var_E8], rax
0x180027e6f  lea     rax, [rbp+57h+var_54]
0x180027e73  mov     [rsp+120h+var_F0], rax
0x180027e78  lea     rax, [rbp+57h+var_50]
0x180027e7c  mov     [rsp+120h+var_F8], rax
0x180027e81  lea     rax, [rbp+57h+var_4C]
0x180027e85  mov     [rsp+120h+phkResult], rax
0x180027e8a  mov     [rbp+57h+var_64], ebx
0x180027e8d  mov     [rbp+57h+var_60], r13d
0x180027e91  mov     [rbp+57h+var_5C], r12d
0x180027e95  mov     [rbp+57h+var_58], r15d
0x180027e99  mov     [rbp+57h+var_54], r14d
0x180027e9d  mov     [rbp+57h+var_50], esi
0x180027ea0  mov     [rbp+57h+var_4C], edi
0x180027ea3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333333333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180027ea8  mov     rcx, [rbp+57h+hKey]; hKey
0x180027eac  call    cs:__imp_RegCloseKey
0x180027eb2  add     rsp, 0E8h
0x180027eb9  pop     r15
0x180027ebb  pop     r14
0x180027ebd  pop     r13
0x180027ebf  pop     r12
0x180027ec1  pop     rdi
0x180027ec2  pop     rsi
0x180027ec3  pop     rbx
0x180027ec4  pop     rbp
0x180027ec5  retn
```
