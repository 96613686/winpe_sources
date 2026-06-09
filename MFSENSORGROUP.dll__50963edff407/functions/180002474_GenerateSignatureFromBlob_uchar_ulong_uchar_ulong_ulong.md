# GenerateSignatureFromBlob(uchar *,ulong,uchar *,ulong,ulong *)

- ea: `0x180002474`
- end: `0x180002f31`
- name: `?GenerateSignatureFromBlob@@YAJPEAEK0KPEAK@Z`
- size: `2749`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszDeviceInterface@<rcx>, ULONG cbInput@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001534`
- `0x1800019d0`
- `0x18001ce24`

## callees

- `0x180002474`
- `0x1800031fc`
- `0x180003464`
- `0x1800035f0`
- `0x180003740`
- `0x180003ac0`
- `0x180003ce4`
- `0x180005fa0`
- `0x180044b1c`
- `0x180044b28`
- `0x180044f30`
- `0x180045900`
- `0x180076280`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800027f0`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800028bc`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180002970`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800027f0`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1800028bc`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180002970`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800025f5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800026f7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180002a7c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180002ab9`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800025f5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800026f7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180002a7c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180002ab9`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002695`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002796`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002ace`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002b83`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002bac`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002bd7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002c0c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002c2f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002dda`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002e2a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002695`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002796`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002ace`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002b83`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002bac`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002bd7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002c0c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002c2f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002dda`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180002e2a`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180002614`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180002711`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180002614`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180002711`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002647`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002684`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002744`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002785`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002647`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002684`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002744`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180002785`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002825`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800029a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ca0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002d05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002d6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002825`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800029a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ca0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002d05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002d6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002852`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000291e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002852`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000291e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002b71`

## pseudocode

```c
__int64 __fastcall GenerateSignatureFromBlob(
        LPCWSTR pszDeviceInterface,
        ULONG cbInput,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  size_t v6; // rdi
  unsigned int v7; // ebx
  ULONG v9; // ebx
  char *v10; // rax
  char *v11; // r15
  __int64 v12; // r14
  DEVPROPTYPE v13; // edi
  CONFIGRET Device_Interface_PropertyW; // eax
  CONFIGRET v15; // eax
  CONFIGRET DevNode_PropertyW; // eax
  signed int v17; // eax
  bool v18; // sf
  signed int v19; // eax
  ULONG v20; // ebx
  CONFIGRET v21; // eax
  CONFIGRET v22; // eax
  CONFIGRET v23; // eax
  signed int v24; // eax
  bool v25; // sf
  signed int v26; // eax
  CONFIGRET v27; // eax
  LSTATUS v28; // eax
  signed int v29; // ebx
  DEVPROPTYPE v30; // edi
  CONFIGRET v31; // eax
  LSTATUS v32; // eax
  signed int v33; // ebx
  int v34; // r14d
  DEVPROPTYPE v35; // edi
  CONFIGRET v36; // eax
  LSTATUS v37; // eax
  signed int v38; // ebx
  DEVPROPTYPE v39; // r14d
  ULONG v40; // ebx
  __int64 v41; // rcx
  __int64 v42; // rbx
  CONFIGRET v43; // eax
  signed int v44; // eax
  bool v45; // sf
  GUID v46; // xmm0
  __int64 v47; // rbx
  __int64 v48; // rcx
  __int64 v49; // rbx
  int v50; // eax
  union _LARGE_INTEGER v51; // rdx
  int v52; // eax
  signed int v53; // eax
  signed int v54; // eax
  signed int v55; // eax
  bool v56; // sf
  bool v57; // sf
  LSTATUS v58; // eax
  LSTATUS v59; // eax
  LSTATUS v60; // eax
  signed int v61; // eax
  bool v62; // sf
  signed int v63; // eax
  bool v64; // sf
  __int64 v65; // rdx
  DEVPROPTYPE PropertyType; // [rsp+30h] [rbp-D0h] BYREF
  ULONG PropertyBufferSize; // [rsp+34h] [rbp-CCh] BYREF
  DEVNODE pdnDevInst; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v69[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY phkDeviceInterface; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v71[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v72; // [rsp+4Ch] [rbp-B4h]
  BYTE v73[8]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  union _LARGE_INTEGER v75; // [rsp+60h] [rbp-A0h] BYREF
  PUCHAR pbOutput; // [rsp+68h] [rbp-98h]
  BYTE v77[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR PropertyBuffer[264]; // [rsp+80h] [rbp-80h] BYREF
  BYTE Src[528]; // [rsp+290h] [rbp+190h] BYREF

  v72 = a4;
  pbOutput = a3;
  v6 = cbInput;
  v75.QuadPart = 0;
  if ( !pszDeviceInterface || !cbInput )
  {
    v7 = -2147024809;
    if ( !g_wppLevels )
      return v7;
    v65 = 93;
LABEL_143:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v65, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v7);
    return v7;
  }
  if ( !a5 )
  {
    v7 = -2147467261;
    if ( !g_wppLevels )
      return v7;
    v65 = 94;
    goto LABEL_143;
  }
  *a5 = 32;
  if ( !a3 )
  {
    v7 = 0;
    if ( !a4 )
      return v7;
  }
  v9 = cbInput + 592;
  v10 = (char *)operator new[](cbInput + 592);
  v11 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    if ( !g_wppLevels )
      return v7;
    v65 = 95;
    goto LABEL_143;
  }
  memset_0(v10, 0, v9);
  memcpy_0(v11, pszDeviceInterface, v6);
  if ( (v6 & 1) == 0 && !pszDeviceInterface[((unsigned int)v6 >> 1) - 1] )
  {
    *(_QWORD *)v73 = 0;
    memset_0(Src, 0, 0x208u);
    *(_QWORD *)Data = 0;
    *(_DWORD *)v71 = 0;
    *(GUID *)v77 = GUID_00000000_0000_0000_0000_000000000000;
    *(_DWORD *)v69 = 0;
    *(_DWORD *)&v11[v6] = FSIsDeviceInterfaceEnabled(pszDeviceInterface);
    v12 = (unsigned int)(v6 + 4);
    memset_0(PropertyBuffer, 0, 0x208u);
    v13 = 0;
    PropertyBufferSize = 520;
    PropertyType = 0;
    pdnDevInst = 0;
    Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                   pszDeviceInterface,
                                   &DEVPKEY_Device_InstanceId,
                                   &PropertyType,
                                   (PBYTE)PropertyBuffer,
                                   &PropertyBufferSize,
                                   0);
    if ( !Device_Interface_PropertyW )
      goto LABEL_11;
    v19 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0xDu);
    v56 = v19 < 0;
    if ( v19 > 0 )
    {
      v19 = (unsigned __int16)v19 | 0x80070000;
      v56 = v19 < 0;
    }
    if ( !v56 )
    {
LABEL_11:
      v15 = CM_Locate_DevNodeW(&pdnDevInst, PropertyBuffer, 0);
      if ( v15 )
      {
        v61 = CM_MapCrToWin32Err(v15, 0xDu);
        v62 = v61 < 0;
        if ( v61 > 0 )
        {
          v61 = (unsigned __int16)v61 | 0x80070000;
          v62 = v61 < 0;
        }
        if ( v62 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v61);
          goto LABEL_21;
        }
      }
      PropertyBufferSize = 0;
      DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                            pdnDevInst,
                            &DEVPKEY_Device_DriverDate,
                            &PropertyType,
                            0,
                            &PropertyBufferSize,
                            0);
      if ( DevNode_PropertyW == 26 )
      {
        if ( PropertyBufferSize > 8 )
          goto LABEL_21;
        PropertyBufferSize = 8;
        DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                              pdnDevInst,
                              &DEVPKEY_Device_DriverDate,
                              &PropertyType,
                              v73,
                              &PropertyBufferSize,
                              0);
      }
      if ( !DevNode_PropertyW )
      {
LABEL_20:
        *(_QWORD *)&v11[v12] = *(_QWORD *)v73;
        v12 = (unsigned int)(v12 + 8);
        goto LABEL_21;
      }
      v17 = CM_MapCrToWin32Err(DevNode_PropertyW, 0xDu);
      v18 = v17 < 0;
      if ( v17 <= 0 )
      {
LABEL_19:
        if ( !v18 )
          goto LABEL_20;
LABEL_21:
        memset_0(PropertyBuffer, 0, 0x208u);
        PropertyBufferSize = 520;
        pdnDevInst = 0;
        PropertyType = 0;
        v20 = 0;
        v21 = CM_Get_Device_Interface_PropertyW(
                pszDeviceInterface,
                &DEVPKEY_Device_InstanceId,
                &pdnDevInst,
                (PBYTE)PropertyBuffer,
                &PropertyBufferSize,
                0);
        if ( !v21 )
          goto LABEL_22;
        v26 = CM_MapCrToWin32Err(v21, 0xDu);
        v57 = v26 < 0;
        if ( v26 > 0 )
        {
          v26 = (unsigned __int16)v26 | 0x80070000;
          v57 = v26 < 0;
        }
        if ( !v57 )
        {
LABEL_22:
          v22 = CM_Locate_DevNodeW(&PropertyType, PropertyBuffer, 0);
          if ( v22 )
          {
            v63 = CM_MapCrToWin32Err(v22, 0xDu);
            v64 = v63 < 0;
            if ( v63 > 0 )
            {
              v63 = (unsigned __int16)v63 | 0x80070000;
              v64 = v63 < 0;
            }
            if ( v64 )
            {
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  25,
                  &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
                  0,
                  v63);
LABEL_32:
              PropertyType = 0;
              pdnDevInst = 0;
              PropertyBufferSize = 0;
              phkDeviceInterface = 0;
              v27 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, &phkDeviceInterface, 0);
              if ( v27 )
              {
                v53 = CM_MapCrToWin32Err(v27, 0xDu);
                v29 = v53;
                if ( v53 > 0 )
                  v29 = (unsigned __int16)v53 | 0x80070000;
                if ( v29 < 0 )
                  goto LABEL_37;
              }
              PropertyType = 0;
              v28 = RegQueryValueExW(phkDeviceInterface, L"FSSensorGroupHashSalt", 0, &pdnDevInst, 0, &PropertyType);
              v29 = v28;
              if ( v28 )
              {
                if ( v28 > 0 )
                  v29 = (unsigned __int16)v28 | 0x80070000;
                if ( v29 < 0 )
                {
LABEL_37:
                  if ( phkDeviceInterface )
                    RegCloseKey(phkDeviceInterface);
                  if ( v29 >= 0 )
                  {
                    memcpy_0(&v11[(unsigned int)v12], Data, v13);
                    v12 = v13 + (unsigned int)v12;
                  }
                  if ( (int)FSGetDeviceNodeProperty(
                              pszDeviceInterface,
                              (DEVPROPKEY *)&DEVPKEY_Device_Capabilities,
                              v71,
                              4u,
                              &PropertyBufferSize) >= 0 )
                  {
                    *(_DWORD *)&v11[v12] = *(_DWORD *)v71;
                    LODWORD(v12) = v12 + 4;
                  }
                  PropertyType = 0;
                  pdnDevInst = 0;
                  phkDeviceInterface = 0;
                  v30 = 0;
                  v31 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, &phkDeviceInterface, 0);
                  if ( v31 )
                  {
                    v54 = CM_MapCrToWin32Err(v31, 0xDu);
                    v33 = v54;
                    if ( v54 > 0 )
                      v33 = (unsigned __int16)v54 | 0x80070000;
                    if ( v33 < 0 )
                      goto LABEL_48;
                  }
                  PropertyType = 0;
                  v32 = RegQueryValueExW(phkDeviceInterface, L"CPV2FaceAuth", 0, &pdnDevInst, 0, &PropertyType);
                  v33 = v32;
                  if ( v32 )
                  {
                    if ( v32 > 0 )
                      v33 = (unsigned __int16)v32 | 0x80070000;
                    if ( v33 < 0 )
                    {
LABEL_48:
                      if ( phkDeviceInterface )
                        RegCloseKey(phkDeviceInterface);
                      if ( v33 < 0 )
                        *(_DWORD *)v69 = -1;
                      memcpy_0(&v11[(unsigned int)v12], v69, v30);
                      v34 = v30 + v12;
                      PropertyType = 0;
                      pdnDevInst = 0;
                      PropertyBufferSize = 0;
                      phkDeviceInterface = 0;
                      v35 = 0;
                      v36 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, &phkDeviceInterface, 0);
                      if ( v36 )
                      {
                        v55 = CM_MapCrToWin32Err(v36, 0xDu);
                        v38 = v55;
                        if ( v55 > 0 )
                          v38 = (unsigned __int16)v55 | 0x80070000;
                        if ( v38 < 0 )
                          goto LABEL_57;
                      }
                      PropertyType = 0;
                      v37 = RegQueryValueExW(
                              phkDeviceInterface,
                              L"FSSensorOrientation",
                              0,
                              &pdnDevInst,
                              0,
                              &PropertyType);
                      v38 = v37;
                      if ( v37 )
                      {
                        if ( v37 > 0 )
                          v38 = (unsigned __int16)v37 | 0x80070000;
                        if ( v38 < 0 )
                        {
LABEL_57:
                          if ( phkDeviceInterface )
                            RegCloseKey(phkDeviceInterface);
                          if ( v38 < 0 )
                            *(_DWORD *)v69 = 0;
                          memcpy_0(&v11[v34], v69, v35);
                          v39 = v35 + v34;
                          if ( (int)FSGetDeviceNodeRegistryEntry(
                                      pszDeviceInterface,
                                      L"MsxuControlBitmask",
                                      v69,
                                      4u,
                                      &PropertyBufferSize) < 0 )
                            *(_DWORD *)v69 = 0;
                          v40 = PropertyBufferSize;
                          memcpy_0(&v11[v39], v69, PropertyBufferSize);
                          v41 = v40 + v39;
                          v42 = (unsigned int)(v41 + 4);
                          *(_DWORD *)&v11[v41] = 1;
                          pdnDevInst = 0;
                          PropertyType = 0;
                          v43 = CM_Get_Device_Interface_PropertyW(
                                  pszDeviceInterface,
                                  &DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid,
                                  &pdnDevInst,
                                  0,
                                  &PropertyType,
                                  0);
                          if ( v43 == 26 )
                          {
                            if ( PropertyType > 0x10 )
                              goto LABEL_70;
                            PropertyType = 16;
                            v43 = CM_Get_Device_Interface_PropertyW(
                                    pszDeviceInterface,
                                    &DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid,
                                    &pdnDevInst,
                                    v77,
                                    &PropertyType,
                                    0);
                          }
                          if ( !v43 )
                            goto LABEL_88;
                          v44 = CM_MapCrToWin32Err(v43, 0xDu);
                          v45 = v44 < 0;
                          if ( v44 > 0 )
                            v45 = 1;
                          if ( !v45 )
                          {
LABEL_88:
                            v46 = *(GUID *)v77;
                            goto LABEL_71;
                          }
LABEL_70:
                          v46 = GUID_00000000_0000_0000_0000_000000000000;
                          *(GUID *)v77 = GUID_00000000_0000_0000_0000_000000000000;
LABEL_71:
                          *(GUID *)&v11[v42] = v46;
                          v47 = (unsigned int)(v42 + 16);
                          *(_DWORD *)&v11[v47] = FSIsOEMOptInForWindowsEffects(pszDeviceInterface);
                          v48 = (unsigned int)(v47 + 4);
                          v49 = (unsigned int)(v47 + 8);
                          *(_DWORD *)&v11[v48] = 1;
                          v50 = FSGetOSShutdownTime(&v75);
                          v51 = v75;
                          LODWORD(v6) = v49 + 8;
                          if ( v50 < 0 )
                            v51.QuadPart = 0;
                          *(union _LARGE_INTEGER *)&v11[v49] = v51;
                          goto LABEL_74;
                        }
                      }
                      v35 = PropertyType;
                      PropertyBufferSize = PropertyType;
                      if ( PropertyType > 4 )
                      {
                        v38 = -1072860816;
                        goto LABEL_57;
                      }
                      PropertyType = 4;
                      v60 = RegQueryValueExW(
                              phkDeviceInterface,
                              L"FSSensorOrientation",
                              0,
                              &pdnDevInst,
                              v69,
                              &PropertyType);
                      v38 = v60;
                      if ( v60 )
                      {
                        if ( v60 > 0 )
                          v38 = (unsigned __int16)v60 | 0x80070000;
                        if ( v38 < 0 )
                          goto LABEL_57;
                      }
                      else
                      {
                        v38 = 0;
                      }
                      v35 = PropertyType;
                      PropertyBufferSize = PropertyType;
                      goto LABEL_57;
                    }
                  }
                  v30 = PropertyType;
                  if ( PropertyType > 4 )
                  {
                    v33 = -1072860816;
                    goto LABEL_48;
                  }
                  PropertyType = 4;
                  v59 = RegQueryValueExW(phkDeviceInterface, L"CPV2FaceAuth", 0, &pdnDevInst, v69, &PropertyType);
                  v33 = v59;
                  if ( v59 )
                  {
                    if ( v59 > 0 )
                      v33 = (unsigned __int16)v59 | 0x80070000;
                    if ( v33 < 0 )
                      goto LABEL_48;
                  }
                  else
                  {
                    v33 = 0;
                  }
                  v30 = PropertyType;
                  goto LABEL_48;
                }
              }
              v13 = PropertyType;
              PropertyBufferSize = PropertyType;
              if ( PropertyType > 8 )
              {
                v29 = -1072860816;
                goto LABEL_37;
              }
              PropertyType = 8;
              v58 = RegQueryValueExW(phkDeviceInterface, L"FSSensorGroupHashSalt", 0, &pdnDevInst, Data, &PropertyType);
              v29 = v58;
              if ( v58 )
              {
                if ( v58 > 0 )
                  v29 = (unsigned __int16)v58 | 0x80070000;
                if ( v29 < 0 )
                  goto LABEL_37;
              }
              else
              {
                v29 = 0;
              }
              v13 = PropertyType;
              PropertyBufferSize = PropertyType;
              goto LABEL_37;
            }
          }
          PropertyBufferSize = 0;
          v23 = CM_Get_DevNode_PropertyW(
                  PropertyType,
                  &DEVPKEY_Device_DriverVersion,
                  &pdnDevInst,
                  0,
                  &PropertyBufferSize,
                  0);
          v20 = PropertyBufferSize;
          if ( v23 == 26 )
          {
            if ( PropertyBufferSize > 0x206 )
              goto LABEL_32;
            PropertyBufferSize = 518;
            v23 = CM_Get_DevNode_PropertyW(
                    PropertyType,
                    &DEVPKEY_Device_DriverVersion,
                    &pdnDevInst,
                    Src,
                    &PropertyBufferSize,
                    0);
          }
          if ( !v23 )
          {
LABEL_31:
            memcpy_0(&v11[(unsigned int)v12], Src, v20 + 2LL);
            v12 = v20 + (unsigned int)v12;
            goto LABEL_32;
          }
          v24 = CM_MapCrToWin32Err(v23, 0xDu);
          v25 = v24 < 0;
          if ( v24 <= 0 )
          {
LABEL_30:
            if ( v25 )
              goto LABEL_32;
            goto LABEL_31;
          }
          v26 = (unsigned __int16)v24 | 0x80070000;
        }
        v25 = v26 < 0;
        goto LABEL_30;
      }
      v19 = (unsigned __int16)v17 | 0x80070000;
    }
    v18 = v19 < 0;
    goto LABEL_19;
  }
LABEL_74:
  v52 = FSCreateHash(L"SHA256", (PUCHAR)v11, v6, pbOutput, v72, a5);
  v7 = v52;
  if ( v52 < 0 && g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v52);
  operator delete(v11);
  return v7;
}

```

## disassembly

```asm
0x180002474  push    rbp
0x180002476  push    rbx
0x180002477  push    rdi
0x180002478  push    r12
0x18000247a  push    r13
0x18000247c  push    r14
0x18000247e  push    r15
0x180002480  lea     rbp, [rsp-3B0h]
0x180002488  sub     rsp, 4B0h
0x18000248f  mov     rax, cs:__security_cookie
0x180002496  xor     rax, rsp
0x180002499  mov     [rbp+3E0h+var_40], rax
0x1800024a0  mov     r13, [rbp+3E0h+arg_20]
0x1800024a7  xor     r14d, r14d
0x1800024aa  mov     [rsp+4E0h+var_494], r9d
0x1800024af  mov     rax, r8
0x1800024b2  mov     [rsp+4E0h+pbOutput], rax
0x1800024b7  mov     r12, rcx
0x1800024ba  mov     edi, edx
0x1800024bc  mov     qword ptr [rsp+4E0h+var_480], r14
0x1800024c1  test    rcx, rcx
0x1800024c4  jnz     short loc_1800024FC
0x1800024c6  mov     ebx, 80070057h
0x1800024cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800024d2  jnb     loc_180002F09
0x1800024d8  mov     eax, ebx
0x1800024da  mov     rcx, [rbp+3E0h+var_40]
0x1800024e1  xor     rcx, rsp; StackCookie
0x1800024e4  call    __security_check_cookie
0x1800024e9  add     rsp, 4B0h
0x1800024f0  pop     r15
0x1800024f2  pop     r14
0x1800024f4  pop     r13
0x1800024f6  pop     r12
0x1800024f8  pop     rdi
0x1800024f9  pop     rbx
0x1800024fa  pop     rbp
0x1800024fb  retn
0x1800024fc  test    edx, edx
0x1800024fe  jz      short loc_1800024C6
0x180002500  test    r13, r13
0x180002503  jz      loc_180002E87
0x180002509  mov     dword ptr [r13+0], 20h ; ' '
0x180002511  test    rax, rax
0x180002514  jz      loc_180002C4E
0x18000251a  lea     eax, [rdi+250h]
0x180002520  mov     ecx, eax; unsigned __int64
0x180002522  mov     ebx, eax
0x180002524  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002529  mov     r15, rax
0x18000252c  test    rax, rax
0x18000252f  jz      loc_180002EA0
0x180002535  mov     r8d, ebx; Size
0x180002538  xor     edx, edx; Val
0x18000253a  mov     rcx, rax; void *
0x18000253d  call    memset_0
0x180002542  mov     r8, rdi; Size
0x180002545  mov     rdx, r12; Src
0x180002548  mov     rcx, r15; void *
0x18000254b  call    memcpy_0
0x180002550  test    dil, 1
0x180002554  jnz     loc_180002B36
0x18000255a  mov     eax, edi
0x18000255c  shr     eax, 1
0x18000255e  dec     eax
0x180002560  cmp     [r12+rax*2], r14w
0x180002565  jnz     loc_180002B36
0x18000256b  xor     edx, edx; Val
0x18000256d  mov     qword ptr [rsp+4E0h+var_490], r14
0x180002572  mov     r8d, 208h; Size
0x180002578  lea     rcx, [rbp+3E0h+Src]; void *
0x18000257f  call    memset_0
0x180002584  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000258b  mov     rcx, r12; unsigned __int16 *
0x18000258e  mov     qword ptr [rsp+4E0h+Data], r14
0x180002593  mov     dword ptr [rsp+4E0h+var_498], r14d
0x180002598  movdqu  xmmword ptr [rsp+4E0h+var_470], xmm0
0x18000259e  mov     dword ptr [rsp+4E0h+var_4A4], r14d
0x1800025a3  call    ?FSIsDeviceInterfaceEnabled@@YA_NPEBG@Z; FSIsDeviceInterfaceEnabled(ushort const *)
0x1800025a8  movzx   eax, al
0x1800025ab  lea     rcx, [rbp+3E0h+PropertyBuffer]; void *
0x1800025af  mov     ebx, 208h
0x1800025b4  mov     [rdi+r15], eax
0x1800025b8  mov     r8d, ebx; Size
0x1800025bb  lea     r14d, [rdi+4]
0x1800025bf  xor     edx, edx; Val
0x1800025c1  call    memset_0
0x1800025c6  xor     edi, edi
0x1800025c8  mov     [rsp+4E0h+var_4AC], ebx
0x1800025cc  lea     rax, [rsp+4E0h+var_4AC]
0x1800025d1  mov     [rsp+4E0h+ulFlags], edi; ulFlags
0x1800025d5  lea     r9, [rbp+3E0h+PropertyBuffer]; PropertyBuffer
0x1800025d9  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800025de  lea     r8, [rsp+4E0h+PropertyType]; PropertyType
0x1800025e3  mov     [rsp+4E0h+PropertyType], edi
0x1800025e7  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800025ee  mov     [rsp+4E0h+pdnDevInst], edi
0x1800025f2  mov     rcx, r12; pszDeviceInterface
0x1800025f5  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800025fb  mov     ebx, 80070000h
0x180002600  test    eax, eax
0x180002602  jnz     loc_180002C05
0x180002608  xor     r8d, r8d; ulFlags
0x18000260b  lea     rdx, [rbp+3E0h+PropertyBuffer]; pDeviceID
0x18000260f  lea     rcx, [rsp+4E0h+pdnDevInst]; pdnDevInst
0x180002614  call    cs:__imp_CM_Locate_DevNodeW
0x18000261a  test    eax, eax
0x18000261c  jnz     loc_180002DD3
0x180002622  mov     ecx, [rsp+4E0h+pdnDevInst]; dnDevInst
0x180002626  lea     rax, [rsp+4E0h+var_4AC]
0x18000262b  mov     [rsp+4E0h+ulFlags], edi; ulFlags
0x18000262f  lea     r8, [rsp+4E0h+PropertyType]; PropertyType
0x180002634  xor     r9d, r9d; PropertyBuffer
0x180002637  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x18000263c  lea     rdx, DEVPKEY_Device_DriverDate; PropertyKey
0x180002643  mov     [rsp+4E0h+var_4AC], edi
0x180002647  call    cs:__imp_CM_Get_DevNode_PropertyW
0x18000264d  cmp     eax, 1Ah
0x180002650  jnz     short loc_18000268A
0x180002652  cmp     [rsp+4E0h+var_4AC], 8
0x180002657  ja      short loc_1800026B5
0x180002659  mov     ecx, [rsp+4E0h+pdnDevInst]; dnDevInst
0x18000265d  lea     rax, [rsp+4E0h+var_4AC]
0x180002662  mov     [rsp+4E0h+ulFlags], edi; ulFlags
0x180002666  lea     r9, [rsp+4E0h+var_490]; PropertyBuffer
0x18000266b  lea     r8, [rsp+4E0h+PropertyType]; PropertyType
0x180002670  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x180002675  lea     rdx, DEVPKEY_Device_DriverDate; PropertyKey
0x18000267c  mov     [rsp+4E0h+var_4AC], 8
0x180002684  call    cs:__imp_CM_Get_DevNode_PropertyW
0x18000268a  test    eax, eax
0x18000268c  jz      short loc_1800026A8
0x18000268e  mov     edx, 0Dh; DefaultErr
0x180002693  mov     ecx, eax; CmReturnCode
0x180002695  call    cs:__imp_CM_MapCrToWin32Err
0x18000269b  test    eax, eax
0x18000269d  jle     short loc_1800026A6
0x18000269f  movzx   eax, ax
0x1800026a2  or      eax, ebx
0x1800026a4  test    eax, eax
0x1800026a6  js      short loc_1800026B5
0x1800026a8  mov     rax, qword ptr [rsp+4E0h+var_490]
0x1800026ad  mov     [r14+r15], rax
0x1800026b1  add     r14d, 8
0x1800026b5  mov     ebx, 208h
0x1800026ba  lea     rcx, [rbp+3E0h+PropertyBuffer]; void *
0x1800026be  mov     r8d, ebx; Size
0x1800026c1  xor     edx, edx; Val
0x1800026c3  call    memset_0
0x1800026c8  lea     rax, [rsp+4E0h+var_4AC]
0x1800026cd  mov     [rsp+4E0h+var_4AC], ebx
0x1800026d1  mov     [rsp+4E0h+ulFlags], edi; ulFlags
0x1800026d5  lea     r9, [rbp+3E0h+PropertyBuffer]; PropertyBuffer
0x1800026d9  lea     r8, [rsp+4E0h+pdnDevInst]; PropertyType
0x1800026de  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800026e3  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800026ea  mov     [rsp+4E0h+pdnDevInst], edi
0x1800026ee  mov     rcx, r12; pszDeviceInterface
0x1800026f1  mov     [rsp+4E0h+PropertyType], edi
0x1800026f5  mov     ebx, edi
0x1800026f7  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800026fd  test    eax, eax
0x1800026ff  jnz     loc_180002C28
0x180002705  xor     r8d, r8d; ulFlags
0x180002708  lea     rdx, [rbp+3E0h+PropertyBuffer]; pDeviceID
0x18000270c  lea     rcx, [rsp+4E0h+PropertyType]; pdnDevInst
0x180002711  call    cs:__imp_CM_Locate_DevNodeW
0x180002717  test    eax, eax
0x180002719  jnz     loc_180002E23
0x18000271f  mov     ecx, [rsp+4E0h+PropertyType]; dnDevInst
0x180002723  lea     rax, [rsp+4E0h+var_4AC]
0x180002728  mov     [rsp+4E0h+ulFlags], edi; ulFlags
0x18000272c  lea     r8, [rsp+4E0h+pdnDevInst]; PropertyType
0x180002731  xor     r9d, r9d; PropertyBuffer
0x180002734  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x180002739  lea     rdx, DEVPKEY_Device_DriverVersion; PropertyKey
0x180002740  mov     [rsp+4E0h+var_4AC], edi
0x180002744  call    cs:__imp_CM_Get_DevNode_PropertyW
0x18000274a  mov     ebx, [rsp+4E0h+var_4AC]
0x18000274e  cmp     eax, 1Ah
0x180002751  jnz     short loc_18000278B
0x180002753  mov     eax, 206h
0x180002758  cmp     ebx, eax
0x18000275a  ja      short loc_1800027C8
0x18000275c  mov     ecx, [rsp+4E0h+PropertyType]; dnDevInst
0x180002760  lea     r9, [rbp+3E0h+Src]; PropertyBuffer
0x180002767  mov     [rsp+4E0h+var_4AC], eax
0x18000276b  lea     r8, [rsp+4E0h+pdnDevInst]; PropertyType
0x180002770  lea     rax, [rsp+4E0h+var_4AC]
0x180002775  mov     [rsp+4E0h+ulFlags], edi; ulFlags
0x180002779  lea     rdx, DEVPKEY_Device_DriverVersion; PropertyKey
0x180002780  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x180002785  call    cs:__imp_CM_Get_DevNode_PropertyW
0x18000278b  test    eax, eax
0x18000278d  jz      short loc_1800027AC
0x18000278f  mov     edx, 0Dh; DefaultErr
0x180002794  mov     ecx, eax; CmReturnCode
0x180002796  call    cs:__imp_CM_MapCrToWin32Err
0x18000279c  test    eax, eax
0x18000279e  jle     short loc_1800027AA
0x1800027a0  movzx   eax, ax
0x1800027a3  or      eax, 80070000h
0x1800027a8  test    eax, eax
0x1800027aa  js      short loc_1800027C8
0x1800027ac  mov     r8d, ebx
0x1800027af  lea     rdx, [rbp+3E0h+Src]; Src
0x1800027b6  mov     ecx, r14d
0x1800027b9  add     r8, 2; Size
0x1800027bd  add     rcx, r15; void *
0x1800027c0  call    memcpy_0
0x1800027c5  add     r14d, ebx
0x1800027c8  lea     r9, [rsp+4E0h+phkDeviceInterface]; phkDeviceInterface
0x1800027cd  mov     [rsp+4E0h+PropertyType], edi
0x1800027d1  mov     edx, 20019h; samDesired
0x1800027d6  mov     [rsp+4E0h+pdnDevInst], edi
0x1800027da  mov     r8d, 1; Disposition
0x1800027e0  mov     [rsp+4E0h+var_4AC], edi
0x1800027e4  mov     rcx, r12; pszDeviceInterface
0x1800027e7  mov     [rsp+4E0h+phkDeviceInterface], rdi
0x1800027ec  mov     dword ptr [rsp+4E0h+PropertyBufferSize], edi; ulFlags
0x1800027f0  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x1800027f6  test    eax, eax
0x1800027f8  jnz     loc_180002B7C
0x1800027fe  mov     rcx, [rsp+4E0h+phkDeviceInterface]; hKey
0x180002803  lea     rax, [rsp+4E0h+PropertyType]
0x180002808  mov     qword ptr [rsp+4E0h+ulFlags], rax; lpcbData
0x18000280d  lea     r9, [rsp+4E0h+pdnDevInst]; lpType
0x180002812  xor     r8d, r8d; lpReserved
0x180002815  mov     [rsp+4E0h+PropertyBufferSize], rdi; lpData
0x18000281a  lea     rdx, ValueName; "FSSensorGroupHashSalt"
0x180002821  mov     [rsp+4E0h+PropertyType], edi
0x180002825  call    cs:__imp_RegQueryValueExW
0x18000282b  mov     ebx, eax
0x18000282d  test    eax, eax
0x18000282f  jz      loc_180002C5F
0x180002835  jle     short loc_180002840
0x180002837  movzx   ebx, ax
0x18000283a  or      ebx, 80070000h
0x180002840  test    ebx, ebx
0x180002842  jns     loc_180002C5F
0x180002848  mov     rcx, [rsp+4E0h+phkDeviceInterface]; hKey
0x18000284d  test    rcx, rcx
0x180002850  jz      short loc_180002858
0x180002852  call    cs:__imp_RegCloseKey
0x180002858  test    ebx, ebx
0x18000285a  jns     loc_180002EB9
0x180002860  lea     rax, [rsp+4E0h+var_4AC]
0x180002865  mov     r9d, 4; unsigned int
0x18000286b  lea     r8, [rsp+4E0h+var_498]; PropertyBuffer
0x180002870  mov     [rsp+4E0h+PropertyBufferSize], rax; unsigned int *
0x180002875  lea     rdx, DEVPKEY_Device_Capabilities; PropertyKey
0x18000287c  mov     rcx, r12; pszDeviceInterface
0x18000287f  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180002884  xor     ebx, ebx
0x180002886  test    eax, eax
0x180002888  js      short loc_180002896
0x18000288a  mov     eax, dword ptr [rsp+4E0h+var_498]
0x18000288e  mov     [r14+r15], eax
0x180002892  add     r14d, 4
0x180002896  lea     r9, [rsp+4E0h+phkDeviceInterface]; phkDeviceInterface
0x18000289b  mov     [rsp+4E0h+PropertyType], ebx
0x18000289f  mov     edx, 20019h; samDesired
0x1800028a4  mov     [rsp+4E0h+pdnDevInst], ebx
0x1800028a8  mov     r8d, 1; Disposition
0x1800028ae  mov     [rsp+4E0h+phkDeviceInterface], rbx
0x1800028b3  mov     rcx, r12; pszDeviceInterface
0x1800028b6  mov     dword ptr [rsp+4E0h+PropertyBufferSize], ebx; ulFlags
0x1800028ba  mov     edi, ebx
0x1800028bc  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x1800028c2  test    eax, eax
0x1800028c4  jnz     loc_180002BA5
0x1800028ca  mov     rcx, [rsp+4E0h+phkDeviceInterface]; hKey
0x1800028cf  lea     rax, [rsp+4E0h+PropertyType]
0x1800028d4  mov     qword ptr [rsp+4E0h+ulFlags], rax; lpcbData
0x1800028d9  lea     r9, [rsp+4E0h+pdnDevInst]; lpType
0x1800028de  xor     r8d, r8d; lpReserved
0x1800028e1  mov     [rsp+4E0h+PropertyBufferSize], rbx; lpData
0x1800028e6  lea     rdx, aCpv2faceauth; "CPV2FaceAuth"
0x1800028ed  mov     [rsp+4E0h+PropertyType], ebx
0x1800028f1  call    cs:__imp_RegQueryValueExW
0x1800028f7  mov     ebx, eax
0x1800028f9  test    eax, eax
0x1800028fb  jz      loc_180002CC8
0x180002901  jle     short loc_18000290C
0x180002903  movzx   ebx, ax
0x180002906  or      ebx, 80070000h
0x18000290c  test    ebx, ebx
0x18000290e  jns     loc_180002CC8
0x180002914  mov     rcx, [rsp+4E0h+phkDeviceInterface]; hKey
0x180002919  test    rcx, rcx
0x18000291c  jz      short loc_180002924
0x18000291e  call    cs:__imp_RegCloseKey
0x180002924  test    ebx, ebx
0x180002926  jns     short loc_180002930
0x180002928  mov     dword ptr [rsp+4E0h+var_4A4], 0FFFFFFFFh
0x180002930  mov     ecx, r14d
0x180002933  lea     rdx, [rsp+4E0h+var_4A4]; Src
0x180002938  add     rcx, r15; void *
0x18000293b  mov     r8d, edi; Size
0x18000293e  call    memcpy_0
  ... truncated ...
```
