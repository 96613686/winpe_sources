# UnionFs::UfsShadowFileObject::Close(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &)

- ea: `0x140058374`
- end: `0x140058600`
- name: `?Close@UfsShadowFileObject@UnionFs@@QEAAXAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@@Z`
- size: `652`
- prototype: `void __fastcall(UnionFs::UfsShadowFileObject *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000cb80`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x14000f880`
- `0x14000ffb4`
- `0x140010148`
- `0x140024bd8`
- `0x1400276c4`
- `0x14002793c`
- `0x140056ac4`
- `0x140058374`
- `0x1400699dc`
- `0x1400799a4`
- `0x14007af90`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400584a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005859d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400584a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005859d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400584b6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400584b6`
- `FLTMGR!FltDeleteContext` at `0x1400583f4`
- `FLTMGR!FltDeleteContext` at `0x1400583f4`
- `FLTMGR!FltReleaseContext` at `0x14005856b`
- `FLTMGR!FltReleaseContext` at `0x14005857f`
- `FLTMGR!FltReleaseContext` at `0x14005856b`
- `FLTMGR!FltReleaseContext` at `0x14005857f`
- `FLTMGR!FltObjectDereference` at `0x1400585ec`
- `FLTMGR!FltObjectDereference` at `0x1400585ec`

## pseudocode

```c
void __fastcall UnionFs::UfsShadowFileObject::Close(
        UnionFs::UfsShadowFileObject *this,
        const struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3)
{
  UnionFs::UfsFsContext2 *v5; // rdi
  void *v6; // rbx
  PFLT_CONTEXT v7; // rsi
  __int64 v8; // r13
  __int64 v9; // rsi
  __int64 v10; // rdx
  void **v11; // r14
  void **v12; // rsi
  void **v13; // rax
  __int64 v14; // rcx
  struct _FLT_INSTANCE *Instance; // rcx
  int v16; // esi
  PFLT_CONTEXT v17; // rcx
  PVOID *v18; // rsi
  const char *v19; // [rsp+28h] [rbp-D8h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-D0h] BYREF
  struct _FLT_CALLBACK_DATA *v21; // [rsp+38h] [rbp-C8h]
  int v22[188]; // [rsp+40h] [rbp-C0h] BYREF

  v21 = (struct _FLT_CALLBACK_DATA *)a2;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v22, 0x183001D0485uLL);
  v5 = (UnionFs::UfsFsContext2 *)*((_QWORD *)this + 4);
  v6 = 0;
  *((_DWORD *)v5 + 10) |= 4u;
  *((_QWORD *)this + 2) = 0;
  UnionFs::UfsStreamHandleCtx::FltGet(&Context, a3->Instance);
  v7 = Context;
  if ( Context )
  {
    FltDeleteContext(Context);
    v6 = v7;
    *((_QWORD *)v7 + 9) = 0;
  }
  v8 = *((_QWORD *)this + 3);
  v9 = *(_QWORD *)(v8 + 136);
  FsFltWil::AcquireFastMutex(&Context, v9 + 72);
  v11 = (void **)(v9 + 40);
  v12 = v11;
  if ( v11[2] == v11 )
    goto LABEL_12;
  v13 = (void **)*v11;
  do
  {
    if ( v13[3] < this )
    {
      v14 = 2;
    }
    else
    {
      v12 = v13;
      v14 = 1;
    }
    v13 = (void **)v13[v14];
  }
  while ( v13 != &utl::_TreeSentinel );
  if ( v12 == v11 )
  {
LABEL_12:
    MicrosoftTelemetryAssertTriggeredMsgKM("Can't find SFO to forget!");
    if ( v12 == v11 )
      goto LABEL_15;
    goto LABEL_13;
  }
  if ( this < v12[3] )
  {
    v12 = v11;
    goto LABEL_12;
  }
LABEL_13:
  LOBYTE(v10) = 1;
  utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_Traverse(v12, v10);
  utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_HeadUnlinkNode(v11, v12);
  v11[3] = (char *)v11[3] - 1;
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
LABEL_15:
  if ( Context )
    ExReleaseFastMutex((PFAST_MUTEX)Context);
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline()
    && (*((_DWORD *)this + 20) & 0x4000) == 0 )
  {
    UnionFs::Utils::CheckOplock(v21, (__int64)a3, (PVOID *)(v8 + 88), (int)v22, 0x80000000);
  }
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  Instance = a3->Instance;
  Context = 0;
  v16 = UnionFs::UfsInstanceCtx::FltGet(Instance);
  if ( v16 >= 0 )
  {
    v18 = (PVOID *)Context;
    _InterlockedDecrement((volatile signed __int32 *)Context + 28);
    FltObjectDereference(*v18);
    v17 = v18;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Failed to get instance context for IRP_MJ_CLOSE");
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)(unsigned int)v16,
      (int)v22,
      (struct UnionFs::StackEventTracer *)0x184001D04DDLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::Close",
      "ORIGIN: Failed to get instance context for IRP_MJ_CLOSE",
      v19);
    v17 = Context;
    if ( !Context )
      goto LABEL_23;
  }
  FltReleaseContext(v17);
LABEL_23:
  if ( v6 )
    FltReleaseContext(v6);
  if ( v5 )
  {
    UnionFs::UfsFsContext2::~UfsFsContext2(v5);
    ExFreePoolWithTag(v5, 0);
  }
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v22);
}

```

## disassembly

```asm
0x140058374  mov     [rsp-8+arg_18], rbx
0x140058379  push    rbp
0x14005837a  push    rsi
0x14005837b  push    rdi
0x14005837c  push    r12
0x14005837e  push    r13
0x140058380  push    r14
0x140058382  push    r15
0x140058384  lea     rbp, [rsp-240h]
0x14005838c  sub     rsp, 340h
0x140058393  mov     rax, cs:__security_cookie
0x14005839a  xor     rax, rsp
0x14005839d  mov     [rbp+270h+var_40], rax
0x1400583a4  mov     [rsp+370h+var_338], rdx
0x1400583a9  mov     r15, rcx
0x1400583ac  mov     rdx, 183001D0485h; unsigned __int64
0x1400583b6  lea     rcx, [rsp+370h+var_330]; this
0x1400583bb  mov     r12, r8
0x1400583be  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x1400583c3  mov     rdi, [r15+20h]
0x1400583c7  lea     rcx, [rsp+370h+Context]
0x1400583cc  mov     r8, r15
0x1400583cf  xor     ebx, ebx
0x1400583d1  or      dword ptr [rdi+28h], 4
0x1400583d5  mov     qword ptr [r15+10h], 0
0x1400583dd  mov     rdx, [r12+18h]
0x1400583e2  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SA?AV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &)
0x1400583e7  mov     rsi, [rsp+370h+Context]
0x1400583ec  test    rsi, rsi
0x1400583ef  jz      short loc_140058410
0x1400583f1  mov     rcx, rsi; Context
0x1400583f4  call    cs:__imp_FltDeleteContext
0x1400583fb  nop     dword ptr [rax+rax+00h]
0x140058400  mov     rbx, rsi
0x140058403  test    rsi, rsi
0x140058406  jz      short loc_140058410
0x140058408  mov     qword ptr [rsi+48h], 0
0x140058410  mov     r13, [r15+18h]
0x140058414  lea     rcx, [rsp+370h+Context]
0x140058419  mov     rsi, [r13+88h]
0x140058420  lea     rdx, [rsi+48h]
0x140058424  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140058429  lea     r14, [rsi+28h]
0x14005842d  mov     rsi, r14
0x140058430  cmp     [r14+10h], r14
0x140058434  jz      short loc_14005846C
0x140058436  mov     rax, [r14]
0x140058439  cmp     [rax+18h], r15
0x14005843d  jb      short loc_140058449
0x14005843f  mov     rsi, rax
0x140058442  mov     ecx, 8
0x140058447  jmp     short loc_14005844E
0x140058449  mov     ecx, 10h
0x14005844e  mov     rax, [rax+rcx]
0x140058452  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140058459  cmp     rax, rcx
0x14005845c  jnz     short loc_140058439
0x14005845e  cmp     rsi, r14
0x140058461  jz      short loc_14005846C
0x140058463  cmp     r15, [rsi+18h]
0x140058467  jnb     short loc_14005847D
0x140058469  mov     rsi, r14
0x14005846c  lea     rcx, aCanTFindSfoToF; "Can't find SFO to forget!"
0x140058473  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140058478  cmp     rsi, r14
0x14005847b  jz      short loc_1400584AC
0x14005847d  mov     dl, 1
0x14005847f  mov     rcx, rsi
0x140058482  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_Traverse(bool)
0x140058487  mov     rdx, rsi
0x14005848a  mov     rcx, r14
0x14005848d  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@@Z; utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>> *)
0x140058492  dec     qword ptr [r14+18h]
0x140058496  test    rsi, rsi
0x140058499  jz      short loc_1400584AC
0x14005849b  xor     edx, edx; Tag
0x14005849d  mov     rcx, rsi; P
0x1400584a0  call    cs:__imp_ExFreePoolWithTag
0x1400584a7  nop     dword ptr [rax+rax+00h]
0x1400584ac  mov     rcx, [rsp+370h+Context]; FastMutex
0x1400584b1  test    rcx, rcx
0x1400584b4  jz      short loc_1400584C2
0x1400584b6  call    cs:__imp_ExReleaseFastMutex
0x1400584bd  nop     dword ptr [rax+rax+00h]
0x1400584c2  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x1400584c7  test    eax, eax
0x1400584c9  jz      short loc_1400584F3
0x1400584cb  test    dword ptr [r15+50h], 4000h
0x1400584d3  jnz     short loc_1400584F3
0x1400584d5  mov     rcx, [rsp+370h+var_338]
0x1400584da  lea     r8, [r13+58h]
0x1400584de  lea     r9, [rsp+370h+var_330]
0x1400584e3  mov     dword ptr [rsp+370h+var_350], 80000000h
0x1400584eb  mov     rdx, r12
0x1400584ee  call    ?CheckOplock@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEAVStackEventTracer@2@W4CheckOplockFlags@12@@Z; UnionFs::Utils::CheckOplock(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::StackEventTracer &,UnionFs::Utils::CheckOplockFlags)
0x1400584f3  mov     qword ptr [r15+18h], 0
0x1400584fb  lea     r9, [rsp+370h+var_330]
0x140058500  mov     qword ptr [r15+20h], 0
0x140058508  lea     r8, [rsp+370h+Context]
0x14005850d  mov     rcx, [r12+18h]; Instance
0x140058512  xor     edx, edx
0x140058514  mov     [rsp+370h+Context], 0
0x14005851d  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140058522  mov     esi, eax
0x140058524  test    eax, eax
0x140058526  jns     loc_1400585DE
0x14005852c  lea     rcx, aFailedToGetIns; "Failed to get instance context for IRP_"...
0x140058533  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140058538  lea     rax, aOriginFailedTo; "ORIGIN: Failed to get instance context "...
0x14005853f  mov     r8, 184001D04DDh; struct UnionFs::StackEventTracer *
0x140058549  lea     r9, aUnionfsUfsshad_5; "UnionFs::UfsShadowFileObject::Close"
0x140058550  mov     [rsp+370h+var_350], rax; char *
0x140058555  lea     rdx, [rsp+370h+var_330]; int
0x14005855a  mov     ecx, esi; this
0x14005855c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058561  mov     rcx, [rsp+370h+Context]; Context
0x140058566  test    rcx, rcx
0x140058569  jz      short loc_140058577
0x14005856b  call    cs:__imp_FltReleaseContext
0x140058572  nop     dword ptr [rax+rax+00h]
0x140058577  test    rbx, rbx
0x14005857a  jz      short loc_14005858B
0x14005857c  mov     rcx, rbx; Context
0x14005857f  call    cs:__imp_FltReleaseContext
0x140058586  nop     dword ptr [rax+rax+00h]
0x14005858b  test    rdi, rdi
0x14005858e  jz      short loc_1400585A9
0x140058590  mov     rcx, rdi; this
0x140058593  call    ??1UfsFsContext2@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext2::~UfsFsContext2(void)
0x140058598  xor     edx, edx; Tag
0x14005859a  mov     rcx, rdi; P
0x14005859d  call    cs:__imp_ExFreePoolWithTag
0x1400585a4  nop     dword ptr [rax+rax+00h]
0x1400585a9  lea     rcx, [rsp+370h+var_330]; this
0x1400585ae  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x1400585b3  mov     rcx, [rbp+270h+var_40]
0x1400585ba  xor     rcx, rsp; StackCookie
0x1400585bd  call    __security_check_cookie
0x1400585c2  mov     rbx, [rsp+370h+arg_18]
0x1400585ca  add     rsp, 340h
0x1400585d1  pop     r15
0x1400585d3  pop     r14
0x1400585d5  pop     r13
0x1400585d7  pop     r12
0x1400585d9  pop     rdi
0x1400585da  pop     rsi
0x1400585db  pop     rbp
0x1400585dc  retn
0x1400585de  mov     rsi, [rsp+370h+Context]
0x1400585e3  nop
0x1400585e4  lock dec dword ptr [rsi+70h]
0x1400585e8  nop
0x1400585e9  mov     rcx, [rsi]; FltObject
0x1400585ec  call    cs:__imp_FltObjectDereference
0x1400585f3  nop     dword ptr [rax+rax+00h]
0x1400585f8  mov     rcx, rsi
0x1400585fb  jmp     loc_14005856B
```
