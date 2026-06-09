# UnionFs::UfsUnionCtx::InsertTombstonesFromConfig(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &)

- ea: `0x140061880`
- end: `0x140061f26`
- name: `?InsertTombstonesFromConfig@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@@Z`
- size: `1702`
- prototype: `int(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140062e54`

## callees

- `0x14000f7fc`
- `0x140036128`
- `0x14003c734`
- `0x140041040`
- `0x1400438e4`
- `0x1400445d8`
- `0x140056ac4`
- `0x140056afc`
- `0x140061880`
- `0x14006fc84`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140061913`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061dd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061e82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061f03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061913`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061dd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061e82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061f03`
- `ntoskrnl!KeSetEvent` at `0x140061ebb`
- `ntoskrnl!KeSetEvent` at `0x140061ebb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061bfd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061cc0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061d6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061bfd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061cc0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061d6e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061c09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061ccc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061d7a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061c09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061ccc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061d7a`

## string_xrefs

- `0x14006193e`: `UnionConfig.TombstoneEntryCount == tombstoneIds.size()`
- `0x1400618ec`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061c46`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061c8f`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061d3f`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061df6`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061e2f`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061c35`: `PUSH: ComputeCombinedPathLength - originalPath`
- `0x140061e1e`: `PUSH: ComputeCombinedPathLength - tombstonePath`
- `0x140061c7c`: `ORIGIN: Rejected tombstone insertion at FS metadata path.`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::InsertTombstonesFromConfig(
        UnionFs::UfsUnionCtx *this,
        const struct UFS_MSG_CREATE_CONFIG_UNION *a2,
        unsigned int a3,
        struct UnionFs::StackEventTracer *a4)
{
  unsigned int TombstoneListFromConfig; // ebx
  PVOID v8; // rcx
  _WORD *v10; // rdi
  unsigned __int64 *v11; // rdx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rbx
  UnionFs::UfsLayerCtx *v14; // r14
  unsigned __int16 v15; // r14
  unsigned __int16 v16; // r8
  struct _UNICODE_STRING *v17; // rdx
  _WORD *i; // rbx
  __int64 v19; // rdx
  int inited; // r14d
  unsigned __int16 v21; // r12
  __int64 v22; // rdx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  bool v24; // zf
  __int64 v25; // r12
  unsigned __int64 *v26; // rdx
  __int64 *v27; // rax
  volatile signed __int32 *v28; // r14
  FsFltWil::Details *v29; // rcx
  int inserted; // r12d
  struct _UNICODE_STRING *v31; // rdx
  struct _UNICODE_STRING *v32; // rdx
  struct _UNICODE_STRING *v33; // rdx
  struct _UNICODE_STRING *v34; // rdx
  struct _UNICODE_STRING *v35; // rdx
  struct _UNICODE_STRING *v36; // rdx
  _QWORD *v37; // rax
  __int64 v38; // rcx
  struct _UNICODE_STRING *v39; // rdx
  const char *v40; // [rsp+28h] [rbp-D8h]
  char *v41; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING v42; // [rsp+40h] [rbp-C0h] BYREF
  FsFltWil::Details *v43; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v44; // [rsp+58h] [rbp-A8h] BYREF
  char v45[8]; // [rsp+68h] [rbp-98h] BYREF
  PERESOURCE Resource[2]; // [rsp+70h] [rbp-90h]
  utl::_RefCountBase *v47; // [rsp+80h] [rbp-80h]
  __int64 v48; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING v49; // [rsp+90h] [rbp-70h] BYREF
  char v50; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING UnicodeString; // [rsp+D0h] [rbp-30h] BYREF
  char v52; // [rsp+E0h] [rbp-20h]
  PVOID P[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v54; // [rsp+120h] [rbp+20h]
  __int64 v55; // [rsp+128h] [rbp+28h]
  UnionFs::UfsUnionCtx *v56; // [rsp+130h] [rbp+30h] BYREF
  utl::_RefCountBase *v57; // [rsp+138h] [rbp+38h]
  FsFltWil::Details *v58; // [rsp+198h] [rbp+98h] BYREF

  if ( !*((_DWORD *)a2 + 3) )
    return 0;
  v54 = -1;
  *(__m128i *)P = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  TombstoneListFromConfig = UnionFs::Utils::GetTombstoneListFromConfig(a2, a3, P);
  if ( (TombstoneListFromConfig & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)TombstoneListFromConfig,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0xA500200D4DLL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::InsertTombstonesFromConfig",
      "PUSH: Getting layer list",
      v40);
    v8 = P[0];
    if ( P[0] != (PVOID)-1LL && P[0] )
LABEL_5:
      ExFreePoolWithTag(v8, 0);
    return TombstoneListFromConfig;
  }
  v10 = P[0];
  if ( *((_DWORD *)a2 + 3) != ((char *)P[1] - (char *)P[0]) >> 4 )
    MicrosoftTelemetryAssertTriggeredMsgKM("UnionConfig.TombstoneEntryCount == tombstoneIds.size()");
  v44 = 0;
  FsFltWil::AcquirePushLockShared(&v58, (char *)this + 72);
  v12 = *((_QWORD *)this + 6);
  v13 = *(volatile signed __int32 **)(v12 + 8);
  v14 = *(UnionFs::UfsLayerCtx **)v12;
  if ( v13 )
    _InterlockedIncrement(v13 + 2);
  if ( v58 )
    FsFltWil::Details::ReleasePushLockShared(v58, v11);
  LOWORD(v58) = UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v14, &v44, 1);
  v15 = (unsigned __int16)v58;
  if ( v13 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v13);
  UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)&v49, &v44, v15);
  UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)&UnicodeString, &v44, v16);
  for ( i = v10; ; i += 8 )
  {
    if ( i == P[1] )
    {
      v37 = UnionFs::g_FilterState;
      *((_BYTE *)this + 208) = 1;
      v38 = v37[15];
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 8), 1u) )
        KeSetEvent((PRKEVENT)(v38 + 16), 0, 0);
      if ( !v52 )
        UnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v17);
      if ( !v50 )
        v49 = 0;
      FsFltWil::Details::FreeUnicodeString(&v49, v39);
      if ( v10 != (_WORD *)-1LL && v10 )
        ExFreePoolWithTag(v10, 0);
      return 0;
    }
    v19 = *(_QWORD *)i;
    v42 = 0;
    v42.MaximumLength = *(_WORD *)(v19 + 4) - *(_WORD *)(v19 + 2);
    v42.Length = v42.MaximumLength;
    v42.Buffer = (PWSTR)(*(unsigned __int16 *)(v19 + 2) + v19 + 6);
    inited = UnionFs::UfsPathName::CombinePath((UnionFs::UfsPathName *)&v49, &v44, &v42, v15, a4);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x30200200D66LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::InsertTombstonesFromConfig",
        "PUSH: ComputeCombinedPathLength - tombstonePath",
        v40);
LABEL_76:
      if ( !v52 )
        UnicodeString = 0;
LABEL_78:
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v31);
      if ( !v50 )
        v49 = 0;
      FsFltWil::Details::FreeUnicodeString(&v49, v36);
      if ( v10 != (_WORD *)-1LL && v10 )
        ExFreePoolWithTag(v10, 0);
      return (unsigned int)inited;
    }
    v21 = i[4];
    if ( v21 == 4 )
    {
      v42 = 0;
      i += 8;
      v22 = *(_QWORD *)i;
      v42.MaximumLength = *(_WORD *)(*(_QWORD *)i + 4LL) - *(_WORD *)(*(_QWORD *)i + 2LL);
      v42.Length = v42.MaximumLength;
      v42.Buffer = (PWSTR)(*(unsigned __int16 *)(v22 + 2) + v22 + 6);
      inited = UnionFs::UfsPathName::CombinePath(
                 (UnionFs::UfsPathName *)&UnicodeString,
                 &v44,
                 &v42,
                 (unsigned __int16)v58,
                 a4);
      if ( inited < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x34800200D7ALL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::InsertTombstonesFromConfig",
          "PUSH: ComputeCombinedPathLength - originalPath",
          v40);
        if ( !v52 )
          UnicodeString = 0;
        goto LABEL_78;
      }
    }
    p_UnicodeString = &UnicodeString;
    v42 = 0;
    if ( v21 != 4 )
      p_UnicodeString = 0;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)this + 8LL));
    v41 = (char *)p_UnicodeString;
    v57 = *(utl::_RefCountBase **)this;
    v56 = this;
    inited = UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(&v56, &v49, v21, &v42, a4);
    if ( v57 )
      utl::_RefCountBase::_DecStrong(v57);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0xA600200D89LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::InsertTombstonesFromConfig",
        "PUSH: Allocating tombstone payload",
        v41);
      if ( v42.Buffer )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42.Buffer);
      goto LABEL_76;
    }
    v24 = *((_DWORD *)this + 7) == 2;
    *(_OWORD *)Resource = 0;
    *(_QWORD *)v45 = 0;
    v47 = 0;
    v48 = 0;
    if ( v24 )
      v25 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
    else
      v25 = *((_QWORD *)UnionFs::g_FilterState + 10);
    FsFltWil::AcquirePushLockShared(&v43, (char *)this + 72);
    v27 = (__int64 *)*((_QWORD *)this + 6);
    v28 = (volatile signed __int32 *)v27[1];
    v55 = *v27;
    if ( v28 )
      _InterlockedIncrement(v28 + 2);
    v29 = v43;
    v43 = 0;
    if ( v29 )
      FsFltWil::Details::ReleasePushLockShared(v29, v26);
    v40 = v45;
    inserted = UnionFs::UfsPathCache::InsertEntry(v25, **(_QWORD **)(v55 + 8), &v49, 10, &v42);
    if ( v28 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v28);
    if ( inserted < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inserted,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0xA700200D9DLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::InsertTombstonesFromConfig",
        "PUSH: Inserting tombstone entry",
        v45);
      if ( v47 )
        utl::_RefCountBase::_DecStrong(v47);
      if ( Resource[0] )
      {
        ExReleaseResourceLite(Resource[0]);
        KeLeaveCriticalRegion();
      }
      if ( v42.Buffer )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42.Buffer);
      if ( !v52 )
        UnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v34);
      if ( !v50 )
        v49 = 0;
      FsFltWil::Details::FreeUnicodeString(&v49, v35);
      if ( v10 != (_WORD *)-1LL && v10 )
        ExFreePoolWithTag(v10, 0);
      return (unsigned int)inserted;
    }
    if ( *(_DWORD *)v45 == 4 )
      break;
    if ( v47 )
      utl::_RefCountBase::_DecStrong(v47);
    if ( Resource[0] )
    {
      ExReleaseResourceLite(Resource[0]);
      KeLeaveCriticalRegion();
    }
    if ( v42.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42.Buffer);
    v15 = (unsigned __int16)v58;
  }
  TombstoneListFromConfig = -1073741811;
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000000DLL,
    (int)a4,
    (struct UnionFs::StackEventTracer *)0x78000200DA4LL,
    (unsigned __int64)"UnionFs::UfsUnionCtx::InsertTombstonesFromConfig",
    "ORIGIN: Rejected tombstone insertion at FS metadata path.",
    v45);
  if ( v47 )
    utl::_RefCountBase::_DecStrong(v47);
  if ( Resource[0] )
  {
    ExReleaseResourceLite(Resource[0]);
    KeLeaveCriticalRegion();
  }
  if ( v42.Buffer )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42.Buffer);
  if ( !v52 )
    UnicodeString = 0;
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v32);
  if ( !v50 )
    v49 = 0;
  FsFltWil::Details::FreeUnicodeString(&v49, v33);
  if ( v10 != (_WORD *)-1LL && v10 )
  {
    v8 = v10;
    goto LABEL_5;
  }
  return TombstoneListFromConfig;
}

```

## disassembly

```asm
0x140061880  push    rbp
0x140061882  push    rbx
0x140061883  push    rsi
0x140061884  push    rdi
0x140061885  push    r12
0x140061887  push    r13
0x140061889  push    r14
0x14006188b  push    r15
0x14006188d  lea     rbp, [rsp-48h]
0x140061892  sub     rsp, 148h
0x140061899  xor     r12d, r12d
0x14006189c  mov     rsi, r9
0x14006189f  mov     eax, r8d
0x1400618a2  mov     r14, rdx
0x1400618a5  mov     r15, rcx
0x1400618a8  cmp     [rdx+0Ch], r12d
0x1400618ac  jbe     loc_140061F0F
0x1400618b2  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400618ba  lea     r8, [rbp+80h+P]
0x1400618be  mov     edx, eax
0x1400618c0  mov     [rbp+80h+var_60], 0FFFFFFFFFFFFFFFFh
0x1400618c8  mov     rcx, r14
0x1400618cb  movdqu  xmmword ptr [rbp+80h+P], xmm0
0x1400618d0  call    ?GetTombstoneListFromConfig@Utils@UnionFs@@YAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAV?$vector@U?$pair@PEAVCONTAINER_ROOT_ID@UnionFs@@W4TombstoneState@2@@utl@@V?$allocator@U?$pair@PEAVCONTAINER_ROOT_ID@UnionFs@@W4TombstoneState@2@@utl@@@2@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetTombstoneListFromConfig(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,utl::vector<utl::pair<UnionFs::CONTAINER_ROOT_ID *,UnionFs::TombstoneState>,utl::allocator<utl::pair<UnionFs::CONTAINER_ROOT_ID *,UnionFs::TombstoneState>>> &,UnionFs::StackEventTracer &)
0x1400618d5  mov     ebx, eax
0x1400618d7  test    eax, eax
0x1400618d9  jns     short loc_140061926
0x1400618db  lea     rax, aPushGettingLay_2; "PUSH: Getting layer list"
0x1400618e2  mov     r8, 0A500200D4Dh; struct UnionFs::StackEventTracer *
0x1400618ec  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x1400618f3  mov     [rsp+180h+var_160], rax; char *
0x1400618f8  mov     rdx, rsi; int
0x1400618fb  mov     ecx, ebx; this
0x1400618fd  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061902  mov     rcx, [rbp+80h+P]; P
0x140061906  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14006190a  jz      short loc_14006191F
0x14006190c  test    rcx, rcx
0x14006190f  jz      short loc_14006191F
0x140061911  xor     edx, edx; Tag
0x140061913  call    cs:__imp_ExFreePoolWithTag
0x14006191a  nop     dword ptr [rax+rax+00h]
0x14006191f  mov     eax, ebx
0x140061921  jmp     loc_140061F11
0x140061926  mov     rcx, [rbp+80h+P+8]
0x14006192a  mov     rdi, [rbp+80h+P]
0x14006192e  mov     eax, [r14+0Ch]
0x140061932  sub     rcx, rdi
0x140061935  sar     rcx, 4
0x140061939  cmp     rax, rcx
0x14006193c  jz      short loc_14006194A
0x14006193e  lea     rcx, aUnionconfigTom; "UnionConfig.TombstoneEntryCount == tomb"...
0x140061945  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006194a  xorps   xmm0, xmm0
0x14006194d  lea     rdx, [r15+48h]
0x140061951  lea     rcx, [rbp+80h+arg_8]
0x140061958  movups  xmmword ptr [rsp+180h+var_128.Length], xmm0
0x14006195d  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140061962  mov     rax, [r15+30h]
0x140061966  mov     rbx, [rax+8]
0x14006196a  mov     r14, [rax]
0x14006196d  test    rbx, rbx
0x140061970  jz      short loc_140061976
0x140061972  lock inc dword ptr [rbx+8]
0x140061976  mov     rcx, [rbp+80h+arg_8]; this
0x14006197d  test    rcx, rcx
0x140061980  jz      short loc_140061987
0x140061982  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140061987  mov     r13d, 1
0x14006198d  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061992  mov     r8b, r13b; bool
0x140061995  mov     rcx, r14; this
0x140061998  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14006199d  mov     word ptr [rbp+80h+arg_8], ax
0x1400619a4  movzx   r14d, ax
0x1400619a8  test    rbx, rbx
0x1400619ab  jz      short loc_1400619B5
0x1400619ad  mov     rcx, rbx; this
0x1400619b0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400619b5  movzx   r8d, r14w; unsigned __int16
0x1400619b9  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x1400619be  lea     rcx, [rbp+80h+var_F0]; this
0x1400619c2  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x1400619c7  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x1400619cc  lea     rcx, [rbp+80h+UnicodeString]; this
0x1400619d0  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x1400619d5  mov     rbx, rdi
0x1400619d8  cmp     rbx, [rbp+80h+P+8]
0x1400619dc  jz      loc_140061E93
0x1400619e2  mov     rdx, [rbx]
0x1400619e5  lea     r8, [rsp+180h+var_140]; struct _UNICODE_STRING *
0x1400619ea  xorps   xmm0, xmm0
0x1400619ed  mov     [rsp+180h+var_160], rsi; struct UnionFs::StackEventTracer *
0x1400619f2  movups  xmmword ptr [rsp+180h+var_140.Length], xmm0
0x1400619f7  movzx   r9d, r14w; unsigned __int16
0x1400619fb  movzx   ecx, word ptr [rdx+4]
0x1400619ff  sub     cx, [rdx+2]
0x140061a03  mov     [rsp+180h+var_140.MaximumLength], cx
0x140061a08  mov     [rsp+180h+var_140.Length], cx
0x140061a0d  lea     rcx, [rdx+6]
0x140061a11  movzx   eax, word ptr [rdx+2]
0x140061a15  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061a1a  add     rcx, rax
0x140061a1d  mov     [rsp+180h+var_140.Buffer], rcx
0x140061a22  lea     rcx, [rbp+80h+var_F0]; this
0x140061a26  call    ?CombinePath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@0GAEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,UnionFs::StackEventTracer &)
0x140061a2b  mov     r14d, eax
0x140061a2e  test    eax, eax
0x140061a30  js      loc_140061E1E
0x140061a36  movzx   r12d, word ptr [rbx+8]
0x140061a3b  mov     eax, 4
0x140061a40  cmp     r12w, ax
0x140061a44  jnz     short loc_140061AA2
0x140061a46  movzx   r9d, word ptr [rbp+80h+arg_8]; unsigned __int16
0x140061a4e  lea     r8, [rsp+180h+var_140]; struct _UNICODE_STRING *
0x140061a53  xorps   xmm0, xmm0
0x140061a56  mov     [rsp+180h+var_160], rsi; struct UnionFs::StackEventTracer *
0x140061a5b  movups  xmmword ptr [rsp+180h+var_140.Length], xmm0
0x140061a60  add     rbx, 10h
0x140061a64  mov     rdx, [rbx]
0x140061a67  movzx   ecx, word ptr [rdx+4]
0x140061a6b  sub     cx, [rdx+2]
0x140061a6f  mov     [rsp+180h+var_140.MaximumLength], cx
0x140061a74  mov     [rsp+180h+var_140.Length], cx
0x140061a79  lea     rcx, [rdx+6]
0x140061a7d  movzx   eax, word ptr [rdx+2]
0x140061a81  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061a86  add     rcx, rax
0x140061a89  mov     [rsp+180h+var_140.Buffer], rcx
0x140061a8e  lea     rcx, [rbp+80h+UnicodeString]; this
0x140061a92  call    ?CombinePath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@0GAEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,UnionFs::StackEventTracer &)
0x140061a97  mov     r14d, eax
0x140061a9a  test    eax, eax
0x140061a9c  js      loc_140061C35
0x140061aa2  xor     eax, eax
0x140061aa4  lea     rcx, [rbp+80h+UnicodeString]
0x140061aa8  xorps   xmm0, xmm0
0x140061aab  movdqu  xmmword ptr [rsp+180h+var_140.Length], xmm0
0x140061ab1  lea     edx, [rax+4]
0x140061ab4  cmp     r12w, dx
0x140061ab8  cmovnz  rcx, rax
0x140061abc  mov     rax, [r15]
0x140061abf  lock inc dword ptr [rax+8]
0x140061ac3  mov     rax, [r15]
0x140061ac6  lea     r9, [rsp+180h+var_140]
0x140061acb  mov     [rsp+180h+var_158], rcx; char *
0x140061ad0  lea     rdx, [rbp+80h+var_F0]
0x140061ad4  lea     rcx, [rbp+80h+var_50]
0x140061ad8  mov     [rbp+80h+var_48], rax
0x140061adc  movzx   r8d, r12w
0x140061ae0  mov     [rbp+80h+var_50], r15
0x140061ae4  mov     [rsp+180h+var_160], rsi
0x140061ae9  call    ?AllocAndInitSharedForTombstone@UfsPathCachePayload@UnionFs@@SAJ$$QEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4TombstoneState@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@4@AEAVStackEventTracer@2@PEBV52@_N@Z; UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx> &&,UnionFs::UfsPathName const &,UnionFs::TombstoneState,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,UnionFs::UfsPathName const *,bool)
0x140061aee  mov     rcx, [rbp+80h+var_48]; this
0x140061af2  xor     r12d, r12d
0x140061af5  mov     r14d, eax
0x140061af8  test    rcx, rcx
0x140061afb  jz      short loc_140061B02
0x140061afd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061b02  test    r14d, r14d
0x140061b05  js      loc_140061DE5
0x140061b0b  cmp     dword ptr [r15+1Ch], 2
0x140061b10  xorps   xmm0, xmm0
0x140061b13  movdqu  xmmword ptr [rsp+180h+Resource], xmm0
0x140061b19  mov     qword ptr [rsp+180h+var_118], r12
0x140061b1e  mov     [rbp+80h+var_100], r12
0x140061b22  mov     [rbp+80h+var_F8], r12
0x140061b26  jnz     short loc_140061B32
0x140061b28  mov     rax, [r15+20h]
0x140061b2c  mov     r12, [rax+10h]
0x140061b30  jmp     short loc_140061B3D
0x140061b32  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140061b39  mov     r12, [rax+50h]
0x140061b3d  lea     rdx, [r15+48h]
0x140061b41  lea     rcx, [rsp+180h+var_130]
0x140061b46  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140061b4b  mov     rax, [r15+30h]
0x140061b4f  mov     r14, [rax+8]
0x140061b53  mov     rcx, [rax]
0x140061b56  mov     [rbp+80h+var_58], rcx
0x140061b5a  test    r14, r14
0x140061b5d  jz      short loc_140061B64
0x140061b5f  lock inc dword ptr [r14+8]
0x140061b64  mov     rcx, [rsp+180h+var_130]; this
0x140061b69  mov     [rsp+180h+var_130], 0
0x140061b72  test    rcx, rcx
0x140061b75  jz      short loc_140061B7C
0x140061b77  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140061b7c  mov     rdx, [rbp+80h+var_58]
0x140061b80  lea     rax, [rsp+180h+var_118]
0x140061b85  mov     [rsp+180h+var_148], 0
0x140061b8e  lea     r8, [rbp+80h+var_F0]
0x140061b92  mov     [rsp+180h+var_150], rsi
0x140061b97  mov     r9d, 0Ah
0x140061b9d  mov     [rsp+180h+var_158], rax; char *
0x140061ba2  mov     rcx, r12
0x140061ba5  mov     rdx, [rdx+8]
0x140061ba9  lea     rax, [rsp+180h+var_140]
0x140061bae  mov     [rsp+180h+var_160], rax
0x140061bb3  mov     rdx, [rdx]
0x140061bb6  call    ?InsertEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4InsertEntryFlags@2@AEBV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAUInsertEntryResults@2@AEAVStackEventTracer@2@PEAUInsertEntryOptionalParams@2@@Z; UnionFs::UfsPathCache::InsertEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::InsertEntryFlags,utl::shared_ptr<UnionFs::UfsPathCachePayload> const &,UnionFs::InsertEntryResults &,UnionFs::StackEventTracer &,UnionFs::InsertEntryOptionalParams *)
0x140061bbb  mov     r12d, eax
0x140061bbe  test    r14, r14
0x140061bc1  jz      short loc_140061BCB
0x140061bc3  mov     rcx, r14; this
0x140061bc6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061bcb  xor     r14d, r14d
0x140061bce  test    r12d, r12d
0x140061bd1  js      loc_140061D2E
0x140061bd7  cmp     dword ptr [rsp+180h+var_118], 4
0x140061bdc  jz      loc_140061C7C
0x140061be2  mov     rcx, [rbp+80h+var_100]; this
0x140061be6  xor     r12d, r12d
0x140061be9  test    rcx, rcx
0x140061bec  jz      short loc_140061BF3
0x140061bee  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061bf3  mov     rcx, [rsp+180h+Resource]; Resource
0x140061bf8  test    rcx, rcx
0x140061bfb  jz      short loc_140061C15
0x140061bfd  call    cs:__imp_ExReleaseResourceLite
0x140061c04  nop     dword ptr [rax+rax+00h]
0x140061c09  call    cs:__imp_KeLeaveCriticalRegion
0x140061c10  nop     dword ptr [rax+rax+00h]
0x140061c15  mov     rcx, [rsp+180h+var_140.Buffer]; this
0x140061c1a  test    rcx, rcx
0x140061c1d  jz      short loc_140061C24
0x140061c1f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061c24  movzx   r14d, word ptr [rbp+80h+arg_8]
0x140061c2c  add     rbx, 10h
0x140061c30  jmp     loc_1400619D8
0x140061c35  lea     rax, aPushComputecom_1; "PUSH: ComputeCombinedPathLength - origi"...
0x140061c3c  mov     r8, 34800200D7Ah; struct UnionFs::StackEventTracer *
0x140061c46  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x140061c4d  mov     [rsp+180h+var_160], rax; char *
0x140061c52  mov     rdx, rsi; int
0x140061c55  mov     ecx, r14d; this
0x140061c58  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061c5d  cmp     [rbp+80h+var_A0], 0
0x140061c61  jnz     short loc_140061C6A
0x140061c63  xorps   xmm0, xmm0
0x140061c66  movups  xmmword ptr [rbp+80h+UnicodeString.Length], xmm0
0x140061c6a  lea     rcx, [rbp+80h+UnicodeString]; UnicodeString
0x140061c6e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140061c73  cmp     [rbp+80h+var_E0], 0
0x140061c77  jmp     loc_140061E60
0x140061c7c  lea     rax, aOriginRejected; "ORIGIN: Rejected tombstone insertion at"...
0x140061c83  mov     ebx, 0C000000Dh
0x140061c88  mov     ecx, ebx; this
0x140061c8a  mov     [rsp+180h+var_160], rax; char *
0x140061c8f  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x140061c96  mov     r8, 78000200DA4h; struct UnionFs::StackEventTracer *
0x140061ca0  mov     rdx, rsi; int
0x140061ca3  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061ca8  mov     rcx, [rbp+80h+var_100]; this
0x140061cac  test    rcx, rcx
0x140061caf  jz      short loc_140061CB6
0x140061cb1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061cb6  mov     rcx, [rsp+180h+Resource]; Resource
0x140061cbb  test    rcx, rcx
0x140061cbe  jz      short loc_140061CD8
0x140061cc0  call    cs:__imp_ExReleaseResourceLite
0x140061cc7  nop     dword ptr [rax+rax+00h]
0x140061ccc  call    cs:__imp_KeLeaveCriticalRegion
0x140061cd3  nop     dword ptr [rax+rax+00h]
0x140061cd8  mov     rcx, [rsp+180h+var_140.Buffer]; this
0x140061cdd  test    rcx, rcx
0x140061ce0  jz      short loc_140061CE7
0x140061ce2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061ce7  cmp     [rbp+80h+var_A0], r14b
0x140061ceb  jnz     short loc_140061CF4
0x140061ced  xorps   xmm0, xmm0
0x140061cf0  movups  xmmword ptr [rbp+80h+UnicodeString.Length], xmm0
0x140061cf4  lea     rcx, [rbp+80h+UnicodeString]; UnicodeString
0x140061cf8  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140061cfd  cmp     [rbp+80h+var_E0], r14b
0x140061d01  jnz     short loc_140061D0A
0x140061d03  xorps   xmm0, xmm0
0x140061d06  movups  xmmword ptr [rbp+80h+var_F0.Length], xmm0
0x140061d0a  lea     rcx, [rbp+80h+var_F0]; UnicodeString
0x140061d0e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140061d13  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140061d17  jz      loc_14006191F
0x140061d1d  test    rdi, rdi
0x140061d20  jz      loc_14006191F
0x140061d26  mov     rcx, rdi
0x140061d29  jmp     loc_140061911
0x140061d2e  lea     rax, aPushInsertingT; "PUSH: Inserting tombstone entry"
0x140061d35  mov     r8, 0A700200D9Dh; struct UnionFs::StackEventTracer *
0x140061d3f  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x140061d46  mov     [rsp+180h+var_160], rax; char *
0x140061d4b  mov     rdx, rsi; int
0x140061d4e  mov     ecx, r12d; this
0x140061d51  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061d56  mov     rcx, [rbp+80h+var_100]; this
0x140061d5a  test    rcx, rcx
0x140061d5d  jz      short loc_140061D64
0x140061d5f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061d64  mov     rcx, [rsp+180h+Resource]; Resource
0x140061d69  test    rcx, rcx
0x140061d6c  jz      short loc_140061D86
  ... truncated ...
```
