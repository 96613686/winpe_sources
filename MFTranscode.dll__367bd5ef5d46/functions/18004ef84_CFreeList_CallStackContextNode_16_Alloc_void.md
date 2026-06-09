# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x18004ef84`
- end: `0x18004f03b`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004f0b0`

## callees

- `0x1800092a0`
- `0x180009370`
- `0x180017074`
- `0x18004ef84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004efc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004effb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004efc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004effb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f022`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f022`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef9d`

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
0x18004ef84  mov     [rsp+arg_0], rbx
0x18004ef89  mov     [rsp+arg_8], rsi
0x18004ef8e  push    rdi
0x18004ef8f  sub     rsp, 20h
0x18004ef93  lea     rsi, [rcx+10h]
0x18004ef97  mov     rbx, rcx
0x18004ef9a  mov     rcx, rsi; lpCriticalSection
0x18004ef9d  call    cs:__imp_EnterCriticalSection
0x18004efa3  mov     rdi, [rbx+38h]
0x18004efa7  test    rdi, rdi
0x18004efaa  jnz     short loc_18004EFE2
0x18004efac  inc     dword ptr [rbx+44h]
0x18004efaf  mov     ecx, 7F8h; Size
0x18004efb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004efb9  mov     rbx, rax
0x18004efbc  test    rax, rax
0x18004efbf  jz      short loc_18004EFDE
0x18004efc1  call    cs:__imp_GetCurrentThreadId
0x18004efc7  lea     r8d, [rdi+7Ch]; unsigned int
0x18004efcb  mov     rcx, rbx; this
0x18004efce  mov     edx, eax; unsigned int
0x18004efd0  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x18004efd5  mov     [rbx+7F0h], rdi
0x18004efdc  jmp     short loc_18004F01F
0x18004efde  xor     ebx, ebx
0x18004efe0  jmp     short loc_18004F01F
0x18004efe2  mov     rax, [rdi+7F0h]
0x18004efe9  mov     [rbx+38h], rax
0x18004efed  mov     qword ptr [rdi+7F0h], 0
0x18004eff8  dec     dword ptr [rbx+40h]
0x18004effb  call    cs:__imp_GetCurrentThreadId
0x18004f001  mov     r8d, 7Ch ; '|'; unsigned int
0x18004f007  mov     rcx, rdi; this
0x18004f00a  mov     edx, eax; unsigned int
0x18004f00c  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x18004f011  mov     qword ptr [rdi+7F0h], 0
0x18004f01c  mov     rbx, rdi
0x18004f01f  mov     rcx, rsi; lpCriticalSection
0x18004f022  call    cs:__imp_LeaveCriticalSection
0x18004f028  mov     rsi, [rsp+28h+arg_8]
0x18004f02d  mov     rax, rbx
0x18004f030  mov     rbx, [rsp+28h+arg_0]
0x18004f035  add     rsp, 20h
0x18004f039  pop     rdi
0x18004f03a  retn
```
