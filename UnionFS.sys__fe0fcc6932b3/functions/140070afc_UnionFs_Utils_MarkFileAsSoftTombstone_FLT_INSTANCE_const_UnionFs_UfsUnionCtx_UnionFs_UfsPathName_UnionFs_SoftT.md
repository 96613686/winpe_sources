# UnionFs::Utils::MarkFileAsSoftTombstone(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,UnionFs::UfsPathName &,UnionFs::SoftTombstoneReason,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &)

- ea: `0x140070afc`
- end: `0x140070e70`
- name: `?MarkFileAsSoftTombstone@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEAVUfsPathName@2@W4SoftTombstoneReason@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `884`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140065798`
- `0x140070a30`

## callees

- `0x14000f81c`
- `0x14003c854`
- `0x140040ff4`
- `0x140041b30`
- `0x140056c44`
- `0x140056c7c`
- `0x140070afc`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140070cec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070ddb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070e2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070cec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070ddb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140070e2d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070cf8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070de7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070e39`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070cf8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070de7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070e39`

## string_xrefs

- `0x140070caa`: `PUSH: Inserting path cache payload`
- `0x140070bec`: `PUSH: Converting cache entry to soft tombstone`
- `0x140070b58`: `PUSH: Allocating path cache payload`
- `0x140070d0f`: `ORIGIN: Rejected tombstone insertion at FS metadata path.`
- `0x140070d9d`: `PUSH: Converting existing cache entry to soft tombstone`

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
  utl::_RefCountBase *v8; // rbx
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
  utl::_RefCountBase *v21[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 *v22; // [rsp+58h] [rbp-29h] BYREF
  __int64 v23; // [rsp+60h] [rbp-21h]
  char v24[8]; // [rsp+68h] [rbp-19h] BYREF
  PERESOURCE Resource[2]; // [rsp+70h] [rbp-11h]
  utl::_RefCountBase *v26; // [rsp+80h] [rbp-1h]
  __int64 v27; // [rsp+88h] [rbp+7h]

  *(_OWORD *)v21 = 0;
  v8 = *(utl::_RefCountBase **)a5;
  if ( *(_QWORD *)a5 )
  {
    v11 = *(volatile signed __int32 **)(a5 + 8);
    v12 = 0;
    if ( v11 )
      _InterlockedIncrement(v11 + 2);
    v21[0] = v8;
    v21[1] = (utl::_RefCountBase *)v11;
  }
  else
  {
    inited = UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(v21, a6, 0);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        a6,
        (struct UnionFs::StackEventTracer *)0x2D20021236ELL,
        (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
        "PUSH: Allocating path cache payload",
        v20);
LABEL_4:
      if ( v21[1] )
        utl::_RefCountBase::_DecStrong(v21[1]);
      return (unsigned int)inited;
    }
    v11 = (volatile signed __int32 *)v21[1];
    v12 = 1;
    v8 = v21[0];
  }
  _InterlockedIncrement((volatile signed __int32 *)(*a2 + 8));
  v23 = *a2;
  v22 = a2;
  v13 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v8, &v22, a3, a4, a6);
  if ( (v13 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v13,
      a6,
      (struct UnionFs::StackEventTracer *)0x3230021237ELL,
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
    *(_QWORD *)v24 = 0;
    v26 = 0;
    v27 = 0;
    if ( v15 )
      v16 = *(_QWORD *)(a2[4] + 16);
    else
      v16 = *((_QWORD *)UnionFs::g_FilterState + 10);
    inited = UnionFs::UfsPathCache::InsertEntry(v16, a1, *((_QWORD *)v8 + 26), 8, v21);
    if ( inited < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inited,
        a6,
        (struct UnionFs::StackEventTracer *)0x2DB00212390LL,
        (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
        "PUSH: Inserting path cache payload",
        v24);
LABEL_22:
      if ( v26 )
        utl::_RefCountBase::_DecStrong(v26);
      if ( Resource[0] )
      {
        ExReleaseResourceLite(Resource[0]);
        KeLeaveCriticalRegion();
      }
      goto LABEL_4;
    }
    if ( *(_DWORD *)v24 == 4 )
    {
      inited = -1073741790;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000022LL,
        a6,
        (struct UnionFs::StackEventTracer *)0x77F00212399LL,
        (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
        "ORIGIN: Rejected tombstone insertion at FS metadata path.",
        v24);
      goto LABEL_22;
    }
    v17 = v26;
    if ( *(_DWORD *)v24 == 2 )
    {
      v18 = (utl::_RefCountBase *)Resource[1];
      if ( v26 )
        _InterlockedIncrement((volatile signed __int32 *)v26 + 2);
      v19 = v17;
      if ( v21[1] )
        utl::_RefCountBase::_DecStrong(v21[1]);
      _InterlockedIncrement((volatile signed __int32 *)(*a2 + 8));
      v23 = *a2;
      v22 = a2;
      v13 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v18, &v22, a3, a4, a6);
      if ( (v13 & 0x80000000) != 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)v13,
          a6,
          (struct UnionFs::StackEventTracer *)0x14F002123A5LL,
          (unsigned __int64)"UnionFs::Utils::MarkFileAsSoftTombstone",
          "PUSH: Converting existing cache entry to soft tombstone",
          v24);
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
      v19 = v21[1];
      v18 = v21[0];
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
0x140070afc  mov     rax, rsp
0x140070aff  mov     [rax+10h], rbx
0x140070b03  mov     [rax+20h], r9d
0x140070b07  mov     [rax+18h], r8
0x140070b0b  mov     [rax+8], rcx
0x140070b0f  push    rbp
0x140070b10  push    rsi
0x140070b11  push    rdi
0x140070b12  push    r12
0x140070b14  push    r13
0x140070b16  push    r14
0x140070b18  push    r15
0x140070b1a  lea     rbp, [rax-4Fh]
0x140070b1e  sub     rsp, 90h
0x140070b25  mov     r14, [rbp+47h+arg_20]
0x140070b29  xorps   xmm0, xmm0
0x140070b2c  mov     rsi, qword ptr [rbp+47h+arg_28]
0x140070b30  mov     r15d, r9d
0x140070b33  mov     r13, rdx
0x140070b36  movdqu  xmmword ptr [rbp+47h+var_80], xmm0
0x140070b3b  mov     rbx, [r14]
0x140070b3e  test    rbx, rbx
0x140070b41  jnz     short loc_140070BA1
0x140070b43  xor     r8d, r8d
0x140070b46  lea     rcx, [rbp+47h+var_80]
0x140070b4a  mov     rdx, rsi
0x140070b4d  call    ?AllocAndInitSharedEmpty@UfsPathCachePayload@UnionFs@@SAJAEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,bool)
0x140070b52  mov     ebx, eax
0x140070b54  test    eax, eax
0x140070b56  jns     short loc_140070B94
0x140070b58  lea     rax, aPushAllocating_29; "PUSH: Allocating path cache payload"
0x140070b5f  mov     r8, 2D20021236Eh; struct UnionFs::StackEventTracer *
0x140070b69  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070b70  mov     [rsp+0C0h+var_A0], rax; char *
0x140070b75  mov     rdx, rsi; int
0x140070b78  mov     ecx, ebx; this
0x140070b7a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070b7f  mov     rcx, [rbp+47h+var_80+8]; this
0x140070b83  test    rcx, rcx
0x140070b86  jz      short loc_140070B8D
0x140070b88  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070b8d  mov     eax, ebx
0x140070b8f  jmp     loc_140070E54
0x140070b94  mov     rdi, [rbp+47h+var_80+8]
0x140070b98  mov     r12b, 1
0x140070b9b  mov     rbx, [rbp+47h+var_80]
0x140070b9f  jmp     short loc_140070BB9
0x140070ba1  mov     rdi, [r14+8]
0x140070ba5  xor     r12b, r12b
0x140070ba8  test    rdi, rdi
0x140070bab  jz      short loc_140070BB1
0x140070bad  lock inc dword ptr [rdi+8]
0x140070bb1  mov     [rbp+47h+var_80], rbx
0x140070bb5  mov     [rbp+47h+var_80+8], rdi
0x140070bb9  mov     rax, [r13+0]
0x140070bbd  lock inc dword ptr [rax+8]
0x140070bc1  mov     rax, [r13+0]
0x140070bc5  lea     rdx, [rbp+47h+var_70]
0x140070bc9  mov     r8, [rbp+47h+arg_10]
0x140070bcd  mov     r9d, r15d
0x140070bd0  mov     rcx, rbx
0x140070bd3  mov     [rbp+47h+var_68], rax
0x140070bd7  mov     [rbp+47h+var_70], r13
0x140070bdb  mov     [rsp+0C0h+var_A0], rsi
0x140070be0  call    ?ConvertToSoftTombstone@UfsPathCachePayload@UnionFs@@QEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4SoftTombstoneReason@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx>,UnionFs::UfsPathName const &,UnionFs::SoftTombstoneReason,UnionFs::StackEventTracer &)
0x140070be5  mov     r15d, eax
0x140070be8  test    eax, eax
0x140070bea  jns     short loc_140070C29
0x140070bec  lea     rax, aPushConverting_0; "PUSH: Converting cache entry to soft to"...
0x140070bf3  mov     r8, 3230021237Eh; struct UnionFs::StackEventTracer *
0x140070bfd  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070c04  mov     [rsp+0C0h+var_A0], rax; char *
0x140070c09  mov     rdx, rsi; int
0x140070c0c  mov     ecx, r15d; this
0x140070c0f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070c14  test    rdi, rdi
0x140070c17  jz      short loc_140070C21
0x140070c19  mov     rcx, rdi; this
0x140070c1c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070c21  mov     eax, r15d
0x140070c24  jmp     loc_140070E54
0x140070c29  test    r12b, r12b
0x140070c2c  jz      loc_140070E45
0x140070c32  cmp     dword ptr [r13+1Ch], 2
0x140070c37  xorps   xmm0, xmm0
0x140070c3a  movdqu  xmmword ptr [rbp+47h+Resource], xmm0
0x140070c3f  mov     qword ptr [rbp+47h+var_60], 0
0x140070c47  mov     [rbp+47h+var_48], 0
0x140070c4f  mov     [rbp+47h+var_40], 0
0x140070c57  jnz     short loc_140070C63
0x140070c59  mov     rax, [r13+20h]
0x140070c5d  mov     rcx, [rax+10h]
0x140070c61  jmp     short loc_140070C6E
0x140070c63  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070c6a  mov     rcx, [rax+50h]
0x140070c6e  mov     r8, [rbx+0D0h]
0x140070c75  lea     rax, [rbp+47h+var_60]
0x140070c79  mov     rdx, [rbp+47h+arg_0]
0x140070c7d  mov     r9d, 8
0x140070c83  mov     qword ptr [rsp+38h], 0
0x140070c8c  mov     [rsp+0C0h+var_90], rsi
0x140070c91  mov     [rsp+0C0h+var_98], rax; char *
0x140070c96  lea     rax, [rbp+47h+var_80]
0x140070c9a  mov     [rsp+0C0h+var_A0], rax
0x140070c9f  call    ?InsertEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4InsertEntryFlags@2@AEBV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAUInsertEntryResults@2@AEAVStackEventTracer@2@PEAUInsertEntryOptionalParams@2@@Z; UnionFs::UfsPathCache::InsertEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::InsertEntryFlags,utl::shared_ptr<UnionFs::UfsPathCachePayload> const &,UnionFs::InsertEntryResults &,UnionFs::StackEventTracer &,UnionFs::InsertEntryOptionalParams *)
0x140070ca4  mov     ebx, eax
0x140070ca6  test    eax, eax
0x140070ca8  jns     short loc_140070D09
0x140070caa  lea     rax, aPushInsertingP_0; "PUSH: Inserting path cache payload"
0x140070cb1  mov     r8, 2DB00212390h; struct UnionFs::StackEventTracer *
0x140070cbb  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070cc2  mov     [rsp+0C0h+var_A0], rax; char *
0x140070cc7  mov     rdx, rsi; int
0x140070cca  mov     ecx, ebx; this
0x140070ccc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070cd1  mov     rcx, [rbp+47h+var_48]; this
0x140070cd5  test    rcx, rcx
0x140070cd8  jz      short loc_140070CDF
0x140070cda  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070cdf  mov     rcx, [rbp+47h+Resource]; Resource
0x140070ce3  test    rcx, rcx
0x140070ce6  jz      loc_140070B7F
0x140070cec  call    cs:__imp_ExReleaseResourceLite
0x140070cf3  nop     dword ptr [rax+rax+00h]
0x140070cf8  call    cs:__imp_KeLeaveCriticalRegion
0x140070cff  nop     dword ptr [rax+rax+00h]
0x140070d04  jmp     loc_140070B7F
0x140070d09  cmp     dword ptr [rbp+47h+var_60], 4
0x140070d0d  jnz     short loc_140070D3D
0x140070d0f  lea     rax, aOriginRejected; "ORIGIN: Rejected tombstone insertion at"...
0x140070d16  mov     ebx, 0C0000022h
0x140070d1b  mov     ecx, ebx; this
0x140070d1d  mov     [rsp+0C0h+var_A0], rax; char *
0x140070d22  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070d29  mov     r8, 77F00212399h; struct UnionFs::StackEventTracer *
0x140070d33  mov     rdx, rsi; int
0x140070d36  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070d3b  jmp     short loc_140070CD1
0x140070d3d  cmp     dword ptr [rbp+47h+var_60], 2
0x140070d41  mov     rbx, [rbp+47h+var_48]
0x140070d45  jnz     loc_140070E04
0x140070d4b  mov     rdi, [rbp+47h+Resource+8]
0x140070d4f  test    rbx, rbx
0x140070d52  jz      short loc_140070D58
0x140070d54  lock inc dword ptr [rbx+8]
0x140070d58  mov     rcx, [rbp+47h+var_80+8]; this
0x140070d5c  mov     r12, rbx
0x140070d5f  test    rcx, rcx
0x140070d62  jz      short loc_140070D69
0x140070d64  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070d69  mov     rax, [r13+0]
0x140070d6d  lock inc dword ptr [rax+8]
0x140070d71  mov     rax, [r13+0]
0x140070d75  lea     rdx, [rbp+47h+var_70]
0x140070d79  mov     r9d, [rbp+47h+arg_18]
0x140070d7d  mov     rcx, rdi
0x140070d80  mov     r8, [rbp+47h+arg_10]
0x140070d84  mov     [rbp+47h+var_68], rax
0x140070d88  mov     [rbp+47h+var_70], r13
0x140070d8c  mov     [rsp+0C0h+var_A0], rsi
0x140070d91  call    ?ConvertToSoftTombstone@UfsPathCachePayload@UnionFs@@QEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4SoftTombstoneReason@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx>,UnionFs::UfsPathName const &,UnionFs::SoftTombstoneReason,UnionFs::StackEventTracer &)
0x140070d96  mov     r15d, eax
0x140070d99  test    eax, eax
0x140070d9b  jns     short loc_140070E0C
0x140070d9d  lea     rax, aPushConverting_2; "PUSH: Converting existing cache entry t"...
0x140070da4  mov     r8, 14F002123A5h; struct UnionFs::StackEventTracer *
0x140070dae  lea     r9, aUnionfsUtilsMa; "UnionFs::Utils::MarkFileAsSoftTombstone"
0x140070db5  mov     [rsp+0C0h+var_A0], rax; char *
0x140070dba  mov     rdx, rsi; int
0x140070dbd  mov     ecx, r15d; this
0x140070dc0  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070dc5  test    rbx, rbx
0x140070dc8  jz      short loc_140070DD2
0x140070dca  mov     rcx, rbx; this
0x140070dcd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070dd2  mov     rcx, [rbp+47h+Resource]; Resource
0x140070dd6  test    rcx, rcx
0x140070dd9  jz      short loc_140070DF3
0x140070ddb  call    cs:__imp_ExReleaseResourceLite
0x140070de2  nop     dword ptr [rax+rax+00h]
0x140070de7  call    cs:__imp_KeLeaveCriticalRegion
0x140070dee  nop     dword ptr [rax+rax+00h]
0x140070df3  test    rbx, rbx
0x140070df6  jz      loc_140070C21
0x140070dfc  mov     rcx, rbx
0x140070dff  jmp     loc_140070C1C
0x140070e04  mov     r12, [rbp+47h+var_80+8]
0x140070e08  mov     rdi, [rbp+47h+var_80]
0x140070e0c  mov     [r14], rdi
0x140070e0f  mov     rdi, [r14+8]
0x140070e13  mov     [r14+8], r12
0x140070e17  test    rbx, rbx
0x140070e1a  jz      short loc_140070E24
0x140070e1c  mov     rcx, rbx; this
0x140070e1f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070e24  mov     rcx, [rbp+47h+Resource]; Resource
0x140070e28  test    rcx, rcx
0x140070e2b  jz      short loc_140070E45
0x140070e2d  call    cs:__imp_ExReleaseResourceLite
0x140070e34  nop     dword ptr [rax+rax+00h]
0x140070e39  call    cs:__imp_KeLeaveCriticalRegion
0x140070e40  nop     dword ptr [rax+rax+00h]
0x140070e45  test    rdi, rdi
0x140070e48  jz      short loc_140070E52
0x140070e4a  mov     rcx, rdi; this
0x140070e4d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140070e52  xor     eax, eax
0x140070e54  mov     rbx, [rsp+0C0h+arg_8]
0x140070e5c  add     rsp, 90h
0x140070e63  pop     r15
0x140070e65  pop     r14
0x140070e67  pop     r13
0x140070e69  pop     r12
0x140070e6b  pop     rdi
0x140070e6c  pop     rsi
0x140070e6d  pop     rbp
0x140070e6e  retn
```
