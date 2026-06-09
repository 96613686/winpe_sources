# EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(EventTag,EventTag)

- ea: `0x18000cd54`
- end: `0x18000ce12`
- name: `??$LogEvent@VEventTag@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXVEventTag@@0@Z`
- size: `190`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c13c`
- `0x18000c20c`
- `0x18000c564`
- `0x18000c6cc`
- `0x18000c7e0`
- `0x18000c8c8`
- `0x18000ff74`
- `0x18008ba20`
- `0x180094e68`
- `0x180095cac`
- `0x18009664c`
- `0x18009a610`
- `0x18009de0c`
- `0x1800b9b64`
- `0x1800b9f84`
- `0x1800ba124`
- `0x1800ba1ec`
- `0x1800ba4ec`
- `0x1800ba6c0`

## callees

- `0x18000cd54`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cd7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cd7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd92`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v4; // ebp
  DWORD CurrentThreadId; // r14d
  _QWORD *v6; // rdi
  __int64 v7; // rsi
  _QWORD v8[7]; // [rsp+50h] [rbp-38h] BYREF

  v8[0] = 0;
  v8[1] = a3;
  v4 = *(_DWORD *)(a1 + 16);
  CurrentThreadId = GetCurrentThreadId();
  if ( dword_180142E08 )
  {
    EnterCriticalSection(&EventLogger::lock_);
    v6 = (_QWORD *)EventLogger::eventSinks_;
    v7 = EventLogger::eventSinks_ + 8 * ((__int64)(*(&EventLogger::eventSinks_ + 1) - EventLogger::eventSinks_) >> 3);
    while ( v6 != (_QWORD *)v7 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, _QWORD *, int))(*(_QWORD *)*v6 + 24LL))(
        *v6,
        0,
        CurrentThreadId,
        v4,
        0x72765363706C41LL,
        a2,
        v8,
        1);
      ++v6;
    }
    LeaveCriticalSection(&EventLogger::lock_);
  }
}

```

## disassembly

```asm
0x18000cd54  mov     rax, rsp
0x18000cd57  push    rbx
0x18000cd58  push    rbp
0x18000cd59  push    rsi
0x18000cd5a  push    rdi
0x18000cd5b  push    r14
0x18000cd5d  sub     rsp, 60h
0x18000cd61  mov     rbx, rdx
0x18000cd64  xor     edi, edi
0x18000cd66  mov     [rax-38h], rdi
0x18000cd6a  mov     [rax-30h], r8
0x18000cd6e  movaps  xmm0, xmmword ptr [rax-38h]
0x18000cd72  movdqa  xmmword ptr [rax-38h], xmm0
0x18000cd77  mov     ebp, [rcx+10h]
0x18000cd7a  call    cs:__imp_GetCurrentThreadId
0x18000cd80  mov     r14d, eax
0x18000cd83  cmp     cs:dword_180142E08, edi
0x18000cd89  jz      short loc_18000CE07
0x18000cd8b  lea     rcx, ?lock_@EventLogger@@0VLock@@A; lpCriticalSection
0x18000cd92  call    cs:__imp_EnterCriticalSection
0x18000cd98  mov     rdi, qword ptr cs:?eventSinks_@EventLogger@@0VEventSinkVec@1@A; EventLogger::EventSinkVec EventLogger::eventSinks_
0x18000cd9f  mov     rcx, qword ptr cs:?eventSinks_@EventLogger@@0VEventSinkVec@1@A+8; EventLogger::EventSinkVec EventLogger::eventSinks_
0x18000cda6  sub     rcx, rdi
0x18000cda9  sar     rcx, 3
0x18000cdad  lea     rsi, [rdi+rcx*8]
0x18000cdb1  jmp     short loc_18000CDF4
0x18000cdb3  mov     rcx, [rdi]
0x18000cdb6  mov     rax, [rcx]
0x18000cdb9  mov     [rsp+88h+var_50], 1
0x18000cdc1  lea     rdx, [rsp+88h+var_38]
0x18000cdc6  mov     [rsp+88h+var_58], rdx
0x18000cdcb  mov     [rsp+88h+var_60], rbx
0x18000cdd0  mov     rdx, 72765363706C41h
0x18000cdda  mov     [rsp+88h+var_68], rdx
0x18000cddf  mov     r9d, ebp
0x18000cde2  mov     r8d, r14d
0x18000cde5  xor     edx, edx
0x18000cde7  mov     rax, [rax+18h]
0x18000cdeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdf0  add     rdi, 8
0x18000cdf4  cmp     rdi, rsi
0x18000cdf7  jnz     short loc_18000CDB3
0x18000cdf9  lea     rcx, ?lock_@EventLogger@@0VLock@@A; lpCriticalSection
0x18000ce00  call    cs:__imp_LeaveCriticalSection
0x18000ce06  nop
0x18000ce07  add     rsp, 60h
0x18000ce0b  pop     r14
0x18000ce0d  pop     rdi
0x18000ce0e  pop     rsi
0x18000ce0f  pop     rbp
0x18000ce10  pop     rbx
0x18000ce11  retn
```
