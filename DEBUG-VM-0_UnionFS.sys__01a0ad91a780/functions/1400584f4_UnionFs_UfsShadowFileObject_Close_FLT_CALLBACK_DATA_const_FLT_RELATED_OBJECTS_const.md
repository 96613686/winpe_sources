# UnionFs::UfsShadowFileObject::Close(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &)

- ea: `0x1400584f4`
- end: `0x140058780`
- name: `?Close@UfsShadowFileObject@UnionFs@@QEAAXAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@@Z`
- size: `652`
- prototype: `void __fastcall(UnionFs::UfsShadowFileObject *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000cb50`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x14000f8a0`
- `0x14000ffd4`
- `0x140010168`
- `0x140024c78`
- `0x140027764`
- `0x1400279dc`
- `0x140056c44`
- `0x1400584f4`
- `0x140069bcc`
- `0x140079cc4`
- `0x14007b2b0`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140058620`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005871d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058620`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005871d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058636`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058636`
- `FLTMGR!FltDeleteContext` at `0x140058574`
- `FLTMGR!FltDeleteContext` at `0x140058574`
- `FLTMGR!FltReleaseContext` at `0x1400586eb`
- `FLTMGR!FltReleaseContext` at `0x1400586ff`
- `FLTMGR!FltReleaseContext` at `0x1400586eb`
- `FLTMGR!FltReleaseContext` at `0x1400586ff`
- `FLTMGR!FltObjectDereference` at `0x14005876c`
- `FLTMGR!FltObjectDereference` at `0x14005876c`

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
0x1400584f4  mov     [rsp-8+arg_18], rbx
0x1400584f9  push    rbp
0x1400584fa  push    rsi
0x1400584fb  push    rdi
0x1400584fc  push    r12
0x1400584fe  push    r13
0x140058500  push    r14
0x140058502  push    r15
0x140058504  lea     rbp, [rsp-240h]
0x14005850c  sub     rsp, 340h
0x140058513  mov     rax, cs:__security_cookie
0x14005851a  xor     rax, rsp
0x14005851d  mov     [rbp+270h+var_40], rax
0x140058524  mov     [rsp+370h+var_338], rdx
0x140058529  mov     r15, rcx
0x14005852c  mov     rdx, 183001D0485h; unsigned __int64
0x140058536  lea     rcx, [rsp+370h+var_330]; this
0x14005853b  mov     r12, r8
0x14005853e  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140058543  mov     rdi, [r15+20h]
0x140058547  lea     rcx, [rsp+370h+Context]
0x14005854c  mov     r8, r15
0x14005854f  xor     ebx, ebx
0x140058551  or      dword ptr [rdi+28h], 4
0x140058555  mov     qword ptr [r15+10h], 0
0x14005855d  mov     rdx, [r12+18h]
0x140058562  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SA?AV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &)
0x140058567  mov     rsi, [rsp+370h+Context]
0x14005856c  test    rsi, rsi
0x14005856f  jz      short loc_140058590
0x140058571  mov     rcx, rsi; Context
0x140058574  call    cs:__imp_FltDeleteContext
0x14005857b  nop     dword ptr [rax+rax+00h]
0x140058580  mov     rbx, rsi
0x140058583  test    rsi, rsi
0x140058586  jz      short loc_140058590
0x140058588  mov     qword ptr [rsi+48h], 0
0x140058590  mov     r13, [r15+18h]
0x140058594  lea     rcx, [rsp+370h+Context]
0x140058599  mov     rsi, [r13+88h]
0x1400585a0  lea     rdx, [rsi+48h]
0x1400585a4  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x1400585a9  lea     r14, [rsi+28h]
0x1400585ad  mov     rsi, r14
0x1400585b0  cmp     [r14+10h], r14
0x1400585b4  jz      short loc_1400585EC
0x1400585b6  mov     rax, [r14]
0x1400585b9  cmp     [rax+18h], r15
0x1400585bd  jb      short loc_1400585C9
0x1400585bf  mov     rsi, rax
0x1400585c2  mov     ecx, 8
0x1400585c7  jmp     short loc_1400585CE
0x1400585c9  mov     ecx, 10h
0x1400585ce  mov     rax, [rax+rcx]
0x1400585d2  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1400585d9  cmp     rax, rcx
0x1400585dc  jnz     short loc_1400585B9
0x1400585de  cmp     rsi, r14
0x1400585e1  jz      short loc_1400585EC
0x1400585e3  cmp     r15, [rsi+18h]
0x1400585e7  jnb     short loc_1400585FD
0x1400585e9  mov     rsi, r14
0x1400585ec  lea     rcx, aCanTFindSfoToF; "Can't find SFO to forget!"
0x1400585f3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400585f8  cmp     rsi, r14
0x1400585fb  jz      short loc_14005862C
0x1400585fd  mov     dl, 1
0x1400585ff  mov     rcx, rsi
0x140058602  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_Traverse(bool)
0x140058607  mov     rdx, rsi
0x14005860a  mov     rcx, r14
0x14005860d  call    ?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@@Z; utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>> *)
0x140058612  dec     qword ptr [r14+18h]
0x140058616  test    rsi, rsi
0x140058619  jz      short loc_14005862C
0x14005861b  xor     edx, edx; Tag
0x14005861d  mov     rcx, rsi; P
0x140058620  call    cs:__imp_ExFreePoolWithTag
0x140058627  nop     dword ptr [rax+rax+00h]
0x14005862c  mov     rcx, [rsp+370h+Context]; FastMutex
0x140058631  test    rcx, rcx
0x140058634  jz      short loc_140058642
0x140058636  call    cs:__imp_ExReleaseFastMutex
0x14005863d  nop     dword ptr [rax+rax+00h]
0x140058642  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140058647  test    eax, eax
0x140058649  jz      short loc_140058673
0x14005864b  test    dword ptr [r15+50h], 4000h
0x140058653  jnz     short loc_140058673
0x140058655  mov     rcx, [rsp+370h+var_338]
0x14005865a  lea     r8, [r13+58h]
0x14005865e  lea     r9, [rsp+370h+var_330]
0x140058663  mov     dword ptr [rsp+370h+var_350], 80000000h
0x14005866b  mov     rdx, r12
0x14005866e  call    ?CheckOplock@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEAVStackEventTracer@2@W4CheckOplockFlags@12@@Z; UnionFs::Utils::CheckOplock(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::StackEventTracer &,UnionFs::Utils::CheckOplockFlags)
0x140058673  mov     qword ptr [r15+18h], 0
0x14005867b  lea     r9, [rsp+370h+var_330]
0x140058680  mov     qword ptr [r15+20h], 0
0x140058688  lea     r8, [rsp+370h+Context]
0x14005868d  mov     rcx, [r12+18h]; Instance
0x140058692  xor     edx, edx
0x140058694  mov     [rsp+370h+Context], 0
0x14005869d  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x1400586a2  mov     esi, eax
0x1400586a4  test    eax, eax
0x1400586a6  jns     loc_14005875E
0x1400586ac  lea     rcx, aFailedToGetIns; "Failed to get instance context for IRP_"...
0x1400586b3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400586b8  lea     rax, aOriginFailedTo; "ORIGIN: Failed to get instance context "...
0x1400586bf  mov     r8, 184001D04DDh; struct UnionFs::StackEventTracer *
0x1400586c9  lea     r9, aUnionfsUfsshad_5; "UnionFs::UfsShadowFileObject::Close"
0x1400586d0  mov     [rsp+370h+var_350], rax; char *
0x1400586d5  lea     rdx, [rsp+370h+var_330]; int
0x1400586da  mov     ecx, esi; this
0x1400586dc  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400586e1  mov     rcx, [rsp+370h+Context]; Context
0x1400586e6  test    rcx, rcx
0x1400586e9  jz      short loc_1400586F7
0x1400586eb  call    cs:__imp_FltReleaseContext
0x1400586f2  nop     dword ptr [rax+rax+00h]
0x1400586f7  test    rbx, rbx
0x1400586fa  jz      short loc_14005870B
0x1400586fc  mov     rcx, rbx; Context
0x1400586ff  call    cs:__imp_FltReleaseContext
0x140058706  nop     dword ptr [rax+rax+00h]
0x14005870b  test    rdi, rdi
0x14005870e  jz      short loc_140058729
0x140058710  mov     rcx, rdi; this
0x140058713  call    ??1UfsFsContext2@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext2::~UfsFsContext2(void)
0x140058718  xor     edx, edx; Tag
0x14005871a  mov     rcx, rdi; P
0x14005871d  call    cs:__imp_ExFreePoolWithTag
0x140058724  nop     dword ptr [rax+rax+00h]
0x140058729  lea     rcx, [rsp+370h+var_330]; this
0x14005872e  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140058733  mov     rcx, [rbp+270h+var_40]
0x14005873a  xor     rcx, rsp; StackCookie
0x14005873d  call    __security_check_cookie
0x140058742  mov     rbx, [rsp+370h+arg_18]
0x14005874a  add     rsp, 340h
0x140058751  pop     r15
0x140058753  pop     r14
0x140058755  pop     r13
0x140058757  pop     r12
0x140058759  pop     rdi
0x14005875a  pop     rsi
0x14005875b  pop     rbp
0x14005875c  retn
0x14005875e  mov     rsi, [rsp+370h+Context]
0x140058763  nop
0x140058764  lock dec dword ptr [rsi+70h]
0x140058768  nop
0x140058769  mov     rcx, [rsi]; FltObject
0x14005876c  call    cs:__imp_FltObjectDereference
0x140058773  nop     dword ptr [rax+rax+00h]
0x140058778  mov     rcx, rsi
0x14005877b  jmp     loc_1400586EB
```
