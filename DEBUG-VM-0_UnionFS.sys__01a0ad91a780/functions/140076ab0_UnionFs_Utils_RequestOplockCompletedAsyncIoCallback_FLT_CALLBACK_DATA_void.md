# UnionFs::Utils::RequestOplockCompletedAsyncIoCallback(_FLT_CALLBACK_DATA *,void *)

- ea: `0x140076ab0`
- end: `0x140076ba3`
- name: `?RequestOplockCompletedAsyncIoCallback@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z`
- size: `243`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056bd0`
- `0x140057b24`
- `0x140076ab0`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076b6b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076b6b`
- `FLTMGR!FltFreeCallbackData` at `0x140076af6`
- `FLTMGR!FltFreeCallbackData` at `0x140076af6`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140076b19`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140076b19`

## string_xrefs

- `0x140076b3f`: `UnionFs::Utils::RequestOplockCompletedAsyncIoCallback`
- `0x140076b29`: `API: Could not post oplock completion work item!`

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

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v7, 0x59F0021269BuLL);
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
      (struct UnionFs::StackEventTracer *)0x5A0002126B9LL,
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
0x140076ab0  mov     [rsp+arg_0], rbx
0x140076ab5  push    rdi
0x140076ab6  sub     rsp, 330h
0x140076abd  mov     rax, cs:__security_cookie
0x140076ac4  xor     rax, rsp
0x140076ac7  mov     [rsp+338h+var_18], rax
0x140076acf  mov     rdi, rdx
0x140076ad2  mov     rbx, rcx
0x140076ad5  mov     rdx, 59F0021269Bh; unsigned __int64
0x140076adf  lea     rcx, [rsp+338h+var_308]; this
0x140076ae4  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140076ae9  mov     rcx, [rdi+28h]; CallbackData
0x140076aed  mov     [rdi+28h], rbx
0x140076af1  test    rcx, rcx
0x140076af4  jz      short loc_140076B02
0x140076af6  call    cs:__imp_FltFreeCallbackData
0x140076afd  nop     dword ptr [rax+rax+00h]
0x140076b02  mov     rdx, [rdi+8]; FltObject
0x140076b06  lea     r8, ?RequestOplockCompletionWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z; WorkerRoutine
0x140076b0d  mov     rcx, [rdi+20h]; FltWorkItem
0x140076b11  xor     r9d, r9d; QueueType
0x140076b14  mov     [rsp+338h+Context], rdi; Context
0x140076b19  call    cs:__imp_FltQueueGenericWorkItem
0x140076b20  nop     dword ptr [rax+rax+00h]
0x140076b25  test    eax, eax
0x140076b27  jns     short loc_140076B77
0x140076b29  lea     rcx, aApiCouldNotPos; "API: Could not post oplock completion w"...
0x140076b30  mov     r8, 5A0002126B9h; struct UnionFs::StackEventTracer *
0x140076b3a  mov     [rsp+338h+Context], rcx; char *
0x140076b3f  lea     r9, aUnionfsUtilsRe_5; "UnionFs::Utils::RequestOplockCompletedA"...
0x140076b46  mov     ecx, eax; this
0x140076b48  lea     rdx, [rsp+338h+var_308]; int
0x140076b4d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076b52  mov     rcx, rdi; this
0x140076b55  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140076b5a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140076b61  mov     rdx, rdi; Entry
0x140076b64  add     rcx, 0A20h; Lookaside
0x140076b6b  call    cs:__imp_ExFreeToLookasideListEx
0x140076b72  nop     dword ptr [rax+rax+00h]
0x140076b77  lea     rcx, [rsp+338h+var_308]; this
0x140076b7c  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140076b81  mov     rcx, [rsp+338h+var_18]
0x140076b89  xor     rcx, rsp; StackCookie
0x140076b8c  call    __security_check_cookie
0x140076b91  mov     rbx, [rsp+338h+arg_0]
0x140076b99  add     rsp, 330h
0x140076ba0  pop     rdi
0x140076ba1  retn
```
