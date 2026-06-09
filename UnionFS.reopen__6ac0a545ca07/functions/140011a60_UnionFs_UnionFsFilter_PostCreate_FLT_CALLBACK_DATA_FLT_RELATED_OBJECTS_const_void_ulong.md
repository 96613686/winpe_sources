# UnionFs::UnionFsFilter::PostCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x140011a60`
- end: `0x140011e0f`
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
- `0x14000f514`
- `0x1400110c8`
- `0x140011308`
- `0x140011a60`
- `0x1400284f0`
- `0x14002abb8`
- `0x140042674`
- `0x140042f54`
- `0x14004327c`
- `0x140056bd0`
- `0x140056c7c`
- `0x140079d44`
- `0x14007a0c0`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011dd4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140011dd4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c14`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c14`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c9a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c20`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011ca6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c20`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011ca6`
- `FLTMGR!FltIsDirectory` at `0x140011b1d`
- `FLTMGR!FltIsDirectory` at `0x140011b1d`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140011ae8`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140011ae8`

## string_xrefs

- `0x140011b40`: `UnionFs::UnionFsFilter::PostCreate`
- `0x140011bcd`: `UnionFs::UnionFsFilter::PostCreate`
- `0x140011d35`: `UnionFs::UnionFsFilter::PostCreate`
- `0x140011b2f`: `API: FltIsDirectory`
- `0x140011bbc`: `PUSH: Failed to replace tombstone`

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
    UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v32, 0xFF00020264uLL, a1);
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
          (struct UnionFs::StackEventTracer *)0x43F00020300LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostCreate",
          "API: FltIsDirectory",
          (const char *)v27);
LABEL_9:
        lambda_af47b0d5c7c2b09a9289ca3bfeac0e14_::operator()(v30, (unsigned int)v10);
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
            (struct UnionFs::StackEventTracer *)0x35600020320LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PostCreate",
            "PUSH: Failed to replace tombstone",
            (const char *)v27);
          lambda_af47b0d5c7c2b09a9289ca3bfeac0e14_::operator()(v30, (unsigned int)v13);
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
      v15 = 0x41300020330LL;
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
          (struct UnionFs::StackEventTracer *)0x19100020355LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostCreate",
          "PUSH: Attaching streamhandle ctx",
          (const char *)v27);
        MicrosoftTelemetryAssertTriggeredMsgKM("Failed to attach streamhandle ctx to item in scratch");
        goto LABEL_9;
      }
      (*(void (__fastcall **)(__int64, PERESOURCE *))(*(_QWORD *)v16 + 16LL))(v16, &Resource);
      v11 = (UnionFs::UfsPathCachePayload *)*((_QWORD *)this + 21);
      v15 = 0x4140002033BLL;
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
0x140011a60  mov     [rsp-8+arg_10], rbx
0x140011a65  mov     [rsp-8+arg_18], rsi
0x140011a6a  push    rbp
0x140011a6b  push    r12
0x140011a6d  push    r13
0x140011a6f  push    r14
0x140011a71  push    r15
0x140011a73  lea     rbp, [rsp-270h]
0x140011a7b  sub     rsp, 370h
0x140011a82  mov     rax, cs:__security_cookie
0x140011a89  xor     rax, rsp
0x140011a8c  mov     [rbp+290h+var_30], rax
0x140011a93  mov     eax, [rcx+18h]
0x140011a96  mov     rsi, r8
0x140011a99  mov     r15, rdx
0x140011a9c  mov     r14, rcx
0x140011a9f  test    eax, eax
0x140011aa1  js      loc_140011DB6
0x140011aa7  cmp     eax, 104h
0x140011aac  jz      loc_140011DB6
0x140011ab2  test    r9b, 1
0x140011ab6  jnz     loc_140011DB6
0x140011abc  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x140011abf  mov     rdx, 0FF00020264h; unsigned __int64
0x140011ac9  lea     rcx, [rsp+390h+var_320]; this
0x140011ace  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x140011ad3  cmp     byte ptr [rsi+0B9h], 0
0x140011ada  jz      short loc_140011AF4
0x140011adc  mov     rax, [r14+10h]
0x140011ae0  mov     rcx, r14; Data
0x140011ae3  bts     dword ptr [rax+20h], 0Dh
0x140011ae8  call    cs:__imp_FltSetCallbackDataDirty
0x140011aef  nop     dword ptr [rax+rax+00h]
0x140011af4  mov     [rsp+390h+var_340], r14
0x140011af9  mov     [rsp+390h+var_338], r15
0x140011afe  cmp     byte ptr [rsi+0B8h], 0
0x140011b05  jz      loc_140011C49
0x140011b0b  mov     rdx, [r15+18h]; Instance
0x140011b0f  lea     r8, [rsp+390h+IsDirectory]; IsDirectory
0x140011b14  mov     rcx, [r15+20h]; FileObject
0x140011b18  mov     [rsp+390h+IsDirectory], 0
0x140011b1d  call    cs:__imp_FltIsDirectory
0x140011b24  nop     dword ptr [rax+rax+00h]
0x140011b29  mov     ebx, eax
0x140011b2b  test    eax, eax
0x140011b2d  jns     short loc_140011B7F
0x140011b2f  lea     rax, aApiFltisdirect; "API: FltIsDirectory"
0x140011b36  mov     r8, 43F00020300h; struct UnionFs::StackEventTracer *
0x140011b40  lea     r9, aUnionfsUnionfs_42; "UnionFs::UnionFsFilter::PostCreate"
0x140011b47  mov     [rsp+390h+var_370], rax; char *
0x140011b4c  lea     rdx, [rsp+390h+var_320]; int
0x140011b51  mov     ecx, ebx; this
0x140011b53  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011b58  mov     edx, ebx
0x140011b5a  lea     rcx, [rsp+390h+var_340]
0x140011b5f  call    _lambda_af47b0d5c7c2b09a9289ca3bfeac0e14___operator__
0x140011b64  mov     [r14+18h], ebx
0x140011b68  mov     qword ptr [r14+20h], 0
0x140011b70  lea     rcx, [rsp+390h+var_320]; this
0x140011b75  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140011b7a  jmp     loc_140011DBB
0x140011b7f  mov     rcx, [rsi+0A8h]
0x140011b86  lea     rdx, [rsp+390h+Resource]
0x140011b8b  mov     rax, [rcx]
0x140011b8e  mov     rax, [rax+10h]
0x140011b92  call    _guard_dispatch_icall
0x140011b97  cmp     [rsp+390h+IsDirectory], 0
0x140011b9c  mov     rbx, [rsi+0A8h]
0x140011ba3  mov     rcx, rbx; this
0x140011ba6  jz      loc_140011C3D
0x140011bac  lea     rdx, [rsp+390h+var_320]; struct UnionFs::StackEventTracer *
0x140011bb1  call    ?MarkReplaced@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::MarkReplaced(UnionFs::StackEventTracer &)
0x140011bb6  mov     ebx, eax
0x140011bb8  test    eax, eax
0x140011bba  jns     short loc_140011C31
0x140011bbc  lea     rax, aPushFailedToRe_0; "PUSH: Failed to replace tombstone"
0x140011bc3  mov     r8, 35600020320h; struct UnionFs::StackEventTracer *
0x140011bcd  lea     r9, aUnionfsUnionfs_42; "UnionFs::UnionFsFilter::PostCreate"
0x140011bd4  mov     [rsp+390h+var_370], rax; char *
0x140011bd9  lea     rdx, [rsp+390h+var_320]; int
0x140011bde  mov     ecx, ebx; this
0x140011be0  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011be5  mov     edx, ebx
0x140011be7  lea     rcx, [rsp+390h+var_340]
0x140011bec  call    _lambda_af47b0d5c7c2b09a9289ca3bfeac0e14___operator__
0x140011bf1  mov     rcx, [rsp+390h+Resource]; Resource
0x140011bf6  mov     [r14+18h], ebx
0x140011bfa  mov     qword ptr [r14+20h], 0
0x140011c02  mov     [rsp+390h+Resource], 0
0x140011c0b  test    rcx, rcx
0x140011c0e  jz      loc_140011B70
0x140011c14  call    cs:__imp_ExReleaseResourceLite
0x140011c1b  nop     dword ptr [rax+rax+00h]
0x140011c20  call    cs:__imp_KeLeaveCriticalRegion
0x140011c27  nop     dword ptr [rax+rax+00h]
0x140011c2c  jmp     loc_140011B70
0x140011c31  mov     rax, [rsi+0A0h]
0x140011c38  or      dword ptr [rax], 8
0x140011c3b  jmp     short loc_140011C87
0x140011c3d  mov     rdx, 41300020330h
0x140011c47  jmp     short loc_140011C7A
0x140011c49  mov     rcx, [rsi+0A8h]
0x140011c50  test    rcx, rcx
0x140011c53  jz      short loc_140011CB2
0x140011c55  mov     rax, [rcx]
0x140011c58  lea     rdx, [rsp+390h+Resource]
0x140011c5d  mov     rax, [rax+10h]
0x140011c61  call    _guard_dispatch_icall
0x140011c66  mov     rbx, [rsi+0A8h]
0x140011c6d  mov     rdx, 4140002033Bh
0x140011c77  mov     rcx, rbx
0x140011c7a  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x140011c7f  mov     rcx, rbx; this
0x140011c82  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ; UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)
0x140011c87  mov     rcx, [rsp+390h+Resource]; Resource
0x140011c8c  mov     [rsp+390h+Resource], 0
0x140011c95  test    rcx, rcx
0x140011c98  jz      short loc_140011CB2
0x140011c9a  call    cs:__imp_ExReleaseResourceLite
0x140011ca1  nop     dword ptr [rax+rax+00h]
0x140011ca6  call    cs:__imp_KeLeaveCriticalRegion
0x140011cad  nop     dword ptr [rax+rax+00h]
0x140011cb2  mov     rbx, [rsi+8]
0x140011cb6  lea     r12, [rsi+0A0h]
0x140011cbd  mov     r13, [r12]
0x140011cc1  lea     rcx, [rsp+390h+Resource]
0x140011cc6  lea     rdx, [rbx+48h]
0x140011cca  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140011ccf  mov     rcx, [rbx+30h]
0x140011cd3  mov     rax, [rcx]
0x140011cd6  mov     [rsp+390h+var_330], rax
0x140011cdb  mov     rax, [rcx+8]
0x140011cdf  mov     [rsp+390h+var_328], rax
0x140011ce4  test    rax, rax
0x140011ce7  jz      short loc_140011CED
0x140011ce9  lock inc dword ptr [rax+8]
0x140011ced  mov     rcx, [rsp+390h+Resource]; this
0x140011cf2  test    rcx, rcx
0x140011cf5  jz      short loc_140011CFC
0x140011cf7  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140011cfc  lea     rdx, [rsp+390h+var_330]
0x140011d01  mov     rcx, r13
0x140011d04  call    ?SetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEAAXV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@@Z; UnionFs::UfsStreamHandleCtx::SetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx>)
0x140011d09  mov     rdx, [r15+20h]; FileObject
0x140011d0d  lea     r9, [rsp+390h+var_320]
0x140011d12  mov     rcx, [r15+18h]; Instance
0x140011d16  mov     r8, r12
0x140011d19  call    ?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140011d1e  mov     ebx, eax
0x140011d20  test    eax, eax
0x140011d22  jns     short loc_140011D5E
0x140011d24  lea     rax, aPushAttachingS; "PUSH: Attaching streamhandle ctx"
0x140011d2b  mov     r8, 19100020355h; struct UnionFs::StackEventTracer *
0x140011d35  lea     r9, aUnionfsUnionfs_42; "UnionFs::UnionFsFilter::PostCreate"
0x140011d3c  mov     [rsp+390h+var_370], rax; char *
0x140011d41  lea     rdx, [rsp+390h+var_320]; int
0x140011d46  mov     ecx, ebx; this
0x140011d48  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011d4d  lea     rcx, aFailedToAttach; "Failed to attach streamhandle ctx to it"...
0x140011d54  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140011d59  jmp     loc_140011B58
0x140011d5e  cmp     byte ptr [rsi+0BAh], 0
0x140011d65  jz      short loc_140011D72
0x140011d67  mov     rax, [rsi+0C0h]
0x140011d6e  mov     [r14+20h], rax
0x140011d72  mov     r8, [r12]; struct UnionFs::UfsStreamHandleCtx *
0x140011d76  mov     rdx, r14; struct _FLT_CALLBACK_DATA *
0x140011d79  call    ?AcknowledgeRedirectionEcp@UnionFsFilter@UnionFs@@AEAAXAEAU_FLT_CALLBACK_DATA@@AEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::AcknowledgeRedirectionEcp(_FLT_CALLBACK_DATA &,UnionFs::UfsStreamHandleCtx const &)
0x140011d7e  mov     r9, [r12]; struct UnionFs::UfsStreamHandleCtx *
0x140011d82  lea     rax, [rsp+390h+var_320]
0x140011d87  mov     [rsp+390h+var_358], 0; unsigned int
0x140011d8f  mov     r8, r15; struct _FLT_RELATED_OBJECTS *
0x140011d92  mov     [rsp+390h+var_360], 0; struct _QUERY_ON_CREATE_ECP_CONTEXT *
0x140011d9b  mov     rdx, r14; struct _FLT_CALLBACK_DATA *
0x140011d9e  mov     [rsp+390h+var_368], rax; struct UnionFs::StackEventTracer *
0x140011da3  mov     rax, [rsi+8]
0x140011da7  mov     [rsp+390h+var_370], rax; struct UnionFs::UfsUnionCtx *
0x140011dac  call    ?VirtualizeQoCEcpIDs@UnionFsFilter@UnionFs@@AEAAXAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVStackEventTracer@2@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@K@Z; UnionFs::UnionFsFilter::VirtualizeQoCEcpIDs(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &,_QUERY_ON_CREATE_ECP_CONTEXT *,ulong)
0x140011db1  jmp     loc_140011B70
0x140011db6  test    rsi, rsi
0x140011db9  jz      short loc_140011DE0
0x140011dbb  mov     rcx, rsi; this
0x140011dbe  call    ??1CreateContext@UnionFs@@QEAA@XZ; UnionFs::CreateContext::~CreateContext(void)
0x140011dc3  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140011dca  mov     rdx, rsi; Entry
0x140011dcd  add     rcx, 0E0h; Lookaside
0x140011dd4  call    cs:__imp_ExFreeToLookasideListEx
0x140011ddb  nop     dword ptr [rax+rax+00h]
0x140011de0  xor     eax, eax
0x140011de2  mov     rcx, [rbp+290h+var_30]
0x140011de9  xor     rcx, rsp; StackCookie
0x140011dec  call    __security_check_cookie
0x140011df1  lea     r11, [rsp+390h+var_20]
0x140011df9  mov     rbx, [r11+40h]
0x140011dfd  mov     rsi, [r11+48h]
0x140011e01  mov     rsp, r11
0x140011e04  pop     r15
0x140011e06  pop     r14
0x140011e08  pop     r13
0x140011e0a  pop     r12
0x140011e0c  pop     rbp
0x140011e0d  retn
```
