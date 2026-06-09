# MpScanBootSector

- ea: `0x140062588`
- end: `0x140063642`
- name: `MpScanBootSector`
- size: `4282`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `authz_impersonation`

## callers

- `0x140004800`
- `0x140030380`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x1400026c0`
- `0x140003950`
- `0x1400051bc`
- `0x140005944`
- `0x140005e78`
- `0x140009bf0`
- `0x14000a760`
- `0x14000a970`
- `0x14000ae58`
- `0x14000bbfc`
- `0x14000c02c`
- `0x14000c17c`
- `0x1400118d0`
- `0x140011900`
- `0x140030060`
- `0x14003a1b0`
- `0x140056b50`
- `0x140062588`
- `0x140063644`
- `0x1400638f8`
- `0x140063a18`
- `0x140064160`
- `0x14006436c`
- `0x14006442c`
- `0x14006cec4`
- `0x140072bfc`
- `0x140072dcc`
- `0x1400785cc`
- `0x14007b608`
- `0x14007cd90`
- `0x14007d048`

## import_xrefs

- `ntoskrnl!ObQueryNameString` at `0x14006274a`
- `ntoskrnl!ObQueryNameString` at `0x1400627c9`
- `ntoskrnl!ObQueryNameString` at `0x14006274a`
- `ntoskrnl!ObQueryNameString` at `0x1400627c9`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140062972`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140062972`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14006298a`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14006298a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062c85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400632da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006351d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ccfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062c85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400632da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006351d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ccfc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062c79`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400632ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062c79`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400632ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062c4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400632af`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062c4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400632af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400626d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062c35`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063299`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400626d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062c35`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063299`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400629c1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400629c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062764`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400634fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400635a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063631`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cc3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ccc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062764`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400634fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400635a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063631`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cc3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ccc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cce0`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140063581`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008cc80`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140063581`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008cc80`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140062940`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140062faf`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14006354f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140062940`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140062faf`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14006354f`
- `ntoskrnl!KeBugCheck` at `0x1400635bc`
- `ntoskrnl!KeBugCheck` at `0x14008cc98`
- `ntoskrnl!KeBugCheck` at `0x1400635bc`
- `ntoskrnl!KeBugCheck` at `0x14008cc98`
- `ntoskrnl!ObfDereferenceObject` at `0x1400629a9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400634c0`
- `ntoskrnl!ObfDereferenceObject` at `0x14008cc50`
- `ntoskrnl!ObfDereferenceObject` at `0x1400629a9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400634c0`
- `ntoskrnl!ObfDereferenceObject` at `0x14008cc50`
- `FLTMGR!FltSendMessage` at `0x140062b97`
- `FLTMGR!FltSendMessage` at `0x140062b97`
- `FLTMGR!FltGetDiskDeviceObject` at `0x1400626ae`
- `FLTMGR!FltGetDiskDeviceObject` at `0x1400626ae`

## pseudocode

```c
__int64 __fastcall MpScanBootSector(__int64 a1, __int64 a2, int a3, struct _KTHREAD *a4, struct _KTHREAD *a5)
{
  __int64 v7; // r15
  const void **v8; // r14
  struct _FLT_VOLUME *v9; // r12
  char IsProcessExemptByData; // al
  NTSTATUS v11; // ebx
  struct _KPROCESS *RequestorProcess; // rax
  ULONG DeviceType; // ecx
  struct _OBJECT_NAME_INFORMATION *PoolWithTag; // rax
  int v15; // r8d
  struct _OBJECT_NAME_INFORMATION *v16; // rax
  int v17; // r8d
  int v18; // edx
  int v19; // r8d
  char IsHotPluggable; // r12
  char v21; // cl
  int v22; // r8d
  int RawDevice; // eax
  __int64 v24; // rax
  HANDLE v25; // rax
  LONGLONG TimeQuadPart; // rbx
  __int64 v27; // rdx
  struct _KTHREAD *v28; // r9
  __int64 v29; // rdx
  NTSTATUS v30; // r13d
  char v31; // r12
  ULONG_PTR v32; // rbx
  __int64 v33; // rax
  struct _KTHREAD *v34; // rdx
  int v35; // eax
  HANDLE v36; // rax
  struct _KTHREAD *v37; // r9
  int v38; // edx
  ULONG_PTR v39; // rbx
  HANDLE CurrentProcessId; // rax
  char v42; // [rsp+44h] [rbp-174h]
  __int64 v44; // [rsp+58h] [rbp-160h] BYREF
  void *Src; // [rsp+60h] [rbp-158h]
  struct _KTHREAD *v46; // [rsp+68h] [rbp-150h]
  __int64 v47; // [rsp+70h] [rbp-148h] BYREF
  struct _OBJECT_NAME_INFORMATION *v48; // [rsp+78h] [rbp-140h]
  NTSTATUS v49; // [rsp+80h] [rbp-138h]
  __int64 v50; // [rsp+88h] [rbp-130h]
  LONGLONG v51; // [rsp+90h] [rbp-128h]
  struct _KTHREAD *v52; // [rsp+98h] [rbp-120h]
  struct _KTHREAD *CurrentThread; // [rsp+A0h] [rbp-118h]
  struct _KTHREAD *v54; // [rsp+A8h] [rbp-110h]
  struct _KTHREAD *v55; // [rsp+B0h] [rbp-108h]
  struct _KTHREAD *v56; // [rsp+B8h] [rbp-100h]
  struct _KTHREAD *v57; // [rsp+C0h] [rbp-F8h]
  struct _KTHREAD *v58; // [rsp+C8h] [rbp-F0h]
  struct _KTHREAD *v59; // [rsp+D0h] [rbp-E8h]
  struct _KTHREAD *v60; // [rsp+D8h] [rbp-E0h]
  struct _KTHREAD *v61; // [rsp+E0h] [rbp-D8h]
  struct _KTHREAD *v62; // [rsp+E8h] [rbp-D0h]
  struct _KTHREAD *v63; // [rsp+F0h] [rbp-C8h]
  struct _KTHREAD *v64; // [rsp+F8h] [rbp-C0h]
  struct _KTHREAD *v65; // [rsp+100h] [rbp-B8h]
  struct _KTHREAD *v66; // [rsp+108h] [rbp-B0h]
  struct _KTHREAD *v67; // [rsp+110h] [rbp-A8h]
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+118h] [rbp-A0h] BYREF
  ULONG ReturnLength; // [rsp+120h] [rbp-98h] BYREF
  PEPROCESS Process; // [rsp+128h] [rbp-90h] BYREF
  ULONG ReplyLength; // [rsp+130h] [rbp-88h] BYREF
  ULONG v72; // [rsp+134h] [rbp-84h] BYREF
  _DWORD ReplyBuffer[8]; // [rsp+138h] [rbp-80h] BYREF
  __int64 v74; // [rsp+158h] [rbp-60h]
  int v75; // [rsp+160h] [rbp-58h]
  __int64 v76; // [rsp+168h] [rbp-50h] BYREF

  v46 = a4;
  v52 = (struct _KTHREAD *)a2;
  CurrentThread = a5;
  Src = 0;
  DiskDeviceObject = 0;
  v7 = 0;
  v50 = 0;
  memset(ReplyBuffer, 0, sizeof(ReplyBuffer));
  v74 = 0;
  v75 = 0;
  ReplyLength = 0;
  v72 = 0;
  ReturnLength = 0;
  v8 = 0;
  v48 = 0;
  v9 = *(struct _FLT_VOLUME **)(a2 + 16);
  v44 = 0;
  v47 = 0;
  if ( a5 )
    *(_QWORD *)a5 = 0;
  *(_BYTE *)a4 = 0;
  v76 = -10000LL * *(unsigned int *)(MpData + 2432);
  if ( a1 )
  {
    IsProcessExemptByData = MpIsProcessExemptByData(a1);
  }
  else
  {
    CurrentProcessId = PsGetCurrentProcessId();
    IsProcessExemptByData = MpIsProcessExemptById(CurrentProcessId);
  }
  if ( (*(_DWORD *)(MpData + 868) & 0x10) != 0 && !*(_BYTE *)(MpData + 208) && !IsProcessExemptByData )
  {
    v11 = FltGetDiskDeviceObject(v9, &DiskDeviceObject);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          (unsigned int)WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
          (unsigned int)KeGetCurrentThread(),
          (__int64)v9);
      return (unsigned int)v11;
    }
    _InterlockedAdd64(&ObTotalReferences, 1u);
    KeEnterCriticalRegion();
    if ( a1 )
    {
      RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
      MpGetProcessContextByObject(RequestorProcess);
    }
    else
    {
      v36 = PsGetCurrentProcessId();
      MpGetProcessContextById(v36, &v44);
    }
    DeviceType = DiskDeviceObject->DeviceType;
    if ( DeviceType != 7 )
    {
      v11 = -1073741804;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        CurrentThread = KeGetCurrentThread();
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
          CurrentThread,
          DeviceType,
          -1073741804);
      }
      goto LABEL_135;
    }
    PoolWithTag = (struct _OBJECT_NAME_INFORMATION *)MpAllocatePoolWithTag(1, 1, 1852067917);
    v8 = (const void **)PoolWithTag;
    v48 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v11 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v52 = KeGetCurrentThread();
        WPP_SF_qDqL(WPP_GLOBAL_Control->AttachedDevice, 14, v15, (_DWORD)v52, 1, (__int64)DiskDeviceObject);
      }
      goto LABEL_135;
    }
    v11 = ObQueryNameString(DiskDeviceObject, PoolWithTag, 0, &ReturnLength);
    ExFreePoolWithTag(v8, 0x6E64504Du);
    if ( v11 == -1073741820 )
    {
      if ( !ReturnLength )
      {
        v11 = -1073741820;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_135;
        LODWORD(v37) = (unsigned int)KeGetCurrentThread();
        v38 = 16;
        goto LABEL_101;
      }
      v16 = (struct _OBJECT_NAME_INFORMATION *)MpAllocatePoolWithTag(1, ReturnLength, 1852067917);
      v8 = (const void **)v16;
      v48 = v16;
      if ( !v16 )
      {
        v11 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v54 = KeGetCurrentThread();
          WPP_SF_qDqL(WPP_GLOBAL_Control->AttachedDevice, 17, v17, (_DWORD)v54, ReturnLength, (__int64)DiskDeviceObject);
        }
        goto LABEL_135;
      }
      v11 = ObQueryNameString(DiskDeviceObject, v16, ReturnLength, &v72);
      if ( v11 >= 0 )
      {
        if ( v72 != ReturnLength )
        {
          v11 = -1073741820;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v56 = KeGetCurrentThread();
            WPP_SF_qDDL(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids);
          }
          goto LABEL_135;
        }
        IsHotPluggable = MpIsHotPluggable(a2);
        v42 = IsHotPluggable;
        v21 = a3;
        if ( !IsHotPluggable && !a3 )
        {
          if ( (unsigned __int8)MpIsGoodBootSector(v8) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              v57 = KeGetCurrentThread();
              WPP_SF_qZ(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                (unsigned int)WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                (_DWORD)v57,
                (__int64)v8);
            }
            goto LABEL_135;
          }
          v21 = a3;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          v58 = KeGetCurrentThread();
          WPP_SF_qZdd(WPP_GLOBAL_Control->AttachedDevice, v18, v19, (_DWORD)v58, (__int64)v8, v21, IsHotPluggable);
        }
        Src = (void *)MpAllocatePoolWithTag((unsigned int)(ExDefaultNonPagedPoolType + 4), 0x2000, 1952600141);
        if ( !Src )
        {
          v11 = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v59 = KeGetCurrentThread();
            WPP_SF_qDqL(WPP_GLOBAL_Control->AttachedDevice, 22, v22, (_DWORD)v59, 0x2000, (__int64)DiskDeviceObject);
          }
          goto LABEL_135;
        }
        RawDevice = MpReadRawDevice(DiskDeviceObject, 0);
        if ( RawDevice < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
              (unsigned int)RawDevice);
          }
          v35 = MpReadRawDevice(DiskDeviceObject, 1);
          v11 = v35;
          if ( v35 < 0 )
          {
            if ( v35 != -1073741805
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v60 = KeGetCurrentThread();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                24,
                WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                v60,
                v35);
            }
            goto LABEL_135;
          }
        }
        v24 = MpAllocatePoolWithTag(1, 8584, 1935822925);
        v7 = v24;
        v50 = v24;
        if ( v24 )
        {
          *(_DWORD *)v24 = 65957;
          *(_DWORD *)(v24 + 4) = 8584;
          *(_DWORD *)(v24 + 24) = (a3 != 0) + 1;
          *(_QWORD *)(v24 + 32) = 0x2000;
          v25 = PsGetCurrentProcessId();
          *(_QWORD *)(v7 + 40) = v25;
          TimeQuadPart = 0;
          v51 = 0;
          if ( v25 )
          {
            Process = 0;
            if ( PsLookupProcessByProcessId(v25, &Process) >= 0 )
            {
              TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
              v51 = TimeQuadPart;
              ObfDereferenceObject(Process);
            }
          }
          *(_QWORD *)(v7 + 56) = MpFileTimeToUlong64(TimeQuadPart);
          *(_QWORD *)(v7 + 64) = PsGetCurrentThreadId();
          if ( v44 )
            *(_DWORD *)(v7 + 48) = *(_DWORD *)(v44 + 56);
          MpGetPriorityInfo(a1, *((_QWORD *)v52 + 4), v7 + 8);
          if ( (*(_WORD *)v8 & 0xFFFEu) >= 0xC4 )
            *(_WORD *)(v7 + 88) = 194;
          else
            *(_WORD *)(v7 + 88) = *(_WORD *)v8;
          memmove((void *)(v7 + 90), v8[1], *(unsigned __int16 *)(v7 + 88));
          ReplyLength = 44;
          if ( a3 == 2 )
          {
            if ( DiskDeviceObject->SectorSize > 0x200u )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  29,
                  WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                  DiskDeviceObject->SectorSize);
              }
            }
            else
            {
              *(_QWORD *)(v7 + 368) = DiskDeviceObject;
              v27 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(MpData + 220));
              *(_DWORD *)(v7 + 376) = v27;
              v11 = MpCreateBootScanContext(DiskDeviceObject, v27, &v47);
              if ( v11 < 0 )
              {
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
                {
                  goto LABEL_135;
                }
                v28 = KeGetCurrentThread();
                v62 = v28;
                v29 = (unsigned int)(a3 + 26);
                goto LABEL_41;
              }
            }
          }
          *(_DWORD *)(v7 + 384) = 0x2000;
          memmove((void *)(v7 + 392), Src, 0x2000u);
          if ( a3 == 2 )
          {
            v39 = MpData;
            KeEnterCriticalRegion();
            ExAcquireResourceExclusiveLite((PERESOURCE)(v39 + 3152), 1u);
          }
          v30 = FltSendMessage(
                  *(PFLT_FILTER *)(MpData + 16),
                  (PFLT_PORT *)(MpData + 320),
                  (PVOID)v7,
                  *(_DWORD *)(v7 + 4),
                  ReplyBuffer,
                  &ReplyLength,
                  (PLARGE_INTEGER)((unsigned __int64)&v76 & -(__int64)(v76 != 0)));
          v49 = v30;
          if ( a3 == 2 )
          {
            ExReleaseResourceLite((PERESOURCE)(MpData + 3152));
            KeLeaveCriticalRegion();
          }
          if ( v30 >= 0 && v30 != 258 )
          {
            if ( ReplyLength >= 0x2C && HIWORD(ReplyBuffer[0]) == 44 )
            {
              if ( LOBYTE(ReplyBuffer[0]) == 0xA5 )
              {
                if ( BYTE1(ReplyBuffer[0]) != 1
                  && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                {
                  v64 = KeGetCurrentThread();
                  WPP_SF_qdddd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    32,
                    WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                    v64,
                    165,
                    BYTE1(ReplyBuffer[0]),
                    165,
                    1);
                }
LABEL_53:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_Zd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    33,
                    (unsigned int)WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                    (_DWORD)v8,
                    ReplyBuffer[1]);
                }
                if ( ReplyBuffer[1] )
                {
                  if ( ReplyBuffer[1] != 3 )
                  {
                    if ( ReplyBuffer[1] == 16 )
                    {
                      *(_BYTE *)v46 = 1;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                      {
                        WPP_SF_Z(
                          WPP_GLOBAL_Control->AttachedDevice,
                          34,
                          WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                          v8);
                      }
                      if ( !IsHotPluggable )
                        MpRemoveGoodBootSector(v8);
                    }
                    goto LABEL_59;
                  }
                  if ( !IsHotPluggable )
                    MpStoreGoodBootSector(v8);
                }
                *(_BYTE *)v46 = 0;
LABEL_59:
                v31 = 0;
                v32 = MpData;
                KeEnterCriticalRegion();
                ExAcquireResourceExclusiveLite((PERESOURCE)(v32 + 752), 1u);
                if ( v30 == 258 )
                {
                  ++*(_DWORD *)(MpData + 608);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                  {
                    v66 = KeGetCurrentThread();
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      35,
                      WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                      v66,
                      *(_DWORD *)(MpData + 608));
                  }
                  SwitchToPanicMode(0, 0, 0);
                  v31 = 1;
                }
                else
                {
                  SwitchOffPanicMode(0);
                }
                ExReleaseResourceLite((PERESOURCE)(MpData + 752));
                KeLeaveCriticalRegion();
                if ( v31 )
                  MpPurgeCache();
                if ( !a3 )
                {
                  v33 = MpAllocatePoolWithTag(1, 24, 1668108365);
                  v34 = CurrentThread;
                  *(_QWORD *)CurrentThread = v33;
                  if ( !v33 )
                  {
                    v11 = -1073741670;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                    {
                      v67 = KeGetCurrentThread();
                      WPP_SF_qD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        36,
                        WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                        v67,
                        -1073741670);
                    }
                    goto LABEL_135;
                  }
                  *(_DWORD *)(v33 + 16) = ReplyBuffer[1];
                  **(_QWORD **)v34 = v7;
                  v7 = 0;
                  v50 = 0;
                  *(_QWORD *)(*(_QWORD *)v34 + 8LL) = v44;
                  v44 = 0;
                  *(_BYTE *)(*(_QWORD *)v34 + 20LL) = v42;
                }
                v11 = 0;
LABEL_135:
                if ( Src )
                  ExFreePoolWithTag(Src, 0x7462504Du);
                ObfDereferenceObject(DiskDeviceObject);
                if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
                {
                  if ( KdRefreshDebuggerNotPresent() )
                    KeBugCheck(1u);
                  __debugbreak();
                }
                if ( v47 )
                  MpDeleteBootScanContext();
                if ( v8 )
                  ExFreePoolWithTag(v8, 0x6E64504Du);
                if ( v7 )
                  ExFreePoolWithTag((PVOID)v7, 0x7362504Du);
                if ( v44 )
                  MpReleaseProcessContext(v44);
                KeLeaveCriticalRegion();
                return (unsigned int)v11;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                v63 = KeGetCurrentThread();
                WPP_SF_qdddd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  31,
                  WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                  v63,
                  LOBYTE(ReplyBuffer[0]),
                  BYTE1(ReplyBuffer[0]),
                  165,
                  1);
              }
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v65 = KeGetCurrentThread();
              WPP_SF_qDD(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
                v65,
                ReplyLength,
                HIWORD(ReplyBuffer[0]));
            }
          }
          ReplyBuffer[1] = 0;
          goto LABEL_53;
        }
        v11 = -1073741670;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_135;
        v37 = KeGetCurrentThread();
        v61 = v37;
        v38 = 27;
LABEL_101:
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          v38,
          (unsigned int)WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids,
          (_DWORD)v37,
          (__int64)DiskDeviceObject);
        goto LABEL_135;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_135;
      v28 = KeGetCurrentThread();
      v55 = v28;
      v29 = 18;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_135;
      v28 = KeGetCurrentThread();
      v46 = v28;
      v29 = 15;
    }
LABEL_41:
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, v29, WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids, v28, v11);
    goto LABEL_135;
  }
  return 0;
}

```

## disassembly

```asm
0x140062588  mov     r11, rsp
0x14006258b  push    rbx
0x14006258c  push    rsi
0x14006258d  push    rdi
0x14006258e  push    r12
0x140062590  push    r13
0x140062592  push    r14
0x140062594  push    r15
0x140062596  sub     rsp, 180h
0x14006259d  mov     rax, cs:__security_cookie
0x1400625a4  xor     rax, rsp
0x1400625a7  mov     [rsp+1B8h+var_48], rax
0x1400625af  mov     [rsp+1B8h+var_150], r9
0x1400625b4  mov     dword ptr [rsp+1B8h+var_170], r8d
0x1400625b9  mov     rdi, rdx
0x1400625bc  mov     [rsp+1B8h+var_120], rdx
0x1400625c4  mov     r13, rcx
0x1400625c7  mov     rax, [rsp+1B8h+arg_20]
0x1400625cf  mov     [rsp+1B8h+var_118], rax
0x1400625d7  xor     esi, esi
0x1400625d9  mov     [rsp+1B8h+Src], rsi
0x1400625de  mov     [r11-0A0h], rsi
0x1400625e5  mov     r15d, esi
0x1400625e8  mov     [r11-130h], rsi
0x1400625ef  xorps   xmm0, xmm0
0x1400625f2  xor     ecx, ecx
0x1400625f4  movups  xmmword ptr [r11-80h], xmm0
0x1400625f9  movups  xmmword ptr [r11-70h], xmm0
0x1400625fe  mov     [r11-60h], rcx
0x140062602  mov     [r11-58h], ecx
0x140062606  mov     [rsp+1B8h+var_88], esi
0x14006260d  mov     [rsp+1B8h+var_84], esi
0x140062614  mov     [rsp+1B8h+ReturnLength], esi
0x14006261b  mov     r14d, esi
0x14006261e  mov     [rsp+1B8h+var_140], rsi
0x140062623  mov     [rsp+1B8h+var_174], sil
0x140062628  mov     r12, [rdx+10h]
0x14006262c  mov     [rsp+1B8h+var_160], rsi
0x140062631  mov     [rsp+1B8h+var_148], rsi
0x140062636  test    rax, rax
0x140062639  jz      short loc_14006263E
0x14006263b  mov     [rax], rsi
0x14006263e  mov     [r9], sil
0x140062641  mov     rax, cs:MpData
0x140062648  mov     ecx, [rax+980h]
0x14006264e  imul    rcx, 0FFFFFFFFFFFFD8F0h
0x140062655  mov     [rsp+1B8h+var_50], rcx
0x14006265d  test    r13, r13
0x140062660  jz      loc_14006354F
0x140062666  mov     rcx, r13
0x140062669  call    MpIsProcessExemptByData
0x14006266e  mov     dl, al
0x140062670  mov     rax, cs:MpData
0x140062677  mov     ecx, [rax+364h]
0x14006267d  test    cl, 10h
0x140062680  jz      loc_140063568
0x140062686  mov     rax, cs:MpData
0x14006268d  mov     cl, [rax+0D0h]
0x140062693  test    cl, cl
0x140062695  jnz     loc_140063568
0x14006269b  test    dl, dl
0x14006269d  jnz     loc_140063568
0x1400626a3  lea     rdx, [rsp+1B8h+DiskDeviceObject]; DiskDeviceObject
0x1400626ab  mov     rcx, r12; Volume
0x1400626ae  call    cs:__imp_FltGetDiskDeviceObject
0x1400626b5  nop     dword ptr [rax+rax+00h]
0x1400626ba  mov     ebx, eax
0x1400626bc  mov     esi, 1
0x1400626c1  test    eax, eax
0x1400626c3  js      short loc_1400626CD
0x1400626c5  lock add cs:ObTotalReferences, rsi
0x1400626cd  test    ebx, ebx
0x1400626cf  js      loc_1400635C9
0x1400626d5  call    cs:__imp_KeEnterCriticalRegion
0x1400626dc  nop     dword ptr [rax+rax+00h]
0x1400626e1  test    r13, r13
0x1400626e4  jz      loc_140062FAF
0x1400626ea  mov     rcx, r13
0x1400626ed  call    MpGetRequestorProcess
0x1400626f2  mov     rcx, rax; Process
0x1400626f5  lea     rdx, [rsp+1B8h+var_160]
0x1400626fa  call    MpGetProcessContextByObject
0x1400626ff  mov     rax, [rsp+1B8h+DiskDeviceObject]
0x140062707  mov     ecx, [rax+48h]
0x14006270a  cmp     ecx, 7
0x14006270d  jnz     loc_140062DE2
0x140062713  mov     r8d, 6E64504Dh
0x140062719  mov     rdx, rsi
0x14006271c  mov     ecx, esi
0x14006271e  call    MpAllocatePoolWithTag
0x140062723  mov     r14, rax
0x140062726  mov     [rsp+1B8h+var_140], rax
0x14006272b  test    rax, rax
0x14006272e  jz      loc_140062EEF
0x140062734  lea     r9, [rsp+1B8h+ReturnLength]; ReturnLength
0x14006273c  xor     r8d, r8d; Length
0x14006273f  mov     rdx, rax; ObjectNameInfo
0x140062742  mov     rcx, [rsp+1B8h+DiskDeviceObject]; Object
0x14006274a  call    cs:__imp_ObQueryNameString
0x140062751  nop     dword ptr [rax+rax+00h]
0x140062756  mov     ebx, eax
0x140062758  mov     [rsp+1B8h+var_178], eax
0x14006275c  mov     edx, 6E64504Dh; Tag
0x140062761  mov     rcx, r14; P
0x140062764  call    cs:__imp_ExFreePoolWithTag
0x14006276b  nop     dword ptr [rax+rax+00h]
0x140062770  mov     r12d, 0C0000004h
0x140062776  cmp     ebx, r12d
0x140062779  jnz     loc_140063015
0x14006277f  mov     eax, [rsp+1B8h+ReturnLength]
0x140062786  test    eax, eax
0x140062788  jz      loc_140063050
0x14006278e  mov     edx, eax
0x140062790  mov     r8d, 6E64504Dh
0x140062796  mov     ecx, esi
0x140062798  call    MpAllocatePoolWithTag
0x14006279d  mov     r14, rax
0x1400627a0  mov     [rsp+1B8h+var_140], rax
0x1400627a5  test    rax, rax
0x1400627a8  jz      loc_1400630DE
0x1400627ae  lea     r9, [rsp+1B8h+var_84]; ReturnLength
0x1400627b6  mov     r8d, [rsp+1B8h+ReturnLength]; Length
0x1400627be  mov     rdx, rax; ObjectNameInfo
0x1400627c1  mov     rcx, [rsp+1B8h+DiskDeviceObject]; Object
0x1400627c9  call    cs:__imp_ObQueryNameString
0x1400627d0  nop     dword ptr [rax+rax+00h]
0x1400627d5  mov     ebx, eax
0x1400627d7  mov     [rsp+1B8h+var_178], eax
0x1400627db  test    eax, eax
0x1400627dd  js      loc_140063145
0x1400627e3  mov     eax, [rsp+1B8h+var_84]
0x1400627ea  cmp     eax, [rsp+1B8h+ReturnLength]
0x1400627f1  jnz     loc_140063183
0x1400627f7  mov     rcx, rdi
0x1400627fa  call    MpIsHotPluggable
0x1400627ff  movzx   r12d, al
0x140062803  mov     [rsp+1B8h+var_174], r12b
0x140062808  mov     ecx, dword ptr [rsp+1B8h+var_170]
0x14006280c  test    al, al
0x14006280e  jnz     short loc_14006287D
0x140062810  test    ecx, ecx
0x140062812  jnz     short loc_14006287D
0x140062814  mov     rcx, r14
0x140062817  call    MpIsGoodBootSector
0x14006281c  test    al, al
0x14006281e  jz      loc_1400631FD
0x140062824  lea     rdi, WPP_GLOBAL_Control
0x14006282b  mov     rax, cs:WPP_GLOBAL_Control
0x140062832  cmp     rax, rdi
0x140062835  jz      loc_1400634AA
0x14006283b  mov     eax, [rax+2Ch]
0x14006283e  test    al, 4
0x140062840  jz      loc_1400634AA
0x140062846  mov     r9, gs:188h
0x14006284f  mov     [rsp+1B8h+var_F8], r9
0x140062857  mov     edx, 14h
0x14006285c  mov     [rsp+1B8h+ReplyBuffer], r14
0x140062861  lea     r8, WPP_3a24fb14a98a3bab9c6401a3dbbb7c6d_Traceguids
0x140062868  mov     rcx, cs:WPP_GLOBAL_Control
0x14006286f  mov     rcx, [rcx+18h]
0x140062873  call    WPP_SF_qZ
0x140062878  jmp     loc_1400634AA
0x14006287d  lea     rdi, WPP_GLOBAL_Control
0x140062884  mov     rax, cs:WPP_GLOBAL_Control
0x14006288b  cmp     rax, rdi
0x14006288e  jnz     loc_140062ADD
0x140062894  mov     eax, 2000h
0x140062899  mov     [rsp+1B8h+var_168], ax
0x14006289e  mov     ecx, cs:ExDefaultNonPagedPoolType
0x1400628a4  add     ecx, 4
0x1400628a7  mov     r8d, 7462504Dh
0x1400628ad  mov     edx, eax
0x1400628af  call    MpAllocatePoolWithTag
0x1400628b4  mov     rbx, rax
0x1400628b7  mov     [rsp+1B8h+Src], rax
0x1400628bc  test    rax, rax
0x1400628bf  jz      loc_140063206
0x1400628c5  mov     dword ptr [rsp+1B8h+ReplyBuffer], 0; int
0x1400628cd  mov     r9d, 2000h
0x1400628d3  mov     r8, rax
0x1400628d6  mov     rcx, [rsp+1B8h+DiskDeviceObject]; DeviceObject
0x1400628de  call    MpReadRawDevice
0x1400628e3  mov     r9d, eax
0x1400628e6  mov     [rsp+1B8h+var_178], eax
0x1400628ea  test    eax, eax
0x1400628ec  js      loc_140062E4B
0x1400628f2  mov     ebx, 2188h
0x1400628f7  mov     [rsp+1B8h+var_164], bx
0x1400628fc  mov     r8d, 7362504Dh
0x140062902  mov     edx, ebx
0x140062904  mov     ecx, esi
0x140062906  call    MpAllocatePoolWithTag
0x14006290b  mov     r15, rax
0x14006290e  mov     [rsp+1B8h+var_130], rax
0x140062916  test    rax, rax
0x140062919  jz      loc_140063230
0x14006291f  mov     dword ptr [rax], 101A5h
0x140062925  mov     [rax+4], ebx
0x140062928  mov     eax, dword ptr [rsp+1B8h+var_170]
0x14006292c  neg     eax
0x14006292e  sbb     ecx, ecx
0x140062930  neg     ecx
0x140062932  add     ecx, esi
0x140062934  mov     [r15+18h], ecx
0x140062938  mov     qword ptr [r15+20h], 2000h
0x140062940  call    cs:__imp_PsGetCurrentProcessId
0x140062947  nop     dword ptr [rax+rax+00h]
0x14006294c  mov     [r15+28h], rax
0x140062950  xor     ebx, ebx
0x140062952  mov     [rsp+1B8h+var_128], rbx
0x14006295a  test    rax, rax
0x14006295d  jz      short loc_1400629B5
0x14006295f  mov     [rsp+1B8h+Process], rbx
0x140062967  lea     rdx, [rsp+1B8h+Process]; Process
0x14006296f  mov     rcx, rax; ProcessId
0x140062972  call    cs:__imp_PsLookupProcessByProcessId
0x140062979  nop     dword ptr [rax+rax+00h]
0x14006297e  test    eax, eax
0x140062980  js      short loc_1400629B5
0x140062982  mov     rcx, [rsp+1B8h+Process]; Process
0x14006298a  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140062991  nop     dword ptr [rax+rax+00h]
0x140062996  mov     rbx, rax
0x140062999  mov     [rsp+1B8h+var_128], rax
0x1400629a1  mov     rcx, [rsp+1B8h+Process]; Object
0x1400629a9  call    cs:__imp_ObfDereferenceObject
0x1400629b0  nop     dword ptr [rax+rax+00h]
0x1400629b5  mov     rcx, rbx
0x1400629b8  call    MpFileTimeToUlong64
0x1400629bd  mov     [r15+38h], rax
0x1400629c1  call    cs:__imp_PsGetCurrentThreadId
0x1400629c8  nop     dword ptr [rax+rax+00h]
0x1400629cd  mov     [r15+40h], rax
0x1400629d1  mov     rcx, [rsp+1B8h+var_160]
0x1400629d6  test    rcx, rcx
0x1400629d9  jz      short loc_1400629E2
0x1400629db  mov     eax, [rcx+38h]
0x1400629de  mov     [r15+30h], eax
0x1400629e2  lea     r8, [r15+8]
0x1400629e6  mov     rdx, [rsp+1B8h+var_120]
0x1400629ee  mov     rdx, [rdx+20h]
0x1400629f2  mov     rcx, r13
0x1400629f5  call    MpGetPriorityInfo
0x1400629fa  movzx   ecx, word ptr [r14]
0x1400629fe  movzx   eax, cx
0x140062a01  mov     edx, 0FFFEh
0x140062a06  and     ax, dx
0x140062a09  mov     edx, 0C4h
0x140062a0e  cmp     ax, dx
0x140062a11  jnb     loc_140062EE0
0x140062a17  mov     [r15+58h], cx
0x140062a1c  movzx   r8d, word ptr [r15+58h]; Size
0x140062a21  lea     rcx, [r15+5Ah]; void *
0x140062a25  mov     rdx, [r14+8]; Src
0x140062a29  call    memmove
0x140062a2e  mov     eax, 2Ch ; ','
0x140062a33  mov     [rsp+1B8h+var_88], eax
0x140062a3a  mov     r13d, dword ptr [rsp+1B8h+var_170]
0x140062a3f  cmp     r13d, 2
0x140062a43  jnz     loc_140062B1C
0x140062a49  mov     rax, [rsp+1B8h+DiskDeviceObject]
0x140062a51  movzx   edx, word ptr [rax+130h]
0x140062a58  mov     ecx, 200h
0x140062a5d  cmp     dx, cx
0x140062a60  ja      loc_14006325A
0x140062a66  mov     [r15+170h], rax
0x140062a6d  mov     rax, cs:MpData
0x140062a74  mov     edx, esi
0x140062a76  lock xadd [rax+0DCh], edx
0x140062a7e  add     edx, esi
0x140062a80  mov     [r15+178h], edx
0x140062a87  lea     r8, [rsp+1B8h+var_148]
0x140062a8c  mov     rcx, [rsp+1B8h+DiskDeviceObject]
0x140062a94  call    MpCreateBootScanContext
0x140062a99  mov     ebx, eax
0x140062a9b  mov     [rsp+1B8h+var_178], eax
0x140062a9f  test    eax, eax
0x140062aa1  jns     short loc_140062B1C
0x140062aa3  mov     rax, cs:WPP_GLOBAL_Control
0x140062aaa  cmp     rax, rdi
0x140062aad  jz      loc_1400634AA
0x140062ab3  mov     eax, [rax+2Ch]
0x140062ab6  test    sil, al
0x140062ab9  jz      loc_1400634AA
0x140062abf  mov     r9, gs:188h
0x140062ac8  mov     [rsp+1B8h+var_D0], r9
0x140062ad0  lea     edx, [r13+1Ah]
0x140062ad4  mov     dword ptr [rsp+1B8h+ReplyBuffer], ebx
0x140062ad8  jmp     loc_140062DC6
0x140062add  mov     eax, [rax+2Ch]
0x140062ae0  test    al, 4
0x140062ae2  jz      loc_140062894
0x140062ae8  mov     r9, gs:188h
0x140062af1  mov     [rsp+1B8h+var_F0], r9
0x140062af9  mov     dword ptr [rsp+1B8h+Timeout], r12d
0x140062afe  mov     dword ptr [rsp+1B8h+ReplyLength], ecx
0x140062b02  mov     [rsp+1B8h+ReplyBuffer], r14
0x140062b07  mov     rcx, cs:WPP_GLOBAL_Control
0x140062b0e  mov     rcx, [rcx+18h]
0x140062b12  call    WPP_SF_qZdd
  ... truncated ...
```
