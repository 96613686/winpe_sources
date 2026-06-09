# AutoPilotGetOobeSettingsOverride

- ea: `0x180012720`
- end: `0x18001285b`
- name: `AutoPilotGetOobeSettingsOverride`
- size: `315`
- prototype: `__int64 __fastcall(unsigned int, BOOL *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800105f4`
- `0x180012720`
- `0x1800132d8`
- `0x180018430`
- `0x18001e204`
- `0x18001e260`
- `0x18001e514`

## string_xrefs

- `0x18001282a`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x1800127dd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x18001281a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x1800127be`: `CloudAssignedOobeConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AutoPilotGetOobeSettingsOverride(unsigned int a1, BOOL *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rcx
  unsigned int v5; // ebx
  const wchar_t *v6; // r9
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  BOOL v9; // eax
  int DwordPolicy; // eax
  unsigned int v11; // edi
  int IsSet; // eax
  unsigned int v14[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v16; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+38h] BYREF

  v2 = (int)a1;
  v17 = 0;
  v5 = Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(a1, &v17);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      if ( (unsigned int)(v2 - 1) > 0xB )
        v6 = L"AUTOPILOT_OOBE_SETTINGS_INVALID";
      else
        v6 = off_180030370[v2];
      McTemplateU0dz_EventWriteTransfer(v4, AutopilotGetOobeSettingsOverrideFailed, v5, v6);
    }
    v7 = v5;
    v8 = 193;
    goto LABEL_15;
  }
  v16 = 0;
  if ( (unsigned __int8)Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsWindowsPatchUXOverriden(v17, &v16) )
  {
    v9 = v16 == 1;
    goto LABEL_18;
  }
  v14[0] = 0;
  DwordPolicy = Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(L"CloudAssignedOobeConfig", v14);
  v5 = -2147023727;
  v11 = DwordPolicy;
  if ( DwordPolicy == -2147023727 )
  {
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)v5,
      v14[0]);
    return v5;
  }
  if ( DwordPolicy < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)(unsigned int)DwordPolicy,
      v14[0]);
    v5 = v11;
    goto LABEL_16;
  }
  LOBYTE(v16) = 0;
  IsSet = Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetOobeConfigIsSet(v17, v14[0], &v16);
  v5 = IsSet;
  if ( IsSet < 0 )
  {
    v7 = (unsigned int)IsSet;
    v8 = 212;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)v7,
      v14[0]);
    goto LABEL_16;
  }
  v9 = (_BYTE)v16 != 0;
LABEL_18:
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x180012720  mov     [rsp-18h+arg_0], rbx
0x180012725  push    rbp
0x180012726  push    rsi
0x180012727  push    rdi
0x180012728  mov     rbp, rsp
0x18001272b  sub     rsp, 30h
0x18001272f  movsxd  rdi, ecx
0x180012732  mov     rsi, rdx
0x180012735  mov     ecx, edi
0x180012737  mov     [rbp+arg_18], 0
0x18001273e  lea     rdx, [rbp+arg_18]
0x180012742  call    ?MapAutoPilotConfigToZtpConfig@AutopilotPolicyInternal@Autopilot@Windows@Microsoft@@SAJW4AUTOPILOT_OOBE_SETTINGS@@PEAW4ZTP_CONFIG@@@Z; Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(AUTOPILOT_OOBE_SETTINGS,ZTP_CONFIG *)
0x180012747  mov     ebx, eax
0x180012749  test    eax, eax
0x18001274b  jns     short loc_18001278E
0x18001274d  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180012754  jz      short loc_180012781
0x180012756  lea     eax, [rdi-1]
0x180012759  cmp     eax, 0Bh
0x18001275c  ja      short loc_18001276B
0x18001275e  lea     r9, off_180030370; "AUTOPILOT_OOBE_SETTINGS_INVALID"
0x180012765  mov     r9, [r9+rdi*8]
0x180012769  jmp     short loc_180012772
0x18001276b  mov     r9, cs:off_180030370; "AUTOPILOT_OOBE_SETTINGS_INVALID"
0x180012772  mov     r8d, ebx
0x180012775  lea     rdx, AutopilotGetOobeSettingsOverrideFailed
0x18001277c  call    McTemplateU0dz_EventWriteTransfer
0x180012781  mov     r9d, ebx
0x180012784  mov     edx, 0C1h
0x180012789  jmp     loc_180012816
0x18001278e  mov     ecx, [rbp+arg_18]
0x180012791  lea     rdx, [rbp+arg_10]
0x180012795  mov     [rbp+arg_10], 0
0x18001279c  call    ?IsWindowsPatchUXOverriden@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NW4ZTP_CONFIG@@AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsWindowsPatchUXOverriden(ZTP_CONFIG,ulong &)
0x1800127a1  test    al, al
0x1800127a3  jz      short loc_1800127B3
0x1800127a5  xor     eax, eax
0x1800127a7  cmp     [rbp+arg_10], 1
0x1800127ab  setz    al
0x1800127ae  jmp     loc_18001284A
0x1800127b3  lea     rdx, [rbp+var_10]; unsigned int *
0x1800127b7  mov     [rbp+var_10], 0
0x1800127be  lea     rcx, aCloudassignedo; "CloudAssignedOobeConfig"
0x1800127c5  call    ?GetDwordPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAK@Z; Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(ushort const *,ulong *)
0x1800127ca  mov     ebx, 80070491h
0x1800127cf  mov     edi, eax
0x1800127d1  cmp     eax, ebx
0x1800127d3  jz      short loc_180012826
0x1800127d5  test    eax, eax
0x1800127d7  jns     short loc_1800127F5
0x1800127d9  mov     rcx, [rbp+18h]; this
0x1800127dd  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800127e4  mov     r9d, eax; char *
0x1800127e7  mov     edx, 0D1h; void *
0x1800127ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127f1  mov     ebx, edi
0x1800127f3  jmp     short loc_180012826
0x1800127f5  mov     edx, [rbp+var_10]
0x1800127f8  lea     r8, [rbp+arg_10]
0x1800127fc  mov     ecx, [rbp+arg_18]
0x1800127ff  mov     byte ptr [rbp+arg_10], 0
0x180012803  call    ?GetOobeConfigIsSet@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJW4ZTP_CONFIG@@KAEA_N@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetOobeConfigIsSet(ZTP_CONFIG,ulong,bool &)
0x180012808  mov     ebx, eax
0x18001280a  test    eax, eax
0x18001280c  jns     short loc_180012842
0x18001280e  mov     r9d, eax; char *
0x180012811  mov     edx, 0D4h; void *
0x180012816  mov     rcx, [rbp+18h]; this
0x18001281a  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012826  mov     rcx, [rbp+18h]; this
0x18001282a  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012831  mov     r9d, ebx; char *
0x180012834  mov     edx, 80h; void *
0x180012839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001283e  mov     eax, ebx
0x180012840  jmp     short loc_18001284E
0x180012842  xor     eax, eax
0x180012844  cmp     byte ptr [rbp+arg_10], al
0x180012847  setnz   al
0x18001284a  mov     [rsi], eax
0x18001284c  xor     eax, eax
0x18001284e  mov     rbx, [rsp+30h+arg_0]
0x180012853  add     rsp, 30h
0x180012857  pop     rdi
0x180012858  pop     rsi
0x180012859  pop     rbp
0x18001285a  retn
```
