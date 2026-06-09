# MdmSettings::IsManagedFmdEnabled(int *)

- ea: `0x1800136b8`
- end: `0x1800137a6`
- name: `?IsManagedFmdEnabled@MdmSettings@@SAJPEAH@Z`
- size: `238`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d50`

## callees

- `0x180002040`
- `0x1800065c0`
- `0x1800136b8`
- `0x18001d3e4`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001374d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001374d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x180013718`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x180013718`

## string_xrefs

- `0x180013777`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`

## pseudocode

```c
__int64 __fastcall MdmSettings::IsManagedFmdEnabled(int *a1)
{
  int PolicyInt; // ebx
  int v3; // edx
  int v4; // ecx
  int v6; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+50h] [rbp+18h] BYREF

  if ( (unsigned __int8)IsPolicyManager_IsPolicySetByMobileDeviceManagerPresent() )
    IsPolicyManager_IsPolicySetByMobileDeviceManagerPresent();
  v7 = 0;
  if ( (int)MdmRegistry::GetDWORDValue(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Policies\\Microsoft\\FindMyDevice",
              L"AllowFindMyDevice",
              (BYTE *)&v7) >= 0
    || (v6 = 0, (int)PolicyManager_IsPolicySetByMobileDeviceManager(L"Experience", L"AllowFindMyDevice", &v6) >= 0)
    && v6 )
  {
    v6 = 0;
    PolicyInt = PolicyManager_GetPolicyInt(L"Experience", L"AllowFindMyDevice", &v6);
    if ( PolicyInt >= 0 )
    {
      *a1 = v6 != 0;
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        PolicyInt,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        79,
        "CHR(PolicyManager_GetPolicyInt(c_szFMDMDMAreaName, c_szFMDMDMPolicyName, &value))");
    }
  }
  else
  {
    return 1;
  }
  return (unsigned int)PolicyInt;
}

```

## disassembly

```asm
0x1800136b8  mov     [rsp+arg_0], rbx
0x1800136bd  push    rdi
0x1800136be  sub     rsp, 30h
0x1800136c2  mov     rdi, rcx
0x1800136c5  call    IsPolicyManager_IsPolicySetByMobileDeviceManagerPresent
0x1800136ca  test    al, al
0x1800136cc  jz      short loc_1800136D3
0x1800136ce  call    IsPolicyManager_IsPolicySetByMobileDeviceManagerPresent
0x1800136d3  lea     rbx, aAllowfindmydev; "AllowFindMyDevice"
0x1800136da  mov     [rsp+38h+arg_10], 0
0x1800136e2  mov     r8, rbx; unsigned __int16 *
0x1800136e5  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x1800136ea  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\FindMyDe"...
0x1800136f1  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800136f8  call    ?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x1800136fd  test    eax, eax
0x1800136ff  jns     short loc_180013736
0x180013701  lea     r8, [rsp+38h+arg_8]
0x180013706  mov     [rsp+38h+arg_8], 0
0x18001370e  mov     rdx, rbx
0x180013711  lea     rcx, aExperience; "Experience"
0x180013718  call    cs:__imp_PolicyManager_IsPolicySetByMobileDeviceManager
0x18001371f  nop     dword ptr [rax+rax+00h]
0x180013724  test    eax, eax
0x180013726  js      short loc_18001372F
0x180013728  cmp     [rsp+38h+arg_8], 0
0x18001372d  jnz     short loc_180013736
0x18001372f  mov     ebx, 1
0x180013734  jmp     short loc_180013798
0x180013736  lea     r8, [rsp+38h+arg_8]
0x18001373b  mov     [rsp+38h+arg_8], 0
0x180013743  mov     rdx, rbx
0x180013746  lea     rcx, aExperience; "Experience"
0x18001374d  call    cs:__imp_PolicyManager_GetPolicyInt
0x180013754  nop     dword ptr [rax+rax+00h]
0x180013759  mov     ebx, eax
0x18001375b  test    eax, eax
0x18001375d  jns     short loc_18001378D
0x18001375f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013766  jz      short loc_180013798
0x180013768  lea     rax, aChrPolicymanag; "CHR(PolicyManager_GetPolicyInt(c_szFMDM"...
0x18001376f  mov     r8d, ebx
0x180013772  mov     [rsp+38h+var_10], rax
0x180013777  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001377e  mov     [rsp+38h+var_18], 34Fh
0x180013786  call    McTemplateU0dsqs_EventWriteTransfer
0x18001378b  jmp     short loc_180013798
0x18001378d  xor     eax, eax
0x18001378f  cmp     [rsp+38h+arg_8], eax
0x180013793  setnz   al
0x180013796  mov     [rdi], eax
0x180013798  mov     eax, ebx
0x18001379a  mov     rbx, [rsp+38h+arg_0]
0x18001379f  add     rsp, 30h
0x1800137a3  pop     rdi
0x1800137a4  retn
```
