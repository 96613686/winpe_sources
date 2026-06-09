# AutoPilotGetOobeSettingsOverride

- ea: `0x180012960`
- end: `0x180012a9c`
- name: `AutoPilotGetOobeSettingsOverride`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180010764`
- `0x180012960`
- `0x180013580`
- `0x1800189a4`
- `0x18001ea4c`
- `0x18001eaa8`
- `0x18001ed68`

## string_xrefs

- `0x180012a6a`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`
- `0x180012a1d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180012a5a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x1800129fe`: `CloudAssignedOobeConfig`

## pseudocode

```c
__int64 __fastcall AutoPilotGetOobeSettingsOverride(int a1, BOOL *a2)
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
  unsigned int v16; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+38h] BYREF

  v2 = a1;
  v17 = 0;
  v5 = Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(a1, &v17);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      if ( (unsigned int)(v2 - 1) > 0xB )
        v6 = L"AUTOPILOT_OOBE_SETTINGS_INVALID";
      else
        v6 = off_180031370[v2];
      McTemplateU0dz_EventWriteTransfer(v4, AutopilotGetOobeSettingsOverrideFailed, v5, v6);
    }
    v7 = v5;
    v8 = 193;
    goto LABEL_15;
  }
  v16 = 0;
  if ( Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsWindowsPatchUXOverriden(v17, &v16) )
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
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)v5);
    return v5;
  }
  if ( DwordPolicy < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)(unsigned int)DwordPolicy);
    v5 = v11;
    goto LABEL_16;
  }
  LOBYTE(v16) = 0;
  IsSet = Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetOobeConfigIsSet((HKEY)v17, v14[0], &v16);
  v5 = IsSet;
  if ( IsSet < 0 )
  {
    v7 = (unsigned int)IsSet;
    v8 = 212;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)v7);
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
0x180012960  mov     [rsp-18h+arg_0], rbx
0x180012965  push    rbp
0x180012966  push    rsi
0x180012967  push    rdi
0x180012968  mov     rbp, rsp
0x18001296b  sub     rsp, 30h
0x18001296f  movsxd  rdi, ecx
0x180012972  mov     rsi, rdx
0x180012975  mov     ecx, edi
0x180012977  mov     [rbp+arg_18], 0
0x18001297e  lea     rdx, [rbp+arg_18]
0x180012982  call    ?MapAutoPilotConfigToZtpConfig@AutopilotPolicyInternal@Autopilot@Windows@Microsoft@@SAJW4AUTOPILOT_OOBE_SETTINGS@@PEAW4ZTP_CONFIG@@@Z; Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(AUTOPILOT_OOBE_SETTINGS,ZTP_CONFIG *)
0x180012987  mov     ebx, eax
0x180012989  test    eax, eax
0x18001298b  jns     short loc_1800129CE
0x18001298d  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180012994  jz      short loc_1800129C1
0x180012996  lea     eax, [rdi-1]
0x180012999  cmp     eax, 0Bh
0x18001299c  ja      short loc_1800129AB
0x18001299e  lea     r9, off_180031370; "AUTOPILOT_OOBE_SETTINGS_INVALID"
0x1800129a5  mov     r9, [r9+rdi*8]
0x1800129a9  jmp     short loc_1800129B2
0x1800129ab  mov     r9, cs:off_180031370; "AUTOPILOT_OOBE_SETTINGS_INVALID"
0x1800129b2  mov     r8d, ebx
0x1800129b5  lea     rdx, AutopilotGetOobeSettingsOverrideFailed
0x1800129bc  call    McTemplateU0dz_EventWriteTransfer
0x1800129c1  mov     r9d, ebx
0x1800129c4  mov     edx, 0C1h
0x1800129c9  jmp     loc_180012A56
0x1800129ce  mov     ecx, [rbp+arg_18]
0x1800129d1  lea     rdx, [rbp+arg_10]
0x1800129d5  mov     [rbp+arg_10], 0
0x1800129dc  call    ?IsWindowsPatchUXOverriden@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NW4ZTP_CONFIG@@AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsWindowsPatchUXOverriden(ZTP_CONFIG,ulong &)
0x1800129e1  test    al, al
0x1800129e3  jz      short loc_1800129F3
0x1800129e5  xor     eax, eax
0x1800129e7  cmp     [rbp+arg_10], 1
0x1800129eb  setz    al
0x1800129ee  jmp     loc_180012A8A
0x1800129f3  lea     rdx, [rbp+var_10]; unsigned int *
0x1800129f7  mov     [rbp+var_10], 0
0x1800129fe  lea     rcx, aCloudassignedo; "CloudAssignedOobeConfig"
0x180012a05  call    ?GetDwordPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAK@Z; Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(ushort const *,ulong *)
0x180012a0a  mov     ebx, 80070491h
0x180012a0f  mov     edi, eax
0x180012a11  cmp     eax, ebx
0x180012a13  jz      short loc_180012A66
0x180012a15  test    eax, eax
0x180012a17  jns     short loc_180012A35
0x180012a19  mov     rcx, [rbp+18h]; this
0x180012a1d  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012a24  mov     r9d, eax; char *
0x180012a27  mov     edx, 0D1h; void *
0x180012a2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a31  mov     ebx, edi
0x180012a33  jmp     short loc_180012A66
0x180012a35  mov     edx, [rbp+var_10]
0x180012a38  lea     r8, [rbp+arg_10]
0x180012a3c  mov     ecx, [rbp+arg_18]
0x180012a3f  mov     byte ptr [rbp+arg_10], 0
0x180012a43  call    ?GetOobeConfigIsSet@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJW4ZTP_CONFIG@@KAEA_N@Z; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetOobeConfigIsSet(ZTP_CONFIG,ulong,bool &)
0x180012a48  mov     ebx, eax
0x180012a4a  test    eax, eax
0x180012a4c  jns     short loc_180012A82
0x180012a4e  mov     r9d, eax; char *
0x180012a51  mov     edx, 0D4h; void *
0x180012a56  mov     rcx, [rbp+18h]; this
0x180012a5a  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012a61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a66  mov     rcx, [rbp+18h]; this
0x180012a6a  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012a71  mov     r9d, ebx; char *
0x180012a74  mov     edx, 80h; void *
0x180012a79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a7e  mov     eax, ebx
0x180012a80  jmp     short loc_180012A8E
0x180012a82  xor     eax, eax
0x180012a84  cmp     byte ptr [rbp+arg_10], al
0x180012a87  setnz   al
0x180012a8a  mov     [rsi], eax
0x180012a8c  xor     eax, eax
0x180012a8e  mov     rbx, [rsp+30h+arg_0]
0x180012a93  add     rsp, 30h
0x180012a97  pop     rdi
0x180012a98  pop     rsi
0x180012a99  pop     rbp
0x180012a9a  retn
```
