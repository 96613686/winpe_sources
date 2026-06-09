# LUATelemetry::LogUACSettings(void)

- ea: `0x180013ad0`
- end: `0x180013dcc`
- name: `?LogUACSettings@LUATelemetry@@SAXXZ`
- size: `764`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013de0`

## callees

- `0x1800018ac`
- `0x18000cb30`
- `0x18001252c`
- `0x180013ad0`
- `0x18001fd94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013b0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013c65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013b0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013dab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013dab`

## string_xrefs

- `0x180013ba6`: `EnableSecureUIAPaths`
- `0x180013b93`: `EnableInstallerDetection`
- `0x180013c2b`: `EnableLinkedConnections`

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
  unsigned int v21; // eax
  unsigned int v22; // ebx
  unsigned int v23; // r8d
  _DWORD *v24; // rcx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  HKEY hKey; // [rsp+A0h] [rbp-29h] BYREF
  unsigned int v29; // [rsp+A8h] [rbp-21h] BYREF
  unsigned int v30; // [rsp+ACh] [rbp-1Dh] BYREF
  unsigned int v31; // [rsp+B0h] [rbp-19h] BYREF
  unsigned int v32; // [rsp+B4h] [rbp-15h] BYREF
  unsigned int v33; // [rsp+B8h] [rbp-11h] BYREF
  unsigned int v34; // [rsp+BCh] [rbp-Dh] BYREF
  unsigned int v35; // [rsp+C0h] [rbp-9h] BYREF
  unsigned int v36; // [rsp+C4h] [rbp-5h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp-1h] BYREF
  unsigned int v38; // [rsp+CCh] [rbp+3h] BYREF
  unsigned int v39; // [rsp+D0h] [rbp+7h] BYREF
  unsigned int v40; // [rsp+D4h] [rbp+Bh] BYREF
  HKEY phkResult; // [rsp+D8h] [rbp+Fh] BYREF
  unsigned int v42; // [rsp+130h] [rbp+67h] BYREF
  unsigned int v43; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned int v44; // [rsp+140h] [rbp+77h] BYREF
  unsigned int v45; // [rsp+148h] [rbp+7Fh] BYREF

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
    v33 = LUATelemetry::QueryLUARegValue(hKey, L"EnableInstallerDetection", v12);
    v32 = LUATelemetry::QueryLUARegValue(hKey, L"EnableSecureUIAPaths", v13);
    v31 = LUATelemetry::QueryLUARegValue(hKey, L"EnableUIADesktopToggle", v14);
    v30 = LUATelemetry::QueryLUARegValue(hKey, L"ValidateAdminCodeSignatures", v15);
    v29 = LUATelemetry::QueryLUARegValue(hKey, L"EnableRestrictedAutoApprove", v16);
    v45 = LUATelemetry::QueryLUARegValue(hKey, L"TypeOfAdminApprovalMode", v17);
    v44 = LUATelemetry::QueryLUARegValue(hKey, L"EnableAutoApproveIntegrityContinuity", v18);
    v43 = LUATelemetry::QueryLUARegValue(hKey, L"EnableAutomaticAdmin", v19);
    v21 = LUATelemetry::QueryLUARegValue(hKey, L"EnableLinkedConnections", v20);
    phkResult = 0;
    v42 = v21;
    v22 = -1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\CredUI",
            0,
            0x20019u,
            &phkResult) )
      v22 = LUATelemetry::QueryLUARegValue(phkResult, L"EnableSecureCredentialPrompting", v23);
    v24 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
    if ( *v24 > 5u )
    {
      if ( (unsigned __int8)tlgKeywordOn(v24, 0x400000000000LL) )
      {
        v34 = v22;
        v35 = v11;
        v36 = v9;
        v37 = v7;
        v38 = v5;
        v39 = v3;
        v40 = LUARegValue;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)&unk_180050ED9,
          v26,
          v27,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v34);
      }
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180013ad0  push    rbp
0x180013ad2  push    rbx
0x180013ad3  push    rsi
0x180013ad4  push    rdi
0x180013ad5  push    r12
0x180013ad7  push    r13
0x180013ad9  push    r14
0x180013adb  push    r15
0x180013add  lea     rbp, [rsp-1Fh]
0x180013ae2  sub     rsp, 0E8h
0x180013ae9  and     [rbp+57h+hKey], 0
0x180013aee  lea     rax, [rbp+57h+hKey]
0x180013af2  mov     r9d, 20019h; samDesired
0x180013af8  mov     [rsp+120h+phkResult], rax; phkResult
0x180013afd  xor     r8d, r8d; ulOptions
0x180013b00  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013b07  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013b0e  call    cs:__imp_RegOpenKeyExW
0x180013b15  nop     dword ptr [rax+rax+00h]
0x180013b1a  test    eax, eax
0x180013b1c  jnz     loc_180013DB7
0x180013b22  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b26  lea     rdx, aEnablelua; "EnableLUA"
0x180013b2d  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b32  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b36  lea     rdx, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x180013b3d  mov     edi, eax
0x180013b3f  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b44  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b48  lea     rdx, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180013b4f  mov     esi, eax
0x180013b51  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b56  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b5a  lea     rdx, aConsentpromptb_1; "ConsentPromptBehaviorEnhancedAdmin"
0x180013b61  mov     r14d, eax
0x180013b64  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b69  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b6d  lea     rdx, aPromptonsecure; "PromptOnSecureDesktop"
0x180013b74  mov     r15d, eax
0x180013b77  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b7c  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b80  lea     rdx, aEnablevirtuali; "EnableVirtualization"
0x180013b87  mov     r12d, eax
0x180013b8a  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b8f  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b93  lea     rdx, aEnableinstalle; "EnableInstallerDetection"
0x180013b9a  mov     r13d, eax
0x180013b9d  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013ba2  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013ba6  lea     rdx, aEnablesecureui; "EnableSecureUIAPaths"
0x180013bad  mov     [rbp+57h+var_68], eax
0x180013bb0  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013bb5  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013bb9  lea     rdx, aEnableuiadeskt; "EnableUIADesktopToggle"
0x180013bc0  mov     [rbp+57h+var_6C], eax
0x180013bc3  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013bc8  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013bcc  lea     rdx, aValidateadminc; "ValidateAdminCodeSignatures"
0x180013bd3  mov     [rbp+57h+var_70], eax
0x180013bd6  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013bdb  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013bdf  lea     rdx, aEnablerestrict; "EnableRestrictedAutoApprove"
0x180013be6  mov     [rbp+57h+var_74], eax
0x180013be9  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013bee  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013bf2  lea     rdx, aTypeofadminapp; "TypeOfAdminApprovalMode"
0x180013bf9  mov     [rbp+57h+var_78], eax
0x180013bfc  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013c01  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013c05  lea     rdx, aEnableautoappr; "EnableAutoApproveIntegrityContinuity"
0x180013c0c  mov     [rbp+57h+arg_18], eax
0x180013c0f  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013c14  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013c18  lea     rdx, aEnableautomati; "EnableAutomaticAdmin"
0x180013c1f  mov     [rbp+57h+arg_10], eax
0x180013c22  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013c27  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013c2b  lea     rdx, aEnablelinkedco; "EnableLinkedConnections"
0x180013c32  mov     [rbp+57h+arg_8], eax
0x180013c35  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013c3a  and     [rbp+57h+var_48], 0
0x180013c3f  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013c46  mov     [rbp+57h+arg_0], eax
0x180013c49  mov     r9d, 20019h; samDesired
0x180013c4f  lea     rax, [rbp+57h+var_48]
0x180013c53  xor     r8d, r8d; ulOptions
0x180013c56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013c5d  mov     [rsp+120h+phkResult], rax; phkResult
0x180013c62  or      ebx, 0FFFFFFFFh
0x180013c65  call    cs:__imp_RegOpenKeyExW
0x180013c6c  nop     dword ptr [rax+rax+00h]
0x180013c71  test    eax, eax
0x180013c73  jnz     short loc_180013C87
0x180013c75  mov     rcx, [rbp+57h+var_48]; HKEY
0x180013c79  lea     rdx, aEnablesecurecr; "EnableSecureCredentialPrompting"
0x180013c80  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013c85  mov     ebx, eax
0x180013c87  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180013c8c  mov     rcx, [rax+8]
0x180013c90  cmp     dword ptr [rcx], 5
0x180013c93  jbe     loc_180013DA7
0x180013c99  mov     rdx, 400000000000h
0x180013ca3  call    _tlgKeywordOn
0x180013ca8  test    al, al
0x180013caa  jz      loc_180013DA7
0x180013cb0  mov     eax, [rbp+57h+arg_0]
0x180013cb3  lea     rdx, unk_180050ED9
0x180013cba  mov     [rbp+57h+arg_0], eax
0x180013cbd  mov     eax, [rbp+57h+arg_8]
0x180013cc0  mov     [rbp+57h+arg_8], eax
0x180013cc3  mov     eax, [rbp+57h+arg_10]
0x180013cc6  mov     [rbp+57h+arg_10], eax
0x180013cc9  mov     eax, [rbp+57h+arg_18]
0x180013ccc  mov     [rbp+57h+arg_18], eax
0x180013ccf  mov     eax, [rbp+57h+var_78]
0x180013cd2  mov     [rbp+57h+var_78], eax
0x180013cd5  mov     eax, [rbp+57h+var_74]
0x180013cd8  mov     [rbp+57h+var_74], eax
0x180013cdb  mov     eax, [rbp+57h+var_70]
0x180013cde  mov     [rbp+57h+var_70], eax
0x180013ce1  mov     eax, [rbp+57h+var_6C]
0x180013ce4  mov     [rbp+57h+var_6C], eax
0x180013ce7  mov     eax, [rbp+57h+var_68]
0x180013cea  mov     [rbp+57h+var_68], eax
0x180013ced  lea     rax, [rbp+57h+var_64]
0x180013cf1  mov     [rsp+120h+var_88], rax
0x180013cf9  lea     rax, [rbp+57h+arg_0]
0x180013cfd  mov     [rsp+120h+var_90], rax
0x180013d05  lea     rax, [rbp+57h+arg_8]
0x180013d09  mov     [rsp+120h+var_98], rax
0x180013d11  lea     rax, [rbp+57h+arg_10]
0x180013d15  mov     [rsp+120h+var_A0], rax
0x180013d1d  lea     rax, [rbp+57h+arg_18]
0x180013d21  mov     [rsp+120h+var_A8], rax
0x180013d26  lea     rax, [rbp+57h+var_78]
0x180013d2a  mov     [rsp+120h+var_B0], rax
0x180013d2f  lea     rax, [rbp+57h+var_74]
0x180013d33  mov     [rsp+120h+var_B8], rax
0x180013d38  lea     rax, [rbp+57h+var_70]
0x180013d3c  mov     [rsp+120h+var_C0], rax
0x180013d41  lea     rax, [rbp+57h+var_6C]
0x180013d45  mov     [rsp+120h+var_C8], rax
0x180013d4a  lea     rax, [rbp+57h+var_68]
0x180013d4e  mov     [rsp+120h+var_D0], rax
0x180013d53  lea     rax, [rbp+57h+var_60]
0x180013d57  mov     [rsp+120h+var_D8], rax
0x180013d5c  lea     rax, [rbp+57h+var_5C]
0x180013d60  mov     [rsp+120h+var_E0], rax
0x180013d65  lea     rax, [rbp+57h+var_58]
0x180013d69  mov     [rsp+120h+var_E8], rax
0x180013d6e  lea     rax, [rbp+57h+var_54]
0x180013d72  mov     [rsp+120h+var_F0], rax
0x180013d77  lea     rax, [rbp+57h+var_50]
0x180013d7b  mov     [rsp+120h+var_F8], rax
0x180013d80  lea     rax, [rbp+57h+var_4C]
0x180013d84  mov     [rsp+120h+phkResult], rax
0x180013d89  mov     [rbp+57h+var_64], ebx
0x180013d8c  mov     [rbp+57h+var_60], r13d
0x180013d90  mov     [rbp+57h+var_5C], r12d
0x180013d94  mov     [rbp+57h+var_58], r15d
0x180013d98  mov     [rbp+57h+var_54], r14d
0x180013d9c  mov     [rbp+57h+var_50], esi
0x180013d9f  mov     [rbp+57h+var_4C], edi
0x180013da2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333333333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013da7  mov     rcx, [rbp+57h+hKey]; hKey
0x180013dab  call    cs:__imp_RegCloseKey
0x180013db2  nop     dword ptr [rax+rax+00h]
0x180013db7  add     rsp, 0E8h
0x180013dbe  pop     r15
0x180013dc0  pop     r14
0x180013dc2  pop     r13
0x180013dc4  pop     r12
0x180013dc6  pop     rdi
0x180013dc7  pop     rsi
0x180013dc8  pop     rbx
0x180013dc9  pop     rbp
0x180013dca  retn
```
