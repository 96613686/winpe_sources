# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x1800a3064`
- end: `0x1800a3121`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a31a0`

## callees

- `0x1800021f0`
- `0x1800022b0`
- `0x180003044`
- `0x1800a3064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a3101`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a3101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a307a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a307a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a309f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a30d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a309f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a30d6`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  CallStackContext *v2; // rsi
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
0x1800a3064  mov     [rsp+arg_0], rbx
0x1800a3069  mov     [rsp+arg_8], rsi
0x1800a306e  push    rdi
0x1800a306f  sub     rsp, 20h
0x1800a3073  mov     rdi, rcx
0x1800a3076  add     rcx, 10h; lpCriticalSection
0x1800a307a  call    cs:__imp_EnterCriticalSection
0x1800a3081  nop     dword ptr [rax+rax+00h]
0x1800a3086  mov     rsi, [rdi+38h]
0x1800a308a  test    rsi, rsi
0x1800a308d  jnz     short loc_1800A30BD
0x1800a308f  inc     dword ptr [rdi+44h]
0x1800a3092  mov     ecx, 7F8h; Size
0x1800a3097  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a309c  mov     rsi, rax
0x1800a309f  call    cs:__imp_GetCurrentThreadId
0x1800a30a6  nop     dword ptr [rax+rax+00h]
0x1800a30ab  mov     r8d, 7Ch ; '|'; unsigned int
0x1800a30b1  mov     rcx, rsi; this
0x1800a30b4  mov     edx, eax; unsigned int
0x1800a30b6  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x1800a30bb  jmp     short loc_1800A30F2
0x1800a30bd  mov     rax, [rsi+7F0h]
0x1800a30c4  mov     [rdi+38h], rax
0x1800a30c8  mov     qword ptr [rsi+7F0h], 0
0x1800a30d3  dec     dword ptr [rdi+40h]
0x1800a30d6  call    cs:__imp_GetCurrentThreadId
0x1800a30dd  nop     dword ptr [rax+rax+00h]
0x1800a30e2  mov     r8d, 7Ch ; '|'; unsigned int
0x1800a30e8  mov     rcx, rsi; this
0x1800a30eb  mov     edx, eax; unsigned int
0x1800a30ed  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x1800a30f2  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800a30f6  mov     qword ptr [rsi+7F0h], 0
0x1800a3101  call    cs:__imp_LeaveCriticalSection
0x1800a3108  nop     dword ptr [rax+rax+00h]
0x1800a310d  mov     rbx, [rsp+28h+arg_0]
0x1800a3112  mov     rax, rsi
0x1800a3115  mov     rsi, [rsp+28h+arg_8]
0x1800a311a  add     rsp, 20h
0x1800a311e  pop     rdi
0x1800a311f  retn
```
