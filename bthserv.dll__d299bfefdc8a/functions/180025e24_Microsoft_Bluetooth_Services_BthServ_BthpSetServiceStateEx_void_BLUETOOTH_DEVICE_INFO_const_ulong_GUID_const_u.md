# Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(void *,_BLUETOOTH_DEVICE_INFO const *,ulong,_GUID const *,ulong,void *,uchar,uchar,uchar,uchar)

- ea: `0x180025e24`
- end: `0x1800262ff`
- name: `?BthpSetServiceStateEx@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@KPEBU_GUID@@K0EEEE@Z`
- size: `1243`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, unsigned __int64 *, const struct _BLUETOOTH_DEVICE_INFO *, _QWORD *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800237e8`
- `0x180025e24`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x1800115ec`
- `0x18001413c`
- `0x1800155c0`
- `0x180022af0`
- `0x180022b34`
- `0x180022d0c`
- `0x180022d74`
- `0x180022f30`
- `0x180023158`
- `0x1800231ac`
- `0x1800248ac`
- `0x180024bd4`
- `0x180024ca8`
- `0x180024e1c`
- `0x180025e24`
- `0x180032c44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025fba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800261b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025fba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800261b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025fab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026027`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002624d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800262c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025fab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026027`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002624d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800262c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026035`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002625b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800262d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026035`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002625b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800262d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002600c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002600c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026220`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002603e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026232`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025f82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002603e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800262a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800262a5`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800261d4`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800261d4`
- `DEVOBJ!DevObjGetClassDevs` at `0x180026205`
- `DEVOBJ!DevObjGetClassDevs` at `0x180026205`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180026247`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180026247`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
        Microsoft::Bluetooth::Services::BthServ *this,
        unsigned __int64 *a2,
        const struct _BLUETOOTH_DEVICE_INFO *a3,
        _QWORD *a4)
{
  Microsoft::Bluetooth::Services::BthServ *v4; // r14
  unsigned int v5; // ebx
  unsigned __int64 *v7; // r13
  unsigned int SDPPriLangServiceName; // edi
  struct _BLUETOOTH_SERVICE_RECORD *v10; // r8
  Microsoft::Bluetooth::Services::BthServ *v11; // rsi
  HANDLE v12; // rax
  Microsoft::Bluetooth::Services::BthServ *v13; // rbx
  unsigned int *v14; // r9
  struct _BLUETOOTH_SDP_RECORD *v15; // rax
  struct _GUID *v16; // r8
  struct _GUID *v17; // r9
  Microsoft::Bluetooth::Services::BthServ *v18; // rsi
  HANDLE v19; // rax
  void *v20; // rdx
  struct _GUID *v21; // r9
  bool v22; // zf
  void *v23; // rdx
  void *v24; // rcx
  char *v25; // r8
  void *v26; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v28; // rsi
  __int64 DeviceInfoList; // rax
  void **v30; // r8
  DWORD LastError; // ebx
  void *v32; // rdx
  HANDLE v33; // rax
  void **v34; // r8
  void *v35; // rdx
  HANDLE v36; // rax
  struct _GUID *v38; // [rsp+20h] [rbp-E0h]
  void *v39; // [rsp+30h] [rbp-D0h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  struct _BLUETOOTH_DEVICE_INFO *v41; // [rsp+58h] [rbp-A8h]
  Microsoft::Bluetooth::Services::BthServ *FirstServiceInternal; // [rsp+60h] [rbp-A0h]
  struct _BLUETOOTH_DEVICE_INFO v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v44[8]; // [rsp+680h] [rbp+580h] BYREF
  char v45[4]; // [rsp+688h] [rbp+588h] BYREF
  int v46; // [rsp+68Ch] [rbp+58Ch]
  WORD wYear; // [rsp+690h] [rbp+590h]
  WORD wMonth; // [rsp+692h] [rbp+592h]
  WORD wDayOfWeek; // [rsp+696h] [rbp+596h]
  __int128 Buf2; // [rsp+6AAh] [rbp+5AAh] BYREF
  char v51[1782]; // [rsp+6BAh] [rbp+5BAh] BYREF

  v4 = 0;
  v5 = (unsigned int)a3;
  LODWORD(v41) = (_DWORD)a3;
  v7 = a2;
  if ( a4 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(a2) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
    {
      LOBYTE(a2) = 0;
    }
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      BYTE1(v39) = 0;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s_guid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
  }
  SDPPriLangServiceName = 1060;
  if ( !this )
  {
    hObject = 0;
    ProcessHeap = GetProcessHeap();
    v28 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( v28 )
    {
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      v28[1] = DeviceInfoList;
      if ( DeviceInfoList == -1 )
      {
        v36 = GetProcessHeap();
        HeapFree(v36, 0, v28);
      }
      else
      {
        if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
        {
          if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                               (Microsoft::Bluetooth::Services::BthServ *)v28,
                               &hObject,
                               v30) )
          {
            v4 = (Microsoft::Bluetooth::Services::BthServ *)v28;
          }
          else
          {
            LastError = GetLastError();
            Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
              (Microsoft::Bluetooth::Services::BthServ *)v28,
              v32);
            SetLastError(LastError);
            v5 = (unsigned int)v41;
          }
        }
        else
        {
          DevObjDestroyDeviceInfoList(v28[1]);
          v33 = GetProcessHeap();
          HeapFree(v33, 0, v28);
        }
        if ( v4 )
        {
          do
          {
            LOBYTE(v39) = 1;
            LODWORD(v38) = 1;
            SDPPriLangServiceName = Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(
                                      (Microsoft::Bluetooth::Services::BthServ *)hObject,
                                      v7,
                                      (const struct _BLUETOOTH_DEVICE_INFO *)v5,
                                      (unsigned int)a4,
                                      v38,
                                      0,
                                      v39,
                                      0,
                                      0,
                                      1u,
                                      (unsigned __int8)hObject);
            CloseHandle(hObject);
          }
          while ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v4, &hObject, v34) );
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v4, v35);
        }
      }
    }
    return SDPPriLangServiceName;
  }
  memset_0(v45, 0, 0x722u);
  *(_QWORD *)v44 = v7[1];
  v46 = 17;
  memset_0(&v43.szName[2], 0, 0x5C4u);
  *(_QWORD *)&v43.dwSize = 32;
  memset(&v43.fRemembered, 0, 36);
  v43.Address.ullLong = (BTH_ADDR)v7;
  *(_QWORD *)&v43.ulClassofDevice = this;
  wcscpy(v43.szName, L"\xD7\x88");
  FirstServiceInternal = (Microsoft::Bluetooth::Services::BthServ *)Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
                                                                      (__int64)&v43,
                                                                      v43.szName,
                                                                      2u);
  if ( !FirstServiceInternal )
    return SDPPriLangServiceName;
  while ( 1 )
  {
    *(_OWORD *)&v43.dwSize = 0;
    if ( *(_DWORD *)v43.szName != 1480 )
    {
      SetLastError(0x51Au);
      goto LABEL_28;
    }
    SetLastError(0xDu);
    if ( (v43.szName[10] & 2) == 0 )
      goto LABEL_28;
    v11 = *(Microsoft::Bluetooth::Services::BthServ **)&v43.szName[16];
    if ( !*(_QWORD *)&v43.szName[16] )
      goto LABEL_28;
    if ( (**(_BYTE **)&v43.szName[16] & 0xF8) != 0x30 )
      goto LABEL_28;
    v12 = GetProcessHeap();
    v13 = (Microsoft::Bluetooth::Services::BthServ *)HeapAlloc(v12, 0, 0x18u);
    if ( !v13 )
      goto LABEL_28;
    LODWORD(hObject) = 0;
    v15 = Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
            v11,
            (struct _BLUETOOTH_SDP_RECORD *)(*(_QWORD *)&v43.szName[4] + *(unsigned int *)&v43.szName[8]),
            (unsigned __int32 *)&hObject,
            v14);
    *(_QWORD *)v13 = v15;
    if ( v15 )
    {
      *((_QWORD *)v13 + 1) = (char *)v15 + (unsigned int)hObject;
      if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(
                           (Microsoft::Bluetooth::Services::BthServ **)v13,
                           (struct _BLUETOOTH_SDP_RECORD *)&v43,
                           v16,
                           v17) )
      {
        v18 = v13;
        goto LABEL_22;
      }
      LODWORD(v4) = GetLastError();
      v18 = 0;
    }
    else
    {
      v18 = 0;
      LODWORD(v4) = 1168;
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v13);
LABEL_22:
    SetLastError((DWORD)v4);
    LODWORD(v4) = 0;
    if ( !v18 )
      goto LABEL_28;
    Buf2 = *(_OWORD *)&v43.dwSize;
    Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(v18, v20);
    if ( !a4 )
      break;
    if ( (_QWORD)Buf2 == *a4 )
    {
      v22 = *((_QWORD *)&Buf2 + 1) == a4[1];
      goto LABEL_27;
    }
LABEL_28:
    if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(
                          FirstServiceInternal,
                          (char *)v43.szName,
                          v10) )
      goto LABEL_40;
  }
  v22 = *(_DWORD *)&v43.szName[12] == (_DWORD)v41;
LABEL_27:
  if ( !v22 )
    goto LABEL_28;
  *(_OWORD *)&v43.dwSize = Buf2;
  if ( Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(this, v7, &v43, v21) )
  {
    Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(
      this,
      v7,
      (const struct _BLUETOOTH_DEVICE_INFO *)&v43.stLastSeen,
      0);
    if ( (v43.stLastUsed.wHour & 0xF) == 0xF )
    {
      v46 |= 4u;
      wDayOfWeek = v43.stLastSeen.wDayOfWeek;
      wYear = v43.stLastSeen.wYear;
      wMonth = v43.stLastSeen.wMonth;
    }
    if ( *(_DWORD *)v7 >= 0x230u )
    {
      SDPPriLangServiceName = BthServClientActivateService(
                                v24,
                                v7 + 1,
                                *(unsigned int *)&v43.szName[8],
                                *(unsigned __int8 *const *)&v43.szName[4]);
      if ( !SDPPriLangServiceName )
      {
        SDPPriLangServiceName = Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(
                                  (Microsoft::Bluetooth::Services::BthServ *)v43.szName,
                                  (const struct _BLUETOOTH_SERVICE_RECORD *)v51,
                                  v25);
        if ( SDPPriLangServiceName )
        {
          if ( memcmp_0(&SerialPortServiceClass_UUID, &Buf2, 0x10u) )
            SDPPriLangServiceName = 0;
        }
      }
    }
    else
    {
      SDPPriLangServiceName = 122;
    }
  }
  else
  {
    SDPPriLangServiceName = 1058;
  }
LABEL_40:
  Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose((void **)FirstServiceInternal, v23);
  if ( !SDPPriLangServiceName )
    return BthServClientUpdateService(v26, 0x72Au, v44, 0);
  return SDPPriLangServiceName;
}

```

## disassembly

```asm
0x180025e24  push    rbp
0x180025e26  push    rbx
0x180025e27  push    rsi
0x180025e28  push    rdi
0x180025e29  push    r12
0x180025e2b  push    r13
0x180025e2d  push    r14
0x180025e2f  push    r15
0x180025e31  lea     rbp, [rsp-0CC8h]
0x180025e39  sub     rsp, 0DC8h
0x180025e40  mov     rax, cs:__security_cookie
0x180025e47  xor     rax, rsp
0x180025e4a  mov     [rbp+0D00h+var_50], rax
0x180025e51  xor     r14d, r14d
0x180025e54  mov     ebx, r8d
0x180025e57  mov     dword ptr [rsp+0E00h+var_DA8], ebx
0x180025e5b  mov     r15, r9
0x180025e5e  mov     r13, rdx
0x180025e61  mov     r12, rcx
0x180025e64  mov     esi, 10h
0x180025e69  test    r9, r9
0x180025e6c  jz      short loc_180025ECA
0x180025e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e75  lea     rax, WPP_GLOBAL_Control
0x180025e7c  cmp     rcx, rax
0x180025e7f  jz      short loc_180025E89
0x180025e81  cmp     byte ptr [rcx+19h], 4
0x180025e85  mov     dl, 1
0x180025e87  jnb     short loc_180025E8C
0x180025e89  mov     dl, r14b
0x180025e8c  lea     rax, WPP_RECORDER_INITIALIZED
0x180025e93  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180025e9a  setnz   r8b
0x180025e9e  test    dl, dl
0x180025ea0  jnz     short loc_180025EA7
0x180025ea2  test    r8b, r8b
0x180025ea5  jz      short loc_180025ECA
0x180025ea7  mov     r9, [rcx+28h]
0x180025eab  lea     rax, WPP_b232bbd09fa63021a92d957d702a2cb3_Traceguids
0x180025eb2  mov     rcx, [rcx+10h]
0x180025eb6  mov     qword ptr [rsp+0E00h+var_DB8], r15
0x180025ebb  mov     qword ptr [rsp+0E00h+var_DC8], rax
0x180025ec0  mov     word ptr [rsp+0E00h+var_DD0], si
0x180025ec5  call    WPP_RECORDER_AND_TRACE_SF_s_guid_
0x180025eca  mov     edi, 424h
0x180025ecf  test    r12, r12
0x180025ed2  jz      loc_18002619D
0x180025ed8  xorps   xmm0, xmm0
0x180025edb  lea     rcx, [rbp+0D00h+var_778]; void *
0x180025ee2  movups  xmmword ptr [rbp+0D00h+var_D90.stLastSeen.wYear], xmm0
0x180025ee6  xor     edx, edx; Val
0x180025ee8  mov     r8d, 722h; Size
0x180025eee  movups  xmmword ptr [rbp+0D00h+var_D90.stLastSeen.wSecond], xmm0
0x180025ef2  call    memset_0
0x180025ef7  mov     rax, [r13+8]
0x180025efb  lea     rcx, [rbp+0D00h+var_D90.szName+4]; void *
0x180025eff  xor     edx, edx; Val
0x180025f01  mov     qword ptr [rbp+0D00h+var_780], rax
0x180025f08  mov     r8d, 5C4h; Size
0x180025f0e  mov     [rbp+0D00h+var_774], 11h
0x180025f18  call    memset_0
0x180025f1d  mov     r8d, 2
0x180025f23  mov     qword ptr [rsp+0E00h+var_D90.dwSize], 20h ; ' '
0x180025f2c  lea     rdx, [rbp+0D00h+var_D90.szName]
0x180025f30  mov     qword ptr [rbp+0D00h+var_D90.fRemembered], r14
0x180025f34  lea     rcx, [rsp+0E00h+var_D90]
0x180025f39  mov     qword ptr [rsp+0E00h+var_D90.Address], r13
0x180025f3e  mov     qword ptr [rbp+0D00h+var_D90.ulClassofDevice], r12
0x180025f42  mov     dword ptr [rbp+0D00h+var_D90.szName], 5C8h
0x180025f49  call    ?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x180025f4e  mov     [rsp+0E00h+var_DA0], rax
0x180025f53  test    rax, rax
0x180025f56  jz      loc_1800262DA
0x180025f5c  cmp     dword ptr [rbp+0D00h+var_D90.szName], 5C8h
0x180025f63  xorps   xmm0, xmm0
0x180025f66  movups  xmmword ptr [rsp+0E00h+var_D90.dwSize], xmm0
0x180025f6b  jz      short loc_180025F7D
0x180025f6d  mov     ecx, 51Ah; dwErrCode
0x180025f72  call    cs:__imp_SetLastError
0x180025f78  jmp     loc_180026088
0x180025f7d  mov     ecx, 0Dh; dwErrCode
0x180025f82  call    cs:__imp_SetLastError
0x180025f88  test    byte ptr [rbp+0D00h+var_D90.szName+14h], 2
0x180025f8c  jz      loc_180026088
0x180025f92  mov     rsi, qword ptr [rbp+0D00h+var_D90.szName+20h]
0x180025f96  test    rsi, rsi
0x180025f99  jz      loc_180026088
0x180025f9f  mov     al, [rsi]
0x180025fa1  and     al, 0F8h
0x180025fa3  cmp     al, 30h ; '0'
0x180025fa5  jnz     loc_180026088
0x180025fab  call    cs:__imp_GetProcessHeap
0x180025fb1  xor     edx, edx; dwFlags
0x180025fb3  mov     rcx, rax; hHeap
0x180025fb6  lea     r8d, [rdx+18h]; dwBytes
0x180025fba  call    cs:__imp_HeapAlloc
0x180025fc0  mov     rbx, rax
0x180025fc3  test    rax, rax
0x180025fc6  jz      loc_180026088
0x180025fcc  mov     edx, dword ptr [rbp+0D00h+var_D90.szName+10h]
0x180025fcf  lea     r8, [rsp+0E00h+hObject]; void *
0x180025fd4  add     rdx, qword ptr [rbp+0D00h+var_D90.szName+8]; struct _BLUETOOTH_SDP_RECORD *
0x180025fd8  mov     rcx, rsi; this
0x180025fdb  mov     dword ptr [rsp+0E00h+hObject], r14d
0x180025fe0  call    ?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)
0x180025fe5  mov     [rbx], rax
0x180025fe8  mov     rcx, rax
0x180025feb  test    rax, rax
0x180025fee  jz      short loc_18002601E
0x180025ff0  mov     eax, dword ptr [rsp+0E00h+hObject]
0x180025ff4  lea     rdx, [rsp+0E00h+var_D90]; void *
0x180025ff9  add     rax, rcx
0x180025ffc  mov     rcx, rbx; this
0x180025fff  mov     [rbx+8], rax
0x180026003  call    ?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)
0x180026008  test    eax, eax
0x18002600a  jnz     short loc_180026019
0x18002600c  call    cs:__imp_GetLastError
0x180026012  mov     r14d, eax
0x180026015  xor     esi, esi
0x180026017  jmp     short loc_180026027
0x180026019  mov     rsi, rbx
0x18002601c  jmp     short loc_18002603B
0x18002601e  mov     rsi, r14
0x180026021  mov     r14d, 490h
0x180026027  call    cs:__imp_GetProcessHeap
0x18002602d  mov     r8, rbx; lpMem
0x180026030  xor     edx, edx; dwFlags
0x180026032  mov     rcx, rax; hHeap
0x180026035  call    cs:__imp_HeapFree
0x18002603b  mov     ecx, r14d; dwErrCode
0x18002603e  call    cs:__imp_SetLastError
0x180026044  xor     r14d, r14d
0x180026047  test    rsi, rsi
0x18002604a  jz      short loc_180026088
0x18002604c  movups  xmm0, xmmword ptr [rsp+0E00h+var_D90.dwSize]
0x180026051  mov     rcx, rsi; this
0x180026054  movdqu  [rbp+0D00h+Buf2], xmm0
0x18002605c  call    ?BluetoothFindClassIdClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindClassIdClose(void *)
0x180026061  test    r15, r15
0x180026064  jz      short loc_18002607F
0x180026066  mov     rax, qword ptr [rbp+0D00h+Buf2]
0x18002606d  cmp     rax, [r15]
0x180026070  jnz     short loc_180026088
0x180026072  mov     rax, qword ptr [rbp+0D00h+Buf2+8]
0x180026079  cmp     rax, [r15+8]
0x18002607d  jmp     short loc_180026086
0x18002607f  mov     eax, dword ptr [rsp+0E00h+var_DA8]
0x180026083  cmp     dword ptr [rbp+0D00h+var_D90.szName+18h], eax
0x180026086  jz      short loc_1800260A3
0x180026088  mov     rcx, [rsp+0E00h+var_DA0]; this
0x18002608d  lea     rdx, [rbp+0D00h+var_D90.szName]; void *
0x180026091  call    ?BluetoothFindNextService@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_BLUETOOTH_SERVICE_RECORD@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextService(void *,_BLUETOOTH_SERVICE_RECORD *)
0x180026096  test    eax, eax
0x180026098  jnz     loc_180025F5C
0x18002609e  jmp     loc_180026170
0x1800260a3  movups  xmm0, [rbp+0D00h+Buf2]
0x1800260aa  lea     r8, [rsp+0E00h+var_D90]; struct _BLUETOOTH_DEVICE_INFO *
0x1800260af  mov     rdx, r13; void *
0x1800260b2  mov     rcx, r12; this
0x1800260b5  movdqu  xmmword ptr [rsp+0E00h+var_D90.dwSize], xmm0
0x1800260bb  call    ?BthpIsTopOfServiceGroup@BthServ@Services@Bluetooth@Microsoft@@YAEPEAXPEBU_BLUETOOTH_DEVICE_INFO@@U_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpIsTopOfServiceGroup(void *,_BLUETOOTH_DEVICE_INFO const *,_GUID)
0x1800260c0  test    al, al
0x1800260c2  jnz     short loc_1800260CE
0x1800260c4  mov     edi, 422h
0x1800260c9  jmp     loc_180026170
0x1800260ce  xor     r9d, r9d; struct _BTH_PNP_INFO *
0x1800260d1  lea     r8, [rbp+0D00h+var_D90.stLastSeen]; struct _BLUETOOTH_DEVICE_INFO *
0x1800260d5  mov     rdx, r13; void *
0x1800260d8  mov     rcx, r12; this
0x1800260db  call    ?BthpFindPnpInfo@BthServ@Services@Bluetooth@Microsoft@@YAXPEAXPEBU_BLUETOOTH_DEVICE_INFO@@PEAU_BTH_PNP_INFO@@H@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindPnpInfo(void *,_BLUETOOTH_DEVICE_INFO const *,_BTH_PNP_INFO *,int)
0x1800260e0  mov     eax, dword ptr [rbp+0D00h+var_D90.stLastUsed.wHour]
0x1800260e3  and     eax, 0Fh
0x1800260e6  cmp     al, 0Fh
0x1800260e8  jnz     short loc_180026112
0x1800260ea  movzx   eax, [rbp+0D00h+var_D90.stLastSeen.wDayOfWeek]
0x1800260ee  or      [rbp+0D00h+var_774], 4
0x1800260f5  mov     [rbp+0D00h+var_76A], ax
0x1800260fc  movzx   eax, [rbp+0D00h+var_D90.stLastSeen.wYear]
0x180026100  mov     [rbp+0D00h+var_770], ax
0x180026107  movzx   eax, [rbp+0D00h+var_D90.stLastSeen.wMonth]
0x18002610b  mov     [rbp+0D00h+var_76E], ax
0x180026112  cmp     dword ptr [r13+0], 230h
0x18002611a  jnb     short loc_180026123
0x18002611c  mov     edi, 7Ah ; 'z'
0x180026121  jmp     short loc_180026170
0x180026123  mov     r9, qword ptr [rbp+0D00h+var_D90.szName+8]; unsigned __int8 *
0x180026127  lea     rdx, [r13+8]; unsigned __int64 *
0x18002612b  mov     r8d, dword ptr [rbp+0D00h+var_D90.szName+10h]; unsigned int
0x18002612f  call    ?BthServClientActivateService@@YAKQEAXPEB_KKQEAE@Z; BthServClientActivateService(void * const,unsigned __int64 const *,ulong,uchar * const)
0x180026134  mov     edi, eax
0x180026136  test    eax, eax
0x180026138  jnz     short loc_180026170
0x18002613a  lea     rdx, [rbp+0D00h+var_746]; struct _BLUETOOTH_SERVICE_RECORD *
0x180026141  lea     rcx, [rbp+0D00h+var_D90.szName]; this
0x180026145  call    ?BthpFindSDPPriLangServiceName@BthServ@Services@Bluetooth@Microsoft@@YAKPEBU_BLUETOOTH_SERVICE_RECORD@@PEADK@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(_BLUETOOTH_SERVICE_RECORD const *,char *,ulong)
0x18002614a  mov     edi, eax
0x18002614c  test    eax, eax
0x18002614e  jz      short loc_180026170
0x180026150  mov     r8d, 10h; Size
0x180026156  lea     rdx, [rbp+0D00h+Buf2]; Buf2
0x18002615d  lea     rcx, SerialPortServiceClass_UUID; Buf1
0x180026164  call    memcmp_0
0x180026169  test    eax, eax
0x18002616b  jz      short loc_180026170
0x18002616d  mov     edi, r14d
0x180026170  mov     rcx, [rsp+0E00h+var_DA0]; this
0x180026175  call    ?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)
0x18002617a  test    edi, edi
0x18002617c  jnz     loc_1800262DA
0x180026182  xor     r9d, r9d; int
0x180026185  lea     r8, [rbp+0D00h+var_780]; unsigned __int8 *
0x18002618c  mov     edx, 72Ah; unsigned int
0x180026191  call    ?BthServClientUpdateService@@YAKPEAXKQEAEH@Z; BthServClientUpdateService(void *,ulong,uchar * const,int)
0x180026196  mov     edi, eax
0x180026198  jmp     loc_1800262DA
0x18002619d  mov     [rsp+0E00h+hObject], r14; unsigned __int8
0x1800261a2  call    cs:__imp_GetProcessHeap
0x1800261a8  mov     r8, rsi; dwBytes
0x1800261ab  mov     edx, 8; dwFlags
0x1800261b0  mov     rcx, rax; hHeap
0x1800261b3  call    cs:__imp_HeapAlloc
0x1800261b9  mov     rsi, rax
0x1800261bc  test    rax, rax
0x1800261bf  jz      loc_1800262DA
0x1800261c5  xor     r9d, r9d
0x1800261c8  mov     [rsp+0E00h+var_DE0], r14
0x1800261cd  xor     r8d, r8d
0x1800261d0  xor     edx, edx
0x1800261d2  xor     ecx, ecx
0x1800261d4  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800261da  mov     [rsi+8], rax
0x1800261de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800261e2  jz      loc_1800262C6
0x1800261e8  mov     qword ptr [rsp+0E00h+var_DD8], r14
0x1800261ed  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x1800261f4  mov     r9d, 12h
0x1800261fa  mov     [rsp+0E00h+var_DE0], r14
0x1800261ff  xor     r8d, r8d
0x180026202  mov     rcx, rax
0x180026205  call    cs:__imp_DevObjGetClassDevs
0x18002620b  test    eax, eax
0x18002620d  jz      short loc_180026243
0x18002620f  lea     rdx, [rsp+0E00h+hObject]; void *
0x180026214  mov     rcx, rsi; this
0x180026217  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x18002621c  test    eax, eax
0x18002621e  jnz     short loc_18002623E
0x180026220  call    cs:__imp_GetLastError
0x180026226  mov     rcx, rsi; this
0x180026229  mov     ebx, eax
0x18002622b  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x180026230  mov     ecx, ebx; dwErrCode
0x180026232  call    cs:__imp_SetLastError
0x180026238  mov     ebx, dword ptr [rsp+0E00h+var_DA8]
0x18002623c  jmp     short loc_180026261
0x18002623e  mov     r14, rsi
0x180026241  jmp     short loc_180026261
0x180026243  mov     rcx, [rsi+8]
0x180026247  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002624d  call    cs:__imp_GetProcessHeap
0x180026253  mov     r8, rsi; lpMem
0x180026256  xor     edx, edx; dwFlags
0x180026258  mov     rcx, rax; hHeap
0x18002625b  call    cs:__imp_HeapFree
0x180026261  test    r14, r14
0x180026264  jz      short loc_1800262DA
0x180026266  mov     rcx, [rsp+0E00h+hObject]; this
0x18002626b  mov     r9, r15; unsigned int
0x18002626e  mov     [rsp+0E00h+var_DB8], 1; unsigned __int8
0x180026273  mov     r8d, ebx; struct _BLUETOOTH_DEVICE_INFO *
0x180026276  mov     [rsp+0E00h+var_DC0], 0; unsigned __int8
0x18002627b  mov     rdx, r13; void *
0x18002627e  mov     [rsp+0E00h+var_DC8], 0; unsigned __int8
0x180026283  mov     byte ptr [rsp+0E00h+var_DD0], 1; void *
0x180026288  mov     qword ptr [rsp+0E00h+var_DD8], 0; unsigned int
0x180026291  mov     dword ptr [rsp+0E00h+var_DE0], 1; struct _GUID *
0x180026299  call    ?BthpSetServiceStateEx@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@KPEBU_GUID@@K0EEEE@Z; Microsoft::Bluetooth::Services::BthServ::BthpSetServiceStateEx(void *,_BLUETOOTH_DEVICE_INFO const *,ulong,_GUID const *,ulong,void *,uchar,uchar,uchar,uchar)
0x18002629e  mov     rcx, [rsp+0E00h+hObject]; hObject
0x1800262a3  mov     edi, eax
0x1800262a5  call    cs:__imp_CloseHandle
0x1800262ab  lea     rdx, [rsp+0E00h+hObject]; void *
0x1800262b0  mov     rcx, r14; this
0x1800262b3  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800262b8  test    eax, eax
0x1800262ba  jnz     short loc_180026266
0x1800262bc  mov     rcx, r14; this
0x1800262bf  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x1800262c4  jmp     short loc_1800262DA
0x1800262c6  call    cs:__imp_GetProcessHeap
0x1800262cc  mov     r8, rsi; lpMem
0x1800262cf  xor     edx, edx; dwFlags
0x1800262d1  mov     rcx, rax; hHeap
0x1800262d4  call    cs:__imp_HeapFree
0x1800262da  mov     eax, edi
0x1800262dc  mov     rcx, [rbp+0D00h+var_50]
0x1800262e3  xor     rcx, rsp; StackCookie
0x1800262e6  call    __security_check_cookie
0x1800262eb  add     rsp, 0DC8h
0x1800262f2  pop     r15
  ... truncated ...
```
