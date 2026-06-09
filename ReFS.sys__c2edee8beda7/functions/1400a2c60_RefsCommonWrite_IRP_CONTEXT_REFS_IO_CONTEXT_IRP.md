# RefsCommonWrite(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)

- ea: `0x1400a2c60`
- end: `0x1400a66fc`
- name: `?RefsCommonWrite@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z`
- size: `15004`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct REFS_IO_CONTEXT *, PIRP Irp)`
- caller_count: `3`
- callee_count: `48`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400b9530`
- `0x1400bd090`
- `0x14032da60`

## callees

- `0x140009d5c`
- `0x14000a590`
- `0x14000dfe0`
- `0x14000e0e0`
- `0x140035df0`
- `0x140035f20`
- `0x140036670`
- `0x140037820`
- `0x1400733d0`
- `0x140075c94`
- `0x140076a40`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400867d0`
- `0x140088990`
- `0x140090c50`
- `0x140093740`
- `0x140095370`
- `0x140097c50`
- `0x140097fe0`
- `0x14009c260`
- `0x14009e300`
- `0x1400a2c60`
- `0x1400a6f44`
- `0x1400a79f8`
- `0x1400a9f50`
- `0x1400ab3a0`
- `0x1400b5ba0`
- `0x1400cea34`
- `0x1400d0fd8`
- `0x1400e6488`
- `0x1400f4880`
- `0x1400ff71c`
- `0x14010b670`
- `0x14010b9e8`
- `0x14010bae8`
- `0x14010bb50`
- `0x140112064`
- `0x1401f3fc0`
- `0x140302e10`
- `0x140302eb0`
- `0x140304230`
- `0x140306290`
- `0x140323450`
- `0x14033046c`
- `0x14033ae88`
- `0x14033afa0`
- `0x14033e290`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a3658`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a4ba4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a4bb9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a4dde`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a3658`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a4ba4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a4bb9`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a4dde`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400a577d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400a577d`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a2fdb`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a2ff5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a31dd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a31f7`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a33a6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a33c0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3554`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a356e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a37cf`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a37e9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a399e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a39b8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3b56`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3b70`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3eb3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3ecd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a601a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a6034`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a2fdb`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a2ff5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a31dd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a31f7`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a33a6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a33c0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3554`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a356e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a37cf`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a37e9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a399e`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a39b8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3b56`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3b70`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3eb3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a3ecd`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a601a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400a6034`
- `ntoskrnl!ExRaiseStatus` at `0x1400a2de0`
- `ntoskrnl!ExRaiseStatus` at `0x1400a5a81`
- `ntoskrnl!ExRaiseStatus` at `0x1400a2de0`
- `ntoskrnl!ExRaiseStatus` at `0x1400a5a81`
- `ntoskrnl!DbgPrintEx` at `0x1400a2f79`
- `ntoskrnl!DbgPrintEx` at `0x1400a317b`
- `ntoskrnl!DbgPrintEx` at `0x1400a333f`
- `ntoskrnl!DbgPrintEx` at `0x1400a34ed`
- `ntoskrnl!DbgPrintEx` at `0x1400a3768`
- `ntoskrnl!DbgPrintEx` at `0x1400a3937`
- `ntoskrnl!DbgPrintEx` at `0x1400a3aef`
- `ntoskrnl!DbgPrintEx` at `0x1400a3e4c`
- `ntoskrnl!DbgPrintEx` at `0x1400a5fb3`
- `ntoskrnl!DbgPrintEx` at `0x1400a2f79`
- `ntoskrnl!DbgPrintEx` at `0x1400a317b`
- `ntoskrnl!DbgPrintEx` at `0x1400a333f`
- `ntoskrnl!DbgPrintEx` at `0x1400a34ed`
- `ntoskrnl!DbgPrintEx` at `0x1400a3768`
- `ntoskrnl!DbgPrintEx` at `0x1400a3937`
- `ntoskrnl!DbgPrintEx` at `0x1400a3aef`
- `ntoskrnl!DbgPrintEx` at `0x1400a3e4c`
- `ntoskrnl!DbgPrintEx` at `0x1400a5fb3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a2fa1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a31a3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a336c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a351a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3795`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3964`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3b1c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3e79`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a5fe0`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a2fa1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a31a3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a336c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a351a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3795`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3964`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3b1c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a3e79`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400a5fe0`
- `ntoskrnl!_strnicmp` at `0x1400a3020`
- `ntoskrnl!_strnicmp` at `0x1400a3222`
- `ntoskrnl!_strnicmp` at `0x1400a33eb`
- `ntoskrnl!_strnicmp` at `0x1400a3599`
- `ntoskrnl!_strnicmp` at `0x1400a3814`
- `ntoskrnl!_strnicmp` at `0x1400a39e3`
- `ntoskrnl!_strnicmp` at `0x1400a3b9b`
- `ntoskrnl!_strnicmp` at `0x1400a3ef8`
- `ntoskrnl!_strnicmp` at `0x1400a605f`
- `ntoskrnl!_strnicmp` at `0x1400a3020`
- `ntoskrnl!_strnicmp` at `0x1400a3222`
- `ntoskrnl!_strnicmp` at `0x1400a33eb`
- `ntoskrnl!_strnicmp` at `0x1400a3599`
- `ntoskrnl!_strnicmp` at `0x1400a3814`
- `ntoskrnl!_strnicmp` at `0x1400a39e3`
- `ntoskrnl!_strnicmp` at `0x1400a3b9b`
- `ntoskrnl!_strnicmp` at `0x1400a3ef8`
- `ntoskrnl!_strnicmp` at `0x1400a605f`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3004`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3206`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a33cf`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a357d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a37f8`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a39c7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3b7f`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3edc`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a6043`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3004`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3206`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a33cf`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a357d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a37f8`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a39c7`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3b7f`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a3edc`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400a6043`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400a57db`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400a57db`
- `ntoskrnl!CcCopyWrite` at `0x1400a5c3a`
- `ntoskrnl!CcCopyWrite` at `0x1400a5c3a`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1400a5b7d`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1400a5b7d`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a4be6`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a4c09`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a4be6`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1400a4c09`
- `ntoskrnl!CcCanIWrite` at `0x1400a3fc2`
- `ntoskrnl!CcCanIWrite` at `0x1400a3fc2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400a4e4f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400a5d87`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401f587f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400a4e4f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400a5d87`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1401f587f`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1400a5b6c`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x1400a5b6c`
- `ntoskrnl!CcDeferWrite` at `0x1400a404b`
- `ntoskrnl!CcDeferWrite` at `0x1400a404b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a4e5e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a5d96`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f588e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a4e5e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a5d96`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f588e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400a5480`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400a5480`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1400a54e4`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1400a54e4`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400a52ea`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400a52ea`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400a5a73`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x1400a5a73`
- `ntoskrnl!CcFlushCache` at `0x1400a5cfd`
- `ntoskrnl!CcFlushCache` at `0x1400a5cfd`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400a5c9a`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400a5c9a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a4ef2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a503c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a511e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a5e43`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f5937`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a4ef2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a503c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a511e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a5e43`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f5937`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a4efe`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a5048`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a512a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a5e4f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1401f5943`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a4efe`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a5048`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a512a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1400a5e4f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1401f5943`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a408f`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a4203`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a42c6`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a4382`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a5ee5`
- `ntoskrnl!ExReleaseFastResource` at `0x1401f59f2`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a408f`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a4203`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a42c6`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a4382`
- `ntoskrnl!ExReleaseFastResource` at `0x1400a5ee5`
- `ntoskrnl!ExReleaseFastResource` at `0x1401f59f2`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4013`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4104`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4013`
- `HAL!KeQueryPerformanceCounter` at `0x1400a4104`

## string_xrefs

- `0x1400a2e96`: `write.c`
- `0x1400a2f44`: `write.c`
- `0x1400a3146`: `write.c`
- `0x1400a3309`: `write.c`
- `0x1400a34b7`: `write.c`
- `0x1400a3732`: `write.c`
- `0x1400a3901`: `write.c`
- `0x1400a3ab9`: `write.c`
- `0x1400a3e16`: `write.c`
- `0x1400a479e`: `write.c`
- `0x1400a4f4e`: `write.c`
- `0x1400a509c`: `write.c`
- `0x1400a5386`: `write.c`
- `0x1400a5a59`: `write.c`
- `0x1400a5f7d`: `write.c`
- `0x1400a6134`: `write.c`
- `0x1400a619c`: `write.c`
- `0x1400a6204`: `write.c`
- `0x1400a626c`: `write.c`
- `0x1400a62d4`: `write.c`
- `0x1400a6339`: `write.c`
- `0x1400a639d`: `write.c`
- `0x1400a6405`: `write.c`
- `0x1400a6472`: `write.c`
- `0x1400a64ed`: `write.c`
- `0x1400a654f`: `write.c`
- `0x1400a65b7`: `write.c`
- `0x1400a6619`: `write.c`
- `0x1400a6677`: `write.c`
- `0x1400a66d5`: `write.c`

## pseudocode

```c
__int64 __fastcall RefsCommonWrite(struct _IRP_CONTEXT *a1, struct REFS_IO_CONTEXT *a2, PIRP Irp)
{
  PIRP v3; // rbx
  struct _IRP_CONTEXT *v5; // rdi
  struct _FILE_OBJECT *v6; // r8
  __int64 FsContext; // rsi
  __int64 v8; // r9
  char *FsContext2; // r13
  int v10; // ecx
  __int64 v11; // r9
  char v12; // dl
  PMRX_NET_ROOT pNetRoot; // rax
  int v14; // r14d
  volatile unsigned int v15; // esi
  struct _KPROCESS *v16; // rsi
  PEPROCESS v17; // rax
  const char *v18; // rax
  __int64 v19; // rcx
  int v21; // eax
  volatile unsigned int v22; // edi
  struct _KPROCESS *v23; // rdi
  PEPROCESS v24; // rax
  const char *v25; // rax
  __int64 v26; // rcx
  volatile unsigned int v27; // edi
  struct _KPROCESS *v28; // rdi
  PEPROCESS v29; // rax
  const char *v30; // rax
  __int64 v31; // rcx
  volatile unsigned int v32; // edi
  struct _KPROCESS *v33; // rdi
  PEPROCESS v34; // rax
  const char *v35; // rax
  __int64 v36; // rdx
  char v37; // r15
  NTSTATUS Flags; // r14d
  char v39; // al
  char v40; // r15
  __int64 v41; // rax
  __int64 v42; // rax
  volatile unsigned int v43; // edi
  struct _KPROCESS *v44; // rdi
  PEPROCESS v45; // rax
  const char *v46; // rax
  __int64 v47; // rdx
  volatile unsigned int v48; // edi
  struct _KPROCESS *v49; // rdi
  PEPROCESS v50; // rax
  const char *v51; // rax
  __int64 v52; // rcx
  volatile unsigned int v53; // edi
  struct _KPROCESS *v54; // rdi
  PEPROCESS v55; // rax
  const char *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  struct _IO_STACK_LOCATION *v59; // rdx
  ULONG v60; // r10d
  __int64 QuadPart; // rcx
  union _LARGE_INTEGER v62; // rdx
  const char *v63; // r11
  const char *v64; // r10
  const char *v65; // r9
  const char *v66; // r8
  const char *v67; // rdx
  const char *v68; // rax
  volatile unsigned int v69; // edi
  struct _KPROCESS *v70; // rdi
  PEPROCESS v71; // rax
  const char *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rax
  int v75; // ebx
  PVOID v76; // r12
  __int64 v77; // rcx
  __int64 v78; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v80; // r9
  char v81; // dl
  char v82; // r10
  __int64 v83; // rdx
  __int64 v84; // rcx
  union _LARGE_INTEGER v85; // rcx
  unsigned int v86; // ecx
  __int64 v87; // rcx
  unsigned __int8 v88; // r9
  int v89; // r12d
  __int64 v90; // rcx
  unsigned int v91; // r8d
  __int64 v92; // rcx
  _DWORD *v93; // rdx
  __int16 v94; // ax
  bool v95; // dl
  unsigned int v96; // r8d
  int v97; // eax
  char v98; // al
  __int64 v99; // rcx
  char v100; // al
  PFILE_OBJECT v101; // rcx
  char *v102; // r8
  unsigned __int8 v103; // r15
  char v104; // r15
  __int16 v105; // ax
  unsigned int v106; // r9d
  char v107; // r12
  unsigned __int8 v108; // bl
  struct REFS_IO_CONTEXT *v109; // rax
  __int64 v110; // rcx
  struct _IRP *v111; // r13
  PFILE_OBJECT v112; // rbx
  ULONG_PTR Information; // rax
  struct _CACHE_UNINITIALIZE_EVENT *v114; // r8
  char v115; // r10
  int v116; // r11d
  __int64 v117; // rdx
  __int64 v118; // rax
  int v119; // eax
  __int64 v120; // r9
  ULONG v121; // r8d
  int v122; // ecx
  __int64 v123; // rcx
  int v124; // eax
  struct REFS_IO_CONTEXT *v125; // rbx
  __int64 v126; // rcx
  __int64 v127; // rcx
  __int16 v128; // ax
  int v129; // ecx
  unsigned int v130; // r10d
  ULONG v131; // eax
  __int64 v132; // rcx
  int v133; // eax
  struct _FAST_MUTEX *v134; // rbx
  __int64 v135; // r8
  union _LARGE_INTEGER v136; // rcx
  union _LARGE_INTEGER v137; // r9
  union _LARGE_INTEGER v138; // rbx
  union _LARGE_INTEGER v139; // r8
  __int64 v140; // rax
  __int64 v141; // r9
  int v142; // r10d
  __int64 v143; // r8
  unsigned __int8 v144; // dl
  struct REFS_IO_CONTEXT *v145; // rax
  struct _IRP_CONTEXT *v146; // rcx
  char v147; // al
  __int64 v148; // rax
  FILE_LOCK *v149; // rcx
  unsigned int v150; // r8d
  struct _CCB *v151; // r12
  int v152; // eax
  int v153; // eax
  __int64 v155; // rdx
  __int64 v156; // rcx
  int ActivityIdIrp; // eax
  char *v158; // rdx
  __int16 v159; // ax
  struct REFS_IO_CONTEXT *v160; // r12
  struct _MS_FAST_RESOURCE_OWNER_ENTRY *v161; // rax
  unsigned int v162; // ecx
  NTSTATUS v163; // eax
  struct _FILE_OBJECT *v164; // r14
  struct _IRP_CONTEXT *v165; // rcx
  unsigned int v166; // r8d
  PVOID v167; // rax
  unsigned int v168; // r8d
  __int64 v169; // r9
  struct _IO_STATUS_BLOCK *p_IoStatus; // rbx
  unsigned int v171; // r8d
  __int64 v172; // r9
  __int64 Status; // r9
  struct _FAST_MUTEX *v174; // rbx
  __int64 HighestPendingFileSize; // rax
  __int64 v176; // r8
  __int64 v177; // rax
  __int64 v178; // rcx
  volatile unsigned int v179; // edi
  struct _KPROCESS *v180; // rdi
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  __int64 v183; // rdx
  struct _FCB *v184; // rbx
  NTSTATUS v185; // eax
  unsigned int v186; // r8d
  NTSTATUS v187; // esi
  unsigned __int8 v188; // [rsp+C8h] [rbp-248h]
  struct _CCB *v189; // [rsp+D8h] [rbp-238h]
  unsigned __int8 v190; // [rsp+E8h] [rbp-228h]
  int v191; // [rsp+ECh] [rbp-224h] BYREF
  bool v192; // [rsp+F0h] [rbp-220h] BYREF
  char v193; // [rsp+F1h] [rbp-21Fh]
  int v194; // [rsp+F4h] [rbp-21Ch]
  struct REFS_IO_CONTEXT *v195; // [rsp+F8h] [rbp-218h]
  __int64 v196; // [rsp+100h] [rbp-210h]
  char v197; // [rsp+108h] [rbp-208h]
  unsigned int v198[2]; // [rsp+110h] [rbp-200h]
  int v199[2]; // [rsp+118h] [rbp-1F8h]
  PFILE_OBJECT FileObject; // [rsp+120h] [rbp-1F0h]
  char v201; // [rsp+128h] [rbp-1E8h]
  __int64 *v202; // [rsp+130h] [rbp-1E0h]
  union _LARGE_INTEGER FileOffset[2]; // [rsp+138h] [rbp-1D8h] BYREF
  ULONG Length[4]; // [rsp+148h] [rbp-1C8h]
  __int64 v205; // [rsp+158h] [rbp-1B8h]
  PVOID Context2; // [rsp+160h] [rbp-1B0h]
  struct _FCB *v207; // [rsp+168h] [rbp-1A8h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+170h] [rbp-1A0h]
  __int64 v209; // [rsp+178h] [rbp-198h]
  struct _CCB *v210; // [rsp+180h] [rbp-190h]
  unsigned int v211; // [rsp+188h] [rbp-188h]
  struct _IRP_CONTEXT *v212; // [rsp+190h] [rbp-180h]
  const char *v213; // [rsp+198h] [rbp-178h]
  _OWORD v214[4]; // [rsp+1A8h] [rbp-168h] BYREF
  __int128 v215; // [rsp+1E8h] [rbp-128h]
  __int64 v216; // [rsp+1F8h] [rbp-118h]
  unsigned int v217; // [rsp+208h] [rbp-108h]
  PIRP v218; // [rsp+210h] [rbp-100h]
  struct REFS_IO_CONTEXT *v219; // [rsp+218h] [rbp-F8h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+220h] [rbp-F0h] BYREF
  struct _IO_STACK_LOCATION *v221; // [rsp+230h] [rbp-E0h]
  __int64 v222; // [rsp+238h] [rbp-D8h]
  __int64 v223; // [rsp+240h] [rbp-D0h]
  _QWORD v224[3]; // [rsp+248h] [rbp-C8h] BYREF
  _BOOL8 v225; // [rsp+260h] [rbp-B0h]
  int v226; // [rsp+268h] [rbp-A8h]
  __int64 v227; // [rsp+270h] [rbp-A0h]
  __int64 v228; // [rsp+278h] [rbp-98h]
  __int64 v229; // [rsp+280h] [rbp-90h]
  __int64 v230; // [rsp+288h] [rbp-88h]
  __int64 v231; // [rsp+290h] [rbp-80h]
  __int64 v232; // [rsp+298h] [rbp-78h]
  __int64 v233; // [rsp+2A0h] [rbp-70h]
  __int64 v234; // [rsp+2A8h] [rbp-68h]
  __int64 v235; // [rsp+2B0h] [rbp-60h]
  __int128 v236; // [rsp+2B8h] [rbp-58h] BYREF
  __int64 v237; // [rsp+2C8h] [rbp-48h]

  v3 = Irp;
  Context2 = Irp;
  v195 = a2;
  v5 = a1;
  v212 = a1;
  v219 = a2;
  v218 = Irp;
  *(_OWORD *)&FileOffset[0].LowPart = 0;
  *(_OWORD *)Length = 0;
  v205 = 0;
  v191 = 0;
  memset(v214, 0, sizeof(v214));
  v215 = 0;
  v216 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v6 = CurrentStackLocation->FileObject;
  FileObject = v6;
  FsContext = (__int64)v6->FsContext;
  if ( !FsContext )
    goto LABEL_671;
  v8 = *(_QWORD *)(FsContext + 144);
  v209 = v8;
  FsContext2 = (char *)v6->FsContext2;
  v210 = (struct _CCB *)FsContext2;
  v10 = *(_DWORD *)(v8 + 24);
  if ( (v10 & 1) == 0 && (!FsContext2 || FsContext2[80] != 4 || (v10 & 2) == 0) )
  {
    *((_DWORD *)v5 + 1) |= 0x100u;
    v11 = *((unsigned int *)v5 + 4);
    if ( (int)v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, v11);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(*((_DWORD *)v5 + 4), 0, "NtfsData.c", 0x3C3u);
    }
    else
    {
      *((_DWORD *)v5 + 4) = -1073741202;
    }
    ExRaiseStatus(*((_DWORD *)v5 + 4));
  }
  if ( FsContext2 )
  {
    v193 = FsContext2[80];
    v12 = v193;
    if ( ((v193 - 2) & 0xFC) != 0 || v193 == 3 )
      goto LABEL_671;
  }
  else
  {
    v12 = 5;
    v193 = 5;
  }
  v202 = (__int64 *)(FsContext + 136);
  v207 = *(struct _FCB **)(FsContext + 136);
  pNetRoot = v207->pNetRoot;
  if ( pNetRoot[2].Context == (PVOID)1313 && pNetRoot[2].pSrvCall == (PMRX_SRV_CALL)1024 )
  {
LABEL_671:
    RefsCompleteReadWriteRequest(v5, a2, v3, -1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221225488LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741808 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741808, "write.c", 1017);
      v179 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741808
        || RefsStatusBreakOnWin32Error && v179 == RtlNtStatusToDosErrorNoTeb(-1073741808) )
      {
        v180 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v180 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (CurrentProcess = IoGetCurrentProcess(),
               ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
               !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
        {
          __int2c();
        }
      }
      v183 = 32LL
           * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
            & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v183) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v183 + 8) = -1073741808;
      *(_QWORD *)((char *)&RefsStatusQueue + v183 + 16) = "write.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v183 + 24) = 1017;
    }
    return 3221225488LL;
  }
  v14 = *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL);
  if ( v14 < 0 && (*(_DWORD *)(FsContext + 152) & 0x2000) == 0 )
  {
    if ( v14 == -1073741608 || v14 == -1073741432 || v14 == -1073741400 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v14 = -1073741823;
      }
      else
      {
        v14 = -1073741823;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_333749fe71273bc3659f43e52285135c_Traceguids,
            3221225473LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741823 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741823, "write.c", 1039);
        v15 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741823
          || RefsStatusBreakOnWin32Error && v15 == RtlNtStatusToDosErrorNoTeb(-1073741823) )
        {
          v16 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v16 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v17 = IoGetCurrentProcess(),
                 v18 = (const char *)PsGetProcessImageFileName(v17),
                 !_strnicmp(&RefsStatusBreakForImage, v18, 0xFu))) )
          {
            __int2c();
          }
        }
        v19 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(_QWORD *)((char *)&RefsStatusQueue + v19) = KeGetCurrentThread();
        *(unsigned int *)((char *)&RefsStatusQueue + v19 + 8) = -1073741823;
        *(_QWORD *)((char *)&RefsStatusQueue + v19 + 16) = "write.c";
        *(unsigned int *)((char *)&RefsStatusQueue + v19 + 24) = 1039;
      }
    }
    RefsCompleteReadWriteRequest(v5, v195, (struct _IRP *)Context2, v14);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_333749fe71273bc3659f43e52285135c_Traceguids,
        (unsigned int)v14);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v14, 0, "write.c", 0x413u);
    return (unsigned int)v14;
  }
  if ( (v10 & 0xA000021) != 1 )
  {
    v3->IoStatus.Information = 0;
    v21 = *(_DWORD *)(v8 + 24);
    if ( (v21 & 0x20) != 0 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741431);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221225865LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741431 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741431, "write.c", 1064);
        v22 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741431
          || RefsStatusBreakOnWin32Error && v22 == RtlNtStatusToDosErrorNoTeb(-1073741431) )
        {
          v23 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v23 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v24 = IoGetCurrentProcess(),
                 v25 = (const char *)PsGetProcessImageFileName(v24),
                 !_strnicmp(&RefsStatusBreakForImage, v25, 0xFu))) )
          {
            __int2c();
          }
        }
        v26 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(_QWORD *)((char *)&RefsStatusQueue + v26) = KeGetCurrentThread();
        *(unsigned int *)((char *)&RefsStatusQueue + v26 + 8) = -1073741431;
        *(_QWORD *)((char *)&RefsStatusQueue + v26 + 16) = "write.c";
        *(unsigned int *)((char *)&RefsStatusQueue + v26 + 24) = 1064;
      }
      return 3221225865LL;
    }
    if ( (v21 & 0x8000000) != 0 || (v21 & 1) == 0 && v12 != 4 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741202);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221226094LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741202 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741202, "write.c", 1076);
        v32 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741202
          || RefsStatusBreakOnWin32Error && v32 == RtlNtStatusToDosErrorNoTeb(-1073741202) )
        {
          v33 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v33 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v34 = IoGetCurrentProcess(),
                 v35 = (const char *)PsGetProcessImageFileName(v34),
                 !_strnicmp(&RefsStatusBreakForImage, v35, 0xFu))) )
          {
            __int2c();
          }
        }
        v36 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(_QWORD *)((char *)&RefsStatusQueue + v36) = KeGetCurrentThread();
        *(unsigned int *)((char *)&RefsStatusQueue + v36 + 8) = -1073741202;
        *(_QWORD *)((char *)&RefsStatusQueue + v36 + 16) = "write.c";
        *(unsigned int *)((char *)&RefsStatusQueue + v36 + 24) = 1076;
      }
      return 3221226094LL;
    }
    if ( (v21 & 0x2000000) != 0 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741662);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221225634LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741662 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741662, "write.c", 1086);
        v27 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741662
          || RefsStatusBreakOnWin32Error && v27 == RtlNtStatusToDosErrorNoTeb(-1073741662) )
        {
          v28 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v28 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v29 = IoGetCurrentProcess(),
                 v30 = (const char *)PsGetProcessImageFileName(v29),
                 !_strnicmp(&RefsStatusBreakForImage, v30, 0xFu))) )
          {
            __int2c();
          }
        }
        v31 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(_QWORD *)((char *)&RefsStatusQueue + v31) = KeGetCurrentThread();
        *(unsigned int *)((char *)&RefsStatusQueue + v31 + 8) = -1073741662;
        *(_QWORD *)((char *)&RefsStatusQueue + v31 + 16) = "write.c";
        *(unsigned int *)((char *)&RefsStatusQueue + v31 + 24) = 1086;
      }
      return 3221225634LL;
    }
  }
  v190 = *((_BYTE *)v5 + 8) & 1;
  BYTE2(v191) = v190;
  v37 = v191 & 0xB7 | (8 * (v3->Flags & 1 | (4 * (v3->Flags & 2))));
  Flags = v6->Flags;
  LOBYTE(Flags) = BYTE1(v191) & 0xBF | (32 * (Flags & 2));
  LODWORD(v196) = Flags;
  BYTE1(v191) = Flags;
  if ( v5 == *((struct _IRP_CONTEXT **)v5 + 13) && LOBYTE(IoGetTopLevelIrp()->Type) )
    v39 = 16;
  else
    v39 = 0;
  v40 = v39 | v37 & 0xEF;
  LOBYTE(v191) = v40;
  v201 = (unsigned __int8)v40 >> 3;
  v192 = (v40 & 8) != 0;
  if ( (v40 & 8) != 0 && (*(_DWORD *)(FsContext + 152) & 0x1000000) != 0 )
  {
    v41 = *((_QWORD *)v5 + 13);
    if ( *(_BYTE *)(v41 + 40) != 13
      || (v42 = *(_QWORD *)(v41 + 72)) == 0
      || *(_DWORD *)(*(_QWORD *)(v42 + 184) + 24LL) != 590047 )
    {
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073739760);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221227536LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073739760 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073739760, "write.c", 1113);
        v43 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073739760
          || RefsStatusBreakOnWin32Error && v43 == RtlNtStatusToDosErrorNoTeb(-1073739760) )
        {
          v44 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v44 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v45 = IoGetCurrentProcess(),
                 v46 = (const char *)PsGetProcessImageFileName(v45),
                 !_strnicmp(&RefsStatusBreakForImage, v46, 0xFu))) )
          {
            __int2c();
          }
        }
        v47 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(_QWORD *)((char *)&RefsStatusQueue + v47) = KeGetCurrentThread();
        *(unsigned int *)((char *)&RefsStatusQueue + v47 + 8) = -1073739760;
        *(_QWORD *)((char *)&RefsStatusQueue + v47 + 16) = "write.c";
        *(unsigned int *)((char *)&RefsStatusQueue + v47 + 24) = 1113;
      }
      return 3221227536LL;
    }
  }
  if ( FsContext2 && (*((_DWORD *)FsContext2 + 1) & 0x2000) != 0 && (v40 & 0x40) == 0 )
  {
    RefsCompleteReadWriteRequest(v5, a2, v3, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741811 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741811, "write.c", 1125);
      v48 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741811
        || RefsStatusBreakOnWin32Error && v48 == RtlNtStatusToDosErrorNoTeb(-1073741811) )
      {
        v49 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v49 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v50 = IoGetCurrentProcess(),
               v51 = (const char *)PsGetProcessImageFileName(v50),
               !_strnicmp(&RefsStatusBreakForImage, v51, 0xFu))) )
        {
          __int2c();
        }
      }
      v52 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v52) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v52 + 8) = -1073741811;
      *(_QWORD *)((char *)&RefsStatusQueue + v52 + 16) = "write.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v52 + 24) = 1125;
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  if ( *(_DWORD *)(FsContext + 344) )
  {
    RefsCompleteRequest(v5, v3, -1073740659);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221226637LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073740659 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073740659, "write.c", 1145);
      v53 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073740659
        || RefsStatusBreakOnWin32Error && v53 == RtlNtStatusToDosErrorNoTeb(-1073740659) )
      {
        v54 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v54 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v55 = IoGetCurrentProcess(),
               v56 = (const char *)PsGetProcessImageFileName(v55),
               !_strnicmp(&RefsStatusBreakForImage, v56, 0xFu))) )
        {
          __int2c();
        }
      }
      v57 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v57) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v57 + 8) = -1073740659;
      *(_QWORD *)((char *)&RefsStatusQueue + v57 + 16) = "write.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v57 + 24) = 1145;
    }
    return 3221226637LL;
  }
  RefsUpdateFileTimestampsFromNonpagedFcb(v207, 0);
  v58 = *((_QWORD *)v5 + 1);
  v59 = CurrentStackLocation;
  if ( (v58 & 0x20000) != 0
    && *(_QWORD *)(FsContext + 32) < CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart
                                   + CurrentStackLocation->Parameters.Read.Length )
  {
    *((_QWORD *)v5 + 1) = v58 & 0xFFFFFFFFFFFDFFFFuLL;
    v59->Parameters.Read.ByteOffset.QuadPart = -1;
  }
  v199[0] = v59->Parameters.Read.Length;
  v60 = v199[0];
  QuadPart = v59->Parameters.Read.ByteOffset.QuadPart;
  FileOffset[0].QuadPart = QuadPart;
  v62.QuadPart = QuadPart + (unsigned int)v199[0];
  FileOffset[1] = v62;
  Length[0] = v199[0];
  *(_QWORD *)v198 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v63 = "EXT";
    if ( QuadPart >= 0 )
      v63 = "NEXT";
    v64 = "TL";
    if ( (v40 & 0x10) == 0 )
      v64 = "NTL";
    v65 = "SYNC";
    if ( (Flags & 0x40) == 0 )
      v65 = "ASYNC";
    v66 = "C";
    if ( !v192 )
      v66 = "NC";
    v67 = "P";
    if ( (v40 & 0x40) == 0 )
      v67 = "NP";
    v213 = "NWAIT";
    v68 = "WAIT";
    if ( !v190 )
      v68 = v213;
    WPP_SF_qiDqssssss(
      *(_QWORD *)(*(_QWORD *)v198 + 24LL),
      (_DWORD)v67,
      (_DWORD)v66,
      FsContext,
      QuadPart,
      v199[0],
      (char)v3,
      (__int64)v68,
      (__int64)v67,
      (__int64)v66,
      (__int64)v65,
      (__int64)v64,
      (__int64)v63);
    v60 = Length[0];
    v62 = FileOffset[1];
    QuadPart = FileOffset[0].QuadPart;
  }
  if ( QuadPart >= 0 && (QuadPart > v62.QuadPart || QuadPart + v60 != v62.QuadPart) )
  {
    RefsCompleteReadWriteRequest(v5, a2, v3, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741811 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741811, "write.c", 1194);
      v69 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741811
        || RefsStatusBreakOnWin32Error && v69 == RtlNtStatusToDosErrorNoTeb(-1073741811) )
      {
        v70 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v70 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v71 = IoGetCurrentProcess(),
               v72 = (const char *)PsGetProcessImageFileName(v71),
               !_strnicmp(&RefsStatusBreakForImage, v72, 0xFu))) )
        {
          __int2c();
        }
      }
      v73 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v73) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v73 + 8) = -1073741811;
      *(_QWORD *)((char *)&RefsStatusQueue + v73 + 16) = "write.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v73 + 24) = 1194;
    }
    return 3221225485LL;
  }
  if ( !v60 )
  {
    *((_QWORD *)v5 + 86) = 8;
    v3->IoStatus.Information = 0;
LABEL_228:
    RefsCompleteReadWriteRequest(v5, a2, v3, 0);
    return 0;
  }
  if ( !v192 )
  {
    v74 = *((_QWORD *)v5 + 1);
    if ( (v74 & 8) == 0 && !CcCanIWrite(FileObject, v60, (v74 & 0x41) != 0, (*((_DWORD *)v5 + 1) & 8) != 0) )
    {
      v75 = *((_DWORD *)v5 + 1);
      v76 = Context2;
      RefsPrePostIrp(v5, (PIRP)Context2);
      *((_DWORD *)v5 + 1) |= 8u;
      if ( (v75 & 8) == 0 && *(_BYTE *)(v209 + 10304) )
        *((LARGE_INTEGER *)v5 + 86) = KeQueryPerformanceCounter(0);
      CcDeferWrite(FileObject, RefsAddToWorkque, v5, v76, Length[0], (v75 & 8) != 0);
      if ( v40 < 0 )
      {
        if ( *(_WORD *)FsContext != 2050 )
          FsContext = *v202;
        v77 = *(_QWORD *)(FsContext + 96);
        if ( !--DWORD2(v215) )
        {
          *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
          ExReleaseFastResource(v77, v214);
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 259);
      }
      return 259;
    }
  }
  v78 = v209;
  if ( *(_BYTE *)(v209 + 10304) )
  {
    PerformanceCounter = *(LARGE_INTEGER *)((char *)v5 + 688);
    if ( PerformanceCounter.QuadPart <= 23 )
      PerformanceCounter = KeQueryPerformanceCounter(0);
    *((LARGE_INTEGER *)v5 + 86) = PerformanceCounter;
    v80 = v190;
    if ( (v40 & 0x40) != 0 || v192 )
      v81 = 0;
    else
      v81 = 4;
    *((_BYTE *)a2 + 56) = v81 | v190 | (*((_BYTE *)v5 + 8) >> 2) & 2 | v201 & 8;
    v78 = v209;
  }
  else
  {
    v80 = v190;
  }
  v82 = v193;
  if ( v193 != 4 )
  {
    v221 = CurrentStackLocation;
    v213 = (const char *)FsContext;
    v198[0] = 0;
    LODWORD(v202) = 0;
    v91 = (unsigned __int8)v40;
    LOBYTE(v91) = v40 & 0x40;
    v92 = 128;
    if ( (v40 & 0x40) != 0 )
    {
      v93 = (_DWORD *)(*(_QWORD *)(v209 + 808)
                     + ((unsigned __int64)(KeGetCurrentProcessorNumber() % RefsNumberProcessors) << 6));
      if ( ((__int64)v207->spacer.Resource & 0x100LL) == 0
        && ((v94 = *(_WORD *)(FsContext + 216), v94 == 128) || v94 == 176) )
      {
        ++v93[5];
        v93[6] += Length[0];
      }
      else
      {
        ++v93[11];
        v93[12] += Length[0];
      }
    }
    v95 = v192;
    if ( (_BYTE)v91 || !v192 )
      *(_DWORD *)(FsContext + 184) = 0;
    v194 = 0;
    *((_QWORD *)&v215 + 1) = 0x100000000LL;
    v216 = 0;
    if ( (v40 & 0x40) == 0 )
    {
      v96 = (unsigned int)v210;
      if ( v210 )
        *((_DWORD *)v5 + 158) = *((_DWORD *)v210 + 21);
      if ( v40 < 0 )
        goto LABEL_342;
      if ( (*((_DWORD *)v5 + 2) & 0x100LL) != 0 )
        goto LABEL_339;
      if ( (*(_DWORD *)(FsContext + 152) & 0x10) != 0 )
      {
        v92 = *(_QWORD *)(*(_QWORD *)(FsContext + 136) + 8LL) & 0x40000100LL;
        if ( v92 == 0x40000000 )
          goto LABEL_339;
      }
      v92 = (__int64)FileObject;
      if ( v82 != 5 )
      {
        if ( !v95 )
          goto LABEL_316;
        if ( FileObject->SectionObjectPointer->DataSectionObject )
          goto LABEL_339;
      }
      if ( v95 )
      {
LABEL_317:
        if ( FileOffset[0].QuadPart >= 0 )
        {
          if ( !v95 || (_BYTE)v80 || (v97 = *(_DWORD *)(FsContext + 152), (v97 & 8) != 0) && (v97 & 0x40) == 0 )
          {
            v227 = FsContext;
            v100 = (unsigned __int8)RefsAcquirePagingFastResourceShared(FileObject, FsContext, v214) << 7;
            v99 = (unsigned __int8)v40;
            LOBYTE(v99) = v40 & 0x7F;
            v40 = v99 | v100;
            LOBYTE(v191) = v99 | v100;
          }
          else
          {
            *(_QWORD *)v199 = FsContext;
            v98 = (unsigned __int8)RefsAcquirePagingFastResourceShared(FileObject, FsContext, (char *)v195 + 720) << 7;
            v99 = (unsigned __int8)v40;
            LOBYTE(v99) = v40 & 0x7F;
            v40 = v99 | v98;
            LOBYTE(v191) = v99 | v98;
            if ( ((v99 | v98) & 0x80u) != 0LL )
            {
              v190 |= 2u;
              BYTE2(v191) = v190;
            }
          }
          Flags = (unsigned __int8)v40;
          if ( v40 >= 0 )
          {
            v103 = v190;
          }
          else
          {
            if ( (*(_DWORD *)(FsContext + 152) & 0x10) == 0 || !_FCB::HasPurgeableEAs(*(_FCB **)(FsContext + 136)) )
            {
              v101 = FileObject;
              if ( (v193 == 5 || (v40 & 8) == 0 || !FileObject->SectionObjectPointer->DataSectionObject)
                && ((v40 & 8) != 0 || FileObject->SectionObjectPointer->SharedCacheMap) )
              {
LABEL_341:
                if ( (Flags & 0x80u) == 0 )
                {
                  LOBYTE(Flags) = Flags & 0xDF;
                  LOBYTE(v191) = Flags;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      30,
                      WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                      3221225688LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741608, v5, "write.c", 0x66Fu);
                  RefsRaiseStatusInternal(v5, -1073741608, v96);
                  goto LABEL_697;
                }
LABEL_342:
                if ( *(_DWORD *)(FsContext + 296) != 3
                  || (v105 = *(_WORD *)(FsContext + 216), v105 != 128) && v105 != 176 )
                {
                  if ( ((__int64)v207->spacer.Resource & 0x20) != 0 )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                    {
                      Flags = -1073741431;
                    }
                    else
                    {
                      Flags = -1073741431;
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        32,
                        WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                        3221225865LL);
                    }
                    if ( !(_BYTE)RefsStatusDebugEnabled )
                      goto LABEL_354;
                    v106 = 1662;
                    goto LABEL_353;
                  }
                  if ( (*(_DWORD *)(FsContext + 152) & 0x80u) != 0 )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                    {
                      Flags = -1073740610;
                    }
                    else
                    {
                      Flags = -1073740610;
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        33,
                        WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                        3221226686LL);
                    }
                    if ( !(_BYTE)RefsStatusDebugEnabled )
                      goto LABEL_354;
                    v106 = 1671;
                    goto LABEL_353;
                  }
                  if ( (*(_DWORD *)(FsContext + 300) & 0x40) == 0 )
                  {
                    if ( RefsIsFileOpen(v207) )
                    {
                      if ( (v40 & 8) != 0 )
                      {
                        v117 = *((_QWORD *)v5 + 13);
                        if ( v5 != (struct _IRP_CONTEXT *)v117 )
                        {
                          if ( _bittest16((const signed __int16 *)(FsContext + 256), 0xEu) )
                          {
                            if ( *(_BYTE *)(v117 + 40) == 13 )
                            {
                              v118 = *(_QWORD *)(v117 + 72);
                              if ( v118 )
                              {
                                if ( *(_DWORD *)(*(_QWORD *)(v118 + 184) + 24LL) == 590047 )
                                  v116 = 2;
                                LODWORD(v202) = v116;
                                v217 = v116;
                              }
                            }
                          }
                        }
                        if ( v115 != 5 && FileObject->SectionObjectPointer->DataSectionObject )
                        {
                          if ( *(_WORD *)FsContext == 2053
                            && *(_QWORD *)(FsContext + 432)
                            && *(_WORD *)(FsContext + 260) )
                          {
                            v119 = 1 << *(_DWORD *)(*(_QWORD *)(FsContext + 144) + 552LL);
                            v117 = -(__int64)v119;
                            v120 = FileOffset[0].QuadPart & v117;
                            v121 = (v117 & (v119 + FileOffset[1].LowPart - 1)) - (FileOffset[0].LowPart & v117);
                          }
                          else
                          {
                            v120 = FileOffset[0].QuadPart;
                            v121 = Length[0];
                          }
                          if ( *(_DWORD *)(FsContext + 176) )
                          {
                            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                            {
                              Flags = -1073740747;
                            }
                            else
                            {
                              Flags = -1073740747;
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                36,
                                WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                3221226549LL);
                            }
                            if ( !(_BYTE)RefsStatusDebugEnabled )
                              goto LABEL_354;
                            v106 = 1744;
                            goto LABEL_353;
                          }
                          Flags = RefsCacheCoherencyFlush(
                                    v5,
                                    (struct _IRP *)v117,
                                    (struct _SCB *)FsContext,
                                    v120,
                                    v121,
                                    1u,
                                    *(_DWORD *)(FsContext + 180) == 0);
                          v194 = Flags;
                          if ( Flags < 0 )
                            goto LABEL_355;
                          if ( FileObject->PrivateCacheMap )
                            RefsUninitializeCacheMap(FileObject, 0, v114);
                        }
                      }
                      if ( !v210 || (*((_DWORD *)v210 + 1) & 0x8000) == 0 )
                      {
                        v122 = *(_DWORD *)(FsContext + 300) & 0x4000;
                        Flags = v122 != 0 ? 0xC000026E : 0;
                        v194 = Flags;
                        if ( !v122 )
                        {
                          Flags = RefsSetWriteRangeFromEof(v5, FsContext, FileOffset, &v191);
                          v194 = Flags;
                          if ( Flags < 0 )
                          {
                            v108 = BYTE2(v191);
                            v190 = BYTE2(v191);
                            v107 = BYTE1(v191);
                            v40 = v191;
                            goto LABEL_357;
                          }
                          v123 = *((_QWORD *)v5 + 13);
                          v124 = *(_DWORD *)(v123 + 4);
                          if ( (v124 & 2) != 0 )
                          {
                            v190 = BYTE2(v191);
                            Flags = BYTE1(v191);
                            LODWORD(v196) = BYTE1(v191);
                          }
                          else
                          {
                            *(_DWORD *)(v123 + 4) = v124 | 2;
                            Flags = BYTE1(v191) | 0x20;
                            LODWORD(v196) = Flags;
                            BYTE1(v191) |= 0x20u;
                            v190 = BYTE2(v191);
                          }
                          v40 = v191;
LABEL_499:
                          if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 && *(_WORD *)(FsContext + 216) != 160 )
                          {
                            v196 = FsContext;
                            RefsAcquireResourceShared(v5, FsContext, 1);
                            LOBYTE(Flags) = Flags | 0x10;
                            BYTE1(v191) = Flags;
                            RefsUpdateScbFromAttribute(v5, (struct _SCB *)FsContext, 0);
                            IoStatus.Pointer = (PVOID)FsContext;
                            RefsReleaseResource(v5, FsContext);
                            LOBYTE(Flags) = Flags & 0xEF;
                            LODWORD(v196) = Flags;
                            BYTE1(v191) = Flags;
                          }
                          v144 = v190;
                          if ( (Flags & 4) != 0 && (v190 & 1) == 0 && (v40 & 8) != 0 )
                          {
                            v144 = v190 | 1;
                            v190 = v144;
                            BYTE2(v191) = v144;
                            *((_QWORD *)v5 + 1) |= 1uLL;
                            v145 = v195;
                            *((_BYTE *)v195 + 56) |= 1u;
                          }
                          else
                          {
                            v145 = v195;
                          }
                          if ( (v40 & 0x40) != 0 )
                          {
LABEL_555:
                            v151 = v210;
                            if ( (v40 & 2) != 0 )
                            {
                              RefsInitiateFileExtensionForWrite(v5, (__int64)&v191);
                              v190 = BYTE2(v191);
                              Flags = BYTE1(v191);
                              LODWORD(v196) = BYTE1(v191);
                              v40 = v191;
                            }
                            v152 = *(_DWORD *)(FsContext + 152);
                            if ( (v152 & 8) != 0 && (v152 & 0x40) == 0 )
                            {
                              if ( (v40 & 8) == 0 )
                              {
LABEL_622:
                                v164 = FileObject;
                                if ( FileObject->PrivateCacheMap > (PVOID)1 )
                                  goto LABEL_625;
                                v165 = v5;
                                if ( *(_QWORD *)(FsContext + 32) <= *(_QWORD *)(FsContext + 24) )
                                {
                                  RefsInitializeCacheMap(v5, FileObject, 0, (struct DataSCB *)FsContext);
                                  CcSetReadAheadGranularity(v164, 0x10000u);
                                  CcSetParallelFlushFile(v164, 1u);
LABEL_625:
                                  if ( (v40 & 0x20) != 0
                                    && (*((_DWORD *)v5 + 2) & 0x100LL) == 0
                                    && ((*(_DWORD *)(FsContext + 152) & 0x10) == 0
                                     || !_FCB::HasPurgeableEAs(*(_FCB **)(FsContext + 136)))
                                    && (*((_DWORD *)v5 + 2) & 0x20000LL) == 0 )
                                  {
                                    v207 = (struct _FCB *)FsContext;
                                    RefsConvertPagingFastResourceExclusiveToShared(v123, FsContext, v214);
                                    v40 &= ~0x20u;
                                    LOBYTE(v191) = v40;
                                  }
                                  if ( *(__int16 *)(FsContext + 256) >= 0
                                    || RefsReserveClusters(
                                         v5,
                                         (struct _SCB *)FsContext,
                                         FileOffset[0].QuadPart,
                                         Length[0]) )
                                  {
                                    if ( (*((_BYTE *)v5 + 41) & 2) != 0 )
                                    {
                                      p_IoStatus = &v3->IoStatus;
                                      CcPrepareMdlWrite(v164, FileOffset, Length[0], (PMDL *)Context2 + 1, p_IoStatus);
                                      Flags = p_IoStatus->Status;
                                      goto LABEL_638;
                                    }
                                    v167 = RefsMapUserBuffer(v3);
                                    if ( CcCopyWrite(v164, FileOffset, Length[0], *((_BYTE *)v5 + 8) & 1, v167) )
                                    {
                                      v169 = *((unsigned int *)v5 + 4);
                                      if ( (int)v169 >= 0 )
                                      {
                                        v3->IoStatus.Status = 0;
                                        v3->IoStatus.Information = Length[0];
                                        Flags = 0;
LABEL_638:
                                        v194 = Flags;
                                        if ( (*(_DWORD *)(*(_QWORD *)(FsContext + 144) + 24LL) & 0x4000000) == 0
                                          || Length[0] < 0x10000 )
                                        {
                                          goto LABEL_355;
                                        }
                                        IoStatus = 0;
                                        CcFlushCache(
                                          (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(FsContext + 248) + 8LL),
                                          FileOffset,
                                          Length[0],
                                          &IoStatus);
                                        v172 = *((unsigned int *)v5 + 4);
                                        if ( (int)v172 >= 0 )
                                        {
                                          Status = (unsigned int)IoStatus.Status;
                                          if ( IoStatus.Status >= 0 )
                                            goto LABEL_355;
LABEL_788:
                                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                          {
                                            WPP_SF_d(
                                              WPP_GLOBAL_Control->AttachedDevice,
                                              56,
                                              WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                              Status);
                                          }
                                          if ( (_BYTE)RefsStatusDebugEnabled )
                                            RefsStatusDebug(IoStatus.Status, v5, "write.c", 0xBA2u);
                                          RefsRaiseStatusInternal(v5, IoStatus.Status, v171);
                                          __debugbreak();
                                          JUMPOUT(0x1400A66FCLL);
                                        }
LABEL_781:
                                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                        {
                                          WPP_SF_d(
                                            WPP_GLOBAL_Control->AttachedDevice,
                                            55,
                                            WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                            v172);
                                        }
                                        if ( (_BYTE)RefsStatusDebugEnabled )
                                          RefsStatusDebug(*((_DWORD *)v5 + 4), v5, "write.c", 0xB9Fu);
                                        RefsRaiseStatusInternal(v5, *((_DWORD *)v5 + 4), v171);
                                        goto LABEL_788;
                                      }
LABEL_774:
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                      {
                                        WPP_SF_d(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          54,
                                          WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                          v169);
                                      }
                                      if ( (_BYTE)RefsStatusDebugEnabled )
                                        RefsStatusDebug(*((_DWORD *)v5 + 4), v5, "write.c", 0xB53u);
                                      RefsRaiseStatusInternal(v5, *((_DWORD *)v5 + 4), v168);
                                      goto LABEL_781;
                                    }
LABEL_767:
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                    {
                                      WPP_SF_d(
                                        WPP_GLOBAL_Control->AttachedDevice,
                                        53,
                                        WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                        3221225688LL);
                                    }
                                    if ( (_BYTE)RefsStatusDebugEnabled )
                                      RefsStatusDebug(-1073741608, v5, "write.c", 0xB4Fu);
                                    RefsRaiseStatusInternal(v5, -1073741608, v168);
                                    goto LABEL_774;
                                  }
LABEL_760:
                                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                  {
                                    WPP_SF_d(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      52,
                                      WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                      3221225599LL);
                                  }
                                  if ( (_BYTE)RefsStatusDebugEnabled )
                                    RefsStatusDebug(-1073741697, v5, "write.c", 0xB36u);
                                  RefsRaiseStatusInternal(v5, -1073741697, v166);
                                  goto LABEL_767;
                                }
LABEL_753:
                                v184 = v207;
                                v185 = RefsQueueTriageForDeadFcb(v165, v207);
                                v187 = v185;
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                {
                                  WPP_SF_qd(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    51,
                                    WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                    v184,
                                    v185);
                                }
                                if ( (_BYTE)RefsStatusDebugEnabled )
                                  RefsStatusDebug(v187, v5, "write.c", 0xAFFu);
                                RefsRaiseStatusInternal(v5, v187, v186);
                                goto LABEL_760;
                              }
                              RefsAcquireExclusiveScb(v5, FsContext, 0);
                              LOBYTE(Flags) = Flags | 0x10;
                              LODWORD(v196) = Flags;
                              BYTE1(v191) = Flags;
                              if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 )
                                RefsUpdateScbFromAttribute(v5, (struct _SCB *)FsContext, 0);
                              v153 = *(_DWORD *)(FsContext + 152);
                              if ( (v153 & 8) != 0 && (v153 & 0x40) == 0 )
                              {
                                Flags = RefsResidentWrite(
                                          v5,
                                          v3,
                                          (struct _SCB *)FsContext,
                                          FileOffset[0].LowPart,
                                          Length[0]);
                                v194 = Flags;
                                RefsCheckpointCurrentTransaction(v5);
                                RefsReleaseFcb(v5, *(struct _FCB **)(FsContext + 136));
                                v107 = v196 & 0xEF;
                                BYTE1(v191) = v196 & 0xEF;
                                goto LABEL_356;
                              }
                              RefsReleaseFcb(v5, *(struct _FCB **)(FsContext + 136));
                              LOBYTE(Flags) = Flags & 0xEF;
                              LODWORD(v196) = Flags;
                              BYTE1(v191) = Flags;
                            }
                            if ( (v40 & 8) != 0 )
                            {
                              v155 = *(int *)(v209 + 276);
                              if ( (((_DWORD)v155 - 1) & FileOffset[0].LowPart) == 0 )
                              {
                                v156 = Length[0];
                                *(_QWORD *)v199 = -v155 & (v155 + Length[0] - 1LL);
                                if ( v199[0] == Length[0] || FileOffset[1].QuadPart >= *(_QWORD *)(FsContext + 32) )
                                {
                                  if ( *(_WORD *)(FsContext + 216) == 128 )
                                  {
                                    v156 = *(unsigned int *)(*(_QWORD *)(FsContext + 144) + 28LL);
                                    if ( (v156 & 0x80u) != 0LL && (v156 & 0x400) != 0 )
                                    {
                                      v156 = *(_QWORD *)(FsContext + 136);
                                      if ( (*(_DWORD *)(v156 + 8) & 0x8905LL) == 0 && (*(_DWORD *)(v156 + 152) & 4) == 0 )
                                      {
                                        v236 = 0;
                                        v237 = 0;
                                        ActivityIdIrp = IoGetActivityIdIrp(v3, (char *)&v236 + 8);
                                        v158 = (char *)&v236 + 8;
                                        if ( ActivityIdIrp < 0 )
                                          v158 = 0;
                                        *(_QWORD *)&v236 = v158;
                                        RefsChangeLogWrite(
                                          v207,
                                          (struct _REFS_ACTIVITY_ID *)&v236,
                                          FileOffset[0].QuadPart,
                                          Length[0]);
                                      }
                                    }
                                  }
                                  if ( (*(_DWORD *)(v209 + 6568) & 2) != 0 && IoGetIoPriorityHint(v3) > IoPriorityLow )
                                  {
                                    if ( ((v159 = *(_WORD *)(FsContext + 216), v159 == 128) || v159 == 176)
                                      && !*(_WORD *)(FsContext + 224)
                                      || (v156 = 160, v159 == 160) )
                                    {
                                      RefsHeatLogIo(v3, v207);
                                    }
                                  }
                                  if ( (v190 & 1) != 0 )
                                  {
                                    v160 = v195;
                                  }
                                  else if ( (v40 & 0x40) != 0 )
                                  {
                                    v189 = v151;
                                    v160 = v195;
                                    if ( (Flags & 1) != 0 )
                                      RefsSetIoContextAsync(
                                        (struct _IRP_CONTEXT *)v156,
                                        v195,
                                        0,
                                        0,
                                        0,
                                        0,
                                        FileOffset[0].QuadPart,
                                        v198[0],
                                        1,
                                        v198[0],
                                        v188,
                                        (struct _SCB *)FsContext,
                                        v189);
                                    else
                                      RefsSetIoContextAsync(
                                        (struct _IRP_CONTEXT *)v156,
                                        v195,
                                        0,
                                        0,
                                        0,
                                        0,
                                        FileOffset[0].QuadPart,
                                        CurrentStackLocation->Parameters.Read.Length,
                                        1,
                                        CurrentStackLocation->Parameters.Read.Length,
                                        v188,
                                        (struct _SCB *)FsContext,
                                        v189);
                                  }
                                  else
                                  {
                                    v160 = v195;
                                    v161 = (struct REFS_IO_CONTEXT *)((char *)v195 + 720);
                                    if ( (v190 & 2) == 0 )
                                      v161 = (struct _MS_FAST_RESOURCE_OWNER_ENTRY *)v214;
                                    RefsSetIoContextAsync(
                                      (struct _IRP_CONTEXT *)CurrentStackLocation->Parameters.Read.Length,
                                      v195,
                                      0,
                                      *(struct _MS_FAST_RESOURCE **)(FsContext + 16),
                                      v161,
                                      0,
                                      FileOffset[0].QuadPart,
                                      CurrentStackLocation->Parameters.Read.Length,
                                      1,
                                      CurrentStackLocation->Parameters.Read.Length,
                                      v188,
                                      (struct _SCB *)FsContext,
                                      v210);
                                  }
                                  if ( (*((_BYTE *)v5 + 8) & 1) == 0 )
                                    RefsFlushForWriteThrough(v5, FsContext, 0);
                                  v162 = (unsigned int)v202;
                                  if ( (Flags & 0x20) != 0 )
                                  {
                                    v162 = (unsigned int)v202 | 0x10;
                                    v217 = (unsigned int)v202 | 0x10;
                                  }
                                  Flags = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RefsNonCachedIo)(
                                            v5,
                                            v160,
                                            v3,
                                            FsContext,
                                            (union _LARGE_INTEGER)FileOffset[0].QuadPart,
                                            v199[0],
                                            v162);
                                  v194 = Flags;
                                  if ( Flags != 259 )
                                  {
                                    Flags = v3->IoStatus.Status;
                                    v194 = Flags;
                                    if ( Flags < 0 )
                                    {
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                                      {
                                        WPP_SF_dd(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          50,
                                          WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                          3221225705LL,
                                          Flags);
                                      }
                                      *((_DWORD *)v5 + 4) = Flags;
                                      if ( (_BYTE)RefsStatusDebugEnabled )
                                        RefsStatusDebug(Flags, v5, "write.c", 0xACBu);
                                      v163 = FsRtlNormalizeNtstatus(Flags, -1073741591);
                                      ExRaiseStatus(v163);
                                    }
                                    v110 = v198[0];
                                    if ( v198[0] )
                                      v3->IoStatus.Information = v198[0];
                                    else
                                      v3->IoStatus.Information = Length[0];
                                    v107 = v196;
                                    v109 = v195;
                                    v108 = v190;
                                    goto LABEL_359;
                                  }
                                  v40 &= ~0x80u;
                                  LOBYTE(v191) = v40;
                                  v5 = 0;
                                  Context2 = 0;
                                  v218 = 0;
                                  v212 = 0;
                                  v109 = 0;
                                  v195 = 0;
                                  v219 = 0;
                                  v107 = v196;
                                  v108 = v190;
LABEL_358:
                                  v110 = v198[0];
LABEL_359:
                                  v111 = (struct _IRP *)Context2;
                                  if ( Context2 )
                                  {
                                    if ( Flags >= 0 && Flags != 259 )
                                      *((_BYTE *)v109 + 56) |= 1u;
                                    v111->IoStatus.Status = Flags;
                                    if ( Flags >= 0 && (v107 & 1) != 0 )
                                      v111->IoStatus.Information = (unsigned int)v110;
                                    v112 = FileObject;
                                    RefsPostWriteProcessing(v5, FileObject, (__int64)FileOffset, (__int64)&v191);
                                    v107 = BYTE1(v191);
                                    if ( Flags >= 0 )
                                    {
                                      v107 = BYTE1(v191) & 0xFB;
                                      BYTE1(v191) &= ~4u;
                                    }
                                    v40 = v191;
                                    if ( (v107 & 0x40) != 0 && (v191 & 0x40) == 0 && FileOffset[0].QuadPart >= 0 )
                                    {
                                      if ( (Flags & 0xC0000000) == 0xC0000000 )
                                        Information = 0;
                                      else
                                        Information = v111->IoStatus.Information;
                                      v112->CurrentByteOffset.QuadPart = FileOffset[0].QuadPart + Information;
                                    }
                                    RefsCleanupTransaction(v5, Flags, 0);
                                    RefsCommitCurrentTransaction(v5, 0);
                                    RefsFlushForWriteThrough(v5, FsContext, 0);
                                    v108 = BYTE2(v191);
                                    v190 = BYTE2(v191);
                                  }
                                  if ( ((v107 & 4) != 0 || (v40 & 4) != 0) && Flags != 259 )
                                  {
                                    v174 = *(struct _FAST_MUTEX **)(FsContext + 48);
                                    KeEnterGuardedRegion();
                                    ExAcquireFastMutexUnsafe(v174);
                                    _InterlockedIncrement((volatile signed __int32 *)(FsContext + 172));
                                    if ( (v40 & 4) != 0 )
                                    {
                                      RefsCompleteFileSizeExtension(v5, (struct DataSCB *)FsContext, (__int64)&v191);
                                      v40 = v191 & 0xFB;
                                      v108 = BYTE2(v191);
                                      v107 = BYTE1(v191);
                                    }
                                    else
                                    {
                                      v108 = v190;
                                    }
                                    if ( (v107 & 4) != 0 && *(_QWORD *)(*(_QWORD *)(FsContext + 248) + 16LL) )
                                    {
                                      HighestPendingFileSize = RefsGetHighestPendingFileSize((const struct DataSCB *)FsContext);
                                      *(_QWORD *)(v176 + 8) = HighestPendingFileSize;
                                    }
                                    v177 = *((_QWORD *)v5 + 1);
                                    if ( (v177 & 0x20000) != 0 )
                                    {
                                      *((_QWORD *)v5 + 1) = v177 & 0xFFFFFFFFFFFDFFFFuLL;
                                      CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = -1;
                                    }
                                    ++*(_DWORD *)(FsContext + 172);
                                    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
                                    KeLeaveGuardedRegion();
                                  }
                                  if ( v111 )
                                  {
                                    if ( (v107 & 0x10) != 0 )
                                      RefsReleaseFcb(v5, *(struct _FCB **)(FsContext + 136));
                                    if ( (v107 & 0x20) != 0 )
                                      *(_DWORD *)(*((_QWORD *)v5 + 13) + 4LL) &= ~2u;
                                  }
                                  if ( v40 < 0 )
                                  {
                                    if ( (v108 & 2) != 0 )
                                    {
                                      v222 = FsContext;
                                      RefsReleasePagingFastResource(v110, FsContext, (char *)v195 + 720);
                                    }
                                    else
                                    {
                                      v223 = FsContext;
                                      if ( *(_WORD *)FsContext != 2050 )
                                        FsContext = *(_QWORD *)(FsContext + 136);
                                      v178 = *(_QWORD *)(FsContext + 96);
                                      if ( !--DWORD2(v215) )
                                      {
                                        *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
                                        ExReleaseFastResource(v178, v214);
                                      }
                                    }
                                  }
                                  HIDWORD(v215) &= ~1u;
                                  RefsCompleteReadWriteRequest(v5, v195, v111, Flags);
                                  return (unsigned int)Flags;
                                }
                              }
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                              {
                                Flags = -1073741822;
                              }
                              else
                              {
                                Flags = -1073741822;
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  49,
                                  WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                  3221225474LL);
                              }
                              if ( !(_BYTE)RefsStatusDebugEnabled )
                                goto LABEL_354;
                              v106 = 2514;
LABEL_353:
                              RefsStatusDebug(Flags, 0, "write.c", v106);
LABEL_354:
                              v194 = Flags;
LABEL_355:
                              v107 = v196;
LABEL_356:
                              v108 = v190;
LABEL_357:
                              v109 = v195;
                              goto LABEL_358;
                            }
                            goto LABEL_622;
                          }
                          if ( v193 != 2 )
                          {
LABEL_552:
                            v150 = (v40 & 1) != 0;
                            v211 = v150;
                            if ( (v40 & 2) != 0 )
                            {
                              v150 |= 2u;
                              v211 = v150;
                            }
                            RefsPostUsnChange(v5, (struct _FCB *)FsContext, v150, 0);
                            goto LABEL_555;
                          }
                          v192 = 0;
                          v197 = 0;
                          *((_QWORD *)v145 + 6) = &v192;
                          if ( (Flags & 0x20) != 0 )
                          {
                            v146 = (struct _IRP_CONTEXT *)*((_QWORD *)v5 + 13);
                            if ( v146 != v5 )
                            {
                              *((_DWORD *)v146 + 1) &= ~2u;
                              LOBYTE(Flags) = Flags & 0xDF;
                              LODWORD(v196) = Flags;
                              BYTE1(v191) = Flags;
                              v197 = 1;
                            }
                          }
                          v224[0] = v145;
                          v224[1] = FsContext;
                          v224[2] = v214;
                          v225 = (v144 & 2) != 0;
                          *((_QWORD *)v5 + 18) = v224;
                          Flags = FsRtlCheckOplock(
                                    (POPLOCK)(FsContext + 88),
                                    v3,
                                    v5,
                                    RefsOplockComplete,
                                    RefsCommonWrite_::_415_::_lambda_1_::_lambda_invoker_cdecl_);
                          v194 = Flags;
                          v190 = v190 & 0xFD | (2 * v225);
                          BYTE2(v191) = v190;
                          if ( Flags )
                          {
                            if ( Flags == 259 && v192 )
                            {
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
                              {
                                Flags = 871;
                              }
                              else
                              {
                                Flags = 871;
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  47,
                                  WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                  871);
                              }
                              if ( (_BYTE)RefsStatusDebugEnabled )
                                RefsStatusDebug(871, 0, "write.c", 0x921u);
                              v194 = 871;
                            }
                            v107 = v196 & 0xEB;
                            BYTE1(v191) = v196 & 0xEB;
                            v5 = 0;
                            Context2 = 0;
                            v218 = 0;
                            v212 = 0;
                            v109 = 0;
                            v195 = 0;
                            v219 = 0;
                            v108 = v190;
                            goto LABEL_358;
                          }
                          if ( v197 )
                          {
                            *(_DWORD *)(*((_QWORD *)v5 + 13) + 4LL) |= 2u;
                            Flags = v196;
                            LOBYTE(Flags) = v196 | 0x20;
                            LODWORD(v196) = Flags;
                            BYTE1(v191) = Flags;
                          }
                          else
                          {
                            Flags = v196;
                          }
                          if ( *(_BYTE *)(FsContext + 5) )
                          {
LABEL_543:
                            v149 = *(FILE_LOCK **)(FsContext + 384);
                            if ( v149 && !FsRtlCheckLockForWriteAccess(v149, v3) )
                            {
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
                              {
                                Flags = -1073741740;
                              }
                              else
                              {
                                Flags = -1073741740;
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  48,
                                  WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                                  3221225556LL);
                              }
                              if ( !(_BYTE)RefsStatusDebugEnabled )
                                goto LABEL_354;
                              v106 = 2395;
                              goto LABEL_353;
                            }
                            goto LABEL_552;
                          }
                          *(_QWORD *)v199 = *(_QWORD *)(FsContext + 144);
                          if ( (*(_DWORD *)(*(_QWORD *)v199 + 24LL) & 0x4000005) == 1
                            && *(_WORD *)FsContext == 2053
                            && (*(_DWORD *)(FsContext + 300) & 0x40) == 0
                            && *(char *)(*(_QWORD *)(FsContext + 136) + 8LL) >= 0 )
                          {
                            if ( (*(_DWORD *)(FsContext + 152) & 0x20) == 0 )
                              goto LABEL_533;
                            if ( FsRtlOplockIsFastIoPossible((POPLOCK)(FsContext + 88)) )
                            {
                              if ( *(__int16 *)(FsContext + 256) >= 0 )
                              {
                                v148 = *(_QWORD *)(FsContext + 384);
                                if ( (!v148 || !*(_BYTE *)(v148 + 16))
                                  && (*(_DWORD *)(*(_QWORD *)v199 + 24LL) & 0x2000000) == 0
                                  && (*(_BYTE *)(*(_QWORD *)(FsContext + 136) + 8LL) & 0x20) == 0 )
                                {
                                  v147 = 1;
                                  goto LABEL_542;
                                }
                              }
LABEL_533:
                              v147 = 2;
LABEL_542:
                              *(_BYTE *)(FsContext + 5) = v147;
                              goto LABEL_543;
                            }
                          }
                          v147 = 0;
                          goto LABEL_542;
                        }
                        goto LABEL_725;
                      }
LABEL_718:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          37,
                          WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                          3221225768LL);
                      }
                      if ( (_BYTE)RefsStatusDebugEnabled )
                        RefsStatusDebug(-1073741528, v5, "write.c", 0x6FFu);
                      RefsRaiseStatusInternal(v5, -1073741528, (unsigned int)v114);
LABEL_725:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          38,
                          WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                          (unsigned int)Flags);
                      }
                      if ( (_BYTE)RefsStatusDebugEnabled )
                        RefsStatusDebug(Flags, v5, "write.c", 0x705u);
                      RefsRaiseStatusInternal(v5, Flags, (unsigned int)v114);
                      goto LABEL_732;
                    }
LABEL_711:
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        35,
                        WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                        3221225768LL);
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                      RefsStatusDebug(-1073741528, v5, "write.c", 0x694u);
                    RefsRaiseStatusInternal(v5, -1073741528, (unsigned int)v114);
                    goto LABEL_718;
                  }
LABEL_704:
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      34,
                      WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                      3221225763LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741533, v5, "write.c", 0x68Fu);
                  RefsRaiseStatusInternal(v5, -1073741533, v96);
                  goto LABEL_711;
                }
LABEL_697:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    31,
                    WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                    3221226659LL);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073740637, v5, "write.c", 0x679u);
                RefsRaiseStatusInternal(v5, -1073740637, v96);
                goto LABEL_704;
              }
            }
            if ( (v190 & 2) != 0 )
            {
              v228 = FsContext;
              v102 = (char *)v195 + 720;
            }
            else
            {
              v229 = FsContext;
              v102 = (char *)v214;
            }
            RefsReleasePagingFastResource(v101, FsContext, v102);
            LOBYTE(Flags) = v40 & 0x7F;
            LOBYTE(v191) = v40 & 0x7F;
            v103 = v190 & 0xFD;
            v190 = v103;
            BYTE2(v191) = v103;
          }
          v234 = FsContext;
          v104 = Flags & 0x7F
               | ((unsigned __int8)RefsAcquirePagingFastResourceExclusive(v99, FsContext, v214, v103 & 1) << 7);
LABEL_340:
          v40 = v104 | 0x20;
          Flags = (unsigned __int8)v40;
          LOBYTE(v191) = v40;
          goto LABEL_341;
        }
LABEL_339:
        v230 = FsContext;
        v104 = v40 & 0x7F | ((unsigned __int8)RefsAcquirePagingFastResourceExclusive(v92, FsContext, v214, v80) << 7);
        goto LABEL_340;
      }
LABEL_316:
      if ( !FileObject->SectionObjectPointer->SharedCacheMap )
        goto LABEL_339;
      goto LABEL_317;
    }
    if ( v210 && (*((_DWORD *)v210 + 2) & 2) != 0 )
      *((_DWORD *)v5 + 158) = *((_DWORD *)v210 + 21);
    if ( v5 == *((struct _IRP_CONTEXT **)v5 + 13) && LOBYTE(IoGetTopLevelIrp()->Type) )
    {
      LOBYTE(IoGetTopLevelIrp()->Type) = 0;
    }
    else if ( (*(_BYTE *)(*((_QWORD *)v5 + 13) + 8LL) & 8) != 0 )
    {
      *((_QWORD *)v5 + 1) |= 8uLL;
      v125 = v195;
      *((_BYTE *)v195 + 56) |= 2u;
      goto LABEL_425;
    }
    v125 = v195;
LABEL_425:
    if ( !*(_QWORD *)(FsContext + 16)
      || (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(FsContext + 136) + 96LL))
      || (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(FsContext + 136) + 88LL) + 64LL) )
    {
      goto LABEL_446;
    }
    if ( (*(_DWORD *)(FsContext + 152) & 0x10) != 0
      && (v126 = *(_QWORD *)(*(_QWORD *)(FsContext + 136) + 8LL) & 0x40000100LL, v126 == 0x40000000) )
    {
      v231 = FsContext;
    }
    else
    {
      v232 = FsContext;
      v40 = v40 & 0x7F
          | ((unsigned __int8)RefsAcquirePagingFastResourceSharedStarveExclusive(v126, FsContext, v214) << 7);
      LOBYTE(v191) = v40;
      if ( v40 >= 0 || (*(_DWORD *)(FsContext + 152) & 0x10) == 0 || !_FCB::HasPurgeableEAs(*(_FCB **)(FsContext + 136)) )
      {
LABEL_438:
        if ( v40 >= 0 )
        {
          v40 &= ~0x20u;
          LOBYTE(v191) = v40;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            Flags = -1073741740;
          }
          else
          {
            Flags = -1073741740;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              39,
              WPP_333749fe71273bc3659f43e52285135c_Traceguids,
              3221225556LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_354;
          v106 = 1909;
          goto LABEL_353;
        }
LABEL_446:
        if ( *(_DWORD *)(FsContext + 296) == 3 )
        {
          v128 = *(_WORD *)(FsContext + 216);
          if ( v128 == 128 || v128 == 176 )
          {
LABEL_732:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                40,
                WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                3221226659LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073740637, v5, "write.c", 0x77Fu);
            RefsRaiseStatusInternal(v5, -1073740637, v91);
            goto LABEL_739;
          }
        }
        if ( (*(_DWORD *)(FsContext + 300) & 0x40) != 0 )
        {
LABEL_739:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              WPP_333749fe71273bc3659f43e52285135c_Traceguids,
              3221225763LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741533, v5, "write.c", 0x788u);
          RefsRaiseStatusInternal(v5, -1073741533, v91);
          goto LABEL_746;
        }
        v129 = *(_DWORD *)(FsContext + 300) & 0x4000;
        v130 = v129 != 0 ? 0xC000026E : 0;
        v199[0] = v130;
        v194 = v130;
        if ( v129 )
        {
LABEL_746:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_333749fe71273bc3659f43e52285135c_Traceguids, v130);
            v130 = v199[0];
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v130, v5, "write.c", 0x78Fu);
          RefsRaiseStatusInternal(v5, v199[0], v91);
          goto LABEL_753;
        }
        if ( IoGetTopLevelIrp()->MdlAddress == (PMDL)2 )
        {
          *((_QWORD *)v5 + 1) &= ~8uLL;
          *((_BYTE *)v125 + 56) &= ~2u;
          v131 = FileObject->Flags;
          if ( (*(_DWORD *)(FsContext + 300) & 0x100) != 0 )
            FileObject->Flags = v131 | 0x8000;
          else
            FileObject->Flags = v131 & 0xFFFF7FFF;
        }
        else
        {
          v132 = *((_QWORD *)v5 + 13);
          v133 = *(_DWORD *)(v132 + 4);
          if ( (v133 & 2) != 0 )
          {
            LOBYTE(Flags) = Flags | 8;
          }
          else
          {
            *(_DWORD *)(v132 + 4) = v133 | 2;
            LOBYTE(Flags) = Flags | 0x20;
          }
          BYTE1(v191) = Flags;
          LODWORD(v196) = Flags;
        }
        v134 = *(struct _FAST_MUTEX **)(FsContext + 48);
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe(v134);
        _InterlockedIncrement((volatile signed __int32 *)(FsContext + 172));
        v136 = *(union _LARGE_INTEGER *)(FsContext + 24);
        v137 = FileOffset[0];
        if ( FileOffset[0].QuadPart >= v136.QuadPart )
        {
          *((_QWORD *)v5 + 86) = 2;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iiP)(
              WPP_GLOBAL_Control->AttachedDevice,
              43,
              v135,
              (union _LARGE_INTEGER)FileOffset[0].QuadPart,
              *(_QWORD *)(FsContext + 24),
              FsContext);
          }
          *((_QWORD *)Context2 + 7) = 0;
          ++*(_DWORD *)(FsContext + 172);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
          KeLeaveGuardedRegion();
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 0);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(0, 0, "write.c", 0x7F9u);
LABEL_470:
          Flags = 0;
          goto LABEL_354;
        }
        v138.QuadPart = -(__int64)*(int *)(v209 + 288) & (v136.QuadPart + *(int *)(v209 + 288) - 1LL);
        if ( FileOffset[1].QuadPart <= v138.QuadPart )
        {
          v138 = FileOffset[1];
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iiP)(
              WPP_GLOBAL_Control->AttachedDevice,
              45,
              (union _LARGE_INTEGER)FileOffset[1].QuadPart,
              (union _LARGE_INTEGER)FileOffset[1].QuadPart,
              (union _LARGE_INTEGER)v138.QuadPart,
              FsContext);
            v137 = FileOffset[0];
          }
          FileOffset[1] = v138;
          Length[0] = v138.LowPart - v137.LowPart;
        }
        v139 = *(union _LARGE_INTEGER *)(FsContext + 24);
        if ( v138.QuadPart > v139.QuadPart )
        {
          if ( v137.QuadPart >= v139.QuadPart )
          {
            *((_QWORD *)Context2 + 7) = 0;
            *(__m128i *)&FileOffset[0].LowPart = _mm_load_si128((const __m128i *)&_xmm);
            Length[0] = -1159767027;
            ++*(_DWORD *)(FsContext + 172);
            ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
            KeLeaveGuardedRegion();
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_333749fe71273bc3659f43e52285135c_Traceguids, 0);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
            {
              RefsStatusDebug(0, 0, "write.c", 0x829u);
              Flags = 0;
              goto LABEL_354;
            }
            goto LABEL_470;
          }
          FileOffset[1] = *(union _LARGE_INTEGER *)(FsContext + 24);
          Length[0] = v139.LowPart - v137.LowPart;
        }
        v140 = RefsGetHighestPendingFileSize((const struct DataSCB *)FsContext);
        if ( v143 > v140 )
        {
          if ( v140 <= v141 )
          {
            LOBYTE(Flags) = Flags | 2;
            BYTE1(v191) = Flags;
          }
          else
          {
            v198[0] = v140 - v142;
            v226 = v140 - v142;
          }
          LOBYTE(Flags) = Flags | 1;
          LODWORD(v196) = Flags;
          BYTE1(v191) = Flags;
        }
        ++*(_DWORD *)(FsContext + 172);
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(FsContext + 48));
        KeLeaveGuardedRegion();
        if ( (*(_BYTE *)(FsContext + 4) & 0x20) != 0 && (*(_DWORD *)(FsContext + 152) & 0x40000) != 0 )
        {
          v123 = *(unsigned int *)(*(_QWORD *)(FsContext + 136) + 8LL);
          if ( (v123 & 0x100) == 0 )
          {
            if ( (Flags & 2) == 0 )
              RefsPostUsnChange(v5, (struct _FCB *)FsContext, 1u, 0);
            RefsCheckpointCurrentTransaction(v5);
          }
        }
        v3 = (PIRP)Context2;
        goto LABEL_499;
      }
      v233 = FsContext;
      RefsReleasePagingFastResource(v127, FsContext, v214);
      v235 = FsContext;
    }
    v40 = v40 & 0x7F | ((unsigned __int8)RefsAcquirePagingFastResourceExclusive(v126, FsContext, v214, 0) << 7) | 0x20;
    LOBYTE(v191) = v40;
    goto LABEL_438;
  }
  if ( (*(_DWORD *)(v78 + 24) & 2) != 0 || (CurrentStackLocation->Flags & 0x10) != 0 )
  {
    v83 = FileOffset[0].QuadPart;
  }
  else
  {
    v83 = FileOffset[0].QuadPart;
    if ( FileOffset[0].QuadPart >= 0
      && FileOffset[0].QuadPart < *(_QWORD *)(FsContext + 32)
      && FileOffset[1].QuadPart > (unsigned int)(16 * *(_DWORD *)(v78 + 276)) )
    {
      if ( a2 )
        *((_QWORD *)v5 + 86) = 3;
      if ( v40 < 0 )
      {
        if ( *(_WORD *)FsContext != 2050 )
          FsContext = *v202;
        v84 = *(_QWORD *)(FsContext + 96);
        if ( !--DWORD2(v215) )
        {
          *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
          ExReleaseFastResource(v84, v214);
        }
      }
      RefsCompleteReadWriteRequest(v5, a2, v3, -1073741790);
      return 3221225506LL;
    }
  }
  if ( (*((_DWORD *)v210 + 1) & 0x100) != 0 )
    goto LABEL_281;
  if ( v83 < 0 || (v85 = *(union _LARGE_INTEGER *)(FsContext + 32), v85.QuadPart <= v83) )
  {
    if ( a2 )
      *((_QWORD *)v5 + 86) = 3;
    if ( v40 < 0 )
    {
      if ( *(_WORD *)FsContext != 2050 )
        FsContext = *v202;
      v87 = *(_QWORD *)(FsContext + 96);
      if ( !--DWORD2(v215) )
      {
        *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
        ExReleaseFastResource(v87, v214);
      }
    }
    goto LABEL_228;
  }
  if ( v85.QuadPart >= FileOffset[1].QuadPart )
  {
LABEL_281:
    v86 = Length[0];
  }
  else
  {
    FileOffset[1] = *(union _LARGE_INTEGER *)(FsContext + 32);
    v86 = v85.LowPart - v83;
    Length[0] = v86;
  }
  v89 = RefsVolumeDasdIo(v5, a2, v3, (struct _SCB *)FsContext, v210, v83, v86);
  if ( v89 >= 0 )
    RefsUpdateFileTimestampsForModification(FileObject, v207, v210, v88);
  if ( (Flags & 0x40) != 0 && (v40 & 0x40) == 0 && v89 >= 0 )
    FileObject->CurrentByteOffset.QuadPart = FileOffset[0].QuadPart + v3->IoStatus.Information;
  if ( v40 < 0 )
  {
    if ( *(_WORD *)FsContext != 2050 )
      FsContext = *v202;
    v90 = *(_QWORD *)(FsContext + 96);
    if ( !--DWORD2(v215) )
    {
      *((_QWORD *)&v215 + 1) &= 0xFFFFFFFD00000000uLL;
      ExReleaseFastResource(v90, v214);
    }
  }
  if ( v190 )
    RefsCompleteReadWriteRequest(v5, v195, v3, v89);
  return (unsigned int)v89;
}

```

## disassembly

```asm
0x1400a2c60  mov     r11, rsp
0x1400a2c63  push    rbx
0x1400a2c64  push    rsi
0x1400a2c65  push    rdi
0x1400a2c66  push    r12
0x1400a2c68  push    r13
0x1400a2c6a  push    r14
0x1400a2c6c  push    r15
0x1400a2c6e  sub     rsp, 260h
0x1400a2c75  mov     rax, cs:__security_cookie
0x1400a2c7c  xor     rax, rsp
0x1400a2c7f  mov     [rsp+298h+var_40], rax
0x1400a2c87  mov     rbx, r8
0x1400a2c8a  mov     [r11-1B0h], rbx
0x1400a2c91  mov     r12, rdx
0x1400a2c94  mov     [r11-218h], rdx
0x1400a2c9b  mov     rdi, rcx
0x1400a2c9e  mov     [r11-180h], rcx
0x1400a2ca5  mov     [r11-0F8h], rdx
0x1400a2cac  mov     [r11-100h], rbx
0x1400a2cb3  xorps   xmm0, xmm0
0x1400a2cb6  xor     eax, eax
0x1400a2cb8  movups  xmmword ptr [rsp+298h+FileOffset], xmm0
0x1400a2cc0  movups  xmmword ptr [rsp+298h+Length], xmm0
0x1400a2cc8  mov     [r11-1B8h], rax
0x1400a2ccf  xor     r15d, r15d
0x1400a2cd2  mov     dword ptr [rsp+298h+var_224], r15d
0x1400a2cd7  movups  [rsp+298h+var_168], xmm0
0x1400a2cdf  movups  [rsp+298h+var_158], xmm0
0x1400a2ce7  movups  [rsp+298h+var_148], xmm0
0x1400a2cef  movups  [rsp+298h+var_138], xmm0
0x1400a2cf7  movups  [rsp+298h+var_128], xmm0
0x1400a2cff  mov     [r11-118h], rax
0x1400a2d06  mov     rax, [r8+0B8h]
0x1400a2d0d  mov     [rsp+298h+var_1A0], rax
0x1400a2d15  mov     r8, [rax+30h]
0x1400a2d19  mov     [rsp+298h+FileObject], r8
0x1400a2d21  mov     rsi, [r8+18h]
0x1400a2d25  test    rsi, rsi
0x1400a2d28  jz      loc_1400A5F17
0x1400a2d2e  mov     r9, [rsi+90h]
0x1400a2d35  mov     [rsp+298h+var_198], r9
0x1400a2d3d  mov     r13, [r8+20h]
0x1400a2d41  mov     [rsp+298h+var_190], r13
0x1400a2d49  mov     ecx, [r9+18h]
0x1400a2d4d  test    cl, 1
0x1400a2d50  jnz     loc_1400A2DED
0x1400a2d56  test    r13, r13
0x1400a2d59  jz      short loc_1400A2D6B
0x1400a2d5b  cmp     byte ptr [r13+50h], 4
0x1400a2d60  jnz     short loc_1400A2D6B
0x1400a2d62  test    cl, 2
0x1400a2d65  jnz     loc_1400A2DED
0x1400a2d6b  or      dword ptr [rdi+4], 100h
0x1400a2d72  mov     r9d, [rdi+10h]
0x1400a2d76  test    r9d, r9d
0x1400a2d79  js      short loc_1400A2D84
0x1400a2d7b  mov     dword ptr [rdi+10h], 0C000026Eh
0x1400a2d82  jmp     short loc_1400A2DDD
0x1400a2d84  lea     r13, WPP_GLOBAL_Control
0x1400a2d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2d92  cmp     rcx, r13
0x1400a2d95  jz      short loc_1400A2DBB
0x1400a2d97  test    dword ptr [rcx+2Ch], 100h
0x1400a2d9e  jz      short loc_1400A2DBB
0x1400a2da0  cmp     byte ptr [rcx+29h], 4
0x1400a2da4  jb      short loc_1400A2DBB
0x1400a2da6  mov     edx, 0Bh
0x1400a2dab  lea     r8, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids
0x1400a2db2  mov     rcx, [rcx+18h]
0x1400a2db6  call    WPP_SF_d
0x1400a2dbb  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a2dc2  test    al, al
0x1400a2dc4  jz      short loc_1400A2DDD
0x1400a2dc6  mov     r9d, 3C3h; unsigned int
0x1400a2dcc  lea     r8, aNtfsdataC; "NtfsData.c"
0x1400a2dd3  xor     edx, edx; struct _IRP_CONTEXT *
0x1400a2dd5  mov     ecx, [rdi+10h]; Status
0x1400a2dd8  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400a2ddd  mov     ecx, [rdi+10h]; Status
0x1400a2de0  call    cs:__imp_ExRaiseStatus
0x1400a2ded  test    r13, r13
0x1400a2df0  jnz     short loc_1400A2DFA
0x1400a2df2  mov     dl, 5
0x1400a2df4  mov     byte ptr [rsp+298h+var_224+5], dl
0x1400a2df8  jmp     short loc_1400A2E17
0x1400a2dfa  movzx   edx, byte ptr [r13+50h]
0x1400a2dff  mov     byte ptr [rsp+298h+var_224+5], dl
0x1400a2e03  lea     eax, [rdx-2]
0x1400a2e06  test    al, 0FCh
0x1400a2e08  jnz     loc_1400A5F17
0x1400a2e0e  cmp     dl, 3
0x1400a2e11  jz      loc_1400A5F17
0x1400a2e17  lea     rax, [rsi+88h]
0x1400a2e1e  mov     [rsp+298h+var_1E0], rax
0x1400a2e26  mov     rax, [rax]
0x1400a2e29  mov     [rsp+298h+var_1A8], rax
0x1400a2e31  mov     rax, [rax+58h]
0x1400a2e35  cmp     qword ptr [rax+100h], 521h
0x1400a2e40  jnz     short loc_1400A2E53
0x1400a2e42  cmp     qword ptr [rax+0F8h], 400h
0x1400a2e4d  jz      loc_1400A5F17
0x1400a2e53  mov     rax, [rdi+68h]
0x1400a2e57  mov     r14d, [rax+10h]
0x1400a2e5b  test    r14d, r14d
0x1400a2e5e  jns     loc_1400A30C1
0x1400a2e64  test    dword ptr [rsi+98h], 2000h
0x1400a2e6e  jnz     loc_1400A30C1
0x1400a2e74  cmp     r14d, 0C00000D8h
0x1400a2e7b  jz      short loc_1400A2EE7
0x1400a2e7d  cmp     r14d, 0C0000188h
0x1400a2e84  jz      short loc_1400A2EE7
0x1400a2e86  cmp     r14d, 0C00001A8h
0x1400a2e8d  jz      short loc_1400A2EE7
0x1400a2e8f  lea     r13, WPP_GLOBAL_Control
0x1400a2e96  lea     rbx, aWriteC; "write.c"
0x1400a2e9d  mov     r9d, r14d; int
0x1400a2ea0  mov     r8, [rsp+298h+Context2]; struct _IRP *
0x1400a2ea8  mov     rdx, [rsp+298h+var_218]; struct REFS_IO_CONTEXT *
0x1400a2eb0  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1400a2eb3  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x1400a2eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2ebf  cmp     rcx, r13
0x1400a2ec2  jz      loc_1400A309B
0x1400a2ec8  test    dword ptr [rcx+2Ch], 100h
0x1400a2ecf  jz      loc_1400A309B
0x1400a2ed5  test    r14d, r14d
0x1400a2ed8  js      loc_1400A307D
0x1400a2ede  cmp     byte ptr [rcx+29h], 5
0x1400a2ee2  jmp     loc_1400A3081
0x1400a2ee7  lea     r13, WPP_GLOBAL_Control
0x1400a2eee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2ef5  cmp     rcx, r13
0x1400a2ef8  jz      short loc_1400A2F29
0x1400a2efa  test    dword ptr [rcx+2Ch], 100h
0x1400a2f01  jz      short loc_1400A2F29
0x1400a2f03  mov     r14d, 0C0000001h
0x1400a2f09  cmp     byte ptr [rcx+29h], 4
0x1400a2f0d  jb      short loc_1400A2F2F
0x1400a2f0f  mov     edx, 13h
0x1400a2f14  mov     r9d, r14d
0x1400a2f17  lea     r8, WPP_333749fe71273bc3659f43e52285135c_Traceguids
0x1400a2f1e  mov     rcx, [rcx+18h]
0x1400a2f22  call    WPP_SF_d
0x1400a2f27  jmp     short loc_1400A2F2F
0x1400a2f29  mov     r14d, 0C0000001h
0x1400a2f2f  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a2f36  test    al, al
0x1400a2f38  jz      loc_1400A2E96
0x1400a2f3e  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400a2f44  lea     rbx, aWriteC; "write.c"
0x1400a2f4b  cmp     eax, r14d
0x1400a2f4e  jnz     short loc_1400A2F85
0x1400a2f50  mov     r9, gs:188h
0x1400a2f59  mov     dword ptr [rsp+298h+var_268], 40Fh
0x1400a2f61  mov     qword ptr [rsp+298h+Retrying], rbx
0x1400a2f66  mov     [rsp+298h+BytesToWrite], r14d
0x1400a2f6b  lea     r8, aThPXSI; "th%p %x %s:%i\n"
0x1400a2f72  xor     edx, edx; Level
0x1400a2f74  mov     ecx, 95h; ComponentId
0x1400a2f79  call    cs:__imp_DbgPrintEx
0x1400a2f80  nop     dword ptr [rax+rax+00h]
0x1400a2f85  mov     ecx, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400a2f8b  mov     esi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400a2f91  cmp     ecx, r14d
0x1400a2f94  jz      short loc_1400A2FB5
0x1400a2f96  test    esi, esi
0x1400a2f98  jz      loc_1400A3038
0x1400a2f9e  mov     ecx, r14d; Status
0x1400a2fa1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400a2fa8  nop     dword ptr [rax+rax+00h]
0x1400a2fad  cmp     esi, eax
0x1400a2faf  jnz     loc_1400A3038
0x1400a2fb5  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400a2fbc  mov     rsi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400a2fc3  test    rcx, rcx
0x1400a2fc6  jz      short loc_1400A3036
0x1400a2fc8  mov     rax, gs:188h
0x1400a2fd1  cmp     rcx, rax
0x1400a2fd4  jnz     short loc_1400A3038
0x1400a2fd6  test    rsi, rsi
0x1400a2fd9  jz      short loc_1400A2FEC
0x1400a2fdb  call    cs:__imp_IoGetCurrentProcess
0x1400a2fe2  nop     dword ptr [rax+rax+00h]
0x1400a2fe7  cmp     rsi, rax
0x1400a2fea  jnz     short loc_1400A3038
0x1400a2fec  cmp     cs:?RefsStatusBreakForImage@@3PADA, r15b; char near * RefsStatusBreakForImage
0x1400a2ff3  jz      short loc_1400A3030
0x1400a2ff5  call    cs:__imp_IoGetCurrentProcess
0x1400a2ffc  nop     dword ptr [rax+rax+00h]
0x1400a3001  mov     rcx, rax
0x1400a3004  call    cs:__imp_PsGetProcessImageFileName
0x1400a300b  nop     dword ptr [rax+rax+00h]
0x1400a3010  mov     rdx, rax; Str2
0x1400a3013  mov     r8d, 0Fh; MaxCount
0x1400a3019  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x1400a3020  call    cs:__imp__strnicmp
0x1400a3027  nop     dword ptr [rax+rax+00h]
0x1400a302c  test    eax, eax
0x1400a302e  jnz     short loc_1400A3038
0x1400a3030  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x1400a3036  int     2Ch; Windows NT - assertion failure
0x1400a3038  mov     ecx, 1
0x1400a303d  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, ecx; ulong RefsStatusNextQueueEntry
0x1400a3045  inc     ecx
0x1400a3047  and     ecx, 0FFFh
0x1400a304d  shl     rcx, 5
0x1400a3051  mov     rax, gs:188h
0x1400a305a  lea     r8, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x1400a3061  mov     [rcx+r8], rax
0x1400a3065  mov     [rcx+r8+8], r14d
0x1400a306a  mov     [rcx+r8+10h], rbx
0x1400a306f  mov     dword ptr [rcx+r8+18h], 40Fh
0x1400a3078  jmp     loc_1400A2E9D
0x1400a307d  cmp     byte ptr [rcx+29h], 4
0x1400a3081  jb      short loc_1400A309B
0x1400a3083  mov     edx, 14h
0x1400a3088  mov     r9d, r14d
0x1400a308b  lea     r8, WPP_333749fe71273bc3659f43e52285135c_Traceguids
0x1400a3092  mov     rcx, [rcx+18h]
0x1400a3096  call    WPP_SF_d
0x1400a309b  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a30a2  test    al, al
0x1400a30a4  jz      short loc_1400A30B9
0x1400a30a6  mov     r9d, 413h; unsigned int
0x1400a30ac  mov     r8, rbx; char *
0x1400a30af  xor     edx, edx; struct _IRP_CONTEXT *
0x1400a30b1  mov     ecx, r14d; Status
0x1400a30b4  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400a30b9  mov     eax, r14d
0x1400a30bc  jmp     loc_1400A60C0
0x1400a30c1  and     ecx, 0A000021h
0x1400a30c7  cmp     ecx, 1
0x1400a30ca  jz      loc_1400A35FF
0x1400a30d0  mov     [rbx+38h], r15
0x1400a30d4  mov     eax, [r9+18h]
0x1400a30d8  test    al, 20h
0x1400a30da  jz      loc_1400A3282
0x1400a30e0  mov     r14d, 0C0000189h
0x1400a30e6  mov     r9d, r14d; int
0x1400a30e9  mov     r8, rbx; struct _IRP *
0x1400a30ec  mov     rdx, r12; struct REFS_IO_CONTEXT *
0x1400a30ef  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1400a30f2  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x1400a30f7  lea     r13, WPP_GLOBAL_Control
0x1400a30fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3105  cmp     rcx, r13
0x1400a3108  jz      short loc_1400A3131
0x1400a310a  test    dword ptr [rcx+2Ch], 100h
0x1400a3111  jz      short loc_1400A3131
0x1400a3113  cmp     byte ptr [rcx+29h], 4
0x1400a3117  jb      short loc_1400A3131
0x1400a3119  mov     edx, 15h
0x1400a311e  mov     r9d, r14d
0x1400a3121  lea     r8, WPP_333749fe71273bc3659f43e52285135c_Traceguids
0x1400a3128  mov     rcx, [rcx+18h]
0x1400a312c  call    WPP_SF_d
0x1400a3131  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a3138  test    al, al
0x1400a313a  jz      loc_1400A327A
0x1400a3140  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400a3146  lea     rbx, aWriteC; "write.c"
0x1400a314d  cmp     eax, r14d
0x1400a3150  jnz     short loc_1400A3187
0x1400a3152  mov     r9, gs:188h
0x1400a315b  mov     dword ptr [rsp+298h+var_268], 428h
0x1400a3163  mov     qword ptr [rsp+298h+Retrying], rbx
0x1400a3168  mov     [rsp+298h+BytesToWrite], r14d
0x1400a316d  lea     r8, aThPXSI; "th%p %x %s:%i\n"
0x1400a3174  xor     edx, edx; Level
0x1400a3176  mov     ecx, 95h; ComponentId
0x1400a317b  call    cs:__imp_DbgPrintEx
0x1400a3182  nop     dword ptr [rax+rax+00h]
0x1400a3187  mov     ecx, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400a318d  mov     edi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400a3193  cmp     ecx, r14d
0x1400a3196  jz      short loc_1400A31B7
0x1400a3198  test    edi, edi
0x1400a319a  jz      loc_1400A323A
0x1400a31a0  mov     ecx, r14d; Status
0x1400a31a3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400a31aa  nop     dword ptr [rax+rax+00h]
0x1400a31af  cmp     edi, eax
0x1400a31b1  jnz     loc_1400A323A
0x1400a31b7  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400a31be  mov     rdi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400a31c5  test    rcx, rcx
0x1400a31c8  jz      short loc_1400A3238
0x1400a31ca  mov     rax, gs:188h
0x1400a31d3  cmp     rcx, rax
0x1400a31d6  jnz     short loc_1400A323A
0x1400a31d8  test    rdi, rdi
0x1400a31db  jz      short loc_1400A31EE
0x1400a31dd  call    cs:__imp_IoGetCurrentProcess
0x1400a31e4  nop     dword ptr [rax+rax+00h]
0x1400a31e9  cmp     rdi, rax
0x1400a31ec  jnz     short loc_1400A323A
0x1400a31ee  cmp     cs:?RefsStatusBreakForImage@@3PADA, r15b; char near * RefsStatusBreakForImage
0x1400a31f5  jz      short loc_1400A3232
0x1400a31f7  call    cs:__imp_IoGetCurrentProcess
  ... truncated ...
```
