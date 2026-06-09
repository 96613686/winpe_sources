# CUsbDeviceEnumerator::GetDevicesToRedirect(IDeviceCollection *)

- ea: `0x1805f0a00`
- end: `0x1805f1a44`
- name: `?GetDevicesToRedirect@CUsbDeviceEnumerator@@UEAAJPEAUIDeviceCollection@@@Z`
- size: `4164`
- prototype: `__int64 __fastcall(CUsbDeviceEnumerator *__hidden this, struct IDeviceCollection *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800186a0`
- `0x1800186d0`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18012962c`
- `0x18012966c`
- `0x1805ee578`
- `0x1805ef060`
- `0x1805f0a00`
- `0x1805f2ca4`
- `0x1805f9eec`
- `0x180688f26`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1805f1882`
- `KERNEL32!CloseHandle` at `0x1805f1882`
- `KERNEL32!DeviceIoControl` at `0x1805f14d1`
- `KERNEL32!DeviceIoControl` at `0x1805f1556`
- `KERNEL32!DeviceIoControl` at `0x1805f14d1`
- `KERNEL32!DeviceIoControl` at `0x1805f1556`
- `KERNEL32!GetLastError` at `0x1805f0ae5`
- `KERNEL32!GetLastError` at `0x1805f0b85`
- `KERNEL32!GetLastError` at `0x1805f0c06`
- `KERNEL32!GetLastError` at `0x1805f0e9a`
- `KERNEL32!GetLastError` at `0x1805f0ee0`
- `KERNEL32!GetLastError` at `0x1805f0fb0`
- `KERNEL32!GetLastError` at `0x1805f1049`
- `KERNEL32!GetLastError` at `0x1805f10bc`
- `KERNEL32!GetLastError` at `0x1805f124f`
- `KERNEL32!GetLastError` at `0x1805f1297`
- `KERNEL32!GetLastError` at `0x1805f14df`
- `KERNEL32!GetLastError` at `0x1805f1560`
- `KERNEL32!GetLastError` at `0x1805f0ae5`
- `KERNEL32!GetLastError` at `0x1805f0b85`
- `KERNEL32!GetLastError` at `0x1805f0c06`
- `KERNEL32!GetLastError` at `0x1805f0e9a`
- `KERNEL32!GetLastError` at `0x1805f0ee0`
- `KERNEL32!GetLastError` at `0x1805f0fb0`
- `KERNEL32!GetLastError` at `0x1805f1049`
- `KERNEL32!GetLastError` at `0x1805f10bc`
- `KERNEL32!GetLastError` at `0x1805f124f`
- `KERNEL32!GetLastError` at `0x1805f1297`
- `KERNEL32!GetLastError` at `0x1805f14df`
- `KERNEL32!GetLastError` at `0x1805f1560`
- `KERNEL32!CreateFileW` at `0x1805f0ad2`
- `KERNEL32!CreateFileW` at `0x1805f0ad2`
- `setupapi!CM_Get_Device_ID_Size` at `0x1805f11b7`
- `setupapi!CM_Get_Device_ID_Size` at `0x1805f11b7`
- `setupapi!CM_Get_Device_IDW` at `0x1805f120d`
- `setupapi!CM_Get_Device_IDW` at `0x1805f120d`
- `setupapi!CM_Locate_DevNodeW` at `0x1805f0f68`
- `setupapi!CM_Locate_DevNodeW` at `0x1805f0f68`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1805f0ed2`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1805f0f50`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1805f0ed2`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1805f0f50`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805f0e8c`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805f0e8c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805f0c7f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805f0e5c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805f12d3`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805f0c7f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805f0e5c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805f12d3`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805f0bfc`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805f128d`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805f0bfc`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805f128d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f1223`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f1861`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f1874`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f1223`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f1861`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1805f1874`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1805f0fa2`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1805f1025`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1805f0fa2`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1805f1025`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f0b71`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f123c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f0b71`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805f123c`
- `CFGMGR32!CM_Get_Sibling` at `0x1805f1185`
- `CFGMGR32!CM_Get_Sibling` at `0x1805f1185`
- `CFGMGR32!CM_Get_Child` at `0x1805f1179`
- `CFGMGR32!CM_Get_Child` at `0x1805f1179`

## string_xrefs

- `0x1805f0bd3`: `DevObjCreateDeviceInfoList FAILED`
- `0x1805f17a1`: `DevObjCreateDeviceInfoList FAILED`
- `0x1805f0b33`: `CreateFile failed`
- `0x1805f0a62`: `\\.\TerminalServicesUSBFilterDriverControlObject`
- `0x1805f13af`: `USB\COMPOSITE`

## pseudocode

```c
__int64 __fastcall CUsbDeviceEnumerator::GetDevicesToRedirect(CUsbDeviceEnumerator *this, struct IDeviceCollection *a2)
{
  unsigned int v2; // edi
  __int64 v3; // r12
  signed int v4; // ebx
  struct _IOCTL_TSUSB_FILTER_QUERY_CHILD_DEVICE_TEXT_OUTPUT *v5; // r14
  void *v6; // r13
  __int64 v7; // r15
  HANDLE v8; // rsi
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  signed int v13; // eax
  signed int v14; // eax
  int v15; // eax
  void *v16; // rax
  unsigned int v17; // eax
  void *v18; // rax
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  void *v22; // rax
  __int64 i; // rdi
  signed int v24; // eax
  signed int v25; // eax
  WCHAR *v26; // rbx
  signed int v27; // eax
  _DWORD *v28; // rcx
  signed int v29; // eax
  signed int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rsi
  _DWORD *v33; // rbx
  __int64 v34; // r12
  CONFIGRET Sibling; // eax
  __int64 v36; // rcx
  void *v37; // rax
  signed int v38; // eax
  signed int v39; // eax
  int v40; // eax
  unsigned int v41; // r15d
  CUsbDeviceEnumerator *v42; // rcx
  int v43; // eax
  CUsbDeviceEnumerator *v44; // rcx
  unsigned int *v45; // r9
  wchar_t *v46; // rax
  unsigned int v47; // r14d
  int v48; // r12d
  unsigned int v49; // eax
  unsigned int v50; // ebx
  DWORD v51; // esi
  _DWORD *v52; // rax
  unsigned int *v53; // rcx
  size_t v54; // r8
  __int64 v55; // rax
  void *v56; // rdx
  char *v57; // rbx
  DWORD v58; // eax
  int v59; // ecx
  bool v60; // sf
  DWORD v61; // r9d
  signed int v62; // eax
  struct IDeviceCollection *v63; // rbx
  void *v64; // rsi
  CUsbDeviceEnumerator *v65; // rcx
  int v66; // ebx
  unsigned int v67; // eax
  int v68; // ebx
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  int v72; // edx
  const char *v73; // rcx
  void **v74; // r13
  __int64 j; // rdi
  unsigned int v77; // eax
  unsigned int v78; // eax
  int v79; // edx
  const char *v80; // rcx
  unsigned int v81; // eax
  unsigned __int8 v82[8]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  DEVNODE dnDevInst; // [rsp+50h] [rbp-B0h] BYREF
  struct _IOCTL_TSUSB_FILTER_QUERY_CHILD_DEVICE_TEXT_OUTPUT *v85; // [rsp+58h] [rbp-A8h] BYREF
  int v86; // [rsp+60h] [rbp-A0h]
  __int64 DeviceInfoList; // [rsp+68h] [rbp-98h]
  unsigned int v88; // [rsp+70h] [rbp-90h] BYREF
  ULONG pulLen; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v90; // [rsp+78h] [rbp-88h]
  unsigned int v91; // [rsp+80h] [rbp-80h] BYREF
  DEVNODE pdnDevInst; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD BytesReturned; // [rsp+88h] [rbp-78h] BYREF
  __int64 v94; // [rsp+90h] [rbp-70h]
  struct ILocalDevice *v95; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h]
  void *v98; // [rsp+B0h] [rbp-50h]
  void *v99; // [rsp+B8h] [rbp-48h] BYREF
  void *v100; // [rsp+C0h] [rbp-40h]
  unsigned int Size; // [rsp+C8h] [rbp-38h] BYREF
  int Size_4; // [rsp+CCh] [rbp-34h]
  void *lpInBuffer; // [rsp+D0h] [rbp-30h]
  void *v104; // [rsp+D8h] [rbp-28h]
  void *Src; // [rsp+E0h] [rbp-20h]
  void *v106; // [rsp+E8h] [rbp-18h]
  int v107; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v108; // [rsp+F4h] [rbp-Ch] BYREF
  void *v109; // [rsp+F8h] [rbp-8h]
  CUsbDeviceEnumerator *v110; // [rsp+100h] [rbp+0h]
  struct IDeviceCollection *v111; // [rsp+108h] [rbp+8h]
  _OWORD v112[2]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v113[3]; // [rsp+130h] [rbp+30h] BYREF

  v2 = 0;
  v111 = a2;
  v110 = this;
  v3 = -1;
  v91 = 0;
  v88 = 0;
  pulLen = 0;
  BytesReturned = 0;
  v4 = 0;
  v85 = 0;
  memset(v112, 0, sizeof(v112));
  v5 = 0;
  v108 = 0;
  dnDevInst = 0;
  v6 = 0;
  memset(v113, 0, sizeof(v113));
  pdnDevInst = 0;
  LODWORD(v7) = 0;
  v107 = 0;
  v95 = 0;
  v90 = -1;
  v99 = 0;
  Src = 0;
  Block = 0;
  lpInBuffer = 0;
  v109 = 0;
  v104 = 0;
  v106 = 0;
  v100 = 0;
  v98 = 0;
  hDevice = CreateFileW(L"\\\\.\\TerminalServicesUSBFilterDriverControlObject", 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v8 = hDevice;
  if ( hDevice == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_183;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 31;
      v12 = "CreateFile failed";
      goto LABEL_9;
    }
  }
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_183;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 32;
      v12 = "DevObjCreateDeviceInfoList FAILED";
      goto LABEL_9;
    }
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_TSUSBBUS_FILTER, 0, 18, 0, 0) )
  {
    v14 = GetLastError();
    v4 = v14;
    if ( v14 > 0 )
      v4 = (unsigned __int16)v14 | 0x80070000;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_183;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 33;
      v12 = "DevObjGetClassDevs failed";
LABEL_9:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v12,
        v4);
      goto LABEL_183;
    }
  }
  do
  {
    LODWORD(v112[0]) = 32;
    v15 = DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DEVINTERFACE_TSUSBBUS_FILTER, v2, v112);
    v7 = v2 + 1;
    if ( !v15 )
      v7 = v2;
    v86 = v7;
    v2 = v7;
  }
  while ( v15 );
  if ( !(_DWORD)v7 )
  {
    v4 = -2147023728;
    goto LABEL_183;
  }
  v16 = operator new(saturated_mul((unsigned int)v7, 4u));
  v98 = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
        v17,
        (__int64)"DEVINST");
    }
    v4 = -2147024882;
    goto LABEL_183;
  }
  memset_0(v16, 0, 4 * v7);
  v18 = operator new(saturated_mul((unsigned int)v7, 8u));
  v106 = v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 35;
      v21 = "PWSTR";
      goto LABEL_42;
    }
    goto LABEL_43;
  }
  memset_0(v18, 0, 8 * v7);
  v22 = operator new(saturated_mul((unsigned int)v7, 4u));
  v100 = v22;
  if ( !v22 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 36;
      v21 = "DEVINST";
      goto LABEL_42;
    }
    goto LABEL_43;
  }
  memset_0(v22, 0, 4 * v7);
  for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
  {
    LODWORD(v112[0]) = 32;
    if ( (unsigned int)DevObjEnumDeviceInterfaces(v3, 0, &GUID_DEVINTERFACE_TSUSBBUS_FILTER, (unsigned int)i, v112) )
    {
      LODWORD(v113[0]) = 48;
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v3, v112, 0, 0, 0, v113) )
        goto LABEL_81;
      v24 = GetLastError();
      v4 = v24;
      if ( v24 != 122 )
      {
        if ( v24 > 0 )
          v4 = (unsigned __int16)v24 | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_82;
      }
      if ( (unsigned int)DevObjGetDeviceInstanceId(v3, v113, 0, 0, &v91) )
        goto LABEL_81;
      v25 = GetLastError();
      v4 = v25;
      if ( v25 != 122 )
      {
        if ( v25 > 0 )
          v4 = (unsigned __int16)v25 | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_82;
      }
      operator delete(Block);
      Block = operator new(saturated_mul(v91, 2u));
      v26 = (WCHAR *)Block;
      if ( !Block )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
            v31,
            (__int64)"WCHAR");
        }
        v4 = -2147024882;
        goto LABEL_82;
      }
      if ( !(unsigned int)DevObjGetDeviceInstanceId(v3, v113, Block, v91, &v91) )
      {
        v30 = GetLastError();
        v4 = v30;
        if ( v30 > 0 )
          v4 = (unsigned __int16)v30 | 0x80070000;
        goto LABEL_82;
      }
      if ( CM_Locate_DevNodeW(&pdnDevInst, v26, 0) )
      {
        v4 = -2147024865;
        goto LABEL_82;
      }
      *((_DWORD *)v98 + i) = pdnDevInst;
      if ( (unsigned int)DevObjGetDeviceRegistryProperty(v3, v113, 14, 0, 0, 0, &v88) )
      {
LABEL_81:
        v4 = -2147024809;
LABEL_82:
        v6 = 0;
        goto LABEL_182;
      }
      v27 = GetLastError();
      v4 = v27;
      if ( v27 == 122 )
      {
        v4 = 0;
      }
      else
      {
        if ( v27 > 0 )
          v4 = (unsigned __int16)v27 | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_82;
      }
      operator delete(0);
      v6 = operator new(saturated_mul((unsigned __int64)v88 >> 1, 2u));
      if ( !v6 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 38;
          v21 = "WCHAR";
LABEL_42:
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
            v19,
            (__int64)v21);
        }
LABEL_43:
        v4 = -2147024882;
        goto LABEL_182;
      }
      if ( !(unsigned int)DevObjGetDeviceRegistryProperty(v3, v113, 14, 0, v6, v88, &v88) )
      {
        v29 = GetLastError();
        v4 = v29;
        if ( v29 > 0 )
          v4 = (unsigned __int16)v29 | 0x80070000;
        goto LABEL_182;
      }
      v28 = v100;
      *((_QWORD *)v106 + i) = v6;
      v28[i] = v88;
    }
  }
  if ( (_DWORD)i != (_DWORD)v7 )
    goto LABEL_82;
  v32 = 0;
LABEL_93:
  v6 = 0;
  Size_4 = v32;
  if ( (unsigned int)v32 >= (unsigned int)v7 )
    goto LABEL_181;
  v33 = v98;
  v34 = v90;
  v94 = v32;
  pdnDevInst = *((_DWORD *)v98 + v32);
  dnDevInst = 0;
  while ( 1 )
  {
    do
    {
LABEL_95:
      if ( dnDevInst )
        Sibling = CM_Get_Sibling(&dnDevInst, dnDevInst, 0);
      else
        Sibling = CM_Get_Child(&dnDevInst, pdnDevInst, 0);
      v6 = 0;
      if ( Sibling )
      {
        v4 = 0;
LABEL_175:
        v32 = (unsigned int)(Size_4 + 1);
        goto LABEL_93;
      }
      v36 = 0;
    }
    while ( !(_DWORD)v7 );
    do
    {
      if ( v33[v36] == dnDevInst )
        goto LABEL_95;
      v36 = (unsigned int)(v36 + 1);
    }
    while ( (unsigned int)v36 < (unsigned int)v7 );
    if ( (_DWORD)v36 != (_DWORD)v7 )
      goto LABEL_95;
    if ( CM_Get_Device_ID_Size(&pulLen, dnDevInst, 0) )
    {
LABEL_173:
      v4 = -2147024865;
      goto LABEL_175;
    }
    ++pulLen;
    operator delete(v104);
    v37 = operator new(saturated_mul(pulLen, 2u));
    v104 = v37;
    if ( !v37 )
      break;
    if ( CM_Get_Device_IDW(dnDevInst, (PWSTR)v37, pulLen, 0) )
      goto LABEL_173;
    if ( v34 != -1 )
      DevObjDestroyDeviceInfoList(v34);
    v90 = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v34 = v90;
    if ( v90 == -1 )
    {
      v38 = GetLastError();
      v4 = v38;
      if ( v38 > 0 )
        v4 = (unsigned __int16)v38 | 0x80070000;
      if ( v4 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
          goto LABEL_181;
        if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 )
        {
          v8 = hDevice;
          goto LABEL_205;
        }
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_181;
        v71 = RdpWppGetCurrentThreadActivityIdPrefix();
        v72 = 40;
        v73 = "DevObjCreateDeviceInfoList FAILED";
LABEL_180:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v72,
          (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
          v71,
          (__int64)v73,
          v4);
        goto LABEL_181;
      }
    }
    if ( !(unsigned int)DevObjGetClassDevs(v34, 0, v104, 20, 0, 0) )
    {
      v39 = GetLastError();
      v4 = v39;
      if ( v39 > 0 )
        v4 = (unsigned __int16)v39 | 0x80070000;
      if ( v4 < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_181;
        }
        v71 = RdpWppGetCurrentThreadActivityIdPrefix();
        v72 = 41;
        v73 = "DevObjGetClassDevs failed";
        goto LABEL_180;
      }
    }
    LODWORD(v112[0]) = 32;
    v40 = DevObjEnumDeviceInterfaces(v34, 0, &GUID_DEVINTERFACE_TSUSBGD, 0, v112);
    v33 = v98;
    if ( v40 == 1 )
      goto LABEL_95;
    v82[0] = 0;
    v41 = CUsbDeviceEnumerator::DeviceRedirectionCheck(v110, dnDevInst);
    Size = 0;
    operator delete(Src);
    String1 = 0;
    v43 = CUsbDeviceEnumerator::CMGetDevNodeRegistryProperty(v42, dnDevInst, 0xFu, (void **)&String1, &Size, v82);
    Src = String1;
    if ( v43 < 0 || v82[0] )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v70 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v70);
      }
    }
    else
    {
      operator delete(v99);
      String1 = 0;
      LODWORD(v99) = 0;
      v60 = CUsbDeviceEnumerator::CMGetDevNodeRegistryProperty(
              v44,
              dnDevInst,
              3u,
              (void **)&String1,
              (unsigned int *)&v99,
              v82) < 0;
      v46 = String1;
      v99 = String1;
      if ( !v60 )
      {
        v47 = 0;
        v48 = 0;
        if ( !v82[0] )
        {
          String1 = L"USB\\COMPOSITE";
          if ( IsAnyStringInMultiSzOnStringTable(v46, (const unsigned __int16 **const)&String1, 1u, v45) )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v49 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_33e1a90c76b132293387724df802fc6e_Traceguids, v49);
            }
            v48 = 1;
            v47 = 8;
          }
        }
        if ( v41 == 4 )
        {
          if ( !v48 )
            goto LABEL_169;
        }
        else if ( v41 <= 1 )
        {
LABEL_169:
          v5 = v85;
LABEL_170:
          v34 = v90;
          goto LABEL_171;
        }
        v50 = Size;
        v51 = Size + *((_DWORD *)v100 + v32) + 8;
        operator delete(lpInBuffer);
        v52 = operator new(v51);
        lpInBuffer = v52;
        if ( v52 )
        {
          v53 = (unsigned int *)v100;
          *v52 = 0;
          memcpy_0(v52 + 2, *((const void **)v106 + v94), v53[v94]);
          v54 = v50;
          v55 = *((unsigned int *)v100 + v94);
          v56 = Src;
          v57 = (char *)lpInBuffer;
          *((_DWORD *)lpInBuffer + 1) = v55;
          memcpy_0(&v57[v55 + 8], v56, v54);
          if ( DeviceIoControl(hDevice, 0x224408u, v57, v51, 0, 0, &BytesReturned, 0) )
            goto LABEL_168;
          v58 = GetLastError();
          v59 = 0;
          if ( v58 != 234 )
            v59 = v58;
          v60 = v59 < 0;
          if ( v59 > 0 )
            v60 = 1;
          if ( v60 )
          {
LABEL_168:
            v32 = v94;
            goto LABEL_169;
          }
          operator delete(v109);
          v109 = operator new(BytesReturned);
          if ( v109 )
          {
            v61 = v51;
            v8 = hDevice;
            if ( DeviceIoControl(hDevice, 0x224408u, v57, v61, v109, BytesReturned, &BytesReturned, 0) )
              goto LABEL_143;
            v62 = GetLastError();
            v4 = v62;
            if ( v62 > 0 )
              v4 = (unsigned __int16)v62 | 0x80070000;
            if ( v4 >= 0 )
            {
LABEL_143:
              if ( v41 == 4 )
                v47 |= 4u;
              v63 = v111;
              v64 = v104;
              if ( !(*(unsigned int (__fastcall **)(struct IDeviceCollection *, void *, _QWORD, __int64, int *))(*(_QWORD *)v111 + 56LL))(
                      v111,
                      v104,
                      v47,
                      4,
                      &v107)
                && !(*(unsigned int (__fastcall **)(struct IDeviceCollection *, void *, struct ILocalDevice **))(*(_QWORD *)v63 + 112LL))(
                      v63,
                      v64,
                      &v95) )
              {
                if ( v48 )
                {
                  v66 = CUsbDeviceEnumerator::QueryDeviceText(v65, v95, &hDevice, &v108, &v85);
                  if ( v66 >= 0 )
                  {
                    v5 = v85;
                    v68 = (*(__int64 (__fastcall **)(struct ILocalDevice *, char *, _QWORD))(*(_QWORD *)v95 + 272LL))(
                            v95,
                            (char *)v85 + 2,
                            2 * (unsigned int)*(unsigned __int16 *)v85);
                    if ( v68 < 0
                      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v69 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        48,
                        WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
                        v69,
                        v68);
                    }
                    goto LABEL_154;
                  }
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v67 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      47,
                      WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
                      v67,
                      v66);
                  }
                }
                v5 = v85;
LABEL_154:
                if ( v95 )
                {
                  TCntPtr<ITSViewerRecorder>::SafeRelease(&v95);
                  v95 = 0;
                  TCntPtr<IPin>::SafeAddRef(&v95);
                }
                if ( v5 )
                {
                  operator delete(v5);
                  v5 = 0;
                  v85 = 0;
                }
                v32 = v94;
                goto LABEL_170;
              }
              goto LABEL_168;
            }
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v77 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                46,
                (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
                v77,
                (__int64)"DeviceIoControl failed",
                v4);
            }
            LODWORD(v7) = v86;
            v5 = v85;
LABEL_205:
            v3 = DeviceInfoList;
            goto LABEL_183;
          }
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_211:
            v5 = v85;
            v4 = -2147024882;
            LODWORD(v7) = v86;
            goto LABEL_181;
          }
          v78 = RdpWppGetCurrentThreadActivityIdPrefix();
          v79 = 45;
          v80 = "IOCTL_TSUSB_FILTER_QUERY_CHILD_DEVICE_PROPRIETARY_ID_OUTPUT";
        }
        else
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_211;
          }
          v78 = RdpWppGetCurrentThreadActivityIdPrefix();
          v79 = 44;
          v80 = "IOCTL_TSUSB_FILTER_QUERY_CHILD_DEVICE_PROPRIETARY_ID_INPUT";
        }
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v79,
          (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
          v78,
          (__int64)v80);
        goto LABEL_211;
      }
    }
LABEL_171:
    LODWORD(v7) = v86;
    v33 = v98;
    if ( v5 )
    {
      operator delete(v5);
      v5 = 0;
      v85 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v81 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_33e1a90c76b132293387724df802fc6e_Traceguids,
      v81,
      (__int64)"WCHAR");
  }
  v4 = -2147024882;
LABEL_181:
  v3 = DeviceInfoList;
LABEL_182:
  v8 = hDevice;
LABEL_183:
  operator delete(Src);
  operator delete(lpInBuffer);
  operator delete(v109);
  operator delete(v104);
  operator delete(v6);
  operator delete(Block);
  operator delete(v99);
  operator delete(0);
  v74 = (void **)v106;
  if ( v106 )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)v7; j = (unsigned int)(j + 1) )
      operator delete(v74[j]);
    operator delete(v74);
  }
  operator delete(v100);
  operator delete(v98);
  if ( v3 != -1 )
    DevObjDestroyDeviceInfoList(v3);
  if ( v90 != -1 )
    DevObjDestroyDeviceInfoList(v90);
  if ( v8 != (HANDLE)-1LL )
    CloseHandle(v8);
  if ( v5 )
    operator delete(v5);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v95);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1805f0a00  mov     [rsp-8+arg_10], rbx
0x1805f0a05  push    rbp
0x1805f0a06  push    rsi
0x1805f0a07  push    rdi
0x1805f0a08  push    r12
0x1805f0a0a  push    r13
0x1805f0a0c  push    r14
0x1805f0a0e  push    r15
0x1805f0a10  lea     rbp, [rsp-70h]
0x1805f0a15  sub     rsp, 170h
0x1805f0a1c  mov     rax, cs:__security_cookie
0x1805f0a23  xor     rax, rsp
0x1805f0a26  mov     [rbp+0A0h+var_40], rax
0x1805f0a2a  xor     edi, edi
0x1805f0a2c  mov     [rbp+0A0h+var_98], rdx
0x1805f0a30  xorps   xmm1, xmm1
0x1805f0a33  mov     [rbp+0A0h+var_A0], rcx
0x1805f0a37  xorps   xmm0, xmm0
0x1805f0a3a  mov     [rsp+1A0h+hTemplateFile], rdi; hTemplateFile
0x1805f0a3f  or      r12, 0FFFFFFFFFFFFFFFFh
0x1805f0a43  mov     [rsp+1A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1805f0a4b  lea     r8d, [rdi+1]; dwShareMode
0x1805f0a4f  mov     [rbp+0A0h+var_120], edi
0x1805f0a52  xor     r9d, r9d; lpSecurityAttributes
0x1805f0a55  mov     [rsp+1A0h+var_130], edi
0x1805f0a59  mov     edx, 80000000h; dwDesiredAccess
0x1805f0a5e  mov     [rsp+1A0h+pulLen], edi
0x1805f0a62  lea     rcx, FileName; "\\\\.\\TerminalServicesUSBFilterDriverC"...
0x1805f0a69  mov     [rbp+0A0h+BytesReturned], edi
0x1805f0a6c  mov     ebx, edi
0x1805f0a6e  mov     [rsp+1A0h+var_148], rdi
0x1805f0a73  movups  [rbp+0A0h+var_90], xmm0
0x1805f0a77  mov     r14d, edi
0x1805f0a7a  mov     [rbp+0A0h+var_AC], edi
0x1805f0a7d  movups  [rbp+0A0h+var_80], xmm0
0x1805f0a81  mov     [rsp+1A0h+dnDevInst], edi
0x1805f0a85  mov     r13d, edi
0x1805f0a88  movups  [rbp+0A0h+var_70], xmm1
0x1805f0a8c  mov     [rbp+0A0h+pdnDevInst], edi
0x1805f0a8f  mov     r15d, edi
0x1805f0a92  movups  [rbp+0A0h+var_60], xmm1
0x1805f0a96  mov     [rbp+0A0h+var_B0], edi
0x1805f0a99  movups  [rbp+0A0h+var_50], xmm1
0x1805f0a9d  mov     [rbp+0A0h+var_108], rdi
0x1805f0aa1  mov     [rsp+1A0h+var_128], r12
0x1805f0aa6  mov     [rbp+0A0h+var_E8], rdi
0x1805f0aaa  mov     [rbp+0A0h+Src], rdi
0x1805f0aae  mov     [rbp+0A0h+Block], rdi
0x1805f0ab2  mov     [rbp+0A0h+lpInBuffer], rdi
0x1805f0ab6  mov     [rbp+0A0h+var_A8], rdi
0x1805f0aba  mov     [rbp+0A0h+var_C8], rdi
0x1805f0abe  mov     [rbp+0A0h+var_B8], rdi
0x1805f0ac2  mov     [rbp+0A0h+var_E0], rdi
0x1805f0ac6  mov     [rbp+0A0h+var_F0], rdi
0x1805f0aca  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x1805f0ad2  call    cs:__imp_CreateFileW
0x1805f0ad8  mov     [rsp+1A0h+hDevice], rax
0x1805f0add  mov     rsi, rax
0x1805f0ae0  cmp     rax, r12
0x1805f0ae3  jnz     short loc_1805F0B62
0x1805f0ae5  call    cs:__imp_GetLastError
0x1805f0aeb  mov     ebx, eax
0x1805f0aed  test    eax, eax
0x1805f0aef  jle     short loc_1805F0AFA
0x1805f0af1  movzx   ebx, ax
0x1805f0af4  or      ebx, 80070000h
0x1805f0afa  test    ebx, ebx
0x1805f0afc  jns     short loc_1805F0B62
0x1805f0afe  mov     rax, cs:WPP_GLOBAL_Control
0x1805f0b05  lea     rdi, WPP_GLOBAL_Control
0x1805f0b0c  cmp     rax, rdi
0x1805f0b0f  jz      loc_1805F17D5
0x1805f0b15  test    byte ptr [rax+1Ch], 8
0x1805f0b19  jz      loc_1805F17D5
0x1805f0b1f  cmp     byte ptr [rax+19h], 2
0x1805f0b23  jb      loc_1805F17D5
0x1805f0b29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f0b2e  mov     edx, 1Fh
0x1805f0b33  lea     rcx, aCreatefileFail; "CreateFile failed"
0x1805f0b3a  mov     [rsp+1A0h+dwFlagsAndAttributes], ebx
0x1805f0b3e  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f0b45  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rcx
0x1805f0b4a  mov     r9d, eax
0x1805f0b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f0b54  mov     rcx, [rcx+10h]
0x1805f0b58  call    WPP_SF_DsD
0x1805f0b5d  jmp     loc_1805F17D5
0x1805f0b62  xor     r9d, r9d
0x1805f0b65  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rdi
0x1805f0b6a  xor     r8d, r8d
0x1805f0b6d  xor     edx, edx
0x1805f0b6f  xor     ecx, ecx
0x1805f0b71  call    cs:__imp_DevObjCreateDeviceInfoList
0x1805f0b77  mov     [rsp+1A0h+var_138], rax
0x1805f0b7c  mov     r12, rax
0x1805f0b7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805f0b83  jnz     short loc_1805F0BDF
0x1805f0b85  call    cs:__imp_GetLastError
0x1805f0b8b  mov     ebx, eax
0x1805f0b8d  test    eax, eax
0x1805f0b8f  jle     short loc_1805F0B9A
0x1805f0b91  movzx   ebx, ax
0x1805f0b94  or      ebx, 80070000h
0x1805f0b9a  test    ebx, ebx
0x1805f0b9c  jns     short loc_1805F0BDF
0x1805f0b9e  mov     rax, cs:WPP_GLOBAL_Control
0x1805f0ba5  lea     rdi, WPP_GLOBAL_Control
0x1805f0bac  cmp     rax, rdi
0x1805f0baf  jz      loc_1805F17D5
0x1805f0bb5  test    byte ptr [rax+1Ch], 8
0x1805f0bb9  jz      loc_1805F17D5
0x1805f0bbf  cmp     byte ptr [rax+19h], 2
0x1805f0bc3  jb      loc_1805F17D5
0x1805f0bc9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f0bce  mov     edx, 20h ; ' '
0x1805f0bd3  lea     rcx, aDevobjcreatede; "DevObjCreateDeviceInfoList FAILED"
0x1805f0bda  jmp     loc_1805F0B3A
0x1805f0bdf  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], rdi
0x1805f0be4  lea     rdx, GUID_DEVINTERFACE_TSUSBBUS_FILTER
0x1805f0beb  mov     r9d, 12h
0x1805f0bf1  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rdi
0x1805f0bf6  xor     r8d, r8d
0x1805f0bf9  mov     rcx, r12
0x1805f0bfc  call    cs:__imp_DevObjGetClassDevs
0x1805f0c02  test    eax, eax
0x1805f0c04  jnz     short loc_1805F0C60
0x1805f0c06  call    cs:__imp_GetLastError
0x1805f0c0c  mov     ebx, eax
0x1805f0c0e  test    eax, eax
0x1805f0c10  jle     short loc_1805F0C1B
0x1805f0c12  movzx   ebx, ax
0x1805f0c15  or      ebx, 80070000h
0x1805f0c1b  test    ebx, ebx
0x1805f0c1d  jns     short loc_1805F0C60
0x1805f0c1f  mov     rax, cs:WPP_GLOBAL_Control
0x1805f0c26  lea     rdi, WPP_GLOBAL_Control
0x1805f0c2d  cmp     rax, rdi
0x1805f0c30  jz      loc_1805F17D5
0x1805f0c36  test    byte ptr [rax+1Ch], 8
0x1805f0c3a  jz      loc_1805F17D5
0x1805f0c40  cmp     byte ptr [rax+19h], 2
0x1805f0c44  jb      loc_1805F17D5
0x1805f0c4a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f0c4f  mov     edx, 21h ; '!'
0x1805f0c54  lea     rcx, aDevobjgetclass; "DevObjGetClassDevs failed"
0x1805f0c5b  jmp     loc_1805F0B3A
0x1805f0c60  lea     rax, [rbp+0A0h+var_90]
0x1805f0c64  mov     dword ptr [rbp+0A0h+var_90], 20h ; ' '
0x1805f0c6b  mov     r9d, edi
0x1805f0c6e  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x1805f0c73  lea     r8, GUID_DEVINTERFACE_TSUSBBUS_FILTER
0x1805f0c7a  xor     edx, edx
0x1805f0c7c  mov     rcx, r12
0x1805f0c7f  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1805f0c85  lea     r15d, [rdi+1]
0x1805f0c89  test    eax, eax
0x1805f0c8b  cmovz   r15d, edi
0x1805f0c8f  mov     [rsp+1A0h+var_140], r15d
0x1805f0c94  mov     edi, r15d
0x1805f0c97  jnz     short loc_1805F0C60
0x1805f0c99  test    r15d, r15d
0x1805f0c9c  jnz     short loc_1805F0CA8
0x1805f0c9e  mov     ebx, 80070490h
0x1805f0ca3  jmp     loc_1805F17D5
0x1805f0ca8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1805f0caf  mov     edi, r15d
0x1805f0cb2  mov     eax, 4
0x1805f0cb7  mul     rdi
0x1805f0cba  cmovb   rax, rcx
0x1805f0cbe  mov     rcx, rax; Size
0x1805f0cc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805f0cc6  mov     [rbp+0A0h+var_F0], rax
0x1805f0cca  test    rax, rax
0x1805f0ccd  jnz     short loc_1805F0D28
0x1805f0ccf  mov     rax, cs:WPP_GLOBAL_Control
0x1805f0cd6  lea     rdi, WPP_GLOBAL_Control
0x1805f0cdd  cmp     rax, rdi
0x1805f0ce0  jz      short loc_1805F0D1E
0x1805f0ce2  test    byte ptr [rax+1Ch], 8
0x1805f0ce6  jz      short loc_1805F0D1E
0x1805f0ce8  cmp     byte ptr [rax+19h], 2
0x1805f0cec  jb      short loc_1805F0D1E
0x1805f0cee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f0cf3  lea     rcx, aDevinst; "DEVINST"
0x1805f0cfa  mov     edx, 22h ; '"'
0x1805f0cff  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rcx
0x1805f0d04  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f0d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f0d12  mov     r9d, eax
0x1805f0d15  mov     rcx, [rcx+10h]
0x1805f0d19  call    WPP_SF_Ds
0x1805f0d1e  mov     ebx, 8007000Eh
0x1805f0d23  jmp     loc_1805F17D5
0x1805f0d28  lea     rsi, ds:0[r15*4]
0x1805f0d30  xor     edx, edx; Val
0x1805f0d32  mov     r8, rsi; Size
0x1805f0d35  mov     rcx, rax; void *
0x1805f0d38  call    memset_0
0x1805f0d3d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1805f0d44  mov     eax, 8
0x1805f0d49  mul     rdi
0x1805f0d4c  cmovb   rax, rcx
0x1805f0d50  mov     rcx, rax; Size
0x1805f0d53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805f0d58  mov     [rbp+0A0h+var_B8], rax
0x1805f0d5c  test    rax, rax
0x1805f0d5f  jnz     short loc_1805F0DBA
0x1805f0d61  mov     rax, cs:WPP_GLOBAL_Control
0x1805f0d68  lea     rdi, WPP_GLOBAL_Control
0x1805f0d6f  cmp     rax, rdi
0x1805f0d72  jz      short loc_1805F0DB0
0x1805f0d74  test    byte ptr [rax+1Ch], 8
0x1805f0d78  jz      short loc_1805F0DB0
0x1805f0d7a  cmp     byte ptr [rax+19h], 2
0x1805f0d7e  jb      short loc_1805F0DB0
0x1805f0d80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f0d85  mov     edx, 23h ; '#'
0x1805f0d8a  lea     rcx, aPwstr; "PWSTR"
0x1805f0d91  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rcx
0x1805f0d96  lea     r8, WPP_33e1a90c76b132293387724df802fc6e_Traceguids
0x1805f0d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1805f0da4  mov     r9d, eax
0x1805f0da7  mov     rcx, [rcx+10h]
0x1805f0dab  call    WPP_SF_Ds
0x1805f0db0  mov     ebx, 8007000Eh
0x1805f0db5  jmp     loc_1805F17D0
0x1805f0dba  lea     r8, ds:0[r15*8]; Size
0x1805f0dc2  xor     edx, edx; Val
0x1805f0dc4  mov     rcx, rax; void *
0x1805f0dc7  call    memset_0
0x1805f0dcc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1805f0dd3  mov     eax, 4
0x1805f0dd8  mul     rdi
0x1805f0ddb  cmovb   rax, rcx
0x1805f0ddf  mov     rcx, rax; Size
0x1805f0de2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805f0de7  mov     [rbp+0A0h+var_E0], rax
0x1805f0deb  test    rax, rax
0x1805f0dee  jnz     short loc_1805F0E25
0x1805f0df0  mov     rax, cs:WPP_GLOBAL_Control
0x1805f0df7  lea     rdi, WPP_GLOBAL_Control
0x1805f0dfe  cmp     rax, rdi
0x1805f0e01  jz      short loc_1805F0DB0
0x1805f0e03  test    byte ptr [rax+1Ch], 8
0x1805f0e07  jz      short loc_1805F0DB0
0x1805f0e09  cmp     byte ptr [rax+19h], 2
0x1805f0e0d  jb      short loc_1805F0DB0
0x1805f0e0f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805f0e14  mov     edx, 24h ; '$'
0x1805f0e19  lea     rcx, aDevinst; "DEVINST"
0x1805f0e20  jmp     loc_1805F0D91
0x1805f0e25  mov     r8, rsi; Size
0x1805f0e28  xor     edx, edx; Val
0x1805f0e2a  mov     rcx, rax; void *
0x1805f0e2d  call    memset_0
0x1805f0e32  xor     edi, edi
0x1805f0e34  cmp     edi, r15d
0x1805f0e37  jnb     loc_1805F1129
0x1805f0e3d  lea     rax, [rbp+0A0h+var_90]
0x1805f0e41  mov     dword ptr [rbp+0A0h+var_90], 20h ; ' '
0x1805f0e48  mov     r9d, edi
0x1805f0e4b  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x1805f0e50  lea     r8, GUID_DEVINTERFACE_TSUSBBUS_FILTER
0x1805f0e57  xor     edx, edx
0x1805f0e59  mov     rcx, r12
0x1805f0e5c  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1805f0e62  test    eax, eax
0x1805f0e64  jz      loc_1805F1042
0x1805f0e6a  lea     rax, [rbp+0A0h+var_70]
0x1805f0e6e  mov     dword ptr [rbp+0A0h+var_70], 30h ; '0'
0x1805f0e75  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], rax
0x1805f0e7a  lea     rdx, [rbp+0A0h+var_90]
0x1805f0e7e  xor     r9d, r9d
0x1805f0e81  mov     qword ptr [rsp+1A0h+dwCreationDisposition], r14
0x1805f0e86  xor     r8d, r8d
0x1805f0e89  mov     rcx, r12
0x1805f0e8c  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1805f0e92  test    eax, eax
0x1805f0e94  jnz     loc_1805F10A8
0x1805f0e9a  call    cs:__imp_GetLastError
0x1805f0ea0  mov     ebx, eax
0x1805f0ea2  cmp     eax, 7Ah ; 'z'
0x1805f0ea5  jz      short loc_1805F0EBC
0x1805f0ea7  test    eax, eax
0x1805f0ea9  jle     short loc_1805F0EB4
0x1805f0eab  movzx   ebx, ax
0x1805f0eae  or      ebx, 80070000h
0x1805f0eb4  test    ebx, ebx
0x1805f0eb6  js      loc_1805F10AD
0x1805f0ebc  lea     rax, [rbp+0A0h+var_120]
0x1805f0ec0  xor     r9d, r9d
0x1805f0ec3  xor     r8d, r8d
0x1805f0ec6  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x1805f0ecb  lea     rdx, [rbp+0A0h+var_70]
0x1805f0ecf  mov     rcx, r12
0x1805f0ed2  call    cs:__imp_DevObjGetDeviceInstanceId
0x1805f0ed8  test    eax, eax
0x1805f0eda  jnz     loc_1805F10A8
0x1805f0ee0  call    cs:__imp_GetLastError
0x1805f0ee6  mov     ebx, eax
  ... truncated ...
```
