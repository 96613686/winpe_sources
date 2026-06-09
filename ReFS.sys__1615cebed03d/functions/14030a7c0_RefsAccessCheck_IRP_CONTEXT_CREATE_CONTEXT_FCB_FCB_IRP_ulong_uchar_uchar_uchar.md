# RefsAccessCheck(_IRP_CONTEXT *,_CREATE_CONTEXT *,_FCB *,_FCB *,_IRP *,ulong,uchar,uchar,uchar)

- ea: `0x14030a7c0`
- end: `0x14030b6ed`
- name: `?RefsAccessCheck@@YAXPEAU_IRP_CONTEXT@@PEAU_CREATE_CONTEXT@@PEAU_FCB@@2PEAU_IRP@@KEEE@Z`
- size: `3885`
- prototype: `void(struct _IRP_CONTEXT *, struct _CREATE_CONTEXT *, struct _FCB *, struct _FCB *, struct _IRP *, unsigned int, unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `4`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402986f0`
- `0x14030a450`
- `0x14030bca0`
- `0x14030d820`

## callees

- `0x140036670`
- `0x1400733d0`
- `0x140076ad0`
- `0x1400862c0`
- `0x140089220`
- `0x1400d0fd8`
- `0x1401f3fc0`
- `0x1401f4400`
- `0x14028c008`
- `0x1402cc818`
- `0x1402d7f2c`
- `0x14030a7c0`
- `0x14030b700`
- `0x140328660`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x14030a8f0`
- `ntoskrnl!IoFileObjectType` at `0x14030aab9`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030a9c0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030ae41`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030af8c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030b148`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030a9c0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030ae41`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030af8c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14030b148`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14030ac0c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14030ac0c`
- `ntoskrnl!SeLockSubjectContext` at `0x14030a98a`
- `ntoskrnl!SeLockSubjectContext` at `0x14030adbd`
- `ntoskrnl!SeLockSubjectContext` at `0x14030b409`
- `ntoskrnl!SeLockSubjectContext` at `0x14030a98a`
- `ntoskrnl!SeLockSubjectContext` at `0x14030adbd`
- `ntoskrnl!SeLockSubjectContext` at `0x14030b409`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030ad58`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b2b0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b34f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b3ad`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b5e0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14034237b`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030ad58`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b2b0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b34f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b3ad`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14030b5e0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14034237b`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x14030a8fa`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x14030a8fa`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x14030a973`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x14030a973`
- `ntoskrnl!SeAppendPrivileges` at `0x14030ac96`
- `ntoskrnl!SeAppendPrivileges` at `0x14030b1db`
- `ntoskrnl!SeAppendPrivileges` at `0x14030ac96`
- `ntoskrnl!SeAppendPrivileges` at `0x14030b1db`
- `ntoskrnl!SeFreePrivileges` at `0x14030acaa`
- `ntoskrnl!SeFreePrivileges` at `0x14030aed3`
- `ntoskrnl!SeFreePrivileges` at `0x14030b01b`
- `ntoskrnl!SeFreePrivileges` at `0x14030b1ef`
- `ntoskrnl!SeFreePrivileges` at `0x14030acaa`
- `ntoskrnl!SeFreePrivileges` at `0x14030aed3`
- `ntoskrnl!SeFreePrivileges` at `0x14030b01b`
- `ntoskrnl!SeFreePrivileges` at `0x14030b1ef`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x14030aac3`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x14030aac3`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x14030b433`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x14030b433`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14030b554`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14030b5a4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14030b554`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14030b5a4`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x14030ac71`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x14030ac71`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x14030ac82`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x14030ac82`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14030b33b`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14030b33b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030b676`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030b689`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342342`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034235d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030b676`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030b689`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342342`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034235d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030abe8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030abe8`

## pseudocode

```c
void __fastcall RefsAccessCheck(
        struct _IRP_CONTEXT *a1,
        struct _CREATE_CONTEXT *a2,
        struct _FCB *a3,
        struct _FCB *a4,
        struct _IRP *a5,
        unsigned int a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        unsigned __int8 a9)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _ACCESS_STATE *v11; // rbx
  unsigned int v12; // r14d
  BOOLEAN AccessGranted; // r12
  struct _IO_STACK_LOCATION *v14; // rcx
  UCHAR MajorFunction; // al
  char v16; // si
  unsigned int v17; // r8d
  struct _ACCESS_STATE *v18; // rdi
  struct _ACCESS_REASONS *v19; // r12
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ACCESS_MASK PreviouslyGrantedAccess; // eax
  char v22; // al
  struct _FCB *v23; // rdi
  PFILE_OBJECT FileObject; // rcx
  unsigned __int16 *p_Length; // rdx
  USHORT Length; // ax
  struct _FILE_OBJECT *RelatedFileObject; // r9
  char v28; // r14
  int v29; // ecx
  int v30; // r9d
  USHORT v31; // cx
  char v32; // si
  bool v33; // di
  char *v34; // r9
  int v35; // edx
  int v36; // eax
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // rcx
  int v40; // eax
  struct _ACCESS_STATE *v41; // rsi
  _ACCESS_REASONS *v42; // rdi
  struct _GENERIC_MAPPING *v43; // rax
  unsigned __int8 v44; // si
  char v45; // dl
  struct _ACCESS_STATE *v46; // rsi
  _ACCESS_REASONS *v47; // rdi
  struct _GENERIC_MAPPING *v48; // rax
  unsigned __int8 v49; // si
  char v50; // al
  bool v51; // zf
  unsigned int v52; // eax
  struct _FCB *v53; // rdx
  struct _IRP_CONTEXT *v54; // rdi
  unsigned int v55; // edx
  struct _ACCESS_STATE *v56; // rcx
  struct _ACCESS_REASONS *v57; // r12
  struct _GENERIC_MAPPING *v58; // rax
  _DWORD *FsContext2; // rax
  char IsFastResourceHeldExclusive; // al
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // rcx
  struct _UNICODE_STRING *v62; // rcx
  struct _FILE_OBJECT *v63; // rdx
  PCUNICODE_STRING v64; // rax
  PCUNICODE_STRING v65; // rdi
  unsigned int v66; // r8d
  char RequestorMode; // al
  ULONG Options; // edx
  unsigned __int64 v69; // rax
  __int64 v70; // r8
  NTSTATUS v71; // ebx
  struct _SCB *AccessState; // [rsp+20h] [rbp-208h]
  unsigned __int8 *GenerateOnClose; // [rsp+40h] [rbp-1E8h]
  struct _ACCESS_REASONS *v74; // [rsp+58h] [rbp-1D0h]
  struct _ACCESS_REASONS *v75; // [rsp+58h] [rbp-1D0h]
  char AccessMode; // [rsp+70h] [rbp-1B8h]
  char v77; // [rsp+72h] [rbp-1B6h]
  char v78; // [rsp+73h] [rbp-1B5h]
  char v79; // [rsp+74h] [rbp-1B4h]
  bool v80; // [rsp+75h] [rbp-1B3h]
  int v81; // [rsp+78h] [rbp-1B0h] BYREF
  unsigned int v82; // [rsp+7Ch] [rbp-1ACh] BYREF
  NTSTATUS Status; // [rsp+80h] [rbp-1A8h]
  char v84; // [rsp+84h] [rbp-1A4h]
  char v85; // [rsp+85h] [rbp-1A3h]
  unsigned int v86; // [rsp+88h] [rbp-1A0h] BYREF
  unsigned int v87; // [rsp+8Ch] [rbp-19Ch] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+90h] [rbp-198h] BYREF
  struct _IRP_CONTEXT *v89; // [rsp+98h] [rbp-190h]
  int v90; // [rsp+A0h] [rbp-188h]
  int v91; // [rsp+A4h] [rbp-184h]
  int v92; // [rsp+A8h] [rbp-180h]
  unsigned int v93; // [rsp+ACh] [rbp-17Ch]
  int v94; // [rsp+B0h] [rbp-178h]
  char v95; // [rsp+B4h] [rbp-174h]
  bool v96; // [rsp+B5h] [rbp-173h]
  struct _IO_STACK_LOCATION *v97; // [rsp+B8h] [rbp-170h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-168h] BYREF
  PCUNICODE_STRING p_FileName; // [rsp+D0h] [rbp-158h]
  PVOID P[2]; // [rsp+E0h] [rbp-148h] BYREF
  PCUNICODE_STRING Source; // [rsp+F0h] [rbp-138h]
  int v102; // [rsp+F8h] [rbp-130h]
  struct _UNICODE_STRING v103; // [rsp+100h] [rbp-128h] BYREF
  struct _UNICODE_STRING SourceString; // [rsp+110h] [rbp-118h] BYREF
  struct _FCB *v105; // [rsp+120h] [rbp-108h]
  struct _ACCESS_STATE *v106; // [rsp+128h] [rbp-100h]
  struct _UNICODE_STRING v107; // [rsp+130h] [rbp-F8h] BYREF
  struct _FCB *v108; // [rsp+140h] [rbp-E8h]
  struct _FCB *v109; // [rsp+148h] [rbp-E0h]
  struct _FCB *v110; // [rsp+150h] [rbp-D8h]
  UNICODE_STRING *v111; // [rsp+158h] [rbp-D0h]
  _ACCESS_REASONS v112; // [rsp+160h] [rbp-C8h] BYREF

  *(_QWORD *)&v103.Length = a4;
  v89 = a1;
  *(_QWORD *)&SourceString.Length = a1;
  *(_QWORD *)&v107.Length = a4;
  v81 = 0;
  Status = -1073741811;
  v87 = 0;
  Privileges = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  memset(&v112, 0, sizeof(v112));
  CurrentStackLocation = a5->Tail.Overlay.CurrentStackLocation;
  v97 = CurrentStackLocation;
  v11 = *(struct _ACCESS_STATE **)(CurrentStackLocation->Parameters.WMI.ProviderId + 8);
  v106 = v11;
  if ( !a3->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(a1, a3);
  Privileges = 0;
  Source = 0;
  LOBYTE(v91) = 0;
  LOBYTE(v92) = 0;
  DestinationString.Buffer = 0;
  *(_OWORD *)P = 0;
  SeAdjustAccessStateForAccessConstraints(
    IoFileObjectType,
    (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
    v11);
  v12 = a6 & ~v11->PreviouslyGrantedAccess;
  AccessGranted = v12 == 0;
  v90 = v12 & 0x2000000;
  v102 = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 20) & 0x1000;
  if ( CurrentStackLocation )
    v14 = CurrentStackLocation;
  else
    v14 = a5->Tail.Overlay.CurrentStackLocation;
  MajorFunction = v14->MajorFunction;
  if ( !v14->MajorFunction )
  {
    if ( (v14->Flags & 1) != 0 )
    {
      AccessMode = 1;
      goto LABEL_8;
    }
    goto LABEL_147;
  }
  if ( MajorFunction == 6 )
  {
    Options = v14->Parameters.Create.Options;
    v69 = Options - 10;
    if ( (unsigned int)v69 <= 0x3E )
    {
      v70 = 0x4080000000000003LL;
      if ( _bittest64(&v70, v69) )
      {
        RequestorMode = (v14->Flags & 1) == 0;
        goto LABEL_148;
      }
    }
    if ( Options == 71 && (v14->Flags & 1) != 0 )
    {
      AccessMode = 1;
      goto LABEL_8;
    }
LABEL_147:
    RequestorMode = a5->RequestorMode;
LABEL_148:
    AccessMode = RequestorMode;
    goto LABEL_8;
  }
  if ( MajorFunction != 5 || v14->Parameters.Create.Options != 71 || (v14->Flags & 1) == 0 )
    goto LABEL_147;
  AccessMode = 1;
LABEL_8:
  v16 = SeAuditingAnyFileEventsWithContextEx(
          (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
          &v11->SubjectSecurityContext,
          0);
  v77 = v16;
  SeLockSubjectContext(&v11->SubjectSecurityContext);
  if ( !v12 )
    goto LABEL_24;
  v18 = v11;
  if ( a9 )
    v18 = 0;
  if ( v16 )
    v19 = (struct _ACCESS_REASONS *)((char *)v11->AuxData + 88);
  else
    v19 = 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  v84 = a8 != 0;
  AccessGranted = RefsSeAccessCheck(
                    v89,
                    a3,
                    &v11->SubjectSecurityContext,
                    1u,
                    a8 != 0,
                    v12,
                    v11->PreviouslyGrantedAccess,
                    &Privileges,
                    FileObjectGenericMapping,
                    AccessMode,
                    &v87,
                    v19,
                    &v81,
                    v18);
  if ( Privileges )
  {
    SeAppendPrivileges(v11, Privileges);
    SeFreePrivileges(Privileges);
    Privileges = 0;
  }
  if ( AccessGranted )
  {
    v12 &= ~(v87 | 0x2000000);
    if ( !a7 )
    {
      v11->PreviouslyGrantedAccess |= v87;
      PreviouslyGrantedAccess = v11->PreviouslyGrantedAccess;
      if ( v90 )
      {
        v35 = (unsigned __int8)v91;
        if ( (PreviouslyGrantedAccess & 0x10000) != 0 )
          v35 = 1;
        v91 = v35;
        v95 = v35;
        v51 = (PreviouslyGrantedAccess & 0x80u) == 0;
        v36 = (unsigned __int8)v92;
        if ( !v51 )
          v36 = 1;
        v92 = v36;
      }
      v11->RemainingDesiredAccess &= ~(v87 | 0x2000000);
    }
  }
  else
  {
    Status = v81;
    v94 = v81;
  }
  v22 = SeShouldCheckForAccessRightsFromParent(
          IoFileObjectType,
          (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
          v11);
  v23 = *(struct _FCB **)&v103.Length;
  if ( !*(_QWORD *)&v103.Length || !v22 || (AccessGranted || (v12 & 0x10080) == 0) && (!v90 || (_BYTE)v91 && (_BYTE)v92) )
  {
LABEL_23:
    CurrentStackLocation = v97;
    goto LABEL_24;
  }
  v78 = 0;
  v79 = 0;
  v93 = 0;
  v86 = 0;
  v82 = 0;
  SeUnlockSubjectContext(&v11->SubjectSecurityContext);
  v108 = v23;
  LOBYTE(v37) = 1;
  RefsAcquireResourceShared(v89, v23, v37);
  if ( !v23->ScavengerFinalizationList.Flink )
  {
    v109 = v23;
    RefsReleaseResource(v89, v23);
    v110 = v23;
    LOBYTE(v38) = 1;
    RefsAcquireResourceExclusive(v39, v23, v38);
  }
  SeLockSubjectContext(&v11->SubjectSecurityContext);
  if ( !v23->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(v89, v23);
  memset(&v112, 0, sizeof(v112));
  if ( (v12 & 0x10000) != 0 || (v40 = v90) != 0 && !(_BYTE)v91 )
  {
    v41 = v11;
    if ( a9 )
      v41 = 0;
    v42 = &v112;
    if ( !v77 )
      v42 = 0;
    v43 = IoGetFileObjectGenericMapping();
    v74 = v42;
    v23 = *(struct _FCB **)&v103.Length;
    v44 = RefsSeAccessCheck(
            v89,
            *(struct _FCB **)&v103.Length,
            &v11->SubjectSecurityContext,
            1u,
            1,
            0x40u,
            0,
            &Privileges,
            v43,
            AccessMode,
            &v86,
            v74,
            &v81,
            v41);
    v45 = 1;
    v78 = 1;
    if ( Privileges )
    {
      SeFreePrivileges(Privileges);
      Privileges = 0;
      v45 = 1;
    }
    if ( v44 )
    {
      v86 = v86 & 0xFFFEFFBF | 0x10000;
      v12 &= ~0x10000u;
    }
    else
    {
      Status = v81;
      v94 = v81;
    }
    v16 = v77;
    v40 = v90;
  }
  else
  {
    v45 = 0;
  }
  if ( (v12 & 0x80u) != 0 || v40 && !(_BYTE)v92 )
  {
    v46 = v11;
    if ( a9 )
      v46 = 0;
    v47 = &v112;
    if ( !v77 )
      v47 = 0;
    v48 = IoGetFileObjectGenericMapping();
    v75 = v47;
    v23 = *(struct _FCB **)&v103.Length;
    v49 = RefsSeAccessCheck(
            v89,
            *(struct _FCB **)&v103.Length,
            &v11->SubjectSecurityContext,
            1u,
            1,
            1u,
            0,
            &Privileges,
            v48,
            AccessMode,
            &v82,
            v75,
            &v81,
            v46);
    v50 = 1;
    v79 = 1;
    if ( Privileges )
    {
      SeFreePrivileges(Privileges);
      Privileges = 0;
      v50 = 1;
    }
    if ( !v49 )
    {
      Status = v81;
      v94 = v81;
      v16 = v77;
      v45 = v78;
      goto LABEL_84;
    }
    v82 = v82 & 0xFFFFFF7E | 0x80;
    v12 &= ~0x80u;
    v16 = v77;
    v45 = v78;
  }
  v50 = v79;
LABEL_84:
  if ( !v16 )
    goto LABEL_93;
  v51 = v50 == 0;
  if ( !v50 )
  {
    if ( !v45 )
      goto LABEL_93;
    v51 = 1;
  }
  v52 = v93;
  if ( !v51 )
    v52 = 128;
  v93 = v52;
  if ( v45 )
  {
    v52 |= 0x10000u;
    v93 = v52;
  }
  RefsUpdateAccessReasonSourceToParentSD(v11, &v112, v52);
LABEL_93:
  v105 = v23;
  v53 = v23;
  v54 = v89;
  RefsReleaseResource(v89, v53);
  if ( v12 )
  {
    v56 = v11;
    if ( a9 )
      v56 = 0;
    *(_QWORD *)&v103.Length = v56;
    if ( v16 )
      v57 = (struct _ACCESS_REASONS *)((char *)v11->AuxData + 88);
    else
      v57 = 0;
    v58 = IoGetFileObjectGenericMapping();
    AccessGranted = RefsSeAccessCheck(
                      v54,
                      a3,
                      &v11->SubjectSecurityContext,
                      1u,
                      v84,
                      v12,
                      0,
                      &Privileges,
                      v58,
                      AccessMode,
                      &v87,
                      v57,
                      &v81,
                      *(struct _ACCESS_STATE **)&v103.Length);
    if ( Privileges )
    {
      SeAppendPrivileges(v11, Privileges);
      SeFreePrivileges(Privileges);
      Privileges = 0;
    }
    if ( AccessGranted )
    {
      v55 = v82;
    }
    else
    {
      Status = v81;
      v94 = v81;
      v55 = v82;
      if ( v12 == 0x2000000 && (v82 || v86) )
      {
        v87 = 0;
        AccessGranted = 1;
      }
    }
  }
  else
  {
    v55 = v82;
    if ( v82 || v86 )
      AccessGranted = 1;
  }
  if ( a7 )
    goto LABEL_23;
  CurrentStackLocation = v97;
  if ( AccessGranted )
  {
    v11->PreviouslyGrantedAccess |= v87 | v86 | v55;
    v11->RemainingDesiredAccess &= ~(v87 | v86 | v55 | 0x2000000);
  }
LABEL_24:
  if ( v16 )
  {
    FileObject = CurrentStackLocation->FileObject;
    p_Length = &FileObject->FileName.Length;
    p_FileName = &FileObject->FileName;
    Length = FileObject->FileName.Length;
    LOBYTE(v17) = Length != 0;
    v80 = Length != 0;
    if ( Length || (CurrentStackLocation->Parameters.Create.Options & 0x2000) == 0 )
    {
      RelatedFileObject = FileObject->RelatedFileObject;
      if ( RelatedFileObject && (FsContext2 = RelatedFileObject->FsContext2) != 0 && (FsContext2[1] & 8) != 0 )
      {
        *(_QWORD *)&SourceString.Length = *((_QWORD *)RelatedFileObject->FsContext + 17);
        IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)&SourceString.Length + 88LL) + 64LL);
        p_SubjectSecurityContext = &v11->SubjectSecurityContext;
        if ( IsFastResourceHeldExclusive )
        {
          SeUnlockSubjectContext(p_SubjectSecurityContext);
          v28 = 0;
          *(struct _UNICODE_STRING *)P = *RefsBuildNormalizedName(
                                            &v107,
                                            v89,
                                            *(struct _FCB **)&SourceString.Length,
                                            0,
                                            AccessState);
          if ( v80 )
            RefsAppendNameToParent(v62, (struct _UNICODE_STRING *)P, (struct _UNICODE_STRING *)p_FileName);
        }
        else
        {
          SeUnlockSubjectContext(p_SubjectSecurityContext);
          v28 = 0;
          *(struct _UNICODE_STRING *)P = *RefsBuildNormalizedName(&v103, v89, a3, 0, AccessState);
        }
        LOBYTE(v17) = 1;
        v80 = 1;
        p_Length = (unsigned __int16 *)P;
        p_FileName = (PCUNICODE_STRING)P;
      }
      else
      {
        v28 = 1;
      }
    }
    else
    {
      SeUnlockSubjectContext(&v11->SubjectSecurityContext);
      v28 = 0;
      *(struct _UNICODE_STRING *)P = *RefsBuildNormalizedName(&SourceString, v89, a3, 0, AccessState);
      LOBYTE(v17) = 1;
      v80 = 1;
      p_Length = (unsigned __int16 *)P;
      p_FileName = (PCUNICODE_STRING)P;
    }
    if ( !v28 )
    {
      SeLockSubjectContext(&v11->SubjectSecurityContext);
      v16 = SeAuditingFileEventsWithContextEx(
              AccessGranted,
              (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4,
              &v11->SubjectSecurityContext,
              0);
      p_Length = &p_FileName->Length;
      v17 = v80;
    }
    if ( v16 )
    {
      *(_QWORD *)&SourceString.Length = a3->Header.FileContextSupportPointer + 102;
      v29 = **(unsigned __int16 **)&SourceString.Length;
      v30 = *p_Length;
      if ( ((v30 + v29 + 4) & 0xFFFF0000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids,
            3221225523LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741773, v89, "SecurSup.c", 0x7D9u);
        RefsRaiseStatusInternal(v89, -1073741773, v17);
      }
      else
      {
        v31 = v30 + v29 + 4;
        DestinationString.MaximumLength = v31;
        if ( (_BYTE)v17 && **((_WORD **)p_Length + 1) == 92 )
        {
          v32 = 1;
          v85 = 1;
          v33 = 0;
LABEL_38:
          DestinationString.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v31, 0x53466552u);
          RtlCopyUnicodeString(&DestinationString, *(PCUNICODE_STRING *)&SourceString.Length);
          if ( !v32 && v33 )
          {
            v65 = Source;
            RtlAppendUnicodeStringToString(&DestinationString, Source);
            if ( v65->Length != 2 )
            {
              DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 92;
              DestinationString.Length += 2;
            }
          }
          if ( v80 )
            RtlAppendUnicodeStringToString(&DestinationString, p_FileName);
          v34 = (char *)&a3->ScavengerFinalizationList.Flink[1].Flink + 4;
          GenerateOnClose = &v11->GenerateOnClose;
          if ( v102 )
            SeOpenObjectForDeleteAuditAlarm(
              (PUNICODE_STRING)&ObjectTypeName,
              0,
              &DestinationString,
              v34,
              v11,
              0,
              AccessGranted,
              AccessMode,
              GenerateOnClose);
          else
            SeOpenObjectAuditAlarm(
              (PUNICODE_STRING)&ObjectTypeName,
              0,
              &DestinationString,
              v34,
              v11,
              0,
              AccessGranted,
              AccessMode,
              GenerateOnClose);
          goto LABEL_141;
        }
      }
      v32 = 0;
      v85 = 0;
      v63 = CurrentStackLocation->FileObject->RelatedFileObject;
      if ( v63 )
      {
        v64 = &v63->FileName;
        Source = &v63->FileName;
        v111 = &v63->FileName;
      }
      else
      {
        v64 = Source;
      }
      v33 = v64 && v64->Length;
      v96 = v33;
      if ( v33 )
      {
        v31 += v64->Length;
        DestinationString.MaximumLength = v31;
      }
      goto LABEL_38;
    }
  }
LABEL_141:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  SeUnlockSubjectContext(&v11->SubjectSecurityContext);
  if ( !AccessGranted )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v71 = Status;
    }
    else
    {
      v71 = Status;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids,
          (unsigned int)Status);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v71, v89, "SecurSup.c", 0x85Du);
    RefsRaiseStatusInternal(v89, v71, v66);
    JUMPOUT(0x14034CC03LL);
  }
}

```

## disassembly

```asm
0x14030a7c0  mov     r11, rsp
0x14030a7c3  push    rbx
0x14030a7c4  push    rsi
0x14030a7c5  push    rdi
0x14030a7c6  push    r12
0x14030a7c8  push    r13
0x14030a7ca  push    r14
0x14030a7cc  push    r15
0x14030a7ce  sub     rsp, 1F0h
0x14030a7d5  mov     rax, cs:__security_cookie
0x14030a7dc  xor     rax, rsp
0x14030a7df  mov     [rsp+228h+var_48], rax
0x14030a7e7  mov     rax, r9
0x14030a7ea  mov     qword ptr [rsp+228h+var_128.Length], rax
0x14030a7f2  mov     r13, r8
0x14030a7f5  mov     [rsp+228h+var_190], rcx
0x14030a7fd  mov     qword ptr [rsp+228h+SourceString], rcx
0x14030a805  mov     qword ptr [rsp+228h+var_F8.Length], rax
0x14030a80d  mov     rsi, [rsp+228h+arg_20]
0x14030a815  xor     r14d, r14d
0x14030a818  mov     [rsp+228h+var_1B0], r14d
0x14030a81d  mov     [rsp+228h+Status], 0C000000Dh
0x14030a828  mov     [r11-19Ch], r14d
0x14030a82f  mov     [r11-198h], r14
0x14030a836  xorps   xmm0, xmm0
0x14030a839  movups  xmmword ptr [rsp+228h+DestinationString.Length], xmm0
0x14030a841  xorps   xmm1, xmm1
0x14030a844  movups  xmmword ptr [rsp+228h+P], xmm1
0x14030a84c  movups  xmmword ptr [rsp+228h+var_C8.Data], xmm0
0x14030a854  movups  xmmword ptr [rsp+228h+var_C8.Data+10h], xmm0
0x14030a85c  movups  xmmword ptr [rsp+228h+var_C8.Data+20h], xmm0
0x14030a864  movups  xmmword ptr [rsp+228h+var_C8.Data+30h], xmm0
0x14030a86c  movups  xmmword ptr [rsp+228h+var_C8.Data+40h], xmm0
0x14030a874  movups  xmmword ptr [r11-78h], xmm0
0x14030a879  movups  xmmword ptr [r11-68h], xmm0
0x14030a87e  movups  xmmword ptr [r11-58h], xmm0
0x14030a883  mov     rdi, [rsi+0B8h]
0x14030a88a  mov     [rsp+228h+var_170], rdi
0x14030a892  mov     rbx, [rdi+8]
0x14030a896  mov     rbx, [rbx+8]
0x14030a89a  mov     [rsp+228h+var_100], rbx
0x14030a8a2  cmp     [r8+0C0h], r14
0x14030a8a9  jz      loc_14030B626
0x14030a8af  mov     [rsp+228h+Privileges], r14
0x14030a8b7  mov     [rsp+228h+Source], r14
0x14030a8bf  mov     byte ptr [rsp+228h+var_184], r14b
0x14030a8c7  mov     byte ptr [rsp+228h+var_180], r14b
0x14030a8cf  mov     [rsp+228h+DestinationString.Buffer], r14
0x14030a8d7  xorps   xmm0, xmm0
0x14030a8da  movups  xmmword ptr [rsp+228h+P], xmm0
0x14030a8e2  mov     rdx, [r13+0C0h]
0x14030a8e9  add     rdx, 14h
0x14030a8ed  mov     r8, rbx
0x14030a8f0  mov     rcx, cs:__imp_IoFileObjectType
0x14030a8f7  mov     rcx, [rcx]
0x14030a8fa  call    cs:__imp_SeAdjustAccessStateForAccessConstraints
0x14030a901  nop     dword ptr [rax+rax+00h]
0x14030a906  mov     r14d, [rbx+14h]
0x14030a90a  not     r14d
0x14030a90d  and     r14d, [rsp+228h+arg_28]
0x14030a915  setz    r12b
0x14030a919  mov     eax, r14d
0x14030a91c  and     eax, 2000000h
0x14030a921  mov     [rsp+228h+var_188], eax
0x14030a928  mov     rax, [rdi+8]
0x14030a92c  mov     eax, [rax+14h]
0x14030a92f  and     eax, 1000h
0x14030a934  mov     [rsp+228h+var_130], eax
0x14030a93b  test    rdi, rdi
0x14030a93e  jz      loc_14030B633
0x14030a944  mov     rcx, rdi
0x14030a947  movzx   eax, byte ptr [rcx]
0x14030a94a  test    al, al
0x14030a94c  jnz     loc_14030B63F
0x14030a952  test    byte ptr [rcx+2], 1
0x14030a956  jz      loc_14030B619
0x14030a95c  mov     [rsp+228h+var_1B8], 1
0x14030a961  mov     rcx, [r13+0C0h]
0x14030a968  add     rcx, 14h
0x14030a96c  xor     r8d, r8d
0x14030a96f  lea     rdx, [rbx+20h]
0x14030a973  call    cs:__imp_SeAuditingAnyFileEventsWithContextEx
0x14030a97a  nop     dword ptr [rax+rax+00h]
0x14030a97f  movzx   esi, al
0x14030a982  mov     [rsp+228h+var_1B6], al
0x14030a986  lea     rcx, [rbx+20h]; SubjectContext
0x14030a98a  call    cs:__imp_SeLockSubjectContext
0x14030a991  nop     dword ptr [rax+rax+00h]
0x14030a996  mov     [rsp+228h+var_1B7], 1
0x14030a99b  test    r14d, r14d
0x14030a99e  jz      loc_14030AAFF
0x14030a9a4  mov     rdi, rbx
0x14030a9a7  xor     ecx, ecx
0x14030a9a9  cmp     [rsp+228h+arg_40], cl
0x14030a9b0  cmovnz  rdi, rcx
0x14030a9b4  test    sil, sil
0x14030a9b7  jnz     loc_14030AB20
0x14030a9bd  xor     r12d, r12d
0x14030a9c0  call    cs:__imp_IoGetFileObjectGenericMapping
0x14030a9c7  nop     dword ptr [rax+rax+00h]
0x14030a9cc  cmp     [rsp+228h+arg_38], 0
0x14030a9d4  setnz   cl
0x14030a9d7  mov     [rsp+228h+var_1A4], cl
0x14030a9de  mov     [rsp+228h+var_1C0], rdi; struct _ACCESS_STATE *
0x14030a9e3  lea     rdx, [rsp+228h+var_1B0]
0x14030a9e8  mov     [rsp+228h+var_1C8], rdx; int *
0x14030a9ed  mov     [rsp+228h+var_1D0], r12; struct _ACCESS_REASONS *
0x14030a9f2  lea     rdx, [rsp+228h+var_19C]
0x14030a9fa  mov     [rsp+228h+var_1D8], rdx; unsigned int *
0x14030a9ff  movzx   edx, [rsp+228h+var_1B8]
0x14030aa04  mov     [rsp+228h+var_1E0], dl; char
0x14030aa08  mov     [rsp+228h+GenerateOnClose], rax; struct _GENERIC_MAPPING *
0x14030aa0d  lea     rax, [rsp+228h+Privileges]
0x14030aa15  mov     qword ptr [rsp+228h+AccessMode], rax; struct _PRIVILEGE_SET **
0x14030aa1a  mov     eax, [rbx+14h]
0x14030aa1d  mov     dword ptr [rsp+228h+AccessGranted], eax; unsigned int
0x14030aa21  mov     dword ptr [rsp+228h+ObjectCreated], r14d; unsigned int
0x14030aa26  mov     byte ptr [rsp+228h+AccessState], cl; struct _SCB *
0x14030aa2a  mov     r9b, 1; unsigned __int8
0x14030aa2d  lea     r8, [rbx+20h]; struct _SECURITY_SUBJECT_CONTEXT *
0x14030aa31  mov     rdx, r13; struct _FCB *
0x14030aa34  mov     rcx, [rsp+228h+var_190]; struct _IRP_CONTEXT *
0x14030aa3c  call    ?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z; RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)
0x14030aa41  movzx   r12d, al
0x14030aa45  mov     [rsp+228h+var_1B2], al
0x14030aa49  mov     rdx, [rsp+228h+Privileges]; Privileges
0x14030aa51  test    rdx, rdx
0x14030aa54  jnz     loc_14030AC93
0x14030aa5a  test    r12b, r12b
0x14030aa5d  jz      loc_14030AB0C
0x14030aa63  mov     ecx, [rsp+228h+var_19C]
0x14030aa6a  mov     eax, ecx
0x14030aa6c  bts     eax, 19h
0x14030aa70  not     eax
0x14030aa72  and     r14d, eax
0x14030aa75  mov     [rsp+228h+arg_28], r14d
0x14030aa7d  cmp     [rsp+228h+arg_30], 0
0x14030aa85  jnz     short loc_14030AAAB
0x14030aa87  or      [rbx+14h], ecx
0x14030aa8a  mov     eax, [rbx+14h]
0x14030aa8d  cmp     [rsp+228h+var_188], 0
0x14030aa95  jnz     loc_14030ACC7
0x14030aa9b  mov     eax, [rsp+228h+var_19C]
0x14030aaa2  bts     eax, 19h
0x14030aaa6  not     eax
0x14030aaa8  and     [rbx+10h], eax
0x14030aaab  mov     rdx, [r13+0C0h]
0x14030aab2  add     rdx, 14h
0x14030aab6  mov     r8, rbx
0x14030aab9  mov     rcx, cs:__imp_IoFileObjectType
0x14030aac0  mov     rcx, [rcx]
0x14030aac3  call    cs:__imp_SeShouldCheckForAccessRightsFromParent
0x14030aaca  nop     dword ptr [rax+rax+00h]
0x14030aacf  mov     rdi, qword ptr [rsp+228h+var_128.Length]
0x14030aad7  test    rdi, rdi
0x14030aada  jz      short loc_14030AAF7
0x14030aadc  test    al, al
0x14030aade  jz      short loc_14030AAF7
0x14030aae0  test    r12b, r12b
0x14030aae3  jz      loc_14030AD06
0x14030aae9  cmp     [rsp+228h+var_188], 0
0x14030aaf1  jnz     loc_14030AD14
0x14030aaf7  mov     rdi, [rsp+228h+var_170]
0x14030aaff  test    sil, sil
0x14030ab02  jnz     short loc_14030AB2D
0x14030ab04  mov     r14b, 1
0x14030ab07  jmp     loc_14030B5B5
0x14030ab0c  mov     eax, [rsp+228h+var_1B0]
0x14030ab10  mov     [rsp+228h+Status], eax
0x14030ab17  mov     [rsp+228h+var_178], eax
0x14030ab1e  jmp     short loc_14030AAAB
0x14030ab20  mov     r12, [rbx+48h]
0x14030ab24  add     r12, 58h ; 'X'
0x14030ab28  jmp     loc_14030A9C0
0x14030ab2d  mov     rcx, [rdi+30h]
0x14030ab31  lea     rdx, [rcx+58h]
0x14030ab35  mov     [rsp+228h+var_158], rdx
0x14030ab3d  movzx   eax, word ptr [rdx]
0x14030ab40  test    ax, ax
0x14030ab43  setnz   r8b
0x14030ab47  mov     [rsp+228h+var_1B3], r8b
0x14030ab4c  test    ax, ax
0x14030ab4f  jz      loc_14030B29F
0x14030ab55  mov     r9, [rcx+40h]
0x14030ab59  test    r9, r9
0x14030ab5c  jnz     loc_14030B308
0x14030ab62  mov     r14b, 1
0x14030ab65  test    r14b, r14b
0x14030ab68  jz      loc_14030B405
0x14030ab6e  test    sil, sil
0x14030ab71  jz      loc_14030B5B5
0x14030ab77  mov     rax, [r13+50h]
0x14030ab7b  add     rax, 330h
0x14030ab81  mov     qword ptr [rsp+228h+SourceString], rax
0x14030ab89  movzx   ecx, word ptr [rax]
0x14030ab8c  movzx   r9d, word ptr [rdx]
0x14030ab90  lea     eax, [rcx+4]
0x14030ab93  add     eax, r9d
0x14030ab96  test    eax, 0FFFF0000h
0x14030ab9b  jnz     loc_14030B455
0x14030aba1  add     cx, 4
0x14030aba5  add     cx, r9w
0x14030aba9  mov     [rsp+228h+DestinationString.MaximumLength], cx
0x14030abb1  test    r8b, r8b
0x14030abb4  jz      loc_14030B4CE
0x14030abba  mov     rax, [rdx+8]
0x14030abbe  cmp     word ptr [rax], 5Ch ; '\'
0x14030abc2  jnz     loc_14030B4CE
0x14030abc8  mov     sil, 1
0x14030abcb  mov     [rsp+228h+var_1A3], sil
0x14030abd3  xor     dil, dil
0x14030abd6  movzx   edx, cx; NumberOfBytes
0x14030abd9  mov     ecx, cs:PoolType
0x14030abdf  or      ecx, 10h; PoolType
0x14030abe2  mov     r8d, 53466552h; Tag
0x14030abe8  call    cs:__imp_ExAllocatePoolWithTag
0x14030abef  nop     dword ptr [rax+rax+00h]
0x14030abf4  mov     [rsp+228h+DestinationString.Buffer], rax
0x14030abfc  mov     rdx, qword ptr [rsp+228h+SourceString]; SourceString
0x14030ac04  lea     rcx, [rsp+228h+DestinationString]; DestinationString
0x14030ac0c  call    cs:__imp_RtlCopyUnicodeString
0x14030ac13  nop     dword ptr [rax+rax+00h]
0x14030ac18  test    sil, sil
0x14030ac1b  jz      loc_14030B538
0x14030ac21  cmp     [rsp+228h+var_1B3], 0
0x14030ac26  jnz     loc_14030B594
0x14030ac2c  lea     rcx, [rbx+0Ah]
0x14030ac30  mov     r9, [r13+0C0h]
0x14030ac37  add     r9, 14h; SecurityDescriptor
0x14030ac3b  mov     [rsp+228h+GenerateOnClose], rcx; GenerateOnClose
0x14030ac40  movzx   eax, [rsp+228h+var_1B8]
0x14030ac45  lea     r8, [rsp+228h+DestinationString]; AbsoluteObjectName
0x14030ac4d  xor     edx, edx; Object
0x14030ac4f  lea     rcx, ObjectTypeName; ObjectTypeName
0x14030ac56  mov     [rsp+228h+AccessMode], al; AccessMode
0x14030ac5a  mov     [rsp+228h+AccessGranted], r12b; AccessGranted
0x14030ac5f  mov     [rsp+228h+ObjectCreated], dl; ObjectCreated
0x14030ac63  mov     [rsp+228h+AccessState], rbx; AccessState
0x14030ac68  cmp     [rsp+228h+var_130], edx
0x14030ac6f  jz      short loc_14030AC82
0x14030ac71  call    cs:__imp_SeOpenObjectForDeleteAuditAlarm
0x14030ac78  nop     dword ptr [rax+rax+00h]
0x14030ac7d  jmp     loc_14030B5B5
0x14030ac82  call    cs:__imp_SeOpenObjectAuditAlarm
0x14030ac89  nop     dword ptr [rax+rax+00h]
0x14030ac8e  jmp     loc_14030B5B5
0x14030ac93  mov     rcx, rbx; AccessState
0x14030ac96  call    cs:__imp_SeAppendPrivileges
0x14030ac9d  nop     dword ptr [rax+rax+00h]
0x14030aca2  mov     rcx, [rsp+228h+Privileges]; Privileges
0x14030acaa  call    cs:__imp_SeFreePrivileges
0x14030acb1  nop     dword ptr [rax+rax+00h]
0x14030acb6  mov     [rsp+228h+Privileges], 0
0x14030acc2  jmp     loc_14030AA5A
0x14030acc7  bt      eax, 10h
0x14030accb  mov     edx, [rsp+228h+var_184]
0x14030acd2  movzx   edx, dl
0x14030acd5  mov     ecx, 1
0x14030acda  cmovb   edx, ecx
0x14030acdd  mov     [rsp+228h+var_184], edx
0x14030ace4  mov     [rsp+228h+var_174], dl
0x14030aceb  test    al, 80h
0x14030aced  mov     eax, [rsp+228h+var_180]
0x14030acf4  movzx   eax, al
0x14030acf7  cmovnz  eax, ecx
0x14030acfa  mov     [rsp+228h+var_180], eax
0x14030ad01  jmp     loc_14030AA9B
0x14030ad06  test    r14d, 10080h
0x14030ad0d  jnz     short loc_14030AD2C
0x14030ad0f  jmp     loc_14030AAE9
0x14030ad14  cmp     byte ptr [rsp+228h+var_184], 0
0x14030ad1c  jz      short loc_14030AD2C
0x14030ad1e  cmp     byte ptr [rsp+228h+var_180], 0
0x14030ad26  jnz     loc_14030AAF7
0x14030ad2c  mov     [rsp+228h+var_1B5], 0
0x14030ad31  mov     [rsp+228h+var_1B4], 0
0x14030ad36  mov     [rsp+228h+var_17C], 0
0x14030ad41  mov     [rsp+228h+var_1A0], 0
0x14030ad4c  mov     [rsp+228h+var_1AC], 0
0x14030ad54  lea     rcx, [rbx+20h]; SubjectContext
0x14030ad58  call    cs:__imp_SeUnlockSubjectContext
0x14030ad5f  nop     dword ptr [rax+rax+00h]
0x14030ad64  mov     [rsp+228h+var_1B7], 0
0x14030ad69  mov     [rsp+228h+var_E8], rdi
0x14030ad71  mov     r8b, 1
0x14030ad74  mov     rdx, rdi
0x14030ad77  mov     rcx, [rsp+228h+var_190]
0x14030ad7f  call    ?RefsAcquireResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquireResourceShared(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x14030ad84  cmp     qword ptr [rdi+0C0h], 0
0x14030ad8c  jnz     short loc_14030ADB9
0x14030ad8e  mov     [rsp+228h+var_E0], rdi
0x14030ad96  mov     rdx, rdi
0x14030ad99  mov     rcx, [rsp+228h+var_190]
0x14030ada1  call    ?RefsReleaseResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleaseResource(_IRP_CONTEXT *,PFCBOrSCB)
0x14030ada6  mov     [rsp+228h+var_D8], rdi
0x14030adae  mov     r8b, 1
0x14030adb1  mov     rdx, rdi
0x14030adb4  call    ?RefsAcquireResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquireResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x14030adb9  lea     rcx, [rbx+20h]; SubjectContext
0x14030adbd  call    cs:__imp_SeLockSubjectContext
  ... truncated ...
```
