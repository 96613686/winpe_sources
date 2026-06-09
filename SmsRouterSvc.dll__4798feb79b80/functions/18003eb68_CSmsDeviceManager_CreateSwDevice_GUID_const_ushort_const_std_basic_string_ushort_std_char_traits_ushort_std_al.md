# CSmsDeviceManager::CreateSwDevice(_GUID const &,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,_WNF_STATE_NAME *,HSWDEVICE__ * *)

- ea: `0x18003eb68`
- end: `0x18003f546`
- name: `?CreateSwDevice@CSmsDeviceManager@@AEAAJAEBU_GUID@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_WNF_STATE_NAME@@PEAPEAUHSWDEVICE__@@@Z`
- size: `2526`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004099c`

## callees

- `0x180003a60`
- `0x180003f50`
- `0x180003f8c`
- `0x18000498c`
- `0x180004998`
- `0x18000659c`
- `0x1800069f0`
- `0x1800093d4`
- `0x18000d388`
- `0x1800267f8`
- `0x1800276a4`
- `0x18003eb68`
- `0x180051420`
- `0x180051628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ed8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ed8a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003eff2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003eff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f4e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f4e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f1be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f1be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f065`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f40f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f065`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f40f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f4ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f4ef`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003ec8c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003ec8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f513`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f513`
- `ntdll!NtDeleteWnfStateName` at `0x18003f4ad`
- `ntdll!NtDeleteWnfStateName` at `0x18003f4ad`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x18003f09e`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x18003f09e`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18003ef91`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18003ef91`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18003f0d7`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18003f0d7`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18003f4cd`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18003f4cd`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18003f4bd`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18003f4bd`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003ed02`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18003ed02`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18003f39b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18003f39b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18003f30c`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18003f30c`

## string_xrefs

- `0x18003ed33`: `RegCreateKey Key: %S`
- `0x18003ed6d`: `CreateWNFStateName`
- `0x18003eca8`: `CSmsDeviceManager::CreateSwDevice`
- `0x18003efd7`: `CSmsDeviceManager::CreateSwDevice`
- `0x18003f08b`: `CSmsDeviceManager::CreateSwDevice`
- `0x18003f17c`: `CSmsDeviceManager::CreateSwDevice`
- `0x18003f3cf`: `CSmsDeviceManager::CreateSwDevice`
- `0x18003f435`: `CSmsDeviceManager::CreateSwDevice`
- `0x18003f487`: `CSmsDeviceManager::CreateSwDevice`
- `0x18003edb5`: `CreateEvent`
- `0x18003f07c`: `RegSetValueEx for %S`
- `0x18003f426`: `RegSetValueEx for %S`
- `0x18003efb2`: `SwDeviceCreate: InstanceID: %S, ParentId: %S`
- `0x18003f01c`: `SwDeviceCreate.ctx.CreateResult: InstanceID: %S, ParentId: %S`
- `0x18003f005`: `SwDeviceCreate.WaitForSingleObject: InstanceID: %S, ParentId: %S`
- `0x18003f170`: `SwDeviceCreate failed as device already exists. Ignoring the error.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSmsDeviceManager::CreateSwDevice(
        __int64 a1,
        const GUID *a2,
        __int64 a3,
        char *a4,
        __int64 *a5,
        __int64 *a6)
{
  _QWORD *v9; // rbx
  HKEY v10; // rdi
  int v11; // eax
  signed int Objects; // r14d
  char *v13; // r9
  unsigned int v14; // edx
  const WCHAR *v15; // rdx
  LSTATUS v16; // eax
  LPCWSTR *v17; // rax
  HANDLE EventW; // r14
  signed int LastError; // eax
  unsigned int v20; // edx
  unsigned __int64 v21; // rsi
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r12
  __int64 v25; // rdx
  const wchar_t *v26; // r8
  __int64 v27; // rax
  wchar_t *v28; // rcx
  wchar_t v29; // r9
  int v30; // eax
  char *v31; // r9
  unsigned int v32; // edx
  __int64 v33; // rax
  int v34; // eax
  int v35; // eax
  __int64 v36; // r8
  void *v37; // r9
  char *v38; // r12
  size_t v39; // rsi
  char *v40; // r9
  unsigned __int16 *v41; // rdx
  __int64 v42; // rax
  unsigned __int16 *v43; // rcx
  unsigned __int16 v44; // r8
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // r8
  _WORD *v48; // r9
  char *v49; // r12
  size_t v50; // rsi
  char *v51; // r9
  DWORD cbData; // eax
  int v53; // eax
  unsigned int v55; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+48h] [rbp-B8h]
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hHandle; // [rsp+78h] [rbp-88h]
  HKEY v63; // [rsp+80h] [rbp-80h]
  _QWORD *v64; // [rsp+88h] [rbp-78h]
  __int64 *v65; // [rsp+90h] [rbp-70h]
  __int64 *v66; // [rsp+98h] [rbp-68h]
  __int64 v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v69; // [rsp+B8h] [rbp-48h]
  _BYTE *v70; // [rsp+C0h] [rbp-40h]
  const wchar_t *v71; // [rsp+C8h] [rbp-38h]
  int v72; // [rsp+D8h] [rbp-28h]
  const wchar_t *v73; // [rsp+E0h] [rbp-20h]
  _QWORD v74[2]; // [rsp+100h] [rbp+0h] BYREF
  int v75; // [rsp+110h] [rbp+10h]
  _WORD Data[262]; // [rsp+114h] [rbp+14h] BYREF
  __int64 v77; // [rsp+320h] [rbp+220h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+328h] [rbp+228h] BYREF
  __int64 v79; // [rsp+338h] [rbp+238h]
  unsigned __int64 v80; // [rsp+340h] [rbp+240h]
  int v81; // [rsp+350h] [rbp+250h] BYREF
  DEVPROPKEY v82; // [rsp+358h] [rbp+258h]
  int v83; // [rsp+36Ch] [rbp+26Ch]
  __int64 v84; // [rsp+370h] [rbp+270h]
  int v85; // [rsp+378h] [rbp+278h]
  int v86; // [rsp+37Ch] [rbp+27Ch]
  _WORD *v87; // [rsp+380h] [rbp+280h]
  int v88; // [rsp+388h] [rbp+288h]
  DEVPROPKEY v89; // [rsp+390h] [rbp+290h]
  int v90; // [rsp+3A4h] [rbp+2A4h]
  __int64 v91; // [rsp+3A8h] [rbp+2A8h]
  int v92; // [rsp+3B0h] [rbp+2B0h]
  int v93; // [rsp+3B4h] [rbp+2B4h]
  __int64 *v94; // [rsp+3B8h] [rbp+2B8h]
  OLECHAR sz[40]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v96[64]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v97[112]; // [rsp+490h] [rbp+390h] BYREF

  v56 = a3;
  v66 = a5;
  v65 = a6;
  hHandle = 0;
  memset_0(v74, 0, 0x220u);
  memset_0(&v68, 0, 0x48u);
  memset_0(v97, 0, 0x64u);
  memset_0(v96, 0, sizeof(v96));
  v57 = 0;
  v67 = 0;
  memset_0(sz, 0, sizeof(sz));
  v9 = 0;
  v64 = 0;
  Src = 0;
  *(_OWORD *)lpSubKey = 0;
  v79 = 0;
  v80 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)lpSubKey, L"Devices", 7u);
  v10 = 0;
  v63 = 0;
  v77 = 0;
  phkResult = 0;
  pcbData = 0;
  v11 = StringFromGUID2(a2, sz, 40);
  Objects = v11;
  if ( v11 < 0 )
  {
    v13 = "StringFromGUID2";
    v14 = 896;
LABEL_3:
    LogSmsRouterError("CSmsDeviceManager::CreateSwDevice", v14, v11, v13);
    goto LABEL_102;
  }
  std::wstring::append(lpSubKey, (void *)L"\\");
  std::wstring::append(lpSubKey, sz);
  v15 = (const WCHAR *)lpSubKey;
  if ( v80 > 7 )
    v15 = lpSubKey[0];
  v16 = RegCreateKeyW(g_SmsRouterKey, v15, &phkResult);
  Objects = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      Objects = (unsigned __int16)v16 | 0x80070000;
    v17 = lpSubKey;
    if ( v80 > 7 )
      v17 = (LPCWSTR *)lpSubKey[0];
    LogSmsRouterError("CSmsDeviceManager::CreateSwDevice", 0x38Bu, Objects, "RegCreateKey Key: %S", v17);
    goto LABEL_102;
  }
  v10 = phkResult;
  v63 = phkResult;
  phkResult = 0;
  v11 = CSmsRpcUtils::CreateWNFStateName(&v77, 0, 176);
  Objects = v11;
  if ( v11 < 0 )
  {
    v13 = "CreateWNFStateName";
    v14 = 917;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  hHandle = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    Objects = LastError;
    if ( LastError > 0 )
      Objects = (unsigned __int16)LastError | 0x80070000;
    LogSmsRouterError("CSmsDeviceManager::CreateSwDevice", 0x3A4u, Objects, "CreateEvent");
    goto LABEL_102;
  }
  v55 = 2;
  v9 = operator new[](0xF0u);
  v64 = v9;
  v20 = 0;
  v21 = -1;
  do
  {
    v22 = 6LL * v20;
    *(_OWORD *)&v9[v22] = *(_OWORD *)&qword_18008C2A0[6 * v20];
    *(_OWORD *)&v9[v22 + 2] = *(_OWORD *)&qword_18008C2A0[6 * v20 + 2];
    *(_OWORD *)&v9[v22 + 4] = *(_OWORD *)&qword_18008C2A0[6 * v20 + 4];
    if ( LODWORD(v9[6 * v20 + 2]) == 1 )
    {
      if ( v9[6 * v20] == DEVPKEY_SmsDevice_NetworkInterfaceId && v9[6 * v20 + 1] == 0xA062340C8EE6408FuLL )
      {
        v9[6 * v20 + 5] = sz;
        v23 = -1;
        do
          ++v23;
        while ( sz[v23] );
        HIDWORD(v9[6 * v20 + 4]) = 2 * v23 + 2;
      }
    }
    else if ( LODWORD(v9[6 * v20 + 2]) == 2
           && v9[6 * v20] == DEVPKEY_SmsDevice_DeviceStateWnf
           && v9[6 * v20 + 1] == 0xA062340C8EE6408FuLL )
    {
      v9[6 * v20 + 5] = &v77;
      HIDWORD(v9[6 * v20 + 4]) = 8;
    }
    ++v20;
  }
  while ( (int)v20 < 5 );
  v24 = 2147483646;
  v25 = 2147483646;
  v26 = L"SmsDevice2\\0";
  v27 = 50;
  v28 = (wchar_t *)v97;
  while ( v25 )
  {
    v29 = *v26;
    if ( *v26 )
    {
      ++v26;
      *v28++ = v29;
      --v25;
      if ( --v27 )
        continue;
    }
    if ( !v27 )
      --v28;
    break;
  }
  *v28 = 0;
  StringCchPrintfW(v96, 0x40u, L"SMS_DEVICE2_%s", sz);
  v74[0] = EventW;
  v75 = -2147467259;
  v68 = 72;
  v69 = v96;
  v70 = v97;
  v71 = L"SWD\\SMSDEVICE\\SmsDevice2\\0";
  v72 = 6;
  v73 = L"Windows.Devices.Sms.SmsDevice2";
  v30 = SwDeviceCreate(L"SMSDEVICE", a3, &v68, 5, v9, SwDeviceCallback, v74, &v57);
  Objects = v30;
  if ( v30 == -2147024713 )
  {
    LogSmsRouterInfo(
      "CSmsDeviceManager::CreateSwDevice",
      0x408u,
      "SwDeviceCreate failed as device already exists. Ignoring the error.");
    pcbData = 520;
    if ( RegGetValueW(v10, 0, L"DeviceId", 2u, 0, Data, &pcbData) )
    {
      v41 = v96;
      v42 = 260;
      v43 = Data;
      while ( v24 )
      {
        v44 = *v41;
        if ( *v41 )
        {
          ++v41;
          *v43++ = v44;
          --v24;
          if ( --v42 )
            continue;
        }
        v24 = 0;
        if ( !v42 )
          --v43;
        break;
      }
      *v43 = v24;
      v45 = 10;
      goto LABEL_75;
    }
    v24 = 0;
  }
  else
  {
    v24 = 0;
    if ( v30 < 0 )
    {
      v31 = "SwDeviceCreate: InstanceID: %S, ParentId: %S";
      v32 = 982;
LABEL_39:
      LogSmsRouterError("CSmsDeviceManager::CreateSwDevice", v32, Objects, v31, v96, v56);
      goto LABEL_102;
    }
    if ( WaitForSingleObject(hHandle, 0x493E0u) )
    {
      Objects = -2147467259;
      LogSmsRouterError(
        "CSmsDeviceManager::CreateSwDevice",
        0x3DFu,
        -2147467259,
        "SwDeviceCreate.WaitForSingleObject: InstanceID: %S, ParentId: %S",
        v96,
        v56);
      goto LABEL_102;
    }
    Objects = v75;
    if ( v75 < 0 )
    {
      v31 = "SwDeviceCreate.ctx.CreateResult: InstanceID: %S, ParentId: %S";
      v32 = 999;
      goto LABEL_39;
    }
    v33 = -1;
    do
      ++v33;
    while ( Data[v33] );
    v34 = RegSetValueExW(v10, L"DeviceId", 0, 1u, (const BYTE *)Data, 2 * v33 + 2);
    if ( v34 )
    {
      if ( v34 > 0 )
        v34 = (unsigned __int16)v34 | 0x80070000;
      LogSmsRouterError("CSmsDeviceManager::CreateSwDevice", 0x3F4u, v34, "RegSetValueEx for %S", L"DeviceId");
    }
    SwDeviceSetLifetime(v57, 0);
    v35 = SwDeviceInterfaceRegister(v57, qword_1800786D8, 0, 1, qword_18008C390, 1, &Src);
    Objects = v35;
    if ( v35 >= 0 )
    {
      v37 = Src;
      do
        ++v21;
      while ( *((_WORD *)Src + v21) );
      if ( v21 > *((_QWORD *)a4 + 3) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)a4,
          v21,
          v36,
          Src);
      }
      else
      {
        if ( *((_QWORD *)a4 + 3) <= 7u )
          v38 = a4;
        else
          v38 = *(char **)a4;
        *((_QWORD *)a4 + 2) = v21;
        v39 = 2 * v21;
        memmove_0(v38, v37, v39);
        *(_WORD *)&v38[v39] = 0;
        v24 = 0;
      }
      if ( *((_QWORD *)a4 + 3) <= 7u )
        v40 = a4;
      else
        v40 = *(char **)a4;
      LogSmsRouterInfo(
        "CSmsDeviceManager::CreateSwDevice",
        0x445u,
        "SwDeviceInterfaceRegister: InterfaceId: %S, DeviceId: %S, ParentId: %S",
        v40,
        Data,
        v56);
      goto LABEL_93;
    }
    if ( v35 != -2147024844 )
    {
      v31 = "SwDeviceInterfaceRegister: InstanceID: %S, ParentId: %S";
      v32 = 1025;
      goto LABEL_39;
    }
  }
  v45 = v55;
LABEL_75:
  v55 = v24;
  v60 = v24;
  v46 = -1;
  do
    ++v46;
  while ( Data[v46] != (_WORD)v24 );
  v81 = v45;
  v82 = DEVPKEY_Device_InstanceId;
  v83 = v24;
  v84 = v24;
  v85 = 18;
  v86 = 2 * v46 + 2;
  v87 = Data;
  v88 = 2;
  v89 = DEVPKEY_DeviceInterface_ClassGuid;
  v90 = v24;
  v91 = v24;
  v92 = 13;
  v93 = 16;
  v94 = qword_1800786D8;
  Objects = DevGetObjects(1, 0, 0, 0, 2, &v81, &v55, &v60);
  if ( Objects < 0 )
  {
    LogSmsRouterError(
      "CSmsDeviceManager::CreateSwDevice",
      0x42Cu,
      Objects,
      "DevGetObjects(Interfaces) failed DeviceId: %S",
      Data);
    goto LABEL_102;
  }
  if ( !v60 || v55 == (_DWORD)v24 )
  {
    Objects = -2147418113;
    LogSmsRouterError(
      "CSmsDeviceManager::CreateSwDevice",
      0x432u,
      -2147418113,
      "DevGetObjects(Interfaces) none DeviceId: %S",
      Data);
LABEL_102:
    if ( v77 )
      NtDeleteWnfStateName(&v77);
    goto LABEL_104;
  }
  v48 = *(_WORD **)(v60 + 8);
  do
    ++v21;
  while ( v48[v21] != (_WORD)v24 );
  if ( v21 > *((_QWORD *)a4 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a4,
      v21,
      v47,
      v48);
  }
  else
  {
    if ( *((_QWORD *)a4 + 3) <= 7u )
      v49 = a4;
    else
      v49 = *(char **)a4;
    *((_QWORD *)a4 + 2) = v21;
    v50 = 2 * v21;
    memmove_0(v49, v48, v50);
    *(_WORD *)&v49[v50] = 0;
    v24 = 0;
  }
  DevFreeObjects(v55, v60);
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v51 = a4;
  else
    v51 = *(char **)a4;
  LogSmsRouterInfo(
    "CSmsDeviceManager::CreateSwDevice",
    0x43Au,
    "SwDeviceInterfaceRegister(dup): InterfaceId: %S, DeviceId: %S, ParentId: %S",
    v51,
    Data,
    v56);
LABEL_93:
  cbData = 2 * *((_DWORD *)a4 + 4) + 2;
  if ( *((_QWORD *)a4 + 3) > 7u )
    a4 = *(char **)a4;
  v53 = RegSetValueExW(v10, L"DeviceInterfaceId", 0, 1u, (const BYTE *)a4, cbData);
  if ( v53 )
  {
    if ( v53 > 0 )
      v53 = (unsigned __int16)v53 | 0x80070000;
    LogSmsRouterError("CSmsDeviceManager::CreateSwDevice", 0x456u, v53, "RegSetValueEx for %S", L"DeviceInterfaceId");
  }
  *v65 = v57;
  v57 = v24;
  *v66 = v77;
  v77 = v24;
LABEL_104:
  if ( Src )
    SwMemFree();
  if ( v57 )
    SwDeviceClose();
  if ( hHandle )
    CloseHandle(hHandle);
  if ( v10 )
    RegCloseKey(v10);
  std::wstring::~wstring((char **)lpSubKey);
  if ( v9 )
    operator delete(v9);
  SysFreeString(0);
  return (unsigned int)Objects;
}

```

## disassembly

```asm
0x18003eb68  mov     [rsp-8+arg_0], rbx
0x18003eb6d  push    rbp
0x18003eb6e  push    rsi
0x18003eb6f  push    rdi
0x18003eb70  push    r12
0x18003eb72  push    r13
0x18003eb74  push    r14
0x18003eb76  push    r15
0x18003eb78  lea     rbp, [rsp-410h]
0x18003eb80  sub     rsp, 510h
0x18003eb87  mov     rax, cs:__security_cookie
0x18003eb8e  xor     rax, rsp
0x18003eb91  mov     [rbp+440h+var_40], rax
0x18003eb98  mov     r15, r9
0x18003eb9b  mov     r13, r8
0x18003eb9e  mov     [rsp+540h+var_4F8], r8
0x18003eba3  mov     rsi, rdx
0x18003eba6  mov     rax, [rbp+440h+arg_20]
0x18003ebad  mov     [rbp+440h+var_4A8], rax
0x18003ebb1  mov     rax, [rbp+440h+arg_28]
0x18003ebb8  mov     [rbp+440h+var_4B0], rax
0x18003ebbc  xor     r12d, r12d
0x18003ebbf  mov     [rsp+540h+hHandle], r12
0x18003ebc4  xor     edx, edx; Val
0x18003ebc6  mov     r8d, 220h; Size
0x18003ebcc  lea     rcx, [rbp+440h+var_440]; void *
0x18003ebd0  call    memset_0
0x18003ebd5  xor     edx, edx; Val
0x18003ebd7  lea     r8d, [r12+48h]; Size
0x18003ebdc  lea     rcx, [rbp+440h+var_490]; void *
0x18003ebe0  call    memset_0
0x18003ebe5  xor     edx, edx; Val
0x18003ebe7  lea     r8d, [r12+64h]; Size
0x18003ebec  lea     rcx, [rbp+440h+var_B0]; void *
0x18003ebf3  call    memset_0
0x18003ebf8  xor     edx, edx; Val
0x18003ebfa  mov     r8d, 80h; Size
0x18003ec00  lea     rcx, [rbp+440h+var_130]; void *
0x18003ec07  call    memset_0
0x18003ec0c  mov     [rsp+540h+var_4F0], r12
0x18003ec11  mov     [rbp+440h+var_4A0], r12
0x18003ec15  xor     edx, edx; Val
0x18003ec17  lea     r8d, [r12+50h]; Size
0x18003ec1c  lea     rcx, [rbp+440h+sz]; void *
0x18003ec23  call    memset_0
0x18003ec28  mov     ebx, r12d
0x18003ec2b  mov     [rbp+440h+var_4B8], rbx
0x18003ec2f  mov     [rsp+540h+Src], r12
0x18003ec34  xorps   xmm0, xmm0
0x18003ec37  movups  xmmword ptr [rbp+440h+lpSubKey], xmm0
0x18003ec3e  mov     [rbp+440h+var_208], r12
0x18003ec45  mov     [rbp+440h+var_200], r12
0x18003ec4c  lea     r8d, [r12+7]
0x18003ec51  lea     rdx, aDevices; "Devices"
0x18003ec58  lea     rcx, [rbp+440h+lpSubKey]
0x18003ec5f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003ec64  nop
0x18003ec65  mov     edi, r12d
0x18003ec68  mov     [rbp+440h+var_4C0], r12
0x18003ec6c  mov     [rbp+440h+var_220], r12
0x18003ec73  mov     [rsp+540h+phkResult], r12
0x18003ec78  mov     [rsp+540h+var_4E8], r12d
0x18003ec7d  lea     r8d, [r12+28h]; cchMax
0x18003ec82  lea     rdx, [rbp+440h+sz]; lpsz
0x18003ec89  mov     rcx, rsi; rguid
0x18003ec8c  call    cs:__imp_StringFromGUID2
0x18003ec92  mov     r14d, eax
0x18003ec95  test    eax, eax
0x18003ec97  jns     short loc_18003ECB9
0x18003ec99  lea     r9, aStringfromguid_0; "StringFromGUID2"
0x18003eca0  mov     edx, 380h; unsigned int
0x18003eca5  mov     r8d, eax; int
0x18003eca8  lea     rcx, aCsmsdevicemana_3; "CSmsDeviceManager::CreateSwDevice"
0x18003ecaf  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003ecb4  jmp     loc_18003F493
0x18003ecb9  lea     rdx, StringValue; "\\"
0x18003ecc0  lea     rcx, [rbp+440h+lpSubKey]; Src
0x18003ecc7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003eccc  lea     rdx, [rbp+440h+sz]; void *
0x18003ecd3  lea     rcx, [rbp+440h+lpSubKey]; Src
0x18003ecda  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003ecdf  lea     rdx, [rbp+440h+lpSubKey]
0x18003ece6  cmp     [rbp+440h+var_200], 7
0x18003ecee  cmova   rdx, [rbp+440h+lpSubKey]; lpSubKey
0x18003ecf6  lea     r8, [rsp+540h+phkResult]; phkResult
0x18003ecfb  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18003ed02  call    cs:__imp_RegCreateKeyW
0x18003ed08  mov     r14d, eax
0x18003ed0b  test    eax, eax
0x18003ed0d  jz      short loc_18003ED44
0x18003ed0f  jle     short loc_18003ED1C
0x18003ed11  movzx   r14d, ax
0x18003ed15  or      r14d, 80070000h
0x18003ed1c  lea     rax, [rbp+440h+lpSubKey]
0x18003ed23  cmp     [rbp+440h+var_200], 7
0x18003ed2b  cmova   rax, [rbp+440h+lpSubKey]
0x18003ed33  lea     r9, aRegcreatekeyKe; "RegCreateKey Key: %S"
0x18003ed3a  mov     edx, 38Bh
0x18003ed3f  jmp     loc_18003F47F
0x18003ed44  mov     rdi, [rsp+540h+phkResult]
0x18003ed49  mov     [rbp+440h+var_4C0], rdi
0x18003ed4d  mov     [rsp+540h+phkResult], r12
0x18003ed52  xor     edx, edx
0x18003ed54  mov     r8d, 0B0h
0x18003ed5a  lea     rcx, [rbp+440h+var_220]
0x18003ed61  call    ?CreateWNFStateName@CSmsRpcUtils@@SAJPEAU_WNF_STATE_NAME@@PEBGKW4_WNF_STATE_NAME_LIFETIME@@@Z; CSmsRpcUtils::CreateWNFStateName(_WNF_STATE_NAME *,ushort const *,ulong,_WNF_STATE_NAME_LIFETIME)
0x18003ed66  mov     r14d, eax
0x18003ed69  test    eax, eax
0x18003ed6b  jns     short loc_18003ED7E
0x18003ed6d  lea     r9, aCreatewnfstate; "CreateWNFStateName"
0x18003ed74  mov     edx, 395h
0x18003ed79  jmp     loc_18003ECA5
0x18003ed7e  xor     r9d, r9d; lpName
0x18003ed81  xor     r8d, r8d; bInitialState
0x18003ed84  lea     edx, [r9+1]; bManualReset
0x18003ed88  xor     ecx, ecx; lpEventAttributes
0x18003ed8a  call    cs:__imp_CreateEventW
0x18003ed90  mov     r14, rax
0x18003ed93  mov     [rsp+540h+hHandle], rax
0x18003ed98  test    rax, rax
0x18003ed9b  jnz     short loc_18003EDC9
0x18003ed9d  call    cs:__imp_GetLastError
0x18003eda3  mov     r14d, eax
0x18003eda6  test    eax, eax
0x18003eda8  jle     short loc_18003EDB5
0x18003edaa  movzx   r14d, ax
0x18003edae  or      r14d, 80070000h
0x18003edb5  lea     r9, aCreateevent; "CreateEvent"
0x18003edbc  mov     r8d, r14d
0x18003edbf  mov     edx, 3A4h
0x18003edc4  jmp     loc_18003ECA8
0x18003edc9  mov     [rsp+540h+var_500], 2
0x18003edd1  mov     ecx, 0F0h; unsigned __int64
0x18003edd6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003eddb  mov     rbx, rax
0x18003edde  mov     [rbp+440h+var_4B8], rax
0x18003ede2  mov     edx, r12d
0x18003ede5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003ede9  mov     eax, edx
0x18003edeb  lea     rcx, [rax+rax*2]
0x18003edef  add     rcx, rcx
0x18003edf2  lea     rax, qword_18008C2A0
0x18003edf9  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18003edfd  movups  xmmword ptr [rbx+rcx*8], xmm0
0x18003ee01  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x18003ee06  movups  xmmword ptr [rbx+rcx*8+10h], xmm1
0x18003ee0b  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x18003ee10  movups  xmmword ptr [rbx+rcx*8+20h], xmm0
0x18003ee15  cmp     dword ptr [rbx+rcx*8+10h], 1
0x18003ee1a  jnz     short loc_18003EE64
0x18003ee1c  mov     rax, [rbx+rcx*8]
0x18003ee20  cmp     rax, cs:DEVPKEY_SmsDevice_NetworkInterfaceId
0x18003ee27  jnz     short loc_18003EE9A
0x18003ee29  mov     rax, [rbx+rcx*8+8]
0x18003ee2e  cmp     rax, cs:qword_180078658
0x18003ee35  jnz     short loc_18003EE9A
0x18003ee37  lea     rax, [rbp+440h+sz]
0x18003ee3e  mov     [rbx+rcx*8+28h], rax
0x18003ee43  lea     r8, [rbp+440h+sz]
0x18003ee4a  mov     rax, rsi
0x18003ee4d  inc     rax
0x18003ee50  cmp     [r8+rax*2], r12w
0x18003ee55  jnz     short loc_18003EE4D
0x18003ee57  lea     eax, ds:2[rax*2]
0x18003ee5e  mov     [rbx+rcx*8+24h], eax
0x18003ee62  jmp     short loc_18003EE9A
0x18003ee64  cmp     dword ptr [rbx+rcx*8+10h], 2
0x18003ee69  jnz     short loc_18003EE9A
0x18003ee6b  mov     rax, [rbx+rcx*8]
0x18003ee6f  cmp     rax, cs:DEVPKEY_SmsDevice_DeviceStateWnf
0x18003ee76  jnz     short loc_18003EE9A
0x18003ee78  mov     rax, [rbx+rcx*8+8]
0x18003ee7d  cmp     rax, cs:qword_1800785C0
0x18003ee84  jnz     short loc_18003EE9A
0x18003ee86  lea     rax, [rbp+440h+var_220]
0x18003ee8d  mov     [rbx+rcx*8+28h], rax
0x18003ee92  mov     dword ptr [rbx+rcx*8+24h], 8
0x18003ee9a  inc     edx
0x18003ee9c  cmp     edx, 5
0x18003ee9f  jl      loc_18003EDE9
0x18003eea5  mov     r12d, 7FFFFFFEh
0x18003eeab  mov     edx, r12d
0x18003eeae  lea     r8, aSmsdevice20; "SmsDevice2\\0"
0x18003eeb5  mov     eax, 32h ; '2'
0x18003eeba  lea     rcx, [rbp+440h+var_B0]
0x18003eec1  xor     r10d, r10d
0x18003eec4  test    rdx, rdx
0x18003eec7  jz      short loc_18003EEF1
0x18003eec9  movzx   r9d, word ptr [r8]
0x18003eecd  test    r9w, r9w
0x18003eed1  jz      short loc_18003EEE8
0x18003eed3  add     r8, 2
0x18003eed7  mov     [rcx], r9w
0x18003eedb  add     rcx, 2
0x18003eedf  dec     rdx
0x18003eee2  sub     rax, 1
0x18003eee6  jnz     short loc_18003EEC4
0x18003eee8  test    rax, rax
0x18003eeeb  jnz     short loc_18003EEF1
0x18003eeed  sub     rcx, 2
0x18003eef1  mov     [rcx], r10w
0x18003eef5  lea     r9, [rbp+440h+sz]
0x18003eefc  lea     r8, aSmsDevice2S; "SMS_DEVICE2_%s"
0x18003ef03  mov     edx, 40h ; '@'; unsigned __int64
0x18003ef08  lea     rcx, [rbp+440h+var_130]; unsigned __int16 *
0x18003ef0f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ef14  mov     [rbp+440h+var_440], r14
0x18003ef18  mov     [rbp+440h+var_430], 80004005h
0x18003ef1f  mov     [rbp+440h+var_490], 48h ; 'H'
0x18003ef26  lea     rax, [rbp+440h+var_130]
0x18003ef2d  mov     [rbp+440h+var_488], rax
0x18003ef31  lea     rax, [rbp+440h+var_B0]
0x18003ef38  mov     [rbp+440h+var_480], rax
0x18003ef3c  lea     rax, aSwdSmsdeviceSm; "SWD\\SMSDEVICE\\SmsDevice2\\0"
0x18003ef43  mov     [rbp+440h+var_478], rax
0x18003ef47  mov     [rbp+440h+var_468], 6
0x18003ef4e  lea     rax, aWindowsDevices; "Windows.Devices.Sms.SmsDevice2"
0x18003ef55  mov     [rbp+440h+var_460], rax
0x18003ef59  lea     rax, [rsp+540h+var_4F0]
0x18003ef5e  mov     [rsp+540h+var_508], rax
0x18003ef63  lea     rax, [rbp+440h+var_440]
0x18003ef67  mov     [rsp+540h+pcbData], rax
0x18003ef6c  lea     rax, ?SwDeviceCallback@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; SwDeviceCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18003ef73  mov     qword ptr [rsp+540h+cbData], rax
0x18003ef78  mov     [rsp+540h+lpData], rbx
0x18003ef7d  mov     r9d, 5
0x18003ef83  lea     r8, [rbp+440h+var_490]
0x18003ef87  mov     rdx, r13
0x18003ef8a  lea     rcx, aSmsdevice; "SMSDEVICE"
0x18003ef91  call    cs:__imp_SwDeviceCreate
0x18003ef97  mov     r14d, eax
0x18003ef9a  mov     r13d, 80070000h
0x18003efa0  cmp     eax, 800700B7h
0x18003efa5  jz      loc_18003F170
0x18003efab  xor     r12d, r12d
0x18003efae  test    eax, eax
0x18003efb0  jns     short loc_18003EFE8
0x18003efb2  lea     r9, aSwdevicecreate_2; "SwDeviceCreate: InstanceID: %S, ParentI"...
0x18003efb9  mov     edx, 3D6h; unsigned int
0x18003efbe  mov     r8d, r14d; int
0x18003efc1  mov     rax, [rsp+540h+var_4F8]
0x18003efc6  mov     qword ptr [rsp+540h+cbData], rax
0x18003efcb  lea     rax, [rbp+440h+var_130]
0x18003efd2  mov     [rsp+540h+lpData], rax
0x18003efd7  lea     rcx, aCsmsdevicemana_3; "CSmsDeviceManager::CreateSwDevice"
0x18003efde  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003efe3  jmp     loc_18003F493
0x18003efe8  mov     edx, 493E0h; dwMilliseconds
0x18003efed  mov     rcx, [rsp+540h+hHandle]; hHandle
0x18003eff2  call    cs:__imp_WaitForSingleObject
0x18003eff8  test    eax, eax
0x18003effa  jz      short loc_18003F013
0x18003effc  mov     r8d, 80004005h
0x18003f002  mov     r14d, r8d
0x18003f005  lea     r9, aSwdevicecreate_1; "SwDeviceCreate.WaitForSingleObject: Ins"...
0x18003f00c  mov     edx, 3DFh
0x18003f011  jmp     short loc_18003EFC1
0x18003f013  mov     r14d, [rbp+440h+var_430]
0x18003f017  test    r14d, r14d
0x18003f01a  jns     short loc_18003F02A
0x18003f01c  lea     r9, aSwdevicecreate_0; "SwDeviceCreate.ctx.CreateResult: Instan"...
0x18003f023  mov     edx, 3E7h
0x18003f028  jmp     short loc_18003EFBE
0x18003f02a  lea     rcx, [rbp+440h+Data]
0x18003f02e  mov     rax, rsi
0x18003f031  inc     rax
0x18003f034  cmp     [rcx+rax*2], r12w
0x18003f039  jnz     short loc_18003F031
0x18003f03b  lea     eax, ds:2[rax*2]
0x18003f042  mov     [rsp+540h+cbData], eax; cbData
0x18003f046  lea     rax, [rbp+440h+Data]
0x18003f04a  mov     [rsp+540h+lpData], rax; lpData
0x18003f04f  mov     r9d, 1; dwType
0x18003f055  xor     r8d, r8d; Reserved
0x18003f058  lea     r14, aDeviceid; "DeviceId"
0x18003f05f  mov     rdx, r14; lpValueName
0x18003f062  mov     rcx, rdi; hKey
0x18003f065  call    cs:__imp_RegSetValueExW
0x18003f06b  test    eax, eax
0x18003f06d  jz      short loc_18003F097
0x18003f06f  jle     short loc_18003F077
0x18003f071  movzx   eax, ax
0x18003f074  or      eax, r13d
0x18003f077  mov     [rsp+540h+lpData], r14
0x18003f07c  lea     r9, aRegsetvalueexF; "RegSetValueEx for %S"
0x18003f083  mov     r8d, eax; int
0x18003f086  mov     edx, 3F4h; unsigned int
0x18003f08b  lea     rcx, aCsmsdevicemana_3; "CSmsDeviceManager::CreateSwDevice"
0x18003f092  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003f097  xor     edx, edx
0x18003f099  mov     rcx, [rsp+540h+var_4F0]
0x18003f09e  call    cs:__imp_SwDeviceSetLifetime
0x18003f0a4  lea     rax, [rsp+540h+Src]
0x18003f0a9  mov     [rsp+540h+pcbData], rax
0x18003f0ae  mov     [rsp+540h+cbData], 1
0x18003f0b6  lea     rax, qword_18008C390
0x18003f0bd  mov     [rsp+540h+lpData], rax
0x18003f0c2  mov     r9d, 1
0x18003f0c8  xor     r8d, r8d
0x18003f0cb  lea     rdx, qword_1800786D8
  ... truncated ...
```
