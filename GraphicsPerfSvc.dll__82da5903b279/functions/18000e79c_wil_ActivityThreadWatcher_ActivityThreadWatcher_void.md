# wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)

- ea: `0x18000e79c`
- end: `0x18000e7f1`
- name: `??1ActivityThreadWatcher@wil@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(wil::ActivityThreadWatcher *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180010070`
- `0x180010880`
- `0x180011630`
- `0x18002f7b2`
- `0x18002f874`
- `0x18002f9a2`

## callees

- `0x18000e79c`
- `0x18000e884`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7c1`

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
0x18000e79c  mov     [rsp+arg_0], rbx
0x18000e7a1  mov     [rsp+arg_8], rsi
0x18000e7a6  push    rdi
0x18000e7a7  sub     rsp, 20h
0x18000e7ab  mov     rsi, rcx
0x18000e7ae  add     rcx, 20h ; ' '; this
0x18000e7b2  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000e7b7  cmp     byte ptr [rsi+18h], 0
0x18000e7bb  jz      short loc_18000E7D9
0x18000e7bd  mov     rbx, [rsi+10h]
0x18000e7c1  call    cs:__imp_GetProcessHeap
0x18000e7c7  mov     r8, rbx; lpMem
0x18000e7ca  xor     edx, edx; dwFlags
0x18000e7cc  mov     rcx, rax; hHeap
0x18000e7cf  call    cs:__imp_HeapFree
0x18000e7d5  mov     byte ptr [rsi+18h], 0
0x18000e7d9  mov     rbx, [rsp+28h+arg_0]
0x18000e7de  mov     qword ptr [rsi+10h], 0
0x18000e7e6  mov     rsi, [rsp+28h+arg_8]
0x18000e7eb  add     rsp, 20h
0x18000e7ef  pop     rdi
0x18000e7f0  retn
```
