# Controller_Create

- ea: `0x140074588`
- end: `0x14007547b`
- name: `Controller_Create`
- size: `3827`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14007a250`

## callees

- `0x14001ac48`
- `0x14001ad0c`
- `0x1400290e0`
- `0x14003bb94`
- `0x1400408a8`
- `0x140042894`
- `0x140042908`
- `0x14004464c`
- `0x140056ba4`
- `0x140059970`
- `0x1400599b0`
- `0x140059a80`
- `0x140059d80`
- `0x140074588`
- `0x140075484`
- `0x1400766d8`
- `0x1400775bc`
- `0x1400777b8`
- `0x140078ad8`
- `0x140078d3c`
- `0x140078fb0`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x140075103`
- `ntoskrnl!KeInitializeMutex` at `0x140075103`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140074c13`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140074c13`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007511a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007511a`
- `HAL!KeQueryPerformanceCounter` at `0x140075340`
- `HAL!KeQueryPerformanceCounter` at `0x140075340`

## pseudocode

```c
__int64 __fastcall Controller_Create(__int64 a1, __int64 a2, int a3, __int64 *a4)
{
  __int64 v8; // rax
  char IsSecureDevice; // r12
  int v10; // r15d
  const char *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rax
  char *v14; // rcx
  char *v15; // rax
  int DeviceEnumerator; // eax
  int v17; // edx
  int AcpiData; // ebx
  int v19; // r9d
  int v20; // r11d
  unsigned int v21; // r10d
  unsigned int v22; // r10d
  int v23; // eax
  __int64 v24; // rdi
  __int64 v25; // rax
  bool v26; // zf
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  struct _DEVICE_OBJECT *v29; // rax
  __int64 v30; // rbx
  int v31; // edx
  __int64 v32; // rcx
  int v33; // eax
  __int128 v35; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+50h] [rbp-B0h]
  __int128 v37; // [rsp+60h] [rbp-A0h]
  __int64 *v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  __int128 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h]
  int v42; // [rsp+98h] [rbp-68h] BYREF
  ULONG RequiredSize; // [rsp+9Ch] [rbp-64h] BYREF
  __int128 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  int v47; // [rsp+C8h] [rbp-38h]
  ULONG Type; // [rsp+CCh] [rbp-34h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v50; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v51; // [rsp+E8h] [rbp-18h]
  __int128 v52; // [rsp+F8h] [rbp-8h]
  __int64 v53; // [rsp+108h] [rbp+8h]
  _QWORD v54[32]; // [rsp+110h] [rbp+10h] BYREF
  char pszSrc[8]; // [rsp+210h] [rbp+110h] BYREF
  char v56[4]; // [rsp+218h] [rbp+118h] BYREF
  __int16 v57; // [rsp+21Ch] [rbp+11Ch]
  char v58; // [rsp+21Eh] [rbp+11Eh]
  __int128 v59; // [rsp+220h] [rbp+120h]
  __int128 v60; // [rsp+230h] [rbp+130h]
  char pszDest[16]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v62; // [rsp+250h] [rbp+150h]
  _BYTE Src[400]; // [rsp+260h] [rbp+160h] BYREF

  v47 = a3;
  memset(v54, 0, 0xF8u);
  LODWORD(v38) = 0;
  LODWORD(v46) = 0;
  LODWORD(v41) = 0;
  v62 = 0;
  *(_QWORD *)pszSrc = 0;
  *(_DWORD *)v56 = 0;
  v57 = 0;
  v58 = 0;
  v35 = 0;
  v39 = 0;
  v36 = 0;
  RequiredSize = 0;
  v37 = 0;
  Type = 0;
  v44 = 0;
  v42 = 0;
  v45 = 0;
  v49 = -1;
  v40 = 0;
  v59 = 0;
  v60 = 0;
  *(_OWORD *)pszDest = 0;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C2C0);
  IsSecureDevice = Device_IsSecureDevice(v8);
  *(_QWORD *)pszSrc = 0;
  *(_DWORD *)v56 = 0;
  v57 = 0;
  v58 = 0;
  v53 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  memset(Src, 0, sizeof(Src));
  *(_QWORD *)&v59 = 56;
  v10 = 2;
  pszDest[0] = 0;
  HIDWORD(v60) = 16;
  *(_QWORD *)&v60 = 0;
  BYTE8(v60) = 0;
  v62 = 0x200000002LL;
  *((_QWORD *)&v59 + 1) = 512;
  RtlStringCchPrintfA(pszDest, 0x10u, "%02d RUNDOWN", a3);
  v35 = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v35) = -1;
    else
      LODWORD(v35) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v35) = 56;
  }
  v38 = off_14006C310;
  *((_QWORD *)&v36 + 1) = 0x100000001LL;
  *((_QWORD *)&v35 + 1) = Controller_WdfEvtCleanupCallback;
  memset(v54, 0, 0xF8u);
  v54[0] = -4294967048LL;
  *(_QWORD *)((char *)&v54[9] + 4) = 0x7FFFFFFF7FFFFFFFLL;
  v11 = "USBXHCI";
  v12 = 40;
  v13 = 2147483646;
  LODWORD(v54[9]) = 0;
  v14 = (char *)&v54[14] + 3;
  BYTE4(v54[12]) = 0;
  BYTE1(v54[13]) = 0;
  BYTE6(v54[13]) = 0;
  WORD2(v54[10]) = 0;
  v54[11] = 0;
  LODWORD(v54[12]) = 0;
  do
  {
    if ( !v13 )
      break;
    if ( !*v11 )
      break;
    *v14++ = *v11++;
    --v13;
    --v12;
  }
  while ( v12 );
  v15 = v14 - 1;
  if ( v12 )
    v15 = v14;
  *v15 = 0;
  v54[4] = UsbDevice_UcxEvtDeviceAdd;
  v54[3] = Controller_UcxEvtGetCurrentFrameNumber;
  v54[5] = Controller_UcxEvtReset;
  v54[1] = Controller_UcxEvtQueryUsbCapability;
  v54[28] = Controller_UcxEvtStartTrackingForTimeSync;
  v54[29] = Controller_UcxEvtStopTrackingForTimeSync;
  v54[30] = Controller_UcxEvtGetFrameNumberAndQpcForTimeSync;
  if ( IsSecureDevice )
  {
    memset(&v54[6], 0, 24);
  }
  else
  {
    v54[7] = Crashdump_UcxEvtGetDumpData;
    v54[8] = Crashdump_UcxEvtFreeDumpData;
    v54[6] = Controller_UcxEvtEnableForwardProgress;
  }
  DeviceEnumerator = Controller_GetDeviceEnumerator(a1, a2, v11);
  if ( !DeviceEnumerator )
  {
    v10 = 1;
    AcpiData = Controller_RetrievePciData(a1, a2, &v50, &v49);
    if ( AcpiData < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = 99;
LABEL_19:
        LOBYTE(v17) = 2;
LABEL_20:
        WPP_RECORDER_SF_d(a2, v17, 4, v19, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, AcpiData);
        return (unsigned int)AcpiData;
      }
      return (unsigned int)AcpiData;
    }
    v20 = 2;
    goto LABEL_32;
  }
  if ( DeviceEnumerator == 1 )
  {
    AcpiData = Controller_RetrieveAcpiData(a1, a2, pszSrc);
    if ( AcpiData < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)AcpiData;
      v19 = 100;
      goto LABEL_25;
    }
  }
  else
  {
    AcpiData = Controller_RetrieveUrsData(
                 a1,
                 a2,
                 (unsigned int)&v42,
                 (unsigned int)pszSrc,
                 (__int64)&v50,
                 (__int64)&v49);
    if ( AcpiData < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)AcpiData;
      v19 = 101;
LABEL_25:
      LOBYTE(v17) = 2;
      goto LABEL_20;
    }
    v10 = v42;
    v20 = 2;
    if ( v42 != 2 )
    {
LABEL_32:
      *(_QWORD *)((char *)&v54[9] + 4) = v50;
      WORD2(v54[10]) = WORD4(v50);
      v54[11] = __PAIR64__(v51, HIDWORD(v50));
      LODWORD(v54[12]) = DWORD1(v51);
      LODWORD(v54[9]) = 1;
      goto LABEL_34;
    }
  }
  LODWORD(v54[9]) = 2;
  RtlStringCchCopyA((NTSTRSAFE_PSTR)&v54[12] + 4, 5u, pszSrc);
  RtlStringCchCopyA((NTSTRSAFE_PSTR)&v54[13] + 1, v21, &pszSrc[5]);
  RtlStringCchCopyA((NTSTRSAFE_PSTR)&v54[13] + 6, v22, &v56[2]);
LABEL_34:
  v23 = DWORD2(v36);
  if ( IsSecureDevice )
    v23 = v20;
  DWORD2(v36) = v23;
  AcpiData = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *, __int128 *, __int64 *))qword_14006CCC8)(
               UcxDriverGlobals,
               a1,
               v54,
               &v35,
               &v39);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 102;
    goto LABEL_19;
  }
  v24 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
          WdfDriverGlobals,
          v39,
          off_14006C310);
  *(_QWORD *)(v24 + 32) = v24 + 24;
  *(_QWORD *)(v24 + 24) = v24 + 24;
  *(_QWORD *)v24 = a1;
  *(_QWORD *)(v24 + 8) = v39;
  *(_QWORD *)(v24 + 728) = v49;
  *(_QWORD *)(v24 + 72) = a2;
  *(_DWORD *)(v24 + 176) = v47;
  *(_DWORD *)(v24 + 644) = v10;
  *(_BYTE *)(v24 + 1041) = IsSecureDevice;
  v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
          WdfDriverGlobals,
          a1,
          off_14006C2C0);
  v26 = *(_DWORD *)(v24 + 644) == 1;
  *(_QWORD *)(v24 + 112) = *(_QWORD *)(v25 + 96);
  if ( v26 )
  {
    v27 = v51;
    *(_OWORD *)(v24 + 648) = v50;
    v28 = v52;
    *(_OWORD *)(v24 + 664) = v27;
    *(_QWORD *)&v27 = v53;
    *(_OWORD *)(v24 + 680) = v28;
    *(_QWORD *)(v24 + 696) = v27;
    *(_BYTE *)(v24 + 704) = 0;
    *(_BYTE *)(v24 + 709) = 0;
    *(_BYTE *)(v24 + 714) = 0;
  }
  else
  {
    *(_QWORD *)(v24 + 704) = *(_QWORD *)pszSrc;
    *(_DWORD *)(v24 + 712) = *(_DWORD *)v56;
    *(_WORD *)(v24 + 716) = v57;
    *(_BYTE *)(v24 + 718) = v58;
    *(_DWORD *)(v24 + 648) = 0x7FFFFFFF;
    *(_DWORD *)(v24 + 652) = 0x7FFFFFFF;
    *(_WORD *)(v24 + 656) = 0;
    *(_QWORD *)(v24 + 660) = 0;
    *(_DWORD *)(v24 + 668) = 0;
  }
  v29 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 264))(
                                   WdfDriverGlobals,
                                   a1);
  if ( IoGetDevicePropertyData(v29, &DEVPKEY_Device_InstanceId, 0, 0, 0x190u, Src, &RequiredSize, &Type) < 0 )
    *(_WORD *)(v24 + 244) = 0;
  else
    memmove((void *)(v24 + 244), Src, RequiredSize);
  Controller_SetLogIdentifier(v24);
  *a4 = v24;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v35) = -1;
    else
      LODWORD(v35) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v35) = 56;
  }
  v38 = off_14006BED8;
  *((_QWORD *)&v36 + 1) = 0x100000001LL;
  v46 = 0;
  v44 = 0;
  v45 = 0;
  if ( IsSecureDevice )
  {
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x37 )
        LODWORD(v44) = -1;
      else
        LODWORD(v44) = *(_DWORD *)(WdfStructures + 440);
    }
    else
    {
      LODWORD(v44) = 40;
    }
    LODWORD(v45) = 0;
    DWORD2(v36) = 2;
  }
  else
  {
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x37 )
        LODWORD(v44) = -1;
      else
        LODWORD(v44) = *(_DWORD *)(WdfStructures + 440);
    }
    else
    {
      LODWORD(v44) = 40;
    }
    LODWORD(v45) = 5000;
  }
  *((_QWORD *)&v44 + 1) = Controller_WdfEvtWatchdogTimerFunc;
  *(_QWORD *)&v37 = v39;
  BYTE4(v45) = 1;
  DWORD2(v45) = 1000;
  AcpiData = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 2544))(
               WdfDriverGlobals,
               &v44,
               &v35,
               v24 + 760);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 103;
    goto LABEL_19;
  }
  *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
               WdfDriverGlobals,
               *(_QWORD *)(v24 + 760),
               off_14006BED8) = MEMORY[0xFFFFF78000000014];
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v35) = -1;
    else
      LODWORD(v35) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v35) = 56;
  }
  *(_QWORD *)&v37 = v39;
  *((_QWORD *)&v36 + 1) = 0x100000001LL;
  v41 = 0;
  v40 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x43 )
      LODWORD(v40) = -1;
    else
      LODWORD(v40) = *(_DWORD *)(WdfStructures + 536);
  }
  else
  {
    LODWORD(v40) = 24;
  }
  *((_QWORD *)&v40 + 1) = Controller_IdleTimeoutUpdateWorker;
  LOBYTE(v41) = 1;
  AcpiData = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 3032))(
               WdfDriverGlobals,
               &v40,
               &v35,
               v24 + 1008);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 104;
    goto LABEL_19;
  }
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v35) = -1;
    else
      LODWORD(v35) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v35) = 56;
  }
  *(_QWORD *)&v37 = v39;
  *((_QWORD *)&v36 + 1) = 0x100000001LL;
  v41 = 0;
  v40 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x43 )
      LODWORD(v40) = -1;
    else
      LODWORD(v40) = *(_DWORD *)(WdfStructures + 536);
  }
  else
  {
    LODWORD(v40) = 24;
  }
  *((_QWORD *)&v40 + 1) = Controller_AudioOffloadWnfStateUpdateWorker;
  LOBYTE(v41) = 1;
  AcpiData = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 3032))(
               WdfDriverGlobals,
               &v40,
               &v35,
               v24 + 1280);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 105;
    goto LABEL_19;
  }
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v35) = -1;
    else
      LODWORD(v35) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v35) = 56;
  }
  v38 = off_14006BFA0;
  *(_QWORD *)&v37 = v39;
  *((_QWORD *)&v36 + 1) = 0x100000001LL;
  v41 = 0;
  v40 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x43 )
      LODWORD(v40) = -1;
    else
      LODWORD(v40) = *(_DWORD *)(WdfStructures + 536);
  }
  else
  {
    LODWORD(v40) = 24;
  }
  *((_QWORD *)&v40 + 1) = Controller_TelemetryReportWorker;
  LOBYTE(v41) = 1;
  AcpiData = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 3032))(
               WdfDriverGlobals,
               &v40,
               &v35,
               v24 + 768);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 106;
    goto LABEL_19;
  }
  v30 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
          WdfDriverGlobals,
          *(_QWORD *)(v24 + 768),
          off_14006BFA0);
  KeInitializeMutex((PRKMUTEX)(v30 + 24), 0);
  *(_QWORD *)(v30 + 8) = v30;
  *(_QWORD *)v30 = v30;
  KeInitializeSpinLock((PKSPIN_LOCK)(v30 + 16));
  AcpiData = DynamicLock_Create(v39, a2, IsSecureDevice != 0, v24 + 1120);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 107;
    goto LABEL_19;
  }
  v35 = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v35) = -1;
    else
      LODWORD(v35) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v35) = 56;
  }
  *(_QWORD *)&v37 = v39;
  *((_QWORD *)&v36 + 1) = 0x100000001LL;
  AcpiData = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64))(WdfFunctions_01033 + 104))(
               WdfDriverGlobals,
               &v35,
               v24 + 1136);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 108;
    goto LABEL_19;
  }
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v35) = -1;
    else
      LODWORD(v35) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v35) = 56;
  }
  v38 = off_14006BFA0;
  *(_QWORD *)&v37 = v39;
  *((_QWORD *)&v36 + 1) = 0x100000001LL;
  v41 = 0;
  v40 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x43 )
      LODWORD(v40) = -1;
    else
      LODWORD(v40) = *(_DWORD *)(WdfStructures + 536);
  }
  else
  {
    LODWORD(v40) = 24;
  }
  *((_QWORD *)&v40 + 1) = Controller_TimeSyncStartTrackingWorker;
  LOBYTE(v41) = 1;
  AcpiData = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033 + 3032))(
               WdfDriverGlobals,
               &v40,
               &v35,
               v24 + 1160);
  if ( AcpiData < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)AcpiData;
    v19 = 109;
    goto LABEL_19;
  }
  *(_QWORD *)(v24 + 1152) = v24 + 1144;
  *(_QWORD *)(v24 + 1144) = v24 + 1144;
  *(_BYTE *)(v24 + 1168) = 0;
  *(_BYTE *)(v24 + 1112) = 0;
  KeQueryPerformanceCounter((PLARGE_INTEGER)(v24 + 1232));
  *(_QWORD *)(v24 + 1240) = 0;
  *(_QWORD *)(v24 + 1248) = 0;
  *(_DWORD *)(v24 + 1256) = 0;
  *(_DWORD *)(v24 + 1128) = 0;
  Controller_QuerySupportedDSMs(v24);
  *(_OWORD *)(v24 + 736) = 0;
  Controller_PopulateDeviceFlags(v24);
  if ( (*(_BYTE *)(v24 + 736) & 0x10) != 0 )
  {
    AcpiData = -1073741637;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v31) = 2;
      WPP_RECORDER_SF_(a2, v31, 4, 110, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    }
  }
  else
  {
    v32 = v24;
    if ( IsSecureDevice )
    {
      AcpiData = Controller_ReferenceTrustletProcess(v24);
      if ( AcpiData < 0 )
        return (unsigned int)AcpiData;
      AcpiData = Controller_CreateSecureObject(v24);
      if ( AcpiData < 0 )
        return (unsigned int)AcpiData;
      v32 = v24;
      v33 = (*(_DWORD *)(v24 + 1056) != 1) + 1;
    }
    else
    {
      v33 = 0;
    }
    *(_DWORD *)(v32 + 1052) = v33;
    *(_QWORD *)(v24 + 1084) = 0;
    AcpiData = DynamicLock_Create(v39, a2, 0, v24 + 1096);
    if ( AcpiData >= 0 )
      return (unsigned int)Controller_AllocateIrqlTrackingArray(v24);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = 111;
      goto LABEL_19;
    }
  }
  return (unsigned int)AcpiData;
}

```

## disassembly

```asm
0x140074588  push    rbp
0x14007458a  push    rbx
0x14007458b  push    rsi
0x14007458c  push    rdi
0x14007458d  push    r12
0x14007458f  push    r13
0x140074591  push    r14
0x140074593  push    r15
0x140074595  lea     rbp, [rsp-308h]
0x14007459d  sub     rsp, 408h
0x1400745a4  mov     rax, cs:__security_cookie
0x1400745ab  xor     rax, rsp
0x1400745ae  mov     [rbp+340h+var_50], rax
0x1400745b5  mov     ebx, r8d
0x1400745b8  mov     rsi, rdx
0x1400745bb  mov     r14, rcx
0x1400745be  mov     [rbp+340h+var_378], ebx
0x1400745c1  xor     edx, edx; Val
0x1400745c3  lea     rcx, [rbp+340h+var_330]; void *
0x1400745c7  mov     r8d, 0F8h; Size
0x1400745cd  mov     r13, r9
0x1400745d0  call    memset
0x1400745d5  mov     r8, cs:off_14006C2C0
0x1400745dc  xor     eax, eax
0x1400745de  mov     rcx, cs:WdfDriverGlobals
0x1400745e5  xorps   xmm0, xmm0
0x1400745e8  xor     edi, edi
0x1400745ea  mov     dword ptr [rsp+440h+var_3D0], eax
0x1400745ee  mov     dword ptr [rbp+340h+var_380], eax
0x1400745f1  mov     rdx, r14
0x1400745f4  mov     dword ptr [rbp+340h+var_3B0], eax
0x1400745f7  mov     [rbp+340h+var_1F0], rax
0x1400745fe  mov     qword ptr [rbp+340h+pszSrc], rax
0x140074605  mov     dword ptr [rbp+340h+var_228], eax
0x14007460b  mov     [rbp+340h+var_224], ax
0x140074612  mov     [rbp+340h+var_222], al
0x140074618  mov     rax, cs:WdfFunctions_01033
0x14007461f  movups  [rsp+440h+var_400], xmm0
0x140074624  mov     [rsp+440h+var_3C8], rdi
0x140074629  movups  [rsp+440h+var_3F0], xmm0
0x14007462e  mov     [rbp+340h+var_3A4], edi
0x140074631  movups  [rsp+440h+var_3E0], xmm0
0x140074636  mov     [rbp+340h+var_374], edi
0x140074639  movups  [rbp+340h+var_3A0], xmm0
0x14007463d  mov     [rbp+340h+var_3A8], edi
0x140074640  movups  [rbp+340h+var_390], xmm0
0x140074644  mov     [rbp+340h+var_370], 0FFFFFFFFFFFFFFFFh
0x14007464c  movups  [rbp+340h+var_3C0], xmm0
0x140074650  movups  [rbp+340h+var_220], xmm0
0x140074657  movups  [rbp+340h+var_210], xmm0
0x14007465e  movups  xmmword ptr [rbp+340h+pszDest], xmm0
0x140074665  mov     rax, [rax+650h]
0x14007466c  call    _guard_dispatch_icall
0x140074671  mov     rcx, rax
0x140074674  call    Device_IsSecureDevice
0x140074679  xorps   xmm0, xmm0
0x14007467c  lea     rcx, [rbp+340h+Src]; void *
0x140074683  mov     r12b, al
0x140074686  xor     edx, edx; Val
0x140074688  xor     eax, eax
0x14007468a  mov     r8d, 190h; Size
0x140074690  mov     qword ptr [rbp+340h+pszSrc], rax
0x140074697  mov     dword ptr [rbp+340h+var_228], eax
0x14007469d  mov     [rbp+340h+var_224], ax
0x1400746a4  mov     [rbp+340h+var_222], al
0x1400746aa  mov     [rbp+340h+var_338], rax
0x1400746ae  movups  [rbp+340h+var_368], xmm0
0x1400746b2  movups  [rbp+340h+var_358], xmm0
0x1400746b6  movups  [rbp+340h+var_348], xmm0
0x1400746ba  call    memset
0x1400746bf  lea     eax, [rdi+10h]
0x1400746c2  mov     qword ptr [rbp+340h+var_220], 38h ; '8'
0x1400746cd  lea     r15d, [rdi+2]
0x1400746d1  mov     [rbp+340h+pszDest], dil
0x1400746d8  mov     edx, eax; cchDest
0x1400746da  mov     dword ptr [rbp+340h+var_210+0Ch], eax
0x1400746e0  mov     r9d, ebx
0x1400746e3  mov     qword ptr [rbp+340h+var_210], rdi
0x1400746ea  lea     r8, a02dRundown; "%02d RUNDOWN"
0x1400746f1  mov     byte ptr [rbp+340h+var_210+8], dil
0x1400746f8  lea     rcx, [rbp+340h+pszDest]; pszDest
0x1400746ff  mov     dword ptr [rbp+340h+var_1F0], r15d
0x140074706  mov     dword ptr [rbp+340h+var_1F0+4], r15d
0x14007470d  mov     qword ptr [rbp+340h+var_220+8], 200h
0x140074718  call    RtlStringCchPrintfA
0x14007471d  xorps   xmm0, xmm0
0x140074720  xor     eax, eax
0x140074722  cmp     cs:WdfClientVersionHigherThanFramework, dil
0x140074729  movups  [rsp+440h+var_400], xmm0
0x14007472e  mov     [rsp+440h+var_3D0], rax
0x140074733  movups  [rsp+440h+var_3F0], xmm0
0x140074738  movups  [rsp+440h+var_3E0], xmm0
0x14007473d  jz      short loc_140074765
0x14007473f  cmp     cs:WdfStructureCount, 26h ; '&'
0x140074746  jbe     short loc_14007475B
0x140074748  mov     rax, cs:WdfStructures
0x14007474f  mov     ecx, [rax+130h]
0x140074755  mov     dword ptr [rsp+440h+var_400], ecx
0x140074759  jmp     short loc_14007476D
0x14007475b  mov     dword ptr [rsp+440h+var_400], 0FFFFFFFFh
0x140074763  jmp     short loc_14007476D
0x140074765  mov     dword ptr [rsp+440h+var_400], 38h ; '8'
0x14007476d  mov     rax, cs:off_14006C310
0x140074774  lea     rcx, [rbp+340h+var_330]; void *
0x140074778  mov     [rsp+440h+var_3D0], rax
0x14007477d  mov     ebx, 1
0x140074782  lea     rax, Controller_WdfEvtCleanupCallback
0x140074789  mov     dword ptr [rsp+440h+var_3F0+8], ebx
0x14007478d  xor     edx, edx; Val
0x14007478f  mov     qword ptr [rsp+440h+var_400+8], rax
0x140074794  mov     r8d, 0F8h; Size
0x14007479a  mov     dword ptr [rsp+440h+var_3F0+0Ch], ebx
0x14007479e  call    memset
0x1400747a3  mov     eax, 7FFFFFFFh
0x1400747a8  mov     [rbp+340h+var_330], 0F8h
0x1400747af  mov     dword ptr [rbp+340h+var_2E4], eax
0x1400747b2  lea     r8, aUsbxhci_0; "USBXHCI"
0x1400747b9  mov     dword ptr [rbp+340h+var_2E4+4], eax
0x1400747bc  lea     edx, [rbx+27h]
0x1400747bf  mov     eax, 7FFFFFFEh
0x1400747c4  mov     [rbp+340h+var_32C], 0FFFFFFFFh
0x1400747cb  mov     [rbp+340h+var_2E8], edi
0x1400747ce  lea     rcx, [rbp+340h+var_2BD]
0x1400747d5  mov     [rbp+340h+var_2CC], dil
0x1400747d9  mov     [rbp+340h+var_2C7], dil
0x1400747dd  mov     [rbp+340h+var_2C2], dil
0x1400747e1  mov     [rbp+340h+var_2DC], di
0x1400747e5  mov     [rbp+340h+var_2D8], rdi
0x1400747e9  mov     [rbp+340h+var_2D0], edi
0x1400747ec  test    rax, rax
0x1400747ef  jz      short loc_14007480A
0x1400747f1  mov     r9b, [r8]
0x1400747f4  test    r9b, r9b
0x1400747f7  jz      short loc_14007480A
0x1400747f9  mov     [rcx], r9b
0x1400747fc  add     r8, rbx
0x1400747ff  add     rcx, rbx
0x140074802  sub     rax, rbx
0x140074805  sub     rdx, rbx
0x140074808  jnz     short loc_1400747EC
0x14007480a  test    rdx, rdx
0x14007480d  lea     rax, [rcx-1]
0x140074811  cmovnz  rax, rcx
0x140074815  mov     [rax], dil
0x140074818  lea     rax, UsbDevice_UcxEvtDeviceAdd
0x14007481f  mov     [rbp+340h+var_310], rax
0x140074823  lea     rax, Controller_UcxEvtGetCurrentFrameNumber
0x14007482a  mov     [rbp+340h+var_318], rax
0x14007482e  lea     rax, Controller_UcxEvtReset
0x140074835  mov     [rbp+340h+var_308], rax
0x140074839  lea     rax, Controller_UcxEvtQueryUsbCapability
0x140074840  mov     [rbp+340h+var_328], rax
0x140074844  lea     rax, Controller_UcxEvtStartTrackingForTimeSync
0x14007484b  mov     [rbp+340h+var_250], rax
0x140074852  lea     rax, Controller_UcxEvtStopTrackingForTimeSync
0x140074859  mov     [rbp+340h+var_248], rax
0x140074860  lea     rax, Controller_UcxEvtGetFrameNumberAndQpcForTimeSync
0x140074867  mov     [rbp+340h+var_240], rax
0x14007486e  test    r12b, r12b
0x140074871  jnz     short loc_140074896
0x140074873  lea     rax, Crashdump_UcxEvtGetDumpData
0x14007487a  mov     [rbp+340h+var_2F8], rax
0x14007487e  lea     rax, Crashdump_UcxEvtFreeDumpData
0x140074885  mov     [rbp+340h+var_2F0], rax
0x140074889  lea     rax, Controller_UcxEvtEnableForwardProgress
0x140074890  mov     [rbp+340h+var_300], rax
0x140074894  jmp     short loc_1400748A2
0x140074896  mov     [rbp+340h+var_2F8], rdi
0x14007489a  mov     [rbp+340h+var_2F0], rdi
0x14007489e  mov     [rbp+340h+var_300], rdi
0x1400748a2  mov     rdx, rsi
0x1400748a5  mov     rcx, r14
0x1400748a8  call    Controller_GetDeviceEnumerator
0x1400748ad  mov     rdx, rsi
0x1400748b0  mov     rcx, r14
0x1400748b3  test    eax, eax
0x1400748b5  jnz     short loc_140074910
0x1400748b7  lea     r9, [rbp+340h+var_370]
0x1400748bb  mov     r15d, ebx
0x1400748be  lea     r8, [rbp+340h+var_368]
0x1400748c2  call    Controller_RetrievePciData
0x1400748c7  mov     ebx, eax
0x1400748c9  test    eax, eax
0x1400748cb  jns     loc_14007499E
0x1400748d1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400748d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400748df  jz      loc_140075455
0x1400748e5  mov     r9d, 63h ; 'c'
0x1400748eb  mov     dl, 2
0x1400748ed  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x1400748f4  mov     dword ptr [rsp+440h+Data], ebx
0x1400748f8  mov     r8d, 4
0x1400748fe  mov     qword ptr [rsp+440h+Size], rax
0x140074903  mov     rcx, rsi
0x140074906  call    WPP_RECORDER_SF_d
0x14007490b  jmp     loc_140075455
0x140074910  cmp     eax, ebx
0x140074912  jnz     short loc_140074949
0x140074914  lea     r8, [rbp+340h+pszSrc]
0x14007491b  call    Controller_RetrieveAcpiData
0x140074920  mov     ebx, eax
0x140074922  test    eax, eax
0x140074924  jns     loc_1400749D3
0x14007492a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140074931  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140074938  jz      loc_140075455
0x14007493e  mov     r9d, 64h ; 'd'
0x140074944  mov     dl, r15b
0x140074947  jmp     short loc_1400748ED
0x140074949  lea     rax, [rbp+340h+var_370]
0x14007494d  mov     [rsp+440h+Data], rax
0x140074952  lea     r9, [rbp+340h+pszSrc]
0x140074959  lea     rax, [rbp+340h+var_368]
0x14007495d  lea     r8, [rbp+340h+var_3A8]
0x140074961  mov     qword ptr [rsp+440h+Size], rax
0x140074966  call    Controller_RetrieveUrsData
0x14007496b  mov     ebx, eax
0x14007496d  test    eax, eax
0x14007496f  jns     short loc_14007498D
0x140074971  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140074978  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007497f  jz      loc_140075455
0x140074985  mov     r9d, 65h ; 'e'
0x14007498b  jmp     short loc_140074944
0x14007498d  mov     r15d, [rbp+340h+var_3A8]
0x140074991  mov     r11d, 2
0x140074997  cmp     r15d, r11d
0x14007499a  jz      short loc_1400749D9
0x14007499c  jmp     short loc_1400749A4
0x14007499e  mov     r11d, 2
0x1400749a4  mov     eax, dword ptr [rbp+340h+var_368]
0x1400749a7  mov     dword ptr [rbp+340h+var_2E4], eax
0x1400749aa  mov     eax, dword ptr [rbp+340h+var_368+4]
0x1400749ad  mov     dword ptr [rbp+340h+var_2E4+4], eax
0x1400749b0  movzx   eax, word ptr [rbp+340h+var_368+8]
0x1400749b4  mov     [rbp+340h+var_2DC], ax
0x1400749b8  mov     eax, dword ptr [rbp+340h+var_368+0Ch]
0x1400749bb  mov     dword ptr [rbp+340h+var_2D8], eax
0x1400749be  mov     eax, dword ptr [rbp+340h+var_358]
0x1400749c1  mov     dword ptr [rbp+340h+var_2D8+4], eax
0x1400749c4  mov     eax, dword ptr [rbp+340h+var_358+4]
0x1400749c7  mov     [rbp+340h+var_2D0], eax
0x1400749ca  mov     [rbp+340h+var_2E8], 1
0x1400749d1  jmp     short loc_140074A1C
0x1400749d3  mov     r11d, 2
0x1400749d9  mov     r10d, 5
0x1400749df  mov     [rbp+340h+var_2E8], r11d
0x1400749e3  mov     edx, r10d; cchDest
0x1400749e6  lea     r8, [rbp+340h+pszSrc]; pszSrc
0x1400749ed  lea     rcx, [rbp+340h+var_2CC]; pszDest
0x1400749f1  call    RtlStringCchCopyA
0x1400749f6  lea     r8, [rbp+340h+pszSrc+5]; pszSrc
0x1400749fd  mov     edx, r10d; cchDest
0x140074a00  lea     rcx, [rbp+340h+var_2C7]; pszDest
0x140074a04  call    RtlStringCchCopyA
0x140074a09  lea     r8, [rbp+340h+var_228+2]; pszSrc
0x140074a10  mov     edx, r10d; cchDest
0x140074a13  lea     rcx, [rbp+340h+var_2C2]; pszDest
0x140074a17  call    RtlStringCchCopyA
0x140074a1c  mov     eax, dword ptr [rsp+440h+var_3F0+8]
0x140074a20  lea     rcx, [rsp+440h+var_3C8]
0x140074a25  mov     qword ptr [rsp+440h+Size], rcx
0x140074a2a  lea     r9, [rsp+440h+var_400]
0x140074a2f  mov     rcx, cs:UcxDriverGlobals
0x140074a36  lea     r8, [rbp+340h+var_330]
0x140074a3a  test    r12b, r12b
0x140074a3d  mov     rdx, r14
0x140074a40  cmovnz  eax, r11d
0x140074a44  mov     dword ptr [rsp+440h+var_3F0+8], eax
0x140074a48  mov     rax, cs:qword_14006CCC8
0x140074a4f  call    _guard_dispatch_icall
0x140074a54  mov     ebx, eax
0x140074a56  test    eax, eax
0x140074a58  jns     short loc_140074A79
0x140074a5a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140074a61  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140074a68  jz      loc_140075455
0x140074a6e  mov     r9d, 66h ; 'f'
0x140074a74  jmp     loc_1400748EB
0x140074a79  mov     rax, cs:WdfFunctions_01033
0x140074a80  mov     r8, cs:off_14006C310
0x140074a87  mov     rdx, [rsp+440h+var_3C8]
0x140074a8c  mov     rcx, cs:WdfDriverGlobals
0x140074a93  mov     rax, [rax+650h]
0x140074a9a  call    _guard_dispatch_icall
0x140074a9f  mov     rdi, rax
0x140074aa2  mov     rdx, r14
0x140074aa5  lea     rcx, [rax+18h]
0x140074aa9  mov     [rcx+8], rcx
0x140074aad  mov     [rcx], rcx
0x140074ab0  mov     [rax], r14
0x140074ab3  mov     rcx, [rsp+440h+var_3C8]
0x140074ab8  mov     [rax+8], rcx
0x140074abc  mov     rcx, [rbp+340h+var_370]
0x140074ac0  mov     [rax+2D8h], rcx
0x140074ac7  mov     [rax+48h], rsi
0x140074acb  mov     eax, [rbp+340h+var_378]
0x140074ace  mov     [rdi+0B0h], eax
0x140074ad4  mov     [rdi+284h], r15d
0x140074adb  mov     [rdi+411h], r12b
  ... truncated ...
```
