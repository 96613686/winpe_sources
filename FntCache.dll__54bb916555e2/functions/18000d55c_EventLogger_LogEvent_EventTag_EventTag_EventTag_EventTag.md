# EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)

- ea: `0x18000d55c`
- end: `0x18000d617`
- name: `??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z`
- size: `187`
- prototype: `void __fastcall(unsigned int *, __int64, __int64, __int64)`
- caller_count: `40`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c08c`
- `0x18000d380`
- `0x18000d3f0`
- `0x18000d710`
- `0x180010338`
- `0x1800105b4`
- `0x1800109bc`
- `0x180010cc4`
- `0x180011ea0`
- `0x180041908`
- `0x180067e1c`
- `0x1800680b0`
- `0x180068b20`
- `0x180068cc0`
- `0x18006a2dc`
- `0x18008bbe0`
- `0x18008d974`
- `0x180097c00`
- `0x180098ad0`
- `0x18009f220`
- `0x1800a14cc`
- `0x1800a571c`
- `0x1800a574c`
- `0x1800a577c`
- `0x1800a57ac`
- `0x1800a5830`
- `0x1800a5860`
- `0x1800b0b54`
- `0x1800b0d60`
- `0x1800b1734`
- `0x1800b1978`
- `0x1800b1b50`
- `0x1800b1f10`
- `0x1800b39e0`
- `0x1800b54b0`
- `0x1800b55c0`
- `0x1800b5700`
- `0x1800dd05d`
- `0x1800dd130`
- `0x1800e0f7d`

## callees

- `0x18000d55c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d603`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d59f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d59f`

## pseudocode

```c
void __fastcall EventLogger::LogEvent<EventTag>(unsigned int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // r14d
  DWORD CurrentThreadId; // r15d
  _QWORD *v8; // rsi
  __int64 v9; // rbp
  _QWORD v10[9]; // [rsp+50h] [rbp-48h] BYREF

  v10[0] = 0;
  v10[1] = a4;
  v6 = *a1;
  CurrentThreadId = GetCurrentThreadId();
  if ( dword_180142E08 )
  {
    EnterCriticalSection(&EventLogger::lock_);
    v8 = (_QWORD *)EventLogger::eventSinks_;
    v9 = EventLogger::eventSinks_ + 8 * ((__int64)(*(&EventLogger::eventSinks_ + 1) - EventLogger::eventSinks_) >> 3);
    while ( v8 != (_QWORD *)v9 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, _QWORD *, int))(*(_QWORD *)*v8 + 24LL))(
        *v8,
        0,
        CurrentThreadId,
        v6,
        a2,
        a3,
        v10,
        1);
      ++v8;
    }
    LeaveCriticalSection(&EventLogger::lock_);
  }
}

```

## disassembly

```asm
0x18000d55c  mov     rax, rsp
0x18000d55f  push    rbx
0x18000d560  push    rbp
0x18000d561  push    rsi
0x18000d562  push    rdi
0x18000d563  push    r14
0x18000d565  push    r15
0x18000d567  sub     rsp, 68h
0x18000d56b  mov     rbx, r8
0x18000d56e  mov     rdi, rdx
0x18000d571  xor     esi, esi
0x18000d573  mov     [rax-48h], rsi
0x18000d577  mov     [rax-40h], r9
0x18000d57b  movaps  xmm0, xmmword ptr [rax-48h]
0x18000d57f  movdqa  xmmword ptr [rax-48h], xmm0
0x18000d584  mov     r14d, [rcx]
0x18000d587  call    cs:__imp_GetCurrentThreadId
0x18000d58d  mov     r15d, eax
0x18000d590  cmp     cs:dword_180142E08, esi
0x18000d596  jz      short loc_18000D60A
0x18000d598  lea     rcx, ?lock_@EventLogger@@0VLock@@A; lpCriticalSection
0x18000d59f  call    cs:__imp_EnterCriticalSection
0x18000d5a5  mov     rsi, qword ptr cs:?eventSinks_@EventLogger@@0VEventSinkVec@1@A; EventLogger::EventSinkVec EventLogger::eventSinks_
0x18000d5ac  mov     rcx, qword ptr cs:?eventSinks_@EventLogger@@0VEventSinkVec@1@A+8; EventLogger::EventSinkVec EventLogger::eventSinks_
0x18000d5b3  sub     rcx, rsi
0x18000d5b6  sar     rcx, 3
0x18000d5ba  lea     rbp, [rsi+rcx*8]
0x18000d5be  jmp     short loc_18000D5F7
0x18000d5c0  mov     rcx, [rsi]
0x18000d5c3  mov     rax, [rcx]
0x18000d5c6  mov     [rsp+98h+var_60], 1
0x18000d5ce  lea     rdx, [rsp+98h+var_48]
0x18000d5d3  mov     [rsp+98h+var_68], rdx
0x18000d5d8  mov     [rsp+98h+var_70], rbx
0x18000d5dd  mov     [rsp+98h+var_78], rdi
0x18000d5e2  mov     r9d, r14d
0x18000d5e5  mov     r8d, r15d
0x18000d5e8  xor     edx, edx
0x18000d5ea  mov     rax, [rax+18h]
0x18000d5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f3  add     rsi, 8
0x18000d5f7  cmp     rsi, rbp
0x18000d5fa  jnz     short loc_18000D5C0
0x18000d5fc  lea     rcx, ?lock_@EventLogger@@0VLock@@A; lpCriticalSection
0x18000d603  call    cs:__imp_LeaveCriticalSection
0x18000d609  nop
0x18000d60a  add     rsp, 68h
0x18000d60e  pop     r15
0x18000d610  pop     r14
0x18000d612  pop     rdi
0x18000d613  pop     rsi
0x18000d614  pop     rbp
0x18000d615  pop     rbx
0x18000d616  retn
```
