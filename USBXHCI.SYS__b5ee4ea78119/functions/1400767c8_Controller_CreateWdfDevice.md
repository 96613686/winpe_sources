# Controller_CreateWdfDevice

- ea: `0x1400767c8`
- end: `0x140077204`
- name: `Controller_CreateWdfDevice`
- size: `2620`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14007a250`

## callees

- `0x14001ad0c`
- `0x14004464c`
- `0x14004465c`
- `0x1400451e8`
- `0x140045414`
- `0x140059970`
- `0x1400599b0`
- `0x140059d80`
- `0x1400767c8`

## import_xrefs

- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x14007713b`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x14007713b`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400771cb`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400771cb`

## pseudocode

```c
__int64 __fastcall Controller_CreateWdfDevice(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v7; // r13d
  __int64 v8; // r9
  NTSTATUS v9; // eax
  int v10; // edx
  __int64 v11; // r9
  unsigned int v12; // ebx
  int v13; // r9d
  __int64 v14; // rbx
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // r9
  NTSTATUS v19; // eax
  int v20; // edx
  int v21; // r9d
  int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // edx
  char *v29; // [rsp+20h] [rbp-E0h]
  char v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 *v35; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v36; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C8h] [rbp-38h]
  int v41; // [rsp+CCh] [rbp-34h]
  _OWORD v42[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v43; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v44; // [rsp+100h] [rbp+0h]
  __int128 v45; // [rsp+110h] [rbp+10h]
  __int64 *v46; // [rsp+120h] [rbp+20h]
  unsigned int *v47; // [rsp+128h] [rbp+28h]
  _OWORD v48[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v49[18]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v50[2]; // [rsp+200h] [rbp+100h] BYREF
  __int128 v51; // [rsp+220h] [rbp+120h]
  GUID v52; // [rsp+230h] [rbp+130h] BYREF
  __int64 v53; // [rsp+240h] [rbp+140h]
  char v54; // [rsp+250h] [rbp+150h] BYREF
  char v55; // [rsp+2A0h] [rbp+1A0h] BYREF

  v31 = a1;
  v47 = a4;
  LODWORD(v35) = 0;
  LODWORD(v46) = 0;
  v53 = 0;
  v40 = 0;
  v30 = 2;
  DestinationString.Buffer = (wchar_t *)&v54;
  *(_QWORD *)&DestinationString.Length = 5242880;
  memset(v42, 0, 28);
  v36.Buffer = (wchar_t *)&v55;
  v32 = 0;
  *(_QWORD *)&v36.Length = 5242880;
  v7 = 0;
  v33 = 0;
  v34 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v52 = 0;
  memset(v48, 0, 60);
  memset(v50, 0, sizeof(v50));
  v51 = 0;
  v38 = 0;
  v39 = 0;
  memset(v49, 0, sizeof(v49));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x29 )
      LODWORD(v49[0]) = -1;
    else
      LODWORD(v49[0]) = *(_DWORD *)(WdfStructures + 328);
  }
  else
  {
    LODWORD(v49[0]) = 144;
  }
  v49[5] = Controller_WdfEvtDevicePrepareHardware;
  v49[6] = Controller_WdfEvtDeviceReleaseHardware;
  v49[15] = Controller_WdfEvtDeviceUsageNotification;
  v49[1] = Controller_WdfEvtDeviceD0Entry;
  v49[2] = Controller_WdfEvtDeviceD0EntryPostInterruptsEnabled;
  v49[4] = Controller_WdfEvtDeviceD0ExitPreInterruptsDisabled;
  v49[3] = Controller_WdfEvtDeviceD0Exit;
  v49[9] = Controller_WdfEvtDeviceSelfManagedIoInit;
  v49[7] = Controller_WdfEvtDeviceSelfManagedIoCleanup;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 440))(WdfDriverGlobals, a1, v49);
  memset(v48, 0, sizeof(v48));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x2B )
      LODWORD(v48[0]) = -1;
    else
      LODWORD(v48[0]) = *(_DWORD *)(WdfStructures + 344);
  }
  else
  {
    LODWORD(v48[0]) = 64;
  }
  *((_QWORD *)&v48[0] + 1) = Controller_WdfEvtDeviceArmWakeFromS0;
  *(_QWORD *)&v48[1] = Controller_WdfEvtDeviceDisarmWakeFromS0;
  *((_QWORD *)&v48[1] + 1) = Controller_WdfEvtDeviceWakeFromS0Triggered;
  *(_QWORD *)&v48[2] = Controller_WdfEvtDeviceArmWakeFromSx;
  *((_QWORD *)&v48[2] + 1) = Controller_WdfEvtDeviceDisarmWakeFromSx;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 448))(
    WdfDriverGlobals,
    v31,
    v48);
  memset(v42, 0, sizeof(v42));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x1B )
      LODWORD(v42[0]) = -1;
    else
      LODWORD(v42[0]) = *(_DWORD *)(WdfStructures + 216);
  }
  else
  {
    LODWORD(v42[0]) = 32;
  }
  *(_QWORD *)&v42[1] = Controller_WdfEvtDeviceFilterRemoveResourceRequirements;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 1024))(
    WdfDriverGlobals,
    v31,
    v42);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 3440))(WdfDriverGlobals, v31, 2);
  LOBYTE(v8) = 22;
  v29 = &v30;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(), __int64))(WdfFunctions_01033
                                                                                                  + 584))(
         WdfDriverGlobals,
         v31,
         Controller_WdfEvtPreprocessSetPowerIrp,
         v8);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 36;
      goto LABEL_83;
    }
    goto LABEL_84;
  }
  if ( *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) )
  {
    LOBYTE(v11) = 15;
    LODWORD(v29) = 0;
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, void *, __int64))(WdfFunctions_01033 + 584))(
           WdfDriverGlobals,
           v31,
           &Controller_EvtIoInternalDeviceControl,
           v11);
    v12 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 37;
        goto LABEL_83;
      }
      goto LABEL_84;
    }
  }
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x1C )
      LODWORD(v38) = -1;
    else
      LODWORD(v38) = *(_DWORD *)(WdfStructures + 224);
  }
  else
  {
    LODWORD(v38) = 40;
  }
  *(_QWORD *)&v39 = 0;
  v40 = 0;
  *((_QWORD *)&v38 + 1) = Controller_EvtDeviceFileCreate;
  *((_QWORD *)&v39 + 1) = Controller_EvtDeviceFileClose;
  v41 = -2147483644;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v32) = -1;
    else
      LODWORD(v32) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v32) = 56;
  }
  v35 = off_14006C298;
  *((_QWORD *)&v33 + 1) = 0x100000001LL;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int128 *))(WdfFunctions_01033 + 568))(
    WdfDriverGlobals,
    v31,
    &v38,
    &v32);
  v32 = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v32) = -1;
    else
      LODWORD(v32) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v32) = 56;
  }
  v35 = off_14006C2C0;
  *((_QWORD *)&v33 + 1) = 0x100000001LL;
  *((_QWORD *)&v32 + 1) = Device_WdfEvtCleanupCallback;
  while ( 1 )
  {
    v9 = RtlUnicodeStringPrintf(&DestinationString, L"%ws%d", L"\\Device\\USBFDO-", v7);
    v12 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 38;
        goto LABEL_83;
      }
LABEL_84:
      imp_WppRecorderLogDelete(WPP_GLOBAL_Control, a2);
      goto LABEL_85;
    }
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01033 + 536))(
           WdfDriverGlobals,
           v31,
           &DestinationString);
    v12 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 39;
        goto LABEL_83;
      }
      goto LABEL_84;
    }
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01033 + 544))(
           WdfDriverGlobals,
           v31,
           &SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_RW_RES_R);
    v12 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 40;
        goto LABEL_83;
      }
      goto LABEL_84;
    }
    v43 = 0;
    v46 = 0;
    v44 = 0;
    v45 = 0;
    if ( WdfClientVersionHigherThanFramework )
      LODWORD(v43) = (unsigned int)WdfStructureCount <= 0x26 ? -1 : *(_DWORD *)(WdfStructures + 304);
    else
      LODWORD(v43) = 56;
    *((_QWORD *)&v44 + 1) = 0x100000001LL;
    v46 = off_14006BF00;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 576))(
      WdfDriverGlobals,
      v31,
      &v43);
    v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, _QWORD *))(WdfFunctions_01033 + 600))(
           WdfDriverGlobals,
           &v31,
           &v32,
           a3);
    v12 = v9;
    if ( v9 != -1073741771 )
      break;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_d(a2, v10, 4, 41, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v7);
    }
    ++v7;
  }
  if ( v9 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_84;
    v13 = 42;
LABEL_83:
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(a2, v10, 4, v13, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v9);
    goto LABEL_84;
  }
  v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
          WdfDriverGlobals,
          *a3,
          off_14006C2C0);
  *(_QWORD *)(v14 + 16) = a2;
  *(_QWORD *)(v14 + 88) = *a3;
  Device_QueryCapabilities(v14);
  if ( !(unsigned __int8)Device_IsSecureDevice(v14) )
  {
    LOBYTE(v15) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64))(WdfFunctions_01033 + 392))(
      WdfDriverGlobals,
      *a3,
      1,
      v15);
    LOBYTE(v16) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64))(WdfFunctions_01033 + 392))(
      WdfDriverGlobals,
      *a3,
      2,
      v16);
    LOBYTE(v17) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64))(WdfFunctions_01033 + 392))(
      WdfDriverGlobals,
      *a3,
      3,
      v17);
    LOBYTE(v18) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64))(WdfFunctions_01033 + 392))(
      WdfDriverGlobals,
      *a3,
      4,
      v18);
  }
  v19 = RtlUnicodeStringPrintf(&v36, L"%ws%d", L"\\DosDevices\\HCD", v7);
  v12 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_85;
    v21 = 43;
    goto LABEL_59;
  }
  v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, struct _UNICODE_STRING *))(WdfFunctions_01033 + 640))(
          WdfDriverGlobals,
          *a3,
          &v36);
  v12 = v19;
  if ( v19 >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = 4;
      WPP_RECORDER_SF_S(a2, v20, v22, 45, (_DWORD)v29, (__int64)v36.Buffer);
    }
    v23 = *a3;
    v52 = GUID_BUS_TYPE_USB;
    v53 = 15;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, GUID *))(WdfFunctions_01033 + 680))(
      WdfDriverGlobals,
      v23,
      &v52);
    v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, GUID *, _QWORD))(WdfFunctions_01033 + 616))(
            WdfDriverGlobals,
            *a3,
            &GUID_DEVINTERFACE_USB_HOST_CONTROLLER,
            0);
    v12 = v19;
    if ( v19 >= 0 )
    {
      memset(v50, 0, sizeof(v50));
      v51 = 0;
      if ( WdfClientVersionHigherThanFramework )
      {
        if ( (unsigned int)WdfStructureCount <= 0xC )
          LODWORD(v50[0]) = -1;
        else
          LODWORD(v50[0]) = *(_DWORD *)(WdfStructures + 96);
      }
      else
      {
        LODWORD(v50[0]) = 48;
      }
      v24 = *a3;
      *(__m128i *)((char *)v50 + 4) = _mm_load_si128((const __m128i *)&_xmm);
      *(_QWORD *)((char *)&v50[1] + 4) = 0x200000002LL;
      *(_QWORD *)&v51 = 0x200000002LL;
      *((_QWORD *)&v51 + 1) = -1;
      HIDWORD(v50[1]) = 1;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 664))(
        WdfDriverGlobals,
        v24,
        v50);
      v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 264))(WdfDriverGlobals, *a3);
      v26 = PoDirectedDripsSetDeviceFlags(v25, 2);
      v12 = v26;
      if ( v26 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = 2;
          WPP_RECORDER_SF_d(a2, v27, 4, 47, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v26);
        }
        v12 = 0;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = 46;
      goto LABEL_59;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v21 = 44;
LABEL_59:
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_d(a2, v20, 4, v21, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v19);
  }
LABEL_85:
  *v47 = v7;
  return v12;
}

```

## disassembly

```asm
0x1400767c8  push    rbp
0x1400767ca  push    rbx
0x1400767cb  push    rsi
0x1400767cc  push    rdi
0x1400767cd  push    r12
0x1400767cf  push    r13
0x1400767d1  push    r14
0x1400767d3  push    r15
0x1400767d5  lea     rbp, [rsp-208h]
0x1400767dd  sub     rsp, 308h
0x1400767e4  mov     rax, cs:__security_cookie
0x1400767eb  xor     rax, rsp
0x1400767ee  mov     [rbp+240h+var_50], rax
0x1400767f5  xorps   xmm0, xmm0
0x1400767f8  mov     [rsp+340h+var_2F8], rcx
0x1400767fd  xor     eax, eax
0x1400767ff  mov     [rbp+240h+var_218], r9
0x140076803  mov     dword ptr [rbp+240h+var_2C0], eax
0x140076806  mov     r12, r8
0x140076809  mov     dword ptr [rbp+240h+var_220], eax
0x14007680c  mov     r15, rdx
0x14007680f  mov     [rbp+240h+var_100], rax
0x140076816  mov     rbx, rcx
0x140076819  mov     [rbp+240h+var_278], eax
0x14007681c  lea     rcx, [rbp+240h+var_1D0]; void *
0x140076820  lea     rax, [rbp+240h+var_F0]
0x140076827  mov     [rsp+340h+var_300], 2
0x14007682c  mov     [rbp+240h+DestinationString.Buffer], rax
0x140076830  mov     r14d, 90h
0x140076836  lea     rax, [rbp+240h+var_A0]
0x14007683d  mov     qword ptr [rbp+240h+DestinationString.Length], 500000h
0x140076845  movups  [rbp+240h+var_270], xmm0
0x140076849  xor     edi, edi
0x14007684b  mov     r8d, r14d; Size
0x14007684e  movups  [rbp+240h+var_1F0], xmm0
0x140076852  xor     edx, edx; Val
0x140076854  mov     [rbp+240h+var_2B8.Buffer], rax
0x140076858  movups  [rsp+340h+var_2F0], xmm0
0x14007685d  mov     qword ptr [rbp+240h+var_2B8.Length], 500000h
0x140076865  mov     r13d, edi
0x140076868  movups  [rsp+340h+var_2E0], xmm0
0x14007686d  movups  [rsp+340h+var_2D0], xmm0
0x140076872  movups  [rbp+240h+var_250], xmm0
0x140076876  movups  [rbp+240h+var_240], xmm0
0x14007687a  movups  [rbp+240h+var_230], xmm0
0x14007687e  movups  [rbp+240h+var_110], xmm0
0x140076885  movups  [rbp+240h+var_270+0Ch], xmm0
0x140076889  movups  [rbp+240h+var_210], xmm0
0x14007688d  movups  [rbp+240h+var_200], xmm0
0x140076891  movups  [rbp+240h+var_1F0+0Ch], xmm0
0x140076895  movups  [rbp+240h+var_140], xmm0
0x14007689c  movups  [rbp+240h+var_130], xmm0
0x1400768a3  movups  [rbp+240h+var_120], xmm0
0x1400768aa  movups  [rbp+240h+var_298], xmm0
0x1400768ae  movups  [rbp+240h+var_288], xmm0
0x1400768b2  call    memset
0x1400768b7  or      esi, 0FFFFFFFFh
0x1400768ba  cmp     cs:WdfClientVersionHigherThanFramework, dil
0x1400768c1  jz      short loc_1400768E3
0x1400768c3  cmp     cs:WdfStructureCount, 29h ; ')'
0x1400768ca  jbe     short loc_1400768DE
0x1400768cc  mov     rax, cs:WdfStructures
0x1400768d3  mov     ecx, [rax+148h]
0x1400768d9  mov     [rbp+240h+var_1D0], ecx
0x1400768dc  jmp     short loc_1400768E7
0x1400768de  mov     [rbp+240h+var_1D0], esi
0x1400768e1  jmp     short loc_1400768E7
0x1400768e3  mov     [rbp+240h+var_1D0], r14d
0x1400768e7  mov     rcx, cs:WdfDriverGlobals
0x1400768ee  lea     rax, Controller_WdfEvtDevicePrepareHardware
0x1400768f5  mov     [rbp+240h+var_1A8], rax
0x1400768fc  lea     r8, [rbp+240h+var_1D0]
0x140076900  lea     rax, Controller_WdfEvtDeviceReleaseHardware
0x140076907  mov     rdx, rbx
0x14007690a  mov     [rbp+240h+var_1A0], rax
0x140076911  lea     rax, Controller_WdfEvtDeviceUsageNotification
0x140076918  mov     [rbp+240h+var_158], rax
0x14007691f  lea     rax, Controller_WdfEvtDeviceD0Entry
0x140076926  mov     [rbp+240h+var_1C8], rax
0x14007692a  lea     rax, Controller_WdfEvtDeviceD0EntryPostInterruptsEnabled
0x140076931  mov     [rbp+240h+var_1C0], rax
0x140076938  lea     rax, Controller_WdfEvtDeviceD0ExitPreInterruptsDisabled
0x14007693f  mov     [rbp+240h+var_1B0], rax
0x140076946  lea     rax, Controller_WdfEvtDeviceD0Exit
0x14007694d  mov     [rbp+240h+var_1B8], rax
0x140076954  lea     rax, Controller_WdfEvtDeviceSelfManagedIoInit
0x14007695b  mov     [rbp+240h+var_188], rax
0x140076962  lea     rax, Controller_WdfEvtDeviceSelfManagedIoCleanup
0x140076969  mov     [rbp+240h+var_198], rax
0x140076970  mov     rax, cs:WdfFunctions_01033
0x140076977  mov     rax, [rax+1B8h]
0x14007697e  call    _guard_dispatch_icall
0x140076983  mov     ebx, 40h ; '@'
0x140076988  lea     rcx, [rbp+240h+var_210]; void *
0x14007698c  mov     r8d, ebx; Size
0x14007698f  xor     edx, edx; Val
0x140076991  call    memset
0x140076996  cmp     cs:WdfClientVersionHigherThanFramework, dil
0x14007699d  jz      short loc_1400769BF
0x14007699f  cmp     cs:WdfStructureCount, 2Bh ; '+'
0x1400769a6  jbe     short loc_1400769BA
0x1400769a8  mov     rax, cs:WdfStructures
0x1400769af  mov     ecx, [rax+158h]
0x1400769b5  mov     dword ptr [rbp+240h+var_210], ecx
0x1400769b8  jmp     short loc_1400769C2
0x1400769ba  mov     dword ptr [rbp+240h+var_210], esi
0x1400769bd  jmp     short loc_1400769C2
0x1400769bf  mov     dword ptr [rbp+240h+var_210], ebx
0x1400769c2  mov     rdx, [rsp+340h+var_2F8]
0x1400769c7  lea     rax, Controller_WdfEvtDeviceArmWakeFromS0
0x1400769ce  mov     rcx, cs:WdfDriverGlobals
0x1400769d5  lea     r8, [rbp+240h+var_210]
0x1400769d9  mov     qword ptr [rbp+240h+var_210+8], rax
0x1400769dd  lea     rax, Controller_WdfEvtDeviceDisarmWakeFromS0
0x1400769e4  mov     qword ptr [rbp+240h+var_200], rax
0x1400769e8  lea     rax, Controller_WdfEvtDeviceWakeFromS0Triggered
0x1400769ef  mov     qword ptr [rbp+240h+var_200+8], rax
0x1400769f3  lea     rax, Controller_WdfEvtDeviceArmWakeFromSx
0x1400769fa  mov     qword ptr [rbp+240h+var_1F0], rax
0x1400769fe  lea     rax, Controller_WdfEvtDeviceDisarmWakeFromSx
0x140076a05  mov     qword ptr [rbp+240h+var_1F0+8], rax
0x140076a09  mov     rax, cs:WdfFunctions_01033
0x140076a10  mov     rax, [rax+1C0h]
0x140076a17  call    _guard_dispatch_icall
0x140076a1c  cmp     cs:WdfClientVersionHigherThanFramework, dil
0x140076a23  xorps   xmm0, xmm0
0x140076a26  movups  [rbp+240h+var_270], xmm0
0x140076a2a  movups  [rbp+240h+var_260], xmm0
0x140076a2e  jz      short loc_140076A50
0x140076a30  cmp     cs:WdfStructureCount, 1Bh
0x140076a37  jbe     short loc_140076A4B
0x140076a39  mov     rax, cs:WdfStructures
0x140076a40  mov     ecx, [rax+0D8h]
0x140076a46  mov     dword ptr [rbp+240h+var_270], ecx
0x140076a49  jmp     short loc_140076A57
0x140076a4b  mov     dword ptr [rbp+240h+var_270], esi
0x140076a4e  jmp     short loc_140076A57
0x140076a50  mov     dword ptr [rbp+240h+var_270], 20h ; ' '
0x140076a57  mov     rdx, [rsp+340h+var_2F8]
0x140076a5c  lea     rax, Controller_WdfEvtDeviceFilterRemoveResourceRequirements
0x140076a63  mov     rcx, cs:WdfDriverGlobals
0x140076a6a  lea     r8, [rbp+240h+var_270]
0x140076a6e  mov     qword ptr [rbp+240h+var_260], rax
0x140076a72  mov     rax, cs:WdfFunctions_01033
0x140076a79  mov     rax, [rax+400h]
0x140076a80  call    _guard_dispatch_icall
0x140076a85  mov     rax, cs:WdfFunctions_01033
0x140076a8c  mov     r8d, 2
0x140076a92  mov     rdx, [rsp+340h+var_2F8]
0x140076a97  mov     rcx, cs:WdfDriverGlobals
0x140076a9e  mov     rax, [rax+0D70h]
0x140076aa5  call    _guard_dispatch_icall
0x140076aaa  mov     rax, cs:WdfFunctions_01033
0x140076ab1  lea     rcx, [rsp+340h+var_300]
0x140076ab6  mov     rdx, [rsp+340h+var_2F8]
0x140076abb  lea     r8, Controller_WdfEvtPreprocessSetPowerIrp
0x140076ac2  mov     r14d, 1
0x140076ac8  mov     r9b, 16h
0x140076acb  mov     dword ptr [rsp+340h+var_318], r14d
0x140076ad0  mov     rax, [rax+248h]
0x140076ad7  mov     [rsp+340h+var_320], rcx
0x140076adc  mov     rcx, cs:WdfDriverGlobals
0x140076ae3  call    _guard_dispatch_icall
0x140076ae8  mov     ebx, eax
0x140076aea  test    eax, eax
0x140076aec  jns     short loc_140076B18
0x140076aee  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140076af5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140076afc  jz      loc_1400771C1
0x140076b02  lea     r9d, [r14+23h]
0x140076b06  lea     r14, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140076b0d  mov     r8d, 4
0x140076b13  jmp     loc_1400771AE
0x140076b18  mov     rax, cs:g_WdfDriverUsbXhciContext
0x140076b1f  cmp     [rax+1Ch], dil
0x140076b23  jz      short loc_140076B79
0x140076b25  mov     rax, cs:WdfFunctions_01033
0x140076b2c  lea     r8, Controller_EvtIoInternalDeviceControl
0x140076b33  mov     rdx, [rsp+340h+var_2F8]
0x140076b38  mov     r9b, 0Fh
0x140076b3b  mov     rcx, cs:WdfDriverGlobals
0x140076b42  mov     dword ptr [rsp+340h+var_318], edi
0x140076b46  mov     rax, [rax+248h]
0x140076b4d  mov     [rsp+340h+var_320], rdi
0x140076b52  call    _guard_dispatch_icall
0x140076b57  mov     ebx, eax
0x140076b59  test    eax, eax
0x140076b5b  jns     short loc_140076B79
0x140076b5d  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140076b64  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140076b6b  jz      loc_1400771C1
0x140076b71  mov     r9d, 25h ; '%'
0x140076b77  jmp     short loc_140076B06
0x140076b79  mov     dl, cs:WdfClientVersionHigherThanFramework
0x140076b7f  test    dl, dl
0x140076b81  jz      short loc_140076BA3
0x140076b83  cmp     cs:WdfStructureCount, 1Ch
0x140076b8a  jbe     short loc_140076B9E
0x140076b8c  mov     rax, cs:WdfStructures
0x140076b93  mov     ecx, [rax+0E0h]
0x140076b99  mov     dword ptr [rbp+240h+var_298], ecx
0x140076b9c  jmp     short loc_140076BAA
0x140076b9e  mov     dword ptr [rbp+240h+var_298], esi
0x140076ba1  jmp     short loc_140076BAA
0x140076ba3  mov     dword ptr [rbp+240h+var_298], 28h ; '('
0x140076baa  xorps   xmm0, xmm0
0x140076bad  mov     qword ptr [rbp+240h+var_288], rdi
0x140076bb1  lea     rax, Controller_EvtDeviceFileCreate
0x140076bb8  mov     [rbp+240h+var_278], edi
0x140076bbb  mov     qword ptr [rbp+240h+var_298+8], rax
0x140076bbf  lea     rax, Controller_EvtDeviceFileClose
0x140076bc6  mov     qword ptr [rbp+240h+var_288+8], rax
0x140076bca  xor     eax, eax
0x140076bcc  mov     [rbp+240h+var_274], 80000004h
0x140076bd3  mov     [rbp+240h+var_2C0], rax
0x140076bd7  movups  [rsp+340h+var_2F0], xmm0
0x140076bdc  lea     ebx, [rax+38h]
0x140076bdf  movups  [rsp+340h+var_2E0], xmm0
0x140076be4  movups  [rsp+340h+var_2D0], xmm0
0x140076be9  test    dl, dl
0x140076beb  jz      short loc_140076C0F
0x140076bed  cmp     cs:WdfStructureCount, 26h ; '&'
0x140076bf4  jbe     short loc_140076C09
0x140076bf6  mov     rax, cs:WdfStructures
0x140076bfd  mov     ecx, [rax+130h]
0x140076c03  mov     dword ptr [rsp+340h+var_2F0], ecx
0x140076c07  jmp     short loc_140076C13
0x140076c09  mov     dword ptr [rsp+340h+var_2F0], esi
0x140076c0d  jmp     short loc_140076C13
0x140076c0f  mov     dword ptr [rsp+340h+var_2F0], ebx
0x140076c13  mov     rax, cs:off_14006C298
0x140076c1a  lea     r9, [rsp+340h+var_2F0]
0x140076c1f  mov     rdx, [rsp+340h+var_2F8]
0x140076c24  lea     r8, [rbp+240h+var_298]
0x140076c28  mov     rcx, cs:WdfDriverGlobals
0x140076c2f  mov     [rbp+240h+var_2C0], rax
0x140076c33  mov     rax, cs:WdfFunctions_01033
0x140076c3a  mov     dword ptr [rsp+340h+var_2E0+8], r14d
0x140076c3f  mov     dword ptr [rsp+340h+var_2E0+0Ch], r14d
0x140076c44  mov     rax, [rax+238h]
0x140076c4b  call    _guard_dispatch_icall
0x140076c50  xorps   xmm0, xmm0
0x140076c53  xor     eax, eax
0x140076c55  cmp     cs:WdfClientVersionHigherThanFramework, dil
0x140076c5c  movups  [rsp+340h+var_2F0], xmm0
0x140076c61  mov     [rbp+240h+var_2C0], rax
0x140076c65  movups  [rsp+340h+var_2E0], xmm0
0x140076c6a  movups  [rsp+340h+var_2D0], xmm0
0x140076c6f  jz      short loc_140076C93
0x140076c71  cmp     cs:WdfStructureCount, 26h ; '&'
0x140076c78  jbe     short loc_140076C8D
0x140076c7a  mov     rax, cs:WdfStructures
0x140076c81  mov     ecx, [rax+130h]
0x140076c87  mov     dword ptr [rsp+340h+var_2F0], ecx
0x140076c8b  jmp     short loc_140076C97
0x140076c8d  mov     dword ptr [rsp+340h+var_2F0], esi
0x140076c91  jmp     short loc_140076C97
0x140076c93  mov     dword ptr [rsp+340h+var_2F0], ebx
0x140076c97  mov     rax, cs:off_14006C2C0
0x140076c9e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140076ca5  mov     [rbp+240h+var_2C0], rax
0x140076ca9  mov     esi, 4
0x140076cae  lea     rax, Device_WdfEvtCleanupCallback
0x140076cb5  mov     dword ptr [rsp+340h+var_2E0+8], r14d
0x140076cba  mov     dword ptr [rsp+340h+var_2E0+0Ch], r14d
0x140076cbf  lea     r14, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140076cc6  mov     qword ptr [rsp+340h+var_2F0+8], rax
0x140076ccb  mov     r9d, r13d
0x140076cce  lea     r8, aDeviceUsbfdo; "\\Device\\USBFDO-"
0x140076cd5  lea     rdx, aWsD; "%ws%d"
0x140076cdc  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x140076ce0  call    RtlUnicodeStringPrintf
0x140076ce5  mov     ebx, eax
0x140076ce7  test    eax, eax
0x140076ce9  js      loc_14007719C
0x140076cef  mov     rax, cs:WdfFunctions_01033
0x140076cf6  lea     r8, [rbp+240h+DestinationString]
0x140076cfa  mov     rdx, [rsp+340h+var_2F8]
0x140076cff  mov     rcx, cs:WdfDriverGlobals
0x140076d06  mov     rax, [rax+218h]
0x140076d0d  call    _guard_dispatch_icall
0x140076d12  mov     ebx, eax
0x140076d14  test    eax, eax
0x140076d16  js      loc_14007718B
0x140076d1c  mov     rax, cs:WdfFunctions_01033
0x140076d23  lea     r8, SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_RW_RES_R
0x140076d2a  mov     rdx, [rsp+340h+var_2F8]
0x140076d2f  mov     rcx, cs:WdfDriverGlobals
0x140076d36  mov     rax, [rax+220h]
0x140076d3d  call    _guard_dispatch_icall
0x140076d42  mov     ebx, eax
0x140076d44  test    eax, eax
0x140076d46  js      loc_14007717A
0x140076d4c  xorps   xmm0, xmm0
0x140076d4f  xor     eax, eax
0x140076d51  cmp     cs:WdfClientVersionHigherThanFramework, al
0x140076d57  movups  [rbp+240h+var_250], xmm0
0x140076d5b  mov     [rbp+240h+var_220], rax
0x140076d5f  movups  [rbp+240h+var_240], xmm0
0x140076d63  movups  [rbp+240h+var_230], xmm0
  ... truncated ...
```
