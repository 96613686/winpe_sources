# Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(void *,_BLUETOOTH_DEVICE_INFO const *,_GUID)

- ea: `0x180024e1c`
- end: `0x18002571e`
- name: `?BthpIsTopOfServiceGroup@BthServ@Services@Bluetooth@Microsoft@@YAEPEAXPEBU_BLUETOOTH_DEVICE_INFO@@U_GUID@@@Z`
- size: `2306`
- prototype: `char __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, struct _BLUETOOTH_DEVICE_INFO *, struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180025e24`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x1800110fc`
- `0x180011194`
- `0x1800114c8`
- `0x180016664`
- `0x180022af0`
- `0x180022b34`
- `0x180022d0c`
- `0x180022f30`
- `0x1800231ac`
- `0x180024ca8`
- `0x180024e1c`
- `0x180032c44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002518d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025415`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002518d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025415`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024ffb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800252c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024ffb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800252c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002500b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002532a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002500b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002532a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800255b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800255d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800255b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800255d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025280`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025290`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025340`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025280`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025290`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025340`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024fae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024fae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800256eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800256eb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800250a6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800250a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024f0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024f0e`

## string_xrefs

- `0x180024f00`: `System\CurrentControlSet\Services\BTHPORT\Parameters\ServiceGroups`

## pseudocode

```c
char __fastcall Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        struct _BLUETOOTH_DEVICE_INFO *a3,
        struct _GUID *a4)
{
  int v4; // ecx
  int v5; // edx
  int v6; // r9d
  int v7; // r10d
  char v8; // r15
  int v9; // r11d
  int v10; // ebx
  int v11; // edi
  int v12; // esi
  int v13; // r8d
  _QWORD *v14; // rcx
  char v15; // dl
  unsigned __int64 v16; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v18; // rax
  unsigned int v19; // ebx
  WCHAR *v20; // rsi
  HANDLE v21; // rax
  void *v22; // rax
  int v23; // r8d
  BYTE *v24; // rdi
  void **v25; // rbx
  DWORD v26; // ecx
  void *v27; // rdx
  __int64 v28; // r8
  _BYTE *v29; // rcx
  _UNKNOWN **v30; // rax
  unsigned int v31; // esi
  BYTE *v32; // rbx
  __int64 v33; // rdi
  struct _BLUETOOTH_SERVICE_RECORD *v34; // r8
  Microsoft::Bluetooth::Services::BthServ *v35; // rdi
  HANDLE v36; // rax
  Microsoft::Bluetooth::Services::BthServ **v37; // rbx
  unsigned int *v38; // r9
  struct _BLUETOOTH_SDP_RECORD *v39; // rax
  struct _GUID *v40; // r8
  struct _GUID *v41; // r9
  Microsoft::Bluetooth::Services::BthServ *v42; // rdi
  DWORD LastError; // esi
  HANDLE v44; // rax
  void *v45; // rdx
  int v46; // eax
  __int64 v47; // r9
  unsigned int v48; // esi
  _WORD *v49; // rbx
  __int64 v50; // rdi
  int v51; // eax
  void *v52; // rdx
  char v53; // dl
  HANDLE v54; // rax
  HANDLE v55; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  int lpcbMaxSubKeyLena; // [rsp+28h] [rbp-D8h]
  int lpcbMaxValueNameLen; // [rsp+40h] [rbp-C0h]
  char v62; // [rsp+70h] [rbp-90h]
  Microsoft::Bluetooth::Services::BthServ *FirstServiceInternal; // [rsp+78h] [rbp-88h]
  DWORD cbMaxValueNameLen; // [rsp+80h] [rbp-80h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-78h]
  __int64 cValues; // [rsp+90h] [rbp-70h] BYREF
  DWORD v67; // [rsp+98h] [rbp-68h]
  DWORD Type; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int32 v69; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v70; // [rsp+A4h] [rbp-5Ch]
  WCHAR *v71; // [rsp+A8h] [rbp-58h]
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  __int128 Buf1; // [rsp+B8h] [rbp-48h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v74; // [rsp+C8h] [rbp-38h]
  __int64 v75; // [rsp+D0h] [rbp-30h]
  DWORD cbData; // [rsp+D8h] [rbp-28h] BYREF
  DWORD cchValueName; // [rsp+DCh] [rbp-24h] BYREF
  void *v78; // [rsp+E0h] [rbp-20h]
  Microsoft::Bluetooth::Services::BthServ *v79; // [rsp+E8h] [rbp-18h]
  void *Buf2; // [rsp+F0h] [rbp-10h]
  int v81; // [rsp+100h] [rbp+0h] BYREF
  char v82[4]; // [rsp+104h] [rbp+4h] BYREF
  __int64 v83; // [rsp+108h] [rbp+8h]
  unsigned int v84; // [rsp+110h] [rbp+10h]
  char v85; // [rsp+114h] [rbp+14h]
  Microsoft::Bluetooth::Services::BthServ *v86; // [rsp+120h] [rbp+20h]
  unsigned __int16 v87[40]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v88[40]; // [rsp+720h] [rbp+620h] BYREF

  v79 = this;
  v4 = a3->Address.rgBytes[6];
  v78 = a2;
  v5 = a3->Address.rgBytes[5];
  v6 = a3->Address.rgBytes[3];
  v7 = a3->Address.rgBytes[2];
  v8 = 1;
  v9 = a3->Address.rgBytes[1];
  v10 = a3->Address.rgBytes[0];
  v11 = *((unsigned __int16 *)&a3->dwSize + 3);
  v12 = *((unsigned __int16 *)&a3->dwSize + 2);
  Buf2 = a3;
  hKey = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  if ( (int)StringCbPrintfW(
              v87,
              0x4Eu,
              L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
              a3->dwSize,
              v12,
              v11,
              v10,
              v9,
              v7,
              v6,
              a3->Address.rgBytes[4],
              v5,
              v4,
              a3->Address.rgBytes[7]) < 0 )
    goto LABEL_121;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\ServiceGroups",
         0,
         0x20019u,
         &hKey) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v15 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      v15 = 0;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_121;
    goto LABEL_120;
  }
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, (LPDWORD)&cValues, &cbMaxValueNameLen, (LPDWORD)&cValues + 1, 0, 0)
    || !(_DWORD)cValues )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v15 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      v15 = 0;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_121;
LABEL_120:
    WPP_RECORDER_AND_TRACE_SF_s(v14[2], v15, v13, v14[5]);
    goto LABEL_121;
  }
  if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
  {
    cbMaxValueNameLen = -1;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v15 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      v15 = 0;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_121;
    goto LABEL_120;
  }
  v16 = 2LL * ++cbMaxValueNameLen;
  if ( v16 > 0xFFFFFFFF )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v15 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      v15 = 0;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_121;
    goto LABEL_120;
  }
  ProcessHeap = GetProcessHeap();
  v18 = (WCHAR *)HeapAlloc(ProcessHeap, 0, (unsigned int)v16);
  v19 = HIDWORD(cValues);
  v20 = v18;
  v71 = v18;
  v21 = GetProcessHeap();
  v22 = HeapAlloc(v21, 0, v19);
  lpMem = v22;
  v24 = (BYTE *)v22;
  if ( !v20 || !v22 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v53 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      v53 = 0;
    if ( v53 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v53, v23, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    if ( v24 )
      goto LABEL_100;
    goto LABEL_101;
  }
  v25 = 0;
  v26 = 0;
  FirstServiceInternal = 0;
  v67 = 0;
  v62 = 0;
  if ( !(_DWORD)cValues )
    goto LABEL_100;
  while ( 1 )
  {
    cbData = HIDWORD(cValues);
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    if ( RegEnumValueW(hKey, v26, v20, &cchValueName, 0, &Type, v24, &cbData) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v27) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        LOBYTE(v27) = 0;
      }
      if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v27,
          v28,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          phkResult,
          lpcbMaxSubKeyLen,
          22,
          (__int64)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids);
      }
LABEL_91:
      if ( v25 )
        goto LABEL_84;
      goto LABEL_100;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v27) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
    {
      LOBYTE(v27) = 0;
    }
    v30 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v27,
        v28,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        phkResult,
        lpcbMaxSubKeyLen,
        23,
        (__int64)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids,
        lpcbMaxValueNameLen,
        (__int64)v20);
      v29 = WPP_GLOBAL_Control;
      v30 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
    }
    if ( Type != 7 )
    {
      if ( v29 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v27) = 1, v29[25] < 3u) )
        LOBYTE(v27) = 0;
      if ( (_BYTE)v27 || v30 != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = v30 != &WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v29 + 2), (_BYTE)v27, v28, *((_QWORD *)v29 + 5));
      }
      goto LABEL_74;
    }
    v31 = 0;
    v70 = 0;
    v32 = v24;
    if ( *(_WORD *)v24 )
    {
      while ( 1 )
      {
        v33 = -1;
        do
          ++v33;
        while ( *(_WORD *)&v32[2 * v33] );
        if ( !(unsigned int)_o__wcsicmp(v32, v87, v28, 0) )
          break;
        ++v31;
        v32 += 2 * v33 + 2;
        v70 = v31;
        if ( !*(_WORD *)v32 )
          goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v27) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
      {
        LOBYTE(v27) = 0;
      }
      if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v27,
          v28,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          phkResult,
          lpcbMaxSubKeyLen,
          25,
          (__int64)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids);
      }
      v62 = 1;
LABEL_43:
      v24 = (BYTE *)lpMem;
    }
    if ( !v62 )
    {
      v25 = (void **)FirstServiceInternal;
      goto LABEL_73;
    }
    memset_0(v82, 0, 0x5C4u);
    *((_QWORD *)&Buf1 + 1) = v78;
    v74 = v79;
    *(_QWORD *)&Buf1 = 32;
    v75 = 0;
    v81 = 1480;
    FirstServiceInternal = (Microsoft::Bluetooth::Services::BthServ *)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
                                                                        (__int64)&Buf1,
                                                                        &v81,
                                                                        2u);
    v25 = (void **)FirstServiceInternal;
    if ( FirstServiceInternal )
      break;
LABEL_73:
    v20 = v71;
LABEL_74:
    v26 = v67 + 1;
    v67 = v26;
    if ( v26 >= (unsigned int)cValues )
      goto LABEL_91;
  }
  while ( 1 )
  {
    Buf1 = 0;
    if ( v81 != 1480 )
    {
      SetLastError(0x51Au);
      goto LABEL_69;
    }
    SetLastError(0xDu);
    if ( (v85 & 2) == 0 )
      goto LABEL_69;
    v35 = v86;
    if ( !v86 || (*(_BYTE *)v86 & 0xF8) != 0x30 )
    {
      v24 = (BYTE *)lpMem;
      goto LABEL_69;
    }
    v36 = GetProcessHeap();
    v37 = (Microsoft::Bluetooth::Services::BthServ **)HeapAlloc(v36, 0, 0x18u);
    if ( v37 )
      break;
LABEL_67:
    v24 = (BYTE *)lpMem;
LABEL_68:
    v25 = (void **)FirstServiceInternal;
LABEL_69:
    if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
                          (Microsoft::Bluetooth::Services::BthServ *)v25,
                          (char *)&v81,
                          v34) )
    {
      Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(v25, v52);
      v25 = 0;
      FirstServiceInternal = 0;
      goto LABEL_73;
    }
  }
  v69 = 0;
  v39 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
          v35,
          (struct _BLUETOOTH_SDP_RECORD *)(v83 + v84),
          &v69,
          v38);
  v42 = 0;
  *v37 = v39;
  if ( v39 )
  {
    v37[1] = (struct _BLUETOOTH_SDP_RECORD *)((char *)v39 + v69);
    if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(
                          v37,
                          (struct _BLUETOOTH_SDP_RECORD *)&Buf1,
                          v40,
                          v41) )
    {
      LastError = GetLastError();
      goto LABEL_57;
    }
    LastError = 0;
    v42 = (Microsoft::Bluetooth::Services::BthServ *)v37;
  }
  else
  {
    LastError = 1168;
LABEL_57:
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v37);
  }
  SetLastError(LastError);
  if ( !v42 )
    goto LABEL_67;
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v42, v45);
  if ( !memcmp_0(&Buf1, Buf2, 0x10u) )
    goto LABEL_67;
  lpcbMaxValueNameLen = BYTE10(Buf1);
  lpcbMaxSubKeyLena = WORD3(Buf1);
  phkResulta = WORD2(Buf1);
  v46 = StringCbPrintfW(v88, 0x4Eu, L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}", (unsigned int)Buf1);
  v27 = 0;
  if ( v46 < 0 )
    goto LABEL_83;
  v24 = (BYTE *)lpMem;
  v48 = 0;
  v49 = lpMem;
  if ( !*(_WORD *)lpMem )
    goto LABEL_68;
  while ( 1 )
  {
    v50 = -1;
    do
      ++v50;
    while ( v49[v50] );
    v51 = _o__wcsicmp(v49, v88, v34, v47);
    v27 = 0;
    if ( !v51 && v48 < v70 )
      break;
    ++v48;
    v49 += v50 + 1;
    if ( !*v49 )
      goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    v8 = 0;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v27) = v8;
    LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v27,
      (_DWORD)v34,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      phkResulta,
      lpcbMaxSubKeyLena,
      26,
      (__int64)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids);
    v27 = 0;
  }
  v8 = 0;
LABEL_83:
  v25 = (void **)FirstServiceInternal;
LABEL_84:
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(v25, v27);
LABEL_100:
  v54 = GetProcessHeap();
  HeapFree(v54, 0, lpMem);
  v20 = v71;
LABEL_101:
  if ( v20 )
  {
    v55 = GetProcessHeap();
    HeapFree(v55, 0, v20);
  }
LABEL_121:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180024e1c  mov     [rsp-8+arg_18], rbx
0x180024e21  push    rbp
0x180024e22  push    rsi
0x180024e23  push    rdi
0x180024e24  push    r12
0x180024e26  push    r13
0x180024e28  push    r14
0x180024e2a  push    r15
0x180024e2c  lea     rbp, [rsp-680h]
0x180024e34  sub     rsp, 780h
0x180024e3b  mov     rax, cs:__security_cookie
0x180024e42  xor     rax, rsp
0x180024e45  mov     [rbp+6B0h+var_40], rax
0x180024e4c  mov     r14, r8
0x180024e4f  mov     [rbp+6B0h+var_6C8], rcx
0x180024e53  movzx   ecx, byte ptr [r8+0Eh]
0x180024e58  xor     eax, eax
0x180024e5a  mov     [rbp+6B0h+var_6D0], rdx
0x180024e5e  movzx   edx, byte ptr [r8+0Dh]
0x180024e63  movzx   r9d, byte ptr [r14+0Bh]
0x180024e68  movzx   r10d, byte ptr [r14+0Ah]
0x180024e6d  lea     r15d, [rax+1]
0x180024e71  movzx   r11d, byte ptr [r14+9]
0x180024e76  movzx   ebx, byte ptr [r14+8]
0x180024e7b  movzx   edi, word ptr [r14+6]
0x180024e80  movzx   esi, word ptr [r14+4]
0x180024e85  mov     [rbp+6B0h+Buf2], r8
0x180024e89  mov     [rbp+6B0h+hKey], rax
0x180024e8d  mov     dword ptr [rbp+6B0h+cValues], eax
0x180024e90  mov     [rbp+6B0h+cbMaxValueNameLen], eax
0x180024e93  mov     dword ptr [rbp+6B0h+cValues+4], eax
0x180024e96  movzx   eax, byte ptr [r8+0Fh]
0x180024e9b  movzx   r8d, byte ptr [r8+0Ch]
0x180024ea0  mov     [rsp+7B0h+var_748], eax
0x180024ea4  mov     [rsp+7B0h+var_750], ecx
0x180024ea8  lea     rcx, [rbp+6B0h+var_E0]; unsigned __int16 *
0x180024eaf  mov     dword ptr [rsp+7B0h+lpftLastWriteTime], edx
0x180024eb3  lea     edx, [r15+4Dh]; unsigned __int64
0x180024eb7  mov     dword ptr [rsp+7B0h+lpcbSecurityDescriptor], r8d
0x180024ebc  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180024ec3  mov     dword ptr [rsp+7B0h+lpcbMaxValueLen], r9d
0x180024ec8  mov     r9d, [r14]
0x180024ecb  mov     dword ptr [rsp+7B0h+lpcbMaxValueNameLen], r10d
0x180024ed0  mov     dword ptr [rsp+7B0h+lpcValues], r11d
0x180024ed5  mov     dword ptr [rsp+7B0h+lpcbMaxClassLen], ebx
0x180024ed9  mov     dword ptr [rsp+7B0h+lpcbMaxSubKeyLen], edi
0x180024edd  mov     dword ptr [rsp+7B0h+phkResult], esi
0x180024ee1  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024ee6  test    eax, eax
0x180024ee8  js      loc_1800256E2
0x180024eee  lea     rax, [rbp+6B0h+hKey]
0x180024ef2  mov     r9d, 20019h; samDesired
0x180024ef8  xor     r8d, r8d; ulOptions
0x180024efb  mov     [rsp+7B0h+phkResult], rax; phkResult
0x180024f00  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\BT"...
0x180024f07  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024f0e  call    cs:__imp_RegOpenKeyExW
0x180024f14  xor     r9d, r9d; lpReserved
0x180024f17  test    eax, eax
0x180024f19  jz      short loc_180024F71
0x180024f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f22  lea     r14, WPP_GLOBAL_Control
0x180024f29  cmp     rcx, r14
0x180024f2c  jz      short loc_180024F37
0x180024f2e  cmp     byte ptr [rcx+19h], 4
0x180024f32  mov     dl, r15b
0x180024f35  jnb     short loc_180024F3A
0x180024f37  mov     dl, r9b
0x180024f3a  lea     r12, WPP_RECORDER_INITIALIZED
0x180024f41  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180024f48  setnz   r8b
0x180024f4c  test    dl, dl
0x180024f4e  jnz     short loc_180024F59
0x180024f50  test    r8b, r8b
0x180024f53  jz      loc_1800256E2
0x180024f59  lea     r13, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180024f60  mov     [rsp+7B0h+lpcValues], r13
0x180024f65  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 11h
0x180024f6c  jmp     loc_1800256D5
0x180024f71  mov     rcx, [rbp+6B0h+hKey]; hKey
0x180024f75  lea     rax, [rbp+6B0h+cValues+4]
0x180024f79  mov     [rsp+7B0h+lpftLastWriteTime], r9; lpftLastWriteTime
0x180024f7e  xor     r8d, r8d; lpcchClass
0x180024f81  mov     [rsp+7B0h+lpcbSecurityDescriptor], r9; lpcbSecurityDescriptor
0x180024f86  xor     edx, edx; lpClass
0x180024f88  mov     [rsp+7B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180024f8d  lea     rax, [rbp+6B0h+cbMaxValueNameLen]
0x180024f91  mov     [rsp+7B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180024f96  lea     rax, [rbp+6B0h+cValues]
0x180024f9a  mov     [rsp+7B0h+lpcValues], rax; lpcValues
0x180024f9f  mov     [rsp+7B0h+lpcbMaxClassLen], r9; lpcbMaxClassLen
0x180024fa4  mov     [rsp+7B0h+lpcbMaxSubKeyLen], r9; lpcbMaxSubKeyLen
0x180024fa9  mov     [rsp+7B0h+phkResult], r9; lpcSubKeys
0x180024fae  call    cs:__imp_RegQueryInfoKeyW
0x180024fb4  xor     r9d, r9d
0x180024fb7  test    eax, eax
0x180024fb9  jnz     loc_180025688
0x180024fbf  cmp     dword ptr [rbp+6B0h+cValues], r9d
0x180024fc3  jz      loc_180025688
0x180024fc9  mov     eax, [rbp+6B0h+cbMaxValueNameLen]
0x180024fcc  lea     ecx, [rax+1]
0x180024fcf  cmp     ecx, eax
0x180024fd1  mov     eax, 0FFFFFFFFh
0x180024fd6  jb      loc_180025636
0x180024fdc  mov     ebx, ecx
0x180024fde  add     rbx, rbx
0x180024fe1  mov     [rbp+6B0h+cbMaxValueNameLen], ecx
0x180024fe4  cmp     rbx, rax
0x180024fe7  ja      loc_1800255E0
0x180024fed  call    cs:__imp_GetProcessHeap
0x180024ff3  mov     r8d, ebx; dwBytes
0x180024ff6  xor     edx, edx; dwFlags
0x180024ff8  mov     rcx, rax; hHeap
0x180024ffb  call    cs:__imp_HeapAlloc
0x180025001  mov     ebx, dword ptr [rbp+6B0h+cValues+4]
0x180025004  mov     rsi, rax
0x180025007  mov     [rbp+6B0h+var_708], rax
0x18002500b  call    cs:__imp_GetProcessHeap
0x180025011  mov     r8d, ebx; dwBytes
0x180025014  xor     edx, edx; dwFlags
0x180025016  mov     rcx, rax; hHeap
0x180025019  call    cs:__imp_HeapAlloc
0x18002501f  xor     r9d, r9d
0x180025022  mov     [rbp+6B0h+lpMem], rax
0x180025026  mov     rdi, rax
0x180025029  test    rsi, rsi
0x18002502c  jz      loc_180025546
0x180025032  test    rax, rax
0x180025035  jz      loc_180025546
0x18002503b  mov     ebx, r9d
0x18002503e  mov     ecx, r9d
0x180025041  mov     [rsp+7B0h+var_738], rbx
0x180025046  mov     [rbp+6B0h+var_718], ecx
0x180025049  mov     [rsp+7B0h+var_740], r9b
0x18002504e  cmp     dword ptr [rbp+6B0h+cValues], r9d
0x180025052  jbe     loc_1800255A5
0x180025058  lea     r14, WPP_GLOBAL_Control
0x18002505f  lea     r12, WPP_RECORDER_INITIALIZED
0x180025066  lea     r13, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x18002506d  mov     eax, dword ptr [rbp+6B0h+cValues+4]
0x180025070  mov     edx, ecx; dwIndex
0x180025072  mov     rcx, [rbp+6B0h+hKey]; hKey
0x180025076  mov     r8, rsi; lpValueName
0x180025079  mov     [rbp+6B0h+cbData], eax
0x18002507c  mov     eax, [rbp+6B0h+cbMaxValueNameLen]
0x18002507f  mov     [rbp+6B0h+cchValueName], eax
0x180025082  lea     rax, [rbp+6B0h+cbData]
0x180025086  mov     [rsp+7B0h+lpcValues], rax; lpcbData
0x18002508b  lea     rax, [rbp+6B0h+Type]
0x18002508f  mov     [rsp+7B0h+lpcbMaxClassLen], rdi; lpData
0x180025094  mov     [rsp+7B0h+lpcbMaxSubKeyLen], rax; lpType
0x180025099  mov     [rsp+7B0h+phkResult], r9; lpReserved
0x18002509e  mov     [rbp+6B0h+Type], r9d
0x1800250a2  lea     r9, [rbp+6B0h+cchValueName]; lpcchValueName
0x1800250a6  call    cs:__imp_RegEnumValueW
0x1800250ac  xor     r9d, r9d
0x1800250af  test    eax, eax
0x1800250b1  jnz     loc_1800254F3
0x1800250b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250be  cmp     rcx, r14
0x1800250c1  jz      short loc_1800250CC
0x1800250c3  cmp     byte ptr [rcx+19h], 2
0x1800250c7  mov     dl, r15b
0x1800250ca  jnb     short loc_1800250CF
0x1800250cc  mov     dl, r9b
0x1800250cf  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x1800250d6  cmp     rax, r12
0x1800250d9  setnz   r8b
0x1800250dd  test    dl, dl
0x1800250df  jnz     short loc_1800250E6
0x1800250e1  test    r8b, r8b
0x1800250e4  jz      short loc_180025115
0x1800250e6  mov     r9, [rcx+28h]
0x1800250ea  mov     rcx, [rcx+10h]
0x1800250ee  mov     [rsp+7B0h+lpcbMaxValueLen], rsi
0x1800250f3  mov     [rsp+7B0h+lpcValues], r13
0x1800250f8  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 17h
0x1800250ff  call    WPP_RECORDER_AND_TRACE_SF_sS
0x180025104  mov     rcx, cs:WPP_GLOBAL_Control
0x18002510b  xor     r9d, r9d
0x18002510e  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x180025115  cmp     [rbp+6B0h+Type], 7
0x180025119  jz      short loc_180025161
0x18002511b  cmp     rcx, r14
0x18002511e  jz      short loc_180025129
0x180025120  cmp     byte ptr [rcx+19h], 3
0x180025124  mov     dl, r15b
0x180025127  jnb     short loc_18002512C
0x180025129  mov     dl, r9b
0x18002512c  cmp     rax, r12
0x18002512f  setnz   r8b
0x180025133  test    dl, dl
0x180025135  jnz     short loc_180025140
0x180025137  test    r8b, r8b
0x18002513a  jz      loc_18002547B
0x180025140  mov     r9, [rcx+28h]
0x180025144  mov     rcx, [rcx+10h]
0x180025148  mov     [rsp+7B0h+lpcValues], r13
0x18002514d  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 18h
0x180025154  call    WPP_RECORDER_AND_TRACE_SF_s
0x180025159  xor     r9d, r9d
0x18002515c  jmp     loc_18002547B
0x180025161  mov     esi, r9d
0x180025164  mov     [rbp+6B0h+var_70C], r9d
0x180025168  mov     rbx, rdi
0x18002516b  cmp     [rdi], r9w
0x18002516f  jz      loc_180025205
0x180025175  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025179  inc     rdi
0x18002517c  cmp     [rbx+rdi*2], r9w
0x180025181  jnz     short loc_180025179
0x180025183  lea     rdx, [rbp+6B0h+var_E0]
0x18002518a  mov     rcx, rbx
0x18002518d  call    cs:__imp__o__wcsicmp
0x180025193  xor     r9d, r9d
0x180025196  test    eax, eax
0x180025198  jz      short loc_1800251B0
0x18002519a  add     esi, r15d
0x18002519d  lea     rbx, [rbx+rdi*2]
0x1800251a1  add     rbx, 2
0x1800251a5  mov     [rbp+6B0h+var_70C], esi
0x1800251a8  cmp     [rbx], r9w
0x1800251ac  jnz     short loc_180025175
0x1800251ae  jmp     short loc_180025201
0x1800251b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251b7  cmp     rcx, r14
0x1800251ba  jz      short loc_1800251C5
0x1800251bc  cmp     byte ptr [rcx+19h], 4
0x1800251c0  mov     dl, r15b
0x1800251c3  jnb     short loc_1800251C8
0x1800251c5  mov     dl, r9b
0x1800251c8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800251cf  setnz   r8b
0x1800251d3  test    dl, dl
0x1800251d5  jnz     short loc_1800251DC
0x1800251d7  test    r8b, r8b
0x1800251da  jz      short loc_1800251FC
0x1800251dc  mov     r9, [rcx+28h]
0x1800251e0  mov     rcx, [rcx+10h]
0x1800251e4  mov     dword ptr [rsp+7B0h+lpcbMaxValueLen], esi
0x1800251e8  mov     [rsp+7B0h+lpcValues], r13
0x1800251ed  mov     word ptr [rsp+7B0h+lpcbMaxClassLen], 19h
0x1800251f4  call    WPP_RECORDER_AND_TRACE_SF_sd
0x1800251f9  xor     r9d, r9d
0x1800251fc  mov     [rsp+7B0h+var_740], r15b
0x180025201  mov     rdi, [rbp+6B0h+lpMem]
0x180025205  cmp     [rsp+7B0h+var_740], r9b
0x18002520a  jz      loc_180025472
0x180025210  xor     edx, edx; Val
0x180025212  lea     rcx, [rbp+6B0h+var_6AC]; void *
0x180025216  mov     r8d, 5C4h; Size
0x18002521c  call    memset_0
0x180025221  mov     rax, [rbp+6B0h+var_6D0]
0x180025225  lea     rdx, [rbp+6B0h+var_6B0]
0x180025229  xor     esi, esi
0x18002522b  mov     qword ptr [rbp+6B0h+Buf1+8], rax
0x18002522f  mov     rax, [rbp+6B0h+var_6C8]
0x180025233  lea     rcx, [rbp+6B0h+Buf1]
0x180025237  mov     [rbp+6B0h+var_6E8], rax
0x18002523b  mov     qword ptr [rbp+6B0h+Buf1], 20h ; ' '
0x180025243  lea     r8d, [rsi+2]
0x180025247  mov     [rbp+6B0h+var_6E0], rsi
0x18002524b  mov     [rbp+6B0h+var_6B0], 5C8h
0x180025252  call    ?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x180025257  xor     r9d, r9d
0x18002525a  mov     [rsp+7B0h+var_738], rax
0x18002525f  mov     rbx, rax
0x180025262  test    rax, rax
0x180025265  jz      loc_180025477
0x18002526b  cmp     [rbp+6B0h+var_6B0], 5C8h
0x180025272  xorps   xmm0, xmm0
0x180025275  movups  [rbp+6B0h+Buf1], xmm0
0x180025279  jz      short loc_18002528B
0x18002527b  mov     ecx, 51Ah; dwErrCode
0x180025280  call    cs:__imp_SetLastError
0x180025286  jmp     loc_180025443
0x18002528b  mov     ecx, 0Dh; dwErrCode
0x180025290  call    cs:__imp_SetLastError
0x180025296  test    [rbp+6B0h+var_69C], 2
0x18002529a  jz      loc_180025443
0x1800252a0  mov     rdi, [rbp+6B0h+var_690]
0x1800252a4  test    rdi, rdi
0x1800252a7  jz      loc_18002546C
0x1800252ad  mov     al, [rdi]
0x1800252af  and     al, 0F8h
0x1800252b1  cmp     al, 30h ; '0'
0x1800252b3  jnz     loc_18002546C
0x1800252b9  call    cs:__imp_GetProcessHeap
0x1800252bf  xor     edx, edx; dwFlags
0x1800252c1  mov     rcx, rax; hHeap
0x1800252c4  lea     r8d, [rdx+18h]; dwBytes
0x1800252c8  call    cs:__imp_HeapAlloc
0x1800252ce  mov     rbx, rax
0x1800252d1  test    rax, rax
0x1800252d4  jz      loc_18002543A
0x1800252da  mov     edx, [rbp+6B0h+var_6A0]
0x1800252dd  lea     r8, [rbp+6B0h+var_710]; void *
0x1800252e1  add     rdx, [rbp+6B0h+var_6A8]; struct _BLUETOOTH_SDP_RECORD *
0x1800252e5  mov     rcx, rdi; this
0x1800252e8  mov     [rbp+6B0h+var_710], esi
  ... truncated ...
```
