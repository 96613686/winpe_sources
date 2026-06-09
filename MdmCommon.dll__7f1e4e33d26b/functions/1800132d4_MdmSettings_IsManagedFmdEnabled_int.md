# MdmSettings::IsManagedFmdEnabled(int *)

- ea: `0x1800132d4`
- end: `0x1800133b5`
- name: `?IsManagedFmdEnabled@MdmSettings@@SAJPEAH@Z`
- size: `225`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d40`

## callees

- `0x180002040`
- `0x180006548`
- `0x1800132d4`
- `0x18001cd64`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180013363`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180013363`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x180013334`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x180013334`

## string_xrefs

- `0x180013387`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`

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
  if ( MdmRegistry::GetDWORDValue(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\FindMyDevice",
         L"AllowFindMyDevice",
         &v7) >= 0
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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        79,
        (__int64)"CHR(PolicyManager_GetPolicyInt(c_szFMDMDMAreaName, c_szFMDMDMPolicyName, &value))");
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
0x1800132d4  mov     [rsp+arg_0], rbx
0x1800132d9  push    rdi
0x1800132da  sub     rsp, 30h
0x1800132de  mov     rdi, rcx
0x1800132e1  call    IsPolicyManager_IsPolicySetByMobileDeviceManagerPresent
0x1800132e6  test    al, al
0x1800132e8  jz      short loc_1800132EF
0x1800132ea  call    IsPolicyManager_IsPolicySetByMobileDeviceManagerPresent
0x1800132ef  lea     rbx, aAllowfindmydev; "AllowFindMyDevice"
0x1800132f6  mov     [rsp+38h+arg_10], 0
0x1800132fe  mov     r8, rbx; unsigned __int16 *
0x180013301  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x180013306  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\FindMyDe"...
0x18001330d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180013314  call    ?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x180013319  test    eax, eax
0x18001331b  jns     short loc_18001334C
0x18001331d  lea     r8, [rsp+38h+arg_8]
0x180013322  mov     [rsp+38h+arg_8], 0
0x18001332a  mov     rdx, rbx
0x18001332d  lea     rcx, aExperience; "Experience"
0x180013334  call    cs:__imp_PolicyManager_IsPolicySetByMobileDeviceManager
0x18001333a  test    eax, eax
0x18001333c  js      short loc_180013345
0x18001333e  cmp     [rsp+38h+arg_8], 0
0x180013343  jnz     short loc_18001334C
0x180013345  mov     ebx, 1
0x18001334a  jmp     short loc_1800133A8
0x18001334c  lea     r8, [rsp+38h+arg_8]
0x180013351  mov     [rsp+38h+arg_8], 0
0x180013359  mov     rdx, rbx
0x18001335c  lea     rcx, aExperience; "Experience"
0x180013363  call    cs:__imp_PolicyManager_GetPolicyInt
0x180013369  mov     ebx, eax
0x18001336b  test    eax, eax
0x18001336d  jns     short loc_18001339D
0x18001336f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013376  jz      short loc_1800133A8
0x180013378  lea     rax, aChrPolicymanag; "CHR(PolicyManager_GetPolicyInt(c_szFMDM"...
0x18001337f  mov     r8d, ebx
0x180013382  mov     [rsp+38h+var_10], rax
0x180013387  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001338e  mov     [rsp+38h+var_18], 34Fh
0x180013396  call    McTemplateU0dsqs_EventWriteTransfer
0x18001339b  jmp     short loc_1800133A8
0x18001339d  xor     eax, eax
0x18001339f  cmp     [rsp+38h+arg_8], eax
0x1800133a3  setnz   al
0x1800133a6  mov     [rdi], eax
0x1800133a8  mov     eax, ebx
0x1800133aa  mov     rbx, [rsp+38h+arg_0]
0x1800133af  add     rsp, 30h
0x1800133b3  pop     rdi
0x1800133b4  retn
```
