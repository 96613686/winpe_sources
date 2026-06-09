# AutoPilotIsLocalProfileAvailable

- ea: `0x180012ca0`
- end: `0x180012d91`
- name: `AutoPilotIsLocalProfileAvailable`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012ca0`
- `0x180016350`
- `0x18001ecc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012d39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012d39`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012cd6`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012cd6`

## string_xrefs

- `0x180012d0d`: `OSData\Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180012cf6`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180012d73`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

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
        (__int64)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)v8);
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
0x180012ca0  push    rbx
0x180012ca2  sub     rsp, 40h
0x180012ca6  mov     rbx, rcx
0x180012ca9  call    ?IsDisabled@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled(void)
0x180012cae  test    al, al
0x180012cb0  jnz     loc_180012D84
0x180012cb6  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180012cbc  mov     [rsp+48h+arg_0], 0
0x180012cc4  mov     [rsp+48h+arg_8], 4
0x180012ccc  jz      short loc_180012CD6
0x180012cce  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180012cd4  jmp     short loc_180012CF4
0x180012cd6  call    cs:__imp_RtlIsStateSeparationEnabled
0x180012cdd  nop     dword ptr [rax+rax+00h]
0x180012ce2  test    al, al
0x180012ce4  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180012ceb  setnz   al
0x180012cee  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180012cf4  test    al, al
0x180012cf6  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\Auto"...
0x180012cfd  lea     rax, [rsp+48h+arg_8]
0x180012d02  mov     r9d, 10h; dwFlags
0x180012d08  mov     [rsp+48h+pcbData], rax; pcbData
0x180012d0d  lea     rdx, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x180012d14  lea     rax, [rsp+48h+arg_0]
0x180012d19  cmovz   rdx, rcx; lpSubKey
0x180012d1d  mov     [rsp+48h+pvData], rax; pvData
0x180012d22  lea     r8, Value; "ProfileAvailable"
0x180012d29  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180012d30  mov     [rsp+48h+pdwType], 0; int
0x180012d39  call    cs:__imp_RegGetValueW
0x180012d40  nop     dword ptr [rax+rax+00h]
0x180012d45  mov     r9d, eax
0x180012d48  test    eax, eax
0x180012d4a  jnz     short loc_180012D56
0x180012d4c  cmp     [rsp+48h+arg_0], 1
0x180012d51  setz    al
0x180012d54  jmp     short loc_180012D86
0x180012d56  add     eax, 0FFFFFFFEh
0x180012d59  cmp     eax, 1
0x180012d5c  jbe     short loc_180012D84
0x180012d5e  test    r9d, r9d
0x180012d61  jle     short loc_180012D6E
0x180012d63  movzx   r9d, r9w
0x180012d67  or      r9d, 80070000h; char *
0x180012d6e  mov     rcx, [rsp+48h]; this
0x180012d73  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012d7a  mov     edx, 0B4h; void *
0x180012d7f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180012d84  xor     eax, eax
0x180012d86  mov     [rbx], eax
0x180012d88  xor     eax, eax
0x180012d8a  add     rsp, 40h
0x180012d8e  pop     rbx
0x180012d8f  retn
```
