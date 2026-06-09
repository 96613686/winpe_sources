# MdmIsFindMyDeviceEnabled(int *,int *)

- ea: `0x180003d40`
- end: `0x180003f7d`
- name: `?MdmIsFindMyDeviceEnabled@@YAJPEAH0@Z`
- size: `573`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005790`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180003d40`
- `0x180006548`
- `0x1800129b0`
- `0x1800132d4`
- `0x18001cb38`

## string_xrefs

- `0x180003d96`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003dc2`: `CPR(pfConfiguredByPolicy)`
- `0x180003edd`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180003e54`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180003ec9`: `CHR(MdmRegistry::GetBOOLValue(c_szFMDSettingRegistryRootPhone, c_szFMDEnabledValueName, *pfEnabled))`

## pseudocode

```c
__int64 __fastcall MdmIsFindMyDeviceEnabled(int *a1, int *a2)
{
  int v4; // r8d
  int IsManagedFmdEnabled; // ebx
  char v7; // [rsp+20h] [rbp-258h]
  const char *v8; // [rsp+28h] [rbp-250h]
  unsigned int v9[4]; // [rsp+30h] [rbp-248h] BYREF
  unsigned __int16 v10[264]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a1 )
  {
    v4 = -2147024809;
    IsManagedFmdEnabled = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v8 = "CPR(pfEnabled)";
      v7 = -46;
LABEL_4:
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        v4,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        v7,
        (__int64)v8);
      return (unsigned int)IsManagedFmdEnabled;
    }
    return (unsigned int)IsManagedFmdEnabled;
  }
  if ( !a2 )
  {
    IsManagedFmdEnabled = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        211,
        (__int64)"CPR(pfConfiguredByPolicy)");
    return (unsigned int)IsManagedFmdEnabled;
  }
  IsManagedFmdEnabled = MdmSettings::IsManagedFmdEnabled(a1);
  if ( IsManagedFmdEnabled == 1 )
  {
    *a2 = 0;
    memset_0(v10, 0, 0x208u);
    v9[0] = 260;
    IsManagedFmdEnabled = MdmRegistry::GetBOOLValue(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\Settings\\FindMyPhone",
                            L"LocationSyncEnabledOverride",
                            a1);
    if ( IsManagedFmdEnabled < 0 )
    {
      IsManagedFmdEnabled = GetMdmCommonSettingValuesPersistedLocation(v10, v9);
      if ( IsManagedFmdEnabled >= 0 )
      {
        IsManagedFmdEnabled = MdmRegistry::GetBOOLValue(HKEY_LOCAL_MACHINE, v10, L"LocationSyncEnabled", a1);
        if ( IsManagedFmdEnabled < 0 )
        {
          IsManagedFmdEnabled = MdmRegistry::GetBOOLValue(
                                  HKEY_LOCAL_MACHINE,
                                  L"Software\\Microsoft\\Settings\\FindMyDevice",
                                  L"LocationSyncEnabled",
                                  a1);
          if ( IsManagedFmdEnabled < 0 )
          {
            IsManagedFmdEnabled = MdmRegistry::GetBOOLValue(
                                    HKEY_LOCAL_MACHINE,
                                    L"Software\\Microsoft\\Settings\\FindMyPhone",
                                    L"LocationSyncEnabled",
                                    a1);
            if ( IsManagedFmdEnabled < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                (_DWORD)a1,
                (_DWORD)a2,
                IsManagedFmdEnabled,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
                18,
                (__int64)"CHR(MdmRegistry::GetBOOLValue(c_szFMDSettingRegistryRootPhone, c_szFMDEnabledValueName, *pfEnabled))");
          }
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          (_DWORD)a2,
          IsManagedFmdEnabled,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          5,
          (__int64)"CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))");
      }
    }
    if ( IsManagedFmdEnabled == -2147023728 || IsManagedFmdEnabled == -2147024894 )
    {
      *a1 = 0;
      return 0;
    }
    if ( IsManagedFmdEnabled < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v8 = "CHR(MdmSettings::IsUnmanagedFmdEnabled(pfEnabled))";
      v7 = -38;
LABEL_24:
      v4 = IsManagedFmdEnabled;
      goto LABEL_4;
    }
  }
  else
  {
    if ( IsManagedFmdEnabled >= 0 )
    {
      *a2 = 1;
      return (unsigned int)IsManagedFmdEnabled;
    }
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v8 = "CHR(hr)";
      v7 = -34;
      goto LABEL_24;
    }
  }
  return (unsigned int)IsManagedFmdEnabled;
}

```

## disassembly

```asm
0x180003d40  mov     [rsp+arg_10], rbx
0x180003d45  push    rbp
0x180003d46  push    rsi
0x180003d47  push    rdi
0x180003d48  sub     rsp, 260h
0x180003d4f  mov     rax, cs:__security_cookie
0x180003d56  xor     rax, rsp
0x180003d59  mov     [rsp+278h+var_28], rax
0x180003d61  mov     rsi, rdx
0x180003d64  mov     rdi, rcx
0x180003d67  test    rcx, rcx
0x180003d6a  jnz     short loc_180003DA7
0x180003d6c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003d73  mov     r8d, 80070057h
0x180003d79  mov     ebx, r8d
0x180003d7c  jz      loc_180003F58
0x180003d82  lea     rax, aCprPfenabled; "CPR(pfEnabled)"
0x180003d89  mov     [rsp+278h+var_250], rax
0x180003d8e  mov     dword ptr [rsp+278h+var_258], 2D2h
0x180003d96  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003d9d  call    McTemplateU0dsqs_EventWriteTransfer
0x180003da2  jmp     loc_180003F58
0x180003da7  test    rsi, rsi
0x180003daa  jnz     short loc_180003DD8
0x180003dac  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003db3  mov     r8d, 80070057h
0x180003db9  mov     ebx, r8d
0x180003dbc  jz      loc_180003F58
0x180003dc2  lea     rax, aCprPfconfigure; "CPR(pfConfiguredByPolicy)"
0x180003dc9  mov     [rsp+278h+var_250], rax
0x180003dce  mov     dword ptr [rsp+278h+var_258], 2D3h
0x180003dd6  jmp     short loc_180003D96
0x180003dd8  call    ?IsManagedFmdEnabled@MdmSettings@@SAJPEAH@Z; MdmSettings::IsManagedFmdEnabled(int *)
0x180003ddd  mov     ebx, eax
0x180003ddf  cmp     eax, 1
0x180003de2  jnz     loc_180003F2F
0x180003de8  xor     edx, edx; Val
0x180003dea  mov     dword ptr [rsi], 0
0x180003df0  mov     r8d, 208h; Size
0x180003df6  lea     rcx, [rsp+278h+var_238]; void *
0x180003dfb  call    memset_0
0x180003e00  mov     rbp, 0FFFFFFFF80000002h
0x180003e07  mov     [rsp+278h+var_248], 104h
0x180003e0f  mov     rcx, rbp; HKEY
0x180003e12  lea     r8, aLocationsyncen_0; "LocationSyncEnabledOverride"
0x180003e19  mov     r9, rdi; int *
0x180003e1c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Settings\\FindMyPh"...
0x180003e23  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003e28  mov     ebx, eax
0x180003e2a  test    eax, eax
0x180003e2c  jns     loc_180003EEC
0x180003e32  lea     rdx, [rsp+278h+var_248]; unsigned int *
0x180003e37  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003e3c  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180003e41  mov     ebx, eax
0x180003e43  test    eax, eax
0x180003e45  jns     short loc_180003E6A
0x180003e47  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003e4e  jz      loc_180003EEC
0x180003e54  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180003e5b  mov     [rsp+278h+var_250], rax
0x180003e60  mov     dword ptr [rsp+278h+var_258], 305h
0x180003e68  jmp     short loc_180003EDD
0x180003e6a  lea     rsi, aLocationsyncen; "LocationSyncEnabled"
0x180003e71  mov     r9, rdi; int *
0x180003e74  mov     r8, rsi; unsigned __int16 *
0x180003e77  lea     rdx, [rsp+278h+var_238]; unsigned __int16 *
0x180003e7c  mov     rcx, rbp; HKEY
0x180003e7f  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003e84  mov     ebx, eax
0x180003e86  test    eax, eax
0x180003e88  jns     short loc_180003EEC
0x180003e8a  mov     r9, rdi; int *
0x180003e8d  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Settings\\FindMyDe"...
0x180003e94  mov     r8, rsi; unsigned __int16 *
0x180003e97  mov     rcx, rbp; HKEY
0x180003e9a  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003e9f  mov     ebx, eax
0x180003ea1  test    eax, eax
0x180003ea3  jns     short loc_180003EEC
0x180003ea5  mov     r9, rdi; int *
0x180003ea8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Settings\\FindMyPh"...
0x180003eaf  mov     r8, rsi; unsigned __int16 *
0x180003eb2  mov     rcx, rbp; HKEY
0x180003eb5  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003eba  mov     ebx, eax
0x180003ebc  test    eax, eax
0x180003ebe  jns     short loc_180003EEC
0x180003ec0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003ec7  jz      short loc_180003EEC
0x180003ec9  lea     rax, aChrMdmregistry_22; "CHR(MdmRegistry::GetBOOLValue(c_szFMDSe"...
0x180003ed0  mov     [rsp+278h+var_250], rax
0x180003ed5  mov     dword ptr [rsp+278h+var_258], 312h
0x180003edd  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003ee4  mov     r8d, ebx
0x180003ee7  call    McTemplateU0dsqs_EventWriteTransfer
0x180003eec  cmp     ebx, 80070490h
0x180003ef2  jz      short loc_180003F25
0x180003ef4  cmp     ebx, 80070002h
0x180003efa  jz      short loc_180003F25
0x180003efc  test    ebx, ebx
0x180003efe  jns     short loc_180003F58
0x180003f00  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003f07  jz      short loc_180003F58
0x180003f09  lea     rax, aChrMdmsettings_11; "CHR(MdmSettings::IsUnmanagedFmdEnabled("...
0x180003f10  mov     [rsp+278h+var_250], rax
0x180003f15  mov     dword ptr [rsp+278h+var_258], 2DAh
0x180003f1d  mov     r8d, ebx
0x180003f20  jmp     loc_180003D96
0x180003f25  mov     dword ptr [rdi], 0
0x180003f2b  xor     ebx, ebx
0x180003f2d  jmp     short loc_180003F58
0x180003f2f  test    ebx, ebx
0x180003f31  jns     short loc_180003F52
0x180003f33  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003f3a  jz      short loc_180003F58
0x180003f3c  lea     rax, aChrHr; "CHR(hr)"
0x180003f43  mov     [rsp+278h+var_250], rax
0x180003f48  mov     dword ptr [rsp+278h+var_258], 2DEh
0x180003f50  jmp     short loc_180003F1D
0x180003f52  mov     dword ptr [rsi], 1
0x180003f58  mov     eax, ebx
0x180003f5a  mov     rcx, [rsp+278h+var_28]
0x180003f62  xor     rcx, rsp; StackCookie
0x180003f65  call    __security_check_cookie
0x180003f6a  mov     rbx, [rsp+278h+arg_10]
0x180003f72  add     rsp, 260h
0x180003f79  pop     rdi
0x180003f7a  pop     rsi
0x180003f7b  pop     rbp
0x180003f7c  retn
```
