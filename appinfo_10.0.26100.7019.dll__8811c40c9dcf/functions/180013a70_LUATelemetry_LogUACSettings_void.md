# LUATelemetry::LogUACSettings(void)

- ea: `0x180013a70`
- end: `0x180013d6c`
- name: `?LogUACSettings@LUATelemetry@@SAXXZ`
- size: `764`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013d80`

## callees

- `0x1800018ac`
- `0x18000cb30`
- `0x1800123ec`
- `0x180013a70`
- `0x180021008`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013aae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013c05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013aae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013c05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d4b`

## string_xrefs

- `0x180013b46`: `EnableSecureUIAPaths`
- `0x180013b33`: `EnableInstallerDetection`
- `0x180013bcb`: `EnableLinkedConnections`

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
          (unsigned int)&unk_18004EE41,
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
0x180013a70  push    rbp
0x180013a72  push    rbx
0x180013a73  push    rsi
0x180013a74  push    rdi
0x180013a75  push    r12
0x180013a77  push    r13
0x180013a79  push    r14
0x180013a7b  push    r15
0x180013a7d  lea     rbp, [rsp-1Fh]
0x180013a82  sub     rsp, 0E8h
0x180013a89  and     [rbp+57h+hKey], 0
0x180013a8e  lea     rax, [rbp+57h+hKey]
0x180013a92  mov     r9d, 20019h; samDesired
0x180013a98  mov     [rsp+120h+phkResult], rax; phkResult
0x180013a9d  xor     r8d, r8d; ulOptions
0x180013aa0  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013aa7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013aae  call    cs:__imp_RegOpenKeyExW
0x180013ab5  nop     dword ptr [rax+rax+00h]
0x180013aba  test    eax, eax
0x180013abc  jnz     loc_180013D57
0x180013ac2  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013ac6  lea     rdx, aEnablelua; "EnableLUA"
0x180013acd  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013ad2  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013ad6  lea     rdx, aConsentpromptb_0; "ConsentPromptBehaviorUser"
0x180013add  mov     edi, eax
0x180013adf  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013ae4  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013ae8  lea     rdx, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180013aef  mov     esi, eax
0x180013af1  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013af6  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013afa  lea     rdx, aConsentpromptb_1; "ConsentPromptBehaviorEnhancedAdmin"
0x180013b01  mov     r14d, eax
0x180013b04  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b09  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b0d  lea     rdx, aPromptonsecure; "PromptOnSecureDesktop"
0x180013b14  mov     r15d, eax
0x180013b17  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b1c  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b20  lea     rdx, aEnablevirtuali; "EnableVirtualization"
0x180013b27  mov     r12d, eax
0x180013b2a  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b2f  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b33  lea     rdx, aEnableinstalle; "EnableInstallerDetection"
0x180013b3a  mov     r13d, eax
0x180013b3d  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b42  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b46  lea     rdx, aEnablesecureui; "EnableSecureUIAPaths"
0x180013b4d  mov     [rbp+57h+var_68], eax
0x180013b50  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b55  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b59  lea     rdx, aEnableuiadeskt; "EnableUIADesktopToggle"
0x180013b60  mov     [rbp+57h+var_6C], eax
0x180013b63  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b68  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b6c  lea     rdx, aValidateadminc; "ValidateAdminCodeSignatures"
0x180013b73  mov     [rbp+57h+var_70], eax
0x180013b76  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b7b  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b7f  lea     rdx, aEnablerestrict; "EnableRestrictedAutoApprove"
0x180013b86  mov     [rbp+57h+var_74], eax
0x180013b89  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013b8e  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013b92  lea     rdx, aTypeofadminapp; "TypeOfAdminApprovalMode"
0x180013b99  mov     [rbp+57h+var_78], eax
0x180013b9c  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013ba1  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013ba5  lea     rdx, aEnableautoappr; "EnableAutoApproveIntegrityContinuity"
0x180013bac  mov     [rbp+57h+arg_18], eax
0x180013baf  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013bb4  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013bb8  lea     rdx, aEnableautomati; "EnableAutomaticAdmin"
0x180013bbf  mov     [rbp+57h+arg_10], eax
0x180013bc2  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013bc7  mov     rcx, [rbp+57h+hKey]; HKEY
0x180013bcb  lea     rdx, aEnablelinkedco; "EnableLinkedConnections"
0x180013bd2  mov     [rbp+57h+arg_8], eax
0x180013bd5  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013bda  and     [rbp+57h+var_48], 0
0x180013bdf  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013be6  mov     [rbp+57h+arg_0], eax
0x180013be9  mov     r9d, 20019h; samDesired
0x180013bef  lea     rax, [rbp+57h+var_48]
0x180013bf3  xor     r8d, r8d; ulOptions
0x180013bf6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013bfd  mov     [rsp+120h+phkResult], rax; phkResult
0x180013c02  or      ebx, 0FFFFFFFFh
0x180013c05  call    cs:__imp_RegOpenKeyExW
0x180013c0c  nop     dword ptr [rax+rax+00h]
0x180013c11  test    eax, eax
0x180013c13  jnz     short loc_180013C27
0x180013c15  mov     rcx, [rbp+57h+var_48]; HKEY
0x180013c19  lea     rdx, aEnablesecurecr; "EnableSecureCredentialPrompting"
0x180013c20  call    ?QueryLUARegValue@LUATelemetry@@CAKPEAUHKEY__@@PEBGK@Z; LUATelemetry::QueryLUARegValue(HKEY__ *,ushort const *,ulong)
0x180013c25  mov     ebx, eax
0x180013c27  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180013c2c  mov     rcx, [rax+8]
0x180013c30  cmp     dword ptr [rcx], 5
0x180013c33  jbe     loc_180013D47
0x180013c39  mov     rdx, 400000000000h
0x180013c43  call    _tlgKeywordOn
0x180013c48  test    al, al
0x180013c4a  jz      loc_180013D47
0x180013c50  mov     eax, [rbp+57h+arg_0]
0x180013c53  lea     rdx, unk_18004EE41
0x180013c5a  mov     [rbp+57h+arg_0], eax
0x180013c5d  mov     eax, [rbp+57h+arg_8]
0x180013c60  mov     [rbp+57h+arg_8], eax
0x180013c63  mov     eax, [rbp+57h+arg_10]
0x180013c66  mov     [rbp+57h+arg_10], eax
0x180013c69  mov     eax, [rbp+57h+arg_18]
0x180013c6c  mov     [rbp+57h+arg_18], eax
0x180013c6f  mov     eax, [rbp+57h+var_78]
0x180013c72  mov     [rbp+57h+var_78], eax
0x180013c75  mov     eax, [rbp+57h+var_74]
0x180013c78  mov     [rbp+57h+var_74], eax
0x180013c7b  mov     eax, [rbp+57h+var_70]
0x180013c7e  mov     [rbp+57h+var_70], eax
0x180013c81  mov     eax, [rbp+57h+var_6C]
0x180013c84  mov     [rbp+57h+var_6C], eax
0x180013c87  mov     eax, [rbp+57h+var_68]
0x180013c8a  mov     [rbp+57h+var_68], eax
0x180013c8d  lea     rax, [rbp+57h+var_64]
0x180013c91  mov     [rsp+120h+var_88], rax
0x180013c99  lea     rax, [rbp+57h+arg_0]
0x180013c9d  mov     [rsp+120h+var_90], rax
0x180013ca5  lea     rax, [rbp+57h+arg_8]
0x180013ca9  mov     [rsp+120h+var_98], rax
0x180013cb1  lea     rax, [rbp+57h+arg_10]
0x180013cb5  mov     [rsp+120h+var_A0], rax
0x180013cbd  lea     rax, [rbp+57h+arg_18]
0x180013cc1  mov     [rsp+120h+var_A8], rax
0x180013cc6  lea     rax, [rbp+57h+var_78]
0x180013cca  mov     [rsp+120h+var_B0], rax
0x180013ccf  lea     rax, [rbp+57h+var_74]
0x180013cd3  mov     [rsp+120h+var_B8], rax
0x180013cd8  lea     rax, [rbp+57h+var_70]
0x180013cdc  mov     [rsp+120h+var_C0], rax
0x180013ce1  lea     rax, [rbp+57h+var_6C]
0x180013ce5  mov     [rsp+120h+var_C8], rax
0x180013cea  lea     rax, [rbp+57h+var_68]
0x180013cee  mov     [rsp+120h+var_D0], rax
0x180013cf3  lea     rax, [rbp+57h+var_60]
0x180013cf7  mov     [rsp+120h+var_D8], rax
0x180013cfc  lea     rax, [rbp+57h+var_5C]
0x180013d00  mov     [rsp+120h+var_E0], rax
0x180013d05  lea     rax, [rbp+57h+var_58]
0x180013d09  mov     [rsp+120h+var_E8], rax
0x180013d0e  lea     rax, [rbp+57h+var_54]
0x180013d12  mov     [rsp+120h+var_F0], rax
0x180013d17  lea     rax, [rbp+57h+var_50]
0x180013d1b  mov     [rsp+120h+var_F8], rax
0x180013d20  lea     rax, [rbp+57h+var_4C]
0x180013d24  mov     [rsp+120h+phkResult], rax
0x180013d29  mov     [rbp+57h+var_64], ebx
0x180013d2c  mov     [rbp+57h+var_60], r13d
0x180013d30  mov     [rbp+57h+var_5C], r12d
0x180013d34  mov     [rbp+57h+var_58], r15d
0x180013d38  mov     [rbp+57h+var_54], r14d
0x180013d3c  mov     [rbp+57h+var_50], esi
0x180013d3f  mov     [rbp+57h+var_4C], edi
0x180013d42  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333333333333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013d47  mov     rcx, [rbp+57h+hKey]; hKey
0x180013d4b  call    cs:__imp_RegCloseKey
0x180013d52  nop     dword ptr [rax+rax+00h]
0x180013d57  add     rsp, 0E8h
0x180013d5e  pop     r15
0x180013d60  pop     r14
0x180013d62  pop     r13
0x180013d64  pop     r12
0x180013d66  pop     rdi
0x180013d67  pop     rsi
0x180013d68  pop     rbx
0x180013d69  pop     rbp
0x180013d6a  retn
```
