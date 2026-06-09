# DafBthSynchronize(ulong *,ulong *)

- ea: `0x18002103c`
- end: `0x180021ac1`
- name: `?DafBthSynchronize@@YAJPEAK0@Z`
- size: `2693`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000c9d8`
- `0x18000d5b0`
- `0x1800100c0`

## callees

- `0x180001790`
- `0x18000230c`
- `0x180002470`
- `0x1800024ac`
- `0x1800209fc`
- `0x180020dec`
- `0x18002103c`
- `0x180021ac8`
- `0x180021b04`
- `0x180021b88`
- `0x180021bd4`
- `0x180021c74`
- `0x180021cc8`
- `0x180021f6c`
- `0x18002226c`
- `0x180022478`
- `0x180022688`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800212b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800212b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021435`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800219f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800219f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a53`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180021440`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800219dc`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180021440`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800219dc`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x1800213fc`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x1800213fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DafBthSynchronize(unsigned int *a1, unsigned int *a2)
{
  int v2; // esi
  _DWORD *v5; // r14
  __int64 v6; // rcx
  signed int LastError; // eax
  signed int LocalDeviceInfo; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  char *v11; // r15
  void **v12; // r14
  _QWORD *v13; // rbx
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  char *v18; // rcx
  int DeviceAddressAndTypeFromAepId; // eax
  int DeviceInfo; // edi
  int v21; // r15d
  int DeviceInfoList; // eax
  __int64 v23; // rax
  _QWORD *v24; // rdi
  __int64 v25; // r12
  struct _BTH_DEVICE_INFO_V3 *v26; // r15
  char v27; // r13
  void **v28; // rsi
  __int64 v29; // rax
  char *v30; // rcx
  unsigned int *v31; // rsi
  void *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  bool v35; // cf
  char v37; // [rsp+60h] [rbp-A0h] BYREF
  char v38; // [rsp+61h] [rbp-9Fh]
  int v39; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  __int64 v42; // [rsp+78h] [rbp-88h]
  HANDLE hHandle[2]; // [rsp+80h] [rbp-80h]
  void *Block[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v45; // [rsp+A0h] [rbp-60h]
  _DWORD *v46; // [rsp+A8h] [rbp-58h]
  int v47; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v48[103]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v49; // [rsp+3F0h] [rbp+2F0h]
  int v50; // [rsp+400h] [rbp+300h]
  int v51; // [rsp+404h] [rbp+304h]
  __int64 v52; // [rsp+408h] [rbp+308h]
  char *v53; // [rsp+410h] [rbp+310h]
  __int64 OutBuffer; // [rsp+420h] [rbp+320h] BYREF
  _QWORD v55[37]; // [rsp+428h] [rbp+328h] BYREF
  int v56; // [rsp+550h] [rbp+450h]
  int v57; // [rsp+558h] [rbp+458h]
  __int128 v58; // [rsp+55Ch] [rbp+45Ch]
  _BYTE v59[28]; // [rsp+56Ch] [rbp+46Ch] BYREF
  int v60; // [rsp+588h] [rbp+488h]
  __int128 v61; // [rsp+590h] [rbp+490h]
  int v62; // [rsp+5A0h] [rbp+4A0h]
  int v63; // [rsp+5A4h] [rbp+4A4h]
  __int64 v64; // [rsp+5A8h] [rbp+4A8h]
  int v65; // [rsp+5B0h] [rbp+4B0h]
  int v66; // [rsp+5B4h] [rbp+4B4h]
  char *v67; // [rsp+5B8h] [rbp+4B8h]
  int v68; // [rsp+5C0h] [rbp+4C0h]
  int v69; // [rsp+5C8h] [rbp+4C8h]
  __int128 v70; // [rsp+5CCh] [rbp+4CCh]
  _BYTE v71[28]; // [rsp+5DCh] [rbp+4DCh] BYREF
  int v72; // [rsp+5F8h] [rbp+4F8h]
  __int128 v73; // [rsp+600h] [rbp+500h]
  int v74; // [rsp+610h] [rbp+510h]
  int v75; // [rsp+614h] [rbp+514h]
  __int64 v76; // [rsp+618h] [rbp+518h]
  int v77; // [rsp+620h] [rbp+520h]
  int v78; // [rsp+624h] [rbp+524h]
  const struct _GUID *v79; // [rsp+628h] [rbp+528h]
  int v80; // [rsp+630h] [rbp+530h]
  __int128 v81; // [rsp+638h] [rbp+538h]
  int v82; // [rsp+648h] [rbp+548h]
  int v83; // [rsp+64Ch] [rbp+54Ch]
  __int64 v84; // [rsp+650h] [rbp+550h]
  __int64 v85; // [rsp+658h] [rbp+558h]
  const struct _GUID *v86; // [rsp+660h] [rbp+560h]
  int v87; // [rsp+668h] [rbp+568h]
  int v88; // [rsp+670h] [rbp+570h]
  __int128 v89; // [rsp+674h] [rbp+574h]
  _BYTE v90[28]; // [rsp+684h] [rbp+584h] BYREF
  int v91; // [rsp+6A0h] [rbp+5A0h]
  int v92; // [rsp+6A8h] [rbp+5A8h]
  __int128 v93; // [rsp+6ACh] [rbp+5ACh]
  _BYTE v94[28]; // [rsp+6BCh] [rbp+5BCh] BYREF

  v2 = 0;
  v45 = a1;
  v42 = 0;
  hObject = 0;
  v46 = 0;
  OutBuffer = 0;
  *(_OWORD *)hHandle = 0;
  v5 = 0;
  *(_OWORD *)Block = 0;
  memset_0(v55, 0, 0x11Cu);
  v62 = 16;
  v67 = &v37;
  memset(v59, 0, sizeof(v59));
  v74 = 5;
  v82 = 5;
  v58 = 0;
  v86 = &DAF_ProtocolId_BluetoothLE;
  v37 = -1;
  v61 = DEVPKEY_Aep_IsAssociated;
  memset(v71, 0, sizeof(v71));
  v56 = 0x100000;
  memset(v90, 0, sizeof(v90));
  v57 = 0;
  memset(v94, 0, sizeof(v94));
  v60 = 2;
  v63 = 0;
  v64 = 0;
  v65 = 17;
  v70 = 0;
  v66 = 1;
  v89 = 0;
  v68 = 3145728;
  v93 = 0;
  v69 = 0;
  v72 = 2;
  v73 = DEVPKEY_Aep_ProtocolId;
  v49 = DEVPKEY_DasParam_AepStoreOnly;
  v75 = 0;
  v76 = 0;
  v77 = 13;
  v78 = 16;
  v79 = &DAF_ProtocolId_Bluetooth;
  v80 = 2;
  v81 = DEVPKEY_Aep_ProtocolId;
  v83 = 0;
  v84 = 0;
  v85 = 0x100000000DLL;
  v87 = 0x400000;
  v88 = 0;
  v91 = 0x200000;
  v92 = 0;
  v50 = 4;
  v51 = 17;
  v52 = 1;
  v53 = &v37;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  *a1 = 0;
  Block[1] = Block;
  *a2 = 0;
  Block[0] = Block;
  hHandle[1] = CreateEventW(0, 1, 0, 0);
  if ( !hHandle[1] )
  {
    LastError = GetLastError();
    LocalDeviceInfo = LastError;
    if ( LastError > 0 )
      LocalDeviceInfo = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_127;
    v10 = 18;
    goto LABEL_10;
  }
  LocalDeviceInfo = BthDevnodeOpenInterfaceHandle(v6, 0x40000000, &hObject);
  if ( LocalDeviceInfo < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_127;
    v10 = 19;
    goto LABEL_10;
  }
  v11 = (char *)hObject;
  LocalDeviceInfo = DafBthGetLocalDeviceInfo(hObject, &OutBuffer);
  if ( LocalDeviceInfo < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_127;
    v10 = 20;
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  LocalDeviceInfo = DevCreateObjectQueryEx(5, 3, 0, 0);
  if ( LocalDeviceInfo < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_127;
    v10 = 22;
    goto LABEL_10;
  }
  WaitForSingleObject(hHandle[1], 0x2710u);
  DevCloseObjectQuery(v42);
  LocalDeviceInfo = (signed int)hHandle[0];
  v42 = 0;
  if ( SLODWORD(hHandle[0]) < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_130;
    v10 = 23;
LABEL_10:
    WPP_SF_sd(v9[2], v10, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
    goto LABEL_127;
  }
  v12 = (void **)Block[0];
  v13 = WPP_GLOBAL_Control;
  while ( v12 != Block )
  {
    v39 = 0;
    memset_0(&v47, 0, 0x340u);
    v41 = 0;
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v12 + v17 + 9) );
    if ( (_DWORD)v17 == 54 )
    {
      v18 = (char *)v12 + 38;
LABEL_38:
      DeviceAddressAndTypeFromAepId = DafBthGetDeviceAddressAndTypeFromAepIdEx(v18, &v39, v48);
      v13 = WPP_GLOBAL_Control;
      DeviceInfo = DeviceAddressAndTypeFromAepId;
      v2 = v39;
      goto LABEL_43;
    }
    if ( (_DWORD)v17 == 58 )
    {
      v18 = (char *)v12 + 42;
      goto LABEL_38;
    }
    if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 25) >= 2u )
    {
      WPP_SF_s(v13[2], 24, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    DeviceInfo = -2147467259;
LABEL_43:
    if ( v41 != v55[0] )
    {
      if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 25) >= 4u )
      {
        WPP_SF_s(v13[2], 25, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
        goto LABEL_70;
      }
      goto LABEL_71;
    }
    if ( DeviceInfo < 0 )
      goto LABEL_65;
    DeviceInfo = DafBthGetDeviceInfo(v11);
    if ( DeviceInfo < 0 )
      goto LABEL_64;
    v21 = v47;
    if ( !v2 )
    {
      if ( (v47 & 0x18) != 0 )
        goto LABEL_69;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_68;
      DeviceInfo = -2140930033;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_65;
      WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v15, v16, (__int64)v12 + 18);
    }
    if ( v2 != 1 )
    {
      v2 = 0;
      goto LABEL_74;
    }
    v2 = 0;
    if ( (v21 & 0x18) == 0 )
    {
      if ( (v21 & 0x30000) == 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          LOBYTE(DeviceInfo) = 15;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v15, v16, (__int64)v12 + 18);
LABEL_64:
            v13 = WPP_GLOBAL_Control;
          }
LABEL_65:
          if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 25) >= 2u )
            WPP_SF_sdS(v13[2], v14, v15, v16, DeviceInfo, (__int64)v12 + 18);
        }
LABEL_68:
        DafBthSyncRemoveAep((unsigned __int16 *)v12 + 9);
        *((_BYTE *)v12 + 16) = 1;
        ++*a2;
LABEL_69:
        v11 = (char *)hObject;
LABEL_70:
        v13 = WPP_GLOBAL_Control;
LABEL_71:
        v2 = 0;
        goto LABEL_72;
      }
      goto LABEL_74;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v15, v16, (__int64)v12 + 18);
LABEL_74:
      v13 = WPP_GLOBAL_Control;
    }
    if ( DeviceInfo < 0 )
      goto LABEL_65;
    v11 = (char *)hObject;
LABEL_72:
    v12 = (void **)*v12;
  }
  if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 25) >= 4u )
    WPP_SF_s(v13[2], 30, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  DeviceInfoList = DafBthGetDeviceInfoListEx(v11);
  v5 = v46;
  LocalDeviceInfo = DeviceInfoList;
  if ( DeviceInfoList < 0 )
    goto LABEL_127;
  v23 = 0;
  LODWORD(v41) = 0;
  if ( !v46[4] )
    goto LABEL_127;
  v24 = WPP_GLOBAL_Control;
  while ( 2 )
  {
    v25 = 208 * v23;
    v26 = (struct _BTH_DEVICE_INFO_V3 *)&v5[208 * v23 + 6];
    if ( (*(_DWORD *)v26 & 0x30018) == 0 )
      goto LABEL_126;
    v27 = 0;
    v38 = 0;
    v28 = (void **)Block[0];
    if ( Block[0] == Block )
      goto LABEL_115;
    while ( 2 )
    {
      v39 = 0;
      memset_0(&v47, 0, 0x340u);
      if ( !*((_BYTE *)v28 + 16) )
      {
        v29 = -1;
        do
          ++v29;
        while ( *((_WORD *)v28 + v29 + 9) );
        if ( (_DWORD)v29 == 54 )
        {
          v30 = (char *)v28 + 38;
LABEL_92:
          LocalDeviceInfo = DafBthGetDeviceAddressAndTypeFromAepIdEx(v30, &v39, v48);
          if ( LocalDeviceInfo >= 0 && v48[0] == *(_QWORD *)&v5[v25 + 8] )
          {
            if ( !v39 )
            {
              v27 = 1;
              goto LABEL_96;
            }
            v24 = WPP_GLOBAL_Control;
            if ( v39 == 1 )
              v38 = 1;
          }
          else
          {
LABEL_96:
            v24 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          if ( (_DWORD)v29 == 58 )
          {
            v30 = (char *)v28 + 42;
            goto LABEL_92;
          }
          if ( v24 != &WPP_GLOBAL_Control && *((_BYTE *)v24 + 25) >= 2u )
          {
            WPP_SF_s(v24[2], 31, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
            v24 = WPP_GLOBAL_Control;
          }
          LocalDeviceInfo = -2140930033;
        }
      }
      v28 = (void **)*v28;
      if ( v28 != Block )
        continue;
      break;
    }
    v26 = (struct _BTH_DEVICE_INFO_V3 *)&v5[v25 + 6];
    if ( v27 )
      goto LABEL_105;
LABEL_115:
    if ( (*(_DWORD *)v26 & 0x18) != 0 && (*(_DWORD *)v26 & 0x4000) != 0 )
    {
      if ( v24 != &WPP_GLOBAL_Control && *((_BYTE *)v24 + 25) >= 4u )
        WPP_SF_si(v24[2], 32);
      LocalDeviceInfo = DafBthSyncCreateOfflineAep(&DAF_ProtocolId_Bluetooth, v26);
      if ( LocalDeviceInfo < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
          v24 = WPP_GLOBAL_Control;
        }
        goto LABEL_126;
      }
      v31 = v45;
      ++*v45;
      v24 = WPP_GLOBAL_Control;
    }
    else
    {
LABEL_105:
      v31 = v45;
    }
    if ( !v38 && (((*(_DWORD *)v26 & 0x30000) != 0) & _bittest((const signed __int32 *)v26, 0xFu)) != 0 )
    {
      if ( v24 != &WPP_GLOBAL_Control && *((_BYTE *)v24 + 25) >= 4u )
        WPP_SF_si(v24[2], 34);
      LocalDeviceInfo = DafBthSyncCreateOfflineAep(&DAF_ProtocolId_BluetoothLE, v26);
      if ( LocalDeviceInfo >= 0 )
      {
        ++*v31;
      }
      else
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_126;
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
      }
      v24 = WPP_GLOBAL_Control;
    }
LABEL_126:
    v23 = (unsigned int)(v41 + 1);
    LODWORD(v41) = v23;
    if ( (unsigned int)v23 < v5[4] )
      continue;
    break;
  }
LABEL_127:
  if ( v42 )
  {
    DevCloseObjectQuery(v42);
    v42 = 0;
  }
  v11 = (char *)hObject;
LABEL_130:
  if ( hHandle[1] )
  {
    CloseHandle(hHandle[1]);
    hHandle[1] = 0;
  }
  while ( 1 )
  {
    v32 = Block[0];
    if ( Block[0] == Block )
      break;
    if ( *((void ***)Block[0] + 1) != Block
      || (v33 = *(_QWORD *)Block[0], *(void **)(*(_QWORD *)Block[0] + 8LL) != Block[0]) )
    {
      __fastfail(3u);
    }
    Block[0] = *(void **)Block[0];
    *(_QWORD *)(v33 + 8) = Block;
    free(v32);
  }
  if ( v5 )
    operator delete(v5);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  v34 = 0;
  if ( LocalDeviceInfo )
    v35 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v35 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v34) = !v35;
    if ( v34 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  }
  return (unsigned int)LocalDeviceInfo;
}

```

## disassembly

```asm
0x18002103c  mov     [rsp-8+arg_10], rbx
0x180021041  push    rbp
0x180021042  push    rsi
0x180021043  push    rdi
0x180021044  push    r12
0x180021046  push    r13
0x180021048  push    r14
0x18002104a  push    r15
0x18002104c  lea     rbp, [rsp-5F0h]
0x180021054  sub     rsp, 6F0h
0x18002105b  mov     rax, cs:__security_cookie
0x180021062  xor     rax, rsp
0x180021065  mov     [rbp+620h+var_40], rax
0x18002106c  xor     esi, esi
0x18002106e  mov     [rbp+620h+var_680], rcx
0x180021072  xorps   xmm0, xmm0
0x180021075  mov     [rsp+720h+var_6A8], rsi
0x18002107a  mov     r13, rdx
0x18002107d  mov     [rsp+720h+hObject], rsi
0x180021082  mov     rbx, rcx
0x180021085  mov     [rbp+620h+var_678], rsi
0x180021089  xor     edx, edx; Val
0x18002108b  mov     [rbp+620h+OutBuffer], rsi
0x180021092  lea     rcx, [rbp+620h+var_2F8]; void *
0x180021099  mov     r8d, 11Ch; Size
0x18002109f  movups  xmmword ptr [rbp+620h+hHandle], xmm0
0x1800210a3  mov     r14d, esi
0x1800210a6  movups  xmmword ptr [rbp+620h+Block], xmm0
0x1800210aa  call    memset_0
0x1800210af  mov     eax, cs:dword_18003C238
0x1800210b5  lea     r8d, [rsi+11h]
0x1800210b9  movups  xmm1, cs:DEVPKEY_Aep_ProtocolId
0x1800210c0  mov     [rbp+620h+var_180], eax
0x1800210c6  lea     rax, [rsp+720h+var_6C0]
0x1800210cb  xorps   xmm0, xmm0
0x1800210ce  mov     [rbp+620h+var_168], rax
0x1800210d5  mov     eax, cs:dword_18003C220
0x1800210db  lea     r12d, [rsi+1]
0x1800210df  movups  xmmword ptr [rbp+620h+var_1B4], xmm0
0x1800210e6  mov     [rbp+620h+var_110], eax
0x1800210ec  lea     edx, [rsi+0Dh]
0x1800210ef  movups  xmmword ptr [rbp+620h+var_1B4+0Ch], xmm0
0x1800210f6  mov     [rbp+620h+var_D8], eax
0x1800210fc  lea     rax, DAF_ProtocolId_BluetoothLE
0x180021103  movups  [rbp+620h+var_1C4], xmm0
0x18002110a  mov     [rbp+620h+var_C0], rax
0x180021111  lea     ecx, [rsi+10h]
0x180021114  movups  xmm0, cs:DEVPKEY_Aep_IsAssociated
0x18002111b  xor     eax, eax
0x18002111d  mov     [rsp+720h+var_6C0], 0FFh
0x180021122  mov     eax, cs:dword_18003C1E8
0x180021128  lea     r9, DAF_ProtocolId_Bluetooth
0x18002112f  movaps  [rbp+620h+var_190], xmm0
0x180021136  xorps   xmm0, xmm0
0x180021139  movups  xmmword ptr [rbp+620h+var_144], xmm0
0x180021140  mov     [rbp+620h+var_1D0], 100000h
0x18002114a  movups  xmmword ptr [rbp+620h+var_9C], xmm0
0x180021151  mov     [rbp+620h+var_1C8], esi
0x180021157  movups  xmmword ptr [rbp+620h+var_64], xmm0
0x18002115e  mov     [rbp+620h+var_198], 2
0x180021168  movups  xmmword ptr [rbp+620h+var_144+0Ch], xmm0
0x18002116f  mov     [rbp+620h+var_17C], esi
0x180021175  movups  xmmword ptr [rbp+620h+var_9C+0Ch], xmm0
0x18002117c  mov     [rbp+620h+var_178], rsi
0x180021183  movups  xmmword ptr [rbp+620h+var_64+0Ch], xmm0
0x18002118a  mov     [rbp+620h+var_170], r8d
0x180021191  movups  [rbp+620h+var_154], xmm0
0x180021198  mov     [rbp+620h+var_16C], r12d
0x18002119f  movups  [rbp+620h+var_AC], xmm0
0x1800211a6  mov     [rbp+620h+var_160], 300000h
0x1800211b0  movups  [rbp+620h+var_74], xmm0
0x1800211b7  mov     [rbp+620h+var_158], esi
0x1800211bd  movups  xmm0, cs:DEVPKEY_DasParam_AepStoreOnly
0x1800211c4  mov     [rbp+620h+var_128], 2
0x1800211ce  movaps  [rbp+620h+var_120], xmm1
0x1800211d5  movups  [rbp+620h+var_330], xmm0
0x1800211dc  mov     [rbp+620h+var_10C], esi
0x1800211e2  mov     [rbp+620h+var_108], rsi
0x1800211e9  mov     [rbp+620h+var_100], edx
0x1800211ef  mov     [rbp+620h+var_FC], ecx
0x1800211f5  mov     [rbp+620h+var_F8], r9
0x1800211fc  mov     [rbp+620h+var_F0], 2
0x180021206  movups  [rbp+620h+var_E8], xmm1
0x18002120d  mov     [rbp+620h+var_D4], esi
0x180021213  mov     [rbp+620h+var_D0], rsi
0x18002121a  mov     dword ptr [rbp+620h+var_C8], edx
0x180021220  mov     dword ptr [rbp+620h+var_C8+4], ecx
0x180021226  mov     [rbp+620h+var_B8], 400000h
0x180021230  mov     [rbp+620h+var_B0], esi
0x180021236  mov     [rbp+620h+var_80], 200000h
0x180021240  mov     [rbp+620h+var_78], esi
0x180021246  mov     [rbp+620h+var_320], eax
0x18002124c  mov     [rbp+620h+var_31C], r8d
0x180021253  mov     [rbp+620h+var_318], r12
0x18002125a  lea     rax, [rsp+720h+var_6C0]
0x18002125f  mov     [rbp+620h+var_310], rax
0x180021266  mov     rcx, cs:WPP_GLOBAL_Control
0x18002126d  lea     rdi, WPP_GLOBAL_Control
0x180021274  cmp     rcx, rdi
0x180021277  jz      short loc_180021292
0x180021279  cmp     byte ptr [rcx+19h], 5
0x18002127d  jb      short loc_180021292
0x18002127f  mov     rcx, [rcx+10h]
0x180021283  mov     edx, r8d
0x180021286  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x18002128d  call    WPP_SF_s
0x180021292  lea     rax, [rbp+620h+Block]
0x180021296  mov     [rbx], esi
0x180021298  mov     [rbp+620h+Block+8], rax
0x18002129c  xor     r9d, r9d; lpName
0x18002129f  lea     rax, [rbp+620h+Block]
0x1800212a3  mov     [r13+0], esi
0x1800212a7  xor     r8d, r8d; bInitialState
0x1800212aa  mov     [rbp+620h+Block], rax
0x1800212ae  mov     edx, r12d; bManualReset
0x1800212b1  xor     ecx, ecx; lpEventAttributes
0x1800212b3  call    cs:__imp_CreateEventW
0x1800212b9  mov     [rbp+620h+hHandle+8], rax
0x1800212bd  test    rax, rax
0x1800212c0  jnz     short loc_18002130F
0x1800212c2  call    cs:__imp_GetLastError
0x1800212c8  mov     ebx, eax
0x1800212ca  test    eax, eax
0x1800212cc  jle     short loc_1800212D7
0x1800212ce  movzx   ebx, ax
0x1800212d1  or      ebx, 80070000h
0x1800212d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212de  cmp     rcx, rdi
0x1800212e1  jz      loc_1800219D2
0x1800212e7  cmp     byte ptr [rcx+19h], 2
0x1800212eb  jb      loc_1800219D2
0x1800212f1  mov     edx, 12h
0x1800212f6  mov     dword ptr [rsp+720h+var_700], ebx
0x1800212fa  mov     rcx, [rcx+10h]
0x1800212fe  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180021305  call    WPP_SF_sd
0x18002130a  jmp     loc_1800219D2
0x18002130f  lea     r8, [rsp+720h+hObject]
0x180021314  mov     edx, 40000000h
0x180021319  call    BthDevnodeOpenInterfaceHandle
0x18002131e  mov     ebx, eax
0x180021320  test    eax, eax
0x180021322  jns     short loc_180021349
0x180021324  mov     rcx, cs:WPP_GLOBAL_Control
0x18002132b  cmp     rcx, rdi
0x18002132e  jz      loc_1800219D2
0x180021334  cmp     byte ptr [rcx+19h], 2
0x180021338  jb      loc_1800219D2
0x18002133e  mov     edx, 13h
0x180021343  mov     dword ptr [rsp+720h+var_700], eax
0x180021347  jmp     short loc_1800212FA
0x180021349  mov     r15, [rsp+720h+hObject]
0x18002134e  lea     rdx, [rbp+620h+OutBuffer]; lpOutBuffer
0x180021355  mov     rcx, r15; hFile
0x180021358  call    DafBthGetLocalDeviceInfo
0x18002135d  mov     ebx, eax
0x18002135f  test    eax, eax
0x180021361  jns     short loc_180021384
0x180021363  mov     rcx, cs:WPP_GLOBAL_Control
0x18002136a  cmp     rcx, rdi
0x18002136d  jz      loc_1800219D2
0x180021373  cmp     byte ptr [rcx+19h], 2
0x180021377  jb      loc_1800219D2
0x18002137d  mov     edx, 14h
0x180021382  jmp     short loc_180021343
0x180021384  mov     rcx, cs:WPP_GLOBAL_Control
0x18002138b  cmp     rcx, rdi
0x18002138e  jz      short loc_1800213AB
0x180021390  cmp     byte ptr [rcx+19h], 4
0x180021394  jb      short loc_1800213AB
0x180021396  mov     rcx, [rcx+10h]
0x18002139a  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x1800213a1  mov     edx, 15h
0x1800213a6  call    WPP_SF_s
0x1800213ab  lea     rax, [rsp+720h+var_6A8]
0x1800213b0  xor     r9d, r9d
0x1800213b3  mov     [rsp+720h+var_6D0], rax
0x1800213b8  xor     r8d, r8d
0x1800213bb  lea     rax, [rbp+620h+hHandle]
0x1800213bf  mov     [rsp+720h+var_6D8], rax
0x1800213c4  lea     rax, ?DafBthSyncAepQueryCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DafBthSyncAepQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800213cb  mov     [rsp+720h+var_6E0], rax
0x1800213d0  lea     edx, [r9+3]
0x1800213d4  lea     rax, [rbp+620h+var_330]
0x1800213db  mov     [rsp+720h+var_6E8], rax
0x1800213e0  lea     ecx, [rdx+2]
0x1800213e3  lea     rax, [rbp+620h+var_1D0]
0x1800213ea  mov     [rsp+720h+var_6F0], r12d
0x1800213ef  mov     [rsp+720h+var_6F8], rax
0x1800213f4  mov     dword ptr [rsp+720h+var_700], 7
0x1800213fc  call    cs:__imp_DevCreateObjectQueryEx
0x180021402  mov     ebx, eax
0x180021404  test    eax, eax
0x180021406  jns     short loc_18002142C
0x180021408  mov     rcx, cs:WPP_GLOBAL_Control
0x18002140f  cmp     rcx, rdi
0x180021412  jz      loc_1800219D2
0x180021418  cmp     byte ptr [rcx+19h], 2
0x18002141c  jb      loc_1800219D2
0x180021422  mov     edx, 16h
0x180021427  jmp     loc_180021343
0x18002142c  mov     rcx, [rbp+620h+hHandle+8]; hHandle
0x180021430  mov     edx, 2710h; dwMilliseconds
0x180021435  call    cs:__imp_WaitForSingleObject
0x18002143b  mov     rcx, [rsp+720h+var_6A8]
0x180021440  call    cs:__imp_DevCloseObjectQuery
0x180021446  mov     ebx, dword ptr [rbp+620h+hHandle]
0x180021449  mov     [rsp+720h+var_6A8], rsi
0x18002144e  test    ebx, ebx
0x180021450  jns     short loc_180021476
0x180021452  mov     rcx, cs:WPP_GLOBAL_Control
0x180021459  cmp     rcx, rdi
0x18002145c  jz      loc_1800219EC
0x180021462  cmp     byte ptr [rcx+19h], 2
0x180021466  jb      loc_1800219EC
0x18002146c  mov     edx, 17h
0x180021471  jmp     loc_1800212F6
0x180021476  mov     r14, [rbp+620h+Block]
0x18002147a  mov     rbx, cs:WPP_GLOBAL_Control
0x180021481  lea     rax, [rbp+620h+Block]
0x180021485  cmp     r14, rax
0x180021488  jz      loc_1800216F2
0x18002148e  xor     edx, edx; Val
0x180021490  mov     [rsp+720h+var_6BC], esi
0x180021494  mov     r8d, 340h; Size
0x18002149a  lea     rcx, [rbp+620h+var_670]; void *
0x18002149e  call    memset_0
0x1800214a3  xor     ecx, ecx
0x1800214a5  lea     r12, [r14+12h]
0x1800214a9  mov     [rsp+720h+var_6B0], rcx
0x1800214ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800214b2  inc     rax
0x1800214b5  cmp     [r12+rax*2], cx
0x1800214ba  jnz     short loc_1800214B2
0x1800214bc  cmp     eax, 36h ; '6'
0x1800214bf  jnz     short loc_1800214C7
0x1800214c1  lea     rcx, [r14+26h]
0x1800214c5  jmp     short loc_1800214D0
0x1800214c7  cmp     eax, 3Ah ; ':'
0x1800214ca  jnz     short loc_1800214F2
0x1800214cc  lea     rcx, [r14+2Ah]
0x1800214d0  lea     r9, [rsp+720h+var_6B0]
0x1800214d5  lea     r8, [rbp+620h+var_668]
0x1800214d9  lea     rdx, [rsp+720h+var_6BC]
0x1800214de  call    DafBthGetDeviceAddressAndTypeFromAepIdEx
0x1800214e3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800214ea  mov     edi, eax
0x1800214ec  mov     esi, [rsp+720h+var_6BC]
0x1800214f0  jmp     short loc_18002151E
0x1800214f2  cmp     rbx, rdi
0x1800214f5  jz      short loc_180021519
0x1800214f7  cmp     byte ptr [rbx+19h], 2
0x1800214fb  jb      short loc_180021519
0x1800214fd  mov     rcx, [rbx+10h]
0x180021501  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180021508  mov     edx, 18h
0x18002150d  call    WPP_SF_s
0x180021512  mov     rbx, cs:WPP_GLOBAL_Control
0x180021519  mov     edi, 80004005h
0x18002151e  mov     rax, [rbp+620h+var_2F8]
0x180021525  cmp     [rsp+720h+var_6B0], rax
0x18002152a  jz      short loc_180021560
0x18002152c  lea     rdi, WPP_GLOBAL_Control
0x180021533  cmp     rbx, rdi
0x180021536  jz      loc_1800216C6
0x18002153c  cmp     byte ptr [rbx+19h], 4
0x180021540  jb      loc_1800216C6
0x180021546  mov     rcx, [rbx+10h]
0x18002154a  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180021551  mov     edx, 19h
0x180021556  call    WPP_SF_s
0x18002155b  jmp     loc_1800216BF
0x180021560  test    edi, edi
0x180021562  js      loc_18002167E
0x180021568  xor     ebx, ebx
0x18002156a  test    esi, esi
0x18002156c  jz      short loc_180021580
0x18002156e  cmp     esi, 1
0x180021571  jz      short loc_180021578
0x180021573  mov     r8d, ebx
0x180021576  jmp     short loc_180021586
0x180021578  mov     r8d, 2
0x18002157e  jmp     short loc_180021586
0x180021580  mov     r8d, 1
0x180021586  mov     rdx, [rbp+620h+var_668]
0x18002158a  lea     r9, [rbp+620h+var_670]
0x18002158e  mov     rcx, r15; hFile
0x180021591  call    DafBthGetDeviceInfo
0x180021596  mov     edi, eax
0x180021598  test    eax, eax
0x18002159a  js      loc_180021677
0x1800215a0  mov     r15d, [rbp+620h+var_670]
0x1800215a4  test    esi, esi
0x1800215a6  jnz     short loc_1800215E5
0x1800215a8  test    r15b, 18h
0x1800215ac  jnz     short loc_18002162D
0x1800215ae  mov     rbx, cs:WPP_GLOBAL_Control
0x1800215b5  lea     rdi, WPP_GLOBAL_Control
0x1800215bc  cmp     rbx, rdi
0x1800215bf  jz      loc_1800216A9
  ... truncated ...
```
