# CGroupPolicy::ApplyGroupPolicyForDiskDevices(_ACL *,void *,ulong,int *,int,int)

- ea: `0x18000f390`
- end: `0x18000fabe`
- name: `?ApplyGroupPolicyForDiskDevices@CGroupPolicy@@IEAAXPEAU_ACL@@PEAXKPEAHHH@Z`
- size: `1838`
- prototype: `void __fastcall(CGroupPolicy *this, struct _ACL *, void *, unsigned int, int *, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fc24`
- `0x1800106e0`

## callees

- `0x180002fa0`
- `0x1800059d0`
- `0x180007160`
- `0x1800097d0`
- `0x18000f390`
- `0x18000fac4`
- `0x1800100c8`
- `0x1800101cc`
- `0x180010d74`
- `0x180010e24`
- `0x180011008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f66e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f66e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f762`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f762`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f974`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f65b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f65b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f72e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f7dc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f72e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000f7dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f5d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f78d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f5d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f78d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f53b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f803`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f86e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f53b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f803`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f86e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa88`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000f922`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000f922`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000f550`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000f550`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000f516`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000f516`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000f576`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000f576`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f5a7`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f611`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f5a7`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f611`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000fa91`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000fa91`

## string_xrefs

- `0x18000f433`: `HotplugSecurityDescriptor`
- `0x18000f47e`: `HotplugSecurityDescriptor`
- `0x18000f43f`: `HotplugSecureOpen`
- `0x18000f498`: `HotplugSecureOpen`
- `0x18000f414`: `Will delete security for disk\n`
- `0x18000f4d6`: `Successfully set disk security in registry\n`
- `0x18000f4ea`: `Failed (%d) to set disk security in registry\n`
- `0x18000f677`: `CreateFile failed (%d) for %ws\n\n`
- `0x18000f8e7`: `Will set security of size %d for disk\n`
- `0x18000f92f`: `SetSecurityInfo for volume succeeded\n`
- `0x18000f95d`: `SetSecurityInfo for volume Failed %d\n`

## pseudocode

```c
void __fastcall CGroupPolicy::ApplyGroupPolicyForDiskDevices(
        CGroupPolicy *this,
        struct _ACL *a2,
        void *a3,
        unsigned int a4,
        int *a5,
        int a6,
        int a7)
{
  unsigned int v7; // r12d
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // edi
  HDEVINFO ClassDevsW; // r15
  unsigned __int16 *v18; // rdi
  DWORD i; // r14d
  DWORD v20; // eax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v21; // rax
  const WCHAR *DevicePath; // r13
  HANDLE FileW; // rsi
  DWORD v24; // ebx
  int *v25; // rsi
  __int64 v26; // rcx
  BOOL v27; // ebx
  DWORD v28; // eax
  DWORD v29; // r12d
  _DWORD *v30; // rbx
  __int64 v31; // rcx
  DWORD v32; // eax
  BOOL v33; // r13d
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  int IsDiskHotPluggable; // eax
  CGroupPolicy *v38; // rcx
  BOOL v39; // ebx
  void *v40; // r13
  DWORD v41; // eax
  CGroupPolicy *v42; // rcx
  __int64 v43; // rcx
  int *v44; // rsi
  CGroupPolicy *v45; // rcx
  DWORD v46; // eax
  DWORD v47; // eax
  DWORD LastError; // eax
  DWORD RequiredSize; // [rsp+40h] [rbp-B1h] BYREF
  unsigned int v50; // [rsp+44h] [rbp-ADh]
  int v51; // [rsp+48h] [rbp-A9h] BYREF
  int v52; // [rsp+4Ch] [rbp-A5h]
  int v53; // [rsp+50h] [rbp-A1h]
  int v54; // [rsp+54h] [rbp-9Dh]
  unsigned int v55; // [rsp+58h] [rbp-99h]
  int *v56; // [rsp+60h] [rbp-91h]
  void *v57; // [rsp+68h] [rbp-89h]
  __int64 v58; // [rsp+70h] [rbp-81h]
  PACL pDacl; // [rsp+78h] [rbp-79h]
  GUID ClassGuid; // [rsp+80h] [rbp-71h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+90h] [rbp-61h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+B0h] [rbp-41h] BYREF
  _OWORD OutBuffer[2]; // [rsp+D0h] [rbp-21h] BYREF

  v56 = a5;
  v50 = a4;
  v7 = a4;
  v57 = a3;
  pDacl = a2;
  RequiredSize = 0;
  v51 = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  ClassGuid = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  if ( a3 )
  {
    v54 = CGroupPolicy::CheckIfGPBeingEnabled(this, (unsigned __int8 *)a3, a4);
    if ( !v54 )
      return;
    v16 = WPDLibSetRegistryValue(
            0,
            v13,
            L"SYSTEM\\CurrentControlSet\\Control\\Storage",
            L"HotplugSecurityDescriptor",
            3,
            a3,
            v7);
    if ( a7 )
    {
      v51 = 0;
      v16 = WPDLibSetRegistryValue(
              0,
              v14,
              L"SYSTEM\\CurrentControlSet\\Control\\Storage",
              L"HotplugSecureOpen",
              4,
              &v51,
              4);
    }
    else
    {
      WPDLibDeleteRegistryValue(v15, v14, L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"HotplugSecureOpen");
    }
    if ( v16 )
      GPDebugPrintX(2u, "Failed (%d) to set disk security in registry\n", v16);
    else
      GPDebugPrintX(8u, "Successfully set disk security in registry\n");
  }
  else
  {
    v54 = 0;
    GPDebugPrintX(8u, "Will delete security for disk\n");
    WPDLibDeleteRegistryValue(v10, v9, L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"HotplugSecurityDescriptor");
    WPDLibDeleteRegistryValue(v12, v11, L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"HotplugSecureOpen");
  }
  ClassGuid = GUID_DEVINTERFACE_VOLUME;
  ClassDevsW = SetupDiGetClassDevsW(&ClassGuid, 0, 0, 0x12u);
  if ( ClassDevsW != (HDEVINFO)-1LL )
  {
    v18 = 0;
    for ( i = 0; ; ++i )
    {
      if ( v18 )
        LocalFree(v18);
      DeviceInfoData.cbSize = 32;
      if ( !SetupDiEnumDeviceInfo(ClassDevsW, i, &DeviceInfoData) )
      {
        LastError = GetLastError();
        if ( LastError == 259 )
          GPDebugPrintX(8u, "Enumerated all volumes successfully\n");
        else
          GPDebugPrintX(2u, "SetupDiEnumDeviceInfo failed (%d) for index %d\n", LastError, i);
LABEL_69:
        SetupDiDestroyDeviceInfoList(ClassDevsW);
        return;
      }
      DeviceInterfaceData.cbSize = 32;
      if ( !SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &ClassGuid, i, &DeviceInterfaceData) )
      {
        v47 = GetLastError();
        if ( v47 == 259 )
          GPDebugPrintX(8u, "Enumerated all interfaces successfully\n");
        else
          GPDebugPrintX(2u, "SetupDiEnumDeviceInterfaces failed (%d) for index %d\n", v47, i);
        goto LABEL_69;
      }
      DeviceInfoData.cbSize = 32;
      if ( SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
        goto LABEL_59;
      v20 = GetLastError();
      if ( v20 != 122 || !RequiredSize )
      {
        GPDebugPrintX(2u, "SetupDiGetDeviceInterfaceDetail failed (%d)\n", v20);
        goto LABEL_69;
      }
      v21 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)LocalAlloc(0x40u, RequiredSize);
      v18 = (unsigned __int16 *)v21;
      if ( !v21 )
      {
LABEL_59:
        GPDebugPrintX(2u, "Failed to allocate memory for device detail\n");
        goto LABEL_69;
      }
      v21->cbSize = 8;
      DevicePath = v21->DevicePath;
      v21->DevicePath[0] = 0;
      if ( !SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, v21, RequiredSize, 0, 0) )
      {
        v46 = GetLastError();
        GPDebugPrintX(2u, "SetupDiGetDeviceInterfaceDetail failed (%d) for index %d\n", v46, i);
        LocalFree(v18);
        goto LABEL_69;
      }
      GPDebugPrintX(8u, "Volume interface name %ws\n", DevicePath);
      FileW = CreateFileW(DevicePath, 0x1E019Fu, 3u, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        v24 = GetLastError();
        GPDebugPrintX(2u, "CreateFile failed (%d) for %ws\n\n", v24, DevicePath);
        if ( v24 == 21 )
        {
          GPDebugPrintX(2u, "The drive probably does not have media\n");
          GPDebugPrintX(8u, "Will restart the disk\n");
          v25 = v56;
          CGroupPolicy::SetDeviceSecurityAndRestart(v26, ClassDevsW, &DeviceInfoData, v57, v7, 1, 0, v56);
          AccessCode = 2;
        }
        else
        {
          v25 = v56;
        }
        *v25 = 1;
      }
      else
      {
        RequiredSize = 0;
        v27 = DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &RequiredSize, 0);
        v28 = GetLastError();
        v29 = v28;
        if ( !v27 && v28 != 234 )
        {
          GPDebugPrintX(2u, "Get Volume Disk Extents failed (%d) for %ws\n\n", v28, DevicePath);
LABEL_29:
          CloseHandle(FileW);
LABEL_30:
          v7 = v50;
          continue;
        }
        RequiredSize = 24 * LODWORD(OutBuffer[0]) + 8;
        v30 = LocalAlloc(0x40u, RequiredSize);
        if ( !v30 )
        {
          GPDebugPrintX(2u, "volExtents NULL\n");
          goto LABEL_29;
        }
        if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, v30, RequiredSize, &RequiredSize, 0) )
        {
          v32 = GetLastError();
          GPDebugPrintX(2u, "Failed (%d) Get Volume Disk Extents\n\n", v32);
          LocalFree(v30);
          goto LABEL_29;
        }
        v33 = 0;
        v55 = -1;
        v34 = 0;
        v53 = 0;
        while ( 1 )
        {
          v52 = v34;
          if ( (unsigned int)v34 >= *v30 )
            break;
          v35 = 3 * v34;
          v36 = (unsigned int)v30[2 * v35 + 2];
          v58 = v35;
          IsDiskHotPluggable = CGroupPolicy::IsDiskHotPluggableEx(v31, v36);
          v33 = IsDiskHotPluggable == 2;
          if ( IsDiskHotPluggable )
          {
            if ( IsDiskHotPluggable == 2 )
            {
              v55 = v30[2 * v58 + 2];
              break;
            }
          }
          else
          {
            v53 = 1;
          }
          v34 = (unsigned int)(v52 + 1);
        }
        LocalFree(v30);
        if ( !v33 )
        {
          GPDebugPrintX(8u, "Will check if the device is hot pluggable\n");
          if ( !CGroupPolicy::IsDeviceHotPluggable(v38, ClassDevsW, &DeviceInfoData) )
          {
            GPDebugPrintX(8u, "Disk is not hotpluggable\n");
            if ( v53 )
              GPDebugPrintX(
                2u,
                "Enforcement requires machine reboot: no disk found to be hotpluggable, and at least one disk hotpluggabi"
                "lity lookup failed, and volume is not hotpluggable\n"
                "\n");
            goto LABEL_29;
          }
        }
        v39 = 1;
        GPDebugPrintX(8u, "Disk is hotpluggable\n");
        v40 = v57;
        if ( v57 )
        {
          GPDebugPrintX(8u, "Will set security of size %d for disk\n", v50);
          if ( pDacl )
          {
            v41 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
            v29 = v41;
            if ( v41 )
            {
              GPDebugPrintX(2u, "SetSecurityInfo for volume Failed %d\n", v41);
              v29 = 0;
            }
            else
            {
              GPDebugPrintX(8u, "SetSecurityInfo for volume succeeded\n");
              CGroupPolicy::SetWPDSecurityInfo(v42, v18 + 2, v40, v50);
              v39 = v54 != 0;
            }
          }
        }
        CloseHandle(FileW);
        if ( v29 )
          goto LABEL_30;
        v44 = v56;
        v7 = v50;
        CGroupPolicy::SetDeviceSecurityAndRestart(v43, ClassDevsW, &DeviceInfoData, v40, v50, 0, 0, v56);
        if ( v39 && v55 != -1 )
        {
          CGroupPolicy::RestartDisk(v45, v55, v44);
          AccessCode = 2;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000f390  mov     [rsp-8+arg_0], rbx
0x18000f395  push    rbp
0x18000f396  push    rsi
0x18000f397  push    rdi
0x18000f398  push    r12
0x18000f39a  push    r13
0x18000f39c  push    r14
0x18000f39e  push    r15
0x18000f3a0  lea     rbp, [rsp-0Fh]
0x18000f3a5  sub     rsp, 100h
0x18000f3ac  mov     rax, cs:__security_cookie
0x18000f3b3  xor     rax, rsp
0x18000f3b6  mov     [rbp+3Fh+var_40], rax
0x18000f3ba  mov     rsi, [rbp+3Fh+arg_20]
0x18000f3be  xorps   xmm1, xmm1
0x18000f3c1  mov     [rsp+130h+var_D0], rsi
0x18000f3c6  xorps   xmm0, xmm0
0x18000f3c9  mov     [rsp+130h+var_EC], r9d
0x18000f3ce  mov     r12d, r9d
0x18000f3d1  mov     [rsp+130h+var_C8], r8
0x18000f3d6  mov     r13, r8
0x18000f3d9  mov     [rbp+3Fh+pDacl], rdx
0x18000f3dd  mov     r14d, 4
0x18000f3e3  mov     [rsp+130h+RequiredSize], 0
0x18000f3eb  mov     [rsp+130h+var_E8], 0
0x18000f3f3  movups  xmmword ptr [rbp+3Fh+DeviceInfoData.cbSize], xmm0
0x18000f3f7  movups  xmmword ptr [rbp+3Fh+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18000f3fb  movups  xmmword ptr [rbp+3Fh+var_80.cbSize], xmm1
0x18000f3ff  movups  xmmword ptr [rbp+3Fh+var_80.InterfaceClassGuid.Data4+4], xmm1
0x18000f403  movups  xmmword ptr [rbp+3Fh+ClassGuid.Data1], xmm0
0x18000f407  movups  [rbp+3Fh+OutBuffer], xmm1
0x18000f40b  movups  [rbp+3Fh+var_50], xmm1
0x18000f40f  test    r8, r8
0x18000f412  jnz     short loc_18000F453
0x18000f414  lea     rdx, aWillDeleteSecu; "Will delete security for disk\n"
0x18000f41b  mov     [rsp+130h+var_DC], r8d
0x18000f420  lea     ecx, [r8+8]; unsigned int
0x18000f424  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f429  lea     rbx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x18000f430  mov     r8, rbx
0x18000f433  lea     r9, aHotplugsecurit; "HotplugSecurityDescriptor"
0x18000f43a  call    WPDLibDeleteRegistryValue
0x18000f43f  lea     r9, aHotplugsecureo; "HotplugSecureOpen"
0x18000f446  mov     r8, rbx
0x18000f449  call    WPDLibDeleteRegistryValue
0x18000f44e  jmp     loc_18000F4FB
0x18000f453  mov     r8d, r12d; unsigned int
0x18000f456  mov     rdx, r13; unsigned __int8 *
0x18000f459  call    ?CheckIfGPBeingEnabled@CGroupPolicy@@IEAAHPEAEK@Z; CGroupPolicy::CheckIfGPBeingEnabled(uchar *,ulong)
0x18000f45e  mov     [rsp+130h+var_DC], eax
0x18000f462  test    eax, eax
0x18000f464  jz      loc_18000FA97
0x18000f46a  mov     dword ptr [rsp+130h+hTemplateFile], r12d
0x18000f46f  lea     rbx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x18000f476  mov     r8, rbx
0x18000f479  mov     [rsp+130h+var_108], r13
0x18000f47e  lea     r9, aHotplugsecurit; "HotplugSecurityDescriptor"
0x18000f485  mov     dword ptr [rsp+130h+DeviceInterfaceData], 3
0x18000f48d  xor     ecx, ecx
0x18000f48f  call    WPDLibSetRegistryValue
0x18000f494  cmp     [rbp+3Fh+arg_30], 0
0x18000f498  lea     r9, aHotplugsecureo; "HotplugSecureOpen"
0x18000f49f  mov     edi, eax
0x18000f4a1  mov     r8, rbx
0x18000f4a4  jz      short loc_18000F4CD
0x18000f4a6  lea     rax, [rsp+130h+var_E8]
0x18000f4ab  mov     dword ptr [rsp+130h+hTemplateFile], r14d
0x18000f4b0  mov     [rsp+130h+var_108], rax
0x18000f4b5  xor     ecx, ecx
0x18000f4b7  mov     dword ptr [rsp+130h+DeviceInterfaceData], r14d
0x18000f4bc  mov     [rsp+130h+var_E8], 0
0x18000f4c4  call    WPDLibSetRegistryValue
0x18000f4c9  mov     edi, eax
0x18000f4cb  jmp     short loc_18000F4D2
0x18000f4cd  call    WPDLibDeleteRegistryValue
0x18000f4d2  test    edi, edi
0x18000f4d4  jnz     short loc_18000F4E7
0x18000f4d6  lea     rdx, aSuccessfullySe; "Successfully set disk security in regis"...
0x18000f4dd  lea     ecx, [rdi+8]; unsigned int
0x18000f4e0  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f4e5  jmp     short loc_18000F4FB
0x18000f4e7  mov     r8d, edi
0x18000f4ea  lea     rdx, aFailedDToSetDi; "Failed (%d) to set disk security in reg"...
0x18000f4f1  mov     ecx, 2; unsigned int
0x18000f4f6  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f4fb  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_VOLUME.Data1
0x18000f502  mov     r9d, 12h; Flags
0x18000f508  lea     rcx, [rbp+3Fh+ClassGuid]; ClassGuid
0x18000f50c  xor     r8d, r8d; hwndParent
0x18000f50f  xor     edx, edx; Enumerator
0x18000f511  movdqu  xmmword ptr [rbp+3Fh+ClassGuid.Data1], xmm0
0x18000f516  call    cs:__imp_SetupDiGetClassDevsW
0x18000f51c  mov     r15, rax
0x18000f51f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f523  jz      loc_18000FA97
0x18000f529  xor     edi, edi
0x18000f52b  xor     r14d, r14d
0x18000f52e  mov     ebx, 20h ; ' '
0x18000f533  test    rdi, rdi
0x18000f536  jz      short loc_18000F543
0x18000f538  mov     rcx, rdi; hMem
0x18000f53b  call    cs:__imp_LocalFree
0x18000f541  xor     edi, edi
0x18000f543  lea     r8, [rbp+3Fh+DeviceInfoData]; DeviceInfoData
0x18000f547  mov     [rbp+3Fh+DeviceInfoData.cbSize], ebx
0x18000f54a  mov     edx, r14d; MemberIndex
0x18000f54d  mov     rcx, r15; DeviceInfoSet
0x18000f550  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000f556  test    eax, eax
0x18000f558  jz      loc_18000FA49
0x18000f55e  lea     rax, [rbp+3Fh+var_80]
0x18000f562  mov     [rbp+3Fh+var_80.cbSize], ebx
0x18000f565  mov     r9d, r14d; MemberIndex
0x18000f568  mov     [rsp+130h+DeviceInterfaceData], rax; DeviceInterfaceData
0x18000f56d  lea     r8, [rbp+3Fh+ClassGuid]; InterfaceClassGuid
0x18000f571  xor     edx, edx; DeviceInfoData
0x18000f573  mov     rcx, r15; DeviceInfoSet
0x18000f576  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18000f57c  test    eax, eax
0x18000f57e  jz      loc_18000FA2A
0x18000f584  lea     rax, [rsp+130h+RequiredSize]
0x18000f589  mov     [rsp+130h+var_108], 0; DeviceInfoData
0x18000f592  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18000f595  mov     [rsp+130h+DeviceInterfaceData], rax; RequiredSize
0x18000f59a  xor     r8d, r8d; DeviceInterfaceDetailData
0x18000f59d  mov     [rbp+3Fh+DeviceInfoData.cbSize], ebx
0x18000f5a0  lea     rdx, [rbp+3Fh+var_80]; DeviceInterfaceData
0x18000f5a4  mov     rcx, r15; DeviceInfoSet
0x18000f5a7  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000f5ad  test    eax, eax
0x18000f5af  jnz     loc_18000FA17
0x18000f5b5  call    cs:__imp_GetLastError
0x18000f5bb  cmp     eax, 7Ah ; 'z'
0x18000f5be  jnz     loc_18000FA01
0x18000f5c4  mov     ecx, [rsp+130h+RequiredSize]
0x18000f5c8  test    ecx, ecx
0x18000f5ca  jz      loc_18000FA01
0x18000f5d0  mov     edx, ecx; uBytes
0x18000f5d2  lea     ecx, [rax-3Ah]; uFlags
0x18000f5d5  call    cs:__imp_LocalAlloc
0x18000f5db  mov     rdi, rax
0x18000f5de  test    rax, rax
0x18000f5e1  jz      loc_18000FA17
0x18000f5e7  mov     dword ptr [rax], 8
0x18000f5ed  lea     r13, [rax+4]
0x18000f5f1  xor     eax, eax
0x18000f5f3  lea     rdx, [rbp+3Fh+var_80]; DeviceInterfaceData
0x18000f5f7  mov     [r13+0], ax
0x18000f5fc  mov     r8, rdi; DeviceInterfaceDetailData
0x18000f5ff  mov     r9d, [rsp+130h+RequiredSize]; DeviceInterfaceDetailDataSize
0x18000f604  mov     rcx, r15; DeviceInfoSet
0x18000f607  mov     [rsp+130h+var_108], rax; DeviceInfoData
0x18000f60c  mov     [rsp+130h+DeviceInterfaceData], rax; RequiredSize
0x18000f611  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000f617  test    eax, eax
0x18000f619  jz      loc_18000F9DF
0x18000f61f  mov     r8, r13
0x18000f622  lea     rdx, aVolumeInterfac; "Volume interface name %ws\n"
0x18000f629  mov     ecx, 8; unsigned int
0x18000f62e  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f633  xor     r9d, r9d; lpSecurityAttributes
0x18000f636  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x18000f63f  mov     dword ptr [rsp+130h+var_108], 0; dwFlagsAndAttributes
0x18000f647  mov     edx, 1E019Fh; dwDesiredAccess
0x18000f64c  mov     rcx, r13; lpFileName
0x18000f64f  mov     dword ptr [rsp+130h+DeviceInterfaceData], 3; dwCreationDisposition
0x18000f657  lea     r8d, [r9+3]; dwShareMode
0x18000f65b  call    cs:__imp_CreateFileW
0x18000f661  mov     rsi, rax
0x18000f664  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f668  jnz     loc_18000F6F8
0x18000f66e  call    cs:__imp_GetLastError
0x18000f674  mov     r9, r13
0x18000f677  lea     rdx, aCreatefileFail; "CreateFile failed (%d) for %ws\n\n"
0x18000f67e  lea     r13d, [rsi+3]
0x18000f682  mov     r8d, eax
0x18000f685  mov     ecx, r13d; unsigned int
0x18000f688  mov     ebx, eax
0x18000f68a  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f68f  cmp     ebx, 15h
0x18000f692  jnz     short loc_18000F6EB
0x18000f694  lea     rdx, aTheDriveProbab; "The drive probably does not have media"...
0x18000f69b  mov     ecx, r13d; unsigned int
0x18000f69e  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f6a3  lea     rdx, aWillRestartThe; "Will restart the disk\n"
0x18000f6aa  lea     ecx, [rsi+9]; unsigned int
0x18000f6ad  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f6b2  mov     rsi, [rsp+130h+var_D0]
0x18000f6b7  lea     r8, [rbp+3Fh+DeviceInfoData]
0x18000f6bb  mov     r9, [rsp+130h+var_C8]
0x18000f6c0  mov     rdx, r15
0x18000f6c3  mov     [rsp+130h+lpOverlapped], rsi
0x18000f6c8  mov     dword ptr [rsp+130h+hTemplateFile], 0
0x18000f6d0  mov     dword ptr [rsp+130h+var_108], 1
0x18000f6d8  mov     dword ptr [rsp+130h+DeviceInterfaceData], r12d
0x18000f6dd  call    ?SetDeviceSecurityAndRestart@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@0KHW4TriState@1@PEAH@Z; CGroupPolicy::SetDeviceSecurityAndRestart(void *,_SP_DEVINFO_DATA *,void *,ulong,int,CGroupPolicy::TriState,int *)
0x18000f6e2  mov     cs:?AccessCode@@3KA, r13d; ulong AccessCode
0x18000f6e9  jmp     short loc_18000F6F0
0x18000f6eb  mov     rsi, [rsp+130h+var_D0]
0x18000f6f0  mov     dword ptr [rsi], 1
0x18000f6f6  jmp     short loc_18000F76D
0x18000f6f8  mov     [rsp+130h+lpOverlapped], 0; lpOverlapped
0x18000f701  lea     rax, [rsp+130h+RequiredSize]
0x18000f706  mov     [rsp+130h+hTemplateFile], rax; lpBytesReturned
0x18000f70b  xor     r9d, r9d; nInBufferSize
0x18000f70e  lea     rax, [rbp+3Fh+OutBuffer]
0x18000f712  mov     dword ptr [rsp+130h+var_108], ebx; nOutBufferSize
0x18000f716  xor     r8d, r8d; lpInBuffer
0x18000f719  mov     [rsp+130h+DeviceInterfaceData], rax; lpOutBuffer
0x18000f71e  mov     edx, 560000h; dwIoControlCode
0x18000f723  mov     [rsp+130h+RequiredSize], 0
0x18000f72b  mov     rcx, rsi; hDevice
0x18000f72e  call    cs:__imp_DeviceIoControl
0x18000f734  mov     ebx, eax
0x18000f736  call    cs:__imp_GetLastError
0x18000f73c  mov     r12d, eax
0x18000f73f  test    ebx, ebx
0x18000f741  jnz     short loc_18000F775
0x18000f743  cmp     eax, 0EAh
0x18000f748  jz      short loc_18000F775
0x18000f74a  mov     r9, r13
0x18000f74d  lea     rdx, aGetVolumeDiskE; "Get Volume Disk Extents failed (%d) for"...
0x18000f754  mov     r8d, eax
0x18000f757  lea     ecx, [rbx+2]; unsigned int
0x18000f75a  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f75f  mov     rcx, rsi; hObject
0x18000f762  call    cs:__imp_CloseHandle
0x18000f768  mov     r12d, [rsp+130h+var_EC]
0x18000f76d  inc     r14d
0x18000f770  jmp     loc_18000F52E
0x18000f775  mov     eax, dword ptr [rbp+3Fh+OutBuffer]
0x18000f778  lea     ecx, [rax+rax*2]
0x18000f77b  lea     ecx, ds:8[rcx*8]
0x18000f782  mov     [rsp+130h+RequiredSize], ecx
0x18000f786  mov     edx, ecx; uBytes
0x18000f788  mov     ecx, 40h ; '@'; uFlags
0x18000f78d  call    cs:__imp_LocalAlloc
0x18000f793  mov     rbx, rax
0x18000f796  test    rax, rax
0x18000f799  jnz     short loc_18000F7AE
0x18000f79b  lea     rdx, aVolextentsNull; "volExtents NULL\n"
0x18000f7a2  mov     ecx, 2; unsigned int
0x18000f7a7  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f7ac  jmp     short loc_18000F75F
0x18000f7ae  lea     rax, [rsp+130h+RequiredSize]
0x18000f7b3  mov     [rsp+130h+lpOverlapped], 0; lpOverlapped
0x18000f7bc  mov     [rsp+130h+hTemplateFile], rax; lpBytesReturned
0x18000f7c1  xor     r9d, r9d; nInBufferSize
0x18000f7c4  mov     eax, [rsp+130h+RequiredSize]
0x18000f7c8  xor     r8d, r8d; lpInBuffer
0x18000f7cb  mov     dword ptr [rsp+130h+var_108], eax; nOutBufferSize
0x18000f7cf  mov     edx, 560000h; dwIoControlCode
0x18000f7d4  mov     rcx, rsi; hDevice
0x18000f7d7  mov     [rsp+130h+DeviceInterfaceData], rbx; lpOutBuffer
0x18000f7dc  call    cs:__imp_DeviceIoControl
0x18000f7e2  test    eax, eax
0x18000f7e4  jnz     short loc_18000F80E
0x18000f7e6  call    cs:__imp_GetLastError
0x18000f7ec  lea     rdx, aFailedDGetVolu; "Failed (%d) Get Volume Disk Extents\n\n"
0x18000f7f3  mov     ecx, 2; unsigned int
0x18000f7f8  mov     r8d, eax
0x18000f7fb  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f800  mov     rcx, rbx; hMem
0x18000f803  call    cs:__imp_LocalFree
0x18000f809  jmp     loc_18000F75F
0x18000f80e  or      eax, 0FFFFFFFFh
0x18000f811  xor     r13d, r13d
0x18000f814  mov     [rsp+130h+var_D8], eax
0x18000f818  xor     eax, eax
0x18000f81a  mov     [rsp+130h+var_E0], r13d
0x18000f81f  mov     [rsp+130h+var_E4], eax
0x18000f823  cmp     eax, [rbx]
0x18000f825  jnb     short loc_18000F86B
0x18000f827  lea     rax, [rax+rax*2]
0x18000f82b  mov     edx, [rbx+rax*8+8]
0x18000f82f  mov     [rsp+130h+var_C0], rax
0x18000f834  call    ?IsDiskHotPluggableEx@CGroupPolicy@@IEAA?AW4TriState@1@K@Z; CGroupPolicy::IsDiskHotPluggableEx(ulong)
0x18000f839  xor     r13d, r13d
0x18000f83c  cmp     eax, 2
0x18000f83f  setz    r13b
0x18000f843  test    eax, eax
0x18000f845  jnz     short loc_18000F851
0x18000f847  mov     [rsp+130h+var_E0], 1
0x18000f84f  jmp     short loc_18000F856
0x18000f851  cmp     eax, 2
0x18000f854  jz      short loc_18000F85E
0x18000f856  mov     eax, [rsp+130h+var_E4]
0x18000f85a  inc     eax
0x18000f85c  jmp     short loc_18000F81F
0x18000f85e  mov     rax, [rsp+130h+var_C0]
0x18000f863  mov     eax, [rbx+rax*8+8]
0x18000f867  mov     [rsp+130h+var_D8], eax
0x18000f86b  mov     rcx, rbx; hMem
0x18000f86e  call    cs:__imp_LocalFree
0x18000f874  test    r13d, r13d
0x18000f877  jnz     short loc_18000F8C0
0x18000f879  lea     ebx, [r13+8]
0x18000f87d  mov     ecx, ebx; unsigned int
0x18000f87f  lea     rdx, aWillCheckIfThe; "Will check if the device is hot pluggab"...
0x18000f886  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
  ... truncated ...
```
