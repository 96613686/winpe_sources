# UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)

- ea: `0x140069bc0`
- end: `0x140069cef`
- name: `?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z`
- size: `303`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056a50`
- `0x140069bc0`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069cb3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069cb3`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140069c1b`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140069c1b`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069c96`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069c96`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140069c7c`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140069c7c`

## string_xrefs

- `0x140069c31`: `API: Queueing oplock completion work item`
- `0x140069c57`: `UnionFs::Utils::CheckOplockComplete`

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

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v9, 0x6D600212793uLL);
  Status = CallbackData->IoStatus.Status;
  if ( Status )
  {
    if ( Status >= 0 )
      goto LABEL_7;
    v5 = "API: Oplock break failed";
    v6 = 0x6D7002127BCLL;
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
    v6 = 0x6D8002127AFLL;
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
0x140069bc0  mov     [rsp+arg_8], rbx
0x140069bc5  mov     [rsp+arg_10], rsi
0x140069bca  push    rdi
0x140069bcb  sub     rsp, 330h
0x140069bd2  mov     rax, cs:__security_cookie
0x140069bd9  xor     rax, rsp
0x140069bdc  mov     [rsp+338h+var_18], rax
0x140069be4  mov     rdi, rdx
0x140069be7  mov     rsi, rcx
0x140069bea  mov     rdx, 6D600212793h; unsigned __int64
0x140069bf4  lea     rcx, [rsp+338h+var_308]; this
0x140069bf9  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140069bfe  mov     ebx, [rsi+18h]
0x140069c01  test    ebx, ebx
0x140069c03  jnz     short loc_140069C44
0x140069c05  mov     rcx, [rdi+8]; FltWorkItem
0x140069c09  lea     r8, ?OplockCompleteWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_DEFERRED_IO_WORKITEM@@PEAU_FLT_CALLBACK_DATA@@PEAX@Z; WorkerRoutine
0x140069c10  xor     r9d, r9d; QueueType
0x140069c13  mov     [rsp+338h+Context], rdi; Context
0x140069c18  mov     rdx, rsi; Data
0x140069c1b  call    cs:__imp_FltQueueDeferredIoWorkItem
0x140069c22  nop     dword ptr [rax+rax+00h]
0x140069c27  mov     ebx, eax
0x140069c29  test    eax, eax
0x140069c2b  jns     loc_140069CBF
0x140069c31  lea     rax, aApiQueueingOpl; "API: Queueing oplock completion work it"...
0x140069c38  mov     r8, 6D8002127AFh
0x140069c42  jmp     short loc_140069C57
0x140069c44  jns     short loc_140069C6F
0x140069c46  lea     rax, aApiOplockBreak_0; "API: Oplock break failed"
0x140069c4d  mov     r8, 6D7002127BCh; struct UnionFs::StackEventTracer *
0x140069c57  lea     r9, aUnionfsUtilsCh_2; "UnionFs::Utils::CheckOplockComplete"
0x140069c5e  mov     [rsp+338h+Context], rax; char *
0x140069c63  lea     rdx, [rsp+338h+var_308]; int
0x140069c68  mov     ecx, ebx; this
0x140069c6a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069c6f  xor     r8d, r8d; Context
0x140069c72  mov     [rsi+18h], ebx
0x140069c75  mov     rcx, rsi; CallbackData
0x140069c78  lea     edx, [r8+4]; CallbackStatus
0x140069c7c  call    cs:__imp_FltCompletePendedPreOperation
0x140069c83  nop     dword ptr [rax+rax+00h]
0x140069c88  test    rdi, rdi
0x140069c8b  jz      short loc_140069CBF
0x140069c8d  mov     rcx, [rdi+8]; FltWorkItem
0x140069c91  test    rcx, rcx
0x140069c94  jz      short loc_140069CA2
0x140069c96  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069c9d  nop     dword ptr [rax+rax+00h]
0x140069ca2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069ca9  mov     rdx, rdi; Entry
0x140069cac  add     rcx, 0A80h; Lookaside
0x140069cb3  call    cs:__imp_ExFreeToLookasideListEx
0x140069cba  nop     dword ptr [rax+rax+00h]
0x140069cbf  lea     rcx, [rsp+338h+var_308]; this
0x140069cc4  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140069cc9  mov     rcx, [rsp+338h+var_18]
0x140069cd1  xor     rcx, rsp; StackCookie
0x140069cd4  call    __security_check_cookie
0x140069cd9  lea     r11, [rsp+338h+var_8]
0x140069ce1  mov     rbx, [r11+18h]
0x140069ce5  mov     rsi, [r11+20h]
0x140069ce9  mov     rsp, r11
0x140069cec  pop     rdi
0x140069ced  retn
```
