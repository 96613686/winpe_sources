# UnionFs::UnionFsFilter::PostCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x140011a40`
- end: `0x140011def`
- name: `?PostCreate@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `943`
- prototype: `enum _FLT_POSTOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, UnionFs::CreateContext *this, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400056b4`
- `0x140006168`
- `0x140006d38`
- `0x14000f4f4`
- `0x1400110a8`
- `0x1400112e8`
- `0x140011a40`
- `0x140028450`
- `0x14002ab18`
- `0x1400424ec`
- `0x140042dd4`
- `0x1400430fc`
- `0x140056a50`
- `0x140056afc`
- `0x140079a24`
- `0x140079da0`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011db4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011db4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011bf4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c7a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011bf4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c7a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c86`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c86`
- `FLTMGR!FltIsDirectory` at `0x140011afd`
- `FLTMGR!FltIsDirectory` at `0x140011afd`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140011ac8`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140011ac8`

## string_xrefs

- `0x140011b20`: `UnionFs::UnionFsFilter::PostCreate`
- `0x140011bad`: `UnionFs::UnionFsFilter::PostCreate`
- `0x140011d15`: `UnionFs::UnionFsFilter::PostCreate`
- `0x140011b0f`: `API: FltIsDirectory`
- `0x140011b9c`: `PUSH: Failed to replace tombstone`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostCreate(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        UnionFs::CreateContext *this,
        char a4)
{
  NTSTATUS Status; // eax
  struct _FLT_INSTANCE *Instance; // rdx
  struct _FILE_OBJECT *FileObject; // rcx
  int v10; // ebx
  UnionFs::UfsPathCachePayload *v11; // rbx
  UnionFs::UfsPathCachePayload *v12; // rcx
  NTSTATUS v13; // ebx
  struct _ERESOURCE *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  struct _ERESOURCE *v17; // rcx
  __int64 v18; // rbx
  const struct UnionFs::UfsStreamHandleCtx **v19; // r12
  __int64 v20; // r13
  unsigned __int64 *v21; // rdx
  _QWORD *v22; // rcx
  __int64 v23; // rax
  UnionFs::UnionFsFilter *v24; // rcx
  UnionFs::UnionFsFilter *v25; // rcx
  struct UnionFs::StackEventTracer *v27; // [rsp+28h] [rbp-D8h]
  unsigned __int8 IsDirectory[8]; // [rsp+40h] [rbp-C0h] BYREF
  PERESOURCE Resource; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v32[188]; // [rsp+70h] [rbp-90h] BYREF

  Status = a1->IoStatus.Status;
  if ( Status >= 0 && Status != 260 && (a4 & 1) == 0 )
  {
    UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v32, 0xFF00020274uLL, a1);
    if ( *((_BYTE *)this + 185) )
    {
      a1->Iopb->Parameters.Create.Options |= 0x2000u;
      FltSetCallbackDataDirty(a1);
    }
    v30[0] = a1;
    v30[1] = a2;
    if ( *((_BYTE *)this + 184) )
    {
      Instance = a2->Instance;
      FileObject = a2->FileObject;
      IsDirectory[0] = 0;
      v10 = FltIsDirectory(FileObject, Instance, IsDirectory);
      if ( v10 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v10,
          (int)v32,
          (struct UnionFs::StackEventTracer *)0x43F00020310LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostCreate",
          "API: FltIsDirectory",
          (const char *)v27);
LABEL_9:
        lambda_0253b8b4e0d6e320c4e155f02c2544ea_::operator()(v30, (unsigned int)v10);
        a1->IoStatus.Status = v10;
        a1->IoStatus.Information = 0;
LABEL_10:
        UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v32);
LABEL_32:
        UnionFs::CreateContext::~CreateContext(this);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), this);
        return 0;
      }
      (*(void (__fastcall **)(_QWORD, PERESOURCE *))(**((_QWORD **)this + 21) + 16LL))(
        *((_QWORD *)this + 21),
        &Resource);
      v11 = (UnionFs::UfsPathCachePayload *)*((_QWORD *)this + 21);
      v12 = v11;
      if ( IsDirectory[0] )
      {
        v13 = UnionFs::UfsPathCachePayload::MarkReplaced(v11, (struct UnionFs::StackEventTracer *)v32);
        if ( v13 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v13,
            (int)v32,
            (struct UnionFs::StackEventTracer *)0x35600020330LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PostCreate",
            "PUSH: Failed to replace tombstone",
            (const char *)v27);
          lambda_0253b8b4e0d6e320c4e155f02c2544ea_::operator()(v30, (unsigned int)v13);
          v14 = Resource;
          a1->IoStatus.Status = v13;
          a1->IoStatus.Information = 0;
          Resource = 0;
          if ( v14 )
          {
            ExReleaseResourceLite(v14);
            KeLeaveCriticalRegion();
          }
          goto LABEL_10;
        }
        **((_DWORD **)this + 20) |= 8u;
        goto LABEL_20;
      }
      v15 = 0x41300020340LL;
    }
    else
    {
      v16 = *((_QWORD *)this + 21);
      if ( !v16 )
      {
LABEL_22:
        v18 = *((_QWORD *)this + 1);
        v19 = (const struct UnionFs::UfsStreamHandleCtx **)((char *)this + 160);
        v20 = *((_QWORD *)this + 20);
        FsFltWil::AcquirePushLockShared(&Resource, v18 + 72);
        v22 = *(_QWORD **)(v18 + 48);
        v31[0] = *v22;
        v23 = v22[1];
        v31[1] = v23;
        if ( v23 )
          _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
        if ( Resource )
          FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Resource, v21);
        UnionFs::UfsStreamHandleCtx::SetBackingLayer(v20, v31);
        v10 = UnionFs::UfsStreamHandleCtx::FltSet(a2->Instance, a2->FileObject);
        if ( v10 >= 0 )
        {
          if ( *((_BYTE *)this + 186) )
            a1->IoStatus.Information = *((_QWORD *)this + 24);
          UnionFs::UnionFsFilter::AcknowledgeRedirectionEcp(v24, a1, *v19);
          UnionFs::UnionFsFilter::VirtualizeQoCEcpIDs(
            v25,
            a1,
            a2,
            *v19,
            *((struct UnionFs::UfsUnionCtx **)this + 1),
            (struct UnionFs::StackEventTracer *)v32,
            0,
            0);
          goto LABEL_10;
        }
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v10,
          (int)v32,
          (struct UnionFs::StackEventTracer *)0x19100020365LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostCreate",
          "PUSH: Attaching streamhandle ctx",
          (const char *)v27);
        MicrosoftTelemetryAssertTriggeredMsgKM("Failed to attach streamhandle ctx to item in scratch");
        goto LABEL_9;
      }
      (*(void (__fastcall **)(__int64, PERESOURCE *))(*(_QWORD *)v16 + 16LL))(v16, &Resource);
      v11 = (UnionFs::UfsPathCachePayload *)*((_QWORD *)this + 21);
      v15 = 0x4140002034BLL;
      v12 = v11;
    }
    UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(v12, v15);
    UnionFs::UfsPathCachePayload::RevertSoftTombstone(v11);
LABEL_20:
    v17 = Resource;
    Resource = 0;
    if ( v17 )
    {
      ExReleaseResourceLite(v17);
      KeLeaveCriticalRegion();
    }
    goto LABEL_22;
  }
  if ( this )
    goto LABEL_32;
  return 0;
}

```

## disassembly

```asm
0x140011a40  mov     [rsp-8+arg_10], rbx
0x140011a45  mov     [rsp-8+arg_18], rsi
0x140011a4a  push    rbp
0x140011a4b  push    r12
0x140011a4d  push    r13
0x140011a4f  push    r14
0x140011a51  push    r15
0x140011a53  lea     rbp, [rsp-270h]
0x140011a5b  sub     rsp, 370h
0x140011a62  mov     rax, cs:__security_cookie
0x140011a69  xor     rax, rsp
0x140011a6c  mov     [rbp+290h+var_30], rax
0x140011a73  mov     eax, [rcx+18h]
0x140011a76  mov     rsi, r8
0x140011a79  mov     r15, rdx
0x140011a7c  mov     r14, rcx
0x140011a7f  test    eax, eax
0x140011a81  js      loc_140011D96
0x140011a87  cmp     eax, 104h
0x140011a8c  jz      loc_140011D96
0x140011a92  test    r9b, 1
0x140011a96  jnz     loc_140011D96
0x140011a9c  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x140011a9f  mov     rdx, 0FF00020274h; unsigned __int64
0x140011aa9  lea     rcx, [rsp+390h+var_320]; this
0x140011aae  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x140011ab3  cmp     byte ptr [rsi+0B9h], 0
0x140011aba  jz      short loc_140011AD4
0x140011abc  mov     rax, [r14+10h]
0x140011ac0  mov     rcx, r14; Data
0x140011ac3  bts     dword ptr [rax+20h], 0Dh
0x140011ac8  call    cs:__imp_FltSetCallbackDataDirty
0x140011acf  nop     dword ptr [rax+rax+00h]
0x140011ad4  mov     [rsp+390h+var_340], r14
0x140011ad9  mov     [rsp+390h+var_338], r15
0x140011ade  cmp     byte ptr [rsi+0B8h], 0
0x140011ae5  jz      loc_140011C29
0x140011aeb  mov     rdx, [r15+18h]; Instance
0x140011aef  lea     r8, [rsp+390h+IsDirectory]; IsDirectory
0x140011af4  mov     rcx, [r15+20h]; FileObject
0x140011af8  mov     [rsp+390h+IsDirectory], 0
0x140011afd  call    cs:__imp_FltIsDirectory
0x140011b04  nop     dword ptr [rax+rax+00h]
0x140011b09  mov     ebx, eax
0x140011b0b  test    eax, eax
0x140011b0d  jns     short loc_140011B5F
0x140011b0f  lea     rax, aApiFltisdirect; "API: FltIsDirectory"
0x140011b16  mov     r8, 43F00020310h; struct UnionFs::StackEventTracer *
0x140011b20  lea     r9, aUnionfsUnionfs_41; "UnionFs::UnionFsFilter::PostCreate"
0x140011b27  mov     [rsp+390h+var_370], rax; char *
0x140011b2c  lea     rdx, [rsp+390h+var_320]; int
0x140011b31  mov     ecx, ebx; this
0x140011b33  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011b38  mov     edx, ebx
0x140011b3a  lea     rcx, [rsp+390h+var_340]
0x140011b3f  call    _lambda_0253b8b4e0d6e320c4e155f02c2544ea___operator__
0x140011b44  mov     [r14+18h], ebx
0x140011b48  mov     qword ptr [r14+20h], 0
0x140011b50  lea     rcx, [rsp+390h+var_320]; this
0x140011b55  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140011b5a  jmp     loc_140011D9B
0x140011b5f  mov     rcx, [rsi+0A8h]
0x140011b66  lea     rdx, [rsp+390h+Resource]
0x140011b6b  mov     rax, [rcx]
0x140011b6e  mov     rax, [rax+10h]
0x140011b72  call    _guard_dispatch_icall
0x140011b77  cmp     [rsp+390h+IsDirectory], 0
0x140011b7c  mov     rbx, [rsi+0A8h]
0x140011b83  mov     rcx, rbx; this
0x140011b86  jz      loc_140011C1D
0x140011b8c  lea     rdx, [rsp+390h+var_320]; struct UnionFs::StackEventTracer *
0x140011b91  call    ?MarkReplaced@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::MarkReplaced(UnionFs::StackEventTracer &)
0x140011b96  mov     ebx, eax
0x140011b98  test    eax, eax
0x140011b9a  jns     short loc_140011C11
0x140011b9c  lea     rax, aPushFailedToRe_0; "PUSH: Failed to replace tombstone"
0x140011ba3  mov     r8, 35600020330h; struct UnionFs::StackEventTracer *
0x140011bad  lea     r9, aUnionfsUnionfs_41; "UnionFs::UnionFsFilter::PostCreate"
0x140011bb4  mov     [rsp+390h+var_370], rax; char *
0x140011bb9  lea     rdx, [rsp+390h+var_320]; int
0x140011bbe  mov     ecx, ebx; this
0x140011bc0  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011bc5  mov     edx, ebx
0x140011bc7  lea     rcx, [rsp+390h+var_340]
0x140011bcc  call    _lambda_0253b8b4e0d6e320c4e155f02c2544ea___operator__
0x140011bd1  mov     rcx, [rsp+390h+Resource]; Resource
0x140011bd6  mov     [r14+18h], ebx
0x140011bda  mov     qword ptr [r14+20h], 0
0x140011be2  mov     [rsp+390h+Resource], 0
0x140011beb  test    rcx, rcx
0x140011bee  jz      loc_140011B50
0x140011bf4  call    cs:__imp_ExReleaseResourceLite
0x140011bfb  nop     dword ptr [rax+rax+00h]
0x140011c00  call    cs:__imp_KeLeaveCriticalRegion
0x140011c07  nop     dword ptr [rax+rax+00h]
0x140011c0c  jmp     loc_140011B50
0x140011c11  mov     rax, [rsi+0A0h]
0x140011c18  or      dword ptr [rax], 8
0x140011c1b  jmp     short loc_140011C67
0x140011c1d  mov     rdx, 41300020340h
0x140011c27  jmp     short loc_140011C5A
0x140011c29  mov     rcx, [rsi+0A8h]
0x140011c30  test    rcx, rcx
0x140011c33  jz      short loc_140011C92
0x140011c35  mov     rax, [rcx]
0x140011c38  lea     rdx, [rsp+390h+Resource]
0x140011c3d  mov     rax, [rax+10h]
0x140011c41  call    _guard_dispatch_icall
0x140011c46  mov     rbx, [rsi+0A8h]
0x140011c4d  mov     rdx, 4140002034Bh
0x140011c57  mov     rcx, rbx
0x140011c5a  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x140011c5f  mov     rcx, rbx; this
0x140011c62  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ; UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)
0x140011c67  mov     rcx, [rsp+390h+Resource]; Resource
0x140011c6c  mov     [rsp+390h+Resource], 0
0x140011c75  test    rcx, rcx
0x140011c78  jz      short loc_140011C92
0x140011c7a  call    cs:__imp_ExReleaseResourceLite
0x140011c81  nop     dword ptr [rax+rax+00h]
0x140011c86  call    cs:__imp_KeLeaveCriticalRegion
0x140011c8d  nop     dword ptr [rax+rax+00h]
0x140011c92  mov     rbx, [rsi+8]
0x140011c96  lea     r12, [rsi+0A0h]
0x140011c9d  mov     r13, [r12]
0x140011ca1  lea     rcx, [rsp+390h+Resource]
0x140011ca6  lea     rdx, [rbx+48h]
0x140011caa  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140011caf  mov     rcx, [rbx+30h]
0x140011cb3  mov     rax, [rcx]
0x140011cb6  mov     [rsp+390h+var_330], rax
0x140011cbb  mov     rax, [rcx+8]
0x140011cbf  mov     [rsp+390h+var_328], rax
0x140011cc4  test    rax, rax
0x140011cc7  jz      short loc_140011CCD
0x140011cc9  lock inc dword ptr [rax+8]
0x140011ccd  mov     rcx, [rsp+390h+Resource]; this
0x140011cd2  test    rcx, rcx
0x140011cd5  jz      short loc_140011CDC
0x140011cd7  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140011cdc  lea     rdx, [rsp+390h+var_330]
0x140011ce1  mov     rcx, r13
0x140011ce4  call    ?SetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEAAXV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@@Z; UnionFs::UfsStreamHandleCtx::SetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx>)
0x140011ce9  mov     rdx, [r15+20h]; FileObject
0x140011ced  lea     r9, [rsp+390h+var_320]
0x140011cf2  mov     rcx, [r15+18h]; Instance
0x140011cf6  mov     r8, r12
0x140011cf9  call    ?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140011cfe  mov     ebx, eax
0x140011d00  test    eax, eax
0x140011d02  jns     short loc_140011D3E
0x140011d04  lea     rax, aPushAttachingS; "PUSH: Attaching streamhandle ctx"
0x140011d0b  mov     r8, 19100020365h; struct UnionFs::StackEventTracer *
0x140011d15  lea     r9, aUnionfsUnionfs_41; "UnionFs::UnionFsFilter::PostCreate"
0x140011d1c  mov     [rsp+390h+var_370], rax; char *
0x140011d21  lea     rdx, [rsp+390h+var_320]; int
0x140011d26  mov     ecx, ebx; this
0x140011d28  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011d2d  lea     rcx, aFailedToAttach; "Failed to attach streamhandle ctx to it"...
0x140011d34  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140011d39  jmp     loc_140011B38
0x140011d3e  cmp     byte ptr [rsi+0BAh], 0
0x140011d45  jz      short loc_140011D52
0x140011d47  mov     rax, [rsi+0C0h]
0x140011d4e  mov     [r14+20h], rax
0x140011d52  mov     r8, [r12]; struct UnionFs::UfsStreamHandleCtx *
0x140011d56  mov     rdx, r14; struct _FLT_CALLBACK_DATA *
0x140011d59  call    ?AcknowledgeRedirectionEcp@UnionFsFilter@UnionFs@@AEAAXAEAU_FLT_CALLBACK_DATA@@AEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::AcknowledgeRedirectionEcp(_FLT_CALLBACK_DATA &,UnionFs::UfsStreamHandleCtx const &)
0x140011d5e  mov     r9, [r12]; struct UnionFs::UfsStreamHandleCtx *
0x140011d62  lea     rax, [rsp+390h+var_320]
0x140011d67  mov     [rsp+390h+var_358], 0; unsigned int
0x140011d6f  mov     r8, r15; struct _FLT_RELATED_OBJECTS *
0x140011d72  mov     [rsp+390h+var_360], 0; struct _QUERY_ON_CREATE_ECP_CONTEXT *
0x140011d7b  mov     rdx, r14; struct _FLT_CALLBACK_DATA *
0x140011d7e  mov     [rsp+390h+var_368], rax; struct UnionFs::StackEventTracer *
0x140011d83  mov     rax, [rsi+8]
0x140011d87  mov     [rsp+390h+var_370], rax; struct UnionFs::UfsUnionCtx *
0x140011d8c  call    ?VirtualizeQoCEcpIDs@UnionFsFilter@UnionFs@@AEAAXAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVStackEventTracer@2@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@K@Z; UnionFs::UnionFsFilter::VirtualizeQoCEcpIDs(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &,_QUERY_ON_CREATE_ECP_CONTEXT *,ulong)
0x140011d91  jmp     loc_140011B50
0x140011d96  test    rsi, rsi
0x140011d99  jz      short loc_140011DC0
0x140011d9b  mov     rcx, rsi; this
0x140011d9e  call    ??1CreateContext@UnionFs@@QEAA@XZ; UnionFs::CreateContext::~CreateContext(void)
0x140011da3  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140011daa  mov     rdx, rsi; Entry
0x140011dad  add     rcx, 0E0h; Lookaside
0x140011db4  call    cs:__imp_ExFreeToLookasideListEx
0x140011dbb  nop     dword ptr [rax+rax+00h]
0x140011dc0  xor     eax, eax
0x140011dc2  mov     rcx, [rbp+290h+var_30]
0x140011dc9  xor     rcx, rsp; StackCookie
0x140011dcc  call    __security_check_cookie
0x140011dd1  lea     r11, [rsp+390h+var_20]
0x140011dd9  mov     rbx, [r11+40h]
0x140011ddd  mov     rsi, [r11+48h]
0x140011de1  mov     rsp, r11
0x140011de4  pop     r15
0x140011de6  pop     r14
0x140011de8  pop     r13
0x140011dea  pop     r12
0x140011dec  pop     rbp
0x140011ded  retn
```
