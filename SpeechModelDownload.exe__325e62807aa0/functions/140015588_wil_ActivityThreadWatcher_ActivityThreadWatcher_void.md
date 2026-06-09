# wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)

- ea: `0x140015588`
- end: `0x1400155dd`
- name: `??1ActivityThreadWatcher@wil@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(wil::ActivityThreadWatcher *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c378`
- `0x14001c38a`
- `0x14001c3d2`
- `0x14001c478`

## callees

- `0x140015588`
- `0x140015794`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400155ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400155ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400155bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400155bb`

## pseudocode

```c
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
0x140015588  mov     [rsp+arg_0], rbx
0x14001558d  mov     [rsp+arg_8], rsi
0x140015592  push    rdi
0x140015593  sub     rsp, 20h
0x140015597  mov     rsi, rcx
0x14001559a  add     rcx, 20h ; ' '; this
0x14001559e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1400155a3  cmp     byte ptr [rsi+18h], 0
0x1400155a7  jz      short loc_1400155C5
0x1400155a9  mov     rbx, [rsi+10h]
0x1400155ad  call    cs:__imp_GetProcessHeap
0x1400155b3  mov     r8, rbx; lpMem
0x1400155b6  xor     edx, edx; dwFlags
0x1400155b8  mov     rcx, rax; hHeap
0x1400155bb  call    cs:__imp_HeapFree
0x1400155c1  mov     byte ptr [rsi+18h], 0
0x1400155c5  mov     rbx, [rsp+28h+arg_0]
0x1400155ca  mov     qword ptr [rsi+10h], 0
0x1400155d2  mov     rsi, [rsp+28h+arg_8]
0x1400155d7  add     rsp, 20h
0x1400155db  pop     rdi
0x1400155dc  retn
```
