# NtfsAccessCheck

- ea: `0x140185c50`
- end: `0x140187564`
- name: `NtfsAccessCheck`
- size: `6420`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1401a0e20`
- `0x1401a2d00`
- `0x140221e50`
- `0x1402376fc`
- `0x14029c204`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x1400592c0`
- `0x140059740`
- `0x1401856a0`
- `0x140185c50`
- `0x14018756c`
- `0x1401875c0`
- `0x140188078`
- `0x140188bc0`
- `0x140199140`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140186b4d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140186b4d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140186b81`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140186f7a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140186b81`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140186f7a`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401871d9`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1401871d9`
- `ntoskrnl!IoFileObjectType` at `0x140185d8f`
- `ntoskrnl!IoFileObjectType` at `0x140186005`
- `ntoskrnl!SeLockSubjectContext` at `0x140185e50`
- `ntoskrnl!SeLockSubjectContext` at `0x1401861b6`
- `ntoskrnl!SeLockSubjectContext` at `0x140186a86`
- `ntoskrnl!SeLockSubjectContext` at `0x140185e50`
- `ntoskrnl!SeLockSubjectContext` at `0x1401861b6`
- `ntoskrnl!SeLockSubjectContext` at `0x140186a86`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14018615e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140186910`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401869e1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401873bc`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1402aac5e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14018615e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140186910`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401869e1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401873bc`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1402aac5e`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x140185d99`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x140185d99`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x140185e1b`
- `ntoskrnl!SeAuditingAnyFileEventsWithContextEx` at `0x140185e1b`
- `ntoskrnl!SeAppendPrivileges` at `0x140185f75`
- `ntoskrnl!SeAppendPrivileges` at `0x140186881`
- `ntoskrnl!SeAppendPrivileges` at `0x140185f75`
- `ntoskrnl!SeAppendPrivileges` at `0x140186881`
- `ntoskrnl!SeFreePrivileges` at `0x140185f89`
- `ntoskrnl!SeFreePrivileges` at `0x140186324`
- `ntoskrnl!SeFreePrivileges` at `0x1401865c7`
- `ntoskrnl!SeFreePrivileges` at `0x140186895`
- `ntoskrnl!SeFreePrivileges` at `0x140185f89`
- `ntoskrnl!SeFreePrivileges` at `0x140186324`
- `ntoskrnl!SeFreePrivileges` at `0x1401865c7`
- `ntoskrnl!SeFreePrivileges` at `0x140186895`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x14018600f`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x14018600f`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x140186abc`
- `ntoskrnl!SeAuditingFileEventsWithContextEx` at `0x140186abc`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarmWithTransaction` at `0x14018703d`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarmWithTransaction` at `0x14018703d`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x140186e44`
- `ntoskrnl!SeOpenObjectForDeleteAuditAlarm` at `0x140186e44`
- `ntoskrnl!SeOpenObjectAuditAlarmWithTransaction` at `0x140186f42`
- `ntoskrnl!SeOpenObjectAuditAlarmWithTransaction` at `0x140186f42`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x140186cfe`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x140186cfe`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x1401872d2`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x14018736c`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x1401872d2`
- `ntoskrnl!SeAuditTransactionStateChange` at `0x14018736c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140185ebc`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140186274`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140186517`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401867d1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140185ebc`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140186274`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140186517`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401867d1`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140186e5e`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140186e5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018738c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401873a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402aac22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402aac3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018738c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401873a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402aac22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402aac3d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140186b29`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140186b29`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140186e8f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187263`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401872fd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140186e8f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187263`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401872fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401866b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187298`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187332`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aabe6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401866b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187298`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187332`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aabe6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401869c9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1401869c9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401861a6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401861a6`
- `ntoskrnl!ExRaiseStatus` at `0x140186d41`
- `ntoskrnl!ExRaiseStatus` at `0x140186d76`
- `ntoskrnl!ExRaiseStatus` at `0x140186d41`
- `ntoskrnl!ExRaiseStatus` at `0x140186d76`

## pseudocode

```c
void __fastcall NtfsAccessCheck(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        const UNICODE_STRING *a4,
        __int64 a5,
        int a6,
        unsigned __int8 a7,
        char a8,
        char a9)
{
  unsigned int v11; // edi
  __int64 v12; // r12
  struct _ACCESS_STATE *AccessState; // rbx
  int v14; // esi
  char *v15; // rcx
  char v16; // al
  char v17; // r12
  char v18; // r12
  __int64 v19; // rcx
  __int64 v20; // rax
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  BOOLEAN v22; // al
  ACCESS_MASK PreviouslyGrantedAccess; // eax
  char v24; // al
  BOOLEAN v25; // r14
  __int64 v26; // r8
  unsigned __int16 *p_Length; // rdx
  __int16 v28; // ax
  __int64 v29; // rcx
  int Length; // ecx
  int v31; // r8d
  const UNICODE_STRING *v32; // r12
  const UNICODE_STRING *Buffer; // rcx
  int v34; // eax
  __int64 v35; // rcx
  _OWORD *v36; // rcx
  PGENERIC_MAPPING v37; // rax
  char v38; // al
  bool v39; // zf
  int v40; // r11d
  __int64 v41; // r10
  unsigned int v42; // r8d
  _DWORD *v43; // rcx
  unsigned int v44; // r9d
  _DWORD *v45; // rdx
  int v46; // eax
  int v47; // r9d
  __int64 v48; // rcx
  _OWORD *v49; // rcx
  PGENERIC_MAPPING v50; // rax
  char v51; // al
  struct _ERESOURCE *v52; // rcx
  int v53; // edx
  char v54; // al
  __int64 v55; // rcx
  __int64 v56; // rax
  PGENERIC_MAPPING v57; // rax
  __int64 v58; // rax
  USHORT v59; // cx
  __int64 *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rdx
  PCUNICODE_STRING v63; // r10
  __int64 v64; // r8
  int v65; // eax
  unsigned int v66; // ecx
  void *v67; // r9
  __int64 v68; // rdx
  const UNICODE_STRING *v69; // rdx
  bool v70; // al
  void *v71; // r9
  const UNICODE_STRING *v72; // rcx
  void *v73; // r9
  void *v74; // r9
  void *v75; // r8
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // rcx
  char *AuxData; // rax
  int v80; // edx
  unsigned __int64 v81; // rax
  __int64 v82; // r8
  char AccessMode; // [rsp+80h] [rbp-1D8h]
  BOOLEAN AccessGranted; // [rsp+81h] [rbp-1D7h]
  char v85; // [rsp+83h] [rbp-1D5h]
  char v86; // [rsp+83h] [rbp-1D5h]
  char v87; // [rsp+83h] [rbp-1D5h]
  char v88; // [rsp+84h] [rbp-1D4h]
  bool v89; // [rsp+85h] [rbp-1D3h]
  char v90; // [rsp+86h] [rbp-1D2h]
  char v91; // [rsp+87h] [rbp-1D1h]
  char v92; // [rsp+88h] [rbp-1D0h]
  char v93; // [rsp+8Ah] [rbp-1CEh] BYREF
  bool v94; // [rsp+8Bh] [rbp-1CDh]
  char v95; // [rsp+8Ch] [rbp-1CCh]
  char v96; // [rsp+8Dh] [rbp-1CBh]
  int v97; // [rsp+90h] [rbp-1C8h]
  unsigned int v98; // [rsp+94h] [rbp-1C4h] BYREF
  char v99; // [rsp+98h] [rbp-1C0h]
  PPRIVILEGE_SET Privileges; // [rsp+A0h] [rbp-1B8h] BYREF
  int v101; // [rsp+A8h] [rbp-1B0h] BYREF
  __int64 v102; // [rsp+B0h] [rbp-1A8h]
  __int64 v103; // [rsp+B8h] [rbp-1A0h] BYREF
  __int64 v104; // [rsp+C0h] [rbp-198h] BYREF
  __int64 v105; // [rsp+C8h] [rbp-190h]
  const UNICODE_STRING *v106; // [rsp+D0h] [rbp-188h]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-180h] BYREF
  char v108; // [rsp+E8h] [rbp-170h]
  char v109; // [rsp+E9h] [rbp-16Fh]
  bool v110; // [rsp+EAh] [rbp-16Eh]
  unsigned int v111; // [rsp+ECh] [rbp-16Ch]
  int v112; // [rsp+F0h] [rbp-168h]
  __int64 v113; // [rsp+F8h] [rbp-160h]
  unsigned int v114; // [rsp+100h] [rbp-158h]
  int v115; // [rsp+104h] [rbp-154h]
  PCUNICODE_STRING Source; // [rsp+108h] [rbp-150h]
  _OWORD *v117; // [rsp+110h] [rbp-148h]
  PCUNICODE_STRING SourceString; // [rsp+118h] [rbp-140h]
  PCUNICODE_STRING v119; // [rsp+120h] [rbp-138h]
  PVOID P[2]; // [rsp+128h] [rbp-130h] BYREF
  int v121; // [rsp+138h] [rbp-120h]
  __int64 v122; // [rsp+140h] [rbp-118h]
  _OWORD *v123; // [rsp+148h] [rbp-110h]
  _DWORD v124[2]; // [rsp+150h] [rbp-108h]
  int v125; // [rsp+158h] [rbp-100h]
  _DWORD v126[3]; // [rsp+15Ch] [rbp-FCh]
  __int64 v127; // [rsp+168h] [rbp-F0h]
  __int64 v128; // [rsp+170h] [rbp-E8h]
  struct _ACCESS_STATE *v129; // [rsp+178h] [rbp-E0h]
  const UNICODE_STRING *v130; // [rsp+180h] [rbp-D8h]
  _OWORD v131[8]; // [rsp+190h] [rbp-C8h] BYREF

  v106 = a4;
  v113 = a2;
  SourceString = a4;
  v98 = 0;
  v11 = 0;
  v93 = 0;
  v102 = 0;
  v101 = 0;
  Privileges = 0;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  v94 = 0;
  memset(v131, 0, sizeof(v131));
  v12 = *(_QWORD *)(a5 + 184);
  v122 = v12;
  AccessState = *(struct _ACCESS_STATE **)(*(_QWORD *)(v12 + 8) + 8LL);
  v129 = AccessState;
  if ( !a3[26] )
    NtfsLoadSecurityDescriptor(a1, a3);
  Privileges = 0;
  v119 = 0;
  v90 = 0;
  v91 = 0;
  DestinationString.Buffer = 0;
  *(_OWORD *)P = 0;
  SeAdjustAccessStateForAccessConstraints(IoFileObjectType, a3[26] + 28LL, AccessState);
  v14 = a6 & ~AccessState->PreviouslyGrantedAccess;
  AccessGranted = v14 == 0;
  v97 = v14 & 0x2000000;
  v121 = *(_DWORD *)(*(_QWORD *)(v12 + 8) + 20LL) & 0x1000;
  v15 = *(char **)(a5 + 184);
  v16 = *v15;
  if ( !*v15 )
  {
    if ( (v15[2] & 1) == 0 )
      goto LABEL_5;
    AccessMode = 1;
    goto LABEL_7;
  }
  if ( v16 == 13 )
  {
    if ( !*(_BYTE *)(a5 + 64) && v15[1] == 4 )
    {
      AccessMode = 0;
      goto LABEL_7;
    }
LABEL_259:
    AccessMode = 1;
    goto LABEL_7;
  }
  if ( v16 != 6 )
  {
    if ( v16 != 5 || *((_DWORD *)v15 + 4) != 71 || (v15[2] & 1) == 0 )
      goto LABEL_5;
    goto LABEL_259;
  }
  v80 = *((_DWORD *)v15 + 4);
  v81 = (unsigned int)(v80 - 10);
  if ( (unsigned int)v81 <= 0x3E )
  {
    v82 = 0x4080000000000003LL;
    if ( _bittest64(&v82, v81) )
    {
      v17 = (v15[2] & 1) == 0;
      goto LABEL_6;
    }
  }
  if ( v80 != 71 || (v15[2] & 1) == 0 )
  {
LABEL_5:
    v17 = *(_BYTE *)(a5 + 64);
LABEL_6:
    AccessMode = v17;
    goto LABEL_7;
  }
  AccessMode = 1;
LABEL_7:
  v85 = SeAuditingAnyFileEventsWithContextEx(a3[26] + 28LL, &AccessState->SubjectSecurityContext, &v93);
  if ( v85 || (v88 = 0, v93) )
    v88 = 1;
  SeLockSubjectContext(&AccessState->SubjectSecurityContext);
  v18 = 1;
  if ( !v14 )
    goto LABEL_26;
  v19 = (__int64)AccessState;
  v20 = 0;
  if ( a9 )
    v19 = 0;
  v105 = v19;
  if ( v88 )
    v20 = (__int64)AccessState->AuxData + 88;
  v104 = v20;
  if ( v113 )
    v103 = *(_QWORD *)(v113 + 184);
  else
    v103 = 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  v99 = a8 != 0;
  v22 = TxfAccessCheck(
          a1,
          v103,
          (_DWORD)a3,
          (int)AccessState + 32,
          1,
          a8 != 0,
          v14,
          AccessState->PreviouslyGrantedAccess,
          (__int64)&Privileges,
          (__int64)FileObjectGenericMapping,
          AccessMode,
          (__int64)&v101,
          v104,
          (__int64)&v98,
          v105);
  AccessGranted = v22;
  if ( Privileges )
  {
    SeAppendPrivileges(AccessState, Privileges);
    SeFreePrivileges(Privileges);
    Privileges = 0;
    v22 = AccessGranted;
  }
  if ( v22 )
  {
    v14 &= ~(v101 | 0x2000000);
    if ( !a7 )
    {
      AccessState->PreviouslyGrantedAccess |= v101;
      PreviouslyGrantedAccess = AccessState->PreviouslyGrantedAccess;
      if ( v97 )
      {
        if ( (PreviouslyGrantedAccess & 0x10000) != 0 )
        {
          v90 = 1;
          v108 = 1;
        }
        if ( (PreviouslyGrantedAccess & 0x80u) != 0 )
          v91 = 1;
      }
      AccessState->RemainingDesiredAccess &= ~(v101 | 0x2000000);
    }
  }
  else
  {
    v11 = v98;
    v111 = v98;
  }
  v24 = SeShouldCheckForAccessRightsFromParent(IoFileObjectType, a3[26] + 28LL, AccessState);
  if ( !v106 || !v24 )
    goto LABEL_26;
  if ( AccessGranted )
    goto LABEL_25;
  while ( 1 )
  {
    if ( (v14 & 0x10080) == 0 )
    {
LABEL_25:
      if ( !v97 || v90 && v91 )
      {
LABEL_26:
        v14 = a7;
        goto LABEL_27;
      }
    }
    v92 = 0;
    v95 = 0;
    v112 = 0;
    LODWORD(v104) = 0;
    LODWORD(v103) = 0;
    SeUnlockSubjectContext(&AccessState->SubjectSecurityContext);
    v32 = v106;
    if ( *(_QWORD *)&v106[13].Length || ExIsResourceAcquiredSharedLite((PERESOURCE)(v106[6].Buffer + 32)) )
    {
      if ( v32->Length == 1794 )
        Buffer = v32;
      else
        Buffer = (const UNICODE_STRING *)v32[11].Buffer;
      ExAcquireResourceSharedLite((PERESOURCE)(Buffer[6].Buffer + 32), 1u);
    }
    else
    {
      if ( v32->Length == 1794 )
        v72 = v32;
      else
        v72 = (const UNICODE_STRING *)v32[11].Buffer;
      ExAcquireResourceExclusiveLite((PERESOURCE)(v72[6].Buffer + 32), 1u);
    }
    SeLockSubjectContext(&AccessState->SubjectSecurityContext);
    v18 = 1;
    if ( !*(_QWORD *)&v106[13].Length )
      NtfsLoadSecurityDescriptor(a1, v106);
    memset(v131, 0, sizeof(v131));
    if ( (v14 & 0x10000) != 0 || (v34 = v97) != 0 && !v90 )
    {
      v48 = (__int64)AccessState;
      if ( a9 )
        v48 = 0;
      v123 = (_OWORD *)v48;
      v49 = v131;
      if ( !v88 )
        v49 = 0;
      v117 = v49;
      if ( v113 )
        v105 = *(_QWORD *)(v113 + 184);
      else
        v105 = 0;
      v50 = IoGetFileObjectGenericMapping();
      v51 = TxfAccessCheck(
              a1,
              v105,
              (_DWORD)v106,
              (int)AccessState + 32,
              1,
              1,
              64,
              0,
              (__int64)&Privileges,
              (__int64)v50,
              AccessMode,
              (__int64)&v104,
              (__int64)v117,
              (__int64)&v98,
              (__int64)v123);
      v90 = v51;
      v92 = 1;
      if ( Privileges )
      {
        SeFreePrivileges(Privileges);
        Privileges = 0;
        v51 = v90;
      }
      if ( v51 )
      {
        LODWORD(v104) = v104 & 0xFFFEFFBF | 0x10000;
        v14 &= ~0x10000u;
      }
      else
      {
        v11 = v98;
        v111 = v98;
      }
      v34 = v97;
    }
    if ( (v14 & 0x80u) != 0 || v34 && !v91 )
    {
      v35 = (__int64)AccessState;
      if ( a9 )
        v35 = 0;
      v117 = (_OWORD *)v35;
      v36 = v131;
      if ( !v88 )
        v36 = 0;
      v123 = v36;
      if ( v113 )
        v105 = *(_QWORD *)(v113 + 184);
      else
        v105 = 0;
      v37 = IoGetFileObjectGenericMapping();
      v38 = TxfAccessCheck(
              a1,
              v105,
              (_DWORD)v106,
              (int)AccessState + 32,
              1,
              1,
              1,
              0,
              (__int64)&Privileges,
              (__int64)v37,
              AccessMode,
              (__int64)&v103,
              (__int64)v123,
              (__int64)&v98,
              (__int64)v117);
      v91 = v38;
      v95 = 1;
      if ( Privileges )
      {
        SeFreePrivileges(Privileges);
        Privileges = 0;
        v38 = v91;
      }
      if ( v38 )
      {
        LODWORD(v103) = v103 & 0xFFFFFF7E | 0x80;
        v14 &= ~0x80u;
      }
      else
      {
        v11 = v98;
        v111 = v98;
      }
    }
    if ( v88 )
    {
      v39 = v95 == 0;
      if ( v95 )
        goto LABEL_62;
      if ( v92 )
      {
        v39 = 1;
LABEL_62:
        v40 = v112;
        if ( !v39 )
          v40 = 128;
        v112 = v40;
        if ( v92 )
        {
          v40 |= 0x10000u;
          v112 = v40;
        }
        v124[0] = 0x10000;
        v124[1] = 64;
        v125 = 16;
        v126[0] = 6;
        v126[1] = 128;
        v126[2] = 1;
        v127 = 7;
        v41 = (__int64)AccessState->AuxData + 88;
        v114 = 0;
        v42 = 0;
        while ( 2 )
        {
          v114 = v42;
          if ( v42 >= 2 )
            goto LABEL_98;
          if ( (v40 & v124[4 * v42]) == 0 )
            goto LABEL_88;
          v43 = (_DWORD *)v131 + (unsigned int)v126[4 * v42];
          v44 = *v43 & 0xFF00FFFF;
          v45 = (_DWORD *)(v41 + 4LL * (unsigned int)v126[4 * v42 - 1]);
          *v45 = v44;
          v46 = *v43 & 0xFF0000;
          switch ( v46 )
          {
            case 65536:
              v47 = v44 | 0x30000;
              break;
            case 131072:
              v47 = v44 | 0x40000;
              break;
            case 327680:
              v47 = v44 | 0x60000;
              break;
            default:
LABEL_88:
              ++v42;
              continue;
          }
          break;
        }
        *v45 = v47;
        goto LABEL_88;
      }
    }
LABEL_98:
    if ( v106->Length == 1794 )
      v52 = (struct _ERESOURCE *)(v106[6].Buffer + 32);
    else
      v52 = (struct _ERESOURCE *)v106->Buffer;
    ExReleaseResourceLite(v52);
    if ( !v14 )
    {
      v53 = v103;
      if ( !(_DWORD)v103 && !(_DWORD)v104 )
      {
        v54 = AccessGranted;
        goto LABEL_103;
      }
      goto LABEL_102;
    }
    v55 = (__int64)AccessState;
    v56 = 0;
    if ( a9 )
      v55 = 0;
    v117 = (_OWORD *)v55;
    if ( v88 )
      v56 = (__int64)AccessState->AuxData + 88;
    v105 = v56;
    if ( v113 )
      v106 = *(const UNICODE_STRING **)(v113 + 184);
    else
      v106 = 0;
    v57 = IoGetFileObjectGenericMapping();
    v54 = TxfAccessCheck(
            a1,
            (_DWORD)v106,
            (_DWORD)a3,
            (int)AccessState + 32,
            1,
            v99,
            v14,
            0,
            (__int64)&Privileges,
            (__int64)v57,
            AccessMode,
            (__int64)&v101,
            v105,
            (__int64)&v98,
            (__int64)v117);
    AccessGranted = v54;
    if ( Privileges )
    {
      SeAppendPrivileges(AccessState, Privileges);
      SeFreePrivileges(Privileges);
      Privileges = 0;
      v54 = AccessGranted;
    }
    if ( v54 )
    {
      v53 = v103;
      goto LABEL_103;
    }
    v11 = v98;
    v111 = v98;
    v53 = v103;
    if ( v14 == 0x2000000 && ((_DWORD)v103 || (_DWORD)v104) )
    {
      v101 = 0;
LABEL_102:
      v54 = 1;
      AccessGranted = 1;
    }
LABEL_103:
    v14 = a7;
    if ( !a7 && v54 )
    {
      AccessState->PreviouslyGrantedAccess |= v101 | v104 | v53;
      AccessState->RemainingDesiredAccess &= ~(v101 | v104 | v53 | 0x2000000);
    }
LABEL_27:
    if ( !v88 )
    {
      v25 = AccessGranted;
      goto LABEL_228;
    }
    v26 = *(_QWORD *)(v122 + 48);
    p_Length = (unsigned __int16 *)(v26 + 88);
    Source = (PCUNICODE_STRING)(v26 + 88);
    v28 = *(_WORD *)(v26 + 88);
    v89 = v28 != 0;
    if ( !v28 && (*(_DWORD *)(v122 + 16) & 0x2000) != 0 )
    {
LABEL_125:
      SeUnlockSubjectContext(&AccessState->SubjectSecurityContext);
      v18 = 0;
      NtfsBuildNormalizedNameWithTxfIsolation(a1, (_DWORD)a3, 0, 0, 0, 0, (__int64)P);
LABEL_126:
      v89 = 1;
      p_Length = (unsigned __int16 *)P;
      Source = (PCUNICODE_STRING)P;
      goto LABEL_32;
    }
    v29 = *(_QWORD *)(v26 + 64);
    if ( v29 )
    {
      v58 = *(_QWORD *)(v29 + 32);
      if ( v58 )
      {
        if ( (*(_DWORD *)(v58 + 4) & 8) != 0 )
        {
          if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v29 + 24) + 184LL)
                                                                         + 104LL)
                                                             + 64LL)) )
            goto LABEL_125;
          SeUnlockSubjectContext(&AccessState->SubjectSecurityContext);
          v18 = 0;
          NtfsBuildNormalizedNameWithTxfIsolation(
            a1,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v122 + 48) + 64LL) + 24LL) + 184LL),
            0,
            0,
            0,
            0,
            (__int64)P);
          if ( !v89 )
            goto LABEL_126;
          NtfsAppendNameToParent(0, P, Source);
          v89 = 1;
          p_Length = (unsigned __int16 *)P;
          Source = (PCUNICODE_STRING)P;
        }
      }
    }
LABEL_32:
    if ( !v18 )
    {
      SeLockSubjectContext(&AccessState->SubjectSecurityContext);
      v18 = 1;
      v85 = SeAuditingFileEventsWithContextEx(AccessGranted, a3[26] + 28LL, &AccessState->SubjectSecurityContext, &v93);
      v109 = v85;
      p_Length = &Source->Length;
    }
    SourceString = (PCUNICODE_STRING)(a3[12] + 7856LL);
    Length = SourceString->Length;
    v31 = *p_Length;
    if ( ((v31 + Length + 4) & 0xFFFF0000) == 0 )
      break;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225523LL, 2034561);
    NtfsRaiseStatusInternal(a1, -1073741773, 0, 0, 2034561);
  }
  v59 = v31 + Length + 4;
  DestinationString.MaximumLength = v59;
  if ( v89 && **((_WORD **)p_Length + 1) == 92 )
  {
    v96 = 1;
  }
  else
  {
    v96 = 0;
    v68 = *(_QWORD *)(*(_QWORD *)(v122 + 48) + 64LL);
    if ( v68 )
    {
      v69 = (const UNICODE_STRING *)(v68 + 88);
      v119 = v69;
      v130 = v69;
    }
    else
    {
      v69 = v119;
    }
    v70 = v69 && v69->Length;
    v94 = v70;
    v110 = v70;
    if ( v70 )
    {
      v59 += v69->Length;
      DestinationString.MaximumLength = v59;
    }
  }
  DestinationString.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v59, 0x5346744Eu);
  RtlCopyUnicodeString(&DestinationString, SourceString);
  if ( !v96 && v94 )
  {
    RtlAppendUnicodeStringToString(&DestinationString, v119);
    if ( v119->Length != 2 )
    {
      DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 92;
      DestinationString.Length += 2;
    }
  }
  if ( v89 )
    RtlAppendUnicodeStringToString(&DestinationString, Source);
  if ( v85 )
  {
    v60 = (__int64 *)(a1 + 400);
    v61 = *(_QWORD *)(a1 + 400);
    v102 = v61;
    if ( !v61 )
    {
      v61 = a3[41];
      if ( v61 )
        v61 = *(_QWORD *)(v61 + 24);
      v102 = v61;
    }
    v128 = v61;
    if ( !v61 )
    {
      v62 = v113;
      if ( v113 )
      {
        if ( *(_QWORD *)(v113 + 184) )
        {
          v63 = (PCUNICODE_STRING)a3[40];
          SourceString = v63;
          if ( _InterlockedCompareExchange((volatile signed __int32 *)(&v63[8].MaximumLength + 1), 4, 4) != 2 )
          {
            v75 = *(void **)(v62 + 184);
            if ( v75 )
            {
              v76 = a3[12];
              if ( (*(_DWORD *)(v76 + 4) & 0x2000000) == 0 )
              {
                if ( (*(_DWORD *)(v76 + 24) & 0x100000) == 0 )
                {
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(a1, 3222863877LL, 2624073);
                  NtfsRaiseStatusInternal(a1, -1072103419, (_DWORD)a3 + 8, (_DWORD)a3, 2624073);
                  __debugbreak();
                }
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(a1, 3221225659LL, 2624069);
                NtfsRaiseStatusInternal(a1, -1073741637, (_DWORD)a3 + 8, (_DWORD)a3, 2624069);
                __debugbreak();
              }
              ObDereferenceObjectDeferDelete(v75);
              v62 = v113;
              *(_QWORD *)(v113 + 184) = 0;
              v60 = (__int64 *)(a1 + 400);
              v63 = SourceString;
            }
          }
          v64 = *(_QWORD *)(v62 + 184);
          if ( v64 )
          {
            v115 = 0;
            if ( !*v60 )
            {
              v65 = TxfTransMgrSearchAddTrans(v63, 0, v64, 50, a1, v60);
              v66 = v65;
              v97 = v65;
              v115 = v65;
              if ( v65 == 29 )
              {
                TxfPostTransactionRelatedWorkItem(a1, 256, *(_QWORD *)(a1 + 400), 0, 0);
                ExRaiseStatus(-1073741608);
              }
              if ( v65 == 30 )
              {
                TxfPostTransactionRelatedWorkItem(a1, 1024, *(_QWORD *)(a1 + 400), 0, 0);
                ExRaiseStatus(-1073741608);
              }
              if ( v65 < 0 )
              {
                if ( (*(_DWORD *)(a1 + 436) & 0x100) != 0 && v65 != -1072037844 )
                {
                  if ( NtfsStatusDebugFlags )
                  {
                    v97 = -1072103421;
                    NtfsStatusTraceAndDebugInternal(0, 3222863875LL, 3213202);
                    v66 = -1072103421;
                  }
                  else
                  {
                    v66 = -1072103421;
                    v97 = -1072103421;
                  }
                  v115 = -1072103421;
                }
                *(_QWORD *)(a1 + 400) = 0;
                if ( NtfsStatusDebugFlags
                  && v66
                  && v66 != 294
                  && v66 - 298 > 1
                  && v66 < 0xFFFFFFED
                  && v66 != -1073741608
                  && v66 != -1073741802
                  && v66 != -1073741807
                  && v66 + 2147483643 > 1
                  && v66 != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(a1, v66, 3213207);
                  v66 = v97;
                }
                NtfsRaiseStatusInternal(a1, v66, 0, 0, 3213207);
                __debugbreak();
              }
              v60 = (__int64 *)(a1 + 400);
            }
          }
          v61 = *v60;
          v102 = v61;
          v128 = v61;
        }
      }
    }
  }
  else
  {
    v61 = v102;
  }
  if ( v121 )
  {
    if ( v61 )
    {
      if ( (*(_DWORD *)(v61 + 16) & 0x40000) == 0 )
      {
        v86 = 0;
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v102 + 24) + 80LL), 1u);
        v77 = v102;
        if ( (*(_DWORD *)(v102 + 16) & 0x40000) == 0 )
        {
          _InterlockedOr((volatile signed __int32 *)(v102 + 16), 0x40000u);
          v86 = 1;
        }
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v77 + 24) + 80LL));
        if ( v86 )
          SeAuditTransactionStateChange((GUID *)(v102 + 256), (GUID *)(*(_QWORD *)(v102 + 208) + 672LL), 0);
      }
      v74 = (void *)(a3[26] + 28LL);
      v25 = AccessGranted;
      SeOpenObjectForDeleteAuditAlarmWithTransaction(
        &FileString,
        0,
        &DestinationString,
        v74,
        AccessState,
        0,
        AccessGranted,
        AccessMode,
        (GUID *)(v102 + 256),
        &AccessState->GenerateOnClose);
    }
    else
    {
      v71 = (void *)(a3[26] + 28LL);
      v25 = AccessGranted;
      SeOpenObjectForDeleteAuditAlarm(
        &FileString,
        0,
        &DestinationString,
        v71,
        AccessState,
        0,
        AccessGranted,
        AccessMode,
        &AccessState->GenerateOnClose);
    }
  }
  else if ( v61 )
  {
    if ( (*(_DWORD *)(v61 + 16) & 0x40000) == 0 )
    {
      v87 = 0;
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v102 + 24) + 80LL), 1u);
      v78 = v102;
      if ( (*(_DWORD *)(v102 + 16) & 0x40000) == 0 )
      {
        _InterlockedOr((volatile signed __int32 *)(v102 + 16), 0x40000u);
        v87 = 1;
      }
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v78 + 24) + 80LL));
      if ( v87 )
        SeAuditTransactionStateChange((GUID *)(v102 + 256), (GUID *)(*(_QWORD *)(v102 + 208) + 672LL), 0);
    }
    v73 = (void *)(a3[26] + 28LL);
    v25 = AccessGranted;
    SeOpenObjectAuditAlarmWithTransaction(
      &FileString,
      0,
      &DestinationString,
      v73,
      AccessState,
      0,
      AccessGranted,
      AccessMode,
      (GUID *)(v102 + 256),
      &AccessState->GenerateOnClose);
  }
  else
  {
    v67 = (void *)(a3[26] + 28LL);
    v25 = AccessGranted;
    SeOpenObjectAuditAlarm(
      &FileString,
      0,
      &DestinationString,
      v67,
      AccessState,
      0,
      AccessGranted,
      AccessMode,
      &AccessState->GenerateOnClose);
  }
LABEL_228:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  SeUnlockSubjectContext(&AccessState->SubjectSecurityContext);
  if ( (_BYTE)v14 )
  {
    AuxData = (char *)AccessState->AuxData;
    *(_OWORD *)(AuxData + 88) = 0;
    *(_OWORD *)(AuxData + 104) = 0;
    *(_OWORD *)(AuxData + 120) = 0;
    *(_OWORD *)(AuxData + 136) = 0;
    *(_OWORD *)(AuxData + 152) = 0;
    *(_OWORD *)(AuxData + 168) = 0;
    *(_OWORD *)(AuxData + 184) = 0;
    *(_OWORD *)(AuxData + 200) = 0;
  }
  if ( !v25 )
  {
    if ( NtfsStatusDebugFlags
      && v11
      && v11 != 294
      && v11 - 298 > 1
      && v11 < 0xFFFFFFED
      && v11 != -1073741608
      && v11 != -1073741802
      && v11 != -1073741807
      && v11 + 2147483643 > 1
      && v11 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v11, 2034760);
    }
    NtfsRaiseStatusInternal(a1, v11, 0, 0, 2034760);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x140185c50  mov     r11, rsp
0x140185c53  push    rbx
0x140185c54  push    rsi
0x140185c55  push    rdi
0x140185c56  push    r12
0x140185c58  push    r13
0x140185c5a  push    r14
0x140185c5c  push    r15
0x140185c5e  sub     rsp, 220h
0x140185c65  mov     rax, cs:__security_cookie
0x140185c6c  xor     rax, rsp
0x140185c6f  mov     [rsp+258h+var_48], rax
0x140185c77  mov     rax, r9
0x140185c7a  mov     [rsp+258h+var_188], rax
0x140185c82  mov     r14, r8
0x140185c85  mov     [rsp+258h+var_160], rdx
0x140185c8d  mov     r13, rcx
0x140185c90  mov     [rsp+258h+SourceString], rax
0x140185c98  mov     r15, [rsp+258h+arg_20]
0x140185ca0  xor     esi, esi
0x140185ca2  mov     [rsp+258h+var_1C4], esi
0x140185ca9  mov     edi, esi
0x140185cab  mov     [rsp+258h+var_1CE], sil
0x140185cb3  mov     [r11-1A8h], rsi
0x140185cba  mov     [rsp+258h+var_1B0], esi
0x140185cc1  mov     [r11-1B8h], rsi
0x140185cc8  xorps   xmm0, xmm0
0x140185ccb  movups  xmmword ptr [rsp+258h+DestinationString.Length], xmm0
0x140185cd3  xorps   xmm1, xmm1
0x140185cd6  movups  xmmword ptr [rsp+258h+P], xmm1
0x140185cde  mov     [rsp+258h+var_1CD], sil
0x140185ce6  movups  [rsp+258h+var_C8], xmm0
0x140185cee  movups  [rsp+258h+var_B8], xmm0
0x140185cf6  movups  [rsp+258h+var_A8], xmm0
0x140185cfe  movups  [rsp+258h+var_98], xmm0
0x140185d06  movups  [rsp+258h+var_88], xmm0
0x140185d0e  movups  xmmword ptr [r11-78h], xmm0
0x140185d13  movups  xmmword ptr [r11-68h], xmm0
0x140185d18  movups  xmmword ptr [r11-58h], xmm0
0x140185d1d  mov     r12, [r15+0B8h]
0x140185d24  mov     [rsp+258h+var_118], r12
0x140185d2c  mov     rbx, [r12+8]
0x140185d31  mov     rbx, [rbx+8]
0x140185d35  mov     [rsp+258h+var_E0], rbx
0x140185d3d  cmp     [r8+0D0h], rsi
0x140185d44  jnz     short loc_140185D4E
0x140185d46  mov     rdx, r8
0x140185d49  call    NtfsLoadSecurityDescriptor
0x140185d4e  mov     [rsp+258h+Privileges], rsi
0x140185d56  mov     [rsp+258h+var_138], rsi
0x140185d5e  mov     [rsp+258h+var_1D2], sil
0x140185d66  mov     [rsp+258h+var_1D1], sil
0x140185d6e  mov     [rsp+258h+DestinationString.Buffer], rsi
0x140185d76  xorps   xmm0, xmm0
0x140185d79  movups  xmmword ptr [rsp+258h+P], xmm0
0x140185d81  mov     rdx, [r14+0D0h]
0x140185d88  add     rdx, 1Ch
0x140185d8c  mov     r8, rbx
0x140185d8f  mov     rcx, cs:__imp_IoFileObjectType
0x140185d96  mov     rcx, [rcx]
0x140185d99  call    cs:__imp_SeAdjustAccessStateForAccessConstraints
0x140185da0  nop     dword ptr [rax+rax+00h]
0x140185da5  mov     esi, [rbx+14h]
0x140185da8  not     esi
0x140185daa  and     esi, [rsp+258h+arg_28]
0x140185db1  setz    [rsp+258h+var_1D7]
0x140185db9  mov     eax, esi
0x140185dbb  and     eax, 2000000h
0x140185dc0  mov     [rsp+258h+var_1C8], eax
0x140185dc7  mov     rax, [r12+8]
0x140185dcc  mov     eax, [rax+14h]
0x140185dcf  and     eax, 1000h
0x140185dd4  mov     [rsp+258h+var_120], eax
0x140185ddb  mov     rcx, [r15+0B8h]
0x140185de2  movzx   eax, byte ptr [rcx]
0x140185de5  test    al, al
0x140185de7  jnz     loc_1401874A4
0x140185ded  test    byte ptr [rcx+2], 1
0x140185df1  jnz     loc_14018748A
0x140185df7  movzx   r12d, byte ptr [r15+40h]
0x140185dfc  mov     [rsp+258h+var_1D8], r12b
0x140185e04  mov     rcx, [r14+0D0h]
0x140185e0b  add     rcx, 1Ch
0x140185e0f  lea     r8, [rsp+258h+var_1CE]
0x140185e17  lea     rdx, [rbx+20h]
0x140185e1b  call    cs:__imp_SeAuditingAnyFileEventsWithContextEx
0x140185e22  nop     dword ptr [rax+rax+00h]
0x140185e27  mov     [rsp+258h+var_1D5], al
0x140185e2e  test    al, al
0x140185e30  jnz     loc_140187497
0x140185e36  mov     [rsp+258h+var_1D4], dil
0x140185e3e  cmp     [rsp+258h+var_1CE], dil
0x140185e46  jnz     loc_140187497
0x140185e4c  lea     rcx, [rbx+20h]; SubjectContext
0x140185e50  call    cs:__imp_SeLockSubjectContext
0x140185e57  nop     dword ptr [rax+rax+00h]
0x140185e5c  mov     r12b, 1
0x140185e5f  mov     [rsp+258h+var_1D6], r12b
0x140185e67  test    esi, esi
0x140185e69  jz      loc_140186046
0x140185e6f  mov     rcx, rbx
0x140185e72  xor     eax, eax
0x140185e74  cmp     [rsp+258h+arg_40], al
0x140185e7b  cmovnz  rcx, rax
0x140185e7f  mov     [rsp+258h+var_190], rcx
0x140185e87  cmp     [rsp+258h+var_1D4], al
0x140185e8e  jnz     loc_140186076
0x140185e94  mov     [rsp+258h+var_198], rax
0x140185e9c  mov     rax, [rsp+258h+var_160]
0x140185ea4  test    rax, rax
0x140185ea7  jz      loc_140186974
0x140185ead  mov     rax, [rax+0B8h]
0x140185eb4  mov     [rsp+258h+var_1A0], rax
0x140185ebc  call    cs:__imp_IoGetFileObjectGenericMapping
0x140185ec3  nop     dword ptr [rax+rax+00h]
0x140185ec8  cmp     [rsp+258h+arg_38], 0
0x140185ed0  setnz   dl
0x140185ed3  mov     [rsp+258h+var_1C0], dl
0x140185eda  mov     rcx, [rsp+258h+var_190]
0x140185ee2  mov     [rsp+258h+var_1E8], rcx
0x140185ee7  lea     rcx, [rsp+258h+var_1C4]
0x140185eef  mov     [rsp+258h+var_1F0], rcx
0x140185ef4  mov     rcx, [rsp+258h+var_198]
0x140185efc  mov     [rsp+258h+var_1F8], rcx
0x140185f01  lea     rcx, [rsp+258h+var_1B0]
0x140185f09  mov     [rsp+258h+var_200], rcx
0x140185f0e  movzx   ecx, [rsp+258h+var_1D8]
0x140185f16  mov     [rsp+258h+var_208], cl
0x140185f1a  mov     [rsp+258h+var_210], rax
0x140185f1f  lea     rax, [rsp+258h+Privileges]
0x140185f27  mov     [rsp+258h+GenerateOnClose], rax
0x140185f2c  mov     eax, [rbx+14h]
0x140185f2f  mov     dword ptr [rsp+258h+AccessMode], eax
0x140185f33  mov     dword ptr [rsp+258h+AccessGranted], esi
0x140185f37  mov     [rsp+258h+ObjectCreated], dl
0x140185f3b  mov     byte ptr [rsp+258h+AccessState], 1
0x140185f40  lea     r9, [rbx+20h]
0x140185f44  mov     r8, r14
0x140185f47  mov     rdx, [rsp+258h+var_1A0]
0x140185f4f  mov     rcx, r13
0x140185f52  call    TxfAccessCheck
0x140185f57  mov     [rsp+258h+var_1D7], al
0x140185f5e  mov     [rsp+258h+var_1CF], al
0x140185f65  mov     rdx, [rsp+258h+Privileges]; Privileges
0x140185f6d  test    rdx, rdx
0x140185f70  jz      short loc_140185FA9
0x140185f72  mov     rcx, rbx; AccessState
0x140185f75  call    cs:__imp_SeAppendPrivileges
0x140185f7c  nop     dword ptr [rax+rax+00h]
0x140185f81  mov     rcx, [rsp+258h+Privileges]; Privileges
0x140185f89  call    cs:__imp_SeFreePrivileges
0x140185f90  nop     dword ptr [rax+rax+00h]
0x140185f95  mov     [rsp+258h+Privileges], 0
0x140185fa1  movzx   eax, [rsp+258h+var_1D7]
0x140185fa9  test    al, al
0x140185fab  jz      loc_140186066
0x140185fb1  mov     ecx, [rsp+258h+var_1B0]
0x140185fb8  mov     eax, ecx
0x140185fba  bts     eax, 19h
0x140185fbe  not     eax
0x140185fc0  and     esi, eax
0x140185fc2  mov     [rsp+258h+arg_28], esi
0x140185fc9  cmp     [rsp+258h+arg_30], 0
0x140185fd1  jnz     short loc_140185FF7
0x140185fd3  or      [rbx+14h], ecx
0x140185fd6  mov     eax, [rbx+14h]
0x140185fd9  cmp     [rsp+258h+var_1C8], 0
0x140185fe1  jnz     loc_140186EA0
0x140185fe7  mov     eax, [rsp+258h+var_1B0]
0x140185fee  bts     eax, 19h
0x140185ff2  not     eax
0x140185ff4  and     [rbx+10h], eax
0x140185ff7  mov     rdx, [r14+0D0h]
0x140185ffe  add     rdx, 1Ch
0x140186002  mov     r8, rbx
0x140186005  mov     rcx, cs:__imp_IoFileObjectType
0x14018600c  mov     rcx, [rcx]
0x14018600f  call    cs:__imp_SeShouldCheckForAccessRightsFromParent
0x140186016  nop     dword ptr [rax+rax+00h]
0x14018601b  cmp     [rsp+258h+var_188], 0
0x140186024  jz      short loc_140186046
0x140186026  test    al, al
0x140186028  jz      short loc_140186046
0x14018602a  cmp     [rsp+258h+var_1D7], 0
0x140186032  jz      loc_14018611D
0x140186038  cmp     [rsp+258h+var_1C8], 0
0x140186040  jnz     loc_140186748
0x140186046  movzx   esi, [rsp+258h+arg_30]
0x14018604e  cmp     [rsp+258h+var_1D4], 0
0x140186056  jnz     short loc_140186083
0x140186058  movzx   r14d, [rsp+258h+var_1D7]
0x140186061  jmp     loc_14018737D
0x140186066  mov     edi, [rsp+258h+var_1C4]
0x14018606d  mov     [rsp+258h+var_16C], edi
0x140186074  jmp     short loc_140185FF7
0x140186076  mov     rax, [rbx+48h]
0x14018607a  add     rax, 58h ; 'X'
0x14018607e  jmp     loc_140185E94
0x140186083  mov     rcx, [rsp+258h+var_118]
0x14018608b  mov     r8, [rcx+30h]
0x14018608f  lea     rdx, [r8+58h]
0x140186093  mov     [rsp+258h+Source], rdx
0x14018609b  movzx   eax, word ptr [rdx]
0x14018609e  test    ax, ax
0x1401860a1  setnz   [rsp+258h+var_1D3]
0x1401860a9  test    ax, ax
0x1401860ac  jz      loc_1401868FF
0x1401860b2  mov     rcx, [r8+40h]
0x1401860b6  test    rcx, rcx
0x1401860b9  jnz     loc_14018699E
0x1401860bf  test    r12b, r12b
0x1401860c2  jz      loc_140186A82
0x1401860c8  mov     rax, [r14+60h]
0x1401860cc  add     rax, 1EB0h
0x1401860d2  mov     [rsp+258h+SourceString], rax
0x1401860da  movzx   ecx, word ptr [rax]
0x1401860dd  movzx   r8d, word ptr [rdx]
0x1401860e1  lea     eax, [rcx+4]
0x1401860e4  add     eax, r8d
0x1401860e7  test    eax, 0FFFF0000h
0x1401860ec  jz      loc_140186AE3
0x1401860f2  movzx   eax, cs:NtfsStatusDebugFlags
0x1401860f9  test    al, al
0x1401860fb  jnz     loc_140186730
0x140186101  mov     [rsp+258h+AccessState], 1F0B81h
0x14018610a  xor     r9d, r9d
0x14018610d  xor     r8d, r8d
0x140186110  mov     edx, 0C0000033h
0x140186115  mov     rcx, r13
0x140186118  call    NtfsRaiseStatusInternal
0x14018611d  test    esi, 10080h
0x140186123  jz      loc_140186038
0x140186129  mov     [rsp+258h+var_1D0], 0
0x140186131  mov     [rsp+258h+var_1CC], 0
0x140186139  mov     [rsp+258h+var_168], 0
0x140186144  mov     dword ptr [rsp+258h+var_198], 0
0x14018614f  mov     dword ptr [rsp+258h+var_1A0], 0
0x14018615a  lea     rcx, [rbx+20h]; SubjectContext
0x14018615e  call    cs:__imp_SeUnlockSubjectContext
0x140186165  nop     dword ptr [rax+rax+00h]
0x14018616a  mov     [rsp+258h+var_1D6], 0
0x140186172  mov     r12, [rsp+258h+var_188]
0x14018617a  cmp     qword ptr [r12+0D0h], 0
0x140186183  jz      loc_140186E55
0x140186189  mov     eax, 702h
0x14018618e  cmp     ax, [r12]
0x140186193  jnz     loc_140186991
0x140186199  mov     rcx, r12
0x14018619c  mov     rcx, [rcx+68h]
0x1401861a0  add     rcx, 40h ; '@'; Resource
0x1401861a4  mov     dl, 1; Wait
0x1401861a6  call    cs:__imp_ExAcquireResourceSharedLite
0x1401861ad  nop     dword ptr [rax+rax+00h]
0x1401861b2  lea     rcx, [rbx+20h]; SubjectContext
0x1401861b6  call    cs:__imp_SeLockSubjectContext
0x1401861bd  nop     dword ptr [rax+rax+00h]
0x1401861c2  mov     r12b, 1
0x1401861c5  mov     [rsp+258h+var_1D6], r12b
0x1401861cd  mov     rax, [rsp+258h+var_188]
0x1401861d5  cmp     qword ptr [rax+0D0h], 0
0x1401861dd  jnz     short loc_1401861EA
0x1401861df  mov     rdx, rax
0x1401861e2  mov     rcx, r13
0x1401861e5  call    NtfsLoadSecurityDescriptor
0x1401861ea  xor     edx, edx; Val
0x1401861ec  mov     r8d, 80h; Size
0x1401861f2  lea     rcx, [rsp+258h+var_C8]; void *
0x1401861fa  call    memset
0x1401861ff  bt      esi, 10h
0x140186203  jb      loc_1401864C4
0x140186209  mov     eax, [rsp+258h+var_1C8]
0x140186210  test    eax, eax
0x140186212  jnz     loc_140186684
0x140186218  test    sil, sil
0x14018621b  jns     loc_140186630
0x140186221  mov     rcx, rbx
0x140186224  xor     eax, eax
0x140186226  cmp     [rsp+258h+arg_40], al
0x14018622d  cmovnz  rcx, rax
0x140186231  mov     [rsp+258h+var_148], rcx
0x140186239  lea     rcx, [rsp+258h+var_C8]
0x140186241  cmp     [rsp+258h+var_1D4], al
0x140186248  cmovz   rcx, rax
0x14018624c  mov     [rsp+258h+var_110], rcx
0x140186254  mov     rax, [rsp+258h+var_160]
0x14018625c  test    rax, rax
0x14018625f  jz      loc_140186662
0x140186265  mov     rax, [rax+0B8h]
0x14018626c  mov     [rsp+258h+var_190], rax
0x140186274  call    cs:__imp_IoGetFileObjectGenericMapping
0x14018627b  nop     dword ptr [rax+rax+00h]
0x140186280  mov     rcx, [rsp+258h+var_148]
0x140186288  mov     [rsp+258h+var_1E8], rcx
0x14018628d  lea     rcx, [rsp+258h+var_1C4]
0x140186295  mov     [rsp+258h+var_1F0], rcx
0x14018629a  mov     rcx, [rsp+258h+var_110]
0x1401862a2  mov     [rsp+258h+var_1F8], rcx
0x1401862a7  lea     rcx, [rsp+258h+var_1A0]
0x1401862af  mov     [rsp+258h+var_200], rcx
0x1401862b4  movzx   ecx, [rsp+258h+var_1D8]
  ... truncated ...
```
