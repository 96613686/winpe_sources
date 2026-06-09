# UnionFs::Utils::MarkFileAsSoftTombstone(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,UnionFs::UfsPathName &,UnionFs::SoftTombstoneReason,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &)

- ea: `0x14007090c`
- end: `0x140070c80`
- name: `?MarkFileAsSoftTombstone@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEAVUfsPathName@2@W4SoftTombstoneReason@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `884`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140065618`
- `0x140070840`

## callees

- `0x14000f7fc`
- `0x14003c734`
- `0x140040e6c`
- `0x1400419a8`
- `0x140056ac4`
- `0x140056afc`
- `0x14007090c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140070afc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070beb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070c3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070afc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070beb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070c3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070b08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070bf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070c49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070b08`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070bf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070c49`

## string_xrefs

- `0x140070aba`: `PUSH: Inserting path cache payload`
- `0x1400709fc`: `PUSH: Converting cache entry to soft tombstone`
- `0x140070968`: `PUSH: Allocating path cache payload`
- `0x140070b1f`: `ORIGIN: Rejected tombstone insertion at FS metadata path.`
- `0x140070bad`: `PUSH: Converting existing cache entry to soft tombstone`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::MarkFileAsSoftTombstone(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  const UNICODE_STRING **v8; // rbx
  int inited; // ebx
  volatile signed __int32 *v11; // rdi
  char v12; // r12
  unsigned int v13; // r15d
  utl::_RefCountBase *v14; // rcx
  bool v15; // zf
  __int64 v16; // rcx
  utl::_RefCountBase *v17; // rbx
  utl::_RefCountBase *v18; // rdi
  utl::_RefCountBase *v19; // r12
  char *v20; // [rsp+30h] [rbp-51h]
  char *v21; // [rsp+30h] [rbp-51h]
  utl::_RefCountBase *v22[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 *v23; // [rsp+58h] [rbp-29h] BYREF
  __int64 v24; // [rsp+60h] [rbp-21h]
  char v25[8]; // [rsp+68h] [rbp-19h] BYREF
  PERESOURCE Resource[2]; // [rsp+70h] [rbp-11h]
  utl::_RefCountBase *v27; // [rsp+80h] [rbp-1h]
  __int64 v28; // [rsp+88h] [rbp+7h]

  *(_OWORD *)v22 = 0;
  v8 = *(const UNICODE_STRING ***)a5;
  if ( *(_QWORD *)a5 )
  {
    v11 = *(volatile signed __int32 **)(a5 + 8);
    v12 = 0;
    if ( v11 )
      _InterlockedIncrement(v11 + 2);
    v22[0] = (utl::_RefCountBase *)v8;
    v22[1] = (utl::_RefCountBase *)v11;
  }
  else
  {
    inited = UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(v22, a6, 0);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        a6,
        (struct UnionFs::StackEventTracer *)0x2D200212338LL,
        (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
        "PUSH: Allocating path cache payload",
        v20);
LABEL_4:
      if ( v22[1] )
        utl::_RefCountBase::_DecStrong(v22[1]);
      return (unsigned int)inited;
    }
    v11 = (volatile signed __int32 *)v22[1];
    v12 = 1;
    v8 = (const UNICODE_STRING **)v22[0];
  }
  _InterlockedIncrement((volatile signed __int32 *)(*a2 + 8));
  v24 = *a2;
  v23 = a2;
  v13 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v8, &v23, a3, a4, a6);
  if ( (v13 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v13,
      a6,
      (struct UnionFs::StackEventTracer *)0x32300212348LL,
      (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
      "PUSH: Converting cache entry to soft tombstone",
      v20);
    if ( !v11 )
      return v13;
    v14 = (utl::_RefCountBase *)v11;
LABEL_14:
    utl::_RefCountBase::_DecStrong(v14);
    return v13;
  }
  if ( v12 )
  {
    v15 = *((_DWORD *)a2 + 7) == 2;
    *(_OWORD *)Resource = 0;
    *(_QWORD *)v25 = 0;
    v27 = 0;
    v28 = 0;
    if ( v15 )
      v16 = *(_QWORD *)(a2[4] + 16);
    else
      v16 = *((_QWORD *)UnionFs::g_FilterState + 10);
    inited = UnionFs::UfsPathCache::InsertEntry(v16, a1, v8[25], 8, (__int64 *)v22, (__int64)v25, a6, 0);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        a6,
        (struct UnionFs::StackEventTracer *)0x2DB0021235ALL,
        (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
        "PUSH: Inserting path cache payload",
        v21);
LABEL_22:
      if ( v27 )
        utl::_RefCountBase::_DecStrong(v27);
      if ( Resource[0] )
      {
        ExReleaseResourceLite(Resource[0]);
        KeLeaveCriticalRegion();
      }
      goto LABEL_4;
    }
    if ( *(_DWORD *)v25 == 4 )
    {
      inited = -1073741790;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000022LL,
        a6,
        (struct UnionFs::StackEventTracer *)0x77F00212363LL,
        (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
        "ORIGIN: Rejected tombstone insertion at FS metadata path.",
        v21);
      goto LABEL_22;
    }
    v17 = v27;
    if ( *(_DWORD *)v25 == 2 )
    {
      v18 = (utl::_RefCountBase *)Resource[1];
      if ( v27 )
        _InterlockedIncrement((volatile signed __int32 *)v27 + 2);
      v19 = v17;
      if ( v22[1] )
        utl::_RefCountBase::_DecStrong(v22[1]);
      _InterlockedIncrement((volatile signed __int32 *)(*a2 + 8));
      v24 = *a2;
      v23 = a2;
      v13 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v18, &v23, a3, a4, a6);
      if ( (v13 & 0x80000000) != 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)v13,
          a6,
          (struct UnionFs::StackEventTracer *)0x14F0021236FLL,
          (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
          "PUSH: Converting existing cache entry to soft tombstone",
          v21);
        if ( v17 )
          utl::_RefCountBase::_DecStrong(v17);
        if ( Resource[0] )
        {
          ExReleaseResourceLite(Resource[0]);
          KeLeaveCriticalRegion();
        }
        if ( !v17 )
          return v13;
        v14 = v17;
        goto LABEL_14;
      }
    }
    else
    {
      v19 = v22[1];
      v18 = v22[0];
    }
    *(_QWORD *)a5 = v18;
    v11 = *(volatile signed __int32 **)(a5 + 8);
    *(_QWORD *)(a5 + 8) = v19;
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    if ( Resource[0] )
    {
      ExReleaseResourceLite(Resource[0]);
      KeLeaveCriticalRegion();
    }
  }
  if ( v11 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
  return 0;
}

```

## disassembly

```asm
0x14007090c  mov     rax, rsp
0x14007090f  mov     [rax+10h], rbx
0x140070913  mov     [rax+20h], r9d
0x140070917  mov     [rax+18h], r8
0x14007091b  mov     [rax+8], rcx
0x14007091f  push    rbp
0x140070920  push    rsi
0x140070921  push    rdi
0x140070922  push    r12
0x140070924  push    r13
0x140070926  push    r14
0x140070928  push    r15
0x14007092a  lea     rbp, [rax-4Fh]
0x14007092e  sub     rsp, 90h
0x140070935  mov     r14, [rbp+47h+arg_20]
0x140070939  xorps   xmm0, xmm0
0x14007093c  mov     rsi, qword ptr [rbp+47h+arg_28]
0x140070940  mov     r15d, r9d
0x140070943  mov     r13, rdx
0x140070946  movdqu  xmmword ptr [rbp+47h+var_80], xmm0
0x14007094b  mov     rbx, [r14]
0x14007094e  test    rbx, rbx
0x140070951  jnz     short loc_1400709B1
0x140070953  xor     r8d, r8d
0x140070956  lea     rcx, [rbp+47h+var_80]
0x14007095a  mov     rdx, rsi
0x14007095d  call    ?AllocAndInitSharedEmpty@UfsPathCachePayload@UnionFs@@SAJAEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,bool)
0x140070962  mov     ebx, eax
0x140070964  test    eax, eax
0x140070966  jns     short loc_1400709A4
0x140070968  lea     rax, aPushAllocating_29; "PUSH: Allocating path cache payload"
0x14007096f  mov     r8, 2D200212338h; struct UnionFs::StackEventTracer *
0x140070979  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070980  mov     [rsp+0C0h+var_A0], rax; char *
0x140070985  mov     rdx, rsi; int
0x140070988  mov     ecx, ebx; this
0x14007098a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007098f  mov     rcx, [rbp+47h+var_80+8]; this
0x140070993  test    rcx, rcx
0x140070996  jz      short loc_14007099D
0x140070998  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007099d  mov     eax, ebx
0x14007099f  jmp     loc_140070C64
0x1400709a4  mov     rdi, [rbp+47h+var_80+8]
0x1400709a8  mov     r12b, 1
0x1400709ab  mov     rbx, [rbp+47h+var_80]
0x1400709af  jmp     short loc_1400709C9
0x1400709b1  mov     rdi, [r14+8]
0x1400709b5  xor     r12b, r12b
0x1400709b8  test    rdi, rdi
0x1400709bb  jz      short loc_1400709C1
0x1400709bd  lock inc dword ptr [rdi+8]
0x1400709c1  mov     [rbp+47h+var_80], rbx
0x1400709c5  mov     [rbp+47h+var_80+8], rdi
0x1400709c9  mov     rax, [r13+0]
0x1400709cd  lock inc dword ptr [rax+8]
0x1400709d1  mov     rax, [r13+0]
0x1400709d5  lea     rdx, [rbp+47h+var_70]
0x1400709d9  mov     r8, [rbp+47h+arg_10]
0x1400709dd  mov     r9d, r15d
0x1400709e0  mov     rcx, rbx
0x1400709e3  mov     [rbp+47h+var_68], rax
0x1400709e7  mov     [rbp+47h+var_70], r13
0x1400709eb  mov     [rsp+0C0h+var_A0], rsi
0x1400709f0  call    ?ConvertToSoftTombstone@UfsPathCachePayload@UnionFs@@QEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4SoftTombstoneReason@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx>,UnionFs::UfsPathName const &,UnionFs::SoftTombstoneReason,UnionFs::StackEventTracer &)
0x1400709f5  mov     r15d, eax
0x1400709f8  test    eax, eax
0x1400709fa  jns     short loc_140070A39
0x1400709fc  lea     rax, aPushConverting_0; "PUSH: Converting cache entry to soft to"...
0x140070a03  mov     r8, 32300212348h; struct UnionFs::StackEventTracer *
0x140070a0d  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070a14  mov     [rsp+0C0h+var_A0], rax; char *
0x140070a19  mov     rdx, rsi; int
0x140070a1c  mov     ecx, r15d; this
0x140070a1f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070a24  test    rdi, rdi
0x140070a27  jz      short loc_140070A31
0x140070a29  mov     rcx, rdi; this
0x140070a2c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070a31  mov     eax, r15d
0x140070a34  jmp     loc_140070C64
0x140070a39  test    r12b, r12b
0x140070a3c  jz      loc_140070C55
0x140070a42  cmp     dword ptr [r13+1Ch], 2
0x140070a47  xorps   xmm0, xmm0
0x140070a4a  movdqu  xmmword ptr [rbp+47h+Resource], xmm0
0x140070a4f  mov     qword ptr [rbp+47h+var_60], 0
0x140070a57  mov     [rbp+47h+var_48], 0
0x140070a5f  mov     [rbp+47h+var_40], 0
0x140070a67  jnz     short loc_140070A73
0x140070a69  mov     rax, [r13+20h]
0x140070a6d  mov     rcx, [rax+10h]
0x140070a71  jmp     short loc_140070A7E
0x140070a73  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070a7a  mov     rcx, [rax+50h]
0x140070a7e  mov     r8, [rbx+0C8h]
0x140070a85  lea     rax, [rbp+47h+var_60]
0x140070a89  mov     rdx, [rbp+47h+arg_0]
0x140070a8d  mov     r9d, 8
0x140070a93  mov     qword ptr [rsp+38h], 0
0x140070a9c  mov     [rsp+0C0h+var_90], rsi
0x140070aa1  mov     [rsp+0C0h+var_98], rax; char *
0x140070aa6  lea     rax, [rbp+47h+var_80]
0x140070aaa  mov     [rsp+0C0h+var_A0], rax
0x140070aaf  call    ?InsertEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4InsertEntryFlags@2@AEBV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAUInsertEntryResults@2@AEAVStackEventTracer@2@PEAUInsertEntryOptionalParams@2@@Z; UnionFs::UfsPathCache::InsertEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::InsertEntryFlags,utl::shared_ptr<UnionFs::UfsPathCachePayload> const &,UnionFs::InsertEntryResults &,UnionFs::StackEventTracer &,UnionFs::InsertEntryOptionalParams *)
0x140070ab4  mov     ebx, eax
0x140070ab6  test    eax, eax
0x140070ab8  jns     short loc_140070B19
0x140070aba  lea     rax, aPushInsertingP_0; "PUSH: Inserting path cache payload"
0x140070ac1  mov     r8, 2DB0021235Ah; struct UnionFs::StackEventTracer *
0x140070acb  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070ad2  mov     [rsp+0C0h+var_A0], rax; char *
0x140070ad7  mov     rdx, rsi; int
0x140070ada  mov     ecx, ebx; this
0x140070adc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070ae1  mov     rcx, [rbp+47h+var_48]; this
0x140070ae5  test    rcx, rcx
0x140070ae8  jz      short loc_140070AEF
0x140070aea  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070aef  mov     rcx, [rbp+47h+Resource]; Resource
0x140070af3  test    rcx, rcx
0x140070af6  jz      loc_14007098F
0x140070afc  call    cs:__imp_ExReleaseResourceLite
0x140070b03  nop     dword ptr [rax+rax+00h]
0x140070b08  call    cs:__imp_KeLeaveCriticalRegion
0x140070b0f  nop     dword ptr [rax+rax+00h]
0x140070b14  jmp     loc_14007098F
0x140070b19  cmp     dword ptr [rbp+47h+var_60], 4
0x140070b1d  jnz     short loc_140070B4D
0x140070b1f  lea     rax, aOriginRejected; "ORIGIN: Rejected tombstone insertion at"...
0x140070b26  mov     ebx, 0C0000022h
0x140070b2b  mov     ecx, ebx; this
0x140070b2d  mov     [rsp+0C0h+var_A0], rax; char *
0x140070b32  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070b39  mov     r8, 77F00212363h; struct UnionFs::StackEventTracer *
0x140070b43  mov     rdx, rsi; int
0x140070b46  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070b4b  jmp     short loc_140070AE1
0x140070b4d  cmp     dword ptr [rbp+47h+var_60], 2
0x140070b51  mov     rbx, [rbp+47h+var_48]
0x140070b55  jnz     loc_140070C14
0x140070b5b  mov     rdi, [rbp+47h+Resource+8]
0x140070b5f  test    rbx, rbx
0x140070b62  jz      short loc_140070B68
0x140070b64  lock inc dword ptr [rbx+8]
0x140070b68  mov     rcx, [rbp+47h+var_80+8]; this
0x140070b6c  mov     r12, rbx
0x140070b6f  test    rcx, rcx
0x140070b72  jz      short loc_140070B79
0x140070b74  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070b79  mov     rax, [r13+0]
0x140070b7d  lock inc dword ptr [rax+8]
0x140070b81  mov     rax, [r13+0]
0x140070b85  lea     rdx, [rbp+47h+var_70]
0x140070b89  mov     r9d, [rbp+47h+arg_18]
0x140070b8d  mov     rcx, rdi
0x140070b90  mov     r8, [rbp+47h+arg_10]
0x140070b94  mov     [rbp+47h+var_68], rax
0x140070b98  mov     [rbp+47h+var_70], r13
0x140070b9c  mov     [rsp+0C0h+var_A0], rsi
0x140070ba1  call    ?ConvertToSoftTombstone@UfsPathCachePayload@UnionFs@@QEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4SoftTombstoneReason@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx>,UnionFs::UfsPathName const &,UnionFs::SoftTombstoneReason,UnionFs::StackEventTracer &)
0x140070ba6  mov     r15d, eax
0x140070ba9  test    eax, eax
0x140070bab  jns     short loc_140070C1C
0x140070bad  lea     rax, aPushConverting_2; "PUSH: Converting existing cache entry t"...
0x140070bb4  mov     r8, 14F0021236Fh; struct UnionFs::StackEventTracer *
0x140070bbe  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070bc5  mov     [rsp+0C0h+var_A0], rax; char *
0x140070bca  mov     rdx, rsi; int
0x140070bcd  mov     ecx, r15d; this
0x140070bd0  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070bd5  test    rbx, rbx
0x140070bd8  jz      short loc_140070BE2
0x140070bda  mov     rcx, rbx; this
0x140070bdd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070be2  mov     rcx, [rbp+47h+Resource]; Resource
0x140070be6  test    rcx, rcx
0x140070be9  jz      short loc_140070C03
0x140070beb  call    cs:__imp_ExReleaseResourceLite
0x140070bf2  nop     dword ptr [rax+rax+00h]
0x140070bf7  call    cs:__imp_KeLeaveCriticalRegion
0x140070bfe  nop     dword ptr [rax+rax+00h]
0x140070c03  test    rbx, rbx
0x140070c06  jz      loc_140070A31
0x140070c0c  mov     rcx, rbx
0x140070c0f  jmp     loc_140070A2C
0x140070c14  mov     r12, [rbp+47h+var_80+8]
0x140070c18  mov     rdi, [rbp+47h+var_80]
0x140070c1c  mov     [r14], rdi
0x140070c1f  mov     rdi, [r14+8]
0x140070c23  mov     [r14+8], r12
0x140070c27  test    rbx, rbx
0x140070c2a  jz      short loc_140070C34
0x140070c2c  mov     rcx, rbx; this
0x140070c2f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070c34  mov     rcx, [rbp+47h+Resource]; Resource
0x140070c38  test    rcx, rcx
0x140070c3b  jz      short loc_140070C55
0x140070c3d  call    cs:__imp_ExReleaseResourceLite
0x140070c44  nop     dword ptr [rax+rax+00h]
0x140070c49  call    cs:__imp_KeLeaveCriticalRegion
0x140070c50  nop     dword ptr [rax+rax+00h]
0x140070c55  test    rdi, rdi
0x140070c58  jz      short loc_140070C62
0x140070c5a  mov     rcx, rdi; this
0x140070c5d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070c62  xor     eax, eax
0x140070c64  mov     rbx, [rsp+0C0h+arg_8]
0x140070c6c  add     rsp, 90h
0x140070c73  pop     r15
0x140070c75  pop     r14
0x140070c77  pop     r13
0x140070c79  pop     r12
0x140070c7b  pop     rdi
0x140070c7c  pop     rsi
0x140070c7d  pop     rbp
0x140070c7e  retn
```
