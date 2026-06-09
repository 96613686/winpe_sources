# UnionFs::UnionFsFilter::PreCreateFileCreate(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x140013708`
- end: `0x140013baa`
- name: `?PreCreateFileCreate@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `1186`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140011e00`

## callees

- `0x14000c20c`
- `0x14000f7fc`
- `0x140010b88`
- `0x140011198`
- `0x140013708`
- `0x14003cd88`
- `0x14004397c`
- `0x140043ef4`
- `0x140056ac4`
- `0x140056afc`
- `0x140060ed8`
- `0x1400610fc`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013929`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001399d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013929`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001399d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013ad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b97`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013859`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013859`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013865`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013865`

## string_xrefs

- `0x1400137ba`: `PUSH: Cache lookup`
- `0x140013959`: `PUSH: Allocating scratch path for layer lookup`
- `0x140013b58`: `PUSH: Preparing for scratch create`
- `0x1400137cb`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x1400138ec`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x1400139ce`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x140013a31`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x140013b69`: `UnionFs::UnionFsFilter::PreCreateFileCreate`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileCreate(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        enum _FLT_PREOP_CALLBACK_STATUS *a4,
        struct UnionFs::CreateContext *a5,
        struct UnionFs::StackEventTracer *a6,
        const struct UnionFs::UfsSiloCtx *a7)
{
  PFILE_OBJECT FileObject; // rax
  int v8; // r15d
  struct UnionFs::CreateContext *v9; // r14
  ULONG v13; // r9d
  _BOOL8 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rcx
  struct UnionFs::StackEventTracer *v17; // rdi
  int v18; // ebx
  struct _ERESOURCE *v19; // rcx
  utl::_RefCountBase *v20; // rcx
  UnionFs::Rtl *v21; // rcx
  struct _UNICODE_STRING *v22; // rdx
  const char *v23; // rax
  __int64 v24; // r8
  struct _UNICODE_STRING *v25; // rdx
  PVOID v26; // rbx
  PVOID v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rcx
  utl::_RefCountBase *v31; // rcx
  utl::_RefCountBase *v32; // rcx
  utl::_RefCountBase *v33; // rcx
  int v35; // esi
  utl::_RefCountBase *v36; // rcx
  struct UnionFs::UfsStreamHandleCtx *v37; // [rsp+28h] [rbp-89h]
  struct UnionFs::UfsStreamHandleCtx *v38; // [rsp+28h] [rbp-89h]
  struct UnionFs::UfsStreamHandleCtx *v39; // [rsp+28h] [rbp-89h]
  UNICODE_STRING Source; // [rsp+50h] [rbp-61h] BYREF
  struct _UNICODE_STRING v41; // [rsp+60h] [rbp-51h] BYREF
  __int128 v42; // [rsp+70h] [rbp-41h] BYREF
  utl::_RefCountBase *v43[2]; // [rsp+80h] [rbp-31h] BYREF
  PERESOURCE Resource; // [rsp+90h] [rbp-21h]
  __int64 v45; // [rsp+98h] [rbp-19h]
  __int128 v46; // [rsp+A0h] [rbp-11h]
  PVOID P; // [rsp+100h] [rbp+4Fh] BYREF

  P = this;
  FileObject = a3->FileObject;
  v8 = 0;
  v9 = a5;
  *a4 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v13 = FileObject->Flags >> 17;
  v42 = 0;
  v14 = (v13 & 1) == 0;
  *(_OWORD *)v43 = 0;
  Resource = 0;
  LODWORD(v42) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v15 = *((_QWORD *)v9 + 1);
  v45 = 0;
  v46 = 0;
  if ( *(_DWORD *)(v15 + 28) == 2 )
    v16 = *(_QWORD *)(*(_QWORD *)(v15 + 32) + 16LL);
  else
    v16 = *((_QWORD *)UnionFs::g_FilterState + 10);
  v17 = a6;
  v37 = a6;
  v18 = UnionFs::UfsPathCache::LookupEntry(v16, a3->Instance, *(_QWORD *)v9, v14, &v42);
  if ( v18 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v18,
      (int)v17,
      (struct UnionFs::StackEventTracer *)0x20F00020739LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileCreate",
      "PUSH: Cache lookup",
      (const char *)v37);
    goto LABEL_56;
  }
  if ( DWORD1(v42) )
  {
    if ( DWORD1(v42) == 1 )
    {
      if ( (BYTE8(v42) & 4) != 0 )
      {
        UnionFs::CreateContext::OverwriteTombstone(v9, v43, 1);
LABEL_10:
        v18 = v8;
        goto LABEL_56;
      }
      a2->IoStatus.Status = -1073741771;
LABEL_12:
      a2->IoStatus.Information = 0;
      *a4 = FLT_PREOP_COMPLETE;
      goto LABEL_10;
    }
    if ( (BYTE8(v42) & 4) != 0 )
    {
      a2->IoStatus.Status = -1073741766;
      goto LABEL_12;
    }
    if ( (_DWORD)v45 == 1 )
    {
      **((_DWORD **)v9 + 20) |= 8u;
      goto LABEL_10;
    }
    v19 = Resource;
    Resource = 0;
    if ( v19 )
    {
      ExReleaseResourceLite(v19);
      KeLeaveCriticalRegion();
    }
    v20 = v43[1];
    v43[0] = 0;
    v43[1] = 0;
    if ( v20 )
      utl::_RefCountBase::_DecStrong(v20);
  }
  P = 0;
  if ( (_DWORD)v45 != 2 )
    goto LABEL_30;
  v21 = (UnionFs::Rtl *)(*(_QWORD *)v9 + 8LL);
  Source = (UNICODE_STRING)**((_OWORD **)&v46 + 1);
  v41 = *(struct _UNICODE_STRING *)v46;
  v8 = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(v21, &v41, &Source, &P, (int)v17);
  if ( v8 < 0 )
  {
    v23 = "PUSH: Replacing substring";
    v24 = 0x38000020783LL;
LABEL_24:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v8,
      (int)v17,
      (struct UnionFs::StackEventTracer *)v24,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileCreate",
      v23,
      (const char *)v37);
    v26 = P;
    if ( !P )
      goto LABEL_10;
    if ( !*((_BYTE *)P + 16) )
      *(_OWORD *)P = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v26, v25);
LABEL_28:
    ExFreePoolWithTag(v26, 0);
    goto LABEL_10;
  }
  v27 = P;
  if ( !P )
  {
LABEL_30:
    v8 = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)v9, &P, v17);
    if ( v8 < 0 )
    {
      v23 = "PUSH: Allocating scratch path for layer lookup";
      v24 = 0x3900002078ELL;
      goto LABEL_24;
    }
    v27 = P;
  }
  v28 = *((_QWORD *)v9 + 20);
  v29 = *(_QWORD *)(v28 + 64);
  *(_QWORD *)(v28 + 64) = v27;
  if ( v29 )
  {
    if ( !*(_BYTE *)(v29 + 16) )
      *(_OWORD *)v29 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v29, v22);
    ExFreePoolWithTag((PVOID)v29, 0);
  }
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&P);
  v26 = P;
  if ( !P )
  {
    v18 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v17,
      (struct UnionFs::StackEventTracer *)0x3FB00020798LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileCreate",
      "ORIGIN: Allocating findAndStatResults",
      (const char *)v37);
    goto LABEL_56;
  }
  v30 = *((_QWORD *)v9 + 1);
  v38 = (struct UnionFs::UfsStreamHandleCtx *)P;
  v41 = *(struct _UNICODE_STRING *)*(_QWORD *)(*((_QWORD *)v9 + 20) + 64LL);
  v8 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v30, a2, &v41);
  if ( v8 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v8,
      (int)v17,
      (struct UnionFs::StackEventTracer *)0xE4000207A2LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileCreate",
      "PUSH: Probing for item in layers",
      (const char *)v38);
    if ( !v26 )
      goto LABEL_10;
    v31 = (utl::_RefCountBase *)*((_QWORD *)v26 + 11);
    if ( v31 )
      utl::_RefCountBase::_DecStrong(v31);
    goto LABEL_28;
  }
  if ( v8 == 260 )
  {
    if ( v26 )
    {
      v32 = (utl::_RefCountBase *)*((_QWORD *)v26 + 11);
      if ( v32 )
        utl::_RefCountBase::_DecStrong(v32);
      ExFreePoolWithTag(v26, 0);
    }
    v18 = 260;
    goto LABEL_56;
  }
  if ( *(_WORD *)v26 == 1 )
  {
    a2->IoStatus.Status = -1073741771;
    a2->IoStatus.Information = 0;
    *a4 = FLT_PREOP_COMPLETE;
LABEL_51:
    if ( v26 )
    {
      v33 = (utl::_RefCountBase *)*((_QWORD *)v26 + 11);
      if ( v33 )
        utl::_RefCountBase::_DecStrong(v33);
      ExFreePoolWithTag(v26, 0);
    }
    v18 = 0;
    goto LABEL_56;
  }
  if ( *(_WORD *)v26 != 3 )
    goto LABEL_51;
  v35 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
          *((UnionFs::UfsUnionCtx **)v9 + 1),
          a2,
          a3,
          *(const struct _FLT_FILE_NAME_INFORMATION **)v9,
          *(const struct UnionFs::UfsPathName **)(*((_QWORD *)v9 + 20) + 64LL),
          *((const struct UnionFs::UfsStreamHandleCtx **)v9 + 20),
          *((const struct UnionFs::UfsLayerCtx **)v26 + 10),
          v17,
          a7);
  if ( v35 >= 0 )
    goto LABEL_51;
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v35,
    (int)v17,
    (struct UnionFs::StackEventTracer *)0xE5000207BFLL,
    (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileCreate",
    "PUSH: Preparing for scratch create",
    (const char *)v39);
  if ( v26 )
  {
    v36 = (utl::_RefCountBase *)*((_QWORD *)v26 + 11);
    if ( v36 )
      utl::_RefCountBase::_DecStrong(v36);
    ExFreePoolWithTag(v26, 0);
  }
  v18 = v35;
LABEL_56:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v42);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140013708  mov     [rsp-8+P], rcx
0x14001370d  push    rbp
0x14001370e  push    rbx
0x14001370f  push    rsi
0x140013710  push    rdi
0x140013711  push    r12
0x140013713  push    r13
0x140013715  push    r14
0x140013717  push    r15
0x140013719  lea     rbp, [rsp-7]
0x14001371e  sub     rsp, 0B8h
0x140013725  mov     rax, [r8+20h]
0x140013729  xor     r15d, r15d
0x14001372c  mov     r14, [rbp+3Fh+arg_20]
0x140013730  mov     r12, r9
0x140013733  mov     [r9], r15d
0x140013736  xorps   xmm1, xmm1
0x140013739  xorps   xmm0, xmm0
0x14001373c  mov     r13, r8
0x14001373f  mov     r9d, [rax+50h]
0x140013743  mov     rsi, rdx
0x140013746  shr     r9d, 11h
0x14001374a  movd    eax, xmm1
0x14001374e  not     r9d
0x140013751  movdqa  [rbp+3Fh+var_80], xmm1
0x140013756  and     r9d, 1
0x14001375a  movdqa  xmmword ptr [rbp+3Fh+var_70], xmm0
0x14001375f  or      eax, 3
0x140013762  mov     [rbp+3Fh+Resource], r15
0x140013766  mov     dword ptr [rbp+3Fh+var_80], eax
0x140013769  mov     rax, [r14+8]
0x14001376d  mov     [rbp+3Fh+var_58], r15
0x140013771  movdqa  [rbp+3Fh+var_50], xmm0
0x140013776  cmp     dword ptr [rax+1Ch], 2
0x14001377a  jnz     short loc_140013786
0x14001377c  mov     rax, [rax+20h]
0x140013780  mov     rcx, [rax+10h]
0x140013784  jmp     short loc_140013791
0x140013786  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001378d  mov     rcx, [rax+50h]
0x140013791  mov     rdi, [rbp+3Fh+arg_28]
0x140013795  lea     rax, [rbp+3Fh+var_80]
0x140013799  mov     r8, [r14]
0x14001379c  mov     rdx, [r13+18h]
0x1400137a0  mov     [rsp+0F0h+var_C0], rsi
0x1400137a5  mov     [rsp+0F0h+var_C8], rdi; char *
0x1400137aa  mov     [rsp+0F0h+var_D0], rax
0x1400137af  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x1400137b4  mov     ebx, eax
0x1400137b6  test    eax, eax
0x1400137b8  jns     short loc_1400137E6
0x1400137ba  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x1400137c1  mov     r8, 20F00020739h; struct UnionFs::StackEventTracer *
0x1400137cb  lea     r9, aUnionfsUnionfs_50; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x1400137d2  mov     [rsp+0F0h+var_D0], rax; char *
0x1400137d7  mov     rdx, rdi; int
0x1400137da  mov     ecx, ebx; this
0x1400137dc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400137e1  jmp     loc_140013AE6
0x1400137e6  mov     edx, dword ptr [rbp+3Fh+var_80+4]
0x1400137e9  mov     ecx, 4
0x1400137ee  test    edx, edx
0x1400137f0  jz      loc_140013887
0x1400137f6  mov     eax, dword ptr [rbp+3Fh+var_80+8]
0x1400137f9  lea     r8d, [rcx-3]
0x1400137fd  and     eax, ecx
0x1400137ff  cmp     edx, r8d
0x140013802  jnz     short loc_14001382D
0x140013804  test    eax, eax
0x140013806  jz      short loc_14001381C
0x140013808  lea     rdx, [rbp+3Fh+var_70]
0x14001380c  mov     rcx, r14
0x14001380f  call    ?OverwriteTombstone@CreateContext@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::CreateContext::OverwriteTombstone(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x140013814  mov     ebx, r15d
0x140013817  jmp     loc_140013AE6
0x14001381c  mov     dword ptr [rsi+18h], 0C0000035h
0x140013823  mov     [rsi+20h], r15
0x140013827  mov     [r12], ecx
0x14001382b  jmp     short loc_140013814
0x14001382d  test    eax, eax
0x14001382f  jz      short loc_14001383A
0x140013831  mov     dword ptr [rsi+18h], 0C000003Ah
0x140013838  jmp     short loc_140013823
0x14001383a  cmp     dword ptr [rbp+3Fh+var_58], r8d
0x14001383e  jnz     short loc_14001384C
0x140013840  mov     rax, [r14+0A0h]
0x140013847  or      dword ptr [rax], 8
0x14001384a  jmp     short loc_140013814
0x14001384c  mov     rcx, [rbp+3Fh+Resource]; Resource
0x140013850  mov     [rbp+3Fh+Resource], r15
0x140013854  test    rcx, rcx
0x140013857  jz      short loc_140013871
0x140013859  call    cs:__imp_ExReleaseResourceLite
0x140013860  nop     dword ptr [rax+rax+00h]
0x140013865  call    cs:__imp_KeLeaveCriticalRegion
0x14001386c  nop     dword ptr [rax+rax+00h]
0x140013871  mov     rcx, [rbp+3Fh+var_70+8]; this
0x140013875  mov     [rbp+3Fh+var_70], r15
0x140013879  mov     [rbp+3Fh+var_70+8], r15
0x14001387d  test    rcx, rcx
0x140013880  jz      short loc_140013887
0x140013882  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013887  cmp     dword ptr [rbp+3Fh+var_58], 2
0x14001388b  mov     [rbp+3Fh+P], r15
0x14001388f  jnz     loc_140013943
0x140013895  mov     rax, qword ptr [rbp+3Fh+var_50+8]
0x140013899  lea     r8, [rbp+3Fh+Source]; Source
0x14001389d  mov     rcx, [r14]
0x1400138a0  lea     rdx, [rbp+3Fh+var_90]; struct _UNICODE_STRING *
0x1400138a4  add     rcx, 8; this
0x1400138a8  mov     [rsp+0F0h+var_C8], rdi; char *
0x1400138ad  movzx   r9d, word ptr [rax+18h]
0x1400138b2  movups  xmm0, xmmword ptr [rax]
0x1400138b5  mov     rax, qword ptr [rbp+3Fh+var_50]
0x1400138b9  movdqu  xmmword ptr [rbp+3Fh+Source.Length], xmm0
0x1400138be  movups  xmm1, xmmword ptr [rax]
0x1400138c1  lea     rax, [rbp+3Fh+P]
0x1400138c5  mov     [rsp+0F0h+var_D0], rax; P
0x1400138ca  movdqu  xmmword ptr [rbp+3Fh+var_90.Length], xmm1
0x1400138cf  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400138d4  mov     r15d, eax
0x1400138d7  test    eax, eax
0x1400138d9  jns     short loc_14001393A
0x1400138db  lea     rax, aPushReplacingS_3; "PUSH: Replacing substring"
0x1400138e2  mov     r8, 38000020783h; struct UnionFs::StackEventTracer *
0x1400138ec  lea     r9, aUnionfsUnionfs_50; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x1400138f3  mov     [rsp+0F0h+var_D0], rax; char *
0x1400138f8  mov     rdx, rdi; int
0x1400138fb  mov     ecx, r15d; this
0x1400138fe  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013903  mov     rbx, [rbp+3Fh+P]
0x140013907  test    rbx, rbx
0x14001390a  jz      loc_140013814
0x140013910  cmp     byte ptr [rbx+10h], 0
0x140013914  jnz     short loc_14001391C
0x140013916  xorps   xmm0, xmm0
0x140013919  movups  xmmword ptr [rbx], xmm0
0x14001391c  mov     rcx, rbx; UnicodeString
0x14001391f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140013924  xor     edx, edx; Tag
0x140013926  mov     rcx, rbx; P
0x140013929  call    cs:__imp_ExFreePoolWithTag
0x140013930  nop     dword ptr [rax+rax+00h]
0x140013935  jmp     loc_140013814
0x14001393a  mov     rax, [rbp+3Fh+P]
0x14001393e  test    rax, rax
0x140013941  jnz     short loc_140013970
0x140013943  mov     rcx, [r14]
0x140013946  lea     rdx, [rbp+3Fh+P]
0x14001394a  mov     r8, rdi
0x14001394d  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140013952  mov     r15d, eax
0x140013955  test    eax, eax
0x140013957  jns     short loc_14001396C
0x140013959  lea     rax, aPushAllocating_13; "PUSH: Allocating scratch path for layer"...
0x140013960  mov     r8, 3900002078Eh
0x14001396a  jmp     short loc_1400138EC
0x14001396c  mov     rax, [rbp+3Fh+P]
0x140013970  mov     rcx, [r14+0A0h]
0x140013977  mov     rbx, [rcx+40h]
0x14001397b  mov     [rcx+40h], rax
0x14001397f  test    rbx, rbx
0x140013982  jz      short loc_1400139A9
0x140013984  cmp     byte ptr [rbx+10h], 0
0x140013988  jnz     short loc_140013990
0x14001398a  xorps   xmm0, xmm0
0x14001398d  movups  xmmword ptr [rbx], xmm0
0x140013990  mov     rcx, rbx; UnicodeString
0x140013993  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140013998  xor     edx, edx; Tag
0x14001399a  mov     rcx, rbx; P
0x14001399d  call    cs:__imp_ExFreePoolWithTag
0x1400139a4  nop     dword ptr [rax+rax+00h]
0x1400139a9  lea     rcx, [rbp+3Fh+P]
0x1400139ad  call    ??$make_unique@UFindAndStatResults@UnionFs@@$$V$0A@@utl@@YA?AV?$unique_ptr@UFindAndStatResults@UnionFs@@U?$default_delete@UFindAndStatResults@UnionFs@@@utl@@@0@XZ; utl::make_unique<UnionFs::FindAndStatResults,,0>(void)
0x1400139b2  mov     rbx, [rbp+3Fh+P]
0x1400139b6  test    rbx, rbx
0x1400139b9  jnz     short loc_1400139EC
0x1400139bb  lea     rax, aOriginAllocati_60; "ORIGIN: Allocating findAndStatResults"
0x1400139c2  mov     ebx, 0C000009Ah
0x1400139c7  mov     ecx, ebx; this
0x1400139c9  mov     [rsp+0F0h+var_D0], rax; char *
0x1400139ce  lea     r9, aUnionfsUnionfs_50; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x1400139d5  mov     r8, 3FB00020798h; struct UnionFs::StackEventTracer *
0x1400139df  mov     rdx, rdi; int
0x1400139e2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400139e7  jmp     loc_140013AE6
0x1400139ec  mov     r9, [r14+0A0h]
0x1400139f3  lea     r8, [rbp+3Fh+var_90]
0x1400139f7  mov     rcx, [r14+8]
0x1400139fb  mov     rdx, rsi
0x1400139fe  mov     [rsp+0F0h+var_C0], rdi
0x140013a03  mov     [rsp+0F0h+var_C8], rbx; char *
0x140013a08  mov     rax, [r9+40h]
0x140013a0c  movups  xmm0, xmmword ptr [rax]
0x140013a0f  movdqu  xmmword ptr [rbp+3Fh+var_90.Length], xmm0
0x140013a14  call    ?FindAndStatItemInLayersAsCaller@UfsUnionCtx@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEBVUfsStreamHandleCtx@2@W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &)
0x140013a19  mov     r15d, eax
0x140013a1c  test    eax, eax
0x140013a1e  jns     short loc_140013A68
0x140013a20  lea     rax, aPushProbingFor; "PUSH: Probing for item in layers"
0x140013a27  mov     r8, 0E4000207A2h; struct UnionFs::StackEventTracer *
0x140013a31  lea     r9, aUnionfsUnionfs_50; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x140013a38  mov     [rsp+0F0h+var_D0], rax; char *
0x140013a3d  mov     rdx, rdi; int
0x140013a40  mov     ecx, r15d; this
0x140013a43  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013a48  test    rbx, rbx
0x140013a4b  jz      loc_140013814
0x140013a51  mov     rcx, [rbx+58h]; this
0x140013a55  test    rcx, rcx
0x140013a58  jz      loc_140013924
0x140013a5e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013a63  jmp     loc_140013924
0x140013a68  cmp     r15d, 104h
0x140013a6f  jnz     short loc_140013A9C
0x140013a71  test    rbx, rbx
0x140013a74  jz      short loc_140013A95
0x140013a76  mov     rcx, [rbx+58h]; this
0x140013a7a  test    rcx, rcx
0x140013a7d  jz      short loc_140013A84
0x140013a7f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013a84  xor     edx, edx; Tag
0x140013a86  mov     rcx, rbx; P
0x140013a89  call    cs:__imp_ExFreePoolWithTag
0x140013a90  nop     dword ptr [rax+rax+00h]
0x140013a95  mov     ebx, 104h
0x140013a9a  jmp     short loc_140013AE6
0x140013a9c  movzx   eax, word ptr [rbx]
0x140013a9f  mov     ecx, 1
0x140013aa4  cmp     ax, cx
0x140013aa7  jnz     short loc_140013B06
0x140013aa9  mov     dword ptr [rsi+18h], 0C0000035h
0x140013ab0  mov     qword ptr [rsi+20h], 0
0x140013ab8  mov     dword ptr [r12], 4
0x140013ac0  test    rbx, rbx
0x140013ac3  jz      short loc_140013AE4
0x140013ac5  mov     rcx, [rbx+58h]; this
0x140013ac9  test    rcx, rcx
0x140013acc  jz      short loc_140013AD3
0x140013ace  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013ad3  xor     edx, edx; Tag
0x140013ad5  mov     rcx, rbx; P
0x140013ad8  call    cs:__imp_ExFreePoolWithTag
0x140013adf  nop     dword ptr [rax+rax+00h]
0x140013ae4  xor     ebx, ebx
0x140013ae6  lea     rcx, [rbp+3Fh+var_80]; this
0x140013aea  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140013aef  mov     eax, ebx
0x140013af1  add     rsp, 0B8h
0x140013af8  pop     r15
0x140013afa  pop     r14
0x140013afc  pop     r13
0x140013afe  pop     r12
0x140013b00  pop     rdi
0x140013b01  pop     rsi
0x140013b02  pop     rbx
0x140013b03  pop     rbp
0x140013b04  retn
0x140013b06  mov     ecx, 3
0x140013b0b  cmp     ax, cx
0x140013b0e  jnz     short loc_140013AC0
0x140013b10  mov     rcx, [r14+0A0h]
0x140013b17  mov     r8, r13; struct _FLT_RELATED_OBJECTS *
0x140013b1a  mov     rax, [rbp+3Fh+arg_30]
0x140013b1e  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x140013b21  mov     r9, [r14]; struct _FLT_FILE_NAME_INFORMATION *
0x140013b24  mov     [rsp+0F0h+var_B0], rax; struct UnionFs::UfsSiloCtx *
0x140013b29  mov     rax, [rbx+50h]
0x140013b2d  mov     [rsp+0F0h+var_B8], rdi; struct UnionFs::StackEventTracer *
0x140013b32  mov     [rsp+0F0h+var_C0], rax; struct UnionFs::UfsLayerCtx *
0x140013b37  mov     rax, [rcx+40h]
0x140013b3b  mov     [rsp+0F0h+var_C8], rcx; char *
0x140013b40  mov     rcx, [r14+8]; this
0x140013b44  mov     [rsp+0F0h+var_D0], rax; struct UnionFs::UfsPathName *
0x140013b49  call    ?EnsureParentPathInScratch@UfsUnionCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBU_FLT_FILE_NAME_INFORMATION@@AEBVUfsPathName@2@AEBVUfsStreamHandleCtx@2@AEBVUfsLayerCtx@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z; UnionFs::UfsUnionCtx::EnsureParentPathInScratch(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,_FLT_FILE_NAME_INFORMATION const &,UnionFs::UfsPathName const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsLayerCtx const &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)
0x140013b4e  mov     esi, eax
0x140013b50  test    eax, eax
0x140013b52  jns     loc_140013AC0
0x140013b58  lea     rax, aPushPreparingF_0; "PUSH: Preparing for scratch create"
0x140013b5f  mov     r8, 0E5000207BFh; struct UnionFs::StackEventTracer *
0x140013b69  lea     r9, aUnionfsUnionfs_50; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x140013b70  mov     [rsp+0F0h+var_D0], rax; char *
0x140013b75  mov     rdx, rdi; int
0x140013b78  mov     ecx, esi; this
0x140013b7a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013b7f  test    rbx, rbx
0x140013b82  jz      short loc_140013BA3
0x140013b84  mov     rcx, [rbx+58h]; this
0x140013b88  test    rcx, rcx
0x140013b8b  jz      short loc_140013B92
0x140013b8d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013b92  xor     edx, edx; Tag
0x140013b94  mov     rcx, rbx; P
0x140013b97  call    cs:__imp_ExFreePoolWithTag
0x140013b9e  nop     dword ptr [rax+rax+00h]
0x140013ba3  mov     ebx, esi
0x140013ba5  jmp     loc_140013AE6
```
