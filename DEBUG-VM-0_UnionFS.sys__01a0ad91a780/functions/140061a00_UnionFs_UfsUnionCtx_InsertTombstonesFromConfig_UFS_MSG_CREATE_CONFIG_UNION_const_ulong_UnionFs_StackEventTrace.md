# UnionFs::UfsUnionCtx::InsertTombstonesFromConfig(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &)

- ea: `0x140061a00`
- end: `0x1400620a6`
- name: `?InsertTombstonesFromConfig@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@@Z`
- size: `1702`
- prototype: `int(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140062fd4`

## callees

- `0x14000f81c`
- `0x140036268`
- `0x14003c854`
- `0x1400411c8`
- `0x140043a64`
- `0x140044758`
- `0x140056c44`
- `0x140056c7c`
- `0x140061a00`
- `0x14006fe74`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140061a93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061f51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062002`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062083`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061a93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140061f51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062002`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062083`
- `ntoskrnl!KeSetEvent` at `0x14006203b`
- `ntoskrnl!KeSetEvent` at `0x14006203b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061d7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061e40`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061eee`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061d7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061e40`
- `ntoskrnl!ExReleaseResourceLite` at `0x140061eee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061d89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061e4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061efa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061d89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061e4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061efa`

## string_xrefs

- `0x140061a6c`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061dc6`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061e0f`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061ebf`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061f76`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061faf`: `UnionFs::UfsUnionCtx::InsertTombstonesFromConfig`
- `0x140061f9e`: `PUSH: ComputeCombinedPathLength - tombstonePath`
- `0x140061abe`: `UnionConfig.TombstoneEntryCount == tombstoneIds.size()`
- `0x140061dfc`: `ORIGIN: Rejected tombstone insertion at FS metadata path.`
- `0x140061db5`: `PUSH: ComputeCombinedPathLength - originalPath`

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
0x140061a00  push    rbp
0x140061a02  push    rbx
0x140061a03  push    rsi
0x140061a04  push    rdi
0x140061a05  push    r12
0x140061a07  push    r13
0x140061a09  push    r14
0x140061a0b  push    r15
0x140061a0d  lea     rbp, [rsp-48h]
0x140061a12  sub     rsp, 148h
0x140061a19  xor     r12d, r12d
0x140061a1c  mov     rsi, r9
0x140061a1f  mov     eax, r8d
0x140061a22  mov     r14, rdx
0x140061a25  mov     r15, rcx
0x140061a28  cmp     [rdx+0Ch], r12d
0x140061a2c  jbe     loc_14006208F
0x140061a32  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140061a3a  lea     r8, [rbp+80h+P]
0x140061a3e  mov     edx, eax
0x140061a40  mov     [rbp+80h+var_60], 0FFFFFFFFFFFFFFFFh
0x140061a48  mov     rcx, r14
0x140061a4b  movdqu  xmmword ptr [rbp+80h+P], xmm0
0x140061a50  call    ?GetTombstoneListFromConfig@Utils@UnionFs@@YAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAV?$vector@U?$pair@PEAVCONTAINER_ROOT_ID@UnionFs@@W4TombstoneState@2@@utl@@V?$allocator@U?$pair@PEAVCONTAINER_ROOT_ID@UnionFs@@W4TombstoneState@2@@utl@@@2@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetTombstoneListFromConfig(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,utl::vector<utl::pair<UnionFs::CONTAINER_ROOT_ID *,UnionFs::TombstoneState>,utl::allocator<utl::pair<UnionFs::CONTAINER_ROOT_ID *,UnionFs::TombstoneState>>> &,UnionFs::StackEventTracer &)
0x140061a55  mov     ebx, eax
0x140061a57  test    eax, eax
0x140061a59  jns     short loc_140061AA6
0x140061a5b  lea     rax, aPushGettingLay_2; "PUSH: Getting layer list"
0x140061a62  mov     r8, 0A500200D4Dh; struct UnionFs::StackEventTracer *
0x140061a6c  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x140061a73  mov     [rsp+180h+var_160], rax; char *
0x140061a78  mov     rdx, rsi; int
0x140061a7b  mov     ecx, ebx; this
0x140061a7d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061a82  mov     rcx, [rbp+80h+P]; P
0x140061a86  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140061a8a  jz      short loc_140061A9F
0x140061a8c  test    rcx, rcx
0x140061a8f  jz      short loc_140061A9F
0x140061a91  xor     edx, edx; Tag
0x140061a93  call    cs:__imp_ExFreePoolWithTag
0x140061a9a  nop     dword ptr [rax+rax+00h]
0x140061a9f  mov     eax, ebx
0x140061aa1  jmp     loc_140062091
0x140061aa6  mov     rcx, [rbp+80h+P+8]
0x140061aaa  mov     rdi, [rbp+80h+P]
0x140061aae  mov     eax, [r14+0Ch]
0x140061ab2  sub     rcx, rdi
0x140061ab5  sar     rcx, 4
0x140061ab9  cmp     rax, rcx
0x140061abc  jz      short loc_140061ACA
0x140061abe  lea     rcx, aUnionconfigTom; "UnionConfig.TombstoneEntryCount == tomb"...
0x140061ac5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140061aca  xorps   xmm0, xmm0
0x140061acd  lea     rdx, [r15+48h]
0x140061ad1  lea     rcx, [rbp+80h+arg_8]
0x140061ad8  movups  xmmword ptr [rsp+180h+var_128.Length], xmm0
0x140061add  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140061ae2  mov     rax, [r15+30h]
0x140061ae6  mov     rbx, [rax+8]
0x140061aea  mov     r14, [rax]
0x140061aed  test    rbx, rbx
0x140061af0  jz      short loc_140061AF6
0x140061af2  lock inc dword ptr [rbx+8]
0x140061af6  mov     rcx, [rbp+80h+arg_8]; this
0x140061afd  test    rcx, rcx
0x140061b00  jz      short loc_140061B07
0x140061b02  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140061b07  mov     r13d, 1
0x140061b0d  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061b12  mov     r8b, r13b; bool
0x140061b15  mov     rcx, r14; this
0x140061b18  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x140061b1d  mov     word ptr [rbp+80h+arg_8], ax
0x140061b24  movzx   r14d, ax
0x140061b28  test    rbx, rbx
0x140061b2b  jz      short loc_140061B35
0x140061b2d  mov     rcx, rbx; this
0x140061b30  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061b35  movzx   r8d, r14w; unsigned __int16
0x140061b39  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061b3e  lea     rcx, [rbp+80h+var_F0]; this
0x140061b42  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x140061b47  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061b4c  lea     rcx, [rbp+80h+UnicodeString]; this
0x140061b50  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x140061b55  mov     rbx, rdi
0x140061b58  cmp     rbx, [rbp+80h+P+8]
0x140061b5c  jz      loc_140062013
0x140061b62  mov     rdx, [rbx]
0x140061b65  lea     r8, [rsp+180h+var_140]; struct _UNICODE_STRING *
0x140061b6a  xorps   xmm0, xmm0
0x140061b6d  mov     [rsp+180h+var_160], rsi; struct UnionFs::StackEventTracer *
0x140061b72  movups  xmmword ptr [rsp+180h+var_140.Length], xmm0
0x140061b77  movzx   r9d, r14w; unsigned __int16
0x140061b7b  movzx   ecx, word ptr [rdx+4]
0x140061b7f  sub     cx, [rdx+2]
0x140061b83  mov     [rsp+180h+var_140.MaximumLength], cx
0x140061b88  mov     [rsp+180h+var_140.Length], cx
0x140061b8d  lea     rcx, [rdx+6]
0x140061b91  movzx   eax, word ptr [rdx+2]
0x140061b95  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061b9a  add     rcx, rax
0x140061b9d  mov     [rsp+180h+var_140.Buffer], rcx
0x140061ba2  lea     rcx, [rbp+80h+var_F0]; this
0x140061ba6  call    ?CombinePath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@0GAEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,UnionFs::StackEventTracer &)
0x140061bab  mov     r14d, eax
0x140061bae  test    eax, eax
0x140061bb0  js      loc_140061F9E
0x140061bb6  movzx   r12d, word ptr [rbx+8]
0x140061bbb  mov     eax, 4
0x140061bc0  cmp     r12w, ax
0x140061bc4  jnz     short loc_140061C22
0x140061bc6  movzx   r9d, word ptr [rbp+80h+arg_8]; unsigned __int16
0x140061bce  lea     r8, [rsp+180h+var_140]; struct _UNICODE_STRING *
0x140061bd3  xorps   xmm0, xmm0
0x140061bd6  mov     [rsp+180h+var_160], rsi; struct UnionFs::StackEventTracer *
0x140061bdb  movups  xmmword ptr [rsp+180h+var_140.Length], xmm0
0x140061be0  add     rbx, 10h
0x140061be4  mov     rdx, [rbx]
0x140061be7  movzx   ecx, word ptr [rdx+4]
0x140061beb  sub     cx, [rdx+2]
0x140061bef  mov     [rsp+180h+var_140.MaximumLength], cx
0x140061bf4  mov     [rsp+180h+var_140.Length], cx
0x140061bf9  lea     rcx, [rdx+6]
0x140061bfd  movzx   eax, word ptr [rdx+2]
0x140061c01  lea     rdx, [rsp+180h+var_128]; struct _UNICODE_STRING *
0x140061c06  add     rcx, rax
0x140061c09  mov     [rsp+180h+var_140.Buffer], rcx
0x140061c0e  lea     rcx, [rbp+80h+UnicodeString]; this
0x140061c12  call    ?CombinePath@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@0GAEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,UnionFs::StackEventTracer &)
0x140061c17  mov     r14d, eax
0x140061c1a  test    eax, eax
0x140061c1c  js      loc_140061DB5
0x140061c22  xor     eax, eax
0x140061c24  lea     rcx, [rbp+80h+UnicodeString]
0x140061c28  xorps   xmm0, xmm0
0x140061c2b  movdqu  xmmword ptr [rsp+180h+var_140.Length], xmm0
0x140061c31  lea     edx, [rax+4]
0x140061c34  cmp     r12w, dx
0x140061c38  cmovnz  rcx, rax
0x140061c3c  mov     rax, [r15]
0x140061c3f  lock inc dword ptr [rax+8]
0x140061c43  mov     rax, [r15]
0x140061c46  lea     r9, [rsp+180h+var_140]
0x140061c4b  mov     [rsp+180h+var_158], rcx; char *
0x140061c50  lea     rdx, [rbp+80h+var_F0]
0x140061c54  lea     rcx, [rbp+80h+var_50]
0x140061c58  mov     [rbp+80h+var_48], rax
0x140061c5c  movzx   r8d, r12w
0x140061c60  mov     [rbp+80h+var_50], r15
0x140061c64  mov     [rsp+180h+var_160], rsi
0x140061c69  call    ?AllocAndInitSharedForTombstone@UfsPathCachePayload@UnionFs@@SAJ$$QEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4TombstoneState@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@4@AEAVStackEventTracer@2@PEBV52@_N@Z; UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx> &&,UnionFs::UfsPathName const &,UnionFs::TombstoneState,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,UnionFs::UfsPathName const *,bool)
0x140061c6e  mov     rcx, [rbp+80h+var_48]; this
0x140061c72  xor     r12d, r12d
0x140061c75  mov     r14d, eax
0x140061c78  test    rcx, rcx
0x140061c7b  jz      short loc_140061C82
0x140061c7d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061c82  test    r14d, r14d
0x140061c85  js      loc_140061F65
0x140061c8b  cmp     dword ptr [r15+1Ch], 2
0x140061c90  xorps   xmm0, xmm0
0x140061c93  movdqu  xmmword ptr [rsp+180h+Resource], xmm0
0x140061c99  mov     qword ptr [rsp+180h+var_118], r12
0x140061c9e  mov     [rbp+80h+var_100], r12
0x140061ca2  mov     [rbp+80h+var_F8], r12
0x140061ca6  jnz     short loc_140061CB2
0x140061ca8  mov     rax, [r15+20h]
0x140061cac  mov     r12, [rax+10h]
0x140061cb0  jmp     short loc_140061CBD
0x140061cb2  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140061cb9  mov     r12, [rax+50h]
0x140061cbd  lea     rdx, [r15+48h]
0x140061cc1  lea     rcx, [rsp+180h+var_130]
0x140061cc6  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140061ccb  mov     rax, [r15+30h]
0x140061ccf  mov     r14, [rax+8]
0x140061cd3  mov     rcx, [rax]
0x140061cd6  mov     [rbp+80h+var_58], rcx
0x140061cda  test    r14, r14
0x140061cdd  jz      short loc_140061CE4
0x140061cdf  lock inc dword ptr [r14+8]
0x140061ce4  mov     rcx, [rsp+180h+var_130]; this
0x140061ce9  mov     [rsp+180h+var_130], 0
0x140061cf2  test    rcx, rcx
0x140061cf5  jz      short loc_140061CFC
0x140061cf7  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140061cfc  mov     rdx, [rbp+80h+var_58]
0x140061d00  lea     rax, [rsp+180h+var_118]
0x140061d05  mov     [rsp+180h+var_148], 0
0x140061d0e  lea     r8, [rbp+80h+var_F0]
0x140061d12  mov     [rsp+180h+var_150], rsi
0x140061d17  mov     r9d, 0Ah
0x140061d1d  mov     [rsp+180h+var_158], rax; char *
0x140061d22  mov     rcx, r12
0x140061d25  mov     rdx, [rdx+8]
0x140061d29  lea     rax, [rsp+180h+var_140]
0x140061d2e  mov     [rsp+180h+var_160], rax
0x140061d33  mov     rdx, [rdx]
0x140061d36  call    ?InsertEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4InsertEntryFlags@2@AEBV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAUInsertEntryResults@2@AEAVStackEventTracer@2@PEAUInsertEntryOptionalParams@2@@Z; UnionFs::UfsPathCache::InsertEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::InsertEntryFlags,utl::shared_ptr<UnionFs::UfsPathCachePayload> const &,UnionFs::InsertEntryResults &,UnionFs::StackEventTracer &,UnionFs::InsertEntryOptionalParams *)
0x140061d3b  mov     r12d, eax
0x140061d3e  test    r14, r14
0x140061d41  jz      short loc_140061D4B
0x140061d43  mov     rcx, r14; this
0x140061d46  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061d4b  xor     r14d, r14d
0x140061d4e  test    r12d, r12d
0x140061d51  js      loc_140061EAE
0x140061d57  cmp     dword ptr [rsp+180h+var_118], 4
0x140061d5c  jz      loc_140061DFC
0x140061d62  mov     rcx, [rbp+80h+var_100]; this
0x140061d66  xor     r12d, r12d
0x140061d69  test    rcx, rcx
0x140061d6c  jz      short loc_140061D73
0x140061d6e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061d73  mov     rcx, [rsp+180h+Resource]; Resource
0x140061d78  test    rcx, rcx
0x140061d7b  jz      short loc_140061D95
0x140061d7d  call    cs:__imp_ExReleaseResourceLite
0x140061d84  nop     dword ptr [rax+rax+00h]
0x140061d89  call    cs:__imp_KeLeaveCriticalRegion
0x140061d90  nop     dword ptr [rax+rax+00h]
0x140061d95  mov     rcx, [rsp+180h+var_140.Buffer]; this
0x140061d9a  test    rcx, rcx
0x140061d9d  jz      short loc_140061DA4
0x140061d9f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061da4  movzx   r14d, word ptr [rbp+80h+arg_8]
0x140061dac  add     rbx, 10h
0x140061db0  jmp     loc_140061B58
0x140061db5  lea     rax, aPushComputecom_1; "PUSH: ComputeCombinedPathLength - origi"...
0x140061dbc  mov     r8, 34800200D7Ah; struct UnionFs::StackEventTracer *
0x140061dc6  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x140061dcd  mov     [rsp+180h+var_160], rax; char *
0x140061dd2  mov     rdx, rsi; int
0x140061dd5  mov     ecx, r14d; this
0x140061dd8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061ddd  cmp     [rbp+80h+var_A0], 0
0x140061de1  jnz     short loc_140061DEA
0x140061de3  xorps   xmm0, xmm0
0x140061de6  movups  xmmword ptr [rbp+80h+UnicodeString.Length], xmm0
0x140061dea  lea     rcx, [rbp+80h+UnicodeString]; UnicodeString
0x140061dee  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140061df3  cmp     [rbp+80h+var_E0], 0
0x140061df7  jmp     loc_140061FE0
0x140061dfc  lea     rax, aOriginRejected; "ORIGIN: Rejected tombstone insertion at"...
0x140061e03  mov     ebx, 0C000000Dh
0x140061e08  mov     ecx, ebx; this
0x140061e0a  mov     [rsp+180h+var_160], rax; char *
0x140061e0f  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x140061e16  mov     r8, 78000200DA4h; struct UnionFs::StackEventTracer *
0x140061e20  mov     rdx, rsi; int
0x140061e23  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061e28  mov     rcx, [rbp+80h+var_100]; this
0x140061e2c  test    rcx, rcx
0x140061e2f  jz      short loc_140061E36
0x140061e31  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061e36  mov     rcx, [rsp+180h+Resource]; Resource
0x140061e3b  test    rcx, rcx
0x140061e3e  jz      short loc_140061E58
0x140061e40  call    cs:__imp_ExReleaseResourceLite
0x140061e47  nop     dword ptr [rax+rax+00h]
0x140061e4c  call    cs:__imp_KeLeaveCriticalRegion
0x140061e53  nop     dword ptr [rax+rax+00h]
0x140061e58  mov     rcx, [rsp+180h+var_140.Buffer]; this
0x140061e5d  test    rcx, rcx
0x140061e60  jz      short loc_140061E67
0x140061e62  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061e67  cmp     [rbp+80h+var_A0], r14b
0x140061e6b  jnz     short loc_140061E74
0x140061e6d  xorps   xmm0, xmm0
0x140061e70  movups  xmmword ptr [rbp+80h+UnicodeString.Length], xmm0
0x140061e74  lea     rcx, [rbp+80h+UnicodeString]; UnicodeString
0x140061e78  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140061e7d  cmp     [rbp+80h+var_E0], r14b
0x140061e81  jnz     short loc_140061E8A
0x140061e83  xorps   xmm0, xmm0
0x140061e86  movups  xmmword ptr [rbp+80h+var_F0.Length], xmm0
0x140061e8a  lea     rcx, [rbp+80h+var_F0]; UnicodeString
0x140061e8e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140061e93  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140061e97  jz      loc_140061A9F
0x140061e9d  test    rdi, rdi
0x140061ea0  jz      loc_140061A9F
0x140061ea6  mov     rcx, rdi
0x140061ea9  jmp     loc_140061A91
0x140061eae  lea     rax, aPushInsertingT; "PUSH: Inserting tombstone entry"
0x140061eb5  mov     r8, 0A700200D9Dh; struct UnionFs::StackEventTracer *
0x140061ebf  lea     r9, aUnionfsUfsunio_7; "UnionFs::UfsUnionCtx::InsertTombstonesF"...
0x140061ec6  mov     [rsp+180h+var_160], rax; char *
0x140061ecb  mov     rdx, rsi; int
0x140061ece  mov     ecx, r12d; this
0x140061ed1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140061ed6  mov     rcx, [rbp+80h+var_100]; this
0x140061eda  test    rcx, rcx
0x140061edd  jz      short loc_140061EE4
0x140061edf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140061ee4  mov     rcx, [rsp+180h+Resource]; Resource
0x140061ee9  test    rcx, rcx
0x140061eec  jz      short loc_140061F06
  ... truncated ...
```
