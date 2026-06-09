# Microsoft::Windows::Autopilot::RegistryPolicyManager::ClearLocalProfileData(void)

- ea: `0x180026b00`
- end: `0x180026b55`
- name: `?ClearLocalProfileData@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEAAJXZ`
- size: `85`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::RegistryPolicyManager *this, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180026b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026b48`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180026b48`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180026b15`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180026b15`

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
0x180026b00  sub     rsp, 28h
0x180026b04  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180026b0b  jz      short loc_180026B15
0x180026b0d  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180026b13  jmp     short loc_180026B2D
0x180026b15  call    cs:__imp_RtlIsStateSeparationEnabled
0x180026b1b  test    al, al
0x180026b1d  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180026b24  setnz   al
0x180026b27  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180026b2d  test    al, al
0x180026b2f  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180026b36  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180026b3d  cmovz   rdx, rcx; lpSubKey
0x180026b41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026b48  call    cs:__imp_RegDeleteTreeW
0x180026b4e  xor     eax, eax
0x180026b50  add     rsp, 28h
0x180026b54  retn
```
