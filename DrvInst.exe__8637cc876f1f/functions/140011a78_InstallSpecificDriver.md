# InstallSpecificDriver

- ea: `0x140011a78`
- end: `0x140011f1e`
- name: `InstallSpecificDriver`
- size: `1190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x14001170c`
- `0x140012258`
- `0x14001a9f0`
- `0x14001bd7c`

## callees

- `0x140001fc0`
- `0x140011274`
- `0x14001167c`
- `0x140011a78`
- `0x140011f24`
- `0x14001204c`
- `0x140018dc0`
- `0x14001dc80`
- `0x140027670`
- `0x14002b7ec`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011bff`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Class_PropertyW` at `0x140011cd8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Class_PropertyW` at `0x140011cd8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140011c2e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140011c2e`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140011c1a`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x140011c1a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011b38`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011bc3`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011c5b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011d69`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011d87`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011da5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011e21`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011e4d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011ee7`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011b38`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011bc3`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011c5b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011d69`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011d87`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011da5`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011e21`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011e4d`
- `DEVRTL!DevRtlWriteTextLog` at `0x140011ee7`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140011ae4`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140011ae4`
- `ext-ms-win-drvinst-desktop-l1-1-0!InstallLegacyDeviceDriver` at `0x140011e98`
- `ext-ms-win-drvinst-desktop-l1-1-0!InstallLegacyDeviceDriver` at `0x140011e98`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140011ca1`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140011ca1`
- `drvstore!DriverStoreFindW` at `0x140011b7d`
- `drvstore!DriverStoreFindW` at `0x140011b7d`
- `drvstore!DriverStoreOpenW` at `0x140011b0e`
- `drvstore!DriverStoreOpenW` at `0x140011b0e`
- `drvstore!DriverStoreClose` at `0x140011ebf`
- `drvstore!DriverStoreClose` at `0x140011ebf`

## string_xrefs

- `0x140011b28`: `Unable to open driver store. Error = 0x%08X`
- `0x140011ba6`: `Cannot install non-native driver package '%ws'. Err = 0x%08X`
- `0x140011d52`: `Device configuration is disabled, performing standard device installation.`
- `0x140011d49`: `Force-installed driver cannot be configured, performing standard device installation.`
- `0x140011d79`: `Installing driver: %ws`
- `0x140011d97`: `Install flags: 0x%08X`
- `0x140011e17`: `Failed to configure device. Error = 0x%08X`
- `0x140011e42`: `Selected driver cannot be configured, performing standard device installation.`
- `0x140011e55`: `Unable to configure device, falling back to standard device installation.`
- `0x140011ece`: `Device install failure (0x%08X) attributed to system shutdown, retrying on next boot...`

## pseudocode

```c
__int64 __fastcall InstallSpecificDriver(__int64 a1, __int64 a2, int *a3, __int64 a4, unsigned __int16 *a5, int a6)
{
  __int64 ThreadLogToken; // rdi
  __int64 v10; // rsi
  unsigned int LastError; // ebx
  DWORD v12; // eax
  int v13; // r15d
  DWORD v14; // eax
  CONFIGRET v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // ebx
  const char *v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int *v26; // r14
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  DEVPROPTYPE *PropertyBufferSize; // [rsp+20h] [rbp-E0h]
  PULONG PropertyBufferSizea; // [rsp+20h] [rbp-E0h]
  PULONG PropertyBufferSizeb; // [rsp+20h] [rbp-E0h]
  ULONG ulFlags[2]; // [rsp+28h] [rbp-D8h]
  ULONG ulFlagsa[2]; // [rsp+28h] [rbp-D8h]
  GUID *ulFlagsb; // [rsp+28h] [rbp-D8h]
  int v38[2]; // [rsp+30h] [rbp-D0h]
  BYTE PropertyBuffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  DEVNODE pdnDevInst; // [rsp+54h] [rbp-ACh] BYREF
  DEVPROPTYPE PropertyType; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v42; // [rsp+5Ch] [rbp-A4h] BYREF
  int *v43; // [rsp+60h] [rbp-A0h]
  int v44[2]; // [rsp+68h] [rbp-98h]
  GUID ClassGUID; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v46[264]; // [rsp+80h] [rbp-80h] BYREF

  v43 = a3;
  ClassGUID = 0;
  *(_QWORD *)v44 = a1;
  PropertyType = 0;
  v42 = 0;
  PropertyBuffer[0] = 0;
  pdnDevInst = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( !a4 || !a5 )
  {
    v10 = 0;
    LastError = 87;
    goto LABEL_43;
  }
  if ( a2 )
  {
    v10 = a2;
  }
  else
  {
    v10 = DriverStoreOpenW(0, 0, 0, 0);
    if ( !v10 )
    {
      LastError = GetLastError();
      DevRtlWriteTextLog(ThreadLogToken, 1, 1, "Unable to open driver store. Error = 0x%08X", LastError);
      g_BootCriticalDevice = 0;
      goto LABEL_46;
    }
  }
  if ( (unsigned int)DriverStoreFindW(v10, a4, 9, 0, 0, v46, 260, 0) )
  {
    v13 = a6;
    if ( !IsDriverInstallAllowed(ThreadLogToken, *(void **)v44, (WCHAR *)a3, v10, v46, a5) )
    {
      v14 = GetLastError();
LABEL_14:
      LastError = v14;
      goto LABEL_43;
    }
    v15 = CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)a3, 1u);
    if ( v15 )
    {
      v38[0] = v15;
      ulFlagsa[0] = CM_MapCrToWin32Err(v15, 0x490u);
      LastError = ulFlagsa[0];
      DevRtlWriteTextLog(
        ThreadLogToken,
        1,
        1,
        "Unable to locate device '%ws'. Error = 0x%08X (0x%02X)",
        v43,
        *(_QWORD *)ulFlagsa,
        *(_QWORD *)v38);
      goto LABEL_43;
    }
    v38[0] = 16;
    ulFlagsb = &ClassGUID;
    PropertyBufferSize = &PropertyType;
    if ( (unsigned int)DriverStoreGetObjectPropertyW(v10, 2, v46, DEVPKEY_DriverPackage_ClassGuid) )
    {
      v42 = 1;
      if ( !CM_Get_Class_PropertyW(
              &ClassGUID,
              &DEVPKEY_DeviceClass_BootCritical,
              &PropertyType,
              PropertyBuffer,
              &v42,
              0)
        && PropertyType == 17
        && PropertyBuffer[0] == 0xFF )
      {
        g_BootCriticalDevice = 1;
      }
    }
    if ( (unsigned __int8)IsSetDriverPackageRestorePointPresent(v17, v16, v18, v19, PropertyBufferSize) )
    {
      v13 = a6 | 0x10000;
      DrvInstActionCallback(13, 0);
    }
    if ( (unsigned int)GetDeviceConfigMode(a2) )
    {
      v20 = DriverPackageConfigurable(v10, v46, ThreadLogToken);
      if ( !v20 || (unsigned int)PnpUtilsDriverPackageAppliesToDevNode(v10, pdnDevInst, v46, 0) )
        goto LABEL_30;
      v21 = "Force-installed driver cannot be configured, performing standard device installation.";
    }
    else
    {
      v21 = "Device configuration is disabled, performing standard device installation.";
    }
    v20 = 0;
    DevRtlWriteTextLog(ThreadLogToken, 1, 4, v21);
LABEL_30:
    DevRtlWriteTextLog(ThreadLogToken, 1, 5, "Installing driver: %ws", a5, ulFlagsb, *(_QWORD *)v38, 0, 0);
    DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Install flags: 0x%08X", v13);
    if ( !v20 && (unsigned __int8)IsSetDriverPackageRestorePointPresent(v23, v22, v24, v25, PropertyBufferSizea) )
    {
      v26 = v43;
    }
    else
    {
      v26 = v43;
      LastError = CoreDeviceInstall(*(__int64 *)v44, pdnDevInst, v43, v46, (__int64)a5, v13);
      if ( !LastError )
        goto LABEL_43;
      if ( !(unsigned __int8)IsSetDriverPackageRestorePointPresent(v28, v27, v29, v30, PropertyBufferSizeb) )
      {
        DevRtlWriteTextLog(ThreadLogToken, 1, 1, "Failed to configure device. Error = 0x%08X", LastError);
        goto LABEL_43;
      }
      if ( (unsigned int)IsFatalDeviceInstallError(LastError, ThreadLogToken) )
        goto LABEL_43;
      if ( LastError == 50 )
        DevRtlWriteTextLog(
          ThreadLogToken,
          1,
          4,
          "Selected driver cannot be configured, performing standard device installation.");
      else
        DevRtlWriteTextLog(
          ThreadLogToken,
          1,
          2,
          "Unable to configure device, falling back to standard device installation.");
    }
    v14 = InstallLegacyDeviceDriver(*(_QWORD *)v44, pdnDevInst, v26, v46, a5, v13, DrvInstActionCallback, 0);
    goto LABEL_14;
  }
  v12 = GetLastError();
  LastError = v12;
  if ( v12 == 1169 )
  {
    LastError = -536870348;
    ulFlags[0] = -536870348;
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      1,
      "Cannot install non-native driver package '%ws'. Err = 0x%08X",
      a4,
      *(_QWORD *)ulFlags);
  }
  else
  {
    ulFlags[0] = v12;
    DevRtlWriteTextLog(ThreadLogToken, 1, 1, "Cannot find driver package '%ws'. Err = 0x%08X", a4, *(_QWORD *)ulFlags);
  }
LABEL_43:
  g_BootCriticalDevice = 0;
  if ( !a2 && v10 )
    DriverStoreClose(v10);
LABEL_46:
  if ( LastError == 1115 )
  {
    DevRtlWriteTextLog(
      ThreadLogToken,
      1,
      1048578,
      "Device install failure (0x%08X) attributed to system shutdown, retrying on next boot...",
      1115);
    DevUtilsMarkDeviceForReinstall(pdnDevInst, ThreadLogToken);
  }
  return LastError;
}

```

## disassembly

```asm
0x140011a78  push    rbp
0x140011a7a  push    rbx
0x140011a7b  push    rsi
0x140011a7c  push    rdi
0x140011a7d  push    r12
0x140011a7f  push    r13
0x140011a81  push    r14
0x140011a83  push    r15
0x140011a85  lea     rbp, [rsp-1A8h]
0x140011a8d  sub     rsp, 2A8h
0x140011a94  mov     rax, cs:__security_cookie
0x140011a9b  xor     rax, rsp
0x140011a9e  mov     [rbp+1E0h+var_50], rax
0x140011aa5  mov     r13, [rbp+1E0h+arg_20]
0x140011aac  mov     rbx, r8
0x140011aaf  xorps   xmm0, xmm0
0x140011ab2  mov     [rsp+2E0h+var_280], rbx
0x140011ab7  movups  xmmword ptr [rsp+2E0h+ClassGUID.Data1], xmm0
0x140011abc  mov     r14, r9
0x140011abf  mov     qword ptr [rsp+2E0h+var_278], rcx
0x140011ac4  mov     r12, rdx
0x140011ac7  mov     [rsp+2E0h+PropertyType], 0
0x140011acf  mov     [rsp+2E0h+var_284], 0
0x140011ad7  mov     [rsp+2E0h+PropertyBuffer], 0
0x140011adc  mov     [rsp+2E0h+pdnDevInst], 0
0x140011ae4  call    cs:__imp_DevRtlGetThreadLogToken
0x140011aea  mov     rdi, rax
0x140011aed  test    r14, r14
0x140011af0  jz      loc_140011EA3
0x140011af6  test    r13, r13
0x140011af9  jz      loc_140011EA3
0x140011aff  test    r12, r12
0x140011b02  jnz     short loc_140011B49
0x140011b04  xor     r9d, r9d
0x140011b07  xor     r8d, r8d
0x140011b0a  xor     edx, edx
0x140011b0c  xor     ecx, ecx
0x140011b0e  call    cs:__imp_DriverStoreOpenW
0x140011b14  mov     rsi, rax
0x140011b17  test    rax, rax
0x140011b1a  jnz     short loc_140011B4C
0x140011b1c  call    cs:__imp_GetLastError
0x140011b22  lea     edx, [rsi+1]
0x140011b25  mov     rcx, rdi
0x140011b28  lea     r9, aUnableToOpenDr_0; "Unable to open driver store. Error = 0x"...
0x140011b2f  mov     dword ptr [rsp+2E0h+PropertyBufferSize], eax
0x140011b33  mov     r8d, edx
0x140011b36  mov     ebx, eax
0x140011b38  call    cs:__imp_DevRtlWriteTextLog
0x140011b3e  mov     cs:g_BootCriticalDevice, esi
0x140011b44  jmp     loc_140011EC5
0x140011b49  mov     rsi, r12
0x140011b4c  mov     [rsp+2E0h+var_2A8], 0
0x140011b55  lea     rax, [rbp+1E0h+var_260]
0x140011b59  mov     [rsp+2E0h+var_2B0], 104h
0x140011b61  mov     r8d, 9
0x140011b67  mov     qword ptr [rsp+2E0h+ulFlags], rax
0x140011b6c  xor     r9d, r9d
0x140011b6f  mov     rdx, r14
0x140011b72  mov     dword ptr [rsp+2E0h+PropertyBufferSize], 0
0x140011b7a  mov     rcx, rsi
0x140011b7d  call    cs:__imp_DriverStoreFindW
0x140011b83  test    eax, eax
0x140011b85  jnz     short loc_140011BCE
0x140011b87  call    cs:__imp_GetLastError
0x140011b8d  mov     edx, 1
0x140011b92  mov     rcx, rdi
0x140011b95  mov     r8d, edx
0x140011b98  mov     ebx, eax
0x140011b9a  cmp     eax, 491h
0x140011b9f  jnz     short loc_140011BB3
0x140011ba1  mov     ebx, 0E0000234h
0x140011ba6  lea     r9, aCannotInstallN; "Cannot install non-native driver packag"...
0x140011bad  mov     [rsp+2E0h+ulFlags], ebx
0x140011bb1  jmp     short loc_140011BBE
0x140011bb3  mov     [rsp+2E0h+ulFlags], eax
0x140011bb7  lea     r9, aCannotFindDriv; "Cannot find driver package '%ws'. Err ="...
0x140011bbe  mov     [rsp+2E0h+PropertyBufferSize], r14
0x140011bc3  call    cs:__imp_DevRtlWriteTextLog
0x140011bc9  jmp     loc_140011EA8
0x140011bce  mov     r15d, [rbp+1E0h+arg_28]
0x140011bd5  lea     rax, [rbp+1E0h+var_260]
0x140011bd9  mov     rdx, qword ptr [rsp+2E0h+var_278]; int
0x140011bde  mov     r9, rsi; int
0x140011be1  mov     [rsp+2E0h+var_2B0], r15d; int
0x140011be6  mov     r8, rbx; int
0x140011be9  mov     qword ptr [rsp+2E0h+ulFlags], r13; unsigned __int16 *
0x140011bee  mov     rcx, rdi; int
0x140011bf1  mov     [rsp+2E0h+PropertyBufferSize], rax; __int64
0x140011bf6  call    IsDriverInstallAllowed
0x140011bfb  test    eax, eax
0x140011bfd  jnz     short loc_140011C0C
0x140011bff  call    cs:__imp_GetLastError
0x140011c05  mov     ebx, eax
0x140011c07  jmp     loc_140011EA8
0x140011c0c  mov     r8d, 1; ulFlags
0x140011c12  lea     rcx, [rsp+2E0h+pdnDevInst]; pdnDevInst
0x140011c17  mov     rdx, rbx; pDeviceID
0x140011c1a  call    cs:__imp_CM_Locate_DevNodeW
0x140011c20  mov     r14d, eax
0x140011c23  test    eax, eax
0x140011c25  jz      short loc_140011C66
0x140011c27  mov     edx, 490h; DefaultErr
0x140011c2c  mov     ecx, eax; CmReturnCode
0x140011c2e  call    cs:__imp_CM_MapCrToWin32Err
0x140011c34  mov     [rsp+2E0h+var_2B0], r14d
0x140011c39  lea     r9, aUnableToLocate; "Unable to locate device '%ws'. Error = "...
0x140011c40  mov     r14, [rsp+2E0h+var_280]
0x140011c45  mov     edx, 1
0x140011c4a  mov     [rsp+2E0h+ulFlags], eax
0x140011c4e  mov     r8d, edx
0x140011c51  mov     rcx, rdi
0x140011c54  mov     [rsp+2E0h+PropertyBufferSize], r14
0x140011c59  mov     ebx, eax
0x140011c5b  call    cs:__imp_DevRtlWriteTextLog
0x140011c61  jmp     loc_140011EA8
0x140011c66  xor     r14d, r14d
0x140011c69  lea     rax, [rsp+2E0h+ClassGUID]
0x140011c6e  mov     [rsp+2E0h+var_2A0], r14d
0x140011c73  lea     r9, DEVPKEY_DriverPackage_ClassGuid
0x140011c7a  mov     [rsp+2E0h+var_2A8], r14
0x140011c7f  lea     r8, [rbp+1E0h+var_260]
0x140011c83  mov     [rsp+2E0h+var_2B0], 10h
0x140011c8b  mov     rcx, rsi
0x140011c8e  mov     qword ptr [rsp+2E0h+ulFlags], rax
0x140011c93  lea     edx, [r14+2]
0x140011c97  lea     rax, [rsp+2E0h+PropertyType]
0x140011c9c  mov     [rsp+2E0h+PropertyBufferSize], rax
0x140011ca1  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140011ca7  test    eax, eax
0x140011ca9  jz      short loc_140011CF6
0x140011cab  lea     rax, [rsp+2E0h+var_284]
0x140011cb0  mov     [rsp+2E0h+ulFlags], r14d; ulFlags
0x140011cb5  lea     ebx, [r14+1]
0x140011cb9  mov     [rsp+2E0h+PropertyBufferSize], rax; PropertyBufferSize
0x140011cbe  lea     r9, [rsp+2E0h+PropertyBuffer]; PropertyBuffer
0x140011cc3  mov     [rsp+2E0h+var_284], ebx
0x140011cc7  lea     r8, [rsp+2E0h+PropertyType]; PropertyType
0x140011ccc  lea     rdx, DEVPKEY_DeviceClass_BootCritical; PropertyKey
0x140011cd3  lea     rcx, [rsp+2E0h+ClassGUID]; ClassGUID
0x140011cd8  call    cs:__imp_CM_Get_Class_PropertyW
0x140011cde  test    eax, eax
0x140011ce0  jnz     short loc_140011CF6
0x140011ce2  cmp     [rsp+2E0h+PropertyType], 11h
0x140011ce7  jnz     short loc_140011CF6
0x140011ce9  cmp     [rsp+2E0h+PropertyBuffer], 0FFh
0x140011cee  jnz     short loc_140011CF6
0x140011cf0  mov     cs:g_BootCriticalDevice, ebx
0x140011cf6  call    IsSetDriverPackageRestorePointPresent
0x140011cfb  test    al, al
0x140011cfd  jz      short loc_140011D11
0x140011cff  xor     edx, edx
0x140011d01  bts     r15d, 10h
0x140011d06  xor     r8d, r8d
0x140011d09  lea     ecx, [rdx+0Dh]
0x140011d0c  call    DrvInstActionCallback
0x140011d11  mov     rcx, r12
0x140011d14  call    GetDeviceConfigMode
0x140011d19  test    eax, eax
0x140011d1b  jz      short loc_140011D52
0x140011d1d  mov     r8, rdi
0x140011d20  lea     rdx, [rbp+1E0h+var_260]
0x140011d24  mov     rcx, rsi
0x140011d27  call    DriverPackageConfigurable
0x140011d2c  mov     ebx, eax
0x140011d2e  test    eax, eax
0x140011d30  jz      short loc_140011D6F
0x140011d32  mov     edx, [rsp+2E0h+pdnDevInst]
0x140011d36  lea     r8, [rbp+1E0h+var_260]
0x140011d3a  xor     r9d, r9d
0x140011d3d  mov     rcx, rsi
0x140011d40  call    PnpUtilsDriverPackageAppliesToDevNode
0x140011d45  test    eax, eax
0x140011d47  jnz     short loc_140011D6F
0x140011d49  lea     r9, aForceInstalled; "Force-installed driver cannot be config"...
0x140011d50  jmp     short loc_140011D59
0x140011d52  lea     r9, aDeviceConfigur; "Device configuration is disabled, perfo"...
0x140011d59  mov     r8d, 4
0x140011d5f  mov     rcx, rdi
0x140011d62  mov     ebx, r14d
0x140011d65  lea     edx, [r8-3]
0x140011d69  call    cs:__imp_DevRtlWriteTextLog
0x140011d6f  mov     edx, 1
0x140011d74  mov     [rsp+2E0h+PropertyBufferSize], r13
0x140011d79  lea     r9, aInstallingDriv; "Installing driver: %ws"
0x140011d80  mov     rcx, rdi
0x140011d83  lea     r8d, [rdx+4]
0x140011d87  call    cs:__imp_DevRtlWriteTextLog
0x140011d8d  mov     edx, 1
0x140011d92  mov     dword ptr [rsp+2E0h+PropertyBufferSize], r15d
0x140011d97  lea     r9, aInstallFlags0x; "Install flags: 0x%08X"
0x140011d9e  mov     rcx, rdi
0x140011da1  lea     r8d, [rdx+3]
0x140011da5  call    cs:__imp_DevRtlWriteTextLog
0x140011dab  lea     rax, DrvInstActionCallback
0x140011db2  test    ebx, ebx
0x140011db4  jnz     short loc_140011DCA
0x140011db6  call    IsSetDriverPackageRestorePointPresent
0x140011dbb  test    al, al
0x140011dbd  jnz     loc_140011E64
0x140011dc3  lea     rax, DrvInstActionCallback
0x140011dca  mov     edx, [rsp+2E0h+pdnDevInst]
0x140011dce  lea     r9, [rbp+1E0h+var_260]
0x140011dd2  mov     rcx, qword ptr [rsp+2E0h+var_278]
0x140011dd7  mov     [rsp+2E0h+var_2A8], r14
0x140011ddc  mov     r14, [rsp+2E0h+var_280]
0x140011de1  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x140011de6  mov     r8, r14
0x140011de9  mov     [rsp+2E0h+ulFlags], r15d
0x140011dee  mov     [rsp+2E0h+PropertyBufferSize], r13
0x140011df3  call    CoreDeviceInstall
0x140011df8  mov     ebx, eax
0x140011dfa  test    eax, eax
0x140011dfc  jz      loc_140011EA8
0x140011e02  call    IsSetDriverPackageRestorePointPresent
0x140011e07  test    al, al
0x140011e09  jnz     short loc_140011E29
0x140011e0b  mov     edx, 1
0x140011e10  mov     dword ptr [rsp+2E0h+PropertyBufferSize], ebx
0x140011e14  mov     r8d, edx
0x140011e17  lea     r9, aFailedToConfig; "Failed to configure device. Error = 0x%"...
0x140011e1e  mov     rcx, rdi
0x140011e21  call    cs:__imp_DevRtlWriteTextLog
0x140011e27  jmp     short loc_140011EA8
0x140011e29  mov     rdx, rdi
0x140011e2c  mov     ecx, ebx
0x140011e2e  call    IsFatalDeviceInstallError
0x140011e33  test    eax, eax
0x140011e35  jnz     short loc_140011EA8
0x140011e37  lea     edx, [rax+1]
0x140011e3a  mov     rcx, rdi
0x140011e3d  cmp     ebx, 32h ; '2'
0x140011e40  jnz     short loc_140011E55
0x140011e42  lea     r9, aSelectedDriver; "Selected driver cannot be configured, p"...
0x140011e49  lea     r8d, [rax+4]
0x140011e4d  call    cs:__imp_DevRtlWriteTextLog
0x140011e53  jmp     short loc_140011E69
0x140011e55  lea     r9, aUnableToConfig; "Unable to configure device, falling bac"...
0x140011e5c  mov     r8d, 2
0x140011e62  jmp     short loc_140011E4D
0x140011e64  mov     r14, [rsp+2E0h+var_280]
0x140011e69  mov     edx, [rsp+2E0h+pdnDevInst]
0x140011e6d  lea     rax, DrvInstActionCallback
0x140011e74  mov     rcx, qword ptr [rsp+2E0h+var_278]
0x140011e79  lea     r9, [rbp+1E0h+var_260]
0x140011e7d  mov     [rsp+2E0h+var_2A8], 0
0x140011e86  mov     r8, r14
0x140011e89  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x140011e8e  mov     [rsp+2E0h+ulFlags], r15d
0x140011e93  mov     [rsp+2E0h+PropertyBufferSize], r13
0x140011e98  call    cs:__imp_InstallLegacyDeviceDriver
0x140011e9e  jmp     loc_140011C05
0x140011ea3  xor     esi, esi
0x140011ea5  lea     ebx, [rsi+57h]
0x140011ea8  mov     cs:g_BootCriticalDevice, 0
0x140011eb2  test    r12, r12
0x140011eb5  jnz     short loc_140011EC5
0x140011eb7  test    rsi, rsi
0x140011eba  jz      short loc_140011EC5
0x140011ebc  mov     rcx, rsi
0x140011ebf  call    cs:__imp_DriverStoreClose
0x140011ec5  mov     eax, 45Bh
0x140011eca  cmp     ebx, eax
0x140011ecc  jnz     short loc_140011EF9
0x140011ece  lea     r9, aDeviceInstallF; "Device install failure (0x%08X) attribu"...
0x140011ed5  mov     dword ptr [rsp+2E0h+PropertyBufferSize], eax
0x140011ed9  mov     edx, 1
0x140011ede  mov     r8d, 100002h
0x140011ee4  mov     rcx, rdi
0x140011ee7  call    cs:__imp_DevRtlWriteTextLog
0x140011eed  mov     ecx, [rsp+2E0h+pdnDevInst]
0x140011ef1  mov     rdx, rdi
0x140011ef4  call    DevUtilsMarkDeviceForReinstall
0x140011ef9  mov     eax, ebx
0x140011efb  mov     rcx, [rbp+1E0h+var_50]
0x140011f02  xor     rcx, rsp; StackCookie
0x140011f05  call    __security_check_cookie
0x140011f0a  add     rsp, 2A8h
0x140011f11  pop     r15
0x140011f13  pop     r14
0x140011f15  pop     r13
0x140011f17  pop     r12
0x140011f19  pop     rdi
0x140011f1a  pop     rsi
0x140011f1b  pop     rbx
0x140011f1c  pop     rbp
0x140011f1d  retn
```
