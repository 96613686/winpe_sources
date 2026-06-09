# FltQueueGenericWorkItem

- ea: `0x18001d2e0`
- end: `0x18001d440`
- name: `FltQueueGenericWorkItem`
- size: `352`
- prototype: `NTSTATUS __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PFLT_GENERIC_WORKITEM_ROUTINE WorkerRoutine, WORK_QUEUE_TYPE QueueType, PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800804a0`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x1800147b0`
- `0x18001d2e0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18001d412`
- `ntoskrnl!ExQueueWorkItem` at `0x18001d412`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18001d346`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18001d346`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001d359`
- `ntoskrnl!IoGetActivityIdThread` at `0x18001d359`

## pseudocode

```c
NTSTATUS __stdcall FltQueueGenericWorkItem(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        PVOID FltObject,
        PFLT_GENERIC_WORKITEM_ROUTINE WorkerRoutine,
        WORK_QUEUE_TYPE QueueType,
        PVOID Context)
{
  _GUID *ActivityIdThread; // rax
  unsigned int v11; // esi
  int v12; // ecx

  if ( (*(_DWORD *)FltObject & 0x1000000) == 0 && (*(_DWORD *)FltObject & 0x2000000) == 0 )
    return -1073741584;
  FltWorkItem->IoPriorityInfo.Size = 16;
  *(_QWORD *)&FltWorkItem->IoPriorityInfo.ThreadPriority = 0xFFFF;
  FltWorkItem->IoPriorityInfo.IoPriority = IoPriorityNormal;
  IoRetrievePriorityInfo(0, 0, KeGetCurrentThread(), &FltWorkItem->IoPriorityInfo);
  FltWorkItem->IoPriorityInfo.ThreadPriority = -1;
  ActivityIdThread = (_GUID *)IoGetActivityIdThread();
  if ( ActivityIdThread )
    FltWorkItem->ActivityId = *ActivityIdThread;
  v11 = FltObjectReference(FltObject);
  if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\worksup.c", 851, 3223060491LL) < 0 )
    return v11;
  if ( (byte_180040A44 & 1) != 0 )
    McTemplateU0spdpppd_EtwWriteTransfer(
      v12,
      (unsigned int)WorkSup_c860,
      (unsigned int)"FltQueueGenericWorkItem",
      (_DWORD)FltWorkItem,
      QueueType,
      (char)FltObject,
      (char)WorkerRoutine,
      (char)Context,
      FltWorkItem->IoPriorityInfo.IoPriority);
  FltWorkItem->FltWork.WorkItem.Parameter = FltWorkItem;
  FltWorkItem->FltWork.WorkItem.WorkerRoutine = (void (__fastcall *)(void *))FltpProcessGenericWorkItem;
  FltWorkItem->FltWork.WorkItem.List.Flink = 0;
  FltWorkItem->FltObject = (_FLT_OBJECT *)FltObject;
  FltWorkItem->DeferredWorkerRoutine = (void (__fastcall *)(_FLT_DEFERRED_IO_WORKITEM *, _FLT_CALLBACK_DATA *, void *))WorkerRoutine;
  FltWorkItem->Context = Context;
  FltWorkItem->QueueType = QueueType;
  ExQueueWorkItem(&FltWorkItem->FltWork.WorkItem, QueueType);
  return 0;
}

```

## disassembly

```asm
0x18001d2e0  push    rbx
0x18001d2e2  push    rbp
0x18001d2e3  push    rdi
0x18001d2e4  push    r14
0x18001d2e6  sub     rsp, 58h
0x18001d2ea  mov     eax, [rdx]
0x18001d2ec  mov     ebp, r9d
0x18001d2ef  mov     r14, r8
0x18001d2f2  mov     rdi, rdx
0x18001d2f5  mov     rbx, rcx
0x18001d2f8  bt      eax, 18h
0x18001d2fc  jb      short loc_18001D316
0x18001d2fe  mov     eax, [rdx]
0x18001d300  bt      eax, 19h
0x18001d304  jb      short loc_18001D316
0x18001d306  mov     eax, 0C00000F0h
0x18001d30b  add     rsp, 58h
0x18001d30f  pop     r14
0x18001d311  pop     rdi
0x18001d312  pop     rbp
0x18001d313  pop     rbx
0x18001d314  retn
0x18001d316  lea     r9, [rcx+40h]; PriorityInfo
0x18001d31a  xor     edx, edx; FileObject
0x18001d31c  mov     dword ptr [r9], 10h
0x18001d323  xor     ecx, ecx; Irp
0x18001d325  mov     qword ptr [r9+4], 0FFFFh
0x18001d32d  mov     dword ptr [r9+0Ch], 2
0x18001d335  mov     r8, gs:188h; Thread
0x18001d33e  mov     [rsp+78h+arg_0], rsi
0x18001d346  call    cs:__imp_IoRetrievePriorityInfo
0x18001d34d  nop     dword ptr [rax+rax+00h]
0x18001d352  mov     dword ptr [rbx+44h], 0FFFFFFFFh
0x18001d359  call    cs:__imp_IoGetActivityIdThread
0x18001d360  nop     dword ptr [rax+rax+00h]
0x18001d365  test    rax, rax
0x18001d368  jz      short loc_18001D371
0x18001d36a  movups  xmm0, xmmword ptr [rax]
0x18001d36d  movups  xmmword ptr [rbx+50h], xmm0
0x18001d371  mov     rcx, rdi; FltObject
0x18001d374  call    FltObjectReference
0x18001d379  mov     r8d, 353h
0x18001d37f  mov     [rsp+78h+var_58], 0
0x18001d388  mov     r9d, 0C01C000Bh
0x18001d38e  lea     rdx, aMinkernelFsFil_5; "minkernel\\fs\\filtermgr\\filter\\works"...
0x18001d395  mov     ecx, eax
0x18001d397  mov     esi, eax
0x18001d399  call    FltpDbgStatus
0x18001d39e  test    eax, eax
0x18001d3a0  jns     short loc_18001D3A6
0x18001d3a2  mov     eax, esi
0x18001d3a4  jmp     short loc_18001D420
0x18001d3a6  test    cs:byte_180040A44, 1
0x18001d3ad  mov     rsi, [rsp+78h+Context]
0x18001d3b5  jz      short loc_18001D3E7
0x18001d3b7  mov     eax, [rbx+4Ch]
0x18001d3ba  lea     r8, aFltqueuegeneri; "FltQueueGenericWorkItem"
0x18001d3c1  mov     [rsp+78h+var_38], eax
0x18001d3c5  lea     rdx, WorkSup_c860
0x18001d3cc  mov     [rsp+78h+var_40], rsi
0x18001d3d1  mov     r9, rbx
0x18001d3d4  mov     [rsp+78h+var_48], r14
0x18001d3d9  mov     [rsp+78h+var_50], rdi
0x18001d3de  mov     dword ptr [rsp+78h+var_58], ebp
0x18001d3e2  call    McTemplateU0spdpppd_EtwWriteTransfer
0x18001d3e7  lea     rcx, [rbx+8]; WorkItem
0x18001d3eb  mov     edx, ebp; QueueType
0x18001d3ed  lea     rax, FltpProcessGenericWorkItem
0x18001d3f4  mov     [rcx+18h], rbx
0x18001d3f8  mov     [rcx+10h], rax
0x18001d3fc  mov     qword ptr [rcx], 0
0x18001d403  mov     [rbx+60h], rdi
0x18001d407  mov     [rbx+30h], r14
0x18001d40b  mov     [rbx+38h], rsi
0x18001d40f  mov     [rbx+28h], ebp
0x18001d412  call    cs:__imp_ExQueueWorkItem
0x18001d419  nop     dword ptr [rax+rax+00h]
0x18001d41e  xor     eax, eax
0x18001d420  mov     rsi, [rsp+78h+arg_0]
0x18001d428  add     rsp, 58h
0x18001d42c  pop     r14
0x18001d42e  pop     rdi
0x18001d42f  pop     rbp
0x18001d430  pop     rbx
0x18001d431  retn
```
