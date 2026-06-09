# ReadUninstallWindow(UnBCL::RegistryKey *,ulong &,ulong &)

- ea: `0x18000ae40`
- end: `0x18000b40e`
- name: `?ReadUninstallWindow@@YAXPEAVRegistryKey@UnBCL@@AEAK1@Z`
- size: `1486`
- prototype: `void __fastcall(struct UnBCL::RegistryKey *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000541c`

## callees

- `0x1800047a8`
- `0x180004c84`
- `0x18000638c`
- `0x180006744`
- `0x18000ae40`
- `0x18001aad4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b388`
- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x18000b070`
- `unbcl!?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z` at `0x18000b070`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000afec`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x18000afec`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000b03b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000b081`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000b03b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000b081`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000afd7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000b05e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000afd7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000b05e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x18000ae9d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x18000ae9d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18000aed0`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18000aed0`
- `WDSCORE!CurrentIP` at `0x18000aeeb`
- `WDSCORE!CurrentIP` at `0x18000af5c`
- `WDSCORE!CurrentIP` at `0x18000b09d`
- `WDSCORE!CurrentIP` at `0x18000b11e`
- `WDSCORE!CurrentIP` at `0x18000b1d3`
- `WDSCORE!CurrentIP` at `0x18000b228`
- `WDSCORE!CurrentIP` at `0x18000b292`
- `WDSCORE!CurrentIP` at `0x18000b332`
- `WDSCORE!CurrentIP` at `0x18000b390`
- `WDSCORE!CurrentIP` at `0x18000aeeb`
- `WDSCORE!CurrentIP` at `0x18000af5c`
- `WDSCORE!CurrentIP` at `0x18000b09d`
- `WDSCORE!CurrentIP` at `0x18000b11e`
- `WDSCORE!CurrentIP` at `0x18000b1d3`
- `WDSCORE!CurrentIP` at `0x18000b228`
- `WDSCORE!CurrentIP` at `0x18000b292`
- `WDSCORE!CurrentIP` at `0x18000b332`
- `WDSCORE!CurrentIP` at `0x18000b390`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000af49`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000afc2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b0f4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b175`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b284`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b2e9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b382`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b3e0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000af49`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000afc2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b0f4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b175`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b284`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b2e9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b382`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000b3e0`

## string_xrefs

- `0x18000ae8f`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x18000aec2`: `ConfigureFeatureUpdateUninstallPeriod`
- `0x18000ae96`: `Update`
- `0x18000aec9`: `Update`
- `0x18000af1a`: `ReadUninstallWindow`
- `0x18000af93`: `ReadUninstallWindow`
- `0x18000b102`: `ReadUninstallWindow`
- `0x18000af26`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000af9f`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000b0d1`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000b152`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000b207`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000b261`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000b2c6`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000b303`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000aef7`: `Successfully read uninstallwindow from CSP: %d`
- `0x18000af70`: `Failed reading uninstallwindow from CSP: Error:0x%x, PolicySet:%d,reading registry`
- `0x18000b04f`: `UninstallWindow`
- `0x18000b19f`: `UninstallWindow`
- `0x18000b0a9`: `Successfully read uninstallwindow from Registry: %d`
- `0x18000b12a`: `Failed reading uninstallwindow from registry: 0x%x,reading onesettings`
- `0x18000b1df`: `Successfully read uninstallwindow from Onesetting: %d`
- `0x18000b239`: `Failed reading uninstallwindow from Onesettings: 0x%x`
- `0x18000b29e`: `Using default uninstallwindow: %d days`
- `0x18000b33e`: `uninstallwindow was not in range; using default value: %d`
- `0x18000b39c`: `uninstallwindow is: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ReadUninstallWindow(struct UnBCL::RegistryKey *a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int *v3; // r14
  int IsPolicySetByMobileDeviceManager; // r15d
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  const struct UnBCL::String *v12; // rax
  struct UnBCL::RegistryKey *v13; // rax
  const struct UnBCL::String *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rcx
  struct ISetupOneSettings *v23; // r15
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  DWORD v27; // edi
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax
  DWORD v30; // edi
  __int64 v31; // rbx
  DWORD v32; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  int v38; // [rsp+20h] [rbp-C8h]
  __int64 v39; // [rsp+38h] [rbp-B0h]
  DWORD v40; // [rsp+40h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-88h]
  struct ISetupOneSettings *v42; // [rsp+68h] [rbp-80h] BYREF
  void (__fastcall ***v43)(_QWORD, __int64); // [rsp+70h] [rbp-78h] BYREF
  void **v44; // [rsp+78h] [rbp-70h] BYREF
  UnBCL::RegistryKey *v45; // [rsp+80h] [rbp-68h]
  _QWORD v46[2]; // [rsp+88h] [rbp-60h] BYREF
  _BYTE v47[80]; // [rsp+98h] [rbp-50h] BYREF
  int v51; // [rsp+100h] [rbp+18h]
  int v52; // [rsp+108h] [rbp+20h] BYREF

  v3 = a3;
  *a2 = 3;
  *a3 = 10;
  v44 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  v45 = 0;
  v52 = 0;
  v42 = 0;
  IsPolicySetByMobileDeviceManager = PolicyManager_IsPolicySetByMobileDeviceManager(
                                       L"Update",
                                       L"ConfigureFeatureUpdateUninstallPeriod",
                                       &v52);
  v41 = IsPolicySetByMobileDeviceManager;
  if ( IsPolicySetByMobileDeviceManager >= 0 )
  {
    if ( v52 )
    {
      IsPolicySetByMobileDeviceManager = PolicyManager_GetPolicyInt(
                                           L"Update",
                                           L"ConfigureFeatureUpdateUninstallPeriod",
                                           v3);
      v41 = IsPolicySetByMobileDeviceManager;
      if ( IsPolicySetByMobileDeviceManager >= 0 )
      {
        *a2 = 0;
        LastError = GetLastError();
        v7 = CurrentIP();
        v8 = ConstructPartialMsgW(0x4000000, "Successfully read uninstallwindow from CSP: %d", *v3);
        WdsSetupLogMessageW(
          v8,
          0,
          L"D",
          0,
          249,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
          L"ReadUninstallWindow",
          v7,
          LastError,
          0,
          0);
        goto LABEL_12;
      }
    }
  }
  v9 = GetLastError();
  v10 = CurrentIP();
  v11 = ConstructPartialMsgW(
          50331648,
          "Failed reading uninstallwindow from CSP: Error:0x%x, PolicySet:%d,reading registry",
          IsPolicySetByMobileDeviceManager,
          v52);
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    254,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"ReadUninstallWindow",
    v10,
    v9,
    0,
    0);
  v12 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v47, L"SYSTEM\\Setup");
  v13 = UnBCL::RegistryKey::OpenSubKey(a1, v12, 0);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v46, (__int64)v13);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=((__int64)&v44, (__int64)v46);
  v46[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)v46);
  UnBCL::String::~String((UnBCL::String *)v47);
  if ( !v45 )
    goto LABEL_6;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v14 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v47, L"UninstallWindow");
    *v3 = UnBCL::RegistryKey::GetValue(v45, v14);
    UnBCL::String::~String((UnBCL::String *)v47);
    *a2 = 2;
    v15 = GetLastError();
    v16 = CurrentIP();
    v17 = ConstructPartialMsgW(0x4000000, "Successfully read uninstallwindow from Registry: %d", *v3);
    WdsSetupLogMessageW(
      v17,
      0,
      L"D",
      0,
      268,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
      L"ReadUninstallWindow",
      v16,
      v15,
      0,
      0);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &UnBCL::Exception * `RTTI Type Descriptor', (UnBCL::Exception **)&v43) )
    {
      if ( v43 )
        (**v43)(v43, 1);
      v3 = a3;
      IsPolicySetByMobileDeviceManager = v41;
      __eh34_try_continuation(0, &UnBCL::Exception * `RTTI Type Descriptor', &loc_18000B100);
LABEL_6:
      v18 = GetLastError();
      v19 = CurrentIP();
      v20 = ConstructPartialMsgW(
              50331648,
              "Failed reading uninstallwindow from registry: 0x%x,reading onesettings",
              IsPolicySetByMobileDeviceManager);
      WdsSetupLogMessageW(
        v20,
        0,
        L"D",
        0,
        277,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
        L"ReadUninstallWindow",
        v19,
        v18,
        0,
        0);
      v51 = CreateSetupOneSettings(v22, v21, &v42);
      v23 = v42;
      if ( v51 < 0
        || (v51 = (*(__int64 (__fastcall **)(struct ISetupOneSettings *, const wchar_t *, unsigned int *))(*(_QWORD *)v42 + 8LL))(
                    v42,
                    L"UninstallWindow",
                    v3)) != 0 )
      {
        v27 = GetLastError();
        v28 = CurrentIP();
        v29 = ConstructPartialMsgW(50331648, "Failed reading uninstallwindow from Onesettings: 0x%x", v51);
        WdsSetupLogMessageW(
          v29,
          0,
          L"D",
          0,
          293,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
          L"ReadUninstallWindow",
          v28,
          v27,
          0,
          0);
        v30 = GetLastError();
        v31 = CurrentIP();
        v26 = ConstructPartialMsgW(0x4000000, "Using default uninstallwindow: %d days", *v3);
        v40 = v30;
        v39 = v31;
        v38 = 294;
      }
      else
      {
        *a2 = 1;
        v24 = GetLastError();
        v25 = CurrentIP();
        v26 = ConstructPartialMsgW(0x4000000, "Successfully read uninstallwindow from Onesetting: %d", *v3);
        v40 = v24;
        v39 = v25;
        v38 = 288;
      }
      WdsSetupLogMessageW(
        v26,
        0,
        L"D",
        0,
        v38,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
        L"ReadUninstallWindow",
        v39,
        v40,
        0,
        0);
      if ( v23 )
        (*(void (__fastcall **)(struct ISetupOneSettings *))(*(_QWORD *)v23 + 24LL))(v23);
    }
  }
LABEL_12:
  if ( *v3 - 2 > 0x3A )
  {
    *a2 = 3;
    *v3 = 10;
    v32 = GetLastError();
    v33 = CurrentIP();
    v34 = ConstructPartialMsgW(0x4000000, "uninstallwindow was not in range; using default value: %d", *v3);
    WdsSetupLogMessageW(
      v34,
      0,
      L"D",
      0,
      306,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
      L"ReadUninstallWindow",
      v33,
      v32,
      0,
      0);
  }
  v35 = GetLastError();
  v36 = CurrentIP();
  v37 = ConstructPartialMsgW(0x4000000, "uninstallwindow is: %d", *v3);
  WdsSetupLogMessageW(
    v37,
    0,
    L"D",
    0,
    309,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
    L"ReadUninstallWindow",
    v36,
    v35,
    0,
    0);
  v44 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign((__int64)&v44);
}

```

## disassembly

```asm
0x18000ae40  mov     r11, rsp
0x18000ae43  mov     [r11+18h], r8
0x18000ae47  mov     [r11+10h], rdx
0x18000ae4b  mov     [r11+8], rcx
0x18000ae4f  push    rbx
0x18000ae50  push    rsi
0x18000ae51  push    rdi
0x18000ae52  push    r13
0x18000ae54  push    r14
0x18000ae56  push    r15
0x18000ae58  sub     rsp, 0B8h
0x18000ae5f  mov     r14, r8
0x18000ae62  mov     rbx, rdx
0x18000ae65  mov     dword ptr [rdx], 3
0x18000ae6b  mov     dword ptr [r8], 0Ah
0x18000ae72  lea     rax, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000ae79  mov     [r11-70h], rax
0x18000ae7d  xor     esi, esi
0x18000ae7f  mov     [r11-68h], rsi
0x18000ae83  mov     [r11+20h], esi
0x18000ae87  mov     [r11-80h], rsi
0x18000ae8b  lea     r8, [r11+20h]
0x18000ae8f  lea     rdx, aConfigurefeatu; "ConfigureFeatureUpdateUninstallPeriod"
0x18000ae96  lea     rcx, aUpdate; "Update"
0x18000ae9d  call    cs:__imp_PolicyManager_IsPolicySetByMobileDeviceManager
0x18000aea3  mov     r15d, eax
0x18000aea6  mov     [rsp+0E8h+var_88], eax
0x18000aeaa  test    eax, eax
0x18000aeac  js      loc_18000AF54
0x18000aeb2  cmp     [rsp+0E8h+arg_18], esi
0x18000aeb9  jz      loc_18000AF54
0x18000aebf  mov     r8, r14
0x18000aec2  lea     rdx, aConfigurefeatu; "ConfigureFeatureUpdateUninstallPeriod"
0x18000aec9  lea     rcx, aUpdate; "Update"
0x18000aed0  call    cs:__imp_PolicyManager_GetPolicyInt
0x18000aed6  mov     r15d, eax
0x18000aed9  mov     [rsp+0E8h+var_88], eax
0x18000aedd  test    eax, eax
0x18000aedf  js      short loc_18000AF54
0x18000aee1  mov     [rbx], esi
0x18000aee3  call    cs:__imp_GetLastError
0x18000aee9  mov     edi, eax
0x18000aeeb  call    cs:__imp_CurrentIP
0x18000aef1  mov     rbx, rax
0x18000aef4  mov     r8d, [r14]
0x18000aef7  lea     rdx, aSuccessfullyRe_0; "Successfully read uninstallwindow from "...
0x18000aefe  mov     ecx, 4000000h; unsigned int
0x18000af03  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000af08  mov     [rsp+0E8h+var_98], esi
0x18000af0c  mov     [rsp+0E8h+var_A0], rsi
0x18000af11  mov     [rsp+0E8h+var_A8], edi
0x18000af15  mov     [rsp+0E8h+var_B0], rbx
0x18000af1a  lea     r13, aReaduninstallw; "ReadUninstallWindow"
0x18000af21  mov     [rsp+0E8h+var_B8], r13
0x18000af26  lea     r15, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000af2d  mov     [rsp+0E8h+var_C0], r15
0x18000af32  mov     [rsp+0E8h+var_C8], 0F9h
0x18000af3a  xor     r9d, r9d
0x18000af3d  lea     r8, aD_0; "D"
0x18000af44  xor     edx, edx
0x18000af46  mov     rcx, rax
0x18000af49  call    cs:__imp_WdsSetupLogMessageW
0x18000af4f  jmp     loc_18000B30A
0x18000af54  call    cs:__imp_GetLastError
0x18000af5a  mov     edi, eax
0x18000af5c  call    cs:__imp_CurrentIP
0x18000af62  mov     rbx, rax
0x18000af65  mov     r9d, [rsp+0E8h+arg_18]
0x18000af6d  mov     r8d, r15d
0x18000af70  lea     rdx, aFailedReadingU_1; "Failed reading uninstallwindow from CSP"...
0x18000af77  mov     ecx, 3000000h; unsigned int
0x18000af7c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000af81  mov     [rsp+0E8h+var_98], esi
0x18000af85  mov     [rsp+0E8h+var_A0], rsi
0x18000af8a  mov     [rsp+0E8h+var_A8], edi
0x18000af8e  mov     [rsp+0E8h+var_B0], rbx
0x18000af93  lea     r13, aReaduninstallw; "ReadUninstallWindow"
0x18000af9a  mov     [rsp+0E8h+var_B8], r13
0x18000af9f  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000afa6  mov     [rsp+0E8h+var_C0], rcx
0x18000afab  mov     [rsp+0E8h+var_C8], 0FEh
0x18000afb3  xor     r9d, r9d
0x18000afb6  lea     r8, aD_0; "D"
0x18000afbd  xor     edx, edx
0x18000afbf  mov     rcx, rax
0x18000afc2  call    cs:__imp_WdsSetupLogMessageW
0x18000afc8  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18000afcf  lea     rcx, [rsp+0E8h+var_50]
0x18000afd7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000afdd  nop
0x18000afde  xor     r8d, r8d
0x18000afe1  mov     rdx, rax
0x18000afe4  mov     rcx, [rsp+0E8h+arg_0]
0x18000afec  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18000aff2  mov     rdx, rax
0x18000aff5  lea     rcx, [rsp+0E8h+var_60]
0x18000affd  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x18000b002  nop
0x18000b003  lea     rdx, [rsp+0E8h+var_60]
0x18000b00b  lea     rcx, [rsp+0E8h+var_70]
0x18000b010  call    ??4?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=(UnBCL::SmartPtr<UnBCL::RegistryKey> const &)
0x18000b015  nop
0x18000b016  lea     rax, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000b01d  mov     [rsp+0E8h+var_60], rax
0x18000b025  lea     rcx, [rsp+0E8h+var_60]
0x18000b02d  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000b032  nop
0x18000b033  lea     rcx, [rsp+0E8h+var_50]
0x18000b03b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000b041  cmp     [rsp+0E8h+var_68], rsi
0x18000b049  jz      loc_18000B116
0x18000b04f  lea     rdx, aUninstallwindo_1; "UninstallWindow"
0x18000b056  lea     rcx, [rsp+0E8h+var_50]
0x18000b05e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000b064  nop
0x18000b065  mov     rdx, rax
0x18000b068  mov     rcx, [rsp+0E8h+var_68]
0x18000b070  call    cs:__imp_?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z; UnBCL::RegistryKey::GetValue(UnBCL::String const *)
0x18000b076  mov     [r14], eax
0x18000b079  lea     rcx, [rsp+0E8h+var_50]
0x18000b081  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18000b087  mov     rax, [rsp+0E8h+arg_8]
0x18000b08f  mov     dword ptr [rax], 2
0x18000b095  call    cs:__imp_GetLastError
0x18000b09b  mov     edi, eax
0x18000b09d  call    cs:__imp_CurrentIP
0x18000b0a3  mov     rbx, rax
0x18000b0a6  mov     r8d, [r14]
0x18000b0a9  lea     rdx, aSuccessfullyRe_1; "Successfully read uninstallwindow from "...
0x18000b0b0  mov     ecx, 4000000h; unsigned int
0x18000b0b5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b0ba  mov     [rsp+0E8h+var_98], esi
0x18000b0be  mov     [rsp+0E8h+var_A0], rsi
0x18000b0c3  mov     [rsp+0E8h+var_A8], edi
0x18000b0c7  mov     [rsp+0E8h+var_B0], rbx
0x18000b0cc  mov     [rsp+0E8h+var_B8], r13
0x18000b0d1  lea     r15, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000b0d8  mov     [rsp+0E8h+var_C0], r15
0x18000b0dd  mov     [rsp+0E8h+var_C8], 10Ch
0x18000b0e5  xor     r9d, r9d
0x18000b0e8  lea     r8, aD_0; "D"
0x18000b0ef  xor     edx, edx
0x18000b0f1  mov     rcx, rax
0x18000b0f4  call    cs:__imp_WdsSetupLogMessageW
0x18000b0fa  nop
0x18000b0fb  jmp     loc_18000B30A
0x18000b100  xor     esi, esi
0x18000b102  lea     r13, aReaduninstallw; "ReadUninstallWindow"
0x18000b109  mov     r14, [rsp+0E8h+arg_10]
0x18000b111  mov     r15d, [rsp+0E8h+var_88]
0x18000b116  call    cs:__imp_GetLastError
0x18000b11c  mov     edi, eax
0x18000b11e  call    cs:__imp_CurrentIP
0x18000b124  mov     rbx, rax
0x18000b127  mov     r8d, r15d
0x18000b12a  lea     rdx, aFailedReadingU; "Failed reading uninstallwindow from reg"...
0x18000b131  mov     ecx, 3000000h; unsigned int
0x18000b136  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b13b  mov     [rsp+0E8h+var_98], esi
0x18000b13f  mov     [rsp+0E8h+var_A0], rsi
0x18000b144  mov     [rsp+0E8h+var_A8], edi
0x18000b148  mov     [rsp+0E8h+var_B0], rbx
0x18000b14d  mov     [rsp+0E8h+var_B8], r13
0x18000b152  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000b159  mov     [rsp+0E8h+var_C0], rcx
0x18000b15e  mov     [rsp+0E8h+var_C8], 115h
0x18000b166  xor     r9d, r9d
0x18000b169  lea     r8, aD_0; "D"
0x18000b170  xor     edx, edx
0x18000b172  mov     rcx, rax
0x18000b175  call    cs:__imp_WdsSetupLogMessageW
0x18000b17b  lea     r8, [rsp+0E8h+var_80]; struct ISetupOneSettings **
0x18000b180  call    ?CreateSetupOneSettings@@YAJPEBG0PEAPEAUISetupOneSettings@@@Z; CreateSetupOneSettings(ushort const *,ushort const *,ISetupOneSettings * *)
0x18000b185  mov     dword ptr [rsp+0E8h+arg_10], eax
0x18000b18c  mov     r15, [rsp+0E8h+var_80]
0x18000b191  test    eax, eax
0x18000b193  js      loc_18000B220
0x18000b199  mov     rax, [r15]
0x18000b19c  mov     r8, r14
0x18000b19f  lea     rdx, aUninstallwindo_1; "UninstallWindow"
0x18000b1a6  mov     rcx, r15
0x18000b1a9  mov     rax, [rax+8]
0x18000b1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b2  mov     dword ptr [rsp+0E8h+arg_10], eax
0x18000b1b9  test    eax, eax
0x18000b1bb  jnz     short loc_18000B220
0x18000b1bd  mov     rax, [rsp+0E8h+arg_8]
0x18000b1c5  mov     dword ptr [rax], 1
0x18000b1cb  call    cs:__imp_GetLastError
0x18000b1d1  mov     edi, eax
0x18000b1d3  call    cs:__imp_CurrentIP
0x18000b1d9  mov     rbx, rax
0x18000b1dc  mov     r8d, [r14]
0x18000b1df  lea     rdx, aSuccessfullyRe; "Successfully read uninstallwindow from "...
0x18000b1e6  mov     ecx, 4000000h; unsigned int
0x18000b1eb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b1f0  mov     [rsp+0E8h+var_98], esi
0x18000b1f4  mov     [rsp+0E8h+var_A0], rsi
0x18000b1f9  mov     [rsp+0E8h+var_A8], edi
0x18000b1fd  mov     [rsp+0E8h+var_B0], rbx
0x18000b202  mov     [rsp+0E8h+var_B8], r13
0x18000b207  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000b20e  mov     [rsp+0E8h+var_C0], rcx
0x18000b213  mov     [rsp+0E8h+var_C8], 120h
0x18000b21b  jmp     loc_18000B2DA
0x18000b220  call    cs:__imp_GetLastError
0x18000b226  mov     edi, eax
0x18000b228  call    cs:__imp_CurrentIP
0x18000b22e  mov     rbx, rax
0x18000b231  mov     r8d, dword ptr [rsp+0E8h+arg_10]
0x18000b239  lea     rdx, aFailedReadingU_0; "Failed reading uninstallwindow from One"...
0x18000b240  mov     ecx, 3000000h; unsigned int
0x18000b245  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b24a  mov     [rsp+0E8h+var_98], esi
0x18000b24e  mov     [rsp+0E8h+var_A0], rsi
0x18000b253  mov     [rsp+0E8h+var_A8], edi
0x18000b257  mov     [rsp+0E8h+var_B0], rbx
0x18000b25c  mov     [rsp+0E8h+var_B8], r13
0x18000b261  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000b268  mov     [rsp+0E8h+var_C0], rcx
0x18000b26d  mov     [rsp+0E8h+var_C8], 125h
0x18000b275  xor     r9d, r9d
0x18000b278  lea     r8, aD_0; "D"
0x18000b27f  xor     edx, edx
0x18000b281  mov     rcx, rax
0x18000b284  call    cs:__imp_WdsSetupLogMessageW
0x18000b28a  call    cs:__imp_GetLastError
0x18000b290  mov     edi, eax
0x18000b292  call    cs:__imp_CurrentIP
0x18000b298  mov     rbx, rax
0x18000b29b  mov     r8d, [r14]
0x18000b29e  lea     rdx, aUsingDefaultUn; "Using default uninstallwindow: %d days"
0x18000b2a5  mov     ecx, 4000000h; unsigned int
0x18000b2aa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b2af  mov     [rsp+0E8h+var_98], esi
0x18000b2b3  mov     [rsp+0E8h+var_A0], rsi
0x18000b2b8  mov     [rsp+0E8h+var_A8], edi
0x18000b2bc  mov     [rsp+0E8h+var_B0], rbx
0x18000b2c1  mov     [rsp+0E8h+var_B8], r13
0x18000b2c6  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000b2cd  mov     [rsp+0E8h+var_C0], rcx
0x18000b2d2  mov     [rsp+0E8h+var_C8], 126h
0x18000b2da  xor     r9d, r9d
0x18000b2dd  lea     r8, aD_0; "D"
0x18000b2e4  xor     edx, edx
0x18000b2e6  mov     rcx, rax
0x18000b2e9  call    cs:__imp_WdsSetupLogMessageW
0x18000b2ef  test    r15, r15
0x18000b2f2  jz      short loc_18000B303
0x18000b2f4  mov     rax, [r15]
0x18000b2f7  mov     rcx, r15
0x18000b2fa  mov     rax, [rax+18h]
0x18000b2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b303  lea     r15, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18000b30a  mov     eax, [r14]
0x18000b30d  sub     eax, 2
0x18000b310  cmp     eax, 3Ah ; ':'
0x18000b313  jbe     short loc_18000B388
0x18000b315  mov     rax, [rsp+0E8h+arg_8]
0x18000b31d  mov     dword ptr [rax], 3
0x18000b323  mov     dword ptr [r14], 0Ah
0x18000b32a  call    cs:__imp_GetLastError
0x18000b330  mov     edi, eax
0x18000b332  call    cs:__imp_CurrentIP
0x18000b338  mov     rbx, rax
0x18000b33b  mov     r8d, [r14]
0x18000b33e  lea     rdx, aUninstallwindo; "uninstallwindow was not in range; using"...
0x18000b345  mov     ecx, 4000000h; unsigned int
0x18000b34a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b34f  mov     [rsp+0E8h+var_98], esi
0x18000b353  mov     [rsp+0E8h+var_A0], rsi
0x18000b358  mov     [rsp+0E8h+var_A8], edi
0x18000b35c  mov     [rsp+0E8h+var_B0], rbx
0x18000b361  mov     [rsp+0E8h+var_B8], r13
0x18000b366  mov     [rsp+0E8h+var_C0], r15
0x18000b36b  mov     [rsp+0E8h+var_C8], 132h
0x18000b373  xor     r9d, r9d
0x18000b376  lea     r8, aD_0; "D"
0x18000b37d  xor     edx, edx
0x18000b37f  mov     rcx, rax
0x18000b382  call    cs:__imp_WdsSetupLogMessageW
0x18000b388  call    cs:__imp_GetLastError
0x18000b38e  mov     edi, eax
0x18000b390  call    cs:__imp_CurrentIP
0x18000b396  mov     rbx, rax
0x18000b399  mov     r8d, [r14]
0x18000b39c  lea     rdx, aUninstallwindo_0; "uninstallwindow is: %d"
0x18000b3a3  mov     ecx, 4000000h; unsigned int
0x18000b3a8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b3ad  mov     [rsp+0E8h+var_98], esi
0x18000b3b1  mov     [rsp+0E8h+var_A0], rsi
0x18000b3b6  mov     [rsp+0E8h+var_A8], edi
0x18000b3ba  mov     [rsp+0E8h+var_B0], rbx
0x18000b3bf  mov     [rsp+0E8h+var_B8], r13
0x18000b3c4  mov     [rsp+0E8h+var_C0], r15
0x18000b3c9  mov     [rsp+0E8h+var_C8], 135h
0x18000b3d1  xor     r9d, r9d
0x18000b3d4  lea     r8, aD_0; "D"
0x18000b3db  xor     edx, edx
0x18000b3dd  mov     rcx, rax
  ... truncated ...
```
