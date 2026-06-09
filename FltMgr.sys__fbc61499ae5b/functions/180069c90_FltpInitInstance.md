# FltpInitInstance

- ea: `0x180069c90`
- end: `0x18006a84f`
- name: `FltpInitInstance`
- size: `3007`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, PVOID@<rdx>, PCUNICODE_STRING SourceString, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800698d0`
- `0x180074810`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x180014950`
- `0x180019950`
- `0x180019be0`
- `0x18001ac40`
- `0x18001c2c0`
- `0x18001ce00`
- `0x18001eb10`
- `0x180020300`
- `0x1800248e0`
- `0x180024c40`
- `0x180063b40`
- `0x180063fa0`
- `0x180067030`
- `0x180069c90`
- `0x18006aad0`
- `0x18006acb0`
- `0x18006ae70`
- `0x18006aef0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18006a6f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006a72b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006a6f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006a72b`
- `ntoskrnl!ExAllocatePool2` at `0x180069eaf`
- `ntoskrnl!ExAllocatePool2` at `0x18006a500`
- `ntoskrnl!ExAllocatePool2` at `0x180069eaf`
- `ntoskrnl!ExAllocatePool2` at `0x18006a500`
- `ntoskrnl!ObfDereferenceObject` at `0x18006a7eb`
- `ntoskrnl!ObfDereferenceObject` at `0x18006a7eb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180069fdb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006a011`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180069fdb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006a011`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18007a7d5`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18007a7d5`
- `ntoskrnl!IoGetStackLimits` at `0x18006a229`
- `ntoskrnl!IoGetStackLimits` at `0x18006a5f5`
- `ntoskrnl!IoGetStackLimits` at `0x18006a229`
- `ntoskrnl!IoGetStackLimits` at `0x18006a5f5`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180069ccb`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180069ccb`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180069d5c`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180069d5c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180069d41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006a09a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006a31b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006a340`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180069d41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006a09a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006a31b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006a340`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180069dbe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a10a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a3c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a3e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a839`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180069dbe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a10a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a3c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a3e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a839`
- `ntoskrnl!ExReleaseFastResource` at `0x180069db2`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a0fe`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a3b7`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a3d9`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a82d`
- `ntoskrnl!ExReleaseFastResource` at `0x180069db2`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a0fe`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a3b7`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a3d9`
- `ntoskrnl!ExReleaseFastResource` at `0x18006a82d`
- `ntoskrnl!RtlCompareAltitudes` at `0x180069d73`
- `ntoskrnl!RtlCompareAltitudes` at `0x180069d92`
- `ntoskrnl!RtlCompareAltitudes` at `0x180069d73`
- `ntoskrnl!RtlCompareAltitudes` at `0x180069d92`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x180069fa0`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x180069fa0`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006a0af`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006a334`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006a355`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006a0af`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006a334`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18006a355`
- `ntoskrnl!ExInitializeRundownProtection` at `0x180069ed8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x180069ed8`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x180069f47`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x180069f47`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x18006a717`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x18006a717`

## pseudocode

```c
__int64 __fastcall FltpInitInstance(
        char *FltObject,
        char *a2,
        unsigned int a3,
        const UNICODE_STRING *a4,
        PCUNICODE_STRING SourceString,
        __int64 *a6)
{
  _DWORD *v7; // r14
  unsigned int Length; // eax
  char v11; // r10
  __int64 v12; // r8
  wchar_t v13; // dx
  __int64 v14; // r8
  int v15; // eax
  int v16; // r9d
  char *v17; // rdx
  unsigned int v18; // r8d
  char i; // al
  __int64 v20; // rsi
  __int64 Pool2; // rax
  __int64 v22; // rbx
  int v23; // r8d
  __int64 v24; // rax
  _QWORD *v25; // r12
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  __int64 CompletionNodeTracking; // rdi
  unsigned __int16 v28; // ax
  __int64 v29; // rdi
  __int64 v30; // r14
  const UNICODE_STRING *v31; // rdx
  UNICODE_STRING *v32; // rcx
  unsigned __int16 v33; // ax
  __int64 v34; // r8
  PVOID *v35; // rdx
  void (__fastcall *v36)(PVOID, __int64, char *); // r12
  __int64 v37; // rcx
  int SupportedFeaturesValue; // eax
  char IsVolumeDetached; // al
  int v40; // ecx
  int v41; // edx
  unsigned int v42; // ecx
  PVOID v43; // rsi
  _DWORD *v44; // rsi
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  unsigned int CountersSamplingRate; // eax
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r8
  int v56; // r8d
  int v57; // ecx
  struct _DEVICE_OBJECT *v58; // rcx
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rax
  PFAST_IO_DISPATCH FastIoDispatch; // r8
  void (__fastcall *FastIoCheckIfPossible)(PDEVICE_OBJECT, __int64, char *); // r9
  signed __int32 v62[8]; // [rsp+0h] [rbp-F8h] BYREF
  __int64 v63; // [rsp+20h] [rbp-D8h]
  __int64 v64; // [rsp+28h] [rbp-D0h]
  __int64 v65; // [rsp+30h] [rbp-C8h]
  PVOID Object; // [rsp+50h] [rbp-A8h]
  unsigned __int64 v67; // [rsp+58h] [rbp-A0h] BYREF
  unsigned __int64 HighLimit[2]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v69[80]; // [rsp+70h] [rbp-88h] BYREF
  unsigned int v71; // [rsp+110h] [rbp+18h]
  unsigned __int64 LowLimit; // [rsp+118h] [rbp+20h] BYREF

  v71 = a3;
  v7 = a2;
  memset(v69, 0, 0x48u);
  ExInitializeFastOwnerEntry(v69);
  Length = a4->Length;
  if ( !(_WORD)Length )
    return 3221225485LL;
  v11 = 0;
  v12 = 0;
  while ( (unsigned int)v12 < Length >> 1 )
  {
    v13 = a4->Buffer[v12];
    if ( v13 == 46 )
    {
      if ( v11 )
        return 3221225485LL;
      v11 = 1;
      v12 = (unsigned int)(v12 + 1);
    }
    else
    {
      if ( (unsigned __int16)(v13 - 48) > 9u )
        return 3221225485LL;
      v12 = (unsigned int)(v12 + 1);
    }
  }
  LODWORD(LowLimit) = -1;
  KeEnterCriticalRegion();
  LOBYTE(v14) = 1;
  ExAcquireFastResourceShared(qword_18003ED18, v69, v14);
  if ( RtlCompareAltitudes(a4, (PCUNICODE_STRING)(*((_QWORD *)FltObject + 7) + 32LL)) < 0
    || RtlCompareAltitudes(a4, (PCUNICODE_STRING)(*((_QWORD *)FltObject + 7) + 48LL)) > 0 )
  {
    v22 = 0;
    ExReleaseFastResource(qword_18003ED18, v69);
    KeLeaveCriticalRegion();
    LODWORD(CompletionNodeTracking) = -1073741637;
    goto LABEL_56;
  }
  ExReleaseFastResource(qword_18003ED18, v69);
  KeLeaveCriticalRegion();
  v15 = v7[15];
  Object = v7 + 15;
  if ( (v15 == 25 || v15 == 26) && (*((_DWORD *)FltObject + 24) & 8) == 0
    || (v7[14] & 0x800) != 0 && (*((_DWORD *)FltObject + 24) & 0x20) == 0 )
  {
    return 3221225659LL;
  }
  if ( (v7[14] & 0x3000) != 0x3000 || (unsigned int)FltiAttachPolicyIsFilterAllowed(v7 + 542, FltObject + 64, a4) )
  {
    if ( SourceString )
      v16 = a4->Length + SourceString->Length;
    else
      v16 = a4->Length;
    v17 = (char *)*((_QWORD *)FltObject + 54);
    v18 = 0;
    if ( v17 )
    {
      for ( i = *v17; i != (char)0x80; v17 += 32 )
      {
        if ( (unsigned __int8)(i + 20) > 1u
          && (*((_QWORD *)v17 + 1) || *((_QWORD *)v17 + 2))
          && (unsigned __int8)(i + 22) < 0x32u )
        {
          ++v18;
        }
        i = v17[32];
      }
    }
    v20 = v18 + 1;
    if ( !*((_QWORD *)FltObject + 48) )
      v20 = v18;
    if ( *((_QWORD *)FltObject + 50) || *((_QWORD *)FltObject + 49) )
      v20 = (unsigned int)(v20 + 1);
    Pool2 = ExAllocatePool2(64, (unsigned int)(v16 + 48 * v20) + 960LL, 1936280902);
    v22 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = 0x1000000;
      *(_DWORD *)(Pool2 + 4) = 1;
      ExInitializeRundownProtection((PEX_RUNDOWN_REF)(Pool2 + 8));
      v23 = *(_DWORD *)v22;
      *(_QWORD *)(v22 + 16) = 0;
      if ( (v23 & 0x2000000) != 0 && (FltGlobals[0] & 0x2000) != 0
        || (FltGlobals[0] & 0x4000) != 0 && (v23 & 0x4000000) != 0
        || (FltGlobals[0] & 0x8000) != 0 && (v23 & 0x1000000) != 0 )
      {
        v24 = ExAllocatePool2(64, 131080, 1819430214);
      }
      else
      {
        v24 = 0;
      }
      *(_QWORD *)(v22 + 32) = v24;
      v25 = (_QWORD *)(v22 + 120);
      *(_OWORD *)(v22 + 40) = 0;
      *(_QWORD *)(v22 + 120) = 0;
      *(_DWORD *)(v22 + 80) |= 4u;
      CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x72724D46u);
      *(_QWORD *)(v22 + 56) = CacheAwareRundownProtection;
      if ( CacheAwareRundownProtection )
      {
        FltObjectReference((PVOID)v22);
        LODWORD(CompletionNodeTracking) = FltObjectReference(v7);
        if ( (int)CompletionNodeTracking >= 0 )
        {
          *(_QWORD *)(v22 + 64) = v7;
          LODWORD(CompletionNodeTracking) = FltObjectReference(FltObject);
          if ( (int)CompletionNodeTracking >= 0 )
          {
            *(_QWORD *)(v22 + 72) = FltObject;
            ExInitializeAutoExpandPushLock(v22 + 136, 1);
            v28 = a4->Length;
            *(_OWORD *)(v22 + 88) = 0;
            *(_WORD *)(v22 + 90) = v28;
            v29 = v22 + 48 * v20 + 960;
            *(_QWORD *)(v22 + 96) = v29;
            v30 = a4->Length;
            RtlCopyUnicodeString((PUNICODE_STRING)(v22 + 88), a4);
            v31 = SourceString;
            v32 = (UNICODE_STRING *)(v22 + 104);
            if ( SourceString )
            {
              v33 = SourceString->Length;
              *v32 = 0;
              *(_WORD *)(v22 + 106) = v33;
              *(_QWORD *)(v22 + 112) = v29 + v30;
              RtlCopyUnicodeString(v32, v31);
            }
            else
            {
              *v32 = 0;
            }
            CompletionNodeTracking = (unsigned int)FltpAllocateCompletionNodeTracking(v22 + 296);
            v7 = a2;
            if ( (int)FltpDbgStatus(CompletionNodeTracking, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 380, 0) < 0 )
            {
              v44 = Object;
              goto LABEL_57;
            }
            v65 = 0;
            LODWORD(v64) = -1071906799;
            LODWORD(v63) = -1071906798;
            CompletionNodeTracking = (unsigned int)FltpInsertVolumeInstance(a2, v22);
            if ( (int)FltpDbgStatus(
                        CompletionNodeTracking,
                        "minkernel\\fs\\filtermgr\\filter\\instancesup.c",
                        399,
                        3223060491LL) >= 0 )
            {
              KeEnterCriticalRegion();
              LOBYTE(v34) = 1;
              ExAcquireFastResourceExclusive(FltObject + 112, 0, v34);
              if ( (*(_DWORD *)FltObject & 1) != 0 )
              {
                LODWORD(CompletionNodeTracking) = -1071906805;
              }
              else
              {
                _InterlockedIncrement((volatile signed __int32 *)FltObject + 58);
                v35 = (PVOID *)*((_QWORD *)FltObject + 28);
                if ( *v35 != FltObject + 216 )
                  __fastfail(3u);
                *v25 = FltObject + 216;
                *(_QWORD *)(v22 + 128) = v35;
                *v35 = v25;
                *((_QWORD *)FltObject + 28) = v25;
              }
              ExReleaseFastResource(FltObject + 112, 0);
              KeLeaveCriticalRegion();
              v36 = 0;
              v63 = 0;
              if ( (int)FltpDbgStatus(
                          (unsigned int)CompletionNodeTracking,
                          "minkernel\\fs\\filtermgr\\filter\\instancesup.c",
                          427,
                          3223060491LL) >= 0 )
              {
                v37 = *((_QWORD *)FltObject + 13);
                Object = 0;
                SupportedFeaturesValue = FltpGetSupportedFeaturesValue(v37, a4, FltObject);
                *(_DWORD *)(v22 + 704) = SupportedFeaturesValue;
                if ( (SupportedFeaturesValue & 8) == 0 )
                {
                  v57 = *(_DWORD *)(*((_QWORD *)a2 + 8) + 72LL);
                  if ( (v57 == 8 || v57 == 3) && (v71 & 4) == 0 && (*((_DWORD *)FltObject + 24) & 0x80u) != 0 )
                  {
                    v58 = *(struct _DEVICE_OBJECT **)(*((_QWORD *)a2 + 11) + 64LL);
                    if ( v58 )
                    {
                      DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(v58);
                      Object = DeviceAttachmentBaseRef;
                      FastIoDispatch = DeviceAttachmentBaseRef->DriverObject->FastIoDispatch;
                      if ( FastIoDispatch )
                      {
                        if ( FastIoDispatch->SizeOfFastIoDispatch >= 0xF0 )
                        {
                          FastIoCheckIfPossible = (void (__fastcall *)(PDEVICE_OBJECT, __int64, char *))FastIoDispatch[1].FastIoCheckIfPossible;
                          if ( FastIoCheckIfPossible )
                          {
                            v36 = (void (__fastcall *)(PVOID, __int64, char *))FastIoDispatch[1].FastIoCheckIfPossible;
                            FastIoCheckIfPossible(DeviceAttachmentBaseRef, 1, FltObject + 64);
                            FltpLogEventBypassIoNotSupported(FltObject, *(unsigned int *)(v22 + 704));
                          }
                        }
                      }
                    }
                  }
                }
                IsVolumeDetached = FltpIsVolumeDetached(a2);
                v40 = v71 | 8;
                if ( !IsVolumeDetached )
                  v40 = v71;
                v41 = v40 | 0x10;
                if ( (*((_DWORD *)a2 + 14) & 0x1000) == 0 )
                  v41 = v40;
                v42 = v41 | 0x20;
                if ( (*((_DWORD *)a2 + 14) & 0x2000) == 0 )
                  v42 = v41;
                v71 = v42;
                LODWORD(CompletionNodeTracking) = FltpDoInstanceSetupNotification(v22, v42);
                if ( (int)CompletionNodeTracking < 0 )
                {
                  v43 = Object;
                  if ( v36 )
                    v36(Object, 2, FltObject + 64);
                  v7 = a2;
                  if ( (_DWORD)CompletionNodeTracking != -1071906801 )
                    FltpLogEventWithObjectID(&FLTMGR_FILTER_FAILED_INSTANCE_SETUP, 0);
                  goto LABEL_54;
                }
                IoPerfInitializeEntityData((struct _IO_PERF_ENTITY_DATA *)(v22 + 768));
                *(_BYTE *)(v22 + 768) = FltpQueryCountersEnabled(v47, v46, v48);
                CountersSamplingRate = FltpQueryCountersSamplingRate(v50, v49, v51);
                FltpIoPerfEnableSampling(v22, CountersSamplingRate);
                LODWORD(LowLimit) = 16;
                if ( (*((_DWORD *)a2 + 14) & 0x40) == 0 )
                  _InterlockedOr((volatile signed __int32 *)a2 + 14, 0x40u);
                v53 = *((_QWORD *)a2 + 11);
                if ( (*(_DWORD *)(v53 + 56) & 0x400) != 0 )
                  _InterlockedAnd((volatile signed __int32 *)(v53 + 56), 0xFFFFFBFF);
                if ( (_DWORD)v20
                  && (v64 = 0,
                      LODWORD(v63) = -1071906805,
                      CompletionNodeTracking = (unsigned int)FltpSetCallbacksForInstance(
                                                               v22,
                                                               v22 + 960,
                                                               (unsigned int)v20),
                      (int)FltpDbgStatus(
                             CompletionNodeTracking,
                             "minkernel\\fs\\filtermgr\\filter\\instancesup.c",
                             592,
                             3223060493LL) < 0) )
                {
                  v7 = a2;
                }
                else
                {
                  KeEnterCriticalRegion();
                  LOBYTE(v54) = 1;
                  ExAcquireFastResourceExclusive(a2 + 192, 0, v54);
                  KeEnterCriticalRegion();
                  LOBYTE(v55) = 1;
                  ExAcquireFastResourceExclusive(FltObject + 112, 0, v55);
                  if ( (*(_DWORD *)a2 & 1) != 0 )
                  {
                    LODWORD(CompletionNodeTracking) = -1071906805;
                    LODWORD(LowLimit) = 8;
                  }
                  else if ( (*(_DWORD *)FltObject & 1) != 0 )
                  {
                    LODWORD(CompletionNodeTracking) = -1071906805;
                    LODWORD(LowLimit) = 4;
                  }
                  else
                  {
                    if ( (*(_DWORD *)(*((_QWORD *)a2 + 13) + 972LL) & 1) != 0
                      && (unsigned int)*(unsigned __int8 *)(*((_QWORD *)a2 + 13) + 64LL) < *((_DWORD *)a2 + 78) )
                    {
                      ++*(_BYTE *)(*((_QWORD *)a2 + 13) + 64LL);
                    }
                    _InterlockedOr(v62, 0);
                    if ( (*(_DWORD *)(v22 + 80) & 4) != 0 )
                      _InterlockedAnd((volatile signed __int32 *)(v22 + 80), 0xFFFFFFFB);
                  }
                  ExReleaseFastResource(FltObject + 112, 0);
                  KeLeaveCriticalRegion();
                  ExReleaseFastResource(a2 + 192, 0);
                  KeLeaveCriticalRegion();
                  v63 = 0;
                  v7 = a2;
                  if ( (int)FltpDbgStatus(
                              (unsigned int)CompletionNodeTracking,
                              "minkernel\\fs\\filtermgr\\filter\\instancesup.c",
                              668,
                              3223060491LL) < 0 )
                  {
                    if ( (byte_180040A42 & 0x20) != 0 )
                      McTemplateU0spwppw_EtwWriteTransfer(
                        *((unsigned __int16 *)a2 + 56) >> 1,
                        (unsigned int)InstanceSup_c670,
                        v56,
                        (_DWORD)FltObject,
                        *((_WORD *)FltObject + 32) >> 1,
                        *((_QWORD *)FltObject + 9),
                        v22,
                        (char)a2,
                        *((_WORD *)a2 + 56) >> 1,
                        *((_QWORD *)a2 + 15));
                  }
                  else
                  {
                    if ( (byte_180040A42 & 0x20) != 0 )
                      McTemplateU0spwppw_EtwWriteTransfer(
                        *((unsigned __int16 *)a2 + 56) >> 1,
                        (unsigned int)InstanceSup_c687,
                        v56,
                        (_DWORD)FltObject,
                        *((_WORD *)FltObject + 32) >> 1,
                        *((_QWORD *)FltObject + 9),
                        v22,
                        (char)a2,
                        *((_WORD *)a2 + 56) >> 1,
                        *((_QWORD *)a2 + 15));
                    if ( !a6 )
                    {
                      FltObjectDereference((PVOID)v22);
                      v43 = Object;
LABEL_54:
                      if ( v43 )
                        ObfDereferenceObject(v43);
                      goto LABEL_56;
                    }
                    *a6 = v22;
                  }
                }
                v43 = Object;
                goto LABEL_54;
              }
              v44 = Object;
              v7 = a2;
LABEL_57:
              if ( (unsigned int)dword_18003E018 <= 5 )
                goto LABEL_60;
              HighLimit[0] = 0;
              LowLimit = 0;
              IoGetStackLimits(&LowLimit, HighLimit);
              if ( (unsigned __int64)HighLimit - LowLimit < 0x200 )
              {
                _InterlockedIncrement(&dword_180040530);
                goto LABEL_60;
              }
              if ( *v44 != 1 )
              {
                if ( (int)FltpDbgStatus(
                            (unsigned int)CompletionNodeTracking,
                            "minkernel\\fs\\filtermgr\\filter\\instancesup.c",
                            738,
                            0) < 0 )
                {
                  if ( (int)FltpDbgStatus(
                              (unsigned int)CompletionNodeTracking,
                              "minkernel\\fs\\filtermgr\\filter\\instancesup.c",
                              738,
                              0) >= 0 )
                    goto LABEL_60;
                  if ( (_DWORD)CompletionNodeTracking == -1071906805 )
                    goto LABEL_93;
                }
                LODWORD(v63) = CompletionNodeTracking;
                ((void (__fastcall *)(char *, _DWORD *, const UNICODE_STRING *, _QWORD, __int64, __int64, __int64))FltpLogInitInstanceFunction)(
                  FltObject,
                  v7,
                  a4,
                  v71,
                  v63,
                  v64,
                  v65);
              }
LABEL_60:
              if ( (int)CompletionNodeTracking >= 0 )
                return (unsigned int)CompletionNodeTracking;
LABEL_93:
              if ( v22 )
                FltpFreeInstance((PVOID)v22);
              return (unsigned int)CompletionNodeTracking;
            }
LABEL_56:
            v44 = v7 + 15;
            goto LABEL_57;
          }
          FltObjectDereference(v7);
        }
        ExFreeCacheAwareRundownProtection(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v22 + 56));
        ExFreePoolWithTag((PVOID)v22, 0x73694D46u);
        return (unsigned int)CompletionNodeTracking;
      }
      ExFreePoolWithTag((PVOID)v22, 0x73694D46u);
    }
    return 3221225626LL;
  }
  if ( (unsigned int)dword_18003E018 > 5 )
  {
    v67 = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &v67);
    if ( (unsigned __int64)&HighLimit[-1] - LowLimit < 0x200 )
    {
      _InterlockedIncrement(&dword_180040530);
    }
    else if ( v7[15] != 1
           && ((int)FltpDbgStatus(3221226719LL, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 200, 0) >= 0
            || (int)FltpDbgStatus(3221226719LL, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 200, 0) < 0) )
    {
      ((void (__fastcall *)(char *, _DWORD *, const UNICODE_STRING *, _QWORD, int))FltpLogInitInstanceFunction)(
        FltObject,
        v7,
        a4,
        a3,
        -1073740577);
    }
  }
  return 3221226719LL;
}

```

## disassembly

```asm
0x180069c90  mov     [rsp+arg_10], r8d
0x180069c95  mov     [rsp+arg_8], rdx
0x180069c9a  push    rdi
0x180069c9b  push    r13
0x180069c9d  push    r14
0x180069c9f  push    r15
0x180069ca1  sub     rsp, 0D8h
0x180069ca8  mov     edi, r8d
0x180069cab  mov     r14, rdx
0x180069cae  mov     r13, rcx
0x180069cb1  xor     edx, edx; Val
0x180069cb3  mov     r8d, 48h ; 'H'; Size
0x180069cb9  lea     rcx, [rsp+0F8h+var_88]; void *
0x180069cbe  mov     r15, r9
0x180069cc1  call    memset
0x180069cc6  lea     rcx, [rsp+0F8h+var_88]
0x180069ccb  call    cs:__imp_ExInitializeFastOwnerEntry
0x180069cd2  nop     dword ptr [rax+rax+00h]
0x180069cd7  movzx   eax, word ptr [r15]
0x180069cdb  test    ax, ax
0x180069cde  jz      loc_18006A548
0x180069ce4  xor     r10b, r10b
0x180069ce7  xor     r8d, r8d
0x180069cea  mov     r9d, eax
0x180069ced  shr     r9d, 1
0x180069cf0  cmp     r8d, r9d
0x180069cf3  jnb     short loc_180069D1B
0x180069cf5  mov     rax, [r15+8]
0x180069cf9  movzx   edx, word ptr [rax+r8*2]
0x180069cfe  cmp     dx, 2Eh ; '.'
0x180069d02  jz      loc_18006A523
0x180069d08  sub     dx, 30h ; '0'
0x180069d0c  cmp     dx, 9
0x180069d10  ja      loc_18006A548
0x180069d16  inc     r8d
0x180069d19  jmp     short loc_180069CF0
0x180069d1b  mov     [rsp+0F8h+var_28], rbx
0x180069d23  mov     [rsp+0F8h+var_30], rsi
0x180069d2b  mov     [rsp+0F8h+var_38], r12
0x180069d33  mov     r12d, 0FFFFFFFFh
0x180069d39  mov     dword ptr [rsp+0F8h+LowLimit], r12d
0x180069d41  call    cs:__imp_KeEnterCriticalRegion
0x180069d48  nop     dword ptr [rax+rax+00h]
0x180069d4d  mov     r8b, 1
0x180069d50  lea     rdx, [rsp+0F8h+var_88]
0x180069d55  lea     rcx, qword_18003ED18
0x180069d5c  call    cs:__imp_ExAcquireFastResourceShared
0x180069d63  nop     dword ptr [rax+rax+00h]
0x180069d68  mov     rdx, [r13+38h]
0x180069d6c  mov     rcx, r15; Altitude1
0x180069d6f  add     rdx, 20h ; ' '; Altitude2
0x180069d73  call    cs:__imp_RtlCompareAltitudes
0x180069d7a  nop     dword ptr [rax+rax+00h]
0x180069d7f  test    eax, eax
0x180069d81  js      loc_18006A81F
0x180069d87  mov     rdx, [r13+38h]
0x180069d8b  mov     rcx, r15; Altitude1
0x180069d8e  add     rdx, 30h ; '0'; Altitude2
0x180069d92  call    cs:__imp_RtlCompareAltitudes
0x180069d99  nop     dword ptr [rax+rax+00h]
0x180069d9e  test    eax, eax
0x180069da0  jg      loc_18006A81F
0x180069da6  lea     rdx, [rsp+0F8h+var_88]
0x180069dab  lea     rcx, qword_18003ED18
0x180069db2  call    cs:__imp_ExReleaseFastResource
0x180069db9  nop     dword ptr [rax+rax+00h]
0x180069dbe  call    cs:__imp_KeLeaveCriticalRegion
0x180069dc5  nop     dword ptr [rax+rax+00h]
0x180069dca  mov     eax, [r14+3Ch]
0x180069dce  lea     rbx, [r14+3Ch]
0x180069dd2  mov     [rsp+0F8h+Object], rbx
0x180069dd7  cmp     eax, 19h
0x180069dda  jnz     loc_18006A2A6
0x180069de0  mov     eax, [r13+60h]
0x180069de4  test    al, 8
0x180069de6  jz      loc_18006A691
0x180069dec  mov     eax, [r14+38h]
0x180069df0  bt      eax, 0Bh
0x180069df4  jb      loc_18006A685
0x180069dfa  mov     eax, [r14+38h]
0x180069dfe  and     eax, 3000h
0x180069e03  cmp     eax, 3000h
0x180069e08  jz      loc_18006A69B
0x180069e0e  mov     rcx, [rsp+0F8h+SourceString]
0x180069e16  movzx   eax, word ptr [r15]
0x180069e1a  test    rcx, rcx
0x180069e1d  jnz     loc_18006A6C4
0x180069e23  mov     r9d, eax
0x180069e26  mov     rdx, [r13+1B0h]
0x180069e2d  xor     r8d, r8d
0x180069e30  test    rdx, rdx
0x180069e33  jz      short loc_180069E68
0x180069e35  movzx   eax, byte ptr [rdx]
0x180069e38  cmp     al, 80h
0x180069e3a  jz      short loc_180069E68
0x180069e3c  nop     dword ptr [rax+00h]
0x180069e40  lea     ecx, [rax+14h]
0x180069e43  cmp     cl, 1
0x180069e46  jbe     short loc_180069E5C
0x180069e48  cmp     qword ptr [rdx+8], 0
0x180069e4d  jz      loc_18006A28F
0x180069e53  add     al, 16h
0x180069e55  cmp     al, 32h ; '2'
0x180069e57  jnb     short loc_180069E5C
0x180069e59  inc     r8d
0x180069e5c  movzx   eax, byte ptr [rdx+20h]
0x180069e60  add     rdx, 20h ; ' '
0x180069e64  cmp     al, 80h
0x180069e66  jnz     short loc_180069E40
0x180069e68  cmp     qword ptr [r13+180h], 0
0x180069e70  lea     esi, [r8+1]
0x180069e74  cmovz   esi, r8d
0x180069e78  cmp     qword ptr [r13+190h], 0
0x180069e80  jnz     loc_18006A29F
0x180069e86  cmp     qword ptr [r13+188h], 0
0x180069e8e  jnz     loc_18006A29F
0x180069e94  lea     edx, [rsi+rsi*2]
0x180069e97  mov     ecx, 40h ; '@'
0x180069e9c  shl     edx, 4
0x180069e9f  mov     r8d, 73694D46h
0x180069ea5  add     edx, r9d
0x180069ea8  add     rdx, 3C0h
0x180069eaf  call    cs:__imp_ExAllocatePool2
0x180069eb6  nop     dword ptr [rax+rax+00h]
0x180069ebb  mov     rbx, rax
0x180069ebe  test    rax, rax
0x180069ec1  jz      loc_18006A701
0x180069ec7  lea     rcx, [rax+8]; RunRef
0x180069ecb  mov     dword ptr [rax], 1000000h
0x180069ed1  mov     dword ptr [rax+4], 1
0x180069ed8  call    cs:__imp_ExInitializeRundownProtection
0x180069edf  nop     dword ptr [rax+rax+00h]
0x180069ee4  mov     r8d, [rbx]
0x180069ee7  xor     edi, edi
0x180069ee9  bt      r8d, 19h
0x180069eee  mov     [rbx+10h], rdi
0x180069ef2  mov     edx, cs:FltGlobals
0x180069ef8  setb    cl
0x180069efb  bt      edx, 0Dh
0x180069eff  setb    al
0x180069f02  test    al, cl
0x180069f04  jnz     loc_18006A4F0
0x180069f0a  bt      edx, 0Eh
0x180069f0e  jb      loc_18006A6D0
0x180069f14  bt      edx, 0Fh
0x180069f18  jb      loc_18006A6E0
0x180069f1e  mov     rax, rdi
0x180069f21  mov     [rbx+20h], rax
0x180069f25  lea     r12, [rbx+78h]
0x180069f29  xorps   xmm0, xmm0
0x180069f2c  mov     edx, 72724D46h; PoolTag
0x180069f31  movups  xmmword ptr [rbx+28h], xmm0
0x180069f35  mov     [r12], rdi
0x180069f39  mov     ecx, 200h; PoolType
0x180069f3e  mov     eax, [rbx+50h]
0x180069f41  or      eax, 4
0x180069f44  mov     [rbx+50h], eax
0x180069f47  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x180069f4e  nop     dword ptr [rax+rax+00h]
0x180069f53  mov     [rbx+38h], rax
0x180069f57  mov     rcx, rbx; P
0x180069f5a  test    rax, rax
0x180069f5d  jz      loc_18006A6F0
0x180069f63  call    FltObjectReference
0x180069f68  mov     rcx, r14; FltObject
0x180069f6b  call    FltObjectReference
0x180069f70  mov     edi, eax
0x180069f72  test    eax, eax
0x180069f74  js      loc_18006A713
0x180069f7a  mov     rcx, r13; FltObject
0x180069f7d  mov     [rbx+40h], r14
0x180069f81  call    FltObjectReference
0x180069f86  mov     edi, eax
0x180069f88  test    eax, eax
0x180069f8a  js      loc_18006A70B
0x180069f90  lea     rcx, [rbx+88h]
0x180069f97  mov     [rbx+48h], r13
0x180069f9b  mov     edx, 1
0x180069fa0  call    cs:__imp_ExInitializeAutoExpandPushLock
0x180069fa7  nop     dword ptr [rax+rax+00h]
0x180069fac  movzx   eax, word ptr [r15]
0x180069fb0  lea     rcx, [rbx+58h]; DestinationString
0x180069fb4  xorps   xmm0, xmm0
0x180069fb7  lea     rdi, [rsi+rsi*2]
0x180069fbb  movups  xmmword ptr [rcx], xmm0
0x180069fbe  shl     rdi, 4
0x180069fc2  mov     rdx, r15; SourceString
0x180069fc5  mov     [rcx+2], ax
0x180069fc9  add     rdi, 3C0h
0x180069fd0  add     rdi, rbx
0x180069fd3  mov     [rcx+8], rdi
0x180069fd7  movzx   r14d, word ptr [r15]
0x180069fdb  call    cs:__imp_RtlCopyUnicodeString
0x180069fe2  nop     dword ptr [rax+rax+00h]
0x180069fe7  mov     rdx, [rsp+0F8h+SourceString]; SourceString
0x180069fef  lea     rcx, [rbx+68h]; DestinationString
0x180069ff3  xorps   xmm0, xmm0
0x180069ff6  test    rdx, rdx
0x180069ff9  jz      loc_18006A287
0x180069fff  movzx   eax, word ptr [rdx]
0x18006a002  movups  xmmword ptr [rcx], xmm0
0x18006a005  mov     [rcx+2], ax
0x18006a009  lea     rax, [rdi+r14]
0x18006a00d  mov     [rcx+8], rax
0x18006a011  call    cs:__imp_RtlCopyUnicodeString
0x18006a018  nop     dword ptr [rax+rax+00h]
0x18006a01d  lea     rcx, [rbx+128h]
0x18006a024  call    FltpAllocateCompletionNodeTracking
0x18006a029  mov     r8d, 17Ch
0x18006a02f  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006a036  xor     r9d, r9d
0x18006a039  mov     ecx, eax
0x18006a03b  mov     edi, eax
0x18006a03d  call    FltpDbgStatus
0x18006a042  mov     r14, [rsp+0F8h+arg_8]
0x18006a04a  test    eax, eax
0x18006a04c  js      loc_18006A80F
0x18006a052  mov     rdx, rbx
0x18006a055  mov     rcx, r14
0x18006a058  call    FltpInsertVolumeInstance
0x18006a05d  mov     [rsp+0F8h+var_C8], 0
0x18006a066  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006a06d  mov     r8d, 18Fh
0x18006a073  mov     dword ptr [rsp+0F8h+var_D0], 0C01C0011h
0x18006a07b  mov     r9d, 0C01C000Bh
0x18006a081  mov     dword ptr [rsp+0F8h+var_D8], 0C01C0012h
0x18006a089  mov     ecx, eax
0x18006a08b  mov     edi, eax
0x18006a08d  call    FltpDbgStatus
0x18006a092  test    eax, eax
0x18006a094  js      loc_18006A804
0x18006a09a  call    cs:__imp_KeEnterCriticalRegion
0x18006a0a1  nop     dword ptr [rax+rax+00h]
0x18006a0a6  mov     r8b, 1
0x18006a0a9  lea     rcx, [r13+70h]
0x18006a0ad  xor     edx, edx
0x18006a0af  call    cs:__imp_ExAcquireFastResourceExclusive
0x18006a0b6  nop     dword ptr [rax+rax+00h]
0x18006a0bb  mov     eax, [r13+0]
0x18006a0bf  test    al, 1
0x18006a0c1  jnz     loc_18006A73C
0x18006a0c7  lock inc dword ptr [r13+0E8h]
0x18006a0cf  lea     rcx, [r13+0D8h]
0x18006a0d6  mov     rdx, [rcx+8]
0x18006a0da  mov     rax, [rdx]
0x18006a0dd  cmp     rax, rcx
0x18006a0e0  jnz     loc_18006A746
0x18006a0e6  mov     [r12], rcx
0x18006a0ea  mov     [rbx+80h], rdx
0x18006a0f1  mov     [rdx], r12
0x18006a0f4  mov     [rcx+8], r12
0x18006a0f8  xor     edx, edx
0x18006a0fa  lea     rcx, [r13+70h]
0x18006a0fe  call    cs:__imp_ExReleaseFastResource
0x18006a105  nop     dword ptr [rax+rax+00h]
0x18006a10a  call    cs:__imp_KeLeaveCriticalRegion
0x18006a111  nop     dword ptr [rax+rax+00h]
0x18006a116  xor     r12d, r12d
0x18006a119  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006a120  mov     r8d, 1ABh
0x18006a126  mov     [rsp+0F8h+var_D8], r12
0x18006a12b  mov     r9d, 0C01C000Bh
0x18006a131  mov     ecx, edi
0x18006a133  call    FltpDbgStatus
0x18006a138  test    eax, eax
0x18006a13a  js      loc_18006A4D8
0x18006a140  mov     rcx, [r13+68h]
0x18006a144  mov     r8, r13
0x18006a147  mov     rdx, r15
0x18006a14a  mov     [rsp+0F8h+Object], r12
0x18006a14f  call    FltpGetSupportedFeaturesValue
0x18006a154  mov     rdi, [rsp+0F8h+arg_8]
0x18006a15c  mov     [rbx+2C0h], eax
0x18006a162  test    al, 8
0x18006a164  jz      loc_18006A44F
0x18006a16a  mov     rcx, rdi
0x18006a16d  call    FltpIsVolumeDetached
0x18006a172  mov     ecx, [rsp+0F8h+arg_10]
0x18006a179  or      ecx, 8
0x18006a17c  test    al, al
0x18006a17e  mov     eax, [rdi+38h]
0x18006a181  cmovz   ecx, [rsp+0F8h+arg_10]
0x18006a189  mov     edx, ecx
0x18006a18b  or      edx, 10h
0x18006a18e  bt      eax, 0Ch
0x18006a192  mov     eax, [rdi+38h]
0x18006a195  cmovnb  edx, ecx
0x18006a198  mov     ecx, edx
0x18006a19a  or      ecx, 20h
0x18006a19d  bt      eax, 0Dh
0x18006a1a1  cmovnb  ecx, edx
0x18006a1a4  mov     [rsp+0F8h+arg_10], ecx
0x18006a1ab  mov     edx, ecx
0x18006a1ad  mov     rcx, rbx
0x18006a1b0  call    FltpDoInstanceSetupNotification
0x18006a1b5  mov     edi, eax
0x18006a1b7  test    eax, eax
0x18006a1b9  jns     loc_18006A2B4
0x18006a1bf  mov     rsi, [rsp+0F8h+Object]
0x18006a1c4  test    r12, r12
  ... truncated ...
```
