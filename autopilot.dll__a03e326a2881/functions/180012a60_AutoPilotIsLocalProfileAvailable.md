# AutoPilotIsLocalProfileAvailable

- ea: `0x180012a60`
- end: `0x180012b44`
- name: `AutoPilotIsLocalProfileAvailable`
- size: `228`
- prototype: `__int64 __fastcall(BOOL *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012a60`
- `0x180015ed0`
- `0x18001e470`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012af3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012af3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012a96`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012a96`

## string_xrefs

- `0x180012ac7`: `OSData\Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180012ab0`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180012b27`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
__int64 __fastcall AutoPilotIsLocalProfileAvailable(BOOL *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  char v4; // al
  char IsStateSeparationEnabled; // al
  const WCHAR *v6; // rdx
  LSTATUS ValueW; // eax
  unsigned __int64 v8; // r9
  BOOL v9; // eax
  int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF

  if ( Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled() )
  {
LABEL_13:
    v9 = 0;
    goto LABEL_14;
  }
  pvData = 0;
  pcbData = 4;
  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v4 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v3, v2);
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    v4 = IsStateSeparationEnabled != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v4;
  }
  v6 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
  if ( !v4 )
    v6 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v6, L"ProfileAvailable", 0x10u, 0, &pvData, &pcbData);
  v8 = (unsigned int)ValueW;
  if ( ValueW )
  {
    if ( (unsigned int)(ValueW - 2) > 1 )
    {
      if ( ValueW > 0 )
        v8 = (unsigned __int16)ValueW | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)v8,
        pdwType);
    }
    goto LABEL_13;
  }
  v9 = pvData == 1;
LABEL_14:
  *a1 = v9;
  return 0;
}

```

## disassembly

```asm
0x180012a60  push    rbx
0x180012a62  sub     rsp, 40h
0x180012a66  mov     rbx, rcx
0x180012a69  call    ?IsDisabled@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled(void)
0x180012a6e  test    al, al
0x180012a70  jnz     loc_180012B38
0x180012a76  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180012a7c  mov     [rsp+48h+arg_0], 0
0x180012a84  mov     [rsp+48h+arg_8], 4
0x180012a8c  jz      short loc_180012A96
0x180012a8e  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180012a94  jmp     short loc_180012AAE
0x180012a96  call    cs:__imp_RtlIsStateSeparationEnabled
0x180012a9c  test    al, al
0x180012a9e  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180012aa5  setnz   al
0x180012aa8  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180012aae  test    al, al
0x180012ab0  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\Auto"...
0x180012ab7  lea     rax, [rsp+48h+arg_8]
0x180012abc  mov     r9d, 10h; dwFlags
0x180012ac2  mov     [rsp+48h+pcbData], rax; pcbData
0x180012ac7  lea     rdx, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x180012ace  lea     rax, [rsp+48h+arg_0]
0x180012ad3  cmovz   rdx, rcx; lpSubKey
0x180012ad7  mov     [rsp+48h+pvData], rax; pvData
0x180012adc  lea     r8, Value; "ProfileAvailable"
0x180012ae3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180012aea  mov     [rsp+48h+pdwType], 0; int
0x180012af3  call    cs:__imp_RegGetValueW
0x180012af9  mov     r9d, eax
0x180012afc  test    eax, eax
0x180012afe  jnz     short loc_180012B0A
0x180012b00  cmp     [rsp+48h+arg_0], 1
0x180012b05  setz    al
0x180012b08  jmp     short loc_180012B3A
0x180012b0a  add     eax, 0FFFFFFFEh
0x180012b0d  cmp     eax, 1
0x180012b10  jbe     short loc_180012B38
0x180012b12  test    r9d, r9d
0x180012b15  jle     short loc_180012B22
0x180012b17  movzx   r9d, r9w
0x180012b1b  or      r9d, 80070000h; char *
0x180012b22  mov     rcx, [rsp+48h]; this
0x180012b27  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012b2e  mov     edx, 0B4h; void *
0x180012b33  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180012b38  xor     eax, eax
0x180012b3a  mov     [rbx], eax
0x180012b3c  xor     eax, eax
0x180012b3e  add     rsp, 40h
0x180012b42  pop     rbx
0x180012b43  retn
```
