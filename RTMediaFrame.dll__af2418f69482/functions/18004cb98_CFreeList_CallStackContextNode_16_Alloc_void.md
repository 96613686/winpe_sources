# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x18004cb98`
- end: `0x18004cc3c`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004ccc0`

## callees

- `0x18001ab84`
- `0x18001acd8`
- `0x1800272a0`
- `0x18004cb98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004cbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004cbfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004cbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004cbfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cbae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cbae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc23`

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
0x18004cb98  mov     [rsp+arg_0], rbx
0x18004cb9d  mov     [rsp+arg_8], rsi
0x18004cba2  push    rdi
0x18004cba3  sub     rsp, 20h
0x18004cba7  mov     rbx, rcx
0x18004cbaa  add     rcx, 10h; lpCriticalSection
0x18004cbae  call    cs:__imp_EnterCriticalSection
0x18004cbb4  mov     rdi, [rbx+38h]
0x18004cbb8  test    rdi, rdi
0x18004cbbb  jnz     short loc_18004CBE5
0x18004cbbd  inc     dword ptr [rbx+44h]
0x18004cbc0  mov     ecx, 7F8h; Size
0x18004cbc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004cbca  mov     rdi, rax
0x18004cbcd  call    cs:__imp_GetCurrentThreadId
0x18004cbd3  mov     r8d, 7Ch ; '|'; unsigned int
0x18004cbd9  mov     rcx, rdi; this
0x18004cbdc  mov     edx, eax; unsigned int
0x18004cbde  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x18004cbe3  jmp     short loc_18004CC14
0x18004cbe5  mov     rax, [rdi+7F0h]
0x18004cbec  mov     [rbx+38h], rax
0x18004cbf0  mov     qword ptr [rdi+7F0h], 0
0x18004cbfb  dec     dword ptr [rbx+40h]
0x18004cbfe  call    cs:__imp_GetCurrentThreadId
0x18004cc04  mov     r8d, 7Ch ; '|'; unsigned int
0x18004cc0a  mov     rcx, rdi; this
0x18004cc0d  mov     edx, eax; unsigned int
0x18004cc0f  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x18004cc14  lea     rcx, [rbx+10h]; lpCriticalSection
0x18004cc18  mov     qword ptr [rdi+7F0h], 0
0x18004cc23  call    cs:__imp_LeaveCriticalSection
0x18004cc29  mov     rbx, [rsp+28h+arg_0]
0x18004cc2e  mov     rax, rdi
0x18004cc31  mov     rsi, [rsp+28h+arg_8]
0x18004cc36  add     rsp, 20h
0x18004cc3a  pop     rdi
0x18004cc3b  retn
```
