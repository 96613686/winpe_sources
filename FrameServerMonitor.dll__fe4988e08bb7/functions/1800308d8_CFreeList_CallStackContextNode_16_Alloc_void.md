# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x1800308d8`
- end: `0x18003098f`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `183`
- prototype: `CallStackContext *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180030bf0`

## callees

- `0x18000261c`
- `0x1800308d8`
- `0x180030998`
- `0x180030fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800308f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800308f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030976`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030976`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003094f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003094f`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  CallStackContext *v3; // rdi
  CallStackContext *v4; // rbx
  DWORD v5; // eax
  DWORD CurrentThreadId; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v3 = *(CallStackContext **)(a1 + 56);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 56) = *((_QWORD *)v3 + 254);
    *((_QWORD *)v3 + 254) = 0;
    --*(_DWORD *)(a1 + 64);
    CurrentThreadId = GetCurrentThreadId();
    CallStackContext::Init(v3, CurrentThreadId, 0x7Cu);
    *((_QWORD *)v3 + 254) = 0;
    v4 = v3;
  }
  else
  {
    ++*(_DWORD *)(a1 + 68);
    v4 = (CallStackContext *)operator new(0x7F8u);
    if ( v4 )
    {
      v5 = GetCurrentThreadId();
      CallStackContext::CallStackContext(v4, v5, 0x7Cu);
      *((_QWORD *)v4 + 254) = 0;
    }
    else
    {
      v4 = 0;
    }
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x1800308d8  mov     [rsp+arg_0], rbx
0x1800308dd  mov     [rsp+arg_8], rsi
0x1800308e2  push    rdi
0x1800308e3  sub     rsp, 20h
0x1800308e7  lea     rsi, [rcx+10h]
0x1800308eb  mov     rbx, rcx
0x1800308ee  mov     rcx, rsi; lpCriticalSection
0x1800308f1  call    cs:__imp_EnterCriticalSection
0x1800308f7  mov     rdi, [rbx+38h]
0x1800308fb  test    rdi, rdi
0x1800308fe  jnz     short loc_180030936
0x180030900  inc     dword ptr [rbx+44h]
0x180030903  mov     ecx, 7F8h; Size
0x180030908  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003090d  mov     rbx, rax
0x180030910  test    rax, rax
0x180030913  jz      short loc_180030932
0x180030915  call    cs:__imp_GetCurrentThreadId
0x18003091b  lea     r8d, [rdi+7Ch]; unsigned int
0x18003091f  mov     rcx, rbx; this
0x180030922  mov     edx, eax; unsigned int
0x180030924  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x180030929  mov     [rbx+7F0h], rdi
0x180030930  jmp     short loc_180030973
0x180030932  xor     ebx, ebx
0x180030934  jmp     short loc_180030973
0x180030936  mov     rax, [rdi+7F0h]
0x18003093d  mov     [rbx+38h], rax
0x180030941  mov     qword ptr [rdi+7F0h], 0
0x18003094c  dec     dword ptr [rbx+40h]
0x18003094f  call    cs:__imp_GetCurrentThreadId
0x180030955  mov     r8d, 7Ch ; '|'; unsigned int
0x18003095b  mov     rcx, rdi; this
0x18003095e  mov     edx, eax; unsigned int
0x180030960  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x180030965  mov     qword ptr [rdi+7F0h], 0
0x180030970  mov     rbx, rdi
0x180030973  mov     rcx, rsi; lpCriticalSection
0x180030976  call    cs:__imp_LeaveCriticalSection
0x18003097c  mov     rsi, [rsp+28h+arg_8]
0x180030981  mov     rax, rbx
0x180030984  mov     rbx, [rsp+28h+arg_0]
0x180030989  add     rsp, 20h
0x18003098d  pop     rdi
0x18003098e  retn
```
