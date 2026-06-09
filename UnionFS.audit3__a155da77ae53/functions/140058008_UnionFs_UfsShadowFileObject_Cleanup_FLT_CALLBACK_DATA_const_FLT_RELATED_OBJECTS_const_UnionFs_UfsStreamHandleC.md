# UnionFs::UfsShadowFileObject::Cleanup(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &)

- ea: `0x140058008`
- end: `0x1400584ee`
- name: `?Cleanup@UfsShadowFileObject@UnionFs@@QEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `1254`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsShadowFileObject *__hidden this@<rcx>, const struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002d6d0`

## callees

- `0x14000f81c`
- `0x140010168`
- `0x1400274cc`
- `0x14002be84`
- `0x140056974`
- `0x140056bd0`
- `0x140056c7c`
- `0x140058008`
- `0x14005a0ec`
- `0x14005a228`
- `0x14005a3a8`
- `0x140069bcc`
- `0x1400702b8`
- `0x140074d3c`
- `0x140075e30`
- `0x140079cfc`
- `0x140079d44`
- `0x140079d8c`
- `0x14007a094`
- `0x14007a0c0`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140058309`
- `ntoskrnl!ZwClose` at `0x140058491`
- `ntoskrnl!ZwClose` at `0x140058309`
- `ntoskrnl!ZwClose` at `0x140058491`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400584bf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400584bf`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400582bf`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400582bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005834b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005834b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058357`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058357`
- `FLTMGR!FltReferenceContext` at `0x1400580a7`
- `FLTMGR!FltReferenceContext` at `0x1400580a7`
- `FLTMGR!FltReleaseContext` at `0x14005824a`
- `FLTMGR!FltReleaseContext` at `0x140058267`
- `FLTMGR!FltReleaseContext` at `0x14005824a`
- `FLTMGR!FltReleaseContext` at `0x140058267`

## string_xrefs

- `0x140058204`: `PUSH: Prepare for delete on SFO cleanup`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsShadowFileObject::Cleanup(
        UnionFs::UfsShadowFileObject *this,
        const struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_CALLBACK_DATA *a3,
        struct UnionFs::UfsStreamHandleCtx *a4,
        struct _ERESOURCE *a5,
        struct UnionFs::StackEventTracer *a6)
{
  __int64 v6; // r12
  __int64 v8; // r14
  unsigned __int64 *v9; // rdx
  char *v10; // rsi
  __int64 v11; // rbx
  _BYTE *v12; // r15
  int BackingLayer; // eax
  unsigned __int64 *v14; // rdx
  struct _FILE_OBJECT *v15; // rbx
  int v16; // ebx
  PFLT_CONTEXT v17; // rcx
  PFLT_CONTEXT v18; // rbx
  int v19; // eax
  char v20; // bl
  unsigned __int64 *v21; // rdx
  HANDLE v22; // rbx
  struct _ERESOURCE *v23; // rcx
  char v24; // r15
  int v25; // esi
  int v26; // eax
  PVOID v27; // rbx
  char *v29; // [rsp+28h] [rbp-81h]
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-69h] BYREF
  PVOID Entry; // [rsp+48h] [rbp-61h] BYREF
  const struct _FLT_CALLBACK_DATA *v32; // [rsp+50h] [rbp-59h]
  PERESOURCE Resource; // [rsp+58h] [rbp-51h] BYREF
  utl::_RefCountBase *v34[2]; // [rsp+60h] [rbp-49h] BYREF
  struct _FLT_CALLBACK_DATA *v35; // [rsp+70h] [rbp-39h]
  FsFltWil::Details *v36; // [rsp+78h] [rbp-31h] BYREF
  char v37; // [rsp+80h] [rbp-29h] BYREF
  char v38; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v39[12]; // [rsp+90h] [rbp-19h] BYREF

  v6 = *((_QWORD *)this + 4);
  v8 = *((_QWORD *)this + 3);
  v35 = (struct _FLT_CALLBACK_DATA *)a2;
  *(_QWORD *)v39 = a4;
  v32 = a3;
  Resource = a5;
  FsFltWil::AcquirePushLockShared(&Context, v6 + 32);
  v10 = (char *)(v6 + 16);
  v11 = *(_QWORD *)(v6 + 16);
  if ( Context )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context, v9);
  if ( !v11 )
    MicrosoftTelemetryAssertTriggeredMsgKM("fsContext2->GetBackingFileHandle()");
  Entry = 0;
  if ( UnionFs::CloseHandleWithResult )
  {
    v12 = *(_BYTE **)(v8 + 136);
    FltReferenceContext(v12);
    if ( !v12[160] )
    {
LABEL_22:
      FltReleaseContext(v12);
      goto LABEL_23;
    }
    *(_OWORD *)v34 = 0;
    BackingLayer = UnionFs::UfsFsContext2::TryGetBackingLayer(v6, v34, a6);
    if ( BackingLayer < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)BackingLayer,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x4F2001D03E2LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "PUSH: No backing layer",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
      goto LABEL_20;
    }
    Context = 0;
    FsFltWil::AcquirePushLockShared(&v36, v6 + 32);
    v15 = *(struct _FILE_OBJECT **)(v6 + 24);
    if ( v36 )
      FsFltWil::Details::ReleasePushLockShared(v36, v14);
    v16 = UnionFs::UfsFileCtx::FltGet(**((PFLT_INSTANCE **)v34[0] + 1), v15, (int)a6);
    if ( v16 >= 0 )
    {
      v18 = Context;
      if ( *((_BYTE *)Context + 56) )
      {
        v19 = UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(
                v35,
                v32,
                *(struct _FLT_RELATED_OBJECTS **)v39,
                (const struct UnionFs::UfsStreamHandleCtx *)Context,
                (__int64)Resource,
                (UnionFs::CleanupContext **)&Entry,
                a6);
        if ( v19 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v19,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x4F8001D0416LL,
            (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
            "PUSH: Prepare for delete on SFO cleanup",
            v29);
          UnionFs::StackEventTracer::LogError(a6);
          *(_DWORD *)a6 = 0;
          *((_WORD *)a6 + 274) = 0;
        }
      }
      if ( !v18 )
        goto LABEL_20;
      v17 = v18;
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("UfsShadowFileObject::Cleanup failed to get backing file context!");
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v16,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x4F4001D03F9LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "PUSH: Getting backing file context",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      v17 = Context;
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
      if ( !v17 )
        goto LABEL_20;
    }
    FltReleaseContext(v17);
LABEL_20:
    if ( v34[1] )
      utl::_RefCountBase::_DecStrong(v34[1]);
    goto LABEL_22;
  }
LABEL_23:
  FsFltWil::AcquireResourceExclusive(&Resource, *(_QWORD *)(v8 + 120) + 56LL);
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    UnionFs::Utils::CheckOplock(v35, (__int64)v32, (PVOID *)(v8 + 88), (int)a6, 0x80000000);
    if ( *(_BYTE *)(*(_QWORD *)(v8 + 144) + 96LL) || (v20 = 1, !FsRtlOplockIsFastIoPossible((POPLOCK)(v8 + 88))) )
      v20 = 0;
    *(_BYTE *)(v8 + 5) = v20;
  }
  FsFltWil::AcquirePushLockExclusive(v39, v6 + 32);
  v22 = 0;
  if ( &v37 != v10 )
  {
    v22 = *(HANDLE *)v10;
    *(_QWORD *)v10 = 0;
  }
  if ( v10 != &v38 )
  {
    if ( *(_QWORD *)v10 )
      ZwClose(*(HANDLE *)v10);
    *(_QWORD *)v10 = 0;
  }
  if ( *(_QWORD *)v39 )
    FsFltWil::Details::ReleasePushLockExclusive(*(FsFltWil::Details **)v39, v21);
  *(_DWORD *)(v6 + 40) |= 2u;
  *((_DWORD *)this + 20) |= 0x4000u;
  v23 = Resource;
  v24 = *((_BYTE *)this + 72);
  *((_QWORD *)this + 6) = 0;
  if ( v23 )
  {
    ExReleaseResourceLite(v23);
    KeLeaveCriticalRegion();
  }
  v25 = 0;
  if ( v24 )
  {
    v25 = UnionFs::UfsFsContext2::UnlockAll((UnionFs::UfsFsContext2 *)v6, a6);
    if ( v25 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v25,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0xC0001D0452LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "PUSH: Unlocking byte-range locks",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
    }
  }
  UnionFs::UfsShadowFileObject::UpdateFileSizesFromBFO(this);
  UnionFs::Utils::RemoveShareAccess(this, 14);
  v26 = *((_DWORD *)this + 20);
  _InterlockedDecrement((volatile signed __int32 *)(v8 + 208));
  if ( (v26 & 8) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)(v8 + 212));
  if ( Entry )
  {
    *(_QWORD *)&v39[4] = 0;
    *(_DWORD *)v39 = 1;
    v25 = ((__int64 (__fastcall *)(HANDLE, _QWORD, __int64, _BYTE *))UnionFs::CloseHandleWithResult)(v22, 0, 12, v39);
    if ( v25 >= 0 )
    {
      UnionFs::Utils::HandlePostCleanupWork(v32, &Entry, *(unsigned int *)&v39[8], a6);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Closing backing file handle");
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v25,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x4F9001D0474LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "API: Closing backing file handle",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
    }
  }
  else if ( v22 )
  {
    ZwClose(v22);
  }
  v27 = Entry;
  if ( Entry )
  {
    UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)Entry);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 800), v27);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x140058008  push    rbp
0x14005800a  push    rbx
0x14005800b  push    rsi
0x14005800c  push    rdi
0x14005800d  push    r12
0x14005800f  push    r13
0x140058011  push    r14
0x140058013  push    r15
0x140058015  lea     rbp, [rsp-0Fh]
0x14005801a  sub     rsp, 0B8h
0x140058021  mov     rax, cs:__security_cookie
0x140058028  xor     rax, rsp
0x14005802b  mov     [rbp+47h+var_50], rax
0x14005802f  mov     r12, [rcx+20h]
0x140058033  mov     r13, rcx
0x140058036  mov     rax, [rbp+47h+arg_20]
0x14005803a  mov     r14, [rcx+18h]
0x14005803e  lea     rcx, [rbp+47h+Context]
0x140058042  mov     rdi, [rbp+47h+arg_28]
0x140058046  mov     [rbp+47h+var_80], rdx
0x14005804a  lea     rdx, [r12+20h]
0x14005804f  mov     [rbp+47h+var_60], r9
0x140058053  mov     [rbp+47h+var_A0], r8
0x140058057  mov     [rbp+47h+Resource], rax
0x14005805b  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140058060  mov     rcx, [rbp+47h+Context]; this
0x140058064  lea     rsi, [r12+10h]
0x140058069  mov     rbx, [rsi]
0x14005806c  test    rcx, rcx
0x14005806f  jz      short loc_140058076
0x140058071  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140058076  test    rbx, rbx
0x140058079  jnz     short loc_140058087
0x14005807b  lea     rcx, aFscontext2Getb; "fsContext2->GetBackingFileHandle()"
0x140058082  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140058087  cmp     cs:?CloseHandleWithResult@UnionFs@@3P6AJPEAXDKPEAU_OBJECT_CLOSE_RESULT@1@@ZEA, 0; long (*UnionFs::CloseHandleWithResult)(void *,char,ulong,UnionFs::_OBJECT_CLOSE_RESULT *)
0x14005808f  mov     [rbp+47h+Entry], 0
0x140058097  jz      loc_140058273
0x14005809d  mov     r15, [r14+88h]
0x1400580a4  mov     rcx, r15; Context
0x1400580a7  call    cs:__imp_FltReferenceContext
0x1400580ae  nop     dword ptr [rax+rax+00h]
0x1400580b3  cmp     byte ptr [r15+0A0h], 0
0x1400580bb  jz      loc_140058264
0x1400580c1  xorps   xmm0, xmm0
0x1400580c4  lea     rdx, [rbp+47h+var_90]
0x1400580c8  mov     r8, rdi
0x1400580cb  mov     rcx, r12
0x1400580ce  movdqu  xmmword ptr [rbp+47h+var_90], xmm0
0x1400580d3  call    ?TryGetBackingLayer@UfsFsContext2@UnionFs@@QEBAJAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::TryGetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)
0x1400580d8  test    eax, eax
0x1400580da  jns     short loc_14005811F
0x1400580dc  lea     rcx, aPushNoBackingL; "PUSH: No backing layer"
0x1400580e3  mov     r8, 4F2001D03E2h; struct UnionFs::StackEventTracer *
0x1400580ed  mov     [rsp+0F0h+var_D0], rcx; char *
0x1400580f2  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x1400580f9  mov     ecx, eax; this
0x1400580fb  mov     rdx, rdi; int
0x1400580fe  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058103  mov     rcx, rdi; this
0x140058106  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14005810b  xor     eax, eax
0x14005810d  mov     dword ptr [rdi], 0
0x140058113  mov     [rdi+224h], ax
0x14005811a  jmp     loc_140058256
0x14005811f  lea     rdx, [r12+20h]
0x140058124  mov     [rbp+47h+Context], 0
0x14005812c  lea     rcx, [rbp+47h+var_78]
0x140058130  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140058135  mov     rcx, [rbp+47h+var_78]; this
0x140058139  mov     rbx, [r12+18h]
0x14005813e  test    rcx, rcx
0x140058141  jz      short loc_140058148
0x140058143  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140058148  mov     rax, [rbp+47h+var_90]
0x14005814c  lea     r9, [rbp+47h+Context]
0x140058150  xor     r8d, r8d
0x140058153  mov     [rsp+0F0h+var_D0], rdi; int
0x140058158  mov     rdx, rbx; FileObject
0x14005815b  mov     rcx, [rax+8]
0x14005815f  mov     rcx, [rcx]; Instance
0x140058162  call    ?FltGet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFileCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140058167  mov     ebx, eax
0x140058169  test    eax, eax
0x14005816b  jns     short loc_1400581C9
0x14005816d  lea     rcx, aUfsshadowfileo; "UfsShadowFileObject::Cleanup failed to "...
0x140058174  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140058179  lea     rax, aPushGettingBac_0; "PUSH: Getting backing file context"
0x140058180  mov     r8, 4F4001D03F9h; struct UnionFs::StackEventTracer *
0x14005818a  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x140058191  mov     [rsp+0F0h+var_D0], rax; char *
0x140058196  mov     rdx, rdi; int
0x140058199  mov     ecx, ebx; this
0x14005819b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400581a0  mov     rcx, rdi; this
0x1400581a3  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x1400581a8  mov     rcx, [rbp+47h+Context]
0x1400581ac  xor     eax, eax
0x1400581ae  mov     dword ptr [rdi], 0
0x1400581b4  mov     [rdi+224h], ax
0x1400581bb  test    rcx, rcx
0x1400581be  jz      loc_140058256
0x1400581c4  jmp     loc_14005824A
0x1400581c9  mov     rbx, [rbp+47h+Context]
0x1400581cd  mov     al, [rbx+38h]
0x1400581d0  nop
0x1400581d1  test    al, al
0x1400581d3  jz      short loc_140058242
0x1400581d5  mov     r8, [rbp+47h+var_60]
0x1400581d9  lea     rax, [rbp+47h+Entry]
0x1400581dd  mov     rdx, [rbp+47h+var_A0]
0x1400581e1  mov     r9, rbx
0x1400581e4  mov     rcx, [rbp+47h+var_80]
0x1400581e8  mov     [rsp+0F0h+var_C0], rdi
0x1400581ed  mov     [rsp+0F0h+var_C8], rax; char *
0x1400581f2  mov     rax, [rbp+47h+Resource]
0x1400581f6  mov     [rsp+0F0h+var_D0], rax
0x1400581fb  call    ?PrepareForDeleteOnCleanupIfNeeded@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVUfsUnionCtx@2@AEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsFileCtx &,UnionFs::UfsUnionCtx &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &,UnionFs::StackEventTracer &)
0x140058200  test    eax, eax
0x140058202  jns     short loc_140058242
0x140058204  lea     rcx, aPushPrepareFor; "PUSH: Prepare for delete on SFO cleanup"
0x14005820b  mov     r8, 4F8001D0416h; struct UnionFs::StackEventTracer *
0x140058215  mov     [rsp+0F0h+var_D0], rcx; char *
0x14005821a  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x140058221  mov     ecx, eax; this
0x140058223  mov     rdx, rdi; int
0x140058226  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005822b  mov     rcx, rdi; this
0x14005822e  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140058233  xor     eax, eax
0x140058235  mov     dword ptr [rdi], 0
0x14005823b  mov     [rdi+224h], ax
0x140058242  test    rbx, rbx
0x140058245  jz      short loc_140058256
0x140058247  mov     rcx, rbx; Context
0x14005824a  call    cs:__imp_FltReleaseContext
0x140058251  nop     dword ptr [rax+rax+00h]
0x140058256  mov     rcx, [rbp+47h+var_90+8]; this
0x14005825a  test    rcx, rcx
0x14005825d  jz      short loc_140058264
0x14005825f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058264  mov     rcx, r15; Context
0x140058267  call    cs:__imp_FltReleaseContext
0x14005826e  nop     dword ptr [rax+rax+00h]
0x140058273  mov     rdx, [r14+78h]
0x140058277  lea     rcx, [rbp+47h+Resource]
0x14005827b  add     rdx, 38h ; '8'
0x14005827f  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140058284  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140058289  test    eax, eax
0x14005828b  jz      short loc_1400582D5
0x14005828d  mov     rdx, [rbp+47h+var_A0]
0x140058291  lea     r8, [r14+58h]
0x140058295  mov     rcx, [rbp+47h+var_80]
0x140058299  mov     r9, rdi
0x14005829c  mov     dword ptr [rsp+0F0h+var_D0], 80000000h
0x1400582a4  call    ?CheckOplock@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEAVStackEventTracer@2@W4CheckOplockFlags@12@@Z; UnionFs::Utils::CheckOplock(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::StackEventTracer &,UnionFs::Utils::CheckOplockFlags)
0x1400582a9  mov     rax, [r14+90h]
0x1400582b0  cmp     byte ptr [rax+60h], 0
0x1400582b4  jnz     short loc_1400582CF
0x1400582b6  lea     rcx, [r14+58h]; Oplock
0x1400582ba  mov     ebx, 1
0x1400582bf  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x1400582c6  nop     dword ptr [rax+rax+00h]
0x1400582cb  test    al, al
0x1400582cd  jnz     short loc_1400582D1
0x1400582cf  xor     ebx, ebx
0x1400582d1  mov     [r14+5], bl
0x1400582d5  lea     rdx, [r12+20h]
0x1400582da  lea     rcx, [rbp+47h+var_60]
0x1400582de  call    ?AcquirePushLockExclusive@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockExclusive@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockExclusive(unsigned __int64 &)
0x1400582e3  lea     rax, [rbp+47h+var_70]
0x1400582e7  xor     ebx, ebx
0x1400582e9  cmp     rax, rsi
0x1400582ec  jz      short loc_1400582F8
0x1400582ee  mov     rbx, [rsi]
0x1400582f1  mov     qword ptr [rsi], 0
0x1400582f8  lea     rax, [rbp+47h+var_68]
0x1400582fc  cmp     rsi, rax
0x1400582ff  jz      short loc_14005831C
0x140058301  mov     rcx, [rsi]; Handle
0x140058304  test    rcx, rcx
0x140058307  jz      short loc_140058315
0x140058309  call    cs:__imp_ZwClose
0x140058310  nop     dword ptr [rax+rax+00h]
0x140058315  mov     qword ptr [rsi], 0
0x14005831c  mov     rcx, [rbp+47h+var_60]; this
0x140058320  test    rcx, rcx
0x140058323  jz      short loc_14005832A
0x140058325  call    ?ReleasePushLockExclusive@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockExclusive(unsigned __int64 *)
0x14005832a  or      dword ptr [r12+28h], 2
0x140058330  bts     dword ptr [r13+50h], 0Eh
0x140058336  mov     rcx, [rbp+47h+Resource]; Resource
0x14005833a  mov     r15b, [r13+48h]
0x14005833e  mov     qword ptr [r13+30h], 0
0x140058346  test    rcx, rcx
0x140058349  jz      short loc_140058363
0x14005834b  call    cs:__imp_ExReleaseResourceLite
0x140058352  nop     dword ptr [rax+rax+00h]
0x140058357  call    cs:__imp_KeLeaveCriticalRegion
0x14005835e  nop     dword ptr [rax+rax+00h]
0x140058363  xor     esi, esi
0x140058365  test    r15b, r15b
0x140058368  jz      short loc_1400583B9
0x14005836a  mov     rdx, rdi; struct UnionFs::StackEventTracer *
0x14005836d  mov     rcx, r12; this
0x140058370  call    ?UnlockAll@UfsFsContext2@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::UnlockAll(UnionFs::StackEventTracer &)
0x140058375  mov     esi, eax
0x140058377  test    eax, eax
0x140058379  jns     short loc_1400583B9
0x14005837b  lea     rax, aPushUnlockingB; "PUSH: Unlocking byte-range locks"
0x140058382  mov     r8, 0C0001D0452h; struct UnionFs::StackEventTracer *
0x14005838c  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x140058393  mov     [rsp+0F0h+var_D0], rax; char *
0x140058398  mov     rdx, rdi; int
0x14005839b  mov     ecx, esi; this
0x14005839d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400583a2  mov     rcx, rdi; this
0x1400583a5  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x1400583aa  xor     eax, eax
0x1400583ac  mov     dword ptr [rdi], 0
0x1400583b2  mov     [rdi+224h], ax
0x1400583b9  mov     rcx, r13; this
0x1400583bc  call    ?UpdateFileSizesFromBFO@UfsShadowFileObject@UnionFs@@QEAAXXZ; UnionFs::UfsShadowFileObject::UpdateFileSizesFromBFO(void)
0x1400583c1  xor     r8d, r8d
0x1400583c4  mov     rcx, r13
0x1400583c7  lea     edx, [r8+0Eh]
0x1400583cb  call    ?RemoveShareAccess@Utils@UnionFs@@YAXAEAU_FILE_OBJECT@@W4ShareAccessCaller@2@PEAVUfsFsContext@2@@Z; UnionFs::Utils::RemoveShareAccess(_FILE_OBJECT &,UnionFs::ShareAccessCaller,UnionFs::UfsFsContext *)
0x1400583d0  mov     eax, [r13+50h]
0x1400583d4  nop
0x1400583d5  lock dec dword ptr [r14+0D0h]
0x1400583dd  nop
0x1400583de  bt      eax, 3
0x1400583e2  jnb     short loc_1400583EE
0x1400583e4  nop
0x1400583e5  lock dec dword ptr [r14+0D4h]
0x1400583ed  nop
0x1400583ee  cmp     [rbp+47h+Entry], 0
0x1400583f3  jz      loc_140058489
0x1400583f9  mov     rax, cs:?CloseHandleWithResult@UnionFs@@3P6AJPEAXDKPEAU_OBJECT_CLOSE_RESULT@1@@ZEA; long (*UnionFs::CloseHandleWithResult)(void *,char,ulong,UnionFs::_OBJECT_CLOSE_RESULT *)
0x140058400  lea     r9, [rbp+47h+var_60]
0x140058404  xor     edx, edx
0x140058406  mov     [rbp+47h+var_60+4], 0
0x14005840e  mov     rcx, rbx
0x140058411  mov     dword ptr [rbp+47h+var_60], 1
0x140058418  lea     r8d, [rdx+0Ch]
0x14005841c  call    _guard_dispatch_icall
0x140058421  mov     esi, eax
0x140058423  test    eax, eax
0x140058425  jns     short loc_140058473
0x140058427  lea     rcx, aClosingBacking; "Closing backing file handle"
0x14005842e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140058433  lea     rax, aApiClosingBack; "API: Closing backing file handle"
0x14005843a  mov     r8, 4F9001D0474h; struct UnionFs::StackEventTracer *
0x140058444  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x14005844b  mov     [rsp+0F0h+var_D0], rax; char *
0x140058450  mov     rdx, rdi; int
0x140058453  mov     ecx, esi; this
0x140058455  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005845a  mov     rcx, rdi; this
0x14005845d  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140058462  xor     eax, eax
0x140058464  mov     dword ptr [rdi], 0
0x14005846a  mov     [rdi+224h], ax
0x140058471  jmp     short loc_14005849D
0x140058473  mov     r8d, [rbp+47h+var_58]
0x140058477  lea     rdx, [rbp+47h+Entry]
0x14005847b  mov     rcx, [rbp+47h+var_A0]
0x14005847f  mov     r9, rdi
0x140058482  call    ?HandlePostCleanupWork@Utils@UnionFs@@YAXAEBU_FLT_RELATED_OBJECTS@@$$QEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@KAEAVStackEventTracer@2@@Z; UnionFs::Utils::HandlePostCleanupWork(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &&,ulong,UnionFs::StackEventTracer &)
0x140058487  jmp     short loc_14005849D
0x140058489  test    rbx, rbx
0x14005848c  jz      short loc_14005849D
0x14005848e  mov     rcx, rbx; Handle
0x140058491  call    cs:__imp_ZwClose
0x140058498  nop     dword ptr [rax+rax+00h]
0x14005849d  mov     rbx, [rbp+47h+Entry]
0x1400584a1  test    rbx, rbx
0x1400584a4  jz      short loc_1400584CB
0x1400584a6  mov     rcx, rbx; this
0x1400584a9  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x1400584ae  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400584b5  mov     rdx, rbx; Entry
0x1400584b8  add     rcx, 320h; Lookaside
0x1400584bf  call    cs:__imp_ExFreeToLookasideListEx
0x1400584c6  nop     dword ptr [rax+rax+00h]
0x1400584cb  mov     eax, esi
0x1400584cd  mov     rcx, [rbp+47h+var_50]
0x1400584d1  xor     rcx, rsp; StackCookie
0x1400584d4  call    __security_check_cookie
0x1400584d9  add     rsp, 0B8h
0x1400584e0  pop     r15
0x1400584e2  pop     r14
0x1400584e4  pop     r13
0x1400584e6  pop     r12
0x1400584e8  pop     rdi
0x1400584e9  pop     rsi
0x1400584ea  pop     rbx
0x1400584eb  pop     rbp
0x1400584ec  retn
  ... truncated ...
```
