# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetOobeConfigIsSet(ZTP_CONFIG,ulong,bool &)

- ea: `0x18001e260`
- end: `0x18001e469`
- name: `?GetOobeConfigIsSet@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJW4ZTP_CONFIG@@KAEA_N@Z`
- size: `521`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012720`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013280`
- `0x180017400`
- `0x18001e260`
- `0x180020c34`
- `0x18002735c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e2fa`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e380`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e2fa`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e380`

## string_xrefs

- `0x18001e2aa`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18001e3fb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetOobeConfigIsSet(
        HKEY a1,
        int a2,
        _BYTE *a3)
{
  __int64 *v4; // rax
  char v6; // al
  const unsigned __int16 *v7; // rdi
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rdx
  HKEY v10; // rcx
  __int64 v11; // r8
  char v12; // al
  __int64 v13; // rcx
  __int64 v14; // r8
  ULONG v15; // r9d
  __int64 *v16; // rdx
  int DeviceAutopilotMode; // eax
  int v18; // [rsp+20h] [rbp-48h]
  unsigned int v19; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+38h] [rbp-30h] BYREF
  unsigned int *v21; // [rsp+48h] [rbp-20h]
  __int64 v22; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v4 = &qword_180038280;
  do
  {
    if ( *(_DWORD *)v4 == (_DWORD)a1 )
      break;
    ++v4;
  }
  while ( v4 != (__int64 *)L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings" );
  if ( v4 == (__int64 *)L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings" )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DC,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
      (const char *)0x80070057LL,
      v18);
    return 2147942487LL;
  }
  LOBYTE(a1) = !*((_DWORD *)v4 + 1) || (a2 & *((_DWORD *)v4 + 1)) != 0;
  *a3 = (_BYTE)a1;
  if ( *((_DWORD *)v4 + 1) == 32 )
  {
    v19 = 0;
    if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
    {
      v6 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
    }
    else
    {
      v6 = (unsigned __int8)RtlIsStateSeparationEnabled(a1, a3) != 0;
      `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v6;
      `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    }
    v7 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings";
    v8 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings";
    if ( !v6 )
      v8 = (const unsigned __int16 *)&stru_180038360;
    if ( (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
                a1,
                v8,
                L"TpmRequiredDisable",
                &v19) >= 0
      && v19 == 1 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
        McGenEventWrite_EventWriteTransfer(
          (__int64)v10,
          (const EVENT_DESCRIPTOR *)AutopilotPolicyManagerOverrideTpmDisabled,
          v11,
          1u,
          &v20);
      *a3 = 0;
      return 0;
    }
    if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
    {
      v12 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
    }
    else
    {
      v12 = (unsigned __int8)RtlIsStateSeparationEnabled(v10, v9) != 0;
      `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v12;
      `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    }
    if ( !v12 )
      v7 = (const unsigned __int16 *)&stru_180038360;
    if ( (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
                v10,
                v7,
                L"TpmForcedRequired",
                &v19) >= 0
      && v19 == 1 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) == 0 )
      {
LABEL_37:
        *a3 = 1;
        return 0;
      }
      v15 = 1;
      v16 = AutopilotPolicyManagerOverrideTpmEnable;
    }
    else
    {
      if ( *a3 )
        return 0;
      v19 = 0;
      DeviceAutopilotMode = EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotWhiteGloveUtils::GetDeviceAutopilotMode((enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *)&v19);
      if ( DeviceAutopilotMode < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x404,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
          (const char *)(unsigned int)DeviceAutopilotMode,
          v18);
      v13 = v19;
      if ( v19 - 1 > 1 )
        return 0;
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) == 0 )
        goto LABEL_37;
      v21 = &v19;
      v22 = 4;
      v15 = 2;
      v16 = AutopilotPolicyManagerOverrideTpmRequiredWhiteGlove;
    }
    McGenEventWrite_EventWriteTransfer(v13, (const EVENT_DESCRIPTOR *)v16, v14, v15, &v20);
    goto LABEL_37;
  }
  return 0;
}

```

## disassembly

```asm
0x18001e260  push    rbp
0x18001e262  push    rbx
0x18001e263  push    rdi
0x18001e264  push    r15
0x18001e266  mov     rbp, rsp
0x18001e269  sub     rsp, 68h
0x18001e26d  mov     rax, cs:__security_cookie
0x18001e274  xor     rax, rsp
0x18001e277  mov     [rbp+var_10], rax
0x18001e27b  mov     rbx, r8
0x18001e27e  lea     rax, qword_180038280
0x18001e285  lea     r8, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001e28c  cmp     [rax], ecx
0x18001e28e  jz      short loc_18001E299
0x18001e290  add     rax, 8
0x18001e294  cmp     rax, r8
0x18001e297  jnz     short loc_18001E28C
0x18001e299  cmp     rax, r8
0x18001e29c  jnz     short loc_18001E2C2
0x18001e29e  mov     rcx, [rbp+20h]; this
0x18001e2a2  mov     ebx, 80070057h
0x18001e2a7  mov     r9d, ebx; char *
0x18001e2aa  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e2b1  mov     edx, 3DCh; void *
0x18001e2b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e2bb  mov     eax, ebx
0x18001e2bd  jmp     loc_18001E453
0x18001e2c2  cmp     dword ptr [rax+4], 0
0x18001e2c6  jz      short loc_18001E2D1
0x18001e2c8  test    [rax+4], edx
0x18001e2cb  jnz     short loc_18001E2D1
0x18001e2cd  xor     cl, cl
0x18001e2cf  jmp     short loc_18001E2D3
0x18001e2d1  mov     cl, 1
0x18001e2d3  mov     rdx, rbx
0x18001e2d6  mov     [rbx], cl
0x18001e2d8  cmp     dword ptr [rax+4], 20h ; ' '
0x18001e2dc  jnz     loc_18001E451
0x18001e2e2  mov     [rbp+var_38], 0
0x18001e2e9  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001e2f0  jz      short loc_18001E2FA
0x18001e2f2  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001e2f8  jmp     short loc_18001E312
0x18001e2fa  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001e300  test    al, al
0x18001e302  setnz   al
0x18001e305  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001e30b  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001e312  lea     r15, stru_180038360
0x18001e319  lea     rdi, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001e320  mov     rdx, rdi
0x18001e323  test    al, al
0x18001e325  cmovz   rdx, r15; unsigned __int16 *
0x18001e329  lea     r9, [rbp+var_38]; unsigned int *
0x18001e32d  lea     r8, aTpmrequireddis; "TpmRequiredDisable"
0x18001e334  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001e339  test    eax, eax
0x18001e33b  js      short loc_18001E36F
0x18001e33d  cmp     [rbp+var_38], 1
0x18001e341  jnz     short loc_18001E36F
0x18001e343  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18001e34a  jge     short loc_18001E367
0x18001e34c  lea     rax, [rbp+var_30]
0x18001e350  mov     qword ptr [rsp+68h+var_48], rax
0x18001e355  mov     r9d, 1
0x18001e35b  lea     rdx, AutopilotPolicyManagerOverrideTpmDisabled
0x18001e362  call    McGenEventWrite_EventWriteTransfer
0x18001e367  mov     byte ptr [rbx], 0
0x18001e36a  jmp     loc_18001E451
0x18001e36f  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001e376  jz      short loc_18001E380
0x18001e378  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001e37e  jmp     short loc_18001E398
0x18001e380  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001e386  test    al, al
0x18001e388  setnz   al
0x18001e38b  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001e391  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001e398  test    al, al
0x18001e39a  cmovz   rdi, r15
0x18001e39e  lea     r9, [rbp+var_38]; unsigned int *
0x18001e3a2  lea     r8, aTpmforcedrequi; "TpmForcedRequired"
0x18001e3a9  mov     rdx, rdi; unsigned __int16 *
0x18001e3ac  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001e3b1  test    eax, eax
0x18001e3b3  js      short loc_18001E3DB
0x18001e3b5  cmp     [rbp+var_38], 1
0x18001e3b9  jnz     short loc_18001E3DB
0x18001e3bb  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18001e3c2  jge     loc_18001E44E
0x18001e3c8  lea     rax, [rbp+var_30]
0x18001e3cc  mov     r9d, 1
0x18001e3d2  lea     rdx, AutopilotPolicyManagerOverrideTpmEnable
0x18001e3d9  jmp     short loc_18001E444
0x18001e3db  cmp     byte ptr [rbx], 0
0x18001e3de  jnz     short loc_18001E451
0x18001e3e0  mov     [rbp+var_38], 0
0x18001e3e7  lea     rcx, [rbp+var_38]; enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *
0x18001e3eb  call    ?GetDeviceAutopilotMode@AutoPilotWhiteGloveUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEAW4AutopilotMode@234@@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotWhiteGloveUtils::GetDeviceAutopilotMode(EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *)
0x18001e3f0  test    eax, eax
0x18001e3f2  jns     short loc_18001E40C
0x18001e3f4  mov     rcx, [rbp+20h]; this
0x18001e3f8  mov     r9d, eax; char *
0x18001e3fb  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e402  mov     edx, 404h; void *
0x18001e407  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e40c  mov     ecx, [rbp+var_38]
0x18001e40f  lea     eax, [rcx-1]
0x18001e412  cmp     eax, 1
0x18001e415  ja      short loc_18001E451
0x18001e417  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18001e41e  jge     short loc_18001E44E
0x18001e420  mov     [rbp+var_38], ecx
0x18001e423  lea     rax, [rbp+var_38]
0x18001e427  mov     [rbp+var_20], rax
0x18001e42b  mov     [rbp+var_18], 4
0x18001e433  lea     rax, [rbp+var_30]
0x18001e437  mov     r9d, 2
0x18001e43d  lea     rdx, AutopilotPolicyManagerOverrideTpmRequiredWhiteGlove
0x18001e444  mov     qword ptr [rsp+68h+var_48], rax
0x18001e449  call    McGenEventWrite_EventWriteTransfer
0x18001e44e  mov     byte ptr [rbx], 1
0x18001e451  xor     eax, eax
0x18001e453  mov     rcx, [rbp+var_10]
0x18001e457  xor     rcx, rsp; StackCookie
0x18001e45a  call    __security_check_cookie
0x18001e45f  add     rsp, 68h
0x18001e463  pop     r15
0x18001e465  pop     rdi
0x18001e466  pop     rbx
0x18001e467  pop     rbp
0x18001e468  retn
```
