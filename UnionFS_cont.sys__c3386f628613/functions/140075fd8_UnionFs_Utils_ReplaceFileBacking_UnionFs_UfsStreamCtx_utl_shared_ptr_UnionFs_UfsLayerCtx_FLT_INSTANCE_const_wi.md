# UnionFs::Utils::ReplaceFileBacking(UnionFs::UfsStreamCtx &,utl::shared_ptr<UnionFs::UfsLayerCtx> &,_FLT_INSTANCE const &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> const &,_FLT_INSTANCE const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140075fd8`
- end: `0x140076300`
- name: `?ReplaceFileBacking@Utils@UnionFs@@YAJAEAVUfsStreamCtx@2@AEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEBU_FLT_INSTANCE@@AEBV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@2AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV78@AEAVStackEventTracer@2@@Z`
- size: `808`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PFLT_INSTANCE Instance, int, int, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140067cb4`

## callees

- `0x140027fb8`
- `0x14002832c`
- `0x14002a6b8`
- `0x140056a50`
- `0x140056afc`
- `0x140075fd8`
- `0x1400799a4`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400762e0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400762e0`
- `FLTMGR!FltDeleteFileContext` at `0x140076018`
- `FLTMGR!FltDeleteFileContext` at `0x140076018`
- `FLTMGR!FltDeleteStreamContext` at `0x14007617c`
- `FLTMGR!FltDeleteStreamContext` at `0x14007617c`
- `FLTMGR!FltReleaseContext` at `0x14007603f`
- `FLTMGR!FltReleaseContext` at `0x140076087`
- `FLTMGR!FltReleaseContext` at `0x14007612d`
- `FLTMGR!FltReleaseContext` at `0x140076149`
- `FLTMGR!FltReleaseContext` at `0x1400761a3`
- `FLTMGR!FltReleaseContext` at `0x1400761eb`
- `FLTMGR!FltReleaseContext` at `0x14007626b`
- `FLTMGR!FltReleaseContext` at `0x14007603f`
- `FLTMGR!FltReleaseContext` at `0x140076087`
- `FLTMGR!FltReleaseContext` at `0x14007612d`
- `FLTMGR!FltReleaseContext` at `0x140076149`
- `FLTMGR!FltReleaseContext` at `0x1400761a3`
- `FLTMGR!FltReleaseContext` at `0x1400761eb`
- `FLTMGR!FltReleaseContext` at `0x14007626b`

## string_xrefs

- `0x14007605d`: `UnionFs::UfsFileCtx::FltDelete`
- `0x1400761c4`: `UnionFs::UfsStreamCtx::FltDelete`
- `0x1400760a1`: `UnionFs::Utils::ReplaceFileBacking`
- `0x14007610e`: `UnionFs::Utils::ReplaceFileBacking`
- `0x140076208`: `UnionFs::Utils::ReplaceFileBacking`

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
      (struct UnionFs::StackEventTracer *)0x51600211A2CLL,
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
    v21 = 0x51700211A36LL;
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
    v26 = 0x51800211A3FLL;
    goto LABEL_22;
  }
  v19 = UnionFs::UfsStreamCtx::FltSet(Instance, *v17, &Context, v18, 2);
  if ( v19 < 0 )
  {
    v20 = "PUSH: Setting stream context on scratch BFO";
    v21 = 0x51900211A4CLL;
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
    v26 = 0x4DA00211A56LL;
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
0x140075fd8  push    rbp
0x140075fda  push    rbx
0x140075fdb  push    rsi
0x140075fdc  push    rdi
0x140075fdd  push    r12
0x140075fdf  push    r13
0x140075fe1  push    r14
0x140075fe3  push    r15
0x140075fe5  mov     rbp, rsp
0x140075fe8  sub     rsp, 58h
0x140075fec  mov     r13, r8
0x140075fef  mov     [rbp+var_18], 1
0x140075ff3  mov     r14, rdx
0x140075ff6  lea     rax, [rbp+Context]
0x140075ffa  mov     rdx, [r9]; FileObject
0x140075ffd  lea     r8, [rbp+OldContext]; OldContext
0x140076001  mov     rsi, rcx
0x140076004  mov     qword ptr [rbp+var_28], rax
0x140076008  xor     edi, edi
0x14007600a  mov     rcx, r13; Instance
0x14007600d  mov     r12, r9
0x140076010  mov     [rbp+Context], rdi
0x140076014  mov     [rbp+OldContext], rdi
0x140076018  call    cs:__imp_FltDeleteFileContext
0x14007601f  nop     dword ptr [rax+rax+00h]
0x140076024  mov     ebx, eax
0x140076026  cmp     [rbp+var_18], dil
0x14007602a  jz      short loc_14007604B
0x14007602c  mov     r8, qword ptr [rbp+var_28]
0x140076030  mov     rdx, [rbp+OldContext]
0x140076034  mov     rcx, [r8]; Context
0x140076037  mov     [r8], rdx
0x14007603a  test    rcx, rcx
0x14007603d  jz      short loc_14007604B
0x14007603f  call    cs:__imp_FltReleaseContext
0x140076046  nop     dword ptr [rax+rax+00h]
0x14007604b  test    ebx, ebx
0x14007604d  jns     short loc_1400760C5
0x14007604f  mov     rdx, [rbp+arg_38]; int
0x140076056  lea     rax, aApiDeletingFil; "API: Deleting file context"
0x14007605d  lea     r9, aUnionfsUfsfile; "UnionFs::UfsFileCtx::FltDelete"
0x140076064  mov     [rsp+58h+var_38], rax; char *
0x140076069  mov     r8, 514000A02B1h; struct UnionFs::StackEventTracer *
0x140076073  mov     ecx, ebx; this
0x140076075  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007607a  mov     rcx, [rbp+Context]; Context
0x14007607e  mov     [rbp+Context], rdi
0x140076082  test    rcx, rcx
0x140076085  jz      short loc_140076093
0x140076087  call    cs:__imp_FltReleaseContext
0x14007608e  nop     dword ptr [rax+rax+00h]
0x140076093  mov     rdx, [rbp+arg_38]; int
0x14007609a  lea     rax, aPushRemovingFi; "PUSH: Removing file context from layer "...
0x1400760a1  lea     r9, aUnionfsUtilsRe_4; "UnionFs::Utils::ReplaceFileBacking"
0x1400760a8  mov     [rsp+58h+var_38], rax; char *
0x1400760ad  mov     r8, 51600211A2Ch; struct UnionFs::StackEventTracer *
0x1400760b7  mov     ecx, ebx; this
0x1400760b9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400760be  mov     eax, ebx
0x1400760c0  jmp     loc_1400762EE
0x1400760c5  mov     rax, [rbp+Context]
0x1400760c9  lea     r8, [rbp+Context]
0x1400760cd  mov     r15, [rbp+arg_30]
0x1400760d1  mov     rbx, [rbp+arg_38]
0x1400760d8  mov     rcx, [rbp+Instance]; Instance
0x1400760dc  mov     r9, rbx
0x1400760df  mov     dword ptr [rsp+58h+var_30], edi; char *
0x1400760e3  mov     rdx, [r15]; FileObject
0x1400760e6  mov     [rbp+Context], rax
0x1400760ea  mov     dword ptr [rsp+58h+var_38], 2; int
0x1400760f2  call    ?FltSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@W4SetContextOperation@2@K@Z; UnionFs::UfsFileCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,UnionFs::SetContextOperation,ulong)
0x1400760f7  mov     edi, eax
0x1400760f9  test    eax, eax
0x1400760fb  jns     short loc_140076140
0x1400760fd  lea     rax, aPushSettingFil; "PUSH: Setting file context on scratch B"...
0x140076104  mov     r8, 51700211A36h; struct UnionFs::StackEventTracer *
0x14007610e  lea     r9, aUnionfsUtilsRe_4; "UnionFs::Utils::ReplaceFileBacking"
0x140076115  mov     [rsp+58h+var_38], rax; char *
0x14007611a  mov     rdx, rbx; int
0x14007611d  mov     ecx, edi; this
0x14007611f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076124  mov     rcx, [rbp+Context]; Context
0x140076128  test    rcx, rcx
0x14007612b  jz      short loc_140076139
0x14007612d  call    cs:__imp_FltReleaseContext
0x140076134  nop     dword ptr [rax+rax+00h]
0x140076139  mov     eax, edi
0x14007613b  jmp     loc_1400762EE
0x140076140  mov     rcx, [rbp+Context]; Context
0x140076144  test    rcx, rcx
0x140076147  jz      short loc_140076155
0x140076149  call    cs:__imp_FltReleaseContext
0x140076150  nop     dword ptr [rax+rax+00h]
0x140076155  mov     rdx, [r12]; FileObject
0x140076159  lea     rax, [rbp+Context]
0x14007615d  lea     r8, [rbp+OldContext]; OldContext
0x140076161  mov     qword ptr [rbp+var_28], rax
0x140076165  mov     rcx, r13; Instance
0x140076168  mov     [rbp+Context], 0
0x140076170  mov     [rbp+OldContext], 0
0x140076178  mov     [rbp+var_18], 1
0x14007617c  call    cs:__imp_FltDeleteStreamContext
0x140076183  nop     dword ptr [rax+rax+00h]
0x140076188  cmp     [rbp+var_18], 0
0x14007618c  mov     edi, eax
0x14007618e  jz      short loc_1400761AF
0x140076190  mov     r8, qword ptr [rbp+var_28]
0x140076194  mov     rdx, [rbp+OldContext]
0x140076198  mov     rcx, [r8]; Context
0x14007619b  mov     [r8], rdx
0x14007619e  test    rcx, rcx
0x1400761a1  jz      short loc_1400761AF
0x1400761a3  call    cs:__imp_FltReleaseContext
0x1400761aa  nop     dword ptr [rax+rax+00h]
0x1400761af  test    edi, edi
0x1400761b1  jns     short loc_140076223
0x1400761b3  lea     rax, aApiDeletingStr; "API: Deleting stream context"
0x1400761ba  mov     r8, 515000A0469h; struct UnionFs::StackEventTracer *
0x1400761c4  lea     r9, aUnionfsUfsstre_7; "UnionFs::UfsStreamCtx::FltDelete"
0x1400761cb  mov     [rsp+58h+var_38], rax; char *
0x1400761d0  mov     rdx, rbx; int
0x1400761d3  mov     ecx, edi; this
0x1400761d5  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400761da  mov     rcx, [rbp+Context]; Context
0x1400761de  mov     [rbp+Context], 0
0x1400761e6  test    rcx, rcx
0x1400761e9  jz      short loc_1400761F7
0x1400761eb  call    cs:__imp_FltReleaseContext
0x1400761f2  nop     dword ptr [rax+rax+00h]
0x1400761f7  lea     rax, aPushRemovingSt; "PUSH: Removing stream context from laye"...
0x1400761fe  mov     r8, 51800211A3Fh; struct UnionFs::StackEventTracer *
0x140076208  lea     r9, aUnionfsUtilsRe_4; "UnionFs::Utils::ReplaceFileBacking"
0x14007620f  mov     [rsp+58h+var_38], rax; char *
0x140076214  mov     rdx, rbx; int
0x140076217  mov     ecx, edi; this
0x140076219  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007621e  jmp     loc_140076139
0x140076223  mov     rax, [rbp+Context]
0x140076227  lea     r8, [rbp+Context]
0x14007622b  mov     rdx, [r15]
0x14007622e  mov     r9, rbx
0x140076231  mov     rcx, [rbp+Instance]
0x140076235  mov     [rbp+Context], rax
0x140076239  mov     dword ptr [rsp+58h+var_38], 2
0x140076241  call    ?FltSet@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@W4SetContextOperation@2@@Z; UnionFs::UfsStreamCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,UnionFs::SetContextOperation)
0x140076246  mov     edi, eax
0x140076248  test    eax, eax
0x14007624a  jns     short loc_140076262
0x14007624c  lea     rax, aPushSettingStr; "PUSH: Setting stream context on scratch"...
0x140076253  mov     r8, 51900211A4Ch
0x14007625d  jmp     loc_14007610E
0x140076262  mov     rcx, [rbp+Context]; Context
0x140076266  test    rcx, rcx
0x140076269  jz      short loc_140076277
0x14007626b  call    cs:__imp_FltReleaseContext
0x140076272  nop     dword ptr [rax+rax+00h]
0x140076277  mov     rax, [r14]
0x14007627a  mov     qword ptr [rbp+var_28], rax
0x14007627e  mov     rax, [r14+8]
0x140076282  mov     [rbp+OldContext], rax
0x140076286  test    rax, rax
0x140076289  jz      short loc_14007628F
0x14007628b  lock inc dword ptr [rax+8]
0x14007628f  mov     r8, qword ptr [rbp+arg_28]; int
0x140076293  lea     rdx, [rbp+var_28]; int
0x140076297  mov     r9, r15; int
0x14007629a  mov     [rsp+58h+var_38], rbx; struct _FILE_OBJECT *
0x14007629f  mov     rcx, rsi; int
0x1400762a2  call    ?ReplaceBackingForSFOs@UfsStreamCtx@UnionFs@@QEAAJV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamCtx::ReplaceBackingForSFOs(utl::shared_ptr<UnionFs::UfsLayerCtx>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &,UnionFs::StackEventTracer &)
0x1400762a7  mov     edi, eax
0x1400762a9  test    eax, eax
0x1400762ab  jns     short loc_1400762C3
0x1400762ad  lea     rax, aPushReplacingS_1; "PUSH: Replacing SFO backings"
0x1400762b4  mov     r8, 4DA00211A56h
0x1400762be  jmp     loc_140076208
0x1400762c3  lea     rdx, [rsi+48h]
0x1400762c7  lea     rcx, [rbp+Context]
0x1400762cb  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x1400762d0  mov     rcx, [rbp+Context]; FastMutex
0x1400762d4  mov     byte ptr [rsi+0A0h], 1
0x1400762db  test    rcx, rcx
0x1400762de  jz      short loc_1400762EC
0x1400762e0  call    cs:__imp_ExReleaseFastMutex
0x1400762e7  nop     dword ptr [rax+rax+00h]
0x1400762ec  xor     eax, eax
0x1400762ee  add     rsp, 58h
0x1400762f2  pop     r15
0x1400762f4  pop     r14
0x1400762f6  pop     r13
0x1400762f8  pop     r12
0x1400762fa  pop     rdi
0x1400762fb  pop     rsi
0x1400762fc  pop     rbx
0x1400762fd  pop     rbp
0x1400762fe  retn
```
