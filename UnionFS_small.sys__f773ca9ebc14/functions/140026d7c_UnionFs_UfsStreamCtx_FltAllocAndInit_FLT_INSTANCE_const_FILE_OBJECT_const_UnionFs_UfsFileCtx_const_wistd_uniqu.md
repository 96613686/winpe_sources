# UnionFs::UfsStreamCtx::FltAllocAndInit(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsFileCtx const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140026d7c`
- end: `0x14002712a`
- name: `?FltAllocAndInit@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBVUfsFileCtx@2@AEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `942`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x140027e58`

## callees

- `0x140026d7c`
- `0x1400276c4`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140057c38`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140026ee0`
- `ntoskrnl!KeInitializeEvent` at `0x140026ef4`
- `ntoskrnl!KeInitializeEvent` at `0x140026ee0`
- `ntoskrnl!KeInitializeEvent` at `0x140026ef4`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140026f0a`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140026f0a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140026f25`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140026f25`
- `FLTMGR!FltAllocateContext` at `0x140026df8`
- `FLTMGR!FltAllocateContext` at `0x140026df8`
- `FLTMGR!FltQueryInformationFile` at `0x140027000`
- `FLTMGR!FltQueryInformationFile` at `0x140027000`
- `FLTMGR!FltReleaseContext` at `0x140026dc1`
- `FLTMGR!FltReleaseContext` at `0x1400270b9`
- `FLTMGR!FltReleaseContext` at `0x1400270c8`
- `FLTMGR!FltReleaseContext` at `0x1400270e7`
- `FLTMGR!FltReleaseContext` at `0x1400270fb`
- `FLTMGR!FltReleaseContext` at `0x140026dc1`
- `FLTMGR!FltReleaseContext` at `0x1400270b9`
- `FLTMGR!FltReleaseContext` at `0x1400270c8`
- `FLTMGR!FltReleaseContext` at `0x1400270e7`
- `FLTMGR!FltReleaseContext` at `0x1400270fb`

## string_xrefs

- `0x140027074`: `UnionFs::UfsStreamCtx::CreateShadowFsContext`

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
0x140026d7c  push    rbp
0x140026d7e  push    rbx
0x140026d7f  push    rsi
0x140026d80  push    rdi
0x140026d81  push    r12
0x140026d83  push    r13
0x140026d85  push    r14
0x140026d87  push    r15
0x140026d89  lea     rbp, [rsp-17h]
0x140026d8e  sub     rsp, 0B8h
0x140026d95  mov     rax, cs:__security_cookie
0x140026d9c  xor     rax, rsp
0x140026d9f  mov     [rbp+4Fh+var_50], rax
0x140026da3  mov     rdi, qword ptr [rbp+4Fh+arg_20]
0x140026da7  xor     esi, esi
0x140026da9  mov     r12, rcx
0x140026dac  mov     [rbp+4Fh+var_A8], r8
0x140026db0  mov     rcx, [r9]; Context
0x140026db3  mov     r15, r9
0x140026db6  mov     [r9], rsi
0x140026db9  mov     r13, rdx
0x140026dbc  test    rcx, rcx
0x140026dbf  jz      short loc_140026DCD
0x140026dc1  call    cs:__imp_FltReleaseContext
0x140026dc8  nop     dword ptr [rax+rax+00h]
0x140026dcd  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140026dd4  lea     rax, [rbp+4Fh+var_B8]
0x140026dd8  mov     [rbp+4Fh+var_B8], rsi
0x140026ddc  mov     r14d, 0A8h
0x140026de2  mov     edx, 8; ContextType
0x140026de7  mov     [rsp+0F0h+ReturnedContext], rax; ReturnedContext
0x140026dec  mov     r9d, 200h; PoolType
0x140026df2  mov     r8d, r14d; ContextSize
0x140026df5  mov     rcx, [rcx]; Filter
0x140026df8  call    cs:__imp_FltAllocateContext
0x140026dff  nop     dword ptr [rax+rax+00h]
0x140026e04  mov     ebx, eax
0x140026e06  test    eax, eax
0x140026e08  jns     short loc_140026E38
0x140026e0a  lea     rax, aApiFltallocate_0; "API: FltAllocateContext"
0x140026e11  mov     r8, 0CB000A03A8h; struct UnionFs::StackEventTracer *
0x140026e1b  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x140026e22  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140026e27  mov     rdx, rdi; int
0x140026e2a  mov     ecx, ebx; this
0x140026e2c  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140026e31  mov     eax, ebx
0x140026e33  jmp     loc_140027109
0x140026e38  mov     rcx, [rbp+4Fh+var_B8]; void *
0x140026e3c  mov     r8, r14; Size
0x140026e3f  xor     edx, edx; Val
0x140026e41  call    memset
0x140026e46  mov     r14, [rbp+4Fh+var_B8]
0x140026e4a  xorps   xmm0, xmm0
0x140026e4d  xorps   xmm1, xmm1
0x140026e50  xor     r8d, r8d; State
0x140026e53  movups  xmmword ptr [r14], xmm0
0x140026e57  lea     rax, [r14+28h]
0x140026e5b  movups  xmmword ptr [r14+10h], xmm1
0x140026e60  mov     [rax], rax
0x140026e63  lea     rbx, [r14+88h]
0x140026e6a  mov     [r14+20h], rsi
0x140026e6e  lea     rcx, [r14+60h]; Event
0x140026e72  mov     [rax+8], rax
0x140026e76  mov     [rax+10h], rax
0x140026e7a  mov     [rax+18h], rsi
0x140026e7e  xor     eax, eax
0x140026e80  movups  xmmword ptr [r14+48h], xmm0
0x140026e85  movups  xmmword ptr [r14+58h], xmm0
0x140026e8a  lea     edx, [rax+1]; Type
0x140026e8d  movups  xmmword ptr [r14+68h], xmm0
0x140026e92  mov     [r14+78h], rax
0x140026e96  movups  xmm0, xmmword ptr [r14+48h]
0x140026e9b  movups  xmm1, xmmword ptr [r14+58h]
0x140026ea0  movups  [rbp+4Fh+var_A0], xmm0
0x140026ea4  movups  xmm0, xmmword ptr [r14+68h]
0x140026ea9  movups  [rbp+4Fh+var_90], xmm1
0x140026ead  movsd   xmm1, qword ptr [r14+78h]
0x140026eb3  mov     [r14+80h], rsi
0x140026eba  movups  [rbp+4Fh+var_80], xmm0
0x140026ebe  xorps   xmm0, xmm0
0x140026ec1  movsd   [rbp+4Fh+var_70], xmm1
0x140026ec6  movups  xmmword ptr [rbx], xmm0
0x140026ec9  mov     [rbx+10h], rax
0x140026ecd  mov     [r14+0A0h], sil
0x140026ed4  mov     [r14+48h], edx
0x140026ed8  mov     [r14+50h], rsi
0x140026edc  mov     [r14+58h], esi
0x140026ee0  call    cs:__imp_KeInitializeEvent
0x140026ee7  nop     dword ptr [rax+rax+00h]
0x140026eec  xor     r8d, r8d; State
0x140026eef  xor     edx, edx; Type
0x140026ef1  mov     rcx, rbx; Event
0x140026ef4  call    cs:__imp_KeInitializeEvent
0x140026efb  nop     dword ptr [rax+rax+00h]
0x140026f00  mov     edx, 63734655h; PoolTag
0x140026f05  mov     ecx, 200h; PoolType
0x140026f0a  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140026f11  nop     dword ptr [rax+rax+00h]
0x140026f16  mov     rcx, [r14+80h]; RunRefCacheAware
0x140026f1d  mov     rbx, rax
0x140026f20  test    rcx, rcx
0x140026f23  jz      short loc_140026F31
0x140026f25  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140026f2c  nop     dword ptr [rax+rax+00h]
0x140026f31  mov     [r14+80h], rbx
0x140026f38  test    rbx, rbx
0x140026f3b  jnz     short loc_140026F6E
0x140026f3d  lea     rax, aOriginAllocati_75; "ORIGIN: Allocating rundown"
0x140026f44  mov     ebx, 0C000009Ah
0x140026f49  mov     ecx, ebx; this
0x140026f4b  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140026f50  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x140026f57  mov     r8, 4BA000A03BAh; struct UnionFs::StackEventTracer *
0x140026f61  mov     rdx, rdi; int
0x140026f64  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140026f69  jmp     loc_1400270C5
0x140026f6e  mov     r9, rdi
0x140026f71  mov     [rbp+4Fh+Context], rsi
0x140026f75  lea     r8, [rbp+4Fh+Context]
0x140026f79  xor     edx, edx
0x140026f7b  mov     rcx, r12; Instance
0x140026f7e  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140026f83  mov     ebx, eax
0x140026f85  test    eax, eax
0x140026f87  jns     short loc_140026FC2
0x140026f89  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x140026f90  mov     r8, 37C000A03C1h; struct UnionFs::StackEventTracer *
0x140026f9a  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x140026fa1  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140026fa6  mov     rdx, rdi; int
0x140026fa9  mov     ecx, ebx; this
0x140026fab  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140026fb0  mov     rcx, [rbp+4Fh+Context]
0x140026fb4  test    rcx, rcx
0x140026fb7  jz      loc_1400270C5
0x140026fbd  jmp     loc_1400270B9
0x140026fc2  mov     rsi, [rbp+4Fh+Context]
0x140026fc6  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140026fca  xor     eax, eax
0x140026fcc  mov     r9d, 18h; Length
0x140026fd2  mov     rdx, r13; FileObject
0x140026fd5  mov     rcx, r12; Instance
0x140026fd8  movups  xmm0, xmmword ptr [rsi+8]
0x140026fdc  movdqu  xmmword ptr [r14], xmm0
0x140026fe1  mov     [rbp+4Fh+var_58], rax
0x140026fe5  mov     [rbp+4Fh+var_C0], eax
0x140026fe8  xorps   xmm0, xmm0
0x140026feb  lea     rax, [rbp+4Fh+var_C0]
0x140026fef  mov     [rsp+0F0h+LengthReturned], rax; char *
0x140026ff4  mov     dword ptr [rsp+0F0h+ReturnedContext], 3Bh ; ';'; FileInformationClass
0x140026ffc  movups  [rbp+4Fh+FileInformation], xmm0
0x140027000  call    cs:__imp_FltQueryInformationFile
0x140027007  nop     dword ptr [rax+rax+00h]
0x14002700c  mov     ebx, eax
0x14002700e  test    eax, eax
0x140027010  jns     short loc_14002703B
0x140027012  lea     rax, aApiQueryingFil; "API: Querying file ID"
0x140027019  mov     r8, 394000A03D0h; struct UnionFs::StackEventTracer *
0x140027023  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x14002702a  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x14002702f  mov     rdx, rdi; int
0x140027032  mov     ecx, ebx; this
0x140027034  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140027039  jmp     short loc_1400270B1
0x14002703b  movups  xmm0, [rbp+4Fh+FileInformation+8]
0x14002703f  mov     rdx, [rbp+4Fh+var_A8]
0x140027043  lea     r9, [r14+20h]
0x140027047  mov     r8, r13
0x14002704a  mov     [rsp+0F0h+ReturnedContext], rdi
0x14002704f  mov     rcx, r14
0x140027052  movdqu  xmmword ptr [r14+10h], xmm0
0x140027058  call    ?AllocAndInit@UfsFsContext@UnionFs@@SAJAEAVUfsStreamCtx@2@AEBVUfsFileCtx@2@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFsContext@UnionFs@@U?$default_delete@VUfsFsContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext::AllocAndInit(UnionFs::UfsStreamCtx &,UnionFs::UfsFileCtx const &,_FILE_OBJECT const &,utl::unique_ptr<UnionFs::UfsFsContext,utl::default_delete<UnionFs::UfsFsContext>> &,UnionFs::StackEventTracer &)
0x14002705d  mov     ebx, eax
0x14002705f  test    eax, eax
0x140027061  jns     short loc_1400270D9
0x140027063  lea     rax, aPushUfsfsconte_1; "PUSH: UfsFsContext::AllocAndInit"
0x14002706a  mov     r8, 11E000A047Dh; struct UnionFs::StackEventTracer *
0x140027074  lea     r9, aUnionfsUfsstre_1; "UnionFs::UfsStreamCtx::CreateShadowFsCo"...
0x14002707b  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x140027080  mov     rdx, rdi; int
0x140027083  mov     ecx, ebx; this
0x140027085  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002708a  lea     rax, aPushCreatingSh_1; "PUSH: Creating shadow FsContext"
0x140027091  mov     r8, 12A000A03D9h; struct UnionFs::StackEventTracer *
0x14002709b  lea     r9, aUnionfsUfsstre_8; "UnionFs::UfsStreamCtx::FltAllocAndInit"
0x1400270a2  mov     [rsp+0F0h+ReturnedContext], rax; char *
0x1400270a7  mov     rdx, rdi; int
0x1400270aa  mov     ecx, ebx; this
0x1400270ac  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400270b1  test    rsi, rsi
0x1400270b4  jz      short loc_1400270C5
0x1400270b6  mov     rcx, rsi; Context
0x1400270b9  call    cs:__imp_FltReleaseContext
0x1400270c0  nop     dword ptr [rax+rax+00h]
0x1400270c5  mov     rcx, r14; Context
0x1400270c8  call    cs:__imp_FltReleaseContext
0x1400270cf  nop     dword ptr [rax+rax+00h]
0x1400270d4  jmp     loc_140026E31
0x1400270d9  mov     rbx, [r15]
0x1400270dc  mov     [r15], r14
0x1400270df  test    rsi, rsi
0x1400270e2  jz      short loc_1400270F3
0x1400270e4  mov     rcx, rsi; Context
0x1400270e7  call    cs:__imp_FltReleaseContext
0x1400270ee  nop     dword ptr [rax+rax+00h]
0x1400270f3  test    rbx, rbx
0x1400270f6  jz      short loc_140027107
0x1400270f8  mov     rcx, rbx; Context
0x1400270fb  call    cs:__imp_FltReleaseContext
0x140027102  nop     dword ptr [rax+rax+00h]
0x140027107  xor     eax, eax
0x140027109  mov     rcx, [rbp+4Fh+var_50]
0x14002710d  xor     rcx, rsp; StackCookie
0x140027110  call    __security_check_cookie
0x140027115  add     rsp, 0B8h
0x14002711c  pop     r15
0x14002711e  pop     r14
0x140027120  pop     r13
0x140027122  pop     r12
0x140027124  pop     rdi
0x140027125  pop     rsi
0x140027126  pop     rbx
0x140027127  pop     rbp
0x140027128  retn
```
