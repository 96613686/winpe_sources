# UnionFs::Utils::RequestOplockCompletedAsyncIoCallback(_FLT_CALLBACK_DATA *,void *)

- ea: `0x1400768b0`
- end: `0x1400769a3`
- name: `?RequestOplockCompletedAsyncIoCallback@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z`
- size: `243`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056a50`
- `0x1400579a4`
- `0x1400768b0`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007696b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007696b`
- `FLTMGR!FltFreeCallbackData` at `0x1400768f6`
- `FLTMGR!FltFreeCallbackData` at `0x1400768f6`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140076919`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140076919`

## string_xrefs

- `0x14007693f`: `UnionFs::Utils::RequestOplockCompletedAsyncIoCallback`
- `0x140076929`: `API: Could not post oplock completion work item!`

## pseudocode

```c
void __fastcall UnionFs::Utils::RequestOplockCompletedAsyncIoCallback(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_CONTEXT Context)
{
  struct _FLT_CALLBACK_DATA *v4; // rcx
  NTSTATUS v5; // eax
  const char *v6; // [rsp+28h] [rbp-310h]
  int v7[188]; // [rsp+30h] [rbp-308h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v7, 0x59F00212665uLL);
  v4 = (struct _FLT_CALLBACK_DATA *)*((_QWORD *)Context + 5);
  *((_QWORD *)Context + 5) = CallbackData;
  if ( v4 )
    FltFreeCallbackData(v4);
  v5 = FltQueueGenericWorkItem(
         *((PFLT_GENERIC_WORKITEM *)Context + 4),
         *((PVOID *)Context + 1),
         (PFLT_GENERIC_WORKITEM_ROUTINE)UnionFs::Utils::RequestOplockCompletionWorkItemRoutine,
         CriticalWorkQueue,
         Context);
  if ( v5 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v5,
      (int)v7,
      (struct UnionFs::StackEventTracer *)0x5A000212683LL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockCompletedAsyncIoCallback",
      "API: Could not post oplock completion work item!",
      v6);
    UnionFs::Utils::RequestOplockContext::~RequestOplockContext((UnionFs::Utils::RequestOplockContext *)Context);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 27, Context);
  }
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v7);
}

```

## disassembly

```asm
0x1400768b0  mov     [rsp+arg_0], rbx
0x1400768b5  push    rdi
0x1400768b6  sub     rsp, 330h
0x1400768bd  mov     rax, cs:__security_cookie
0x1400768c4  xor     rax, rsp
0x1400768c7  mov     [rsp+338h+var_18], rax
0x1400768cf  mov     rdi, rdx
0x1400768d2  mov     rbx, rcx
0x1400768d5  mov     rdx, 59F00212665h; unsigned __int64
0x1400768df  lea     rcx, [rsp+338h+var_308]; this
0x1400768e4  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x1400768e9  mov     rcx, [rdi+28h]; CallbackData
0x1400768ed  mov     [rdi+28h], rbx
0x1400768f1  test    rcx, rcx
0x1400768f4  jz      short loc_140076902
0x1400768f6  call    cs:__imp_FltFreeCallbackData
0x1400768fd  nop     dword ptr [rax+rax+00h]
0x140076902  mov     rdx, [rdi+8]; FltObject
0x140076906  lea     r8, ?RequestOplockCompletionWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z; WorkerRoutine
0x14007690d  mov     rcx, [rdi+20h]; FltWorkItem
0x140076911  xor     r9d, r9d; QueueType
0x140076914  mov     [rsp+338h+Context], rdi; Context
0x140076919  call    cs:__imp_FltQueueGenericWorkItem
0x140076920  nop     dword ptr [rax+rax+00h]
0x140076925  test    eax, eax
0x140076927  jns     short loc_140076977
0x140076929  lea     rcx, aApiCouldNotPos; "API: Could not post oplock completion w"...
0x140076930  mov     r8, 5A000212683h; struct UnionFs::StackEventTracer *
0x14007693a  mov     [rsp+338h+Context], rcx; char *
0x14007693f  lea     r9, aUnionfsUtilsRe_5; "UnionFs::Utils::RequestOplockCompletedA"...
0x140076946  mov     ecx, eax; this
0x140076948  lea     rdx, [rsp+338h+var_308]; int
0x14007694d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076952  mov     rcx, rdi; this
0x140076955  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x14007695a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140076961  mov     rdx, rdi; Entry
0x140076964  add     rcx, 0A20h; Lookaside
0x14007696b  call    cs:__imp_ExFreeToLookasideListEx
0x140076972  nop     dword ptr [rax+rax+00h]
0x140076977  lea     rcx, [rsp+338h+var_308]; this
0x14007697c  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140076981  mov     rcx, [rsp+338h+var_18]
0x140076989  xor     rcx, rsp; StackCookie
0x14007698c  call    __security_check_cookie
0x140076991  mov     rbx, [rsp+338h+arg_0]
0x140076999  add     rsp, 330h
0x1400769a0  pop     rdi
0x1400769a1  retn
```
