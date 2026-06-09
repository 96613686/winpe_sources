# UnionFs::UnionFsFilter::PreCleanup(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x14002d6d0`
- end: `0x14002dc6c`
- name: `?PreCleanup@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `1436`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140005574`
- `0x1400056b4`
- `0x140005ff8`
- `0x140006168`
- `0x14000efa0`
- `0x14000f81c`
- `0x140027a9c`
- `0x140027cb8`
- `0x14002b4c8`
- `0x14002be84`
- `0x14002d6d0`
- `0x140056974`
- `0x140056c7c`
- `0x140058008`
- `0x140074d3c`
- `0x14007a114`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002da73`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002db37`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002da73`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002db37`
- `FLTMGR!FltReleaseContext` at `0x14002d8f3`
- `FLTMGR!FltReleaseContext` at `0x14002da9d`
- `FLTMGR!FltReleaseContext` at `0x14002dadb`
- `FLTMGR!FltReleaseContext` at `0x14002db61`
- `FLTMGR!FltReleaseContext` at `0x14002dba4`
- `FLTMGR!FltReleaseContext` at `0x14002dbeb`
- `FLTMGR!FltReleaseContext` at `0x14002d8f3`
- `FLTMGR!FltReleaseContext` at `0x14002da9d`
- `FLTMGR!FltReleaseContext` at `0x14002dadb`
- `FLTMGR!FltReleaseContext` at `0x14002db61`
- `FLTMGR!FltReleaseContext` at `0x14002dba4`
- `FLTMGR!FltReleaseContext` at `0x14002dbeb`

## string_xrefs

- `0x14002da25`: `PUSH: Preparing for delete`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCleanup(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        void **a3)
{
  bool v6; // r8
  int v7; // esi
  struct UnionFs::UfsStreamHandleCtx *v8; // rbx
  __int64 v9; // rdx
  unsigned int v10; // r14d
  PFILE_OBJECT FileObject; // rcx
  _WORD *FsContext; // rax
  int v13; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v14; // rdx
  struct _FILE_OBJECT *v15; // rdx
  int Set; // eax
  int v17; // eax
  __int16 v18; // cx
  int v19; // edi
  __int64 v20; // rcx
  PVOID v21; // rdi
  PVOID v22; // rdi
  PVOID *v23; // rax
  PVOID v24; // rbx
  struct UnionFs::StackEventTracer *v26; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v27; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v28; // [rsp+28h] [rbp-D8h]
  PVOID Entry; // [rsp+48h] [rbp-B8h] BYREF
  PFLT_CONTEXT v30; // [rsp+50h] [rbp-B0h]
  __int128 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  struct UnionFs::UfsStreamHandleCtx *v33; // [rsp+70h] [rbp-90h]
  _BYTE v34[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v35[14]; // [rsp+80h] [rbp-80h] BYREF
  struct UnionFs::UfsUnionCtx *v36; // [rsp+F0h] [rbp-10h]
  utl::_RefCountBase *v37; // [rsp+F8h] [rbp-8h]
  __int64 v38; // [rsp+100h] [rbp+0h] BYREF
  char v39; // [rsp+108h] [rbp+8h]
  _BYTE v40[112]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v41; // [rsp+180h] [rbp+80h]
  PFLT_CONTEXT Context[3]; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v43[17]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v44[4]; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v45[46]; // [rsp+2A0h] [rbp+1A0h]
  __int16 v46; // [rsp+412h] [rbp+312h]
  __int16 v47; // [rsp+44Ch] [rbp+34Ch]

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v44, 0x2D1000B090CuLL, a1);
  memset(Context, 0, sizeof(Context));
  memset(v43, 0, sizeof(v43));
  v7 = UnionFs::UfsStreamHandleCtx::FltGet(
         a2->Instance,
         a2->FileObject,
         v6,
         (struct UnionFs::HandleCtxAndUnionWithRundown *)Context,
         (struct UnionFs::StackEventTracer *)v44);
  if ( v7 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v7,
      (int)v44,
      (struct UnionFs::StackEventTracer *)0x2D5000B091ELL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
      "PUSH: Getting handle ctx",
      (const char *)v26);
    UnionFs::StackEventTracer::LogError((UnionFs::StackEventTracer *)v44);
    *(_DWORD *)v44 = 0;
    v47 = 0;
  }
  v8 = (struct UnionFs::UfsStreamHandleCtx *)Context[0];
  v36 = (struct UnionFs::UfsUnionCtx *)Context[1];
  v37 = (utl::_RefCountBase *)Context[2];
  v38 = v43[0];
  v39 = v43[1];
  memset(Context, 0, sizeof(Context));
  wistd::function<void (bool)>::function<void (bool)>(v40, &v43[2]);
  memset(v43, 0, sizeof(v43));
  v10 = 1;
  if ( v8 )
  {
    FileObject = a2->FileObject;
    FsContext = FileObject->FsContext;
    if ( FsContext )
    {
      v9 = 17217;
      if ( *FsContext == 17217 && (*(_BYTE *)v8 & 1) != 0 )
      {
        v13 = UnionFs::UfsShadowFileObject::Cleanup(
                (UnionFs::UfsShadowFileObject *)FileObject,
                a1,
                a2,
                v8,
                v36,
                (struct UnionFs::StackEventTracer *)v44);
        if ( v13 < 0 )
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v13,
            (int)v44,
            (struct UnionFs::StackEventTracer *)0xC1000B093ALL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
            "PUSH: Cleaning up SFO",
            (const char *)v27);
        a1->IoStatus.Status = 0;
        a1->IoStatus.Information = 0;
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v38, v14);
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
        if ( v37 )
          utl::_RefCountBase::_DecStrong(v37);
        FltReleaseContext(v8);
        v10 = 4;
        goto LABEL_48;
      }
    }
    if ( v7 < 0 )
      goto LABEL_27;
    v15 = a2->FileObject;
    v30 = 0;
    Set = UnionFs::UfsFileCtx::FltGetSet(a2->Instance, v15, 0);
    if ( Set < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Set,
        (int)v44,
        (struct UnionFs::StackEventTracer *)0x2D8000B0951LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
        "PUSH: Getting file ctx",
        (const char *)v26);
LABEL_27:
      FsFltWil::Details::ReleaseRundownProtectionCacheAware(
        (FsFltWil::Details *)&v38,
        (struct FsFltWil::Details::RundownRefCacheAware *)v9);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
      if ( v37 )
        utl::_RefCountBase::_DecStrong(v37);
      FltReleaseContext(v8);
      goto LABEL_48;
    }
    v35[0] = off_14007E908;
    v35[13] = v35;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(v44, v34);
    Entry = 0;
    v17 = UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(
            a1,
            (const struct _FLT_CALLBACK_DATA *)a2,
            (struct _FLT_RELATED_OBJECTS *)v8,
            (const struct UnionFs::UfsStreamHandleCtx *)v30,
            (__int64)v36,
            (UnionFs::CleanupContext **)&Entry,
            (UnionFs::StackEventTracer *)v44);
    v18 = v46;
    v19 = v17;
    if ( v46 )
    {
      --v46;
      v9 = 120LL * (unsigned __int16)(v18 - 1);
      v20 = *(_QWORD *)((char *)v45 + v9);
      *(_QWORD *)((char *)v45 + v9) = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
    }
    if ( v19 < 0 )
    {
      if ( v19 != -1073741567 )
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v19,
          (int)v44,
          (struct UnionFs::StackEventTracer *)0x4F6000B096ALL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
          "PUSH: Preparing for delete",
          (const char *)v28);
      v21 = Entry;
      if ( Entry )
      {
        UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)Entry);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 800), v21);
      }
      goto LABEL_27;
    }
    v22 = Entry;
    if ( Entry )
      goto LABEL_36;
    if ( (*(_DWORD *)v8 & 0x40) == 0 )
      goto LABEL_27;
    v32 = 0;
    v33 = v8;
    v31 = 0;
    v23 = (PVOID *)utl::make_unique<UnionFs::CleanupContext,UnionFs::CleanupContext,0>(&Entry, &v31);
    v22 = *v23;
    *v23 = 0;
    v24 = Entry;
    if ( Entry )
    {
      UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 800), v24);
    }
    UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)&v31);
    if ( v22 )
    {
      v8 = 0;
LABEL_36:
      *a3 = v22;
      FsFltWil::Details::ReleaseRundownProtectionCacheAware(
        (FsFltWil::Details *)&v38,
        (struct FsFltWil::Details::RundownRefCacheAware *)v9);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
      if ( v37 )
        utl::_RefCountBase::_DecStrong(v37);
      if ( v8 )
        FltReleaseContext(v8);
      v10 = 0;
      goto LABEL_48;
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)0xC000009ALL,
      (int)v44,
      (struct UnionFs::StackEventTracer *)0x28A000B097ALL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
      "PUSH: Allocating cleanup context",
      (const char *)v28);
  }
  FsFltWil::Details::ReleaseRundownProtectionCacheAware(
    (FsFltWil::Details *)&v38,
    (struct FsFltWil::Details::RundownRefCacheAware *)v9);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
  if ( v37 )
    utl::_RefCountBase::_DecStrong(v37);
LABEL_48:
  UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v44);
  return v10;
}

```

## disassembly

```asm
0x14002d6d0  mov     [rsp-8+arg_18], rbx
0x14002d6d5  push    rbp
0x14002d6d6  push    rsi
0x14002d6d7  push    rdi
0x14002d6d8  push    r12
0x14002d6da  push    r13
0x14002d6dc  push    r14
0x14002d6de  push    r15
0x14002d6e0  lea     rbp, [rsp-420h]
0x14002d6e8  sub     rsp, 520h
0x14002d6ef  mov     rax, cs:__security_cookie
0x14002d6f6  xor     rax, rsp
0x14002d6f9  mov     [rbp+450h+var_38], rax
0x14002d700  mov     r12, r8
0x14002d703  mov     r15, rdx
0x14002d706  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14002d709  mov     rdi, rcx
0x14002d70c  lea     rcx, [rbp+450h+var_328]; this
0x14002d713  mov     rdx, 2D1000B090Ch; unsigned __int64
0x14002d71d  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14002d722  xorps   xmm0, xmm0
0x14002d725  lea     rcx, [rbp+450h+var_3B0]; void *
0x14002d72c  xorps   xmm1, xmm1
0x14002d72f  xor     r13d, r13d
0x14002d732  mov     r14d, 88h
0x14002d738  mov     [rbp+450h+var_3A8], r13b
0x14002d73f  mov     r8d, r14d; Size
0x14002d742  mov     [rbp+450h+var_330], r13
0x14002d749  xor     edx, edx; Val
0x14002d74b  movdqu  xmmword ptr [rbp+450h+Context], xmm0
0x14002d753  movdqu  xmmword ptr [rbp+98h], xmm1
0x14002d75b  call    memset
0x14002d760  mov     rdx, [r15+20h]; FileObject
0x14002d764  lea     rax, [rbp+450h+var_328]
0x14002d76b  mov     rcx, [r15+18h]; Instance
0x14002d76f  lea     r9, [rbp+450h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14002d776  mov     [rsp+550h+var_530], rax; struct UnionFs::StackEventTracer *
0x14002d77b  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14002d780  mov     esi, eax
0x14002d782  test    eax, eax
0x14002d784  jns     short loc_14002D7CC
0x14002d786  lea     rax, aPushGettingHan; "PUSH: Getting handle ctx"
0x14002d78d  mov     r8, 2D5000B091Eh; struct UnionFs::StackEventTracer *
0x14002d797  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002d79e  mov     [rsp+550h+var_530], rax; char *
0x14002d7a3  lea     rdx, [rbp+450h+var_328]; int
0x14002d7aa  mov     ecx, esi; this
0x14002d7ac  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d7b1  lea     rcx, [rbp+450h+var_328]; this
0x14002d7b8  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14002d7bd  mov     dword ptr [rbp+450h+var_328], r13d
0x14002d7c4  mov     [rbp+450h+var_104], r13w
0x14002d7cc  mov     rax, [rbp+450h+Context+8]
0x14002d7d3  lea     rdx, [rbp+450h+var_3A0]
0x14002d7da  mov     rbx, [rbp+450h+Context]
0x14002d7e1  lea     rcx, [rbp+450h+var_440]
0x14002d7e5  mov     [rbp+450h+var_460], rax
0x14002d7e9  xorps   xmm0, xmm0
0x14002d7ec  mov     rax, [rbp+450h+var_3B8]
0x14002d7f3  mov     [rbp+450h+var_458], rax
0x14002d7f7  mov     rax, [rbp+450h+var_3B0]
0x14002d7fe  mov     [rbp+450h+var_450], rax
0x14002d802  mov     al, [rbp+450h+var_3A8]
0x14002d808  mov     [rbp+450h+var_448], al
0x14002d80b  mov     [rbp+450h+Context], r13
0x14002d812  movdqu  xmmword ptr [rbp+450h+Context+8], xmm0
0x14002d81a  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14002d81f  mov     r8, r14; Size
0x14002d822  lea     rcx, [rbp+450h+var_3B0]; void *
0x14002d829  xor     edx, edx; Val
0x14002d82b  call    memset
0x14002d830  mov     r14d, 1
0x14002d836  test    rbx, rbx
0x14002d839  jz      loc_14002DBF7
0x14002d83f  mov     rcx, [r15+20h]; this
0x14002d843  mov     rax, [rcx+18h]
0x14002d847  test    rax, rax
0x14002d84a  jz      loc_14002D90A
0x14002d850  mov     edx, 4341h
0x14002d855  cmp     [rax], dx
0x14002d858  jnz     loc_14002D90A
0x14002d85e  test    [rbx], r14b
0x14002d861  jz      loc_14002D90A
0x14002d867  mov     rax, [rbp+450h+var_460]
0x14002d86b  lea     rdx, [rbp+450h+var_328]
0x14002d872  mov     [rsp+550h+var_528], rdx; char *
0x14002d877  mov     r9, rbx; struct UnionFs::UfsStreamHandleCtx *
0x14002d87a  mov     rdx, rdi; struct _FLT_CALLBACK_DATA *
0x14002d87d  mov     [rsp+550h+var_530], rax; struct UnionFs::UfsUnionCtx *
0x14002d882  mov     r8, r15; struct _FLT_RELATED_OBJECTS *
0x14002d885  call    ?Cleanup@UfsShadowFileObject@UnionFs@@QEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsShadowFileObject::Cleanup(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &)
0x14002d88a  test    eax, eax
0x14002d88c  jns     short loc_14002D8B9
0x14002d88e  lea     rcx, aPushCleaningUp; "PUSH: Cleaning up SFO"
0x14002d895  mov     r8, 0C1000B093Ah; struct UnionFs::StackEventTracer *
0x14002d89f  mov     [rsp+550h+var_530], rcx; char *
0x14002d8a4  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002d8ab  mov     ecx, eax; this
0x14002d8ad  lea     rdx, [rbp+450h+var_328]; int
0x14002d8b4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d8b9  lea     rcx, [rbp+450h+var_450]; this
0x14002d8bd  mov     [rdi+18h], r13d
0x14002d8c1  mov     [rdi+20h], r13
0x14002d8c5  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002d8ca  mov     rcx, [rbp+450h+var_3D0]
0x14002d8d1  test    rcx, rcx
0x14002d8d4  jz      short loc_14002D8E2
0x14002d8d6  mov     rax, [rcx]
0x14002d8d9  mov     rax, [rax+18h]
0x14002d8dd  call    _guard_dispatch_icall
0x14002d8e2  mov     rcx, [rbp+450h+var_458]; this
0x14002d8e6  test    rcx, rcx
0x14002d8e9  jz      short loc_14002D8F0
0x14002d8eb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d8f0  mov     rcx, rbx; Context
0x14002d8f3  call    cs:__imp_FltReleaseContext
0x14002d8fa  nop     dword ptr [rax+rax+00h]
0x14002d8ff  mov     r14d, 4
0x14002d905  jmp     loc_14002DC26
0x14002d90a  test    esi, esi
0x14002d90c  js      loc_14002DAA9
0x14002d912  mov     rdx, rcx; FileObject
0x14002d915  mov     [rsp+550h+var_500], r13
0x14002d91a  mov     rcx, [r15+18h]; Instance
0x14002d91e  lea     r9, [rbp+450h+var_328]
0x14002d925  lea     r8, [rsp+550h+var_500]
0x14002d92a  mov     dword ptr [rsp+550h+var_530], r13d; int
0x14002d92f  call    ?FltGetSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@K@Z; UnionFs::UfsFileCtx::FltGetSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,ulong)
0x14002d934  test    eax, eax
0x14002d936  jns     short loc_14002D976
0x14002d938  lea     rcx, aPushGettingFil_1; "PUSH: Getting file ctx"
0x14002d93f  mov     r8, 2D8000B0951h; struct UnionFs::StackEventTracer *
0x14002d949  mov     [rsp+550h+var_530], rcx; char *
0x14002d94e  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002d955  mov     ecx, eax; this
0x14002d957  lea     rdx, [rbp+450h+var_328]; int
0x14002d95e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d963  mov     rcx, [rsp+550h+var_500]
0x14002d968  test    rcx, rcx
0x14002d96b  jz      loc_14002DAA9
0x14002d971  jmp     loc_14002DA9D
0x14002d976  lea     rax, off_14007E908
0x14002d97d  mov     [rbp+450h+var_4D0], rax
0x14002d981  lea     rdx, [rsp+550h+var_4D8]
0x14002d986  lea     rax, [rbp+450h+var_4D0]
0x14002d98a  lea     rcx, [rbp+450h+var_328]
0x14002d991  mov     [rbp+450h+var_468], rax
0x14002d995  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x14002d99a  mov     rax, [rbp+450h+var_460]
0x14002d99e  lea     rcx, [rbp+450h+var_328]
0x14002d9a5  mov     rsi, [rsp+550h+var_500]
0x14002d9aa  mov     r8, rbx
0x14002d9ad  mov     [rsp+550h+var_520], rcx
0x14002d9b2  mov     r9, rsi
0x14002d9b5  lea     rcx, [rsp+550h+Entry]
0x14002d9ba  mov     [rsp+550h+Entry], r13
0x14002d9bf  mov     [rsp+550h+var_528], rcx; char *
0x14002d9c4  mov     rdx, r15
0x14002d9c7  mov     rcx, rdi
0x14002d9ca  mov     [rsp+550h+var_530], rax
0x14002d9cf  call    ?PrepareForDeleteOnCleanupIfNeeded@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVUfsUnionCtx@2@AEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsFileCtx &,UnionFs::UfsUnionCtx &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &,UnionFs::StackEventTracer &)
0x14002d9d4  movzx   ecx, [rbp+450h+var_13E]
0x14002d9db  mov     edi, eax
0x14002d9dd  test    cx, cx
0x14002d9e0  jz      short loc_14002DA19
0x14002d9e2  mov     eax, 0FFFFh
0x14002d9e7  add     cx, ax
0x14002d9ea  mov     [rbp+450h+var_13E], cx
0x14002d9f1  movzx   ecx, cx
0x14002d9f4  imul    rdx, rcx, 78h ; 'x'
0x14002d9f8  mov     rcx, [rbp+rdx+450h+var_2B0]
0x14002da00  mov     [rbp+rdx+450h+var_2B0], r13
0x14002da08  test    rcx, rcx
0x14002da0b  jz      short loc_14002DA19
0x14002da0d  mov     rax, [rcx]
0x14002da10  mov     rax, [rax+18h]
0x14002da14  call    _guard_dispatch_icall
0x14002da19  test    edi, edi
0x14002da1b  jns     short loc_14002DA81
0x14002da1d  cmp     edi, 0C0000101h
0x14002da23  jz      short loc_14002DA50
0x14002da25  lea     rax, aPushPreparingF_1; "PUSH: Preparing for delete"
0x14002da2c  mov     r8, 4F6000B096Ah; struct UnionFs::StackEventTracer *
0x14002da36  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002da3d  mov     [rsp+550h+var_530], rax; char *
0x14002da42  lea     rdx, [rbp+450h+var_328]; int
0x14002da49  mov     ecx, edi; this
0x14002da4b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002da50  mov     rdi, [rsp+550h+Entry]
0x14002da55  test    rdi, rdi
0x14002da58  jz      short loc_14002DA95
0x14002da5a  mov     rcx, rdi; this
0x14002da5d  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x14002da62  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002da69  mov     rdx, rdi; Entry
0x14002da6c  add     rcx, 320h; Lookaside
0x14002da73  call    cs:__imp_ExFreeToLookasideListEx
0x14002da7a  nop     dword ptr [rax+rax+00h]
0x14002da7f  jmp     short loc_14002DA95
0x14002da81  mov     rdi, [rsp+550h+Entry]
0x14002da86  test    rdi, rdi
0x14002da89  jnz     loc_14002DB55
0x14002da8f  mov     eax, [rbx]
0x14002da91  test    al, 40h
0x14002da93  jnz     short loc_14002DAEC
0x14002da95  test    rsi, rsi
0x14002da98  jz      short loc_14002DAA9
0x14002da9a  mov     rcx, rsi; Context
0x14002da9d  call    cs:__imp_FltReleaseContext
0x14002daa4  nop     dword ptr [rax+rax+00h]
0x14002daa9  lea     rcx, [rbp+450h+var_450]; this
0x14002daad  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002dab2  mov     rcx, [rbp+450h+var_3D0]
0x14002dab9  test    rcx, rcx
0x14002dabc  jz      short loc_14002DACA
0x14002dabe  mov     rax, [rcx]
0x14002dac1  mov     rax, [rax+18h]
0x14002dac5  call    _guard_dispatch_icall
0x14002daca  mov     rcx, [rbp+450h+var_458]; this
0x14002dace  test    rcx, rcx
0x14002dad1  jz      short loc_14002DAD8
0x14002dad3  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002dad8  mov     rcx, rbx; Context
0x14002dadb  call    cs:__imp_FltReleaseContext
0x14002dae2  nop     dword ptr [rax+rax+00h]
0x14002dae7  jmp     loc_14002DC26
0x14002daec  xorps   xmm0, xmm0
0x14002daef  mov     [rsp+550h+var_4E8], r13
0x14002daf4  lea     rdx, [rsp+550h+var_4F8]
0x14002daf9  mov     [rsp+550h+var_4E0], rbx
0x14002dafe  lea     rcx, [rsp+550h+Entry]
0x14002db03  movdqu  [rsp+550h+var_4F8], xmm0
0x14002db09  call    ??$make_unique@UCleanupContext@UnionFs@@U12@$0A@@utl@@YA?AV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@0@$$QEAUCleanupContext@UnionFs@@@Z; utl::make_unique<UnionFs::CleanupContext,UnionFs::CleanupContext,0>(UnionFs::CleanupContext &&)
0x14002db0e  mov     rdi, [rax]
0x14002db11  mov     [rax], r13
0x14002db14  mov     rbx, [rsp+550h+Entry]
0x14002db19  test    rbx, rbx
0x14002db1c  jz      short loc_14002DB43
0x14002db1e  mov     rcx, rbx; this
0x14002db21  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x14002db26  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002db2d  mov     rdx, rbx; Entry
0x14002db30  add     rcx, 320h; Lookaside
0x14002db37  call    cs:__imp_ExFreeToLookasideListEx
0x14002db3e  nop     dword ptr [rax+rax+00h]
0x14002db43  lea     rcx, [rsp+550h+var_4F8]; this
0x14002db48  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x14002db4d  test    rdi, rdi
0x14002db50  jz      short loc_14002DBB5
0x14002db52  mov     rbx, r13
0x14002db55  mov     [r12], rdi
0x14002db59  test    rsi, rsi
0x14002db5c  jz      short loc_14002DB6D
0x14002db5e  mov     rcx, rsi; Context
0x14002db61  call    cs:__imp_FltReleaseContext
0x14002db68  nop     dword ptr [rax+rax+00h]
0x14002db6d  lea     rcx, [rbp+450h+var_450]; this
0x14002db71  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002db76  mov     rcx, [rbp+450h+var_3D0]
0x14002db7d  test    rcx, rcx
0x14002db80  jz      short loc_14002DB8E
0x14002db82  mov     rax, [rcx]
0x14002db85  mov     rax, [rax+18h]
0x14002db89  call    _guard_dispatch_icall
0x14002db8e  mov     rcx, [rbp+450h+var_458]; this
0x14002db92  test    rcx, rcx
0x14002db95  jz      short loc_14002DB9C
0x14002db97  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002db9c  test    rbx, rbx
0x14002db9f  jz      short loc_14002DBB0
0x14002dba1  mov     rcx, rbx; Context
0x14002dba4  call    cs:__imp_FltReleaseContext
0x14002dbab  nop     dword ptr [rax+rax+00h]
0x14002dbb0  mov     r14d, r13d
0x14002dbb3  jmp     short loc_14002DC26
0x14002dbb5  lea     rax, aPushAllocating_20; "PUSH: Allocating cleanup context"
0x14002dbbc  mov     r8, 28A000B097Ah; struct UnionFs::StackEventTracer *
0x14002dbc6  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002dbcd  mov     [rsp+550h+var_530], rax; char *
0x14002dbd2  lea     rdx, [rbp+450h+var_328]; int
0x14002dbd9  mov     ecx, 0C000009Ah; this
0x14002dbde  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002dbe3  test    rsi, rsi
0x14002dbe6  jz      short loc_14002DBF7
0x14002dbe8  mov     rcx, rsi; Context
0x14002dbeb  call    cs:__imp_FltReleaseContext
0x14002dbf2  nop     dword ptr [rax+rax+00h]
0x14002dbf7  lea     rcx, [rbp+450h+var_450]; this
0x14002dbfb  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002dc00  mov     rcx, [rbp+450h+var_3D0]
0x14002dc07  test    rcx, rcx
0x14002dc0a  jz      short loc_14002DC18
0x14002dc0c  mov     rax, [rcx]
0x14002dc0f  mov     rax, [rax+18h]
0x14002dc13  call    _guard_dispatch_icall
0x14002dc18  mov     rcx, [rbp+450h+var_458]; this
0x14002dc1c  test    rcx, rcx
0x14002dc1f  jz      short loc_14002DC26
0x14002dc21  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002dc26  lea     rcx, [rbp+450h+Context]; this
  ... truncated ...
```
