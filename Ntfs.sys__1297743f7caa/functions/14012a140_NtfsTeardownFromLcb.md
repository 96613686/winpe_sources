# NtfsTeardownFromLcb

- ea: `0x14012a140`
- end: `0x14012b263`
- name: `NtfsTeardownFromLcb`
- size: `4387`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140128da0`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x14000d1e0`
- `0x14000ea70`
- `0x140012e70`
- `0x14001e810`
- `0x1400331f8`
- `0x14003380c`
- `0x14004a4ac`
- `0x140129550`
- `0x14012a140`
- `0x14012b270`
- `0x14012bac0`
- `0x14012c0e0`
- `0x1401403d0`
- `0x140141a3c`
- `0x140148f80`
- `0x14015e444`
- `0x1401c0130`
- `0x1401e3280`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a332`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a38c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012afd3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012b049`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a332`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012a38c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012afd3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012b049`
- `ntoskrnl!ObfDereferenceObject` at `0x14012aa5f`
- `ntoskrnl!ObfDereferenceObject` at `0x14012ae45`
- `ntoskrnl!ObfDereferenceObject` at `0x14012aa5f`
- `ntoskrnl!ObfDereferenceObject` at `0x14012ae45`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012aa25`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012ae06`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012aa25`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14012ae06`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a71f`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a82c`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012ab4e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012ab72`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a71f`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012a82c`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012ab4e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14012ab72`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a5e5`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a80b`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012ab2a`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a5e5`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012a80b`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012ab2a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14012a2d4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14012a2d4`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012a988`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012ad71`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012a988`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14012ad71`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a5d6e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a5d6e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a517`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a59e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a5b4`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a9fa`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012addf`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b23c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a5db5`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a517`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a59e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a5b4`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012a9fa`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012addf`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b23c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a5db5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012a8b7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012a8b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a6c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a7ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a6c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012a7ef`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012aee9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012aee9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012aa4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012ae36`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012af69`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012aa4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012ae36`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012af69`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012a632`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012a632`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012a6a4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012a6a4`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012a966`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012ad4e`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012af40`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012a966`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012ad4e`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14012af40`

## pseudocode

```c
void __fastcall NtfsTeardownFromLcb(__int64 a1, __int64 a2, KSPIN_LOCK a3, char *a4, char a5, _BYTE *a6, _BYTE *a7)
{
  int v7; // ebx
  KSPIN_LOCK v8; // rdi
  __int64 v9; // r15
  KSPIN_LOCK v10; // r13
  char v11; // r12
  int v12; // r10d
  struct _FILE_OBJECT *v13; // rcx
  __int64 v14; // rdx
  bool v15; // al
  __int64 v16; // rbx
  char *v17; // rbx
  struct _FILE_OBJECT *v18; // r9
  int v19; // eax
  int v20; // r14d
  __int64 v21; // rdx
  unsigned __int64 v22; // rax
  __int64 v23; // r14
  _QWORD **v24; // r14
  _QWORD *v25; // rcx
  __int64 v26; // r12
  KSPIN_LOCK v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rax
  LIST_ENTRY *p_WaitListHead; // r14
  __int64 v31; // rcx
  char *v32; // rcx
  char **v33; // rdx
  void **v34; // rcx
  char **v35; // rdx
  void **v36; // rcx
  char *v37; // rcx
  __int64 v38; // rcx
  PFILE_OBJECT v39; // rbx
  __int64 v40; // rdi
  __int64 v41; // rdi
  _DWORD *v42; // rbx
  __int64 v43; // rbx
  char *v44; // r8
  unsigned __int64 v45; // rdx
  __int64 v46; // rcx
  unsigned __int8 v47; // r14
  PFILE_OBJECT v48; // rcx
  _DWORD *FsContext; // rax
  bool v50; // zf
  __int64 *v51; // r14
  union _LARGE_INTEGER *v52; // rdx
  KSPIN_LOCK IrpListLock; // rdx
  char v54; // al
  PFILE_OBJECT v55; // rdx
  KSPIN_LOCK *v56; // r12
  KSPIN_LOCK v57; // rax
  KSPIN_LOCK **v58; // rdx
  KSPIN_LOCK **v59; // rax
  __int64 v60; // rdi
  bool v61; // r14
  unsigned __int8 v62; // bl
  __int64 v63; // rdi
  __int64 v64; // rax
  union _LARGE_INTEGER *v65; // rdx
  __int64 v66; // rcx
  char *v67; // rdx
  char *v68; // r8
  char **v69; // r9
  BOOLEAN v70; // dl
  PFILE_OBJECT v71; // r8
  ULONG *p_Waiters; // rcx
  BOOLEAN IsResourceAcquiredExclusiveLite; // al
  __int64 MatchingLcbPair; // rax
  unsigned int v75; // r10d
  __int64 v76; // rax
  char v77; // [rsp+40h] [rbp-D8h]
  char v78; // [rsp+41h] [rbp-D7h] BYREF
  BOOLEAN v79; // [rsp+42h] [rbp-D6h]
  bool v80; // [rsp+43h] [rbp-D5h]
  char v81; // [rsp+44h] [rbp-D4h]
  char v82; // [rsp+45h] [rbp-D3h]
  struct _FILE_OBJECT *v83; // [rsp+48h] [rbp-D0h]
  int v84; // [rsp+50h] [rbp-C8h]
  char v85; // [rsp+54h] [rbp-C4h]
  char v86; // [rsp+55h] [rbp-C3h]
  char v87; // [rsp+56h] [rbp-C2h]
  unsigned int v88; // [rsp+58h] [rbp-C0h]
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp-B8h]
  __int64 v90; // [rsp+68h] [rbp-B0h]
  int v91; // [rsp+70h] [rbp-A8h]
  unsigned int v92; // [rsp+74h] [rbp-A4h]
  int v93; // [rsp+78h] [rbp-A0h]
  KSPIN_LOCK v94; // [rsp+80h] [rbp-98h] BYREF
  PFILE_OBJECT v95; // [rsp+88h] [rbp-90h]
  __int64 v96; // [rsp+90h] [rbp-88h]
  ULONG *v97; // [rsp+98h] [rbp-80h]
  _QWORD *v98; // [rsp+A0h] [rbp-78h]
  _QWORD *v99; // [rsp+A8h] [rbp-70h]
  __int64 v100; // [rsp+B0h] [rbp-68h]
  PFSRTL_ADVANCED_FCB_HEADER v101; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v102; // [rsp+C0h] [rbp-58h]
  char *v103; // [rsp+C8h] [rbp-50h]
  PFSRTL_ADVANCED_FCB_HEADER v104; // [rsp+D0h] [rbp-48h] BYREF
  __int64 v105; // [rsp+D8h] [rbp-40h]
  KSPIN_LOCK v108; // [rsp+130h] [rbp+18h]
  char *v109; // [rsp+138h] [rbp+20h]

  v109 = a4;
  v108 = a3;
  v8 = a3;
  v9 = a1;
  v105 = a1;
  v95 = 0;
  v10 = a3;
  v94 = a3;
  v11 = 0;
  v77 = 0;
  v78 = 0;
  LOBYTE(v7) = 0;
  v93 = v7;
  v81 = 0;
  v12 = 1;
  if ( (*(_DWORD *)(a2 + 4) & 0x8000823) == 1 )
  {
    LOBYTE(v7) = *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) == 0;
    v93 = (unsigned __int8)v7;
    v81 = v7;
  }
LABEL_3:
  v13 = 0;
  v83 = 0;
  v95 = 0;
  v14 = 0;
  v88 = 0;
  LOBYTE(a3) = 0;
  v84 = a3;
  v85 = 0;
  v15 = (_BYTE)v7 && (*(_DWORD *)(v10 + 4) & 0x101) == 0;
  v80 = v15;
  while ( 1 )
  {
    v16 = *(_QWORD *)(v10 + 48);
    if ( v16 == v10 + 48 )
      goto LABEL_76;
    if ( v10 == v8 )
      v17 = a4;
    else
      v17 = (char *)(v16 - 56);
    if ( *((_DWORD *)v17 + 47) )
      goto LABEL_211;
    if ( (*((_DWORD *)v17 + 1) & 3) == 1 )
    {
      MatchingLcbPair = NtfsFindMatchingLcbPair(v17, v14);
      if ( MatchingLcbPair )
      {
        SetFlagInterlocked(MatchingLcbPair + 4, 1);
        ClearFlagInterlocked(v17 + 4, v75);
      }
      else
      {
        v76 = *((_QWORD *)v17 + 3);
        if ( v76 )
        {
          v13 = v83;
          if ( *(int *)(*(_QWORD *)(v76 + 184) + 176LL) < 0 && *(_DWORD *)(*((_QWORD *)v17 + 6) + 20LL) )
            goto LABEL_211;
          v12 = 1;
          goto LABEL_206;
        }
        v12 = 1;
      }
      v13 = v83;
LABEL_206:
      LOBYTE(a3) = v84;
      LODWORD(v14) = v88;
    }
    v18 = (struct _FILE_OBJECT *)*((_QWORD *)v17 + 3);
    FileObject = v18;
    if ( !v18 )
      break;
    v19 = *((_DWORD *)v17 + 1);
    v88 = v19 | v14;
    if ( v13 )
    {
      LODWORD(a3) = (unsigned __int8)a3;
      if ( v13 != v18 )
        LODWORD(a3) = v12;
      v84 = a3;
      v85 = a3;
    }
    if ( !*((_DWORD *)v17 + 44) && (v19 & 0x20) != 0 )
    {
      v20 = *((_DWORD *)v17 + 46);
      v91 = v20;
      v21 = *(_QWORD *)(*((_QWORD *)v17 + 6) + 96LL) + 4968LL;
      v90 = v21;
      v98 = 0;
      v92 = 0;
      if ( (!v9 || (*(_DWORD *)(v9 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
      {
        McTemplateU0pdpw_EtwWriteTransfer(
          *((unsigned __int16 *)v17 + 36) >> 1,
          v21,
          v21,
          v20,
          (char)v17,
          *((_WORD *)v17 + 36) >> 1,
          *((_QWORD *)v17 + 10));
        v21 = v90;
      }
      v97 = (ULONG *)(v21 + 16);
      ExAcquirePushLockSharedEx(v21 + 16, 0);
      v22 = v20 & (unsigned int)(*(_DWORD *)v90 - 1);
      if ( (unsigned int)v22 < *(_DWORD *)(v90 + 4) )
        v22 = v20 & (unsigned int)(2 * *(_DWORD *)v90 - 1);
      v23 = 16 * (v22 & 0x3FF);
      v102 = v23;
      v99 = (_QWORD *)(v90 + 8 * ((v22 >> 10) + 3));
      ExAcquirePushLockExclusiveEx(v23 + *v99 + 8LL, 0);
      v24 = (_QWORD **)(*v99 + v23);
      v98 = v24;
      while ( 1 )
      {
        v25 = *v24;
        if ( !*v24 )
          break;
        if ( *((_DWORD *)v25 + 4) == v91 && (char *)v25[1] == v17 )
        {
          *v24 = (_QWORD *)*v25;
          ExFreePoolWithTag(v25, 0);
        }
        else
        {
          v24 = (_QWORD **)*v24;
          v98 = v25;
          ++v92;
        }
      }
      if ( v92 > 5 && !*(_DWORD *)(v90 + 8) && *(_DWORD *)v90 < 0x8000u )
        *(_DWORD *)(v90 + 8) = 1;
      ExReleasePushLockEx(v102 + 8 + *v99, 0);
      ExReleasePushLockEx(v97, 0);
      *((_DWORD *)v17 + 46) = 0;
      v18 = FileObject;
      if ( (*((_DWORD *)v17 + 1) & 0x20) != 0 )
        _InterlockedAnd((volatile signed __int32 *)v17 + 1, 0xFFFFFFDF);
    }
    p_WaitListHead = &v18->Event.Header.WaitListHead;
    FsRtlAcquireHeaderMutex(&v18->LastLock, &v18->Event.Header.WaitListHead);
    if ( *((_DWORD *)v17 + 44) )
    {
      FsRtlReleaseHeaderMutex(&FileObject->LastLock, p_WaitListHead);
      v13 = v83;
      goto LABEL_211;
    }
    if ( v17 == v109 )
      *a6 = 1;
    if ( (*((_DWORD *)v17 + 1) & 0x20) != 0 )
    {
      NtfsRemoveHashEntry(v9, *(_QWORD *)(*((_QWORD *)v17 + 6) + 96LL) + 4968LL, *((unsigned int *)v17 + 46), v17);
      *((_DWORD *)v17 + 46) = 0;
      ClearFlagInterlocked(v17 + 4, 32);
    }
    NtfsRemovePrefix(v31, v17);
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*((_QWORD *)v17 + 6) + 104LL) + 8LL));
    v32 = (char *)*((_QWORD *)v17 + 15);
    while ( v32 != v17 + 120 )
    {
      v67 = v32;
      v68 = *(char **)v32;
      v32 = *(char **)v32;
      if ( *((_QWORD *)v67 + 2) )
      {
        if ( *((char **)v68 + 1) != v67 )
          goto LABEL_133;
        v69 = (char **)*((_QWORD *)v67 + 1);
        if ( *v69 != v67 )
          goto LABEL_133;
        *v69 = v68;
        *((_QWORD *)v68 + 1) = v69;
        *((_QWORD *)v67 + 2) = 0;
      }
    }
    v33 = (char **)*((_QWORD *)v17 + 1);
    if ( v33[1] != v17 + 8
      || (v34 = (void **)*((_QWORD *)v17 + 2), *v34 != v17 + 8)
      || (*v34 = v33, v33[1] = (char *)v34, v35 = (char **)*((_QWORD *)v17 + 7), v35[1] != v17 + 56)
      || (v36 = (void **)*((_QWORD *)v17 + 8), *v36 != v17 + 56) )
    {
LABEL_133:
      __fastfail(3u);
    }
    *v36 = v35;
    v35[1] = (char *)v36;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*((_QWORD *)v17 + 6) + 104LL) + 8LL));
    v37 = (char *)*((_QWORD *)v17 + 24);
    if ( v37 != v17 + 144 )
    {
      ExFreePoolWithTag(v37, 0);
      *((_QWORD *)v17 + 24) = 0;
    }
    if ( *((_DWORD *)v17 + 46) )
      MicrosoftTelemetryAssertTriggeredMsgKM("(*Lcb)->HashValue == 0");
    *(_WORD *)v17 = 0;
    v38 = *((_QWORD *)v17 + 6);
    if ( v17 != (char *)(v38 + 1144) && v17 != (char *)(v38 + 1352) )
    {
      v44 = v17;
      v103 = v17;
      v45 = 53;
      v100 = 53;
      if ( ((unsigned __int8)v17 & 4) != 0 )
      {
        *(_DWORD *)v17 = -1163005939;
        v45 = 52;
        v100 = 52;
        v44 = v17 + 4;
        v103 = v17 + 4;
      }
      memset64(v44, 0xBAADF00DBAADF00DuLL, v45 >> 1);
      if ( (v45 & 1) != 0 )
        *(_DWORD *)&v44[4 * v45 - 4] = -1163005939;
      ExFreeToLookasideListEx(&NtfsLcbLookasideList, v17);
      v8 = v108;
    }
    v39 = FileObject;
    if ( !(_BYTE)v84 && FileObject[2].FileObjectExtension == &FileObject[2].FileObjectExtension )
    {
      IrpListLock = FileObject->IrpListLock;
      if ( *(int *)(IrpListLock + 176) >= 0 )
      {
        v54 = NtfsAcquireExclusiveFcb(v9, IrpListLock, FileObject, 3);
        v55 = v83;
        if ( v54 )
          v55 = v39;
        v83 = v55;
        v95 = v55;
      }
    }
    FsRtlReleaseHeaderMutex(&v39->LastLock, p_WaitListHead);
    if ( v10 == v8 )
    {
      v13 = v83;
LABEL_76:
      if ( *(_QWORD *)(v10 + 48) != v10 + 48 )
        goto LABEL_31;
      if ( v80 && ((*(_DWORD *)(v10 + 184) & 0x20000000) != 0 || (*(_DWORD *)(v10 + 4) & 0x10) != 0) )
      {
        NtfsUpdateStandardInformation(v9, v10);
        NtfsCheckpointCurrentTransaction(v9);
      }
      v40 = *(_QWORD *)(v10 + 64);
      if ( v40 == v10 + 64 )
        goto LABEL_86;
      v41 = v40 - 168;
      v104 = (PFSRTL_ADVANCED_FCB_HEADER)v41;
      if ( (*(_DWORD *)(v41 + 512) & 0x100000) != 0 || *(_DWORD *)(v41 + 208) )
        goto LABEL_86;
      if ( (unsigned __int16)(*(_WORD *)v41 - 1797) > 1u )
      {
        FsRtlAcquireHeaderMutex(v41 + 120, v41 + 160);
        v43 = *(_QWORD *)(v41 + 640);
        FsRtlReleaseHeaderMutex(v41 + 120, v41 + 160);
        if ( v43 != v41 + 640 )
          goto LABEL_86;
        v9 = a1;
      }
      v42 = (_DWORD *)(v41 + 212);
      if ( !*(_DWORD *)(v41 + 212) )
      {
LABEL_85:
        NtfsDeleteScb(v9, &v104);
        goto LABEL_86;
      }
      if ( !*(_QWORD *)(v41 + 280) )
        goto LABEL_86;
      if ( (*(_DWORD *)(v41 + 200) & 0x400) != 0 )
        goto LABEL_86;
      v46 = *(_QWORD *)(v41 + 184);
      if ( (*(_DWORD *)(v46 + 4) & 0x20100) != 0 )
        goto LABEL_86;
      v91 = *(_WORD *)(*(_QWORD *)(v41 + 184) + 188LL) == 0;
      v84 = v91;
      v47 = 0;
      v86 = 0;
      if ( !*(_QWORD *)(v41 + 280) || (*(_DWORD *)(v41 + 200) & 0x400) != 0 )
        goto LABEL_121;
      if ( !*(_QWORD *)(v41 + 16) )
      {
LABEL_105:
        v90 = v41 + 184;
        if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v41 + 184) + 104LL) + 64LL))
          || !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v41 + 192) + 2160LL))
          && (*(_DWORD *)(v9 + 16) & 0x40000000) == 0 )
        {
          ExAcquirePushLockExclusiveEx(*(_QWORD *)v90 + 200LL, 0);
          v47 = 1;
          v86 = 1;
        }
        NtfsUnlockSystemFilePages(v9, v41, v47, 1);
        FileObject = *(PFILE_OBJECT *)(v41 + 280);
        v48 = FileObject;
        *(_QWORD *)(v41 + 280) = 0;
        FsContext = v48->FsContext;
        if ( FsContext && (FsContext[50] & 0x4000) == 0 )
        {
          *(_DWORD *)&v48->FileName.Length = 0;
          v48->FileName.Buffer = 0;
        }
        v50 = v47 == 0;
        v51 = (__int64 *)v90;
        if ( !v50 )
        {
          ExReleasePushLockEx(*(_QWORD *)v90 + 200LL, 0);
          v48 = FileObject;
        }
        if ( v48->PrivateCacheMap )
        {
          v52 = &NtfsLarge0;
          if ( !(_BYTE)v91 )
            v52 = 0;
          CcUninitializeCacheMap(v48, v52, 0);
          v48 = FileObject;
        }
        if ( *(_QWORD *)(v41 + 16) )
        {
          if ( *(_WORD *)v41 != 1794 )
            v41 = *v51;
          ExReleaseResourceLite(*(PERESOURCE *)(v41 + 112));
          v48 = FileObject;
        }
        ObfDereferenceObject(v48);
        goto LABEL_121;
      }
      v70 = 0;
      v79 = 0;
      if ( *(_WORD *)v41 == 1794 )
        v71 = (PFILE_OBJECT)v41;
      else
        v71 = (PFILE_OBJECT)v46;
      FileObject = v71;
      p_Waiters = &v71->Waiters;
      v97 = &v71->Waiters;
      v90 = (__int64)&v71->Waiters;
      while ( 2 )
      {
        if ( ((__int64)v71->Vpb & 0x200) == 0 )
          goto LABEL_176;
        if ( v9 )
        {
          if ( (*(_DWORD *)(v9 + 16) & 0x40000000) != 0 )
            goto LABEL_176;
          v90 = (__int64)p_Waiters;
          if ( (*(_DWORD *)(*(_QWORD *)(v9 + 144) + 16LL) & 0x40000000) != 0 )
            goto LABEL_176;
        }
        IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v71->FileName.Buffer + 1080));
        v70 = v79;
        if ( IsResourceAcquiredExclusiveLite )
        {
          v71 = FileObject;
LABEL_176:
          if ( v70 )
            goto LABEL_105;
          v90 = (__int64)&v71->Waiters;
          v70 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)&v71->Waiters, 0);
          v79 = v70;
          if ( !v70 )
            goto LABEL_121;
          v71 = FileObject;
          p_Waiters = v97;
          continue;
        }
        break;
      }
      if ( v79 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)v90);
        v79 = 0;
      }
LABEL_121:
      if ( !*v42 )
        goto LABEL_85;
LABEL_86:
      if ( *(_QWORD *)(v10 + 64) != v10 + 64 )
        goto LABEL_49;
      ExAcquirePushLockExclusiveEx(a2 + 656, 0);
      v78 = 1;
      if ( *(_DWORD *)(v10 + 28) )
      {
        ExReleasePushLockEx(a2 + 656, 0);
        v78 = 0;
LABEL_49:
        v11 = v77;
        v9 = a1;
        goto LABEL_30;
      }
      if ( v10 == v108 )
        *a7 = 1;
      v9 = a1;
      NtfsDeleteFcb(a1, &v94, (unsigned __int64 *)&v78);
      v11 = 0;
      v10 = v94;
LABEL_30:
      v13 = v83;
LABEL_31:
      if ( !v13 )
        goto LABEL_211;
      if ( v11 )
      {
        NtfsReleaseFcbEx(v9, v10, 0);
        v13 = v83;
      }
      v10 = v13->IrpListLock;
      v94 = v10;
      v77 = 1;
      v83 = 0;
      v95 = 0;
      v96 = 0;
      v26 = 0;
      while ( 1 )
      {
        v27 = v10 + 64;
        v28 = *(_QWORD *)(v10 + 64);
        if ( v28 == v10 + 64 )
          break;
        v29 = *(_QWORD *)(v10 + 64);
        if ( v26 )
          v29 = *(_QWORD *)(v26 + 168);
        v26 = v29 - 168;
        if ( v29 == v27 )
          v26 = 0;
        if ( !v26 )
          goto LABEL_51;
        if ( *(_DWORD *)(v26 + 256) != 32 || (*(_DWORD *)(v26 + 512) & 0x40) != 0 || v28 == *(_QWORD *)(v10 + 72) )
        {
          v101 = (PFSRTL_ADVANCED_FCB_HEADER)v26;
          v82 = 0;
          if ( (*(_DWORD *)(v26 + 512) & 0x100000) == 0 && !*(_DWORD *)(v26 + 208) )
          {
            if ( (unsigned __int16)(*(_WORD *)v26 - 1797) <= 1u
              || (FsRtlAcquireHeaderMutex(v26 + 120, v26 + 160),
                  v60 = *(_QWORD *)(v26 + 640),
                  FsRtlReleaseHeaderMutex(v26 + 120, v26 + 160),
                  v60 == v26 + 640) )
            {
              if ( a5 && *(_DWORD *)(*(_QWORD *)(v26 + 288) + 4LL) )
              {
                NtfsAddScbToFspClose(v9, (_QWORD *)v26, 0, v105 == *(_QWORD *)(v9 + 144), 0);
              }
              else
              {
                if ( !*(_DWORD *)(v26 + 212) )
                  goto LABEL_47;
                if ( *(_QWORD *)(v26 + 280)
                  && (*(_DWORD *)(v26 + 200) & 0x400) == 0
                  && (*(_DWORD *)(*(_QWORD *)(v26 + 184) + 4LL) & 0x20100) == 0 )
                {
                  v61 = *(_WORD *)(*(_QWORD *)(v26 + 184) + 188LL) == 0;
                  v91 = v61;
                  v62 = 0;
                  v87 = 0;
                  if ( !*(_QWORD *)(v26 + 16) || (unsigned __int8)NtfsAcquirePagingResourceExclusive(v9, v26, 0) )
                  {
                    if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v26 + 184) + 104LL)
                                                                       + 64LL))
                      || !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v26 + 192) + 2160LL))
                      && (*(_DWORD *)(v9 + 16) & 0x40000000) == 0 )
                    {
                      ExAcquirePushLockExclusiveEx(*(_QWORD *)(v26 + 184) + 200LL, 0);
                      v62 = 1;
                      v87 = 1;
                    }
                    NtfsUnlockSystemFilePages(v9, v26, v62, 1);
                    v63 = *(_QWORD *)(v26 + 280);
                    *(_QWORD *)(v26 + 280) = 0;
                    v64 = *(_QWORD *)(v63 + 24);
                    if ( v64 && (*(_DWORD *)(v64 + 200) & 0x4000) == 0 )
                    {
                      *(_DWORD *)(v63 + 88) = 0;
                      *(_QWORD *)(v63 + 96) = 0;
                    }
                    if ( v62 )
                      ExReleasePushLockEx(*(_QWORD *)(v26 + 184) + 200LL, 0);
                    if ( *(_QWORD *)(v63 + 48) )
                    {
                      v65 = &NtfsLarge0;
                      if ( !v61 )
                        v65 = 0;
                      CcUninitializeCacheMap((PFILE_OBJECT)v63, v65, 0);
                    }
                    if ( *(_QWORD *)(v26 + 16) )
                    {
                      if ( *(_WORD *)v26 == 1794 )
                        v66 = v26;
                      else
                        v66 = *(_QWORD *)(v26 + 184);
                      ExReleaseResourceLite(*(PERESOURCE *)(v66 + 112));
                    }
                    ObfDereferenceObject((PVOID)v63);
                  }
                  if ( !*(_DWORD *)(v26 + 212) )
                  {
LABEL_47:
                    NtfsDeleteScb(v9, &v101);
                    v82 = 1;
                    v26 = 0;
                    v96 = 0;
                    continue;
                  }
                }
              }
            }
          }
          if ( v96 )
            goto LABEL_51;
        }
        else
        {
          v56 = (KSPIN_LOCK *)(v26 + 168);
          v57 = *v56;
          if ( *v56 == v27 )
            goto LABEL_51;
          if ( *(KSPIN_LOCK **)(v57 + 8) != v56 )
            goto LABEL_133;
          v58 = (KSPIN_LOCK **)v56[1];
          if ( *v58 != v56 )
            goto LABEL_133;
          *v58 = (KSPIN_LOCK *)v57;
          *(_QWORD *)(v57 + 8) = v58;
          v59 = *(KSPIN_LOCK ***)(v10 + 72);
          if ( *v59 != (KSPIN_LOCK *)v27 )
            goto LABEL_133;
          *v56 = v27;
          v56[1] = (KSPIN_LOCK)v59;
          *v59 = v56;
          *(_QWORD *)(v10 + 72) = v56;
          v26 = 0;
          v96 = 0;
        }
      }
      if ( *(_DWORD *)(v10 + 24) )
      {
LABEL_51:
        v11 = 1;
        v13 = v83;
        goto LABEL_211;
      }
      LOBYTE(v7) = v93;
      v11 = 1;
      v8 = v108;
      a4 = v109;
      v12 = 1;
      goto LABEL_3;
    }
    v13 = v83;
    v14 = v88;
    LODWORD(a3) = v84;
    a4 = v109;
    v12 = 1;
  }
  MicrosoftTelemetryAssertTriggeredMsgKM("!\"NtfsTeardownFromLcb has an LCB with a NULL SCB\"");
  v13 = v83;
LABEL_211:
  if ( v78 )
  {
    ExReleasePushLockEx(a2 + 656, 0);
    v13 = v83;
  }
  if ( v11 )
  {
    NtfsReleaseFcbEx(v9, v10, 0);
    v13 = v83;
  }
  if ( v13 )
    NtfsReleaseFcbEx(v9, v13->IrpListLock, 0);
}

```

## disassembly

```asm
0x14012a140  mov     [rsp+arg_18], r9
0x14012a145  mov     [rsp+arg_10], r8
0x14012a14a  mov     [rsp+arg_8], rdx
0x14012a14f  mov     qword ptr [rsp+arg_0], rcx
0x14012a154  push    rbx
0x14012a155  push    rsi
0x14012a156  push    rdi
0x14012a157  push    r12
0x14012a159  push    r13
0x14012a15b  push    r14
0x14012a15d  push    r15
0x14012a15f  sub     rsp, 0E0h
0x14012a166  mov     rdi, r8
0x14012a169  mov     r15, rcx
0x14012a16c  mov     [rsp+118h+var_40], rcx
0x14012a174  xor     esi, esi
0x14012a176  mov     [rsp+118h+var_90], rsi
0x14012a17e  mov     r13, r8
0x14012a181  mov     [rsp+118h+var_98], r8
0x14012a189  xor     r12b, r12b
0x14012a18c  mov     [rsp+118h+var_D8], r12b
0x14012a191  mov     [rsp+118h+var_D7], sil
0x14012a196  xor     bl, bl
0x14012a198  mov     [rsp+118h+var_A0], ebx
0x14012a19c  mov     [rsp+118h+var_D4], bl
0x14012a1a0  mov     eax, [rdx+4]
0x14012a1a3  and     eax, 8000823h
0x14012a1a8  mov     r10d, 1
0x14012a1ae  cmp     eax, r10d
0x14012a1b1  jnz     short loc_14012A1CC
0x14012a1b3  mov     rax, [rcx+90h]
0x14012a1ba  movzx   ebx, bl
0x14012a1bd  cmp     [rax+18h], esi
0x14012a1c0  cmovz   ebx, r10d
0x14012a1c4  mov     [rsp+118h+var_A0], ebx
0x14012a1c8  mov     [rsp+118h+var_D4], bl
0x14012a1cc  mov     rcx, rsi
0x14012a1cf  mov     [rsp+118h+var_D0], rcx
0x14012a1d4  mov     [rsp+118h+var_90], rcx
0x14012a1dc  mov     edx, esi
0x14012a1de  mov     [rsp+118h+var_C0], edx
0x14012a1e2  xor     r8b, r8b
0x14012a1e5  mov     [rsp+118h+var_C8], r8d
0x14012a1ea  mov     [rsp+118h+var_C4], r8b
0x14012a1ef  test    bl, bl
0x14012a1f1  jz      loc_14012A8D0
0x14012a1f7  test    dword ptr [r13+4], 101h
0x14012a1ff  jnz     loc_14012A8D0
0x14012a205  mov     al, 1
0x14012a207  mov     [rsp+118h+var_D5], al
0x14012a20b  lea     rax, [r13+30h]
0x14012a20f  mov     rbx, [rax]
0x14012a212  cmp     rbx, rax
0x14012a215  jz      loc_14012A739
0x14012a21b  cmp     r13, rdi
0x14012a21e  jnz     loc_14012AB14
0x14012a224  mov     rbx, r9
0x14012a227  cmp     dword ptr [rbx+0BCh], 0
0x14012a22e  jnz     loc_14012B1F3
0x14012a234  mov     eax, [rbx+4]
0x14012a237  and     al, 3
0x14012a239  cmp     al, 1
0x14012a23b  jz      loc_14012B0C7
0x14012a241  mov     r9, [rbx+18h]
0x14012a245  mov     [rsp+118h+FileObject], r9
0x14012a24a  test    r9, r9
0x14012a24d  jz      loc_14012B0B1
0x14012a253  mov     eax, [rbx+4]
0x14012a256  or      edx, eax
0x14012a258  mov     [rsp+118h+var_C0], edx
0x14012a25c  test    rcx, rcx
0x14012a25f  jnz     loc_14012B141
0x14012a265  cmp     dword ptr [rbx+0B0h], 0
0x14012a26c  jnz     loc_14012A5D7
0x14012a272  test    al, 20h
0x14012a274  jz      loc_14012A5D7
0x14012a27a  mov     r14d, [rbx+0B8h]
0x14012a281  mov     [rsp+118h+var_A8], r14d
0x14012a286  mov     rax, [rbx+30h]
0x14012a28a  mov     rdx, [rax+60h]
0x14012a28e  add     rdx, 1368h
0x14012a295  mov     [rsp+118h+var_B0], rdx
0x14012a29a  mov     [rsp+118h+var_78], rsi
0x14012a2a2  mov     [rsp+118h+var_A4], esi
0x14012a2a6  test    r15, r15
0x14012a2a9  jz      short loc_14012A2B6
0x14012a2ab  mov     eax, [r15+10h]
0x14012a2af  bt      rax, 14h
0x14012a2b4  jb      short loc_14012A2C3
0x14012a2b6  cmp     byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 0
0x14012a2bd  jl      loc_14012B15B
0x14012a2c3  lea     rax, [rdx+10h]
0x14012a2c7  mov     [rsp+118h+var_80], rax
0x14012a2cf  xor     edx, edx
0x14012a2d1  mov     rcx, rax
0x14012a2d4  call    cs:__imp_ExAcquirePushLockSharedEx
0x14012a2db  nop     dword ptr [rax+rax+00h]
0x14012a2e0  mov     rdx, [rsp+118h+var_B0]
0x14012a2e5  mov     ecx, [rdx]
0x14012a2e7  lea     eax, [rcx-1]
0x14012a2ea  and     eax, r14d
0x14012a2ed  cmp     eax, [rdx+4]
0x14012a2f0  jnb     short loc_14012A2FC
0x14012a2f2  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rcx*2]
0x14012a2f9  and     eax, r14d
0x14012a2fc  mov     r14d, eax
0x14012a2ff  and     r14d, 3FFh
0x14012a306  shl     r14, 4
0x14012a30a  mov     [rsp+118h+var_58], r14
0x14012a312  shr     rax, 0Ah
0x14012a316  add     rax, 3
0x14012a31a  lea     rax, [rdx+rax*8]
0x14012a31e  mov     [rsp+118h+var_70], rax
0x14012a326  mov     rcx, [rax]
0x14012a329  add     rcx, 8
0x14012a32d  add     rcx, r14
0x14012a330  xor     edx, edx
0x14012a332  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012a339  nop     dword ptr [rax+rax+00h]
0x14012a33e  mov     rdx, [rsp+118h+var_70]
0x14012a346  add     r14, [rdx]
0x14012a349  mov     [rsp+118h+var_78], r14
0x14012a351  mov     rcx, [r14]; P
0x14012a354  test    rcx, rcx
0x14012a357  jz      loc_14012A577
0x14012a35d  mov     eax, [rsp+118h+var_A8]
0x14012a361  cmp     [rcx+10h], eax
0x14012a364  jz      loc_14012A7DD
0x14012a36a  mov     r14, rcx
0x14012a36d  mov     [rsp+118h+var_78], rcx
0x14012a375  inc     [rsp+118h+var_A4]
0x14012a379  jmp     short loc_14012A351
0x14012a37b  mov     rdi, [rsp+118h+arg_8]
0x14012a383  xor     edx, edx
0x14012a385  lea     rcx, [rdi+290h]
0x14012a38c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012a393  nop     dword ptr [rax+rax+00h]
0x14012a398  mov     [rsp+118h+var_D7], 1
0x14012a39d  cmp     dword ptr [r13+1Ch], 0
0x14012a3a2  jnz     loc_14012A50E
0x14012a3a8  cmp     r13, [rsp+118h+arg_10]
0x14012a3b0  jnz     short loc_14012A3BD
0x14012a3b2  mov     rax, [rsp+118h+arg_30]
0x14012a3ba  mov     byte ptr [rax], 1
0x14012a3bd  lea     r8, [rsp+118h+var_D7]
0x14012a3c2  lea     rdx, [rsp+118h+var_98]
0x14012a3ca  mov     r15, qword ptr [rsp+118h+arg_0]
0x14012a3d2  mov     rcx, r15
0x14012a3d5  call    NtfsDeleteFcb
0x14012a3da  xor     r12b, r12b
0x14012a3dd  mov     [rsp+118h+var_D8], r12b
0x14012a3e2  mov     r13, [rsp+118h+var_98]
0x14012a3ea  xor     esi, esi
0x14012a3ec  mov     rcx, [rsp+118h+var_D0]
0x14012a3f1  test    rcx, rcx
0x14012a3f4  jz      loc_14012B1F3
0x14012a3fa  test    r12b, r12b
0x14012a3fd  jnz     loc_14012B083
0x14012a403  mov     r13, [rcx+0B8h]
0x14012a40a  mov     [rsp+118h+var_98], r13
0x14012a412  mov     [rsp+118h+var_D8], 1
0x14012a417  mov     rdx, rsi
0x14012a41a  mov     [rsp+118h+var_D0], rdx
0x14012a41f  mov     [rsp+118h+var_90], rdx
0x14012a427  mov     rax, rsi
0x14012a42a  mov     [rsp+118h+var_88], rax
0x14012a432  mov     r12, rsi
0x14012a435  lea     rcx, [r13+40h]
0x14012a439  mov     rdx, [rcx]
0x14012a43c  cmp     rdx, rcx
0x14012a43f  jz      loc_14012A53B
0x14012a445  test    rax, rax
0x14012a448  jnz     loc_14012ABAF
0x14012a44e  test    r12, r12
0x14012a451  mov     rax, rdx
0x14012a454  jz      short loc_14012A45E
0x14012a456  mov     rax, [r12+0A8h]
0x14012a45e  lea     r12, [rax-0A8h]
0x14012a465  cmp     rax, rcx
0x14012a468  cmovz   r12, rsi
0x14012a46c  test    r12, r12
0x14012a46f  jz      loc_14012A542
0x14012a475  cmp     dword ptr [r12+100h], 20h ; ' '
0x14012a47e  jz      loc_14012AABB
0x14012a484  mov     [rsp+118h+var_60], r12
0x14012a48c  mov     [rsp+118h+var_D3], 0
0x14012a491  test    dword ptr [r12+200h], 100000h
0x14012a49d  jnz     loc_14012AB97
0x14012a4a3  cmp     dword ptr [r12+0D0h], 0
0x14012a4ac  jnz     loc_14012AB97
0x14012a4b2  movzx   eax, word ptr [r12]
0x14012a4b7  mov     ecx, 705h
0x14012a4bc  sub     ax, cx
0x14012a4bf  cmp     ax, 1
0x14012a4c3  ja      loc_14012AB1D
0x14012a4c9  cmp     [rsp+118h+arg_20], 0
0x14012a4d1  jnz     loc_14012AFEC
0x14012a4d7  cmp     dword ptr [r12+0D4h], 0
0x14012a4e0  jnz     loc_14012AB88
0x14012a4e6  lea     rdx, [rsp+118h+var_60]
0x14012a4ee  mov     rcx, r15
0x14012a4f1  call    NtfsDeleteScb
0x14012a4f6  mov     [rsp+118h+var_D3], 1
0x14012a4fb  mov     r12, rsi
0x14012a4fe  mov     rax, rsi
0x14012a501  mov     [rsp+118h+var_88], rax
0x14012a509  jmp     loc_14012A435
0x14012a50e  xor     edx, edx
0x14012a510  lea     rcx, [rdi+290h]
0x14012a517  call    cs:__imp_ExReleasePushLockEx
0x14012a51e  nop     dword ptr [rax+rax+00h]
0x14012a523  mov     [rsp+118h+var_D7], 0
0x14012a528  movzx   r12d, [rsp+118h+var_D8]
0x14012a52e  mov     r15, qword ptr [rsp+118h+arg_0]
0x14012a536  jmp     loc_14012A3EA
0x14012a53b  cmp     dword ptr [r13+18h], 0
0x14012a540  jz      short loc_14012A552
0x14012a542  movzx   r12d, [rsp+118h+var_D8]
0x14012a548  mov     rcx, [rsp+118h+var_D0]
0x14012a54d  jmp     loc_14012B1F3
0x14012a552  mov     ebx, [rsp+118h+var_A0]
0x14012a556  movzx   r12d, [rsp+118h+var_D8]
0x14012a55c  mov     rdi, [rsp+118h+arg_10]
0x14012a564  mov     r9, [rsp+118h+arg_18]
0x14012a56c  mov     r10d, 1
0x14012a572  jmp     loc_14012A1CC
0x14012a577  cmp     [rsp+118h+var_A4], 5
0x14012a57c  ja      loc_14012ACCA
0x14012a582  mov     rax, [rsp+118h+var_70]
0x14012a58a  mov     rcx, [rax]
0x14012a58d  mov     rdx, [rsp+118h+var_58]
0x14012a595  add     rdx, 8
0x14012a599  add     rcx, rdx
0x14012a59c  xor     edx, edx
0x14012a59e  call    cs:__imp_ExReleasePushLockEx
0x14012a5a5  nop     dword ptr [rax+rax+00h]
0x14012a5aa  xor     edx, edx
0x14012a5ac  mov     rcx, [rsp+118h+var_80]
0x14012a5b4  call    cs:__imp_ExReleasePushLockEx
0x14012a5bb  nop     dword ptr [rax+rax+00h]
0x14012a5c0  mov     [rbx+0B8h], esi
0x14012a5c6  mov     eax, [rbx+4]
0x14012a5c9  mov     r9, [rsp+118h+FileObject]
0x14012a5ce  test    al, 20h
0x14012a5d0  jz      short loc_14012A5D7
0x14012a5d2  lock and dword ptr [rbx+4], 0FFFFFFDFh
0x14012a5d7  lea     r14, [r9+0A0h]
0x14012a5de  lea     rcx, [r9+78h]
0x14012a5e2  mov     rdx, r14
0x14012a5e5  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14012a5ec  nop     dword ptr [rax+rax+00h]
0x14012a5f1  cmp     dword ptr [rbx+0B0h], 0
0x14012a5f8  jnz     loc_14012AB66
0x14012a5fe  cmp     rbx, [rsp+118h+arg_18]
0x14012a606  jnz     short loc_14012A613
0x14012a608  mov     rax, [rsp+118h+arg_28]
0x14012a610  mov     byte ptr [rax], 1
0x14012a613  mov     eax, [rbx+4]
0x14012a616  test    al, 20h
0x14012a618  jnz     loc_14012B188
0x14012a61e  mov     rdx, rbx
0x14012a621  call    NtfsRemovePrefix
0x14012a626  mov     rax, [rbx+30h]
0x14012a62a  mov     rcx, [rax+68h]
0x14012a62e  add     rcx, 8; FastMutex
0x14012a632  call    cs:__imp_ExAcquireFastMutex
0x14012a639  nop     dword ptr [rax+rax+00h]
0x14012a63e  lea     rax, [rbx+78h]
0x14012a642  mov     rcx, [rax]
0x14012a645  cmp     rcx, rax
0x14012a648  jnz     loc_14012AE65
0x14012a64e  lea     rax, [rbx+8]
0x14012a652  mov     rdx, [rax]
0x14012a655  cmp     [rdx+8], rax
0x14012a659  jnz     loc_14012AB0D
0x14012a65f  mov     rcx, [rbx+10h]
0x14012a663  cmp     [rcx], rax
0x14012a666  jnz     loc_14012AB0D
0x14012a66c  mov     [rcx], rdx
0x14012a66f  mov     [rdx+8], rcx
0x14012a673  lea     rax, [rbx+38h]
0x14012a677  mov     rdx, [rax]
0x14012a67a  cmp     [rdx+8], rax
0x14012a67e  jnz     loc_14012AB0D
0x14012a684  mov     rcx, [rbx+40h]
0x14012a688  cmp     [rcx], rax
0x14012a68b  jnz     loc_14012AB0D
0x14012a691  mov     [rcx], rdx
0x14012a694  mov     [rdx+8], rcx
0x14012a698  mov     rax, [rbx+30h]
0x14012a69c  mov     rcx, [rax+68h]
0x14012a6a0  add     rcx, 8; FastMutex
0x14012a6a4  call    cs:__imp_ExReleaseFastMutex
0x14012a6ab  nop     dword ptr [rax+rax+00h]
0x14012a6b0  mov     rcx, [rbx+0C0h]; P
0x14012a6b7  lea     rax, [rbx+90h]
0x14012a6be  cmp     rcx, rax
0x14012a6c1  jz      short loc_14012A6D8
0x14012a6c3  xor     edx, edx; Tag
0x14012a6c5  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```
