# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsWindowsPatchUXOverriden(ZTP_CONFIG,ulong &)

- ea: `0x18001ed68`
- end: `0x18001edde`
- name: `?IsWindowsPatchUXOverriden@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NW4ZTP_CONFIG@@AEAK@Z`
- size: `118`
- prototype: `bool __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012960`

## callees

- `0x18001ed68`
- `0x18002164c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ed8d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ed8d`

## string_xrefs

- `0x18001edc2`: `DontAllowUpdatesInOobe`

## pseudocode

```c
bool __fastcall Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsWindowsPatchUXOverriden(
        __int64 a1,
        unsigned int *a2)
{
  char v3; // al
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v5; // rdx

  *a2 = 0;
  if ( (_DWORD)a1 != 9 )
    return 0;
  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v3 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    v3 = IsStateSeparationEnabled != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v3;
  }
  v5 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings";
  if ( !v3 )
    v5 = (const unsigned __int16 *)&stru_180039380;
  return (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
                (HKEY)&stru_180039380,
                v5,
                L"DontAllowUpdatesInOobe",
                a2) >= 0;
}

```

## disassembly

```asm
0x18001ed68  push    rbx
0x18001ed6a  sub     rsp, 20h
0x18001ed6e  mov     dword ptr [rdx], 0
0x18001ed74  mov     rbx, rdx
0x18001ed77  cmp     ecx, 9
0x18001ed7a  jnz     short loc_18001EDD5
0x18001ed7c  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001ed83  jz      short loc_18001ED8D
0x18001ed85  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001ed8b  jmp     short loc_18001EDAB
0x18001ed8d  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001ed94  nop     dword ptr [rax+rax+00h]
0x18001ed99  test    al, al
0x18001ed9b  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001eda2  setnz   al
0x18001eda5  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001edab  test    al, al
0x18001edad  lea     rcx, stru_180039380; HKEY
0x18001edb4  lea     rdx, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001edbb  mov     r9, rbx; unsigned int *
0x18001edbe  cmovz   rdx, rcx; unsigned __int16 *
0x18001edc2  lea     r8, aDontallowupdat; "DontAllowUpdatesInOobe"
0x18001edc9  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001edce  test    eax, eax
0x18001edd0  setns   al
0x18001edd3  jmp     short loc_18001EDD7
0x18001edd5  xor     al, al
0x18001edd7  add     rsp, 20h
0x18001eddb  pop     rbx
0x18001eddc  retn
```
