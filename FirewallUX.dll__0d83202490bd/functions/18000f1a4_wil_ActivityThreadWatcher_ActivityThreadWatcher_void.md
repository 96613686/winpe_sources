# wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)

- ea: `0x18000f1a4`
- end: `0x18000f1f9`
- name: `??1ActivityThreadWatcher@wil@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(wil::ActivityThreadWatcher *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ab4c`
- `0x18002b496`
- `0x18002bb14`

## callees

- `0x180005cd8`
- `0x18000f1a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f1d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f1d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::ActivityThreadWatcher::~ActivityThreadWatcher(wil::ActivityThreadWatcher *this)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::ActivityThreadWatcher *)((char *)this + 32));
  if ( *((_BYTE *)this + 24) )
  {
    v2 = (void *)*((_QWORD *)this + 2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *((_BYTE *)this + 24) = 0;
  }
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x18000f1a4  mov     [rsp+arg_0], rbx
0x18000f1a9  mov     [rsp+arg_8], rsi
0x18000f1ae  push    rdi
0x18000f1af  sub     rsp, 20h
0x18000f1b3  mov     rsi, rcx
0x18000f1b6  add     rcx, 20h ; ' '; this
0x18000f1ba  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000f1bf  cmp     byte ptr [rsi+18h], 0
0x18000f1c3  jz      short loc_18000F1E1
0x18000f1c5  mov     rbx, [rsi+10h]
0x18000f1c9  call    cs:__imp_GetProcessHeap
0x18000f1cf  mov     r8, rbx; lpMem
0x18000f1d2  xor     edx, edx; dwFlags
0x18000f1d4  mov     rcx, rax; hHeap
0x18000f1d7  call    cs:__imp_HeapFree
0x18000f1dd  mov     byte ptr [rsi+18h], 0
0x18000f1e1  mov     rbx, [rsp+28h+arg_0]
0x18000f1e6  mov     qword ptr [rsi+10h], 0
0x18000f1ee  mov     rsi, [rsp+28h+arg_8]
0x18000f1f3  add     rsp, 20h
0x18000f1f7  pop     rdi
0x18000f1f8  retn
```
