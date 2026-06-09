# UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory(_FLT_CALLBACK_DATA const &,_FLT_FILE_NAME_INFORMATION const &,_EJOB const &,bool,bool *,UnionFs::StackEventTracer &)

- ea: `0x1400628e4`
- end: `0x140062e4e`
- name: `?OpenAndCheckForEmptyDirectory@UfsUnionCtx@UnionFs@@QEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_FILE_NAME_INFORMATION@@AEBU_EJOB@@_NPEA_NAEAVStackEventTracer@2@@Z`
- size: `1386`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_FILE_NAME_INFORMATION *, const struct _EJOB *, bool, bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14002e3c8`

## callees

- `0x14000f7fc`
- `0x140027178`
- `0x14002793c`
- `0x140028450`
- `0x140029560`
- `0x14002ab18`
- `0x140056afc`
- `0x14005a438`
- `0x1400628e4`
- `0x14006f8b8`
- `0x140072c08`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!PsDereferenceSiloContext` at `0x1400629b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062d1e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062e24`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400629b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062d1e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062e24`
- `ntoskrnl!ObfDereferenceObject` at `0x140062a7d`
- `ntoskrnl!ObfDereferenceObject` at `0x140062cf5`
- `ntoskrnl!ObfDereferenceObject` at `0x140062dfb`
- `ntoskrnl!ObfDereferenceObject` at `0x140062a7d`
- `ntoskrnl!ObfDereferenceObject` at `0x140062cf5`
- `ntoskrnl!ObfDereferenceObject` at `0x140062dfb`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062a64`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062b5b`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062cd8`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062dde`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062a64`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062b5b`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062cd8`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062dde`
- `FLTMGR!FltClose` at `0x140062a92`
- `FLTMGR!FltClose` at `0x140062d0a`
- `FLTMGR!FltClose` at `0x140062e10`
- `FLTMGR!FltClose` at `0x140062a92`
- `FLTMGR!FltClose` at `0x140062d0a`
- `FLTMGR!FltClose` at `0x140062e10`
- `FLTMGR!FltReleaseContext` at `0x140062c29`
- `FLTMGR!FltReleaseContext` at `0x140062cb0`
- `FLTMGR!FltReleaseContext` at `0x140062db6`
- `FLTMGR!FltReleaseContext` at `0x140062c29`
- `FLTMGR!FltReleaseContext` at `0x140062cb0`
- `FLTMGR!FltReleaseContext` at `0x140062db6`

## string_xrefs

- `0x140062b18`: `PUSH: Getting relative path`
- `0x140062994`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062a3b`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062b29`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062c91`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062a2a`: `PUSH: Opening directory file`
- `0x140062a16`: `Directory should exist in scratch`
- `0x140062d98`: `PUSH: Checking if directory is Empty`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory(
        UnionFs::UfsUnionCtx *this,
        const struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_FILE_NAME_INFORMATION *a3,
        const struct _EJOB *a4,
        bool a5,
        bool *a6,
        struct UnionFs::StackEventTracer *a7)
{
  unsigned __int64 *v10; // rdx
  __int64 *v11; // rax
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rdi
  struct _FLT_INSTANCE *v14; // r13
  int RemainingPath; // ebx
  PFLT_CONTEXT v16; // rcx
  PFLT_CONTEXT v18; // rdi
  int v19; // eax
  PVOID v20; // rcx
  unsigned __int64 *v21; // rdx
  __int64 *v22; // rax
  volatile signed __int32 *v23; // rbx
  __int64 v24; // r14
  __int128 *v25; // r14
  struct _UNICODE_STRING *v26; // rdx
  struct _FILE_OBJECT *v27; // r12
  unsigned __int64 *v28; // rdx
  _QWORD *v29; // rax
  volatile signed __int32 *v30; // r15
  PFLT_CONTEXT v31; // rbx
  int IsDirectoryEmpty; // r14d
  const char *v33; // rax
  __int64 v34; // r8
  const char *v35; // rax
  __int64 v36; // r8
  struct _UNICODE_STRING *v37; // rdx
  PVOID v38; // rcx
  unsigned __int64 *v39; // rdx
  _QWORD *v40; // rcx
  __int64 v41; // rax
  struct _UNICODE_STRING *v42; // rdx
  PVOID v43; // rcx
  char *v44; // [rsp+30h] [rbp-59h]
  char *p_Context; // [rsp+30h] [rbp-59h]
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-41h] BYREF
  __int128 v47; // [rsp+50h] [rbp-39h] BYREF
  FsFltWil::Details *v48; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-21h] BYREF
  PVOID Object[2]; // [rsp+78h] [rbp-11h] BYREF
  PVOID EcpContext; // [rsp+88h] [rbp-1h]

  v48 = (UnionFs::UfsUnionCtx *)((char *)this + 72);
  FsFltWil::AcquirePushLockShared(&Context, (char *)this + 72);
  v11 = (__int64 *)*((_QWORD *)this + 6);
  v12 = (volatile signed __int32 *)v11[1];
  v13 = *v11;
  if ( v12 )
    _InterlockedIncrement(v12 + 2);
  if ( Context )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context, v10);
  v14 = **(struct _FLT_INSTANCE ***)(v13 + 8);
  if ( v12 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v12);
  Context = 0;
  RemainingPath = UnionFs::UfsSiloCtx::Get(a4, v14, &Context, a7);
  if ( RemainingPath < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)RemainingPath,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0xF4002005BFLL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory",
      "PUSH: Getting silo context",
      v44);
    v16 = Context;
    if ( !Context )
      return (unsigned int)RemainingPath;
LABEL_9:
    PsDereferenceSiloContext(v16);
    return (unsigned int)RemainingPath;
  }
  v18 = Context;
  *(_OWORD *)Object = 0;
  EcpContext = 0;
  v19 = UnionFs::Utils::OpenAsReparsePoint(v14, &a3->Name, 0x80u, a5, Object, (__int64)a7, (__int64 *)Context, 0);
  RemainingPath = v19;
  if ( v19 == -1073741766 || v19 == -1073741772 )
    MicrosoftTelemetryAssertTriggeredMsgKM("Directory should exist in scratch");
  if ( RemainingPath < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)RemainingPath,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0xF2002005CELL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory",
      "PUSH: Opening directory file",
      p_Context);
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v20 = Object[1];
    Object[1] = 0;
LABEL_18:
    if ( v20 )
      ObfDereferenceObject(v20);
    if ( Object[0] )
      FltClose(Object[0]);
    if ( !v18 )
      return (unsigned int)RemainingPath;
    v16 = v18;
    goto LABEL_9;
  }
  FsFltWil::AcquirePushLockShared(&Context, (char *)this + 72);
  v22 = (__int64 *)*((_QWORD *)this + 6);
  v23 = (volatile signed __int32 *)v22[1];
  v24 = *v22;
  if ( v23 )
    _InterlockedIncrement(v23 + 2);
  if ( Context )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context, v21);
  v25 = *(__int128 **)(v24 + 16);
  if ( v23 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v23);
  UnicodeString = 0;
  v47 = *v25;
  RemainingPath = UnionFs::Utils::GetRemainingPath(a3, &v47, &UnicodeString, a7);
  if ( RemainingPath < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)RemainingPath,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0xF5002005DALL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory",
      "PUSH: Getting relative path",
      p_Context);
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v26);
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v20 = Object[1];
    Object[1] = 0;
    goto LABEL_18;
  }
  v27 = (struct _FILE_OBJECT *)Object[1];
  FsFltWil::AcquirePushLockShared(&Context, (char *)this + 72);
  v29 = (_QWORD *)*((_QWORD *)this + 6);
  v30 = (volatile signed __int32 *)v29[1];
  *(_QWORD *)&v47 = *v29;
  if ( v30 )
    _InterlockedIncrement(v30 + 2);
  if ( Context )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context, v28);
  UnionFs::UfsStreamHandleCtx::FltGet(&Context, v14);
  v31 = Context;
  if ( Context )
    goto LABEL_46;
  p_Context = (char *)&Context;
  IsDirectoryEmpty = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(v47, v27, v25, &UnicodeString, 0);
  if ( IsDirectoryEmpty < 0 )
  {
    v33 = "PUSH: Allocating streamhandle ctx";
    v34 = 0xF9000A0616LL;
    goto LABEL_41;
  }
  IsDirectoryEmpty = UnionFs::UfsStreamHandleCtx::FltSet(v14, v27);
  if ( IsDirectoryEmpty >= 0 )
  {
    v31 = Context;
LABEL_46:
    IsDirectoryEmpty = 0;
    goto LABEL_47;
  }
  v33 = "PUSH: Setting streamhandle context";
  v34 = 0xFC000A061CLL;
LABEL_41:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)IsDirectoryEmpty,
    (int)a7,
    (struct UnionFs::StackEventTracer *)v34,
    (unsigned __int64)"UnionFs::UfsStreamHandleCtx::FltGetSet",
    v33,
    (const char *)&Context);
  if ( Context )
    FltReleaseContext(Context);
LABEL_47:
  if ( v30 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
  if ( IsDirectoryEmpty < 0 )
  {
    v35 = "PUSH: Getting/setting internal handle context";
    v36 = 0xF6002005E8LL;
LABEL_51:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)IsDirectoryEmpty,
      (int)a7,
      (struct UnionFs::StackEventTracer *)v36,
      (unsigned __int64)"UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory",
      v35,
      p_Context);
    if ( v31 )
      FltReleaseContext(v31);
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v37);
    if ( EcpContext )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
    v38 = Object[1];
    Object[1] = 0;
    if ( v38 )
      ObfDereferenceObject(v38);
    if ( Object[0] )
      FltClose(Object[0]);
    if ( v18 )
      PsDereferenceSiloContext(v18);
    return (unsigned int)IsDirectoryEmpty;
  }
  FsFltWil::AcquirePushLockShared(&v48, v48);
  v40 = (_QWORD *)*((_QWORD *)this + 6);
  *(_QWORD *)&v47 = *v40;
  v41 = v40[1];
  *((_QWORD *)&v47 + 1) = v41;
  if ( v41 )
    _InterlockedIncrement((volatile signed __int32 *)(v41 + 8));
  if ( v48 )
    FsFltWil::Details::ReleasePushLockShared(v48, v39);
  UnionFs::UfsStreamHandleCtx::SetBackingLayer(v31, &v47);
  IsDirectoryEmpty = UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty((UnionFs::UfsStreamHandleCtx *)v31, a2, a6, a7, 1);
  if ( IsDirectoryEmpty < 0 )
  {
    v35 = "PUSH: Checking if directory is Empty";
    v36 = 0x102002005F1LL;
    goto LABEL_51;
  }
  if ( v31 )
    FltReleaseContext(v31);
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v42);
  if ( EcpContext )
    FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, EcpContext);
  v43 = Object[1];
  Object[1] = 0;
  if ( v43 )
    ObfDereferenceObject(v43);
  if ( Object[0] )
    FltClose(Object[0]);
  if ( v18 )
    PsDereferenceSiloContext(v18);
  return 0;
}

```

## disassembly

```asm
0x1400628e4  mov     rax, rsp
0x1400628e7  mov     [rax+18h], rbx
0x1400628eb  mov     [rax+10h], rdx
0x1400628ef  mov     [rax+8], rcx
0x1400628f3  push    rbp
0x1400628f4  push    rsi
0x1400628f5  push    rdi
0x1400628f6  push    r12
0x1400628f8  push    r13
0x1400628fa  push    r14
0x1400628fc  push    r15
0x1400628fe  lea     rbp, [rax-47h]
0x140062902  sub     rsp, 90h
0x140062909  lea     rax, [rcx+48h]
0x14006290d  mov     r15, rcx
0x140062910  mov     rdx, rax
0x140062913  mov     [rbp+3Fh+var_68], rax
0x140062917  lea     rcx, [rbp+3Fh+Context]
0x14006291b  mov     r14, r9
0x14006291e  mov     r12, r8
0x140062921  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062926  mov     rax, [r15+30h]
0x14006292a  mov     rbx, [rax+8]
0x14006292e  mov     rdi, [rax]
0x140062931  test    rbx, rbx
0x140062934  jz      short loc_14006293A
0x140062936  lock inc dword ptr [rbx+8]
0x14006293a  mov     rcx, [rbp+3Fh+Context]; this
0x14006293e  test    rcx, rcx
0x140062941  jz      short loc_140062948
0x140062943  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062948  mov     rax, [rdi+8]
0x14006294c  mov     r13, [rax]
0x14006294f  test    rbx, rbx
0x140062952  jz      short loc_14006295C
0x140062954  mov     rcx, rbx; this
0x140062957  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14006295c  mov     rsi, [rbp+3Fh+arg_30]
0x140062960  lea     r8, [rbp+3Fh+Context]
0x140062964  mov     r9, rsi
0x140062967  mov     [rbp+3Fh+Context], 0
0x14006296f  mov     rdx, r13
0x140062972  mov     rcx, r14
0x140062975  call    ?Get@UfsSiloCtx@UnionFs@@SAJAEBU_EJOB@@AEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsSiloCtx::Get(_EJOB const &,_FLT_INSTANCE const &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> &,UnionFs::StackEventTracer &)
0x14006297a  xor     r14d, r14d
0x14006297d  mov     ebx, eax
0x14006297f  test    eax, eax
0x140062981  jns     short loc_1400629C6
0x140062983  lea     rax, aPushGettingSil; "PUSH: Getting silo context"
0x14006298a  mov     r8, 0F4002005BFh; struct UnionFs::StackEventTracer *
0x140062994  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x14006299b  mov     [rsp+0C0h+var_A0], rax; char *
0x1400629a0  mov     rdx, rsi; int
0x1400629a3  mov     ecx, ebx; this
0x1400629a5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400629aa  mov     rcx, [rbp+3Fh+Context]
0x1400629ae  test    rcx, rcx
0x1400629b1  jz      short loc_1400629BF
0x1400629b3  call    cs:__imp_PsDereferenceSiloContext
0x1400629ba  nop     dword ptr [rax+rax+00h]
0x1400629bf  mov     eax, ebx
0x1400629c1  jmp     loc_140062E32
0x1400629c6  mov     rdi, [rbp+3Fh+Context]
0x1400629ca  lea     rax, [rbp+3Fh+Object]
0x1400629ce  movzx   r9d, [rbp+3Fh+arg_20]
0x1400629d3  lea     rdx, [r12+8]
0x1400629d8  mov     [rsp+38h], r14
0x1400629dd  xorps   xmm0, xmm0
0x1400629e0  mov     [rsp+0C0h+var_90], rdi
0x1400629e5  mov     r8d, 80h
0x1400629eb  mov     [rsp+0C0h+var_98], rsi; char *
0x1400629f0  mov     rcx, r13
0x1400629f3  mov     [rsp+0C0h+var_A0], rax
0x1400629f8  movdqu  xmmword ptr [rbp+3Fh+Object], xmm0
0x1400629fd  mov     [rbp+3Fh+EcpContext], r14
0x140062a01  call    ?OpenAsReparsePoint@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KW4OpenAsReparsePointFlags@12@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@PEAX@Z; UnionFs::Utils::OpenAsReparsePoint(_FLT_INSTANCE const &,_UNICODE_STRING const &,ulong,UnionFs::Utils::OpenAsReparsePointFlags,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *,void *)
0x140062a06  mov     ebx, eax
0x140062a08  cmp     eax, 0C000003Ah
0x140062a0d  jz      short loc_140062A16
0x140062a0f  cmp     eax, 0C0000034h
0x140062a14  jnz     short loc_140062A22
0x140062a16  lea     rcx, aDirectoryShoul; "Directory should exist in scratch"
0x140062a1d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140062a22  test    ebx, ebx
0x140062a24  jns     loc_140062AAF
0x140062a2a  lea     rax, aPushOpeningDir; "PUSH: Opening directory file"
0x140062a31  mov     r8, 0F2002005CEh; struct UnionFs::StackEventTracer *
0x140062a3b  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x140062a42  mov     [rsp+0C0h+var_A0], rax; char *
0x140062a47  mov     rdx, rsi; int
0x140062a4a  mov     ecx, ebx; this
0x140062a4c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062a51  mov     rdx, [rbp+3Fh+EcpContext]; EcpContext
0x140062a55  test    rdx, rdx
0x140062a58  jz      short loc_140062A70
0x140062a5a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140062a61  mov     rcx, [rcx]; Filter
0x140062a64  call    cs:__imp_FltFreeExtraCreateParameter
0x140062a6b  nop     dword ptr [rax+rax+00h]
0x140062a70  mov     rcx, [rbp+3Fh+Object+8]; Object
0x140062a74  mov     [rbp+3Fh+Object+8], r14
0x140062a78  test    rcx, rcx
0x140062a7b  jz      short loc_140062A89
0x140062a7d  call    cs:__imp_ObfDereferenceObject
0x140062a84  nop     dword ptr [rax+rax+00h]
0x140062a89  mov     rcx, [rbp+3Fh+Object]; FileHandle
0x140062a8d  test    rcx, rcx
0x140062a90  jz      short loc_140062A9E
0x140062a92  call    cs:__imp_FltClose
0x140062a99  nop     dword ptr [rax+rax+00h]
0x140062a9e  test    rdi, rdi
0x140062aa1  jz      loc_1400629BF
0x140062aa7  mov     rcx, rdi
0x140062aaa  jmp     loc_1400629B3
0x140062aaf  lea     rdx, [r15+48h]
0x140062ab3  lea     rcx, [rbp+3Fh+Context]
0x140062ab7  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062abc  mov     rax, [r15+30h]
0x140062ac0  mov     rbx, [rax+8]
0x140062ac4  mov     r14, [rax]
0x140062ac7  test    rbx, rbx
0x140062aca  jz      short loc_140062AD0
0x140062acc  lock inc dword ptr [rbx+8]
0x140062ad0  mov     rcx, [rbp+3Fh+Context]; this
0x140062ad4  test    rcx, rcx
0x140062ad7  jz      short loc_140062ADE
0x140062ad9  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062ade  mov     r14, [r14+10h]
0x140062ae2  test    rbx, rbx
0x140062ae5  jz      short loc_140062AEF
0x140062ae7  mov     rcx, rbx; this
0x140062aea  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062aef  xorps   xmm0, xmm0
0x140062af2  lea     r8, [rbp+3Fh+UnicodeString]
0x140062af6  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm0
0x140062afa  mov     r9, rsi
0x140062afd  lea     rdx, [rbp+3Fh+var_78]
0x140062b01  movups  xmm1, xmmword ptr [r14]
0x140062b05  mov     rcx, r12
0x140062b08  movdqu  [rbp+3Fh+var_78], xmm1
0x140062b0d  call    ?GetRemainingPath@Utils@UnionFs@@YAJAEBU_FLT_FILE_NAME_INFORMATION@@AEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetRemainingPath(_FLT_FILE_NAME_INFORMATION const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140062b12  mov     ebx, eax
0x140062b14  test    eax, eax
0x140062b16  jns     short loc_140062B78
0x140062b18  lea     rax, aPushGettingRel; "PUSH: Getting relative path"
0x140062b1f  mov     r8, 0F5002005DAh; struct UnionFs::StackEventTracer *
0x140062b29  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x140062b30  mov     [rsp+0C0h+var_A0], rax; char *
0x140062b35  mov     rdx, rsi; int
0x140062b38  mov     ecx, ebx; this
0x140062b3a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062b3f  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x140062b43  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140062b48  mov     rdx, [rbp+3Fh+EcpContext]; EcpContext
0x140062b4c  test    rdx, rdx
0x140062b4f  jz      short loc_140062B67
0x140062b51  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140062b58  mov     rcx, [rcx]; Filter
0x140062b5b  call    cs:__imp_FltFreeExtraCreateParameter
0x140062b62  nop     dword ptr [rax+rax+00h]
0x140062b67  mov     rcx, [rbp+3Fh+Object+8]
0x140062b6b  mov     [rbp+3Fh+Object+8], 0
0x140062b73  jmp     loc_140062A78
0x140062b78  mov     r12, [rbp+3Fh+Object+8]
0x140062b7c  lea     rdx, [r15+48h]
0x140062b80  lea     rcx, [rbp+3Fh+Context]
0x140062b84  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062b89  mov     rax, [r15+30h]
0x140062b8d  mov     r15, [rax+8]
0x140062b91  mov     rcx, [rax]
0x140062b94  mov     qword ptr [rbp+3Fh+var_78], rcx
0x140062b98  test    r15, r15
0x140062b9b  jz      short loc_140062BA2
0x140062b9d  lock inc dword ptr [r15+8]
0x140062ba2  mov     rcx, [rbp+3Fh+Context]; this
0x140062ba6  test    rcx, rcx
0x140062ba9  jz      short loc_140062BB0
0x140062bab  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062bb0  mov     r8, r12
0x140062bb3  lea     rcx, [rbp+3Fh+Context]
0x140062bb7  mov     rdx, r13
0x140062bba  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SA?AV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &)
0x140062bbf  mov     rbx, [rbp+3Fh+Context]
0x140062bc3  test    rbx, rbx
0x140062bc6  jnz     loc_140062C67
0x140062bcc  mov     rcx, qword ptr [rbp+3Fh+var_78]
0x140062bd0  lea     rax, [rbp+3Fh+Context]
0x140062bd4  mov     [rsp+0C0h+var_90], rsi
0x140062bd9  lea     r9, [rbp+3Fh+UnicodeString]
0x140062bdd  mov     [rsp+0C0h+var_98], rax; char *
0x140062be2  mov     r8, r14
0x140062be5  mov     rdx, r12
0x140062be8  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x140062bec  call    ?FltAllocAndInit@UfsStreamHandleCtx@UnionFs@@SAJAEBVUfsLayerCtx@2@AEBU_FILE_OBJECT@@AEBVUfsPathName@2@AEBU_UNICODE_STRING@@W4HandleCtxFlags@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltAllocAndInit(UnionFs::UfsLayerCtx const &,_FILE_OBJECT const &,UnionFs::UfsPathName const &,_UNICODE_STRING const &,UnionFs::HandleCtxFlags,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140062bf1  mov     r14d, eax
0x140062bf4  test    eax, eax
0x140062bf6  jns     short loc_140062C37
0x140062bf8  lea     rax, aPushAllocating_24; "PUSH: Allocating streamhandle ctx"
0x140062bff  mov     r8, 0F9000A0616h; struct UnionFs::StackEventTracer *
0x140062c09  lea     r9, aUnionfsUfsstre_10; "UnionFs::UfsStreamHandleCtx::FltGetSet"
0x140062c10  mov     [rsp+0C0h+var_A0], rax; char *
0x140062c15  mov     rdx, rsi; int
0x140062c18  mov     ecx, r14d; this
0x140062c1b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062c20  mov     rcx, [rbp+3Fh+Context]; Context
0x140062c24  test    rcx, rcx
0x140062c27  jz      short loc_140062C6A
0x140062c29  call    cs:__imp_FltReleaseContext
0x140062c30  nop     dword ptr [rax+rax+00h]
0x140062c35  jmp     short loc_140062C6A
0x140062c37  mov     r9, rsi
0x140062c3a  lea     r8, [rbp+3Fh+Context]
0x140062c3e  mov     rdx, r12; FileObject
0x140062c41  mov     rcx, r13; Instance
0x140062c44  call    ?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140062c49  mov     r14d, eax
0x140062c4c  test    eax, eax
0x140062c4e  jns     short loc_140062C63
0x140062c50  lea     rax, aPushSettingStr_1; "PUSH: Setting streamhandle context"
0x140062c57  mov     r8, 0FC000A061Ch
0x140062c61  jmp     short loc_140062C09
0x140062c63  mov     rbx, [rbp+3Fh+Context]
0x140062c67  xor     r14d, r14d
0x140062c6a  test    r15, r15
0x140062c6d  jz      short loc_140062C77
0x140062c6f  mov     rcx, r15; this
0x140062c72  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062c77  test    r14d, r14d
0x140062c7a  jns     loc_140062D32
0x140062c80  lea     rax, aPushGettingSet; "PUSH: Getting/setting internal handle c"...
0x140062c87  mov     r8, 0F6002005E8h; struct UnionFs::StackEventTracer *
0x140062c91  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x140062c98  mov     [rsp+0C0h+var_A0], rax; char *
0x140062c9d  mov     rdx, rsi; int
0x140062ca0  mov     ecx, r14d; this
0x140062ca3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062ca8  test    rbx, rbx
0x140062cab  jz      short loc_140062CBC
0x140062cad  mov     rcx, rbx; Context
0x140062cb0  call    cs:__imp_FltReleaseContext
0x140062cb7  nop     dword ptr [rax+rax+00h]
0x140062cbc  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x140062cc0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140062cc5  mov     rdx, [rbp+3Fh+EcpContext]; EcpContext
0x140062cc9  test    rdx, rdx
0x140062ccc  jz      short loc_140062CE4
0x140062cce  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140062cd5  mov     rcx, [rcx]; Filter
0x140062cd8  call    cs:__imp_FltFreeExtraCreateParameter
0x140062cdf  nop     dword ptr [rax+rax+00h]
0x140062ce4  mov     rcx, [rbp+3Fh+Object+8]; Object
0x140062ce8  mov     [rbp+3Fh+Object+8], 0
0x140062cf0  test    rcx, rcx
0x140062cf3  jz      short loc_140062D01
0x140062cf5  call    cs:__imp_ObfDereferenceObject
0x140062cfc  nop     dword ptr [rax+rax+00h]
0x140062d01  mov     rcx, [rbp+3Fh+Object]; FileHandle
0x140062d05  test    rcx, rcx
0x140062d08  jz      short loc_140062D16
0x140062d0a  call    cs:__imp_FltClose
0x140062d11  nop     dword ptr [rax+rax+00h]
0x140062d16  test    rdi, rdi
0x140062d19  jz      short loc_140062D2A
0x140062d1b  mov     rcx, rdi
0x140062d1e  call    cs:__imp_PsDereferenceSiloContext
0x140062d25  nop     dword ptr [rax+rax+00h]
0x140062d2a  mov     eax, r14d
0x140062d2d  jmp     loc_140062E32
0x140062d32  mov     rdx, [rbp+3Fh+var_68]
0x140062d36  lea     rcx, [rbp+3Fh+var_68]
0x140062d3a  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062d3f  mov     rax, [rbp+3Fh+arg_0]
0x140062d43  mov     rcx, [rax+30h]
0x140062d47  mov     rax, [rcx]
0x140062d4a  mov     qword ptr [rbp+3Fh+var_78], rax
0x140062d4e  mov     rax, [rcx+8]
0x140062d52  mov     qword ptr [rbp+3Fh+var_78+8], rax
0x140062d56  test    rax, rax
0x140062d59  jz      short loc_140062D5F
0x140062d5b  lock inc dword ptr [rax+8]
0x140062d5f  mov     rcx, [rbp+3Fh+var_68]; this
0x140062d63  test    rcx, rcx
0x140062d66  jz      short loc_140062D6D
0x140062d68  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062d6d  lea     rdx, [rbp+3Fh+var_78]
0x140062d71  mov     rcx, rbx
0x140062d74  call    ?SetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEAAXV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@@Z; UnionFs::UfsStreamHandleCtx::SetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx>)
0x140062d79  mov     r8, [rbp+3Fh+arg_28]; bool *
0x140062d7d  mov     r9, rsi; struct UnionFs::StackEventTracer *
0x140062d80  mov     rdx, [rbp+3Fh+arg_8]; struct _FLT_CALLBACK_DATA *
0x140062d84  mov     rcx, rbx; this
0x140062d87  mov     byte ptr [rsp+0C0h+var_A0], 1; bool
0x140062d8c  call    ?IsDirectoryEmpty@UfsStreamHandleCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@PEA_NAEAVStackEventTracer@2@_N@Z; UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty(_FLT_CALLBACK_DATA const &,bool *,UnionFs::StackEventTracer &,bool)
0x140062d91  mov     r14d, eax
0x140062d94  test    eax, eax
0x140062d96  jns     short loc_140062DAE
0x140062d98  lea     rax, aPushCheckingIf; "PUSH: Checking if directory is Empty"
0x140062d9f  mov     r8, 102002005F1h
0x140062da9  jmp     loc_140062C91
0x140062dae  test    rbx, rbx
  ... truncated ...
```
