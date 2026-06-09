# RefsCommonVolumeOpen(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)

- ea: `0x14030bca0`
- end: `0x14030c8e4`
- name: `?RefsCommonVolumeOpen@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z`
- size: `3140`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *, struct _CREATE_CONTEXT *)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b9530`
- `0x14030d160`

## callees

- `0x14000c9b0`
- `0x14000e0e0`
- `0x140037820`
- `0x1400757c0`
- `0x140075ae0`
- `0x140076ad0`
- `0x140080070`
- `0x140085570`
- `0x1400862c0`
- `0x1400889f0`
- `0x14008c720`
- `0x140093bc0`
- `0x1400ab7ac`
- `0x1400d0fd8`
- `0x1400ffd64`
- `0x14028debc`
- `0x14028e0ec`
- `0x140302e10`
- `0x140302eb0`
- `0x140304a70`
- `0x140308440`
- `0x14030a7c0`
- `0x14030bca0`
- `0x14030c8f0`
- `0x14031f9c0`
- `0x140334b60`
- `0x1403366e0`

## import_xrefs

- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14030be43`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14030c831`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403424d3`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14030be43`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14030c831`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1403424d3`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x14030c116`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x14030c116`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x14030c27e`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x14030c27e`
- `ntoskrnl!ObGetObjectSecurity` at `0x14030c67d`
- `ntoskrnl!ObGetObjectSecurity` at `0x14030c67d`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14030c6d7`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14030c6d7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14030be2f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14030be2f`
- `ntoskrnl!ExReleaseFastResource` at `0x14030c257`
- `ntoskrnl!ExReleaseFastResource` at `0x14030c257`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c4b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c4b9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030c49a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030c49a`

## string_xrefs

- `0x14030bd8d`: `Create.c`
- `0x14030c8c1`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsCommonVolumeOpen(struct _IRP_CONTEXT *a1, struct _IRP *a2, struct _CREATE_CONTEXT *a3)
{
  __int64 v5; // rsi
  __int64 v6; // r12
  char v7; // r15
  __int64 v8; // rdi
  PFILE_OBJECT v9; // r14
  NTSTATUS v10; // r14d
  unsigned int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // eax
  NTSTATUS v17; // eax
  char v18; // cl
  int v19; // edx
  NTSTATUS v20; // eax
  int v21; // edx
  int v22; // ecx
  __int64 v23; // rdx
  char v24; // al
  struct _IRP_CONTEXT *v25; // rcx
  struct _IRP_CONTEXT *v26; // rdi
  int v27; // edx
  unsigned int v28; // r8d
  unsigned int v29; // r8d
  int v30; // edx
  PFILE_OBJECT v31; // rdi
  IRP *v32; // rdx
  char v34; // [rsp+81h] [rbp-87h]
  char v35; // [rsp+83h] [rbp-85h]
  char v36; // [rsp+84h] [rbp-84h]
  bool v37; // [rsp+90h] [rbp-78h]
  __int64 v38; // [rsp+98h] [rbp-70h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-68h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-58h]
  __int64 v42; // [rsp+B8h] [rbp-50h]
  PFILE_OBJECT v43; // [rsp+C0h] [rbp-48h]
  struct _CREATE_CONTEXT *MemoryAllocated; // [rsp+120h] [rbp+18h] BYREF
  PVOID P; // [rsp+128h] [rbp+20h] BYREF

  MemoryAllocated = a3;
  v5 = 0;
  v42 = 0;
  v6 = 0;
  v41 = 0;
  v38 = 0;
  v7 = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  LOBYTE(P) = 0;
  v8 = *((_QWORD *)a3 + 20);
  v9 = *(PFILE_OBJECT *)(v8 + 48);
  FileObject = v9;
  v43 = v9;
  *((_DWORD *)a1 + 175) = 25;
  if ( ((*(_BYTE *)(v8 + 19) - 1) & 0xFD) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v10 = -1073741790;
    }
    else
    {
      v10 = -1073741790;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v11 = 4365;
LABEL_9:
      RefsStatusDebug(v10, 0, "Create.c", v11);
      goto LABEL_133;
    }
    goto LABEL_133;
  }
  if ( (*(_DWORD *)(v8 + 16) & 1) == 0 )
  {
    if ( (*(_BYTE *)(v8 + 26) & 6) == 0 )
    {
      KeWaitForSingleObject((PVOID)(*((_QWORD *)a1 + 8) + 6128LL), Executive, 0, 0, 0);
      FsRtlNotifyVolumeEvent(v9, 3u);
      v35 = 1;
    }
    v5 = *((_QWORD *)a1 + 8);
    v42 = v5;
    v12 = *((_QWORD *)a1 + 13);
    v13 = *(_QWORD *)(v12 + 8) & 0x20000000000LL;
    if ( (*(_BYTE *)(v8 + 26) & 6) != 0 )
    {
      if ( !v13 )
      {
        MsInitializeFastResourceOwnerEntry(v12 + 160);
        *(_QWORD *)(v12 + 8) |= v15;
      }
      if ( !(unsigned __int8)MsAcquireFastResourceSharedInternal<0>(v5 + 1312, v12 + 160, *((_BYTE *)a1 + 8) & 1) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            &WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, a1, "ResrcSup.c", 0x1EDu);
        RefsRaiseStatusInternal(a1, -1073741608, (unsigned int)a3);
        __debugbreak();
      }
    }
    else
    {
      if ( !v13 )
      {
        MsInitializeFastResourceOwnerEntry(v12 + 160);
        *(_QWORD *)(v12 + 8) |= v14;
      }
      if ( !(unsigned __int8)MsAcquireFastResourceExclusive(v5 + 1312, v12 + 160, *((_BYTE *)a1 + 8) & 1) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            &WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, a1, "ResrcSup.c", 0x1A8u);
        RefsRaiseStatusInternal(a1, -1073741608, (unsigned int)a3);
        __debugbreak();
      }
    }
    v7 = 1;
    if ( (*(_DWORD *)(v5 + 24) & 0x802) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741790;
      }
      else
      {
        v10 = -1073741790;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225506LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v11 = 4417;
        goto LABEL_9;
      }
      goto LABEL_133;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 208) + 16LL) + 48LL) & 2) != 0 || (*(_DWORD *)(v5 + 24) & 1) == 0 )
    {
      *((_DWORD *)a1 + 1) |= 0x200000u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225688LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741608, a1, "Create.c", 0x1160u);
      RefsRaiseStatusInternal(a1, -1073741608, (unsigned int)a3);
      __debugbreak();
      JUMPOUT(0x14030C8E4LL);
    }
    v6 = *(_QWORD *)(*(_QWORD *)(v5 + 72) + 136LL);
    v41 = v6;
    RefsAcquireExclusiveFcb(a1, v6, 0, 1);
    RefsAccessCheck(
      a1,
      0,
      (struct _FCB *)v6,
      0,
      a2,
      *(_DWORD *)(a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId + 16),
      0,
      0,
      0);
    RefsReleaseFcb(a1, (struct _FCB *)v6);
    v34 = 0;
    RefsCheckpointCurrentTransaction(a1);
    v16 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL) + 20LL);
    if ( (*(_BYTE *)(v8 + 26) & 6) != 0 )
    {
      if ( (v16 & 7) != 0 )
        v37 = (*(_DWORD *)(v5 + 24) & 0x2000000) == 0;
      goto LABEL_112;
    }
    if ( (v16 & 6) != 0 )
    {
      LOBYTE(P) = 1;
      if ( FsRtlAreVolumeStartupApplicationsComplete() )
        *(_WORD *)(v8 + 26) &= ~1u;
    }
    if ( (*(_BYTE *)(v8 + 26) & 1) == 0 && *(_DWORD *)(v5 + 216) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741757;
      }
      else
      {
        v10 = -1073741757;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 60, &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225539LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v11 = 4530;
        goto LABEL_9;
      }
      goto LABEL_133;
    }
    if ( RefsUseFlushVolumeParallel )
      v17 = RefsFlushVolumeParallel(a1, v5, 15);
    else
      v17 = RefsFlushVolumeOriginal(a1, v5, 15);
    v10 = v17;
    if ( v17 == -1073741797 )
      v10 = 0;
    v18 = 0;
    v19 = *(_DWORD *)(v5 + 220);
    LODWORD(a3) = *(_DWORD *)(v5 + 228);
    if ( (*(_BYTE *)(v8 + 26) & 1) != 0 )
    {
      if ( *(_DWORD *)(v5 + 224) == v19 - (_DWORD)a3 )
        goto LABEL_97;
    }
    else if ( v19 == (_DWORD)a3 )
    {
      goto LABEL_97;
    }
    v18 = 1;
    if ( v10 >= 0 )
    {
      RefsCheckpointCurrentTransaction(a1);
      if ( (*((_DWORD *)a1 + 1) & 0x2000) != 0 )
      {
        *((_DWORD *)a1 + 1) &= 0xFFFFCFFF;
        ExReleaseFastResource(v5 + 1208, 0);
      }
      RefsReleaseAllExclusiveFcbsWithPaging(a1);
      RefsReleaseVcb(a1, (struct _VCB *)v5);
      CcWaitForCurrentLazyWriterActivity();
      RefsAcquireExclusiveVcb(a1, (struct _VCB *)v5, 1u);
      if ( (*(_DWORD *)(v5 + 24) & 0x802) != 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v10 = -1073741790;
        }
        else
        {
          v10 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            61,
            &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225506LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 4609;
          goto LABEL_9;
        }
        goto LABEL_133;
      }
      if ( RefsUseFlushVolumeParallel )
        v20 = RefsFlushVolumeParallel(a1, v5, 15);
      else
        v20 = RefsFlushVolumeOriginal(a1, v5, 15);
      v10 = v20;
      if ( v20 == -1073741797 )
        v10 = 0;
      v18 = 0;
      v21 = *(_DWORD *)(v5 + 220);
      LODWORD(a3) = *(_DWORD *)(v5 + 228);
      if ( (*(_BYTE *)(v8 + 26) & 1) != 0 )
      {
        if ( *(_DWORD *)(v5 + 224) == v21 - (_DWORD)a3 )
          goto LABEL_97;
        v18 = 1;
        if ( !RefsTrackVolumeOpenSharingViolation )
          goto LABEL_97;
      }
      else
      {
        if ( v21 == (_DWORD)a3 )
          goto LABEL_97;
        v18 = 1;
        if ( !RefsTrackVolumeOpenSharingViolation )
          goto LABEL_97;
      }
      __int2c();
    }
LABEL_97:
    if ( v18 )
    {
      if ( v10 >= 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v10 = -1073741757;
        }
        else
        {
          v10 = -1073741757;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            62,
            &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225539LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 4667;
          goto LABEL_9;
        }
      }
      goto LABEL_133;
    }
    if ( v10 < 0 && v10 != -1073741797 )
      goto LABEL_133;
    v9 = FileObject;
    if ( (_BYTE)P )
      v36 = 1;
LABEL_112:
    P = v9->FileName.Buffer;
    v9->FileName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x10u, 0x43466552u);
    if ( P )
      ExFreePoolWithTag(P, 0);
    *(_OWORD *)v9->FileName.Buffer = *(_OWORD *)L"\\$Volume";
    *(_DWORD *)&v9->FileName.Length = 1048592;
    v9->Flags &= ~0x40u;
    v9->Flags |= 8u;
    v9->PrivateCacheMap = 0;
    RefsAcquireExclusiveFcb(a1, v6, 0, 1);
    v34 = 1;
    v22 = 2;
    if ( *(_DWORD *)(v6 + 16) )
      v22 = 0;
    v10 = RefsOpenAttribute(
            (struct _IRP **)a1,
            v8,
            v5,
            0,
            (__int64)MemoryAllocated,
            (struct _FCB *)v6,
            2,
            (__int64)&RefsEmptyString,
            0x80u,
            v22,
            4,
            0,
            2,
            0,
            (struct _SCB **)(v5 + 72),
            &v38);
    if ( v10 >= 0 )
    {
      v23 = *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL);
      if ( (*(_BYTE *)(v23 + 20) & 3) == 3 )
      {
        *(_WORD *)(v38 + 88) |= 0x200u;
      }
      else if ( RefsCanAdministerVolume((struct _IRP_CONTEXT *)(*(_DWORD *)(v23 + 20) & 3), a2, (struct _FCB *)v6, 0, 0) )
      {
        *(_WORD *)(v38 + 88) |= 0x200u;
      }
      else
      {
        v24 = RefsEffectiveMode(a2, (struct _IO_STACK_LOCATION *)v8);
        if ( RefsPrivilegeCheck(
               0x1Cu,
               (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL) + 32LL),
               v24) )
        {
          *(_WORD *)(v38 + 88) |= 0x200u;
        }
        else
        {
          LOBYTE(MemoryAllocated) = 0;
          SecurityDescriptor = 0;
          LODWORD(P) = 3;
          if ( !ObGetObjectSecurity(
                  *(PVOID *)(*(_QWORD *)(v5 + 208) + 16LL),
                  &SecurityDescriptor,
                  (PBOOLEAN)&MemoryAllocated)
            && SecurityDescriptor )
          {
            if ( RefsCanAdministerVolume(v25, a2, (struct _FCB *)v6, SecurityDescriptor, (unsigned int *)&P) )
              *(_WORD *)(v38 + 88) |= 0x200u;
            ObReleaseObjectSecurity(SecurityDescriptor, (BOOLEAN)MemoryAllocated);
          }
        }
      }
      if ( v37 )
        *(_DWORD *)(v38 + 4) |= 0x200u;
      if ( v36 )
      {
        *(_DWORD *)(v5 + 24) |= 2u;
        *(_QWORD *)(v5 + 872) = FileObject;
        v35 = 0;
      }
      a2->IoStatus.Information = 1;
    }
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v10 = -1073741811;
  }
  else
  {
    v10 = -1073741811;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225485LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v11 = 4375;
    goto LABEL_9;
  }
LABEL_133:
  v26 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 13);
  if ( a1 != v26 && *((_BYTE *)a1 + 40) == 3 )
    v26 = a1;
  v27 = *((_DWORD *)v26 + 4);
  if ( v27 < 0 )
  {
    RefsRaiseStatusInternal(a1, v27, (unsigned int)a3);
    __debugbreak();
  }
  if ( v10 < 0 && RefsIsTransactionActive(v26) )
  {
    RefsRaiseStatusInternal(a1, v10, v28);
    __debugbreak();
  }
  if ( *((_DWORD *)a1 + 154) || *((_DWORD *)a1 + 155) )
  {
    RefsWriteUsnJournalChanges(a1);
    RefsCommitCurrentTransaction(a1, 0);
    v30 = *((_DWORD *)v26 + 4);
    if ( v30 < 0 )
    {
      RefsRaiseStatusInternal(a1, v30, v29);
      __debugbreak();
    }
  }
  v31 = FileObject;
  if ( !v10 )
  {
    FileObject->FileName.Buffer = 0;
    *(_DWORD *)&v31->FileName.Length = 0;
    *(_DWORD *)(v38 + 4) |= 0x4000u;
  }
  if ( v34 )
    RefsReleaseFcb(a1, (struct _FCB *)v6);
  if ( v7 )
    RefsReleaseVcb(a1, (struct _VCB *)v5);
  if ( v35 )
  {
    if ( RefsIsTransactionActive(a1) )
    {
      if ( !*((_QWORD *)a1 + 43) )
        MsTriageGetContext(*((_QWORD *)a1 + 3), (char *)a1 + 344);
      RefsAbortTransaction(a1);
    }
    RefsReleaseAllResources(a1);
    FsRtlNotifyVolumeEvent(v31, 4u);
  }
  v32 = 0;
  if ( (*((_BYTE *)a1 + 8) & 2) == 0 )
    v32 = a2;
  RefsCompleteRequest(a1, v32, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14030bca0  mov     r11, rsp
0x14030bca3  mov     [r11+18h], r8
0x14030bca7  mov     [r11+8], rcx
0x14030bcab  push    rbx
0x14030bcac  push    rsi
0x14030bcad  push    rdi
0x14030bcae  push    r12
0x14030bcb0  push    r13
0x14030bcb2  push    r14
0x14030bcb4  push    r15
0x14030bcb6  sub     rsp, 0D0h
0x14030bcbd  mov     rax, r8
0x14030bcc0  mov     r13, rdx
0x14030bcc3  mov     rbx, rcx
0x14030bcc6  xor     esi, esi
0x14030bcc8  mov     [r11-50h], rsi
0x14030bccc  xor     r12d, r12d
0x14030bccf  mov     [r11-58h], r12
0x14030bcd3  mov     [r11-70h], rsi
0x14030bcd7  xor     r15b, r15b
0x14030bcda  mov     [r11-86h], r15b
0x14030bce1  mov     [rsp+108h+var_87], sil
0x14030bce9  mov     [rsp+108h+var_84], sil
0x14030bcf1  mov     [rsp+108h+var_85], sil
0x14030bcf9  mov     [rsp+108h+var_78], sil
0x14030bd01  mov     [r11+20h], sil
0x14030bd05  mov     rdi, [r8+0A0h]
0x14030bd0c  mov     r14, [rdi+30h]
0x14030bd10  mov     [rsp+108h+FileObject], r14
0x14030bd18  mov     [rsp+108h+var_48], r14
0x14030bd20  mov     dword ptr [rcx+2BCh], 19h
0x14030bd2a  movzx   eax, byte ptr [rdi+13h]
0x14030bd2e  dec     al
0x14030bd30  test    al, 0FDh
0x14030bd32  jz      short loc_14030BDAB
0x14030bd34  lea     rax, WPP_GLOBAL_Control
0x14030bd3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14030bd42  cmp     rcx, rax
0x14030bd45  jz      short loc_14030BD76
0x14030bd47  mov     eax, [rcx+2Ch]
0x14030bd4a  bt      eax, 8
0x14030bd4e  jnb     short loc_14030BD76
0x14030bd50  cmp     byte ptr [rcx+29h], 4
0x14030bd54  jb      short loc_14030BD76
0x14030bd56  mov     edx, 38h ; '8'
0x14030bd5b  mov     r14d, 0C0000022h
0x14030bd61  mov     r9d, r14d
0x14030bd64  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030bd6b  mov     rcx, [rcx+18h]
0x14030bd6f  call    WPP_SF_d
0x14030bd74  jmp     short loc_14030BD7C
0x14030bd76  mov     r14d, 0C0000022h
0x14030bd7c  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030bd83  test    al, al
0x14030bd85  jz      short loc_14030BD9E
0x14030bd87  mov     r9d, 110Dh; unsigned int
0x14030bd8d  lea     r8, aCreateC; "Create.c"
0x14030bd94  xor     edx, edx; struct _IRP_CONTEXT *
0x14030bd96  mov     ecx, r14d; Status
0x14030bd99  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14030bd9e  mov     [rsp+108h+var_80], r14d
0x14030bda6  jmp     loc_14030C72C
0x14030bdab  mov     eax, [rdi+10h]
0x14030bdae  test    al, 1
0x14030bdb0  jz      short loc_14030BE0D
0x14030bdb2  lea     rax, WPP_GLOBAL_Control
0x14030bdb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14030bdc0  cmp     rcx, rax
0x14030bdc3  jz      short loc_14030BDF4
0x14030bdc5  mov     eax, [rcx+2Ch]
0x14030bdc8  bt      eax, 8
0x14030bdcc  jnb     short loc_14030BDF4
0x14030bdce  cmp     byte ptr [rcx+29h], 4
0x14030bdd2  jb      short loc_14030BDF4
0x14030bdd4  mov     edx, 39h ; '9'
0x14030bdd9  mov     r14d, 0C000000Dh
0x14030bddf  mov     r9d, r14d
0x14030bde2  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030bde9  mov     rcx, [rcx+18h]
0x14030bded  call    WPP_SF_d
0x14030bdf2  jmp     short loc_14030BDFA
0x14030bdf4  mov     r14d, 0C000000Dh
0x14030bdfa  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030be01  test    al, al
0x14030be03  jz      short loc_14030BD9E
0x14030be05  mov     r9d, 1117h
0x14030be0b  jmp     short loc_14030BD8D
0x14030be0d  test    byte ptr [rdi+1Ah], 6
0x14030be11  jnz     short loc_14030BE57
0x14030be13  mov     rcx, [rcx+40h]
0x14030be17  add     rcx, 17F0h; Object
0x14030be1e  mov     [rsp+108h+Timeout], 0; Timeout
0x14030be27  xor     r9d, r9d; Alertable
0x14030be2a  xor     r8d, r8d; WaitMode
0x14030be2d  xor     edx, edx; WaitReason
0x14030be2f  call    cs:__imp_KeWaitForSingleObject
0x14030be36  nop     dword ptr [rax+rax+00h]
0x14030be3b  mov     edx, 3; EventCode
0x14030be40  mov     rcx, r14; FileObject
0x14030be43  call    cs:__imp_FsRtlNotifyVolumeEvent
0x14030be4a  nop     dword ptr [rax+rax+00h]
0x14030be4f  mov     [rsp+108h+var_85], 1
0x14030be57  mov     rsi, [rbx+40h]
0x14030be5b  mov     [rsp+108h+var_50], rsi
0x14030be63  mov     rdx, [rbx+68h]
0x14030be67  mov     r8, 20000000000h
0x14030be71  mov     rcx, [rdx+8]
0x14030be75  and     rcx, r8
0x14030be78  test    byte ptr [rdi+1Ah], 6
0x14030be7c  jnz     loc_14030BF2B
0x14030be82  test    rcx, rcx
0x14030be85  jnz     short loc_14030BE97
0x14030be87  lea     rcx, [rdx+0A0h]
0x14030be8e  call    MsInitializeFastResourceOwnerEntry
0x14030be93  or      [rdx+8], r8
0x14030be97  movzx   r8d, byte ptr [rbx+8]
0x14030be9c  and     r8b, 1
0x14030bea0  lea     rcx, [rsi+520h]
0x14030bea7  add     rdx, 0A0h
0x14030beae  call    MsAcquireFastResourceExclusive
0x14030beb3  test    al, al
0x14030beb5  jnz     loc_14030BFD0
0x14030bebb  lea     rax, WPP_GLOBAL_Control
0x14030bec2  mov     rcx, cs:WPP_GLOBAL_Control
0x14030bec9  cmp     rcx, rax
0x14030becc  jz      short loc_14030BEF8
0x14030bece  test    dword ptr [rcx+2Ch], 100h
0x14030bed5  jz      short loc_14030BEF8
0x14030bed7  cmp     byte ptr [rcx+29h], 4
0x14030bedb  jb      short loc_14030BEF8
0x14030bedd  mov     edx, 0Ah
0x14030bee2  mov     r9d, 0C00000D8h
0x14030bee8  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x14030beef  mov     rcx, [rcx+18h]
0x14030bef3  call    WPP_SF_d
0x14030bef8  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030beff  test    al, al
0x14030bf01  jz      short loc_14030BF1D
0x14030bf03  mov     r9d, 1A8h; unsigned int
0x14030bf09  lea     r8, aResrcsupC; "ResrcSup.c"
0x14030bf10  mov     rdx, rbx; struct _IRP_CONTEXT *
0x14030bf13  mov     ecx, 0C00000D8h; Status
0x14030bf18  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14030bf1d  mov     edx, 0C00000D8h; int
0x14030bf22  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14030bf25  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14030bf2a  int     3; Trap to Debugger
0x14030bf2b  test    rcx, rcx
0x14030bf2e  jnz     short loc_14030BF40
0x14030bf30  lea     rcx, [rdx+0A0h]
0x14030bf37  call    MsInitializeFastResourceOwnerEntry
0x14030bf3c  or      [rdx+8], r8
0x14030bf40  movzx   r8d, byte ptr [rbx+8]
0x14030bf45  and     r8b, 1
0x14030bf49  lea     rcx, [rsi+520h]
0x14030bf50  add     rdx, 0A0h
0x14030bf57  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14030bf5c  test    al, al
0x14030bf5e  jnz     short loc_14030BFD0
0x14030bf60  lea     rax, WPP_GLOBAL_Control
0x14030bf67  mov     rcx, cs:WPP_GLOBAL_Control
0x14030bf6e  cmp     rcx, rax
0x14030bf71  jz      short loc_14030BF9D
0x14030bf73  test    dword ptr [rcx+2Ch], 100h
0x14030bf7a  jz      short loc_14030BF9D
0x14030bf7c  cmp     byte ptr [rcx+29h], 4
0x14030bf80  jb      short loc_14030BF9D
0x14030bf82  mov     edx, 0Bh
0x14030bf87  mov     r9d, 0C00000D8h
0x14030bf8d  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x14030bf94  mov     rcx, [rcx+18h]
0x14030bf98  call    WPP_SF_d
0x14030bf9d  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030bfa4  test    al, al
0x14030bfa6  jz      short loc_14030BFC2
0x14030bfa8  mov     r9d, 1EDh; unsigned int
0x14030bfae  lea     r8, aResrcsupC; "ResrcSup.c"
0x14030bfb5  mov     rdx, rbx; struct _IRP_CONTEXT *
0x14030bfb8  mov     ecx, 0C00000D8h; Status
0x14030bfbd  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14030bfc2  mov     edx, 0C00000D8h; int
0x14030bfc7  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14030bfca  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14030bfcf  int     3; Trap to Debugger
0x14030bfd0  mov     r15b, 1
0x14030bfd3  mov     [rsp+108h+var_86], r15b
0x14030bfdb  test    dword ptr [rsi+18h], 802h
0x14030bfe2  jz      short loc_14030C046
0x14030bfe4  lea     rax, WPP_GLOBAL_Control
0x14030bfeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14030bff2  cmp     rcx, rax
0x14030bff5  jz      short loc_14030C026
0x14030bff7  mov     eax, [rcx+2Ch]
0x14030bffa  bt      eax, 8
0x14030bffe  jnb     short loc_14030C026
0x14030c000  cmp     byte ptr [rcx+29h], 4
0x14030c004  jb      short loc_14030C026
0x14030c006  mov     edx, 3Ah ; ':'
0x14030c00b  mov     r14d, 0C0000022h
0x14030c011  mov     r9d, r14d
0x14030c014  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030c01b  mov     rcx, [rcx+18h]
0x14030c01f  call    WPP_SF_d
0x14030c024  jmp     short loc_14030C02C
0x14030c026  mov     r14d, 0C0000022h
0x14030c02c  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030c033  test    al, al
0x14030c035  jz      loc_14030BD9E
0x14030c03b  mov     r9d, 1141h
0x14030c041  jmp     loc_14030BD8D
0x14030c046  mov     eax, [rsi+18h]
0x14030c049  mov     rax, [rsi+0D0h]
0x14030c050  mov     rcx, [rax+10h]
0x14030c054  mov     eax, [rcx+30h]
0x14030c057  test    al, 2
0x14030c059  jnz     loc_14030C86C
0x14030c05f  mov     eax, [rsi+18h]
0x14030c062  test    r15b, al
0x14030c065  jz      loc_14030C86C
0x14030c06b  mov     rax, [rsi+48h]
0x14030c06f  mov     r12, [rax+88h]
0x14030c076  mov     [rsp+108h+var_58], r12
0x14030c07e  mov     r9d, 1
0x14030c084  xor     r8d, r8d
0x14030c087  mov     rdx, r12
0x14030c08a  mov     rcx, rbx
0x14030c08d  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14030c092  mov     [rsp+108h+var_87], r15b
0x14030c09a  mov     rax, [r13+0B8h]
0x14030c0a1  mov     rax, [rax+8]
0x14030c0a5  mov     [rsp+108h+var_C8], 0; unsigned __int8
0x14030c0aa  mov     [rsp+108h+var_D0], 0; unsigned __int8
0x14030c0af  mov     [rsp+108h+var_D8], 0; unsigned __int8
0x14030c0b4  mov     eax, [rax+10h]
0x14030c0b7  mov     [rsp+108h+var_E0], eax; unsigned int
0x14030c0bb  mov     [rsp+108h+Timeout], r13; struct _IRP *
0x14030c0c0  xor     r9d, r9d; struct _FCB *
0x14030c0c3  mov     r8, r12; struct _FCB *
0x14030c0c6  xor     edx, edx; struct _CREATE_CONTEXT *
0x14030c0c8  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14030c0cb  call    ?RefsAccessCheck@@YAXPEAU_IRP_CONTEXT@@PEAU_CREATE_CONTEXT@@PEAU_FCB@@2PEAU_IRP@@KEEE@Z; RefsAccessCheck(_IRP_CONTEXT *,_CREATE_CONTEXT *,_FCB *,_FCB *,_IRP *,ulong,uchar,uchar,uchar)
0x14030c0d0  mov     rdx, r12; struct _FCB *
0x14030c0d3  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14030c0d6  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x14030c0db  mov     [rsp+108h+var_87], 0
0x14030c0e3  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14030c0e6  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x14030c0eb  mov     rax, [rdi+8]
0x14030c0ef  mov     rcx, [rax+8]
0x14030c0f3  mov     eax, [rcx+14h]
0x14030c0f6  test    byte ptr [rdi+1Ah], 6
0x14030c0fa  jnz     loc_14030C456
0x14030c100  test    al, 6
0x14030c102  jz      short loc_14030C12F
0x14030c104  movzx   eax, r15b
0x14030c108  mov     byte ptr [rsp+108h+P], al
0x14030c10f  mov     [rsp+108h+var_7C], al
0x14030c116  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x14030c11d  nop     dword ptr [rax+rax+00h]
0x14030c122  test    al, al
0x14030c124  jz      short loc_14030C12F
0x14030c126  mov     eax, 0FFFEh
0x14030c12b  and     [rdi+1Ah], ax
0x14030c12f  test    [rdi+1Ah], r15b
0x14030c133  jnz     short loc_14030C1A0
0x14030c135  cmp     dword ptr [rsi+0D8h], 0
0x14030c13c  jz      short loc_14030C1A0
0x14030c13e  lea     rax, WPP_GLOBAL_Control
0x14030c145  mov     rcx, cs:WPP_GLOBAL_Control
0x14030c14c  cmp     rcx, rax
0x14030c14f  jz      short loc_14030C180
0x14030c151  mov     eax, [rcx+2Ch]
0x14030c154  bt      eax, 8
0x14030c158  jnb     short loc_14030C180
0x14030c15a  cmp     byte ptr [rcx+29h], 4
0x14030c15e  jb      short loc_14030C180
0x14030c160  mov     edx, 3Ch ; '<'
0x14030c165  mov     r14d, 0C0000043h
0x14030c16b  mov     r9d, r14d
0x14030c16e  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030c175  mov     rcx, [rcx+18h]
0x14030c179  call    WPP_SF_d
0x14030c17e  jmp     short loc_14030C186
0x14030c180  mov     r14d, 0C0000043h
0x14030c186  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030c18d  test    al, al
0x14030c18f  jz      loc_14030BD9E
0x14030c195  mov     r9d, 11B2h
0x14030c19b  jmp     loc_14030BD8D
0x14030c1a0  movzx   eax, cs:?RefsUseFlushVolumeParallel@@3EC; uchar volatile RefsUseFlushVolumeParallel
0x14030c1a7  mov     r8d, 0Fh
0x14030c1ad  mov     rdx, rsi
0x14030c1b0  mov     rcx, rbx
0x14030c1b3  test    al, al
0x14030c1b5  jz      short loc_14030C1BE
0x14030c1b7  call    ?RefsFlushVolumeParallel@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeParallel(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x14030c1bc  jmp     short loc_14030C1C3
0x14030c1be  call    ?RefsFlushVolumeOriginal@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeOriginal(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x14030c1c3  mov     r14d, eax
0x14030c1c6  mov     [rsp+108h+var_80], eax
  ... truncated ...
```
