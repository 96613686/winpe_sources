# UnionFs::UfsShadowFileObject::SetUp(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathCachePayload &,UnionFs::ShareAccessCaller,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x14005913c`
- end: `0x140059ff7`
- name: `?SetUp@UfsShadowFileObject@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsLayerCtx@2@AEAVUfsPathCachePayload@2@W4ShareAccessCaller@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `3771`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, struct _FLT_CALLBACK_DATA *@<rdx>, UnionFs::UfsPathCachePayload *, struct UnionFs::StackEventTracer *, __int64, struct UnionFs::Utils::CheckOplockHParams *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013b60`
- `0x14001568c`

## callees

- `0x140001008`
- `0x14000110c`
- `0x14000f81c`
- `0x140010168`
- `0x140024c78`
- `0x140025c20`
- `0x140027764`
- `0x1400284f0`
- `0x14002a2b0`
- `0x140041650`
- `0x140042270`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140057a14`
- `0x140057a7c`
- `0x14005913c`
- `0x14005a3a8`
- `0x14006989c`
- `0x140069bcc`
- `0x140069ee8`
- `0x14006a0dc`
- `0x140079d8c`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!IoSetShadowFileInformation` at `0x140059cf0`
- `ntoskrnl!IoSetShadowFileInformation` at `0x140059cf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400593f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400596c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059963`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059edc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400593f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400596c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059963`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059edc`
- `ntoskrnl!ZwClose` at `0x140059316`
- `ntoskrnl!ZwClose` at `0x140059431`
- `ntoskrnl!ZwClose` at `0x1400596fe`
- `ntoskrnl!ZwClose` at `0x14005999c`
- `ntoskrnl!ZwClose` at `0x140059f15`
- `ntoskrnl!ZwClose` at `0x140059fb9`
- `ntoskrnl!ZwClose` at `0x140059316`
- `ntoskrnl!ZwClose` at `0x140059431`
- `ntoskrnl!ZwClose` at `0x1400596fe`
- `ntoskrnl!ZwClose` at `0x14005999c`
- `ntoskrnl!ZwClose` at `0x140059f15`
- `ntoskrnl!ZwClose` at `0x140059fb9`
- `ntoskrnl!ObfReferenceObject` at `0x140059328`
- `ntoskrnl!ObfReferenceObject` at `0x140059328`
- `ntoskrnl!ObfDereferenceObject` at `0x14005941b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400596e8`
- `ntoskrnl!ObfDereferenceObject` at `0x140059986`
- `ntoskrnl!ObfDereferenceObject` at `0x140059eff`
- `ntoskrnl!ObfDereferenceObject` at `0x140059fa3`
- `ntoskrnl!ObfDereferenceObject` at `0x14005941b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400596e8`
- `ntoskrnl!ObfDereferenceObject` at `0x140059986`
- `ntoskrnl!ObfDereferenceObject` at `0x140059eff`
- `ntoskrnl!ObfDereferenceObject` at `0x140059fa3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059512`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005969b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059781`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059939`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059eb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059f74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059512`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005969b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059781`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059939`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059eb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059f74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005951e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400596a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005978d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059945`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059ebe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059f80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005951e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400596a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005978d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059945`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059ebe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059f80`
- `FLTMGR!FltOplockFsctrl` at `0x140059be4`
- `FLTMGR!FltOplockFsctrl` at `0x140059c83`
- `FLTMGR!FltOplockFsctrl` at `0x140059be4`
- `FLTMGR!FltOplockFsctrl` at `0x140059c83`
- `FLTMGR!FltObjectReference` at `0x140059dd1`
- `FLTMGR!FltObjectReference` at `0x140059dd1`
- `FLTMGR!FltReferenceContext` at `0x1400591bb`
- `FLTMGR!FltReferenceContext` at `0x1400591bb`
- `FLTMGR!FltReleaseContext` at `0x140059228`
- `FLTMGR!FltReleaseContext` at `0x1400592b4`
- `FLTMGR!FltReleaseContext` at `0x140059445`
- `FLTMGR!FltReleaseContext` at `0x140059593`
- `FLTMGR!FltReleaseContext` at `0x14005967c`
- `FLTMGR!FltReleaseContext` at `0x140059716`
- `FLTMGR!FltReleaseContext` at `0x14005975e`
- `FLTMGR!FltReleaseContext` at `0x14005991a`
- `FLTMGR!FltReleaseContext` at `0x1400599b0`
- `FLTMGR!FltReleaseContext` at `0x140059e93`
- `FLTMGR!FltReleaseContext` at `0x140059f29`
- `FLTMGR!FltReleaseContext` at `0x140059f55`
- `FLTMGR!FltReleaseContext` at `0x140059fcd`
- `FLTMGR!FltReleaseContext` at `0x140059228`
- `FLTMGR!FltReleaseContext` at `0x1400592b4`
- `FLTMGR!FltReleaseContext` at `0x140059445`
- `FLTMGR!FltReleaseContext` at `0x140059593`
- `FLTMGR!FltReleaseContext` at `0x14005967c`
- `FLTMGR!FltReleaseContext` at `0x140059716`
- `FLTMGR!FltReleaseContext` at `0x14005975e`
- `FLTMGR!FltReleaseContext` at `0x14005991a`
- `FLTMGR!FltReleaseContext` at `0x1400599b0`
- `FLTMGR!FltReleaseContext` at `0x140059e93`
- `FLTMGR!FltReleaseContext` at `0x140059f29`
- `FLTMGR!FltReleaseContext` at `0x140059f55`
- `FLTMGR!FltReleaseContext` at `0x140059fcd`

## string_xrefs

- `0x140059a31`: `ORIGIN: Filter oplock request on directory`
- `0x140059a6e`: `ORIGIN: Filter oplock request with existing opens`
- `0x140059284`: `PUSH: Checking caller access from cache`
- `0x140059180`: `ORIGIN: FILE_DIRECTORY_FILE and FILE_NON_DIRECTORY_FILE both set`
- `0x14005924d`: `ORIGIN: Attempt to open a directory as a file.`
- `0x1400591f0`: `ORIGIN: Attempt to open a file as a directory.`
- `0x1400599eb`: `PUSH: CheckShareAccess`
- `0x140059bf7`: `API: Setting up atomic create-with-oplock`
- `0x1400597f1`: `UnionFs::UfsShadowFileObject::CheckShareAccess`
- `0x1400597e0`: `PUSH: Checking share access of SFO`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsShadowFileObject::SetUp(
        struct _FILE_OBJECT *a1,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_CALLBACK_DATA *a3,
        __int64 a4,
        PFLT_CONTEXT *a5,
        struct UnionFs::StackEventTracer *a6,
        __int64 *a7,
        struct UnionFs::Utils::CheckOplockHParams *a8)
{
  unsigned int v10; // esi
  PFLT_CONTEXT *v12; // rdi
  _QWORD *v13; // rbx
  ULONG Options; // edx
  _QWORD *v15; // rcx
  const char *v16; // rax
  __int64 v17; // r8
  unsigned int v18; // edi
  struct UnionFs::UfsFsContext *v19; // r15
  int DuplicateBackingFileHandle; // r14d
  volatile signed __int32 *v21; // rcx
  utl::_RefCountBase **v22; // r12
  utl::_RefCountBase *v23; // r14
  utl::_RefCountBase *v24; // rax
  __int64 v25; // rcx
  int ShadowFsContext2; // r12d
  UnionFs::UfsFsContext2 *v27; // rdi
  struct _FLT_RELATED_OBJECTS *v28; // rax
  int v29; // r8d
  int v30; // r9d
  char *v31; // rdx
  PVOID *v32; // rax
  PFLT_CONTEXT v33; // rcx
  const char *v34; // rax
  __int64 v35; // r8
  int v36; // r12d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  int v39; // r8d
  int v40; // r9d
  const char *v41; // rax
  __int64 v42; // r8
  ULONG Flags; // eax
  struct _FLT_RELATED_OBJECTS *v44; // rcx
  __int64 v45; // r8
  char *v46; // rdx
  int v47; // r8d
  int v48; // r9d
  PFLT_CONTEXT v49; // r12
  NTSTATUS v50; // eax
  int v51; // r13d
  struct UnionFs::StackEventTracer *v52; // [rsp+28h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v53; // [rsp+30h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v54; // [rsp+30h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v55; // [rsp+30h] [rbp-D8h]
  PVOID *p_P; // [rsp+38h] [rbp-D0h]
  _WORD v57[2]; // [rsp+58h] [rbp-B0h] BYREF
  int v58; // [rsp+5Ch] [rbp-ACh] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-A8h] BYREF
  PVOID Object; // [rsp+68h] [rbp-A0h] BYREF
  PERESOURCE Resource; // [rsp+70h] [rbp-98h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-90h]
  int v63; // [rsp+80h] [rbp-88h] BYREF
  PVOID P; // [rsp+88h] [rbp-80h] BYREF
  struct _FLT_RELATED_OBJECTS *v65; // [rsp+90h] [rbp-78h] BYREF
  char v66[8]; // [rsp+98h] [rbp-70h] BYREF
  char *v67; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v68[6]; // [rsp+A8h] [rbp-60h] BYREF
  char v69; // [rsp+D8h] [rbp-30h]
  void *p_PreviouslyGrantedAccess; // [rsp+E0h] [rbp-28h] BYREF
  utl::_RefCountBase *v71; // [rsp+E8h] [rbp-20h]
  int v72; // [rsp+F0h] [rbp-18h]
  _QWORD v73[5]; // [rsp+F8h] [rbp-10h] BYREF
  char v74; // [rsp+120h] [rbp+18h]
  char v75; // [rsp+170h] [rbp+68h] BYREF
  struct _FLT_CALLBACK_DATA *v76; // [rsp+178h] [rbp+70h]
  __int64 v77; // [rsp+180h] [rbp+78h]

  v77 = a4;
  v76 = a3;
  if ( ((__int64)a2->Iopb->Parameters.QueryEa.EaList & 0x41) == 0x41 )
  {
    v10 = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x127001D01D4LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "ORIGIN: FILE_DIRECTORY_FILE and FILE_NON_DIRECTORY_FILE both set",
      (const char *)v53);
    return v10;
  }
  v12 = a5;
  FltReferenceContext(a5[9]);
  v13 = v12[9];
  Options = a2->Iopb->Parameters.Create.Options;
  v15 = (_QWORD *)v13[4];
  Context = v15;
  if ( (Options & 1) != 0 && !*(_BYTE *)(v15[18] + 96LL) )
  {
    v16 = "ORIGIN: Attempt to open a file as a directory.";
    v17 = 0x128001D01E1LL;
    v18 = -1073741565;
LABEL_7:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)v18,
      (int)a8,
      (struct UnionFs::StackEventTracer *)v17,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      v16,
      (const char *)v53);
    if ( v13 )
      FltReleaseContext(v13);
    return v18;
  }
  if ( (Options & 0x40) != 0 && *(_BYTE *)(v15[18] + 96LL) )
  {
    v16 = "ORIGIN: Attempt to open a directory as a file.";
    v17 = 0x195001D01E9LL;
    v18 = -1073741638;
    goto LABEL_7;
  }
  v19 = a8;
  DuplicateBackingFileHandle = UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(
                                 (UnionFs::UfsPathCachePayload *)v12,
                                 a2,
                                 a8,
                                 0);
  if ( DuplicateBackingFileHandle < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DuplicateBackingFileHandle,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x22F001D01EFLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Checking caller access from cache",
      (const char *)v53);
LABEL_15:
    if ( v13 )
      FltReleaseContext(v13);
    return (unsigned int)DuplicateBackingFileHandle;
  }
  Handle = 0;
  DuplicateBackingFileHandle = UnionFs::UfsPathCachePayload::GetDuplicateBackingFileHandle(v12, &Handle, v19);
  if ( DuplicateBackingFileHandle < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DuplicateBackingFileHandle,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x23C001D01F6LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Getting duplicate layer handle",
      (const char *)v53);
    if ( Handle )
      ZwClose(Handle);
    goto LABEL_15;
  }
  ObfReferenceObject(v12[8]);
  v21 = (volatile signed __int32 *)v12[5];
  v22 = (utl::_RefCountBase **)v12[4];
  v67 = (char *)v12[8];
  Object = v67;
  if ( v21 )
    _InterlockedIncrement(v21 + 2);
  _InterlockedIncrement((volatile signed __int32 *)*v22 + 2);
  v23 = *v22;
  v71 = *v22;
  p_PreviouslyGrantedAccess = v22;
  if ( v21 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v21);
  v24 = v22[1];
  P = 0;
  v25 = *a7;
  *(_QWORD *)v66 = *(_QWORD *)v24;
  ShadowFsContext2 = UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2(
                       v25,
                       (unsigned int)&p_PreviouslyGrantedAccess,
                       (unsigned int)&Handle,
                       (unsigned int)&Object,
                       (__int64)&P,
                       (_DWORD)v19);
  if ( ShadowFsContext2 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)ShadowFsContext2,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x12D001D020DLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Creating shadow FsContext2",
      (const char *)v54);
LABEL_27:
    v27 = (UnionFs::UfsFsContext2 *)P;
LABEL_28:
    if ( v27 )
    {
      UnionFs::UfsFsContext2::~UfsFsContext2(v27);
      ExFreePoolWithTag(v27, 0);
    }
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( Handle )
      ZwClose(Handle);
    if ( v13 )
      FltReleaseContext(v13);
    return (unsigned int)ShadowFsContext2;
  }
  v28 = (struct _FLT_RELATED_OBJECTS *)Context;
  a1->FsContext = Context;
  v65 = v28;
  FsFltWil::AcquireResourceExclusive(&Resource, (char *)v28[2].Instance + 56);
  v68[0] = a1;
  v68[3] = v57;
  v57[0] = 0;
  v75 = 0;
  v68[4] = (char *)v57 + 1;
  v68[1] = &v75;
  v68[5] = &v65;
  v68[2] = v77;
  v69 = 1;
  ShadowFsContext2 = UnionFs::UfsStreamHandleCtx::FltSet(**(PFLT_INSTANCE **)(v77 + 8), a1);
  if ( ShadowFsContext2 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)ShadowFsContext2,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x12E001D024BLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Attaching handle context to SFO",
      (const char *)v54);
LABEL_41:
    wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    goto LABEL_27;
  }
  v75 = 1;
  Context = 0;
  ShadowFsContext2 = UnionFs::UfsInstanceCtx::FltGet(**(PFLT_INSTANCE **)(v77 + 8));
  if ( ShadowFsContext2 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)ShadowFsContext2,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x12F001D0256LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Getting scratch instance ctx",
      (const char *)v54);
    if ( Context )
      FltReleaseContext(Context);
    goto LABEL_41;
  }
  v27 = (UnionFs::UfsFsContext2 *)P;
  a1->FsContext2 = P;
  v58 = 0;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    v58 = UnionFs::Utils::BreakBatchAndHOplocks((UnionFs::Utils *)a2, v76, v65, v19, v52);
    ShadowFsContext2 = v58;
    if ( v58 == 259 )
    {
      if ( (unsigned int)dword_14009E178 <= 4
        || (qword_14009E188 & 0x202200) == 0
        || (qword_14009E190 & 0x202200) != qword_14009E190 )
      {
        goto LABEL_53;
      }
      v63 = 625;
      P = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
      v31 = byte_140098B11;
      v67 = "Oplock break";
      p_P = &P;
      v32 = (PVOID *)&v67;
LABEL_52:
      *(_QWORD *)v66 = "UnionFs::UfsShadowFileObject::SetUp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        2105856,
        (_DWORD)v31,
        v29,
        v30,
        (__int64)v32,
        (__int64)v66,
        (__int64)p_P,
        (__int64)&v63);
LABEL_53:
      v10 = v58;
      goto LABEL_54;
    }
    if ( v58 < 0 )
    {
      v34 = "PUSH: Breaking oplocks";
      v35 = 0x6EE001D0276LL;
LABEL_70:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)ShadowFsContext2,
        (int)v19,
        (struct UnionFs::StackEventTracer *)v35,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
        v34,
        (const char *)v54);
LABEL_71:
      if ( Context )
        FltReleaseContext(Context);
      wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
      if ( Resource )
      {
        ExReleaseResourceLite(Resource);
        KeLeaveCriticalRegion();
      }
      goto LABEL_28;
    }
  }
  LODWORD(v54) = (_DWORD)a6;
  v36 = UnionFs::Utils::CheckShareAccess(
          *(unsigned int *)(*(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8) + 20LL),
          a2->Iopb->Parameters.Create.ShareAccess,
          a1,
          a1->FsContext,
          1);
  if ( v36 >= 0 )
    v36 = 0;
  else
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v36,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x627001D05B2LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::CheckShareAccess",
      "PUSH: Checking share access of SFO",
      (const char *)v54);
  v58 = v36;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v58 == -1073741757 )
    {
      Iopb = a2->Iopb;
      if ( (Iopb->Parameters.Create.Options & 0x100) == 0 )
      {
        SecurityContext = Iopb->Parameters.Create.SecurityContext;
        v72 = 128;
        p_PreviouslyGrantedAccess = &SecurityContext->AccessState->PreviouslyGrantedAccess;
        v71 = (utl::_RefCountBase *)((char *)&Iopb->Parameters.WMI.BufferSize + 2);
        ShadowFsContext2 = UnionFs::Utils::CheckOplockH(
                             a2,
                             v76,
                             (struct _FLT_RELATED_OBJECTS *)((char *)v65 + 88),
                             (unsigned int **)&p_PreviouslyGrantedAccess,
                             v19);
        if ( ShadowFsContext2 == 259 )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x202200) != 0
            && (qword_14009E190 & 0x202200) == qword_14009E190 )
          {
            v63 = 663;
            v67 = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
            *(_QWORD *)v66 = "UnionFs::UfsShadowFileObject::SetUp";
            P = "H oplock break for sharing violation";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              2105856,
              (unsigned int)byte_140098B99,
              v39,
              v40,
              (__int64)&P,
              (__int64)v66,
              (__int64)&v67,
              (__int64)&v63);
          }
          if ( Context )
            FltReleaseContext(Context);
          wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
          if ( Resource )
          {
            ExReleaseResourceLite(Resource);
            KeLeaveCriticalRegion();
          }
          if ( v27 )
          {
            UnionFs::UfsFsContext2::~UfsFsContext2(v27);
            ExFreePoolWithTag(v27, 0);
          }
          if ( v23 )
            utl::_RefCountBase::_DecStrong(v23);
          if ( Object )
            ObfDereferenceObject(Object);
          if ( Handle )
            ZwClose(Handle);
          if ( v13 )
            FltReleaseContext(v13);
          return 259;
        }
        if ( ShadowFsContext2 < 0 )
        {
          v34 = "PUSH: CheckOplockH";
          v35 = 0x3DE001D029CLL;
          goto LABEL_70;
        }
      }
    }
  }
  ShadowFsContext2 = v58;
  if ( v58 < 0 )
  {
    v34 = "PUSH: CheckShareAccess";
    v35 = 0x22E001D02A0LL;
    goto LABEL_70;
  }
  LOBYTE(v57[0]) = 1;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (a2->Iopb->Parameters.Create.Options & 0x100000) != 0 )
    {
      if ( *(_BYTE *)(*(_QWORD *)&v65[3].Size + 96LL) )
      {
        v41 = "ORIGIN: Filter oplock request on directory";
        v42 = 0x6EF001D02AFLL;
        v10 = -1073741811;
LABEL_109:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)v10,
          (int)v19,
          (struct UnionFs::StackEventTracer *)v42,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
          v41,
          (const char *)v54);
LABEL_54:
        v33 = Context;
        if ( !Context )
        {
LABEL_56:
          wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
          if ( Resource )
          {
            ExReleaseResourceLite(Resource);
            KeLeaveCriticalRegion();
          }
          if ( v27 )
          {
            UnionFs::UfsFsContext2::~UfsFsContext2(v27);
            ExFreePoolWithTag(v27, 0);
          }
          if ( v23 )
            utl::_RefCountBase::_DecStrong(v23);
          if ( Object )
            ObfDereferenceObject(Object);
          if ( Handle )
            ZwClose(Handle);
          if ( v13 )
            FltReleaseContext(v13);
          return v10;
        }
LABEL_55:
        FltReleaseContext(v33);
        goto LABEL_56;
      }
      if ( LODWORD(v65[4].Volume) > 1 )
      {
        v41 = "ORIGIN: Filter oplock request with existing opens";
        v42 = 0x6F0001D02B5LL;
        v10 = -1073741598;
        goto LABEL_109;
      }
    }
    v58 = UnionFs::Utils::CheckOplock(a2, (__int64)v76, (PVOID *)&v65[1].Transaction, (int)v19, 0);
    ShadowFsContext2 = v58;
    if ( v58 == 259 )
    {
      if ( (unsigned int)dword_14009E178 <= 4
        || (qword_14009E188 & 0x202200) == 0
        || (qword_14009E190 & 0x202200) != qword_14009E190 )
      {
        goto LABEL_53;
      }
      v63 = 705;
      v67 = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
      v31 = &byte_140098BD7;
      P = "Oplock break";
      p_P = (PVOID *)&v67;
      v32 = &P;
      goto LABEL_52;
    }
    if ( v58 < 0 )
    {
      v34 = "PUSH: Checking oplock";
      v35 = 0x6F1001D02C6LL;
      goto LABEL_70;
    }
    ShadowFsContext2 = UnionFs::Utils::CheckOplock(a2, (__int64)v76, (PVOID *)&v65[1].Transaction, (int)v19, 2);
    if ( ShadowFsContext2 < 0 )
    {
      v34 = "PUSH: Oplock key check";
      v35 = 0x6F2001D02D1LL;
      goto LABEL_70;
    }
  }
  Flags = a1->Flags;
  v44 = v65;
  _InterlockedIncrement((volatile signed __int32 *)&v65[4].Volume);
  if ( (Flags & 8) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)&v44[4].Volume + 1);
  HIBYTE(v57[0]) = 1;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (a2->Iopb->Parameters.Create.Options & 0x10000) != 0 )
    {
      ShadowFsContext2 = FltOplockFsctrl((POPLOCK)&v65[1].Transaction, a2, (ULONG)v65[4].Volume);
      if ( ShadowFsContext2 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)ShadowFsContext2,
          (int)v19,
          (struct UnionFs::StackEventTracer *)0x6F3001D02E2LL,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
          "API: Setting up atomic create-with-oplock",
          (const char *)v54);
        goto LABEL_71;
      }
    }
  }
  v73[0] = a2;
  v73[1] = &v58;
  v73[2] = v76;
  v73[3] = &v65;
  v73[4] = v19;
  v74 = 1;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (a2->Iopb->Parameters.Create.Options & 0x100000) != 0 && !*(_BYTE *)(*(_QWORD *)&v65[3].Size + 96LL) )
    {
      ShadowFsContext2 = FltOplockFsctrl((POPLOCK)&v65[1].Transaction, a2, (ULONG)v65[4].Volume);
      if ( ShadowFsContext2 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)ShadowFsContext2,
          (int)v19,
          (struct UnionFs::StackEventTracer *)0x6F4001D0306LL,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
          "API: Setting up reserve opfilter",
          (const char *)v54);
        wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
        goto LABEL_71;
      }
    }
  }
  v45 = *(_QWORD *)v66;
  v46 = v67;
  a1->LockOperation = v67[72];
  a1->DeletePending = v46[73];
  a1->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)*((_QWORD *)v46 + 5);
  v58 = IoSetShadowFileInformation(a1, v46, v45);
  if ( v58 < 0
    && (unsigned int)dword_14009E178 > 3
    && (qword_14009E188 & 0x2000) != 0
    && (qword_14009E190 & 0x2000) == qword_14009E190 )
  {
    v63 = v58;
    v67 = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
    p_PreviouslyGrantedAccess = "Failed to set shadow file information";
    LODWORD(P) = 800;
    *(_QWORD *)v66 = "UnionFs::UfsShadowFileObject::SetUp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)&byte_140098B4F,
      v47,
      v48,
      (__int64)&p_PreviouslyGrantedAccess,
      (__int64)v66,
      (__int64)&v67,
      (__int64)&P,
      (__int64)&v63);
  }
  v49 = Context;
  a1->Vpb = (PVPB)*((_QWORD *)Context + 4);
  UnionFs::UfsShadowFileObject::UpdateFileSizesFromBFO((UnionFs::UfsShadowFileObject *)a1);
  if ( a1->CurrentByteOffset.QuadPart )
    MicrosoftTelemetryAssertTriggeredMsgKM("this->CurrentByteOffset.QuadPart == 0");
  v50 = FltObjectReference(*(PVOID *)v49);
  LODWORD(P) = v50;
  if ( v50 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v50,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x6000A017BLL,
      (unsigned __int64)"UnionFs::UfsInstanceCtx::IncrementActiveShadowFileCount",
      "API: Referencing FLT_INSTANCE",
      (const char *)v54);
    v10 = (unsigned int)P;
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)P,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x92001D0337LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Incrementing active SFO count",
      (const char *)v55);
    wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
    v33 = v49;
    goto LABEL_55;
  }
  _InterlockedIncrement((volatile signed __int32 *)v49 + 28);
  v51 = UnionFs::UfsStreamCtx::RememberSFO((UnionFs::UfsStreamCtx *)v13, a1, v19);
  if ( v51 >= 0 )
  {
    *((_DWORD *)v27 + 10) |= 1u;
    v69 = 0;
    v74 = 0;
    wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
    FltReleaseContext(v49);
    wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( Handle )
      ZwClose(Handle);
    if ( v13 )
      FltReleaseContext(v13);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v51,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x46B001D033ELL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Remembering new SFO",
      (const char *)v54);
    wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
    FltReleaseContext(v49);
    wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    if ( v27 )
    {
      UnionFs::UfsFsContext2::~UfsFsContext2(v27);
      ExFreePoolWithTag(v27, 0);
    }
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( Handle )
      ZwClose(Handle);
    if ( v13 )
      FltReleaseContext(v13);
    return (unsigned int)v51;
  }
}

```

## disassembly

```asm
0x14005913c  mov     rax, rsp
0x14005913f  mov     [rax+8], rbx
0x140059143  mov     [rax+20h], r9
0x140059147  mov     [rax+18h], r8
0x14005914b  push    rbp
0x14005914c  push    rsi
0x14005914d  push    rdi
0x14005914e  push    r12
0x140059150  push    r13
0x140059152  push    r14
0x140059154  push    r15
0x140059156  lea     rbp, [rax-58h]
0x14005915a  sub     rsp, 120h
0x140059161  mov     rax, [rdx+10h]
0x140059165  mov     rsi, rdx
0x140059168  mov     r13, rcx
0x14005916b  mov     r10d, [rax+20h]
0x14005916f  and     r10d, 41h
0x140059173  cmp     r10b, 41h ; 'A'
0x140059177  jnz     short loc_1400591B0
0x140059179  mov     rdx, [rbp+50h+arg_38]; int
0x140059180  lea     rax, aOriginFileDire; "ORIGIN: FILE_DIRECTORY_FILE and FILE_NO"...
0x140059187  mov     esi, 0C000000Dh
0x14005918c  mov     [rsp+150h+var_130], rax; char *
0x140059191  mov     ecx, esi; this
0x140059193  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x14005919a  mov     r8, 127001D01D4h; struct UnionFs::StackEventTracer *
0x1400591a4  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400591a9  mov     eax, esi
0x1400591ab  jmp     loc_140059FDB
0x1400591b0  mov     rdi, [rbp+50h+arg_20]
0x1400591b7  mov     rcx, [rdi+48h]; Context
0x1400591bb  call    cs:__imp_FltReferenceContext
0x1400591c2  nop     dword ptr [rax+rax+00h]
0x1400591c7  mov     rax, [rsi+10h]
0x1400591cb  xor     r12d, r12d
0x1400591ce  mov     rbx, [rdi+48h]
0x1400591d2  mov     edx, [rax+20h]
0x1400591d5  mov     rcx, [rbx+20h]
0x1400591d9  mov     [rsp+150h+Context], rcx
0x1400591de  test    dl, 1
0x1400591e1  jz      short loc_14005923B
0x1400591e3  mov     rax, [rcx+90h]
0x1400591ea  cmp     [rax+60h], r12b
0x1400591ee  jnz     short loc_14005923B
0x1400591f0  lea     rax, aOriginAttemptT_1; "ORIGIN: Attempt to open a file as a dir"...
0x1400591f7  mov     r8, 128001D01E1h; struct UnionFs::StackEventTracer *
0x140059201  mov     edi, 0C0000103h
0x140059206  mov     rdx, [rbp+50h+arg_38]; int
0x14005920d  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x140059214  mov     ecx, edi; this
0x140059216  mov     [rsp+150h+var_130], rax; char *
0x14005921b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140059220  test    rbx, rbx
0x140059223  jz      short loc_140059234
0x140059225  mov     rcx, rbx; Context
0x140059228  call    cs:__imp_FltReleaseContext
0x14005922f  nop     dword ptr [rax+rax+00h]
0x140059234  mov     eax, edi
0x140059236  jmp     loc_140059FDB
0x14005923b  test    dl, 40h
0x14005923e  jz      short loc_140059265
0x140059240  mov     rax, [rcx+90h]
0x140059247  cmp     [rax+60h], r12b
0x14005924b  jz      short loc_140059265
0x14005924d  lea     rax, aOriginAttemptT_3; "ORIGIN: Attempt to open a directory as "...
0x140059254  mov     r8, 195001D01E9h
0x14005925e  mov     edi, 0C00000BAh
0x140059263  jmp     short loc_140059206
0x140059265  mov     r15, [rbp+50h+arg_38]
0x14005926c  xor     r9d, r9d; bool
0x14005926f  mov     r8, r15; struct UnionFs::StackEventTracer *
0x140059272  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x140059275  mov     rcx, rdi; this
0x140059278  call    ?CheckAndCacheCallerAccess@UfsPathCachePayload@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &,bool)
0x14005927d  mov     r14d, eax
0x140059280  test    eax, eax
0x140059282  jns     short loc_1400592C8
0x140059284  lea     rax, aPushCheckingCa_0; "PUSH: Checking caller access from cache"
0x14005928b  mov     r8, 22F001D01EFh; struct UnionFs::StackEventTracer *
0x140059295  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x14005929c  mov     [rsp+150h+var_130], rax; char *
0x1400592a1  mov     rdx, r15; int
0x1400592a4  mov     ecx, r14d; this
0x1400592a7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400592ac  test    rbx, rbx
0x1400592af  jz      short loc_1400592C0
0x1400592b1  mov     rcx, rbx; Context
0x1400592b4  call    cs:__imp_FltReleaseContext
0x1400592bb  nop     dword ptr [rax+rax+00h]
0x1400592c0  mov     eax, r14d
0x1400592c3  jmp     loc_140059FDB
0x1400592c8  mov     r8, r15
0x1400592cb  mov     [rsp+150h+Handle], r12
0x1400592d0  lea     rdx, [rsp+150h+Handle]
0x1400592d5  mov     rcx, rdi
0x1400592d8  call    ?GetDuplicateBackingFileHandle@UfsPathCachePayload@UnionFs@@QEBAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::GetDuplicateBackingFileHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,UnionFs::StackEventTracer &)
0x1400592dd  mov     r14d, eax
0x1400592e0  test    eax, eax
0x1400592e2  jns     short loc_140059324
0x1400592e4  lea     rax, aPushGettingDup; "PUSH: Getting duplicate layer handle"
0x1400592eb  mov     r8, 23C001D01F6h; struct UnionFs::StackEventTracer *
0x1400592f5  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x1400592fc  mov     [rsp+150h+var_130], rax; char *
0x140059301  mov     rdx, r15; int
0x140059304  mov     ecx, r14d; this
0x140059307  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005930c  mov     rcx, [rsp+150h+Handle]; Handle
0x140059311  test    rcx, rcx
0x140059314  jz      short loc_1400592AC
0x140059316  call    cs:__imp_ZwClose
0x14005931d  nop     dword ptr [rax+rax+00h]
0x140059322  jmp     short loc_1400592AC
0x140059324  mov     rcx, [rdi+40h]; Object
0x140059328  call    cs:__imp_ObfReferenceObject
0x14005932f  nop     dword ptr [rax+rax+00h]
0x140059334  mov     rax, [rdi+40h]
0x140059338  mov     rcx, [rdi+28h]; this
0x14005933c  mov     r12, [rdi+20h]
0x140059340  mov     [rbp+50h+var_B8], rax
0x140059344  mov     [rsp+150h+Object], rax
0x140059349  test    rcx, rcx
0x14005934c  jz      short loc_140059352
0x14005934e  lock inc dword ptr [rcx+8]
0x140059352  mov     rax, [r12]
0x140059356  lock inc dword ptr [rax+8]
0x14005935a  mov     r14, [r12]
0x14005935e  mov     [rbp+50h+var_70], r14
0x140059362  mov     [rbp+50h+var_78], r12
0x140059366  test    rcx, rcx
0x140059369  jz      short loc_140059370
0x14005936b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140059370  mov     rax, [r12+8]
0x140059375  lea     r9, [rsp+150h+Object]
0x14005937a  mov     rdi, [rbp+50h+arg_30]
0x140059381  lea     r8, [rsp+150h+Handle]
0x140059386  mov     [rsp+150h+var_128], r15; char *
0x14005938b  lea     rdx, [rbp+50h+var_78]
0x14005938f  mov     [rbp+50h+P], 0
0x140059397  mov     rax, [rax]
0x14005939a  mov     rcx, [rdi]
0x14005939d  mov     qword ptr [rbp+50h+var_C0], rax
0x1400593a1  lea     rax, [rbp+50h+P]
0x1400593a5  mov     [rsp+150h+var_130], rax; struct UnionFs::StackEventTracer *
0x1400593aa  call    ?CreateShadowFsContext2@UfsStreamHandleCtx@UnionFs@@QEAAJ$$QEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAV?$unique_ptr@VUfsFsContext2@UnionFs@@U?$default_delete@VUfsFsContext2@UnionFs@@@utl@@@4@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2(utl::shared_ptr<UnionFs::UfsLayerCtx> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &&,utl::unique_ptr<UnionFs::UfsFsContext2,utl::default_delete<UnionFs::UfsFsContext2>> &,UnionFs::StackEventTracer &)
0x1400593af  mov     r12d, eax
0x1400593b2  test    eax, eax
0x1400593b4  jns     loc_140059459
0x1400593ba  lea     rax, aPushCreatingSh; "PUSH: Creating shadow FsContext2"
0x1400593c1  mov     r8, 12D001D020Dh; struct UnionFs::StackEventTracer *
0x1400593cb  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x1400593d2  mov     [rsp+150h+var_130], rax; char *
0x1400593d7  mov     rdx, r15; int
0x1400593da  mov     ecx, r12d; this
0x1400593dd  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400593e2  mov     rdi, [rbp+50h+P]
0x1400593e6  test    rdi, rdi
0x1400593e9  jz      short loc_140059404
0x1400593eb  mov     rcx, rdi; this
0x1400593ee  call    ??1UfsFsContext2@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext2::~UfsFsContext2(void)
0x1400593f3  xor     edx, edx; Tag
0x1400593f5  mov     rcx, rdi; P
0x1400593f8  call    cs:__imp_ExFreePoolWithTag
0x1400593ff  nop     dword ptr [rax+rax+00h]
0x140059404  test    r14, r14
0x140059407  jz      short loc_140059411
0x140059409  mov     rcx, r14; this
0x14005940c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140059411  mov     rcx, [rsp+150h+Object]; Object
0x140059416  test    rcx, rcx
0x140059419  jz      short loc_140059427
0x14005941b  call    cs:__imp_ObfDereferenceObject
0x140059422  nop     dword ptr [rax+rax+00h]
0x140059427  mov     rcx, [rsp+150h+Handle]; Handle
0x14005942c  test    rcx, rcx
0x14005942f  jz      short loc_14005943D
0x140059431  call    cs:__imp_ZwClose
0x140059438  nop     dword ptr [rax+rax+00h]
0x14005943d  test    rbx, rbx
0x140059440  jz      short loc_140059451
0x140059442  mov     rcx, rbx; Context
0x140059445  call    cs:__imp_FltReleaseContext
0x14005944c  nop     dword ptr [rax+rax+00h]
0x140059451  mov     eax, r12d
0x140059454  jmp     loc_140059FDB
0x140059459  mov     rax, [rsp+150h+Context]
0x14005945e  lea     rcx, [rsp+150h+Resource]
0x140059463  mov     [r13+18h], rax
0x140059467  mov     [rbp+50h+var_C8], rax
0x14005946b  mov     rdx, [rax+78h]
0x14005946f  add     rdx, 38h ; '8'
0x140059473  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140059478  xor     eax, eax
0x14005947a  mov     [rbp+50h+var_B0], r13
0x14005947e  mov     byte ptr [rsp+150h+var_100+1], al
0x140059482  lea     rcx, [rsp+150h+var_100]
0x140059487  mov     [rbp+50h+var_98], rcx
0x14005948b  mov     r9, r15
0x14005948e  mov     byte ptr [rsp+150h+var_100], al
0x140059492  lea     rcx, [rsp+150h+var_100+1]
0x140059497  mov     [rbp+50h+arg_8], al
0x14005949a  mov     r8, rdi
0x14005949d  mov     [rbp+50h+var_90], rcx
0x1400594a1  lea     rax, [rbp+50h+arg_8]
0x1400594a5  mov     [rbp+50h+var_A8], rax
0x1400594a9  lea     rcx, [rbp+50h+var_C8]
0x1400594ad  mov     rax, [rbp+50h+arg_18]
0x1400594b1  mov     rdx, r13; FileObject
0x1400594b4  mov     [rbp+50h+var_88], rcx
0x1400594b8  mov     [rbp+50h+var_A0], rax
0x1400594bc  mov     [rbp+50h+var_80], 1
0x1400594c0  mov     rcx, [rax+8]
0x1400594c4  mov     rcx, [rcx]; Instance
0x1400594c7  call    ?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x1400594cc  mov     r12d, eax
0x1400594cf  test    eax, eax
0x1400594d1  jns     short loc_14005952F
0x1400594d3  lea     rax, aPushAttachingH; "PUSH: Attaching handle context to SFO"
0x1400594da  mov     r8, 12E001D024Bh; struct UnionFs::StackEventTracer *
0x1400594e4  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x1400594eb  mov     [rsp+150h+var_130], rax; char *
0x1400594f0  mov     rdx, r15; int
0x1400594f3  mov     ecx, r12d; this
0x1400594f6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400594fb  lea     rcx, [rbp+50h+var_B0]
0x1400594ff  call    wil__details__lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3______lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___
0x140059504  mov     rcx, [rsp+150h+Resource]; Resource
0x140059509  test    rcx, rcx
0x14005950c  jz      loc_1400593E2
0x140059512  call    cs:__imp_ExReleaseResourceLite
0x140059519  nop     dword ptr [rax+rax+00h]
0x14005951e  call    cs:__imp_KeLeaveCriticalRegion
0x140059525  nop     dword ptr [rax+rax+00h]
0x14005952a  jmp     loc_1400593E2
0x14005952f  mov     r9, [rbp+50h+arg_18]
0x140059533  lea     r8, [rsp+150h+Context]
0x140059538  mov     [rbp+50h+arg_8], 1
0x14005953c  xor     edx, edx
0x14005953e  mov     [rsp+150h+Context], 0
0x140059547  mov     rcx, [r9+8]
0x14005954b  mov     r9, r15
0x14005954e  mov     rcx, [rcx]; Instance
0x140059551  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140059556  mov     r12d, eax
0x140059559  test    eax, eax
0x14005955b  jns     short loc_1400595A4
0x14005955d  lea     rax, aPushGettingScr_1; "PUSH: Getting scratch instance ctx"
0x140059564  mov     r8, 12F001D0256h; struct UnionFs::StackEventTracer *
0x14005956e  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x140059575  mov     [rsp+150h+var_130], rax; char *
0x14005957a  mov     rdx, r15; int
0x14005957d  mov     ecx, r12d; this
0x140059580  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140059585  mov     rcx, [rsp+150h+Context]; Context
0x14005958a  test    rcx, rcx
0x14005958d  jz      loc_1400594FB
0x140059593  call    cs:__imp_FltReleaseContext
0x14005959a  nop     dword ptr [rax+rax+00h]
0x14005959f  jmp     loc_1400594FB
0x1400595a4  mov     rdi, [rbp+50h+P]
0x1400595a8  mov     [r13+20h], rdi
0x1400595ac  mov     dword ptr [rsp+150h+var_100+4], 0
0x1400595b4  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x1400595b9  test    eax, eax
0x1400595bb  jz      loc_14005979E
0x1400595c1  mov     r8, [rbp+50h+var_C8]; struct _FLT_RELATED_OBJECTS *
0x1400595c5  mov     r9, r15; struct UnionFs::UfsFsContext *
0x1400595c8  mov     rdx, [rbp+50h+arg_10]; struct _FLT_CALLBACK_DATA *
0x1400595cc  mov     rcx, rsi; this
0x1400595cf  call    ?BreakBatchAndHOplocks@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsFsContext@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::BreakBatchAndHOplocks(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsFsContext &,UnionFs::StackEventTracer &)
0x1400595d4  mov     dword ptr [rsp+150h+var_100+4], eax
0x1400595d8  mov     r12d, eax
0x1400595db  cmp     eax, 103h
0x1400595e0  jnz     loc_140059727
0x1400595e6  mov     eax, cs:dword_14009E178
0x1400595ec  cmp     eax, 4
0x1400595ef  jbe     short loc_14005966E
0x1400595f1  mov     rdx, cs:qword_14009E190
0x1400595f8  mov     ecx, 202200h
0x1400595fd  mov     rax, cs:qword_14009E188
0x140059604  test    rcx, rax
0x140059607  jz      short loc_14005966E
0x140059609  mov     rax, rdx
0x14005960c  and     rax, rcx
0x14005960f  cmp     rax, rdx
0x140059612  jnz     short loc_14005966E
0x140059614  lea     rax, aOnecoreBaseFsU_17; "onecore\\base\\fs\\unionfs\\sys\\sfosup"...
0x14005961b  mov     [rsp+150h+var_D8], 271h
0x140059623  mov     [rbp+50h+P], rax
0x140059627  lea     rdx, byte_140098B11
0x14005962e  lea     rax, aOplockBreak; "Oplock break"
0x140059635  mov     [rbp+50h+var_B8], rax
0x140059639  lea     rax, [rsp+150h+var_D8]
0x14005963e  mov     [rsp+150h+var_118], rax
0x140059643  lea     rax, [rbp+50h+P]
0x140059647  mov     [rsp+150h+var_120], rax
0x14005964c  lea     rax, [rbp+50h+var_C0]
0x140059650  mov     [rsp+150h+var_128], rax
0x140059655  lea     rax, [rbp+50h+var_B8]
0x140059659  lea     rsi, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
  ... truncated ...
```
