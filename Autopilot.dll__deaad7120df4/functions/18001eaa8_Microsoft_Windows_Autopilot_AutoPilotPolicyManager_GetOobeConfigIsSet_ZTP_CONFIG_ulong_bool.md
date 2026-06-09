# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::GetOobeConfigIsSet(ZTP_CONFIG,ulong,bool &)

- ea: `0x18001eaa8`
- end: `0x18001ecbe`
- name: `?GetOobeConfigIsSet@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SAJW4ZTP_CONFIG@@KAEA_N@Z`
- size: `534`
- prototype: `__int64 __fastcall(HKEY, int, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012960`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013520`
- `0x18001792c`
- `0x18001eaa8`
- `0x18002164c`
- `0x180028380`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18001eb42`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ebce`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001eb42`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ebce`

## string_xrefs

- `0x18001eaf2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x18001ec4f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`

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
  __int64 v15; // r9
  __int64 *v16; // rdx
  int DeviceAutopilotMode; // eax
  int v18; // [rsp+20h] [rbp-48h]
  unsigned int v19; // [rsp+30h] [rbp-38h] BYREF
  unsigned int *v20; // [rsp+48h] [rbp-20h]
  __int64 v21; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v4 = &qword_1800392A0;
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
      v8 = (const unsigned __int16 *)&stru_180039380;
    if ( (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
                a1,
                v8,
                L"TpmRequiredDisable",
                &v19) >= 0
      && v19 == 1 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
        McGenEventWrite_EventWriteTransfer(v10, AutopilotPolicyManagerOverrideTpmDisabled, v11, 1);
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
      v7 = (const unsigned __int16 *)&stru_180039380;
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
      v20 = &v19;
      v21 = 4;
      v15 = 2;
      v16 = AutopilotPolicyManagerOverrideTpmRequiredWhiteGlove;
    }
    McGenEventWrite_EventWriteTransfer(v13, v16, v14, v15);
    goto LABEL_37;
  }
  return 0;
}

```

## disassembly

```asm
0x18001eaa8  push    rbp
0x18001eaaa  push    rbx
0x18001eaab  push    rdi
0x18001eaac  push    r15
0x18001eaae  mov     rbp, rsp
0x18001eab1  sub     rsp, 68h
0x18001eab5  mov     rax, cs:__security_cookie
0x18001eabc  xor     rax, rsp
0x18001eabf  mov     [rbp+var_10], rax
0x18001eac3  mov     rbx, r8
0x18001eac6  lea     rax, qword_1800392A0
0x18001eacd  lea     r8, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001ead4  cmp     [rax], ecx
0x18001ead6  jz      short loc_18001EAE1
0x18001ead8  add     rax, 8
0x18001eadc  cmp     rax, r8
0x18001eadf  jnz     short loc_18001EAD4
0x18001eae1  cmp     rax, r8
0x18001eae4  jnz     short loc_18001EB0A
0x18001eae6  mov     rcx, [rbp+20h]; this
0x18001eaea  mov     ebx, 80070057h
0x18001eaef  mov     r9d, ebx; char *
0x18001eaf2  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001eaf9  mov     edx, 3DCh; void *
0x18001eafe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb03  mov     eax, ebx
0x18001eb05  jmp     loc_18001ECA7
0x18001eb0a  cmp     dword ptr [rax+4], 0
0x18001eb0e  jz      short loc_18001EB19
0x18001eb10  test    [rax+4], edx
0x18001eb13  jnz     short loc_18001EB19
0x18001eb15  xor     cl, cl
0x18001eb17  jmp     short loc_18001EB1B
0x18001eb19  mov     cl, 1
0x18001eb1b  mov     rdx, rbx
0x18001eb1e  mov     [rbx], cl
0x18001eb20  cmp     dword ptr [rax+4], 20h ; ' '
0x18001eb24  jnz     loc_18001ECA5
0x18001eb2a  mov     [rbp+var_38], 0
0x18001eb31  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001eb38  jz      short loc_18001EB42
0x18001eb3a  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001eb40  jmp     short loc_18001EB60
0x18001eb42  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001eb49  nop     dword ptr [rax+rax+00h]
0x18001eb4e  test    al, al
0x18001eb50  setnz   al
0x18001eb53  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001eb59  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001eb60  lea     r15, stru_180039380
0x18001eb67  lea     rdi, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001eb6e  mov     rdx, rdi
0x18001eb71  test    al, al
0x18001eb73  cmovz   rdx, r15; unsigned __int16 *
0x18001eb77  lea     r9, [rbp+var_38]; unsigned int *
0x18001eb7b  lea     r8, aTpmrequireddis; "TpmRequiredDisable"
0x18001eb82  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001eb87  test    eax, eax
0x18001eb89  js      short loc_18001EBBD
0x18001eb8b  cmp     [rbp+var_38], 1
0x18001eb8f  jnz     short loc_18001EBBD
0x18001eb91  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18001eb98  jge     short loc_18001EBB5
0x18001eb9a  lea     rax, [rbp+var_30]
0x18001eb9e  mov     qword ptr [rsp+68h+var_48], rax
0x18001eba3  mov     r9d, 1
0x18001eba9  lea     rdx, AutopilotPolicyManagerOverrideTpmDisabled
0x18001ebb0  call    McGenEventWrite_EventWriteTransfer
0x18001ebb5  mov     byte ptr [rbx], 0
0x18001ebb8  jmp     loc_18001ECA5
0x18001ebbd  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001ebc4  jz      short loc_18001EBCE
0x18001ebc6  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001ebcc  jmp     short loc_18001EBEC
0x18001ebce  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001ebd5  nop     dword ptr [rax+rax+00h]
0x18001ebda  test    al, al
0x18001ebdc  setnz   al
0x18001ebdf  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001ebe5  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001ebec  test    al, al
0x18001ebee  cmovz   rdi, r15
0x18001ebf2  lea     r9, [rbp+var_38]; unsigned int *
0x18001ebf6  lea     r8, aTpmforcedrequi; "TpmForcedRequired"
0x18001ebfd  mov     rdx, rdi; unsigned __int16 *
0x18001ec00  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001ec05  test    eax, eax
0x18001ec07  js      short loc_18001EC2F
0x18001ec09  cmp     [rbp+var_38], 1
0x18001ec0d  jnz     short loc_18001EC2F
0x18001ec0f  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18001ec16  jge     loc_18001ECA2
0x18001ec1c  lea     rax, [rbp+var_30]
0x18001ec20  mov     r9d, 1
0x18001ec26  lea     rdx, AutopilotPolicyManagerOverrideTpmEnable
0x18001ec2d  jmp     short loc_18001EC98
0x18001ec2f  cmp     byte ptr [rbx], 0
0x18001ec32  jnz     short loc_18001ECA5
0x18001ec34  mov     [rbp+var_38], 0
0x18001ec3b  lea     rcx, [rbp+var_38]; enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *
0x18001ec3f  call    ?GetDeviceAutopilotMode@AutoPilotWhiteGloveUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEAW4AutopilotMode@234@@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotWhiteGloveUtils::GetDeviceAutopilotMode(EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *)
0x18001ec44  test    eax, eax
0x18001ec46  jns     short loc_18001EC60
0x18001ec48  mov     rcx, [rbp+20h]; this
0x18001ec4c  mov     r9d, eax; char *
0x18001ec4f  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ec56  mov     edx, 404h; void *
0x18001ec5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ec60  mov     ecx, [rbp+var_38]
0x18001ec63  lea     eax, [rcx-1]
0x18001ec66  cmp     eax, 1
0x18001ec69  ja      short loc_18001ECA5
0x18001ec6b  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18001ec72  jge     short loc_18001ECA2
0x18001ec74  mov     [rbp+var_38], ecx
0x18001ec77  lea     rax, [rbp+var_38]
0x18001ec7b  mov     [rbp+var_20], rax
0x18001ec7f  mov     [rbp+var_18], 4
0x18001ec87  lea     rax, [rbp+var_30]
0x18001ec8b  mov     r9d, 2
0x18001ec91  lea     rdx, AutopilotPolicyManagerOverrideTpmRequiredWhiteGlove
0x18001ec98  mov     qword ptr [rsp+68h+var_48], rax
0x18001ec9d  call    McGenEventWrite_EventWriteTransfer
0x18001eca2  mov     byte ptr [rbx], 1
0x18001eca5  xor     eax, eax
0x18001eca7  mov     rcx, [rbp+var_10]
0x18001ecab  xor     rcx, rsp; StackCookie
0x18001ecae  call    __security_check_cookie
0x18001ecb3  add     rsp, 68h
0x18001ecb7  pop     r15
0x18001ecb9  pop     rdi
0x18001ecba  pop     rbx
0x18001ecbb  pop     rbp
0x18001ecbc  retn
```
