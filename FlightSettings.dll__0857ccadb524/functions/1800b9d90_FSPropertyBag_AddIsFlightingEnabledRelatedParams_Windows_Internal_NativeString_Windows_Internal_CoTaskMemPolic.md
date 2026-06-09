# FSPropertyBag::AddIsFlightingEnabledRelatedParams(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x1800b9d90`
- end: `0x1800ba1fc`
- name: `?AddIsFlightingEnabledRelatedParams@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `1132`
- prototype: `__int64 __fastcall(FSPropertyBag *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bb5ec`

## callees

- `0x18000cc8c`
- `0x1800871f4`
- `0x180087390`
- `0x180089c18`
- `0x18008ae24`
- `0x1800925c4`
- `0x1800b9d90`
- `0x1800c0bf0`
- `0x1800c0c54`
- `0x1800c0d58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9e50`
- `DiagnosticDataSettings!TelGetMaximumAllowedTelemetryLevel` at `0x1800b9f44`
- `DiagnosticDataSettings!TelGetMaximumAllowedTelemetryLevel` at `0x1800b9f44`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x1800b9ef6`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x1800b9ef6`

## string_xrefs

- `0x1800ba0b6`: `Update`
- `0x1800ba0fd`: `configSettingMdmPolicy`
- `0x1800ba131`: `configSettingMdmPolicy`
- `0x1800ba15b`: `configExperimentMdmPolicy`
- `0x1800ba18f`: `configExperimentMdmPolicy`
- `0x1800b9df0`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800ba1b2`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800ba1d2`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
__int64 __fastcall FSPropertyBag::AddIsFlightingEnabledRelatedParams(FSPropertyBag *this, __int64 a2)
{
  unsigned int IsRetailOS; // eax
  __int64 active; // rbx
  int updated; // r14d
  __int64 v7; // rdx
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-30h]
  int v13; // [rsp+40h] [rbp-10h] BYREF
  int v14[3]; // [rsp+44h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int v16; // [rsp+90h] [rbp+40h] BYREF
  int v17; // [rsp+98h] [rbp+48h] BYREF

  LOWORD(v16) = 0;
  IsRetailOS = FlightSettingsAPICommon::IsRetailOS((__int16 *)&v16);
  v12 = (__int16)v16;
  LODWORD(active) = IsRetailOS;
  updated = FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(this, a2, L"isRetail", IsRetailOS);
  if ( updated < 0 )
  {
    v7 = 928;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)updated,
      v12);
    return (unsigned int)updated;
  }
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"bcdBootMgrState")
    || FSPropertyBag::ShouldIncludeProperty(this, L"bcdOsInstanceState") )
  {
    v13 = 0;
    v16 = 0;
    if ( CFlightingAdmin::GetFlightSigningBcdSettings(&v13, (int *)&v16) )
      LODWORD(active) = 0;
    else
      LODWORD(active) = GetLastError();
    v12 = v16;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"bcdBootMgrState", (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 935;
      goto LABEL_3;
    }
    v12 = v13;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"bcdOsInstanceState", (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 936;
      goto LABEL_3;
    }
  }
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"currentTelemetryLevelInt")
    || FSPropertyBag::ShouldIncludeProperty(this, L"telemetrySettingAuthorityInt") )
  {
    v13 = 0;
    v16 = 0;
    active = (unsigned int)TelEvaluateActiveSettingAuthority(&v13, &v16);
    v12 = v13;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"currentTelemetryLevelInt", active);
    if ( updated < 0 )
    {
      v7 = 945;
      goto LABEL_3;
    }
    if ( (int)active < 0 )
      goto LABEL_22;
    v9 = v16;
    if ( v16 > 1 )
      goto LABEL_23;
    v14[0] = 0;
    LODWORD(active) = TelGetMaximumAllowedTelemetryLevel(v14);
    if ( (int)active < 0 || v14[0] <= v13 )
    {
LABEL_22:
      v9 = v16;
    }
    else
    {
      v9 = 2;
      v16 = 2;
    }
LABEL_23:
    v12 = v9;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(
                this,
                a2,
                L"telemetrySettingAuthorityInt",
                (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 959;
      goto LABEL_3;
    }
  }
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"codeIntegrityInformationUlong") )
  {
    v16 = 0;
    LODWORD(active) = FlightSettingsAPICommon::GetCodeIntegrityInformation(&v16);
    v12 = v16;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(
                this,
                a2,
                L"codeIntegrityInformationUlong",
                (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 966;
      goto LABEL_3;
    }
  }
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"controlBuildFlightingiIcense") )
  {
    LOBYTE(v16) = 0;
    LODWORD(active) = FSPolicyReader::IsControlBuildFlightLicensePresent((bool *)&v16);
    v12 = (unsigned __int8)v16;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(
                this,
                a2,
                L"controlBuildFlightingiIcense",
                (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 973;
      goto LABEL_3;
    }
  }
  v17 = 0;
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"allowBuildPreviewMdmPolicy") )
  {
    LODWORD(active) = FSPolicyReader::GetMdmPolicy(L"AllowBuildPreview", L"System", &v17);
    v12 = v17;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(
                this,
                a2,
                L"allowBuildPreviewMdmPolicy",
                (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 981;
      goto LABEL_3;
    }
  }
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"managePreviewBuildsMdmPolicy") )
  {
    LODWORD(active) = FSPolicyReader::GetMdmPolicy(L"ManagePreviewBuilds", L"Update", &v17);
    v12 = v17;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(
                this,
                a2,
                L"managePreviewBuildsMdmPolicy",
                (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 988;
      goto LABEL_3;
    }
  }
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"configSettingMdmPolicy") )
  {
    LODWORD(active) = FSPolicyReader::GetMdmPolicy(L"AllowExperimentation", L"System", &v17);
    v12 = v17;
    updated = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(this, a2, L"configSettingMdmPolicy", (unsigned int)active);
    if ( updated < 0 )
    {
      v7 = 994;
      goto LABEL_3;
    }
  }
  if ( FSPropertyBag::ShouldIncludeProperty(this, L"configExperimentMdmPolicy")
    && (LODWORD(active) = FSPolicyReader::GetMdmPolicy(L"AllowExperimentation", L"System", &v17),
        v12 = v17,
        v10 = FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(
                this,
                a2,
                L"configExperimentMdmPolicy",
                (unsigned int)active),
        v11 = v10,
        v10 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E8,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v10,
      v12);
    return v11;
  }
  else
  {
    if ( (int)active < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3EB,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)active,
        v12);
    return (unsigned int)active;
  }
}

```

## disassembly

```asm
0x1800b9d90  mov     [rsp-28h+arg_0], rbx
0x1800b9d95  push    rbp
0x1800b9d96  push    rsi
0x1800b9d97  push    rdi
0x1800b9d98  push    r14
0x1800b9d9a  push    r15
0x1800b9d9c  mov     rbp, rsp
0x1800b9d9f  sub     rsp, 50h
0x1800b9da3  mov     rdi, rcx
0x1800b9da6  xor     r15d, r15d
0x1800b9da9  lea     rcx, [rbp+arg_10]; __int16 *
0x1800b9dad  mov     word ptr [rbp+arg_10], r15w
0x1800b9db2  mov     rsi, rdx
0x1800b9db5  call    ?IsRetailOS@FlightSettingsAPICommon@@SAJPEAF@Z; FlightSettingsAPICommon::IsRetailOS(short *)
0x1800b9dba  movsx   r8d, word ptr [rbp+arg_10]
0x1800b9dbf  mov     r9d, eax
0x1800b9dc2  mov     [rsp+50h+var_20], r15b
0x1800b9dc7  mov     rdx, rsi
0x1800b9dca  mov     [rsp+50h+var_30], r8d; int
0x1800b9dcf  mov     rcx, rdi
0x1800b9dd2  lea     r8, aIsretail; "isRetail"
0x1800b9dd9  mov     ebx, eax
0x1800b9ddb  call    ?UpdateParamsWithBooleanBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJH1_N@Z; FSPropertyBag::UpdateParamsWithBooleanBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,int,ushort const *,bool)
0x1800b9de0  mov     r14d, eax
0x1800b9de3  test    eax, eax
0x1800b9de5  jns     short loc_1800B9E07
0x1800b9de7  mov     edx, 3A0h; void *
0x1800b9dec  mov     rcx, [rbp+28h]; this
0x1800b9df0  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800b9df7  mov     r9d, r14d; char *
0x1800b9dfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b9dff  mov     eax, r14d
0x1800b9e02  jmp     loc_1800BA1E8
0x1800b9e07  lea     rdx, aBcdbootmgrstat; "bcdBootMgrState"
0x1800b9e0e  mov     rcx, rdi; this
0x1800b9e11  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800b9e16  test    al, al
0x1800b9e18  jnz     short loc_1800B9E31
0x1800b9e1a  lea     rdx, aBcdosinstances; "bcdOsInstanceState"
0x1800b9e21  mov     rcx, rdi; this
0x1800b9e24  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800b9e29  test    al, al
0x1800b9e2b  jz      loc_1800B9EBC
0x1800b9e31  lea     rdx, [rbp+arg_10]; int *
0x1800b9e35  mov     [rbp+var_10], r15d
0x1800b9e39  lea     rcx, [rbp+var_10]; int *
0x1800b9e3d  mov     [rbp+arg_10], r15d
0x1800b9e41  call    ?GetFlightSigningBcdSettings@CFlightingAdmin@@SAHPEAH0@Z; CFlightingAdmin::GetFlightSigningBcdSettings(int *,int *)
0x1800b9e46  cmp     eax, 1
0x1800b9e49  jnz     short loc_1800B9E50
0x1800b9e4b  mov     ebx, r15d
0x1800b9e4e  jmp     short loc_1800B9E58
0x1800b9e50  call    cs:__imp_GetLastError
0x1800b9e56  mov     ebx, eax
0x1800b9e58  mov     eax, [rbp+arg_10]
0x1800b9e5b  lea     r8, aBcdbootmgrstat; "bcdBootMgrState"
0x1800b9e62  mov     [rsp+50h+var_28], r15b
0x1800b9e67  mov     r9d, ebx
0x1800b9e6a  mov     rdx, rsi
0x1800b9e6d  mov     [rsp+50h+var_30], eax
0x1800b9e71  mov     rcx, rdi
0x1800b9e74  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800b9e79  mov     r14d, eax
0x1800b9e7c  test    eax, eax
0x1800b9e7e  jns     short loc_1800B9E8A
0x1800b9e80  mov     edx, 3A7h
0x1800b9e85  jmp     loc_1800B9DEC
0x1800b9e8a  mov     eax, [rbp+var_10]
0x1800b9e8d  lea     r8, aBcdosinstances; "bcdOsInstanceState"
0x1800b9e94  mov     [rsp+50h+var_28], r15b
0x1800b9e99  mov     r9d, ebx
0x1800b9e9c  mov     rdx, rsi
0x1800b9e9f  mov     [rsp+50h+var_30], eax
0x1800b9ea3  mov     rcx, rdi
0x1800b9ea6  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800b9eab  mov     r14d, eax
0x1800b9eae  test    eax, eax
0x1800b9eb0  jns     short loc_1800B9EBC
0x1800b9eb2  mov     edx, 3A8h
0x1800b9eb7  jmp     loc_1800B9DEC
0x1800b9ebc  lea     rdx, aCurrenttelemet; "currentTelemetryLevelInt"
0x1800b9ec3  mov     rcx, rdi; this
0x1800b9ec6  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800b9ecb  test    al, al
0x1800b9ecd  jnz     short loc_1800B9EE6
0x1800b9ecf  lea     rdx, aTelemetrysetti; "telemetrySettingAuthorityInt"
0x1800b9ed6  mov     rcx, rdi; this
0x1800b9ed9  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800b9ede  test    al, al
0x1800b9ee0  jz      loc_1800B9F94
0x1800b9ee6  lea     rdx, [rbp+arg_10]
0x1800b9eea  mov     [rbp+var_10], r15d
0x1800b9eee  lea     rcx, [rbp+var_10]
0x1800b9ef2  mov     [rbp+arg_10], r15d
0x1800b9ef6  call    cs:__imp_TelEvaluateActiveSettingAuthority
0x1800b9efc  mov     [rsp+50h+var_28], r15b
0x1800b9f01  lea     r8, aCurrenttelemet; "currentTelemetryLevelInt"
0x1800b9f08  mov     ebx, eax
0x1800b9f0a  mov     rdx, rsi
0x1800b9f0d  mov     eax, [rbp+var_10]
0x1800b9f10  mov     r9d, ebx
0x1800b9f13  mov     rcx, rdi
0x1800b9f16  mov     [rsp+50h+var_30], eax
0x1800b9f1a  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800b9f1f  mov     r14d, eax
0x1800b9f22  test    eax, eax
0x1800b9f24  jns     short loc_1800B9F30
0x1800b9f26  mov     edx, 3B1h
0x1800b9f2b  jmp     loc_1800B9DEC
0x1800b9f30  test    ebx, ebx
0x1800b9f32  js      short loc_1800B9F62
0x1800b9f34  mov     eax, [rbp+arg_10]
0x1800b9f37  cmp     eax, 1
0x1800b9f3a  ja      short loc_1800B9F65
0x1800b9f3c  lea     rcx, [rbp+var_C]
0x1800b9f40  mov     [rbp+var_C], r15d
0x1800b9f44  call    cs:__imp_TelGetMaximumAllowedTelemetryLevel
0x1800b9f4a  mov     ebx, eax
0x1800b9f4c  test    eax, eax
0x1800b9f4e  js      short loc_1800B9F62
0x1800b9f50  mov     eax, [rbp+var_10]
0x1800b9f53  cmp     [rbp+var_C], eax
0x1800b9f56  jle     short loc_1800B9F62
0x1800b9f58  mov     eax, 2
0x1800b9f5d  mov     [rbp+arg_10], eax
0x1800b9f60  jmp     short loc_1800B9F65
0x1800b9f62  mov     eax, [rbp+arg_10]
0x1800b9f65  mov     [rsp+50h+var_28], r15b
0x1800b9f6a  lea     r8, aTelemetrysetti; "telemetrySettingAuthorityInt"
0x1800b9f71  mov     r9d, ebx
0x1800b9f74  mov     [rsp+50h+var_30], eax
0x1800b9f78  mov     rdx, rsi
0x1800b9f7b  mov     rcx, rdi
0x1800b9f7e  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800b9f83  mov     r14d, eax
0x1800b9f86  test    eax, eax
0x1800b9f88  jns     short loc_1800B9F94
0x1800b9f8a  mov     edx, 3BFh
0x1800b9f8f  jmp     loc_1800B9DEC
0x1800b9f94  lea     rdx, aCodeintegrityi; "codeIntegrityInformationUlong"
0x1800b9f9b  mov     rcx, rdi; this
0x1800b9f9e  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800b9fa3  test    al, al
0x1800b9fa5  jz      short loc_1800B9FE8
0x1800b9fa7  lea     rcx, [rbp+arg_10]; unsigned int *
0x1800b9fab  mov     [rbp+arg_10], r15d
0x1800b9faf  call    ?GetCodeIntegrityInformation@FlightSettingsAPICommon@@SAJPEAK@Z; FlightSettingsAPICommon::GetCodeIntegrityInformation(ulong *)
0x1800b9fb4  mov     ebx, eax
0x1800b9fb6  mov     [rsp+50h+var_28], r15b
0x1800b9fbb  mov     eax, [rbp+arg_10]
0x1800b9fbe  lea     r8, aCodeintegrityi; "codeIntegrityInformationUlong"
0x1800b9fc5  mov     r9d, ebx
0x1800b9fc8  mov     [rsp+50h+var_30], eax
0x1800b9fcc  mov     rdx, rsi
0x1800b9fcf  mov     rcx, rdi
0x1800b9fd2  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800b9fd7  mov     r14d, eax
0x1800b9fda  test    eax, eax
0x1800b9fdc  jns     short loc_1800B9FE8
0x1800b9fde  mov     edx, 3C6h
0x1800b9fe3  jmp     loc_1800B9DEC
0x1800b9fe8  lea     rdx, aControlbuildfl; "controlBuildFlightingiIcense"
0x1800b9fef  mov     rcx, rdi; this
0x1800b9ff2  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800b9ff7  test    al, al
0x1800b9ff9  jz      short loc_1800BA03D
0x1800b9ffb  lea     rcx, [rbp+arg_10]; bool *
0x1800b9fff  mov     byte ptr [rbp+arg_10], r15b
0x1800ba003  call    ?IsControlBuildFlightLicensePresent@FSPolicyReader@@SAJPEA_N@Z; FSPolicyReader::IsControlBuildFlightLicensePresent(bool *)
0x1800ba008  mov     ebx, eax
0x1800ba00a  mov     [rsp+50h+var_28], r15b
0x1800ba00f  movzx   eax, byte ptr [rbp+arg_10]
0x1800ba013  lea     r8, aControlbuildfl; "controlBuildFlightingiIcense"
0x1800ba01a  mov     r9d, ebx
0x1800ba01d  mov     [rsp+50h+var_30], eax
0x1800ba021  mov     rdx, rsi
0x1800ba024  mov     rcx, rdi
0x1800ba027  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba02c  mov     r14d, eax
0x1800ba02f  test    eax, eax
0x1800ba031  jns     short loc_1800BA03D
0x1800ba033  mov     edx, 3CDh
0x1800ba038  jmp     loc_1800B9DEC
0x1800ba03d  lea     rdx, aAllowbuildprev_0; "allowBuildPreviewMdmPolicy"
0x1800ba044  mov     [rbp+arg_18], r15d
0x1800ba048  mov     rcx, rdi; this
0x1800ba04b  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba050  test    al, al
0x1800ba052  jz      short loc_1800BA09F
0x1800ba054  lea     r8, [rbp+arg_18]; int *
0x1800ba058  lea     rdx, aSystem; "System"
0x1800ba05f  lea     rcx, aAllowbuildprev; "AllowBuildPreview"
0x1800ba066  call    ?GetMdmPolicy@FSPolicyReader@@SAJPEBG0PEAH@Z; FSPolicyReader::GetMdmPolicy(ushort const *,ushort const *,int *)
0x1800ba06b  mov     ebx, eax
0x1800ba06d  mov     [rsp+50h+var_28], r15b
0x1800ba072  mov     eax, [rbp+arg_18]
0x1800ba075  lea     r8, aAllowbuildprev_0; "allowBuildPreviewMdmPolicy"
0x1800ba07c  mov     r9d, ebx
0x1800ba07f  mov     [rsp+50h+var_30], eax
0x1800ba083  mov     rdx, rsi
0x1800ba086  mov     rcx, rdi
0x1800ba089  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba08e  mov     r14d, eax
0x1800ba091  test    eax, eax
0x1800ba093  jns     short loc_1800BA09F
0x1800ba095  mov     edx, 3D5h
0x1800ba09a  jmp     loc_1800B9DEC
0x1800ba09f  lea     rdx, aManagepreviewb; "managePreviewBuildsMdmPolicy"
0x1800ba0a6  mov     rcx, rdi; this
0x1800ba0a9  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba0ae  test    al, al
0x1800ba0b0  jz      short loc_1800BA0FD
0x1800ba0b2  lea     r8, [rbp+arg_18]; int *
0x1800ba0b6  lea     rdx, aUpdate; "Update"
0x1800ba0bd  lea     rcx, aManagepreviewb_0; "ManagePreviewBuilds"
0x1800ba0c4  call    ?GetMdmPolicy@FSPolicyReader@@SAJPEBG0PEAH@Z; FSPolicyReader::GetMdmPolicy(ushort const *,ushort const *,int *)
0x1800ba0c9  mov     ebx, eax
0x1800ba0cb  mov     [rsp+50h+var_28], r15b
0x1800ba0d0  mov     eax, [rbp+arg_18]
0x1800ba0d3  lea     r8, aManagepreviewb; "managePreviewBuildsMdmPolicy"
0x1800ba0da  mov     r9d, ebx
0x1800ba0dd  mov     [rsp+50h+var_30], eax
0x1800ba0e1  mov     rdx, rsi
0x1800ba0e4  mov     rcx, rdi
0x1800ba0e7  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba0ec  mov     r14d, eax
0x1800ba0ef  test    eax, eax
0x1800ba0f1  jns     short loc_1800BA0FD
0x1800ba0f3  mov     edx, 3DCh
0x1800ba0f8  jmp     loc_1800B9DEC
0x1800ba0fd  lea     rdx, aConfigsettingm; "configSettingMdmPolicy"
0x1800ba104  mov     rcx, rdi; this
0x1800ba107  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba10c  test    al, al
0x1800ba10e  jz      short loc_1800BA15B
0x1800ba110  lea     r8, [rbp+arg_18]; int *
0x1800ba114  lea     rdx, aSystem; "System"
0x1800ba11b  lea     rcx, aAllowexperimen; "AllowExperimentation"
0x1800ba122  call    ?GetMdmPolicy@FSPolicyReader@@SAJPEBG0PEAH@Z; FSPolicyReader::GetMdmPolicy(ushort const *,ushort const *,int *)
0x1800ba127  mov     ebx, eax
0x1800ba129  mov     [rsp+50h+var_28], r15b
0x1800ba12e  mov     eax, [rbp+arg_18]
0x1800ba131  lea     r8, aConfigsettingm; "configSettingMdmPolicy"
0x1800ba138  mov     r9d, ebx
0x1800ba13b  mov     [rsp+50h+var_30], eax
0x1800ba13f  mov     rdx, rsi
0x1800ba142  mov     rcx, rdi
0x1800ba145  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba14a  mov     r14d, eax
0x1800ba14d  test    eax, eax
0x1800ba14f  jns     short loc_1800BA15B
0x1800ba151  mov     edx, 3E2h
0x1800ba156  jmp     loc_1800B9DEC
0x1800ba15b  lea     rdx, aConfigexperime; "configExperimentMdmPolicy"
0x1800ba162  mov     rcx, rdi; this
0x1800ba165  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800ba16a  test    al, al
0x1800ba16c  jz      short loc_1800BA1CA
0x1800ba16e  lea     r8, [rbp+arg_18]; int *
0x1800ba172  lea     rdx, aSystem; "System"
0x1800ba179  lea     rcx, aAllowexperimen; "AllowExperimentation"
0x1800ba180  call    ?GetMdmPolicy@FSPolicyReader@@SAJPEBG0PEAH@Z; FSPolicyReader::GetMdmPolicy(ushort const *,ushort const *,int *)
0x1800ba185  mov     ebx, eax
0x1800ba187  mov     [rsp+50h+var_28], r15b
0x1800ba18c  mov     eax, [rbp+arg_18]
0x1800ba18f  lea     r8, aConfigexperime; "configExperimentMdmPolicy"
0x1800ba196  mov     r9d, ebx
0x1800ba199  mov     [rsp+50h+var_30], eax; int
0x1800ba19d  mov     rdx, rsi
0x1800ba1a0  mov     rcx, rdi
0x1800ba1a3  call    ?UpdateParamsWithDWORDBasedOnHr@FSPropertyBag@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@PEBGJK_N@Z; FSPropertyBag::UpdateParamsWithDWORDBasedOnHr(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ushort const *,long,ulong,bool)
0x1800ba1a8  mov     edi, eax
0x1800ba1aa  test    eax, eax
0x1800ba1ac  jns     short loc_1800BA1CA
0x1800ba1ae  mov     rcx, [rbp+28h]; this
0x1800ba1b2  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800ba1b9  mov     r9d, eax; char *
0x1800ba1bc  mov     edx, 3E8h; void *
0x1800ba1c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba1c6  mov     eax, edi
0x1800ba1c8  jmp     short loc_1800BA1E8
0x1800ba1ca  test    ebx, ebx
0x1800ba1cc  jns     short loc_1800BA1E6
0x1800ba1ce  mov     rcx, [rbp+28h]; this
0x1800ba1d2  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800ba1d9  mov     r9d, ebx; char *
0x1800ba1dc  mov     edx, 3EBh; void *
0x1800ba1e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba1e6  mov     eax, ebx
0x1800ba1e8  mov     rbx, [rsp+50h+arg_0]
0x1800ba1f0  add     rsp, 50h
0x1800ba1f4  pop     r15
0x1800ba1f6  pop     r14
0x1800ba1f8  pop     rdi
0x1800ba1f9  pop     rsi
0x1800ba1fa  pop     rbp
0x1800ba1fb  retn
```
