# UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)

- ea: `0x140069db0`
- end: `0x140069edf`
- name: `?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z`
- size: `303`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056bd0`
- `0x140069db0`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069ea3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069ea3`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140069e0b`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140069e0b`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069e86`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069e86`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140069e6c`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140069e6c`

## string_xrefs

- `0x140069e21`: `API: Queueing oplock completion work item`
- `0x140069e47`: `UnionFs::Utils::CheckOplockComplete`

## pseudocode

```c
void __fastcall UnionFs::Utils::CheckOplockComplete(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_DEFERRED_IO_WORKITEM *Context)
{
  int Status; // ebx
  const char *v5; // rax
  __int64 v6; // r8
  struct _FLT_DEFERRED_IO_WORKITEM *v7; // rcx
  const char *v8; // [rsp+28h] [rbp-310h]
  int v9[188]; // [rsp+30h] [rbp-308h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v9, 0x6D6002127C9uLL);
  Status = CallbackData->IoStatus.Status;
  if ( Status )
  {
    if ( Status >= 0 )
      goto LABEL_7;
    v5 = "API: Oplock break failed";
    v6 = 0x6D7002127F2LL;
  }
  else
  {
    Status = FltQueueDeferredIoWorkItem(
               Context[1],
               CallbackData,
               (PFLT_DEFERRED_IO_WORKITEM_ROUTINE)UnionFs::Utils::OplockCompleteWorkItemRoutine,
               CriticalWorkQueue,
               Context);
    if ( Status >= 0 )
      goto LABEL_11;
    v5 = "API: Queueing oplock completion work item";
    v6 = 0x6D8002127E5LL;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)Status,
    (int)v9,
    (struct UnionFs::StackEventTracer *)v6,
    (unsigned __int64)"UnionFs::Utils::CheckOplockComplete",
    v5,
    v8);
LABEL_7:
  CallbackData->IoStatus.Status = Status;
  FltCompletePendedPreOperation(CallbackData, FLT_PREOP_COMPLETE, 0);
  if ( Context )
  {
    v7 = Context[1];
    if ( v7 )
      FltFreeDeferredIoWorkItem(v7);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, Context);
  }
LABEL_11:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v9);
}

```

## disassembly

```asm
0x140069db0  mov     [rsp+arg_8], rbx
0x140069db5  mov     [rsp+arg_10], rsi
0x140069dba  push    rdi
0x140069dbb  sub     rsp, 330h
0x140069dc2  mov     rax, cs:__security_cookie
0x140069dc9  xor     rax, rsp
0x140069dcc  mov     [rsp+338h+var_18], rax
0x140069dd4  mov     rdi, rdx
0x140069dd7  mov     rsi, rcx
0x140069dda  mov     rdx, 6D6002127C9h; unsigned __int64
0x140069de4  lea     rcx, [rsp+338h+var_308]; this
0x140069de9  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140069dee  mov     ebx, [rsi+18h]
0x140069df1  test    ebx, ebx
0x140069df3  jnz     short loc_140069E34
0x140069df5  mov     rcx, [rdi+8]; FltWorkItem
0x140069df9  lea     r8, ?OplockCompleteWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_DEFERRED_IO_WORKITEM@@PEAU_FLT_CALLBACK_DATA@@PEAX@Z; WorkerRoutine
0x140069e00  xor     r9d, r9d; QueueType
0x140069e03  mov     [rsp+338h+Context], rdi; Context
0x140069e08  mov     rdx, rsi; Data
0x140069e0b  call    cs:__imp_FltQueueDeferredIoWorkItem
0x140069e12  nop     dword ptr [rax+rax+00h]
0x140069e17  mov     ebx, eax
0x140069e19  test    eax, eax
0x140069e1b  jns     loc_140069EAF
0x140069e21  lea     rax, aApiQueueingOpl; "API: Queueing oplock completion work it"...
0x140069e28  mov     r8, 6D8002127E5h
0x140069e32  jmp     short loc_140069E47
0x140069e34  jns     short loc_140069E5F
0x140069e36  lea     rax, aApiOplockBreak_0; "API: Oplock break failed"
0x140069e3d  mov     r8, 6D7002127F2h; struct UnionFs::StackEventTracer *
0x140069e47  lea     r9, aUnionfsUtilsCh_2; "UnionFs::Utils::CheckOplockComplete"
0x140069e4e  mov     [rsp+338h+Context], rax; char *
0x140069e53  lea     rdx, [rsp+338h+var_308]; int
0x140069e58  mov     ecx, ebx; this
0x140069e5a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069e5f  xor     r8d, r8d; Context
0x140069e62  mov     [rsi+18h], ebx
0x140069e65  mov     rcx, rsi; CallbackData
0x140069e68  lea     edx, [r8+4]; CallbackStatus
0x140069e6c  call    cs:__imp_FltCompletePendedPreOperation
0x140069e73  nop     dword ptr [rax+rax+00h]
0x140069e78  test    rdi, rdi
0x140069e7b  jz      short loc_140069EAF
0x140069e7d  mov     rcx, [rdi+8]; FltWorkItem
0x140069e81  test    rcx, rcx
0x140069e84  jz      short loc_140069E92
0x140069e86  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069e8d  nop     dword ptr [rax+rax+00h]
0x140069e92  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069e99  mov     rdx, rdi; Entry
0x140069e9c  add     rcx, 0A80h; Lookaside
0x140069ea3  call    cs:__imp_ExFreeToLookasideListEx
0x140069eaa  nop     dword ptr [rax+rax+00h]
0x140069eaf  lea     rcx, [rsp+338h+var_308]; this
0x140069eb4  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140069eb9  mov     rcx, [rsp+338h+var_18]
0x140069ec1  xor     rcx, rsp; StackCookie
0x140069ec4  call    __security_check_cookie
0x140069ec9  lea     r11, [rsp+338h+var_8]
0x140069ed1  mov     rbx, [r11+18h]
0x140069ed5  mov     rsi, [r11+20h]
0x140069ed9  mov     rsp, r11
0x140069edc  pop     rdi
0x140069edd  retn
```
