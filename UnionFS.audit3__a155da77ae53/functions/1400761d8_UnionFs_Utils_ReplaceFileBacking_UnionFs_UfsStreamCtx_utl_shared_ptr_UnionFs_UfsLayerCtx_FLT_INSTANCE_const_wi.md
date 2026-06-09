# UnionFs::Utils::ReplaceFileBacking(UnionFs::UfsStreamCtx &,utl::shared_ptr<UnionFs::UfsLayerCtx> &,_FLT_INSTANCE const &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> const &,_FLT_INSTANCE const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x1400761d8`
- end: `0x140076500`
- name: `?ReplaceFileBacking@Utils@UnionFs@@YAJAEAVUfsStreamCtx@2@AEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEBU_FLT_INSTANCE@@AEBV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@2AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV78@AEAVStackEventTracer@2@@Z`
- size: `808`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PFLT_INSTANCE Instance, int, int, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140067ea4`

## callees

- `0x140028058`
- `0x1400283cc`
- `0x14002a758`
- `0x140056bd0`
- `0x140056c7c`
- `0x1400761d8`
- `0x140079cc4`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400764e0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400764e0`
- `FLTMGR!FltDeleteFileContext` at `0x140076218`
- `FLTMGR!FltDeleteFileContext` at `0x140076218`
- `FLTMGR!FltDeleteStreamContext` at `0x14007637c`
- `FLTMGR!FltDeleteStreamContext` at `0x14007637c`
- `FLTMGR!FltReleaseContext` at `0x14007623f`
- `FLTMGR!FltReleaseContext` at `0x140076287`
- `FLTMGR!FltReleaseContext` at `0x14007632d`
- `FLTMGR!FltReleaseContext` at `0x140076349`
- `FLTMGR!FltReleaseContext` at `0x1400763a3`
- `FLTMGR!FltReleaseContext` at `0x1400763eb`
- `FLTMGR!FltReleaseContext` at `0x14007646b`
- `FLTMGR!FltReleaseContext` at `0x14007623f`
- `FLTMGR!FltReleaseContext` at `0x140076287`
- `FLTMGR!FltReleaseContext` at `0x14007632d`
- `FLTMGR!FltReleaseContext` at `0x140076349`
- `FLTMGR!FltReleaseContext` at `0x1400763a3`
- `FLTMGR!FltReleaseContext` at `0x1400763eb`
- `FLTMGR!FltReleaseContext` at `0x14007646b`

## string_xrefs

- `0x14007625d`: `UnionFs::UfsFileCtx::FltDelete`
- `0x1400763c4`: `UnionFs::UfsStreamCtx::FltDelete`
- `0x1400762a1`: `UnionFs::Utils::ReplaceFileBacking`
- `0x14007630e`: `UnionFs::Utils::ReplaceFileBacking`
- `0x140076408`: `UnionFs::Utils::ReplaceFileBacking`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::ReplaceFileBacking(
        __int64 a1,
        _QWORD *a2,
        struct _FLT_INSTANCE *a3,
        struct _FILE_OBJECT **a4,
        PFLT_INSTANCE Instance,
        int a6,
        PFILE_OBJECT *a7,
        struct _FILE_OBJECT *a8)
{
  struct _FILE_OBJECT *v10; // rdx
  unsigned int v13; // ebx
  void *v14; // rcx
  PFLT_CONTEXT v15; // rcx
  PFILE_OBJECT *v17; // r15
  struct _FILE_OBJECT *v18; // rbx
  NTSTATUS v19; // edi
  const char *v20; // rax
  __int64 v21; // r8
  struct _FILE_OBJECT *v22; // rdx
  void *v23; // rcx
  PFLT_CONTEXT v24; // rcx
  const char *v25; // rax
  __int64 v26; // r8
  volatile signed __int32 *v27; // rax
  struct _FAST_MUTEX *v28; // rcx
  char *v29; // [rsp+28h] [rbp-30h]
  char *v30; // [rsp+28h] [rbp-30h]
  char *v31; // [rsp+28h] [rbp-30h]
  int v32[2]; // [rsp+30h] [rbp-28h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+38h] [rbp-20h] BYREF
  char v34; // [rsp+40h] [rbp-18h]
  PFLT_CONTEXT Context; // [rsp+B8h] [rbp+60h] BYREF

  v34 = 1;
  v10 = *a4;
  *(_QWORD *)v32 = &Context;
  Context = 0;
  OldContext = 0;
  v13 = FltDeleteFileContext(a3, v10, &OldContext);
  if ( v34 )
  {
    v14 = **(void ***)v32;
    **(_QWORD **)v32 = OldContext;
    if ( v14 )
      FltReleaseContext(v14);
  }
  if ( (v13 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)v13,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x514000A02B1LL,
      (unsigned __int64)"UnionFs::UfsFileCtx::FltDelete",
      "API: Deleting file context",
      v29);
    v15 = Context;
    Context = 0;
    if ( v15 )
      FltReleaseContext(v15);
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v13,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x51600211A62LL,
      (unsigned __int64)"UnionFs::Utils::ReplaceFileBacking",
      "PUSH: Removing file context from layer BFO",
      v30);
    return v13;
  }
  v17 = a7;
  v18 = a8;
  v19 = UnionFs::UfsFileCtx::FltSet(Instance, *a7, 2, 0);
  if ( v19 < 0 )
  {
    v20 = "PUSH: Setting file context on scratch BFO";
    v21 = 0x51700211A6CLL;
    goto LABEL_10;
  }
  if ( Context )
    FltReleaseContext(Context);
  v22 = *a4;
  *(_QWORD *)v32 = &Context;
  Context = 0;
  OldContext = 0;
  v34 = 1;
  v19 = FltDeleteStreamContext(a3, v22, &OldContext);
  if ( v34 )
  {
    v23 = **(void ***)v32;
    **(_QWORD **)v32 = OldContext;
    if ( v23 )
      FltReleaseContext(v23);
  }
  if ( v19 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v19,
      (int)v18,
      (struct UnionFs::StackEventTracer *)0x515000A0469LL,
      (unsigned __int64)"UnionFs::UfsStreamCtx::FltDelete",
      "API: Deleting stream context",
      v31);
    v24 = Context;
    Context = 0;
    if ( v24 )
      FltReleaseContext(v24);
    v25 = "PUSH: Removing stream context from layer BFO";
    v26 = 0x51800211A75LL;
    goto LABEL_22;
  }
  v19 = UnionFs::UfsStreamCtx::FltSet(Instance, *v17, &Context, v18, 2);
  if ( v19 < 0 )
  {
    v20 = "PUSH: Setting stream context on scratch BFO";
    v21 = 0x51900211A82LL;
LABEL_10:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v19,
      (int)v18,
      (struct UnionFs::StackEventTracer *)v21,
      (unsigned __int64)"UnionFs::Utils::ReplaceFileBacking",
      v20,
      v31);
    if ( Context )
      FltReleaseContext(Context);
    return (unsigned int)v19;
  }
  if ( Context )
    FltReleaseContext(Context);
  *(_QWORD *)v32 = *a2;
  v27 = (volatile signed __int32 *)a2[1];
  OldContext = (PFLT_CONTEXT)v27;
  if ( v27 )
    _InterlockedIncrement(v27 + 2);
  v19 = UnionFs::UfsStreamCtx::ReplaceBackingForSFOs(a1, (int)v32, a6, (int)v17, v18);
  if ( v19 < 0 )
  {
    v25 = "PUSH: Replacing SFO backings";
    v26 = 0x4DA00211A8CLL;
LABEL_22:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v19,
      (int)v18,
      (struct UnionFs::StackEventTracer *)v26,
      (unsigned __int64)"UnionFs::Utils::ReplaceFileBacking",
      v25,
      v31);
    return (unsigned int)v19;
  }
  FsFltWil::AcquireFastMutex(&Context, a1 + 72);
  v28 = (struct _FAST_MUTEX *)Context;
  *(_BYTE *)(a1 + 160) = 1;
  if ( v28 )
    ExReleaseFastMutex(v28);
  return 0;
}

```

## disassembly

```asm
0x1400761d8  push    rbp
0x1400761da  push    rbx
0x1400761db  push    rsi
0x1400761dc  push    rdi
0x1400761dd  push    r12
0x1400761df  push    r13
0x1400761e1  push    r14
0x1400761e3  push    r15
0x1400761e5  mov     rbp, rsp
0x1400761e8  sub     rsp, 58h
0x1400761ec  mov     r13, r8
0x1400761ef  mov     [rbp+var_18], 1
0x1400761f3  mov     r14, rdx
0x1400761f6  lea     rax, [rbp+Context]
0x1400761fa  mov     rdx, [r9]; FileObject
0x1400761fd  lea     r8, [rbp+OldContext]; OldContext
0x140076201  mov     rsi, rcx
0x140076204  mov     qword ptr [rbp+var_28], rax
0x140076208  xor     edi, edi
0x14007620a  mov     rcx, r13; Instance
0x14007620d  mov     r12, r9
0x140076210  mov     [rbp+Context], rdi
0x140076214  mov     [rbp+OldContext], rdi
0x140076218  call    cs:__imp_FltDeleteFileContext
0x14007621f  nop     dword ptr [rax+rax+00h]
0x140076224  mov     ebx, eax
0x140076226  cmp     [rbp+var_18], dil
0x14007622a  jz      short loc_14007624B
0x14007622c  mov     r8, qword ptr [rbp+var_28]
0x140076230  mov     rdx, [rbp+OldContext]
0x140076234  mov     rcx, [r8]; Context
0x140076237  mov     [r8], rdx
0x14007623a  test    rcx, rcx
0x14007623d  jz      short loc_14007624B
0x14007623f  call    cs:__imp_FltReleaseContext
0x140076246  nop     dword ptr [rax+rax+00h]
0x14007624b  test    ebx, ebx
0x14007624d  jns     short loc_1400762C5
0x14007624f  mov     rdx, [rbp+arg_38]; int
0x140076256  lea     rax, aApiDeletingFil; "API: Deleting file context"
0x14007625d  lea     r9, aUnionfsUfsfile; "UnionFs::UfsFileCtx::FltDelete"
0x140076264  mov     [rsp+58h+var_38], rax; char *
0x140076269  mov     r8, 514000A02B1h; struct UnionFs::StackEventTracer *
0x140076273  mov     ecx, ebx; this
0x140076275  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007627a  mov     rcx, [rbp+Context]; Context
0x14007627e  mov     [rbp+Context], rdi
0x140076282  test    rcx, rcx
0x140076285  jz      short loc_140076293
0x140076287  call    cs:__imp_FltReleaseContext
0x14007628e  nop     dword ptr [rax+rax+00h]
0x140076293  mov     rdx, [rbp+arg_38]; int
0x14007629a  lea     rax, aPushRemovingFi; "PUSH: Removing file context from layer "...
0x1400762a1  lea     r9, aUnionfsUtilsRe_4; "UnionFs::Utils::ReplaceFileBacking"
0x1400762a8  mov     [rsp+58h+var_38], rax; char *
0x1400762ad  mov     r8, 51600211A62h; struct UnionFs::StackEventTracer *
0x1400762b7  mov     ecx, ebx; this
0x1400762b9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400762be  mov     eax, ebx
0x1400762c0  jmp     loc_1400764EE
0x1400762c5  mov     rax, [rbp+Context]
0x1400762c9  lea     r8, [rbp+Context]
0x1400762cd  mov     r15, [rbp+arg_30]
0x1400762d1  mov     rbx, [rbp+arg_38]
0x1400762d8  mov     rcx, [rbp+Instance]; Instance
0x1400762dc  mov     r9, rbx
0x1400762df  mov     dword ptr [rsp+58h+var_30], edi; char *
0x1400762e3  mov     rdx, [r15]; FileObject
0x1400762e6  mov     [rbp+Context], rax
0x1400762ea  mov     dword ptr [rsp+58h+var_38], 2; int
0x1400762f2  call    ?FltSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@W4SetContextOperation@2@K@Z; UnionFs::UfsFileCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,UnionFs::SetContextOperation,ulong)
0x1400762f7  mov     edi, eax
0x1400762f9  test    eax, eax
0x1400762fb  jns     short loc_140076340
0x1400762fd  lea     rax, aPushSettingFil; "PUSH: Setting file context on scratch B"...
0x140076304  mov     r8, 51700211A6Ch; struct UnionFs::StackEventTracer *
0x14007630e  lea     r9, aUnionfsUtilsRe_4; "UnionFs::Utils::ReplaceFileBacking"
0x140076315  mov     [rsp+58h+var_38], rax; char *
0x14007631a  mov     rdx, rbx; int
0x14007631d  mov     ecx, edi; this
0x14007631f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076324  mov     rcx, [rbp+Context]; Context
0x140076328  test    rcx, rcx
0x14007632b  jz      short loc_140076339
0x14007632d  call    cs:__imp_FltReleaseContext
0x140076334  nop     dword ptr [rax+rax+00h]
0x140076339  mov     eax, edi
0x14007633b  jmp     loc_1400764EE
0x140076340  mov     rcx, [rbp+Context]; Context
0x140076344  test    rcx, rcx
0x140076347  jz      short loc_140076355
0x140076349  call    cs:__imp_FltReleaseContext
0x140076350  nop     dword ptr [rax+rax+00h]
0x140076355  mov     rdx, [r12]; FileObject
0x140076359  lea     rax, [rbp+Context]
0x14007635d  lea     r8, [rbp+OldContext]; OldContext
0x140076361  mov     qword ptr [rbp+var_28], rax
0x140076365  mov     rcx, r13; Instance
0x140076368  mov     [rbp+Context], 0
0x140076370  mov     [rbp+OldContext], 0
0x140076378  mov     [rbp+var_18], 1
0x14007637c  call    cs:__imp_FltDeleteStreamContext
0x140076383  nop     dword ptr [rax+rax+00h]
0x140076388  cmp     [rbp+var_18], 0
0x14007638c  mov     edi, eax
0x14007638e  jz      short loc_1400763AF
0x140076390  mov     r8, qword ptr [rbp+var_28]
0x140076394  mov     rdx, [rbp+OldContext]
0x140076398  mov     rcx, [r8]; Context
0x14007639b  mov     [r8], rdx
0x14007639e  test    rcx, rcx
0x1400763a1  jz      short loc_1400763AF
0x1400763a3  call    cs:__imp_FltReleaseContext
0x1400763aa  nop     dword ptr [rax+rax+00h]
0x1400763af  test    edi, edi
0x1400763b1  jns     short loc_140076423
0x1400763b3  lea     rax, aApiDeletingStr; "API: Deleting stream context"
0x1400763ba  mov     r8, 515000A0469h; struct UnionFs::StackEventTracer *
0x1400763c4  lea     r9, aUnionfsUfsstre_7; "UnionFs::UfsStreamCtx::FltDelete"
0x1400763cb  mov     [rsp+58h+var_38], rax; char *
0x1400763d0  mov     rdx, rbx; int
0x1400763d3  mov     ecx, edi; this
0x1400763d5  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400763da  mov     rcx, [rbp+Context]; Context
0x1400763de  mov     [rbp+Context], 0
0x1400763e6  test    rcx, rcx
0x1400763e9  jz      short loc_1400763F7
0x1400763eb  call    cs:__imp_FltReleaseContext
0x1400763f2  nop     dword ptr [rax+rax+00h]
0x1400763f7  lea     rax, aPushRemovingSt; "PUSH: Removing stream context from laye"...
0x1400763fe  mov     r8, 51800211A75h; struct UnionFs::StackEventTracer *
0x140076408  lea     r9, aUnionfsUtilsRe_4; "UnionFs::Utils::ReplaceFileBacking"
0x14007640f  mov     [rsp+58h+var_38], rax; char *
0x140076414  mov     rdx, rbx; int
0x140076417  mov     ecx, edi; this
0x140076419  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007641e  jmp     loc_140076339
0x140076423  mov     rax, [rbp+Context]
0x140076427  lea     r8, [rbp+Context]
0x14007642b  mov     rdx, [r15]
0x14007642e  mov     r9, rbx
0x140076431  mov     rcx, [rbp+Instance]
0x140076435  mov     [rbp+Context], rax
0x140076439  mov     dword ptr [rsp+58h+var_38], 2
0x140076441  call    ?FltSet@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@W4SetContextOperation@2@@Z; UnionFs::UfsStreamCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,UnionFs::SetContextOperation)
0x140076446  mov     edi, eax
0x140076448  test    eax, eax
0x14007644a  jns     short loc_140076462
0x14007644c  lea     rax, aPushSettingStr; "PUSH: Setting stream context on scratch"...
0x140076453  mov     r8, 51900211A82h
0x14007645d  jmp     loc_14007630E
0x140076462  mov     rcx, [rbp+Context]; Context
0x140076466  test    rcx, rcx
0x140076469  jz      short loc_140076477
0x14007646b  call    cs:__imp_FltReleaseContext
0x140076472  nop     dword ptr [rax+rax+00h]
0x140076477  mov     rax, [r14]
0x14007647a  mov     qword ptr [rbp+var_28], rax
0x14007647e  mov     rax, [r14+8]
0x140076482  mov     [rbp+OldContext], rax
0x140076486  test    rax, rax
0x140076489  jz      short loc_14007648F
0x14007648b  lock inc dword ptr [rax+8]
0x14007648f  mov     r8, qword ptr [rbp+arg_28]; int
0x140076493  lea     rdx, [rbp+var_28]; int
0x140076497  mov     r9, r15; int
0x14007649a  mov     [rsp+58h+var_38], rbx; struct _FILE_OBJECT *
0x14007649f  mov     rcx, rsi; int
0x1400764a2  call    ?ReplaceBackingForSFOs@UfsStreamCtx@UnionFs@@QEAAJV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamCtx::ReplaceBackingForSFOs(utl::shared_ptr<UnionFs::UfsLayerCtx>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &,UnionFs::StackEventTracer &)
0x1400764a7  mov     edi, eax
0x1400764a9  test    eax, eax
0x1400764ab  jns     short loc_1400764C3
0x1400764ad  lea     rax, aPushReplacingS_1; "PUSH: Replacing SFO backings"
0x1400764b4  mov     r8, 4DA00211A8Ch
0x1400764be  jmp     loc_140076408
0x1400764c3  lea     rdx, [rsi+48h]
0x1400764c7  lea     rcx, [rbp+Context]
0x1400764cb  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x1400764d0  mov     rcx, [rbp+Context]; FastMutex
0x1400764d4  mov     byte ptr [rsi+0A0h], 1
0x1400764db  test    rcx, rcx
0x1400764de  jz      short loc_1400764EC
0x1400764e0  call    cs:__imp_ExReleaseFastMutex
0x1400764e7  nop     dword ptr [rax+rax+00h]
0x1400764ec  xor     eax, eax
0x1400764ee  add     rsp, 58h
0x1400764f2  pop     r15
0x1400764f4  pop     r14
0x1400764f6  pop     r13
0x1400764f8  pop     r12
0x1400764fa  pop     rdi
0x1400764fb  pop     rsi
0x1400764fc  pop     rbx
0x1400764fd  pop     rbp
0x1400764fe  retn
```
