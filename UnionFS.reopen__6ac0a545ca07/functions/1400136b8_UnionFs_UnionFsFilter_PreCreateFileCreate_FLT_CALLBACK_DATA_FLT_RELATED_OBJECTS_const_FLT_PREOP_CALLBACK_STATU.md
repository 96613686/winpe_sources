# UnionFs::UnionFsFilter::PreCreateFileCreate(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x1400136b8`
- end: `0x140013b5a`
- name: `?PreCreateFileCreate@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `1186`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140011e20`

## callees

- `0x14000c1dc`
- `0x14000f81c`
- `0x140010ba8`
- `0x1400111b8`
- `0x1400136b8`
- `0x14003cea8`
- `0x140043afc`
- `0x140044074`
- `0x140056c44`
- `0x140056c7c`
- `0x140061058`
- `0x14006127c`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400138d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001394d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001394d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b47`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013809`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013809`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013815`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013815`

## string_xrefs

- `0x14001376a`: `PUSH: Cache lookup`
- `0x140013909`: `PUSH: Allocating scratch path for layer lookup`
- `0x140013b08`: `PUSH: Preparing for scratch create`
- `0x14001377b`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x14001389c`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x14001397e`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x1400139e1`: `UnionFs::UnionFsFilter::PreCreateFileCreate`
- `0x140013b19`: `UnionFs::UnionFsFilter::PreCreateFileCreate`

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
      (struct UnionFs::StackEventTracer *)0x20F00020729LL,
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
    v24 = 0x38000020773LL;
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
      v24 = 0x3900002077ELL;
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
      (struct UnionFs::StackEventTracer *)0x3FB00020788LL,
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
      (struct UnionFs::StackEventTracer *)0xE400020792LL,
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
    (struct UnionFs::StackEventTracer *)0xE5000207AFLL,
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
0x1400136b8  mov     [rsp-8+P], rcx
0x1400136bd  push    rbp
0x1400136be  push    rbx
0x1400136bf  push    rsi
0x1400136c0  push    rdi
0x1400136c1  push    r12
0x1400136c3  push    r13
0x1400136c5  push    r14
0x1400136c7  push    r15
0x1400136c9  lea     rbp, [rsp-7]
0x1400136ce  sub     rsp, 0B8h
0x1400136d5  mov     rax, [r8+20h]
0x1400136d9  xor     r15d, r15d
0x1400136dc  mov     r14, [rbp+3Fh+arg_20]
0x1400136e0  mov     r12, r9
0x1400136e3  mov     [r9], r15d
0x1400136e6  xorps   xmm1, xmm1
0x1400136e9  xorps   xmm0, xmm0
0x1400136ec  mov     r13, r8
0x1400136ef  mov     r9d, [rax+50h]
0x1400136f3  mov     rsi, rdx
0x1400136f6  shr     r9d, 11h
0x1400136fa  movd    eax, xmm1
0x1400136fe  not     r9d
0x140013701  movdqa  [rbp+3Fh+var_80], xmm1
0x140013706  and     r9d, 1
0x14001370a  movdqa  xmmword ptr [rbp+3Fh+var_70], xmm0
0x14001370f  or      eax, 3
0x140013712  mov     [rbp+3Fh+Resource], r15
0x140013716  mov     dword ptr [rbp+3Fh+var_80], eax
0x140013719  mov     rax, [r14+8]
0x14001371d  mov     [rbp+3Fh+var_58], r15
0x140013721  movdqa  [rbp+3Fh+var_50], xmm0
0x140013726  cmp     dword ptr [rax+1Ch], 2
0x14001372a  jnz     short loc_140013736
0x14001372c  mov     rax, [rax+20h]
0x140013730  mov     rcx, [rax+10h]
0x140013734  jmp     short loc_140013741
0x140013736  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001373d  mov     rcx, [rax+50h]
0x140013741  mov     rdi, [rbp+3Fh+arg_28]
0x140013745  lea     rax, [rbp+3Fh+var_80]
0x140013749  mov     r8, [r14]
0x14001374c  mov     rdx, [r13+18h]
0x140013750  mov     [rsp+0F0h+var_C0], rsi
0x140013755  mov     [rsp+0F0h+var_C8], rdi; char *
0x14001375a  mov     [rsp+0F0h+var_D0], rax
0x14001375f  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140013764  mov     ebx, eax
0x140013766  test    eax, eax
0x140013768  jns     short loc_140013796
0x14001376a  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x140013771  mov     r8, 20F00020729h; struct UnionFs::StackEventTracer *
0x14001377b  lea     r9, aUnionfsUnionfs_51; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x140013782  mov     [rsp+0F0h+var_D0], rax; char *
0x140013787  mov     rdx, rdi; int
0x14001378a  mov     ecx, ebx; this
0x14001378c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013791  jmp     loc_140013A96
0x140013796  mov     edx, dword ptr [rbp+3Fh+var_80+4]
0x140013799  mov     ecx, 4
0x14001379e  test    edx, edx
0x1400137a0  jz      loc_140013837
0x1400137a6  mov     eax, dword ptr [rbp+3Fh+var_80+8]
0x1400137a9  lea     r8d, [rcx-3]
0x1400137ad  and     eax, ecx
0x1400137af  cmp     edx, r8d
0x1400137b2  jnz     short loc_1400137DD
0x1400137b4  test    eax, eax
0x1400137b6  jz      short loc_1400137CC
0x1400137b8  lea     rdx, [rbp+3Fh+var_70]
0x1400137bc  mov     rcx, r14
0x1400137bf  call    ?OverwriteTombstone@CreateContext@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::CreateContext::OverwriteTombstone(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x1400137c4  mov     ebx, r15d
0x1400137c7  jmp     loc_140013A96
0x1400137cc  mov     dword ptr [rsi+18h], 0C0000035h
0x1400137d3  mov     [rsi+20h], r15
0x1400137d7  mov     [r12], ecx
0x1400137db  jmp     short loc_1400137C4
0x1400137dd  test    eax, eax
0x1400137df  jz      short loc_1400137EA
0x1400137e1  mov     dword ptr [rsi+18h], 0C000003Ah
0x1400137e8  jmp     short loc_1400137D3
0x1400137ea  cmp     dword ptr [rbp+3Fh+var_58], r8d
0x1400137ee  jnz     short loc_1400137FC
0x1400137f0  mov     rax, [r14+0A0h]
0x1400137f7  or      dword ptr [rax], 8
0x1400137fa  jmp     short loc_1400137C4
0x1400137fc  mov     rcx, [rbp+3Fh+Resource]; Resource
0x140013800  mov     [rbp+3Fh+Resource], r15
0x140013804  test    rcx, rcx
0x140013807  jz      short loc_140013821
0x140013809  call    cs:__imp_ExReleaseResourceLite
0x140013810  nop     dword ptr [rax+rax+00h]
0x140013815  call    cs:__imp_KeLeaveCriticalRegion
0x14001381c  nop     dword ptr [rax+rax+00h]
0x140013821  mov     rcx, [rbp+3Fh+var_70+8]; this
0x140013825  mov     [rbp+3Fh+var_70], r15
0x140013829  mov     [rbp+3Fh+var_70+8], r15
0x14001382d  test    rcx, rcx
0x140013830  jz      short loc_140013837
0x140013832  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013837  cmp     dword ptr [rbp+3Fh+var_58], 2
0x14001383b  mov     [rbp+3Fh+P], r15
0x14001383f  jnz     loc_1400138F3
0x140013845  mov     rax, qword ptr [rbp+3Fh+var_50+8]
0x140013849  lea     r8, [rbp+3Fh+Source]; Source
0x14001384d  mov     rcx, [r14]
0x140013850  lea     rdx, [rbp+3Fh+var_90]; struct _UNICODE_STRING *
0x140013854  add     rcx, 8; this
0x140013858  mov     [rsp+0F0h+var_C8], rdi; char *
0x14001385d  movzx   r9d, word ptr [rax+18h]
0x140013862  movups  xmm0, xmmword ptr [rax]
0x140013865  mov     rax, qword ptr [rbp+3Fh+var_50]
0x140013869  movdqu  xmmword ptr [rbp+3Fh+Source.Length], xmm0
0x14001386e  movups  xmm1, xmmword ptr [rax]
0x140013871  lea     rax, [rbp+3Fh+P]
0x140013875  mov     [rsp+0F0h+var_D0], rax; P
0x14001387a  movdqu  xmmword ptr [rbp+3Fh+var_90.Length], xmm1
0x14001387f  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140013884  mov     r15d, eax
0x140013887  test    eax, eax
0x140013889  jns     short loc_1400138EA
0x14001388b  lea     rax, aPushReplacingS_3; "PUSH: Replacing substring"
0x140013892  mov     r8, 38000020773h; struct UnionFs::StackEventTracer *
0x14001389c  lea     r9, aUnionfsUnionfs_51; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x1400138a3  mov     [rsp+0F0h+var_D0], rax; char *
0x1400138a8  mov     rdx, rdi; int
0x1400138ab  mov     ecx, r15d; this
0x1400138ae  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400138b3  mov     rbx, [rbp+3Fh+P]
0x1400138b7  test    rbx, rbx
0x1400138ba  jz      loc_1400137C4
0x1400138c0  cmp     byte ptr [rbx+10h], 0
0x1400138c4  jnz     short loc_1400138CC
0x1400138c6  xorps   xmm0, xmm0
0x1400138c9  movups  xmmword ptr [rbx], xmm0
0x1400138cc  mov     rcx, rbx; UnicodeString
0x1400138cf  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400138d4  xor     edx, edx; Tag
0x1400138d6  mov     rcx, rbx; P
0x1400138d9  call    cs:__imp_ExFreePoolWithTag
0x1400138e0  nop     dword ptr [rax+rax+00h]
0x1400138e5  jmp     loc_1400137C4
0x1400138ea  mov     rax, [rbp+3Fh+P]
0x1400138ee  test    rax, rax
0x1400138f1  jnz     short loc_140013920
0x1400138f3  mov     rcx, [r14]
0x1400138f6  lea     rdx, [rbp+3Fh+P]
0x1400138fa  mov     r8, rdi
0x1400138fd  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140013902  mov     r15d, eax
0x140013905  test    eax, eax
0x140013907  jns     short loc_14001391C
0x140013909  lea     rax, aPushAllocating_13; "PUSH: Allocating scratch path for layer"...
0x140013910  mov     r8, 3900002077Eh
0x14001391a  jmp     short loc_14001389C
0x14001391c  mov     rax, [rbp+3Fh+P]
0x140013920  mov     rcx, [r14+0A0h]
0x140013927  mov     rbx, [rcx+40h]
0x14001392b  mov     [rcx+40h], rax
0x14001392f  test    rbx, rbx
0x140013932  jz      short loc_140013959
0x140013934  cmp     byte ptr [rbx+10h], 0
0x140013938  jnz     short loc_140013940
0x14001393a  xorps   xmm0, xmm0
0x14001393d  movups  xmmword ptr [rbx], xmm0
0x140013940  mov     rcx, rbx; UnicodeString
0x140013943  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140013948  xor     edx, edx; Tag
0x14001394a  mov     rcx, rbx; P
0x14001394d  call    cs:__imp_ExFreePoolWithTag
0x140013954  nop     dword ptr [rax+rax+00h]
0x140013959  lea     rcx, [rbp+3Fh+P]
0x14001395d  call    ??$make_unique@UFindAndStatResults@UnionFs@@$$V$0A@@utl@@YA?AV?$unique_ptr@UFindAndStatResults@UnionFs@@U?$default_delete@UFindAndStatResults@UnionFs@@@utl@@@0@XZ; utl::make_unique<UnionFs::FindAndStatResults,,0>(void)
0x140013962  mov     rbx, [rbp+3Fh+P]
0x140013966  test    rbx, rbx
0x140013969  jnz     short loc_14001399C
0x14001396b  lea     rax, aOriginAllocati_61; "ORIGIN: Allocating findAndStatResults"
0x140013972  mov     ebx, 0C000009Ah
0x140013977  mov     ecx, ebx; this
0x140013979  mov     [rsp+0F0h+var_D0], rax; char *
0x14001397e  lea     r9, aUnionfsUnionfs_51; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x140013985  mov     r8, 3FB00020788h; struct UnionFs::StackEventTracer *
0x14001398f  mov     rdx, rdi; int
0x140013992  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013997  jmp     loc_140013A96
0x14001399c  mov     r9, [r14+0A0h]
0x1400139a3  lea     r8, [rbp+3Fh+var_90]
0x1400139a7  mov     rcx, [r14+8]
0x1400139ab  mov     rdx, rsi
0x1400139ae  mov     [rsp+0F0h+var_C0], rdi
0x1400139b3  mov     [rsp+0F0h+var_C8], rbx; char *
0x1400139b8  mov     rax, [r9+40h]
0x1400139bc  movups  xmm0, xmmword ptr [rax]
0x1400139bf  movdqu  xmmword ptr [rbp+3Fh+var_90.Length], xmm0
0x1400139c4  call    ?FindAndStatItemInLayersAsCaller@UfsUnionCtx@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEBVUfsStreamHandleCtx@2@W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &)
0x1400139c9  mov     r15d, eax
0x1400139cc  test    eax, eax
0x1400139ce  jns     short loc_140013A18
0x1400139d0  lea     rax, aPushProbingFor; "PUSH: Probing for item in layers"
0x1400139d7  mov     r8, 0E400020792h; struct UnionFs::StackEventTracer *
0x1400139e1  lea     r9, aUnionfsUnionfs_51; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x1400139e8  mov     [rsp+0F0h+var_D0], rax; char *
0x1400139ed  mov     rdx, rdi; int
0x1400139f0  mov     ecx, r15d; this
0x1400139f3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400139f8  test    rbx, rbx
0x1400139fb  jz      loc_1400137C4
0x140013a01  mov     rcx, [rbx+58h]; this
0x140013a05  test    rcx, rcx
0x140013a08  jz      loc_1400138D4
0x140013a0e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013a13  jmp     loc_1400138D4
0x140013a18  cmp     r15d, 104h
0x140013a1f  jnz     short loc_140013A4C
0x140013a21  test    rbx, rbx
0x140013a24  jz      short loc_140013A45
0x140013a26  mov     rcx, [rbx+58h]; this
0x140013a2a  test    rcx, rcx
0x140013a2d  jz      short loc_140013A34
0x140013a2f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013a34  xor     edx, edx; Tag
0x140013a36  mov     rcx, rbx; P
0x140013a39  call    cs:__imp_ExFreePoolWithTag
0x140013a40  nop     dword ptr [rax+rax+00h]
0x140013a45  mov     ebx, 104h
0x140013a4a  jmp     short loc_140013A96
0x140013a4c  movzx   eax, word ptr [rbx]
0x140013a4f  mov     ecx, 1
0x140013a54  cmp     ax, cx
0x140013a57  jnz     short loc_140013AB6
0x140013a59  mov     dword ptr [rsi+18h], 0C0000035h
0x140013a60  mov     qword ptr [rsi+20h], 0
0x140013a68  mov     dword ptr [r12], 4
0x140013a70  test    rbx, rbx
0x140013a73  jz      short loc_140013A94
0x140013a75  mov     rcx, [rbx+58h]; this
0x140013a79  test    rcx, rcx
0x140013a7c  jz      short loc_140013A83
0x140013a7e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013a83  xor     edx, edx; Tag
0x140013a85  mov     rcx, rbx; P
0x140013a88  call    cs:__imp_ExFreePoolWithTag
0x140013a8f  nop     dword ptr [rax+rax+00h]
0x140013a94  xor     ebx, ebx
0x140013a96  lea     rcx, [rbp+3Fh+var_80]; this
0x140013a9a  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140013a9f  mov     eax, ebx
0x140013aa1  add     rsp, 0B8h
0x140013aa8  pop     r15
0x140013aaa  pop     r14
0x140013aac  pop     r13
0x140013aae  pop     r12
0x140013ab0  pop     rdi
0x140013ab1  pop     rsi
0x140013ab2  pop     rbx
0x140013ab3  pop     rbp
0x140013ab4  retn
0x140013ab6  mov     ecx, 3
0x140013abb  cmp     ax, cx
0x140013abe  jnz     short loc_140013A70
0x140013ac0  mov     rcx, [r14+0A0h]
0x140013ac7  mov     r8, r13; struct _FLT_RELATED_OBJECTS *
0x140013aca  mov     rax, [rbp+3Fh+arg_30]
0x140013ace  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x140013ad1  mov     r9, [r14]; struct _FLT_FILE_NAME_INFORMATION *
0x140013ad4  mov     [rsp+0F0h+var_B0], rax; struct UnionFs::UfsSiloCtx *
0x140013ad9  mov     rax, [rbx+50h]
0x140013add  mov     [rsp+0F0h+var_B8], rdi; struct UnionFs::StackEventTracer *
0x140013ae2  mov     [rsp+0F0h+var_C0], rax; struct UnionFs::UfsLayerCtx *
0x140013ae7  mov     rax, [rcx+40h]
0x140013aeb  mov     [rsp+0F0h+var_C8], rcx; char *
0x140013af0  mov     rcx, [r14+8]; this
0x140013af4  mov     [rsp+0F0h+var_D0], rax; struct UnionFs::UfsPathName *
0x140013af9  call    ?EnsureParentPathInScratch@UfsUnionCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBU_FLT_FILE_NAME_INFORMATION@@AEBVUfsPathName@2@AEBVUfsStreamHandleCtx@2@AEBVUfsLayerCtx@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z; UnionFs::UfsUnionCtx::EnsureParentPathInScratch(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,_FLT_FILE_NAME_INFORMATION const &,UnionFs::UfsPathName const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsLayerCtx const &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)
0x140013afe  mov     esi, eax
0x140013b00  test    eax, eax
0x140013b02  jns     loc_140013A70
0x140013b08  lea     rax, aPushPreparingF_0; "PUSH: Preparing for scratch create"
0x140013b0f  mov     r8, 0E5000207AFh; struct UnionFs::StackEventTracer *
0x140013b19  lea     r9, aUnionfsUnionfs_51; "UnionFs::UnionFsFilter::PreCreateFileCr"...
0x140013b20  mov     [rsp+0F0h+var_D0], rax; char *
0x140013b25  mov     rdx, rdi; int
0x140013b28  mov     ecx, esi; this
0x140013b2a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013b2f  test    rbx, rbx
0x140013b32  jz      short loc_140013B53
0x140013b34  mov     rcx, [rbx+58h]; this
0x140013b38  test    rcx, rcx
0x140013b3b  jz      short loc_140013B42
0x140013b3d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013b42  xor     edx, edx; Tag
0x140013b44  mov     rcx, rbx; P
0x140013b47  call    cs:__imp_ExFreePoolWithTag
0x140013b4e  nop     dword ptr [rax+rax+00h]
0x140013b53  mov     ebx, esi
0x140013b55  jmp     loc_140013A96
```
