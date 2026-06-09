# Broker::ScopedWriteLock::Acquire(void)

- ea: `0x18000f400`
- end: `0x18000f425`
- name: `?Acquire@ScopedWriteLock@Broker@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(Broker::ScopedWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c970`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f40c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f40c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f412`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f412`

## pseudocode

```c
void __fastcall Broker::ScopedWriteLock::Acquire(Broker::ScopedWriteLock *this)
{
  RtlAcquireSRWLockExclusive(*(_QWORD *)this);
  *((_DWORD *)this + 3) = GetCurrentThreadId();
  *((_BYTE *)this + 8) = 1;
}

```

## disassembly

```asm
0x18000f400  push    rbx
0x18000f402  sub     rsp, 20h
0x18000f406  mov     rbx, rcx
0x18000f409  mov     rcx, [rcx]
0x18000f40c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000f412  call    cs:__imp_GetCurrentThreadId
0x18000f418  mov     [rbx+0Ch], eax
0x18000f41b  mov     byte ptr [rbx+8], 1
0x18000f41f  add     rsp, 20h
0x18000f423  pop     rbx
0x18000f424  retn
```
