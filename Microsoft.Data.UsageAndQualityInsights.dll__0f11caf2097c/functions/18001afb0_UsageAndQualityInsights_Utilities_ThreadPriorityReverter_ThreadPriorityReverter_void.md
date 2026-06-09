# UsageAndQualityInsights::Utilities::ThreadPriorityReverter::~ThreadPriorityReverter(void)

- ea: `0x18001afb0`
- end: `0x18001afcf`
- name: `??1ThreadPriorityReverter@Utilities@UsageAndQualityInsights@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(UsageAndQualityInsights::Utilities::ThreadPriorityReverter *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180102f63`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001afb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001afb8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001afc8`

## pseudocode

```c
void __fastcall UsageAndQualityInsights::Utilities::ThreadPriorityReverter::~ThreadPriorityReverter(
        UsageAndQualityInsights::Utilities::ThreadPriorityReverter *this)
{
  int v1; // ebx
  HANDLE CurrentThread; // rax

  v1 = *(_DWORD *)this;
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, v1);
}

```

## disassembly

```asm
0x18001afb0  push    rbx
0x18001afb2  sub     rsp, 20h
0x18001afb6  mov     ebx, [rcx]
0x18001afb8  call    cs:__imp_GetCurrentThread
0x18001afbe  mov     rcx, rax
0x18001afc1  mov     edx, ebx
0x18001afc3  add     rsp, 20h
0x18001afc7  pop     rbx
0x18001afc8  jmp     cs:__imp_SetThreadPriority
```
