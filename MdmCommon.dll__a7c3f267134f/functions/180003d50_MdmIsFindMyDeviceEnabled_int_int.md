# MdmIsFindMyDeviceEnabled(int *,int *)

- ea: `0x180003d50`
- end: `0x180003f8e`
- name: `?MdmIsFindMyDeviceEnabled@@YAJPEAH0@Z`
- size: `574`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800057e0`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180003d50`
- `0x1800065c0`
- `0x180012d8c`
- `0x1800136b8`
- `0x18001d19c`

## string_xrefs

- `0x180003da6`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003dd2`: `CPR(pfConfiguredByPolicy)`
- `0x180003eed`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180003e64`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180003ed9`: `CHR(MdmRegistry::GetBOOLValue(c_szFMDSettingRegistryRootPhone, c_szFMDEnabledValueName, *pfEnabled))`

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
        v8);
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
        "CPR(pfConfiguredByPolicy)");
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
                "CHR(MdmRegistry::GetBOOLValue(c_szFMDSettingRegistryRootPhone, c_szFMDEnabledValueName, *pfEnabled))",
                *(_QWORD *)v9);
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
          "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
          *(_QWORD *)v9);
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
0x180003d50  mov     [rsp+arg_10], rbx
0x180003d55  push    rbp
0x180003d56  push    rsi
0x180003d57  push    rdi
0x180003d58  sub     rsp, 260h
0x180003d5f  mov     rax, cs:__security_cookie
0x180003d66  xor     rax, rsp
0x180003d69  mov     [rsp+278h+var_28], rax
0x180003d71  mov     rsi, rdx
0x180003d74  mov     rdi, rcx
0x180003d77  test    rcx, rcx
0x180003d7a  jnz     short loc_180003DB7
0x180003d7c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003d83  mov     r8d, 80070057h
0x180003d89  mov     ebx, r8d
0x180003d8c  jz      loc_180003F68
0x180003d92  lea     rax, aCprPfenabled; "CPR(pfEnabled)"
0x180003d99  mov     [rsp+278h+var_250], rax
0x180003d9e  mov     dword ptr [rsp+278h+var_258], 2D2h
0x180003da6  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003dad  call    McTemplateU0dsqs_EventWriteTransfer
0x180003db2  jmp     loc_180003F68
0x180003db7  test    rsi, rsi
0x180003dba  jnz     short loc_180003DE8
0x180003dbc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003dc3  mov     r8d, 80070057h
0x180003dc9  mov     ebx, r8d
0x180003dcc  jz      loc_180003F68
0x180003dd2  lea     rax, aCprPfconfigure; "CPR(pfConfiguredByPolicy)"
0x180003dd9  mov     [rsp+278h+var_250], rax
0x180003dde  mov     dword ptr [rsp+278h+var_258], 2D3h
0x180003de6  jmp     short loc_180003DA6
0x180003de8  call    ?IsManagedFmdEnabled@MdmSettings@@SAJPEAH@Z; MdmSettings::IsManagedFmdEnabled(int *)
0x180003ded  mov     ebx, eax
0x180003def  cmp     eax, 1
0x180003df2  jnz     loc_180003F3F
0x180003df8  xor     edx, edx; Val
0x180003dfa  mov     dword ptr [rsi], 0
0x180003e00  mov     r8d, 208h; Size
0x180003e06  lea     rcx, [rsp+278h+var_238]; void *
0x180003e0b  call    memset_0
0x180003e10  mov     rbp, 0FFFFFFFF80000002h
0x180003e17  mov     [rsp+278h+var_248], 104h
0x180003e1f  mov     rcx, rbp; HKEY
0x180003e22  lea     r8, aLocationsyncen_0; "LocationSyncEnabledOverride"
0x180003e29  mov     r9, rdi; int *
0x180003e2c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Settings\\FindMyPh"...
0x180003e33  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003e38  mov     ebx, eax
0x180003e3a  test    eax, eax
0x180003e3c  jns     loc_180003EFC
0x180003e42  lea     rdx, [rsp+278h+var_248]; unsigned int *
0x180003e47  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180003e4c  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180003e51  mov     ebx, eax
0x180003e53  test    eax, eax
0x180003e55  jns     short loc_180003E7A
0x180003e57  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003e5e  jz      loc_180003EFC
0x180003e64  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180003e6b  mov     [rsp+278h+var_250], rax
0x180003e70  mov     dword ptr [rsp+278h+var_258], 305h
0x180003e78  jmp     short loc_180003EED
0x180003e7a  lea     rsi, aLocationsyncen; "LocationSyncEnabled"
0x180003e81  mov     r9, rdi; int *
0x180003e84  mov     r8, rsi; unsigned __int16 *
0x180003e87  lea     rdx, [rsp+278h+var_238]; unsigned __int16 *
0x180003e8c  mov     rcx, rbp; HKEY
0x180003e8f  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003e94  mov     ebx, eax
0x180003e96  test    eax, eax
0x180003e98  jns     short loc_180003EFC
0x180003e9a  mov     r9, rdi; int *
0x180003e9d  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Settings\\FindMyDe"...
0x180003ea4  mov     r8, rsi; unsigned __int16 *
0x180003ea7  mov     rcx, rbp; HKEY
0x180003eaa  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003eaf  mov     ebx, eax
0x180003eb1  test    eax, eax
0x180003eb3  jns     short loc_180003EFC
0x180003eb5  mov     r9, rdi; int *
0x180003eb8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Settings\\FindMyPh"...
0x180003ebf  mov     r8, rsi; unsigned __int16 *
0x180003ec2  mov     rcx, rbp; HKEY
0x180003ec5  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180003eca  mov     ebx, eax
0x180003ecc  test    eax, eax
0x180003ece  jns     short loc_180003EFC
0x180003ed0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003ed7  jz      short loc_180003EFC
0x180003ed9  lea     rax, aChrMdmregistry_22; "CHR(MdmRegistry::GetBOOLValue(c_szFMDSe"...
0x180003ee0  mov     [rsp+278h+var_250], rax
0x180003ee5  mov     dword ptr [rsp+278h+var_258], 312h
0x180003eed  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003ef4  mov     r8d, ebx
0x180003ef7  call    McTemplateU0dsqs_EventWriteTransfer
0x180003efc  cmp     ebx, 80070490h
0x180003f02  jz      short loc_180003F35
0x180003f04  cmp     ebx, 80070002h
0x180003f0a  jz      short loc_180003F35
0x180003f0c  test    ebx, ebx
0x180003f0e  jns     short loc_180003F68
0x180003f10  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003f17  jz      short loc_180003F68
0x180003f19  lea     rax, aChrMdmsettings_11; "CHR(MdmSettings::IsUnmanagedFmdEnabled("...
0x180003f20  mov     [rsp+278h+var_250], rax
0x180003f25  mov     dword ptr [rsp+278h+var_258], 2DAh
0x180003f2d  mov     r8d, ebx
0x180003f30  jmp     loc_180003DA6
0x180003f35  mov     dword ptr [rdi], 0
0x180003f3b  xor     ebx, ebx
0x180003f3d  jmp     short loc_180003F68
0x180003f3f  test    ebx, ebx
0x180003f41  jns     short loc_180003F62
0x180003f43  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003f4a  jz      short loc_180003F68
0x180003f4c  lea     rax, aChrHr; "CHR(hr)"
0x180003f53  mov     [rsp+278h+var_250], rax
0x180003f58  mov     dword ptr [rsp+278h+var_258], 2DEh
0x180003f60  jmp     short loc_180003F2D
0x180003f62  mov     dword ptr [rsi], 1
0x180003f68  mov     eax, ebx
0x180003f6a  mov     rcx, [rsp+278h+var_28]
0x180003f72  xor     rcx, rsp; StackCookie
0x180003f75  call    __security_check_cookie
0x180003f7a  mov     rbx, [rsp+278h+arg_10]
0x180003f82  add     rsp, 260h
0x180003f89  pop     rdi
0x180003f8a  pop     rsi
0x180003f8b  pop     rbp
0x180003f8c  retn
```
