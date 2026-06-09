# IPxlatPolicyMgrReadConfiguration

- ea: `0x18000dcc8`
- end: `0x18000df74`
- name: `IPxlatPolicyMgrReadConfiguration`
- size: `684`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b1a0`
- `0x1800128d0`

## callees

- `0x180001d40`
- `0x18000d2e0`
- `0x18000db48`
- `0x18000dcc8`
- `0x18000e43c`
- `0x18000e478`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000df02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000df02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ddb9`

## string_xrefs

- `0x18000dde9`: `Setting policy configuration from group policy. Name: %s, Value: %d`
- `0x18000deec`: `Failed to read GPO registry key`
- `0x18000de20`: `System\CurrentControlSet\Services\IpxlatCfgSvc`
- `0x18000de3f`: `Setting policy configuration from local preferences. Name: %s, Value: %d`
- `0x18000de64`: `Failed to read local config registry key`
- `0x18000dd19`: `Reading policy configuration`
- `0x18000de8d`: `Setting policy configuration to default. Name: %s, Value: %d`
- `0x18000df0a`: `Failed to read configuration`
- `0x18000dedd`: `Invalid Registry Setting; either GetPrefixInfoFromDns or GetPrefixInfoFromRa should be set`

## pseudocode

```c
__int64 __fastcall IPxlatPolicyMgrReadConfiguration(_DWORD *a1)
{
  int v3; // r14d
  unsigned int v4; // r15d
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned int *v6; // r12
  const WCHAR *v7; // r13
  int RegistryValue; // eax
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // [rsp+20h] [rbp-59h]
  LPCWSTR lpValue; // [rsp+30h] [rbp-49h]
  _DWORD v14[2]; // [rsp+38h] [rbp-41h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-39h]
  int v16; // [rsp+48h] [rbp-31h]
  const wchar_t *v17; // [rsp+50h] [rbp-29h]
  int v18; // [rsp+58h] [rbp-21h]
  const wchar_t *v19; // [rsp+60h] [rbp-19h]
  int v20; // [rsp+68h] [rbp-11h]
  const wchar_t *v21; // [rsp+70h] [rbp-9h]
  int v22; // [rsp+78h] [rbp-1h]

  if ( !phkResult )
    return 5023;
  if ( !a1 )
    return 87;
  IPxlatPolicyMgrLogger::LogInfo((IPxlatPolicyMgrLogger *)(phkResult + 15), L"Reading policy configuration");
  v3 = 1;
  v14[0] = 0;
  v16 = 1;
  lpValue = L"PermitNonCellularCLAT";
  v15 = L"GetPrefixInfoFromDNS";
  v17 = L"GetPrefixInfoFromRA";
  v19 = L"DisableDnsQueryNetworkServers";
  v21 = L"AutoEnable";
  v18 = 1;
  v20 = 0;
  v22 = 1;
  v12 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::GetImpl'::`2'::impl)
      + 4;
  v4 = 0;
  do
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)(phkResult + 10);
    v6 = &v14[4 * v4];
    v7 = *(const WCHAR **)&v14[4 * v4 - 2];
    EnterCriticalSection((LPCRITICAL_SECTION)phkResult + 2);
    RegistryValue = InternalReadRegistryValue(
                      phkResult,
                      L"Software\\Policies\\Microsoft\\Windows\\TCPIP\\v6Transition\\IPxlatCfgSvc",
                      v7,
                      v6);
    v9 = RegistryValue;
    if ( !RegistryValue )
    {
      IPxlatPolicyMgrLogger::LogInfo(
        (IPxlatPolicyMgrLogger *)(phkResult + 15),
        L"Setting policy configuration from group policy. Name: %s, Value: %d",
        v7,
        *v6);
      if ( v5 )
        LeaveCriticalSection(v5);
      goto LABEL_18;
    }
    if ( RegistryValue != 2 )
    {
      IPxlatPolicyMgrLogger::LogError(
        (IPxlatPolicyMgrLogger *)(phkResult + 15),
        RegistryValue,
        L"Failed to read GPO registry key");
      if ( v5 )
        LeaveCriticalSection(v5);
      v11 = v9;
LABEL_29:
      IPxlatPolicyMgrLogger::LogError((IPxlatPolicyMgrLogger *)(phkResult + 15), v9, L"Failed to read configuration");
      goto LABEL_30;
    }
    v10 = InternalReadRegistryValue(phkResult + 5, L"System\\CurrentControlSet\\Services\\IpxlatCfgSvc", v7, v6);
    v9 = v10;
    if ( v10 )
    {
      if ( v10 != 2 )
        IPxlatPolicyMgrLogger::LogError(
          (IPxlatPolicyMgrLogger *)(phkResult + 15),
          v10,
          L"Failed to read local config registry key");
    }
    else
    {
      IPxlatPolicyMgrLogger::LogInfo(
        (IPxlatPolicyMgrLogger *)(phkResult + 15),
        L"Setting policy configuration from local preferences. Name: %s, Value: %d",
        v7,
        *v6);
    }
    if ( v5 )
      LeaveCriticalSection(v5);
    if ( v9 == 2 )
    {
      IPxlatPolicyMgrLogger::LogInfo(
        (IPxlatPolicyMgrLogger *)(phkResult + 15),
        L"Setting policy configuration to default. Name: %s, Value: %d",
        *(_QWORD *)&v14[4 * v4 - 2],
        (unsigned int)v14[4 * v4]);
LABEL_18:
      v11 = 0;
      goto LABEL_20;
    }
    v11 = v9;
    if ( v9 )
      goto LABEL_29;
LABEL_20:
    ++v4;
  }
  while ( v4 < v12 );
  if ( !v11 && v14[0] && !v16 && !v18 )
  {
    v11 = 87;
    IPxlatPolicyMgrLogger::LogError(
      (IPxlatPolicyMgrLogger *)(phkResult + 15),
      87,
      L"Invalid Registry Setting; either GetPrefixInfoFromDns or GetPrefixInfoFromRa should be set");
  }
LABEL_30:
  *a1 = v14[0];
  a1[1] = v16;
  a1[2] = v18;
  a1[3] = v20;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::GetImpl'::`2'::impl) )
    v3 = v22;
  a1[4] = v3;
  return v11;
}

```

## disassembly

```asm
0x18000dcc8  push    rbp
0x18000dcca  push    rbx
0x18000dccb  push    rsi
0x18000dccc  push    rdi
0x18000dccd  push    r12
0x18000dccf  push    r13
0x18000dcd1  push    r14
0x18000dcd3  push    r15
0x18000dcd5  lea     rbp, [rsp-1Fh]
0x18000dcda  sub     rsp, 98h
0x18000dce1  mov     rax, cs:__security_cookie
0x18000dce8  xor     rax, rsp
0x18000dceb  mov     [rbp+57h+var_50], rax
0x18000dcef  mov     rsi, rcx
0x18000dcf2  mov     rcx, cs:phkResult
0x18000dcf9  test    rcx, rcx
0x18000dcfc  jnz     short loc_18000DD08
0x18000dcfe  mov     eax, 139Fh
0x18000dd03  jmp     loc_18000DF54
0x18000dd08  test    rsi, rsi
0x18000dd0b  jnz     short loc_18000DD15
0x18000dd0d  lea     eax, [rsi+57h]
0x18000dd10  jmp     loc_18000DF54
0x18000dd15  add     rcx, 78h ; 'x'; this
0x18000dd19  lea     rdx, aReadingPolicyC; "Reading policy configuration"
0x18000dd20  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000dd25  mov     r14d, 1
0x18000dd2b  mov     [rbp+57h+var_98], 0
0x18000dd32  lea     rax, aPermitnoncellu; "PermitNonCellularCLAT"
0x18000dd39  mov     [rbp+57h+var_88], r14d
0x18000dd3d  mov     [rbp+57h+lpValue], rax
0x18000dd41  lea     rax, aGetprefixinfof; "GetPrefixInfoFromDNS"
0x18000dd48  mov     [rbp+57h+var_90], rax
0x18000dd4c  lea     rax, aGetprefixinfof_1; "GetPrefixInfoFromRA"
0x18000dd53  mov     [rbp+57h+var_80], rax
0x18000dd57  lea     rax, aDisablednsquer; "DisableDnsQueryNetworkServers"
0x18000dd5e  mov     [rbp+57h+var_70], rax
0x18000dd62  lea     rax, aAutoenable; "AutoEnable"
0x18000dd69  mov     [rbp+57h+var_60], rax
0x18000dd6d  mov     [rbp+57h+var_78], r14d
0x18000dd71  mov     [rbp+57h+var_68], 0
0x18000dd78  mov     [rbp+57h+var_58], r14d
0x18000dd7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::GetImpl(void)'::`2'::impl
0x18000dd83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::__private_IsEnabled(void)
0x18000dd88  movzx   eax, al
0x18000dd8b  add     eax, 4
0x18000dd8e  mov     [rbp+57h+var_B0], eax
0x18000dd91  xor     r15d, r15d
0x18000dd94  mov     rbx, cs:phkResult
0x18000dd9b  lea     r12, [rbp+57h+var_98]
0x18000dd9f  mov     eax, r15d
0x18000dda2  add     rbx, 50h ; 'P'
0x18000dda6  shl     rax, 4
0x18000ddaa  mov     rcx, rbx; lpCriticalSection
0x18000ddad  mov     [rbp+57h+var_A8], rax
0x18000ddb1  add     r12, rax
0x18000ddb4  mov     r13, [rbp+rax+57h+lpValue]
0x18000ddb9  call    cs:__imp_EnterCriticalSection
0x18000ddbf  mov     rcx, cs:phkResult; phkResult
0x18000ddc6  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18000ddcd  mov     r9, r12
0x18000ddd0  mov     r8, r13; lpValue
0x18000ddd3  call    InternalReadRegistryValue
0x18000ddd8  mov     rcx, cs:phkResult
0x18000dddf  mov     edi, eax
0x18000dde1  test    eax, eax
0x18000dde3  jnz     short loc_18000DE13
0x18000dde5  mov     r9d, [r12]
0x18000dde9  lea     rdx, aSettingPolicyC_0; "Setting policy configuration from group"...
0x18000ddf0  add     rcx, 78h ; 'x'; this
0x18000ddf4  mov     r8, r13
0x18000ddf7  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000ddfc  test    rbx, rbx
0x18000ddff  jz      loc_18000DEAE
0x18000de05  mov     rcx, rbx; lpCriticalSection
0x18000de08  call    cs:__imp_LeaveCriticalSection
0x18000de0e  jmp     loc_18000DEAE
0x18000de13  cmp     edi, 2
0x18000de16  jnz     loc_18000DEE8
0x18000de1c  add     rcx, 28h ; '('; phkResult
0x18000de20  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ip"...
0x18000de27  mov     r9, r12
0x18000de2a  mov     r8, r13; lpValue
0x18000de2d  call    InternalReadRegistryValue
0x18000de32  mov     edi, eax
0x18000de34  test    eax, eax
0x18000de36  jnz     short loc_18000DE58
0x18000de38  mov     rcx, cs:phkResult
0x18000de3f  lea     rdx, aSettingPolicyC; "Setting policy configuration from local"...
0x18000de46  mov     r9d, [r12]
0x18000de4a  add     rcx, 78h ; 'x'; this
0x18000de4e  mov     r8, r13
0x18000de51  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000de56  jmp     short loc_18000DE76
0x18000de58  cmp     edi, 2
0x18000de5b  jz      short loc_18000DE76
0x18000de5d  mov     rcx, cs:phkResult
0x18000de64  lea     r8, aFailedToReadLo; "Failed to read local config registry ke"...
0x18000de6b  add     rcx, 78h ; 'x'; this
0x18000de6f  mov     edx, edi; unsigned int
0x18000de71  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000de76  test    rbx, rbx
0x18000de79  jz      short loc_18000DE84
0x18000de7b  mov     rcx, rbx; lpCriticalSection
0x18000de7e  call    cs:__imp_LeaveCriticalSection
0x18000de84  cmp     edi, 2
0x18000de87  jnz     short loc_18000DEB2
0x18000de89  mov     r8, [rbp+57h+var_A8]
0x18000de8d  lea     rdx, aSettingPolicyC_1; "Setting policy configuration to default"...
0x18000de94  mov     rcx, cs:phkResult
0x18000de9b  add     rcx, 78h ; 'x'; this
0x18000de9f  mov     r9d, [rbp+r8+57h+var_98]
0x18000dea4  mov     r8, [rbp+r8+57h+lpValue]
0x18000dea9  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000deae  xor     ebx, ebx
0x18000deb0  jmp     short loc_18000DEB8
0x18000deb2  mov     ebx, edi
0x18000deb4  test    edi, edi
0x18000deb6  jnz     short loc_18000DF0A
0x18000deb8  add     r15d, r14d
0x18000debb  cmp     r15d, [rbp+57h+var_B0]
0x18000debf  jb      loc_18000DD94
0x18000dec5  test    ebx, ebx
0x18000dec7  jnz     short loc_18000DF23
0x18000dec9  cmp     [rbp+57h+var_98], ebx
0x18000decc  jz      short loc_18000DF23
0x18000dece  cmp     [rbp+57h+var_88], ebx
0x18000ded1  jnz     short loc_18000DF23
0x18000ded3  cmp     [rbp+57h+var_78], ebx
0x18000ded6  jnz     short loc_18000DF23
0x18000ded8  mov     ebx, 57h ; 'W'
0x18000dedd  lea     r8, aInvalidRegistr_0; "Invalid Registry Setting; either GetPre"...
0x18000dee4  mov     edx, ebx
0x18000dee6  jmp     short loc_18000DF13
0x18000dee8  add     rcx, 78h ; 'x'; this
0x18000deec  lea     r8, aFailedToReadGp; "Failed to read GPO registry key"
0x18000def3  mov     edx, edi; unsigned int
0x18000def5  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000defa  test    rbx, rbx
0x18000defd  jz      short loc_18000DF08
0x18000deff  mov     rcx, rbx; lpCriticalSection
0x18000df02  call    cs:__imp_LeaveCriticalSection
0x18000df08  mov     ebx, edi
0x18000df0a  lea     r8, aFailedToReadCo; "Failed to read configuration"
0x18000df11  mov     edx, edi; unsigned int
0x18000df13  mov     rcx, cs:phkResult
0x18000df1a  add     rcx, 78h ; 'x'; this
0x18000df1e  call    ?LogError@IPxlatPolicyMgrLogger@@QEAAXIPEBGZZ; IPxlatPolicyMgrLogger::LogError(uint,ushort const *,...)
0x18000df23  mov     eax, [rbp+57h+var_98]
0x18000df26  mov     [rsi], eax
0x18000df28  mov     eax, [rbp+57h+var_88]
0x18000df2b  mov     [rsi+4], eax
0x18000df2e  mov     eax, [rbp+57h+var_78]
0x18000df31  mov     [rsi+8], eax
0x18000df34  mov     eax, [rbp+57h+var_68]
0x18000df37  mov     [rsi+0Ch], eax
0x18000df3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::GetImpl(void)'::`2'::impl
0x18000df41  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_AutoEnable>::__private_IsEnabled(void)
0x18000df46  test    al, al
0x18000df48  jz      short loc_18000DF4E
0x18000df4a  mov     r14d, [rbp+57h+var_58]
0x18000df4e  mov     [rsi+10h], r14d
0x18000df52  mov     eax, ebx
0x18000df54  mov     rcx, [rbp+57h+var_50]
0x18000df58  xor     rcx, rsp; StackCookie
0x18000df5b  call    __security_check_cookie
0x18000df60  add     rsp, 98h
0x18000df67  pop     r15
0x18000df69  pop     r14
0x18000df6b  pop     r13
0x18000df6d  pop     r12
0x18000df6f  pop     rdi
0x18000df70  pop     rsi
0x18000df71  pop     rbx
0x18000df72  pop     rbp
0x18000df73  retn
```
