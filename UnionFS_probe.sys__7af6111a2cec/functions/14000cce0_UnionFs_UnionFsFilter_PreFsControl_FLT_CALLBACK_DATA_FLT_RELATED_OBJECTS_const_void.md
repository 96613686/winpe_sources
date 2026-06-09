# UnionFs::UnionFsFilter::PreFsControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x14000cce0`
- end: `0x14000de65`
- name: `?PreFsControl@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `4485`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400747d0`

## callees

- `0x140001008`
- `0x1400053c0`
- `0x140005444`
- `0x140005574`
- `0x1400056b4`
- `0x140005cc8`
- `0x140005ec4`
- `0x140005ff8`
- `0x1400060b4`
- `0x140006168`
- `0x140006340`
- `0x1400069b4`
- `0x140008388`
- `0x140009860`
- `0x140009b40`
- `0x14000a398`
- `0x14000cce0`
- `0x14000e2dc`
- `0x14000f06c`
- `0x14000f374`
- `0x14000f7fc`
- `0x140010148`
- `0x1400279fc`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x1400699dc`
- `0x140074a84`
- `0x140074ae0`
- `0x140079df4`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d013`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d146`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d33c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d446`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d543`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d67d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000db2e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000dca0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d013`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d146`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d33c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d446`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d543`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d67d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000db2e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000dca0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da6f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da6f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000d986`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000d986`
- `FLTMGR!FltReleaseContext` at `0x14000d1ab`
- `FLTMGR!FltReleaseContext` at `0x14000d4a9`
- `FLTMGR!FltReleaseContext` at `0x14000db8f`
- `FLTMGR!FltReleaseContext` at `0x14000dd01`
- `FLTMGR!FltReleaseContext` at `0x14000de14`
- `FLTMGR!FltReleaseContext` at `0x14000d1ab`
- `FLTMGR!FltReleaseContext` at `0x14000d4a9`
- `FLTMGR!FltReleaseContext` at `0x14000db8f`
- `FLTMGR!FltReleaseContext` at `0x14000dd01`
- `FLTMGR!FltReleaseContext` at `0x14000de14`
- `FLTMGR!FltVetoBypassIo` at `0x14000da8b`
- `FLTMGR!FltVetoBypassIo` at `0x14000da8b`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreFsControl(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        void **a3)
{
  char v6; // r14
  bool v7; // r8
  int v8; // eax
  _DWORD *v9; // rdi
  int v10; // ebx
  unsigned int v11; // r12d
  char v12; // r15
  int v13; // r9d
  enum _FLT_PREOP_CALLBACK_STATUS v14; // ebx
  struct FsFltWil::Details::RundownRefCacheAware *v15; // rdx
  int v16; // r9d
  struct FsFltWil::Details::RundownRefCacheAware *v17; // rdx
  _QWORD *v18; // rbx
  struct FsFltWil::Details::RundownRefCacheAware *v19; // rdx
  _QWORD **v20; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v21; // rdx
  _QWORD *v22; // r14
  __int64 v23; // rcx
  int v24; // r9d
  struct FsFltWil::Details::RundownRefCacheAware *v25; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v26; // rdx
  __int64 Iopb; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v28; // rdx
  __int64 v29; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v30; // rdx
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  bool v36; // zf
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  int v40; // r15d
  int v41; // r9d
  struct FsFltWil::Details::RundownRefCacheAware *v42; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v43; // rdx
  __int64 v44; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v45; // rdx
  UnionFs::UnionFsFilter *v46; // rcx
  UnionFs::QueryUsnContext *v47; // rbx
  int v48; // r9d
  enum _FLT_PREOP_CALLBACK_STATUS v49; // edi
  struct FsFltWil::Details::RundownRefCacheAware *v50; // rdx
  FsFltWil::Details *v51; // rbx
  __int64 v52; // rcx
  void (*v53)(void); // rax
  struct FsFltWil::Details::RundownRefCacheAware *v54; // rdx
  int v55; // edi
  int v56; // r9d
  __int64 v57; // rcx
  _QWORD *v58; // rcx
  int v59; // r9d
  unsigned int v60; // r15d
  int v61; // r9d
  enum _FLT_PREOP_CALLBACK_STATUS v62; // esi
  struct FsFltWil::Details::RundownRefCacheAware *v63; // rdx
  __int64 v64; // rcx
  struct _FLT_CALLBACK_DATA *v65; // r8
  __int64 v66; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v67; // rdx
  void (*v68)(void); // rax
  unsigned int v69; // eax
  int v70; // r9d
  __int64 v71; // r8
  __int64 v72; // rcx
  unsigned int v73; // eax
  unsigned int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned int v77; // eax
  unsigned int v78; // eax
  unsigned int v79; // eax
  unsigned int v80; // eax
  int v81; // eax
  unsigned int v82; // r15d
  char *FsContext; // r15
  int v84; // eax
  int v85; // r8d
  bool v86; // al
  NTSTATUS SfoForBfo; // r15d
  ULONG_PTR v88; // rax
  _DWORD *v89; // rax
  int v90; // eax
  __int64 v91; // r15
  struct FsFltWil::Details::RundownRefCacheAware *v92; // rdx
  __int64 v93; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v94; // rdx
  int *v95; // rax
  __int64 v96; // r8
  const char *v97; // rax
  int v98; // eax
  enum _FLT_PREOP_CALLBACK_STATUS v99; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v100; // rdx
  __int64 v101; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v102; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v103; // rdx
  struct UnionFs::StackEventTracer *v105; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v106; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v107; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v108; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v109; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v110; // [rsp+20h] [rbp-E0h]
  int v111; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v112; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v113; // [rsp+20h] [rbp-E0h]
  struct UnionFs::UfsStreamHandleCtx *v114; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v115; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v116; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v117; // [rsp+28h] [rbp-D8h]
  bool v118; // [rsp+40h] [rbp-C0h] BYREF
  PFLT_CONTEXT v119; // [rsp+48h] [rbp-B8h] BYREF
  PVOID v120; // [rsp+50h] [rbp-B0h] BYREF
  enum _FLT_PREOP_CALLBACK_STATUS v121; // [rsp+58h] [rbp-A8h] BYREF
  char v122; // [rsp+5Ch] [rbp-A4h]
  __int16 v123; // [rsp+5Dh] [rbp-A3h]
  char v124; // [rsp+5Fh] [rbp-A1h]
  __int128 v125; // [rsp+60h] [rbp-A0h]
  __int128 v126; // [rsp+70h] [rbp-90h]
  char *v127; // [rsp+80h] [rbp-80h] BYREF
  PVOID Entry[2]; // [rsp+88h] [rbp-78h] BYREF
  PFLT_CONTEXT v129; // [rsp+98h] [rbp-68h] BYREF
  utl::_RefCountBase *v130; // [rsp+A0h] [rbp-60h]
  __int64 v131; // [rsp+A8h] [rbp-58h] BYREF
  char v132; // [rsp+B0h] [rbp-50h]
  char v133[112]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v134; // [rsp+128h] [rbp+28h]
  _QWORD v135[17]; // [rsp+130h] [rbp+30h] BYREF
  PFLT_CONTEXT Context[3]; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v137[17]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v138; // [rsp+258h] [rbp+158h] BYREF
  char v139; // [rsp+260h] [rbp+160h]
  char v140[112]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v141; // [rsp+2D8h] [rbp+1D8h]
  unsigned __int64 v142[94]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v127 = (char *)a3;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v142, 0x5E000109CEuLL, a1);
  v6 = 0;
  *a3 = 0;
  memset(Context, 0, sizeof(Context));
  memset(v137, 0, sizeof(v137));
  v8 = UnionFs::UfsStreamHandleCtx::FltGet(
         a2->Instance,
         a2->FileObject,
         v7,
         (struct UnionFs::HandleCtxAndUnionWithRundown *)Context,
         (struct UnionFs::StackEventTracer *)v142);
  v9 = Context[0];
  v129 = Context[1];
  v10 = v8;
  v130 = (utl::_RefCountBase *)Context[2];
  v131 = v137[0];
  v132 = v137[1];
  memset(Context, 0, sizeof(Context));
  v119 = v9;
  wistd::function<void (bool)>::function<void (bool)>(&v133, &v137[2]);
  memset(v137, 0, sizeof(v137));
  v11 = 1;
  if ( v9 && (*v9 & 1) != 0 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( !v9 )
      goto LABEL_7;
  }
  if ( (*v9 & 0x20) != 0 )
    v6 = 1;
LABEL_7:
  if ( v10 == -1058209784 )
  {
    if ( v12 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)0xC0ED0008LL,
        (int)v142,
        (struct UnionFs::StackEventTracer *)0x701000109E9LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
        "PUSH: Got SFO but union is not active.",
        (const char *)v114);
      v14 = UnionFs::Utils::PreOpFinishProcessing(
              (UnionFs::Utils *)4,
              (enum _FLT_PREOP_CALLBACK_STATUS)a1,
              (struct _FLT_CALLBACK_DATA *)0xC0ED0008LL,
              v13,
              (unsigned __int64)v106);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v15);
      if ( !v134 )
        goto LABEL_11;
      goto LABEL_10;
    }
LABEL_16:
    memset(v135, 0, sizeof(v135));
    v18 = 0;
    v120 = 0;
    if ( v12 && !v6 )
    {
      UnionFs::UfsStreamCtx::SyncWithCOW(*((UnionFs::UfsStreamCtx **)a2->FileObject->FsContext + 17));
      wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(
        (FsFltWil::Details *)v135,
        &v138);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v138, v19);
      if ( v141 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 24LL))(v141);
      v138 = v135[0];
      v139 = v135[1];
      wistd::function<void (bool)>::function<void (bool)>(&v140, &v135[2]);
      memset(v135, 0, sizeof(v135));
      v20 = (_QWORD **)utl::make_unique<UnionFs::IoSyncContext,UnionFs::IoSyncContext,0>(Entry, &v138);
      v18 = *v20;
      *v20 = 0;
      v22 = Entry[0];
      v120 = v18;
      if ( Entry[0] )
      {
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)Entry[0], v21);
        v23 = v22[16];
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v22);
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v138, v21);
      if ( v141 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 24LL))(v141);
      if ( !v18 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)v142,
          (struct UnionFs::StackEventTracer *)0x70200010A02LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
          "ORIGIN: Allocating IoSyncContext",
          (const char *)v114);
        v14 = UnionFs::Utils::PreOpFinishProcessing(
                (UnionFs::Utils *)4,
                (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                (struct _FLT_CALLBACK_DATA *)0xC000009ALL,
                v24,
                (unsigned __int64)v108);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v25);
        if ( v135[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v26);
        if ( v134 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
        goto LABEL_11;
      }
    }
    Iopb = (__int64)a1->Iopb;
    v121 = FLT_PREOP_SUCCESS_NO_CALLBACK;
    v122 = 0;
    v123 = 0;
    v36 = (*(_BYTE *)(Iopb + 5) & 0xFB) == 0;
    v124 = 0;
    v125 = 0;
    v126 = 0;
    if ( !v36 )
    {
      UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
      if ( v18 )
      {
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v18, v28);
        v29 = v18[16];
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v18);
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v28);
      if ( v135[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v30);
      if ( v134 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
      if ( v130 )
        utl::_RefCountBase::_DecStrong(v130);
      if ( v9 )
        FltReleaseContext(v9);
LABEL_74:
      v14 = FLT_PREOP_SUCCESS_NO_CALLBACK;
      goto LABEL_216;
    }
    v31 = *(_DWORD *)(Iopb + 40);
    if ( v31 <= 0x90270 )
    {
      if ( v31 != 590448 )
      {
        Iopb = 589844;
        if ( v31 <= 0x90014 )
        {
          if ( v31 != 589844 )
          {
            v32 = v31 - 589824;
            if ( v32 )
            {
              v33 = v32 - 4;
              if ( v33 )
              {
                v34 = v33 - 4;
                if ( v34 )
                {
                  v35 = v34 - 4;
                  if ( v35 )
                  {
                    v36 = v35 == 4;
                    goto LABEL_57;
                  }
                }
              }
            }
          }
LABEL_101:
          if ( !(unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() || !v12 )
            goto LABEL_58;
          v60 = UnionFs::UnionFsFilter::HandleOplockRequest(
                  (UnionFs::UnionFsFilter *)Iopb,
                  a1,
                  (const struct UnionFs::UfsStreamHandleCtx *)v9,
                  (struct UnionFs::StackEventTracer *)v142);
          if ( (v60 & 0x80000000) == 0 )
          {
            if ( v60 == 259 )
            {
              v65 = 0;
              v66 = 2;
            }
            else
            {
              v65 = (struct _FLT_CALLBACK_DATA *)v60;
              v66 = 4;
            }
            v14 = UnionFs::Utils::PreOpFinishProcessing(
                    (UnionFs::Utils *)v66,
                    (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                    v65,
                    v59,
                    (unsigned __int64)v105);
            UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
            utl::unique_ptr<UnionFs::IoSyncContext,utl::default_delete<UnionFs::IoSyncContext>>::~unique_ptr<UnionFs::IoSyncContext,utl::default_delete<UnionFs::IoSyncContext>>(&v120);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v67);
            if ( !v135[16] )
              goto LABEL_213;
            v68 = *(void (**)(void))(*(_QWORD *)v135[16] + 24LL);
LABEL_212:
            v68();
LABEL_213:
            UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)&v129);
            goto LABEL_214;
          }
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)v60,
            (int)v142,
            (struct UnionFs::StackEventTracer *)0x4F300010BA7LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
            "PUSH: Oplock request on SFO",
            (const char *)v114);
          v62 = UnionFs::Utils::PreOpFinishProcessing(
                  (UnionFs::Utils *)4,
                  (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                  (struct _FLT_CALLBACK_DATA *)v60,
                  v61,
                  (unsigned __int64)v113);
          UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
          if ( v18 )
          {
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v18, v63);
            v64 = v18[16];
            if ( v64 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 24LL))(v64);
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v18);
          }
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v63);
          if ( v135[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)&v129);
LABEL_197:
          if ( v9 )
            FltReleaseContext(v9);
          v14 = v62;
          goto LABEL_216;
        }
        v37 = v31 - 589904;
        if ( !v37 )
          goto LABEL_101;
        v38 = v37 - 12;
        if ( !v38 )
          goto LABEL_101;
        v39 = v38 - 143;
        if ( v39 )
        {
          v36 = v39 == 341;
LABEL_57:
          if ( !v36 )
            goto LABEL_58;
          goto LABEL_101;
        }
        if ( !v9 )
        {
          UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
          if ( v18 )
          {
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v18, v43);
            v44 = v18[16];
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44);
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v18);
          }
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v43);
          if ( v135[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v45);
          if ( v134 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
          if ( v130 )
            utl::_RefCountBase::_DecStrong(v130);
          goto LABEL_74;
        }
        utl::make_unique<UnionFs::QueryUsnContext,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&void FltReleaseContext(void *)>>,UnionFs::UfsUnionCtxWithRundown,utl::unique_ptr<UnionFs::IoSyncContext,utl::default_delete<UnionFs::IoSyncContext>>,0>(
          Entry,
          &v119,
          &v129,
          &v120);
        v47 = (UnionFs::QueryUsnContext *)Entry[0];
        if ( Entry[0] )
        {
          v55 = UnionFs::UnionFsFilter::CheckAndSwitchTarget(
                  v46,
                  a1,
                  a2,
                  *(const struct UnionFs::UfsStreamHandleCtx **)Entry[0],
                  (struct UnionFs::StackEventTracer *)v142,
                  (struct UnionFs::CheckAndSwitchResults *)&v121);
          if ( v55 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v55,
              (int)v142,
              (struct UnionFs::StackEventTracer *)0x6FF00010B7ELL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
              "PUSH: Switching target",
              (const char *)v115);
            v49 = UnionFs::Utils::PreOpFinishProcessing(
                    (UnionFs::Utils *)4,
                    (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                    (struct _FLT_CALLBACK_DATA *)(unsigned int)v55,
                    v56,
                    (unsigned __int64)v112);
            if ( v47 )
            {
              UnionFs::QueryUsnContext::~QueryUsnContext(v47);
              ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 704), v47);
            }
            UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
            v51 = (FsFltWil::Details *)v120;
            if ( !v120 )
              goto LABEL_82;
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v120, v50);
            v57 = *((_QWORD *)v51 + 16);
            if ( !v57 )
              goto LABEL_81;
            v53 = *(void (**)(void))(*(_QWORD *)v57 + 24LL);
            goto LABEL_80;
          }
          v36 = v122 == 0;
          v58 = v127;
          *(_QWORD *)v127 = v47;
          v51 = (FsFltWil::Details *)v120;
          if ( !v36 && v120 )
          {
            v51 = 0;
            *v58 = v120;
          }
          v49 = UnionFs::Utils::PreOpFinishProcessing(
                  0,
                  (enum _FLT_PREOP_CALLBACK_STATUS)&v121,
                  (const struct UnionFs::CheckAndSwitchResults *)a1,
                  0,
                  v111,
                  (unsigned __int64)v115);
          UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
        }
        else
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)0xC000009ALL,
            (int)v142,
            (struct UnionFs::StackEventTracer *)0x76000010B72LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
            "PUSH: Allocating USN query context",
            (const char *)v114);
          v49 = UnionFs::Utils::PreOpFinishProcessing(
                  (UnionFs::Utils *)4,
                  (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                  (struct _FLT_CALLBACK_DATA *)0xC000009ALL,
                  v48,
                  (unsigned __int64)v110);
          UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
          v51 = (FsFltWil::Details *)v120;
        }
        if ( !v51 )
        {
LABEL_82:
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v50);
          if ( v135[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v54);
          if ( v134 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
          if ( v130 )
            utl::_RefCountBase::_DecStrong(v130);
          if ( v119 )
            FltReleaseContext(v119);
          v14 = v49;
          goto LABEL_216;
        }
        FsFltWil::Details::ReleaseRundownProtectionCacheAware(v51, v50);
        v52 = *((_QWORD *)v51 + 16);
        if ( !v52 )
        {
LABEL_81:
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v51);
          goto LABEL_82;
        }
        v53 = *(void (**)(void))(*(_QWORD *)v52 + 24LL);
LABEL_80:
        v53();
        goto LABEL_81;
      }
      v118 = 0;
      v69 = UnionFs::UnionFsFilter::SetPurgeFailureMode(
              (UnionFs::UnionFsFilter *)Iopb,
              a1,
              a2,
              &v118,
              (struct UnionFs::StackEventTracer *)v142,
              (const struct UnionFs::UfsStreamHandleCtx *)v9);
      if ( !v118 )
      {
        v71 = v69;
        v72 = 4;
LABEL_186:
        v99 = UnionFs::Utils::PreOpFinishProcessing(
                (UnionFs::Utils *)v72,
                (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                (struct _FLT_CALLBACK_DATA *)v71,
                v70,
                (unsigned __int64)v105);
LABEL_187:
        v62 = v99;
        UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
        if ( v18 )
        {
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v18, v100);
          v101 = v18[16];
          if ( v101 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 24LL))(v101);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v18);
        }
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v100);
        if ( v135[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v102);
        if ( v134 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
        if ( v130 )
          utl::_RefCountBase::_DecStrong(v130);
        goto LABEL_197;
      }
LABEL_58:
      if ( v9 )
      {
        v40 = UnionFs::UnionFsFilter::CheckAndSwitchTarget(
                (UnionFs::UnionFsFilter *)Iopb,
                a1,
                a2,
                (const struct UnionFs::UfsStreamHandleCtx *)v9,
                (struct UnionFs::StackEventTracer *)v142,
                (struct UnionFs::CheckAndSwitchResults *)&v121);
        if ( v40 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v40,
            (int)v142,
            (struct UnionFs::StackEventTracer *)0x70000010BC0LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
            "PUSH: Switching target",
            (const char *)v114);
          v14 = UnionFs::Utils::PreOpFinishProcessing(
                  (UnionFs::Utils *)4,
                  (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                  (struct _FLT_CALLBACK_DATA *)(unsigned int)v40,
                  v41,
                  (unsigned __int64)v109);
          UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
          utl::unique_ptr<UnionFs::IoSyncContext,utl::default_delete<UnionFs::IoSyncContext>>::~unique_ptr<UnionFs::IoSyncContext,utl::default_delete<UnionFs::IoSyncContext>>(&v120);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v42);
          if ( v135[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)&v129);
          goto LABEL_215;
        }
      }
      if ( v122 && v18 )
      {
        v11 = 0;
        v120 = 0;
        *(_QWORD *)v127 = v18;
      }
      v14 = UnionFs::Utils::PreOpFinishProcessing(
              (UnionFs::Utils *)v11,
              (enum _FLT_PREOP_CALLBACK_STATUS)&v121,
              (const struct UnionFs::CheckAndSwitchResults *)a1,
              0,
              (int)v105,
              (unsigned __int64)v114);
      UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
      utl::unique_ptr<UnionFs::IoSyncContext,utl::default_delete<UnionFs::IoSyncContext>>::~unique_ptr<UnionFs::IoSyncContext,utl::default_delete<UnionFs::IoSyncContext>>(&v120);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v103);
      if ( !v135[16] )
        goto LABEL_213;
      v68 = *(void (**)(void))(*(_QWORD *)v135[16] + 24LL);
      goto LABEL_212;
    }
    v73 = v31 - 590736;
    if ( !v73 )
    {
      if ( !v12 || *(_DWORD *)(Iopb + 24) < 4u )
        goto LABEL_58;
      **(_DWORD **)(Iopb + 48) = 1;
      a1->IoStatus.Status = 0;
      a1->IoStatus.Information = 4;
      goto LABEL_164;
    }
    v74 = v73 - 4;
    if ( !v74 )
    {
      v95 = *(int **)(Iopb + 48);
      if ( v95 )
      {
        if ( *(_DWORD *)(Iopb + 32) == 4 )
        {
          v98 = *v95;
          if ( (v98 & 0xFFFFFC00) == 0 )
          {
            if ( (v98 & 0x200) == 0 )
              goto LABEL_58;
            if ( !v12 )
            {
              v99 = UnionFs::UnionFsFilter::FsctlSetLayerRoot(
                      (UnionFs::UnionFsFilter *)Iopb,
                      a1,
                      (struct UnionFs::StackEventTracer *)v142);
              goto LABEL_187;
            }
            UnionFs::ProcessTraceStatusOrigin(
              (UnionFs *)0xC00004D0LL,
              (int)v142,
              (struct UnionFs::StackEventTracer *)0x18B00010A52LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
              "ORIGIN: FSCTL_SET_LAYER_ROOT on shadow file",
              (const char *)v114);
            v71 = 3221226704LL;
LABEL_185:
            v72 = 4;
            goto LABEL_186;
          }
          v96 = 0x6600011058LL;
          v97 = "ORIGIN: Invalid flags set";
        }
        else
        {
          v96 = 0x650001104FLL;
          v97 = "ORIGIN: Input buffer wrong size";
        }
      }
      else
      {
        v96 = 0x5F00011047LL;
        v97 = "ORIGIN: No input";
      }
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        (int)v142,
        (struct UnionFs::StackEventTracer *)v96,
        (unsigned __int64)"UnionFs::UnionFsFilter::ValidateContainerRootInfoInputBuffer",
        v97,
        (const char *)v114);
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)0xC000000DLL,
        (int)v142,
        (struct UnionFs::StackEventTracer *)0x6000010A42LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
        "PUSH: Validate input",
        (const char *)v117);
      v71 = 3221225485LL;
      goto LABEL_185;
    }
    v75 = v74 - 180;
    if ( v75 )
    {
      v76 = v75 - 6968;
      if ( v76 )
      {
        v77 = v76 - 4;
        if ( v77 )
        {
          v78 = v77 - 8928;
          if ( v78 )
          {
            v79 = v78 - 16388;
            if ( v79 )
            {
              v80 = v79 - 220;
              if ( v80 && v80 != 164 )
                goto LABEL_58;
              v118 = 0;
              v81 = UnionFs::UnionFsFilter::HandleDuplicateExtents(
                      (UnionFs::UnionFsFilter *)Iopb,
                      a1,
                      a2,
                      &v118,
                      (struct UnionFs::StackEventTracer *)v142,
                      (const struct UnionFs::UfsStreamHandleCtx *)v9);
              v82 = v81;
              if ( !v118 )
              {
                if ( v81 >= 0 )
                  goto LABEL_58;
                UnionFs::ProcessTraceStatusPushLocation(
                  (UnionFs *)(unsigned int)v81,
                  (int)v142,
                  (struct UnionFs::StackEventTracer *)0x6A600010B4BLL,
                  (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
                  "PUSH: Failed handling duplicate extents.",
                  (const char *)v114);
              }
            }
            else
            {
              if ( !v12 )
                goto LABEL_58;
              v82 = -1073700188;
              UnionFs::ProcessTraceStatusOrigin(
                (UnionFs *)0xC000A2A4LL,
                (int)v142,
                (struct UnionFs::StackEventTracer *)0x6700010A8DLL,
                (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
                "ORIGIN: FSCTL_SET_LAYER_ROOT on shadow file",
                (const char *)v114);
            }
            v71 = v82;
          }
          else
          {
            if ( !(unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() || !v12 )
              goto LABEL_58;
            LODWORD(v105) = 0;
            FsContext = (char *)a2->FileObject->FsContext;
            v84 = UnionFs::Utils::CheckOplock(a1, a2, FsContext + 88, v142);
            LODWORD(v119) = v84;
            if ( v84 == 259 )
            {
              if ( (unsigned int)dword_14009E178 > 4
                && (qword_14009E188 & 0x282000) != 0
                && (qword_14009E190 & 0x282000) == qword_14009E190 )
              {
                LODWORD(v119) = 2667;
                Entry[0] = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
                v127 = "UnionFs::UnionFsFilter::PreFsControl";
                v120 = "Oplock break";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  qword_14009E190,
                  (unsigned int)byte_1400958F1,
                  v85,
                  (unsigned int)"UnionFs::UnionFsFilter::PreFsControl",
                  (__int64)&v120,
                  (__int64)&v127,
                  (__int64)Entry,
                  (__int64)&v119);
              }
              v71 = 0;
              v72 = 2;
              goto LABEL_186;
            }
            if ( v84 >= 0 )
            {
              if ( !FsContext[5] )
              {
                v86 = !*(_BYTE *)(*((_QWORD *)FsContext + 18) + 96LL)
                   && FsRtlOplockIsFastIoPossible((POPLOCK)FsContext + 11);
                FsContext[5] = v86;
              }
              goto LABEL_58;
            }
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v84,
              (int)v142,
              (struct UnionFs::StackEventTracer *)0x70300010A72LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
              "PUSH: Checking oplock",
              (const char *)v114);
            v71 = (unsigned int)v119;
          }
          goto LABEL_185;
        }
        LODWORD(v119) = 0;
        SfoForBfo = UnionFs::UnionFsFilter::ProcessGetSfoForBfo(
                      (UnionFs::UnionFsFilter *)Iopb,
                      a1,
                      a2,
                      (unsigned int *)&v119,
                      (struct UnionFs::StackEventTracer *)v142,
                      (const struct UnionFs::UfsStreamHandleCtx *)v9);
        if ( SfoForBfo < 0 )
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)SfoForBfo,
            (int)v142,
            (struct UnionFs::StackEventTracer *)0x68C00010B35LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
            "PUSH: Failed to get SFO for BFO.",
            (const char *)v116);
        a1->IoStatus.Status = SfoForBfo;
        if ( SfoForBfo != 260 )
        {
          v88 = (unsigned int)v119;
LABEL_163:
          a1->IoStatus.Information = v88;
          goto LABEL_164;
        }
        goto LABEL_164;
      }
      a1->IoStatus.Status = -1073741822;
    }
    else
    {
      if ( !v12 )
        goto LABEL_58;
      v89 = *(_DWORD **)(Iopb + 48);
      if ( v89 && *(_DWORD *)(Iopb + 32) >= 0x18u )
      {
        if ( ((*v89 - 1) & 0xFFFFFFFD) != 0 )
          goto LABEL_58;
        *(_OWORD *)Entry = 0;
        RtlInitUnicodeString((PUNICODE_STRING)Entry, L"Bypass not supported on a file from a layer");
        v90 = FltVetoBypassIo(a1, a2, 3221226704LL, Entry);
        v91 = v90;
        if ( v90 < 0 )
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)v90,
            (int)v142,
            (struct UnionFs::StackEventTracer *)0xA300010ABALL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
            "API: FltVetoBypassIo",
            (const char *)v114);
        a1->IoStatus.Status = v91;
        if ( (_DWORD)v91 != 260 )
        {
          v88 = ((v91 >> 63) & 0xFFFFFFFFFFFFFEA0uLL) + 352;
          goto LABEL_163;
        }
LABEL_164:
        UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults((UnionFs::CheckAndSwitchResults *)&v121);
        if ( v18 )
        {
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v18, v92);
          v93 = v18[16];
          if ( v93 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 24LL))(v93);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v18);
        }
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v135, v92);
        if ( v135[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v135[16] + 24LL))(v135[16]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v94);
        if ( v134 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
        if ( v130 )
          utl::_RefCountBase::_DecStrong(v130);
        if ( v9 )
          FltReleaseContext(v9);
        v14 = FLT_PREOP_COMPLETE;
        goto LABEL_216;
      }
      a1->IoStatus.Status = -1073741306;
    }
    a1->IoStatus.Information = 0;
    goto LABEL_164;
  }
  if ( v10 >= 0 )
    goto LABEL_16;
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v10,
    (int)v142,
    (struct UnionFs::StackEventTracer *)0x45F000109F2LL,
    (unsigned __int64)"UnionFs::UnionFsFilter::PreFsControl",
    "PUSH: Getting handle ctx",
    (const char *)v114);
  v14 = UnionFs::Utils::PreOpFinishProcessing(
          (UnionFs::Utils *)4,
          (enum _FLT_PREOP_CALLBACK_STATUS)a1,
          (struct _FLT_CALLBACK_DATA *)(unsigned int)v10,
          v16,
          (unsigned __int64)v107);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v131, v17);
  if ( v134 )
LABEL_10:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 24LL))(v134);
LABEL_11:
  if ( v130 )
    utl::_RefCountBase::_DecStrong(v130);
LABEL_214:
  if ( v9 )
LABEL_215:
    FltReleaseContext(v9);
LABEL_216:
  UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v142);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000cce0  mov     [rsp-8+arg_18], rbx
0x14000cce5  push    rbp
0x14000cce6  push    rsi
0x14000cce7  push    rdi
0x14000cce8  push    r12
0x14000ccea  push    r13
0x14000ccec  push    r14
0x14000ccee  push    r15
0x14000ccf0  lea     rbp, [rsp-4E0h]
0x14000ccf8  sub     rsp, 5E0h
0x14000ccff  mov     rax, cs:__security_cookie
0x14000cd06  xor     rax, rsp
0x14000cd09  mov     [rbp+510h+var_40], rax
0x14000cd10  mov     rbx, r8
0x14000cd13  mov     r13, rdx
0x14000cd16  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14000cd19  mov     [rbp+510h+var_590], rbx
0x14000cd1d  mov     rsi, rcx
0x14000cd20  mov     rdx, 5E000109CEh; unsigned __int64
0x14000cd2a  lea     rcx, [rbp+510h+var_330]; this
0x14000cd31  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14000cd36  xor     r14d, r14d
0x14000cd39  lea     rcx, [rbp+510h+var_440]; void *
0x14000cd40  mov     [rbx], r14
0x14000cd43  xorps   xmm0, xmm0
0x14000cd46  xorps   xmm1, xmm1
0x14000cd49  mov     [rbp+510h+var_438], r14b
0x14000cd50  mov     r15d, 88h
0x14000cd56  mov     [rbp+510h+var_3C0], r14
0x14000cd5d  mov     r8d, r15d; Size
0x14000cd60  xor     edx, edx; Val
0x14000cd62  movdqu  xmmword ptr [rbp+510h+Context], xmm0
0x14000cd6a  movdqu  xmmword ptr [rbp+0C8h], xmm1
0x14000cd72  call    memset
0x14000cd77  mov     rdx, [r13+20h]; FileObject
0x14000cd7b  lea     rax, [rbp+510h+var_330]
0x14000cd82  mov     rcx, [r13+18h]; Instance
0x14000cd86  lea     r9, [rbp+510h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14000cd8d  mov     [rsp+610h+var_5F0], rax; int
0x14000cd92  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14000cd97  mov     rcx, [rbp+510h+Context+8]
0x14000cd9e  lea     rdx, [rbp+510h+var_430]
0x14000cda5  mov     rdi, [rbp+510h+Context]
0x14000cdac  xorps   xmm0, xmm0
0x14000cdaf  mov     [rbp+510h+var_578], rcx
0x14000cdb3  mov     ebx, eax
0x14000cdb5  mov     rcx, [rbp+510h+var_448]
0x14000cdbc  mov     [rbp+510h+var_570], rcx
0x14000cdc0  mov     rcx, [rbp+510h+var_440]
0x14000cdc7  mov     [rbp+510h+var_568], rcx
0x14000cdcb  mov     cl, [rbp+510h+var_438]
0x14000cdd1  mov     [rbp+510h+var_560], cl
0x14000cdd4  lea     rcx, [rbp+510h+var_558]
0x14000cdd8  mov     [rbp+510h+Context], r14
0x14000cddf  mov     [rsp+610h+var_5C8], rdi
0x14000cde4  movdqu  xmmword ptr [rbp+510h+Context+8], xmm0
0x14000cdec  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14000cdf1  mov     r8d, r15d; Size
0x14000cdf4  lea     rcx, [rbp+510h+var_440]; void *
0x14000cdfb  xor     edx, edx; Val
0x14000cdfd  call    memset
0x14000ce02  lea     r12d, [r14+1]
0x14000ce06  test    rdi, rdi
0x14000ce09  jz      short loc_14000CE17
0x14000ce0b  mov     eax, [rdi]
0x14000ce0d  test    r12b, al
0x14000ce10  jz      short loc_14000CE17
0x14000ce12  mov     r15b, r12b
0x14000ce15  jmp     short loc_14000CE1F
0x14000ce17  mov     r15b, r14b
0x14000ce1a  test    rdi, rdi
0x14000ce1d  jz      short loc_14000CE28
0x14000ce1f  mov     eax, [rdi]
0x14000ce21  test    al, 20h
0x14000ce23  jz      short loc_14000CE28
0x14000ce25  mov     r14b, r12b
0x14000ce28  mov     ecx, 0C0ED0008h; this
0x14000ce2d  cmp     ebx, ecx
0x14000ce2f  jnz     short loc_14000CEB0
0x14000ce31  test    r15b, r15b
0x14000ce34  jz      loc_14000CF0C
0x14000ce3a  lea     rax, aPushGotSfoButU; "PUSH: Got SFO but union is not active."
0x14000ce41  mov     r8, 701000109E9h; struct UnionFs::StackEventTracer *
0x14000ce4b  lea     r9, aUnionfsUnionfs_8; "UnionFs::UnionFsFilter::PreFsControl"
0x14000ce52  mov     [rsp+610h+var_5F0], rax; unsigned __int64
0x14000ce57  lea     rdx, [rbp+510h+var_330]; int
0x14000ce5e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000ce63  mov     r8d, 0C0ED0008h; struct _FLT_CALLBACK_DATA *
0x14000ce69  mov     rdx, rsi; enum _FLT_PREOP_CALLBACK_STATUS
0x14000ce6c  mov     ecx, 4; this
0x14000ce71  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x14000ce76  lea     rcx, [rbp+510h+var_568]; this
0x14000ce7a  mov     ebx, eax
0x14000ce7c  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000ce81  mov     rdx, [rbp+510h+var_4E8]
0x14000ce85  test    rdx, rdx
0x14000ce88  jz      short loc_14000CE99
0x14000ce8a  mov     rcx, [rdx]
0x14000ce8d  mov     rax, [rcx+18h]
0x14000ce91  mov     rcx, rdx
0x14000ce94  call    _guard_dispatch_icall
0x14000ce99  mov     rcx, [rbp+510h+var_570]; this
0x14000ce9d  test    rcx, rcx
0x14000cea0  jz      loc_14000DE0C
0x14000cea6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14000ceab  jmp     loc_14000DE0C
0x14000ceb0  test    ebx, ebx
0x14000ceb2  jns     short loc_14000CF0C
0x14000ceb4  lea     rax, aPushGettingHan; "PUSH: Getting handle ctx"
0x14000cebb  mov     r8, 45F000109F2h; struct UnionFs::StackEventTracer *
0x14000cec5  lea     r9, aUnionfsUnionfs_8; "UnionFs::UnionFsFilter::PreFsControl"
0x14000cecc  mov     [rsp+610h+var_5F0], rax; unsigned __int64
0x14000ced1  lea     rdx, [rbp+510h+var_330]; int
0x14000ced8  mov     ecx, ebx; this
0x14000ceda  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000cedf  mov     r8d, ebx; struct _FLT_CALLBACK_DATA *
0x14000cee2  mov     rdx, rsi; enum _FLT_PREOP_CALLBACK_STATUS
0x14000cee5  mov     ecx, 4; this
0x14000ceea  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x14000ceef  lea     rcx, [rbp+510h+var_568]; this
0x14000cef3  mov     ebx, eax
0x14000cef5  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000cefa  mov     rcx, [rbp+510h+var_4E8]
0x14000cefe  test    rcx, rcx
0x14000cf01  jz      short loc_14000CE99
0x14000cf03  mov     rdx, [rcx]
0x14000cf06  mov     rax, [rdx+18h]
0x14000cf0a  jmp     short loc_14000CE94
0x14000cf0c  xor     edx, edx; Val
0x14000cf0e  lea     rcx, [rbp+510h+var_4E0]; void *
0x14000cf12  mov     r8d, 88h; Size
0x14000cf18  call    memset
0x14000cf1d  xor     ebx, ebx
0x14000cf1f  mov     [rsp+610h+var_5C0], rbx
0x14000cf24  test    r15b, r15b
0x14000cf27  jz      loc_14000D0D1
0x14000cf2d  test    r14b, r14b
0x14000cf30  jnz     loc_14000D0D1
0x14000cf36  mov     rax, [r13+20h]
0x14000cf3a  lea     rdx, [rbp+510h+var_3B8]
0x14000cf41  mov     rcx, [rax+18h]
0x14000cf45  mov     rcx, [rcx+88h]; this
0x14000cf4c  call    ?SyncWithCOW@UfsStreamCtx@UnionFs@@QEAA@XZ; UnionFs::UfsStreamCtx::SyncWithCOW(void)
0x14000cf51  lea     rdx, [rbp+510h+var_3B8]; void *
0x14000cf58  lea     rcx, [rbp+510h+var_4E0]; this
0x14000cf5c  call    ??4?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0> &&)
0x14000cf61  lea     rcx, [rbp+510h+var_3B8]; this
0x14000cf68  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000cf6d  mov     rcx, [rbp+510h+var_338]
0x14000cf74  test    rcx, rcx
0x14000cf77  jz      short loc_14000CF85
0x14000cf79  mov     rax, [rcx]
0x14000cf7c  mov     rax, [rax+18h]
0x14000cf80  call    _guard_dispatch_icall
0x14000cf85  mov     rax, [rbp+510h+var_4E0]
0x14000cf89  lea     rdx, [rbp+510h+var_4D0]
0x14000cf8d  mov     [rbp+510h+var_3B8], rax
0x14000cf94  lea     rcx, [rbp+510h+var_3A8]
0x14000cf9b  mov     al, [rbp+510h+var_4D8]
0x14000cf9e  mov     [rbp+510h+var_3B0], al
0x14000cfa4  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14000cfa9  xor     edx, edx; Val
0x14000cfab  lea     rcx, [rbp+510h+var_4E0]; void *
0x14000cfaf  mov     r8d, 88h; Size
0x14000cfb5  call    memset
0x14000cfba  lea     rdx, [rbp+510h+var_3B8]
0x14000cfc1  lea     rcx, [rbp+510h+Entry]
0x14000cfc5  call    ??$make_unique@UIoSyncContext@UnionFs@@U12@$0A@@utl@@YA?AV?$unique_ptr@UIoSyncContext@UnionFs@@U?$default_delete@UIoSyncContext@UnionFs@@@utl@@@0@$$QEAUIoSyncContext@UnionFs@@@Z; utl::make_unique<UnionFs::IoSyncContext,UnionFs::IoSyncContext,0>(UnionFs::IoSyncContext &&)
0x14000cfca  mov     rbx, [rax]
0x14000cfcd  mov     qword ptr [rax], 0
0x14000cfd4  mov     r14, [rbp+510h+Entry]
0x14000cfd8  mov     [rsp+610h+var_5C0], rbx
0x14000cfdd  test    r14, r14
0x14000cfe0  jz      short loc_14000D01F
0x14000cfe2  mov     rcx, r14; this
0x14000cfe5  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000cfea  mov     rcx, [r14+80h]
0x14000cff1  test    rcx, rcx
0x14000cff4  jz      short loc_14000D002
0x14000cff6  mov     rax, [rcx]
0x14000cff9  mov     rax, [rax+18h]
0x14000cffd  call    _guard_dispatch_icall
0x14000d002  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000d009  mov     rdx, r14; Entry
0x14000d00c  add     rcx, 380h; Lookaside
0x14000d013  call    cs:__imp_ExFreeToLookasideListEx
0x14000d01a  nop     dword ptr [rax+rax+00h]
0x14000d01f  lea     rcx, [rbp+510h+var_3B8]; this
0x14000d026  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000d02b  mov     rcx, [rbp+510h+var_338]
0x14000d032  test    rcx, rcx
0x14000d035  jz      short loc_14000D043
0x14000d037  mov     rax, [rcx]
0x14000d03a  mov     rax, [rax+18h]
0x14000d03e  call    _guard_dispatch_icall
0x14000d043  test    rbx, rbx
0x14000d046  jnz     loc_14000D0D1
0x14000d04c  lea     rax, aOriginAllocati_19; "ORIGIN: Allocating IoSyncContext"
0x14000d053  mov     ebx, 0C000009Ah
0x14000d058  mov     ecx, ebx; this
0x14000d05a  mov     [rsp+610h+var_5F0], rax; unsigned __int64
0x14000d05f  lea     r9, aUnionfsUnionfs_8; "UnionFs::UnionFsFilter::PreFsControl"
0x14000d066  mov     r8, 70200010A02h; struct UnionFs::StackEventTracer *
0x14000d070  lea     rdx, [rbp+510h+var_330]; int
0x14000d077  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000d07c  mov     r8d, ebx; struct _FLT_CALLBACK_DATA *
0x14000d07f  mov     rdx, rsi; enum _FLT_PREOP_CALLBACK_STATUS
0x14000d082  mov     ecx, 4; this
0x14000d087  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x14000d08c  lea     rcx, [rbp+510h+var_4E0]; this
0x14000d090  mov     ebx, eax
0x14000d092  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000d097  mov     rcx, [rbp+510h+var_460]
0x14000d09e  test    rcx, rcx
0x14000d0a1  jz      short loc_14000D0AF
0x14000d0a3  mov     rdx, [rcx]
0x14000d0a6  mov     rax, [rdx+18h]
0x14000d0aa  call    _guard_dispatch_icall
0x14000d0af  lea     rcx, [rbp+510h+var_568]; this
0x14000d0b3  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000d0b8  mov     rcx, [rbp+510h+var_4E8]
0x14000d0bc  test    rcx, rcx
0x14000d0bf  jz      loc_14000CE99
0x14000d0c5  mov     rax, [rcx]
0x14000d0c8  mov     rax, [rax+18h]
0x14000d0cc  jmp     loc_14000CE94
0x14000d0d1  mov     rcx, [rsi+10h]; this
0x14000d0d5  xor     eax, eax
0x14000d0d7  xorps   xmm0, xmm0
0x14000d0da  mov     [rsp+610h+var_5B8], r12d
0x14000d0df  xorps   xmm1, xmm1
0x14000d0e2  mov     [rsp+610h+var_5B4], 0
0x14000d0e7  mov     [rsp+610h+var_5B3], ax
0x14000d0ec  test    byte ptr [rcx+5], 0FBh
0x14000d0f0  mov     [rsp+610h+var_5B1], al
0x14000d0f4  movdqu  [rsp+610h+var_5B0], xmm0
0x14000d0fa  movdqu  [rsp+610h+var_5A0], xmm1
0x14000d100  jz      loc_14000D1BC
0x14000d106  lea     rcx, [rsp+610h+var_5B8]; this
0x14000d10b  call    ??1CheckAndSwitchResults@UnionFs@@QEAA@XZ; UnionFs::CheckAndSwitchResults::~CheckAndSwitchResults(void)
0x14000d110  test    rbx, rbx
0x14000d113  jz      short loc_14000D152
0x14000d115  mov     rcx, rbx; this
0x14000d118  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000d11d  mov     rcx, [rbx+80h]
0x14000d124  test    rcx, rcx
0x14000d127  jz      short loc_14000D135
0x14000d129  mov     rax, [rcx]
0x14000d12c  mov     rax, [rax+18h]
0x14000d130  call    _guard_dispatch_icall
0x14000d135  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000d13c  mov     rdx, rbx; Entry
0x14000d13f  add     rcx, 380h; Lookaside
0x14000d146  call    cs:__imp_ExFreeToLookasideListEx
0x14000d14d  nop     dword ptr [rax+rax+00h]
0x14000d152  lea     rcx, [rbp+510h+var_4E0]; this
0x14000d156  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000d15b  mov     rcx, [rbp+510h+var_460]
0x14000d162  test    rcx, rcx
0x14000d165  jz      short loc_14000D173
0x14000d167  mov     rax, [rcx]
0x14000d16a  mov     rax, [rax+18h]
0x14000d16e  call    _guard_dispatch_icall
0x14000d173  lea     rcx, [rbp+510h+var_568]; this
0x14000d177  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000d17c  mov     rcx, [rbp+510h+var_4E8]
0x14000d180  test    rcx, rcx
0x14000d183  jz      short loc_14000D191
0x14000d185  mov     rax, [rcx]
0x14000d188  mov     rax, [rax+18h]
0x14000d18c  call    _guard_dispatch_icall
0x14000d191  mov     rcx, [rbp+510h+var_570]; this
0x14000d195  test    rcx, rcx
0x14000d198  jz      short loc_14000D19F
0x14000d19a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14000d19f  test    rdi, rdi
0x14000d1a2  jz      loc_14000D395
0x14000d1a8  mov     rcx, rdi; Context
0x14000d1ab  call    cs:__imp_FltReleaseContext
0x14000d1b2  nop     dword ptr [rax+rax+00h]
0x14000d1b7  jmp     loc_14000D395
0x14000d1bc  mov     eax, [rcx+28h]
0x14000d1bf  mov     edx, 90270h
0x14000d1c4  mov     r14d, 4
0x14000d1ca  cmp     eax, edx
0x14000d1cc  ja      loc_14000D74F
0x14000d1d2  jz      loc_14000D713
0x14000d1d8  mov     ecx, 90014h; this
0x14000d1dd  cmp     eax, ecx
0x14000d1df  ja      short loc_14000D212
0x14000d1e1  jz      loc_14000D5CE
0x14000d1e7  sub     eax, 90000h
0x14000d1ec  jz      loc_14000D5CE
0x14000d1f2  sub     eax, r14d
0x14000d1f5  jz      loc_14000D5CE
0x14000d1fb  sub     eax, r14d
0x14000d1fe  jz      loc_14000D5CE
0x14000d204  sub     eax, r14d
0x14000d207  jz      loc_14000D5CE
0x14000d20d  cmp     eax, r14d
  ... truncated ...
```
