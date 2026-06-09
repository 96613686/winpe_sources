# CDsmDeviceTask::_RemovePnPDevnode(ushort const *,bool *)

- ea: `0x1800367b4`
- end: `0x180036a11`
- name: `?_RemovePnPDevnode@CDsmDeviceTask@@AEAAJPEBGPEA_N@Z`
- size: `605`
- prototype: `int(CDsmDeviceTask *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180036680`
- `0x180036a18`

## callees

- `0x180009f20`
- `0x1800112c8`
- `0x18001af70`
- `0x18001ba48`
- `0x18001cb60`
- `0x180036038`
- `0x1800367b4`

## import_xrefs

- `DEVOBJ!DevObjDeleteDevice` at `0x180036977`
- `DEVOBJ!DevObjDeleteDevice` at `0x180036977`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18003690b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18003690b`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180036956`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180036956`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x1800368a2`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x1800368f1`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x1800368a2`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x1800368f1`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x18003687b`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x18003687b`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstallParamsW` at `0x1800368d6`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstallParamsW` at `0x1800368d6`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x18003685d`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiOpenDeviceInfoW` at `0x18003685d`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x180036806`
- `ext-ms-win-setupapi-classinstallers-l1-1-1!SetupDiCreateDeviceInfoList` at `0x180036806`

## string_xrefs

- `0x18003681c`: `onecoreuap\base\devices\setup\dsm\service\devicetask.cpp`
- `0x180036891`: `onecoreuap\base\devices\setup\dsm\service\devicetask.cpp`
- `0x18003698d`: `onecoreuap\base\devices\setup\dsm\service\devicetask.cpp`

## pseudocode

```c
__int64 __fastcall CDsmDeviceTask::_RemovePnPDevnode(CDsmDeviceTask *this, const unsigned __int16 *a2, bool *a3)
{
  bool v5; // di
  HDEVINFO DeviceInfoList; // rbx
  const char *v7; // r9
  const char *v9; // r9
  __int64 v10; // rdx
  unsigned int LastError; // edi
  const char *v12; // r9
  __int64 v13; // rdx
  unsigned int v14; // ebx
  BOOL v15; // eax
  BOOL v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+60h] [rbp-A0h]
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v16 = 0;
  v5 = 1;
  if ( (unsigned __int8)IsSetupDiCallClassInstallerPresent(this) )
  {
    DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
    if ( DeviceInfoList == (HDEVINFO)-1LL )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x97,
               (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetask.cpp",
               v7);
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    if ( !SetupDiOpenDeviceInfoW(DeviceInfoList, a2, 0, 0, &DeviceInfoData) )
    {
      v10 = 166;
LABEL_8:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v10,
                    (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetask.cpp",
                    v9);
      SetupDiDestroyDeviceInfoList(DeviceInfoList);
      return LastError;
    }
    if ( !SetupDiCallClassInstaller(5u, DeviceInfoList, &DeviceInfoData) )
    {
      v10 = 171;
      goto LABEL_8;
    }
    memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
    DeviceInstallParams.cbSize = 584;
    if ( SetupDiGetDeviceInstallParamsW(DeviceInfoList, &DeviceInfoData, &DeviceInstallParams) )
      v16 = (DeviceInstallParams.Flags & 0x180) != 0;
    SetupDiDestroyDeviceInfoList(DeviceInfoList);
    goto LABEL_20;
  }
  v17 = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( v17 == -1 )
  {
    v13 = 186;
LABEL_18:
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetask.cpp",
            v12);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v17);
    return v14;
  }
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 48;
  v19 = 0;
  if ( !(unsigned int)DevObjOpenDeviceInfo(v17, a2, 0, 0, &DeviceInfoData) )
  {
    v13 = 196;
    goto LABEL_18;
  }
  if ( !(unsigned int)DevObjDeleteDevice(v17, &DeviceInfoData, 0, &v16) )
  {
    v13 = 202;
    goto LABEL_18;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v17);
LABEL_20:
  v15 = v16;
  if ( !v16 )
    goto LABEL_24;
  if ( (byte_180059BC1 & 1) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(&userpnp_Context, &PNP_REBOOT_REQUIRED, a2);
    v15 = v16;
  }
  if ( !v15 )
LABEL_24:
    v5 = 0;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800367b4  mov     [rsp-8+arg_0], rbx
0x1800367b9  mov     [rsp-8+arg_18], rsi
0x1800367be  push    rbp
0x1800367bf  push    rdi
0x1800367c0  push    r14
0x1800367c2  lea     rbp, [rsp-1D0h]
0x1800367ca  sub     rsp, 2D0h
0x1800367d1  mov     rax, cs:__security_cookie
0x1800367d8  xor     rax, rsp
0x1800367db  mov     [rbp+1E0h+var_20], rax
0x1800367e2  mov     r14, r8
0x1800367e5  mov     [rsp+2E0h+var_2B0], 0
0x1800367ed  mov     rsi, rdx
0x1800367f0  call    IsSetupDiCallClassInstallerPresent
0x1800367f5  xor     edx, edx; hwndParent
0x1800367f7  xor     ecx, ecx; ClassGuid
0x1800367f9  mov     edi, 1
0x1800367fe  test    al, al
0x180036800  jz      loc_1800368FC
0x180036806  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18003680c  mov     rbx, rax
0x18003680f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036813  jnz     short loc_180036832
0x180036815  mov     rcx, [rbp+1E8h]; this
0x18003681c  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180036823  mov     edx, 97h; void *
0x180036828  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003682d  jmp     loc_1800369EA
0x180036832  xorps   xmm0, xmm0
0x180036835  lea     rax, [rsp+2E0h+var_2A0]
0x18003683a  movups  xmmword ptr [rsp+2E0h+var_2A0.cbSize], xmm0
0x18003683f  xor     r9d, r9d; OpenFlags
0x180036842  mov     [rsp+2E0h+var_2A0.cbSize], 20h ; ' '
0x18003684a  xor     r8d, r8d; hwndParent
0x18003684d  mov     [rsp+2E0h+DeviceInfoData], rax; DeviceInfoData
0x180036852  mov     rdx, rsi; DeviceInstanceId
0x180036855  mov     rcx, rbx; DeviceInfoSet
0x180036858  movups  xmmword ptr [rsp+2E0h+var_2A0.ClassGuid.Data4+4], xmm0
0x18003685d  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180036863  test    eax, eax
0x180036865  jnz     short loc_18003686E
0x180036867  mov     edx, 0A6h
0x18003686c  jmp     short loc_18003688A
0x18003686e  lea     r8, [rsp+2E0h+var_2A0]; DeviceInfoData
0x180036873  mov     rdx, rbx; DeviceInfoSet
0x180036876  mov     ecx, 5; InstallFunction
0x18003687b  call    cs:__imp_SetupDiCallClassInstaller
0x180036881  test    eax, eax
0x180036883  jnz     short loc_1800368AF
0x180036885  mov     edx, 0ABh; void *
0x18003688a  mov     rcx, [rbp+1E8h]; this
0x180036891  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180036898  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003689d  mov     rcx, rbx; DeviceInfoSet
0x1800368a0  mov     edi, eax
0x1800368a2  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800368a8  mov     eax, edi
0x1800368aa  jmp     loc_1800369EA
0x1800368af  xor     edx, edx; Val
0x1800368b1  lea     rcx, [rsp+2E0h+DeviceInstallParams.Flags]; void *
0x1800368b6  mov     r8d, 244h; Size
0x1800368bc  call    memset_0
0x1800368c1  lea     r8, [rsp+2E0h+DeviceInstallParams]; DeviceInstallParams
0x1800368c6  mov     [rsp+2E0h+DeviceInstallParams.cbSize], 248h
0x1800368ce  lea     rdx, [rsp+2E0h+var_2A0]; DeviceInfoData
0x1800368d3  mov     rcx, rbx; DeviceInfoSet
0x1800368d6  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x1800368dc  test    eax, eax
0x1800368de  jz      short loc_1800368EE
0x1800368e0  test    [rsp+2E0h+DeviceInstallParams.Flags], 180h
0x1800368e8  jz      short loc_1800368EE
0x1800368ea  mov     [rsp+2E0h+var_2B0], edi
0x1800368ee  mov     rcx, rbx; DeviceInfoSet
0x1800368f1  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800368f7  jmp     loc_1800369B3
0x1800368fc  xor     r9d, r9d
0x1800368ff  mov     [rsp+2E0h+DeviceInfoData], 0
0x180036908  xor     r8d, r8d
0x18003690b  call    cs:__imp_DevObjCreateDeviceInfoList
0x180036911  mov     [rsp+2E0h+var_2A8], rax
0x180036916  mov     rbx, rax
0x180036919  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003691d  jnz     short loc_180036926
0x18003691f  mov     edx, 0BAh
0x180036924  jmp     short loc_180036986
0x180036926  xorps   xmm0, xmm0
0x180036929  lea     rax, [rsp+2E0h+var_2A0]
0x18003692e  movups  xmmword ptr [rsp+2E0h+var_2A0.cbSize], xmm0
0x180036933  xor     r9d, r9d
0x180036936  mov     [rsp+2E0h+var_2A0.cbSize], 30h ; '0'
0x18003693e  xor     r8d, r8d
0x180036941  mov     [rsp+2E0h+DeviceInfoData], rax
0x180036946  mov     rdx, rsi
0x180036949  mov     rcx, rbx
0x18003694c  movups  xmmword ptr [rsp+2E0h+var_2A0.ClassGuid.Data4+4], xmm0
0x180036951  movups  [rsp+2E0h+var_280], xmm0
0x180036956  call    cs:__imp_DevObjOpenDeviceInfo
0x18003695c  test    eax, eax
0x18003695e  jnz     short loc_180036967
0x180036960  mov     edx, 0C4h
0x180036965  jmp     short loc_180036986
0x180036967  lea     r9, [rsp+2E0h+var_2B0]
0x18003696c  xor     r8d, r8d
0x18003696f  lea     rdx, [rsp+2E0h+var_2A0]
0x180036974  mov     rcx, rbx
0x180036977  call    cs:__imp_DevObjDeleteDevice
0x18003697d  test    eax, eax
0x18003697f  jnz     short loc_1800369A9
0x180036981  mov     edx, 0CAh; void *
0x180036986  mov     rcx, [rbp+1E8h]; this
0x18003698d  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180036994  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036999  lea     rcx, [rsp+2E0h+var_2A8]
0x18003699e  mov     ebx, eax
0x1800369a0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x1800369a5  mov     eax, ebx
0x1800369a7  jmp     short loc_1800369EA
0x1800369a9  lea     rcx, [rsp+2E0h+var_2A8]
0x1800369ae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x1800369b3  mov     eax, [rsp+2E0h+var_2B0]
0x1800369b7  test    eax, eax
0x1800369b9  jz      short loc_1800369E2
0x1800369bb  test    cs:byte_180059BC1, dil
0x1800369c2  jz      short loc_1800369DE
0x1800369c4  mov     r8, rsi
0x1800369c7  lea     rdx, PNP_REBOOT_REQUIRED
0x1800369ce  lea     rcx, userpnp_Context
0x1800369d5  call    McTemplateU0z_EventWriteTransfer
0x1800369da  mov     eax, [rsp+2E0h+var_2B0]
0x1800369de  test    eax, eax
0x1800369e0  jnz     short loc_1800369E5
0x1800369e2  xor     dil, dil
0x1800369e5  mov     [r14], dil
0x1800369e8  xor     eax, eax
0x1800369ea  mov     rcx, [rbp+1E0h+var_20]
0x1800369f1  xor     rcx, rsp; StackCookie
0x1800369f4  call    __security_check_cookie
0x1800369f9  lea     r11, [rsp+2E0h+var_10]
0x180036a01  mov     rbx, [r11+20h]
0x180036a05  mov     rsi, [r11+38h]
0x180036a09  mov     rsp, r11
0x180036a0c  pop     r14
0x180036a0e  pop     rdi
0x180036a0f  pop     rbp
0x180036a10  retn
```
