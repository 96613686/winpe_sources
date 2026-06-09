# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsWindowsPatchUXOverriden(ZTP_CONFIG,ulong &)

- ea: `0x18001e514`
- end: `0x18001e583`
- name: `?IsWindowsPatchUXOverriden@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NW4ZTP_CONFIG@@AEAK@Z`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012720`

## callees

- `0x18001e514`
- `0x180020c34`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e539`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e539`

## string_xrefs

- `0x18001e568`: `DontAllowUpdatesInOobe`

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
    v5 = (const unsigned __int16 *)&stru_180038360;
  return Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
           (HKEY)&stru_180038360,
           v5,
           L"DontAllowUpdatesInOobe",
           a2) >= 0;
}

```

## disassembly

```asm
0x18001e514  push    rbx
0x18001e516  sub     rsp, 20h
0x18001e51a  mov     dword ptr [rdx], 0
0x18001e520  mov     rbx, rdx
0x18001e523  cmp     ecx, 9
0x18001e526  jnz     short loc_18001E57B
0x18001e528  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001e52f  jz      short loc_18001E539
0x18001e531  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001e537  jmp     short loc_18001E551
0x18001e539  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001e53f  test    al, al
0x18001e541  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001e548  setnz   al
0x18001e54b  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001e551  test    al, al
0x18001e553  lea     rcx, stru_180038360; HKEY
0x18001e55a  lea     rdx, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001e561  mov     r9, rbx; unsigned int *
0x18001e564  cmovz   rdx, rcx; unsigned __int16 *
0x18001e568  lea     r8, aDontallowupdat; "DontAllowUpdatesInOobe"
0x18001e56f  call    ?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001e574  test    eax, eax
0x18001e576  setns   al
0x18001e579  jmp     short loc_18001E57D
0x18001e57b  xor     al, al
0x18001e57d  add     rsp, 20h
0x18001e581  pop     rbx
0x18001e582  retn
```
