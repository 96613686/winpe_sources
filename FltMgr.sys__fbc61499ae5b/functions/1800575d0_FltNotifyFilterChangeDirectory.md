# FltNotifyFilterChangeDirectory

- ea: `0x1800575d0`
- end: `0x1800576e6`
- name: `FltNotifyFilterChangeDirectory`
- size: `278`
- prototype: `void __stdcall(PNOTIFY_SYNC NotifySync, PLIST_ENTRY NotifyList, PVOID FsContext, PSTRING FullDirectoryName, BOOLEAN WatchTree, BOOLEAN IgnoreBuffer, ULONG CompletionFilter, PFLT_CALLBACK_DATA NotifyCallbackData, PCHECK_FOR_TRAVERSE_ACCESS TraverseCallback, PSECURITY_SUBJECT_CONTEXT SubjectContext, PFILTER_REPORT_CHANGE FilterCallback)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180086860`

## callees

- `0x180007230`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18005765b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005765b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800576cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800576cc`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1800576c0`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1800576c0`

## pseudocode

```c
void __stdcall FltNotifyFilterChangeDirectory(
        PNOTIFY_SYNC NotifySync,
        PLIST_ENTRY NotifyList,
        PVOID FsContext,
        PSTRING FullDirectoryName,
        BOOLEAN WatchTree,
        BOOLEAN IgnoreBuffer,
        ULONG CompletionFilter,
        PFLT_CALLBACK_DATA NotifyCallbackData,
        PCHECK_FOR_TRAVERSE_ACCESS TraverseCallback,
        PSECURITY_SUBJECT_CONTEXT SubjectContext,
        PFILTER_REPORT_CHANGE FilterCallback)
{
  struct _STRING *v12; // rsi
  IRP *NotifyIrp; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v17; // rax

  v12 = FullDirectoryName;
  LOBYTE(FullDirectoryName) = 1;
  NotifyIrp = *(IRP **)&NotifyCallbackData[-3].RequestorMode;
  FltpMoveCallbackDataToIrp(&NotifyCallbackData[-3].IoStatus.Information, NotifyIrp, 0, FullDirectoryName);
  CurrentStackLocation = NotifyIrp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v17 = NotifyIrp->Tail.Overlay.CurrentStackLocation;
  v17[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FltpFsRtlCompletionRoutine;
  v17[-1].Context = NotifyCallbackData;
  v17[-1].Control = -32;
  --NotifyIrp->CurrentLocation;
  --NotifyIrp->Tail.Overlay.CurrentStackLocation;
  KeEnterCriticalRegion();
  FsRtlNotifyFilterChangeDirectory(
    NotifySync,
    NotifyList,
    FsContext,
    v12,
    WatchTree,
    IgnoreBuffer,
    CompletionFilter,
    NotifyIrp,
    TraverseCallback,
    SubjectContext,
    FilterCallback);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1800575d0  push    rbx
0x1800575d2  push    rbp
0x1800575d3  push    rsi
0x1800575d4  push    rdi
0x1800575d5  push    r14
0x1800575d7  push    r15
0x1800575d9  sub     rsp, 68h
0x1800575dd  mov     rbx, [rsp+98h+NotifyCallbackData]
0x1800575e5  mov     r15, rcx
0x1800575e8  mov     rsi, r9
0x1800575eb  mov     rbp, r8
0x1800575ee  mov     r14, rdx
0x1800575f1  mov     r9b, 1
0x1800575f4  xor     r8d, r8d
0x1800575f7  lea     rcx, [rbx-0E8h]
0x1800575fe  mov     rdi, [rcx+30h]
0x180057602  mov     rdx, rdi
0x180057605  call    FltpMoveCallbackDataToIrp
0x18005760a  mov     rax, [rdi+0B8h]
0x180057611  lea     rcx, FltpFsRtlCompletionRoutine
0x180057618  movups  xmm0, xmmword ptr [rax]
0x18005761b  movups  xmmword ptr [rax-48h], xmm0
0x18005761f  movups  xmm1, xmmword ptr [rax+10h]
0x180057623  movups  xmmword ptr [rax-38h], xmm1
0x180057627  movups  xmm0, xmmword ptr [rax+20h]
0x18005762b  movups  xmmword ptr [rax-28h], xmm0
0x18005762f  movsd   xmm1, qword ptr [rax+30h]
0x180057634  movsd   qword ptr [rax-18h], xmm1
0x180057639  mov     byte ptr [rax-45h], 0
0x18005763d  mov     rax, [rdi+0B8h]
0x180057644  mov     [rax-10h], rcx
0x180057648  mov     [rax-8], rbx
0x18005764c  mov     byte ptr [rax-45h], 0E0h
0x180057650  dec     byte ptr [rdi+43h]
0x180057653  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x18005765b  call    cs:__imp_KeEnterCriticalRegion
0x180057662  nop     dword ptr [rax+rax+00h]
0x180057667  mov     rax, [rsp+98h+FilterCallback]
0x18005766f  mov     r9, rsi; FullDirectoryName
0x180057672  mov     [rsp+98h+var_48], rax; FilterCallback
0x180057677  mov     r8, rbp; FsContext
0x18005767a  mov     rax, [rsp+98h+SubjectContext]
0x180057682  mov     rdx, r14; NotifyList
0x180057685  mov     [rsp+98h+var_50], rax; SubjectContext
0x18005768a  mov     rcx, r15; NotifySync
0x18005768d  mov     rax, [rsp+98h+TraverseCallback]
0x180057695  mov     [rsp+98h+var_58], rax; TraverseCallback
0x18005769a  mov     eax, [rsp+98h+CompletionFilter]
0x1800576a1  mov     [rsp+98h+NotifyIrp], rdi; NotifyIrp
0x1800576a6  mov     [rsp+98h+var_68], eax; CompletionFilter
0x1800576aa  mov     al, [rsp+98h+IgnoreBuffer]
0x1800576b1  mov     [rsp+98h+var_70], al; IgnoreBuffer
0x1800576b5  mov     al, [rsp+98h+WatchTree]
0x1800576bc  mov     [rsp+98h+var_78], al; WatchTree
0x1800576c0  call    cs:__imp_FsRtlNotifyFilterChangeDirectory
0x1800576c7  nop     dword ptr [rax+rax+00h]
0x1800576cc  call    cs:__imp_KeLeaveCriticalRegion
0x1800576d3  nop     dword ptr [rax+rax+00h]
0x1800576d8  add     rsp, 68h
0x1800576dc  pop     r15
0x1800576de  pop     r14
0x1800576e0  pop     rdi
0x1800576e1  pop     rsi
0x1800576e2  pop     rbp
0x1800576e3  pop     rbx
0x1800576e4  retn
```
