# USBSTOR_FdoDeviceUsageNotification

- ea: `0x14001fca8`
- end: `0x140020669`
- name: `USBSTOR_FdoDeviceUsageNotification`
- size: `2497`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x14000e268`
- `0x1400105e8`
- `0x140010664`
- `0x140010894`
- `0x140012d0c`
- `0x140013950`
- `0x140013d40`
- `0x14001fca8`
- `0x1400208c0`
- `0x14002239c`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140020235`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400202a0`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140020235`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400202a0`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14001fecd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14002011c`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400202da`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14001fecd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14002011c`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400202da`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140020428`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140020428`
- `ntoskrnl!IoFreeIrp` at `0x14002049d`
- `ntoskrnl!IoFreeIrp` at `0x1400205d4`
- `ntoskrnl!IoFreeIrp` at `0x14002049d`
- `ntoskrnl!IoFreeIrp` at `0x1400205d4`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140020087`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400200a8`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400200c9`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400200ea`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140020087`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400200a8`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400200c9`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400200ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ff5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ff74`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ff8b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ffa2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ff5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ff74`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ff8b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ffa2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001fe48`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001fe48`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140020379`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140020379`
- `ntoskrnl!ZwPowerInformation` at `0x140020410`
- `ntoskrnl!ZwPowerInformation` at `0x140020410`
- `ntoskrnl!ExAllocatePool2` at `0x140020017`
- `ntoskrnl!ExAllocatePool2` at `0x140020017`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140020579`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140020579`
- `ntoskrnl!swprintf_s` at `0x14001ffe4`
- `ntoskrnl!swprintf_s` at `0x1400201c8`
- `ntoskrnl!swprintf_s` at `0x14001ffe4`
- `ntoskrnl!swprintf_s` at `0x1400201c8`
- `ntoskrnl!IofCallDriver` at `0x140020590`
- `ntoskrnl!IofCallDriver` at `0x140020590`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020134`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002032b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020134`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002032b`
- `ntoskrnl!KeInitializeEvent` at `0x140020533`
- `ntoskrnl!KeInitializeEvent` at `0x140020533`
- `ntoskrnl!IofCompleteRequest` at `0x1400205e5`
- `ntoskrnl!IofCompleteRequest` at `0x1400205e5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400205b8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400205b8`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x14001fdfd`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x14001fdfd`
- `ntoskrnl!ZwClose` at `0x14001ff20`
- `ntoskrnl!ZwClose` at `0x14001ff20`
- `ntoskrnl!RtlSetPortableOperatingSystem` at `0x14001fe1f`
- `ntoskrnl!RtlSetPortableOperatingSystem` at `0x14001fe1f`
- `ntoskrnl!IoAllocateIrp` at `0x14002047c`
- `ntoskrnl!IoAllocateIrp` at `0x1400204bf`
- `ntoskrnl!IoAllocateIrp` at `0x14002047c`
- `ntoskrnl!IoAllocateIrp` at `0x1400204bf`

## string_xrefs

- `0x14001ff80`: `\LocationPaths`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoDeviceUsageNotification(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG Options; // r14d
  BOOLEAN Lock; // r12
  char v8; // cl
  NTSTATUS Status; // ebx
  char v10; // bl
  char *v11; // rax
  unsigned __int8 v12; // bl
  __int64 v13; // rax
  int v14; // eax
  USHORT v15; // bx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  NTSTATUS v18; // ebx
  __int64 v19; // rax
  int v20; // edx
  int v21; // ecx
  int v22; // eax
  int StateSeparationLocation; // eax
  WCHAR *v24; // rsi
  NTSTATUS v25; // ebx
  int v26; // ebx
  ULONG Flags; // edx
  ULONG v28; // edx
  IRP *v29; // rcx
  PIRP v30; // rsi
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  struct _IO_STACK_LOCATION *v35; // rax
  PVOID ValueData; // [rsp+20h] [rbp-E0h]
  char v38; // [rsp+40h] [rbp-C0h] BYREF
  char v39; // [rsp+41h] [rbp-BFh]
  int v40; // [rsp+44h] [rbp-BCh] BYREF
  int v41; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  void *DeviceRegKey; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR Path; // [rsp+68h] [rbp-98h] BYREF
  __int128 InputBuffer; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h]
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING v48; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING v49; // [rsp+A8h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v51[14]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v52; // [rsp+140h] [rbp+40h] BYREF
  __int128 v53; // [rsp+150h] [rbp+50h]
  __int128 v54; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+170h] [rbp+70h]
  wchar_t Dst[8]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v57[28]; // [rsp+188h] [rbp+88h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v38 = 0;
  DeviceRegKey = 0;
  v46 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v41 = 0;
  v40 = 0;
  SourceString = 0;
  v39 = 0;
  v48 = 0;
  Path = 0;
  v49 = 0;
  DestinationString = 0;
  InputBuffer = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Lock = CurrentStackLocation->Parameters.SetLock.Lock;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1314210886, DeviceObject, Irp, 0);
  v8 = DeviceExtension[1813];
  if ( !v8 && Options - 1 <= 3 )
  {
    Status = -1073741637;
    Irp->IoStatus.Status = -1073741637;
    goto LABEL_99;
  }
  if ( Lock && Options == 3 )
  {
    if ( !DeviceExtension[1866] && v8 && !DeviceExtension[1814] )
      *((_DWORD *)DeviceExtension + 33) &= ~0x80u;
    goto LABEL_71;
  }
  if ( Options != 4 )
    goto LABEL_71;
  v10 = 0;
  v11 = (char *)*((_QWORD *)DeviceExtension + 4);
  do
  {
    if ( v11 == DeviceExtension + 32 )
      break;
    v12 = v11[49];
    v11 = *(char **)v11;
    v10 = v12 >> 7;
  }
  while ( !v10 );
  if ( ((int)RtlCheckPortableOperatingSystem(&v38) < 0 || v38) && v10 != 1 )
    goto LABEL_71;
  RtlSetPortableOperatingSystem(0);
  if ( !*((_DWORD *)DeviceExtension + 31) )
  {
    if ( IoOpenDeviceRegistryKey(*((PDEVICE_OBJECT *)DeviceExtension + 2), 2u, 0x1F0000u, &DeviceRegKey) >= 0 )
    {
      v41 = 1;
      if ( RtlWriteRegistryValue(0x40000000u, (PCWSTR)DeviceRegKey, L"NonRemovable", 4u, &v41, 4u) < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 112, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
      ZwClose(DeviceRegKey);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
  }
  if ( (int)USBSTOR_InRootContainer(*((PDEVICE_OBJECT *)DeviceExtension + 2)) >= 0 && !v39 )
  {
    RtlInitUnicodeString(&DestinationString, 0);
    RtlInitUnicodeString(&SourceString, L"DeviceOverrides\\");
    RtlInitUnicodeString(&v48, L"\\LocationPaths");
    RtlInitUnicodeString(&v49, L"\\*");
    memset(v57, 0, sizeof(v57));
    *(_OWORD *)Dst = 0;
    v13 = *((_QWORD *)DeviceExtension + 6);
    LODWORD(ValueData) = *(unsigned __int16 *)(v13 + 10);
    v14 = swprintf_s(Dst, 0x16u, L"USB#VID_%04x&PID_%04x", *(unsigned __int16 *)(v13 + 8), ValueData);
    if ( v14 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_51;
      }
      v17 = 115;
    }
    else
    {
      v15 = SourceString.MaximumLength + v48.MaximumLength + v49.MaximumLength + 2 * v14;
      DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v15, 1396788565);
      if ( DestinationString.Buffer )
      {
        DestinationString.Length = 0;
        DestinationString.MaximumLength = v15;
        RtlUnicodeStringCat(&DestinationString, &SourceString);
        RtlCreateRegistryKey(2u, DestinationString.Buffer);
        RtlUnicodeStringCatString(&DestinationString, Dst);
        RtlCreateRegistryKey(2u, DestinationString.Buffer);
        RtlUnicodeStringCat(&DestinationString, &v48);
        RtlCreateRegistryKey(2u, DestinationString.Buffer);
        RtlUnicodeStringCat(&DestinationString, &v49);
        RtlCreateRegistryKey(2u, DestinationString.Buffer);
        v41 = 0;
        v18 = RtlWriteRegistryValue(2u, DestinationString.Buffer, L"Removable", 4u, &v41, 4u);
        ExFreePoolWithTag(DestinationString.Buffer, 0x53414D55u);
        if ( v18 >= 0 )
          goto LABEL_51;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_51;
        }
        v17 = 114;
      }
      else
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_51;
        }
        v17 = 113;
      }
    }
    WPP_SF_(v16->AttachedDevice, v17, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
LABEL_51:
  if ( (*((_DWORD *)DeviceExtension + 33) & 0x40) == 0 )
  {
    v19 = *((_QWORD *)DeviceExtension + 6);
    LODWORD(ValueData) = *(unsigned __int16 *)(v19 + 10);
    if ( swprintf_s(Dst, 0x16u, L"usbstor\\%04X%04X", *(unsigned __int16 *)(v19 + 8), ValueData) < 0 )
      goto LABEL_69;
    memset(v51, 0, sizeof(v51));
    v40 = 0;
    v51[2] = L"DeviceHackFlags";
    LODWORD(v51[1]) = 288;
    LODWORD(v51[4]) = 67108868;
    v51[3] = &v40;
    LODWORD(v51[6]) = 4;
    v51[5] = &v40;
    if ( (int)RtlQueryRegistryValuesEx(2, Dst, v51) < 0 )
      v22 = 64;
    else
      v22 = v40 | 0x40;
    v40 = v22;
    StateSeparationLocation = USBSTOR_GetStateSeparationLocation(v21, v20, (unsigned int)Dst, 44, (__int64)&Path);
    v24 = (WCHAR *)Path;
    v25 = StateSeparationLocation;
    if ( StateSeparationLocation >= 0 )
    {
      v26 = v40;
      v40 = 0;
      if ( (int)RtlQueryRegistryValuesEx(0, Path, v51) >= 0 )
        v26 |= v40;
      v40 = v26;
      v25 = RtlWriteRegistryValue(0, v24, L"DeviceHackFlags", 4u, &v40, 4u);
      if ( v25 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
    }
    if ( v24 )
      ExFreePoolWithTag(v24, 0);
    if ( v25 < 0 )
    {
LABEL_69:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
    }
  }
LABEL_71:
  if ( IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)DeviceExtension + 3), Irp) )
    Status = Irp->IoStatus.Status;
  else
    Status = -1073741823;
  if ( Options - 1 <= 2 && Status >= 0 )
  {
    Flags = DeviceObject->Flags;
    if ( (*(_DWORD *)(*((_QWORD *)DeviceExtension + 3) + 48LL) & 0x2000) != 0 )
      v28 = Flags | 0x2000;
    else
      v28 = Flags & 0xFFFFDFFF;
    DeviceObject->Flags = v28;
  }
  v46 = 0;
  InputBuffer = 0;
  *((_QWORD *)&InputBuffer + 1) = *((_QWORD *)DeviceExtension + 3);
  LODWORD(v46) = 16;
  if ( Options != 1 || (LODWORD(InputBuffer) = 58, (DeviceObject->Flags & 0x2000) != 0) )
    LODWORD(InputBuffer) = 59;
  ZwPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 0x18u, 0, 0);
  if ( RtlCheckRegistryKey(2u, (PWSTR)L"MiniNT") < 0 )
  {
    if ( Options != 1 )
      goto LABEL_87;
    if ( !Lock )
      goto LABEL_99;
    if ( Status < 0 )
    {
LABEL_87:
      if ( Options != 4 )
        goto LABEL_99;
    }
    memset(&Event, 0, sizeof(Event));
    DeviceExtension[1876] = 1;
    USBSTOR_InitializeEmergencyWorkerThread();
    v29 = IoAllocateIrp(DeviceObject->StackSize, 0);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)DeviceExtension + 235, (signed __int64)v29, 0) && v29 )
      IoFreeIrp(v29);
    if ( !DeviceExtension[1877] )
    {
      v30 = IoAllocateIrp(*(_BYTE *)(*((_QWORD *)DeviceExtension + 3) + 76LL), 0);
      if ( v30 )
      {
        v31 = *((_DWORD *)DeviceExtension + 454);
        v55 = 0;
        v32 = *((_QWORD *)DeviceExtension + 12);
        v53 = 0x200001000uLL;
        v52 = 0x3800000001uLL;
        v54 = 0;
        LODWORD(v54) = v31;
        v33 = *(_QWORD *)(v32 + 8);
        v34 = *((_QWORD *)DeviceExtension + 13);
        *((_QWORD *)&v53 + 1) = v33;
        LODWORD(v55) = v31;
        *((_QWORD *)&v54 + 1) = *(_QWORD *)(v34 + 8);
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        v35 = v30->Tail.Overlay.CurrentStackLocation;
        v35[-1].Parameters.WMI.ProviderId = (ULONG_PTR)&v52;
        v35[-1].MajorFunction = 15;
        v35[-1].Parameters.Read.ByteOffset.LowPart = 4789263;
        if ( IoSetCompletionRoutineEx(DeviceObject, v30, USBSTOR_SyncCompletionRoutine, &Event, 1u, 1u, 1u) >= 0 )
        {
          if ( IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), v30) == 259 )
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          if ( v30->IoStatus.Status >= 0 )
            DeviceExtension[1877] = 1;
        }
        IoFreeIrp(v30);
      }
    }
  }
LABEL_99:
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1853187174, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001fca8  mov     [rsp-8+arg_10], rbx
0x14001fcad  push    rbp
0x14001fcae  push    rsi
0x14001fcaf  push    rdi
0x14001fcb0  push    r12
0x14001fcb2  push    r13
0x14001fcb4  push    r14
0x14001fcb6  push    r15
0x14001fcb8  lea     rbp, [rsp-0B0h]
0x14001fcc0  sub     rsp, 1B0h
0x14001fcc7  mov     rax, cs:__security_cookie
0x14001fcce  xor     rax, rsp
0x14001fcd1  mov     [rbp+0E0h+var_38], rax
0x14001fcd8  mov     rdi, [rcx+40h]
0x14001fcdc  xor     esi, esi
0x14001fcde  xorps   xmm0, xmm0
0x14001fce1  mov     [rsp+1E0h+var_1A0], sil
0x14001fce6  xor     eax, eax
0x14001fce8  mov     [rsp+1E0h+DeviceRegKey], rsi
0x14001fced  mov     [rbp+0E0h+var_160], rax
0x14001fcf1  xorps   xmm1, xmm1
0x14001fcf4  mov     rax, [rdx+0B8h]
0x14001fcfb  mov     r13, rdx
0x14001fcfe  mov     [rsp+1E0h+var_198], esi
0x14001fd02  mov     r15, rcx
0x14001fd05  mov     [rsp+1E0h+var_19C], esi
0x14001fd09  movups  xmmword ptr [rbp+0E0h+SourceString.Length], xmm0
0x14001fd0d  mov     [rsp+1E0h+var_19F], sil
0x14001fd12  movups  xmmword ptr [rbp+0E0h+var_148.Length], xmm1
0x14001fd16  mov     [rsp+1E0h+Path], rsi
0x14001fd1b  movups  xmmword ptr [rbp+0E0h+var_138.Length], xmm0
0x14001fd1f  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm1
0x14001fd24  movups  [rsp+1E0h+InputBuffer], xmm0
0x14001fd29  mov     r14d, [rax+10h]
0x14001fd2d  mov     r12b, [rax+8]
0x14001fd31  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd38  lea     rax, WPP_GLOBAL_Control
0x14001fd3f  cmp     rcx, rax
0x14001fd42  jz      short loc_14001FD64
0x14001fd44  mov     eax, [rcx+2Ch]
0x14001fd47  test    al, 2
0x14001fd49  jz      short loc_14001FD64
0x14001fd4b  cmp     byte ptr [rcx+29h], 4
0x14001fd4f  jb      short loc_14001FD64
0x14001fd51  mov     rcx, [rcx+18h]
0x14001fd55  lea     edx, [rsi+6Eh]
0x14001fd58  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001fd5f  call    WPP_SF_
0x14001fd64  xor     r9d, r9d
0x14001fd67  mov     r8, r13
0x14001fd6a  mov     rdx, r15
0x14001fd6d  mov     ecx, 4E554446h
0x14001fd72  call    USBSTOR_LogEntry
0x14001fd77  mov     cl, [rdi+715h]
0x14001fd7d  test    cl, cl
0x14001fd7f  jnz     short loc_14001FD98
0x14001fd81  lea     eax, [r14-1]
0x14001fd85  cmp     eax, 3
0x14001fd88  ja      short loc_14001FD98
0x14001fd8a  mov     ebx, 0C00000BBh
0x14001fd8f  mov     [r13+30h], ebx
0x14001fd93  jmp     loc_1400205E0
0x14001fd98  test    r12b, r12b
0x14001fd9b  jz      short loc_14001FDD2
0x14001fd9d  cmp     r14d, 3
0x14001fda1  jnz     short loc_14001FDD2
0x14001fda3  cmp     [rdi+74Ah], sil
0x14001fdaa  jnz     loc_140020372
0x14001fdb0  test    cl, cl
0x14001fdb2  jz      loc_140020372
0x14001fdb8  cmp     [rdi+716h], sil
0x14001fdbf  jnz     loc_140020372
0x14001fdc5  btr     dword ptr [rdi+84h], 7
0x14001fdcd  jmp     loc_140020372
0x14001fdd2  cmp     r14d, 4
0x14001fdd6  jnz     loc_140020372
0x14001fddc  lea     rcx, [rdi+20h]
0x14001fde0  mov     bl, sil
0x14001fde3  mov     rax, [rcx]
0x14001fde6  cmp     rax, rcx
0x14001fde9  jz      short loc_14001FDF8
0x14001fdeb  mov     bl, [rax+31h]
0x14001fdee  mov     rax, [rax]
0x14001fdf1  shr     bl, 7
0x14001fdf4  test    bl, bl
0x14001fdf6  jz      short loc_14001FDE6
0x14001fdf8  lea     rcx, [rsp+1E0h+var_1A0]
0x14001fdfd  call    cs:__imp_RtlCheckPortableOperatingSystem
0x14001fe04  nop     dword ptr [rax+rax+00h]
0x14001fe09  test    eax, eax
0x14001fe0b  js      short loc_14001FE14
0x14001fe0d  cmp     [rsp+1E0h+var_1A0], sil
0x14001fe12  jz      short loc_14001FE1D
0x14001fe14  cmp     bl, 1
0x14001fe17  jnz     loc_140020372
0x14001fe1d  xor     ecx, ecx
0x14001fe1f  call    cs:__imp_RtlSetPortableOperatingSystem
0x14001fe26  nop     dword ptr [rax+rax+00h]
0x14001fe2b  cmp     [rdi+7Ch], esi
0x14001fe2e  jnz     loc_14001FF2E
0x14001fe34  mov     rcx, [rdi+10h]; DeviceObject
0x14001fe38  lea     r9, [rsp+1E0h+DeviceRegKey]; DeviceRegKey
0x14001fe3d  mov     edx, 2; DevInstKeyType
0x14001fe42  mov     r8d, 1F0000h; DesiredAccess
0x14001fe48  call    cs:__imp_IoOpenDeviceRegistryKey
0x14001fe4f  nop     dword ptr [rax+rax+00h]
0x14001fe54  test    eax, eax
0x14001fe56  jns     short loc_14001FE9E
0x14001fe58  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe5f  lea     rbx, WPP_GLOBAL_Control
0x14001fe66  cmp     rcx, rbx
0x14001fe69  jz      loc_14001FF35
0x14001fe6f  mov     eax, [rcx+2Ch]
0x14001fe72  test    al, 2
0x14001fe74  jz      loc_14001FF35
0x14001fe7a  cmp     byte ptr [rcx+29h], 2
0x14001fe7e  jb      loc_14001FF35
0x14001fe84  mov     rcx, [rcx+18h]
0x14001fe88  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001fe8f  mov     edx, 6Fh ; 'o'
0x14001fe94  call    WPP_SF_
0x14001fe99  jmp     loc_14001FF35
0x14001fe9e  mov     rdx, [rsp+1E0h+DeviceRegKey]; Path
0x14001fea3  lea     rax, [rsp+1E0h+var_198]
0x14001fea8  mov     ecx, 4
0x14001fead  mov     [rsp+1E0h+var_198], 1
0x14001feb5  mov     [rsp+1E0h+ValueLength], ecx; ValueLength
0x14001feb9  lea     r8, ValueName; "NonRemovable"
0x14001fec0  mov     r9d, ecx; ValueType
0x14001fec3  mov     [rsp+1E0h+ValueData], rax; ValueData
0x14001fec8  mov     ecx, 40000000h; RelativeTo
0x14001fecd  call    cs:__imp_RtlWriteRegistryValue
0x14001fed4  nop     dword ptr [rax+rax+00h]
0x14001fed9  test    eax, eax
0x14001fedb  jns     short loc_14001FF14
0x14001fedd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fee4  lea     rbx, WPP_GLOBAL_Control
0x14001feeb  cmp     rcx, rbx
0x14001feee  jz      short loc_14001FF1B
0x14001fef0  mov     eax, [rcx+2Ch]
0x14001fef3  test    al, 2
0x14001fef5  jz      short loc_14001FF1B
0x14001fef7  cmp     byte ptr [rcx+29h], 2
0x14001fefb  jb      short loc_14001FF1B
0x14001fefd  mov     rcx, [rcx+18h]
0x14001ff01  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001ff08  mov     edx, 70h ; 'p'
0x14001ff0d  call    WPP_SF_
0x14001ff12  jmp     short loc_14001FF1B
0x14001ff14  lea     rbx, WPP_GLOBAL_Control
0x14001ff1b  mov     rcx, [rsp+1E0h+DeviceRegKey]; Handle
0x14001ff20  call    cs:__imp_ZwClose
0x14001ff27  nop     dword ptr [rax+rax+00h]
0x14001ff2c  jmp     short loc_14001FF35
0x14001ff2e  lea     rbx, WPP_GLOBAL_Control
0x14001ff35  mov     rcx, [rdi+10h]; DeviceObject
0x14001ff39  lea     rdx, [rsp+1E0h+var_19F]
0x14001ff3e  call    USBSTOR_InRootContainer
0x14001ff43  test    eax, eax
0x14001ff45  js      loc_140020199
0x14001ff4b  cmp     [rsp+1E0h+var_19F], sil
0x14001ff50  jnz     loc_140020199
0x14001ff56  xor     edx, edx; SourceString
0x14001ff58  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x14001ff5d  call    cs:__imp_RtlInitUnicodeString
0x14001ff64  nop     dword ptr [rax+rax+00h]
0x14001ff69  lea     rdx, aDeviceoverride; "DeviceOverrides\\"
0x14001ff70  lea     rcx, [rbp+0E0h+SourceString]; DestinationString
0x14001ff74  call    cs:__imp_RtlInitUnicodeString
0x14001ff7b  nop     dword ptr [rax+rax+00h]
0x14001ff80  lea     rdx, aLocationpaths; "\\LocationPaths"
0x14001ff87  lea     rcx, [rbp+0E0h+var_148]; DestinationString
0x14001ff8b  call    cs:__imp_RtlInitUnicodeString
0x14001ff92  nop     dword ptr [rax+rax+00h]
0x14001ff97  lea     rdx, asc_140016960; "\\*"
0x14001ff9e  lea     rcx, [rbp+0E0h+var_138]; DestinationString
0x14001ffa2  call    cs:__imp_RtlInitUnicodeString
0x14001ffa9  nop     dword ptr [rax+rax+00h]
0x14001ffae  xorps   xmm0, xmm0
0x14001ffb1  lea     r8, aUsbVid04xPid04; "USB#VID_%04x&PID_%04x"
0x14001ffb8  movups  xmmword ptr [rbp+0E0h+var_58], xmm0
0x14001ffbf  mov     edx, 16h; SizeInWords
0x14001ffc4  movups  xmmword ptr [rbp+0E0h+var_58+0Ch], xmm0
0x14001ffcb  movups  xmmword ptr [rbp+0E0h+Dst], xmm0
0x14001ffcf  mov     rax, [rdi+30h]
0x14001ffd3  movzx   ecx, word ptr [rax+0Ah]
0x14001ffd7  movzx   r9d, word ptr [rax+8]
0x14001ffdc  mov     dword ptr [rsp+1E0h+ValueData], ecx
0x14001ffe0  lea     rcx, [rbp+0E0h+Dst]; Dst
0x14001ffe4  call    cs:__imp_swprintf_s
0x14001ffeb  nop     dword ptr [rax+rax+00h]
0x14001fff0  test    eax, eax
0x14001fff2  js      loc_14002016B
0x14001fff8  add     ax, ax
0x14001fffb  mov     ecx, 100h
0x140020000  add     ax, [rbp+0E0h+var_138.MaximumLength]
0x140020004  mov     r8d, 53414D55h
0x14002000a  add     ax, [rbp+0E0h+var_148.MaximumLength]
0x14002000e  add     ax, [rbp+0E0h+SourceString.MaximumLength]
0x140020012  movzx   ebx, ax
0x140020015  mov     edx, ebx
0x140020017  call    cs:__imp_ExAllocatePool2
0x14002001e  nop     dword ptr [rax+rax+00h]
0x140020023  mov     [rsp+1E0h+DestinationString.Buffer], rax
0x140020028  test    rax, rax
0x14002002b  jnz     short loc_140020063
0x14002002d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020034  lea     rax, WPP_GLOBAL_Control
0x14002003b  cmp     rcx, rax
0x14002003e  jz      loc_140020199
0x140020044  mov     eax, [rcx+2Ch]
0x140020047  test    al, 2
0x140020049  jz      loc_140020199
0x14002004f  cmp     byte ptr [rcx+29h], 2
0x140020053  jb      loc_140020199
0x140020059  mov     edx, 71h ; 'q'
0x14002005e  jmp     loc_140020189
0x140020063  lea     rdx, [rbp+0E0h+SourceString]; SourceString
0x140020067  mov     [rsp+1E0h+DestinationString.Length], si
0x14002006c  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x140020071  mov     [rsp+1E0h+DestinationString.MaximumLength], bx
0x140020076  call    RtlUnicodeStringCat
0x14002007b  mov     rdx, [rsp+1E0h+DestinationString.Buffer]; Path
0x140020080  mov     ebx, 2
0x140020085  mov     ecx, ebx; RelativeTo
0x140020087  call    cs:__imp_RtlCreateRegistryKey
0x14002008e  nop     dword ptr [rax+rax+00h]
0x140020093  lea     rdx, [rbp+0E0h+Dst]; pszSrc
0x140020097  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x14002009c  call    RtlUnicodeStringCatString
0x1400200a1  mov     rdx, [rsp+1E0h+DestinationString.Buffer]; Path
0x1400200a6  mov     ecx, ebx; RelativeTo
0x1400200a8  call    cs:__imp_RtlCreateRegistryKey
0x1400200af  nop     dword ptr [rax+rax+00h]
0x1400200b4  lea     rdx, [rbp+0E0h+var_148]; SourceString
0x1400200b8  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1400200bd  call    RtlUnicodeStringCat
0x1400200c2  mov     rdx, [rsp+1E0h+DestinationString.Buffer]; Path
0x1400200c7  mov     ecx, ebx; RelativeTo
0x1400200c9  call    cs:__imp_RtlCreateRegistryKey
0x1400200d0  nop     dword ptr [rax+rax+00h]
0x1400200d5  lea     rdx, [rbp+0E0h+var_138]; SourceString
0x1400200d9  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1400200de  call    RtlUnicodeStringCat
0x1400200e3  mov     rdx, [rsp+1E0h+DestinationString.Buffer]; Path
0x1400200e8  mov     ecx, ebx; RelativeTo
0x1400200ea  call    cs:__imp_RtlCreateRegistryKey
0x1400200f1  nop     dword ptr [rax+rax+00h]
0x1400200f6  mov     rdx, [rsp+1E0h+DestinationString.Buffer]; Path
0x1400200fb  lea     ecx, [rbx+2]
0x1400200fe  mov     [rsp+1E0h+ValueLength], ecx; ValueLength
0x140020102  lea     rax, [rsp+1E0h+var_198]
0x140020107  mov     r9d, ecx; ValueType
0x14002010a  mov     [rsp+1E0h+var_198], esi
0x14002010e  mov     ecx, ebx; RelativeTo
0x140020110  mov     [rsp+1E0h+ValueData], rax; ValueData
0x140020115  lea     r8, aRemovable; "Removable"
0x14002011c  call    cs:__imp_RtlWriteRegistryValue
0x140020123  nop     dword ptr [rax+rax+00h]
0x140020128  mov     rcx, [rsp+1E0h+DestinationString.Buffer]; P
0x14002012d  mov     edx, 53414D55h; Tag
0x140020132  mov     ebx, eax
0x140020134  call    cs:__imp_ExFreePoolWithTag
0x14002013b  nop     dword ptr [rax+rax+00h]
0x140020140  test    ebx, ebx
0x140020142  jns     short loc_140020199
0x140020144  mov     rcx, cs:WPP_GLOBAL_Control
0x14002014b  lea     rax, WPP_GLOBAL_Control
0x140020152  cmp     rcx, rax
0x140020155  jz      short loc_140020199
0x140020157  mov     eax, [rcx+2Ch]
0x14002015a  test    al, 2
0x14002015c  jz      short loc_140020199
0x14002015e  cmp     byte ptr [rcx+29h], 2
0x140020162  jb      short loc_140020199
0x140020164  mov     edx, 72h ; 'r'
0x140020169  jmp     short loc_140020189
0x14002016b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020172  cmp     rcx, rbx
0x140020175  jz      short loc_140020199
0x140020177  mov     eax, [rcx+2Ch]
0x14002017a  test    al, 2
0x14002017c  jz      short loc_140020199
0x14002017e  cmp     byte ptr [rcx+29h], 2
0x140020182  jb      short loc_140020199
0x140020184  mov     edx, 73h ; 's'
0x140020189  mov     rcx, [rcx+18h]
0x14002018d  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140020194  call    WPP_SF_
0x140020199  mov     eax, [rdi+84h]
0x14002019f  test    al, 40h
0x1400201a1  jnz     loc_140020372
0x1400201a7  mov     rax, [rdi+30h]
0x1400201ab  lea     r8, aUsbstor04x04x_0; "usbstor\\%04X%04X"
0x1400201b2  mov     edx, 16h; SizeInWords
0x1400201b7  movzx   ecx, word ptr [rax+0Ah]
0x1400201bb  movzx   r9d, word ptr [rax+8]
0x1400201c0  mov     dword ptr [rsp+1E0h+ValueData], ecx
0x1400201c4  lea     rcx, [rbp+0E0h+Dst]; Dst
0x1400201c8  call    cs:__imp_swprintf_s
  ... truncated ...
```
