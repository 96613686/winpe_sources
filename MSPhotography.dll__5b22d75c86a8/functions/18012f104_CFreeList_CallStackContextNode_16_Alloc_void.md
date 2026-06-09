# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x18012f104`
- end: `0x18012f1a8`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18012f3f0`

## callees

- `0x180002da0`
- `0x18012f104`
- `0x18012f1b0`
- `0x18012f7b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012f11a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012f11a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f18f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f18f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f139`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f16a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f139`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f16a`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  CallStackContext *v2; // rdi
  DWORD v3; // eax
  DWORD CurrentThreadId; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v2 = *(CallStackContext **)(a1 + 56);
  if ( v2 )
  {
    *(_QWORD *)(a1 + 56) = *((_QWORD *)v2 + 254);
    *((_QWORD *)v2 + 254) = 0;
    --*(_DWORD *)(a1 + 64);
    CurrentThreadId = GetCurrentThreadId();
    CallStackContext::Init(v2, CurrentThreadId, 0x7Cu);
  }
  else
  {
    ++*(_DWORD *)(a1 + 68);
    v2 = (CallStackContext *)operator new(0x7F8u);
    v3 = GetCurrentThreadId();
    CallStackContext::CallStackContext(v2, v3, 0x7Cu);
  }
  *((_QWORD *)v2 + 254) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  return v2;
}

```

## disassembly

```asm
0x18012f104  mov     [rsp+arg_0], rbx
0x18012f109  mov     [rsp+arg_8], rsi
0x18012f10e  push    rdi
0x18012f10f  sub     rsp, 20h
0x18012f113  mov     rbx, rcx
0x18012f116  add     rcx, 10h; lpCriticalSection
0x18012f11a  call    cs:__imp_EnterCriticalSection
0x18012f120  mov     rdi, [rbx+38h]
0x18012f124  test    rdi, rdi
0x18012f127  jnz     short loc_18012F151
0x18012f129  inc     dword ptr [rbx+44h]
0x18012f12c  mov     ecx, 7F8h; Size
0x18012f131  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012f136  mov     rdi, rax
0x18012f139  call    cs:__imp_GetCurrentThreadId
0x18012f13f  mov     r8d, 7Ch ; '|'; unsigned int
0x18012f145  mov     rcx, rdi; this
0x18012f148  mov     edx, eax; unsigned int
0x18012f14a  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x18012f14f  jmp     short loc_18012F180
0x18012f151  mov     rax, [rdi+7F0h]
0x18012f158  mov     [rbx+38h], rax
0x18012f15c  mov     qword ptr [rdi+7F0h], 0
0x18012f167  dec     dword ptr [rbx+40h]
0x18012f16a  call    cs:__imp_GetCurrentThreadId
0x18012f170  mov     r8d, 7Ch ; '|'; unsigned int
0x18012f176  mov     rcx, rdi; this
0x18012f179  mov     edx, eax; unsigned int
0x18012f17b  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x18012f180  lea     rcx, [rbx+10h]; lpCriticalSection
0x18012f184  mov     qword ptr [rdi+7F0h], 0
0x18012f18f  call    cs:__imp_LeaveCriticalSection
0x18012f195  mov     rbx, [rsp+28h+arg_0]
0x18012f19a  mov     rax, rdi
0x18012f19d  mov     rsi, [rsp+28h+arg_8]
0x18012f1a2  add     rsp, 20h
0x18012f1a6  pop     rdi
0x18012f1a7  retn
```
