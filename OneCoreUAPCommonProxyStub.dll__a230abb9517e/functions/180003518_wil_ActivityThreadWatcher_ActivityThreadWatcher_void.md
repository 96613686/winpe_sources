# wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)

- ea: `0x180003518`
- end: `0x18000356d`
- name: `??1ActivityThreadWatcher@wil@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(wil::ActivityThreadWatcher *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000314c`
- `0x18000a500`
- `0x18000b2c2`
- `0x18000b6eb`

## callees

- `0x180003518`
- `0x180003574`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000354b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000354b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000353d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000353d`

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
0x180003518  mov     [rsp+arg_0], rbx
0x18000351d  mov     [rsp+arg_8], rsi
0x180003522  push    rdi
0x180003523  sub     rsp, 20h
0x180003527  mov     rsi, rcx
0x18000352a  add     rcx, 20h ; ' '; this
0x18000352e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180003533  cmp     byte ptr [rsi+18h], 0
0x180003537  jz      short loc_180003555
0x180003539  mov     rbx, [rsi+10h]
0x18000353d  call    cs:__imp_GetProcessHeap
0x180003543  mov     r8, rbx; lpMem
0x180003546  xor     edx, edx; dwFlags
0x180003548  mov     rcx, rax; hHeap
0x18000354b  call    cs:__imp_HeapFree
0x180003551  mov     byte ptr [rsi+18h], 0
0x180003555  mov     rbx, [rsp+28h+arg_0]
0x18000355a  mov     qword ptr [rsi+10h], 0
0x180003562  mov     rsi, [rsp+28h+arg_8]
0x180003567  add     rsp, 20h
0x18000356b  pop     rdi
0x18000356c  retn
```
