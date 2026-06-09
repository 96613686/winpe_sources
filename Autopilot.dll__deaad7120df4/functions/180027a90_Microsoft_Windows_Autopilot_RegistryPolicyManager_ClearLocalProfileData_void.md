# Microsoft::Windows::Autopilot::RegistryPolicyManager::ClearLocalProfileData(void)

- ea: `0x180027a90`
- end: `0x180027af2`
- name: `?ClearLocalProfileData@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::RegistryPolicyManager *this, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180027a90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180027ade`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180027ade`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027aa5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027aa5`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::RegistryPolicyManager::ClearLocalProfileData(
        Microsoft::Windows::Autopilot::RegistryPolicyManager *this,
        __int64 a2)
{
  char v2; // al
  char IsStateSeparationEnabled; // al
  const WCHAR *v4; // rdx

  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v2 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(this, a2);
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    v2 = IsStateSeparationEnabled != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v2;
  }
  v4 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  if ( !v2 )
    v4 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  RegDeleteTreeW(HKEY_LOCAL_MACHINE, v4);
  return 0;
}

```

## disassembly

```asm
0x180027a90  sub     rsp, 28h
0x180027a94  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180027a9b  jz      short loc_180027AA5
0x180027a9d  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180027aa3  jmp     short loc_180027AC3
0x180027aa5  call    cs:__imp_RtlIsStateSeparationEnabled
0x180027aac  nop     dword ptr [rax+rax+00h]
0x180027ab1  test    al, al
0x180027ab3  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180027aba  setnz   al
0x180027abd  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180027ac3  test    al, al
0x180027ac5  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180027acc  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180027ad3  cmovz   rdx, rcx; lpSubKey
0x180027ad7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027ade  call    cs:__imp_RegDeleteTreeW
0x180027ae5  nop     dword ptr [rax+rax+00h]
0x180027aea  xor     eax, eax
0x180027aec  add     rsp, 28h
0x180027af0  retn
```
