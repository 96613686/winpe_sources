# BthEnumEnumerateProtocolOrDevice

- ea: `0x14001e1e0`
- end: `0x14001ec30`
- name: `BthEnumEnumerateProtocolOrDevice`
- size: `2640`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001214`
- `0x140001328`
- `0x1400013e8`
- `0x140003328`
- `0x140003428`
- `0x14000366c`
- `0x140007d00`
- `0x140007e40`
- `0x140008140`
- `0x14001aaac`
- `0x14001df2c`
- `0x14001e034`
- `0x14001e1e0`
- `0x14001ec38`

## import_xrefs

- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14001e96a`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x14001e96a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e983`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e983`
- `ntoskrnl!RtlCompareMemory` at `0x14001e36b`
- `ntoskrnl!RtlCompareMemory` at `0x14001e389`
- `ntoskrnl!RtlCompareMemory` at `0x14001e3a7`
- `ntoskrnl!RtlCompareMemory` at `0x14001e6de`
- `ntoskrnl!RtlCompareMemory` at `0x14001e6fd`
- `ntoskrnl!RtlCompareMemory` at `0x14001e36b`
- `ntoskrnl!RtlCompareMemory` at `0x14001e389`
- `ntoskrnl!RtlCompareMemory` at `0x14001e3a7`
- `ntoskrnl!RtlCompareMemory` at `0x14001e6de`
- `ntoskrnl!RtlCompareMemory` at `0x14001e6fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e4d0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e4d0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e4ea`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001e4ea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e66e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ebd4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001e66e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ebd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e67a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ebe0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e67a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ebe0`
- `ntoskrnl!RtlStringFromGUID` at `0x14001e3da`
- `ntoskrnl!RtlStringFromGUID` at `0x14001e3da`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e755`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001e755`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14001e7b5`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14001e7b5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001e7d3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001e7d3`
- `ntoskrnl!IoCreateDevice` at `0x14001e816`
- `ntoskrnl!IoCreateDevice` at `0x14001e85f`
- `ntoskrnl!IoCreateDevice` at `0x14001e816`
- `ntoskrnl!IoCreateDevice` at `0x14001e85f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e69d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e69d`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14001ec04`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14001ec04`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14001e653`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14001e653`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001ebba`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001ebba`
- `ntoskrnl!ExFreePool` at `0x14001e828`
- `ntoskrnl!ExFreePool` at `0x14001ec1f`
- `ntoskrnl!ExFreePool` at `0x14001e828`
- `ntoskrnl!ExFreePool` at `0x14001ec1f`
- `ntoskrnl!ExAllocatePool2` at `0x14001e404`
- `ntoskrnl!ExAllocatePool2` at `0x14001e72b`
- `ntoskrnl!ExAllocatePool2` at `0x14001e943`
- `ntoskrnl!ExAllocatePool2` at `0x14001e404`
- `ntoskrnl!ExAllocatePool2` at `0x14001e72b`
- `ntoskrnl!ExAllocatePool2` at `0x14001e943`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e3c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e771`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e3c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e771`

## pseudocode

```c
__int64 __fastcall BthEnumEnumerateProtocolOrDevice(__int64 a1, __int64 a2, __int64 a3)
{
  _OWORD *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // r15
  _QWORD *v7; // r13
  int v8; // edx
  NTSTATUS appended; // ebx
  int v10; // ecx
  int v11; // edx
  __int64 v13; // rsi
  __int64 Pool2; // rax
  int v15; // edx
  int v16; // r9d
  NTSTATUS v17; // eax
  __int64 v18; // r12
  bool v19; // zf
  __int64 v20; // rbx
  int v21; // esi
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  _OWORD *v26; // rcx
  __int128 v27; // xmm1
  __int16 v28; // cx
  ULONG v29; // ecx
  __int64 v30; // r15
  _DWORD *DeviceExtension; // rsi
  _BYTE *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r15
  WCHAR *v35; // rax
  _OWORD *v36; // rax
  __int128 v37; // xmm1
  __int64 v38; // rax
  __int64 v39; // r8
  _OWORD *v40; // rcx
  __int64 v41; // rax
  __int128 v42; // xmm1
  __int64 v43; // r13
  __int64 v44; // rcx
  unsigned __int64 v45; // rdi
  int v46; // r14d
  __int64 v47; // rcx
  _QWORD *v48; // rax
  unsigned __int64 v49; // rcx
  int DeviceCharacteristics; // [rsp+20h] [rbp-99h]
  BOOLEAN Exclusive[8]; // [rsp+28h] [rbp-91h]
  PDEVICE_OBJECT *DeviceObject; // [rsp+30h] [rbp-89h]
  __int64 v53; // [rsp+38h] [rbp-81h]
  PDEVICE_OBJECT v54; // [rsp+40h] [rbp-79h] BYREF
  ULONG UnicodeStringActualByteCount; // [rsp+48h] [rbp-71h] BYREF
  __int64 v56; // [rsp+50h] [rbp-69h]
  __int64 v57; // [rsp+58h] [rbp-61h]
  __int64 v58; // [rsp+60h] [rbp-59h]
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-51h] BYREF
  struct _UNICODE_STRING String; // [rsp+78h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-31h] BYREF
  _QWORD *v62; // [rsp+98h] [rbp-21h]
  _OWORD *v63; // [rsp+A0h] [rbp-19h]
  PFAST_MUTEX FastMutex; // [rsp+A8h] [rbp-11h]
  _OWORD v65[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v66; // [rsp+D0h] [rbp+17h]

  v57 = a1;
  v54 = 0;
  v4 = (_OWORD *)a2;
  v5 = a1;
  DestinationString = 0;
  if ( a2 )
    v6 = *(_QWORD *)(a2 + 8);
  else
    v6 = 0;
  v7 = 0;
  Destination = 0;
  UnicodeStringActualByteCount = 0;
  String = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v53 = a3;
    DeviceObject = (PDEVICE_OBJECT *)a2;
    *(_DWORD *)&Exclusive[4] = HIDWORD(a1);
    WPP_RECORDER_SF_qqq(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a1);
    v5 = v57;
  }
  v8 = *(_DWORD *)a3;
  if ( *(int *)a3 >= 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        4,
        30,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids);
LABEL_9:
    appended = -1073741811;
    goto LABEL_59;
  }
  v10 = *(_DWORD *)(a3 + 4);
  appended = 0;
  if ( v10 )
  {
    if ( (unsigned int)(v10 - 1) <= 1 )
    {
      BthEnumRemoveProtocol(v5, v4, a3);
      goto LABEL_13;
    }
    goto LABEL_9;
  }
  v13 = *(_QWORD *)(v5 + 64);
  v58 = v13;
  if ( v8 != 1 )
  {
LABEL_21:
    RtlInitUnicodeString(&DestinationString, 0);
    if ( RtlStringFromGUID((const GUID *const)(a3 + 16), &DestinationString) < 0 )
    {
      appended = -1073741670;
      goto LABEL_59;
    }
    Pool2 = ExAllocatePool2(256, 2928, 1330467906);
    v62 = (_QWORD *)Pool2;
    v7 = (_QWORD *)Pool2;
    if ( !Pool2 )
    {
      appended = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_59;
      v16 = 31;
      *(_DWORD *)Exclusive = -1073741670;
      goto LABEL_26;
    }
    v63 = (_OWORD *)(Pool2 + 24);
    v17 = RtlStringCbPrintfW((NTSTRSAFE_PWSTR)(Pool2 + 24), 0x1Au, L"%04X%08X", WORD2(v6), v6);
    appended = v17;
    if ( v17 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = 32;
        *(_DWORD *)Exclusive = v17;
LABEL_26:
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          4,
          v16,
          (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
          *(_QWORD *)Exclusive,
          DeviceObject,
          v53);
      }
LABEL_59:
      RtlFreeUnicodeString(&DestinationString);
      if ( !v7 )
        goto LABEL_13;
      goto LABEL_124;
    }
    v7[7] = DestinationString.Buffer;
    memmove(v7 + 130, (const void *)a3, 0x730u);
    KeEnterCriticalRegion();
    FastMutex = (PFAST_MUTEX)(v13 + 152);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v13 + 152));
    v18 = v13 + 136;
    v19 = (*(_BYTE *)(v13 + 144) & 1) == 0;
    v20 = *(_QWORD *)(v13 + 136);
    v56 = v13 + 136;
    if ( !v19 && v20 )
      v20 ^= v18;
    v21 = *(_BYTE *)(v13 + 144) & 1;
    while ( v20 )
    {
      v22 = BthEnumChildCompare(v7, v20);
      if ( v22 >= 0 )
      {
        if ( v22 <= 0 )
          break;
        v23 = *(_QWORD *)(v20 + 8);
      }
      else
      {
        v23 = *(_QWORD *)v20;
      }
      if ( v21 && v23 )
        v20 ^= v23;
      else
        v20 = v23;
    }
    v24 = *(_DWORD *)a3;
    if ( v20 )
    {
      if ( v24 != 2 )
        goto LABEL_61;
      if ( v4 )
      {
        v25 = 6;
        v26 = (_OWORD *)(v20 + 104);
        do
        {
          *v26 = *v4;
          v26[1] = v4[1];
          v26[2] = v4[2];
          v26[3] = v4[3];
          v26[4] = v4[4];
          v26[5] = v4[5];
          v26[6] = v4[6];
          v27 = v4[7];
          v4 += 8;
          v26[7] = v27;
          v26 += 8;
          --v25;
        }
        while ( v25 );
        *v26 = *v4;
        v26[1] = v4[1];
        v26[2] = v4[2];
        v26[3] = v4[3];
        v26[4] = v4[4];
        *((_QWORD *)v26 + 10) = *((_QWORD *)v4 + 10);
      }
      v28 = *(_WORD *)(a3 + 556);
      if ( v28 && *(_WORD *)(a3 + 548) && *(_WORD *)(a3 + 550) )
      {
        *(_WORD *)(v20 + 1516) = v28;
        *(_WORD *)(v20 + 1508) = *(_WORD *)(a3 + 548);
        *(_WORD *)(v20 + 1510) = *(_WORD *)(a3 + 550);
      }
      if ( *(_BYTE *)(v20 + 2840) )
      {
        BthEnumSetDevicePdoProperties(v20 - 80, 0);
        IoInvalidateDeviceState(*(PDEVICE_OBJECT *)(v20 - 64));
      }
      if ( (unsigned int)Feature_56664216__private_IsEnabledDeviceUsageNoInline() )
        appended = 0;
      else
LABEL_61:
        appended = -1073741811;
      goto LABEL_57;
    }
    if ( v24 == 1
      && (RtlCompareMemory(&DialupNetworkingServiceClass_UUID, (const void *)(a3 + 16), 0x10u) == 16
       || RtlCompareMemory(&SerialPortServiceClass_UUID, (const void *)(a3 + 16), 0x10u) == 16) )
    {
      *(_QWORD *)&Destination.Length = 0x1000000;
      Destination.Buffer = (wchar_t *)ExAllocatePool2(256, 258, 1330467906);
      if ( !Destination.Buffer )
      {
        appended = -1073741670;
        goto LABEL_57;
      }
      appended = RtlAppendUnicodeToString(&Destination, L"\\Device\\BthModem");
      if ( appended < 0 )
        goto LABEL_57;
      RtlInitUnicodeString(&String, 0);
      v29 = Value;
      *(_DWORD *)&String.Length = 2621440;
      v66 = 0;
      String.Buffer = (wchar_t *)v65;
      ++Value;
      memset(v65, 0, sizeof(v65));
      appended = RtlIntegerToUnicodeString(v29, 0xAu, &String);
      if ( appended < 0 )
        goto LABEL_57;
      appended = RtlAppendUnicodeStringToString(&Destination, &String);
      if ( appended < 0 )
        goto LABEL_57;
      v30 = v57;
      appended = IoCreateDevice(*(PDRIVER_OBJECT *)(v57 + 8), 0xB70u, &Destination, 0x22u, 0, 0, &v54);
      ExFreePool(Destination.Buffer);
    }
    else
    {
      v30 = v57;
      appended = IoCreateDevice(*(PDRIVER_OBJECT *)(v57 + 8), 0xB70u, 0, 0x22u, 0x80u, 0, &v54);
    }
    if ( appended >= 0 )
    {
      DeviceExtension = v54->DeviceExtension;
      memset(DeviceExtension, 0, 0xB70u);
      if ( *(_DWORD *)a3 )
      {
        if ( *(_DWORD *)a3 == 1 )
        {
          *DeviceExtension = 542065744;
        }
        else if ( *(_DWORD *)a3 == 2 )
        {
          *DeviceExtension = 1329877060;
        }
      }
      else
      {
        *DeviceExtension = 1329877076;
      }
      *((_QWORD *)DeviceExtension + 1) = v30;
      *((_QWORD *)DeviceExtension + 2) = v54;
      DeviceExtension[45] = 0;
      *((_QWORD *)DeviceExtension + 7) = DestinationString.Buffer;
      DeviceExtension[44] = 0;
      *((_BYTE *)DeviceExtension + 2920) = 0;
      if ( !*((_QWORD *)DeviceExtension + 9) )
      {
        if ( a3 != -1070 )
        {
          v32 = (_BYTE *)(a3 + 1070);
          v33 = 256;
          do
          {
            if ( !*v32 )
              break;
            ++v32;
            --v33;
          }
          while ( v33 );
          v34 = (256 - v33) & -(__int64)(v33 != 0);
          if ( v33 )
          {
            if ( v34 )
            {
              UnicodeStringActualByteCount = 2 * v34 + 2;
              v35 = (WCHAR *)ExAllocatePool2(64, UnicodeStringActualByteCount, 1330467906);
              *((_QWORD *)DeviceExtension + 9) = v35;
              if ( v35 )
              {
                if ( RtlUTF8ToUnicodeN(
                       v35,
                       UnicodeStringActualByteCount,
                       &UnicodeStringActualByteCount,
                       (PCCH)(a3 + 1070),
                       v34) < 0 )
                {
                  ExFreePoolWithTag(*((PVOID *)DeviceExtension + 9), 0x42544D45u);
                  *((_QWORD *)DeviceExtension + 9) = 0;
                }
              }
            }
          }
        }
        v18 = v56;
      }
      v36 = v63;
      *(_OWORD *)(DeviceExtension + 6) = *v63;
      v37 = *(_OWORD *)((char *)v36 + 10);
      v38 = v57;
      *(_OWORD *)((char *)DeviceExtension + 34) = v37;
      v54->StackSize += *(_BYTE *)(v38 + 76);
      memmove(DeviceExtension + 260, (const void *)a3, 0x730u);
      if ( v4 )
      {
        v40 = DeviceExtension + 46;
        v41 = 6;
        do
        {
          *v40 = *v4;
          v40[1] = v4[1];
          v40[2] = v4[2];
          v40[3] = v4[3];
          v40[4] = v4[4];
          v40[5] = v4[5];
          v40[6] = v4[6];
          v42 = v4[7];
          v4 += 8;
          v40[7] = v42;
          v40 += 8;
          --v41;
        }
        while ( v41 );
        *v40 = *v4;
        v40[1] = v4[1];
        v40[2] = v4[2];
        v40[3] = v4[3];
        v40[4] = v4[4];
        *((_QWORD *)v40 + 10) = *((_QWORD *)v4 + 10);
      }
      v43 = v58;
      *((_QWORD *)DeviceExtension + 21) = 0;
      if ( (*(_DWORD *)(v43 + 248) & 1) != 0 )
      {
        appended = BthEnumCheckGuidAgainstRegistry(DeviceExtension + 264);
        if ( appended >= 0 )
        {
          DeviceExtension[720] = 1;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              3,
              33,
              (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids);
        }
        else
        {
          DeviceExtension[720] = 0;
          appended = 0;
        }
      }
      v44 = v57;
      if ( (*(_DWORD *)(v57 + 48) & 4) != 0 )
        v54->Flags |= 4u;
      if ( (*(_DWORD *)(v44 + 48) & 0x10) != 0 )
        v54->Flags |= 4u;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SS(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)&WPP_RECORDER_INITIALIZED,
          v39,
          34,
          DeviceCharacteristics,
          (__int64)DestinationString.Buffer,
          (__int64)(DeviceExtension + 6));
      v45 = *(_QWORD *)v18;
      if ( (*(_BYTE *)(v18 + 8) & 1) != 0 && v45 )
        v45 ^= v18;
      LOBYTE(v39) = 0;
      v46 = *(_BYTE *)(v18 + 8) & 1;
      if ( v45 )
      {
        while ( 1 )
        {
          if ( (int)BthEnumChildCompare(DeviceExtension, v45) < 0 )
          {
            v49 = *(_QWORD *)v45;
            if ( v46 && v49 )
              v48 = (_QWORD *)(v49 ^ v45);
            else
              v48 = *(_QWORD **)v45;
            if ( !v48 )
            {
              LOBYTE(v39) = 0;
              break;
            }
          }
          else
          {
            v47 = *(_QWORD *)(v45 + 8);
            if ( v46 && v47 )
              v48 = (_QWORD *)(v47 ^ v45);
            else
              v48 = *(_QWORD **)(v45 + 8);
            if ( !v48 )
            {
              LOBYTE(v39) = 1;
              break;
            }
          }
          v45 = (unsigned __int64)v48;
        }
      }
      RtlRbInsertNodeEx(v18, v45, v39, DeviceExtension + 20);
      ++*(_DWORD *)(v43 + 252);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v43 + 152));
      KeLeaveCriticalRegion();
      v54->Flags |= 0x2000u;
      v54->Flags &= ~0x80u;
      IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(v43 + 16), BusRelations);
LABEL_58:
      v7 = v62;
      if ( appended >= 0 )
      {
LABEL_124:
        ExFreePool(v7);
        goto LABEL_13;
      }
      goto LABEL_59;
    }
LABEL_57:
    ExReleaseFastMutexUnsafe(FastMutex);
    KeLeaveCriticalRegion();
    goto LABEL_58;
  }
  if ( RtlCompareMemory(&DialupNetworkingServiceClass_UUID, (const void *)(a3 + 16), 0x10u) == 16
    || RtlCompareMemory(&SerialPortServiceClass_UUID, (const void *)(a3 + 16), 0x10u) == 16
    || RtlCompareMemory(&FaxServiceClass_UUID, (const void *)(a3 + 16), 0x10u) == 16 )
  {
    v13 = v58;
    goto LABEL_21;
  }
LABEL_13:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    *(_DWORD *)Exclusive = appended;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      4,
      35,
      (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
      *(_QWORD *)Exclusive);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001e1e0  mov     [rsp-8+arg_18], rbx
0x14001e1e5  push    rbp
0x14001e1e6  push    rsi
0x14001e1e7  push    rdi
0x14001e1e8  push    r12
0x14001e1ea  push    r13
0x14001e1ec  push    r14
0x14001e1ee  push    r15
0x14001e1f0  lea     rbp, [rsp-27h]
0x14001e1f5  sub     rsp, 0E0h
0x14001e1fc  mov     rax, cs:__security_cookie
0x14001e203  xor     rax, rsp
0x14001e206  mov     [rbp+57h+var_38], rax
0x14001e20a  mov     [rbp+57h+var_B8], rcx
0x14001e20e  xorps   xmm0, xmm0
0x14001e211  mov     [rbp+57h+var_D0], 0
0x14001e219  mov     r14, r8
0x14001e21c  mov     rdi, rdx
0x14001e21f  mov     r9, rcx
0x14001e222  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001e226  test    rdx, rdx
0x14001e229  jnz     short loc_14001E230
0x14001e22b  xor     r15d, r15d
0x14001e22e  jmp     short loc_14001E234
0x14001e230  mov     r15, [rdx+8]
0x14001e234  xor     r13d, r13d
0x14001e237  xorps   xmm1, xmm1
0x14001e23a  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x14001e23e  mov     [rbp+57h+UnicodeStringActualByteCount], r13d
0x14001e242  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x14001e246  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e24d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e254  jz      short loc_14001E280
0x14001e256  mov     [rsp+110h+var_D8], r14
0x14001e25b  mov     [rsp+110h+DeviceObject], rdi
0x14001e260  mov     qword ptr [rsp+110h+Exclusive], rcx
0x14001e265  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e26c  mov     rcx, [rcx+40h]
0x14001e270  call    WPP_RECORDER_SF_qqq
0x14001e275  mov     r9, [rbp+57h+var_B8]
0x14001e279  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e280  mov     edx, [r14]
0x14001e283  lea     rcx, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001e28a  cmp     edx, 3
0x14001e28d  jl      short loc_14001E2C1
0x14001e28f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e296  jz      short loc_14001E2B7
0x14001e298  mov     qword ptr [rsp+110h+DeviceCharacteristics], rcx
0x14001e29d  mov     r9d, 1Eh
0x14001e2a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2aa  lea     r8d, [r9-1Ah]
0x14001e2ae  mov     rcx, [rcx+40h]
0x14001e2b2  call    WPP_RECORDER_SF_
0x14001e2b7  mov     ebx, 0C000000Dh
0x14001e2bc  jmp     loc_14001E692
0x14001e2c1  mov     ecx, [r14+4]
0x14001e2c5  xor     ebx, ebx
0x14001e2c7  test    ecx, ecx
0x14001e2c9  jz      short loc_14001E347
0x14001e2cb  sub     ecx, 1
0x14001e2ce  jz      short loc_14001E2D5
0x14001e2d0  cmp     ecx, 1
0x14001e2d3  jnz     short loc_14001E2B7
0x14001e2d5  mov     r8, r14
0x14001e2d8  mov     rdx, rdi
0x14001e2db  mov     rcx, r9
0x14001e2de  call    BthEnumRemoveProtocol
0x14001e2e3  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001e2ea  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001e2f1  jz      short loc_14001E31D
0x14001e2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2fa  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001e301  mov     r9d, 23h ; '#'
0x14001e307  mov     dword ptr [rsp+110h+Exclusive], ebx
0x14001e30b  mov     qword ptr [rsp+110h+DeviceCharacteristics], rax
0x14001e310  mov     rcx, [rcx+40h]
0x14001e314  lea     r8d, [r9-1Fh]
0x14001e318  call    WPP_RECORDER_SF_d
0x14001e31d  mov     eax, ebx
0x14001e31f  mov     rcx, [rbp+57h+var_38]
0x14001e323  xor     rcx, rsp; StackCookie
0x14001e326  call    __security_check_cookie
0x14001e32b  mov     rbx, [rsp+110h+arg_18]
0x14001e333  add     rsp, 0E0h
0x14001e33a  pop     r15
0x14001e33c  pop     r14
0x14001e33e  pop     r13
0x14001e340  pop     r12
0x14001e342  pop     rdi
0x14001e343  pop     rsi
0x14001e344  pop     rbp
0x14001e345  retn
0x14001e347  mov     rsi, [r9+40h]
0x14001e34b  mov     r12d, 10h
0x14001e351  mov     [rbp+57h+var_B0], rsi
0x14001e355  cmp     edx, 1
0x14001e358  jnz     short loc_14001E3C0
0x14001e35a  lea     rsi, [r14+10h]
0x14001e35e  mov     r8d, r12d; Length
0x14001e361  mov     rdx, rsi; Source2
0x14001e364  lea     rcx, DialupNetworkingServiceClass_UUID; Source1
0x14001e36b  call    cs:__imp_RtlCompareMemory
0x14001e372  nop     dword ptr [rax+rax+00h]
0x14001e377  cmp     rax, r12
0x14001e37a  jz      short loc_14001E3BC
0x14001e37c  mov     r8d, r12d; Length
0x14001e37f  lea     rcx, SerialPortServiceClass_UUID; Source1
0x14001e386  mov     rdx, rsi; Source2
0x14001e389  call    cs:__imp_RtlCompareMemory
0x14001e390  nop     dword ptr [rax+rax+00h]
0x14001e395  cmp     rax, r12
0x14001e398  jz      short loc_14001E3BC
0x14001e39a  mov     r8d, r12d; Length
0x14001e39d  lea     rcx, FaxServiceClass_UUID; Source1
0x14001e3a4  mov     rdx, rsi; Source2
0x14001e3a7  call    cs:__imp_RtlCompareMemory
0x14001e3ae  nop     dword ptr [rax+rax+00h]
0x14001e3b3  cmp     rax, r12
0x14001e3b6  jnz     loc_14001E2E3
0x14001e3bc  mov     rsi, [rbp+57h+var_B0]
0x14001e3c0  xor     edx, edx; SourceString
0x14001e3c2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e3c6  call    cs:__imp_RtlInitUnicodeString
0x14001e3cd  nop     dword ptr [rax+rax+00h]
0x14001e3d2  lea     rcx, [r14+10h]; Guid
0x14001e3d6  lea     rdx, [rbp+57h+DestinationString]; GuidString
0x14001e3da  call    cs:__imp_RtlStringFromGUID
0x14001e3e1  nop     dword ptr [rax+rax+00h]
0x14001e3e6  test    eax, eax
0x14001e3e8  jns     short loc_14001E3F4
0x14001e3ea  mov     ebx, 0C000009Ah
0x14001e3ef  jmp     loc_14001E692
0x14001e3f4  mov     edx, 0B70h
0x14001e3f9  mov     ecx, 100h
0x14001e3fe  mov     r8d, 4F4D5442h
0x14001e404  call    cs:__imp_ExAllocatePool2
0x14001e40b  nop     dword ptr [rax+rax+00h]
0x14001e410  mov     [rbp+57h+var_78], rax
0x14001e414  mov     r13, rax
0x14001e417  test    rax, rax
0x14001e41a  jnz     short loc_14001E464
0x14001e41c  mov     ebx, 0C000009Ah
0x14001e421  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001e428  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001e42f  jz      loc_14001E699
0x14001e435  lea     r9d, [rax+1Fh]
0x14001e439  mov     dword ptr [rsp+110h+Exclusive], ebx
0x14001e43d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e444  lea     rax, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001e44b  mov     r8d, 4
0x14001e451  mov     qword ptr [rsp+110h+DeviceCharacteristics], rax
0x14001e456  mov     rcx, [rcx+40h]
0x14001e45a  call    WPP_RECORDER_SF_d
0x14001e45f  jmp     loc_14001E699
0x14001e464  lea     rcx, [rax+18h]; pszDest
0x14001e468  mov     [rsp+110h+DeviceCharacteristics], r15d
0x14001e46d  mov     rax, r15
0x14001e470  mov     [rbp+57h+var_70], rcx
0x14001e474  shr     rax, 20h
0x14001e478  lea     r8, a04x08x; "%04X%08X"
0x14001e47f  movzx   r9d, ax
0x14001e483  mov     edx, 1Ah; cbDest
0x14001e488  call    RtlStringCbPrintfW
0x14001e48d  mov     ebx, eax
0x14001e48f  test    eax, eax
0x14001e491  jns     short loc_14001E4B3
0x14001e493  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001e49a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001e4a1  jz      loc_14001E699
0x14001e4a7  mov     r9d, 20h ; ' '
0x14001e4ad  mov     dword ptr [rsp+110h+Exclusive], eax
0x14001e4b1  jmp     short loc_14001E43D
0x14001e4b3  mov     rax, [rbp+57h+DestinationString.Buffer]
0x14001e4b7  lea     rcx, [r13+410h]; void *
0x14001e4be  mov     rdx, r14; Src
0x14001e4c1  mov     [r13+38h], rax
0x14001e4c5  mov     r8d, 730h; Size
0x14001e4cb  call    memmove
0x14001e4d0  call    cs:__imp_KeEnterCriticalRegion
0x14001e4d7  nop     dword ptr [rax+rax+00h]
0x14001e4dc  lea     rax, [rsi+98h]
0x14001e4e3  mov     rcx, rax; FastMutex
0x14001e4e6  mov     [rbp+57h+FastMutex], rax
0x14001e4ea  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001e4f1  nop     dword ptr [rax+rax+00h]
0x14001e4f6  lea     r12, [rsi+88h]
0x14001e4fd  test    byte ptr [r12+8], 1
0x14001e503  mov     rbx, [r12]
0x14001e507  mov     [rbp+57h+var_C0], r12
0x14001e50b  jz      short loc_14001E515
0x14001e50d  test    rbx, rbx
0x14001e510  jz      short loc_14001E515
0x14001e512  xor     rbx, r12
0x14001e515  movzx   esi, byte ptr [r12+8]
0x14001e51b  and     esi, 1
0x14001e51e  jmp     short loc_14001E54B
0x14001e520  mov     rdx, rbx
0x14001e523  mov     rcx, r13
0x14001e526  call    BthEnumChildCompare
0x14001e52b  test    eax, eax
0x14001e52d  jns     short loc_14001E534
0x14001e52f  mov     rax, [rbx]
0x14001e532  jmp     short loc_14001E53A
0x14001e534  jle     short loc_14001E550
0x14001e536  mov     rax, [rbx+8]
0x14001e53a  test    esi, esi
0x14001e53c  jz      short loc_14001E548
0x14001e53e  test    rax, rax
0x14001e541  jz      short loc_14001E548
0x14001e543  xor     rbx, rax
0x14001e546  jmp     short loc_14001E54B
0x14001e548  mov     rbx, rax
0x14001e54b  test    rbx, rbx
0x14001e54e  jnz     short loc_14001E520
0x14001e550  mov     eax, [r14]
0x14001e553  test    rbx, rbx
0x14001e556  jz      loc_14001E6BE
0x14001e55c  cmp     eax, 2
0x14001e55f  jnz     loc_14001E6B7
0x14001e565  test    rdi, rdi
0x14001e568  jz      loc_14001E5F3
0x14001e56e  mov     eax, 6
0x14001e573  lea     rcx, [rbx+68h]
0x14001e577  lea     r13d, [rax+7Ah]
0x14001e57b  movups  xmm0, xmmword ptr [rdi]
0x14001e57e  movups  xmmword ptr [rcx], xmm0
0x14001e581  movups  xmm1, xmmword ptr [rdi+10h]
0x14001e585  movups  xmmword ptr [rcx+10h], xmm1
0x14001e589  movups  xmm0, xmmword ptr [rdi+20h]
0x14001e58d  movups  xmmword ptr [rcx+20h], xmm0
0x14001e591  movups  xmm1, xmmword ptr [rdi+30h]
0x14001e595  movups  xmmword ptr [rcx+30h], xmm1
0x14001e599  movups  xmm0, xmmword ptr [rdi+40h]
0x14001e59d  movups  xmmword ptr [rcx+40h], xmm0
0x14001e5a1  movups  xmm1, xmmword ptr [rdi+50h]
0x14001e5a5  movups  xmmword ptr [rcx+50h], xmm1
0x14001e5a9  movups  xmm0, xmmword ptr [rdi+60h]
0x14001e5ad  movups  xmmword ptr [rcx+60h], xmm0
0x14001e5b1  movups  xmm1, xmmword ptr [rdi+70h]
0x14001e5b5  add     rdi, r13
0x14001e5b8  movups  xmmword ptr [rcx+70h], xmm1
0x14001e5bc  add     rcx, r13
0x14001e5bf  sub     rax, 1
0x14001e5c3  jnz     short loc_14001E57B
0x14001e5c5  movups  xmm0, xmmword ptr [rdi]
0x14001e5c8  movups  xmmword ptr [rcx], xmm0
0x14001e5cb  movups  xmm1, xmmword ptr [rdi+10h]
0x14001e5cf  movups  xmmword ptr [rcx+10h], xmm1
0x14001e5d3  movups  xmm0, xmmword ptr [rdi+20h]
0x14001e5d7  movups  xmmword ptr [rcx+20h], xmm0
0x14001e5db  movups  xmm1, xmmword ptr [rdi+30h]
0x14001e5df  movups  xmmword ptr [rcx+30h], xmm1
0x14001e5e3  movups  xmm0, xmmword ptr [rdi+40h]
0x14001e5e7  movups  xmmword ptr [rcx+40h], xmm0
0x14001e5eb  mov     rax, [rdi+50h]
0x14001e5ef  mov     [rcx+50h], rax
0x14001e5f3  movzx   ecx, word ptr [r14+22Ch]
0x14001e5fb  xor     eax, eax
0x14001e5fd  cmp     ax, cx
0x14001e600  jz      short loc_14001E63B
0x14001e602  cmp     ax, [r14+224h]
0x14001e60a  jz      short loc_14001E63B
0x14001e60c  cmp     ax, [r14+226h]
0x14001e614  jz      short loc_14001E63B
0x14001e616  mov     [rbx+5ECh], cx
0x14001e61d  movzx   eax, word ptr [r14+224h]
0x14001e625  mov     [rbx+5E4h], ax
0x14001e62c  movzx   eax, word ptr [r14+226h]
0x14001e634  mov     [rbx+5E6h], ax
0x14001e63b  cmp     byte ptr [rbx+0B18h], 0
0x14001e642  jz      short loc_14001E65F
0x14001e644  xor     edx, edx
0x14001e646  lea     rcx, [rbx-50h]
0x14001e64a  call    BthEnumSetDevicePdoProperties
0x14001e64f  mov     rcx, [rbx-40h]; PhysicalDeviceObject
0x14001e653  call    cs:__imp_IoInvalidateDeviceState
0x14001e65a  nop     dword ptr [rax+rax+00h]
0x14001e65f  call    Feature_56664216__private_IsEnabledDeviceUsageNoInline
0x14001e664  test    eax, eax
0x14001e666  jz      short loc_14001E6B7
0x14001e668  xor     ebx, ebx
0x14001e66a  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x14001e66e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001e675  nop     dword ptr [rax+rax+00h]
0x14001e67a  call    cs:__imp_KeLeaveCriticalRegion
0x14001e681  nop     dword ptr [rax+rax+00h]
0x14001e686  mov     r13, [rbp+57h+var_78]
0x14001e68a  test    ebx, ebx
0x14001e68c  jns     loc_14001EC15
0x14001e692  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001e699  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x14001e69d  call    cs:__imp_RtlFreeUnicodeString
0x14001e6a4  nop     dword ptr [rax+rax+00h]
0x14001e6a9  test    r13, r13
0x14001e6ac  jz      loc_14001E2EA
0x14001e6b2  jmp     loc_14001EC1C
0x14001e6b7  mov     ebx, 0C000000Dh
0x14001e6bc  jmp     short loc_14001E66A
0x14001e6be  mov     r13d, 80h
0x14001e6c4  cmp     eax, 1
  ... truncated ...
```
