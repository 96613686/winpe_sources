# UnionFs::UfsStreamCtx::FltAllocAndInit(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsFileCtx const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140026e1c`
- end: `0x1400271ca`
- name: `?FltAllocAndInit@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBVUfsFileCtx@2@AEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `942`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x140027ef8`

## callees

- `0x140026e1c`
- `0x140027764`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140057db8`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140026f80`
- `ntoskrnl!KeInitializeEvent` at `0x140026f94`
- `ntoskrnl!KeInitializeEvent` at `0x140026f80`
- `ntoskrnl!KeInitializeEvent` at `0x140026f94`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140026faa`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140026faa`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140026fc5`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140026fc5`
- `FLTMGR!FltAllocateContext` at `0x140026e98`
- `FLTMGR!FltAllocateContext` at `0x140026e98`
- `FLTMGR!FltQueryInformationFile` at `0x1400270a0`
- `FLTMGR!FltQueryInformationFile` at `0x1400270a0`
- `FLTMGR!FltReleaseContext` at `0x140026e61`
- `FLTMGR!FltReleaseContext` at `0x140027159`
- `FLTMGR!FltReleaseContext` at `0x140027168`
- `FLTMGR!FltReleaseContext` at `0x140027187`
- `FLTMGR!FltReleaseContext` at `0x14002719b`
- `FLTMGR!FltReleaseContext` at `0x140026e61`
- `FLTMGR!FltReleaseContext` at `0x140027159`
- `FLTMGR!FltReleaseContext` at `0x140027168`
- `FLTMGR!FltReleaseContext` at `0x140027187`
- `FLTMGR!FltReleaseContext` at `0x14002719b`

## string_xrefs

- `0x140027114`: `UnionFs::UfsStreamCtx::CreateShadowFsContext`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsStreamCtx::FltAllocAndInit(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        void **a4,
        __int64 a5)
{
  void *v6; // rcx
  NTSTATUS v9; // ebx
  _OWORD *v11; // r14
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v15; // rcx
  PEX_RUNDOWN_REF_CACHE_AWARE v16; // rbx
  PFLT_CONTEXT v17; // rcx
  PFLT_CONTEXT v18; // rsi
  __int64 v19; // rdx
  void *v20; // rbx
  const char *LengthReturned; // [rsp+28h] [rbp-79h]
  const char *LengthReturneda; // [rsp+28h] [rbp-79h]
  const char *LengthReturnedb; // [rsp+28h] [rbp-79h]
  ULONG v24; // [rsp+30h] [rbp-71h] BYREF
  PFLT_CONTEXT ReturnedContext; // [rsp+38h] [rbp-69h] BYREF
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-61h]
  __int64 v27; // [rsp+48h] [rbp-59h]
  __int128 v28; // [rsp+50h] [rbp-51h]
  __int128 v29; // [rsp+60h] [rbp-41h]
  __int128 v30; // [rsp+70h] [rbp-31h]
  __int64 v31; // [rsp+80h] [rbp-21h]
  _BYTE FileInformation[24]; // [rsp+88h] [rbp-19h] BYREF

  v27 = a3;
  v6 = *a4;
  *a4 = 0;
  if ( v6 )
    FltReleaseContext(v6);
  ReturnedContext = 0;
  v9 = FltAllocateContext(*(PFLT_FILTER *)UnionFs::g_FilterState, 8u, 0xA8u, (POOL_TYPE)512, &ReturnedContext);
  if ( v9 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v9,
      a5,
      (struct UnionFs::StackEventTracer *)0xCB000A03A8LL,
      (unsigned __int64)"UnionFs::UfsStreamCtx::FltAllocAndInit",
      "API: FltAllocateContext",
      LengthReturned);
    return (unsigned int)v9;
  }
  memset(ReturnedContext, 0, 0xA8u);
  v11 = ReturnedContext;
  *(_OWORD *)ReturnedContext = 0;
  v11[1] = 0;
  *((_QWORD *)v11 + 5) = (char *)v11 + 40;
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)v11 + 6) = (char *)v11 + 40;
  *((_QWORD *)v11 + 7) = (char *)v11 + 40;
  *((_QWORD *)v11 + 8) = 0;
  *(_OWORD *)((char *)v11 + 72) = 0;
  *(_OWORD *)((char *)v11 + 88) = 0;
  *(_OWORD *)((char *)v11 + 104) = 0;
  *((_QWORD *)v11 + 15) = 0;
  v12 = *(_OWORD *)((char *)v11 + 88);
  v28 = *(_OWORD *)((char *)v11 + 72);
  v13 = *(_OWORD *)((char *)v11 + 104);
  v29 = v12;
  *(_QWORD *)&v12 = *((_QWORD *)v11 + 15);
  *((_QWORD *)v11 + 16) = 0;
  v30 = v13;
  v31 = v12;
  *(_OWORD *)((char *)v11 + 136) = 0;
  *((_QWORD *)v11 + 19) = 0;
  *((_BYTE *)v11 + 160) = 0;
  *((_DWORD *)v11 + 18) = 1;
  *((_QWORD *)v11 + 10) = 0;
  *((_DWORD *)v11 + 22) = 0;
  KeInitializeEvent((PRKEVENT)v11 + 4, SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)((char *)v11 + 136), NotificationEvent, 0);
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x63734655u);
  v15 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v11 + 16);
  v16 = CacheAwareRundownProtection;
  if ( v15 )
    ExFreeCacheAwareRundownProtection(v15);
  *((_QWORD *)v11 + 16) = v16;
  if ( !v16 )
  {
    v9 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x4BA000A03BALL,
      (unsigned __int64)"UnionFs::UfsStreamCtx::FltAllocAndInit",
      "ORIGIN: Allocating rundown",
      LengthReturned);
LABEL_20:
    FltReleaseContext(v11);
    return (unsigned int)v9;
  }
  Context = 0;
  v9 = UnionFs::UfsInstanceCtx::FltGet(Instance);
  if ( v9 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v9,
      a5,
      (struct UnionFs::StackEventTracer *)0x37C000A03C1LL,
      (unsigned __int64)"UnionFs::UfsStreamCtx::FltAllocAndInit",
      "PUSH: Getting instance context",
      LengthReturned);
    v17 = Context;
    if ( !Context )
      goto LABEL_20;
LABEL_19:
    FltReleaseContext(v17);
    goto LABEL_20;
  }
  v18 = Context;
  *v11 = *(_OWORD *)((char *)Context + 8);
  v24 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v9 = FltQueryInformationFile(
         Instance,
         FileObject,
         FileInformation,
         0x18u,
         FileMaximumInformation|FileBothDirectoryInformation,
         &v24);
  if ( v9 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v9,
      a5,
      (struct UnionFs::StackEventTracer *)0x394000A03D0LL,
      (unsigned __int64)"UnionFs::UfsStreamCtx::FltAllocAndInit",
      "API: Querying file ID",
      LengthReturneda);
LABEL_17:
    if ( !v18 )
      goto LABEL_20;
    v17 = v18;
    goto LABEL_19;
  }
  v19 = v27;
  v11[1] = *(_OWORD *)&FileInformation[8];
  v9 = UnionFs::UfsFsContext::AllocAndInit(v11, v19, FileObject, v11 + 2, a5);
  if ( v9 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v9,
      a5,
      (struct UnionFs::StackEventTracer *)0x11E000A047DLL,
      (unsigned __int64)"UnionFs::UfsStreamCtx::CreateShadowFsContext",
      "PUSH: UfsFsContext::AllocAndInit",
      LengthReturneda);
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v9,
      a5,
      (struct UnionFs::StackEventTracer *)0x12A000A03D9LL,
      (unsigned __int64)"UnionFs::UfsStreamCtx::FltAllocAndInit",
      "PUSH: Creating shadow FsContext",
      LengthReturnedb);
    goto LABEL_17;
  }
  v20 = *a4;
  *a4 = v11;
  if ( v18 )
    FltReleaseContext(v18);
  if ( v20 )
    FltReleaseContext(v20);
  return 0;
}

```

## disassembly

```asm
0x140026e1c  push    rbp
0x140026e1e  push    rbx
0x140026e1f  push    rsi
0x140026e20  push    rdi
0x140026e21  push    r12
0x140026e23  push    r13
0x140026e25  push    r14
0x140026e27  push    r15
0x140026e29  lea     rbp, [rsp-17h]
0x140026e2e  sub     rsp, 0B8h
0x140026e35  mov     rax, cs:__security_cookie
0x140026e3c  xor     rax, rsp
0x140026e3f  mov     [rbp+4Fh+var_50], rax
0x140026e43  mov     rdi, qword ptr [rbp+4Fh+arg_20]
0x140026e47  xor     esi, esi
0x140026e49  mov     r12, rcx
0x140026e4c  mov     [rbp+4Fh+var_A8], r8
0x140026e50  mov     rcx, [r9]; Context
0x140026e53  mov     r15, r9
0x140026e56  mov     [r9], rsi
0x140026e59  mov     r13, rdx
0x140026e5c  test    rcx, rcx
0x140026e5f  jz      short loc_140026E6D
0x140026e61  call    cs:__imp_FltReleaseContext
0x140026e68  nop     dword ptr [rax+rax+00h]
0x140026e6d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140026e74  lea     rax, [rbp+4Fh+var_B8]
0x140026e78  mov     [rbp+4Fh+var_B8], rsi
0x140026e7c  mov     r14d, 0A8h
0x140026e82  mov     edx, 8; ContextType
0x140026e87  mov     [rsp+0F0h+ReturnedContext], rax; ReturnedContext
0x140026e8c  mov     r9d, 200h; PoolType
0x140026e92  mov     r8d, r14d; ContextSize
0x140026e95  mov     rcx, [rcx]; Filter
0x140026e98  call    cs:__imp_FltAllocateContext
0x140026e9f  nop     dword ptr [rax+rax+00h]
0x140026ea4  mov     ebx, eax
0x140026ea6  test    eax, eax
0x140026ea8  jns     short loc_140026ED8
0x140026eaa  lea     rax, aApiFltallocate_0; "API: FltAllocateContext"
0x140026eb1  mov     r8, 0CB000A03A8h; struct UnionFs::StackEventTracer *
0x140026ebb  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x140026ec2  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140026ec7  mov     rdx, rdi; int
0x140026eca  mov     ecx, ebx; this
0x140026ecc  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140026ed1  mov     eax, ebx
0x140026ed3  jmp     loc_1400271A9
0x140026ed8  mov     rcx, [rbp+4Fh+var_B8]; void *
0x140026edc  mov     r8, r14; Size
0x140026edf  xor     edx, edx; Val
0x140026ee1  call    memset
0x140026ee6  mov     r14, [rbp+4Fh+var_B8]
0x140026eea  xorps   xmm0, xmm0
0x140026eed  xorps   xmm1, xmm1
0x140026ef0  xor     r8d, r8d; State
0x140026ef3  movups  xmmword ptr [r14], xmm0
0x140026ef7  lea     rax, [r14+28h]
0x140026efb  movups  xmmword ptr [r14+10h], xmm1
0x140026f00  mov     [rax], rax
0x140026f03  lea     rbx, [r14+88h]
0x140026f0a  mov     [r14+20h], rsi
0x140026f0e  lea     rcx, [r14+60h]; Event
0x140026f12  mov     [rax+8], rax
0x140026f16  mov     [rax+10h], rax
0x140026f1a  mov     [rax+18h], rsi
0x140026f1e  xor     eax, eax
0x140026f20  movups  xmmword ptr [r14+48h], xmm0
0x140026f25  movups  xmmword ptr [r14+58h], xmm0
0x140026f2a  lea     edx, [rax+1]; Type
0x140026f2d  movups  xmmword ptr [r14+68h], xmm0
0x140026f32  mov     [r14+78h], rax
0x140026f36  movups  xmm0, xmmword ptr [r14+48h]
0x140026f3b  movups  xmm1, xmmword ptr [r14+58h]
0x140026f40  movups  [rbp+4Fh+var_A0], xmm0
0x140026f44  movups  xmm0, xmmword ptr [r14+68h]
0x140026f49  movups  [rbp+4Fh+var_90], xmm1
0x140026f4d  movsd   xmm1, qword ptr [r14+78h]
0x140026f53  mov     [r14+80h], rsi
0x140026f5a  movups  [rbp+4Fh+var_80], xmm0
0x140026f5e  xorps   xmm0, xmm0
0x140026f61  movsd   [rbp+4Fh+var_70], xmm1
0x140026f66  movups  xmmword ptr [rbx], xmm0
0x140026f69  mov     [rbx+10h], rax
0x140026f6d  mov     [r14+0A0h], sil
0x140026f74  mov     [r14+48h], edx
0x140026f78  mov     [r14+50h], rsi
0x140026f7c  mov     [r14+58h], esi
0x140026f80  call    cs:__imp_KeInitializeEvent
0x140026f87  nop     dword ptr [rax+rax+00h]
0x140026f8c  xor     r8d, r8d; State
0x140026f8f  xor     edx, edx; Type
0x140026f91  mov     rcx, rbx; Event
0x140026f94  call    cs:__imp_KeInitializeEvent
0x140026f9b  nop     dword ptr [rax+rax+00h]
0x140026fa0  mov     edx, 63734655h; PoolTag
0x140026fa5  mov     ecx, 200h; PoolType
0x140026faa  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140026fb1  nop     dword ptr [rax+rax+00h]
0x140026fb6  mov     rcx, [r14+80h]; RunRefCacheAware
0x140026fbd  mov     rbx, rax
0x140026fc0  test    rcx, rcx
0x140026fc3  jz      short loc_140026FD1
0x140026fc5  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140026fcc  nop     dword ptr [rax+rax+00h]
0x140026fd1  mov     [r14+80h], rbx
0x140026fd8  test    rbx, rbx
0x140026fdb  jnz     short loc_14002700E
0x140026fdd  lea     rax, aOriginAllocati_76; "ORIGIN: Allocating rundown"
0x140026fe4  mov     ebx, 0C000009Ah
0x140026fe9  mov     ecx, ebx; this
0x140026feb  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140026ff0  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x140026ff7  mov     r8, 4BA000A03BAh; struct UnionFs::StackEventTracer *
0x140027001  mov     rdx, rdi; int
0x140027004  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140027009  jmp     loc_140027165
0x14002700e  mov     r9, rdi
0x140027011  mov     [rbp+4Fh+Context], rsi
0x140027015  lea     r8, [rbp+4Fh+Context]
0x140027019  xor     edx, edx
0x14002701b  mov     rcx, r12; Instance
0x14002701e  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140027023  mov     ebx, eax
0x140027025  test    eax, eax
0x140027027  jns     short loc_140027062
0x140027029  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x140027030  mov     r8, 37C000A03C1h; struct UnionFs::StackEventTracer *
0x14002703a  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x140027041  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140027046  mov     rdx, rdi; int
0x140027049  mov     ecx, ebx; this
0x14002704b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140027050  mov     rcx, [rbp+4Fh+Context]
0x140027054  test    rcx, rcx
0x140027057  jz      loc_140027165
0x14002705d  jmp     loc_140027159
0x140027062  mov     rsi, [rbp+4Fh+Context]
0x140027066  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14002706a  xor     eax, eax
0x14002706c  mov     r9d, 18h; Length
0x140027072  mov     rdx, r13; FileObject
0x140027075  mov     rcx, r12; Instance
0x140027078  movups  xmm0, xmmword ptr [rsi+8]
0x14002707c  movdqu  xmmword ptr [r14], xmm0
0x140027081  mov     [rbp+4Fh+var_58], rax
0x140027085  mov     [rbp+4Fh+var_C0], eax
0x140027088  xorps   xmm0, xmm0
0x14002708b  lea     rax, [rbp+4Fh+var_C0]
0x14002708f  mov     [rsp+0F0h+LengthReturned], rax; char *
0x140027094  mov     dword ptr [rsp+0F0h+ReturnedContext], 3Bh ; ';'; FileInformationClass
0x14002709c  movups  [rbp+4Fh+FileInformation], xmm0
0x1400270a0  call    cs:__imp_FltQueryInformationFile
0x1400270a7  nop     dword ptr [rax+rax+00h]
0x1400270ac  mov     ebx, eax
0x1400270ae  test    eax, eax
0x1400270b0  jns     short loc_1400270DB
0x1400270b2  lea     rax, aApiQueryingFil; "API: Querying file ID"
0x1400270b9  mov     r8, 394000A03D0h; struct UnionFs::StackEventTracer *
0x1400270c3  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x1400270ca  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x1400270cf  mov     rdx, rdi; int
0x1400270d2  mov     ecx, ebx; this
0x1400270d4  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400270d9  jmp     short loc_140027151
0x1400270db  movups  xmm0, [rbp+4Fh+FileInformation+8]
0x1400270df  mov     rdx, [rbp+4Fh+var_A8]
0x1400270e3  lea     r9, [r14+20h]
0x1400270e7  mov     r8, r13
0x1400270ea  mov     [rsp+0F0h+ReturnedContext], rdi
0x1400270ef  mov     rcx, r14
0x1400270f2  movdqu  xmmword ptr [r14+10h], xmm0
0x1400270f8  call    ?AllocAndInit@UfsFsContext@UnionFs@@SAJAEAVUfsStreamCtx@2@AEBVUfsFileCtx@2@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFsContext@UnionFs@@U?$default_delete@VUfsFsContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext::AllocAndInit(UnionFs::UfsStreamCtx &,UnionFs::UfsFileCtx const &,_FILE_OBJECT const &,utl::unique_ptr<UnionFs::UfsFsContext,utl::default_delete<UnionFs::UfsFsContext>> &,UnionFs::StackEventTracer &)
0x1400270fd  mov     ebx, eax
0x1400270ff  test    eax, eax
0x140027101  jns     short loc_140027179
0x140027103  lea     rax, aPushUfsfsconte_1; "PUSH: UfsFsContext::AllocAndInit"
0x14002710a  mov     r8, 11E000A047Dh; struct UnionFs::StackEventTracer *
0x140027114  lea     r9, aUnionfsUfsstre_1; "UnionFs::UfsStreamCtx::CreateShadowFsCo"...
0x14002711b  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140027120  mov     rdx, rdi; int
0x140027123  mov     ecx, ebx; this
0x140027125  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002712a  lea     rax, aPushCreatingSh_1; "PUSH: Creating shadow FsContext"
0x140027131  mov     r8, 12A000A03D9h; struct UnionFs::StackEventTracer *
0x14002713b  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x140027142  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140027147  mov     rdx, rdi; int
0x14002714a  mov     ecx, ebx; this
0x14002714c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140027151  test    rsi, rsi
0x140027154  jz      short loc_140027165
0x140027156  mov     rcx, rsi; Context
0x140027159  call    cs:__imp_FltReleaseContext
0x140027160  nop     dword ptr [rax+rax+00h]
0x140027165  mov     rcx, r14; Context
0x140027168  call    cs:__imp_FltReleaseContext
0x14002716f  nop     dword ptr [rax+rax+00h]
0x140027174  jmp     loc_140026ED1
0x140027179  mov     rbx, [r15]
0x14002717c  mov     [r15], r14
0x14002717f  test    rsi, rsi
0x140027182  jz      short loc_140027193
0x140027184  mov     rcx, rsi; Context
0x140027187  call    cs:__imp_FltReleaseContext
0x14002718e  nop     dword ptr [rax+rax+00h]
0x140027193  test    rbx, rbx
0x140027196  jz      short loc_1400271A7
0x140027198  mov     rcx, rbx; Context
0x14002719b  call    cs:__imp_FltReleaseContext
0x1400271a2  nop     dword ptr [rax+rax+00h]
0x1400271a7  xor     eax, eax
0x1400271a9  mov     rcx, [rbp+4Fh+var_50]
0x1400271ad  xor     rcx, rsp; StackCookie
0x1400271b0  call    __security_check_cookie
0x1400271b5  add     rsp, 0B8h
0x1400271bc  pop     r15
0x1400271be  pop     r14
0x1400271c0  pop     r13
0x1400271c2  pop     r12
0x1400271c4  pop     rdi
0x1400271c5  pop     rsi
0x1400271c6  pop     rbx
0x1400271c7  pop     rbp
0x1400271c8  retn
```
