# WorkPool::EnqueueOnThreadPool(IThreadCall *)

- ea: `0x180002834`
- end: `0x180002929`
- name: `?EnqueueOnThreadPool@WorkPool@@SAJPEAVIThreadCall@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(struct IThreadCall *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800020c0`

## callees

- `0x180002834`
- `0x180002930`
- `0x18000296c`
- `0x1800029d8`
- `0x180003d54`
- `0x180012654`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000284f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000284f`

## string_xrefs

- `0x1800028d6`: `com\complus\src\events\tier1\workpool.cpp`
- `0x1800028ed`: `com\complus\src\events\tier1\workpool.cpp`
- `0x180002914`: `com\complus\src\events\tier1\workpool.cpp`
- `0x1800028cf`: `(1 == pEventThreadWorker->QueueTo(DelayedWorkQueue))`
- `0x18000290d`: `(0 != pIThreadCall)`

## pseudocode

```c
__int64 __fastcall WorkPool::EnqueueOnThreadPool(struct IThreadCall *a1)
{
  struct WorkerQueueItem *v2; // rax
  struct WorkerQueueItem *v3; // rbx
  WORK_QUEUE *Queue; // rax
  WORK_QUEUE *v5; // rdi
  int v6; // ebx

  if ( !a1 )
    InternalAssert(L"com\\complus\\src\\events\\tier1\\workpool.cpp", 0x3Du, 0x10u, L"(0 != pIThreadCall)");
  v2 = (struct WorkerQueueItem *)CoTaskMemAlloc(0x30u);
  v3 = v2;
  if ( v2 )
  {
    *((_QWORD *)v2 + 3) = v2;
    *((_QWORD *)v2 + 2) = AutoDeleteWorker::DoWork;
    *(_QWORD *)v2 = 0;
    *((_QWORD *)v2 + 4) = EventThreadWorkerFunction;
    *((_QWORD *)v2 + 5) = a1;
    (*(void (__fastcall **)(struct IThreadCall *))(*(_QWORD *)a1 + 8LL))(a1);
  }
  else
  {
    InternalError(L"com\\complus\\src\\events\\tier1\\workpool.cpp", 0x3Fu, 0xC0001204, 0x12u);
    v3 = 0;
  }
  Queue = (WORK_QUEUE *)WorkerQueues::GetQueue();
  v5 = Queue;
  if ( !Queue || (v6 = WORK_QUEUE::Add(Queue, v3), WORK_QUEUE::Release(v5), v6 != 1) )
    InternalAssert(
      L"com\\complus\\src\\events\\tier1\\workpool.cpp",
      0x40u,
      0x10u,
      L"(1 == pEventThreadWorker->QueueTo(DelayedWorkQueue))");
  return 0;
}

```

## disassembly

```asm
0x180002834  mov     [rsp+arg_0], rbx
0x180002839  push    rdi
0x18000283a  sub     rsp, 20h
0x18000283e  mov     rdi, rcx
0x180002841  test    rcx, rcx
0x180002844  jz      loc_180002907
0x18000284a  mov     ecx, 30h ; '0'; cb
0x18000284f  call    cs:__imp_CoTaskMemAlloc
0x180002855  mov     rbx, rax
0x180002858  test    rax, rax
0x18000285b  jz      loc_1800028E8
0x180002861  lea     rax, ?DoWork@AutoDeleteWorker@@CAXPEAX@Z; AutoDeleteWorker::DoWork(void *)
0x180002868  mov     [rbx+18h], rbx
0x18000286c  mov     [rbx+10h], rax
0x180002870  mov     rcx, rdi
0x180002873  lea     rax, ?EventThreadWorkerFunction@@YAXPEAX@Z; EventThreadWorkerFunction(void *)
0x18000287a  mov     qword ptr [rbx], 0
0x180002881  mov     [rbx+20h], rax
0x180002885  mov     [rbx+28h], rdi
0x180002889  mov     rax, [rdi]
0x18000288c  mov     rax, [rax+8]
0x180002890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002895  call    ?GetQueue@WorkerQueues@@QEAAPEAVWORK_QUEUE@@W4_WORK_QUEUE_TYPE@@@Z; WorkerQueues::GetQueue(_WORK_QUEUE_TYPE)
0x18000289a  mov     rdi, rax
0x18000289d  test    rax, rax
0x1800028a0  jz      short loc_1800028C9
0x1800028a2  mov     rdx, rbx; struct WorkerQueueItem *
0x1800028a5  mov     rcx, rax; this
0x1800028a8  call    ?Add@WORK_QUEUE@@QEAAHPEAVWorkerQueueItem@@@Z; WORK_QUEUE::Add(WorkerQueueItem *)
0x1800028ad  mov     rcx, rdi; this
0x1800028b0  mov     ebx, eax
0x1800028b2  call    ?Release@WORK_QUEUE@@QEAAXXZ; WORK_QUEUE::Release(void)
0x1800028b7  cmp     ebx, 1
0x1800028ba  jnz     short loc_1800028C9
0x1800028bc  mov     rbx, [rsp+28h+arg_0]
0x1800028c1  xor     eax, eax
0x1800028c3  add     rsp, 20h
0x1800028c7  pop     rdi
0x1800028c8  retn
0x1800028c9  mov     r8d, 10h; unsigned __int16
0x1800028cf  lea     r9, a1Peventthreadw; "(1 == pEventThreadWorker->QueueTo(Delay"...
0x1800028d6  lea     rcx, aComComplusSrcE_17; "com\\complus\\src\\events\\tier1\\workp"...
0x1800028dd  lea     edx, [r8+30h]; unsigned int
0x1800028e1  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x1800028e6  jmp     short loc_1800028BC
0x1800028e8  mov     edx, 3Fh ; '?'; unsigned int
0x1800028ed  lea     rcx, aComComplusSrcE_17; "com\\complus\\src\\events\\tier1\\workp"...
0x1800028f4  mov     r8d, 0C0001204h; unsigned int
0x1800028fa  lea     r9d, [rdx-2Dh]; unsigned __int16
0x1800028fe  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180002903  xor     ebx, ebx
0x180002905  jmp     short loc_180002895
0x180002907  mov     r8d, 10h; unsigned __int16
0x18000290d  lea     r9, a0Pithreadcall; "(0 != pIThreadCall)"
0x180002914  lea     rcx, aComComplusSrcE_17; "com\\complus\\src\\events\\tier1\\workp"...
0x18000291b  lea     edx, [r8+2Dh]; unsigned int
0x18000291f  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180002924  jmp     loc_18000284A
```
