# UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory(_FLT_CALLBACK_DATA const &,_FLT_FILE_NAME_INFORMATION const &,_EJOB const &,bool,bool *,UnionFs::StackEventTracer &)

- ea: `0x140062a64`
- end: `0x140062fce`
- name: `?OpenAndCheckForEmptyDirectory@UfsUnionCtx@UnionFs@@QEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_FILE_NAME_INFORMATION@@AEBU_EJOB@@_NPEA_NAEAVStackEventTracer@2@@Z`
- size: `1386`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_FILE_NAME_INFORMATION *, const struct _EJOB *, bool, bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14002e468`

## callees

- `0x14000f81c`
- `0x140027218`
- `0x1400279dc`
- `0x1400284f0`
- `0x140029600`
- `0x14002abb8`
- `0x140056c7c`
- `0x14005a5b8`
- `0x140062a64`
- `0x14006faa8`
- `0x140072df8`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!PsDereferenceSiloContext` at `0x140062b33`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062e9e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062fa4`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062b33`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062e9e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140062fa4`
- `ntoskrnl!ObfDereferenceObject` at `0x140062bfd`
- `ntoskrnl!ObfDereferenceObject` at `0x140062e75`
- `ntoskrnl!ObfDereferenceObject` at `0x140062f7b`
- `ntoskrnl!ObfDereferenceObject` at `0x140062bfd`
- `ntoskrnl!ObfDereferenceObject` at `0x140062e75`
- `ntoskrnl!ObfDereferenceObject` at `0x140062f7b`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062be4`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062cdb`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062e58`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062f5e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062be4`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062cdb`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062e58`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140062f5e`
- `FLTMGR!FltClose` at `0x140062c12`
- `FLTMGR!FltClose` at `0x140062e8a`
- `FLTMGR!FltClose` at `0x140062f90`
- `FLTMGR!FltClose` at `0x140062c12`
- `FLTMGR!FltClose` at `0x140062e8a`
- `FLTMGR!FltClose` at `0x140062f90`
- `FLTMGR!FltReleaseContext` at `0x140062da9`
- `FLTMGR!FltReleaseContext` at `0x140062e30`
- `FLTMGR!FltReleaseContext` at `0x140062f36`
- `FLTMGR!FltReleaseContext` at `0x140062da9`
- `FLTMGR!FltReleaseContext` at `0x140062e30`
- `FLTMGR!FltReleaseContext` at `0x140062f36`

## string_xrefs

- `0x140062c98`: `PUSH: Getting relative path`
- `0x140062b96`: `Directory should exist in scratch`
- `0x140062b14`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062bbb`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062ca9`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062e11`: `UnionFs::UfsUnionCtx::OpenAndCheckForEmptyDirectory`
- `0x140062baa`: `PUSH: Opening directory file`
- `0x140062f18`: `PUSH: Checking if directory is Empty`

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
0x140062a64  mov     rax, rsp
0x140062a67  mov     [rax+18h], rbx
0x140062a6b  mov     [rax+10h], rdx
0x140062a6f  mov     [rax+8], rcx
0x140062a73  push    rbp
0x140062a74  push    rsi
0x140062a75  push    rdi
0x140062a76  push    r12
0x140062a78  push    r13
0x140062a7a  push    r14
0x140062a7c  push    r15
0x140062a7e  lea     rbp, [rax-47h]
0x140062a82  sub     rsp, 90h
0x140062a89  lea     rax, [rcx+48h]
0x140062a8d  mov     r15, rcx
0x140062a90  mov     rdx, rax
0x140062a93  mov     [rbp+3Fh+var_68], rax
0x140062a97  lea     rcx, [rbp+3Fh+Context]
0x140062a9b  mov     r14, r9
0x140062a9e  mov     r12, r8
0x140062aa1  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062aa6  mov     rax, [r15+30h]
0x140062aaa  mov     rbx, [rax+8]
0x140062aae  mov     rdi, [rax]
0x140062ab1  test    rbx, rbx
0x140062ab4  jz      short loc_140062ABA
0x140062ab6  lock inc dword ptr [rbx+8]
0x140062aba  mov     rcx, [rbp+3Fh+Context]; this
0x140062abe  test    rcx, rcx
0x140062ac1  jz      short loc_140062AC8
0x140062ac3  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062ac8  mov     rax, [rdi+8]
0x140062acc  mov     r13, [rax]
0x140062acf  test    rbx, rbx
0x140062ad2  jz      short loc_140062ADC
0x140062ad4  mov     rcx, rbx; this
0x140062ad7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062adc  mov     rsi, [rbp+3Fh+arg_30]
0x140062ae0  lea     r8, [rbp+3Fh+Context]
0x140062ae4  mov     r9, rsi
0x140062ae7  mov     [rbp+3Fh+Context], 0
0x140062aef  mov     rdx, r13
0x140062af2  mov     rcx, r14
0x140062af5  call    ?Get@UfsSiloCtx@UnionFs@@SAJAEBU_EJOB@@AEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsSiloCtx::Get(_EJOB const &,_FLT_INSTANCE const &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> &,UnionFs::StackEventTracer &)
0x140062afa  xor     r14d, r14d
0x140062afd  mov     ebx, eax
0x140062aff  test    eax, eax
0x140062b01  jns     short loc_140062B46
0x140062b03  lea     rax, aPushGettingSil; "PUSH: Getting silo context"
0x140062b0a  mov     r8, 0F4002005BFh; struct UnionFs::StackEventTracer *
0x140062b14  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x140062b1b  mov     [rsp+0C0h+var_A0], rax; char *
0x140062b20  mov     rdx, rsi; int
0x140062b23  mov     ecx, ebx; this
0x140062b25  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062b2a  mov     rcx, [rbp+3Fh+Context]
0x140062b2e  test    rcx, rcx
0x140062b31  jz      short loc_140062B3F
0x140062b33  call    cs:__imp_PsDereferenceSiloContext
0x140062b3a  nop     dword ptr [rax+rax+00h]
0x140062b3f  mov     eax, ebx
0x140062b41  jmp     loc_140062FB2
0x140062b46  mov     rdi, [rbp+3Fh+Context]
0x140062b4a  lea     rax, [rbp+3Fh+Object]
0x140062b4e  movzx   r9d, [rbp+3Fh+arg_20]
0x140062b53  lea     rdx, [r12+8]
0x140062b58  mov     [rsp+38h], r14
0x140062b5d  xorps   xmm0, xmm0
0x140062b60  mov     [rsp+0C0h+var_90], rdi
0x140062b65  mov     r8d, 80h
0x140062b6b  mov     [rsp+0C0h+var_98], rsi; char *
0x140062b70  mov     rcx, r13
0x140062b73  mov     [rsp+0C0h+var_A0], rax
0x140062b78  movdqu  xmmword ptr [rbp+3Fh+Object], xmm0
0x140062b7d  mov     [rbp+3Fh+EcpContext], r14
0x140062b81  call    ?OpenAsReparsePoint@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KW4OpenAsReparsePointFlags@12@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@PEAX@Z; UnionFs::Utils::OpenAsReparsePoint(_FLT_INSTANCE const &,_UNICODE_STRING const &,ulong,UnionFs::Utils::OpenAsReparsePointFlags,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *,void *)
0x140062b86  mov     ebx, eax
0x140062b88  cmp     eax, 0C000003Ah
0x140062b8d  jz      short loc_140062B96
0x140062b8f  cmp     eax, 0C0000034h
0x140062b94  jnz     short loc_140062BA2
0x140062b96  lea     rcx, aDirectoryShoul; "Directory should exist in scratch"
0x140062b9d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140062ba2  test    ebx, ebx
0x140062ba4  jns     loc_140062C2F
0x140062baa  lea     rax, aPushOpeningDir; "PUSH: Opening directory file"
0x140062bb1  mov     r8, 0F2002005CEh; struct UnionFs::StackEventTracer *
0x140062bbb  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x140062bc2  mov     [rsp+0C0h+var_A0], rax; char *
0x140062bc7  mov     rdx, rsi; int
0x140062bca  mov     ecx, ebx; this
0x140062bcc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062bd1  mov     rdx, [rbp+3Fh+EcpContext]; EcpContext
0x140062bd5  test    rdx, rdx
0x140062bd8  jz      short loc_140062BF0
0x140062bda  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140062be1  mov     rcx, [rcx]; Filter
0x140062be4  call    cs:__imp_FltFreeExtraCreateParameter
0x140062beb  nop     dword ptr [rax+rax+00h]
0x140062bf0  mov     rcx, [rbp+3Fh+Object+8]; Object
0x140062bf4  mov     [rbp+3Fh+Object+8], r14
0x140062bf8  test    rcx, rcx
0x140062bfb  jz      short loc_140062C09
0x140062bfd  call    cs:__imp_ObfDereferenceObject
0x140062c04  nop     dword ptr [rax+rax+00h]
0x140062c09  mov     rcx, [rbp+3Fh+Object]; FileHandle
0x140062c0d  test    rcx, rcx
0x140062c10  jz      short loc_140062C1E
0x140062c12  call    cs:__imp_FltClose
0x140062c19  nop     dword ptr [rax+rax+00h]
0x140062c1e  test    rdi, rdi
0x140062c21  jz      loc_140062B3F
0x140062c27  mov     rcx, rdi
0x140062c2a  jmp     loc_140062B33
0x140062c2f  lea     rdx, [r15+48h]
0x140062c33  lea     rcx, [rbp+3Fh+Context]
0x140062c37  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062c3c  mov     rax, [r15+30h]
0x140062c40  mov     rbx, [rax+8]
0x140062c44  mov     r14, [rax]
0x140062c47  test    rbx, rbx
0x140062c4a  jz      short loc_140062C50
0x140062c4c  lock inc dword ptr [rbx+8]
0x140062c50  mov     rcx, [rbp+3Fh+Context]; this
0x140062c54  test    rcx, rcx
0x140062c57  jz      short loc_140062C5E
0x140062c59  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062c5e  mov     r14, [r14+10h]
0x140062c62  test    rbx, rbx
0x140062c65  jz      short loc_140062C6F
0x140062c67  mov     rcx, rbx; this
0x140062c6a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062c6f  xorps   xmm0, xmm0
0x140062c72  lea     r8, [rbp+3Fh+UnicodeString]
0x140062c76  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm0
0x140062c7a  mov     r9, rsi
0x140062c7d  lea     rdx, [rbp+3Fh+var_78]
0x140062c81  movups  xmm1, xmmword ptr [r14]
0x140062c85  mov     rcx, r12
0x140062c88  movdqu  [rbp+3Fh+var_78], xmm1
0x140062c8d  call    ?GetRemainingPath@Utils@UnionFs@@YAJAEBU_FLT_FILE_NAME_INFORMATION@@AEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetRemainingPath(_FLT_FILE_NAME_INFORMATION const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140062c92  mov     ebx, eax
0x140062c94  test    eax, eax
0x140062c96  jns     short loc_140062CF8
0x140062c98  lea     rax, aPushGettingRel; "PUSH: Getting relative path"
0x140062c9f  mov     r8, 0F5002005DAh; struct UnionFs::StackEventTracer *
0x140062ca9  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x140062cb0  mov     [rsp+0C0h+var_A0], rax; char *
0x140062cb5  mov     rdx, rsi; int
0x140062cb8  mov     ecx, ebx; this
0x140062cba  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062cbf  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x140062cc3  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140062cc8  mov     rdx, [rbp+3Fh+EcpContext]; EcpContext
0x140062ccc  test    rdx, rdx
0x140062ccf  jz      short loc_140062CE7
0x140062cd1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140062cd8  mov     rcx, [rcx]; Filter
0x140062cdb  call    cs:__imp_FltFreeExtraCreateParameter
0x140062ce2  nop     dword ptr [rax+rax+00h]
0x140062ce7  mov     rcx, [rbp+3Fh+Object+8]
0x140062ceb  mov     [rbp+3Fh+Object+8], 0
0x140062cf3  jmp     loc_140062BF8
0x140062cf8  mov     r12, [rbp+3Fh+Object+8]
0x140062cfc  lea     rdx, [r15+48h]
0x140062d00  lea     rcx, [rbp+3Fh+Context]
0x140062d04  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062d09  mov     rax, [r15+30h]
0x140062d0d  mov     r15, [rax+8]
0x140062d11  mov     rcx, [rax]
0x140062d14  mov     qword ptr [rbp+3Fh+var_78], rcx
0x140062d18  test    r15, r15
0x140062d1b  jz      short loc_140062D22
0x140062d1d  lock inc dword ptr [r15+8]
0x140062d22  mov     rcx, [rbp+3Fh+Context]; this
0x140062d26  test    rcx, rcx
0x140062d29  jz      short loc_140062D30
0x140062d2b  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062d30  mov     r8, r12
0x140062d33  lea     rcx, [rbp+3Fh+Context]
0x140062d37  mov     rdx, r13
0x140062d3a  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SA?AV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &)
0x140062d3f  mov     rbx, [rbp+3Fh+Context]
0x140062d43  test    rbx, rbx
0x140062d46  jnz     loc_140062DE7
0x140062d4c  mov     rcx, qword ptr [rbp+3Fh+var_78]
0x140062d50  lea     rax, [rbp+3Fh+Context]
0x140062d54  mov     [rsp+0C0h+var_90], rsi
0x140062d59  lea     r9, [rbp+3Fh+UnicodeString]
0x140062d5d  mov     [rsp+0C0h+var_98], rax; char *
0x140062d62  mov     r8, r14
0x140062d65  mov     rdx, r12
0x140062d68  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x140062d6c  call    ?FltAllocAndInit@UfsStreamHandleCtx@UnionFs@@SAJAEBVUfsLayerCtx@2@AEBU_FILE_OBJECT@@AEBVUfsPathName@2@AEBU_UNICODE_STRING@@W4HandleCtxFlags@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltAllocAndInit(UnionFs::UfsLayerCtx const &,_FILE_OBJECT const &,UnionFs::UfsPathName const &,_UNICODE_STRING const &,UnionFs::HandleCtxFlags,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140062d71  mov     r14d, eax
0x140062d74  test    eax, eax
0x140062d76  jns     short loc_140062DB7
0x140062d78  lea     rax, aPushAllocating_24; "PUSH: Allocating streamhandle ctx"
0x140062d7f  mov     r8, 0F9000A0616h; struct UnionFs::StackEventTracer *
0x140062d89  lea     r9, aUnionfsUfsstre_10; "UnionFs::UfsStreamHandleCtx::FltGetSet"
0x140062d90  mov     [rsp+0C0h+var_A0], rax; char *
0x140062d95  mov     rdx, rsi; int
0x140062d98  mov     ecx, r14d; this
0x140062d9b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062da0  mov     rcx, [rbp+3Fh+Context]; Context
0x140062da4  test    rcx, rcx
0x140062da7  jz      short loc_140062DEA
0x140062da9  call    cs:__imp_FltReleaseContext
0x140062db0  nop     dword ptr [rax+rax+00h]
0x140062db5  jmp     short loc_140062DEA
0x140062db7  mov     r9, rsi
0x140062dba  lea     r8, [rbp+3Fh+Context]
0x140062dbe  mov     rdx, r12; FileObject
0x140062dc1  mov     rcx, r13; Instance
0x140062dc4  call    ?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140062dc9  mov     r14d, eax
0x140062dcc  test    eax, eax
0x140062dce  jns     short loc_140062DE3
0x140062dd0  lea     rax, aPushSettingStr_1; "PUSH: Setting streamhandle context"
0x140062dd7  mov     r8, 0FC000A061Ch
0x140062de1  jmp     short loc_140062D89
0x140062de3  mov     rbx, [rbp+3Fh+Context]
0x140062de7  xor     r14d, r14d
0x140062dea  test    r15, r15
0x140062ded  jz      short loc_140062DF7
0x140062def  mov     rcx, r15; this
0x140062df2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062df7  test    r14d, r14d
0x140062dfa  jns     loc_140062EB2
0x140062e00  lea     rax, aPushGettingSet; "PUSH: Getting/setting internal handle c"...
0x140062e07  mov     r8, 0F6002005E8h; struct UnionFs::StackEventTracer *
0x140062e11  lea     r9, aUnionfsUfsunio_28; "UnionFs::UfsUnionCtx::OpenAndCheckForEm"...
0x140062e18  mov     [rsp+0C0h+var_A0], rax; char *
0x140062e1d  mov     rdx, rsi; int
0x140062e20  mov     ecx, r14d; this
0x140062e23  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062e28  test    rbx, rbx
0x140062e2b  jz      short loc_140062E3C
0x140062e2d  mov     rcx, rbx; Context
0x140062e30  call    cs:__imp_FltReleaseContext
0x140062e37  nop     dword ptr [rax+rax+00h]
0x140062e3c  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x140062e40  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140062e45  mov     rdx, [rbp+3Fh+EcpContext]; EcpContext
0x140062e49  test    rdx, rdx
0x140062e4c  jz      short loc_140062E64
0x140062e4e  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140062e55  mov     rcx, [rcx]; Filter
0x140062e58  call    cs:__imp_FltFreeExtraCreateParameter
0x140062e5f  nop     dword ptr [rax+rax+00h]
0x140062e64  mov     rcx, [rbp+3Fh+Object+8]; Object
0x140062e68  mov     [rbp+3Fh+Object+8], 0
0x140062e70  test    rcx, rcx
0x140062e73  jz      short loc_140062E81
0x140062e75  call    cs:__imp_ObfDereferenceObject
0x140062e7c  nop     dword ptr [rax+rax+00h]
0x140062e81  mov     rcx, [rbp+3Fh+Object]; FileHandle
0x140062e85  test    rcx, rcx
0x140062e88  jz      short loc_140062E96
0x140062e8a  call    cs:__imp_FltClose
0x140062e91  nop     dword ptr [rax+rax+00h]
0x140062e96  test    rdi, rdi
0x140062e99  jz      short loc_140062EAA
0x140062e9b  mov     rcx, rdi
0x140062e9e  call    cs:__imp_PsDereferenceSiloContext
0x140062ea5  nop     dword ptr [rax+rax+00h]
0x140062eaa  mov     eax, r14d
0x140062ead  jmp     loc_140062FB2
0x140062eb2  mov     rdx, [rbp+3Fh+var_68]
0x140062eb6  lea     rcx, [rbp+3Fh+var_68]
0x140062eba  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062ebf  mov     rax, [rbp+3Fh+arg_0]
0x140062ec3  mov     rcx, [rax+30h]
0x140062ec7  mov     rax, [rcx]
0x140062eca  mov     qword ptr [rbp+3Fh+var_78], rax
0x140062ece  mov     rax, [rcx+8]
0x140062ed2  mov     qword ptr [rbp+3Fh+var_78+8], rax
0x140062ed6  test    rax, rax
0x140062ed9  jz      short loc_140062EDF
0x140062edb  lock inc dword ptr [rax+8]
0x140062edf  mov     rcx, [rbp+3Fh+var_68]; this
0x140062ee3  test    rcx, rcx
0x140062ee6  jz      short loc_140062EED
0x140062ee8  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062eed  lea     rdx, [rbp+3Fh+var_78]
0x140062ef1  mov     rcx, rbx
0x140062ef4  call    ?SetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEAAXV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@@Z; UnionFs::UfsStreamHandleCtx::SetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx>)
0x140062ef9  mov     r8, [rbp+3Fh+arg_28]; bool *
0x140062efd  mov     r9, rsi; struct UnionFs::StackEventTracer *
0x140062f00  mov     rdx, [rbp+3Fh+arg_8]; struct _FLT_CALLBACK_DATA *
0x140062f04  mov     rcx, rbx; this
0x140062f07  mov     byte ptr [rsp+0C0h+var_A0], 1; bool
0x140062f0c  call    ?IsDirectoryEmpty@UfsStreamHandleCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@PEA_NAEAVStackEventTracer@2@_N@Z; UnionFs::UfsStreamHandleCtx::IsDirectoryEmpty(_FLT_CALLBACK_DATA const &,bool *,UnionFs::StackEventTracer &,bool)
0x140062f11  mov     r14d, eax
0x140062f14  test    eax, eax
0x140062f16  jns     short loc_140062F2E
0x140062f18  lea     rax, aPushCheckingIf; "PUSH: Checking if directory is Empty"
0x140062f1f  mov     r8, 102002005F1h
0x140062f29  jmp     loc_140062E11
0x140062f2e  test    rbx, rbx
  ... truncated ...
```
