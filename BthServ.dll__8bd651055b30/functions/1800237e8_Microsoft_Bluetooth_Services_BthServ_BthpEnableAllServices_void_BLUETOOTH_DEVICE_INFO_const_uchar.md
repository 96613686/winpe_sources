# Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(void *,_BLUETOOTH_DEVICE_INFO const *,uchar)

- ea: `0x1800237e8`
- end: `0x180023f3b`
- name: `?BthpEnableAllServices@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@E@Z`
- size: `1875`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, void *, const struct _BLUETOOTH_DEVICE_INFO *, unsigned __int8)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d5a0`

## callees

- `0x180001790`
- `0x180001cf0`
- `0x180001d58`
- `0x1800024ac`
- `0x1800086d8`
- `0x180011194`
- `0x18001140c`
- `0x180022688`
- `0x180022af0`
- `0x180022b34`
- `0x180022d0c`
- `0x180022f30`
- `0x1800231ac`
- `0x180023214`
- `0x1800237e8`
- `0x180024004`
- `0x1800248ac`
- `0x180024ca8`
- `0x180025e24`
- `0x1800284a8`
- `0x1800284c8`
- `0x18002863c`
- `0x180028a84`
- `0x180028b64`
- `0x180032bf0`
- `0x180032c44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800239a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800239a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023a15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023a15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023a23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002395a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023967`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002395a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023967`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023cd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023cd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023cfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023cfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c90`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023e78`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023e78`

## string_xrefs

- `0x180023c4a`: `System\CurrentControlSet\Services\BTHPORT\Parameters\Restrictions\COD Major %02x Minor %02x`
- `0x180023cca`: `DontAddIncomingSPPInWizard`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(
        Microsoft::Bluetooth::Services::BthServ *this,
        _QWORD *a2,
        const struct _BLUETOOTH_DEVICE_INFO *a3)
{
  char v5; // bl
  DWORD LastError; // r14d
  char v7; // di
  Microsoft::Bluetooth::Services::BthServ *FirstServiceInternal; // r12
  const struct _BLUETOOTH_DEVICE_INFO *v9; // rdx
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  struct _BLUETOOTH_SERVICE_RECORD *v13; // r8
  Microsoft::Bluetooth::Services::BthServ *v14; // rsi
  HANDLE ProcessHeap; // rax
  Microsoft::Bluetooth::Services::BthServ *v16; // rbx
  unsigned int *v17; // r9
  struct _BLUETOOTH_SDP_RECORD *v18; // rax
  struct _GUID *v19; // r8
  Microsoft::Bluetooth::Services::BthServ *v20; // rsi
  HANDLE v21; // rax
  void *v22; // rdx
  __int64 *v23; // rax
  int v24; // edx
  int v25; // edx
  int v26; // r8d
  char v27; // dl
  BOOL v28; // ebx
  unsigned int v29; // ebx
  void *v30; // rdx
  void *v31; // rdx
  __int64 v32; // rbx
  void *v33; // rcx
  int v34; // eax
  void *v35; // rdx
  unsigned int v36; // r8d
  HKEY v37; // rcx
  HKEY v38; // rbx
  void *v39; // rdx
  unsigned int v40; // r8d
  const char *v41; // r9
  int phkResult; // [rsp+20h] [rbp-E0h]
  struct _BLUETOOTH_LOCAL_SERVICE_INFO *phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int lpcbData; // [rsp+28h] [rbp-D8h]
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-C8h]
  int v48; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v49[8]; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v50; // [rsp+50h] [rbp-B0h]
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  __int128 Buf1; // [rsp+78h] [rbp-88h] BYREF
  Microsoft::Bluetooth::Services::BthServ *v56; // [rsp+88h] [rbp-78h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  _BLUETOOTH_DEVICE_INFO v58; // [rsp+98h] [rbp-68h] BYREF
  int v59; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v60[4]; // [rsp+2F4h] [rbp+1F4h] BYREF
  __int64 v61; // [rsp+2F8h] [rbp+1F8h]
  unsigned int v62; // [rsp+300h] [rbp+200h]
  char v63; // [rsp+304h] [rbp+204h]
  struct _BLUETOOTH_DEVICE_INFO *v64; // [rsp+308h] [rbp+208h]
  Microsoft::Bluetooth::Services::BthServ *v65; // [rsp+310h] [rbp+210h]
  WCHAR SubKey[6]; // [rsp+8C0h] [rbp+7C0h] BYREF
  int v67; // [rsp+8CCh] [rbp+7CCh]
  wil::details::in1diag3 *retaddr; // [rsp+1038h] [rbp+F38h]

  v5 = 0;
  memset_0(&v58.stLastSeen.wHour, 0, sizeof(_BLUETOOTH_DEVICE_INFO));
  *(_QWORD *)&v58.stLastUsed.wYear = a2[1];
  *(_DWORD *)&v58.stLastSeen.wHour = 560;
  LastError = 0;
  *(_QWORD *)&Buf1 = 32;
  v57 = 0;
  *((_QWORD *)&Buf1 + 1) = &v58.stLastSeen.wHour;
  v56 = this;
  memset_0(v60, 0, 0x5C4u);
  v59 = 1480;
  v7 = 1;
  do
  {
    if ( v5 )
      return 1168;
    FirstServiceInternal = (Microsoft::Bluetooth::Services::BthServ *)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
                                                                        &Buf1,
                                                                        &v59,
                                                                        1);
    v5 = 1;
  }
  while ( !FirstServiceInternal );
  memset(&v58, 0, 28);
  Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(this, a2, &v58, (struct _BTH_PNP_INFO *)1, phkResult);
  if ( (v58.fRemembered & 0xF) != 0xF )
  {
    v10 = Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(
            (Microsoft::Bluetooth::Services::BthServ *)a2,
            v9);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v11) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v11) = 0;
      }
      if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v49[0] = v10;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (_DWORD)phkResulta,
          lpcbData,
          11,
          (__int64)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids);
      }
    }
  }
  do
  {
    Buf1 = 0;
    if ( v59 != 1480 )
    {
      SetLastError(0x51Au);
      continue;
    }
    SetLastError(0xDu);
    if ( (v63 & 2) != 0 )
    {
      v14 = v65;
      if ( v65 )
      {
        if ( (*(_BYTE *)v65 & 0xF8) == 0x30 )
        {
          ProcessHeap = GetProcessHeap();
          v16 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(ProcessHeap, 0, 0x18u);
          if ( v16 )
          {
            Type = 0;
            v18 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
                    v14,
                    (struct _BLUETOOTH_SDP_RECORD *)(v61 + v62),
                    &Type,
                    v17);
            *(_QWORD *)v16 = v18;
            if ( v18 )
            {
              *((_QWORD *)v16 + 1) = (char *)v18 + Type;
              if ( Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(v16, &Buf1, v19) )
              {
                v20 = v16;
                goto LABEL_24;
              }
              LastError = GetLastError();
              v20 = 0;
            }
            else
            {
              v20 = 0;
              LastError = 1168;
            }
            v21 = GetProcessHeap();
            HeapFree(v21, 0, v16);
LABEL_24:
            SetLastError(LastError);
            LastError = 0;
            if ( v20 )
            {
              Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v20, v22);
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
                goto LABEL_37;
              if ( dword_180044E1C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + (unsigned int)tls_index)
                                               + 4LL) )
              {
                Init_thread_header(&dword_180044E1C);
                if ( dword_180044E1C == -1 )
                {
                  xmmword_180044D30 = (__int128)AudioSinkServiceClass_UUID;
                  xmmword_180044D40 = (__int128)AVRemoteControlTargetServiceClass_UUID;
                  xmmword_180044D50 = (__int128)AVRemoteControlServiceClass_UUID;
                  xmmword_180044D60 = (__int128)HandsfreeServiceClass_UUID;
                  Init_thread_footer(&dword_180044E1C);
                }
              }
              v23 = (__int64 *)&xmmword_180044D30;
              v24 = Buf1;
              do
              {
                if ( *(_OWORD *)v23 == Buf1 )
                  break;
                v23 += 2;
              }
              while ( v23 != ____PchSym__00_KxulyqvxgPillgKxulmvxlivUwirevihUdwnUyofvgllgsUfhviUygshvieUhvieviUyofvgllgszkrhUoryUlyquivUznwGEUkxsOlyq_bthserv_bluetoothapis );
              if ( v23 == ____PchSym__00_KxulyqvxgPillgKxulmvxlivUwirevihUdwnUyofvgllgsUfhviUygshvieUhvieviUyofvgllgszkrhUoryUlyquivUznwGEUkxsOlyq_bthserv_bluetoothapis )
              {
LABEL_37:
                if ( !memcmp_0(&Buf1, &SerialPortServiceClass_UUID, 0x10u) )
                {
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (v27 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
                  {
                    v27 = 0;
                  }
                  if ( v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    *(_QWORD *)v49 = a2[1];
                    lpOverlapped = (LPOVERLAPPED)&WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids;
                    LOWORD(lpBytesReturned) = 14;
                    WPP_RECORDER_AND_TRACE_SF_si(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v27,
                      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                      *((_QWORD *)WPP_GLOBAL_Control + 5));
                  }
                  if ( !Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
                          this,
                          &v58.stLastSeen.wHour,
                          (const struct _BLUETOOTH_DEVICE_INFO *)(unsigned int)v64,
                          0,
                          (const struct _GUID *)phkResulta,
                          lpcbData,
                          lpBytesReturned,
                          (unsigned __int8)lpOverlapped,
                          v48,
                          v49[0],
                          v50) )
                  {
                    LODWORD(phkResulta) = LOBYTE(v58.stLastUsed.wHour) >> 2;
                    if ( (int)StringCchPrintfW(
                                SubKey,
                                0xB8u,
                                L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\Restrictions\\COD Major %02x Minor %02x",
                                (*(_DWORD *)&v58.stLastUsed.wHour >> 8) & 0x1F) < 0 )
                      goto LABEL_59;
                    hKey = 0;
                    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
                      goto LABEL_59;
                    v28 = 1;
                    Type = 0;
                    *(_DWORD *)Data = 0;
                    cbData = 4;
                    if ( !RegQueryValueExW(hKey, L"DontAddIncomingSPPInWizard", 0, &Type, Data, &cbData)
                      && Type == 4
                      && cbData == 4 )
                    {
                      v28 = *(_DWORD *)Data == 0;
                    }
                    RegCloseKey(hKey);
                    if ( v28 )
                    {
LABEL_59:
                      v29 = 0;
                      while ( 1 )
                      {
                        memset_0(SubKey, 0, 0x410u);
                        if ( Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(
                               0,
                               v30,
                               (const struct _GUID *)v29,
                               (unsigned int)SubKey,
                               phkResulta)
                          || !*(_DWORD *)SubKey )
                        {
                          break;
                        }
                        if ( ++v29 >= 0xFF )
                          goto LABEL_65;
                      }
                      Microsoft::Bluetooth::Services::BthServ::InstallIncomingComPort(
                        (Microsoft::Bluetooth::Services::BthServ *)&v58.stLastSeen.wHour,
                        (const struct _BLUETOOTH_DEVICE_INFO *)v29,
                        (unsigned int)v13);
                    }
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (LOBYTE(v25) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
                  {
                    LOBYTE(v25) = 0;
                  }
                  if ( (_BYTE)v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_s_guid_i(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v25,
                      v26,
                      *((_QWORD *)WPP_GLOBAL_Control + 5),
                      (_DWORD)phkResulta,
                      lpcbData,
                      13,
                      (_DWORD)lpOverlapped,
                      v48,
                      (__int64)&Buf1,
                      a2[1]);
                  }
                  Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
                    this,
                    &v58.stLastSeen.wHour,
                    0,
                    (unsigned int)&Buf1,
                    (const struct _GUID *)phkResulta,
                    lpcbData,
                    lpBytesReturned,
                    (unsigned __int8)lpOverlapped,
                    v48,
                    v49[0],
                    v50);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (LOBYTE(v24) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
                {
                  LOBYTE(v24) = 0;
                }
                LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                if ( (_BYTE)v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_AND_TRACE_SF_s_guid_i(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v24,
                    (_DWORD)v13,
                    *((_QWORD *)WPP_GLOBAL_Control + 5),
                    (_DWORD)phkResulta,
                    lpcbData,
                    12,
                    (_DWORD)lpOverlapped,
                    v48,
                    (__int64)&Buf1,
                    a2[1]);
              }
            }
          }
        }
      }
    }
LABEL_65:
    ;
  }
  while ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
                          FirstServiceInternal,
                          &v59,
                          v13) );
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(FirstServiceInternal, v31);
  v32 = a2[1];
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v7 = 0;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  hKey = 0;
  v34 = BthDevnodeOpenInterfaceHandle((__int64)v33, 0, &hKey);
  if ( v34 >= 0 )
  {
    memset_0(SubKey, 0, 0x72Au);
    *(_QWORD *)SubKey = v32;
    v67 = 128;
    *(_DWORD *)Data = 0;
    v38 = hKey;
    if ( !DeviceIoControl(hKey, 0x411030u, SubKey, 0x72Au, 0, 0, (LPDWORD)Data, 0) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v39, v40, v41);
    if ( (unsigned __int64)v38 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v37 = v38;
      goto LABEL_79;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(retaddr, v35, v36, (const char *)(unsigned int)v34, (int)phkResulta);
    v37 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_79:
      CloseHandle(v37);
  }
  return 0;
}

```

## disassembly

```asm
0x1800237e8  mov     [rsp-8+arg_10], rbx
0x1800237ed  push    rbp
0x1800237ee  push    rsi
0x1800237ef  push    rdi
0x1800237f0  push    r12
0x1800237f2  push    r13
0x1800237f4  push    r14
0x1800237f6  push    r15
0x1800237f8  lea     rbp, [rsp-0F00h]
0x180023800  mov     eax, 1000h
0x180023805  call    _alloca_probe
0x18002380a  sub     rsp, rax
0x18002380d  mov     rax, cs:__security_cookie
0x180023814  xor     rax, rsp
0x180023817  mov     [rbp+0F30h+var_40], rax
0x18002381e  mov     r15, rdx
0x180023821  mov     r13, rcx
0x180023824  mov     ebx, 230h
0x180023829  mov     r8d, ebx; Size
0x18002382c  xor     edx, edx; Val
0x18002382e  lea     rcx, [rbp+0F30h+var_F98.stLastSeen.wHour]; void *
0x180023832  call    memset_0
0x180023837  mov     rax, [r15+8]
0x18002383b  mov     qword ptr [rbp+0F30h+var_F98.stLastUsed.wYear], rax
0x18002383f  mov     dword ptr [rbp+0F30h+var_F98.stLastSeen.wHour], ebx
0x180023842  xor     r14d, r14d
0x180023845  mov     qword ptr [rsp+1030h+Buf1], 20h ; ' '
0x18002384e  mov     [rbp+0F30h+var_FA0], r14
0x180023852  lea     rax, [rbp+0F30h+var_F98.stLastSeen.wHour]
0x180023856  mov     qword ptr [rbp+0F30h+Buf1+8], rax
0x18002385a  mov     [rbp+0F30h+var_FA8], r13
0x18002385e  xor     edx, edx; Val
0x180023860  mov     r8d, 5C4h; Size
0x180023866  lea     rcx, [rbp+0F30h+var_D3C]; void *
0x18002386d  call    memset_0
0x180023872  mov     [rbp+0F30h+var_D40], 5C8h
0x18002387c  mov     bl, r14b
0x18002387f  lea     edi, [r14+1]
0x180023883  cmp     bl, dil
0x180023886  jnb     loc_180023EA6
0x18002388c  mov     r8d, edi
0x18002388f  lea     rdx, [rbp+0F30h+var_D40]
0x180023896  lea     rcx, [rsp+1030h+Buf1]
0x18002389b  call    ?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x1800238a0  mov     r12, rax
0x1800238a3  add     bl, dil
0x1800238a6  test    rax, rax
0x1800238a9  jz      short loc_180023883
0x1800238ab  xorps   xmm0, xmm0
0x1800238ae  movups  xmmword ptr [rbp+0F30h+var_F98.dwSize], xmm0
0x1800238b2  movups  xmmword ptr [rbp+0F30h+var_F98.Address+4], xmm0
0x1800238b6  mov     r9d, edi; struct _BTH_PNP_INFO *
0x1800238b9  lea     r8, [rbp+0F30h+var_F98]; struct _BLUETOOTH_DEVICE_INFO *
0x1800238bd  mov     rdx, r15; void *
0x1800238c0  mov     rcx, r13; this
0x1800238c3  call    ?BthpFindPnpInfo@BthServ@Services@Bluetooth@Microsoft@@YAXPEAXPEBU_BLUETOOTH_DEVICE_INFO@@PEAU_BTH_PNP_INFO@@H@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(void *,_BLUETOOTH_DEVICE_INFO const *,_BTH_PNP_INFO *,int)
0x1800238c8  mov     eax, [rbp+0F30h+var_F98.fRemembered]
0x1800238cb  and     eax, 0Fh
0x1800238ce  lea     rsi, WPP_GLOBAL_Control
0x1800238d5  lea     rbx, WPP_RECORDER_INITIALIZED
0x1800238dc  cmp     al, 0Fh
0x1800238de  jz      short loc_18002393C
0x1800238e0  mov     rcx, r15; this
0x1800238e3  call    ?BthpFindAndStampPnpInfoFromServiceSearch@BthServ@Services@Bluetooth@Microsoft@@YAJPEBU_BLUETOOTH_DEVICE_INFO@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindAndStampPnpInfoFromServiceSearch(_BLUETOOTH_DEVICE_INFO const *)
0x1800238e8  test    eax, eax
0x1800238ea  jns     short loc_18002393C
0x1800238ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238f3  cmp     rcx, rsi
0x1800238f6  jz      short loc_180023901
0x1800238f8  cmp     byte ptr [rcx+19h], 3
0x1800238fc  mov     dl, dil
0x1800238ff  jnb     short loc_180023904
0x180023901  mov     dl, r14b
0x180023904  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18002390b  setnz   r8b
0x18002390f  test    dl, dl
0x180023911  jnz     short loc_180023918
0x180023913  test    r8b, r8b
0x180023916  jz      short loc_18002393C
0x180023918  mov     dword ptr [rsp+1030h+var_FE8], eax
0x18002391c  lea     r10, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180023923  mov     [rsp+1030h+lpOverlapped], r10; unsigned __int8
0x180023928  mov     word ptr [rsp+1030h+lpBytesReturned], 0Bh
0x18002392f  mov     r9, [rcx+28h]
0x180023933  mov     rcx, [rcx+10h]
0x180023937  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002393c  mov     eax, 0Dh
0x180023941  xorps   xmm0, xmm0
0x180023944  movups  [rsp+1030h+Buf1], xmm0
0x180023949  cmp     [rbp+0F30h+var_D40], 5C8h
0x180023953  jz      short loc_180023965
0x180023955  mov     ecx, 51Ah; dwErrCode
0x18002395a  call    cs:__imp_SetLastError
0x180023960  jmp     loc_180023D5D
0x180023965  mov     ecx, eax; dwErrCode
0x180023967  call    cs:__imp_SetLastError
0x18002396d  test    [rbp+0F30h+var_D2C], 2
0x180023974  jz      loc_180023D5D
0x18002397a  mov     rsi, [rbp+0F30h+var_D20]
0x180023981  test    rsi, rsi
0x180023984  jz      loc_180023D56
0x18002398a  mov     al, [rsi]
0x18002398c  and     al, 0F8h
0x18002398e  cmp     al, 30h ; '0'
0x180023990  jnz     loc_180023D56
0x180023996  call    cs:__imp_GetProcessHeap
0x18002399c  mov     rcx, rax; hHeap
0x18002399f  xor     edx, edx; dwFlags
0x1800239a1  lea     r8d, [rdx+18h]; dwBytes
0x1800239a5  call    cs:__imp_HeapAlloc
0x1800239ab  mov     rbx, rax
0x1800239ae  test    rax, rax
0x1800239b1  jz      loc_180023D56
0x1800239b7  mov     [rsp+1030h+Type], r14d
0x1800239bc  mov     edx, [rbp+0F30h+var_D30]
0x1800239c2  add     rdx, [rbp+0F30h+var_D38]; struct _BLUETOOTH_SDP_RECORD *
0x1800239c9  lea     r8, [rsp+1030h+Type]; void *
0x1800239ce  mov     rcx, rsi; this
0x1800239d1  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x1800239d6  mov     [rbx], rax
0x1800239d9  test    rax, rax
0x1800239dc  jz      short loc_180023A0C
0x1800239de  mov     ecx, [rsp+1030h+Type]
0x1800239e2  add     rcx, rax
0x1800239e5  mov     [rbx+8], rcx
0x1800239e9  lea     rdx, [rsp+1030h+Buf1]; void *
0x1800239ee  mov     rcx, rbx; this
0x1800239f1  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x1800239f6  test    eax, eax
0x1800239f8  jnz     short loc_180023A07
0x1800239fa  call    cs:__imp_GetLastError
0x180023a00  mov     r14d, eax
0x180023a03  xor     esi, esi
0x180023a05  jmp     short loc_180023A15
0x180023a07  mov     rsi, rbx
0x180023a0a  jmp     short loc_180023A29
0x180023a0c  mov     rsi, r14
0x180023a0f  mov     r14d, 490h
0x180023a15  call    cs:__imp_GetProcessHeap
0x180023a1b  mov     rcx, rax; hHeap
0x180023a1e  mov     r8, rbx; lpMem
0x180023a21  xor     edx, edx; dwFlags
0x180023a23  call    cs:__imp_HeapFree
0x180023a29  mov     ecx, r14d; dwErrCode
0x180023a2c  call    cs:__imp_SetLastError
0x180023a32  xor     r14d, r14d
0x180023a35  test    rsi, rsi
0x180023a38  jz      loc_180023D56
0x180023a3e  mov     rcx, rsi; this
0x180023a41  call    ?BluetoothFindClassIdClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(void *)
0x180023a46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x180023a4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x180023a52  test    al, al
0x180023a54  jnz     loc_180023B1B
0x180023a5a  mov     edx, 4
0x180023a5f  mov     eax, cs:_tls_index
0x180023a65  mov     rcx, gs:58h
0x180023a6e  mov     rax, [rcx+rax*8]
0x180023a72  mov     ecx, [rdx+rax]
0x180023a75  cmp     cs:dword_180044E1C, ecx
0x180023a7b  jg      loc_180023ED5
0x180023a81  lea     rax, xmmword_180044D30
0x180023a88  mov     rcx, qword ptr [rbp+0F30h+Buf1+8]
0x180023a8c  mov     rdx, qword ptr [rsp+1030h+Buf1]
0x180023a91  lea     rbx, __@@_PchSym_@00@KxulyqvxgPillgKxulmvxlivUwirevihUdwnUyofvgllgsUfhviUygshvieUhvieviUyofvgllgszkrhUoryUlyquivUznwGEUkxsOlyq@bthserv_bluetoothapis
0x180023a98  cmp     [rax], rdx
0x180023a9b  jnz     short loc_180023AA3
0x180023a9d  cmp     [rax+8], rcx
0x180023aa1  jz      short loc_180023AAC
0x180023aa3  add     rax, 10h
0x180023aa7  cmp     rax, rbx
0x180023aaa  jnz     short loc_180023A98
0x180023aac  cmp     rax, rbx
0x180023aaf  jz      short loc_180023B1B
0x180023ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ab8  lea     rsi, WPP_GLOBAL_Control
0x180023abf  cmp     rcx, rsi
0x180023ac2  jz      short loc_180023ACD
0x180023ac4  cmp     byte ptr [rcx+19h], 4
0x180023ac8  mov     dl, dil
0x180023acb  jnb     short loc_180023AD0
0x180023acd  mov     dl, r14b
0x180023ad0  lea     rax, WPP_RECORDER_INITIALIZED
0x180023ad7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180023ade  setnz   r8b
0x180023ae2  test    dl, dl
0x180023ae4  jnz     short loc_180023AEF
0x180023ae6  test    r8b, r8b
0x180023ae9  jz      loc_180023D5D
0x180023aef  mov     rax, [r15+8]
0x180023af3  mov     qword ptr [rsp+1030h+var_FE0], rax
0x180023af8  lea     rax, [rsp+1030h+Buf1]
0x180023afd  mov     qword ptr [rsp+1030h+var_FE8], rax
0x180023b02  mov     word ptr [rsp+1030h+lpBytesReturned], 0Ch
0x180023b09  mov     r9, [rcx+28h]
0x180023b0d  mov     rcx, [rcx+10h]
0x180023b11  call    WPP_RECORDER_AND_TRACE_SF_s_guid_i
0x180023b16  jmp     loc_180023D5D
0x180023b1b  mov     r8d, 10h; Size
0x180023b21  lea     rdx, SerialPortServiceClass_UUID; Buf2
0x180023b28  lea     rcx, [rsp+1030h+Buf1]; Buf1
0x180023b2d  call    memcmp_0
0x180023b32  test    eax, eax
0x180023b34  jz      short loc_180023BB0
0x180023b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b3d  lea     rsi, WPP_GLOBAL_Control
0x180023b44  cmp     rcx, rsi
0x180023b47  jz      short loc_180023B52
0x180023b49  cmp     byte ptr [rcx+19h], 4
0x180023b4d  mov     dl, dil
0x180023b50  jnb     short loc_180023B55
0x180023b52  mov     dl, r14b
0x180023b55  lea     rax, WPP_RECORDER_INITIALIZED
0x180023b5c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180023b63  setnz   r8b
0x180023b67  test    dl, dl
0x180023b69  jnz     short loc_180023B70
0x180023b6b  test    r8b, r8b
0x180023b6e  jz      short loc_180023B97
0x180023b70  mov     rax, [r15+8]
0x180023b74  mov     qword ptr [rsp+1030h+var_FE0], rax; unsigned __int8
0x180023b79  lea     rax, [rsp+1030h+Buf1]
0x180023b7e  mov     qword ptr [rsp+1030h+var_FE8], rax; unsigned __int8
0x180023b83  mov     word ptr [rsp+1030h+lpBytesReturned], 0Dh; void *
0x180023b8a  mov     r9, [rcx+28h]
0x180023b8e  mov     rcx, [rcx+10h]
0x180023b92  call    WPP_RECORDER_AND_TRACE_SF_s_guid_i
0x180023b97  lea     r9, [rsp+1030h+Buf1]; unsigned int
0x180023b9c  xor     r8d, r8d; struct _BLUETOOTH_DEVICE_INFO *
0x180023b9f  lea     rdx, [rbp+0F30h+var_F98.stLastSeen.wHour]; void *
0x180023ba3  mov     rcx, r13; this
0x180023ba6  call    ?BthpSetServiceStateEx@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@KPEBU_GUID@@K0EEEE@Z; Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(void *,_BLUETOOTH_DEVICE_INFO const *,ulong,_GUID const *,ulong,void *,uchar,uchar,uchar,uchar)
0x180023bab  jmp     loc_180023D5D
0x180023bb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bb7  lea     rsi, WPP_GLOBAL_Control
0x180023bbe  cmp     rcx, rsi
0x180023bc1  jz      short loc_180023BCC
0x180023bc3  cmp     byte ptr [rcx+19h], 4
0x180023bc7  mov     dl, dil
0x180023bca  jnb     short loc_180023BCF
0x180023bcc  mov     dl, r14b
0x180023bcf  lea     rax, WPP_RECORDER_INITIALIZED
0x180023bd6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180023bdd  setnz   r8b
0x180023be1  test    dl, dl
0x180023be3  jnz     short loc_180023BEA
0x180023be5  test    r8b, r8b
0x180023be8  jz      short loc_180023C13
0x180023bea  mov     rax, [r15+8]
0x180023bee  mov     qword ptr [rsp+1030h+var_FE8], rax; unsigned __int8
0x180023bf3  lea     rax, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180023bfa  mov     [rsp+1030h+lpOverlapped], rax; unsigned __int8
0x180023bff  mov     word ptr [rsp+1030h+lpBytesReturned], 0Eh; void *
0x180023c06  mov     r9, [rcx+28h]
0x180023c0a  mov     rcx, [rcx+10h]
0x180023c0e  call    WPP_RECORDER_AND_TRACE_SF_si
0x180023c13  xor     r9d, r9d; unsigned int
0x180023c16  mov     r8d, dword ptr [rbp+0F30h+var_D28]; struct _BLUETOOTH_DEVICE_INFO *
0x180023c1d  lea     rdx, [rbp+0F30h+var_F98.stLastSeen.wHour]; void *
0x180023c21  mov     rcx, r13; this
0x180023c24  call    ?BthpSetServiceStateEx@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@KPEBU_GUID@@K0EEEE@Z; Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(void *,_BLUETOOTH_DEVICE_INFO const *,ulong,_GUID const *,ulong,void *,uchar,uchar,uchar,uchar)
0x180023c29  test    eax, eax
0x180023c2b  jnz     loc_180023D5D
0x180023c31  mov     r9d, dword ptr [rbp+0F30h+var_F98.stLastUsed.wHour]
0x180023c35  mov     eax, r9d
0x180023c38  shr     eax, 2
0x180023c3b  and     eax, 3Fh
0x180023c3e  shr     r9d, 8
0x180023c42  and     r9d, 1Fh
0x180023c46  mov     dword ptr [rsp+1030h+phkResult], eax
0x180023c4a  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\BT"...
0x180023c51  mov     edx, 0B8h; unsigned __int64
0x180023c56  lea     rcx, [rbp+0F30h+SubKey]; unsigned __int16 *
0x180023c5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023c62  test    eax, eax
0x180023c64  js      loc_180023D08
0x180023c6a  mov     [rsp+1030h+hKey], r14
0x180023c6f  lea     rax, [rsp+1030h+hKey]
0x180023c74  mov     [rsp+1030h+phkResult], rax; phkResult
0x180023c79  mov     r9d, 20019h; samDesired
0x180023c7f  xor     r8d, r8d; ulOptions
0x180023c82  lea     rdx, [rbp+0F30h+SubKey]; lpSubKey
0x180023c89  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023c90  call    cs:__imp_RegOpenKeyExW
0x180023c96  test    eax, eax
0x180023c98  jnz     short loc_180023D08
0x180023c9a  mov     ebx, edi
0x180023c9c  mov     [rsp+1030h+Type], r14d
0x180023ca1  mov     dword ptr [rsp+1030h+Data], r14d
0x180023ca6  mov     [rsp+1030h+cbData], 4
0x180023cae  lea     rax, [rsp+1030h+cbData]
0x180023cb3  mov     [rsp+1030h+lpcbData], rax; lpcbData
0x180023cb8  lea     rax, [rsp+1030h+Data]
0x180023cbd  mov     [rsp+1030h+phkResult], rax; struct _BLUETOOTH_LOCAL_SERVICE_INFO *
0x180023cc2  lea     r9, [rsp+1030h+Type]; lpType
0x180023cc7  xor     r8d, r8d; lpReserved
0x180023cca  lea     rdx, aDontaddincomin; "DontAddIncomingSPPInWizard"
0x180023cd1  mov     rcx, [rsp+1030h+hKey]; hKey
0x180023cd6  call    cs:__imp_RegQueryValueExW
0x180023cdc  test    eax, eax
  ... truncated ...
```
