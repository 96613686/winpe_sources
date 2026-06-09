# MdmSettings::SetUnmanagedFmd(int)

- ea: `0x180014344`
- end: `0x180014489`
- name: `?SetUnmanagedFmd@MdmSettings@@SAJH@Z`
- size: `325`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800057e0`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x180014344`
- `0x18001d77c`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18001441f`
- `ntdll!RtlPublishWnfStateData` at `0x18001441f`

## string_xrefs

- `0x180014456`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800143a9`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x1800143ec`: `CHR(MdmRegistry::SetBOOLValue(wszKey, c_szFMDEnabledValueName, fEnabled))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetUnmanagedFmd(int a1)
{
  int v2; // edx
  int v3; // ecx
  int MdmCommonSettingValuesPersistedLocation; // ebx
  int v5; // edx
  int v6; // ecx
  int v7; // eax
  int v8; // edx
  int v9; // ecx
  unsigned int v11; // [rsp+20h] [rbp-248h]
  unsigned int v12; // [rsp+30h] [rbp-238h] BYREF
  int v13[3]; // [rsp+34h] [rbp-234h] BYREF
  unsigned __int16 v14[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(v14, 0, 0x208u);
  v12 = 260;
  v13[0] = 1;
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v14, &v12);
  if ( MdmCommonSettingValuesPersistedLocation >= 0 )
  {
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetBOOLValue(
                                                HKEY_LOCAL_MACHINE,
                                                v14,
                                                L"LocationSyncEnabled",
                                                a1,
                                                v11);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
    {
      v7 = RtlPublishWnfStateData(WNF_SHEL_SETTINGS_CHANGED, 0, v13, 4, 0);
      if ( v7 )
      {
        MdmCommonSettingValuesPersistedLocation = v7 | 0x10000000;
        if ( v7 < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v9,
            v8,
            MdmCommonSettingValuesPersistedLocation,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
            117,
            "CHR(((HRESULT) ((ntstatus) | 0x10000000)))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        104,
        "CHR(MdmRegistry::SetBOOLValue(wszKey, c_szFMDEnabledValueName, fEnabled))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      102,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))");
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180014344  mov     [rsp+arg_8], rbx
0x180014349  push    rdi
0x18001434a  sub     rsp, 260h
0x180014351  mov     rax, cs:__security_cookie
0x180014358  xor     rax, rsp
0x18001435b  mov     [rsp+268h+var_18], rax
0x180014363  mov     edi, ecx
0x180014365  xor     edx, edx; Val
0x180014367  lea     rcx, [rsp+268h+var_228]; void *
0x18001436c  mov     r8d, 208h; Size
0x180014372  call    memset_0
0x180014377  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x18001437c  mov     [rsp+268h+var_238], 104h
0x180014384  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180014389  mov     [rsp+268h+var_234], 1
0x180014391  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180014396  mov     ebx, eax
0x180014398  test    eax, eax
0x18001439a  jns     short loc_1800143C2
0x18001439c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800143a3  jz      loc_180014465
0x1800143a9  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x1800143b0  mov     [rsp+268h+var_240], rax
0x1800143b5  mov     dword ptr [rsp+268h+var_248], 366h
0x1800143bd  jmp     loc_180014456
0x1800143c2  mov     r9d, edi; int
0x1800143c5  lea     r8, aLocationsyncen; "LocationSyncEnabled"
0x1800143cc  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x1800143d1  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800143d8  call    ?SetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z; MdmRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)
0x1800143dd  mov     ebx, eax
0x1800143df  test    eax, eax
0x1800143e1  jns     short loc_180014402
0x1800143e3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800143ea  jz      short loc_180014465
0x1800143ec  lea     rax, aChrMdmregistry_6; "CHR(MdmRegistry::SetBOOLValue(wszKey, c"...
0x1800143f3  mov     [rsp+268h+var_240], rax
0x1800143f8  mov     dword ptr [rsp+268h+var_248], 368h
0x180014400  jmp     short loc_180014456
0x180014402  mov     rcx, cs:WNF_SHEL_SETTINGS_CHANGED
0x180014409  lea     r8, [rsp+268h+var_234]
0x18001440e  mov     r9d, 4
0x180014414  mov     [rsp+268h+var_248], 0
0x18001441d  xor     edx, edx
0x18001441f  call    cs:__imp_RtlPublishWnfStateData
0x180014426  nop     dword ptr [rax+rax+00h]
0x18001442b  test    eax, eax
0x18001442d  jz      short loc_180014465
0x18001442f  mov     ebx, eax
0x180014431  or      ebx, 10000000h
0x180014437  jge     short loc_180014465
0x180014439  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014440  jz      short loc_180014465
0x180014442  lea     rax, aChrHresultNtst; "CHR(((HRESULT) ((ntstatus) | 0x10000000"...
0x180014449  mov     [rsp+268h+var_240], rax
0x18001444e  mov     dword ptr [rsp+268h+var_248], 375h
0x180014456  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001445d  mov     r8d, ebx
0x180014460  call    McTemplateU0dsqs_EventWriteTransfer
0x180014465  mov     eax, ebx
0x180014467  mov     rcx, [rsp+268h+var_18]
0x18001446f  xor     rcx, rsp; StackCookie
0x180014472  call    __security_check_cookie
0x180014477  mov     rbx, [rsp+268h+arg_8]
0x18001447f  add     rsp, 260h
0x180014486  pop     rdi
0x180014487  retn
```
