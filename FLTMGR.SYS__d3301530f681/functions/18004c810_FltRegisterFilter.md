# FltRegisterFilter

- ea: `0x18004c810`
- end: `0x18004d19b`
- name: `FltRegisterFilter`
- size: `2443`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT Driver, const FLT_REGISTRATION *Registration, PFLT_FILTER *RetFilter)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800875c0`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180014d80`
- `0x18001fc90`
- `0x180024940`
- `0x18004c810`
- `0x18004d1a4`
- `0x18004d7e0`
- `0x18004f6c4`
- `0x1800524c0`
- `0x180054f50`
- `0x180055a88`
- `0x180055fd0`
- `0x180057058`
- `0x18005dcc0`
- `0x180067030`
- `0x1800688d0`
- `0x18006b340`
- `0x180077c90`
- `0x1800788d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18004c8fb`
- `ntoskrnl!ExAllocatePool2` at `0x18004cae5`
- `ntoskrnl!ExAllocatePool2` at `0x18004c8fb`
- `ntoskrnl!ExAllocatePool2` at `0x18004cae5`
- `ntoskrnl!KeInitializeEvent` at `0x18004cb59`
- `ntoskrnl!KeInitializeEvent` at `0x18004cb9a`
- `ntoskrnl!KeInitializeEvent` at `0x18004cbdb`
- `ntoskrnl!KeInitializeEvent` at `0x18004cb59`
- `ntoskrnl!KeInitializeEvent` at `0x18004cb9a`
- `ntoskrnl!KeInitializeEvent` at `0x18004cbdb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18004cd3e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18004cd3e`
- `ntoskrnl!IoGetStackLimits` at `0x18004c954`
- `ntoskrnl!IoGetStackLimits` at `0x18004cf2a`
- `ntoskrnl!IoGetStackLimits` at `0x18004d03a`
- `ntoskrnl!IoGetStackLimits` at `0x18004d0e0`
- `ntoskrnl!IoGetStackLimits` at `0x18004d15a`
- `ntoskrnl!IoGetStackLimits` at `0x18004c954`
- `ntoskrnl!IoGetStackLimits` at `0x18004cf2a`
- `ntoskrnl!IoGetStackLimits` at `0x18004d03a`
- `ntoskrnl!IoGetStackLimits` at `0x18004d0e0`
- `ntoskrnl!IoGetStackLimits` at `0x18004d15a`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18004cfb0`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18004cfb0`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x18004cbfe`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x18004cbfe`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18004ca7e`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18004ca7e`
- `ntoskrnl!ExInitializeFastResource` at `0x18004cb18`
- `ntoskrnl!ExInitializeFastResource` at `0x18004cb18`
- `ntoskrnl!ExDeleteFastResource` at `0x18004cfc0`
- `ntoskrnl!ExDeleteFastResource` at `0x18004cfc0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d121`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18004d121`
- `ntoskrnl!FsRtlSetDriverBacking` at `0x18004ccca`
- `ntoskrnl!FsRtlSetDriverBacking` at `0x18004ccca`

## pseudocode

```c
NTSTATUS __stdcall FltRegisterFilter(
        PDRIVER_OBJECT Driver,
        const FLT_REGISTRATION *Registration,
        PFLT_FILTER *RetFilter)
{
  unsigned __int16 Version; // cx
  int (__fastcall *GenerateFileNameCallback)(_FLT_INSTANCE *, _FILE_OBJECT *, _FLT_CALLBACK_DATA *, unsigned int, unsigned __int8 *, _FLT_NAME_CONTROL *); // rdx
  bool v9; // al
  const _FLT_OPERATION_REGISTRATION *OperationRegistration; // rax
  unsigned int v11; // r15d
  __int64 Pool2; // rax
  __int64 v13; // rdi
  int (__fastcall *v14)(_FLT_INSTANCE *, _FILE_OBJECT *, _FLT_CALLBACK_DATA *, unsigned int, unsigned __int8 *, _FLT_NAME_CONTROL *); // r8
  int (__fastcall *NormalizeNameComponentCallback)(_FLT_INSTANCE *, const _UNICODE_STRING *, unsigned __int16, const _UNICODE_STRING *, _FILE_NAMES_INFORMATION *, unsigned int, unsigned int, void **); // r9
  _DWORD *v16; // rcx
  _DWORD *v17; // rdx
  int v18; // r8d
  __int64 v19; // rax
  __int64 InstanceAltitude; // rbx
  __int64 v21; // rax
  char v22; // bl
  size_t v23; // r8
  __int64 v24; // r12
  char *i; // r15
  char v26; // cl
  unsigned __int16 Length; // cx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 (__fastcall *v30)(); // rcx
  signed __int64 v31; // rax
  signed __int64 v32; // rtt
  unsigned int UniqueIdentifierForObject; // eax
  __int64 v34; // rdx
  unsigned int v35; // eax
  __int64 v36; // [rsp+20h] [rbp-88h]
  unsigned __int64 HighLimit; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int64 v38; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int64 v39; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int64 v41; // [rsp+60h] [rbp-48h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-40h] BYREF
  unsigned __int64 LowLimit; // [rsp+C0h] [rbp+18h] BYREF

  *RetFilter = 0;
  if ( (dword_18003ECD0 & 1) == 0 )
    return -1071906809;
  Version = Registration->Version;
  if ( (Version & 0xFF00) != 0x200 )
    return -1073741811;
  GenerateFileNameCallback = Registration->GenerateFileNameCallback;
  v9 = Registration->NormalizeNameComponentCallback
    || Version >= 0x202u && Registration->NormalizeNameComponentExCallback;
  if ( GenerateFileNameCallback )
  {
    if ( !v9 )
      return -1073741811;
  }
  else if ( v9 || Registration->NormalizeContextCleanupCallback )
  {
    return -1073741811;
  }
  OperationRegistration = Registration->OperationRegistration;
  v11 = 0;
  if ( OperationRegistration )
  {
    while ( 1 )
    {
      ++v11;
      if ( OperationRegistration->MajorFunction == 0x80 )
        break;
      ++OperationRegistration;
    }
  }
  Pool2 = ExAllocatePool2(64, 32 * v11 + Driver->DriverExtension->ServiceKeyName.Length + 704LL, 1818643782);
  v13 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 264) = Registration->FilterUnloadCallback;
    *(_QWORD *)(Pool2 + 272) = Registration->InstanceSetupCallback;
    *(_QWORD *)(Pool2 + 280) = Registration->InstanceQueryTeardownCallback;
    *(_QWORD *)(Pool2 + 288) = Registration->InstanceTeardownStartCallback;
    *(_QWORD *)(Pool2 + 296) = Registration->InstanceTeardownCompleteCallback;
    v14 = Registration->GenerateFileNameCallback;
    *(_QWORD *)(Pool2 + 384) = v14;
    NormalizeNameComponentCallback = Registration->NormalizeNameComponentCallback;
    *(_QWORD *)(Pool2 + 392) = NormalizeNameComponentCallback;
    *(_QWORD *)(Pool2 + 408) = Registration->NormalizeContextCleanupCallback;
    if ( Registration->Version >= 0x201u )
      *(_QWORD *)(Pool2 + 416) = Registration->TransactionNotificationCallback;
    if ( Registration->Version >= 0x202u )
      *(_QWORD *)(Pool2 + 400) = Registration->NormalizeNameComponentExCallback;
    if ( Registration->Version >= 0x203u )
      *(_QWORD *)(Pool2 + 424) = Registration->SectionNotificationCallback;
    v16 = (_DWORD *)(Pool2 + 96);
    if ( (Registration->Flags & 2) != 0 )
      *v16 |= 8u;
    v17 = (_DWORD *)(Pool2 + 96);
    if ( (Registration->Flags & 4) != 0 )
    {
      v17 = (_DWORD *)(Pool2 + 96);
      *(_DWORD *)(Pool2 + 96) |= 0x20u;
    }
    if ( v14 )
    {
      v16 = v17;
    }
    else if ( !NormalizeNameComponentCallback && !*(_QWORD *)(Pool2 + 400) && !*(_QWORD *)(Pool2 + 408) )
    {
LABEL_41:
      *(_DWORD *)Pool2 = 0x2000000;
      *(_DWORD *)(Pool2 + 4) = 1;
      ExInitializeRundownProtection((PEX_RUNDOWN_REF)(Pool2 + 8));
      v18 = *(_DWORD *)v13;
      *(_QWORD *)(v13 + 16) = 0;
      if ( (v18 & 0x2000000) != 0 && (FltGlobals[0] & 0x2000) != 0
        || (v18 & 0x4000000) != 0 && (FltGlobals[0] & 0x4000) != 0
        || (v18 & 0x1000000) != 0 && (FltGlobals[0] & 0x8000) != 0 )
      {
        v19 = ExAllocatePool2(64, 131080, 1819430214);
      }
      else
      {
        v19 = 0;
      }
      *(_QWORD *)(v13 + 32) = v19;
      *(_OWORD *)(v13 + 40) = 0;
      FltObjectReference((PVOID)v13);
      *(_QWORD *)(v13 + 104) = Driver;
      *(_DWORD *)(v13 + 232) = 0;
      ExInitializeFastResource(v13 + 112, 8);
      *(_QWORD *)(v13 + 224) = v13 + 216;
      *(_QWORD *)(v13 + 216) = v13 + 216;
      *(_DWORD *)(v13 + 520) = 0;
      *(_DWORD *)(v13 + 448) = 1;
      *(_QWORD *)(v13 + 456) = 0;
      *(_DWORD *)(v13 + 464) = 0;
      KeInitializeEvent((PRKEVENT)(v13 + 472), SynchronizationEvent, 0);
      *(_QWORD *)(v13 + 512) = v13 + 504;
      *(_QWORD *)(v13 + 504) = v13 + 504;
      *(_DWORD *)(v13 + 600) = 0;
      *(_DWORD *)(v13 + 528) = 1;
      *(_QWORD *)(v13 + 536) = 0;
      *(_DWORD *)(v13 + 544) = 0;
      KeInitializeEvent((PRKEVENT)(v13 + 552), SynchronizationEvent, 0);
      *(_QWORD *)(v13 + 592) = v13 + 584;
      *(_QWORD *)(v13 + 584) = v13 + 584;
      *(_DWORD *)(v13 + 680) = 0;
      *(_DWORD *)(v13 + 608) = 1;
      *(_QWORD *)(v13 + 616) = 0;
      *(_DWORD *)(v13 + 624) = 0;
      KeInitializeEvent((PRKEVENT)(v13 + 632), SynchronizationEvent, 0);
      *(_QWORD *)(v13 + 672) = v13 + 664;
      *(_QWORD *)(v13 + 664) = v13 + 664;
      ExInitializeAutoExpandPushLock(v13 + 688, 1);
      if ( Registration->ContextRegistration )
      {
        InstanceAltitude = (unsigned int)FltpProcessContextRegistration(v13);
        if ( (int)FltpDbgStatus(InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 325, 0) < 0 )
          goto LABEL_87;
      }
      v21 = v13 + 704;
      if ( Registration->OperationRegistration )
      {
        *(_QWORD *)(v13 + 432) = v21;
        v22 = 0;
        v23 = 32LL * v11;
        v24 = v23 + v21;
        memmove((void *)(v13 + 704), Registration->OperationRegistration, v23);
        for ( i = *(char **)(v13 + 432); ; i += 32 )
        {
          v26 = *i;
          if ( *i == (char)0x80 )
            break;
          if ( v26 == -19 )
          {
            *(_QWORD *)(v13 + 368) = *((_QWORD *)i + 1);
            *(_QWORD *)(v13 + 376) = *((_QWORD *)i + 2);
          }
          else if ( v26 != -20 )
          {
            if ( v26 == 16 )
            {
              *((_QWORD *)i + 2) = 0;
            }
            else if ( (unsigned __int8)(v26 - 3) <= 1u || v26 == 13 )
            {
              if ( !v22 )
              {
                InstanceAltitude = (unsigned int)FsRtlSetDriverBacking(Driver, 1);
                if ( (int)FltpDbgStatus(InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 400, 0) < 0 )
                  goto LABEL_87;
                *(_DWORD *)(v13 + 96) |= 0x10u;
                v22 = 1;
              }
              if ( (unsigned __int8)(*i - 3) <= 1u )
                *(_DWORD *)(v13 + 96) |= 0x80u;
            }
          }
        }
      }
      else
      {
        v24 = v13 + 704;
      }
      Length = Driver->DriverExtension->ServiceKeyName.Length;
      *(_OWORD *)(v13 + 64) = 0;
      *(_WORD *)(v13 + 66) = Length;
      *(_QWORD *)(v13 + 72) = v24;
      RtlCopyUnicodeString((PUNICODE_STRING)(v13 + 64), &Driver->DriverExtension->ServiceKeyName);
      InstanceAltitude = (unsigned int)FltpInitializeFilterVerifier(v13);
      if ( (int)FltpDbgStatus(InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 449, 0) < 0 )
      {
        if ( (byte_180040A41 & 0x40) != 0 )
          McTemplateU0sdw_EtwWriteTransfer(
            *(unsigned __int16 *)(v13 + 64) >> 1,
            (unsigned int)RegSup_c451,
            (unsigned int)"FltRegisterFilter",
            InstanceAltitude,
            *(_WORD *)(v13 + 64) >> 1,
            *(_QWORD *)(v13 + 72));
LABEL_87:
        if ( (int)FltpDbgStatus((unsigned int)InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 590, 0) >= 0 )
        {
          UnicodeString = 0;
          v35 = FltpTelemetrySerializeFilterRegistrationInfo(v13, Registration, &UnicodeString);
          v36 = v13 + 40;
          if ( (int)FltpDbgStatus(v35, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 654, 0) >= 0 )
          {
            FltpLogEventWithObjectID(&FLTMGR_FILTER_REGISTERED, v36);
            if ( (unsigned int)dword_18003E018 > 5 )
            {
              v40 = 0;
              LowLimit = 0;
              IoGetStackLimits(&LowLimit, &v40);
              if ( (unsigned __int64)&v40 - LowLimit >= 0x200 )
                FltpTelemetryFilterRegistration((unsigned int)InstanceAltitude, v13, &UnicodeString, Driver);
              else
                _InterlockedIncrement(&dword_180040530);
            }
            RtlFreeUnicodeString(&UnicodeString);
            return InstanceAltitude;
          }
          FltpLogEventWithObjectID(&FLTMGR_FILTER_REGISTERED, v36);
          if ( (unsigned int)dword_18003E018 <= 5 )
            return InstanceAltitude;
          v41 = 0;
          LowLimit = 0;
          IoGetStackLimits(&LowLimit, &v41);
          if ( (unsigned __int64)&v41 - LowLimit >= 0x200 )
          {
            v34 = v13;
            goto LABEL_103;
          }
        }
        else
        {
          ExCleanupAutoExpandPushLock(v13 + 688);
          ExDeleteFastResource(v13 + 112);
          FltpCleanupContextRegistration(v13);
          FltpCleanupFilterVerifier(v13);
          FltpFreeUnicodeString(v13 + 80);
          if ( (*(_BYTE *)v13 & 3) != 3 )
            _InterlockedOr((volatile signed __int32 *)v13, 3u);
          FltpObjectPointerDereference(v13);
          FltpLogEventWithObjectID(&FLTMGR_REGISTER_FILTER_FAILED, 0);
          if ( (unsigned int)dword_18003E018 <= 5 )
            return InstanceAltitude;
          v39 = 0;
          LowLimit = 0;
          IoGetStackLimits(&LowLimit, &v39);
          if ( (unsigned __int64)&v39 - LowLimit >= 0x200 )
          {
            v34 = 0;
LABEL_103:
            FltpTelemetryFilterRegistration((unsigned int)InstanceAltitude, v34, 0, Driver);
            return InstanceAltitude;
          }
        }
        _InterlockedIncrement(&dword_180040530);
        return InstanceAltitude;
      }
      InstanceAltitude = (unsigned int)FltpGetInstanceAltitude(v13, v28, v29, v13 + 80);
      if ( (int)FltpDbgStatus(InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 474, 0) < 0 )
        goto LABEL_87;
      InstanceAltitude = (unsigned int)FltpFindFrameForFilter(v13, (const UNICODE_STRING *)(v13 + 80));
      if ( (int)FltpDbgStatus(InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 486, 0) < 0 )
        goto LABEL_87;
      if ( *(_QWORD *)(v13 + 416) )
      {
        InstanceAltitude = (unsigned int)FltpCreateKtmResourceManager(
                                           (void **)(*(_QWORD *)(v13 + 56) + 504LL),
                                           (PKRESOURCEMANAGER *)(*(_QWORD *)(v13 + 56) + 512LL),
                                           (NTSTATUS (__stdcall *)(PKENLISTMENT, PVOID, PVOID, ULONG, PLARGE_INTEGER, ULONG, PVOID))FltpKtmNotification,
                                           *(void **)(v13 + 56));
        if ( (int)FltpDbgStatus(InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 503, 0) < 0 )
          goto LABEL_87;
      }
      InstanceAltitude = (unsigned int)FltpLinkFilterIntoFrame(v13);
      if ( (int)FltpDbgStatus(InstanceAltitude, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 515, 0) < 0 )
        goto LABEL_87;
      *(_QWORD *)(v13 + 440) = Driver->DriverUnload;
      if ( !Registration->FilterUnloadCallback || (Registration->Flags & 1) != 0 )
      {
        v30 = 0;
        *((_QWORD *)DriverObject + 13) = 0;
      }
      else
      {
        v30 = FltpMiniFilterDriverUnload;
      }
      v32 = *(_QWORD *)(v13 + 440);
      v31 = _InterlockedCompareExchange64((volatile signed __int64 *)&Driver->DriverUnload, (signed __int64)v30, v32);
      if ( v32 != v31 )
      {
        do
        {
          *(_QWORD *)(v13 + 440) = v31;
          v31 = _InterlockedCompareExchange64(
                  (volatile signed __int64 *)&Driver->DriverUnload,
                  (signed __int64)v30,
                  v31);
        }
        while ( v31 != *(_QWORD *)(v13 + 440) );
      }
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 0x20) != 0 )
        McTemplateU0sww_EtwWriteTransfer(
          *(unsigned __int16 *)(v13 + 80) >> 1,
          (unsigned int)RegSup_c572,
          (unsigned int)"FltRegisterFilter",
          *(unsigned __int16 *)(v13 + 64) >> 1,
          *(_QWORD *)(v13 + 72),
          *(_WORD *)(v13 + 80) >> 1,
          *(_QWORD *)(v13 + 88));
      if ( (unsigned int)dword_18003E018 > 5 )
      {
        v38 = 0;
        LowLimit = 0;
        IoGetStackLimits(&LowLimit, &v38);
        if ( (unsigned __int64)&v38 - LowLimit >= 0x200 )
        {
          UniqueIdentifierForObject = FltpGetUniqueIdentifierForObject(v13);
          if ( (int)FltpDbgStatus(UniqueIdentifierForObject, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 580, 0) >= 0 )
          {
LABEL_86:
            *RetFilter = (PFLT_FILTER)v13;
            goto LABEL_87;
          }
        }
        else
        {
          _InterlockedIncrement(&dword_180040530);
        }
      }
      _InterlockedIncrement(&dword_180040534);
      goto LABEL_86;
    }
    *v16 |= 4u;
    goto LABEL_41;
  }
  FltpLogEventWithObjectID(&FLTMGR_REGISTER_FILTER_FAILED, 0);
  if ( (unsigned int)dword_18003E018 > 5 )
  {
    HighLimit = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit >= 0x200 )
      FltpTelemetryFilterRegistration(3221225626LL, 0, 0, Driver);
    else
      _InterlockedAdd(&dword_180040530, 1u);
  }
  return -1073741670;
}

```

## disassembly

```asm
0x18004c810  mov     [rsp+arg_0], rbx
0x18004c815  mov     [rsp+arg_8], rsi
0x18004c81a  push    rdi
0x18004c81b  push    r12
0x18004c81d  push    r13
0x18004c81f  push    r14
0x18004c821  push    r15
0x18004c823  sub     rsp, 80h
0x18004c82a  xor     r12d, r12d
0x18004c82d  mov     r13, r8
0x18004c830  mov     [r8], r12
0x18004c833  mov     rsi, rdx
0x18004c836  mov     eax, cs:dword_18003ECD0
0x18004c83c  mov     r14, rcx
0x18004c83f  lea     ebx, [r12+1]
0x18004c844  test    bl, al
0x18004c846  jnz     short loc_18004C84F
0x18004c848  mov     eax, 0C01C0007h
0x18004c84d  jmp     short loc_18004C897
0x18004c84f  movzx   ecx, word ptr [rdx+2]
0x18004c853  mov     edx, 0FF00h
0x18004c858  movzx   eax, cx
0x18004c85b  and     ax, dx
0x18004c85e  mov     edx, 200h
0x18004c863  cmp     ax, dx
0x18004c866  jnz     short loc_18004C892
0x18004c868  mov     eax, 202h
0x18004c86d  mov     rdx, [rsi+40h]
0x18004c871  cmp     [rsi+48h], r12
0x18004c875  jnz     short loc_18004C887
0x18004c877  cmp     cx, ax
0x18004c87a  jb      short loc_18004C882
0x18004c87c  cmp     [rsi+60h], r12
0x18004c880  jnz     short loc_18004C887
0x18004c882  mov     al, r12b
0x18004c885  jmp     short loc_18004C889
0x18004c887  mov     al, bl
0x18004c889  test    rdx, rdx
0x18004c88c  jz      short loc_18004C8B5
0x18004c88e  test    al, al
0x18004c890  jnz     short loc_18004C8BF
0x18004c892  mov     eax, 0C000000Dh
0x18004c897  lea     r11, [rsp+0A8h+var_28]
0x18004c89f  mov     rbx, [r11+30h]
0x18004c8a3  mov     rsi, [r11+38h]
0x18004c8a7  mov     rsp, r11
0x18004c8aa  pop     r15
0x18004c8ac  pop     r14
0x18004c8ae  pop     r13
0x18004c8b0  pop     r12
0x18004c8b2  pop     rdi
0x18004c8b3  retn
0x18004c8b5  test    al, al
0x18004c8b7  jnz     short loc_18004C892
0x18004c8b9  cmp     [rsi+50h], r12
0x18004c8bd  jnz     short loc_18004C892
0x18004c8bf  mov     rax, [rsi+10h]
0x18004c8c3  mov     r15d, r12d
0x18004c8c6  test    rax, rax
0x18004c8c9  jz      short loc_18004C8D9
0x18004c8cb  jmp     short loc_18004C8D1
0x18004c8cd  lea     rax, [rax+20h]
0x18004c8d1  add     r15d, ebx
0x18004c8d4  cmp     byte ptr [rax], 80h
0x18004c8d7  jnz     short loc_18004C8CD
0x18004c8d9  mov     rax, [r14+30h]
0x18004c8dd  mov     ecx, 40h ; '@'
0x18004c8e2  mov     r8d, 6C664D46h
0x18004c8e8  movzx   edx, word ptr [rax+18h]
0x18004c8ec  mov     eax, r15d
0x18004c8ef  shl     eax, 5
0x18004c8f2  add     edx, eax
0x18004c8f4  add     rdx, 2C0h
0x18004c8fb  call    cs:__imp_ExAllocatePool2
0x18004c902  nop     dword ptr [rax+rax+00h]
0x18004c907  mov     rdi, rax
0x18004c90a  test    rax, rax
0x18004c90d  jnz     loc_18004C994
0x18004c913  mov     edi, 0C000009Ah
0x18004c918  mov     [rsp+0A8h+var_88], r12; __int64
0x18004c91d  mov     edx, edi
0x18004c91f  lea     rcx, FLTMGR_REGISTER_FILTER_FAILED; EventDescriptor
0x18004c926  xor     r9d, r9d
0x18004c929  mov     r8, r14
0x18004c92c  call    FltpLogEventWithObjectID
0x18004c931  cmp     cs:dword_18003E018, 5
0x18004c938  jbe     short loc_18004C98D
0x18004c93a  lea     rdx, [rsp+0A8h+HighLimit]; HighLimit
0x18004c93f  mov     [rsp+0A8h+HighLimit], r12
0x18004c944  lea     rcx, [rsp+0A8h+LowLimit]; LowLimit
0x18004c94c  mov     [rsp+0A8h+LowLimit], r12
0x18004c954  call    cs:__imp_IoGetStackLimits
0x18004c95b  nop     dword ptr [rax+rax+00h]
0x18004c960  lea     rax, [rsp+0A8h+HighLimit]
0x18004c965  sub     rax, [rsp+0A8h+LowLimit]
0x18004c96d  cmp     rax, 200h
0x18004c973  jnb     short loc_18004C97E
0x18004c975  lock add cs:dword_180040530, ebx
0x18004c97c  jmp     short loc_18004C98D
0x18004c97e  mov     r9, r14
0x18004c981  xor     r8d, r8d
0x18004c984  xor     edx, edx
0x18004c986  mov     ecx, edi
0x18004c988  call    FltpTelemetryFilterRegistration
0x18004c98d  mov     eax, edi
0x18004c98f  jmp     loc_18004C897
0x18004c994  mov     rax, [rsi+18h]
0x18004c998  mov     [rdi+108h], rax
0x18004c99f  mov     rax, [rsi+20h]
0x18004c9a3  mov     [rdi+110h], rax
0x18004c9aa  mov     rax, [rsi+28h]
0x18004c9ae  mov     [rdi+118h], rax
0x18004c9b5  mov     rax, [rsi+30h]
0x18004c9b9  mov     [rdi+120h], rax
0x18004c9c0  mov     rax, [rsi+38h]
0x18004c9c4  mov     [rdi+128h], rax
0x18004c9cb  mov     r8, [rsi+40h]
0x18004c9cf  mov     [rdi+180h], r8
0x18004c9d6  mov     r9, [rsi+48h]
0x18004c9da  mov     [rdi+188h], r9
0x18004c9e1  mov     rax, [rsi+50h]
0x18004c9e5  mov     [rdi+198h], rax
0x18004c9ec  mov     eax, 201h
0x18004c9f1  cmp     [rsi+2], ax
0x18004c9f5  jb      short loc_18004CA02
0x18004c9f7  mov     rax, [rsi+58h]
0x18004c9fb  mov     [rdi+1A0h], rax
0x18004ca02  mov     eax, 202h
0x18004ca07  cmp     [rsi+2], ax
0x18004ca0b  jb      short loc_18004CA18
0x18004ca0d  mov     rax, [rsi+60h]
0x18004ca11  mov     [rdi+190h], rax
0x18004ca18  mov     eax, 203h
0x18004ca1d  cmp     [rsi+2], ax
0x18004ca21  jb      short loc_18004CA2E
0x18004ca23  mov     rax, [rsi+68h]
0x18004ca27  mov     [rdi+1A8h], rax
0x18004ca2e  mov     eax, [rsi+4]
0x18004ca31  lea     rcx, [rdi+60h]
0x18004ca35  test    al, 2
0x18004ca37  jz      short loc_18004CA3C
0x18004ca39  or      dword ptr [rcx], 8
0x18004ca3c  mov     eax, [rsi+4]
0x18004ca3f  mov     rdx, rcx
0x18004ca42  test    al, 4
0x18004ca44  jz      short loc_18004CA4D
0x18004ca46  lea     rdx, [rdi+60h]
0x18004ca4a  or      dword ptr [rdx], 20h
0x18004ca4d  test    r8, r8
0x18004ca50  jnz     short loc_18004CA6B
0x18004ca52  test    r9, r9
0x18004ca55  jnz     short loc_18004CA6E
0x18004ca57  cmp     [rdi+190h], r12
0x18004ca5e  jnz     short loc_18004CA6E
0x18004ca60  cmp     [rdi+198h], r12
0x18004ca67  jz      short loc_18004CA71
0x18004ca69  jmp     short loc_18004CA6E
0x18004ca6b  mov     rcx, rdx
0x18004ca6e  or      dword ptr [rcx], 4
0x18004ca71  lea     rcx, [rdi+8]; RunRef
0x18004ca75  mov     dword ptr [rdi], 2000000h
0x18004ca7b  mov     [rdi+4], ebx
0x18004ca7e  call    cs:__imp_ExInitializeRundownProtection
0x18004ca85  nop     dword ptr [rax+rax+00h]
0x18004ca8a  mov     r8d, [rdi]
0x18004ca8d  bt      r8d, 19h
0x18004ca92  mov     [rdi+10h], r12
0x18004ca96  mov     edx, cs:FltGlobals
0x18004ca9c  setb    cl
0x18004ca9f  bt      edx, 0Dh
0x18004caa3  setb    al
0x18004caa6  test    al, cl
0x18004caa8  jnz     short loc_18004CAD5
0x18004caaa  bt      r8d, 1Ah
0x18004caaf  setb    cl
0x18004cab2  bt      edx, 0Eh
0x18004cab6  setb    al
0x18004cab9  test    al, cl
0x18004cabb  jnz     short loc_18004CAD5
0x18004cabd  bt      r8d, 18h
0x18004cac2  setb    cl
0x18004cac5  bt      edx, 0Fh
0x18004cac9  setb    al
0x18004cacc  test    al, cl
0x18004cace  jnz     short loc_18004CAD5
0x18004cad0  mov     rax, r12
0x18004cad3  jmp     short loc_18004CAF1
0x18004cad5  mov     edx, 20008h
0x18004cada  mov     ecx, 40h ; '@'
0x18004cadf  mov     r8d, 6C724D46h
0x18004cae5  call    cs:__imp_ExAllocatePool2
0x18004caec  nop     dword ptr [rax+rax+00h]
0x18004caf1  xorps   xmm0, xmm0
0x18004caf4  mov     [rdi+20h], rax
0x18004caf8  mov     rcx, rdi; FltObject
0x18004cafb  movups  xmmword ptr [rdi+28h], xmm0
0x18004caff  call    FltObjectReference
0x18004cb04  mov     [rdi+68h], r14
0x18004cb08  lea     rcx, [rdi+70h]
0x18004cb0c  mov     edx, 8
0x18004cb11  mov     [rdi+0E8h], r12d
0x18004cb18  call    cs:__imp_ExInitializeFastResource
0x18004cb1f  nop     dword ptr [rax+rax+00h]
0x18004cb24  lea     rax, [rdi+0D8h]
0x18004cb2b  xor     r8d, r8d; State
0x18004cb2e  mov     [rax+8], rax
0x18004cb32  lea     rcx, [rdi+1D8h]; Event
0x18004cb39  mov     [rax], rax
0x18004cb3c  mov     edx, ebx; Type
0x18004cb3e  mov     [rdi+208h], r12d
0x18004cb45  mov     [rdi+1C0h], ebx
0x18004cb4b  mov     [rdi+1C8h], r12
0x18004cb52  mov     [rdi+1D0h], r12d
0x18004cb59  call    cs:__imp_KeInitializeEvent
0x18004cb60  nop     dword ptr [rax+rax+00h]
0x18004cb65  lea     rax, [rdi+1F8h]
0x18004cb6c  xor     r8d, r8d; State
0x18004cb6f  mov     [rax+8], rax
0x18004cb73  lea     rcx, [rdi+228h]; Event
0x18004cb7a  mov     [rax], rax
0x18004cb7d  mov     edx, ebx; Type
0x18004cb7f  mov     [rdi+258h], r12d
0x18004cb86  mov     [rdi+210h], ebx
0x18004cb8c  mov     [rdi+218h], r12
0x18004cb93  mov     [rdi+220h], r12d
0x18004cb9a  call    cs:__imp_KeInitializeEvent
0x18004cba1  nop     dword ptr [rax+rax+00h]
0x18004cba6  lea     rax, [rdi+248h]
0x18004cbad  xor     r8d, r8d; State
0x18004cbb0  mov     [rax+8], rax
0x18004cbb4  lea     rcx, [rdi+278h]; Event
0x18004cbbb  mov     [rax], rax
0x18004cbbe  mov     edx, ebx; Type
0x18004cbc0  mov     [rdi+2A8h], r12d
0x18004cbc7  mov     [rdi+260h], ebx
0x18004cbcd  mov     [rdi+268h], r12
0x18004cbd4  mov     [rdi+270h], r12d
0x18004cbdb  call    cs:__imp_KeInitializeEvent
0x18004cbe2  nop     dword ptr [rax+rax+00h]
0x18004cbe7  lea     rax, [rdi+298h]
0x18004cbee  mov     edx, ebx
0x18004cbf0  lea     rcx, [rdi+2B0h]
0x18004cbf7  mov     [rax+8], rax
0x18004cbfb  mov     [rax], rax
0x18004cbfe  call    cs:__imp_ExInitializeAutoExpandPushLock
0x18004cc05  nop     dword ptr [rax+rax+00h]
0x18004cc0a  mov     rdx, [rsi+8]
0x18004cc0e  test    rdx, rdx
0x18004cc11  jz      short loc_18004CC3C
0x18004cc13  mov     rcx, rdi
0x18004cc16  call    FltpProcessContextRegistration
0x18004cc1b  mov     r8d, 145h
0x18004cc21  lea     rdx, aMinkernelFsFil_16; "minkernel\\fs\\filtermgr\\filter\\regsu"...
0x18004cc28  xor     r9d, r9d
0x18004cc2b  mov     ecx, eax
0x18004cc2d  mov     ebx, eax
0x18004cc2f  call    FltpDbgStatus
0x18004cc34  test    eax, eax
0x18004cc36  js      loc_18004CF8A
0x18004cc3c  lea     rax, [rdi+2C0h]
0x18004cc43  cmp     [rsi+10h], r12
0x18004cc47  jz      loc_18004CD14
0x18004cc4d  mov     [rdi+1B0h], rax
0x18004cc54  mov     bl, r12b
0x18004cc57  mov     rdx, [rsi+10h]; Src
0x18004cc5b  mov     rcx, rax; void *
0x18004cc5e  mov     r8d, r15d
0x18004cc61  shl     r8, 5; Size
0x18004cc65  lea     r12, [r8+rax]
0x18004cc69  call    memmove
0x18004cc6e  mov     r15, [rdi+1B0h]
0x18004cc75  mov     cl, [r15]
0x18004cc78  cmp     cl, 80h
0x18004cc7b  jz      loc_18004CD17
0x18004cc81  cmp     cl, 0EDh
0x18004cc84  jnz     short loc_18004CC9E
0x18004cc86  mov     rax, [r15+8]
0x18004cc8a  mov     [rdi+170h], rax
0x18004cc91  mov     rax, [r15+10h]
0x18004cc95  mov     [rdi+178h], rax
0x18004cc9c  jmp     short loc_18004CD0B
0x18004cc9e  cmp     cl, 0ECh
0x18004cca1  jz      short loc_18004CD0B
0x18004cca3  cmp     cl, 10h
0x18004cca6  jnz     short loc_18004CCB2
0x18004cca8  mov     qword ptr [r15+10h], 0
0x18004ccb0  jmp     short loc_18004CD0B
0x18004ccb2  lea     eax, [rcx-3]
0x18004ccb5  cmp     al, 1
0x18004ccb7  jbe     short loc_18004CCBE
0x18004ccb9  cmp     cl, 0Dh
0x18004ccbc  jnz     short loc_18004CD0B
0x18004ccbe  test    bl, bl
0x18004ccc0  jnz     short loc_18004CCFD
0x18004ccc2  mov     edx, 1
0x18004ccc7  mov     rcx, r14
0x18004ccca  call    cs:__imp_FsRtlSetDriverBacking
0x18004ccd1  nop     dword ptr [rax+rax+00h]
0x18004ccd6  mov     r8d, 190h
0x18004ccdc  lea     rdx, aMinkernelFsFil_16; "minkernel\\fs\\filtermgr\\filter\\regsu"...
  ... truncated ...
```
