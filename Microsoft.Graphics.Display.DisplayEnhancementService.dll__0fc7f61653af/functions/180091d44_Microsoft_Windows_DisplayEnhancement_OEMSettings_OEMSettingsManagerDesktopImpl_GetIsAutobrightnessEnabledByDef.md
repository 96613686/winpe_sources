# Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetIsAutobrightnessEnabledByDefaultFromPowerGuids(void)

- ea: `0x180091d44`
- end: `0x180091e6c`
- name: `?GetIsAutobrightnessEnabledByDefaultFromPowerGuids@OEMSettingsManagerDesktopImpl@OEMSettings@DisplayEnhancement@Windows@Microsoft@@AEAA_NXZ`
- size: `296`
- prototype: `bool __fastcall(Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180091f7c`

## callees

- `0x18000fa0c`
- `0x18006ce0c`
- `0x180091d44`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180091d74`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x180091d74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091e59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091e59`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x180091dd1`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x180091dd1`
- `POWRPROF!PowerReadACDefaultIndex` at `0x180091e13`
- `POWRPROF!PowerReadACDefaultIndex` at `0x180091e13`

## string_xrefs

- `0x180091d86`: `onecoreuap\drivers\mobilepc\displayenhancement\service\oemsettings\desktop\lib\oemsettingsmanagerdesktop.cpp`
- `0x180091de3`: `onecoreuap\drivers\mobilepc\displayenhancement\service\oemsettings\desktop\lib\oemsettingsmanagerdesktop.cpp`
- `0x180091e25`: `onecoreuap\drivers\mobilepc\displayenhancement\service\oemsettings\desktop\lib\oemsettingsmanagerdesktop.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl::GetIsAutobrightnessEnabledByDefaultFromPowerGuids(
        Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl *this)
{
  bool v1; // bl
  DWORD ActiveScheme; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  const char *v5; // r9
  GUID *v6; // rcx
  char result; // al
  unsigned int DcDefaultIndex; // [rsp+20h] [rbp-38h]
  unsigned int DcDefaultIndexa; // [rsp+20h] [rbp-38h]
  unsigned int DcDefaultIndexb; // [rsp+20h] [rbp-38h]
  GUID **p_SchemePersonalityGuid; // [rsp+30h] [rbp-28h] BYREF
  GUID *v12; // [rsp+38h] [rbp-20h] BYREF
  char v13; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingsManagerDesktopImpl *v15; // [rsp+60h] [rbp+8h] BYREF
  DWORD AcDefaultIndex; // [rsp+68h] [rbp+10h] BYREF
  GUID *SchemePersonalityGuid; // [rsp+70h] [rbp+18h] BYREF

  v15 = this;
  SchemePersonalityGuid = 0;
  p_SchemePersonalityGuid = &SchemePersonalityGuid;
  v12 = 0;
  v1 = 1;
  v13 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &v12);
  try
  {
    if ( ActiveScheme )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\oemsettings\\desktop\\lib\\oemsettings"
                      "managerdesktop.cpp",
        (const char *)ActiveScheme,
        DcDefaultIndex);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_SchemePersonalityGuid);
    LODWORD(v15) = 0;
    AcDefaultIndex = 0;
    v3 = PowerReadDCDefaultIndex(
           0,
           SchemePersonalityGuid,
           &GUID_VIDEO_SUBGROUP,
           &GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS,
           (LPDWORD)&v15);
    if ( v3 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x229,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\oemsettings\\desktop\\lib\\oemsettings"
                      "managerdesktop.cpp",
        (const char *)v3,
        DcDefaultIndexa);
    v4 = PowerReadACDefaultIndex(
           0,
           SchemePersonalityGuid,
           &GUID_VIDEO_SUBGROUP,
           &GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS,
           &AcDefaultIndex);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\oemsettings\\desktop\\lib\\oemsettings"
                      "managerdesktop.cpp",
        (const char *)v4,
        DcDefaultIndexb);
    if ( !(_DWORD)v15 )
      v1 = AcDefaultIndex != 0;
    v6 = SchemePersonalityGuid;
    SchemePersonalityGuid = 0;
    if ( v6 )
      LocalFree(v6);
    result = v1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\oemsettings\\desktop\\lib\\oemsettingsma"
                    "nagerdesktop.cpp",
      v5);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180091d44  mov     r11, rsp
0x180091d47  mov     [r11+8], rcx
0x180091d4b  push    rbx
0x180091d4c  sub     rsp, 50h
0x180091d50  mov     qword ptr [r11+18h], 0
0x180091d58  lea     rax, [r11+18h]
0x180091d5c  mov     [r11-28h], rax
0x180091d60  mov     qword ptr [r11-20h], 0
0x180091d68  mov     bl, 1
0x180091d6a  mov     [rsp+58h+var_18], bl
0x180091d6e  lea     rdx, [r11-20h]; ActivePolicyGuid
0x180091d72  xor     ecx, ecx; UserRootPowerKey
0x180091d74  call    cs:__imp_PowerGetActiveScheme
0x180091d7a  mov     rcx, [rsp+58h]; this
0x180091d7f  test    eax, eax
0x180091d81  jz      short loc_180091D98
0x180091d83  mov     r9d, eax; char *
0x180091d86  lea     r8, aOnecoreuapDriv_24; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180091d8d  mov     edx, 221h; void *
0x180091d92  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180091d98  lea     rcx, [rsp+58h+var_28]
0x180091d9d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180091da2  mov     dword ptr [rsp+58h+arg_0], 0
0x180091daa  mov     [rsp+58h+AcDefaultIndex], 0
0x180091db2  lea     rax, [rsp+58h+arg_0]
0x180091db7  mov     qword ptr [rsp+58h+DcDefaultIndex], rax; unsigned int
0x180091dbc  lea     r9, GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS; PowerSettingGuid
0x180091dc3  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180091dca  mov     rdx, [rsp+58h+SchemePersonalityGuid]; SchemePersonalityGuid
0x180091dcf  xor     ecx, ecx; RootPowerKey
0x180091dd1  call    cs:__imp_PowerReadDCDefaultIndex
0x180091dd7  mov     rcx, [rsp+58h]; this
0x180091ddc  test    eax, eax
0x180091dde  jz      short loc_180091DF4
0x180091de0  mov     r9d, eax; char *
0x180091de3  lea     r8, aOnecoreuapDriv_24; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180091dea  mov     edx, 229h; void *
0x180091def  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180091df4  lea     rax, [rsp+58h+AcDefaultIndex]
0x180091df9  mov     qword ptr [rsp+58h+DcDefaultIndex], rax; unsigned int
0x180091dfe  lea     r9, GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS; PowerSettingGuid
0x180091e05  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180091e0c  mov     rdx, [rsp+58h+SchemePersonalityGuid]; SchemePersonalityGuid
0x180091e11  xor     ecx, ecx; RootPowerKey
0x180091e13  call    cs:__imp_PowerReadACDefaultIndex
0x180091e19  mov     rcx, [rsp+58h]; this
0x180091e1e  test    eax, eax
0x180091e20  jz      short loc_180091E36
0x180091e22  mov     r9d, eax; char *
0x180091e25  lea     r8, aOnecoreuapDriv_24; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180091e2c  mov     edx, 22Eh; void *
0x180091e31  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180091e36  cmp     dword ptr [rsp+58h+arg_0], 0
0x180091e3b  jnz     short loc_180091E46
0x180091e3d  cmp     [rsp+58h+AcDefaultIndex], 0
0x180091e42  jnz     short loc_180091E46
0x180091e44  xor     bl, bl
0x180091e46  mov     rcx, [rsp+58h+SchemePersonalityGuid]; hMem
0x180091e4b  mov     [rsp+58h+SchemePersonalityGuid], 0
0x180091e54  test    rcx, rcx
0x180091e57  jz      short loc_180091E5F
0x180091e59  call    cs:__imp_LocalFree
0x180091e5f  mov     al, bl
0x180091e61  jmp     short loc_180091E65
0x180091e63  mov     al, 1
0x180091e65  add     rsp, 50h
0x180091e69  pop     rbx
0x180091e6a  retn
```
