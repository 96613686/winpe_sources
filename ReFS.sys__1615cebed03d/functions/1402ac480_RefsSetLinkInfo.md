# RefsSetLinkInfo

- ea: `0x1402ac480`
- end: `0x1402adb2a`
- name: `RefsSetLinkInfo`
- size: `5802`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14031cca8`

## callees

- `0x14004ffc0`
- `0x140076ad0`
- `0x1400862c0`
- `0x140089260`
- `0x1400928d0`
- `0x140093bc0`
- `0x14009e59c`
- `0x1400a8498`
- `0x1400a9f3c`
- `0x1400aa778`
- `0x1400bdcd0`
- `0x1400d0fd8`
- `0x1400e6524`
- `0x1400f53c4`
- `0x140113384`
- `0x1401f3f92`
- `0x1401f3fc0`
- `0x1401f4100`
- `0x1401f4400`
- `0x1401f4920`
- `0x14028c008`
- `0x14028c3d4`
- `0x14028cfa0`
- `0x14028e7f8`
- `0x1402aa38c`
- `0x1402ac480`
- `0x1402d6a88`
- `0x140302e10`
- `0x140304230`
- `0x14030b700`
- `0x140314110`
- `0x14031f9c0`
- `0x140327d00`
- `0x140328660`
- `0x14032a744`
- `0x14032ac50`
- `0x14033789c`
- `0x14033aa78`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402ada63`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403474c0`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402ada63`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403474c0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402ac8df`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402ac8df`
- `ntoskrnl!SeAuditingHardLinkEventsWithContext` at `0x1402ad667`
- `ntoskrnl!SeAuditingHardLinkEventsWithContext` at `0x1402ad667`
- `ntoskrnl!SeAuditHardLinkCreation` at `0x1402ad910`
- `ntoskrnl!SeAuditHardLinkCreation` at `0x1402ad910`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402ad636`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402ad636`
- `ntoskrnl!ExReleaseFastResource` at `0x1402ada7c`
- `ntoskrnl!ExReleaseFastResource` at `0x1403474dd`
- `ntoskrnl!ExReleaseFastResource` at `0x1402ada7c`
- `ntoskrnl!ExReleaseFastResource` at `0x1403474dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad3c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad92b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad942`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad959`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad9fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada36`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403473f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034740f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347427`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347454`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034746f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347493`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad3c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad92b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad942`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad959`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad9fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ada36`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403473f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034740f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347427`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347454`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034746f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347493`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad0ac`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad12b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad329`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad781`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad864`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad0ac`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad12b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad329`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad781`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ad864`

## pseudocode

```c
__int64 __fastcall RefsSetLinkInfo(struct _IRP_CONTEXT *a1, IRP *a2, struct _VCB *a3, struct _FCB *a4, __int64 a5)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  LARGE_INTEGER ByteOffset; // r13
  _BYTE *v9; // rcx
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  __int64 ActualAllocationLength; // r14
  __int64 v13; // rax
  char v15; // dl
  __int64 v16; // r12
  unsigned int v17; // edi
  unsigned int v18; // r9d
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ULONGLONG v20; // rdx
  __int64 v21; // rax
  struct _REFS_FILE_REFERENCE *v22; // rbx
  IndexSCB *v23; // r13
  __int64 v24; // rdx
  unsigned int v25; // r9d
  __int64 v26; // rdx
  WCHAR *v27; // rdx
  bool v28; // r12
  __int64 *v29; // rdx
  unsigned int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // r8
  unsigned int v33; // ecx
  int v34; // eax
  char v35; // al
  char v36; // bl
  struct _IRP_CONTEXT *v37; // rcx
  __int64 v38; // rcx
  struct _REFS_FILE_REFERENCE *v39; // rbx
  unsigned int v40; // ecx
  __int64 v41; // rcx
  WCHAR *PoolWithTag; // rax
  USHORT v43; // cx
  const struct _DIR_INDEX_ENTRY *v44; // rbx
  unsigned __int64 CmsKeyLength; // r9
  __int64 v46; // rax
  void *v47; // rsp
  PVOID v48; // rbx
  unsigned int v49; // edx
  __int64 v50; // rcx
  WCHAR *v51; // r9
  char *v52; // rbx
  int v53; // r12d
  __int64 v54; // rcx
  char v55; // dl
  ULONG v56; // r8d
  __int64 v57; // rcx
  ULONG v58; // edx
  ULONG v59; // r10d
  PVOID *v60; // r12
  unsigned __int16 v61; // ax
  unsigned int v62; // ebx
  unsigned int v63; // r9d
  struct _VCB *v64; // rbx
  unsigned int v65; // ebx
  struct _VCB *v66; // rbx
  __int64 v67; // rdx
  WCHAR *v68; // rcx
  __int64 v69; // r8
  __int64 v70; // rbx
  struct _SCB *CompletionRoutine; // [rsp+20h] [rbp-50h]
  __int64 v72; // [rsp+70h] [rbp+0h] BYREF
  PVOID P; // [rsp+78h] [rbp+8h] BYREF
  int v74; // [rsp+80h] [rbp+10h] BYREF
  bool v75; // [rsp+84h] [rbp+14h]
  unsigned int v76; // [rsp+88h] [rbp+18h]
  void *Buf1[2]; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v78; // [rsp+A0h] [rbp+30h] BYREF
  struct _VCB *v79; // [rsp+A8h] [rbp+38h]
  struct _UNICODE_STRING LinkName; // [rsp+B0h] [rbp+40h] BYREF
  PIRP Irp[2]; // [rsp+C0h] [rbp+50h] BYREF
  struct _REFS_FILE_REFERENCE *v82; // [rsp+D0h] [rbp+60h] BYREF
  struct _UNICODE_STRING v83; // [rsp+D8h] [rbp+68h] BYREF
  PVOID v84[2]; // [rsp+E8h] [rbp+78h] BYREF
  int v85; // [rsp+F8h] [rbp+88h]
  struct _FCB *v86; // [rsp+100h] [rbp+90h]
  WCHAR *v87; // [rsp+108h] [rbp+98h]
  IndexSCB *v88; // [rsp+110h] [rbp+A0h]
  PVOID v89[2]; // [rsp+120h] [rbp+B0h] BYREF
  struct _UNICODE_STRING v90; // [rsp+130h] [rbp+C0h] BYREF
  __int64 v91; // [rsp+140h] [rbp+D0h]
  PVOID v92; // [rsp+148h] [rbp+D8h]
  PVOID v93; // [rsp+150h] [rbp+E0h]
  struct _UNICODE_STRING v94; // [rsp+158h] [rbp+E8h] BYREF
  __int64 v95[10]; // [rsp+170h] [rbp+100h] BYREF
  _OWORD v96[2]; // [rsp+1C0h] [rbp+150h] BYREF
  int v97; // [rsp+1E0h] [rbp+170h]

  v86 = a4;
  v79 = a3;
  Irp[0] = a2;
  v89[0] = (PVOID)a5;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)Buf1 = 0;
  v90 = 0;
  memset(v96, 0, sizeof(v96));
  v97 = 0;
  v88 = 0;
  *(_QWORD *)&LinkName.Length = 0;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  v83 = 0;
  *(_OWORD *)v84 = 0;
  P = 0;
  memset(v95, 0, 0x48u);
  v9 = *(_BYTE **)(*((_QWORD *)a1 + 9) + 24LL);
  if ( CurrentStackLocation->Parameters.Create.Options == 11 )
  {
    v76 = *v9 != 0;
  }
  else
  {
    v76 = *(_DWORD *)v9;
    if ( (v76 & 0xFFFFFE04) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225659LL;
      v11 = 8018;
      goto LABEL_33;
    }
  }
  v95[0] = (__int64)a1;
  if ( (*(_DWORD *)(a5 + 4) & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v10 = 8030;
LABEL_297:
    RefsStatusDebug(-1073741811, 0, "FileInfo.c", v10);
    return 3221225485LL;
  }
  ActualAllocationLength = a4->ActualAllocationLength;
  v13 = *(_QWORD *)(ActualAllocationLength + 88);
  if ( *(_QWORD *)(v13 + 248) || !*(_QWORD *)(v13 + 256) )
  {
    if ( !RefsHardlinksSupported(*((struct _VCB **)a1 + 8)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225659LL;
      v11 = 8049;
LABEL_33:
      RefsStatusDebug(-1073741637, 0, "FileInfo.c", v11);
      return 3221225659LL;
    }
    v16 = *(_QWORD *)(a5 + 72);
    if ( v16 )
    {
      v82 = *(struct _REFS_FILE_REFERENCE **)(v16 + 24);
      if ( !*(_DWORD *)(ActualAllocationLength + 176) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741790;
        }
        else
        {
          v17 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            122,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v17;
        v18 = 8094;
        goto LABEL_78;
      }
    }
    else
    {
      if ( !*(_DWORD *)(ActualAllocationLength + 176) && (v15 & 8) != 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741790;
        }
        else
        {
          v17 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            120,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v17;
        v18 = 8071;
LABEL_78:
        RefsStatusDebug(-1073741790, 0, "FileInfo.c", v18);
        return v17;
      }
      if ( !ByteOffset.QuadPart )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            121,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225485LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return 3221225485LL;
        v10 = 8079;
        goto LABEL_297;
      }
      v82 = 0;
    }
    if ( (*(_DWORD *)(ActualAllocationLength + 8) & 0x100LL) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v10 = 8108;
      goto LABEL_297;
    }
    if ( RefsEffectiveMode(Irp[0], CurrentStackLocation) == 1 && (*(_WORD *)(a5 + 88) & 0x310) == 0 )
    {
      v78 = 0;
      v74 = 0;
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( !RefsSeAccessCheck(
              a1,
              (struct _FCB *)ActualAllocationLength,
              *((struct _SECURITY_SUBJECT_CONTEXT **)a1 + 18),
              0,
              0,
              0x100u,
              0,
              0,
              FileObjectGenericMapping,
              1,
              &v78,
              0,
              &v74,
              0) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741790;
        }
        else
        {
          v17 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            124,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v17;
        v18 = 8147;
        goto LABEL_78;
      }
    }
    if ( (*((_BYTE *)a1 + 8) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v10 = 8160;
      goto LABEL_297;
    }
    v17 = 0;
    LODWORD(v72) = 0;
    v74 = 0;
    v92 = 0;
    v93 = 0;
    if ( (*((_DWORD *)v89[0] + 1) & 8) == 0 && **((_WORD **)v89[0] + 3) == 92 )
      LOBYTE(v95[1]) |= 8u;
    *((_DWORD *)a1 + 158) = *((_DWORD *)v89[0] + 21);
    if ( (*(_DWORD *)(ActualAllocationLength + 8) & 0x10000000) == 0 )
      RefsLinkFileToSelf(a1, (struct _FCB *)ActualAllocationLength);
    v20 = v86->ActualAllocationLength;
    v21 = *(_QWORD *)(v20 + 232);
    if ( v21 && *(_DWORD *)(v21 + 104) )
    {
      RefsPostUsnChange(a1, (struct _FCB *)v20, 0x80000000, 0);
      RefsCheckpointCurrentTransaction(a1);
    }
    v22 = v82;
    RefsFindTargetElements(a1, (__int64)&LinkName, (__int64)&v90, (__int64)Buf1);
    if ( LOWORD(Buf1[0]) > 0x1FEu || !RefsIsFileNameValid((struct _UNICODE_STRING *)Buf1, 0) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v17 = -1073741773;
      }
      else
      {
        v17 = -1073741773;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            126,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225523LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_279;
      v25 = 8234;
      goto LABEL_278;
    }
    v23 = v88;
    v24 = *((_QWORD *)v88 + 17);
    if ( (*(_DWORD *)(v24 + 8) & 0x100LL) != 0 && v88 != *((IndexSCB **)v79 + 4) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v17 = -1073741790;
      }
      else
      {
        v17 = -1073741790;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            127,
            WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
            3221225506LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_279;
      v25 = 8245;
      goto LABEL_278;
    }
    RefsAcquireFcbWithPaging((__int64)a1, v24, (__int64)v88, 0x34u);
    v95[3] = (__int64)v23;
    if ( *(_QWORD *)(*((_QWORD *)v23 + 17) + 96LL) )
    {
      v88 = (IndexSCB *)1;
      v95[3] = (unsigned __int64)v23 & 0xFFFFFFFFFFFFFFF8uLL | 1;
    }
    if ( v23 == v22 )
    {
      v26 = *(_QWORD *)(v16 + 148);
      v78 = *(_DWORD *)(v16 + 140) - 4;
      v94.MaximumLength = v78;
      v94.Length = v78;
      v27 = (WCHAR *)(v26 + 4);
      v94.Buffer = v27;
      if ( LOWORD(Buf1[0]) == (_WORD)v78 )
      {
        v28 = 0;
        if ( !memcmp(Buf1[1], v27, LOWORD(Buf1[0])) )
        {
          if ( (v76 & 1) == 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741771;
            }
            else
            {
              v17 = -1073741771;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                128,
                WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
                3221225525LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8270;
LABEL_278:
            RefsStatusDebug(v17, 0, "FileInfo.c", v25);
LABEL_279:
            LODWORD(v72) = v17;
            goto LABEL_280;
          }
          goto LABEL_178;
        }
LABEL_115:
        if ( (*(_DWORD *)(ActualAllocationLength + 8) & 0x10000000) != 0 )
        {
          v29 = *(__int64 **)(ActualAllocationLength + 328);
          if ( v29 != (__int64 *)v23 )
          {
            if ( !(unsigned __int8)RefsAcquireFcbWithPaging(
                                     (__int64)a1,
                                     v29[17],
                                     0,
                                     (*((_DWORD *)a1 + 2) & 0x100LL) != 0 ? 53 : 51) )
            {
              *((_QWORD *)a1 + 1) |= 0x100uLL;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741608, a1, "FileInfo.c", 0x2070u);
              RefsRaiseStatusInternal(a1, -1073741608, v30);
            }
            v31 = *(_QWORD *)(ActualAllocationLength + 328);
            v95[4] = v31;
            if ( *(_QWORD *)(*(_QWORD *)(v31 + 136) + 96LL) )
            {
              v91 = 1;
              v95[4] = v31 & 0xFFFFFFFFFFFFFFF8uLL | 1;
            }
          }
        }
        if ( !*(_DWORD *)(*((_QWORD *)v23 + 17) + 176LL) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v17 = -1073741738;
          }
          else
          {
            v17 = -1073741738;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              130,
              WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
              3221225558LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_279;
          v25 = 8316;
          goto LABEL_278;
        }
        IndexSCB::EnsureDirectoryNormalizedName(v23, a1);
        v33 = *((unsigned __int8 *)v79 + 793) | (*((unsigned __int8 *)v79 + 792) << 8);
        if ( v33 >= 0x30B )
          v34 = v33 > 0x30B;
        else
          v34 = -1;
        if ( *(_DWORD *)(ActualAllocationLength + 180) >= 0x2000u )
        {
          if ( v34 < 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741211;
            }
            else
            {
              v17 = -1073741211;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                132,
                WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
                3221226085LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8334;
          }
          else
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741211;
            }
            else
            {
              v17 = -1073741211;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                131,
                WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
                3221226085LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8329;
          }
          goto LABEL_278;
        }
        P = 0;
        LOBYTE(v32) = (*((_DWORD *)v89[0] + 1) & 1) != 0
                   && ((*((_DWORD *)v89[0] + 1) & 0x4000000) != 0
                    || (*(_DWORD *)(*((_QWORD *)v23 + 17) + 8LL) & 0x400000) == 0);
        v35 = RefsLookupEntry(a1, v23, v32, Buf1, v96, &P);
        v36 = v95[1] & 0xFD | (2 * (v35 & 1));
        LOBYTE(v95[1]) = v36;
        if ( RefsIsTransactionActive(a1) )
        {
          RefsCheckpointCurrentTransaction(v37);
          v36 = v95[1];
        }
        if ( (v36 & 2) != 0 )
        {
          if ( (v76 & 1) == 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741771;
            }
            else
            {
              v17 = -1073741771;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                133,
                WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
                3221225525LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8383;
            goto LABEL_278;
          }
          v75 = 0;
          v38 = *(_QWORD *)(ActualAllocationLength + 88);
          if ( *((_QWORD *)P + 1) == *(_QWORD *)(v38 + 256) && *(_QWORD *)P == *(_QWORD *)(v38 + 248) )
          {
            v36 |= 0x10u;
            LOBYTE(v95[1]) = v36;
          }
          if ( !memcmp(*(const void **)((char *)P + 84), Buf1[1], LOWORD(Buf1[0])) )
          {
            v36 |= 0x20u;
            LOBYTE(v95[1]) = v36;
          }
          if ( (v36 & 0x10) != 0 )
          {
            v28 = (v36 & 0x20) != 0;
            v75 = v28;
          }
          if ( v28 )
          {
LABEL_178:
            v17 = 0;
            LODWORD(v72) = 0;
LABEL_280:
            v48 = P;
LABEL_281:
            if ( v84[1] )
              ExFreePoolWithTag(v84[1], 0);
            if ( v92 )
              ExFreePoolWithTag(v92, 0);
            _FILE_NAME::CleanupFileName((_FILE_NAME *)v96);
            if ( v48 )
              ExFreePoolWithTag(v48, 0);
            if ( (v95[1] & 4) != 0 )
            {
              v70 = v95[7];
              LOBYTE(v69) = 1;
              ExAcquireFastResourceExclusive(*(_QWORD *)(v95[7] + 80) + 624LL, 0, v69);
              _InterlockedDecrement((volatile signed __int32 *)(v70 + 24));
              ExReleaseFastResource(*(_QWORD *)(v70 + 80) + 624LL, 0);
            }
            if ( v17 != 871 )
              RefsRenameCleanup((struct _REFS_RENAME_CLEANUP *)v95);
            return v17;
          }
          if ( (v36 & 8) != 0 )
          {
            v39 = v82;
            v40 = LOWORD(Buf1[0]) + 2 + *((unsigned __int16 *)v82 + 196);
            if ( v40 > 0xFFFE )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              {
                v17 = -1073741562;
              }
              else
              {
                v17 = -1073741562;
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  134,
                  WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
                  3221225734LL);
              }
              if ( !(_BYTE)RefsStatusDebugEnabled )
                goto LABEL_279;
              v25 = 8418;
              goto LABEL_278;
            }
            LOWORD(v84[0]) = LOWORD(Buf1[0]) + 2 + *((_WORD *)v82 + 196);
            WORD1(v84[0]) = v40;
            v84[1] = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v40, 0x46466552u);
            memmove(v84[1], *((const void **)v39 + 50), *((unsigned __int16 *)v39 + 196));
            v41 = *((unsigned __int16 *)v39 + 196);
            PoolWithTag = (WCHAR *)((char *)v84[1] + v41);
            v87 = (WCHAR *)((char *)v84[1] + v41);
            if ( (_WORD)v41 == 2 )
            {
              LOWORD(v84[0]) -= 2;
            }
            else
            {
              *PoolWithTag++ = 92;
              v87 = PoolWithTag;
            }
            v83.Buffer = PoolWithTag;
            v43 = (USHORT)Buf1[0];
          }
          else
          {
            PoolWithTag = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), LOWORD(Buf1[0]), 0x46466552u);
            v83.Buffer = PoolWithTag;
            v84[1] = PoolWithTag;
            v43 = (USHORT)Buf1[0];
            v83.MaximumLength = (USHORT)Buf1[0];
            LOWORD(v84[0]) = Buf1[0];
          }
          v83.MaximumLength = v43;
          v83.Length = v43;
          v44 = (const struct _DIR_INDEX_ENTRY *)P;
          memmove(PoolWithTag, *(const void **)((char *)P + 84), v43);
          if ( (v95[1] & 0x10) != 0 )
          {
            RefsRemoveLink(a1, (struct _FCB *)ActualAllocationLength, v23, &v83);
            v74 = 1;
            *(_QWORD *)(ActualAllocationLength + 8) &= ~0x4000uLL;
            v95[7] = ActualAllocationLength;
          }
          else
          {
            v82 = 0;
            CmsKeyLength = RefsGetCmsKeyLength(v44, &v83, &v82);
            v46 = CmsKeyLength + 15;
            if ( CmsKeyLength + 15 <= CmsKeyLength )
              v46 = 0xFFFFFFFFFFFFFF0LL;
            v47 = alloca(v46 & 0xFFFFFFFFFFFFFFF0uLL);
            RefsInitCmsKey((struct _CmsKey *)&v72, &v83, v82, CmsKeyLength);
            v48 = P;
            v17 = RefsRemoveSupersededTarget(
                    a1,
                    Irp[0],
                    (__int64)v89[0],
                    (__int64)&v72,
                    (v76 & 2) != 0,
                    (v76 & 0x40) != 0,
                    (__int64)v95,
                    &v83);
            LODWORD(v72) = v17;
            if ( v17 )
              goto LABEL_281;
          }
          v36 = v95[1];
        }
        if ( *(_QWORD *)&LinkName.Length && (*(_DWORD *)(*(_QWORD *)&LinkName.Length + 4LL) & 8) != 0
          || (v36 & 8) != 0 && !v90.Buffer )
        {
          v49 = LOWORD(Buf1[0]) + 2 + *((unsigned __int16 *)v23 + 196);
          if ( v49 > 0xFFFE )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741562;
            }
            else
            {
              v17 = -1073741562;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                135,
                WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
                3221225734LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8541;
            goto LABEL_278;
          }
          v90.Length = LOWORD(Buf1[0]) + 2 + *((_WORD *)v23 + 196);
          v90.MaximumLength = v49;
          v92 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v49, 0x46466552u);
          v90.Buffer = (PWSTR)v92;
          v93 = v92;
          memmove(v92, *((const void **)v23 + 50), *((unsigned __int16 *)v23 + 196));
          v50 = *((unsigned __int16 *)v23 + 196);
          v51 = (PWSTR)((char *)v90.Buffer + v50);
          v87 = (PWSTR)((char *)v90.Buffer + v50);
          if ( (_WORD)v50 == 2 )
          {
            v90.Length -= 2;
          }
          else
          {
            *v51++ = 92;
            v87 = v51;
          }
          memmove(v51, Buf1[1], LOWORD(Buf1[0]));
        }
        if ( P )
        {
          ExFreePoolWithTag(P, 0);
          P = 0;
        }
        v52 = (char *)v89[0];
        RefsCheckIndexForAddOrDelete(a1, Irp[0], *((struct _FCB **)v23 + 17), 2u, (struct _CCB *)v89[0]);
        RefsUpdateFileTimestampsForChange(v86->ActualAllocationLength, v52, 0x400000, 0);
        RefsAddLink(a1, v23, (struct _FCB *)ActualAllocationLength, (struct _FILE_NAME *)v96);
        v53 = --v74;
        RefsUpdateFcbTimestamps(*((_QWORD *)v23 + 17), 0, 2684354576LL);
        v55 = v95[1];
        if ( (v95[1] & 0x10) != 0 )
        {
          RefsReplaceLinkInDir((_DWORD)a1, (_DWORD)v23, ActualAllocationLength, (unsigned int)Buf1, (__int64)&v83);
          v55 = v95[1];
        }
        if ( (v55 & 2) != 0 && (v55 & 0x10) == 0 )
        {
          RefsUpdateFcbFromLinkRemoval(v54, v23, v95[7], &v83);
          v55 = v95[1];
        }
        if ( (v55 & 8) != 0 )
        {
          v56 = 0;
          v85 = 0;
          if ( (v55 & 0x20) != 0 )
          {
            v59 = 0;
            if ( (v55 & 0x10) == 0 )
            {
              v56 = 508;
              v85 = 508;
              v59 = 3;
            }
          }
          else
          {
            if ( (v55 & 2) != 0 )
            {
              v57 = *(_QWORD *)(v95[7] + 88);
              if ( *(_QWORD *)(v57 + 248) || (v58 = 2, !*(_QWORD *)(v57 + 256)) )
                v58 = 1;
              RefsReportDirNotify(
                (IndexSCB *)((char *)v23 + 392),
                v79,
                (struct _UNICODE_STRING *)v84,
                LOWORD(v84[0]) - v83.Length,
                0,
                (struct _UNICODE_STRING *)((char *)v23 + 392),
                v58,
                2u,
                *((struct _FCB **)v23 + 17));
            }
            v56 = 1;
            v85 = 1;
            v59 = 1;
          }
          if ( v56 )
            RefsReportDirNotify(
              (IndexSCB *)((char *)v23 + 392),
              v79,
              &v90,
              v90.Length - LOWORD(Buf1[0]),
              0,
              (struct _UNICODE_STRING *)((char *)v23 + 392),
              v56,
              v59,
              *((struct _FCB **)v23 + 17));
        }
        RefsPostUsnChange(a1, v86, 0x80010000, (const struct _FILE_NAME *)v96);
        RefsConvertToStandardInfoLinkCount(
          a1,
          ActualAllocationLength,
          (unsigned int)(*(_DWORD *)(ActualAllocationLength + 180) - v53),
          0);
        if ( *((_QWORD *)a1 + 76) )
        {
          RefsCheckpointCurrentTransaction(a1);
          *(_DWORD *)(ActualAllocationLength + 180) -= v53;
          *(_DWORD *)(ActualAllocationLength + 176) -= v53;
          v53 = 0;
          v74 = 0;
          *(_QWORD *)(v86->ActualAllocationLength + 8) &= ~0x4000uLL;
        }
        FsRtlCheckOplockEx((POPLOCK)v23 + 11, Irp[0], 0x10u, 0, 0, 0);
        if ( !*(_QWORD *)(ActualAllocationLength + 192) )
          RefsLoadSecurityDescriptor(a1, (struct _FCB *)ActualAllocationLength);
        if ( !SeAuditingHardLinkEventsWithContext(
                1u,
                (PSECURITY_DESCRIPTOR)(*(_QWORD *)(ActualAllocationLength + 192) + 20LL),
                0) )
        {
LABEL_270:
          RefsCheckpointCurrentTransaction(a1);
          *(_DWORD *)(ActualAllocationLength + 180) -= v53;
          *(_DWORD *)(ActualAllocationLength + 176) -= v53;
          goto LABEL_280;
        }
        v89[0] = 0;
        Irp[0] = 0;
        *(_QWORD *)&LinkName.Length = 0;
        v76 = 0;
        v89[1] = 0;
        Irp[1] = 0;
        LinkName.Buffer = 0;
        v60 = (PVOID *)(v52 + 16);
        v61 = *((_WORD *)v52 + 8);
        if ( !v61 )
        {
          *(struct _UNICODE_STRING *)v89 = *RefsBuildNormalizedName(
                                              &v94,
                                              a1,
                                              (struct _FCB *)v86->ActualAllocationLength,
                                              *((struct _LCB **)v52 + 9),
                                              CompletionRoutine);
          v60 = v89;
          v61 = _mm_cvtsi128_si32(*(__m128i *)v89);
        }
        v62 = v61 + *((unsigned __int16 *)v79 + 408);
        v76 = v62;
        if ( v62 <= 0xFFFE )
        {
          Irp[1] = (PIRP)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v62, 0x46466552u);
          WORD1(Irp[0]) = v62;
          LOWORD(Irp[0]) = v62;
          v64 = v79;
          memmove(Irp[1], *((const void **)v79 + 103), *((unsigned __int16 *)v79 + 408));
          memmove((char *)Irp[1] + *((unsigned __int16 *)v64 + 408), v60[1], *(unsigned __int16 *)v60);
          v65 = LOWORD(Buf1[0]) + *((unsigned __int16 *)v64 + 408) + *((unsigned __int16 *)v23 + 196) + 2;
          v76 = v65;
          if ( v65 <= 0xFFFE )
          {
            LinkName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v65, 0x46466552u);
            LinkName.MaximumLength = v65;
            LinkName.Length = v65;
            v66 = v79;
            memmove(LinkName.Buffer, *((const void **)v79 + 103), *((unsigned __int16 *)v79 + 408));
            memmove(
              (char *)LinkName.Buffer + *((unsigned __int16 *)v66 + 408),
              *((const void **)v23 + 50),
              *((unsigned __int16 *)v23 + 196));
            v67 = *((unsigned __int16 *)v23 + 196);
            v68 = (PWSTR)((char *)LinkName.Buffer + *((unsigned __int16 *)v66 + 408) + v67);
            v87 = v68;
            if ( (_WORD)v67 == 2 )
            {
              LinkName.Length -= 2;
            }
            else
            {
              *v68++ = 92;
              v87 = v68;
            }
            memmove(v68, Buf1[1], LOWORD(Buf1[0]));
            SeAuditHardLinkCreation((PUNICODE_STRING)Irp, &LinkName, 1u);
            goto LABEL_263;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v17 = -1073741562;
          }
          else
          {
            v17 = -1073741562;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              137,
              WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
              3221225734LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
          {
LABEL_250:
            LODWORD(v72) = -1073741562;
LABEL_263:
            if ( v89[1] )
              ExFreePoolWithTag(v89[1], 0);
            if ( LinkName.Buffer )
              ExFreePoolWithTag(LinkName.Buffer, 0);
            if ( Irp[1] )
              ExFreePoolWithTag(Irp[1], 0);
            v53 = v74;
            goto LABEL_270;
          }
          v63 = 8840;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v17 = -1073741562;
          }
          else
          {
            v17 = -1073741562;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              136,
              WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids,
              3221225734LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_250;
          v63 = 8827;
        }
        RefsStatusDebug(-1073741562, 0, "FileInfo.c", v63);
        goto LABEL_250;
      }
    }
    else
    {
      BYTE1(v95[1]) |= 4u;
    }
    v28 = 0;
    goto LABEL_115;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids, 3221225658LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741638, 0, "FileInfo.c", 0x1F69u);
  return 3221225658LL;
}

```

## disassembly

```asm
0x1402ac480  push    rbp
0x1402ac482  push    rbx
0x1402ac483  push    rsi
0x1402ac484  push    rdi
0x1402ac485  push    r12
0x1402ac487  push    r13
0x1402ac489  push    r14
0x1402ac48b  push    r15
0x1402ac48d  sub     rsp, 1F8h
0x1402ac494  lea     rbp, [rsp+70h]
0x1402ac499  mov     rax, cs:__security_cookie
0x1402ac4a0  xor     rax, rbp
0x1402ac4a3  mov     [rbp+1C0h+var_48], rax
0x1402ac4aa  mov     rsi, r9
0x1402ac4ad  mov     [rbp+1C0h+var_130], r9
0x1402ac4b4  mov     [rbp+1C0h+var_188], r8
0x1402ac4b8  mov     [rbp+1C0h+Irp], rdx
0x1402ac4bc  mov     r15, rcx
0x1402ac4bf  mov     rdi, [rbp+1C0h+arg_20]
0x1402ac4c6  mov     [rbp+1C0h+var_110], rdi
0x1402ac4cd  mov     rbx, [rdx+0B8h]
0x1402ac4d4  xorps   xmm0, xmm0
0x1402ac4d7  movups  xmmword ptr [rbp+1C0h+Buf1], xmm0
0x1402ac4db  xorps   xmm1, xmm1
0x1402ac4de  movups  xmmword ptr [rbp+1C0h+var_100.Length], xmm1
0x1402ac4e5  xor     eax, eax
0x1402ac4e7  movups  [rbp+1C0h+var_70], xmm0
0x1402ac4ee  movups  [rbp+1C0h+var_60], xmm0
0x1402ac4f5  mov     [rbp+1C0h+var_50], eax
0x1402ac4fb  xor     r12d, r12d
0x1402ac4fe  mov     [rbp+1C0h+var_120], r12
0x1402ac505  mov     qword ptr [rbp+1C0h+LinkName.Length], r12
0x1402ac509  mov     r13, [rbx+18h]
0x1402ac50d  movups  xmmword ptr [rbp+1C0h+var_158.Length], xmm0
0x1402ac511  movups  xmmword ptr [rbp+1C0h+var_148], xmm1
0x1402ac515  mov     [rbp+1C0h+P], r12
0x1402ac519  xor     edx, edx; Val
0x1402ac51b  lea     r8d, [rax+48h]; Size
0x1402ac51f  lea     rcx, [rbp+1C0h+var_C0]; void *
0x1402ac526  call    memset
0x1402ac52b  mov     rax, [r15+48h]
0x1402ac52f  mov     rcx, [rax+18h]
0x1402ac533  cmp     dword ptr [rbx+10h], 0Bh
0x1402ac537  jnz     short loc_1402AC5AC
0x1402ac539  mov     eax, r12d
0x1402ac53c  cmp     [rcx], r12b
0x1402ac53f  setnz   al
0x1402ac542  mov     [rbp+1C0h+var_1A8], eax
0x1402ac545  mov     [rbp+1C0h+var_C0], r15
0x1402ac54c  mov     edx, [rdi+4]
0x1402ac54f  test    dl, 2
0x1402ac552  jnz     loc_1402AC60C
0x1402ac558  lea     rax, WPP_GLOBAL_Control
0x1402ac55f  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac566  cmp     rcx, rax
0x1402ac569  jz      short loc_1402AC593
0x1402ac56b  bt      dword ptr [rcx+2Ch], 8
0x1402ac570  jnb     short loc_1402AC593
0x1402ac572  cmp     byte ptr [rcx+29h], 4
0x1402ac576  jb      short loc_1402AC593
0x1402ac578  mov     edx, 75h ; 'u'
0x1402ac57d  mov     r9d, 0C000000Dh
0x1402ac583  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac58a  mov     rcx, [rcx+18h]
0x1402ac58e  call    WPP_SF_d
0x1402ac593  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac599  test    al, al
0x1402ac59b  jz      loc_1402ADB01
0x1402ac5a1  mov     r9d, 1F5Eh
0x1402ac5a7  jmp     loc_1402ADAEE
0x1402ac5ac  mov     eax, [rcx]
0x1402ac5ae  mov     [rbp+1C0h+var_1A8], eax
0x1402ac5b1  test    eax, 0FFFFFE04h
0x1402ac5b6  jz      short loc_1402AC545
0x1402ac5b8  lea     rax, WPP_GLOBAL_Control
0x1402ac5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac5c6  cmp     rcx, rax
0x1402ac5c9  jz      short loc_1402AC5F3
0x1402ac5cb  bt      dword ptr [rcx+2Ch], 8
0x1402ac5d0  jnb     short loc_1402AC5F3
0x1402ac5d2  cmp     byte ptr [rcx+29h], 4
0x1402ac5d6  jb      short loc_1402AC5F3
0x1402ac5d8  mov     edx, 74h ; 't'
0x1402ac5dd  mov     r9d, 0C00000BBh
0x1402ac5e3  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac5ea  mov     rcx, [rcx+18h]
0x1402ac5ee  call    WPP_SF_d
0x1402ac5f3  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac5f9  test    al, al
0x1402ac5fb  jz      loc_1402AC6FC
0x1402ac601  mov     r9d, 1F52h
0x1402ac607  jmp     loc_1402AC6E9
0x1402ac60c  mov     r14, [rsi+88h]
0x1402ac613  mov     rax, [r14+58h]
0x1402ac617  cmp     [rax+0F8h], r12
0x1402ac61e  jnz     short loc_1402AC691
0x1402ac620  cmp     [rax+100h], r12
0x1402ac627  jz      short loc_1402AC691
0x1402ac629  lea     rax, WPP_GLOBAL_Control
0x1402ac630  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac637  cmp     rcx, rax
0x1402ac63a  jz      short loc_1402AC664
0x1402ac63c  bt      dword ptr [rcx+2Ch], 8
0x1402ac641  jnb     short loc_1402AC664
0x1402ac643  cmp     byte ptr [rcx+29h], 4
0x1402ac647  jb      short loc_1402AC664
0x1402ac649  mov     edx, 76h ; 'v'
0x1402ac64e  mov     r9d, 0C00000BAh
0x1402ac654  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac65b  mov     rcx, [rcx+18h]
0x1402ac65f  call    WPP_SF_d
0x1402ac664  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac66a  test    al, al
0x1402ac66c  jz      short loc_1402AC687
0x1402ac66e  mov     r9d, 1F69h; unsigned int
0x1402ac674  lea     r8, aFileinfoC; "FileInfo.c"
0x1402ac67b  xor     edx, edx; struct _IRP_CONTEXT *
0x1402ac67d  mov     ecx, 0C00000BAh; Status
0x1402ac682  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402ac687  mov     eax, 0C00000BAh
0x1402ac68c  jmp     loc_1402ADB06
0x1402ac691  mov     rcx, [r15+40h]; struct _VCB *
0x1402ac695  call    ?RefsHardlinksSupported@@YAEPEAU_VCB@@@Z; RefsHardlinksSupported(_VCB *)
0x1402ac69a  test    al, al
0x1402ac69c  jnz     short loc_1402AC706
0x1402ac69e  lea     rax, WPP_GLOBAL_Control
0x1402ac6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac6ac  cmp     rcx, rax
0x1402ac6af  jz      short loc_1402AC6D9
0x1402ac6b1  bt      dword ptr [rcx+2Ch], 8
0x1402ac6b6  jnb     short loc_1402AC6D9
0x1402ac6b8  cmp     byte ptr [rcx+29h], 4
0x1402ac6bc  jb      short loc_1402AC6D9
0x1402ac6be  mov     edx, 77h ; 'w'
0x1402ac6c3  mov     r9d, 0C00000BBh
0x1402ac6c9  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac6d0  mov     rcx, [rcx+18h]
0x1402ac6d4  call    WPP_SF_d
0x1402ac6d9  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac6df  test    cl, cl
0x1402ac6e1  jz      short loc_1402AC6FC
0x1402ac6e3  mov     r9d, 1F71h; unsigned int
0x1402ac6e9  lea     r8, aFileinfoC; "FileInfo.c"
0x1402ac6f0  xor     edx, edx; struct _IRP_CONTEXT *
0x1402ac6f2  mov     ecx, 0C00000BBh; Status
0x1402ac6f7  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402ac6fc  mov     eax, 0C00000BBh
0x1402ac701  jmp     loc_1402ADB06
0x1402ac706  mov     r12, [rdi+48h]
0x1402ac70a  xor     ecx, ecx
0x1402ac70c  test    r12, r12
0x1402ac70f  jnz     loc_1402AC840
0x1402ac715  cmp     [r14+0B0h], ecx
0x1402ac71c  jnz     short loc_1402AC780
0x1402ac71e  test    dl, 8
0x1402ac721  jz      short loc_1402AC780
0x1402ac723  lea     rax, WPP_GLOBAL_Control
0x1402ac72a  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac731  cmp     rcx, rax
0x1402ac734  jz      short loc_1402AC762
0x1402ac736  bt      dword ptr [rcx+2Ch], 8
0x1402ac73b  jnb     short loc_1402AC762
0x1402ac73d  cmp     byte ptr [rcx+29h], 4
0x1402ac741  jb      short loc_1402AC762
0x1402ac743  lea     edx, [r12+78h]
0x1402ac748  mov     edi, 0C0000022h
0x1402ac74d  mov     r9d, edi
0x1402ac750  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac757  mov     rcx, [rcx+18h]
0x1402ac75b  call    WPP_SF_d
0x1402ac760  jmp     short loc_1402AC767
0x1402ac762  mov     edi, 0C0000022h
0x1402ac767  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac76d  test    al, al
0x1402ac76f  jz      loc_1402AC99B
0x1402ac775  mov     r9d, 1F87h
0x1402ac77b  jmp     loc_1402AC98B
0x1402ac780  test    r13, r13
0x1402ac783  jnz     short loc_1402AC7D8
0x1402ac785  lea     rax, WPP_GLOBAL_Control
0x1402ac78c  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac793  cmp     rcx, rax
0x1402ac796  jz      short loc_1402AC7BF
0x1402ac798  bt      dword ptr [rcx+2Ch], 8
0x1402ac79d  jnb     short loc_1402AC7BF
0x1402ac79f  cmp     byte ptr [rcx+29h], 4
0x1402ac7a3  jb      short loc_1402AC7BF
0x1402ac7a5  lea     edx, [r13+79h]
0x1402ac7a9  mov     r9d, 0C000000Dh
0x1402ac7af  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac7b6  mov     rcx, [rcx+18h]
0x1402ac7ba  call    WPP_SF_d
0x1402ac7bf  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac7c5  test    al, al
0x1402ac7c7  jz      loc_1402ADB01
0x1402ac7cd  mov     r9d, 1F8Fh
0x1402ac7d3  jmp     loc_1402ADAEE
0x1402ac7d8  mov     [rbp+1C0h+var_160], rcx
0x1402ac7dc  mov     eax, [r14+8]
0x1402ac7e0  mov     esi, 100h
0x1402ac7e5  test    rsi, rax
0x1402ac7e8  jz      loc_1402AC8AF
0x1402ac7ee  lea     rax, WPP_GLOBAL_Control
0x1402ac7f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac7fc  cmp     rcx, rax
0x1402ac7ff  jz      short loc_1402AC827
0x1402ac801  test    [rcx+2Ch], esi
0x1402ac804  jz      short loc_1402AC827
0x1402ac806  cmp     byte ptr [rcx+29h], 4
0x1402ac80a  jb      short loc_1402AC827
0x1402ac80c  mov     edx, 7Bh ; '{'
0x1402ac811  mov     r9d, 0C000000Dh
0x1402ac817  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac81e  mov     rcx, [rcx+18h]
0x1402ac822  call    WPP_SF_d
0x1402ac827  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac82d  test    al, al
0x1402ac82f  jz      loc_1402ADB01
0x1402ac835  mov     r9d, 1FACh
0x1402ac83b  jmp     loc_1402ADAEE
0x1402ac840  mov     rax, [r12+18h]
0x1402ac845  mov     [rbp+1C0h+var_160], rax
0x1402ac849  cmp     [r14+0B0h], ecx
0x1402ac850  jnz     short loc_1402AC7DC
0x1402ac852  lea     rax, WPP_GLOBAL_Control
0x1402ac859  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac860  cmp     rcx, rax
0x1402ac863  jz      short loc_1402AC891
0x1402ac865  bt      dword ptr [rcx+2Ch], 8
0x1402ac86a  jnb     short loc_1402AC891
0x1402ac86c  cmp     byte ptr [rcx+29h], 4
0x1402ac870  jb      short loc_1402AC891
0x1402ac872  mov     edx, 7Ah ; 'z'
0x1402ac877  mov     edi, 0C0000022h
0x1402ac87c  mov     r9d, edi
0x1402ac87f  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac886  mov     rcx, [rcx+18h]
0x1402ac88a  call    WPP_SF_d
0x1402ac88f  jmp     short loc_1402AC896
0x1402ac891  mov     edi, 0C0000022h
0x1402ac896  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac89c  test    al, al
0x1402ac89e  jz      loc_1402AC99B
0x1402ac8a4  mov     r9d, 1F9Eh
0x1402ac8aa  jmp     loc_1402AC98B
0x1402ac8af  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x1402ac8b2  mov     rcx, [rbp+1C0h+Irp]; struct _IRP *
0x1402ac8b6  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402ac8bb  mov     edx, 1
0x1402ac8c0  xor     ebx, ebx
0x1402ac8c2  cmp     al, dl
0x1402ac8c4  jnz     loc_1402AC9A7
0x1402ac8ca  mov     ecx, 310h
0x1402ac8cf  test    [rdi+58h], cx
0x1402ac8d3  jnz     loc_1402AC9A7
0x1402ac8d9  mov     [rbp+1C0h+var_190], ebx
0x1402ac8dc  mov     [rbp+1C0h+var_1B0], ebx
0x1402ac8df  call    cs:__imp_IoGetFileObjectGenericMapping
0x1402ac8e6  nop     dword ptr [rax+rax+00h]
0x1402ac8eb  mov     [rsp+230h+var_1C8], rbx; struct _ACCESS_STATE *
0x1402ac8f0  lea     rcx, [rbp+1C0h+var_1B0]
0x1402ac8f4  mov     [rsp+230h+var_1D0], rcx; int *
0x1402ac8f9  mov     [rsp+230h+var_1D8], rbx; struct _ACCESS_REASONS *
0x1402ac8fe  lea     rcx, [rbp+1C0h+var_190]
0x1402ac902  mov     [rsp+230h+var_1E0], rcx; unsigned int *
0x1402ac907  mov     [rsp+230h+var_1E8], 1; char
0x1402ac90c  mov     [rsp+230h+var_1F0], rax; struct _GENERIC_MAPPING *
0x1402ac911  mov     qword ptr [rsp+230h+var_1F8], rbx; struct _PRIVILEGE_SET **
0x1402ac916  mov     [rsp+230h+var_200], ebx; unsigned int
0x1402ac91a  mov     dword ptr [rsp+230h+PostIrpRoutine], esi; unsigned int
0x1402ac91e  mov     byte ptr [rsp+230h+CompletionRoutine], bl; char
0x1402ac922  xor     r9d, r9d; unsigned __int8
0x1402ac925  mov     r8, [r15+90h]; struct _SECURITY_SUBJECT_CONTEXT *
0x1402ac92c  mov     rdx, r14; struct _FCB *
0x1402ac92f  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402ac932  call    ?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z; RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)
0x1402ac937  test    al, al
0x1402ac939  jnz     short loc_1402AC9A2
0x1402ac93b  lea     rax, WPP_GLOBAL_Control
0x1402ac942  mov     rcx, cs:WPP_GLOBAL_Control
0x1402ac949  cmp     rcx, rax
0x1402ac94c  jz      short loc_1402AC976
0x1402ac94e  test    [rcx+2Ch], esi
0x1402ac951  jz      short loc_1402AC976
0x1402ac953  cmp     byte ptr [rcx+29h], 4
0x1402ac957  jb      short loc_1402AC976
0x1402ac959  lea     edx, [rbx+7Ch]
0x1402ac95c  mov     edi, 0C0000022h
0x1402ac961  mov     r9d, edi
0x1402ac964  lea     r8, WPP_0f526c56a29e3bccdcb81098a0e78ea1_Traceguids
0x1402ac96b  mov     rcx, [rcx+18h]
0x1402ac96f  call    WPP_SF_d
0x1402ac974  jmp     short loc_1402AC97B
0x1402ac976  mov     edi, 0C0000022h
0x1402ac97b  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402ac981  test    al, al
0x1402ac983  jz      short loc_1402AC99B
0x1402ac985  mov     r9d, 1FD3h; unsigned int
0x1402ac98b  lea     r8, aFileinfoC; "FileInfo.c"
0x1402ac992  xor     edx, edx; struct _IRP_CONTEXT *
  ... truncated ...
```
