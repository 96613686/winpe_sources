# BthEnumSetDevicePdoProperties

- ea: `0x14001aaac`
- end: `0x14001b55c`
- name: `BthEnumSetDevicePdoProperties`
- size: `2736`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019058`
- `0x14001e1e0`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x140018a54`
- `0x140018b90`
- `0x14001aaac`
- `0x14001b564`

## import_xrefs

- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14001ae00`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14001ae00`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001abfe`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001acb1`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001ad0f`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001ad7f`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001ae5d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b20d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b28d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b2ae`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b32d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b34e`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b3ae`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b414`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001abfe`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001acb1`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001ad0f`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001ad7f`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001ae5d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b20d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b28d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b2ae`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b32d`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b34e`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b3ae`
- `ntoskrnl!IoSetDevicePropertyData` at `0x14001b414`
- `ntoskrnl!ExFreePool` at `0x14001b44f`
- `ntoskrnl!ExFreePool` at `0x14001b4bf`
- `ntoskrnl!ExFreePool` at `0x14001b4d3`
- `ntoskrnl!ExFreePool` at `0x14001b4e7`
- `ntoskrnl!ExFreePool` at `0x14001b4fb`
- `ntoskrnl!ExFreePool` at `0x14001b44f`
- `ntoskrnl!ExFreePool` at `0x14001b4bf`
- `ntoskrnl!ExFreePool` at `0x14001b4d3`
- `ntoskrnl!ExFreePool` at `0x14001b4e7`
- `ntoskrnl!ExFreePool` at `0x14001b4fb`
- `ntoskrnl!ExAllocatePool2` at `0x14001ab1e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b148`
- `ntoskrnl!ExAllocatePool2` at `0x14001ab1e`
- `ntoskrnl!ExAllocatePool2` at `0x14001b148`

## string_xrefs

- `0x14001b121`: `Computer.Desktop`
- `0x14001b10f`: `Computer.Laptop`
- `0x14001b118`: `Computer.Server`
- `0x14001b106`: `Computer.Handheld`
- `0x14001b0fd`: `Computer`
- `0x14001b0d2`: `Communication.Phone`
- `0x14001b052`: `Communication.Headset.Bluetooth`

## pseudocode

```c
__int64 __fastcall BthEnumSetDevicePdoProperties(__int64 a1, char a2)
{
  PVOID v3; // r13
  PVOID v4; // r15
  _WORD *v5; // rsi
  WCHAR *v7; // rdi
  NTSTATUS v8; // ebx
  __int64 v9; // r12
  int v10; // eax
  int v11; // edx
  NTSTATUS v12; // eax
  int v13; // edx
  int v14; // r9d
  int v15; // r8d
  NTSTATUS v16; // eax
  bool v17; // zf
  NTSTATUS v18; // eax
  const CHAR *v19; // r9
  __int64 v20; // rax
  unsigned int v21; // eax
  const wchar_t *v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  const wchar_t *v29; // rax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // rdx
  _WORD *v47; // rax
  int v48; // edx
  __int64 v49; // rdx
  unsigned __int64 v50; // rdx
  __int64 v51; // rcx
  _WORD *v52; // rcx
  __int64 v53; // rdx
  int v54; // r9d
  struct _DEVICE_OBJECT *v55; // rcx
  struct _DEVICE_OBJECT *v56; // rcx
  __int64 v57; // rdx
  __int64 Size; // [rsp+28h] [rbp-28h]
  WCHAR *Pool2; // [rsp+40h] [rbp-10h]
  PVOID Data; // [rsp+48h] [rbp-8h] BYREF
  ULONG UnicodeStringActualByteCount; // [rsp+90h] [rbp+40h] BYREF
  int v63; // [rsp+94h] [rbp+44h]
  char v64; // [rsp+A0h] [rbp+50h] BYREF
  PVOID v65; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  Data = 0;
  v4 = 0;
  v65 = 0;
  v5 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      44,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids);
  Pool2 = (WCHAR *)ExAllocatePool2(256, 498, 1330467906);
  v7 = Pool2;
  if ( Pool2 )
  {
    v9 = -1;
    if ( a2 )
    {
      v10 = BthEnumGenerateAepId(a1, &Data);
      v8 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            3,
            46,
            (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
            v10);
        v3 = Data;
        goto LABEL_162;
      }
      v3 = Data;
      v12 = IoSetDevicePropertyData(*(PDEVICE_OBJECT *)(a1 + 16), &DEVPKEY_Aep_AepId, 0, 0, 0x12u, 0x6Eu, Data);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_162:
          v4 = v65;
          goto LABEL_163;
        }
        v14 = 47;
        goto LABEL_15;
      }
      v12 = BthEnumGenerateAepDeviceAddress(*(_QWORD *)(a1 + 192), &v65);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_162;
        v14 = 48;
        goto LABEL_15;
      }
      v12 = IoSetDevicePropertyData(*(PDEVICE_OBJECT *)(a1 + 16), &DEVPKEY_Aep_DeviceAddress, 0, 0, 0x12u, 0x24u, v65);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_162;
        v14 = 49;
LABEL_15:
        LODWORD(Size) = v12;
LABEL_16:
        v15 = 3;
LABEL_17:
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          v15,
          v14,
          (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
          Size);
        goto LABEL_162;
      }
      v16 = IoSetDevicePropertyData(
              *(PDEVICE_OBJECT *)(a1 + 16),
              &DEVPKEY_DeviceContainer_DiscoveryMethod,
              0,
              0,
              0x2012u,
              0x16u,
              L"Bluetooth");
      v13 = 0;
      v8 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_162;
        v14 = 50;
        LODWORD(Size) = v16;
        v15 = 1;
        goto LABEL_17;
      }
      v17 = (*(_DWORD *)(a1 + 184) & 0x8000000) == 0;
      LOBYTE(UnicodeStringActualByteCount) = -1;
      if ( !v17 )
      {
        v18 = IoSetDevicePropertyData(
                *(PDEVICE_OBJECT *)(a1 + 16),
                &DEVPKEY_Bluetooth_SecureConnectionPaired,
                0,
                0,
                0x11u,
                1u,
                &UnicodeStringActualByteCount);
        if ( v18 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(Size) = v18;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            3,
            51,
            (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
            Size);
        }
      }
    }
    if ( (*(_DWORD *)(a1 + 184) & 4) != 0 )
    {
      UnicodeStringActualByteCount = 0;
      v19 = (const CHAR *)(a1 + 204);
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      v8 = RtlUTF8ToUnicodeN(Pool2, 0x1F2u, &UnicodeStringActualByteCount, v19, v20);
      if ( v8 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_162;
        v14 = 52;
        goto LABEL_37;
      }
      v8 = IoSetDevicePropertyData(
             *(PDEVICE_OBJECT *)(a1 + 16),
             &DEVPKEY_Device_FriendlyName,
             0,
             0,
             0x12u,
             UnicodeStringActualByteCount + 2,
             Pool2);
      if ( v8 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_162;
        v14 = 53;
LABEL_37:
        LODWORD(Size) = v8;
        goto LABEL_16;
      }
    }
    v21 = (*(_DWORD *)(a1 + 200) >> 2) & 0x3F;
    switch ( (*(_DWORD *)(a1 + 200) >> 8) & 0x1F )
    {
      case 1:
        v41 = v21 - 1;
        if ( !v41 )
        {
          v22 = L"Computer.Desktop";
          goto LABEL_118;
        }
        v42 = v41 - 1;
        if ( !v42 )
        {
          v22 = L"Computer.Server";
          goto LABEL_118;
        }
        v43 = v42 - 1;
        if ( !v43 )
        {
          v22 = L"Computer.Laptop";
          goto LABEL_118;
        }
        v44 = v43 - 1;
        if ( !v44 || (v45 = v44 - 1) == 0 )
        {
          v22 = L"Computer.Handheld";
          goto LABEL_118;
        }
        if ( v45 != 1 )
        {
          v22 = L"Computer";
          goto LABEL_118;
        }
        goto LABEL_88;
      case 2:
        if ( v21 == 4 )
          v22 = L"Network.Modem";
        else
          v22 = L"Communication.Phone";
        goto LABEL_118;
      case 3:
        v22 = L"Network";
        goto LABEL_118;
    }
    if ( ((*(_DWORD *)(a1 + 200) >> 8) & 0x1F) != 4 )
    {
      if ( ((*(_DWORD *)(a1 + 200) >> 8) & 0x1F) == 5 )
      {
        if ( ((*(_DWORD *)(a1 + 200) >> 2) & 0x10) != 0 )
        {
          v22 = L"Input.Keyboard";
        }
        else if ( ((*(_DWORD *)(a1 + 200) >> 2) & 0x20) != 0 )
        {
          v22 = L"Input.Mouse";
        }
        else
        {
          v22 = L"Input.Gaming";
          if ( v21 != 2 )
            v22 = L"Input";
        }
        goto LABEL_118;
      }
      if ( ((*(_DWORD *)(a1 + 200) >> 8) & 0x1F) != 6 )
      {
        if ( ((*(_DWORD *)(a1 + 200) >> 8) & 0x1F) != 7 && ((*(_DWORD *)(a1 + 200) >> 8) & 0x1F) != 8 )
        {
          if ( ((*(_DWORD *)(a1 + 200) >> 8) & 0x1F) == 9 )
          {
            v23 = v21 - 1;
            if ( !v23 )
            {
              v22 = L"Health.BloodPressure";
              goto LABEL_118;
            }
            v24 = v23 - 1;
            if ( !v24 )
              goto LABEL_61;
            v25 = v24 - 1;
            if ( !v25 )
              goto LABEL_61;
            v26 = v25 - 1;
            if ( !v26 )
            {
              v22 = L"Health.BloodGlucose";
              goto LABEL_118;
            }
            v27 = v26 - 1;
            if ( !v27 )
              goto LABEL_61;
            v28 = v27 - 1;
            if ( !v28 )
            {
              v22 = L"Health.HeartRate";
              goto LABEL_118;
            }
            if ( v28 != 2 )
            {
LABEL_61:
              v22 = L"Health";
              goto LABEL_118;
            }
            v22 = L"Health.Pedometer";
          }
          else
          {
            v22 = L"Unknown";
          }
LABEL_118:
          v46 = -1;
          do
            ++v46;
          while ( v22[v46] );
          v47 = (_WORD *)ExAllocatePool2(256, 2 * v46 + 4, 1330467906);
          v5 = v47;
          if ( !v47 )
          {
            v8 = -1073741670;
            goto LABEL_158;
          }
          v49 = -1;
          do
            ++v49;
          while ( v22[v49] );
          v8 = -1073741811;
          v50 = v49 + 1;
          if ( v50 )
          {
            if ( v50 > 0x7FFFFFFF )
            {
              *v47 = 0;
            }
            else
            {
              v51 = 2147483646;
              do
              {
                if ( !v51 )
                  break;
                if ( !*v22 )
                  break;
                *v47++ = *v22++;
                --v51;
                --v50;
              }
              while ( v50 );
              v52 = v47 - 1;
              if ( v50 )
                v52 = v47;
              v53 = -(__int64)v50;
              v8 = v53 == 0 ? 0x80000005 : 0;
              *v52 = 0;
              if ( v53 )
              {
                do
                  ++v9;
                while ( v5[v9] );
                v8 = IoSetDevicePropertyData(
                       *(PDEVICE_OBJECT *)(a1 + 16),
                       &DEVPKEY_DeviceContainer_Category,
                       0,
                       0,
                       0x2012u,
                       2 * v9 + 4,
                       v5);
                if ( v8 < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_161;
                  v54 = 55;
                  goto LABEL_160;
                }
                v55 = *(struct _DEVICE_OBJECT **)(a1 + 16);
                if ( (*(_DWORD *)(a1 + 184) & 0x20) != 0 )
                {
                  v8 = IoSetDevicePropertyData(v55, &DEVPKEY_Bluetooth_LastConnectedTime, 0, 0, 0x10u, 0, 0);
                  if ( v8 == -1073741772 )
                    goto LABEL_143;
                }
                else
                {
                  UnicodeStringActualByteCount = *(_DWORD *)(a1 + 1000);
                  v63 = *(_DWORD *)(a1 + 1004);
                  v8 = IoSetDevicePropertyData(
                         v55,
                         &DEVPKEY_Bluetooth_LastConnectedTime,
                         0,
                         0,
                         0x10u,
                         8u,
                         &UnicodeStringActualByteCount);
                }
                if ( v8 < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_161;
                  v54 = 56;
                  goto LABEL_160;
                }
LABEL_143:
                v56 = *(struct _DEVICE_OBJECT **)(a1 + 16);
                if ( (*(_DWORD *)(a1 + 184) & 0x20) != 0 )
                {
                  v8 = IoSetDevicePropertyData(v56, &DEVPKEY_Bluetooth_LastConnectedTime_Deprecated, 0, 0, 0x10u, 0, 0);
                  if ( v8 == -1073741772 )
                  {
LABEL_149:
                    v8 = IoSetDevicePropertyData(
                           *(PDEVICE_OBJECT *)(a1 + 16),
                           &DEVPKEY_Bluetooth_LastConnectionStatus,
                           0,
                           0,
                           3u,
                           1u,
                           (PVOID)(a1 + 1016));
                    if ( v8 >= 0 )
                    {
                      v64 = -(*(_BYTE *)(a1 + 1017) != 0);
                      v8 = IoSetDevicePropertyData(
                             *(PDEVICE_OBJECT *)(a1 + 16),
                             &DEVPKEY_Bluetooth_LastConnectionBlockedBySystem,
                             0,
                             0,
                             0x11u,
                             1u,
                             &v64);
                      if ( v8 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        goto LABEL_161;
                      v54 = 59;
                      goto LABEL_160;
                    }
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_161;
                    v54 = 58;
LABEL_160:
                    LODWORD(Size) = v8;
                    WPP_RECORDER_SF_d(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v48,
                      1,
                      v54,
                      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
                      Size);
                    goto LABEL_161;
                  }
                }
                else
                {
                  UnicodeStringActualByteCount = *(_DWORD *)(a1 + 1000);
                  v63 = *(_DWORD *)(a1 + 1004);
                  v8 = IoSetDevicePropertyData(
                         v56,
                         &DEVPKEY_Bluetooth_LastConnectedTime_Deprecated,
                         0,
                         0,
                         0x10u,
                         8u,
                         &UnicodeStringActualByteCount);
                }
                if ( v8 < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_161;
                  v54 = 57;
                  goto LABEL_160;
                }
                goto LABEL_149;
              }
            }
          }
          ExFreePool(v5);
          v5 = 0;
LABEL_158:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v54 = 54;
            goto LABEL_160;
          }
LABEL_161:
          v7 = Pool2;
          goto LABEL_162;
        }
LABEL_88:
        v22 = L"Other";
        goto LABEL_118;
      }
      if ( ((*(_DWORD *)(a1 + 200) >> 2) & 0x20) != 0 )
      {
        v22 = L"PrintFax.Printer";
        goto LABEL_118;
      }
      if ( ((*(_DWORD *)(a1 + 200) >> 2) & 0x10) != 0 )
      {
        v22 = L"Imaging.Scanner";
        goto LABEL_118;
      }
      if ( ((*(_DWORD *)(a1 + 200) >> 2) & 4) == 0 )
      {
        v29 = L"Imaging.Camera";
        if ( ((*(_DWORD *)(a1 + 200) >> 2) & 8) == 0 )
          v29 = L"Other";
        v22 = v29;
        goto LABEL_118;
      }
LABEL_68:
      v22 = L"Display";
      goto LABEL_118;
    }
    if ( v21 > 9 )
    {
      v36 = v21 - 10;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( !v38 || (v39 = v38 - 1) == 0 )
          {
            v22 = L"Imaging.Camcorder";
            goto LABEL_118;
          }
          v40 = v39 - 1;
          if ( !v40 )
          {
            v22 = L"Display.Monitor";
            goto LABEL_118;
          }
          if ( v40 - 1 >= 2 )
            goto LABEL_88;
          goto LABEL_68;
        }
      }
    }
    else if ( v21 != 9 )
    {
      v30 = v21 - 1;
      if ( !v30 || (v31 = v30 - 1) == 0 || (v32 = v31 - 1) == 0 )
      {
        v22 = L"Communication.Headset.Bluetooth";
        goto LABEL_118;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        v22 = L"Audio.Microphone";
        goto LABEL_118;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        v22 = L"Audio.Speakers";
        goto LABEL_118;
      }
      v35 = v34 - 1;
      if ( !v35 )
      {
        v22 = L"Audio.Headphone";
        goto LABEL_118;
      }
      if ( v35 - 1 >= 2 )
        goto LABEL_88;
    }
    v22 = L"Multimedia";
    goto LABEL_118;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      3,
      45,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids);
  v8 = -1073741670;
LABEL_163:
  v57 = a1 + 2888;
  if ( *(_WORD *)(a1 + 2888) )
    BthEnumSetPdoInterfaceProperties(a1, v57);
  if ( v7 )
    ExFreePool(v7);
  if ( v3 )
    ExFreePool(v3);
  if ( v4 )
    ExFreePool(v4);
  if ( v5 )
    ExFreePool(v5);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(Size) = v8;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v57,
      3,
      60,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      Size);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001aaac  mov     [rsp-38h+arg_8], rbx
0x14001aab1  push    rbp
0x14001aab2  push    rsi
0x14001aab3  push    rdi
0x14001aab4  push    r12
0x14001aab6  push    r13
0x14001aab8  push    r14
0x14001aaba  push    r15
0x14001aabc  mov     rbp, rsp
0x14001aabf  sub     rsp, 50h
0x14001aac3  xor     eax, eax
0x14001aac5  mov     bl, dl
0x14001aac7  mov     r13d, eax
0x14001aaca  mov     [rbp+var_8], rax
0x14001aace  mov     r15d, eax
0x14001aad1  mov     [rbp+arg_18], rax
0x14001aad5  mov     esi, eax
0x14001aad7  mov     r14, rcx
0x14001aada  lea     r12, WPP_RECORDER_INITIALIZED
0x14001aae1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001aae8  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001aaef  jz      short loc_14001AB0E
0x14001aaf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aaf8  lea     r9d, [rsi+2Ch]
0x14001aafc  lea     r8d, [rsi+3]
0x14001ab00  mov     qword ptr [rsp+50h+Type], rax
0x14001ab05  mov     rcx, [rcx+40h]
0x14001ab09  call    WPP_RECORDER_SF_
0x14001ab0e  mov     edx, 1F2h
0x14001ab13  mov     ecx, 100h
0x14001ab18  mov     r8d, 4F4D5442h
0x14001ab1e  call    cs:__imp_ExAllocatePool2
0x14001ab25  nop     dword ptr [rax+rax+00h]
0x14001ab2a  xor     edx, edx
0x14001ab2c  mov     [rbp+var_10], rax
0x14001ab30  mov     rdi, rax
0x14001ab33  test    rax, rax
0x14001ab36  jnz     short loc_14001AB6F
0x14001ab38  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ab3f  jz      short loc_14001AB65
0x14001ab41  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab48  lea     r9d, [rax+2Dh]
0x14001ab4c  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001ab53  lea     r8d, [rdi+3]
0x14001ab57  mov     qword ptr [rsp+50h+Type], rax
0x14001ab5c  mov     rcx, [rcx+40h]
0x14001ab60  call    WPP_RECORDER_SF_
0x14001ab65  mov     ebx, 0C000009Ah
0x14001ab6a  jmp     loc_14001B49F
0x14001ab6f  or      r12, 0FFFFFFFFFFFFFFFFh
0x14001ab73  mov     r15d, 1
0x14001ab79  test    bl, bl
0x14001ab7b  jz      loc_14001ADCB
0x14001ab81  lea     rdx, [rbp+var_8]
0x14001ab85  mov     rcx, r14
0x14001ab88  call    BthEnumGenerateAepId
0x14001ab8d  mov     ebx, eax
0x14001ab8f  test    eax, eax
0x14001ab91  jns     short loc_14001ABD4
0x14001ab93  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001ab9a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001aba1  jz      short loc_14001ABCB
0x14001aba3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001abaa  lea     r9d, [r15+2Dh]
0x14001abae  mov     dword ptr [rsp+50h+Size], eax
0x14001abb2  lea     r8d, [r15+2]
0x14001abb6  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001abbd  mov     qword ptr [rsp+50h+Type], rax
0x14001abc2  mov     rcx, [rcx+40h]
0x14001abc6  call    WPP_RECORDER_SF_d
0x14001abcb  mov     r13, [rbp+var_8]
0x14001abcf  jmp     loc_14001B49B
0x14001abd4  mov     r13, [rbp+var_8]
0x14001abd8  lea     rdx, DEVPKEY_Aep_AepId; PropertyKey
0x14001abdf  mov     rcx, [r14+10h]; Pdo
0x14001abe3  xor     r9d, r9d; Flags
0x14001abe6  mov     [rsp+50h+Data], r13; Data
0x14001abeb  xor     r8d, r8d; Lcid
0x14001abee  mov     dword ptr [rsp+50h+Size], 6Eh ; 'n'; Size
0x14001abf6  mov     [rsp+50h+Type], 12h; Type
0x14001abfe  call    cs:__imp_IoSetDevicePropertyData
0x14001ac05  nop     dword ptr [rax+rax+00h]
0x14001ac0a  mov     ebx, eax
0x14001ac0c  test    eax, eax
0x14001ac0e  jns     short loc_14001AC55
0x14001ac10  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001ac17  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001ac1e  jz      loc_14001B49B
0x14001ac24  mov     r9d, 2Fh ; '/'
0x14001ac2a  mov     dword ptr [rsp+50h+Size], eax
0x14001ac2e  mov     r8d, 3
0x14001ac34  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac3b  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001ac42  mov     qword ptr [rsp+50h+Type], rax
0x14001ac47  mov     rcx, [rcx+40h]
0x14001ac4b  call    WPP_RECORDER_SF_d
0x14001ac50  jmp     loc_14001B49B
0x14001ac55  mov     rcx, [r14+0C0h]
0x14001ac5c  lea     rdx, [rbp+arg_18]
0x14001ac60  call    BthEnumGenerateAepDeviceAddress
0x14001ac65  mov     ebx, eax
0x14001ac67  test    eax, eax
0x14001ac69  jns     short loc_14001AC87
0x14001ac6b  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001ac72  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001ac79  jz      loc_14001B49B
0x14001ac7f  mov     r9d, 30h ; '0'
0x14001ac85  jmp     short loc_14001AC2A
0x14001ac87  mov     rax, [rbp+arg_18]
0x14001ac8b  lea     rdx, DEVPKEY_Aep_DeviceAddress; PropertyKey
0x14001ac92  mov     rcx, [r14+10h]; Pdo
0x14001ac96  xor     r9d, r9d; Flags
0x14001ac99  mov     [rsp+50h+Data], rax; Data
0x14001ac9e  xor     r8d, r8d; Lcid
0x14001aca1  mov     dword ptr [rsp+50h+Size], 24h ; '$'; Size
0x14001aca9  mov     [rsp+50h+Type], 12h; Type
0x14001acb1  call    cs:__imp_IoSetDevicePropertyData
0x14001acb8  nop     dword ptr [rax+rax+00h]
0x14001acbd  mov     ebx, eax
0x14001acbf  test    eax, eax
0x14001acc1  jns     short loc_14001ACE2
0x14001acc3  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001acca  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001acd1  jz      loc_14001B49B
0x14001acd7  mov     r9d, 31h ; '1'
0x14001acdd  jmp     loc_14001AC2A
0x14001ace2  mov     rcx, [r14+10h]; Pdo
0x14001ace6  lea     rax, aBluetooth_0; "Bluetooth"
0x14001aced  mov     [rsp+50h+Data], rax; Data
0x14001acf2  lea     rdx, DEVPKEY_DeviceContainer_DiscoveryMethod; PropertyKey
0x14001acf9  mov     dword ptr [rsp+50h+Size], 16h; Size
0x14001ad01  xor     r9d, r9d; Flags
0x14001ad04  xor     r8d, r8d; Lcid
0x14001ad07  mov     [rsp+50h+Type], 2012h; Type
0x14001ad0f  call    cs:__imp_IoSetDevicePropertyData
0x14001ad16  nop     dword ptr [rax+rax+00h]
0x14001ad1b  xor     edx, edx
0x14001ad1d  mov     ebx, eax
0x14001ad1f  test    eax, eax
0x14001ad21  jns     short loc_14001AD47
0x14001ad23  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001ad2a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001ad31  jz      loc_14001B49B
0x14001ad37  lea     r9d, [rdx+32h]
0x14001ad3b  mov     dword ptr [rsp+50h+Size], eax
0x14001ad3f  mov     r8, r15
0x14001ad42  jmp     loc_14001AC34
0x14001ad47  test    dword ptr [r14+0B8h], 8000000h
0x14001ad52  mov     byte ptr [rbp+UnicodeStringActualByteCount], r12b
0x14001ad56  jz      short loc_14001ADCB
0x14001ad58  mov     rcx, [r14+10h]; Pdo
0x14001ad5c  lea     rax, [rbp+UnicodeStringActualByteCount]
0x14001ad60  mov     [rsp+50h+Data], rax; Data
0x14001ad65  lea     rdx, DEVPKEY_Bluetooth_SecureConnectionPaired; PropertyKey
0x14001ad6c  mov     dword ptr [rsp+50h+Size], r15d; Size
0x14001ad71  xor     r9d, r9d; Flags
0x14001ad74  xor     r8d, r8d; Lcid
0x14001ad77  mov     [rsp+50h+Type], 11h; Type
0x14001ad7f  call    cs:__imp_IoSetDevicePropertyData
0x14001ad86  nop     dword ptr [rax+rax+00h]
0x14001ad8b  xor     edx, edx
0x14001ad8d  test    eax, eax
0x14001ad8f  jns     short loc_14001ADCB
0x14001ad91  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001ad98  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001ad9f  jz      short loc_14001ADCB
0x14001ada1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ada8  lea     r9d, [rdx+33h]
0x14001adac  mov     dword ptr [rsp+50h+Size], eax
0x14001adb0  lea     r8d, [rdx+3]
0x14001adb4  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001adbb  mov     qword ptr [rsp+50h+Type], rax
0x14001adc0  mov     rcx, [rcx+40h]
0x14001adc4  call    WPP_RECORDER_SF_d
0x14001adc9  xor     edx, edx
0x14001adcb  mov     eax, [r14+0B8h]
0x14001add2  test    al, 4
0x14001add4  jz      loc_14001AE8C
0x14001adda  mov     [rbp+UnicodeStringActualByteCount], edx
0x14001addd  lea     r9, [r14+0CCh]; UTF8StringSource
0x14001ade4  mov     rax, r12
0x14001ade7  inc     rax
0x14001adea  cmp     [r9+rax], dl
0x14001adee  jnz     short loc_14001ADE7
0x14001adf0  lea     r8, [rbp+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x14001adf4  mov     [rsp+50h+Type], eax; UTF8StringByteCount
0x14001adf8  mov     edx, 1F2h; UnicodeStringMaxByteCount
0x14001adfd  mov     rcx, rdi; UnicodeStringDestination
0x14001ae00  call    cs:__imp_RtlUTF8ToUnicodeN
0x14001ae07  nop     dword ptr [rax+rax+00h]
0x14001ae0c  mov     ebx, eax
0x14001ae0e  test    eax, eax
0x14001ae10  jns     short loc_14001AE35
0x14001ae12  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ae19  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ae20  jz      loc_14001B49B
0x14001ae26  mov     r9d, 34h ; '4'
0x14001ae2c  mov     dword ptr [rsp+50h+Size], ebx
0x14001ae30  jmp     loc_14001AC2E
0x14001ae35  mov     eax, [rbp+UnicodeStringActualByteCount]
0x14001ae38  lea     rdx, DEVPKEY_Device_FriendlyName; PropertyKey
0x14001ae3f  mov     rcx, [r14+10h]; Pdo
0x14001ae43  add     eax, 2
0x14001ae46  mov     [rsp+50h+Data], rdi; Data
0x14001ae4b  xor     r9d, r9d; Flags
0x14001ae4e  mov     dword ptr [rsp+50h+Size], eax; Size
0x14001ae52  xor     r8d, r8d; Lcid
0x14001ae55  mov     [rsp+50h+Type], 12h; Type
0x14001ae5d  call    cs:__imp_IoSetDevicePropertyData
0x14001ae64  nop     dword ptr [rax+rax+00h]
0x14001ae69  xor     r8d, r8d
0x14001ae6c  mov     ebx, eax
0x14001ae6e  test    eax, eax
0x14001ae70  jns     short loc_14001AE8F
0x14001ae72  lea     rax, WPP_RECORDER_INITIALIZED
0x14001ae79  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001ae80  jz      loc_14001B49B
0x14001ae86  lea     r9d, [r8+35h]
0x14001ae8a  jmp     short loc_14001AE2C
0x14001ae8c  xor     r8d, r8d
0x14001ae8f  mov     ecx, [r14+0C8h]
0x14001ae96  mov     eax, ecx
0x14001ae98  shr     eax, 2
0x14001ae9b  shr     ecx, 8
0x14001ae9e  and     eax, 3Fh
0x14001aea1  and     ecx, 1Fh
0x14001aea4  sub     ecx, r15d
0x14001aea7  jz      loc_14001B0DB
0x14001aead  sub     ecx, r15d
0x14001aeb0  jz      loc_14001B0B5
0x14001aeb6  sub     ecx, r15d
0x14001aeb9  jz      loc_14001B0AC
0x14001aebf  sub     ecx, r15d
0x14001aec2  jz      loc_14001AFE7
0x14001aec8  sub     ecx, r15d
0x14001aecb  jz      loc_14001AFAD
0x14001aed1  sub     ecx, r15d
0x14001aed4  jz      loc_14001AF61
0x14001aeda  sub     ecx, r15d
0x14001aedd  jz      loc_14001B022
0x14001aee3  sub     ecx, r15d
0x14001aee6  jz      loc_14001B022
0x14001aeec  cmp     ecx, r15d
0x14001aeef  jz      short loc_14001AEFD
0x14001aef1  lea     rdi, aUnknown; "Unknown"
0x14001aef8  jmp     loc_14001B128
0x14001aefd  sub     eax, r15d
0x14001af00  jz      short loc_14001AF55
0x14001af02  sub     eax, r15d
0x14001af05  jz      short loc_14001AF49
0x14001af07  sub     eax, r15d
0x14001af0a  jz      short loc_14001AF49
0x14001af0c  sub     eax, r15d
0x14001af0f  jz      short loc_14001AF3D
0x14001af11  sub     eax, r15d
0x14001af14  jz      short loc_14001AF49
0x14001af16  sub     eax, r15d
0x14001af19  jz      short loc_14001AF31
0x14001af1b  sub     eax, r15d
0x14001af1e  jz      short loc_14001AF49
0x14001af20  cmp     eax, r15d
0x14001af23  jnz     short loc_14001AF49
0x14001af25  lea     rdi, aHealthPedomete; "Health.Pedometer"
0x14001af2c  jmp     loc_14001B128
0x14001af31  lea     rdi, aHealthHeartrat; "Health.HeartRate"
0x14001af38  jmp     loc_14001B128
0x14001af3d  lea     rdi, aHealthBloodglu; "Health.BloodGlucose"
0x14001af44  jmp     loc_14001B128
0x14001af49  lea     rdi, aHealth; "Health"
0x14001af50  jmp     loc_14001B128
0x14001af55  lea     rdi, aHealthBloodpre; "Health.BloodPressure"
0x14001af5c  jmp     loc_14001B128
0x14001af61  test    al, 20h
0x14001af63  jz      short loc_14001AF71
0x14001af65  lea     rdi, aPrintfaxPrinte; "PrintFax.Printer"
0x14001af6c  jmp     loc_14001B128
0x14001af71  test    al, 10h
0x14001af73  jz      short loc_14001AF81
0x14001af75  lea     rdi, aImagingScanner; "Imaging.Scanner"
0x14001af7c  jmp     loc_14001B128
0x14001af81  test    al, 4
0x14001af83  jz      short loc_14001AF91
0x14001af85  lea     rdi, aDisplay; "Display"
0x14001af8c  jmp     loc_14001B128
0x14001af91  test    al, 8
0x14001af93  lea     rdi, aOther; "Other"
0x14001af9a  lea     rax, aImagingCamera; "Imaging.Camera"
0x14001afa1  cmovz   rax, rdi
0x14001afa5  mov     rdi, rax
0x14001afa8  jmp     loc_14001B128
0x14001afad  test    al, 10h
0x14001afaf  jz      short loc_14001AFBD
0x14001afb1  lea     rdi, aInputKeyboard; "Input.Keyboard"
0x14001afb8  jmp     loc_14001B128
0x14001afbd  test    al, 20h
0x14001afbf  jz      short loc_14001AFCD
0x14001afc1  lea     rdi, aInputMouse; "Input.Mouse"
0x14001afc8  jmp     loc_14001B128
0x14001afcd  cmp     eax, 2
0x14001afd0  lea     rdi, aInputGaming; "Input.Gaming"
  ... truncated ...
```
