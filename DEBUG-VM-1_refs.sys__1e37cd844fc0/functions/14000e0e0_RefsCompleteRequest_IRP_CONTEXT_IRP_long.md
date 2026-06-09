# RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)

- ea: `0x14000e0e0`
- end: `0x14000ed04`
- name: `?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z`
- size: `3108`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, PIRP Irp, NTSTATUS Status)`
- caller_count: `138`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a650`
- `0x14000b1b0`
- `0x14000c180`
- `0x14000d0c0`
- `0x14000d820`
- `0x14000dfe0`
- `0x140099db0`
- `0x1400a2c60`
- `0x1400aeae0`
- `0x1400b9530`
- `0x1400ba4d0`
- `0x1400bc5b0`
- `0x1400bd090`
- `0x1400ce2a0`
- `0x1400cee08`
- `0x1400ef254`
- `0x1400efcac`
- `0x1400f64a4`
- `0x1400f6650`
- `0x1400f7350`
- `0x140109690`
- `0x140109750`
- `0x14010b330`
- `0x14028d4ec`
- `0x14028dacc`
- `0x140291a00`
- `0x140294008`
- `0x14029d114`
- `0x1402a1288`
- `0x1402a1e94`
- `0x1402a37bc`
- `0x1402a3f80`
- `0x1402a7120`
- `0x1402ac410`
- `0x1402af8dc`
- `0x1402b0518`
- `0x1402b0838`
- `0x1402b0d14`
- `0x1402b1658`
- `0x1402b1b38`
- `0x1402b1d38`
- `0x1402b2768`
- `0x1402b2a90`
- `0x1402b2c70`
- `0x1402b39ec`
- `0x1402b3dbc`
- `0x1402b3e3c`
- `0x1402b412c`
- `0x1402b4908`
- `0x1402b5944`

## callees

- `0x14000e0e0`
- `0x14000ed10`
- `0x1400862c0`
- `0x1400cedec`
- `0x1400d0fd8`
- `0x1400fd078`
- `0x140302eb0`
- `0x140323140`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e500`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e500`
- `ntoskrnl!IofCompleteRequest` at `0x14000e4a6`
- `ntoskrnl!IofCompleteRequest` at `0x14000e4a6`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e518`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e518`
- `ntoskrnl!KeSetEvent` at `0x14000e7f3`
- `ntoskrnl!KeSetEvent` at `0x14000e7f3`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14000e8cb`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14000e8cb`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000ebf0`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000ec07`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000e42c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000e77d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ea2b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000e42c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000e77d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000ea2b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000ecc4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000ecc4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000e6be`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000e7a8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000e968`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000e6be`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000e7a8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000e968`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e6cd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e7b7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e977`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e6cd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e7b7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e977`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e70d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e803`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e9bc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e70d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e803`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e9bc`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000e719`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000e80f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000e9c8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000e719`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000e80f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000e9c8`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000e551`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000e551`
- `ntoskrnl!ExReleaseFastResource` at `0x14000e574`
- `ntoskrnl!ExReleaseFastResource` at `0x14000e5d6`
- `ntoskrnl!ExReleaseFastResource` at `0x14000e88c`
- `ntoskrnl!ExReleaseFastResource` at `0x14000ec4b`
- `ntoskrnl!ExReleaseFastResource` at `0x14000e574`
- `ntoskrnl!ExReleaseFastResource` at `0x14000e5d6`
- `ntoskrnl!ExReleaseFastResource` at `0x14000e88c`
- `ntoskrnl!ExReleaseFastResource` at `0x14000ec4b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ea58`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ec67`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ea58`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ec67`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eca0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eca0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecec`

## pseudocode

```c
void __fastcall RefsCompleteRequest(PSECURITY_SUBJECT_CONTEXT *a1, PIRP Irp, NTSTATUS Status)
{
  PSECURITY_SUBJECT_CONTEXT *v3; // r13
  struct _FILE_OBJECT *v6; // rdx
  unsigned int v7; // r8d
  PSECURITY_SUBJECT_CONTEXT v9; // r10
  PSECURITY_SUBJECT_CONTEXT v10; // r11
  int *v11; // rax
  volatile signed __int64 *v12; // rax
  PSECURITY_SUBJECT_CONTEXT v13; // rax
  char v14; // al
  PSECURITY_SUBJECT_CONTEXT v15; // rsi
  int v16; // eax
  struct _IRP_CONTEXT *v17; // rbx
  char *v18; // r15
  struct _IRP_CONTEXT *v19; // rcx
  PSECURITY_SUBJECT_CONTEXT v20; // rax
  __int16 v21; // r8
  _QWORD *v22; // rcx
  struct _IRP_CONTEXT *v23; // r13
  struct _IRP_CONTEXT *v24; // rax
  PSECURITY_SUBJECT_CONTEXT *v25; // rsi
  char *v26; // r13
  PSECURITY_SUBJECT_CONTEXT *v27; // rsi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v29; // r8
  unsigned int i; // edx
  __int64 v31; // rcx
  PSECURITY_SUBJECT_CONTEXT *v32; // rax
  struct _IRP_CONTEXT *v33; // rsi
  struct _IRP_CONTEXT *v34; // rax
  PSECURITY_SUBJECT_CONTEXT *v35; // r15
  PSECURITY_SUBJECT_CONTEXT *m; // rcx
  int v37; // ecx
  unsigned __int64 v38; // rax
  _QWORD **v39; // rbx
  _QWORD *v40; // rcx
  bool v41; // zf
  int v42; // eax
  PSECURITY_SUBJECT_CONTEXT v43; // rcx
  unsigned int v44; // eax
  struct _NPAGED_LOOKASIDE_LIST *v45; // r9
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *FsContext; // rcx
  PFILE_OBJECT FileObject; // rax
  _QWORD *v49; // rax
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  struct _IRP_CONTEXT *j; // rcx
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v54; // rcx
  int v55; // ecx
  char v56; // cl
  PSECURITY_SUBJECT_CONTEXT v57; // rcx
  struct _FAST_MUTEX *v58; // rbx
  PSECURITY_SUBJECT_CONTEXT v59; // rdx
  PSECURITY_SUBJECT_CONTEXT **v60; // rcx
  unsigned int v61; // eax
  struct _FAST_MUTEX *PrimaryToken; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v63; // rcx
  _QWORD *v64; // rcx
  __int64 v65; // rcx
  struct _IRP_CONTEXT *k; // rax
  PSECURITY_SUBJECT_CONTEXT v67; // rdx
  struct _ERESOURCE *ClientToken; // rcx
  PVOID *p_ProcessAuditId; // rdx
  BOOLEAN IsOperationSynchronous; // al
  struct _IRP_CONTEXT *v71; // rax
  PSECURITY_SUBJECT_CONTEXT v72; // rcx
  struct _FAST_MUTEX *v73; // rsi
  PSECURITY_SUBJECT_CONTEXT v74; // rdx
  PSECURITY_SUBJECT_CONTEXT **v75; // rcx
  unsigned int v76; // eax
  struct _VCB *v77; // rcx
  volatile signed __int64 *v78; // rax
  struct _FILE_OBJECT *v79; // [rsp+30h] [rbp-68h]
  PSECURITY_SUBJECT_CONTEXT v80; // [rsp+38h] [rbp-60h]
  PSECURITY_SUBJECT_CONTEXT v81; // [rsp+40h] [rbp-58h]
  PSECURITY_SUBJECT_CONTEXT *v82; // [rsp+48h] [rbp-50h]
  struct _IRP_CONTEXT *v83; // [rsp+50h] [rbp-48h]
  PSECURITY_SUBJECT_CONTEXT *v84; // [rsp+58h] [rbp-40h]
  __int16 v85; // [rsp+A0h] [rbp+8h]
  int v86; // [rsp+B8h] [rbp+20h]

  v3 = 0;
  v80 = 0;
  v81 = 0;
  v6 = 0;
  v79 = 0;
  v7 = 29;
  v86 = 29;
  v9 = 0;
  v10 = 0;
  if ( a1 )
  {
    if ( a1[3] )
      RefsCommitCurrentTransaction((struct _IRP_CONTEXT *)a1, 0);
    v11 = (int *)a1[13];
    if ( a1 != (PSECURITY_SUBJECT_CONTEXT *)v11
      && v11[4] >= 0
      && Status < 0
      && *((_BYTE *)a1 + 40) != 3
      && (*((_DWORD *)a1 + 1) & 0x8000) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          36,
          &WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids,
          (unsigned int)Status);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(Status, 0, "NtfsData.c", 0xAE5u);
      LODWORD(a1[13]->PrimaryToken) = Status;
    }
    if ( Status == -1073741202 )
    {
      v77 = (struct _VCB *)a1[8];
      if ( v77 )
      {
        if ( (*((_DWORD *)v77 + 6) & 1) != 0 && (*((_DWORD *)v77 + 7) & 1) == 0 )
          RefsPostSelfDismount(v77, v6, -1073741202);
      }
    }
    if ( *((_DWORD *)a1 + 164) && (_BYTE)KdDebuggerEnabled )
      __int2c();
    if ( *((_DWORD *)a1 + 165) && (_BYTE)KdDebuggerEnabled )
      __int2c();
    v12 = (volatile signed __int64 *)a1[8];
    if ( v12 && Status < 0 )
    {
      v56 = *((_BYTE *)a1 + 40);
      if ( v56 == 4 )
      {
        switch ( Status )
        {
          case -1073741803:
            v78 = v12 + 945;
            break;
          case -1073741435:
            v78 = v12 + 946;
            break;
          case -1073741391:
            v78 = v12 + 947;
            break;
          default:
            v78 = v12 + 948;
            break;
        }
        _InterlockedIncrement64(v78);
      }
      else if ( v56 == 3 )
      {
        _InterlockedIncrement64(v12 + 949);
      }
    }
    if ( Irp )
    {
      v13 = a1[8];
      if ( v13 )
      {
        if ( Status >= 0 && LOBYTE(v13[322].ClientToken) )
        {
          v14 = *((_BYTE *)a1 + 40);
          if ( v14 == 2 )
            goto LABEL_17;
          if ( v14 )
          {
            if ( v14 != 18 )
              goto LABEL_18;
            goto LABEL_17;
          }
          if ( ((_BYTE)a1[1] & 0x40) == 0 )
          {
LABEL_17:
            v80 = a1[88];
            v86 = *((_DWORD *)a1 + 175);
            v79 = (struct _FILE_OBJECT *)a1[86];
            v81 = a1[8];
            a1[86] = (PSECURITY_SUBJECT_CONTEXT)21;
          }
        }
      }
    }
LABEL_18:
    if ( a1[6] )
      RefsReleaseSharedResources((struct _IRP_CONTEXT *)a1);
    v15 = a1[7];
    if ( !v15 )
      goto LABEL_21;
    if ( LOWORD(v15->ClientToken) == 2050 )
    {
      v67 = a1[13];
      ClientToken = (struct _ERESOURCE *)v15[3].ClientToken;
      if ( v67[10].PrimaryToken != ClientToken
        || !LODWORD(v67[10].ClientToken)
        || (p_ProcessAuditId = &v67[7].ProcessAuditId) == 0 )
      {
        ExReleaseResourceLite(ClientToken);
        a1[7] = 0;
        goto LABEL_21;
      }
      v41 = (*((_DWORD *)p_ProcessAuditId + 18))-- == 1;
      if ( v41 )
      {
        *((_DWORD *)p_ProcessAuditId + 19) &= ~2u;
        ExReleaseFastResource(ClientToken, p_ProcessAuditId);
        a1[7] = 0;
        goto LABEL_21;
      }
    }
    else
    {
      a1[7] = 0;
      PrimaryToken = (struct _FAST_MUTEX *)v15[1].PrimaryToken;
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(PrimaryToken);
      v63 = v15 + 14;
      if ( v63->ClientToken == v63 )
      {
        v15[13].ProcessAuditId = 0;
      }
      else
      {
        v64 = v63->ClientToken;
        v15[13].ProcessAuditId = (PVOID)((unsigned __int64)v15[13].ProcessAuditId | 3);
        ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v64);
        *(_QWORD *)(v65 + 8) = 0;
        *(_QWORD *)v65 = 0;
        KeSetEvent((PRKEVENT)(v65 + 16), 0, 0);
      }
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)v15[1].PrimaryToken);
      KeLeaveGuardedRegion();
    }
    a1[7] = 0;
LABEL_21:
    v16 = *((_DWORD *)a1 + 1);
    if ( (v16 & 0x2000) != 0 )
    {
      *((_DWORD *)a1 + 1) = v16 & 0xFFFFCFFF;
      ExReleaseFastResource(&a1[8][37].ProcessAuditId, 0);
    }
    v17 = (struct _IRP_CONTEXT *)a1[14];
LABEL_24:
    if ( v17 != (struct _IRP_CONTEXT *)(a1 + 14) )
    {
      v18 = (char *)v17 - 64;
      v85 = *((_WORD *)v17 - 18);
      v19 = v17;
      v83 = v17;
      v17 = *(struct _IRP_CONTEXT **)v17;
      while ( !*(_QWORD *)v19 )
      {
LABEL_36:
        if ( *(_WORD *)v18 == 2050 )
          v26 = v18;
        else
          v26 = (char *)*((_QWORD *)v18 + 17);
        v27 = 0;
        CurrentThread = KeGetCurrentThread();
        v29 = *((_QWORD *)v26 + 11) + 64LL;
        for ( i = 0; i < 2; ++i )
        {
          v31 = 14LL * i;
          v32 = &a1[v31 + 44];
          if ( *v32 == (PSECURITY_SUBJECT_CONTEXT)v29 && a1[v31 + 45] == (PSECURITY_SUBJECT_CONTEXT)CurrentThread )
          {
            v27 = &a1[v31 + 44];
            if ( v32 )
              goto LABEL_82;
            break;
          }
        }
        for ( j = (struct _IRP_CONTEXT *)a1[72]; j != (struct _IRP_CONTEXT *)(a1 + 72); j = *(struct _IRP_CONTEXT **)j )
        {
          if ( *((_QWORD *)j - 12) == v29 && *((struct _KTHREAD **)j - 11) == CurrentThread )
          {
            v27 = (PSECURITY_SUBJECT_CONTEXT *)((char *)j - 96);
            break;
          }
        }
LABEL_82:
        IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(*((_QWORD *)v26 + 11) + 64LL);
        if ( !v27 )
        {
          v54 = (struct _ERESOURCE *)(*((_QWORD *)v26 + 11) + 64LL);
          if ( IsFastResourceHeldExclusive )
            ExReleaseFastResource(v54, 0);
          else
            ExReleaseResourceLite(v54);
          goto LABEL_85;
        }
        v55 = *((_DWORD *)v27 + 4);
        if ( IsFastResourceHeldExclusive )
        {
          if ( !v55 )
            goto LABEL_91;
          *((_DWORD *)v27 + 4) = v55 - 1;
          if ( v55 != 1 )
            goto LABEL_91;
LABEL_90:
          *v27 = 0;
          v27[1] = 0;
          goto LABEL_91;
        }
        *((_DWORD *)v27 + 4) = v55 - 1;
        if ( v55 == 1 )
          goto LABEL_90;
LABEL_91:
        ExReleaseFastResource(*((_QWORD *)v26 + 11) + 64LL, v27 + 3);
LABEL_85:
        v19 = v83;
        v3 = 0;
LABEL_86:
        if ( !--v85 )
          goto LABEL_24;
      }
      if ( *((_WORD *)v18 + 14) != 1 )
        goto LABEL_35;
      v20 = a1[3];
      if ( v20 && v20[4].PrimaryToken && ((*((_DWORD *)v18 + 2) & 0x8000LL) == 0 || (*((_DWORD *)a1 + 1) & 0x1000) != 0) )
        goto LABEL_86;
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v19);
      v22[1] = 0;
      *v22 = 0;
      v23 = (struct _IRP_CONTEXT *)(a1 + 80);
      v24 = (struct _IRP_CONTEXT *)a1[80];
      if ( v24 == (struct _IRP_CONTEXT *)(a1 + 80) )
        goto LABEL_35;
      v25 = 0;
      v82 = 0;
      while ( v24 != v23 )
      {
        if ( *((_WORD *)v24 - 4) == v21 )
        {
          v25 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v24 - 8);
          v82 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v24 - 8);
          break;
        }
        v24 = *(struct _IRP_CONTEXT **)v24;
      }
      if ( !v25 )
      {
LABEL_35:
        --*((_WORD *)v18 + 14);
        goto LABEL_36;
      }
      while ( 1 )
      {
        v71 = *(struct _IRP_CONTEXT **)v23;
        v84 = 0;
        if ( *(struct _IRP_CONTEXT **)v23 != v23 )
        {
          if ( v25 )
            v71 = (struct _IRP_CONTEXT *)v25[1];
          while ( v71 != v23 )
          {
            if ( *((_WORD *)v71 - 4) == v21 )
            {
              v84 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v71 - 8);
              break;
            }
            v71 = *(struct _IRP_CONTEXT **)v71;
          }
        }
        v72 = v25[6];
        if ( v72 )
        {
          if ( *(char **)&v72[4].ImpersonationLevel != v18 )
            goto LABEL_151;
          if ( (((__int64)v72[4].ProcessAuditId & 0x2000) != 0 || (*(&v72[9].ImpersonationLevel + 1) & 0x40) != 0)
            && ((__int64)v72[4].ProcessAuditId & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)&v72[4].ProcessAuditId, 0xFFFFDFFF);
          }
          v73 = (struct _FAST_MUTEX *)v25[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v73);
          v25 = v82;
          _InterlockedIncrement((volatile signed __int32 *)&v82[6][5].ImpersonationLevel + 1);
          v82[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v82[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v82[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v74 = v25[1];
        if ( *(PSECURITY_SUBJECT_CONTEXT **)&v74->ImpersonationLevel != v25 + 1 )
          goto LABEL_163;
        v75 = (PSECURITY_SUBJECT_CONTEXT **)v25[2];
        if ( *v75 != v25 + 1 )
          goto LABEL_163;
        *v75 = (PSECURITY_SUBJECT_CONTEXT *)v74;
        *(_QWORD *)&v74->ImpersonationLevel = v75;
        if ( v25 != a1 + 91 )
        {
          v76 = *((_DWORD *)v25 - 2);
          if ( v76 >= RefsNumberProcessors )
            v76 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v76], v25 - 1);
        }
LABEL_151:
        v21 = 2087;
        v82 = v84;
        v25 = v84;
        if ( !v84 )
          goto LABEL_35;
      }
    }
    v33 = (struct _IRP_CONTEXT *)(a1 + 80);
    v34 = (struct _IRP_CONTEXT *)a1[80];
    if ( v34 != (struct _IRP_CONTEXT *)(a1 + 80) )
    {
      v35 = 0;
      while ( v34 != v33 )
      {
        if ( *((_WORD *)v34 - 4) == 2087 )
        {
          v35 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v34 - 8);
          break;
        }
        v34 = *(struct _IRP_CONTEXT **)v34;
      }
      if ( v35 )
      {
        while ( 1 )
        {
          if ( *(struct _IRP_CONTEXT **)v33 != v33 )
          {
            for ( k = (struct _IRP_CONTEXT *)v35[1]; k != v33; k = *(struct _IRP_CONTEXT **)k )
            {
              if ( *((_WORD *)k - 4) == 2087 )
              {
                v3 = (PSECURITY_SUBJECT_CONTEXT *)((char *)k - 8);
                break;
              }
            }
          }
          v57 = v35[6];
          if ( v57 )
          {
            if ( (((__int64)v57[4].ProcessAuditId & 0x2000) != 0 || (*(&v57[9].ImpersonationLevel + 1) & 0x40) != 0)
              && ((__int64)v57[4].ProcessAuditId & 0x2000) != 0 )
            {
              _InterlockedAnd((volatile signed __int32 *)&v57[4].ProcessAuditId, 0xFFFFDFFF);
            }
            v58 = (struct _FAST_MUTEX *)v35[6][1].PrimaryToken;
            KeEnterGuardedRegion();
            ExAcquireFastMutexUnsafe(v58);
            _InterlockedIncrement((volatile signed __int32 *)&v35[6][5].ImpersonationLevel + 1);
            v35[6][8].ProcessAuditId = 0;
            ++*((_DWORD *)&v35[6][5].ImpersonationLevel + 1);
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)v35[6][1].PrimaryToken);
            KeLeaveGuardedRegion();
          }
          v59 = v35[1];
          if ( *(PSECURITY_SUBJECT_CONTEXT **)&v59->ImpersonationLevel != v35 + 1
            || (v60 = (PSECURITY_SUBJECT_CONTEXT **)v35[2], *v60 != v35 + 1) )
          {
LABEL_163:
            __fastfail(3u);
          }
          *v60 = (PSECURITY_SUBJECT_CONTEXT *)v59;
          *(_QWORD *)&v59->ImpersonationLevel = v60;
          if ( v35 != a1 + 91 )
          {
            v61 = *((_DWORD *)v35 - 2);
            if ( v61 >= RefsNumberProcessors )
              v61 %= RefsNumberProcessors;
            ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v61], v35 - 1);
          }
          if ( !v3 )
            break;
          v35 = v3;
          v3 = 0;
        }
      }
    }
    for ( m = (PSECURITY_SUBJECT_CONTEXT *)a1[75]; m; m = (PSECURITY_SUBJECT_CONTEXT *)a1[75] )
    {
      a1[75] = *m;
      ExFreePoolWithTag(m, 0);
    }
    v37 = *((_DWORD *)a1 + 1);
    if ( (v37 & 0x400) != 0 || (v38 = (unsigned __int64)a1[1], (v38 & 0x10000) != 0) )
    {
      if ( (v37 & 0x40000) != 0 )
      {
        *((_DWORD *)a1 + 1) = v37 & 0xFFFBFBFF;
      }
      else
      {
        *((_DWORD *)a1 + 1) = v37 & 0xBFF9C0C5;
        a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFFFFBFFuLL);
      }
      *((_DWORD *)a1 + 4) = 0;
      goto LABEL_67;
    }
    if ( (v38 & 0x20000000000LL) != 0 )
    {
      *((_DWORD *)a1 + 59) &= ~1u;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)(v38 & 0xFFFFFDFFFFFFFFFFuLL);
    }
    if ( a1[42] )
    {
      *((_DWORD *)a1 + 81) &= ~1u;
      a1[42] = 0;
    }
    v39 = (_QWORD **)(a1 + 72);
    while ( 1 )
    {
      v40 = *v39;
      if ( *v39 == v39 )
        break;
      if ( (_QWORD **)v40[1] != v39 )
        goto LABEL_163;
      v49 = (_QWORD *)*v40;
      if ( *(_QWORD **)(*v40 + 8LL) != v40 )
        goto LABEL_163;
      *v39 = v49;
      v49[1] = v39;
      ExFreePoolWithTag(v40 - 12, 0);
    }
    a1[44] = 0;
    a1[58] = 0;
    v41 = ((_BYTE)a1[1] & 0x20) == 0;
    *((_DWORD *)a1 + 148) = 0;
    if ( !v41 )
    {
      SeReleaseSubjectContext(a1[18]);
      ExFreePoolWithTag(a1[18], 0);
    }
    v42 = *((_DWORD *)a1 + 2);
    a1[18] = 0;
    if ( (*(_QWORD *)&v42 & 0x100000LL) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      *(_QWORD *)&TopLevelIrp->Flags = 0;
      IoSetTopLevelIrp(MdlAddress);
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
    }
    v43 = a1[89];
    if ( v43 )
    {
      ExFreePoolWithTag(v43, 0);
      a1[89] = 0;
    }
    if ( ((_DWORD)a1[1] & 0x80000LL) == 0 )
      goto LABEL_67;
    v44 = *((_DWORD *)a1 - 2);
    if ( *((_WORD *)a1 + 1) == 1664 )
    {
      v45 = RefsIrpAndIoContextLookasideList;
      if ( v44 < RefsNumberProcessors )
        goto LABEL_66;
    }
    else
    {
      v45 = RefsIrpContextLookasideList;
      if ( v44 < RefsNumberProcessors )
      {
LABEL_66:
        ExFreeToNPagedLookasideList(&v45[(unsigned __int64)v44], a1 - 1);
LABEL_67:
        v10 = v81;
        v9 = v80;
        v7 = v86;
        v6 = v79;
        goto LABEL_68;
      }
    }
    v44 %= RefsNumberProcessors;
    goto LABEL_66;
  }
LABEL_68:
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    FsContext = 0;
    FileObject = CurrentStackLocation->FileObject;
    if ( FileObject )
      FsContext = FileObject->FsContext;
    Irp->IoStatus.Status = Status;
    if ( (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) <= 1u && Status == -1073741670 )
    {
      if ( FsContext )
      {
        if ( (*(_BYTE *)(FsContext[17] + 8LL) & 4) != 0 )
        {
          IsOperationSynchronous = IoIsOperationSynchronous(Irp);
          v6 = v79;
          v7 = v86;
          v9 = v80;
          v10 = v81;
          if ( IsOperationSynchronous )
            ++RefsFailedPagingFileOps;
        }
      }
    }
    if ( CurrentStackLocation->MajorFunction == 3 && Status == -1073741670 && (Irp->Flags & 2) != 0 )
      ++RefsFailedPagingReads;
    if ( (__int64)v6 > 23 )
      RefsIoPerfCollectBasicData(v10, Irp, v9, v7, v6);
    IofCompleteRequest(Irp, 1);
  }
}

```

## disassembly

```asm
0x14000e0e0  mov     [rsp+arg_8], rbx
0x14000e0e5  push    rbp
0x14000e0e6  push    rsi
0x14000e0e7  push    rdi
0x14000e0e8  push    r12
0x14000e0ea  push    r13
0x14000e0ec  push    r14
0x14000e0ee  push    r15
0x14000e0f0  sub     rsp, 60h
0x14000e0f4  xor     r13d, r13d
0x14000e0f7  mov     r12d, r8d
0x14000e0fa  mov     [rsp+98h+var_60], r13
0x14000e0ff  mov     rbp, rdx
0x14000e102  mov     [rsp+98h+var_58], r13
0x14000e107  mov     edx, r13d; struct _FILE_OBJECT *
0x14000e10a  mov     [rsp+98h+var_68], rdx
0x14000e10f  mov     r8d, 1Dh
0x14000e115  mov     [rsp+98h+arg_18], r8d
0x14000e11d  mov     rdi, rcx
0x14000e120  mov     r10d, r13d
0x14000e123  mov     r11d, r13d
0x14000e126  test    rcx, rcx
0x14000e129  jz      loc_14000E44F
0x14000e12f  cmp     [rcx+18h], rdx
0x14000e133  jnz     loc_14000E531
0x14000e139  mov     rax, [rdi+68h]
0x14000e13d  cmp     rdi, rax
0x14000e140  jnz     loc_14000EB05
0x14000e146  cmp     r12d, 0C000026Eh
0x14000e14d  jz      loc_14000EBBD
0x14000e153  cmp     [rdi+290h], r13d
0x14000e15a  jnz     loc_14000EBF0
0x14000e160  cmp     [rdi+294h], r13d
0x14000e167  jnz     loc_14000EC07
0x14000e16d  mov     rax, [rdi+40h]
0x14000e171  test    rax, rax
0x14000e174  jz      short loc_14000E17F
0x14000e176  test    r12d, r12d
0x14000e179  js      loc_14000E5E4
0x14000e17f  test    rbp, rbp
0x14000e182  jz      short loc_14000E1EA
0x14000e184  mov     rax, [rdi+40h]
0x14000e188  test    rax, rax
0x14000e18b  jz      short loc_14000E1EA
0x14000e18d  test    r12d, r12d
0x14000e190  js      short loc_14000E1EA
0x14000e192  movzx   eax, byte ptr [rax+2840h]
0x14000e199  test    al, al
0x14000e19b  jz      short loc_14000E1EA
0x14000e19d  movzx   eax, byte ptr [rdi+28h]
0x14000e1a1  cmp     al, 2
0x14000e1a3  jz      short loc_14000E1B1
0x14000e1a5  test    al, al
0x14000e1a7  jz      loc_14000E670
0x14000e1ad  cmp     al, 12h
0x14000e1af  jnz     short loc_14000E1EA
0x14000e1b1  mov     rax, [rdi+2C0h]
0x14000e1b8  mov     rcx, [rdi+40h]
0x14000e1bc  mov     [rsp+98h+var_60], rax
0x14000e1c1  mov     eax, [rdi+2BCh]
0x14000e1c7  mov     [rsp+98h+arg_18], eax
0x14000e1ce  mov     rax, [rdi+2B0h]
0x14000e1d5  mov     [rsp+98h+var_68], rax
0x14000e1da  mov     [rsp+98h+var_58], rcx
0x14000e1df  mov     qword ptr [rdi+2B0h], 15h
0x14000e1ea  cmp     [rdi+30h], r13
0x14000e1ee  jz      short loc_14000E1F8
0x14000e1f0  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14000e1f3  call    ?RefsReleaseSharedResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseSharedResources(_IRP_CONTEXT *)
0x14000e1f8  mov     rsi, [rdi+38h]
0x14000e1fc  mov     eax, 802h
0x14000e201  test    rsi, rsi
0x14000e204  jnz     loc_14000E797
0x14000e20a  mov     eax, [rdi+4]
0x14000e20d  bt      eax, 0Dh
0x14000e211  jb      loc_14000EC36
0x14000e217  mov     rbx, [rdi+70h]
0x14000e21b  lea     r14, [rdi+70h]
0x14000e21f  mov     r8d, 827h
0x14000e225  cmp     rbx, r14
0x14000e228  jz      loc_14000E305
0x14000e22e  movzx   eax, word ptr [rbx-24h]
0x14000e232  lea     r15, [rbx-40h]
0x14000e236  mov     [rsp+98h+arg_0], ax
0x14000e23e  mov     rcx, rbx
0x14000e241  mov     [rsp+98h+var_48], rbx
0x14000e246  mov     eax, 0FFFFh
0x14000e24b  mov     rbx, [rbx]
0x14000e24e  cmp     qword ptr [rcx], 0
0x14000e252  jz      short loc_14000E2B8
0x14000e254  cmp     word ptr [r15+1Ch], 1
0x14000e25a  jnz     short loc_14000E2B3
0x14000e25c  mov     rax, [rdi+18h]
0x14000e260  test    rax, rax
0x14000e263  jnz     loc_14000EA9C
0x14000e269  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x14000e26e  mov     [rcx+8], r13
0x14000e272  mov     [rcx], r13
0x14000e275  lea     r13, [rdi+280h]
0x14000e27c  mov     rax, [r13+0]
0x14000e280  cmp     rax, r13
0x14000e283  jz      short loc_14000E2AE
0x14000e285  xor     esi, esi
0x14000e287  mov     [rsp+98h+var_50], rsi
0x14000e28c  cmp     rax, r13
0x14000e28f  jz      short loc_14000E2A5
0x14000e291  cmp     [rax-8], r8w
0x14000e296  jnz     loc_14000EB1D
0x14000e29c  lea     rsi, [rax-8]
0x14000e2a0  mov     [rsp+98h+var_50], rsi
0x14000e2a5  test    rsi, rsi
0x14000e2a8  jnz     loc_14000E910
0x14000e2ae  mov     eax, 0FFFFh
0x14000e2b3  add     [r15+1Ch], ax
0x14000e2b8  mov     eax, 802h
0x14000e2bd  cmp     [r15], ax
0x14000e2c1  jnz     loc_14000E664
0x14000e2c7  mov     r13, r15
0x14000e2ca  mov     r8, [r13+58h]
0x14000e2ce  xor     esi, esi
0x14000e2d0  mov     r9, gs:188h
0x14000e2d9  add     r8, 40h ; '@'
0x14000e2dd  xor     edx, edx
0x14000e2df  cmp     edx, 2
0x14000e2e2  jnb     loc_14000E53B
0x14000e2e8  mov     eax, edx
0x14000e2ea  imul    rcx, rax, 70h ; 'p'
0x14000e2ee  lea     rax, [rdi+160h]
0x14000e2f5  add     rax, rcx
0x14000e2f8  cmp     [rax], r8
0x14000e2fb  jz      loc_14000E62B
0x14000e301  inc     edx
0x14000e303  jmp     short loc_14000E2DF
0x14000e305  lea     rsi, [rdi+280h]
0x14000e30c  mov     rax, [rsi]
0x14000e30f  cmp     rax, rsi
0x14000e312  jz      short loc_14000E334
0x14000e314  mov     r15, r13
0x14000e317  cmp     rax, rsi
0x14000e31a  jz      short loc_14000E32B
0x14000e31c  cmp     [rax-8], r8w
0x14000e321  jnz     loc_14000EACB
0x14000e327  lea     r15, [rax-8]
0x14000e32b  test    r15, r15
0x14000e32e  jnz     loc_14000E680
0x14000e334  mov     rcx, [rdi+258h]; P
0x14000e33b  test    rcx, rcx
0x14000e33e  jnz     loc_14000EC94
0x14000e344  mov     ecx, [rdi+4]
0x14000e347  bt      ecx, 0Ah
0x14000e34b  jb      loc_14000E607
0x14000e351  mov     rax, [rdi+8]
0x14000e355  bt      rax, 10h
0x14000e35a  jb      loc_14000E607
0x14000e360  bt      rax, 29h ; ')'
0x14000e365  jnb     short loc_14000E37F
0x14000e367  and     dword ptr [rdi+0ECh], 0FFFFFFFEh
0x14000e36e  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x14000e378  and     rax, rcx
0x14000e37b  mov     [rdi+8], rax
0x14000e37f  cmp     qword ptr [rdi+150h], 0
0x14000e387  jz      short loc_14000E397
0x14000e389  and     dword ptr [rdi+144h], 0FFFFFFFEh
0x14000e390  mov     [rdi+150h], r13
0x14000e397  lea     rbx, [rdi+240h]
0x14000e39e  mov     rcx, [rbx]
0x14000e3a1  cmp     rcx, rbx
0x14000e3a4  jnz     loc_14000E4CB
0x14000e3aa  mov     [rdi+160h], r13
0x14000e3b1  mov     [r14+160h], r13
0x14000e3b8  test    byte ptr [rdi+8], 20h
0x14000e3bc  mov     [rdi+250h], r13d
0x14000e3c3  jnz     loc_14000ECBD
0x14000e3c9  mov     eax, [rdi+8]
0x14000e3cc  mov     [rdi+90h], r13
0x14000e3d3  bt      rax, 14h
0x14000e3d8  jb      loc_14000E500
0x14000e3de  mov     rcx, [rdi+2C8h]; P
0x14000e3e5  test    rcx, rcx
0x14000e3e8  jnz     loc_14000ECEA
0x14000e3ee  mov     eax, [rdi+8]
0x14000e3f1  bt      rax, 13h
0x14000e3f6  jnb     short loc_14000E438
0x14000e3f8  mov     eax, [rdi-8]
0x14000e3fb  mov     ecx, 680h
0x14000e400  cmp     [rdi+2], cx
0x14000e404  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14000e40a  jz      loc_14000E64A
0x14000e410  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x14000e417  cmp     eax, ecx
0x14000e419  jnb     loc_14000E659
0x14000e41f  mov     ecx, eax
0x14000e421  lea     rdx, [rdi-8]; Entry
0x14000e425  shl     rcx, 7
0x14000e429  add     rcx, r9; Lookaside
0x14000e42c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000e433  nop     dword ptr [rax+rax+00h]
0x14000e438  mov     r11, [rsp+98h+var_58]
0x14000e43d  mov     r10, [rsp+98h+var_60]
0x14000e442  mov     r8d, [rsp+98h+arg_18]
0x14000e44a  mov     rdx, [rsp+98h+var_68]
0x14000e44f  test    rbp, rbp
0x14000e452  jz      short loc_14000E4B2
0x14000e454  mov     rbx, [rbp+0B8h]
0x14000e45b  mov     rcx, r13
0x14000e45e  mov     rax, [rbx+30h]
0x14000e462  test    rax, rax
0x14000e465  jz      short loc_14000E46B
0x14000e467  mov     rcx, [rax+18h]
0x14000e46b  mov     [rbp+30h], r12d
0x14000e46f  movzx   eax, byte ptr [rbx]
0x14000e472  sub     al, 3
0x14000e474  cmp     al, 1
0x14000e476  jbe     loc_14000E8A1
0x14000e47c  cmp     byte ptr [rbx], 3
0x14000e47f  jz      loc_14000EA6D
0x14000e485  cmp     rdx, 17h
0x14000e489  jle     short loc_14000E4A1
0x14000e48b  mov     [rsp+98h+var_78], rdx
0x14000e490  mov     r9d, r8d
0x14000e493  mov     r8, r10
0x14000e496  mov     rdx, rbp
0x14000e499  mov     rcx, r11
0x14000e49c  call    ?RefsIoPerfCollectBasicData@@YAXPEAU_VCB@@PEAU_IRP@@PEAXW4_REFS_IO_PERF_IO_TYPE@@_J@Z; RefsIoPerfCollectBasicData(_VCB *,_IRP *,void *,_REFS_IO_PERF_IO_TYPE,__int64)
0x14000e4a1  mov     dl, 1; PriorityBoost
0x14000e4a3  mov     rcx, rbp; Irp
0x14000e4a6  call    cs:__imp_IofCompleteRequest
0x14000e4ad  nop     dword ptr [rax+rax+00h]
0x14000e4b2  mov     rbx, [rsp+98h+arg_8]
0x14000e4ba  add     rsp, 60h
0x14000e4be  pop     r15
0x14000e4c0  pop     r14
0x14000e4c2  pop     r13
0x14000e4c4  pop     r12
0x14000e4c6  pop     rdi
0x14000e4c7  pop     rsi
0x14000e4c8  pop     rbp
0x14000e4c9  retn
0x14000e4cb  cmp     [rcx+8], rbx
0x14000e4cf  jnz     loc_14000EAD3
0x14000e4d5  mov     rax, [rcx]
0x14000e4d8  cmp     [rax+8], rcx
0x14000e4dc  jnz     loc_14000EAD3
0x14000e4e2  mov     [rbx], rax
0x14000e4e5  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14000e4e9  xor     edx, edx; Tag
0x14000e4eb  mov     [rax+8], rbx
0x14000e4ef  call    cs:__imp_ExFreePoolWithTag
0x14000e4f6  nop     dword ptr [rax+rax+00h]
0x14000e4fb  jmp     loc_14000E39E
0x14000e500  call    cs:__imp_IoGetTopLevelIrp
0x14000e507  nop     dword ptr [rax+rax+00h]
0x14000e50c  mov     rcx, [rax+8]; Irp
0x14000e510  mov     [rax+4], r13d
0x14000e514  mov     [rax+10h], r13
0x14000e518  call    cs:__imp_IoSetTopLevelIrp
0x14000e51f  nop     dword ptr [rax+rax+00h]
0x14000e524  and     qword ptr [rdi+8], 0FFFFFFFFFFEFFFFFh
0x14000e52c  jmp     loc_14000E3DE
0x14000e531  call    ?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)
0x14000e536  jmp     loc_14000E139
0x14000e53b  lea     rax, [rdi+240h]
0x14000e542  mov     rcx, [rax]
0x14000e545  cmp     rcx, rax
0x14000e548  jnz     loc_14000EB70
0x14000e54e  mov     rcx, r8
0x14000e551  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14000e558  nop     dword ptr [rax+rax+00h]
0x14000e55d  test    rsi, rsi
0x14000e560  jnz     short loc_14000E5A6
0x14000e562  mov     rcx, [r13+58h]
0x14000e566  add     rcx, 40h ; '@'; Resource
0x14000e56a  test    al, al
0x14000e56c  jz      loc_14000EC67
0x14000e572  xor     edx, edx
0x14000e574  call    cs:__imp_ExReleaseFastResource
0x14000e57b  nop     dword ptr [rax+rax+00h]
0x14000e580  mov     rcx, [rsp+98h+var_48]
0x14000e585  xor     r13d, r13d
0x14000e588  mov     r8d, 827h
0x14000e58e  mov     eax, 0FFFFh
0x14000e593  add     [rsp+98h+arg_0], ax
0x14000e59b  jz      loc_14000E225
0x14000e5a1  jmp     loc_14000E24E
0x14000e5a6  mov     ecx, [rsi+10h]
0x14000e5a9  test    al, al
0x14000e5ab  jnz     loc_14000EB4D
0x14000e5b1  lea     eax, [rcx-1]
0x14000e5b4  mov     [rsi+10h], eax
0x14000e5b7  test    eax, eax
0x14000e5b9  jnz     short loc_14000E5CA
0x14000e5bb  mov     qword ptr [rsi], 0
0x14000e5c2  mov     qword ptr [rsi+8], 0
0x14000e5ca  mov     rcx, [r13+58h]
0x14000e5ce  lea     rdx, [rsi+18h]
0x14000e5d2  add     rcx, 40h ; '@'
0x14000e5d6  call    cs:__imp_ExReleaseFastResource
0x14000e5dd  nop     dword ptr [rax+rax+00h]
0x14000e5e2  jmp     short loc_14000E580
0x14000e5e4  movzx   ecx, byte ptr [rdi+28h]
  ... truncated ...
```
