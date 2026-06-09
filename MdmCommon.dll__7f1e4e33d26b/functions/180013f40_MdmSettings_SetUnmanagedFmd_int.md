# MdmSettings::SetUnmanagedFmd(int)

- ea: `0x180013f40`
- end: `0x18001407e`
- name: `?SetUnmanagedFmd@MdmSettings@@SAJH@Z`
- size: `318`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005790`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180013f40`
- `0x18001d0d0`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18001401b`
- `ntdll!RtlPublishWnfStateData` at `0x18001401b`

## string_xrefs

- `0x18001404c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013fa5`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180013fe8`: `CHR(MdmRegistry::SetBOOLValue(wszKey, c_szFMDEnabledValueName, fEnabled))`

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
            (__int64)"CHR(((HRESULT) ((ntstatus) | 0x10000000)))");
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
        (__int64)"CHR(MdmRegistry::SetBOOLValue(wszKey, c_szFMDEnabledValueName, fEnabled))");
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
      (__int64)"CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))");
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180013f40  mov     [rsp+arg_8], rbx
0x180013f45  push    rdi
0x180013f46  sub     rsp, 260h
0x180013f4d  mov     rax, cs:__security_cookie
0x180013f54  xor     rax, rsp
0x180013f57  mov     [rsp+268h+var_18], rax
0x180013f5f  mov     edi, ecx
0x180013f61  xor     edx, edx; Val
0x180013f63  lea     rcx, [rsp+268h+var_228]; void *
0x180013f68  mov     r8d, 208h; Size
0x180013f6e  call    memset_0
0x180013f73  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013f78  mov     [rsp+268h+var_238], 104h
0x180013f80  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013f85  mov     [rsp+268h+var_234], 1
0x180013f8d  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013f92  mov     ebx, eax
0x180013f94  test    eax, eax
0x180013f96  jns     short loc_180013FBE
0x180013f98  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013f9f  jz      loc_18001405B
0x180013fa5  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013fac  mov     [rsp+268h+var_240], rax
0x180013fb1  mov     dword ptr [rsp+268h+var_248], 366h
0x180013fb9  jmp     loc_18001404C
0x180013fbe  mov     r9d, edi; int
0x180013fc1  lea     r8, aLocationsyncen; "LocationSyncEnabled"
0x180013fc8  lea     rdx, [rsp+268h+var_228]; unsigned __int16 *
0x180013fcd  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180013fd4  call    ?SetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z; MdmRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)
0x180013fd9  mov     ebx, eax
0x180013fdb  test    eax, eax
0x180013fdd  jns     short loc_180013FFE
0x180013fdf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013fe6  jz      short loc_18001405B
0x180013fe8  lea     rax, aChrMdmregistry_6; "CHR(MdmRegistry::SetBOOLValue(wszKey, c"...
0x180013fef  mov     [rsp+268h+var_240], rax
0x180013ff4  mov     dword ptr [rsp+268h+var_248], 368h
0x180013ffc  jmp     short loc_18001404C
0x180013ffe  mov     rcx, cs:WNF_SHEL_SETTINGS_CHANGED
0x180014005  lea     r8, [rsp+268h+var_234]
0x18001400a  mov     r9d, 4
0x180014010  mov     [rsp+268h+var_248], 0
0x180014019  xor     edx, edx
0x18001401b  call    cs:__imp_RtlPublishWnfStateData
0x180014021  test    eax, eax
0x180014023  jz      short loc_18001405B
0x180014025  mov     ebx, eax
0x180014027  or      ebx, 10000000h
0x18001402d  jge     short loc_18001405B
0x18001402f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180014036  jz      short loc_18001405B
0x180014038  lea     rax, aChrHresultNtst; "CHR(((HRESULT) ((ntstatus) | 0x10000000"...
0x18001403f  mov     [rsp+268h+var_240], rax
0x180014044  mov     dword ptr [rsp+268h+var_248], 375h
0x18001404c  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180014053  mov     r8d, ebx
0x180014056  call    McTemplateU0dsqs_EventWriteTransfer
0x18001405b  mov     eax, ebx
0x18001405d  mov     rcx, [rsp+268h+var_18]
0x180014065  xor     rcx, rsp; StackCookie
0x180014068  call    __security_check_cookie
0x18001406d  mov     rbx, [rsp+268h+arg_8]
0x180014075  add     rsp, 260h
0x18001407c  pop     rdi
0x18001407d  retn
```
